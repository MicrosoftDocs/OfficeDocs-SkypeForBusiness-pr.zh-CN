---
title: Microsoft Teams 中的 Walkie Talkie 应用程序
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: 如何在 Microsoft Teams 中从 ITAdmin 角度配置 Walkie Talkie 应用。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: eb00501a0c795f754c927dd9ed3bd5114f61fab7
ms.sourcegitcommit: b8c4536db4ce9ea682e247d6c8ee7019b08462f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/18/2021
ms.locfileid: "50875042"
---
# <a name="walkie-talkie-app-in-microsoft-teams"></a>Microsoft Teams 中的 Walkie Talkie 应用

Teams 中的 Walkie Talkie 应用为团队提供即时 (PTT) 通信，现在可在 Android 上使用。 Walkie Talkie 允许用户使用他们作为其成员的相同基础频道来与团队联系。 只有通过频道连接到 Walkie Talkie 的用户才能成为参与者，并且可以使用推送到交谈来相互通信，一次一个。

借助 Teams 中的 Walkie Talkie，一线员工现在无需携带大量无线电即可安全地与熟悉的 PTT 体验进行通信，Walkie Talkie 可在任何位置使用 WiFi 或移动电话 Internet 连接工作。

## <a name="getting-started"></a>入门

### <a name="deploying-walkie-talkie"></a>部署 Walkie Talkie

目前，未预安装 Walkie Talkie。 若要为组织中用户启用此功能，需要将 Walkie Talkie 添加到从 Teams [](teams-app-setup-policies.md)管理中心分配给用户的应用   [设置策略](https://admin.teams.microsoft.com/)。

启用后，Walkie Talkie 将在 48 小时内在 Android 应用上可用。

### <a name="adding-walkie-talkie-to-your-app-list"></a>将 Walkie Talkie 添加到应用列表

在 Microsoft Teams 管理中心的 **"Teams 应用** 设置策略"下，应该将"允许用户  >  **固定**"设置为"**打开"。** 然后，在"固定应用"部分下，单击 **"+添加应用"。**

:::image type="content" source="media/deploy-walkie-talkie-1.png" alt-text="显示"固定的应用"部分和要选择的"添加应用"按钮。":::

在右侧 **出现的"添加固定** 应用"面板上，使用"搜索" **文本框查找** Walkie Talkie。 将名称作为搜索结果时，选择名称右边的"添加"按钮，将其添加到列表中。

:::image type="content" source="media/deploy-walkie-talkie-2.png" alt-text="显示搜索结果中已输入 Walkie 的"添加固定应用"边栏和搜索结果中的 Walkie Talkie 应用，旁边有"添加"按钮。":::

Walkie Talkie 应用现在应显示在"固定应用"列表中，单击"保存"按钮后 **即可使用。**

:::image type="content" source="media/deploy-walkie-talkie-3.png" alt-text="显示已添加 Walkie Talkie 应用的"固定应用"列表，以及列表下方的"保存"按钮。":::

### <a name="network-documentation"></a>网络文档

Teams 中的 Walkie Talkie 需要 Internet 连接且低于网络条件才能获得最佳体验。

|指标 | 必需 |
|---|---|
|RTT (延迟)  | < 300 毫秒 |
|抖动 |< 30 毫秒 |
|丢包 |< 1% |

如上所述，通过 IP 网络实时媒体的质量受到网络连接质量的很大影响，尤其是以下数量：

- **延迟** - 这是从网络上点 A 到点 B 获取 IP 数据包所花的时间。 此网络传播延迟实质上与两个点之间的物理距离和光速有关，包括两者之间的各种路由器所取的更多开销。 延迟以 RTT 流量的往返 (时间) 。
- **数据包** 丢失 - 这通常定义为给定时间窗口中丢失的数据包的百分比。 数据包丢失直接影响音频质量 -从小型、单个丢失的数据包几乎没有任何影响，到导致音频完全中断的背对背突发丢失。
- **抖动** - 这是连续数据包之间的延迟的平均变化。

发送或接收音频时，Walkie Talkie 的预期数据使用量约为 20KB/s。 空闲时，Walkie Talkie 的预期数据使用量可忽略不计。

### <a name="walkie-talkie-devices"></a>Walkie Talkie 设备

一线员工经常需要说话和接听 Walkie Talkie 呼叫，即使他们的电话已锁定。 此体验可以通过具有专用 PTT 按钮的专用设备获得。

- 耳机
  - Klein Electronics ([有线耳机](https://www.kleinelectronics.com/poc-accessories/mtwt/)) 
  - [Jabra BlueParrott (无线耳机) ](https://www.blueparrott.com/microsoft-teams-walkie-talkie)
- 粗式手机
  - Samsung Galaxy XCover Pro
    - [详细信息](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/)。
    - [设置指南](https://docs.samsungknox.com/admin/knox-service-plugin/intune-teams.htm)。

> [!NOTE]
> 这些设备未通过 Teams 认证。 已验证它们与 Teams Walkie Talkie 一起工作。

### <a name="license-requirements"></a>许可证要求

Walkie Talkie 应用包含在 [Office 365](https://docs.microsoft.com/MicrosoftTeams/office-365-licensing)订阅中 Teams 的所有付费许可证中。 有关获取 Teams 的信息，请参阅如何 [获取 Microsoft Teams 的访问权限](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)？

> [!NOTE]
> 某些高级功能可能需要额外的许可。 例如，与 Samsung Galaxy XCover Pro 集成需要 Knox 许可证。

## <a name="further-information"></a>更多信息

- ITAdmins 可以通过应用策略保持对谁使用 Walkie Talkie 的控制。
- 如果一线员工使用移动数据通过 Teams 进行通信，Walkie Talkie 将使用相同的方法。
- Walkie Talkie 应在低带宽情况下或智能手机已连接且正常工作的情况下运行良好。 当没有任何连接时，Walkie Talkie 将不起作用。

有关最终用户体验的进一步阅读，请参阅：

- [Teams Walkie Talkie 入门](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [使用 Walkie Talkie 与团队沟通](https://support.microsoft.com/office/communicate-with-your-team-in-walkie-talkie-e4342550-5516-4451-b9ec-93166b60f8a4)
