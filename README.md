# 郝仁昱 · 作品集（网页版）

一个纯静态单页站点：`index.html` + `assets/`，无构建、无依赖、无外链，双击即可打开。

## 本地预览

直接双击 `index.html`。若想用本地服务器（避免个别浏览器对 `file://` 的限制）：

```bash
cd portfolio-site
python -m http.server 8000
# 打开 http://localhost:8000
```

## 部署到 GitHub Pages

方式一：用户主页（推荐，地址最好记）

1. 在 GitHub 新建仓库，名字必须是 `haohaohao-cell.github.io`
2. 把本目录下的 `index.html` 和 `assets/` 推到 `main` 分支
3. 一两分钟后访问 `https://haohaohao-cell.github.io`

方式二：项目页

1. 新建任意仓库（例如 `portfolio`），推上去
2. Settings → Pages → Source 选 `main` / `root`
3. 访问 `https://haohaohao-cell.github.io/portfolio/`

命令行（方式二）：

```bash
cd portfolio-site
git init && git add -A && git commit -m "portfolio site"
git branch -M main
git remote add origin https://github.com/haohaohao-cell/portfolio.git
git push -u origin main
```

## 结构

```
portfolio-site/
├── index.html      # 全部样式与脚本都在这一个文件里
└── assets/         # 10 张截图，WebP，合计约 350 KB
```

## 改内容时的位置

- 文案：`index.html` 里每个 `<section class="project">` 的 `<h2>` / `<p class="p-sub">` / `<div class="notes">`
- 图片：`assets/*.webp`，替换同名文件即可，宽高属性记得同步改
- 配色：`:root` 里的 `--bg` / `--ink` / `--line` 三个变量

## 已验证

- 桌面 1440 宽与 500 宽下布局正常（媒体查询断点 860px）
- 图片懒加载，总大小 387 KB
- 支持 `prefers-reduced-motion`；打印时自动展开所有动效元素
- 点击截图可放大查看，Esc 关闭
