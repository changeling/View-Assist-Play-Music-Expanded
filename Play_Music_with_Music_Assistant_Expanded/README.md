# View Assist – Play Music with Music Assistant (Expanded)

A voice-control blueprint for [View Assist](https://github.com/dinki/View-Assist) that lets you run your whole [Music Assistant](https://github.com/music-assistant) setup by talking to it. It builds on dinki's original *Play Music with Music Assistant* blueprint (v1.2.7) and adds a large set of new commands — playback control, queue management, moving music between rooms, announcements, and more.

You talk to a View Assist satellite; the blueprint figures out which player that satellite controls and acts on it. Spoken replies come back through the satellite's own voice, and the music screen updates automatically.

> **Beta:** This expanded blueprint is currently hosted in a fork while it's being tested, with the goal of contributing it back to the official View Assist project. Feedback from beta testers is welcome.

---

## Installation

### Before you start

You'll need:
- **View Assist** installed, with at least one satellite set up.
- The **Music Assistant** integration configured, with at least one player.

### Option 1 — One-click import (easiest)

Click the button below. It opens the blueprint import dialog in your own Home Assistant, with the address already filled in — just confirm.

[![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fgithub.com%2Fchangeling%2FView-Assist-Play-Music-Expanded%2Fblob%2Fmain%2FPlay_Music_with_Music_Assistant_Expanded%2Fblueprint-playmusicwithmusicassistantexpanded.yaml)

If the badge doesn't render, use this link: [My Home Assistant import link](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fgithub.com%2Fchangeling%2FView-Assist-Play-Music-Expanded%2Fblob%2Fmain%2FPlay_Music_with_Music_Assistant_Expanded%2Fblueprint-playmusicwithmusicassistantexpanded.yaml)

### Option 2 — Manual import

1. In Home Assistant, go to **Settings → Automations & Scenes → Blueprints**.
2. Click **Import Blueprint** (bottom right).
3. Paste this address and import:

   ```
   https://github.com/changeling/View-Assist-Play-Music-Expanded/blob/main/Play_Music_with_Music_Assistant_Expanded/blueprint-playmusicwithmusicassistantexpanded.yaml
   ```

You can also view or download the blueprint file directly here: [blueprint-playmusicwithmusicassistantexpanded.yaml](https://github.com/changeling/View-Assist-Play-Music-Expanded/blob/main/Play_Music_with_Music_Assistant_Expanded/blueprint-playmusicwithmusicassistantexpanded.yaml).

### After importing

1. Go to **Settings → Automations & Scenes → Automations → Create Automation → Use Blueprint**, and pick **View Assist - Play Music with Music Assistant Expanded**.
2. Fill in the options (see [Configuration](#configuration-for-everyone) below). At minimum, choose your Music Assistant instance.
3. Save the automation.
4. Test a few phrases in **Developer Tools → Assist** before using them by voice.

---

## What you can do

Everything below is a thing you can say out loud. The exact wording is flexible and can be changed (see [Configuration](#configuration-for-everyone)), but these are the defaults.

### Play music
- **An artist** — "play some Pink Floyd," "play music by Adele"
- **An album** — "play the album Rumours," "play the album Abbey Road by the Beatles"
- **A song** — "play Bohemian Rhapsody by Queen"
- **A playlist** — "start the Friday playlist," "play the Friday playlist"
- **A radio station** — "play the radio station Jazz FM," "play Jazz FM radio"
- **Radio mode** (an endless mix based on an artist) — "play radio based on Fleetwood Mac"
- **A random mix** — "play some random music," "play random tracks"

### Control what's playing
- **Shuffle** — "shuffle on," "turn off shuffle"
- **Repeat** — "repeat this song," "repeat all," "repeat off"
- **Stop** — "stop the music"
- **Clear the queue** — "clear the queue"
- **Change the source** — "change the source to Spotify"

### Manage the queue
- **Play a song next** — "queue Yesterday by the Beatles"
- **Add a song to the end** — "add Yesterday by the Beatles to the queue"
- **Hear what's playing** — "what's playing" (tells you the song, artist, and album)
- **Hear what's up next** — "what's next," "what's in the queue" (tells you the next track)

### Move music around the house
- **Send it to another room** — "move the music to the bedroom"
- **Bring it to where you are** — "move the music here"
- **Group speakers together** — "join the living room"
- **Add the current room to the group** — "play here too"
- **Leave a group** — "unjoin"

### Other
- **Favorite the current song** — "favorite this song"
- **Make a spoken announcement** — "announce dinner is ready" (the assistant says it out loud)
- **Play an announcement sound** — "play the doorbell announcement" (plays a sound clip you've set up)

---

## What's new compared to the original blueprint

The original blueprint could do four things: play an artist, play a playlist, play a song, and queue a song. Everything else in the list above is new. Grouped up, the additions are:

**More ways to play music**
- Albums
- Radio stations
- Radio mode (artist-seeded endless mix)
- A random mix from your library
- An extra queue option: add a song to the end of the queue (the original only had "play now" and "play next")

**Playback controls** (previously you had none of these by voice through this blueprint)
- Shuffle on/off
- Repeat off / one / all
- Stop
- Clear the queue
- Change the player's source

**Queue awareness**
- "What's playing" — now reports song, artist, and album
- "What's next" — tells you the next track in the queue

**Moving music between rooms**
- Send the music to a named room
- Bring the music to the room you're in
- Group and ungroup speakers ("join" / "play here too" / "unjoin")

**Announcements**
- Speak any text out loud
- Play a pre-set sound clip (doorbell, chime, etc.)

**Favorites**
- Favorite the song that's currently playing

**Smaller refinements**
- The playlist command now accepts "play the … playlist" as well as "start the … playlist"
- "What's playing" now includes the album name when one is available

---

## Configuration (for everyone)

When you add the blueprint and create an automation from it, you'll see a list of options. You can ignore most of them and accept the defaults. These are the ones worth knowing about.

**Music Assistant Instance** — pick your Music Assistant server from the list. Required.

**Dashboard Info view** — the View Assist screen used to show music (e.g. `/view-assist/music`). Leave the default unless you've named yours differently.

**Language** — the language for spoken replies. Choose from the supported list.

**The command phrasings** — there is one option per command (e.g. *Play Album Command*, *Stop Command*). Each holds the words you can say to trigger that command. You can leave them alone, or edit them to match how you naturally speak. For example, if you'd rather say "kill the music" than "stop the music," you can add that. You don't need to understand the symbols to add a simple alternative — just keep the `{...}` parts (those are the slots where you say an artist, song, room, etc.).

**Join Alias Map** — *(optional)* a list that tells the blueprint which speaker each room name refers to, so "join the living room" or "move the music to the office" work reliably. Click **Add** to create a row, then fill in two boxes:

- **Spoken phrase** — what you say (e.g. `living room`)
- **Player entity_id** — the Music Assistant player it maps to (e.g. `media_player.ma_living_room`)

Add as many rows as you like, and you can point several spoken phrases at the same speaker (handy because speech recognition isn't always exact). Leave the list empty and the blueprint will try to match by the speaker's own name instead — it just works better when you fill this in.

**Announcement Sound Map** — *(optional)* the same idea, but for sound clips. Click **Add** for each entry and fill in:

- **Spoken name** — what you say (e.g. `doorbell`)
- **Sound URL** — the web address of the audio file (e.g. `http://192.168.1.50:8123/local/doorbell.mp3`)

With those set, "play the doorbell announcement" plays that clip. Leave it empty if you only want spoken announcements.

**Radio Station Aliases** — *(optional)* for radio stations that don't come up reliably when you just say their name. Click **Add** for each station and fill in:

- **Spoken phrase** — what you say (e.g. `the beeb`)
- **Media id** — the exact Music Assistant radio station to play (e.g. `BBC Radio 1`)
- **Station name** — *(optional)* a friendly name for the spoken reply; if left blank, the spoken phrase is used

Aliased stations take priority; anything not listed falls back to a normal search, so you only need entries for the stations search struggles with.

**Random Track Count** — how many songs "play some random music" should queue up. Default is 25.

### A note on announcements and ducking

When you say "announce …," the assistant speaks the text through your satellite's normal voice. If your satellite's announcement player and music player are the same speaker, Music Assistant automatically handles the music while the announcement plays — and whether the music *dips underneath* the announcement or *pauses and resumes* depends on your speaker type (Sonos S2, Snapcast, and Sendspin players dip the volume; most others pause and resume). Either way you don't have to set anything up for it; it's handled for you.

### Trying it out

After setting things up, the safest way to test is to type the phrases into **Developer Tools → Assist** in Home Assistant and watch what happens, before relying on them by voice. This also catches any cases where a new phrase overlaps with another command you already use.

---

## Configuration (for developers and tinkerers)

This section is for anyone who wants to read, modify, or extend the blueprint.

### How the file is organized

The blueprint is one YAML file. Every addition made on top of the original v1.2.7 is wrapped in marker comments so you can see exactly what changed:

```
# >>>>> NEW CODE BEGIN (...) >>>>>
...added code...
# <<<<< NEW CODE END (...) <<<<<
```

A one-line change to the original (the playlist verb) is marked with `# >>>>> MODIFIED ...` instead. The original author's own code uses no comments and annotates logic with `alias:` labels; the additions follow that same style.

### The anatomy of a command

Every command is built from four pieces that live in four places in the file. To add or change a command you touch all four:

1. **An input** under `blueprint: → input:` — defines the spoken phrasing (a [hassil sentence template](https://www.home-assistant.io/voice_control/aliases/), e.g. `(play | start) [the] {playlist} playlist`).
2. **A trigger** in the top-level `trigger:` list — a `conversation` trigger bound to that input, with a unique `id`.
3. **Response strings** in the `translations:` block — one entry per supported language, keyed by language code. *Every declared language must have every key, or the response lookup errors at runtime.*
4. **A branch** in the final `choose:` action — matched on the trigger `id`, this is where the work happens.

### How players and rooms are resolved

- The player a satellite controls comes from its `musicplayer_device` attribute: `state_attr(target_satellite_device, 'musicplayer_device')`. Most commands act on this.
- Commands that need "whatever is currently playing" (join, transfer, what's-next) find the first Music Assistant `media_player` in the `playing` state. This is simple and works for a single active queue; it's ambiguous if several players are playing independently.
- Named rooms ("join the living room," "move it to the office") are resolved by the **Join Alias Map** first (exact, case-insensitive name match), then fall back to matching the spoken text against player friendly names.
- The favorite button is resolved dynamically: it finds the `button.*` entity on the same device as the music player whose entity id contains `favorite`. Nothing needs to be hard-coded.

### How spoken replies and the screen work

- Spoken replies use `set_conversation_response`. The View Assist satellite's own Assist pipeline voices it — there is no separate TTS engine to configure, and you should **not** add one. ("Announce" is literally just `set_conversation_response` with the spoken text.)
- The screen is driven by `view_assist.set_state` (e.g. `mode: music`, `last_said`) and `view_assist.navigate`.
- Action commands gate their spoken confirmation on the satellite's `use_announce` attribute, matching the original. Query commands ("what's playing," "what's next") always speak, since silencing the answer to a question defeats it.

### Music Assistant actions used

- `music_assistant.search` → resolve artist/album/track/radio/playlist by name (original).
- `music_assistant.play_media` → play with `media_type`, `enqueue` (`play` / `replace` / `next` / `add` / `replace_next`), and `radio_mode`. `media_id` accepts a single name/URI **or a list of URIs** (used by the random-mix command).
- `music_assistant.get_library` → `order_by: random` with a `limit` builds the random mix; its `items[].uri` list is handed straight to `play_media`.
- `music_assistant.get_queue` → returns per-player queue metadata including `current_item` and `next_item`. Home Assistant limits this to the current and next item only; `items` is a **count** (int), not a list. Used to read the next track.
- `music_assistant.transfer_queue` → `target.entity_id` is the **destination**, `data.source_player` the origin, `auto_play: true` resumes playback.
- `music_assistant.play_announcement` → URL-based sound announcements only (the text path uses the pipeline, not this action).
- Standard `media_player.*` actions for the Tier 3 controls (`shuffle_set`, `repeat_set`, `clear_playlist`, `media_stop`, `select_source`, `join`, `unjoin`) and `button.press` for favoriting.

### Adding a new command — checklist

1. Add an input with a sensible default sentence; keep `{slot}` names consistent with how you'll read them (`trigger.slots.<name>`).
2. Add a `conversation` trigger with a new unique `id`.
3. Add response keys for **all eight** languages (ca, de, en, es, nl, pl, pt, ro).
4. Add a `choose` branch keyed on the trigger id, following the existing `if target_use_announce is not false / then / else` pattern for confirmations.
5. Validate the whole file as a single YAML document before importing.

### Things to verify in your own environment

- **Next-track field** — "what's next" reads `next_item.name`, falling back to `next_item.media_item.name`. If your Music Assistant version names these differently you'll hear "nothing is queued after this" rather than an error. Confirm by running `music_assistant.get_queue` in Developer Tools → Actions and inspecting the response.
- **`select_source`** — the spoken source must match a source the player actually exposes; this is the most fragile control and not every player exposes sources.
- **Grouping** — `media_player.join` only works among compatible player types and will error otherwise.
- **Sentence collisions** — several new commands share opening words ("play …") with existing ones; the trailing words disambiguate, but test in Developer Tools → Assist.

### Known design boundaries (deliberate, not bugs)

- **Announcements** ride the conversation reply (pipeline voice). A true *ducked spoken overlay on the music player* — as opposed to the satellite voicing the reply — would need either an explicit TTS engine via `tts.speak` to the music player, or resolving the satellite's `assist_satellite` entity for `assist_satellite.announce`. This was left out on purpose to avoid fighting the mechanism that already works.
- **"What's next"** reports only the **next track**. `get_queue` is intentionally limited to the current and next item (a Home Assistant policy), so listing the full upcoming queue isn't possible through it — that would require Music Assistant's REST API (`player_queues/all`) via a `rest_command`, which is out of scope for this blueprint.
- **Native intents** (next/previous, pause, resume, volume) are intentionally not included — Home Assistant handles those out of the box, and adding them would create conflicts.

### Translations

Eight languages are supported. The English strings are exact; the other seven were produced as best-effort and should be reviewed by native speakers before any upstream contribution. Any new response key must be added to all eight, or the language lookup will fail when that language is active.

### Releasing (maintainer checklist)

This project uses independent semantic versioning in the `0.x` beta range — patch (`x.y.Z`) for fixes, minor (`x.Y.0`) for new commands or behavior changes, `1.0.0` when stable. Breaking changes are acceptable during `0.x` but must be flagged. To cut a release:

1. Land all changes on `main` and confirm the blueprint validates as a single YAML document.
2. Bump the version in **two** places in the blueprint — the `# Version:` header comment and the `vX.Y.Z` in the `description:`. Home Assistant blueprints have no native version field, so both must move together; the `description:` is the only version a user sees in the HA UI.
3. In `CHANGELOG.md`, give the top `[X.Y.Z]` section its date (replace "Unreleased").
4. Write `RELEASE_NOTES_vX.Y.Z.md` from that CHANGELOG section: add a one-line framing of the release, foreground any breaking change with an "action required" note and an *Upgrading* step, and append the install block (My Home Assistant badge + import link + README link).
5. Commit and push to `main`.
6. On GitHub: **Releases → Draft a new release → Choose a tag** `vX.Y.Z` (create on publish) → **Target** `main` → title `vX.Y.Z` → paste the release notes → tick **Set as a pre-release** (for `0.x`) → **Publish**. Do not use *Generate release notes* while the repo keeps curated notes.
7. Verify the release/tag resolves and the CHANGELOG's version link works.

Install links stay on `/main/` during the beta so testers always get the latest; pin them to a tag (`/vX.Y.Z/`) only once a version is considered stable.

---

## Credits

- Original *Play Music with Music Assistant* blueprint by [dinki](https://github.com/dinki/View-Assist).
- [Music Assistant](https://github.com/music-assistant) by the Open Home Foundation and contributors.
