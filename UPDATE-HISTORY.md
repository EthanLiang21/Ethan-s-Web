# Ethan 个人主页 — 更新历史（Update History）

站点：https://ethanliang21.github.io/Ethan-s-Web/

---

## beta0.5（当前线上版本）— 图标、邮箱交互与音乐氛围以及页面调整

- **Instagram 图标修复**：此前渐变定义在通过 `<use>` 引用的隐藏 SVG 中，导致填充失效、图标不显示。改为**内联 SVG + 自带 `<defs>` 渐变**，`igGrad2` 与图形在同一 SVG 内，渐变相机稳定渲染（已用浏览器实测确认）。
- **Gmail 图标改用官方资源**：直接内嵌 Gmail 官方红色 M 信封图标（gstatic 官方 favicon，PNG base64），替换此前手绘版本。
- **163 邮箱图标改用官方资源**：直接内嵌网易邮箱官方红色 "e" 标志，替换此前的红底信封自绘版。
- **QQ 音乐图标改用官方资源**：内嵌 QQ 音乐官方黄色圆底 + 绿色音符标志。
- **音乐库入口接入真实链接**：Apple Music → 喜爱歌曲歌单；QQ 音乐 → 官方歌单页（链接由用户提供）。
- **新增 B 站展示入口**：位于「关于我」个人简介下方，视觉与 Apple Music 模块一致（渐变顶边卡片 + 官方蓝电视图标 + 按钮）。
- **关于我区块精简（同源迭代）**：B 站由独立大模块改为个人档案框内的紧凑内联链接，保留官方蓝电视图标与真实链接。
- **B 站风格小卡片布局**：`AI & TOOLS` 卡片内改为 4 个可点击小卡片，各带官方风格 Logo与官网链接，悬浮聚光。
- **设备小卡片归入街头摄影并缩小**：iPhone 13 Pro 与飓风相机 2.0 两张小卡片收进「街头摄影」卡片内部（`.card-gear` + `.gear-mini`），不再是 bento 中独立的 gear-row 大模块；随后按用户反馈改为 flex-wrap 紧凑标签（padding 7px 11px、圆角 9px、图标 20px、字号 .8rem/10px），尺寸与「B 站 · 视频频道」入口接近，不再撑满整行。
- **LOGO 修正**：WorkBuddy 由手绘紫色盾牌改为**官方绿色渐变 Logo*；iPhone 13 Pro 用**苹果官方黑色剪影 Logo**（随主题 currentColor）；飓风相机 2.0 用**影视飓风官方光圈 Logo**。
- **音乐氛围**：删除 `SYNTHWAVE` 标签；`LO-FI` 标签改粉色磨砂玻璃质感 + 缓慢飘移的粒子点与扫光动画，字体色阶与其他标签区分；`prefers-reduced-motion` 下关闭动画。
- **页脚品牌名**：由 `DEV.IO` 改为 `Ethan Liang`。
- **官方图标实现方式**：从各平台官网抓取 favicon，ICO 正确解码为透明 PNG（处理 40 字节 DIB 头偏移与自下而上行序），以 base64 data URI 内嵌进 SVG symbol，保持单文件零外部依赖。
- **音乐板块氛围融合**：Synthwave / Lo-Fi 卡片加入 R&B / RNB、Rock、Jazz 视觉元素与文案（律动 / 失真音墙 / 即兴呼吸），新增 R&B·ROCK·JAZZ·SYNTHWAVE·LO-FI 类型标签、动态均衡器与黑胶装饰；QQ 音乐与 Apple Music 入口已接入真实链接（见上），Apple Music 图标为主题自适应黑白双音符。
- **邮箱交互改造**：两个邮箱入口由 `mailto:` 跳转改为**点击复制邮箱地址到剪贴板**：
  - 点击后显示「复制成功」Toast 提示（2.2 秒自动消失）；
  - 鼠标悬浮显示完整邮箱号（tooltip）；
  - `navigator.clipboard` 优先，失败自动降级到 `execCommand('copy')`；
  - 逐入口 `aria-label` 无障碍标注，复制按钮带短暂高亮反馈。

## beta0.1.4 — 真实社交链接与官方品牌图标

- 经历时间线精简为单卡两行。
- 联系区全部接入真实链接：X、GitHub 主页、LinkedIn、Gmail、163 邮箱、Instagram；。
- 引入各平台官方品牌 SVG 标志并保留品牌原色。

## beta0.1.3 — 个人背景与作品扩充

- 略

## beta0.1.2 — 导航、响应式与繁简统一

- 修复窄屏导航消失：≤960px 用汉堡按钮 + 下拉菜单，支持点击外部 / Esc 收起。
- 修复导航错跳与死链：导航项与真实锚点一一对应（首页/关于/经历/作品/联系），滚动自动高亮，锚点增加偏移避免被固定导航遮挡。
- 恢复中文名「梁铭恩」，与 Ethan 并列显示。
- 全页繁体统一为简体，`lang` 改为 `zh-CN`。
- 修复交互空转：404 图片降级显示，占位链接阻止跳转。

## beta0.1.1 — 双主题与视觉升级

- 新增黑 / 白双主题切换：首次跟随系统 `prefers-color-scheme`，手动切换写入 `localStorage` 记忆；两套完整 CSS 变量覆盖文字/背景/边框/按钮/阴影/渐变，对比度经 WCAG 校验均 ≥ 4.5:1。
- 字体内嵌：标题 Orbitron（近似 Manuka Bold 几何粗体感）、副标题 Rajdhani（近似 Fraktion 窄体科技感），以 base64 内嵌，零外部请求。
- 融合 GMP 风格：明亮基底 + 蓝紫粉渐变光晕、白底卡片顶部渐变条、鼠标悬停聚光。
- 微信联系方式弹窗加入英雄联盟 S12 Reconfiguration 氛围：切角边框流光、扫描线、网格底纹、故障标题、加载环、状态面板。

## beta0.1 — 初始化与改名

- 将 `ioi.github.io` 私有仓库启用 GitHub Pages，并把 HTML 设为首页（新增 `index.html` 作为入口）。
- 视觉改为深色太空质感：多层冷色渐变、噪点、星点微闪、玻璃拟态、光标光晕、跑马灯、滚动淡入；尊重 `prefers-reduced-motion`，触摸设备关闭光标特效。
- 移除原 Tailwind / Lucide / Google Fonts 三个 CDN 依赖，图标改为内联 SVG。

---

## 技术说明

- **单文件交付**：最终页面 `index.html`（`test.html` 保持同步）。
- **字体**：`orbitron.woff2`、`rajdhani.woff2`（base64 内嵌于 HTML，源码目录保留原始文件）。
- **无第三方库**：全部原生 HTML / CSS / JavaScript。
