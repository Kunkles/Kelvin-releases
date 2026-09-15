# CamMatch

**A Mac app for matching white balance and EI across ARRI ALEXA cameras,
then moving them together.** Match each camera by eye on its own colour
wheel, link them, and a master wheel moves every linked camera at once
while keeping the match you made.

**[Download CamMatch](../../releases/latest/download/CamMatch.zip)** ·
macOS 14 or later · free · [all releases](../../releases/latest)

---

## How it works

CamMatch talks to each camera over the network, through the camera's Web
Remote interface: the same one ARRI's browser remote uses. Add a camera
by its IP address and it gets a card with its own wheel.

### Match

Every camera has a colour wheel laid out like a vectorscope: warmer to
the left, cooler to the right, magenta up and to the right, green down
and to the left. Drag the puck, type a colour temperature or tint, or
step with the arrow keys. The other cameras show as faint dots on every
wheel, so you can see how far apart they are.

### Link

Link the cameras you've matched. The **master** wheel sits at their
average. Move it and every linked camera moves by the same amount:
colour temperature in mireds, the way a gel shifts light, and tint in
CC. Offsets you set by eye stay put, and a move stops when any linked
camera reaches the end of its range rather than letting one fall out of
the match.

### EI

Each card has an EI slider with a tick for every EI the camera can take
right now, with 800 in the middle. Near a tick, the slider pulls onto
it. The master EI slider moves linked cameras by the same number of
stops; uncheck **Link EI** to keep white balance linked while setting EI
camera by camera.

### Size

The master and every camera card are the same size and scale together,
from the toolbar, with ⌘= and ⌘−, or by dragging the window's edge. The
window fits itself to the cards.

---

## Installing

Download **[CamMatch.zip](../../releases/latest/download/CamMatch.zip)**
(that link always fetches the newest build), unzip it, drag **CamMatch**
to Applications and open it. The first time it looks for a camera, macOS
asks whether CamMatch may find devices on your local network. Allow it,
or CamMatch can't reach the cameras.

The zip includes **README.txt**, a guide to every control.

CamMatch is signed with a Developer ID certificate and notarised by
Apple, so it opens without warnings.

---

## Before you use it on a shoot

- **Every change goes to the camera immediately.** In ProRes, white
  balance is recorded into the picture; in ARRIRAW it's metadata you can
  change later.
- **The Mac has to reach each camera's network interface**: the same
  network, and the IP address the camera shows in its network settings.

---

## Known gaps

- **Used with the ALEXA 35.** White balance goes through settings other
  ALEXA models also have, but none has been tried.
- **EI is ALEXA 35 only for now.** A camera whose EI list doesn't match
  shows "not available" instead of a slider, rather than a wrong value.

---

## Trademarks

ARRI and ALEXA are trademarks of ARRI. CamMatch is not affiliated with
or endorsed by ARRI.

---

## Changelog

CamMatch matches white balance and EI across ARRI ALEXA cameras, then
moves them together.

### 1.0.0 — 2026-09-15

The first release.

#### Added
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
