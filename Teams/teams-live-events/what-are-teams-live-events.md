---
title: 什么是 Microsoft Teams 实时事件？
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.collection:
- M365-collaboration
- m365initiative-meetings
- m365solution-spcomms
- m365solution-scenario
ms.reviewer: sonua
audience: admin
search.appverid: MET150
description: 了解实时事件如何让用户广播视频和内容，以增加 Teams、Yammer 和 Stream 中的在线受众。
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.liveevents
- ms.teamsadmincenter.liveevents.policies
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: 8f196e1539085966c22a775a784913ced417c9cb
ms.sourcegitcommit: 50111653f72f6758a3491a4dc3e91160ab75022c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2021
ms.locfileid: "51506719"
---
# <a name="what-are-microsoft-teams-live-events"></a><span data-ttu-id="71f82-103">Microsoft Teams 实时事件是什么</span><span class="sxs-lookup"><span data-stu-id="71f82-103">What are Microsoft Teams live events</span></span>

## <a name="overview"></a><span data-ttu-id="71f82-104">概述</span><span class="sxs-lookup"><span data-stu-id="71f82-104">Overview</span></span>

<span data-ttu-id="71f82-105">借助Teams直播活动，您的组织中的用户可以向大量在线观众广播视频和会议内容。</span><span class="sxs-lookup"><span data-stu-id="71f82-105">With Teams lives events, users in your organization can broadcast video and meeting content to large online audiences.</span></span>

<span data-ttu-id="71f82-106">Microsoft 365 实时事件将实时视频流式处理带到了新高度。</span><span class="sxs-lookup"><span data-stu-id="71f82-106">Microsoft 365 live events bring live video streaming to a new level.</span></span> <span data-ttu-id="71f82-107">实时事件鼓励在整个预订周期内，与参会者在实时事件前、中、后建立连接。</span><span class="sxs-lookup"><span data-stu-id="71f82-107">Live events encourage connection throughout the entire engagement lifecycle with attendees before, during, and after live events.</span></span> <span data-ttu-id="71f82-108">无论受众、团队或社区驻留在何处，都可以使用 Microsoft Stream、Teams 或 Yammer 创建实时事件。</span><span class="sxs-lookup"><span data-stu-id="71f82-108">You can create a live event wherever your audience, team, or community resides, using Microsoft Stream, Teams, or Yammer.</span></span>  

<span data-ttu-id="71f82-109">Teams 可以实现基于聊天的协作、呼叫、会议和实时事件，这样你可以展开会议的受众。</span><span class="sxs-lookup"><span data-stu-id="71f82-109">Teams delivers chat-based collaboration, calling, meetings, and live events, so you can expand the audience of your meetings.</span></span> <span data-ttu-id="71f82-110">Teams 实时事件是 Teams 会议的拓展，它使得用户能够向大体量网络受众广播视频和会议内容。</span><span class="sxs-lookup"><span data-stu-id="71f82-110">Teams live events is an extension of Teams meetings, enabling users to broadcast video and meeting content to a large online audience.</span></span> <span data-ttu-id="71f82-111">实时事件是一种一对多的通信，事件主持人领导交互，受众参与主要参与方式是查看主持人共享的内容。</span><span class="sxs-lookup"><span data-stu-id="71f82-111">Live events are meant for one-to-many communications where the host of the event is leading the interactions and audience participation is primarily to view the content shared by host.</span></span> <span data-ttu-id="71f82-112">与会者可以在 Yammer、Teams 或 Stream 中观看实时或录制的事件，并且可以使用主持的问答&或 Yammer 对话与演示者交互。</span><span class="sxs-lookup"><span data-stu-id="71f82-112">The attendees can watch the live or recorded event in Yammer, Teams, or Stream and can interact with the presenters using moderated Q & A or a Yammer conversation.</span></span>

