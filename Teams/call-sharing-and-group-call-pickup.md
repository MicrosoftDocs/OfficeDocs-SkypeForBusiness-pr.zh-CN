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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.users.voice.groupcallpickup.tooltip
- ms.teamsadmincenter.users.voice.callorderanddelay.tooltip
- Phone System
- seo-marvel-mar2020
description: 呼叫共享和群组呼叫取件允许用户与同事共享传入呼叫，以便当用户不可用时可以捕获呼叫。
ms.openlocfilehash: 7f9e24114d47ff331ad36a653a2bbe0f31fcad08
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/30/2021
ms.locfileid: "60014126"
---
# <a name="call-sharing-and-group-call-pickup-in-microsoft-teams"></a>Microsoft Teams 中的呼叫共享和组内呼叫应答

呼叫共享和群组呼叫取件功能Microsoft Teams允许用户与同事共享其传入呼叫，以便同事可以应答在用户不可用时发生的呼叫。

与其他形式的呼叫共享 (（例如呼叫转发或同时拨打) ）相比，组呼叫取件对收件人的干扰性更低，因为用户可以配置通过 Teams 应用) 中的音频和视频通知、仅可视或横幅来通知传入共享呼叫 (的方式，并且他们可决定是否接听。

若要与其他人共享呼叫，用户创建一个呼叫组并添加要与用户共享其呼叫的用户。 然后，选择同时响铃或向前设置。 有关详细信息[，请参阅呼叫Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)和同时拨打。 请注意，只有当移动设备设置为横幅和铃声时，它们才收到通知。

> [!IMPORTANT]
> 用户、呼叫组所有者和呼叫组的成员必须Teams部署模式。 有关部署模式Teams的详细信息，请参阅了解Microsoft Teams和Skype for Business[共存和互操作性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)。

## <a name="license-required"></a>需要许可证

必须为用户提供一个Microsoft Teams 电话系统许可证才能设置和使用呼叫共享和群组呼叫取件。 有关许可模型的其他详细信息[，请参阅此处](/MicrosoftTeams/here-s-what-you-get-with-phone-system)是使用 电话系统。

## <a name="configure-group-call-pickup"></a>配置群组呼叫取件

要设置组呼叫取件，用户首先配置呼叫组 (这与安全组或 Microsoft 365 组) 不同，然后添加要与用户共享其呼叫的用户。 然后，选择同时拨打或呼叫转发设置。 有关详细信息和分步过程，请参阅呼叫[转发](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)和同时拨打 Teams。

呼叫组创建和通知首选项是用户驱动的功能;管理员不需要为用户配置这些功能。 无法从安全组或安全组创建Microsoft 365组;它们必须在 Teams 中创建。

管理员应该通过 **TeamsCallingPolicy AllowCallGroups 设置为用户** 启用呼叫组。 管理员还可通过管理员门户Teams此功能。  此外，配置的用户还可以直接通过客户端配置其呼叫组。 管理员或最终用户无法相互阻止配置，Teams门户Teams客户端应在两处准确显示此关系。 

重要提示：当管理员为 (用户关闭呼叫组且呼叫组关系已配置) 时，管理员必须清理 Teams 管理中心中的用户的呼叫组关系以避免不正确的呼叫路由。 

## <a name="limitations"></a>限制

每个配置的呼叫组最多可以有 25 个用户或 32，768 个字符。 

## <a name="more-information"></a>更多信息

[呼叫转发和同时拨打Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)
