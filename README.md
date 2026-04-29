# GroundedAI Tools

Internal browser-based content and editing tools for the GroundedAI team. All tools run locally in the browser — no uploads, no servers, no accounts.

## Tools

| Tool | Path | Purpose |
|------|------|---------|
| Video resizer | `/resizer/` | Compress video to fit Claude's 30 MB upload limit |
| Loop maker | `/loop-maker/` | Convert video to web-ready loops (MP4 + WebM) or animated GIFs |
| Speed up | `/speed-up/` | Speed up videos 2x to 20x — turn long footage into time-lapses |
| Frame capture | `/frame-capture/` | Pull source-resolution stills from any video |

All tools share the Bold Copper v3 brand system.

## Deploy to GitHub Pages

### 1. Create the repo

```bash
cd groundedai-tools
git init
git add .
git commit -m "Initial: GroundedAI tools directory"
git branch -M main
git remote add origin https://github.com/<your-org>/<repo-name>.git
git push -u origin main
```

### 2. Enable GitHub Pages

1. Go to the repo on GitHub → **Settings** → **Pages**
2. Under **Source**, select **Deploy from a branch**
3. Choose **main** branch and **/ (root)** folder
4. Click **Save**

GitHub will publish to `https://<your-org>.github.io/<repo-name>/` within a minute or two.

### 3. (Optional) Custom domain

To serve at `tools.groundedai.com`:

1. In the repo, create a file at the root called `CNAME` containing just `tools.groundedai.com`
2. In your DNS (wherever GroundedAI's domain is managed), add a CNAME record:
   - **Name**: `tools`
   - **Value**: `<your-org>.github.io`
3. Back in GitHub → Settings → Pages, enter `tools.groundedai.com` under Custom domain and check "Enforce HTTPS" once the cert provisions (takes 5–30 minutes)

## Adding a new tool

1. Create a new folder at the root (e.g., `audio-compressor/`)
2. Drop the tool's HTML inside as `index.html`
3. Add a card to the index page (`index.html` at the root) — copy one of the existing `<a class="tool-card">` blocks and update the icon, name, tagline, description, tags, and `href`
4. Update the `section-count` in the index page header
5. Commit and push — GitHub Pages auto-deploys on push to main

## File structure

```
groundedai-tools/
├── index.html               # Tools directory landing page
├── .nojekyll                # Tells GitHub Pages to skip Jekyll processing
├── README.md
├── resizer/
│   └── index.html
├── loop-maker/
│   └── index.html
├── speed-up/
│   └── index.html
└── frame-capture/
    └── index.html
```

Each tool is fully self-contained (single HTML file with inline CSS and JS). No build step, no dependencies, no install.

## Brand system

All tools use Bold Copper v3 tokens:

- **Copper** `#DA7E3A` — primary CTA, key outcomes
- **Ember** `#C86E30` — subtle accents, hover states
- **Steel Blue** `#3791CF` — data, inputs, process indicators
- **Ink** `#1a1a1a` — text, dark surfaces

Typography: system stack (`-apple-system`, `BlinkMacSystemFont`, `Inter`) for sans, `SF Mono` / `Geist Mono` / `Menlo` for monospace.

Light theme is primary. Dark theme activates via `prefers-color-scheme`.
