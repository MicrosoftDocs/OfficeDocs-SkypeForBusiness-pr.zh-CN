---
title: 使用 Azure Monitor 监视Microsoft Teams 会议室设备
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: f8109905-3279-475f-a64b-31d37af48bfe
ms.collection:
- M365-collaboration
description: 本文讨论如何使用 Azure Monitor 以集成方式监视Microsoft Teams 会议室设备。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 38238d4b1d0bc33182f002e7dcf6389028315c48
ms.sourcegitcommit: 89904ab4116294ad9e4fd407feba8d7e3eefef10
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/19/2022
ms.locfileid: "66880206"
---
# <a name="monitor-microsoft-teams-rooms-devices-with-azure-monitor"></a>使用 Azure Monitor 监视Microsoft Teams 会议室设备

本文讨论如何使用 Azure Monitor 以集成方式监视Microsoft Teams 会议室。

可以将 Azure Monitor 配置为提供基本遥测数据，以帮助监视 Microsoft Teams 会议室设备。 有关详细信息，请参阅[使用 Azure Monitor 进行计划Microsoft Teams 会议室管理](azure-monitor-plan.md)，并[使用 Azure Monitor 部署Microsoft Teams 会议室管理](azure-monitor-deploy.md)。 随着监视解决方案的成熟，可以使用其他数据和监视功能创建更详细的设备性能视图。

## <a name="understand-the-log-entries"></a>了解日志条目

当Microsoft Teams 会议室应用记录 Windows 事件日志中的相应信息时，以下事件说明每五分钟插入一次事件日志描述字段。 Microsoft Monitoring Agent 将这些记录传递给 Azure Monitor 中的 Log Analytics，后者将其分析为在[使用 Azure Monitor 部署Microsoft Teams 会议室监视](azure-monitor-deploy.md)中创建的仪表板。 使用仪表板，可以查看单个日志条目，以确定操作过程（如果需要）。

事件 ID 2000 和 3000 表示Teams 会议室按预期工作。 事件 ID 2001 和 3001 表示已找到问题。 与你设置的基线或组织中其他已部署的设备相比，事件 ID 4000 可能需要比预期更频繁地执行操作。

通过了解这些事件描述，可以快速提醒你出现了什么问题，并让你可以开始进行进一步的故障排除操作。

