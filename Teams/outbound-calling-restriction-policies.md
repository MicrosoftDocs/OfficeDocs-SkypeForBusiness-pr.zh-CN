---
title: 出站呼叫限制 - 音频会议& PSTN 呼叫
ms.reviewer: ''
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.topic: article
ms.service: msteams
ms.tgt.pltfrm: cloud
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
- Audio Conferencing
- seo-marvel-mar2020
description: 管理员可以控制用户可以进行的音频会议和最终用户 PSTN 调用的类型。
ms.openlocfilehash: 67c138db8522ec6eee1f384e182f5c8d01ea40fd
ms.sourcegitcommit: 5abfb6f1abe10b6d32cf6eb97a890cf3138ed0e6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2022
ms.locfileid: "67641763"
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a>音频会议和用户 PSTN 通话的出站通话限制策略

作为管理员，可以使用出站呼叫控制来限制音频会议和最终用户公共交换电话网络的类型 (PSTN) 可由组织中的用户进行的呼叫。

可以根据每个用户或租户应用出站呼叫控件，并提供以下两个控件来独立限制每种类型的出站调用。 默认情况下，这两个控件设置为允许国际和国内出站呼叫。

|控制|说明|控件选项|
|:-----|:-----|:-----|
|音频会议 PSTN 呼叫|限制出站类型 </br>允许从用户组织 </br>的会议内呼叫。|任何目标 (默认) </br>与组织者位于同一国家或地区 </br> 仅[限区域 A 国家/地区](audio-conferencing-zones.md) </br>不允许|
|最终用户 PSTN 调用|限制可以由用户 </br>拨打的呼叫类型。|国际和国内 （默认值）</br>国内</br>无|

若要了解哪些国家和地区被视为区域 A，请参阅 [音频会议的国家/地区和区域](audio-conferencing-zones.md)。

   > [!NOTE]
   > 如果拨号的号码位于为会议组织者设置了 Microsoft 365 或Office 365的同一国家/地区，则呼叫被视为国内呼叫 (（对于音频会议) ），或者最终用户在最终用户 PSTN 呼叫) 的情况下 (。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="restrict-audio-conferencing-outbound-calls"></a>限制音频会议出站呼叫

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 管理中心

1. 在左侧导航栏中，选择 **“用户**”，然后从可用用户列表中选择用户的显示名称。

2. 接下来转到 **音频会议**，选择 **“编辑**”。

3. 在 **会议拨号** 下，选择所需的拨出限制选项。

4. 选择“**保存**”。

### <a name="using-powershell"></a>使用 PowerShell

出站呼叫限制由名为 OnlineDialOutPolicy 的单个策略控制，该策略对每个策略都有限制属性。 无法自定义策略，而是为每个设置组织使用预定义策略实例。

可以使用Get-CSOnlineDialOutPolicy cmdlet 查看出站调用策略，并使用以下命令进行设置。

**使用以下 cmdlet 在每个用户级别设置** 策略。  (Grant cmdlet 不包含“Online”一词，就像 Get cmdlet 那样。) 

```powershell
Grant-CsDialoutPolicy -Identity <username> -PolicyName <policy name>    
```

**使用以下 cmdlet 在租户级别设置** 策略。

```powershell
Grant-CsDialoutPolicy -PolicyName <policy name>  -Global 
```

未分配任何拨号策略的租户的所有用户都将获得此策略。 其他用户仍保留其当前策略。

**使用以下 cmdlet 检查租户级别的当前** 策略。

```powershell
Get-CSOnlineDialOutPolicy -Identity Global
```

下表概述了每个策略。

|PowerShell cmdlet|说明|
|:-----|:-----|
|标识='tag:DialoutCPCandPSTNInternational'    |    参加会议的用户可以拨打国际和国内号码，同时此用户还可出站呼叫国际和国内号码。    |
|标识='tag:DialoutCPCDomesticPSTNInternational'  |    参加会议的用户只能拨打国内号码，同时此用户只能出站呼叫国际和国内号码。    |
|    标识='tag:DialoutCPCDisabledPSTNInternational'    |    会议中的用户无法拨打电话。此用户可以拨打国际和国内号码的出站呼叫。    |
|    标识='tag:DialoutCPCInternationalPSTNDomestic'    |    参加会议的用户可以拨打国际和国内号码，同时此用户只能出站呼叫国内 PSTN 号码。    |
|    标识='tag:DialoutCPCInternationalPSTNDisabled'    |    参加会议的用户可以拨打国际和国内号码，同时此用户无法出站呼叫 PSTN 号码，紧急号码除外。    |
|    标识='tag:DialoutCPCandPSTNDomestic'    |    参加会议的用户只能拨打国内号码，同时此用户只能出站呼叫对国内 PSTN 号码。    |
|    标识='tag:DialoutCPCDomesticPSTNDisabled'    |    参加会议的用户仅可拨打国内号码，同时此用户无法出站呼叫 PSTN 号码，紧急号码除外。    |
|    标识='tag:DialoutCPCDisabledPSTNDomestic'    |    会议中的用户无法拨出，并且此用户只能对国内 PSTN 号码进行出站呼叫。    |
|    标识='tag:DialoutCPCandPSTNDisabled'    |    会议中的用户无法拨打电话，此用户除了紧急号码外，无法对 PSTN 号码进行任何出站呼叫。    |
|    Identity='tag：DialoutCPCZoneAPSTNInternational'    |    会议中的用户只能拨打 [A 区国家和地区](audio-conferencing-zones.md)的电话，此用户可以拨打国际和国内号码的出站电话。    |
|    Identity='tag：DialoutCPCZoneAPSTNDomestic'    |    会议中的用户只能拨出 [到区域 A](audio-conferencing-zones.md) 国家和地区，而此用户只能拨打国内 PSTN 号码的出站呼叫。    |
|    Identity='tag：DialoutCPCZoneAPSTNDisabled'    |    会议中的用户只能拨打 [A 区国家和地区](audio-conferencing-zones.md)，此用户除了紧急号码外，无法对 PSTN 号码进行任何出站呼叫。    |
