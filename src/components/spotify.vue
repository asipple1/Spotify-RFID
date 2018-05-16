<template>
  <div class="container is-fluid">
    <div v-if="message">{{ message }}</div>
    <div v-if="song" class="music-details">
        <h1>Playing: {{ song }}</h1>
        <h1>By: {{ artist }}</h1>
    </div>

    <!-- <br>
    <input type="text" v-on:keyup.enter="checkEnter" placeholder="play spotify song"> -->
    <div class="record-wrapper">
      <img class="record-wrapper__image" :src="albumImgUrl" />
      <svg class="record-wrapper__svg" version="1.1" id="Layer_1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px"
      viewBox="0 0 1054.8 1054.8" preserveAspectRatio="none">
      <g class="st0">
      <image style="overflow:visible;opacity:0.75;" width="53" height="59" xlink:href="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAADYAAAA8CAYAAAAt3km7AAAACXBIWXMAAAsSAAALEgHS3X78AAAA
      GXRFWHRTb2Z0d2FyZQBBZG9iZSBJbWFnZVJlYWR5ccllPAAABOhJREFUeNrsmo1uozAQhDEY0rR3
      7/+kbQLE3rtKtjQa7RobuPYqBWkFbRPg66z3D7ruuT23/2JzX3w++SlgruJv8h2w7qTvuYpzSuPP
      XwqmAVj7EpgY+9MA3Y7P4t46tlwRQazjUwDdDqga43MzxJYdhnM7oXpl3xuAGlCEfVR+b7lp9eYb
      oRhkoGOGZLBIFuhnzTXdHjjXCMVAQ/rnDGCsHioVAIgNQYWUbFbO74TKQJ82wrEnOFQMgR6KhXSt
      AOrFvcr5SlURMENNCSrvR4AcyB1FAVr/2gLHq+FBu+B8QwTsQZUp2QVsAsgB1lwHamWoJZlP+16J
      qI8jcL5SLXTBEaBe/to17RFwLIBlqHv63J0Udkk9OaKcb3C/AdbUBFCvyV7Askv2cFPofvd0jhu4
      LqcJzmeH1pgz4NwG2K+0vyabAMwB2CfUnMA+4B/gjCjKOdDVgta4Yk9BYwS3+4R4S2Bvya7pb9kd
      OwXsprisU0CiEvZjTfj3G26IarFiF3LF3wksu+UEN41gdwLvlbWk5TJRlDJVa1WMVXsB1VA5dMd8
      8QetL6+ACVUjQalWXE2v5yvXF8KNRmR8BbjsjnmdCQSPixFcMHIGStzZ+lrVfGNJNUA+swCv4I4j
      3ExIYOyCDLXSPtvQotqeIphdcqSEjbkNA0gGw5yFpdYK6QD3KynXQwDpLNVqS6qu4JqeIBGUAwiu
      KyGVFoiaM0TNfP5VaY2kJY+5AlRp/XG17ylPRYLiauSe7ArHczrHolQnRXf0xlzC7WjVS9WKA3fE
      aj+rNQPMjUozrWvQ3LG5utda+2gcS8FtHa2rSSmmJ6Wg1qCsSZnUglntvCgNopZzOB+yWtwhaEp5
      amJ5Waie1G8AWSXOo9AwZos0w+gKgYeb1lEBKs1UimBSANQS6KqE5ZXyT6B2H6+rVTQ1owarmKhe
      Y6wUVgArgc1gCxgnY1cINtpwqKSU21sramsrUCu/UES7Q5GrNZzOGNS4nbPLpqjINVgJ6g5gN+ik
      J2og83l7CPuPwnyxU9bmaXNFbRYYqK+aIe9oUW2gHOapP8M1u9WuHAKTwqDTUuxiJFWeeWhtzAzB
      xwKNe0B95ZMRngmuUO7caPTGfRZX9j2BceDhqFoaoErrGnPU0TrFFX1STBuWOiUZX5Q2ZoH1mQPP
      UgCMxoMLaV1jndJe5N5oUfIOz+1xJID9GbYxebDzAYCoHufCKnesqRUFVAuFOb42rw+0HrUBT1bs
      HeBmRbnQMs8vrTFOfpEGM71RFVjV+4XymgD0LUG9k3IaWDQUkxZXdEYQySNoK2FiVzxDfmMwHsm9
      J2OwYLjkYVe04CyoCMFhhnHcSB11pH7sBustR8otV9w182CXjMZDAwaPSsll5bfVaDZLrhjPUkxz
      yQ7g+OFeoBsuPYV50GetvBYKQLIHTPsyNpEMF+iGJ6Vh5MiJj5dWiogr9XexJuS3jAbcBpzWjK4w
      cvNKnhOqG1d6MFiboLujimlwYvRuDxibWa29pnKgmjEY60qOvg5R+8STE3dvVCR9IeDEyoftmwn6
      6LtUW++AMJCWHqSzX5cotTCnK2Y9xLCGqVvdrxQ6dgtGWm7uXwJ2FS29bCjT9L7HWS9iuo11WHMt
      q5rY9W7VV7xh2grWdSe8y3g22Nnnlu+8+FnXk+65Pbfn9mO2PwIMAGWFUJSnHmbBAAAAAElFTkSu
      QmCC" transform="matrix(1 0 0 1 504.9602 503.715)">
      </image>
      <g>
      <ellipse transform="matrix(0.866 -0.5 0.5 0.866 -193.1579 334.7924)" class="st1" cx="528.2" cy="527.8" rx="9.2" ry="14.3"/>
      </g>
      </g>
      <radialGradient id="SVGID_1_" cx="521.2762" cy="520.6415" r="19.2609" fx="520.3353" fy="519.8838" gradientUnits="userSpaceOnUse">
      <stop  offset="9.525092e-03" style="stop-color:#838383"/>
      <stop  offset="0.1184" style="stop-color:#707070"/>
      <stop  offset="0.2983" style="stop-color:#585858"/>
      <stop  offset="0.488" style="stop-color:#474747"/>
      <stop  offset="0.6919" style="stop-color:#3C3C3C"/>
      <stop  offset="0.9355" style="stop-color:#393939"/>
      </radialGradient>
      <circle class="st2" cx="527.4" cy="526.1" r="16.6"/>
      <g>
      <linearGradient id="SVGID_2_" gradientUnits="userSpaceOnUse" x1="242.0638" y1="122.4532" x2="819.2889" y2="939.1385">
      <stop  offset="9.525092e-03" style="stop-color:#2B2B2B"/>
      <stop  offset="8.178049e-02" style="stop-color:#212121"/>
      <stop  offset="0.217" style="stop-color:#151515"/>
      <stop  offset="0.4072" style="stop-color:#0F0F0F"/>
      <stop  offset="0.9355" style="stop-color:#0D0D0D"/>
      </linearGradient>
      <path class="st3" d="M527.4,26.1c-276.1,0-500,223.9-500,500s223.9,500,500,500s500-223.9,500-500S803.5,26.1,527.4,26.1z
      M527.4,804.1c-153.5,0-278-124.5-278-278s124.5-278,278-278s278,124.5,278,278S680.9,804.1,527.4,804.1z"/>
      <path class="st4" d="M527.4,248.1c-153.5,0-278,124.5-278,278s124.5,278,278,278s278-124.5,278-278S680.9,248.1,527.4,248.1z
      M527.4,744.5c-120.6,0-218.4-97.8-218.4-218.4s97.8-218.4,218.4-218.4s218.4,97.8,218.4,218.4S648,744.5,527.4,744.5z"/>
      </g>
      <path class="st5" d="M660.6,98.3c-42.1-13.1-86.8-20.1-133.2-20.1c-232,0-422.7,176.3-445.7,402.2"/>
      <path class="st6" d="M660.6,98.3c-42.1-13.1-86.8-20.1-133.2-20.1c-232,0-422.7,176.3-445.7,402.2"/>
      <path class="st5" d="M212.2,297.3c-46.7,64.2-74.3,143.3-74.3,228.8c0,187.6,132.6,344.2,309.2,381.2"/>
      <path class="st5" d="M592.9,844.6C741,814.3,852.4,683.2,852.4,526.1c0-67.3-20.5-129.9-55.5-181.7"/>
      <path class="st5" d="M353,938.9c53.6,22.7,112.5,35.2,174.4,35.2c247.4,0,448-200.6,448-448c0-136.5-61-258.7-157.3-340.9"/>
      <path class="st5" d="M843.2,754c46.3-64.1,73.6-142.8,73.6-227.9c0-183-126.2-336.6-296.4-378.3"/>
      <path class="st5" d="M483.1,204.1c-158.6,21.6-280.8,157.6-280.8,322.1c0,27,3.3,53.3,9.5,78.4"/>
      </svg>
    </div>


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
  // let _token = 'BQC0LWRqZ6n_T53J2HJq-0mWHmVjGEBwpjsqeitg8U9kXyztIdpVoUX5SuGGQbHK1kme8FP2qExU7HC2VEKtgGlG44YQspxsC63kkNeI3_iT5FbI_LWUXNJ7-W_nETov6qAt3TvV2crMus0RNTDbqJZ5EKnfzLNDVw';
  console.log(_token);

  const authEndpoint = "https://accounts.spotify.com/authorize";

  // Replace with your app's client ID, redirect URI and desired scopes
  const clientId = "36600d1fedd5473aa0ce196ab8ba07c0";
  // const redirectUri = "http://127.0.0.1:8080/";
  const redirectUri = "http://tangy-station.surge.sh";
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
          // Play a random song if paused
          if(state.paused) {
            let randomSong = this.pickRandomProperty(this.rfidArray).song;
            this.play(randomSong);
          }
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
      },
      pickRandomProperty: function(obj) {
        var keys = Object.keys(obj)
        return obj[keys[ keys.length * Math.random() << 0]];
      }
    }
  };
</script>

<style lang="scss">
	.st0{opacity:0.49;}
	.st1{fill:#231F20;}
	.st2{fill:url(#SVGID_1_);}
	.st3{fill:url(#SVGID_2_);}
	.st4{fill:#2D2D2D;}
	.st5{fill:none;stroke:#58595B;stroke-width:3;stroke-miterlimit:10;}
	.st6{fill:none;stroke:#5C5D5E;stroke-width:3;stroke-miterlimit:10;}

  .container {
    margin-top: 40px;
    text-align: center;
  }

  h1 {
    font-size: 2em;
    line-height: 1.3em;
  }

  .record-wrapper {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    position: relative;
    margin-top: 40px;
    animation: rotation 12s infinite linear;
    &__image {
      position: absolute;
      width: 230px;
    }
    &__svg {
      position: relative;
      width: 550px;
      z-index: 10000;
    }
  }


@keyframes rotation {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(360deg);
  }
}
</style>
