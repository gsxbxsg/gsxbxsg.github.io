---
title: Hexo + Butterfly 快速上手
published: 2026-10-02
updated: 2026-10-03
description: 记录如何快速搭建一个 Hexo 博客并应用 Butterfly 主题。本站现已迁移至 Astro + Firefly，本文作为历史记录保留。
tags: [Hexo, Butterfly, 教程]
category: 技术
slug: hexo-butterfly-guide
---

本文记录如何快速搭建一个 Hexo 博客并应用 Butterfly 主题。

> [!NOTE]
> 本站已于 2026-10-03 从 Hexo + Butterfly 迁移到 **Astro + Firefly**。本文作为历史记录保留，内容仍适用于想使用 Hexo 的读者。

## 安装

```bash
npm install -g hexo-cli
hexo init blog && cd blog
npm install hexo-theme-butterfly hexo-renderer-pug hexo-renderer-stylus --save
```

## 启用主题

修改 `_config.yml`：

```yaml
theme: butterfly
```

并把 `node_modules/hexo-theme-butterfly/_config.yml` 复制为根目录的 `_config.butterfly.yml`，之后所有主题配置都在这个文件修改，升级主题不会丢失。

## 常用命令

| 命令 | 说明 |
| --- | --- |
| `hexo new "标题"` | 新建文章 |
| `hexo server` | 本地预览 |
| `hexo generate` | 生成静态文件 |
| `hexo clean` | 清理缓存 |
