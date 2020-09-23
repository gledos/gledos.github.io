---
title: niconico 动画等 M3U8 播放列表 & 自适性串流视频下载指南
layout: post
published: true
# date: '2020-05-21 18:01:57'
tags:
    - 指南
description: 一份 M3U8 视频的下载指南
---

由于部分网站的视频使用的是 M3U8/MPD/F4M/ISM 播放列表把一堆视频片段按顺序播放，无法使用通用的手段进行视频下载，
所以接下来是关于这类视频的下载指南 & 教程。

<!-- more -->

<!-- 本文开始写作时间为5月21日 -->

首先是必要的工具，使用 FFmpeg 可能对于缺少经验的视频下载者需要主意这几点：

1. shell的基本使用方法，比如CMD与Bash
2. 环境变量，将 FFmpeg 的路径记录进环境变量里

如果对下面对 M3U8 等技术的讲解不感兴趣，可以直接跳转到[下载部分](#使用-ffmpeg-进行自动化的下载)

-------------------------------------------------------------------------------

直接放置一个MP4文件的在线视频网站基本上已经消失了，因为视频越来越大运营成本越来越高。

首先以上四种适应串流方案都属于是[自适性串流](https://zh.wikipedia.org/zh-cn/自適性串流)(英语：ABS, adaptive bitrate streaming)
的实现，实际流行的只有两个，分别是 M3U8 与 DASH。

| 全名                         | 简称 | 扩展名   | 切片的编码格式   | 支持厂商  |
| ---------------------------- | ---- | -------- | ---------------- | --------- |
| Apple HTTP Live Streaming    | HLS  | m3u8     | MPEG-TS          | Apple     |
| MPEG-DASH                    | DASH | mpd      | 主流的基本都支持 | MPEG      |
| Adobe HTTP Dynamic Streaming | HDS  | f4m      | FLV/F4V/MP4      | Adobe     |
| Microsoft Smooth Streaming   | MSS  | ism/ismc | MP4              | Microsoft |

+ 自适性串流的优点
  + 服务器单个硬盘的压力会大大降低[^20200521105611]
  + 可以对媒体进行AES加密
  + 如果播放器无法重新加载媒体播放列表文件，则播放器将尝试切换到另一个兼容的媒体播放列表
+ 不是那么主要的优点
  + 推动外挂式字幕
  + 快进和快退播放
  + 备用音频和视频格式
  + 广告插入方便
  + 增加爬虫成本

单从技术上来说，MPEG-DASH 比苹果的 HLS 更强，具体的对比在这篇文章里
[MPEG-DASH vs. Apple HLS vs. Microsoft Smooth Streaming vs. Adobe HDS - Bitmovin](https://web.archive.org/web/20191002111059/https://bitmovin.com/mpeg-dash-vs-apple-hls-vs-microsoft-smooth-streaming-vs-adobe-hds/)。
之所以 m3u8 还是比较常见，主要有苹果没有支持原生支持 MPEG-DASH ，而使用开源库势必会有性能上的损失，
还有维护成本等原因，所以 m3u8 非常常见。

还有一个原因是苹果公司较早之前就要求IOS开发者在超过10分钟或大于5MB的视频都使用 HLS 。[^20190223161426]

M3U8 播放列表都使用的是 MPEG-TS(MPEG-2 Transport Stream) 格式片段视频，
TS 格式设计目的就是为了地面和卫星的可靠性较低的传输介质，所以 TS 无损的拼接大量片段以及在移动设备上会很可靠。
直接修改 .ts 的后缀为 .mp4 也没有问题。

下载与合并
----------

### 录制

这是最直觉，但也是损失很大的获取视频的方式，一般只有以下的几种情况才会经常使用。

+ 使用 OBS Studio, Captura 等录制软件对难以嗅探到的视频进行"盗录"
+ 通过录制快速获取带有弹幕效果的视频
+ 使用 VLC, PotPlayer 等支持播放与录制网络流媒体的软件进行录制网络直播

### 使用 FFmpeg 进行自动化的下载

如果需要对 FFmpeg 进行代理，请先看[简易的 Netch 代理 ffmpeg 教程](#简易的-netch-代理-ffmpeg-教程)

首先得找到 m3u8 链接的位置，以前没有工具的情况下可能需要开启开发者工具进行寻找，现在 niconico 播放器右键开启系统信息[^xit]就能够看到。

`master.m3u8?` 之后的参数也要带上，有了这个就可以下载、拼接视频了，然后在 shell 里输入

```shell
ffmpeg -i "[视频m3u8地址]" -c copy "[视频名字.mp4]"
```

如：

```shell
ffmpeg -i "https://■■■■.nico/master.m3u8?■■■" -c copy "sm■■658215.mp4"
```

使用浏览器扩展或者用户脚本可以加速这一过程，比如 Firefox, Chrome 可以安装 [stream-detector](https://github.com/rowrawer/stream-detector/) 这款扩展快速生成下载参数。

然后就能获得下载到的 MP4 视频了。

### 使用 You-Get 进行下载

由于 You-Get 基于 python，又没有打包成独立的exe可执行文件，所以没有安装 python 的 Windows 系统相对而言比较麻烦。
并且受限于网络问题，可能安装速度很慢，所以安装的时候可能需要使用代理进行加速。

按照官网的安装方法完成后，就可以用来下载 niconico 视频了。

不过每次下载都需要登陆账号并且下载到的视频质量不高，优点是 python 软件很容易使用代理，比如 PySocks。

如果想要尝试用 You-Get 下载视频，那么 Eric 写的教程能够帮助到你 [使用 you-get 下载视频 Eric](https://ericclose.github.io/you-get-tutorial.html)

### ffmpeg 等程序不支持代理的网络问题

通常 Niconico[^niconet] 等网站在大陆直连的情况下无法正常使用，所以比起其他地方下载视频，还有一个额外的操作，就是对 ffmpeg 进行代理。

| 代理方式      | 可行性                    |
| ------------- | ------------------------- |
| 软件自带代理  | ffmpeg 没有或者几乎不可用 |
| 使用shell代理 | 我尝试过，但没有成功      |
| VPN全局代理   | 不适合大多数人            |
| 劫持*         | 算是最适合大多数人的方法  |

*劫持指的是 API hook, LSP(Layered Service Provider), 虚拟网卡等

| 技术                                     | 软件                                     |
| ---------------------------------------- | ---------------------------------------- |
| DLL注入(hook)                            | Proxifier(Windows旧版), SocksCap64       |
| LSP                                      | Proxifier(Windows新版), 大部分游戏加速器 |
| [TUN/TAP][^tuntap](虚拟网卡) + tun2socks | SSTAP, OpenVPN                           |
| 混合技术                                 | Netch, Mellow                            |

[^tuntap]: [虚拟网卡 TUN/TAP 驱动程序设计原理](https://web.archive.org/web/20170307233136/https://www.ibm.com/developerworks/cn/linux/l-tuntap/index.html)

> 小历史:
>
> SocksCap 的停止更新后，Taro 开发一款私人使用的支持64位程序的DLL注入代理，名为 Sockscap64。
>
>但因为DLL注入对反作弊的游戏不友好，所以 Taro 又开发了 SSTAP，以虚拟网卡的方式，达到最大的兼容性。
>
>最后作者在官网声明 SSTap 和 SocksCap64 于2017年11月19日停止开发及维护和下载，Taro 的 SSCap 也停止了维护。
>
>原因是「硬蝶損壞，所有數據已丟失，多方償試修復未果，決定放棄，SSTAP及SC64永久停更。BYE！」。
>
>最后2019年6月，Netch 与 Mellow 这两款软件接过了 SSTAP 的接力棒，继续向前。

我通常用的是 Netch 代理 ffmpeg.exe 因为比较方便，Mellow 我还不会用，所以就没法写快速入门的教程了。

Netch 新建代理配置很容易，因为图形化的界面以及简单易懂的配置目录。

#### 简易的 Netch 代理 ffmpeg 教程

1. 菜单中选择`服务器(Server)`，如果你常用的代理软件已经给出了 Socks5 端口，就可以直接在`添加 [Socks5] 服务器`选项中填写，进行伪·双重代理
2. 菜单中选择`模式(Mode)`，然后创建新的模式
3. 名称随意，在最下方的`可输入字符框`里输入 ffmpeg.exe ，接着点击`添加(Add)`，最后点击`保存(Save)`
4. 主页面中找到`配置信息(Configuration)`里的部分，两个下拉列表`服务器(Server)`与`模式(Mode)`都设置到位
5. 点击`启动(Start)`以启动对 ffmpeg 的代理

### 合并片段视频

通常使用上述的 FFmpeg 教程就能直接合成，但如果你在学会使用之前，就下载了大量的 .ts 视频片段，这时就需要下面介绍的方法了。

假设只有很少量的文件，如三个TS文件，如 A.ts B.ts 与 C.ts ，只要在输入命令时注意先后顺序就能按顺序合成了。

```shell
copy /b A.ts+B.ts+C.ts 输出的视频.ts
```

假设只有小于等于9个文件，比如 1.ts 2.ts ...... 9.ts ，只要使用星号就能按顺序合成，
但如果超过9个文件，和成时就会把`10`排在`2`的前面，导致顺序错误。

```shell
copy /b *.ts 输出的视频.ts
```

当文件数量很大时，如果还是 1.ts 开头，就要批量修改文件名了，使用 everything 等工具进行批量补0。
比如有200个ts文件，就需要对 99.ts 及其之前的文件进行补0，使文件列表变成下表所示。

```file
001.ts
002.ts
003.ts
...
200.ts
```

> 之所以需要这么处理是因为大多数系统默认的排序都是自然排序顺序(Natural sort order)
> 这是一种从首位到末尾进行排序的方法，所以会导致`10`排在`2`的前面。
>
> + **相关维基百科** [Natural sort order - Wikipedia](https://en.wikipedia.org/wiki/Natural_sort_order),
> + **相关测试** [DaveKoelle.com The Alphanum Algorithm](https://archive.vn/wJSeC),
> + **相关讨论** [Why do some sorting methods sort by 1, 10, 2, 3...? - Software Engineering Stack Exchange](https://archive.vn/efHfP)

<!-- 

1.说说进程注入的原理
2.讲讲各个平台有哪些软件

最后就开始下载了

 -->

### 下载时间

如果没有会员，那么只能在深夜到上午12:00左右才能下载高清的视频。

脚注
----

[^20200521105611]: [为什么网络点播系统使用m3u8更有优势-PPVOD视频点播源码/直播平台/服务器转码软件系统](https://web.archive.org/web/20200521105611/http://www.ppvod.com/dianbo/wenti/443.html)

[^20190223161426]: [About HTTP Live Streaming](https://web.archive.org/web/20190223161426/https://developer.apple.com/library/archive/referencelibrary/GettingStarted/AboutHTTPLiveStreaming/about/about.html)

[^xit]: 开启系统信息按钮的繁体中文为: 開啟系統訊息;  
        日语为：システムメッセージを開く

[^niconet]: [Niconico动画在中国大陆地区的屏蔽](https://zh.wikipedia.org/wiki/Niconico動畫#中国大陆地区的屏蔽)
