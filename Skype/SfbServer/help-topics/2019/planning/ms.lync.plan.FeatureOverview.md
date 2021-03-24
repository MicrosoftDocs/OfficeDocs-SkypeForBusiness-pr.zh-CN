---
title: '功能概述 (规划工具) '
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.plan.FeatureOverview
- ms.lync.plan.FeatureOverview
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 44783b37-c87f-41f2-9de1-39176f1856ab
ROBOTS: NOINDEX, NOFOLLOW
description: Skype for Business Server 规划工具
ms.openlocfilehash: 4084d263a693a064e06a814d2fab4542ca3142c0
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093320"
---
# <a name="feature-overview-planning-tool"></a><span data-ttu-id="ebd75-103">功能概述 (规划工具) </span><span class="sxs-lookup"><span data-stu-id="ebd75-103">Feature Overview (Planning Tool)</span></span>
 
<span data-ttu-id="ebd75-104">Skype for Business Server 规划工具</span><span class="sxs-lookup"><span data-stu-id="ebd75-104">Skype for Business Server Planning Tool</span></span>
  
<span data-ttu-id="ebd75-105">可以使用规划 **工具的"中央站点** "页设计 Skype for Business Server 部署。</span><span class="sxs-lookup"><span data-stu-id="ebd75-105">You can use the **Central Sites** page of the Planning Tool to design the Skype for Business Server deployment.</span></span> <span data-ttu-id="ebd75-106">可以创建两个集中部署或分布式部署。</span><span class="sxs-lookup"><span data-stu-id="ebd75-106">You can create two either a centralized or distributed deployment.</span></span> <span data-ttu-id="ebd75-107">集中式部署只有一个中央站点，用于存储组织的所有 Skype for Business 用户。</span><span class="sxs-lookup"><span data-stu-id="ebd75-107">A centralized deployment only has one central site, which homes all Skype for Business users in your organization.</span></span> <span data-ttu-id="ebd75-108">分布式部署具有多个中央站点。</span><span class="sxs-lookup"><span data-stu-id="ebd75-108">A distributed deployment has more than one central site.</span></span> <span data-ttu-id="ebd75-109">如果在多个中央站点部署 Skype for Business Server，你将在规划工具中输入每个中央站点的用户数。</span><span class="sxs-lookup"><span data-stu-id="ebd75-109">If you deploy Skype for Business Server at multiple central sites, then you will enter the number of users at each central site in the Planning Tool.</span></span>
  
<span data-ttu-id="ebd75-110">若要完成中央站点的定义，首先需要提供以下信息：</span><span class="sxs-lookup"><span data-stu-id="ebd75-110">To complete the definition of the central site, you first need to provide the following information:</span></span>
  
- <span data-ttu-id="ebd75-111">**网站名称** 输入中央站点的名称。</span><span class="sxs-lookup"><span data-stu-id="ebd75-111">**Site Name** Enter the name of the Central Site.</span></span>
    
- <span data-ttu-id="ebd75-112">**用户数** 输入用户数，包括分支站点中位于中央站点的用户数。</span><span class="sxs-lookup"><span data-stu-id="ebd75-112">**Number of Users** Enter the number of users, including users at branch sites who are homed into the central site.</span></span>
    
- <span data-ttu-id="ebd75-113">**云托管用户** 输入从 Skype for Business Online 中位于中央站点的用户数。</span><span class="sxs-lookup"><span data-stu-id="ebd75-113">**Cloud Homed Users** Enter the number of users that are homed into the central site from Skype for Business Online.</span></span>
    
## <a name="ui-elements"></a><span data-ttu-id="ebd75-114">UI 元素</span><span class="sxs-lookup"><span data-stu-id="ebd75-114">UI Elements</span></span>

<span data-ttu-id="ebd75-115">其余元素已填充为"入门"向导中的问题提供的答案，或者，如果跳过了向导，规划工具将自动填充这些元素。</span><span class="sxs-lookup"><span data-stu-id="ebd75-115">The remaining elements have either been populated with the answers you provided to the questions presented in the **Get Started** wizard, or, if you skipped the wizard, automatically populated by the planning tool.</span></span>
  
