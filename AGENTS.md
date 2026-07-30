# Repository Guidelines

> 本文件是 End-to-End Content System 的项目协作与 Codex 工作流权威源。
> 优先级：用户当前明确指令 > 本文件 > Skill 默认行为。

## 项目定位

本项目通过 Codex 驱动中文图文内容生产。首要目标是把一个好想法讨论清楚，形成结构化 GitHub 内容 Issue，再生成可直接交付的小红书图文帖子。

一套完整帖子至少包含：选题与受众、可追溯研究资料、标题与正文、标签建议、卡片规划、完整卡片图片和发布前 QA。

当前阶段不建设内容管理平台，不以 Web 为核心，也不接入小红书、抖音等平台的一键发布。Web 页面以后只作为预览或成果展示层。

## Codex 协作方式

- 默认使用中文沟通、写文档、创建 Issue 和 PR。
- Codex 是核心 Agent，负责需求访谈、Issue 结构化、流程编排、状态管理和验收。
- Codex 主动补全执行方案和合理默认值，只在账号定位、内容边界、首次视觉路线、代表性样稿、远程发布或付费操作等关键决策点确认。
- 用户想法尚不完整时，先整理已有信息，提出推荐方向并继续讨论。只有当目标、受众、核心观点、素材条件和验收标准足够清楚时，才创建内容 Issue。
- 已确认的定位、语气、视觉规范和禁区应沉淀到项目文件，后续批次直接复用。
- 修改本文件前，先展示完整草案或精确 diff，说明影响范围，得到用户明确确认后再写入。

## 从想法到内容 Issue

一个好想法默认对应一个内容 Issue；一个内容 Issue 默认对应一篇完整图文帖子。批量生产通过多个 Issue 编号组合，不把多个不相关想法塞进同一个 Issue。

创建内容 Issue 前，与用户讨论并锁定：

- 原始想法与创作动机；
- 目标受众及其真实问题；
- 核心观点、内容承诺和期望反应；
- 已有素材、个人经历和来源；
- 待研究、待核实及禁止编造的部分；
- 语气、表达边界和视觉偏好；
- 标题、正文、卡片和 QA 验收标准。

内容 Issue 状态按 `need discussion → ready for production → in production → ready for review` 流转。用户确认 Issue 清晰后，才进入图文生产。

## 标准内容流水线

1. **需求访谈**：明确定位、受众、目标、主题范围、产量和素材条件。
2. **选题诊断**：检查价值、传播空间、Hook 和可用素材。
3. **资料研究**：收集来源，区分事实、引用、观点和推测。
4. **结构与初稿**：完成内容结构、标题候选、正文和标签建议。
5. **小红书适配**：压缩信息，每张卡片只表达一个核心意思。
6. **中文去 AI 味**：清理空话、套话、机械排比和模板化表达，保留作者观点。
7. **视觉生产**：生成封面和正文卡片，默认采用小红书 3:4 规格。
8. **质量检查**：检查事实、文案、视觉、尺寸、可读性和文件完整性。
9. **内容包交付**：状态标记为 `ready`，等待用户人工发布。

研究、去 AI 味和最终 QA 都是主链路门禁。当前流程到内容包交付结束，不执行平台发布。

## 内容项目目录

每篇内容使用独立目录：

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

- `brief.md`：目标、受众、主题、语气、禁区和已确认假设。
- `manifest.md`：Issue、当前阶段、状态、失败原因和交付路径。
- `sources/`：资料摘录、来源链接和素材来源记录。
- `research.md`：证据、观点、争议和引用关系。
- `copy.md`：最终标题、正文、标签建议和可选版本。
- `cards/plan.md`：封面 Hook、每页核心信息、视觉证据和版式。
- `cards/output/`：最终卡片图片。
- `qa.md`：事实、文案、视觉和文件完整性检查结果。

不得混用不同 Issue 的中间材料。失败项保留原因，不用空白文件伪装完成。

## 项目级总控 Skill

总控入口是 `.agents/skills/xhs-content-pipeline/SKILL.md`。

用户表达“生成一批小红书图文”“把这些素材做成帖子”“继续这个内容 Issue”“把 #12 做成完整图文”等意图时，应使用该 Skill。它负责读取 Issue、选择能力、维护内容包、控制确认点、调用 NewAPI 和执行最终 QA。

首版采用 instruction-only Skill，不新增独立 CLI、服务端或数据库。

