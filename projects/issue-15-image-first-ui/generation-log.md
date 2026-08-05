# Generation Log

## 2026-08-05

- 内容生产由 Codex 完成，未调用下游文本模型。
- 视觉路线为用户确认的单张 split-flow 封面。
- 封面采用确定性 HTML/CSS，不调用图片模型。
- 同平台视觉研究记录在 `sources/visual-references.md`。
- 待记录：渲染命令、最终 PNG、预览图和视觉核验结果。

## 封面渲染

- Renderer: Google Chrome Headless（本机已安装）
- Source: `cards/html/xhs-01-cover.html`
- Command: `Google Chrome --headless=new --hide-scrollbars --disable-gpu --force-device-scale-factor=1 --window-size=1080,1440 --screenshot=... file://.../xhs-01-cover.html`
- Final: `cards/output/xhs-01-cover.png`，1080 × 1440
- Preview grid: `cards/output/preview-grid.png`，720 × 960
- Mobile preview: `cards/output/preview-mobile.png`，360 × 480
- Visual inspection: 原尺寸与手机预览均已检查；主标题、两步标签和方向箭头清晰，无文字裁切。
