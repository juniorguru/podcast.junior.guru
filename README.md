# podcast.junior.guru

Podcast for juniors in tech 🐣 This repository works as backend for the podcast.

## FFmpeg Cheatsheet

Stereo

```
ffmpeg -i episode.wav -vn -c:a libmp3lame -ar 44100 -ac 2 -qscale:a 5 -f mp3 episode_stereo.mp3
```

Mono

```
ffmpeg -i episode.wav -vn -c:a libmp3lame -ar 44100 -ac 1 -qscale:a 5 -f mp3 episode_mono.mp3
```

## License

Copyright (c) 2021 Jan Javorek and Pavlína Froňková
