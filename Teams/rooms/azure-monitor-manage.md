---
title: 使用 Azure Monitor Microsoft Teams 会议室设备
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: f8109905-3279-475f-a64b-31d37af48bfe
ms.collection:
- M365-collaboration
description: 本文讨论如何使用 Azure Monitor Microsoft Teams 会议室集成方式管理设备。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 41375c313940099b6ed6e102e2452290e0817bec
ms.sourcegitcommit: b8c4536db4ce9ea682e247d6c8ee7019b08462f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/18/2021
ms.locfileid: "50874762"
---
# <a name="manage-microsoft-teams-rooms-devices-with-azure-monitor"></a>使用 Azure Monitor Microsoft Teams 会议室设备

本文讨论如何使用 Azure Monitor Microsoft Teams 会议室集成方式管理设备。

可以将 Azure Monitor 配置为提供基本遥测，以帮助管理Microsoft Teams设备。 有关详细信息[，Microsoft Teams 会议室 Azure Monitor](azure-monitor-plan.md)规划管理[，Microsoft Teams 会议室 Azure Monitor 部署](azure-monitor-deploy.md)管理。 随着管理解决方案的成熟，可以使用其他数据和管理功能来创建更详细的设备性能视图。

## <a name="understand-the-log-entries"></a>了解日志条目

当应用在事件日志中记录Microsoft Teams 会议室信息时，每隔五分钟将以下事件说明插入Windows说明。 该Microsoft Monitoring Agent将这些记录传递给 Azure Monitor 中的 Log Analytics，它将这些记录解析为使用 Azure Monitor Microsoft Teams 会议室[管理中创建的仪表板](azure-monitor-deploy.md)。 使用仪表板，可以检查各个日志条目，确定操作步骤（如果需要）。

事件 ID 2000 和 3000 指示问题设备正在正常使用。 事件 ID 2001 和 3001 指示发现了问题。 如果看到的事件 ID 4000 比设置的基线或组织中其他已部署设备的基线要频繁，可能需要采取措施。

通过了解这些事件描述，可以快速提醒你出现了什么问题，并让你可以开始进行进一步的故障排除操作。

