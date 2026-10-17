# VFX MUSIC VAULT

Responsive neon music web app powered by SOURAJIT VFX, with a Node.js JioSaavn API proxy.

## Features
- Search JioSaavn tracks by song, artist, or keyword
- Artwork and artist/album metadata
- Stream when the provider returns a usable audio URL
- Load a JioSaavn playlist by its playlist/list ID from the player queue button
- Local liked songs, recently played, and a browser-local playlist
- Demo tracks remain available if the API is temporarily unavailable

## Deploy the backend (Render, Railway, or Koyeb)
Use this repository as a Node.js web service. Build command: `npm install`. Start command: `npm start`. Node.js 18 or newer is required. The server reads the hosting platform's `PORT` variable.

After deployment, test `https://YOUR-BACKEND/api/health` and `https://YOUR-BACKEND/api/search?q=arijit`.

## GitHub Pages or InfinityFree frontend
These are static hosts and cannot run `server.js`. Deploy the Node.js backend separately on Render/Railway/Koyeb, then edit `config.js` and set:

```js
window.VFX_API_BASE = "https://YOUR-BACKEND-DOMAIN";
```

Commit the real backend URL (no trailing slash is required). If you leave it empty on a static host, live API search will not work. InfinityFree: upload the static files to `htdocs`; do not upload `server.js` expecting it to run.

## API notes
The backend calls JioSaavn's web API and normalizes common search/playlist response fields. This is an unofficial integration; endpoints, CORS/network availability, stream URLs, and service terms can change. No API key or credentials are included. Stream playback is only possible when the returned media URL is available to the browser. Respect the service's terms and applicable music rights.

## Local run
Install Node.js 18+, run `npm install`, then `npm start` and open `http://localhost:3000`.
