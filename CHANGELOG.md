# Changelog

All notable changes to Heartside Games are tracked here, newest first.
Versions follow `MAJOR.MINOR.PATCH` — MAJOR for a new game or a rebuild of
how a game works, MINOR for features/fixes within a game, PATCH for small
site-wide tweaks (copy, style, favicon, etc).

The version number in each file also appears as a small, unobtrusive
watermark in the bottom-right corner of every page (e.g. `v1.1.0`) — so if
someone reports a bug, the first thing to ask is "what version does the
corner say?" before chasing it, since an old cached build is a very common
cause of a bug that's already fixed.

## v1.2.0 — Canasta connection resilience
- **Fix:** in a live 2-player online game, a player could occasionally get
  stuck unable to draw or act on their turn, with no error and no visible
  cause — as if the button just stopped working. Root-caused to an
  occasional stalled WebRTC message (the kind of thing that can happen on
  spotty Wi-Fi or cellular), which left the waiting player's screen out of
  sync with the actual game state. The turn logic itself was verified
  correct; this was a transport reliability gap.
- Added two layers of self-healing: the host now quietly re-sends the
  current game state to each guest every few seconds regardless of
  whether anything changed, so a missed update catches up on its own
  within moments. If a guest goes quiet for longer than that, a small
  banner appears — "Connection seems quiet — tap to resync" — that
  immediately requests a fresh state from the host.

## v1.1.0 — Canasta online + freeze-rule fixes
- **Fix:** guests couldn't connect to a hosted room. Room codes are now
  case-insensitive (the join field no longer gets mangled by a phone's
  auto-capitalize), and the "Start hosted game" button now visibly greys
  out with a "waiting for players" message instead of looking clickable
  while it's actually inert.
- **Fix:** a red 3 was incorrectly freezing the pile *permanently*, the
  same as a wild. Corrected: a red 3 now freezes the pile only for the
  next player's turn, then clears on its own — only a wild card freezes
  the pile until it's taken with two matching cards from hand.
- **Fix:** tapping a greyed-out "Take pile" button now explains why,
  right on screen (a hover tooltip alone doesn't work on a phone).
- Added versioning (this file, README, and the on-page version badge).

## v1.0.2 — Name fields, consistency pass
- Every game's name field (host and guest/join) now has a clear
  "✎ Your name — tap to change" label and a highlighted border, since
  several testers didn't realize names — including the host's — were
  editable. Applied consistently across Canasta, Dominoes, Rummikub,
  and Blokus.

## v1.0.1 — Drawn-tile highlight, legibility
- Canasta and Rummikub now highlight the card/tile *you* just drew — a
  few red blinks, then a held red rim for a few seconds — so it's easy
  to spot among your other cards. (Opponents' draws are never shown,
  by design, so this only ever applies to your own hand.)
- Bumped text size and contrast site-wide on the landing page, with an
  extra bump on phones, after feedback that it was hard to read for
  older family members.

## v1.0.0 — Soft opening
- Public launch of heartsidegames.com with all four games: Canasta,
  Dominoes, Rummikub, and Blokus.
- Every game supports solo (vs. a computer opponent with an adjustable
  difficulty), pass-and-play on one device, and online play by hosting
  or joining a room with a short code.
- Security hardening: PeerJS is self-hosted rather than pulled from a
  CDN, a Content-Security-Policy is set on every game, and player names
  are escaped everywhere they're displayed.
- Shared TURN/STUN setup across all four games so online play works
  from behind most home and corporate networks without any setup.
