# Changelog

All notable changes to **View Assist – Play Music with Music Assistant (Expanded)** are documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/), and this project follows [Semantic Versioning](https://semver.org/spec/v2.0.0.html). Versions in the `0.x` range indicate beta status — commands and behavior may change before `1.0.0`.

This is an expanded fork of dinki's *Play Music with Music Assistant* blueprint (v1.2.7). Version numbers here are independent of the original project's numbering.

---

## [0.1.0] – 2026-06-14

First tracked release of the Expanded edition. Everything in **Added** is new relative to the original v1.2.7, which provided only: play artist, play playlist, play song, and queue song.

### Added

**More ways to play music**
- Play an album, optionally by a named artist.
- Play a radio station by name.
- Radio mode — an endless mix seeded from an artist.
- Play a random mix from the library, with a configurable track count (*Random Track Count*).
- Add a song to the end of the queue (distinct from "queue," which inserts it next).

**Playback controls**
- Shuffle on / off.
- Repeat off / one / all.
- Stop.
- Clear the queue.
- Change the player's source.

**Queue awareness**
- "What's playing" — reports the current song, artist, and album.
- "What's next" — reports the next track in the queue.

**Moving music between rooms**
- Transfer the queue to a named room ("move the music to the bedroom").
- Transfer the queue to the current room ("move the music here").
- Group speakers: join a named room, "play here too," and unjoin.

**Other commands**
- Favorite the current song (the favorite button is resolved dynamically).
- Spoken announcements ("announce …"), voiced through the satellite's own Assist pipeline.
- Named sound-clip announcements via URL ("play the doorbell announcement").

**New configuration inputs**
- *Join Alias Map* — map spoken room names to Music Assistant players (also used by transfer).
- *Announcement Sound Map* — map spoken names to announcement sound URLs.
- *Random Track Count* — how many tracks "play random music" queues.

### Changed
- The playlist command now accepts "play the … playlist" in addition to "start the … playlist."

### Notes
- Eight languages are supported (ca, de, en, es, nl, pl, pt, ro). English strings are exact; the others are best-effort and would benefit from native-speaker review.
- "What's next" reports only the next track. Music Assistant's `get_queue` is intentionally limited to the current and next item, so full-queue listing is not available through it.
- This release validates structurally; the underlying Music Assistant actions still warrant a live test in your environment (see the README).

[0.1.0]: https://github.com/changeling/View-Assist-Play-Music-Expanded/releases/tag/v0.1.0
