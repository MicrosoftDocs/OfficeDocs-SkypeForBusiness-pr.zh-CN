---
title: 音频会议的网络内会议
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: oscarr
ms.topic: conceptual
ms.tgt.pltfrm: cloud
audience: admin
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
- m365initiative-meetings
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 下面介绍音频会议的网络内开放预览版功能。
ms.openlocfilehash: d6df81cc077c69fdeb4246d682797d2ebb26b875
ms.sourcegitcommit: 950387da2a2c094b7580bcf81ae5d8b6dfba0d6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2021
ms.locfileid: "51637834"
---
# <a name="open-preview-of-on-network-conferencing-for-audio-conferencing"></a>打开音频会议网络会议预览版

网络会议开放预览版可供所有客户使用。 网络会议允许组织通过直接路由向 Microsoft 拨入号码发送入站和出站音频会议呼叫。 此功能不旨在将音频会议支持扩展到第三方拨入号码。 如果网络会议用于通过第三方拨入电话号码或 Microsoft 音频会议网桥的出站呼叫将入站呼叫路由到音频会议服务，则不支持网络会议。 

本文介绍为组织启用网络会议所需的先决条件和配置步骤。

> [!IMPORTANT]
> 不得使用印度的任何电话设备部署网络内会议。
  
## <a name="prerequisites"></a>先决条件

在配置网络会议之前，请确保组织满足以下先决条件： 

- 确保组织中已启用或将启用音频会议的所有用户都使用 Teams 进行所有会议。 仅 Teams 会议支持通过网络内会议路由入站和出站音频会议呼叫。

- 将音频会议许可证分配给将使用网络内会议的所有用户。

- 设置音频会议服务。 有关其他信息，请参阅 [为 Microsoft Teams 设置音频会议](set-up-audio-conferencing-in-teams.md)。

- 为直接路由设置 SBC () 边界控制器。 有关其他信息，请参阅 [规划直接路由](direct-routing-plan.md) 和 [配置直接路由](direct-routing-configure.md)。 

  如果仅针对音频会议设置直接路由，则只需完成"步骤 1：连接 SBC"网络会议。
  
## <a name="enable-the-routing-of-dial-in-calls-to-microsoft-audio-conferencing-through-direct-routing"></a>启用通过直接路由将拨入呼叫路由到 Microsoft 音频会议 

若要通过直接路由将本地用户拨打的拨入呼叫路由到音频会议服务，需要为 SDC 和专用交换机 (PBX)  (配置适当的) 。

需要配置站点的电话设备，以通过直接路由中继将呼叫路由到组织会议网桥的任何服务号码。

可以在 Teams 管理中心中的"会议 **"-> 会议** 网桥下找到服务号码，或者使用 Skype for Business Online PowerShell cmdlet Get-CsOnlineDialInConferencingBridge 查找服务号码。 有关其他信息，请参阅 Microsoft Teams 中的音频 [会议号码列表](see-a-list-of-audio-conferencing-numbers-in-teams.md)。

> [!NOTE]
> 具有每分钟音频会议付费许可证的用户无法使用此功能。

## <a name="enable-the-routing-of-teams-meeting-dial-out-calls-through-direct-routing"></a>通过直接路由启用 Teams 会议拨出呼叫的路由

Teams 会议拨出呼叫从你组织的会议内发起到 PSTN 号码，包括呼叫时呼叫和将新参与者带到会议。 

若要通过直接路由向网络用户启用 Teams 会议拨出路由，需要创建并分配名为"OnlineAudioConferencingRoutingPolicy"的音频会议路由策略。 

OnlineAudioConferencingRoutingPolicy 策略等同于通过直接路由进行 1：1 PSTN 呼叫的 CsOnlineVoiceRoutingPolicy。 可以使用以下 cmdlet 管理 OnlineAudioConferencingRoutingPolicy 策略：

-   New-CsOnlineAudioConferencingRoutingPolicy
- Set-CsOnlineAudioConferencingRoutingPolicy
- Get-CsOnlineAudioConferencingRoutingPolicy
- Grant-CsOnlineAudioConferencingRoutingPolicy
- Remove-CsOnlineAudioConferencingRoutingPolicy

有关直接路由的路由详细信息，请参阅 [为直接路由配置语音路由](direct-routing-voice-routing.md)。


若要通过直接路由启用会议拨出呼叫的路由，需要： 

- 配置音频会议路由策略
- 在组织的电话设备上配置路由
-  (可选) 配置拨号计划

Teams 会议的拨出呼叫来自会议网桥上的默认服务号码。 有关音频会议网桥的默认服务号码的其他信息，请参阅更改音频会议网桥 [上的电话号码](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)。

### <a name="configure-audio-conferencing-routing-policies"></a>配置音频会议路由策略

