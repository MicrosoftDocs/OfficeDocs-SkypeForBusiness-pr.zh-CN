---
title: 为你的用户设置 "呼叫我" 功能
author: LanaChin
ms.author: v-lanac
ms.reviewer: macai
manager: serdars
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: 了解如何在团队中设置 "呼叫我" 功能, 以便用户可以在使用其计算机音频的情况下通过电话加入音频部分。
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3f1ffee416b1d5674e831fda4c5bb15a89c510f4
ms.sourcegitcommit: 1ddd29e3839e50387efb4ec7b9d2154991bb2642
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2019
ms.locfileid: "35432120"
---
# <a name="set-up-the-call-me-feature-for-your-users"></a>为你的用户设置 "呼叫我" 功能

在 Microsoft 团队中, "**呼叫我**" 功能为用户提供了一种通过电话加入会议音频部分的方式。 这在可能无法使用计算机音频的情况下很方便。 用户通过其手机或土地线以及会议&mdash;的内容部分 (如另一个会议参与者共享他们的屏幕或通过其计算机播放视频&mdash;) 获取会议的音频部分。

## <a name="the-user-experience"></a>用户体验

单击 "**加入**" 加入会议, 然后单击 "**选择您的音频和视频设置**" 屏幕上的 "**电话音频**"。 在此, 用户可以进行会议呼叫并加入会议或手动拨入会议。

![电话音频选项的屏幕截图](media/set-up-the-call-me-feature-for-your-users-phone-audio.png)

**允许团队会议通话**

在 "**使用电话语音通话**" 屏幕上, 用户输入其电话号码, 然后单击 "**呼叫我**"。 会议将调用用户并将其加入会议。

!["使用电话语音电话" 屏幕上的 "呼叫我" 选项的屏幕截图](media/set-up-the-call-me-feature-for-your-users-call-me.png)

**手动拨入**

加入的另一种方法是直接拨入会议。 在 "**使用电话语音音频**" 屏幕上, 单击 "**手动拨入**" 以获取用于拨入会议的电话号码列表。

![手动拨入选项的屏幕截图](media/set-up-the-call-me-feature-for-your-users-dial-in.png)

## <a name="set-up-the-call-me-feature"></a>设置 "呼叫我" 功能

若要为组织中的用户启用 "呼叫我" 功能, 必须配置以下内容:

- 为组织中安排会议的用户 (会议组织者) 启用音频会议。 若要了解详细信息, 请参阅[为团队设置音频会议](set-up-audio-conferencing-in-teams.md)和[管理团队中用户的音频会议设置](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)。

- 用户可以从会议拨出。 若要了解详细信息, 请参阅[管理团队用户的音频会议设置](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)。

如果用户未启用 "从会议拨出", 则 "**呼叫我**" 选项不可用, 并且用户将不会收到将其加入会议的呼叫。 相反, 用户可以在 "**使用电话语音**" 屏幕上看到电话号码的列表, 他们可以使用它们在手机上手动拨入会议。

