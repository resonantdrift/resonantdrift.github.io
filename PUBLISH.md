# Heartside Games — publish checklist

Put ALL of these files in the root of your GitHub Pages repo (same folder as index.html):

    index.html      canasta.html   dominoes.html
    rummikub.html   blokus.html    peerjs.min.js   favicon.svg

Steps:
1. Copy every file above into the repo root (replace the old index.html and the old game files).
2. Commit and push.
3. GitHub Pages rebuilds in ~1 minute. Share your URL (heartsidegames.com) with testers.
4. In the repo's Settings → Pages, confirm "Enforce HTTPS" is on.

Notes:
- peerjs.min.js and favicon.svg must sit in the root — the games load them by relative path.
- All four games work solo, pass-and-play, and online (host a table, share the room code).