音频会议路由策略 OnlineAudioConferencingRoutingPolicy 确定将哪些会议拨出呼叫路由到直接路由中继。 如果熟悉 CsOnlineVoiceRoutingPolicy 策略，此策略的工作方式非常相似。

需要执行以下步骤来设置音频会议路由策略：
1.  创建 PSTN 使用情况
2.  配置语音路由
3.  创建音频会议语音路由策略
4.  向用户分配策略


#### <a name="create-pstn-usages"></a>创建 PSTN 使用情况

PSTN 用法是语音路由的集合。 当从给定组织者的会议发起拨出呼叫时，语音路由将用于根据通过用户的语音路由策略关联到用户的 PSTN 使用情况来确定呼叫的路由路径。

可以使用"Set-CsOnlinePstnUsage"cmdlet 创建 PSTN 使用情况。 例如：

```powershell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

#### <a name="configure-voice-routes"></a>配置语音路由

语音路由根据从 Teams 会议拨打的电话号码来确定用于路由呼叫的 PSTN 网关。 语音路由将 Teams 会议拨打的电话号码与正则表达式模式匹配，确定用于路由给定呼叫的 PSTN 网关。 创建语音路由时，该路由必须与一个或多个 PSTN 用法相关联。

可以使用"New-CsOnlineVoiceRoute"cmdlet 创建语音路由并定义要与语音路由关联的正则表达式和网关。 例如：

```powershell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

#### <a name="create-audio-conferencing-voice-routing-policies"></a>创建音频会议语音路由策略

音频会议语音路由策略根据会议拨出呼叫的目标电话号码，确定可用于路由源自组织者会议的呼叫的可能路由。 音频会议语音路由策略与一个或多个 PSTN 使用相关联，这反过来决定了可能尝试用于与该策略关联的组织者的会议拨出呼叫的路由。

可以使用"New- CsOnlineAudioConferencingRoutingPolicy"cmdlet 创建音频会议语音路由策略。 例如：

```powershell
New-CsOnlineAudioConferencingRoutingPolicy "Policy 1" -OnlinePstnUsages "US and Canada"
```

将策略分配给用户后，当从用户的其中一个会议发起会议拨出呼叫时，将评估通过用户的语音路由策略关联到组织者的 PSTN 使用情况中的语音路由。 如果会议拨出呼叫目标与与组织者关联的其中一个语音路由中的正则表达式匹配，会议拨出呼叫将路由到语音路由中定义的 PSTN 网关。 如果会议拨出呼叫目标与与组织者关联的任何语音路由不匹配，则会议拨出呼叫由 Microsoft 路由。

#### <a name="assign-a-policy-to-your-users"></a>向用户分配策略

定义音频会议路由策略后，现在可以将其分配给用户。 为它们分配策略后，将针对会议拨出呼叫进行评估，以确定其路由路径。 音频会议路由策略始终根据会议组织者进行评估，独立于发起会议拨出呼叫的会议用户。

可以使用"Grant-CsOnlineAudioConferencingRoutingPolicy"cmdlet 向用户分配音频会议语音路由策略。 例如：

```powershell
Grant-CsOnlineAudioConferencingRoutingPolicy -Identity "<User Identity>" -PolicyName "Policy 1”
```


### <a name="configure-routing-on-the-telephony-equipment-of-your-organization"></a>在组织的电话设备上配置路由

在组织的电话设备上，你需要确保通过直接路由路由的会议拨出呼叫路由到预期的网络目标。


### <a name="optional-configure-a-dial-plan"></a> (可选) 配置拨号计划

拨号计划是一组规范化规则，用于将单个用户拨打的电话号码转换为备用格式 (通常为 E.164) ，以便进行呼叫授权和呼叫路由。

默认情况下，Teams 用户可以拨打 E.164 格式的 PSTN 号码，即 + \<country code\> \<number\> 。 但是，拨号计划可用于允许用户以其他格式拨打电话号码，例如 4 位数分机号码。

如果要通过网络内会议启用基于分机的拨号，可以设置拨号计划，以将分机拨号模式与贵组织的电话号码范围相匹配。 若要设置拨号计划，请参阅 [创建和管理拨号计划](create-and-manage-dial-plans.md)。


## <a name="known-issues-in-open-preview"></a>开放预览版中的已知问题

下面是网络会议开放预览版当前存在已知问题的列表。 Microsoft 正在努力解决这些问题。

| 问题 | 解决方法 |
| :--- | :--- |
| 通过网络会议路由的具有匿名/隐藏呼叫 ID 的拨入呼叫无法连接到会议。 | 如果可能，在 PBX 或 SBC 中设置配置，始终发送通过网络会议路由的呼叫的来电显示。|
| 在某些情况下，当用户拨入服务时向用户播放的欢迎消息 ("欢迎使用音频会议服务...") 将被截断，用户不会听到"欢迎"一词。| 目前没有此问题的解决方法。 |




## <a name="related-topics"></a>相关主题


