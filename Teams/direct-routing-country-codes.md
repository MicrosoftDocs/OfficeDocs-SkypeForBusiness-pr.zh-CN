---
title: 直接路由国家/地区代码
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: reference
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 阅读本文以查找直接路由的媒体路径国家/地区代码，以便可以选择最佳媒体路径。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 330d178c7bfa969020ffc8c26b1e05283c182ae8
ms.sourcegitcommit: 90615674e9703aa5ea32be64ab3638aa30e83127
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/02/2021
ms.locfileid: "52717993"
---
# <a name="direct-routing-media-path-country-codes"></a>直接路由媒体路径国家/地区代码

选择媒体的路由路径时，默认情况下，直接路由始终基于会话边界控制器 (SBC) 的公共 IP 地址分配数据中心，并始终选择最靠近 SBC 数据中心的路径。

但是，在某些情况下，默认媒体路径可能不是最佳媒体路径;例如，可以将美国范围的公共 IP 分配到位于欧洲的 SBC。 

将 -MediaRelayRoutingLocationOverride 参数与 New-CsOnlinePSTNGateway 和 Set-CsOnlinePSTNGateway cmdlet 一起使用，可以指定媒体流量的首选区域。 例如，以下命令指定首选区域为德国：

Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com –MediaRelayRoutingLocationOverride DE 

请注意，只有在调用日志明确指示媒体路径的数据中心默认分配不使用离 SBC 数据中心最近的路径时，Microsoft 才建议设置此参数。 

> [!NOTE]
> 保留 MediaRelayRoutingLocationOverride 参数，供托管运营商使用。
 
## <a name="country-code-reference-table"></a>国家/地区代码参考表

下表显示了 -MediaRelayRoutingLocationOverride 参数的国家/地区代码值：

