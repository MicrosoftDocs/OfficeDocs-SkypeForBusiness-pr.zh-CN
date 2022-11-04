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
audience: Admin
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.callqueues.overview
- Phone System
- seo-marvel-apr2020
description: 了解如何为呼叫转接和委派配置用户设置。
ms.openlocfilehash: 7d1ab3252461d57a99956c90a011a43620c76bea
ms.sourcegitcommit: 18e66d54a9e349d4516253addc85cc12892c69a3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2022
ms.locfileid: "68851843"
---
# <a name="configure-call-settings-for-your-users"></a>为用户配置呼叫设置

本文介绍管理员如何更改用户的呼叫转接和委派设置。 你可能想要更改这些设置，例如，如果：

- 用户休病假，你需要确保将用户的来电转接到同事。
- 你需要检查部门中所有用户的呼叫转接设置，并可能根据需要对其进行更正。
- 新助理已被雇用，你需要将该助理添加为一组员工的代理人。

可以使用 Teams 管理中心或 Teams PowerShell cmdlet 查看和更改用户的呼叫设置。

若要为用户设置呼叫设置，用户必须具有分配的 Microsoft 电话系统许可证。

## <a name="use-the-teams-admin-center"></a>使用 Teams 管理中心

可以使用 Teams 管理中心为用户配置呼叫转接和未应答设置、组呼叫应答和呼叫委派。

配置即时呼叫转接设置：

1. 在 Teams 管理中心中，转到 **“用户** > **管理用户** ”，然后选择一个用户。

2. 在用户详细信息页上，转到“ **语音** ”选项卡。

3. 在 **“呼叫应答规则**”下，选择“ **立即转接**”，然后选择相应的呼叫转接类型和目标。

若要配置同时响铃，请在同一页上选择“ **拨打用户设备**”。 在“ **还允许”** 下拉列表中，选择适当的同时响铃设置。

若要配置未处理设置，请在同一页上的“ **如果未得到处理** ”下拉列表中选择相应的设置。 在 **“重定向前的响铃数秒”** 下拉列表中，指定等待的秒数。

通过选择适当的类型，将呼叫委派和组呼叫应答的配置集成到呼叫转接和未应答设置中。 例如，若要配置呼叫还应拨打用户的代理人，请在同一页上选择“**允许**”下的“**呼叫委派**”。 然后，通过选择“ **添加人员** ”并单击“ **保存**”来添加相应的代理人。

此视频演示查看和编辑用户语音设置的步骤。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE546F7?autoplay=false]

## <a name="use-powershell"></a>使用 PowerShell

可以使用 PowerShell 为用户配置呼叫转接和委派设置。  你将使用以下 cmdlet，这些 cmdlet 在 Teams PowerShell 模块 4.0 或更高版本中可用：

- [Get-CsUserCallingSettings](/powershell/module/teams/get-csusercallingsettings) - 显示用户的呼叫转接设置、委托和委托人信息。
- [Set-CsUserCallingSettings](/powershell/module/teams/set-csusercallingsettings) - 设置用户的呼叫转接设置。
- [New-CsUserCallingDelegate](/powershell/module/teams/new-csusercallingdelegate) - 添加具有用户权限的新委托。
- [Set-CsUserCallingDelegate](/powershell/module/teams/set-csusercallingdelegate) - 更改现有委托的权限。
- [Remove-CsUserCallingDelegate](/powershell/module/teams/remove-csusercallingdelegate) - 从用户中删除委托。

### <a name="display-call-forward-and-delegation-settings-for-a-user"></a>显示用户的呼叫转接和委派设置

若要显示用户的当前呼叫转接和委派设置，请使用 Get-CsUserCallingSettings cmdlet，如以下示例所示：

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
Delegates                 : Id:sip:user2@contoso.com
Delegators                :
CallGroupOrder            : InOrder
CallGroupTargets          : {}
GroupMembershipDetails    :
GroupNotificationOverride : Ring

(Get-CsUserCallingSettings -Identity user1@contoso.com).Delegates

Id             : sip:user2@contoso.com
MakeCalls      : True
ManageSettings : True
ReceiveCalls   : True
```

输出显示 user1 同时响铃到已配置的委托。 未接听的呼叫会在 20 秒后发送到语音邮件。 User2 定义为具有所有委托权限的委托。

### <a name="set-call-forward-settings-for-a-user"></a>为用户设置呼叫转接设置

若要将 user1 的所有调用转发到 user2，请使用 Set-CsUserCallingSettings cmdlet，如以下示例所示：

```PowerShell
Set-CsUserCallingSettings -Identity user1@contoso.com -IsForwardingEnabled $true -ForwardingType Immediate -ForwardingTargetType SingleTarget -ForwardingTarget user2@contoso.com
```

若要同时拨打 user3 的所有委托，请使用 Set-CsUserCallingSettings cmdlet，如以下示例所示：

```PowerShell
Set-CsUserCallingSettings -Identity user3@contoso.com -IsForwardingEnabled $true -ForwardingType Simultaneous -ForwardingTargetType MyDelegates
```

以下示例使用 Set-CsUserCallingSettings cmdlet 配置 user4 的呼叫组，其中 user5 和 user6 作为成员。 对组成员的所有调用均按定义顺序转发：

```PowerShell
$cgm = @("user5@contoso.com","user6@contoso.com")

Set-CsUserCallingSettings -Identity user4@contoso.com -CallGroupOrder InOrder -CallGroupTargets $cgm

Set-CsUserCallingSettings -Identity user4@contoso.com -IsForwardingEnabled $true -ForwardingType Immediate -ForwardingTargetType Group
```

有关更多示例，请参阅 [Set-CsUserCallingSettings](/powershell/module/teams/get-csusercallingsettings)。

### <a name="add-a-calling-delegate-for-a-user"></a>为用户添加调用委托

若要将 user2 添加为具有所有允许权限的 user1 的委托，请使用 New-CsUserCallingDelegate cmdlet，如以下示例所示：

```PowerShell
New-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com -MakeCalls $true -ReceiveCalls $true -ManageSettings $true
```

### <a name="change-calling-delegate-permissions"></a>更改调用委托权限

若要更改委托权限（例如不允许 user2 对 user1 发出调用），请使用 Set-CsUserCallingDelegate cmdlet，如以下示例所示：

```PowerShell
Set-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com -MakeCalls $false
```

### <a name="remove-a-calling-delegate-for-a-user"></a>删除用户的呼叫委托

若要删除 user2 作为 user1 的委托，请使用 Remove-CsUserCallingDelegate cmdlet，如以下示例所示：

```PowerShell
Remove-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com
```

## <a name="additional-notes"></a>其他说明

- 从未由用户或租户管理员修改过呼叫应答规则的用户的默认行为是，未应答的呼叫将在 30 秒后转发到语音邮件。 在团队管理员中心或 Teams PowerShell 中为用户显示的设置会将未响应的目标显示为“无”，延迟为 20 秒。

## <a name="related-topics"></a>相关主题

- [Get-CsUserCallingSettings](/powershell/module/teams/get-csusercallingsettings)
- [Set-CsUserCallingSettings](/powershell/module/teams/set-csusercallingsettings)
- [New-CsUserCallingDelegate](/powershell/module/teams/new-csusercallingdelegate)
- [Set-CsUserCallingDelegate](/powershell/module/teams/set-csusercallingdelegate)
- [Remove-CsUserCallingDelegate](/powershell/module/teams/remove-csusercallingdelegate)
