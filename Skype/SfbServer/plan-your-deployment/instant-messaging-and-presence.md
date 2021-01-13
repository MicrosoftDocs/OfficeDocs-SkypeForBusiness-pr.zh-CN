---
title: 在 Skype for Business Server 中规划即时消息和状态
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 70d2151e-9382-485d-ab14-758597571a74
description: 摘要：了解如何在 Skype for Business Server 中规划即时消息和状态。
ms.openlocfilehash: a29d68cc66e0ac4a70fc759283646fc3ce49cdf5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816272"
---
# <a name="plan-for-instant-messaging-and-presence-in-skype-for-business-server"></a><span data-ttu-id="cf916-103">在 Skype for Business Server 中规划即时消息和状态</span><span class="sxs-lookup"><span data-stu-id="cf916-103">Plan for instant messaging and presence in Skype for Business Server</span></span>
 
<span data-ttu-id="cf916-104">**摘要：** 了解如何在 Skype for Business Server 中规划即时消息和状态。</span><span class="sxs-lookup"><span data-stu-id="cf916-104">**Summary:** Learn how to plan for instant messaging and presence in Skype for Business Server.</span></span>
  
<span data-ttu-id="cf916-105">在 Skype for Business Server 中规划即时消息和状态。</span><span class="sxs-lookup"><span data-stu-id="cf916-105">Plan for instant messaging and presence in Skype for Business Server.</span></span> <span data-ttu-id="cf916-106">若要了解特定的部署选项，例如启用或禁用脱机即时消息 (IM) ，请参阅在 Skype for Business [Server](../deploy/im-and-presence/im-and-presence.md)中部署即时消息和状态。</span><span class="sxs-lookup"><span data-stu-id="cf916-106">To learn about specific deployment options, such as enabling or disabling Offline Instant Messaging (IM), see [Deploy instant messaging and presence in Skype for Business Server](../deploy/im-and-presence/im-and-presence.md).</span></span>
  
## <a name="plan-for-instant-messaging-and-presence-in-skype-for-business-server"></a><span data-ttu-id="cf916-107">在 Skype for Business Server 中规划即时消息和状态</span><span class="sxs-lookup"><span data-stu-id="cf916-107">Plan for instant messaging and presence in Skype for Business Server</span></span>

<span data-ttu-id="cf916-108">前端服务器提供核心 Skype for Business Server 功能，如即时消息 (IM) 和状态，并包含在每个 Skype for Business Server 部署中。</span><span class="sxs-lookup"><span data-stu-id="cf916-108">Front End Servers provide core Skype for Business Server functionality such as instant messaging (IM) and presence and are included in every Skype for Business Server deployment.</span></span> <span data-ttu-id="cf916-109">有两个版本可用：Skype for Business Server Enterprise Edition（主要面向大型组织设计）和 Skype for Business Server Standard Edition（主要针对需要较小硬件投资且不需要完整高可用性选项的较小组织设计）。</span><span class="sxs-lookup"><span data-stu-id="cf916-109">There are two editions available: Skype for Business Server Enterprise Edition, which is designed primarily for larger organizations, and Skype for Business Server Standard Edition, which is designed primarily for smaller organizations which want a smaller hardware investment and do not require full high availability options.</span></span> <span data-ttu-id="cf916-110">这两个版本都支持所有 Skype for Business Server 工作负载，包括 IM、状态、会议和企业语音。</span><span class="sxs-lookup"><span data-stu-id="cf916-110">Both editions support all Skype for Business Server workloads including IM, presence, conferencing, and Enterprise Voice.</span></span>
  
<span data-ttu-id="cf916-p103">通过即时消息 (IM)，用户可以在其计算机上使用基于文本的消息进行实时通信。支持双方和多方之间的 IM 会话。双方 IM 对话中的一方可以随时将第三方参与者加入对话中。发生这种情况时，对话窗口会做出相应改变以支持会议功能。</span><span class="sxs-lookup"><span data-stu-id="cf916-p103">Instant messaging (IM) enables your users to communicate with each other in real time on their computers using text-based messages. Both two-party and multiparty IM sessions are supported. A participant in a two-party IM conversation can add a third participant to the conversation at any time. When this happens, the Conversation window changes to support conferencing features.</span></span>
  
