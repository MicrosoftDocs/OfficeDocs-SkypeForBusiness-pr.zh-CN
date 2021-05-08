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
description: 了解如何在视频中设置"呼叫我"功能Teams以便用户在使用计算机进行音频时通过电话加入音频部分可能不可能。
localization_priority: Normal
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 04510a827e9343010c756b14590e9800354c71e9
ms.sourcegitcommit: f979c491af5210e6ceb1d1c00e000767f1a8311d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/07/2021
ms.locfileid: "51623126"
---
# <a name="set-up-the-call-me-feature-for-your-users"></a><span data-ttu-id="2f755-103">为用户设置“致电我”功能</span><span class="sxs-lookup"><span data-stu-id="2f755-103">Set up the Call me feature for your users</span></span>

<span data-ttu-id="2f755-104">在Microsoft Teams中，"呼叫我"功能为用户提供了通过电话加入会议音频部分的方法。</span><span class="sxs-lookup"><span data-stu-id="2f755-104">In Microsoft Teams, the **Call me** feature gives users a way to join the audio portion of a meeting by phone.</span></span> <span data-ttu-id="2f755-105">当无法将计算机用于音频时，这非常方便。</span><span class="sxs-lookup"><span data-stu-id="2f755-105">This is handy in scenarios when using a computer for audio might not be possible.</span></span> <span data-ttu-id="2f755-106">用户通过其移动电话或座机获取会议的音频部分以及会议的内容部分，例如当其他会议参与者共享其屏幕或通过其计算机 &mdash; &mdash; 播放视频时。</span><span class="sxs-lookup"><span data-stu-id="2f755-106">Users get the audio portion of the meeting through their cell phone or land line and the content portion of the meeting&mdash;such as when another meeting participant shares their screen or plays a video&mdash;through their computer.</span></span>

