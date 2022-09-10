---
title: Microsoft 365 中的音频会议
ms.author: heidip
author: MicrosoftHeidi
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
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- ms.teamsadmincenter.audioconferencing.overview
- seo-marvel-apr2020
description: 了解 Microsoft 365 中的音频会议如何允许用户通过手机呼叫会议。
ms.openlocfilehash: 1ac2842d219648c5a5deef0d687698cd7b5544dd
ms.sourcegitcommit: 5abfb6f1abe10b6d32cf6eb97a890cf3138ed0e6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2022
ms.locfileid: "67641923"
---
# <a name="audio-conferencing-in-microsoft-365"></a>Microsoft 365 中的音频会议

Microsoft 365 中的音频会议使用户能够通过手机呼叫会议。 音频会议最多允许 1000 名电话与会者。

## <a name="what-is-audio-conferencing"></a>什么是音频会议？

呼叫 (拨入会议) 对在路上且无法在笔记本电脑或移动设备上使用 Microsoft Teams 应用参加会议的用户非常有用。 但是，在其他情况下，使用手机参加 Teams 会议比在计算机上使用应用更好：
  
- Internet 连接受限。
- 会议只有音频。
- 此人试图加入 Teams 会议，但失败。
- 拨入时通话质量更佳。
- 用户可以使用蓝牙设备“免提”加入会议。
- 用户发现对于他们的情况而言，这样更加简便。

你只需为打算安排或主持会议的人设置音频会议。 拨入会议与会者不需要分配给他们或其他安装程序的许可证。

与会者加入会议后，还可以拨打电话并邀请其他呼叫者参加 Teams 会议。
请参阅 [Teams 会议中的拨号，以便其他人可以加入会议](dialing-out-from-a-teams-meeting-so-other-people-can-join-it.md) 以获取详细信息。

## <a name="what-does-it-cost"></a>费用是多少？

有关定价信息，请参阅[音频会议定价](https://go.microsoft.com/fwlink/?linkid=799762&clcid=0x409)。

## <a name="where-is-it-available"></a>它在哪些国家/地区可用？

借助音频会议，你的用户可以使用收费和免费电话号码拨入会议。 如果组织已启用音频会议，收费（服务）号码会自动作为共享音频会议号码分配给组织。 在其他城市中，可以将专用的收费和免费号码分配给组织。

免费电话号码（服务号码）仅适用于某些国家/地区。 若要了解你所在国家或地区的可用功能，请参阅[音频会议和通话套餐的国家/地区可用情况](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)。

在决定对组织使用音频会议后，你需要为组织中将要计划/主持音频会议的每个人都购买一个 **音频会议** 许可证。

## <a name="how-do-conferencing-bridges-work"></a>会议网桥的工作原理是什么？

为 Teams 设置音频会议时，你将获得音频会议网桥。 会议网桥可以包含一个或多个电话号码。 设置的电话号码将包含在 Teams 应用的会议邀请中。 你可以[更改会议网桥上的电话号码](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)，也可以[更改其他音频会议网桥设置](change-the-settings-for-an-audio-conferencing-bridge.md)。

音频会议网桥负责应答使用电话拨入会议的用户的呼叫。 它通过来自自动助理的语音提示应答呼叫者，然后根据你的设置，会议网桥可以播放通知并让呼叫者录制其姓名。 **Microsoft 网桥设置** 允许您更改会议通知和会议加入体验的设置，并设置 [Microsoft Teams](set-the-pin-length-for-audio-conferencing-meetings-in-teams.md) 中会议组织者使用的 PIN 的长度。 如果会议组织者无法使用 Teams 应用加入会议，则使用 PIN 启动会议。

## <a name="dial-in-phone-numbers-set-on-an-audio-conferencing-bridge"></a>在音频会议网桥上设置的拨入电话号码

可分配到会议网桥的电音频会议电话号码包括两种类型：**共享** 和 **专用**。 这两种类型的号码都可以供任何呼叫者加入贵组织中召开的音频会议。
  
 **专用电话号码** 是只有你组织内的用户才可以使用的电话号码。 你可以更改当有人呼入其中的某个号码时使用的语言。 为此，你将需要获得一个服务电话号码。
  
 **共享电话号码** 是可与其他 Microsoft 365 共享的电话号码。 你无法更改当有人呼入其中的某个号码时使用的语言。
  
虽然会议邀请中只包括分配给组织者的默认音频会议号码，但是呼叫者可以使用分配给你的会议网桥的任一电话号码加入会议。 使用每个会议邀请中包含的" **查找本地号码**"链接，可以找到可用于加入会议的电话号码列表。

有关详细信息，请参阅 [Microsoft Teams 中音频会议的电话号码](phone-numbers-for-audio-conferencing-in-teams.md) 。

## <a name="automatically-assigned-audio-conferencing-phone-numbers"></a>自动分配的音频会议电话号码

组织启用音频会议后，系统将自动向组织分配共享音频会议电话号码。 分配电话号码时，电话号码会作为默认电话号码分配给会议网桥。 作为网桥默认号码分配的电话号码来自组织所在的国家/地区。

> [!NOTE]
> 你可以登录到 **Microsoft 365 管理中心**，然后在“**组织资料**”下面查找，以确定贵组织所在的国家或地区位置。

> [!CAUTION]
> 由于委内瑞拉、印度尼西亚和阿联酋 (UAE) 限制收费电话号码的使用，因此系统不会自动向这些国家/地区的组织分配音频会议收费号码。 这些地点可使用的免费号码取决于可用库存。

若要查看支持给组织自动分配电话号码的国家/地区列表，请参阅 [音频会议和通话套餐所支持的国家/地区](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)。

## <a name="how-do-you-get-dedicated-phone-numbers"></a>如何获得专用电话号码？

专用音频会议电话号码是你可以获取并随后分配给组织的服务号码。 可通过以下三种方式之一获得专用的会议网桥收费和免费电话号码：

- **使用 Teams 管理中心。** 对于某些国家/地区，可以使用 Teams 管理中心获取会议网桥的号码。 参见[获取服务电话号码](./getting-service-phone-numbers.md)。

- **转网现有的号码。** 可以将现有号码从当前服务提供商或电话运营商移植或传输到 Microsoft 365。 如需获取有助于执行此操作的详细信息，请参阅[将电话号码转接到 Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) 或[管理你的组织的电话号码](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。  
  
- **使用新号码的请求表单。** 有时 (取决于你的国家/地区) 你将无法使用 Teams 管理中心获取新的电话号码，或者需要特定的电话号码或区号。 如果是这样，则需要下载表单并将其发送回我们。 有关详细信息，请参阅[管理你的组织的电话号码](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。

## <a name="how-do-you-set-it-up"></a>如何进行设置？

决定为用户设置音频会议后，请参阅 [为 Microsoft Teams 设置音频会议](set-up-audio-conferencing-in-teams.md) ，了解需要执行的步骤。

## <a name="related-topics"></a>相关主题

[Microsoft Teams 中用于音频会议的电话号码](phone-numbers-for-audio-conferencing-in-teams.md)
