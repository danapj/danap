# danap

Dana Pek's portfolio, live at https://danapek.com.

Static files, no build step.

- `index.html`: the "work in progress" splash shown at danapek.com for now.
- `preview/index.html`: the full site, at danapek.com/preview/ (hidden from search engines, not secret).
- `img/`: photos and screenshots.
- `design/`: the design system (type scale, colours, spacing, components, voice). Read `design/README.md` before changing the look.

**To launch:** replace `index.html` with `preview/index.html`, change every `../img/` to `img/` and `../favicon` to `favicon`, remove the `noindex` line, then delete `preview/`.

## Editing

- **Work, case studies and photos** are lists near the bottom of `preview/index.html` (`WORK`, `FEATURED`, `PHOTOS`).
- **Screenshots and photos** go in `img/`. Reference them as `img/your-file.png`.
- **Unfinished placeholders** are hidden. Set `SHOW_TODOS = true` in `preview/index.html` to see them while editing locally.

Pushing to `main` publishes the site through GitHub Actions. Only `index.html`, `preview/`, `img/` and the favicons are published; everything else stays in the repo. If you add a new page or folder, add it to the "Collect site files" step in `.github/workflows/deploy.yml`.
