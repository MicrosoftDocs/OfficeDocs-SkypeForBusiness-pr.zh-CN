---
title: 带有直接路由、GCCH 和 DoD 的音频会议
author: LanaChin
ms.author: v-lanac
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
description: 管理员可了解如何在 GCCH 和 DoD 环境中使用直接路由的音频会议。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 34fcb84ee0e5126188f47a4ccc231c04ffd093b2
ms.sourcegitcommit: 8924cd77923ca321de72edc3fed04425a4b13044
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/24/2020
ms.locfileid: "48262489"
---
# <a name="audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>适用于 GCC High 和 DoD 且含直接路由的音频会议

具有适用于 GCC 高和 DoD 的直接路由的音频会议使参与者能够使用电话设备加入您的 GCC 高或 DoD 组织中的团队会议。 会议参与者可能希望使用电话设备在方案中加入团队会议，例如，当 internet 连接受到限制或用户处于旅途中且无权访问团队时。 参与者可以通过拨入到组织的拨入电话号码或通过将会议拨出到电话设备来选择加入会议。

通过具有适用于 GCC 高和 DoD 的直接路由的音频会议，你的组织使用其自己的号码作为拨入电话号码，并且通过直接路由路由对电话设备的所有拨出会议。 若要启用该服务，组织需要设置直接路由和配置可用作拨入电话号码的电话号码。 使用直接路由的要求与向非 GCC 的高和非 DoD 组织提供的音频会议服务不同，电话拨入电话号码由 Microsoft 提供。

## <a name="deploy-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>通过适用于 GCC 高和 DoD 的直接路由部署音频会议

### <a name="step-1-get-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses"></a>步骤1：使用适用于 GCC 的高或 DoD 许可证的直接路由获得音频会议 

若要在 GCC 高或 DoD 中使用音频会议，你的组织和组织中的用户需要具有分配了直接路由许可证的音频会议。 以下是使用适用于 GCC 高或 DoD 的直接路由启用音频会议所需的许可证。

- GCC 高：音频会议-适用于您的组织的 GCC 高租户许可证和音频会议-适用于您的用户的 GCC 高许可证。

- DoD：针对你的组织和音频会议的 DoD 租户许可证-适用于你的用户的 dod 许可证。

启用服务需要租户许可证和至少一个用户许可证。 不能仅使用租户许可证或仅使用用户许可证启用服务。 若要为你的租户和组织中的用户获取服务许可证，请联系你的帐户团队。

> [!IMPORTANT]
> 在设置电话拨入式电话号码之前，不能通过直接路由为音频会议启用用户。 我们建议您不要向用户分配具有针对 GCC 高或 DoD 许可证的直接路由的音频会议，直到您按照本文所述设置电话拨入式电话号码。

### <a name="step-2-set-up-direct-routing"></a>步骤2：设置直接路由

若要设置直接路由，请参阅以下文章：

- [规划直接路由](direct-routing-plan.md)

- [配置直接路由](direct-routing-configure.md)

> [!NOTE]
> 设置直接路由时，请记住使用特定于 GCC 的高或 DoD 特定的 Fqdn 和在这两个文章中介绍的端口。

### <a name="step-3-set-up-dial-in-phone-numbers"></a>步骤3：设置电话拨入式电话号码

电话拨入电话号码是与您的音频会议网桥相关联的电话号码。 参与者使用这些号码加入您的组织中的用户安排的会议。 这些号码还包括在您的组织中安排会议的用户和 "查找本地号码" 页面上的会议邀请中。

#### <a name="define-service-phone-numbers-in-your-tenant"></a>在租户中定义服务电话号码

你可以使用 csHybridTelephoneNumber PowerShell cmdlet 定义租户中的服务电话号码，这些电话号码可用于通过直接路由将呼叫路由到音频会议服务。 

  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber <Phone number in E.164 format>
  ```

例如：
  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber "+14250000000"
  ```

#### <a name="assign-the-service-phone-numbers-to-the-audio-conferencing-bridge-of-your-organization"></a>将服务电话号码分配给组织的音频会议桥

你可以使用 Set-csonlinedialinconferencingservicenumber PowerShell cmdlet 将服务电话号码分配给你的组织的音频会议桥。

  ```PowerShell
  Register-csOnlineDialInConferencingServiceNumber -identity <Telephone number in E.164 format> -BridgeId <Identity of the audio conferencing bridge>
  ```

你可以使用 Get-csonlinedialinconferencingbridge 查看音频会议桥的 ID。 例如：

  ```PowerShell
  $b= Get-CsOnlineDialInConferencingBridge
  Register-csOnlineDialInConferencingServiceNumber -identity 14257048060 -BridgeId $b.identity
  ```


### <a name="step-4-define-a-global-voice-routing-policy-to-enable-the-routing-of-outbound-calls-from-meetings"></a>步骤4：定义全局语音路由策略以启用来自会议的出站呼叫路由

由组织中的用户组织的会议对 PSTN 发出的出站呼叫的路由由组织的全局语音路由策略定义。 如果您的组织已定义全局语音路由策略，请验证全局语音路由策略是否允许从组织中的用户组织的会议中发起出站呼叫。 如果你的组织未定义全局语音路由策略，你将需要定义一个，以便从组织中的用户组织的会议中将出站呼叫路由到 PSTN。 请注意，您的组织的全局语音路由策略也适用于您的组织中的用户对 PSTN 的一次呼叫。 如果为您的组织中的用户启用了对 PSTN 的一对一调用，请确保全球语音路由策略满足两种类型的通话的组织需求。 

