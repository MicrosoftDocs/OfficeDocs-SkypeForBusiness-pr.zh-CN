---
title: 规划即时消息和状态 Skype 业务 Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 70d2151e-9382-485d-ab14-758597571a74
description: 摘要： 了解如何规划即时消息和状态 Skype 业务服务器。
ms.openlocfilehash: e68a7b427545105db9ed543e2f1ad77411ba88b7
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "21002231"
---
# <a name="plan-for-instant-messaging-and-presence-in-skype-for-business-server"></a><span data-ttu-id="d3a8f-103">规划即时消息和状态 Skype 业务 Server</span><span class="sxs-lookup"><span data-stu-id="d3a8f-103">Plan for instant messaging and presence in Skype for Business Server</span></span>
 
<span data-ttu-id="d3a8f-104">**摘要：** 了解如何规划即时消息和状态 Skype 业务 Server。</span><span class="sxs-lookup"><span data-stu-id="d3a8f-104">**Summary:** Learn how to plan for instant messaging and presence in Skype for Business Server.</span></span>
  
<span data-ttu-id="d3a8f-105">规划即时消息和状态 Skype 业务 Server。</span><span class="sxs-lookup"><span data-stu-id="d3a8f-105">Plan for instant messaging and presence in Skype for Business Server.</span></span> <span data-ttu-id="d3a8f-106">若要了解有关具体的部署选项，如启用或禁用脱机即时消息 (IM)，请参阅[Deploy 即时消息和 Skype 业务服务器中的状态](../deploy/im-and-presence/im-and-presence.md)。</span><span class="sxs-lookup"><span data-stu-id="d3a8f-106">To learn about specific deployment options, such as enabling or disabling Offline Instant Messaging (IM), see [Deploy instant messaging and presence in Skype for Business Server](../deploy/im-and-presence/im-and-presence.md).</span></span>
  
## <a name="plan-for-instant-messaging-and-presence-in-skype-for-business-server"></a><span data-ttu-id="d3a8f-107">规划即时消息和状态 Skype 业务 Server</span><span class="sxs-lookup"><span data-stu-id="d3a8f-107">Plan for instant messaging and presence in Skype for Business Server</span></span>

<span data-ttu-id="d3a8f-108">前端服务器提供核心业务服务器功能，如即时消息 (IM) 和状态的 Skype 和都包含在每个 Skype 业务服务器部署。</span><span class="sxs-lookup"><span data-stu-id="d3a8f-108">Front End Servers provide core Skype for Business Server functionality such as instant messaging (IM) and presence and are included in every Skype for Business Server deployment.</span></span> <span data-ttu-id="d3a8f-109">有两个版本可用： 对于业务 Server Enterprise Edition，主要用于更大型组织，其中的 Skype 和业务 Server Standard Edition，其中主要用于较小的组织希望较小的 Skype硬件投资和不要求具备高可用性选项。</span><span class="sxs-lookup"><span data-stu-id="d3a8f-109">There are two editions available: Skype for Business Server Enterprise Edition, which is designed primarily for larger organizations, and Skype for Business Server Standard Edition, which is designed primarily for smaller organizations which want a smaller hardware investment and do not require full high availability options.</span></span> <span data-ttu-id="d3a8f-110">这两个版本的业务服务器工作负荷，包括 IM、 状态、 会议和企业语音支持所有 Skype。</span><span class="sxs-lookup"><span data-stu-id="d3a8f-110">Both editions support all Skype for Business Server workloads including IM, presence, conferencing, and Enterprise Voice.</span></span>
  
<span data-ttu-id="d3a8f-p103">通过即时消息 (IM)，用户可以在其计算机上使用基于文本的消息进行实时通信。支持双方和多方之间的 IM 会话。双方 IM 对话中的一方可以随时将第三方参与者加入对话中。发生这种情况时，对话窗口会做出相应改变以支持会议功能。</span><span class="sxs-lookup"><span data-stu-id="d3a8f-p103">Instant messaging (IM) enables your users to communicate with each other in real time on their computers using text-based messages. Both two-party and multiparty IM sessions are supported. A participant in a two-party IM conversation can add a third participant to the conversation at any time. When this happens, the Conversation window changes to support conferencing features.</span></span>
  
