---
title: steam在大陆网络问题的捕风捉影
layout: post
published: true
# date: '2018-07-12 20:52:00 +0800'
tags:
    - 历史
    - 游戏
description: steam在大陆网络问题的捕风捉影，是一个记录关于 Steam 在大陆包括但不限于网络的记录
file-name: 2018-07-12-wegame-steam.markdown
---
<!-- 谁杀死了Steam？ -->

这是一个历史事件的记录，可能有所遗漏，但我会尽可能的详细记录的。

<!-- more -->

虽然不太好说出口，但我还是想说我想保持中立，如果有什么我遗漏掉的**信息**，请通过电子邮箱 cngledos@gmail.com 联系我。

这里和wiki的方针一样，详细记录，保持客观、真实和公开。邮件交流的内容也可以被公开(如果您同意的话)。

~~原标题：《steam出现101、103错误与腾讯wegame的联系》。在 UTC+8 时间 2017年8月9日 写下的，因为不客观就修改了标题~~

---

目前此记录里已有大量链接失效，其中失效的网页大量是百度贴吧，原因是 2017 年以前的帖子被冻结为不可读了。

如果有网页被删除了或「自然」失效，我可能会用 [web.archive.org](https://web.archive.org/) 的网页快照替换掉原网页。

如果你想要缓存网页并作为证据，我推荐此chrome扩展 [Save To The Wayback Machine](https://chrome.google.com/webstore/detail/eebpioaailbjojmdbmlpomfgijnlcemk)。
火狐、Opera也有保存到 Wayback Machine 的附加元件，可以去这个扩展的[官网](https://github.com/VerifiedJoseph/Save-to-the-Wayback-Machine)找到。

如果 [web.archive.org](https://web.archive.org/) 无法保存防爬虫、重定向等对 archive.org 不友好的网站，可以尝试 [archive.today](https://archive.today/) 。

Emoji 前缀标识的意思

+ 红色十字交叉 ❌，表示我已经无法找到了这个网页的原页面了。
+ 锤子和扳手 🛠，表示建议使用源码模式或禁用JavaScript打开这个链接，因为这个快照中有「错误」的JavaScript，使网页不能正常的显示
+ 相机 📷，表示这个链接是图片，而不是HTML富文本之类的东西
+ 发光的星星 🌟，表示内容丰富或高重要性

主时间轴
--------

1. `2015-06-23 23:33` **帖子** [自己抓了一些高速IP - SteamCN 蒸汽动力](https://web.archive.org/web/20160507135854/https://steamcn.com/t133519-1-1)

    这是使用百度搜索引擎找到的关于 steam 在国内的 CDN 最早的侧面记录，里面提到了 8686c.com 这个属于**万网志成**下的**网宿科技**的 CDN 。

2. `2016-02-05 13:47:50` **帖子** [🛠乐山电信屏蔽cdn.akamai.steamstatic.com？ -  SteamCN 蒸汽动力](https://web.archive.org/web/20180102074626/https://steamcn.com/t165524-1-3)

    省略读标题就能知道的内容

    > 19楼:63.110.60.27我这能通，我怀疑你的那个ISP就是故意ban了steam。你只能换你那边的isp没ban的网段。。。把解析结果写入本地hosts。要不就施放魔法/或者走科学了，只能这样。

3. `2016-02-14` **行政法规** [网络出版服务管理规定](https://web.archive.org/web/20200418093136/http://www.charltonslaw.com/newsletters/china-news-alerts/cn/2016/489/9.pdf)，3月10日生效

4. `2016-02-28 09:58:48` **帖子** [【教程】在学校利用网宿教育网CDN/国外IPv6 CDN加速Steam下载 - SteamCN 蒸汽动力](https://archive.is/5o9QT "https://steamcn.com/t170155-1-5")

    省略其他不相关的内容

    > 在国内使用Steam客户端时，默认选择了中囯节点的下载服务器，域名为cdn.mileweb.cs.steampowered.com.8686c.com

5. `2016-04-08 12:08:23` **帖子** [❌8086c.com？CDN劫持还是steam的国内CDN？ - SteamCN 蒸汽动力](https://steamcn.com/t180448-1-1)

    精简后的帖子信息:
    > IP是常州电信，并且测试了换DNS并不能解决域名重定向问题
    >
    >Steam网页源代码上的域名都变了，而不是从akamai跳转过去，Valve肯定是知道的。而且只有当你是国内IP的时候才会使用这个CDN，一般只有网站自己才会做这种事情

6. `2016-04-10 00:23:25` **帖子** [steam（仅限国区）已启用8686c.com（万网）CDN，来解决移动屏蔽图片问题 - SteamCN 蒸汽动力](https://archive.is/HU43I "https://keylol.com/t180986-1-1")

    > 前情提要：8086c.com？CDN劫持还是steam的国内CDN？
    > 目前cdn.steamstatic.com的图片被导向了cdn.steamstatic.com.8686c.com。
    > 经过whois查询，8686c.com是来自万网旗下的公司的CDN（网宿科技）
    >
    > 刚开始我以为是域名劫持（这个域名实在是太可疑了，太像联通劫持404页面的样子了）。
    > 但是后来经坛子里的人提醒这串地址是嵌入网页源代码之中的，而不是跳转。
    > 经过我与一票人的实验 最后得出结论
    >
    > 国区帐号下，steam商店的图片由8686C提供
    > 其他区域帐号依然是旧版本CDN
    >
    > 于是图片服务器也分区了
    >
    > 虽然看起来有利于国内玩家，但是这个举动似乎说明了什么。。。。（G胖开始在国内黑白两道混了？）

7. `2016-05-15 12:32` 蒹葭游戏汉化组创始人、组长**改了名的哈里斯基**在**微博**上发布了一则关于steam会在国内玩不了的信息

    信息出现后不久就删除了

    + **新闻** [Steam要完了！蒹葭汉化组长爆料Steam即将被封 牛游戏网资讯](https://web.archive.org/web/20200815100548/https://www.newyx.net/news/374713_1.htm "https://archive.is/rSJK4")
    + [📷打码截图](/img/steam/93871788.jpg) [📷清晰截图](/img/steam/50218944.jpg)

8. `2016-05-02` [Steam 在中国大陆的 CDN - V2EX](https://archive.is/oRs3w)

    > 可能是我火星了。。刚刚在 Steam 的设置页面里发现了这个选项。能选择中国大陆的节点。

9. `2016-08-12` **公告** [北京翼晰科技有限公司正式收购SteamCN正版游戏论坛](https://web.archive.org/web/20200708035900/https://mp.weixin.qq.com/s?__biz=MzI1MjM5MDk5NA==&mid=2247483800&idx=1&sn=301bcde99830339dbc81aa6012f313ee)

10. `2016-11-07 19:38:21` **新法案通过** [中华人民共和国网络安全法（2016年11月7日第十二届全国人民代表大会常务委员会第二十四次会议通过）](https://web.archive.org/web/20161126211942/http://www.cac.gov.cn/2016-11/07/c_1119867116.htm)

11. `2016-12-23` **讨论帖** [惊天新闻，steam国区惨遭和谐 - 其乐 Keylol](https://archive.is/jco7k "https://keylol.com/t236512-1-1")

    <!-- 详情在《关于和谐游戏的百科与全解名鉴》有记录 -->

12. `2017-03-09之前 具体时间未知`steam群组**中国共产党**被GFW屏蔽，几天后(尚无资料)Valve关闭了这个群组并把曾经加入了群组的人上了无法暂时个人主页的黑名单。[资料来源](https://archive.vn/l1bO9 "狗胖子开始处理膜X用户，想赚中国的钱就要先向……低头。上周，万里长 https://psnine.com/gene/16956")、[时间来源](https://web.archive.org/web/20180713134641/https://tieba.baidu.com/p/5013992646?pid=105030907901&cid=0)

    > [📷主页不能展示](/img/steam/93977024.jpg) [📷该群组的主页](/img/steam/14518426.jpg)

13. `2017-04-20 21:05` **腾讯新闻** [专访WEGAME平台负责人：恢复国内游戏生态 扶植国内优质项目 腾讯网](https://web.archive.org/web/20200708032559/https://games.qq.com/a/20170420/068669.htm)

    同时间同样评论的另一个新闻标题，电脑版已删除，手机版还在：[~~WEGAME平台：恢复国内游戏生态 扶植国内优质项目~~](https://web.archive.org/web/20200708035020/https://xw.qq.com/cmsid/2017042006866900)，但是两条新闻在`2017年1月27日左右`对比后发现有一些地方文本不同。

14. `2017-04-21 11:57` **触乐新闻** [WeGame群访记录：若Steam出现服务器、支付方面的问题，绝对跟腾讯无关 - 触乐](https://web.archive.org/web/20180129133347/https://www.chuapp.com/?c=Article&a=index&id=282876)

    和上面的腾讯新闻的文本对比在这里: [diffchecker🔗](https://web.archive.org/web/20181009064019/https://www.diffchecker.com/OR6gPGjd)

15. `2017-04-07 01:56:00` **steamcn帖子** [Steam图片资源链接重定向V3 [移动/联通] - SteamCN 蒸汽动力](https://archive.is/EmeHv "https://keylol.com/t261420-1-1")

    省略帖子中手动劫持的方法

    > V社不知道发什么神经又把国内的图片CDN切换到其他域名去了(又是被移动域名关键字屏蔽的)
    >
    > 不过原来的网宿8686c还有保留,所以做了这个.将就下先

16. `2017-04-19 23:28` **NGA论坛** [[ 在此输入喷点 ] 从TGP到wegame，等待我们的会是什么？](https://web.archive.org/web/20180712025701/https://webcache.googleusercontent.com/search?q=cache:Mw80VWmcPl4J:bbs.ngacn.cc/read.php?tid=11437668)

17. `2017-04-20 19:01:53` **新闻** [腾讯谈Steam：在国内发生任何问题和我们无关](https://web.archive.org/web/20170526024043/https://www.ithome.com/html/game/305355.htm)，原3DM新闻以及IT之家的转载已经被删除，这里是 Wayback Machine 备份的IT之家的转载新闻，Wayback Machine 无法保存IT之家的评论。

    > 在经历了各种爆料预热之后，腾讯的WeGame平台在今日的UP 2017腾讯互动娱乐年度发布会上正式发表了，
    > 作为直指全球化的腾讯全新游戏平台，将于2017年7月份上线，那么同样是游戏平台的Steam会否因此受到影响呢？
    >
    > 在这之前，就有一些玩家担心WeGame的上线会否影响到Steam在国内的发展，各种推测也是层出不穷，
    > 从商业竞争的讨论上升到了阴谋论，对此腾讯方面也进行了回复。
    >
    > 腾讯公司副总裁王波表示，不管是Steam还是友商，还是更希望一起把这个领域重新恢复起来，
    > 盼望能够看到越来越多的玩家玩到更加多类的游戏，让这个蛋糕和生态越来越大。并且他还表示，
    > 有信心能够把自己该做的事情做好。最后他还发布了“官方声明”：Steam在中国出现服务器，支付等任何问题，绝对跟腾讯无关。
    >
    > 从最近的发售计划来说，官方更关注独立游戏，近期玩家们会看到一些耳熟能详的独立游戏登陆Steam。
    >
    > 腾讯方面澄清了一些玩家猜测的，因为要去发展WeGame而做出一些事情来干扰Steam，
    > 而Steam日后在国内可能会出现的问题也是和腾讯无关的，腾讯会努力搞好自己的平台，而不是去“使绊子”阻碍别人来达到自己的目标。

18. `2017-05-01 20:53` **新闻** [【图说天朝】steam上不得擅自成立党支部](https://web.archive.org/web/20200419061247/https://chinadigitaltimes.net/chinese/2017/05/【图说天朝】steam上不得擅自成立党支部/)

    里面讲述了steam上的一些组早已被墙了，steam采取了措施关闭了违规的群组

19. `2017-05-04 19:39` **steamcn帖子** [【Steam已修复该问题】Steam图片资源链接重定向V3 [移动/联通] - SteamCN 蒸汽动力](https://archive.is/EmeHv "https://steamcn.com/t261420-1-1")

    Steam CDN 被移动域名关键字屏蔽这个问题已修复。

20. `2017-05-20`101、103错误开始在贴吧出现，不过还很少量

21. `2017-06-01 11:03:25` **法案生效** [《中华人民共和国网络安全法》6月1日起实施](https://web.archive.org/web/20170811171714/http://www.cac.gov.cn/2017-06/01/c_1121068451.htm)

22. `2017-06-05` 101、103、105错误开始在贴吧里陆续出现

23. `2017-06-07 01:49` **贴吧** [关于近日steam访问异常的简单解决方案](https://archive.is/Yfhcb "http://tieba.baidu.com/p/5150230370")

    >通过这两天的观察，部分dns服务（比如某些电信，某些联通，某知名dns114）不再正常解析steam域名，并且有扩大的趋势。
    >
    >但目前ip还没有被封，在不使用魔法上网的情况下暂时还可以通过修改dns处理。
    >
    >...省略解决办法....
    >
    >实际上不正常的dns也能得到一个ip地址，但这个地址会“连接被重置”，这和谷歌是一个套路的。所以??
    >
    >14年16年都发生过，这次呢（这次多了wegame啊）。
    >
    >[如何查看自己的steam是否被放逐📷](/img/steam/26980862.jpg)

24. `2017-06-08 08:46` **帖子** [steam是不是已经遭到了屏蔽？](https://web.archive.org/web/20190409175013/http://bbs.3dmgame.com/thread-5592941-1-1.html)

    > 今天上steam就发现很多商店页面的cdn都遭到了connection reset。
    >
    > 我北方某城电信线的，已经测试如下的ip都ban掉了，第一下可能还能连，后续都没戏。
    >
    > _6楼_:江苏的，问了这边的电信客户经理，应工信部新政策要求，许多服务商需要提供各类资质证明，没提供的一律封

25. `2017-06-15 14:28` **贴吧** [❌ 关于103的问题，看了那个帖子，我又上去看了一下](https://tieba.baidu.com/p/5164174953)

    帖子认为是一个鉴赏家的名字被拦截了，浏览就会阻断steam的所有域名

    > _9楼楼中楼补充道_:一个IP段都会遭殃，持续90秒
    >
    > 12楼: 不错，操作太慢这个解释可以接受。但我觉得还是有个疑点。论坛有人反应4月份那个鉴赏家就会造成103，为什么等这么久才大规模爆发。
    >
    > 18楼: [被阻断动图📷](/img/steam/65245738.jpg)

26. `2017-06-15 17:14` **贴吧** [【图片】【重发】关于Steam 101，103的原因【steam吧】](https://web.archive.org/web/20180107101922/https://tieba.baidu.com/p/5164457265)

    > 一张图说明问题
    >
    > 实际上就是有人作死，触发了敏感词，然后和那个人周围的IP全部遭罪，因为Store是Http的，所以会出事。
    >
    > 举报掉下划红线的那位可能这次就结了（要爬出去举报）
    >
    > 顺便其他人也要引以为戒，不要再闹点事情出来。

27. `2017-06-16前` 关闭腾讯软件就能够连接上steam这一消息被较为广泛的传播(黑桐谷歌也发微博传播)

    _有人确认了这可行，也有人确认了这不可行。_

28. `2017-06-16 10:50` **帖子** [【吧务组】暂时禁止关于steam错误的个人主题贴](https://web.archive.org/web/20180724034605/https://tieba.baidu.com/p/5165583121)

29. `2017-06-22` **公告**&**新闻** [巨头抢滩百亿红利 网宿卡位力推VR承载平台](https://web.archive.org/web/20200419065247/https://www.wangsu.com/content/details45_2756.html) 最后一段首次(我还没有找到更早的官方资料)公开网宿和 steam 合作，而且说法还有保留。[中国网](https://web.archive.org/web/20200419065300/http://finance.china.com.cn/industry/20170622/4259141.shtml)

    > 事实上，早在2016年8月，CDN行业龙头网宿科技在CDN下载产品中已经新增VR套餐，专为VR内容提供下载加速服务。
    > 通过专有下载私有传输协议、防劫持、防篡改等多种安全策略以满足VR游戏快速、安全的分发需求。
    > 目前，全球范围内包括HTC、steam等多家知名VR游戏及分发平台均为网宿客户。

30. `2017-06-26 20:57` **帖子** [关于最近steam老是错误101 103.. （应该正确）解决方案 - steam吧](https://archive.is/BUf0Y "https://tieba.baidu.com/p/5162665305")

    > 28楼:可以试试在103后右键返回，你会发现你的网址是多跳了一次。

    *有15条回复都是称赞或者实验成功了的*

31. `2017-06-26 23:02:51` **帖子** [【科普】101、103、105意味着什么 - SteamCN 蒸汽动力](https://archive.is/ "https://keylol.com/t284467-1-1")

    里面详细的描述了错误代码101、103、105的区别和 DNS 是否能对错误带来帮助。

32. `2017-07-14 21:20:52` **图片** [❌ 恶意高流量的敏感链接导致steam继续被封锁](https://keylol.com/forum.php?mod=viewthread&tid=280638&page=10#pid4457536),[几乎无用的backup](https://archive.is/sntzf

33. `2017-07-21 16:13` **贴吧** [❌ steam 10X错误解决办法，忍无可忍再发一帖](https://tieba.baidu.com/p/5235680550)

    原帖已被删除，但还是能够被证实这篇帖子存在并且内容无误：[【SteamCN 蒸汽动力的转帖】](https://archive.is/4MMHT)

    > 吧里各种解决办法满天飞，包括置顶帖的，没一个说到点上。
    >
    > 由于众所周知的原因，网宿科技CDN不再为大陆提供steam网页加速服务，6月初国内steam IP都解析到了Akamai CDN上，
    > 然而Akamai CDN IP被干扰不是一天两天了。DNS解析的原则是解析到响应最快的IP上，但这些IP有很大几率被干扰，表现就是商店打不开，如下图所示，这些ip会导致10X。
    >
    > 不同ISP不同地区对Akamai CDN干扰情况不同，修改hosts工具提供的IP可能张三能用，李四不能用，或者A时间可以用，
    > B时间又不能用的情况。因为对IP的干扰不是持续，而是断断续续。
    >
    > 根本解决10X的办法还是挂梯子，因为你不能保证改hosts的这个IP永远不会被干扰。或者更简单办法，这里有个小工具，
    > 改hosts之前先检查下这个IP你那里是否可用，连续测试10次，如果某个ip测试期间都没被干扰，可视为稳定IP，填入hosts即可，如下格式：
    >
    > 23.63.219.132 store.steampowered.com ; 23.63.219.132 steamcommunity.com
    >
    > 改hosts有可能造成个人资料卡在验证登陆状态，SSL证书原因，重启下steam即可。
    >
    > 最后特别声明：感谢小工具原作者，他曾经发过类似的帖子但石沉大海，借花献佛再次把这个小工具拿出来。

34. `2017-07-21 21:48` **记录** [关于steam当前情况的一些整理 - 游戏论坛 - Stage1st - stage1/s1 游戏动漫论坛](https://web.archive.org/web/20170724000251/https://bbs.saraba1st.com/2b/thread-1532481-1-1.html)

    内有比较模糊的一些记录，以及网络测试

35. `2017-07-23 17:31` **贴吧** [【吧务组通告】对于近期删除10X,1xx错误部分相关贴公告](https://archive.is/YsMMA "https://tieba.baidu.com/p/5239340529")

    > 7楼楼中楼: 我狂点 商店 然后就好了

    *有10个人回复10个人成功了*

36. `2017-07-26 13:29` **讨论帖** [关于最近传的很疯的知乎某大v号称steam要被墙的言论 - 游戏论坛 - Stage1st - stage1/s1 游戏动漫论坛](https://archive.is/44VlH "https://bbs.saraba1st.com/2b/forum.php?mod=viewthread&tid=1533372")

37. `2017-07-30 12:25:08` **帖子** [聊聊101,105问题 - SteamCN 蒸汽动力](https://archive.is/49XIJ "https://keylol.com/t293805-1-1")

38. `2017-07-30 22:57` **贴吧** [关于近日steam访问异常的简单解决方案](https://archive.is/vD5tV "https://tieba.baidu.com/p/5150230370?pn=2")

    > 56楼: 主要还是akamai的分包服务主要服务于油 管和脸 书，导致污染严重波及steam。之前国内为steam提供加速分包的公司突然翻脸不干了，其它的就不多说了……

39. `2017-08-07 18:49` **触乐网**发布了[微博](https://archive.is/S9F5N "https://weibo.com/3957040489/Fg1hVbztX")

    > 在最新一期的英国游戏杂志《Edge》上，知名游戏记者Simon Parkin发表了一篇名为《东诺》（Eastern Promise）的文章，
    > 其摘要是“一场争夺世界上最大、变化也最快的PC游戏市场的战争”。
    > 文章第一段，作者爆料一位腾讯高级经理曾在2016年11月上海的《最终幻想15》发布会后向某国内游戏开发者透露：“等到时机成熟，Steam在中国将不复存在。”
    >
    > [图1](/img/steam/69444902.jpg) [图2](/img/steam/61188460.jpg) [图3](/img/steam/34063224.jpg)

40. `2017-08-08 14:32` **腾讯WeGame**发布了[微博](https://archive.is/Qkp74 "https://archive.is/Qkp74")

    >早上听说有外国友人提到，WeGame 有人在去年 FF15 发布会现场爆了个什么料，一脸懵逼赶紧自查，发现我们确实没人去过，害的老板怀疑我们偷着去玩[抓狂]！话说 WeGame 一直倡导公平竞争，玩家的游戏体验才是我们最关注的，所以给开发商的分发标准分成其实是 70%，就是要激励大家提供更好的游戏。至于有人猜测的那些离谱手段，我们真心不搞这些#[左哼哼]#[右哼哼]。有问题尽管找 G 哥，这里有不匿名的靠谱信息#[二哈]。

41. `2017-08-10 11:13` **新闻** [腾讯投资《绝地求生：大逃杀》开发商Bluehole 为引入中国做准备](https://web.archive.org/web/20200419061649/https://www.jiemian.com/article/1538312.html)

42. `2017-08-10 16:33:56` **新闻** [那篇腾讯要墙Steam的爆料，这里有全文](https://web.archive.org/web/20200419061642/https://ent.163.com/game/17/0810/16/CRG8R2LB00318QE8.html)。

43. `2017-08-17 04:06:09` **帖子** [101/103已解除???不可描述的阻断似乎已经解除?](https://archive.is/gie4S "https://keylol.com/t299518-1-1")

    > 目前全国GET统统都是正常的..当然不排除是某个设备突然抽风了..
    >
    > 这是水区,我说话可不负责哈,没准明早起来又
    >
    > 出现 102 问题的打开hosts，找到steam的相关字段，删掉就可以了
    >
    > 5楼回复:目测大范围解除了，就算遇到关键词也不再会短暂性阻断

44. `2017-11-01` 钢铁雄心4在 steam 国区被下架

    + 由于价格也删除了，所以无法使用Sub大法进行购买[^311712]
    + [Hearts of Iron IV removed from Steam in China Paradox Interactive Forums](https://web.archive.org/web/20200702105900/https://forum.paradoxplaza.com/forum/threads/hearts-of-iron-iv-removed-from-steam-in-china.1052971/)
    + [P社回应钢铁雄心4锁区：不是我们的锅_网易游戏](https://web.archive.org/web/20200821042211/https://ent.163.com/game/17/1103/11/D2AJPUG200318T0C.html)
    + [关于《钢铁雄心4》Steam锁区 P社相关解释疑点重重](https://web.archive.org/web/20200821042248/https://www.sohu.com/a/205165705_119620)

45. `2017-11-26` **知乎** [华中科技大学校园网限制steam的下载](https://web.archive.org/web/20200826082327/https://www.zhihu.com/question/68631319)

    >从贴吧里的反应来看，应该是彻底的封禁了steam。[链接1](https://web.archive.org/web/20180106220243/http://tieba.baidu.com/p/5450503489),[链接2](https://web.archive.org/web/20180106220246/http://tieba.baidu.com/p/5450646499)

46. `2017-11-28` **报告** [2017年中国游戏行业发展报告](https://web.archive.org/web/20190820125533/http://www.cnccea.com/index.php?m=newscon&id=408&aid=770) 由[中国文化娱乐行业协会](https://web.archive.org/web/20200616171446/http://www.cnccea.com/index.php?m=newscon&id=411&aid=596)信息中心与中娱智库联合课题组编撰。

    稍微介绍一下这个**中国文化娱乐行业协会**，*信息详细在* [*中国文化娱乐行业协会简介*](https://web.archive.org/web/20200616171238/http://www.cnccea.com/index.php?m=content&id=402)

    > 中国文化娱乐行业协会是由民政部登记管理，文化部业务主管，公安部支持的国家一级协会。发起单位包括万达文化产业集团、
    > 小米、腾讯、网易、搜狐、联想、温莎、好乐迪、世宇、希力、大玩家、雷石、视易以及各省、市级行业协会等最有代表性的上百家文化机构，
    > 涉及歌舞娱乐场所、游戏机经营场所、网络游戏、手机游戏、家庭娱乐、室外游乐园、会展、文化娱乐内容技术服务等多个业态，涉及文化娱乐行业全产业链。

    ......后略

47. `2017-12-16 12:03:37` **讨论贴** [❌ Steam社区页遭域名污染+HTTP连接重置双重封锁](https://steamcn.com/t339379-1-1)

48. `2017-12-19 11:31` **新闻** [Steam社区/个人资料等界面被屏蔽 但有简便解决方案](https://web.archive.org/web/20201231075040/https://www.ali213.net/news/html/2017-12/337053.html)

49. `2017-12-19 13:10:44` **新闻** [Steam Community access has been blocked in China](https://web.archive.org/web/20201112031818/https://www.pcgamer.com/steam-community-access-has-been-blocked-in-china/)

50. `2017-12-19` **讨论贴** [G胖疑似自我阉割了[国区]论坛功能](https://archive.is/M5ILs "https://keylol.com/t340304-1-1")

    > 今天(12月19日)早上我尝试进入steam社区的论坛版面，无论如何都进不去，包括用魔法。
    >
    > 换浏览器、取消hosts都无效。
    >
    > 效的是登录我的美小号，或者退出登录。
    >
    > 论坛版面与国区账户无缘了。这个可能是我的个例，楼下的你们能打开吗？

51. `2017-12-22` **整合贴** [❌ 近期Steam无法打开社区、库存页面，出现错误代码101、110、113、118等解决办法](https://steamcn.com/t342004-1-1) [这是一份转载](https://web.archive.org/web/20201231074530/https://cloud.tencent.com/developer/news/50185)

52. `2017-12-23 16:08:49` **网络测试** [17CE上的对cdn.steamcommunity.com在陆网络测试](https://web.archive.org/web/20180107162715/http://www.17ce.com/site/http/201712_7b17c36238fa05f8abbaed8024760229.html)

53. `2017-12-24 14:42` **讨论贴** [steam是这样回复我的，谁给我解释解释，我感觉说的好含糊啊 - Steam吧](https://web.archive.org/web/20201231080231/https://tieba.baidu.com/p/5490856537)

    >[与客服交流的图片📷](/img/steam/28680806.jpg)

54. `2018-01-22 22:43:33` **行动通告** [北京启动网络游戏专项整治行动](https://web.archive.org/web/20180123054854/http://www.xinhuanet.com/legal/2018-01/22/c_1122297489.htm)

55. `2018-01-24` **软件** *Tower Accelerator* 在 steam 上发行(现已下架)

56. `2018-01-27 03:15` **新闻** [网络游戏究竟应该靠什么赢得未来](https://web.archive.org/web/20180127115641/https://news.gmw.cn/2018-01/27/content_27473422.htm)，大多重量级的网媒在一天内发布了。

    关于这篇新闻及其来源的细节:
    + 新闻里的配图的创作公司是 [EG365](https://web.archive.org/web/20191224002544/https://eg365.cn/aboutus)，官网里看起来不像普通人可以使用的配图服务。
    + [山东师范大学齐鲁文化研究院](https://web.archive.org/web/20180120031543/http://www.qlwh.sdnu.edu.cn/)在2018年01月16日的下午成立了[齐鲁文化研究院新闻宣传小组](https://web.archive.org/web/20200821032013/http://www.qlwh.sdnu.edu.cn/info/1038/1244.htm)
    + `山东师范大学齐鲁文化研究院` + `网瘾` 关键词的新闻
        + `2013-04-18` [山师大教授耗时十余年科研 戒除网瘾获突破进展 齐鲁网](https://web.archive.org/web/20131105040349/http://news.iqilu.com/shandong/yuanchuang/2013/0418/1506271.shtml), [一个有趣的软件网站也转载了该文章——绿色同年，看起来是绿坝的同类软件](https://web.archive.org/web/20200821032554/http://child.rksec.com/media/6826.html)
    + `数字艺术哲学研究` + `低碳` 关键词的新闻
        + `2014-11-14` [国家社科项目“数字艺术伦理学研究”研讨会在我校举办 - 山东师范大学 新闻网](https://web.archive.org/web/20200508145647/http://www.qlshx.sdnu.edu.cn/page.jsp?urltype=news.NewsContentUrl&wbtreeid=10445&wbnewsid=95767)
        + `2015-06-07 16:32` [数字艺术哲学研究智库落户山东师大 首创低碳艺术理论--山东频道--人民网 山东频道](https://web.archive.org/web/20200821034021/http://sd.people.com.cn/n/2015/0607/c172848-25151845.html)
    + 以**山东师范大学齐鲁文化研究院**的名义在近年发表的关于戒网瘾的新闻:
        + `2015-06-10` [首家数字艺术哲学研究智库落户山东师大 中国网·新山东](https://web.archive.org/web/20200508145631/http://sd.china.com.cn/a/2015/jykj_0610/240272.html)
        + `2017-12-07` [马立新 刘中锦：实施数字艺术通识教育很有必要 人民政协网](https://web.archive.org/web/20200508145733/http://www.rmzxb.com.cn/c/2017-12-07/1893042.shtml)
          + 本文为[国家社科基金](https://web.archive.org/web/20200821035826/https://baike.baidu.com/item/国家社会科学基金)项目“数字艺术哲学研究”和“数字艺术伦理学研究”阶段性成果
    + 作者之一的**马立新**教授发表的数篇网瘾相关的报刊:
        + `2007年4期` [论网络游戏的本体特征 - 《山东师范大学学报》](https://archive.is/18W3r "http://d.wanfangdata.com.cn/periodical/sdsdxb-rwshkxb200704002")
        + `2013年5月10日` [论数字艺术德性生成机制 - 《理论学刊》](https://archive.is/VSYZh "http://d.wanfangdata.com.cn/periodical/llxk201302025")
        + `2013年5期` [《易经》哲学与当代低碳文化建设 - 《广东社会科学》](https://web.archive.org/web/20200508145539/http://www.cqvip.com/qk/80603x/201305/47188678.html)
        + `2014年5月` [高碳网络文化的危害、成因与管控 - 《上海师范大学学报》](https://web.archive.org/web/20180128065246/http://qktg.shnu.edu.cn/skb/ch/reader/create_pdf.aspx?file_no=201403017&year_id=2014&quarter_id=3&falg=1)
        + `2015年7月` [高碳艺术精神损害研究 - 《上海师范大学学报(哲学社会科学版)》](https://web.archive.org/web/20180128065328/https://qktg.shnu.edu.cn/skb/ch/reader/create_pdf.aspx?file_no=201504013&flag=1&journal_id=shsfqksskb&year_id=2015)
        + `2017年7月` [论数字艺术生产义务的量变与质变 - 《上海师范大学学报(哲学社会科学版)》](https://web.archive.org/web/20200821033315/http://qktg.shnu.edu.cn/skb/ch/reader/create_pdf.aspx?file_no=201704015&flag=1&journal_id=shsfqksskb&year_id=2017)

57. `2018-01-31` **帖子** steam 社区网页显示 **您的网站暂时无法访问**

    + [🛠STEAM市场被工信部关闭？](https://web.archive.org/web/20180713135005/https://steamcn.com/t355700-1-1)
    + [手机steam这是玩完了？？？已用UU加速。](https://web.archive.org/web/20180131074239/https://tieba.baidu.com/p/5535223095)
    + [你们的steam有这样么](https://web.archive.org/web/20180131074252/https://tieba.baidu.com/p/5535178758)
    + [这是什么情况?](https://web.archive.org/web/20180131074312/https://tieba.baidu.com/p/5535236915)

    似乎是都是用了网易UU加速器才出现这样的错误，搜索引擎上查询了一下文字，并没有没得到有价值的信息

58. `2018-02-03` **软件** [Tower Accelerator](https://web.archive.org/web/20200821041010/https://steamcommunity.com/app/758670/discussions/0/1699415798765578829/) 在 steam 上被下架

59. `2018-02-10 19:30` **新闻** [专家：青少年登录境外游戏服务器严重 应尽快纳入国内监管体系](https://web.archive.org/web/20181108213803/http://society.people.com.cn/n1/2018/0210/c1008-29817234.html) [keylol 其乐讨论帖](https://archive.vn/mQ6H8 "https://keylol.com/t360358-1-1")

    **gledos注: 虽然内容很长，但文章似乎有几分重量**

60. `2018-02-11 下午` **知乎** 需登录 [如何看待人民网发文《青少年登录境外游戏服务器严重，应尽快纳入国内监管体系》？](https://www.zhihu.com/question/267002275)

    参与讨论的人数超过1000，[剽窃镜像站爬取的这个问题](https://archive.is/nwAH0)

61. `2018-05-09 21:55:13` **IT之家** [Steam 测试版新增 6 个国内节点：包括青岛、乌鲁木齐等城市 - Steam,青岛,乌鲁木齐 - IT之家](https://archive.is/RIO6H "https://www.ithome.com/html/game/359116.htm")

62. `2018-05-28 17:24` **贴吧** [6.1【教程】国内 Steam社区 / 商店 报错及打不开的解决方法](https://web.archive.org/web/20180711132403/https://tieba.baidu.com/p/5720575784) 吧主发帖。2018年7月11日进行了顶置

63. `2018-06-12` **新闻** 完美世界宣布与Valve合作推出Steam中国版

    + [Valve 宣布与完美合作，Steam 将正式进入中国 - Valve,Steam - IT之家](https://archive.vn/Qnq1E "https://www.ithome.com/html/game/364421.htm")
    + [Valve will officially launch Steam in China](https://www.theverge.com/2018/6/11/17451484/steam-china-announced-valve-perfect-world)
    + [完美世界：宣布与美国Valve成立“STEAM中国”项目](https://www.ithome.com/html/it/364433.htm)
    + [全球最大VR发行平台Steam正式进入中国，与完美世界合作](http://www.sohu.com/a/235248684_213766)
    + [完美世界获Valve授权 在中国大陆运营及推广Steam中国](https://cn.reuters.com/article/perfect-world-valve-china-business-0612-idCNKBS1J8049)
    + [Valve宣布与完美中国达成合作 将正式推出Steam中国版](https://tech.sina.com.cn/roll/2018-06-12/doc-ihcufqih5876894.shtml)
    + [完美世界与美国Valve宣布“STEAM中国”项目](http://www.nbd.com.cn/articles/2018-06-12/1225220.html)
    + [央视报道完美世界Steam中国项目](http://www.chinanews.com/business/2018/06-14/8537646.shtml)
    + [Valve 联手完美世界推出「中国版」Steam](https://cn.engadget.com/2018/06/12/steam-china/)
    + [潜力是3100万活跃玩家！完美世界联合V社上线Steam中国版](http://www.sootoo.com/content/676117.shtml)
    + [中国文创引进来走出去添新平台](http://tv.cntv.cn/video/C10616/3bd40bdd9ba548358b0b8a148403a381) [全文](http://user.guancha.cn/main/content?id=21422&comments-container)如下
        > 中美两国文化企业12号宣布启动战略合作，将共建游戏娱乐平台，引进全球精品游戏，同时中国游戏也将通过该平台拓展海外市场。
        >
        > 此次与中国企业合作的美国Steam游戏平台拥有全球两万多家游戏开发商提供的游戏产品，是世界上最大的数字娱乐分销平台。
        > 按照战略协议，将由中国企业完美世界建立平台，并被授权使用Steam商标，按照中国游戏产品上线流程，从平台挑选游戏，
        > 申报版号及备案，接受监督，让海外游戏健康有序，服务中国市场。
        >
        > 今年上半年，中国游戏收入超过1000亿人民币，继续占领全球最大市场地位。据游戏产业专业分析数据伽马数据统计，
        > 截止到去年年底，中国正式审批，获得版号的游戏，一共9800款，但是实际上还有大量的游戏处在监管真空或模糊地带，
        > 也影响游戏产业发展秩序。
        >
        > 中国游戏产业报告分析师滕华表示：“在国外的游戏平台上面，聚集着大量的中国玩家，而这些中国玩家接触到的，
        > 跟正在玩的游戏远远超过了9800款，大概有2万多款。”
        >
        > 专家认为，这一平台的建立对游戏产品和产业管理模式而言，是一个管理创新，实现了更有效、更科学监管。
        > 另一方面，中国游戏可以借助这一平台更好地与国际接轨，实现中国游戏更好地走出去，帮助中国中小游戏研发企业拓展海外市场。
    + **讨论** [Valve：Steam中国版不会对玩家已有游戏产生影响 - vgtime.com](https://archive.vn/VvEPE "https://www.vgtime.com/topic/951090.jhtml")
    + [关于Steam中国锁区，Steam的官方回复怎么说？ VR陀螺](https://archive.vn/45g7R "http://k.sina.cn/article_6012711797_16662b37500100a2sl.html")

64. `2018-06-13` **CCTV** Steam 被央视点名表扬

    +[中国玩家的福音：央视宣传steam中国版，力求按中国游戏上线流程，让海外游戏健康有序服务中国市场](https://web.archive.org/web/20180615073029/https://www.bilibili.com/video/av24829932/)
    +[Steam这么“黄暴”的平台，竟然上央视了？这是单机游戏的机会还是末日？ - 知乎](https://archive.vn/zwtbN "https://zhuanlan.zhihu.com/p/38057639")

65. `2018-06-14 13:53` **财经新闻** [Steam中国的背后：完美与Valve的挑战](https://archive.vn/32B7a "https://www.tfcaijing.com/article/page/2c91219663dce09a0163fc29810c5bac")

66. `2018-07-10` **贴吧** 101错误开始蔓延到一部分玩家的商店主页

67. `2018-07-31 14:08` **新闻** [Steam中国开始招聘员工！惨遭玩家怒喷：滚出中国！](https://web.archive.org/web/20200527123526/https://www.sohu.com/a/244361654_100191223?sec=wd)

    内有Steam中国招工信息与帕斯亚科技对Steam中国的认识

68. `2018-07-10 至 2018-07-14` **贴吧** 讨论帖收集，许多用户开始首次遇到打不开市场的问题

    + [今天大家是不是都steam打不开了？网页和软件都打不开了！](https://web.archive.org/web/20180710124939/https://tieba.baidu.com/p/5789930101)
    + [今天服务器是不是又炸了、、、](https://web.archive.org/web/20180710124754/https://tieba.baidu.com/p/5789953505)
    + [为什么你们steam商店进不去了，但是我进得去啊](https://web.archive.org/web/20180710124509/https://tieba.baidu.com/p/5789660785)
    + [商店进不去啊，好几天了，开加速器也只能进进个人主页，](https://web.archive.org/web/20180710124342/https://tieba.baidu.com/p/5789810337)
    + 11日
    + [steam炸了？ 开加速器也没用？](https://web.archive.org/web/20180711132630/https://tieba.baidu.com/p/5791371399) *错误代码: 102*
    + 12日
    + [TX上架围攻了，有中文的](https://web.archive.org/web/20180712024152/https://tieba.baidu.com/p/5791875321)
    + [steam怎么商店也进不去了。开了置顶软件。难道真的凉了么。](https://web.archive.org/web/20180712022657/https://tieba.baidu.com/p/5791892218)
    + [今天才知道steam中国的消息，来贴吧看看似乎没什么风头，是大家都等着看，还是有什么好消息？](https://web.archive.org/web/20180712022813/https://tieba.baidu.com/p/5791876707)
    + [装了Wegame Steam商店就显示103](http://web.archive.org/web/20180712023444/https://tieba.baidu.com/p/5791881116)
    + 14日
    + [steam不能创建账户了吗？](https://web.archive.org/web/20180714064205/https://tieba.baidu.com/p/5794821414)
    + [steam 商店打开，有大佬知道怎么解决吗](https://web.archive.org/web/20180714063924/https://tieba.baidu.com/p/5794763528)
    + [不用加速器steam市场就打不开怎么办？](https://web.archive.org/web/20180714060529/https://tieba.baidu.com/p/5794560012)
    + [错误代码101怎解决？](https://web.archive.org/web/20180714050551/https://tieba.baidu.com/p/5151618796)

69. `2018-10-30 11:48` **新闻** [刚刚！Steam中国北京运营开启，Steam中国真的来了！游戏](https://web.archive.org/web/20200527123521/https://www.sohu.com/a/272143651_535013)

70. `2019-08-21` **新闻** [🌟 Valve talks Steam China, curation and exclusivity • Eurogamer.net](https://web.archive.org/web/20201220032923/https://www.eurogamer.net/articles/2019-08-21-valve-talks-steam-china-curation-exclusivity)

    > In fact, Valve isn't sure itself. Eurogamer spoke to Valve's DJ Powers, who works in the company's business development team, at the event to try and get a better sense of what exactly is going on. As you'll read it's pretty clear even Valve can't explain - or maybe more accurately, can't say - what's going to happen to the international version of Steam out in China. Nor, for that matter, can the company say what'll happen to the accounts and property of tens of millions of Chinese players, who may or may not be able to access the international version of Steam once the official Chinese version goes live.
    >
    > ......
    >
    > And there's an expectation as well that companies will sort of "self-regulate" in a way. I think Tencent is an example where it implemented time limits for younger players off its own back, before government regulation came in. Will you consider self-regulating certain things as well?
    >
    > Powers: There's just policies and laws in place that we have to follow, so yeah, we'll adhere to all of those.
    >
    > ......
    >
    > What if I own a game on Steam as-is, that isn't on Steam China at launch?
    >
    > Powers: Nothing'll change about Steam global.
    >
    > So Steam global will still be available in China?
    >
    > Powers: Nothing'll change about Steam global.
    >
    > Okay, could something external prevent Steam global from being available in China?
    >
    > Powers: I mean, anything, yeah. There's always externalities you can't control. But the direction we're headed is that Steam global remains as it is today.

    机翻润色

    > 事实上，Valve自己也不确定。Eurogamer在活动中采访了Valve的DJ Powers，他在公司的业务开发团队工作，试图更好地了解到底发生了什么。正如你所读到的那样，很明显，即使Valve也无法解释或许更准确地说，是无法说清Steam在中国推出的国际版会发生什么。同样，公司也无法说清数千万中国玩家的账号和财产会发生什么，一旦中文版正式上线，这些玩家可能会或无法访问国际版Steam。
    >
    > ......
    >
    > 而且也有一种期待，希望公司能在某种程度上进行 "自律"。我觉得腾讯就是一个例子，在政府监管进来之前，它就对年轻玩家实施了时间限制，不在自己的背后。你也会考虑在某些事情上进行自律?
    >
    > Powers: 我们必须遵守的政策和法律，所以是的，我们会遵守所有这些。
    >
    > ......
    >
    > 如果我在Steam上拥有一款原封不动的游戏，但却没有在Steam中国上线，怎么办？
    >
    > Powers: Steam global 的情况不会改变
    >
    > 所以 Steam global 还能在中国使用？
    >
    > Powers: Steam global 的情况不会改变
    >
    > 好吧，会不会有什么外在的东西阻止了 Steam global 在中国的使用？
    >
    > Powers: 我的意思是，是的。总是存在无法控制的外部性。 但是我们前进的方向是，Steam global 仍然保持今天的状态。

71. `2019-08-21` **IT之家** [蒸汽平台首批上线游戏达 40 款，含《DOTA2》《刀塔霸业》 - Steam,V社,完美世界 - IT之家](https://archive.is/1dP5k "https://www.ithome.com/0/440/351.htm")

72. `2019-08-22` **新闻** [中國玩家還能翻牆玩嗎？Valve：一切依法行政 電競 新頭殼 Newtalk](https://web.archive.org/web/20200821030708/https://newtalk.tw/news/view/2019-08-22/289090)

73. `2019-08-22` **新闻** [不用再辛苦翻牆！中國版Steam「蒸汽平台」即將登場 電競 新頭殼 Newtalk](https://web.archive.org/web/20200527202753/https://newtalk.tw/news/view/2019-08-22/289036)

74. `2019-11-11 09:43` [严格控制未成年人使用网络游戏时段、时长_服务信息_中国政府网](https://web.archive.org/web/20200609171539/http://www.gov.cn/fuwu/2019-11/11/content_5450800.htm) [archive.is](https://archive.is/46U3p)

75. `2020-04-26 02:13:11` **讨论帖** [蒸汽平台或有望在2020年面世？ - 其乐 Keylol](https://archive.is/uA3tG "https://keylol.com/t588262-1-1")

76. `2020-04-27 17:07:43` **转载** 蒸汽平台或有望在2020年面世？

    + [终于来了！Steam国服域名曝光：玩游戏不掉线了？](https://web.archive.org/web/20200814044525/http://www.bajieyou.com/new/7b2f9fd4057645949e7fbe87eaa3075b),
        [新浪网](https://web.archive.org/web/20200508143013/https://k.sina.com.cn/article_5061312402_12dad7f9202700sy1i.html)
    + [蒸汽平台或有望在2020年面世 NGA玩家社区](https://archive.is/OpCGR "https://ngabbs.com/read.php?tid=21472536")
        > 蒸汽平台或有望在2020年面世？
        >
        > 社区坛友@清靈語 发现了完美世界所拥有的蒸汽平台相关域名和证书，其中wmsjsteam今年2月份取得了证书，并被Valve所拥有。
        > 此外坛友zxrzy也发现这些域名今年4月初都已过审，以及去年12月份获得软著的完美世界对战平台，支付网关，神秘商店，电子竞技App.
77. `2020-05-05` 完美世界的蒸汽平台的强制全屏 5 秒 《健康游戏忠告》

    + `2020-05-05 12:06 編輯` [蒸汽平台会强制全屏 5 秒《健康游戏忠告》](https://archive.vn/GaFoT "https://keylol.com/t592086-1-1")
    + `2020-05-06 19:15 編輯` [蒸汽平台会强制全屏 5 秒《健康游戏忠告》](https://archive.vn/XYbqf "https://keylol.com/t592086-1-1")
    + `2020-05-08 15:16 编辑` [蒸汽平台会强制全屏 5 秒《健康游戏忠告》](https://archive.vn/7QKHo "https://keylol.com/t592086-1-1")
    + `2020-07-20 18:54 编辑` [蒸汽平台会强制全屏 5 秒《健康游戏忠告》](https://archive.is/lmpFL "https://keylol.com/t592086-1-1")
    + PTT上的讨论 [Fw: [閒聊] 中國的蒸汽平台會限制遊戲時間 - 批踢踢實業坊](https://web.archive.org/web/20200508143401/https://www.ptt.cc/bbs/Steam/M.1588677634.A.C96.html)
78. `2020-05-19` steam 中国客户端α版风波

    + [Valve quietly releases censored Steam China client to alpha - CS:GO - News - WIN.gg](https://archive.fo/Yc4dX "https://win.gg/news/4554/valve-quietly-releases-censored-steam-china-client-to-alpha")
        + 中文标题可能会被翻译为《V社悄然推行STEAM中国客户端α版》
    + [🌟 如何看待文章《V社悄然推行STEAM中国客户端α版》？ - 知乎](https://web.archive.org/web/20200820142415/https://www.zhihu.com/question/397509621)
    + [据说 steam 要出国内特供版本了…… - V2EX](https://archive.is/FPXXQ "https://www.v2ex.com/t/676328")
    + [steam要出中国特供版了 - 电子游戏(Game)版 - 北大未名BBS](https://web.archive.org/web/20200821025126/https://bbs.pku.edu.cn/v2/post-read.php?bid=49&threadid=16445230)
    + [蒸汽平台有遊戲時限！中國玩家崩潰：你不要過來 - Yahoo奇摩股市](https://archive.is/bFJva "https://tw.stock.yahoo.com/news/蒸汽平台有遊戲時限-中國玩家崩潰-你不要過來-035828837.html")
79. `2020-05-24` **新闻** [Valve Releases Censored Chinese Steam Client for Alpha Testing – Sankaku Complex](https://web.archive.org/web/20200524112247/https://www.sankakucomplex.com/2020/05/24/valve-releases-censored-chinese-steam-client-for-alpha-testing/)
80. `2020-05-27 20:55:29` **IT之家** [Steam 中国版泄露：加入健康游戏忠告，限制未成年人游戏时长 - Steam - IT之家](https://archive.is/VHNXv)
81. `2020-05-31 23:21:55` **IT之家** [《CS：GO》防沉迷错误已修复：Steam玩家需切换至Beta版 - CSGO - IT之家](https://archive.is/Mwtb9)
82. `2020-06-06` **新闻** [News - Client Updates](https://web.archive.org/web/20200606115302/https://store.steampowered.com/news/?feed=steam_client) 、
    [News - Steam Client Update Released](https://web.archive.org/web/20200606115322/https://store.steampowered.com/news/62162/)

    + Steam 这几天前后更新了多次测试版的客户端，为了完美世界的防沉迷而更新
    + [Steam Community :: Group :: Steam Client Beta](https://web.archive.org/web/20200606114915/https://steamcommunity.com/groups/SteamClientBeta/announcements)

83. `2020-06-04` **新闻讨论帖** [今日 Steam Beta 修复了多项与完美服有关的问题，建议更新至 Beta 版本 - 其乐 Keylol](https://archive.is/KXmnP "https://keylol.com/t604384-1-1")

84. `2020-06-08` **新闻讨论帖** [蒸汽平台不会出现“双重”《健康游戏忠告》 - 其乐 Keylol](https://archive.vn/X8YGL "https://keylol.com/t606186-1-1")

85. `2020-06-11` **新闻讨论帖** [蒸汽平台现以 CS:GO 完美服启动器呈现！ - 全球攻势 - 其乐 Keylol](https://archive.is/103Gm "https://keylol.com/t607467-1-1")

    > 也就是说，CS:GO 完美服启动器已经从Steam 的阉割版，变成了蒸汽平台阉割版，
    > 且其不再使用「IPCountry」等国际化的一些参数来作为参考标准，而是强制执行「完美区」的标准。

86. `2020-07-17` **新闻讨论帖** [Steam 将新增大陆下载区域，包括深圳、杭州和沈阳等…… - 热点聚焦 - 其乐 Keylol](https://archive.is/v9Kjl "https://keylol.com/t621136-1-1")

87. `2020-07-23` **新闻讨论帖** [蒸汽平台專用 CM 已下線 - 談天說地 - 其樂 Keylol - 驅動正版遊戲的引擎！](https://archive.is/9Qq7A "https://keylol.com/t623359-1-1")

88. `2020-07-25` **新闻讨论帖** [Steam中國微博賬號最新動向：現已改名為「蒸汽平台官方賬號」 - 談天說地 - 其樂 Keylol - 驅動正版遊戲的引擎！](https://archive.is/cyMXS "https://keylol.com/t624344-1-1")

89. `2020-07-28` Wallpaper Engine 登陆腾讯 WeGame

    + **IT之家** [腾讯：热门壁纸软件《Wallpaper Engine》即将上线 WeGame](https://archive.is/3F5mt "https://www.ithome.com/0/489/906.htm")
    + **其乐** [WeGame Wallpaper Engine即将于7月30日启动技术测试](https://archive.is/FPP87 "https://keylol.com/t625021-1-1")
    + **IT之家** [《Wallpaper Engine：壁纸引擎》登陆腾讯 WeGame 商店，即将开启测试](https://archive.vn/E5pXO "https://www.ithome.com/0/500/141.htm")，[评论](https://web.archive.org/web/20200801090600/https://dyn.ithome.com/comment/49250a21adb87da4)

90. `2020-07-29` **新闻讨论帖** [Steam CD改区界面变了 - 购物心得 - 其乐 Keylol](https://archive.is/EXDVS "https://keylol.com/t625576-1-1")，

    [steam已更改跨区政策，现在只能用当地支付方式购买游戏或者联系客服才能改，不能再通过IP直接改了，不知道是好是坏 百度steam吧](https://archive.is/9Pk56 "https://tieba.baidu.com/p/6848144877")

    > 请注意Steam商店跨区购买是违反Steam用户协议的
    >
    > 今天早上Steam再次更新了改区方式现在改区界面已经变成了这样，然后Steam又不支持阿根廷那边的货币结算，
    > 所以，以后去阿根廷，要么有当地银行卡，要么就找客服了

91. `2020-08-02` **新闻讨论帖** [蒸汽平台可以在 Linux 上启动 - 谈天说地 - 其乐 Keylol - 驱动正版游戏的引擎！](https://archive.is/ah7rS "https://keylol.com/t627361-1-1")

92. `2020-08-05` steam 添加了新标签 steamchinaapproved ，目前共有20多款游戏属于这个标签下，以下链接如无说明，则均有评论区
    > Steam中国过审游戏标记？——万狐飞仙
    + [SteamDB 泄露“Steam中国”首批游戏？ - 其乐 Keylol](https://archive.vn/ewTPv "https://keylol.com/t628374-1-1")
    + [确认“steamchinaapproved”标签为蒸汽平台过审标签 - 其乐 Keylol](https://web.archive.org/web/20200806025409if_/https://webcache.googleusercontent.com/search?q=cache:Ui-YPqnUq0QJ:https://keylol.com/t628599-1-1)
    + [Steam 中国首批游戏疑似被泄露：超 20 款游戏 - IT之家](https://archive.is/cHgbf "https://www.ithome.com/0/501/786.htm")
    + [SteamDB疑似泄露“Steam中国”游戏 大部分为国产游戏 _ 游民星空 GamerSky.com](https://web.archive.org/web/20200806063247/https://www.gamersky.com/news/202008/1310480.shtml)
    + [Steam后台数据库泄露了“Steam中国”的首批游戏 NGA玩家社区](https://archive.vn/lHbNQ "https://ngabbs.com/read.php?tid=22839992")
    + [Steam中国首批游戏疑似被第三方数据库泄露 - vgtime.com](https://archive.is/QnzZW "https://www.vgtime.com/topic/1094400.jhtml")
    + [Steam中国游戏列表疑似泄露 - 旅法师营地](https://archive.vn/c77vn "https://www.iyingdi.com/web/article/detail/105527?title=Steam中国游戏列表疑似泄露")
    + [Steam中国首批游戏阵容曝光，地平线黎明时分PC版媒体分出炉，生化3重制全解锁DLC售卖 - 哔哩哔哩](https://archive.is/wzKF8 "https://www.bilibili.com/video/BV1b541187Mn")
    + **无评论** [Steam China's first batch of over 20 games suspected to be leaked - cnTechPost](https://archive.is/0Ob6S "https://cntechpost.com/2020/08/06/steam-chinas-first-batch-of-over-20-games-suspected-to-be-leaked/")
    + **无评论区** [SteamDB疑洩露Steam中國首批遊戲 大量國產遊戲在列 電玩狂人](https://archive.is/RyIOg "https://playgame.wiki/news/a00a422d37")

93. `2020-08-13` steam 新的商店区域 XC，目前这个区域是蒸汽平台的区域，而目前进入蒸汽平台仍然只需要在启动项里添加 -steamchina
    + [蒸汽平台可能不是 Steam 中国（大陆）区——“?cc=xc”目前可以直接访问蒸汽平台商店 - 其乐 Keylol](https://archive.is/xbj9Z "https://keylol.com/t631490-1-1")
    + [【8.15 更新】蒸汽平台可能不是 Steam 中国（大陆）区——目前通过“?cc=xc”可以直接访问 - 其乐 Keylol](https://archive.is/r1mDF "https://keylol.com/t631490-1-1 更新了XC的意思以及游戏定价的可能性")
    + [Add SteamChina price · Issue #680 · SteamDatabase/steamdb.info · GitHub](https://web.archive.org/web/20200814051226/https://github.com/SteamDatabase/steamdb.info/issues/680)
    + **转载** [其乐论坛用户清靈語关于蒸汽平台的发现 - 游戏论坛 - Stage1st - stage1/s1 游戏动漫论坛](https://web.archive.org/web/20200814051443/https://bbs.saraba1st.com/2b/thread-1954559-1-1.html)
    + **转载** [网友探究：蒸汽平台可能并非Steam中国大陆区 游民星空 GamerSky.com](https://archive.is/v9wFW "https://www.gamersky.com/news/202008/1312620.shtml")
    + [看来，国区大概没事了【steam吧】百度贴吧](https://archive.is/RArzq "https://tieba.baidu.com/p/6880158622")
    + [也不知道是没人发还是都被删了，steamchina商店网址 NGA玩家社区](https://archive.is/diFB1 "https://keylol.com/t630992-1-1")
    + [继续探究，蒸汽平台可能不是#Steam# 中国（大陆）区... 来自其乐Keylol - 微博](https://archive.is/5QRDP "https://weibo.com/1842080303/JfJzNyVjH")
    + steam XC区相关的页面
        + [XC区商店主页英文版的模样](https://web.archive.org/web/20200813104028/https://store.steampowered.com/?cc=xc)
        + XC区免费以及有价格的游戏
            + [2020年8月13日为26个](https://web.archive.org/web/20200813104940/https://store.steampowered.com/search/?cc=xc)
        + [2020年8月20日，GTAV在?cc=xc无法显示商店页面](https://web.archive.org/web/20200820140446/https://store.steampowered.com/app/271590/Grand_Theft_Auto_V/?cc=xc)
            + 需登录 [《非「steamchinaapproved」标签游戏已无法从蒸汽平台打开页面》](https://keylol.com/t630992-1-1 "https://archive.is/NML4B")
        + [目前仍然没有国区价格的中国式家长的steamdb页面](https://archive.is/b5LkB "https://steamdb.info/app/736190/")

94. `2020-08-13` **新闻讨论帖** [Steam 的 CM 被细化——采用“cm.wmsjsteam.com” - 其乐 Keylol](https://archive.is/9XCUq "https://webcache.googleusercontent.com/search?q=cache:https://keylol.com/t631322-1-1")

95. `2020-08-18` **新闻讨论帖**

    + [蒸汽平台信息更新帖：8.18 去除“更新与优惠”数据 - 其乐 Keylol](https://web.archive.org/web/20200820134250if_/https://webcache.googleusercontent.com/search?q=cache:WSRFqwXzqtYJ:https://keylol.com/t633101-1-1)
    + [蒸汽平台信息更新帖：8.19 增加了支付系統 - 其乐 Keylol](https://archive.is/mmQId "https://keylol.com/t633101-1-1")

96. `2020-08-26` 教育部等六部门下发通知联合开展未成年人网络环境专项治理行动。「一是集中整治未成年人沉迷网络问题。重点对未落实网络游戏用户账号实名注册制度」

    + [教育部等六部门关于联合开展未成年人网络环境专项治理行动的通知 - 中华人民共和国教育部政府门户网站](https://web.archive.org/web/20200826080754/http://www.moe.gov.cn/srcsite/A06/s7053/202008/t20200826_480306.html)
    + [教育部等六部门下发通知联合开展未成年人网络环境专项治理行动 - 中华人民共和国教育部政府门户网站](https://web.archive.org/web/20200826080756/http://www.moe.gov.cn/jyb_xwfb/gzdt_gzdt/s5987/202008/t20200826_480307.html "https://archive.is/RPxTR")
    + [六部门联合印发通知：重拳治理未成年人网络环境！_新闻_央视网(cctv.com)](https://web.archive.org/web/20200826082126/https://m.news.cctv.com/2020/08/26/ARTIb7C8AF3WXxaSmZyhyjx4200826.shtml)

97. `2020-08-31以及后续几天` **新闻讨论帖** steam 新的商店区域 XC 的进一步变化，[🛠【9.12 更新】蒸汽平台信息更新帖：蒸汽平台商店页面网址确定，发布时可能没有社区 - 其乐 Keylol](https://archive.is/vi4s9 "https://keylol.com/t633101-1-1")

    1. 必须使用蒸汽平台的 UA 才能访问新商店区域 `Mozilla/5.0 (Windows; U; Windows NT 10.0; en-US; Valve Steam Client/steamchina/0; )`
    2. 蒸汽平台客户端的商店首页已几乎关闭，没有任何游戏，即使开启异家归途等蒸汽平台的游戏，也会提示「您所在的地区目前不提供此物品」
    3. 蒸汽平台社区页面无法打开，直接返回404状态码

98. `2020-09-12` **新闻讨论帖** Steam beta 客户端更新

    + [Steam 下载区域新增“南宁”，同时修正武汉等地的地理信息 - 其乐 Keylol](https://archive.is/T4S4Z "https://keylol.com/t641284-1-1")
    + [蒸汽平台商店页面网址确定，发布时可能沒有社区 - 其乐 Keylol](https://archive.is/O1tKo "https://keylol.com/t641289-1-1")
        + 蒸汽平台的 Steam 游戏中界面默认主页为 store.steamchina.com ，目前该页面还未上线
        + 社区被完全移除，客户端里删除了这个选项卡
    + [Steam中国使用总结 凌晨大黑狗 哔哩哔哩](https://archive.vn/hDJfM "https://www.bilibili.com/video/BV1KT4y1A7Ma")

99. `2020-09-16` SteamDatabase 的 SteamTracking 抓取到了未实装的[新代码](https://web.archive.org/web/20200919053038/https://github.com/SteamDatabase/SteamTracking/blob/53466cd4589225b5a0bec1ef29e83ca5fcbd8712/partner.steamgames.com/public/javascript/game_admin.js)，里面含有一个新的语言 "sc_schinese" 自带的描述为 "SteamChina - Simplified Chinese"

    Steam 的语言与区域是可以分别选择的，比如选择日区的商店的同时，可以使用简体中文，等任意语言作为客户端 & 网页的显示效果。

    可能是为了保留无删减的国际版的简体中文，只对 SteamChina 做本地化(和谐)。

    相关新闻讨论帖 [Steamworks 新增蒸汽平台专属语言选项“sc_schinese” - 热点聚焦 - 其乐 Keylol - 驱动正版游戏的引擎！](https://archive.is/Bkgh5 "https://keylol.com/t642396-1-1")

100. `2020-09-16 12:23:02` **新闻讨论帖** ……离谱！Steamworks 新增蒸汽平台专属语言选项“sc_schinese” - [阅读权限 255]

     详细信息我还没有获取到，我会尽快跟进

101. `2020-09-17` **新游戏即将推出** MECHBLAZE 在 Steam 出现了页面，SteamDatabase 抓取到的
     [信息](https://web.archive.org/web/20200919055553/https://steamdb.info/app/1398500/)
     说明该游戏应该是首个支持 sc_schinese 语言的游戏，
     [CSGO](https://web.archive.org/web/20200608055623/https://steamdb.info/app/730/info/) 以及
     [漫漫长路](https://web.archive.org/web/20200919062157/https://steamdb.info/app/856990/info/)
     目前均没有支持 sc_schinese 语言。

102. `2020-09-17 20:57` **新闻讨论帖** [STEAM遊戲支持語言新增 簡體中文-steam中國 - 其樂 Keylol](https://archive.is/7HS4H "https://keylol.com/t642813-1-1")

103. `2020-09-18 0点` 其乐论坛社区进入了关闭论坛的维护状态，时长为两周。详细内容这里:[其乐 - ggame.wiki](https://github.com/gledos/ggame_wiki/blob/master/website/其乐.md)

104. `2020-09-23 21:23` **数据挖掘** 游戏市场调研服务商 Niko Partners 的高级分析师 Daniel Ahmad 发现了还无法使用的蒸汽平台的注册与登录页面。

     + [Daniel Ahmad on Twitter: "Steam China login page is live (but doesn't allow logins/sign ups yet). This is a China specific version of Steam that is being operated by Perfect World and Valve. Will host games that have been approved by the games regulator. No change to international Steam. - Twitter](https://archive.is/mvtt8 "https://twitter.com/ZhugeEX/status/1308758939371270145")
     + 资讯报道&讨论
         + [Steam中国客户端 账户注册页面现已上线 - 3DM单机](https://archive.is/FSRy9 "https://www.3dmgame.com/news/202009/3798139.html")
         + [Steam中国客户端 账户注册页面现已上线 - AcFun弹幕视频网](https://archive.is/sXWw5 "https://www.aixifan.com/a/ac18077388")
         + [Steam中国客户端 账户注册页面现已上线 - 百度 Steam 贴吧](https://archive.is/bN2s3 "https://tieba.baidu.com/p/6976688701")
         + [消息称 Steam 中国客户端即将到来，账户注册页面现已上线 - IT之家](https://archive.vn/qH1G7 "https://www.ithome.com/0/510/511.htm")

105. 其乐论坛社区进入了关闭论坛的维护状态期间的时候，似乎更换了 TLS 证书，新证书签发于2020年8月26日，有效期为一年。

106. `2020-10-01 22:00:00` **新闻讨论帖** [蒸汽平台账户注册页面已可被访问 - 其乐 Keylol](https://archive.is/GQipU "https://keylol.com/t643151-1-1")

     [测试中的 SteamCN 创建账户页面](https://web.archive.org/web/20200923060617/https://rnr-sandbox.pwesports.cn/register.html)

     目前还无法使用，且《蒸汽中国用户协议》《隐私政策》均无法查看

107. `2020-10-21 08:04` [蒸汽平台 LOGO 已出現在 Steamworks - 其乐 Keylol](https://archive.is/mYSRI)，[30 files - styles_landing.css, main.css, profilev2.css, broadcast.css… · SteamDatabase/SteamTracking@d0d2875 · GitHub](https://web.archive.org/web/20201024090423/https://github.com/SteamDatabase/SteamTracking/commit/d0d2875401a6d39d36e645bdd69be329b48bb34a)

     ![Steam China](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAI8AAAAsCAYAAABc6+vTAAAAGXRFWHRTb2Z0d2FyZQBBZG9iZSBJbWFnZVJlYWR5ccllPAAAAyJpVFh0WE1MOmNvbS5hZG9iZS54bXAAAAAAADw/eHBhY2tldCBiZWdpbj0i77u/IiBpZD0iVzVNME1wQ2VoaUh6cmVTek5UY3prYzlkIj8+IDx4OnhtcG1ldGEgeG1sbnM6eD0iYWRvYmU6bnM6bWV0YS8iIHg6eG1wdGs9IkFkb2JlIFhNUCBDb3JlIDUuMy1jMDExIDY2LjE0NTY2MSwgMjAxMi8wMi8wNi0xNDo1NjoyNyAgICAgICAgIj4gPHJkZjpSREYgeG1sbnM6cmRmPSJodHRwOi8vd3d3LnczLm9yZy8xOTk5LzAyLzIyLXJkZi1zeW50YXgtbnMjIj4gPHJkZjpEZXNjcmlwdGlvbiByZGY6YWJvdXQ9IiIgeG1sbnM6eG1wPSJodHRwOi8vbnMuYWRvYmUuY29tL3hhcC8xLjAvIiB4bWxuczp4bXBNTT0iaHR0cDovL25zLmFkb2JlLmNvbS94YXAvMS4wL21tLyIgeG1sbnM6c3RSZWY9Imh0dHA6Ly9ucy5hZG9iZS5jb20veGFwLzEuMC9zVHlwZS9SZXNvdXJjZVJlZiMiIHhtcDpDcmVhdG9yVG9vbD0iQWRvYmUgUGhvdG9zaG9wIENTNiAoV2luZG93cykiIHhtcE1NOkluc3RhbmNlSUQ9InhtcC5paWQ6NDZGOTI3NDMxMjMwMTFFQjlCNEREQTNDNkM5MjJEMDEiIHhtcE1NOkRvY3VtZW50SUQ9InhtcC5kaWQ6NDZGOTI3NDQxMjMwMTFFQjlCNEREQTNDNkM5MjJEMDEiPiA8eG1wTU06RGVyaXZlZEZyb20gc3RSZWY6aW5zdGFuY2VJRD0ieG1wLmlpZDo0NkY5Mjc0MTEyMzAxMUVCOUI0RERBM0M2QzkyMkQwMSIgc3RSZWY6ZG9jdW1lbnRJRD0ieG1wLmRpZDo0NkY5Mjc0MjEyMzAxMUVCOUI0RERBM0M2QzkyMkQwMSIvPiA8L3JkZjpEZXNjcmlwdGlvbj4gPC9yZGY6UkRGPiA8L3g6eG1wbWV0YT4gPD94cGFja2V0IGVuZD0iciI/Pl/SM9QAAApwSURBVHja7J0LcBbV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)

108. `2020-10-21 16:35` **数据挖掘** 为 SteamDB 工作的数据挖掘者 [Pavel Djundik](https://twitter.com/thexpaw) 发现了必须获得版号，装入文字过滤系统，接入防沉迷系统，拥有启动页面的48字真言才能上架蒸汽平台。[^Pavel]

     [^Pavel]: [Pavel Djundik on Twitter: "This is what game publishers will need to fill in to get their game released in Steam China https://t.co/iN2td0RpfK" / Twitter](https://archive.is/Dmbb0)

     中文资讯： [蒸汽平台上的游戏应该必须要有版号才能发行 - 其乐 Keylol](https://archive.is/CVw6t "https://keylol.com/t649792-1-1")

109. `2020-10-21 左右` **新闻** [steam网页登录界面更新了 - 其乐 Keylol](https://archive.is/zNx4o "https://keylol.com/t649678-1-1")，登陆页面更加现代化

110. `2020-11-05` [测试中的蒸汽平台大更新：使用红色 STEAM 图标，社区沦为“空间”及意味深长的英语条目 - 其乐 Keylol](https://archive.is/ryHck "https://keylol.com/t654581-1-1")

     商店、客服及个人资料页面全面使用“steamchina.com”社区功能目前只剩下好友之间的个人资料页面（STEAM 空间），客户端强制“简体中文 - 蒸汽平台”，且无大屏幕模式，好友数据隔离。

     还有意味深长的新菜单条目，这可能意味着不会强制性让Steam大陆区转移到蒸汽平台，仅仅是一个选择：

     ```text
     "Steam_Startup_SteamChinaRequiredTitle"         "需要蒸汽平台"
     "Steam_Startup_GetSteamChina"                   "%gamename% 现在可以在蒸汽平台获取，请点击下面的链接安装其客户端。"
     "Steam_Startup_RunSteamChina"                   "%gamename% 现在可以在蒸汽平台获取，请启动蒸汽平台以导入您的游戏。"
     "Steam_Startup_SteamChinaImportedUninstall"     "%gamename% 已导入蒸汽平台，现在您可以安全卸载此启动器。"
     "Steam_Startup_LauncherDeprecated"              "%gamename% 现在可以在蒸汽平台运行，此安装不再受支持，即将退出。"
     "Steam_Startup_ImportGameFromLauncherTitle"     "导入游戏"
     "Steam_Startup_ImportGameFromLauncherMsg"       "您想将%gamename%导入蒸汽平台吗，那么您将可以安全地卸载旧版启动器。"
     
     "Steam_Download_SteamChina"                     "下载蒸汽平台"
     ```

111. `2020-11-18` [今日 Steam 商店首页头部 LOGO 更新，换成了 SVG 图，顺便新增了蒸汽平台 LOGO - 其乐 Keylol](https://archive.is/sBmc1 "https://keylol.com/t658948-1-1")

     16日时steamchina.com 新签发了三个次级域名的证书

112. `2020-11-19` [蒸汽平台客户端已出现 CS:GO 及 DOTA 2 - 其乐 Keylol](https://archive.is/gPl02 "https://keylol.com/t659236-1-1")

113. `2020-12-03` [蒸汽平台有着独有的三个下载 CDN，分别由腾讯云、网宿科技和阿里云提供服务 - 其乐 Keylol](https://archive.is/tmU04 "https://keylol.com/t663540-1-1")

     这可能意味着蒸汽平台与Steam大陆区会并行运营，而非强制切换/转移。

114. `2020-12-09` [用户可在 Steam Support 撤销蒸汽平台访问权限和和实名认证信息 - 其乐 Keylol](https://archive.is/umaqI "https://keylol.com/t665563-1-1") [Source](https://web.archive.org/web/20201216052320/https://github.com/SteamDatabase/SteamTracking/commit/65bb929fb02b3f996de247dd8819c51a2967a07d)

115. `2020-12-21 12:31` **微博** [2021年1月16-17日，蒸汽平台实验室，与你不见不散[嘻嘻] 来自蒸汽平台 - 微博](https://archive.is/PC7Vh "https://weibo.com/6654528440/Jztv8sdeb")

116. `2020-12-24 15:59:02` [蒸汽平台客户端“独立分开”，目前确认其没有大屏幕模式和远程同乐 - 其乐 Keylol](https://archive.is/M9tYb "https://keylol.com/t669953-1-1")

     在此之前，Steam与蒸汽平台都是请求相同的更新文件目录，所以客户端的文件也一样，但在12月23日后，从官网上下载的更新文件目录就不同了，目前蒸汽平台客户端的更新早于启动器早于 Steam。

     对比文件后发现，蒸汽平台客户端缺少了大屏幕模式所需的 tenfoot 相关文件，以及远程同乐/远程畅玩所需的 streaming_client.exe 。

117. `2020-12-28` [蒸汽平台客户端允许运行在中文目录，但 Steam 客户端还不行 - 其乐 Keylol](https://archive.is/1Umap "https://keylol.com/t671051-1-1")

118. `2020-12-31` [【蒸汽平台相关】新标签“AllowPurchaseInSteamChina”，地区代码”XC“ - 其乐 Keylol](https://archive.is/D7Zq6 "https://keylol.com/t671965-1-1")

119. `2021-01-01` [G胖连夜加班，为大伙移除了 Steam 客户端中的蒸汽平台文件作为新年礼物 - 其乐 Keylol](https://archive.is/X7Qyz "https://keylol.com/t672268-1-1")

     > 今日更新从 Steam 客户端删除了 steamchina 目录，并作为一个 Depot 添加进蒸汽平台客户端中。
     >
     > **但这并不影响通过参数“-steamchina”而从 Steam 客户端进入蒸汽平台。**

120. [蒸汽平台可通过实名信息找回密码 - 其乐 Keylol](https://archive.is/9LXtc "https://keylol.com/t673662-1-1")

     蒸汽平台沙箱测试网站中出现了一个名为 [recovery.html](https://archive.is/z7slN "https://rnr-sandbox.pwesports.cn/recovery.html") 的嵌入页面，预计蒸汽平台将会通过实名认证的信息进行找回密码。

121. `2021-01-08 11:27` **Steam Beta Update** Remote Play Together is now available in China[^ws_scb118]

     [^ws_scb118]: [Steam Community :: Group :: Steam Client Beta](https://web.archive.org/web/20210109074448/https://steamcommunity.com/groups/SteamClientBeta/announcements/detail/2933499125713869805)

     Steam Beta 更新日志是称远程同乐功能在大陆现能够使用，不过一些玩家测试后发现还是没法连接上。[^ws_scb118_tset]

     [^ws_scb118_tset]: [远程同乐貌似可以在中国运行了 - 其乐 Keylol](https://archive.is/0uLu9 "https://keylol.com/t674459-1-1")

     <!-- [【不实信息】CS:GO 和 DOTA 2 完美服玩家不会被强制转至蒸汽平台 - 热点聚焦 - 其乐 Keylol - 驱动正版游戏的引擎！](https://archive.is/31s6A) -->

122. `2021-01-08 09:09` [玩 CS:GO 和 DOTA 2 大陆服务器需要将帐户从完美通行证迁移至蒸汽平台 - 热点聚焦 - 其乐 Keylol - 驱动正版游戏的引擎！](https://archive.is/SfsUB "https://keylol.com/t674392-1-1")

123. `2021-01-09` [免费获得的CSGO今起也可出现国服国际服选择框 - 其乐 Keylol](https://archive.is/PxFaM "https://keylol.com/t674754-1-1")

124. `2021-01-25` 26日这天前后，CSGO大陆区运营商完美世界，旗下的多款游戏都会在这段时间里进行维护

     + 2021年1月26日 00:00-14:00 期间，《完美国际2》所有服务器进行停机维护[^ws_pwg2]
     + 2021年1月26日 00:00-14:00 期间，《武林外传》全区全服进行数据库升级[^ws_wulin2]
     + 2021年1月26日 00:00-14:00 期间，《完美世界》数据库升级维护[^ws_world2]
     + 2021年1月26日 00:00-14:00 期间，《神魔大陆2》数据库升级维护[^ws_shenmo]
     + 2021年1月26日 00:00-14:00 期间，《梦幻诛仙2》全区全服进行数据库升级[^ws_mhzx2]
     + 2021年1月26日 从零时开始到当天内，《新诛仙手游》对部分服务器进行「数据互通」，关闭源服务器和目标服务器的部分功能[^ws_zx]
     + 2021年1月26日 00:10-14:00 期间，《CSGO》游戏账号体系进行升级[^ws_csgoml]
     + 2021年1月26日 00:10-14:00 期间，《创世战车》对服务器进行维护，本次维护不停服[^ws_co]
     + 2021年1月26日 00:10-14:00 期间，《神鬼传奇》对正式服进行不停机维护[^ws_sgcq]
     + 2021年1月26日 08:00-10:00 期间，《诛仙3》所有服务器进行停机维护[^ws_zx3]

     [^ws_pwg2]: [《完美国际2》数据库升级维护说明公告 - 《完美国际2》官方网站](https://archive.is/M9EYq "https://w2i.wanmei.com/news/bulletin/20210125/83373.shtml")

     [^ws_wulin2]: [《武林外传》1月26日数据库升级公告-《武林外传》游戏官方网站，今日新区豪礼相送](https://web.archive.org/web/20210127161306/https://wulin2.wanmei.com/news/gamebroad/20210125/229138.shtml)

     [^ws_world2]: [《完美世界》数据库升级维护公告 - 《完美世界：撼世王朝》官方网站 - 国产东方唯美3D时长版网游！无商城！](https://web.archive.org/web/20210127163348/https://world2.games.wanmei.com/article_news/gonggao/20210125/83382.shtml)

     [^ws_shenmo]: [《神魔大陆2》数据库升级维护说明公告 -跨年狂欢趴 《神魔大陆2》惊喜双旦派对](https://web.archive.org/web/20210127162935/https://shenmo.games.wanmei.com/news/gamepost/20210125/229154.shtml)

     [^ws_mhzx2]: [《梦幻诛仙2》1月26日数据库升级公告 - 《梦幻诛仙2》官方网站](https://web.archive.org/web/20210127163001/https://mhzx2.wanmei.com/news/gamebroad/20210125/229135.shtml)

     [^ws_zx]: [1月28日数据互通公告 - 新《诛仙》手游新版12.31上线 兽首联动青云加强](https://web.archive.org/web/20210127161220/https://zx.wanmei.com/news/gamebroad/20210125/229133.shtml)

     [^ws_csgoml]: [CSGO国服账号体系升级公告 来自CSGO - 微博](https://archive.is/C8ugn "https://archive.is/BA5rv & https://weibo.com/5980136393/JEQfh61Fw")

     [^ws_co]: [1月26日不停服维护公告 - 《创世战车》官方网站](https://web.archive.org/web/20210127162955/https://co.games.wanmei.com/news/gamebroad/20210125/229156.shtml)

     [^ws_sgcq]: [游戏公告 -《神鬼传奇》官方网站 - 完美世界](https://web.archive.org/web/20210127162950/http://sgcq.wanmei.com/news/gamenotice/20210125/229157.shtml)

     [^ws_zx3]: [1月26日全服停机更新维护公告 - 《诛仙3》官方网站-新版“诀世天昭”今日震撼公测-完美世界](https://web.archive.org/web/20210127161001/http://zhuxian.wanmei.com/news/gamebroad/20210125/83380.shtml)

     完美世界在这期间未维护的客户端网络游戏：《笑傲江湖OL》《DOTA 2》《赤壁》《热舞派对》《神鬼世界》《口袋西游》

125. `2021-01-27` [Steam国区商店价格有小数点了...... - 其乐 Keylol](https://archive.is/HORhf "https://keylol.com/t680022-1-1")

126. `2021-02-03` [正式确认蒸汽平台有 macOS 客户端，暂未见 Linux 客户端 - 其乐 Keylol](https://archive.is/RGO30 "https://keylol.com/t682384-1-1")

127. `2021-03-03` [【2021.3.3】锁偏好游戏通过愿望单已无法添加购物车，sub大法亦失效（接收礼物暂不影响） - 其乐 Keylol](https://archive.is/BMex0 "https://keylol.com/t691241-1-1")

     Steam 大陆区从原来的 SUBID 购买「软锁」游戏的方法已失效。

     注: 曾经能够使用 SUBID 添加购物车或者愿望单的游戏常常被叫做「软锁」。

128. `2021-11-03` [Steam 不再提供中国内地的 CM 服务器 - 其乐 Keylol](https://archive.md/4rxwl "https://archive.md/4rxwl")

     > CM（Connection Manager）服務器，用於 Steam 帳戶登錄認證、好友在線狀態、聊天和遊戲邀請等等方面。
     >
     > 目前 Steam 獲取的服務器列表已不存在中國內地服務器
     >
     > 中國內地服務器（域名為 wmsjsteam.com）僅存在於蒸汽平台所獲取的服務器列表之中

129. 未完待续

<!-- [这是真的吗 NGA玩家社区](https://archive.vn/rgmOt) 在隔壁群友看到的，如果是真的话，那?死也不会用的
    steam中国、WAC反作弊 -->

<!-- 质量不高的转载新闻或不适合列表起来的来源

【有评论】 [中国版Steam蒸汽平台传首发这28款游戏，玩家崩溃：你不要过来啊 - 游戏资讯(英雄联盟LOL)](https://web.archive.org/web/20200820135555/http://www.bajieyou.com/new/805cd40bb50e4703895f874bd6ec2939)

2020-08-20 的Steam新闻 热点聚焦板块的快照 [Steam新闻 - 热点聚焦 - 其乐 Keylol - 驱动正版游戏的引擎！](https://archive.is/tpV63 "https://keylol.com/forum.php?mod=forumdisplay&fid=161&filter=typeid&typeid=461")

 -->

[^311712]: https://archive.is/RsasZ "https://keylol.com/t436526-1-1"

可能有关的资料
--------------

### 网宿科技相关但没有直接与 steam 相关的资料

`2015-12-07`[东方明珠战略联手网宿科技 合作互联网电视领域](http://finance.china.com.cn/stock/ssgs/20151207/3481965.shtml)。

`2016-12-16`[网宿获首批内容分发牌照 CDN开启牌照时代](http://www.wangsu.com/content/details45_2148.html)

`2017-08-10`[网宿科技正式获工信部云服务业务许可牌照](http://www.wangsu.com/content/details45_2760.html)。这个时间有点耐人寻味

额外的资料
---------

### 1321200 eula 事件

+ [网络游戏防沉迷系统及实名认证服务协议](https://web.archive.org/web/20200603140815/https://store.steampowered.com//eula/1321200_eula_0)
+ [《网络游戏防沉迷系统及实名认证服务协议》出现在Steam上 - 热点聚焦 - 其乐 Keylol](https://archive.is/4iOaX)
+ [我在SteamDB上找到了EA准备上线Steam的app - 热点聚焦 - 其乐 Keylol](https://archive.is/Mnyfl)
+ [我在SteamDB上找到了EA准备上线Steam的app - 第2页 - 热点聚焦 - 其乐 Keylol](https://archive.is/hwUMw)
+ [Pavel Djundik on Twitter: "Scanned available EULAs for unknown Steam apps, there's quite a few EA apps https://t.co/gIqjt63GBR" / Twitter](https://archive.is/BhIsW)
+ [eulas.csv · GitHub](https://web.archive.org/web/20200603145059/https://gist.github.com/xPaw/a7ffdd64043d076d900666c833e8aa8d)
+ [SteamDB Unknown App 1321200 · AppID: 1321200 · SteamDB](https://web.archive.org/web/20200603144234/https://steamdb.info/app/1321200/)
+ [SteamDB页面出现“网络游戏防沉迷系统及实名认证服务协议” _ 游民星空 GamerSky.com](https://archive.vn/dvT8e)
+ [《网游防沉迷系统及实名认证服务协议》出现在Steam上_3DM单机](https://web.archive.org/web/20200603143803/https://m.3dmgame.com/news/202006/3790036.html)
+ [Steam上出现《网游防沉迷系统及实名认证服务协议》 今后或要求Steam老玩家实名认证 NGA玩家社区](https://web.archive.org/web/20200604060727/https://webcache.googleusercontent.com/search?q=cache:jbrH0Cu28OEJ:bbs.nga.cn/read.php%3Ftid%3D22029173)
+ [Steam上出现《网游防沉迷系统及实名认证服务协议》 NGA玩家社区](https://web.archive.org/web/20200604060902/https://webcache.googleusercontent.com/search?q=cache:05TvUfgVG8AJ:https://ngabbs.com/read.php%3Ftid%3D22029173)
+ [Steam中国区要变?防沉迷+实名认证来了 防沉迷+实名认证来了-手机行情_华商网数码](https://web.archive.org/web/20200604060545/http://digi.hsw.cn/system/2020/0604/136034.shtml)
+ [SteamDB页面出现“网络游戏防沉迷系统及实名认证服务协议”_IT新闻_博客园](https://web.archive.org/web/20200604060532/https://news.cnblogs.com/n/663372/)
+ [有玩家在Steam的域名下找到一份《网络游戏防沉迷系统及实名认证服务协议》 来自触乐 - 大神](https://web.archive.org/web/20200604060612/https://ds.163.com/user/e961b214f48e4cee918a7f0efddecef1/feed/5ed864e012b80d4efdfc0a04/)
+ [Steam也有网络游戏防沉迷系统了 - 中国焦点日报网](https://web.archive.org/web/20200604060238/http://games.cnjdz.net/yxpd/2020/0604/26032.html)
+ [SteamDB页面出现“网络游戏防沉迷系统及实名认证服务协议”-steam,游戏,防沉迷,实名制 ——快科技(驱动之家旗下媒体)--科技改变未来](https://web.archive.org/web/20200604060253/https://news.mydrivers.com/1/692/692991.htm)
+ [《网游防沉迷系统及实名认证服务协议》上Steam 该来的终于来了_牛游戏网资讯](https://web.archive.org/web/20200604055934/https://www.newyx.net/news/635389_1.htm)
+ [Steam中国区或将上线实名认证及防沉迷系统_风闻社区](https://web.archive.org/web/20200604060012/https://user.guancha.cn/main/content?id=321717&s=fwzxhfbt)
+ [《網遊防沉迷系統及實名認證服務協議》出現在Steam上 電玩狂人](https://web.archive.org/web/20200604064726/https://playgame.wiki/news/4bc9d2ff4e)

### steam 商店页面在中国的测速

+ `2018-07-13` [主站 store.steampowered.com 测试](https://web.archive.org/web/20180713132408/https://www.17ce.com/site/http/20180713_c0ec16e0869f11e8bab64ffc7156171c:1.html)
+ `2018-07-14` [主站 store.steampowered.com 测试](https://web.archive.org/web/20200820132339/http://www.17ce.com/site/http/201807_04596bd0208b5b3c168a845761dd4b1b.html)

<!-- greatfire.org 似乎不可靠

### **CDN** *akamai.steamstatic.com* 域名下的 GFW 阻断情况

+ [根据 greatfire 的信息得出结论：并没用看见是 GFW 在阻断 Akamai](https://zh.greatfire.org/search/all/Akamai.steam)
+ [cdn.steampowered.com 也没有在 GFW 上被拦截](https://zh.greatfire.org/search/all/cdn.steampowered.com) -->

### 腾讯 wegame 的网络限制行为（疑惑&不确定）

+ [关于高延迟/文件损坏/弹窗闪退/多开等问题临时解决方案的公告-新闻中心-天涯明月刀-官方网站-腾讯游戏-电影网游新艺术，这就是武侠](https://web.archive.org/web/20190205015329/https://wuxia.qq.com/webplat/info/news_version3/5012/5013/5014/5016/m3486/201709/636379.shtml)
  + 此公告建议用户回退 Windows10 版本到旧版本，并且关闭 Windows10 自动更新
+ [TGP/WeGame驱动导致WSL网络服务异常](https://archive.is/W3pyk "https://zhuanlan.zhihu.com/p/33723838")
+ [坑爹的腾讯TGP（WeGame）导致WSL无法连接到端口问题](https://archive.is/GiQ5s "https://zhuanlan.zhihu.com/p/27731530")
+ [大毒瘤！卸载WeGame解决XPS 15蓝屏问题 - 阅读 - 掘金](https://web.archive.org/web/20180712070032/https://juejin.im/entry/5b2b15cae51d4558d35facf5)
+ [TGP 驱动导致 WSL 故障 - V2EX](https://web.archive.org/web/20180712045236/https://www.v2ex.com/t/429742)
+ [蓝屏毒瘤:腾讯居然比360还牛逼！隐蔽的TDI筛选器！](https://archive.is/shhBm "https://www.bilibili.com/read/cv248113/")
+ [发现了tgp里的【无用】驱动【windows8吧】_百度贴吧](https://web.archive.org/web/20180712055929/http://tieba.baidu.com/p/3637947742)
+ [一上线就说检测到异常 网络连接断开（客服已回复）,沃特碧们的Colg,DNF地下城与勇士 - COLG社区](https://web.archive.org/web/20180712030019/https://bbs.colg.cn/thread-7258396-1-1.html)
+ [❌STEAM和WEGAME冲突？](https://steamcn.com/t314958-1-1)

### 玩家认为是腾讯软件的问题

大多数内容都是关闭了QQ，然后就能上steam社区了，不过以下内容均无法确认因果关系

+ [震惊!Steam无法访问的背后原因竟然是...... - 其乐 Keylol](https://archive.is/DuQeb "https://keylol.com/t291334-1-1")

## 捕风捉影中的捕风捉影

[steam 被墙了? 还是只是临时抽风](https://web.archive.org/web/20200820153443/https://www.v2ex.com/t/377252)
    + 32楼：有种说法是 6 月 1 号 Law of Cyber Security 开始实施后，Steam 不能再用国内 8686c 的 CDN，
      所以国内用户访问时也使用 Akamai，Akamai CDN 被 GFW RST 导致的

<!-- 一些IT之家的steam相关新闻
[Steam 游戏节秋季版将于 10 月 7 日至 13 日举办，大量游戏提供试玩 - Steam,游戏 - IT之家](https://archive.is/ADeg5)
[《蘑菇采摘模拟器》登陆 Steam 售价 16 元，网友：这一点都不云南 ！ - Steam,蘑菇 - IT之家](https://archive.is/xrh04)
[Steam 上周销量排行：《糖豆人：终极淘汰赛》三连冠，《GTA5》在列 - Steam - IT之家](https://archive.is/UZio2)
[Steam 喜加一：动作冒险解密游戏《磁力高手：黑暗脉冲》免费领取 - Steam,喜加一,游戏 - IT之家](https://archive.is/G7YbF)
[动作游戏《鬼泣 5》Steam 再次永久降价：标准版 137 元 - Steam - IT之家](https://archive.is/4FYzD)
[大型多人 RPG 游戏《激战 2》登陆 Steam：11 月发售 - 游戏,Steam - IT之家](https://archive.is/2AEyf)
 -->

## 非常侧面的资料-友商的资料

[❌转个A9VG关于psn网络不好用原因的帖子](https://tieba.baidu.com/p/3504351437)

## 腾讯邮箱屏蔽steam邮件事件

注意，这到底是故意的还是无意的我是没有找到证据，当然除了有时候block steam之外还会block 其他的邮件，比如 DMM。但是我是没找到有人被qq邮箱屏蔽了邮件

+ `2013-07-04` **新闻** [拦截D2邮件,恶性竞争&无意为之？](https://web.archive.org/web/20180122021905/https://dota2.uuu9.com/201307/447561.shtml)
+ `2014-08-29` **帖子** [为什么我的qq邮箱收不到完美的邮件。。。](https://archive.is/3AldK "https://tieba.baidu.com/p/3262705495")
+ `2015-05-07` **帖子** [QQ邮箱出现了新的针对DOTA2方法！求破解](https://archive.is/KWUOT "https://tieba.baidu.com/p/3748153998")

## DOTA2刚开服时出现的"腾讯拒绝员"事件

同样此事件真实性存疑

[帖子](https://archive.is/f2JPC "https://tieba.baidu.com/p/2324368326") 27楼：基本遇到拒绝都是玩上海服务器和东南亚的，现在只排澳洲表示再也没遇见过拒绝狂魔！！
V社真的该对拒绝游戏施加点什么限制因素了，不然TX真的用个几千水军来拒绝基本这游戏中国地区的玩家就可以不用玩了，大家还是去玩lol吧！！

## steam 帐号盗号相关的一些资料

+ `2017-12-31 05:55` [各位steam吧友，本人近期卧  底于steam黑号群，现在曝光](https://web.archive.org/web/20180129041630/https://tieba.baidu.com/p/5498583590)

    > 各位steam吧友，本人近期卧底于steam黑号群，现在曝光黑号群是怎么盗取别人steam账号的。
    >
    > 1.利用租号网上的账号用软件破解密码（无法改邮箱密码叫做临时黑，卖20-25块）
    >
    > 2.利用特殊的软件，可盗取steam的账号和原始邮箱（可修改密码邮箱，叫做永久黑45-50等）
    >
    > 3.白号，盗取的steam号啥都没绑，而且还刚买了游戏（游戏为吃鸡这种最容易被盗）！！！
    >
    > 以上被盗用和大肆售卖的号，主要用途为绝地求生开启辅助用，基本上都是VAC封禁！！！！
    >
    > 各位steam吧友，最好设置steam令牌，邮箱最好设qq邮箱，qq邮箱没有被盗成功过的案例，被盗的基本为163邮箱，
    > 希望官方能在找回steam账号的步骤越来越严格，这样对打击绝地求生的外挂和减少steam被盗的风险都有好处，望各位吧友，保管好自己的账号。

## steam 在中国网吧的一些资料

+ `2017-10-09 20:03` **帖子** [❌日，去了趟网吧账号被盗](https://tieba.baidu.com/p/5363625498)

    > 本人因为电脑BOOM，无奈去了两天网吧玩吃鸡，结果账号被盗，邮箱被改还绑定了别人手机
    >
    > 现在向客服发出申请，有发到我邮箱的更改邮箱和手机成功的邮件截图，以及好友送我游戏的历史截图，
    > 更有甚者因为我偷懒，所以连我的steam账户名都是我的QQ号（一串数字）。。。
    >
    > 求问大佬们，这总能找回的吧。。。找回时间会很久么。。。

+ `2017-12-24 12:28` **帖子** [现在的网吧都这么玩的吗](https://archive.is/62ONh "https://tieba.baidu.com/p/5490726117")
    >[图片📷](/img/steam/35363372.jpg)

## steam对中国区的动作

>Steam真的很努力在改善中国市场，为此花费了大价钱专门在美国和马来西亚雇佣了大批华人来负责客服方面的问题。（有待确认）

## steam玩家提供的信息

### 匿名玩家326DustySheeps

``` text
匿名玩家326DustySheeps:

    贴吧里已经找不到那个帖子了，腾讯的DNS可以正常使用steam所有功能，
    实测成功，大概是上月22号之前的事。

[2:46:59 PM] gledos:

    你当时使用过其他的DNS来测试吗？

[2:48:07 PM] 匿名玩家326DustySheeps:

    没有，一直是默认的dns，上不去
    基本不改改dns

[2:50:04 PM] gledos:

    https://web.archive.org/web/20180205064820/https://steamcn.b0.upaiyun.com/archiver/tid-293805.html?page=1
    这里的资料描述了steam 与 第三方的DNS 之间的一些联系
    所以有可能是在你的网络下只要使用第三方的DNS就能连接上steam的网络

[2:56:20 PM] 匿名玩家326DustySheeps:

    一周前这个dns上不去steam了
    改其他的也没有效果

[2:57:54 PM] gledos:

    商店也上不去吗？

[2:58:19 PM] 匿名玩家326DustySheeps:

    商店可以的
    除了市场，动态，愿望单，其他可以
    商店就出现过一次问题

[2:59:40 PM] gledos:

    省份和网络商可以透露一下吗？
    具体无法链接市场，动态，愿望单的时间您记得吗？

[3:00:28 PM] 匿名玩家326DustySheeps:

    江苏移动。

[3:01:56 PM] 匿名玩家326DustySheeps:

    时间记不清，说的不一定准确

[3:03:41 PM] 匿名玩家326DustySheeps:

    在网络盛传因为膜的那个组，
    以及国内才准备对膜采取措施的那个时间点左右steam所有的服务都断过一次

[3:04:13 PM] 匿名玩家326DustySheeps:

    12月底后steam的社区服务就完全上不去了

[3:06:03 PM] 匿名玩家326DustySheeps:

    只记得这些。

[3:13:13 PM] gledos:这

    两句话似乎有矛盾......
    一周前这个dns上不去steam了
    12月底后steam的社区服务就完全上不去了

[3:16:05 PM] 匿名玩家326DustySheeps:

    第一个表意不明确，我指的上不去是“上不去社区及个人资料等”
    >对于上去过的腾讯DNS
    之后12月底除了挂梯就上不去。这么个意思
    >steam的好友，聊天，商店，支付系统，鉴赏家，新闻，统计，都一直正常

[3:19:27 PM] gledos:

    ......我还是把你的原句记录下来好了

[3:20:04 PM] 匿名玩家326DustySheeps:

    还有wallpaper engine的内置创意工坊可以直接访问。不会出奇怪问题

[3:21:37 PM] gledos:

    allpaper engine 可以访问创意工坊这件事有待确认，因为有人认为是 wallpaper engine 自己的服务器
    具体的测试实验我也没法做，我的电脑坏了

[3:30:21 PM] 匿名玩家326DustySheeps:

    嗯 我也就知道这么多。

[3:31:38 PM] gledos:

    谢谢
```

信息来源名单
------------

感谢：

+ [spartan1096](https://tieba.baidu.com/home/main?un=spartan1096)
+ [清靈語](https://keylol.com/suid-209154)

<!-- [清靈語的微博_微博主页](https://archive.is/ViPOw) -->
