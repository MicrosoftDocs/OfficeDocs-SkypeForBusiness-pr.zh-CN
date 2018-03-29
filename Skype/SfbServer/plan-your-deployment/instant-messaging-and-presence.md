---
title: 规划 Skype for Business Server 2015 中的即时消息和状态
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 6/28/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 70d2151e-9382-485d-ab14-758597571a74
description: 摘要： 了解如何规划业务服务器 2015年的即时消息和 Skype 在状态。
ms.openlocfilehash: 1934f0308cda59b52073c47d1652ad2286bd6977
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-instant-messaging-and-presence-in-skype-for-business-server-2015"></a><span data-ttu-id="0e554-103">规划 Skype for Business Server 2015 中的即时消息和状态</span><span class="sxs-lookup"><span data-stu-id="0e554-103">Plan for instant messaging and presence in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="0e554-104">**摘要：**了解如何规划 Skype for Business Server 2015 中的即时消息和状态。</span><span class="sxs-lookup"><span data-stu-id="0e554-104">**Summary:** Learn how to plan for instant messaging and presence in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="0e554-105">规划 Skype for Business Server 2015 中的即时消息和状态。</span><span class="sxs-lookup"><span data-stu-id="0e554-105">Plan for instant messaging and presence in Skype for Business Server 2015.</span></span> <span data-ttu-id="0e554-106">若要了解有关特定的部署选项，例如启用或禁用脱机即时消息 (IM)，请参阅[部署即时消息和 Skype 的业务服务器 2015年遍布](../deploy/im-and-presence/im-and-presence.md)。</span><span class="sxs-lookup"><span data-stu-id="0e554-106">To learn about specific deployment options, such as enabling or disabling Offline Instant Messaging (IM), see [Deploy instant messaging and presence in Skype for Business Server 2015](../deploy/im-and-presence/im-and-presence.md).</span></span>
  
## <a name="plan-for-instant-messaging-and-presence-in-skype-for-business-server-2015"></a><span data-ttu-id="0e554-107">规划 Skype for Business Server 2015 中的即时消息和状态</span><span class="sxs-lookup"><span data-stu-id="0e554-107">Plan for instant messaging and presence in Skype for Business Server 2015</span></span>

<span data-ttu-id="0e554-108">前端服务器提供核心 Skype 的业务服务器功能，如即时消息 (IM) 和状态，包括在每一个 Skype 业务服务器部署。</span><span class="sxs-lookup"><span data-stu-id="0e554-108">Front End Servers provide core Skype for Business Server functionality such as instant messaging (IM) and presence and are included in every Skype for Business Server deployment.</span></span> <span data-ttu-id="0e554-109">有两种版本： Skype 业务服务器企业版，它主要用于较大的组织和 Skype 业务服务器标准版中，它主要用于较小的公司要小硬件的投资，而不需要完整的高可用性选项。</span><span class="sxs-lookup"><span data-stu-id="0e554-109">There are two editions available: Skype for Business Server Enterprise Edition, which is designed primarily for larger organizations, and Skype for Business Server Standard Edition, which is designed primarily for smaller organizations which want a smaller hardware investment and do not require full high availability options.</span></span> <span data-ttu-id="0e554-110">这两个版本支持所有 Skype 业务服务器工作负荷包括即时消息、 状态显示、 会议和企业语音。</span><span class="sxs-lookup"><span data-stu-id="0e554-110">Both editions support all Skype for Business Server workloads including IM, presence, conferencing, and Enterprise Voice.</span></span>
  
<span data-ttu-id="0e554-111">通过即时消息 (IM)，用户可以在其计算机上使用基于文本的消息进行实时通信。</span><span class="sxs-lookup"><span data-stu-id="0e554-111">Instant messaging (IM) enables your users to communicate with each other in real time on their computers using text-based messages.</span></span> <span data-ttu-id="0e554-112">支持双方和多方之间的 IM 会话。</span><span class="sxs-lookup"><span data-stu-id="0e554-112">Both two-party and multiparty IM sessions are supported.</span></span> <span data-ttu-id="0e554-113">双方 IM 对话中的一方可以随时将第三方参与者加入对话中。</span><span class="sxs-lookup"><span data-stu-id="0e554-113">A participant in a two-party IM conversation can add a third participant to the conversation at any time.</span></span> <span data-ttu-id="0e554-114">发生这种情况时，对话窗口会做出相应改变以支持会议功能。</span><span class="sxs-lookup"><span data-stu-id="0e554-114">When this happens, the Conversation window changes to support conferencing features.</span></span>
  