### <a name="online-collaboration"></a><span data-ttu-id="ebd75-116">联机协作</span><span class="sxs-lookup"><span data-stu-id="ebd75-116">Online Collaboration</span></span>

 <span data-ttu-id="ebd75-117">**联机协作** 包含以下选项：</span><span class="sxs-lookup"><span data-stu-id="ebd75-117">**Online Collaboration** contains the following options:</span></span>
  
- <span data-ttu-id="ebd75-118">**IM 和状态**</span><span class="sxs-lookup"><span data-stu-id="ebd75-118">**IM and Presence**</span></span>
    
    <span data-ttu-id="ebd75-119">即时消息 (IM) 使用户可以使用基于文本的消息在计算机中实时相互通信。</span><span class="sxs-lookup"><span data-stu-id="ebd75-119">Instant Messaging (IM) enables users to communicate with each other in real time on their computers using text-based messages.</span></span> <span data-ttu-id="ebd75-120">支持双方和多方之间的 IM 会话。</span><span class="sxs-lookup"><span data-stu-id="ebd75-120">Both two-party and multiparty IM sessions are supported.</span></span> <span data-ttu-id="ebd75-121">状态会为用户提供有关网络上其他人的状态的信息。</span><span class="sxs-lookup"><span data-stu-id="ebd75-121">Presence provides information to users about the status of others on the network.</span></span> <span data-ttu-id="ebd75-122">用户的状态信息可帮助其他人确定用户是否联机以及如何最好地与用户联系。</span><span class="sxs-lookup"><span data-stu-id="ebd75-122">A user's presence status provides information to help others determine whether the user is online and how to best contact the user.</span></span> <span data-ttu-id="ebd75-123">例如，最好通过电子邮件联系正在参加会议的用户。</span><span class="sxs-lookup"><span data-stu-id="ebd75-123">For example, a user who is in a meeting is best contacted by email.</span></span>
    
- <span data-ttu-id="ebd75-124">**音频和视频会议**</span><span class="sxs-lookup"><span data-stu-id="ebd75-124">**Audio and Video Conferencing**</span></span>
    
    <span data-ttu-id="ebd75-125">音频/ (A/V) 会议支持实时音频和视频会议。</span><span class="sxs-lookup"><span data-stu-id="ebd75-125">Audio/Video (A/V) conferencing enables real-time audio and video conferences.</span></span>
    
- <span data-ttu-id="ebd75-126">**电话拨入式会议**</span><span class="sxs-lookup"><span data-stu-id="ebd75-126">**Dial-in Conferencing**</span></span>
    
    <span data-ttu-id="ebd75-127">电话拨入式会议使用户能够从 PSTN 上的电话加入 A/V。</span><span class="sxs-lookup"><span data-stu-id="ebd75-127">Dial-in conferencing enables users to join an A/V from a telephone on the PSTN.</span></span> <span data-ttu-id="ebd75-128">电话拨入式会议要求部署会议助理和会议通知服务应用程序。</span><span class="sxs-lookup"><span data-stu-id="ebd75-128">Dial-in conferencing requires that you deploy the Conferencing Attendant and Conferencing Announcement Service applications.</span></span>
    
- <span data-ttu-id="ebd75-129">**Web 会议**</span><span class="sxs-lookup"><span data-stu-id="ebd75-129">**Web Conferencing**</span></span>
    
    <span data-ttu-id="ebd75-130">Web 会议使防火墙内外的企业用户能够创建和加入内部服务器上承载实时会议。</span><span class="sxs-lookup"><span data-stu-id="ebd75-130">Web conferencing enables enterprise users inside and outside of the firewall to create and join real-time conferences that are hosted on your internal servers.</span></span>
    
