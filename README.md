# podcast.junior.guru

Podcast for juniors in tech 🐣

## How does it work?

This repo serves as a hosting for the podcast audio files. There are episodes in the `episodes` directory. There are GitHub Pages which publish and serve the files. There's `index.html` which redirects nosy visitors. That's it!

The episodes are linked from the [junior.guru codebase](https://github.com/honzajavorek/junior.guru/), which also generates the podcast feed and provides the podcast website.

## FAQ

**Why not Anchor?** Anchor costs nothing, but it would own our Spotify listeners. According to our research, it would be very hard to change the hosting provider later in the future. Anchor feels like one of those services where you pay by freedom rather than money.

**Why not Buzzsprout?** We wanted to start small and with zero costs.

**Why not S3?** Our lives are too short to fiddle with cloud consoles and the IAM hell.

**You shouldn't put large files to Git!** True. But GitHub makes it too easy to resist! It's okay to store files up to 100 MB directly in the repo. If the podcast grows, the escape plan is to repurpose GitHub Releases, where we can upload large binaries without any limits. The downside is that each time we would have to create a git tag first, so for the start, we decided to use GitHub Pages.

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
