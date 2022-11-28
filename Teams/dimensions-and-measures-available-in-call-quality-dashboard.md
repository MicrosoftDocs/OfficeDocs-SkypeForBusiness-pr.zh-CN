---
title: '维度和度量 - 通话质量仪表板 (CQD) '
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: siunies, mikedav, gageames
ms.topic: article
ms.assetid: e97aeeee-9e43-416f-b433-9cdd63d8874b
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Reporting
- seo-marvel-mar2020
description: 获取有关通话质量仪表板 (CQD) 用于 Microsoft Teams 和 Skype for Business Online 的维度和度量的详细信息。
ms.openlocfilehash: fdbd655958a3c49a99f4442495a1543b045a5d98
ms.sourcegitcommit: 548978550d58f8657d7035b57b736e9cf9b15984
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2022
ms.locfileid: "69163242"
---
# <a name="dimensions-and-measurements-available-in-call-quality-dashboard-cqd"></a>通话质量仪表板中提供的尺寸和度量值 (CQD) 

Microsoft Teams 和 Skype for Business Online 的呼叫质量仪表板 (CQD) ，可以更好地了解使用这些服务发出的呼叫的通话质量。 本主题提供有关通过 CQD 可见的尺寸和度量的详细信息。 若要了解有关 CQD 的详细信息，请参阅[使用 CQD 管理 Microsoft Teams 中的通话和会议质量](quality-of-experience-review-guide.md)。

## <a name="first-and-second-endpoint-classification"></a>第一和第二终结点分类

CQD 中的许多尺寸和度量值标记为第一个或第二个。 以下逻辑用于确定将流或通话中涉及的哪些终结点标为第一。

- 服务器终结点 (AV MCU、中介服务器等) 在流或调用中涉及服务器时被视为“第一”。
- 客户端终结点被视为 Second，除非流位于两个服务器终结点之间。
- 如果两个终结点的类型相同，则基于用户代理类别的内部排序设置第一个与第二个，以确保排序一致。

例如，此处每一行表示流中涉及的一对用户代理：

|呼叫方的用户代理类别 |被叫方的用户代理类别 |First Endpoint |Second Endpoint|First Is Caller
|:--- |:--- |:--- |:--- |:--- |
|AV-MCU |OC（Skype for Business 客户端） |AV-MCU |OC（Skype for Business 客户端） |是 |
|OC（Skype for Business 客户端） |AV-MCU |AV-MCU |OC（Skype for Business 客户端） |否 |
|OC（Skype for Business 客户端） |OC（Skype for Business 客户端） |OC（Skype for Business 客户端） |OC（Skype for Business 客户端） |否 |
|AV-MCU |中介服务器 |中介服务器 |AV-MCU ||
|中介服务器 |AV-MCU |中介服务器 |AV-MCU |是 |
|OC（Skype for Business 客户端） |OC 电话（Skype for Business IP 电话） |OC（Skype for Business 客户端） |OC 电话（Skype for Business IP 电话） |是 |
|OC 电话（Skype for Business IP 电话） |OC（Skype for Business 客户端） |OC（Skype for Business 客户端） |OC 电话（Skype for Business IP 电话） |否 |

> [!NOTE]
> That First and Second classification is separate from which endpoint is the caller or callee. The First Is Caller dimension can be used to help identify which endpoint was the caller or callee.

## <a name="dimensions"></a>维度

维度信息部分基于上传到 CQD 门户的数据。 许多维度值也可以用作筛选器。

### <a name="dimension-data-types-and-units"></a>维度数据类型和单位

#### <a name="boolean"></a>Boolean

布尔值始终为 True 或 False。 在某些情况下，True 也可以表示为 1，False 可以表示为 0。

#### <a name="range"></a>范围

