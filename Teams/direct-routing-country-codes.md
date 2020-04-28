---
title: 直接路由国家代码
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
description: 阅读本文以查找直接路由的 "国家/地区" 代码，以便您可以选择最佳媒体路径。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 69265e797b256186f714e2cd4dcefcb3751c05ee
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2020
ms.locfileid: "43904804"
---
# <a name="direct-routing-media-path-country-codes"></a>直接路由媒体路径国家代码

选择媒体的路由路径时，直接路由默认情况下，始终根据会话边界控制器（SBC）的公共 IP 地址分配数据中心，并始终选择最接近于 SBC 数据中心的路径。

但是，在某些情况下，默认媒体路径可能不是最佳媒体路径;例如，美国范围内的公共 IP 可能分配给位于欧洲的 SBC。 

通过将-MediaRelayRoutingLocationOverride 参数与 CsOnlinePSTNGateway 和 CsOnlinePSTNGateway cmdlet 结合使用，你可以指定媒体流量的首选区域。 例如，以下命令指定首选区域为德国：

CSOnlinePSTNGateway-身份 sbc1.contoso.com-MediaRelayRoutingLocationOverride DE 

请注意，如果通话记录明确指明媒体路径的数据中心的默认分配不使用与 SBC 数据中心最接近的路径，则 Microsoft 仅建议设置此参数。 
 
## <a name="country-code-reference-table"></a>国家/地区代码引用表

下表显示了-MediaRelayRoutingLocationOverride 参数的国家/地区代码值：

