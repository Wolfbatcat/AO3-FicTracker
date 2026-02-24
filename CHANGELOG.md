# Changelog

All notable changes to this fork are documented here.

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

## Versioning scheme
- Format: `upstream.major.minor.patch.forkPatch`
- Example progression:
  - `1.6.6.4.1`
  - `1.6.6.4.2`
  - upstream updates to `1.6.6.5` -> next fork release `1.6.6.5.1`
