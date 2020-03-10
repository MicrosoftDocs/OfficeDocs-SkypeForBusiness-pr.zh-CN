---
title: "\"呼叫质量\" 仪表板中可用的尺寸和测量"
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: siunies, mikedav, gageames
ms.topic: conceptual
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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom: Reporting
description: 获取有关 Microsoft 团队和 Skype for business Online 的通话质量仪表板使用的维度和度量的详细信息。
ms.openlocfilehash: b23b87ee7cf0f28fca59a3dee13113dcf28a141a
ms.sourcegitcommit: 33bec766519397f898518a999d358657a413924c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/10/2020
ms.locfileid: "42583072"
---
# <a name="dimensions-and-measurements-available-in-call-quality-dashboard"></a>"呼叫质量" 仪表板中可用的尺寸和测量

Microsoft 团队和 Skype for business Online 的通话质量仪表板（CQD）使你能够更好地了解通过这些服务进行通话的通话质量。 本主题提供有关通过 CQD 可见的维度和度量的详细信息。 若要了解有关 CQD 的详细信息，请参阅[打开和使用 Microsoft 团队和 Skype for Business Online 的通话质量仪表板](turning-on-and-using-call-quality-dashboard.md)。

## <a name="first-and-second-endpoint-classification"></a>第一和第二终结点分类

CQD 中的许多维度和度量值标记为第一或第二。 以下逻辑用于确定将流或通话中涉及的哪些终结点标为第一。

- 当服务器参与流或呼叫时，首先考虑服务器终结点（AV MCU、中介服务器等）。
- 客户端终结点被视为第二个终结点，除非该流位于两个服务器终结点之间。
- 如果两个终结点的类型相同，则 "第一个" 与 "第二" 是基于用户代理类别的内部排序设置的，以确保排序一致。

例如，下面的每一行表示一个流中涉及的一对用户代理：

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
> [!注释] 第一和第二分类与终结点是呼叫方还是被叫方无关。"第一是呼叫方"维度可以用来帮助确定哪个终结点是呼叫方或被叫方。

## <a name="dimensions"></a>维度

维度信息基于上载到 CQD 门户的数据的一部分。 许多维度值也可以用作筛选器。 下表按查询编辑器中列出的顺序列出了 CQD 中当前可用的维度，这些维度是用于创建报表或编辑以前定义的报表。

