# toothdr.org

Static one-page site for Dr. Aida Goltalab Rad, DDS. No build step — plain HTML/CSS/JS.

## Files
- `index.html` — the whole site
- `assets/Aida-Rad-DDS-CV.pdf` — downloadable CV
- `fa/index.html` — Persian (RTL) version
- `assets/gallery/` — before/after cases from Instagram @dr.a.rad.dds (listed inside `#igGrid` in both pages)

## Deploy
**Manual (SSH):** on the server, inside the web root for toothdr.org:
```
git clone https://github.com/zarkeshmohsen-bot/toothdr.org .   # first time
git pull                                                        # updates
```

**Automatic:** `.github/workflows/deploy.yml` rsyncs to the server on every push to `main` once these repo secrets are set (Settings → Secrets → Actions): `SSH_HOST`, `SSH_USER`, `SSH_KEY` (private key), `SSH_PORT` (defaults to 2222), `DEPLOY_PATH` (e.g. `/home/USER/toothdr.org`). Until then the workflow just skips. rsync `--delete` never touches `.well-known` (AutoSSL), `cgi-bin` or the server's `.htaccess`.
