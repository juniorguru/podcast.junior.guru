# podcast.junior.guru

Podcast for juniors in tech 🐣

## Status: archived

The podcast ran from January 2022 to February 2024 (episodes 0–20). No new episodes are planned, so this repository is archived and read-only.

The audio files stay online, as the podcast is still listed on Apple Podcasts, Spotify and other platforms, and they keep downloading the episodes from here.

- **Don't delete or rename anything.** Each file name in `episodes` is the episode's permanent ID and part of its public URL.
- **Don't delete this repository or remove the `podcast.junior.guru` DNS record.** Every episode on every platform would stop playing.

## How does it work?

This repo serves as a hosting for the podcast audio files. There are episodes in the `episodes` directory. GitHub Pages publish and serve the files at `https://podcast.junior.guru/episodes/<number>.mp3`. There's `index.html` which redirects nosy visitors. That's it!

Everything else lives in the [junior.guru](https://github.com/juniorguru/junior.guru) repository:

- [`podcast.yml`](https://github.com/juniorguru/junior.guru/blob/main/src/jg/coop/data/podcast.yml) holds the episode metadata, including each file's size and duration, so nothing ever needs to download the audio files.
- [`podcast.py`](https://github.com/juniorguru/junior.guru/blob/main/src/jg/coop/sync/podcast.py) loads the metadata into the database.
- [`api.py`](https://github.com/juniorguru/junior.guru/blob/main/src/jg/coop/web/api.py) generates the [podcast.xml](https://junior.guru/api/podcast.xml) feed, which the podcast platforms read.
- The same data is used for the [podcast homepage](https://junior.guru/podcast/).

Until [juniorguru/junior.guru#2004](https://github.com/juniorguru/junior.guru/pull/2004), the sync also checked the audio files, rendered posters and announced new episodes on Discord. The podcast was produced by Pavlína Froňková, with Honza Javorek's help.

## FAQ

**Why not Anchor?** Anchor costs nothing, but it would own our Spotify listeners. According to our research, it would be very hard to change the hosting provider later in the future. Anchor feels like one of those services where you pay by freedom rather than money.

**Why not Buzzsprout?** We wanted to start small and with zero costs until we have at least rough idea if we manage to keep publishing and how much listeners we are able to attract.

**Why not S3?** Our lives are too short to fiddle with cloud consoles and the IAM hell.

**You shouldn't put large files to Git!** True. But GitHub makes it too easy to resist! It's okay to store files up to 100 MB each directly in the repo. If the podcast grows, the plan is to repurpose GitHub Releases, where we can upload large binaries without any limits. The downside is that each time we would have to create a git tag first, so for simplicity, we decided to use GitHub Pages in the beginning.

## License

Copyright (c) 2022 Pavlína Froňková, Jan Javorek
