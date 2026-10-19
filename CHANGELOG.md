# ShowCaseStandalone changelog

## Version 3.0.1 — 2026-10-18

- Added an optional asynchronous GitHub update check once per startup.
- Report newer stable releases, the current version, or unknown status in the console. Checks do not download or install plugins.
- Added `update-checker.enabled` to existing configurations with a default of `true`.

- Updated the plugin to compile against Paper 26.3 build 205 and Java 25.
- Fixed legacy material initialization when signs are edited or clicked by replacing numeric sign data with the wall sign's current facing information.
- Safely ignore standing and hanging signs that are not supported shop signs.
- Preserve back-side sign text and update shop sign fronts after sign edits complete.
- Respect cancelled sign edits.
- Resolve current item names and `minecraft:` namespaced names without legacy material conversion. Numeric suffixes remain available for damage on damageable items; old numeric block variants must use their current material names.
- Updated item damage comparisons and main-hand item access to current APIs.
- Updated the default grass and path blacklist entries to their current material names.
- Updated WorldGuard and WorldEdit compilation dependencies to current API families.
- Handle the newer Essentials economy balance-limit exception without letting it escape the adapter.
- Removed obsolete MCStats reporting.
- Added Tommy10606 to the authors shown in plugin information and `/scs version`, retaining the original authors and contributor credits.
- Retained the plugin name, `/scs` commands, permissions, configuration paths, serialization aliases, and existing shop storage versions.
