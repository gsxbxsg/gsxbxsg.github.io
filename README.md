# 我的博客

基于 [Astro](https://astro.build) + [Firefly](https://github.com/CuteLeaf/Firefly) 主题的个人博客。
（2026-10-03 从 Hexo + Butterfly 迁移而来）

## 环境要求

- Node.js ≥ 22
- pnpm ≥ 11（`npm install -g pnpm`）

## 常用命令

| 命令 | 说明 |
| --- | --- |
| `pnpm install` | 安装依赖 |
| `pnpm dev` | 本地预览 → http://localhost:4321 |
| `pnpm build` | 构建静态站点到 `dist/` |
| `pnpm preview` | 预览构建产物 |
| `pnpm new-post -- <文件名>` | 新建文章（生成到 `src/content/posts/`） |

## 目录说明

```
src/
├── content/
│   ├── posts/      # 博客文章（Markdown / MDX）
│   └── spec/       # 特殊页面：about.md 关于页
├── config/         # 所有站点配置
│   ├── siteConfig.ts      # 站点标题、语言、页面开关、文章布局
│   ├── profileConfig.ts   # 头像、昵称、签名、社交链接
│   ├── navBarConfig.ts    # 导航栏
│   ├── sidebarConfig.ts   # 侧边栏组件
│   ├── commentConfig.ts   # 评论系统（默认关闭）
│   └── ...
public/             # 静态资源（favicon、图片等）
```

## 文章 Frontmatter

```yaml
---
title: 文章标题
published: 2026-10-03
updated: 2026-10-04        # 可选
description: 文章简介
tags: [标签1, 标签2]
category: 分类
slug: my-post              # URL 路径，可选
image: ./cover.jpg         # 封面图，可选
pinned: false              # 置顶
draft: false               # 草稿
---
```

## 部署

- **Vercel / Netlify / Cloudflare Pages**：直接导入仓库，框架预设选 Astro，构建命令 `pnpm run build`，输出目录 `dist`
- **GitHub Pages**：仓库已包含 `.github/workflows/deploy.yml`，推送到 `master` 分支自动部署（需在仓库 Settings → Pages 中将 Source 设为 GitHub Actions）

部署前请修改 `src/config/siteConfig.ts` 里的 `site_url` 为实际域名。

主题完整文档见 `FIREFLY-README.md` 或 https://docs-firefly.cuteleaf.cn
