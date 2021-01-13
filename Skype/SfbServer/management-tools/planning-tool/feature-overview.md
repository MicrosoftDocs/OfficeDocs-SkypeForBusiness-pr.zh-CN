---
title: '功能概述 (规划工具) '
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/6/2016
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.plan.FeatureOverview
- ms.lync.plan.FeatureOverview
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 44783b37-c87f-41f2-9de1-39176f1856ab
description: Skype for Business Server 2015 规划工具
ms.openlocfilehash: 3aa259314d8a92142cf37dcd3611773490248e02
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834782"
---
# <a name="feature-overview-planning-tool"></a><span data-ttu-id="37240-103">功能概述 (规划工具) </span><span class="sxs-lookup"><span data-stu-id="37240-103">Feature Overview (Planning Tool)</span></span>
 
<span data-ttu-id="37240-104">Skype for Business Server 2015 规划工具</span><span class="sxs-lookup"><span data-stu-id="37240-104">Skype for Business Server 2015 Planning Tool</span></span>
  
<span data-ttu-id="37240-105">可以使用规划工具 **的** "中央站点"页设计 Skype for Business Server 部署。</span><span class="sxs-lookup"><span data-stu-id="37240-105">You can use the **Central Sites** page of the Planning Tool to design the Skype for Business Server deployment.</span></span> <span data-ttu-id="37240-106">可以创建两个集中部署或分布式部署。</span><span class="sxs-lookup"><span data-stu-id="37240-106">You can create two either a centralized or distributed deployment.</span></span> <span data-ttu-id="37240-107">集中式部署只有一个中央站点，该中央站点用于组织的所有 Skype for Business 用户。</span><span class="sxs-lookup"><span data-stu-id="37240-107">A centralized deployment only has one central site, which homes all Skype for Business users in your organization.</span></span> <span data-ttu-id="37240-108">分布式部署具有多个中央站点。</span><span class="sxs-lookup"><span data-stu-id="37240-108">A distributed deployment has more than one central site.</span></span> <span data-ttu-id="37240-109">如果在多个中央站点部署 Skype for Business Server，你将在规划工具中输入每个中央站点的用户数。</span><span class="sxs-lookup"><span data-stu-id="37240-109">If you deploy Skype for Business Server at multiple central sites, then you will enter the number of users at each central site in the Planning Tool.</span></span>
  
<span data-ttu-id="37240-110">若要完成中央网站的定义，首先需要提供以下信息：</span><span class="sxs-lookup"><span data-stu-id="37240-110">To complete the definition of the central site, you first need to provide the following information:</span></span>
  
- <span data-ttu-id="37240-111">**网站名称** 输入中央站点的名称。</span><span class="sxs-lookup"><span data-stu-id="37240-111">**Site Name** Enter the name of the Central Site.</span></span>
    
- <span data-ttu-id="37240-112">**用户数** 输入用户数，包括分支站点中位于中央站点的用户。</span><span class="sxs-lookup"><span data-stu-id="37240-112">**Number of Users** Enter the number of users, including users at branch sites who are homed into the central site.</span></span>
    
- <span data-ttu-id="37240-113">**云托管用户** 输入从 Skype for Business Online 中位于中央站点的用户数。</span><span class="sxs-lookup"><span data-stu-id="37240-113">**Cloud Homed Users** Enter the number of users that are homed into the central site from Skype for Business Online.</span></span>
    
> [!NOTE]
> <span data-ttu-id="37240-114">此工具不会针对 Skype for Business Server 2019 进行更新。</span><span class="sxs-lookup"><span data-stu-id="37240-114">This tool will not be updated for Skype for Business Server 2019.</span></span>

## <a name="ui-elements"></a><span data-ttu-id="37240-115">UI 元素</span><span class="sxs-lookup"><span data-stu-id="37240-115">UI Elements</span></span>

<span data-ttu-id="37240-116">其余元素已填充为"入门"向导中提供的问题答案，或者，如果跳过了向导，则由规划工具自动填充。</span><span class="sxs-lookup"><span data-stu-id="37240-116">The remaining elements have either been populated with the answers you provided to the questions presented in the **Get Started** wizard, or, if you skipped the wizard, automatically populated by the planning tool.</span></span>
  
### <a name="online-collaboration"></a><span data-ttu-id="37240-117">联机协作</span><span class="sxs-lookup"><span data-stu-id="37240-117">Online Collaboration</span></span>

 <span data-ttu-id="37240-118">**联机协作** 包含以下选项：</span><span class="sxs-lookup"><span data-stu-id="37240-118">**Online Collaboration** contains the following options:</span></span>
  
