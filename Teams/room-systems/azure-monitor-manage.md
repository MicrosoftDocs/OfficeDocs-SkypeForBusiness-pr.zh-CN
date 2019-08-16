---
title: 通过 Azure 监视器管理 Microsoft 团队聊天室设备
ms.author: v-lanac
author: lanachin
ms.reviewer: davgroom
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
ms.assetid: f8109905-3279-475f-a64b-31d37af48bfe
ms.collection: M365-voice
description: 本文介绍如何使用 Azure 监视器以集成方式管理 Microsoft 团队聊天室设备。
ms.openlocfilehash: 8dc5c1fa71ab25d4f90326c4c17a608557df8ff8
ms.sourcegitcommit: 1401ee484a2bc8e72d96649b0571bb59198f9dab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/15/2019
ms.locfileid: "36428074"
---
# <a name="manage-microsoft-teams-rooms-devices-with-azure-monitor"></a>通过 Azure 监视器管理 Microsoft 团队聊天室设备

本文介绍如何使用 Azure 监视器以集成方式管理 Microsoft 团队聊天室设备。

你可以将 Azure 监视器配置为提供基本遥测, 以帮助你管理 Skype 会议室设备。 有关详细信息, 请参阅[通过 Azure 监视器规划 Microsoft 团队聊天室管理](azure-monitor-plan.md)和[部署 microsoft 团队聊天室管理和 azure 监视器](azure-monitor-deploy.md)。 随着管理解决方案的成熟, 你可以使用其他数据和管理功能来创建更详细的设备性能视图。

## <a name="understand-the-log-entries"></a>了解日志条目

当 Microsoft 团队聊天室应用在 Windows 事件日志中记录相应信息时, 以下事件说明将每隔五分钟插入到 "事件日志描述" 字段中。 Microsoft Monitoring Agent 将这些记录传递到 Azure 监视器中的日志分析, 这会将它们解析为在[通过 Azure 监视器部署 Microsoft 团队聊天室管理](azure-monitor-deploy.md)时创建的仪表板。 通过仪表板, 你可以查看个别日志条目, 以确定需要的操作课程。

事件 Id 2000 和3000表示所述设备工作正常。 事件 Id 2001 和3001表示发现问题。 如果发现的基线比你设置的基线或你的组织中的其他已部署设备, 则事件 ID 4000 可能需要执行操作。

通过了解这些事件描述，可以快速提醒你出现了什么问题，并让你可以开始进行进一步的故障排除操作。

