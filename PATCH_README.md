# video_player_web_hls (vendored patch)

Temporary local fork of [ovenbits/video_player_web_hls](https://github.com/ovenbits/video_player_web_hls) (`fix/chromium-browsers-hls-crash`) with a defensive guard around `Hls.isSupported` when the hls.js global is missing.

## Changes vs upstream

- `lib/hls.dart`: `isHlsJsAvailable()` and `isHlsPlaybackSupported()` helpers
- `lib/src/video_player.dart`: `shouldUseHlsLibrary()` uses `isHlsPlaybackSupported()` instead of bare `isSupported()`

## Upstream follow-up

Open a PR against `ovenbits/video_player_web_hls` with these changes. After merge, replace the `path` dependency in `apps/messengerx/pubspec.yaml` with the new git `ref` and remove this directory.
