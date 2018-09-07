---
title: 音频会议和用户 PSTN 通话的出站呼叫限制策略
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
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 管理员可以控制音频会议和最终用户 PSTN 的呼叫可以由用户所做的类型。
ms.openlocfilehash: fd1a3b770debfcc6aa048d150b6536c94db4f9ce
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23856878"
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a>音频会议和用户 PSTN 通话的出站呼叫限制策略

作为管理员，您可以使用出站呼叫控件来限制组织用户可以进行的音频会议和最终用户 PSTN 呼叫类型。 

出站通话控件可以应用基于每个用户，并提供了下列两个控件，以便独立限制每种类型的出站呼叫。 默认情况下，这两个控件设置为允许国际和国内出站呼叫。 

|控件|说明|控件选项|
|:-----|:-----|:-----|
|音频会议 PSTN 呼叫|限制出站类型 </br>允许从用户组织 </br>的会议内呼叫。|国际和国内 （默认值）</br>国内</br>无|
|最终用户 PSTN 呼叫|限制可以由用户 </br>拨打的呼叫类型。|国际和国内 （默认值）</br>国内</br>无|

   > [!NOTE]
   > 如果呼叫的电话号码位于与会议组织者（对于音频会议）或最终用户（对于最终用户 PSTN 呼叫）的 Office 365 中设置的国家/地区相同，则呼叫被确定为国内。 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="restrict-audio-conferencing-outbound-calls"></a>限制音频会议出站呼叫 

![teams-logo-30x30.png](../images/teams-logo-30x30.png) **使用 Microsoft Teams 和 Skype for Business 管理中心：**

1. 在左侧导航窗格中，单击**用户**，然后从可用用户列表中选择用户。

2. 在页面的顶部，单击**编辑**。

3. 在**音频会议**旁边，单击**编辑**。

4. 在**会议拨出权限**下，选择所需的拨出限制选项。

5. 单击**保存**。 

![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **使用 Skype for Business 管理中心**

1.  在左侧导航窗格的 **Skype for Business 管理中心**中，转到**音频会议** > **用户**，然后从可用用户列表中选择用户。

2.  在“操作”窗格中，单击**编辑**。

3.  在**限制此用户从会议拨出**下，选择所需的拨出限制选项。

    ![拨出选项限制](../images/restrictions-to-dial-outs.png)

5. 单击**保存**。

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

**使用 PowerShell**

出站呼叫限制由名为 OnlineDialOutPolicy 的单个策略控制，其中每个都有一个限制属性。 无法自定义策略，而是为每个设置组织使用预定义策略实例。 

Get CSOnlineDialOutPolicy cmdlet 可用于查看出站呼叫策略并使用 CSDialOutPolicy cmdlet 将其分配给用户。 （请注意，授予 cmdlet 不包含 Get cmdlet 使用的单词“Online”。） 

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
