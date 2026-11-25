# TrackTrace Mobile PWA

Mac-free iPhone prototype for importing recordings and demonstrating the TrackTrace investigation workflow.

## Deploy
1. Open Settings → Pages.
2. Choose Deploy from a branch, `main`, `/ (root)`.
3. Open the published HTTPS URL in Safari.
4. Share → Add to Home Screen.

## Offline playlist library (v0.2.0)
- Import a YouTube playlist's metadata while online using a restricted YouTube Data API v3 key.
- Save the imported playlist list in local browser storage for offline reference.
- Add audio files from Files using the multi-file picker. TrackTrace stores the audio blobs in IndexedDB on the device and provides local playback without Wi-Fi or mobile data.
- Playlist metadata and audio files are stored separately. YouTube playlist videos are not downloaded or extracted.
- Browser storage can be cleared by iOS or the user; keep a separate copy of source audio files. Large imports may exceed available storage.
- For best offline behavior, install the PWA to the Home Screen and open it while online before leaving coverage.

## Current limits
This prototype imports recordings saved through iOS Screen Recording or Files. It does not capture another iOS app's live audio. Demo investigation results are sample data, not real recognition. Live AudD and YouTube API integration requires a secure server-side proxy; never put private API keys in client-side code.

## YouTube playlist import
Paste a YouTube playlist URL into the Playlist Intake panel. The playlist can be opened in YouTube or embedded in TrackTrace without an API key. To import a browsable video list, create a YouTube Data API v3 key in Google Cloud, enable the YouTube Data API v3, and restrict the key by HTTP referrer to your GitHub Pages origin. The key is held in session memory only and is not sent to TrackTrace servers. Public/access-permitted playlist items are loaded 50 at a time.

This does not download or extract playlist audio. Use audio files you have rights to use for the offline library.