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

## Workflow

1. Read `AGENTS.md`, the requested GitHub Issue, and any existing `projects/issue-<number>-<slug>/manifest.md`.
2. If the input is only an idea, discuss it until the Issue contract is complete. Show the final Issue draft and create it only after user confirmation.
3. Require Issue state `ready for production` before generation. Otherwise continue discussion or record the missing fields.
4. Create or resume the exact package defined by `references/output-contract.md`; never overwrite a successful stage silently.
5. Research first. Preserve source URLs and separate facts, quotes, opinions, and inference.
6. Produce title candidates, final copy, tags, and card plan. Apply the Humanizer-zh principles before visual generation.
7. On a new visual direction, render one representative cover/sample and get user confirmation before the rest of the batch.
8. Generate static assets with `AI_IMAGE_MODEL`; use deterministic HTML/card layout when the selected card workflow supports it. Static posts do not call `AI_VIDEO_MODEL`.
9. Inspect every final image, complete `qa.md`, and update `manifest.md` truthfully to `ready`, `partial`, or `blocked`.
10. Deliver file paths and unresolved risks. Stop before platform publishing.

## Hard rules

- One Issue equals one post; a batch is a list of Issue numbers.
- Use NewAPI for downstream text/image/video inference; never route directly to a vendor.
- Do not fabricate sources, data, personal experience, screenshots, or successful outputs.
- Missing credentials/model availability is `blocked`, not a reason to substitute an unapproved backend.
- Keep remote publishing outside this skill.
