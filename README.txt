Kelvin
========

Match white balance and EI across ARRI ALEXA cameras, then move them
together.

Kelvin shows a colour wheel for every camera. Match each camera by
eye on its own wheel, link the ones you've matched, and a master wheel
moves all of them at once while keeping the offsets between them.

Version 1.4.4. Newest download:
https://github.com/Kunkles/Kelvin-releases/releases/latest


WALKTHROUGH
-----------

The first time Kelvin opens, a walkthrough points at each control in
the window. It runs on two practice cameras, Practice A and Practice
B, which aren't on the network, so nothing it shows can change a real
camera. They're removed when the walkthrough ends, and your own
cameras (hidden during it) come back. See it again any time from
Help > Kelvin Walkthrough.


WHAT YOU NEED
-------------

- A Mac running macOS 14 (Sonoma) or later.
- ARRI ALEXA cameras on the same network as the Mac, and each camera's
  IP address (shown in the camera's network settings). Kelvin has
  been used with the ALEXA 35.


INSTALLING
----------

1. Unzip Kelvin.zip.
2. Drag Kelvin into your Applications folder.
3. Open it.

The first time Kelvin looks for a camera, macOS asks whether it may
find devices on your local network. Click Allow. Without it, Kelvin
can't reach the cameras.

If you clicked Don't Allow by mistake: System Settings > Privacy &
Security > Local Network, and turn Kelvin on.


IMPORTANT BEFORE A SHOOT
------------------------

- Every change goes to the camera straight away. Dragging a wheel or
  a slider changes the live picture.
- In ProRes, white balance is recorded into the image. In ARRIRAW it's
  metadata and can be changed later.


THE WINDOW
----------

  Sidebar       Your cameras: name, IP address, a status dot, current
                kelvin and tint, and a link button.
                Type an IP address in the box at the bottom and press
                Return (or +) to add a camera. Double-click a camera's
                IP address to change it.

  Master card   The lighter card on the left. It moves every linked
                camera together.

  Camera cards  One per camera, side by side, all the same size as the
                master.

Status dot: green is connected, orange is connecting, red is offline.
An offline camera's card shows the reason in red under its name.


ADDING, RENAMING AND REMOVING CAMERAS
-------------------------------------

- Add: type the camera's IP address in the sidebar box and press
  Return.
- Rename: click the name at the top of the camera's card and type.
- Change the address: double-click the address under the camera's name
  in the sidebar, type the new one, and press Return (Escape cancels).
  The camera reconnects at the new address, keeping its name, colour
  and link. An address another camera already has is refused.
- Remove: right-click the camera in the sidebar, or use the (...) menu
  on its card, and choose Remove Camera. Or select it in the sidebar
  and press Delete.

Kelvin remembers your cameras, which ones are linked, and the card
size, between launches.


MATCHING A CAMERA
-----------------

Each camera's wheel is laid out like a vectorscope:

  left ......... warmer (higher kelvin)
  right ........ cooler (lower kelvin)
  up and right . more magenta
  down and left  more green

The puck is that camera's setting. The small dots are the other
cameras, so you can see how far apart they are.

- Drag anywhere on the wheel to move the puck. It moves from where it
  is; grabbing the wheel never makes it jump.
- Hold Shift while dragging, or turn on Fine in the toolbar (or
  View > Fine, Option Command F), to move at a fifth of the speed.
- Click the wheel, then use the arrow keys:
      Left / Right   warmer / cooler by 100 K (10 K with Shift)
      Up / Down      magenta / green by 1 CC (0.1 with Shift)
- Or type a value into TEMP or TINT and press Return.

The (...) menu on a card has the camera's own white balance presets
(for example 3200 K and 5600 K), Zero Tint, and Copy White Balance to
All Cameras, which sets every other camera to exactly this camera's
values as a starting point.

Kelvin moves in 10 K steps and tint in 0.1 CC steps, as on the camera.


LINKING AND THE MASTER WHEEL
----------------------------

Once cameras match, link them:

- Click the link button on a camera's card or in the sidebar, or
- Choose Link All in the toolbar or in the master card's (...) menu.

A linked card is outlined in your Mac's accent colour, and its link
button is highlighted. The master card says how many cameras it is
moving.

The master puck sits at the average of the linked cameras. When you
move the master, every linked camera moves by the same amount:
the same amount of warming or cooling (the way a gel shifts
light, rather than the same number of kelvin) and the same tint in
CC. So if B camera sits 200 K warmer than A because that's what
matched by eye, it stays that much warmer.

If a move would push any linked camera past the end of its range, the
whole group stops there, so no camera falls out of the match.

You can still adjust any linked camera on its own wheel.


EI
--

Each card has an EI slider underneath the TEMP and TINT readouts.

- There is a tick for every EI the camera can use right now, with 800
  in the middle.
- Drag the slider: near a tick it pulls onto it. The camera only
  accepts listed EIs, so the value is always a tick.
- Or click a tick, or click the slider and use Left / Right to step one
  EI at a time.
- "ES" next to the value means the camera is in Enhanced Sensitivity.
- "not available" means Kelvin doesn't recognise this camera's EI
  list. EI is supported on the ALEXA 35 for now.

The master card's EI slider moves every linked camera by the same
number of stops. If the linked cameras are at different EIs, the
master shows the range, for example 400-800.

To keep white balance linked but set EI on each camera separately,
uncheck Link EI on the master card. The master EI slider greys out and
says "unlinked".


LENSES
------

Lenses have their own colour cast, so a lens change can break a match
you just made. Kelvin can hold the look across the change.

Under each camera's readouts is the lens on that camera. Choose one and
Kelvin moves that camera by the difference between the two lenses, so
the look stays where it was and only that camera's own cast changes.

The zero lens:

Pick one lens as the one everything else is measured from. Put it on
every camera, add it with New Lens, and match the cameras as usual. Its
offset stays zero: what you dial in there is the difference between the
bodies, which is the match itself. Every other lens is then measured
against that.

Setting a lens's offset:

1. Put the lens on the camera and choose it in the camera's lens menu.
   New Lens adds one, on that camera, with no offset yet. Nothing opens
   over the window, so the wheel stays under your hand.
2. Set the white balance: drag the wheel, type a value, or white
   balance on the camera itself. What you've moved it by shows in
   orange beside the lens name.
3. Click that orange amount, or choose "Apply ... to <lens>" from the
   lens menu.

From then on that lens carries the offset onto any camera it goes on.
If one body really does see a lens differently, use "Apply to <lens> on
This Camera Only" and that body keeps its own value for it; the rest
keep using the lens's.

"Make <lens> the Zero Lens" measures everything from a different lens
instead. Every lens moves by the same amount, so they keep their
relationships, and nothing on a camera moves.

An offset is a fixed amount of warming or cooling, not a fixed number
of kelvin, so a lens that runs a little warm runs just as warm at
3200 K as at 8000 K. That means the kelvin it is worth depends on where
you are: the lens list shows each offset at 5600 K, and a camera's card
shows it from wherever that camera is sitting.

Moving the master doesn't count as a lens correction: the look moves
and the offsets are kept. Only moving a camera on its own does.

Lens Offsets... in the lens menu lists every lens, what it does, and
any camera that has its own value for one. Each lens also holds its
make, model and serial number, so an offset belongs to the piece of
glass it was measured on rather than to the model: two copies of the
same lens don't have the same cast. The card shows only the short name
you give it; the rest is in the list and in the tooltip.


SIZE
----

All cards scale together when you drag the window's edge, the master
included. When you let go, the window fits itself to the cards.
Window > Fit Window to Wheels (Command 0) snaps the window back to the
cards.

The window can't be made smaller than the cards at their smallest.
If there are more cameras than fit on the screen, the cards scroll
sideways.


TANGENT PANEL
-------------

Kelvin can be driven from a Tangent panel (Element, Wave, Ripple).
Install Tangent Hub from tangentwave.co.uk, connect the panel, and
open Kelvin: the panel finds it on its own, and the sidebar says which
panel is connected. Window > Use Tangent Panel turns this off.

The panel has two modes; the B button steps between them.

  Camera   Ball 1 is the camera selected in the sidebar. The two
           buttons beside it select the previous and next camera.
           The ring is that camera's EI.

  Rig      Ball 1 is the master and moves every linked camera, as the
           master wheel does. Balls 2 and 3 are cameras, each cycled
           with the two buttons beside it, so you can hold two cameras
           under your hands. Each ring is that camera's EI.

Left and right on a ball is kelvin, up and down is tint,
the same as the wheel on screen. A count is a fixed amount of warming,
so a turn shifts the light by as much at 3200 K as at 8000 K. The A button is
ALT: hold it for finer moves.

The displays show which camera each ball is on and its values. On a
panel with a bigger display, the same is spelled out in full.

The layout above is the default. Tangent Mapper can change any of it:
Kelvin appears there as "Kelvin", with every control it has.


TROUBLESHOOTING
---------------

A camera stays red (offline)
  - Check the IP address against the camera's network settings. If
    it's wrong, double-click it in the sidebar, fix it and press
    Return.
  - Make sure the Mac and camera are on the same network.
  - Check Local Network permission: System Settings > Privacy &
    Security > Local Network > Kelvin.

The panel does nothing
  - Check Tangent Hub is installed and running, and that the panel is
    connected (Kelvin's sidebar says which panel it sees).
  - Check Window > Use Tangent Panel is ticked.
  - Kelvin has to be the application the panel is on. The Hub switches
    that automatically when Kelvin is in front.

The wheel seems to fight you
  - Someone may be changing white balance on the camera itself.
    Kelvin follows changes made on the camera, but never in the
    middle of your drag.

EI shows "not available"
  - The camera's EI list isn't one Kelvin recognises. EI is
    supported on the ALEXA 35 for now; white balance still works.


ABOUT
-----

Kelvin is free. It is signed with a Developer ID certificate and
notarised by Apple.

ARRI and ALEXA are trademarks of ARRI. Kelvin is not affiliated with
or endorsed by ARRI.
