---
title: 音频会议的网络会议
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
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 以下介绍音频会议的开放预览功能。
ms.openlocfilehash: 38b8be382ccd1b80002688cdb7fce9aa166efc2c
ms.sourcegitcommit: f9daef3213a305676127cf5140af907e3b96d046
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2020
ms.locfileid: "48369177"
---
# <a name="open-preview-of-on-network-conferencing-for-audio-conferencing"></a>为音频会议打开网络会议预览

所有客户均可使用网络会议的开放预览。 网络会议允许组织通过直接路由向 Microsoft 拨入号码发送入站和出站音频会议呼叫。 此功能不用于将音频会议的支持扩展到第三方拨入号码。 如果网络会议用于通过第三方拨入电话号码将入站呼叫路由到音频会议服务，则不支持网络会议。

本文介绍为你的组织启用网络会议所需的先决条件和配置步骤。

> [!IMPORTANT]
> 网络会议不得与印度的任何电话设备一起部署。
  
## <a name="prerequisites"></a>先决条件

在配置网络会议之前，请确保你的组织满足以下先决条件： 

- 确保您的组织中启用或启用音频会议的所有用户都处于 "仅工作组" 模式。 只有团队会议才支持通过网络会议进行入站和出站音频会议呼叫的路由。

- 将音频会议许可证分配给将使用网络会议的所有用户。

- 设置音频会议服务。 有关其他信息，请参阅 [为 Microsoft 团队设置音频会议](set-up-audio-conferencing-in-teams.md)。

- 设置会话边界控制器 (SBC) 直接路由。 有关其他信息，请参阅 [规划直接路由](direct-routing-plan.md) 和 [配置直接路由](direct-routing-configure.md)。 

  如果仅为音频会议设置直接路由，则只需要完整的 "步骤1：连接 SBC" 即可进行网络会议。
  
## <a name="enable-the-routing-of-dial-in-calls-to-microsoft-audio-conferencing-through-direct-routing"></a>通过直接路由支持将拨入呼叫路由到 Microsoft 音频会议 

若要通过直接路由将本地用户拨打的拨入呼叫路由到音频会议服务，您需要为 SBCs 和专用分支 Exchange 配置适当的路由规则， (s)  (Pbx) 。

您需要配置您的站点的电话服务设备，通过直接路由主干将呼叫路由到您的组织的任何服务号码。

你可以在 "会议" 下的 "团队管理中心" 下找到服务号码 **> 会议桥** 或使用 Skype For Business Online PowerShell cmdlet get-csonlinedialinconferencingbridge。 有关其他信息，请参阅 [Microsoft 团队中的音频会议号码](see-a-list-of-audio-conferencing-numbers-in-teams.md)列表。

> [!NOTE]
> 对于具有按分钟付费的音频会议许可证的用户，此功能不可用。

## <a name="enable-the-routing-of-teams-meeting-dial-out-calls-through-direct-routing"></a>通过直接路由启用团队的路由会议拨出呼叫

从组织中的会议开始拨出呼叫的团队将从您的组织内的某个会议开始，包括呼叫我的呼叫和呼叫，并将新参与者加入会议。 

若要通过直接路由启用团队会议拨出路由，你需要创建并分配一个名为 "OnlineAudioConferencingRoutingPolicy" 的音频会议路由策略。 

OnlineAudioConferencingRoutingPolicy 策略等效于 CsOnlineVoiceRoutingPolicy 通过直接路由进行的 1:1 PSTN 呼叫。 可以使用以下 cmdlet 管理 OnlineAudioConferencingRoutingPolicy 策略：

-   新-CsOnlineAudioConferencingRoutingPolicy
- Set-CsOnlineAudioConferencingRoutingPolicy
- CsOnlineAudioConferencingRoutingPolicy
- 授权-CsOnlineAudioConferencingRoutingPolicy
- Remove-CsOnlineAudioConferencingRoutingPolicy

有关路由选择直接路由的详细信息，请参阅 [为直接路由配置语音路由](direct-routing-voice-routing.md)。


若要通过直接路由启用会议拨出呼叫的路由，您需要： 

- 配置音频会议路由策略
- 在组织的电话服务设备上配置路由
-  (可选) 配置拨号计划

来自团队会议的拨出呼叫来自会议网桥上的默认服务号码。 有关音频会议桥的默认服务号码的其他信息，请参阅 [在音频会议网桥上更改电话号码](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)。

### <a name="configure-audio-conferencing-routing-policies"></a>配置音频会议路由策略

音频会议路由策略 OnlineAudioConferencingRoutingPolicy 确定将哪些会议拨出呼叫路由到直接路由中继。 如果你熟悉 CsOnlineVoiceRoutingPolicy 策略，此策略的工作方式非常类似。

