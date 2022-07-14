---
title: 呼叫共享和组内呼叫应答
author: CarolynRowe
ms.author: crowe
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
description: 呼叫共享和组呼叫取件允许用户与同事共享传入呼叫，以便在用户不可用时捕获呼叫。
ms.openlocfilehash: 70b1be389309d52b01852e575d08093ef7095a04
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/14/2022
ms.locfileid: "66789947"
---
# <a name="call-sharing-and-group-call-pickup-in-microsoft-teams"></a>Microsoft Teams 中的呼叫共享和组内呼叫应答

Microsoft Teams 的呼叫共享和组呼叫取件功能允许用户与同事共享其传入呼叫，以便同事可以接听用户不可用时发生的呼叫。

与其他形式的呼叫共享 (（例如呼叫转接或同时拨打) ）相比，组呼叫接机对收件人的干扰较小，因为用户可以通过音频和视觉 (通知、仅视觉对象或 Teams 应用) 中的横幅来配置其接收共享呼叫 (通知的方式，并且他们可以决定是否应答。

若要与他人共享呼叫，用户将创建一个呼叫组，并添加要与之共享呼叫的用户。 然后，他们选择同时响铃或前进设置。 有关详细信息，请参阅 [Teams 中的呼叫转接和同时响铃](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) 。 请注意，移动设备仅在设置横幅和铃声时才会收到通知。

> [!IMPORTANT]
> 用户、呼叫组所有者和呼叫组成员必须处于仅 Teams 部署模式。 有关 Teams 部署模式的更多详细信息，请参阅[了解 Microsoft Teams 并Skype for Business共存和互操作性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)。

## <a name="license-required"></a>所需的许可证

必须为用户分配Microsoft Teams 电话系统许可证才能设置和使用呼叫共享和组呼叫取件。 有关许可模型的其他详细信息，请参阅 [电话系统](/MicrosoftTeams/here-s-what-you-get-with-phone-system)获取的内容。

## <a name="configure-group-call-pickup"></a>配置组呼叫取件

若要设置组呼叫取件，用户首先配置一个呼叫组 (这与安全组或 Microsoft 365 组) 不同，然后添加要与之共享呼叫的用户。 然后，他们选择同时响铃或向前调用设置。 有关详细信息和分步过程，请参阅 [Teams 中的呼叫转接和同时响铃](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)。

呼叫组创建和通知首选项是用户驱动的功能;管理员不必为其用户配置这些功能。 无法从安全组或 Microsoft 365 组创建呼叫组;必须在 Teams 中创建它们。

管理员应通过用户的 **TeamsCallingPolicy AllowCallGroups** 设置启用呼叫组。 管理员还可以通过 Teams 管理员 门户启用此功能。  此外，配置的用户还可以通过客户端直接配置其呼叫组。 管理员或最终用户不能互相阻止配置，但 Teams 管理员门户和 Teams 客户端应在这两个位置准确显示此关系。 

重要提示：当管理员在用户 (启用呼叫组并) 配置呼叫组关系后关闭呼叫组时，管理员必须清理 Teams 管理中心中用户的呼叫组关系，以避免呼叫路由不正确。 

## <a name="limitations"></a>限制

每个配置的呼叫组最多可以有 25 个用户或 32，768 个字符。 

## <a name="more-information"></a>更多信息

[Teams 中的呼叫转接和同时响铃](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)
