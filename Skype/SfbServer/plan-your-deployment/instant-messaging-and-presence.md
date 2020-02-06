---
title: 在 Skype for Business 服务器中规划即时消息和状态
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
ms.assetid: 70d2151e-9382-485d-ab14-758597571a74
description: 摘要：了解如何规划 Skype for Business 服务器中的即时消息和状态。
ms.openlocfilehash: d62559afe0c7767ee7863f41b41f2d1b64127643
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815900"
---
# <a name="plan-for-instant-messaging-and-presence-in-skype-for-business-server"></a><span data-ttu-id="cec43-103">在 Skype for Business 服务器中规划即时消息和状态</span><span class="sxs-lookup"><span data-stu-id="cec43-103">Plan for instant messaging and presence in Skype for Business Server</span></span>
 
<span data-ttu-id="cec43-104">**摘要：** 了解如何规划 Skype for Business 服务器中的即时消息和状态。</span><span class="sxs-lookup"><span data-stu-id="cec43-104">**Summary:** Learn how to plan for instant messaging and presence in Skype for Business Server.</span></span>
  
<span data-ttu-id="cec43-105">在 Skype for Business 服务器中规划即时消息和状态。</span><span class="sxs-lookup"><span data-stu-id="cec43-105">Plan for instant messaging and presence in Skype for Business Server.</span></span> <span data-ttu-id="cec43-106">若要了解特定的部署选项（如启用或禁用脱机即时消息（IM）），请参阅[在 Skype For Business 服务器中部署即时消息和状态](../deploy/im-and-presence/im-and-presence.md)。</span><span class="sxs-lookup"><span data-stu-id="cec43-106">To learn about specific deployment options, such as enabling or disabling Offline Instant Messaging (IM), see [Deploy instant messaging and presence in Skype for Business Server](../deploy/im-and-presence/im-and-presence.md).</span></span>
  
## <a name="plan-for-instant-messaging-and-presence-in-skype-for-business-server"></a><span data-ttu-id="cec43-107">在 Skype for Business 服务器中规划即时消息和状态</span><span class="sxs-lookup"><span data-stu-id="cec43-107">Plan for instant messaging and presence in Skype for Business Server</span></span>

<span data-ttu-id="cec43-108">前端服务器提供核心 Skype for business 服务器功能，如即时消息（IM）和联机状态，并且包括在每个 Skype for Business 服务器部署中。</span><span class="sxs-lookup"><span data-stu-id="cec43-108">Front End Servers provide core Skype for Business Server functionality such as instant messaging (IM) and presence and are included in every Skype for Business Server deployment.</span></span> <span data-ttu-id="cec43-109">有两个可用的版本： Skype for business Server 企业版，主要针对较大型组织和 Skype for business Server Standard Edition 进行设计，它主要用于需要较小的小型组织硬件投资，不需要完整的高可用性选项。</span><span class="sxs-lookup"><span data-stu-id="cec43-109">There are two editions available: Skype for Business Server Enterprise Edition, which is designed primarily for larger organizations, and Skype for Business Server Standard Edition, which is designed primarily for smaller organizations which want a smaller hardware investment and do not require full high availability options.</span></span> <span data-ttu-id="cec43-110">这两个版本都支持所有 Skype for Business 服务器工作负载，包括即时消息、状态、会议和企业语音。</span><span class="sxs-lookup"><span data-stu-id="cec43-110">Both editions support all Skype for Business Server workloads including IM, presence, conferencing, and Enterprise Voice.</span></span>
  
<span data-ttu-id="cec43-111">通过即时消息 (IM)，用户可以在其计算机上使用基于文本的消息进行实时通信。</span><span class="sxs-lookup"><span data-stu-id="cec43-111">Instant messaging (IM) enables your users to communicate with each other in real time on their computers using text-based messages.</span></span> <span data-ttu-id="cec43-112">支持双方和多方之间的 IM 会话。</span><span class="sxs-lookup"><span data-stu-id="cec43-112">Both two-party and multiparty IM sessions are supported.</span></span> <span data-ttu-id="cec43-113">双方 IM 对话中的一方可以随时将第三方参与者加入对话中。</span><span class="sxs-lookup"><span data-stu-id="cec43-113">A participant in a two-party IM conversation can add a third participant to the conversation at any time.</span></span> <span data-ttu-id="cec43-114">发生这种情况时，对话窗口会做出相应改变以支持会议功能。</span><span class="sxs-lookup"><span data-stu-id="cec43-114">When this happens, the Conversation window changes to support conferencing features.</span></span>
  