设置音频会议路由策略需要以下步骤：
1.  创建 PSTN 用法
2.  配置语音路由
3.  创建音频会议语音路由策略
4.  为你的用户分配策略


#### <a name="create-pstn-usages"></a>创建 PSTN 用法

PSTN 用法是语音路由的集合。 从给定组织者的会议启动拨出呼叫时，将使用语音路由基于通过用户的语音路由策略与用户关联的 PSTN 用法确定呼叫的路由路径。

你可以使用 "CsOnlinePstnUsage" cmdlet 创建 PSTN 使用。 例如：

```
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

#### <a name="configure-voice-routes"></a>配置语音路由

语音路由根据从团队会议中拨出的电话号码确定应用于路由呼叫的 PSTN 网关。 语音路由通过匹配使用 regex 模式的团队会议所拨的电话号码，确定应用于路由给定呼叫的 PSTN 网关。 创建语音路由时，路由必须与一个或多个 PSTN 使用实例相关联。

你可以使用 "CsOnlineVoiceRoute" cmdlet 创建语音路由，并定义要与语音路由关联的 regex 和网关。 例如：

```
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

#### <a name="create-audio-conferencing-voice-routing-policies"></a>创建音频会议语音路由策略

音频会议语音路由策略确定可能的路由，可用于根据会议拨出呼叫的目标电话号码传送来自组织者会议的呼叫。 音频会议语音路由策略与一个或多个 PSTN 用途相关联，后者随后确定可能尝试用于与策略关联的组织者拨出呼叫的可能路线。

可以使用 "CsOnlineAudioConferencingRoutingPolicy" cmdlet 创建音频会议语音路由策略。 例如：

```
New-CsOnlineAudioConferencingRoutingPolicy "Policy 1" -OnlinePstnUsages "US and Canada"
```

将策略分配给用户并从用户的其中一个会议中启动会议拨出呼叫时，将评估 PSTN 使用中通过用户的语音路由策略关联到组织者的语音路由。 如果会议拨出呼叫目标与与管理器关联的某个语音路由中的 regex 匹配，则会议拨出呼叫将路由到在语音路由中定义的 PSTN 网关。 如果会议拨出呼叫目标与与组织者关联的任何语音路由都不匹配，则由 Microsoft 发送会议拨出呼叫。

#### <a name="assign-a-policy-to-your-users"></a>为你的用户分配策略

定义音频会议路由策略后，您现在可以将它们分配给用户。 向其分配策略后，将对会议拨出呼叫进行评估，以确定其路由路径。 音频会议路由策略始终基于会议的组织者（独立于会议中启动会议拨出呼叫的用户）进行评估。

可以使用 "授权-CsOnlineAudioConferencingRoutingPolicy" cmdlet 将音频会议语音路由策略分配给用户。 例如：

```
Grant-CsOnlineAudioConferencingRoutingPolicy -Identity "<User Identity>" -PolicyName "Policy 1”
```


### <a name="configure-routing-on-the-telephony-equipment-of-your-organization"></a>在组织的电话服务设备上配置路由

在你的组织的电话服务设备上，你需要确保通过直接路由路由的会议拨出呼叫路由到目标目标。


### <a name="optional-configure-a-dial-plan"></a> (可选) 配置拨号计划

拨号计划是一组规范化规则，将已拨打的电话号码由单个用户转换为备用格式 (通常是) ，以供呼叫授权和呼叫路由使用。

默认情况下，团队用户可以采用 E：164格式拨出到 PSTN 号码，即 + \<country code\> \<number\> 。 但是，拨号计划可用于允许用户以其他格式拨打电话号码，例如4位数的分机号码。

如果想要通过网络会议启用基于扩展的拨号，可以将拨号计划设置为与 "分机" 拨号模式匹配，使其与您的组织的电话号码区域的电话号码范围相匹配。 若要设置拨号计划，请参阅 [创建和管理拨号计划](create-and-manage-dial-plans.md)。


## <a name="known-issues-in-open-preview"></a>打开预览中的已知问题

以下是当前在网络会议的开放式预览版中当前存在的已知问题的列表。 Microsoft 正在努力解决这些问题。

| 问题 | 规避 |
| :--- | :--- |
| 通过网络会议路由的匿名/隐藏呼叫方 Id 的拨入呼叫无法连接到会议。 | 如果可能，请将 PBX 或 SBC 中的配置设置为始终发送呼叫者 ID，以便通过网络会议路由呼叫。|
| 在某些情况下，当用户拨入服务时，向用户播放的欢迎消息 ( "欢迎使用音频会议服务 ..." ) 被截断，并且用户听不到 "欢迎" word。| 目前尚无此问题的解决方法。 |




## <a name="related-topics"></a>相关主题


