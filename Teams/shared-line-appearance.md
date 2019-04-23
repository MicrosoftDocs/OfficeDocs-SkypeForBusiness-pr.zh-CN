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
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 共享的行外观允许用户选择代理人应答或处理代表其拨打的呼叫。
ms.openlocfilehash: d16fe4b3241e814609999d8068ee47743bfca516
ms.sourcegitcommit: 920a7dbdc2a0ede94d0a4bd573c01a1ccd838b7e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "31993537"
---
# <a name="shared-line-appearance-in-microsoft-teams"></a>Microsoft Teams 中的共享线路外观

共享的行外观是允许用户选择代理人应答或处理代表其拨打的呼叫委派功能的一部分。 此功能很有用，如果用户具有行政助理定期处理用户的呼叫。 在上下文中共享的行外观，管理器是某人人员授予要发起或接收呼叫代表自己的委托和代理人可以发起和接收代表别人呼叫。

> [!IMPORTANT]
> 此功能才可用在仅团队部署模式下。 团队部署模式的详细信息，请参阅[了解 Microsoft 团队和 Skype 的业务共存及互操作性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

## <a name="license-required"></a>所需的许可证

用户必须是企业语音用户成为代理人或设置委派和允许其他人发起或接收代表其拨打的呼叫。

同时将经理和代理人必须是启用的企业语音。 共享的行体验一部分委派，而且不需要其他许可证。 有关许可模型的其他详细信息，请参阅[Office 365 许可的 Microsoft 团队](office-365-licensing.md)。

## <a name="configuring-delegation-and-shared-line-appearance"></a>配置委派和共享的行外观

委派和共享的行外观是用户驱动的功能： 没有管理员设置配置。 有关如何使用该功能的信息，请参阅[共享与代理人的电话线路](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)

租户管理员应启用此功能**TeamsCallingPolicy AllowDelegation**设置，以便通过委派。

## <a name="shared-line-appearance-feature-availability"></a>共享行外观功能可用性

共享的行外观是当前支持以下应用程序和设备。

| 功能 | 团队桌面 | 团队 Mac 应用程序 | 工作组 Web 应用程序 （边缘） |团队移动 iOS/Android 应用程序 | 团队 IP 电话 |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|
| 设置委派 | 是  | 是  | 是 | 否 | 否 |
| 接收代表另一个呼叫 | 是  | 是  | 是  | 是  | 是 |
| 呼叫代表另一个电话号码 | 是  | 是  | 是  | 是  | 是 |
| 代表其他呼叫团队用户 | 是  | 是  | 是  | 是  | 是 |
| 查看共享的行的管理视图 | 是  | 是  | 是 | 否 | 否 |
| 请参阅经理的呼叫活动的管理视图 | 是  | 是  | 是 | 否 | 否 |
| 查看代理人的管理器视图 | 是  | 是  | 是 | 否 | 否 |
| 管理员或管理器可以保持或恢复 | 是  | 是  | 是 | 否 | 否 |

## <a name="limitations"></a>限制

管理员可以添加最多 25 代理人，代理人可以有最多 25 个经理。 可在租户中创建的委派关系的数量没有限制。 
 
如果代理者和代理人不在相同的地理位置，则由要允许呼叫者 ID 显示从不同地理位置的委派 （代表的） 呼叫的 PSTN 提供程序。 
 
## <a name="more-information"></a>更多信息

[与代理人共享电话线路](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)
