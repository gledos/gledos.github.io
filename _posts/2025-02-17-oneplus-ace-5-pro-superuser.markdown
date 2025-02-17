---
title: 一加 Ace 5 Pro 的 root 及其自定义玩法
layout: post
published: true
# header-img: "img/bg/pixiv_53864290.svg"
# header-img-object-position: 100% top
# date: '2025-02-17 12:19:00'
tags:
- 折腾
# description:
file-name: 2025-02-17-oneplus-ace-5-pro-superuser.markdown
---

在小米几乎无法解开 BL 锁后，一加手机可能是玩机最方便，社区人数、热度还行，以及性价比高的手机了。
下面会介绍一加 Ace 5 Pro 这款手机的解 BL 锁、root、装模块、调整电压频率等自定义玩法。

<!-- more -->

## 手机简介

先简单介绍一加 Ace 5 Pro，它搭载了高通的<ruby>骁龙 8 至尊版<rt>Snapdragon 8 Elite</rt></ruby>，以及优秀的散热，
所以性能释放可以比较完整。（只是 Hexagon NPU 似乎较少宣传，不确定具体有什么性能，被用在了什么地方）

## 准备

解锁等自定义玩法，是有风险的操作，所以最好拥有一定程度的知识。现在 LLM 如此发达，遇到不懂的词语、机制，
大概可以问问 GPT 之类的 LLM。

然后需要一台电脑，需要配置好 Android 驱动，adb、fastboot 的环境。

并且手机上不要留下重要内容，因为系统为了保护用户隐私，解除 BL 锁时会格式化全部用户内容。所以新手机可以随便玩玩就解锁，
旧手机需要备份重要资料。

最后再提醒：解 BL 锁，及其使用 root 等权限，存在风险。误操作、安装了恶意模块都可能让手机变砖，无法正常使用。
如果第一次接触，还是多看几篇指南再实操，应该能避免一些危险的错误行为。

## Bootloader

解锁并没有什么难度，先在手机系统里开启「开发者选项」，然后开启「OEM 解锁」功能，将手机启动到 fastboot，
输入 fastboot oem unlock 等待格式化。BL 锁就被解除了。[^84050][^41123] 具体操作如下：

