---
title: 具有直接路由、GCCH 和 DoD 的音频会议
author: MicrosoftHeidi
ms.author: heidip
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
- Microsoft Teams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 管理员可以了解如何在 GCCH 和 DoD 环境中将音频会议与直接路由配合使用。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bd467b9da8d296c21d4a0405d651bbaa6b001fd3
ms.sourcegitcommit: 5abfb6f1abe10b6d32cf6eb97a890cf3138ed0e6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2022
ms.locfileid: "67641773"
---
# <a name="audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>适用于 GCC High 和 DoD 且含直接路由的音频会议

使用 GCC High 和 DoD 的直接路由的音频会议使参与者能够使用电话设备加入 GCC High 或 DoD 组织中的 Teams 会议。 在 Internet 连接受限或用户在路上且无法访问 Teams 的情况下，会议参与者可能更愿意使用电话设备加入 Teams 会议。 参与者可以选择通过拨入组织的拨入电话号码或让会议拨出到其电话设备来加入会议。

使用适用于 GCC High 和 DoD 的直接路由的音频会议，组织使用自己的号码作为拨入电话号码，所有电话设备的会议拨号都通过直接路由路由。 若要启用该服务，组织需要设置直接路由并配置可用作拨入电话号码的电话号码。 使用直接路由的要求不同于向 Microsoft 提供拨入电话号码的非 GCC High 和非 DoD 组织提供的音频会议服务。

## <a name="deploy-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>使用 GCC High 和 DoD 的直接路由部署音频会议

### <a name="step-1-get-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses"></a>步骤 1：使用 GCC High 或 DoD 许可证的直接路由获取音频会议

若要在 GCC High 或 DoD 中使用音频会议，组织和组织中的用户需要分配有直接路由许可证的音频会议。 下面是使用 GCC High 或 DoD 的直接路由启用音频会议所需的许可证。

- GCC High：音频会议 - 组织和音频会议的 GCC 高租户许可证 - 面向用户的 GCC 高许可证。

- DoD：音频会议 - 组织的 DoD 租户许可证和音频会议 - 用户的 DoD 许可证。

启用服务需要租户许可证和至少一个用户许可证。 不能仅使用租户许可证或仅具有用户许可证来启用该服务。 若要获取租户和组织中用户的服务许可证，请联系你的帐户团队。

> [!IMPORTANT]
> 在设置拨入电话号码之前，无法为具有直接路由的音频会议启用用户。 建议在设置电话拨入电话号码之前，不要为用户分配具有 GCC High 或 DoD 许可证的直接路由的音频会议。  未能遵循此指南可能导致拨号盘在 Teams 客户端中完全缺失。

### <a name="step-2-set-up-direct-routing"></a>步骤 2：设置直接路由

若要设置直接路由，请参阅以下文章：

- [规划直接路由](direct-routing-plan.md)

- [配置直接路由](direct-routing-configure.md)

> [!NOTE]
> 设置直接路由时，请记住使用 GCC High 或特定于 DoD 的 FQDN 以及这两篇文章中所述的端口。

### <a name="step-3-set-up-dial-in-phone-numbers"></a>步骤 3：设置拨入电话号码

拨入电话号码是与音频会议网桥关联的电话号码。 参与者使用这些数字加入组织中用户安排的会议。 这些数字还包含在组织中安排会议的用户的会议邀请中，以及“查找本地号码”页上。

#### <a name="define-service-phone-numbers-in-your-tenant"></a>在租户中定义服务电话号码

可以使用 New-csHybridTelephoneNumber PowerShell cmdlet 在租户中定义服务电话号码，这些电话号码可用于通过直接路由将呼叫路由到音频会议服务。

  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber <Phone number in E.164 format>
  ```

例如：

  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber "+14250000000"
  ```

#### <a name="assign-the-service-phone-numbers-to-the-audio-conferencing-bridge-of-your-organization"></a>将服务电话号码分配到组织的音频会议网桥

可以使用 Register-csOnlineDialInConferencingServiceNumber PowerShell cmdlet 将服务电话号码分配到组织的音频会议网桥。

  ```PowerShell
  Register-csOnlineDialInConferencingServiceNumber -identity <Telephone number in E.164 format> -BridgeId <Identity of the audio conferencing bridge>
  ```

可以使用 Get-CsOnlineDialInConferencingBridge 查看音频会议桥的 ID。 例如：

  ```PowerShell
  $b= Get-CsOnlineDialInConferencingBridge
  Register-csOnlineDialInConferencingServiceNumber -identity 14257048060 -BridgeId $b.identity
  ```

### <a name="step-4-define-a-global-voice-routing-policy-to-enable-the-routing-of-outbound-calls-from-meetings"></a>步骤 4：定义全局语音路由策略，以启用来自会议的出站呼叫的路由

组织中用户组织的会议向 PSTN 发出的出站呼叫路由由组织的全局语音路由策略定义。 如果组织定义了全局语音路由策略，请验证全局语音路由策略是否允许从组织中用户组织的会议启动对 PSTN 的出站呼叫。 如果组织未定义全局语音路由策略，则需要定义一个策略，以便从组织中用户组织的会议中启用到 PSTN 的出站呼叫路由。 请注意，组织的全局语音路由策略也适用于组织中用户对 PSTN 进行的一对一调用。 如果为组织中的用户启用了对 PSTN 的一对一调用，请确保全局语音路由策略满足组织对这两种类型的呼叫的需求。

> [!NOTE]
> Location-Based路由在 Microsoft 365 政府社区云 (GCC) 高部署或 DoD 部署中不可用。 启用音频会议时，请验证 GCC High 或 DoD 环境中没有为音频会议用户启用Location-Based路由。

