# jingdingwang.github.io

Personal research site. Plain HTML + CSS — no build step, no dependencies.
Edit the files, commit, push; GitHub Pages redeploys in about a minute.

## Pages

| File | Page |
|---|---|
| `index.html` | Home — name, research statement, about, current-work cards |
| `research.html` | Publications, job market paper, dissertation, works in progress, fieldwork, presentations |
| `teaching.html` | Instructor of record, TA appointments, methods training |
| `awards.html` | External and internal grants, service |
| `cv.html` | Embedded CV PDF plus education summary |
| `contact.html` | Email, office, profile links, references |
| `style.css` | All styling for all six pages. Colors are CSS variables at the top. |
| `.nojekyll` | Tells GitHub Pages to serve the files as-is. Leave it alone. |

### The nav bar is duplicated

Each page carries its own copy of the `<nav>` block, because there is no build
step to share one. **If you add or rename a page, update the nav in all six
files.** The current page is marked with `aria-current="page"`, which is what
gives it the red underline — move that attribute when you copy a nav.

## Files served for download

| File | Notes |
|---|---|
| `files/Wang_CV.pdf` | Linked from the nav, home page, CV page, and contact page. Overwrite it to update — the link never changes. |
| `files/Chia_Wang_Deflected_Disruption.pdf` | The *New Political Economy* article. |
| `files/photo.jpg` | Your headshot. **Not present yet.** Add it and it appears on the home page automatically; until then a "JW" placeholder shows. |

## Things to fill in

Search for `data-placeholder` across the HTML files — there are link buttons on
`index.html` and `contact.html` (Google Scholar, ORCID, X/Twitter) whose `href`
is still `#`. Replace each `#` with the real URL, or delete the `<li>` line if
you do not want that link.

## Adding a headshot

Save a photo as `files/photo.jpg`. Portrait orientation, roughly 4:5, at least
600px wide. It gets cropped to fill the frame, so center your face.

## Adding a new paper

Copy an existing `<article class="entry">` block in `research.html` and edit it.
The `<span class="tag">` is the small red badge — use it sparingly.

## Updating the CV

```
cp /path/to/new/Wang_CV.pdf files/Wang_CV.pdf
git add -A && git commit -m "Update CV" && git push
```

Keep the filename `Wang_CV.pdf` — seven links across three pages point at it.

**Then bump the version stamp.** Every CV link ends in `?v=2026-09-20`.
Browsers cache PDFs hard, so without a new stamp anyone who already opened the
old CV keeps seeing it. Find and replace the old date with the new one across
all files (`Cmd+Shift+H` in VS Code), and update the "Last updated" line in
`cv.html` to match.

## Previewing locally

```
python3 -m http.server 4173
```

Then open http://localhost:4173. Use a server rather than double-clicking
`index.html` — the embedded CV viewer on `cv.html` does not work over `file://`.
