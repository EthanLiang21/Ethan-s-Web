# Ethan 个人主页 · Ethan's Web

🔗 **在线访问**：https://ethanliang21.github.io/Ethan-s-Web/

---

## 简介

这是一个**单文件静态个人网站**，把个人档案、经历、作品、兴趣与联系方式整合在一张带有太空 / 科技质感的页面里。视觉上以蓝紫粉渐变、玻璃拟态与双主题（明 / 暗）为基调，整站零第三方库 / 框架依赖——所有 HTML、CSS、JavaScript 均原生编写，字体与图标全部内嵌，可离线打开。

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
| `index.html` | **正式展示版**（线上首页，即 `Ethan-s-Web/` 实际部署文件） |
| `test.html` | **更改测试版**（所有改动先在此进行，验收通过后才同步到正式版） |
| `template.html` | 可维护源模板（字体使用 `/*__FONTS__*/` 占位符，注入后生成页面） |
| `source-package.zip` | 源码打包，含字体、官方图标与各版本说明 |
| `UPDATE-HISTORY.md` | 更新历史 / 版本记录（见下） |
| `README.md` | 本文件 |

## 更新流程

1. **先改测试版**：所有页面改动先在 `test.html` 上进行，不直接改动正式版 `index.html`。
2. **验收后同步**：确认满意后，把测试版同步覆盖到 `index.html`，并推送上线。
3. **记录变更**：正式发布后，将本版相对上一版的更新内容补充到 `UPDATE-HISTORY.md` 对应版本条目。

