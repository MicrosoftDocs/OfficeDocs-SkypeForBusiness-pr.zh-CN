---
title: 在 Skype for Business 服务器中规划大型会议
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 21507e18-bd79-4019-9c3a-0867fccaa3b4
description: 摘要：阅读本主题，了解在 Skype for Business 服务器中实施和管理大型会议的最佳做法。
ms.openlocfilehash: 136896a45be36508af419d84bc5bd684c9d8a429
ms.sourcegitcommit: 9fd23cf0e03dd8fcf7ed04ef09dcdac048ebb44a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2019
ms.locfileid: "34696041"
---
# <a name="plan-for-large-meetings-in-skype-for-business-server"></a><span data-ttu-id="8b38d-103">在 Skype for Business 服务器中规划大型会议</span><span class="sxs-lookup"><span data-stu-id="8b38d-103">Plan for large meetings in Skype for Business Server</span></span>
 
<span data-ttu-id="8b38d-104">**摘要：** 阅读本主题，了解在 Skype for Business 服务器中实施和管理大型会议的最佳做法。</span><span class="sxs-lookup"><span data-stu-id="8b38d-104">**Summary:** Read this topic to learn about best practices for implementing and managing large meetings in Skype for Business Server.</span></span>
  
<span data-ttu-id="8b38d-105">Skype for Business 服务器可以支持的会议的大小取决于会议是否托管在共享池上的250参与者和专用池上的1000参与者。</span><span class="sxs-lookup"><span data-stu-id="8b38d-105">The size of meetings that Skype for Business Server can support depends on whether conferencing is hosted on a shared or dedicated pool: anywhere from 250 participants on a shared pool to 1000 participants on a dedicated pool.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="8b38d-106">本主题重点介绍 Skype for business 服务器支持的大型会议的最佳做法。</span><span class="sxs-lookup"><span data-stu-id="8b38d-106">This topic focuses on best practices for large meetings supported by Skype for Business Server.</span></span> <span data-ttu-id="8b38d-107">如果您的组织需要更大的会议功能，您应该考虑实施利用 Skype 会议直播的混合环境，这是 Office 365 中的一种新的在线服务。</span><span class="sxs-lookup"><span data-stu-id="8b38d-107">If your organization requires larger meeting capabilities, you should consider implementing a hybrid environment that takes advantage of Skype Meeting Broadcast, a new online service that is part of Office 365.</span></span> 

