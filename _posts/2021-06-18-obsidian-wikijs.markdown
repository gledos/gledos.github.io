---
title: 使用 Obsidian 编辑 Wiki.js
layout: post
published: true
# date: '2021-06-18 00:00:00'
tags:
    - 软件
header-img: "img/bg/sync_wikijs_github_obsidian.svg"
header-img-object-position: 0% 50%
description: Obsidian 是一款很好用的本地个人笔记本，不过默认设置不适配编辑 Wiki.js 的源文件。需要进行一些手动的设置。
# file-name: 2021-06-18-obsidian-wikijs.markdown
---

[Obsidian](https://obsidian.md/) 是一款很好用的本地个人笔记本，不过默认设置不适配编辑 [Wiki.js](https://js.wiki/) 的源文件。需要进行一些手动的设置。

<!-- more -->

首先简述一下这两款软件

## Obsidian

[Obsidian](https://obsidian.md/) 是知识库笔记本，特点是维基化、{% include furigana.html text="非线性" furigana="Non-Linear" class="default" %}、Markdown 写作、本地化、社区插件。如果用一个词语来形容 Obsidian 的设计与功能，我想，最贴切的应该是{% include furigana.html text="极客" furigana="Geek" class="default" %}。

## Wiki.js

[Wiki.js](https://js.wiki/) 是基于 Node.js 的维基网站软件，特点与 Obsidian 很相似，许多功能都足够的模块化，还能够同步含有 YAML 元数据的 Markdown 到各种储存环境，如 Git。同样十分的极客。

## 设置 Wiki.js 存储

我使用的是这样的连接:

```text
Wiki.js <---> Github <---> Obsidian
         [1]          [2]
```

均是双向自动同步，只有本地的 Obsidian 需要手动使用 Git 进行同步。

[1] 需要在 Wiki.js 网站中设置，进入模块下的存储管理区，就能设置 SFTP, Amazon S3, Azure Blob Storage, Git 等同步仓库。含有版本控制且易于操作的 Git 当然是一个优秀的选项，于是我使用了 Github 提供的仓库，需要在 wiki.js 与 GitHub 中填入 SSH 密钥与公钥，[^st_git]并设置同步方向为双向。

[^st_git]: [Git - Wiki.js](https://docs.requarks.io/storage/git)

[2] 仓库的根目录创建一个 `.gitignore` 文件，将 `.obsidian` 文件夹排除，这样就不会使 Obsidian 自带的版本控制文件上传到 Git，使仓库结构过于复杂。

## 设置 Obsidian

主要是修改选项里的「文件与链接」，需要将「使用 Wiki 链接」这个选项关闭。其他的设置根据自己的喜好来设置。如果想让编辑模式的字体全部大小相同，可以使用我修改自 [habdenscrimen/obsidian.css](https://gist.github.com/habdenscrimen/be1bb1539ddac6dba71e6067e118b2cf) 的 CSS 代码段——[gledos/obsidian.css](https://gist.github.com/gledos/953d4fa4ec278bb9603dfd837ee47146)，如果要修改字体大小，只需将 15px 更换成适合自己的字体大小。

如果无法连接 GitHub Gits 获取 CSS 代码段，可以访问 GitHub Pages 里的 [obsidian.css](text/obsidian/obsidian.css) 文件。

然后需要模板，因为 Wiki.js 不认识没有 YAML 元数据的 Markdown 文件，使用模板能大大缩短新建条目的时间，将下面的代码块保存到仓库里，比如 `templates/templates.md` 根目录下的 templates 文件夹里的 templates.md 文件，然后使用 Obsidian 自带的核心插件「日记」或「模板」进行新建模板。

{% raw %}

```text
---
title: 
description: 
published: true
date: {{date:YYYY-MM-DD}}T{{time:HH:mm:ss.SSS}}Z
tags: 
editor: markdown
dateCreated: {{date:YYYY-MM-DD}}T{{time:HH:mm:ss.SSS}}Z
---

## 

```

{% endraw %}

### 日记

启动这个核心插件，并将插件选项里的日记配置为:

| 设置描述           | 参数                |
| ------------------ | ------------------- |
| 新建日记的存放位置 | templates           |
| 日记模板位置       | templates/templates |

注意: 日记模板位置不需要对文件加 .md 扩展名

然后 Obsidian 界面的最左边多了一个日历形状的标志，点击后就能在 `templates` 文件夹中生成一个含有大部分框架的包含 YAML 元数据的 Markdown 文件。然后手动修改文件名、标题、简介与标签就完成了 YAML 元数据。

### 模板

启动这个核心插件，并将插件选项里的模板配置为:

| 设置描述       | 参数      |
| -------------- | --------- |
| 模板文件夹位置 | templates |

然后 Obsidian 界面的最左边多了一个复制形状的标志，点击就会在当前行插入模板，其他操作与「日记」相同，可能会比「日记」功能繁琐一点。

## Obsidian 其他的一些设置

### 字体选择

在「第三方插件」选项中安装名为「[Minimal Theme Settings](https://github.com/kepano/obsidian-minimal-settings)」的插件，启用后在该插件的设置最下方分别自定义预览、编辑器与等宽字体的字体。

### SOCKS5 代理

因为 Obsidian 是 electron 的软件，所以在启动参数中增加 `--proxy-server=socks5://127.0.0.1:1080` 这样的参数，就能够进行代理。
