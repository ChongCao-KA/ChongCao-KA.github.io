# Personal Homepage

这是一个浅蓝色、al-folio 风格的 GitHub Pages 个人主页模板，放在：

```text
/Users/chongcao/Documents/Codex/research/personal_homepage
```

## 本地预览

最简单的方式是直接双击打开 `index.html`。如果你希望模拟 GitHub Pages 的访问方式，可以在本目录运行：

```bash
python3 -m http.server 8000
```

然后访问：

```text
http://localhost:8000
```

## 发布到 GitHub Pages

1. 在 GitHub 新建一个仓库。个人主页仓库通常命名为 `你的GitHub用户名.github.io`。
2. 把本目录里的文件提交到该仓库。
3. 进入仓库的 `Settings` -> `Pages`。
4. Source 选择 `Deploy from a branch`，Branch 选择 `main` 和 `/root`。
5. 保存后等待 GitHub Pages 构建完成。

## 如何修改主页内容

主要编辑 `index.html`。

常用位置：

- 网页标题：修改 `<title>Your Name | Research Homepage</title>`。
- 顶部名字：修改 `<a class="brand" href="#top">Your Name</a>`。
- 首页大标题：修改 `<h1>Your Name</h1>`。
- 一句话简介：修改 `.subtitle` 这一段中文。
- 邮箱、GitHub、Google Scholar、CV：修改 `.link-row` 里的链接。
- 头像：替换 `assets/img/profile-placeholder.svg`，并保持文件名不变；或者修改 `index.html` 里的 `src`。
- 研究方向：修改 `Research Interests` 区域。
- 最新动态：修改 `News` 区域的 `<ol class="timeline">`。
- 论文：修改 `Selected Publications` 区域的 `.publication` 卡片。
- 项目：修改 `Projects` 区域，更多项目可放在 `projects/index.html`。
- 联系方式：修改页面底部 `Contact` 区域。

## 如何调节浅蓝色主题

颜色集中在 `assets/css/style.css` 顶部的 `:root` 变量里。

最常改的变量：

```css
--bg: #f7fbff;          /* 页面背景 */
--surface: #ffffff;     /* 卡片背景 */
--surface-blue: #eaf6ff;/* 浅蓝色块 */
--text: #1d2a36;        /* 正文颜色 */
--muted: #5d7186;       /* 次要文字 */
--line: #cfe4f5;        /* 分割线 */
--accent: #4da3ff;      /* 主蓝色 */
--accent-dark: #1976c9; /* 链接和强调色 */
--accent-soft: #d8efff; /* 柔和蓝色 */
```

如果你想让整体更淡，优先调浅 `--bg`、`--surface-blue` 和 `--accent-soft`。
如果你想让链接和按钮更明显，调深 `--accent-dark`。

## 如何新增论文

在 `index.html` 中找到：

```html
<div class="publication-list">
```

复制一个完整的：

```html
<article class="publication">
  ...
</article>
```

然后改年份、标题、作者、会议/期刊名称和链接即可。

## 如何新增项目

首页项目在 `index.html` 的：

```html
<div class="project-grid">
```

复制一个 `.project-card` 即可。项目归档页在 `projects/index.html`，可以用同样的方法添加更多项目。

## 建议保留的文件结构

```text
personal_homepage/
  index.html
  README.md
  .nojekyll
  assets/
    css/
      style.css
    img/
      profile-placeholder.svg
  projects/
    index.html
```

`.nojekyll` 可以让 GitHub Pages 按普通静态网页发布，不经过 Jekyll 处理。
