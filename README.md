# GroundedAI Tools

Internal browser-based content and editing tools for the GroundedAI team. All tools run locally in the browser — no uploads, no servers, no accounts.

## Tools

| Tool | File |
|------|------|
| Video resizer | `resizer.html` |
| Loop maker | `loop-maker.html` |
| Speed up | `speed-up.html` |
| Frame capture | `frame-capture.html` |
| Tools menu | `index.html` |

All tools share the Bold Copper v3 brand system.

## Adding a new tool

1. Add the new HTML file to the root (e.g., `audio-compressor.html`)
2. Edit `index.html` — copy any existing `<a class="tool-card">` block, update icon, name, description, and `href`
3. Update the tool count in the section header
4. Commit and push
