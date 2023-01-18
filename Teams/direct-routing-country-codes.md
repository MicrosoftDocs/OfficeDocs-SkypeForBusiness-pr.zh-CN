---
title: 直接路由国家/地区代码
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: reference
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 阅读本文，查找直接路由的媒体路径国家/地区代码，以便选择最佳媒体路径。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a70dad128987a5fb0df639984be07b623f9ff425
ms.sourcegitcommit: 95a56dab4e30f7ad6615ebd4a4a0f61996fdc20f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2023
ms.locfileid: "69812669"
---
# <a name="direct-routing-media-path-country-codes"></a>直接路由媒体路径国家/地区代码

为媒体选择路由路径时，默认情况下，直接路由始终基于会话边界控制器 (SBC) 的公共 IP 地址分配数据中心，并始终选择离 SBC 数据中心最近的路径。

但是，在某些情况下，默认媒体路径可能不是最佳媒体路径;例如，美国范围内的公共 IP 可能分配给位于欧洲的 SBC。 

通过将 -MediaRelayRoutingLocationOverride 参数与 New-CsOnlinePSTNGateway 和 Set-CsOnlinePSTNGateway cmdlet 配合使用，可以指定媒体流量的首选区域。 例如，以下命令指定首选区域是德国：

Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com –MediaRelayRoutingLocationOverride DE 

请注意，仅当调用日志明确指示媒体路径的数据中心的默认分配不使用最靠近 SBC 数据中心的路径时，Microsoft 才建议设置此参数。 
 
## <a name="country-code-reference-table"></a>国家/地区代码参考表

下表显示了 -MediaRelayRoutingLocationOverride 参数的国家/地区代码值：

