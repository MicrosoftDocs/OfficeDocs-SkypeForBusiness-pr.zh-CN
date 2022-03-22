---
title: 为用户配置呼叫设置
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jenstr
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.callqueues.overview"
- Phone System - seo-marvel-apr2020
description: 了解如何配置呼叫转发和委派的用户设置。
ms.openlocfilehash: 5443ad958d23753b1d67d42782ddab41d9d6d080
ms.sourcegitcommit: ff975c21725e1812e6db8fc9fe37de1362f168c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/11/2022
ms.locfileid: "63689057"
---
# <a name="configure-call-settings-for-your-users"></a>为用户配置呼叫设置

本文介绍管理员如何更改用户的呼叫转发和委派设置。 可能需要更改这些设置，例如，如果：

- 用户病假外出，你需要确保将传入用户的呼叫转发给同事。

- 需要检查部门中所有用户的呼叫转发设置，并可能适当地更正这些设置。

- 已雇用一个新助理，你需要将助理添加为一组员工的代理人。

可以使用 Teams 管理Teams PowerShell cmdlet 来查看和更改用户的呼叫设置。

若要为用户设置呼叫设置，用户必须具有Microsoft 电话许可证。

## <a name="use-the-teams-admin-center"></a>使用 Teams 管理中心

可以使用管理Teams为用户配置组呼叫取件和呼叫委派。 

> [!NOTE]
> 配置呼叫前向设置的选项当前在 Teams中心中不可用。

配置群组呼叫取件：

1. 在Teams管理中心，转到 **"用户** > **""管理用户"** 并选择一个用户。

2. 在用户详细信息页上，转到"语音 **"** 选项卡。

3. 在" **群组呼叫取件"** 下，选择" **添加人员"**。 

4. 指定呼叫延迟 **和订单的设置**。

若要配置委派，请在同一页上转到" **呼叫委派"，** 然后选择" **添加人员"**。

## <a name="use-powershell"></a>使用 PowerShell

可以使用 PowerShell 为用户配置呼叫转发和委派设置。  将使用以下 cmdlet，这些 cmdlet Teams PowerShell 模块 4.0 或更高版本中提供：

- [Get-CsUserCallingSettings](/powershell/module/teams/get-csusercallingsettings?view=teams-ps) - 显示用户的呼叫转发设置、代理人和委派者信息。

- [Set-CsUserCallingSettings](/powershell/module/teams/set-csusercallingsettings?view=teams-ps) - 设置用户的呼叫转发设置。

- [New-CsUserCallingDelegate](/powershell/module/teams/new-csusercallingdelegate?view=teams-ps) - 添加具有用户权限的新委托。

-   [Set-CsUserCallingDelegate](/powershell/module/teams/set-csusercallingdelegate?view=teams-ps) - 更改现有委托的权限。

-   [Remove-CsUserCallingDelegate](/powershell/module/teams/remove-csusercallingdelegate?view=teams-ps) - 从用户中删除委托。


### <a name="display-call-forward-and-delegation-settings-for-a-user"></a>显示用户的呼叫转发和委派设置

若要显示用户的当前呼叫转发和委派设置，请使用 Get-CsUserCallingSettings cmdlet，如以下示例所示：

```PowerShell
Get-CsUserCallingSettings -Identity user1@contoso.com
SipUri                    : sip:opr1@contoso.com
IsForwardingEnabled       : True
ForwardingType            : Simultaneous
ForwardingTarget          :
ForwardingTargetType      : MyDelegates
IsUnansweredEnabled       : True
UnansweredTarget          :
UnansweredTargetType      : Voicemail
UnansweredDelay           : 00:00:20
Delegates                 : Id:user2@contoso.com
Delegators                : 
CallGroupOrder            : InOrder
CallGroupTargets          : {}
GroupMembershipDetails    :
GroupNotificationOverride : Ring

(Get-CsUserCallingSettings -Identity user1@contoso.com).Delegates

Id             : user2@contoso.com
MakeCalls      : True
ManageSettings : True
ReceiveCalls   : True
```

输出显示 user1 已同时向已配置的代理人响铃。 未接听的呼叫在 20 秒后发送到语音邮件。 User2 定义为具有所有代理权限的委托。


### <a name="set-call-forward-settings-for-a-user"></a>为用户设置呼叫转发设置

若要将 user1 的所有调用转发到 user2，Set-CsUserCallingSettings cmdlet，如以下示例所示： 

```PowerShell
Set-CsUserCallingSettings -Identity user1@contoso.com -IsForwardingEnabled $true -ForwardingType Immediate -ForwardingTargetType SingleTarget -ForwardingTarget user2@contoso.com
```

若要同时圈出 user3 的所有代理人，请使用 Set-CsUserCallingSettings cmdlet，如以下示例所示： 

```PowerShell
Set-CsUserCallingSettings -Identity user3@contoso.com -IsForwardingEnabled $true -ForwardingType Simultaneous -ForwardingTargetType MyDelegates
```

以下示例使用 Set-CsUserCallingSettings cmdlet 为 user4 配置调用组，将 user5 和 user6 作为成员。 对组成员的所有调用将按照定义的顺序转发： 

```PowerShell
$cgm = @("user5@contoso.com","user6@contoso.com")

Set-CsUserCallingSettings -Identity user4@contoso.com -CallGroupOrder InOrder -CallGroupTargets $cgm

Set-CsUserCallingSettings -Identity user4@contoso.com -IsForwardingEnabled $true -ForwardingType Immediate -ForwardingTargetType Group
```

有关更多示例，请参阅 [Set-CsUserCallingSettings](/powershell/module/teams/get-csusercallingsettings?view=teams-ps)。

### <a name="add-a-calling-delegate-for-a-user"></a>为用户添加呼叫代理人

若要将 user2 添加为具有所有权限的用户 1 的委托，请使用 New-CsUserCallingDelegate cmdlet，如以下示例所示： 

```PowerShell
New-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com -MakeCalls $true -ReceiveCalls $true -ManageSettings $true
```

### <a name="change-calling-delegate-permissions"></a>更改呼叫代理权限

若要更改委托权限（例如，不允许 user2 对 user1 进行调用），请使用 Set-CsUserCallingDelegate cmdlet，如以下示例所示： 

```PowerShell
Set-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com -MakeCalls $false
```

### <a name="remove-a-calling-delegate-for-a-user"></a>删除用户的呼叫代理人

若要删除 user2 作为 user1 的委托，请使用 Remove-CsUserCallingDelegate cmdlet，如以下示例所示： 

```PowerShell
Remove-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com
```


## <a name="related-topics"></a>相关主题

- [Get-CsUserCallingSettings](/powershell/module/teams/get-csusercallingsettings?view=teams-ps) 

- [Set-CsUserCallingSettings](/powershell/module/teams/set-csusercallingsettings?view=teams-ps) 

- [New-CsUserCallingDelegate](/powershell/module/teams/new-csusercallingdelegate?view=teams-ps) 

-   [Set-CsUserCallingDelegate](/powershell/module/teams/set-csusercallingdelegate?view=teams-ps) 

-   [Remove-CsUserCallingDelegate](/powershell/module/teams/remove-csusercallingdelegate?view=teams-ps) 