<span data-ttu-id="cec43-115">状态向用户提供网络中其他人的状态信息。</span><span class="sxs-lookup"><span data-stu-id="cec43-115">Presence provides information to users about the status of others on the network.</span></span> <span data-ttu-id="cec43-116">用户的状态提供有助于其他人决定是否应尝试联系用户以及是否使用即时消息、电话或电子邮件的信息。</span><span class="sxs-lookup"><span data-stu-id="cec43-116">A user's presence status provides information to help others decide whether they should try to contact the user and whether to use instant messaging, phone, or email.</span></span> <span data-ttu-id="cec43-117">只要有可能，状态就会敦促进行即时通信；但状态也提供关于用户是否在开会或外出的信息，表明这种情况下不能进行即时通信。</span><span class="sxs-lookup"><span data-stu-id="cec43-117">Presence encourages instant communication when possible, but it also provides information about whether a user is in a meeting or out of the office, indicating that instant communication is not possible.</span></span> <span data-ttu-id="cec43-118">此状态在 Skype for Business 和其他可检测状态的应用程序（包括 Microsoft Outlook 消息和协作客户端、Microsoft SharePoint 技术和 Microsoft Office）中显示为状态图标。</span><span class="sxs-lookup"><span data-stu-id="cec43-118">This presence status is displayed as a presence icon in Skype for Business and other presence-aware applications, including the Microsoft Outlook messaging and collaboration client, Microsoft SharePoint technologies, and Microsoft Office.</span></span> <span data-ttu-id="cec43-119">"状态" 图标表示用户的当前可用性和通信意愿。</span><span class="sxs-lookup"><span data-stu-id="cec43-119">The presence icon represents the user's current availability and willingness to communicate.</span></span> 
  
### <a name="technical-requirements"></a><span data-ttu-id="cec43-120">技术要求</span><span class="sxs-lookup"><span data-stu-id="cec43-120">Technical requirements</span></span>