<span data-ttu-id="d3a8f-115">状态向用户提供网络中其他人的状态信息。</span><span class="sxs-lookup"><span data-stu-id="d3a8f-115">Presence provides information to users about the status of others on the network.</span></span> <span data-ttu-id="d3a8f-116">用户的状态提供有助于其他人决定自己是否应尝试与该用户联系，以及是否使用即时消息、 电话还是电子邮件的信息。</span><span class="sxs-lookup"><span data-stu-id="d3a8f-116">A user's presence status provides information to help others decide whether they should try to contact the user and whether to use instant messaging, phone, or email.</span></span> <span data-ttu-id="d3a8f-117">只要有可能，状态就会敦促进行即时通信；但状态也提供关于用户是否在开会或外出的信息，表明这种情况下不能进行即时通信。</span><span class="sxs-lookup"><span data-stu-id="d3a8f-117">Presence encourages instant communication when possible, but it also provides information about whether a user is in a meeting or out of the office, indicating that instant communication is not possible.</span></span> <span data-ttu-id="d3a8f-118">此状态在 Skype for Business 和其他可检测状态的应用程序（包括 Microsoft Outlook 消息和协作客户端、Microsoft SharePoint 技术和 Microsoft Office）中显示为状态图标。</span><span class="sxs-lookup"><span data-stu-id="d3a8f-118">This presence status is displayed as a presence icon in Skype for Business and other presence-aware applications, including the Microsoft Outlook messaging and collaboration client, Microsoft SharePoint technologies, and Microsoft Office.</span></span> <span data-ttu-id="d3a8f-119">状态图标表示用户的当前有空以及愿意进行交流。</span><span class="sxs-lookup"><span data-stu-id="d3a8f-119">The presence icon represents the user's current availability and willingness to communicate.</span></span> 
  
### <a name="technical-requirements"></a><span data-ttu-id="d3a8f-120">技术要求</span><span class="sxs-lookup"><span data-stu-id="d3a8f-120">Technical requirements</span></span>