| 事件&nbsp;ID&nbsp;级别|事件&nbsp;行为&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|事件&nbsp;说明&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|
|:---    |:---   |:---  |
| 2000  <br> 信息 | 这是正常的信号事件。 每隔 5 分钟，Microsoft Teams 会议室检查它是否已登录到 Microsoft Teams 或Skype for Business并具有网络和 Exchange 连接。 <br> 如果这三个因素都属实，它会每隔 5 分钟将事件 ID 2000 写入事件日志，直到设备脱机或不再满足一个或多个条件。 | `{"Description":"Heartbeat is healthy.", "ResourceState":"Healthy", "OperationName":"Heartbeat", "OperationResult":"Pass", "OS":"Windows 10", "OSVersion":"10.0.14393.693", "Alias":"alias<span></span>@contoso.com",  "DisplayName":"Display name", "AppVersion":"1.0.38.0", "IPv4Address":"10.10.10.10",  "IPv6Address":"IP v6 address"}` <br><br> 在此示例中，满足所有检测信号条件，并且Microsoft Teams 会议室设备标记为正常。 如果存在错误，则应用会改为记录事件 ID 2001。 |
| 2001  <br> 错误 | 这是应用错误事件。 每隔 5 分钟，Microsoft Teams 会议室检查它是否已登录到 Microsoft Teams 或使用网络和 Exchange 连接Skype for Business。 如果一个或多个因素不是真的，它会每隔 5 分钟将 EventID 2001 写入事件日志，直到设备脱机或再次满足所有条件。  | `{"Description":"Network status : Healthy. Exchange status : Connected. Sign in status: Unhealthy. Teams sign in status: Healthy.", "ResourceState":"Unhealthy", "OperationName":"Heartbeat", "OperationResult":"Fail", "OS":"Windows 10", "OSVersion":"10.0.14393.693", "Alias":"", "DisplayName":"Display Name", "AppVersion":"1.0.38.0", "IPv4Address":"10.10.10.10", "IPv6Address":"ip v6 address"}` <br><br>  在此示例中，Microsoft Teams 会议室确定网络连接正常且应用已连接到 Exchange，但加粗部分指示应用未连接。 这可能是设备或主机上的配置问题。  <br> <br> 网络状态显示为“正常”或“不正常”。 如果状态不正常，则可能会出现网络问题，或者设备可能已被拔下 (但也可能出现 Exchange 和 Microsoft Teams 或Skype for Business错误) 。  <br><br> Exchange 状态显示为“已连接”或“已断开连接”、“连接”、“自动发现器” (最常见的错误) 、GeneralError 或 ServerVersionNotSupported。 如果状态为“正在连接”，请等到发送下一条运行状况消息，对于其他错误，请将此问题提交到具有解决 Exchange 问题经验的管理员。  <br><br>  _登录状态_/_Teams 登录状态_ (指示应用已登录到Skype for Business或 Teams) 显示为 _“正常_”或 _“不正常_”。 如果状态为不正常，请派遣技术人员做进一步调查。 |
| 3000  <br> 信息 | 此事件验证是否运行了硬件检查并发现其运行正常。 每隔 5 分钟Microsoft Teams 会议室检查配置的硬件组件（如会议室前显示器、麦克风、扬声器和相机）是否已连接并正常工作。 如果所有组件都正常运行，它会将 EventID 3000 写入事件日志。 除非连接的设备出现问题，否则每隔 5 分钟写一次此事件。  <br> | `{"Description":"HardwareCheckEngine is healthy.",  "ResourceState":"Healthy", "OperationName":"HardwareCheckEngine",  "OperationResult":"Pass", "OS":"Windows 10",  "OSVersion":"10.0.14393.693", "Alias":"alias<span></span>@contoso.com", "DisplayName":"Display Name", "AppVersion":"1.0.38.0",  "IPv4Address":"10.10.10.10", "IPv6Address":"ip v6 address"}` <br><br> 在该示例中，所有硬件检查均通过。 如果出现错误，应用将改为记录事件 ID 3001。 |
| 3001  <br> 错误事件  | 这是硬件错误事件。 Microsoft Teams 会议室应用有一个过程，每隔 5 分钟检查一次会议室前、麦克风、扬声器、相机)  (连接硬件组件的运行状况。 如果一个或多个组件不正常，它会将 EventID 3001 写入事件日志。 此事件每 5 分钟写一次，直到设备问题得到解决。   | `{"Description":" Front of Room Display status : Unhealthy. Configured display count is 2. Real display count is 0. Conference Microphone status : Unhealthy. Conference Speaker status : Healthy. Default Speaker status : Healthy. Camera status : Healthy.", "ResourceState":"Unhealthy", "OperationName":"HardwareCheckEngine", "OperationResult":"Fail", "OS":"Windows 10", "OSVersion":"10.0.14393.1198", "Alias":"alias<span></span>@contoso.com", "DisplayName":"Yosemite conference room", "AppVersion":"2.0.58.0", "IPv4Address":"10.10.10.10", "IPv6Address":"IPv6Address", "IPv4Address2":"10.10.10.10"}` <br><br>  外围硬件显示为正常或不正常。 <br> 在此示例中，配置了两个 _会议室前_ 显示器，目前这两个显示器都不可用。 _会议麦克风状态__不正常_，这可能有几个可能的原因。 由于至少有一个资源未通过检查，因此 ResourceState 显示为不正常。 请派遣技术人员做进一步调查。 |
| 4000  <br> 信息  <br> | 这是应用重启事件。 每次应用重启时，都会将此事件记录到 Windows 事件日志中。  <br> | `{"Description":"App restarts.", "ResourceState":"Healthy", "OperationName":"Restart", "OperationResult":"Pass", "OS":"Windows 10", "OSVersion":"10.0.14393.693", "Alias":"alias<span></span>@domain.com", "DisplayName":"Display Name", "AppVersion":"1.0.38.0", "IPv4Address":"10.10.10.10", "IPv6Address":"ip v6 address"}` <br><br> 由于各种原因，应用可能会重启。 比较同一建筑物和不同建筑物中设备的重启频率。 请记住电源波动和故障等已知问题，因为这可能为基础结构问题提供线索。|

## <a name="related-topics"></a>相关主题
 

[使用 Azure Monitor 规划Microsoft Teams 会议室监视](azure-monitor-plan.md)

[使用 Azure Monitor 部署Microsoft Teams 会议室监视](azure-monitor-deploy.md)
