# Heartside Games — deploy (keep the CNAME file in the repo root)
index.html  canasta.html  dominoes.html  rummikub.html  blokus.html
peerjs.min.js  favicon.svg  CHANGELOG.md  README.md

v1.2.0: Canasta connection resilience — a host heartbeat and a guest-side
"tap to resync" banner recover from a rare stalled WebRTC message, which
was the cause of a player occasionally getting stuck unable to act on
their turn in a live online game. See CHANGELOG.md for full detail.
