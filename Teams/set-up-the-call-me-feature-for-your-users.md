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
# <a name="set-up-the-call-me-feature-for-your-users"></a><span data-ttu-id="ad096-103">为用户设置“致电我”功能</span><span class="sxs-lookup"><span data-stu-id="ad096-103">Set up the Call me feature for your users</span></span>

<span data-ttu-id="ad096-104">在 Microsoft Teams 中 **，"呼叫我** "功能为用户提供了通过电话加入会议音频部分的方法。</span><span class="sxs-lookup"><span data-stu-id="ad096-104">In Microsoft Teams, the **Call me** feature gives users a way to join the audio portion of a meeting by phone.</span></span> <span data-ttu-id="ad096-105">如果无法将计算机用于音频，则此功能非常方便。</span><span class="sxs-lookup"><span data-stu-id="ad096-105">This is handy in scenarios when using a computer for audio might not be possible.</span></span> <span data-ttu-id="ad096-106">用户通过其移动电话或座机获取会议的音频部分和会议的内容部分，例如当其他会议参与者共享其屏幕或通过其计算机 &mdash; &mdash; 播放视频时。</span><span class="sxs-lookup"><span data-stu-id="ad096-106">Users get the audio portion of the meeting through their cell phone or land line and the content portion of the meeting&mdash;such as when another meeting participant shares their screen or plays a video&mdash;through their computer.</span></span>

