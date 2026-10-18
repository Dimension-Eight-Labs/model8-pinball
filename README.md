# Model 8 — DIM8 Pinball

A vintage-computer pinball table as an offline PWA. No ads, no tracking, no leaderboards.

## Run locally
    python3 -m http.server 8000
then open http://localhost:8000 (service worker only registers over https).

## Deploy
Push to a GitHub repo and enable Pages; open the Pages URL in Safari on the iPhone,
Share > Add to Home Screen. Bump VERSION in sw.js whenever a file changes.

## Controls
- Touch: hold left / right half for flippers; drag down on the right to pull the plunger (tap = standard shot); flick a finger upward to nudge.
- Keyboard: Z / Left Shift / Left arrow and / / Right Shift / Right arrow for flippers; hold Space, Enter or Down to pull, release to launch; N or Up arrow nudges; P or Esc pauses.

## Rules (v1)
- L-O-A-D lanes: light all four to raise the bonus multiplier (2x/4x/8x/16x). Flipping moves the lit lanes.
- Punch card: knock down all five drop targets for 10,000 and 2 core bits.
- Bus ramp: 2,500 and 1 bit. Core memory saucer: 1,000 and 1 bit. Eight bits = BYTE COMPLETE, 50,000.
- Vacuum-tube bumpers 100, slingshots 10, tape spinner 25 per spin.
- Nudge: four nudges in quick succession is TILT (flippers dead, no bonus). A ball that sits dead still for 2.5 s gets bumped (ball search).
- Nudge: four nudges in quick succession is TILT (flippers dead, no bonus). A ball sitting dead still for 2.5 s gets bumped (ball search).
- 3 balls, 8-second ball save after each launch, end-of-ball bonus x multiplier.

## Files
index.html (whole game, no dependencies), manifest.webmanifest, sw.js, icons/.

## iOS 27 top blur workaround
Installed iOS PWAs get a blur band over the top of the screen. A solid fixed strip (#topfix, color var(--bg)) at the top stops it; it only shows in the installed iOS app. It's a community workaround, not an Apple API; remove the #topfix CSS block and element if a future iOS changes things.
