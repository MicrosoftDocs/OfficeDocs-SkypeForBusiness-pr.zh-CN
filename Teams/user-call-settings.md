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
description: 了解如何为呼叫转接和委派配置用户设置。
ms.openlocfilehash: 46fc88d20efb14ea130f38d9be284f8faad6f80f
ms.sourcegitcommit: 3beef904411a9d5787a73678464003a868630649
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64817773"
---
# <a name="configure-call-settings-for-your-users"></a>为用户配置呼叫设置

本文介绍管理员如何更改用户的呼叫转接和委派设置。 你可能想要更改这些设置，例如，如果：

- 用户请病假，你需要确保将给用户的传入呼叫转发给同事。

- 你需要检查部门中所有用户的呼叫转发设置，并根据需要对其进行更正。

- 已雇用一名新助理，你需要将助理添加为一组员工的代理人。

可以使用Teams管理中心或 Teams PowerShell cmdlet 来查看和更改用户的呼叫设置。

若要为用户设置呼叫设置，用户必须具有分配Microsoft 电话系统许可证。

## <a name="use-the-teams-admin-center"></a>使用Teams管理中心

可以使用Teams管理中心为用户配置呼叫转发和未应答设置、组呼叫取件和呼叫委派。 

若要配置即时调用转发设置，请执行以下操作：

1. 在Teams管理中心，转到 **UsersManage**  >  用户并选择用户。

2. 在“用户详细信息”页上，转到 **“语音”** 选项卡。

3. 在 **“呼叫应答规则**”下，选择 **“立即转发**”，然后选择适当的呼叫转发类型和目标。

若要配置同时响铃，请在同一页上选择 **“响铃”用户的设备**。 在“ **还允许** ”下拉列表中，选择相应的同时响铃设置。

若要配置未答复的设置，请在同一页上选择“ **If 未应答** ”下拉列表中的相应设置。 在 **重定向** 下拉列表之前的环形中，指定要等待的秒数。

呼叫委派和组呼叫取件的配置通过选择适当的类型集成到呼叫转发和未答复的设置中。 例如，若要配置调用也应响铃用户委托，请在同一页上选择“**也允许**”下的 **呼叫委** 派。 然后，通过选择 **“添加人员** ”并单击“ **保存**”来添加相应的委托。


## <a name="use-powershell"></a>使用 PowerShell

可以使用 PowerShell 为用户配置呼叫转发和委派设置。  你将使用以下 cmdlet，这些 cmdlet 在 Teams PowerShell 模块版本 4.0 或更高版本中提供：

- [Get-CsUserCallingSettings](/powershell/module/teams/get-csusercallingsettings?view=teams-ps) - 显示用户的呼叫转发设置、委托和委派者信息。

- [Set-CsUserCallingSettings](/powershell/module/teams/set-csusercallingsettings?view=teams-ps) - 设置用户的调用转发设置。

- [New-CsUserCallingDelegate](/powershell/module/teams/new-csusercallingdelegate?view=teams-ps) - 添加具有用户权限的新委托。

-   [Set-CsUserCallingDelegate](/powershell/module/teams/set-csusercallingdelegate?view=teams-ps) - 更改现有委托的权限。

-   [Remove-CsUserCallingDelegate](/powershell/module/teams/remove-csusercallingdelegate?view=teams-ps) - 从用户中删除委托。


### <a name="display-call-forward-and-delegation-settings-for-a-user"></a>显示用户的呼叫转发和委派设置

若要显示用户的当前呼叫转发和委派设置，请使用Get-CsUserCallingSettings cmdlet，如以下示例所示：

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

输出显示用户 1 已同时向配置的委托响铃。 未接听的呼叫在 20 秒后发送到语音邮件。 User2 定义为具有所有委托权限的委托。


### <a name="set-call-forward-settings-for-a-user"></a>为用户设置呼叫转发设置

若要将 user1 的所有调用转发到 user2，请使用Set-CsUserCallingSettings cmdlet，如以下示例所示： 

```PowerShell
Set-CsUserCallingSettings -Identity user1@contoso.com -IsForwardingEnabled $true -ForwardingType Immediate -ForwardingTargetType SingleTarget -ForwardingTarget user2@contoso.com
```

若要同时为 user3 拨打所有委托，请使用Set-CsUserCallingSettings cmdlet，如以下示例所示： 

```PowerShell
Set-CsUserCallingSettings -Identity user3@contoso.com -IsForwardingEnabled $true -ForwardingType Simultaneous -ForwardingTargetType MyDelegates
```

以下示例使用 Set-CsUserCallingSettings cmdlet 为 user4 配置呼叫组，用户 5 和 user6 为成员。 对组成员的所有调用都按定义的顺序转发： 

```PowerShell
$cgm = @("user5@contoso.com","user6@contoso.com")

Set-CsUserCallingSettings -Identity user4@contoso.com -CallGroupOrder InOrder -CallGroupTargets $cgm

Set-CsUserCallingSettings -Identity user4@contoso.com -IsForwardingEnabled $true -ForwardingType Immediate -ForwardingTargetType Group
```

有关更多示例，请参阅 [Set-CsUserCallingSettings](/powershell/module/teams/get-csusercallingsettings?view=teams-ps)。

### <a name="add-a-calling-delegate-for-a-user"></a>为用户添加调用委托

若要将 user2 添加为允许所有权限的 user1 委托，请使用New-CsUserCallingDelegate cmdlet，如以下示例所示： 

```PowerShell
New-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com -MakeCalls $true -ReceiveCalls $true -ManageSettings $true
```

### <a name="change-calling-delegate-permissions"></a>更改调用委托权限

若要更改委托权限（例如不允许 user2 对 user1 进行调用）请使用Set-CsUserCallingDelegate cmdlet，如以下示例所示： 

```PowerShell
Set-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com -MakeCalls $false
```

### <a name="remove-a-calling-delegate-for-a-user"></a>删除用户的调用委托

若要删除 user2 作为 user1 的委托，请使用Remove-CsUserCallingDelegate cmdlet，如以下示例所示： 

```PowerShell
Remove-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com
```


## <a name="related-topics"></a>相关主题

- [Get-CsUserCallingSettings](/powershell/module/teams/get-csusercallingsettings?view=teams-ps) 

- [Set-CsUserCallingSettings](/powershell/module/teams/set-csusercallingsettings?view=teams-ps) 

- [New-CsUserCallingDelegate](/powershell/module/teams/new-csusercallingdelegate?view=teams-ps) 

-   [Set-CsUserCallingDelegate](/powershell/module/teams/set-csusercallingdelegate?view=teams-ps) 

-   [Remove-CsUserCallingDelegate](/powershell/module/teams/remove-csusercallingdelegate?view=teams-ps) 
