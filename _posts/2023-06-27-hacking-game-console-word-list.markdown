---
title: 游戏机黑客词汇表
layout: post
published: true
# header-img: "img/bg/pixiv_53864290.svg"
# header-img-object-position: 100% top
# date: '2023-06-27 00:00:00'
tags:
- 游戏
description: 游戏机 Hacking 相关的概念比较多，这里收集整理了相关的词汇表
file-name: 2023-06-27-hacking-game-console-word-list.markdown
---

游戏机黑客相关的概念比较多，而词语含义可能也不容易理解，这里收集整理了相关的词汇表，用作参考。

正在施工中，尚未完成。

<!-- more -->

如果想要给封闭的设备换上功能强大的自制系统，然后获取最高权限，以及运行各种第三方程序，可能就需要让机器运行自定义固件，下面是相关的词典。

## 通用

+   boot loader

    引导加载程序，比如 PC 主要使用的引导加载程序通常就是 UEFI（之前常用的是 BIOS）。在封闭的设备里，如果换成自定义引导加载程序，就能加载不同或者修补后的固件，Switch 的 Hekate 就是一个自定义引导加载程序。

+   Recovery Mode

    恢复模式，通常是为了维修设备，所预留的高权限模式，有了权限就能做到许多自定义。

+   OFW

    原本系统固件 (Original Firmware) 的缩写，比如 Switch 的 OFW 是 Horizo​​n OS。

+   [CFW](https://en.wikipedia.org/wiki/Custom_firmware)

    自定义固件 (Custom firmware) 的缩写，通常固件也等同于系统的概念，所以第三方 Android ROM 比如 LineageOS 和第三方路由器系统 OpenWrt 也算是自定义固件。

+   the homebrew channel, [the homebrew launcher](https://smealum.github.io/3ds/), homebrew loader, hbmenu

    这是任天堂游戏机 Wii, 3DS 和 Switch 平台上的自制程序启动器，用来图形化的呈现各个自制软件。

+   [Homebrew](https://en.wikipedia.org/wiki/Homebrew_(video_games))

    原意是家酿啤酒，在自定义固件领域就是自制软件的意思，比如上文提到的非任天堂授权创建的所有程序，包括 CFW 和自定义引导加载程序，《香港97》这款第三方 FC 游戏也算是 Homebrew。

## 3DS

+   Smealum

    Cubic Ninja 漏洞的发现者。[^3hlbropg]

[^3hlbropg]: Tom Phillips, 《[3DS homebrew loader built, requires obscure puzzle game](https://web.archive.org/web/20230227234517/https://www.eurogamer.net/3ds-homebrew-loader-built-requires-obscure-puzzle-game)》, Eurogamer.net, 2014-11-19. (参照 2023-06-27).

+   Cubic Ninja, キュービックニンジャ, 方块忍者, 立体忍者

    3DS 早期游戏，内置的 QR 码扫描工具被 Smealum 发现了漏洞，可以用来作为 the homebrew launcher 的启动器。[^3hlbropg]

+   Ninjhax

    通过 Cubic Ninja 进入 the homebrew launcher 的漏洞利用工具。

+   the homebrew launcher

    待续

+   LumaCFW

    待续

+   Braindump

    待续

+   hans

    待续

## Switch

这里的均是 Switch 相关的词汇，其他平台不一定适用。

+   CFW (Switch)

    Switch 常见的自定义固件有 SXOS, Atmosphere 和 ReiNX，但它们均为修补的固件或固件修补程序，这意味着它们除了运行自制程序/游戏之外，也能直接运行 Switch 程序/游戏，不过也能让 Switch 运行 Android 这个独立于 Switch 原生系统的 CFW。[^shgb][^1loscf]

[^shgb]: 《[Before Starting](https://switch.homebrew.guide/gettingstarted/beforestarting.html)》, Homebrew Guide documentation. (参照 2023-06-27).

[^1loscf]: 《[List of Switch custom firmwares](https://wiki.gbatemp.net/wiki/List_of_Switch_custom_firmwares)》, WikiTemp, the GBAtemp wiki, 2019-07-28. (参照 2023-06-27).

+   RCM

    恢复模式 (ReCovery Mode) 缩写，有时会被称作工程模式，通常是维修设备所预留的高权限模式，但 RCM 这个缩写的使用范围并不广泛，因为这是 NVIDIA Tegra 芯片手册里的缩写，而 Intel 和 AMD 似乎没有使用这种缩写，所以似乎只有 Switch 和 [Microsoft Surface RT](https://openrt.gitbook.io/open-surfacert/) 这种使用了 NVIDIA Tegra 芯片的设备，才会使用到 RCM 缩写。

+   Horizon OS, HOS, 地平线系统

    待续

+   Hekate

    待续

+   SXOS

    待续

+   Atmosphere

    待续

+   ReiNX

    待续

+   fusee-gelee, ShofEL2, CVE-2018-6242

    待续

+   deja-vu

    待续

+   SDSetup

    待续

+   emuNAND, emuMMC

    待续

+   [SwitchBrew](https://switchbrew.org/wiki/Main_Page)

    是一个讨论和研究 Nintendo Switch 自制程序的 wiki，有开发环境、硬件和 API 等资料。

+   待续

    软破、硬破、大气层、tesla、nx-ovlloader

## 参考资料

+   Mars, 《[Switch硬件破解经验分享 - 术语篇](https://www.marsshen.com/posts/f96d7ec4/)》, Mars的博客 \| Mars's Blog, 2022-05-29. (参照 2023-06-27).
+   2023game.com, 《[switch问题自查](https://docs.qq.com/doc/DYVNDUG54V3J5V25E)》.

## 脚注
