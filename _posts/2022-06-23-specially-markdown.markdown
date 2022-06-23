---
title: 与众不同的 Markdown
layout: post
published: true
# header-img: "img/bg/pixiv_53864290.svg"
# header-img-object-position: 100% top
# date: '2022-06-21 20:42:50'
tags:
- Markdown
# description: 关于柏凛Porin的历史记录
file-name: 2022-06-22-specially-markdown.markdown
---

<!-- more -->

标记语言有许多种，最常用的是超文本标记语言 (HTML)，被几乎所有的网站使用，所以进入网络时代后，新诞生的标记语言或多或少都受到 HTML 的影响，比如 HTML 的标题有六级标题，分别是 H1 到 H6，所以大多标记语言也只有六级标题。

同理，带有文字的外部链接语法也是大同小异：

| 语言                   | 年代 | 语法                    |
| ---------------------- | ---- | ----------------------- |
| HTML:                  |      | `<a href=链接>文字</a>` |
| [AsciiDoc][]:          |      | `链接[文字]`            |
| BBCode:                |      | `[url=链接]文字[/url]`  |
| Org Mode：             |      | `[[链接][文字]]`        |
| [Wikitext][]:          |      | `[链接 文字]`           |
| Markdown:              |      | `[文字](链接)`          |
| reStructuredText:      |      | ```\`文字 <链接>`_```   |
| [MoinMoin's syntax][]: |      | `[[链接\|文字]]`        |

之后可能会持续更新这个表格。

[AsciiDoc]: https://docs.asciidoctor.org/asciidoc/latest/macros/url-macro/
[Wikitext]: https://en.wikipedia.org/wiki/Help:Wikitext
[MoinMoin's syntax]: https://moinmo.in/HelpOnMoinWikiSyntax

可以看出，大部分的标记语言都是链接在前，文字在后，但 Markdown 选择了相反顺序，这应该就是将可读性列为首位的目标，而进行的设计。

并且 Markdown 有另一种引用式的链接语法，并且可以在链接之后添加提示性文字（上面的语法也可以这样，使用 `[文字](链接 "提示")` 这样的语法就好）：

```markdown
[文字][ID]

[ID]: 链接 "提示"
```

这样让 Markdown 文本更具有可读性，如果有多个文字指向相同的链接，那么还能带来可维护性。

如果需要，还可以隐藏 ID：

```markdown
[文字][]

[文字]: 链接 "提示"
```

备注：以上 Markdown 语法来自原作者编写的最初规则 ——《[Markdown Syntax Documentation](https://daringfireball.net/projects/markdown/syntax)》，理应是最应该被支持的功能。
