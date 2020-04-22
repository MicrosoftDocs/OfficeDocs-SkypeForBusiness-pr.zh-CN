---
title: 在 Skype for Business Server 中规划大型会议
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 21507e18-bd79-4019-9c3a-0867fccaa3b4
description: 摘要：阅读本主题，了解在 Skype for business Server 中实施和管理大型会议的最佳做法。
ms.openlocfilehash: 18b0f036e49996564aa68735300f4e677ce5b1cb
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780231"
---
# <a name="plan-for-large-meetings-in-skype-for-business-server"></a><span data-ttu-id="7b9ac-103">在 Skype for Business Server 中规划大型会议</span><span class="sxs-lookup"><span data-stu-id="7b9ac-103">Plan for large meetings in Skype for Business Server</span></span>
 
<span data-ttu-id="7b9ac-104">**摘要：** 阅读本主题，了解在 Skype for business Server 中实施和管理大型会议的最佳做法。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-104">**Summary:** Read this topic to learn about best practices for implementing and managing large meetings in Skype for Business Server.</span></span>
  
<span data-ttu-id="7b9ac-105">Skype for Business Server 可以支持的会议大小取决于会议是位于共享池上，还是位于专用池上的1000参与者上，从共享池上的250参与者到任何位置。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-105">The size of meetings that Skype for Business Server can support depends on whether conferencing is hosted on a shared or dedicated pool: anywhere from 250 participants on a shared pool to 1000 participants on a dedicated pool.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="7b9ac-106">本主题重点介绍 Skype for business Server 支持的大型会议的最佳实践。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-106">This topic focuses on best practices for large meetings supported by Skype for Business Server.</span></span> <span data-ttu-id="7b9ac-107">如果您的组织需要更大的会议功能，应考虑实施使用 Skype 会议直播的混合环境，这是 Office 365 中的一种新联机服务。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-107">If your organization requires larger meeting capabilities, you should consider implementing a hybrid environment that takes advantage of Skype Meeting Broadcast, a new online service that is part of Office 365.</span></span> 