| 事件&nbsp;ID&nbsp;级别|事件&nbsp;行为&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|事件&nbsp;描述&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|
|:---    |:---   |:---  |
| 2000  <br> 信息 | 这是正常的信号事件。 每隔5分钟, Microsoft 团队聊天室会检查它是否已登录到 Microsoft 团队或 Skype for business, 并具有网络和 Exchange 连接。 <br> 如果所有3个因素均为 true, 则它会将事件 ID 2000 每隔5分钟写入事件日志, 直到设备离线或不再满足一个或多个条件。 | {"说明": "检测信号不正常"。 "ResourceState": "运行状况", "OperationResult": "Pass", "": "": "Windows 10", "OSVersion": "10.0.14393.693", "Alias": "alias<span></span>@contoso .com", "DisplayName": "显示名称"," AppVersion ":" 1.0.38.0 "," IPv4Address ":" 10.10.10.10 "," IPv6Address ":" IP v6 address "} <br><br> 在此示例中, 满足所有检测条件条件, 并将 Microsoft 团队聊天室设备标记为 "正常"。 如果存在错误，则应用会改为记录事件 ID 2001。 |
| 2001  <br> 错误 | 这是应用错误事件。 每隔5分钟, Microsoft 团队聊天室会检查它是否已登录到 Microsoft 团队或具有网络和 Exchange 连接的 Skype for business。 如果有一个或多个因素不为 true, 则它将每隔5分钟将 EventID 2001 写入事件日志, 直到设备离线或再次满足所有条件。  | {"Description":"Network status : Healthy. Exchange status : Connected. **Signin status: Unhealthy.** "," ResourceState ":" 不正常 "," 操作名称 ":" 心跳 "," OperationResult ":" Windows 10 "," OSVersion ":" Windows 10 "," ":" 10.0.14393.693 "," Alias ":" "显示名称", "AppVersion": "1.0.38.0", "IPv4Address": "10.10.10.10", "IPv6Address ":" ip v6 地址 "} <br><br>  在此示例中, Microsoft 团队聊天室确定网络连接正常运行, 并且该应用已连接到 Exchange, 但粗体部分指示该应用未连接。 这可能是设备或主机上的配置问题。  <br> <br> 网络状态显示为 "正常" 或 "不正常"。 如果状态不正常, 可能是网络问题或设备已被拔出 (但您可能还需要 Exchange 和 Microsoft 团队或 Skype for business 错误)。  <br><br> Exchange 状态显示为 "已连接" 或下列之一: 断开连接、连接 AutodiscoveryError (最常见的错误)、GeneralError 或 ServerVersionNotSupported。 如果状态为 "正在连接", 请等到发送下一个运行状况消息时, 如果有其他错误, 请参阅管理员有解决 Exchange 问题的经验。  <br><br>  登录状态 (指示应用已登录) 显示为 "正常" 或 "运行不正常"。 如果状态为不正常，请派遣技术人员做进一步调查。 |
| 3000  <br> 信息 | 此事件验证硬件检查是否已运行且发现正常。 每5分钟 Microsoft 团队聊天室检查已配置的硬件组件 (如会议室显示、麦克风、扬声器和摄像头) 是否已连接并正常工作。 如果所有组件都运行正常, 它会将 EventID 3000 写入事件日志。 此事件每5分钟写入一次, 除非已连接的设备出现问题。  <br> | {"说明": "HardwareCheckEngine 为正常状态"。 "ResourceState": ""、"OperationResult": "HardwareCheckEngine"、"": "Pass"、"OS": "Windows 10"、"OSVersion": "10.0.14393.693"、"Alias": "alias<span></span>@contoso .com", "DisplayName ":" 显示名称 "," AppVersion ":" 1.0.38.0 "," IPv4Address ":" 10.10.10.10 "," IPv6Address ":" ip v6 address "}  <br><br> 在该示例中，所有硬件检查均通过。 如果出现错误, 应用将改为记录事件 ID 3001。 |
| 3001  <br> 错误事件  | 这是硬件错误事件。 Microsoft 团队聊天室应用具有一个过程, 该过程检查连接的硬件组件 (室内、麦克风、扬声器、摄像头) 的运行状况是否每隔5分钟。 如果一个或多个组件运行不正常, 它会将 EventID 3001 写入事件日志。 此事件每5分钟写入一次, 直到修复设备问题。   | {"说明": "**会议室的前面显示状态:** " 不正常 "。 Configured display count is 2. Real display count is 0. **Conference Microphone status : Unhealthy.** Conference Speaker status : Healthy. Default Speaker status : Healthy. "相机状态:", "ResourceState": "不正常"、"操作名称": "HardwareCheckEngine"、"OperationResult": ""、"OS": "Windows 10"、"OSVersion": "10.0.14393.1198"、"Alias": "<span></span>alias @contoso .com"、"DisplayName": "Yosemite会议室 "," AppVersion ":" 2.0.58.0 "," IPv4Address ":" 10.10.10.10 "," IPv6Address ":" IPv6Address "," IPv4Address2 ":" 10.10.10.10 "} <br><br>  外围硬件显示为正常或不正常。 <br> 在该示例中，在会议室前面配置了两个显示器，目前两个显示器均不可用。 会议麦克风状态不正常, 这可能有几个可能的原因。 由于至少有一个资源未通过检查，因此 ResourceState 显示为不正常。 请派遣技术人员做进一步调查。 |
| 4000  <br> 信息  <br> | 这是应用重启事件。 每次应用重启时，都会将此事件记录到 Windows 事件日志中。  <br> | {"说明": "应用重启", "ResourceState": "Restart", "OperationResult": "": "Pass", "OS": "Windows 10", "OSVersion": "10.0.14393.693", "Alias": "alias<span></span>@domain .com", "DisplayName": "显示名称", "AppVersion ":" 1.0.38.0 "," IPv4Address ":" 10.10.10.10 "," IPv6Address ":" ip v6 地址 "} <br><br> 由于各种原因, 应用可能会重启。 比较同一建筑物和不同建筑物中的设备重启频率。 请牢记已知问题 (如电源波动和故障), 因为这可能会提供基础结构问题的线索。|

## <a name="see-also"></a>另请参阅
 

[通过 Azure 监视器规划 Microsoft 团队聊天室管理](azure-monitor-plan.md)

[通过 Azure 监视器部署 Microsoft 团队聊天室管理](azure-monitor-deploy.md)
