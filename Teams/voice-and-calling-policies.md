---
title: 在Teams中管理语音和呼叫策略
author: mkbond007
ms.author: mabond
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: 了解Teams语音和呼叫策略。
audience: admin
ms.localizationpriority: medium
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8a63aa772d94a4a385301315d1c1bd3b6488fa3b
ms.sourcegitcommit: 9532eb79310cd653010565607fa394f2b8dd182d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/23/2022
ms.locfileid: "65646461"
---
# <a name="manage-voice-and-calling-policies-in-microsoft-teams"></a>在Microsoft Teams中管理语音和呼叫策略

语音和呼叫策略用于控制语音和呼叫Microsoft Teams。

## <a name="emergency-calling-policies"></a>紧急呼叫策略

使用 [紧急呼叫策略](manage-emergency-calling-policies.md) 来配置组织中的用户发出紧急呼叫时发生的情况。 这些策略在Teams管理中心或使用Windows PowerShell进行管理。

![紧急呼叫策略的屏幕截图。](media/emergency-calling-policy2.png)

## <a name="emergency-call-routing-policies"></a>紧急呼叫路由策略

如果你的组织已 **部署电话系统直接路由**，则可以使用 [紧急呼叫路由策略](manage-emergency-call-routing-policies.md)来确定紧急呼叫的路由位置、是否启用增强的紧急服务以及用于紧急服务的号码。 这些策略使用 PowerShell 或Microsoft Teams管理中心进行管理。

![紧急呼叫路由策略的屏幕截图。](media/emergency-call-routing-policy.png)

## <a name="caller-id-policies"></a>调用方 ID 策略

[调用方 ID 策略](caller-id-policies.md) 用于更改或阻止调用方 ID。

![调用方 ID 策略的屏幕截图。](media/caller-id-policy.png)

## <a name="voice-routing-policies"></a>语音路由策略

[语音路由策略](manage-voice-routing-policies.md)是公共交换电话网络 (PSTN) 使用记录的容器。 如果你的组织已部署 **电话系统直接路由，** 则可以使用这些策略。 语音路由策略可以使用 PowerShell 或Teams管理中心进行管理。

![语音路由策略的屏幕截图。](media/voice-routing-policy.png)

## <a name="calling-policies"></a>通话策略

[呼叫策略](teams-calling-policy.md) 控制哪些呼叫和呼叫转接功能可供用户使用，包括用户是否可以进行私人呼叫、向呼叫组发送呼叫以及将呼叫路由到语音邮件。

![调用策略的屏幕截图。](media/calling-policy.png)

## <a name="call-park-and-retrieve-policies"></a>调用寄存和检索策略

[通过呼叫寄存和检索](call-park-and-retrieve.md) ，用户可将其他用户置于暂停状态，并允许同一用户或其他人继续呼叫。

![呼叫寄存和检索策略的屏幕截图。](media/call-park-policy.png)

## <a name="create-and-manage-dial-plans"></a>创建并管理拨号计划

[拨号计划](create-and-manage-dial-plans.md) 转换拨号电话号码以进行呼叫授权和路由。 可以通过 PowerShell 或Microsoft Teams管理中心创建和管理拨号计划。

![拨号计划的屏幕截图。](media/dial-plans.png)

## <a name="related-topics"></a>相关主题

* [在Microsoft Teams中管理紧急呼叫策略](manage-emergency-calling-policies.md)
* [管理紧急呼叫路由策略](manage-emergency-call-routing-policies.md)
* [在 Microsoft Teams 中管理呼叫方 ID 策略](caller-id-policies.md)
* [管理语音路由策略](manage-voice-routing-policies.md)
* [Microsoft Teams 中的呼叫策略](teams-calling-policy.md)
* [Microsoft Teams 中的呼叫寄存和取回](call-park-and-retrieve.md)
* [创建并管理拨号计划](create-and-manage-dial-plans.md)
* [使用策略管理Teams](manage-teams-with-policies.md)
