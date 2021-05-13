---
title: '维度和度量 - 呼叫质量仪表板 (CQD) '
ms.author: serdars
author: SerdarSoysal
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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Reporting
- seo-marvel-mar2020
description: 获取有关呼叫质量仪表板和适用于 Microsoft Teams Online 的 CQD (CQD) 和Skype for Business的详细信息。
ms.openlocfilehash: 981c5811f00d2e9005bd1387a7b58d23431af848
ms.sourcegitcommit: 50ec59b454e751d952cde9fd13c8017529d0e1d6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2021
ms.locfileid: "52469734"
---
# <a name="dimensions-and-measurements-available-in-call-quality-dashboard-cqd"></a>呼叫质量仪表板和 CQD (中的维度和) 

呼叫质量仪表板 (用于) Microsoft Teams Skype for Business Online 的 CQD 仪表板使您可以更好地了解这些服务的呼叫质量。 本主题提供有关通过 CQD 可见的维度和度量的详细信息。 若要了解有关 CQD 的更多信息，请参阅使用 CQD 在 Microsoft Teams 中管理[呼叫和Microsoft Teams。](quality-of-experience-review-guide.md)

## <a name="first-and-second-endpoint-classification"></a>第一和第二终结点分类

CQD 中的许多维度和度量被标记为第一个或第二个。 以下逻辑用于确定将流或通话中涉及的哪些终结点标为第一。

- 当服务器 (流或调用时，) AV MCU、中介服务器等服务器终结点视为 First。
- 除非流在两个服务器终结点之间，否则客户端终结点被视为"第二"。
- 如果两个终结点的类型相同，则第一个和第二个终结点是根据用户代理类别的内部顺序设置的，以确保排序一致。

例如，此处每行表示流中涉及的一对用户代理：

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

维度信息部分基于上传到 CQD 门户的数据。 许多维度值也可以用作筛选器。 下表列出了 CQD 中当前可用的维度，按查询编辑器中用于创建报表或编辑以前定义的报表的顺序列出。

