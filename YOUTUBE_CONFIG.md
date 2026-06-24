# PCCE YouTube Configuration

## Channel
https://www.youtube.com/@ScienceMadeVisual

## Pharmacy Leadership Series Playlist
https://youtube.com/playlist?list=PLNrMcS-BlJSD9ln4zuPqepJMa-X3svrkp

## How to add a new video
When Danny says "new video" or "add latest video":
1. Fetch the playlist URL above using yt-dlp or web fetch to get latest video IDs and titles
2. Compare against the current `shorts` array in the `EDU_SERIES` JavaScript block in `index.html` (around line 1346)
3. Add any new `{ id: 'VIDEO_ID', title: 'Video Title' }` entries to the array
4. Commit and push via osascript (auto-push rule applies)

## Videos currently on site
- UFZdjqLfsf4 — "Pharmacy Leadership – A new series!"
- _Fe_4-XbOUo — "Clinical leadership: using the expertise around you"


## Medication Education series (added 2026-06-24)
- _06TcN-B6sw — How Calcium Channel Blockers Work
- EvnCz4aHabw — How Statins Actually Work 💊
