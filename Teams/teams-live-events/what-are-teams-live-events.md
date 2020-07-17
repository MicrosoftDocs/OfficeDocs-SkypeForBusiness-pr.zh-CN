---
title: Microsoft Teams 实时事件是什么？
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: sonua
audience: admin
search.appverid: MET150
description: 了解实时事件如何使用户能够将视频和内容广播到团队、Yammer 和流中的大型在线受众。
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.liveevents
- ms.teamsadmincenter.liveevents.policies
appliesto:
- Microsoft Teams
ms.openlocfilehash: 088643de889ee27d717d167b6166b9a43ec69256
ms.sourcegitcommit: a73df97a06ea860bfaf5387e0acbf3c724697e14
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "44902287"
---
# <a name="what-are-microsoft-teams-live-events"></a><span data-ttu-id="14b36-103">Microsoft Teams 实时事件是什么？</span><span class="sxs-lookup"><span data-stu-id="14b36-103">What are Microsoft Teams live events?</span></span>

## <a name="overview"></a><span data-ttu-id="14b36-104">概述</span><span class="sxs-lookup"><span data-stu-id="14b36-104">Overview</span></span>

<span data-ttu-id="14b36-105">通过团队实时事件，你组织中的用户可以将视频和会议内容广播到大型在线受众。</span><span class="sxs-lookup"><span data-stu-id="14b36-105">With Teams live events, users in your organization can broadcast video and meeting content to large online audiences.</span></span> 

<span data-ttu-id="14b36-106">Microsoft 365 实时事件将实时视频流转到新的级别，在整个服务生命周期中与与会者在实时事件之前、期间和之后鼓励其连接。</span><span class="sxs-lookup"><span data-stu-id="14b36-106">Microsoft 365 live events bring live video streaming to a new level, encouraging connection throughout the entire engagement lifecycle with attendees before, during, and after live events.</span></span> <span data-ttu-id="14b36-107">你可以使用 Microsoft Stream、团队或 Yammer 在你的受众、团队或社区所驻留的任何位置创建实时事件。</span><span class="sxs-lookup"><span data-stu-id="14b36-107">You can create a live event wherever your audience, team, or community resides, using Microsoft Stream, Teams, or Yammer.</span></span>  

<span data-ttu-id="14b36-108">团队提供基于聊天的协作、通话、会议和实时事件，因此您可以展开您的会议的受众。</span><span class="sxs-lookup"><span data-stu-id="14b36-108">Teams delivers chat-based collaboration, calling, meetings, and live events, so you can expand the audience of your meetings.</span></span> <span data-ttu-id="14b36-109">团队活动事件是团队会议的扩展，使用户能够将视频和会议内容广播给较大的联机受众。</span><span class="sxs-lookup"><span data-stu-id="14b36-109">Teams live events is an extension of Teams meetings, enabling users to broadcast video and meeting content to a large online audience.</span></span> <span data-ttu-id="14b36-110">这些内容适用于一对多通信，其中事件的主机在移动时主要是查看由主机共享的内容。</span><span class="sxs-lookup"><span data-stu-id="14b36-110">These are meant for one-to-many communications where the host of the event is leading the interactions and audience participation is primarily to view the content shared by host.</span></span> <span data-ttu-id="14b36-111">与会者可以在 Yammer、团队和/或流中观看实时或录制的事件，并且可以使用 & 或 Yammer 对话中的 "审核" 问答与演示者交互。</span><span class="sxs-lookup"><span data-stu-id="14b36-111">The attendees can watch the live or recorded event in Yammer, Teams, and/or Stream, and can interact with the presenters using moderated Q & A or a Yammer conversation.</span></span>

<span data-ttu-id="14b36-112">团队活动事件被视为下一版本的 Skype 会议直播，最终将替换 Skype 会议直播中提供的功能。</span><span class="sxs-lookup"><span data-stu-id="14b36-112">Teams live events are considered the next version of Skype Meeting Broadcast and will eventually replace the capabilities provided in Skype Meeting Broadcast.</span></span> <span data-ttu-id="14b36-113">在此情况下，Microsoft 将继续为在其组织中使用 Skype for Business 的用户继续支持 Skype 会议直播，而不会中断新事件或将来事件的服务。</span><span class="sxs-lookup"><span data-stu-id="14b36-113">At this point, Microsoft will continue to support Skype Meeting Broadcast for users who are using Skype for Business in their organizations, with no disruption in service for new or future events.</span></span> <span data-ttu-id="14b36-114">但是，我们鼓励你尝试使用团队实时事件来利用所有全新的激动人心的功能，包括屏幕共享和对外部硬件/软件编码器的支持。</span><span class="sxs-lookup"><span data-stu-id="14b36-114">However, we encourage you to try out Teams live events to leverage all the new and exciting features including screen sharing and support for external hardware/software encoders.</span></span>

