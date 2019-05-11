---
title: Feature Overview (Planning Tool)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: e239730acbe41c1a08c9876c013670d7a69e5019
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33887270"
---
# <a name="feature-overview-planning-tool"></a><span data-ttu-id="bcdef-103">Feature Overview (Planning Tool)</span><span class="sxs-lookup"><span data-stu-id="bcdef-103">Feature Overview (Planning Tool)</span></span>
 
<span data-ttu-id="bcdef-104">Skype for Business Server 2015 规划工具</span><span class="sxs-lookup"><span data-stu-id="bcdef-104">Skype for Business Server 2015 Planning Tool</span></span>
  
<span data-ttu-id="bcdef-105">您可以使用**中央站点**页上的规划工具设计业务服务器部署 Skype。</span><span class="sxs-lookup"><span data-stu-id="bcdef-105">You can use the **Central Sites** page of the Planning Tool to design the Skype for Business Server deployment.</span></span> <span data-ttu-id="bcdef-106">可以创建两个集中或分布式部署。</span><span class="sxs-lookup"><span data-stu-id="bcdef-106">You can create two either a centralized or distributed deployment.</span></span> <span data-ttu-id="bcdef-107">集中的部署只有一个中央站点，哪些用户的组织中的业务用户的所有 Skype 的都这些。</span><span class="sxs-lookup"><span data-stu-id="bcdef-107">A centralized deployment only has one central site, which homes all Skype for Business users in your organization.</span></span> <span data-ttu-id="bcdef-108">分布式部署有多个中央站点。</span><span class="sxs-lookup"><span data-stu-id="bcdef-108">A distributed deployment has more than one central site.</span></span> <span data-ttu-id="bcdef-109">如果您的业务 Server 上的多个中央站点部署 Skype，然后将规划工具中输入每个中央站点的用户的数。</span><span class="sxs-lookup"><span data-stu-id="bcdef-109">If you deploy Skype for Business Server at multiple central sites, then you will enter the number of users at each central site in the Planning Tool.</span></span>
  
<span data-ttu-id="bcdef-110">为了完成中央站点的定义，您首先需要提供以下信息：</span><span class="sxs-lookup"><span data-stu-id="bcdef-110">To complete the definition of the central site, you first need to provide the following information:</span></span>
  
- <span data-ttu-id="bcdef-111">**站点名** 输入中央站点的名称。</span><span class="sxs-lookup"><span data-stu-id="bcdef-111">**Site Name** Enter the name of the Central Site.</span></span>
    
- <span data-ttu-id="bcdef-112">**用户数** 输入用户数，包括驻留在中央站点的分支站点用户。</span><span class="sxs-lookup"><span data-stu-id="bcdef-112">**Number of Users** Enter the number of users, including users at branch sites who are homed into the central site.</span></span>
    
- <span data-ttu-id="bcdef-113">**云托管用户**输入驻留的用户数到管理中心网站从 Skype 业务联机。</span><span class="sxs-lookup"><span data-stu-id="bcdef-113">**Cloud Homed Users** Enter the number of users that are homed into the central site from Skype for Business Online.</span></span>
    
## <a name="ui-elements"></a><span data-ttu-id="bcdef-114">UI 元素</span><span class="sxs-lookup"><span data-stu-id="bcdef-114">UI Elements</span></span>

<span data-ttu-id="bcdef-115">其余元素要么已经由你在“**入门**”向导中提供的问题答案填充，要么由规划工具自动填充（如果你跳过了该向导）。</span><span class="sxs-lookup"><span data-stu-id="bcdef-115">The remaining elements have either been populated with the answers you provided to the questions presented in the **Get Started** wizard, or, if you skipped the wizard, automatically populated by the planning tool.</span></span>
  
### <a name="online-collaboration"></a><span data-ttu-id="bcdef-116">联机协作</span><span class="sxs-lookup"><span data-stu-id="bcdef-116">Online Collaboration</span></span>

 <span data-ttu-id="bcdef-117">“**联机协作**”包含以下选项：</span><span class="sxs-lookup"><span data-stu-id="bcdef-117">**Online Collaboration** contains the following options:</span></span>
  