- <span data-ttu-id="ebd75-131">**持久聊天**</span><span class="sxs-lookup"><span data-stu-id="ebd75-131">**Persistent Chat**</span></span>
    
    <span data-ttu-id="ebd75-132">持久聊天使多个用户可以参与对话，用户可在对话中发布和访问有关特定主题的内容，包括文本、链接和文件。</span><span class="sxs-lookup"><span data-stu-id="ebd75-132">Persistent Chat enables multiple users to participate in conversations in which they post and access content about specific topics, including text, links, and files.</span></span> <span data-ttu-id="ebd75-133">尽管用户可以在会话期间实时进行通信，但每个会话的内容都可以持久保存，也就是说，在会话结束后依然可以获得这些内容。</span><span class="sxs-lookup"><span data-stu-id="ebd75-133">Although users can communicate in real time during a session, the content of each session is persistent, which means it continues to be available after a session ends.</span></span>

    > [!NOTE] 
    > <span data-ttu-id="ebd75-134">持久聊天在 Skype for Business Server 2015 中可用，但在 Skype for Business Server 2019 中不再受支持。</span><span class="sxs-lookup"><span data-stu-id="ebd75-134">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="ebd75-135">Teams 中提供了相同的功能。</span><span class="sxs-lookup"><span data-stu-id="ebd75-135">The same functionality is available in Teams.</span></span> <span data-ttu-id="ebd75-136">有关详细信息，请参阅 [Skype for Business 到 Microsoft Teams 的升级](/MicrosoftTeams/upgrade-start-here)。</span><span class="sxs-lookup"><span data-stu-id="ebd75-136">For more information, see [Skype for Business to Microsoft Teams upgrade](/MicrosoftTeams/upgrade-start-here).</span></span> <span data-ttu-id="ebd75-137">如果需要使用持久聊天，你的选择是：将需要此功能的用户迁移到 Teams，或者继续使用 Skype for Business Server 2015。</span><span class="sxs-lookup"><span data-stu-id="ebd75-137">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams or continue using Skype for Business Server 2015.</span></span>
    
### <a name="users"></a><span data-ttu-id="ebd75-138">用户</span><span class="sxs-lookup"><span data-stu-id="ebd75-138">Users</span></span>

 <span data-ttu-id="ebd75-139">**用户** 包含以下选项：</span><span class="sxs-lookup"><span data-stu-id="ebd75-139">**Users** contains the following options:</span></span>
  
- <span data-ttu-id="ebd75-140">**内部组织**</span><span class="sxs-lookup"><span data-stu-id="ebd75-140">**Internal organization**</span></span>
    
- <span data-ttu-id="ebd75-141">**与其他组织的联盟**</span><span class="sxs-lookup"><span data-stu-id="ebd75-141">**Federation with other organizations**</span></span>
    
- <span data-ttu-id="ebd75-142">**与以前版本的联盟**</span><span class="sxs-lookup"><span data-stu-id="ebd75-142">**Federation with previous versions**</span></span>
    
- <span data-ttu-id="ebd75-143">**与公共 IM 服务提供商联盟** 允许贵组织的用户与公共即时消息服务提供商（如 MSN、Yahoo！和 AOL）建立通信。</span><span class="sxs-lookup"><span data-stu-id="ebd75-143">**Federation with public IM services providers** Allows users in your organization to establish communication with public instant messaging service providers such as MSN, Yahoo!, and AOL.</span></span> <span data-ttu-id="ebd75-144">与公共即时消息网络建立联盟需要单独的许可证。</span><span class="sxs-lookup"><span data-stu-id="ebd75-144">A separate license is required to establish federation with public instant messaging networks.</span></span>
    
- <span data-ttu-id="ebd75-145">**与基于 XMPP 的服务提供商联盟**</span><span class="sxs-lookup"><span data-stu-id="ebd75-145">**Federation with XMPP-based service provider**</span></span>
    
    <span data-ttu-id="ebd75-146">Skype for Business Server 2015 引入了完全集成的 XMPP 代理 (部署在边缘服务器) 和 XMPP 网关部署在前端服务器上。</span><span class="sxs-lookup"><span data-stu-id="ebd75-146">Skype for Business Server 2015 introduced a fully integrated XMPP proxy (deployed on the Edge Servers) and an XMPP gateway deployed on your Front End Servers.</span></span> <span data-ttu-id="ebd75-147">你可以部署添加和配置 XMPP 代理和 XMPP 网关将允许 Skype for Business Server 用户添加来自基于 XMPP 的合作伙伴的联系人，以便 (IM) 和状态。</span><span class="sxs-lookup"><span data-stu-id="ebd75-147">You can deploy Adding and configuring the XMPP proxy and XMPP gateway will allow your Skype for Business Server users to add contacts from XMPP-based partners for instant messaging (IM) and presence.</span></span>
    