<span data-ttu-id="14b36-115">因此，让我们开始吧。</span><span class="sxs-lookup"><span data-stu-id="14b36-115">So, let's get started.</span></span> <span data-ttu-id="14b36-116">首先，看看下图显示了 Microsoft 365 实时事件中涉及的高级组件以及它们的连接方式。</span><span class="sxs-lookup"><span data-stu-id="14b36-116">First, take a look at the following diagram that shows high level components involved in Microsoft 365 live events and how they are connected.</span></span> 

<span data-ttu-id="14b36-117">![显示实时事件的关键组件的图表](../media/teams-live-events.png  "图表显示实时事件、计划、生产、流平台、经过认证的第三方 eCDN 提供商的关键组件")</span><span class="sxs-lookup"><span data-stu-id="14b36-117">![Diagram showing key components of live events](../media/teams-live-events.png  "Diagram showing key components of live events, scheduling, production, Stream platform, certified third-party eCDN providers")</span></span>

### <a name="event-group-roles"></a><span data-ttu-id="14b36-118">事件组角色</span><span class="sxs-lookup"><span data-stu-id="14b36-118">Event group roles</span></span>
<span data-ttu-id="14b36-119">团队中的实时事件使多个角色（组织者、制造者、演示者和与会者）能够成功广播和参与事件。</span><span class="sxs-lookup"><span data-stu-id="14b36-119">Live events in Teams empowers multiple roles (organizer, producer, presenter, and attendee) to successfully broadcast and participate in an event.</span></span> <span data-ttu-id="14b36-120">若要了解详细信息，请参阅[事件组角色](https://support.office.com/article/get-started-with-microsoft-teams-live-events-d077fec2-a058-483e-9ab5-1494afda578a?ui=en-US&rs=en-US&ad=US#bkmk_roles)。</span><span class="sxs-lookup"><span data-stu-id="14b36-120">To learn more, see [Event group roles](https://support.office.com/article/get-started-with-microsoft-teams-live-events-d077fec2-a058-483e-9ab5-1494afda578a?ui=en-US&rs=en-US&ad=US#bkmk_roles).</span></span>

## <a name="key-components"></a><span data-ttu-id="14b36-121">关键组件</span><span class="sxs-lookup"><span data-stu-id="14b36-121">Key components</span></span>
<span data-ttu-id="14b36-122">您可以从上面的图片中看到，有四个关键组件与团队中的实时事件一起使用。</span><span class="sxs-lookup"><span data-stu-id="14b36-122">You can see from the picture above that there are four key components that are used with live events in Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="14b36-123">有关如何设置实时事件和与会者体验的概述，请查看这些简短[视频](https://support.office.com/article/video-plan-and-schedule-a-live-event-f92363a0-6d98-46d2-bdd9-f2248075e502)。</span><span class="sxs-lookup"><span data-stu-id="14b36-123">For an overview of how to set up live events and the attendee experience, check out these short [videos](https://support.office.com/article/video-plan-and-schedule-a-live-event-f92363a0-6d98-46d2-bdd9-f2248075e502).</span></span>

### <a name="scheduling"></a><span data-ttu-id="14b36-124">级</span><span class="sxs-lookup"><span data-stu-id="14b36-124">Scheduling</span></span>
<span data-ttu-id="14b36-125">团队使组织者能够使用相应的与会者权限创建事件、指定事件团队成员、选择生产方法和邀请与会者。</span><span class="sxs-lookup"><span data-stu-id="14b36-125">Teams provides the ability for the organizers to create an event with the appropriate attendee permissions, designate event team members, select a production method, and invite attendees.</span></span> <span data-ttu-id="14b36-126">如果实时事件是从 Yammer 组内创建的，则实时事件参与者将能够使用 Yammer 对话与事件中的人员交互。</span><span class="sxs-lookup"><span data-stu-id="14b36-126">If the live event was created from within a Yammer group, the live event attendees will be able to use Yammer conversation for interacting with people in the event.</span></span> 

<span data-ttu-id="14b36-127">![显示 "新的实时事件" 屏幕的屏幕截图](../media/teams-live-events-schedule.png "显示 "新建实时事件" 屏幕以创建和安排新实时事件的屏幕截图")</span><span class="sxs-lookup"><span data-stu-id="14b36-127">![Screenshot showing the New live events screen](../media/teams-live-events-schedule.png "Screen shot showing the New live event screen to create and schedule a new live event")</span></span>

### <a name="production"></a><span data-ttu-id="14b36-128">生成</span><span class="sxs-lookup"><span data-stu-id="14b36-128">Production</span></span>
<span data-ttu-id="14b36-129">视频输入是实时事件的基础，它可能会因单个网络摄像头而异。</span><span class="sxs-lookup"><span data-stu-id="14b36-129">The video input is the foundation of the live event and it can vary from a single webcam to a multi-camera professional video production.</span></span> <span data-ttu-id="14b36-130">Microsoft 365 中的实时事件支持各种生产方案，包括使用网络摄像头或在外部应用或设备中生成的事件在团队中生成的事件。</span><span class="sxs-lookup"><span data-stu-id="14b36-130">The live events in Microsoft 365 support a spectrum of production scenarios, include an event produced in Teams using a webcam or an event produced in an external app or device.</span></span> <span data-ttu-id="14b36-131">您可以根据其项目要求和预算选择这些选项。</span><span class="sxs-lookup"><span data-stu-id="14b36-131">You can choose these options depending on their project requirements and budget.</span></span> <span data-ttu-id="14b36-132">可通过两种方式生成事件：</span><span class="sxs-lookup"><span data-stu-id="14b36-132">There are two ways to produce events:</span></span>

- <span data-ttu-id="14b36-133">**团队**：此生产方法允许用户使用其网络摄像头在团队中生成活动事件，或使用来自团队室系统的/V 输入。</span><span class="sxs-lookup"><span data-stu-id="14b36-133">**Teams**: This production method allows users to produce their live events in Teams using their webcam or using A/V input from Teams room systems.</span></span> <span data-ttu-id="14b36-134">如果你想要使用连接到电脑或邀请远程演示者参与事件的音频和视频设备，此选项是最佳和最快的选项。</span><span class="sxs-lookup"><span data-stu-id="14b36-134">This option is the best and quickest option if you want to use the audio and video devices connected to the PC or are inviting remote presenters to participate in the event.</span></span> <span data-ttu-id="14b36-135">此选项允许用户轻松使用其网络摄像头并在事件中共享其屏幕作为输入。</span><span class="sxs-lookup"><span data-stu-id="14b36-135">This option allows users to easily use their webcams and share their screen as input in the event.</span></span> 

    <span data-ttu-id="14b36-136">![显示使用 "快速入门" 方法生成的实时事件的屏幕截图](../media/teams-live-events-quick-start.png "屏幕截图显示使用快速入门生产方法生成的实时事件")</span><span class="sxs-lookup"><span data-stu-id="14b36-136">![Screenshot showing a live event produced using quick start method](../media/teams-live-events-quick-start.png "Screen shot showing a live event that's produced by using the quick start production method")</span></span>

- <span data-ttu-id="14b36-137">**外部应用或设备**：外部编码器允许用户直接从具有[流](https://stream.microsoft.com)的外部硬件或基于软件的编码器生成实时事件。</span><span class="sxs-lookup"><span data-stu-id="14b36-137">**External app or device**: External encoders allow users to produce their live events directly from an external hardware or software-based encoder with [Stream](https://stream.microsoft.com).</span></span> <span data-ttu-id="14b36-138">如果你已经有了 studio 质量的设备（例如 media mixers），并且支持实时消息传递协议（RTMP）服务流，则此选项最适用。</span><span class="sxs-lookup"><span data-stu-id="14b36-138">This option is best if you already have studio quality equipment (for example, media mixers) which support streaming to a Real-time Messaging Protocol (RTMP) service.</span></span> <span data-ttu-id="14b36-139">这种类型的生产通常在大规模事件中使用，如 executive 城镇 halls-将媒体混合器中的单个流广播给观众。</span><span class="sxs-lookup"><span data-stu-id="14b36-139">This type of production is typically used in large scale events such as executive town halls – where a single stream from a media mixer is broadcasted to the audience.</span></span> 

    <span data-ttu-id="14b36-140">![显示使用外部应用或设备生成的实时事件的屏幕截图](../media/teams-live-events-external-encoder.png "显示使用外部应用或设备生产方法生成的实时事件的屏幕截图")</span><span class="sxs-lookup"><span data-stu-id="14b36-140">![Screenshot showing a live event produced using an external app or device](../media/teams-live-events-external-encoder.png "Screen shot showing a live event that's produced by using the external app or device production method")</span></span>

### <a name="streaming-platform"></a><span data-ttu-id="14b36-141">流式处理平台</span><span class="sxs-lookup"><span data-stu-id="14b36-141">Streaming platform</span></span>
<span data-ttu-id="14b36-142">实时事件流平台由以下部分组成：</span><span class="sxs-lookup"><span data-stu-id="14b36-142">The live event streaming platform is made up of the following pieces:</span></span>

- <span data-ttu-id="14b36-143">**Azure 媒体服务**： [azure 媒体服务](https://docs.microsoft.com/azure/media-services/previous/)为你提供了一种广播质量的视频流服务，可在当今最常用的移动设备上与更大的受众联系。</span><span class="sxs-lookup"><span data-stu-id="14b36-143">**Azure Media Services**:  [Azure Media Services](https://docs.microsoft.com/azure/media-services/previous/) gives you broadcast-quality video streaming services to reach larger audiences on today’s most popular mobile devices.</span></span> <span data-ttu-id="14b36-144">媒体服务增强了辅助功能、分发和可伸缩性，并让您能够轻松、经济高效地将内容流式传输给您的本地或全球受众，同时保护内容。</span><span class="sxs-lookup"><span data-stu-id="14b36-144">Media Services enhances accessibility, distribution, and scalability, and makes it easy and cost-effective to stream content to your local or worldwide audiences — all while protecting your content.</span></span>
- <span data-ttu-id="14b36-145">**Azure 内容交付网络（CDN）**：一旦你的流投入使用，它将通过[Azure 内容交付网络（cdn）](https://docs.microsoft.com/azure/cdn/)进行传递。</span><span class="sxs-lookup"><span data-stu-id="14b36-145">**Azure Content Delivery Network (CDN)**:  Once your stream goes live, it's delivered through the [Azure Content Delivery Network (CDN)](https://docs.microsoft.com/azure/cdn/).</span></span> <span data-ttu-id="14b36-146">Azure 媒体服务为流式处理终结点提供集成的 CDN。</span><span class="sxs-lookup"><span data-stu-id="14b36-146">Azure Media Services provides integrated CDN for streaming endpoints.</span></span> <span data-ttu-id="14b36-147">这允许在全球查看流，无缓冲。</span><span class="sxs-lookup"><span data-stu-id="14b36-147">This allows the streams to be viewed worldwide with no buffering.</span></span>

### <a name="enterprise-content-delivery-network-ecdn"></a><span data-ttu-id="14b36-148">企业内容交付网络（eCDN）</span><span class="sxs-lookup"><span data-stu-id="14b36-148">Enterprise Content Delivery Network (eCDN)</span></span>
<span data-ttu-id="14b36-149">ECDN 的目标是从 internet 获取视频内容，并在整个企业中分发内容，而不会影响网络性能。</span><span class="sxs-lookup"><span data-stu-id="14b36-149">The goal of eCDN is to take the video content from the internet and distribute the content throughout your enterprise without impacting network performance.</span></span> <span data-ttu-id="14b36-150">您可以使用以下认证的 eCDN 合作伙伴之一来优化您的网络，以便在您的组织内保持实时事件：</span><span class="sxs-lookup"><span data-stu-id="14b36-150">You can use one of the following certified eCDN partners to optimize your network for live events held within your organization:</span></span>
- [<span data-ttu-id="14b36-151">配置单元</span><span class="sxs-lookup"><span data-stu-id="14b36-151">Hive</span></span>](https://www.hivestreaming.com/partners/integration-partners/microsoft/)
- [<span data-ttu-id="14b36-152">Kollective</span><span class="sxs-lookup"><span data-stu-id="14b36-152">Kollective</span></span>](https://kollective.com/ecdn-solutions/microsoft-live-events/)
- [<span data-ttu-id="14b36-153">渐变</span><span class="sxs-lookup"><span data-stu-id="14b36-153">Ramp</span></span>](https://rampecdn.com)

### <a name="attendee-experience"></a><span data-ttu-id="14b36-154">与会者体验</span><span class="sxs-lookup"><span data-stu-id="14b36-154">Attendee experience</span></span> 
<span data-ttu-id="14b36-155">与会者体验是实时事件的最重要的方面，并且很重要的是与会者无需任何问题即可参与实时事件。</span><span class="sxs-lookup"><span data-stu-id="14b36-155">The attendee experience is the most important aspect of live events and it's critical that the attendees can participate in the live event without having any issues.</span></span> <span data-ttu-id="14b36-156">与会者体验使用流式播放机（适用于团队中生成的事件）和 Azure 媒体播放器（对于在外部应用或设备中生成的事件），并跨桌面、浏览器和移动设备（iOS、Android）工作。</span><span class="sxs-lookup"><span data-stu-id="14b36-156">The attendee experience uses Stream Player (for events produced in Teams) and Azure Media Player (for events produced in an external app or device) and works across desktop, browser, and mobile (iOS, Android).</span></span> <span data-ttu-id="14b36-157">Microsoft 365 和 Office 365 将 Yammer 和团队作为两个协作中心提供，并将实时与会者体验集成到这些协作工具中。</span><span class="sxs-lookup"><span data-stu-id="14b36-157">Microsoft 365 and Office 365 provide Yammer and Teams as two collaboration hubs, and the live attendee experience is integrated into these collaboration tools.</span></span> 

<span data-ttu-id="14b36-158">![显示实时事件与会者体验的屏幕截图](../media/teams-live-events-attendee.png "显示实时事件与会者体验的屏幕截图")</span><span class="sxs-lookup"><span data-stu-id="14b36-158">![Screenshot showing the live events attendee experience](../media/teams-live-events-attendee.png "Screen shot showing the live events attendee experience")</span></span>

### <a name="live-event-usage-report"></a><span data-ttu-id="14b36-159">实时事件使用率报告</span><span class="sxs-lookup"><span data-stu-id="14b36-159">Live event usage report</span></span> 
<span data-ttu-id="14b36-160">租户管理员可在 Microsoft 团队管理中心中查看实时事件的实时使用情况分析。</span><span class="sxs-lookup"><span data-stu-id="14b36-160">Tenant admins can view real time usage analytics for live events in Microsoft Teams admin center.</span></span>  <span data-ttu-id="14b36-161">[实时事件使用情况报表](../teams-analytics-and-reports/teams-live-event-usage-report.md)显示组织中保留的实时事件的活动概述。</span><span class="sxs-lookup"><span data-stu-id="14b36-161">The [live event usage report](../teams-analytics-and-reports/teams-live-event-usage-report.md) shows the activity overview of the live events held in the organization.</span></span>  <span data-ttu-id="14b36-162">管理员可以查看事件使用信息，包括事件状态、开始时间、视图和生产类型。</span><span class="sxs-lookup"><span data-stu-id="14b36-162">Admins can view event usage information, including event status, start time, views and production type.</span></span>  

## <a name="next-steps"></a><span data-ttu-id="14b36-163">后续步骤</span><span class="sxs-lookup"><span data-stu-id="14b36-163">Next steps</span></span>
<span data-ttu-id="14b36-164">转到 "[规划团队实时事件](plan-for-teams-live-events.md)"。</span><span class="sxs-lookup"><span data-stu-id="14b36-164">Go to [Plan for Teams live events](plan-for-teams-live-events.md).</span></span>

### <a name="related-topics"></a><span data-ttu-id="14b36-165">相关主题</span><span class="sxs-lookup"><span data-stu-id="14b36-165">Related topics</span></span>
- [<span data-ttu-id="14b36-166">Yammer、Microsoft 团队和 Microsoft Stream 中跨 Microsoft 365 的实时事件</span><span class="sxs-lookup"><span data-stu-id="14b36-166">Live events across Microsoft 365 in Yammer, Microsoft Teams, and Microsoft Stream</span></span>](https://docs.microsoft.com/stream/live-event-m365)
- [<span data-ttu-id="14b36-167">Microsoft Teams 直播活动入门</span><span class="sxs-lookup"><span data-stu-id="14b36-167">Get started with Microsoft Teams live events</span></span>](https://support.office.com/article/d077fec2-a058-483e-9ab5-1494afda578a)
- [<span data-ttu-id="14b36-168">Yammer 中的实时事件</span><span class="sxs-lookup"><span data-stu-id="14b36-168">Live events in Yammer</span></span>](https://support.office.com/article/live-events-in-yammer-4ece0ee2-c268-4636-bf2a-16e454befe57)
- [<span data-ttu-id="14b36-169">Microsoft Stream 中的实时事件</span><span class="sxs-lookup"><span data-stu-id="14b36-169">Live events in Microsoft Stream</span></span>](https://docs.microsoft.com/stream/live-event-overview)

 
