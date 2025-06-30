### Assets TW Emojis
For using on custom websites, mail signatures, or whatever.
- [svgs](https://mapaor.github.io/tw-emojis/tw-emojis-svgs)
- [pngs](https://mapaor.github.io/tw-emojis/tw-emojis-pngs)
TODO: I used Inkscape CLI to render the pngs from the svgs. But they rendered at 36x36. Now I've got to do it again to 128x128, which is better for emojis.
### TIPS
Use [ffmpeg](https://ffmpeg.org/download.html) to trim to 60s:
```
ffmpeg -y -ss 30 -i "BigBuckBunny.mp4" -t 60 -c copy "60s/BigBuckBunny.mp4"
```
Or to convert quality to 720p if needed:
```
ffmpeg -i "BigBuckBunny.mp4" -vf "scale=-1:720" -c:v libx264 -crf 23 -preset fast -c:a copy "720p/BigBuckBunny.mp4"
```
Note: 23 is the ICQ (quality of compression). 18-28 is a normal range, being 18 a great quality preset and 28 a poor quality one.
### Sample Videos
Maybe you're also interested in sample videos as URL mp4 files: [https://github.com/Mapaor/sample-videos](https://github.com/Mapaor/sample-videos)