> [!IMPORTANT]
> 
> <span data-ttu-id="ad096-107">在会议容量较高期间（随着新型冠状肺炎 (COVID-19) 爆发，我们一直面临此问题），建议用户通过单击“加入团队会议”按钮来加入会议，而不是使用 PSTN 会议号码或“给我打电话”。<strong></strong><strong></strong></span><span class="sxs-lookup"><span data-stu-id="ad096-107">During periods of high meeting volume (which we've been experiencing in conjunction with the COVID-19 outbreak), we recommend that users join meetings by clicking the <strong>Join Teams Meeting</strong> button rather than dialing in by using the PSTN conference numbers or by using <strong>Call me at</strong>.</span></span> <span data-ttu-id="ad096-108">这有助于在高容量会议造成 PSTN 网络拥堵时确保音频质量。</span><span class="sxs-lookup"><span data-stu-id="ad096-108">This helps ensure quality audio during times when high meeting volume is causing congestion on the PSTN network.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="ad096-109">在新型冠状肺炎（COVID-19） 爆发期间，建议用户通过单击“**加入团队会议**”按钮来加入会议，而不是使用 PSTN 会议号码或 **给我打电话**</strong>。</span><span class="sxs-lookup"><span data-stu-id="ad096-109">During the duration of the COVID-19 outbreak, we recommend that users join meetings by clicking the **Join Teams Meeting** button rather than dialing in by using the PSTN conference numbers or by using **Call me at**</strong>.</span></span> <span data-ttu-id="ad096-110">这主要是由于新型冠状病毒（COVID-19）所影响国家/地区的电话基础设施拥堵而导致。</span><span class="sxs-lookup"><span data-stu-id="ad096-110">This is primarily because of congestion in the telephony infrastructures of countries impacted by COVID-19.</span></span> <span data-ttu-id="ad096-111">通过避免 PSTN 通话，您可能会体验到更好的音频质量。</span><span class="sxs-lookup"><span data-stu-id="ad096-111">By avoiding PSTN calls, you'll likely experience better audio quality.</span></span> 

## <a name="the-user-experience"></a><span data-ttu-id="ad096-112">用户体验</span><span class="sxs-lookup"><span data-stu-id="ad096-112">The user experience</span></span>

### <a name="join-a-meeting-by-using-phone-for-audio"></a><span data-ttu-id="ad096-113">使用电话进行音频加入会议</span><span class="sxs-lookup"><span data-stu-id="ad096-113">Join a meeting by using phone for audio</span></span>

<span data-ttu-id="ad096-114">单击 **"** 加入"以加入会议，然后在"选择 **音频和视频设置"** 屏幕上单击"电话音频"。</span><span class="sxs-lookup"><span data-stu-id="ad096-114">Click **Join** to join a meeting, and then click **Phone audio** on the  **Choose your audio and video settings** screen.</span></span> <span data-ttu-id="ad096-115">在这里，用户可以进行会议呼叫并加入会议或手动拨入会议。</span><span class="sxs-lookup"><span data-stu-id="ad096-115">From here, users can have the meeting call and join them or dial in manually to the meeting.</span></span>

!["电话"音频选项的屏幕截图](media/set-up-the-call-me-feature-for-your-users-phone-audio.png)

<span data-ttu-id="ad096-117">**让 Teams 会议通话**</span><span class="sxs-lookup"><span data-stu-id="ad096-117">**Let the Teams meeting call**</span></span>

<span data-ttu-id="ad096-118">在"**将电话用于音频**"屏幕上，用户输入其电话号码，然后单击"呼叫 **我"。**</span><span class="sxs-lookup"><span data-stu-id="ad096-118">On the **Use phone for audio** screen, the user enters their phone number, and then clicks **Call me**.</span></span> <span data-ttu-id="ad096-119">会议将呼叫用户并加入会议。</span><span class="sxs-lookup"><span data-stu-id="ad096-119">The meeting calls the user and joins them to the meeting.</span></span>

!["将电话用于音频"屏幕上的"呼叫我"选项的屏幕截图](media/set-up-the-call-me-feature-for-your-users-call-me.png)

<span data-ttu-id="ad096-121">**手动拨入**</span><span class="sxs-lookup"><span data-stu-id="ad096-121">**Dial in manually**</span></span>

<span data-ttu-id="ad096-122">另一种加入方法就是直接拨入会议。</span><span class="sxs-lookup"><span data-stu-id="ad096-122">Another way to join is to dial in directly to the meeting.</span></span> <span data-ttu-id="ad096-123">在 **"将电话用于音频**"屏幕上，单击"手动拨入"，获取用于拨入会议的电话号码列表。</span><span class="sxs-lookup"><span data-stu-id="ad096-123">On the **Use phone for audio** screen, click **Dial in manually** to get a list of phone numbers to use to dial in to the meeting.</span></span>

!["手动拨入"选项的屏幕截图](media/set-up-the-call-me-feature-for-your-users-dial-in.png)

### <a name="get-a-call-back-when-something-goes-wrong-with-audio-during-a-meeting"></a><span data-ttu-id="ad096-125">在会议期间音频出现问题时进行回电</span><span class="sxs-lookup"><span data-stu-id="ad096-125">Get a call back when something goes wrong with audio during a meeting</span></span>

<span data-ttu-id="ad096-126">如果用户在会议期间使用计算机时遇到音频问题，用户可以轻松地切换到使用电话进行音频处理。</span><span class="sxs-lookup"><span data-stu-id="ad096-126">If a user experiences audio issues when using their computer during a meeting, the user can easily switch to using their phone for audio.</span></span> <span data-ttu-id="ad096-127">Teams 检测何时发生音频或设备问题，通过显示"回叫我"选项将用户重定向为使用 **其** 电话。</span><span class="sxs-lookup"><span data-stu-id="ad096-127">Teams detects when an audio or device issue occurs and redirects the user to use their phone by displaying a **Call me back** option.</span></span>

<span data-ttu-id="ad096-128">下面是当 Teams 未检测到麦克风时显示的消息和"回电"选项的示例。</span><span class="sxs-lookup"><span data-stu-id="ad096-128">Here's an example of the message and the **Call me back** option that's displayed when Teams doesn't detect a microphone.</span></span>

!["回叫我"选项的屏幕截图](media/set-up-the-call-me-feature-for-your-users-no-mic.PNG)

<span data-ttu-id="ad096-130">用户单击 **"回电"，** 显示"使用电话 **进行音频"** 屏幕。</span><span class="sxs-lookup"><span data-stu-id="ad096-130">The user clicks **Call me back**, which brings up the **Use phone for audio** screen.</span></span> <span data-ttu-id="ad096-131">在这里，他们可以输入其电话号码，让 Teams 会议呼叫并加入会议或手动拨入会议。</span><span class="sxs-lookup"><span data-stu-id="ad096-131">From here, they can enter their phone number and have the Teams meeting call and join them to the meeting or dial in manually to the meeting.</span></span>

## <a name="set-up-the-call-me-feature"></a><span data-ttu-id="ad096-132">设置"呼叫我"功能</span><span class="sxs-lookup"><span data-stu-id="ad096-132">Set up the Call me feature</span></span>

<span data-ttu-id="ad096-133">若要为贵组织的用户启用"呼叫我"功能，必须配置以下各项：</span><span class="sxs-lookup"><span data-stu-id="ad096-133">To enable the Call me feature for users in your organization, the following must be configured:</span></span>

- <span data-ttu-id="ad096-134">为组织中安排会议的用户启用音频会议 (会议组织者) 。</span><span class="sxs-lookup"><span data-stu-id="ad096-134">Audio Conferencing is enabled for users in your organization who schedule meetings (meeting organizers).</span></span> <span data-ttu-id="ad096-135">若要了解有关详细信息，请参阅"为[Teams](set-up-audio-conferencing-in-teams.md)设置音频会议"和"在 Teams 中管理用户的音频[会议设置"。](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="ad096-135">To learn more, see [Set up Audio Conferencing for Teams](set-up-audio-conferencing-in-teams.md) and [Manage the Audio Conferencing settings for a user in Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span></span>

- <span data-ttu-id="ad096-136">用户可以从会议拨出。</span><span class="sxs-lookup"><span data-stu-id="ad096-136">Users can dial out from meetings.</span></span> <span data-ttu-id="ad096-137">若要了解有关详细信息，请参阅["在 Teams 中管理用户的音频会议设置"。](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="ad096-137">To learn more, see [Manage the Audio Conferencing settings for a user in Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span></span>

<span data-ttu-id="ad096-138">如果用户未启用会议拨出功能，则"呼叫我"选项不可用，并且用户不会收到用于加入会议的呼叫。</span><span class="sxs-lookup"><span data-stu-id="ad096-138">If a user doesn't have dial out from meetings enabled, the **Call me** option isn't available and the user won't receive a call to join them to the meeting.</span></span> <span data-ttu-id="ad096-139">相反，用户在"将电话用于音频"屏幕上看到电话号码列表，他们可以使用该列表手动拨入其电话上的会议。</span><span class="sxs-lookup"><span data-stu-id="ad096-139">Instead, the user sees a list of phone numbers on the **Use phone for audio** screen that they can use to dial in manually to the meeting on their phone.</span></span>
