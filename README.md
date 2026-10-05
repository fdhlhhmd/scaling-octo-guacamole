# QR Studio (PWA)

Installable, offline-capable QR code app. No build step, no backend.

## Run locally
Service workers need HTTPS or localhost:

    python3 -m http.server 8080
    # open http://localhost:8080

## Deploy to GitHub Pages (included workflow)
1. Create a GitHub repo and push these files to the `main` branch (keep `.github/workflows/deploy.yml`).
2. In the repo go to Settings > Pages and set Source to "GitHub Actions".
3. Push again (or run the workflow from the Actions tab). The site goes live at https://YOUR-USER.github.io/YOUR-REPO/

## Deploy elsewhere (any static host with HTTPS)
Upload this whole folder. Examples: GitHub Pages, Netlify (drag and drop), Vercel, Cloudflare Pages.
If you host in a sub-folder (e.g. https://user.github.io/qr-studio/), it works as is: all paths are relative.

## Install
- Android / Chrome / Edge: menu > Install app (or the install icon in the address bar)
- iPhone / iPad Safari: Share > Add to Home Screen

## Notes
- History is stored in the browser (localStorage) on each device. There is no sync.
- The camera scanner needs HTTPS (or localhost) and camera permission. "Scan image" works without it.
- After editing any file, bump CACHE in sw.js (e.g. qr-studio-v2) so installed copies update.
- Libraries are bundled in vendor/: qrcode-generator 1.4.4, JSZip 3.10.1, jsQR 1.4.0.
