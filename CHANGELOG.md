# Changelog

All notable changes to this fork are documented here.

## [1.6.6.4.8] - 2026-05-12
- Fork changes:
  - Added full Change Status support for series — status buttons on series pages and bookmarks listing page; creates/updates/deletes series bookmarks via `/series/{id}/bookmarks`
  - Series bookmarks automatically receive a `Series` bookmark tag on create/update; tag is stripped before the empty-bookmark check so auto-delete still fires correctly
  - Fixed stale `Series` collection entry being re-submitted on every update
  - Fixed `newBookmarksPrivate`/`newBookmarksRec` not being applied on series bookmark updates (was create-only)
  - Fixed incorrect Change Status dropdown labels for series on bookmarks listing page — now resolves `series_{id}` entity ID from the blurb class
  - Fixed stale localStorage for series statuses not being cleared when a series bookmark is deleted (series page now clears stale IDs on load when no bookmark exists)

## [1.6.6.4.7] - 2026-04-27
- Fork changes:
  - Fixed "Change Status" dropdown items scrolling page to top on click — added missing `event.preventDefault()` in `setupQuickTagListener`

## [1.6.6.4.6] - 2026-04-24
- Fork changes:
  - Added "Change Status" dropdown integrated into AO3's stats bar (`<dl class="stats">` / `<dd>` structure)
  - Fixed dropdown clipping/z-index issues caused by CSS `transform` stacking context and bookmark `overflow: hidden`
  - Added user-configurable `changeStatusLabel` setting (with settings panel UI) to customize the dropdown toggle text
  - Added `FT_uiConfig` sync key for cross-device sync of UI preferences; fixed constructor ordering bug, incorrect `LAST_SYNCED` gating, and missing key in initialization payload


## [1.6.6.4.2] - 2026-02-25
- Fork changes:
  - Fixed `FT_statusesConfig` changes (e.g. highlight color edits) not being pushed to Google Sheets sync
    - `optimizeOperations` now correctly collapses stale `set` ops: a newer `set` for the same key always replaces an older one, regardless of value — previously two different `set` values for the same key would both remain in the queue
    - `updateLocalStorage` no longer overwrites the local `FT_statusesConfig` with stale server data when there is an unpushed local change (detected via diff against `FT_lastSyncedStatusesConfig`); new custom statuses from the server config are still merged in, but local display settings (colors, borders, opacity) are preserved

## [1.6.6.4.1] - 2026-02-24
- Upstream base: `1.6.6.4`
- Fork changes:
  - Non-destructive Google Sheets initialization flow for secondary browsers
  - Safer sync success handling for multiple API response shapes
  - Added guard to prevent empty-browser initialization from overwriting remote data
  - Included kudos storage key in initialization payload
  - Synced custom status definitions via `FT_statusesConfig` (userscript-side)
  - Applied status config before status lists during pull so custom keys load correctly
  - Added userscript fallback to infer missing custom statuses from synced `FT_*` status keys
  - Persisted merged/inferred status config back to local settings for new-device initialization
  - Manual `Sync Now` now saves in-panel settings before syncing, preventing stale highlight/status config uploads
  - Added status-config confirmation logic after sync and automatic re-queue when server response does not confirm `FT_statusesConfig`
  - Fixed pending queue dedupe for status operations (duplicate same-action ops are no longer re-enqueued)
  - Updated remote status-config apply to be deletion-aware (remote config now replaces local status set by storage key)
  - Matched initialize pull behavior with the same deletion-aware status-config replacement semantics
  - Reset Sync Settings now also clears stale sync state keys (`FT_pendingChanges`, `FT_lastSyncedStatusesConfig`)
  - Added debug trace for initialize pull showing how many statuses were applied from remote config
  - Improved mobile reliability for AO3 top-menu dropdown labels by replacing one-shot injection with retry-based injection
  - Added DOM-aware retry triggers (`MutationObserver`, `pageshow`, and `visibilitychange`) so dropdown links appear when menu markup loads late
  - Hardened dropdown username detection with a fallback profile-link lookup and success/failure return flow for `addDropdownOptions`

## Versioning scheme
- Format: `upstream.major.minor.patch.forkPatch`
- Example progression:
  - `1.6.6.4.1`
  - `1.6.6.4.2`
  - upstream updates to `1.6.6.5` -> next fork release `1.6.6.5.1`