| 事件 &nbsp; ID &nbsp; 级别|事件 &nbsp; 行为&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|事件 &nbsp; 说明&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|
|:---    |:---   |:---  |
| 2000  <br> 信息 | 这是正常的信号事件。 每隔 5 分钟Microsoft Teams 会议室检查它是否登录到 Microsoft Teams 或 Skype for Business并且具有网络和Exchange连接。 <br> 如果所有 3 个因素都成立，它将每隔 5 分钟将事件 ID 2000 写入事件日志，直到设备脱机或不再满足一个或多个条件。 | `{"Description":"Heartbeat is healthy.", "ResourceState":"Healthy", "OperationName":"Heartbeat", "OperationResult":"Pass", "OS":"Windows 10", "OSVersion":"10.0.14393.693", "Alias":"alias<span></span>@contoso.com",  "DisplayName":"Display name", "AppVersion":"1.0.38.0", "IPv4Address":"10.10.10.10",  "IPv6Address":"IP v6 address"}` <br><br> 本示例满足所有检测信号条件，Microsoft Teams 会议室设备标记为正常。 如果存在错误，则应用会改为记录事件 ID 2001。 |
| 2001  <br> 错误 | 这是应用错误事件。 每隔 5 分钟Microsoft Teams 会议室检查它是否登录到Microsoft Teams或Skype for Business网络Exchange连接。 如果一个或多个因素不为 true，它会每隔 5 分钟将 EventID 2001 写入事件日志，直到设备脱机或再次满足所有条件。  | `{"Description":"Network status : Healthy. Exchange status : Connected. Signin status: Unhealthy. ", "ResourceState":"Unhealthy", "OperationName":"Heartbeat", "OperationResult":"Fail", "OS":"Windows 10", "OSVersion":"10.0.14393.693", "Alias":"", "DisplayName":"Display Name", "AppVersion":"1.0.38.0", "IPv4Address":"10.10.10.10", "IPv6Address":"ip v6 address"}` <br><br>  此示例中，Microsoft Teams 会议室确定网络连接正常，并且应用已连接到 Exchange，但加粗部分指示应用未连接。 这可能是设备或主机上的配置问题。  <br> <br> 网络状态会显示为"正常"或"不正常"。 如果状态不正常，则可能是网络问题或设备可能拔下 (但可能还出现 Exchange 和 Microsoft Teams 或 Skype for Business 错误) 。  <br><br> "Exchange状态"显示为"已连接"或下列其中一项：已断开连接、正在连接、自动发现 (最常见错误) 、GeneralError 或 ServerVersionNotSupported。 如果状态为"正在连接"，请等到下一条运行状况消息发送完成，对于其他错误，请向具有解决问题经验的管理员Exchange该问题。  <br><br>  "_登录状态 (_ 指示应用已登录 _) 状态为_"正常"或"_不正常"。_ 如果状态为不正常，请派遣技术人员做进一步调查。 |
| 3000  <br> 信息 | 此事件验证是否运行了硬件检查，并发现其运行正常。 每隔 5 Microsoft Teams 会议室检查配置的硬件组件（如房间显示器、麦克风、扬声器和相机）是否连接且正常运行。 如果所有组件都正常运行，它会将 EventID 3000 写入事件日志。 此事件每 5 分钟写入一次，除非已连接的设备存在问题。  <br> | `{"Description":"HardwareCheckEngine is healthy.",  "ResourceState":"Healthy", "OperationName":"HardwareCheckEngine",  "OperationResult":"Pass", "OS":"Windows 10",  "OSVersion":"10.0.14393.693", "Alias":"alias<span></span>@contoso.com", "DisplayName":"Display Name", "AppVersion":"1.0.38.0",  "IPv4Address":"10.10.10.10", "IPv6Address":"ip v6 address"}` <br><br> 在该示例中，所有硬件检查均通过。 如果存在错误，应用将改为记录事件 ID 3001。 |
| 3001  <br> 错误事件  | 这是硬件错误事件。 该应用Microsoft Teams 会议室一个过程，它每隔 5 分钟检查 (、麦克风、扬声器、) 连接的硬件组件的运行状况。 如果一个或多个组件不正常，它会将 EventID 3001 写入事件日志。 此事件每隔 5 分钟写入一次，直到设备问题得到解决。   | `{"Description":" Front of Room Display status : Unhealthy. Configured display count is 2. Real display count is 0. Conference Microphone status : Unhealthy. Conference Speaker status : Healthy. Default Speaker status : Healthy. Camera status : Healthy.", "ResourceState":"Unhealthy", "OperationName":"HardwareCheckEngine", "OperationResult":"Fail", "OS":"Windows 10", "OSVersion":"10.0.14393.1198", "Alias":"alias<span></span>@contoso.com", "DisplayName":"Yosemite conference room", "AppVersion":"2.0.58.0", "IPv4Address":"10.10.10.10", "IPv6Address":"IPv6Address", "IPv4Address2":"10.10.10.10"}` <br><br>  外围硬件显示为正常或不正常。 <br> 此示例中配置了两 _个前_ 室显示，目前这两个屏幕都不可用。 会议 _麦克风状态__不正常_，这可能有几个可能的原因。 由于至少有一个资源未通过检查，因此 ResourceState 显示为不正常。 请派遣技术人员做进一步调查。 |
| 4000  <br> 信息  <br> | 这是应用重启事件。 每次应用重启时，都会将此事件记录到 Windows 事件日志中。  <br> | `{"Description":"App restarts.", "ResourceState":"Healthy", "OperationName":"Restart", "OperationResult":"Pass", "OS":"Windows 10", "OSVersion":"10.0.14393.693", "Alias":"alias<span></span>@domain.com", "DisplayName":"Display Name", "AppVersion":"1.0.38.0", "IPv4Address":"10.10.10.10", "IPv6Address":"ip v6 address"}` <br><br> 应用可能会出于各种原因重新启动。 比较同一大楼和不同建筑物中的设备的重启频率。 请记住电源波动和故障等已知问题，因为这可能提供基础结构问题的线索。|

## <a name="related-topics"></a>相关主题
 

[使用 Azure Monitor Microsoft Teams 会议室计划管理](azure-monitor-plan.md)

[使用 Azure Monitor Microsoft Teams 会议室管理](azure-monitor-deploy.md)
