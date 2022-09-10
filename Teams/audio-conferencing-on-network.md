---
title: 音频会议的网络会议
ms.author: heidip
author: MicrosoftHeidi
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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 下面介绍了音频会议的网络。
ms.openlocfilehash: 56e2addc3b924d7d73df7475ad217a999dc0aca0
ms.sourcegitcommit: 5abfb6f1abe10b6d32cf6eb97a890cf3138ed0e6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2022
ms.locfileid: "67641873"
---
# <a name="on-network-conferencing-for-audio-conferencing"></a>音频会议的网络会议

网络会议允许组织通过直接路由向 Microsoft 拨入号码发送入站和出站音频会议呼叫。 此功能不旨在将音频会议的支持扩展到第三方拨入号码。 如果网络会议用于通过第三方电话拨入电话号码或从 Microsoft 音频会议桥向 PSTN 的出站呼叫路由到音频会议服务的入站呼叫，则不支持网络会议。

本文介绍为组织启用网络会议所需的先决条件和配置步骤。

> [!IMPORTANT]
> 网络会议不得与印度的任何电话设备一起部署。

## <a name="prerequisites"></a>先决条件

在配置网络会议之前，请确保组织满足以下先决条件：

- 确保组织中为音频会议启用或将启用的所有用户都使用 Teams 进行所有会议。 仅 Teams 会议支持通过网络会议路由入站和出站音频会议呼叫。

- 将音频会议许可证分配给所有将使用网络会议的用户。

- 设置音频会议服务。 有关其他信息，请参阅 [为 Microsoft Teams 设置音频会议](set-up-audio-conferencing-in-teams.md)。

- 为直接路由设置会话边框控制器 (SBC) 。 有关其他信息，请参阅 [计划直接路由](direct-routing-plan.md) 和 [配置直接路由](direct-routing-configure.md)。

  如果设置直接路由只是为了音频会议，则只需完成网络会议的“步骤 1：连接 SBC”。

## <a name="enable-the-routing-of-dial-in-calls-to-microsoft-audio-conferencing-through-direct-routing"></a>通过直接路由启用到 Microsoft 音频会议的电话拨入呼叫的路由

若要通过直接路由将本地用户拨打的电话拨入电话路由到音频会议服务，需要为 SBC 和 Private Branch Exchange ()  (PBXs) 配置适当的路由规则。

需要配置站点的电话设备，以便通过直接路由中继将呼叫路由到组织会议网桥的任何服务号码。

你可以在 Teams 管理中心（ **会议->会议桥** ）下或使用 Teams PowerShell cmdlet Get-CsOnlineDialInConferencingBridge 找到服务号码。 有关其他信息，请参阅 [Microsoft Teams 中的音频会议号码](see-a-list-of-audio-conferencing-numbers-in-teams.md)列表。

> [!NOTE]
> 此功能不适用于具有按分钟付费音频会议许可证的用户。

## <a name="enable-the-routing-of-teams-meeting-dial-out-calls-through-direct-routing"></a>通过直接路由启用 Teams 会议拨号呼叫的路由

Teams 会议拨号呼叫从组织中的会议内启动到 PSTN 号码，包括呼叫我呼叫和呼叫以将新参与者带到会议。

若要通过直接路由向网络用户启用 Teams 会议拨号路由，需要创建并分配名为“OnlineAudioConferencingRoutingPolicy”的音频会议路由策略。

OnlineAudioConferencingRoutingPolicy 策略等效于通过直接路由进行 1：1 PSTN 调用的 CsOnlineVoiceRoutingPolicy。 OnlineAudioConferencingRoutingPolicy 策略可以通过使用以下 cmdlet 进行管理：

- New-CsOnlineAudioConferencingRoutingPolicy
- Set-CsOnlineAudioConferencingRoutingPolicy
- Get-CsOnlineAudioConferencingRoutingPolicy
- Grant-CsOnlineAudioConferencingRoutingPolicy
- Remove-CsOnlineAudioConferencingRoutingPolicy

有关直接路由的路由的详细信息，请参阅 [为直接路由配置语音路由](direct-routing-voice-routing.md)。

若要通过直接路由启用会议拨号呼叫的路由，需要：

- 配置音频会议路由策略
- 在组织的电话设备上配置路由
-  (可选) 配置拨号计划

Teams 会议的拨号呼叫来自会议桥上的默认服务号码。 有关音频会议网桥的默认服务号码的其他信息，请参阅 [“更改音频会议桥上的电话号码](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)”。

