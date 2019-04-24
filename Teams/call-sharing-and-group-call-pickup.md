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
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 调用共享并组呼叫应答让用户与同事共享传入呼叫，以便用户不可用时，可以捕获呼叫。
ms.openlocfilehash: e822d06e48f3d7df548f0fd0d04645e7e9328598
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32211820"
---
# <a name="call-sharing-and-group-call-pickup-in-microsoft-teams"></a>Microsoft Teams 中的呼叫共享和组内呼叫应答

呼叫共享和组呼叫 Microsoft 团队让的用户共享其传入呼叫与同事，以便同事可以应答，当用户不可用时进行的呼叫的分拣的功能。

组呼叫应答是呼叫的对中断较小收件人比其他形式的共享 （如呼叫转接或同时响铃），因为用户可配置他们希望如何通知的 （通过音频和可视通知，仅 visual 共享传入呼叫或横幅团队应用程序中），并且他们可以决定是否要应答呼叫。

与其他人共享呼叫，用户的呼叫组并将添加他们希望共享具有其呼叫的用户。 然后他们选择同时响铃，或转发设置。 有关详细信息，请参阅[呼叫转接和同时拨打团队](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)。

> [!IMPORTANT]
> 用户、 呼叫组所有者和呼叫组的成员必须在仅团队部署模式下。 团队部署模式的详细信息，请参阅[了解 Microsoft 团队和 Skype 的业务共存及互操作性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

## <a name="license-required"></a>所需的许可证

用户必须启用设置和使用呼叫共享和组呼叫应答的企业语音。 有关许可模型的其他详细信息，请参阅[Office 365 许可的 Microsoft 团队](office-365-licensing.md)。

## <a name="configure-group-call-pickup"></a>配置组呼叫应答

若要设置组的呼叫应答，用户首次配置 （这是不相同为安全组或 Office 365 组） 的呼叫组，，然后添加他们希望共享具有其呼叫的用户。 然后，他们选择同时响铃，或呼叫转接设置。 有关详细信息和分步过程，请参阅[呼叫转接和同时拨打团队](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)。

呼叫组的创建和通知首选项是用户驱动的功能;管理员不需要配置这些功能的用户。 无法从安全组或 Office 365 组; 创建呼叫组必须在工作组中创建它们。

管理员应启用通过**TeamsCallingPolicy AllowCallGroups**设置用户的呼叫组。 管理员可以仅控制此用户是否可以配置呼叫组。 一旦位设置为 true，则管理员无法防止其他用户配置和添加他们选择的呼叫组用户。

## <a name="limitations"></a>限制

租户可以包含最多个 32768 呼叫组。 可以有 5 个用户每个呼叫组中的最大值。 

## <a name="more-information"></a>更多信息

[呼叫转接和同时响铃团队中](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)