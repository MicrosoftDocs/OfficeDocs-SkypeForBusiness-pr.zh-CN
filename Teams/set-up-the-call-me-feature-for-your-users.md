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
ms.openlocfilehash: 8cee6937a1bdc2bef6d2184066cb32a4aa94d8e6
ms.sourcegitcommit: 4ee9835282e1440d03abc6dbcd172bc20c5b3015
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/01/2020
ms.locfileid: "43096847"
---
# <a name="set-up-the-call-me-feature-for-your-users"></a><span data-ttu-id="a35f2-103">为用户设置“致电我”功能</span><span class="sxs-lookup"><span data-stu-id="a35f2-103">Set up the Call me feature for your users</span></span>

<span data-ttu-id="a35f2-104">在 Microsoft 团队中，"**呼叫我**" 功能为用户提供了一种通过电话加入会议音频部分的方式。</span><span class="sxs-lookup"><span data-stu-id="a35f2-104">In Microsoft Teams, the **Call me** feature gives users a way to join the audio portion of a meeting by phone.</span></span> <span data-ttu-id="a35f2-105">这在可能无法使用计算机音频的情况下很方便。</span><span class="sxs-lookup"><span data-stu-id="a35f2-105">This is handy in scenarios when using a computer for audio might not be possible.</span></span> <span data-ttu-id="a35f2-106">用户通过其手机或土地线以及会议&mdash;的内容部分（如另一个会议参与者共享他们的屏幕或通过其计算机播放视频&mdash;）获取会议的音频部分。</span><span class="sxs-lookup"><span data-stu-id="a35f2-106">Users get the audio portion of the meeting through their cell phone or land line and the content portion of the meeting&mdash;such when another meeting participant shares their screen or plays a video&mdash;through their computer.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a35f2-107">在 COVID 爆发期间，我们建议用户通过单击 "**加入团队会议**" 按钮（而不是通过使用 PSTN 会议号码或使用 "**呼叫我**</strong>"）来加入会议。</span><span class="sxs-lookup"><span data-stu-id="a35f2-107">During the duration of the COVID-19 outbreak, we recommend that users join meetings by clicking the **Join Teams Meeting** button rather than dialing in by using the PSTN conference numbers or by using **Call me at**</strong>.</span></span> <span data-ttu-id="a35f2-108">这主要是因为受 COVID 影响的国家/地区的电话架构拥塞。</span><span class="sxs-lookup"><span data-stu-id="a35f2-108">This is primarily because of congestion in the telephony infrastructures of countries impacted by COVID-19.</span></span> <span data-ttu-id="a35f2-109">通过避免 PSTN 呼叫，你可能会体验到更好的音频质量。</span><span class="sxs-lookup"><span data-stu-id="a35f2-109">By avoiding PSTN calls, you'll likely experience better audio quality.</span></span> 

## <a name="the-user-experience"></a><span data-ttu-id="a35f2-110">用户体验</span><span class="sxs-lookup"><span data-stu-id="a35f2-110">The user experience</span></span>

### <a name="join-a-meeting-by-using-phone-for-audio"></a><span data-ttu-id="a35f2-111">通过使用手机 for 音频加入会议</span><span class="sxs-lookup"><span data-stu-id="a35f2-111">Join a meeting by using phone for audio</span></span>

<span data-ttu-id="a35f2-112">单击 "**加入**" 加入会议，然后单击 "**选择您的音频和视频设置**" 屏幕上的 "**电话音频**"。</span><span class="sxs-lookup"><span data-stu-id="a35f2-112">Click **Join** to join a meeting, and then click **Phone audio** on the  **Choose your audio and video settings** screen.</span></span> <span data-ttu-id="a35f2-113">在此，用户可以进行会议呼叫并加入会议或手动拨入会议。</span><span class="sxs-lookup"><span data-stu-id="a35f2-113">From here, users can have the meeting call and join them or dial in manually to the meeting.</span></span>

![电话音频选项的屏幕截图](media/set-up-the-call-me-feature-for-your-users-phone-audio.png)

<span data-ttu-id="a35f2-115">**允许团队会议通话**</span><span class="sxs-lookup"><span data-stu-id="a35f2-115">**Let the Teams meeting call**</span></span>

<span data-ttu-id="a35f2-116">在 "**使用电话语音通话**" 屏幕上，用户输入其电话号码，然后单击 "**呼叫我**"。</span><span class="sxs-lookup"><span data-stu-id="a35f2-116">On the **Use phone for audio** screen, the user enters their phone number, and then clicks **Call me**.</span></span> <span data-ttu-id="a35f2-117">会议将调用用户并将其加入会议。</span><span class="sxs-lookup"><span data-stu-id="a35f2-117">The meeting calls the user and joins them to the meeting.</span></span>

!["使用电话语音电话" 屏幕上的 "呼叫我" 选项的屏幕截图](media/set-up-the-call-me-feature-for-your-users-call-me.png)

<span data-ttu-id="a35f2-119">**手动拨入**</span><span class="sxs-lookup"><span data-stu-id="a35f2-119">**Dial in manually**</span></span>