<span data-ttu-id="71f82-113">Teams 实时事件是 Skype 会议直播的下一版本，会最终代替 Skype 会议直播中的功能。</span><span class="sxs-lookup"><span data-stu-id="71f82-113">Teams live events are considered the next version of Skype Meeting Broadcast and will eventually replace the capabilities provided in Skype Meeting Broadcast.</span></span> <span data-ttu-id="71f82-114">目前，Microsoft 将继续支持 Skype 会议直播，以及正在在组织中使用 Skype for Business 的用户，不会中断新的或未来事件的服务。</span><span class="sxs-lookup"><span data-stu-id="71f82-114">At this point, Microsoft will continue to support Skype Meeting Broadcast for users who are using Skype for Business in their organizations, with no disruption in service for new or future events.</span></span> <span data-ttu-id="71f82-115">但是，我们鼓励你尝试Teams活动，以使用所有令人兴奋的新功能，包括屏幕共享和外部硬件/软件编码器支持。</span><span class="sxs-lookup"><span data-stu-id="71f82-115">However, we encourage you to try out Teams live events to use all the new and exciting features including screen sharing and support for external hardware/software encoders.</span></span>

<span data-ttu-id="71f82-116">所以，让我们开始吧。</span><span class="sxs-lookup"><span data-stu-id="71f82-116">So, let's get started.</span></span> <span data-ttu-id="71f82-117">首先，看看下面的关系图，它显示了 Microsoft 365 实时事件中的高级组件及它们之间联系的方式。</span><span class="sxs-lookup"><span data-stu-id="71f82-117">First, take a look at the following diagram that shows high level components involved in Microsoft 365 live events and how they're connected.</span></span>

<span data-ttu-id="71f82-118">![实时事件的主要组件](../media/live-event-flow-diagram.png  "实时事件的主要组件，日程安排、生成、数据流平台和认证第三方 eCDN 提供商")</span><span class="sxs-lookup"><span data-stu-id="71f82-118">![The key components of live events](../media/live-event-flow-diagram.png  "Key components of live events, scheduling, production, Stream platform, certified third-party eCDN providers")</span></span>

> [!Note]
> <span data-ttu-id="71f82-119">我们希望强调，考虑到广播Teams的性质，实时事件通常超出会议 () 的正常情况。</span><span class="sxs-lookup"><span data-stu-id="71f82-119">We would like to emphasize that Teams Live Events, given the nature of broadcast technology, often exceed normal (internal) meeting populations.</span></span>
>
> <span data-ttu-id="71f82-120">与其他较大的媒体广播服务一样，我们依赖于内容交付网络将实时事件的内容传送给收件人。</span><span class="sxs-lookup"><span data-stu-id="71f82-120">As is the case with other larger reaching media broadcasting services, we rely on Content Delivery Networks to deliver the content for your live event to recipients.</span></span> <span data-ttu-id="71f82-121">此内容受加密方法的保护，受访问令牌授权，这些令牌仅基于实时事件会议配置颁发给收件人。</span><span class="sxs-lookup"><span data-stu-id="71f82-121">This content is protected by encryption methods and subject to authorization by access tokens that are only issued to recipients based on your live event meeting configuration.</span></span>
>
> <span data-ttu-id="71f82-122">应格外小心，确保会议内容适合如此多的受众，或者适当减少受众以适合敏感内容。</span><span class="sxs-lookup"><span data-stu-id="71f82-122">Extra care should be given to ensuring that either the meeting content is appropriate for such a large audience, or that the audience is appropriately reduced for sensitive content.</span></span>  
>
> <span data-ttu-id="71f82-123">与行业一样，对人员或基础结构等安全要素的泄漏可能会影响实时事件的安全性。</span><span class="sxs-lookup"><span data-stu-id="71f82-123">As is common in the industry, compromises to other elements of your security such as personnel or infrastructure, could impact the security of your live events.</span></span> <span data-ttu-id="71f82-124">组织应考虑在安全规划和练习中包括实时事件和其他广播服务。</span><span class="sxs-lookup"><span data-stu-id="71f82-124">Organizations should consider including Live Events and other broadcast service in their security planning and exercises.</span></span>

### <a name="event-group-roles"></a><span data-ttu-id="71f82-125">活动组角色</span><span class="sxs-lookup"><span data-stu-id="71f82-125">Event group roles</span></span>

