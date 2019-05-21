---
title: 音频会议和用户 PSTN 通话的出站通话限制策略
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 管理员可以控制音频会议和最终用户 PSTN 的呼叫可以由用户所做的类型。
ms.openlocfilehash: e4589a2785d5debf4de6d6a146ede76b020cd2d6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34299150"
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a>音频会议和用户 PSTN 通话的出站通话限制策略

作为管理员，您可以使用出站呼叫控件来限制组织用户可以进行的音频会议和最终用户 PSTN 呼叫类型。 

Outbound call controls can be applied on a per-user basis and provide the following two controls to independently restrict each type of outbound calls. By default, both controls are set to allow international and domestic outbound calls. 

|源代码|说明|控件选项|
|:-----|:-----|:-----|
|音频会议 PSTN 呼叫|限制出站类型 </br>允许从用户组织 </br>的会议内呼叫。|国际和国内 （默认值）</br>版</br>无|
|最终用户 PSTN 呼叫|限制可以由用户 </br>拨打的呼叫类型。|国际和国内 （默认值）</br>版</br>无|

   > [!NOTE]
   > 如果所拨打的号码位于与会议组织者 (如音频会议) 或最终用户 (如果最终用户 PSTN 呼叫) 的组织者相同的365国家内, 则会将呼叫视为国内呼叫。 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="restrict-audio-conferencing-outbound-calls"></a>限制音频会议出站呼叫 

![](../images/teams-logo-30x30.png) **使用 Microsoft 团队管理中心的**teams-logo-30x30

1. 在左侧导航中, 单击 "**用户**", 然后从可用用户列表中选择用户。

2. 在页面的顶部，单击**编辑**。

3. 在**音频会议**旁边，单击**编辑**。

4. 在**会议拨出权限**下，选择所需的拨出限制选项。

5. 单击“**保存**”。 

![](../images/sfb-logo-30x30.png) **使用 Skype for business 管理中心**sfb-logo-30x30

1.  在**Skype for business 管理中心**的左侧导航中, 转到 "**音频会议** > **用户**", 然后从可用的用户列表中选择用户。

2.  在"操作"窗格中，单击" **编辑**"。

3.  在**限制此用户从会议拨出**下，选择所需的拨出限制选项。

    ![拨出选项限制](../images/restrictions-to-dial-outs.png)

5. 单击“**保存**”。

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

**使用 PowerShell**

Outbound call restrictions are controlled by a single policy called OnlineDialOutPolicy which has a restriction attribute for each. The policy cannot be customized, rather there are pre-defined policy instances for each combination of the settings. 

You can use the Get-CSOnlineDialOutPolicy cmdlet to view the outbound calling policies and assign them to users by using the Grant-CSDialOutPolicy cmdlet. (Please note that the Grant cmdlet doesn’t contain the word “Online” as the Get cmdlet does.) 

下表概述了每个策略。

|||
|:-----|:-----|
|标识='tag:DialoutCPCandPSTNInternational'    |    参加会议的用户可以拨打国际和国内号码，同时此用户还可出站呼叫国际和国内号码。    |
|标识='tag:DialoutCPCDomesticPSTNInternational'  |    参加会议的用户只能拨打国内号码，同时此用户只能出站呼叫国际和国内号码。    |
|    标识='tag:DialoutCPCDisabledPSTNInternational'    |    参加会议的用户无法进行任何拨出。此用户可以出站呼叫国际和国内号码。    |
|    标识='tag:DialoutCPCInternationalPSTNDomestic'    |    参加会议的用户可以拨打国际和国内号码，同时此用户只能出站呼叫国内 PSTN 号码。    |
|    标识='tag:DialoutCPCInternationalPSTNDisabled'    |    参加会议的用户可以拨打国际和国内号码，同时此用户无法出站呼叫 PSTN 号码，紧急号码除外。    |
|    标识='tag:DialoutCPCandPSTNDomestic'    |    参加会议的用户只能拨打国内号码，同时此用户只能出站呼叫对国内 PSTN 号码。    |
|    标识='tag:DialoutCPCDomesticPSTNDisabled'    |    参加会议的用户仅可拨打国内号码，同时此用户无法出站呼叫 PSTN 号码，紧急号码除外。    |
|    标识='tag:DialoutCPCDisabledPSTNDomestic'    |    参加会议的用户无法进行任何拨出，同时此用户仅可出站呼叫国内 PSTN 号码。    |
|    标识='tag:DialoutCPCandPSTNDisabled'    |    参加会议的用户无法拨打任何号码，同时此用户无法出站呼叫  PSTN 号码，紧急号码除外。    |
