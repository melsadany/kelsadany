# Khalid Elsadany - Architecture Portfolio

Portfolio website for architect Khalid Elsadany, built with GitHub Pages (Jekyll, Cayman theme).

## Live Site
https://melsadany.github.io/kelsadany

## How to edit
Everything lives in `index.md`. Search for `[` to find placeholder text to replace.

| What | Where |
|---|---|
| Name, title, firm, contact links | Sidebar at the top of the `<body>` section |
| Headshot | `assets/images/profile/` (update the `<img src>` in the sidebar) |
| CV PDF | `assets/docs/profile/Elsadany-CV.pdf` |
| Projects | `#projects` section — copy a `<div class="project">` block per project |
| Project images | `assets/images/projects/<project-name>/` |
| Awards / competitions | `#recognition` section |
| Gallery | Put images in `assets/gallery/`, then add a line to `galleryImages` near the bottom of `index.md`. The `category` field creates filter buttons automatically. |
| Colors | `:root` CSS variables at the top of `index.md` |

Tip: compress images (e.g. under ~500 KB, 1600-2400 px wide) before uploading so the site loads fast. GitHub rejects files over 100 MB.

## Moving to Khalid's own account
1. Khalid creates a GitHub account (e.g. `kelsadany`).
2. Settings → Transfer ownership → transfer this repo to `kelsadany`.
3. Rename the repo to `kelsadany.github.io` so it is served at https://kelsadany.github.io.
