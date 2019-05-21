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
- Teams_ITAdmin_Help
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 共享行的外观使用户可以选择代表代表他们应答或处理呼叫的代理人。
ms.openlocfilehash: 619e011e1af5a765bc86ca6bd68134dc5ab1e9fa
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34298652"
---
# <a name="shared-line-appearance-in-microsoft-teams"></a>Microsoft Teams 中的共享线路外观

共享行的外观是委派功能的一部分, 允许用户选择代理人代表他们应答或处理呼叫。 如果用户有一个管理助理负责定期处理用户的通话, 此功能将很有帮助。 在共享行外观的上下文中, 经理是指授权代理人代表他们拨打或接听呼叫的人员, 而代理人可以代表其他人拨打和接听电话。

> [!IMPORTANT]
> 此功能仅适用于 "仅限团队" 部署模式。 有关团队部署模式的更多详细信息, 请参阅[了解 Microsoft 团队和 Skype For business 共存和互操作性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

## <a name="license-required"></a>需要许可证

用户必须是企业语音用户才能成为代理人或设置委派, 并允许其他人代表他们进行或接收呼叫。

经理和代理人都需要具备企业语音功能。 共享行体验是委派的一部分, 不需要额外许可证。 有关许可模型的其他详细信息, 请参阅[Microsoft 团队的 Office 365 授权](office-365-licensing.md)。

## <a name="configuring-delegation-and-shared-line-appearance"></a>配置委派和共享行的外观

委派和共享行的外观是用户驱动的功能: 没有要配置的管理员设置。 有关如何使用该功能的信息, 请参阅[与代理人共享电话线路](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)

租户管理员应通过**TeamsCallingPolicy AllowDelegation**设置启用委派, 此功能才能正常工作。

## <a name="shared-line-appearance-feature-availability"></a>共享行外观功能的可用性

以下应用和设备当前支持共享行的外观。

| 能 | 团队桌面版 | 团队 Mac 应用 | 团队 Web App (Edge) |团队移动 iOS/Android 应用程序 | 团队 IP 电话 |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|
| 设置委派 | 是 | 是 | 是 | 否 | 否 |
| 代表他人接听电话 | 是 | 是 | 是 | 是 | 是 |
| 代表另一个电话号码拨打电话 | 是 | 是 | 是 | 是 | 是 |
| 代表另一个团队用户调用团队用户 | 是 | 是 | 是 | 是 | 是 |
| 查看共享行的管理员视图 | 是 | 是 | 是 | 否 | 否 |
| 查看经理的通话活动的管理员视图 | 是 | 是 | 是 | 否 | 否 |
| 查看代理人的管理者视图 | 是 | 是 | 是 | 否 | 否 |
| 管理员或管理者可以保留或继续 | 是 | 是 | 是 | 否 | 否 |

## <a name="limitations"></a>优缺点

经理最多可以添加25位代理人, 并且代理人最多可以有25名经理。 对于可在租户中创建的委派关系的数量没有限制。 
 
如果委托人进行通话和代理人不在同一地理位置, 则由 PSTN 提供商允许呼叫者 ID 显示来自不同地理位置的委派 (代表) 呼叫。 
 
## <a name="more-information"></a>详细信息

[与代理人共享电话线路](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)
