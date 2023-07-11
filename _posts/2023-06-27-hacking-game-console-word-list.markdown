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

如果想要给封闭的设备换上功能强大的自制系统，然后获取最高权限，以及运行各种第三方程序，
可能就需要让机器运行自定义固件，下面是相关的词典。

## 通用

### BootROM

+   含义：是固化在 SOC 内部只读闪存上的一段代码，包含系统启动所需的代码，也称为引导加载程序 (bootloader)。

[bootROM]: #bootrom

### boot loader

+   含义：引导加载程序，比如 PC 主要使用的引导加载程序通常就是 UEFI（之前常用的是 BIOS）。在封闭的设备里，
    如果换成自定义引导加载程序，就能加载不同或者修补后的固件，Switch 的 [Hekate][] 就是一个自定义引导加载程序。

### Recovery Mode

+   含义：恢复模式，通常是为了维修设备，所预留的高权限模式，有了权限就能做到许多自定义。

### OFW

原本系统固件 (Original Firmware) 的缩写，比如 Switch 的 OFW 是 Horizon OS。

### CFW

+   含义：CFW 是自定义固件 (Custom firmware) 的缩写，通常固件也等同于系统的概念，
    所以第三方 Android ROM 比如 LineageOS 和第三方路由器系统 OpenWrt 也算是自定义固件。
