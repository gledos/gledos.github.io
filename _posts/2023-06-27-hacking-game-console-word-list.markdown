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

    原本系统固件 (Original Firmware) 的缩写，比如 Switch 的 OFW 是 Horizon OS。

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

+   Cubic Ninja, キュービックニンジャ、方块忍者、立体忍者

    3DS 早期游戏，内置的 QR 码扫描工具被 Smealum 发现了漏洞，可以用来作为 the homebrew launcher 的启动器。[^3hlbropg]

+   Ninjhax

    通过 Cubic Ninja 进入 the homebrew launcher 的漏洞利用工具。

+   the homebrew launcher

    〔待扩充〕

+   LumaCFW

    〔待扩充〕

+   Braindump

    〔待扩充〕

+   hans

    〔待扩充〕

+   NAND

    3DS 使用 NAND 闪存芯片作为存储系统，所以在 3DS 语境下，NAND 泛指系统存储，
    自制软件教程通常也是以「[创建 NAND 备份][]」来表示创建主机的系统镜像，以备恢复。

[创建 NAND 备份]: https://3ds.hacks.guide/zh_CN/godmode9-usage.html#创建-nand-备份

## Switch

这里的均是 Switch 相关的词汇，其他平台不一定适用。

+   CFW (Switch)

    Switch 常见的自定义固件有 SXOS, Atmosphere 和 ReiNX，但它们均为修补的固件或固件修补程序，这意味着它们除了运行自制程序/游戏之外，也能直接运行 Switch 程序/游戏，不过也能让 Switch 运行 Android 这个独立于 Switch 原生系统的 CFW。[^shgb][^1loscf]