- <span data-ttu-id="bcdef-118">**IM 和状态**</span><span class="sxs-lookup"><span data-stu-id="bcdef-118">**IM and Presence**</span></span>
    
    <span data-ttu-id="bcdef-119">即时消息 (IM) 使用户能够使用基于文本的消息在其计算机上实时相互通信。</span><span class="sxs-lookup"><span data-stu-id="bcdef-119">Instant Messaging (IM) enables users to communicate with each other in real time on their computers using text-based messages.</span></span> <span data-ttu-id="bcdef-120">支持两方和多方 IM 会话。</span><span class="sxs-lookup"><span data-stu-id="bcdef-120">Both two-party and multiparty IM sessions are supported.</span></span> <span data-ttu-id="bcdef-121">状态向用户提供网络上其他人的状态信息。</span><span class="sxs-lookup"><span data-stu-id="bcdef-121">Presence provides information to users about the status of others on the network.</span></span> <span data-ttu-id="bcdef-122">用户的状态提供信息以帮助其他人确定用户是否联机以及如何以最佳联系该用户。</span><span class="sxs-lookup"><span data-stu-id="bcdef-122">A user's presence status provides information to help others determine whether the user is online and how to best contact the user.</span></span> <span data-ttu-id="bcdef-123">例如，最好通过电子邮件与正在开会的用户联系。</span><span class="sxs-lookup"><span data-stu-id="bcdef-123">For example, a user who is in a meeting is best contacted by email.</span></span>
    
- <span data-ttu-id="bcdef-124">**音频和视频会议**</span><span class="sxs-lookup"><span data-stu-id="bcdef-124">**Audio and Video Conferencing**</span></span>
    
    <span data-ttu-id="bcdef-125">音频/视频 (A/V) 会议实现实时音频和视频会议。</span><span class="sxs-lookup"><span data-stu-id="bcdef-125">Audio/Video (A/V) conferencing enables real-time audio and video conferences.</span></span>
    
- <span data-ttu-id="bcdef-126">**电话拨入式会议**</span><span class="sxs-lookup"><span data-stu-id="bcdef-126">**Dial-in Conferencing**</span></span>
    
    <span data-ttu-id="bcdef-p103">拨入式会议使用户能够从 PSTN 上的电话加入 A/V 会议。拨入式会议需要您部署会议助理和会议公告服务应用程序。</span><span class="sxs-lookup"><span data-stu-id="bcdef-p103">Dial-in conferencing enables users to join an A/V from a telephone on the PSTN. Dial-in conferencing requires that you deploy the Conferencing Attendant and Conferencing Announcement Service applications.</span></span>
    
- <span data-ttu-id="bcdef-129">**Web 会议**</span><span class="sxs-lookup"><span data-stu-id="bcdef-129">**Web Conferencing**</span></span>
    
    <span data-ttu-id="bcdef-130">Web 会议使防火墙内部和外部的企业用户能够创建和加入在内部服务器上召开的实时会议。</span><span class="sxs-lookup"><span data-stu-id="bcdef-130">Web conferencing enables enterprise users inside and outside of the firewall to create and join real-time conferences that are hosted on your internal servers.</span></span>
    
- <span data-ttu-id="bcdef-131">**持久聊天**</span><span class="sxs-lookup"><span data-stu-id="bcdef-131">**Persistent Chat**</span></span>
    
    <span data-ttu-id="bcdef-p104">通过持久聊天，多个用户可以参与可在其中发布和访问有关特定主题的内容（包括文本、链接和文件）的对话。尽管在会话过程中用户可以实时通信，但每个会话的内容都是持久存在的，这意味着在会话结束后，内容仍然可用。</span><span class="sxs-lookup"><span data-stu-id="bcdef-p104">Persistent Chat enables multiple users to participate in conversations in which they post and access content about specific topics, including text, links, and files. Although users can communicate in real time during a session, the content of each session is persistent, which means it continues to be available after a session ends.</span></span>
    
### <a name="users"></a><span data-ttu-id="bcdef-134">用户</span><span class="sxs-lookup"><span data-stu-id="bcdef-134">Users</span></span>

 <span data-ttu-id="bcdef-135">“**用户**”包含以下选项：</span><span class="sxs-lookup"><span data-stu-id="bcdef-135">**Users** contains the following options:</span></span>
  
- <span data-ttu-id="bcdef-136">**内部组织**</span><span class="sxs-lookup"><span data-stu-id="bcdef-136">**Internal organization**</span></span>
    
