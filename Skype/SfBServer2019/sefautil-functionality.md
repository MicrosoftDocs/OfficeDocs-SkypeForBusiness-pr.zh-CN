---
title: 在 Skype for business Server 2019 中支持在 PowerShell 中使用 SEFAUtil 功能
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
description: 摘要：了解在安装累积更新1之后，如何使用 PowerShell 获取 Skype for Business Server 2019 中的 SEFAUtil 功能。
ms.openlocfilehash: 19c3ba1124bbc1f32f301096036404f8bd101fe9
ms.sourcegitcommit: 6a4bd155e73ab21944dd5f4f0c776e4cd0508147
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/24/2020
ms.locfileid: "44868549"
---
# <a name="using-sefautil-functionality-via-powershell-in-skype-for-business-server-2019"></a>在 Skype for business Server 2019 中通过 PowerShell 使用 SEFAUtil 功能

SEFAUtil （辅助扩展功能激活）使 Skype for Business Server 管理员和支持人员代理能够代表 Skype for Business Server 用户配置代理响铃、呼叫转接和组呼叫装货设置。 此工具还允许管理员查询为特定用户发布的呼叫路由设置。 安装 Skype for Business Server 2019 年7月累积更新后，当前只能通过 SEFAUtil 管理的以下功能也将通过 PowerShell 进行管理：

- [呼叫转接设置](#call-forwarding-settings)
- [委派设置](#delegation-settings)
- [团队成员和相关设置](#team-members-and-related-settings)

## <a name="call-forwarding-settings"></a>呼叫转接设置

管理员可以使用 PowerShell 中的以下 cmdlet 更改呼叫转接设置：

- `Get-CsUserCallForwardingSettings -Identity <UserIdParameter>`

此 cmdlet 以对象的形式返回指定用户的呼叫转接设置，并在屏幕上显示相同的外观。

- `Set-CsUserCallForwardingSettings -Identity <UserIdParameter> [Param1 <Value>] [Param2 <Value>]…`

此 cmdlet 修改指定用户的呼叫转接设置。 此 cmdlet 以对象的形式返回指定用户的呼叫转接设置，并在出现成功时在屏幕上显示相同的外观。 如果出现故障，将显示相应的错误消息。

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToVoicemail] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

此 cmdlet 禁用用户的呼叫转接设置（我们在此处显示两个不同的参数示例）。

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableForwarding <String> [-Delegates <PSListModifier>] [-DelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

此 cmdlet 修改用户的呼叫转接设置。

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToVoicemail]  [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>] [-Team <PSListModifier>] [-TeamDelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>]  [-Team <PSListModifier>]  [-TeamDelegateRingWaitTime <TimeSpan>]  [-SettingsActiveWorkHours]`

此 cmdlet 修改同时设置（同样，有两个参数示例，一个用于无人答复语音邮件，第二个用于未答复其他设置）。

## <a name="delegation-settings"></a>委派设置

管理员可以使用 PowerShell 中的以下 cmdlet 更改委派设置：

- `Get-CsuserDelegates -Identity <UserIdParameter>`

此 cmdlet 返回 "代理" 列表的对象，并显示指定的用户的代理列表（如果成功）。 如果出现故障，将显示相应的错误消息。

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates <PSListModifier>]`

此 cmdlet 可修改指定的用户的委派设置，返回一个代表 "委派" 列表的对象，并显示代理（如果成功）的列表。 如果出现故障，将显示相应的错误消息。 

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{add=[list]}] [-Delegates @{remove=[list]}]`

此 cmdlet 添加或删除委派。

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{replace=[list]}]`

此 cmdlet 可将委派列表设置为特定委派。

## <a name="team-members-and-related-settings"></a>团队成员和相关设置

管理员可以使用 PowerShell 中的以下 cmdlet 更改团队成员和相关设置：

- `Get-CsUserTeamMembers -Identity <UserIdParameter>`

此 cmdlet 返回一个包含工作组成员列表的对象，并在屏幕上显示该对象（如果成功）。 如果出现故障，将显示相应的错误消息。

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team <PSListModifier>]`

此 cmdlet 可修改指定用户的团队成员列表，返回一个包含工作组成员列表的对象，并在成功时在屏幕上显示该对象。 如果出现故障，将显示相应的错误消息。

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{add=[list]}] [-Team @{remove=[list]}]`

此 cmdlet 添加或删除团队成员。

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{replace=[list]}]`

此 cmdlet 将团队列表设置为特定成员。

## <a name="more-information"></a>更多信息

对于本地部署，此功能中引入的 cmdlet 只能由下列组的成员基于下面指定的访问级别运行：

- CsAdministrator –获取并设置所有 cmdlet
- CsVoiceAdministrator-获取并设置所有 cmdlet
- CsHelpDesk-获取所有 cmdlet

有关这些管理员角色的详细信息，请参阅[创建 Skype For Business Server 控制面板管理员](../SfbServer/help-topics/help-depwiz/create-skype-for-business-server-control-panel-administrators.md)。 管理员可以通过直接或远程登录到服务器计算机来访问这些 cmdlet。
对于混合部署，Skype for Business 管理员应能够调用所有 cmdlet 的 Get 和 Set。 有关完整角色列表的详细信息，请参阅[关于管理员角色](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)。

> [!NOTE]
> 必须启用服务器自动发现。 不会引入使用 cmdlet 的其他许可要求。
