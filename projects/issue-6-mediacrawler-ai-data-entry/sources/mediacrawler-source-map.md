# MediaCrawler 来源记录

核验日期：2026-07-31（Asia/Taipei）

核验基线：MediaCrawler `main` 分支提交 [`1779dde9725f6b7ef42e29022c0054b3e678f1af`](https://github.com/NanmiCoder/MediaCrawler/commit/1779dde9725f6b7ef42e29022c0054b3e678f1af)。

## 1. 项目 README

- URL：https://github.com/NanmiCoder/MediaCrawler/blob/1779dde9725f6b7ef42e29022c0054b3e678f1af/README.md
- 用途：核对项目定位、覆盖平台、主要采集能力、Playwright 原理和开源版/Pro 版边界。
- 可支持的内容事实：
  - 开源版定位为多平台自媒体数据采集工具；
  - 覆盖小红书、抖音、快手、B 站、微博、贴吧、知乎；
  - README 功能表列出关键词搜索、指定内容、二级评论、指定创作者主页、登录态缓存等能力；
  - 基于 Playwright 浏览器自动化保存登录态；
  - “内容拆解 Agent”和“AI Agent Skill”位于 README 的 MediaCrawlerPro 介绍段落，不属于开源版核心能力。

## 2. 数据保存指南

- URL：https://github.com/NanmiCoder/MediaCrawler/blob/1779dde9725f6b7ef42e29022c0054b3e678f1af/docs/data_storage_guide.md
- 用途：核对数据输出格式。
- 可支持的内容事实：支持 CSV、JSON、JSONL、Excel、SQLite、MySQL、PostgreSQL；其中 JSONL 是指南写明的默认格式。

## 3. 基础配置

- URL：https://github.com/NanmiCoder/MediaCrawler/blob/1779dde9725f6b7ef42e29022c0054b3e678f1af/config/base_config.py
- 用途：交叉核对平台代号、采集类型和保存选项。
- 可支持的内容事实：
  - 平台配置包含 `xhs`、`dy`、`ks`、`bili`、`wb`、`tieba`、`zhihu`；
  - 采集类型包含 `search`、`detail`、`creator`；
  - 保存选项包含 CSV、JSON、JSONL、SQLite、Excel、PostgreSQL 等。

## 4. 许可证

- URL：https://github.com/NanmiCoder/MediaCrawler/blob/1779dde9725f6b7ef42e29022c0054b3e678f1af/LICENSE
- 用途：核对公开介绍必须保留的使用边界。
- 关键边界：`NON-COMMERCIAL LEARNING LICENSE 1.1`；软件限非商业学习与研究，不用于大规模采集、干扰平台运行或对第三方造成不当影响。

## 5. GitHub 项目页

- URL：https://github.com/NanmiCoder/MediaCrawler
- 用途：向读者提供项目入口。
- 备注：本篇不引用 Star、Fork 等易变化数字。