<span data-ttu-id="d3a8f-121">即时消息 (IM) 和状态始终在 Enterprise Edition 前端池和 Standard Edition 服务器上运行。</span><span class="sxs-lookup"><span data-stu-id="d3a8f-121">Instant messaging (IM) and presence always run on Enterprise Edition Front End pools and Standard Edition servers.</span></span> <span data-ttu-id="d3a8f-122">有关受支持的硬件、 操作系统和数据库软件的信息，请参阅[认证的网关](../../SfbPartnerCertification/certification/infra-gateways.md)、[您 Skype 业务 2015年环境的要求](requirements-for-your-environment/requirements-for-your-environment.md)和 for Business Server 2019 Skype 的[基础结构要求](../../SfBServer2019/plan/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d3a8f-122">For information on supported hardware, operating systems, and database software, see  [Certified Gateways](../../SfbPartnerCertification/certification/infra-gateways.md),  [Requirements for your Skype for Business 2015 environment](requirements-for-your-environment/requirements-for-your-environment.md), and [Infrastructure requirements for Skype for Business Server 2019](../../SfBServer2019/plan/system-requirements.md).</span></span>
  
### <a name="enabling-communication-with-external-users"></a><span data-ttu-id="d3a8f-123">启用与外部用户的通信</span><span class="sxs-lookup"><span data-stu-id="d3a8f-123">Enabling communication with external users</span></span>

<span data-ttu-id="d3a8f-p106">通过允许您的用户与外部用户进行通信，可大大增加在 Skype for Business Server 中投资的收益。外部用户可能包括：</span><span class="sxs-lookup"><span data-stu-id="d3a8f-p106">You can greatly increase the benefits of your investment in Skype for Business Server by enabling your users to communicate with external users. External users can include:</span></span>
  
- <span data-ttu-id="d3a8f-126">远程用户： 您组织的内部用户，在防火墙外工作并使用其便携式计算机或其他 Skype 的业务服务器设备。</span><span class="sxs-lookup"><span data-stu-id="d3a8f-126">Remote users: Your organization's own users, when they are working outside your firewalls and are using their laptops or other Skype for Business Server devices.</span></span>
    
- <span data-ttu-id="d3a8f-127">联盟用户： 从您使用的公司还业务服务器运行 Skype 的用户。</span><span class="sxs-lookup"><span data-stu-id="d3a8f-127">Federated users: Users from companies you work with who also run Skype for Business Server.</span></span> <span data-ttu-id="d3a8f-128">要使用户轻松与这些用户联系，应与这些公司建立联盟关系。</span><span class="sxs-lookup"><span data-stu-id="d3a8f-128">To enable your users to easily contact these users, you create federated relationships with these companies.</span></span> 
    
- <span data-ttu-id="d3a8f-129">Skype 用户：Skype for Business 用户可使用 IM、语音和视频联系 Skype 上的数亿用户。</span><span class="sxs-lookup"><span data-stu-id="d3a8f-129">Skype users: Skype for Business users can reach the hundreds of millions of users on Skype with IM, voice and video.</span></span>
    
> [!NOTE]
> <span data-ttu-id="d3a8f-130">不再支持 AOL、Yahoo 和 Google Talk。</span><span class="sxs-lookup"><span data-stu-id="d3a8f-130">AOL, Yahoo, and Google Talk are no longer supported.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="d3a8f-131">要实现任意或所有这些方案，需要部署边缘服务器以帮助启用 Skype for Business Server 部署和外部用户之间的安全通信。</span><span class="sxs-lookup"><span data-stu-id="d3a8f-131">To enable any or all of these scenarios, you need to deploy an Edge Server to help enable secure communications between your Skype for Business Server deployment and external users.</span></span> <span data-ttu-id="d3a8f-132">贵组织的远程用户和联盟组织的用户都将能够查看彼此的状态，并使用 IM 进行通信。</span><span class="sxs-lookup"><span data-stu-id="d3a8f-132">Your organization's remote users and users at federated organizations will be able to see each other's presence and communicate using IM.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="d3a8f-133">可扩展消息传递和状态协议 (XMPP) 仅支持统一功能协作平台 (UCCP) 联合互操作性测试命令 (JITC) 认证方案。</span><span class="sxs-lookup"><span data-stu-id="d3a8f-133">Extensible Messaging and Presence Protocol (XMPP) is only supported for Unified Capabilities Collaboration Platform (UCCP) Joint Interoperability Test Command (JITC) certification scenarios.</span></span> 
  
### <a name="archiving-im-content"></a><span data-ttu-id="d3a8f-134">存档 IM 内容</span><span class="sxs-lookup"><span data-stu-id="d3a8f-134">Archiving IM content</span></span>

<span data-ttu-id="d3a8f-135">如果组织必须遵守合规性要求，Skype for Business Server 提供了您可以使用的功能。</span><span class="sxs-lookup"><span data-stu-id="d3a8f-135">Skype for Business Server provides features you can use if your organization must follow compliance regulations.</span></span> <span data-ttu-id="d3a8f-136">您可以使用存档功能为组织中的所有用户或仅为您指定的特定用户存档 IM 消息的内容。</span><span class="sxs-lookup"><span data-stu-id="d3a8f-136">You can use Archiving to archive the content of IM messages for all users in your organization or for only certain users that you specify.</span></span> <span data-ttu-id="d3a8f-137">有关详细信息，请参阅[Plan for Business Server 的 Skype 的存档](archiving/archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="d3a8f-137">For details, see [Plan for archiving in Skype for Business Server](archiving/archiving.md).</span></span> 
  
<span data-ttu-id="d3a8f-138">如果您还部署了 Microsoft Exchange Server 2013，则可以将 Exchange 数据的存档与 Skype for Business Server 数据的存档进行集成，并使用一个工具同时搜索这两种类型的存档数据。</span><span class="sxs-lookup"><span data-stu-id="d3a8f-138">If you also have Microsoft Exchange Server 2013 deployed, you can integrate the archiving of Exchange data with the archiving of Skype for Business Server data, and use a single tool to search both types of archived data.</span></span> <span data-ttu-id="d3a8f-139">有关详细信息，请参阅[业务服务器要使用 Exchange Server 存档配置的 Skype](../deploy/integrate-with-exchange-server/use-exchange-archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="d3a8f-139">For more information, see [Configure Skype for Business Server to use Exchange Server archiving](../deploy/integrate-with-exchange-server/use-exchange-archiving.md).</span></span>
  
### <a name="topologies-and-components"></a><span data-ttu-id="d3a8f-140">拓扑和组件</span><span class="sxs-lookup"><span data-stu-id="d3a8f-140">Topologies and components</span></span>

<span data-ttu-id="d3a8f-141">即时消息 (IM) 和状态所需的唯一组件是：</span><span class="sxs-lookup"><span data-stu-id="d3a8f-141">The only components required for instant messaging (IM) and presence are:</span></span>
  
- <span data-ttu-id="d3a8f-142">（称为池） 的组织的前端服务器或 Standard Edition server。</span><span class="sxs-lookup"><span data-stu-id="d3a8f-142">Your organization's Front End servers (known as a pool) or a Standard Edition server.</span></span> <span data-ttu-id="d3a8f-143">将始终在这些服务器上启用 IM 和状态功能。</span><span class="sxs-lookup"><span data-stu-id="d3a8f-143">IM and presence capabilities are always enabled on these servers.</span></span> <span data-ttu-id="d3a8f-144">在前端池拓扑结构和管理的详细信息，请参阅[前端池高可用性和管理](high-availability-and-disaster-recovery/high-availability.md)。</span><span class="sxs-lookup"><span data-stu-id="d3a8f-144">For more information on Front End pool topologies and management, see [Front End Pool high availability and management](high-availability-and-disaster-recovery/high-availability.md).</span></span>
    
- <span data-ttu-id="d3a8f-145">负载平衡器（如果您拥有 Enterprise Edition 前端池）。</span><span class="sxs-lookup"><span data-stu-id="d3a8f-145">A load balancer, if you have an Enterprise Edition Front End pool.</span></span>
    
### <a name="supported-collocation"></a><span data-ttu-id="d3a8f-146">支持的并置</span><span class="sxs-lookup"><span data-stu-id="d3a8f-146">Supported collocation</span></span>

<span data-ttu-id="d3a8f-147">并置指的是，在单个服务器或一组服务器上安装多个角色。</span><span class="sxs-lookup"><span data-stu-id="d3a8f-147">Collocation is defined as having a single server, or group of servers, with multiple roles installed.</span></span> <span data-ttu-id="d3a8f-148">并置的详细信息，请参阅[拓扑的 Skype 业务服务器的基础知识](topology-basics/topology-basics.md)。</span><span class="sxs-lookup"><span data-stu-id="d3a8f-148">For details on collocation, see [Topology Basics for Skype for Business Server](topology-basics/topology-basics.md).</span></span> 
  

