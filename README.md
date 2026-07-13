# 周络丹个人学术网站

本仓库是 Luodan Zhou（周络丹）的个人学术网站，通过 GitHub Pages 部署在
<https://yuanqili2027-creator.github.io/>。

> 本 README 主要写给未来维护本站的 Claude Code 会话（以及作者本人）。

## 仓库用途

一个极简的静态个人网站：主页 / 随笔（Essays）/ 项目（Projects）/ 简历（CV）/
演示文稿（Slides）。
不使用任何框架或构建工具——只有纯手写的 HTML 和一份共享的 CSS。推送到 `main`
分支后，GitHub Pages 会在约 1 分钟内自动重新部署。

## 目录结构

```
index.html                            主页 / 关于
essays/index.html                     随笔列表（按年份分组）
essays/2026/on-reading-history.html    英文示例随笔，同时是新文章的模板
essays/2026/guanyu-jiyi.html           中文示例随笔
projects/index.html                   项目列表
cv/index.html                         简历
slides/index.html                     演示文稿列表（deck 本体在独立仓库）
assets/style.css                      唯一的共享样式表
assets/cv.pdf                         简历 PDF（占位文件）
docs/DESIGN.md                        设计规范
```

## 设计规则（务必遵守）

- **严格单色（monochrome）**：背景 `#fafafa`、正文 `#111`、次要文字 `#666`、
  分隔线 `#e5e5e5`。**任何地方都不得使用彩色。**
- **不用框架**：不引入 CSS/JS 框架、不加构建步骤。所有样式集中在
  `assets/style.css`。
- 字体：正文用系统无衬线字体栈；日期与编号用等宽字体栈（`"SF Mono", Menlo,
  monospace`），字号小、带字距。
- 布局：内容列最大宽度约 680px 居中，留白充足，用发丝线分隔各区块。
- 所有界面文字（导航、标题、页脚、标签）使用英文。
- 详细规范见 `docs/DESIGN.md`。

## 发布新随笔的约定流程

1. 复制模板：把 `essays/2026/on-reading-history.html` 复制为
   `essays/YYYY/slug.html`（`YYYY` 为年份，`slug` 为英文短标题）。
2. 填写内容：修改 `<title>`、`.article-title`、`.article-date` 和正文
   `.article-body`。中文文章给 `.article-body` 加上 `cjk` class。
3. 在 `essays/index.html` 中新增一行（放在对应年份下，最新的在最上面）。
4. 更新主页 `index.html` 的「Recent Essays」列表。
5. 提交并推送到 `main`：

   ```bash
   git add -A
   git commit -m "Add essay: <title>"
   git push
   ```

6. 等待约 1 分钟，GitHub Pages 会自动重新部署。

## 发布新 slides 的约定流程

每个 deck 是一个**独立仓库**（Slidev 项目，构建产物发布到该仓库自己的 GitHub
Pages），本站只负责在 `slides/index.html` 里维护列表。参考实现见
[slides-african-history](https://github.com/yuanqili2027-creator/slides-african-history)
（其 CLAUDE.md 记录了 Slidev 的构建命令、CSS 规则与排版纪律）。

1. 新建 deck 仓库 `slides-<topic>`，按参考实现搭建并部署。
2. 在本站 `slides/index.html` 的 `.row-list` 中新增一行，链接指向
   `https://yuanqili2027-creator.github.io/slides-<topic>/`。
3. 提交并推送本站。注意：deck 本身可以有配色（不受本站单色规则约束），
   但本站的列表页仍严格单色。

## 待办 / 占位内容

- 主页头像目前是纯 CSS 占位块，日后替换为真实照片（记得加灰度滤镜）。
- CV 各栏目、项目第二条、页脚的 LinkedIn/X 链接均为占位内容，需替换。
- `assets/cv.pdf` 为占位 PDF，需替换为真实简历。