- <span data-ttu-id="ebd75-148">**行动能力**</span><span class="sxs-lookup"><span data-stu-id="ebd75-148">**Mobility**</span></span>
    
    <span data-ttu-id="ebd75-149">部署 Skype for Business Server Mobility Service 时，用户可以使用受支持的 Apple iOS、Android、Windows Phone 或 Nokia 移动设备执行发送和接收即时消息、查看联系人和查看状态等活动。</span><span class="sxs-lookup"><span data-stu-id="ebd75-149">When you deploy the Skype for Business Server Mobility Service, users can use supported Apple iOS, Android, Windows Phone, or Nokia mobile devices to perform such activities as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span>
    
- <span data-ttu-id="ebd75-150">**W15 Exchange 邮箱**</span><span class="sxs-lookup"><span data-stu-id="ebd75-150">**W15 Exchange mailbox**</span></span>
    
    <span data-ttu-id="ebd75-151">Skype for Business Server 使您可以将语音邮件存储在 Exchange 统一消息 (UM) ;这些语音邮件随后将在用户的收件箱中显示为电子邮件。</span><span class="sxs-lookup"><span data-stu-id="ebd75-151">Skype for Business Server enables you to have voicemail messages stored in Exchange Unified Messaging (UM); those voicemail messages will then appear as email messages in your users' Inboxes.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ebd75-152">Exchange 2019 中不再提供以前已知的 Exchange 统一消息，但您仍可以使用电话系统录制语音邮件，然后在用户的 Exchange 邮箱中保留录制。</span><span class="sxs-lookup"><span data-stu-id="ebd75-152">Exchange Unified Messaging as previously known is no longer available in Exchange 2019, but you can still use Phone System to record voicemail messages and then leave the recording in a user's Exchange mailbox.</span></span> <span data-ttu-id="ebd75-153">有关详细信息 [，请参阅规划](../../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) 云语音邮件服务。</span><span class="sxs-lookup"><span data-stu-id="ebd75-153">See [Plan Cloud Voicemail service](../../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) for more information.</span></span>
    
### <a name="voice"></a><span data-ttu-id="ebd75-154">语音</span><span class="sxs-lookup"><span data-stu-id="ebd75-154">Voice</span></span>

 <span data-ttu-id="ebd75-155">**语音** 包含以下选项：</span><span class="sxs-lookup"><span data-stu-id="ebd75-155">**Voice** contains the following options:</span></span>
  
- <span data-ttu-id="ebd75-156">**企业语音**</span><span class="sxs-lookup"><span data-stu-id="ebd75-156">**Enterprise Voice**</span></span>
    
    <span data-ttu-id="ebd75-157">企业语音是 Microsft 的软件支持 VoIP 解决方案。</span><span class="sxs-lookup"><span data-stu-id="ebd75-157">Enterprise voice is Microsft's software-powered VoIP solution.</span></span> <span data-ttu-id="ebd75-158">企业语音允许用户使用 Skype for Business 从他们的计算机发出电话呼叫。</span><span class="sxs-lookup"><span data-stu-id="ebd75-158">Enterprise voice enables users to use Skype for Business to place a phone call from their computer.</span></span>
    
