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

Markdown 有许多跟其他标记语言不同的特征，此文会围绕这些特征进行描述与讨论。

<!-- more -->

## CommonMark

最早的 Markdown 语法解析器，是 John Gruber 与 Aaron Swartz 创造的 `Markdown.pl` ，但此解析器存在歧义，并且开发者 John Gruber 不再更新，而 Aaron Swartz 早已辞世，也就导致了其他人制作的 Markdown 解析器各不相同。

2012年，一群 Markdown 爱好者开始制作具有共识的规范，原理是使用目前流行的解析器测试，将之前存在歧义，疏漏的情况进行填补，不过还是以原始的 `Markdown.pl` 为准，所以像是脚注这样的扩展语法不会收录进此项目中，最后此规范被命名为了 [CommonMark][] 。

[CommonMark]: https://commonmark.org

不过 CommonMark 规范只是指导意见，熟悉此规范可能只会减少遇到一些奇怪的解析问题的可能性，具体情况还是需要阅读该平台的 Markdown 指南，如果是开源软件，应该也能找到具体解析器的相关说明。

如果阅读 CommonMark 的内容太枯燥，也可以在 VS Code 等常见编辑器中安装 [markdownlint][] 插件，从而快速检查可能有问题的部分。（不过可能会看到大量错误，如果不得不这么做，比如一些扩展语法被当作错误，就需要到设置了关闭不需要的规则）

[markdownlint]: https://github.com/DavidAnson/markdownlint

## Markdown 撰写文章常见问题

### 标题

Markdown 在 HTML 中使用时，最好只有一个 \<H1> 标题标签，即一个 # 标题，这是 [HTML 的标准规范][html_moz]。如果 YAML 头文件含有 title 元素，那么不建议在正文中再次使用 \<H1> 标题，因为 \<H1> 往往表示该页面的标题。也需要注意避免跳过某级标题。

[html_moz]: https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Heading_Elements

### 换行

古典的 Markdown 使用严格换行，即只按下一次回车，Markdown 解析器是会自动忽略掉这个回车。如果想要文章不分段的换行，那么需要使用 \<br> 表前或者输入两次空格后再按下回车。Visual Studio Code 可以在设置中搜索 renderWhitespace 选项，来显示尾部的空白字符。

现在一些简单入门的 Markdown 工具可能为了方便，会默认设置禁止严格换行，比如 Obsidian 这款笔记软件和 Github。

### 空格

只要不是左右包括住里面的内容的 Markdown 语法，比如标题和列表，都需要在标记与文字间留下空格，否则解析可能不成功，或者其他的解析器会遇到问题。比如：

| 名称     | 语法          |
| -------- | ------------- |
| 标题     | `# 标题`      |
| 无序列表 | `+ 无序列表`  |
| 有序列表 | `1. 有序列表` |
| 块状引用 | `> 块状引用`  |

### 缩进

Markdown 的列表缩进，是靠空格缩进的，比如下面的标记所示：

```markdown
1. 有序列表1
2. 有序列表2
3. 有序列表3
   1. 有序列表3.1
   2. 有序列表3.2
      1. 有序列表3.2.1
   3. 有序列表3.3
4. 有序列表4
```

但是如果涉及复杂的缩进，情况就比较复杂了，比如编写了一个超过 100 编号的有序列表，并且列表里还有多行内容，这里就是一个可能出错的地方，因为大多数简单教程没有提及空格缩进的原理。我们先来看看错误的 Markdown 书写吧：

```markdown
98. 前略

    这里没问题

99. 这里没问题

    测试内容测试内容测试内容

100. 这里有问题

    测试内容测试内容测试内容
```

渲染出来的效果：

![100-list](img/specially-markdown/100-list.webp)

这是一个超过 100 编号的有序列表，[^49302511][^49278202]并且每个列表都含有额外的多行内容。简单的来说，`99. 第九十九条` 这段 Markdown 内容的「正文」部分的前面空了 4 个空位，而它下面同样是 4 个空格，所以是正常的。但 `100. 这里有问题` 的「正文」部分的前面有 5 个空位，而它下面只有 4 个空格，造成了解析错误。

