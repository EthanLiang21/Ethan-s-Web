# Ethan 个人主页 · Ethan's Web

梁铭恩（Ethan）的个人主页与作品展示站，部署于 GitHub Pages。

🔗 **在线访问**：https://ethanliang21.github.io/Ethan-s-Web/

---

## 简介

这是一个**单文件静态个人网站**，把个人档案、经历、作品、兴趣与联系方式整合在一张带有太空 / 科技质感的页面里。视觉上以蓝紫粉渐变、玻璃拟态与双主题（明 / 暗）为基调，并融入英雄联盟 S12 Reconfiguration 风格的交互弹窗。整站零第三方库 / 框架依赖——所有 HTML、CSS、JavaScript 均原生编写，字体与图标全部内嵌，可离线打开。

## 主要内容

页面由顶部固定导航（首页 / 关于 / 经历 / 作品 / 联系）串联，包含以下板块：

- **Hero 首屏** — 「我是梁铭恩 aka：Ethan。」个人标识与简介。
- **关于我（ABOUT）** — 个人档案（生物技术本科、现于横琴济恩药业从事研发 QA），内联 B 站视频频道入口，以及兴趣卡片：
  - **AI & TOOLS**：DeepSeek、ChatGPT、Claude、WorkBuddy 四个官方 Logo 快捷入口。
  - **街头摄影**：iPhone 13 Pro、飓风相机 2.0 两个设备标签。
  - **独立游戏**：Hollow Knight。
  - **音乐偏好**：Synthwave / Lo-Fi / R&B / Rock / Jazz，含 QQ 音乐、Apple Music 歌单入口与 LO-FI 粉色磨砂粒子动效。
- **经历时间线（TIMELINE）** — 齐齐哈尔大学（2022–2026）、大创与「互联网+」校二等奖等。
- **精选作品（WORK）** — GMP 交互式全库项目（独立站点，单文件交互网页）。
- **联系（CONTACT）** — X、GitHub、LinkedIn、Instagram，以及 Gmail / 163 邮箱一键复制入口（点击复制并提示，不跳转）；另有 S12 Reconfiguration 风格的信息弹窗。

## 特性

- **单文件交付**：最终页面全部集中在 `index.html`，无需构建、无需联网即可运行。
- **双主题**：明 / 暗两套完整 CSS 变量，首次跟随系统 `prefers-color-scheme`，手动切换写入 `localStorage`；对比度符合 WCAG AA。
- **官方品牌图标**：各平台 Logo 取自官网 favicon，转为透明 PNG 后以 base64 内嵌，保留品牌原色。
- **零外部依赖**：无 CDN、无前端框架；标题字体 Orbitron、副标题字体 Rajdhani 均以 base64 内嵌。
- **响应式与无障碍**：适配桌面与移动端（≤960px 汉堡菜单、≤720px 单列）；含 `aria-label`、`prefers-reduced-motion` 支持。
- **交互细节**：滚动淡入、导航高亮、鼠标聚光、外链箭头等均原生实现。

## 技术栈

原生 HTML5 · CSS3（CSS 变量 / Flex / Grid / 动画）· JavaScript（ES6+）。无构建工具、无运行时依赖。

## 目录结构

| 文件 | 说明 |
| --- | --- |
| `index.html` | 站点首页（正式入口，实际部署文件） |
| `test.html` | 与 `index.html` 内容一致的副本 |
| `template.html` | 可维护源模板（字体使用 `/*__FONTS__*/` 占位符，注入后生成 `index.html`） |
| `source-package.zip` | 源码打包，含字体、官方图标与各版本说明 |
| `UPDATE-HISTORY.md` | 更新历史 / 版本记录（见下） |
| `README.md` | 本文件 |

## 版本说明

版本命名演进：`beta0.1`（初版）→ `0.1.1` ~ `0.1.4`（功能迭代）→ `beta0.5`（当前线上版本）。详细变更见 [UPDATE-HISTORY.md](UPDATE-HISTORY.md)。

## 部署

仓库已启用 GitHub Pages，来源为 `main` 分支根目录。推送 `index.html` 后 Pages 会自动构建发布；如需手动触发，可调用仓库的 Pages build API。

## 相关链接

- GMP 项目站点：https://ethanliang21.github.io/-GMP-beta0.1-/
- GitHub：https://github.com/EthanLiang21
