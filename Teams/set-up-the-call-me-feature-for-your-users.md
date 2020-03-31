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
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8fc2a66e2414350a56874583af6a00f688450f0e
ms.sourcegitcommit: 996ae0d36ae1bcb3978c865bb296d8eccf48598e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/31/2020
ms.locfileid: "43068514"
---
# <a name="set-up-the-call-me-feature-for-your-users"></a><span data-ttu-id="3aac4-103">为用户设置“致电我”功能</span><span class="sxs-lookup"><span data-stu-id="3aac4-103">Set up the Call me feature for your users</span></span>

<span data-ttu-id="3aac4-104">在 Microsoft 团队中，"**呼叫我**" 功能为用户提供了一种通过电话加入会议音频部分的方式。</span><span class="sxs-lookup"><span data-stu-id="3aac4-104">In Microsoft Teams, the **Call me** feature gives users a way to join the audio portion of a meeting by phone.</span></span> <span data-ttu-id="3aac4-105">这在可能无法使用计算机音频的情况下很方便。</span><span class="sxs-lookup"><span data-stu-id="3aac4-105">This is handy in scenarios when using a computer for audio might not be possible.</span></span> <span data-ttu-id="3aac4-106">用户通过其手机或土地线以及会议&mdash;的内容部分（如另一个会议参与者共享他们的屏幕或通过其计算机播放视频&mdash;）获取会议的音频部分。</span><span class="sxs-lookup"><span data-stu-id="3aac4-106">Users get the audio portion of the meeting through their cell phone or land line and the content portion of the meeting&mdash;such when another meeting participant shares their screen or plays a video&mdash;through their computer.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3aac4-107">在 COVID 爆发期间，我们建议用户通过单击 "**加入团队会议**" 按钮（而不是通过使用 PSTN 会议号码或使用 "**呼叫我**"）来加入会议。</span><span class="sxs-lookup"><span data-stu-id="3aac4-107">During the duration of the COVID-19 outbreak, we recommend that users join meetings by clicking the **Join Teams Meeting** button rather than dialing in by using the PSTN conference numbers or by using **Call me at**.</span></span> <span data-ttu-id="3aac4-108">这有助于在较高的会议音量在 PSTN 网络上导致拥挤的时间内确保质量的音频。</span><span class="sxs-lookup"><span data-stu-id="3aac4-108">This helps ensure quality audio during times when high meeting volume is causing congestion on the PSTN network.</span></span>

## <a name="the-user-experience"></a><span data-ttu-id="3aac4-109">用户体验</span><span class="sxs-lookup"><span data-stu-id="3aac4-109">The user experience</span></span>

### <a name="join-a-meeting-by-using-phone-for-audio"></a><span data-ttu-id="3aac4-110">通过使用手机 for 音频加入会议</span><span class="sxs-lookup"><span data-stu-id="3aac4-110">Join a meeting by using phone for audio</span></span>

<span data-ttu-id="3aac4-111">单击 "**加入**" 加入会议，然后单击 "**选择您的音频和视频设置**" 屏幕上的 "**电话音频**"。</span><span class="sxs-lookup"><span data-stu-id="3aac4-111">Click **Join** to join a meeting, and then click **Phone audio** on the  **Choose your audio and video settings** screen.</span></span> <span data-ttu-id="3aac4-112">在此，用户可以进行会议呼叫并加入会议或手动拨入会议。</span><span class="sxs-lookup"><span data-stu-id="3aac4-112">From here, users can have the meeting call and join them or dial in manually to the meeting.</span></span>

![电话音频选项的屏幕截图](media/set-up-the-call-me-feature-for-your-users-phone-audio.png)

<span data-ttu-id="3aac4-114">**允许团队会议通话**</span><span class="sxs-lookup"><span data-stu-id="3aac4-114">**Let the Teams meeting call**</span></span>

<span data-ttu-id="3aac4-115">在 "**使用电话语音通话**" 屏幕上，用户输入其电话号码，然后单击 "**呼叫我**"。</span><span class="sxs-lookup"><span data-stu-id="3aac4-115">On the **Use phone for audio** screen, the user enters their phone number, and then clicks **Call me**.</span></span> <span data-ttu-id="3aac4-116">会议将调用用户并将其加入会议。</span><span class="sxs-lookup"><span data-stu-id="3aac4-116">The meeting calls the user and joins them to the meeting.</span></span>

!["使用电话语音电话" 屏幕上的 "呼叫我" 选项的屏幕截图](media/set-up-the-call-me-feature-for-your-users-call-me.png)

<span data-ttu-id="3aac4-118">**手动拨入**</span><span class="sxs-lookup"><span data-stu-id="3aac4-118">**Dial in manually**</span></span>

