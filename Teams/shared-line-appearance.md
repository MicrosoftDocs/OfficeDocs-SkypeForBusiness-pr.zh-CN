---
title: Microsoft Teams 中的共享线路外观
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 02/19/2019
ms.reviewer: srividhc
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
description: 了解如何在 Microsoft Teams 中向用户发送包含其音频会议信息的电子邮件。
ms.openlocfilehash: 3646cf27e22f5224dc825c758f757cc04d5804fc
ms.sourcegitcommit: 4d88637f510a78d5709d1213c3e285d83a022014
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/14/2022
ms.locfileid: "66794320"
---
# <a name="shared-line-appearance-in-microsoft-teams"></a>Microsoft Teams 中的共享线路外观

共享行外观是委派功能的一部分，该功能允许用户选择代表其应答或处理呼叫的委托。 如果用户具有定期处理用户呼叫的管理助理，则此功能非常有用。 在共享行外观的上下文中，经理是授权代理人代表其拨打或接听电话的人员，并且代理人可以代表其他人发出和接听电话。

> [!IMPORTANT]
> 此功能仅在仅 Teams 部署模式下可用。 有关 Teams 部署模式的更多详细信息，请参阅[了解 Microsoft Teams 并Skype for Business共存和互操作性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

## <a name="license-required"></a>所需的许可证

用户必须具有具有 PSTN 连接的电话系统 (呼叫计划许可证或直接路由 OnlineVoiceRoutingPolicy) 才能成为代理人或设置委派，并允许其他人代表其拨打或接听呼叫。

经理和委托都需要将具有 PSTN 连接的电话系统 (呼叫计划许可证或直接路由 OnlineVoiceRoutingPolicy) 。 共享线路体验是委派的一部分，包含在电话系统中。 有关许可模型的其他详细信息，请参阅 [Microsoft Teams 服务说明](/office365/servicedescriptions/teams-service-description)。

## <a name="configuring-delegation-and-shared-line-appearance"></a>配置委派和共享行外观

委派和共享行外观是用户驱动的功能：没有要配置的管理员设置。 有关如何使用该功能的信息，请参阅 [与委托共享电话线](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)

租户管理员可以通过 **TeamsCallingPolicy AllowDelegation** 设置或 Teams 管理员 门户启用委派，以便此功能正常工作。 

租户管理员还可以在 Teams 管理中心为用户配置委派关系。 此外，最终用户还可以直接在 Teams 中配置其委派关系。 租户管理员或用户不能互相阻止配置，但 Teams 管理中心和 Teams 客户端应在这两个位置准确显示此关系。 

> [!IMPORTANT]
> 当租户管理员在用户 (启用) 后关闭委派时，他们还需要清理 Teams 管理中心中该用户的委派关系，以避免呼叫路由不正确。

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
 
如果委托人和委托人不在同一地理位置，则由 PSTN 提供程序允许调用方 ID 代表) 调用从其他地理位置显示委托 (。 

不允许循环委派配置。 如果委派的用户之间也有代表团，他们只能看到其委派，而不能看到初始委派。
 
## <a name="more-information"></a>更多信息

[与委托共享电话线](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)
