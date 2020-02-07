---
title: Microsoft Teams 中的共享线路外观
ms.author: lolaj
author: LolaJacobsen
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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
- ms.teamsadmincenter.users.voice.calldelegation.tooltip
description: 共享行的外观使用户可以选择代表代表他们应答或处理呼叫的代理人。
ms.openlocfilehash: bb6728de67d1bf29a5e00ed9b62d8957391dd8ba
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837962"
---
# <a name="shared-line-appearance-in-microsoft-teams"></a>Microsoft Teams 中的共享线路外观

共享行的外观是委派功能的一部分，允许用户选择代理人代表他们应答或处理呼叫。 如果用户有一个管理助理负责定期处理用户的通话，此功能将很有帮助。 在共享行外观的上下文中，经理是指授权代理人代表他们拨打或接听呼叫的人员，而代理人可以代表其他人拨打和接听电话。

> [!IMPORTANT]
> 此功能仅适用于 "仅限团队" 部署模式。 有关团队部署模式的更多详细信息，请参阅[了解 Microsoft 团队和 Skype For business 共存和互操作性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

## <a name="license-required"></a>需要许可证

用户必须使用具有 PSTN 连接的电话系统（呼叫计划许可证或直接路由 OnlineVoiceRoutingPolicy）作为代理人，或者设置委派并允许其他人代表他们进行或接收呼叫。

管理者和代理人都需要具有 PSTN 连接的电话系统（呼叫计划许可证或直接路由 OnlineVoiceRoutingPolicy）。 共享线路体验是委派的一部分，并包含在电话系统中。 有关许可模型的其他详细信息，请参阅[Microsoft 团队的 Office 365 授权](office-365-licensing.md)。

## <a name="configuring-delegation-and-shared-line-appearance"></a>配置委派和共享行的外观

委派和共享行的外观是用户驱动的功能：没有要配置的管理员设置。 有关如何使用该功能的信息，请参阅[与代理人共享电话线路](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)

租户管理员可通过**TeamsCallingPolicy AllowDelegation**设置或通过团队管理门户启用委派，此功能将起作用。 

租户管理员还可以为团队管理中心中的用户配置委派关系。 此外，最终用户还可以直接在团队中配置其委派关系。 租户管理员或用户无法彼此阻止配置，但团队管理中心和团队客户应在这两个位置中准确显示此关系。 

> [!IMPORTANT]
> 当租户管理员为用户关闭委派时（在已启用）时，他们还需要清理团队管理中心中该用户的委派关系，以避免不正确的呼叫路由。

## <a name="shared-line-appearance-feature-availability"></a>共享行外观功能的可用性

以下应用和设备当前支持共享行的外观。

| 能 | 团队桌面版 | 团队 Mac 应用 | 团队 Web App （Edge） |团队移动 iOS/Android 应用程序 | 团队 IP 电话 |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|
| 设置委派 | 必需 | 是  | 是 | 否 | 否 |
| 代表他人接听电话 | 必需 | 是  | 是  | 是  | 是 |
| 代表另一个电话号码拨打电话 | 必需 | 是  | 是  | 是  | 是 |
| 代表另一个团队用户调用团队用户 | 必需 | 是  | 是  | 是  | 是 |
| 查看共享行的管理员视图 | 必需 | 是  | 是 | 否 | 否 |
| 查看经理的通话活动的管理员视图 | 必需 | 是  | 是 | 否 | 否 |
| 查看代理人的管理者视图 | 必需 | 是  | 是 | 否 | 否 |
| 管理员或管理者可以保留或继续 | 必需 | 是  | 是 | 否 | 否 |

## <a name="limitations"></a>优缺点

经理最多可以添加25位代理人，并且代理人最多可以有25名经理。 对于可在租户中创建的委派关系的数量没有限制。 
 
如果委托人进行通话和代理人不在同一地理位置，则由 PSTN 提供商允许呼叫者 ID 显示来自不同地理位置的委派（代表）呼叫。 
 
## <a name="more-information"></a>更多信息

[与代理人共享电话线路](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)
