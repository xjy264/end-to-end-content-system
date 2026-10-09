# Manifest

- Issue：https://github.com/xjy264/end-to-end-content-system/issues/24
- 分支：codex/24-ai-task-playbook
- 状态：reviewing（新版图像和草稿回读通过，正在推送远程）。
- 阶段：第二版封面完成；原有Chrome草稿已替换并重新打开回读。
- PR：https://github.com/xjy264/end-to-end-content-system/pull/29（目标main；未合并）。
- 远程内容提交：944676c7dbb4a5ca2413a32e73fad75372938f39，包含完整文案、HTML、正式图片与预览；本次后续提交补充草稿回读与交付记录。
- 仓库状态：原14个必需文件已跟踪并推送，PR存在；本次新增draft-readback.json并随交付记录一并推送。
- 交付：1张1080×1440封面＋完整配文；用户要求直接批量生成，不等待封面审批。
- 平台状态：已保存并从草稿列表重新打开；标题、正文逐字一致；1张图片1080×1440，解码像素与本地原图差异为0；未发布。
- 草稿范围：本次替换前后均为5篇；更新原草稿，无新增、无删除、无重复。
- 模型调用：无下游文本、图片、视频模型调用；Codex二创，HTML/CSS经Chrome渲染；无付费生图。
- 方法复现：按用户要求未做，不把方法建议写成已验证效果。
- 手机同步：未验证，不承诺。
- 最后核验：2026-10-09T12:18:00.980950（Asia/Shanghai）。
- 失败项：无。
- 下一步：用户可直接在本机Chrome草稿箱调整内容；本任务不执行发布。

## 文件入口

- 文案：copy.md
- 封面：cards/output/xhs-01-cover.png
- HTML：cards/html/xhs-01-cover.html
- 来源：sources/references.md
- QA：qa.md
- 实际回读：draft-readback.json

## 第二版封面

- 参考与要素提取：sources/cover-redesign.md。
- 布局检查：cards/layout-qa.json。
- 正文原文件SHA256：4dce98eeab35bb74a1fcb9f9e273687ecf4a1ab51a02ad7f978a63047a37ca7d，本次未变。
- 本次回读：2026-10-09T12:55:31.723854。
