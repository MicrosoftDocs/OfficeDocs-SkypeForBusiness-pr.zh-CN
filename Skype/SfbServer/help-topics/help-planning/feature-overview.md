---
title: 功能概述 （规划工具）
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 4/6/2016
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.plan.FeatureOverview
- ms.lync.plan.FeatureOverview
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 44783b37-c87f-41f2-9de1-39176f1856ab
description: Skype for Business Server 2015 规划工具
ms.openlocfilehash: 8d35b9babe99b4899cda51804f40dd6e3302feeb
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="feature-overview-planning-tool"></a><span data-ttu-id="b8380-103">功能概述 （规划工具）</span><span class="sxs-lookup"><span data-stu-id="b8380-103">Feature Overview (Planning Tool)</span></span>
 
<span data-ttu-id="b8380-104">Skype for Business Server 2015 规划工具</span><span class="sxs-lookup"><span data-stu-id="b8380-104">Skype for Business Server 2015 Planning Tool</span></span>
  
<span data-ttu-id="b8380-105">可以使用规划工具的**中央网站**页面设计业务服务器部署 Skype。</span><span class="sxs-lookup"><span data-stu-id="b8380-105">You can use the **Central Sites** page of the Planning Tool to design the Skype for Business Server deployment.</span></span> <span data-ttu-id="b8380-106">可以创建两个集中或分布式部署。</span><span class="sxs-lookup"><span data-stu-id="b8380-106">You can create two either a centralized or distributed deployment.</span></span> <span data-ttu-id="b8380-107">集中的部署只有一个中心站点，对象为所有有关组织中的业务用户的 Skype。</span><span class="sxs-lookup"><span data-stu-id="b8380-107">A centralized deployment only has one central site, which homes all Skype for Business users in your organization.</span></span> <span data-ttu-id="b8380-108">分布式部署有多个中央站点。</span><span class="sxs-lookup"><span data-stu-id="b8380-108">A distributed deployment has more than one central site.</span></span> <span data-ttu-id="b8380-109">如果您为多个中心站点的业务服务器部署 Skype，然后将在规划工具中输入每个中心站点的用户数。</span><span class="sxs-lookup"><span data-stu-id="b8380-109">If you deploy Skype for Business Server at multiple central sites, then you will enter the number of users at each central site in the Planning Tool.</span></span>
  
<span data-ttu-id="b8380-110">为了完成中央站点的定义，您首先需要提供以下信息：</span><span class="sxs-lookup"><span data-stu-id="b8380-110">To complete the definition of the central site, you first need to provide the following information:</span></span>
  
- <span data-ttu-id="b8380-111">**站点名** 输入中央站点的名称。</span><span class="sxs-lookup"><span data-stu-id="b8380-111">**Site Name** Enter the name of the Central Site.</span></span>
    
- <span data-ttu-id="b8380-112">**用户数** 输入用户数，包括驻留在中央站点的分支站点用户。</span><span class="sxs-lookup"><span data-stu-id="b8380-112">**Number of Users** Enter the number of users, including users at branch sites who are homed into the central site.</span></span>
    
- <span data-ttu-id="b8380-113">**云托管用户**托管的用户数从输入到中心站点 Skype 的在线业务。</span><span class="sxs-lookup"><span data-stu-id="b8380-113">**Cloud Homed Users** Enter the number of users that are homed into the central site from Skype for Business Online.</span></span>
    
## <a name="ui-elements"></a><span data-ttu-id="b8380-114">UI 元素</span><span class="sxs-lookup"><span data-stu-id="b8380-114">UI Elements</span></span>

<span data-ttu-id="b8380-115">其余元素要么已经由你在“**入门**”向导中提供的问题答案填充，要么由规划工具自动填充（如果你跳过了该向导）。</span><span class="sxs-lookup"><span data-stu-id="b8380-115">The remaining elements have either been populated with the answers you provided to the questions presented in the **Get Started** wizard, or, if you skipped the wizard, automatically populated by the planning tool.</span></span>
  
### <a name="online-collaboration"></a><span data-ttu-id="b8380-116">联机协作</span><span class="sxs-lookup"><span data-stu-id="b8380-116">Online Collaboration</span></span>

 <span data-ttu-id="b8380-117">“**联机协作**”包含以下选项：</span><span class="sxs-lookup"><span data-stu-id="b8380-117">**Online Collaboration** contains the following options:</span></span>
  
