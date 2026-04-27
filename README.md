# AIWire — Web

The career hub for AI work. **Land your AI job in 90 days.**

🚀 **Live demo:** https://prab187.github.io/aiwire-web/

---

## What is this?

AIWire is a personalized AI career platform:

- **Personal AI roadmap** — upload your resume; Claude builds a 90-day learning + application plan tailored to your background
- **Smart job matching** — every listing scored on 5 dimensions: skill fit, role level, location, salary, company quality
- **Mock interviews** — practice with an AI interviewer trained on real AI-role questions, voice or text
- **Live AI news + videos** — curated AI news feed + AI-summarized YouTube videos for your skills

This repository contains the **deployable web build** of the iOS Flutter app.

---

## Tech stack

| Layer | Tech |
|---|---|
| **Frontend** | Flutter Web (compiled from Dart) |
| **Intelligence** | Anthropic Claude Haiku 4.5 (with TTL caching) |
| **Job data** | Adzuna · Reed · The Muse · Remotive (4 boards aggregated) |
| **Video data** | YouTube Data API v3 + scraper fallback |
| **Events** | PredictHQ · Eventbrite |
| **Auth** | Apple Sign-In · Google Sign-In · guest mode |
| **Analytics** | Firebase Analytics |
| **Hosting** | GitHub Pages |

The full Flutter source (iOS · Android · Web) lives in a private repository.

---

## Run locally

```bash
git clone https://github.com/Prab187/aiwire-web.git
cd aiwire-web
python3 -m http.server 8080
# open http://localhost:8080
```

> Note: when running locally outside the `/aiwire-web/` path, edit `index.html` and change `<base href="/aiwire-web/">` to `<base href="/">`.

---

## Deploy

This repo is auto-deployed to **GitHub Pages** on every push to `main`. The workflow lives in `.github/workflows/deploy.yml`.

To enable Pages on a fresh fork:

1. Go to **Settings → Pages**
2. Source: **GitHub Actions**
3. Push to `main` — first deploy runs in ~30 sec

---

## Folder structure

```
.
├── index.html              # Entry point (with SEO + loading state)
├── 404.html                # Fallback for client-side routes
├── main.dart.js            # Compiled Flutter app (~3.7 MB)
├── flutter_bootstrap.js    # Flutter loader
├── canvaskit/              # Canvas renderer (~1.5 MB)
├── assets/                 # Fonts, images, AssetManifest
├── icons/                  # PWA icons
├── manifest.json           # PWA manifest
└── .github/workflows/
    └── deploy.yml          # Pages deploy on push
```

---

## License

Copyright © 2026 AIWire. All rights reserved.
