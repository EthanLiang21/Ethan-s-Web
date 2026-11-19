# DEV.IO 个人主页 — 版本优化记录

仓库：`EthanLiang21/Ethan-s-Web`（原 `ioi.github.io`，已重命名）
站点：https://ethanliang21.github.io/Ethan-s-Web/

本站所有版本均为**单文件 HTML**，零第三方库/框架依赖，字体与图标全部内嵌。

---

## v6（当前线上版本）— 图标与邮箱交互修复

- **Instagram 图标修复**：此前渐变定义在通过 `<use>` 引用的隐藏 SVG 中，导致填充失效、图标不显示。改为**内联 SVG + 自带 `<defs>` 渐变**，`igGrad2` 与图形在同一 SVG 内，渐变相机稳定渲染（已用浏览器实测确认）。
- **Gmail 图标**：换用 Gmail 官方四色信封标志（蓝 / 绿 / 红 / 黄）替换原 Google "G" 标志。
- **163 邮箱图标**：换用网易邮箱官方红底信封 + "163" 字样标志。
- **邮箱交互改造**：两个邮箱入口由 `mailto:` 跳转改为**点击复制邮箱地址到剪贴板**：
  - 点击后显示「复制成功」Toast 提示（2.2 秒自动消失）；
  - 鼠标悬浮显示完整邮箱号（tooltip）；
  - `navigator.clipboard` 优先，失败自动降级到 `execCommand('copy')`；
  - 逐入口 `aria-label` 无障碍标注，复制按钮带短暂高亮反馈。
- 邮箱对应关系：GMAIL → `ethanming21@gmail.com`；163 邮箱 → `lme13825671390@163.com`。

## v5 — 真实社交链接与官方品牌图标

- Hero 文案改为「我是梁铭恩 aka：Ethan。」
- 经历时间线精简为单卡两行（齐齐哈尔大学 2022–2026；大创、互联网+ 均获校二等奖）。
- 联系区全部接入真实链接：X（x.com/Lme2261）、GitHub 主页、LinkedIn、Gmail、163 邮箱、Instagram；`RSS_FEED` 改为 Instagram。
- 引入各平台官方品牌 SVG 标志并保留品牌原色（X 随主题黑白、GitHub 随主题黑白、LinkedIn #0A66C2、Google 四色、网易红、Instagram 渐变）。

## v4 — 个人背景与作品扩充

- 个人简介更新：生物技术本科已毕业，现于横琴济恩药业从事研发 QA 工作（同步修正原「在读大学生」表述）。
- 新增「经历」板块：2022–2026 齐齐哈尔大学生物技术专业；大创与「互联网+」均获校二等奖。
- 作品区新增 GMP 交互式全库项目展示卡，链接至 https://ethanliang21.github.io/-GMP-beta0.1-/ 。
- GitHub 链接指向 https://github.com/EthanLiang21 。

## v3 — 导航、响应式与繁简统一

- 修复窄屏导航消失：≤960px 用汉堡按钮 + 下拉菜单，支持点击外部 / Esc 收起。
- 修复导航错跳与死链：导航项与真实锚点一一对应（首页/关于/经历/作品/联系），滚动自动高亮，锚点增加偏移避免被固定导航遮挡。
- 恢复中文名「梁铭恩」，与 Ethan 并列显示（页头、Hero、关于我、meta author）。
- 全页繁体统一为简体，`lang` 改为 `zh-CN`。
- 修复交互空转：404 图片降级显示，占位链接阻止跳转。

## v2 — 双主题与视觉升级

- 新增黑 / 白双主题切换：首次跟随系统 `prefers-color-scheme`，手动切换写入 `localStorage` 记忆；两套完整 CSS 变量覆盖文字/背景/边框/按钮/阴影/渐变，对比度经 WCAG 校验均 ≥ 4.5:1。
- 字体内嵌：标题 Orbitron（近似 Manuka Bold 几何粗体感）、副标题 Rajdhani（近似 Fraktion 窄体科技感），以 base64 内嵌，零外部请求。
- 融合 GMP 风格：明亮基底 + 蓝紫粉渐变光晕、白底卡片顶部渐变条、鼠标悬停聚光。
- 微信联系方式弹窗加入英雄联盟 S12 Reconfiguration 氛围：切角边框流光、扫描线、网格底纹、故障标题、加载环、状态面板。

## v1 — 初始化与改名

- 将 `ioi.github.io` 私有仓库启用 GitHub Pages，并把 HTML 设为首页（新增 `index.html` 作为入口）。
- 全站旧代号统一替换：`Tonny Liang` → `Ethan`（可见文案、标题、meta、alt 及相关标识）。
- 视觉改为深色太空质感：多层冷色渐变、噪点、星点微闪、玻璃拟态、光标光晕、跑马灯、滚动淡入；尊重 `prefers-reduced-motion`，触摸设备关闭光标特效。
- 移除原 Tailwind / Lucide / Google Fonts 三个 CDN 依赖，图标改为内联 SVG。

---

## 技术说明

- **单文件交付**：最终页面 `index.html`（`test.html` 保持同步）。
- **字体**：`orbitron.woff2`、`rajdhani.woff2`（base64 内嵌于 HTML，源码目录保留原始文件）。
- **模板**：`template.html` 为带 `/*__FONTS__*/` 占位符的可维护源模板；注入字体后生成最终 HTML。
- **无第三方库**：全部原生 HTML / CSS / JavaScript。
