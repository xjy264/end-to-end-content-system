# Card Plan

| Page | Role | Core message | Evidence/asset | Layout |
| --- | --- | --- | --- | --- |
| 01 | 单图教程 | 一张 C 罗成品图对应一套可理解、可替换的提示词结构 | 用户选定的 `gpt-image-2` 候选图；`copy.md` 最终提示词 | 1080 × 1440；顶部短标题；左侧一张 9:16 成品图；右侧完整核心提示词与 5 个结构标签；底部 AI 生成标识 |

## Candidate gate

1. 使用相同模型和尺寸分别生成 A、B、C 三个方向。
2. 记录每次生成的提示词、模型、输出、优点、缺点与失败原因。
3. 实际视觉检查后向用户展示 3 个候选。
4. 用户确认一个方向后，再锁定最终标题、右栏文案与成图。

## Candidate previews

- A: `work/candidates/cards/candidate-a.png`，1080 × 1440，已视觉检查。
- B: `work/candidates/cards/candidate-b.png`，1080 × 1440，已视觉检查。
- C: `work/candidates/cards/candidate-c.png`，1080 × 1440，已视觉检查；原图含品牌勾形标识，未通过边界检查。

## Readability constraints

- 最终只出现一张 AI 成品图，不做多图拼贴。
- 提示词正文不使用小于 28 px 的字号；结构标签不使用小于 24 px 的字号。
- 右栏只保留能解释结果的核心指令，不以极小字号塞入全部生成参数。
- 图片主体、脸部与关键动作不得被左栏裁切。

## Final card

- Asset: `cards/output/xhs-01-cover.png`
- Selected direction: 用户提供模板填入 C 罗主题后的叙事剪影。
- Title: 把提示词填成一张 C 罗海报
- Layout: 左侧只放一张 `gpt-image-2` 成品图；右侧按主题、外轮廓、内部世界、叙事关系、视觉融合、材质色彩和排除项讲解。
- Full prompt: 保存在 `copy.md` 正文；卡片保留可读的模板填空内容，不用极小字号塞入长提示词。