- <span data-ttu-id="37240-119">**IM 和状态**</span><span class="sxs-lookup"><span data-stu-id="37240-119">**IM and Presence**</span></span>
    
    <span data-ttu-id="37240-120">即时消息 (IM) 使用户可以使用基于文本的消息在计算机中实时相互通信。</span><span class="sxs-lookup"><span data-stu-id="37240-120">Instant Messaging (IM) enables users to communicate with each other in real time on their computers using text-based messages.</span></span> <span data-ttu-id="37240-121">支持双方和多方之间的 IM 会话。</span><span class="sxs-lookup"><span data-stu-id="37240-121">Both two-party and multiparty IM sessions are supported.</span></span> <span data-ttu-id="37240-122">状态会向用户提供有关网络上其他人的状态的信息。</span><span class="sxs-lookup"><span data-stu-id="37240-122">Presence provides information to users about the status of others on the network.</span></span> <span data-ttu-id="37240-123">用户的状态信息可帮助其他人确定用户是否联机以及如何最好地与用户联系。</span><span class="sxs-lookup"><span data-stu-id="37240-123">A user's presence status provides information to help others determine whether the user is online and how to best contact the user.</span></span> <span data-ttu-id="37240-124">例如，最好通过电子邮件联系参加会议的用户。</span><span class="sxs-lookup"><span data-stu-id="37240-124">For example, a user who is in a meeting is best contacted by email.</span></span>
    
- <span data-ttu-id="37240-125">**音频和视频会议**</span><span class="sxs-lookup"><span data-stu-id="37240-125">**Audio and Video Conferencing**</span></span>
    
    <span data-ttu-id="37240-126">音频/ (A/V) 会议支持实时音频和视频会议。</span><span class="sxs-lookup"><span data-stu-id="37240-126">Audio/Video (A/V) conferencing enables real-time audio and video conferences.</span></span>
    
- <span data-ttu-id="37240-127">**电话拨入式会议**</span><span class="sxs-lookup"><span data-stu-id="37240-127">**Dial-in Conferencing**</span></span>
    
    <span data-ttu-id="37240-128">电话拨入式会议使用户能够从 PSTN 上的电话加入 A/V。</span><span class="sxs-lookup"><span data-stu-id="37240-128">Dial-in conferencing enables users to join an A/V from a telephone on the PSTN.</span></span> <span data-ttu-id="37240-129">电话拨入式会议要求您部署会议助理和会议通知服务应用程序。</span><span class="sxs-lookup"><span data-stu-id="37240-129">Dial-in conferencing requires that you deploy the Conferencing Attendant and Conferencing Announcement Service applications.</span></span>
    
- <span data-ttu-id="37240-130">**Web 会议**</span><span class="sxs-lookup"><span data-stu-id="37240-130">**Web Conferencing**</span></span>
    
    <span data-ttu-id="37240-131">Web 会议使防火墙内外的企业用户能够创建和加入内部服务器上承载实时会议。</span><span class="sxs-lookup"><span data-stu-id="37240-131">Web conferencing enables enterprise users inside and outside of the firewall to create and join real-time conferences that are hosted on your internal servers.</span></span>
    
- <span data-ttu-id="37240-132">**持久聊天**</span><span class="sxs-lookup"><span data-stu-id="37240-132">**Persistent Chat**</span></span>
    
    <span data-ttu-id="37240-133">持久聊天使多个用户可以参与对话，他们可在其中发布和访问有关特定主题的内容，包括文本、链接和文件。</span><span class="sxs-lookup"><span data-stu-id="37240-133">Persistent Chat enables multiple users to participate in conversations in which they post and access content about specific topics, including text, links, and files.</span></span> <span data-ttu-id="37240-134">尽管用户可以在会话期间实时进行通信，但每个会话的内容都可以持久保存，也就是说，在会话结束后依然可以获得这些内容。</span><span class="sxs-lookup"><span data-stu-id="37240-134">Although users can communicate in real time during a session, the content of each session is persistent, which means it continues to be available after a session ends.</span></span>
    
### <a name="users"></a><span data-ttu-id="37240-135">用户</span><span class="sxs-lookup"><span data-stu-id="37240-135">Users</span></span>

 <span data-ttu-id="37240-136">**用户** 包含以下选项：</span><span class="sxs-lookup"><span data-stu-id="37240-136">**Users** contains the following options:</span></span>
  