> [!IMPORTANT]
> 
> <span data-ttu-id="2f755-107">在会议容量较高期间（随着新型冠状肺炎 (COVID-19) 爆发，我们一直面临此问题），建议用户通过单击“加入团队会议”按钮来加入会议，而不是使用 PSTN 会议号码或“给我打电话”。<strong></strong><strong></strong></span><span class="sxs-lookup"><span data-stu-id="2f755-107">During periods of high meeting volume (which we've been experiencing in conjunction with the COVID-19 outbreak), we recommend that users join meetings by clicking the <strong>Join Teams Meeting</strong> button rather than dialing in by using the PSTN conference numbers or by using <strong>Call me at</strong>.</span></span> <span data-ttu-id="2f755-108">这有助于在高容量会议造成 PSTN 网络拥堵时确保音频质量。</span><span class="sxs-lookup"><span data-stu-id="2f755-108">This helps ensure quality audio during times when high meeting volume is causing congestion on the PSTN network.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="the-user-experience"></a><span data-ttu-id="2f755-109">用户体验</span><span class="sxs-lookup"><span data-stu-id="2f755-109">The user experience</span></span>

### <a name="join-a-meeting-by-using-phone-for-audio"></a><span data-ttu-id="2f755-110">使用电话进行音频加入会议</span><span class="sxs-lookup"><span data-stu-id="2f755-110">Join a meeting by using phone for audio</span></span>

<span data-ttu-id="2f755-111">单击 **"** 加入"以 **加入** 会议，电话选择视频和音频选项屏幕上的音频，然后单击"立即 **加入"。**</span><span class="sxs-lookup"><span data-stu-id="2f755-111">Click **Join** to join a meeting, then **Phone audio** on the **Choose your video and audio options** screen, and click **Join now**.</span></span> <span data-ttu-id="2f755-112">在这里，用户可以进行会议呼叫并加入会议或手动拨入会议。</span><span class="sxs-lookup"><span data-stu-id="2f755-112">From here, users can have the meeting call and join them or dial in manually to the meeting.</span></span>

![音频选项电话屏幕截图](media/set-up-the-call-me-feature-for-your-users-phone-audio.png)

<span data-ttu-id="2f755-114">**让Teams会议呼叫**</span><span class="sxs-lookup"><span data-stu-id="2f755-114">**Let the Teams meeting call**</span></span>

<span data-ttu-id="2f755-115">在"**将电话用于音频**"屏幕上，用户输入其电话号码，然后单击"呼叫 **我"。**</span><span class="sxs-lookup"><span data-stu-id="2f755-115">On the **Use phone for audio** screen, the user enters their phone number, and then clicks **Call me**.</span></span> <span data-ttu-id="2f755-116">会议将呼叫用户并加入会议。</span><span class="sxs-lookup"><span data-stu-id="2f755-116">The meeting calls the user and joins them to the meeting.</span></span>

!["将电话用于音频"屏幕上的"呼叫我"选项的屏幕截图](media/set-up-the-call-me-feature-for-your-users-call-me.png)

<span data-ttu-id="2f755-118">**手动拨入**</span><span class="sxs-lookup"><span data-stu-id="2f755-118">**Dial in manually**</span></span>

<span data-ttu-id="2f755-119">加入的另一种方式是直接拨入会议。</span><span class="sxs-lookup"><span data-stu-id="2f755-119">Another way to join is to dial in directly to the meeting.</span></span> <span data-ttu-id="2f755-120">在 **"将电话用于音频**"屏幕上，单击"手动拨入"，获取用于拨入会议的电话号码列表。</span><span class="sxs-lookup"><span data-stu-id="2f755-120">On the **Use phone for audio** screen, click **Dial in manually** to get a list of phone numbers to use to dial in to the meeting.</span></span>

!["手动拨入"选项的屏幕截图](media/set-up-the-call-me-feature-for-your-users-dial-in.png)

### <a name="get-a-call-back-when-something-goes-wrong-with-audio-during-a-meeting"></a><span data-ttu-id="2f755-122">在会议期间音频出现问题时进行回电</span><span class="sxs-lookup"><span data-stu-id="2f755-122">Get a call back when something goes wrong with audio during a meeting</span></span>

<span data-ttu-id="2f755-123">如果用户在会议期间使用计算机时遇到音频问题，用户可以轻松地切换到使用手机进行音频处理。</span><span class="sxs-lookup"><span data-stu-id="2f755-123">If a user experiences audio issues when using their computer during a meeting, the user can easily switch to using their phone for audio.</span></span> <span data-ttu-id="2f755-124">Teams音频或设备问题何时发生，并显示"回叫我"选项，重定向用户使用 **其手机。**</span><span class="sxs-lookup"><span data-stu-id="2f755-124">Teams detects when an audio or device issue occurs and redirects the user to use their phone by displaying a **Call me back** option.</span></span>

<span data-ttu-id="2f755-125">下面是消息的示例，以及当未检测到麦克风时显示的"Teams回叫"选项。</span><span class="sxs-lookup"><span data-stu-id="2f755-125">Here's an example of the message and the **Call me back** option that's displayed when Teams doesn't detect a microphone.</span></span>

!["回叫我"选项的屏幕截图](media/set-up-the-call-me-feature-for-your-users-no-mic.PNG)

<span data-ttu-id="2f755-127">用户单击 **"回电"，** 显示"将 **手机用于音频"** 屏幕。</span><span class="sxs-lookup"><span data-stu-id="2f755-127">The user clicks **Call me back**, which brings up the **Use phone for audio** screen.</span></span> <span data-ttu-id="2f755-128">在这里，他们可以输入其电话号码，并Teams会议呼叫，并加入会议或手动拨入会议。</span><span class="sxs-lookup"><span data-stu-id="2f755-128">From here, they can enter their phone number and have the Teams meeting call and join them to the meeting or dial in manually to the meeting.</span></span>

## <a name="set-up-the-call-me-feature"></a><span data-ttu-id="2f755-129">设置"呼叫我"功能</span><span class="sxs-lookup"><span data-stu-id="2f755-129">Set up the Call me feature</span></span>

<span data-ttu-id="2f755-130">若要为组织中用户启用"呼叫我"功能，必须配置以下各项：</span><span class="sxs-lookup"><span data-stu-id="2f755-130">To enable the Call me feature for users in your organization, the following must be configured:</span></span>

- <span data-ttu-id="2f755-131">为组织中安排会议的用户启用音频会议 (组织者) 。</span><span class="sxs-lookup"><span data-stu-id="2f755-131">Audio Conferencing is enabled for users in your organization who schedule meetings (meeting organizers).</span></span> <span data-ttu-id="2f755-132">有关详细信息，请参阅[为](set-up-audio-conferencing-in-teams.md)用户设置音频[Teams和管理用户](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)的音频会议设置Teams。</span><span class="sxs-lookup"><span data-stu-id="2f755-132">To learn more, see [Set up Audio Conferencing for Teams](set-up-audio-conferencing-in-teams.md) and [Manage the Audio Conferencing settings for a user in Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span></span>

- <span data-ttu-id="2f755-133">会议组织者可以从会议中拨出。</span><span class="sxs-lookup"><span data-stu-id="2f755-133">Meeting organizer can dial-out from meetings.</span></span> <span data-ttu-id="2f755-134">若要了解有关详细信息，请参阅[管理](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)用户的音频会议设置Teams。</span><span class="sxs-lookup"><span data-stu-id="2f755-134">To learn more, see [Manage the Audio Conferencing settings for a user in Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span></span>

<span data-ttu-id="2f755-135">如果会议组织者未启用会议拨出功能，则"选择视频和音频选项"屏幕上的 **电话** 音频选项对任何人都不可用，并且其他用户无法收到加入会议的呼叫。</span><span class="sxs-lookup"><span data-stu-id="2f755-135">If the meeting organizer doesn't have dial-out from meetings enabled, the **Phone audio** option on the **Choose your video and audio options** screen isn't available to anyone, and other users can't receive a call to join them to the meeting.</span></span> <span data-ttu-id="2f755-136">对于启用了拨出功能的用户，加入会议后，他们可以加入其他人，通过"显示参与者"图标拨打 **其** 号码。</span><span class="sxs-lookup"><span data-stu-id="2f755-136">For users with dial-out enabled, once they have joined the meeting, they can join others dialing their number from the **Show participants** icon.</span></span>