- <span data-ttu-id="ebd75-159">**Exchange 统一消息**</span><span class="sxs-lookup"><span data-stu-id="ebd75-159">**Exchange Unified Messaging**</span></span>
    
    <span data-ttu-id="ebd75-160">Exchange 统一 (UM) 将语音邮件和电子邮件合并到单个邮件基础结构中。</span><span class="sxs-lookup"><span data-stu-id="ebd75-160">Exchange Unified Messaging (UM) combines voice mail and email into a single messaging infrastructure.</span></span> <span data-ttu-id="ebd75-161">Skype for Business Server 2015 使用 Exchange UM 提供呼叫应答、订阅者访问、呼叫通知和自动助理服务。</span><span class="sxs-lookup"><span data-stu-id="ebd75-161">Skype for Business Server 2015 uses Exchange UM to provide call answering, subscriber access, call notification, and auto attendant services.</span></span> <span data-ttu-id="ebd75-162">如果使用这些服务，则需要在共享的 Active Directory 拓扑中集成 Exchange UM 和 Skype for Business Server。</span><span class="sxs-lookup"><span data-stu-id="ebd75-162">If you use these services, you will need to integrate Exchange UM and Skype for Business Server in a shared Active Directory topology.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ebd75-163">Exchange 2019 中不再提供以前已知的 Exchange 统一消息，但您仍可以使用电话系统录制语音邮件，然后在用户的 Exchange 邮箱中保留录制。</span><span class="sxs-lookup"><span data-stu-id="ebd75-163">Exchange Unified Messaging as previously known is no longer available in Exchange 2019, but you can still use Phone System to record voicemail messages and then leave the recording in a user's Exchange mailbox.</span></span> <span data-ttu-id="ebd75-164">有关详细信息 [，请参阅规划](../../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) 云语音邮件服务。</span><span class="sxs-lookup"><span data-stu-id="ebd75-164">See [Plan Cloud Voicemail service](../../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) for more information.</span></span>
    
### <a name="additional-deployment-options"></a><span data-ttu-id="ebd75-165">其他部署选项</span><span class="sxs-lookup"><span data-stu-id="ebd75-165">Additional Deployment Options</span></span>

 <span data-ttu-id="ebd75-166">**其他部署选项** 包含以下选项：</span><span class="sxs-lookup"><span data-stu-id="ebd75-166">**Additional Deployment Options** contains the following options:</span></span>
  
- <span data-ttu-id="ebd75-167">**高可用性**</span><span class="sxs-lookup"><span data-stu-id="ebd75-167">**High Availability**</span></span>
    
    <span data-ttu-id="ebd75-168">高可用性为备用服务器启用故障转移支持。</span><span class="sxs-lookup"><span data-stu-id="ebd75-168">High availability enables standby servers for failover support.</span></span>
    
- <span data-ttu-id="ebd75-169">**灾难恢复**</span><span class="sxs-lookup"><span data-stu-id="ebd75-169">**Disaster Recovery**</span></span>
    
    <span data-ttu-id="ebd75-170">灾难恢复措施使您能够对位于两个数据中心的前端池进行配对。</span><span class="sxs-lookup"><span data-stu-id="ebd75-170">Disaster recovery measures enable you to pair Front End pools located in two datacenters.</span></span>
    
- <span data-ttu-id="ebd75-171">**监视**</span><span class="sxs-lookup"><span data-stu-id="ebd75-171">**Monitoring**</span></span>
    
    <span data-ttu-id="ebd75-172">监控捕获与通信会话相关的呼叫详细信息记录。</span><span class="sxs-lookup"><span data-stu-id="ebd75-172">Monitoring captures call detail records related to communication sessions.</span></span> <span data-ttu-id="ebd75-173">它还从参与者终结点的音频和视频会话收集指标。</span><span class="sxs-lookup"><span data-stu-id="ebd75-173">It also collects metrics from audio and video sessions at the participant endpoints.</span></span> <span data-ttu-id="ebd75-174">监控服务器提供使用情况统计信息、趋势和媒体质量统计信息。</span><span class="sxs-lookup"><span data-stu-id="ebd75-174">Monitoring Server provides usage statistics, trends, and media quality statistics.</span></span>
    
- <span data-ttu-id="ebd75-175">**存档**</span><span class="sxs-lookup"><span data-stu-id="ebd75-175">**Archiving**</span></span>
    
    <span data-ttu-id="ebd75-176">存档存储即时消息对话和会议。</span><span class="sxs-lookup"><span data-stu-id="ebd75-176">Archiving stores instant messaging conversations and conferences.</span></span>
    
- <span data-ttu-id="ebd75-177">**Exchange 存档集成**</span><span class="sxs-lookup"><span data-stu-id="ebd75-177">**Exchange Archiving Integration**</span></span>
    
    <span data-ttu-id="ebd75-178">如果你的用户位于 Exchange 上并且其邮箱已被置于 In-Place 保留状态，可以选择将 Skype for Business Server 存储与 Exchange 存储集成。</span><span class="sxs-lookup"><span data-stu-id="ebd75-178">If you have users who are homed on Exchange and their mailboxes have been put on In-Place Hold, you can select the option to integrate Skype for Business Server storage with Exchange storage.</span></span>
    