### <a name="configure-audio-conferencing-routing-policies"></a>配置音频会议路由策略

音频会议路由策略 OnlineAudioConferencingRoutingPolicy 确定将哪些会议拨出呼叫路由到直接路由中继。 如果你熟悉 CsOnlineVoiceRoutingPolicy 策略，则此策略的工作方式非常相似。

设置音频会议路由策略需要执行以下步骤：

1. 创建 PSTN 用法
1. 配置语音路由
1. 创建音频会议语音路由策略
1. 为用户分配策略

#### <a name="create-pstn-usages"></a>创建 PSTN 用法

PSTN 用法是语音路由的集合。 当从给定组织者的会议启动拨号呼叫时，语音路由将用于根据通过用户的语音路由策略与用户关联的 PSTN 使用情况确定呼叫的路由路径。

可以使用“Set-CsOnlinePstnUsage”cmdlet 创建 PSTN 使用情况。 例如：

```powershell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

#### <a name="configure-voice-routes"></a>配置语音路由

语音路由根据 Teams 会议拨号的电话号码确定应用于路由呼叫的 PSTN 网关。 语音路由确定应用于路由给定呼叫的 PSTN 网关，方法是将 Teams 会议中拨号的电话号码与正则表达式模式相匹配。 创建语音路由时，路由必须与一个或多个 PSTN 用法相关联。

可以使用“New-CsOnlineVoiceRoute”cmdlet 创建语音路由并定义要与语音路由关联的正则表达式和网关。 例如：

```powershell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

#### <a name="create-audio-conferencing-voice-routing-policies"></a>创建音频会议语音路由策略

音频会议语音路由策略根据会议拨出呼叫的目标电话号码确定可用于路由来自组织者会议的呼叫的可能路由。 音频会议语音路由策略与一个或多个 PSTN 使用情况相关联，而 PSTN 使用情况又决定了将尝试用于与策略关联的组织者的会议拨号呼叫的可能路由。

可以使用“New- CsOnlineAudioConferencingRoutingPolicy”cmdlet 创建音频会议语音路由策略。 例如：

```powershell
New-CsOnlineAudioConferencingRoutingPolicy "Policy 1" -OnlinePstnUsages "US and Canada"
```

将策略分配给用户后，当从用户的某个会议启动会议拨号呼叫时，将评估通过用户的语音路由策略关联到组织者的 PSTN 使用情况中的语音路由。 如果会议拨出呼叫目标与某个与组织者关联的语音路由中的正则表达式匹配，则会议拨出呼叫将路由到语音路由中定义的 PSTN 网关。 如果会议拨出呼叫目标与与组织者关联的任何语音路由不匹配，则会由 Microsoft 路由会议拨出呼叫。

#### <a name="assign-a-policy-to-your-users"></a>为用户分配策略

定义音频会议路由策略后，现在可以将其分配给用户。 将策略分配给他们后，会根据策略评估会议拨号呼叫，以确定其路由路径。 音频会议路由策略始终基于会议组织者进行评估，独立于启动会议拨号呼叫的会议中的用户。

可以使用“Grant-CsOnlineAudioConferencingRoutingPolicy”cmdlet 向用户分配音频会议语音路由策略。 例如：

```powershell
Grant-CsOnlineAudioConferencingRoutingPolicy -Identity "<User Identity>" -PolicyName "Policy 1"
```

### <a name="configure-routing-on-the-telephony-equipment-of-your-organization"></a>在组织的电话设备上配置路由

在组织的电话设备上，需要确保通过直接路由路由的会议拨号呼叫路由到预期的网络目标。

### <a name="optional-configure-a-dial-plan"></a> (可选) 配置拨号计划

拨号计划是一组规范化规则，用于将单个用户拨打的电话号码转换为备用格式 (通常为 E.164) ，用于呼叫授权和呼叫路由。

默认情况下，Teams 用户可以以 E.164 格式（即 +\<country code\>\<number\>）拨出 PSTN 号码。 但是，拨号计划可用于允许用户拨打其他格式的电话号码，例如 4 位扩展名。

如果要通过网络会议启用基于扩展的拨号，可以设置拨号计划，以将扩展拨号模式与组织的电话号码范围相匹配。 若要设置拨号计划，请参阅 [“创建和管理拨号计划](create-and-manage-dial-plans.md)”。

## <a name="related-topics"></a>相关主题
