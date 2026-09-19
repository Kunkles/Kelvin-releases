# Changelog

Kelvin matches white balance and EI across ARRI ALEXA cameras, then
moves them together. It was called CamMatch until 1.2.0.

## 1.6.0 — 2026-09-18

### Added
- **Kelvin-only and tint-only drags.** Hold Command while dragging for
  kelvin alone, Option for tint alone.
- **Cameras are named after themselves.** A camera that reports its index
  letter is called "B Cam" and so on, until you give it a name of your
  own.
- **Zero Kelvin and Zero Tint on every card.** On a camera they put that
  axis back to neutral; on the master they undo its shift on that axis.
- **White balance presets on every camera's menu**, the camera's own when
  it reports them and the usual four when it doesn't.

### Changed
- **Zeroing the master undoes what it did.** It used to drop the handle
  back in the middle and leave the shift on the cameras. It now takes its
  own shift back off the linked cameras; what you dialled on each camera
  by hand stays. The master's menu has lost its colour temperatures,
  which meant nothing on a control that only ever shifts.
- **Fine lights up in the accent colour.** The system's "on" grey for a
  toolbar button is too quiet to catch across a cart.
- **The wheels move at half the speed.** Dragging tracked the wheel one
  for one, which is more than the hand wants when matching by eye. Fine
  is unchanged, so it's finer again by the same margin as before.
- **The master puck stays where you put it, and reads out a shift.** It
  sat at the linked cameras' average, so dialling one camera by hand
  dragged the master around with it. The master moves cameras by a shift,
  so it's a handle rather than a reading: it now sits in the middle of
  its wheel at zero, only moves when you move it, and its readouts say
  how far the rig has been shifted (+200 K, +0.5 CC) rather than a colour
  temperature. Zero the Master, in its menu, puts the handle back in the
  middle without moving a camera. A master move still shifts every linked
  camera equally and still stops at the first camera's limit.
- **The ND list comes from the camera.** A camera that reports its
  filters offers those; only one that reports none falls back to the
  ALEXA 35's.

## 1.5.0 — 2026-09-18

### Changed
- **No lens button on the master card.** The master has no lens, so the
  row is blank space there; it keeps the cards the same height and the EI
  sliders lined up. The lens list is still in each camera's lens menu.

## 1.5.0 — 2026-09-18

### Added
- **Internal ND offsets.** Each card now carries the ND in that camera
  beside its lens — No ND, 0.6, 1.2, 1.8. An ND stays with the body, so
  its offsets are that camera's alone: match the camera with the ND in
  and click the orange amount to set it. ND and lens offsets add up.
- **Kelvin follows the ND in the camera, and can move it.** Turn the ND
  wheel on the camera and Kelvin sees the filter change and applies that
  camera's offset for it, with nothing to tell the app; choosing an ND in
  Kelvin moves the filter in the camera. On a camera that reports no
  filter, the ND is just something you tell Kelvin, as before.

### Changed
- **No lens button on the master card.** The master has no lens, so the
  row is blank space there; it keeps the cards the same height and the EI
  sliders lined up. The lens list is still in each camera's lens menu.

### Fixed
- **What you've dialled clears as soon as it's applied.** The amount
  beside the lens is worked out from a value the card wasn't watching, so
  it sat there stale until something else redrew the card.

## 1.4.4 — 2026-09-18

### Fixed
- **The window fits the cards again.** The lens row, added in 1.4.0, made
  every camera card taller than the master, and the window still ended at
  the bottom of the master: the cards were cut off. The master now has a
  row of its own (Lens Offsets…, which opens the list), so the cards are
  the same height again, and the window fits whichever card is tallest so
  this can't cut one off again.
- **Fine can't go missing.** It's now in the View menu (⌥⌘F) as well as
  the toolbar, and the two toolbar buttons are separate items rather than
  a group, so a crowded toolbar can't drop Fine while keeping Link All.

## 1.4.3 — 2026-09-18

### Fixed
- **The walkthrough's "Or type it" page points at the readouts again.**
  The lens row, added in 1.4.0, had taken over the marker the tour aims
  at, so the page spotlighted the lens menu instead. The same slip left
  the kelvin and tint fields editable on an offline camera.

## 1.4.2 — 2026-09-18

### Changed
- **It's called kelvin, the way the camera does.** The walkthrough, the
  guide, the public page and the Tangent panel's controls all say kelvin
  rather than colour temperature, so the app and the camera use one word
  for the same setting. The panel's displays read "A K", "Rig K", and
  the readouts on the cards are unchanged.
- **Lens offsets read in kelvin, not mireds.** Nothing on screen says
  mired any more. A correction you've dialled shows as the change you
  actually made — "Apply +530 K" — and a lens in the menu shows what it
  is worth on that camera where it sits now; the lens list shows each one
  at 5600 K. An offset is still held as a fixed amount of warming, so it
  holds at any kelvin, which is why the number it is worth moves with the
  look.

## 1.4.1 — 2026-09-18

### Changed
- **The walkthrough covers lenses.** Two pages after EI: one pointing at
  the lens on a card, and one on setting an offset — pick a zero lens,
  put a new lens on, match it, apply it.

## 1.4.0 — 2026-09-18

### Added
- **Lens offsets.** Each camera card has the lens that's on it. Choosing
  a different one moves that camera by the difference between the two
  lenses' casts, so a match survives a lens change. Match a camera after
  putting a lens on and the correction shows beside the lens name; fold
  it into that lens and every camera that takes the lens gets it, or
  apply it to one body only when that body really does see the lens
  differently. New Lens puts a lens on the camera with no offset and
  opens nothing over the window, so the wheel is there while you set it,
  and one lens can be made the zero every other lens is measured from.
  Each lens also holds its make, model and serial, so an offset belongs
  to the copy it was measured on. Offsets are kept in mireds and CC, so they hold at any
  colour temperature, and moving the master moves the look without
  touching them.

## 1.3.0 — 2026-09-18

### Added
- **Tangent panel support.** With Tangent Hub installed, an Element,
  Wave or Ripple panel finds Kelvin by itself. In Camera mode ball 1 is
  the camera selected in the sidebar; in Rig mode ball 1 is the master
  and balls 2 and 3 are cameras you cycle with the buttons beside them.
  Rings set EI, and the panel's displays name the camera each ball is on
  and show its colour temperature and tint. One count is one mired, so a
  turn shifts the light by as much at 3200 K as at 8000 K. Every move
  goes through the same code as the wheels, so nothing the panel does is
  out of step with the window. Tangent Mapper can remap all of it, and
  Window › Use Tangent Panel turns it off, and the walkthrough has a page
  on it.

## 1.2.4 — 2026-09-16

### Added
- **Change a camera's address in the sidebar.** Double-click it, type the
  new one and press Return; Escape cancels. The camera reconnects at the
  new address and keeps its name, colour and link. An empty address, or
  one another camera already has, is refused.

## 1.2.3 — 2026-09-16

### Changed
- **No zoom controls.** The magnifying glass buttons are gone from the
  toolbar, and Bigger and Smaller Wheels from the Window menu. The cards
  still scale by dragging the window's edge, and Fit Window to Wheels
  (⌘0) still snaps the window back to them.

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