- <span data-ttu-id="ebd75-179">**IPv4**</span><span class="sxs-lookup"><span data-stu-id="ebd75-179">**IPv4**</span></span>
    
    <span data-ttu-id="ebd75-180">IPv4 地址是 32 位地址，允许计算机通过 Internet 进行通信。</span><span class="sxs-lookup"><span data-stu-id="ebd75-180">IPv4 addresses are 32-bit addresses that allow a computer to communicate over the Internet.</span></span> <span data-ttu-id="ebd75-181">由于全球设备数量不断增加，可用 IPv4 地址已用完。因此，许多新设备都迁移到使用 IPv6 地址。</span><span class="sxs-lookup"><span data-stu-id="ebd75-181">Due to the increasing number of devices worldwide, the available IPv4 addresses have run out. Because of this, many new devices are moving to using IPv6 addresses.</span></span>
    
- <span data-ttu-id="ebd75-182">**IPv6**</span><span class="sxs-lookup"><span data-stu-id="ebd75-182">**IPv6**</span></span>
    
    <span data-ttu-id="ebd75-183">IPv6 地址执行与 IPv4 地址相同的功能（另外还有一些附加功能），但 IPv6 地址不仅使用 32 位，而且还使用 128 位。</span><span class="sxs-lookup"><span data-stu-id="ebd75-183">IPv6 addresses perform the same function as IPv4 addresses (with some additional features), but instead of using only 32-bits, IPv6 addresses use 128-bits.</span></span> <span data-ttu-id="ebd75-184">这不仅提供了一组新的地址，而且数量远远超过原来的地址集。</span><span class="sxs-lookup"><span data-stu-id="ebd75-184">This provides not only a new set of addresses, but also a much larger number of them.</span></span>
    
- <span data-ttu-id="ebd75-185">**设备更新 Web 服务**</span><span class="sxs-lookup"><span data-stu-id="ebd75-185">**Device Update Web service**</span></span>
    
    <span data-ttu-id="ebd75-186">设备更新 Web 服务提供了用于更新在组织外部部署的所有设备（如 Skype for Business for Windows Phone）的自动化方法。</span><span class="sxs-lookup"><span data-stu-id="ebd75-186">The Device Update Web service provides an automated way to update all devices, such as Skype for Business for Windows Phone, that are deployed outside of your organization.</span></span>
    
### <a name="server-applications"></a><span data-ttu-id="ebd75-187">服务器应用程序</span><span class="sxs-lookup"><span data-stu-id="ebd75-187">Server Applications</span></span>

 <span data-ttu-id="ebd75-188">**服务器应用程序** 包含以下选项：</span><span class="sxs-lookup"><span data-stu-id="ebd75-188">**Server Applications** contains the following options:</span></span>
  
- <span data-ttu-id="ebd75-189">**响应组**</span><span class="sxs-lookup"><span data-stu-id="ebd75-189">**Response Group**</span></span>
    
    <span data-ttu-id="ebd75-190">响应组应用程序会自动应答呼叫并将呼叫分发给可用的支持人员代理。</span><span class="sxs-lookup"><span data-stu-id="ebd75-190">The Response Group application automatically answers and distributes calls to an available helpdesk agent.</span></span>
    
- <span data-ttu-id="ebd75-191">**公告**</span><span class="sxs-lookup"><span data-stu-id="ebd75-191">**Announcement**</span></span>
    
    <span data-ttu-id="ebd75-192">如果计划部署企业语音，可能需要能够配置拨打的号码有效但没有分配给用户公用区域时如何处理电话呼叫。</span><span class="sxs-lookup"><span data-stu-id="ebd75-192">If you plan to deploy Enterprise Voice, you might want to be able to configure how phone calls are handled if the dialed number is valid but not assigned to a user common area.</span></span> <span data-ttu-id="ebd75-193">管理员可以配置通知服务，以便这些呼叫转接到预先确定的目标 (电话号码或 SIP URI) 播放音频通知或同时播放两者。</span><span class="sxs-lookup"><span data-stu-id="ebd75-193">Administrators can configure Announcement Service so that these calls transfer to a predetermined destination (phone number or SIP URI) or play an audio announcement or both.</span></span> <span data-ttu-id="ebd75-194">使用通知服务可以避免呼叫者拨错电话并听到忙音或 SIP 客户端收到错误消息的情况。</span><span class="sxs-lookup"><span data-stu-id="ebd75-194">Using Announcement Service avoids the situation in which a caller misdials and hears a busy tone or the SIP client receives an error message.</span></span> <span data-ttu-id="ebd75-195">通知服务功能是典型的 PBX 功能。</span><span class="sxs-lookup"><span data-stu-id="ebd75-195">Announcement Service functionality is a typical PBX feature.</span></span> 
    