- <span data-ttu-id="bcdef-137">**与其他组织的联盟**</span><span class="sxs-lookup"><span data-stu-id="bcdef-137">**Federation with other organizations**</span></span>
    
- <span data-ttu-id="bcdef-138">**与以前版本的联盟**</span><span class="sxs-lookup"><span data-stu-id="bcdef-138">**Federation with previous versions**</span></span>
    
- <span data-ttu-id="bcdef-p105">**与公共 IM 服务提供商的联盟** 允许组织中的用户与公共即时消息服务提供商（如 MSN、Yahoo! 和 AOL）建立通信。与公共即时消息网络建立联盟需要单独的许可证。</span><span class="sxs-lookup"><span data-stu-id="bcdef-p105">**Federation with public IM services providers** Allows users in your organization to establish communication with public instant messaging service providers such as MSN, Yahoo!, and AOL. A separate license is required to establish federation with public instant messaging networks.</span></span>
    
- <span data-ttu-id="bcdef-141">**与基于 XMPP 的服务提供商的联盟**</span><span class="sxs-lookup"><span data-stu-id="bcdef-141">**Federation with XMPP-based service provider**</span></span>
    
    <span data-ttu-id="bcdef-142">Skype 的业务服务器 2015年引入了 （部署边缘服务器上） 的完全集成的 XMPP 代理和 XMPP 网关部署在前端服务器上。</span><span class="sxs-lookup"><span data-stu-id="bcdef-142">Skype for Business Server 2015 introduces a fully integrated XMPP proxy (deployed on the Edge Servers) and an XMPP gateway deployed on your Front End Servers.</span></span> <span data-ttu-id="bcdef-143">您可以部署添加和配置 XMPP 代理和 XMPP 网关将允许您 Skype 业务服务器 2015年用户将联系人从基于 XMPP 的合作伙伴的即时消息 (IM) 和状态。</span><span class="sxs-lookup"><span data-stu-id="bcdef-143">You can deploy Adding and configuring the XMPP proxy and XMPP gateway will allow your Skype for Business Server 2015 users to add contacts from XMPP-based partners for instant messaging (IM) and presence.</span></span>
    
- <span data-ttu-id="bcdef-144">**移动性**</span><span class="sxs-lookup"><span data-stu-id="bcdef-144">**Mobility**</span></span>
    
    <span data-ttu-id="bcdef-145">在部署 Skype 的业务服务器 2015 Mobility Service 时，用户可以使用支持的 Apple iOS、 Android、 Windows Phone 或 Nokia 移动设备执行如下活动发送和接收即时消息、 查看联系人和查看状态中。</span><span class="sxs-lookup"><span data-stu-id="bcdef-145">When you deploy the Skype for Business Server 2015 Mobility Service, users can use supported Apple iOS, Android, Windows Phone, or Nokia mobile devices to perform such activities as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span>
    
- <span data-ttu-id="bcdef-146">**W15 Exchange 邮箱**</span><span class="sxs-lookup"><span data-stu-id="bcdef-146">**W15 Exchange mailbox**</span></span>
    
    <span data-ttu-id="bcdef-147">Skype 的业务服务器 2015年使您能够具有语音邮件消息存储在 Exchange 统一消息 (UM);然后，这些语音邮件消息将显示为用户的收件箱中的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="bcdef-147">Skype for Business Server 2015 enables you to have voicemail messages stored in Exchange Unified Messaging (UM); those voicemail messages will then appear as email messages in your users' Inboxes.</span></span>
    
### <a name="voice"></a><span data-ttu-id="bcdef-148">语音</span><span class="sxs-lookup"><span data-stu-id="bcdef-148">Voice</span></span>

 <span data-ttu-id="bcdef-149">“**语音**”包含以下选项：</span><span class="sxs-lookup"><span data-stu-id="bcdef-149">**Voice** contains the following options:</span></span>
  
- <span data-ttu-id="bcdef-150">**企业语音**</span><span class="sxs-lookup"><span data-stu-id="bcdef-150">**Enterprise Voice**</span></span>
    
    <span data-ttu-id="bcdef-151">企业语音是以的由软件驱动的 VoIP 解决方案。</span><span class="sxs-lookup"><span data-stu-id="bcdef-151">Enterprise voice is Microsft's software-powered VoIP solution.</span></span> <span data-ttu-id="bcdef-152">企业语音，用户可以使用 for Business 的 Skype 发起电话呼叫从其计算机。</span><span class="sxs-lookup"><span data-stu-id="bcdef-152">Enterprise voice enables users to use Skype for Business to place a phone call from their computer.</span></span>
    
