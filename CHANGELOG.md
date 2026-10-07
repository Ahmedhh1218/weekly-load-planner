# Changelog

## 1.3.0 - 2026-10-07

- Tapping a block now only shows its details. A small pencil button on the block turns on editing (drag, resize, change details), and a tick or Done turns it off.
- Tapping empty space closes the details.
- New Add block button in the schedule panel.
- Fix: installing an update could keep old files from the browser cache, so some phones kept the old layout. Updates are now fetched fresh.

## 1.2.0 - 2026-10-07
- Phone layout: on narrow screens the week shows days across and hours down, so it scrolls with the page instead of sideways. Drag, resize and tap-to-add work in both layouts.
- Fixed: the timeline could jump under your finger or mouse while dragging a block, because the summary text above it changed height.

## 1.1.0 - 2026-10-07
- Income and the expense log now fold open and closed, with a one line summary when closed. Your choice is remembered.

## 1.0.0 - 2026-10-07
First public release.
- Weekly timeline with drag, resize and add, undo, overlap warnings
- Charts: hours or effort by category, load against daily capacity
- Money view: fixed and hourly income in any currency, daily expenses, budgets, recurring bills, six month trend
- Live exchange rates with manual override
- Backup and restore (JSON), first-run setup with templates
- Light, dark and automatic themes
- Installable and offline (service worker), with an update prompt
