# For Williams ♥

A cozy, single-page site for sharing memories, songs, and little reasons with someone special.  
Built as a pure static HTML/CSS/JS page (no build step required).

## Features

- Day / night theme (saved in the browser)
- Typed intro message
- Live “time together” counter (optional)
- Flip cards with personal reasons
- Photo gallery, audio player (with vinyl animation), and video section
- Particle / heart effects
- Optional uploader (`?edit`) that can push files directly into the GitHub repo
- Works on GitHub Pages and Netlify

## Quick start

1. Clone or download the repo.
2. Open `index.html` in a browser (or deploy it).
3. Put your photos, songs, and videos inside the `media/` folder.

Supported types:
- Images: `.jpg`, `.jpeg`, `.png`, `.gif`, `.webp`, `.avif`, `.svg`
- Audio: `.mp3`, `.m4a`, `.wav`, `.ogg`, `.aac`, `.flac`
- Video: `.mp4`, `.webm`, `.m4v`, `.mov`

## Customization

Open `index.html` and edit the block marked `// EDIT ME` (around line 615):

| Variable     | Purpose                                      | Example                          |
|--------------|----------------------------------------------|----------------------------------|
| `NAME`       | Name shown in the title and throughout the page | `"Williams"`                    |
| `START_DATE` | Start of the relationship (for the counter). Leave `""` to hide it. | `"2024-06-15"` or `""`         |
| `MEDIA_DIR`  | Folder that holds the media files            | `"media"`                        |
| `REPO`       | Required when hosting outside GitHub Pages (e.g. Netlify) so the page can list files | `{ owner: "aethertimi-ctrl", repo: "dami-repo", branch: "main" }` |
| `INTRO`      | Message that types out at the top            | Custom string                    |
| `REASONS`    | Array of texts for the flip cards            | Add/remove/edit strings          |
| `LOVE_LINES` | Messages shown when the “Send a little love” button is clicked | Array of strings              |

## Deploying

### GitHub Pages
Just enable Pages in the repo settings (branch `main`, root).  
The page automatically detects the GitHub Pages URL and lists files from the `media/` folder.

### Netlify (or any other host)
Because the page normally relies on the GitHub API to discover media files, set the `REPO` object:

```js
const REPO = { owner: "aethertimi-ctrl", repo: "dami-repo", branch: "main" };
```

Then deploy the repository as a static site (no build command, publish directory = `/`).

## File structure

```
.
├── index.html          # The whole site
├── media/              # Photos, audio, and videos go here
│   ├── dami.jpeg
│   ├── echoix.m4a
│   └── project.mp4
└── README.md
```

## Notes

- The uploader (`?edit`) needs a GitHub personal access token with contents read/write permission if you want to add files through the page itself.
- Filenames with spaces are supported.
- The site is fully client-side and works offline once the files are loaded.

## Code of Conduct

Please read our [Code of Conduct](CODE_OF_CONDUCT.md).

Made with ♥.