- <span data-ttu-id="b8380-118">**IM 和状态**</span><span class="sxs-lookup"><span data-stu-id="b8380-118">**IM and Presence**</span></span>
    
    <span data-ttu-id="b8380-119">即时消息 (IM) 使用户能够使用基于文本的消息在其计算机上实时相互通信。</span><span class="sxs-lookup"><span data-stu-id="b8380-119">Instant Messaging (IM) enables users to communicate with each other in real time on their computers using text-based messages.</span></span> <span data-ttu-id="b8380-120">支持两方和多方 IM 会话。</span><span class="sxs-lookup"><span data-stu-id="b8380-120">Both two-party and multiparty IM sessions are supported.</span></span> <span data-ttu-id="b8380-121">状态向用户提供网络上其他人的状态信息。</span><span class="sxs-lookup"><span data-stu-id="b8380-121">Presence provides information to users about the status of others on the network.</span></span> <span data-ttu-id="b8380-122">用户的状态提供信息来帮助确定用户是否处于联机状态，以及如何最好地与用户联系的其他人。</span><span class="sxs-lookup"><span data-stu-id="b8380-122">A user's presence status provides information to help others determine whether the user is online and how to best contact the user.</span></span> <span data-ttu-id="b8380-123">例如，最好通过电子邮件与正在开会的用户联系。</span><span class="sxs-lookup"><span data-stu-id="b8380-123">For example, a user who is in a meeting is best contacted by email.</span></span>
    
- <span data-ttu-id="b8380-124">**音频和视频会议**</span><span class="sxs-lookup"><span data-stu-id="b8380-124">**Audio and Video Conferencing**</span></span>
    
    <span data-ttu-id="b8380-125">音频/视频 (A/V) 会议实现实时音频和视频会议。</span><span class="sxs-lookup"><span data-stu-id="b8380-125">Audio/Video (A/V) conferencing enables real-time audio and video conferences.</span></span>
    
- <span data-ttu-id="b8380-126">**电话拨入式会议**</span><span class="sxs-lookup"><span data-stu-id="b8380-126">**Dial-in Conferencing**</span></span>
    
    <span data-ttu-id="b8380-p103">拨入式会议使用户能够从 PSTN 上的电话加入 A/V 会议。拨入式会议需要您部署会议助理和会议公告服务应用程序。</span><span class="sxs-lookup"><span data-stu-id="b8380-p103">Dial-in conferencing enables users to join an A/V from a telephone on the PSTN. Dial-in conferencing requires that you deploy the Conferencing Attendant and Conferencing Announcement Service applications.</span></span>
    
- <span data-ttu-id="b8380-129">**Web 会议**</span><span class="sxs-lookup"><span data-stu-id="b8380-129">**Web Conferencing**</span></span>
    
    <span data-ttu-id="b8380-130">Web 会议使防火墙内部和外部的企业用户能够创建和加入在内部服务器上召开的实时会议。</span><span class="sxs-lookup"><span data-stu-id="b8380-130">Web conferencing enables enterprise users inside and outside of the firewall to create and join real-time conferences that are hosted on your internal servers.</span></span>
    
- <span data-ttu-id="b8380-131">**持久聊天**</span><span class="sxs-lookup"><span data-stu-id="b8380-131">**Persistent Chat**</span></span>
    
    <span data-ttu-id="b8380-p104">通过持久聊天，多个用户可以参与可在其中发布和访问有关特定主题的内容（包括文本、链接和文件）的对话。尽管在会话过程中用户可以实时通信，但每个会话的内容都是持久存在的，这意味着在会话结束后，内容仍然可用。</span><span class="sxs-lookup"><span data-stu-id="b8380-p104">Persistent Chat enables multiple users to participate in conversations in which they post and access content about specific topics, including text, links, and files. Although users can communicate in real time during a session, the content of each session is persistent, which means it continues to be available after a session ends.</span></span>
    
### <a name="users"></a><span data-ttu-id="b8380-134">用户</span><span class="sxs-lookup"><span data-stu-id="b8380-134">Users</span></span>

 <span data-ttu-id="b8380-135">“**用户**”包含以下选项：</span><span class="sxs-lookup"><span data-stu-id="b8380-135">**Users** contains the following options:</span></span>
  