## NewAPI 模型边界

Codex 是顶层 Agent。Codex 发起的下游文本、视觉理解、图片和视频模型调用统一经过 NewAPI，不直接对接具体厂商 API。

本地 `.env` 使用：

```dotenv
NEW_API_URL=https://llmapi.lovbrowser.com/v1
NEW_API_KEY=<machine-local-secret>
AI_TEXT_MODEL=gpt-5.6-sol
AI_IMAGE_MODEL=gpt-image-2
AI_VIDEO_MODEL=doubao-seedance-2-0-260128
```

- `gpt-5.6-sol`：研究、写作、润色和视觉验收。
- `gpt-image-2`：封面、插图和必要视觉素材。
- `doubao-seedance-2-0-260128`：预留动态卡片或视频扩展；静态图文默认链路不调用。
- 真实 Key 只写本地 `.env`；公开仓库仅提交 Key 为空的 `.env.example`。
- 调用前检查 `.env` 和 `/models`。配置缺失或模型不可见时，在 `manifest.md` 记录阻塞点并停止对应生成阶段。
- NotebookLM 只保留为研究工作流参考；实际模型生成统一走 NewAPI。

## 参考 Skill 与仓库

以下仓库是能力来源和工作流参考。初版只记录链接、职责和路由，不复制代码、不使用 Git submodule，也不假定本机已经安装。

1. **Humanizer-zh** — https://github.com/op7418/Humanizer-zh
   中文去 AI 味与终稿润色；负责表达质量，不负责事实研究。
2. **dbskill** — https://github.com/dontbesilent2025/dbskill
   商业表达、选题、Hook、传播判断和小红书标题诊断。
3. **content-research-writer** — https://github.com/openakita/openakita/tree/main/skills/content-research-writer
   通用研究、提纲、初稿、引用和逐段反馈流程。
4. **notebooklm-skill** — https://github.com/claude-world/notebooklm-skill
   作为资料库研究方法参考；NewAPI-only 首版不进入实际模型调用链。
5. **khazix-skills** — https://github.com/KKKKhazix/khazix-skills
   深度研究、热点分析和长文方法；作为观点素材来源，不直接套用个人文风。
6. **ian-xiaohei-illustrations** — https://github.com/helloianneo/ian-xiaohei-illustrations
   把观点、流程和隐喻转成手绘正文插图，再适配到小红书卡片。
7. **guizang-social-card-skill** — https://github.com/op7418/guizang-social-card-skill
   小红书 3:4 图文卡片的主要排版与交付能力。
8. **baoyu-skills** — https://github.com/JimLiu/baoyu-skills
   小红书图片、封面、信息图和插图工具箱，作为补充视觉路线。
9. **guizang-ppt-skill** — https://github.com/op7418/guizang-ppt-skill
   PPT、演讲和横向展示，属于后续二次分发能力。
10. **html-anything** — https://github.com/clockless-org/html-anything
    HTML 预览或展示页能力，不作为图片生成主链路。

默认路由：`dbskill → 研究/写作 → Humanizer-zh → guizang-social-card-skill → QA`。其他能力按内容需要启用，不强行使用全部十个 Skill。

使用上游能力前确认当前版本、实际入口、本机可用性、模型后端和许可证。不要把上游代码、模板或大段说明直接复制到本公开仓库。

## 批量生产规则

- 多篇批次仍保持一 Issue 一帖子、独立研究、文案、卡片和 QA。
- 首次生产或视觉路线变化时，先完成一篇代表性帖子和封面样稿，用户确认后再批量展开。
- 已确认的定位和视觉规范后续复用，不重复确认。
- 单篇失败不抹掉其他成功结果；在 manifest 中标记 `partial` 并记录原因。
- 不为了凑数量编造选题、数据、案例、引用或个人经历。
- QA 阶段检查同质标题、重复 Hook 和机械复用模板。

## 内容与视觉验收

### 事实与来源

- 关键事实有来源，事实、引用、观点和推测已区分。
- 当前产品、政策、价格和新闻已核实。
- 图片和外部素材保留来源记录。
- 不编造数据、案例、体验和个人经历。

### 文案

- 标题默认不超过 20 个中文字符，超出时记录理由。
- 标题、封面和正文承诺一致。
- 开头能独立建立话题和阅读理由。
- 正文没有明显空话、机械排比和模板化 AI 表达。
- 一篇内容保留一个主要结论，标签不堆砌无关热词。

