# podcast.junior.guru

Podcast for juniors in tech 🐣

## How does it work?

This repo serves as a hosting for the podcast audio files. There are episodes in the `episodes` directory. There are GitHub Pages which publish and serve the files. There's `index.html` which redirects nosy visitors. That's it!

### Humans

1. Pavlína comes up with a topic, Honza helps her to find and contact guests.
2. Pavlína takes care of production, including communication with guests, recording, post-processing.
3. Pavlína drops mp3 file to the `episodes` directory. The name of the file is a unique ID of the episode, which must not ever change.
4. Pavlína and Honza collaborate on the [podcast.yml](https://github.com/honzajavorek/junior.guru/blob/main/juniorguru/data/podcast.yml) file in the junior.guru repo to add episode metadata.

### Robots

5. Every day, the [podcast.py](https://github.com/honzajavorek/junior.guru/blob/main/juniorguru/sync/podcast.py) script in the junior.guru repo takes the available data and creates corresponding database entries.
6. The [api.py](https://github.com/honzajavorek/junior.guru/blob/main/juniorguru/mkdocs/api.py) generates the [podcast.xml](https://junior.guru/api/podcast.xml) feed. It includes only episodes with publish dates in the past.
7. The same data is used for generating the [podcast homepage](https://junior.guru/podcast/).
8. (_not implemented yet_) The same data serves to the Discord bot for announcing new podcast episodes in the club.
9. Podcast platforms, such as Spotify or Apple, regularly check the podcast.xml feed and process updates.

### Humans (again)

10. Honza announces new podcast episodes on social media as part of his regular posting routine.


## FAQ

**Why not Anchor?** Anchor costs nothing, but it would own our Spotify listeners. According to our research, it would be very hard to change the hosting provider later in the future. Anchor feels like one of those services where you pay by freedom rather than money.

**Why not Buzzsprout?** We wanted to start small and with zero costs until we have at least rough idea if we manage to keep publishing and how much listeners we are able to attract.

**Why not S3?** Our lives are too short to fiddle with cloud consoles and the IAM hell.

**You shouldn't put large files to Git!** True. But GitHub makes it too easy to resist! It's okay to store files up to 100 MB each directly in the repo. If the podcast grows, the plan is to repurpose GitHub Releases, where we can upload large binaries without any limits. The downside is that each time we would have to create a git tag first, so for simplicity, we decided to use GitHub Pages in the beginning.

## License

Copyright (c) 2022 Pavlína Froňková, Jan Javorek