| 名称 | 数据类型  | 说明 | 空值的可能原因 |
|:---  |:---        |:---         |:--- |
|**Endpoint**|||
| First CPU Name  | 字符串  | 第一终结点使用的 CPU 的名称。 <br/> **示例值：** Contoso CPU X11 @ 1.80 GHz | <br/>&bull; 终结点未报告此数据   |
| Second CPU Name  | 字符串  | 第二终结点使用的 CPU 的名称。 <br/> **示例值：** Contoso CPU X11 @ 1.80 GHz | <br/>&bull; 终结点未报告此数据     |
| First CPU Number Of Cores  | 内核数量  | 第一终结点上可用的 CPU 内核数。 <br/> **示例值：8**  | <br/>&bull; 终结点未报告此数据    |
| Second CPU Number Of Cores  | 内核数量  | 第二终结点上可用的 CPU 内核数。 <br/> **示例值：8**  | <br/>&bull; 终结点未报告此数据     |
| First CPU Processor Speed  | CPU 速度，单位为 MHz  | 第一终结点使用的 CPU 的速度，单位为 MHz。 <br/> **示例值** ：1800  | <br/>&bull; 终结点未报告此数据   |
| Second CPU Processor Speed  | CPU 速度，单位为 MHz  | 第二终结点使用的 CPU 的速度，单位为 MHz。 <br/> **示例值** ：1800 | <br/>&bull; 终结点未报告此数据     |
| First Endpoint  | 字符串  | 如果第一终结点为服务器或云服务客户端，此终结点报告的计算机名称。 <br/> **示例值：** MACHINENAME  | <br/>&bull; 终结点未报告此数据    |
| Second Endpoint  | 字符串  | 如果第二终结点为服务器或云服务客户端，此终结点报告的计算机名称。 <br/> **示例值：** MACHINENAME | <br/>&bull; 终结点未报告此数据     |
| First OS  | 字符串  | 第一终结点报告的完整操作系统和体系结构字符串。 <br/> **示例值**：Windows 10.0.14996 SP： 0.0 类型：1 (工作站) Suite： 256 Arch： x64 WOW64： True | <br/>&bull; 终结点未报告此数据 |
| Second OS  | 字符串  | 第二终结点报告的完整操作系统和体系结构字符串。 <br/> **示例值**：Windows 10.0.14996 SP： 0.0 类型：1 (工作站) Suite： 256 Arch： x64 WOW64： True  | <br/>&bull; 终结点未报告此数据 |
| First OS Filtered  | 字符串  | 第一终结点报告的操作系统名称和主要版本及次要版本。 此字符串可以包含多个 OS 名称和版本。 <br/> **示例值：Windows 10**  | <br/>&bull; 终结点未报告此信息 <br/>&bull; 未收到来自此终结点的报告。  |
| Second OS Filtered  | 字符串  | 第二终结点报告的操作系统名称和主要版本及次要版本。 此字符串可以包含多个 OS 名称和版本。 <br/> **示例值：Windows 10**  | <br/>&bull; 终结点未报告此信息 <br/>&bull; 未收到来自此终结点的报告 |
| First OS Architecture  | 字符串  | 第一终结点报告的硬件体系结构。 <br/> **示例值：x64**  | &bull; 终结点未报告此信息 <br/>&bull; 未收到来自此终结点的报告 <br/>&bull; 无法识别体系结构的格式 |
| Second OS Architecture  | 字符串  | 第二终结点报告的硬件体系结构。 <br/> **示例值：x64**  | &bull; 终结点未报告此信息 <br/>&bull; 未收到来自此终结点的报告 <br/>&bull; 无法识别体系结构的格式  |
| First Virtualization Flag  | 枚举 <br/>**可能的值：** <br/> "0x00" = 无  <br/> "0x01" = Hyper-V <br/> "0x02" = VMware <br/> "0x04" = 虚拟电脑 <br/> "0x08" = Xen PC | 指示第一终结点报告的虚拟化环境类型的标志。 | <br/>&bull; 终结点未报告数据 |
| Second Virtualization Flag  | 枚举 <br/>**可能的值：** <br/> "0x00" = 无  <br/> "0x01" = Hyper-V <br/> "0x02" = VMware <br/> "0x04" = 虚拟电脑 <br/> "0x08" = Xen PC | 指示第二终结点报告的虚拟化环境类型的标志。  | <br/>&bull; 终结点未报告数据 |
|First Endpoint Make |String |设备制造商从终结点数据文件 EndpointMake 字段读取信息。 | <br/>&bull; 终结点没有数据文件 |
| 第一终结点模型 |String|设备模型，从终结点数据文件 EndpointModel 字段读取信息。| <br/>&bull; 终结点没有数据文件 |
| 第一终结点类型|String|设备类型，从终结点数据文件 EndpointType 字段读取信息。| <br/>&bull; 终结点没有数据文件 |
| 第一终结点标签 1|String|一个可自定义的标签，从终结点数据文件 读取信息。| <br/>&bull; 终结点没有数据文件 |
| First Endpoint Label 2|String|可自定义的标签，从终结点数据文件读取信息。| <br/>&bull; 终结点没有数据文件 |
| First Endpoint Label 3|String|可自定义的标签，从终结点数据文件读取信息。|  <br/>&bull; 终结点没有数据文件|
| Second Endpoint Make|String|设备制造商从终结点数据文件 EndpointName 字段中读取信息。 | <br/>&bull; 终结点没有数据文件 |
| 第二终结点模型|String|设备模型，从终结点数据文件 EndpointModel 字段读取信息。| <br/>&bull; 终结点没有数据文件 |
| 第二终结点类型|String|设备类型，从终结点数据文件 EndpointType 字段读取信息。|  <br/>&bull; 终结点没有数据文件|
| 第二终结点标签 1|String| 可自定义的标签，从终结点数据文件读取信息。 | <br/>&bull; 终结点没有数据文件 |
| 第二终结点标签 2|String|可自定义的标签，从终结点数据文件读取信息。| <br/>&bull; 终结点没有数据文件|
| 第二终结点标签 3|String|可自定义的标签，从终结点数据文件读取信息。| <br/>&bull; 终结点没有数据文件 |
| First ASN|String|第一终结点的自治系统编号。 <br/> **示例值** ：8069  | <br/>&bull; 网络数据无法确定终结点 ASN |
| Second ASN|String|第二终结点的自治系统编号。 <br/> **示例值** ：8069  | <br/>&bull; 网络数据无法确定终结点 ASN |
| 第一个 ASN 国家/地区代码|String|为第一终结点确定的自治系统编号的国家/地区代码。 <br/> **示例值：** 美国  | <br/>&bull; 网络数据无法确定终结点 ASN |
| 第二个 ASN 国家/地区代码|String|为第二终结点确定的自治系统编号的国家/地区代码。 <br/> **示例值：** 美国  | <br/>&bull; 网络数据无法确定终结点 ASN |
| 第一个 ASN 国家/地区|String|为第一终结点确定的自治系统编号的国家/地区名称。 <br/> **示例值：** 美国  | <br/>&bull; 网络数据无法确定终结点 ASN |
| 第二个 ASN 国家/地区|String|为第二终结点确定的自治系统编号的国家/地区名称。 <br/> **示例值：** 美国  | <br/>&bull; 网络数据无法确定终结点 ASN |
| First ASN City|String|为第一终结点确定的自治系统编号的城市名称。 <br/> **示例值：** 雷德蒙德  | <br/>&bull; 网络数据无法确定终结点 ASN |
| Second ASN City|String|为第二终结点确定的自治系统编号的城市名称。 <br/> **示例值：** 雷德蒙德  | <br/>&bull; 网络数据无法确定终结点 ASN |
| 第一个 ASN 状态|String|为第一终结点确定的自治系统编号的状态名称。 <br/> **示例值：** WA  | <br/>&bull; 网络数据无法确定终结点 ASN |
| 第二个 ASN 状态|String|为第二终结点确定的自治系统编号的状态名称。 <br/> **示例值：** WA  | <br/>&bull; 网络数据无法确定终结点 ASN |
|**大楼**| | |
| First Network | 字符串 | 如果子网存在于子网到租户建筑物数据中，则第一终结点用于媒体流的子网。 <br/> **示例值** ：10.0.1.12.0 | &bull; 终结点未报告网络数据 <br/>&bull; 子网映射数据中未定义网络。  |
| First Network Name  | 字符串  | 第一终结点用于媒体流的网络的名称。 基于子网与租户建筑物数据的映射。 <br/> **示例值：** USA/WA/REDMOND | &bull; 终结点未报告网络数据 <br/>&bull; 子网映射数据中未定义网络  |
| First Network Range  | 字符串  | 第一终结点用于媒体流的子网的网络前缀/范围，基于数据映射子网到租户建筑物。 <br/> **示例值：24** | &bull; 终结点未报告网络数据 <br/>&bull; 子网映射数据中未定义网络 |
| First Building Name  | 字符串  | 根据子网与租户建筑物映射数据，第一终结点所在的建筑物的名称。  <br/> **示例值：** Main  | &bull; 终结点未报告网络数据 <br/>&bull; 子网映射数据中未定义网络   |
| First Ownership Type  | 字符串  | 第一终结点所在的建筑物的所有权类型。 基于子网与租户建筑物数据的映射。 <br/> **示例值：** Contoso-IT  | &bull; 终结点未报告网络数据 <br/>&bull; 网络不在企业网络中，或者子网映射数据中未定义网络所有权  |
| First Building Type   | 字符串  | 根据子网与租户建筑物映射数据，第一终结点所在的建筑物类型。 <br/> **示例值：** 打开Office | &bull; 终结点未报告网络数据 <br/>&bull; 网络不在企业网络中 <br/>&bull; 子网映射数据中未定义网络建筑物类型  |
| First Building Office Type  | 字符串  | 根据子网与租户建筑物映射数据，第一终结点所在的建筑物类型。 <br/> **示例值：** 打开Office | &bull; 终结点未报告网络数据 <br/>&bull; 网络不在企业网络中 <br/>&bull; 子网映射数据中未定义网络建筑物类型  |
| First City  | 字符串  | 根据子网与租户建筑物映射数据，第一终结点所在的城市。 <br/> **示例值：** 雷德蒙德 | &bull; 终结点未报告网络数据 <br/>&bull; 网络不在企业网络中 <br/>&bull; 网络没有在子网映射数据中定义的城市   |
| First Zip Code  | 字符串  | 根据子网与租户建筑物映射数据，第一终结点所在的邮政编码。 <br/> **示例值** ：98052 | &bull; 终结点未报告网络数据 <br/>&bull; 网络不在企业网络中 <br/>&bull; 网络没有在子网映射数据中定义的邮政编码   |
| First Country  | 字符串  | 根据子网与租户建筑物映射数据，第一终结点所在的国家/地区。 <br/> **示例值：** 美国 | <br/>&bull; 终结点未报告网络数据<br/>&bull; 网络不在企业网络中 <br/>&bull; 网络没有在子网映射数据中定义的国家/地区 |
| First State  | 字符串  | 根据子网与租户建筑物映射数据，第一终结点所在的状态。 <br/> **示例值：** WA | <br/>&bull; 终结点未报告网络数据<br/>&bull; 网络不在企业网络中 <br/>&bull; 网络没有子网映射数据中定义的状态。   |
| First Region  | 字符串  | 根据子网与租户建筑物映射数据，第一终结点所在的区域。 <br/> **示例值：** 北美 | <br/>&bull; 终结点未报告网络数据<br/>&bull; 网络不在企业网络中 <br/>&bull; 网络没有在子网映射数据中定义的区域。 |
| First Express Route  | 布尔值  | 如果根据子网与租户建筑物映射数据，为 Azure ExpressRoute 启用了第一终结点用于媒体流的子网，则为 True。 如果决定，可以出于其他目的自定义使用情况。  |  &bull; 终结点未报告网络数据 <br/>&bull; 网络不在企业网络中 <br/>&bull; 网络在子网映射数据中未设置 ExpressRoute 标志。|
| Second Network  | 字符串  | 如果子网存在于子网到租户建筑物数据中，则第二终结点用于媒体流的子网。 <br/> **示例值** ：10.0.1.12.0  | &bull; 终结点未报告网络数据 <br/>&bull; 子网映射数据中未定义网络  |
| Second Network Name  | 字符串  | 根据子网与租户建筑物映射数据，第二终结点用于媒体流的网络的名称。 <br/> **示例值：** USA/WA/REDMOND  | &bull; 终结点未报告网络数据 <br/>&bull; 网络没有在子网映射数据中定义的网络名称  |
| Second Network Range  | 字符串  | 根据子网与租户建筑物映射数据，第二终结点用于媒体流的子网的网络前缀/范围。 <br/> **示例值：24**  | &bull; 终结点未报告网络数据 <br/>&bull; 网络没有子网映射数据中定义的网络范围  |
| Second Building Name  | 字符串  | 根据子网与租户建筑物映射数据，第二终结点所在的建筑物的名称。 <br/> **示例值：** Main | <br/>&bull; 终结点未报告网络数据<br/>&bull; 网络不在企业网络中 <br/>&bull; 网络没有在子网映射数据中定义的建筑物名称 |
| Second Ownership Type  | 字符串  | 根据子网与租户建筑物映射数据，第二终结点所在的建筑物的所有权类型。 <br/> **示例值：** Contoso - IT | &bull; 终结点未报告网络数据<br/>&bull; 网络不在企业网络中 <br/>&bull; 网络没有在子网映射数据中定义的所有权 |
| Second Building Type  | 字符串  | 根据子网与租户建筑物映射数据，第二终结点所在的建筑物类型。 <br/> **示例值：** 打开Office | <br/>&bull; 终结点未报告网络数据<br/>&bull; 网络不在企业网络中 <br/>&bull; 子网映射数据中未定义网络建筑物类型   |
| Second Building Office Type  | 字符串  | Office子网与租户建筑物映射数据，第二终结点所在的建筑物类型。 <br/> **示例值：Office**  | <br/>&bull; 终结点未报告网络数据<br/>&bull; 网络不在企业网络中 <br/>&bull; 网络没有在子网映射数据中定义的建筑物办公类型。  |
| Second City  | 字符串  | 根据子网与租户建筑物映射数据，第二终结点所在的城市。 <br/> **示例值：** 雷德蒙德 |  <br/>&bull; 终结点未报告网络数据  <br/>&bull; 网络不在企业网络中  <br/>&bull; 网络没有在子网映射数据中定义的城市   |
| Second Zip Code  | 字符串  | 根据子网与租户建筑物映射数据，第二终结点所在的邮政编码。 <br/> **示例值** ：98052  | <br/>&bull; 终结点未报告网络数据 <br/>&bull; 网络不在企业网络中 <br/>&bull; 网络没有在子网映射数据中定义的邮政编码 |
| Second Country  | 字符串  | 根据子网与租户建筑物映射数据，第二终结点所在的国家/地区。 <br/> **示例值：** 美国  | <br/>&bull; 终结点未报告网络数据<br/>&bull; 网络不在企业网络中 <br/>&bull; 网络没有在子网映射数据中定义国家/地区  |
| Second State  | 字符串  | 根据子网与租户建筑物映射数据，第二终结点所在的状态。 <br/> **示例值：** WA  | <br/>&bull; 终结点未报告网络数据<br/>&bull; 网络不在企业网络中 <br/>&bull; 网络没有在子网映射数据中定义的状态  |
| Second Region  | 字符串  | 根据子网与租户建筑物映射数据，第二终结点所在的区域。 <br/> **示例值：** 北美  | <br/>&bull; 终结点未报告网络数据 <br/>&bull; 网络不在企业网络中 <br/>&bull; 网络没有在子网映射数据中定义区域。 |
| Second Express Route  | 布尔值  | 如果根据子网与租户建筑物映射数据，为 ExpressRoute 启用了第二终结点用于媒体流的子网，则为 True。    | <br/>&bull; 终结点未报告网络数据 <br/>&bull; 网络不在企业网络中 <br/>&bull; 网络未在子网映射数据中设置 ExpressRoute 标志   |
| First Inside Corp  | 枚举 <br/>**可能的值：** <br/> 内部、外部  | 根据子网与租户建筑物映射数据，指示第一终结点是否位于企业网络内的子网中。 默认情况下，认为终结点位于外部。 <br/> **示例值：** 内部 | |
| Second Inside Corp  | 枚举 <br/> **可能的值：** <br/> 内部、外部 | 根据子网与租户建筑物映射数据，指示第二终结点是否位于企业网络内的子网中。 默认情况下，认为终结点位于外部。 <br/>**示例值：** 内部  |  |
|**Deployment**| | | |
| First Tenant Id  | 字符串  | 第一终结点的租户 ID。 <br/> **示例值** ：00000000 - 0000 -0000 - 0000 - 000000000000  | <br/>&bull; 无法确定第一终结点的租户 ID。 这可能表示终结点已登录到本地 Skype for Business Server部署。  |
| Second Tenant Id  | 字符串  | 第二终结点的租户 ID。 <br/> **示例值** ：00000000 - 0000 - 0000 - 0000 - 000000000000  |  <br/>&bull; 无法确定第二终结点的租户 ID。 这可能表示终结点已登录到本地 Skype for Business Server部署。  |
| First Pool  | 字符串  | 分配给第一终结点的 Skype for Business Online 池 FQDN <br/> **示例值：pool1** <span></span> .lync <span></span> .com  | <br/>&bull;指示终结点已登录到 Microsoft Teams 或 Skype for Business。 只有使用本地部署和本地部署为流填充Skype for Business Server字段。 |
| Second Pool  | 字符串  | 分配给第二终结点的 Skype for Business Online 池 FQDN <br/> **示例值：pool1.lync.com** <span></span>   | &bull;Skype for Business无法确定第二终结点的联机池。 这可能表示终结点已登录到本地 Skype for Business Server部署。  |
| Is Federated  | 布尔值  | 如果流在两个联合租户之间，则为 True，否则为 False。   | <br/>&bull; 无法确定这是否为联合流 <br/>&bull; 未收集某些信号数据   |
|区域 | String   |  部署所在的区域基于租户的主页区域。 <br/> **示例值：** 北美 | <br/>&bull; 未报告网络数据 <br/>&bull; 网络不在企业网络中 <br/>&bull; 网络没有在子网映射数据中定义区域。 |
|**Stream**| | | |
| QoE Record Available  | 布尔值  | 如果为通话/会话提供至少一个用户体验质量报告，则为 True。 许多维度和度量仅在 QoE 记录可用时可用。 如果呼叫设置失败，QoE 记录将不可用。    |   |
| CDR Record Available  | 布尔值  | 如果为通话/会话提供至少一个呼叫详细记录，则为 True。     | |
| Media Line Label  | 整型  | SDP 中用于媒体行的标签。使用"媒体类型"来确定是否为视频、音频、应用共享或基于视频的屏幕共享使用标签。<br/> **示例值：0**  | &bull; 终结点未报告此数据。  |
| Media Type  | 字符串  | 媒体的类型（视频、音频、应用共享或基于视频的屏幕共享）。 <br/> **示例值：** 音频 |  |
|媒体行标签文本 | String |会话说明协议 (SDP) 与流相对应的媒体行的标签属性。 有关更多详细信息，请参阅[RFC 4574。](https://tools.ietf.org/html/rfc4574) <br/> **示例值**： <br/> main-audio<br/> main-video<br/> main-video1<br/> main-video2<br/> main-video3<br/> main-video4<br/> main-video5<br/> main-video6<br/> main-video7<br/> main-video8<br/> main-video9<br/> 全景视频<br/> applicationsharing-video<br/> 数据   | |
| First Is Server  | 枚举 <br/>**可能的值：** <br/>&bull; 客户端 <br/>&bull; 服务器  | 指示第一个终结点是会议服务器 (AVMCU、ASMCU) 或其他媒体服务器 (中介服务器) ，还是客户端终结点。  **示例值：** 客户端 | |
| Second Is Server  | 枚举 <br/>**可能的值：** <br/>&bull; 客户端 <br/>&bull; 服务器   | 指示第二个终结点是服务器终结点，还是客户端终结点。 <br/>  **示例值：** 客户端 | |
| First Is Caller  | 布尔值  | 如果第一终结点是发起会话的调用方，则为 True。   | |
| First Network Connection Detail  | 枚举 <br>**可能的值：** <br/>&bull; 有线 <br/>&bull; WiFi <br/>&bull; MobileBB <br/>&bull;Tunnel <br/>&bull; 其他 | 第一终结点使用的网络类型。  <br/> **示例值：** 有线  | &bull; 终结点未报告数据  |
| Second Network Connection Detail  | 枚举 <br/>**可能的值：** <br/>&bull; 有线 <br/>&bull; WiFi <br/>&bull; MobileBB <br/>&bull;Tunnel <br/>&bull; 其他 | 第二终结点使用的网络类型。  <br/> **示例值：** 有线  | &bull; 终结点未报告数据  |
| Stream Direction  | 枚举 <br/>**可能的值：** <br/>&bull; 第一到第二个 <br/>&bull; 第二到第一 <br/> | 指示流的方向。 <br/>&bull;**示例值：** 第一到第二个 | &bull; 未报告指示流方向的数据 |
| Payload Description  | 字符串  | 流中最后使用的编解码器的名称。 <br/> **示例值：** SILKWide | &bull; 无可用数据 |
| Audio and Video Call  | 布尔值  | 如果呼叫同时包含音频和视频流，则为 True，否则为 False    | &bull; 未报告任何数据来指示流的媒体类型。 |
| Duration 5 seconds or less  | 布尔值  | 如果流的持续时间为 5 秒或更短，则为 True，否则为 False。   ||
| Duration 60 seconds or more  | 布尔值  | 如果流的持续时间超过 60 秒，则为 True，否则为 False。   | |
| 是Teams  | Boolean  | True 表示流的第一个或第二个用户代理是Microsoft Teams终结点。 <br/> False 表示用户代理Skype for Business终结点。 |  |
| Duration (Minutes)  | 范围（分钟）  | 流的持续时间，以分钟为单位。值按范围分组表示。<br/> **示例值** ：065：[3-4)  ||
| Duration (Seconds)  | 范围（秒） | 流的持续时间，以秒为单位。值按范围分组表示。<br/> **示例值** ：062：[1 -2) ||
|**日期**|||
|结束时间|  String| 通话结束的一天中的时间。|&bull; 调用设置失败 |
| Year  | 整型  | 流结束的年份。 值以 UTC 时区报告。 <br/> **示例值** ：2018 | |
| Month  | 整型  | 流结束的月份。 值以 UTC 时区报告。 <br/> **示例值：2** | |
| Day  | 整型  | 流结束的一天。 值以 UTC 时区报告。 <br/> **示例值：1** | |
| 日期  | String  | 流结束的日期。 值以 UTC 时区报告。 <br/> **示例值** ：2018-06-01 | |
| Hour  | 整型  | 流结束的小时。 值以 UTC 时区报告。 <br/> **示例值：1**  ||
| Minute  | 整型  | 流结束的分钟数。 值以 UTC 时区报告。 <br/> **示例值：30** | |
| Second  | 整型  | 流结束的第二秒。 值以 UTC 时区报告。 <br/> **示例值：12** | |
| Day Of Year  | 整型  | 流结束时的一年中的一天。 值以 UTC 时区报告。 <br/> **示例值：32** | |
| Day Of Week  | 字符串  | 流结束的一周中的一天。 值以 UTC 时区报告。 <br/> **示例值：** 星期三 | |
| Day Number Of Week  | 整型  | 流结束的星期数。 值以 UTC 时区报告。 <br/> **示例值：3** | |
|Week|  String  |通话的开始日期。 <br/> **示例值** ：2019-09-01 |&bull; 调用设置失败 |
| Month Year  | 字符串  | 流的结束月份和年份。 值以 UTC 时区报告。 <br/> **示例值** ：2017-02 | |
| Full Month  | 日期时间  | 流结束的完整月份。 值以 UTC 时区报告。 <br/> **示例值** ：2017-02-01T00：00：00 | |
|开始时间|String  |通话开始一天的时间。|&bull; 调用设置失败 |
|**UserAgent** | | |
| First Domain  | 字符串  | 第一终结点用户的域。 如果第一个终结点是会议服务器，则它使用会议组织者的域。 也可能是场景中使用的服务帐户的域。  <br/> **示例值：contoso** <span></span> .com | |
| Second Domain  | 字符串  | 第二终结点用户的域。 如果第二终结点是会议服务器，则它使用会议组织者的域。 也可能是场景中使用的服务帐户的域。 <br/> **示例值：contoso** <span></span> .com  | |
| First User Agent Category  | 字符串  | 第一终结点的用户代理的类别。 <br/> **示例值：** OC | &bull; 用户代理当前没有映射    |
| Second User Agent Category  | 字符串  | 第二终结点的用户代理的类别。 <br/> **示例值：** OC | &bull; 用户代理当前没有映射    |
| First User Agent  | 字符串  | 第一终结点的用户代理字符串。 <br/> **示例值：** UCCAPI/16.0.7766.5281 OC/16.0.7766.2047 (Skype for Business)  | &bull; 第一终结点未报告任何用户代理   |
| Second User Agent  | 字符串  | 第二终结点的用户代理字符串。 <br/> **示例值：** UCCAPI/16.0.7766.5281 OC/16.0.7766.2047 (Skype for Business)  | &bull; 第二终结点未报告任何用户代理   |
| Conference Type  | 枚举 <br/>**可能的值：** <br/>&bull; conf：applicationsharing <br/>&bull; conf：audio-video <br/>&bull; conf：focus | 会议 URI 的类型。  <br/> **示例值** ：conf：audio-video | &bull; 非会议方案。   |
| 会议 ID  | String | 会议 ID (与) 关联的呼叫 ID。 在 cqd.teams.microsoft.com，所有呼叫都有呼叫 ID，无论他们是 P2P 呼叫 (还是电话会议) 人对人。 此维度可能包含过多的行，无法用作报表的维度。 它可能会转为用作筛选器。   <br/> **示例值** (cqd.teams.microsoft.com) ：5a962ccf-b9cb-436a-a433-f28bf5404ad8  | |
| First Client App Version  | 字符串  | 第一终结点使用的应用程序的版本。数据从用户代理字符串解析。<br/> **示例值** ：16.0.7766.2047 | &bull; 无法分析版本字符串 <br/>&bull; 未报告该值。   |
| Second Client App Version  | 字符串  | 第二终结点使用的应用程序的版本。数据从用户代理字符串解析。<br/> **示例值** ：16.0.7766.2047 | &bull; 无法分析版本字符串 <br/>&bull; 未报告该值。 |
|会议 ID |String |创建会议时生成的会议标识符。  <br/> **示例值** ：19：meeting_MzB...zIw@thread.v2| |
|**网络**||| 
| Transport  | 枚举 <br/>**可能的值：** <br/>&bull; UDP <br/>&bull; TCP <br/>&bull; 无法识别  | 流使用的网络传输类型。  无法识别指示系统无法确定传输类型是 TCP 还是 UDP。  | &bull; 未报告传输类型 <br/>&bull; 未建立媒体路径  |
| First Connectivity Ice  | 枚举 <br/>**可能的值：** <br/>&bull; DIRECT= 直接网络路径 <br/>&bull; 中继 = 通过中继 <br/>&bull; HTTP = 通过 HTTP 代理 <br/>&bull; 失败 = 连接失败 | 第一终结点使用的 ICE 连接类型。  |&bull; 未报告传输类型 <br/>&bull; 未建立媒体路径   |
| Second Connectivity Ice  | 枚举 <br/>**可能的值：** <br/>&bull; DIRECT= 直接网络路径 <br/>&bull; 中继 = 通过中继 <br/>&bull; HTTP = 通过 HTTP 代理 <br/>&bull; 失败 = 连接失败  | 第二终结点使用的 ICE 连接类型。    | &bull; 未报告传输类型 <br/>&bull; 未建立媒体路径    |
| First IP Address  | 字符串  | 第一终结点的 IP 地址。请注意，此维度可能包含过多的行，导致无法用作报告中的一个维度。它可能会转为用作筛选器。<br/> **示例值** ：10.0.0.10  | &bull; 未报告传输类型 <br/>&bull; 未建立媒体路径   |
| Second IP Address  | 字符串  | 第二终结点的 IP 地址。 <br/> **注意：** 此维度可能包含过多的行，无法用作报表的维度。 It can be used as a filter instead. <br/> **示例值** ：10.0.0.10  | &bull; 未报告传输类型 <br/>&bull; 未建立媒体路径   |
| First Link Speed   |整型  | 第一终结点使用的网络适配器报告的链路速度，以"位/秒"为单位。 <br/> **示例值** ：10000000  | &bull; 未报告传输类型 <br/>&bull; 未建立媒体路径   |
| Second Link Speed   |整型  | 第二终结点使用的网络适配器报告的链路速度，以"位/秒"为单位。 <br/> **示例值** ：10000000 | &bull; 未报告传输类型 <br/>&bull; 未建立媒体路径    |
| First Port  | 端口号  | 第一终结点用于媒体的网络端口号。 <br/> **示例值** ：50018  | &bull; 未报告传输类型 <br/>&bull; 未建立媒体路径   |
| Second Port  | 端口号  | 第二终结点用于媒体的网络端口号。 <br/> **示例值** ：50018 | &bull; 未报告传输类型 <br/>&bull; 未建立媒体路径    |
| First Reflexive Local IP  | 字符串  | 媒体中继服务器观察到的第一终结点的 IP 地址。通常是与流的第一终结点关联的公共内部 IP 地址。<br/> **示例值** ：104.43.195.251  | &bull; 未报告传输类型 <br/>&bull; 未建立媒体路径   |
| Second Reflexive Local IP  | 字符串  | 媒体中继服务器观察到的第二终结点的 IP 地址。通常是与流的第二终结点关联的公共内部 IP 地址。<br/> **示例值** ：104.43.195.251  | &bull; 未报告传输类型 <br/>&bull; 未建立媒体路径  |
| First Relay IP  | 字符串  | 第一终结点分配的媒体中继服务器的 IP 地址。 <br/> **示例值** ：104.43.195.251  | &bull; 未报告传输类型 <br/>&bull; 未建立媒体路径   |
| Second Relay IP  | 字符串  | 第二终结点分配的媒体中继服务器的 IP 地址。 <br/> **示例值** ：104.43.195.251 | &bull; 未报告传输类型 <br/>&bull; 未建立媒体路径|
| First Relay Port  | 整型  | 第一终结点在媒体中继服务器上分配的媒体端口。 <br/> **示例值** ：3478  | &bull; 未报告传输类型 <br/>&bull; 未建立媒体路径   |
| Second Relay Port  | 整型  | 第二终结点在媒体中继服务器上分配的媒体端口。 <br/> **示例值** ：3478  | &bull; 未报告传输类型 <br/>&bull; 未建立媒体路径|
| First Subnet  | 字符串  | 第一终结点用于媒体流的子网，每个八进制数用短划线隔开。 <br/> **示例值** ：104.43.195.0  | &bull;终结点未报告数据 <br/>&bull; 未建立媒体路径 <br/>&bull; 使用了 IPv6|
| Second Subnet  | 字符串  | 第二终结点用于媒体流的子网，每个八进制数用短划线隔开。 <br/> **示例值** ：104.43.195.0 | &bull;终结点未报告数据 <br/>&bull; 未建立媒体路径 <br/>&bull; 使用了 IPv6 |
| First VPN  | 布尔值  | 如果第一终结点使用的网络适配器指出它是 VPN 连接，则为 True，否则为 False。 有些 VPN 不会正确报告此数据。   | &bull; 未报告传输类型 <br/>&bull; 未建立媒体路径   |
| Second VPN  | 布尔值  | 如果第二终结点使用的网络适配器指出它是 VPN 连接，则为 True，否则为 False。 有些 VPN 不会正确报告此数据。    | &bull; 未报告传输类型 <br/>&bull; 未建立媒体路径   |
| Applied Bandwidth Source  | 枚举 <br/>**可能的值：** <br/>&bull; 静态最大值 <br/>&bull; API 形式 <br/>&bull; API Modality_All <br/>&bull; API SendSide BWLimit <br/>&bull; 首选项值 <br/>&bull; TURN <br/>&bull; ReceiveSide TURN <br/>&bull; API SDP 形式 <br/>&bull; 远程接收 <br/>&bull; Side BWLimit <br/>&bull; API ServiceQuality <br/>&bull; API SDP <br/>&bull; 接收 SidePDP | 指示应用于流的带宽来源。 | &bull; 未报告传输类型 <br/>&bull; 未建立媒体路径   |
| Bandwidth Est | 整数范围  | 第一和第二终结点之间可用的平均带宽估计值，以"位/秒"为单位。  <br/> **示例值** ：026：[260000 - 270000)   | &bull; 未报告传输类型 <br/>&bull; 未建立媒体路径  |
| Mediation Server Bypass Flag  | 布尔值  | 如果媒体流绕过中介服务器并直接在客户端和 PSTN 网关/PBX 之间传输，则为 True，否则为 False。   | &bull; 未报告传输类型 <br/>&bull; 未建立媒体路径    |
| 第一个 CDR 连接类型  | 枚举 <br/>**可能的值：** <br/>&bull; OS <br/>&bull; PeerDerived <br/>&bull; Stun <br/>&bull; 轮次  | 指示第一终结点选择用于此流的 ICE 连接路径。 <br/> **示例值：** OS  | &bull; 未报告传输类型 <br/>&bull; 未建立媒体路径   |
| 第二个 CDR 连接类型  | 枚举 <br/>**可能的值：** <br/>&bull; OS <br/>&bull; PeerDerived <br/>&bull; Stun <br/>&bull; 轮次  | 指示第二终结点选择用于此流的 ICE 连接路径。  <br/> **示例值：** OS   | &bull; 未报告传输类型 <br/>&bull; 未建立媒体路径   |
|First BSSID|String | 用于连接到网络的第一终结点的无线 LAN 基本服务集标识符。| |
| Second BSSID| String|用于连接到网络的第二终结点的无线 LAN 基本服务集标识符。| |
| 第一个基地址 | String | 第一终结点用于分配媒体中继候选项的接口的 IP 地址。 仅适用于过去 28 天的数据，并且仅对具有允许 EUII 访问的角色的用户可见。 <br/> **示例值** ：10.0.0.10 | &bull; 未报告传输诊断类型 <br/>&bull; 未建立媒体路径 |
| 第二个基地址 | String | 第二终结点用于分配媒体中继候选项的接口的 IP 地址。 仅适用于过去 28 天的数据，并且仅对具有允许 EUII 访问的角色的用户可见。 <br/> **示例值** ：10.0.0.10 | &bull; 未报告传输诊断类型 <br/>&bull; 未建立媒体路径 |
| 第一个本地地址 | String | 媒体连接检查结束时用于媒体流的第一终结点的 IP 地址。 仅适用于过去 28 天的数据，并且仅对具有允许 EUII 访问的角色的用户可见。 <br/> **示例值** ：10.0.0.10 | &bull; 未报告传输诊断类型 <br/>&bull; 未建立媒体路径 |
| 第二个本地地址 | String | 在媒体连接检查结束时用于媒体流的第二终结点的 IP 地址。 仅适用于过去 28 天的数据，并且仅对具有允许 EUII 访问的角色的用户可见。 <br/> **示例值** ：10.0.0.10 | &bull; 未报告传输诊断类型 <br/>&bull; 未建立媒体路径 |
| 第一个本地地址类型 | 枚举 <br/>**可能的值** <br/>&bull;IceAddrType_Os <br/>&bull;IceAddrType_Stun <br/>&bull;IceAddrType_Turn <br/>&bull;IceAddrType_UPnP <br/>&bull;IceAddrType_ISA_Proxy <br/>&bull;IceAddrType_PeerDerived <br/>&bull;IceAddrType_Invalid | 第一个本地地址的候选类型。 IceAddrType_Turn表示中继调用。 其余类型指示直接连接。 | &bull; 未报告传输诊断类型 <br/>&bull; 未建立媒体路径 |
| 第二个本地地址类型 | 枚举 <br/>**可能的值** <br/>&bull;IceAddrType_Os <br/>&bull;IceAddrType_Stun <br/>&bull;IceAddrType_Turn <br/>&bull;IceAddrType_UPnP <br/>&bull;IceAddrType_ISA_Proxy <br/>&bull;IceAddrType_PeerDerived <br/>&bull;IceAddrType_Invalid | 第二个本地地址的候选类型。 IceAddrType_Turn表示中继调用。 其余类型指示直接连接。 | &bull; 未报告传输诊断类型 <br/>&bull; 未建立媒体路径 |
| 第一个远程地址 | String | 第一终结点在媒体连接检查结束时将媒体发送到的第二终结点的 IP 地址。 仅适用于过去 28 天的数据，并且仅对具有允许 EUII 访问的角色的用户可见。 <br/> **示例值** ：10.0.0.10 | &bull; 未报告传输诊断类型 <br/>&bull; 未建立媒体路径 |
| 第二个远程地址 | String | 第二终结点在媒体连接检查结束时将媒体发送到的第一终结点的 IP 地址。 仅适用于过去 28 天的数据，并且仅对具有允许 EUII 访问的角色的用户可见。 <br/> **示例值** ：10.0.0.10 | &bull; 未报告传输诊断类型 <br/>&bull; 未建立媒体路径 |
| 第一个远程地址类型 | 枚举 <br/>**可能的值** <br/>&bull;IceAddrType_Os <br/>&bull;IceAddrType_Stun <br/>&bull;IceAddrType_Turn <br/>&bull;IceAddrType_UPnP <br/>&bull;IceAddrType_ISA_Proxy <br/>&bull;IceAddrType_PeerDerived <br/>&bull;IceAddrType_Invalid | 第一个远程地址的候选类型。 IceAddrType_Turn表示中继调用。 其余值指示直接连接。 | &bull; 未报告传输诊断类型 <br/>&bull; 未建立媒体路径 |
| 第二个远程地址类型 | 枚举  <br/>**可能的值** <br/>&bull;IceAddrType_Os <br/>&bull;IceAddrType_Stun <br/>&bull;IceAddrType_Turn <br/>&bull;IceAddrType_UPnP <br/>&bull;IceAddrType_ISA_Proxy <br/>&bull;IceAddrType_PeerDerived <br/>&bull;IceAddrType_Invalid | 第二个远程地址的候选类型。 IceAddrType_Turn表示中继调用。 其余值指示直接连接。 | &bull; 未报告传输诊断类型 <br/>&bull; 未建立媒体路径 |
| 第一个本地站点 | String | 媒体中继服务器看到的第一终结点的 IP 地址。 这通常是与流的第一终结点关联的公共 Internet IP 地址。 如果出于某种原因中继不可访问或分配失败，这将是第一终结点上本地接口的 IP。 <br/> 这类似于第一个反身本地 IP，但此信息由传输诊断事件而不是 QoE 报告。 仅适用于过去 28 天的数据，并且仅对具有允许 EUII 访问的角色的用户可见。 <br/> **示例值** ：104.43.195.251 | &bull; 未报告传输诊断类型 <br/>&bull; 未建立媒体路径 |
| 第二个本地站点 | String | 媒体中继服务器看到的第二终结点的 IP 地址。 这通常是与流的第二终结点关联的公共 Internet IP 地址。 如果出于某种原因中继不可访问或分配失败，这将是第一终结点上本地接口的 IP。 <br/> 这类似于第二个反身本地 IP，但此信息由传输诊断事件而不是 QoE 报告。 仅适用于过去 28 天的数据，并且仅对具有允许 EUII 访问的角色的用户可见。 <br/> **示例值** ：104.43.195.251 | &bull; 未报告传输诊断类型 <br/>&bull; 未建立媒体路径 |
| 第一个远程站点 | String | 第二终结点报告并和第一终结点交换的本地站点 IP 地址。 <br/> 如果第二终结点上的传输诊断事件出于任何原因不可用，则提供额外信息。 仅适用于过去 28 天的数据，并且仅对具有允许 EUII 访问的角色的用户可见。 <br/> **示例值** ：104.43.195.251 | &bull; 未报告传输诊断类型 <br/>&bull; 未建立媒体路径 |
| Second Remote Site | String | 第一终结点报告并和第二终结点交换的本地站点 IP 地址。 <br/> 如果第一终结点上的传输诊断事件出于任何原因不可用，则提供额外信息。 仅适用于过去 28 天的数据，并且仅对具有允许 EUII 访问的角色的用户可见。 <br/> **示例值** ：104.43.195.251 | &bull; 未报告传输诊断类型 <br/>&bull; 未建立媒体路径 |
| 第一个本地媒体中继地址 | String | 第一终结点分配的媒体中继服务器的 Microsoft IP 地址。 <br/> 此信息类似于第一个中继 IP，但由传输诊断事件而不是 QoE 报告。 <br/> **示例值** ：52.114.5.237 | &bull; 未报告传输诊断类型 <br/>&bull; 未建立媒体路径 |
| 第二个本地媒体中继地址 | String | 第二终结点分配的媒体中继服务器的 Microsoft IP 地址。 <br/> 此信息类似于 Second Relay IP，但由传输诊断事件而不是 QoE 报告。 <br/> **示例值** ：52.114.5.237 | &bull; 未报告传输诊断类型 <br/>&bull; 未建立媒体路径 |
| 第一个远程媒体中继地址 | String | 第二终结点分配并和第一终结点交换的媒体中继服务器的 Microsoft IP 地址。 <br/> 如果第二终结点上的传输诊断事件出于任何原因不可用，则提供额外信息。 <br/> **示例值** ：52.114.5.237 | &bull; 未报告传输诊断类型 <br/>&bull; 未建立媒体路径 |
| 第二个远程媒体中继地址 | String | 第一终结点分配并和第二终结点交换的媒体中继服务器的 Microsoft IP 地址。 <br/> 如果第一终结点上的传输诊断事件出于任何原因不可用，则提供额外信息。 <br/> **示例值** ：52.114.5.237 | &bull; 未报告传输诊断类型 <br/>&bull; 未建立媒体路径 |
| 第一个传输协议 | 枚举字符串 | 第一终结点用于发送媒体的通信协议。 <br/>**可能的值** <br/>&bull;UDP - 用于 TURN 和主机分配的多用途 UDP <br/>&bull;TurnTCP - TCP TURN 分配。 如果指定了代理设置，则使用代理 <br/>&bull;TCPHostPassive - 被动连接类型的 TCP 侦听主机套接字 <br/>&bull;TCPHostActive - 使用活动连接类型的 TCP 连接 <br/>&bull;复合TCP - 上游和下游 TCP 连接的组合。 通常通过 HTTPS 协议。 <br/>&bull;MultiTCP - 一种连接模型，它使用多个 TCP 连接，并使用轮循机制将数据包分发到每个连接。 </br> | &bull; 未报告传输诊断类型 <br/>&bull; 未建立媒体路径 |
| 第二个传输协议 | 枚举字符串 | 第二终结点用于发送媒体的通信协议。 <br/>**可能的值** <br/>&bull;UDP - 用于 TURN 和主机分配的多用途 UDP <br/>&bull;TurnTCP - TCP TURN 分配。 如果指定了代理设置，则使用代理 <br/>&bull;TCPHostPassive - 被动连接类型的 TCP 侦听主机套接字 <br/>&bull;TCPHostActive - 使用活动连接类型的 TCP 连接 <br/>&bull;复合TCP - 上游和下游 TCP 连接的组合。 通常通过 HTTPS 协议。 <br/>&bull;MultiTCP - 一种连接模型，它使用多个 TCP 连接，并使用轮循机制将数据包分发到每个连接。 </br> | &bull; 未报告传输诊断类型 <br/>&bull; 未建立媒体路径 |
|**Device**| |||
| First Capture Dev  | 字符串  | 第一终结点使用的捕获设备的名称。对于：<br/> **音频流** = 用于麦克风的设备 <br/> **视频流** = 用于相机的设备 <br/> **基于视频的屏幕共享流** = 屏幕剪贴器 <br/> **应用共享流** = 空白 <br/> **示例值：** Headset Microphone (Microsoft LifeChat LX-6000)   | &bull; 终结点未报告数据 <br/>&bull; 未建立媒体路径 <br/>&bull; 流是基于视频的屏幕共享或应用程序共享。  |
| Second Capture Dev  | 字符串  | 第二终结点使用的捕获设备的名称。  <br/> **音频流** = 用于麦克风的设备 <br/> **视频流** = 用于相机的设备 <br/> **基于视频的屏幕共享流** = 屏幕剪贴器 <br/> **应用共享流** = 空白 <br/> **示例值：** Headset Microphone (Microsoft LifeChat LX-6000)  | <br/>&bull; 终结点未报告数据 <br/>&bull; 未建立媒体路径 <br/>&bull; 流是基于视频的屏幕共享或应用程序共享   |
| First Capture Dev Driver  | 字符串  | 第一终结点使用的捕获设备驱动器的名称，格式为"制造商: 版本"。对于：<br/> **音频流** = 用于麦克风的驱动程序 <br/> **视频流** = 用于相机的驱动程序 <br/> **基于视频的屏幕共享与应用共享流** = 空白  <br/> **示例值：** Microsoft：10.0.14393.0 | <br/>&bull; 终结点未报告数据 <br/>&bull; 未建立媒体路径 <br/>&bull; 流是基于视频的屏幕共享或应用程序共享。  |
| Second Capture Dev Driver  | 字符串  | 第二终结点使用的捕获设备驱动器的名称，格式为"制造商: 版本"。对于：<br/> **音频流** = 用于麦克风的驱动程序 <br/> **视频流** = 用于相机的驱动程序 <br/> **基于视频的屏幕共享与应用共享流** = 空白 <br/> **示例值：** Microsoft：10.0.14393.0  | <br/>&bull; 终结点未报告数据 <br/>&bull; 未建立媒体路径 <br/>&bull; 流是基于视频的屏幕共享或应用程序共享。  |
| First Render Dev  | 字符串  | 第一终结点使用的呈现设备的名称。对于：<br/> 音频流 - 用于扬声器的设备 <br/> 基于视频和基于视频的屏幕共享流 - 用于显示的设备 <br/> 应用共享流 - 空  <br/> **示例值：** Headset Earphone (Microsoft LifeChat LX-6000)  | <br/>&bull; 终结点未报告此数据 <br/>&bull; 未建立媒体路径  <br/>&bull; 流是应用程序共享    |
| Second Render Dev  | 字符串  | 第二终结点使用的呈现设备的名称。对于：<br/> 音频流 - 用于扬声器的设备 <br/> 基于视频和基于视频的屏幕共享流 - 用于显示的设备 <br/> 应用共享流 - 空 <br/> **示例值：** Headset Earphone (Microsoft LifeChat LX-6000)  | <br/>&bull; 终结点未报告此数据， <br/>&bull; 未建立媒体路径 <br/>&bull; 流是应用程序共享     |
| First Render Dev Driver  | 字符串  | 第一终结点使用的呈现设备驱动器的名称。对于：<br/> 音频流 - 用于扬声器的驱动程序 <br/> 基于视频和基于视频的屏幕共享流 - 用于显示的驱动程序 <br/> 应用共享流 - 空  <br/> **示例值：** Microsoft：10.0.14393.0 | <br/>&bull; 终结点未报告此数据 <br/>&bull; 未建立媒体路径 <br/>&bull; 流是应用程序共享    |
| Second Render Dev Driver  | 字符串  | 第二终结点使用的呈现设备驱动器的名称。对于：<br/> 音频流 - 用于扬声器的驱动程序 <br/> 基于视频和基于视频的屏幕共享流 - 用于显示的驱动程序 <br/> 应用共享流 - 空 <br/> **示例值：** Microsoft：10.0.14393.0  | <br/>&bull; 终结点未报告此数据 <br/>&bull; 未建立媒体路径 <br/>&bull; 流是应用程序共享   |
|**WiFi**|||
| First Wi-Fi Microsoft Driver  | 字符串  | 第一终结点报告的所使用的 Microsoft WiFi 驱动器的名称。值可能会根据终结点使用的语言进行本地化。<br/> **示例值：** Microsoft 托管的网络虚拟适配器  | <br/>&bull; 终结点未使用 WiFi <br/>&bull; 未报告驱动程序信息|
| Second Wi-Fi Microsoft Driver  | 字符串  | 第二终结点报告的所使用的 Microsoft WiFi 驱动器的名称。值可能会根据终结点使用的语言进行本地化。<br/> **示例值：** Microsoft 托管的网络虚拟适配器  | <br/>&bull; 终结点未使用 WiFi <br/>&bull; 未报告驱动程序信息|
| First Wi-Fi Vendor Driver  | 字符串  | 第一终结点报告的 Wifi 驱动器的供应商和名称。 <br/> **示例值：** Contoso 双频无线 AC 驱动程序  | <br/>&bull; 终结点未使用 WiFi <br/>&bull; 未报告驱动程序信息 |
| Second Wi-Fi Vendor Driver  | 字符串  | 第二终结点报告的 Wifi 驱动器的供应商和名称。  <br/> **示例值：** Contoso 双频无线 AC 驱动程序 | <br/>&bull; 终结点未使用 WiFi <br/>&bull; 未报告驱动程序信息 |
| 第一Wi-Fi Microsoft 驱动程序版本  | 字符串  | 第一终结点报告的 Microsoft Wifi 驱动器的版本。 <br/> **示例值：** Microsoft：10.0.14393.0 | <br/>&bull; 终结点未使用 WiFi <br/>&bull; 未报告驱动程序信息  |
| 第二Wi-Fi Microsoft 驱动程序版本  | 字符串  | 第二终结点报告的 Microsoft Wifi 驱动器的版本。 <br/> **示例值：** Microsoft：10.0.14393.0 | <br/>&bull; 终结点未使用 WiFi <br/>&bull; 未报告驱动程序信息  |
| 第一Wi-Fi供应商驱动程序版本  | 字符串  | 第一终结点报告的 Wifi 驱动器的供应商和版本。 <br/> **示例值：** Contoso：15.1.1.0 | <br/>&bull; 终结点未使用 WiFi <br/>&bull; 未报告驱动程序信息  |
| 第二Wi-Fi供应商驱动程序版本  | 字符串  | 第二终结点报告的 Wifi 驱动器的供应商和版本。 <br/> **示例值：** Contoso：15.1.1.0 | <br/>&bull; 终结点未使用 WiFi <br/>&bull; 未报告驱动程序信息  |
| First Wi-Fi Channel  | 字符串  | 第一终结点使用的 Wifi 频道。  <br/> **示例值：10**| <br/>&bull; 未使用 WiFi <br/>&bull; 未报告频道   |
| 第二Wi-Fi频道  | 字符串  | 第二终结点使用的 Wifi 频道。 <br/> **示例值：10**  | <br/>&bull; 未使用 WiFi <br/>&bull; 未报告频道  |
| 第一Wi-Fi单选类型  | 字符串  | 第一终结点使用的 WiFi 无线电的类型。HRDSSS 等于 802.11b。<br/> **示例值** ：802.11ac  | <br/>&bull; 未使用 WiFi <br/>&bull; 未报告 WiFi 类型  |
| 第二Wi-Fi无线电类型  | 字符串  | 第二终结点使用的 WiFi 无线电的类型。HRDSSS 等于 802.11b。<br/> **示例值** ：802.11ac  | <br/>&bull; 未使用 WiFi <br/>&bull; 未报告 WiFi 类型  |
| First DNS Suffix  | 字符串  | 第一终结点报告的与网络适配器关联的 DNS 后缀。 请注意，可能会为任何类型的网络适配器报告此值。 **示例值：corp** <span></span> .contoso <span></span> .com  | <br/>&bull; 终结点未报告此值 <br/>  |
| Second DNS Suffix  | 字符串  | 第二终结点报告的与网络适配器关联的 DNS 后缀。请注意，可能会为任何类型的网络适配器报告此值。<br/> **示例值：corp** <span></span> .contoso <span></span> .com   | <br/>&bull; 终结点未报告此值  |
| First Wi-Fi Band  | 字符串  | 第一终结点报告的所使用的 Wifi 波段。 <br/> **示例值** ：5.0 Ghz  | <br/>&bull; 终结点未计算该值 <br/>&bull; 未报告值  |
| Second Wi-Fi Band  | 字符串  | 第二终结点报告的所使用的 Wifi 波段。 <br/> **示例值** ：5.0 Ghz  | <br/>&bull; 终结点未计算该值 <br/>&bull; 未报告值  |
| 第一Wi-Fi信号强度  | String  | 第一终结点报告的 WiFi 信号强度百分比 [0-100]。 <br/> **示例值** ：081：[90 - 100)   | <br/>&bull; 终结点未计算该值 <br/>&bull; 未报告值  |
| Second Wi-Fi Signal Strength  | String  | 第二终结点报告的 WiFi 信号强度百分比 [0-100]。 <br/> **示例值** ：081：[90 - 100)   | <br/>&bull; 终结点未计算该值 <br/>&bull; 未报告值  |
| 首次Wi-Fi电池充电  | 范围（百分比）  | 第一终结点报告的电池剩余电量的百分比估计值 [0-99]。值按范围分组表示。0 表示设备已插电。<br/> **示例值** ：081：[90 - 100)  | &bull; 未使用 WiFi <br/>&bull; 未报告费用值   |
| 第二Wi-Fi电池充电  | 范围（百分比）  | 第二终结点报告的电池剩余电量的百分比估计值 [0-99]。值按范围分组表示。0 表示设备已插电。<br/> **示例值** ：081：[90 - 100)  | &bull; 未使用 WiFi <br/>&bull; 未报告费用值  |
|**指标**|||
| Audio Degradation Avg  | 范围（平均意见得分 0-5） | 关于流降级的网络平均意见得分的平均值。 表示网络丢失和抖动对接收音频质量的影响。 值按范围分组表示。 <br/> **示例值** ：015：[0.01 - 0.02)  | &bull; 接收流的终结点未报告网络 MOS 降级 <br/>&bull; 流不是音频流。    |
| Jitter  | 范围（毫秒）  | 流的平均抖动值，以毫秒为单位。值按范围分组表示。<br/> **示例值** ：065：[2 - 3)   | &bull; 接收流的终结点未报告抖动数据 |
| Jitter Max  | 范围（毫秒）  | 流的最大抖动值，以毫秒为单位。值按范围分组表示。<br/> **示例值** ：065：[2 - 3)  | &bull; 接收流的终结点未报告抖动数据   |
| Packet Loss Rate  | 范围（比率）  | 流的平均丢包率。 值按范围分组表示。 0.1 表示数据包丢失 10%。 <br/> **示例值** ：015：[0.01 - 0.02)   | &bull; 接收流的终结点未报告数据包丢失数据 |
| Packet Loss Rate Max  | 范围（比率）  | 流的最大丢包率。 值按范围分组表示。 0.1 表示数据包丢失 10%。 <br/> **示例值** ：023：[0.09 - 0.1)   | &bull; 接收流的终结点未报告数据包丢失数据  <br/>&bull; 给定流的数据包利用率小于 100 数据包 |
| Overall Avg Network MOS  | 范围 (MOS)  | 流的网络 MOS 平均值。值按范围分组表示。<br/> **示例值** ：076：[4.4 - 4.5)  | &bull; 接收流的终结点未报告网络 MOS 降级 <br/>&bull; 流不是音频流  |
| Ratio Concealed Samples Avg  | 范围（比率）  | 含有丢包隐藏生成样本的音频帧数与总音频帧数的比率。值按范围分组表示。0.1 表示 10% 的帧包含隐藏样本。<br/> **示例值** ：015：[0.01 - 0.02)  | &bull; 流接收方未报告此值 <br/>&bull; 流不是音频流  |
|隐藏比率最大值 |范围（比率） | 具有数据包丢失隐藏生成的样本的音频帧的最大可见数量到音频帧的总数。 值按范围分组表示。 0.1 表示 10% 的帧包含隐藏样本。 <br/> **示例值** ：015：[0.01 - 0.02) | |
| Ratio Stretched Samples Avg  | 范围（比率）  | 通过拉伸样本补偿抖动或丢失的音频帧数与总音频帧数的比率。值按范围分组表示。0.1 表示 10% 的音频帧包含拉伸样本。<br/> **示例值** ：017：[0.03 - 0.04)  | &bull; 流接收方未报告此值  <br/>&bull; 流不是音频流   |
|修复器数据包丢弃率|范围（比率） |由修复程序丢弃的音频数据包与修复程序收到的音频数据包总数的比率。 有关详细信息 [，请参阅 2.2.1.12.1](/openspecs/office_protocols/ms-qoe/56d41628-26d5-44c8-8f79-6bac4b0355a5) 子元素。| |
| 修复程序 FEC 数据包使用比率| 范围（比率）  |已用转发错误更正 (FEC) 数据包数与已接收 FEC 数据包总数的比率。 有关详细信息 [，请参阅 2.2.1.12.1](/openspecs/office_protocols/ms-qoe/56d41628-26d5-44c8-8f79-6bac4b0355a5) 子元素。  | |
| Round Trip  | 范围（毫秒）  | 计算的平均网络传播往返时间，根据 RFC3550 以毫秒为单位指定。值按范围分组表示。<br/> **示例值** ：070：[15 - 20)   | <br/>&bull; 终结点未计算该值 <br/>&bull; 未报告值  |
| Round Trip Max  | 范围（毫秒）  | 计算的最大网络传播往返时间，根据 RFC3550 以毫秒为单位指定。值按范围分组表示。<br/>**示例值** ：098：[350 - 375)    | <br/>&bull; 终结点未计算该值 <br/>&bull; 未报告值 |
| 数据包利用率 | 数据包 (个)  |在Real-Time发送 (RTP) 传输协议数。|
| 抖动缓冲区大小平均值|数字 (范围)  |会话期间抖动缓冲区的平均大小。| |
| 抖动缓冲区大小最大值|数字 (范围) |会话期间抖动缓冲区的最大大小。 |
| 抖动缓冲区大小最小值|数字 (范围) |会话期间抖动缓冲区的最小大小。|
|相对 OneWay 间距持续时间| 对等的相对单向延迟的间隙持续时间。||
| Audio Post FECPLR|  数字 |在 FEC 应用于音频后报告数据包丢失率。 介于 0.00 和 1.00 之间的值。| |
| Network Jitter Avg  | 范围（毫秒）  | 会话期间以 20 秒时间窗口计算的平均网络抖动，以毫秒为单位。值按范围分组表示。<br/> **示例值** ：066：[3–4)   | <br/>&bull; 流不是音频流 <br/>&bull; 接收流的终结点未报告数据  |
|网络抖动最大值|事件数|会话期间在 20 秒时段内计算的网络抖动最大值。|
| 网络抖动最小值|事件数|会话期间在 20 秒时段内计算的最小网络抖动。| |
| Video Post FECPLR  | 范围（比率）  | 应用 FEC 后，跨所有视频流和编解码器汇总的丢包率。值按范围分组表示。<br/> **示例值** ：014：[0 - 0.01)  | <br/>&bull; 流不是基于视频或基于视频的屏幕共享流  <br/>&bull; 接收流的终结点未报告数据   |
| Video Local Frame Loss Percentage Avg  | 范围（百分比）  | 向用户显示的视频帧丢失平均百分比。值按范围分组表示。其中包括从网络丢失恢复的帧。<br/> **示例值** ：160：[80 - 85)  | <br/>&bull; 流不是基于视频或基于视频的屏幕共享流  <br/>&bull; 接收流的终结点未报告数据   |
| 接收帧速率平均值  | 范围（每秒帧数）  | 在会话持续期间计算到的所有视频流每秒接收的平均帧数。值按范围分组表示。<br/> **示例值** ：101：[14.5 - 15)  | <br/>&bull; 流不是基于视频或基于视频的屏幕共享流  <br/>&bull; 接收流的终结点未报告数据   |
| Low Frame Rate Call Percent | 范围（百分比）  | 帧速率低于 7.5 帧/秒的通话时间的百分比。值按范围分组表示。<br/> **示例值** ：099：[13.5 - 14)  | <br/>&bull; 流不是基于视频或基于视频的屏幕共享流  <br/>&bull; 接收流的终结点未报告数据   |
| Video Packet Loss Rate  | 范围（比率）  | 在会话持续期间计算到的平均丢包比率（小数），根据 RFC3550 指定。值按范围分组表示。<br/> **示例值** ：037：[0.75 - 0.8)  | <br/>&bull; 流不是基于视频或基于视频的屏幕共享流  <br/>&bull; 接收流的终结点未报告数据   |
| Video Frame Rate Avg  | 范围（每秒帧数）  | 在会话持续期间计算到的视频流每秒接收的平均帧数。值按范围分组表示。<br/> **示例值** ：135：[31.5 - 32)   | <br/>&bull; 流不是基于视频或基于视频的屏幕共享流  <br/>&bull; 接收流的终结点未报告数据  |
| Dynamic Capability Percent  | 范围（百分比）  | 客户端以低于此类型 CPU 预期视频处理容量的 70% 运行的时间的百分比，按范围分组。 <br/> **示例值** ：122：[25 - 25.5)   | <br/>&bull; 流不是基于视频或基于视频的屏幕共享流  <br/>&bull; 接收流的终结点未报告数据  |
| Spoiled Tile Percent Total  | 范围（百分比）  | 没有被发送到远程对等点（例如，从 MCU 到查看器）而是被丢弃的图块的百分比。值按范围分组表示。丢弃图块可能是由于客户端与服务器之间的带宽限制所致。<br/> **示例值** ：140：[34 - 34.5)   | <br/>&bull; 流不是应用程序共享流 <br/>&bull; 发送流的终结点未报告数据  |
| AppSharing Relative OneWay Average  | 范围（秒）  | 应用程序共享流的终结点之间的平均单向延迟，以秒数表示。 值按范围分组表示。 <br/> **示例值** ：015：[0.01 - 0.02)  | <br/>&bull; 流不是应用程序共享流 <br/>&bull; 发送流的终结点未报告数据   |
| AppSharing RDP Tile Processing Latency Average  | 范围（毫秒）  | 在会议服务器上处理 RDP 堆栈图块的平均延迟，以毫秒为单位。值按范围分组表示。<br/> **示例值** ：103：[15.5 - 16)  | &bull; 流不是会议中的应用程序共享流 <br/>&bull; 发送流的终结点未报告数据   | 
| First Network Delay Event Ratio  | 范围（比率）  | 满足以下条件的通话的比率（小数）：第一终结点检测到网络延迟足以影响实时双向通信能力。值按范围分组表示。<br/> **示例值** ：016：[0.02 - 0.03)   | &bull; 这是非音频流 <br/>&bull; 第一终结点未报告数据|
| Second Network Delay Event Ratio  | 范围（比率）  | 满足以下条件的通话的比率（小数）：第二终结点检测到网络延迟足以影响实时双向通信能力。值按范围分组表示。<br/> **示例值** ：016：[0.02 - 0.03)   | &bull; 指示非音频流 <br/>&bull; 第二终结点未报告数据 |
| First Network Bandwidth Low Event Ratio  | 范围（比率）  | 满足以下条件的通话的比率（小数）：第一终结点检测到可用带宽或带宽策略低到足以导致已发送音频的质量差。值按范围分组表示。<br/> **示例值** ：016：[0.02 - 0.03)  | &bull; 这是非音频流 <br/>&bull; 第一终结点未报告数据  |
| Second Network Bandwidth Low Event Ratio  | 范围（比率）  | 满足以下条件的通话的比率（小数）：第二终结点检测到可用带宽或带宽策略低到足以导致已发送音频的质量差。值按范围分组表示。<br/> **示例值** ：016：[0.02 - 0.03)  | &bull; 指示非音频流 <br/>&bull; 第二终结点未报告数据 |
| First Mic Glitch Rate| 数字 |第一终结点的麦克风捕获每 5 分钟的平均故障数。 有关详细信息 [，请参阅 2.2.1.12.1](/openspecs/office_protocols/ms-qoe/56d41628-26d5-44c8-8f79-6bac4b0355a5) 子元素。 |
| Second Mic Glitch Rate|数字 |第二终结点的麦克风捕获每 5 分钟的平均故障数。 有关详细信息 [，请参阅 2.2.1.12.1](/openspecs/office_protocols/ms-qoe/56d41628-26d5-44c8-8f79-6bac4b0355a5) 子元素。 |
| 第一个扬声器故障率|事件数|第一个扬声器呈现时每 5 分钟的平均故障数。| |
| 第二个扬声器故障率|事件数|第二个扬声器呈现时每 5 分钟的平均故障数。| |
|**音频**|||
| Audio FEC Used  | 布尔值  | True 表示通话期间在某些点上使用了音频前向纠错 (FEC)。False 表示未使用。     | &bull; 流不是音频流 <br/>&bull; 发送流的终结点未报告数据  |
|**Measure**|||
| ClassifiedPoorCall  | 布尔值  | 如果根据呼叫质量仪表板中的流分类中列出的指标将呼叫中的一个或多个流分类为差，[为 True。](stream-classification-in-call-quality-dashboard.md)   | &bull; 调用没有足够的指标报告被分类为好或差   |
| Video Poor Due To VideoPostFecplr  | 布尔值  | 如果根据以下文章中列出的"FEC PLR 后的视频"指标阈值将流分类为差，则为 True：呼叫质量仪表板 [中的流分类](stream-classification-in-call-quality-dashboard.md)。 对于非视频流，始终为 False。   | &bull; 终结点未报告此数据  <br/>&bull; 流不是视频流。  |
| Video Poor Due To VideoLocalFrameLossPercentageAvg  | Boolean  | 如果根据以下位置列出的视频本地帧丢失百分比平均值指标阈值将视频流分类为差，则为 [True：呼叫质量仪表板中的流分类](stream-classification-in-call-quality-dashboard.md)。 对于非视频流，始终为 False。   | &bull; 终结点未报告此数据  <br/>&bull; 流不是视频流。 |
| Video Poor Due To VideoFrameRateAvg  | Boolean  | 如果根据以下位置中列出的视频帧速率平均指标阈值将视频流分类为差，则为 True：呼叫质量仪表板 [中的流分类](stream-classification-in-call-quality-dashboard.md)。 对于非视频流，始终为 False。    | &bull; 终结点未报告此数据  <br/>&bull; 流不是视频流 |
| VBSS Poor Due To VideoPostFecplr  | Boolean  | 如果基于视频的屏幕共享流根据以下文章中列出的视频发布 FEC PLR 指标阈值被分类为差，则为 True：呼叫质量仪表板中的 [流分类](stream-classification-in-call-quality-dashboard.md)。 对于非基于视频的屏幕共享流，始终为 False。    | &bull; 终结点未报告此数据 <br/>&bull; 流不是基于视频的屏幕共享流  |
| VBSS Poor Due To VideoLocalFrameLossPercentageAvg  | Boolean  | 如果基于视频的屏幕共享流根据以下位置列出的视频本地帧丢失百分比平均指标阈值被分类为差，则为 True：呼叫质量仪表板中的 [流分类](stream-classification-in-call-quality-dashboard.md)。 对于非基于视频的屏幕共享流，始终为 False。    | &bull; 终结点未报告此数据 <br/>&bull; 流不是基于视频的屏幕共享流  |
| Video Poor Due To Freeze | Boolean  | 1：根据视频冻结实例将视频流分类为差：呼叫质量仪表板 [中的流分类](stream-classification-in-call-quality-dashboard.md) | &bull; 终结点未报告此数据  <br/>&bull; 流不是视频流。 此字段特定于Microsoft Teams字段。 |
| VBSS Poor Due To VideoFrameRateAvg  | Boolean  | 如果基于视频的屏幕共享流根据以下位置列出的视频帧速率平均指标阈值被分类为差，则为 [True：](stream-classification-in-call-quality-dashboard.md)呼叫质量仪表板中的流分类。 对于非基于视频的屏幕共享流，始终为 False。   | &bull; 终结点未报告此数据 <br/>&bull; 流不是基于视频的屏幕共享流   |
| AppSharing Poor Due To SpoiledTilePercentTotal  | Boolean  | 如果根据以下位置中列出的"损坏的平铺百分比总计"指标阈值将应用程序共享流分类为差，则为 [True：呼叫质量仪表板中的流分类](stream-classification-in-call-quality-dashboard.md)。 对于非应用程序共享流，始终为 False。   | &bull; 终结点未报告此数据  <br/>&bull; 流不是应用程序共享流。  |
| AppSharing Poor Due To RelativeOneWayAverage  | Boolean  | 如果根据以下位置中列出的"相对单向平均"指标阈值将应用程序共享流分类为差，则为 True：呼叫质量仪表板中的 [流分类](stream-classification-in-call-quality-dashboard.md)。 对于非应用程序共享流，始终为 False。    | &bull; 终结点未报告此数据  <br/>&bull; 流不是应用程序共享流 |
| AppSharing Poor Due To RDPTileProcessingLatencyAverage | Boolean  | 如果根据以下位置列出的 RDP 平铺处理延迟平均指标阈值将应用程序共享流分类为差，则为 [True：呼叫质量仪表板中的流分类](stream-classification-in-call-quality-dashboard.md)。 对于非应用程序共享流，始终为 False。    | &bull; 终结点未报告此数据  <br/>&bull; 流不是应用程序共享流 |
| Audio Poor Due To Jitter  | 布尔值  | 如果根据以下位置列出的抖动指标阈值将音频流分类为差，则为 [True：呼叫质量仪表板中的流分类](stream-classification-in-call-quality-dashboard.md)。 对于非音频流，始终为 False。    | &bull; 终结点未报告此数据 <br/>&bull; 流不是音频共享流 |
| Audio Poor Due To RoundTrip  | 布尔值  | 如果根据以下位置列出的往返行程指标阈值将音频流分类为差，则为 [True：呼叫质量仪表板中的流分类](stream-classification-in-call-quality-dashboard.md)。 对于非音频流，始终为 False。   | &bull; 终结点未报告此数据 <br/>&bull; 流不是音频共享流 |
| Audio Poor Due To Packet Loss  | 布尔值  | 如果根据以下位置中列出的数据包丢失指标阈值将音频流分类为差，则为 [True：呼叫质量仪表板中的流分类](stream-classification-in-call-quality-dashboard.md)。 对于非音频流，始终为 False。    | &bull; 终结点未报告此数据 <br/>&bull; 流不是音频共享流 |
| Audio Poor Due To Degradation  | 布尔值  | 如果根据以下位置中列出的降级指标阈值将音频流分类为差，则为 [True：呼叫质量仪表板中的流分类](stream-classification-in-call-quality-dashboard.md)。 对于非音频流，始终为 False。    | &bull; 终结点未报告此数据 <br/>&bull; 流不是音频共享流 |
| Audio Poor Due To Concealed Ratio  | 布尔值  | 如果根据以下位置中列出的"隐藏比率"指标阈值将音频流分类为差，则为 True：呼叫质量仪表板中的 [流分类](stream-classification-in-call-quality-dashboard.md)。 对于非音频流，始终为 False。    | &bull; 终结点未报告此数据 <br/>&bull; 流不是音频共享流 |
| Poor Reason  | 标志 <br/>**可能的值：** <br/>&bull; 隐藏比率 <br/>&bull; 降级 <br/>&bull; 抖动 <br/>&bull; 数据包丢失 <br/>&bull; 往返行程 <br/> Video Frame Rate Avg <br/> Video Local Frame Loss Percentage Avg <br/>&bull; 视频 FEC PLR 发布后 <br/>&bull; RDP 平铺处理平均延迟 <br/>&bull; 相对 OneWay 平均值 <br/>&bull; 损坏的平铺百分比总计 | 用于确定为何将流分类为差的一系列标志。 由于将流分类为差的原因有很多，因此可能会有设置多个标记。 有关详细信息， [请参阅呼叫质量仪表板中的](stream-classification-in-call-quality-dashboard.md) 流分类。  | &bull; 流未分类为差 |
| Poor  | 布尔值  | 如果流有足够的数据被分类为好或差，并且流被分类为差，则为 True。 否则为 False。   |   |
| Good  | 布尔值  | 如果流有足够的数据被分类为好或差，并且流被分类为良好，则为 True。 否则为 False。   |   |
| Unclassified  | 布尔值  | 如果流有足够的数据被分类为好或差，为 False。 否则为 True。 <br/>**示例值：1** |   |
| OnePercent PacketLoss  | 布尔值  | 如果丢包率超过 1%，则为 True;否则为 False。  |   |
|**分级**|||
| First Feedback Rating  | 用户评级 (1-5)  | 第一终结点对与流关联的通话进行的评级，等级为 1-5（5 = 很好）。0 表示向用户显示了通话评级调查，但用户没有对其体验进行评级。<br/> **示例值：5** | &bull; 未向第一终结点显示调查  |
| Second Feedback Rating  | 用户评级 (1-5)  | 第二终结点对与流关联的通话进行的评级，等级为 1-5（5 = 很好）。0 表示向用户显示了通话评级调查，但用户没有对其体验进行评级。<br/> **示例值：5** | &bull; 未向第二终结点显示调查   |
| First Feedback Tokens  | 字符串  | 包含反馈令牌列表的字符串，其布尔标志指示令牌是否由提供第一终结点反馈的用户设置。 <br/> **示例值** ：{DistortedSpeech：1;ElectronicFeedback：1;BackgroundNoise：1;MuffledSpeech：1;Echo：1;}  | &bull; 第一终结点的用户未提供反馈  |
| Second Feedback Tokens  | 字符串  | 包含反馈令牌列表的字符串，其布尔标志指示令牌是否由提供第二终结点反馈的用户设置。 <br/> **示例值** ：{DistortedSpeech：1;ElectronicFeedback：1;BackgroundNoise：1;MuffledSpeech：1;Echo：1;}  | &bull; 第二终结点的用户未提供反馈  |
| First Feedback Has Audio Issue  | 布尔值  | 如果第一终结点的反馈标记指出流包含音频问题，则为 True，否则为 False。   |  |
| Second Feedback Has Audio Issue  | 布尔值  | 如果来自第二终结点的反馈令牌指示流存在音频问题，则为 True，否则为 False。    ||
| First Feedback Has Video Issue  | 布尔值  | 如果来自第一终结点的反馈令牌指示流存在视频问题，则为 True，否则为 False。    | |
| Second Feedback Has Video Issue  | 布尔值  | 如果来自第二终结点的反馈令牌指示流存在视频问题，则为 True，否则为 False。    | |
| First Feedback Has AppSharing Issue  | Boolean  | 如果来自第一终结点的反馈令牌指示流存在应用共享问题，则为 True。 否则为 False。 | |  
| Second Feedback Has Appsharing Issue  | Boolean  | 如果来自第二终结点的反馈令牌指示流存在应用共享问题，则为 True。 否则为 False。 | |  
|**音频信号**|||
| First Echo Event Causes  | 标志  | 指示第一终结点上发生设备回声事件的原因的标志。一个流可能拥有多个标志。标志包括：<br/> BAD_TIMESTAMP - 从所使用的具有较差质量的捕获设备或呈现设备上获得的音频时间戳 <br/> POSTAEC_ECHO - 消除回声后仍具有较高水平的回声 <br/> MIC_CLIPPING - 拥有最大信号强度显著实例的捕获设备上的信号强度 <br/> EVENT_ANLP - 包含高噪音的捕获设备上的音频采样。 <br/> **示例值：** BAD_TIMESTAMP | &bull; 这是非音频流 <br/>&bull; 第一终结点未报告任何事件原因  |
| Second Echo Event Causes  | 标志  | 指示第二终结点上发生设备回声事件的原因的标志。一个流可能拥有多个标志。标志包括：<br/> BAD_TIMESTAMP - 从所使用的具有较差质量的捕获设备或呈现设备上获得的音频时间戳 <br/> POSTAEC_ECHO - 消除回声后仍具有较高水平的回声 <br/> MIC_CLIPPING - 拥有最大信号强度显著实例的捕获设备上的信号强度 <br/> EVENT_ANLP - 包含高噪音的捕获设备上的音频采样。 <br/> **示例值：** BAD_TIMESTAMP   | &bull; 这是非音频流 <br/>&bull; 第一终结点未报告任何事件原因 |
| First Echo Percent Mic In  | 范围（百分比）  | 在消除回声之前，第一终结点从捕获设备或麦克风设备检测到音频中存在回声的时间百分比。值按范围分组表示。<br/> **示例值** ：068：[5 - 10)   | &bull; 这是非音频流 <br/>&bull; 第一终结点未报告数据 |
| Second Echo Percent Mic In  | 范围（百分比）  | 在消除回声之前，第二终结点从捕获设备或麦克风设备检测到音频中存在回声的时间百分比。值按范围分组表示。<br/> **示例值** ：068：[5 - 10)  | &bull; 指示非音频流 <br/>&bull; 第二终结点未报告数据 |
| First Echo Percent Send  | 范围（百分比）  | 消除回声后，第一终结点在音频中检测到回声的时间百分比。 值按范围分组表示。 <br/> **示例值** ：068：[5 - 10)   | &bull; 这是非音频流 <br/>&bull; 第一终结点未报告数据 |
| Second Echo Percent Send  | 范围（百分比）  | 第二终结点取消回声后在音频中检测到回声的时间百分比。 值按范围分组表示。 <br/> **示例值** ：068：[5 - 10)  | &bull; 指示非音频流 <br/>&bull; 第二终结点未报告数据 |
| First Send Signal Level  | 范围（dB、分贝）  | 对于被分类为单声道语音或左声道立体声语音的音频，第一终结点发送的音频的平均能量水平。值按范围分组表示。<br/> **示例值** ：055：[-15 - -10)  | &bull; 这是非音频流 <br/>&bull; 第一终结点未报告数据 |
| Second Send Signal Level  | 范围（dB、分贝）  | 对于被分类为单声道语音或左声道立体声语音的音频，第二终结点发送的音频的平均能量水平。值按范围分组表示。<br/> **示例值** ：055：[-15 - -10)  | &bull; 指示非音频流 <br/>&bull; 第二终结点未报告数据  |
| 首次接收信号级别  | 范围（dB、分贝）  | 对于被分类为单声道语音或左声道立体声语音的音频，第一终结点接收的音频的平均能量水平。值按范围分组表示。<br/> **示例值** ：056：[-10 - -5)   | &bull; 这是非音频流 <br/>&bull; 第一终结点未报告数据 |
| Second Received Signal Level  | 范围（dB、分贝）  | 对于被分类为单声道语音或左声道立体声语音的音频，第二终结点接收的音频的平均能量水平。值按范围分组表示。<br/> **示例值** ：056：[-10 - -5)  | &bull; 指示非音频流 <br/>&bull; 第二终结点未报告数据  |
| First Send Noise Level  | 范围（dB、分贝）  | 被分类为单声道噪音或左声道立体声噪音的音频的平均能量水平（由第一终结点发送）。 值按范围分组表示。 <br/> **示例值** ：048：[-50 - -45)   | &bull; 这是非音频流 <br/>&bull; 第一终结点未报告数据 |
| Second Send Noise Level  | 范围（dB、分贝）  | 第二终结点分类为单声道噪音或立体声左声道噪音的音频的平均能量水平。 值按范围分组表示。 <br/> **示例值** ：048：[-50 - -45)   | &bull; 指示非音频流 <br/>&bull; 第二终结点未报告数据 |
| 首次接收的噪音级别  | 范围（dB、分贝）  | 第一终结点收到的单声道噪音或立体声左声道噪音的平均能量水平。 值按范围分组表示。 <br/> **示例值** ：048：[-50 - -45)   | &bull; 这是非音频流 <br/>&bull; 第一终结点未报告数据 |
| Second Received Noise Level  | 范围（dB、分贝）  | 第二终结点收到的单声道噪音或立体声左声道噪音的平均能量水平。 值按范围分组表示。 <br/> **示例值** ：048：[-50 - -45)   | &bull; 指示非音频流 <br/>&bull; 第二终结点未报告数据 |
|First Initial Signal Level RMS | 范围（dB、分贝） | 第一终结点 (30) 接收信号的 RMS 的均方根数。 请参阅 [2.2.1.28.1 子元素](/openspecs/office_protocols/ms-qoe/3c78f383-73fe-49f6-89cb-614e7aa8b2e7)  | |
| Second Initial Signal Level RMS |范围（dB、分贝） | RMS 的根均方 (表示) 终结点的调用前 30 秒收到的信号。 有关详细信息 [，请参阅 2.2.1.28.1](/openspecs/office_protocols/ms-qoe/3c78f383-73fe-49f6-89cb-614e7aa8b2e7) 子元素。||
| First RxAGC Signal Level |范围（dB、分贝）| 在 AGC 的自动增益控制 (接收) 第一个入站音频流的信号级别。| |
| Second RxAGC Signal Level |范围（dB、分贝）|在 AGC 的自动增益控制 (接收) 第二个入站音频流的信号级别。|| 
| First RxAGC Noise Level|范围（dB、分贝）|第一个入站音频流的 AGC (AGC) 接收的噪音级别。 ||
| Second RxAGC Noise Level|范围（dB、分贝）|第二个入站音频流的 AGC (AGC) 接收的噪音级别。||
| First Render Loopback Signal Level |范围（dB、分贝）| 第一个入站音频流的环回信号级别。 ||
| Second Render Loopback Signal Level |范围（dB、分贝）|第二个入站音频流的环回信号级别。||
|**客户端事件** |||
| First Network Send Quality Event Ratio  | 范围（比率）  | 满足以下条件的通话的比率（小数）：第一终结点检测到网络导致已发送音频的质量差。值按范围分组表示。<br/> **示例值** ：015：[0.01 - 0.02)    | &bull; 指示非音频流 <br/>&bull; 第一终结点未报告数据|
| Second Network Send Quality Event Ratio  | 范围（比率）  | 满足以下条件的通话的比率（小数）：第二终结点检测到网络导致已发送音频的质量差。值按范围分组表示。<br/> **示例值** ：015：[0.01 - 0.02)   | &bull; 指示非音频流 <br/>&bull; 第二终结点未报告数据 |
| First Network Receive Quality Event Ratio  | 范围（比率）  | 满足以下条件的通话的比率（小数）：第一终结点检测到网络导致已接收音频的质量差。值按范围分组表示。<br/> **示例值** ：015：[0.01 - 0.02)   | &bull; 这是非音频流 <br/>&bull; 第一终结点未报告数据 |
| Second Network Receive Quality Event Ratio  | 范围（比率）  | 满足以下条件的通话的比率（小数）：第二终结点检测到网络导致已接收音频的质量差。值按范围分组表示。<br/> **示例值** ：015：[0.01 - 0.02)   | &bull; 指示非音频流 <br/>&bull; 第二终结点未报告数据 |
| First CPU Insufficient Event Ratio  | 范围（比率）  | 满足以下条件的通话的比率（小数）：第一终结点检测到可用 CPU 资源不足并导致已发送和已接收音频的质量差。值按范围分组表示。<br/> **示例值** ：016：[0.02 - 0.03)   | &bull; 指示非音频流 <br/>&bull; 第一终结点未报告数据 |
| Second CPU Insufficient Event Ratio  | 范围（比率）  | 满足以下条件的通话的比率（小数）：第二终结点检测到可用 CPU 资源不足并导致已发送和已接收音频的质量差。值按范围分组表示。<br/> **示例值** ：016：[0.02 - 0.03)   | &bull; 指示非音频流 <br/>&bull; 第二终结点未报告数据 |
| First Device Half Duplex AEC Event Ratio  | 范围（比率）  | 满足以下比例的通话：第一终结点检测到问题，在半双工模式下运行回声消除器，这影响了实时双向通信的能力。 值按范围分组表示。 <br/> **示例值** ：016：[0.02 - 0.03)   | &bull; 这是非音频流 <br/>&bull; 第一终结点未报告数据 |
| Second Device Half Duplex AEC Event Ratio  | 范围（比率）  | 满足以下要求的小数部分：第二终结点检测到问题，在半双工模式下运行回声消除器，这影响了实时双向通信的能力。 值按范围分组表示。 <br/> **示例值** ：016：[0.02 - 0.03)  | &bull; 指示非音频流 <br/>&bull; 第二终结点未报告数据  |
| First Device Render Not Functioning Event Ratio  | 范围（比率）  | 满足以下条件的通话的比率（小数）：第一终结点检测到呈现设备未正常工作。值按范围分组表示。<br/> **示例值** ：016：[0.02 - 0.03)  | &bull; 这是非音频流 <br/>&bull; 第一终结点未报告数据  |
| Second Device Render Not Functioning Event Ratio  | 范围（比率）  | 满足以下条件的通话的比率（小数）：第二终结点检测到呈现设备未正常工作。值按范围分组表示。<br/> **示例值** ：016：[0.02 - 0.03)   | &bull; 指示非音频流 <br/>&bull; 第二终结点未报告数据 |
| First Device Capture Not Functioning Event Ratio  | 范围（比率）  | 满足以下条件的通话的比率（小数）：第一终结点检测到捕获设备未正常工作。值按范围分组表示。<br/> **示例值** ：016：[0.02 - 0.03)  | &bull; 这是非音频流 <br/>&bull; 第一终结点未报告数据  |
| Second Device Capture Not Functioning Event Ratio  | 范围（比率）  | 满足以下条件的通话的比率（小数）：第二终结点检测到捕获设备未正常工作。值按范围分组表示。<br/> **示例值** ：016：[0.02 - 0.03)   | &bull; 指示非音频流 <br/>&bull; 第二终结点未报告数据 |
| First Device Glitches Event Ratio  | 范围（比率）  | 满足以下条件通话的一小部分：第一终结点检测到故障或间隙，导致发送或接收的音频质量差。 值按范围分组表示。 <br/> **示例值** ：016：[0.02 - 0.03)  | &bull; 这是非音频流 <br/>&bull; 第一终结点未报告数据  |
| Second Device Glitches Event Ratio  | 范围（比率）  | 满足以下条件通话的一小部分：第二终结点检测到音频中出现故障或间隙，导致发送或接收的音频质量差。 值按范围分组表示。 <br/> **示例值** ：016：[0.02 - 0.03)  | &bull; 指示非音频流 <br/>&bull; 第二终结点未报告数据  |
| First Device Low SNR Event Ratio  | 范围（比率）  | 满足以下条件的通话的比率（小数）：第一终结点检测到语音降低到噪音级别，导致发送的音频质量差。值按范围分组表示。<br/> **示例值** ：016：[0.02 - 0.03)  | &bull; 指示非音频流 <br/>&bull; 第一终结点未报告数据  |
| Second Device Low SNR Event Ratio  | 范围（比率）  | 满足以下条件的通话的比率（小数）：第二终结点检测到语音降低到噪音级别，导致发送的音频质量差。值按范围分组表示。<br/> **示例值** ：016：[0.02 - 0.03)  | &bull; 指示非音频流 <br/>&bull; 第二终结点未报告数据  |
| First Device Low Speech Level Event Ratio  | 范围（比率）  | 满足以下条件的通话的比率（小数）：第一终结点检测到语音级别降低，导致发送的音频质量差。值按范围分组表示。<br/> **示例值** ：016：[0.02 - 0.03)   | &bull; 这是非音频流 <br/>&bull; 第一终结点未报告数据 |
| Second Device Low Speech Level Event Ratio  | 范围（比率）  | 满足以下条件的通话的比率（小数）：第二终结点检测到语音级别降低，导致发送的音频质量差。值按范围分组表示。<br/> **示例值** ：016：[0.02 - 0.03)  | &bull; 指示非音频流 <br/>&bull; 第二终结点未报告数据  |
| First Device Clipping Event Ratio  | 范围（比率）  | 满足以下条件的通话的比率（小数）：第一终结点检测到捕获的音频中存在削波现象，导致发送的音频质量差。值按范围分组表示。<br/> **示例值** ：016：[0.02 - 0.03)  | &bull; 指示非音频流 <br/>&bull; 第一终结点未报告数据  |
| Second Device Clipping Event Ratio  | 范围（比率）  | 满足以下条件的通话的比率（小数）：第二终结点检测到捕获的音频中存在削波现象，导致发送的音频质量差。值按范围分组表示。<br/> **示例值** ：016：[0.02 - 0.03)   | &bull; 指示非音频流 <br/>&bull; 第二终结点未报告数据 |
| First Device Echo Event Ratio  | 范围（比率）  | 满足以下条件的通话的比率（小数）：第一终结点检测到回声，导致发送的音频质量差。值按范围分组表示。<br/> **示例值** ：016：[0.02 - 0.03)   | &bull; 这是非音频流 <br/>&bull; 第一终结点未报告数据 |
| Second Device Echo Event Ratio  | 范围（比率）  | 满足以下条件的通话的比率（小数）：第二终结点检测到回声，导致发送的音频质量差。值按范围分组表示。<br/> **示例值** ：016：[0.02 - 0.03)   | &bull; 指示非音频流 <br/>&bull; 第二终结点未报告数据 |
| First Device Near End To Echo Ratio Event Ratio | 范围（比率）| 满足以下比率的通话的比率：第一终结点检测到近端信号与回声的比率，导致音频质量差。 值按范围分组表示。 <br/> **示例值** ：016：[0.02 - 0.03)  | &bull; 这是非音频流 <br/>&bull; 第一终结点未报告数据|
| Second Device Near End To Echo Ratio Event Ratio  | 范围（比率）  | 满足以下条件的比率（小数部分：第二终结点检测到近端信号与回声级别的比率）导致音频质量差。 值按范围分组表示。 <br/> **示例值** ：016：[0.02 - 0.03)   | &bull; 指示非音频流 <br/>&bull; 第二终结点未报告数据 |
| First Device Render Zero Volume Event Ratio  | 范围（比率）  | 满足以下条件的通话的比率（小数）：第一终结点检测到设备呈现音量设置为 0。值按范围分组表示。<br/> **示例值** ：016：[0.02 - 0.03)  | &bull; 这是非音频流 <br/>&bull; 第一终结点未报告数据 |
| Second Device Render Zero Volume Event Ratio  | 范围（比率）  | 满足以下条件的通话的比率（小数）：第二终结点检测到设备呈现音量设置为 0。值按范围分组表示。<br/> **示例值** ：016：[0.02 - 0.03)  | &bull; 指示非音频流 <br/>&bull; 第二终结点未报告数据  |
| First Device Render Mute Event Ratio  | 范围（比率）  | 满足以下条件的通话的比率（小数）：第一终结点检测到设备呈现被静音。值按范围分组表示。<br/> **示例值** ：016：[0.02 - 0.03)    | &bull; 这是非音频流 <br/>&bull; 第一终结点未报告数据 |
| Second Device Render Mute Event Ratio  | 范围（比率）  | 满足以下条件的通话的比率（小数）：第二终结点检测到设备呈现被静音。值按范围分组表示。<br/> **示例值** ：016：[0.02 - 0.03)  | &bull; 指示非音频流 <br/>&bull; 第二终结点未报告数据  |
| First Device Multiple Endpoints Event Count  | 范围（比率）  | 通话期间，第一终结点检测到同一房间或声音环境中存到多个终结点的次数。值按范围分组表示。<br/> **示例值** ：016：[0.02 - 0.03)   | &bull; 这是非音频流 <br/>&bull; 第一终结点未报告数据 |
| Second Device Multiple Endpoints Event Count  | 范围（比率）  | 通话期间，第二终结点检测到同一房间或声音环境中存到多个终结点的次数。值按范围分组表示。<br/> **示例值** ：016：[0.02 - 0.03)   | &bull; 指示非音频流 <br/>&bull; 第二终结点未报告数据 |
| First Device Howling Event Count  | 范围（比率）  | 在通话期间，第一终结点检测到同一房间中两个或多个终结点导致音频质量差（例如，叫声或叫声）次数。 值按范围分组表示。 <br/> **示例值** ：016：[0.02 - 0.03)   | &bull; 这是非音频流 <br/>&bull; 第一终结点未报告数据 |
| Second Device Howling Event Count  | 范围（比率）  | 通话期间，第二终结点检测到同一房间或声音环境中存到两个或更多个终结点并因此导致存在啸声或尖叫声的差质量音频的次数。值按范围分组表示。<br/> **示例值** ：016：[0.02 - 0.03)   | &bull; 指示非音频流 <br/>&bull; 第二终结点未报告数据 |
|**调用诊断**|||
| Error Report Sender  | 字符串  | 指示发送流的通话错误报告的终结点。此报告包含额外的遥测并可能指出通话中的通话设置或断线问题。<br/> **示例值：** First | &bull; 指示未发送调用错误报告。  |
| Is Media Error  | 字符串  | 指示为流报告的通话错误是否为媒体级错误。此报告包含额外的遥测并可能指出通话中的通话设置或断线问题。    | &bull; 指示未发送调用错误报告。 |
| Media Failure Type  | 枚举 <br/>**可能的值：** <br/>&bull; Midcall <br/>&bull;  CallSetup <br/>&bull;  NotMediaFailure。 | 与流关联的媒体故障的类型。   | &bull; 指示未发送调用错误报告。   |
| 调用分类| 枚举 |分配给调用的可靠性分类。 **可能的值**：Success、Failure、ClassificationUnavailable | |
| 分类原因|String|将分类分配到流的原因。| |
| 测试呼叫类型|枚举|指示此调用是常规调用还是测试调用。 如果是测试调用，则指示测试调用的类型。 <br/>**可能的值：** NonTest、Silent、UserInitiated、Synthetic <br/>**含义：** <br/> NonTest – 常规呼叫 <br/> 无提示 - 无提示测试调用 <br/> UserInitiated – 用户启动的测试调用 <br/>综合 – ST 终结点发起的调用|
|**Session**|||
| RTP RTCP 多路复用器  | 布尔值  | True 表示在同一端口多路复用 RTP 和 RTCP。否则为 False。    | <br/>&bull; 终结点未报告数据  |
| Stun Version  | 整型  | 建立通话所使用的 STUN 协议的版本。  | <br/>&bull; 终结点未报告数据 <br/> **示例值：2**  |
| Media Relay  | 字符串  | 用于会话的一个或多个媒体中继的 IP 地址。对于流，可能会报告一对中继，中间用"+"隔开。<br/> **示例值：** "13.107.8.2 + 13.107.8.2"  | &bull; 终结点未报告此数据  |
| Is Anonymous Join Session  | 布尔值  | 如果用户匿名加入会议，则为 True，否则为 False。   | &bull; 无数据可确定用户是匿名加入还是非匿名加入   |
| 具有媒体诊断 Blob  | 布尔值  | 如何会话具有媒体诊断数据，则为 True，否则为 False。   | &bull; 未为此流收集某些信号数据   |
| Call Setup Failure Reason  | 枚举  | 通话未能建立媒体连接的原因分类。 <br/>**可能的值：** <br/> **缺少 FW 深度数据包检查免除** 规则 - 指示路径中的网络设备可能会由于深度数据包检查规则而阻止建立媒体路径。 这可能是因为未正确配置代理或防火墙规则。 <br/> **缺少 FW IP** 阻止免除规则 - 指示路径中的网络设备可能阻止建立到网络Office 365路径。 这可能是因为未正确将代理或防火墙规则配置为允许访问用于 Skype for Business 流量的 IP 地址和端口。 <br/> **其他** - 指示无法建立调用的媒体路径，但无法分类根本原因。 <br/> 不是媒体故障 - 表示在建立媒体路径时未检测到问题。  | &bull; 由于未知媒体问题，呼叫设置失败  |
| 会话类型  | 枚举 <br/>**可能的值：** <br/> Conf、P2P  | 指示呼叫会话类型是使用 P2P () 或对等呼叫 (会议) 。 <br/> **示例值：** Conf | |
| CDR 响应原因  | 枚举 <br/>**可能的值：** <br/> 0 或 200 = "OK" <br/> 410 = "MediaConnectivityErrors"<br/> 480 = "UserUnavailable"<br/> 487 = "PickupTimedOut" <br/> 603 = "CallDeclined" | 所有其他 CDR 代码 = "Other" | 提供通话会话结束的原因，无论呼叫是否成功，并允许在未完成的呼叫 (无应答、忙碌、拒绝) 和失败的呼叫 (媒体) 。 <br/> **示例值：** 还行 | <br/>&bull; 值"其他"表示响应代码在 Microsoft 工程团队外部在诊断上没有用 |
|**DNS**|||
| 已用 DNS 解析缓存  | 布尔值  | 如果终结点使用了 DNS 缓存来解析媒体中继地址，则为 True，否则为 False。    | <br/>&bull; 终结点未报告此数据    |
|**UserData**| |||
| First User ObjectId|String|第一终结点用户的 Active Directory 对象 ID。 仅适用于过去 28 天的数据，并且仅对具有允许 EUII 访问的角色的用户可见。  | |
| Second User ObjectId|String|第二终结点用户的 Active Directory 对象 ID。 仅适用于过去 28 天的数据，并且仅对具有允许 EUII 访问的角色的用户可见。 | |
| 第一个 MAC 地址|String|MAC 中的 (访问控制) 第一终结点的网络设备的地址。 仅适用于过去 28 天的数据，并且仅对具有允许 EUII 访问的角色的用户可见。| |
| 第二个 MAC 地址|String|MAC 中的 (访问控制) 第二终结点的网络设备的地址。 仅适用于过去 28 天的数据，并且仅对具有允许 EUII 访问的角色的用户可见。| |
| First Sip Uri|String|会话启动协议 (SIP) 第一终结点用户的 URI。 仅适用于过去 28 天的数据，并且仅对具有允许 EUII 访问的角色的用户可见。| &bull;仅针对终结点Skype for Business填充。 <br/>&bull; 用户无权查看 EUII。 |
| Second Sip Uri|String|第一终结点用户的 SIP URI。 仅适用于过去 28 天的数据，并且仅对具有允许 EUII 访问的角色的用户可见。| &bull;仅针对终结点Skype for Business填充。<br/>&bull; 用户无权查看 EUII。 |
| First 电话 Number|String|第一终结点用户的电话号码。 仅适用于过去 28 天的数据，并且仅对具有允许 EUII 访问的角色的用户可见。 无论 EUII 查看权限如何，最后四位数的 PSTN 号码始终在 CQD 中模糊处理。<br/> **示例值** ：+1425555****| &bull; 仅为 PSTN 终结点填充。 <br/>&bull; 用户无权查看 EUII。 |
| Second 电话 Number|String|第二终结点用户的电话号码。 仅适用于过去 28 天的数据，并且仅对具有允许 EUII 访问的角色的用户可见。 无论 EUII 查看权限如何，最后四位数的 PSTN 号码始终在 CQD 中模糊处理。<br/> **示例值** ：+1425555**** | &bull; 仅为 PSTN 终结点填充。<br/>&bull; 用户无权查看 EUII。 |
| First UPN|String|用户主体名称 (第) 终结点用户的 UPN 名称。 仅适用于过去 28 天的数据，并且仅对具有允许 EUII 访问的角色的用户可见。| &bull; 并非所有 UserType 都有 UPN;包括第二个 UserType 或 Second User ObjectId 维度，以了解有关这些终结点的更多信息。 |
| Second UPN|String|用户主体名称 (第) 终结点用户的 UPN 名称。 仅适用于过去 28 天的数据，并且仅对具有允许 EUII 访问的角色的用户可见。| &bull; 并非所有 UserType 都有 UPN;包括第二个 UserType 或 Second User ObjectId 维度，以了解有关这些终结点的更多信息。 |
| 第一个反馈文本|String|详细反馈文本（如果有）由第一终结点的用户在调用结束时提供。 仅适用于过去 28 天的数据，并且仅对具有允许 EUII 访问的角色的用户可见。 | |
| Second Feedback Text|String| 逐字反馈文本（如果有）由第二终结点用户在调用结束时提供。 仅适用于过去 28 天的数据，并且仅对具有允许 EUII 访问的角色的用户可见。|
| 第一个客户端终结点名称|String|第一终结点计算机名称。 仅适用于过去 28 天的数据，并且仅对具有允许 EUII 访问的角色的用户可见。|
| 第二个客户端终结点名称|String|第二终结点计算机名称。 仅适用于过去 28 天的数据，并且仅对具有允许 EUII 访问的角色的用户可见。|
| First Endpoint Product Name|String|第一终结点的产品名称 (或Skype for Business Microsoft Teams) 。|
| Second Endpoint Product Name|String|第二终结点的产品名称 (或Skype for Business Microsoft Teams) 。|
| First UserType|枚举字符串|第一终结点上的用户类型。 <br/> **可能的值：** 用户、服务器、匿名、应用程序、PSTN、语音邮件、未知 <br/> <br/>**未知** - 如果无法根据收到的信息确定 UserType，则为默认值。 <br/>**PSTN** - PSTN 用户。 <br/>**匿名**- Teams或Skype for Business访问者。 <br/>**应用程序** - 机器人。 <br/>**用户**- AAD 用户，可以是Skype for Business用户Teams用户。 <br/>**服务器** - 对于会议，至少一端是服务器。 <br/>**语音邮件** - 由语音邮件服务应答终结点。||
| Second UserType|枚举字符串|第二终结点上的用户类型。 <br/> **可能的值：** 用户、服务器、匿名、应用程序、PSTN、语音邮件、未知 <br/> <br/>**未知** - 如果无法根据收到的信息确定 UserType，则为默认值。 <br/>**PSTN** - PSTN 用户。 <br/>**匿名**- Teams或Skype for Business访问者。 <br/>**应用程序** - 机器人。 <br/>**用户**- AAD 用户，可以是Skype for Business用户Teams用户。 <br/>**服务器** - 对于会议，至少一端是服务器。 <br/>**语音邮件** - 由语音邮件服务应答终结点。||
|**PSTN**|||
|PSTN 呼叫结束原因 (SIP 响应代码) |Int|三位数整数响应代码显示调用的最终状态。 <br/> 有关 SIP 说明详细信息，请参阅 [SIP 响应代码列表](https://www.wikipedia.org/wiki/List_of_SIP_response_codes)。 <br/>**示例** ：404||
|PSTN 中继 FQDN|String|FQDN 是会话边界控制器 (SBC) FQDN (完全限定) 。<br/>**示例：sbcgw.contoso.com**||
|PSTN 运营商名称|String|由监管机构授权运营电信系统的公司。<br/>**示例：** Colt|直接路由没有运营商。 只有呼叫计划具有运营商。|
|PSTN 呼叫类型|String|此字符串结合了服务类型和调用类型。<br/><br/>服务类型：<br/>user ->呼叫计划<br/>byot ->直接路由<br/>conf -> 音频会议<br/>ucap -> 语音应用<br/>紧急 -> 紧急号码<br/><br/>呼叫类型：<br/>在 -> 入站呼叫中<br/>出>出站呼叫<br/>Out_transfer ->出站呼叫转接到第三方<br/>Out_forward ->将出站呼叫转发给第三方<br/>Out_conf -> PSTN 参与者进行出站呼叫<br/><br/>**示例：** ByotIn||
|PSTN 连接类型|String|PSTN 连接类型包括直接路由、呼叫计划或音频会议。 目前，"呼叫质量仪表板"和 CQD (中仅) 。<br/>**示例：** 直接路由||
|PSTN 最终 SIP 代码短语|String|对应于 SIP 响应代码和 Microsoft 响应代码的原因短语。<br/>**示例：** BYE||
|PSTN 呼叫结束子原因|Int|从 Microsoft 组件发送的响应代码，指示发生的特定操作。<br/>**示例** ：540000||
|PSTN 事件类型|String|提供遥测的事件类型。<br/>**示例：** End||
|PSTN 事件信息时间|日期|从 Microsoft 网络启动出站呼叫或入站呼叫到达 Microsoft 网络的时间，采用 UTC 格式。<br/>**示例** ：2020-02-06 20：57：53.1750000||
|PSTN MP 位置|String|在非绕过模式下，媒体处理器位置会显示媒体路径。<br/>**示例：** USWE||
|第一个 PSTN 国家/地区|String|如果 FirstIsCaller 为 true，则第一个 PSTN 国家/地区是呼叫者的国家/地区。 如果为 false，则第二个 PSTN 国家/地区是呼叫者的国家/地区。<br/>**示例：** 美国||
|抖动|毫秒|RTP 数据包到达时间的变化。 有关详细信息， [请参阅呼叫质量仪表板中的](stream-classification-in-call-quality-dashboard.md) 流分类。<br/>**示例** ：5.982||
|Packet Loss Rate|百分比|中介服务器与 SBC 或网关之间的流百分比（如果可用）。 有关详细信息， [请参阅呼叫质量仪表板中的](stream-classification-in-call-quality-dashboard.md) 流分类。<br/>**示例** ：1.2%||
|往返 (延迟) |毫秒|计算每个流的平均网络传播往返时间。 有关详细信息， [请参阅呼叫质量仪表板中的](stream-classification-in-call-quality-dashboard.md) 流分类。<br/>**示例** ：3.49||
|**会议**|||
|会议方案|枚举 <br/>**可能的值：** <br/> Bookings <br/> EHR 连接器 <br/> 未知 |由会议安排客户端团队提供的字段 (例如 Bookings、EHR Connector) 遥测数据，以帮助区分其他会议。 截至 2021 年 4 月，只有 Bookings 和 EHR 连接器已注册以提供遥测数据来识别会议方案。|计划客户端尚未通过其遥测提供此参数。|
|**Datapair**|||
| Network Connection Detail Pair  | 枚举对 <br/>**可能的值：** <br/> wifi : wifi <br/> wifi : 有线 <br/> 有线 : wifi <br/> 有线 : 有线 <br/> MobileBB : MobileBB <br/> MobileBB : 其他 <br/> MobileBB : 隧道 <br/> MobileBB : wifi <br/> MobileBB : 有线 <br/> 其他 : 其他 <br/> 其他 : wifi <br/> 其他 : 有线 <br/> 隧道 : 隧道 <br/> 隧道 : wifi <br/> 隧道 : 有线 <br/> : MobileBB <br/> : 其他 <br/> : 隧道 <br/> : wifi <br/> : 有线 <br/> :  | 表示第一和第二终结点的网络连接详情的成对值。  | &bull; 终结点网络连接类型未知。 当无法建立通话时可能会出现这种情况。   |
| User Agent Category Pair  | 枚举对  | 表示第一和第二终结点的用户代理类别的成对值。 <br/> **示例值：** AV-MCU ：OC  | &bull; 终结点用户代理不是已知类型  |
| Is Server Pair  | 枚举对 <br/>**可能的值：** 客户端：客户端 <br/> 客户端：服务器 <br/> 服务器：服务器  | 表示第一和第二终结点是客户端还是服务器的成对值。  | 没有空值   |
| Connectivity Ice Pair  | 枚举对 <br/>**可能的值：** <br/> 直接 : 直接 <br/> 直接 : 失败 <br/> 直接 : HTTP <br/> 失败 : 失败 <br/> 失败 : 中继 <br/> HTTP : 中继 <br/> : <br/> : 直接 <br/> : 失败 <br/> : HTTP <br/> : 中继 | 表示每个终结点使用的 ICE 连接类型的成对值。   | &bull; 终结点使用的 ICE 连接未知或报告   |
| OS Pair  | 枚举对  | 表示第一和第二终结点的操作系统名称和版本的成对值。 <br/> **示例值：Windows 10** ： Windows 10  | &bull; 无法分析 OS 名称或终结点未报告 OS 名称  |
| Tenant Id Pair  | 枚举对  | 表示第一和第二终结点的租户 ID 的成对值。 <br/> **示例值** ：00000000 - 0000 - 0000 - 0000 - 000000000000 ： 00000000 - 0000 - 0000 - 00000000000000  |  &bull; 无法确定租户标识符。 当终结点登录到了本地 Skype for Business Server 部署时可能会出现此情况。  |
| Building Name Pair  | 枚举对  | 表示第一和第二终结点的建筑物名称的成对值。  | &bull; 无法确定终结点的建筑物名称。 这可能是因为终结点位于企业网络外部，或正在从没有子网映射的站点访问网络。 <br/> **示例值：** 主建筑物：分支网站建筑物 |
| Inside Corp Pair  | 枚举对 <br/>**可能的值：** <br/> 内部 : 内部 <br/> 内部 : 外部 <br/> 外部 : 外部 | 根据子网映射，显示终结点位于企业网络内部还是外部的成对值。   |   |
| Scenario Pair  | 枚举对  | 显示终结点位于企业网络内部还是外部（根据子网映射确定）以及网络连接详情的成对值。 <br/> **注意：** 对由"--"分隔。 <br/> **示例值：** Client-Inside--Client-Inside-wifi  | &bull; 任一终结点或两个终结点的网络连接类型未知。  |
||||


### <a name="notes-on-dimension-data-typeunits"></a>维度维度数据类型/单位的备注

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
|066：[3-4)  |3 分钟 < = 流持续时间 < 4 分钟 |
|  | |

The \<sort order string> is used to control the sort order when presenting the data and can be used for filtering. For example, a filter on Duration (Minutes) < "065", would show streams with duration less than 2 minutes (The leading '0' is needed for the filter to work as expected).

> [!NOTE]
> [!注释] 排序字符串的实际值并不重要。

#### <a name="enumeration-strings"></a>枚举字符串

CQD 使用的字符串通常派生自数据文件，这些字符串几乎可以是允许长度内的任意字符组合。 某些维度看起来像字符串，但由于它们只能是预定义值的简短列表之一，因此它们是枚举而不是真正的字符串。 某些枚举字符串也用于成对。

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

上表列出了维度可能出现空值的原因。 如果 QoE 记录可用维度为 false，则许多维度和度量将为空。 这通常出现在通话未能成功建立的情况下。

## <a name="measurements"></a>度量

许多度量值也可以用作筛选器。 下表列出了 CQD 中当前可用的度量，如查询编辑器中列出的顺序所示

|衡量指标名称 |单位 |说明 |
|:--- |:--- |:--- |
|Total Stream Count |流的数量 |无论媒体类型如何，媒体流的数量，包括可能没有媒体类型的可靠性/诊断流。 |
| CDR 可用流计数总计 | 流的数量 |具有可用可靠性/诊断信息的媒体流的数量。 请参阅[在通话中 (CDR) 录音Skype for Business Server](/skypeforbusiness/manage/health-and-monitoring/call-detail-recording-cdr) |
|Total Media Failed Stream Count |流的数量 |媒体路径未能建立或未正常终止的流的数量。 |
|Total Call Setup Failed Stream Count |流的数量 |呼叫之初无法在终结点之间建立媒体路径的流的数量。 |
|Total Call Dropped Stream Count |流的数量 |媒体路径未正常终止的流的数量。 |
|Total Media Succeeded Stream Count |流的数量 |媒体路径成功建立并正常终止的流的数量。 |
|Total Call Setup Succeeded Stream Count |流的数量 |呼叫之初在终结点之间成功建立媒体路径的流的数量。|
|Total Call Setup Failure Percentage |百分比 |呼叫之初无法在终结点之间建立媒体路径的所有流的百分比。 |
|Total Call Dropped Failure Percentage |百分比 |媒体路径未正常终止的成功建立的流的百分比。| 
|Total Answer Seizure Ratio |比率 |持续时间低于 5 秒钟的通话占通话总数的比率。 |
|Total Short Call Percentage |百分比 |总通话时间在 1 分钟以下的百分比。 |
|Total Media Failure Percentage |百分比 |媒体路径未能建立或未正常终止的所有流的百分比。 |
|总音频流持续时间 (分钟)  |分钟 |所选时间范围内的总音频流持续时间（以分钟数表示）。 |
|Media Failed Due To Firewall DPI Stream Count |流的数量 |由于深度包检测不允许 Skype for Business 流量导致网络设备阻止访问进而未能建立的流的数量。 这些故障通常表示代理、防火墙或其他网络安全设备未正确配置为访问 Microsoft 365 或 Office 365 中的 Skype for Business 使用的 IP 地址和端口。 |
|Firewall DPI Media Failure Percentage |百分比 |由于深度包检测不允许 Skype for Business 流量导致网络设备阻止访问进而未能建立的流的百分比。 这些故障通常表示代理、防火墙或其他网络安全设备未正确配置为访问 Microsoft 365 或 Office 365 中的 Skype for Business 使用的 IP 地址和端口。 |
|Media Failed Due To Firewall IP Blocked Stream Count |流的数量 |由于网络设备阻止访问 Skype for Business 服务器而未能建立的流的数量。 这些故障通常表示代理、防火墙或其他网络安全设备未正确配置为访问 Microsoft 365 或 Office 365 中的 Skype for Business 使用的 IP 地址和端口。 |
|Firewall IP Blocked Media Failure Percentage |百分比 |由于网络设备阻止了对服务器的访问而未能建立的Skype for Business百分比。 这些故障通常表示代理、防火墙或其他网络安全设备未正确配置为访问 Microsoft 365 或 Office 365 中的 Skype for Business 使用的 IP 地址和端口。 |
| 媒体因其他流计数而失败|流的数量| 由于未确定/未分类的原因，在终结点之间无法建立媒体路径的流的数量。| |
| 其他媒体故障百分比|百分比| 由于未确定/未分类的原因，在终结点之间无法建立媒体路径的流百分比。 ||
| CDR 可用呼叫计数总计|流的数量|具有可用可靠性/诊断信息的媒体流总数。 此度量值最多存在 0.2% 的错误。 有关详细信息，请参阅下面的注释。|
| 媒体失败呼叫计数总计|流的数量|在终结点之间无法建立媒体路径的流的数量。 此度量值最多存在 0.2% 的错误。 有关详细信息，请参阅下面的注释。|
|Audio Stream Count |流的数量 |音频流的数量。 |
|Audio Poor Stream Count |流的数量 |根据以下位置列出的网络指标被分类为差的音频流的数量：呼叫质量仪表板 [中的流分类](stream-classification-in-call-quality-dashboard.md)。 |
 |Audio Good Stream Count |流的数量 |根据以下位置列出的网络指标被分类为良好音频流的数量：呼叫质量仪表板 [中的流分类](stream-classification-in-call-quality-dashboard.md)。 |
|Audio Unclassified Stream Count |流的数量 |根据以下位置列出的网络指标，没有足够数据被分类为好或差的音频流的数量：呼叫质量仪表板中的 [流分类](stream-classification-in-call-quality-dashboard.md)。 |
|Audio Poor Percentage |百分比 |根据以下位置中列出的网络指标被分类为差的所有音频流的百分比：呼叫质量仪表板 [中的流分类](stream-classification-in-call-quality-dashboard.md)。 |
|Audio OnePercent PacketLoss Count |流的数量 |丢包率大于 1% 的音频流的数量。 |
|Audio OnePercent PacketLoss Percentage |百分比 |丢包率大于 1% 的所有音频流的百分比。 |
|Audio Poor Due To Jitter Count |流的数量 |抖动指标超过以下位置中列出的阈值的音频流的数量：呼叫质量仪表板 [中的流分类](stream-classification-in-call-quality-dashboard.md)。 |
|Audio Poor Due To PacketLoss Count |流的数量 |丢包指标超过以下位置所列阈值的音频流的数量：呼叫质量仪表板 [中的流分类](stream-classification-in-call-quality-dashboard.md) |
|Audio Poor Due To Degradation Count |流的数量 |降级指标超过以下位置列出的阈值的音频流的数量：呼叫质量仪表板 [中的流分类](stream-classification-in-call-quality-dashboard.md)。 |
|Audio Poor Due To RoundTrip Count |流的数量 |往返行程超过以下位置中列出的阈值的音频流的数量：呼叫质量仪表板 [中的流分类](stream-classification-in-call-quality-dashboard.md)。 |
|Audio Poor Due To ConcealedRatio Count |流的数量 |隐藏比率超过以下位置所列阈值的音频流的数量：呼叫质量仪表板 [中的流分类](stream-classification-in-call-quality-dashboard.md)。 |
|Audio SLA Good Call Count |通话的数量 |Microsoft 产品和在线服务的语音质量 SLA Skype for Business批量许可 (范围内被分类为[](https://aka.ms/voicequalitysla)) 网络性能目标的音频呼叫数。 |
|Audio SLA Poor Call Count |通话的数量 |Microsoft 产品和在线服务的Skype for Business SLA (批量许可范围内被归类为) 未满足[](https://aka.ms/voicequalitysla)网络性能目标的音频呼叫数。 |
|Audio SLA Call Count |通话的数量 |Microsoft 产品与在线服务Skype for Business批量许可Skype for Business语音质量 (SLA 范围内的音频[呼叫](https://aka.ms/voicequalitysla)) 。 |
|Audio SLA Good Call Percentage |百分比 |Skype for Business 语音质量 SLA（[Microsoft 产品和在线服务的批量许可](https://aka.ms/voicequalitysla)）范围内被分类为满足网络性能目标的音频通话的百分比。 |
|Audio Good Call Stream Count |流的数量 |根据以下位置列出的网络指标 (通话中的两个音频流 () 被分类为差的音频流的数量：呼叫质量仪表板中的 [流分类](stream-classification-in-call-quality-dashboard.md)。 |
|Audio Poor Call Stream Count |流的数量 |根据以下位置列出的网络指标 (通话段) 中至少有一个音频流被分类为差的音频流的数量：呼叫质量仪表板中的流 [分类](stream-classification-in-call-quality-dashboard.md)。 |
|Audio Unclassified Call Stream Count |流的数量 |由于缺少网络指标，无法 (呼叫) 音频流的音频流的数量。 |
|Audio Poor Call Level Percentage |百分比 |通话中至少有一个音频流 (呼叫段) 根据以下列出的网络指标被分类为差的所有音频流的百分比：呼叫质量仪表板中的流 [分类](stream-classification-in-call-quality-dashboard.md)。 |
| 音频呼叫计数 | 数字 |涉及音频的呼叫数。 此度量值最多存在 0.2% 的错误。 有关详细信息，请参阅下面的注释。|
| Audio Poor Call Count|数字  |涉及被分类为差的音频的呼叫数。 此度量值最多存在 0.2% 的错误。 有关详细信息，请参阅下面的注释。|
| 音频良好呼叫计数 |通话的数量|涉及被分类为良好音频的呼叫数。 此度量值最多存在 0.2% 的错误。 有关详细信息，请参阅下面的说明。|
| 音频未分类呼叫计数 |通话的数量|涉及无法分类为"良好"或"差"的音频的呼叫数。 此度量值最多存在 0.2% 的错误。 有关详细信息，请参阅下面的注释。|
| Audio Poor Call Percentage |通话百分比|涉及被分类为差的音频的通话的百分比。 此度量值最多存在 0.2% 的错误。 有关详细信息，请参阅下面的注释。|
|AppSharing Stream Count |流的数量 |基于 RDP 的应用程序共享流的数量。 |
|AppSharing Poor Due To SpoiledTilePercentTotal Count |流的数量 |损坏的磁贴百分比总指标超过以下位置列出的阈值的应用程序共享流的数量：呼叫质量仪表板 [中的流分类](stream-classification-in-call-quality-dashboard.md)。 |
|AppSharing Poor Due To RelativeOneWayAverage Count |流的数量 |损坏的磁贴百分比总指标超过以下位置列出的阈值的应用程序共享流的数量：呼叫质量仪表板 [中的流分类](stream-classification-in-call-quality-dashboard.md)。 |
|AppSharing Poor Due To RDPTileProcessingLatencyAverage Count |流的数量 |RDP 磁贴处理平均延迟超过以下位置列出的阈值的应用程序共享流的数量：呼叫质量仪表板 [中的流分类](stream-classification-in-call-quality-dashboard.md)。 |
|AppSharing Poor Stream Count |流的数量 |根据以下列出的网络指标分类为差的应用程序共享流的数量：呼叫质量仪表板 [中的流分类](stream-classification-in-call-quality-dashboard.md)。 |
|AppSharing Good Stream Count |流的数量 |根据以下列出的网络指标分类为良好应用程序共享流的数量：呼叫质量仪表板 [中的流分类](stream-classification-in-call-quality-dashboard.md)。 |
|AppSharing Unclassified Stream Count |流的数量 |根据以下列出的网络指标，没有足够数据被分类为好或差的应用程序共享流的数量：呼叫质量仪表板中的 [流分类](stream-classification-in-call-quality-dashboard.md)。 |
|AppSharing Poor Percentage |百分比 |根据以下位置列出的网络指标被分类为差的应用程序共享流总数百分比：呼叫质量仪表板 [中的流分类](stream-classification-in-call-quality-dashboard.md)。 |
|Video Stream Count |流的数量 |视频流的数量。 |
|Video Poor Due To VideoPostFecplr Count |流的数量 |Fec plr 后的视频超过以下文章中列出的阈值的视频流的数量：呼叫质量仪表板 [中的流分类](stream-classification-in-call-quality-dashboard.md)。 |
|Video Poor Due To VideoLocalFrameLossPercentageAvg Count |流的数量 |视频本地帧丢失百分比平均值超过以下所列阈值的视频流的数量：呼叫质量仪表板 [中的流分类](stream-classification-in-call-quality-dashboard.md)。 |
|Video Poor Due To VideoFrameRateAvg Count |流的数量 |视频帧速率平均值超过以下位置中列出的阈值的视频流的数量：呼叫质量仪表板 [中的流分类](stream-classification-in-call-quality-dashboard.md)。 |
|Video Poor Due to Freeze Count |流的数量 | 视频冻结指标超过此处所列阈值的主视频流的数量。 [呼叫质量仪表板中的流分类](stream-classification-in-call-quality-dashboard.md)。 此字段特定于Microsoft Teams |
|Video Poor Stream Count |流的数量 |根据通话质量仪表板中的流分类中列出的网络指标分类为差 [的视频流的数量](stream-classification-in-call-quality-dashboard.md)。 |
|Video Good Stream Count |流的数量 |根据以下位置列出的网络指标被分类为良好视频流的数量：呼叫质量仪表板 [中的流分类](stream-classification-in-call-quality-dashboard.md)。 |
|Video Unclassified Stream Count |流的数量 |根据以下列出的网络指标，没有足够数据被分类为好或差的视频流的数量：呼叫质量仪表板中的 [流分类](stream-classification-in-call-quality-dashboard.md)。 |
|Video Poor Percentage|百分比 |根据通话质量仪表板中的流分类中列出的网络指标被分类为差的总 [视频流的百分比](stream-classification-in-call-quality-dashboard.md)。 |
|Video Poor Percentage Due to Freeze|百分比 | 根据"通话质量仪表板"中的流分类中列出的"由于冻结导致的视频差"指标被分类为差的主要视频流的 [百分比](stream-classification-in-call-quality-dashboard.md)。 此字段特定于Microsoft Teams |
|VBSS Stream Count |流的数量 |基于视频的屏幕共享流的数量。 |
|VBSS Poor Due To VideoPostFecplr Count |流的数量 |视频发布 Fec plr 超过以下文章中列出的阈值的基于视频的屏幕共享流的数量：呼叫质量仪表板中的 [流分类](stream-classification-in-call-quality-dashboard.md)。 |
|VBSS Poor Due To VideoLocalFrameLossPercentageAvg Count |流的数量 |视频本地帧丢失百分比平均值超过以下所列阈值的基于视频的屏幕共享流的数量：呼叫质量仪表板中的 [流分类](stream-classification-in-call-quality-dashboard.md)。 |
|VBSS Poor Due To VideoFrameRateAvg Count |流的数量 |视频帧速率平均值超过以下位置列出的阈值的基于视频的屏幕共享流的数量：呼叫质量仪表板中的 [流分类](stream-classification-in-call-quality-dashboard.md)。 |
|VBSS Poor Stream Count |流的数量 |基于视频的屏幕共享流的数量，根据以下位置列出的网络指标被分类为差：呼叫质量仪表板 [中的流分类](stream-classification-in-call-quality-dashboard.md)。 |
|VBSS Good Stream Count |流的数量 |基于视频的屏幕共享流的数量，根据以下位置列出的网络指标被分类为良好：呼叫质量仪表板中的 [流分类](stream-classification-in-call-quality-dashboard.md)。 |
|VBSS Unclassified Stream Count |流的数量 |基于视频的屏幕共享流的数量，这些流没有足够的数据，无法根据以下列出的网络指标分类为好或差：呼叫质量仪表板中的流 [分类](stream-classification-in-call-quality-dashboard.md)。 |
|VBSS Poor Percentage |百分比 |根据以下位置列出的网络指标分类为差的基于视频的屏幕共享流的总百分比：呼叫质量仪表板 [中的流分类](stream-classification-in-call-quality-dashboard.md)。 |
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
|First Feedback Token Video Issue Count |被评级的流的数量 |使用第一终结点的用户指示视频问题的流的数量。 |
|Second Feedback Token Video Issue Count |被评级的流的数量 |使用第二终结点的用户指示视频问题的流的数量。 |
|Avg First Echo Percent Mic In |百分比 |在流持续期间，第一终结点在消除回声之前通过捕获设备或麦克风设备在音频中检测到回声的持续时间的平均百分比。 |
|Avg Second Echo Percent Mic In |百分比 |在流持续期间，第二终结点在消除回声之前通过捕获设备或麦克风设备在音频中检测到回声的持续时间的平均百分比。 |
|Avg First Echo Percent Send |百分比 |在流持续期间，第一终结点在消除回声之后通过捕获设备或麦克风设备在音频中检测到回声的持续时间的平均百分比。 |
|Avg Second Echo Percent Send |百分比 |在流持续期间，第二终结点在消除回声之后通过捕获设备或麦克风设备在音频中检测到回声的持续时间的平均百分比。 |
| Avg First Initial Signal Level RMS| 范围 (分贝)  |第一终结点调用前 30 秒 (RMS) 平均平方根数的平均值。  有关详细信息 [，请参阅 2.2.1.28.1](/openspecs/office_protocols/ms-qoe/3c78f383-73fe-49f6-89cb-614e7aa8b2e7) 子元素|
| Avg Second Initial Signal Level RMS|范围 (分贝)  |第二终结点调用前 30 秒 (RMS) 平均平方根数的平均值。||
| Avg First RxAGC Signal Level|范围 (分贝)   |第一个入站音频流的自动增益控制接收的平均信号级别。 | |
| Avg Second RxAGC Signal Level|范围 (分贝)  |第二个入站音频流的自动增益控制接收的平均信号级别。| |
| Avg First RxAGC Noise Level|范围 (分贝)  |第一个入站音频流的自动增益控制收到的平均噪音级别。||
| Avg Second RxAGC Noise Level|范围 (分贝)  |第二个入站音频流的自动增益控制收到的平均噪音级别。| |
| Avg First Render Loopback Signal Level|范围 (分贝)  | 应用任何设备卸载 (后，第一个扬声器环回信号的平均) 。|
| Avg Second Render Loopback Signal Level|范围 (分贝)  | 在应用任何设备卸载 (后，第二扬声器环回信号的平均) 。|
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
|Avg Audio Degradation |平均意见得分 (0-5) |关于流降级的网络平均意见得分的平均值。 表示网络丢失和抖动对接收音频质量的影响。 |
|Avg Jitter |毫秒 |流的平均网络抖动，以毫秒为单位。 |
|Avg Jitter Max |毫秒 |流的最大网络抖动值，以毫秒为单位。 |
|Avg Packet Loss Rate |比率 |以 5 秒钟时间间隔计算到的流的平均丢包百分比的平均值。 0.1 表示数据包丢失 10%。 |
|Avg Packet Loss Rate Max |比率 |以 5 秒钟时间间隔计算到的流的最大丢包百分比的平均值。 0.1 表示数据包丢失 10%。 |
| Avg Send Listen MOS |数字 |从用户发送的音频流的宽带 (平均意见评分预测) MOS-LQ 评分的平均值。 <br/>请参阅 Lync 监视报告解码器中"平均 [发送 MOS"](https://gallery.technet.microsoft.com/Lync-Reports-Decoder-001ba287)|
|Avg Overall Avg Network MOS |平均意见得分 (0-5) |流的网络平均意见得分的平均值。表示通过考虑网络损耗、抖动和编解码器对所收到的音频质量的平均估计。 |
|Avg Ratio Concealed Samples |比率 |含有丢包隐藏生成样本的音频帧数与流的总音频帧数的平均比率的平均值。0.1 表示 10% 的帧包含隐藏样本。 |
| 平均隐藏比率最大值| 比率 |丢包隐藏生成的样本的音频帧数与流的总音频帧数的最大比率的平均值。 0.1 表示 10% 的帧包含隐藏样本。| |
|Avg Ratio Stretched Samples |比率 |通过拉伸样本补偿抖动或丢失的音频帧数与流的总音频帧数的平均比率的平均值。0.1 表示 10% 的音频帧包含拉伸样本。 |
| Avg Healer Packet Drop Ratio|范围 (比率) |由修复程序丢弃的音频数据包与修复程序收到的音频数据包总数的平均比率。 | |
| Avg Healer FEC Packet Used Ratio|范围 (比率) |已用 FEC 数据包与已接收 FEC 数据包总数的平均比率。|
|Avg Round Trip |毫秒 |计算的平均网络传播往返时间的平均值，根据 RFC3550 以毫秒为单位指定。 |
|Avg Round Trip Max |毫秒 |计算的最大网络传播往返时间的平均值，根据 RFC3550 以毫秒为单位指定。 |
 平均数据包利用率|数据包数|在会话中Real-Time每秒发送 (RTP) 传输协议的平均数目。|
|Avg Network Jitter |毫秒 |   会话期间在 20 秒时段内计算的网络抖动平均值。 |
| Avg Network Jitter Max|毫秒 |会话期间在 20 秒时段内计算的最大网络抖动的平均值（以毫秒为单位）。  ||
| Avg Network Jitter Min|毫秒|在会话期间为流计算的最小网络抖动值（以毫秒为单位）的平均值。| |
| Avg Jitter Buffer Size Max|毫秒|会话期间抖动缓冲区的最大大小。| |
| Avg Jitter Buffer Size Min|毫秒|会话期间抖动缓冲区的最小大小。| |
| Avg Relative OneWay |毫秒|对等的平均计算相对单向延迟。| |
| Avg Relative OneWay Gap Occurrences|毫秒|对等的相对单向延迟中间隙的平均实例数。| |
| Avg Relative OneWay 间距密度|毫秒|对等方相对单向延迟的平均间隙密度。| |
| Avg Relative OneWay Gap Duration|数字 (毫秒) |对等方相对单向延迟的间隙的平均持续时间。| |
|Avg Audio Post FECPLR |比率 |应用 FEC 后跨所有音频流和编解码器聚合的数据包丢失率的平均值。 |
|Avg Video Post FECPLR |比率 |应用 FEC 后，跨所有视频流和编解码器汇总的丢包率的平均值。 |
|Avg Video Local Frame Loss Percentage |百分比 |向用户显示的流视频帧丢失平均百分比。其中包括从网络丢失恢复的帧。 |
 |Avg Video Received Frame Rate Average |帧/秒 |在会话持续期间计算到的流的所有视频流每秒接收的平均帧数的平均值。 |
 |Avg Video Low Frame Rate Call Percent |百分比 |帧速率低于 7.5 帧/秒的流通话时间的平均百分比。 |
|Avg Video Packet Loss Rate |比率 |根据 [RFC3550](https://tools.ietf.org/html/rfc3550)中指定的，在流的会话持续时间内计算的平均丢包率的平均值。 |
|Avg Video Frame Rate |帧/秒 |在会话持续期间计算到的视频流每秒接收的平均帧数。值按范围分组表示。 |
|Avg Video Dynamic Capability Percent |毫秒 |客户端以低于此类型 CPU 预期视频处理容量的 70% 运行的流时间的平均百分比。 |
|Avg AppSharing Spoiled Tile Percent Total |毫秒 |没有被发送到远程对等点（例如，从 MCU 到查看器）而是被丢弃的图块的平均百分比。丢弃图块可能是由于客户端与服务器之间的带宽限制所致。 |
|Avg AppSharing Relative OneWay |秒 |应用程序共享流的终结点之间的平均单向延迟平均值，以秒数表示。 |
|Avg AppSharing RDP Tile Processing Latency |毫秒 |在会议服务器上处理 RDP 堆栈图块的流平均延迟的平均值，以毫秒为单位。 |
|Avg First Device Capture Not Functioning Event Ratio |比率 |第一终结点检测到捕获设备未正常工作的通话的分数的平均值。 |
|Avg Second Device Capture Not Functioning Event Ratio |比率 |第二终结点检测到捕获设备未正常工作的通话的分数的平均值。 |
|Avg First Device Render Not Functioning Event Ratio |比率 |第一终结点检测到呈现设备未正常工作的通话的分数的平均值。 |
|Avg Second Device Render Not Functioning Event Ratio |比率 |第二终结点检测到呈现设备未正常工作的通话的分数的平均值。 |
|Avg First Mic 故障率| 故障数|对于流的终结点麦克风 (，第一个麦克风故障率) 每 5 分钟故障数。  ||
| Avg Second Mic Glitch Rate|故障数|对于流的终结点麦克风 (，第二个麦克风故障率) 每 5 分钟故障数。 ||
| Avg First Speaker Glitch Rate|故障数|对于流的终结点扬声器 (扬声器，第一扬声器) 平均故障率。 |
| Avg Second Speaker Glitch Rate|故障数|对于流的终结点扬声器 (扬声器，第二扬声器故障) 平均故障率。 |
| First User Count|数字 | 唯一或不同的第一终结点用户数。 仅适用于过去 28 天的数据。 此度量值最多存在 0.2% 的错误。 有关详细信息，请参阅下面的注释。|
| Second User Count|数字|唯一或不同的第二终结点用户数。 仅适用于过去 28 天的数据。 此度量值最多存在 0.2% 的错误。 有关详细信息，请参阅下面的注释。|
| Avg First Device Glitches Event Ratio|百分比|满足以下条件的平均通话分数：第一终结点检测到媒体播放或捕获的故障或间隙，导致发送或接收的媒体质量差。|
| Avg Second Device Glitches Event Ratio|百分比|满足以下条件的平均通话分数：第二终结点检测到播放或捕获的媒体中的故障或间隙，导致发送或接收的媒体质量差。|
| First Device Glitches Event Count| 数字 | 第一终结点检测到播放或捕获的媒体中导致发送或接收媒体质量差的明显故障或间隙的流的数量。|
| Second Device Glitches Event Count| 数字 | 第二终结点检测到播放或捕获的媒体中导致发送或接收媒体质量差的明显故障或间隙的流的数量。|
| PSTN 尝试总数计数 | 通话的数量 | 尝试的呼叫总数，包括所选时间范围内成功的调用和失败的调用。 此度量值最多存在 0.2% 的错误。 有关详细信息，请参阅下面的注释。|
|PSTN 总连接计数 | 通话的数量 | 所选时间范围内成功连接的呼叫总数。 此度量值最多存在 0.2% 的错误。 有关详细信息，请参阅下面的注释。|
|PSTN 入站尝试计数 | 通话的数量 | 尝试的入站呼叫总数，包括选定时间范围内成功的调用和失败的调用。 此度量值最多存在 0.2% 的错误。 有关详细信息，请参阅下面的注释。|
|PSTN 入站连接计数 | 通话的数量 | 所选时间范围内成功连接的入站呼叫总数。 此度量值最多存在 0.2% 的错误。 有关详细信息，请参阅下面的注释。|
|PSTN 出站尝试计数 | 通话的数量 | 尝试的出站呼叫总数，包括所选时间范围内成功的调用和失败的调用。 此度量值最多存在 0.2% 的错误。 有关详细信息，请参阅下面的注释。|
|PSTN 出站连接计数 | 呼叫次数 | 所选时间范围内成功连接的出站呼叫总数。 此度量值最多存在 0.2% 的错误。 有关详细信息，请参阅下面的注释。|
|PSTN 总分钟数 | 分钟 | 所选时间范围内的总分钟使用量。|
|PSTN 入站总分钟数 | 分钟 | 所选时间范围内入站分钟用量总计。|
|PSTN 出站总分钟数 | 分钟 | 所选时间范围内出站分钟用量总计。|
|PSTN 活动用户计数 | 用户数 | 当天至少进行了一次已连接呼叫的用户数。|
|PSTN 平均呼叫持续时间 | 分钟 | 所选时间范围内所有已连接呼叫的平均持续时间。 通常，1：1 PSTN 呼叫需要 4 到 5 分钟。 但是，每个公司的平均值可能不同。|
|PSTN 入站并发呼叫计数总计 | 通话的数量 | 一分钟内同时进行的活动入站呼叫的最大数量。|
|PSTN 总出站并发呼叫计数 | 通话的数量 | 一分钟内同时进行的活动出站呼叫的最大数量。|
|P50 延迟 | 毫秒 | 50% 的请求应比给定的延迟更快。|
|P50 抖动 | 毫秒 | 50% 的请求应比给定的抖动更快。|
|P50 数据包丢失率 | 百分比 | 50% 的请求应低于给定的数据包丢失率。|
|PSTN 传出后拨号延迟| 毫秒 | 从拨打号码到呼叫方听到铃声的传出呼叫发生的延迟。|
|PSTN 传入后拨号延迟 | 毫秒 | 从拨打号码到呼叫方或被呼叫方听到铃声的传入呼叫发生的时间或延迟。|
|PSTN NER 良好百分比 | 百分比 | NER 通过测量已发送的呼叫数与发送给收件人的呼叫数，测量网络传送呼叫的能力。<br/>NER = (应答呼叫 + 用户忙 + 无响铃无应答 + 终端拒绝放弃）/ 总尝试呼叫数 x 100。此措施最多存在 0.2% 的错误。 有关详细信息，请参阅下面的注释。|
||||

### <a name="notes-on-measurements"></a>有关度量的注意事项

#### <a name="accuracy-limitations"></a>准确性限制
某些用户和调用计数度量依赖于对数据集执行不同的 countif 操作来计算计数。 根据所执行的操作的行数，非重复 countif 操作当前存在最多 0.2% 的错误。 对于最准确的卷，应该使用流计数度量值，因为它们不依赖于此不同的 countif 操作。 减少数据量的筛选可以减少错误，但可能无法消除不同调用和用户计数中的此错误源。 有关此限制详细信息，请参阅 [dcount 聚合函数](/azure/data-explorer/kusto/query/dcount-aggfunction)。

## <a name="filters"></a>筛选器

许多维度和度量值也可以用作筛选器。 可以使用查询中的筛选器以与选择"维度"或"度量"以在查询中添加或包含信息相同的方式来消除信息。

## <a name="related-topics"></a>相关主题

[改进和监视呼叫质量Teams](monitor-call-quality-qos.md)

[什么是 CQD？](CQD-what-is-call-quality-dashboard.md)

[使用 CQD (设置呼叫质量) ](turning-on-and-using-call-quality-dashboard.md)

[Upload租户和建筑物数据](CQD-upload-tenant-building-data.md)

[CQD 数据和报表](CQD-data-and-reports.md)

[使用 CQD 管理呼叫和会议质量](quality-of-experience-review-guide.md)

[CQD 中的流分类](stream-classification-in-call-quality-dashboard.md)

[使用Power BI分析 CQD 数据](CQD-Power-BI-query-templates.md)
