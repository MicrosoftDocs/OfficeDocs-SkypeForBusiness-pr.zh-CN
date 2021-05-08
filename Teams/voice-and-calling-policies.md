---
title: 管理语音和呼叫策略Teams
author: karlistites
ms.author: kastites
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: 了解Teams和呼叫策略。
audience: admin
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9056c9b81fcda9c0e7408c63b4af00c1aabbffd0
ms.sourcegitcommit: d62e6cefceebe481eb207c59872f1aa67f0fc528
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2021
ms.locfileid: "50460582"
---
# <a name="manage-voice-and-calling-policies-in-microsoft-teams"></a>管理语音和呼叫策略Microsoft Teams

语音和呼叫策略用于控制语音和Microsoft Teams。

## <a name="emergency-calling-policies"></a>紧急呼叫策略

使用 [紧急呼叫策略](manage-emergency-calling-policies.md) 来配置当贵组织的用户进行紧急呼叫时会发生什么情况。 这些策略在管理中心Teams管理，或者使用Windows PowerShell。

![紧急呼叫策略的屏幕截图。](media/emergency-calling-policy2.png)

## <a name="emergency-call-routing-policies"></a>紧急呼叫路由策略

如果组织已部署 **电话系统** 路由，可以使用紧急呼叫路由策略来确定紧急呼叫 [](manage-emergency-call-routing-policies.md)的路由位置、是否启用了增强型紧急服务，以及用于紧急服务的电话号码。 这些策略使用 PowerShell 或管理中心Microsoft Teams管理。

![紧急呼叫路由策略的屏幕截图。](media/emergency-call-routing-policy.png)

## <a name="caller-id-policies"></a>调用方 ID 策略

[来电显示](caller-id-policies.md) 策略用于更改或阻止来电显示。

![调用方 ID 策略的屏幕截图。](media/caller-id-policy.png)

## <a name="voice-routing-policies"></a>语音路由策略

语音 [路由策略](manage-voice-routing-policies.md) 是 PSTN 公用电话交换网 (PSTN) 容器。 如果组织已部署直接路由 **，电话系统策略**。 语音路由策略可以使用 PowerShell 或 Teams管理中心进行管理。

![语音路由策略的屏幕截图。](media/voice-routing-policy.png)

## <a name="calling-policies"></a>通话策略

[呼叫策略](teams-calling-policy.md) 控制哪些呼叫和呼叫转发功能可供用户使用，包括用户是否可以进行私人呼叫、向呼叫组发送呼叫以及将呼叫路由到语音邮件。

![调用策略的屏幕截图。](media/calling-policy.png)

## <a name="call-park-and-retrieve-policies"></a>呼叫停放和检索策略

[呼叫暂停和检索](call-park-and-retrieve.md) 允许用户将其他用户置于保持状态，使同一用户或其他人能够继续呼叫。

![呼叫停放和检索策略的屏幕截图。](media/call-park-policy.png)

## <a name="create-and-manage-dial-plans"></a>创建并管理拨号计划

[拨号计划](create-and-manage-dial-plans.md) 转换拨入的电话号码进行呼叫授权和路由。 可以通过 PowerShell 或管理中心创建和管理Microsoft Teams套餐。

![拨号计划的屏幕截图。](media/dial-plans.png)

## <a name="related-topics"></a>相关主题

* [管理紧急呼叫策略Microsoft Teams](manage-emergency-calling-policies.md)
* [管理紧急呼叫路由策略](manage-emergency-call-routing-policies.md)
* [在 Microsoft Teams 中管理呼叫方 ID 策略](caller-id-policies.md)
* [管理语音路由策略](manage-voice-routing-policies.md)
* [Microsoft Teams 中的呼叫策略](teams-calling-policy.md)
* [Microsoft Teams 中的呼叫寄存和取回](call-park-and-retrieve.md)
* [创建并管理拨号计划](create-and-manage-dial-plans.md)
* [使用Teams管理策略](manage-teams-with-policies.md)