- <span data-ttu-id="bcdef-153">**Exchange 统一消息**</span><span class="sxs-lookup"><span data-stu-id="bcdef-153">**Exchange Unified Messaging**</span></span>
    
    <span data-ttu-id="bcdef-154">Exchange 统一消息 (UM) 合并语音邮件和电子邮件到单个消息传递基础结构。</span><span class="sxs-lookup"><span data-stu-id="bcdef-154">Exchange Unified Messaging (UM) combines voice mail and email into a single messaging infrastructure.</span></span> <span data-ttu-id="bcdef-155">Skype 的业务服务器 2015年使用 Exchange UM 来提供呼叫应答、 订阅者访问、 呼叫通知和自动助理服务。</span><span class="sxs-lookup"><span data-stu-id="bcdef-155">Skype for Business Server 2015 uses Exchange UM to provide call answering, subscriber access, call notification, and auto attendant services.</span></span> <span data-ttu-id="bcdef-156">如果您使用这些服务，您需要将 Exchange UM 和 Skype 为共享的 Active Directory 拓扑中的业务 Server 相集成。</span><span class="sxs-lookup"><span data-stu-id="bcdef-156">If you use these services, you will need to integrate Exchange UM and Skype for Business Server in a shared Active Directory topology.</span></span>
    
### <a name="additional-deployment-options"></a><span data-ttu-id="bcdef-157">其他部署选项</span><span class="sxs-lookup"><span data-stu-id="bcdef-157">Additional Deployment Options</span></span>

 <span data-ttu-id="bcdef-158">“**其他部署选项**”包含以下选项：</span><span class="sxs-lookup"><span data-stu-id="bcdef-158">**Additional Deployment Options** contains the following options:</span></span>
  
- <span data-ttu-id="bcdef-159">**高可用性**</span><span class="sxs-lookup"><span data-stu-id="bcdef-159">**High Availability**</span></span>
    
    <span data-ttu-id="bcdef-160">高可用性启用备用服务器以支持故障转移。</span><span class="sxs-lookup"><span data-stu-id="bcdef-160">High availability enables standby servers for failover support.</span></span>
    
- <span data-ttu-id="bcdef-161">**灾难恢复**</span><span class="sxs-lookup"><span data-stu-id="bcdef-161">**Disaster Recovery**</span></span>
    
    <span data-ttu-id="bcdef-162">灾难恢复度量值将使您到对前端池在两个数据中心中的位置。</span><span class="sxs-lookup"><span data-stu-id="bcdef-162">Disaster recovery measures enable you to pair Front End pools located in two datacenters.</span></span>
    
- <span data-ttu-id="bcdef-163">**监视**</span><span class="sxs-lookup"><span data-stu-id="bcdef-163">**Monitoring**</span></span>
    
    <span data-ttu-id="bcdef-164">监控功能捕获与通信会话相关的呼叫详细记录。</span><span class="sxs-lookup"><span data-stu-id="bcdef-164">Monitoring captures call detail records related to communication sessions.</span></span> <span data-ttu-id="bcdef-165">它还从参与者终结点处的音频和视频会话收集指标。</span><span class="sxs-lookup"><span data-stu-id="bcdef-165">It also collects metrics from audio and video sessions at the participant endpoints.</span></span> <span data-ttu-id="bcdef-166">监控服务器提供了使用统计信息、 趋势和媒体质量统计信息。</span><span class="sxs-lookup"><span data-stu-id="bcdef-166">Monitoring Server provides usage statistics, trends, and media quality statistics.</span></span>
    
- <span data-ttu-id="bcdef-167">**存档**</span><span class="sxs-lookup"><span data-stu-id="bcdef-167">**Archiving**</span></span>
    
    <span data-ttu-id="bcdef-168">存档功能存储即时消息对话和会议。</span><span class="sxs-lookup"><span data-stu-id="bcdef-168">Archiving stores instant messaging conversations and conferences.</span></span>
    