<span data-ttu-id="cf916-115">状态会向用户提供有关网络上其他人的状态的信息。</span><span class="sxs-lookup"><span data-stu-id="cf916-115">Presence provides information to users about the status of others on the network.</span></span> <span data-ttu-id="cf916-116">用户的状态信息可帮助其他人决定是否应尝试与用户联系以及是使用即时消息、电话还是电子邮件。</span><span class="sxs-lookup"><span data-stu-id="cf916-116">A user's presence status provides information to help others decide whether they should try to contact the user and whether to use instant messaging, phone, or email.</span></span> <span data-ttu-id="cf916-117">只要有可能，状态就会敦促进行即时通信；但状态也提供关于用户是否在开会或外出的信息，表明这种情况下不能进行即时通信。</span><span class="sxs-lookup"><span data-stu-id="cf916-117">Presence encourages instant communication when possible, but it also provides information about whether a user is in a meeting or out of the office, indicating that instant communication is not possible.</span></span> <span data-ttu-id="cf916-118">此状态在 Skype for Business 和其他状态感知应用程序中显示为状态图标，包括 Microsoft Outlook 消息和协作客户端、Microsoft SharePoint 技术和 Microsoft Office。</span><span class="sxs-lookup"><span data-stu-id="cf916-118">This presence status is displayed as a presence icon in Skype for Business and other presence-aware applications, including the Microsoft Outlook messaging and collaboration client, Microsoft SharePoint technologies, and Microsoft Office.</span></span> <span data-ttu-id="cf916-119">状态图标表示用户的当前可用性和通信愿意。</span><span class="sxs-lookup"><span data-stu-id="cf916-119">The presence icon represents the user's current availability and willingness to communicate.</span></span> 
  
### <a name="technical-requirements"></a><span data-ttu-id="cf916-120">技术要求</span><span class="sxs-lookup"><span data-stu-id="cf916-120">Technical requirements</span></span>

<span data-ttu-id="cf916-121">即时消息 (IM) 和状态始终在 Enterprise Edition 前端池和 Standard Edition 服务器上运行。</span><span class="sxs-lookup"><span data-stu-id="cf916-121">Instant messaging (IM) and presence always run on Enterprise Edition Front End pools and Standard Edition servers.</span></span> <span data-ttu-id="cf916-122">有关支持的硬件、操作系统和数据库软件的信息，请参阅认证网关[、Skype for Business 2015](requirements-for-your-environment/requirements-for-your-environment.md)环境的要求和 Skype [for Business Server 2019](../../SfBServer2019/plan/system-requirements.md)的基础结构要求。 [](../../SfbPartnerCertification/certification/infra-gateways.md)</span><span class="sxs-lookup"><span data-stu-id="cf916-122">For information on supported hardware, operating systems, and database software, see  [Certified Gateways](../../SfbPartnerCertification/certification/infra-gateways.md),  [Requirements for your Skype for Business 2015 environment](requirements-for-your-environment/requirements-for-your-environment.md), and [Infrastructure requirements for Skype for Business Server 2019](../../SfBServer2019/plan/system-requirements.md).</span></span>
  
### <a name="enabling-communication-with-external-users"></a><span data-ttu-id="cf916-123">启用与外部用户的通信</span><span class="sxs-lookup"><span data-stu-id="cf916-123">Enabling communication with external users</span></span>

<span data-ttu-id="cf916-124">通过允许用户与外部用户进行通信，可以大大增加 Skype for Business Server 投资收益。</span><span class="sxs-lookup"><span data-stu-id="cf916-124">You can greatly increase the benefits of your investment in Skype for Business Server by enabling your users to communicate with external users.</span></span> <span data-ttu-id="cf916-125">外部用户可能包括：</span><span class="sxs-lookup"><span data-stu-id="cf916-125">External users can include:</span></span>
  
- <span data-ttu-id="cf916-126">远程用户：组织自己的用户，当他们在防火墙外工作并且正在使用其便携式计算机或其他 Skype for Business Server 设备时。</span><span class="sxs-lookup"><span data-stu-id="cf916-126">Remote users: Your organization's own users, when they are working outside your firewalls and are using their laptops or other Skype for Business Server devices.</span></span>
    
- <span data-ttu-id="cf916-127">联盟用户：来自合作公司同时也运行 Skype for Business Server 的用户。</span><span class="sxs-lookup"><span data-stu-id="cf916-127">Federated users: Users from companies you work with who also run Skype for Business Server.</span></span> <span data-ttu-id="cf916-128">若要使用户轻松与这些用户联系，请与这些公司建立联盟关系。</span><span class="sxs-lookup"><span data-stu-id="cf916-128">To enable your users to easily contact these users, you create federated relationships with these companies.</span></span> 
    
- <span data-ttu-id="cf916-129">Skype 用户：Skype for Business 用户可以使用 IM、语音和视频访问 Skype 上的数亿用户。</span><span class="sxs-lookup"><span data-stu-id="cf916-129">Skype users: Skype for Business users can reach the hundreds of millions of users on Skype with IM, voice and video.</span></span>
    
> [!NOTE]
> <span data-ttu-id="cf916-130">不再支持 AOL、Yahoo 和 Google Talk。</span><span class="sxs-lookup"><span data-stu-id="cf916-130">AOL, Yahoo, and Google Talk are no longer supported.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="cf916-131">若要启用任意或所有这些方案，需要部署边缘服务器以帮助启用 Skype for Business Server 部署和外部用户之间的安全通信。</span><span class="sxs-lookup"><span data-stu-id="cf916-131">To enable any or all of these scenarios, you need to deploy an Edge Server to help enable secure communications between your Skype for Business Server deployment and external users.</span></span> <span data-ttu-id="cf916-132">贵组织的远程用户和联盟组织的用户将能够查看彼此的存在，并能够使用 IM 进行通信。</span><span class="sxs-lookup"><span data-stu-id="cf916-132">Your organization's remote users and users at federated organizations will be able to see each other's presence and communicate using IM.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="cf916-133">只有统一功能协作平台 (UCCP) 联合互操作性测试命令 (JITC) ) 认证方案才支持可扩展消息传递和状态协议 (XMPP) 。</span><span class="sxs-lookup"><span data-stu-id="cf916-133">Extensible Messaging and Presence Protocol (XMPP) is only supported for Unified Capabilities Collaboration Platform (UCCP) Joint Interoperability Test Command (JITC) certification scenarios.</span></span> 
  