按范围或分组表示的维度值使用以下格式显示：

 _\<sort order string\> [\<lower bound inclusive\> - \<upper bound exclusive\>_

例如，持续时间（分钟）维度表示以分钟为单位的通话持续时间，报告的值以取值范围的形式表示。

|Duration (Minutes) |解释方法 |
|:--- |:--- |
|062: [0 - 0) |流持续时间 = 0 分钟 |
|064: [1 - 2) |1 分钟 < = 流持续时间 < 2 分钟 |
|065: [2 - 3) |2 分钟 < = 流持续时间 < 3 分钟 |
|066： [3-4)  |3 分钟 < = 流持续时间 < 4 分钟 |
|  | |

The \<sort order string> is used to control the sort order when presenting the data and can be used for filtering. For example, a filter on Duration (Minutes) < "065", would show streams with duration less than 2 minutes (The leading '0' is needed for the filter to work as expected). [!注释] 排序字符串的实际值并不重要。

> [!NOTE]
> 你可能会注意到，对于给定维度而言，范围似乎无效。 例如，当 100 是 Wifi 信号强度的最大值时，显示 082： [100 - 110) 范围内的呼叫。 这是因为如何将数字分配给 CQD 数据模型中的范围。 如果整数值为 99，则将在 081： [90 - 100) 范围内计数。 如果该值为 100，则将在 082： [100 - 110) 范围内计数。 这并不表示报告了大于 100% 的 Wifi 信号强度值。

#### <a name="enumeration-strings"></a>枚举字符串

CQD 使用的字符串通常派生自数据文件，这些字符串几乎可以是允许长度内的任意字符组合。 某些维度看起来像字符串，但由于它们只能是预定义值的简短列表之一，因此它们是枚举，而不是真正的字符串。 某些枚举字符串也成对使用。

#### <a name="enumeration-pair"></a>枚举对

按枚举对表示的维度使用以下格式显示：

 _\<enumeration value from one end point\> : \<enumeration value from the other endpoint\>_

枚举值的顺序一致，但此顺序不反映第一或第二终结点的顺序。

例如，网络连接详情对显示两个终结点的网络连接详情值：

|Network Connection Detail Pair |解释方法 |
|:--- |:--- |
|有线 : 有线 |第一和第二终结点均使用有线以太网连接。 |
|有线 : wifi |第一个终结点使用有线以太网连接且第二个终结点使用 Wi-Fi 连接，或第二个终结点使用有线以太网连接且第一个终结点使用 Wi-Fi 连接。 |
|: wifi |第一个终结点使用 WiFi 连接且第二个终结点使用的网络连接未知，或第二个终结点使用 WiFi 连接且第一个终结点使用的网络连接未知。 |
| | |

#### <a name="blank-values"></a>空值

下表列出了维度可能为空的可能原因。 如果 QoE 记录可用维度为 false，则许多维度和度量值将为空。 当调用未成功建立时，或者客户端无法将其遥测数据发送到服务时，通常会发生这种情况。

### <a name="available-dimensions"></a>可用维度 

下表按用于创建报表或编辑以前定义的报表的Editor Power Query中列出的顺序列出了 CQD 中当前可用的维度。

|名称|数据类型|说明|空值的可能原因|
|:---|:---|:---|:---|
|**Endpoint**||||
| First CPU Name  | 字符串  | 第一终结点使用的 CPU 的名称。 <br/> **示例值：** Contoso CPU X11 @ 1.80 GHz | <br/>&bull; 终结点未报告此数据   |
| Second CPU Name  | 字符串  | 第二终结点使用的 CPU 的名称。 <br/> **示例值：** Contoso CPU X11 @ 1.80 GHz | <br/>&bull; 终结点未报告此数据     |
| First CPU Number Of Cores  | 内核数量  | 第一终结点上可用的 CPU 内核数。 <br/> **示例值：** 8  | <br/>&bull; 终结点未报告此数据    |
| Second CPU Number Of Cores  | 内核数量  | 第二终结点上可用的 CPU 内核数。 <br/> **示例值：** 8  | <br/>&bull; 终结点未报告此数据     |
| First CPU Processor Speed  | CPU 速度，单位为 MHz  | 第一终结点使用的 CPU 的速度，单位为 MHz。 <br/> **示例值：** 1800  | <br/>&bull; 终结点未报告此数据   |
| Second CPU Processor Speed  | CPU 速度，单位为 MHz  | 第二终结点使用的 CPU 的速度，单位为 MHz。 <br/> **示例值：** 1800 | <br/>&bull; 终结点未报告此数据     |
| First Endpoint  | 字符串  | 如果第一终结点为服务器或云服务客户端，此终结点报告的计算机名称。 <br/> **示例值：** MACHINENAME  | <br/>&bull; 终结点未报告此数据    |
| Second Endpoint  | 字符串  | 如果第二终结点为服务器或云服务客户端，此终结点报告的计算机名称。 <br/> **示例值：** MACHINENAME | <br/>&bull; 终结点未报告此数据     |
| First OS  | 字符串  | 第一终结点报告的完整操作系统和体系结构字符串。 <br/> **示例值：** Windows 10.0.14996 SP： 0.0 类型： 1 (工作站) 套件： 256 Arch： x64 WOW64： True | <br/>&bull; 终结点未报告此数据 |
| Second OS  | 字符串  | 第二终结点报告的完整操作系统和体系结构字符串。 <br/> **示例值：** Windows 10.0.14996 SP： 0.0 类型： 1 (工作站) 套件： 256 Arch： x64 WOW64： True  | <br/>&bull; 终结点未报告此数据 |
| First OS Filtered  | 字符串  | 第一终结点报告的操作系统名称和主要版本及次要版本。 此字符串可以包含 OS 名称和版本以外的内容。 <br/> **示例值：** Windows 10  | <br/>&bull; 终结点未报告此信息 <br/>&bull; 未收到来自此终结点的报告。  |
| Second OS Filtered  | 字符串  | 第二终结点报告的操作系统名称和主要版本及次要版本。 此字符串可以包含 OS 名称和版本以外的内容。 <br/> **示例值：** Windows 10  | <br/>&bull; 终结点未报告此信息 <br/>&bull; 未收到来自此终结点的报告 |
| First OS Architecture  | 字符串  | 第一终结点报告的硬件体系结构。 <br/> **示例值：** x64  | &bull; 终结点未报告此信息 <br/>&bull; 未收到来自此终结点的报告 <br/>&bull; 无法识别体系结构的格式 |
| Second OS Architecture  | 字符串  | 第二终结点报告的硬件体系结构。 <br/> **示例值：** x64  | &bull; 终结点未报告此信息 <br/>&bull; 未收到来自此终结点的报告 <br/>&bull; 无法识别体系结构的格式  |
| First Virtualization Flag  | 枚举 <br/>**可能的值：** <br/> “0x00” = 无  <br/> “0x01” = Hyper-V <br/> “0x02” = VMware <br/> “0x04” = 虚拟电脑 <br/> “0x08” = Xen PC | 指示第一终结点报告的虚拟化环境类型的标志。 | <br/>&bull; 终结点未报告数据 |
| Second Virtualization Flag  | 枚举 <br/>**可能的值：** <br/> “0x00” = 无  <br/> “0x01” = Hyper-V <br/> “0x02” = VMware <br/> “0x04” = 虚拟电脑 <br/> “0x08” = Xen PC | 指示第二终结点报告的虚拟化环境类型的标志。  | <br/>&bull; 终结点未报告数据 |
| 第一个 VTC 设备名称 | String | 第一终结点使用的 VTC 设备的友好名称 | <br/>&bull; 终结点未报告数据 <br/>&bull; 字段是 EUII，28 天过去了 |
| 第二个 VTC 设备名称 | String | 第二终结点使用的 VTC 设备的友好名称 | <br/>&bull; 终结点未报告数据 <br/>&bull; 字段是 EUII，28 天过去了 |
| 第一个 VTC 设备详细信息 | String | 第一终结点使用的 VTC 设备的平台和版本信息 <br/> **示例值：** 坦德伯格，529 | <br/>&bull; 终结点未报告数据 |
| 第二个 VTC 设备详细信息 | String | 第二终结点使用的 VTC 设备的平台和版本信息 <br/> **示例值：** 坦德伯格，529 | <br/>&bull; 终结点未报告数据 |
| 第一终结点生成 |String |设备制造商，将从终结点数据文件 EndpointMake 字段中读取信息。 | <br/>&bull; 没有终结点的数据文件 |
| 第一终结点模型 |String|设备型号，将从终结点数据文件 EndpointModel 字段读取信息。| <br/>&bull; 没有终结点的数据文件 |
| 第一终结点类型|String|设备类型，从终结点数据文件 EndpointType 字段读取信息。| <br/>&bull; 没有终结点的数据文件 |
| 第一终结点标签 1|String|可从终结点数据文件 读取可自定义标签的信息。| <br/>&bull; 没有终结点的数据文件 |
| 第一终结点标签 2|String|可从终结点数据文件读取可自定义的标签信息。| <br/>&bull; 没有终结点的数据文件 |
| 第一终结点标签 3|String|可从终结点数据文件读取可自定义的标签信息。|  <br/>&bull; 没有终结点的数据文件|
| 第二终结点生成|String|设备制造商从终结点数据文件 EndpointName 字段读取信息。 | <br/>&bull; 没有终结点的数据文件 |
| 第二终结点模型|String|设备型号，将从终结点数据文件 EndpointModel 字段读取信息。| <br/>&bull; 没有终结点的数据文件 |
| 第二终结点类型|String|设备类型，从终结点数据文件 EndpointType 字段读取信息。|  <br/>&bull; 没有终结点的数据文件|
| 第二终结点标签 1|String| 可从终结点数据文件读取可自定义的标签信息。 | <br/>&bull; 没有终结点的数据文件 |
| 第二终结点标签 2|String|可从终结点数据文件读取可自定义的标签信息。| <br/>&bull; 没有终结点的数据文件|
| 第二终结点标签 3|String|可从终结点数据文件读取可自定义的标签信息。| <br/>&bull; 没有终结点的数据文件 |
| 第一个 ASN|String|第一终结点的自治系统编号。 <br/> **示例值：** 8069  | <br/>&bull; 网络数据无法确定终结点 ASN |
| 第二个 ASN|String|第二终结点的自治系统编号。 <br/> **示例值：** 8069  | <br/>&bull; 网络数据无法确定终结点 ASN |
| 第一个 ASN ISP 名称|String|ASN 持有者的名称（通常是 Internet 服务提供商或 ISP），表示第一终结点的自治系统编号。 <br/> **示例值** Microsoft Corporation  | <br/>&bull; 网络数据无法确定终结点 ASN |
| 第二个 ASN ISP 名称|String|ASN 持有者的名称（通常是 Internet 服务提供商或 ISP），表示第二终结点的自治系统编号。 <br/> **示例值：** Microsoft Corporation  | <br/>&bull; 网络数据无法确定终结点 ASN |
| 第一个 ASN 国家/地区代码|String|为第一终结点确定的自治系统编号的国家/地区代码。 <br/> **示例值：** 我们  | <br/>&bull; 网络数据无法确定终结点 ASN |
| 第二个 ASN 国家/地区代码|String|为第二终结点确定的自治系统编号的国家/地区代码。 <br/> **示例值：** 我们  | <br/>&bull; 网络数据无法确定终结点 ASN |
| 第一个 ASN 国家/地区|String|为第一终结点确定的自治系统编号的国家/地区名称。 <br/> **示例值：** Estados Unidos  | <br/>&bull; 网络数据无法确定终结点 ASN |
| 第二个 ASN 国家/地区|String|为第二终结点确定的自治系统编号的国家/地区名称。 <br/> **示例值：** Estados Unidos  | <br/>&bull; 网络数据无法确定终结点 ASN |
| 第一个 ASN 城市|String|为第一终结点确定的自治系统编号的城市名称。 <br/> **示例值：** 雷德蒙  | <br/>&bull; 网络数据无法确定终结点 ASN |
| 第二个 ASN 城市|String|为第二终结点确定的自治系统编号的城市名称。 <br/> **示例值：** 雷德蒙  | <br/>&bull; 网络数据无法确定终结点 ASN |
| 第一个 ASN 状态|String|为第一终结点确定的自治系统编号的状态名称。 <br/> **示例值：** 洼  | <br/>&bull; 网络数据无法确定终结点 ASN |
| 第二个 ASN 状态|String|为第二终结点确定的自治系统编号的状态名称。 <br/> **示例值：** 洼  | <br/>&bull; 网络数据无法确定终结点 ASN |
|**大楼**| | | |
| First Network | 字符串 | 如果子网存在于子网到租户的生成数据中，则第一终结点用于媒体流的子网。 <br/> **示例值：** 10.0.1.12.0 | &bull; 终结点未报告网络数据 <br/>&bull; 网络未在子网映射数据中定义。  |
| First Network Name  | 字符串  | 第一终结点用于媒体流的网络名称。 基于将子网映射到租户生成数据。 <br/> **示例值：** USA/WA/REDMOND | &bull; 终结点未报告网络数据 <br/>&bull; 未在子网映射数据中定义网络  |
| First Network Range  | 字符串  | 第一终结点用于媒体流的子网的网络前缀/范围，基于子网到租户构建的数据映射。 <br/> **示例值：** 24 | &bull; 终结点未报告网络数据 <br/>&bull; 未在子网映射数据中定义网络 |
| First Building Name  | 字符串  | 基于将子网映射到租户生成数据的第一终结点所在的建筑物的名称。  <br/> **示例值：** 主要  | &bull; 终结点未报告网络数据 <br/>&bull; 未在子网映射数据中定义网络   |
| First Ownership Type  | 字符串  | 第一终结点所在的建筑物的所有权类型。 基于将子网映射到租户生成数据。 <br/> **示例值：** Contoso-IT  | &bull; 终结点未报告网络数据 <br/>&bull; 网络不在公司网络内，或者子网映射数据中未定义网络所有权  |
| First Building Type   | 字符串  | 基于将子网映射到租户生成数据的第一终结点所在的生成类型。 <br/> **示例值：** 打开 Office | &bull; 终结点未报告的网络数据 <br/>&bull; 网络不在企业网络内 <br/>&bull; 子网映射数据中未定义网络生成类型  |
| First Building Office Type  | 字符串  | 基于将子网映射到租户生成数据的第一终结点所在的生成类型。 <br/> **示例值：** 打开 Office | &bull; 终结点未报告的网络数据 <br/>&bull; 网络不在企业网络内 <br/>&bull; 子网映射数据中未定义网络生成类型  |
| First City  | 字符串  | 第一个终结点所在的城市基于将子网映射到租户生成数据。 <br/> **示例值：** 雷德蒙 | &bull; 终结点未报告的网络数据 <br/>&bull; 网络不在企业网络内 <br/>&bull; 网络未在子网映射数据中定义城市   |
| First Zip Code  | 字符串  | 第一终结点所在的 Zip/邮政编码基于将子网映射到租户生成数据。 <br/> **示例值：** 98052 | &bull; 终结点未报告的网络数据 <br/>&bull; 网络不在企业网络内 <br/>&bull; 网络未在子网映射数据中定义邮政编码   |
| First Country  | 字符串  | 基于将子网映射到租户生成数据的第一终结点所在的国家/地区。 <br/> **示例值：** 美国 | <br/>&bull; 终结点未报告的网络数据<br/>&bull; 网络不在企业网络内 <br/>&bull; 网络未在子网映射数据中定义国家/地区 |
| First State  | 字符串  | 第一个终结点所在的状态基于将子网映射到租户生成数据。 <br/> **示例值：** 洼 | <br/>&bull; 终结点未报告网络数据<br/>&bull; 网络不在企业网络内 <br/>&bull; 网络未在子网映射数据中定义状态。   |
| 第一个区域  | 字符串  | 第一个终结点所在的区域基于将子网映射到租户生成数据。 <br/> **示例值：** 北米 | <br/>&bull; 终结点未报告的网络数据<br/>&bull; 网络不在企业网络内 <br/>&bull; 网络未在子网映射数据中定义区域。 |
| First Express Route  | 布尔值  | 如此 如果基于将子网映射到租户生成数据为 Azure ExpressRoute 启用了第一终结点用于媒体流的子网。 可以出于其他目的自定义使用情况（如果决定）。  |  &bull; 终结点未报告的网络数据 <br/>&bull; 网络不在企业网络内 <br/>&bull; 网络未在子网映射数据中设置 ExpressRoute 标志。|
| 第一个网络映射 VPN  | Boolean  | 如此 如果第一终结点用于媒体流的子网是 VPN 子网，基于将子网映射到租户生成数据。 |  &bull; 终结点未报告的网络数据 <br/>&bull; 网络不在企业网络内 <br/>&bull; 网络未在子网映射数据中设置 VPN 标志。|
| Second Network  | 字符串  | 如果子网中存在子网到租户生成数据，则第二终结点用于媒体流的子网。 <br/> **示例值：** 10.0.1.12.0  | &bull; 终结点未报告的网络数据 <br/>&bull; 未在子网映射数据中定义网络  |
| Second Network Name  | 字符串  | 第二终结点用于媒体流的网络名称，具体取决于将子网映射到租户生成数据。 <br/> **示例值：** USA/WA/REDMOND  | &bull; 终结点未报告的网络数据 <br/>&bull; 网络没有在子网映射数据中定义的网络名称  |
| Second Network Range  | 字符串  | 第二终结点用于媒体流的子网的网络前缀/范围，具体取决于将子网映射到租户生成数据。 <br/> **示例值：** 24  | &bull; 终结点未报告的网络数据 <br/>&bull; 网络未在子网映射数据中定义网络范围  |
| Second Building Name  | 字符串  | 基于将子网映射到租户生成数据的第二终结点所在的建筑物的名称。 <br/> **示例值：** 主要 | <br/>&bull; 终结点未报告的网络数据<br/>&bull; 网络不在企业网络内 <br/>&bull; 网络没有在子网映射数据中定义的生成名称 |
| Second Ownership Type  | 字符串  | 第二终结点所在的建筑物的所有权类型基于将子网映射到租户生成数据。 <br/> **示例值：** Contoso — IT | &bull; 终结点未报告的网络数据<br/>&bull; 网络不在企业网络内 <br/>&bull; 网络未在子网映射数据中定义所有权 |
| Second Building Type  | 字符串  | 基于将子网映射到租户生成数据的第二终结点所在的生成类型。 <br/> **示例值：** 打开 Office | <br/>&bull; 终结点未报告的网络数据<br/>&bull; 网络不在企业网络内 <br/>&bull; 子网映射数据中未定义网络生成类型  |
| Second Building Office Type  | 字符串  | 第二终结点所在的办公室大楼类型基于将子网映射到租户建筑物数据。 <br/> **示例值：** 办公室  | <br/>&bull; 终结点未报告的网络数据<br/>&bull; 网络不在企业网络内 <br/>&bull; 网络未在子网映射数据中定义建筑物办公室类型。  |
| Second City  | 字符串  | 基于将子网映射到租户生成数据的第二终结点所在的城市。 <br/> **示例值：** 雷德蒙 |  <br/>&bull; 终结点未报告的网络数据  <br/>&bull; 网络不在企业网络内  <br/>&bull; 网络未在子网映射数据中定义城市   |
| Second Zip Code  | 字符串  | 基于将子网映射到租户生成数据的第二终结点所在的 Zip/邮政编码。 <br/> **示例值：** 98052  | <br/>&bull; 终结点未报告的网络数据 <br/>&bull; 网络不在企业网络内 <br/>&bull; 网络未在子网映射数据中定义邮政编码 |
| Second Country  | 字符串  | 第二终结点所在的国家/地区基于将子网映射到租户生成数据。 <br/> **示例值：** 美国  | <br/>&bull; 终结点未报告的网络数据<br/>&bull; 网络不在企业网络内 <br/>&bull; 网络未在子网映射数据中定义国家/地区  |
| Second State  | 字符串  | 第二终结点所在的状态基于将子网映射到租户生成数据。 <br/> **示例值：** 洼  | <br/>&bull; 终结点未报告的网络数据<br/>&bull; 网络不在企业网络内 <br/>&bull; 网络未在子网映射数据中定义状态  |
| 第二个区域  | 字符串  | 第二终结点所在的区域基于将子网映射到租户生成数据。 <br/> **示例值：** 北米  | <br/>&bull; 终结点未报告的网络数据 <br/>&bull; 网络不在企业网络内 <br/>&bull; 网络未在子网映射数据中定义区域。 |
| Second Express Route  | 布尔值  | 如果基于将子网映射到租户生成数据，为 ExpressRoute 启用了第二终结点用于媒体流的子网，则为 True。    | <br/>&bull; 终结点未报告的网络数据 <br/>&bull; 网络不在企业网络内 <br/>&bull; 网络未在子网映射数据中设置 ExpressRoute 标志   |
| 第二个网络映射 VPN  | Boolean  | 如此 如果第二终结点用于媒体流的子网是 VPN 子网，基于将子网映射到租户生成数据。 |  &bull; 终结点未报告的网络数据 <br/>&bull; 网络不在企业网络内 <br/>&bull; 网络未在子网映射数据中设置 VPN 标志。|
| First Inside Corp  | 枚举 <br/>**可能的值：** <br/> 内部、外部  | 根据将子网映射到租户生成数据，指示第一个终结点是否位于公司网络内的子网上。 默认情况下，认为终结点位于外部。 <br/> **示例值：** 里面 | |
| Second Inside Corp  | 枚举 <br/> **可能的值：** <br/> 内部、外部 | 根据子网到租户生成数据的映射，指示第二个终结点是否位于公司网络内的子网上。 默认情况下，认为终结点位于外部。 <br/>**示例值：** 里面  |  |
|**Deployment**| | | |
| First Tenant Id  | 字符串  | 第一个终结点的租户 ID。 <br/> **示例值：** 00000000 — 0000 -0000 - 0000 — 0000000000000  | <br/>&bull; 无法确定第一个终结点的租户 ID。 这可能表示终结点已登录到本地Skype for Business Server部署。  |
| Second Tenant Id  | 字符串  | 第二个终结点的租户 ID。 <br/> **示例值：** 00000000 — 0000 - 0000 - 0000 — 000000000000  |  <br/>&bull; 无法确定第二终结点的租户 ID。 这可能表示终结点已登录到本地Skype for Business Server部署。  |
| First Pool  | 字符串  | 分配给第一终结点的 Skype for Business Online 池 FQDN <br/> **示例值：** pool1.lync.com <span></span><span></span>  | <br/>&bull;指示终结点已登录到Microsoft Teams 或Skype for Business。 此字段仅针对使用本地Skype for Business Server部署的流填充。 |
| Second Pool  | 字符串  | 分配给第二终结点的 Skype for Business Online 池 FQDN <br/> **示例值：**<span>pool1.lync.com</span>   | &bull;无法为第二个终结点确定Skype for Business联机池。 这可能表示终结点已登录到本地Skype for Business Server部署。  |
| Is Federated  | 布尔值  | 如果流在两个联合租户之间，则为 True，否则为 False。   | <br/>&bull; 无法确定此流是否为联合流 <br/>&bull; 未收集某些信号数据   |
|区域 | String   |  部署所在的区域基于租户的主区域。 <br/> **示例值：** 北米 | <br/>&bull; 未报告网络数据 <br/>&bull; 网络不在企业网络内 <br/>&bull; 网络未在子网映射数据中定义区域。 |
|**Stream**| | | |
| QoE Record Available  | 布尔值  | 如果为通话/会话提供至少一个用户体验质量报告，则为 True。 仅当 QoE 记录可用时，许多维度和度量值才可用。 如果呼叫设置失败，QoE 记录将不可用。    |   |
| CDR Record Available  | 布尔值  | 如果为通话/会话提供至少一个呼叫详细记录，则为 True。     | |
| Media Line Label  | 整型  | Label in SDP for media line. Use Media Type to determine if label is used for video, audio, app sharing, or video based screen sharing. <br/> **示例值：** 0  | &bull; 终结点未报告此数据。  |
| Media Type  | 字符串  | 媒体的类型（视频、音频、应用共享或基于视频的屏幕共享）。 <br/> **示例值：** 音频 |  |
|媒体行标签文本 | String |会话描述协议 (SDP) 与流对应的媒体行的标签属性。 有关更多详细信息，请参阅 [RFC 4574](https://tools.ietf.org/html/rfc4574) 。 <br/> **示例值**： <br/> main-audio<br/> main-video<br/> main-video1<br/> main-video2<br/> main-video3<br/> main-video4<br/> main-video5<br/> main-video6<br/> main-video7<br/> main-video8<br/> main-video9<br/> 全景视频<br/> applicationsharing-video<br/> 数据   | |
| First Is Server  | 枚举 <br/>**可能的值：** <br/>&bull; 客户 <br/>&bull; 服务器  | 指示第一个终结点是服务器终结点，例如会议服务器 (AVMCU、ASMCU) 或其他媒体服务器 (中介服务器) ，还是客户端终结点。  **示例值：** 客户 | |
| Second Is Server  | 枚举 <br/>**可能的值：** <br/>&bull; 客户 <br/>&bull; 服务器   | 指示第二个终结点是服务器终结点还是客户端终结点。 <br/>  **示例值：** 客户 | |
| First Is Caller  | 布尔值  | 如此 如果第一个终结点是发起会话的调用方。   | |
| First Network Connection Detail  | 枚举 <br>**可能的值：** <br/>&bull; 有线 <br/>&bull; 无线 <br/>&bull; MobileBB <br/>&bull; 隧道 <br/>&bull; 其他 | 第一终结点使用的网络类型。  <br/> **示例值：** 有线  | &bull; 终结点未报告数据  |
| Second Network Connection Detail  | 枚举 <br/>**可能的值：** <br/>&bull; 有线 <br/>&bull; 无线 <br/>&bull; MobileBB <br/>&bull; 隧道 <br/>&bull; 其他 | 第二终结点使用的网络类型。  <br/> **示例值：** 有线  | &bull; 终结点未报告数据  |
| Stream Direction  | 枚举 <br/>**可能的值：** <br/>&bull; First-to-Second <br/>&bull; Second-to-First <br/> | 指示流的方向。 <br/>&bull;**示例值：** First-to-Second | &bull; 未报告任何指示流方向的数据 |
| Payload Description  | 字符串  | 流中最后使用的编解码器的名称。 <br/> **示例值：** SILKWide | &bull; 没有可用的数据 |
| Audio and Video Call  | 布尔值  | 如果呼叫同时包含音频和视频流，则为 True;否则为 False    | &bull; 未报告任何数据来指示流的媒体类型。 |
| 第一个 QoE 记录可用  | Boolean  | 如果第一个终结点的 QoE 记录已报告给 CQD，则为 True。  ||
| 第二条 QoE 记录可用  | Boolean  | 如果第一个终结点的 QoE 记录已报告给 CQD，则为 True。   ||
| Duration 5 seconds or less  | 布尔值  | 如果流的持续时间不超过 5 秒，则为 True;否则为 False。   ||
| Duration 60 seconds or more  | 布尔值  | 如此 如果流的持续时间超过 60 秒，否则为 False。   | |
| 是 Teams  | Boolean  | True 表示流的第一个或第二个用户代理是Microsoft Teams 终结点。 <br/> False 指示用户代理Skype for Business终结点。 |  |
| Duration (Minutes)  | 范围（分钟）  | 流的持续时间，以分钟为单位。 值按范围分组表示。 <br/> **示例值：** 065：[3–4)  ||
| Duration (Seconds)  | 范围（秒） | 流的持续时间，以秒为单位。 值按范围分组表示。 <br/> **示例值：** 062：[1 -2) ||
|**日期**||| |
|结束时间|  String| 通话结束的一天中的时间。 值以 UTC 时区报告。 |&bull; 呼叫设置失败或未建立 (请参阅 CDR 响应原因)  |
| Year  | 整型  | 流的结束年份。 值以 UTC 时区报告。 <br/> **示例值：** 2018 | |
| Month  | 整型  | 流结束的月份。 值以 UTC 时区报告。 <br/> **示例值：** 2 | |
| Day  | 整型  | 流结束的日期。 值以 UTC 时区报告。 <br/> **示例值：** 1 | |
| 日期  | String  | 流的结束日期。 值以 UTC 时区报告。 <br/> **示例值：** 2018-06-01 | |
| Hour  | 整型  | 流结束的小时。 值以 UTC 时区报告。 <br/> **示例值：** 1  ||
| Minute  | 整型  | 流结束的分钟数。 值以 UTC 时区报告。 <br/> **示例值：** 30 | |
| 第二个  | 整型  | 流末尾的第二个。 值以 UTC 时区报告。 <br/> **示例值：** 12 | |
| Day Of Year  | 整型  | 流结束的一年中的某一天。 值以 UTC 时区报告。 <br/> **示例值：** 32 | |
| Day Of Week  | 字符串  | 流结束的星期几。 值以 UTC 时区报告。 <br/> **示例值：** 星期三 | |
| Day Number Of Week  | 整型  | 流结束的星期数。 值以 UTC 时区报告。 <br/> **示例值：** 3 | |
|周|  String  |呼叫开始的一周的开始日期。 <br/> **示例值：** 2019-09-01 |&bull; 呼叫设置失败或未建立 (请参阅 CDR 响应原因)  |
| Month Year  | 字符串  | 流结束的月份和年份。 值以 UTC 时区报告。 <br/> **示例值：** 2017-02 | |
| Full Month  | 日期时间  | 流结束的整个月份。 值以 UTC 时区报告。 <br/> **示例值：** 2017-02-01T00：00：00 | |
|开始时间|String  |呼叫开始的一天中的时间。 值以 UTC 时区报告。 |&bull; 呼叫设置失败或未建立 (请参阅 CDR 响应原因)  |
|**UserAgent** | | | |
| First Domain  | 字符串  | 第一个终结点用户的域。 如果第一个终结点是会议服务器，则它使用会议组织者的域。 也可能是场景中使用的服务帐户的域。  <br/> **示例值：** contoso.com <span></span> | |
| Second Domain  | 字符串  | 第二终结点用户的域。 如果第二个终结点是会议服务器，则它使用会议组织者的域。 也可能是场景中使用的服务帐户的域。 <br/> **示例值：** contoso.com <span></span>  | |
| First User Agent Category  | 字符串  | 第一终结点的用户代理的类别。 <br/> **示例值：** Oc | &bull; 用户代理当前没有映射    |
| Second User Agent Category  | 字符串  | 第二终结点的用户代理的类别。 <br/> **示例值：** Oc | &bull; 用户代理当前没有映射    |
| First User Agent  | 字符串  | 第一终结点的用户代理字符串。 <br/> **示例值：** UCCAPI/16.0.7766.5281 OC/16.0.7766.2047 (Skype for Business)  | &bull; 第一终结点未报告任何用户代理   |
| Second User Agent  | 字符串  | 第二终结点的用户代理字符串。 <br/> **示例值：** UCCAPI/16.0.7766.5281 OC/16.0.7766.2047 (Skype for Business)  | &bull; 第二终结点未报告任何用户代理   |
| Conference Type  | 枚举 <br/>**可能的值：** <br/>&bull; conf：applicationsharing <br/>&bull; conf：audio-video <br/>&bull; conf：focus | 会议 URI 的类型。  <br/> **示例值：** conf：audio-video | &bull; 非会议方案。   |
| 会议 ID  | String | 与流关联的会议 ID (或呼叫 ID) 。 在 cqd.teams.microsoft.com 中，无论呼叫是个人对人 (P2P) 呼叫还是电话会议，所有呼叫都有呼叫 ID。 此维度的行可能太多，无法用作报表中的维度。 它可能会转为用作筛选器。   <br/> **示例值 (cqd.teams.microsoft.com) ：** 5a962ccf-b9cb-436a-a433-f28bf5404ad8  | |
| First Client App Version  | 字符串  | 第一终结点使用的应用程序的版本。 数据从用户代理字符串解析。 <br/> **示例值：** 16.0.7766.2047 | &bull; 无法分析版本字符串 <br/>&bull; 未报告该值。   |
| Second Client App Version  | 字符串  | 第二终结点使用的应用程序的版本。 数据从用户代理字符串解析。 <br/> **示例值：** 16.0.7766.2047 | &bull; 无法分析版本字符串 <br/>&bull; 未报告该值。 |
|会议 ID |String |创建会议时生成的会议的标识符。  <br/> **示例值：** 19：meeting_MzB...zIw@thread.v2| |
|**网络**||| |
| Transport  | 枚举 <br/>**可能的值：** <br/>&bull; Udp <br/>&bull; Tcp <br/>&bull; 未知  | 流使用的网络传输类型。  无法识别表示系统无法确定传输类型是 TCP 还是 UDP。  | &bull; 未报告传输类型 <br/>&bull; 媒体路径未建立  |
| First Connectivity Ice  | 枚举 <br/>**可能的值：** <br/>&bull; DIRECT = 直接网络路径 <br/>&bull; RELAY = 通过中继 <br/>&bull; HTTP = 通过 HTTP 代理 <br/>&bull; FAILED = 连接失败 | 第一终结点使用的 ICE 连接类型。  |&bull; 未报告传输类型 <br/>&bull; 媒体路径未建立   |
| Second Connectivity Ice  | 枚举 <br/>**可能的值：** <br/>&bull; DIRECT = 直接网络路径 <br/>&bull; RELAY = 通过中继 <br/>&bull; HTTP = 通过 HTTP 代理 <br/>&bull; FAILED = 连接失败  | 第二终结点使用的 ICE 连接类型。    | &bull; 未报告传输类型 <br/>&bull; 媒体路径未建立    |
| First IP Address  | 字符串  | IP address for first endpoint. Note this dimension may have too many rows to be used as dimension in a report. It can be used as a filter instead. <br/> **示例值：** 10.0.0.10  | &bull; 未报告传输类型 <br/>&bull; 媒体路径未建立   |
| Second IP Address  | 字符串  | 第二终结点的 IP 地址。 <br/> **注意：** 此维度的行可能太多，无法用作报表中的维度。 It can be used as a filter instead. <br/> **示例值：** 10.0.0.10  | &bull; 未报告传输类型 <br/>&bull; 媒体路径未建立   |
| First Link Speed   |整型  | 第一终结点使用的网络适配器报告的链路速度，以"位/秒"为单位。 <br/> **示例值：** 10000000  | &bull; 未报告传输类型 <br/>&bull; 媒体路径未建立   |
| Second Link Speed   |整型  | 第二终结点使用的网络适配器报告的链路速度，以"位/秒"为单位。 <br/> **示例值：** 10000000 | &bull; 未报告传输类型 <br/>&bull; 媒体路径未建立    |
| First Port  | 端口号  | 第一终结点用于媒体的网络端口号。 <br/> **示例值：** 50018  | &bull; 未报告传输类型 <br/>&bull; 媒体路径未建立   |
| Second Port  | 端口号  | 第二终结点用于媒体的网络端口号。 <br/> **示例值：** 50018 | &bull; 未报告传输类型 <br/>&bull; 媒体路径未建立    |
| First Reflexive Local IP  | 字符串  | IP address of first endpoint as seen by the media relay server. This is typically the public internet IP address associated to the first endpoint for the stream. <br/> **示例值：** 104.43.195.251  | &bull; 未报告传输类型 <br/>&bull; 媒体路径未建立   |
| Second Reflexive Local IP  | 字符串  | IP address of second endpoint as seen by the media relay server. This is typically the public internet IP address associated to the second endpoint for the stream. <br/> **示例值：** 104.43.195.251  | &bull; 未报告传输类型 <br/>&bull; 媒体路径未建立  |
| First Relay IP  | 字符串  | 第一终结点分配的媒体中继服务器的 IP 地址。 <br/> **示例值：** 104.43.195.251  | &bull; 未报告传输类型 <br/>&bull; 媒体路径未建立   |
| Second Relay IP  | 字符串  | 第二终结点分配的媒体中继服务器的 IP 地址。 <br/> **示例值：** 104.43.195.251 | &bull; 未报告传输类型 <br/>&bull; 媒体路径未建立|
| First Relay Port  | 整型  | 第一终结点在媒体中继服务器上分配的媒体端口。 <br/> **示例值：** 3478  | &bull; 未报告传输类型 <br/>&bull; 媒体路径未建立   |
| Second Relay Port  | 整型  | 第二终结点在媒体中继服务器上分配的媒体端口。 <br/> **示例值：** 3478  | &bull; 未报告传输类型 <br/>&bull; 媒体路径未建立|
| First Subnet  | 字符串  | 第一终结点用于媒体流的子网，每个八进制数用短划线隔开。 <br/> **示例值：** 104.43.195.0  | &bull;终结点未报告的数据 <br/>&bull; 媒体路径未建立 <br/>&bull; 已使用 IPv6|
| Second Subnet  | 字符串  | 第二终结点用于媒体流的子网，每个八进制数用短划线隔开。 <br/> **示例值：** 104.43.195.0 | &bull;终结点未报告的数据 <br/>&bull; 媒体路径未建立 <br/>&bull; 已使用 IPv6 |
| First VPN  | 布尔值  | 如此 如果第一终结点使用的网络适配器指示它是 VPN 连接，否则为 False。 某些 VPN 未正确报告此数据。   | &bull; 未报告传输类型 <br/>&bull; 媒体路径未建立   |
| Second VPN  | 布尔值  | 如此 如果第二终结点使用的网络适配器指示它是 VPN 连接，否则为 False。 某些 VPN 未正确报告此数据。    | &bull; 未报告传输类型 <br/>&bull; 媒体路径未建立   |
| Applied Bandwidth Source  | 枚举 <br/>**可能的值：** <br/>&bull; 静态最大值 <br/>&bull; API 模式 <br/>&bull; API Modality_All <br/>&bull; API SendSide BWLimit <br/>&bull; 首选项值 <br/>&bull; 把 <br/>&bull; ReceiveSide TURN <br/>&bull; API SDP 模式 <br/>&bull; 远程接收 <br/>&bull; Side BWLimit <br/>&bull; API ServiceQuality <br/>&bull; API SDP <br/>&bull; 接收端PDP | 指示应用于流的带宽来源。 | &bull; 未报告传输类型 <br/>&bull; 媒体路径未建立   |
| Bandwidth Est | 整数范围  | 第一和第二终结点之间可用的平均带宽估计值，以"位/秒"为单位。  <br/> **示例值：** 026：[260000 - 270000)   | &bull; 未报告传输类型 <br/>&bull; 媒体路径未建立  |
| Mediation Server Bypass Flag  | 布尔值  | 如此 如果媒体流绕过中介服务器，并直接在客户端和 PSTN 网关/PBX 之间，否则为 False。   | &bull; 未报告传输类型 <br/>&bull; 媒体路径未建立    |
| 第一个 CDR 连接类型  | 枚举 <br/>**可能的值：** <br/>&bull; 操作系统 <br/>&bull; PeerDerived <br/>&bull; 打 晕 <br/>&bull; 把  | 指示第一终结点选择用于此流的 ICE 连接路径。 <br/> **示例值：** 操作系统  | &bull; 未报告传输类型 <br/>&bull; 媒体路径未建立   |
| 第二个 CDR 连接类型  | 枚举 <br/>**可能的值：** <br/>&bull; 操作系统 <br/>&bull; PeerDerived <br/>&bull; 打 晕 <br/>&bull; 把  | 指示第二终结点选择用于此流的 ICE 连接路径。  <br/> **示例值：** 操作系统   | &bull; 未报告传输类型 <br/>&bull; 媒体路径未建立   |
|第一个 BSSID|String | 用于连接到网络的第一终结点的无线 LAN 基本服务集标识符。| |
| 第二个 BSSID| String|用于连接到网络的第二终结点的无线 LAN 基本服务集标识符。| |
| 第一个基址 | String | 第一终结点用于分配媒体中继候选项的接口的 IP 地址。 仅适用于过去 28 天的数据，并且仅对具有允许 EUII 访问的角色的用户可见。 <br/> **示例值：** 10.0.0.10 | &bull; 未报告传输诊断类型 <br/>&bull; 媒体路径未建立 |
| 第二个基址 | String | 第二终结点用于分配媒体中继候选项的接口的 IP 地址。 仅适用于过去 28 天的数据，并且仅对具有允许 EUII 访问的角色的用户可见。 <br/> **示例值：** 10.0.0.10 | &bull; 未报告传输诊断类型 <br/>&bull; 媒体路径未建立 |
| 第一个本地地址 | String | 第一终结点在媒体连接检查结束时用于媒体流的 IP 地址。 仅适用于过去 28 天的数据，并且仅对具有允许 EUII 访问的角色的用户可见。 <br/> **示例值：** 10.0.0.10 | &bull; 未报告传输诊断类型 <br/>&bull; 媒体路径未建立 |
| 第二个本地地址 | String | 第二终结点在媒体连接检查结束时用于媒体流的 IP 地址。 仅适用于过去 28 天的数据，并且仅对具有允许 EUII 访问的角色的用户可见。 <br/> **示例值：** 10.0.0.10 | &bull; 未报告传输诊断类型 <br/>&bull; 媒体路径未建立 |
| 第一个本地地址类型 | 枚举 <br/>**可能的值** <br/>&bull;IceAddrType_Os <br/>&bull;IceAddrType_Stun <br/>&bull;IceAddrType_Turn <br/>&bull;IceAddrType_UPnP <br/>&bull;IceAddrType_ISA_Proxy <br/>&bull;IceAddrType_PeerDerived <br/>&bull;IceAddrType_Invalid | 第一个本地地址的候选类型。 IceAddrType_Turn指示中继呼叫。 其余类型表示直接连接。 | &bull; 未报告传输诊断类型 <br/>&bull; 媒体路径未建立 |
| 第二个本地地址类型 | 枚举 <br/>**可能的值** <br/>&bull;IceAddrType_Os <br/>&bull;IceAddrType_Stun <br/>&bull;IceAddrType_Turn <br/>&bull;IceAddrType_UPnP <br/>&bull;IceAddrType_ISA_Proxy <br/>&bull;IceAddrType_PeerDerived <br/>&bull;IceAddrType_Invalid | 第二个本地地址的候选类型。 IceAddrType_Turn指示中继呼叫。 其余类型表示直接连接。 | &bull; 未报告传输诊断类型 <br/>&bull; 媒体路径未建立 |
| 第一个远程地址 | String | 在媒体连接检查结束时，第一终结点将向其发送媒体的第二终结点的 IP 地址。 仅适用于过去 28 天的数据，并且仅对具有允许 EUII 访问的角色的用户可见。 <br/> **示例值：** 10.0.0.10 | &bull; 未报告传输诊断类型 <br/>&bull; 媒体路径未建立 |
| 第二个远程地址 | String | 在媒体连接性检查结束时，第二终结点将向其发送媒体的第一终结点的 IP 地址。 仅适用于过去 28 天的数据，并且仅对具有允许 EUII 访问的角色的用户可见。 <br/> **示例值：** 10.0.0.10 | &bull; 未报告传输诊断类型 <br/>&bull; 媒体路径未建立 |
| 第一个远程地址类型 | 枚举 <br/>**可能的值** <br/>&bull;IceAddrType_Os <br/>&bull;IceAddrType_Stun <br/>&bull;IceAddrType_Turn <br/>&bull;IceAddrType_UPnP <br/>&bull;IceAddrType_ISA_Proxy <br/>&bull;IceAddrType_PeerDerived <br/>&bull;IceAddrType_Invalid | 第一个远程地址的候选类型。 IceAddrType_Turn指示中继呼叫。 其余值表示直接连接。 | &bull; 未报告传输诊断类型 <br/>&bull; 媒体路径未建立 |
| 第二个远程地址类型 | 枚举  <br/>**可能的值** <br/>&bull;IceAddrType_Os <br/>&bull;IceAddrType_Stun <br/>&bull;IceAddrType_Turn <br/>&bull;IceAddrType_UPnP <br/>&bull;IceAddrType_ISA_Proxy <br/>&bull;IceAddrType_PeerDerived <br/>&bull;IceAddrType_Invalid | 第二个远程地址的候选类型。 IceAddrType_Turn指示中继呼叫。 其余值表示直接连接。 | &bull; 未报告传输诊断类型 <br/>&bull; 媒体路径未建立 |
| 第一个本地站点 | String | 第一终结点的 IP 地址，如媒体中继服务器所示。 这通常是与流的第一个终结点关联的公共 Internet IP 地址。 如果由于某种原因无法访问中继或分配失败，则这是第一终结点上本地接口的 IP。 <br/> 这类似于 First Reflexive Local IP，但此信息由传输诊断事件而不是 QoE 报告。 仅适用于过去 28 天的数据，并且仅对具有允许 EUII 访问的角色的用户可见。 <br/> **示例值：** 104.43.195.251 | &bull; 未报告传输诊断类型 <br/>&bull; 媒体路径未建立 |
| 第二个本地站点 | String | 第二终结点的 IP 地址，如媒体中继服务器所示。 这通常是与流的第二个终结点关联的公共 Internet IP 地址。 如果由于某种原因无法访问中继或分配失败，则这是第一终结点上本地接口的 IP。 <br/> 这类似于第二个反射本地 IP，但此信息由传输诊断事件而不是 QoE 报告。 仅适用于过去 28 天的数据，并且仅对具有允许 EUII 访问的角色的用户可见。 <br/> **示例值：** 104.43.195.251 | &bull; 未报告传输诊断类型 <br/>&bull; 媒体路径未建立 |
| 第一个远程站点 | String | 由第二终结点报告并与第一终结点交换的本地站点 IP 地址。 <br/> 第二终结点上的传输诊断事件出于任何原因不可用时的额外信息。 仅适用于过去 28 天的数据，并且仅对具有允许 EUII 访问的角色的用户可见。 <br/> **示例值：** 104.43.195.251 | &bull; 未报告传输诊断类型 <br/>&bull; 媒体路径未建立 |
| 第二个远程站点 | String | 第一终结点报告并与第二个终结点交换的本地站点 IP 地址。 <br/> 第一终结点上的传输诊断事件出于任何原因不可用时的额外信息。 仅适用于过去 28 天的数据，并且仅对具有允许 EUII 访问的角色的用户可见。 <br/> **示例值：** 104.43.195.251 | &bull; 未报告传输诊断类型 <br/>&bull; 媒体路径未建立 |
| 第一个本地媒体中继地址 | String | Microsoft第一终结点分配的媒体中继服务器的 IP 地址。 <br/> 此信息与第一个中继 IP 类似，但由传输诊断事件而不是 QoE 报告。 <br/> **示例值：** 52.114.5.237 | &bull; 未报告传输诊断类型 <br/>&bull; 媒体路径未建立 |
| 第二个本地媒体中继地址 | String | Microsoft第二终结点分配的媒体中继服务器的 IP 地址。 <br/> 此信息与第二个中继 IP 类似，但由传输诊断事件而不是 QoE 报告。 <br/> **示例值：** 52.114.5.237 | &bull; 未报告传输诊断类型 <br/>&bull; 媒体路径未建立 |
| 第一个远程媒体中继地址 | String | Microsoft由第二终结点分配并与第一终结点交换的媒体中继服务器的 IP 地址。 <br/> 如果第二终结点上的传输诊断事件因任何原因而不可用，则提供额外信息。 <br/> **示例值：** 52.114.5.237 | &bull; 未报告传输诊断类型 <br/>&bull; 媒体路径未建立 |
| 第二个远程媒体中继地址 | String | Microsoft由第一终结点分配并与第二终结点交换的媒体中继服务器的 IP 地址。 <br/> 第一终结点上的传输诊断事件出于任何原因不可用时的额外信息。 <br/> **示例值：** 52.114.5.237 | &bull; 未报告传输诊断类型 <br/>&bull; 媒体路径未建立 |
| 第一个传输协议 | 枚举字符串 | 第一终结点用于发送媒体的通信协议。 <br/>**可能的值** <br/>&bull;UDP - 用于 TURN 和主机分配的多用途 UDP <br/>&bull;TurnTCP - TCP TURN 分配。 如果指定了代理设置，则使用代理 <br/>&bull;TCPHostPassive - 被动连接类型的 TCP 侦听主机套接字 <br/>&bull;TCPHostActive - 使用活动连接类型的 TCP 连接 <br/>&bull;CompoundTCP - 上游和下游 TCP 连接的组合。 通常通过 HTTPS 协议。 <br/>&bull;MultiTCP - 一种连接模型，它使用多个 TCP 连接，并使用轮循机制将数据包分发到每个连接。 </br> | &bull; 未报告传输诊断类型 <br/>&bull; 媒体路径未建立 |
| 第二个传输协议 | 枚举字符串 | 第二终结点用于发送媒体的通信协议。 <br/>**可能的值** <br/>&bull;UDP - 用于 TURN 和主机分配的多用途 UDP <br/>&bull;TurnTCP - TCP TURN 分配。 如果指定了代理设置，则使用代理 <br/>&bull;TCPHostPassive - 被动连接类型的 TCP 侦听主机套接字 <br/>&bull;TCPHostActive - 使用活动连接类型的 TCP 连接 <br/>&bull;CompoundTCP - 上游和下游 TCP 连接的组合。 通常通过 HTTPS 协议。 <br/>&bull;MultiTCP - 一种连接模型，它使用多个 TCP 连接，并使用轮循机制将数据包分发到每个连接。 </br> | &bull; 未报告传输诊断类型 <br/>&bull; 媒体路径未建立 |
| 第一个反射本地 IP 网络 | String | 第一终结点的 IP 子网 (/24) ，如媒体中继服务器所示。 这通常是与流的第一个终结点关联的公共 Internet IP 地址的子网。 <br/>**示例值：** 52.114.5.0 | &bull; 未报告传输诊断类型 <br/>&bull; 媒体路径未建立 |
| 第二个反射本地 IP 网络 | String | 第二终结点的 IP 子网 (/24) ，如媒体中继服务器所示。 这通常是与流的第二终结点关联的公共 Internet IP 地址的子网。 <br/>**示例值：** 52.114.5.0 | &bull; 未报告传输诊断类型 <br/>&bull; 媒体路径未建立 |
| 估计的第一个 VPN | Boolean | 指示通过虚拟专用网络 (VPN) 建立连接的概率较高。 <br/>**可能的值：** 0 或 1 | |
| 估计的第二个 VPN | Boolean | 指示通过虚拟专用网络 (VPN) 建立连接的概率较高。 <br/>**可能的值：** 0 或 1 | |
| 第一个漫游触发器 | 枚举 (字符串)  | 指示第一终结点在通话中执行轻量级重新连接（其中不涉及信号）的最新原因。 例如，当终结点在同一网络上切换无线接入点时。 <br/>**可能的值：** <br/> &bull;**远程** - 将数据包发送到对等方，但对等未接收数据包 <br/> &bull;**ConsentKA** - Keep-Alive失败;如果没有对保持活动数据包的响应，则为 7 秒超时 <br/> &bull;**接口** - 本地接口更改或翻盖 <br/> &bull;**RelayDraining** - 服务维护 (预期)  | &bull; 未发生漫游 <br/> &bull; 终结点未发送数据 |
| 第二个漫游触发器 | 枚举 (字符串)  | 指示第二终结点在通话中执行轻量级重新连接（其中不涉及信号）的次数。 例如，当终结点在同一网络上切换无线接入点时。 <br/>**可能的值：** <br/> &bull;**远程** - 将数据包发送到对等方，但对等未接收数据包 <br/> &bull;**ConsentKA** - Keep-Alive失败;如果没有对保持活动数据包的响应，则为 7 秒超时 <br/> &bull;**接口** - 本地接口更改或翻盖 <br/> &bull;**RelayDraining** - 服务维护 (预期)  | &bull; 未发生漫游 <br/> &bull; 终结点未发送数据 |
| 首次漫游计数 | 范围 (整数)  | 指示第一终结点在通话中执行轻量级重新连接（其中不涉及信号）的次数。 例如，当终结点在同一网络上切换无线接入点时。 <br/>**示例值：** 064：[1 - 2)  | |
| 第二个漫游计数 | 范围 (整数)  | 指示第二终结点在通话中执行轻量级重新连接（其中不涉及信号）的次数。 例如，当终结点在同一网络上切换无线接入点时。 <br/>**示例值：** 064：[1 - 2)  | |
|**Device**| |||
| First Capture Dev  | 字符串  | 第一终结点使用的捕获设备的名称。 对于： <br/> **音频流** = 用于麦克风的设备 <br/> **视频流** = 用于相机的设备 <br/> **基于视频的屏幕共享流** = 屏幕抓取器 <br/> **应用共享流** = 空白 <br/> **示例值：** 头戴显示麦克风 (Microsoft LifeChat LX-6000)   | &bull; 终结点未报告数据 <br/>&bull; 媒体路径未建立 <br/>&bull; 流是基于视频的屏幕共享或应用程序共享。  |
| Second Capture Dev  | 字符串  | 第二终结点使用的捕获设备的名称。  <br/> **音频流** = 用于麦克风的设备 <br/> **视频流** = 用于相机的设备 <br/> **基于视频的屏幕共享流** = 屏幕抓取器 <br/> **应用共享流** = 空白 <br/> **示例值：** 头戴显示麦克风 (Microsoft LifeChat LX-6000)  | <br/>&bull; 终结点未报告数据 <br/>&bull; 媒体路径未建立 <br/>&bull; 流是基于视频的屏幕共享或应用程序共享   |
| First Capture Dev Driver  | 字符串  | 第一终结点使用的捕获设备驱动器的名称，格式为"制造商: 版本"。 对于： <br/> **音频流** = 用于麦克风的驱动程序 <br/> **视频流** = 用于相机的驱动程序 <br/> **基于视频的屏幕共享和应用共享流** = 空白  <br/> **示例值：** Microsoft：10.0.14393.0 | <br/>&bull; 终结点未报告数据 <br/>&bull; 媒体路径未建立 <br/>&bull; 流是基于视频的屏幕共享或应用程序共享。  |
| Second Capture Dev Driver  | 字符串  | 第二终结点使用的捕获设备驱动器的名称，格式为"制造商: 版本"。 对于： <br/> **音频流** = 用于麦克风的驱动程序 <br/> **视频流** = 用于相机的驱动程序 <br/> **基于视频的屏幕共享和应用共享流** = 空白 <br/> **示例值：** Microsoft：10.0.14393.0  | <br/>&bull; 终结点未报告数据 <br/>&bull; 媒体路径未建立 <br/>&bull; 流是基于视频的屏幕共享或应用程序共享。  |
| First Render Dev  | 字符串  | 第一终结点使用的呈现设备的名称。 对于： <br/> 音频流 - 用于扬声器的设备 <br/> 基于视频和基于视频的屏幕共享流 - 用于显示的设备 <br/> 应用共享流 - 空  <br/> **示例值：** 头戴显示耳机耳机 (Microsoft LifeChat LX-6000)  | <br/>&bull; 终结点未报告此数据 <br/>&bull; 媒体路径未建立  <br/>&bull; 流是应用程序共享    |
| Second Render Dev  | 字符串  | 第二终结点使用的呈现设备的名称。 对于： <br/> 音频流 - 用于扬声器的设备 <br/> 基于视频和基于视频的屏幕共享流 - 用于显示的设备 <br/> 应用共享流 - 空 <br/> **示例值：** 头戴显示耳机耳机 (Microsoft LifeChat LX-6000)  | <br/>&bull; 终结点未报告此数据， <br/>&bull; 媒体路径未建立 <br/>&bull; 流是应用程序共享     |
| First Render Dev Driver  | 字符串  | 第一终结点使用的呈现设备驱动器的名称。 对于： <br/> 音频流 - 用于扬声器的驱动程序 <br/> 基于视频和基于视频的屏幕共享流 - 用于显示器的驱动程序 <br/> 应用共享流 - 空  <br/> **示例值：** Microsoft：10.0.14393.0 | <br/>&bull; 终结点未报告此数据 <br/>&bull; 媒体路径未建立 <br/>&bull; 流是应用程序共享    |
| Second Render Dev Driver  | 字符串  | 第二终结点使用的呈现设备驱动器的名称。 对于： <br/> 音频流 - 用于扬声器的驱动程序 <br/> 基于视频和基于视频的屏幕共享流 - 用于显示器的驱动程序 <br/> 应用共享流 - 空 <br/> **示例值：** Microsoft：10.0.14393.0  | <br/>&bull; 终结点未报告此数据 <br/>&bull; 媒体路径未建立 <br/>&bull; 流是应用程序共享   |
|**无线**||||
| 第一个Wi-Fi Microsoft驱动程序  | String  | 第一终结点报告的所使用的 Microsoft WiFi 驱动器的名称。 值可能会根据终结点使用的语言进行本地化。 <br/> **示例值：** Microsoft托管网络虚拟适配器  | <br/>&bull; 终结点未使用 WiFi <br/>&bull; 未报告驱动程序信息|
| 第二个Wi-Fi Microsoft驱动程序  | String  | 第二终结点报告的所使用的 Microsoft WiFi 驱动器的名称。 值可能会根据终结点使用的语言进行本地化。 <br/> **示例值：** Microsoft托管网络虚拟适配器  | <br/>&bull; 终结点未使用 WiFi <br/>&bull; 未报告驱动程序信息|
| 第一Wi-Fi供应商驱动程序  | String  | 第一终结点报告的 Wifi 驱动器的供应商和名称。 <br/> **示例值：** Contoso 双频无线交流驱动程序  | <br/>&bull; 终结点未使用 WiFi <br/>&bull; 未报告驱动程序信息 |
| 第二Wi-Fi供应商驱动程序  | String  | 第二终结点报告的 Wifi 驱动器的供应商和名称。  <br/> **示例值：** Contoso 双频无线交流驱动程序 | <br/>&bull; 终结点未使用 WiFi <br/>&bull; 未报告驱动程序信息 |
| 第一Wi-Fi Microsoft驱动程序版本  | String  | 第一终结点报告的 Microsoft Wifi 驱动器的版本。 <br/> **示例值：** Microsoft：10.0.14393.0 | <br/>&bull; 终结点未使用 WiFi <br/>&bull; 未报告驱动程序信息  |
| 第二个Wi-Fi Microsoft驱动程序版本  | String  | 第二终结点报告的 Microsoft Wifi 驱动器的版本。 <br/> **示例值：** Microsoft：10.0.14393.0 | <br/>&bull; 终结点未使用 WiFi <br/>&bull; 未报告驱动程序信息  |
| 第一Wi-Fi供应商驱动程序版本  | String  | 第一终结点报告的 Wifi 驱动器的供应商和版本。 <br/> **示例值：** Contoso：15.1.1.0 | <br/>&bull; 终结点未使用 WiFi <br/>&bull; 未报告驱动程序信息  |
| 第二Wi-Fi供应商驱动程序版本  | String  | 第二终结点报告的 Wifi 驱动器的供应商和版本。 <br/> **示例值：** Contoso：15.1.1.0 | <br/>&bull; 终结点未使用 WiFi <br/>&bull; 未报告驱动程序信息  |
| 第一Wi-Fi频道  | String  | 第一终结点使用的 Wifi 频道。  <br/> **示例值：** 10| <br/>&bull; 未使用 WiFi <br/>&bull; 未报告频道   |
| 第二个Wi-Fi通道  | String  | 第二终结点使用的 Wifi 频道。 <br/> **示例值：** 10  | <br/>&bull; 未使用 WiFi <br/>&bull; 未报告频道  |
| 第一个Wi-Fi单选类型  | String  | 第一终结点使用的 WiFi 无线电的类型。 HRDSSS 等于 802.11b。 <br/> **示例值：** 802.11ac  | <br/>&bull; 未使用 WiFi <br/>&bull; 未报告 WiFi 类型  |
| 第二个Wi-Fi单选类型  | String  | 第二终结点使用的 WiFi 无线电的类型。 HRDSSS 等于 802.11b。 <br/> **示例值：** 802.11ac  | <br/>&bull; 未使用 WiFi <br/>&bull; 未报告 WiFi 类型  |
| First DNS Suffix  | 字符串  | 第一终结点报告的与网络适配器关联的 DNS 后缀。 请注意，可能会为任何类型的网络适配器报告此值。 **示例值：** corp.contoso.com <span></span><span></span>  | <br/>&bull; 终结点未报告此值 <br/>  |
| Second DNS Suffix  | 字符串  | DNS suffix associated with the network adapter reported by the second endpoint. Note this value may be reported for any type of network adapter.<br/> **示例值：** corp.contoso.com <span></span><span></span>   | <br/>&bull; 终结点未报告此值  |
| 第一个Wi-Fi带  | String  | 第一终结点报告的所使用的 Wifi 波段。 <br/> **示例值：** 5.0 Ghz  | <br/>&bull; 值不是由终结点计算的 <br/>&bull; 未报告该值  |
| 第二个Wi-Fi带  | String  | 第二终结点报告的所使用的 Wifi 波段。 <br/> **示例值：** 5.0 Ghz  | <br/>&bull; 值不是由终结点计算的 <br/>&bull; 未报告该值  |
| 第一Wi-Fi信号强度  | String  | 第一终结点报告的 WiFi 信号强度百分比 [0-100]。 <br/> **示例值：** 081：[90 - 100)   | <br/>&bull; 值不是由终结点计算的 <br/>&bull; 未报告该值  |
| 第二Wi-Fi信号强度  | String  | 第二终结点报告的 WiFi 信号强度百分比 [0-100]。 <br/> **示例值：** 081：[90 - 100)   | <br/>&bull; 值不是由终结点计算的 <br/>&bull; 未报告该值  |
| 首次Wi-Fi电池充电  | 范围（百分比）  | Estimated remaining battery charge in percentage [0-99] reported by the first endpoint. Values grouped by range. 0 indicates that the device was plugged in. <br/> **示例值：** 081：[90 - 100)  | &bull; 未使用 WiFi <br/>&bull; 未报告费用值   |
| 第二个Wi-Fi电池充电  | 范围（百分比）  | Estimated remaining battery charge in percentage [0-99] reported by the second endpoint. Values grouped by range. 0 indicates that the device was plugged in.  <br/> **示例值：** 081：[90 - 100)  | &bull; 未使用 WiFi <br/>&bull; 未报告费用值  |
|**指标**||||
| Audio Degradation Avg  | 范围（平均意见得分 0-5） | 关于流降级的网络平均意见得分的平均值。 表示网络丢失和抖动对接收音频质量的影响程度。 不适用于 SATIN 或 WebRTC/VDI。 值按范围分组表示。 <br/> **示例值：** 015：[0.01 - 0.02)  | &bull; 接收流的终结点未报告网络 MOS 降级 <br/>&bull; 流不是音频流。   |
| 抖动  | 范围（毫秒）  | 流的平均抖动值，以毫秒为单位。 值按范围分组表示。 <br/> **示例值：** 065：[2 - 3)   | &bull; 接收流的终结点未报告抖动数据 |
| Jitter Max  | 范围（毫秒）  | 流的最大抖动值，以毫秒为单位。 值按范围分组表示。 <br/> **示例值：** 065：[2 - 3)  | &bull; 接收流的终结点未报告抖动数据   |
| Packet Loss Rate  | 范围（比率）  | 流的平均丢包率。 值按范围分组表示。 0.1 表示 10% 的数据包丢失。 <br/> **示例值：** 015：[0.01 - 0.02)   | &bull; 接收流的终结点未报告数据包丢失数据 |
| Packet Loss Rate Max  | 范围（比率）  | 流的最大丢包率。 值按范围分组表示。 0.1 表示 10% 的数据包丢失。 <br/> **示例值：** 023：[0.09 - 0.1)   | &bull; 接收流的终结点未报告数据包丢失数据  <br/>&bull; 给定流的数据包利用率小于 100 个数据包 |
| 发送侦听 MOS  | 范围 (MOS)  | 流的平均 MOS。 值按范围分组表示。 <br/> **示例值：** 076：[4.4 - 4.5)  | &bull; 接收流的终结点未报告 MOS <br/>&bull; 流不是音频流 <br/>&bull; 使用的编解码器不报告 MOS |
| Overall Avg Network MOS  | 范围 (MOS)  | 流的网络 MOS 平均值。 值按范围分组表示。 <br/> **示例值：** 076：[4.4 - 4.5)  | &bull; 接收流的终结点未报告网络 MOS 降级 <br/>&bull; 流不是音频流 <br/>&bull; 使用的编解码器不报告 MOS |
| Ratio Concealed Samples Avg  | 范围（比率）  | Ratio of the number of audio frames with samples generated by packet loss concealment to the total number of audio frames. Values grouped by range. 0.1 indicates 10% of frames contained concealed samples. <br/> **示例值：** 015：[0.01 - 0.02)  | &bull; 流接收方未报告此值 <br/>&bull; 流不是音频流  |
|最大隐藏比率 |范围（比率） | 包含数据包丢失隐藏生成的样本的最大音频帧数占音频帧总数。 值按范围分组表示。 0.1 表示 10% 的帧包含隐藏样本。 <br/> **示例值：** 015：[0.01 - 0.02) | |
| Ratio Stretched Samples Avg  | 范围（比率）  | Ratio of the number of audio frames with samples that have been stretched to compensate for jitter or loss to the total number of audio frames. Values grouped by range. 0.1 indicates 10% audio frames contained stretched samples. <br/> **示例值：** 017：[0.03 - 0.04)  | &bull; 流接收方未报告此值  <br/>&bull; 流不是音频流   |
|愈合器数据包下降比率|范围（比率） |愈合程序丢弃的音频数据包与愈合程序接收的音频数据包总数的比率。 有关详细信息 [，请参阅 2.2.1.12.1 子元素](/openspecs/office_protocols/ms-qoe/56d41628-26d5-44c8-8f79-6bac4b0355a5) 。| |
| 愈合器 FEC 数据包使用比率| 范围（比率）  |使用前向纠错 (FEC) 数据包与接收的 FEC 数据包总数的比率。 有关详细信息 [，请参阅 2.2.1.12.1 子元素](/openspecs/office_protocols/ms-qoe/56d41628-26d5-44c8-8f79-6bac4b0355a5) 。  | |
| Round Trip  | 范围（毫秒）  | 计算的平均网络传播往返时间，根据 RFC3550 以毫秒为单位指定。 值按范围分组表示。 <br/> **示例值：** 070：[15 - 20)   | <br/>&bull; 值不是由终结点计算的 <br/>&bull; 未报告该值  |
| Round Trip Max  | 范围（毫秒）  | 计算的最大网络传播往返时间，根据 RFC3550 以毫秒为单位指定。 值按范围分组表示。 <br/>**示例值：** 098：[350 - 375)    | <br/>&bull; 值不是由终结点计算的 <br/>&bull; 未报告该值 |
| 数据包利用率 |  (数据包数)  |会话中发送的Real-Time传输协议 (RTP) 数据包的数目。||
| 抖动缓冲区大小平均值|数字 (范围)  |会话期间抖动缓冲区的平均大小。| |
| 最大抖动缓冲区大小|数字 (范围) |会话期间抖动缓冲区的最大大小。 ||
| 抖动缓冲区大小最小值|数字 (范围) |会话期间抖动缓冲区的最小大小。||
|相对单向间隙持续时间| 对等方相对单向延迟的间隔持续时间。|||
| 音频后 FECPLR|  数字 |报告对音频应用 FEC 后的数据包丢失率。 介于 0.00 和 1.00 之间的值。| |
| Network Jitter Avg  | 范围（毫秒）  | 会话期间以 20 秒时间窗口计算的平均网络抖动，以毫秒为单位。 值按范围分组表示。 <br/> **示例值：** 066：[3–4)   | <br/>&bull; 流不是音频流 <br/>&bull; 接收流的终结点未报告数据  |
|最大网络抖动|事件数|会话期间超过 20 秒窗口计算的最大网络抖动。||
| 网络抖动最小值|事件数|会话期间在 20 秒时段内计算的最小网络抖动。| |
| Video Post FECPLR  | 范围（比率）  | 应用 FEC 后，跨所有视频流和编解码器汇总的丢包率。 值按范围分组表示。 <br/> **示例值：** 014：[0 - 0.01)  | <br/>&bull; 流不是视频或基于视频的屏幕共享流  <br/>&bull; 接收流的终结点未报告数据   |
| Video Local Frame Loss Percentage Avg  | 范围（百分比）  | 向用户显示的视频帧丢失平均百分比。 值按范围分组表示。 其中包括从网络丢失恢复的帧。 <br/> **示例值：** 160：[80 - 85)  | <br/>&bull; 流不是视频或基于视频的屏幕共享流  <br/>&bull; 接收流的终结点未报告数据   |
| 接收帧速率平均值  | 范围（每秒帧数）  | 在会话持续期间计算到的所有视频流每秒接收的平均帧数。 值按范围分组表示。 <br/> **示例值：** 101：[14.5 - 15)  | <br/>&bull; 流不是视频或基于视频的屏幕共享流  <br/>&bull; 接收流的终结点未报告数据   |
| Low Frame Rate Call Percent | 范围（百分比）  | 帧速率低于 7.5 帧/秒的通话时间的百分比。 值按范围分组表示。 <br/> **示例值：** 099：[13.5 - 14)  | <br/>&bull; 流不是视频或基于视频的屏幕共享流  <br/>&bull; 接收流的终结点未报告数据   |
| Video Packet Loss Rate  | 范围（比率）  | 在会话持续期间计算到的平均丢包比率（小数），根据 RFC3550 指定。 值按范围分组表示。 <br/> **示例值：** 037：[0.75 - 0.8)  | <br/>&bull; 流不是视频或基于视频的屏幕共享流  <br/>&bull; 接收流的终结点未报告数据   |
| Video Frame Rate Avg  | 范围（每秒帧数）  | 在会话持续期间计算到的视频流每秒接收的平均帧数。 值按范围分组表示。 <br/> **示例值：** 135：[31.5 - 32)   | <br/>&bull; 流不是视频或基于视频的屏幕共享流  <br/>&bull; 接收流的终结点未报告数据  |
| Dynamic Capability Percent  | 范围（百分比）  | 客户端以低于此类型 CPU 预期视频处理容量的 70% 运行的时间的百分比，按范围分组。 <br/> **示例值：** 122：[25 - 25.5)   | <br/>&bull; 流不是视频或基于视频的屏幕共享流  <br/>&bull; 接收流的终结点未报告数据  |
| Spoiled Tile Percent Total  | 范围（百分比）  | Percentage of tiles which are discarded instead of being sent to a remote peer (for example, from the MCU to a viewer). Values grouped by range. Discarded tiles may be caused by bandwidth restrictions between client and server. <br/> **示例值：** 140：[34 - 34.5)   | <br/>&bull; 流不是应用程序共享流 <br/>&bull; 发送流的终结点未报告数据  |
| AppSharing Relative OneWay Average  | 范围（秒）  | 应用程序共享流的终结点之间的平均相对单向延迟（以秒为单位）。 值按范围分组表示。 <br/> **示例值：** 015：[0.01 - 0.02)  | <br/>&bull; 流不是应用程序共享流 <br/>&bull; 发送流的终结点未报告数据   |
| AppSharing RDP Tile Processing Latency Average  | 范围（毫秒）  | 在会议服务器上处理 RDP 堆栈图块的平均延迟，以毫秒为单位。 值按范围分组表示。 <br/> **示例值：** 103：[15.5 - 16)  | &bull; 流不是会议中的应用程序共享流 <br/>&bull; 发送流的终结点未报告数据   | 
| First Network Delay Event Ratio  | 范围（比率）  | Fraction of the call that the first endpoint detected the network delay was significant enough to impact the ability to have real-time two-way communication. Values grouped by range. <br/> **示例值：** 016：[0.02 - 0.03)   | &bull; 这是非音频流 <br/>&bull; 第一终结点未报告数据|
| Second Network Delay Event Ratio  | 范围（比率）  | Fraction of the call that the second endpoint detected the network delay was significant enough to impact the ability to have real-time two-way communication. Values grouped by range. <br/> **示例值：** 016：[0.02 - 0.03)   | &bull; 指示非音频流 <br/>&bull; 第二终结点未报告数据 |
| First Network Bandwidth Low Event Ratio  | 范围（比率）  | Fraction of the call that the first endpoint detected the available bandwidth or bandwidth policy was low enough to cause poor quality of the audio sent. Values grouped by range. <br/> **示例值：** 016：[0.02 - 0.03)  | &bull; 这是非音频流 <br/>&bull; 第一终结点未报告数据  |
| Second Network Bandwidth Low Event Ratio  | 范围（比率）  | Fraction of the call that the second endpoint detected the available bandwidth or bandwidth policy was low enough to cause poor quality of the audio sent. Values grouped by range. <br/> **示例值：** 016：[0.02 - 0.03)  | &bull; 指示非音频流 <br/>&bull; 第二终结点未报告数据 |
| 第一个麦克风故障率| 数字 |第一终结点的麦克风捕获每 5 分钟的平均故障数。 有关详细信息 [，请参阅 2.2.1.12.1 子元素](/openspecs/office_protocols/ms-qoe/56d41628-26d5-44c8-8f79-6bac4b0355a5) 。 ||
| 第二个麦克风故障率|数字 |第二终结点的麦克风捕获每 5 分钟的平均故障数。 有关详细信息 [，请参阅 2.2.1.12.1 子元素](/openspecs/office_protocols/ms-qoe/56d41628-26d5-44c8-8f79-6bac4b0355a5) 。 ||
| 第一个扬声器故障率|事件数|第一个扬声器渲染每 5 分钟的平均故障数。| |
| 第二个扬声器故障率|事件数|第二个扬声器渲染每 5 分钟的平均故障数。| |
|**音频**||||
| Audio FEC Used  | 布尔值  | True 表示通话期间在某些点上使用了音频前向纠错 (FEC)。 False 表示未使用。     | &bull; 流不是音频流 <br/>&bull; 发送流的终结点未报告数据  |
| 使用中的第一个音频呈现设备  | String  | 指示使用哪个硬件设备在第一终结点上播放音频流。  | <br/>&bull; 终结点未报告数据  |
| 正在使用的第二个音频呈现设备  | String  | 指示使用哪个硬件设备播放第二终结点上的音频流。  | <br/>&bull; 终结点未报告数据  |
| 使用中的第一个音频捕获设备  | String  | 指示哪个硬件设备用于捕获第一终结点上的音频流。  | <br/>&bull; 终结点未报告数据  |
| 正在使用的第二个音频捕获设备  | String  | 指示使用哪个硬件设备捕获第二终结点上的音频流。  | <br/>&bull; 终结点未报告数据  |
|**措施**||||
| ClassifiedPoorCall  | 布尔值  | 如此 如果通话中的一个或多个流根据通话 [质量仪表板的流分类](stream-classification-in-call-quality-dashboard.md)中列出的指标被分类为差。   | &bull; 调用没有足够的指标报告为好或差   |
| Video Poor Due To VideoPostFecplr  | 布尔值  | 如此 如果流根据此处列出的视频后 FEC PLR 指标阈值被分类为差： [通话质量仪表板中的流分类](stream-classification-in-call-quality-dashboard.md)。 对于非视频流，始终为 False。   | &bull; 终结点未报告此数据  <br/>&bull; 该流不是视频流。  |
| Video Poor Due To VideoLocalFrameLossPercentageAvg  | Boolean  | 如此 如果视频流根据此处列出的视频本地帧丢失百分比平均值指标阈值被分类为差： [通话质量仪表板中的流分类](stream-classification-in-call-quality-dashboard.md)。 对于非视频流，始终为 False。   | &bull; 终结点未报告此数据  <br/>&bull; 该流不是视频流。 |
| Video Poor Due To VideoFrameRateAvg  | Boolean  | 如此 如果视频流根据此处列出的视频帧速率平均值指标阈值分类差： [通话质量仪表板中的流分类](stream-classification-in-call-quality-dashboard.md)。 对于非视频流，始终为 False。    | &bull; 终结点未报告此数据  <br/>&bull; 流不是视频流 |
| VBSS Poor Due To VideoPostFecplr  | Boolean  | 如此 如果基于视频的屏幕共享流根据此处列出的视频后 FEC PLR 指标阈值被分类为差： [通话质量仪表板中的流分类](stream-classification-in-call-quality-dashboard.md)。 对于基于非视频的屏幕共享流，始终为 False。    | &bull; 终结点未报告此数据 <br/>&bull; 流不是基于视频的屏幕共享流  |
| VBSS Poor Due To VideoLocalFrameLossPercentageAvg  | Boolean  | 如此 如果基于视频的屏幕共享流根据此处列出的视频本地帧丢失百分比平均值指标阈值被分类为差： [通话质量仪表板中的流分类](stream-classification-in-call-quality-dashboard.md)。 对于基于非视频的屏幕共享流，始终为 False。    | &bull; 终结点未报告此数据 <br/>&bull; 流不是基于视频的屏幕共享流  |
| 由于冻结导致视频差 | Boolean  | 如果视频流根据视频冻结实例分类为差，则为 1： [通话质量仪表板中的流分类](stream-classification-in-call-quality-dashboard.md) | &bull; 终结点未报告此数据  <br/>&bull; 该流不是视频流。 此字段特定于Microsoft Teams。 |
| VBSS Poor Due To VideoFrameRateAvg  | Boolean  | 如此 如果基于视频的屏幕共享流根据此处列出的视频帧速率平均指标阈值被分类为差： [通话质量仪表板中的流分类](stream-classification-in-call-quality-dashboard.md)。 对于基于非视频的屏幕共享流，始终为 False。   | &bull; 终结点未报告此数据 <br/>&bull; 流不是基于视频的屏幕共享流   |
| AppSharing Poor Due To SpoiledTilePercentTotal  | Boolean  | 如此 如果应用程序共享流根据此处列出的损坏的平铺总数百分比指标阈值被分类为差： [通话质量仪表板中的流分类](stream-classification-in-call-quality-dashboard.md)。 对于非应用程序共享流，始终为 False。   | &bull; 终结点未报告此数据  <br/>&bull; 流不是应用程序共享流。  |
| AppSharing Poor Due To RelativeOneWayAverage  | Boolean  | 如此 如果应用程序共享流根据此处列出的相对单向平均指标阈值分类差： [通话质量仪表板中的流分类](stream-classification-in-call-quality-dashboard.md)。 对于非应用程序共享流，始终为 False。    | &bull; 终结点未报告此数据  <br/>&bull; 流不是应用程序共享流 |
| AppSharing Poor Due To RDPTileProcessingLatencyAverage | Boolean  | 如此 如果根据此处列出的 RDP 磁贴处理延迟平均指标阈值将应用程序共享流分类为差： [通话质量仪表板中的流分类](stream-classification-in-call-quality-dashboard.md)。 对于非应用程序共享流，始终为 False。    | &bull; 终结点未报告此数据  <br/>&bull; 流不是应用程序共享流 |
| Audio Poor Due To Jitter  | 布尔值  | 如此 如果音频流根据此处列出的抖动指标阈值被分类为差： [通话质量仪表板中的流分类](stream-classification-in-call-quality-dashboard.md)。 对于非音频流，始终为 False。    | &bull; 终结点未报告此数据 <br/>&bull; 流不是音频共享流 |
| Audio Poor Due To RoundTrip  | 布尔值  | 如此 如果音频流根据此处列出的往返指标阈值被分类为差： [通话质量仪表板中的流分类](stream-classification-in-call-quality-dashboard.md)。 对于非音频流，始终为 False。   | &bull; 终结点未报告此数据 <br/>&bull; 流不是音频共享流 |
| Audio Poor Due To Packet Loss  | 布尔值  | 如此 如果音频流根据此处列出的数据包丢失指标阈值被分类为差： [通话质量仪表板中的流分类](stream-classification-in-call-quality-dashboard.md)。 对于非音频流，始终为 False。    | &bull; 终结点未报告此数据 <br/>&bull; 流不是音频共享流 |
| Audio Poor Due To Degradation  | 布尔值  | 如此 如果音频流根据此处列出的降级指标阈值被分类为差： [通话质量仪表板中的流分类](stream-classification-in-call-quality-dashboard.md)。 对于非音频流，始终为 False。 注意：分类器中已弃用此功能。   | &bull; 终结点未报告此数据 <br/>&bull; 流不是音频共享流 |
| Audio Poor Due To Concealed Ratio  | 布尔值  | 如此 如果音频流根据此处列出的隐藏比率指标阈值被分类为差： [通话质量仪表板中的流分类](stream-classification-in-call-quality-dashboard.md)。 对于非音频流，始终为 False。 注意：分类器中已弃用此功能。   | &bull; 终结点未报告此数据 <br/>&bull; 流不是音频共享流 |
| Poor Reason  | 标志 <br/>**可能的值：** <br/>&bull; 隐藏比率 <br/>&bull; 降解 <br/>&bull; 抖动 <br/>&bull; 数据包丢失 <br/>&bull; 往返 <br/> Video Frame Rate Avg <br/> Video Local Frame Loss Percentage Avg <br/>&bull; 视频后 FEC PLR <br/>&bull; RDP 磁贴处理延迟平均值 <br/>&bull; 相对 OneWay 平均值 <br/>&bull; 损坏的平铺总数百分比 | 用于确定为何将流分类为差的一系列标志。 由于将流分类为差的原因有很多，因此可能会有设置多个标记。 有关详细信息，请参阅 [通话质量仪表板中的流分类](stream-classification-in-call-quality-dashboard.md) 。  | &bull; 该流未分类为差 |
| Poor  | 布尔值  | 如此 如果流有足够的数据被分类为好或差，流被分类为差。 否则为 False。   |   |
| Good  | 布尔值  | 如果流有足够的数据被分类为良好或差，并且流被分类为良好，则为 True。 否则为 False。   |   |
| Unclassified  | 布尔值  | 如果流有足够的数据被分类为好或差，则为 False。 否则为 True。 <br/>**示例值：** 1 |   |
| OnePercent PacketLoss  | 布尔值  | 如果数据包丢失超过 1%，则为 True，否则为 False。  |   |
| 检测到入站网络问题 | Boolean | 如果为 true，则表示媒体流可能由于入站网络而受到影响的高置信度。 | &bull; 此维度仅适用于流 *方向 == 第一到第二的流* |
| 检测到上行问题| Boolean | 如果为 true，则表示媒体流可能由于网络上行而受到影响的高置信度。 | &bull; 此维度不适用于 P2P 调用。 |
| 检测到远程输入设备问题 | Boolean | 如果为 true，则表示媒体流可能由于远程捕获设备而受到影响的高置信度。 |
| 检测到本地输入设备问题 | Boolean | 如果为 true，则表示媒体流可能由于第一终结点上的呈现设备而受到影响的高置信度。 | &bull; 此维度仅适用于流 *方向 == 第一到第二的流* |
| 检测到回显| Boolean | 如果为 true，则表示媒体流可能由于回显而受到影响的高置信度。|
| 检测到远程计算问题 | Boolean | 如果为 true，则表示媒体流可能由于远程端的计算资源而受到影响的高置信度。 |
| 检测到本地计算问题 | Boolean | 如果为 true，则表示媒体流可能由于本地计算资源而受到影响的高置信度。 | &bull; 此维度仅适用于流 *方向 == 第一到第二的流* |
| 检测到媒体模式问题 | Boolean | 如果为 true，则表示用户对入站媒体流的体验较差的置信度很高。 | &bull; 此维度仅适用于流 *方向 == 第一到第二的流* |
|**评级**||||
| First Feedback Rating  | 用户评级 (1-5)  | Rating of the call associated with the stream by the first endpoint on 1-5 scale (5 = excellent). 0 indicates the user was shown the call rating survey but did not rate their experience.  <br/> **示例值：** 5 | &bull; 未向第一终结点显示任何调查  |
| Second Feedback Rating  | 用户评级 (1-5)  | Rating of the call associated with the stream by the second endpoint on 1-5 scale (5 = excellent). 0 indicates the user was shown the call rating survey but did not rate their experience. <br/> **示例值：** 5 | &bull; 未向第二终结点显示任何调查   |
| First Feedback Tokens  | 字符串  | 包含具有布尔标志的反馈令牌列表的字符串，指示令牌是否由提供来自第一终结点的反馈的用户设置。 <br/> **示例值：** {DistortedSpeech：1;ElectronicFeedback：1;BackgroundNoise：1;MuffledSpeech：1;Echo：1;}  | &bull; 第一终结点的用户未提供任何反馈  |
| Second Feedback Tokens  | 字符串  | 包含具有布尔标志的反馈令牌列表的字符串，指示令牌是否由提供来自第二终结点的反馈的用户设置。 <br/> **示例值：** {DistortedSpeech：1;ElectronicFeedback：1;BackgroundNoise：1;MuffledSpeech：1;Echo：1;}  | &bull; 第二终结点的用户未提供任何反馈  |
| First Feedback Has Audio Issue  | 布尔值  | 如果第一终结点的反馈标记指出流包含音频问题，则为 True，否则为 False。   |  |
| Second Feedback Has Audio Issue  | 布尔值  | 如果来自第二终结点的反馈令牌指示流存在音频问题，则为 True;否则为 False。    ||
| First Feedback Has Video Issue  | 布尔值  | 如果第一终结点的反馈令牌指示流存在视频问题，则为 True，否则为 False。    | |
| Second Feedback Has Video Issue  | 布尔值  | 如果第二终结点的反馈令牌指示流存在视频问题，则为 True，否则为 False。    | |
| 第一个反馈存在应用共享问题  | Boolean  | 如果第一终结点的反馈令牌指示流存在应用共享问题，则为 True。 否则为 False。 | |  
| 第二个反馈存在应用共享问题  | Boolean  | 如果来自第二终结点的反馈令牌指示流存在应用共享问题，则为 True。 否则为 False。 | |  
|**音频信号**||||
| First Echo Event Causes  | 标志  | Flags that indicate the reasons the DeviceEchoEvent was raised on the first endpoint. There may be multiple flags for a single stream. Flags include: <br/> BAD_TIMESTAMP - 从所使用的具有较差质量的捕获设备或呈现设备上获得的音频时间戳 <br/> POSTAEC_ECHO - 消除回声后仍具有较高水平的回声 <br/> MIC_CLIPPING - 拥有最大信号强度显著实例的捕获设备上的信号强度 <br/> EVENT_ANLP - 包含高噪音的捕获设备上的音频采样。 <br/> **示例值：** BAD_TIMESTAMP | &bull; 这是非音频流 <br/>&bull; 第一个终结点未报告任何事件原因  |
| Second Echo Event Causes  | 标志  | Flags that indicate the reasons the DeviceEchoEvent was raised on the second endpoint. There may be multiple flags for a single stream. Flags include: <br/> BAD_TIMESTAMP - 从所使用的具有较差质量的捕获设备或呈现设备上获得的音频时间戳 <br/> POSTAEC_ECHO - 消除回声后仍具有较高水平的回声 <br/> MIC_CLIPPING - 拥有最大信号强度显著实例的捕获设备上的信号强度 <br/> EVENT_ANLP - 包含高噪音的捕获设备上的音频采样。 <br/> **示例值：** BAD_TIMESTAMP   | &bull; 这是非音频流 <br/>&bull; 第一个终结点未报告任何事件原因 |
| First Echo Percent Mic In  | 范围（百分比）  | Percentage of time when echo is detected in the audio from the capture or microphone device prior to echo cancellation by the first endpoint. Values grouped by range.  <br/> **示例值：** 068：[5 - 10)   | &bull; 这是非音频流 <br/>&bull; 第一终结点未报告数据 |
| Second Echo Percent Mic In  | 范围（百分比）  | Percentage of time when echo is detected in the audio from the capture or microphone device prior to echo cancellation by the second endpoint. Values grouped by range. <br/> **示例值：** 068：[5 - 10)  | &bull; 指示非音频流 <br/>&bull; 第二终结点未报告数据 |
| First Echo Percent Send  | 范围（百分比）  | 第一终结点在回声取消后在音频中检测到时间回声的百分比。 值按范围分组表示。 <br/> **示例值：** 068：[5 - 10)   | &bull; 这是非音频流 <br/>&bull; 第一终结点未报告数据 |
| Second Echo Percent Send  | 范围（百分比）  | 第二终结点在回声取消后在音频中检测到时间回声的百分比。 值按范围分组表示。 <br/> **示例值：** 068：[5 - 10)  | &bull; 指示非音频流 <br/>&bull; 第二终结点未报告数据 |
| First Send Signal Level  | 范围（dB、分贝）  | Average energy level of sent audio for audio classified as mono speech, or left channel of stereo speech by the first endpoint. Values grouped by range. <br/> **示例值：** 055：[-15 - -10)  | &bull; 这是非音频流 <br/>&bull; 第一终结点未报告数据 |
| Second Send Signal Level  | 范围（dB、分贝）  | Average energy level of sent audio for audio classified as mono speech, or left channel of stereo speech by the second endpoint. Values grouped by range. <br/> **示例值：** 055：[-15 - -10)  | &bull; 指示非音频流 <br/>&bull; 第二终结点未报告数据  |
| 首次接收信号级别  | 范围（dB、分贝）  | Average energy level of received audio for audio classified as mono speech, or left channel of stereo speech by the first endpoint. Values grouped by range. <br/> **示例值：** 056：[-10 - -5)   | &bull; 这是非音频流 <br/>&bull; 第一终结点未报告数据 |
| 第二个接收信号级别  | 范围（dB、分贝）  | Average energy level of received audio for audio classified as mono speech, or left channel of stereo speech by the second endpoint. Values grouped by range. <br/> **示例值：** 056：[-10 - -5)  | &bull; 指示非音频流 <br/>&bull; 第二终结点未报告数据  |
| First Send Noise Level  | 范围（dB、分贝）  | 分类为单声道噪音或立体声左声道噪音（由第一终结点发送）的音频的平均能量水平。 值按范围分组表示。 <br/> **示例值：** 048：[-50 - -45)   | &bull; 这是非音频流 <br/>&bull; 第一终结点未报告数据 |
| Second Send Noise Level  | 范围（dB、分贝）  | 第二终结点分类为单声道噪音或立体声左声道噪音的音频的平均能量水平。 值按范围分组表示。 <br/> **示例值：** 048：[-50 - -45)   | &bull; 指示非音频流 <br/>&bull; 第二终结点未报告数据 |
| 首次接收的噪音级别  | 范围（dB、分贝）  | 第一终结点接收的单声道噪音或立体声左声道噪声的平均能量水平。 值按范围分组表示。 <br/> **示例值：** 048：[-50 - -45)   | &bull; 这是非音频流 <br/>&bull; 第一终结点未报告数据 |
| 第二个接收噪音级别  | 范围（dB、分贝）  | 第二终结点接收的单声道噪声或立体声左声道噪声的平均能量水平。 值按范围分组表示。 <br/> **示例值：** 048：[-50 - -45)   | &bull; 指示非音频流 <br/>&bull; 第二终结点未报告数据 |
|第一个初始信号级别 RMS | 范围（dB、分贝） | 第一终结点调用前 30 秒接收信号的均方根 (RMS) 。 请参阅 [2.2.1.28.1 子元素](/openspecs/office_protocols/ms-qoe/3c78f383-73fe-49f6-89cb-614e7aa8b2e7)  | |
| 第二个初始信号级别 RMS |范围（dB、分贝） | 第二终结点调用的前 30 秒，均方根 (RMS) 接收的信号。 有关详细信息 [，请参阅 2.2.1.28.1 子元素](/openspecs/office_protocols/ms-qoe/3c78f383-73fe-49f6-89cb-614e7aa8b2e7) 。||
| 第一个 RxAGC 信号级别 |范围（dB、分贝）| 在第一个入站音频流的自动增益控制 (AGC) 接收的信号级别。| |
| 第二个 RxAGC 信号级别 |范围（dB、分贝）|第二个入站音频流的自动增益控制 (AGC) 接收的信号级别。|| 
| 第一个 RxAGC 干扰级别|范围（dB、分贝）|对于第一个入站音频流，自动增益控制 (AGC) 接收的噪音级别。 ||
| 第二个 RxAGC 噪声级别|范围（dB、分贝）|对于第二个入站音频流，自动增益控制 (AGC) 接收的噪音级别。||
| 第一个呈现环回信号级别 |范围（dB、分贝）| 第一个入站音频流的环回信号级别。 ||
| 第二个呈现环回信号级别 |范围（dB、分贝）|第二个入站音频流的环回信号级别。||
|**客户端事件** ||||
| First Network Send Quality Event Ratio  | 范围（比率）  | 满足以下条件的通话的比率（小数）：第一终结点检测到网络导致已发送音频的质量差。 值按范围分组表示。 <br/> **示例值：** 015：[0.01 - 0.02)    | &bull; 指示非音频流 <br/>&bull; 第一终结点未报告数据|
| Second Network Send Quality Event Ratio  | 范围（比率）  | 满足以下条件的通话的比率（小数）：第二终结点检测到网络导致已发送音频的质量差。 值按范围分组表示。 <br/> **示例值：** 015：[0.01 - 0.02)   | &bull; 指示非音频流 <br/>&bull; 第二终结点未报告数据 |
| First Network Receive Quality Event Ratio  | 范围（比率）  | 满足以下条件的通话的比率（小数）：第一终结点检测到网络导致已接收音频的质量差。 值按范围分组表示。 <br/> **示例值：** 015：[0.01 - 0.02)   | &bull; 这是非音频流 <br/>&bull; 第一终结点未报告数据 |
| Second Network Receive Quality Event Ratio  | 范围（比率）  | 满足以下条件的通话的比率（小数）：第二终结点检测到网络导致已接收音频的质量差。 值按范围分组表示。 <br/> **示例值：** 015：[0.01 - 0.02)   | &bull; 指示非音频流 <br/>&bull; 第二终结点未报告数据 |
| First CPU Insufficient Event Ratio  | 范围（比率）  | Fraction of the call that the first endpoint detected the CPU resources available were insufficient and caused poor quality of the audio sent and received. Values grouped by range. <br/> **示例值：** 016：[0.02 - 0.03)   | &bull; 指示非音频流 <br/>&bull; 第一终结点未报告数据 |
| Second CPU Insufficient Event Ratio  | 范围（比率）  | Fraction of the call that the second endpoint detected the CPU resources available were insufficient and caused poor quality of the audio sent and received. Values grouped by range. <br/> **示例值：** 016：[0.02 - 0.03)   | &bull; 指示非音频流 <br/>&bull; 第二终结点未报告数据 |
| First Device Half Duplex AEC Event Ratio  | 范围（比率）  | 第一终结点检测到问题并在半双工模式下操作声学回声消除器，这影响了实时双向通信的能力。 值按范围分组表示。 <br/> **示例值：** 016：[0.02 - 0.03)   | &bull; 这是非音频流 <br/>&bull; 第一终结点未报告数据 |
| Second Device Half Duplex AEC Event Ratio  | 范围（比率）  | 第二终结点检测到问题并在半双工模式下操作声学回声消除器，这影响了实时双向通信的能力。 值按范围分组表示。 <br/> **示例值：** 016：[0.02 - 0.03)  | &bull; 指示非音频流 <br/>&bull; 第二终结点未报告数据  |
| First Device Render Not Functioning Event Ratio  | 范围（比率）  | 第一终结点检测到呈现设备无法正常工作的调用的一小部分。 值按范围分组表示。 <br/> **示例值：** 016：[0.02 - 0.03)  | &bull; 这是非音频流 <br/>&bull; 第一终结点未报告数据  |
| Second Device Render Not Functioning Event Ratio  | 范围（比率）  | 第二终结点检测到呈现设备无法正常工作的调用的一小部分。 值按范围分组表示。 <br/> **示例值：** 016：[0.02 - 0.03)   | &bull; 指示非音频流 <br/>&bull; 第二终结点未报告数据 |
| First Device Capture Not Functioning Event Ratio  | 范围（比率）  | 第一终结点检测到捕获设备无法正常工作的调用的一小部分。 值按范围分组表示。 <br/> **示例值：** 016：[0.02 - 0.03)  | &bull; 这是非音频流 <br/>&bull; 第一终结点未报告数据  |
| Second Device Capture Not Functioning Event Ratio  | 范围（比率）  | 第二终结点检测到捕获设备无法正常工作的调用的一小部分。 值按范围分组表示。 <br/> **示例值：** 016：[0.02 - 0.03)   | &bull; 指示非音频流 <br/>&bull; 第二终结点未报告数据 |
| First Device Glitches Event Ratio  | 范围（比率）  | 第一终结点检测到导致发送或接收音频质量不佳的故障或间隔的呼叫的分数。 值按范围分组表示。 <br/> **示例值：** 016：[0.02 - 0.03)  | &bull; 这是非音频流 <br/>&bull; 第一终结点未报告数据  |
| Second Device Glitches Event Ratio  | 范围（比率）  | 第二终结点检测到的通话的小数部分在音频中检测到故障或间隙，导致发送或接收的音频质量不佳。 值按范围分组表示。 <br/> **示例值：** 016：[0.02 - 0.03)  | &bull; 指示非音频流 <br/>&bull; 第二终结点未报告数据  |
| First Device Low SNR Event Ratio  | 范围（比率）  | Fraction of the call that the first endpoint detected low speech to noise level that caused poor quality of the audio being sent. Values grouped by range. <br/> **示例值：** 016：[0.02 - 0.03)  | &bull; 指示非音频流 <br/>&bull; 第一终结点未报告数据  |
| Second Device Low SNR Event Ratio  | 范围（比率）  | Fraction of the call that the second endpoint detected low speech to noise level that caused poor quality of the audio being sent. Values grouped by range. <br/> **示例值：** 016：[0.02 - 0.03)  | &bull; 指示非音频流 <br/>&bull; 第二终结点未报告数据  |
| First Device Low Speech Level Event Ratio  | 范围（比率）  | Fraction of the call that the first endpoint detected low speech level that caused poor quality of the audio being sent. Values grouped by range. <br/> **示例值：** 016：[0.02 - 0.03)   | &bull; 这是非音频流 <br/>&bull; 第一终结点未报告数据 |
| Second Device Low Speech Level Event Ratio  | 范围（比率）  | Fraction of the call that the second endpoint detected low speech level that caused poor quality of the audio being sent. Values grouped by range. <br/> **示例值：** 016：[0.02 - 0.03)  | &bull; 指示非音频流 <br/>&bull; 第二终结点未报告数据  |
| First Device Clipping Event Ratio  | 范围（比率）  | Fraction of the call that the first endpoint detected clipping in the captured audio that caused poor quality of the audio being sent. Values grouped by range. <br/> **示例值：** 016：[0.02 - 0.03)  | &bull; 指示非音频流 <br/>&bull; 第一终结点未报告数据  |
| Second Device Clipping Event Ratio  | 范围（比率）  | Fraction of the call that the second endpoint detected clipping in the captured audio that caused poor quality of the audio being sent. Values grouped by range. <br/> **示例值：** 016：[0.02 - 0.03)   | &bull; 指示非音频流 <br/>&bull; 第二终结点未报告数据 |
| First Device Echo Event Ratio  | 范围（比率）  | 满足以下条件的通话的比率（小数）：第一终结点检测到回声，导致发送的音频质量差。 值按范围分组表示。 <br/> **示例值：** 016：[0.02 - 0.03)   | &bull; 这是非音频流 <br/>&bull; 第一终结点未报告数据 |
| Second Device Echo Event Ratio  | 范围（比率）  | 满足以下条件的通话的比率（小数）：第二终结点检测到回声，导致发送的音频质量差。 值按范围分组表示。 <br/> **示例值：** 016：[0.02 - 0.03)   | &bull; 指示非音频流 <br/>&bull; 第二终结点未报告数据 |
| First Device Near End To Echo Ratio Event Ratio | 范围（比率）| 第一终结点检测到近端信号与回声比率导致音频质量不佳的呼叫的分数。 值按范围分组表示。 <br/> **示例值：** 016：[0.02 - 0.03)  | &bull; 这是非音频流 <br/>&bull; 第一终结点未报告数据|
| Second Device Near End To Echo Ratio Event Ratio  | 范围（比率）  | 第二终结点检测到近端信号与回声级别的比率导致音频质量不佳的呼叫的分数。 值按范围分组表示。 <br/> **示例值：** 016：[0.02 - 0.03)   | &bull; 指示非音频流 <br/>&bull; 第二终结点未报告数据 |
| First Device Render Zero Volume Event Ratio  | 范围（比率）  | 满足以下条件的通话的比率（小数）：第一终结点检测到设备呈现音量设置为 0。 值按范围分组表示。  <br/> **示例值：** 016：[0.02 - 0.03)  | &bull; 这是非音频流 <br/>&bull; 第一终结点未报告数据 |
| Second Device Render Zero Volume Event Ratio  | 范围（比率）  | 满足以下条件的通话的比率（小数）：第二终结点检测到设备呈现音量设置为 0。 值按范围分组表示。 <br/> **示例值：** 016：[0.02 - 0.03)  | &bull; 指示非音频流 <br/>&bull; 第二终结点未报告数据  |
| First Device Render Mute Event Ratio  | 范围（比率）  | 满足以下条件的通话的比率（小数）：第一终结点检测到设备呈现被静音。 值按范围分组表示。 <br/> **示例值：** 016：[0.02 - 0.03)    | &bull; 这是非音频流 <br/>&bull; 第一终结点未报告数据 |
| Second Device Render Mute Event Ratio  | 范围（比率）  | 满足以下条件的通话的比率（小数）：第二终结点检测到设备呈现被静音。 值按范围分组表示。 <br/> **示例值：** 016：[0.02 - 0.03)  | &bull; 指示非音频流 <br/>&bull; 第二终结点未报告数据  |
| First Device Multiple Endpoints Event Count  | 范围（比率）  | Number of times during the call that the first endpoint detected multiple endpoints in the same room or acoustic environment. Values grouped by range. <br/> **示例值：** 016：[0.02 - 0.03)   | &bull; 这是非音频流 <br/>&bull; 第一终结点未报告数据 |
| Second Device Multiple Endpoints Event Count  | 范围（比率）  | Number of times during the call that the second endpoint detected multiple endpoints in the same room or acoustic environment. Values grouped by range. <br/> **示例值：** 016：[0.02 - 0.03)   | &bull; 指示非音频流 <br/>&bull; 第二终结点未报告数据 |
| First Device Howling Event Count  | 范围（比率）  | 通话期间，第一终结点检测到同一房间中的两个或更多终结点的次数，这些终结点以咆叫或尖叫音频的形式导致音频质量不佳。 值按范围分组表示。 <br/> **示例值：** 016：[0.02 - 0.03)   | &bull; 这是非音频流 <br/>&bull; 第一终结点未报告数据 |
| Second Device Howling Event Count  | 范围（比率）  | Number of times during the call that the second endpoint detected two or more endpoints in the same room or acoustic environment that caused poor quality audio in the form of howling or screeching audio. Values grouped by range. <br/> **示例值：** 016：[0.02 - 0.03)   | &bull; 指示非音频流 <br/>&bull; 第二终结点未报告数据 |
|**呼叫诊断**||||
| Error Report Sender  | 字符串  | Indicates which endpoint sent the call error report for the stream. This report contains additional telemetry and may indicate call setup or call drop issue with the call. <br/> **示例值：** 第一 | &bull; 指示未收到呼叫错误报告。  |
| Is Media Error  | 字符串  | Indicates if the call error report for the stream was a media level error or not. This report contains additional telemetry and may indicate call setup or call drop issue with the call.    | &bull; 指示未收到呼叫错误报告。 |
| Media Failure Type  | 枚举 <br/>**可能的值：** <br/>&bull; Midcall <br/>&bull;  CallSetup <br/>&bull; MediaFailureUnknownType <br/>&bull;  NotMediaFailure | 与流关联的媒体故障的类型。 <br/> 注意：“NotMediaFailure”并不表示发生了非媒体故障，仅表示未发生媒体故障。 MediaFailureUnknownType 指示检测到媒体故障，但由于是边缘案例方案或缺少遥测数据，未属于 MidCall 或 CallSetup 分类。   | &bull; 指示未收到呼叫错误报告。   |
| 呼叫分类| 枚举 |分配给调用的可靠性分类。 <br/> **可能的值**：Success、Failure、ClassificationUnavailable | |
| 分类原因|String|将分类分配给流的原因。| |
| 测试调用类型|枚举|指示此调用是常规调用还是测试调用。 如果是测试调用，则指示测试调用的类型。 <br/>**可能的值：** NonTest、Silent、UserInitiated、Synthetic <br/>**意义：** <br/> 非测试 - 常规调用 <br/> 无提示 - 无提示测试调用 <br/> UserInitiated - 用户发起的测试调用 <br/>合成 - ST 终结点发起的调用||
|**Session**||||
| RTP RTCP 复用  | Boolean  | True 表示在同一端口多路复用 RTP 和 RTCP。 否则为 False。    | <br/>&bull; 终结点未报告数据  |
| Stun Version  | 整型  | 建立通话所使用的 STUN 协议的版本。  | <br/>&bull; 终结点未报告数据 <br/> **示例值：** 2  |
| Media Relay  | 字符串  | 用于会话的一个或多个媒体中继的 IP 地址。 对于流，可能会报告一对中继，中间用"+"隔开。 <br/> **示例值：** "13.107.8.2 + 13.107.8.2"  | &bull; 终结点未报告此数据  |
| Is Anonymous Join Session  | 布尔值  | 如果用户匿名加入会议，则为 True，否则为 False。   | &bull; 没有用于确定用户是否匿名加入的数据   |
| 具有媒体诊断 Blob  | Boolean  | 如何会话具有媒体诊断数据，则为 True，否则为 False。   | &bull; 未为此流收集一些信号数据   |
| Call Setup Failure Reason  | 枚举  | 通话未能建立媒体连接的原因分类。 <br/>**可能的值：** <br/> **缺少 FW 深度数据包检查豁免规则** - 指示路径上的网络设备可能因深度数据包检查规则而阻止建立媒体路径。 这可能是因为未正确配置代理或防火墙规则。 <br/> **缺少 FW IP 阻止豁免规则** - 指示路径上的网络设备可能阻止建立到Office 365网络的媒体路径。 这可能是因为未正确将代理或防火墙规则配置为允许访问用于 Skype for Business 流量的 IP 地址和端口。 <br/> **其他** - 指示无法建立调用的媒体路径，但无法对根本原因进行分类。 <br/> 不是媒体故障 - 指示在建立媒体路径时未检测到问题。  | &bull; 由于未知媒体问题，呼叫设置失败  |
| 会话类型  | 枚举 <br/>**可能的值：** <br/> Conf、P2P  | 指示呼叫会话类型是会议 (Conf) 还是对等呼叫 (P2P) 方案。 <br/> **示例值：** Conf | |
| CDR 响应原因  | 枚举 <br/>**可能的值：** <br/> 0 或 200 = “OK” <br/> 410 = “MediaConnectivityErrors”<br/> 480 = “UserUnavailable”<br/> 487 = “PickupTimedOut” <br/> 603 = “CallDeclined” <br/> 所有其他 CDR 代码 = “Other” | 提供通话会话结束的原因、呼叫是否成功，并允许区分不完整的呼叫 (无应答、忙碌、拒绝) 和失败呼叫 (媒体建立) 。 请注意，410 错误可能并不总是与“失败”分类相关联;这是由于标识的排除项造成的，因此不被视为影响媒体故障。 <br/> **示例值：** 还行 | <br/>&bull;值“Other”表示响应代码在诊断上对Microsoft的工程团队没有帮助 |
|**DNS**||||
| 已用 DNS 解析缓存  | Boolean  | 如果终结点使用了 DNS 缓存来解析媒体中继地址，则为 True，否则为 False。    | <br/>&bull; 终结点未报告此数据    |
|**UserData**| |||
| First User ObjectId|String|第一终结点用户的 Active Directory 对象 ID。 仅适用于过去 28 天的数据，并且仅对具有允许 EUII 访问的角色的用户可见。  | |
| Second User ObjectId|String|第二终结点用户的 Active Directory 对象 ID。 仅适用于过去 28 天的数据，并且仅对具有允许 EUII 访问的角色的用户可见。 | |
| 第一个 MAC 地址|String|媒体访问控制 (MAC) 第一终结点的网络设备的地址。 仅适用于过去 28 天的数据，并且仅对具有允许 EUII 访问的角色的用户可见。| |
| 第二个 MAC 地址|String|媒体访问控制 (MAC) 第二终结点的网络设备的地址。 仅适用于过去 28 天的数据，并且仅对具有允许 EUII 访问的角色的用户可见。| |
| 第一个 Sip Uri|String|会话初始协议 (第一终结点用户的 SIP) URI。 仅适用于过去 28 天的数据，并且仅对具有允许 EUII 访问的角色的用户可见。| &bull;仅为Skype for Business终结点填充。 <br/>&bull; 用户没有查看 EUII 的权限。 |
| 第二个 Sip Uri|String|第一终结点用户的 SIP URI。 仅适用于过去 28 天的数据，并且仅对具有允许 EUII 访问的角色的用户可见。| &bull;仅为Skype for Business终结点填充。<br/>&bull; 用户没有查看 EUII 的权限。 |
| 第一个电话号码|String|第一终结点用户的电话号码。 仅适用于过去 28 天的数据，并且仅对具有允许 EUII 访问的角色的用户可见。 无论 EUII 查看权限如何，PSTN 号码的最后四位数字始终在 CQD 中被模糊处理。<br/> **示例值：** +1425555****| &bull; 仅为 PSTN 终结点填充。 <br/>&bull; 用户没有查看 EUII 的权限。 |
| 第二个电话号码|String|第二终结点用户的电话号码。 仅适用于过去 28 天的数据，并且仅对具有允许 EUII 访问的角色的用户可见。 无论 EUII 查看权限如何，PSTN 号码的最后四位数字始终在 CQD 中被模糊处理。<br/> **示例值：** +1425555**** | &bull; 仅为 PSTN 终结点填充。<br/>&bull; 用户没有查看 EUII 的权限。 |
| 第一个 UPN|String|用户主体名称 (UPN) 第一终结点的用户。 仅适用于过去 28 天的数据，并且仅对具有允许 EUII 访问的角色的用户可见。| &bull; 并非所有 UserType 都具有 UPN;包括 First UserType 或 First User ObjectId 维度，以了解有关这些终结点的详细信息。 |
| 第二个 UPN|String|用户主体名称 (第二终结点用户的 UPN) 。 仅适用于过去 28 天的数据，并且仅对具有允许 EUII 访问的角色的用户可见。| &bull; 并非所有 UserType 都具有 UPN;包括 Second UserType 或 Second User ObjectId 维度，以了解有关这些终结点的详细信息。 |
| 第一个反馈文本|String|第一终结点的用户在调用结束时提供的逐字反馈文本（如果有）。 仅适用于过去 28 天的数据，并且仅对具有允许 EUII 访问的角色的用户可见。 | |
| 第二个反馈文本|String| 调用结束时由第二终结点的用户提供的逐字反馈文本（如果有）。 仅适用于过去 28 天的数据，并且仅对具有允许 EUII 访问的角色的用户可见。||
| 第一个客户端终结点名称|String|第一个终结点的计算机名称。 仅适用于过去 28 天的数据，并且仅对具有允许 EUII 访问的角色的用户可见。||
| 第二个客户端终结点名称|String|第二终结点的计算机名称。 仅适用于过去 28 天的数据，并且仅对具有允许 EUII 访问的角色的用户可见。||
| 第一终结点产品名称|String|第一个终结点的产品名称 (Skype for Business或Microsoft Teams) 。||
| 第二终结点产品名称|String|第二终结点的产品名称 (Skype for Business或Microsoft Teams) 。||
| First UserType|枚举字符串|第一终结点上的用户类型。 <br/> **可能的值：** 用户、服务器、匿名、应用程序、PSTN、语音邮件、未知 <br/> <br/>**未知** - 如果无法根据收到的信息确定 UserType，则为默认值。 <br/>**PSTN** - PSTN 用户。 <br/>**匿名** - Teams 用户或Skype for Business访问者。 <br/>**应用程序** - 机器人。 <br/>**用户** - AAD 用户，可以是Skype for Business用户或 Teams 用户。 <br/>**服务器** - 对于会议，至少有一端是服务器。 <br/>**语音邮件** - 终结点已由语音邮件服务应答。||
| Second UserType|枚举字符串|第二终结点上的用户类型。 <br/> **可能的值：** 用户、服务器、匿名、应用程序、PSTN、语音邮件、未知 <br/> <br/>**未知** - 如果无法根据收到的信息确定 UserType，则为默认值。 <br/>**PSTN** - PSTN 用户。 <br/>**匿名** - Teams 用户或Skype for Business访问者。 <br/>**应用程序** - 机器人。 <br/>**用户** - AAD 用户，可以是Skype for Business用户或 Teams 用户。 <br/>**服务器** - 对于会议，至少有一端是服务器。 <br/>**语音邮件** - 终结点由语音邮件服务应答。||
| Organizer ObjectId|String|会议组织者的用户的 Active Directory 对象 ID。 仅适用于过去 28 天的数据，并且仅对具有允许 EUII 访问的角色的用户可见。  | &bull; 用户没有查看 EUII 的权限。 <br/>&bull; 记录超过 28 天。 |
| 组织者 UPN|String|用户主体名称 (会议组织者的用户的 UPN) 。 仅适用于过去 28 天的数据，并且仅对具有允许 EUII 访问的角色的用户可见。| &bull; 用户没有查看 EUII 的权限。 <br/>&bull; 记录超过 28 天。 |
| 组织者 Sip Uri|String|会话初始协议 (会议组织者的用户的 SIP) URI。 仅适用于过去 28 天的数据，并且仅对具有允许 EUII 访问的角色的用户可见。| &bull;仅为Skype for Business终结点填充。 <br/>&bull; 用户没有查看 EUII 的权限。 <br/>&bull; 记录超过 28 天。|
|**Devices**||||
| 第一个捕获设备外形规格|枚举字符串|音频捕获设备的外形规格 (麦克风在第一终结点上) 。 | &bull; 终结点未报告。 |
| 第二个捕获设备外形规格|枚举字符串|音频捕获设备的外形规格 (麦克风在第一终结点上) 。 | &bull; 终结点未报告。 |
| 第一个呈现设备外形规格|枚举字符串|音频捕获设备的外形规格 (扬声器在第一终结点) 。 | &bull; 终结点未报告。 |
| 第二个呈现设备外形规格|枚举字符串|音频捕获设备的外形规格 (扬声器在第一终结点) 。 | &bull; 终结点未报告。 |
|**Video**||||
| 第一个视频持续时间秒 |范围（秒）| 第一终结点的视频流的持续时间，以秒为单位，显示为范围。 <br/>**示例值：** 254：[1000 - 1500] | &bull; 终结点未报告。 |
| 第二个视频持续时间秒 |范围（秒）| 第二终结点的视频流的持续时间，以秒为单位，显示为范围。 <br/>**示例值：** 254：[1000 - 1500] | &bull; 终结点未报告。 |
|**PSTN**||||
|第一个 PSTN 国家/地区区域|String|如果 FirstIsCaller 为 true，则第一个 PSTN 国家/地区是调用方所在的国家/地区。 如果为 false，则第二个 PSTN 国家/地区区域是调用方的国家/地区。<br/>**例子：** 我们||
|第二个 PSTN 国家/地区|String|如果 FirstIsCaller 为 false，则第二个 PSTN 国家/地区是调用方所在的国家/地区。 如果为 true，则“第一 PSTN 国家/地区”区域是调用方所在的国家/地区。<br/>**例子：** 我们||
|PSTN 中继 FQDN|String|FQDN 是会话边界控制器 (SBC) 的 FQDN)  (完全限定的域名。<br/>**示例：** sbcgw.contoso.com||
|PSTN 运营商名称|String|经监管机构授权运营电信系统的公司。<br/>**例子：** 柯 尔 特|直接路由没有运营商。 只有通话套餐才有运营商。|
|PSTN 呼叫类型|String|此字符串将服务类型和调用类型组合在一起。<br/><br/>服务类型：<br/>user -> 通话套餐<br/>byot -> 直接路由<br/>conf ->音频会议<br/>ucap -> 语音应用<br/>紧急 ->紧急号码<br/><br/>呼叫类型：<br/>在 -> 入站呼叫<br/>Out ->出站呼叫<br/>Out_transfer ->出站呼叫转接到第三人称<br/>Out_forward ->出站呼叫转接到第三人称<br/>Out_conf ->临时 PSTN 参与者的出站呼叫<br/><br/>**例子：** ByotIn||
|PSTN 连接类型|String|PSTN 连接类型包括直接路由、通话套餐或音频会议。 目前，只有直接路由在呼叫质量仪表板中可用， (CQD) 。<br/>**例子：** 直接路由||
|PSTN 最终 SIP 代码短语|String|对应于 SIP 响应代码的原因短语和Microsoft响应代码。<br/>**例子：** 再见||
|PSTN 呼叫结束子原因|Int|从 Microsoft 组件发送的响应代码，指示发生的特定操作。<br/>**示例：** 540000||
|PSTN 事件类型|String|提供遥测的事件类型。<br/>**例子：** 结束||
|PSTN 事件信息时间|日期|出站呼叫从Microsoft网络启动或入站呼叫到达Microsoft网络的时间（UTC 格式）。<br/>**示例：** 2020-02-06 20：57：53.1750000||
|PSTN MP 位置|String|处于非旁路模式时，媒体处理器位置将显示媒体路径。<br/>**例子：** USWE||
|PSTN 中继呼叫 ID|String|PSTN SIP 中继与 SIP 代理之间的 SIP 呼叫 ID。 直接路由客户可以使用此值来对 PSTN 呼叫方案进行故障排除，方法是将中继呼叫 ID 与正在使用的会话边界控制器或媒体网关的日志交叉引用。||
|PSTN 中继用户代理|String|PSTN SIP 中继的会话边界控制器或媒体网关的制造商和型号信息。<br/>**例子：** Mediant 1000/v.7.20A.258.750 ||
|PSTN 呼叫结束原因|Int|三位数整数响应代码显示调用的最终状态。 <br/> 有关 SIP 解释的详细信息，请参阅 [SIP 响应代码列表](https://www.wikipedia.org/wiki/List_of_SIP_response_codes)。 <br/>**示例：** 404||
|**语音应用 (预览版)**||对于此类别，有关详细信息，请参阅 [自动助理&呼叫队列历史记录报告](aa-cq-cqd-historical-reports.md) 。) ||
|自动助理标识|String|附加到自动助理的资源帐户的名称。|&bull; 用户没有查看 EUII 的权限。 <br/>&bull; 记录超过 28 天。|
|自动助理链索引|整型| 呼叫中自动助理的顺序。||
|自动助理链开始时间|String|自动助理呼叫开始时间和日期。||
|自动助理链持续时间秒|整型| 自动助理中呼叫的持续时间，以秒为单位。||
|自动助理调用方操作计数|整型|呼叫期间调用方在自动助理中选择的操作计数。||
|自动助理呼叫流|String| 封装自动助理调用的不同状态。||
|自动助理转移操作|枚举| 呼叫转移目标类型。||
|自动助理呼叫结果|枚举| 使用自动助理的最终呼叫结果。 ||
|自动助理目录搜索方法|枚举|使用的最后一个通讯簿搜索方法。||
|自动助理计数|整型| 呼叫中涉及的自动助理数。||
|呼叫队列标识|String|附加到呼叫队列的资源帐户的名称。 |&bull; 用户没有查看 EUII 的权限。 <br/>&bull; 记录超过 28 天。|
|呼叫队列为会议模式|Boolean|如果为 True，则呼叫队列配置为使用会议模式，否则呼叫队列配置为使用传输模式。 ||
|呼叫队列代理计数|整型|队列中配置的代理数。 ||
|呼叫队列代理选择加入计数|整型|已选择加入队列的已配置代理数。 ||
|呼叫队列目标类型|枚举|呼叫重定向目标类型。 ||
|呼叫队列调用结果|枚举|呼叫队列呼叫最终状态。 ||
|调用队列最终状态操作|枚举|呼叫队列最终操作。 ||
|呼叫队列超时时间|整型|为呼叫队列配置的超时值。 ||
|从呼叫队列标识转移|String|附加到转移呼叫的呼叫队列的资源帐户的名称。 |&bull; 用户没有查看 EUII 的权限。 <br/>&bull; 记录超过 28 天。|
|是否涉及自动助理|Boolean| 如果为 True，则自动助理参与了给定的呼叫或流。||
|是否涉及呼叫队列|Boolean|如果为 True，则给定的呼叫或流中涉及呼叫队列。 ||
|**会议**||||
|计划源应用 ID|String |预订会议的第一方或第三方计划客户端的 AppID。|计划客户端未通过其遥测提供此参数。|
|**常见**||||
| 第一个 ACS 资源 ID |String |与第一个终结点关联的 Azure 通信服务的不可变资源标识符。 <br/> **示例：** 00000000-0000-0000-0000-000000000000 | 终结点未使用 Azure Communication Services API|
| 第二个 ACS 资源 ID |String |与第二终结点关联的 Azure 通信服务的不可变资源标识符。 <br/> **示例：** 00000000-0000-0000-0000-000000000000 | 终结点未使用 Azure Communication Services API|
|**Datapair**||||
| Network Connection Detail Pair  | 枚举对 <br/>**可能的值：** <br/> wifi : wifi <br/> wifi : 有线 <br/> 有线 : wifi <br/> 有线 : 有线 <br/> MobileBB : MobileBB <br/> MobileBB : 其他 <br/> MobileBB : 隧道 <br/> MobileBB : wifi <br/> MobileBB : 有线 <br/> 其他 : 其他 <br/> 其他 : wifi <br/> 其他 : 有线 <br/> 隧道 : 隧道 <br/> 隧道 : wifi <br/> 隧道 : 有线 <br/> : MobileBB <br/> : 其他 <br/> : 隧道 <br/> : wifi <br/> : 有线 <br/> :  | 表示第一和第二终结点的网络连接详情的成对值。  | &bull; 终结点网络连接类型未知。 当无法建立通话时可能会出现这种情况。   |
| User Agent Category Pair  | 枚举对  | 表示第一和第二终结点的用户代理类别的成对值。 <br/> **示例值：** AV-MCU ： OC  | &bull; 终结点用户代理不是已知类型  |
| Is Server Pair  | 枚举对 <br/>**可能的值：** 客户端：客户端 <br/> 客户端： 服务器 <br/> 服务器： 服务器  | 表示第一和第二终结点是客户端还是服务器的成对值。  | 没有空值   |
| Connectivity Ice Pair  | 枚举对 <br/>**可能的值：** <br/> 直接 : 直接 <br/> 直接 : 失败 <br/> 直接 : HTTP <br/> 失败 : 失败 <br/> 失败 : 中继 <br/> HTTP : 中继 <br/> : <br/> : 直接 <br/> : 失败 <br/> : HTTP <br/> : 中继 | 表示每个终结点使用的 ICE 连接类型的成对值。   | &bull; 终结点使用的 ICE 连接未知或未报告   |
| OS Pair  | 枚举对  | 表示第一和第二终结点的操作系统名称和版本的成对值。 <br/> **示例值：** Windows 10：Windows 10  | &bull; 无法分析或终结点未报告 OS 名称  |
| Tenant Id Pair  | 枚举对  | 表示第一和第二终结点的租户 ID 的成对值。 <br/> **示例值：** 00000000 — 0000 - 0000 - 0000 — 00000000000 ： 000000000 — 0000 - 0000 - 0000 — 000000000000  |  &bull; 无法确定租户标识符。 当终结点登录到了本地 Skype for Business Server 部署时可能会出现此情况。  |
| Building Name Pair  | 枚举对  | 表示第一和第二终结点的建筑物名称的成对值。  | &bull; 无法确定终结点的生成名称。 这可能是因为终结点位于企业网络外部，或正在从没有子网映射的站点访问网络。 <br/> **示例值：** 主建筑：分支站点建筑 |
| Inside Corp Pair  | 枚举对 <br/>**可能的值：** <br/> 内部 : 内部 <br/> 内部 : 外部 <br/> 外部 : 外部 | 根据子网映射，显示终结点位于企业网络内部还是外部的成对值。   |   |
|**应用场景**||||
| Scenario Pair  | 枚举对  | 显示终结点位于企业网络内部还是外部（根据子网映射确定）以及网络连接详情的成对值。 <br/> **注意：** 对由“--”分隔。 <br/> **示例值：** Client-Inside--Client-Inside-wifi  | &bull; 任一终结点或两个终结点的网络连接类型未知。  |


## <a name="measurements"></a>测量

许多度量值也可以用作筛选器。 下表列出了 CQD 中当前可用的度量值，按Editor Power Query中列出的顺序显示

|衡量指标名称|单位|说明|
|:---|:---|:---|
|Total Stream Count |流的数量 |无论介质类型如何，都对媒体流进行编号，包括可能没有媒体类型的可靠性/诊断流。 |
| CDR 可用流计数总计 | 流的数量 |具有可用可靠性/诊断信息的媒体流数。 请参阅 [Skype for Business Server 中的呼叫详细信息记录 (CDR) ](/skypeforbusiness/manage/health-and-monitoring/call-detail-recording-cdr) |
|Total Media Failed Stream Count |流的数量 |媒体路径未能建立或未正常终止的流的数量。 |
|Total Call Setup Failed Stream Count |流的数量 |呼叫之初无法在终结点之间建立媒体路径的流的数量。 |
|Total Call Dropped Stream Count |流的数量 |媒体路径未正常终止的流的数量。 |
|Total Media Succeeded Stream Count |流的数量 |媒体路径成功建立并正常终止的流的数量。 |
|Total Call Setup Succeeded Stream Count |流的数量 |呼叫之初在终结点之间成功建立媒体路径的流的数量。|
|Total Call Setup Failure Percentage |百分比 |呼叫之初无法在终结点之间建立媒体路径的所有流的百分比。 |
|Total Call Dropped Failure Percentage |百分比 |媒体路径未正常终止的成功建立流的百分比。| 
|Total Answer Seizure Ratio |比率 |持续时间低于 5 秒钟的通话占通话总数的比率。 |
|Total Short Call Percentage |百分比 |总调用时间小于 1 分钟的百分比。 |
|Total Media Failure Percentage |百分比 |媒体路径未能建立或未正常终止的所有流的百分比。 |
|总音频流持续时间 (分钟)  |分钟 |所选时间范围内的总音频流持续时间（分钟）。 |
|Media Failed Due To Firewall DPI Stream Count |流的数量 |由于深度包检测不允许 Skype for Business 流量导致网络设备阻止访问进而未能建立的流的数量。 这些故障通常表示代理、防火墙或其他网络安全设备未正确配置为访问 Microsoft 365 或 Office 365 中的Skype for Business使用的 IP 地址和端口。 |
|Firewall DPI Media Failure Percentage |百分比 |由于深度包检测不允许 Skype for Business 流量导致网络设备阻止访问进而未能建立的流的百分比。 这些故障通常表示代理、防火墙或其他网络安全设备未正确配置为访问 Microsoft 365 或 Office 365 中的Skype for Business使用的 IP 地址和端口。 |
|Media Failed Due To Firewall IP Blocked Stream Count |流的数量 |由于网络设备阻止访问 Skype for Business 服务器而未能建立的流的数量。 这些故障通常表示代理、防火墙或其他网络安全设备未正确配置为访问 Microsoft 365 或 Office 365 中的Skype for Business使用的 IP 地址和端口。 |
|Firewall IP Blocked Media Failure Percentage |百分比 |由于网络设备阻止了对Skype for Business服务器的访问而未能建立的流的百分比。 这些故障通常表示代理、防火墙或其他网络安全设备未正确配置为访问 Microsoft 365 或 Office 365 中Skype for Business使用的 IP 地址和端口。 |
| 媒体因其他流计数而失败|流的数量| 由于不确定/未分类的原因，无法在终结点之间建立媒体路径的流数。|
| 其他媒体故障百分比|百分比| 由于不确定/未分类的原因，无法在终结点之间建立媒体路径的流百分比。 |
| CDR 可用调用计数总数|流的数量|具有可用可靠性/诊断信息的媒体流的总数。 此度量值的误差高达 0.2%。 有关详细信息，请参阅下面的说明。|
| 媒体失败调用计数总数|流的数量|无法在终结点之间建立媒体路径的流数。 此度量值的误差高达 0.2%。 有关详细信息，请参阅下面的说明。|
|Audio Stream Count |流的数量 |音频流的数量。 |
|Audio Poor Stream Count |流的数量 |根据此处列出的网络指标分类为差的音频流数： [通话质量仪表板中的流分类](stream-classification-in-call-quality-dashboard.md)。 |
 |Audio Good Stream Count |流的数量 |根据此处列出的网络指标分类为良好的音频流数： [通话质量仪表板中的流分类](stream-classification-in-call-quality-dashboard.md)。 |
|Audio Unclassified Stream Count |流的数量 |根据以下列出的网络指标，没有足够的数据被分类为好或差的音频流数： [通话质量仪表板中的流分类](stream-classification-in-call-quality-dashboard.md)。 “差百分比”计算中省略未分类的流。 |
|Audio Poor Percentage |百分比 |根据此处列出的网络指标，分类为差的已分类音频流的百分比： [通话质量仪表板中的流分类](stream-classification-in-call-quality-dashboard.md)。 |
|Audio OnePercent PacketLoss Count |流的数量 |丢包率大于 1% 的音频流的数量。 |
|Audio OnePercent PacketLoss Percentage |百分比 |丢包率大于 1% 的所有音频流的百分比。 |
|Audio Poor Due To Jitter Count |流的数量 |抖动指标超过此处列出的阈值的音频流数： [通话质量仪表板中的流分类](stream-classification-in-call-quality-dashboard.md)。 |
|Audio Poor Due To PacketLoss Count |流的数量 |数据包丢失指标超过此处列出的阈值的音频流数： [通话质量仪表板中的流分类](stream-classification-in-call-quality-dashboard.md) |
|Audio Poor Due To Degradation Count |流的数量 |降级指标超过此处列出的阈值的音频流数： [通话质量仪表板中的流分类](stream-classification-in-call-quality-dashboard.md)。 |
|Audio Poor Due To RoundTrip Count |流的数量 |往返次数超过此处列出的阈值的音频流数： [通话质量仪表板中的流分类](stream-classification-in-call-quality-dashboard.md)。 |
|Audio Poor Due To ConcealedRatio Count |流的数量 |隐藏比率超过此处列出的阈值的音频流数： [通话质量仪表板中的流分类](stream-classification-in-call-quality-dashboard.md)。 |
|Audio SLA Good Call Count |通话的数量 |Microsoft[产品和联机服务的](https://aka.ms/voicequalitysla)Skype for Business语音质量 SLA (批量许可范围内的音频呼叫数) 归类为满足网络性能目标。 |
|Audio SLA Poor Call Count |通话的数量 |Microsoft[产品和联机服务的](https://aka.ms/voicequalitysla)Skype for Business语音质量 SLA (批量许可范围内的音频呼叫数) 分类为不符合网络性能目标。 |
|Audio SLA Call Count |通话的数量 |Microsoft [产品和联机服务](https://aka.ms/voicequalitysla)) 的 Skype for Business 语音质量 SLA (批量许可范围内的音频呼叫数。 |
|Audio SLA Good Call Percentage |百分比 |Skype for Business 语音质量 SLA（[Microsoft 产品和在线服务的批量许可](https://aka.ms/voicequalitysla)）范围内被分类为满足网络性能目标的音频通话的百分比。 |
|Audio Good Call Stream Count |流的数量 |根据下面列出的网络指标，呼叫 (呼叫) 中的音频流未分类为差的音频流数： [通话质量仪表板中的流分类](stream-classification-in-call-quality-dashboard.md)。 |
|Audio Poor Call Stream Count |流的数量 |根据此处列出的网络指标，呼叫 (通话) 中至少有一个音频流被分类为差的音频流数： [通话质量仪表板中的流分类](stream-classification-in-call-quality-dashboard.md)。 |
|Audio Unclassified Call Stream Count |流的数量 |由于缺少网络指标，无法对呼叫 (呼叫) 中的音频流进行分类的音频流数。 |
|音频差呼叫级别百分比 |百分比 |根据下面列出的网络指标，呼叫 (通话) 中至少有一个音频流被分类为差的所有音频流的百分比： [通话质量仪表板中的流分类](stream-classification-in-call-quality-dashboard.md)。 |
| 音频呼叫计数 | 数字 |涉及音频的呼叫数。 此度量值的误差高达 0.2%。 有关详细信息，请参阅下面的说明。|
| 音频差呼叫计数|数字  |涉及音频分类为差的呼叫数。 此度量值的误差高达 0.2%。 有关详细信息，请参阅下面的说明。|
| 音频正常呼叫计数 |通话的数量|涉及分类为良好音频的呼叫数。 此度量值的误差高达 0.2%。 有关详细信息，请参阅下面的说明。|
| 音频未分类呼叫计数 |通话的数量|涉及无法分类为“好”或“差”的音频的呼叫数。 “不良调用百分比”计算中省略未分类的调用。 此度量值的误差高达 0.2%。 有关详细信息，请参阅下面的说明。|
| Audio Poor Call Percentage |调用百分比|涉及分类为差音频的已分类呼叫的百分比。 此度量值的误差高达 0.2%。 有关详细信息，请参阅下面的说明。|
|AppSharing Stream Count |流的数量 |基于 RDP 的应用程序共享流的数目。 |
|AppSharing Poor Due To SpoiledTilePercentTotal Count |流的数量 |损坏的磁贴百分比总指标超过此处列出的阈值的应用程序共享流数： [通话质量仪表板中的流分类](stream-classification-in-call-quality-dashboard.md)。 |
|AppSharing Poor Due To RelativeOneWayAverage Count |流的数量 |损坏的磁贴百分比总指标超过此处列出的阈值的应用程序共享流数： [通话质量仪表板中的流分类](stream-classification-in-call-quality-dashboard.md)。 |
|AppSharing Poor Due To RDPTileProcessingLatencyAverage Count |流的数量 |RDP 磁贴处理延迟平均值超过此处列出的阈值的应用程序共享流数： [通话质量仪表板中的流分类](stream-classification-in-call-quality-dashboard.md)。 |
|AppSharing Poor Stream Count |流的数量 |根据此处列出的网络指标分类为差的应用程序共享流的数量： [通话质量仪表板中的流分类](stream-classification-in-call-quality-dashboard.md)。 |
|AppSharing Good Stream Count |流的数量 |根据此处列出的网络指标，分类为良好的应用程序共享流的数量： [通话质量仪表板中的流分类](stream-classification-in-call-quality-dashboard.md)。 |
|AppSharing Unclassified Stream Count |流的数量 |根据以下列出的网络指标，没有足够的数据被分类为好或差的应用程序共享流的数量： [通话质量仪表板中的流分类](stream-classification-in-call-quality-dashboard.md)。 “差百分比”计算中省略未分类的流。 |
|AppSharing Poor Percentage |百分比 |根据此处列出的网络指标，分类为差的分类应用程序共享流的百分比： [通话质量仪表板中的流分类](stream-classification-in-call-quality-dashboard.md)。 |
|Video Stream Count |流的数量 |视频流的数量。 |
|Video Poor Due To VideoPostFecplr Count |流的数量 |视频后 Fec plr 超出此处列出的阈值的视频流数： [通话质量仪表板中的流分类](stream-classification-in-call-quality-dashboard.md)。 |
|Video Poor Due To VideoLocalFrameLossPercentageAvg Count |流的数量 |视频本地帧丢失百分比平均值超过此处列出的阈值的视频流数： [通话质量仪表板中的流分类](stream-classification-in-call-quality-dashboard.md)。 |
|Video Poor Due To VideoFrameRateAvg Count |流的数量 |视频帧速率平均值超过此处列出的阈值的视频流数： [通话质量仪表板中的流分类](stream-classification-in-call-quality-dashboard.md)。 |
|由于冻结计数，视频差 |流的数量 | 视频冻结指标超过此处列出的阈值的主要视频流的数量。 [通话质量仪表板中的流分类](stream-classification-in-call-quality-dashboard.md)。 此字段特定于Microsoft Teams |
|Video Poor Stream Count |流的数量 |根据 [通话质量仪表板中的](stream-classification-in-call-quality-dashboard.md)流分类中列出的网络指标，分类为差的视频流的数量。 |
|Video Good Stream Count |流的数量 |根据此处列出的网络指标分类为良好视频流的数量： [通话质量仪表板中的流分类](stream-classification-in-call-quality-dashboard.md)。 |
|Video Unclassified Stream Count |流的数量 |根据以下列出的网络指标，没有足够的数据被分类为好或差的视频流的数量： [通话质量仪表板中的流分类](stream-classification-in-call-quality-dashboard.md)。 “差百分比”计算中省略未分类的流。 |
|Video Poor Percentage|百分比 |根据 [通话质量仪表板中的](stream-classification-in-call-quality-dashboard.md)流分类中列出的网络指标，分类为差的分类视频流的百分比。 |
|由于冻结导致视频差百分比|百分比 | 根据 [通话质量仪表板](stream-classification-in-call-quality-dashboard.md)中的流分类中列出的“视频差因冻结”指标分类，被分类为差的主要视频流的百分比。 此字段特定于Microsoft Teams |
|VBSS Stream Count |流的数量 |基于视频的屏幕共享流的数量。 |
|VBSS Poor Due To VideoPostFecplr Count |流的数量 |视频后 Fec plr 超出此处列出的阈值的基于视频的屏幕共享流的数量： [通话质量仪表板中的流分类](stream-classification-in-call-quality-dashboard.md)。 |
|VBSS Poor Due To VideoLocalFrameLossPercentageAvg Count |流的数量 |视频本地帧丢失百分比平均值超过此处列出的阈值的基于视频的屏幕共享流的数量： [通话质量仪表板中的流分类](stream-classification-in-call-quality-dashboard.md)。 |
|VBSS 差由于 VideoFrameRateAvg 计数 |流的数量 |视频帧速率平均值超过此处列出的阈值的基于视频的屏幕共享流的数量： [通话质量仪表板中的流分类](stream-classification-in-call-quality-dashboard.md)。 |
|VBSS Poor Stream Count |流的数量 |基于视频的屏幕共享流的数量，根据此处列出的网络指标分类为差： [通话质量仪表板中的流分类](stream-classification-in-call-quality-dashboard.md)。 |
|VBSS Good Stream Count |流的数量 |基于视频的屏幕共享流的数量根据此处列出的网络指标分类为良好： [通话质量仪表板中的流分类](stream-classification-in-call-quality-dashboard.md)。 |
|VBSS Unclassified Stream Count |流的数量 |基于视频的屏幕共享流的数量，这些流没有足够的数据根据此处列出的网络指标被分类为好或差： [通话质量仪表板中的流分类](stream-classification-in-call-quality-dashboard.md)。 “差百分比”计算中省略未分类的流。|
|VBSS Poor Percentage |百分比 |根据下面列出的网络指标分类的基于视频的屏幕共享流的百分比： [通话质量仪表板中的流分类](stream-classification-in-call-quality-dashboard.md)。 |
|Avg Call Duration |秒 |流的平均持续时间，以秒为单位。 |
|First Feedback Rating Avg |用户评级 (1-5) |Average rating of streams reported by the user using the first endpoint. Calls are rated from 1-5 and the rating is applied to all streams of the call. |
|Second Feedback Rating Avg |用户评级 (1-5) |Average rating of streams reported by the user using the second endpoint. Calls are rated from 1-5 and the rating is applied to all streams of the call. |
|First Feedback Rating Count |被评级的流的数量 |Number of streams rated by the user using the first endpoint. Calls are rated from 1-5 and the rating is applied to all streams of the call. |
|Second Feedback Rating Count |被评级的流的数量 |Number of streams rated by the user using the second endpoint. Calls are rated from 1-5 and the rating is applied to all streams of the call. |
|First Feedback Rating Poor Count |被评级的流的数量 |Number of streams rated by the user using the first endpoint as either 1 or 2. Calls are rated from 1-5 and the rating is applied to all streams of the call. |
|Second Feedback Rating Poor Count |被评级的流的数量 |Number of streams rated by the user using the second endpoint as either 1 or 2. Calls are rated from 1-5 and the rating is applied to all streams of the call. |
|First Feedback Rating Poor Percentage |被评级的流的数量 |Percentage of all rated streams that were rated by the user using the first endpoint as either 1 or 2. Calls are rated from 1-5 and the rating is applied to all streams of the call. |
|Second Feedback Rating Poor Percentage |被评级的流的数量 |Percentage of all rated streams that were rated by the user using the second endpoint as either 1 or 2. Calls are rated from 1-5 and the rating is applied to all streams of the call. |
|First Feedback Token Audio Issue Count |被评级流的数量 |被使用第一终结点的用户指出存在音频问题的流的数量。 |
|Second Feedback Token Audio Issue Count |被评级流的数量 |被使用第二终结点的用户指出存在音频问题的流的数量。 |
|First Feedback Token Video Issue Count |被评级的流的数量 |使用第一终结点的用户指示视频出现问题的流数。 |
|Second Feedback Token Video Issue Count |被评级的流的数量 |使用第二终结点的用户指示视频出现问题的流数。 |
|Avg First Echo Percent Mic In |百分比 |在流持续期间，第一终结点在消除回声之前通过捕获设备或麦克风设备在音频中检测到回声的持续时间的平均百分比。 |
|Avg Second Echo Percent Mic In |百分比 |在流持续期间，第二终结点在消除回声之前通过捕获设备或麦克风设备在音频中检测到回声的持续时间的平均百分比。 |
|Avg First Echo Percent Send |百分比 |在流持续期间，第一终结点在消除回声之后通过捕获设备或麦克风设备在音频中检测到回声的持续时间的平均百分比。 |
|Avg Second Echo Percent Send |百分比 |在流持续期间，第二终结点在消除回声之后通过捕获设备或麦克风设备在音频中检测到回声的持续时间的平均百分比。 |
| Avg First Initial Signal Level RMS| 范围 (分贝)  |第一终结点调用前 30 秒接收信号的均方根 (RMS) 平均值。  有关详细信息[，请参阅 2.2.1.28.1 子元素](/openspecs/office_protocols/ms-qoe/3c78f383-73fe-49f6-89cb-614e7aa8b2e7)|
| Avg Second Initial Signal Level RMS|范围 (分贝)  |第二终结点调用前 30 秒接收信号的均方根 (RMS) 平均值。|
| Avg First RxAGC Signal Level|范围 (分贝)   |在第一个入站音频流自动增益控制处接收的平均信号级别。 |
| Avg Second RxAGC Signal Level|范围 (分贝)  |第二个入站音频流的自动增益控制处接收的平均信号级别。|
| Avg First RxAGC Noise Level|范围 (分贝)  |在第一个入站音频流自动增益控制处接收的平均噪音级别。|
| Avg Second RxAGC Noise Level|范围 (分贝)  |第二个入站音频流的自动增益控制处接收的平均噪音级别。|
| Avg First Render 环回信号级别|范围 (分贝)  | ) 应用任何设备卸载效果后，第一个扬声器环回信号 (的平均值。|
| Avg Second Render 环回信号级别|范围 (分贝)  | ) 应用任何设备卸载效果后，第二个扬声器环回信号 (的平均值。|
|Avg First Audio Send Signal Level |分贝 |对于被分类为单声道语音或左声道立体声语音的音频，第一终结点发送的音频的平均能量水平。 |
|Avg Second Audio Send Signal Level |分贝 |对于被分类为单声道语音或左声道立体声语音的音频，第二终结点发送的音频的平均能量水平。 |
|Avg First Audio Received Signal Level |分贝 |对于被分类为单声道语音或左声道立体声语音的音频，第一终结点接收的音频的平均能量水平。 |
|Avg Second Audio Received Signal Level |分贝 |对于被分类为单声道语音或左声道立体声语音的音频，第二终结点接收的音频的平均能量水平。 |
|Avg First Audio Send Noise Level |分贝 |对于被分类为单声道噪音或左声道立体声噪音的音频，第一终结点发送的音频的平均能量水平。 |
|Avg Second Audio Send Noise Level |分贝 |对于被分类为单声道噪音或左声道立体声噪音的音频，第二终结点发送的音频的平均能量水平。 |
|Avg First Audio Received Noise Level |分贝 |对于被分类为单声道噪音或左声道立体声噪音的音频，第一终结点接收的音频的平均能量水平。 |
|Avg Second Audio Received Noise Level |分贝 |对于被分类为单声道噪音或左声道立体声噪音的音频，第二终结点接收的音频的平均能量水平。 |
|First Audio Echo BAD_TIMESTAMP Count |流的数量 |具有以下特征的流的数量：第一终结点的差质量设备时间戳导致了回声，限制了已发送音频中的回声消除。 |
|First Audio Echo POSTAEC_ECHO Count |流的数量 |具有以下特征的流的数量：第一终结点在已发送音频进行回声消除后检测到了高回声。 |
|First Audio Echo EVENT_ANLP Count |流的数量 |具有以下特征的流的数量：第一终结点在捕获的音频中检测到噪音，限制了已发送音频中的回声消除。 |
|First Audio Echo EVENT_DNLP Count |流的数量 |具有以下特征的流的数量：第一终结点在捕获的音频中检测到噪音，限制了已发送音频中的回声消除。 |
|First Audio Echo MIC_CLIPPING Count |流的数量 |具有以下特征的流的数量：第一终结点在捕获的音频中检测到削波，限制了已发送音频中的回声消除。 |
|First Audio Echo BAD_STATE Count |流的数量 |具有以下特征的流的数量：第一终结点检测到内部状态问题，限制了已发送音频中的回声消除。 |
|Second Audio Echo BAD_TIMESTAMP Count |流的数量 |具有以下特征的流的数量：第二终结点的差质量设备时间戳导致了回声，限制了已发送音频中的回声消除。 |
|Second Audio Echo POSTAEC_ECHO Count |流的数量 |具有以下特征的流的数量：第二终结点在已发送音频进行回声消除后检测到了高回声。 |
|Second Audio Echo EVENT_ANLP Count |流的数量 |具有以下特征的流的数量：第二终结点在捕获的音频中检测到噪音，限制了已发送音频中的回声消除。 |
|Second Audio Echo EVENT_DNLP Count |流的数量 |具有以下特征的流的数量：第二终结点在捕获的音频中检测到噪音，限制了已发送音频中的回声消除。 |
|Second Audio Echo MIC_CLIPPING Count |流的数量 |具有以下特征的流的数量：第二终结点在捕获的音频中检测到削波，限制了已发送音频中的回声消除。 |
|Second Audio Echo BAD_STATE Count |流的数量 |具有以下特征的流的数量：第二终结点检测到内部状态问题，限制了已发送音频中的回声消除。 |
|Avg Audio Degradation |平均意见得分 (0-5) |关于流降级的网络平均意见得分的平均值。 表示网络丢失和抖动对接收音频质量的影响程度。 |
|Avg Jitter |毫秒 |流的平均网络抖动，以毫秒为单位。 这是通用网络有效负载中报告的到达间抖动，针对所有流类型进行报告。 |
|Avg Jitter Max |毫秒 |流的最大网络抖动值，以毫秒为单位。 这是通用网络有效负载中报告的到达间抖动，针对所有流类型进行报告。 |
|Avg Packet Loss Rate |比率 |以 5 秒钟时间间隔计算到的流的平均丢包百分比的平均值。 0.1 表示 10% 的数据包丢失。 |
|Avg Packet Loss Rate Max |比率 |以 5 秒钟时间间隔计算到的流的最大丢包百分比的平均值。 0.1 表示 10% 的数据包丢失。 |
| Avg Send Listen MOS |数字 |从用户发送的音频流的宽带收听质量平均意见分数 (MOS-LQ) 预测平均值。 <br/>请参阅 [Lync 监视报告解码器](https://gallery.technet.microsoft.com/Lync-Reports-Decoder-001ba287)中的“平均发送 MOS”|
|Avg Overall Avg Network MOS |平均意见得分 (0-5) |Average or average network Mean Opinion Score for streams. Represents the average predicted quality of received audio factoring in network loss, jitter, and codec. |
|Avg Ratio Concealed Samples |比率 |Average of average ratio of the number of audio frames with samples generated by packet loss concealment to the total number of audio frames for streams. 0.1 indicates 10% of frames contained concealed samples. |
| 平均隐藏比率最大值| 比率 |包含数据包丢失隐藏生成的样本的音频帧数与流音频帧总数的最大比率的平均值。 0.1 表示 10% 的帧包含隐藏样本。|
|Avg Ratio Stretched Samples |比率 |Average of average ratio of the number of audio frames with samples that have been stretched to compensate for jitter or loss to the total number of audio frames for streams. 0.1 indicates 10% audio frames contained stretched samples. |
| 平均愈合器数据包下降比率|范围 (比率) |愈合程序丢弃的音频数据包与愈合程序接收的音频数据包总数的平均比率。 |
| 平均愈合器 FEC 数据包使用比率|范围 (比率) |已用 FEC 数据包与接收的 FEC 数据包总数的平均比率。|
|Avg Round Trip |毫秒 |计算的平均网络传播往返时间的平均值，根据 RFC3550 以毫秒为单位指定。 |
|Avg Round Trip Max |毫秒 |计算的最大网络传播往返时间的平均值，根据 RFC3550 以毫秒为单位指定。 |
 平均数据包利用率|数据包数|会话中每秒发送的Real-Time传输协议 (RTP) 数据包数。|
|Avg Network Jitter |毫秒 |   会话期间超过 20 秒时段计算的网络抖动平均值。 此指标包含在 QoE 的音频有效负载中。 音频以外的流类型不会报告此度量值。 |
| 平均网络抖动最大值|毫秒 |会话期间超过 20 秒时段计算的最大网络抖动的平均值（以毫秒为单位）。 此指标包含在 QoE 的音频有效负载中。 音频以外的流类型不会报告此度量值。 |
| 平均网络抖动最小值|毫秒|在流会话期间，在 20 秒时段内计算的最小网络抖动值的平均值（以毫秒为单位）。 此指标包含在 QoE 的音频有效负载中。 音频以外的流类型不会报告此度量值。|
| 平均抖动缓冲区大小|毫秒|会话期间抖动缓冲区的平均大小。 此指标包含在 QoE 的音频有效负载中。 音频以外的流类型不会报告此度量值。|
| 平均抖动缓冲区大小最大值|毫秒|会话期间抖动缓冲区的最大大小。 此指标包含在 QoE 的音频有效负载中。 音频以外的流类型不会报告此度量值。|
| 平均抖动缓冲区大小最小值|毫秒|会话期间抖动缓冲区的最小大小。 此指标包含在 QoE 的音频有效负载中。 音频以外的流类型不会报告此度量值。|
| Avg Relative OneWay |毫秒|对等方的平均计算相对单向延迟。 |
| 平均相对单向间隙出现次数|毫秒|对等方相对单向延迟中间隔的平均实例数。|
| 平均相对单向间隙密度|毫秒|对等方相对单向延迟中间隔的平均密度。|
| 平均相对单向间隙持续时间|数字 (毫秒) |对等方相对单向延迟的平均间隔持续时间。|
|Avg Audio Post FECPLR |比率 |应用于所有音频流和流编解码器的聚合 FEC 后的数据包丢失率平均值。 |
|Avg Video Post FECPLR |比率 |应用 FEC 后，跨所有视频流和编解码器汇总的丢包率的平均值。 |
|Avg Video Local Frame Loss Percentage |百分比 |向用户显示的流视频帧丢失平均百分比。 其中包括从网络丢失恢复的帧。 |
|平均视频接收帧速率平均值 |帧/秒 |在会话持续期间计算到的流的所有视频流每秒接收的平均帧数的平均值。 |
|Avg Video Low Frame Rate Call Percent |百分比 |帧速率低于 7.5 帧/秒的流通话时间的平均百分比。 |
|Avg Video Packet Loss Rate |比率 |在流会话持续时间内计算的 [RFC3550](https://tools.ietf.org/html/rfc3550) 中指定的数据包丢失平均分数的平均值。 |
|Avg Video Frame Rate |帧/秒 |在会话持续期间计算到的视频流每秒接收的平均帧数。 值按范围分组表示。 |
|Avg Video Dynamic Capability Percent |毫秒 |客户端以低于此类型 CPU 预期视频处理容量的 70% 运行的流时间的平均百分比。 |
|Avg AppSharing Spoiled Tile Percent Total |毫秒 |Average of percentage of tiles which are discarded instead of being sent to a remote peer (for example, from the MCU to a viewer) for streams. Discarded tiles may be caused by bandwidth restrictions between client and server. |
|Avg AppSharing Relative OneWay |秒 |应用程序共享流的终结点之间的平均相对单向延迟（以秒为单位）。 |
|Avg AppSharing RDP Tile Processing Latency |毫秒 |在会议服务器上处理 RDP 堆栈图块的流平均延迟的平均值，以毫秒为单位。 |
|Avg First Device Capture Not 正常运行事件比率 |比率 |第一终结点检测到捕获设备无法正常工作的调用分数的平均值。 |
|Avg Second Device Capture Not 工作事件比率 |比率 |第二终结点检测到捕获设备无法正常工作的调用分数的平均值。 |
|Avg First Device Render Not 正常运行事件比率 |比率 |第一终结点检测到呈现设备无法正常工作的调用分数的平均值。 |
|Avg Second Device Render Not 正常运行事件比率 |比率 |第二终结点检测到呈现设备无法正常工作的调用分数的平均值。 |
|平均第一个麦克风故障率| 故障数|对于流的终结点麦克风) ，每 5 分钟平均第一个麦克风故障率 (故障。  |
| 平均第二麦克风故障率|故障数|对于流的终结点麦克风) ，每 5 分钟平均第二个麦克风故障率 (故障。 |
| 平均第一个说话人故障率|故障数|对于流的终结点扬声器) ，每 5 分钟平均第一个扬声器故障率 (故障。 |
| Avg Second Speaker 毛刺率|故障数|对于流的终结点扬声器) ，每 5 分钟的平均第二个扬声器故障率 (故障。 |
| 第一个用户计数|数字 | 唯一或不同的第一终结点用户数。 仅适用于过去 28 天的数据。 此度量值的误差高达 0.2%。 有关详细信息，请参阅下面的说明。|
| 第二个用户计数|数字|唯一或不同的第二终结点用户数。 仅适用于过去 28 天的数据。 此度量值的误差高达 0.2%。 有关详细信息，请参阅下面的说明。|
| Avg First Device 毛刺事件比率|百分比|第一终结点检测到播放或捕获的媒体故障或间隙导致发送或接收媒体质量不佳的调用的平均分数。|
| 平均秒设备故障事件比率|百分比|第二终结点检测到播放或捕获的媒体中的故障或间隙导致发送或接收媒体质量不佳的呼叫的平均分数。|
| 第一个设备故障事件计数| 数字 | 第一终结点检测到播放或捕获的媒体中出现严重故障或间隙，导致发送或接收媒体质量不佳的流数。|
| 第二个设备故障事件计数| 数字 | 第二终结点检测到播放或捕获的媒体中出现严重故障或间隙，导致发送或接收媒体质量不佳的流数。|
| PSTN 总尝试次数计数 | 通话的数量 | 尝试的调用总数，包括所选时间范围内的成功调用和失败的调用。 此度量值的误差高达 0.2%。 有关详细信息，请参阅下面的说明。|
|PSTN 总连接计数 | 通话的数量 | 所选时间范围内成功连接的呼叫总数。 此度量值的误差高达 0.2%。 有关详细信息，请参阅下面的说明。|
|PSTN 入站尝试计数 | 通话的数量 | 总入站尝试调用，包括所选时间范围内的成功调用和失败调用。 此度量值的误差高达 0.2%。 有关详细信息，请参阅下面的说明。|
|PSTN 入站连接计数 | 通话的数量 | 所选时间范围内成功连接的入站呼叫总数。 此度量值的误差高达 0.2%。 有关详细信息，请参阅下面的说明。|
|PSTN 出站尝试计数 | 通话的数量 | 出站尝试调用总数，包括在所选时间范围内成功调用和失败的调用。 此度量值的误差高达 0.2%。 有关详细信息，请参阅下面的说明。|
|PSTN 出站连接计数 | 调用次数 | 所选时间范围内成功连接的出站呼叫总数。 此度量值的误差高达 0.2%。 有关详细信息，请参阅下面的说明。|
|PSTN 总分钟数 | 分钟 | 所选时间范围内的总分钟使用量。|
|PSTN 入站总分钟数 | 分钟 | 所选时间范围内的总入站分钟使用量。|
|PSTN 出站总分钟数 | 分钟 | 所选时间范围内的出站分钟使用量总计。|
|PSTN 活动用户计数 | 用户数 | 当天进行至少一次连接呼叫的用户数。|
|PSTN 平均呼叫持续时间 | 分钟 | 所选时间范围内所有已连接调用的平均持续时间。 通常，1：1 PSTN 呼叫是 4 到 5 分钟。 但是，此平均值可能因公司而异。|
|PSTN 总入站并发呼叫计数 | 通话的数量 | 一分钟内同时活动的入站呼叫的最大数目。|
|PSTN 出站并发呼叫总数 | 通话的数量 | 一分钟内同时活动的出站呼叫的最大数目。|
|P50 延迟 | 毫秒 | 50% 的请求应比给定的延迟快。|
|P50 抖动 | 毫秒 | 50% 的请求速度应比给定的抖动快。|
|P50 数据包丢失率 | 百分比 | 50% 的请求应低于给定的数据包丢失率。|
|PSTN 传出后拨号延迟| 毫秒 | 从拨打号码到呼叫方或被呼叫方听到响铃时所度量的传出呼叫发生的延迟。|
|PSTN 传入后拨号延迟 | 毫秒 | 从拨打号码到呼叫方或被叫方听到响铃的时间或延迟，在传入呼叫上发生的时间或延迟。|
|PSTN NER 良好百分比 | 百分比 | NER 通过测量发送的呼叫数与传递给收件人的呼叫数来衡量网络传递呼叫的能力。<br/>NER = (应答呼叫 + 用户忙碌 + 无响铃 + 终端拒绝) /总尝试呼叫数 x 100。 此度量值的误差高达 0.2%。 有关详细信息，请参阅下面的说明。|
| 平均自动助理链持续时间秒 | 整型 | 用户在自动助理中花费的平均持续时间，以秒为单位。 |
| 平均呼叫队列持续时间秒 | 整型 | 用户等待呼叫队列由代理应答的平均持续时间，以秒为单位。 |

### <a name="notes-on-measurements"></a>有关度量的说明

#### <a name="accuracy-limitations"></a>准确性限制
某些用户和调用计数度量依赖于对数据集执行不同的 countif 操作来计算计数。 非重复 countif 操作目前存在高达 0.2% 的错误，具体取决于执行操作的行数。 对于最准确的卷，应使用流计数度量值，因为它们不依赖于这种不同的计数操作。 通过筛选来减少数据量可以减少错误，但可能不会消除不同调用和用户计数中的此错误源。 有关此限制的详细信息，请参阅 [dcount 聚合函数](/azure/data-explorer/kusto/query/dcount-aggfunction)。

## <a name="filters"></a>筛选器

许多维度和度量值也可以用作筛选器。 可以在查询中使用筛选器来消除信息，就像选择维度或度量以在查询中添加或包含信息一样。

## <a name="related-topics"></a>相关主题

[改进和监视 Teams 的通话质量](monitor-call-quality-qos.md)

[什么是 CQD？](CQD-what-is-call-quality-dashboard.md)

[ (CQD) 设置通话质量仪表板 ](turning-on-and-using-call-quality-dashboard.md)

[上传租户和生成数据](CQD-upload-tenant-building-data.md)

[CQD 数据和报表](CQD-data-and-reports.md)

[使用 CQD 管理通话和会议质量](quality-of-experience-review-guide.md)

[CQD 中的流分类](stream-classification-in-call-quality-dashboard.md)

[使用 Power BI 分析 CQD 数据](CQD-Power-BI-query-templates.md)