- <span data-ttu-id="b8380-136">**内部组织**</span><span class="sxs-lookup"><span data-stu-id="b8380-136">**Internal organization**</span></span>
    
- <span data-ttu-id="b8380-137">**与其他组织的联盟**</span><span class="sxs-lookup"><span data-stu-id="b8380-137">**Federation with other organizations**</span></span>
    
- <span data-ttu-id="b8380-138">**与以前版本的联盟**</span><span class="sxs-lookup"><span data-stu-id="b8380-138">**Federation with previous versions**</span></span>
    
- <span data-ttu-id="b8380-p105">**与公共 IM 服务提供商的联盟** 允许组织中的用户与公共即时消息服务提供商（如 MSN、Yahoo! 和 AOL）建立通信。与公共即时消息网络建立联盟需要单独的许可证。</span><span class="sxs-lookup"><span data-stu-id="b8380-p105">**Federation with public IM services providers** Allows users in your organization to establish communication with public instant messaging service providers such as MSN, Yahoo!, and AOL. A separate license is required to establish federation with public instant messaging networks.</span></span>
    
- <span data-ttu-id="b8380-141">**与基于 XMPP 的服务提供商的联盟**</span><span class="sxs-lookup"><span data-stu-id="b8380-141">**Federation with XMPP-based service provider**</span></span>
    
    <span data-ttu-id="b8380-142">Skype 业务服务器 2015年的介绍 （在边缘服务器上部署） 的完全集成的 XMPP 代理和您前端服务器上部署的 XMPP 网关。</span><span class="sxs-lookup"><span data-stu-id="b8380-142">Skype for Business Server 2015 introduces a fully integrated XMPP proxy (deployed on the Edge Servers) and an XMPP gateway deployed on your Front End Servers.</span></span> <span data-ttu-id="b8380-143">添加和配置 XMPP 代理服务器可以部署并 XMPP 网关允许业务服务器 2015年用户您 Skype 要从基于 XMPP 的即时消息 (IM) 的伙伴和状态添加联系人。</span><span class="sxs-lookup"><span data-stu-id="b8380-143">You can deploy Adding and configuring the XMPP proxy and XMPP gateway will allow your Skype for Business Server 2015 users to add contacts from XMPP-based partners for instant messaging (IM) and presence.</span></span>
    
- <span data-ttu-id="b8380-144">**移动性**</span><span class="sxs-lookup"><span data-stu-id="b8380-144">**Mobility**</span></span>
    
    <span data-ttu-id="b8380-145">在部署 Skype 业务服务器 2015年移动服务时，用户可以使用支持的苹果 iOS、 Android、 Windows Phone 或诺基亚移动设备执行为发送和接收即时消息、 查看联系人，查看存在此类活动。</span><span class="sxs-lookup"><span data-stu-id="b8380-145">When you deploy the Skype for Business Server 2015 Mobility Service, users can use supported Apple iOS, Android, Windows Phone, or Nokia mobile devices to perform such activities as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span>
    
- <span data-ttu-id="b8380-146">**W15 Exchange 邮箱**</span><span class="sxs-lookup"><span data-stu-id="b8380-146">**W15 Exchange mailbox**</span></span>
    
    <span data-ttu-id="b8380-147">Skype 的业务服务器 2015年使您能够将语音邮件消息存储在 Exchange 统一消息 (UM);然后，这些语音邮件消息将显示为用户的收件箱中的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="b8380-147">Skype for Business Server 2015 enables you to have voicemail messages stored in Exchange Unified Messaging (UM); those voicemail messages will then appear as email messages in your users' Inboxes.</span></span>
    
### <a name="voice"></a><span data-ttu-id="b8380-148">语音</span><span class="sxs-lookup"><span data-stu-id="b8380-148">Voice</span></span>

 <span data-ttu-id="b8380-149">“**语音**”包含以下选项：</span><span class="sxs-lookup"><span data-stu-id="b8380-149">**Voice** contains the following options:</span></span>
  
