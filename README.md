# 布文的个人博客

个人学术主页与博客仓库，用于展示个人介绍、科研项目、学习笔记、保研经验和阶段性总结。

## 网站入口

- 个人主页：[https://blog.buwen.homes/](https://blog.buwen.homes/)
- 仓库地址：[https://github.com/buwenjiayou/buwenjiayou.github.io](https://github.com/buwenjiayou/buwenjiayou.github.io)

## 内容维护

博客采用“自定义首页 + Markdown 发文”的方式维护：

- 首页：`docs/index.html`
- 文章源文件：`posts/*.md`
- 文章模板：`posts/_template.md`
- 静态资源：`docs/assets/`
- 生成脚本：`scripts/build_posts.py`

新增文章时，复制 `posts/_template.md`，新建一个不以下划线开头的 Markdown 文件，例如：

```text
posts/research-note-001.md
```

文章开头保留 front matter：

```markdown
---
title: 文章标题
date: 2026-07-03
slug: research-note-001
tags: 科研, 学习
description: 一句话摘要。
pdf: ../assets/pdf/example.pdf
---
```

其中 `pdf` 为可选字段。若填写，文章页会自动显示 PDF 下载按钮。

## 部署

推送到 `main` 分支后，GitHub Actions 会自动运行：

```bash
python scripts/build_posts.py
```

然后发布 `docs/` 目录到 GitHub Pages。

本地预览生成：

```bash
python scripts/build_posts.py
```

生成后打开 `docs/index.html` 查看效果。