> [!NOTE]
> <span data-ttu-id="8b38d-108">Skype 会议直播使用户可以向多达10000个参与者的大型联机受众主持和广播会议。</span><span class="sxs-lookup"><span data-stu-id="8b38d-108">Skype Meeting Broadcast enables users to host and broadcast meetings to large online audiences of up to 10,000 participants.</span></span> <span data-ttu-id="8b38d-109">使用 Skype 会议直播需要在具有生产 Office 365 租户的混合设置中配置 Skype for business 服务器。</span><span class="sxs-lookup"><span data-stu-id="8b38d-109">The use of Skype Meeting Broadcast requires that Skype for Business Server already be configured in a hybrid setup with a production Office 365 tenant.</span></span> <span data-ttu-id="8b38d-110">所有用户都必须具有作为先决条件建立的联机租户。</span><span class="sxs-lookup"><span data-stu-id="8b38d-110">All users must have an online tenant established as a prerequisite.</span></span> <span data-ttu-id="8b38d-111">如果您有兴趣部署可利用 Skype 会议直播的混合解决方案，请参阅[什么是 Skype 会议直播？](https://go.microsoft.com/fwlink/?LinkId=617071)并[为 Skype 会议直播配置内部部署](../../deploy/configure-skype-meeting-broadcast.md)。</span><span class="sxs-lookup"><span data-stu-id="8b38d-111">If you are interested in deploying a hybrid solution that can take advantage of Skype Meeting Broadcast, see [What is a Skype Meeting Broadcast?](https://go.microsoft.com/fwlink/?LinkId=617071) and [Configure your on-premises deployment for Skype Meeting Broadcast](../../deploy/configure-skype-meeting-broadcast.md).</span></span> 
  
<span data-ttu-id="8b38d-112">大型会议通常具有以下特征：</span><span class="sxs-lookup"><span data-stu-id="8b38d-112">Large meetings typically have the following characteristics:</span></span>
  
- <span data-ttu-id="8b38d-113">会议形式为一对多的演示。</span><span class="sxs-lookup"><span data-stu-id="8b38d-113">The meeting format is a one-to-many presentation.</span></span>
    
- <span data-ttu-id="8b38d-114">一个或一些用户为演示者，并且所有人只能作为出席者参与。</span><span class="sxs-lookup"><span data-stu-id="8b38d-114">One or a few users are presenters, and everyone else participates only as attendees.</span></span>
    
- <span data-ttu-id="8b38d-115">PowerPoint 演示文稿共享是主要数据协作活动。</span><span class="sxs-lookup"><span data-stu-id="8b38d-115">PowerPoint presentation sharing is the main data collaboration activity.</span></span>
    
- <span data-ttu-id="8b38d-116">需要音频，还可能使用视频。</span><span class="sxs-lookup"><span data-stu-id="8b38d-116">Audio is required and video may also be used.</span></span>
    
- <span data-ttu-id="8b38d-117">专门人员（一般是会议组织者或组织者的助手）提前设置好会议。</span><span class="sxs-lookup"><span data-stu-id="8b38d-117">A dedicated person, generally either the meeting organizer or an assistant to the organizer, sets up the meeting well in advance.</span></span>
    
- <span data-ttu-id="8b38d-118">专门人员（不是演示者）运行会议，包括根据需要连接到联机会议、验证音频、视频和幻灯片共享工作、管理会议厅和用户角色、将参与者静音和取消静音、提问和管理记录。</span><span class="sxs-lookup"><span data-stu-id="8b38d-118">Dedicated staff (not the presenters) runs the meeting, including connecting to an online meeting, verifying that audio, video, and slide sharing work, managing lobby and user roles, muting and unmuting participants, taking questions, and managing recordings, as appropriate.</span></span>
    
<span data-ttu-id="8b38d-119">当用户安排会议时，Skype for Business 服务器在会议数据库中创建一条记录，用于存储会议数据，但不会提前为计划会议保留任何硬件资源。</span><span class="sxs-lookup"><span data-stu-id="8b38d-119">When a user schedules a meeting, Skype for Business Server creates a record in the conferencing database, which stores conferencing data, but does not reserve any hardware resources for the scheduled meeting ahead of time.</span></span> <span data-ttu-id="8b38d-120">相反，Skype for Business 服务器具有内置负载平衡逻辑，可通过在池中的所有前端服务器上平均分配负载的方式在前端服务器上动态分配会议资源。</span><span class="sxs-lookup"><span data-stu-id="8b38d-120">Instead, Skype for Business Server has built-in load balancing logic to dynamically allocate conferencing resources on Front End Servers in a way that distributes loads equally across all Front End Servers in the pool.</span></span> <span data-ttu-id="8b38d-121">这样做可以有效调配和使用硬件资源，但重要的是，应相应地作出规划来支持较大规模的会议。</span><span class="sxs-lookup"><span data-stu-id="8b38d-121">This effectively provisions and uses hardware resources, but it is important that you plan appropriately to support very large meetings.</span></span> 
  
<span data-ttu-id="8b38d-122">例如，当 Skype for Business 服务器池的运行接近其最大容量时，每台前端服务器可能会托管大约125平均大小的会议。</span><span class="sxs-lookup"><span data-stu-id="8b38d-122">For example, when a Skype for Business Server pool is running close to its top capacity, each Front End Server might host approximately 125 average-size meetings.</span></span> <span data-ttu-id="8b38d-123">再添加一个小型会议不会有问题，但是添加一个 1000 用户的会议就会出现问题，因为前端服务器可能无法在已有其他 125 个会议的同时支持这样的大型会议。</span><span class="sxs-lookup"><span data-stu-id="8b38d-123">Adding another small meeting would not be a problem, but adding a meeting for 1000 users would be a problem because the Front End Servers would probably not be able to support such a large meeting at the same time as the other 125 meetings.</span></span>
  
<span data-ttu-id="8b38d-124">支持多达 1000 名参与者的大型会议需要解决与共享硬件模型和无保留模型相关的问题。</span><span class="sxs-lookup"><span data-stu-id="8b38d-124">Supporting large meetings of up to 1000 participants requires addressing the issues related to both the shared hardware model and the no-reservation model.</span></span> <span data-ttu-id="8b38d-125">一般情况下，你需要针对专用池进行规划，并按照以下部分中所述执行最佳做法。</span><span class="sxs-lookup"><span data-stu-id="8b38d-125">In general, you need to plan for a dedicated pool and follow best practices as described in the following sections.</span></span> 
  
## <a name="plan-for-a-dedicated-pool"></a><span data-ttu-id="8b38d-126">规划专用池</span><span class="sxs-lookup"><span data-stu-id="8b38d-126">Plan for a dedicated pool</span></span>

<span data-ttu-id="8b38d-127">如果组织需要超过 250 名参与者的会议，您需要规划专用池来支持该负载。</span><span class="sxs-lookup"><span data-stu-id="8b38d-127">If your organization requires meetings with greater than 250 participants, you need to plan for a dedicated pool to support the load.</span></span> 
  
<span data-ttu-id="8b38d-128">为了给多达 1000 个用户的会议提供充足的 CPU 和会议资源，宿主前端服务器不应承载任何其他即时消息 (IM) 和状态或企业语音工作负荷。</span><span class="sxs-lookup"><span data-stu-id="8b38d-128">To have sufficient CPU and memory resources for meetings of up to 1000 users, the hosting Front End Servers should not host any other instant messaging (IM) and presence or Enterprise Voice workloads.</span></span> <span data-ttu-id="8b38d-129">该服务器还不应承载任何其他会议，无论其他会议的规模如何。</span><span class="sxs-lookup"><span data-stu-id="8b38d-129">The servers should also not host any other meetings, regardless of the size of the other meetings.</span></span> <span data-ttu-id="8b38d-130">若要托管最多为1000用户的会议，你需要设置单独的 Skype for Business 服务器池，专用于托管大型会议。</span><span class="sxs-lookup"><span data-stu-id="8b38d-130">To host meetings of up to 1000 users, you need to set up a separate Skype for Business Server pool that is dedicated to hosting large meetings.</span></span>
  
<span data-ttu-id="8b38d-131">专用于托管大型会议的 Skype for business Server 池应同时托管一个会议和最多1000个用户，因此需要通过带外计划流程提前保留会议时间，以确保从前端服务器。</span><span class="sxs-lookup"><span data-stu-id="8b38d-131">A Skype for Business Server pool that is dedicated to hosting large meetings should host one and only one meeting of up to 1000 users at the same time, so meeting times need to be reserved in advance via an out of band scheduling process to ensure dedicated support from the Front End Servers.</span></span> <span data-ttu-id="8b38d-132">若要同时支持多个大型会议，应设置多个专用的大型会议池。</span><span class="sxs-lookup"><span data-stu-id="8b38d-132">To support more than one large meeting at the same time, you should set up multiple dedicated large-meeting pools.</span></span>
  
<span data-ttu-id="8b38d-133">有关硬件和软件要求以及规划支持大型会议的拓扑的详细信息，请参阅[Skype For Business 服务器中的会议硬件和软件要求](hardware-and-software-requirements.md)和[规划你的会议拓扑Skype for Business 服务器](conferencing-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="8b38d-133">For more information about hardware and software requirements, and planning a topology that supports large meetings, see [Hardware and software requirements for conferencing in Skype for Business Server](hardware-and-software-requirements.md) and [Plan your conferencing topology for Skype for Business Server](conferencing-topology.md).</span></span>
  
## <a name="implement-best-practices-for-large-meetings"></a><span data-ttu-id="8b38d-134">实施大型会议的最佳做法</span><span class="sxs-lookup"><span data-stu-id="8b38d-134">Implement best practices for large meetings</span></span>

<span data-ttu-id="8b38d-p108">在为大型会议设置了专用池之后，您可以采取相应的步骤，帮助确保托管在池中的大型会议提供最佳的用户体验。下面几节提供管理大型会议的准则：</span><span class="sxs-lookup"><span data-stu-id="8b38d-p108">After setting up a dedicated pool for large meetings, you can take steps to help ensure that large meetings hosted in the pool provide the best user experience. The following sections provide guidelines for managing large meetings:</span></span>
  
- <span data-ttu-id="8b38d-137">创建专门的会议组织者</span><span class="sxs-lookup"><span data-stu-id="8b38d-137">Create dedicated meeting organizers</span></span>
    
- <span data-ttu-id="8b38d-138">创建专门的主持人</span><span class="sxs-lookup"><span data-stu-id="8b38d-138">Create dedicated moderators</span></span>
    
- <span data-ttu-id="8b38d-139">维护单独的大型会议日历</span><span class="sxs-lookup"><span data-stu-id="8b38d-139">Maintain a separate calendar of large meetings</span></span>
    
- <span data-ttu-id="8b38d-140">实施大型会议日程安排过程</span><span class="sxs-lookup"><span data-stu-id="8b38d-140">Implement a large-meeting scheduling process</span></span>
    
- <span data-ttu-id="8b38d-141">指定相应的日程安排详细信息</span><span class="sxs-lookup"><span data-stu-id="8b38d-141">Specify appropriate scheduling details</span></span>
    
- <span data-ttu-id="8b38d-142">创建大型会议的会议策略</span><span class="sxs-lookup"><span data-stu-id="8b38d-142">Create a conferencing policy for large meetings</span></span>
    
### <a name="create-dedicated-meeting-organizers"></a><span data-ttu-id="8b38d-143">创建专门的会议组织者</span><span class="sxs-lookup"><span data-stu-id="8b38d-143">Create dedicated meeting organizers</span></span>

<span data-ttu-id="8b38d-144">为最大限度地减少大型会议池中的实时通信流量，Microsoft 不建议托管使用 Skype for Business 客户端定期登录并参与即时消息（IM）、状态、会议和语音会议的用户。</span><span class="sxs-lookup"><span data-stu-id="8b38d-144">To minimize the real-time communications traffic in the large-meeting pool, Microsoft does not recommend hosting users who regularly sign in using Skype for Business clients and participate in instant messaging (IM), presence, conferencing, and voice sessions.</span></span> <span data-ttu-id="8b38d-145">请改为执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="8b38d-145">Instead, do one of the following:</span></span>
  
- <span data-ttu-id="8b38d-146">创建一个或多个仅安排大型会议的专用用户帐户</span><span class="sxs-lookup"><span data-stu-id="8b38d-146">Create one or more dedicated user accounts just for scheduling large meetings</span></span>
    
- <span data-ttu-id="8b38d-147">托管负责在大型会议池中安排大型会议的员工的用户帐户</span><span class="sxs-lookup"><span data-stu-id="8b38d-147">Home the user accounts of the staff responsible for scheduling large meetings on a large-meeting pool</span></span>
    
### <a name="create-dedicated-moderators"></a><span data-ttu-id="8b38d-148">创建专门的主持人</span><span class="sxs-lookup"><span data-stu-id="8b38d-148">Create dedicated moderators</span></span>

<span data-ttu-id="8b38d-149">如果会议中有数百到数千名用户，好的做法是，有专门人员主持大型会议的联机会话。</span><span class="sxs-lookup"><span data-stu-id="8b38d-149">With several hundred to a thousand users in a meeting, it is a good practice to have a dedicated person moderate the online session of a large meeting.</span></span> <span data-ttu-id="8b38d-150">此专职人员可以是会议组织者的代理人，也可以是组织的大型会议支持人员的成员。</span><span class="sxs-lookup"><span data-stu-id="8b38d-150">This dedicated person can be a delegate of the meeting organizer or a member of the organization's large-meeting support staff.</span></span> <span data-ttu-id="8b38d-151">尽管可以在会议进行时将某个联机与会者升级为演示者角色，但在计划会议时添加专门的会议主持人作为演示者仍非常重要。</span><span class="sxs-lookup"><span data-stu-id="8b38d-151">It is important to add the dedicated meeting moderator as a presenter at the time that the meeting is scheduled, although it is possible to promote an online meeting attendee to the presenter role while the meeting is in progress.</span></span>
  
<span data-ttu-id="8b38d-152">会议审阅者可以使用 Skype for Business 客户端的所有演示者功能来管理大型会议。</span><span class="sxs-lookup"><span data-stu-id="8b38d-152">The meeting moderator can use all presenter functionalities of Skype for Business clients to manage the large meeting.</span></span> <span data-ttu-id="8b38d-153">这些功能包括：</span><span class="sxs-lookup"><span data-stu-id="8b38d-153">These functionalities include:</span></span>
  
- <span data-ttu-id="8b38d-154">监控会议厅并允许和拒绝会议厅中的用户</span><span class="sxs-lookup"><span data-stu-id="8b38d-154">Monitoring the lobby and admitting or rejecting users in the lobby</span></span>
    
- <span data-ttu-id="8b38d-155">将任何不应留在会议中的用户从会议中移除</span><span class="sxs-lookup"><span data-stu-id="8b38d-155">Removing any users from the meeting who should not be in the meeting</span></span>
    
- <span data-ttu-id="8b38d-156">更改会议访问类型</span><span class="sxs-lookup"><span data-stu-id="8b38d-156">Changing meeting access types</span></span>
    
- <span data-ttu-id="8b38d-157">更改参与者角色</span><span class="sxs-lookup"><span data-stu-id="8b38d-157">Changing participant roles</span></span>
    
- <span data-ttu-id="8b38d-158">在会议期间使用拖放功能、电话拨出或电子邮件邀请其他参与者</span><span class="sxs-lookup"><span data-stu-id="8b38d-158">Inviting additional participants during the meeting using drag and drop functionality, phone dial out, or email</span></span>
    
- <span data-ttu-id="8b38d-159">使观众或个别用户静音/取消静音</span><span class="sxs-lookup"><span data-stu-id="8b38d-159">Muting and unmuting the audience or individual users</span></span>
    
- <span data-ttu-id="8b38d-160">管理会议内容，包括上载内容、删除内容和切换活动内容</span><span class="sxs-lookup"><span data-stu-id="8b38d-160">Managing meeting content, including uploading content, deleting content, and switching active content</span></span>

    
### <a name="maintain-a-separate-calendar"></a><span data-ttu-id="8b38d-161">维护单独的日历</span><span class="sxs-lookup"><span data-stu-id="8b38d-161">Maintain a separate calendar</span></span>

<span data-ttu-id="8b38d-162">对于每个大型会议池，您应在该池上维护一个单独的已计划大型会议的日历。</span><span class="sxs-lookup"><span data-stu-id="8b38d-162">For each large-meeting pool, you should maintain a separate calendar of large meetings scheduled on that pool.</span></span> <span data-ttu-id="8b38d-163">例如，你可以在大会议池中使用单个用户帐户，并将 Outlook 与 Skype for business 的 Exchange 和联机会议外接程序配合使用来维护单独的日历。</span><span class="sxs-lookup"><span data-stu-id="8b38d-163">For example, you can home a single user account on the large-meeting pool and use Outlook with Exchange and Online Meeting Add-in for Skype for Business to maintain a separate calendar.</span></span> <span data-ttu-id="8b38d-164">如果使用多个用户帐户来允许支持人员创建大型会议，则可设置一个单独的日历，以聚合支持人员的成员创建的所有大型会议。</span><span class="sxs-lookup"><span data-stu-id="8b38d-164">If you use multiple user accounts to enable a support staff to create large meetings, you can set up a separate calendar that aggregates all large meetings created by the members of the support staff.</span></span> 
  
<span data-ttu-id="8b38d-165">维护单独的大型会议日历可帮助防止冲突和确保任何时候都只有一个大型会议处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="8b38d-165">Maintaining a separate large meeting calendar helps to prevent conflicts and ensure that only one large meeting is active at any time.</span></span>
  
### <a name="implement-a-scheduling-process"></a><span data-ttu-id="8b38d-166">实施日程安排过程</span><span class="sxs-lookup"><span data-stu-id="8b38d-166">Implement a scheduling process</span></span>

<span data-ttu-id="8b38d-167">由于在专用大型会议池上一次仅支持一个大型会议，因此你应该实施大型会议计划过程来帮助设置大型会议并帮助防止冲突。</span><span class="sxs-lookup"><span data-stu-id="8b38d-167">Because only one large meeting at a time is supported on the dedicated large meeting pool, you should implement a large meeting scheduling process to facilitate setting up large meetings and help prevent conflicts.</span></span> <span data-ttu-id="8b38d-168">此类功能不直接由 Skype for business 服务器或 Skype for business 客户端提供。</span><span class="sxs-lookup"><span data-stu-id="8b38d-168">Such capability is not provided directly by Skype for Business Server or Skype for Business clients.</span></span> <span data-ttu-id="8b38d-169">实施此类流程的一种方法是使用您的组织的支持团队的票证发放系统（如有）。</span><span class="sxs-lookup"><span data-stu-id="8b38d-169">One way to implement such a process is to use your organization's support team's ticketing system, if available.</span></span>
  
<span data-ttu-id="8b38d-170">安排大型会议需要完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="8b38d-170">Scheduling a large meeting involves completing the following steps:</span></span>
  
- <span data-ttu-id="8b38d-p114">会议组织者或代理人决定即将举行的会议的时间、持续时间、规模以及演示者列表。如果预期会议规模超过 250 名用户或者要确保为少于 250 名用户的会议提供最佳用户体验，组织者或代理人应提交大型会议请求。</span><span class="sxs-lookup"><span data-stu-id="8b38d-p114">The meeting organizer or delegate determines the time, duration, and size of an upcoming meeting, in addition to the list of presenters. If the anticipated meeting size exceeds 250 users or to ensure the best user experience for a meeting of fewer than 250 users, the organizer or the delegate submits a request for a large meeting.</span></span>
    
- <span data-ttu-id="8b38d-p115">计划人员检查申请日期和时间是否可行。由于专用池一次仅支持一个大型会议，计划人员需要检查大型会议日历，以确定申请日期和时间是否计划了其他会议。如果申请的时间可行，计划人员将批准会议请求。</span><span class="sxs-lookup"><span data-stu-id="8b38d-p115">The scheduling staff checks to see whether the requested date and time is available. Since we support only a single large meeting on the dedicated pool at a time, the scheduling staff needs to check the large-meeting calendar to determine whether there is another meeting scheduled for the requested date and time. If the requested time is available, the staff approves the meeting request.</span></span>
    
- <span data-ttu-id="8b38d-176">如果请求已批准，则计划人员（使用专用池上的凭据）使用 Outlook 的 Skype for business 的联机会议加载项在专用的大型会议池中设置会议。</span><span class="sxs-lookup"><span data-stu-id="8b38d-176">If the request is approved, the scheduling staff (using credentials on the dedicated pool) uses Online Meeting Add-in for Skype for Business with Outlook to set up a meeting on the dedicated large-meeting pool.</span></span> <span data-ttu-id="8b38d-177">用于加入会议的 URL 将作为批准通知的一部分提供给申请者。</span><span class="sxs-lookup"><span data-stu-id="8b38d-177">The URL to be used to join the meeting is provided to the requester as part of the approval notice.</span></span>
    
- <span data-ttu-id="8b38d-p117">会议组织者或代理人使用 Outlook 计划即将到来的会议，将用于加入会议的 URL 添加到会议邀请中。会议组织者或代理人随后指定要邀请的用户并发出会议邀请。</span><span class="sxs-lookup"><span data-stu-id="8b38d-p117">The meeting organizer or delegate uses Outlook to schedule the upcoming meeting, adding the URL for joining the meeting to the meeting invitation. The meeting organizer or delegate then specifies the users to be invited and sends out the meeting invitation.</span></span>
    
### <a name="specify-appropriate-scheduling-details"></a><span data-ttu-id="8b38d-180">指定相应的日程安排详细信息</span><span class="sxs-lookup"><span data-stu-id="8b38d-180">Specify appropriate scheduling details</span></span>

<span data-ttu-id="8b38d-181">检查确保在请求的时间没有安排其他会议后，处理请求的大型会议支持人员将在大型会议池中安排会议。</span><span class="sxs-lookup"><span data-stu-id="8b38d-181">After checking to ensure that no other meeting is scheduled at the requested time, the large meeting support staff that handles the request schedules the meeting on the large-meeting pool.</span></span> 
  
<span data-ttu-id="8b38d-182">为确保最佳用户体验，请务必使用适合于会议组织者需求的适当访问级别和会议设置安排大型会议。</span><span class="sxs-lookup"><span data-stu-id="8b38d-182">To ensure the best user experience, it is important to schedule the large meeting with the right access levels and meeting settings that are appropriate to the meeting organizer's needs.</span></span> <span data-ttu-id="8b38d-183">请考虑 Skype for Business 会议选项中配置的以下日程安排设置：</span><span class="sxs-lookup"><span data-stu-id="8b38d-183">Consider the following scheduling settings configured in Skype for Business Meeting options:</span></span>
  
- <span data-ttu-id="8b38d-184">对每个大型会议使用新的会议空间而不重用专用会议空间。</span><span class="sxs-lookup"><span data-stu-id="8b38d-184">Use a new meeting space for each large meeting instead of reusing the dedicated meeting space.</span></span> 
    
- <span data-ttu-id="8b38d-185">按以下方式指定会议访问级别：</span><span class="sxs-lookup"><span data-stu-id="8b38d-185">Specify the meeting access level as follows:</span></span>
    
  - <span data-ttu-id="8b38d-p119">如果至少有一个被邀请者在组织外部，则将会议访问类型设置为“任何人（无限制）”\*\*\*\*。这样，您在会议过程中便无需管理可能较大的会议厅。</span><span class="sxs-lookup"><span data-stu-id="8b38d-p119">If at least one invitee is external to the organization, set the meeting access type to **Anyone (no restrictions)**. This enables you to avoid having to manage a potentially large lobby when the meeting is in progress.</span></span>
    
  - <span data-ttu-id="8b38d-188">如果会议是仅针对内部的会议，则将会议访问类型设置为“我的组织中的任何人”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8b38d-188">If the meeting is an internal-only meeting, set the meeting access type to **Anyone from my organization**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="8b38d-189">避免将会议访问类型设置为“从我的公司邀请的人员”\*\*\*\*，因为当您使用此设置时，组织者必须将所有用户电子邮件地址添加到被邀请者列表，且您无法邀请通讯组。</span><span class="sxs-lookup"><span data-stu-id="8b38d-189">Avoid setting the meeting access type to **People I invite from my company** because when you use this setting, organizers must add all user email addresses to the invitee list and you cannot invite a distribution group.</span></span> <span data-ttu-id="8b38d-190">避免将会议访问类型设置为“只有我（会议组织者）”\*\*\*\*，因为此设置要求在会议运行时必须将每个会议参与者（包括演示者）置于会议厅中。</span><span class="sxs-lookup"><span data-stu-id="8b38d-190">Avoid setting the meeting access type to **Only me, the meeting organizer** because this setting requires that every meeting participant, including presenters, must be put in the lobby at meeting run time.</span></span> <span data-ttu-id="8b38d-191">负责主持大型会议的人员随后必须持续监视会议厅名单并允许位于会议厅中的新用户加入会议。</span><span class="sxs-lookup"><span data-stu-id="8b38d-191">The person responsible for running the large meeting must then constantly monitor the lobby roster and admit new users who are in the lobby.</span></span>
  
- <span data-ttu-id="8b38d-192">允许用电话拨入的用户选中“呼叫者直接参与”\*\*\*\* 设置自动进入会议。</span><span class="sxs-lookup"><span data-stu-id="8b38d-192">Allow users who dial-in from phones to enter the meeting automatically by checking the **Callers get in directly** setting.</span></span>
    
- <span data-ttu-id="8b38d-193">显式邀请以下用户：</span><span class="sxs-lookup"><span data-stu-id="8b38d-193">Explicitly invite the following users:</span></span>
    
  - <span data-ttu-id="8b38d-194">会议组织者和代理人（请求者）</span><span class="sxs-lookup"><span data-stu-id="8b38d-194">Meeting organizer and delegate (requester)</span></span>
    
  - <span data-ttu-id="8b38d-195">会议请求者提供的演示者的列表</span><span class="sxs-lookup"><span data-stu-id="8b38d-195">The list of presenters provided by a meeting requester</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="8b38d-196">如果会议访问类型设置为“我选择的人员”\*\*\*\*，则需要将大型会议的每个参与者显式添加为会议的受邀者。</span><span class="sxs-lookup"><span data-stu-id="8b38d-196">If the meeting access type is set to **People I choose**, you need to explicitly add each participant of a large meeting as an invitee of the meeting.</span></span> 
  
- <span data-ttu-id="8b38d-p121">显式管理演示者，而不用将演示者选项设置为自动升级值之一。确保将以下用户作为演示者添加：</span><span class="sxs-lookup"><span data-stu-id="8b38d-p121">Explicitly manage presenters, instead of setting the presenter option to one of the auto-promote values. Be sure to add the following users as presenters:</span></span>
    
  - <span data-ttu-id="8b38d-199">会议组织者和代理人（请求者）</span><span class="sxs-lookup"><span data-stu-id="8b38d-199">Meeting organizer and delegate (requester)</span></span>
    
  - <span data-ttu-id="8b38d-200">大型会议请求者提供的演示者的列表</span><span class="sxs-lookup"><span data-stu-id="8b38d-200">The list of presenters provided by large meeting requesters</span></span>
    
    <span data-ttu-id="8b38d-p122">通过显式管理演示者，可以将演示者限制为足够小的数量，从而实现有效的大型会议。如果大多数会议参与者都具有与会者角色，则有助于减少人员意外获得对演示的控制权、删除 PowerPoint 演示、将演示者设为静音/取消静音以及对会议的其他中断的机会。</span><span class="sxs-lookup"><span data-stu-id="8b38d-p122">By explicitly managing presenters, you can limit presenters to a small enough number to make it possible to have an effective large meeting. If the majority of meeting participants have the attendee role, it helps reduce the chance of people accidentally taking control of the presentation, deleting a PowerPoint presentation, muting/unmuting presenters, and other disruptions to the meeting.</span></span> 
    
- <span data-ttu-id="8b38d-203">选中“将所有与会者设为静音”\*\*\*\* 设置以确保只有演示者能将音频广播到会议中。</span><span class="sxs-lookup"><span data-stu-id="8b38d-203">Check the **Mute all attendees** setting to make sure that only presenters can broadcast audio into the meeting.</span></span>
    
- <span data-ttu-id="8b38d-204">检查 "**阻止与会者的视频"** 设置，确保只有演示者可以将视频广播到会议中。</span><span class="sxs-lookup"><span data-stu-id="8b38d-204">Check the **Block attendees' video** setting to make sure only presenters can broadcast video into the meeting.</span></span>
    
### <a name="create-a-conferencing-policy"></a><span data-ttu-id="8b38d-205">创建会议策略</span><span class="sxs-lookup"><span data-stu-id="8b38d-205">Create a conferencing policy</span></span>

<span data-ttu-id="8b38d-p123">创建一个专用于大型会议的新会议策略，然后将此会议策略分配给驻留在专用大型会议池中的用户。使用以下设置配置会议策略：</span><span class="sxs-lookup"><span data-stu-id="8b38d-p123">Create a new conferencing policy specifically for large meetings, and then assign the conferencing policy to the users who are homed on the dedicated large-meeting pool. Configure the conferencing policy using the following settings:</span></span>
  
- <span data-ttu-id="8b38d-208">将**MaxMeetingSize**选项设置为1000。</span><span class="sxs-lookup"><span data-stu-id="8b38d-208">Set the **MaxMeetingSize** option to 1000.</span></span> <span data-ttu-id="8b38d-209">（默认值为250。）</span><span class="sxs-lookup"><span data-stu-id="8b38d-209">(The default is 250.)</span></span>
    
- <span data-ttu-id="8b38d-210">将 **AllowLargeMeetings** 选项设置为 **True**。</span><span class="sxs-lookup"><span data-stu-id="8b38d-210">Set the **AllowLargeMeetings** option to **True**.</span></span> 
    
- <span data-ttu-id="8b38d-211">将 **EnableAppDesktopSharing** 选项设置为“无”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8b38d-211">Set the **EnableAppDesktopSharing** option to **None**.</span></span>
    
- <span data-ttu-id="8b38d-212">将 **AllowUserToScheduleMeetingsWithAppSharing** 选项设置为 **False**。</span><span class="sxs-lookup"><span data-stu-id="8b38d-212">Set the **AllowUserToScheduleMeetingsWithAppSharing** option to **False**.</span></span>
    
- <span data-ttu-id="8b38d-213">将 **AllowSharedNotes** 选项设置为 **False**。</span><span class="sxs-lookup"><span data-stu-id="8b38d-213">Set the **AllowSharedNotes** option to **False**.</span></span>
    
- <span data-ttu-id="8b38d-214">将 **AllowAnnotations** 选项设置为 **False**。</span><span class="sxs-lookup"><span data-stu-id="8b38d-214">Set the **AllowAnnotations** option to **False**.</span></span>
    
- <span data-ttu-id="8b38d-215">将 **DisablePowerPointAnnotations** 选项设置为 **True**。</span><span class="sxs-lookup"><span data-stu-id="8b38d-215">Set the **DisablePowerPointAnnotations** option to **True**.</span></span>
    
- <span data-ttu-id="8b38d-216">将 **AllowMultiview** 选项设置为 **False**。</span><span class="sxs-lookup"><span data-stu-id="8b38d-216">Set the **AllowMultiview** option to **False**.</span></span>
    
- <span data-ttu-id="8b38d-217">将 **EnableMultiviewJoin** 选项设置为 **False**。</span><span class="sxs-lookup"><span data-stu-id="8b38d-217">Set the **EnableMultiviewJoin** option to **False**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="8b38d-218">对 Skype for Business 服务器中的大型会议的支持要求**AllowLargeMeetings**设置设置为 true。</span><span class="sxs-lookup"><span data-stu-id="8b38d-218">Support for large meetings in Skype for Business Server requires that the **AllowLargeMeetings** setting be set to true.</span></span> <span data-ttu-id="8b38d-219">当此设置设置为 true 时，当用户加入会议时，Skype for Business 体验将针对超大型会议进行优化。</span><span class="sxs-lookup"><span data-stu-id="8b38d-219">When this setting is set to true, the Skype for Business experience will be optimized for extra-large meetings when users join the meeting.</span></span> <span data-ttu-id="8b38d-220">尤其是在大型会议中，Skype for Business 不会显示完整会议参与者列表的初始或更新，这是客户端和 Skype for Business 服务器的性能瓶颈。</span><span class="sxs-lookup"><span data-stu-id="8b38d-220">Specifically, in a large meeting, Skype for Business will not show the initial or update of the full meeting participant list, which is a performance bottleneck for both the client and Skype for Business Server.</span></span> <span data-ttu-id="8b38d-221">Skype for business 将仅显示有关用户和会议演示者列表的信息。</span><span class="sxs-lookup"><span data-stu-id="8b38d-221">Instead, Skype for Business will only show information about the user and the list of presenters of the meeting.</span></span> <span data-ttu-id="8b38d-222">Skype for business 仍将显示大型会议中可用的参与者总数。</span><span class="sxs-lookup"><span data-stu-id="8b38d-222">Skype for Business will still show the total number of participants available in the large meetings.</span></span>

<span data-ttu-id="8b38d-223">**AllowLargeMeetings $true**设置将导致以下情况：</span><span class="sxs-lookup"><span data-stu-id="8b38d-223">The **AllowLargeMeetings $true** setting causes the following:</span></span>

- <span data-ttu-id="8b38d-224">隐藏与会者名单。</span><span class="sxs-lookup"><span data-stu-id="8b38d-224">Hides the Attendee roster.</span></span> 

- <span data-ttu-id="8b38d-225">在即时消息窗口中禁用错误。</span><span class="sxs-lookup"><span data-stu-id="8b38d-225">Disables errors in the IM window.</span></span>

- <span data-ttu-id="8b38d-226">禁用多方视频。</span><span class="sxs-lookup"><span data-stu-id="8b38d-226">Disables multi-party video.</span></span>

- <span data-ttu-id="8b38d-227">禁用将与会者提升为演示者的能力。</span><span class="sxs-lookup"><span data-stu-id="8b38d-227">Disables ability to promote an Attendee to Presenter.</span></span> <span data-ttu-id="8b38d-228">必须事先规划并在会议中声明所有演示者。</span><span class="sxs-lookup"><span data-stu-id="8b38d-228">You must plan ahead and declare all Presenters before the meeting.</span></span>

- <span data-ttu-id="8b38d-229">禁用对单个与会者取消静音的功能。</span><span class="sxs-lookup"><span data-stu-id="8b38d-229">Disables ability to unmute individual Attendees.</span></span>

- <span data-ttu-id="8b38d-230">禁用对与会者应用 "锁定视频聚焦" 功能的功能。</span><span class="sxs-lookup"><span data-stu-id="8b38d-230">Disables ability to apply the Lock Video Spotlight feature to Attendees.</span></span>

- <span data-ttu-id="8b38d-231">用户的 PSTN 拨号将无法自行取消静音，因为负责活动大型会议中的 DTMF 命令的个人虚拟协助缺失。</span><span class="sxs-lookup"><span data-stu-id="8b38d-231">PSTN dial in users will be unable to unmute themselves using 6 because Personal Virtual Assistance which is responsible for DTMF commands in active large meetings is missing.</span></span>

- <span data-ttu-id="8b38d-232">如果演示者/组织者安排一次应将每个人都设为静音的会议（"全部静音"），PSTN 用户将在整个呼叫中静音，并且不能自行取消静音。</span><span class="sxs-lookup"><span data-stu-id="8b38d-232">If the presenter/organizer schedules a meeting where everyone should be muted first ("Mute All"), PSTN users will be muted throughout the call and will not be able to unmute themselves.</span></span>

<span data-ttu-id="8b38d-233">若要禁用大型会议中不需要的会议功能，需要使用此处指定的所有会议策略设置（“最大会议规模”\*\*\*\* 设置除外）。</span><span class="sxs-lookup"><span data-stu-id="8b38d-233">Except for the **Maximum meeting size** setting, all the other conferencing policy settings specified here are required in order to disable conferencing capabilities that are not necessary in large meetings.</span></span>
  
<span data-ttu-id="8b38d-234">此外，你需要配置专用的大型会议池，以便托管在池上并负责管理会议计划的每个 Skype for Business 服务器用户都具有相应的权限。</span><span class="sxs-lookup"><span data-stu-id="8b38d-234">Additionally, you need to configure the dedicated large-meeting pool so that each Skype for Business Server user who is homed on the pool and responsible for managing the meeting schedule has the appropriate permissions.</span></span> <span data-ttu-id="8b38d-235">为此，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="8b38d-235">To do this, do the following:</span></span>
  
- <span data-ttu-id="8b38d-p128">将“指定为演示者”\*\*\*\* 选项设置为“无”\*\*\*\*。通常，大型会议的所有参与者中仅一个或几个用户可成为演示者，因此不应自动允许参与者以演示者身份参加大型会议。相反，应在计划会议时明确指定演示者，或在大型会议进行中将参与者显式提升为演示者。</span><span class="sxs-lookup"><span data-stu-id="8b38d-p128">Set the **Designate as presenter** option to **None**. Typically, one or just a few users of all the participants of a large meeting are presenters, so participants should not be automatically admitted to large meetings as presenters. Instead, the presenters should be explicitly designated at meeting scheduling time, or be explicitly promoted during the large meeting.</span></span>
    
- <span data-ttu-id="8b38d-239">确保未选中“默认分配的会议类型”\*\*\*\* 复选框。</span><span class="sxs-lookup"><span data-stu-id="8b38d-239">Make sure that the **Assigned conference type by default** check box is not selected.</span></span> <span data-ttu-id="8b38d-240">此设置控制 Skype for business 的联机会议加载项是否始终使用组织者分配的会议安排会议，这意味着计划的会议具有相同的联接 URL 和音频信息。</span><span class="sxs-lookup"><span data-stu-id="8b38d-240">This setting controls whether the Online Meeting Add-in for Skype for Business always schedules conferences using the organizer's assigned conference, which means that scheduled meetings have the same join URL and audio information.</span></span> <span data-ttu-id="8b38d-241">在小组协作方案中，可确保此类分配的会议类型很好地进行，因为每个用户均具有自己的单独分配的会议，并且持续加入 URL 和音频信息有助于推动更快的会议加入。</span><span class="sxs-lookup"><span data-stu-id="8b38d-241">In small group collaboration scenarios, having such assigned conference type works well because everyone has their own individual assigned conference, and the constant join URL and audio information helps to facilitate faster meeting joining.</span></span> <span data-ttu-id="8b38d-242">但是，在大型会议方案中，大型会议支持人员将使用一组用户凭据来计划大型会议，然后向会议请求者提供加入 URL 和音频信息。</span><span class="sxs-lookup"><span data-stu-id="8b38d-242">However, in the large-meeting scenario, the large meeting support staff schedules the large meetings using a single set of user credentials, and then provides join URLs and audio information to the meeting requesters.</span></span> <span data-ttu-id="8b38d-243">在此情况下，使用不同的 URL 加入各个会议所达到的效果会更佳。</span><span class="sxs-lookup"><span data-stu-id="8b38d-243">In this case, using a different URL to join each meeting works better.</span></span>
    
- <span data-ttu-id="8b38d-244">确保未选中“默认允许匿名用户”\*\*\*\* 复选框，除非需要这样做。</span><span class="sxs-lookup"><span data-stu-id="8b38d-244">Ensure that the **Admit anonymous users by default** check box is not selected, unless it is required.</span></span> <span data-ttu-id="8b38d-245">此设置影响未使用分配的会议时由 Skype for business 的联机会议加载项计划的默认会议访问类型。</span><span class="sxs-lookup"><span data-stu-id="8b38d-245">This setting affects the default meeting access type scheduled by the Online Meeting Add-in for Skype for Business when not using an assigned conference.</span></span> <span data-ttu-id="8b38d-246">此设置的相应选项取决于组织的需求。</span><span class="sxs-lookup"><span data-stu-id="8b38d-246">The appropriate option for this setting depends on your organization's needs.</span></span> <span data-ttu-id="8b38d-247">如果您组织的大多数大型会议是内部会议，请不要选择此选项。</span><span class="sxs-lookup"><span data-stu-id="8b38d-247">If most large meetings for your organization are internal meetings, do not select this option.</span></span> <span data-ttu-id="8b38d-248">如果大多数大型会议需要外部用户能够加入，请选择此选项。</span><span class="sxs-lookup"><span data-stu-id="8b38d-248">If most large meetings require that external users be able to join, select this option.</span></span>
    
<span data-ttu-id="8b38d-249">有关创建会议策略的详细信息，请参阅[在 Skype For Business 服务器中管理会议策略](../../manage/conferencing/conferencing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="8b38d-249">For more information about creating a conferencing policy, see [Manage conferencing policies in Skype for Business Server](../../manage/conferencing/conferencing-policies.md).</span></span>
  

