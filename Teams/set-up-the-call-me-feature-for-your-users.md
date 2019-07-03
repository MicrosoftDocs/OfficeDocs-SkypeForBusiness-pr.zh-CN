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
# <a name="set-up-the-call-me-feature-for-your-users"></a><span data-ttu-id="cc873-103">为你的用户设置 "呼叫我" 功能</span><span class="sxs-lookup"><span data-stu-id="cc873-103">Set up the Call me feature for your users</span></span>

<span data-ttu-id="cc873-104">在 Microsoft 团队中, "**呼叫我**" 功能为用户提供了一种通过电话加入会议音频部分的方式。</span><span class="sxs-lookup"><span data-stu-id="cc873-104">In Microsoft Teams, the **Call me** feature gives users a way to join the audio portion of a meeting by phone.</span></span> <span data-ttu-id="cc873-105">这在可能无法使用计算机音频的情况下很方便。</span><span class="sxs-lookup"><span data-stu-id="cc873-105">This is handy in scenarios when using a computer for audio might not be possible.</span></span> <span data-ttu-id="cc873-106">用户通过其手机或土地线以及会议&mdash;的内容部分 (如另一个会议参与者共享他们的屏幕或通过其计算机播放视频&mdash;) 获取会议的音频部分。</span><span class="sxs-lookup"><span data-stu-id="cc873-106">Users get the audio portion of the meeting through their cell phone or land line and the content portion of the meeting&mdash;such when another meeting participant shares their screen or plays a video&mdash;through their computer.</span></span>

## <a name="the-user-experience"></a><span data-ttu-id="cc873-107">用户体验</span><span class="sxs-lookup"><span data-stu-id="cc873-107">The user experience</span></span>

<span data-ttu-id="cc873-108">单击 "**加入**" 加入会议, 然后单击 "**选择您的音频和视频设置**" 屏幕上的 "**电话音频**"。</span><span class="sxs-lookup"><span data-stu-id="cc873-108">Click **Join** to join a meeting, and then click **Phone audio** on the  **Choose your audio and video settings** screen.</span></span> <span data-ttu-id="cc873-109">在此, 用户可以进行会议呼叫并加入会议或手动拨入会议。</span><span class="sxs-lookup"><span data-stu-id="cc873-109">From here, users can have the meeting call and join them or dial in manually to the meeting.</span></span>

![电话音频选项的屏幕截图](media/set-up-the-call-me-feature-for-your-users-phone-audio.png)

<span data-ttu-id="cc873-111">**允许团队会议通话**</span><span class="sxs-lookup"><span data-stu-id="cc873-111">**Let the Teams meeting call**</span></span>

<span data-ttu-id="cc873-112">在 "**使用电话语音通话**" 屏幕上, 用户输入其电话号码, 然后单击 "**呼叫我**"。</span><span class="sxs-lookup"><span data-stu-id="cc873-112">On the **Use phone for audio** screen, the user enters their phone number, and then clicks **Call me**.</span></span> <span data-ttu-id="cc873-113">会议将调用用户并将其加入会议。</span><span class="sxs-lookup"><span data-stu-id="cc873-113">The meeting calls the user and joins them to the meeting.</span></span>

!["使用电话语音电话" 屏幕上的 "呼叫我" 选项的屏幕截图](media/set-up-the-call-me-feature-for-your-users-call-me.png)

<span data-ttu-id="cc873-115">**手动拨入**</span><span class="sxs-lookup"><span data-stu-id="cc873-115">**Dial in manually**</span></span>

<span data-ttu-id="cc873-116">加入的另一种方法是直接拨入会议。</span><span class="sxs-lookup"><span data-stu-id="cc873-116">Another way to join is to dial in directly to the meeting.</span></span> <span data-ttu-id="cc873-117">在 "**使用电话语音音频**" 屏幕上, 单击 "**手动拨入**" 以获取用于拨入会议的电话号码列表。</span><span class="sxs-lookup"><span data-stu-id="cc873-117">On the **Use phone for audio** screen, click **Dial in manually** to get a list of phone numbers to use to dial in to the meeting.</span></span>

![手动拨入选项的屏幕截图](media/set-up-the-call-me-feature-for-your-users-dial-in.png)

## <a name="set-up-the-call-me-feature"></a><span data-ttu-id="cc873-119">设置 "呼叫我" 功能</span><span class="sxs-lookup"><span data-stu-id="cc873-119">Set up the Call me feature</span></span>

<span data-ttu-id="cc873-120">若要为组织中的用户启用 "呼叫我" 功能, 必须配置以下内容:</span><span class="sxs-lookup"><span data-stu-id="cc873-120">To enable the Call me feature for users in your organization, the following must be configured:</span></span>

- <span data-ttu-id="cc873-121">为组织中安排会议的用户 (会议组织者) 启用音频会议。</span><span class="sxs-lookup"><span data-stu-id="cc873-121">Audio Conferencing is enabled for users in your organization who schedule meetings (meeting organizers).</span></span> <span data-ttu-id="cc873-122">若要了解详细信息, 请参阅[为团队设置音频会议](set-up-audio-conferencing-in-teams.md)和[管理团队中用户的音频会议设置](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="cc873-122">To learn more, see [Set up Audio Conferencing for Teams](set-up-audio-conferencing-in-teams.md) and [Manage the Audio Conferencing settings for a user in Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span></span>

- <span data-ttu-id="cc873-123">用户可以从会议拨出。</span><span class="sxs-lookup"><span data-stu-id="cc873-123">Users can dial out from meetings.</span></span> <span data-ttu-id="cc873-124">若要了解详细信息, 请参阅[管理团队用户的音频会议设置](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="cc873-124">To learn more, see [Manage the Audio Conferencing settings for a user in Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span></span>

<span data-ttu-id="cc873-125">如果用户未启用 "从会议拨出", 则 "**呼叫我**" 选项不可用, 并且用户将不会收到将其加入会议的呼叫。</span><span class="sxs-lookup"><span data-stu-id="cc873-125">If a user doesn't have dial out from meetings enabled, the **Call me** option isn't available and the user won't receive a call to join them to the meeting.</span></span> <span data-ttu-id="cc873-126">相反, 用户可以在 "**使用电话语音**" 屏幕上看到电话号码的列表, 他们可以使用它们在手机上手动拨入会议。</span><span class="sxs-lookup"><span data-stu-id="cc873-126">Instead, the user sees a list of phone numbers on the **Use phone for audio** screen that they can use to dial in manually to the meeting on their phone.</span></span>

