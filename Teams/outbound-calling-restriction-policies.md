---
title: 出站呼叫限制-& PSTN 呼叫的音频会议
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 管理员可以控制音频会议和最终用户 PSTN 的呼叫可以由用户所做的类型。
ms.openlocfilehash: 84acbed4017a709b63e657f12ef0bbe3c1eb620c
ms.sourcegitcommit: 5a88788bd0a0b2ccbc5b977b38dcfe4681cd5d10
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/18/2020
ms.locfileid: "44278175"
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a>音频会议和用户 PSTN 通话的出站通话限制策略

作为管理员，您可以使用出站呼叫控件来限制组织用户可以进行的音频会议和最终用户 PSTN 呼叫类型。 

Outbound call controls can be applied on a per-user basis and provide the following two controls to independently restrict each type of outbound calls. By default, both controls are set to allow international and domestic outbound calls. 

|源代码|说明|控件选项|
|:-----|:-----|:-----|
|音频会议 PSTN 呼叫|限制出站类型 </br>允许从用户组织 </br>的会议内呼叫。|任何目的地（默认值）</br>在与 organizor 相同的国家或地区 </br> </br>仅对国家或地区进行分区 </br>不允许|
|最终用户 PSTN 呼叫|限制可以由用户 </br>拨打的呼叫类型。|国际和国内 （默认值）</br>版</br>无|

若要了解哪些国家/地区被视为区域 A，请参阅将[国家/地区分区](https://docs.microsoft.com/microsoftteams/calling-plans-for-office-365)。

   > [!NOTE]
   > 如果所拨打的号码位于与为会议组织者设置的 Office 365 相同的国家/地区（对于音频会议）或最终用户（如果最终用户 PSTN 呼叫），则会将呼叫视为国内呼叫。 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="restrict-audio-conferencing-outbound-calls"></a>限制音频会议出站呼叫 

![一个显示 Microsoft Teams 徽标的图标](media/teams-logo-30x30.png) **使用 Microsoft Teams 管理中心**

1. 在左侧导航中，单击 "**用户**"，然后从可用用户列表中选择用户。

2. 在页面的顶部，单击**编辑**。

3. 在**音频会议**旁边，单击**编辑**。

4. 在**会议拨出权限**下，选择所需的拨出限制选项。

5. 单击“**保存**”。 

![显示 Skype for Business 徽标的图标](media/sfb-logo-30x30.png) **使用 Skype for Business 管理中心**

1.    在**Skype for business 管理中心**的左侧导航中，转到 "**音频会议**  >  **用户**"，然后从可用的用户列表中选择用户。

2.    在"操作"窗格中，单击" **编辑**"。

3.    在**限制此用户从会议拨出**下，选择所需的拨出限制选项。

    ![拨出选项限制](media/restrictions-to-dial-outs.png)

5. 单击“**保存**”。

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

**使用 PowerShell**

出站呼叫限制由名为 OnlineDialOutPolicy 的单个策略控制，其中每个都有一个限制属性。 无法自定义策略，而是为每个设置组织使用预定义策略实例。 

Get CSOnlineDialOutPolicy cmdlet 可用于查看出站呼叫策略并使用 CSDialOutPolicy cmdlet 将其分配给用户。 （请注意，授予 cmdlet 不包含 "Online" 一词，因为 Get cmdlet 是。） 

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
|    Identity = "tag： DialoutCPCZoneAPSTNInternational"    |    会议中的用户只能拨出以对国家和地区进行分区，并且此用户可以拨出到国际和国内号码的电话。    |
|    Identity = "tag： DialoutCPCZoneAPSTNDomestic"    |    会议中的用户只能拨出以对国家和地区进行分区，并且此用户只能拨出到国内 PSTN 号码的出站呼叫。    |
|    Identity = "tag： DialoutCPCZoneAPSTNDisabled"    |    会议中的用户只能拨出以对国家和地区进行分区，并且除了紧急号码之外，此用户不能对 PSTN 号码进行任何出站呼叫。    |
