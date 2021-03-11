---
title: 使用直接路由、GCCH 和 DoD 的音频会议
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
f1.keywords:
- NOCSH
localization_priority: Normal
description: 管理员可以了解如何在 GCCH 和 DoD 环境中通过直接路由使用音频会议。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 84f2789c6d4f4e9c5446ad39d6f2d50d842b92a6
ms.sourcegitcommit: 0a7c1f52484452f66f678b0feca1455bade4fcf3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/11/2021
ms.locfileid: "50716927"
---
# <a name="audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>适用于 GCC High 和 DoD 且含直接路由的音频会议

具有直接路由的 GCC High 和 DoD 的音频会议使参与者能够使用电话设备加入 GCC High 或 DoD 组织中 Teams 会议。 在 Internet 连接受限或用户正在路况中且无法访问 Teams 等情况下，会议参与者可能希望使用电话设备加入 Teams 会议。 参与者可以通过拨入组织的拨入电话号码或让会议拨出到其电话设备来选择加入会议。

借助具有 GCC High 和 DoD 直接路由的音频会议，您的组织使用自己的号码作为拨入电话号码，并且通过直接路由路由到电话设备的所有会议拨出。 若要启用该服务，组织需要设置直接路由并配置可用作拨入电话号码的电话号码。 使用直接路由的要求不同于提供给非 GCC High 和非 DoD 组织的音频会议服务，其中拨入电话号码由 Microsoft 提供。

## <a name="deploy-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>使用直接路由为 GCC High 和 DoD 部署音频会议

### <a name="step-1-get-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses"></a>步骤 1：使用 GCC High 或 DoD 许可证的直接路由获取音频会议 

若要在 GCC High 或 DoD 中使用音频会议，您的组织和组织中用户需要分配有具有直接路由许可证的音频会议。 以下是使用直接路由为 GCC High 或 DoD 启用音频会议所需的许可证。

- GCC 高：音频会议 - 组织的 GCC 高租户许可证和音频会议 - 用户的 GCC 高许可证。

- DoD：音频会议 - 组织的 DoD 租户许可证和音频会议 - 用户的 DoD 许可证。

启用该服务需要租户许可证和至少一个用户许可证。 不能仅启用租户许可证或仅具有用户许可证的服务。 若要获取租户和组织中用户的服务许可证，请联系帐户团队。

> [!IMPORTANT]
> 在设置拨入电话号码并且用户在 Teams 客户端中具有工作拨号盘之前，无法为具有直接路由的音频会议启用用户。 建议在按本文所述设置拨入电话号码之前，不要向用户分配具有直接路由的 GCC 高或 DoD 许可证的音频会议。

### <a name="step-2-set-up-direct-routing"></a>步骤 2：设置直接路由

若要设置直接路由，请参阅以下文章：

- [规划直接路由](direct-routing-plan.md)

- [配置直接路由](direct-routing-configure.md)

> [!NOTE]
> 设置直接路由时，请记住使用这两篇文章中所述的 GCC High 或 DoD 特定的 FQDN 和端口。

### <a name="step-3-set-up-dial-in-phone-numbers"></a>步骤 3：设置拨入电话号码

拨入电话号码是关联到音频会议网桥的电话号码。 参与者使用这些数字加入组织中用户安排的会议。 在组织中安排会议的用户的会议邀请和"查找本地号码"页面上也包含这些数字。

#### <a name="define-service-phone-numbers-in-your-tenant"></a>在租户中定义服务电话号码

可以使用 New-csHybridTelephoneNumber PowerShell cmdlet 在你的租户中定义可用于通过直接路由将呼叫路由到音频会议服务的服务电话号码。 

  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber <Phone number in E.164 format>
  ```

例如：
  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber "+14250000000"
  ```

#### <a name="assign-the-service-phone-numbers-to-the-audio-conferencing-bridge-of-your-organization"></a>将服务电话号码分配给组织的音频会议网桥

可以使用 Register-csOnlineDialInConferencingServiceNumber PowerShell cmdlet 将服务电话号码分配给组织的音频会议网桥。

  ```PowerShell
  Register-csOnlineDialInConferencingServiceNumber -identity <Telephone number in E.164 format> -BridgeId <Identity of the audio conferencing bridge>
  ```

可以使用 Get-CsOnlineDialInConferencingBridge 查看音频会议网桥的 ID。 例如：

  ```PowerShell
  $b= Get-CsOnlineDialInConferencingBridge
  Register-csOnlineDialInConferencingServiceNumber -identity 14257048060 -BridgeId $b.identity
  ```


### <a name="step-4-define-a-global-voice-routing-policy-to-enable-the-routing-of-outbound-calls-from-meetings"></a>步骤 4：定义全局语音路由策略，以便从会议路由出站呼叫

从组织中用户组织的会议向 PSTN 拨打的出站呼叫的路由由组织的全局语音路由策略定义。 如果组织定义了全局语音路由策略，请验证全局语音路由策略是否允许从组织中用户组织的会议发起的 PSTN 出站呼叫。 如果组织未定义全局语音路由策略，则需要定义一个策略，以便从组织中用户组织的会议中将出站呼叫路由到 PSTN。 请注意，组织的全局语音路由策略也适用于组织中用户对 PSTN 的一对一呼叫。 如果为贵组织的用户启用了对 PSTN 的一对一呼叫，请确保全局语音路由策略满足组织对两种类型的呼叫的需求。 

> [!NOTE]
> Location-Based在 Microsoft 365 政府社区云和 GCC (高级或 DoD) 中不可用。 启用音频会议时，请验证 GCC High 中未启用音频会议用户或 DoD 环境中是否启用了Location-Based路由。

