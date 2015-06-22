title: GitHub Flavored Markdown 本地实时预览
date: 2015-06-23 02:44:06
tags:
  - GFM
  - Markdown
  - Hexo
category:
---

习惯用 [GFW](https://help.github.com/articles/github-flavored-markdown/) 写作之后，发现最大的障碍之一在于实时预览 orz

虽然说吧，Markdown 的设计思想之一便是可读性：

> "The idea is that a Markdown-formatted document should be publishable as-is, as plain text, without looking like it’s been marked up with tags or formatting instructions."

然而随着用 GFW 用得越来越多，便会发现有时 Markdown 并不完全是最终的发布格式。例如：

- GitHub 上的 `README.md` 将会在对应页面直接渲染，大多数人接触到的是 HTML
- Hexo 写博客时 `*.md` 文件最后都会被渲染成 HTML
- 用 GFW 写实验报告最后需要转成 pdf 交作业

这些情况下 Markdown 压根不是发布格式哇摔 Σ(っ °Д °;)っ

所以自然，总是会有一种想实时看到最终效果的愿望 ╮(╯▽╰)╭

<!-- more -->

至于解决方法嘛，大概有以下几个：

- 专门的 Markdown 编辑器，似乎有不少，没调查
- 编辑器的 Markdown 预览插件，如 Atom 的 [markdown-preview](https://atom.io/packages/markdown-preview)
- 在线 Markdown 编辑器，如 [StackEdit](https://stackedit.io)，GitHub 自带的
  Preview etc.

但是他们分别有一些缺点：

- 太臃肿，本来就是为了轻量
- 选择很少，效果不一定和 Github 渲染结果一样
- 不能/不能完全离线编辑，用本地图片之类的也很捉急

## 解决方案

好了废话不多说直接上搜寻结果

### [Github Markdown Preview](https://github.com/dmarcotte/github-markdown-preview)

能监测文件改动，实时渲染出 HTML

然而要让浏览器监测 HTML 改动并 reload 就是另一个故事了…

关键词：LivePage，LiveReload

（Safari 似乎由于 API 受限没有简单的解决方案 orz）

### [Grip](https://github.com/joeyespo/grip)

Python 实现，不过似乎因此离线功能仍在开发中（谁让 Github 用 Ruby →_→），没试

### [octodown](https://github.com/ianks/octodown)

最终选择，通过内嵌代码的形式，去掉了对浏览器插件的依赖。

于是在所有浏览器都能实时 reload，完美 ↖(￣▽￣")
