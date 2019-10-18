---
title: 为用户设置“致电我”功能
author: LanaChin
ms.author: v-lanac
ms.reviewer: macai, phedry
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: 了解如何在团队中设置 "呼叫我" 功能，以便用户可以在使用其计算机音频的情况下通过电话加入音频部分。
localization_priority: Normal
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8bd9ca9b73d3d2e60b707d0f40ebb1797d4e1a00
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2019
ms.locfileid: "37571542"
---
# <a name="set-up-the-call-me-feature-for-your-users"></a>为用户设置“致电我”功能

在 Microsoft 团队中，"**呼叫我**" 功能为用户提供了一种通过电话加入会议音频部分的方式。 这在可能无法使用计算机音频的情况下很方便。 用户通过其手机或土地线以及会议&mdash;的内容部分（如另一个会议参与者共享他们的屏幕或通过其计算机播放视频&mdash;）获取会议的音频部分。

## <a name="the-user-experience"></a>用户体验

### <a name="join-a-meeting-by-using-phone-for-audio"></a>通过使用手机 for 音频加入会议

单击 "**加入**" 加入会议，然后单击 "**选择您的音频和视频设置**" 屏幕上的 "**电话音频**"。 在此，用户可以进行会议呼叫并加入会议或手动拨入会议。

![电话音频选项的屏幕截图](media/set-up-the-call-me-feature-for-your-users-phone-audio.png)

**允许团队会议通话**

在 "**使用电话语音通话**" 屏幕上，用户输入其电话号码，然后单击 "**呼叫我**"。 会议将调用用户并将其加入会议。

!["使用电话语音电话" 屏幕上的 "呼叫我" 选项的屏幕截图](media/set-up-the-call-me-feature-for-your-users-call-me.png)

**手动拨入**

加入的另一种方法是直接拨入会议。 在 "**使用电话语音音频**" 屏幕上，单击 "**手动拨入**" 以获取用于拨入会议的电话号码列表。

![手动拨入选项的屏幕截图](media/set-up-the-call-me-feature-for-your-users-dial-in.png)

### <a name="get-a-call-back-when-something-goes-wrong-with-audio-during-a-meeting"></a>在会议期间有音频出现问题时，您可以取回来电

如果用户在会议期间使用计算机时遇到音频问题，用户可以轻松地切换到使用手机进行音频。 团队检测到出现音频或设备问题时，通过显示 "**呼叫我**回电" 选项，重定向用户以使用其电话。

下面是在团队未检测到麦克风时显示的消息和 "**呼叫我回电**" 选项的示例。

!["呼叫我回电" 选项的屏幕截图](media/set-up-the-call-me-feature-for-your-users-no-mic.PNG)

用户单击 "**回拨**"，这将显示 "**使用电话进行音频**" 屏幕。 在这里，他们可以输入自己的电话号码并让团队会议呼叫，并将他们加入会议或手动拨入会议。

## <a name="set-up-the-call-me-feature"></a>设置 "呼叫我" 功能

若要为组织中的用户启用 "呼叫我" 功能，必须配置以下内容：

- 为组织中安排会议的用户（会议组织者）启用音频会议。 若要了解详细信息，请参阅[为团队设置音频会议](set-up-audio-conferencing-in-teams.md)和[管理团队中用户的音频会议设置](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)。

- 用户可以从会议拨出。 若要了解详细信息，请参阅[管理团队用户的音频会议设置](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)。

如果用户未启用 "从会议拨出"，则 "**呼叫我**" 选项不可用，并且用户将不会收到将其加入会议的呼叫。 相反，用户可以在 "**使用电话语音**" 屏幕上看到电话号码的列表，他们可以使用它们在手机上手动拨入会议。
