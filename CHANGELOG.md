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
