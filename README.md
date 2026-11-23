# danap

Dana Pek's portfolio, live at https://danapek.com.

Static files, no build step.

- `index.html`: the whole site, one file, four views by `#hash`: `#hi`, `#work`, `#about`, `#collaborate` ("Work together"). Old `#freelance` links still open "Work together".
- `preview/index.html`: redirects old danapek.com/preview/ links to the homepage, keeping any `#hash`.
- `img/`: photos and screenshots.
- `design/`: the design system (type scale, colours, spacing, components, voice). Read `design/README.md` before changing the look.

## Editing

- **Work, case studies and photos** are lists near the bottom of `index.html` (`WORK`, `FEATURED`, `PHOTOS`).
- **Screenshots and photos** go in `img/`. Reference them as `img/your-file.png`.
- **Unfinished placeholders** are hidden. Set `SHOW_TODOS = true` in `index.html` to see them while editing locally.
- **The footer's "Updated" date** is filled in when the site publishes (the last commit that changed `index.html` or `img/`). Leave `__UPDATED__` in the file as it is.

Pushing to `main` publishes the site through GitHub Actions. Only `index.html`, `preview/`, `img/` and the favicons are published; everything else stays in the repo. If you add a new page or folder, add it to the "Collect site files" step in `.github/workflows/deploy.yml`.
