## Download Youtube as mp3 

`youtube-dl -f bestaudio --extract-audio --audio-format mp3 --audio-quality 0 YOUTUBE_URL`

## Download Playlist

`yt-dlp --no-part -x --yes-playlist --audio-format mp3 -o "%(title)s.%(ext)s"`
