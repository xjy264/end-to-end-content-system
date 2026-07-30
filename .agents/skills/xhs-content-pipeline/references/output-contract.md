# Post Package Contract

Use this exact shape:

```text
projects/issue-<number>-<slug>/
├── brief.md
├── manifest.md
├── sources/
├── research.md
├── copy.md
├── cards/
│   ├── plan.md
│   └── output/
└── qa.md
```

## Status

`manifest.md` uses one of: `planning`, `researching`, `writing`, `designing`, `reviewing`, `ready`, `partial`, `blocked`.

Record the Issue URL, current stage, completed files, model IDs, last verification time, failures, and next action.

## Deliverable definitions

- `brief.md`: frozen audience, goal, angle, tone, boundaries, assumptions.
- `research.md`: claims with source mapping; separate fact, quote, opinion, inference.
- `copy.md`: title candidates, selected title, body, tags, CTA if applicable.
- `cards/plan.md`: cover hook plus one core message per page and evidence source.
- `cards/output/`: `1080x1440` PNG files named `xhs-01-cover.png`, `xhs-02-<slug>.png`, and so on.
- `qa.md`: source, copy, mobile readability, dimensions, crop, consistency, and package checks.

Never mark `ready` before every required file exists and every final image has been visually inspected.