| 名称 | 数据类型  | 说明 | 空值的可能原因 |
|:---  |:---        |:---         |:--- |
|**Endpoint**|||
| First CPU Name  | String  | 第一终结点使用的 CPU 的名称。 <br/> **示例值：** Contoso CPU X11 @ 1.80 GHz | <br/>&bull;终结点未报告此数据   |
| Second CPU Name  | String  | 第二终结点使用的 CPU 的名称。 <br/> **示例值：** Contoso CPU X11 @ 1.80 GHz | <br/>&bull;终结点未报告此数据     |
| First CPU Number Of Cores  | 内核数量  | 第一终结点上可用的 CPU 内核数。 <br/> **示例值：** 8  | <br/>&bull;终结点未报告此数据    |
| Second CPU Number Of Cores  | 内核数量  | 第二终结点上可用的 CPU 内核数。 <br/> **示例值：** 8  | <br/>&bull;终结点未报告此数据     |
| First CPU Processor Speed  | CPU 速度，单位为 MHz  | 第一终结点使用的 CPU 的速度，单位为 MHz。 <br/> **示例值：** 1800  | <br/>&bull;终结点未报告此数据   |
| Second CPU Processor Speed  | CPU 速度，单位为 MHz  | 第二终结点使用的 CPU 的速度，单位为 MHz。 <br/> **示例值：** 1800 | <br/>&bull;终结点未报告此数据     |
| First Endpoint  | String  | 如果第一终结点为服务器或云服务客户端，此终结点报告的计算机名称。 <br/> **示例值：** MACHINENAME  | <br/>&bull;终结点未报告此数据    |
| Second Endpoint  | 字符串  | 如果第二终结点为服务器或云服务客户端，此终结点报告的计算机名称。 <br/> **示例值：** MACHINENAME | <br/>&bull;终结点未报告此数据     |
| First OS  | String  | 第一终结点报告的完整操作系统和体系结构字符串。 <br/> **示例值：** Windows 10.0.14996 SP：0.0 类型：1（工作站）套件：256： x64 WOW64： True | <br/>&bull;终结点未报告此数据 |
| Second OS  | String  | 第二终结点报告的完整操作系统和体系结构字符串。 <br/> **示例值：** Windows 10.0.14996 SP：0.0 类型：1（工作站）套件：256： x64 WOW64： True  | <br/>&bull;终结点未报告此数据 |
| First OS Filtered  | String  | 第一终结点报告的操作系统名称和主要版本及次要版本。 此字符串可以包含大于 OS 名称和版本的字符串。 <br/> **示例值：** Windows 10  | <br/>&bull;终结点未报告此信息 <br/>&bull;未收到此终结点的报告。  |
| Second OS Filtered  | 字符串  | 第二终结点报告的操作系统名称和主要版本及次要版本。 此字符串可以包含大于 OS 名称和版本的字符串。 <br/> **示例值：** Windows 10  | <br/>&bull;终结点未报告此信息 <br/>&bull;未收到此终结点的报告 |
| First OS Architecture  | String  | 第一终结点报告的硬件体系结构。 <br/> **示例值：** x64  | &bull;终结点未报告此信息 <br/>&bull;未收到此终结点的报告 <br/>&bull;无法识别体系结构的格式 |
| Second OS Architecture  | 字符串  | 第二终结点报告的硬件体系结构。 <br/> **示例值：** x64  | &bull;终结点未报告此信息 <br/>&bull;未收到此终结点的报告 <br/>&bull;无法识别体系结构的格式  |
| First Virtualization Flag  | 枚举 <br/>**可能的值：** <br/> "0x00" = None " <br/> "0x01" = HyperV <br/> "0x02" = VMWare <br/> "0x04" = Virtual PC <br/> "0x08" = Xen PC | 指示第一个终结点报告的虚拟化环境类型的标志。 | <br/>&bull;终结点未报告数据 |
| Second Virtualization Flag  | 枚举 <br/>**可能的值：** <br/> "0x00" = None " <br/> "0x01" = HyperV <br/> "0x02" = VMWare <br/> "0x04" = Virtual PC <br/> "0x08" = Xen PC | 指示第二终结点报告的虚拟化环境类型的标志。  | <br/>&bull;终结点未报告数据 |
|第一个终结点创建 |String |设备制造商，从终结点数据文件 EndpointMake 字段中读取信息。 | <br/>&bull;没有用于终结点的数据文件 |
| 第一终结点模型 |String|设备模型，从终结点数据文件 EndpointModel 字段中读取信息。| <br/>&bull;没有用于终结点的数据文件 |
| 第一终结点类型|String|设备类型，从终结点数据文件 EndpointType 字段中读取信息。| <br/>&bull;没有用于终结点的数据文件 |
| 第一个终结点标签1|String|可自定义标签，从终结点数据文件中读取信息。| <br/>&bull;没有用于终结点的数据文件 |
| 第一个终结点标签2|String|可自定义标签，从终结点数据文件中读取信息。| <br/>&bull;没有用于终结点的数据文件 |
| 第一个终结点标签3|String|可自定义标签，从终结点数据文件中读取信息。|  <br/>&bull;没有用于终结点的数据文件|
| 第二终结点创建|String|设备制造商，从终结点数据文件终结点字段中读取信息。 | <br/>&bull;没有用于终结点的数据文件 |
| 第二终结点模型|String|设备模型，从终结点数据文件 EndpointModel 字段中读取信息。| <br/>&bull;没有用于终结点的数据文件 |
| 第二终结点类型|String|设备类型，从终结点数据文件 EndpointType 字段中读取信息。|  <br/>&bull;没有用于终结点的数据文件|
| 第二终结点标签1|String| 可自定义标签，从终结点数据文件中读取信息。 | <br/>&bull;没有用于终结点的数据文件 |
| 第二终结点标签2|String|可自定义标签，从终结点数据文件中读取信息。| <br/>&bull;没有用于终结点的数据文件|
| 第二终结点标签3|String|可自定义标签，从终结点数据文件中读取信息。| <br/>&bull;没有用于终结点的数据文件 |
|**大楼**| | |
| First Network | String | 第一个终结点的媒体流用于媒体流的子网（如果子网存在于租户生成数据中）。 <br/> **示例值：** 10.0.1.12。0 | &bull;终结点未报告网络数据 <br/>&bull;子网映射数据中未定义网络。  |
| First Network Name  | String  | 第一终结点用于媒体流的网络名称。 基于将子网映射到租户生成数据。 <br/> **示例值：** 美国/WA/雷德蒙 | &bull;终结点未报告网络数据 <br/>&bull;子网映射数据中未定义网络  |
| First Network Range  | String  | 第一个终结点用于媒体流的子网的网络前缀/范围，基于与租户建筑物的数据映射子网。 <br/> **示例值：** 24 | &bull;终结点未报告网络数据 <br/>&bull;子网映射数据中未定义网络 |
| First Building Name  | String  | 根据将子网映射到租户建筑物数据，第一个终结点所在建筑物的名称。  <br/> **示例值：** 会计  | &bull;终结点未报告网络数据 <br/>&bull;子网映射数据中未定义网络   |
| First Ownership Type  | String  | 第一个终结点所在的建筑物的所有权类型。 基于将子网映射到租户生成数据。 <br/> **示例值：** Contoso-IT  | &bull;终结点未报告网络数据 <br/>&bull;网络不在企业网络内或网络所有权未在子网映射数据中定义  |
| First Building Type   | String  | 基于子网与租户建筑物数据的映射，第一个终结点所在的构建类型。 <br/> **示例值：** 打开 Office | &bull;终结点未报告网络数据 <br/>&bull;网络不在企业网络中 <br/>&bull;子网映射数据中未定义网络建筑物类型  |
| First Building Office Type  | String  | 基于子网与租户建筑物数据的映射，第一个终结点所在的构建类型。 <br/> **示例值：** 打开 Office | &bull;终结点未报告网络数据 <br/>&bull;网络不在企业网络中 <br/>&bull;子网映射数据中未定义网络建筑物类型  |
| First City  | String  | 根据子网与租户建筑物数据的映射，第一个终结点所在的城市。 <br/> **示例值：** 德 | &bull;终结点未报告网络数据 <br/>&bull;网络不在企业网络中 <br/>&bull;网络没有在子网映射数据中定义城市   |
| First Zip Code  | String  | 基于子网与租户建筑物数据的映射，第一个终结点所在的邮政编码。 <br/> **示例值：** 98052 | &bull;终结点未报告网络数据 <br/>&bull;网络不在企业网络中 <br/>&bull;网络没有在子网映射数据中定义的邮政编码   |
| First Country  | String  | 基于子网与租户建筑物数据的映射，第一个终结点所在的国家/地区。 <br/> **示例值：** 特区 | <br/>&bull;终结点未报告网络数据<br/>&bull;网络不在企业网络中 <br/>&bull;网络没有在子网映射数据中定义的国家/地区 |
| First State  | String  | 基于子网与租户建筑物数据的映射，第一个终结点所在的状态。 <br/> **示例值：** WA | <br/>&bull;终结点未报告网络数据<br/>&bull;网络不在企业网络中 <br/>&bull;网络没有在子网映射数据中定义的状态。   |
| First Region  | String  | 基于子网与租户建筑物数据的映射，第一个终结点所在的区域。 <br/> **示例值：** 北美 | <br/>&bull;终结点未报告网络数据<br/>&bull;网络不在企业网络中 <br/>&bull;网络没有在子网映射数据中定义的区域。 |
| First Express Route  | 布尔值  | 如果第一终结点用于媒体流的子网针对 Azure ExpressRoute 启用，基于将子网映射到租户生成数据，则为 True。 如果你决定，可以自定义其他用途的用法。  |  &bull;终结点未报告网络数据 <br/>&bull;网络不在企业网络中 <br/>&bull;网络没有在子网映射数据中设置的 ExpressRoute 标志。|
| Second Network  | 字符串  | 第二终结点用于媒体流的子网（如果子网中存在子网与租户建筑物数据）。 <br/> **示例值：** 10.0.1.12。0  | &bull;终结点未报告网络数据 <br/>&bull;子网映射数据中未定义网络  |
| Second Network Name  | String  | 第二终结点用于媒体流的网络的名称，基于将子网映射到租户生成数据。 <br/> **示例值：** 美国/WA/雷德蒙  | &bull;终结点未报告网络数据 <br/>&bull;网络没有在子网映射数据中定义的网络名称  |
| Second Network Range  | String  | 第二终结点用于媒体流的子网的网络前缀/范围，基于将子网映射到租户生成数据。 <br/> **示例值：** 24  | &bull;终结点未报告网络数据 <br/>&bull;网络没有在子网映射数据中定义网络范围  |
| Second Building Name  | String  | 根据将子网映射到租户建筑物数据，第二终结点所在建筑物的名称。 <br/> **示例值：** 会计 | <br/>&bull;终结点未报告网络数据<br/>&bull;网络不在企业网络中 <br/>&bull;网络没有在子网映射数据中定义的建筑物名称 |
| Second Ownership Type  | String  | 基于将子网映射到租户生成数据的第二终结点所在建筑物的所有权类型。 <br/> **示例值：** Contoso-IT | &bull;终结点未报告网络数据<br/>&bull;网络不在企业网络中 <br/>&bull;网络没有在子网映射数据中定义的所有权 |
| Second Building Type  | String  | 基于子网与租户建筑物数据的映射，第二终结点所在的建筑物的类型。 <br/> **示例值：** 打开 Office | <br/>&bull;终结点未报告网络数据<br/>&bull;网络不在企业网络中 <br/>&bull;子网映射数据中未定义网络建筑物类型   |
| Second Building Office Type  | String  | 基于将子网映射到租户生成数据的第二终结点所在的 Office 建筑物类型。 <br/> **示例值：** Office  | <br/>&bull;终结点未报告网络数据<br/>&bull;网络不在企业网络中 <br/>&bull;网络没有在子网映射数据中定义的构建 office 类型。  |
| Second City  | String  | 根据将子网映射到租户建筑物数据，第二终结点所在的城市。 <br/> **示例值：** 德 |  <br/>&bull;终结点未报告网络数据  <br/>&bull;网络不在企业网络中  <br/>&bull;网络没有在子网映射数据中定义城市   |
| Second Zip Code  | String  | 根据子网与租户建筑物数据的映射，第二终结点所在的邮政编码。 <br/> **示例值：** 98052  | <br/>&bull;终结点未报告网络数据 <br/>&bull;网络不在企业网络中 <br/>&bull;网络没有在子网映射数据中定义的邮政编码 |
| Second Country  | String  | 基于将子网映射到租户建筑物数据的第二终结点所在的国家/地区。 <br/> **示例值：** 特区  | <br/>&bull;终结点未报告网络数据<br/>&bull;网络不在企业网络中 <br/>&bull;网络没有在子网映射数据中定义的国家/地区  |
| Second State  | String  | 根据子网与租户建筑物数据的映射，第二终结点所在的状态。 <br/> **示例值：** WA  | <br/>&bull;终结点未报告网络数据<br/>&bull;网络不在企业网络中 <br/>&bull;网络没有在子网映射数据中定义的状态  |
| Second Region  | String  | 第二终结点所在的区域，基于将子网映射到租户生成数据的位置。 <br/> **示例值：** 北美  | <br/>&bull;终结点未报告网络数据 <br/>&bull;网络不在企业网络中 <br/>&bull;网络没有在子网映射数据中定义区域。 |
| Second Express Route  | 布尔值  | 如果通过第二终结点用于媒体流的子网针对 ExpressRoute 启用，并基于将子网映射到租户生成数据，则为 True。    | <br/>&bull;终结点未报告网络数据 <br/>&bull;网络不在企业网络中 <br/>&bull;网络没有在子网映射数据中设置的 ExpressRoute 标志   |
| First Inside Corp  | 枚举 <br/>**可能的值：** <br/> 内部、外部  | 指示第一个终结点是否位于企业网络内的子网上，具体取决于将子网映射到租户生成数据。 默认情况下，认为终结点位于外部。 <br/> **示例值：** 置于 | |
| Second Inside Corp  | 枚举 <br/> **可能的值：** <br/> 内部、外部 | 指示第二个终结点是否位于企业网络内的子网上，具体取决于将子网映射到租户生成数据。 默认情况下，认为终结点位于外部。 <br/>**示例值：** 置于  |  |
|**Deployment**| | | |
| First Tenant Id  | 字符串  | 第一终结点的 Office 365 租户 ID。 <br/> **示例值：** 00000000 （0000-0000-0000）-000000000000  | <br/>&bull;无法确定第一个终结点的租户 id。 这可能表示终结点已登录到内部部署的 Skype for business 服务器部署。  |
| Second Tenant Id  | String  | 第二终结点的 Office 365 租户 ID。 <br/> **示例值：** 00000000 （0000-0000-0000）-000000000000  |  <br/>&bull;无法确定第二终结点的租户 id。 这可能表示终结点已登录到内部部署的 Skype for business 服务器部署。  |
| First Pool  | String  | 分配给第一终结点的 Skype for Business Online 池 FQDN <br/> **示例值：** pool1<span></span><span></span>  | <br/>&bull;指示终结点已登录到 Microsoft 团队或 Skype for Business。 将仅为使用内部部署 Skype for Business 服务器部署的流填充此字段。 |
| Second Pool  | String  | 分配给第二终结点的 Skype for Business Online 池 FQDN <br/> **示例值：** <span>pool1.lync.com</span>   | &bull;无法确定第二终结点的 Skype for Business Online 池。 这可能表示终结点已登录到内部部署的 Skype for business 服务器部署。  |
| Is Federated  | Boolean  | 如果流在两个联合租户之间，则为 True，否则为 False。   | <br/>&bull;无法确定它是否是联合流 <br/>&bull;未收集某些信号数据   |
|区域 | String   |  基于租户的主区域的部署所在的地区。 <br/> **示例值：** 北美 | <br/>&bull;未报告网络数据 <br/>&bull;网络不在企业网络中 <br/>&bull;网络没有在子网映射数据中定义区域。 |
|**Stream**| | | |
| QoE Record Available  | 布尔值  | 如果为通话/会话提供至少一个用户体验质量报告，则为 True。 只有当 QoE 记录可用时，许多维度和测量才可用。 如果呼叫设置失败，QoE 记录将不可用。    |   |
| CDR Record Available  | Boolean  | 如果为通话/会话提供至少一个呼叫详细记录，则为 True。     | |
| Media Line Label  | 整型  | SDP 中用于媒体行的标签。使用"媒体类型"来确定是否为视频、音频、应用共享或基于视频的屏幕共享使用标签。<br/> **示例值：** 0  | &bull;终结点未报告此数据。  |
| Media Type  | 字符串  | 媒体的类型（视频、音频、应用共享或基于视频的屏幕共享）。 <br/> **示例值：** 视听 |  |
|媒体行标签文本 | String |与流相对应的媒体行的会话描述协议（SDP）标签属性。 有关详细信息，请参阅[RFC 4574](https://tools.ietf.org/html/rfc4574) 。 <br/> **示例值**： <br/> 主音频<br/> 主视频<br/> main-video1<br/> main-video2<br/> main-video3<br/> main-video4<br/> main-video5<br/> main-video6<br/> main-video7<br/> main-video8<br/> main-video9<br/> 全景视频<br/> applicationsharing-视频<br/> 数据   | |
| First Is Server  | 枚举 <br/>**可能的值：** <br/>&bull;客户端 <br/>&bull;服务  | 指示第一个终结点是服务器终结点（如会议服务器）（AVMCU、ASMCU）或其他媒体服务器（中介服务器），还是客户端终结点。  **示例值：** 客户端 | |
| Second Is Server  | 枚举 <br/>**可能的值：** <br/>&bull;客户端 <br/>&bull;服务   | 指示第二个终结点是服务器终结点还是客户端终结点。 <br/>  **示例值：** 客户端 | |
| First Is Caller  | 布尔值  | 如果第一个终结点是启动会话的调用方，则为 True。   | |
| First Network Connection Detail  | 枚举 <br>**可能的值：** <br/>&bull;线 <br/>&bull;Wifi <br/>&bull;MobileBB <br/>&bull;通道 <br/>&bull;之外 | 第一终结点使用的网络类型。  <br/> **示例值：** 线  | &bull;终结点未报告数据  |
| Second Network Connection Detail  | 枚举 <br/>**可能的值：** <br/>&bull;线 <br/>&bull;Wifi <br/>&bull;MobileBB <br/>&bull;通道 <br/>&bull;之外 | 第二终结点使用的网络类型。  <br/> **示例值：** 线  | &bull;终结点未报告数据  |
| Stream Direction  | 枚举 <br/>**可能的值：** <br/>&bull;第一秒 <br/>&bull;第二至前 <br/> | 指示流的方向。 <br/>&bull;**示例值：** 第一秒 | &bull;未报告任何数据指示流的方向 |
| Payload Description  | 字符串  | 流中最后使用的编解码器的名称。 <br/> **示例值：** SILKWide | &bull;无可用数据 |
| Audio and Video Call  | Boolean  | 如果通话同时具有音频流和视频流，则为 True，否则为 False    | &bull;未报告任何数据表示流的媒体类型。 |
| Duration 5 seconds or less  | Boolean  | 如果流的持续时间大于或等于5秒，则为 True，否则为 False。   ||
| Duration 60 seconds or more  | 布尔值  | 如果流的持续时间为60秒，则为 True，否则为 False。   | |
| 团队  | Boolean  | True 表示流的第一或第二用户代理是 Microsoft 团队终结点。 <br/> False 表示用户代理是 Skype for Business 终结点。 |  |
| Duration (Minutes)  | 范围（分钟）  | 流的持续时间，以分钟为单位。值按范围分组表示。<br/> **示例值：** 065： [3 –4） ||
| Duration (Seconds)  | 范围（秒） | 流的持续时间，以秒为单位。值按范围分组表示。<br/> **示例值：** 062： [1-2）||
|**日期**|||
|结束时间|  String| 通话结束的时间。|&bull;呼叫设置失败 |
| Year  | 整型  | 流结尾的年份。 在 UTC 时区中报告值。 <br/> **示例值：** 2018 | |
| Month  | 整型  | 流末尾的月份。 在 UTC 时区中报告值。 <br/> **示例值：** 2 | |
| Day  | 整型  | 流结尾的一天。 在 UTC 时区中报告值。 <br/> **示例值：** 1 | |
| 日期  | String  | 流结束的日期。 在 UTC 时区中报告值。 <br/> **示例值：** 2018-06-01 | |
| Hour  | 整型  | 流结尾的小时数。 在 UTC 时区中报告值。 <br/> **示例值：** 1  ||
| Minute  | 整型  | 流结尾的分钟数。 在 UTC 时区中报告值。 <br/> **示例值：** 30 | |
| Second  | 整型  | 流末尾的秒数。 在 UTC 时区中报告值。 <br/> **示例值：** 12 | |
| Day Of Year  | 整型  | 流结尾的一年中的某一天。 在 UTC 时区中报告值。 <br/> **示例值：** 32 | |
| Day Of Week  | 字符串  | 流结尾的一周中的某一天。 在 UTC 时区中报告值。 <br/> **示例值：** 星期三 | |
| Day Number Of Week  | 整型  | 流末尾的第几周的天数。 在 UTC 时区中报告值。 <br/> **示例值：** 3 | |
|单周|  String  |发生通话的周的开始日期。 <br/> **示例值：** 2019-09-01 |&bull;呼叫设置失败 |
| Month Year  | String  | 流结尾的月份和年份。 在 UTC 时区中报告值。 <br/> **示例值：** 2017-02 | |
| Full Month  | 日期时间  | 流末尾的完整月份。 在 UTC 时区中报告值。 <br/> **示例值：** 2017-02-01T00：00：00 | |
|开始时间|String  |通话开始的时间。|&bull;呼叫设置失败 |
|**UserAgent** | | |
| First Domain  | String  | 第一个终结点的用户的域。 如果第一个终结点是会议服务器，它将使用会议组织者的域。 也可能是场景中使用的服务帐户的域。  <br/> **示例值：** contoso<span></span> | |
| Second Domain  | String  | 第二终结点用户的域。 如果第二个终结点是会议服务器，它将使用会议组织者的域。 也可能是场景中使用的服务帐户的域。 <br/> **示例值：** contoso<span></span>  | |
| First User Agent Category  | String  | 第一终结点的用户代理的类别。 <br/> **示例值：** OC | &bull;用户代理目前没有映射    |
| Second User Agent Category  | String  | 第二终结点的用户代理的类别。 <br/> **示例值：** OC | &bull;用户代理目前没有映射    |
| First User Agent  | String  | 第一终结点的用户代理字符串。 <br/> **示例值：** UCCAPI/16.0.7766.5281 OC/16.0.7766.2047 （Skype for Business） | &bull;第一个终结点未报告任何用户代理   |
| Second User Agent  | String  | 第二终结点的用户代理字符串。 <br/> **示例值：** UCCAPI/16.0.7766.5281 OC/16.0.7766.2047 （Skype for Business） | &bull;第二终结点未报告用户代理   |
| Conference Type  | 枚举 <br/>**可能的值：** <br/>&bull;会议： applicationsharing <br/>&bull;会议：音频-视频 <br/>&bull;会议：焦点 | 会议 URI 的类型。  <br/> **示例值：** 会议：音频-视频 | &bull;非会议方案。   |
| 会议 ID  | String | 与流相关联的会议 ID （或通话 ID）。 在 cqd.teams.microsoft.com 中，所有呼叫都有一个呼叫 ID，无论它们是人到人员（P2P）呼叫还是电话会议。 在 cqd.lync.com 中，此值仅适用于 Skype for business 会议呼叫 avialble。  此维度可能有太多行，无法用作报表中的维度。 它可能会转为用作筛选器。  <br/> **示例值（cqd.lync.com）：** 0001P6GK <br/> **示例值（cqd.teams.microsoft.com）：** 5a962ccf-b9cb-436a-a433-f28bf5404ad8  | |
| First Client App Version  | String  | 第一终结点使用的应用程序的版本。数据从用户代理字符串解析。<br/> **示例值：** 16.0.7766.2047 | &bull;无法解析版本字符串 <br/>&bull;未报告值。   |
| Second Client App Version  | 字符串  | 第二终结点使用的应用程序的版本。数据从用户代理字符串解析。<br/> **示例值：** 16.0.7766.2047 | &bull;无法解析版本字符串 <br/>&bull;未报告值。 |
|会议 Id （在 cqd.teams.microsoft.com 中） <br/> 会议 ID （在 cqd.lync.com 中） |String |会议的标识符，在创建会议时生成。 <br/> **示例值（Skype For business）：** 0001P6GK  <br/> **示例值（团队）：** 19： meeting_MzB .。。zIw@thread v2| |
|**网络**||| 
| Transport  | 枚举 <br/>**可能的值：** <br/>&bull;UDP <br/>&bull;TCP-OUT <br/>&bull;辨识  | 流使用的网络传输类型。  "无法识别" 表示系统无法确定传输类型是 TCP 还是 UDP。  | &bull;未报告传输类型 <br/>&bull;未建立媒体路径  |
| First Connectivity Ice  | 枚举 <br/>**可能的值：** <br/>&bull;直接 = 直接网络路径 <br/>&bull;中继 = 通过中继 <br/>&bull;HTTP = 通过 HTTP 代理 <br/>&bull;失败 = 连接失败 | 第一终结点使用的 ICE 连接类型。  |&bull;未报告传输类型 <br/>&bull;未建立媒体路径   |
| Second Connectivity Ice  | 枚举 <br/>**可能的值：** <br/>&bull;直接 = 直接网络路径 <br/>&bull;中继 = 通过中继 <br/>&bull;HTTP = 通过 HTTP 代理 <br/>&bull;失败 = 连接失败  | 第二终结点使用的 ICE 连接类型。    | &bull;未报告传输类型 <br/>&bull;未建立媒体路径    |
| First IP Address  | String  | 第一终结点的 IP 地址。请注意，此维度可能包含过多的行，导致无法用作报告中的一个维度。它可能会转为用作筛选器。<br/> **示例值：** 10.0.0.10  | &bull;未报告传输类型 <br/>&bull;未建立媒体路径   |
| Second IP Address  | String  | 第二终结点的 IP 地址。 <br/> **注意：** 此维度可能有太多行，无法用作报表中的维度。 It can be used as a filter instead. <br/> **示例值：** 10.0.0.10  | &bull;未报告传输类型 <br/>&bull;未建立媒体路径   |
| First Link Speed   |整型  | 第一终结点使用的网络适配器报告的链路速度，以"位/秒"为单位。 <br/> **示例值：** 10000000  | &bull;未报告传输类型 <br/>&bull;未建立媒体路径   |
| Second Link Speed   |整型  | 第二终结点使用的网络适配器报告的链路速度，以"位/秒"为单位。 <br/> **示例值：** 10000000 | &bull;未报告传输类型 <br/>&bull;未建立媒体路径    |
| First Port  | 端口号  | 第一终结点用于媒体的网络端口号。 <br/> **示例值：** 50018  | &bull;未报告传输类型 <br/>&bull;未建立媒体路径   |
| Second Port  | 端口号  | 第二终结点用于媒体的网络端口号。 <br/> **示例值：** 50018 | &bull;未报告传输类型 <br/>&bull;未建立媒体路径    |
| First Reflexive Local IP  | String  | 媒体中继服务器观察到的第一终结点的 IP 地址。通常是与流的第一终结点关联的公共内部 IP 地址。<br/> **示例值：** 104.43.195.251  | &bull;未报告传输类型 <br/>&bull;未建立媒体路径   |
| Second Reflexive Local IP  | String  | 媒体中继服务器观察到的第二终结点的 IP 地址。通常是与流的第二终结点关联的公共内部 IP 地址。<br/> **示例值：** 104.43.195.251  | &bull;未报告传输类型 <br/>&bull;未建立媒体路径  |
| First Relay IP  | String  | 第一终结点分配的媒体中继服务器的 IP 地址。 <br/> **示例值：** 104.43.195.251  | &bull;未报告传输类型 <br/>&bull;未建立媒体路径   |
| Second Relay IP  | String  | 第二终结点分配的媒体中继服务器的 IP 地址。 <br/> **示例值：** 104.43.195.251 | &bull;未报告传输类型 <br/>&bull;未建立媒体路径|
| First Relay Port  | 整型  | 第一终结点在媒体中继服务器上分配的媒体端口。 <br/> **示例值：** 3478  | &bull;未报告传输类型 <br/>&bull;未建立媒体路径   |
| Second Relay Port  | 整型  | 第二终结点在媒体中继服务器上分配的媒体端口。 <br/> **示例值：** 3478  | &bull;未报告传输类型 <br/>&bull;未建立媒体路径|
| First Subnet  | String  | 第一终结点用于媒体流的子网，每个八进制数用短划线隔开。 <br/> **示例值：** 104.43.195。0  | &bull;终结点未报告的数据 <br/>&bull;未建立媒体路径 <br/>&bull;已使用 IPv6|
| Second Subnet  | 字符串  | 第二终结点用于媒体流的子网，每个八进制数用短划线隔开。 <br/> **示例值：** 104.43.195。0 | &bull;终结点未报告的数据 <br/>&bull;未建立媒体路径 <br/>&bull;已使用 IPv6 |
| First VPN  | Boolean  | 如果第一终结点使用的网络适配器指示它是 VPN 连接，则为 True，否则为 False。 有些 VPN 不会正确报告此数据。   | &bull;未报告传输类型 <br/>&bull;未建立媒体路径   |
| Second VPN  | Boolean  | 如果第二终结点使用的网络适配器指示它是 VPN 连接，则为 True，否则为 False。 有些 VPN 不会正确报告此数据。    | &bull;未报告传输类型 <br/>&bull;未建立媒体路径   |
| Applied Bandwidth Source  | 枚举 <br/>**可能的值：** <br/>&bull;静态最大值 <br/>&bull;API 模态 <br/>&bull;API Modality_All <br/>&bull;API SendSide BWLimit <br/>&bull;首选值 <br/>&bull;关闭 <br/>&bull;ReceiveSide 车 <br/>&bull;API SDP 模态 <br/>&bull;已收到远程 <br/>&bull;侧面 BWLimit <br/>&bull;API ServiceQuality <br/>&bull;API SDP <br/>&bull;接收 SidePDP | 指示应用于流的带宽来源。 | &bull;未报告传输类型 <br/>&bull;未建立媒体路径   |
| Bandwidth Est | 整数范围  | 第一和第二终结点之间可用的平均带宽估计值，以"位/秒"为单位。  <br/> **示例值：** 026： [260000-270000）  | &bull;未报告传输类型 <br/>&bull;未建立媒体路径  |
| Mediation Server Bypass Flag  | 布尔值  | 如果媒体流绕过中介服务器，并且在客户端和 PSTN 网关/PBX 之间直接出现，则为 True，否则为 False。   | &bull;未报告传输类型 <br/>&bull;未建立媒体路径    |
| 第一个 CDR 连接类型  | 枚举 <br/>**可能的值：** <br/>&bull;O <br/>&bull;PeerDerived <br/>&bull;Stun <br/>&bull;关闭  | 指示第一终结点选择用于此流的 ICE 连接路径。 <br/> **示例值：** O  | &bull;未报告传输类型 <br/>&bull;未建立媒体路径   |
| 第二个 CDR 连接类型  | 枚举 <br/>**可能的值：** <br/>&bull;O <br/>&bull;PeerDerived <br/>&bull;Stun <br/>&bull;关闭  | 指示第二终结点选择用于此流的 ICE 连接路径。  <br/> **示例值：** O   | &bull;未报告传输类型 <br/>&bull;未建立媒体路径   |
|第一个 BSSID|String | 用于连接到网络的第一个终结点的无线 LAN 基本服务集标识符。| |
| 第二个 BSSID| String|用于连接到网络的第二终结点的无线 LAN 基本服务集标识符。| |
| 第一个基址 | String | 第一个终结点用于分配媒体中继候选人的接口的 IP 地址。 仅对过去30天的数据可用，并且仅对具有允许 EUII 访问权限的用户可见。 <br/> **示例值：** 10.0.0.10 | &bull;未报告传输诊断类型 <br/>&bull;未建立媒体路径 |
| 第二基址 | String | 第二终结点用于分配媒体中继候选人的接口的 IP 地址。 仅对过去30天的数据可用，并且仅对具有允许 EUII 访问权限的用户可见。 <br/> **示例值：** 10.0.0.10 | &bull;未报告传输诊断类型 <br/>&bull;未建立媒体路径 |
| 第一个本地地址 | String | 媒体连接检查结束时用于媒体流的第一个终结点的 IP 地址。 仅对过去30天的数据可用，并且仅对具有允许 EUII 访问权限的用户可见。 <br/> **示例值：** 10.0.0.10 | &bull;未报告传输诊断类型 <br/>&bull;未建立媒体路径 |
| 第二本地地址 | String | 在媒体连接检查结束时，第二终结点用于媒体流的 IP 地址。 仅对过去30天的数据可用，并且仅对具有允许 EUII 访问权限的用户可见。 <br/> **示例值：** 10.0.0.10 | &bull;未报告传输诊断类型 <br/>&bull;未建立媒体路径 |
| 第一本地地址类型 | 枚举 <br/>**可能值** <br/>&bull;IceAddrType_Os <br/>&bull;IceAddrType_Stun <br/>&bull;IceAddrType_Turn <br/>&bull;IceAddrType_UPnP <br/>&bull;IceAddrType_ISA_Proxy <br/>&bull;IceAddrType_PeerDerived <br/>&bull;IceAddrType_Invalid | 第一个本地地址的候选类型。 IceAddrType_Turn 表示中继呼叫。 其余类型指示直接连接。 | &bull;未报告传输诊断类型 <br/>&bull;未建立媒体路径 |
| 第二本地地址类型 | 枚举 <br/>**可能值** <br/>&bull;IceAddrType_Os <br/>&bull;IceAddrType_Stun <br/>&bull;IceAddrType_Turn <br/>&bull;IceAddrType_UPnP <br/>&bull;IceAddrType_ISA_Proxy <br/>&bull;IceAddrType_PeerDerived <br/>&bull;IceAddrType_Invalid | 第二本地地址的候选类型。 IceAddrType_Turn 表示中继呼叫。 其余类型指示直接连接。 | &bull;未报告传输诊断类型 <br/>&bull;未建立媒体路径 |
| 第一个远程地址 | String | 第二终结点的 IP 地址，第二终结点在媒体连接检查结束时，第一个终结点将媒体发送到该终结点。 仅对过去30天的数据可用，并且仅对具有允许 EUII 访问权限的用户可见。 <br/> **示例值：** 10.0.0.10 | &bull;未报告传输诊断类型 <br/>&bull;未建立媒体路径 |
| 第二远程地址 | String | 在媒体连接检查结束时第二终结点将媒体发送到的第一个终结点的 IP 地址。 仅对过去30天的数据可用，并且仅对具有允许 EUII 访问权限的用户可见。 <br/> **示例值：** 10.0.0.10 | &bull;未报告传输诊断类型 <br/>&bull;未建立媒体路径 |
| 第一远程地址类型 | 枚举 <br/>**可能值** <br/>&bull;IceAddrType_Os <br/>&bull;IceAddrType_Stun <br/>&bull;IceAddrType_Turn <br/>&bull;IceAddrType_UPnP <br/>&bull;IceAddrType_ISA_Proxy <br/>&bull;IceAddrType_PeerDerived <br/>&bull;IceAddrType_Invalid | 第一个远程地址的候选类型。 IceAddrType_Turn 表示中继呼叫。 其余值表示直接连接。 | &bull;未报告传输诊断类型 <br/>&bull;未建立媒体路径 |
| 第二远程地址类型 | 枚举  <br/>**可能值** <br/>&bull;IceAddrType_Os <br/>&bull;IceAddrType_Stun <br/>&bull;IceAddrType_Turn <br/>&bull;IceAddrType_UPnP <br/>&bull;IceAddrType_ISA_Proxy <br/>&bull;IceAddrType_PeerDerived <br/>&bull;IceAddrType_Invalid | 第二个远程地址的候选类型。 IceAddrType_Turn 表示中继呼叫。 其余值表示直接连接。 | &bull;未报告传输诊断类型 <br/>&bull;未建立媒体路径 |
| 第一个本地网站 | String | 媒体中继服务器看到的第一个终结点的 IP 地址。 这通常是与流的第一个终结点关联的公共 internet IP 地址。 如果由于某些原因，中继无法访问或分配失败，这将是第一个终结点上的本地接口的 IP。 <br/> 这与第一个反身本地 IP 类似，但此信息由传输诊断事件（而不是 QoE）报告。 仅对过去30天的数据可用，并且仅对具有允许 EUII 访问权限的用户可见。 <br/> **示例值：** 104.43.195.251 | &bull;未报告传输诊断类型 <br/>&bull;未建立媒体路径 |
| 第二本地网站 | String | 媒体中继服务器看到的第二终结点的 IP 地址。 这通常是与流的第二个终结点关联的公共 internet IP 地址。 如果由于某些原因，中继无法访问或分配失败，这将是第一个终结点上的本地接口的 IP。 <br/> 这与第二个反身本地 IP 类似，但此信息由传输诊断事件（而不是 QoE）报告。 仅对过去30天的数据可用，并且仅对具有允许 EUII 访问权限的用户可见。 <br/> **示例值：** 104.43.195.251 | &bull;未报告传输诊断类型 <br/>&bull;未建立媒体路径 |
| 第一个远程网站 | String | 第二终结点报告的本地站点 IP 地址，并与第一个终结点交换。 <br/> 由于任何原因，第二终结点上的传输诊断事件的额外信息不可用。 仅对过去30天的数据可用，并且仅对具有允许 EUII 访问权限的用户可见。 <br/> **示例值：** 104.43.195.251 | &bull;未报告传输诊断类型 <br/>&bull;未建立媒体路径 |
| 第二远程网站 | String | 第一个终结点报告的本地站点 IP 地址，并与第二个终结点交换。 <br/> 额外信息，以防第一个终结点上的传输诊断事件因任何原因不可用。 仅对过去30天的数据可用，并且仅对具有允许 EUII 访问权限的用户可见。 <br/> **示例值：** 104.43.195.251 | &bull;未报告传输诊断类型 <br/>&bull;未建立媒体路径 |
| 第一个本地媒体中继地址 | String | 第一个终结点分配的媒体中继服务器的 Microsoft IP 地址。 <br/> 这与第一个中继 IP 的信息类似，但它由传输诊断事件（而不是 QoE）报告。 <br/> **示例值：** 52.114.5.237 | &bull;未报告传输诊断类型 <br/>&bull;未建立媒体路径 |
| 第二个本地媒体中继地址 | String | 第二终结点分配的媒体中继服务器的 Microsoft IP 地址。 <br/> 这与第二个中继 IP 的信息类似，但它由传输诊断事件（而不是 QoE）报告。 <br/> **示例值：** 52.114.5.237 | &bull;未报告传输诊断类型 <br/>&bull;未建立媒体路径 |
| 第一个远程媒体中继地址 | String | 由第二终结点分配并与第一个终结点交换的媒体中继服务器的 Microsoft IP 地址。 <br/> 额外信息，以防第二终结点上的传输诊断事件因任何原因不可用。 <br/> **示例值：** 52.114.5.237 | &bull;未报告传输诊断类型 <br/>&bull;未建立媒体路径 |
| 第二个远程媒体中继地址 | String | 由第一个终结点分配并与第二个终结点交换的媒体中继服务器的 Microsoft IP 地址。 <br/> 额外信息，以防第一个终结点上的传输诊断事件因任何原因不可用。 <br/> **示例值：** 52.114.5.237 | &bull;未报告传输诊断类型 <br/>&bull;未建立媒体路径 |
| 第一传输协议 | 枚举字符串 | 第一个终结点用于发送媒体的通信协议。 <br/>**可能值** <br/>&bull;UDP-多用途 UDP 用于转换和主机分配 <br/>&bull;TurnTCP-TCP 车削分配。 如果指定了代理设置，则使用代理 <br/>&bull;TCPHostPassive-TCP 侦听主机套接字以获取被动连接类型 <br/>&bull;TCPHostActive-使用活动连接类型的 TCP 连接 <br/>&bull;CompoundTCP-上游和下游 TCP 连接的组合。 通常通过 HTTPS 协议。 <br/> | &bull;未报告传输诊断类型 <br/>&bull;未建立媒体路径 |
| 第二传输协议 | 枚举字符串 | 第二终结点用于发送媒体的通信协议。 <br/>**可能值** <br/>&bull;UDP-多用途 UDP 用于转换和主机分配 <br/>&bull;TurnTCP-TCP 车削分配。 如果指定了代理设置，则使用代理 <br/>&bull;TCPHostPassive-TCP 侦听主机套接字以获取被动连接类型 <br/>&bull;TCPHostActive-使用活动连接类型的 TCP 连接 <br/>&bull;CompoundTCP-上游和下游 TCP 连接的组合。 通常通过 HTTPS 协议。 <br/> | &bull;未报告传输诊断类型 <br/>&bull;未建立媒体路径 |
|**Device**| |||
| First Capture Dev  | String  | 第一终结点使用的捕获设备的名称。对于：<br/> **音频流**= 用于麦克风的设备 <br/> **视频流**= 相机使用的设备 <br/> **基于视频的屏幕共享流**= 屏幕 scraper <br/> **应用共享流**= 空白 <br/> **示例值：** 耳机式麦克风（Microsoft LifeChat LX-6000）  | &bull;终结点未报告数据 <br/>&bull;未建立媒体路径 <br/>&bull;流是基于视频的屏幕共享或应用程序共享。  |
| Second Capture Dev  | 字符串  | 第二终结点使用的捕获设备的名称。  <br/> **音频流**= 用于麦克风的设备 <br/> **视频流**= 相机使用的设备 <br/> **基于视频的屏幕共享流**= 屏幕 scraper <br/> **应用共享流**= 空白 <br/> **示例值：** 耳机式麦克风（Microsoft LifeChat LX-6000） | <br/>&bull;终结点未报告数据 <br/>&bull;未建立媒体路径 <br/>&bull;流是基于视频的屏幕共享或应用程序共享   |
| First Capture Dev Driver  | String  | 第一终结点使用的捕获设备驱动器的名称，格式为"制造商: 版本"。对于：<br/> **音频流**= 用于麦克风的驱动程序 <br/> **视频流**= 相机使用的驱动程序 <br/> **基于视频的屏幕共享和应用共享流**= 空白  <br/> **示例值：** Microsoft：10.0.14393。0 | <br/>&bull;终结点未报告数据 <br/>&bull;未建立媒体路径 <br/>&bull;流是基于视频的屏幕共享或应用程序共享。  |
| Second Capture Dev Driver  | 字符串  | 第二终结点使用的捕获设备驱动器的名称，格式为"制造商: 版本"。对于：<br/> **音频流**= 用于麦克风的驱动程序 <br/> **视频流**= 相机使用的驱动程序 <br/> **基于视频的屏幕共享和应用共享流**= 空白 <br/> **示例值：** Microsoft：10.0.14393。0  | <br/>&bull;终结点未报告数据 <br/>&bull;未建立媒体路径 <br/>&bull;流是基于视频的屏幕共享或应用程序共享。  |
| First Render Dev  | String  | 第一终结点使用的呈现设备的名称。对于：<br/> 音频流-用于扬声器的设备 <br/> 视频和基于视频的屏幕共享流-用于显示的设备 <br/> 应用共享流 - 空  <br/> **示例值：** 耳机 Earphone （Microsoft LifeChat LX-6000） | <br/>&bull;终结点未报告此数据 <br/>&bull;未建立媒体路径  <br/>&bull;流是应用程序共享    |
| Second Render Dev  | String  | 第二终结点使用的呈现设备的名称。对于：<br/> 音频流-用于扬声器的设备 <br/> 视频和基于视频的屏幕共享流-用于显示的设备 <br/> 应用共享流 - 空 <br/> **示例值：** 耳机 Earphone （Microsoft LifeChat LX-6000） | <br/>&bull;终结点未报告此数据。 <br/>&bull;未建立媒体路径 <br/>&bull;流是应用程序共享     |
| First Render Dev Driver  | String  | 第一终结点使用的呈现设备驱动器的名称。对于：<br/> 音频流-用于扬声器的驱动程序 <br/> 视频和基于视频的屏幕共享流-用于显示的驱动程序 <br/> 应用共享流 - 空  <br/> **示例值：** Microsoft：10.0.14393。0 | <br/>&bull;终结点未报告此数据 <br/>&bull;未建立媒体路径 <br/>&bull;流是应用程序共享    |
| Second Render Dev Driver  | 字符串  | 第二终结点使用的呈现设备驱动器的名称。对于：<br/> 音频流-用于扬声器的驱动程序 <br/> 视频和基于视频的屏幕共享流-用于显示的驱动程序 <br/> 应用共享流 - 空 <br/> **示例值：** Microsoft：10.0.14393。0  | <br/>&bull;终结点未报告此数据 <br/>&bull;未建立媒体路径 <br/>&bull;流是应用程序共享   |
|**WiFi**|||
| 第一 wi-fi Microsoft 驱动程序  | String  | 第一终结点报告的所使用的 Microsoft WiFi 驱动器的名称。值可能会根据终结点使用的语言进行本地化。<br/> **示例值：** Microsoft 托管网络虚拟适配器  | <br/>&bull;终结点未使用 WiFi <br/>&bull;未报告驱动程序信息|
| 第二个 Wi-fi Microsoft 驱动程序  | String  | 第二终结点报告的所使用的 Microsoft WiFi 驱动器的名称。值可能会根据终结点使用的语言进行本地化。<br/> **示例值：** Microsoft 托管网络虚拟适配器  | <br/>&bull;终结点未使用 WiFi <br/>&bull;未报告驱动程序信息|
| 第一 wi-fi 供应商驱动程序  | String  | 第一终结点报告的 Wifi 驱动器的供应商和名称。 <br/> **示例值：** Contoso 双频无线-交流驱动程序  | <br/>&bull;终结点未使用 WiFi <br/>&bull;未报告驱动程序信息 |
| 第二个 Wi-fi 供应商驱动程序  | String  | 第二终结点报告的 Wifi 驱动器的供应商和名称。  <br/> **示例值：** Contoso 双频无线-交流驱动程序 | <br/>&bull;终结点未使用 WiFi <br/>&bull;未报告驱动程序信息 |
| 第一 wi-fi Microsoft 驱动程序版本  | String  | 第一终结点报告的 Microsoft Wifi 驱动器的版本。 <br/> **示例值：** Microsoft：10.0.14393。0 | <br/>&bull;终结点未使用 WiFi <br/>&bull;未报告驱动程序信息  |
| 第二个 Wi-fi Microsoft 驱动程序版本  | String  | 第二终结点报告的 Microsoft Wifi 驱动器的版本。 <br/> **示例值：** Microsoft：10.0.14393。0 | <br/>&bull;终结点未使用 WiFi <br/>&bull;未报告驱动程序信息  |
| 第一 wi-fi 供应商驱动程序版本  | String  | 第一终结点报告的 Wifi 驱动器的供应商和版本。 <br/> **示例值：** Contoso：15.1.1。0 | <br/>&bull;终结点未使用 WiFi <br/>&bull;未报告驱动程序信息  |
| 第二个 Wi-fi 供应商驱动程序版本  | String  | 第二终结点报告的 Wifi 驱动器的供应商和版本。 <br/> **示例值：** Contoso：15.1.1。0 | <br/>&bull;终结点未使用 WiFi <br/>&bull;未报告驱动程序信息  |
| 第一 Wi-fi 频道  | String  | 第一终结点使用的 Wifi 频道。  <br/> **示例值：** 10| <br/>&bull;未使用 WiFi <br/>&bull;未报告频道   |
| 第二个 Wi-fi 频道  | String  | 第二终结点使用的 Wifi 频道。 <br/> **示例值：** 10  | <br/>&bull;未使用 WiFi <br/>&bull;未报告频道  |
| 第一 Wi-fi 无线电类型  | 字符串  | 第一终结点使用的 WiFi 无线电的类型。HRDSSS 等于 802.11b。<br/> **示例值：** 802.11 ac  | <br/>&bull;未使用 WiFi <br/>&bull;未报告 WiFi 类型  |
| 第二个 Wi-fi 无线电类型  | String  | 第二终结点使用的 WiFi 无线电的类型。HRDSSS 等于 802.11b。<br/> **示例值：** 802.11 ac  | <br/>&bull;未使用 WiFi <br/>&bull;未报告 WiFi 类型  |
| First DNS Suffix  | 字符串  | 第一终结点报告的与网络适配器关联的 DNS 后缀。 请注意，可能会为任何类型的网络适配器报告此值。 **示例值：** corp<span></span><span></span>.com  | <br/>&bull;终结点未报告此值 <br/>  |
| Second DNS Suffix  | 字符串  | 第二终结点报告的与网络适配器关联的 DNS 后缀。请注意，可能会为任何类型的网络适配器报告此值。<br/> **示例值：** corp<span></span><span></span>.com   | <br/>&bull;终结点未报告此值  |
| 第一 Wi-fi 频带  | String  | 第一终结点报告的所使用的 Wifi 波段。 <br/> **示例值：** 5.0 Ghz  | <br/>&bull;值不是由终结点计算得出的 <br/>&bull;未报告值  |
| 第二个 Wi-fi 频带  | String  | 第二终结点报告的所使用的 Wifi 波段。 <br/> **示例值：** 5.0 Ghz  | <br/>&bull;值不是由终结点计算得出的 <br/>&bull;未报告值  |
| 第一 wi-fi 信号强度  | String  | 第一个终结点报告的 WiFi 信号强度百分比 [0-100]。 <br/> **示例值：** 081： [90-100）  | <br/>&bull;值不是由终结点计算得出的 <br/>&bull;未报告值  |
| 第二个 Wi-fi 信号强度  | String  | 第二终结点报告的 WiFi 信号强度（百分比 [0-100]）。 <br/> **示例值：** 081： [90-100）  | <br/>&bull;值不是由终结点计算得出的 <br/>&bull;未报告值  |
| 第一 wi-fi 电池电量  | 范围（百分比）  | 第一终结点报告的电池剩余电量的百分比估计值 [0-99]。值按范围分组表示。0 表示设备已插电。<br/> **示例值：** 081： [90-100） | &bull;未使用 WiFi <br/>&bull;未报告费用值   |
| 第二个 Wi-fi 电池电量  | 范围（百分比）  | 第二终结点报告的电池剩余电量的百分比估计值 [0-99]。值按范围分组表示。0 表示设备已插电。<br/> **示例值：** 081： [90-100） | &bull;未使用 WiFi <br/>&bull;未报告费用值  |
|**指标**|||
| Audio Degradation Avg  | 范围（平均意见得分 0-5） | 关于流降级的网络平均意见得分的平均值。 表示网络损失和抖动对收到的音频质量有多大影响。 值按范围分组表示。 <br/> **示例值：** 015： [0.01-0.02） | &bull;接收流的终结点未报告任何网络 MOS 性能下降 <br/>&bull;流不是音频流。    |
| Jitter  | 范围（毫秒）  | 流的平均抖动值，以毫秒为单位。值按范围分组表示。<br/> **示例值：** 065： [2-3）  | &bull;接收流的终结点未报告抖动数据 |
| Jitter Max  | 范围（毫秒）  | 流的最大抖动值，以毫秒为单位。值按范围分组表示。<br/> **示例值：** 065： [2-3） | &bull;接收流的终结点未报告抖动数据   |
| Packet Loss Rate  | 范围（比率）  | 流的平均丢包率。 值按范围分组表示。 0.1 表示丢失了10% 的数据包。 <br/> **示例值：** 015： [0.01-0.02）  | &bull;接收流的终结点未报告任何数据包丢失数据 |
| Packet Loss Rate Max  | 范围（比率）  | 流的最大丢包率。 值按范围分组表示。 0.1 表示丢失了10% 的数据包。 <br/> **示例值：** 023： [0.09-0.1）  | &bull;接收流的终结点未报告任何数据包丢失数据 |
| Overall Avg Network MOS  | 范围 (MOS)  | 流的网络 MOS 平均值。值按范围分组表示。<br/> **示例值：** 076： [4.4-4.5） | &bull;接收流的终结点未报告任何网络 MOS 性能下降 <br/>&bull;流不是音频流  |
| Ratio Concealed Samples Avg  | 范围（比率）  | 含有丢包隐藏生成样本的音频帧数与总音频帧数的比率。值按范围分组表示。0.1 表示 10% 的帧包含隐藏样本。<br/> **示例值：** 015： [0.01-0.02） | &bull;流的接收方未报告此值 <br/>&bull;流不是音频流  |
|隐藏比率最大值 |范围（比率） | 带有数据包丢失 concealment 生成的样本的音频帧的最大数量，包括音频帧总数。 值按范围分组表示。 0.1 表示 10% 的帧包含隐藏样本。 <br/> **示例值：** 015： [0.01-0.02）| |
| Ratio Stretched Samples Avg  | 范围（比率）  | 通过拉伸样本补偿抖动或丢失的音频帧数与总音频帧数的比率。值按范围分组表示。0.1 表示 10% 的音频帧包含拉伸样本。<br/> **示例值：** 017： [0.03-0.04） | &bull;流的接收方未报告此值  <br/>&bull;流不是音频流   |
|Healer 数据包丢弃比率|范围（比率） |通过 healer 接收的音频数据包总数 healer 丢弃的音频数据包的比率。 有关详细信息，请参阅[2.2.1.12.1 子元素](https://docs.microsoft.com/openspecs/office_protocols/ms-qoe/56d41628-26d5-44c8-8f79-6bac4b0355a5)。| |
| Healer FEC 数据包使用比率| 范围（比率）  |超过收到的 FEC 数据包的总数的已用转发错误纠正（FEC）数据包的比率。 有关详细信息，请参阅[2.2.1.12.1 子元素](https://docs.microsoft.com/openspecs/office_protocols/ms-qoe/56d41628-26d5-44c8-8f79-6bac4b0355a5)。  | |
| Round Trip  | 范围（毫秒）  | 计算的平均网络传播往返时间，根据 RFC3550 以毫秒为单位指定。值按范围分组表示。<br/> **示例值：** 070： [15-20）  | <br/>&bull;值不是由终结点计算得出的 <br/>&bull;未报告值  |
| Round Trip Max  | 范围（毫秒）  | 计算的最大网络传播往返时间，根据 RFC3550 以毫秒为单位指定。值按范围分组表示。<br/>**示例值：** 098： [350-375）   | <br/>&bull;值不是由终结点计算得出的 <br/>&bull;未报告值 |
| 数据包利用率 | 号码（数据包） |在会话中发送的实时传输协议（RTP）数据包的数量。|
| 抖动缓冲区大小平均|数字（范围） |会话期间抖动缓冲区的平均大小。| |
| 最大抖动缓冲区大小|数字（范围）|会话期间抖动缓冲区的最大大小。 |
| 抖动缓冲区大小最小值|数字（范围）|会话期间抖动缓冲区的最小大小。|
|相对的单向间隙持续时间| 对等的相对单向延迟中的间隔持续时间。||
| 音频帖子 FECPLR|  数字 |在应用音频 FEC 后报告数据包丢失率。 0.00 和1.00 之间的值。| |
| Network Jitter Avg  | 范围（毫秒）  | 会话期间以 20 秒时间窗口计算的平均网络抖动，以毫秒为单位。值按范围分组表示。<br/> **示例值：** 066： [3 –4）  | <br/>&bull;流不是音频流 <br/>&bull;接收流的终结点未报告数据  |
|网络抖动最大值|事件数|会话期间，最大网络抖动超过20秒的窗口。|
| 网络抖动最少|事件数|会话期间，最小网络抖动通过20秒窗口计算出来。| |
| Video Post FECPLR  | 范围（比率）  | 应用 FEC 后，跨所有视频流和编解码器汇总的丢包率。值按范围分组表示。<br/> **示例值：** 014： [0-0.01） | <br/>&bull;流不是视频或基于视频的屏幕共享流  <br/>&bull;接收流的终结点未报告数据   |
| Video Local Frame Loss Percentage Avg  | 范围（百分比）  | 向用户显示的视频帧丢失平均百分比。值按范围分组表示。其中包括从网络丢失恢复的帧。<br/> **示例值：** 160： [80-85） | <br/>&bull;流不是视频或基于视频的屏幕共享流  <br/>&bull;接收流的终结点未报告数据   |
| 收到的帧速率平均值  | 范围（每秒帧数）  | 在会话持续期间计算到的所有视频流每秒接收的平均帧数。值按范围分组表示。<br/> **示例值：** 101： [14.5-15） | <br/>&bull;流不是视频或基于视频的屏幕共享流  <br/>&bull;接收流的终结点未报告数据   |
| Low Frame Rate Call Percent | 范围（百分比）  | 帧速率低于 7.5 帧/秒的通话时间的百分比。值按范围分组表示。<br/> **示例值：** 099： [13.5-14） | <br/>&bull;流不是视频或基于视频的屏幕共享流  <br/>&bull;接收流的终结点未报告数据   |
| Video Packet Loss Rate  | 范围（比率）  | 在会话持续期间计算到的平均丢包比率（小数），根据 RFC3550 指定。值按范围分组表示。<br/> **示例值：** 037： [0.75-0.8） | <br/>&bull;流不是视频或基于视频的屏幕共享流  <br/>&bull;接收流的终结点未报告数据   |
| Video Frame Rate Avg  | 范围（每秒帧数）  | 在会话持续期间计算到的视频流每秒接收的平均帧数。值按范围分组表示。<br/> **示例值：** 135： [31.5-32）  | <br/>&bull;流不是视频或基于视频的屏幕共享流  <br/>&bull;接收流的终结点未报告数据  |
| Dynamic Capability Percent  | 范围（百分比）  | 客户端以低于此类型 CPU 预期视频处理容量的 70% 运行的时间的百分比，按范围分组。 <br/> **示例值：** 122： [25-25.5）  | <br/>&bull;流不是视频或基于视频的屏幕共享流  <br/>&bull;接收流的终结点未报告数据  |
| Spoiled Tile Percent Total  | 范围（百分比）  | 没有被发送到远程对等点（例如，从 MCU 到查看器）而是被丢弃的图块的百分比。值按范围分组表示。丢弃图块可能是由于客户端与服务器之间的带宽限制所致。<br/> **示例值：** 140： [34-34.5）  | <br/>&bull;流不是应用程序共享流 <br/>&bull;发送流的终结点未报告数据  |
| AppSharing Relative OneWay Average  | 范围（秒）  | 应用程序共享流终结点之间的平均相对单向延迟（以秒为单位）。 值按范围分组表示。 <br/> **示例值：** 015： [0.01-0.02） | <br/>&bull;流不是应用程序共享流 <br/>&bull;发送流的终结点未报告数据   |
| AppSharing RDP Tile Processing Latency Average  | 范围（毫秒）  | 在会议服务器上处理 RDP 堆栈图块的平均延迟，以毫秒为单位。值按范围分组表示。<br/> **示例值：** 103： [15.5-16） | &bull;流不是会议中的应用程序共享流 <br/>&bull;发送流的终结点未报告数据   | 
| First Network Delay Event Ratio  | 范围（比率）  | 满足以下条件的通话的比率（小数）：第一终结点检测到网络延迟足以影响实时双向通信能力。值按范围分组表示。<br/> **示例值：** 016： [0.02-0.03）  | &bull;这是非音频流 <br/>&bull;第一个终结点未报告数据|
| Second Network Delay Event Ratio  | 范围（比率）  | 满足以下条件的通话的比率（小数）：第二终结点检测到网络延迟足以影响实时双向通信能力。值按范围分组表示。<br/> **示例值：** 016： [0.02-0.03）  | &bull;指示非音频流 <br/>&bull;第二终结点未报告数据 |
| First Network Bandwidth Low Event Ratio  | 范围（比率）  | 满足以下条件的通话的比率（小数）：第一终结点检测到可用带宽或带宽策略低到足以导致已发送音频的质量差。值按范围分组表示。<br/> **示例值：** 016： [0.02-0.03） | &bull;这是非音频流 <br/>&bull;第一个终结点未报告数据  |
| Second Network Bandwidth Low Event Ratio  | 范围（比率）  | 满足以下条件的通话的比率（小数）：第二终结点检测到可用带宽或带宽策略低到足以导致已发送音频的质量差。值按范围分组表示。<br/> **示例值：** 016： [0.02-0.03） | &bull;指示非音频流 <br/>&bull;第二终结点未报告数据 |
| 第一麦克风故障率| 数字 |第一个终结点的麦克风捕获每5分钟的平均故障。 有关详细信息，请参阅[2.2.1.12.1 子元素](https://docs.microsoft.com/openspecs/office_protocols/ms-qoe/56d41628-26d5-44c8-8f79-6bac4b0355a5)。 |
| 第二麦克风故障率|数字 |第二终结点的麦克风捕获每5分钟的平均故障。 有关详细信息，请参阅[2.2.1.12.1 子元素](https://docs.microsoft.com/openspecs/office_protocols/ms-qoe/56d41628-26d5-44c8-8f79-6bac4b0355a5)。 |
| 第一扬声器故障率|事件数|第一个扬声器呈现每5分钟的平均故障。| |
| 第二扬声器故障率|事件数|第二个扬声器呈现的每5分钟平均故障。| |
|**音频**|||
| Audio FEC Used  | 布尔值  | True 表示通话期间在某些点上使用了音频前向纠错 (FEC)。False 表示未使用。     | &bull;流不是音频流 <br/>&bull;发送流的终结点未报告数据  |
|**测度**|||
| ClassifiedPoorCall  | Boolean  | 如果流根据 "[呼叫质量" 仪表板中的 "流分类](stream-classification-in-call-quality-dashboard.md)" 中列出的指标归类为差，则为 True。   | &bull;流未报告足够的指标被分类为 "良好" 或 "差"   |
| Video Poor Due To VideoPostFecplr  | 布尔值  | 如果流基于以下列表中列出的视频帖子 FEC PLR 后指标，则为 True：在 "[通话质量" 仪表板中流分类](stream-classification-in-call-quality-dashboard.md)。 对于非视频流，将始终为 False。   | &bull;终结点未报告此数据  <br/>&bull;流不是视频流。  |
| 由于 VideoLocalFrameLossPercentageAvg，视频较差  | Boolean  | 如果视频流根据视频本地帧丢失百分比（此处列出的平均指标阈值）分类为差，则为 True：[在 "通话质量" 仪表板中流分类](stream-classification-in-call-quality-dashboard.md)。 对于非视频流，将始终为 False。   | &bull;终结点未报告此数据  <br/>&bull;流不是视频流。 |
| 由于 VideoFrameRateAvg，视频较差  | Boolean  | 如果视频流根据视频帧速率（此处列出的 "平均指标阈值"）分类为差，则为 True：[在 "通话质量" 仪表板中流分类](stream-classification-in-call-quality-dashboard.md)。 对于非视频流，将始终为 False。    | &bull;终结点未报告此数据  <br/>&bull;流不是视频流 |
| VBSS 较差，原因是 VideoPostFecplr  | Boolean  | 如果基于视频 Post 的视频 Post 流将基于视频的屏幕共享流归类为差的 FEC，则为 True：在 "[通话质量" 仪表板中流分类](stream-classification-in-call-quality-dashboard.md)。 对于不基于视频的屏幕共享流，将始终为 False。    | &bull;终结点未报告此数据 <br/>&bull;流不是基于视频的屏幕共享流  |
| VBSS 较差，原因是 VideoLocalFrameLossPercentageAvg  | Boolean  | 如果基于视频本地帧丢失百分比将基于视频的屏幕共享流归类为差的情况，则为 True： "[通话质量" 仪表板中的 "流分类](stream-classification-in-call-quality-dashboard.md)"。 对于不基于视频的屏幕共享流，将始终为 False。    | &bull;终结点未报告此数据 <br/>&bull;流不是基于视频的屏幕共享流  |
| 由于冻结而导致视频较差 | Boolean  | 如果视频流基于视频冻结实例被分类为差，则为1：[在通话质量仪表板中流分类](stream-classification-in-call-quality-dashboard.md) | &bull;终结点未报告此数据  <br/>&bull;流不是视频流。 此字段仅特定于 Microsoft 团队。 |
| VBSS 较差，原因是 VideoFrameRateAvg  | Boolean  | 如果基于视频帧速率对基于视频的屏幕共享流归类为差的情况，则为 True： "[通话质量" 仪表板中的 "流分类](stream-classification-in-call-quality-dashboard.md)"。 对于不基于视频的屏幕共享流，将始终为 False。   | &bull;终结点未报告此数据 <br/>&bull;流不是基于视频的屏幕共享流   |
| 应用共享较差，原因是 SpoiledTilePercentTotal  | Boolean  | 如果应用程序共享流被分类为基于以下所列的总指标阈值的损坏，则为 True：[在 "通话质量" 仪表板中流分类](stream-classification-in-call-quality-dashboard.md)。 对于非应用程序共享流，将始终为 False。   | &bull;终结点未报告此数据  <br/>&bull;流不是应用程序共享流。  |
| 应用共享较差，原因是 RelativeOneWayAverage  | Boolean  | 如果应用程序共享流被分类为基于以下所列平均指标阈值的相对比较差，则为 True：[在 "通话质量" 仪表板中流分类](stream-classification-in-call-quality-dashboard.md)。 对于非应用程序共享流，将始终为 False。    | &bull;终结点未报告此数据  <br/>&bull;流不是应用程序共享流 |
| 应用共享较差，原因是 RDPTileProcessingLatencyAverage | Boolean  | 如果应用程序共享流被分类为基于以下所列的 RDP 图块处理延迟平均指标阈值，则为 True：[在 "通话质量" 仪表板中流分类](stream-classification-in-call-quality-dashboard.md)。 对于非应用程序共享流，将始终为 False。    | &bull;终结点未报告此数据  <br/>&bull;流不是应用程序共享流 |
| Audio Poor Due To Jitter  | Boolean  | 如果音频流根据此处列出的抖动标准阈值归类为差，则为 True：[在 "通话质量" 仪表板中流分类](stream-classification-in-call-quality-dashboard.md)。 对于非音频流，将始终为 False。    | &bull;终结点未报告此数据 <br/>&bull;流不是音频共享流 |
| Audio Poor Due To RoundTrip  | Boolean  | 如果音频流根据此处列出的往返行程指标阈值归类为差，则为 True：[在 "通话质量" 仪表板中流分类](stream-classification-in-call-quality-dashboard.md)。 对于非音频流，将始终为 False。   | &bull;终结点未报告此数据 <br/>&bull;流不是音频共享流 |
| Audio Poor Due To Packet Loss  | Boolean  | 如果音频流根据此处列出的 "数据包丢失指标" 阈值归类为差，则为 True：[在 "通话质量" 仪表板中流分类](stream-classification-in-call-quality-dashboard.md)。 对于非音频流，将始终为 False。    | &bull;终结点未报告此数据 <br/>&bull;流不是音频共享流 |
| Audio Poor Due To Degradation  | Boolean  | 如果音频流根据此处列出的降级指标阈值归类为差，则为 True：[在 "通话质量" 仪表板中流分类](stream-classification-in-call-quality-dashboard.md)。 对于非音频流，将始终为 False。    | &bull;终结点未报告此数据 <br/>&bull;流不是音频共享流 |
| Audio Poor Due To Concealed Ratio  | Boolean  | 如果音频流根据此处列出的隐藏比率指标进行归类为差，则为 True：[在 "通话质量" 仪表板中流式分类](stream-classification-in-call-quality-dashboard.md)。 对于非音频流，将始终为 False。    | &bull;终结点未报告此数据 <br/>&bull;流不是音频共享流 |
| Poor Reason  | 标志 <br/>**可能的值：** <br/>&bull;隐藏比率 <br/>&bull;有所 <br/>&bull;抖动 <br/>&bull;数据包丢失 <br/>&bull;往返行程 <br/> Video Frame Rate Avg <br/> Video Local Frame Loss Percentage Avg <br/>&bull;视频文章 FEC PLR 后 <br/>&bull;RDP 磁贴处理延迟平均 <br/>&bull;相对单向平均 <br/>&bull;损坏磁贴百分比总计 | 用于确定为何将流分类为差的一系列标志。 由于将流分类为差的原因有很多，因此可能会有设置多个标记。 有关详细信息，请参阅[通话质量仪表板中的流分类](stream-classification-in-call-quality-dashboard.md)。  | &bull;流未分类为不良 |
| Poor  | Boolean  | 如果流具有足够的数据可分类为正常或较差，并且流分类为较差，则为 True。 否则为 False。   |   |
| Good  | Boolean  | 如果流具有足够的数据可分类为良好或较差，并且流分类为良好，则为 True。 否则为 False。   |   |
| Unclassified  | Boolean  | 如果流有足够的数据被分类为好或较差，则为 False。 否则为 True。 <br/>**示例值：** 1 |   |
| 百分之一丢包  | Boolean  | 如果数据包丢失超过1%，则为 True，否则为 False。  |   |
|**分级**|||
| First Feedback Rating  | 用户评级 (1-5)  | 第一终结点对与流关联的通话进行的评级，等级为 1-5（5 = 很好）。0 表示向用户显示了通话评级调查，但用户没有对其体验进行评级。<br/> **示例值：** 5 | &bull;未向第一个终结点显示任何调查  |
| Second Feedback Rating  | 用户评级 (1-5)  | 第二终结点对与流关联的通话进行的评级，等级为 1-5（5 = 很好）。0 表示向用户显示了通话评级调查，但用户没有对其体验进行评级。<br/> **示例值：** 5 | &bull;未向第二终结点显示任何调查   |
| First Feedback Tokens  | String  | 包含带有 boolean 标志的反馈令牌列表的字符串，指示令牌是否由用户通过第一个终结点提供反馈。 <br/> **示例值：** {DistortedSpeech： 1;ElectronicFeedback： 1;BackgroundNoise： 1;MuffledSpeech： 1;回音： 1;}  | &bull;第一个终结点的用户未提供任何反馈  |
| Second Feedback Tokens  | 字符串  | 包含带有 boolean 标志的反馈令牌列表的字符串，指示令牌是否由用户通过第二终结点提供反馈。 <br/> **示例值：** {DistortedSpeech： 1;ElectronicFeedback： 1;BackgroundNoise： 1;MuffledSpeech： 1;回音： 1;}  | &bull;第二终结点的用户未提供任何反馈  |
| First Feedback Has Audio Issue  | 布尔值  | 如果第一终结点的反馈标记指出流包含音频问题，则为 True，否则为 False。   |  |
| Second Feedback Has Audio Issue  | Boolean  | 如果第二终结点的反馈标记指示流有音频问题，则为 True，否则为 False。    ||
| First Feedback Has Video Issue  | Boolean  | 如果第一终结点的反馈标记指示流有视频问题，则为 True，否则为 False。    | |
| Second Feedback Has Video Issue  | 布尔值  | 如果第二终结点的反馈标记指示流有视频问题，则为 True，否则为 False。    | |
| 第一反馈有应用共享问题  | Boolean  | 如果第一终结点的反馈标记指示流存在应用共享问题，则为 True。 否则为 False。 | |  
| 第二反馈有应用共享问题  | Boolean  | 如果第二终结点的反馈标记指示流存在应用共享问题，则为 True。 否则为 False。 | |  
|**音频信号**|||
| First Echo Event Causes  | 标志  | 指示第一终结点上发生设备回声事件的原因的标志。一个流可能拥有多个标志。标志包括：<br/> BAD_TIMESTAMP - 从所使用的具有较差质量的捕获设备或呈现设备上获得的音频时间戳 <br/> POSTAEC_ECHO - 消除回声后仍具有较高水平的回声 <br/> MIC_CLIPPING - 拥有最大信号强度显著实例的捕获设备上的信号强度 <br/> EVENT_ANLP - 包含高噪音的捕获设备上的音频采样。 <br/> **示例值：** BAD_TIMESTAMP | &bull;这是非音频流 <br/>&bull;第一个终结点未报告任何事件原因  |
| Second Echo Event Causes  | 标志  | 指示第二终结点上发生设备回声事件的原因的标志。一个流可能拥有多个标志。标志包括：<br/> BAD_TIMESTAMP - 从所使用的具有较差质量的捕获设备或呈现设备上获得的音频时间戳 <br/> POSTAEC_ECHO - 消除回声后仍具有较高水平的回声 <br/> MIC_CLIPPING - 拥有最大信号强度显著实例的捕获设备上的信号强度 <br/> EVENT_ANLP - 包含高噪音的捕获设备上的音频采样。 <br/> **示例值：** BAD_TIMESTAMP   | &bull;这是非音频流 <br/>&bull;第一个终结点未报告任何事件原因 |
| First Echo Percent Mic In  | 范围（百分比）  | 在消除回声之前，第一终结点从捕获设备或麦克风设备检测到音频中存在回声的时间百分比。值按范围分组表示。<br/> **示例值：** 068： [5-10）  | &bull;这是非音频流 <br/>&bull;第一个终结点未报告数据 |
| Second Echo Percent Mic In  | 范围（百分比）  | 在消除回声之前，第二终结点从捕获设备或麦克风设备检测到音频中存在回声的时间百分比。值按范围分组表示。<br/> **示例值：** 068： [5-10） | &bull;指示非音频流 <br/>&bull;第二终结点未报告数据 |
| First Echo Percent Send  | 范围（百分比）  | 第一个终结点取消回声后在音频中检测到回显的时间百分比。 值按范围分组表示。 <br/> **示例值：** 068： [5-10）  | &bull;这是非音频流 <br/>&bull;第一个终结点未报告数据 |
| Second Echo Percent Send  | 范围（百分比）  | 在第二个终结点进行回声取消后，在音频中检测到回显的时间百分比。 值按范围分组表示。 <br/> **示例值：** 068： [5-10） | &bull;指示非音频流 <br/>&bull;第二终结点未报告数据 |
| First Send Signal Level  | 范围（dB、分贝）  | 对于被分类为单声道语音或左声道立体声语音的音频，第一终结点发送的音频的平均能量水平。值按范围分组表示。<br/> **示例值：** 055： [-15--10） | &bull;这是非音频流 <br/>&bull;第一个终结点未报告数据 |
| Second Send Signal Level  | 范围（dB、分贝）  | 对于被分类为单声道语音或左声道立体声语音的音频，第二终结点发送的音频的平均能量水平。值按范围分组表示。<br/> **示例值：** 055： [-15--10） | &bull;指示非音频流 <br/>&bull;第二终结点未报告数据  |
| 第一次收到的信号级别  | 范围（dB、分贝）  | 对于被分类为单声道语音或左声道立体声语音的音频，第一终结点接收的音频的平均能量水平。值按范围分组表示。<br/> **示例值：** 056： [-10--5）  | &bull;这是非音频流 <br/>&bull;第一个终结点未报告数据 |
| 第二次收到的信号级别  | 范围（dB、分贝）  | 对于被分类为单声道语音或左声道立体声语音的音频，第二终结点接收的音频的平均能量水平。值按范围分组表示。<br/> **示例值：** 056： [-10--5） | &bull;指示非音频流 <br/>&bull;第二终结点未报告数据  |
| First Send Noise Level  | 范围（dB、分贝）  | 将音频分类为单声道噪音或由第一个终结点发送的立体声左声道噪音的平均能源水平。 值按范围分组表示。 <br/> **示例值：** 048： [-50--45）  | &bull;这是非音频流 <br/>&bull;第一个终结点未报告数据 |
| Second Send Noise Level  | 范围（dB、分贝）  | 将音频分类为单声道噪音或第二终结点的立体声左声道噪音的平均能源水平。 值按范围分组表示。 <br/> **示例值：** 048： [-50--45）  | &bull;指示非音频流 <br/>&bull;第二终结点未报告数据 |
| 第一次收到的噪声级别  | 范围（dB、分贝）  | 第一个终结点收到的单声道噪音或立体声左声道噪音的平均能量级别。 值按范围分组表示。 <br/> **示例值：** 048： [-50--45）  | &bull;这是非音频流 <br/>&bull;第一个终结点未报告数据 |
| 第二已接收噪音级别  | 范围（dB、分贝）  | 第二终结点收到的单声道噪音或立体声左声道噪音的平均能量级别。 值按范围分组表示。 <br/> **示例值：** 048： [-50--45）  | &bull;指示非音频流 <br/>&bull;第二终结点未报告数据 |
|第一初始信号级别 RMS | 范围（dB、分贝） | 第一次终结点调用的前30秒的接收信号的根平均值-平方（RMS）。 请参阅[2.2.1.28.1 子元素](https://docs.microsoft.com/openspecs/office_protocols/ms-qoe/3c78f383-73fe-49f6-89cb-614e7aa8b2e7)  | |
| 第二初始信号级别 RMS |范围（dB、分贝） | 第二终结点呼叫的前30秒内收到的信号的根平均值-平方（RMS）。 有关详细信息，请参阅[2.2.1.28.1 子元素](https://docs.microsoft.com/openspecs/office_protocols/ms-qoe/3c78f383-73fe-49f6-89cb-614e7aa8b2e7)。||
| 第一 RxAGC 信号级别 |范围（dB、分贝）| 在第一个入站音频流的自动增益控制（AGC）处收到的信号级别。| |
| 第二 RxAGC 信号级别 |范围（dB、分贝）|在第二个入站音频流的自动增益控制（AGC）处收到的信号级别。|| 
| 第一 RxAGC 噪音级别|范围（dB、分贝）|在第一个入站音频流的自动增益控制（AGC）处收到的噪音级别。 ||
| 第二 RxAGC 噪音级别|范围（dB、分贝）|在第二个入站音频流的自动增益控件（AGC）上收到的噪音级别。||
| 第一呈现环回信号级别 |范围（dB、分贝）| 第一个入站音频流的环回信号级别。 ||
| 第二呈现环回信号级别 |范围（dB、分贝）|第二个入站音频流的环回信号级别。||
|**客户端事件** |||
| First Network Send Quality Event Ratio  | 范围（比率）  | 满足以下条件的通话的比率（小数）：第一终结点检测到网络导致已发送音频的质量差。值按范围分组表示。<br/> **示例值：** 015： [0.01-0.02）   | &bull;指示非音频流 <br/>&bull;第一个终结点未报告数据|
| Second Network Send Quality Event Ratio  | 范围（比率）  | 满足以下条件的通话的比率（小数）：第二终结点检测到网络导致已发送音频的质量差。值按范围分组表示。<br/> **示例值：** 015： [0.01-0.02）  | &bull;指示非音频流 <br/>&bull;第二终结点未报告数据 |
| First Network Receive Quality Event Ratio  | 范围（比率）  | 满足以下条件的通话的比率（小数）：第一终结点检测到网络导致已接收音频的质量差。值按范围分组表示。<br/> **示例值：** 015： [0.01-0.02）  | &bull;这是非音频流 <br/>&bull;第一个终结点未报告数据 |
| Second Network Receive Quality Event Ratio  | 范围（比率）  | 满足以下条件的通话的比率（小数）：第二终结点检测到网络导致已接收音频的质量差。值按范围分组表示。<br/> **示例值：** 015： [0.01-0.02）  | &bull;指示非音频流 <br/>&bull;第二终结点未报告数据 |
| First CPU Insufficient Event Ratio  | 范围（比率）  | 满足以下条件的通话的比率（小数）：第一终结点检测到可用 CPU 资源不足并导致已发送和已接收音频的质量差。值按范围分组表示。<br/> **示例值：** 016： [0.02-0.03）  | &bull;指示非音频流 <br/>&bull;第一个终结点未报告数据 |
| Second CPU Insufficient Event Ratio  | 范围（比率）  | 满足以下条件的通话的比率（小数）：第二终结点检测到可用 CPU 资源不足并导致已发送和已接收音频的质量差。值按范围分组表示。<br/> **示例值：** 016： [0.02-0.03）  | &bull;指示非音频流 <br/>&bull;第二终结点未报告数据 |
| First Device Half Duplex AEC Event Ratio  | 范围（比率）  | 第一个终结点检测到的问题，并以半双工模式运行声音回声 canceler，这会影响具有实时双向通信的能力。 值按范围分组表示。 <br/> **示例值：** 016： [0.02-0.03）  | &bull;这是非音频流 <br/>&bull;第一个终结点未报告数据 |
| Second Device Half Duplex AEC Event Ratio  | 范围（比率）  | 第二终结点检测出的问题和以半双工模式操作的声音回声 canceler 的一小部分，这会影响具有实时双向通信的能力。 值按范围分组表示。 <br/> **示例值：** 016： [0.02-0.03） | &bull;指示非音频流 <br/>&bull;第二终结点未报告数据  |
| First Device Render Not Functioning Event Ratio  | 范围（比率）  | 满足以下条件的通话的比率（小数）：第一终结点检测到呈现设备未正常工作。值按范围分组表示。<br/> **示例值：** 016： [0.02-0.03） | &bull;这是非音频流 <br/>&bull;第一个终结点未报告数据  |
| Second Device Render Not Functioning Event Ratio  | 范围（比率）  | 满足以下条件的通话的比率（小数）：第二终结点检测到呈现设备未正常工作。值按范围分组表示。<br/> **示例值：** 016： [0.02-0.03）  | &bull;指示非音频流 <br/>&bull;第二终结点未报告数据 |
| First Device Capture Not Functioning Event Ratio  | 范围（比率）  | 满足以下条件的通话的比率（小数）：第一终结点检测到捕获设备未正常工作。值按范围分组表示。<br/> **示例值：** 016： [0.02-0.03） | &bull;这是非音频流 <br/>&bull;第一个终结点未报告数据  |
| Second Device Capture Not Functioning Event Ratio  | 范围（比率）  | 满足以下条件的通话的比率（小数）：第二终结点检测到捕获设备未正常工作。值按范围分组表示。<br/> **示例值：** 016： [0.02-0.03）  | &bull;指示非音频流 <br/>&bull;第二终结点未报告数据 |
| First Device Glitches Event Ratio  | 范围（比率）  | 第一个终结点被检测为导致发送或接收音频质量不佳的问题或间隙的一小部分调用。 值按范围分组表示。 <br/> **示例值：** 016： [0.02-0.03） | &bull;这是非音频流 <br/>&bull;第一个终结点未报告数据  |
| Second Device Glitches Event Ratio  | 范围（比率）  | 第二终结点在音频中检测到导致发送或接收音频质量不佳的问题或间隙的一小部分调用。 值按范围分组表示。 <br/> **示例值：** 016： [0.02-0.03） | &bull;指示非音频流 <br/>&bull;第二终结点未报告数据  |
| First Device Low SNR Event Ratio  | 范围（比率）  | 满足以下条件的通话的比率（小数）：第一终结点检测到语音降低到噪音级别，导致发送的音频质量差。值按范围分组表示。<br/> **示例值：** 016： [0.02-0.03） | &bull;指示非音频流 <br/>&bull;第一个终结点未报告数据  |
| Second Device Low SNR Event Ratio  | 范围（比率）  | 满足以下条件的通话的比率（小数）：第二终结点检测到语音降低到噪音级别，导致发送的音频质量差。值按范围分组表示。<br/> **示例值：** 016： [0.02-0.03） | &bull;指示非音频流 <br/>&bull;第二终结点未报告数据  |
| First Device Low Speech Level Event Ratio  | 范围（比率）  | 满足以下条件的通话的比率（小数）：第一终结点检测到语音级别降低，导致发送的音频质量差。值按范围分组表示。<br/> **示例值：** 016： [0.02-0.03）  | &bull;这是非音频流 <br/>&bull;第一个终结点未报告数据 |
| Second Device Low Speech Level Event Ratio  | 范围（比率）  | 满足以下条件的通话的比率（小数）：第二终结点检测到语音级别降低，导致发送的音频质量差。值按范围分组表示。<br/> **示例值：** 016： [0.02-0.03） | &bull;指示非音频流 <br/>&bull;第二终结点未报告数据  |
| First Device Clipping Event Ratio  | 范围（比率）  | 满足以下条件的通话的比率（小数）：第一终结点检测到捕获的音频中存在削波现象，导致发送的音频质量差。值按范围分组表示。<br/> **示例值：** 016： [0.02-0.03） | &bull;指示非音频流 <br/>&bull;第一个终结点未报告数据  |
| Second Device Clipping Event Ratio  | 范围（比率）  | 满足以下条件的通话的比率（小数）：第二终结点检测到捕获的音频中存在削波现象，导致发送的音频质量差。值按范围分组表示。<br/> **示例值：** 016： [0.02-0.03）  | &bull;指示非音频流 <br/>&bull;第二终结点未报告数据 |
| First Device Echo Event Ratio  | 范围（比率）  | 满足以下条件的通话的比率（小数）：第一终结点检测到回声，导致发送的音频质量差。值按范围分组表示。<br/> **示例值：** 016： [0.02-0.03）  | &bull;这是非音频流 <br/>&bull;第一个终结点未报告数据 |
| Second Device Echo Event Ratio  | 范围（比率）  | 满足以下条件的通话的比率（小数）：第二终结点检测到回声，导致发送的音频质量差。值按范围分组表示。<br/> **示例值：** 016： [0.02-0.03）  | &bull;指示非音频流 <br/>&bull;第二终结点未报告数据 |
| First Device Near End To Echo Ratio Event Ratio | 范围（比率）| 调用的一小部分，第一个终结点检测到对导致质量较差的回声的接近结束信号的比率。 值按范围分组表示。 <br/> **示例值：** 016： [0.02-0.03） | &bull;这是非音频流 <br/>&bull;第一个终结点未报告数据|
| Second Device Near End To Echo Ratio Event Ratio  | 范围（比率）  | 调用的一小部分，即第二个终结点检测到与导致质量较差的回音级别的接近结束信号的比率。 值按范围分组表示。 <br/> **示例值：** 016： [0.02-0.03）  | &bull;指示非音频流 <br/>&bull;第二终结点未报告数据 |
| First Device Render Zero Volume Event Ratio  | 范围（比率）  | 满足以下条件的通话的比率（小数）：第一终结点检测到设备呈现音量设置为 0。值按范围分组表示。<br/> **示例值：** 016： [0.02-0.03） | &bull;这是非音频流 <br/>&bull;第一个终结点未报告数据 |
| Second Device Render Zero Volume Event Ratio  | 范围（比率）  | 满足以下条件的通话的比率（小数）：第二终结点检测到设备呈现音量设置为 0。值按范围分组表示。<br/> **示例值：** 016： [0.02-0.03） | &bull;指示非音频流 <br/>&bull;第二终结点未报告数据  |
| First Device Render Mute Event Ratio  | 范围（比率）  | 满足以下条件的通话的比率（小数）：第一终结点检测到设备呈现被静音。值按范围分组表示。<br/> **示例值：** 016： [0.02-0.03）   | &bull;这是非音频流 <br/>&bull;第一个终结点未报告数据 |
| Second Device Render Mute Event Ratio  | 范围（比率）  | 满足以下条件的通话的比率（小数）：第二终结点检测到设备呈现被静音。值按范围分组表示。<br/> **示例值：** 016： [0.02-0.03） | &bull;指示非音频流 <br/>&bull;第二终结点未报告数据  |
| First Device Multiple Endpoints Event Count  | 范围（比率）  | 通话期间，第一终结点检测到同一房间或声音环境中存到多个终结点的次数。值按范围分组表示。<br/> **示例值：** 016： [0.02-0.03）  | &bull;这是非音频流 <br/>&bull;第一个终结点未报告数据 |
| Second Device Multiple Endpoints Event Count  | 范围（比率）  | 通话期间，第二终结点检测到同一房间或声音环境中存到多个终结点的次数。值按范围分组表示。<br/> **示例值：** 016： [0.02-0.03）  | &bull;指示非音频流 <br/>&bull;第二终结点未报告数据 |
| First Device Howling Event Count  | 范围（比率）  | 调用期间第一个终结点在同一房间内检测到的两个或更多终结点的次数，这些终结点在啸声或 screeching 音频形式导致质量较差的音频。 值按范围分组表示。 <br/> **示例值：** 016： [0.02-0.03）  | &bull;这是非音频流 <br/>&bull;第一个终结点未报告数据 |
| Second Device Howling Event Count  | 范围（比率）  | 通话期间，第二终结点检测到同一房间或声音环境中存到两个或更多个终结点并因此导致存在啸声或尖叫声的差质量音频的次数。值按范围分组表示。<br/> **示例值：** 016： [0.02-0.03）  | &bull;指示非音频流 <br/>&bull;第二终结点未报告数据 |
|**呼叫诊断**|||
| Error Report Sender  | String  | 指示发送流的通话错误报告的终结点。此报告包含额外的遥测并可能指出通话中的通话设置或断线问题。<br/> **示例值：** 条 | &bull;指示未发送呼叫错误报告。  |
| Is Media Error  | String  | 指示为流报告的通话错误是否为媒体级错误。此报告包含额外的遥测并可能指出通话中的通话设置或断线问题。    | &bull;指示未发送呼叫错误报告。 |
| Media Failure Type  | 枚举 <br/>**可能的值：** <br/>&bull;Midcall <br/>&bull;CallSetup <br/>&bull;NotMediaFailure. | 与流关联的媒体故障的类型。   | &bull;指示未发送呼叫错误报告。   |
| 通话分类| 枚举 |分配给呼叫的可靠性分类。 **可能的值**：成功、失败、ClassificationUnavailable | |
| 分类原因|String|分类已分配给流的原因。| |
| 测试呼叫类型|枚举|指示此调用是常规调用还是测试调用。 如果是测试调用，则指示测试调用的类型。 <br/>**可能的值：** NonTest、Silent、UserInitiated、合成 <br/>**在于** <br/> NonTest-常规通话 <br/> 无提示-无提示测试呼叫 <br/> UserInitiated-用户启动的测试呼叫 <br/>综合– ST 终结点启动的呼叫|
|**Session**|||
| RTP RTCP Mux  | Boolean  | True 表示在同一端口多路复用 RTP 和 RTCP。否则为 False。    | <br/>&bull;终结点未报告数据  |
| Stun Version  | 整型  | 建立通话所使用的 STUN 协议的版本。  | <br/>&bull;终结点未报告数据 <br/> **示例值：** 2  |
| Media Relay  | 字符串  | 用于会话的一个或多个媒体中继的 IP 地址。对于流，可能会报告一对中继，中间用"+"隔开。<br/> **示例值：**"13.107.8.2 + 13.107.8.2"  | &bull;终结点未报告此数据  |
| Is Anonymous Join Session  | 布尔值  | 如果用户匿名加入会议，则为 True，否则为 False。   | &bull;没有用于确定用户是否已匿名加入的数据   |
| 具有媒体诊断 Blob  | Boolean  | 如何会话具有媒体诊断数据，则为 True，否则为 False。   | &bull;未收集此流的某些信号数据   |
| Call Setup Failure Reason  | 枚举  | 通话未能建立媒体连接的原因分类。 <br/>**可能的值：** <br/> **缺少 FW Deep Packet "数据包检查" 规则**-指示路径上的网络设备可能阻止了由于较深数据包检查规则而无法建立媒体路径。 这可能是因为未正确配置代理或防火墙规则。 <br/> **缺少 FW IP 阻止免除规则**-指示路径上的网络设备可能阻止将媒体路径建立到 Office 365 网络。 这可能是因为未正确将代理或防火墙规则配置为允许访问用于 Skype for Business 流量的 IP 地址和端口。 <br/> **其他**-表示无法建立呼叫的媒体路径，但无法对根本原因进行分类。 <br/> 非媒体故障-指示未检测到建立媒体路径的问题。  | &bull;由于未知媒体问题，呼叫设置失败  |
|**DNS**|||
| 使用的 DNS 解析缓存  | 布尔值  | 如果终结点使用了 DNS 缓存来解析媒体中继地址，则为 True，否则为 False。    | <br/>&bull;终结点未报告此数据    |
|**UserData**| |||
| 第一个用户 ObjectId|String|第一个终结点的用户的 Active Directory 对象 ID。 仅对过去30天的数据可用，并且仅对具有允许 EUII 访问权限的用户可见。  | |
| 第二用户 ObjectId|String|第二终结点的用户的 Active Directory 对象 ID。 仅对过去30天的数据可用，并且仅对具有允许 EUII 访问权限的用户可见。 | |
| 第一个 MAC 地址|String|第一个终结点的网络设备的媒体访问控制（MAC）地址。 仅对过去30天的数据可用，并且仅对具有允许 EUII 访问权限的用户可见。| |
| 第二个 MAC 地址|String|第二终结点的网络设备的媒体访问控制（MAC）地址。 仅对过去30天的数据可用，并且仅对具有允许 EUII 访问权限的用户可见。| |
| 第一个 Sip Uri|String|第一个终结点的用户的会话初始协议（SIP） URI。 仅填充 Skype for Business 终结点。 仅对过去30天的数据可用，并且仅对具有允许 EUII 访问权限的用户可见。|
| 第二 Sip Uri|String|第一个终结点的用户的 SIP URI。 仅填充 Skype for Business 终结点。 仅对过去30天的数据可用，并且仅对具有允许 EUII 访问权限的用户可见。|
| 第一个电话号码|String|第一个终结点的用户的电话号码。 仅针对 PSTN 终结点进行填充。 仅对过去30天的数据可用，并且仅对具有允许 EUII 访问权限的用户可见。|
| 第二个电话号码|String|第二终结点的用户的电话号码。 仅针对 PSTN 终结点进行填充。 仅对过去30天的数据可用，并且仅对具有允许 EUII 访问权限的用户可见。|
| 第一个 UPN|String|第一个终结点的用户的用户主体名称（UPN）。 仅对过去30天的数据可用，并且仅对具有允许 EUII 访问权限的用户可见。|
| 第二 UPN|String|第二终结点的用户的用户主体名称（UPN）。 仅对过去30天的数据可用，并且仅对具有允许 EUII 访问权限的用户可见。|
| 第一反馈文本|String|在呼叫结束时由第一个终结点的用户提供的逐字反馈文本（如果有）。 仅对过去30天的数据可用，并且仅对具有允许 EUII 访问权限的用户可见。 | |
| 第二反馈文本|String| 在呼叫结束时由第二终结点的用户提供的逐字反馈文本（如有）。 仅对过去30天的数据可用，并且仅对具有允许 EUII 访问权限的用户可见。|
| 第一个客户端终结点名称|String|第一个终结点的计算机名称。 仅对过去30天的数据可用，并且仅对具有允许 EUII 访问权限的用户可见。|
| 第二客户端终结点名称|String|第二终结点的计算机名称。 仅对过去30天的数据可用，并且仅对具有允许 EUII 访问权限的用户可见。|
| 第一个终结点产品名称|String|第一个终结点（Skype for Business 或 Microsoft 团队）的产品名称。|
| 第二终结点产品名称|String|第二终结点（Skype for business 或 Microsoft 团队）的产品名称。|
| 第一个 UserType|枚举字符串|第一个终结点上的用户类型。 <br/> **可能的值：** 用户、服务器、匿名、应用程序、PSTN、语音邮件、未知 <br/> <br/>**未知**-如果无法根据收到的信息确定 UserType，则为默认值。 <br/>**Pstn** -pstn 用户。 <br/>**匿名**-团队用户或 Skype for business 访问者。 <br/>**应用程序**-一个 bot。 <br/>**用户**-AAD 用户可以是 Skype For business 用户或团队用户。 <br/>**服务器**-对于会议，至少一方是服务器。 <br/>**语音邮件**-终结点由语音邮件服务应答。||
| 第二 UserType|枚举字符串|第二终结点上的用户类型。 <br/> **可能的值：** 用户、服务器、匿名、应用程序、PSTN、语音邮件、未知 <br/> <br/>**未知**-如果无法根据收到的信息确定 UserType，则为默认值。 <br/>**Pstn** -pstn 用户。 <br/>**匿名**-团队用户或 Skype for business 访问者。 <br/>**应用程序**-一个 bot。 <br/>**用户**-AAD 用户可以是 Skype For business 用户或团队用户。 <br/>**服务器**-对于会议，至少一方是 "服务器"。 <br/>**语音邮件**-终结点由语音邮件服务应答。||
|**Datapair**|||
| Network Connection Detail Pair  | 枚举对 <br/>**可能的值：** <br/> wifi : wifi <br/> wifi : 有线 <br/> 有线 : wifi <br/> 有线 : 有线 <br/> MobileBB : MobileBB <br/> MobileBB : 其他 <br/> MobileBB : 隧道 <br/> MobileBB : wifi <br/> MobileBB : 有线 <br/> 其他 : 其他 <br/> 其他 : wifi <br/> 其他 : 有线 <br/> 隧道 : 隧道 <br/> 隧道 : wifi <br/> 隧道 : 有线 <br/> : MobileBB <br/> : 其他 <br/> : 隧道 <br/> : wifi <br/> : 有线 <br/> :  | 表示第一和第二终结点的网络连接详情的成对值。  | &bull;终结点网络连接类型未知。 当无法建立通话时可能会出现这种情况。   |
| User Agent Category Pair  | 枚举对  | 表示第一和第二终结点的用户代理类别的成对值。 <br/> **示例值：** AV-MCU： OC  | &bull;终结点用户代理不是已知类型  |
| Is Server Pair  | 枚举对 <br/>**可能的值：** 客户端：客户端 <br/> 客户端：服务器 <br/> 服务器：服务器  | 表示第一和第二终结点是客户端还是服务器的成对值。  | 没有空值   |
| Connectivity Ice Pair  | 枚举对 <br/>**可能的值：** <br/> 直接 : 直接 <br/> 直接 : 失败 <br/> 直接 : HTTP <br/> 失败 : 失败 <br/> 失败 : 中继 <br/> HTTP : 中继 <br/> : <br/> : 直接 <br/> : 失败 <br/> : HTTP <br/> : 中继 | 表示每个终结点使用的 ICE 连接类型的成对值。   | &bull;终结点使用的 ICE 连接未知或未报告   |
| OS Pair  | 枚举对  | 表示第一和第二终结点的操作系统名称和版本的成对值。 <br/> **示例值：** Windows 10： Windows 10  | &bull;无法解析操作系统名称或终结点未报告操作系统名称  |
| Tenant Id Pair  | 枚举对  | 表示第一和第二终结点的租户 ID 的成对值。 <br/> **示例值：** 00000000 （0000-0000-0000-000000000000: 00000000-0000-0000-0000）000000000000  |  &bull;无法确定租户标识符。 当终结点登录到了本地 Skype for Business Server 部署时可能会出现此情况。  |
| Building Name Pair  | 枚举对  | 表示第一和第二终结点的建筑物名称的成对值。  | &bull;无法确定终结点的建筑物名称。 这可能是因为终结点位于企业网络外部，或正在从没有子网映射的站点访问网络。 <br/> **示例值：** 主建筑物：分支网站构建 |
| Inside Corp Pair  | 枚举对 <br/>**可能的值：** <br/> 内部 : 内部 <br/> 内部 : 外部 <br/> 外部 : 外部 | 根据子网映射，显示终结点位于企业网络内部还是外部的成对值。   |   |
| Scenario Pair  | 枚举对  | 显示终结点位于企业网络内部还是外部（根据子网映射确定）以及网络连接详情的成对值。 <br/> **注意：** 对用 "--" 分隔。 <br/> **示例值：** 客户端内部-客户端内部-wifi  | &bull;两个终结点或这两个终结点的网络连接类型均未知。  |
|**PSTN**|||
|PSTN 呼叫结束原因（SIP 响应代码）|整形|一个三位数的整数响应代码显示了通话的最终状态。 <br/> 有关 SIP 说明的详细信息，请参阅[SIP 响应代码列表](https://www.wikipedia.org/wiki/List_of_SIP_response_codes)。 <br/>**示例：** 404||
|PSTN 中继 FQDN|String|FQDN 是会话边界控制器（SBC）的完全限定的域名（FQDN）。<br/>**示例：** sbcgw.contoso.com||
|PSTN 运营商名称|String|由监管机构授权的公司，用于运营电信系统。<br/>**示例：** Colt|直接路由没有运营商。 只有通话计划才有运营商。|
|PSTN 呼叫类型|String|此字符串结合服务类型和呼叫类型。<br/><br/>服务类型：<br/>用户 > 通话计划<br/>byot-> 直接路由<br/>会议 > 音频会议<br/>ucap-> 语音应用<br/>紧急 > 紧急号码<br/><br/>呼叫类型：<br/>> 入站通话<br/>传出呼叫 ><br/>Out_transfer > 出站呼叫转移给第三人<br/>Out_forward > 出站呼叫转移给第三人<br/>与临时 PSTN 参与者 Out_conf > 出站呼叫<br/><br/>**示例：** ByotIn||
|PSTN 连接类型|String|PSTN 连接类型包括直接路由、呼叫计划或音频会议。 此时，只有直接路由才可在通话质量仪表板（CQD）中使用。<br/>**示例：** 直接路由||
|PSTN 最终 SIP 代码短语|String|与 SIP 响应代码和 Microsoft 响应代码对应的 "原因短语"。<br/>**示例：** 再见||
|PSTN 呼叫结束子原因|整形|从 Microsoft 组件发出的指示所发生特定操作的响应代码。<br/>**示例：** 540000||
|PSTN 事件类型|String|提供遥测的事件类型。<br/>**示例：** 成品||
|PSTN 事件信息时间|日期|当出站呼叫从 Microsoft 网络开始或入站通话到达 Microsoft 网络时的 UTC 格式的时间。<br/>**示例：** 2020-02-06 20：57：53.1750000||
|PSTN MP 位置|String|在非绕过模式下，媒体处理器位置将显示媒体路径。<br/>**示例：** USWE||
|第一个 PSTN 国家区域|String|如果 FirstIsCaller 为 true，则第一个 PSTN 国家地区是呼叫方的国家/地区。 如果为 false，则第二个 PSTN 国家/地区是呼叫方的国家/地区。<br/>**示例：** 我们||
|抖动|毫秒|RTP 数据包的到达时间变体。 有关详细信息，请参阅[通话质量仪表板中的流分类](stream-classification-in-call-quality-dashboard.md)。<br/>**示例：** 5.982||
|Packet Loss Rate|百分比|中介服务器与 SBC 或网关之间的流的百分比（如果可用）。 有关详细信息，请参阅[通话质量仪表板中的流分类](stream-classification-in-call-quality-dashboard.md)。<br/>**示例：** 1.2%||
|延迟（往返行程时间）|毫秒|每个流的平均网络传播往返时间。 有关详细信息，请参阅[通话质量仪表板中的流分类](stream-classification-in-call-quality-dashboard.md)。<br/>**示例：** 3.49||
||||

### <a name="notes-on-dimension-data-typeunits"></a>有关维度数据类型/单位的注释

#### <a name="boolean"></a>Boolean

布尔值始终为 True 或 False。 在某些情况下，True 还可以表示为1，False 可以表示为0。

#### <a name="range"></a>范围

按范围或分组表示的维度值使用以下格式显示：

 _\<排序顺序字符串\> [\<下限非\> - \<独占上限\>_

例如，持续时间（分钟）维度表示以分钟为单位的通话持续时间，报告的值以取值范围的形式表示。

|Duration (Minutes) |解释方法 |
|:--- |:--- |
|062: [0 - 0) |流持续时间 = 0 分钟 |
|064: [1 - 2) |1 分钟 < = 流持续时间 < 2 分钟 |
|065: [2 - 3) |2 分钟 < = 流持续时间 < 3 分钟 |
|066： [3 –4） |3 分钟 < = 流持续时间 < 4 分钟 |
|  | |

\<排序顺序字符串> 用于在呈现数据时控制排序顺序，并且可用于筛选。 For example, a filter on Duration (Minutes) < "065", would show streams with duration less than 2 minutes (The leading '0' is needed for the filter to work as expected).

> [!NOTE]
> [!注释] 排序字符串的实际值并不重要。

#### <a name="enumeration-strings"></a>枚举字符串

CQD 使用的字符串通常派生自数据文件，它们几乎可以是允许长度内的任何字符组合。 某些维度看起来像是字符串，但由于它们只能是预定义值的简短列表之一，因此它们是枚举而不是真正的字符串。 某些枚举字符串也会成对使用。

#### <a name="enumeration-pair"></a>枚举对

按枚举对表示的维度使用以下格式显示：

 _\<一个终结点的枚举值\> ： \<来自其他终结点的枚举值\>_

枚举值的顺序一致，但此顺序不反映第一或第二终结点的顺序。

例如，网络连接详情对显示两个终结点的网络连接详情值：

|Network Connection Detail Pair |解释方法 |
|:--- |:--- |
|有线 : 有线 |第一和第二终结点均使用有线以太网连接。 |
|有线 : wifi |第一个终结点使用有线以太网连接且第二个终结点使用 Wi-Fi 连接，或第二个终结点使用有线以太网连接且第一个终结点使用 Wi-Fi 连接。 |
|: wifi |第一个终结点使用 WiFi 连接且第二个终结点使用的网络连接未知，或第二个终结点使用 WiFi 连接且第一个终结点使用的网络连接未知。 |
| | |

#### <a name="blank-values"></a>空值

上表列出了维度可能出现空值的原因。 如果 QoE 记录的可用维度为 false，则许多维度和度量值将为空。 这通常出现在通话未能成功建立的情况下。

## <a name="measurements"></a>计量

许多度量值也可以用作筛选器。 下表列出了 CQD 中当前可用的度量值，按查询编辑器中列出的顺序显示：

|衡量指标名称 |单位 |说明 |
|:--- |:--- |:--- |
|Total Stream Count |流的数量 |媒体流的数量，不区分媒体的类型。 |
| CDR 可用流计数总数 | 流的数量 |可用可靠性/诊断信息的媒体流的数量。 请参阅[Skype For Business 服务器中的呼叫详细记录（CDR）](https://docs.microsoft.com/skypeforbusiness/manage/health-and-monitoring/call-detail-recording-cdr) |
|Total Media Failed Stream Count |流的数量 |媒体路径未能建立或未正常终止的流的数量。 |
|Total Call Setup Failed Stream Count |流的数量 |呼叫之初无法在终结点之间建立媒体路径的流的数量。 |
|Total Call Dropped Stream Count |流的数量 |媒体路径未正常终止的流的数量。 |
|Total Media Succeeded Stream Count |流的数量 |媒体路径成功建立并正常终止的流的数量。 |
|Total Call Setup Succeeded Stream Count |流的数量 |呼叫之初在终结点之间成功建立媒体路径的流的数量。|
|Total Call Setup Failure Percentage |百分比 |呼叫之初无法在终结点之间建立媒体路径的所有流的百分比。 |
|Total Call Dropped Failure Percentage |百分比 |媒体路径未正常终止的已成功建立的数据流的百分比。 | 短通话总次数
|Total Answer Seizure Ratio |比率 |持续时间低于 5 秒钟的通话占通话总数的比率。 |
|Total Short Call Percentage |百分比 |长时间不超过1分钟的通话总次数的百分比。 |
|Total Media Failure Percentage |百分比 |媒体路径未能建立或未正常终止的所有流的百分比。 |
|Media Failed Due To Firewall DPI Stream Count |流的数量 |由于深度包检测不允许 Skype for Business 流量导致网络设备阻止访问进而未能建立的流的数量。 这些故障通常意味着未正确将代理、防火墙或其他网络安全设备配置为允许访问 Office 365 中的 Skype for Business 使用的 IP 地址和端口。 |
|Firewall DPI Media Failure Percentage |百分比 |由于深度包检测不允许 Skype for Business 流量导致网络设备阻止访问进而未能建立的流的百分比。 这些故障通常意味着未正确将代理、防火墙或其他网络安全设备配置为允许访问 Office 365 中的 Skype for Business 使用的 IP 地址和端口。 |
|Media Failed Due To Firewall IP Blocked Stream Count |流的数量 |由于网络设备阻止访问 Skype for Business 服务器而未能建立的流的数量。这些故障通常意味着未正确将代理、防火墙或其他网络安全设备配置为允许访问 Office 365 中的 Skype for Business 使用的 IP 地址和端口。 |
|Firewall IP Blocked Media Failure Percentage |百分比 |由于网络设备阻止访问 Skype for business 服务器而无法建立的数据流的百分比。 这些故障通常表示代理服务器、防火墙或其他网络安全设备未正确配置为访问 Office 365 中 Skype for Business 使用的 IP 地址和端口。 |
| 媒体因其他流计数而失败|流的数量| 由于不确定/未分类原因而无法在终结点之间建立媒体路径的流的数量。| |
| 其他媒体故障百分比|百分比| 由于不确定/未分类原因而无法在终结点之间建立媒体路径的流的百分比。 ||
| CDR 可用通话计数总数|流的数量|可用可靠性/诊断信息的媒体流总数。|
| 媒体总通话失败次数|流的数量|无法在终结点之间建立媒体路径的流的数量。|
|Audio Stream Count |流的数量 |音频流的数量。 |
|Audio Poor Stream Count |流的数量 |根据此处列出的网络指标被分类为差的音频流的数量：[在 "通话质量" 仪表板中进行流分类](stream-classification-in-call-quality-dashboard.md)。 |
 |Audio Good Stream Count |流的数量 |根据此处列出的网络指标被分类为好的音频流的数量：[在 "通话质量" 仪表板中进行流分类](stream-classification-in-call-quality-dashboard.md)。 |
|Audio Unclassified Stream Count |流的数量 |根据此处列出的网络指标，不具有足够数据分类的音频流的数量：在 "[通话质量" 仪表板中进行流分类](stream-classification-in-call-quality-dashboard.md)。 |
|Audio Poor Percentage |百分比 |根据此处列出的网络指标被分类为差的所有音频流的百分比：[在 "通话质量" 仪表板中流分类](stream-classification-in-call-quality-dashboard.md)。 |
|Audio OnePercent PacketLoss Count |流的数量 |丢包率大于 1% 的音频流的数量。 |
|Audio OnePercent PacketLoss Percentage |百分比 |丢包率大于 1% 的所有音频流的百分比。 |
|Audio Poor Due To Jitter Count |流的数量 |抖动指标超过以下所列阈值的音频流的数量：[在 "通话质量" 仪表板中进行流分类](stream-classification-in-call-quality-dashboard.md)。 |
|Audio Poor Due To PacketLoss Count |流的数量 |数据包丢失指标超过以下所列阈值的音频流的数量：[在通话质量仪表板中的流分类](stream-classification-in-call-quality-dashboard.md) |
|Audio Poor Due To Degradation Count |流的数量 |降级指标超过以下所列阈值的音频流的数量：[在 "通话质量" 仪表板中进行流分类](stream-classification-in-call-quality-dashboard.md)。 |
|Audio Poor Due To RoundTrip Count |流的数量 |往返行程超过以下所列阈值的音频流的数量：[在 "通话质量" 仪表板中进行流分类](stream-classification-in-call-quality-dashboard.md)。 |
|Audio Poor Due To ConcealedRatio Count |流的数量 |隐藏比率超过以下所列阈值的音频流的数量：[在 "通话质量" 仪表板中进行流分类](stream-classification-in-call-quality-dashboard.md)。 |
|Audio SLA Good Call Count |通话的数量 |Skype for Business 语音质量 SLA 范围内的音频呼叫数（[Microsoft 产品和联机服务的批量许可](https://aka.ms/voicequalitysla)）已分类为会议网络性能目标。 |
|Audio SLA Poor Call Count |通话的数量 |在 Skype for Business 语音质量 SLA 范围内的音频呼叫数（[Microsoft 产品和联机服务的批量许可](https://aka.ms/voicequalitysla)），分类为不满足网络性能目标。 |
|Audio SLA Call Count |通话的数量 |Skype for Business 语音质量 SLA 范围内的音频呼叫数（[Microsoft 产品和联机服务的批量许可](https://aka.ms/voicequalitysla)）。 |
|Audio SLA Good Call Percentage |百分比 |Skype for Business 语音质量 SLA（[Microsoft 产品和在线服务的批量许可](https://aka.ms/voicequalitysla)）范围内被分类为满足网络性能目标的音频通话的百分比。 |
|Audio Good Call Stream Count |流的数量 |在以下情况下，呼叫中的音频流（呼叫路）的音频流的数量不会根据网络指标被分类为差： "[通话质量" 仪表板中的流分类](stream-classification-in-call-quality-dashboard.md)。 |
|Audio Poor Call Stream Count |流的数量 |通话中至少有一个音频流的音频流的数量（呼叫条）根据此处列出的网络指标被分类为差：[在 "通话质量" 仪表板中进行流分类](stream-classification-in-call-quality-dashboard.md)。 |
|Audio Unclassified Call Stream Count |流的数量 |由于缺少网络指标，呼叫中的两个音频流（呼叫路）无法分类的音频流的数量。 |
|音频不太好通话级别百分比 |百分比 |在呼叫中至少有一个音频流的所有音频流的百分比（呼叫条）根据以下列出的网络指标被分类为差： "[通话质量" 仪表板中的流分类](stream-classification-in-call-quality-dashboard.md)。 |
| 音频呼叫计数 | 数字 |涉及音频的通话次数。| |
| 音频不佳通话计数|数字  |涉及音频分类为差的通话次数。|
| 音频完好通话计数 |通话的数量|涉及音频分类为良好的通话的次数。|
| 音频未分类通话计数 |通话的数量|涉及音频的通话次数无法进行保密或不太好的通话。|
| Audio Poor Call Percentage |通话百分比|涉及音频分类为差的通话百分比。|
|AppSharing Stream Count |流的数量 |基于 RDP 的应用程序共享流的数量。 |
|AppSharing Poor Due To SpoiledTilePercentTotal Count |流的数量 |损坏磁贴百分比总指标超过以下所列阈值的应用程序共享流的数量：[在 "通话质量" 仪表板中流分类](stream-classification-in-call-quality-dashboard.md)。 |
|AppSharing Poor Due To RelativeOneWayAverage Count |流的数量 |损坏磁贴百分比总指标超过以下所列阈值的应用程序共享流的数量：[在 "通话质量" 仪表板中流分类](stream-classification-in-call-quality-dashboard.md)。 |
|AppSharing Poor Due To RDPTileProcessingLatencyAverage Count |流的数量 |RDP 磁贴处理延迟平均超过以下所列阈值的应用程序共享流的数量：[在 "通话质量" 仪表板中流分类](stream-classification-in-call-quality-dashboard.md)。 |
|AppSharing Poor Stream Count |流的数量 |根据此处列出的网络指标被分类为差的应用程序共享流的数量：[在 "通话质量" 仪表板中进行流分类](stream-classification-in-call-quality-dashboard.md)。 |
|AppSharing Good Stream Count |流的数量 |根据下面列出的网络指标，归类为良好的应用程序共享流的数量：[在 "通话质量" 仪表板中进行流分类](stream-classification-in-call-quality-dashboard.md)。 |
|AppSharing Unclassified Stream Count |流的数量 |根据此处列出的网络指标，没有足够数据分类为良好或差的应用程序共享流的数量：在 "[通话质量" 仪表板中进行流分类](stream-classification-in-call-quality-dashboard.md)。 |
|AppSharing Poor Percentage |百分比 |根据下面列出的网络指标被分类为差的应用程序共享流的总百分比：[在 "通话质量" 仪表板中进行流分类](stream-classification-in-call-quality-dashboard.md)。 |
|Video Stream Count |流的数量 |视频流的数量。 |
|Video Poor Due To VideoPostFecplr Count |流的数量 |视频 Post Fec plr 后超过以下所列阈值的视频流的数量：[在 "通话质量" 仪表板中流分类](stream-classification-in-call-quality-dashboard.md)。 |
|Video Poor Due To VideoLocalFrameLossPercentageAvg Count |流的数量 |视频本地帧损失百分比平均超过以下所列阈值的视频流的数量：[在 "通话质量" 仪表板中流分类](stream-classification-in-call-quality-dashboard.md)。 |
|Video Poor Due To VideoFrameRateAvg Count |流的数量 |视频帧的平均速率超过以下所列阈值的视频流的数量：[在 "通话质量" 仪表板中进行流分类](stream-classification-in-call-quality-dashboard.md)。 |
|由于冻结计数而导致视频较差 |流的数量 | 视频冻结指标超过此处列出的阈值的主视频流的数量。 ["通话质量" 仪表板中的流分类](stream-classification-in-call-quality-dashboard.md)。 此字段仅特定于 Microsoft 团队 |
|Video Poor Stream Count |流的数量 |根据此处列出的网络指标被分类为差的视频流的数量。 "[呼叫质量" 仪表板中的 "流分类](stream-classification-in-call-quality-dashboard.md)"。 |
|Video Good Stream Count |流的数量 |根据此处列出的网络指标被分类为好的视频流的数量：[在 "通话质量" 仪表板中进行流分类](stream-classification-in-call-quality-dashboard.md)。 |
|Video Unclassified Stream Count |流的数量 |根据此处列出的网络指标，没有足够数据分类的视频流的数量：在 "[通话质量" 仪表板中进行流分类](stream-classification-in-call-quality-dashboard.md)。 |
|Video Poor Percentage|百分比 |根据此处列出的网络指标被分类为差的视频流总数的百分比。 "[呼叫质量" 仪表板中的 "流分类](stream-classification-in-call-quality-dashboard.md)"。 |
|由于冻结而导致视频较差的百分比|百分比 | 由于此处在 "[通话质量" 仪表板中](stream-classification-in-call-quality-dashboard.md)列出的冻结导致的 "视频不正常" 的主视频流的百分比（基于视频的冻结指标）。 此字段仅特定于 Microsoft 团队 |
|VBSS Stream Count |流的数量 |基于视频的屏幕共享流的数量。 |
|VBSS Poor Due To VideoPostFecplr Count |流的数量 |视频 Post Fec plr 后超过以下所列阈值的基于视频的屏幕共享流的数量：[在 "通话质量" 仪表板中进行流分类](stream-classification-in-call-quality-dashboard.md)。 |
|VBSS Poor Due To VideoLocalFrameLossPercentageAvg Count |流的数量 |视频本地帧损失百分比平均超过以下所列阈值的基于视频的屏幕共享流的数量：[在 "通话质量" 仪表板中进行流分类](stream-classification-in-call-quality-dashboard.md)。 |
|由于 VideoFrameRateAvg 计数，VBSS 较差 |流的数量 |视频帧速率超过以下所列阈值的基于视频的屏幕共享流的数量：[在 "通话质量" 仪表板中进行流分类](stream-classification-in-call-quality-dashboard.md)。 |
|VBSS Poor Stream Count |流的数量 |根据此处列出的网络指标被分类为差的基于视频的屏幕共享流的数量：[在 "通话质量" 仪表板中进行流分类](stream-classification-in-call-quality-dashboard.md)。 |
|VBSS Good Stream Count |流的数量 |基于以下内容的网络指标归类为良好的基于视频的屏幕共享流的数量：[在 "通话质量" 仪表板中进行流分类](stream-classification-in-call-quality-dashboard.md)。 |
|VBSS Unclassified Stream Count |流的数量 |由于此处列出的网络指标，基于视频的屏幕共享流的数量没有足够的数据分类为好或差：在 "[通话质量" 仪表板中进行流分类](stream-classification-in-call-quality-dashboard.md)。 |
|VBSS Poor Percentage |百分比 |根据以下列出的网络指标分类为差的所有基于视频的屏幕共享流的百分比：[在 "通话质量" 仪表板中进行流分类](stream-classification-in-call-quality-dashboard.md)。 |
|Avg Call Duration |秒 |流的平均持续时间，以秒为单位。 |
|First Feedback Rating Avg |用户评级 (1-5) |使用第一终结点的用户报告的流平均评级。通话评级分为 1-5 级，评级适用于通话的所有流。 |
|Second Feedback Rating Avg |用户评级 (1-5) |使用第二终结点的用户报告的流平均评级。通话评级分为 1-5 级，评级适用于通话的所有流。 |
|First Feedback Rating Count |被评级的流的数量 |使用第一终结点的用户进行了评级的流的数量。通话评级分为 1-5 级，评级适用于通话的所有流。 |
|Second Feedback Rating Count |被评级的流的数量 |使用第二终结点的用户进行了评级的流的数量。通话评级分为 1-5 级，评级适用于通话的所有流。 |
|First Feedback Rating Poor Count |被评级的流的数量 |被使用第一终结点的用户评级为 1 或 2 的流的数量。通话评级分为 1-5 级，评级适用于通话的所有流。 |
|Second Feedback Rating Poor Count |被评级的流的数量 |被使用第二终结点的用户评级为 1 或 2 的流的数量。通话评级分为 1-5 级，评级适用于通话的所有流。 |
|First Feedback Rating Poor Percentage |被评级的流的数量 |被使用第一终结点的用户评级为 1 或 2 的所有流的百分比。通话评级分为 1-5 级，评级适用于通话的所有流。 |
|Second Feedback Rating Poor Percentage |被评级的流的数量 |被使用第二终结点的用户评级为 1 或 2 的所有流的百分比。通话评级分为 1-5 级，评级适用于通话的所有流。 |
|First Feedback Token Audio Issue Count |被评级流的数量 |被使用第一终结点的用户指出存在音频问题的流的数量。 |
|Second Feedback Token Audio Issue Count |被评级流的数量 |被使用第二终结点的用户指出存在音频问题的流的数量。 |
|First Feedback Token Video Issue Count |被评级的流的数量 |使用第一个终结点的用户指示视频有问题的流的数量。 |
|Second Feedback Token Video Issue Count |被评级的流的数量 |使用第二终结点的用户指示视频有问题的流的数量。 |
|Avg First Echo Percent Mic In |百分比 |在流持续期间，第一终结点在消除回声之前通过捕获设备或麦克风设备在音频中检测到回声的持续时间的平均百分比。 |
|Avg Second Echo Percent Mic In |百分比 |在流持续期间，第二终结点在消除回声之前通过捕获设备或麦克风设备在音频中检测到回声的持续时间的平均百分比。 |
|Avg First Echo Percent Send |百分比 |在流持续期间，第一终结点在消除回声之后通过捕获设备或麦克风设备在音频中检测到回声的持续时间的平均百分比。 |
|Avg Second Echo Percent Send |百分比 |在流持续期间，第二终结点在消除回声之后通过捕获设备或麦克风设备在音频中检测到回声的持续时间的平均百分比。 |
| 第一初始信号级别 RMS 平均级别| 范围（分贝） |第一次终结点呼叫的前30秒内收到的信号的平均平均值平方（RMS）。  有关详细信息，请参阅[2.2.1.28.1 子元素](https://docs.microsoft.com/openspecs/office_protocols/ms-qoe/3c78f383-73fe-49f6-89cb-614e7aa8b2e7)|
| 平均第二次初始信号级别 RMS|范围（分贝） |第二终结点呼叫的前30秒内收到的信号的平均平均值平方（RMS）。||
| 平均第一个 RxAGC 信号级别|范围（分贝）  |在第一个入站音频流的自动增益控制处收到的平均信号级别。 | |
| 平均第二 RxAGC 信号级别|范围（分贝） |第二个入站音频流的自动增益控制收到的平均信号级别。| |
| 第一 RxAGC 的平均噪音级别|范围（分贝） |在第一个入站音频流的自动增益控制处收到的平均噪音级别。||
| 平均第二 RxAGC 噪声级别|范围（分贝） |第二个入站音频流的自动增益控制处收到的平均噪音级别。| |
| 平均第一个呈现环回信号级别|范围（分贝） | 第一个扬声器环回信号的平均级别（应用了任何设备卸载效果之后）。|
| 平均第二呈现环回信号级别|范围（分贝） | 第二种扬声器环回信号的平均级别（应用了任何设备卸载效果之后）。|
|Avg First Audio Send Signal Level |分贝 |对于被分类为单声道语音或左声道立体声语音的音频，第一终结点发送的音频的平均能量水平。 |
|Avg Second Audio Send Signal Level |分贝 |对于被分类为单声道语音或左声道立体声语音的音频，第二终结点发送的音频的平均能量水平。 |
|第一音频接收的平均音频信号级别 |分贝 |对于被分类为单声道语音或左声道立体声语音的音频，第一终结点接收的音频的平均能量水平。 |
|接收的平均第二音频信号级别 |分贝 |对于被分类为单声道语音或左声道立体声语音的音频，第二终结点接收的音频的平均能量水平。 |
|Avg First Audio Send Noise Level |分贝 |对于被分类为单声道噪音或左声道立体声噪音的音频，第一终结点发送的音频的平均能量水平。 |
|Avg Second Audio Send Noise Level |分贝 |对于被分类为单声道噪音或左声道立体声噪音的音频，第二终结点发送的音频的平均能量水平。 |
|第一音频接收的平均噪音级别 |分贝 |对于被分类为单声道噪音或左声道立体声噪音的音频，第一终结点接收的音频的平均能量水平。 |
|平均第二音频接收噪音级别 |分贝 |对于被分类为单声道噪音或左声道立体声噪音的音频，第二终结点接收的音频的平均能量水平。 |
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
|Avg Audio Degradation |平均意见得分 (0-5) |关于流降级的网络平均意见得分的平均值。 表示网络损失和抖动对收到的音频质量有多大影响。 |
|Avg Jitter |毫秒 |流的平均网络抖动，以毫秒为单位。 |
|Avg Jitter Max |毫秒 |流的最大网络抖动值，以毫秒为单位。 |
|Avg Packet Loss Rate |比率 |以 5 秒钟时间间隔计算到的流的平均丢包百分比的平均值。 0.1 表示丢失了10% 的数据包。 |
|Avg Packet Loss Rate Max |比率 |以 5 秒钟时间间隔计算到的流的最大丢包百分比的平均值。 0.1 表示丢失了10% 的数据包。 |
| 平均发送侦听 MOS |数字 |从用户发送的音频流的宽带的预测质量平均观点（MOS-LQ）的平均值。 <br/>请参阅[Lync Monitoring Reports 解码器](https://gallery.technet.microsoft.com/Lync-Reports-Decoder-001ba287)中的 "平均发送 MOS"|
|Avg Overall Avg Network MOS |平均意见得分 (0-5) |流的网络平均意见得分的平均值。表示通过考虑网络损耗、抖动和编解码器对所收到的音频质量的平均估计。 |
|Avg Ratio Concealed Samples |比率 |含有丢包隐藏生成样本的音频帧数与流的总音频帧数的平均比率的平均值。0.1 表示 10% 的帧包含隐藏样本。 |
| 平均隐藏比率最大值| 比率 |使用数据包丢失 concealment 生成的样本的音频帧数的最大比率的平均值到流的音频帧总数。 0.1 表示 10% 的帧包含隐藏样本。| |
|Avg Ratio Stretched Samples |比率 |通过拉伸样本补偿抖动或丢失的音频帧数与流的总音频帧数的平均比率的平均值。0.1 表示 10% 的音频帧包含拉伸样本。 |
| 平均 Healer 数据包丢弃比率|范围（比率）|由 healer 丢弃的音频数据包的平均比率，超过 healer 收到的音频数据包总数。 | |
| 平均 Healer FEC 数据包使用比率|范围（比率）|已使用的 FEC 数据包的平均比率，超过了收到的 FEC 数据包的总数。|
|Avg Round Trip |毫秒 |计算的平均网络传播往返时间的平均值，根据 RFC3550 以毫秒为单位指定。 |
|Avg Round Trip Max |毫秒 |计算的最大网络传播往返时间的平均值，根据 RFC3550 以毫秒为单位指定。 |
 平均数据包利用率|数据包数|会话中每秒发送的实时传输协议（RTP）数据包的平均数量。|
|Avg Network Jitter |毫秒 |   会话期间通过20秒的窗口计算的网络抖动的平均值。 |
| 平均网络抖动最大值|毫秒 |会话期间通过20秒窗口计算的最大网络抖动（以毫秒为单位）的平均值。  ||
| 平均网络抖动最小值|毫秒|最小网络抖动值的平均值，以毫秒为单位在流的会话期间通过20秒的时间计算。| |
| 平均抖动缓冲区大小的最大值|毫秒|会话期间抖动缓冲区的最大大小。| |
| 平均抖动缓冲区大小（最小）|毫秒|会话期间抖动缓冲区的最小大小。| |
| 平均相对单向 |毫秒|对等的平均计算的相对一种单向延迟。| |
| 平均相对单向间隔出现次数|毫秒|对等的相对单向延迟中的平均间隔实例数。| |
| 平均相对单向间隙密度|毫秒|对等的相对单向延迟中的平均间隔密度。| |
| 平均相对的单向间隙持续时间|数字（毫秒）|对等的相对单向延迟中的间隔平均持续时间。| |
|平均音频发布 FECPLR |比率 |在所有音频流和流的编解码器上应用了 FEC 后，数据包丢失率的平均值。 |
|Avg Video Post FECPLR |比率 |应用 FEC 后，跨所有视频流和编解码器汇总的丢包率的平均值。 |
|Avg Video Local Frame Loss Percentage |百分比 |向用户显示的流视频帧丢失平均百分比。其中包括从网络丢失恢复的帧。 |
 |接收的平均视频帧速率平均值 |帧/秒 |在会话持续期间计算到的流的所有视频流每秒接收的平均帧数的平均值。 |
 |Avg Video Low Frame Rate Call Percent |百分比 |帧速率低于 7.5 帧/秒的流通话时间的平均百分比。 |
|Avg Video Packet Loss Rate |比率 |在流的会话持续时间内，在[根据 rfc3550](https://tools.ietf.org/html/rfc3550)中指定的数据包平均损失的平均值。 |
|Avg Video Frame Rate |帧/秒 |在会话持续期间计算到的视频流每秒接收的平均帧数。值按范围分组表示。 |
|Avg Video Dynamic Capability Percent |毫秒 |客户端以低于此类型 CPU 预期视频处理容量的 70% 运行的流时间的平均百分比。 |
|Avg AppSharing Spoiled Tile Percent Total |毫秒 |没有被发送到远程对等点（例如，从 MCU 到查看器）而是被丢弃的图块的平均百分比。丢弃图块可能是由于客户端与服务器之间的带宽限制所致。 |
|Avg AppSharing Relative OneWay |秒 |应用程序共享流的终结点之间的平均相对单向延迟（以秒为单位）。 |
|Avg AppSharing RDP Tile Processing Latency |毫秒 |在会议服务器上处理 RDP 堆栈图块的流平均延迟的平均值，以毫秒为单位。 |
|平均第一设备捕获不起作用事件比率 |比率 |第一个终结点检测到的捕获设备的调用分数的平均值未正常工作。 |
|平均第二设备捕获不起作用事件比率 |比率 |第二终结点检测到的捕获设备的调用分数的平均值未正常工作。 |
|第一设备的平均呈现不起作用事件比率 |比率 |第一个终结点检测到呈现设备的调用分数的平均值未正常工作。 |
|平均第二设备呈现不起作用事件比率 |比率 |第二终结点检测到呈现设备的调用分数的平均值未正常工作。 |
|第一次麦克风故障率| 故障次数|流的第一种麦克风故障率（每5分钟的故障）的平均值。  ||
| 平均第二个麦克风故障率|故障次数|流的平均每秒 Mic 故障率（每5分钟的故障）。 ||
| 平均第一个扬声器故障率|故障次数|流的平均第一次扬声器故障率（终结点扬声器的每5分钟故障）。 |
| 平均第二扬声器故障率|故障次数|流的平均第二个扬声器故障率（终结点扬声器的每5分钟故障）。 |
| 第一个用户计数|数字 | 唯一或独特的第一个终结点用户的数量。| |
| 第二用户计数|数字|唯一或独特的第二终结点用户的数量。|
| 第一设备的平均故障率事件比率|百分比|第一个终结点检测到或捕获的媒体中导致无法发送或接收的较差媒体质量的问题的平均分数。|
| 平均第二设备故障事件比率|百分比|第二终结点检测到或捕获的媒体中导致无法发送或接收的较差媒体质量的问题的平均分数。|
| 第一设备故障事件计数|第一个终结点检测到或捕获的媒体中的严重故障或中断，导致发送或接收的媒体质量不佳的流的数量。||
| 第二设备故障事件计数|第二终结点在播放或捕获的媒体中检测到的、导致无法发送或接收的媒体质量较差的流的数量。||
| PSTN 总尝试次数 | 通话的数量 | 已尝试的通话总次数，包括成功的呼叫和在所选时间范围内失败的通话。|
|PSTN 总连接计数 | 通话的数量 | 所选时间范围内已成功连接的通话总数。|
|PSTN 入站尝试计数 | 通话的数量 | 入站尝试的通话总数，包括成功的呼叫和选择时间范围内的失败呼叫。|
|PSTN 入站连接计数 | 通话的数量 | 所选时间范围内入站成功连接的通话总数。|
|PSTN 出站尝试计数 | 通话的数量 | 拨出的通话总次数，包括成功的呼叫和在所选时间范围内失败的通话。|
|PSTN 出站连接计数 | 通话次数 | 所选时间范围内的出站成功连接的通话总数。|
|PSTN 总分钟数 | 分钟 | 总分钟数 | 所选时间范围内的总分钟使用率。|
|PSTN 入站总分钟数 | 分钟 | 所选时间范围内的入站分钟使用率总计。|
|PSTN 出站总分钟数 | 分钟 | 所选时间范围内的总出站分钟使用率。|
|PSTN 活动用户计数 | 用户数 | 在同一天内至少进行一次连接通话的用户数。|
|PSTN 平均呼叫持续时间 | 分钟 | 所选时间范围内所有连接的通话的平均持续时间。 正常情况下，1:1 PSTN 呼叫为4至5分钟。 但是，对于每个公司，此平均值可能有所不同。|
|PSTN 总入站并发通话计数 | 通话的数量 | 一分钟内活动拨入拨入电话的最大数量。|
|PSTN 总出站并发呼叫计数 | 通话的数量 | 一分钟内同时进行的活动出站通话的最大数量。|
|P50 延迟 | 毫秒 | 50% 的请求速度应比给定的延迟更快。|
|P50 抖动 | 毫秒 | 50% 的请求速度应比给定的抖动更快。|
|P50 数据包丢失率 | 百分比 | 50% 的请求应低于给定的数据包丢失速率。|
|PSTN 传出的拨出后延迟| 毫秒 | 拨出电话拨出的电话上的延迟，从拨打电话到呼叫方或呼叫方听到铃声的时间开始。|
|PSTN 传入后拨号延迟 | 毫秒 | 拨入电话时，从拨打电话到呼叫方或呼叫方听到响铃的时间或延迟。|
|PSTN NER 优惠百分比 | 百分比 | NER 衡量网络通过测量发送的呼叫数与发送给收件人的呼叫次数之间传递呼叫的能力。<br/>NER = （接听电话 + 用户占线 + 环无应答 + 终端拒绝病情发作）/总尝试拨打 x 100|
||||

## <a name="filters"></a>筛选器

许多维度和度量值也可以用作筛选器。 你可以在查询中使用筛选器来消除信息，方法与选择维度或度量以在查询中添加或包含信息的方式相同。

## <a name="related-topics"></a>相关主题

[设置 Skype for Business 通话分析](set-up-call-analytics.md)

[使用通话分析来排查通话质量不良问题](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[通话分析和通话质量仪表板](difference-between-call-analytics-and-call-quality-dashboard.md)
 
