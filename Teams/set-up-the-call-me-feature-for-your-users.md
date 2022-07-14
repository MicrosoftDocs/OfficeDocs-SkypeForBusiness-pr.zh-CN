---
title: 为用户设置“致电我”功能
author: CarolynRowe
ms.author: crowe
ms.reviewer: macai, phedry
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: 了解如何在 Teams 中设置“呼叫我”功能，以便用户在使用计算机进行音频时可以通过电话加入音频部分。
ms.localizationpriority: medium
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a144e6a751f44ff520ee0317dbbcb390f30abbfd
ms.sourcegitcommit: 4d88637f510a78d5709d1213c3e285d83a022014
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/14/2022
ms.locfileid: "66794530"
---
# <a name="set-up-the-call-me-feature-for-your-users"></a>为用户设置“致电我”功能

在 Microsoft Teams 中，“ **呼叫我** ”功能为用户提供了通过电话加入会议音频部分的方法。 如果无法将计算机用于音频，则这种情况非常方便。 用户通过手机或固定电话和会议&mdash;内容部分获取会议的音频部分，例如当另一个会议参与者共享其屏幕或通过其计算机播放视频&mdash;时。

> [!IMPORTANT]
> 
> 在会议容量较高期间（随着新型冠状肺炎 (COVID-19) 爆发，我们一直面临此问题），建议用户通过单击“加入团队会议”按钮来加入会议，而不是使用 PSTN 会议号码或“给我打电话”。<strong></strong><strong></strong> 这有助于在高容量会议造成 PSTN 网络拥堵时确保音频质量。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="the-user-experience"></a>用户体验

### <a name="join-a-meeting-by-using-phone-for-audio"></a>使用手机进行音频加入会议

单击 **“加入**”加入会议，然后单击“**选择视频和音频选项**”屏幕上的 **“电话音频**”，然后立即单击 **“加入**”。 在此处，用户可以进行会议呼叫并加入会议，或手动拨入会议。

![“电话音频”选项的屏幕截图。](media/set-up-the-call-me-feature-for-your-users-phone-audio.png)

**让 Teams 会议呼叫**

在音频屏幕的 **“使用电话** ”上，用户输入其电话号码，然后单击 **“呼叫我**”。 会议会调用用户并将其加入会议。

![音频屏幕的“使用电话”上的“呼叫我”选项的屏幕截图。](media/set-up-the-call-me-feature-for-your-users-call-me.png)

**手动拨入**

加入的另一种方法是直接拨入会议。 在音频屏幕的 **“使用电话** ”上， **手动单击“拨入** ”以获取用于拨入会议的电话号码列表。

![“手动拨入”选项的屏幕截图。](media/set-up-the-call-me-feature-for-your-users-dial-in.png)

### <a name="get-a-call-back-when-something-goes-wrong-with-audio-during-a-meeting"></a>在会议期间音频出现问题时回电

如果用户在会议期间使用计算机时遇到音频问题，则用户可以轻松切换到将手机用于音频。 Teams 会检测何时发生音频或设备问题，并通过显示 **“回电”** 选项重定向用户以使用其手机。

下面是消息的示例，以及 Teams 未检测到麦克风时显示的 **“回电** ”选项。

![“给我回电”选项的屏幕截图。](media/set-up-the-call-me-feature-for-your-users-no-mic.PNG)

用户单击 **“给我回电**”，此时会显示 **音频屏幕的“使用电话** ”。 在这里，他们可以输入他们的电话号码，并让 Teams 会议呼叫，并加入会议或手动拨入会议。

## <a name="set-up-the-call-me-feature"></a>设置“呼叫我”功能

若要为组织中的用户启用“呼叫我”功能，必须配置以下各项：

- 为组织中安排会议的用户启用音频会议 (会议组织者) 。 若要了解详细信息，请参阅 [为 Teams 设置音频会议](set-up-audio-conferencing-in-teams.md) 并 [管理 Teams 中用户的音频会议设置](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)。

- 会议组织者可以从会议拨号。 若要了解详细信息，请参阅 [管理 Teams 中用户的音频会议设置](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)。

如果会议组织者未启用会议拨号，则“**选择您的视频和音频选项**”屏幕上的 **“电话”音频** 选项对任何人都不可用，其他用户也无法接到加入会议的电话。 对于启用了拨号的用户，加入会议后，他们可以加入其他人，从 **“显示参与者** ”图标拨号。
