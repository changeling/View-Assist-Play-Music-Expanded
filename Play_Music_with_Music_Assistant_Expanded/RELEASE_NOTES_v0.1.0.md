First beta of the **Expanded edition** — voice control for Music Assistant from a View Assist satellite. This expands dinki's original [*Play Music with Music Assistant*](https://github.com/dinki/View-Assist/tree/main/View_Assist_custom_sentences/Play_Music_with_Music_Assistant) blueprint (v1.2.7), which provided play artist, play playlist, play song, and queue song. Everything below is new on top of that.

### Added

**More ways to play music**
- Play an album, optionally by a named artist.
- Play a radio station by name.
- Radio mode — an endless mix seeded from an artist.
- Play a random mix from the library, with a configurable track count.
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
- Favorite the current song.
- Spoken announcements ("announce …"), voiced through the satellite's own Assist pipeline.
- Named sound-clip announcements via URL ("play the doorbell announcement").

**New configuration inputs**
- Join Alias Map — map spoken room names to Music Assistant players.
- Announcement Sound Map — map spoken names to announcement sound URLs.
- Random Track Count — how many tracks "play random music" queues.

### Changed
- The playlist command now accepts "play the … playlist" as well as "start the … playlist."

### Notes
- Eight languages supported (ca, de, en, es, nl, pl, pt, ro). English is exact; the others are best-effort and would benefit from native-speaker review.
- "What's next" reports only the next track — Music Assistant's queue lookup is limited to the current and next item.

---

⚠️ **This is an early beta (0.x).** Commands and behavior may change before 1.0.0. Installation instructions are in the [README](https://github.com/changeling/View-Assist-Play-Music-Expanded/blob/main/Play_Music_with_Music_Assistant_Expanded/README.md) — please try it out and report any issues.
