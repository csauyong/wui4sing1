TRACKS DIRECTORY - assets for the record-player music player

The page loads the web derivatives, not the masters. Masters stay in the repo
for archival but are excluded from the Cloudflare deploy by /.assetsignore.

  played by the site          master
  --------------------------  ------------------------------------
  track-01-highlight.m4a      002 等後_2.wav
  track-02-highlight.m4a      003 復甦_2.wav
  track-03-highlight.m4a      004 詩想 (Day version)_2.wav
  track-04-highlight.m4a      以馬忤斯 live demo ver2_2.wav

  track-01-cover-web.jpg      track-01-cover.jpg
  track-02-cover-web.jpg      track-02-cover.jpg
  track-03-cover-web.jpg      track-03-cover.png
  track-04-cover-web.jpg      track-04-cover.jpg

Current running order (see TRACKS in index.html):

  1. 等後      Lamentations 3:25-26 · 耶利米哀歌
  2. 復甦      Ezekiel 37:7-10 · 以西結書
  3. 詩想      Psalm 119:54 · 詩篇
  4. 以馬忤斯  Luke 24:13-16 · 路加福音

Regenerating a derivative:

  cover  sips -Z 800 -s format jpeg -s formatOptions 78 MASTER --out track-0N-cover-web.jpg
  audio  afconvert -f m4af -d aac -b 128000 MASTER track-0N-highlight.m4a

Covers render into a ~210px circle, so 800px square is already retina-generous.
Audio clips are 30-60 sec highlights.

If an audio file is missing the play button becomes inert but the rest of the
player still works. If a cover is missing, a Chinese-character letterform
placeholder is shown in its place.
