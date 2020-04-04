---
title: Office 365 中的音频会议
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: conceptual
ms.assetid: a5a696c3-d321-4e61-9aad-e3a87041196e
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
- M365-collaboration
search.appverid: MET150
audience: admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- ms.teamsadmincenter.audioconferencing.overview
- seo-marvel-mar2020
description: 了解 Office 365 中的音频会议，包括成本、可用性和专用电话号码。
ms.openlocfilehash: 5fef21489bbbceb490a2b97d70ee9dbafd2a791c
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/03/2020
ms.locfileid: "43139011"
---
# <a name="audio-conferencing-in-office-365"></a>Office 365 中的音频会议
Office 365 中的音频会议支持用户从手机呼入会议。 音频会议最多允许 250 名电话与会者。

## <a name="what-is-audio-conferencing"></a>什么是音频会议？
对于因在旅途中而无法使用其笔记本电脑或移动设备上的 Skype for Business 或 Microsoft Teams 应用参与会议的用户来说，呼入（或拨入）会议非常有用。 但还有其他一些情况，使用手机参加 Skype for Business 或 Microsoft Teams 会议可能比在计算机上使用应用更好：
  
- Internet 连接受限。
- 会议只有音频。
- 用户尝试加入 Skype for Business 会议，但是失败。
- 拨入时通话质量更佳。
- 用户可以使用蓝牙设备“免提”加入会议。
- 用户发现对于他们的情况而言，这样更加简便。

你只需为打算安排或主持会议的人设置音频会议。 拨入会议与会者不需要分配给他们或其他安装程序的许可证。

加入会议后，与会者还可以拨出并邀请其他呼叫者加入 Skype for Business 或 Microsoft Teams 会议。 请参阅[从 Teams 会议拨出，以便其他人可以加入](dialing-out-from-a-teams-meeting-so-other-people-can-join-it.md)或[从 Skype for Business 会议拨出，以便其他人可以加入](/SkypeForBusiness/audio-conferencing-in-office-365/dialing-out-from-a-meeting-so-other-people-can-join-it)。

