---
title: 支持在 Skype for business Server 2019 中的 PowerShell 中使用 SEFAUtil 功能
ms.reviewer: rogupta
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.date: 07/22/2019
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
description: '摘要: 在安装累积更新1之后, 了解如何使用 PowerShell 获取 Skype for Business Server 2019 中的 SEFAUtil 功能。'
ms.openlocfilehash: 1c5d8d32c1b7b1b988b0ab39c79e4a7f40752875
ms.sourcegitcommit: 14700a4faab81a294ac794f25b26619a5ed242a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/23/2019
ms.locfileid: "35821319"
---
# <a name="using-sefautil-functionality-via-powershell-in-skype-for-business-server-2019"></a>在 Skype for business Server 2019 中通过 PowerShell 使用 SEFAUtil 功能

SEFAUtil (辅助扩展功能激活) 使 Skype for Business 服务器管理员和支持人员可以代表 Skype for business Server 用户配置代理响铃、呼叫转接和群组呼叫装货设置。 此工具还使管理员能够查询为特定用户发布的呼叫路由设置。 安装此更新后, 当前只能通过 SEFAUtil 管理的以下功能也将通过 PowerShell 进行管理:

- [呼叫转接设置](#call-forwarding-settings)
- [委派设置](#delegation-settings)
- [团队成员和相关设置](#team-members-and-related-settings)

## <a name="call-forwarding-settings"></a>呼叫转接设置

管理员可以使用 PowerShell 中的以下 cmdlet 更改呼叫转接设置:

- `Get-CsUserForwardingSettings -Identity <UserIdParameter>`

此 cmdlet 以对象的形式返回指定用户的呼叫转接设置, 并在屏幕上显示相同的外观。

- `Set-CsUserForwardingSettings -Identity <UserIdParameter> [Param1 <Value>] [Param2 <Value>]…`

此 cmdlet 修改指定用户的呼叫转接设置。 此 cmdlet 以对象的形式返回指定用户的 "呼叫转接" 设置, 并在屏幕上显示 "相同" (如果成功)。 如果出现故障, 将显示相应的错误消息。

- `Set-CsUserForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToVoicemail] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

此 cmdlet 将禁用用户的呼叫转接设置 (此处显示两个不同的参数示例)。

- `Set-CsUserForwardingSettings [-Identity] <UserIdParameter> -EnableForwarding <String> [-Delegates <PSListModifier>] [-DelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

此 cmdlet 修改用户的呼叫转接设置。

- `Set-CsUserForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToVoicemail]  [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>] [-Team <PSListModifier>] [-TeamDelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>]  [-Team <PSListModifier>]  [-TeamDelegateRingWaitTime <TimeSpan>]  [-SettingsActiveWorkHours]`

此 cmdlet 修改 SimulRing 设置 (同样, 有两个参数示例, 一个用于无人接听语音邮件, 第二个是未答复其他设置)。

## <a name="delegation-settings"></a>委派设置

管理员可以使用 PowerShell 中的以下 cmdlet 更改委派设置:

- `Get-CsuserDelegates -Identity <UserIdParameter>`

此 cmdlet 返回代理人列表的对象, 并显示指定用户的委派列表 (如果成功)。 如果出现故障, 将显示相应的错误消息。

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates <PSListModifier>]`

此 cmdlet 修改指定用户的委派设置, 返回代理人列表的对象, 并显示代理人的列表 (如果成功)。 如果出现故障, 将显示相应的错误消息。 

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{add=[list]}] [-Delegates @{remove=[list]}]`

此 cmdlet 添加或删除代理人。

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{replace=[list]}]`

此 cmdlet 将委派列表设置为特定代理人。

## <a name="team-members-and-related-settings"></a>团队成员和相关设置

管理员可以使用 PowerShell 中的以下 cmdlet 更改团队成员和相关设置:

- `Get-CsUserTeamMembers -Identity <UserIdParameter>`

此 cmdlet 返回包含团队成员列表的对象, 并在屏幕上显示对象 (如果成功)。 如果出现故障, 将显示相应的错误消息。

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team <PSListModifier>]`

此 cmdlet 修改指定用户的团队成员列表, 返回一个包含团队成员列表的对象, 并在屏幕上显示该对象 (如果成功)。 如果出现故障, 将显示相应的错误消息。

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{add=[list]}] [-Team @{remove=[list]}]`

此 cmdlet 将添加或删除团队成员。

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{replace=[list]}]`

此 cmdlet 将团队列表设置为特定成员。

## <a name="more-information"></a>详细信息

对于本地部署, 此功能中引入的 cmdlet 只能由下列组的成员根据以下指定的访问级别来运行:

- CsAdministrator –获取并设置所有 cmdlet
- CsVoiceAdministrator-获取并设置所有 cmdlet
- CsHelpDesk-获取所有 cmdlet

有关这些管理员角色的详细信息, 请参阅[创建 Skype For Business 服务器控制面板管理员](../SfbServer/help-topics/help-depwiz/create-skype-for-business-server-control-panel-administrators.md)。 管理员可以直接或远程登录到服务器计算机来访问这些 cmdlet。
对于混合部署, Skype for Business 管理员应该能够为所有 cmdlet 调用 Get 和 Set。 有关完整的角色列表的详细信息, 请参阅[关于 Office 365 管理员角色](https://docs.microsoft.com/en-us/office365/admin/add-users/about-admin-roles)

> [!NOTE]
> 必须启用服务器自动发现。 不会引入使用 cmdlet 的其他许可要求。
