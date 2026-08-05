# Research

## Facts

1. 可把 AI UI 工作拆成视觉探索和代码实现两个阶段。来源依据是 Taste Skill README 对 image-generation skills 与 implementation skills 的职责区分。
2. 图片生成阶段产出的是视觉参考，不是可运行前端。README 明确称图片生成类 Skills 只输出 reference images。
3. 确认后的视觉参考可以交给 Codex、Cursor 或 Claude Code分析并实现。README 明确描述了这一交接方式。
4. Image-first 示例流程包含 generate images → analyze → code。来源见 README 的 Image-first tip。

## Quotes

无。最终正文不直接引用来源原句。

## Opinions

- “先解决页面长什么样，再解决怎样实现”是本帖对上述工作流的中文概括。
- 把设计与实现拆开，可以减少“高级一点”这类抽象描述带来的理解偏差。

## Inference

- 设计图可以成为需求方与编程 Agent 的共同视觉参照，但不保证像素级还原。
- 响应式、交互状态、真实内容长度和可访问性仍需在浏览器中验收，这些不能从单张静态图直接得到。

## Source map

| 内容点 | 类型 | 来源 |
| --- | --- | --- |
| 图片生成与代码实现分为两类能力 | 事实 | `sources/taste-skill-readme.md` |
| 先生成图片，再分析并写代码 | 事实 | Taste Skill README 的 Image-first tip |
| 图片是共同参照 | 推论 | 对 Image-first 工作流的解释 |
| 浏览器验收仍有必要 | 推论 | 静态设计图与可运行页面职责不同 |
| 封面版式 | 视觉研究 | `sources/visual-references.md` |