[^shgb]: 《[Before Starting](https://switch.homebrew.guide/gettingstarted/beforestarting.html)》, Homebrew Guide documentation. (参照 2023-06-27).

[^1loscf]: 《[List of Switch custom firmwares](https://wiki.gbatemp.net/wiki/List_of_Switch_custom_firmwares)》, WikiTemp, the GBAtemp wiki, 2019-07-28. (参照 2023-06-27).

+   RCM

    恢复模式 (ReCovery Mode) 缩写，有时会被称作工程模式，通常是维修设备所预留的高权限模式，
    但 RCM 这个缩写的使用范围并不广泛，因为这是 NVIDIA Tegra 芯片手册里的缩写，
    而 Intel 和 AMD 似乎没有使用这种缩写，所以似乎只有 Switch 和 [Microsoft Surface RT][]，
    这种使用了 NVIDIA Tegra 芯片的设备，才会使用到 RCM 缩写。

[Microsoft Surface RT]: https://openrt.gitbook.io/open-surfacert/

+   Hekate

    〔待扩充〕

+   Horizon OS, HOS, 地平线系统

    〔待扩充〕

+   SXOS

    〔待扩充〕

+   Atmosphere

    〔待扩充〕

+   ReiNX

    〔待扩充〕

+   [RP2040](https://www.raspberrypi.com/products/rp2040/)

    RP2040 是树莓派 (Raspberry Pi) 的一款芯片，也是 Raspberry Pi Pico 系列所使用的芯片。

+   [RP2040-Zero](https://www.waveshare.com/wiki/RP2040-Zero)

    是 Waveshare 公司贩售的 Pico-Like 板，功能类似于 Raspberry Pi Pico，不过更小型化，
    核心是树莓派公司的 RP2040 芯片。

+   [Picofly](https://github.com/Ansem-SoD/Picofly)

    这是 RP2040-Zero 破解 Switch 所需的固件。

+   树莓派

    指使用 RP2040-Zero 破解 Switch 的方案版本，与其他的攻击/破解芯片方案进行区别。

+   Hard mod

    指对硬件进行操作，比如将 Switch 右 Joycon 的金属引脚接地，又或者是焊接攻击/破解芯片等操作，都算是 Hard mod。[^gwsg]

    理论上只要有硬件上的修改，没有依靠软件，就属于 Hard mod，现在 Switch 的破解方法均是 Hard mod。[^605846]

[^gwsg]: [Switch Glossary](https://wiki.gbatemp.net/wiki/Switch_Glossary), WikiTemp, the GBAtemp wiki.

[^605846]: PizzaBitez, [Why don't we see softmodding on the Switch?](https://gbatemp.net/threads/why-dont-we-see-softmodding-on-the-switch.605846/).

+   Soft mod

    一种使用软件修改 Switch 以允许运行未签名代码的方法，它通常是比 Hard mod 更简单的方法，但是目前尚未发现。

+   硬件破解（硬破）、硬件改装（硬改）

    和 Hard mod 接近，但仅包括焊接攻击/破解芯片，单纯的引脚操作没有被算作硬破。

+   Mariko (T214)

    漏洞名称，Nvidia Tegra X1 的第一版中的错误和漏洞代号。[^gwsg]

+   Fusée Gelée, fusee-gelee, ShofEL2, CVE-2018-6242

    漏洞名称，上面四个名称均指向同一个漏洞。

    〔待扩充〕

+   [Fusée Launcher](https://github.com/Qyriad/fusee-launcher)

    开源全平台软件，是一个 proof-of-concept 的任意代码加载器，适用于各种 Tegra 处理器，
    利用 CVE-2018-6242 (Fusée Gelée) 漏洞，将任意代码通过 USB 向 Switch 加载小型 payload 并执行。

    Fusée Launcher 运行在 Switch 之外的设备上，需要将此设备连接上 Switch，然后在该设备上运行 Fusée Launcher。

    软件活跃情况：已停止开发，仓库已封存。

+   [NXLoader](https://github.com/DavidBuchanan314/NXLoader)

    开源的 Android APP，使用了 Fusée Launcher 以及 ShofEL2 的代码，作用与 Fusée Launcher 相似。

    软件活跃情况：已停止更新。

+   payload

    加载到 Switch 内存中然后运行的程序，通常以二进制文件的形式注入到已经运行的进程中，
    通常是利用 Fusée Gelée 漏洞时，用于修补 Switch OFW，使其运行 CFW。[^gwsg]

    [NXLoader](https://github.com/DavidBuchanan314/NXLoader) 主页中，fusee.bin 被称作 payload。

    payload 与通常的 .elf、.nro、.cxi 或其他独立可执行程序不同，并不是可独立运行的程序。

+   deja-vu

    〔待扩充〕

+   SDSetup

    〔待扩充〕

+   Cold boot、冷启动

    在内存是掉电，空白的情况下启动设备。

+   Warm boot、热启动

    在内存是运行中，存在数据的情况下启动设备。

+   Signed code/Unsigned code, 签名代码/未签名代码

    Switch 在一些时候，只能运行被任天堂签名了的代码，而未签名的代码会被拒绝执行，
    所以如果要运行 Homebrew，就需要使用漏洞绕过相关的验证，就能执行未签名代码了。[^gwsg]

+   eMMC, NAND

    也许是 3DS 以及之前的任天堂游戏破解都是使用 NAND 作为存储芯片，然后开发者习惯了这种说法，
    所以 Switch 虽然使用的是 eMMC，还是会有人将其称为 NAND，二者在 Switch 的语境下可以当作同义词。[^gwsg]

+   emuMMC, emuNAND

    〔待扩充〕

+   NRO, nro

    Horizon OS 使用的可执行文件格式，部分 Homebrew 会使用此格式，能够被 Horizon 和 Homebrew 启动器启动。[^gwsg]

+   NSP, nsp

    Switch eshop 的游戏包格式，类似于 3DS 的 cia 以及 Wii 的 .wad 格式。[^gwsg]

+   XCI, xci

    Switch 卡带的格式，类似于 3ds 控制台的 .3ds 文件。[^gwsg]

<!-- 编译后的 .elf 文件必须转换为 .nro 才能在交换机上运行。 -->

+   拆字库

+   [SwitchBrew](https://switchbrew.org/wiki/Main_Page)

    是一个讨论和研究 Nintendo Switch 自制程序的 wiki，有开发环境、硬件和 API 等资料。

+   〔待扩充〕

    软破、硬破、大气层、tesla、nx-ovlloader、eFuse

## 备注

部分页面提及「Horizo​​n」时，在字母 o 与 n 之间存在两个零宽空格，尚不明确其原因。

## 参考资料

+   Mars, 《[Switch硬件破解经验分享 - 术语篇](https://www.marsshen.com/posts/f96d7ec4/)》, Mars的博客 \| Mars's Blog, 2022-05-29. (参照 2023-06-27).
+   2023game.com, 《[switch问题自查](https://docs.qq.com/doc/DYVNDUG54V3J5V25E)》.

## 脚注