### <a name="archiving-im-content"></a><span data-ttu-id="cf916-134">存档 IM 内容</span><span class="sxs-lookup"><span data-stu-id="cf916-134">Archiving IM content</span></span>

<span data-ttu-id="cf916-135">如果你的组织必须遵守合规性法规，Skype for Business Server 将提供可以使用的功能。</span><span class="sxs-lookup"><span data-stu-id="cf916-135">Skype for Business Server provides features you can use if your organization must follow compliance regulations.</span></span> <span data-ttu-id="cf916-136">可以使用存档来存档组织中所有用户或仅针对您指定的特定用户的 IM 消息内容。</span><span class="sxs-lookup"><span data-stu-id="cf916-136">You can use Archiving to archive the content of IM messages for all users in your organization or for only certain users that you specify.</span></span> <span data-ttu-id="cf916-137">有关详细信息，请参阅 [规划 Skype for Business Server 中的存档](archiving/archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="cf916-137">For details, see [Plan for archiving in Skype for Business Server](archiving/archiving.md).</span></span> 
  
<span data-ttu-id="cf916-138">如果还部署了 Microsoft Exchange Server 2013，可以将 Exchange 数据的存档与 Skype for Business Server 数据的存档集成，并使用单个工具来搜索这两种类型的存档数据。</span><span class="sxs-lookup"><span data-stu-id="cf916-138">If you also have Microsoft Exchange Server 2013 deployed, you can integrate the archiving of Exchange data with the archiving of Skype for Business Server data, and use a single tool to search both types of archived data.</span></span> <span data-ttu-id="cf916-139">有关详细信息，请参阅配置 [Skype for Business Server 以使用Exchange Server存档](../deploy/integrate-with-exchange-server/use-exchange-archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="cf916-139">For more information, see [Configure Skype for Business Server to use Exchange Server archiving](../deploy/integrate-with-exchange-server/use-exchange-archiving.md).</span></span>
  
### <a name="topologies-and-components"></a><span data-ttu-id="cf916-140">拓扑和组件</span><span class="sxs-lookup"><span data-stu-id="cf916-140">Topologies and components</span></span>

<span data-ttu-id="cf916-141">即时消息 (IM) 和状态所需的唯一组件是：</span><span class="sxs-lookup"><span data-stu-id="cf916-141">The only components required for instant messaging (IM) and presence are:</span></span>
  
- <span data-ttu-id="cf916-142">组织的前端服务器称为 (池) Standard Edition Server。</span><span class="sxs-lookup"><span data-stu-id="cf916-142">Your organization's Front End servers (known as a pool) or a Standard Edition server.</span></span> <span data-ttu-id="cf916-143">这些服务器中始终启用 IM 和状态功能。</span><span class="sxs-lookup"><span data-stu-id="cf916-143">IM and presence capabilities are always enabled on these servers.</span></span> <span data-ttu-id="cf916-144">有关前端池拓扑和管理的信息，请参阅 [前端池的高可用性和管理](high-availability-and-disaster-recovery/high-availability.md)。</span><span class="sxs-lookup"><span data-stu-id="cf916-144">For more information on Front End pool topologies and management, see [Front End Pool high availability and management](high-availability-and-disaster-recovery/high-availability.md).</span></span>
    
- <span data-ttu-id="cf916-145">负载平衡器（如果有 Enterprise Edition 前端池）。</span><span class="sxs-lookup"><span data-stu-id="cf916-145">A load balancer, if you have an Enterprise Edition Front End pool.</span></span>
    
### <a name="supported-collocation"></a><span data-ttu-id="cf916-146">支持的并置</span><span class="sxs-lookup"><span data-stu-id="cf916-146">Supported collocation</span></span>

<span data-ttu-id="cf916-147">并置定义为具有一台服务器或一组安装了多个角色的服务器。</span><span class="sxs-lookup"><span data-stu-id="cf916-147">Collocation is defined as having a single server, or group of servers, with multiple roles installed.</span></span> <span data-ttu-id="cf916-148">有关并置的详细信息，请参阅[Topology Basics for Skype for Business Server。](topology-basics/topology-basics.md)</span><span class="sxs-lookup"><span data-stu-id="cf916-148">For details on collocation, see [Topology Basics for Skype for Business Server](topology-basics/topology-basics.md).</span></span> 
  

