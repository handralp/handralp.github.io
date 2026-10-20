# Poornakanta Handral — personal website

A plain HTML/CSS site for GitHub Pages. No build step, nothing to install.

```
index.html        the page (all text lives here)
style.css         colours, fonts, layout
images/           every picture on the site — replace these
files/            downloadable files (the CV PDF)
.nojekyll         tells GitHub Pages to serve the files as they are
```

## Replacing images

Save your picture **with the same file name** over the placeholder in `images/`.
No code changes needed.

| File | What goes there | Best size |
| --- | --- | --- |
| `profile.jpg` | Your portrait (shown in a circle) | 800 × 800, square |
| `research-thermal-expansion-light.mp4` + `.jpg` | Thermal-expansion animation, light theme (white background) | 1920 × 1080 |
| `research-thermal-expansion.mp4` + `.jpg` | Same animation, dark theme | 1920 × 1080 |
| `research-cable-robot-light.mp4` + `.jpg` | Cable-robot video, light theme | 1920 × 1080 |
| `research-cable-robot.mp4` + `.jpg` | Cable-robot video, dark theme | 1920 × 1080 |
| `research-stereo-vision-light.mp4` + `.jpg` | ArUco-marker Möbius reconstruction (experimental data), light theme | 1920 × 1080 |
| `research-stereo-vision.mp4` + `.jpg` | Same, dark theme | 1920 × 1080 |
| `patent-3d-printer.jpg` | The cable-actuated flexible-arm 3D printer | 1200 × 800 (3:2) |
| `pub-2026-thermal-expansion.jpg` | Acta Mechanica 2026 paper | 1200 × 800 (3:2) |
| `pub-2021-mobius-strips.jpg` | Proc. R. Soc. A 2021 paper | 1200 × 800 (3:2) |
| `pub-2020-elastic-ribbons.jpg` | JMPS 2020 paper | 1200 × 800 (3:2) |
| `pub-2020-elastica-robot.jpg` | Extreme Mechanics Letters 2020 paper | 1200 × 800 (3:2) |
| `pub-2019-shape-control.jpg` | J. Applied Mechanics 2019 paper | 1200 × 800 (3:2) |
| `dare-to-dream.jpg` | Dare to Dream 2.0 award-ceremony photo | 1200 × 800 (3:2) |
| `og-preview.jpg` | Preview image when the link is shared on WhatsApp/LinkedIn | 1200 × 630 |
| `favicon.svg` | Browser-tab icon (already made; optional to change) | — |

How pictures fit their frames:
- **Research topics and the award photo:** shown whole inside a 3:2 frame (never cropped).
- **Publications:** fill their 3:2 frame and are cropped at the edges, so keep the important part near the centre.
- **Patent:** shown whole, in a white frame that takes the picture's own shape.

About 1200–1800 px wide is plenty.

**Videos (research topics only):** each research topic shows either a picture or a
video. Each video exists twice: `name-light.mp4` (white background, used by default) and
`name.mp4` (dark background, used when a visitor switches to dark mode). Each has a `.jpg`
of its labelled opening frame, shown until it plays. To give another topic a video, copy one
`<video …>` block in `index.html` and change the `src`, `poster`, `data-light` and `data-dark`
names. Use MP4 (H.264), no audio, under ~10 MB.

**Light and dark theme:** the site opens in the light theme. The sun/moon icon in the header
switches to dark, and the browser remembers the visitor's choice. Dark colours are set in
`style.css` under `:root[data-theme="dark"]`.

If your file is a `.png`, either convert it to `.jpg` or change the matching
`src="images/…"` in `index.html`. Keep images under ~500 KB so the page loads fast.

To update the CV, replace `files/Poornakanta_Handral_CV.pdf` (keep the name).
This public copy has no phone number on purpose.

## Publishing on GitHub Pages (first time)

1. Create a free account at github.com. Your username becomes your web address.
2. Create a new **public** repository named exactly `handralp.github.io`
   (replace handralp with your GitHub username).
3. Upload the contents of this folder (not the folder itself):
   **Add file → Upload files**, drag everything in, then **Commit changes**.
   Or, with GitHub Desktop: clone the repo into `D:\GitHub`, copy these files in, commit, push.
4. In the repository go to **Settings → Pages**, set *Source* to
   **Deploy from a branch**, branch **main**, folder **/ (root)**, and save.
5. After a minute or two the site is live at `https://handralp.github.io`.
6. In `index.html`, replace `handralp` in the `og:image` line so link previews work.

## Updating later

Edit `index.html` (any text editor works), then upload or push the changed
files. GitHub republishes automatically within a minute or two.

- **After editing `style.css`:** change the `?v=…` tag on the stylesheet link in `index.html`
  (for example to `?v=2026-10-25`) so browsers load the new version instead of a cached one.

- **Profile links:** ORCID and LinkedIn are in the Contact section. To add Google Scholar or GitHub,
  remove the `<!--` and `-->` around those two lines and put in your own URLs.
- **New paper:** copy one `<li>…</li>` block in the Publications list and edit it.

## Checking locally

Double-click `index.html` to open it in your browser. Fonts load from Google Fonts,
so the headings look right only when you are online.