- <span data-ttu-id="b8380-150">**企业语音**</span><span class="sxs-lookup"><span data-stu-id="b8380-150">**Enterprise Voice**</span></span>
    
    <span data-ttu-id="b8380-151">企业语音是 Microsft 的软件驱动的 VoIP 解决方案。</span><span class="sxs-lookup"><span data-stu-id="b8380-151">Enterprise voice is Microsft's software-powered VoIP solution.</span></span> <span data-ttu-id="b8380-152">企业语音使用户能够使用 Skype 业务要发出电话呼叫，从他们的计算机。</span><span class="sxs-lookup"><span data-stu-id="b8380-152">Enterprise voice enables users to use Skype for Business to place a phone call from their computer.</span></span>
    
- <span data-ttu-id="b8380-153">**Exchange 统一消息**</span><span class="sxs-lookup"><span data-stu-id="b8380-153">**Exchange Unified Messaging**</span></span>
    
    <span data-ttu-id="b8380-154">Exchange 统一消息 (UM) 结合语音邮件和电子邮件到一个消息基础结构。</span><span class="sxs-lookup"><span data-stu-id="b8380-154">Exchange Unified Messaging (UM) combines voice mail and email into a single messaging infrastructure.</span></span> <span data-ttu-id="b8380-155">商业服务器 2015年的 Skype 使用 UM Exchange 提供呼叫应答、 订阅者访问、 电话通知和自动助理服务。</span><span class="sxs-lookup"><span data-stu-id="b8380-155">Skype for Business Server 2015 uses Exchange UM to provide call answering, subscriber access, call notification, and auto attendant services.</span></span> <span data-ttu-id="b8380-156">如果您使用这些服务，您需要集成业务共享的 Active Directory 拓扑中的服务器的 Exchange UM 和 Skype。</span><span class="sxs-lookup"><span data-stu-id="b8380-156">If you use these services, you will need to integrate Exchange UM and Skype for Business Server in a shared Active Directory topology.</span></span>
    
### <a name="additional-deployment-options"></a><span data-ttu-id="b8380-157">其他部署选项</span><span class="sxs-lookup"><span data-stu-id="b8380-157">Additional Deployment Options</span></span>

 <span data-ttu-id="b8380-158">“**其他部署选项**”包含以下选项：</span><span class="sxs-lookup"><span data-stu-id="b8380-158">**Additional Deployment Options** contains the following options:</span></span>
  
- <span data-ttu-id="b8380-159">**高可用性**</span><span class="sxs-lookup"><span data-stu-id="b8380-159">**High Availability**</span></span>
    
    <span data-ttu-id="b8380-160">高可用性启用备用服务器以支持故障转移。</span><span class="sxs-lookup"><span data-stu-id="b8380-160">High availability enables standby servers for failover support.</span></span>
    
- <span data-ttu-id="b8380-161">**灾难恢复**</span><span class="sxs-lookup"><span data-stu-id="b8380-161">**Disaster Recovery**</span></span>
    
    <span data-ttu-id="b8380-162">灾难恢复措施将使您对前端池位于两个数据中心。</span><span class="sxs-lookup"><span data-stu-id="b8380-162">Disaster recovery measures enable you to pair Front End pools located in two datacenters.</span></span>
    
- <span data-ttu-id="b8380-163">**监控**</span><span class="sxs-lookup"><span data-stu-id="b8380-163">**Monitoring**</span></span>
    
    <span data-ttu-id="b8380-164">监控功能捕获与通信会话相关的呼叫详细记录。</span><span class="sxs-lookup"><span data-stu-id="b8380-164">Monitoring captures call detail records related to communication sessions.</span></span> <span data-ttu-id="b8380-165">它还从参与者终结点处的音频和视频会话收集指标。</span><span class="sxs-lookup"><span data-stu-id="b8380-165">It also collects metrics from audio and video sessions at the participant endpoints.</span></span> <span data-ttu-id="b8380-166">监视服务器提供使用情况统计信息、 趋势和介质质量统计。</span><span class="sxs-lookup"><span data-stu-id="b8380-166">Monitoring Server provides usage statistics, trends, and media quality statistics.</span></span>
    
- <span data-ttu-id="b8380-167">**存档**</span><span class="sxs-lookup"><span data-stu-id="b8380-167">**Archiving**</span></span>
    
    <span data-ttu-id="b8380-168">存档功能存储即时消息对话和会议。</span><span class="sxs-lookup"><span data-stu-id="b8380-168">Archiving stores instant messaging conversations and conferences.</span></span>
    
