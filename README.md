# HOLO — control your notes with bare hands

Iron Man mode for your markdown notes. Your webcam becomes the interface: folders float as orbs on your own mirrored video, you pinch files out of the air, throw them with real momentum, crush a note between two hands and the AI voice reads you the TL;DR.

No cloud. No API keys. No accounts. Hand tracking runs 100% on your machine (Google MediaPipe, self-hosted in this folder) and your camera frames never leave the page.

Built live with Claude Code as part of the JARVIS second-brain project.

## Run it (2 steps)

```
python3 server.py
```

Open http://localhost:4890 in Chrome, allow the camera, raise a hand.

That's it. Python 3 is the only requirement (standard library only, nothing to install).

## The gestures

| Do this | Get this |
|---|---|
| PINCH a card | grab it, drag it, throw it with real momentum |
| Quick pinch (tap) | orb opens its files, note opens the reader |
| Flick a note off-screen | it evaporates |
| Two-hand STRETCH a note | big = opens the reader, CRUSH it small = spoken TL;DR |
| Two pinches in empty space | zoom + rotate the whole scene |
| Open palm, snap to FIST | force-pull the nearest far card to you |
| Open palm THRUST at camera | repulsor blast, everything shoves away |
| POINT (one finger) | draw glowing ink in the air |
| Both palms sweep down, or PEACE ✌ | everything tidies into a grid |
| CLAP | shockwave scatters the board |
| Drag to the right edge | dock a card on the shelf |

An on-screen legend shows all of this while you play.

## JARVIS mode

Press `J`. The deck goes gold, and the AI speaks about what your hands do: "Filed, sir." "Clean slate, sir." Crush a note and he reads you the gist out loud. Voice is your browser's own local speech engine (Daniel, the British butler, if your machine has him). Zero setup, zero keys.

## Your own notes

Point `holo.json` at any folder of markdown files:

```
{"folder": "/path/to/your/notes"}
```

Subfolders become orbs. It ships pointed at `sample-notes/` so it works the second you run it.

## Extras

- `?sim=1` — a scripted demo loop plays with synthetic hands, no camera needed
- `?probe=1` — the built-in test battery runs the real engine on synthetic frames (this build: 22/22)
- Mouse works as a fallback everywhere

## Want the full JARVIS?

This deck is the free slice of a much bigger build: the full JARVIS second brain has a 3D knowledge galaxy you steer with these same hands, a voice you talk to, phone calls it makes for you, email and calendar, and a computer-takeover mode.

The full build, the install lessons, and every project like it live in the AI Workshop community: https://www.skool.com/aiworkshop

Watch it get built: https://www.youtube.com/@mygptworkshop

## License

Original code: MIT (see LICENSE). The `vendor/` folder contains Google MediaPipe Tasks Vision (Apache-2.0) and three.js (MIT), self-hosted so ad-blockers and offline machines can't break the tracking. Note: both `vendor/wasm/vision_wasm_*.js` files carry a one-line shim at the top (marked HOLO SHIM) that fixes a crash in the release build of MediaPipe's wasm glue. If you re-download MediaPipe yourself, you need to re-apply it.
