# End-to-End Content System

由 Codex 驱动的中文图文内容生产仓库。它把一个模糊想法推进为清晰的 GitHub 内容 Issue，再把 Issue 生产为一套完整的小红书图文内容包。

## 当前范围

首版聚焦：

```text
想法讨论 → 内容 Issue → 研究 → 文案 → 去 AI 味 → 3:4 图文卡片 → QA → 人工发布
```

当前不建设 Web 应用、CLI、数据库或平台自动发布。Codex 是核心 Agent；外部文本、图片和视频模型统一通过 NewAPI 调用。

## 快速开始

1. 复制本地配置：`cp .env.example .env`。
2. 在 `.env` 填入 `NEW_API_KEY`；默认模型已经固定为 `gpt-5.6-sol`、`gpt-image-2` 和 `doubao-seedance-2-0-260128`。
3. 从仓库根目录开启 Codex。
4. 和 Codex 讨论一个想法，确认后让它创建内容 Issue。
5. 说“把 #<issue-number> 做成完整的小红书图文”，或调用 `$xhs-content-pipeline #<issue-number>`。

完整协作规则见 [AGENTS.md](./AGENTS.md)。

## 内容包

每个 Issue 的产物位于：

```text
projects/issue-<number>-<slug>/
```

内容包包含需求、研究、最终文案、卡片规划、HTML 源文件、成品图、预览图、生成日志和 QA 记录。所有正式结果通过内容 Issue 的任务分支和 GitHub PR 交付；仓库外目录只用于临时生成与验证。平台发布由用户人工完成。