#### <a name="defining-a-global-voice-routing-policy"></a>定义全局语音路由策略

可以通过定义 PSTN 使用情况、语音路由、语音路由策略和分配新的语音路由策略作为组织的全局语音路由策略来定义全局语音路由策略。

以下步骤介绍了如何为组织定义新的全局语音路由策略（不带策略）。 如果组织已定义语音路由策略，请验证以下配置是否不与组织的现有语音路由策略冲突。

若要在 Skype for Business Online 的远程 PowerShell 会话中创建新的 PSTN 使用情况，请使用以下命令：

  ```PowerShell
  Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
  ```

有关详细信息，请参阅[Set-CsOnlinePstnUsage。](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage)

若要创建新的语音路由，请使用以下命令：

  ```PowerShell
  New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz -OnlinePstnUsages "International"
  ```

为组织定义新的语音路由时，请指定在配置直接路由期间为组织定义的一个或多个 PSTN 联机 PSTN 网关。 

号码模式根据呼叫的目标电话号码，指定将通过指定的网关列表路由哪些呼叫。 在以上示例中，对世界上任何目的地的调用都将与语音路由匹配。 如果要限制可以从组织中用户的会议拨打的电话号码，可以更改号码模式，使语音路由仅与允许的目标号码模式匹配。 请注意，如果没有与给定呼叫的目标电话号码的号码模式匹配的语音路由，将不会路由呼叫。

有关详细信息，请参阅[New-CsOnlineVoiceRoute。](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroute)

若要创建新的语音路由策略，请使用以下命令：

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "InternationalVoiceRoutingPolicy" -OnlinePstnUsages "International"
  ```

如果在语音路由策略中定义了多个 PSTN 使用情况，将按照定义的顺序评估这些 PSTN 使用情况。 建议根据与 PSTN 用法关联的语音路由的数量模式，按照最具体、更通用的顺序定义 PSTN 使用情况。 例如，如果定义了 PSTN 使用情况以将呼叫路由到美国，并且定义了另一个 PSTN 使用情况以将呼叫路由到世界上任何其他位置，那么在 PSTN 使用将呼叫路由到世界上任何其他位置之前，应先在语音路由策略中列出美国呼叫的 PSTN 使用情况。

有关详细信息，请参阅[New-CsOnlineVoiceRoutingPolicy。](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy)

若要将新的语音路由分配到组织的全局语音路由策略，请使用以下命令：

  ```PowerShell
  Grant-CsOnlineVoiceRoutingPolicy -PolicyName "InternationalVoiceRoutingPolicy" -Global
  ```

有关详细信息，请参阅[Grant-CsOnlineVoiceRoutingPolicy。](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy)

定义全局语音路由策略后，将针对与全局语音路由策略的 PSTN 用法关联的语音路由，对组织中用户组织的会议进行的任何出站呼叫进行评估。 出站呼叫将按照与拨号电话号码的号码模式匹配的第一个语音路由进行路由。

### <a name="step-5-assign-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses-to-your-users"></a>步骤 5：使用直接路由为用户分配具有 GCC High 或 DoD 许可证的音频会议

若要为用户分配具有直接路由的音频会议，以便 GCC 高或 DoD 许可证，请参阅"向[用户分配许可证"。](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)

### <a name="step-6-optional-see-a-list-of-audio-conferencing-numbers-in-teams"></a>步骤 6： (可选) 查看 Teams 中的音频会议号码列表

若要查看组织的音频会议号码列表，请转到 Microsoft Teams 中的音频会议 [号码列表](see-a-list-of-audio-conferencing-numbers-in-teams.md)。

### <a name="step-7-optional-set-auto-attendant-languages-for-the-audio-conferencing-dial-in-numbers-of-you-organization"></a>步骤 7： (可选) 为贵组织的音频会议拨入号码设置自动助理语言

若要更改组织的音频会议拨入号码的语言，请参阅"在 Microsoft Teams 中为音频会议设置[自动助理语言"。](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)

### <a name="step-8-optional-change-the-settings-of-the-audio-conferencing-bridge-of-your-organization"></a>步骤 8： (可选) 更改组织的音频会议网桥的设置

若要更改组织的音频会议网桥的设置，请参阅"更改音频[会议网桥的设置"。](change-the-settings-for-an-audio-conferencing-bridge.md)

### <a name="step-9-optional-set-the-phone-numbers-included-in-the-meeting-invites-of-the-users-in-your-organization"></a>步骤 9： (可选) 设置组织中用户的会议邀请中包含的电话号码

若要更改用户的会议邀请中包含的电话号码集，请参阅"设置 Microsoft Teams 中的邀请中包含的电话号码["。](set-the-phone-numbers-included-on-invites-in-teams.md)

## <a name="audio-conferencing-capabilities-not-supported-in-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>音频会议功能在具有直接路由的 GCC High 和 DoD 音频会议中不受支持

以下是音频会议功能，对于 GCC High 和 DoD，使用直接路由的音频会议不支持这些功能：

- 使用名称录制的进入和退出通知。 对于具有直接路由的音频会议，进入和退出通知在会议中以音调播放。

- 音频会议出站呼叫限制策略。 用于限制出站呼叫的用户级控件不适用于通过直接路由路由的会议拨出呼叫。

- 禁止对会议特定组织者使用免费电话号码。 限制使用免费电话号码加入组织会议的用户级控制不适用于通过直接路由路由的呼叫。

- 当用户的设置更改时，向用户发送通知电子邮件。 音频会议通知电子邮件不支持使用直接路由进行 GCC High 和 DoD 的音频会议。
