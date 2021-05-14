---
title: 常见 CLI 软件 SOCKS5 代理方式全解
layout: post
published: false
# header-img: "img/bg/pixiv_53864290.svg"
# header-img-object-position: 100% top
# date: '2021-05-02 00:00:00'
tags:
    - 指南
description: git, ruby, ffmpeg 等常见 CLI 软件代理方式全解
file-name: 2021-05-16-all-about-software-proxy.markdown
---

施工中

<!-- more -->

通常 CLI({% include furigana.html text="命令行,界面" furigana="Command-line,interface" class="default" type="B" %}) 软件
没有明显的 SOCKS5 代理设置，需要手动查阅软件的使用手册，不过可能 SOCKS5 代理功能在一些软件中不属于常用功能，
所以手册中也不一定会提到代理设置的方法。

下面出现的 SOCKS5 端口默认 1080，http 为 2080，https 与 SOCKS4 代理少见，所以就不在正文里提了。

如果没有特殊说明，通常下面提到的方法都是全平台(Windows, Linux, macOS)支持的。

## home 文件夹

因为习惯原因 `~/` 文件夹指 *nix 系统中的 $HOME 文件夹，[^Tilde_Expansion]软件的设置常会保存在这个地方。
引申到 Windows 下指 %USERPROFILE%("%HOMEDRIVE%%HOMEPATH%") 这个地方，也就是 `C:\Users\你的用户名` 这个地方。

[^Tilde_Expansion]: [Tilde Expansion (Bash Reference Manual)](https://www.gnu.org/software/bash/manual/html_node/Tilde-Expansion.html)

## Windows 自带代理设置

### 系统图形化代理设置

Windows 10 中，打开 `设置`，进入 `网络和 Internet` 选项就能看到 `代理` 选项卡。

这里可以设置 PAC({% include furigana.html text="自动设置代理" furigana="Proxy auto-config" class="default" %}) 或者手动设置代理。

不过可用性不高，因为 PAC list 总是赶不上变化，手动设置代理又不够灵活，可能代理了本不需要代理的软件，适配的软件并不一目了然。

这个设置在多数情况都是使用其他软件一键设置，作为临时代理支持的软件的方法。

已知可以获得这个代理设置的软件:

+ Internet Explorer*
+ Microsoft Edge
+ Google Chrome* 以及各种 Chromium*
+ Mozilla Firefox
+ Opera Opera*

\* 注意，星号标记的软件默认情况下(不使用扩展)在 Windows 下仅支持系统中的代理设置。

### 环境变量代理设置

Windows 10 中，右键桌面上的此电脑，进入 `属性`，应该就能看到 `高级系统设置`，然后就出现 `环境变量` 的入口。

关于使用大写 `HTTP_PROXY` 或小写 `http_proxy` 的区别，PHPor 通过实验得出的结论是小写使用得广泛。[^phpor]

[^phpor]: [关于http_proxy 与https_proxy – PHPor 的Blog](https://web.archive.org/web/20210510032501/https://phpor.net/blog/post/4352)

在 `系统变量` 中增加两个变量，分别是 `http_proxy` 与 `https_proxy`，然后都填上 http 代理地址。

```text
http_proxy      http://127.0.0.1:2080
https_proxy     http://127.0.0.1:2080

如果有用户名与密码则这么写:
http_proxy      http://用户名:密码@127.0.0.1:2080
https_proxy     http://用户名:密码@127.0.0.1:2080
```

也可以使用临时环境变量，在 CMD 里输入下面的命令:

```shell
set http_proxy=http://127.0.0.1:2080
set https_proxy=http://127.0.0.1:2080
```

PowerShell 里需要这么写:

```PowerShell
$env:http_proxy = "http://127.0.0.1:2080"
$env:https_proxy = "http://127.0.0.1:2080"
```

这样能够代理基于 TCP 与 UDP 通信的部分 CLI 软件，不过 ICMP 无法被代理。

已知可以获得这个代理设置的软件:

+ pip
+ wegt
+ ffmpeg

## git

通常对 git 进行代理只需要修改 `~/.gitconfig` 这个文件。[^gist_zzqcn]

[^gist_zzqcn]: [zzqcn 对 git 设置和取消代理的长评论 - gist](https://gist.github.com/laispace/666dd7b27e9116faece6#gistcomment-2836692)

用户名和密码身份验证可以使用常用写法 `proxy = socks5://用户名:密码@代理服务器地址:端口` 搞定，除了 SOCKS5 也能填入 http 代理地址。[^gist_evantoli]

[^gist_evantoli]: [Configure Git to use a proxy - gist](https://gist.github.com/evantoli/f8c23a37eb3558ab8765)

仅对 GitHub 代理演示代码:

```gitconfig
[http "https://github.com"]
    proxy = socks5://127.0.0.1:1080
```

全局代理演示代码:

```gitconfig
[http]
    proxy = socks5://127.0.0.1:1080
```

## ssh

目前我还没有成功让 ssh 使用 SOCKS5 代理，相关资料中说与 ProxyCommand 这个参数有关。

Linux 用户可以先参考这篇指南: [让你的SSH通过HTTP代理或者SOCKS5代理](https://kanda.me/2019/07/01/ssh-over-http-or-socks/)

<!-- ssh 设置文件位置 `~/.ssh/config` -->

详细设置方法待续

如果你需要测试是否让 ssh 通过了代理，可以使用防火墙拦截 ssh 的流量，然后链接 GitHub 给的测试服务器:

```shell
ssh -T git@github.com
```

## youtube-dl

> Use the specified HTTP/HTTPS/SOCKS proxy. To enable SOCKS proxy, specify a proper scheme.
> For example socks5://127.0.0.1:1080/. Pass in an empty string (--proxy "") for direct connection

```shell
youtube-dl --proxy "socks5://127.0.0.1:1080" {YouTube URL}
```

如上所示，使用 `--proxy` 空格 代理地址字符串，作为参数就能实现代理，支持 HTTP/HTTPS/SOCKS 代理。

-------------------------------------------------------------------------------

接下来的软件就不是 CLI 软件了，不过因为代理设置不明显，所以也写进来。

## electron

electron 软件可以在启动项中加入 `--proxy-server=address:port` 以实现代理，[^electron_proxy]例如:

[^electron_proxy]: [Supported Command Line Switches - Electron](https://www.electronjs.org/docs/api/command-line-switches#--proxy-serveraddressport)

```shell
--proxy-server="socks5://127.0.0.1:1080"
```

注意: electron 软件不支持用户名和密码身份验证。