+   网页：[Wikipedia](https://en.wikipedia.org/wiki/Custom_firmware)

<!-- ### the homebrew channel, [the homebrew launcher](https://smealum.github.io/3ds/), homebrew loader, hbmenu

+   含义：这是任天堂游戏机 Wii, 3DS 和 Switch 平台上的自制程序启动器，用来图形化的呈现各个自制软件。 -->

### Homebrew

+   含义：Homebrew 的原意是家酿啤酒，在自定义固件领域就是自制软件的意思，
    比如上文提到的非任天堂授权创建的所有程序，包括 CFW 和自定义引导加载程序，
    《香港97》这款第三方 SFC/SNES 游戏也算是 Homebrew。

+   网页：[Wikipedia](https://en.wikipedia.org/wiki/Homebrew_(video_games))

### ifixit

+   含义：是一个关于硬件维修的网站，免费提供维修硬件的步骤。
+   网页：[官网](https://www.ifixit.com)

[ifixit]: #ifixit

## 3DS

这里的均是 3DS 相关的词汇，其他平台不一定适用。

### Smealum

Cubic Ninja 漏洞的发现者。[^3hlbropg]

[^3hlbropg]: Tom Phillips, 《[3DS homebrew loader built, requires obscure puzzle game](https://web.archive.org/web/20230227234517/https://www.eurogamer.net/3ds-homebrew-loader-built-requires-obscure-puzzle-game)》, Eurogamer.net, 2014-11-19. (参照 2023-06-27).

### Cubic Ninja

+   别名：キュービックニンジャ、方块忍者、立体忍者
+   含义：3DS 早期游戏，内置的 QR 码扫描工具被 Smealum 发现了漏洞，
    可以用来作为 the homebrew launcher 的启动器。[^3hlbropg]

### Ninjhax

+   含义：通过 Cubic Ninja 进入 the homebrew launcher 的漏洞利用工具。

### Sighax

〔待扩充〕

### ARM9

+   含义：3DS 的处理器之一。这是系统作为辅助使用的单核处理器。用于向后兼容 NDS，
    还负责初始启动、加密/解密和所有签名检查。

### ARM9LoaderHax (A9LH)

+   含义：利用 ARM9 加载程序中的缺陷来运行非官方代码的漏洞。该漏洞利用修改后的加密密钥，
    以便在加载程序解密 ARM9 二进制文件时对其进行破坏。这是通过特定方式完成的，
    以使执行流跳转到先前注入的有效负载。

### ARM11

+   含义：3DS 的处理器之一。这是系统的主要双核（new 3DS 上为四核）处理器，处理大多数任务。
    其中一个核心仅用于设备的操作系统，其他核心则执行所有其他任务。

### b9

+   含义：全称是 Boot9，是指 ARM9 的 BootROM。

### b11

+   含义：全称是 Boot11，是指 ARM11 的 BootROM。

### b9s

+   含义：全称是 Boot9Strap。

### the homebrew launcher

〔待扩充〕

### LumaCFW

〔待扩充〕

### Braindump

〔待扩充〕

### hans

〔待扩充〕

### NAND (3DS)

+   含义：3DS 使用 NAND 闪存芯片作为存储系统，所以在 3DS 语境下，NAND 泛指系统存储，
    自制软件教程通常也是以「创建 NAND 备份 (Creating a NAND Backup)」来表示创建主机的系统镜像，
    以备恢复。

### TWiLight Menu++

https://wiki.ds-homebrew.com/twilightmenu/installing-3ds

## Switch

这里的均是 Switch 相关的词汇，其他平台不一定适用。

### Tegra X1

+   别名：Erista, T210, V1。
    +   Tegra X1 是正式名称，rista 是代号，T210 是型号，V1 表示这是第一版芯片。
+   含义：这是 NVIDIA 公司推出的芯片名，是 Switch 早期版本所使用的型号，含有 Fusée Gelée 漏洞。

[Tegra X1]: #tegra-x1

### Tegra X1+

+   别名：Mariko, T214, T210B01, V2。
    +   Tegra X1+ 是正式名称，Mariko 是代号，T214, T210B01 是型号，V1 表示这是第一版芯片。
+   含义：是 Erista 的后继芯片，修复了 Fusée Gelée 漏洞，提升了效能功耗比，从而实现相同的电池容量，
    而增加续航和减少发热，伴随 Switch 续航版推出。[^gwsg]

### HEG-001

+   含义：是 Switch 机身被面上标注的型号，全称是 MOD.HEG-001，表示 Nintendo Switch（OLED 款式）。
+   芯片：Tegra X1+。
+   外形：标准的 Switch 外观。
+   屏幕：7.0 英寸，屏幕是全贴合的 OLED，并且尺寸较大，所以屏幕边缘的黑边被明显改善。
+   备注：OLED 在日本叫做「有機EL」，即「有机EL」，指的是有机电致发光 (Organic Electroluminescent)，
    跟 OLED 全称有机发光二极管 (Organic Light-Emitting Diode) 指代的是相同的产品，前者指代的是技术，
    后者指代具体的元器件名称。

### HAC-001

+   含义：是 Switch 机身被面上标注的型号，全称是 MOD.HAC-001，表示 Nintendo Switch 初版和续航增强版，
    续航增强版型号的全称是 MOD.HAC-001(-01)，增加了后半部分。
+   芯片：初版是 Tegra X1，而续航增强版是 Tegra X1+。
+   外形：标准的 Switch 外观。
+   屏幕：6.2 英寸，屏幕不是全贴合的，尺寸较小，所以屏幕边缘有大黑边。

### HDH-001

+   含义：是 Switch 机身被面上标注的型号，全称是 MOD.HDH-001，表示 Nintendo Switch Lite。
+   芯片：Tegra X1+。
+   外形：缩小的的 Switch 外观，一体成形的外侧，所以没有可拆卸的 Joy-Con 手柄。
+   屏幕：5.5 英寸，屏幕不是全贴合的，尺寸较小，所以屏幕边缘有大黑边，但是被染色的成了主机的颜色，
    类似于 2DS 的解决方案。

### CFW (Switch)

+   含义：Switch 常见的自定义固件有 SX OS, Atmosphere 和 ReiNX，但它们均为修补的固件或固件修补程序，
    这意味着它们除了运行自制程序/游戏之外，也能直接运行 Switch 程序/游戏，不过也能让 Switch
    运行 Android 这个独立于 Switch 原生系统的 CFW。[^shgb][^1loscf]

[^shgb]: 《[Before Starting](https://switch.homebrew.guide/gettingstarted/beforestarting.html)》, Homebrew Guide documentation. (参照 2023-06-27).

[^1loscf]: 《[List of Switch custom firmwares](https://wiki.gbatemp.net/wiki/List_of_Switch_custom_firmwares)》, WikiTemp, the GBAtemp wiki, 2019-07-28. (参照 2023-06-27).

[CFW (Switch)]: #cfw-switch

### RCM

+   含义：恢复模式 (ReCovery Mode) 缩写，有时会被称作工程模式，通常是维修设备所预留的高权限模式，
    但 RCM 这个缩写的使用范围并不广泛，因为这是 NVIDIA Tegra 芯片手册里的缩写，
    而 Intel 和 AMD 似乎没有使用这种缩写，所以似乎只有 Switch 和 [Microsoft Surface RT][]，
    这种使用了 NVIDIA Tegra 芯片的设备，才会使用到 RCM 缩写。

+   进入方法：早期版本的 NVIDIA Tegra 进入 RCM 的方法，是在启动时按下 Home 和 Volume Up 键，
    但是 Switch 平板本体没有 Home 键（左 Joy-Con 的 Home 键不算）。

[Microsoft Surface RT]: https://openrt.gitbook.io/open-surfacert/

[RCM]: #rcm

### Hekate

+   含义：Custom Switch bootloader，Switch 自定义引导程序，有完整的图形化界面支持（图形化程序名为 Nyx GUI），可以引导进入各种 OFW, [CFW (Switch)][] 甚至是 Android 和 Linux。

+   作者：CTCaer

+   软件活跃情况：积极开发和维护中。

+   网站：[GitHub 仓库](https://github.com/CTCaer/hekate)

[Hekate]: #hekate

### Horizon OS

+   别名：HOS, 地平线系统, [OFW](#OFW), FW

+   别名含义：HOS 是简称，「地平线系统」是中文翻译，后者可以查看 [OFW](#OFW) 词语的解释。

+   含义：Horizon OS 基于 FreeBSD 开发的系统，比起前身 3DS 的系统来说，隐藏了浏览器，并且有完善的虚拟化，
    这使之前 3DS 的软件漏洞问题几乎无法在 Switch 上复现。

[Horizon OS]: #horizon-os

### Atmosphere

+   翻译：大气层

+   别名：Atmosphère

+   含义：开源的 [CFW (Switch)][]，属于对 [Horizon OS][] 的修补，替换或修改了一部分系统组件。

+   作者：SciresM, TuxSH, hexkyz 和 fincs。

+   软件活跃情况：积极开发和维护中。

+   网站：[GitHub 仓库](https://github.com/Atmosphere-NX/Atmosphere).

[Atmosphere]: #atmosphere

### RajNX

+   含义：一套 [CFW (Switch)][] 整合包，包含 [Hekate][], Atmosphere, hbloader, hbmenu 等软件。

+   作者：rajkosto

+   软件活跃情况：已停止更新，并且作者不推荐继续使用。

+   网站：
    +   已编译程序：<https://switchtools.sshnuke.net>
    +   GBAtemp：<https://gbatemp.net/threads/no-longer-maintained-rajnx-starter-pack-for-nintendo-switch.513785/>
    +   维基：<https://www.gamebrew.org/wiki/RajNX_Switch>

### ReiNX

〔待扩充〕

### modchip

+   别名：破解芯片

+   含义：执行 Hard Mod 的芯片。

### RP2040

+   含义：RP2040 是树莓派 (Raspberry Pi) 的一款芯片，也是 Raspberry Pi Pico 系列所使用的芯片。
+   官网：<https://www.raspberrypi.com/products/rp2040/>

### RP2040-Zero

+   含义：RP2040-Zero 是 Waveshare 公司贩售的 Pico-Like 板，功能类似于 Raspberry Pi Pico，
    不过更小型化，核心是树莓派公司的 RP2040 芯片。
+   官网：<https://www.waveshare.com/wiki/RP2040-Zero>

### Picofly

+   含义：Picofly 是 RP2040-Zero 破解 Switch 所需的固件，有时也可以指代这项破解 Switch 的方案。

+   作用范围：Picofly 不仅仅能用在 Waveshare 公司的 RP2040-Zero 上，还有 RP2040-One, RP2040-Tiny，
    以及其他公司的 Seeed XIAO-RP2040, Adafruit ItsyBitsy RP2040。[^dpig]

+   其他类似概念：能够运行 Picofly 的硬件，可能被称作 Picofly 板。

+   官网：<https://github.com/Ansem-SoD/Picofly>

[^dpig]: lightninjay, [A definitive PicoFly install guide V.6.2](https://gbatemp.net/download/a-definitive-picofly-install-guide.37968/), GBAtemp.net, Apr 13, 2023.

### 树莓派

+   含义：指使用 RP2040 芯片的开发板破解 Switch 的方案版本，与其他的破解芯片方案进行区别。

### McFly

+   含义：McFly 是兼容 Picofly 的 RP2040 开发板板，于 2023年3月22日 公开，预计分发协议是 CC BY-SA，
    不过截至 2023年6月30日 还没有正式发布。[^mcfly]

[^mcfly]: [McFly - an RP2040 board compatible with Picofly](https://gbatemp.net/threads/mcfly-an-rp2040-board-compatible-with-picofly.629024/), GBAtemp.net.

### Team Xecuter

+   别名：TX

+   含义：Team Xecuter 是一个破解游戏机的黑客小组，主要贩售 Switch 相关的破解商品。

[Team Xecuter]: #team-xecuter

### SX Pro

+   含义：[Team Xecuter][] 开发的注入器，是用来运行 SX OS 的工具。[^txsx]

[^txsx]: [Team Xecuter SX.](https://web.archive.org/web/20180531150029/https://sx.xecuter.com/)

+   破解原理：Fusée Gelée 漏洞。

### SXTools

+   含义：SXTools 是第三方开发者基于 NXLoader，所开发的替代 SX Pro 的软件，
    只要有支持 OTG 功能的 Android 设备。

+   官网：<https://github.com/annson24/SXTools>

### SX Core/Lite

+   别名：TX 破解芯片、SX 破解芯片
+   含义：SX Core 和 SX Lite 都是 [Team Xecuter][] 的芯片商品，焊接在 Switch 主板上进行破解。

### SX OS

+   别名：TX 系统。

+   含义：[Team Xecuter][] 开发的 [CFW (Switch)][]，是非开放的，具有特殊的 DRM。[^txsx]

### Spacecraft-NX

+   含义：第三方开发者为 SX Core/Lite 开发的完全开源兼容固件，可以游玩受太空入侵者启发的迷你游戏，
    也可以加载任何 [payload][]，除了 SX OS，因为无法破解 TX 的 DRM 功能；

    官网：<https://github.com/Spacecraft-NX/firmware>

### 国产芯片

+   别名：高仿芯片、国产山寨芯片、国产 TX 芯片和 hwfly 芯片。
    +   前四个别名的意思都是山寨 Team Xecuter 的 SX Core/Lite 芯片，原因是 Team Xecuter 在 2020 年时，
        成员被捕，接着 Team Xecuter 停止了活动，于是有人仿照 SX Core/Lite 的硬件，推出了仿制芯片。
    +   而 hwfly 似乎是品牌名称。

芯片版本差异（未翻译）：[^97580]

[^97580]: [For Hwfly Lite V3/V4.1 Chip Accessories,Flex Cables,V4.1 Flash Usb(No Include The Chip Itself),Wholesale Price !!](https://archive.is/W53CW "https://www.aliexpress.com/item/3256804269997580.html"), aliexpress.

+   V3 Chip:
    Unflashable & Non upgradable, has stopped make,no suggest now !
+   V4 Chip(Oled and Core):
    +   Flashable & Upgradable!! (Pre installed nx firmware)
    +   BUG: V4 chip can't work with Toshiba emmc(THGBM*****)console !!
    +   Design defect:USB wrong put port bring chip burn risk!
    +   Newest V4 chip 0.7.1 firmware can't support V1 console,
        need downgrade it by yourself ! (Suggest V5 core for V1 console)
    +   Chip train and reading speed slow, and compatibility needs to be improved !
+   V4.1 and V4.1+ Chip(Lite,Oled and Lite&Oled universal version):
    +   Flashable & Upgradable!! (Pre installed sx firmware or nx firmware)
    +   No USB wrong put port chip burn risk with circuit insurance！
    +   Sx ic,Fast chip train and reading speed,best compatibility(support Toshiba emmc console) !!
    +   Ultimate version and last version special for lite console and popular Oled chip model !!
    +   All v4.1 models same work and only accessories different !!
+   V5 and V5+ Chip(Lite,Core and Oled):
    +   Flashable & Upgradable!! (Pre installed sx firmware or nx firmware)
    +   No USB wrong put port chip burn risk with circuit insurance！
    +   Sx ic,Fast chip train and reading speed,best compatibility(support Toshiba emmc console) !!
    +   Ultimate version and last version special for V1,V2 console and Newest Oled chip model !!
+   How to choose the correct console chip model?
    1.  Hwfly V3 chip Unflashable & Non upgradable chip has stopped make,no suggest now !
    2.  Hwfly Core V4/V5 chip work with big Normal V1/V2 console MOD.(HAC-001/001-01) !
    3.  Hwfly Lite V5/V4.1 chip work with small Lite console MOD.(HDH-001) !
    4.  Hwfly Oled V4/V4.1/V4.1+/V5/V5+ chip work with big Oled console MOD.(HEG-001) !
    5.  Chip accessories, Flex cables and so on !

### PCB 丝印

不同的芯片会有一些标记来区分型号：

+   `HWFLY`：国产第一代芯片，可运行 Spacecraft-NX 固件引导大气层系统，不稳定。[^xmsjh]
+   `MV1-6`：国产第二带芯片，虚拟系统可以离线升级，但真实系统联网升级后该芯片会不起作用，需要重置芯片。[^xmsjh]
+   `MV1-6`, `MV1-6.0`：国产三代芯片，不能更新固件，有关机关不掉 bug。[^78703]
+   `MV1-7`, `MV1-7.1`：国产四代芯片，可以更新固件。[^78703]
+   `MV1-7 OL`, `MV1-7.1 OL`：国产四代芯片，OLED 专用。[^78703]
+   `MV1-8 OL`：国产第五代芯片，OLED 专用。[^78703]
+   `Hwfly Core RP2040`：七代芯片，即树莓派芯片。[^78703]
+   `Hwfly Oled RP2040`
+   `Oled V6`：INSTINCT-NX 芯片，为 OLED 优化。6 个焊点的排线换成长条的，不用翻折，更合理。[^78703][^28676]
+   `PG 树莓派 第三版`
+   `new2040plus`
+   `Mv-OL v2.1`

[^xmsjh]: Charlie Liu, 《[任天堂 Switch 的破解史](https://xmper.cc/2023/02/21/Switch-jailbreaking-history/ "https://web.archive.org/web/20230701122305/https://xmper.cc/2023/02/21/Switch-jailbreaking-history/")》, 寻梦派, 2023-02-21.

[^78703]: 不晓自在, 《[switch芯片软硬件教程](https://zhuanlan.zhihu.com/p/639078703 "https://archive.is/teyeC")》, 知乎专栏, 2023-06-23.

[^28676]: HWE, [Hacking INSTINCT-NX Chip](https://gbatemp.net/threads/instinct-nx-chip.628676/)

### 一次性破解、系留越狱

〔待扩充〕

### Hard mod

指对硬件进行操作，比如将 Switch 右 Joy-Con 的金属引脚接地，又或者是焊接攻击/破解芯片等操作，都算是 Hard mod。[^gwsg]

理论上只要有硬件上的修改，没有依靠软件，就属于 Hard mod，现在 Switch 的破解方法均是 Hard mod。[^605846]

[^gwsg]: [Switch Glossary](https://wiki.gbatemp.net/wiki/Switch_Glossary), WikiTemp, the GBAtemp wiki.

[^605846]: PizzaBitez, [Why don't we see softmodding on the Switch?](https://gbatemp.net/threads/why-dont-we-see-softmodding-on-the-switch.605846/).

### Soft mod

一种使用软件修改 Switch 以允许运行未签名代码的方法，它通常是比 Hard mod 更简单的方法，但是目前尚未发现。

### 硬件破解（硬破）、硬件改装（硬改）

和 Hard mod 接近，但仅包括焊接攻击/破解芯片，单纯的引脚操作没有被算作硬破。

### CVE-2018-6242

+   别名：Fusée Gelée, fusee-gelee, ShofEL2
    +   均是指同一个漏洞名称
+   含义：这是 [Tegra X1][] 芯片含有的漏洞，设备进入 [RCM][] 后可以绕过保护芯片的 [bootROM][] 锁定
    （可能类似于 Android 设备常说的「解 Bootloader 锁」），使攻击者执行任意代码，比如启动 [CFW (Switch)][]。[^kotue]

[^kotue]: Kyle Orland, [The “unpatchable” exploit that makes every current Nintendo Switch hackable](https://arstechnica.com/gaming/2018/04/the-unpatchable-exploit-that-makes-every-current-nintendo-switch-hackable/)

### Fusée Launcher

+   Fusée Launcher 是开源多平台软件，是 proof-of-concept 的任意代码加载器，适用于各种 Tegra 处理器，
    利用 CVE-2018-6242 (Fusée Gelée) 漏洞，将任意代码通过 USB 向 Switch 加载小型 [payload][] 并执行。

    Fusée Launcher 运行在 Switch 之外的设备上，需要将此设备连接上 Switch，然后在该设备上运行 Fusée Launcher。

+   软件活跃情况：已停止开发，仓库已封存。

+   官网：<https://github.com/Qyriad/fusee-launcher>

### TegraRcmSmash

+   含义：TegraRcmSmash 是 Windows 平台软件，用 C++ 重新实现 Fusée Launcher 的功能。

+   作者：rajkosto

+   软件活跃情况：已停止更新。

+   网站：
    +   已编译程序：<https://switchtools.sshnuke.net>
    +   源代码：<https://github.com/rajkosto/TegraRcmSmash>

### ChoiDujourNX

+   含义：一款在 Switch 上直接更新固件的自制软件，不会出现官方软件更新固件伴随的烧保险的情况 ([burning fuses][])。

+   作者：rajkosto

+   软件活跃情况：已停止更新。

+   网站
    +   官网：<https://switchtools.sshnuke.net>
    +   指南：<https://www.cfwaifu.com/choidujournx/>

### NXLoader

+   含义：NXLoader 是开源的 Android APP，使用了 Fusée Launcher 以及 ShofEL2 的代码，
    作用与 Fusée Launcher 相似。

+   软件活跃情况：已停止更新。
+   官网：<https://github.com/DavidBuchanan314/NXLoader>

### burning fuses

+   翻译：熔断
+   含义：Switch 的 Nvidia Tegra X1 SOC 里配有保险丝驱动器，相当于一个硬件计数器，难以修改，
    更新系统版本会熔断保险丝直到一个具体的数量，如果尝试降级到旧版系统，自检时发现熔断数量多余预定数量，
    就会无法启动。[^7a8ba]

[^7a8ba]: jonluca, [How the Nintendo Switch prevents downgrades by irreparably blowing its own fuses](https://hackernoon.com/how-the-nintendo-switch-prevents-downgrades-by-irreparably-blowing-its-own-fuses-884bd3b7a8ba), April 25th 2018.

[burning fuses]: #burning-fuses

### payload

+   含义：加载到 Switch 内存中然后运行的程序，通常以二进制文件的形式注入到已经运行的进程中，
    通常是利用 Fusée Gelée 漏洞时，用于修补 Switch OFW，使其运行 [CFW (Switch)][]。[^gwsg]

    payload 与通常的 .elf、.nro、.cxi 或其他独立可执行程序不同，并不是可独立运行的程序。

    [NXLoader](https://github.com/DavidBuchanan314/NXLoader) 主页中，fusee.bin 被称作 payload。

[payload]: #payload

### Tesla

+   含义：一套为 Switch 开发的覆盖菜单

+   作者：WerWolv

+   外部链接：[GitHub 仓库](https://github.com/WerWolv/nx-ovlloader), [GBAtemp](https://gbatemp.net/threads/tesla-the-nintendo-switch-overlay-menu.557362/).

### Mission Control

+   含义：一款在 Switch 上的自制软件，让 Switch 支持蓝牙手柄，不过目前尚未支持 BLE (Bluetooth Low Energy, 低功耗蓝牙)，比如 Xbox 固件版本较高时使用的是 BLE，所以需要降级才能正常使用。

+   作者：ndeadly

+   软件活跃情况：仍在维护。

+   网站：[GitHub 仓库](https://github.com/ndeadly/MissionControl)

### NX Activity Log

+   含义：一款在 Switch 上的自制软件，让 Switch 用户能轻松查看游戏时长。

+   自制软件类型：nro

+   作者：tallbl0nde

+   软件活跃情况：不再维护。

+   网站：[GitHub 仓库](https://github.com/tallbl0nde/NX-Activity-Log)

+   分支情况：zdm65477730 修改了 API 等程序代码，尝试让其运行在 HOS 16.0.0 版本，仍有一些 Bug，不过可以使用了：[GitHub 仓库](https://github.com/zdm65477730/NX-Activity-Log/releases)。

### deja-vu

〔待扩充〕

### SDSetup

〔待扩充〕

### Cold boot

+   翻译：冷启动

+   含义：在内存是掉电，空白的情况下启动设备。

### Warm boot

+   翻译：热启动

+   含义：在内存是运行中，存在数据的情况下启动设备。

### Signed code/Unsigned code

+   翻译：签名代码/未签名代码
+   含义：Switch 在一些时候，只能运行被任天堂签名了的代码，而未签名的代码会被拒绝执行，
    所以如果要运行 Homebrew，就需要使用漏洞绕过相关的验证，就能执行未签名代码了。[^gwsg]

### eMMC, NAND

+   含义：也许是 3DS 以及之前的任天堂游戏破解都是使用 NAND 作为存储芯片，然后开发者习惯了这种说法，
    所以 Switch 虽然使用的是 eMMC，还是会有人将其称为 NAND，二者在 Switch 的语境下可以当作同义词。[^gwsg]

### emuMMC, emuNAND

〔待扩充〕

### NRO, nro

+   含义：Horizon OS 使用的可执行文件格式，部分 Homebrew 会使用此格式，
    能够被 Horizon 和 Homebrew 启动器启动。[^gwsg]

### NSP, nsp

+   含义：Switch eshop 的游戏包格式，类似于 3DS 的 cia 以及 Wii 的 .wad 格式。[^gwsg]

### XCI, xci

+   含义：Switch 卡带的格式，类似于 3ds 控制台的 .3ds 文件。[^gwsg]

<!-- 编译后的 .elf 文件必须转换为 .nro 才能在交换机上运行。 -->

### 拆字库

+   含义：「字库」是维修手机的人对闪存芯片的俗称，因为早期手机的闪存里，主要的内容就是字库。

    所以拆字库就是拆闪存的意思，使用风枪的高温将闪存颗粒从 PCB（印刷电路板）拆下。

### 硅脂

+   含义：Switch 的硅脂（导热膏）尚不明确型号，是某种较稠的糊状物，
    [ifixit][] 给出的推荐替代品是 K5 Pro 粘性导热膏，理由是普通的导热膏不能弥合大缝隙。[^nsomh]

[^nsomh]: [Nintendo Switch OLED Model Heat Sink Replacement](https://www.ifixit.com/Guide/Nintendo+Switch+OLED+Model+Heat+Sink+Replacement/150095), ifixit.

### SwitchBrew

+   含义：SwitchBrew 是一个讨论和研究 Nintendo Switch 自制程序的 wiki，有开发环境、硬件和 API 等资料。

+   官网：<https://switchbrew.org/wiki/Main_Page>

### 〔待扩充〕

+   含义：软破、硬破、大气层、tesla、nx-ovlloader、eFuse

### Switch 相关指南网站

+   [NH Switch Guide](https://nh-server.github.io/switch-guide/)
+   [Homebrew Guide documentation](https://switch.homebrew.guide/)

## 备注

+   部分页面提及「Horizon」时，在字母 o 与 n 之间存在两个零宽空格，就像这样「Horizo​​n」，尚不明确其原因。

## 参考资料

+   Mars, 《[Switch硬件破解经验分享 - 术语篇](https://www.marsshen.com/posts/f96d7ec4/)》, Mars的博客 \| Mars's Blog, 2022-05-29. (参照 2023-06-27).
+   2023game.com, 《[switch问题自查](https://docs.qq.com/doc/DYVNDUG54V3J5V25E)》.

<!--
https://switchway.net
https://rentry.org/SwitchHackingIsEasy
https://www.cfwaifu.com/switch/
https://nh-server.github.io/switch-guide/
https://www.sdsetup.com  -->

## 脚注
