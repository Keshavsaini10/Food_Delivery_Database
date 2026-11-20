# Deployment guide

This repo is a static project overview (index.html + Markdown docs). It can be deployed on **Render** (Docker) or **Vercel** (static). Both need the files in this folder to be at the **root of the GitHub repo**.

## Render (fixes "failed to read dockerfile")

1. Make sure `Dockerfile`, `nginx.conf.template`, `index.html`, `docs/`, `proto/` are at the repo root on `main`:
   ```bash
   git add .
   git commit -m "Add Dockerfile and deployment config"
   git push origin main
   ```
2. Render → your service → **Settings**:
   - Language/Runtime: **Docker**
   - Dockerfile Path: `./Dockerfile`
   - Docker Build Context Directory: `.`
   - Health Check Path: `/healthz`
3. **Manual Deploy → Deploy latest commit**.

Or use the Blueprint: **New → Blueprint** and select the repo; it reads `render.yaml`.

Test locally:
```bash
docker build -t food-delivery .
docker run --rm -p 8080:10000 food-delivery
# open http://localhost:8080
```

## Vercel

Import the repo, Framework Preset **Other**, leave Build/Output/Install empty, Deploy. `vercel.json` handles clean URLs and shows `.md`/`.proto` files in the browser.

## Note

Render "Web Services" host a running app. A database-only repo should instead use **New → PostgreSQL** (or an external MongoDB such as Atlas for this project's design).