- <span data-ttu-id="ebd75-196">**呼叫寄存**</span><span class="sxs-lookup"><span data-stu-id="ebd75-196">**Call Park**</span></span>
    
    <span data-ttu-id="ebd75-197">呼叫保留应用程序使呼叫企业语音用户从一部电话将呼叫置于保持状态，然后从另一部电话接收呼叫，而不会使接听该呼叫的电话上的资源增加。</span><span class="sxs-lookup"><span data-stu-id="ebd75-197">Call Park application enables an Enterprise Voice user to put a call on hold from one telephone, and then receive the call from another telephone without tying up resources on the phone that received the call.</span></span> <span data-ttu-id="ebd75-198">当用户需要转接呼叫，但特定收件人未知时，呼叫呼叫管理应用程序非常有用。</span><span class="sxs-lookup"><span data-stu-id="ebd75-198">Call Park application is useful when a user needs to transfer a call, but the specific recipient is unknown.</span></span> 
    
- <span data-ttu-id="ebd75-199">**会议助理**</span><span class="sxs-lookup"><span data-stu-id="ebd75-199">**Conference Attendant**</span></span>
    
    <span data-ttu-id="ebd75-200">会议助理应用程序向没有第三方音频会议提供商服务的电话用户提供音频会议功能。</span><span class="sxs-lookup"><span data-stu-id="ebd75-200">Conferencing Attendant application provides audio conferencing capabilities to phone users without the service of a third-party audio conferencing provider.</span></span>
    
- <span data-ttu-id="ebd75-201">**会议通知**</span><span class="sxs-lookup"><span data-stu-id="ebd75-201">**Conferencing Announcement**</span></span>
    
    <span data-ttu-id="ebd75-202">会议通知应用程序会生成提示音，在用户进入或离开会议时发出信号，以及电话用户被静音或取消静音时向这些用户发送通知。</span><span class="sxs-lookup"><span data-stu-id="ebd75-202">Conferencing Announcement application produces tones that signal when users enter or leave a conference, as well as notifications to phone users when they are muted or unmuted.</span></span>
    
- <span data-ttu-id="ebd75-203">**呼叫允许控制**</span><span class="sxs-lookup"><span data-stu-id="ebd75-203">**Call Admission Control**</span></span>
    
    <span data-ttu-id="ebd75-204">呼叫允许控制 (CAC) 也称为 WAN 带宽管理，它根据可用带宽确定是否允许建立新的实时通信会话，帮助防止出现塞塞网络的用户体验质量差。</span><span class="sxs-lookup"><span data-stu-id="ebd75-204">Call Admission Control (CAC), also known as WAN bandwidth management, helps to prevent poor quality of experience for users on congested networks by determining, based on available bandwidth, whether to allow and new real-time communications sessions to be established.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="ebd75-205">CAC 仅控制实时流量，不会影响数据流量。</span><span class="sxs-lookup"><span data-stu-id="ebd75-205">CAC only controls real-time traffic and does not affect data traffic.</span></span> 
  
    <span data-ttu-id="ebd75-206">如果新语音或视频会话超出在 WAN 上分配的带宽限制，则只会将 (呼叫的会话阻止或) 重新路由到 PSTN。</span><span class="sxs-lookup"><span data-stu-id="ebd75-206">If a new voice or video session exceeds the bandwidth limits that you have allocated on a WAN, the session is either blocked or (for phone calls only) rerouted to the PSTN.</span></span>
