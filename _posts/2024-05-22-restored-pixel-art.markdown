---
title: 逆向还原像素画
layout: post
published: true
# header-img: "img/bg/pixiv_53864290.svg"
# header-img-object-position: 100% top
# date: '2024-05-22 00:00:00'
tags:
- 考据
description: 将被放大、压缩、缩放算法「编译」过的像素画，还原到像素点对点（1 px）的原始版本。
file-name: 2024-05-22-restored-pixel-art.markdown
---

社交媒体平台没有针对像素画（Pixel Art）优化，这使得像素艺术家不得不倍数放大，以保持像素的锐利，
防止压缩和缩放算法毁掉像素艺术。

但是社交媒体上分享的像素画，也变得难以二次编辑。就像是难以对已经编译的程序进行二次开发一样，可能需要反编译。
而被放大、压缩、缩放算法「编译」过的像素画，也能「反编译」到每个像素点对点（1 px）的原始版本。

<!-- more -->

## 算法

最简单上手，也是最有毅力的方法，是徒手重绘。不过这不现实，除非是少量重要的像素画。经过查找看到了有五种逆向像素画的算法，
分别是：

+   [Antonio Neves](https://community.wolfram.com/groups/-/m/t/2407109)

    +   基于边缘识别的检测角点

    +   傅立叶变换

        傅立叶变换这个算法比较有趣，JPEG 格式的压缩就会用到傅立叶变换，原理是图片小块的形状，能用各种波形叠出来，
        也就能得到小容量的近似图。

        因为像素画的「形状」其实是各种棱角分明的小块，所以给像素画用到傅立叶变换后，也能看到许多十字形暗带。
        而这个数据中存在像素长度与宽度信息，Antonio Neves 用算法读取到了这个信息，就能自动缩放了。

    +   分析调色板

+   victorqribeiro

    +   [pixelRestorer](https://github.com/victorqribeiro/pixelRestorer)（原理不明）

+   Astropulse

    +   pixeldetector

        原理是边缘检测，确定缩放大小因子。并使用 k 均值聚类算法来简化调色板。

## 实用性评估

victorqribeiro 的 pixelRestorer 只有演示，代码也不适合二次开发，就先忽略吧。

Antonio Neves 的傅立叶变换在他的笔记中，是最推荐的方案。但是仅有 wolfram 工具，经过不断与 GPT-4o 与 3.5 的讨论后，
总算成功移植为了 Python 版：[restored_pixel_art.py][]。不过效果与 wolfram 有差异，成功恢复的概率不高。

Retro Diffusion 这个 AIGC 的开发者 Astropulse，在研究用 AIGC 生成像素画。但是遇到了不够清晰、颜色杂乱等问题，于是
Astropulse 也编写了 Python 脚本 pixeldetector 来处理生成的图片。

pixeldetector 效果相对傅立叶变换，也许强一些。最好的方法，可能是一起使用，然后选择效果更好的吧。

## 开发新的半自动工具

以上自动化的工具总是有些问题，如果无法自动处理，还是得用半自动的工具来兜底。

脑海里出现了一个想法：标记像素画中的像素中心点，只要标记一些，然后用算法自动推理出网格，再提取网格中心的颜色，
就能还原了。

让 GPT-4o 编写，但效果不够好，所以还是换了个思路。半自动匹配网格：调整网格每个方形的边长，X 和 Y 轴偏移，
再提取网格中心点的颜色，从而还原像素画。

效果相当不错，可以用鼠标滚轮调整边长，然后鼠标拖动来偏移 X 和 Y 轴。可以在 [manual_restored_pixel_art.html][] 体验。

## 演示

下面的图片来自 ゆずたろ（[@yuzutarou0011][]）的作品[「……あげる」][]。

[@yuzutarou0011]: https://x.com/yuzutarou0011
[「……あげる」]: https://x.com/yuzutarou0011/status/1625405798661914624

| 使用的方法                                                | 示例                                                                                                                     |
| --------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------ |
| 原图<br>（13285 色、1280 px）                             | ![「……あげる」原图](<https://s3.tebi.io/ggame/ShareX/blog_restored-pixel-art_「……あげる」.jpg>)                          |
| pixeldetector.py<br>（4995 色、320 px）                   | ![「……あげる」pixeldetector.py](</img/restored-pixel-art/「……あげる」_pd.png>)                                           |
| pixeldetector.py × 2<br>（2216 色、160 px）               | ![「……あげる」pixeldetector.py × 2](</img/restored-pixel-art/「……あげる」_pd_pd.png>)                                    |
| pixeldetector.py × 2 + sd-palettize<br>（236 色、160 px） | ![「……あげる」pixeldetector.py × 2 + sd-palettize](</img/restored-pixel-art/「……あげる」_pd_pd_sd-palettize.png>)        |
| 半自动匹配网格<br>（1912 色、160 px）                     | ![「……あげる」manual_restored_pixel_art.html](</img/restored-pixel-art/「……あげる」_mr.png>)                             |
| 半自动匹配网格 + sd-palettize<br>（237 色、160 px）       | ![「……あげる」manual_restored_pixel_art.html + sd-palettize](</img/restored-pixel-art/「……あげる」_mr_sd-palettize.png>) |
| 傅立叶变换<br>（3173 色、320 px）                         | ![「……あげる」傅立叶变换](</img/restored-pixel-art/「……あげる」_restored.png>)                                           |
| 傅立叶变换 × 2<br>（681 色、80 px）                       | ![「……あげる」傅立叶变换 × 2](</img/restored-pixel-art/「……あげる」_restored_restored.png>)                              |

这个案例中，可以看出需要两次使用 pixeldetector.py，才能缩小到合适的 1 px 大小。而傅立叶变换的效果不好。

并且在转换后，最好缩小调色板的工具 sd-palettize，尽量让颜色变少，这样也能起到清理杂色的效果。

附言：png 图片有经过 pngquant 无损压缩，减少体积。

## 工具们

下面是之前提到过的工具们：

+   [restored_pixel_art.py][]：Antonio Neves 的傅立叶变换算法，作用是缩小被放大的像素画。
+   [pixeldetector.py][]：Astropulse 的缩小像素画工具，自带缩小调色板效果。
+   [sd-palettize.py][]：Astropulse 的缩小调色板工具。
+   [manual_restored_pixel_art.html][]：由 gledos 设想，GPT-4o 编写的单页网页工具。

[restored_pixel_art.py]: https://gist.github.com/gledos/aa7c98b53b8eb73670dc0462656c1a10
[pixeldetector.py]: https://github.com/Astropulse/pixeldetector
[sd-palettize.py]: https://gist.github.com/gledos/71414747e12b2077569e42bf93f152ad
[manual_restored_pixel_art.html]: http://gledos.science/tool/manual_restored_pixel_art.html
