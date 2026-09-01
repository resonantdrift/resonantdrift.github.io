# Heartside Games

Classic table games, rebuilt to play together — solo against a computer,
passing one device around the room, or hosting a table for friends
anywhere. Live at **heartsidegames.com**.

## What's here

| File | Game |
|---|---|
| `index.html` | Landing page (the "porch light" home page) |
| `canasta.html` | Canasta |
| `dominoes.html` | Dominoes |
| `rummikub.html` | Rummikub |
| `blokus.html` | Blokus |
| `peerjs.min.js` | Self-hosted copy of the PeerJS library all four games use for online play |
| `favicon.svg` | Site icon (the "Hearth Heart" mark) |
| `CNAME` | Tells GitHub Pages which custom domain to serve — **don't delete this** |

Every game is a single, self-contained HTML file — no build step, no
server beyond GitHub Pages itself.

## Versioning

See **CHANGELOG.md** for the history of what changed and when. Every
page also shows its version as a small watermark in the bottom-right
corner (e.g. `v1.1.0`) — if you or a tester hit something odd, check that
number first. A stale cached copy of an older build is one of the most
common causes of a bug that's already been fixed, so it's always worth
a hard refresh before digging further.

Version numbers follow `MAJOR.MINOR.PATCH`:
- **MAJOR** — a new game, or a rebuild of how an existing one works
- **MINOR** — a feature or a real bug fix within a game
- **PATCH** — small site-wide tweaks (copy, style, favicon, etc.)

## Publishing an update

1. Copy the updated files into the root of the GitHub Pages repo,
   replacing the old ones. **Leave the `CNAME` file alone** — GitHub
   Pages needs it to keep serving heartsidegames.com; if it gets
   deleted, the custom domain silently detaches and the site falls back
   to the default `github.io` address.
2. Commit and push.
3. GitHub Pages rebuilds automatically, usually within about a minute.
4. Do a hard refresh (or an incognito window) before testing, so you're
   not looking at a cached copy of the old build.

## How the games work, briefly

- **Solo** — play against a computer opponent. Difficulty is adjustable
  per game.
- **Pass-and-play** — everyone takes turns on one device; a "hand-off"
  screen keeps each player's hand private from the others in between
  turns.
- **Online** — one player hosts (which creates a short room code) and
  the others join by entering that code. The host's device is the
  source of truth for the game state, which also keeps online play
  fair. Connections use PeerJS over WebRTC, with a shared TURN/STUN
  setup so it works from behind most networks without any setup on the
  players' end.

## Reporting an issue

The version badge in the corner of the page, plus a screenshot and a
short description of what you expected to happen, is normally all
that's needed to track something down.