<span data-ttu-id="0e554-115">状态向用户提供网络中其他人的状态信息。</span><span class="sxs-lookup"><span data-stu-id="0e554-115">Presence provides information to users about the status of others on the network.</span></span> <span data-ttu-id="0e554-116">用户的状态提供信息以帮助其他人决定是否他们应该尝试联系用户，以及是否使用即时消息、 电话或电子邮件。</span><span class="sxs-lookup"><span data-stu-id="0e554-116">A user's presence status provides information to help others decide whether they should try to contact the user and whether to use instant messaging, phone, or email.</span></span> <span data-ttu-id="0e554-117">只要有可能，状态就会敦促进行即时通信；但状态也提供关于用户是否在开会或外出的信息，表明这种情况下不能进行即时通信。</span><span class="sxs-lookup"><span data-stu-id="0e554-117">Presence encourages instant communication when possible, but it also provides information about whether a user is in a meeting or out of the office, indicating that instant communication is not possible.</span></span> <span data-ttu-id="0e554-118">此状态在 Skype for Business 和其他可检测状态的应用程序（包括 Microsoft Outlook 消息和协作客户端、Microsoft SharePoint 技术和 Microsoft Office）中显示为状态图标。</span><span class="sxs-lookup"><span data-stu-id="0e554-118">This presence status is displayed as a presence icon in Skype for Business and other presence-aware applications, including the Microsoft Outlook messaging and collaboration client, Microsoft SharePoint technologies, and Microsoft Office.</span></span> <span data-ttu-id="0e554-119">状态图标表示该用户的当前可用性和意愿进行通信。</span><span class="sxs-lookup"><span data-stu-id="0e554-119">The presence icon represents the user's current availability and willingness to communicate.</span></span> 
  
### <a name="technical-requirements"></a><span data-ttu-id="0e554-120">技术要求</span><span class="sxs-lookup"><span data-stu-id="0e554-120">Technical requirements</span></span>

