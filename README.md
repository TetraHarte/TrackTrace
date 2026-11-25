# TrackTrace Mobile PWA

Mac-free iPhone prototype for importing recordings and demonstrating the TrackTrace investigation workflow.

## Deploy
1. Open Settings → Pages.
2. Choose Deploy from a branch, `main`, `/ (root)`.
3. Open the published HTTPS URL in Safari.
4. Share → Add to Home Screen.

## Current limits
This prototype imports recordings saved through iOS Screen Recording or Files. It does not capture another iOS app's live audio. Demo investigation results are sample data, not real recognition. Live AudD and YouTube API integration requires a secure server-side proxy; never put private API keys in client-side code.
 
## YouTube playlist import
Paste a YouTube playlist URL into the Playlist Intake panel. The playlist can be opened in YouTube or embedded in TrackTrace without an API key. To import a browsable video list, create a YouTube Data API v3 key in Google Cloud, enable the YouTube Data API v3, and restrict the key by HTTP referrer to your GitHub Pages origin. The key is held in session memory only and is not sent to TrackTrace servers. Public/access-permitted playlist items are loaded 50 at a time.

This does not download or extract playlist audio. Use the embedded YouTube player or open videos in YouTube; import recordings separately for audio investigation.
