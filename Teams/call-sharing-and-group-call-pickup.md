---
title: Microsoft Teams 中的呼叫共享和组内呼叫应答
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.date: 02/19/2019
ms.reviewer: srividhc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 呼叫共享和群组通话分拣允许用户与同事共享传入呼叫, 以便可以在用户不可用时捕获呼叫。
ms.openlocfilehash: caf472f9829f9cf68ccb87a5081bc0b5cfae28f8
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36237159"
---
# <a name="call-sharing-and-group-call-pickup-in-microsoft-teams"></a>Microsoft Teams 中的呼叫共享和组内呼叫应答

Microsoft 团队的呼叫共享和组呼叫功能允许用户与同事共享传入呼叫, 以便同事可以接听在用户不可用时出现的呼叫。

组呼叫对收件人的干扰比其他呼叫共享形式 (如呼叫转接或同时拨打) 的干扰更少, 因为用户可以配置他们希望如何收到传入共享呼叫的通知 (通过音频和视觉通知, 仅限 visual)"团队" 应用中的 "标题" 或 "横幅", 他们可以决定是否应答。

若要与其他人共享呼叫, 用户将创建呼叫组, 并添加他们想要与之共享其通话的用户。 然后选择 "同时拨打" 或 "转发" 设置。 有关详细信息, 请参阅有关[团队的呼叫转接和同时拨打](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)的详细信息。

> [!IMPORTANT]
> 用户、呼叫组所有者和呼叫组成员必须位于 "仅限团队" 部署模式。 有关团队部署模式的更多详细信息, 请参阅[了解 Microsoft 团队和 Skype For business 共存和互操作性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

## <a name="license-required"></a>需要许可证

用户必须是启用企业语音才能设置和使用呼叫共享和组呼叫装货。 有关许可模型的其他详细信息, 请参阅[Microsoft 团队的 Office 365 授权](office-365-licensing.md)。

## <a name="configure-group-call-pickup"></a>配置组呼叫装货

若要设置组呼叫装货, 用户首先配置呼叫组 (这与安全组或 Office 365 组不同), 然后添加他们想要与之共享呼叫的用户。 然后, 选择 "同时拨打" 或 "呼叫转接" 设置。 有关详细信息和分步过程, 请参阅[团队中的呼叫转接和同时拨打](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)。

呼叫组创建和通知首选项是用户驱动的功能;管理员不必为其用户配置这些功能。 无法从安全组或 Office 365 组创建呼叫组;它们必须在团队中创建。

管理员应通过用户的**TeamsCallingPolicy AllowCallGroups**设置启用呼叫组。 管理员还可以通过团队管理员门户启用此操作。  此外, 已配置的用户还可以直接通过客户端配置其呼叫组。 管理员或最终用户不能互相阻止配置, 但团队管理员门户和团队客户应在这两个位置准确地显示这种关系。 

重要提示: 当管理员为用户关闭呼叫组时 (已启用和呼叫组关系已配置), 管理员必须清理团队管理中心中的用户的呼叫组关系, 以避免呼叫路由错误。 

## <a name="limitations"></a>优缺点

一个租户最多可以包含32768个呼叫组。 每个呼叫组中最多只能有25个用户。 

## <a name="more-information"></a>详细信息

[团队中的呼叫转接和同时拨打](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)
