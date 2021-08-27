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
ms.localizationpriority: medium
description: 管理员可以了解如何在 GCCH 和 DoD 环境中将音频会议与直接路由一同使用。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4137aaa3157d680d7758e425db1e9d09dcf9e612
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58578426"
---
# <a name="audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>适用于 GCC High 和 DoD 且含直接路由的音频会议

使用直接路由GCC高和 DoD 的音频会议Teams使用电话设备GCC高或 DoD 组织加入 Teams 会议。 在 Internet 连接受限或用户正在路况中且无法访问 Teams 等情况下，会议参与者可能希望使用电话设备加入 Teams。 Teams 参与者可以通过拨入组织的拨入电话号码或让会议拨出到其电话设备来选择加入会议。

借助具有 GCC High 和 DoD 直接路由的音频会议，您的组织使用自己的号码作为拨入电话号码，并且通过直接路由路由到电话设备的所有会议拨出。 若要启用该服务，组织需要设置直接路由并配置可用作拨入电话号码的电话号码。 使用直接路由的要求不同于提供给非 GCC High 和非 DoD 组织的音频会议服务，其中拨入电话号码由 Microsoft 提供。

## <a name="deploy-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>使用直接路由为高和GCC部署音频会议

### <a name="step-1-get-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses"></a>步骤 1：使用直接路由获取音频会议GCC高或 DoD 许可证 

若要在高GCC DoD 中使用音频会议，您的组织和组织中用户需要分配有具有直接路由许可证的音频会议。 以下是使用直接路由为高或 doD 启用音频GCC许可证。

- GCC高：音频会议 - GCC高租户许可证和音频会议 - GCC高许可证。

- DoD：音频会议 - 组织的 DoD 租户许可证和音频会议 - 用户的 DoD 许可证。

启用该服务需要租户许可证和至少一个用户许可证。 不能仅启用具有租户许可证或仅具有用户许可证的服务。 若要获取租户和组织中用户的服务许可证，请联系帐户团队。

> [!IMPORTANT]
> 在设置拨入电话号码之前，无法通过直接路由为用户启用音频会议。 建议在按本文所述设置拨入电话号码之前，不要向用户分配具有 GCC High 或 DoD 许可证的直接路由音频会议。  未能遵循本指南可能会导致拨号盘在客户端中完全Teams丢失。

### <a name="step-2-set-up-direct-routing"></a>步骤 2：设置直接路由

若要设置直接路由，请参阅以下文章：

- [规划直接路由](direct-routing-plan.md)

- [配置直接路由](direct-routing-configure.md)

> [!NOTE]
> 设置直接路由时，请记得GCC两篇文章中所述的特定于 DoD 或 DoD 的 FQD 和端口。

### <a name="step-3-set-up-dial-in-phone-numbers"></a>步骤 3：设置拨入电话号码

拨入电话号码是关联到音频会议网桥的电话号码。 参与者使用这些数字加入组织中用户安排的会议。 在组织中安排会议的用户的会议邀请和"查找本地号码"页面上也包含这些数字。

#### <a name="define-service-phone-numbers-in-your-tenant"></a>在租户中定义服务电话号码

可以使用 New-csHybridTelephoneNumber PowerShell cmdlet 在租户中定义可用于通过直接路由将呼叫路由到音频会议服务的服务电话号码。 

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

从组织中用户组织的会议向 PSTN 拨打的出站呼叫的路由由组织的全局语音路由策略定义。 如果你的组织定义了全局语音路由策略，请验证全局语音路由策略是否允许对 PSTN 的出站呼叫，这些呼叫应该从组织中用户组织的会议中发起。 如果组织未定义全局语音路由策略，则需要定义一个策略，以便从组织中用户组织的会议中将出站呼叫路由到 PSTN。 请注意，组织的全局语音路由策略也适用于组织中用户对 PSTN 的一对一呼叫。 如果为贵组织的用户启用了对 PSTN 的一对一呼叫，请确保全局语音路由策略满足组织在这两种类型的呼叫的需求。 

> [!NOTE]
> Location-Based高级或 DoD 部署Microsoft 365 政府社区云 (GCC) 路由不可用。 启用音频会议时，请验证"高"GCC或 DoD 环境中没有为音频会议用户启用Location-Based路由。

#### <a name="defining-a-global-voice-routing-policy"></a>定义全局语音路由策略

可以通过定义 PSTN 使用情况、语音路由、语音路由策略，并将新的语音路由策略分配为组织的全局语音路由策略来定义全局语音路由策略。

以下步骤介绍如何为没有全局语音路由策略的组织定义新的全局语音路由策略。 如果组织已定义语音路由策略，请验证以下配置是否不与组织的现有语音路由策略冲突。

若要在 Skype for Business Online 的远程 PowerShell 会话中创建新的 PSTN 使用情况，请使用以下命令：

  ```PowerShell
  Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
  ```

