Kelvin
========

Match white balance and EI across ARRI ALEXA cameras, then move them
together.

Kelvin shows a colour wheel for every camera. Match each camera by
eye on its own wheel, link the ones you've matched, and a master wheel
moves all of them at once while keeping the offsets between them.

Version 1.2.0. Newest download:
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
                colour temperature and tint, and a link button.
                Type an IP address in the box at the bottom and press
                Return (or +) to add a camera.

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
- Remove: right-click the camera in the sidebar, or use the (...) menu
  on its card, and choose Remove Camera. Or select it in the sidebar
  and press Delete.

Kelvin remembers your cameras, which ones are linked, and the card
size, between launches.


MATCHING A CAMERA
-----------------

Each camera's wheel is laid out like a vectorscope:

  left ......... warmer (higher colour temperature)
  right ........ cooler (lower colour temperature)
  up and right . more magenta
  down and left  more green

The puck is that camera's setting. The small dots are the other
cameras, so you can see how far apart they are.

- Drag anywhere on the wheel to move the puck. It moves from where it
  is; grabbing the wheel never makes it jump.
- Hold Shift while dragging, or turn on Fine in the toolbar, to move
  at a fifth of the speed.
- Click the wheel, then use the arrow keys:
      Left / Right   warmer / cooler by 100 K (10 K with Shift)
      Up / Down      magenta / green by 1 CC (0.1 with Shift)
- Or type a value into TEMP or TINT and press Return.

The (...) menu on a card has the camera's own white balance presets
(for example 3200 K and 5600 K), Zero Tint, and Copy White Balance to
All Cameras, which sets every other camera to exactly this camera's
values as a starting point.

Colour temperature moves in 10 K steps and tint in 0.1 CC steps.


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
colour temperature in mireds (the way a gel shifts light) and tint in
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


SIZE
----

All cards scale together:

- The size slider and magnifying glass buttons in the toolbar.
- Window > Bigger Wheels (Command =) and Smaller Wheels (Command -).
- Dragging the window's edge. When you let go, the window fits itself
  to the cards.
- Window > Fit Window to Wheels (Command 0) snaps the window back to
  the cards.

The window can't be made smaller than the cards at their smallest.
If there are more cameras than fit on the screen, the cards scroll
sideways.


TROUBLESHOOTING
---------------

A camera stays red (offline)
  - Check the IP address against the camera's network settings.
  - Make sure the Mac and camera are on the same network.
  - Check Local Network permission: System Settings > Privacy &
    Security > Local Network > Kelvin.

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
