<template>
  <v-container>
    <v-row class="text-center">
      <v-col cols="10">
        <v-card class="mx-auto">
          <v-card-title>Player</v-card-title>
          <v-card-text class="d-flex justify-center">
            <video ref="videoPlayer" class="video-js"></video>
          </v-card-text>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
  import videojs from 'video.js';
  import { registerIVSTech } from 'amazon-ivs-player';
  import 'video.js/dist/video-js.css';

  export default {
    name: 'HelloWorld',

    data: () => ({
      player: null,
      videoSource: process.env.VUE_APP_CHAN_ENDPOINT,
      videoOptions: {
        autoplay: true,
        controls: true,
        techOrder: ["AmazonIVS"],
        width: "800"
      }
    }),

    mounted() {
      // register the tech with videojs
      console.log(`wasmWorker: ${this.createAbsolutePath('/assets/amazon-ivs-wasmworker.min.js')}`);

      registerIVSTech(videojs,  {
        wasmWorker: this.createAbsolutePath('/assets/amazon-ivs-wasmworker.min.js'),
        wasmBinary: this.createAbsolutePath('/assets/amazon-ivs-wasmworker.min.wasm'),
      });

      // Init the player
      this.player = videojs(this.$refs.videoPlayer, this.videoOptions, () => {
        console.log('Player is ready to use!');
        // play the stream
        this.player.src(this.videoSource);
      })
    },

    beforeDestroy() {
      // Destroy the player instance
      if(this.player) {
        this.player.dispose();
      }
    },

    methods: {
      createAbsolutePath(assetPath) {
        return new URL(assetPath, document.URL).toString();
      }
    }
  }
</script>

<style scoped>
</style>