| 国家/地区         | 代码 
|-----------------|--------------------|
| 阿富汗     | AF |
| 阿兰群岛   | AX |
| 阿尔巴尼亚         | AL |
| 阿尔及利亚         | DZ |
| 美属萨摩亚  | AS |
| 安道尔         | AD |
| 安哥拉          | AO |
| 安圭拉岛        | AI |
| 南极洲      | AQ | 
| 安提瓜和巴布达 | AG |
| 阿根廷       | AR |
| 亚美尼亚         | AM |
| 阿鲁巴岛           | AW |
| 澳大利亚       | AU |
| 奥地利         | AT |
| 阿塞拜疆      | AZ |
| 巴哈马         | BS |
| 巴林         | BH |
| 孟加拉      | BD |
| 巴巴多斯        | BB |
| 白俄罗斯         | BY |
| 比利时         | BE |
| 伯利兹          | BZ |
| 贝宁           | BJ |
| 百慕大         | BM |
| 不丹          | BT |
| 玻利维亚         | BO |
| 博奈尔         | BQ |
| 波斯尼亚和黑塞哥维那 | BA |
| 博茨瓦纳        | BW |
| 布维岛   | BV |
| 巴西          | BR |
| 英属印地安群岛 | IO |
| 英属维尔京群岛 | VG |
| 文莱          | BN |
| 保加利亚        | BG |
| 布基纳法索    | BF |
| 卢旺达         | BI |
| 佛得角      | CV |
| 柬埔寨        | KH |
| 喀麦隆        | CM |
| 加拿大          | CA |
| 开曼群岛  | KY |
| 中非共和国 | CF |
| 苏丹            | TD |
| 智利           | CL |
| 中国           | CN |
| 圣诞岛 | CX |
| 科科斯 (基林) 群岛 | CC |
| 哥伦比亚        | CO |
| 科摩罗         | KM |
| 刚果（金）           | CG |
| 刚果 (金)      | CD |
| 维尔京群岛    | CK |
| 哥斯达黎加      | CR |
| 科特迪瓦   | CI |
| 克罗地亚         | 人力资源 |
| 委内瑞拉            | CU |
| 库拉索         | CW |
| 塞浦路斯          | CY |
| 捷克         | CZ |
| 丹麦         | DK |
| 吉布提        | DJ |
| 多米尼加        | DM |
| 多米尼加共和国 | DO |
| 厄瓜多尔         | EC |
| 埃及           | EG |
| 萨尔瓦多     | SV |
| 赤道几内亚 | GQ |
| 厄立特里亚         | ER |
| 爱沙尼亚         | EE |
| Eswatini        | SZ |
| 埃塞俄比亚        | ET |
| 福克兰群岛 | FK |
| 法罗群岛   | FO |
| 斐济            | FJ |
| 芬兰         | FI |
| 法国          | FR |
| 法属圭亚那   | GF |
| 法属波利尼西亚 | PF |
| 法属南部领地 | TF |
| 加纳           | GA |
| 佛得角          | GM |
| 格鲁吉亚         | GE |
| 德国         | DE |
| 加纳           | GH |
| 直布罗陀       | GI |
| 希腊          | GR |
| 格陵兰       | GL |
| 格林纳达         | GD |
| 瓜德罗普      | GP |
| 关岛            | GU |
| 危地马拉       | GT |
| 根西岛        | GG |
| 几内亚          | GN |
| Guinea-Bissau   | GW |
| 圭亚那          | GY |
| 海地           | 你好 |
| 赫德岛和 McDonald 群岛 | HM |
| 洪都拉斯        | HN |
| 香港特别行政区   | HK |
| 匈牙利         | HU |
| 冰岛         | IS |
| 印度           | IN |
| 印度尼西亚       | ID |
| 伊朗            | IR |
| 伊拉克            | IQ |
| 爱尔兰         | IE |
| 马恩岛     | 即时消息 |
| 以色列          | IL |
| 意大利           | IT |
| 牙买加         | JM |
| Jan Mayen       | XJ |
| 日本           | JP |
| 西岛          | JE |
| 约旦          | JO |
| 哈萨克斯坦      | KZ |
| 肯尼亚           | KE |
| 基里巴斯        | KI |
| 韩国           | KR |
| 阿尔巴尼亚          | XK |
| 科威特          | KW |
| 吉尔吉斯斯坦      | KG |
| 老挝            | LA |
| 拉脱维亚          | LV |
| 黎巴嫩         | LB |
| 莱索托         | LS |
| 利比亚         | LR |
| 利比亚           | LY |
| 列支敦士登   | LI |
| 立陶宛       | LT |
| 卢森堡      | LU |
| 澳门特别行政区       | MO |
| 非洲      | MG |
| 马拉维          | 兆瓦 |
| 马来西亚        | MY |
| 斯里兰卡        | MV |
| 马里            | ML |
| 马耳他           | MT |
| 马绍尔群岛 | MH |
| 马提尼克岛      | MQ |
| 毛里求斯      | MR |
| 毛里求斯       | MU |
| 马约特岛         | YT |
| 墨西哥          | MX |
| 密克罗尼西亚      | FM |
| 摩尔多瓦         | MD |
| 摩纳哥          | MC |
| 蒙古        | MN |
| 黑山共和国      | ME |
| 蒙特塞拉特      | MS |
| 摩洛哥         | MA |
| 莫桑比克      | MZ |
| 缅甸         | MM |
| 纳米比亚         | NA |
| 澳大利亚           | NR |
| 尼泊尔           | NP |
| 荷兰     | NL |
| 新喀里多尼亚   | NC |
| 新西兰     | NZ |
| 尼加拉瓜       | NI |
| 尼日尔           | NE |
| 尼日利亚         | NG |
| 纽埃            | NU |
| 诺folk 岛  | NF |
| 朝鲜     | KP |
| 北马其顿 | MK |
| 北马里亚纳群岛 | NP |
| 挪威          | 不 |
| 阿曼            | OM |
| 巴基斯坦        | PK |
| 帕劳           | PW |
| 巴勒斯坦权力机构 | PS |
| 巴拿马          | PA |
| 新西兰 | PG |
| 巴拉圭        | PY |
| 秘鲁            | PE |
| 菲律宾     | PH |
| 基茨凯恩群岛 | PN |
| 波兰          | PL |
| 葡萄牙        | PT |
| 波多黎各     | PR |
| 卡塔尔           | QA |
| 留尼旺         | RE |
| 罗马尼亚         | RO |
| 俄罗斯          | RU |
| 卢旺达          | RW |
| 萨巴            | XS |
| 圣巴塞勒米 | BL |
| 圣基茨和尼维斯 | KN |
| 圣卢西亚     | LC |
| 圣马丁    | MF |
| 圣马丁和密克隆群岛 | PM |
| 圣文森特和格林纳丁斯 | VC |
| 萨摩亚           | WS |
| 圣马力诺      | SM |
| 圣多美和圣多美 | ST |
| 沙特阿拉伯    | SA |
| 塞内加尔         | SN |
| 塞尔维亚          | RS |
| 群岛      | SC |
| 共和国    | SL | 
| 新加坡       | SG |
| Sint Eustatius  | XE |
| 圣马丁    | SX |
| 斯洛伐克        | SK |
| 斯洛文尼亚        | SL |
| 福克兰群岛 | SB |
| 肯尼亚         | SO |
| 南非    | ZA |
| 南格鲁吉亚和南威奇群岛 | GS |
| 南苏丹     | SS |
| 西班牙           | ES |
| 斯里兰卡       | LK |
| 圣赫勒拿、阿森松、Tristan da 库尼亚 | SH |
| 苏丹           | SD |
| 苏里南        | SR |
| Svalbard        | SJ |
| 瑞典          | SE |
| 瑞士     | CH |
| 叙利亚           | SY |
| 台湾          | TW |
| 塔吉克斯坦      | TJ |
| 肯尼亚        | TZ |
| 泰国        | TH |
| Timor-Leste     | TL |
| 多哥            | TG |
| 群岛         | TK |
| 斐济           | 自 |
| 特立尼达和多巴哥 | TT |
| 突尼斯         | TN |
| 土耳其          | TR |
| 土库曼斯坦    | TM |
| 特克斯和凯科斯群岛 | TC |
| 秘鲁          | 电视 |
| 美属外岛 | UM |
| 美属维尔京群岛 | VI |
| 乌干达          | UG |
| 乌克兰         | UA |
| 阿拉伯联合酋长国 | AE |
| 英国  | GB |
| 美国   | 美国 |
| 乌拉圭         | UY |
| 乌兹别克斯坦      | UZ |
| 萨摩亚         | VU |
| 梵蒂冈城    | VA |
| 委内瑞拉       | VE |
| 越南         | VN |
| 瓦利斯和富图纳 | WF |
| 也门           | YE |
| 赞比亚          | ZM |
| 津巴布韦        | ZW |
