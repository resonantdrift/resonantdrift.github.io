# Heartside Games — deploy (keep the CNAME file in the repo root)
index.html  canasta.html  dominoes.html  rummikub.html  blokus.html
peerjs.min.js  favicon.svg  CHANGELOG.md  README.md

This build (v1.1.0):
- Every page now shows its version number as a small watermark, bottom-right.
- Added CHANGELOG.md (history of releases) and README.md (what's in the repo,
  how to publish, how the games work) — for your own reference; GitHub Pages
  doesn't serve them as pages, they just live in the repo.
- Canasta: guests couldn't connect (case-sensitive room codes + phone
  auto-capitalize) — fixed. "Start hosted game" now visibly greys out while
  waiting for a guest, instead of looking clickable-but-dead. Red 3 now
  correctly freezes the pile for only the next player's turn (a wild is the
  only card that freezes it permanently). Tapping a greyed "Take pile" now
  explains why, on-screen.