| 国家         | 代码 
|-----------------|--------------------|
| 阿富汗     | Af |
| 阿兰群岛   | 斧头 |
| 阿尔巴尼亚         | 铝 |
| 阿尔及利亚         | Dz |
| 美属萨摩亚  | AS |
| 安道尔         | AD |
| 安哥拉          | 坳 |
| 安圭拉岛        | 艾 |
| 南极洲      | Aq | 
| 安提瓜和巴布达 | 银 |
| 阿根廷       | AR |
| 亚美尼亚         | 是 |
| 阿鲁巴岛           | AW |
| 澳大利亚       | AU |
| 奥地利         | 在 |
| 阿塞拜疆      | Az |
| 巴哈马         | Bs |
| 巴林         | Bh |
| 孟加拉      | 屋宇 署 |
| 巴巴多斯        | Bb |
| 白俄罗斯         | BY |
| 比利时         | BE |
| 伯利兹          | BZ |
| 贝宁           | 北京 |
| 百慕大         | Bm |
| 不丹          | Bt |
| 玻利维亚         | 博 |
| 博内尔岛         | BQ |
| 波斯尼亚和黑塞哥维那 | BA |
| 博茨瓦纳        | Bw |
| 布维特岛   | Bv |
| 巴西          | BR |
| 英属印度洋领地 | Io |
| 英属维尔京群岛 | Vg |
| 文莱          | BN |
| 保加利亚        | BG |
| 布基纳法索    | 高炉 |
| 布隆迪         | BI |
| 佛得角      | 简历 |
| 柬埔寨        | Kh |
| 喀麦隆        | 厘米 |
| 加拿大          | 约 |
| 开曼群岛  | 肯塔基州 |
| 中非共和国 | Cf |
| 乍得            | Td |
| 智利           | CL |
| 中国           | CN |
| 圣诞岛 | 残雪 |
| 科科斯 (基) 群岛 | Cc |
| 哥伦比亚        | CO |
| 科摩罗         | 公里 |
| 刚果           | Cg |
| 刚果 ()      | Cd |
| 库克群岛    | Ck |
| 哥斯达黎加      | 铬 |
| 科特迪瓦   | 词 |
| 克罗地亚         | 人力资源 |
| 古巴            | 铜 |
| 库拉索岛         | 连续 |
| 塞浦路斯          | CY |
| 捷克         | Cz |
| 丹麦         | DK |
| 吉布提        | Dj |
| 多米尼加        | Dm |
| 多米尼加共和国 | DO |
| 厄瓜多尔         | EC |
| 埃及           | EG |
| 萨尔瓦多     | Sv |
| 赤道几内亚 | Gq |
| 厄立特里亚         | 二 |
| 爱沙尼亚         | EE |
| Eswatini        | 深圳 |
| 埃塞俄比亚        | Et |
| 福克兰群岛 | Fk |
| 法罗群岛   | 佛 |
| 斐济            | 福建 |
| 芬兰         | FI |
| 法国          | FR |
| 法属圭亚那   | 女朋友 |
| 法属波利尼西亚 | PF |
| 法属南领地 | Tf |
| 加蓬           | Ga |
| 冈比亚          | 通用 汽车 |
| 格鲁吉亚         | 通用 电气 |
| 德国         | DE |
| 加纳           | Gh |
| 直布罗陀       | Gi |
| 希腊          | Gr |
| 格陵兰       | Gl |
| 格林纳达         | Gd |
| 瓜德罗普      | Gp |
| 关岛            | 古 |
| 危地马拉       | 燃气轮机 |
| 格恩西岛        | Gg |
| 几内亚          | Gn |
| Guinea-Bissau   | Gw |
| 圭亚那          | Gy |
| 海地           | 你好 |
| 赫德岛和麦克唐纳群岛 | HM |
| 洪都拉斯        | HN |
| 香港特别行政区   | HK |
| 匈牙利         | HU |
| 冰岛         | 是 |
| 印度           | IN |
| 印度尼西亚       | ID |
| 伊朗            | 红外 |
| 伊拉克            | 智商 |
| 爱尔兰         | IE |
| 马恩岛     | 即时消息 |
| 以色列          | IL |
| 意大利           | IT |
| 牙买加         | Jm |
| Jan Mayen       | Xj |
| 日本           | JP |
| 球衣          | 流行性乙型脑炎 |
| 约旦          | 乔 |
| 哈萨克斯坦      | KZ |
| 肯尼亚           | KE |
| 基里巴斯        | K i |
| 韩国           | KR |
| 科索沃          | Xk |
| 科威特          | 千瓦 |
| 吉尔吉斯斯坦      | KG |
| 老挝            | 洛杉矶 |
| 拉脱维亚          | 低压 |
| 黎巴嫩         | 磅 |
| 莱索托         | LS |
| 利比里亚         | Lr |
| 利比亚           | LY |
| 列支敦士登   | 李 |
| 立陶宛       | LT |
| 卢森堡      | LU |
| 澳门特别行政区       | 莫 |
| 马达加斯加      | 镁 |
| 马拉维          | M w |
| 马来西亚        | MY |
| 马尔代夫        | Mv |
| 马里            | 毫升 |
| 马耳他           | MT |
| 马绍尔群岛 | MH |
| 马提尼克岛      | Mq |
| 毛里塔尼亚      | 先生 |
| 毛里求斯       | 木 |
| 马约特岛         | 刘日东 |
| 墨西哥          | MX |
| 密克罗尼西亚      | 调频 |
| 摩尔多瓦         | MD |
| 摩纳哥          | MC |
| 蒙古        | 锰 |
| 黑山共和国      | 我 |
| 蒙特塞拉特      | 女士 |
| 摩洛哥         | 马 |
| 莫桑比克      | Mz |
| 缅甸         | 毫米 |
| 纳米比亚         | NA |
| 瑙鲁           | 星期日 |
| 尼泊尔           | Np |
| 荷兰     | NL |
| 新喀里多尼亚   | 数控 |
| 新西兰     | 新西兰 |
| 尼加拉瓜       | 镍 |
| 尼日尔           | NE |
| 尼日利亚         | 议员 |
| 纽埃            | 女 |
| 诺福克岛  | Nf |
| 朝鲜     | Kp |
| 北马其顿 | Mk |
| 北马里亚纳群岛 | Np |
| 挪威          | 不 |
| 阿曼            | Om |
| 巴基斯坦        | PK |
| 帕劳           | PW |
| 巴勒斯坦权力机构 | PS |
| 巴拿马          | PA |
| 巴布亚新几内亚 | Pg |
| 巴拉圭        | PY |
| 秘鲁            | PE |
| 菲律宾     | PH |
| 皮特凯恩群岛 | Pn |
| 波兰          | PL |
| 葡萄牙        | PT |
| 波多黎各     | PR |
| 卡塔尔           | QA |
| 留尼旺         | RE |
| 罗马尼亚         | RO |
| 俄罗斯          | 如 |
| 卢旺达          | 乌尔曼 |
| 萨巴            | Xs |
| 圣巴泰勒米 | BL |
| 圣基茨和尼维斯 | KN |
| 圣卢西亚     | 立法会 |
| 圣马丁    | Mf |
| 圣皮埃尔和密克隆 | 下午 |
| 圣文森特和格林纳丁斯 | Vc |
| 萨摩亚           | Ws |
| 圣马力诺      | Sm |
| 圣多美和普林西比 | 圣 |
| 沙特阿拉伯    | SA |
| 塞内加尔         | SN |
| 塞尔维亚          | RS |
| 塞舌尔      | Sc |
| 塞拉利昂    | Sl | 
| 新加坡       | SG |
| 圣尤斯特歇斯  | 氙气 |
| 圣马丁    | Sx |
| 斯洛伐克        | SK |
| 斯洛文尼亚        | Sl |
| 所罗门群岛 | 某人 |
| 索马里         | 所以 |
| 南非    | ZA |
| 南佐治亚岛和南桑威奇群岛 | Gs |
| 南苏丹     | SS |
| 西班牙           | ES |
| 斯里兰卡       | 路 |
| 圣赫勒拿、阿森松、特里斯坦·达库尼亚 | Sh |
| 苏丹           | Sd |
| 苏里南        | 锶 |
| 斯瓦尔巴特        | Sj |
| 瑞典          | SE |
| 瑞士     | CH |
| 叙利亚           | Sy |
| 台湾          | TW |
| 塔吉克斯坦      | Tj |
| 坦桑尼亚        | TZ |
| 泰国        | TH |
| Timor-Leste     | Tl |
| 多哥            | Tg |
| 托克劳         | TK |
| 汤加           | 自 |
| 特立尼达和多巴哥 | Tt |
| 突尼斯         | Tn |
| 土耳其          | TR |
| 土库曼斯坦    | Tm |
| 特克斯和凯科斯群岛 | Tc |
| 图瓦卢          | 电视 |
| 美国离岛 | UM |
| 美属维尔京群岛 | 六 |
| 乌干达          | UG |
| 乌克兰         | Ua |
| 阿拉伯联合酋长国 | AE |
| 英国  | GB |
| 美国   | 我们 |
| 乌拉圭         | UY |
| 乌兹别克斯坦      | UZ |
| 瓦努阿图         | Vu |
| 梵蒂冈城    | Va |
| 委内瑞拉       | VE |
| 越南         | VN |
| 瓦利斯和富图纳 | WF |
| 也门           | 你们 |
| 赞比亚          | Zm |
| 津巴布韦        | ZW |
