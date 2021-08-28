---
title: 出站呼叫限制 - 音频会议& PSTN 呼叫
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 管理员可以控制用户可以拨打的音频会议和最终用户 PSTN 呼叫的类型。
ms.openlocfilehash: 9e7f656cd51131237507cc184e021128a33d9268
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58598406"
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a>音频会议和用户 PSTN 通话的出站通话限制策略

作为管理员，您可以使用出站呼叫控件来限制音频会议和最终用户公用电话交换网 (PSTN) 呼叫的类型，这些呼叫由您的组织中的用户可以进行。

可以基于每个用户或租户应用出站调用控件，并提供以下两个控件来独立限制每种类型的出站调用。 默认情况下，这两个控件设置为允许国际和国内出站呼叫。

|控件|说明|控件选项|
|:-----|:-----|:-----|
|音频会议 PSTN 呼叫|限制出站类型 </br>允许从用户组织 </br>的会议内呼叫。|任何目标 (默认) </br>与组织者在同一国家/地区 </br> [仅区域 A 国家/地区](audio-conferencing-zones.md) </br>不允许|
|最终用户 PSTN 呼叫|限制可以由用户 </br>拨打的呼叫类型。|国际和国内 （默认值）</br>国内</br>无|

若要了解哪些国家和地区被视为区域 A，请参阅音频会议 [的国家和地区区域](audio-conferencing-zones.md)。

   > [!NOTE]
   > 如果拨打的号码位于为会议组织者设置 Microsoft 365 或 Office 365 的国家/地区（对于音频会议 () ）或最终用户 (（对于最终用户 PSTN 呼叫) ）中，呼叫被视为国内呼叫。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="restrict-audio-conferencing-outbound-calls"></a>限制音频会议出站呼叫

![Microsoft Teams徽标 使用 ](media/teams-logo-30x30.png) **Microsoft Teams 管理中心**

1. 在左侧导航栏中， **选择"用户**"，显示名称可用用户列表中选择该用户的用户名。

3. 在"**音频会议"旁边，** 选择"**编辑"。**

4. 在 **"从会议拨出"** 下，选择你需要的拨出限制选项。

5. 选择“**保存**”。

![显示 Skype for Business 徽标的图标](media/sfb-logo-30x30.png) **使用 Skype for Business 管理中心**

1. 在 **Skype for Business** 管理中心的 左侧导航中，转到"音频会议用户"，然后从可用  >  用户列表中选择用户。

2. 在"操作"窗格中，选择"编辑 **"。**

3.  在 **限制此用户从会议拨出** 下，选择所需的拨出限制选项。

      ![拨出选项限制](media/restrictions-to-dial-outs.png)

4. 选择“**保存**”。

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

**使用 PowerShell**

出站调用限制由名为 OnlineDialOutPolicy 的单个策略控制，该策略具有每个策略的限制属性。 无法自定义策略，而是为每个设置组织使用预定义策略实例。

可以使用 Get-CSOnlineDialOutPolicy cmdlet 查看出站调用策略，并使用以下命令进行设置。

**使用以下 cmdlet 在每个用户级别设置策略**。  (Grant cmdlet 不包含"联机"一词，就像 Get cmdlet 一样) 

```
Grant-CsDialoutPolicy -Identity <username> -PolicyName <policy name>    
```

**使用以下 cmdlet 在租户级别设置策略**。

```
Grant-CsDialoutPolicy  -Tenant <guid> -PolicyName <policy name>  -Global 
```

未分配任何拨出策略的租户的所有用户都将获取此策略。 其他用户仍保留其当前策略。

下表概述了每个策略。

|PowerShell cmdlet|说明|
|:-----|:-----|
|标识='tag:DialoutCPCandPSTNInternational'    |    参加会议的用户可以拨打国际和国内号码，同时此用户还可出站呼叫国际和国内号码。    |
|标识='tag:DialoutCPCDomesticPSTNInternational'  |    参加会议的用户只能拨打国内号码，同时此用户只能出站呼叫国际和国内号码。    |
|    标识='tag:DialoutCPCDisabledPSTNInternational'    |    会议中的用户无法拨出。此用户可以拨打国际和国内号码的出站电话。    |
|    标识='tag:DialoutCPCInternationalPSTNDomestic'    |    参加会议的用户可以拨打国际和国内号码，同时此用户只能出站呼叫国内 PSTN 号码。    |
|    标识='tag:DialoutCPCInternationalPSTNDisabled'    |    参加会议的用户可以拨打国际和国内号码，同时此用户无法出站呼叫 PSTN 号码，紧急号码除外。    |
|    标识='tag:DialoutCPCandPSTNDomestic'    |    参加会议的用户只能拨打国内号码，同时此用户只能出站呼叫对国内 PSTN 号码。    |
|    标识='tag:DialoutCPCDomesticPSTNDisabled'    |    参加会议的用户仅可拨打国内号码，同时此用户无法出站呼叫 PSTN 号码，紧急号码除外。    |
|    标识='tag:DialoutCPCDisabledPSTNDomestic'    |    会议中的用户无法拨出，并且此用户只能拨打国内 PSTN 号码的出站呼叫。    |
|    标识='tag:DialoutCPCandPSTNDisabled'    |    会议中的用户无法拨出，并且除紧急号码外，此用户无法拨打 PSTN 号码的任何出站呼叫。    |
|    Identity='tag：DialoutCPCZoneAPSTNInternational'    |    会议中的用户只能拨出到区域 [A](audio-conferencing-zones.md)国家和地区，并且此用户可以拨打国际和国内号码的出站呼叫。    |
|    Identity='tag：DialoutCPCZoneAPSTNDomestic'    |    会议中的用户只能拨出到 [区域 A](audio-conferencing-zones.md)国家和地区，并且此用户只能拨打国内 PSTN 号码的出站呼叫。    |
|    Identity='tag：DialoutCPCZoneAPSTNDisabled'    |    会议中的用户只能拨出到区域 [A](audio-conferencing-zones.md)国家和地区，并且除了紧急号码之外，此用户无法对 PSTN 号码进行任何出站呼叫。    |
