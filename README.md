# hello-ivs

This is a project created to test the integration of [Amazon IVS Player](https://docs.aws.amazon.com/ivs/latest/userguide/player.html) with the [Video.js](https://videojs.com/). Currently just loads a stream channel into the player, the _Playback URL_ must be placed in the `.env` file.

## Project setup

Install all dependencies

```
npm install
```

Create a `.env` file and set the value for the variable `VUE_APP_CHAN_ENDPOINT`

```
VUE_APP_CHAN_ENDPOINT='https://fcc3ddae59ed.us-west-2.playback.live-video.net/api/video/v1/us-west-2.893648527354.channel.DmumNckWFTqz.m3u8'
```

### Compiles and hot-reloads for development

```
npm run serve
```

### Customize configuration

See [Configuration Reference](https://cli.vuejs.org/config/).

## Test Streams

You can use these test streams provided by Amazon IVS

- 1080p30 - https://fcc3ddae59ed.us-west-2.playback.live-video.net/api/video/v1/us-west-2.893648527354.channel.DmumNckWFTqz.m3u8
- Square Video - https://fcc3ddae59ed.us-west-2.playback.live-video.net/api/video/v1/us-west-2.893648527354.channel.XFAcAcypUxQm.m3u8
- Vertical Video - https://fcc3ddae59ed.us-west-2.playback.live-video.net/api/video/v1/us-west-2.893648527354.channel.YtnrVcQbttF0.m3u8
- Quiz - https://fcc3ddae59ed.us-west-2.playback.live-video.net/api/video/v1/us-west-2.893648527354.channel.xhP3ExfcX8ON.m3u8
- VOD - https://d6hwdeiig07o4.cloudfront.net/ivs/956482054022/cTo5UpKS07do/2020-07-13T22-54-42.188Z/OgRXMLtq8M11/media/hls/master.m3u8

## Code Samples

You may find more code samples of Amazon IVS in the[ official repository](https://github.com/aws-samples/amazon-ivs-player-web-sample).
