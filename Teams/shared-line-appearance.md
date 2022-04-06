---
title: Microsoft Teams 中的共享线路外观
ms.author: serdars
author: SerdarSoysal
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
description: 了解如何向用户发送包含其音频会议信息的电子邮件，Microsoft Teams。
ms.openlocfilehash: d47b763b877c49194c26eae05904ea1b7ccee5ec
ms.sourcegitcommit: 2ce3e95401ac06c0370a54862372a94ec6291d01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/05/2022
ms.locfileid: "64642856"
---
# <a name="shared-line-appearance-in-microsoft-teams"></a>Microsoft Teams 中的共享线路外观

共享线路外观是委派功能中的一部分，允许用户选择代理人来代表他们应答或处理呼叫。 如果用户具有定期处理用户呼叫的管理助理，此功能非常有用。 在共享线路外观的上下文中，经理是授权代理人代表他们进行呼叫或接听呼叫的人，代理人可以代表其他人拨打和接听呼叫。

> [!IMPORTANT]
> 此功能仅在仅Teams模式下可用。 有关部署模式Teams的详细信息，请参阅了解Microsoft Teams和Skype for Business[共存和互操作性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

## <a name="license-required"></a>需要许可证

用户必须电话系统 PSTN 连接 (呼叫计划许可证或 Direct Routing OnlineVoiceRoutingPolicy) 才能成为代理人或设置委派，并允许其他人代表他们拨打或接听呼叫。

经理和代理人都需要使用呼叫电话系统或直接路由 OnlineVoiceRoutingPolicy (PSTN 连接) 。 共享线路体验是委派的一部分，包含在电话系统。 有关许可模型的其他详细信息，请参阅Microsoft Teams[说明](/office365/servicedescriptions/teams-service-description)。

## <a name="configuring-delegation-and-shared-line-appearance"></a>配置委派和共享行外观

委派和共享行外观是用户驱动的功能：无需配置管理员设置。 有关如何使用该功能的信息，请参阅 [与代理人共享电话线](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)

租户管理员可以通过 **TeamsCallingPolicy AllowDelegation** 设置或 Teams管理门户启用委派，以便此功能正常工作。 

租户管理员还可以在管理中心为用户配置Teams关系。 此外，最终用户还可以直接在 Teams 中配置其委派关系。 租户管理员或用户无法相互阻止配置，但Teams管理中心和Teams客户端应在两处准确显示此关系。 

> [!IMPORTANT]
> 当租户管理员在用户 (启用) 后关闭其委派时，还需要在 Teams 管理中心中清理该用户的委派关系，以避免不正确的呼叫路由。

## <a name="shared-line-appearance-feature-availability"></a>共享线外观功能可用性

以下应用和设备目前支持共享线外观。

| 功能 | Teams 桌面 | Teams Mac 应用 | Teams Web 应用 (Edge)  |Teams iOS/Android 应用 | Teams IP 电话 |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|
| 设置委派 | 是 | 是 | 是 | 否 | 是 |
| 代表另一个接收呼叫 | 是 | 是 | 是 | 是 | 是 |
| 代表另一个号码呼叫电话号码 | 是 | 是 | 是 | 是 | 是 |
| 代表Teams呼叫用户 | 是 | 是 | 是 | 是 | 是 |
| 查看共享行的委托视图 | 是 | 是 | 是 | 否 | 是 |
| 查看经理呼叫活动的代理人视图 | 是 | 是 | 是 | 否 | 是 |
| 查看代理人的经理视图 | 是 | 是 | 是 | 否 | 是 |
| 代理人或经理可以保留或继续 | 是 | 是 | 是 | 否 | 是 |

## <a name="limitations"></a>限制

经理可添加多达 25 名代理人，代理人最多只能有 25 名经理。 可以在租户中创建的委派关系数没有限制。 
 
如果委派方和代理人不在同一地理位置，则由 PSTN 提供商负责允许呼叫者 ID 代表) 呼叫从委派的 (的不同地理位置显示。 

不允许循环委派配置。 如果委托的用户之间还有委托，他们只能看到其委派，而不是初始委派。
 
## <a name="more-information"></a>更多信息

[与代理人共享电话线](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)