有关其他信息，请参阅[Set-CsOnlinePstnUsage。](/powershell/module/skype/set-csonlinepstnusage)

若要创建新的语音路由，请使用以下命令：

  ```PowerShell
  New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz -OnlinePstnUsages "International"
  ```

为组织定义新的语音路由时，请指定在配置直接路由期间为组织定义的一个或多个 PSTN 联机 PSTN 网关。 

号码模式根据呼叫的目标电话号码指定将通过指定的网关列表路由哪些呼叫。 在上例中，对世界上任何目的地的调用都将与语音路由匹配。 如果要限制可以从组织中用户的会议拨打的电话号码，可以更改号码模式，使语音路由仅匹配允许的目标号码模式。 请注意，如果没有与给定呼叫的目标电话号码号码模式匹配的语音路由，将不会路由呼叫。

有关其他信息，请参阅 [New-CsOnlineVoiceRoute](/powershell/module/skype/new-csonlinevoiceroute)。

若要创建新的语音路由策略，请使用以下命令：

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "InternationalVoiceRoutingPolicy" -OnlinePstnUsages "International"
  ```

如果在语音路由策略中定义了多个 PSTN 使用情况，将按照定义的顺序评估这些 PSTN 使用情况。 建议根据与 PSTN 使用相关联的语音路由的数量模式，按照最具体到更通用的顺序定义 PSTN 使用情况。 例如，如果定义了 PSTN 使用情况以将呼叫路由到美国，并且定义了另一个 PSTN 使用情况以将呼叫路由到世界上任何其他位置，则呼叫到美国的 PSTN 使用情况应列在语音路由策略中，然后 PSTN 使用将呼叫路由到世界上任何其他位置。

有关其他信息，请参阅 [New-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/new-csonlinevoiceroutingpolicy)。

若要将新的语音路由分配到组织的全局语音路由策略，请使用以下命令：

  ```PowerShell
  Grant-CsOnlineVoiceRoutingPolicy -PolicyName "InternationalVoiceRoutingPolicy" -Global
  ```

有关其他信息，请参阅 [Grant-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/grant-csonlinevoiceroutingpolicy)。

定义全局语音路由策略后，将针对与全局语音路由策略的 PSTN 使用情况关联的语音路由评估组织中用户组织的会议发出的任何出站呼叫。 出站呼叫将按照与已拨入电话号码的号码模式匹配的第一个语音路由进行路由。

### <a name="step-5-assign-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses-to-your-users"></a>步骤 5：为用户分配具有直接路由GCC高或 DoD 许可证的音频会议

若要为用户分配具有直接路由的音频GCC高或 DoD 许可证，请参阅[向用户分配许可证](/microsoft-365/admin/manage/assign-licenses-to-users)。

### <a name="step-6-optional-see-a-list-of-audio-conferencing-numbers-in-teams"></a>步骤 6： (可选) 查看音频会议号码列表Teams

若要查看贵组织的音频会议号码列表，请转到在"会议"中查看音频会议[Microsoft Teams。](see-a-list-of-audio-conferencing-numbers-in-teams.md)

### <a name="step-7-optional-set-auto-attendant-languages-for-the-audio-conferencing-dial-in-numbers-of-you-organization"></a>步骤 7： (可选) 为贵组织的音频会议拨入号码设置自动助理语言

若要更改贵组织的音频会议拨入号码的语言，请参阅在 Microsoft Teams 中为音频会议[设置自动助理Microsoft Teams。](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)

### <a name="step-8-optional-change-the-settings-of-the-audio-conferencing-bridge-of-your-organization"></a>步骤 8： (可选) 更改组织的音频会议网桥的设置

若要更改组织的音频会议网桥的设置，请参阅更改音频 [会议网桥的设置](change-the-settings-for-an-audio-conferencing-bridge.md)。

### <a name="step-9-optional-set-the-phone-numbers-included-in-the-meeting-invites-of-the-users-in-your-organization"></a>步骤 9： (可选) 设置组织中用户的会议邀请中包含的电话号码

若要更改用户的会议邀请中包含的电话号码集，您的组织是您的组织，请参阅设置邀请中包含的电话号码[Microsoft Teams。](set-the-phone-numbers-included-on-invites-in-teams.md)

## <a name="audio-conferencing-capabilities-not-supported-in-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>音频会议功能在音频会议中不受支持，使用直接路由GCC高和 DoD

以下是音频会议功能，对于高和 DoD，使用直接路由GCC音频会议功能：

- 使用名称录制的进入和退出通知。 对于具有直接路由的音频会议，进入和退出通知在会议以音调播放。

- 禁止对会议特定组织者使用免费号码。 限制使用免费号码加入组织会议的用户级控件不适用于通过直接路由路由的呼叫。

- 当用户的设置更改时向用户发送通知电子邮件。 音频会议通知电子邮件不支持通过直接路由进行音频会议，GCC高和 DoD。
