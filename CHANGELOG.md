# Changelog

Kelvin matches white balance and EI across ARRI ALEXA cameras, then
moves them together. It was called CamMatch until 1.2.0.

## 1.2.2 — 2026-09-16

### Changed
- **A new window opens at its smallest size.** With no remembered
  window, Kelvin used to open at a fixed 1400 × 880. It now opens with
  every card at its minimum width, and that's also the default card size,
  so the window doesn't open small and then grow. Card sizes you've
  already set are kept, and a window you've used before still reopens
  where you left it.

## 1.2.1 — 2026-09-16

### Added
- **Buy Me a Beer.** A code to point a phone at, at the end of the
  walkthrough and in Help › Buy Me a Beer. Deliberately not a link:
  Kelvin doesn't send anybody to a payment page.

### Changed
- **The toolbar's zoom slider is gone.** The two magnifying glass
  buttons, ⌘= and ⌘−, and dragging the window's edge already scale the
  cards, and the slider was the widest thing in the toolbar for the
  least use.
- **Fine is a button with its name on it.** As a bare icon it was
  indistinguishable from the plain buttons beside it, and an unlit
  toggle gave no sign it could be switched on.

### Fixed
- **No more resize on launch.** The window is restored at whatever size
  it was last left, which is rarely what the cards need, and the first
  fit animated that difference — measured from one saved frame, the
  window slid through twelve sizes over about half a second. That fit
  happens without animation now, so the window simply opens at the right
  size. Fits you cause, like adding a camera, still animate.

## 1.2.0 — 2026-09-16

### Changed
- **The app is called Kelvin.** CamMatch sat too close to TCMatch, the
  timecode app, for two apps that live on the same cart. Your cameras,
  window size and Local Network permission carry over: the app keeps the
  identity it has always had underneath. Downloads have moved with it,
  to github.com/Kunkles/Kelvin-releases.

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