<span data-ttu-id="71f82-126">实时事件Teams组织者、 (、演示者和与会者) 角色成功广播和参与活动。</span><span class="sxs-lookup"><span data-stu-id="71f82-126">Live events in Teams empower multiple roles (organizer, producer, presenter, and attendee) to successfully broadcast and participate in an event.</span></span> <span data-ttu-id="71f82-127">了解更多信息，请参阅[事件组角色](https://support.office.com/article/get-started-with-microsoft-teams-live-events-d077fec2-a058-483e-9ab5-1494afda578a?ui=en-US&rs=en-US&ad=US#bkmk_roles)。</span><span class="sxs-lookup"><span data-stu-id="71f82-127">To learn more, see [Event group roles](https://support.office.com/article/get-started-with-microsoft-teams-live-events-d077fec2-a058-483e-9ab5-1494afda578a?ui=en-US&rs=en-US&ad=US#bkmk_roles).</span></span>

## <a name="key-components"></a><span data-ttu-id="71f82-128">主要组件</span><span class="sxs-lookup"><span data-stu-id="71f82-128">Key components</span></span>

<span data-ttu-id="71f82-129">你可以看到上方的图片，在 Teams 中，有五个主要组件用于实时事件。</span><span class="sxs-lookup"><span data-stu-id="71f82-129">You can see from the picture above that there are five key components that are used with live events in Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="71f82-130">要查看关于设置实时事件以及与会者体验的概述，请查看此段[视频](https://support.office.com/article/video-plan-and-schedule-a-live-event-f92363a0-6d98-46d2-bdd9-f2248075e502)。</span><span class="sxs-lookup"><span data-stu-id="71f82-130">For an overview of how to set up live events and the attendee experience, check out these short [videos](https://support.office.com/article/video-plan-and-schedule-a-live-event-f92363a0-6d98-46d2-bdd9-f2248075e502).</span></span>

### <a name="scheduling"></a><span data-ttu-id="71f82-131">安排</span><span class="sxs-lookup"><span data-stu-id="71f82-131">Scheduling</span></span>

<span data-ttu-id="71f82-132">Teams 允许组织者创建具有相应与会者权限的事件、指定事件团队成员、选择制作方法和邀请与会者。</span><span class="sxs-lookup"><span data-stu-id="71f82-132">Teams provides the ability for the organizers to create an event with the appropriate attendee permissions, designate event team members, select a production method, and invite attendees.</span></span> <span data-ttu-id="71f82-133">如果实时事件是在 Yammer 组中创建的，实时事件与会者可以使用 Yammer 对话与事件中的人员进行交互。</span><span class="sxs-lookup"><span data-stu-id="71f82-133">If the live event was created from within a Yammer group, the live event attendees will be able to use Yammer conversation for interacting with people in the event.</span></span>

<span data-ttu-id="71f82-134">![新的实时事件屏幕](../media/teams-live-events-schedule.png "显示新实时事件屏幕的屏幕截图，显示新实时事件的创建和日程安排。")</span><span class="sxs-lookup"><span data-stu-id="71f82-134">![the New live events screen](../media/teams-live-events-schedule.png "Screen shot showing the New live event screen to create and schedule a new live event")</span></span>

> [!IMPORTANT]
> <span data-ttu-id="71f82-135">当用户脱机或以有限带宽运行时，Teams 不允许用户安排会议或直播活动。</span><span class="sxs-lookup"><span data-stu-id="71f82-135">Teams won't let users schedule meetings or live events when they're offline or running with limited bandwidth.</span></span>

### <a name="production"></a><span data-ttu-id="71f82-136">制作</span><span class="sxs-lookup"><span data-stu-id="71f82-136">Production</span></span>

<span data-ttu-id="71f82-137">此视频输入是实时事件的基础，它可以是单一网络摄像头，也可以是多摄像头专业视频制作设备。</span><span class="sxs-lookup"><span data-stu-id="71f82-137">The video input is the foundation of the live event and it can vary from a single webcam to a multi-camera professional video production.</span></span> <span data-ttu-id="71f82-138">Microsoft 365 中的实时事件支持多种生成场景，包括在 Teams 中用网络摄像头制作的事件或由外部应用或设备制作的事件。</span><span class="sxs-lookup"><span data-stu-id="71f82-138">The live events in Microsoft 365 support a spectrum of production scenarios, include an event produced in Teams using a webcam or an event produced in an external app or device.</span></span> <span data-ttu-id="71f82-139">你可以根据项目要求和预算选择不同选项。</span><span class="sxs-lookup"><span data-stu-id="71f82-139">You can choose these options depending on their project requirements and budget.</span></span> <span data-ttu-id="71f82-140">有两种方法可以生成事件：</span><span class="sxs-lookup"><span data-stu-id="71f82-140">There are two ways to produce events:</span></span>

- <span data-ttu-id="71f82-141">**Teams**：此制作方法允许用户从 Teams 房间系统使用网络摄像头或 A/V 输入生成实时事件。</span><span class="sxs-lookup"><span data-stu-id="71f82-141">**Teams**: This production method allows users to produce their live events in Teams using their webcam or using A/V input from Teams room systems.</span></span> <span data-ttu-id="71f82-142">当你想要使用连接到电脑的音频或视频设备或正在邀请远程演示者参与事件时，此选项是最好和最快的。</span><span class="sxs-lookup"><span data-stu-id="71f82-142">This option is the best and quickest option if you want to use the audio and video devices connected to the PC or are inviting remote presenters to participate in the event.</span></span> <span data-ttu-id="71f82-143">此选项允许用户轻松地通过输入的方式在事件中使用他们的网络摄像头并共享屏幕。</span><span class="sxs-lookup"><span data-stu-id="71f82-143">This option allows users to easily use their webcams and share their screen as input in the event.</span></span>

- <span data-ttu-id="71f82-144">**外部应用或设备**：外部编码器允许用户直接通过 [ Stream](https://stream.microsoft.com) 从外部硬件或基于软件的编码器生成实时事件。</span><span class="sxs-lookup"><span data-stu-id="71f82-144">**External app or device**: External encoders allow users to produce their live events directly from an external hardware or software-based encoder with [Stream](https://stream.microsoft.com).</span></span> <span data-ttu-id="71f82-145">当你已经具有工作室质量的设备（例如，媒体混合器），此设备需支持流式处理到实时消息协议 (RTMP) 服务，此选项是最好的。</span><span class="sxs-lookup"><span data-stu-id="71f82-145">This option is best if you already have studio quality equipment (for example, media mixers) which support streaming to a Real-time Messaging Protocol (RTMP) service.</span></span> <span data-ttu-id="71f82-146">此类制作经常用于大规模事件，例如行政会议 - 此场景下来自媒体混合器的单一数据流被广播给受众。</span><span class="sxs-lookup"><span data-stu-id="71f82-146">This type of production is typically used in large-scale events such as executive town halls – where a single stream from a media mixer is broadcasted to the audience.</span></span>

    <span data-ttu-id="71f82-147">![使用外部应用或设备生成的实时事件](../media/teams-live-events-external-encoder.png "使用外部应用或设备生成方法生成的实时事件的屏幕截图")</span><span class="sxs-lookup"><span data-stu-id="71f82-147">![a live event produced using an external app or device](../media/teams-live-events-external-encoder.png "Screen shot showing a live event that's produced by using the external app or device production method")</span></span>

>[!Note]
> <span data-ttu-id="71f82-p112">从使用 Microsoft Stream 到[使用 OneDrive for Business 和 SharePoint for meeting 进行会议录制](../tmr-meeting-recording-change.md)的改变将是分阶段进行的。在发布时，你将能够选择加入此体验，如果想继续使用 Stream，则在 11 月必须选择退出，在 2021 年初的某个时候，我们将要求所有客户使用 OneDrive for Business 和 SharePoint 进行新的会议录制。</span><span class="sxs-lookup"><span data-stu-id="71f82-p112">The change from using Microsoft Stream to [OneDrive for Business and SharePoint for meeting recordings](../tmr-meeting-recording-change.md) will be a phased approach. At launch you'll be able to opt-in to this experience, in November you'll have to opt-out if you want to continue using Stream, and some time in early 2021 we'll require all customers to use OneDrive for Business and SharePoint for new meeting recordings.</span></span>

### <a name="streaming-platform"></a><span data-ttu-id="71f82-150">流式处理平台</span><span class="sxs-lookup"><span data-stu-id="71f82-150">Streaming platform</span></span>

<span data-ttu-id="71f82-151">实时事件流式处理平台由以下部分组成：</span><span class="sxs-lookup"><span data-stu-id="71f82-151">The live event streaming platform is made up of the following pieces:</span></span>

- <span data-ttu-id="71f82-152">**Microsoft Azure 媒体服务**：[Microsoft Azure 媒体服务](/azure/media-services/previous/)提供给你广播质量的视频流式处理服务，以帮助你在现在最常用的移动设备上触及更大的受众群。</span><span class="sxs-lookup"><span data-stu-id="71f82-152">**Azure Media Services**:  [Azure Media Services](/azure/media-services/previous/) gives you broadcast-quality video streaming services to reach larger audiences on today’s most popular mobile devices.</span></span> <span data-ttu-id="71f82-153">媒体服务强化可及性、分发和可伸缩性，使得数据流内容能够轻松且低成本地传输到本地和世界的受众 - 同时保护你的内容。</span><span class="sxs-lookup"><span data-stu-id="71f82-153">Media Services enhances accessibility, distribution, and scalability, and makes it easy and cost-effective to stream content to your local or worldwide audiences — all while protecting your content.</span></span>
- <span data-ttu-id="71f82-154">**Azure 内容交付网络 (CDN)**：当你的数据流实时后，它将通过 [Azure 内容交付网络 (CDN)](/azure/cdn/) 交付。</span><span class="sxs-lookup"><span data-stu-id="71f82-154">**Azure Content Delivery Network (CDN)**:  Once your stream goes live, it's delivered through the [Azure Content Delivery Network (CDN)](/azure/cdn/).</span></span> <span data-ttu-id="71f82-155">Microsoft Azure 媒体服务提供集成的 CDN 作为流式处理端点。</span><span class="sxs-lookup"><span data-stu-id="71f82-155">Azure Media Services provides integrated CDN for streaming endpoints.</span></span> <span data-ttu-id="71f82-156">这允许数据流在世界范围内无需缓冲就能查看。</span><span class="sxs-lookup"><span data-stu-id="71f82-156">This allows the streams to be viewed worldwide with no buffering.</span></span>

### <a name="enterprise-content-delivery-network-ecdn"></a><span data-ttu-id="71f82-157">企业内容交付网络 (eCDN)</span><span class="sxs-lookup"><span data-stu-id="71f82-157">Enterprise Content Delivery Network (eCDN)</span></span>

<span data-ttu-id="71f82-158">eCDN 的目标是从 Internet 上获取视频内容，然后将内容分发到你的企业中而不受网络性能的影响。</span><span class="sxs-lookup"><span data-stu-id="71f82-158">The goal of eCDN is to take the video content from the internet and distribute the content throughout your enterprise without impacting network performance.</span></span> <span data-ttu-id="71f82-159">你可以使用下列认证的 eCDN 合作伙伴之一来优化你的网络，以支持组织内主持的实时事件：</span><span class="sxs-lookup"><span data-stu-id="71f82-159">You can use one of the following certified eCDN partners to optimize your network for live events held within your organization:</span></span>

- [<span data-ttu-id="71f82-160">Hive</span><span class="sxs-lookup"><span data-stu-id="71f82-160">Hive</span></span>](https://www.hivestreaming.com/partners/integration-partners/microsoft/)
- [<span data-ttu-id="71f82-161">Kollective</span><span class="sxs-lookup"><span data-stu-id="71f82-161">Kollective</span></span>](https://kollective.com/ecdn-solutions/microsoft-live-events/)
- [<span data-ttu-id="71f82-162">Ramp</span><span class="sxs-lookup"><span data-stu-id="71f82-162">Ramp</span></span>](https://rampecdn.com)
- [<span data-ttu-id="71f82-163">Riverbed</span><span class="sxs-lookup"><span data-stu-id="71f82-163">Riverbed</span></span>](https://www.riverbed.com/solutions/office-365.html)

### <a name="attendee-experience"></a><span data-ttu-id="71f82-164">与会者体验</span><span class="sxs-lookup"><span data-stu-id="71f82-164">Attendee experience</span></span>

<span data-ttu-id="71f82-165">与会者体验是实时事件最重要的方面，让与会者参与实时事件而不遇到任何问题非常关键。</span><span class="sxs-lookup"><span data-stu-id="71f82-165">The attendee experience is the most important aspect of live events and it's critical that the attendees can participate in the live event without having any issues.</span></span> <span data-ttu-id="71f82-166">与会者体验使用 Stream 播放器（用于 Teams 中生成的事件）和 Azure Media Player（用于外部应用或设备生成的事件），且支持桌面、浏览器和移动端 (iOS、Android)。</span><span class="sxs-lookup"><span data-stu-id="71f82-166">The attendee experience uses Stream Player (for events produced in Teams) and Azure Media Player (for events produced in an external app or device) and works across desktop, browser, and mobile (iOS, Android).</span></span> <span data-ttu-id="71f82-167">Microsoft 365 和 Office 365 提供 Yammer 和 Teams 作为两个协作中心，实时与会者体验集合到这些协作工具中。</span><span class="sxs-lookup"><span data-stu-id="71f82-167">Microsoft 365 and Office 365 provide Yammer and Teams as two collaboration hubs, and the live attendee experience is integrated into these collaboration tools.</span></span>

<span data-ttu-id="71f82-168">![实时事件与会者体验的例子](../media/teams-live-events-attendee.png "实时事件与会者体验的视频截图")</span><span class="sxs-lookup"><span data-stu-id="71f82-168">![Example of the live events attendee experience](../media/teams-live-events-attendee.png "Screen shot showing the live events attendee experience")</span></span>

### <a name="live-event-usage-report"></a><span data-ttu-id="71f82-169">实时事件使用情况报告</span><span class="sxs-lookup"><span data-stu-id="71f82-169">Live event usage report</span></span>

<span data-ttu-id="71f82-170">租户管理员可以在 Microsoft Teams 管理中心查看实时事件的实时使用情况分析。</span><span class="sxs-lookup"><span data-stu-id="71f82-170">Tenant admins can view real-time usage analytics for live events in Microsoft Teams admin center.</span></span>  <span data-ttu-id="71f82-171">[实时事件使用情况报告](../teams-analytics-and-reports/teams-live-event-usage-report.md)显示了组织内主持的实时事件的活动概述。</span><span class="sxs-lookup"><span data-stu-id="71f82-171">The [live event usage report](../teams-analytics-and-reports/teams-live-event-usage-report.md) shows the activity overview of the live events held in the organization.</span></span>  <span data-ttu-id="71f82-172">管理员可以查看使用情况信息，包括事件状态、开始时间、查看量和生成类型。</span><span class="sxs-lookup"><span data-stu-id="71f82-172">Admins can view event usage information, including event status, start time, views, and production type.</span></span>  

## <a name="next-steps"></a><span data-ttu-id="71f82-173">下一步</span><span class="sxs-lookup"><span data-stu-id="71f82-173">Next steps</span></span>

<span data-ttu-id="71f82-174">转到 [Teams 实时事件计划](plan-for-teams-live-events.md)。</span><span class="sxs-lookup"><span data-stu-id="71f82-174">Go to [Plan for Teams live events](plan-for-teams-live-events.md).</span></span>

### <a name="related-topics"></a><span data-ttu-id="71f82-175">相关主题</span><span class="sxs-lookup"><span data-stu-id="71f82-175">Related topics</span></span>

- [<span data-ttu-id="71f82-176">在 Yammer、Microsoft Teams 和 Microsoft Stream 之间的 Microsoft 365 实时事件</span><span class="sxs-lookup"><span data-stu-id="71f82-176">Live events across Microsoft 365 in Yammer, Microsoft Teams, and Microsoft Stream</span></span>](/stream/live-event-m365)
- [<span data-ttu-id="71f82-177">Microsoft Teams 直播活动入门</span><span class="sxs-lookup"><span data-stu-id="71f82-177">Get started with Microsoft Teams live events</span></span>](https://support.office.com/article/d077fec2-a058-483e-9ab5-1494afda578a)
- [<span data-ttu-id="71f82-178">Yammer 中的实时事件</span><span class="sxs-lookup"><span data-stu-id="71f82-178">Live events in Yammer</span></span>](https://support.office.com/article/live-events-in-yammer-4ece0ee2-c268-4636-bf2a-16e454befe57)
- [<span data-ttu-id="71f82-179">Microsoft Stream 中的实时事件</span><span class="sxs-lookup"><span data-stu-id="71f82-179">Live events in Microsoft Stream</span></span>](/stream/live-event-overview)
