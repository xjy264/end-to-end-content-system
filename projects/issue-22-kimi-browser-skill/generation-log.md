# 生成记录

## 2026-10-09

- 用户已确认候选 1、2、4、7、9 及五篇正文。
- 用户明确要求只使用 2026-08-01 及之后的帖子，不复现，只做二创。
- 根据用户 pi Agent 参考帖实际封面，选择深暖灰／米白／红色的大字单列路线。
- 原始网页加载图片为 750×1000；正式排版尺寸为 1080×1440。
- 封面由 HTML/CSS 原创排版，不复制第三方图像、标识或装饰。
- 未调用下游模型，没有付费生成。
- 渲染器：本机 Google Chrome Headless；使用独立临时 user-data-dir，不读取用户浏览器登录资料。
- 实际渲染参数：--headless=new --disable-gpu --hide-scrollbars --force-device-scale-factor=1 --window-size=1080,1440 --virtual-time-budget=2000；--screenshot 指向 cards/output/xhs-01-cover.png，输入 cards/html/xhs-01-cover.html 的 file URL。
- 预览：系统 sips -Z 480 与 -Z 960 从封面生成。
- 尺寸回读：封面 1080×1440、手机 360×480、概览 720×960。
- 实际查看封面及手机图：标题层级、Kimi 红色强调、副文案与工具全称清晰；无文字裁切和遮挡。
- 字体：本机 PingFang SC／Hiragino Sans GB，HTML 中声明回退字体；在其他操作系统重渲染需核对字体与换行。
- 当前封面为待用户确认样稿，不据此自动批准后续四张。
- 平台草稿保存：待首张封面确认后执行。

- 布局核对：body 使用相对定位固定页脚参考画布，普通窗口预览与截图尺寸一致；各文字区块无重叠。

## 样稿交付

- 内容提交：1f6eb02f48ea57ab475f8a83c8397bcbb7a85ca1，已推送 origin/codex/22-kimi-browser-skill。
- Draft PR：https://github.com/xjy264/end-to-end-content-system/pull/27。
- 当前等待首张封面确认；同批次其余四篇已建立 Issue #23、#24、#25、#26，正文与交付结构已记录，尚未制作封面。
- 本次不把源帖中的教程当作复现任务，不上传平台。