[^49302511]: Waylan, 《[Answer to 「Markdown enumerated list with indices over 99 changes nested list formatting」](https://stackoverflow.com/a/49302511)》, Stack Overflow, 2018-03-15. (参照 2022-06-25).

[^49278202]: James Elderfield, 《[Markdown enumerated list with indices over 99 changes nested list formatting](https://stackoverflow.com/q/49278202)》, Stack Overflow, 2018-03-14. (参照 2022-06-25).

解决方式就是同步空位，将 100 以及之后的多行内容都要修改为 5 个空位才行，需要形成「对齐」的效果。

## 前置的链接文字

标记语言有许多种，最常用的是超文本标记语言 (HTML)，被几乎所有的网站使用，所以进入网络时代后，新诞生的标记语言或多或少都受到 HTML 的影响，比如 HTML 的标题有六级标题，分别是 H1 到 H6，所以大多标记语言也只有六级标题。

同理，带有文字的外部链接语法也是大同小异：

| 语言                  | 年代       | 语法                    |
| --------------------- | ---------- | ----------------------- |
| HTML                  | 1993       | `<a href=链接>文字</a>` |
| BBCode                | 1998       | `[url=链接]文字[/url]`  |
| reStructuredText      | 2002-04-02 | ```\`文字 <链接>`_```   |
| [AsciiDoc][]          | 2002-11-25 | `链接[文字]`            |
| [Wikitext][]          | 2002       | `[链接 文字]`           |
| Org Mode              | 2003       | `[[链接][文字]]`        |
| Markdown              | 2004-03-19 | `[文字](链接)`          |
| [MoinMoin's syntax][] | 2007       | `[[链接\|文字]]`        |

之后可能会持续更新这个表格。

[AsciiDoc]: https://docs.asciidoctor.org/asciidoc/latest/macros/url-macro/
[Wikitext]: https://en.wikipedia.org/wiki/Help:Wikitext
[MoinMoin's syntax]: https://moinmo.in/HelpOnMoinWikiSyntax

可以看出，大部分的标记语言都是链接在前，文字在后，但 Markdown 选择了相反顺序，这应该就是将可读性列为首位的目标，而进行的设计。

并且 Markdown 有另一种引用式的链接语法，并且可以在链接之后添加提示性文字（上面的语法也可以这样，使用 `[文字](链接 "提示")` 这样的语法就好）：

```text
[文字][ID]

[ID]: 链接 "提示"
```

这样让 Markdown 文本更具有可读性，如果有多个文字指向相同的链接，那么还能带来可维护性。如果需要，还可以像下面那样隐藏 ID：

```text
[文字][]

[文字]: 链接 "提示"
```

备注：以上 Markdown 语法来自原作者编写的最初规则 ——《[Markdown Syntax Documentation][]》，理应是最应该被支持的功能。

[Markdown Syntax Documentation]: https://daringfireball.net/projects/markdown/syntax

## 扩展语法

之前提到了 [CommonMark](#CommonMark) 这个 Markdown 的规范指导，但 CommonMark 仅包含原始的 Markdown 语法，脚注和表格这样常见基本的扩展语法，均没有在里面提到。不过好在脚注和表格出现的早，所以在各种 Markdown 解析器中基本没有差异，但在 Markdown 解析器越来越多的现在，想要创建一个广泛被其他解析器接受的扩展语法，就很难了。

虽然没有规范指导，但有一定共识的语法列表是存在的，Markdown Guide 编写了《[Extended Syntax][]》这篇指南，将最流行的 Markdown 扩展语法记录了下来。

[Extended Syntax]: https://www.markdownguide.org/extended-syntax/

## 各式各样的 Admonitions

AsciiDoc 的 [Admonitions][ad_a]（告诫）是创建一个高亮的框体，这个功能也被一些 Markdown 解析器添加为扩展语法，但每个的实现都不相同。

[ad_a]: https://docs.asciidoctor.org/asciidoc/latest/blocks/admonitions/

+   Python-Markdown 内置的标准扩展

    +   被命名为 Admonitions，[^pm]被 Mkdocs 使用，语法是：

        [^pm]:  《[Admonition](https://python-markdown.github.io/extensions/admonition/)》, Python-Markdown 3.3.7 documentation. (参照 2022-06-25).

        ```text
        !!! 关键字 "标题"

            内容。
        ```

+   Microsoft Docs

    +   被命名为 Alerts，[^mdr]语法是：

        [^mdr]:  meganbradley, 《[Markdown reference](https://docs.microsoft.com/en-us/contribute/markdown-reference)》, Microsoft Docs Contributor Guide, 2022-03-30. (参照 2022-06-14).

        Obsidian 也使用了相同的语法，但名称为 Callouts。[^o_c]

        [^o_c]:  《[Use callouts](https://help.obsidian.md/How+to/Use+callouts)》, Obsidian Help. (参照 2022-06-25).

        ```text
        > [!关键字] 标题
        >
        > 内容。
        ```

+   Github

    +   暂时未命名，还在公开测试中，目前有 Note 和 Warning 这两个选项，[^gc]语法是：

        [^gc]:  dipree, 《[[Markdown] An option to highlight a 「Note」 and 「Warning」 using blockquote (Beta) · Discussion #16925 · github-community](https://github.com/orgs/github-community/discussions/16925)》, GitHub, 2022-05-19. (参照 2022-06-25).

        ```text
        > **关键字**
        > 内容。
        ```

+   Wiki.js

    +   属于块状引用 (Blockquotes) 的扩展语法，所以应该算作是块引用的主题，[^wj]语法是：

        [^wj]:  《[Markdown User Guide](https://docs.requarks.io/en/editors/markdown)》, Wiki.js. (参照 2022-06-25).

        ```text
        > 内容。
        {.is-关键字}
        ```

+   Markdown-it

    +   Markdown-it 没有直接附带此功能，不过开发者 docarys 制作了插件 [markdown-it-admonition][]，语法是：

        [markdown-it-admonition]: https://github.com/docarys/markdown-it-admonition

        ```text
        !!! 关键字 标题
        内容。
        !!!
        ```

+   Remarkable

    +   [Remarkable][] 是 Markdown 编辑器，有 Linux 与 Windows 版本。

        原版没有这个功能，但开发者 elviswolcott 制作了 [remark-admonitions][] 插件，为它添加了相应的支持，随后 [Docusaurus][] 将此插件添加进了语法中，同样命名为 [Admonitions][ds]，语法是：

        [Remarkable]: https://remarkableapp.github.io
        [remark-admonitions]: https://github.com/elviswolcott/remark-admonitions
        [Docusaurus]: https://docusaurus.io
        [ds]: https://docusaurus.io/docs/markdown-features/admonitions

        ```text
        :::关键字 标题
        内容。
        :::
        ```

## gledos 的习惯

1.  使用 `+` 符号作为无序列表的标记
2.  缩进使用 4 个空位，比如：
    +   `+   无序列表`
    +   `1.  有序列表`

    这样写，列表 9 与 10 之间就不会出现增加空位的情况，就像下面这样：

    ```markdown
    9.  有序列表
    10. 有序列表
    ```

3.  块状引用使用 2 个空位缩进：

    ```markdown
    > 块状引用
    >
    > > 块状引用的缩进。
    > >
    > > 4 个空位又稍微有点大了，并且不兼容许多扩展语法，所以使用了 2 个空位缩进。
    ```

4.  使用严格换行

    因为这对于很长的内容来说比较方便编辑（严格换行可以把长句截成多行的短句，尤其是里面有链接的时候，不过可以使用引用式的链接，防止文字杂乱），空行也能缓解我的阅读障碍。

---

## 脚注
