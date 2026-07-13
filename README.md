# 周络丹个人学术网站

本仓库是 Luodan Zhou（周络丹）的个人学术网站，通过 GitHub Pages 部署在
<https://yuanqili2027-creator.github.io/>。

> 本 README 主要写给未来维护本站的 Claude Code 会话（以及作者本人）。

## 仓库用途

一个极简的静态个人网站：主页 / 随笔（Essays）/ 项目（Projects）/ 简历（CV）。
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

## 待办 / 占位内容

- 主页头像目前是纯 CSS 占位块，日后替换为真实照片（记得加灰度滤镜）。
- CV 各栏目、项目第二条、页脚的 LinkedIn/X 链接均为占位内容，需替换。
- `assets/cv.pdf` 为占位 PDF，需替换为真实简历。
