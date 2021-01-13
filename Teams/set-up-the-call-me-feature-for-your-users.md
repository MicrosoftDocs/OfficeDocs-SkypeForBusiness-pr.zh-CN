---
title: 为用户设置“致电我”功能
author: cichur
ms.author: v-cichur
ms.reviewer: macai, phedry
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: 了解如何在 Teams 中设置"呼叫我"功能，以便用户在将计算机用于音频时通过电话加入音频部分。
localization_priority: Normal
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 6b78edc01f68df19e850a85eb0ffa99163b9edae
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821092"
---
# <a name="set-up-the-call-me-feature-for-your-users"></a>为用户设置“致电我”功能

在 Microsoft Teams 中 **，"呼叫我** "功能为用户提供了通过电话加入会议音频部分的方法。 如果无法将计算机用于音频，则此功能非常方便。 用户通过其移动电话或座机获取会议的音频部分和会议的内容部分，例如当其他会议参与者共享其屏幕或通过其计算机 &mdash; &mdash; 播放视频时。

> [!IMPORTANT]
> 
> 在会议容量较高期间（随着新型冠状肺炎 (COVID-19) 爆发，我们一直面临此问题），建议用户通过单击“加入团队会议”按钮来加入会议，而不是使用 PSTN 会议号码或“给我打电话”。<strong></strong><strong></strong> 这有助于在高容量会议造成 PSTN 网络拥堵时确保音频质量。 

> [!IMPORTANT]
> 在新型冠状肺炎（COVID-19） 爆发期间，建议用户通过单击“**加入团队会议**”按钮来加入会议，而不是使用 PSTN 会议号码或 **给我打电话**</strong>。 这主要是由于新型冠状病毒（COVID-19）所影响国家/地区的电话基础设施拥堵而导致。 通过避免 PSTN 通话，您可能会体验到更好的音频质量。 

## <a name="the-user-experience"></a>用户体验

### <a name="join-a-meeting-by-using-phone-for-audio"></a>使用电话进行音频加入会议

单击 **"** 加入"以加入会议，然后在"选择 **音频和视频设置"** 屏幕上单击"电话音频"。 在这里，用户可以进行会议呼叫并加入会议或手动拨入会议。

!["电话"音频选项的屏幕截图](media/set-up-the-call-me-feature-for-your-users-phone-audio.png)

**让 Teams 会议通话**

在"**将电话用于音频**"屏幕上，用户输入其电话号码，然后单击"呼叫 **我"。** 会议将呼叫用户并加入会议。

!["将电话用于音频"屏幕上的"呼叫我"选项的屏幕截图](media/set-up-the-call-me-feature-for-your-users-call-me.png)

**手动拨入**

另一种加入方法就是直接拨入会议。 在 **"将电话用于音频**"屏幕上，单击"手动拨入"，获取用于拨入会议的电话号码列表。

!["手动拨入"选项的屏幕截图](media/set-up-the-call-me-feature-for-your-users-dial-in.png)

### <a name="get-a-call-back-when-something-goes-wrong-with-audio-during-a-meeting"></a>在会议期间音频出现问题时进行回电

如果用户在会议期间使用计算机时遇到音频问题，用户可以轻松地切换到使用电话进行音频处理。 Teams 检测何时发生音频或设备问题，通过显示"回叫我"选项将用户重定向为使用 **其** 电话。

下面是当 Teams 未检测到麦克风时显示的消息和"回电"选项的示例。

!["回叫我"选项的屏幕截图](media/set-up-the-call-me-feature-for-your-users-no-mic.PNG)

用户单击 **"回电"，** 显示"使用电话 **进行音频"** 屏幕。 在这里，他们可以输入其电话号码，让 Teams 会议呼叫并加入会议或手动拨入会议。

## <a name="set-up-the-call-me-feature"></a>设置"呼叫我"功能

若要为贵组织的用户启用"呼叫我"功能，必须配置以下各项：

- 为组织中安排会议的用户启用音频会议 (会议组织者) 。 若要了解有关详细信息，请参阅"为[Teams](set-up-audio-conferencing-in-teams.md)设置音频会议"和"在 Teams 中管理用户的音频[会议设置"。](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)

- 用户可以从会议拨出。 若要了解有关详细信息，请参阅["在 Teams 中管理用户的音频会议设置"。](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)

如果用户未启用会议拨出功能，则"呼叫我"选项不可用，并且用户不会收到用于加入会议的呼叫。 相反，用户在"将电话用于音频"屏幕上看到电话号码列表，他们可以使用该列表手动拨入其电话上的会议。
