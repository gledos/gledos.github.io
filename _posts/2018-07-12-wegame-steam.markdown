---
title: steam在华网络问题的捕风捉影
layout: post
published: true
# date: '2018-07-12 20:52:00 +0800'
tags:
    - 历史
    - 游戏
---
<!-- 谁杀死了Steam？ -->

这是一个历史事件的记录，可能有所遗漏，但我会尽可能的详细记录的。

<!-- more -->

虽然不太好说出口，但我还是想说我想保持中立，如果有什么我遗漏掉的**信息**，请通过电子邮箱 cngledos@gmail.com 联系我。

这里和wiki的方针一样，详细记录，保持客观、真实和公开。邮件交流的内容也可以被公开(如果您同意的话)。

~~原标题：《steam出现101、103错误与腾讯wegame的联系》。在东八区时间 2017年8月9日 写下的，因为不客观就修改了标题~~

---

目前此记录里已有大量链接失效，其中失效的网页大量是百度贴吧，原因是 2017 年以前的帖子被冻结为不可读了。

如果有网页被删除了或「自然」失效，我可能会用 [web.archive.org](https://web.archive.org/) 的网页快照替换掉原网页。

如果你想要缓存网页并作为证据，我推荐此chrome扩展 [Save To The Wayback Machine](https://chrome.google.com/webstore/detail/eebpioaailbjojmdbmlpomfgijnlcemk)。火狐、Opera也有保存到 Wayback Machine 的附加元件，可以去这个扩展的[官网](https://github.com/VerifiedJoseph/Save-to-the-Wayback-Machine)找到。

如果 [web.archive.org](https://web.archive.org/) 无法保存防爬虫、重定向等对 archive.org 不友好的网站，可以尝试 [archive.today](https://archive.today/) 。

主时间轴
--------

1. `2015-6-23 23:33` **帖子** [自己抓了一些高速IP](https://steamcn.com/t133519-1-1)
    这是使用百度搜索引擎找到的关于 steam 在国内的 CDN 最早的侧面记录，里面提到了 8686c.com 这个属于**万网志成**下的**网宿科技**的 CDN 。
2. `2016-02-05 13:47:50` **帖子** [乐山电信屏蔽cdn.akamai.steamstatic.com？](https://steamcn.com/t165524-1-3)
    省略读标题就能知道的内容
    >19楼:63.110.60.27我这能通，我怀疑你的那个ISP就是故意ban了steam。你只能换你那边的isp没ban的网段。。。把解析结果写入本地hosts。要不就施放魔法/或者走科学了，只能这样。
3. `2016-02-14` **行政法规** [网络出版服务管理规定](https://web.archive.org/web/20200418093136/http://www.charltonslaw.com/newsletters/china-news-alerts/cn/2016/489/9.pdf)，3月10日生效
4. `2016-2-28 09:58:48` **帖子** [【教程】在学校利用网宿教育网CDN/国外IPv6 CDN加速Steam下载 - 平台研讨 - SteamCN 蒸汽动力](https://steamcn.com/t170155-1-5)
    省略其他不相关的内容

    >在国内使用Steam客户端时，默认选择了中囯节点的下载服务器，域名为cdn.mileweb.cs.steampowered.com.8686c.com
5. `2016-04-08 12:08:23` **帖子** [8086c.com？CDN劫持还是steam的国内CDN？](https://steamcn.com/t180448-1-1)
    精简帖子信息

    >IP是常州电信，并且测试了换DNS并不能解决域名重定向问题
    >
    >Steam网页源代码上的域名都变了，而不是从akamai跳转过去，Valve肯定是知道的。而且只有当你是国内IP的时候才会使用这个CDN，一般只有网站自己才会做这种事情
6. `2016-04-10 00:23:25` **帖子** [steam（仅限国区）已启用8686c.com（万网）CDN，来解决移动屏蔽图片问题](https://archive.is/HU43I)
    >前情提要：8086c.com？CDN劫持还是steam的国内CDN？
    >目前cdn.steamstatic.com的图片被导向了cdn.steamstatic.com.8686c.com。
    >经过whois查询，8686c.com是来自万网旗下的公司的CDN（网宿科技）
    >
    >刚开始我以为是域名劫持（这个域名实在是太可疑了，太像联通劫持404页面的样子了）。
    >但是后来经坛子里的人提醒这串地址是嵌入网页源代码之中的，而不是跳转。
    >经过我与一票人的实验 最后得出结论
    >
    >国区帐号下，steam商店的图片由8686C提供
    >其他区域帐号依然是旧版本CDN
    >
    >于是图片服务器也分区了
    >
    >虽然看起来有利于国内玩家，但是这个举动似乎说明了什么。。。。（G胖开始在国内黑白两道混了？）
7. `2016-05-15 12:32`蒹葭游戏汉化组创始人、组长**改了名的哈里斯基**在**微博**上发布了一则关于steam会在国内玩不了的信息

    发信息后不久就被删除了

    >[打码截图📷](/img/steam/93871788.jpg)
    >[清晰截图📷](/img/steam/50218944.jpg)
8. `2016-08-12` **公告** [北京翼晰科技有限公司正式收购SteamCN正版游戏论坛](https://web.archive.org/web/20200708035900/https://mp.weixin.qq.com/s?__biz=MzI1MjM5MDk5NA==&mid=2247483800&idx=1&sn=301bcde99830339dbc81aa6012f313ee)
9. `2016-11-07 19:38:21` **新法案通过** [中华人民共和国网络安全法（2016年11月7日第十二届全国人民代表大会常务委员会第二十四次会议通过）](http://www.cac.gov.cn/2016-11/07/c_1119867116.htm)
10. `2017-03-09之前 具体时间未知`steam群组**中国共产党**被GFW屏蔽，几天后(尚无资料)G胖关闭了这个群组并把曾经加入了群组的人上了无法暂时个人主页的黑名单。[资料来源](https://archive.vn/l1bO9 "狗胖子开始处理膜X用户，想赚中国的钱就要先向……低头。上周，万里长")、[时间来源](https://web.archive.org/web/20180713134641/https://tieba.baidu.com/p/5013992646?pid=105030907901&cid=0)

    >[主页不能展示📷](/img/steam/93977024.jpg)
    >[该群组的主页📷](/img/steam/14518426.jpg)
11. `2017-04-20 21:05` **腾讯新闻** [专访WEGAME平台负责人：恢复国内游戏生态 扶植国内优质项目 腾讯网](https://web.archive.org/web/20200708032559/https://games.qq.com/a/20170420/068669.htm)

    同时间同样评论的另一个新闻标题，电脑版已删除，手机版还在：[~~WEGAME平台：恢复国内游戏生态 扶植国内优质项目~~](https://web.archive.org/web/20200708035020/https://xw.qq.com/cmsid/2017042006866900)，但是两条新闻在`2017年1月27日左右`对比后发现有一些地方文本不同。
12. `2017-04-21 11:57` **触乐新闻** [WeGame群访记录：若Steam出现服务器、支付方面的问题，绝对跟腾讯无关 - 触乐](https://web.archive.org/web/20180129133347/https://www.chuapp.com/?c=Article&a=index&id=282876)

    和上面的腾讯新闻的文本对比在这里: [diffchecker🔗](https://web.archive.org/web/20181009064019/https://www.diffchecker.com/OR6gPGjd)
13. `2017-4-7 01:56:00` **steamcn帖子** [Steam图片资源链接重定向V3 [移动/联通]](https://archive.is/EmeHv)

    省略帖子中手动劫持的方法

    >V社不知道发什么神经又把国内的图片CDN切换到其他域名去了(又是被移动域名关键字屏蔽的)\\
    >不过原来的网宿8686c还有保留,所以做了这个.将就下先
14. `2017-04-19 23:28` **NGA论坛** [[ 在此输入喷点 ] 从TGP到wegame，等待我们的会是什么？](https://web.archive.org/web/20180712025701/https://webcache.googleusercontent.com/search?q=cache:Mw80VWmcPl4J:bbs.ngacn.cc/read.php?tid=11437668)
15. `2017-04-20 19:01:53` **新闻** [腾讯谈Steam：在国内发生任何问题和我们无关](https://web.archive.org/web/20170526024043/https://www.ithome.com/html/game/305355.htm)，原3DM新闻以及IT之家的转载已经被删除，这里是 Wayback Machine 备份的IT之家的转载新闻，Wayback Machine 无法保存IT之家的评论。

    >在经历了各种爆料预热之后，腾讯的WeGame平台在今日的UP 2017腾讯互动娱乐年度发布会上正式发表了，作为直指全球化的腾讯全新游戏平台，将于2017年7月份上线，那么同样是游戏平台的Steam会否因此受到影响呢？
    >
    >在这之前，就有一些玩家担心WeGame的上线会否影响到Steam在国内的发展，各种推测也是层出不穷，从商业竞争的讨论上升到了阴谋论，对此腾讯方面也进行了回复。
    >
    >腾讯公司副总裁王波表示，不管是Steam还是友商，还是更希望一起把这个领域重新恢复起来，盼望能够看到越来越多的玩家玩到更加多类的游戏，让这个蛋糕和生态越来越大。并且他还表示，有信心能够把自己该做的事情做好。最后他还发布了“官方声明”：Steam在中国出现服务器，支付等任何问题，绝对跟腾讯无关。
    >
    >从最近的发售计划来说，官方更关注独立游戏，近期玩家们会看到一些耳熟能详的独立游戏登陆Steam。
    >
    >腾讯方面澄清了一些玩家猜测的，因为要去发展WeGame而做出一些事情来干扰Steam，而Steam日后在国内可能会出现的问题也是和腾讯无关的，腾讯会努力搞好自己的平台，而不是去“使绊子”阻碍别人来达到自己的目标。
16. `2017-05-01 20:53` **新闻** [【图说天朝】steam上不得擅自成立党支部](https://web.archive.org/web/20200419061247/https://chinadigitaltimes.net/chinese/2017/05/【图说天朝】steam上不得擅自成立党支部/)

    里面讲述了steam上的一些组先是被墙了，steam采取了措施关闭了违规的群组
17. `2017-05-04 19:39` **steamcn帖子** [【Steam已修复该问题】Steam图片资源链接重定向V3 [移动/联通]](https://steamcn.com/t261420-1-1)

    标题修改了，这个问题已修复。
18. `2017-05-20`101、103错误开始在贴吧出现，不过还很少量
19. `2017-06-01 11:03:25` **法案生效** [《中华人民共和国网络安全法》6月1日起实施](https://web.archive.org/web/20170811171714/http://www.cac.gov.cn/2017-06/01/c_1121068451.htm)
20. `2017-06-05`101、103、105错误开始在贴吧里陆续出现
21. `2017-06-07 01:49` **帖子** [关于近日steam访问异常的简单解决方案](https://tieba.baidu.com/p/5150230370)

    >通过这两天的观察，部分dns服务（比如某些电信，某些联通，某知名dns114）不再正常解析steam域名，并且有扩大的趋势。\\
    >但目前ip还没有被封，在不使用魔法上网的情况下暂时还可以通过修改dns处理。
    >
    >...省略解决办法....
    >
    >实际上不正常的dns也能得到一个ip地址，但这个地址会“连接被重置”，这和谷歌是一个套路的。所以??\\
    >14年16年都发生过，这次呢（这次多了wegame啊）。
    >
    >[如何查看自己的steam是否被放逐📷](/img/steam/26980862.jpg)
22. `2017-06-08 08:46` **帖子** [steam是不是已经遭到了屏蔽？](https://web.archive.org/web/20190409175013/http://bbs.3dmgame.com/thread-5592941-1-1.html)

    >今天上steam就发现很多商店页面的cdn都遭到了connection reset。\\
    >我北方某城电信线的，已经测试如下的ip都ban掉了，第一下可能还能连，后续都没戏。\\
    >*6楼*:江苏的，问了这边的电信客户经理，应工信部新政策要求，许多服务商需要提供各类资质证明，没提供的一律封
23. `2017-06-08` **游戏** [墙](https://web.archive.org/web/20181002024909/https://store.steampowered.com/app/635070/THE_WALL/)开始在steam上发行([绿光页面](https://web.archive.org/web/20200419061832/https://steamcommunity.com/sharedfiles/filedetails/?id=909799960)、[社区页面](https://web.archive.org/web/20200419061841/https://steamcommunity.com/app/635070))\\
    然而作者毫不保留露出了自己的QQ邮箱......后果后面有记录\\
    作者的常用用户名叫 玫瑰狗
24. `2017-06-15 14:28` **帖子** [关于103的问题，看了那个帖子，我又上去看了一下](https://tieba.baidu.com/p/5164174953)

    帖子认为是一个鉴赏家的名字被拦截了，浏览就会阻断steam的所有域名

    >*9楼楼中楼补充道*:一个IP段都会遭殃，持续90秒\\
    >12楼: 不错，操作太慢这个解释可以接受。但我觉得还是有个疑点。论坛有人反应4月份那个鉴赏家就会造成103，为什么等这么久才大规模爆发。\\
    >18楼: [被阻断动图📷](/img/steam/65245738.jpg)
25. `2017-06-16前` 关闭腾讯软件就能够连接上steam这一消息被较为广泛的传播(黑桐谷歌也发微博称)

    *有人确认了这可行，也有人确认了这不可行。*
26. `2017-06-16 10:50` **帖子** [【吧务组】暂时禁止关于steam错误的个人主题贴](https://web.archive.org/web/20180724034605/https://tieba.baidu.com/p/5165583121)
27. `2017-06-22` **公告**&**新闻** [巨头抢滩百亿红利 网宿卡位力推VR承载平台](https://web.archive.org/web/20200419065247/https://www.wangsu.com/content/details45_2756.html) 最后一段首次(我还没有找到更早的官方资料)公开网宿和 steam 合作，而且说法还有保留。([中国网](https://web.archive.org/web/20200419065300/http://finance.china.com.cn/industry/20170622/4259141.shtml))

    >事实上，早在2016年8月，CDN行业龙头网宿科技在CDN下载产品中已经新增VR套餐，专为VR内容提供下载加速服务。通过专有下载私有传输协议、防劫持、防篡改等多种安全策略以满足VR游戏快速、安全的分发需求。目前，全球范围内包括HTC、steam等多家知名VR游戏及分发平台均为网宿客户。
28. `2017-06-26 20:57` **帖子** [关于最近steam老是错误101 103.. （应该正确）解决方案](https://tieba.baidu.com/p/5162665305)

    >28楼:可以试试在103后右键返回，你会发现你的网址是多跳了一次。

    *有15条回复都是称赞或者实验成功了的*
29. `2017-06-26 23:02:51` **帖子** [【科普】101、103、105意味着什么](https://steamcn.com/t284467-1-1)

    里面详细的描述了101、103、105的区别和 DNS 是否生效。
30. `2017-07-14 21:20:52` **图片** [恶意高流量的敏感链接导致steam继续被封锁](https://steamcn.com/forum.php?mod=viewthread&tid=280638&page=10#pid4457536)
31. `2017-07-19 13:35:46` **《墙（THE WALL）》的作者说** [我被相关部门批评教育了。我人没事。大家不用担心。](https://web.archive.org/web/20200419061706/https://cowlevel.net/question/1912997/answer/2198681)
32. `2017-07-19` **帖子** [[爆卦] Steam遊戲《牆》在中國被封鎖並鎖區](http://disp.cc/b/163-a9eH)

    >中國的影片或遊戲評論網站上，關於這款遊戲的訊息都已經被下架。\\
    >這款遊戲在Steam上中國區也已經鎖區了，作者已經被叫去"喝茶"，並且據消息指出。Steam不是作者自己設定鎖區的，是今天自己突然就鎖區了，\\
    >還不確定是否為Steam收到中國官方的通知之後做出的動作..
33. `2017-07-21 16:13` **帖子** [steam 10X错误解决办法，忍无可忍再发一帖](https://tieba.baidu.com/p/5235680550)❌

    原帖已被删除，但还是能够被证实这篇帖子存在并且内容无误：[【转帖】](https://steamcn.com/t292119-1-1)

    >吧里各种解决办法满天飞，包括置顶帖的，没一个说到点上。\\
    >由于众所周知的原因，网宿科技CDN不再为大陆提供steam网页加速服务，6月初国内steam IP都解析到了Akamai CDN上，然而Akamai CDN IP被干扰不是一天两天了。DNS解析的原则是解析到响应最快的IP上，但这些IP有很大几率被干扰，表现就是商店打不开，如下图所示，这些ip会导致10X。\\
    >不同ISP不同地区对Akamai CDN干扰情况不同，修改hosts工具提供的IP可能张三能用，李四不能用，或者A时间可以用，B时间又不能用的情况。因为对IP的干扰不是持续，而是断断续续。\\
    >根本解决10X的办法还是挂梯子，因为你不能保证改hosts的这个IP永远不会被干扰。或者更简单办法，这里有个小工具，改hosts之前先检查下这个IP你那里是否可用，连续测试10次，如果某个ip测试期间都没被干扰，可视为稳定IP，填入hosts即可，如下格式：\\
    >23.63.219.132 store.steampowered.com ; 23.63.219.132 steamcommunity.com\\
    >改hosts有可能造成个人资料卡在验证登陆状态，SSL证书原因，重启下steam即可。\\
    >最后特别声明：感谢小工具原作者，他曾经发过类似的帖子但石沉大海，借花献佛再次把这个小工具拿出来。
34. `2017-07-23 17:31` **帖子** [【吧务组通告】对于近期删除10X,1xx错误部分相关贴公告](https://tieba.baidu.com/p/5239340529)

    >7楼楼中楼: 我狂点 商店 然后就好了

    *有10个人回复10个人成功了*
35. `2017-07-30 12:25:08` **帖子** [聊聊101,105问题](https://steamcn.com/t293805-1-1)
36. `2017-07-30 22:57` **孔子云老子曰发言** [56楼](https://tieba.baidu.com/p/5150230370?pn=2)

    >主要还是akamai的分包服务主要服务于油 管和脸 书，导致污染严重波及steam。之前国内为steam提供加速分包的公司突然翻脸不干了，其它的就不多说了……
37. `2017-08-07 18:49` **触乐网**发布了[微博](http://weibo.com/3957040489/Fg1hVbztX?from=page_1006063957040489_profile&wvr=6&mod=weibotime)

    >在最新一期的英国游戏杂志《Edge》上，知名游戏记者Simon Parkin发表了一篇名为《东诺》（Eastern Promise）的文章，其摘要是“一场争夺世界上最大、变化也最快的PC游戏市场的战争”。文章第一段，作者爆料一位腾讯高级经理曾在2016年11月上海的《最终幻想15》发布会后向某国内游戏开发者透露：“等到时机成熟，Steam在中国将不复存在。”\\
    >[图1](/img/steam/69444902.jpg) [图2](/img/steam/61188460.jpg) [图3](/img/steam/34063224.jpg)
38. `2017-08-08 14:32` **腾讯WeGame**发布了[微博](http://weibo.com/6068787464/Fg92hxBIJ?from=page_1006066068787464_profile&wvr=&type=comment)

    >早上听说有外国友人提到，WeGame 有人在去年 FF15 发布会现场爆了个什么料，一脸懵逼赶紧自查，发现我们确实没人去过，害的老板怀疑我们偷着去玩[抓狂]！话说 WeGame 一直倡导公平竞争，玩家的游戏体验才是我们最关注的，所以给开发商的分发标准分成其实是 70%，就是要激励大家提供更好的游戏。至于有人猜测的那些离谱手段，我们真心不搞这些\[左哼哼]\[右哼哼]。有问题尽管找 G 哥，这里有不匿名的靠谱信息\[二哈]。
39. `2017-08-10 11:13` **新闻** [腾讯投资《绝地求生：大逃杀》开发商Bluehole 为引入中国做准备](https://web.archive.org/web/20200419061649/https://www.jiemian.com/article/1538312.html)
40. `2017-08-10 16:33:56` **新闻** [那篇腾讯要墙Steam的爆料，这里有全文](https://web.archive.org/web/20200419061642/https://ent.163.com/game/17/0810/16/CRG8R2LB00318QE8.html)。
41. `2017-08-17 04:06:09` **帖子** [101/103已解除???不可描述的阻断似乎已经解除?](https://steamcn.com/t299518-1-1)

    >目前全国GET统统都是正常的..当然不排除是某个设备突然抽风了..\\
    >这是水区,我说话可不负责哈,没准明早起来又\\
    >出现 102 问题的打开hosts，找到steam的相关字段，删掉就可以了\\
    >5楼回复:目测大范围解除了，就算遇到关键词也不再会短暂性阻断
42. `2017-11-26` **知乎** [华中科技大学校园网限制steam的下载](https://www.zhihu.com/question/68631319)

    >从贴吧里的反应来看，应该是彻底的封禁了steam。[链接1](https://web.archive.org/web/20180106220243/http://tieba.baidu.com/p/5450503489),[链接2](https://web.archive.org/web/20180106220246/http://tieba.baidu.com/p/5450646499)
43. `2017-11-28` **报告** [2017年中国游戏行业发展报告](http://www.cnccea.com/index.php?m=newscon&id=408&aid=770) 由[中国文化娱乐行业协会](http://www.cnccea.com/index.php?m=newscon&id=411&aid=596)信息中心与中娱智库联合课题组编撰。

    稍微介绍一下这个**中国文化娱乐行业协会**，*信息详细在* [*中国文化娱乐行业协会简介*](http://www.cnccea.com/index.php?m=content&id=402)

    >中国文化娱乐行业协会是由民政部登记管理，文化部业务主管，公安部支持的国家一级协会。发起单位包括万达文化产业集团、小米、腾讯、网易、搜狐、联想、温莎、好乐迪、世宇、希力、大玩家、雷石、视易以及各省、市级行业协会等最有代表性的上百家文化机构，涉及歌舞娱乐场所、游戏机经营场所、网络游戏、手机游戏、家庭娱乐、室外游乐园、会展、文化娱乐内容技术服务等多个业态，涉及文化娱乐行业全产业链。

    ......后略
44. `2017-12-16 12:03:37` **讨论贴** [Steam社区页遭域名污染+HTTP连接重置双重封锁](https://steamcn.com/t339379-1-1)
45. `2017-12-19 11:31` **新闻** [Steam社区/个人资料等界面被屏蔽 但有简便解决方案](http://www.ali213.net/news/html/2017-12/337053.html)
46. `2017-12-19 13:10:44` **新闻** [Steam Community access has been blocked in China](http://www.pcgamer.com/steam-community-access-has-been-blocked-in-china/)
47. `2017-12-19` **讨论贴** [G胖疑似自我阉割了[国区]论坛功能](https://steamcn.com/forum.php?mod=viewthread&tid=340304&page=1&authorid=498096)

    >今天(12月19日)早上我尝试进入steam社区的论坛版面，无论如何都进不去，包括用魔法。\\
    >换浏览器、取消hosts都无效。\\
    >效的是登录我的美小号，或者退出登录。\\
    >论坛版面与国区账户无缘了。这个可能是我的个例，楼下的你们能打开吗？
48. `2017-12-22` **整合贴** [近期Steam无法打开社区、库存页面，出现错误代码101、110、113、118等解决办法](https://steamcn.com/t342004-1-1)

49. `2017-12-23 16:08:49` **网络测试** [17CE上的对cdn.steamcommunity.com在华网络测试](http://www.17ce.com/site/http/201712_7b17c36238fa05f8abbaed8024760229.html)

50. `2017-12-24 14:42` **讨论贴** [steam是这样回复我的，谁给我解释解释，我感觉说的好含糊啊](https://tieba.baidu.com/p/5490856537)

    >[与客服交流的图片📷](/img/steam/28680806.jpg)

51. `2018-01-22 22:43:33` **行动通告** [北京启动网络游戏专项整治行动](http://www.xinhuanet.com/legal/2018-01/22/c_1122297489.htm)

52. `2018-01-24` **软件** *Tower Accelerator* 在 steam 上发行(现已下架)

53. `2018-01-27 03:15` **新闻** [网络游戏究竟应该靠什么赢得未来](http://news.gmw.cn/2018-01/27/content_27473422.htm)，大多重量级的网媒在一天内发布了。

    关于这篇新闻及其来源的细节:
    + 新闻里的配图的创作公司是 [EG365](http://eg365.cn/aboutus)，官网里看起来不像普通人可以使用的配图服务。
    + [山东师范大学齐鲁文化研究院](http://www.qlwh.sdnu.edu.cn/)在2018年01月16日的下午成立了[齐鲁文化研究院新闻宣传小组](http://www.qlwh.sdnu.edu.cn/info/1038/1244.htm)
    + `山东师范大学齐鲁文化研究院` + `网瘾` 关键词的新闻
        + `2013-04-18` [山师大教授耗时十余年科研 戒除网瘾获突破进展](http://www.chinadaily.com.cn/hqgj/jryw/2013-04-19/content_8801572.html)
    + 以**山东师范大学齐鲁文化研究院**的名义在近年发表的关于戒网瘾的新闻:
        + `2015-06-10` [首家数字艺术哲学研究智库落户山东师大](http://sd.china.com.cn/a/2015/jykj_0610/240272.html)
        + `2017-12-07` [实施数字艺术通识教育很有必要](http://www.rmzxb.com.cn/c/2017-12-07/1893042.shtml)
        + `2014-11-14` [国家社科项目“数字艺术伦理学研究”研讨会在山东师范大学举办](http://www.qlshx.sdnu.edu.cn/page.jsp?urltype=news.NewsContentUrl&wbtreeid=10445&wbnewsid=95767)
    + 作者之一的**马立新**教授发表的数篇网瘾相关的文书:
        + `2007年4期` [论网络游戏的本体特征-《山东师范大学学报》](http://www.wanfangdata.com.cn/details/detail.do?_type=perio&id=sdsdxb-rwshkxb200704002)
        + `2013年5月10日` [论数字艺术德性生成机制-《理论学刊》](http://www.wanfangdata.com.cn/details/detail.do?_type=perio&id=llxk201302025)
        + `2013年5期` [《易经》哲学与当代低碳文化建设-《广东社会科学》](http://www.cqvip.com/qk/80603x/201305/47188678.html)
        + `2014年5月` [高碳网络文化的危害、成因与管控-《上海师范大学学报》](http://qktg.shnu.edu.cn/skb/ch/reader/create_pdf.aspx?file_no=201403017&year_id=2014&quarter_id=3&falg=1)
        + `2015年7月` [高碳艺术精神损害研究-《上海师范大学学报》](http://qktg.shnu.edu.cn/skb/ch/reader/create_pdf.aspx?file_no=201504013&flag=1&journal_id=shsfqksskb&year_id=2015)

    还有几篇就不在这里列举了，这些资料已经足够了。
54. `2018-01-31` **帖子** steam 社区网页显示 **您的网站暂时无法访问**

    + [STEAM市场被工信部关闭？](https://steamcn.com/t355700-1-1)
    + [手机steam这是玩完了？？？已用UU加速。](https://tieba.baidu.com/p/5535223095)
    + [你们的steam有这样么](https://tieba.baidu.com/p/5535178758)
    + [这是什么情况?](https://tieba.baidu.com/p/5535236915)

    似乎是都是用了网易UU加速器才出现这样的错误，搜索引擎上查询了一下文字，并没有没得到有价值的信息
55. `2018-02-03` **软件** [Tower Accelerator](http://steamcommunity.com/app/758670/discussions/0/1699415798765578829/) 在 steam 上被下架
56. `2018-02-10 19:30` **新闻** [专家：青少年登录境外游戏服务器严重 应尽快纳入国内监管体系](http://society.people.com.cn/n1/2018/0210/c1008-29817234.html) [讨论帖](https://archive.vn/mQ6H8)
    > **gledos注: 虽然内容很长，但文章似乎有几分重量**\\
    > 人民网北京2月11日电 （张晓赫）随着寒假的到来，家长们发现，
    > 一直替代自己管理孩子玩游戏的防沉迷系统“失效”了：在一款名为《绝地求生》的风靡游戏中，
    > 用户可以轻易登陆国外服务器，而国外并没有类似设置。
    > 专家表示，海外游戏中国本地化势在必行，“这既包括符合国情的改造，也包括纳入到国内相关监管、规则体系内”，
    > 应尽快利用新时代中国特色社会主义价值观，道德观，审美趣味，对海外游戏进行必要的改造、优化，以适应国情，
    > 为广大用户提供更加健康、积极的精神文化产品。\\
    > 《绝地求生》是一款2017年3月上线的多人战术竞技类游戏，截至今年1月，其全球总销量已超过3000万份，
    > 成为历史上销量最高的PC游戏。这中间也少不了中国游戏者的参与，根据官方数据，有64%的玩家使用中文操作系统。
    > 进入寒假，问题也随之而来。由于很多游戏没有引进正版，服务器没有实现本地化，很多青少年在登录境外服务器后，
    > 既难有效防沉迷，也很容易接触到大量不良信息。\\
    > 记者从北京市几位初中教师处了解到，寒假开始后“家长群”里都在讨论《绝地求生》，
    > “过去玩游戏可以受到防沉迷系统的约束，家长也可以限制学生的游戏时间。但是现在这个游戏不在防沉迷系统里，
    > 家长上班后学生仍可以玩。”\\
    > 近年来，主管部门不断强化保护未成年人合法权益，指导企业完善游戏防沉迷机制。经过努力，
    > 一方面是在主管部门的要求和积极推动下，防沉迷系统广泛应用；另一方面，
    > 国内游戏公司也根据规定对于游戏内的聊天、对话等进行了处理，基本解决了以网络游戏作为渠道传递有害信息的问题。
    > 由此，我国已经初步建立了严格的网络游戏监管制度。
    > 比如，在腾讯一些游戏的防沉迷系统中，不超过12周岁的用户在晚上9点至翌日8点之间不能进行游戏；
    > 白天累计登录游戏时长1个小时，也将被强制下线，当日不能再登录。此外，家长也可以掌控孩子游戏登录和消费的信息。
    > 家长孙先生告诉记者，他发现国外服务器里外挂特别严重，“没有公平竞争，孩子就是想要买外挂，不用瞄准就打败对方了。
    > 我想这对于正在成长中的孩子的影响，是非常大的。”\\
    > 张先生也发现，在《绝地求生》中除了有很多暴力、血腥画面，许多玩家也不断“爆粗口”进行互相辱骂。
    > 而在他经常玩的国内游戏中，这些情况或者被改造、或者被屏蔽，“不应该让孩子接触，
    > 应该尽快将它按照国内的习惯和要求进行改造。”\\
    > 除了一般用户，类似情况在网吧也非常严重。根据中国互联网上网服务行业协会发布至2017年第三季度的报告，
    > 《绝地求生》在2017年前三季度都是网吧热门游戏。但一些媒体报道披露，在一些网吧游戏外挂严重，
    > 引发玩家的进一步模仿、购买外挂。此外，由于国外服务器基本不存在监管，涉黄、涉暴等有害信息泛滥，
    > 对网吧用户产生了较大的负面影响。近日，甚至发生了外挂玩家在著名直播平台约战、直播外挂大战，
    > 并进行外挂推销的情况。\\
    > 记者调查发现，类似情况不仅存在于《绝地求生》。由于跨境支付的日益便利，
    > 外国大牌游戏发布后很快就可以在国内买到，甚至可以在国内进行预约。
    > 对于由此引发的问题，专家解释，主要是因为游戏未正式引进国内，国内已经广泛使用的反沉迷系统、
    > 反外挂系统都是与游戏服务器相结合，无法在国外服务器上应用。\\
    > 业内也认为，互联网时代，更好解决网络互通带来的挑战，应创新机制，
    > 尽快将相关网络文化产品纳入国内的监管和管理体系。而具体到网络游戏，最佳路径之一，
    > 就是尽快通过引进符合中国国情的正版游戏，建设监管指导下的国内服务器。\\
    > “对进口游戏的内容审查我们是有一套体系的，是以内容为标准的。对真正的文化遗产，优秀的文明我们要吸收；
    > 不符合我们国情的，和我们价值观有很大冲突的，我们要处理，这个我们是能控制住的。”
    > 清华大学新闻与传播学院副院长、文化部文化产业专家委员会委员熊澄宇表示，
    > 引进游戏后对不符合的内容进行一些技术处理和内容处理，使其符合标准也是可以的，这与进口电影的情况类似。
57. `2018-02-11 下午` **知乎** [如何看待人民网发文《青少年登录境外游戏服务器严重，应尽快纳入国内监管体系》？](https://www.zhihu.com/question/267002275)
    参与讨论的人数超过1000
58. `2018-05-09 21:55:13` **IT之家** [Steam 测试版新增 6 个国内节点：包括青岛、乌鲁木齐等城市 - Steam,青岛,乌鲁木齐 - IT之家](https://archive.is/RIO6H)
59. `2018-05-28 17:24` **贴吧** [6.1【教程】国内 Steam社区 / 商店 报错及打不开的解决方法](https://web.archive.org/web/20180711132403/https://tieba.baidu.com/p/5720575784) 吧主发帖。2018年7月11日进行了顶置
60. `2018-06-12 07:12:34` **IT之家** [Valve 宣布与完美合作，Steam 将正式进入中国 - Valve,Steam - IT之家](https://archive.vn/Qnq1E)
61. `2018-06-12 07:34` **新闻** STEAM CN
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
        > 此次与中国企业合作的美国Steam游戏平台拥有全球两万多家游戏开发商提供的游戏产品，是世界上最大的数字娱乐分销平台。按照战略协议，将由中国企业完美世界建立平台，并被授权使用Steam商标，按照中国游戏产品上线流程，从平台挑选游戏，申报版号及备案，接受监督，让海外游戏健康有序，服务中国市场。
        >
        > 今年上半年，中国游戏收入超过1000亿人民币，继续占领全球最大市场地位。据游戏产业专业分析数据伽马数据统计，截止到去年年底，中国正式审批，获得版号的游戏，一共9800款，但是实际上还有大量的游戏处在监管真空或模糊地带，也影响游戏产业发展秩序。
        >
        > 中国游戏产业报告分析师滕华表示：“在国外的游戏平台上面，聚集着大量的中国玩家，而这些中国玩家接触到的，跟正在玩的游戏远远超过了9800款，大概有2万多款。”
        >
        > 专家认为，这一平台的建立对游戏产品和产业管理模式而言，是一个管理创新，实现了更有效、更科学监管。另一方面，中国游戏可以借助这一平台更好地与国际接轨，实现中国游戏更好地走出去，帮助中国中小游戏研发企业拓展海外市场。
62. `2018-06-13 16:18:07` **资讯** **讨论** [Valve：Steam中国版不会对玩家已有游戏产生影响 - vgtime.com](https://archive.vn/VvEPE)
63. `2018-06-13 19:55` **资讯** [关于Steam中国锁区，Steam的官方回复怎么说？丨VR陀螺](https://archive.vn/45g7R)
64. `2018-06-13 21:56:30` **视频** [中国玩家的福音：央视宣传steam中国版，力求按中国游戏上线流程，让海外游戏健康有序服务中国市场](https://web.archive.org/web/20180615073029/https://www.bilibili.com/video/av24829932/)
65. `2018-06-14 10:35:53` **资讯** [Steam这么“黄暴”的平台，竟然上央视了？这是单机游戏的机会还是末日？ - 知乎](https://archive.vn/zwtbN)
66. `2018-06-14 13:53` **新闻** [Steam中国的背后：完美与Valve的挑战](https://archive.vn/32B7a)
67. `2018-07-10` **贴吧** 101错误开始蔓延到一部分玩家的商店主页
68. `2018-07-31 14:08` **新闻** [Steam中国开始招聘员工！惨遭玩家怒喷：滚出中国！](https://web.archive.org/web/20200527123526/https://www.sohu.com/a/244361654_100191223?sec=wd) 内有Steam中国招工信息与帕斯亚科技对Steam中国的认识
    + [今天大家是不是都steam打不开了？网页和软件都打不开了！](https://web.archive.org/web/20180710124939/https://tieba.baidu.com/p/5789930101)
    + [今天服务器是不是又炸了、、、](https://web.archive.org/web/20180710124754/https://tieba.baidu.com/p/5789953505)
    + [为什么你们steam商店进不去了，但是我进得去啊](https://web.archive.org/web/20180710124509/https://tieba.baidu.com/p/5789660785)
    + [商店进不去啊，好几天了，开加速器也只能进进个人主页，](https://web.archive.org/web/20180710124342/https://tieba.baidu.com/p/5789810337)
    + 11日
    + [steam炸了？ 开加速器也没用？](https://web.archive.org/web/20180711132630/https://tieba.baidu.com/p/5791371399) *错误代码: 102*
    + 12日
    + [TX上架围攻了，有中文的](https://tieba.baidu.com/p/5791875321)
    + [steam怎么商店也进不去了。开了置顶软件。难道真的凉了么。](https://web.archive.org/web/20180712022657/https://tieba.baidu.com/p/5791892218)
    + [今天才知道steam中国的消息，来贴吧看看似乎没什么风头，是大家都等着看，还是有什么好消息？](https://web.archive.org/web/20180712022813/https://tieba.baidu.com/p/5791876707)
    + [装了Wegame Steam商店就显示103](http://web.archive.org/web/20180712023444/https://tieba.baidu.com/p/5791881116)
    + 14日
    + [steam不能创建账户了吗？](https://web.archive.org/web/20180714064205/https://tieba.baidu.com/p/5794821414)
    + [steam 商店打开，有大佬知道怎么解决吗](https://web.archive.org/web/20180714063924/https://tieba.baidu.com/p/5794763528)
    + [不用加速器steam市场就打不开怎么办？](https://web.archive.org/web/20180714060529/https://tieba.baidu.com/p/5794560012)
    + [错误代码101怎解决？](https://web.archive.org/web/20180714050551/https://tieba.baidu.com/p/5151618796)
69. `2018-10-30 11:48` **新闻** [刚刚！Steam中国北京运营开启，Steam中国真的来了！_游戏](https://web.archive.org/web/20200527123521/https://www.sohu.com/a/272143651_535013)
70. `2019-11-11 09:43` [严格控制未成年人使用网络游戏时段、时长_服务信息_中国政府网](https://web.archive.org/web/20200609171539/http://www.gov.cn/fuwu/2019-11/11/content_5450800.htm) [archive.is](https://archive.is/46U3p)
71. `2020-04-27 17:07:43` **新闻** [终于来了！Steam国服域名曝光：玩游戏不掉线了？](https://web.archive.org/web/20200508143012/http://www.bajieyou.com/new/7b2f9fd4057645949e7fbe87eaa3075b) [新浪网](https://web.archive.org/web/20200508143013/https://k.sina.com.cn/article_5061312402_12dad7f9202700sy1i.html)
    + 4月27日讯，根据Keylol其乐社区坛友提供的情报，
      我们发现目前完美世界的手上已经拥有了多个Steam相关的网站域名与相关证书，
      其中wmsjsteam（完美世界Steam）这个域名在今年2月份的时候就已经成功取得了证书，
      生效日期从2020年2月19日起至2022年2月23日为止。
72. `2020-05-05` 完美世界的蒸汽平台
    + `2020-5-5 12:06 編輯` [蒸汽平台会强制全屏 5 秒《健康游戏忠告》](https://archive.vn/GaFoT)
    + `2020-5-6 19:15 編輯` [蒸汽平台會強制全屏 5 秒《健康遊戲忠告》](https://archive.vn/XYbqf)
    + `2020-5-8 15:16 编辑` [蒸汽平台會強制全屏 5 秒《健康遊戲忠告》](https://archive.vn/7QKHo)
    + PTT上的讨论 [Fw: [閒聊] 中國的蒸汽平台會限制遊戲時間 - 批踢踢實業坊](https://web.archive.org/web/20200508143401/https://www.ptt.cc/bbs/Steam/M.1588677634.A.C96.html)
73. `2020-05-19` **新闻** [Valve quietly releases censored Steam China client to alpha - CS:GO - News - WIN.gg](https://archive.fo/Yc4dX)
74. `2020-05-24` **新闻** [Valve Releases Censored Chinese Steam Client for Alpha Testing – Sankaku Complex](https://web.archive.org/web/20200524112247/https://www.sankakucomplex.com/2020/05/24/valve-releases-censored-chinese-steam-client-for-alpha-testing/)
75. `2020-05-27 20:55:29` **IT之家** [Steam 中国版泄露：加入健康游戏忠告，限制未成年人游戏时长 - Steam - IT之家](https://archive.is/VHNXv)
76. `2020-05-31 23:21:55` **IT之家** [《CS：GO》防沉迷错误已修复：Steam玩家需切换至Beta版 - CSGO - IT之家](https://archive.is/Mwtb9)
77. `2020-06-06` **新闻** [News - Client Updates](https://web.archive.org/web/20200606115302/https://store.steampowered.com/news/?feed=steam_client) 、 [News - Steam Client Update Released](https://web.archive.org/web/20200606115322/https://store.steampowered.com/news/62162/)
    + Steam 这几天前后更新了多次测试版的客户端，为了完美世界的防沉迷而更新
    + [Steam Community :: Group :: Steam Client Beta](https://web.archive.org/web/20200606114915/https://steamcommunity.com/groups/SteamClientBeta/announcements)
78. `2020-06-04` **讨论帖** [今日 Steam Beta 修复了多项与完美服有关的问题，建议更新至 Beta 版本 - 其乐 Keylol](https://archive.is/KXmnP)
79. `2020-06-08` **讨论帖** [蒸汽平台不会出现“双重”《健康游戏忠告》 - 其乐 Keylol](https://archive.vn/X8YGL)
80. `2020-07-17` **讨论帖** [Steam 将新增大陆下载区域，包括深圳、杭州和沈阳等…… - 热点聚焦 - 其乐 Keylol](https://archive.is/v9Kjl)
81. `2020-07-28` Wallpaper Engine 登陆腾讯 WeGame
    + **IT之家** [腾讯：热门壁纸软件《Wallpaper Engine》即将上线 WeGame](https://archive.is/3F5mt)
    + **其乐** [WeGame Wallpaper Engine即将于7月30日启动技术测试](https://archive.is/FPP87)
    + **IT之家** [《Wallpaper Engine：壁纸引擎》登陆腾讯 WeGame 商店，即将开启测试](https://archive.vn/E5pXO)，[评论](https://web.archive.org/web/20200801090600/https://dyn.ithome.com/comment/49250a21adb87da4)
82. `2020-07-29` **讨论帖** [Steam CD改区界面变了 - 购物心得 - 其乐 Keylol](https://archive.is/EXDVS)，[steam已更改跨区政策，现在只能用当地支付方式购买游戏或者联系客服才能改，不能再通过IP直接改了，不知道是好是坏 百度steam吧](https://archive.is/9Pk56)
    请注意Steam商店跨区购买是违反Steam用户协议的

    今天早上Steam再次更新了改区方式现在改区界面已经变成了这样，然后Steam又不支持阿根廷那边的货币结算，所以，以后去阿根廷，要么有当地银行卡，要么就找客服了
83. `2020-08-05` steam 添加了新标签 steamchinaapproved ，目前共有20多款游戏属于这个标签下，以下链接如无说明，则均有评论区
    > Steam中国过审游戏标记？
    > ——万狐飞仙
    + [SteamDB 泄露“Steam中国”首批游戏？ - 其乐 Keylol](https://archive.vn/ewTPv)
    + [确认“steamchinaapproved”标签为蒸汽平台过审标签 - 其乐 Keylol](https://web.archive.org/web/20200806025409if_/https://webcache.googleusercontent.com/search?q=cache:Ui-YPqnUq0QJ:https://keylol.com/t628599-1-1)
    + [Steam 中国首批游戏疑似被泄露：超 20 款游戏 - IT之家](https://archive.is/cHgbf)
    + [SteamDB疑似泄露“Steam中国”游戏 大部分为国产游戏 _ 游民星空 GamerSky.com](https://web.archive.org/web/20200806063247/https://www.gamersky.com/news/202008/1310480.shtml)
    + [Steam后台数据库泄露了“Steam中国”的首批游戏 NGA玩家社区](https://archive.vn/lHbNQ)
    + [Steam中国首批游戏疑似被第三方数据库泄露 - vgtime.com](https://archive.is/QnzZW)
    + [Steam中国游戏列表疑似泄露 - 旅法师营地](https://archive.vn/c77vn)
    + [Steam中国首批游戏阵容曝光，地平线黎明时分PC版媒体分出炉，生化3重制全解锁DLC售卖_哔哩哔哩 (゜-゜)つロ 干杯~-bilibili](https://archive.is/wzKF8)
    + **无评论** [Steam China's first batch of over 20 games suspected to be leaked - cnTechPost](https://archive.is/0Ob6S)
    + **无评论区** [SteamDB疑洩露Steam中國首批遊戲 大量國產遊戲在列 電玩狂人](https://archive.is/RyIOg)

<!-- 

[这是真的吗 NGA玩家社区](https://archive.vn/rgmOt) 在隔壁群友看到的，如果是真的话，那?死也不会用的
    steam中国、WAC反作弊

 -->

可能有关的资料
--------------

### 网宿科技相关但没有直接与steam相关的资料

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

### steam 在中国的 CDN 测速

+ [1](http://www.17ce.com/site/http/201604_c2e730ad4d5d756601d01c423539fd7b.html)、[2](http://www.17ce.com/site/http/201602_4e419287a56c8584a6ea0361282b66a8.html)
+ `2018-07-13` [主站 store.steampowered.com 测试](https://www.17ce.com/site/http/20180713_c0ec16e0869f11e8bab64ffc7156171c:1.html)
+ `2018-07-14` [主站 store.steampowered.com 测试](http://www.17ce.com/site/http/201807_04596bd0208b5b3c168a845761dd4b1b.html)

### **CDN** *akamai.steamstatic.com* 域名下的 GFW 阻断情况

+ [根据 greatfire 的信息得出结论：并没用看见是 GFW 在阻断 Akamai](https://zh.greatfire.org/search/all/Akamai.steam)
+ [cdn.steampowered.com 也没有在 GFW 上被拦截](https://zh.greatfire.org/search/all/cdn.steampowered.com)

### 腾讯 wegame 的网络限制行为（疑惑）

+ [关于高延迟/文件损坏/弹窗闪退/多开等问题临时解决方案的公告-新闻中心-天涯明月刀-官方网站-腾讯游戏-电影网游新艺术，这就是武侠](https://wuxia.qq.com/webplat/info/news_version3/5012/5013/5014/5016/m3486/201709/636379.shtml)
    此公告建议用户回退 Windows10 版本到旧版本，并且关闭 Windows10 自动更新
+ [TGP/WeGame驱动导致WSL网络服务异常](https://zhuanlan.zhihu.com/p/33723838)
+ [坑爹的腾讯TGP（WeGame）导致WSL无法连接到端口问题](https://zhuanlan.zhihu.com/p/27731530)
+ [大毒瘤！卸载WeGame解决XPS 15蓝屏问题 - 阅读 - 掘金](https://juejin.im/entry/5b2b15cae51d4558d35facf5)
+ [TGP 驱动导致 WSL 故障 - V2EX](https://www.v2ex.com/t/429742)
+ [蓝屏毒瘤:腾讯居然比360还牛逼！隐蔽的TDI筛选器！](https://www.bilibili.com/read/cv248113/)
+ [发现了tgp里的【无用】驱动【windows8吧】_百度贴吧](http://tieba.baidu.com/p/3637947742)
+ [一上线就说检测到异常 网络连接断开（客服已回复）,沃特碧们的Colg,DNF地下城与勇士 - COLG社区](http://bbs.colg.cn/thread-7258396-1-1.html)
+ [STEAM和WEGAME冲突？](https://steamcn.com/t314958-1-1)

## F.O.A.F

[帖子](https://www.v2ex.com/t/377252)32楼：有种说法是 6 月 1 号 Law of Cyber Security 开始实施后，Steam 不能再用国内 8686c 的 CDN，所以国内用户访问时也使用 Akamai，Akamai CDN 被 GFW RST 导致的

## 非常侧面的资料

[转个A9VG关于psn网络不好用原因的帖子](https://tieba.baidu.com/p/3504351437)

## 腾讯邮箱屏蔽steam邮件事件

注意，这到底是故意的还是无意的我是没有找到证据，当然除了有时候block steam之外还会block 其他的邮件，比如 DMM。但是我是没找到有人被qq邮箱屏蔽了邮件
`2013-07-04` **新闻** [拦截D2邮件,恶性竞争&无意为之？](http://dota2.uuu9.com/201307/447561.shtml)
`2014-08-29` **帖子** [为什么我的qq邮箱收不到完美的邮件。。。](https://tieba.baidu.com/p/3262705495)
`2015-05-07` **帖子** [QQ邮箱出现了新的针对DOTA2方法！求破解](https://tieba.baidu.com/p/3748153998)

## DOTA2刚开服时出现的"腾讯拒绝员"事件

没有什么靠得住的依据的信息我没放上来，同样此事件真实性存疑\\
[帖子](https://tieba.baidu.com/p/2324368326)27楼：基本遇到拒绝都是玩上海服务器和东南亚的，现在只排澳洲表示再也没遇见过拒绝狂魔！！V社真的该对拒绝游戏施加点什么限制因素了，不然TX真的用个几千水军来拒绝基本这游戏中国地区的玩家就可以不用玩了，大家还是去玩lol吧！！

## steam 帐号盗号相关的一些资料

+ `2017-12-31 05:55` [各位steam吧友，本人近期卧  底于steam黑号群，现在曝光](https://tieba.baidu.com/p/5498583590)

    >各位steam吧友，本人近期卧底于steam黑号群，现在曝光黑号群是怎么盗取别人steam账号的。\\
    >1.利用租号网上的账号用软件破解密码（无法改邮箱密码叫做临时黑，卖20-25块）\\
    >2.利用特殊的软件，可盗取steam的账号和原始邮箱（可修改密码邮箱，叫做永久黑45-50等）\\
    >3.白号，盗取的steam号啥都没绑，而且还刚买了游戏（游戏为吃鸡这种最容易被盗）！！！\\
    >以上被盗用和大肆售卖的号，主要用途为绝地求生开启辅助用，基本上都是VAC封禁！！！！\\
    >各位steam吧友，最好设置steam令牌，邮箱最好设qq邮箱，qq邮箱没有被盗成功过的案例，被盗的基本为163邮箱，希望官方能在找回steam账号的步骤越来越严格，这样对打击绝地求生的外挂和减少steam被盗的风险都有好处，望各位吧友，保管好自己的账号。

## 有关 THE WALL 的作者玫瑰狗本人的事情

一个玩家对《墙》这款游戏的[评价](/text/steam/abc.txt)，原文来源自奶牛关，由于《墙》这款游戏的条目被奶牛关移除了，我是在玫瑰狗动里发现他对此点赞的(猜测：可能只要是野蔷薇计划获得key来评测游戏，基本都点赞了的，与是否认同评论无关)，但玫瑰狗对此的评价是：「你特么是真的想了这么多？！」

玫瑰狗有一款没有完成的游戏，叫做 [无信者 - 十三号治疗室](https://www.zhihu.com/question/51926893/answer/131915185)*[backup](http://archive.is/ZjNCe)*
，游戏内容与杨永信息息相关，玫瑰狗也在随后表示了这款游戏的[严肃性](https://cowlevel.net/article/1846170)(可能是被质疑吃人血馒头，跟风)，之后公布了游戏的[设定](https://cowlevel.net/article/1848198)

## steam 在中国网吧的一些资料

+ `2017-10-09 20:03` **帖子** [日，去了趟网吧账号被盗](https://tieba.baidu.com/p/5363625498)

    >本人因为电脑BOOM，无奈去了两天网吧玩吃鸡，结果账号被盗，邮箱被改还绑定了别人手机\\
    >现在向客服发出申请，有发到我邮箱的更改邮箱和手机成功的邮件截图，以及好友送我游戏的历史截图，更有甚者因为我偷懒，所以连我的steam账户名都是我的QQ号（一串数字）。。。\\
    >求问大佬们，这总能找回的吧。。。找回时间会很久么。。。

+ `2017-12-24 12:28` **帖子** [现在的网吧都这么玩的吗](https://tieba.baidu.com/p/5490726117)
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

    https://steamcn.b0.upaiyun.com/archiver/tid-293805.html?page=1
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

提供信息者名单
--------------

感谢：

[spartan1096](https://tieba.baidu.com/home/main?un=spartan1096)