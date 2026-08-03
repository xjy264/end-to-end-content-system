# Generation Log

## 2026-08-03 Text

- Endpoint role: NewAPI text generation
- Model: gpt-5.6-sol
- Calls:
  1. 研究结论综合与正文初稿
  2. Humanizer 审校，保留事实强度与两部分结构
- Output: copy.md
- Result: success
- Secrets logged: no

## 2026-08-03 Visual research

- Platform: 小红书 Web 搜索
- Query: 去AI味 写作
- Samples: 5
- Selected direction: 编辑中的文章
- Output: sources/visual-references.md, cards/plan.md

## 2026-08-03 Cover generation

- Endpoint role: NewAPI image generation
- Model: gpt-image-2
- Prompt constraints: portrait editorial manuscript; warm ivory paper; abstract unreadable gray text marks; restrained red editing annotations; no readable text, logo, product name, person, device or UI
- First request: rejected because the Codex image channel did not accept `output_format`; request was retried without that optional parameter
- Successful source image: 1086×1448 PNG, RGB
- Source handling: disposable local intermediate; no external or copyrighted visual asset imported
- Renderer: bundled Python + Pillow
- Final title font: `/System/Library/Fonts/Hiragino Sans GB.ttc`, W6
- Title overlay: deterministic four-line layout; `AI 味` in red; remaining title in charcoal
- Final output: cards/output/xhs-01-cover.png, 1080×1440 PNG
- Previews: cards/output/preview-mobile.png, cards/output/preview-grid.png

## 2026-08-03 Visual QA

- Manual inspection: original 1080×1440, 360×480 mobile preview, 600×800 overview preview
- AI review model: gpt-5.6-sol via NewAPI
- AI review result: title exact; mobile readable; no issues,乱码、Logo、裁切或遮挡
- Review response: `{"title_exact":true,"readable":true,"issues":[]}`
- Last updated at: 2026-08-03T08:09:53Z