<span data-ttu-id="3aac4-119">加入的另一种方法是直接拨入会议。</span><span class="sxs-lookup"><span data-stu-id="3aac4-119">Another way to join is to dial in directly to the meeting.</span></span> <span data-ttu-id="3aac4-120">在 "**使用电话语音音频**" 屏幕上，单击 "**手动拨入**" 以获取用于拨入会议的电话号码列表。</span><span class="sxs-lookup"><span data-stu-id="3aac4-120">On the **Use phone for audio** screen, click **Dial in manually** to get a list of phone numbers to use to dial in to the meeting.</span></span>

![手动拨入选项的屏幕截图](media/set-up-the-call-me-feature-for-your-users-dial-in.png)

### <a name="get-a-call-back-when-something-goes-wrong-with-audio-during-a-meeting"></a><span data-ttu-id="3aac4-122">在会议期间有音频出现问题时，您可以取回来电</span><span class="sxs-lookup"><span data-stu-id="3aac4-122">Get a call back when something goes wrong with audio during a meeting</span></span>

<span data-ttu-id="3aac4-123">如果用户在会议期间使用计算机时遇到音频问题，用户可以轻松地切换到使用手机进行音频。</span><span class="sxs-lookup"><span data-stu-id="3aac4-123">If a user experiences audio issues when using their computer during a meeting, the user can easily switch to using their phone for audio.</span></span> <span data-ttu-id="3aac4-124">团队检测到出现音频或设备问题时，通过显示 "**呼叫我**回电" 选项，重定向用户以使用其电话。</span><span class="sxs-lookup"><span data-stu-id="3aac4-124">Teams detects when an audio or device issue occurs and redirects the user to use their phone by displaying a **Call me back** option.</span></span>

<span data-ttu-id="3aac4-125">下面是在团队未检测到麦克风时显示的消息和 "**呼叫我回电**" 选项的示例。</span><span class="sxs-lookup"><span data-stu-id="3aac4-125">Here's an example of the message and the **Call me back** option that's displayed when Teams doesn't detect a microphone.</span></span>

!["呼叫我回电" 选项的屏幕截图](media/set-up-the-call-me-feature-for-your-users-no-mic.PNG)

<span data-ttu-id="3aac4-127">用户单击 "**回拨**"，这将显示 "**使用电话进行音频**" 屏幕。</span><span class="sxs-lookup"><span data-stu-id="3aac4-127">The user clicks **Call me back**, which brings up the **Use phone for audio** screen.</span></span> <span data-ttu-id="3aac4-128">在这里，他们可以输入自己的电话号码并让团队会议呼叫，并将他们加入会议或手动拨入会议。</span><span class="sxs-lookup"><span data-stu-id="3aac4-128">From here, they can enter their phone number and have the Teams meeting call and join them to the meeting or dial in manually to the meeting.</span></span>

## <a name="set-up-the-call-me-feature"></a><span data-ttu-id="3aac4-129">设置 "呼叫我" 功能</span><span class="sxs-lookup"><span data-stu-id="3aac4-129">Set up the Call me feature</span></span>

<span data-ttu-id="3aac4-130">若要为组织中的用户启用 "呼叫我" 功能，必须配置以下内容：</span><span class="sxs-lookup"><span data-stu-id="3aac4-130">To enable the Call me feature for users in your organization, the following must be configured:</span></span>

- <span data-ttu-id="3aac4-131">为组织中安排会议的用户（会议组织者）启用音频会议。</span><span class="sxs-lookup"><span data-stu-id="3aac4-131">Audio Conferencing is enabled for users in your organization who schedule meetings (meeting organizers).</span></span> <span data-ttu-id="3aac4-132">若要了解详细信息，请参阅[为团队设置音频会议](set-up-audio-conferencing-in-teams.md)和[管理团队中用户的音频会议设置](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="3aac4-132">To learn more, see [Set up Audio Conferencing for Teams](set-up-audio-conferencing-in-teams.md) and [Manage the Audio Conferencing settings for a user in Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span></span>

- <span data-ttu-id="3aac4-133">用户可以从会议拨出。</span><span class="sxs-lookup"><span data-stu-id="3aac4-133">Users can dial out from meetings.</span></span> <span data-ttu-id="3aac4-134">若要了解详细信息，请参阅[管理团队用户的音频会议设置](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="3aac4-134">To learn more, see [Manage the Audio Conferencing settings for a user in Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span></span>

<span data-ttu-id="3aac4-135">如果用户未启用 "从会议拨出"，则 "**呼叫我**" 选项不可用，并且用户将不会收到将其加入会议的呼叫。</span><span class="sxs-lookup"><span data-stu-id="3aac4-135">If a user doesn't have dial out from meetings enabled, the **Call me** option isn't available and the user won't receive a call to join them to the meeting.</span></span> <span data-ttu-id="3aac4-136">相反，用户可以在 "**使用电话语音**" 屏幕上看到电话号码的列表，他们可以使用它们在手机上手动拨入会议。</span><span class="sxs-lookup"><span data-stu-id="3aac4-136">Instead, the user sees a list of phone numbers on the **Use phone for audio** screen that they can use to dial in manually to the meeting on their phone.</span></span>