> [!NOTE]
> <span data-ttu-id="7b9ac-108">通过 Skype 会议直播，用户可以将会议托管和广播到最多为10000个参与者的大型 online 访问群体。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-108">Skype Meeting Broadcast enables users to host and broadcast meetings to large online audiences of up to 10,000 participants.</span></span> <span data-ttu-id="7b9ac-109">使用 Skype 会议直播要求已在包含生产 Office 365 组织的混合设置中配置 Skype for Business Server。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-109">The use of Skype Meeting Broadcast requires that Skype for Business Server already be configured in a hybrid setup with a production Office 365 organization.</span></span> <span data-ttu-id="7b9ac-110">所有用户必须具有作为先决条件建立的联机租户。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-110">All users must have an online tenant established as a prerequisite.</span></span> <span data-ttu-id="7b9ac-111">如果您希望部署可利用 Skype 会议直播功能的混合解决方案，请参阅[什么是 Skype 会议直播？](https://go.microsoft.com/fwlink/?LinkId=617071)并[为 Skype 会议直播配置本地部署](../../deploy/configure-skype-meeting-broadcast.md)。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-111">If you are interested in deploying a hybrid solution that can take advantage of Skype Meeting Broadcast, see [What is a Skype Meeting Broadcast?](https://go.microsoft.com/fwlink/?LinkId=617071) and [Configure your on-premises deployment for Skype Meeting Broadcast](../../deploy/configure-skype-meeting-broadcast.md).</span></span> 
  
<span data-ttu-id="7b9ac-112">大型会议通常具有以下特征：</span><span class="sxs-lookup"><span data-stu-id="7b9ac-112">Large meetings typically have the following characteristics:</span></span>
  
- <span data-ttu-id="7b9ac-113">会议形式为一对多的演示。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-113">The meeting format is a one-to-many presentation.</span></span>
    
- <span data-ttu-id="7b9ac-114">一个或一些用户为演示者，并且所有人只能作为出席者参与。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-114">One or a few users are presenters, and everyone else participates only as attendees.</span></span>
    
- <span data-ttu-id="7b9ac-115">PowerPoint 演示文稿共享是主要数据协作活动。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-115">PowerPoint presentation sharing is the main data collaboration activity.</span></span>
    
- <span data-ttu-id="7b9ac-116">需要音频，还可能使用视频。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-116">Audio is required and video may also be used.</span></span>
    
- <span data-ttu-id="7b9ac-117">一个专门人员（通常是会议组织者或组织者的助理）提前设置会议。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-117">A dedicated person, generally either the meeting organizer or an assistant to the organizer, sets up the meeting well in advance.</span></span>
    
- <span data-ttu-id="7b9ac-118">专门人员（不是演示者）运行会议，包括根据需要连接到联机会议、验证音频、视频和幻灯片共享工作、管理会议厅和用户角色、将参与者静音或取消静音、提问和管理记录。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-118">Dedicated staff (not the presenters) runs the meeting, including connecting to an online meeting, verifying that audio, video, and slide sharing work, managing lobby and user roles, muting and unmuting participants, taking questions, and managing recordings, as appropriate.</span></span>
    
<span data-ttu-id="7b9ac-119">当用户安排会议时，Skype for Business Server 在会议数据库中创建一条记录，该记录存储会议数据，但不提前为计划会议预留任何硬件资源。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-119">When a user schedules a meeting, Skype for Business Server creates a record in the conferencing database, which stores conferencing data, but does not reserve any hardware resources for the scheduled meeting ahead of time.</span></span> <span data-ttu-id="7b9ac-120">相反，Skype for Business Server 具有内置负载平衡逻辑，以在前端服务器上动态分配会议资源，以在池中的所有前端服务器上平均分布负载。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-120">Instead, Skype for Business Server has built-in load balancing logic to dynamically allocate conferencing resources on Front End Servers in a way that distributes loads equally across all Front End Servers in the pool.</span></span> <span data-ttu-id="7b9ac-121">这将有效地预配和使用硬件资源，但必须正确规划以支持非常大型的会议，这一点非常重要。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-121">This effectively provisions and uses hardware resources, but it is important that you plan appropriately to support very large meetings.</span></span> 
  
<span data-ttu-id="7b9ac-122">例如，当 Skype for Business Server 池的运行接近其最大容量时，每台前端服务器可能会托管大约125平均大小的会议。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-122">For example, when a Skype for Business Server pool is running close to its top capacity, each Front End Server might host approximately 125 average-size meetings.</span></span> <span data-ttu-id="7b9ac-123">添加另一个小会议并不是一个问题，但为1000用户添加会议是一个问题，因为前端服务器可能无法同时支持其他125会议的大型会议。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-123">Adding another small meeting would not be a problem, but adding a meeting for 1000 users would be a problem because the Front End Servers would probably not be able to support such a large meeting at the same time as the other 125 meetings.</span></span>
  
<span data-ttu-id="7b9ac-124">支持最多为1000个参与者的大型会议需要解决与共享硬件模型和非保留模型相关的问题。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-124">Supporting large meetings of up to 1000 participants requires addressing the issues related to both the shared hardware model and the no-reservation model.</span></span> <span data-ttu-id="7b9ac-125">通常情况下，您需要规划专用池，并遵循以下各节所述的最佳做法。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-125">In general, you need to plan for a dedicated pool and follow best practices as described in the following sections.</span></span> 
  
## <a name="plan-for-a-dedicated-pool"></a><span data-ttu-id="7b9ac-126">规划专用池</span><span class="sxs-lookup"><span data-stu-id="7b9ac-126">Plan for a dedicated pool</span></span>

<span data-ttu-id="7b9ac-127">如果您的组织需要参与者大于250的会议，则需要规划专用池来支持负载。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-127">If your organization requires meetings with greater than 250 participants, you need to plan for a dedicated pool to support the load.</span></span> 
  
<span data-ttu-id="7b9ac-128">若要为最高为1000个用户的会议提供充足的 CPU 和内存资源，托管前端服务器不应承载任何其他即时消息（IM）和状态或企业语音工作负载。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-128">To have sufficient CPU and memory resources for meetings of up to 1000 users, the hosting Front End Servers should not host any other instant messaging (IM) and presence or Enterprise Voice workloads.</span></span> <span data-ttu-id="7b9ac-129">无论其他会议的大小如何，服务器也不应承载任何其他会议。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-129">The servers should also not host any other meetings, regardless of the size of the other meetings.</span></span> <span data-ttu-id="7b9ac-130">若要承载最多为1000个用户的会议，您需要设置单独的 Skype for Business 服务器池，专用于承载大型会议。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-130">To host meetings of up to 1000 users, you need to set up a separate Skype for Business Server pool that is dedicated to hosting large meetings.</span></span>
  
<span data-ttu-id="7b9ac-131">专用于承载大型会议的 Skype for Business Server 池应同时托管一个会议，且最多只能为1000个用户提供一次会议，因此需要通过带外计划过程提前保留会议时间，以确保从前端服务器获得专用支持。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-131">A Skype for Business Server pool that is dedicated to hosting large meetings should host one and only one meeting of up to 1000 users at the same time, so meeting times need to be reserved in advance via an out of band scheduling process to ensure dedicated support from the Front End Servers.</span></span> <span data-ttu-id="7b9ac-132">若要同时支持多个大型会议，应设置多个专用大型会议池。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-132">To support more than one large meeting at the same time, you should set up multiple dedicated large-meeting pools.</span></span>
  
<span data-ttu-id="7b9ac-133">有关硬件和软件要求以及规划支持大型会议的拓扑的详细信息，请参阅[skype for Business server 中的会议的硬件和软件要求](hardware-and-software-requirements.md)，并[为 Skype For business server 规划会议拓扑](conferencing-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-133">For more information about hardware and software requirements, and planning a topology that supports large meetings, see [Hardware and software requirements for conferencing in Skype for Business Server](hardware-and-software-requirements.md) and [Plan your conferencing topology for Skype for Business Server](conferencing-topology.md).</span></span>
  
## <a name="implement-best-practices-for-large-meetings"></a><span data-ttu-id="7b9ac-134">实施大型会议的最佳实践</span><span class="sxs-lookup"><span data-stu-id="7b9ac-134">Implement best practices for large meetings</span></span>

<span data-ttu-id="7b9ac-135">为大型会议设置专用池之后，您可以采取措施来帮助确保在该池中托管的大型会议提供最佳用户体验。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-135">After setting up a dedicated pool for large meetings, you can take steps to help ensure that large meetings hosted in the pool provide the best user experience.</span></span> <span data-ttu-id="7b9ac-136">以下各节提供了有关管理大型会议的准则：</span><span class="sxs-lookup"><span data-stu-id="7b9ac-136">The following sections provide guidelines for managing large meetings:</span></span>
  
- <span data-ttu-id="7b9ac-137">创建专用会议组织者</span><span class="sxs-lookup"><span data-stu-id="7b9ac-137">Create dedicated meeting organizers</span></span>
    
- <span data-ttu-id="7b9ac-138">创建专用仲裁人</span><span class="sxs-lookup"><span data-stu-id="7b9ac-138">Create dedicated moderators</span></span>
    
- <span data-ttu-id="7b9ac-139">维护一个单独的大型会议日历</span><span class="sxs-lookup"><span data-stu-id="7b9ac-139">Maintain a separate calendar of large meetings</span></span>
    
- <span data-ttu-id="7b9ac-140">实施大型会议日程安排过程</span><span class="sxs-lookup"><span data-stu-id="7b9ac-140">Implement a large-meeting scheduling process</span></span>
    
- <span data-ttu-id="7b9ac-141">指定适当的日程安排详细信息</span><span class="sxs-lookup"><span data-stu-id="7b9ac-141">Specify appropriate scheduling details</span></span>
    
- <span data-ttu-id="7b9ac-142">为大型会议创建会议策略</span><span class="sxs-lookup"><span data-stu-id="7b9ac-142">Create a conferencing policy for large meetings</span></span>
    
### <a name="create-dedicated-meeting-organizers"></a><span data-ttu-id="7b9ac-143">创建专用会议组织者</span><span class="sxs-lookup"><span data-stu-id="7b9ac-143">Create dedicated meeting organizers</span></span>

<span data-ttu-id="7b9ac-144">为最大限度地减少大型会议池中的实时通信流量，Microsoft 不建议让定期使用 Skype for Business 客户端进行登录并参与即时消息（IM）、状态、会议和语音会议的用户。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-144">To minimize the real-time communications traffic in the large-meeting pool, Microsoft does not recommend hosting users who regularly sign in using Skype for Business clients and participate in instant messaging (IM), presence, conferencing, and voice sessions.</span></span> <span data-ttu-id="7b9ac-145">而应执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="7b9ac-145">Instead, do one of the following:</span></span>
  
- <span data-ttu-id="7b9ac-146">仅创建用于安排大型会议的一个或多个专用用户帐户</span><span class="sxs-lookup"><span data-stu-id="7b9ac-146">Create one or more dedicated user accounts just for scheduling large meetings</span></span>
    
- <span data-ttu-id="7b9ac-147">Home 负责在大型会议池中安排大型会议的人员的用户帐户</span><span class="sxs-lookup"><span data-stu-id="7b9ac-147">Home the user accounts of the staff responsible for scheduling large meetings on a large-meeting pool</span></span>
    
### <a name="create-dedicated-moderators"></a><span data-ttu-id="7b9ac-148">创建专用仲裁人</span><span class="sxs-lookup"><span data-stu-id="7b9ac-148">Create dedicated moderators</span></span>

<span data-ttu-id="7b9ac-149">如果会议中有数百到一千名用户，则最好让一个专门人员来安排大型会议的联机会话。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-149">With several hundred to a thousand users in a meeting, it is a good practice to have a dedicated person moderate the online session of a large meeting.</span></span> <span data-ttu-id="7b9ac-150">此专用人员可以是会议组织者的代理人，也可以是组织的大型会议支持人员的成员。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-150">This dedicated person can be a delegate of the meeting organizer or a member of the organization's large-meeting support staff.</span></span> <span data-ttu-id="7b9ac-151">在安排会议时，将专门的会议审阅者添加为演示者是非常重要的，尽管可以在会议进行过程中将联机会议与会者提升为演示者角色。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-151">It is important to add the dedicated meeting moderator as a presenter at the time that the meeting is scheduled, although it is possible to promote an online meeting attendee to the presenter role while the meeting is in progress.</span></span>
  
<span data-ttu-id="7b9ac-152">会议仲裁人可以使用 Skype for Business 客户端的所有演示者功能来管理大型会议。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-152">The meeting moderator can use all presenter functionalities of Skype for Business clients to manage the large meeting.</span></span> <span data-ttu-id="7b9ac-153">这些功能包括：</span><span class="sxs-lookup"><span data-stu-id="7b9ac-153">These functionalities include:</span></span>
  
- <span data-ttu-id="7b9ac-154">监视前厅浏览和允许或拒绝会议厅中的用户</span><span class="sxs-lookup"><span data-stu-id="7b9ac-154">Monitoring the lobby and admitting or rejecting users in the lobby</span></span>
    
- <span data-ttu-id="7b9ac-155">从会议中删除不应位于会议中的任何用户</span><span class="sxs-lookup"><span data-stu-id="7b9ac-155">Removing any users from the meeting who should not be in the meeting</span></span>
    
- <span data-ttu-id="7b9ac-156">更改会议访问类型</span><span class="sxs-lookup"><span data-stu-id="7b9ac-156">Changing meeting access types</span></span>
    
- <span data-ttu-id="7b9ac-157">更改参与者角色</span><span class="sxs-lookup"><span data-stu-id="7b9ac-157">Changing participant roles</span></span>
    
- <span data-ttu-id="7b9ac-158">在会议过程中使用拖放功能、电话拨出或电子邮件邀请其他参与者</span><span class="sxs-lookup"><span data-stu-id="7b9ac-158">Inviting additional participants during the meeting using drag and drop functionality, phone dial out, or email</span></span>
    
- <span data-ttu-id="7b9ac-159">观众或个人用户的静音和观众</span><span class="sxs-lookup"><span data-stu-id="7b9ac-159">Muting and unmuting the audience or individual users</span></span>
    
- <span data-ttu-id="7b9ac-160">管理会议内容，包括上载内容、删除内容和切换活动内容</span><span class="sxs-lookup"><span data-stu-id="7b9ac-160">Managing meeting content, including uploading content, deleting content, and switching active content</span></span>

    
### <a name="maintain-a-separate-calendar"></a><span data-ttu-id="7b9ac-161">维护单独的日历</span><span class="sxs-lookup"><span data-stu-id="7b9ac-161">Maintain a separate calendar</span></span>

<span data-ttu-id="7b9ac-162">对于每个大型会议池，应为在该池上安排的大型会议保留一个单独的日历。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-162">For each large-meeting pool, you should maintain a separate calendar of large meetings scheduled on that pool.</span></span> <span data-ttu-id="7b9ac-163">例如，您可以在大型会议池上使用单个用户帐户，并将 Outlook 与 Skype for business 的 Exchange 和联机会议外接程序一起使用来维护单独的日历。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-163">For example, you can home a single user account on the large-meeting pool and use Outlook with Exchange and Online Meeting Add-in for Skype for Business to maintain a separate calendar.</span></span> <span data-ttu-id="7b9ac-164">如果使用多个用户帐户来允许支持人员创建大型会议，则可设置一个单独的日历，以聚合支持人员的成员创建的所有大型会议。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-164">If you use multiple user accounts to enable a support staff to create large meetings, you can set up a separate calendar that aggregates all large meetings created by the members of the support staff.</span></span> 
  
<span data-ttu-id="7b9ac-165">维护单独的大型会议日历可帮助防止冲突和确保任何时候都只有一个大型会议处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-165">Maintaining a separate large meeting calendar helps to prevent conflicts and ensure that only one large meeting is active at any time.</span></span>
  
### <a name="implement-a-scheduling-process"></a><span data-ttu-id="7b9ac-166">实施日程安排过程</span><span class="sxs-lookup"><span data-stu-id="7b9ac-166">Implement a scheduling process</span></span>

<span data-ttu-id="7b9ac-167">由于在专用大型会议池上一次仅支持一个大型会议，因此您应该实施大型会议日程安排过程以协助设置大型会议并帮助防止冲突。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-167">Because only one large meeting at a time is supported on the dedicated large meeting pool, you should implement a large meeting scheduling process to facilitate setting up large meetings and help prevent conflicts.</span></span> <span data-ttu-id="7b9ac-168">Skype for Business Server 或 Skype for business 客户端不会直接提供此类功能。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-168">Such capability is not provided directly by Skype for Business Server or Skype for Business clients.</span></span> <span data-ttu-id="7b9ac-169">实施此类过程的一种方法是使用贵组织的支持团队的票证系统（如果有）。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-169">One way to implement such a process is to use your organization's support team's ticketing system, if available.</span></span>
  
<span data-ttu-id="7b9ac-170">安排大型会议时需要完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="7b9ac-170">Scheduling a large meeting involves completing the following steps:</span></span>
  
- <span data-ttu-id="7b9ac-171">会议组织者或代理人决定了即将召开的会议的时间、持续时间和大小，以及演示者列表。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-171">The meeting organizer or delegate determines the time, duration, and size of an upcoming meeting, in addition to the list of presenters.</span></span> <span data-ttu-id="7b9ac-172">如果预期的会议大小超过250个用户，或者为了确保会议的用户体验少于250个用户，则组织者或代理人将提交大型会议的请求。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-172">If the anticipated meeting size exceeds 250 users or to ensure the best user experience for a meeting of fewer than 250 users, the organizer or the delegate submits a request for a large meeting.</span></span>
    
- <span data-ttu-id="7b9ac-173">计划员工检查以查看是否有请求的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-173">The scheduling staff checks to see whether the requested date and time is available.</span></span> <span data-ttu-id="7b9ac-174">由于我们一次仅支持专用池上的一个大型会议，因此计划员工需要检查大型会议日历，以确定是否为请求的日期和时间安排了另一个会议。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-174">Since we support only a single large meeting on the dedicated pool at a time, the scheduling staff needs to check the large-meeting calendar to determine whether there is another meeting scheduled for the requested date and time.</span></span> <span data-ttu-id="7b9ac-175">如果请求的时间可用，员工将批准会议请求。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-175">If the requested time is available, the staff approves the meeting request.</span></span>
    
- <span data-ttu-id="7b9ac-176">如果请求得到批准，计划员工（使用专用池上的凭据）使用 Outlook 的 Skype for business 的联机会议外接程序在专用大型会议池上设置会议。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-176">If the request is approved, the scheduling staff (using credentials on the dedicated pool) uses Online Meeting Add-in for Skype for Business with Outlook to set up a meeting on the dedicated large-meeting pool.</span></span> <span data-ttu-id="7b9ac-177">作为审批通知的一部分，将用于加入会议的 URL 提供给申请者。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-177">The URL to be used to join the meeting is provided to the requester as part of the approval notice.</span></span>
    
- <span data-ttu-id="7b9ac-178">会议组织者或代理人使用 Outlook 安排即将召开的会议，并将用于加入会议的 URL 添加到会议邀请中。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-178">The meeting organizer or delegate uses Outlook to schedule the upcoming meeting, adding the URL for joining the meeting to the meeting invitation.</span></span> <span data-ttu-id="7b9ac-179">会议组织者或代理人将指定被邀请的用户并发出会议邀请。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-179">The meeting organizer or delegate then specifies the users to be invited and sends out the meeting invitation.</span></span>
    
### <a name="specify-appropriate-scheduling-details"></a><span data-ttu-id="7b9ac-180">指定适当的日程安排详细信息</span><span class="sxs-lookup"><span data-stu-id="7b9ac-180">Specify appropriate scheduling details</span></span>

<span data-ttu-id="7b9ac-181">检查确保在请求的时间没有安排其他会议后，处理请求的大型会议支持人员将在大型会议池中安排会议。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-181">After checking to ensure that no other meeting is scheduled at the requested time, the large meeting support staff that handles the request schedules the meeting on the large-meeting pool.</span></span> 
  
<span data-ttu-id="7b9ac-182">为了确保获得最佳用户体验，请务必使用适合于会议组织者需求的合适的访问级别和会议设置安排大型会议。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-182">To ensure the best user experience, it is important to schedule the large meeting with the right access levels and meeting settings that are appropriate to the meeting organizer's needs.</span></span> <span data-ttu-id="7b9ac-183">请考虑在 Skype for Business 会议选项中配置的以下计划设置：</span><span class="sxs-lookup"><span data-stu-id="7b9ac-183">Consider the following scheduling settings configured in Skype for Business Meeting options:</span></span>
  
- <span data-ttu-id="7b9ac-184">对每个大型会议使用新的会议空间而不重用专用会议空间。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-184">Use a new meeting space for each large meeting instead of reusing the dedicated meeting space.</span></span> 
    
- <span data-ttu-id="7b9ac-185">按以下方式指定会议访问级别：</span><span class="sxs-lookup"><span data-stu-id="7b9ac-185">Specify the meeting access level as follows:</span></span>
    
  - <span data-ttu-id="7b9ac-186">如果组织中至少有一个被邀请者是外部的，请将会议访问类型设置为 "**任何人" （无限制）**。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-186">If at least one invitee is external to the organization, set the meeting access type to **Anyone (no restrictions)**.</span></span> <span data-ttu-id="7b9ac-187">这样，您在会议过程中便无需管理可能较大的会议厅。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-187">This enables you to avoid having to manage a potentially large lobby when the meeting is in progress.</span></span>
    
  - <span data-ttu-id="7b9ac-188">如果会议是仅针对内部的会议，则将会议访问类型设置为**我的组织中的任何人**。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-188">If the meeting is an internal-only meeting, set the meeting access type to **Anyone from my organization**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7b9ac-189">避免将会议访问类型设置为**从我的公司邀请的人员**，因为当您使用此设置时，组织者必须将所有用户电子邮件地址添加到被邀请者列表，且您无法邀请通讯组。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-189">Avoid setting the meeting access type to **People I invite from my company** because when you use this setting, organizers must add all user email addresses to the invitee list and you cannot invite a distribution group.</span></span> <span data-ttu-id="7b9ac-190">避免将会议访问类型设置为**只有我（会议组织者）**，因为此设置要求在会议运行时必须将每个会议参与者（包括演示者）置于会议厅中。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-190">Avoid setting the meeting access type to **Only me, the meeting organizer** because this setting requires that every meeting participant, including presenters, must be put in the lobby at meeting run time.</span></span> <span data-ttu-id="7b9ac-191">负责主持大型会议的人员随后必须持续监视会议厅名单并允许位于会议厅中的新用户加入会议。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-191">The person responsible for running the large meeting must then constantly monitor the lobby roster and admit new users who are in the lobby.</span></span>
  
- <span data-ttu-id="7b9ac-192">允许用电话拨入的用户通过选中“呼叫者直接参与”\*\*\*\* 设置自动进入会议。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-192">Allow users who dial-in from phones to enter the meeting automatically by checking the **Callers get in directly** setting.</span></span>
    
- <span data-ttu-id="7b9ac-193">显式邀请以下用户：</span><span class="sxs-lookup"><span data-stu-id="7b9ac-193">Explicitly invite the following users:</span></span>
    
  - <span data-ttu-id="7b9ac-194">会议组织者和代理人（请求者）</span><span class="sxs-lookup"><span data-stu-id="7b9ac-194">Meeting organizer and delegate (requester)</span></span>
    
  - <span data-ttu-id="7b9ac-195">会议请求者提供的演示者的列表</span><span class="sxs-lookup"><span data-stu-id="7b9ac-195">The list of presenters provided by a meeting requester</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7b9ac-196">如果会议访问类型设置为**我选择的人员**，则需要将大型会议的每个参与者作为会议的被邀请者显式添加。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-196">If the meeting access type is set to **People I choose**, you need to explicitly add each participant of a large meeting as an invitee of the meeting.</span></span> 
  
- <span data-ttu-id="7b9ac-p121">显式管理演示者，而不用将演示者选项设置为自动升级值之一。确保将以下用户作为演示者添加：</span><span class="sxs-lookup"><span data-stu-id="7b9ac-p121">Explicitly manage presenters, instead of setting the presenter option to one of the auto-promote values. Be sure to add the following users as presenters:</span></span>
    
  - <span data-ttu-id="7b9ac-199">会议组织者和代理人（请求者）</span><span class="sxs-lookup"><span data-stu-id="7b9ac-199">Meeting organizer and delegate (requester)</span></span>
    
  - <span data-ttu-id="7b9ac-200">大型会议请求者提供的演示者的列表</span><span class="sxs-lookup"><span data-stu-id="7b9ac-200">The list of presenters provided by large meeting requesters</span></span>
    
    <span data-ttu-id="7b9ac-201">通过显式管理演示者，可以将演示者限制为足够小的数字，以使其可以拥有有效的大型会议。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-201">By explicitly managing presenters, you can limit presenters to a small enough number to make it possible to have an effective large meeting.</span></span> <span data-ttu-id="7b9ac-202">如果大多数会议参与者都具有与会者角色，则有助于减少人员意外获得对演示的控制权、删除 PowerPoint 演示、将演示者设为静音/取消静音以及对会议的其他中断的机会。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-202">If the majority of meeting participants have the attendee role, it helps reduce the chance of people accidentally taking control of the presentation, deleting a PowerPoint presentation, muting/unmuting presenters, and other disruptions to the meeting.</span></span> 
    
- <span data-ttu-id="7b9ac-203">选中“将所有与会者设为静音”\*\*\*\* 设置以确保只有演示者能将音频广播到会议中。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-203">Check the **Mute all attendees** setting to make sure that only presenters can broadcast audio into the meeting.</span></span>
    
- <span data-ttu-id="7b9ac-204">检查 "**阻止与会者" 的视频**设置，以确保只有演示者能够将视频广播到会议中。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-204">Check the **Block attendees' video** setting to make sure only presenters can broadcast video into the meeting.</span></span>
    
### <a name="create-a-conferencing-policy"></a><span data-ttu-id="7b9ac-205">创建会议策略</span><span class="sxs-lookup"><span data-stu-id="7b9ac-205">Create a conferencing policy</span></span>

<span data-ttu-id="7b9ac-206">专门为大型会议创建新的会议策略，然后将会议策略分配给驻留在专用大型会议池上的用户。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-206">Create a new conferencing policy specifically for large meetings, and then assign the conferencing policy to the users who are homed on the dedicated large-meeting pool.</span></span> <span data-ttu-id="7b9ac-207">使用以下设置配置会议策略：</span><span class="sxs-lookup"><span data-stu-id="7b9ac-207">Configure the conferencing policy using the following settings:</span></span>
  
- <span data-ttu-id="7b9ac-208">将**MaxMeetingSize**选项设置为1000。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-208">Set the **MaxMeetingSize** option to 1000.</span></span> <span data-ttu-id="7b9ac-209">（默认值为250。）</span><span class="sxs-lookup"><span data-stu-id="7b9ac-209">(The default is 250.)</span></span>
    
- <span data-ttu-id="7b9ac-210">将 **AllowLargeMeetings** 选项设置为 **True**。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-210">Set the **AllowLargeMeetings** option to **True**.</span></span> 
    
- <span data-ttu-id="7b9ac-211">将 **EnableAppDesktopSharing** 选项设置为“无”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-211">Set the **EnableAppDesktopSharing** option to **None**.</span></span>
    
- <span data-ttu-id="7b9ac-212">将 **AllowUserToScheduleMeetingsWithAppSharing** 选项设置为 **False**。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-212">Set the **AllowUserToScheduleMeetingsWithAppSharing** option to **False**.</span></span>
    
- <span data-ttu-id="7b9ac-213">将 **AllowSharedNotes** 选项设置为 **False**。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-213">Set the **AllowSharedNotes** option to **False**.</span></span>
    
- <span data-ttu-id="7b9ac-214">将 **AllowAnnotations** 选项设置为 **False**。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-214">Set the **AllowAnnotations** option to **False**.</span></span>
    
- <span data-ttu-id="7b9ac-215">将 **DisablePowerPointAnnotations** 选项设置为 **True**。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-215">Set the **DisablePowerPointAnnotations** option to **True**.</span></span>
    
- <span data-ttu-id="7b9ac-216">将 **AllowMultiview** 选项设置为 **False**。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-216">Set the **AllowMultiview** option to **False**.</span></span>
    
- <span data-ttu-id="7b9ac-217">将 **EnableMultiviewJoin** 选项设置为 **False**。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-217">Set the **EnableMultiviewJoin** option to **False**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="7b9ac-218">在 Skype for business Server 中，对大型会议的支持要求将**AllowLargeMeetings**设置设置为 true。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-218">Support for large meetings in Skype for Business Server requires that the **AllowLargeMeetings** setting be set to true.</span></span> <span data-ttu-id="7b9ac-219">当此设置设置为 true 时，当用户加入会议时，Skype for Business 体验将针对超大型会议进行优化。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-219">When this setting is set to true, the Skype for Business experience will be optimized for extra-large meetings when users join the meeting.</span></span> <span data-ttu-id="7b9ac-220">具体来说，在大型会议中，Skype for Business 不会显示完整会议参与者列表的初始或更新，这是客户端和 Skype for business Server 的性能瓶颈。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-220">Specifically, in a large meeting, Skype for Business will not show the initial or update of the full meeting participant list, which is a performance bottleneck for both the client and Skype for Business Server.</span></span> <span data-ttu-id="7b9ac-221">相反，Skype for Business 将仅显示有关用户和会议演示者列表的信息。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-221">Instead, Skype for Business will only show information about the user and the list of presenters of the meeting.</span></span> <span data-ttu-id="7b9ac-222">Skype for Business 仍将显示在大型会议中可用的参与者总数。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-222">Skype for Business will still show the total number of participants available in the large meetings.</span></span>

<span data-ttu-id="7b9ac-223">**AllowLargeMeetings $true**设置将导致以下问题：</span><span class="sxs-lookup"><span data-stu-id="7b9ac-223">The **AllowLargeMeetings $true** setting causes the following:</span></span>

- <span data-ttu-id="7b9ac-224">隐藏与会者名单。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-224">Hides the Attendee roster.</span></span> 

- <span data-ttu-id="7b9ac-225">禁用 IM 窗口中的错误。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-225">Disables errors in the IM window.</span></span>

- <span data-ttu-id="7b9ac-226">禁用多方视频。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-226">Disables multi-party video.</span></span>

- <span data-ttu-id="7b9ac-227">禁用将与会者提升为演示者的功能。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-227">Disables ability to promote an Attendee to Presenter.</span></span> <span data-ttu-id="7b9ac-228">您必须事先规划并声明所有演示者，然后才能参加会议。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-228">You must plan ahead and declare all Presenters before the meeting.</span></span>

- <span data-ttu-id="7b9ac-229">禁用对各个与会者取消静音的功能。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-229">Disables ability to unmute individual Attendees.</span></span>

- <span data-ttu-id="7b9ac-230">禁用将 "锁定视频聚焦" 功能应用于与会者的功能。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-230">Disables ability to apply the Lock Video Spotlight feature to Attendees.</span></span>

- <span data-ttu-id="7b9ac-231">用户将无法使用6取消静音呼叫，因为负责活动大型会议中的 DTMF 命令的个人虚拟协助丢失。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-231">PSTN dial in users will be unable to unmute themselves using 6 because Personal Virtual Assistance which is responsible for DTMF commands in active large meetings is missing.</span></span>

- <span data-ttu-id="7b9ac-232">如果演示者/组织者安排了应首先将其设为静音的会议（"全部静音"），PSTN 用户将在整个呼叫中静音，并且不能自行取消静音。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-232">If the presenter/organizer schedules a meeting where everyone should be muted first ("Mute All"), PSTN users will be muted throughout the call and will not be able to unmute themselves.</span></span>

<span data-ttu-id="7b9ac-233">若要禁用大型会议中不需要的会议功能，需要使用此处指定的所有会议策略设置（“最大会议规模”\*\*\*\* 设置除外）。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-233">Except for the **Maximum meeting size** setting, all the other conferencing policy settings specified here are required in order to disable conferencing capabilities that are not necessary in large meetings.</span></span>
  
<span data-ttu-id="7b9ac-234">此外，还需要配置专用的大型会议池，以便驻留在该池上并负责管理会议计划的每个 Skype for Business Server 用户拥有相应的权限。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-234">Additionally, you need to configure the dedicated large-meeting pool so that each Skype for Business Server user who is homed on the pool and responsible for managing the meeting schedule has the appropriate permissions.</span></span> <span data-ttu-id="7b9ac-235">为此，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="7b9ac-235">To do this, do the following:</span></span>
  
- <span data-ttu-id="7b9ac-p128">将“指定为演示者”\*\*\*\* 选项设置为“无”\*\*\*\*。通常，大型会议的所有参与者中仅一个或几个用户可成为演示者，因此不应自动允许参与者以演示者身份参加大型会议。相反，应在计划会议时明确指定演示者，或在大型会议进行中将参与者显式提升为演示者。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-p128">Set the **Designate as presenter** option to **None**. Typically, one or just a few users of all the participants of a large meeting are presenters, so participants should not be automatically admitted to large meetings as presenters. Instead, the presenters should be explicitly designated at meeting scheduling time, or be explicitly promoted during the large meeting.</span></span>
    
- <span data-ttu-id="7b9ac-239">确保未选中“默认分配的会议类型”\*\*\*\* 复选框。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-239">Make sure that the **Assigned conference type by default** check box is not selected.</span></span> <span data-ttu-id="7b9ac-240">此设置可控制 Skype for business 的联机会议外接程序是否始终使用组织者分配的会议安排会议，这意味着安排的会议具有相同的联接 URL 和音频信息。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-240">This setting controls whether the Online Meeting Add-in for Skype for Business always schedules conferences using the organizer's assigned conference, which means that scheduled meetings have the same join URL and audio information.</span></span> <span data-ttu-id="7b9ac-241">在小组协作方案中，可确保此类分配的会议类型很好地进行，因为每个用户均具有自己的单独分配的会议，并且持续加入 URL 和音频信息有助于推动更快的会议加入。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-241">In small group collaboration scenarios, having such assigned conference type works well because everyone has their own individual assigned conference, and the constant join URL and audio information helps to facilitate faster meeting joining.</span></span> <span data-ttu-id="7b9ac-242">但是，在大型会议方案中，大型会议支持人员将使用一组用户凭据来计划大型会议，然后向会议请求者提供加入 URL 和音频信息。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-242">However, in the large-meeting scenario, the large meeting support staff schedules the large meetings using a single set of user credentials, and then provides join URLs and audio information to the meeting requesters.</span></span> <span data-ttu-id="7b9ac-243">在此情况下，使用不同的 URL 加入各个会议所达到的效果会更佳。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-243">In this case, using a different URL to join each meeting works better.</span></span>
    
- <span data-ttu-id="7b9ac-244">确保未选中“默认允许匿名用户”\*\*\*\* 复选框，除非需要这样做。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-244">Ensure that the **Admit anonymous users by default** check box is not selected, unless it is required.</span></span> <span data-ttu-id="7b9ac-245">在不使用分配的会议时，此设置会影响由 Skype for business 的联机会议外接程序安排的默认会议访问类型。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-245">This setting affects the default meeting access type scheduled by the Online Meeting Add-in for Skype for Business when not using an assigned conference.</span></span> <span data-ttu-id="7b9ac-246">此设置的相应选项取决于您的组织的需求。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-246">The appropriate option for this setting depends on your organization's needs.</span></span> <span data-ttu-id="7b9ac-247">如果您组织的大多数大型会议是内部会议，请不要选择此选项。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-247">If most large meetings for your organization are internal meetings, do not select this option.</span></span> <span data-ttu-id="7b9ac-248">如果大多数大型会议需要外部用户能够加入，请选择此选项。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-248">If most large meetings require that external users be able to join, select this option.</span></span>
    
<span data-ttu-id="7b9ac-249">有关创建会议策略的详细信息，请参阅[在 Skype For Business Server 中管理会议策略](../../manage/conferencing/conferencing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="7b9ac-249">For more information about creating a conferencing policy, see [Manage conferencing policies in Skype for Business Server](../../manage/conferencing/conferencing-policies.md).</span></span>
  

