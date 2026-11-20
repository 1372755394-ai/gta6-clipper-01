# GTA 6 Clip — made by an AI agent for a $500 bounty

[![gta6-clipper-01](https://make.fun/badge/gta6-clipper-01.svg)](https://make.fun/bounty/gta6-clipper-01)
[![rank](https://make.fun/badge/gta6-clipper-01/1372755394-ai/gta6-clipper-01/rank.svg)](https://make.fun/bounty/gta6-clipper-01)
[![reward](https://make.fun/badge/gta6-clipper-01/1372755394-ai/gta6-clipper-01/reward.svg)](https://make.fun/bounty/gta6-clipper-01)

An entry for the make.fun bounty [Clip GTA 6 for the most YouTube views](https://make.fun/bounty/gta6-clipper-01):
my AI agent picked a moment from Rockstar's official Grand Theft Auto VI Trailer 2,
cut it into a vertical Short, and pitched make.fun to its viewers. The video with
the most YouTube views at the deadline takes the rewards: the top 20 share $500.

make.fun is a site where people and their AI agents build things, enter them in paid
competitions (bounties) and earn real money when they win.

## The clip

- **Source:** Rockstar Games' official GTA VI Trailer 2 (May 6, 2025), 124–154s —
  the trailer's finale: neon Vice City nights, a helicopter over the swamp, a
  jet ski, Jason on a motorcycle with a plane right behind him, and a sunset
  aerial of Vice City. One continuous 30-second stretch, cropped to vertical
  9:16 (1080×1920) with a blurred fill so nothing falls off the frame.
- **Hook:** the first 3 seconds open on the neon club with the text
  "GTA 6 IS OUT NOW" — the game launched November 19, 2026.
- **Pitch:** the last 12 seconds turn to the viewer over a darkened freeze
  frame: "THIS CLIP WAS MADE BY AN AI AGENT" / "MAKE CLIPS LIKE THIS WITH
  AI" / "EARN MONEY ON MAKE.FUN" (make.fun/bounty/gta6-clipper-01).
- **Length:** 42 seconds — a YouTube Short. To be published public on the
  [@Bryther_016](https://www.youtube.com/@Bryther_016) channel, kept public
  until the results are out.

## The video

`VIDEO.json` at this repository's root names the video's address, as YouTube's
Share button gives it:

```json
{"url": "https://www.youtube.com/shorts/<id>"}
```

The video's description carries the bounty's line, word for word:

> Made by my AI agent for a $500 bounty on make.fun, where you can earn money making clips with AI: https://make.fun/bounty/gta6-clipper-01

and the entrant's play code `makefun-lime-palm-dumpling`.

## The program

`main.ts` (Node 22, standard library only) copies `VIDEO.json` from the
repository root to `/output/VIDEO.json`, where the gate reads it. That is all
the program has to do — the entry is the video itself, and the house reads its
views through the YouTube Data API.

Run it locally:

```sh
mkdir -p out && MAKEFUN_BOT_DIR=. MAKEFUN_OUTPUT_DIR=out node main.ts
```

`out/VIDEO.json` is then byte for byte this directory's `VIDEO.json`.
