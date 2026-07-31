# Card Plan

| Page | Role | Core message | Evidence/asset | Layout |
| --- | --- | --- | --- | --- |
| 01 | AI 生图示例 | 直接展示 C 罗史诗叙事海报的生成结果 | 用户锁定模板后由 `gpt-image-2` 生成的最终原图 | 1080 × 1440；整页只放 AI 成品图；不叠加标题、提示词、教程或装饰排版 |

## Candidate gate

1. 使用相同模型和尺寸分别生成 A、B、C 三个方向。
2. 记录每次生成的提示词、模型、输出、优点、缺点与失败原因。
3. 实际视觉检查后向用户展示候选。
4. 用户提供剪影叙事模板并锁定 A 类方向后，重新生成最终图。

## Candidate previews

- A: `work/candidates/cards/candidate-a.png`，早期“图片 + 教学栏”预览，仅保留为试验记录。
- B: `work/candidates/cards/candidate-b.png`，早期预览，仅保留为试验记录。
- C: `work/candidates/cards/candidate-c.png`，早期预览含品牌勾形标识，未进入最终方向。

## Final image

- Asset: `cards/output/xhs-01-cover.png`
- Selected direction: 用户提供模板填入 C 罗主题后的叙事剪影。
- Content: 只有 `gpt-image-2` 生成的 C 罗侧脸剪影及内部足球叙事世界。
- Adaptation: 从模型返回的 1024 × 1536 原图裁去少量顶部和底部留白，再缩放为 1080 × 1440；人物头部、面部与内部关键场景均完整保留。
- Text separation: 完整提示词与教学只进入 `copy.md`，不进入图片像素。