<span data-ttu-id="a35f2-120">加入的另一种方法是直接拨入会议。</span><span class="sxs-lookup"><span data-stu-id="a35f2-120">Another way to join is to dial in directly to the meeting.</span></span> <span data-ttu-id="a35f2-121">在 "**使用电话语音音频**" 屏幕上，单击 "**手动拨入**" 以获取用于拨入会议的电话号码列表。</span><span class="sxs-lookup"><span data-stu-id="a35f2-121">On the **Use phone for audio** screen, click **Dial in manually** to get a list of phone numbers to use to dial in to the meeting.</span></span>

![手动拨入选项的屏幕截图](media/set-up-the-call-me-feature-for-your-users-dial-in.png)

### <a name="get-a-call-back-when-something-goes-wrong-with-audio-during-a-meeting"></a><span data-ttu-id="a35f2-123">在会议期间有音频出现问题时，您可以取回来电</span><span class="sxs-lookup"><span data-stu-id="a35f2-123">Get a call back when something goes wrong with audio during a meeting</span></span>

<span data-ttu-id="a35f2-124">如果用户在会议期间使用计算机时遇到音频问题，用户可以轻松地切换到使用手机进行音频。</span><span class="sxs-lookup"><span data-stu-id="a35f2-124">If a user experiences audio issues when using their computer during a meeting, the user can easily switch to using their phone for audio.</span></span> <span data-ttu-id="a35f2-125">团队检测到出现音频或设备问题时，通过显示 "**呼叫我**回电" 选项，重定向用户以使用其电话。</span><span class="sxs-lookup"><span data-stu-id="a35f2-125">Teams detects when an audio or device issue occurs and redirects the user to use their phone by displaying a **Call me back** option.</span></span>

<span data-ttu-id="a35f2-126">下面是在团队未检测到麦克风时显示的消息和 "**呼叫我回电**" 选项的示例。</span><span class="sxs-lookup"><span data-stu-id="a35f2-126">Here's an example of the message and the **Call me back** option that's displayed when Teams doesn't detect a microphone.</span></span>

!["呼叫我回电" 选项的屏幕截图](media/set-up-the-call-me-feature-for-your-users-no-mic.PNG)

<span data-ttu-id="a35f2-128">用户单击 "**回拨**"，这将显示 "**使用电话进行音频**" 屏幕。</span><span class="sxs-lookup"><span data-stu-id="a35f2-128">The user clicks **Call me back**, which brings up the **Use phone for audio** screen.</span></span> <span data-ttu-id="a35f2-129">在这里，他们可以输入自己的电话号码并让团队会议呼叫，并将他们加入会议或手动拨入会议。</span><span class="sxs-lookup"><span data-stu-id="a35f2-129">From here, they can enter their phone number and have the Teams meeting call and join them to the meeting or dial in manually to the meeting.</span></span>

## <a name="set-up-the-call-me-feature"></a><span data-ttu-id="a35f2-130">设置 "呼叫我" 功能</span><span class="sxs-lookup"><span data-stu-id="a35f2-130">Set up the Call me feature</span></span>

<span data-ttu-id="a35f2-131">若要为组织中的用户启用 "呼叫我" 功能，必须配置以下内容：</span><span class="sxs-lookup"><span data-stu-id="a35f2-131">To enable the Call me feature for users in your organization, the following must be configured:</span></span>

- <span data-ttu-id="a35f2-132">为组织中安排会议的用户（会议组织者）启用音频会议。</span><span class="sxs-lookup"><span data-stu-id="a35f2-132">Audio Conferencing is enabled for users in your organization who schedule meetings (meeting organizers).</span></span> <span data-ttu-id="a35f2-133">若要了解详细信息，请参阅[为团队设置音频会议](set-up-audio-conferencing-in-teams.md)和[管理团队中用户的音频会议设置](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="a35f2-133">To learn more, see [Set up Audio Conferencing for Teams](set-up-audio-conferencing-in-teams.md) and [Manage the Audio Conferencing settings for a user in Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span></span>

- <span data-ttu-id="a35f2-134">用户可以从会议拨出。</span><span class="sxs-lookup"><span data-stu-id="a35f2-134">Users can dial out from meetings.</span></span> <span data-ttu-id="a35f2-135">若要了解详细信息，请参阅[管理团队用户的音频会议设置](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="a35f2-135">To learn more, see [Manage the Audio Conferencing settings for a user in Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span></span>

<span data-ttu-id="a35f2-136">如果用户未启用 "从会议拨出"，则 "**呼叫我**" 选项不可用，并且用户将不会收到将其加入会议的呼叫。</span><span class="sxs-lookup"><span data-stu-id="a35f2-136">If a user doesn't have dial out from meetings enabled, the **Call me** option isn't available and the user won't receive a call to join them to the meeting.</span></span> <span data-ttu-id="a35f2-137">相反，用户可以在 "**使用电话语音**" 屏幕上看到电话号码的列表，他们可以使用它们在手机上手动拨入会议。</span><span class="sxs-lookup"><span data-stu-id="a35f2-137">Instead, the user sees a list of phone numbers on the **Use phone for audio** screen that they can use to dial in manually to the meeting on their phone.</span></span>
