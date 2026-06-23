Second beta of the **Expanded edition**. This release brings the alias-configuration inputs into a cleaner, labeled editor format and adds **radio station aliases** for stations that search doesn't resolve well.

⚠️ **Breaking change — action required.** The Join Alias Map and Announcement Sound Map now use a structured, labeled list instead of the old freeform key/value box. **Your existing entries will not carry over** and must be re-entered after updating (see *Upgrading* below). This is expected during the 0.x beta.

### Added
- **Radio station aliases.** "Play radio station …" can now match spoken names against an optional alias list — each entry pairs a spoken phrase with the exact Music Assistant radio media id and an optional friendly name. Aliases take priority and match case-insensitively; anything not listed falls back to the normal search, so nothing changes for stations you don't alias.

### Changed
- **The Join Alias Map and Announcement Sound Map are now structured lists.** Instead of typing `name: value` pairs into an object box, you click **Add** and fill labeled fields — Join entries are *Spoken phrase* + *Player entity_id*; Announcement entries are *Spoken name* + *Sound URL*. Matching is still case-insensitive, and Join still falls back to friendly-name matching when no alias is listed.

### Upgrading
After updating the blueprint, open your automation and re-enter any Join Alias Map and Announcement Sound Map entries using the new **Add** button. Values saved in the previous format won't appear and can be discarded.

---

⚠️ **This is an early beta (0.x).** Commands and behavior may change before 1.0.0.

**Install (Note that during the beta phase, the link and badge below will always update to the current development version, not this release tag.):**

[![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fgithub.com%2Fchangeling%2FView-Assist-Play-Music-Expanded%2Fblob%2Fmain%2FPlay_Music_with_Music_Assistant_Expanded%2Fblueprint-playmusicwithmusicassistantexpanded.yaml)

If the badge doesn't render, use [this import link](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fgithub.com%2Fchangeling%2FView-Assist-Play-Music-Expanded%2Fblob%2Fmain%2FPlay_Music_with_Music_Assistant_Expanded%2Fblueprint-playmusicwithmusicassistantexpanded.yaml). Full instructions and configuration are in the [README](https://github.com/changeling/View-Assist-Play-Music-Expanded/blob/main/Play_Music_with_Music_Assistant_Expanded/README.md) — please try it out and report any issues.
