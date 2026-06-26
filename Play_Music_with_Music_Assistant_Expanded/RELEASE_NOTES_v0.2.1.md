Patch release fixing the spoken confirmation for the **queue** command.

### Fixed
- "Queue {song} by {artist}" now responds with the queue confirmation ("Adding to the queue …") instead of the play confirmation ("Playing …"). The song was always queued correctly — only the spoken and on-screen reply was wrong. This bug was present since v0.1.0.

---

⚠️ **This is an early beta (0.x).** Commands and behavior may change before 1.0.0.

**Install (Note that during the beta phase, the link and badge below will always update to the current development version, not this release tag.):**

[![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fgithub.com%2Fchangeling%2FView-Assist-Play-Music-Expanded%2Fblob%2Fmain%2FPlay_Music_with_Music_Assistant_Expanded%2Fblueprint-playmusicwithmusicassistantexpanded.yaml)

If the badge doesn't render, use [this import link](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fgithub.com%2Fchangeling%2FView-Assist-Play-Music-Expanded%2Fblob%2Fmain%2FPlay_Music_with_Music_Assistant_Expanded%2Fblueprint-playmusicwithmusicassistantexpanded.yaml). Full instructions and configuration are in the [README](https://github.com/changeling/View-Assist-Play-Music-Expanded/blob/main/Play_Music_with_Music_Assistant_Expanded/README.md) — please try it out and report any issues.