[^84050]: 喵勒个咪, 《[一加手机 解锁教程 解除设备限制](https://bbs.oneplus.com/thread/484050)》, 一加社区, 2014-09-05 12:42.

[^41123]: Nooboyu, 《[【刷机】一加 Ace 5 Pro ROOT教程（KernelSU）](https://bbs.oneplus.com/thread/1762656137636741123)》, 一加社区, 2024-12-30. (参照 2025-02-17).

0.  准备输入解锁指令的设备，数据线和手机。并登出系统的 Google 帐号。（如果有）
1.  打开手机设置 ->「关于本机」->「版本信息」，连续点击「版本号」多次以开启「开发者选项」。
2.  返回到设置主页，进入「系统与更新」->「开发者选项」。
3.  将「OEM 解锁」，以及「USB 调试」选项开启。
4.  将手机链接上输入解锁指令的设备，比如 PC。
5.  PC 在命令行里输入 `adb devices`，并检查手机是否出现验证通知。需要在手机勾选记住设备，并确认该操作。
6.  PC 输入指令 `adb reboot bootloader`，等待手机重启到 bootloader 模式。
7.  手机屏幕出现左上角绿色 START 的文字界面后，PC 输入指令 `fastboot devices`，表示检查设备。
8.  出现 `xxxxxxx device` 表示可以连上，PC 输入指令 `fastboot flashing unlock`。
9.  手机会出现提示解锁 BL 的提示，按音量下键，将光标移动到「UNLOCK THE BOOTLOADER」，再按下电源键确认。
10. 手机格式化后再重启到引导界面，基本说明解锁成功。

如果遇到了意外情况，
可以参考「喵勒个咪」编写的《[【刷机】一加 Ace 5 Pro ROOT教程（KernelSU）](https://bbs.oneplus.com/thread/484050)》。
里面介绍了一些链接失败的解决方法，并有许多配图。

<!--
adb reboot bootloader
fastboot oem device-info
-->

设备重置后，如果你之前没有登出 Google 帐号，那么 Factory Reset Protection 机制开始生效。这是一种防盗功能，
设备必须联网登录 Google 后，才能会解锁。ColorOS 的开机设置不是 Google 原版的，所以不会被拦截在这里，
但之后就不能安装 app 商店之外的本地 apk。解决方法是前往 fastboot，然后 移除 frp 分区。[^lf856]
或用翻墙路由器的透明代理等操作。

[^lf856]: Hikari_Calyx, 《[重置保护 / 谷歌锁 Factory Reset Protection 的解除方法](https://bbs.letitfly.me/d/856)》, LetITFly BBS, 2018-12-18. (参照 2025-02-17).

## Root

解锁后，原本被保护的系统分区，就能自定义了。Magisk 这类对内核修改，从而获得最高权限 root 的工具，也就能够安装了。
不过 Magist 开发者入职 Google 后，MagiskHide 功能被移除，并且缺乏更新，于是现在主流的 root 路径不再是 Magisk。

现在主流的 root 方式有：

1.  [Kitsune Magisk](https://github.com/HuskyDG/magisk-files)（狐狸面具）
2.  [KernelSU](https://github.com/tiann/KernelSU)
3.  [KernelSU Next](https://github.com/rifsxd/KernelSU-Next)
4.  [APatch](https://github.com/bmax121/APatch)

这里选择 GitHub 仓库 star 最高的 KernelSU，作为获取 root 的方式。首先需要获取当前系统版本的 `init_boot.img` 镜像文件，
这是手机的 init_boot 分区镜像。然后交给 KernelSU app 里修补。最后将此修补后的镜像，
取代手机的 init_boot 分区。[^84050][^41123][^59584] 具体操作如下：

[^59584]: N1730466003993, 《[KernelSU教程](https://bbs.oneplus.com/thread/1720955150568259584)》, 一加社区, 2024-11-03. (参照 2025-02-17).

0.  按照接靠 BL 锁的步骤，将「USB 调试」选项开启。
1.  下载与当前版本相同的完整（全量）的系统 ROM，然后使用 PC 工具 [payload-dumper-go](https://github.com/ssut/payload-dumper-go)，
    或是 Android 上的 [MT 管理器](https://mt2.cn/) 解包，提取出 `init_boot.img` 镜像文件，并放到手机任意位置。
2.  为手机安装并开启 KernelSU，在顶部的「下载」按钮里找到「选择档案」，然后选择刚提取的 `init_boot.img` 文件，
    完成修补镜像。
3.  将修补好的镜像，传输到 PC。然后输入指令 `adb reboot bootloader`，将手机重启到 bootloader 模式。
4.  PC 输入指令 `fastboot flash init_boot "你修补的镜像文件名"`，将修补的镜像刷入 init_boot 分区。
5.  刷入完成后输入指令 `fastboot reboot`，将手机重启。
6.  在 KernelSU app 里检查状态，如果是「工作中 <LKM>」就说明成功了。

如果 fastboot 给 init_boot 分区刷错了镜像，导致手机 bootloop（变砖），那么再刷入原始的 `init_boot.img` 就好。

此时你就能在 KernelSU app 里，给其它 app 提供 root 权限，以及刷入各种 magisk 模块。

## 软件与模块

### 基础

获取到 root 后，这时该安装一些基础的，使用 root 权限的 app 以及模块。推荐列表如下：

0.  具有 root 编辑权限的文件管理器，之前提到的 MT 管理器就挺不错的。
1.  [Shizuku](https://github.com/RikkaApps/Shizuku)，一些软件会从 Shizuku 获得权限，详细列表可参考 GitHub 上的
    [timschneeb/awesome-shizuku](https://github.com/timschneeb/awesome-shizuku) 仓库。
2.  [aShell](https://f-droid.org/packages/in.sunilpaulmathew.ashell/) 或 [aShell You](https://github.com/DP-Hridayan/aShellYou)，
    它能直接利用 Shizuku 权限，对手机自己执行 adb 命令。
3.  如果有用 Google Play 及其上面的软件，可以 [Play Integrity Fix](https://github.com/chiteroman/PlayIntegrityFix)，
    以修复 Play Integrity 和 SafetyNet，从而能够使用一些会检查完整性的 app。

有了这些工具，就能做各种事情了。

### LSPosed

现在最重要的模块，可能就是 LSPosed，它能 hook 系统与 app，所以使 Android 系统与 App 变得易于修改、自定义。
不过它需要的前置软件不像 Magisk，Magisk 与 LSPosed 的依赖分别是：

Magisk -> Zygisk -> LSPosed

KernelSU -> Zygisk Next -> LSPosed

<!--
```mermaid
graph LR;
    1_1[Magisk] -\-> 1_2[Zygisk] -\-> 1_3[LSPosed]
    2_1[KernelSU] -\-> 2_2["Zygisk Next"] -\-> 2_3[LSPosed]
```
-->

所以需要先安装适配 KernelSU 的 [Zygisk Next](https://github.com/Dr-TSNG/ZygiskNext) 模块，然后再安装 LSPosed。
然而 LSPosed 在停更后（停止公开发布后），旧版无法在基于 ColorOS 15 的一加 Ace 5 Pro 上运行，
所以需要使用其它积极开发的 LSPosed 分叉。

[JingMatrix/LSPosed](https://github.com/JingMatrix/LSPosed) 是目前人气最高的分支，使用该框架就好。在安装 Zygisk Next，
以及 JingMatrix/LSPosed 后，特征会非常明显。容易被游戏封号以及被禁止使用银行软件。

那么最好还要安装 [shamiko](https://github.com/LSPosed/LSPosed.github.io/releases) 模块，以隐藏特征，只是 shamiko 不开源。
如果有顾虑，可能只能不装 LSPosed，或者承受被封号、禁止使用银行软件的情况。

### LuckyTool

有了 LSPosed，就能使用各种好用的 Xposed 模块。这里首推 [LuckyTool](https://github.com/Xposed-Modules-Repo/com.luckyzyx.luckytool)，
这是修改 ColorOS 的模块，功能十分强大。功能有：

1.  对系统隐藏 root，从而使用一些 root 后丢失的功能。
2.  自定义启动器桌面及其文件夹的行列数量。
3.  关闭一些无法关闭的广告。
4.  状态栏的时间显示秒数。
5.  自定义状态栏的音乐流体云名单。（各种音乐 app 都能使用流体云了，不过哔哩哔哩不行）

这只是其中一些典型功能，各种自定义开关加起来，应该超过了 100 个。

## 高级自定义

接下来是更高级的玩法，用 [KonaBess](https://github.com/libxzr/KonaBess) 给 GPU 降压超频，
[Scene](http://vtools.omarea.com/) 来研究功耗以及游戏帧率（付费闭源软件），以及第三方调度。

〔未完待续〕

---

## 脚注