- <span data-ttu-id="bcdef-169">**Exchange 存档集成**</span><span class="sxs-lookup"><span data-stu-id="bcdef-169">**Exchange Archiving Integration**</span></span>
    
    <span data-ttu-id="bcdef-170">如果您有用户驻留在 Exchange 2013 上和其邮箱已被置于就地保留，可以选择将 Skype 集成业务服务器 2015年存储与 Exchange 存储的选项。</span><span class="sxs-lookup"><span data-stu-id="bcdef-170">If you have users who are homed on Exchange 2013 and their mailboxes have been put on In-Place Hold, you can select the option to integrate Skype for Business Server 2015 storage with Exchange storage.</span></span>
    
- <span data-ttu-id="bcdef-171">**IPv4**</span><span class="sxs-lookup"><span data-stu-id="bcdef-171">**IPv4**</span></span>
    
    <span data-ttu-id="bcdef-p110">IPv4 地址是 32 位地址，允许计算机通过 Internet 进行通信。由于世界范围内设备数量的不断增加，可用的 IPv4 地址已经用完。因此，许多新设备开始使用 IPv6 地址。</span><span class="sxs-lookup"><span data-stu-id="bcdef-p110">IPv4 addresses are 32-bit addresses that allow a computer to communicate over the Internet. Due to the increasing number of devices worldwide, the available IPv4 addresses have run out. Because of this, many new devices are moving to using IPv6 addresses.</span></span>
    
- <span data-ttu-id="bcdef-174">**IPv6**</span><span class="sxs-lookup"><span data-stu-id="bcdef-174">**IPv6**</span></span>
    
    <span data-ttu-id="bcdef-p111">IPv6 地址执行与 IPv4 地址相同的功能（并另外增加了一些功能），只不过 IPv6 地址不是使用 32 位，而是使用 128 位。这不仅可以提供一组新地址，而且地址数量也大大增加。</span><span class="sxs-lookup"><span data-stu-id="bcdef-p111">IPv6 addresses perform the same function as IPv4 addresses (with some additional features), but instead of using only 32-bits, IPv6 addresses use 128-bits. This provides not only a new set of addresses, but also a much larger number of them.</span></span>
    
- <span data-ttu-id="bcdef-177">**设备更新 Web 服务**</span><span class="sxs-lookup"><span data-stu-id="bcdef-177">**Device Update Web service**</span></span>
    
    <span data-ttu-id="bcdef-178">设备更新 Web 服务提供用于更新的所有设备，如 Skype 的业务的 Windows Phone，组织外部部署自动的方法。</span><span class="sxs-lookup"><span data-stu-id="bcdef-178">The Device Update Web service provides an automated way to update all devices, such as Skype for Business for Windows Phone, that are deployed outside of your organization.</span></span>
    
### <a name="server-applications"></a><span data-ttu-id="bcdef-179">服务器应用程序</span><span class="sxs-lookup"><span data-stu-id="bcdef-179">Server Applications</span></span>

 <span data-ttu-id="bcdef-180">“**服务器应用程序**”包含以下选项：</span><span class="sxs-lookup"><span data-stu-id="bcdef-180">**Server Applications** contains the following options:</span></span>
  
- <span data-ttu-id="bcdef-181">**响应组**</span><span class="sxs-lookup"><span data-stu-id="bcdef-181">**Response Group**</span></span>
    
    <span data-ttu-id="bcdef-182">响应组应用程序自动回答和分发到可用的帮助台代理的呼叫。</span><span class="sxs-lookup"><span data-stu-id="bcdef-182">The Response Group application automatically answers and distributes calls to an available helpdesk agent.</span></span>
    
