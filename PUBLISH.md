# Heartside Games — deploy (keep the CNAME file in the repo root)
index.html  canasta.html  dominoes.html  rummikub.html  blokus.html  peerjs.min.js  favicon.svg

Canasta this build:
- Online: room codes are now case-insensitive and the join field no longer auto-capitalizes on phones (fixes guests failing to connect). "Start hosted game" now visibly greys out with a "waiting for players" hint until the guest joins.
- Red 3 freeze is now TEMPORARY — it freezes the pile for the next player's turn only, then clears (a wild still freezes permanently until taken).
- Take pile: tapping the greyed button now explains why on-screen (mobile has no hover tooltip).