#### <a name="defining-a-global-voice-routing-policy"></a>定义全局语音路由策略

可以通过定义 PSTN 使用情况、语音路由、语音路由策略以及将新语音路由策略分配为组织的全局语音路由策略来定义全局语音路由策略。

以下步骤介绍如何为没有全局语音路由策略的组织定义新的全局语音路由策略。 如果组织已定义语音路由策略，请验证以下配置是否与组织的现有语音路由策略不冲突。

若要在 Teams 中的远程 PowerShell 会话中创建新的 PSTN 使用情况，请使用以下命令：

  ```PowerShell
  Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
  ```

有关其他信息，请参阅 [Set-CsOnlinePstnUsage](/powershell/module/skype/set-csonlinepstnusage)。

若要创建新的语音路由，请使用以下命令：

  ```PowerShell
  New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz -OnlinePstnUsages "International"
  ```

为组织定义新语音路由时，请指定在配置直接路由期间为组织定义的一个或多个 PSTN 联机 PSTN 网关。

号码模式指定哪些呼叫将基于呼叫的目标电话号码通过指定的网关列表路由。 在上面的示例中，对世界上任何目标的调用将匹配语音路由。 如果要限制可从组织中用户会议拨号的电话号码，可以更改号码模式，使语音路由仅与允许的目标号码模式匹配。 请注意，如果没有与给定呼叫的目标电话号码的号码模式匹配的语音路由，则不会路由呼叫。

有关其他信息，请参阅 [New-CsOnlineVoiceRoute](/powershell/module/skype/new-csonlinevoiceroute)。

若要创建新的语音路由策略，请使用以下命令：

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "InternationalVoiceRoutingPolicy" -OnlinePstnUsages "International"
  ```

如果在语音路由策略中定义了多个 PSTN 用法，则将按定义它们的顺序评估这些用法。 建议根据与 PSTN 使用情况关联的语音路由的数量模式，根据最具体的顺序定义 PSTN 使用情况。 例如，如果定义了 PSTN 使用率来将呼叫路由到美国，并且定义了另一个 PSTN 用法来将呼叫路由到世界上任何其他位置，则对美国的调用的 PSTN 用法应在 PSTN 使用率之前列在语音路由策略中，以便将呼叫路由到世界上任何其他位置。

有关其他信息，请参阅 [New-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/new-csonlinevoiceroutingpolicy)。

若要将新语音路由分配到组织的全局语音路由策略，请使用以下命令：

  ```PowerShell
  Grant-CsOnlineVoiceRoutingPolicy -PolicyName "InternationalVoiceRoutingPolicy" -Global
  ```

有关其他信息，请参阅 [Grant-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/grant-csonlinevoiceroutingpolicy)。

定义全局语音路由策略后，将根据与全局语音路由策略的 PSTN 使用情况相关联的语音路由，评估组织中用户组织的会议发出的任何出站呼叫。 出站呼叫将根据第一个与拨号电话号码的号码模式匹配的语音路由进行路由。

### <a name="step-5-assign-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses-to-your-users"></a>步骤 5：为用户分配具有 GCC High 或 DoD 许可证的直接路由的音频会议

若要为用户分配具有 GCC High 或 DoD 许可证的直接路由的音频会议，请参阅 [向用户分配许可证](/microsoft-365/admin/manage/assign-licenses-to-users)。

### <a name="step-6-optional-see-a-list-of-audio-conferencing-numbers-in-teams"></a>步骤 6： (可选) 查看 Teams 中的音频会议号码列表

若要查看组织的音频会议号码列表，请转到 [Microsoft Teams 中的音频会议号码列表](see-a-list-of-audio-conferencing-numbers-in-teams.md)。

### <a name="step-7-optional-set-auto-attendant-languages-for-the-audio-conferencing-dial-in-numbers-of-you-organization"></a>步骤 7： (可选) 为组织音频会议拨入号码设置自动助理语言

若要更改组织的音频会议拨入号码的语言，请参阅 [Microsoft Teams 中的音频会议设置自动助理语言](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)。

### <a name="step-8-optional-change-the-settings-of-the-audio-conferencing-bridge-of-your-organization"></a>步骤 8： (可选) 更改组织音频会议网桥的设置

若要更改组织的音频会议网桥的设置，请 [参阅更改音频会议网桥的设置](change-the-settings-for-an-audio-conferencing-bridge.md)。

### <a name="step-9-optional-set-the-phone-numbers-included-in-the-meeting-invites-of-the-users-in-your-organization"></a>步骤 9： (可选) 设置组织中用户的会议邀请中包含的电话号码

若要更改用户会议邀请中包含的电话号码集是你的组织，请参阅 [设置 Microsoft Teams 中邀请中包含的电话号码](set-the-phone-numbers-included-on-invites-in-teams.md)。

## <a name="audio-conferencing-capabilities-not-supported-in-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>音频会议中不支持使用 GCC High 和 DoD 的直接路由的音频会议功能

下面是音频会议中不支持的音频会议功能，以及 GCC High 和 DoD 的直接路由：

- 使用名称录制的入口和退出通知。 对于具有直接路由的音频会议，在会议中将输入和退出通知作为音调播放。

- 禁用特定于会议组织者的免费号码。 限制使用免费号码加入组织会议的用户级控件不适用于通过直接路由路由的呼叫。

- 当用户的设置发生更改时，向用户发送通知电子邮件。 音频会议通知电子邮件不支持通过直接路由进行 GCC High 和 DoD 的音频会议。
