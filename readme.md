## 项目结构
```
.
├── hugo.toml                 # 网站配置文件
├── content/
│   ├── _index.md            # 首页内容（About）
│   └── publications/
│       └── _index.md        # Publications 页面
├── static/
│   └── images/
│       └── Hongbo.JPG       # 头像图片
├── assets/
│   └── css/
│       └── extended/
│           └── custom.css   # 自定义样式
├── layouts/
│   └── index.html           # 首页模板
├── themes/
│   └── PaperMod/            # 主题（git submodule）
└── docs/                     # 构建输出目录（用于 GitHub Pages）
```

## 修改内容

### 修改首页（About）

编辑 `content/_index.md`

### 修改 Publications

编辑 `content/publications/_index.md`

### 修改网站标题、菜单、社交链接

编辑 `hugo.toml`

### 修改样式（字号、布局等）

编辑 `assets/css/extended/custom.css`

## 本地预览
```bash
hugo server
```

然后打开 http://localhost:1313/

## 构建与部署

### 1. 构建网站
```bash
hugo
```

生成的文件在 `docs/` 目录下。

### 2. 推送到 GitHub
```bash
git add .
git commit -m "Update site"
git push
```

### 3. GitHub Pages 设置

- 进入仓库 → Settings → Pages
- Source: Deploy from a branch
- Branch: `master`，文件夹: `/docs`

## 配置说明

### hugo.toml 关键配置
```toml
baseURL = "https://hongbobo.github.io/"   # 网站地址
title = "Hongbo Bo"                        # 网站标题
theme = "PaperMod"                         # 主题
publishDir = "docs"                        # 输出目录

[markup.goldmark.renderer]
unsafe = true                              # 允许 Markdown 中使用 HTML
```

### 添加新页面

1. 在 `content/` 下创建文件夹，如 `content/cv/`
2. 在里面创建 `_index.md`
3. 在 `hugo.toml` 的 `[[menu.main]]` 里添加菜单项

### 常用命令

| 命令 | 用途 |
|------|------|
| `hugo server` | 本地预览 |
| `hugo` | 构建网站 |
| `git add . && git commit -m "msg" && git push` | 推送更新 |

## 注意事项

- 修改内容后需要重新运行 `hugo` 构建
- Markdown 中使用 HTML 需要在 `hugo.toml` 里设置 `unsafe = true`
- 每行末尾加两个空格或用 `<br>` 才能换行