- <span data-ttu-id="bcdef-183">**公告**</span><span class="sxs-lookup"><span data-stu-id="bcdef-183">**Announcement**</span></span>
    
    <span data-ttu-id="bcdef-184">如果您计划部署企业语音，您可能希望能够配置已拨的号码是否有效，但不是分配给用户的公共区域电话的处理方式。</span><span class="sxs-lookup"><span data-stu-id="bcdef-184">If you plan to deploy Enterprise Voice, you might want to be able to configure how phone calls are handled if the dialed number is valid but not assigned to a user common area.</span></span> <span data-ttu-id="bcdef-185">管理员可以配置通知服务，以便这些呼叫转接到预定目标 （电话号码或 SIP URI） 或播放音频通知或两者。</span><span class="sxs-lookup"><span data-stu-id="bcdef-185">Administrators can configure Announcement Service so that these calls transfer to a predetermined destination (phone number or SIP URI) or play an audio announcement or both.</span></span> <span data-ttu-id="bcdef-186">使用通知服务可以避免在其中呼叫者拨错号并听到忙音或 SIP 客户端收到错误消息的情况。</span><span class="sxs-lookup"><span data-stu-id="bcdef-186">Using Announcement Service avoids the situation in which a caller misdials and hears a busy tone or the SIP client receives an error message.</span></span> <span data-ttu-id="bcdef-187">公告服务功能是一个典型的 PBX 功能。</span><span class="sxs-lookup"><span data-stu-id="bcdef-187">Announcement Service functionality is a typical PBX feature.</span></span> 
    
- <span data-ttu-id="bcdef-188">**呼叫寄存**</span><span class="sxs-lookup"><span data-stu-id="bcdef-188">**Call Park**</span></span>
    
    <span data-ttu-id="bcdef-189">呼叫寄存应用程序启用企业语音用户将呼叫置于保留从一个电话，然后从另一个电话接收呼叫，而不必占用接收呼叫的电话上的资源。</span><span class="sxs-lookup"><span data-stu-id="bcdef-189">Call Park application enables an Enterprise Voice user to put a call on hold from one telephone, and then receive the call from another telephone without tying up resources on the phone that received the call.</span></span> <span data-ttu-id="bcdef-190">用户需要转接呼叫，但特定收件人是未知时，呼叫寄存应用程序很有用。</span><span class="sxs-lookup"><span data-stu-id="bcdef-190">Call Park application is useful when a user needs to transfer a call, but the specific recipient is unknown.</span></span> 
    
- <span data-ttu-id="bcdef-191">**会议助理**</span><span class="sxs-lookup"><span data-stu-id="bcdef-191">**Conference Attendant**</span></span>
    
    <span data-ttu-id="bcdef-192">会议助理应用程序向如果不使用第三方音频会议提供商的服务的电话用户提供音频会议功能。</span><span class="sxs-lookup"><span data-stu-id="bcdef-192">Conferencing Attendant application provides audio conferencing capabilities to phone users without the service of a third-party audio conferencing provider.</span></span>
    
- <span data-ttu-id="bcdef-193">**会议公告**</span><span class="sxs-lookup"><span data-stu-id="bcdef-193">**Conferencing Announcement**</span></span>
    
    <span data-ttu-id="bcdef-194">会议通知应用程序会生成提示音，当用户进入或被静音或取消静音时向电话用户离开会议以及通知。</span><span class="sxs-lookup"><span data-stu-id="bcdef-194">Conferencing Announcement application produces tones that signal when users enter or leave a conference, as well as notifications to phone users when they are muted or unmuted.</span></span>
    
- <span data-ttu-id="bcdef-195">**呼叫允许控制**</span><span class="sxs-lookup"><span data-stu-id="bcdef-195">**Call Admission Control**</span></span>
    
    <span data-ttu-id="bcdef-196">呼叫允许控制 (CAC) 也称为 WAN 带宽管理，它根据可用带宽确定是否允许建立新的实时通信会话，以帮助防止拥塞网络上出现较差的用户体验质量。</span><span class="sxs-lookup"><span data-stu-id="bcdef-196">Call Admission Control (CAC), also known as WAN bandwidth management, helps to prevent poor quality of experience for users on congested networks by determining, based on available bandwidth, whether to allow and new real-time communications sessions to be established.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="bcdef-197">CAC 只控制实时流量，不影响数据流量。</span><span class="sxs-lookup"><span data-stu-id="bcdef-197">CAC only controls real-time traffic and does not affect data traffic.</span></span> 
  
    <span data-ttu-id="bcdef-198">如果新的语音或视频会话超出您在 WAN 上分配的带宽限制，会话将会被阻止（仅限电话呼叫）或重新路由到 PSTN。</span><span class="sxs-lookup"><span data-stu-id="bcdef-198">If a new voice or video session exceeds the bandwidth limits that you have allocated on a WAN, the session is either blocked or (for phone calls only) rerouted to the PSTN.</span></span>
    

