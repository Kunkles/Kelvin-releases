# Changelog

CamMatch matches white balance and EI across ARRI ALEXA cameras, then
moves them together.

## 1.1.0 — 2026-09-15

### Added
- **A walkthrough.** The first launch dims the window and spotlights each
  control in turn, with a card saying what it's for, the way Ringr's tour
  does. It runs on two practice cameras that never touch the network and
  are removed when it ends; your own cameras are hidden, not removed,
  while it's open. It stays in Help › CamMatch Walkthrough.

## 1.0.0 — 2026-09-15

The first release.

### Added
- **A wheel for every camera.** Add cameras by IP address. Each gets a
  card with a colour wheel laid out like a vectorscope, colour
  temperature and tint readouts you can type into, and a menu with the
  camera's own white balance presets. The other cameras show as dots on
  every wheel.
- **Link cameras to a master wheel.** Moving the master moves every
  linked camera by the same shift, in mireds and CC, so a match made by
  eye survives global changes. It stops at the end of any camera's range
  instead of breaking the match.
- **EI sliders** with a magnet tick at each EI the camera can take and
  800 in the middle. The master EI slider moves linked cameras by stops,
  and **Link EI** turns that off while white balance stays linked.
- **Cards that scale together** from the toolbar, ⌘= and ⌘−, or by
  dragging the window's edge, with the window fitting itself to them.
- **Fine control:** hold Shift or turn on Fine to drag at a fifth of the
  speed, and step with the arrow keys.
- CamMatch remembers your cameras, which are linked, and the card size.
