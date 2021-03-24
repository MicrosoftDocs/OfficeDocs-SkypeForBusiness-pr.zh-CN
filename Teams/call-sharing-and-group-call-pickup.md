---
title: 呼叫共享和组内呼叫应答
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 02/19/2019
ms.reviewer: srividhc
ms.topic: article
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
- ms.teamsadmincenter.users.voice.groupcallpickup.tooltip
- ms.teamsadmincenter.users.voice.callorderanddelay.tooltip
- Phone System
- seo-marvel-mar2020
description: 呼叫共享和群组呼叫取件允许用户与同事共享传入呼叫，以便当用户不可用时可以捕获呼叫。
ms.openlocfilehash: 1ec3c389bf2eb69f30e13ebbba6c7d5d1d5fe38c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102788"
---
# <a name="call-sharing-and-group-call-pickup-in-microsoft-teams"></a>Microsoft Teams 中的呼叫共享和组内呼叫应答

Microsoft Teams 的呼叫共享和群组呼叫取件功能允许用户与同事共享其传入呼叫，以便同事可以应答在用户不可用时发生的呼叫。

与其他形式的呼叫共享 (（如呼叫转发或同时拨打) ）相比，组呼叫取件对收件人的干扰性较小，因为用户可以配置通过音频和视频通知、仅可视通知或 Teams 应用) 中的横幅来通知传入共享呼叫 (的方式，并且他们可决定是否接听。

若要与其他人共享呼叫，用户创建一个呼叫组，并添加要与用户共享其呼叫的用户。 然后，选择同时响铃或向前设置。 有关详细信息 [，请参阅 Teams 中的呼叫转发和](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) 同时拨打。 请注意，只有当移动设备设置为横幅和铃声时，它们才收到通知。

> [!IMPORTANT]
> 用户、呼叫组所有者和呼叫组的成员必须进入"仅 Teams"部署模式。 有关 Teams 部署模式的更多详细信息，请参阅了解 Microsoft Teams 和 [Skype for Business 共存和互操作性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

## <a name="license-required"></a>需要许可证

必须允许用户企业语音设置和使用呼叫共享和群组呼叫取件。 有关许可模型的其他详细信息，请参阅 Microsoft [Teams 服务说明](/office365/servicedescriptions/teams-service-description)。

## <a name="configure-group-call-pickup"></a>配置群组呼叫取件

要设置群组呼叫取件，用户首先配置呼叫组 (这与安全组或 Microsoft 365 组) 不同，然后添加要与用户共享其呼叫的用户。 然后，选择同时拨打或呼叫转发设置。 有关详细信息和分步过程，请参阅 Teams 中的呼叫 [转发和同时拨打](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)。

呼叫组创建和通知首选项是用户驱动的功能;管理员不需要为用户配置这些功能。 无法从安全组或 Microsoft 365 组创建呼叫组;必须在 Teams 中创建它们。

管理员应该通过 **TeamsCallingPolicy AllowCallGroups 设置为用户启用** 呼叫组。 管理员还可通过 Teams 管理门户启用此功能。  此外，配置的用户还可以直接通过客户端配置其呼叫组。 管理员或最终用户无法相互阻止配置，但 Teams 管理门户和 Teams 客户端应在两处准确显示此关系。 

重要提示：当管理员为 (用户关闭呼叫组且呼叫组关系已配置) 时，管理员必须清理 Teams 管理中心中用户的呼叫组关系以避免不正确的呼叫路由。 

## <a name="limitations"></a>限制

一个租户最多可以包含 32，768 个呼叫组。 每个呼叫组中最多可以有 25 个用户。 

## <a name="more-information"></a>更多信息

[Teams 中的呼叫转发和同时拨打](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)