<span data-ttu-id="cec43-121">即时消息 (IM) 和状态始终在 Enterprise Edition 前端池和 Standard Edition 服务器上运行。</span><span class="sxs-lookup"><span data-stu-id="cec43-121">Instant messaging (IM) and presence always run on Enterprise Edition Front End pools and Standard Edition servers.</span></span> <span data-ttu-id="cec43-122">有关受支持的硬件、操作系统和数据库软件的信息，请参阅[认证网关](../../SfbPartnerCertification/certification/infra-gateways.md)、skype for business [2015 环境的要求](requirements-for-your-environment/requirements-for-your-environment.md)和[skype For Business Server 2019 的基础结构要求](../../SfBServer2019/plan/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="cec43-122">For information on supported hardware, operating systems, and database software, see  [Certified Gateways](../../SfbPartnerCertification/certification/infra-gateways.md),  [Requirements for your Skype for Business 2015 environment](requirements-for-your-environment/requirements-for-your-environment.md), and [Infrastructure requirements for Skype for Business Server 2019](../../SfBServer2019/plan/system-requirements.md).</span></span>
  
### <a name="enabling-communication-with-external-users"></a><span data-ttu-id="cec43-123">启用与外部用户的通信</span><span class="sxs-lookup"><span data-stu-id="cec43-123">Enabling communication with external users</span></span>

<span data-ttu-id="cec43-124">通过使你的用户能够与外部用户进行通信，你可以大大增加 Skype for business 服务器的投资带来的好处。</span><span class="sxs-lookup"><span data-stu-id="cec43-124">You can greatly increase the benefits of your investment in Skype for Business Server by enabling your users to communicate with external users.</span></span> <span data-ttu-id="cec43-125">外部用户可能包括：</span><span class="sxs-lookup"><span data-stu-id="cec43-125">External users can include:</span></span>
  
- <span data-ttu-id="cec43-126">远程用户：你的组织自己的用户，当他们在防火墙外部工作时使用笔记本或其他 Skype for business 服务器设备。</span><span class="sxs-lookup"><span data-stu-id="cec43-126">Remote users: Your organization's own users, when they are working outside your firewalls and are using their laptops or other Skype for Business Server devices.</span></span>
    
- <span data-ttu-id="cec43-127">联盟用户：与同时运行 Skype for business Server 的用户进行协作的公司用户。</span><span class="sxs-lookup"><span data-stu-id="cec43-127">Federated users: Users from companies you work with who also run Skype for Business Server.</span></span> <span data-ttu-id="cec43-128">要使用户轻松与这些用户联系，应与这些公司建立联盟关系。</span><span class="sxs-lookup"><span data-stu-id="cec43-128">To enable your users to easily contact these users, you create federated relationships with these companies.</span></span> 
    
- <span data-ttu-id="cec43-129">Skype 用户：Skype for Business 用户可使用 IM、语音和视频联系 Skype 上的数亿用户。</span><span class="sxs-lookup"><span data-stu-id="cec43-129">Skype users: Skype for Business users can reach the hundreds of millions of users on Skype with IM, voice and video.</span></span>
    
> [!NOTE]
> <span data-ttu-id="cec43-130">不再支持 AOL、Yahoo 和 Google Talk。</span><span class="sxs-lookup"><span data-stu-id="cec43-130">AOL, Yahoo, and Google Talk are no longer supported.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="cec43-131">若要启用任何或所有这些方案，你需要部署边缘服务器以帮助在 Skype for Business 服务器部署和外部用户之间实现安全通信。</span><span class="sxs-lookup"><span data-stu-id="cec43-131">To enable any or all of these scenarios, you need to deploy an Edge Server to help enable secure communications between your Skype for Business Server deployment and external users.</span></span> <span data-ttu-id="cec43-132">你的组织的远程用户和联合组织中的用户将能够使用 IM 查看彼此的状态和通信。</span><span class="sxs-lookup"><span data-stu-id="cec43-132">Your organization's remote users and users at federated organizations will be able to see each other's presence and communicate using IM.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="cec43-133">可扩展消息传递和状态协议 (XMPP) 仅支持统一功能协作平台 (UCCP) 联合互操作性测试命令 (JITC) 认证方案。</span><span class="sxs-lookup"><span data-stu-id="cec43-133">Extensible Messaging and Presence Protocol (XMPP) is only supported for Unified Capabilities Collaboration Platform (UCCP) Joint Interoperability Test Command (JITC) certification scenarios.</span></span> 
  
### <a name="archiving-im-content"></a><span data-ttu-id="cec43-134">存档 IM 内容</span><span class="sxs-lookup"><span data-stu-id="cec43-134">Archiving IM content</span></span>

<span data-ttu-id="cec43-135">如果您的组织必须遵守合规性法规，则 Skype for business 服务器提供可以使用的功能。</span><span class="sxs-lookup"><span data-stu-id="cec43-135">Skype for Business Server provides features you can use if your organization must follow compliance regulations.</span></span> <span data-ttu-id="cec43-136">你可以使用存档功能为组织中的所有用户或仅为你指定的特定用户存档 IM 消息的内容。</span><span class="sxs-lookup"><span data-stu-id="cec43-136">You can use Archiving to archive the content of IM messages for all users in your organization or for only certain users that you specify.</span></span> <span data-ttu-id="cec43-137">有关详细信息，请参阅[在 Skype For Business 服务器中规划存档](archiving/archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="cec43-137">For details, see [Plan for archiving in Skype for Business Server](archiving/archiving.md).</span></span> 
  
<span data-ttu-id="cec43-138">如果你还部署了 Microsoft Exchange Server 2013，你可以将 Exchange 数据的存档与 Skype for Business 服务器数据的存档进行集成，并使用单个工具搜索两种类型的已存档数据。</span><span class="sxs-lookup"><span data-stu-id="cec43-138">If you also have Microsoft Exchange Server 2013 deployed, you can integrate the archiving of Exchange data with the archiving of Skype for Business Server data, and use a single tool to search both types of archived data.</span></span> <span data-ttu-id="cec43-139">有关详细信息，请参阅[配置 Skype For Business 服务器以使用 Exchange Server 存档](../deploy/integrate-with-exchange-server/use-exchange-archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="cec43-139">For more information, see [Configure Skype for Business Server to use Exchange Server archiving](../deploy/integrate-with-exchange-server/use-exchange-archiving.md).</span></span>
  
### <a name="topologies-and-components"></a><span data-ttu-id="cec43-140">拓扑和组件</span><span class="sxs-lookup"><span data-stu-id="cec43-140">Topologies and components</span></span>

<span data-ttu-id="cec43-141">即时消息 (IM) 和状态所需的唯一组件是：</span><span class="sxs-lookup"><span data-stu-id="cec43-141">The only components required for instant messaging (IM) and presence are:</span></span>
  
- <span data-ttu-id="cec43-142">组织的前端服务器（称为池）或标准版服务器。</span><span class="sxs-lookup"><span data-stu-id="cec43-142">Your organization's Front End servers (known as a pool) or a Standard Edition server.</span></span> <span data-ttu-id="cec43-143">将始终在这些服务器上启用 IM 和状态功能。</span><span class="sxs-lookup"><span data-stu-id="cec43-143">IM and presence capabilities are always enabled on these servers.</span></span> <span data-ttu-id="cec43-144">有关前端池拓扑和管理的详细信息，请参阅[前端池高可用性和管理](high-availability-and-disaster-recovery/high-availability.md)。</span><span class="sxs-lookup"><span data-stu-id="cec43-144">For more information on Front End pool topologies and management, see [Front End Pool high availability and management](high-availability-and-disaster-recovery/high-availability.md).</span></span>
    
- <span data-ttu-id="cec43-145">负载平衡器（如果您拥有 Enterprise Edition 前端池）。</span><span class="sxs-lookup"><span data-stu-id="cec43-145">A load balancer, if you have an Enterprise Edition Front End pool.</span></span>
    
### <a name="supported-collocation"></a><span data-ttu-id="cec43-146">支持的并置</span><span class="sxs-lookup"><span data-stu-id="cec43-146">Supported collocation</span></span>

<span data-ttu-id="cec43-147">并置指的是，在单个服务器或一组服务器上安装多个角色。</span><span class="sxs-lookup"><span data-stu-id="cec43-147">Collocation is defined as having a single server, or group of servers, with multiple roles installed.</span></span> <span data-ttu-id="cec43-148">有关 collocation 的详细信息，请参阅[Skype for Business 服务器的拓扑基础知识](topology-basics/topology-basics.md)。</span><span class="sxs-lookup"><span data-stu-id="cec43-148">For details on collocation, see [Topology Basics for Skype for Business Server](topology-basics/topology-basics.md).</span></span> 
  