- <span data-ttu-id="b8380-169">**Exchange 存档集成**</span><span class="sxs-lookup"><span data-stu-id="b8380-169">**Exchange Archiving Integration**</span></span>
    
    <span data-ttu-id="b8380-170">如果您有用户驻留在 Exchange 2013 和其邮箱已放在原地保留，可以选择将 Skype 集成业务服务器 2015年存储与 Exchange 存储有关的选项。</span><span class="sxs-lookup"><span data-stu-id="b8380-170">If you have users who are homed on Exchange 2013 and their mailboxes have been put on In-Place Hold, you can select the option to integrate Skype for Business Server 2015 storage with Exchange storage.</span></span>
    
- <span data-ttu-id="b8380-171">**IPv4**</span><span class="sxs-lookup"><span data-stu-id="b8380-171">**IPv4**</span></span>
    
    <span data-ttu-id="b8380-p110">IPv4 地址是 32 位地址，允许计算机通过 Internet 进行通信。由于世界范围内设备数量的不断增加，可用的 IPv4 地址已经用完。因此，许多新设备开始使用 IPv6 地址。</span><span class="sxs-lookup"><span data-stu-id="b8380-p110">IPv4 addresses are 32-bit addresses that allow a computer to communicate over the Internet. Due to the increasing number of devices worldwide, the available IPv4 addresses have run out. Because of this, many new devices are moving to using IPv6 addresses.</span></span>
    
- <span data-ttu-id="b8380-174">**IPv6**</span><span class="sxs-lookup"><span data-stu-id="b8380-174">**IPv6**</span></span>
    
    <span data-ttu-id="b8380-p111">IPv6 地址执行与 IPv4 地址相同的功能（并另外增加了一些功能），只不过 IPv6 地址不是使用 32 位，而是使用 128 位。这不仅可以提供一组新地址，而且地址数量也大大增加。</span><span class="sxs-lookup"><span data-stu-id="b8380-p111">IPv6 addresses perform the same function as IPv4 addresses (with some additional features), but instead of using only 32-bits, IPv6 addresses use 128-bits. This provides not only a new set of addresses, but also a much larger number of them.</span></span>
    
- <span data-ttu-id="b8380-177">**设备更新 Web 服务**</span><span class="sxs-lookup"><span data-stu-id="b8380-177">**Device Update Web service**</span></span>
    
    <span data-ttu-id="b8380-178">设备更新 Web 服务提供了自动化的方式来更新所有设备，如 Skype 业务为 Windows Phone，对于部署在您的组织之外。</span><span class="sxs-lookup"><span data-stu-id="b8380-178">The Device Update Web service provides an automated way to update all devices, such as Skype for Business for Windows Phone, that are deployed outside of your organization.</span></span>
    
### <a name="server-applications"></a><span data-ttu-id="b8380-179">服务器应用程序</span><span class="sxs-lookup"><span data-stu-id="b8380-179">Server Applications</span></span>

 <span data-ttu-id="b8380-180">“**服务器应用程序**”包含以下选项：</span><span class="sxs-lookup"><span data-stu-id="b8380-180">**Server Applications** contains the following options:</span></span>
  
- <span data-ttu-id="b8380-181">**响应组**</span><span class="sxs-lookup"><span data-stu-id="b8380-181">**Response Group**</span></span>
    
    <span data-ttu-id="b8380-182">响应组应用程序自动回答和分布对可用的帮助台代理调用。</span><span class="sxs-lookup"><span data-stu-id="b8380-182">The Response Group application automatically answers and distributes calls to an available helpdesk agent.</span></span>
    
