# HLS URL Player Test Page

Test page for validating HLS playback via AVPlayer on tvOS.

## Files

- `hls-urlplayer-test.html` - Main test page (clear and encrypted HLS modes)
- `hls-test-common.js` - Playback controls, event monitoring, manifest parsing
- `hls-test-fairplay.js` - FairPlay DRM config and EME session management
- `hls-test-common.css` - Styles
- `m3u8-parser.min.js` - HLS manifest parser (local copy to avoid CORS)

## Running locally

Start a server from this directory:

    python3 -m http.server 8080 --bind 0.0.0.0

Find your IP:

    ipconfig getifaddr en0

Open in browser to verify:

    http://<your-ip>:8080/hls-urlplayer-test.html?mode=clear

## Deploying to tvOS device

Pass the test page URL and allow insecure origin:

    --url=http://<your-ip>:8080/hls-urlplayer-test.html?mode=clear
    --unsafely-treat-insecure-origin-as-secure=http://<your-ip>:8080

## URL parameters

- `?mode=clear` - Clear HLS (default)
- `?mode=encrypted` - FairPlay encrypted HLS