### 卡片

- 默认输出 `1080 × 1440`、3:4，包含封面和必要正文页。
- 每页只表达一个核心意思，移动端文字可读，无溢出和错误裁切。
- 同一帖子保持统一视觉系统。
- 最终图片经过实际视觉检查，不以接口返回成功代替验收。

### 内容包

- 必需文件齐全，manifest 状态与真实结果一致。
- 卡片数量与计划对应，引用和素材可追溯。
- QA 记录检查结果及遗留问题。

## GitHub Issue 与 PR 流程

### Issue First

- 所有准备纳入版本库的系统、规范、模板、Skill 或内容改动，开始前创建或确认 GitHub Issue。
- Issue 写清背景、目标、边界和验收标准；同一 PR 的增量修改和 Review 修复复用原 Issue。
- 纯讨论、只读研究或不准备提交的本地试验可跳过；准备入库前先补 Issue。
- 新建 Issue 默认指派当前 GitHub 登录账号；标题、正文和评论使用中文。

### Label 规范

每个 Issue 必须且只能有一个优先级标签：

- `:broom: p1-chore`
- `:cake: p2-nice-to-have`
- `:hammer: p3-minor-bug`
- `:exclamation: p4-important`
- `:fire: p5-urgent`

类型标签至少一个：`:sparkles: feature request`、`:lady_beetle: bug`、`need documentation`、`research`、`content batch`。

范围标签按需选择：`scope: research`、`scope: content`、`scope: visual`、`scope: pipeline`、`scope: docs`、`scope: infra`。

状态标签按实际状态使用：`need discussion`、`need more info`、`ready for production`、`in production`、`ready for review`、`ready to merge`、`wait changes`、`🛑 on hold`。

### Worktree First

- 默认分支为 `main`。任务分支基于最新 `origin/main`，命名为 `codex/<issue-number>-<slug>`。
- 版本库改动默认在独立 Git worktree 执行，不直接在主工作区修改。
- 初次建仓和治理文件是一次性 bootstrap 特例；初始提交后不再直接推送 `main`。
- 文档微调仍需要 Issue，但可在当前任务分支完成，不强制额外 worktree。

### Commit 与 PR

- 改动完成后运行范围对应的验证，再提交、推送任务分支并创建目标为 `main` 的 PR。
- PR 使用中文，包含摘要、影响范围、验证方式和结果，并以 `Closes #<issue-number>` 关联 Issue。
- 每次实现、补充修改或 Review 后，在同一 PR 留言记录改动和验证结果。
- Agent 交付边界止于创建或更新 PR；不合并 PR、不开启自动合并、不绕过 Review、不直接推送远程 `main`。

## 开发与架构约束

- 首版采用文档、模板和项目级 Skill，不提前引入 Web、CLI、数据库、队列或工作流框架。
- 新增运行时代码、第三方依赖或界面前，先建立 Issue 并说明现有 Codex 工作流的不足。
- 优先使用 Markdown、目录协议和现有 Codex 能力，不为未来假设提前搭建抽象层。
- Web 如有需要只做预览、筛选和成果展示，生产核心仍由 Codex 总控 Skill 驱动。
- 自动发布属于独立阶段，当前不配置平台凭据。

## 测试与验证

纯文档和 Skill 改动至少执行：

```bash
git diff --check
test -f AGENTS.md
test -f .agents/skills/xhs-content-pipeline/SKILL.md
```

同时人工检查：十个链接完整、Skill 触发条件清楚、目录协议与模板一致、Issue 表单和 Label 规范一致、上游代码未被复制、敏感信息未进入公开仓库。

加入可执行代码后，根据真实技术栈补充测试命令，不预先写不存在的命令。

## 环境变量、素材与敏感信息

- 密钥、Token、Cookie、登录状态和平台凭据不得入库。
- 公开仓库不提交未获许可的私人资料、客户素材或账号数据。
- 本地中间文件和大体积生成产物是否入库，由对应 Issue 明确。
- 日志、Issue、PR 和回复中的敏感信息必须脱敏。
- 外部图片、资料和模板保留来源 URL，涉及转载或商业使用时由用户确认授权范围。

## 发布边界

- 当前只交付内容包，不上传小红书、抖音或其他平台。
- 平台发布、定时发布、账号矩阵和数据回收需要独立设计、独立 Issue 和用户明确确认。