| 该国         | 条码 
|-----------------|--------------------|
| 阿富汗     | AF |
| Aland 群岛   | DPE-AX |
| 阿尔巴尼亚         | 谭 |
| 阿尔及利亚         | DZ |
| 美属萨摩亚  | 方式 |
| 安道尔         | AD |
| 安哥拉          | AO |
| 安圭拉岛        | AI |
| Antarctica      | AQ | 
| 安提瓜和巴布达 | 集团 |
| 阿根廷       | AR |
| 亚美尼亚         | 格林威治 |
| 阿鲁巴岛           | AW |
| 澳大利亚       | AU |
| 奥地利         | 看 |
| 阿塞拜疆      | AZ |
| 巴哈马         | BS |
| 巴林         | BH |
| 孟加拉      | BD |
| 巴巴多斯        | BB |
| 白俄罗斯         | BY |
| 比利时         | 会 |
| 伯利兹          | BZ |
| 贝宁           | BJ |
| 百慕大         | BM |
| 不丹          | BT |
| 玻利维亚         | BO |
| 博内尔         | BQ |
| 波斯尼亚和黑塞哥维那 | BA |
| 博茨瓦纳        | 黑白 |
| 布维岛   | BV |
| 巴西          | BR |
| 不列颠印度洋属土 | IO |
| 英属维尔京群岛 | VG |
| 文莱          | BN |
| 保加利亚        | BG |
| 布基纳法索    | BF |
| 布隆迪         | 智能 |
| 佛得角      | 方便 |
| 柬埔寨        | KH |
| 喀麦隆        | 厘米 |
| 加拿大          | 认证 |
| 开曼群岛  | KY-KG&PLATFORM |
| 中非共和国 | CF |
| Chad            | 加入 |
| 智利           | CL |
| 中国           | CN |
| 圣诞岛 | CX |
| 科科斯（基林）群岛 | 修 |
| 哥伦比亚        | CO |
| 科摩罗         | KM-KH&PLATFORM |
| 刚果           | CG |
| 刚果（金）     | LCD |
| 库的岛    | CK 可以 |
| 哥斯达黎加      | CR |
| 科特迪瓦   | CI |
| 克罗地亚         | 人力资源 |
| 古巴            | CU |
| Curacao         | CW |
| 塞浦路斯          | CY |
| Czechia         | CZ |
| 丹麦         | DK |
| 吉布提        | DJ |
| 多米尼加        | 私信 |
| 多米尼加共和国 | 切勿 |
| 厄瓜多尔         | EC |
| 埃及           | EG |
| 萨尔瓦多     | SV |
| 赤道几内亚 | GQ |
| 厄立特里亚         | L |
| 爱沙尼亚         | EE |
| Eswatini        | SZ |
| 埃塞俄比亚        | 东部 |
| 福克兰群岛 | FK |
| 法罗群岛   | 命令 |
| 斐济            | FJ |
| 芬兰         | FI |
| 法国          | FR |
| 法属圭亚那   | GF |
| 法属波利尼西亚 | PF |
| 法属南部领地 | SETTINGS |
| 加蓬           | GA |
| 冈比亚          | 通用 |
| 格鲁吉亚         | 失效 |
| 德国         | DE |
| 加纳           | GH |
| 直布罗陀       | GI |
| 希腊          | GR |
| 格陵兰       | GL |
| 格林纳达         | GD |
| 瓜德罗普      | GP |
| 关岛            | GU-IN&PLATFORM |
| 危地马拉       | GT |
| Guernsey        | GG |
| 几内亚          | GN |
| 几内亚比绍   | 网 |
| 圭亚那          | GY |
| 海地           | 你好 |
| 赫德岛和麦克唐纳群岛 | HM |
| 洪都拉斯        | HN |
| 香港特别行政区   | HK |
| 匈牙利         | HU |
| 冰岛         | 是 |
| 印度           | 登录 |
| 印度尼西亚       | ID |
| 伊朗            | 外 |
| 伊拉克            | IQ |
| 爱尔兰         | IE |
| 曼岛     | 即时消息 |
| 以色列          | IL |
| 意大利           | 更加 |
| 牙买加         | JM |
| 扬马延       | XJ |
| 日本           | JP |
| 泽          | JE |
| 约旦          | JO |
| 哈萨克斯坦      | KZ |
| 肯尼亚           | KE |
| 基里巴斯        | KI |
| 韩国           | KR |
| Kosovo          | XK |
| 科威特          | 知识 |
| 吉尔吉斯斯坦      | 千克 |
| 老挝            | LA |
| 拉脱维亚          | LV |
| 黎巴嫩         | LB-LU&PLATFORM |
| 莱索托         | 3 |
| 利比里亚         | LR |
| 利比亚           | LY |
| 列支敦士登   | 离子 |
| 立陶宛       | L |
| 卢森堡      | LU |
| 澳门特别行政区       | MO |
| 马达加斯加      | MG |
| 马拉维          | MW |
| 马来西亚        | MY |
| 群岛        | MV |
| 马里            | ML |
| 马耳他           | 幼圆 |
| 马绍尔群岛 | MH |
| 马提尼克岛      | .MQ |
| 毛里塔尼亚      | MR |
| 毛里求斯       | MU |
| 马约特岛         | YT |
| 墨西哥          | MX |
| 密克罗尼西亚      | 调频广播 |
| 摩尔多瓦         | MD |
| 摩纳哥          | MC |
| 蒙古        | MN |
| 黑山共和国      | 一下 |
| 蒙特塞拉特      | MS-DOS |
| 摩洛哥         | 州 |
| 莫桑比克      | MZ |
| 缅甸         | 分钟 |
| 纳米比亚         | NA |
| Nauru           | NR |
| 尼泊尔           | NP |
| 荷兰     | NL |
| 新喀里多尼亚   | NC |
| 新西兰     | NZ |
| 尼加拉瓜       | NI |
| 尼日尔           | 左下 |
| 尼日利亚         | NG |
| Niue            | NU |
| 诺福克岛  | NF-E |
| 朝鲜     | KP |
| 北马其顿共和国 | MK |
| 北马里亚纳群岛 | NP |
| 挪威          | 不 |
| 阿曼            | 模型 |
| 巴基斯坦        | 主键 |
| 帕劳           | PW |
| 巴勒斯坦权力机构 | PS |
| 巴拿马          | PA |
| 巴布亚新几内亚 | 页码 |
| 巴拉圭        | PY |
| 秘鲁            | PE |
| 菲律宾     | PH |
| 皮特凯恩群岛 | PN |
| 波兰          | PL |
| 葡萄牙        | PT |
| 波多黎各     | 公共 |
| 卡塔尔           | QA |
| 留尼旺         | & |
| 罗马尼亚         | RO |
| 俄罗斯          | RU-RU&PLATFORM |
| 卢旺达          | RW-RW&PLATFORM |
| Saba            | XS |
| 圣 Barthelemy | BL |
| 圣基茨和尼维斯 | KN |
| 圣卢西亚     | LC |
| 法属圣马丁    | MF |
| 圣皮埃尔和密克隆岛 | 12：00 |
| 圣文森特和格林纳丁斯 | VC |
| 萨摩亚           | WS-TRUST |
| 圣马力诺      | SM |
| 圣多美圣多美和普林西比 | 短期 |
| 沙特阿拉伯    | SA |
| 塞内加尔         | SN |
| 塞尔维亚          | RS |
| 群岛      | SC |
| 塞拉利昂    | SL | 
| 新加坡       | SG |
| 圣尤斯特歇斯  | XE |
| 圣圣马丁    | S |
| 斯洛伐克        | SK |
| 斯洛文尼亚        | SL |
| 所罗门群岛 | SB |
| 索马里         | 您尚未 |
| 南非    | ZA |
| 南乔治亚和南桑威奇群岛 | GS |
| 南苏丹     | 汇总 |
| 西班牙           | ES |
| 斯里兰卡       | LK |
| 圣赫勒拿、阿森松、特里斯坦达库尼亚 | SH |
| 苏丹           | 仿真 |
| 苏里南        | SR-IOV |
| 群岛        | SJ |
| 瑞典          | SE |
| 瑞士     | 48 |
| 叙利亚           | SY |
| 台湾          | TW |
| 塔吉克斯坦      | TJ |
| 坦桑尼亚        | TZ |
| 泰国        | TH |
| 东帝汶-东帝汶     | TL |
| 多哥            | TG |
| Tokelau         | TK-TM&PLATFORM |
| 语           | 自 |
| 特立尼达和多巴哥 | TT-RU&PLATFORM |
| 突尼斯         | TN-ZA&PLATFORM |
| 土耳其          | TR |
| 土库曼斯坦    | TM |
| 特克斯和凯科斯群岛 | TC |
| Tuvalu          | 收看 |
| 美属外部岛 | 联 |
| 美属维尔京群岛 | 六 |
| 乌干达          | UG-CN&PLATFORM |
| 乌克兰         | UK-UA&PLATFORM |
| 阿拉伯联合酋长国 | AE |
| 英国  | GB |
| 美国   | 我们 |
| 乌拉圭         | UY |
| 乌兹别克斯坦      | UZ |
| 瓦努阿图         | VU |
| 梵蒂冈城    | 弗吉尼亚 |
| 委内瑞拉       | VE |
| 越南         | VN |
| 瓦利斯和富图纳 | WF |
| 也门           | YE |
| 赞比亚          | ZM |
| 津巴布韦        | ZW |