## <a name="what-does-it-cost"></a>费用是多少？
有关定价信息，请参阅[音频会议定价](https://products.office.com/microsoft-teams/online-meeting-solutions#customerstoryregion2)。

## <a name="where-is-it-available"></a>它在哪些国家/地区可用？
借助音频会议，你的用户可以使用收费和免费电话号码拨入会议。 如果组织已启用音频会议，收费（服务）号码会自动作为共享音频会议号码分配给组织。 在其他城市中，可以将专用的收费和免费号码分配给组织。

免费电话号码（服务号码）仅适用于某些国家/地区。 若要了解你所在国家或地区的可用功能，请参阅[音频会议和通话套餐的国家/地区可用情况](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)。

在决定对组织使用音频会议后，你需要为组织中将要计划/主持音频会议的每个人都购买一个**音频会议**许可证。

## <a name="how-do-conferencing-bridges-work"></a>会议网桥的工作原理是什么？
为 Skype for Business 或 Microsoft Teams 设置音频会议时，你将看到音频会议网桥。 会议网桥可以包含一个或多个电话号码。 你设置的电话号码将包括在 Skype for Business 和 Microsoft Teams 应用的会议邀请中。 你可以[更改会议网桥上的电话号码](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)，也可以[更改其他音频会议网桥设置](change-the-settings-for-an-audio-conferencing-bridge.md)。 
  
音频会议网桥负责应答使用电话拨入会议的用户的呼叫。 它通过来自自动助理的语音提示应答呼叫者，然后根据你的设置，会议网桥可以播放通知并让呼叫者录制其姓名。 在 **Microsoft 网桥设置**中，你可以更改有关会议通知和会议加入体验的设置，并设置会议组织者在 [Microsoft Teams](set-the-pin-length-for-audio-conferencing-meetings-in-teams.md) 或 [Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-pin-length-for-audio-conferencing-meetings) 中使用的 PIN 的长度。 如果会议组织者无法使用 Skype for Business 或 Microsoft Teams 应用加入会议，则会使用 PIN 来启动会议。

## <a name="dial-in-phone-numbers-set-on-an-audio-conferencing-bridge"></a>在音频会议网桥上设置的拨入电话号码
可分配到会议网桥的电音频会议电话号码包括两种类型：**共享**和**专用**。 这两种类型的号码都可以供任何呼叫者加入贵组织中召开的音频会议。
  
 **专用电话号码** 是只有你组织内的用户才可以使用的电话号码。 你可以更改当有人呼入其中的某个号码时使用的语言。 为此，你将需要获得一个服务电话号码。
  
 **共享电话号码** 是可以与其他 Office 365 组织共享的电话号码。你无法更改当有人呼入其中的某个号码时使用的语言。
  
虽然会议邀请中只包括分配给组织者的默认音频会议号码，但是呼叫者可以使用分配给你的会议网桥的任一电话号码加入会议。 使用每个会议邀请中包含的" **查找本地号码**"链接，可以找到可用于加入会议的电话号码列表。

有关详细信息，请参阅 [Microsoft Teams 中用于音频会议的电话号码](phone-numbers-for-audio-conferencing-in-teams.md)或 [Skype for Business Online 中用于音频会议的电话号码](/SkypeForBusiness/audio-conferencing-in-office-365/phone-numbers-for-audio-conferencing)。
  
## <a name="automatically-assigned-audio-conferencing-phone-numbers"></a>自动分配的音频会议电话号码
组织启用音频会议后，系统将自动向组织分配共享音频会议电话号码。 分配电话号码时，电话号码会作为默认电话号码分配给会议网桥。 作为网桥默认号码分配的电话号码来自组织所在的国家/地区。
  
> [!NOTE]
> 你可以登录到 **Microsoft 365 管理中心**，然后在“**组织资料**”下面查找，以确定贵组织所在的国家或地区位置。 
  
> [!CAUTION]
> 由于委内瑞拉、印度尼西亚和阿联酋 (UAE) 限制收费电话号码的使用，因此系统不会自动向这些国家/地区的组织分配音频会议收费号码。 这些地点可使用的免费号码取决于可用库存。 
  
若要查看支持给组织自动分配电话号码的国家/地区列表，请参阅 [音频会议和通话套餐所支持的国家/地区](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)。
  
## <a name="how-do-you-get-dedicated-phone-numbers"></a>如何获得专用电话号码？
专用音频会议电话号码是你可以获取并随后分配给组织的服务号码。 可通过以下三种方式之一获得专用的会议网桥收费和免费电话号码：

- **使用 Skype for Business 管理中心。** 对于某些国家/地区，你可以使用 Skype for Business 管理中心获取会议网桥号码。 参见[获取服务电话号码](/microsoftteams/getting-service-phone-numbers)。
    
- **转网现有的号码。** 您可以将当前服务提供商或电话运营商提供的现有号码转网或转移到 Office 365。 如需获取有助于执行此操作的详细信息，请参阅[将电话号码转接到 Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) 或[管理你的组织的电话号码](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。  
  
- **使用新号码的请求表单。** 有时（具体取决于你所在的国家/地区），你无法使用 Skype for Business 管理中心获取新电话号码，或你需要特定的电话号码或区号。 如果是这样，则需下载表单并将其发回给我们。 有关详细信息，请参阅[管理你的组织的电话号码](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。

## <a name="how-do-you-set-it-up"></a>如何进行设置？
在决定为你的用户设置音频会议后，请参阅[设置 Microsoft Teams 的音频会议](set-up-audio-conferencing-in-teams.md)或[设置 Skype for Business Online 的音频会议](/SkypeForBusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)，了解可遵循的操作步骤。

## <a name="related-topics"></a>相关主题

[设置 Skype for Business Online](/SkypeForBusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)
  
[Microsoft Teams 中用于音频会议的电话号码](phone-numbers-for-audio-conferencing-in-teams.md) 

[Skype for Business Online 中用于音频会议的电话号码](/SkypeForBusiness/audio-conferencing-in-office-365/phone-numbers-for-audio-conferencing)
