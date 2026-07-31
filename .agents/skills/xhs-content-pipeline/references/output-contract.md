# Post Package Contract

Use this exact shape:

```text
projects/issue-<number>-<slug>/
├── brief.md
├── manifest.md
├── sources/
├── research.md
├── copy.md
├── content-map.md
├── cards/
│   ├── plan.md
│   ├── html/
│   └── output/
├── generation-log.md
└── qa.md
```

The package must live inside the current repository. Repository-external directories may be used only for disposable working files, never as the formal delivery location.

## Status

`manifest.md` uses one of: `planning`, `researching`, `writing`, `designing`, `reviewing`, `ready`, `partial`, `blocked`.

Record the Issue URL, current stage, completed files, model IDs, branch, pull request URL, remote commit, repository status, last verification time, failures, and next action.

`ready` requires all mandatory files to be tracked by Git, the current commit to exist on the remote task branch, and a pull request to `main` to be open or updated.

## Deliverable definitions

- `brief.md`: frozen audience, goal, angle, tone, boundaries, assumptions.
- `research.md`: claims with source mapping; separate fact, quote, opinion, inference.
- `copy.md`: title candidates, selected title, body, tags, CTA if applicable.
- `content-map.md`: source-to-card mapping for every retained, merged, lightly edited, or removed core point.
- `cards/plan.md`: cover hook plus one core message per page and evidence source.
- `cards/html/`: reproducible HTML/CSS sources when the HTML route is used.
- `cards/output/`: `1080x1440` PNG files named `xhs-01-cover.png`, `xhs-02-<slug>.png`, and so on.
- `cards/output/preview-grid.png` and `cards/output/preview-mobile.png`: overview and mobile-readability previews.
- `generation-log.md`: renderer, model calls, generated files, and verification timestamp.
- `qa.md`: source, copy, mobile readability, dimensions, crop, consistency, and package checks.

Never mark `ready` before every required file exists, every final image has been visually inspected, and the complete formal package has been pushed to the pull request branch.