- <span data-ttu-id="37240-137">**内部组织**</span><span class="sxs-lookup"><span data-stu-id="37240-137">**Internal organization**</span></span>
    
- <span data-ttu-id="37240-138">**与其他组织的联盟**</span><span class="sxs-lookup"><span data-stu-id="37240-138">**Federation with other organizations**</span></span>
    
- <span data-ttu-id="37240-139">**与以前版本的联盟**</span><span class="sxs-lookup"><span data-stu-id="37240-139">**Federation with previous versions**</span></span>
    
- <span data-ttu-id="37240-140">**与公共 IM 服务提供商联盟** 允许贵组织的用户与 MSN、Yahoo！和 AOL 等公共即时消息服务提供商建立通信。</span><span class="sxs-lookup"><span data-stu-id="37240-140">**Federation with public IM services providers** Allows users in your organization to establish communication with public instant messaging service providers such as MSN, Yahoo!, and AOL.</span></span> <span data-ttu-id="37240-141">与公共即时消息网络建立联盟需要单独的许可证。</span><span class="sxs-lookup"><span data-stu-id="37240-141">A separate license is required to establish federation with public instant messaging networks.</span></span>
    
- <span data-ttu-id="37240-142">**与基于 XMPP 的服务提供商的联盟**</span><span class="sxs-lookup"><span data-stu-id="37240-142">**Federation with XMPP-based service provider**</span></span>
    
    <span data-ttu-id="37240-143">Skype for Business Server 2015 引入了一个完全集成的 XMPP 代理 (部署在边缘服务器) 和一个在前端服务器上部署的 XMPP 网关。</span><span class="sxs-lookup"><span data-stu-id="37240-143">Skype for Business Server 2015 introduces a fully integrated XMPP proxy (deployed on the Edge Servers) and an XMPP gateway deployed on your Front End Servers.</span></span> <span data-ttu-id="37240-144">你可以部署添加和配置 XMPP 代理，XMPP 网关将允许 Skype for Business Server 2015 用户添加来自基于 XMPP 的合作伙伴的联系人，用于即时消息 (IM) 和状态。</span><span class="sxs-lookup"><span data-stu-id="37240-144">You can deploy Adding and configuring the XMPP proxy and XMPP gateway will allow your Skype for Business Server 2015 users to add contacts from XMPP-based partners for instant messaging (IM) and presence.</span></span>

