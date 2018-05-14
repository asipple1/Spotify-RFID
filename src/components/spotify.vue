<template>
  <div class="container is-fluid">
    <h1 v-if="message">{{ message }}</h1>

    <h1>Currently Playing {{ song }} by {{ artist }}</h1>
    <img :src="albumImgUrl" />

    <br>
    <input type="text" v-on:keyup.enter="checkEnter" placeholder="play spotify song">

  </div>
</template>
<script>
  import firebase from 'firebase';
  // Initialize Firebase
  const config = {
    apiKey: "AIzaSyDG0X9HFUksao0tKgxYrez45pAvIEuOh9s",
    authDomain: "rfid-music-jukebox.firebaseapp.com",
    databaseURL: "https://rfid-music-jukebox.firebaseio.com",
    projectId: "rfid-music-jukebox",
    storageBucket: "rfid-music-jukebox.appspot.com",
    messagingSenderId: "284548597468"
  };
  firebase.initializeApp(config);
  // RFID array firebase
  const dbRefRFID = firebase.database().ref().child("rfid");
  // Active RFID firebase
  const dbRefActiveRFID = firebase.database().ref().child("active");


  /*******************************************
   The Following variables are for spotify
  *******************************************/

  // Get the hash of the url
  const hash = window.location.hash
    .substring(1)
    .split("&")
    .reduce(function(initial, item) {
      if (item) {
        var parts = item.split("=");
        initial[parts[0]] = decodeURIComponent(parts[1]);
      }
      return initial;
    }, {});
  window.location.hash = "";

  // Set token
  let _token = hash.access_token;
  // let _token = '';
  console.log(_token);

  const authEndpoint = "https://accounts.spotify.com/authorize";

  // Replace with your app's client ID, redirect URI and desired scopes
  const clientId = "36600d1fedd5473aa0ce196ab8ba07c0";
  const redirectUri = "http://127.0.0.1:8080/";
  const scopes = [
    "streaming",
    "user-read-birthdate",
    "user-read-private",
    "user-modify-playback-state"
  ];

  // If there is no token, redirect to Spotify authorization
  if (!_token) {
    window.location = `${authEndpoint}?client_id=${clientId}&redirect_uri=${redirectUri}&scope=${scopes.join(
      "%20"
    )}&response_type=token&show_dialog=true`;
  }


  /*******************************************
   VUE CODE
  *******************************************/

  export default {
    name: "spotify",
    data() {
      return {
        message: null,
        deviceId: null,
        webPlayerActive: false,
        songId: "spotify:track:5JtPGzRgrWxkXX9LoROq3d",
        artist: "",
        album: "",
        albumImgUrl: "",
        song: "",
        activeRFID: null,
        rfidArray: []
      };
    },
    created() {
      window.onSpotifyWebPlaybackSDKReady = () => {};
      this.putItAllTogether();

      // RFID SONG ARRAY
      dbRefRFID.on("value", snap => {
        this.rfidArray = snap.val();
      });

      // Active Song
      dbRefActiveRFID.on("value", snap => {
        this.activeRFID = snap.val();
      });

    },
    watch: {
      activeRFID: function(val) {
        if(this.webPlayerActive) {
          for(let i in this.rfidArray){
            // Check to see if active RFID value equals any RFID tag in RFID array and get song.
            if(i == val) {
              this.songId = this.rfidArray[i].song;
              this.play(this.rfidArray[i].song);
            }
            // Maybe put else to play a random song if RFID tag is not recongized
          }
        }
      }
    },
    methods: {
      waitForSpotifyWebPlaybackSDKToLoad: async function() {
        return new Promise(resolve => {
          const interval = setInterval(() => {
            if ("Spotify" in window) {
              resolve(window.Spotify);
              clearInterval(interval);
            }
          });
        });
      },
      waitUntilUserHasSelectedPlayer: async function(sdk) {
        return new Promise(resolve => {
          let interval = setInterval(async () => {
            let state = await sdk.getCurrentState();
            if (state !== null) {
              resolve(state);
              clearInterval(interval);
            }
          });
        });
      },
      play: function(songId) {
        return fetch(
          `https://api.spotify.com/v1/me/player/play?device_id=${this.deviceId}`,
          {
            method: "PUT",
            body: JSON.stringify({
              uris: [songId]
            }),
            headers: {
              Authorization: `Bearer ${_token}`
            }
          }
        );
      },
      putItAllTogether: async function() {
        const { Player } = await this.waitForSpotifyWebPlaybackSDKToLoad();

        // Create a new spotify player
        const sdk = new Player({
          name: "HAHA",
          volume: 0.8,
          getOAuthToken: callback => {
            callback(_token);
          }
        });

        // Get the device id when ready
        sdk.on("ready", data => {
          this.deviceId = data.device_id;
        });

        // Watch for changes in the player and update song variables
        sdk.on("player_state_changed", state => {
          let songData = state.track_window.current_track;
          this.artist = songData.artists[0].name;
          this.album = songData.album.name;
          this.song = songData.name;
          this.albumImgUrl = songData.album.images[0].url;
        });

        // Wait for the player to connect
        let connected = await sdk.connect();
        if (connected) {
          this.message = "Waiting for player to be selected ...";
          let state = await this.waitUntilUserHasSelectedPlayer(sdk);
          this.message = null;
          this.webPlayerActive = true;
        } else {
          console.error("Failed to connect Player");
        }
      },
      // Manually enter in Spotify Music ID
      checkEnter: function(val) {
        this.songId = val.target.value;
        this.play(this.songId);
      }
    }
  };
</script>

<style lang="scss">
  
</style>