> [!NOTE]
> 基于位置的路由在 Microsoft 365 政府社区云中不可用 (GCC) 高或 DoD 部署。 启用音频会议时，请确认未对 GCC 高或 DoD 环境中的音频会议用户启用基于位置的路由。

#### <a name="defining-a-global-voice-routing-policy"></a>定义全局语音路由策略

全局语音路由策略可以通过定义 PSTN 使用、语音路由、语音路由策略以及将新的 "语音路由策略" 分配为组织的全局语音路由策略来定义。

以下步骤介绍了如何为没有一个组织的组织定义新的全局语音路由策略。 如果你的组织已定义了语音路由策略，请验证以下配置是否与你的组织的现有语音路由策略不冲突。

若要在 Skype for Business Online 的远程 PowerShell 会话中创建新的 PSTN 使用，请使用以下命令：

  ```PowerShell
  Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
  ```

有关详细信息，请参阅 [设置 CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage)。

若要创建新的语音路由，请使用以下命令：

  ```PowerShell
  New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz -OnlinePstnUsages "International"
  ```

为你的组织定义新的语音路由时，请在配置直接路由期间指定已为你的组织定义的一个或多个 PSTN online PSTN 网关。 

数字模式指定哪些调用将通过基于呼叫的目标电话号码的网关指定列表进行路由。 在上述示例中，拨打世界各地的任何目的地都将与语音路线相匹配。 如果您想要限制可从组织中的用户的会议中拨打的电话号码，您可以更改号码模式以使语音路由仅匹配所允许的目标的数字模式。 请注意，如果没有与给定呼叫的目标电话号码的号码模式匹配的语音路线，则不会路由呼叫。

有关其他信息，请参阅 [CsOnlineVoiceRoute](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroute)。

若要创建新的语音路由策略，请使用以下命令：

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "InternationalVoiceRoutingPolicy" -OnlinePstnUsages "International"
  ```

如果在 "语音路由策略" 中定义了多个 PSTN 用法，它们将按定义的顺序进行评估。 根据与 PSTN 用法相关联的语音路由的数字模式，建议以最具体到更通用的顺序定义 PSTN 用法。 例如，如果定义了 PSTN 使用以将呼叫路由到美国，并且另一个 PSTN 使用被定义为将呼叫路由到世界上的任何其他位置，则拨打美国电话的 PSTN 使用应在 "全球" 的 "语音路由策略" 中列出，以将呼叫路由到世界上的任何其他位置。

有关其他信息，请参阅 [CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy)。

若要将新的语音路由分配给组织的全局语音路由策略，请使用以下命令：

  ```PowerShell
  Grant-CsOnlineVoiceRoutingPolicy -PolicyName "InternationalVoiceRoutingPolicy" -Global
  ```

有关其他信息，请参阅 [授权-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy)。

定义全局语音路由策略后，由组织中的用户组织的会议发出的任何出站呼叫均将根据与全局语音路由策略的 PSTN 用法相关联的语音路由进行评估。 出站呼叫将根据与已拨电话号码的号码模式匹配的第一个语音路由进行路由。

### <a name="step-5-assign-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses-to-your-users"></a>步骤5：为你的用户分配适用于 GCC 的最高或 DoD 许可证的直接路由的音频会议

若要向用户分配适用于 GCC 高或 DoD 许可证的直接路由的音频会议，请参阅向 [用户分配许可证](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)。

### <a name="step-6-optional-see-a-list-of-audio-conferencing-numbers-in-teams"></a>步骤6： (可选) 查看团队中的音频会议号码列表

若要查看您的组织的音频会议号码列表，请 [参阅 Microsoft 团队中的音频会议号码列表](see-a-list-of-audio-conferencing-numbers-in-teams.md)。

### <a name="step-7-optional-set-auto-attendant-languages-for-the-audio-conferencing-dial-in-numbers-of-you-organization"></a>步骤7： (可选) 为组织的音频会议拨入号码设置自动助理语言

若要更改组织的音频会议拨入号码的语言，请参阅为 [Microsoft 团队中的音频会议设置自动助理语言](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)。

### <a name="step-8-optional-change-the-settings-of-the-audio-conferencing-bridge-of-your-organization"></a>步骤8： (可选) 更改组织的音频会议桥的设置

若要更改组织的音频会议桥的设置，请参阅 [更改音频会议网桥的设置](change-the-settings-for-an-audio-conferencing-bridge.md)。

### <a name="step-9-optional-set-the-phone-numbers-included-in-the-meeting-invites-of-the-users-in-your-organization"></a>步骤9： (可选) 设置组织中的用户的会议邀请中包含的电话号码

若要更改您的组织中的会议邀请中包含的电话号码集，请参阅 [设置 Microsoft 团队邀请中包含的电话号码](set-the-phone-numbers-included-on-invites-in-teams.md)。

## <a name="audio-conferencing-capabilities-not-supported-in-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>音频会议中不支持的音频会议功能，适用于 GCC 高和 DoD 的直接路由

以下是适用于 GCC 高和 DoD 直接路由的音频会议的音频会议功能：

- 使用名称录制进入和退出通知。 对于带有直接路由的音频会议，进入和退出通知将在会议中作为声音播放。

- 音频会议的出站呼叫限制策略。 限制出站呼叫的用户级控件不适用于通过直接路由路由的会议拨出呼叫。

- 禁止会议特定组织者使用免费电话号码。 限制免费号码的使用以限制您的组织的会议的用户级控件不适用于通过直接路由路由的呼叫。

- 在用户的设置更改时向用户发送通知电子邮件。 对于具有适用于 GCC 高和 DoD 的直接路由的音频会议，音频会议通知电子邮件不受支持。