- <span data-ttu-id="b8380-183">**公告**</span><span class="sxs-lookup"><span data-stu-id="b8380-183">**Announcement**</span></span>
    
    <span data-ttu-id="b8380-184">如果您计划同时部署企业语音，可能希望能够配置电话拨叫的号码是否有效，但不是分配给用户的公共区域的处理方式。</span><span class="sxs-lookup"><span data-stu-id="b8380-184">If you plan to deploy Enterprise Voice, you might want to be able to configure how phone calls are handled if the dialed number is valid but not assigned to a user common area.</span></span> <span data-ttu-id="b8380-185">这样，这些调用将转移到预先确定的目标 （电话号码或 SIP URI） 或播放和 / 或音频通知，管理员可以配置发布服务。</span><span class="sxs-lookup"><span data-stu-id="b8380-185">Administrators can configure Announcement Service so that these calls transfer to a predetermined destination (phone number or SIP URI) or play an audio announcement or both.</span></span> <span data-ttu-id="b8380-186">使用发布服务可以避免这种情况在其中调用 misdials，听到占线音或 SIP 客户端收到一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="b8380-186">Using Announcement Service avoids the situation in which a caller misdials and hears a busy tone or the SIP client receives an error message.</span></span> <span data-ttu-id="b8380-187">发布服务功能是一个典型的 PBX 功能。</span><span class="sxs-lookup"><span data-stu-id="b8380-187">Announcement Service functionality is a typical PBX feature.</span></span> 
    
- <span data-ttu-id="b8380-188">**呼叫寄存**</span><span class="sxs-lookup"><span data-stu-id="b8380-188">**Call Park**</span></span>
    
    <span data-ttu-id="b8380-189">调用公园应用程序启用企业语音用户呼叫置于保持从一个电话、 并再从另一部电话接收呼叫，而不必占用资源上接收到呼叫电话。</span><span class="sxs-lookup"><span data-stu-id="b8380-189">Call Park application enables an Enterprise Voice user to put a call on hold from one telephone, and then receive the call from another telephone without tying up resources on the phone that received the call.</span></span> <span data-ttu-id="b8380-190">当用户需要转接呼叫，但特定收件人未知时，调用公园应用程序非常有用。</span><span class="sxs-lookup"><span data-stu-id="b8380-190">Call Park application is useful when a user needs to transfer a call, but the specific recipient is unknown.</span></span> 
    
- <span data-ttu-id="b8380-191">**会议助理**</span><span class="sxs-lookup"><span data-stu-id="b8380-191">**Conference Attendant**</span></span>
    
    <span data-ttu-id="b8380-192">会议助理应用程序而无需第三方音频会议提供商的服务电话用户提供音频会议功能。</span><span class="sxs-lookup"><span data-stu-id="b8380-192">Conferencing Attendant application provides audio conferencing capabilities to phone users without the service of a third-party audio conferencing provider.</span></span>
    
- <span data-ttu-id="b8380-193">**会议公告**</span><span class="sxs-lookup"><span data-stu-id="b8380-193">**Conferencing Announcement**</span></span>
    
    <span data-ttu-id="b8380-194">会议发布应用程序会生成用户输入或在静音或 unmuted 时向电话用户离开会议，以及通知时发出信号的声音。</span><span class="sxs-lookup"><span data-stu-id="b8380-194">Conferencing Announcement application produces tones that signal when users enter or leave a conference, as well as notifications to phone users when they are muted or unmuted.</span></span>
    
- <span data-ttu-id="b8380-195">**呼叫允许控制**</span><span class="sxs-lookup"><span data-stu-id="b8380-195">**Call Admission Control**</span></span>
    
    <span data-ttu-id="b8380-196">呼叫允许控制 (CAC) 也称为 WAN 带宽管理，它根据可用带宽确定是否允许建立新的实时通信会话，以帮助防止拥塞网络上出现较差的用户体验质量。</span><span class="sxs-lookup"><span data-stu-id="b8380-196">Call Admission Control (CAC), also known as WAN bandwidth management, helps to prevent poor quality of experience for users on congested networks by determining, based on available bandwidth, whether to allow and new real-time communications sessions to be established.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="b8380-197">CAC 只控制实时流量，不影响数据流量。</span><span class="sxs-lookup"><span data-stu-id="b8380-197">CAC only controls real-time traffic and does not affect data traffic.</span></span> 
  
    <span data-ttu-id="b8380-198">如果新的语音或视频会话超出您在 WAN 上分配的带宽限制，会话将会被阻止（仅限电话呼叫）或重新路由到 PSTN。</span><span class="sxs-lookup"><span data-stu-id="b8380-198">If a new voice or video session exceeds the bandwidth limits that you have allocated on a WAN, the session is either blocked or (for phone calls only) rerouted to the PSTN.</span></span>
    