<span data-ttu-id="0e554-121">即时消息 (IM) 和状态始终在 Enterprise Edition 前端池和 Standard Edition 服务器上运行。</span><span class="sxs-lookup"><span data-stu-id="0e554-121">Instant messaging (IM) and presence always run on Enterprise Edition Front End pools and Standard Edition servers.</span></span> <span data-ttu-id="0e554-122">有关受支持的硬件、 操作系统和数据库软件的信息，请参阅[基础结构以实现业务的 Skype](https://technet.microsoft.com/en-us/office/dn947483)和[为您的业务环境的 Skype 的要求](requirements-for-your-environment/requirements-for-your-environment.md)。</span><span class="sxs-lookup"><span data-stu-id="0e554-122">For information on supported hardware, operating systems, and database software, see [Infrastructure for Skype for Business](https://technet.microsoft.com/en-us/office/dn947483) and [Requirements for your Skype for Business environment](requirements-for-your-environment/requirements-for-your-environment.md).</span></span>
  
### <a name="enabling-communication-with-external-users"></a><span data-ttu-id="0e554-123">启用与外部用户的通信</span><span class="sxs-lookup"><span data-stu-id="0e554-123">Enabling communication with external users</span></span>

<span data-ttu-id="0e554-p106">通过允许您的用户与外部用户进行通信，可大大增加在 Skype for Business Server 中投资的收益。外部用户可能包括：</span><span class="sxs-lookup"><span data-stu-id="0e554-p106">You can greatly increase the benefits of your investment in Skype for Business Server by enabling your users to communicate with external users. External users can include:</span></span>
  
- <span data-ttu-id="0e554-126">远程用户： 组织自己的用户，您的防火墙之外工作和业务服务器设备笔记本电脑或其他 Skype 使用时。</span><span class="sxs-lookup"><span data-stu-id="0e554-126">Remote users: Your organization's own users, when they are working outside your firewalls and are using their laptops or other Skype for Business Server devices.</span></span>
    
- <span data-ttu-id="0e554-127">联合用户： 在公司使用还为业务服务器运行 Skype 的用户。</span><span class="sxs-lookup"><span data-stu-id="0e554-127">Federated users: Users from companies you work with who also run Skype for Business Server.</span></span> <span data-ttu-id="0e554-128">要使用户轻松与这些用户联系，应与这些公司建立联盟关系。</span><span class="sxs-lookup"><span data-stu-id="0e554-128">To enable your users to easily contact these users, you create federated relationships with these companies.</span></span> 
    
- <span data-ttu-id="0e554-129">Skype 用户：Skype for Business 用户可使用 IM、语音和视频联系 Skype 上的数亿用户。</span><span class="sxs-lookup"><span data-stu-id="0e554-129">Skype users: Skype for Business users can reach the hundreds of millions of users on Skype with IM, voice and video.</span></span>
    
> [!NOTE]
> <span data-ttu-id="0e554-130">不再支持 AOL、Yahoo 和 Google Talk。</span><span class="sxs-lookup"><span data-stu-id="0e554-130">AOL, Yahoo, and Google Talk are no longer supported.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="0e554-131">要实现任意或所有这些方案，需要部署边缘服务器以帮助启用 Skype for Business Server 部署和外部用户之间的安全通信。</span><span class="sxs-lookup"><span data-stu-id="0e554-131">To enable any or all of these scenarios, you need to deploy an Edge Server to help enable secure communications between your Skype for Business Server deployment and external users.</span></span> <span data-ttu-id="0e554-132">您的组织的远程用户和联盟组织的用户将能够看到对方的状态并使用即时消息进行通信。</span><span class="sxs-lookup"><span data-stu-id="0e554-132">Your organization's remote users and users at federated organizations will be able to see each other's presence and communicate using IM.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="0e554-133">可扩展消息传递和状态协议 (XMPP) 仅支持统一功能协作平台 (UCCP) 联合互操作性测试命令 (JITC) 认证方案。</span><span class="sxs-lookup"><span data-stu-id="0e554-133">Extensible Messaging and Presence Protocol (XMPP) is only supported for Unified Capabilities Collaboration Platform (UCCP) Joint Interoperability Test Command (JITC) certification scenarios.</span></span> 
  
### <a name="archiving-im-content"></a><span data-ttu-id="0e554-134">存档 IM 内容</span><span class="sxs-lookup"><span data-stu-id="0e554-134">Archiving IM content</span></span>

<span data-ttu-id="0e554-p109">如果组织必须遵守合规性要求，Skype for Business Server 提供了您可以使用的功能。您可以使用存档功能为组织中的所有用户或仅为您指定的特定用户存档 IM 消息的内容。有关详细信息，请参阅规划文档中的“规划 Skype for Business Server 2015 中的存档”。</span><span class="sxs-lookup"><span data-stu-id="0e554-p109">Skype for Business Server provides features you can use if your organization must follow compliance regulations. You can use Archiving to archive the content of IM messages for all users in your organization or for only certain users that you specify. For details, see Planning for Archiving in Skype for Business Server 2015 in the Planning documentation.</span></span> 
  
<span data-ttu-id="0e554-138">如果您还部署了 Microsoft Exchange Server 2013，则可以将 Exchange 数据的存档与 Skype for Business Server 数据的存档进行集成，并使用一个工具同时搜索这两种类型的存档数据。</span><span class="sxs-lookup"><span data-stu-id="0e554-138">If you also have Microsoft Exchange Server 2013 deployed, you can integrate the archiving of Exchange data with the archiving of Skype for Business Server data, and use a single tool to search both types of archived data.</span></span> <span data-ttu-id="0e554-139">有关详细信息，请参阅配置为使用 Microsoft Exchange Server 2013年归档的业务服务器 2015年的 Skype。</span><span class="sxs-lookup"><span data-stu-id="0e554-139">For more information, see Configuring Skype for Business Server 2015 to use Microsoft Exchange Server 2013 archiving.</span></span>
  
### <a name="topologies-and-components"></a><span data-ttu-id="0e554-140">拓扑和组件</span><span class="sxs-lookup"><span data-stu-id="0e554-140">Topologies and components</span></span>

<span data-ttu-id="0e554-141">即时消息 (IM) 和存在所需的唯一组件包括：</span><span class="sxs-lookup"><span data-stu-id="0e554-141">The only components required for instant messaging (IM) and presence are:</span></span>
  
- <span data-ttu-id="0e554-142">您的组织的前端服务器 （称为池） 或标准版服务器。</span><span class="sxs-lookup"><span data-stu-id="0e554-142">Your organization's Front End servers (known as a pool) or a Standard Edition server.</span></span> <span data-ttu-id="0e554-143">将始终在这些服务器上启用 IM 和状态功能。</span><span class="sxs-lookup"><span data-stu-id="0e554-143">IM and presence capabilities are always enabled on these servers.</span></span> <span data-ttu-id="0e554-144">前端池拓扑和管理的详细信息，请参阅[前结束池高可用性和管理](high-availability-and-disaster-recovery/high-availability.md)。</span><span class="sxs-lookup"><span data-stu-id="0e554-144">For more information on Front End pool topologies and management, see [Front End Pool high availability and management](high-availability-and-disaster-recovery/high-availability.md).</span></span>
    
- <span data-ttu-id="0e554-145">负载平衡器（如果您拥有 Enterprise Edition 前端池）。</span><span class="sxs-lookup"><span data-stu-id="0e554-145">A load balancer, if you have an Enterprise Edition Front End pool.</span></span>
    
### <a name="supported-collocation"></a><span data-ttu-id="0e554-146">支持的并置</span><span class="sxs-lookup"><span data-stu-id="0e554-146">Supported collocation</span></span>

<span data-ttu-id="0e554-147">并置指的是，在单个服务器或一组服务器上安装多个角色。</span><span class="sxs-lookup"><span data-stu-id="0e554-147">Collocation is defined as having a single server, or group of servers, with multiple roles installed.</span></span> <span data-ttu-id="0e554-148">有关配置的详细信息，请参阅[有关业务服务器 2015年的 Skype 的拓扑结构基础](topology-basics/topology-basics.md)。</span><span class="sxs-lookup"><span data-stu-id="0e554-148">For details on collocation, see [Topology Basics for Skype for Business Server 2015](topology-basics/topology-basics.md).</span></span> 
  

