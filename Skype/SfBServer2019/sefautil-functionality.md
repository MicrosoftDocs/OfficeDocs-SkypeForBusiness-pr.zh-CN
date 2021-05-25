---
title: 2019 年 2 月支持在 PowerShell Skype for Business Server SEFAUtil 功能
ms.reviewer: rogupta
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.date: 07/22/2019
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 摘要：了解如何在安装累积更新 1 后，在 Skype for Business Server 2019 使用 PowerShell 获取 SEFAUtil 功能。
ms.openlocfilehash: fa7bccaa30b559bf694274471b1f8883e8482861
ms.sourcegitcommit: 330e60ff3549cd5cff5b52ad95dc4259e4e8de13
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/24/2021
ms.locfileid: "52629001"
---
# <a name="using-sefautil-functionality-via-powershell-in-skype-for-business-server-2019"></a>在 2019 年 10 月通过 PowerShell Skype for Business Server SEFAUtil 功能

SEFAUtil (辅助扩展功能激活) 允许 Skype for Business Server 管理员和技术支持代理代表 Skype for Business Server 用户配置委派响铃、呼叫转发和组内呼叫接听设置。 此工具还允许管理员查询为特定用户发布的呼叫路由设置。 安装 2019 Skype for Business Server 2019 年 7 月累积更新后，当前仅能通过 SEFAUtil 管理的以下功能也可通过 PowerShell 进行管理：

- [呼叫转发设置](#call-forwarding-settings)
- [委派设置](#delegation-settings)
- [团队成员和相关设置](#team-members-and-related-settings)

## <a name="call-forwarding-settings"></a>呼叫转发设置

管理员可以在 PowerShell 中通过以下 cmdlet 更改呼叫转发设置：

- `Get-CsUserCallForwardingSettings -Identity <UserIdParameter>`

此 cmdlet 将指定用户的呼叫转发设置作为对象返回，并在屏幕上显示相同的设置。

- `Set-CsUserCallForwardingSettings -Identity <UserIdParameter> [Param1 <Value>] [Param2 <Value>]…`

此 cmdlet 可修改指定用户的呼叫转发设置。 此 cmdlet 将指定用户的呼叫转发设置作为对象返回，如果成功，则在屏幕上显示相同的设置。 如果失败，将显示相应的错误消息。

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToVoicemail] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

此 cmdlet 可禁用用户的呼叫转发设置， (此处显示了两个不同的参数) 。

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableForwarding <String> [-Delegates <PSListModifier>] [-DelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

此 cmdlet 可修改用户的呼叫转发设置。

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToVoicemail]  [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>] [-Team <PSListModifier>] [-TeamDelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>]  [-Team <PSListModifier>]  [-TeamDelegateRingWaitTime <TimeSpan>]  [-SettingsActiveWorkHours]`

此 cmdlet 使用两个参数示例 (同时修改同时响铃设置，一个针对语音邮件未answered，另一个未answered to other) 。

## <a name="delegation-settings"></a>委派设置

管理员可以在 PowerShell 中通过以下 cmdlet 更改委派设置：

- `Get-CsuserDelegates -Identity <UserIdParameter>`

此 cmdlet 返回委派列表的对象，并显示指定用户的委派列表（如果成功）。 如果失败，将显示相应的错误消息。

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates <PSListModifier>]`

此 cmdlet 可修改指定用户的委派设置，返回委派列表的对象，并显示委派列表（如果成功）。 如果失败，将显示相应的错误消息。 

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{add=[list]}] [-Delegates @{remove=[list]}]`

此 cmdlet 可添加或删除代理。

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{replace=[list]}]`

此 cmdlet 将委派列表设置到特定代理。

## <a name="team-members-and-related-settings"></a>团队成员和相关设置

管理员可以在 PowerShell 中通过以下 cmdlet 更改团队成员和相关设置：

- `Get-CsUserTeamMembers -Identity <UserIdParameter>`

此 cmdlet 返回包含团队成员列表的对象，如果成功，则在屏幕上显示该对象。 如果失败，将显示相应的错误消息。

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team <PSListModifier>]`

此 cmdlet 可修改指定用户的团队成员列表，返回一个包含团队成员列表的对象，如果成功，则在屏幕上显示该对象。 如果失败，将显示相应的错误消息。

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{add=[list]}] [-Team @{remove=[list]}]`

此 cmdlet 可添加或删除团队成员。

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{replace=[list]}]`

此 cmdlet 将团队列表设置给特定成员。

## <a name="more-information"></a>更多信息

对于本地部署，根据下面指定的访问级别，此功能中引入的 cmdlet 只能由以下各组的成员运行：

- CsAdministrator – 获取和设置所有 cmdlet
- CsVoiceAdministrator - 获取和设置所有 cmdlet
- CsHelpDesk - 获取所有 cmdlet

有关这些管理员角色详细信息，请参阅 Create [Skype for Business Server Control Panel Administrators](../SfbServer/help-topics/help-depwiz/create-skype-for-business-server-control-panel-administrators.md)。 管理员可以直接或远程登录到服务器计算机来访问这些 cmdlet。
对于混合部署，Skype for Business管理员应能够调用所有 cmdlet 的 Get 和 Set。 有关角色的完整列表详细信息，请参阅关于 [管理员角色](/microsoft-365/admin/add-users/about-admin-roles)。

> [!NOTE]
> 必须启用服务器自动发现。 不会引入其他许可要求来使用 cmdlet。
