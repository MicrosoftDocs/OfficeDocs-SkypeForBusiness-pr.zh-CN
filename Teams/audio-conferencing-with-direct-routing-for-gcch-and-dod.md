---
title: 带有 GCCH 和 DoD 直接路由的音频会议
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
localization_priority: Normal
description: 了解如何在 GCCH 和 DoD 环境中通过直接路由使用音频会议。
ms.openlocfilehash: 6c1403fedbbb47231780916eb8c7acb8014539e9
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992892"
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
  New-csHybridTelephoneNumber -TelephoneNumber “+14250000000”
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

### <a name="step-4-assign-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses-to-your-users"></a>步骤4：为你的用户分配适用于 GCC 的最高或 DoD 许可证的直接路由的音频会议

若要向你的用户分配适用于适用于 GCC 的适用于 GCC 或 DoD 许可证的直接路由的音频会议，请参阅[在 Office 365 for business 中向用户分配许可证](https://docs.microsoft.com/en-us/office365/admin/subscriptions-and-billing/assign-licenses-to-users)。

### <a name="step-5-optional-see-a-list-of-audio-conferencing-numbers-in-teams"></a>步骤5：（可选）查看团队中的音频会议号码列表

若要查看您的组织的音频会议号码列表，请[参阅 Microsoft 团队中的音频会议号码列表](see-a-list-of-audio-conferencing-numbers-in-teams.md)

### <a name="step-6-optional-set-auto-attendant-languages-for-the-audio-conferencing-dial-in-numbers-of-you-organization"></a>步骤6：（可选）为你的组织的音频会议拨入号码设置自动助理语言

若要更改组织的音频会议拨入号码的语言，请参阅[在 Microsoft 团队中设置音频会议的自动助理语言](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)

### <a name="step-7-optional-change-the-settings-of-the-audio-conferencing-bridge-of-your-organization"></a>步骤7：（可选）更改你的组织的音频会议桥的设置

若要更改组织的音频会议桥的设置，请参阅[更改音频会议网桥的设置](change-the-settings-for-an-audio-conferencing-bridge.md)

### <a name="step-8-optional-set-the-phone-numbers-included-in-the-meeting-invites-of-the-users-in-your-organization"></a>步骤8：（可选）设置你的组织中的用户的会议邀请中包含的电话号码

若要更改用户的会议邀请中包含的电话号码集，请参阅[设置 Microsoft 团队邀请中包含的电话](set-the-phone-numbers-included-on-invites-in-teams.md)号码

## <a name="audio-conferencing-capabilities-not-supported-in-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>音频会议中不支持的音频会议功能，适用于 GCC 高和 DoD 的直接路由

以下是适用于 GCC 高和 DoD 直接路由的音频会议的音频会议功能：

- 使用名称录制进入和退出通知。 对于带有直接路由的音频会议，进入和退出通知将在会议中作为声音播放。

- 音频会议的出站呼叫限制策略。 限制出站呼叫的用户级控件不适用于通过直接路由路由的会议拨出呼叫。

- 禁止会议特定组织者使用免费电话号码。 限制免费号码的使用以限制您的组织的会议的用户级控件不适用于通过直接路由路由的呼叫。

- 在用户的设置更改时向用户发送通知电子邮件。 对于具有适用于 GCC 高和 DoD 的直接路由的音频会议，音频会议通知电子邮件不受支持。
