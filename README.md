# Poornakanta Handral — personal website

A plain HTML/CSS site for GitHub Pages. No build step, nothing to install.

```
index.html        the page (all text lives here)
style.css         colours, fonts, layout
images/           every picture on the site — replace these
gallery/          gallery videos, their poster images and readme.txt
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
| `dare-to-dream.jpg` | Dare to Dream 2.0 award-ceremony photo (first item in the Gallery) | 1200 × 800 (3:2) |
| `qr-handralp.svg` | QR code shown in Contact (opens https://handralp.github.io) | — |
| `qr-handralp.png` | QR card with name and web address, sent by "Share QR code" | — |
| `skills/icon-*.png` | Logo marks for the Simulation row (Abaqus/3DS, ANSYS, COMSOL) | 64–128 px tall |
| `og-preview.jpg` | Preview image when the link is shared on WhatsApp/LinkedIn | 1200 × 630 |
| `favicon.svg` | Browser-tab icon (already made; optional to change) | — |

How pictures fit their frames:
- **Research topics:** shown whole inside a 3:2 frame (never cropped).
- **Gallery thumbnails:** cropped to 16:9; the full picture or video opens when clicked.
- **Publications:** fill their 3:2 frame and are cropped at the edges, so keep the important part near the centre.
- **Patent:** shown whole, in a white frame that takes the picture's own shape.

About 1200–1800 px wide is plenty.

**Videos (research topics only):** each research topic shows either a picture or a
video. Each video exists twice: `name-light.mp4` (white background, used by default) and
`name.mp4` (dark background, used when a visitor switches to dark mode). Each has a `.jpg`
of its labelled opening frame, shown until it plays. To give another topic a video, copy one
`<video …>` block in `index.html` and change the `src`, `poster`, `data-light` and `data-dark`
names. Use MP4 (H.264), no audio, under ~10 MB.

**Gallery:** the Gallery section (just before Contact) shows each video in `gallery/` as a
small thumbnail with a play button and its title only; clicking it opens the video in the large
player, with a download icon. Gallery items stand on their own (no links to other sections), so
pick videos that explain themselves. Details of each video are in `gallery/readme.txt`. To add one,
put the `.mp4` and a `.jpg` poster frame in `gallery/`, then copy one `<figure class="gal-item">`
block in `index.html` and change `data-src`, `data-title`, the poster and the caption (write spaces
in file names as `%20`). Gallery videos have a single version, used in both themes.
A gallery item can also be a photo (like the award photo): copy that block, which uses `data-img`
instead of `data-src` and has no play button; it opens the photo full size with a download icon.

**QR code:** the Contact section shows a QR code for https://handralp.github.io. The share icon
on its corner opens a small menu: **Share link** or **Share QR code** (the PNG card with name). On phones
this opens the phone's share sheet (WhatsApp, email, …); on computers without one, the link is copied
and the QR card is downloaded instead. It stays dark-on-white in both themes so phones can scan it. If the
web address ever changes, regenerate both files, e.g. with Python:
`pip install segno`, then
`python -c "import segno; q=segno.make('https://NEW-ADDRESS', error='q'); q.save('images/qr-handralp.svg', scale=10, border=4); q.save('images/qr-handralp.png', scale=20, border=4)"`
(this makes a plain PNG without the name; that is fine).

**Light and dark theme:** the site opens in the light theme. The sun/moon icon in the header
switches to dark, and the browser remembers the visitor's choice. Dark colours are set in
`style.css` under `:root[data-theme="dark"]`.

If your file is a `.png`, either convert it to `.jpg` or change the matching
`src="images/…"` in `index.html`. Keep images under ~500 KB so the page loads fast.

To update the CV, replace `files/Poornakanta_Handral_CV.pdf` (keep the name).
This public copy has no phone number on purpose.

## Where it lives

The site is published from the GitHub repository `handralp/handralp.github.io` (branch `main`,
folder `/ (root)`, set in **Settings → Pages**) at https://handralp.github.io.
The local copy is `D:\GitHub\webpage\handralp.github.io`; commit and push with GitHub Desktop.

## Updating later

Edit `index.html` (any text editor works), then upload or push the changed
files. GitHub republishes automatically within a minute or two.

- **After editing `style.css`:** change the `?v=…` tag on the stylesheet link in `index.html`
  (for example to `?v=2026-11-15`) so browsers load the new version instead of a cached one.

- **Profile links:** ORCID and LinkedIn are in the Contact section. To add Google Scholar or GitHub,
  remove the `<!--` and `-->` around those two lines and put in your own URLs.
- **New paper:** copy one `<li>…</li>` block in the Publications list and edit it. Each paper is
  one paragraph: the linked title (the small link icon at its start opens the DOI), then the authors
  (shown in italics) and the journal. The patent title links to the certificate the same way.
- **Skills:** four text columns (Experiments, Coding, Design, Visual design), each kept in
  alphabetical order, then a Simulation row showing each tool's logo mark from `images/skills/`
  (`icon-abaqus.png` is the 3DS mark, shown in white in dark mode). To add a skill, insert an
  `<li>` in the right place alphabetically; to add a simulation tool, add its logo to `images/skills/`
  and copy one `<li><img …>Name</li>` line.
- **Research topics:** each topic is a column in the Research section, with a small label
  (Measure / Move / See) above its title that matches the figures at the top of the page. Keep each
  description to about two sentences so the three columns stay level.

## Checking locally

Double-click `index.html` to open it in your browser. Fonts load from Google Fonts,
so the headings look right only when you are online.
