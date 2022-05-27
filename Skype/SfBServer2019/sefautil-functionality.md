---
title: 支持在 2019 Skype for Business Server Skype PowerShell 中使用 SEFAUtil 功能
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
ms.localizationpriority: medium
ms.collection: IT_Skype16
description: 摘要：了解如何在安装累积更新 1 后使用 PowerShell 在 2019 Skype for Business Server获取 SEFAUtil 功能。
ms.openlocfilehash: 07d05ef1687fa9ca14f7e90108ae8b5c0e7e3bb9
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676534"
---
# <a name="using-sefautil-functionality-via-powershell-in-skype-for-business-server-2019"></a>在 2019 Skype for Business Server通过 PowerShell 使用 SEFAUtil 功能

SEFAUtil (辅助扩展功能激活) 使Skype for Business Server管理员和技术支持人员能够代表Skype for Business Server用户配置委托响铃、呼叫转发和组呼叫取件设置。 SEFAUtil 还允许管理员查询特定用户的呼叫路由设置。

安装 Skype for Business Server 2019 年 7 月累积更新后，仅通过 SEFAUtil 提供的以下功能也可在 Skype PowerShell 中使用：

- [呼叫转接设置](#call-forwarding-settings)
- [委派设置](#delegation-settings)
- [团队成员和相关设置](#team-members-and-related-settings)

## <a name="call-forwarding-settings"></a>呼叫转接设置

管理员可以在 PowerShell 中使用以下命令更改呼叫转发设置：

```powershell
Get-CsUserCallForwardingSettings -Identity <UserIdParameter>
```

此命令返回指定用户的调用转发设置作为对象，并在屏幕上显示相同的设置。

```powershell
Set-CsUserCallForwardingSettings -Identity <UserIdParameter> [Param1 <Value>] [Param2 <Value>]...
```

此命令修改指定用户的呼叫转发设置。 此命令返回指定用户的调用转发设置作为对象，并在屏幕上显示相同的设置。 如果命令未成功，则会显示适当的错误消息。

```powershell
Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToVoicemail] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]
```

```powershell
Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]
```

此命令禁用用户的呼叫转接设置 () 此处显示两个不同的参数示例。

```powershell
Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableForwarding <String> [-Delegates <PSListModifier>] [-DelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]
```

此命令修改用户的呼叫转发设置。

```powershell
Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToVoicemail]  [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>] [-Team <PSListModifier>] [-TeamDelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]
```

```powershell
Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>]  [-Team <PSListModifier>]  [-TeamDelegateRingWaitTime <TimeSpan>]  [-SettingsActiveWorkHours]
```

此命令再次修改同时 (的环形设置，其中两个参数示例，一个用于未答复语音邮件，另一个未回答其他) 。

## <a name="delegation-settings"></a>委派设置

管理员可以在 PowerShell 中使用以下命令更改委派设置：

```powershell
Get-CsuserDelegates -Identity <UserIdParameter>
```

此命令返回委托列表的对象，并显示指定用户的委托列表。 如果命令未成功，则会显示适当的错误消息。

```powershell
Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates <PSListModifier>]
```

此命令修改指定用户的委派设置，返回委托列表的对象，并显示委托列表。 如果命令未成功，则会显示适当的错误消息。

```powershell
Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{add=[list]}] [-Delegates @{remove=[list]}]
```

此命令添加或删除委托。

```powershell
Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{replace=[list]}]
```

此命令将委托列表设置为特定委托。

## <a name="team-members-and-related-settings"></a>团队成员和相关设置

管理员可以在 PowerShell 中使用以下命令更改团队成员和相关设置：

```powershell
Get-CsUserTeamMembers -Identity <UserIdParameter>
```

此命令返回包含团队成员列表的对象，并在屏幕上显示该对象。 如果命令未成功，则会显示适当的错误消息。

```powershell
Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team <PSListModifier>]
```

此命令修改指定用户的团队成员列表，返回包含团队成员列表的对象，并在屏幕上显示该对象。 如果命令未成功，则会显示适当的错误消息。

```powershell
Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{add=[list]}] [-Team @{remove=[list]}]
```

此命令添加或删除团队成员。

```powershell
Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{replace=[list]}]
```

此命令将团队列表设置为特定成员。

## <a name="more-information"></a>更多信息

对于本地部署，根据下面指定的访问级别，此功能中引入的 cmdlet 只能由以下组的成员运行：

- CsAdministrator - 获取和设置所有 cmdlet
- CsVoiceAdministrator - 获取和设置所有 cmdlet
- CsHelpDesk - 获取所有 cmdlet

有关这些管理员角色的详细信息，请参阅[“创建Skype for Business Server 控制面板管理员](../SfbServer/help-topics/help-depwiz/create-skype-for-business-server-control-panel-administrators.md)”。 管理员可以通过直接或远程登录到服务器计算机来访问这些 cmdlet。
对于混合部署，Skype for Business管理员应该能够为所有 cmdlet 调用“获取”和“设置”。 有关角色的完整列表的详细信息， [请参阅“关于管理员角色](/microsoft-365/admin/add-users/about-admin-roles)”。

> [!NOTE]
> 必须启用服务器自动发现。 不会为使用 cmdlet 引入其他许可要求。
