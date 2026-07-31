# Content projects

每个准备生产的内容 Issue 使用 `projects/issue-<number>-<slug>/` 独立目录。复制 `templates/post-package/` 的结构后，再按 `.agents/skills/xhs-content-pipeline/references/output-contract.md` 填充。正式内容包必须被 Git 跟踪，并通过对应任务分支和 GitHub PR 交付。

未经对应 Issue 明确约定，私人来源放在 `sources/private/`，运行中间文件放在 `work/`；这两个位置已被 Git 忽略，也不属于正式内容交付。
