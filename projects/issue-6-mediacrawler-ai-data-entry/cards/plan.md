# 四卡视觉计划

## 交付数量

最终只交付以下 4 张卡片：

1. `cards/output/xhs-01-cover.png`
2. `cards/output/xhs-02-capabilities.png`
3. `cards/output/xhs-03-ai-workflow.png`
4. `cards/output/xhs-04-boundaries.png`

## 统一规格与视觉

- 尺寸：`1080×1440`
- 比例：3:4
- 格式：PNG
- 安全边距：四周至少 64 px
- 生成方式：本地 HTML/CSS 确定性排版后截图
- 参考 [“自媒体人都在用的爬虫神器”](https://www.xiaohongshu.com/explore/694eed8c000000002203a8f0) 的横线笔记本结构；
- 四张统一使用暖黄色外框、白色横线纸、左侧装订孔、黑色粗体和粉色荧光笔强调；
- 弱化 GitHub：不使用大号 `GitHub` 字样与章鱼图形，`MediaCrawler` 始终是项目识别主体；
- 所有平台只使用文字名称，不使用 Logo；
- 不放 GitHub Star、作者头像、仓库截图或未经许可的外部图片。

## 卡片 1：封面

- 核心信息：这是一个能为 AI 工作流提供真实平台资料的开源采集项目。
- 眉题：`开源工具介绍`
- 第一视觉中心：`MediaCrawler`
- Hook：`给 AI 一个 / 真实数据入口`
- 轻量说明：`先收集公开内容与评论，再交给 AI 做研究和分析`
- 三个能力标签：`7 个平台`、`公开内容`、`结构化保存`
- 页码：`01 / 04`

## 卡片 2：项目能力

- 核心信息：MediaCrawler 能从七个平台收集哪些公开资料。
- 标题：`它到底能收集什么？`
- 平台：小红书、抖音、快手、B站、微博、贴吧、知乎；
- 三组能力：
  - `搜`：关键词内容；
  - `看`：指定内容、创作者主页；
  - `收`：评论、二级评论。
- 保存格式：JSON、Excel、SQLite / 数据库
- 页码：`02 / 04`

## 卡片 3：AI 工作流

- 核心信息：采集与 AI 分析是前后相接的两个阶段。
- 标题：`它和 AI，怎么配合？`
- 示例主题：`普通用户最不懂 AI 绘图的什么？`
- 四步链路：
  1. 确定主题与关键词；
  2. MediaCrawler 收集公开内容与评论；
  3. 保存原始数据并保留出处；
  4. AI 归纳高频问题、争议观点和选题线索。
- 结论：`不是让 AI 替你下结论，而是先给它可回看的材料。`
- 页码：`03 / 04`

## 卡片 4：能力边界

- 核心信息：介绍工具时必须分清开源版、Pro 版和使用边界。
- 标题：`先分清这 3 件事`
- 三点：
  1. 开源版核心是数据采集，不是内置 AI Agent；
  2. README 提到的内容拆解 Agent、AI Agent Skill 属于 MediaCrawlerPro；
  3. 项目限非商业学习与研究，遵守平台规则，不做大规模采集。
- 强调：`采集 ≠ 分析；AI 总结 ≠ 事实结论`
- 项目入口：`github.com/NanmiCoder/MediaCrawler`
- 页码：`04 / 04`

## 证据映射

- 七个平台、采集能力：MediaCrawler README、`config/base_config.py`；
- 数据格式：数据保存指南；
- AI 工作流：基于已核实能力形成的方法示例，不声称已经实测固定效果；
- 开源版/Pro 版边界：README 的 MediaCrawlerPro 段落；
- 非商业学习边界：LICENSE。

事实来源见 `../sources/mediacrawler-source-map.md`；视觉参考见 `../sources/visual-reference.md`。

## QA 重点

- 四张图片文件名、数量、尺寸和计划一致；
- 每张只表达一个核心意思，手机缩略图下标题仍清楚；
- 七个平台名称无遗漏、无错字；
- AI 工作流顺序一眼可读；
- 不让读者误以为 MediaCrawler 开源版内置 AI；
- 底部页码、边界文字不贴边、不裁切；
- `cards/output/` 中最终只有四张 PNG。
