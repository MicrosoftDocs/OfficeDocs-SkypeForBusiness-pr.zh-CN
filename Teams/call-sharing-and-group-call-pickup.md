---
title: 呼叫共享和组内呼叫应答
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 02/19/2019
ms.reviewer: jenstr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.users.voice.groupcallpickup.tooltip
- ms.teamsadmincenter.users.voice.callorderanddelay.tooltip
- Phone System
- seo-marvel-mar2020
description: Microsoft Teams 中的呼叫共享和组呼叫取件允许用户与同事共享传入呼叫，以便在用户不可用时捕获呼叫。
ms.openlocfilehash: 420378ce6d75523bf51b18c17e733d13a76ad877
ms.sourcegitcommit: f0e2a5928e9b959daf45202b9f256f65c2087195
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/20/2022
ms.locfileid: "68613844"
---
# <a name="call-sharing-and-group-call-pickup"></a>呼叫共享和组内呼叫应答

Microsoft Teams 的呼叫共享和组呼叫取件功能允许用户与同事共享其传入呼叫，以便同事可以接听用户不可用时发生的呼叫。

与其他形式的呼叫共享相比，组呼叫接机对收件人的干扰较小，因为用户可以配置想要如何收到传入共享呼叫的通知，并且他们可以决定是否应答。 呼叫组的成员收到传入呼叫通知的顺序可以指定为同时或按顺序 (，) 有 5 个或更少的成员。

> [!IMPORTANT]
> 用户、呼叫组所有者和呼叫组成员必须处于仅 Teams 部署模式。 有关 Teams 部署模式的更多详细信息，请参阅[了解 Microsoft Teams 并Skype for Business共存和互操作性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)。

## <a name="license-required"></a>所需的许可证

必须为用户分配Microsoft Teams 电话系统许可证才能设置和使用呼叫共享和组呼叫取件。 有关许可模型的其他详细信息，请参阅 [电话系统](/MicrosoftTeams/here-s-what-you-get-with-phone-system)获取的内容。

## <a name="limitations"></a>限制

用户只能是一个呼叫组的所有者。 每个配置的呼叫组最多可以有 25 个用户或 32，768 个字符。 用户最多可以是 25 个呼叫组的成员。

请注意，移动设备仅在设置横幅和铃声时才会收到通知。

## <a name="enable-the-use-of-group-call-pickup"></a>启用组呼叫取件的使用

通过为用户配置 **TeamsCallingPolicy AllowCallGroups** 设置来启用呼叫组。 可以使用 Teams 管理中心或 PowerShell。 启用后，用户可以在 Teams 客户端中配置其呼叫组。 

重要提示：为用户关闭呼叫组时，必须清理 Teams 管理中心中用户的呼叫组关系，以避免呼叫路由不正确。 

## <a name="use-teams-admin-center"></a>使用 Teams 管理中心

若要使用 Teams 管理中心为用户配置组呼叫取件，请参阅 [为用户配置呼叫设置](/MicrosoftTeams/user-call-settings)。

## <a name="use-powershell"></a>使用 PowerShell

若要为用户配置呼叫组，请使用以下 Teams PowerShell 模块 cmdlet：

- [Set-CsUserCallingSettings](/powershell/module/teams/set-csusercallingsettings)

- [Get-CsUserCallingSettings](/powershell/module/teams/get-csusercallingsettings)

### <a name="examples"></a>示例

以下示例使用成员 user2@contoso.com 和 user3@contoso.com 创建 user1@contoso.com 的调用组，并设置 user1@contoso.com 的呼叫组的即时调用转发：

```powershell
$cgm = @("sip:user2@contoso.com","sip:user3@contoso.com")
Set-CsUserCallingSettings -Identity user1@contoso.com -CallGroupOrder InOrder -CallGroupTargets $cgm
Set-CsUserCallingSettings -Identity user1@contoso.com -IsForwardingEnabled $true -ForwardingType Immediate -ForwardingTargetType Group
```

下一个示例演示如何更新 user1@contoso.com 的调用组以添加 user5@contoso.com，并删除 user6@contoso.com：

```powershell
$ucs = Get-CsUserCallingSettings -Identity user1@contoso.com
$cgt = {$ucs.CallGroupTargets}.Invoke()
$cgt.Add("sip:user5@contoso.com")
$cgt.Remove("sip:user6@contoso.com")
Set-CsUserCallingSettings -Identity user1@contoso.com -CallGroupOrder $ucs.CallGroupOrder -CallGroupTargets $cgt
```

## <a name="more-information"></a>更多信息

[Teams 中的呼叫转接和同时响铃](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)

[Teams 调用策略](/MicrosoftTeams/teams-calling-policy)

[New-CsTeamsCallingPolicy](/powershell/module/skype/new-csteamscallingpolicy)

[Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)
