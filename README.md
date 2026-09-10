# jingdingwang.github.io

Personal research site. Plain HTML + CSS — no build step, no dependencies.
Edit the files, commit, push; GitHub Pages redeploys in about a minute.

## Files

| File | What it is |
|---|---|
| `index.html` | All the content. Sections are marked with `<!-- ==== NAME ==== -->` comments. |
| `style.css` | All the styling. Colors are CSS variables at the top of the file. |
| `files/Wang_CV.pdf` | The downloadable CV. Overwrite this file to update it — the link never changes. |
| `files/photo.jpg` | Your headshot. **Not present yet.** Add it and it appears automatically; until then a "JW" placeholder shows. |
| `.nojekyll` | Tells GitHub Pages to serve the files as-is. Leave it alone. |

## Things to fill in

Search `index.html` for `data-placeholder` — there are three link buttons
(Google Scholar, ORCID, X/Twitter) whose `href` is still `#`. Replace each `#`
with the real URL, or delete the whole `<li>` line if you do not want that link.

## Adding a headshot

Save a photo as `files/photo.jpg`. Portrait orientation, roughly 4:5, at least
600px wide. It gets cropped to fill the frame, so center your face.

## Adding a new paper

Copy an existing `<article class="entry">` block in the Research section and
edit it. The `<span class="tag">` is the small red badge — use it sparingly.

## Updating the CV

```
cp /path/to/new/Wang_CV.pdf files/Wang_CV.pdf
git add -A && git commit -m "Update CV" && git push
```

## Previewing locally

```
python3 -m http.server 4173
```

Then open http://localhost:4173. Opening `index.html` directly by
double-clicking also works, but a server matches what GitHub Pages does.
