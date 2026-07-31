---
name: xhs-content-pipeline
description: Use when a user wants to discuss a Chinese content idea into a GitHub content Issue, turn an Issue into a complete Xiaohongshu image-post package, continue a paused content Issue, or batch-produce posts from Issue numbers.
---

# XHS Content Pipeline

## Purpose

Turn one idea into one clear content Issue, then turn that Issue into one complete, traceable Xiaohongshu post package. Codex remains the orchestrator; downstream model calls use the project's NewAPI configuration.

## Required references

- Read `references/issue-contract.md` while discussing or creating an Issue.
- Read `references/output-contract.md` before creating or resuming a post package.
- Read `references/model-routing.md` before any model call.
- Read `references/upstream-routing.md` only when selecting upstream methods or visual workflows.
- Read `templates/visual-library/README.md` before researching or selecting a visual template.

## Workflow

1. Read `AGENTS.md`, the requested GitHub Issue, and any existing `projects/issue-<number>-<slug>/manifest.md`.
2. If the input is only an idea, discuss it until the Issue contract is complete. Show the final Issue draft and create it only after user confirmation.
3. Require Issue state `ready for production` before generation. Otherwise continue discussion or record the missing fields.
4. Before formal generation, freeze the delivery structure in the Issue and `brief.md`: content type, final image count and role of each image, caption sections, tags, CTA, and platform-operation boundary. If the user changes any of these, update the Issue, brief, copy, and card plan before continuing.
5. In the content Issue's task worktree, create or resume the exact repository package defined by `references/output-contract.md`; never overwrite a successful stage silently or use a repository-external directory as the formal delivery location.
6. Research first. Preserve source URLs and separate facts, quotes, opinions, and inference. Build the source-to-card content map before deciding the final page count.
7. Produce title candidates, final copy, optional tags and CTA, and the card plan. Keep image responsibilities separate from caption responsibilities and apply the Humanizer-zh principles before visual generation.
8. For a new visual direction or template change, research 3–5 real posts from the same platform, topic, and content form. Record sources and real dimensions, present the layout candidates, and wait for the user's selection before formal rendering. Recheck both `candidate` and `validated` library entries before use.
9. Route by content type: preserve argument depth for opinion posts; lead with user benefit and cover capability, method, and result for tool explainers; keep the final image separate from prompt/tutorial caption text for AI-image showcases unless the frozen delivery structure says otherwise.
10. On an approved visual direction, render and refine the cover first. After approval, batch-render the remaining cards from the confirmed content map and visual template. Default to subtraction rather than adding unrequested progress bars, panels, diagrams, or decoration.
11. For text-led opinion, educational, and business-analysis posts, default to deterministic HTML/CSS layout and export. Call `AI_IMAGE_MODEL` only when the approved visual plan explicitly requires a photo, illustration, or other generated asset. Static posts do not call `AI_VIDEO_MODEL`.
12. Inspect every final image at original size and mobile-preview size, then complete `qa.md` against the content map and delivery structure. Mark `manifest.md` as `partial` or `blocked` when appropriate; reserve `ready` for a complete package that is tracked by Git and present on the remote task branch.
13. Commit and push the content package, create or update its pull request to `main`, and deliver the PR URL plus unresolved risks. Stop before platform publishing.

## Hard rules

- One Issue equals one post; a batch is a list of Issue numbers.
- Store every formal deliverable under `projects/issue-<number>-<slug>/` in this repository. GitHub pull requests are the delivery source; desktop folders and other repository-external paths are not deliverables.
- Track research, copy, content maps, reproducible HTML sources when used, final images, previews, generation logs, and QA results. Keep secrets, private sources, and unlicensed assets out of Git.
- Build a source-to-card content map before deciding the final page count. When the user asks to preserve source material, limit edits to clarity, repetition, sentence breaks, and necessary explanation.
- Inspect the real dimensions and layout system of user-provided visual references before deriving a template. Do not infer platform ratios or add unrequested visual complexity.
- Do not begin formal generation until the delivery structure is frozen. The latest explicit user correction replaces the earlier structure and must be reflected in the Issue and package files before work resumes.
- Keep image and caption responsibilities distinct. Tags and CTA are optional, and research or risk material enters public cards only when it affects a core fact, a necessary usage condition, or the user's decision.
- For tool explainers, the cover must state the user benefit before abstract mechanism, and the body must make capability, method, and result clear. For AI-image showcases, default to a pure final image plus separate prompt/tutorial caption text.
- Keep body copy readable and uncropped. Minor overlap among decorative page numbers, rules, or accents is acceptable when it does not obscure content.
- Use NewAPI for downstream text/image/video inference; never route directly to a vendor.
- Do not fabricate sources, data, personal experience, screenshots, or successful outputs.
- Missing credentials/model availability is `blocked`, not a reason to substitute an unapproved backend.
- Keep remote publishing outside this skill.
