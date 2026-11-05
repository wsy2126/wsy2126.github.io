# wsy2126.github.io

我的个人主页。**https://wsy2126.github.io/**

一个手写的静态单页，没有框架、没有构建、没有依赖。clone 下来双击 `index.html` 就能看，推到 `main` 就自动上线（GitHub Pages 从 `/ (root)` 发布）。

**状态：完成，不再计划新增功能。**

---

## 文件

- `index.html` — 整站全部内容：结构、样式、脚本、图标，都在这一个文件里
- `LICENSE` — MIT
- `README.md` — 本文件

没有 CSS/JS 外链、没有图片资源、没有分享卡片、没有自定义 404。单页够用，分文件反而多几次请求和几个路径要操心。等真出现第二个页面（比如文章详情页）再说分离的事。

---

## 改哪里

都在 `index.html`，搜关键词就能定位：

- **文案**：直接改正文中文，Hero 副标题在 `<div class="hero">` 里
- **配色**：`<style>` 开头的 `:root`（深色）和 `:root[data-theme="light"]`（浅色）两组 CSS 变量，主色是 `--accent`
- **上线日期**：脚本里的 `var START = new Date(2026, 10, 1)`，月份从 0 算，11 月写 `10`
- **QQ 号**：两处，`data-qq="1452459792"` 和卡片里显示的数字，要一起改
- **GitHub 链接**：两处，联系方式卡片和页脚
- **加图标**：body 开头 `<svg class="sprite">` 里加一个 `<symbol id="i-名字" viewBox="0 0 24 24">`，用的时候 `<svg class="ico"><use href="#i-名字"/></svg>`。全站统一 24×24 / 只描边 / 1.7px / 圆角端点
- **导航条目**：`<nav class="nav-links">` 里的 `#about` `#notes` `#contact` 对应各区块的 `id`

改完 Commit，等一两分钟刷新。手机上直接编辑也行：打开文件 → 铅笔 → 粘贴 → Commit。

---

## 几个刻意的选择

- **图标不用 emoji**：各系统长得不一样、还自带颜色。改成内联 SVG sprite，零请求，深浅主题自动跟随
- **入场淡入只播一次**：触发后 `unobserve`，播完把 `reveal` 类摘掉。来回滚动不重播，hover 也不受影响
- **hover 效果限定 `@media(hover:hover)`**：手机点完不会残留橙框
- **不加 OG 分享卡片**：国内平台基本不抓，实测没作用，删了
- **不写自定义 404**：Pages 自带的够用

---

## 关于

页面代码、样式与文案整理由 AI 协助生成，我负责提需求、逐轮审校和修改。代码完全开放，随意取用。

MIT License，见 [`LICENSE`](./LICENSE)。

*Built with GitHub Pages · 2026*