> [!NOTE]
> <span data-ttu-id="37240-145">XMPP 网关和代理在 Skype for Business Server 2015 中可用，但在 Skype for Business Server 2019 中不再受支持。</span><span class="sxs-lookup"><span data-stu-id="37240-145">XMPP Gateways and proxies are available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="37240-146">有关详细信息 [，请参阅"迁移 XMPP](../../../SfBServer2019/migration/migrating-xmpp-federation.md) 联盟"。</span><span class="sxs-lookup"><span data-stu-id="37240-146">See [Migrating XMPP federation](../../../SfBServer2019/migration/migrating-xmpp-federation.md) for more information.</span></span>
    
- <span data-ttu-id="37240-147">**移动性**</span><span class="sxs-lookup"><span data-stu-id="37240-147">**Mobility**</span></span>
    
    <span data-ttu-id="37240-148">部署 Skype for Business Server 2015 Mobility Service 时，用户可以使用受支持的 Apple iOS、Android、Windows Phone 或 Nokia 移动设备执行发送和接收即时消息、查看联系人和查看状态等活动。</span><span class="sxs-lookup"><span data-stu-id="37240-148">When you deploy the Skype for Business Server 2015 Mobility Service, users can use supported Apple iOS, Android, Windows Phone, or Nokia mobile devices to perform such activities as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span>
    
- <span data-ttu-id="37240-149">**W15 Exchange 邮箱**</span><span class="sxs-lookup"><span data-stu-id="37240-149">**W15 Exchange mailbox**</span></span>
    
    <span data-ttu-id="37240-150">Skype for Business Server 2015 使您可以将语音邮件消息存储在 Exchange 统一消息 (UM) ;这些语音邮件随后将在用户的收件箱中显示为电子邮件。</span><span class="sxs-lookup"><span data-stu-id="37240-150">Skype for Business Server 2015 enables you to have voicemail messages stored in Exchange Unified Messaging (UM); those voicemail messages will then appear as email messages in your users' Inboxes.</span></span>
    
### <a name="voice"></a><span data-ttu-id="37240-151">语音</span><span class="sxs-lookup"><span data-stu-id="37240-151">Voice</span></span>

 <span data-ttu-id="37240-152">**语音** 包含以下选项：</span><span class="sxs-lookup"><span data-stu-id="37240-152">**Voice** contains the following options:</span></span>
  
- <span data-ttu-id="37240-153">**企业语音**</span><span class="sxs-lookup"><span data-stu-id="37240-153">**Enterprise Voice**</span></span>
    
    <span data-ttu-id="37240-154">企业语音是 Microsft 的软件支持 VoIP 解决方案。</span><span class="sxs-lookup"><span data-stu-id="37240-154">Enterprise voice is Microsft's software-powered VoIP solution.</span></span> <span data-ttu-id="37240-155">企业语音允许用户使用 Skype for Business 从计算机发出电话呼叫。</span><span class="sxs-lookup"><span data-stu-id="37240-155">Enterprise voice enables users to use Skype for Business to place a phone call from their computer.</span></span>
    
- <span data-ttu-id="37240-156">**Exchange 统一消息**</span><span class="sxs-lookup"><span data-stu-id="37240-156">**Exchange Unified Messaging**</span></span>
    
    <span data-ttu-id="37240-157">Exchange 统一 (UM) 将语音邮件和电子邮件合并到单个邮件基础结构中。</span><span class="sxs-lookup"><span data-stu-id="37240-157">Exchange Unified Messaging (UM) combines voice mail and email into a single messaging infrastructure.</span></span> <span data-ttu-id="37240-158">Skype for Business Server 2015 使用 Exchange UM 提供呼叫应答、订阅者访问、呼叫通知和自动助理服务。</span><span class="sxs-lookup"><span data-stu-id="37240-158">Skype for Business Server 2015 uses Exchange UM to provide call answering, subscriber access, call notification, and auto attendant services.</span></span> <span data-ttu-id="37240-159">如果使用这些服务，则需要在共享的 Active Directory 拓扑中集成 Exchange UM 和 Skype for Business Server。</span><span class="sxs-lookup"><span data-stu-id="37240-159">If you use these services, you will need to integrate Exchange UM and Skype for Business Server in a shared Active Directory topology.</span></span>
    
### <a name="additional-deployment-options"></a><span data-ttu-id="37240-160">其他部署选项</span><span class="sxs-lookup"><span data-stu-id="37240-160">Additional Deployment Options</span></span>

 <span data-ttu-id="37240-161">**其他部署选项** 包含以下选项：</span><span class="sxs-lookup"><span data-stu-id="37240-161">**Additional Deployment Options** contains the following options:</span></span>
  
- <span data-ttu-id="37240-162">**高可用性**</span><span class="sxs-lookup"><span data-stu-id="37240-162">**High Availability**</span></span>
    
    <span data-ttu-id="37240-163">高可用性使备用服务器能够支持故障转移。</span><span class="sxs-lookup"><span data-stu-id="37240-163">High availability enables standby servers for failover support.</span></span>
    
- <span data-ttu-id="37240-164">**灾难恢复**</span><span class="sxs-lookup"><span data-stu-id="37240-164">**Disaster Recovery**</span></span>
    
    <span data-ttu-id="37240-165">灾难恢复措施使您能够对位于两个数据中心的前端池进行配对。</span><span class="sxs-lookup"><span data-stu-id="37240-165">Disaster recovery measures enable you to pair Front End pools located in two datacenters.</span></span>
    
- <span data-ttu-id="37240-166">**监视**</span><span class="sxs-lookup"><span data-stu-id="37240-166">**Monitoring**</span></span>
    
    <span data-ttu-id="37240-167">监控捕获与通信会话相关的呼叫详细信息记录。</span><span class="sxs-lookup"><span data-stu-id="37240-167">Monitoring captures call detail records related to communication sessions.</span></span> <span data-ttu-id="37240-168">它还从参与者终结点的音频和视频会话收集指标。</span><span class="sxs-lookup"><span data-stu-id="37240-168">It also collects metrics from audio and video sessions at the participant endpoints.</span></span> <span data-ttu-id="37240-169">监控服务器提供使用情况统计信息、趋势和媒体质量统计信息。</span><span class="sxs-lookup"><span data-stu-id="37240-169">Monitoring Server provides usage statistics, trends, and media quality statistics.</span></span>
    
- <span data-ttu-id="37240-170">**存档**</span><span class="sxs-lookup"><span data-stu-id="37240-170">**Archiving**</span></span>
    
    <span data-ttu-id="37240-171">存档存储即时消息对话和会议。</span><span class="sxs-lookup"><span data-stu-id="37240-171">Archiving stores instant messaging conversations and conferences.</span></span>
    
- <span data-ttu-id="37240-172">**Exchange 存档集成**</span><span class="sxs-lookup"><span data-stu-id="37240-172">**Exchange Archiving Integration**</span></span>
    
    <span data-ttu-id="37240-173">如果你的用户位于 Exchange 2013 上并且其邮箱已被置于 In-Place 保留状态，可以选择将 Skype for Business Server 2015 存储与 Exchange 存储集成。</span><span class="sxs-lookup"><span data-stu-id="37240-173">If you have users who are homed on Exchange 2013 and their mailboxes have been put on In-Place Hold, you can select the option to integrate Skype for Business Server 2015 storage with Exchange storage.</span></span>
    
- <span data-ttu-id="37240-174">**IPv4**</span><span class="sxs-lookup"><span data-stu-id="37240-174">**IPv4**</span></span>
    
    <span data-ttu-id="37240-175">IPv4 地址是 32 位地址，允许计算机通过 Internet 进行通信。</span><span class="sxs-lookup"><span data-stu-id="37240-175">IPv4 addresses are 32-bit addresses that allow a computer to communicate over the Internet.</span></span> <span data-ttu-id="37240-176">由于全球设备数量不断增加，可用 IPv4 地址已用完。因此，许多新设备都迁移到使用 IPv6 地址。</span><span class="sxs-lookup"><span data-stu-id="37240-176">Due to the increasing number of devices worldwide, the available IPv4 addresses have run out. Because of this, many new devices are moving to using IPv6 addresses.</span></span>
    
- <span data-ttu-id="37240-177">**IPv6**</span><span class="sxs-lookup"><span data-stu-id="37240-177">**IPv6**</span></span>
    
    <span data-ttu-id="37240-178">IPv6 地址执行与 IPv4 地址相同的功能（另外还有一些附加功能），但 IPv6 地址不仅使用 32 位，而且还使用 128 位。</span><span class="sxs-lookup"><span data-stu-id="37240-178">IPv6 addresses perform the same function as IPv4 addresses (with some additional features), but instead of using only 32-bits, IPv6 addresses use 128-bits.</span></span> <span data-ttu-id="37240-179">这不仅提供了一组新的地址，而且数量远远超过原来的地址集。</span><span class="sxs-lookup"><span data-stu-id="37240-179">This provides not only a new set of addresses, but also a much larger number of them.</span></span>
    
- <span data-ttu-id="37240-180">**设备更新 Web 服务**</span><span class="sxs-lookup"><span data-stu-id="37240-180">**Device Update Web service**</span></span>
    
    <span data-ttu-id="37240-181">设备更新 Web 服务提供了一种自动更新在组织外部部署的所有设备（如 Skype for Business for Windows Phone）的方法。</span><span class="sxs-lookup"><span data-stu-id="37240-181">The Device Update Web service provides an automated way to update all devices, such as Skype for Business for Windows Phone, that are deployed outside of your organization.</span></span>
    
### <a name="server-applications"></a><span data-ttu-id="37240-182">服务器应用程序</span><span class="sxs-lookup"><span data-stu-id="37240-182">Server Applications</span></span>

 <span data-ttu-id="37240-183">**服务器应用程序** 包含以下选项：</span><span class="sxs-lookup"><span data-stu-id="37240-183">**Server Applications** contains the following options:</span></span>
  
- <span data-ttu-id="37240-184">**响应组**</span><span class="sxs-lookup"><span data-stu-id="37240-184">**Response Group**</span></span>
    
    <span data-ttu-id="37240-185">响应组应用程序会自动应答呼叫并将呼叫分发给可用的支持人员代理。</span><span class="sxs-lookup"><span data-stu-id="37240-185">The Response Group application automatically answers and distributes calls to an available helpdesk agent.</span></span>
    
- <span data-ttu-id="37240-186">**公告**</span><span class="sxs-lookup"><span data-stu-id="37240-186">**Announcement**</span></span>
    
    <span data-ttu-id="37240-187">如果计划部署企业语音，可能需要能够配置拨打的号码有效但没有分配给用户公用区域时如何处理电话呼叫。</span><span class="sxs-lookup"><span data-stu-id="37240-187">If you plan to deploy Enterprise Voice, you might want to be able to configure how phone calls are handled if the dialed number is valid but not assigned to a user common area.</span></span> <span data-ttu-id="37240-188">管理员可以配置通知服务，以便这些呼叫转接到预定 (电话号码或 SIP URI) 播放音频通知或同时播放两者。</span><span class="sxs-lookup"><span data-stu-id="37240-188">Administrators can configure Announcement Service so that these calls transfer to a predetermined destination (phone number or SIP URI) or play an audio announcement or both.</span></span> <span data-ttu-id="37240-189">使用通知服务可以避免呼叫者拨错电话并听到忙音或 SIP 客户端收到错误消息的情况。</span><span class="sxs-lookup"><span data-stu-id="37240-189">Using Announcement Service avoids the situation in which a caller misdials and hears a busy tone or the SIP client receives an error message.</span></span> <span data-ttu-id="37240-190">通知服务功能是典型的 PBX 功能。</span><span class="sxs-lookup"><span data-stu-id="37240-190">Announcement Service functionality is a typical PBX feature.</span></span> 
    
- <span data-ttu-id="37240-191">**呼叫寄存**</span><span class="sxs-lookup"><span data-stu-id="37240-191">**Call Park**</span></span>
    
    <span data-ttu-id="37240-192">呼叫保留应用程序使 企业语音 用户可以从一部电话将呼叫置于保持状态，然后从另一部电话接收呼叫，而不会使接听电话上的资源不足。</span><span class="sxs-lookup"><span data-stu-id="37240-192">Call Park application enables an Enterprise Voice user to put a call on hold from one telephone, and then receive the call from another telephone without tying up resources on the phone that received the call.</span></span> <span data-ttu-id="37240-193">当用户需要转接呼叫，但特定收件人未知时，呼叫转移应用程序非常有用。</span><span class="sxs-lookup"><span data-stu-id="37240-193">Call Park application is useful when a user needs to transfer a call, but the specific recipient is unknown.</span></span> 
    
- <span data-ttu-id="37240-194">**会议助理**</span><span class="sxs-lookup"><span data-stu-id="37240-194">**Conference Attendant**</span></span>
    
    <span data-ttu-id="37240-195">会议助理应用程序为没有第三方音频会议提供商服务的电话用户提供音频会议功能。</span><span class="sxs-lookup"><span data-stu-id="37240-195">Conferencing Attendant application provides audio conferencing capabilities to phone users without the service of a third-party audio conferencing provider.</span></span>
    
- <span data-ttu-id="37240-196">**会议通知**</span><span class="sxs-lookup"><span data-stu-id="37240-196">**Conferencing Announcement**</span></span>
    
    <span data-ttu-id="37240-197">会议通知应用程序会生成提示音，以在用户进入或离开会议时发出信号，在电话用户静音或取消静音时向这些用户发送通知。</span><span class="sxs-lookup"><span data-stu-id="37240-197">Conferencing Announcement application produces tones that signal when users enter or leave a conference, as well as notifications to phone users when they are muted or unmuted.</span></span>
    
- <span data-ttu-id="37240-198">**呼叫允许控制**</span><span class="sxs-lookup"><span data-stu-id="37240-198">**Call Admission Control**</span></span>
    
    <span data-ttu-id="37240-199">呼叫允许控制 (CAC) 也称为 WAN 带宽管理，它根据可用带宽确定是否允许和建立新的实时通信会话，帮助防止在交通塞塞网络上用户获得较差的体验质量。</span><span class="sxs-lookup"><span data-stu-id="37240-199">Call Admission Control (CAC), also known as WAN bandwidth management, helps to prevent poor quality of experience for users on congested networks by determining, based on available bandwidth, whether to allow and new real-time communications sessions to be established.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="37240-200">CAC 仅控制实时流量，不会影响数据流量。</span><span class="sxs-lookup"><span data-stu-id="37240-200">CAC only controls real-time traffic and does not affect data traffic.</span></span> 
  
    <span data-ttu-id="37240-201">如果新语音或视频会话超出在 WAN 上分配的带宽限制，则只会将 (呼叫的会话阻止或) 重新路由到 PSTN。</span><span class="sxs-lookup"><span data-stu-id="37240-201">If a new voice or video session exceeds the bandwidth limits that you have allocated on a WAN, the session is either blocked or (for phone calls only) rerouted to the PSTN.</span></span>
    

