# Changelog

All notable changes to this fork are documented here.

## [1.6.7.4.3] - 2026-06-17
- **Kudos history import** from [AO3: No Re-Kudos](https://greasyfork.org/en/scripts/551623) — absorbed automatically on first run and kept in sync going forward if you use both
- **Change Status dropdown and note boxes now match your active skin's real styling** (colors, borders, spacing) instead of a generic look
- **Fixed highlight-disabled status tags (e.g. "Dropped", "Finished Reading") stripping a work's normal border and shadow** instead of just skipping the glow effect

## [1.6.7.4.2] - 2026-06-17
- **Fixed AO3's History page not being recognized** — status highlighting, the quick-tag dropdown, and notes now work there too

## [1.6.7.4.1] - 2026-06-17
- **Rebased onto upstream 1.6.7.4**
- **Prefill bookmark note with work details** — auto-fills a customizable template (title, author, fandom, pairings, summary, series) when adding a status tag, with a live preview in settings
- **Highlight priority per status** — when a work matches multiple tracked statuses, the highest-priority one now controls the highlight instead of layering unpredictably
- **Fixed kudos/status/note changes occasionally being lost** if you made a change while a Google Sheets sync was in progress
- **Fixed "Reset Sync Settings" leaving behind stale sync state**

## [1.6.6.4.8] - 2026-05-12
- **Change Status now works on series**, not just individual works — buttons on series pages and the bookmarks listing
- **Fixed several series bookmark bugs**: stale tags/collections being re-sent on update, private/rec settings not applying to updates, wrong dropdown labels on the bookmarks listing, and stale status highlighting after deleting a series bookmark

## [1.6.6.4.7] - 2026-04-27
- **Fixed "Change Status" dropdown items scrolling the page to the top** when clicked

## [1.6.6.4.6] - 2026-04-24
- **Change Status dropdown redesigned** to sit directly in AO3's stats bar
- **Fixed the dropdown menu getting clipped** on bookmark listing pages
- **Added a customizable label** for the Change Status dropdown button
- **Fixed UI preference sync** (dropdown label, etc.) not syncing reliably across devices

## [1.6.6.4.2] - 2026-02-25
- **Fixed status config changes (e.g. highlight color edits) not syncing** to Google Sheets

## [1.6.6.4.1] - 2026-02-24
- **Safer, non-destructive Google Sheets setup** — connecting a second device now checks for existing data first instead of risking an overwrite
- **Custom status tags now sync across devices** along with their colors and settings
- **Fixed "Sync Now" occasionally uploading stale settings**
- **Improved reliability of the AO3 menu dropdown links** on mobile and slow-loading pages

## Versioning scheme
- Format: `upstream.major.minor.patch.forkPatch`
- Example progression:
  - `1.6.6.4.1`
  - `1.6.6.4.2`
  - upstream updates to `1.6.6.5` -> next fork release `1.6.6.5.1`
