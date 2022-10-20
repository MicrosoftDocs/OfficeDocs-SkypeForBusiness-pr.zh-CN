---
title: Microsoft Teams 中的共享线路外观
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 02/19/2019
ms.reviewer: jenstr
ms.topic: conceptual
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
- Phone System
- ms.teamsadmincenter.users.voice.calldelegation.tooltip
- seo-marvel-apr2020
description: 了解 Microsoft Teams 中的“共享行外观”功能。
ms.openlocfilehash: 7e3259e948e5a3443d5959eef693416ca3d754ca
ms.sourcegitcommit: f0e2a5928e9b959daf45202b9f256f65c2087195
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/20/2022
ms.locfileid: "68614094"
---
# <a name="shared-line-appearance-in-microsoft-teams"></a>Microsoft Teams 中的共享线路外观

共享行外观允许用户选择代表其应答或处理呼叫的委托。 如果用户具有定期处理用户呼叫的管理助理，则此功能非常有用。 在共享行外观的上下文中，经理是授权代理人代表其拨打或接听电话的人。 委托可以代表委派人发出或接听呼叫。

> [!IMPORTANT]
> 此功能仅在仅 Teams 部署模式下可用。 有关 Teams 部署模式的更多详细信息，请参阅[了解 Microsoft Teams 并Skype for Business共存和互操作性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

## <a name="license-required"></a>所需的许可证

经理和代理人都必须拥有具有 PSTN 连接的电话系统许可证 (呼叫计划、操作员连接或直接路由) 。 共享线路体验是委派的一部分，包含在电话系统中。 有关许可的详细信息，请参阅 [Microsoft Teams 服务说明](/office365/servicedescriptions/teams-service-description)。

## <a name="shared-line-appearance-feature-availability"></a>共享行外观功能可用性

以下应用和设备目前支持共享行外观。

| 功能 | Teams 桌面 | Teams Mac 应用 | Teams Web App (Edge)  |Teams 移动 iOS/Android 应用 | Teams IP 电话 |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|
| 设置委派 | 是 | 是 | 是 | 否 | 是 |
| 代表另一个接听呼叫 | 是 | 是 | 是 | 是 | 是 |
| 代表另一个电话号码呼叫电话号码 | 是 | 是 | 是 | 是 | 是 |
| 代表另一个用户调用 Teams 用户 | 是 | 是 | 是 | 是 | 是 |
| 查看共享行的委托视图 | 是 | 是 | 是 | 否 | 是 |
| 查看经理调用活动的委托视图 | 是 | 是 | 是 | 否 | 是 |
| 查看委托的管理器视图 | 是 | 是 | 是 | 否 | 是 |
| 委托或经理可以保留或恢复 | 是 | 是 | 是 | 否 | 是 |

## <a name="limitations"></a>限制

经理最多可以有 25 名代表，而代理人最多可以有 25 名经理。 可在租户中创建的委派关系数没有限制。 
 
如果委托人和委托不在同一地理位置，则 PSTN 提供程序必须允许调用方 ID 从其他地理位置显示委托呼叫。 

不允许循环委派配置。 如果委派的用户之间也有代表团，他们只能看到其委派，而不能看到初始委派。

## <a name="enable-delegation-and-shared-line-appearance"></a>启用委派和共享行外观

使用 **TeamsCallingPolicy AllowDelegation** 设置启用委派。 可以使用 Teams 管理中心或 Teamms PowerShell。 

启用后，最终用户可以直接在 Teams 中配置其委派关系。 

> [!IMPORTANT]
> 为用户关闭委派时，还需要在 Teams 管理中心为该用户清理委派关系，以避免呼叫路由不正确。

## <a name="use-teams-admin-center"></a>使用 Teams 管理中心

若要使用 Teams 管理中心配置委派和共享行外观，请参阅 [为用户配置呼叫设置](/MicrosoftTeams/user-call-settings)。

## <a name="use-powershell"></a>使用 PowerShell

若要使用 Teams PowerShell 配置委派和共享行外观，请使用以下 cmdlet：

- [New-CsUserCallingDelegate](/powershell/module/teams/new-csusercallingdelegate)

- [Set-CsUserCallingDelegate](/powershell/module/teams/set-csusercallingdelegate)

- [Remove-CsUserCallingDelegate](/powershell/module/teams/remove-csusercallingdelegate)

### <a name="examples"></a>示例

在以下示例中，user2@contoso.com 添加为具有代表 user1 进行和接收呼叫的权限的 user1@contoso.com 委托，以及更改其他委托的设置：

```powershell
New-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com -MakeCalls $true -ReceiveCalls $true -ManageSettings $true
```

在下一个示例中，不再允许委托 user2@contoso.com 代表 user1 进行呼叫：

```powershell
Set-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com -MakeCalls $false
```

在下一个示例中，user2@contoso.com 作为 user1@contoso.com 的委托删除：

```powershell
Remove-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com
```
 
## <a name="more-information"></a>更多信息

[与委托共享电话线](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)

[Teams 调用策略](/MicrosoftTeams/teams-calling-policy)

[New-CsTeamsCallingPolicy](/powershell/module/skype/new-csteamscallingpolicy)

[Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)
