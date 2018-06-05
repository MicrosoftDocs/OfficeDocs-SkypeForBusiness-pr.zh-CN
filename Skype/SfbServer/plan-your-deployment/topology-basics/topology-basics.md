---
title: Skype for Business Server 2015 的拓扑基础知识
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 113e8c3f-71de-435c-bc4a-918ac7b50008
description: 摘要： 为业务服务器 2015 Skype 选择您的拓扑。 了解有关的 Skype 的业务服务器 2015年的服务器并置。
ms.openlocfilehash: d7760ecc2998bdb2ace400cfaeec6eddaf5fcb5b
ms.sourcegitcommit: a5b8b0a1e5ae5eb718e296ca6df6687368ee9174
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/05/2018
ms.locfileid: "19504521"
---
# <a name="topology-basics-for-skype-for-business-server-2015"></a><span data-ttu-id="d559c-104">Skype for Business Server 2015 的拓扑基础知识</span><span class="sxs-lookup"><span data-stu-id="d559c-104">Topology Basics for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="d559c-p102">**摘要：** 为 Skype for Business Server 2015 选择拓扑。了解 Skype for Business Server 2015 的服务器并置。</span><span class="sxs-lookup"><span data-stu-id="d559c-p102">**Summary:** Choose your topology for Skype for Business Server 2015. Learn about server collocation for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="d559c-107">之前准备任何其他操作，您需要知道您的业务服务器 2015 Skype 的部署计划右拓扑。</span><span class="sxs-lookup"><span data-stu-id="d559c-107">Before preparing anything else, you'll want to know you're planning for the right topology for your deployment of Skype for Business Server 2015.</span></span> <span data-ttu-id="d559c-108">如果您将对业务服务器 2015年拥有 Skype 的内部部署或您打算将这与在混合部署中的业务 Server 联机部署的 Skype 相结合的首先需要决定。</span><span class="sxs-lookup"><span data-stu-id="d559c-108">The first thing you need to decide is if you're going to have an on-premises deployment of Skype for Business Server 2015, or if you're going to combine this with a Skype for Business Server Online deployment in a Hybrid deployment.</span></span> <span data-ttu-id="d559c-109">两种方法，您将需要进一步，阅读，我们将详细介绍在本地拓扑在这里，但混合详细信息记录在各自的部分。</span><span class="sxs-lookup"><span data-stu-id="d559c-109">Either way, you're going to want to read further, as we'll detail the on-premises topologies here, but the Hybrid details are documented in their own section.</span></span>
  
<span data-ttu-id="d559c-110">您还可以参见[业务服务器 2015年的 Skype 的参考拓扑](reference-topologies.md)中的一些示例拓扑。</span><span class="sxs-lookup"><span data-stu-id="d559c-110">You can also see some example topologies in [Reference topologies for Skype for Business Server 2015](reference-topologies.md).</span></span>
  
## <a name="sites"></a><span data-ttu-id="d559c-111">站点</span><span class="sxs-lookup"><span data-stu-id="d559c-111">Sites</span></span>

<span data-ttu-id="d559c-112">Skype 业务服务器，在网站定义包含 Skype 业务服务器组件在网络上。</span><span class="sxs-lookup"><span data-stu-id="d559c-112">In Skype for Business Server, you define sites on your network that contain Skype for Business Server components.</span></span> <span data-ttu-id="d559c-113">站点是一组由高速度、低延迟网络（例如，单个局域网 (LAN) 或由高速光纤网络连接的两个网络）完美连接的计算机。</span><span class="sxs-lookup"><span data-stu-id="d559c-113">A site is a set of computers that is well-connected by a high-speed, low-latency network, such as a single local area network (LAN) or two networks connected by a high-speed fiber optic network.</span></span> <span data-ttu-id="d559c-114">请注意，业务 Server 网站的 Skype 从 Active Directory 域服务站点和 Microsoft Exchange Server 网站的一个单独的概念。</span><span class="sxs-lookup"><span data-stu-id="d559c-114">Note that Skype for Business Server sites are a separate concept from Active Directory Domain Services sites and Microsoft Exchange Server sites.</span></span> <span data-ttu-id="d559c-115">您的业务 Server 网站的 Skype 不需要对应于您的 Active Directory 站点。</span><span class="sxs-lookup"><span data-stu-id="d559c-115">Your Skype for Business Server sites do not need to correspond to your Active Directory sites.</span></span>
  
<span data-ttu-id="d559c-116">业务服务器 2015年的 Skype 支持的本地部署可根据您的高可用性和位置要求进行扩展的一个或多个网站。</span><span class="sxs-lookup"><span data-stu-id="d559c-116">Skype for Business Server 2015 supports on-premises deployment of one or more sites that can be scaled according to your high availability and location requirements.</span></span>
  
<span data-ttu-id="d559c-117">您部署都将具有至少一个中央站点 （也称为数据中心，这是一个数据中心的位于它的所有服务器），并部署中的每个中央站点具有一台 Standard Edition 服务器或至少一个 Enterprise Edition 前端池。</span><span class="sxs-lookup"><span data-stu-id="d559c-117">Your deployment will have at least one central site (also called a datacenter, this is a datacenter for all the servers located in it), and each central site in your deployment will have one Standard Edition server, or at least one Enterprise Edition Front End pool.</span></span> <span data-ttu-id="d559c-118">您可以在以下每个选项中了解其中的差异：</span><span class="sxs-lookup"><span data-stu-id="d559c-118">You can see the differences in each option below:</span></span>
  
- <span data-ttu-id="d559c-119">Standard Edition server 包括一个并置的 SQL Server Express 数据库。</span><span class="sxs-lookup"><span data-stu-id="d559c-119">Standard Edition server includes a collocated SQL Server Express database.</span></span>
    
- <span data-ttu-id="d559c-120">Enterprise Edition 前端池包括：</span><span class="sxs-lookup"><span data-stu-id="d559c-120">Enterprise Edition Front End pool includes:</span></span>
    
  - <span data-ttu-id="d559c-121">一个或多个前端服务器 （理想情况下至少三个，为实现可伸缩性），最多为 12 个。</span><span class="sxs-lookup"><span data-stu-id="d559c-121">One or more Front End Servers (Ideally at least three, for scalability), with a maximum of twelve.</span></span> <span data-ttu-id="d559c-122">对于多个服务器，需要提供负载平衡。</span><span class="sxs-lookup"><span data-stu-id="d559c-122">Load-balancing would be required for more than one server.</span></span>
    
  - <span data-ttu-id="d559c-123">单独后端服务器。</span><span class="sxs-lookup"><span data-stu-id="d559c-123">A separate Back End Server.</span></span>
    
<span data-ttu-id="d559c-124">您可以在此部分了解有关各种服务器角色的更多信息。</span><span class="sxs-lookup"><span data-stu-id="d559c-124">You can learn more about the various server roles a little later in this section.</span></span>
  
<span data-ttu-id="d559c-125">除了中央站点，可能还都有一个或多个与中央站点关联的分支站点。</span><span class="sxs-lookup"><span data-stu-id="d559c-125">In addition to your central sites, you may also end up having one or more branch sites associated with your central site.</span></span> <span data-ttu-id="d559c-126">他们取决于其几乎所有的功能的中央站点，以便他们组成，完全是什么？</span><span class="sxs-lookup"><span data-stu-id="d559c-126">They depend on the central site for almost all their functionality, so what are they made up of, exactly?</span></span>
  
- <span data-ttu-id="d559c-127">Survivable Branch Appliance，与业务服务器 2015年功能一些 Skype 结合使用公用电话交换网 (pstn) 网关。</span><span class="sxs-lookup"><span data-stu-id="d559c-127">Survivable Branch Appliance, which combines a public switched telephone network (PSTN) gateway, with some Skype for Business Server 2015 functionality.</span></span>
    
- <span data-ttu-id="d559c-128">Survivable Branch Server，它是运行 Windows Server 已安装的业务服务器 2015年注册器和中介服务器软件的 Skype 的服务器。</span><span class="sxs-lookup"><span data-stu-id="d559c-128">Survivable Branch Server, it's a server running Windows Server that has Skype for Business Server 2015 Registrar and Mediation Server software installed.</span></span>
    
- <span data-ttu-id="d559c-129">独立 PSTN 网关 （其不是 Survivable Branch Appliance 的一部分）。</span><span class="sxs-lookup"><span data-stu-id="d559c-129">Stand-alone PSTN gateway (which isn't part of the Survivable Branch Appliance).</span></span>
    
- <span data-ttu-id="d559c-130">独立的中介服务器或独立中介服务器池 （如果您不想要将此角色并置与 Survivable Branch Appliance）。</span><span class="sxs-lookup"><span data-stu-id="d559c-130">Stand-alone Mediation Server or stand-alone Mediation Server pool (if you don't want to collocate this role with the Survivable Branch Appliance).</span></span>
    
## <a name="whats-in-a-skype-for-business-server-site"></a><span data-ttu-id="d559c-131">Skype 业务 Server 网站中是什么？</span><span class="sxs-lookup"><span data-stu-id="d559c-131">What's in a Skype for Business Server site?</span></span>

<span data-ttu-id="d559c-132">要获取到更多详细信息，请中央站点还可以：</span><span class="sxs-lookup"><span data-stu-id="d559c-132">To get into more detail, a central site can also have:</span></span>
  
- <span data-ttu-id="d559c-133">多个前端池，在同一个或多个不同域 （记住规划所有前端服务器在前端池中后, 端服务器池，以及处于同一个域）。</span><span class="sxs-lookup"><span data-stu-id="d559c-133">Multiple Front End pools, in the same domain or different domains (remember in planning that all the Front End Servers in a Front End pool, along with the Back End Servers for the pool, do have to be in the same domain).</span></span>
    
- <span data-ttu-id="d559c-134">多个 Standard Edition 服务器。</span><span class="sxs-lookup"><span data-stu-id="d559c-134">Multiple Standard Edition servers.</span></span>
    
- <span data-ttu-id="d559c-135">Office Web Apps Server，用于与 Office Web Apps 中 Skype 业务服务器 2015年共享和呈现的 PowerPoint 演示文稿。</span><span class="sxs-lookup"><span data-stu-id="d559c-135">Office Web Apps Server, which is used with Office Web Apps in Skype for Business Server 2015 for sharing and rendering of PowerPoint presentations.</span></span>
    
- <span data-ttu-id="d559c-136">边缘服务器或边缘池 （在外围网络中）。</span><span class="sxs-lookup"><span data-stu-id="d559c-136">Edge Server or Edge pool (in a perimeter network).</span></span> <span data-ttu-id="d559c-137">如果希望部署支持联盟伙伴、公共 IM 连接、可扩展消息传递和状态协议 (XMPP) 网关以及远程用户访问，则需要此组件。</span><span class="sxs-lookup"><span data-stu-id="d559c-137">Needed if you want your deployment to support federated partners, public IM connectivity, extensible messaging and presence protocol (XMPP) gateway, and remote user access.</span></span> <span data-ttu-id="d559c-138">边缘服务器规划文档中，可以找到更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="d559c-138">More details can be found in the Edge Server Planning documentation.</span></span>
    
- <span data-ttu-id="d559c-139">持久聊天服务器。</span><span class="sxs-lookup"><span data-stu-id="d559c-139">Persistent Chat Server.</span></span> <span data-ttu-id="d559c-140">如果您希望用户能够参与多方、基于主题的持久对话，则此组件将提供帮助。</span><span class="sxs-lookup"><span data-stu-id="d559c-140">Useful if you want users to be able to take part in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="d559c-141">没有位于 Planning for Persistent Chat Server 主题的详细信息。</span><span class="sxs-lookup"><span data-stu-id="d559c-141">There's more information at the Planning for Persistent Chat Server topic.</span></span>
    
- <span data-ttu-id="d559c-142">监控。</span><span class="sxs-lookup"><span data-stu-id="d559c-142">Monitoring.</span></span> <span data-ttu-id="d559c-143">用于支持数据收集的音频/视频 (A / V) 的用户体验质量 (QoE) 和呼叫详细记录 (CDR) 信息的企业语音和 A / V 会议部署中的。</span><span class="sxs-lookup"><span data-stu-id="d559c-143">Used to support data collection for audio/video (A/V) Quality of Experience (QoE) and call detail recording (CDR) for Enterprise Voice and A/V conferences in your deployment.</span></span> <span data-ttu-id="d559c-144">我们将在“规划监控”主题中详细谈论这一内容。</span><span class="sxs-lookup"><span data-stu-id="d559c-144">We discuss it in detail at the Planning for Monitoring topic.</span></span>
    
- <span data-ttu-id="d559c-145">控制器或控制器池。</span><span class="sxs-lookup"><span data-stu-id="d559c-145">Director or Director pool.</span></span> <span data-ttu-id="d559c-146">不需要，但有用如果您想要提高恢复能力和启用业务 2015年到用户的主池的用户请求的 Skype 的重定向。</span><span class="sxs-lookup"><span data-stu-id="d559c-146">Not required, but useful if you want to improve resiliency and enable redirection of Skype for Business 2015 user requests to the user's home pool.</span></span> <span data-ttu-id="d559c-147">如果您想要部署控制器，则支持最大值 10 每个池。</span><span class="sxs-lookup"><span data-stu-id="d559c-147">If you want to deploy Directors, a maximum of 10 per pool is supported.</span></span> <span data-ttu-id="d559c-148">如果这是一个需要肯定控制器主题规划在继续阅读。</span><span class="sxs-lookup"><span data-stu-id="d559c-148">If this is something you need, definitely continue reading at the Planning for Directors topic.</span></span>
    
- <span data-ttu-id="d559c-149">反向代理。</span><span class="sxs-lookup"><span data-stu-id="d559c-149">Reverse proxy.</span></span> <span data-ttu-id="d559c-150">这不是 Skype 对于业务服务器 2015年组件，但如果您想要支持共享的 web 内容的联盟用户，如果您打算支持移动通信，如果您的远程用户想要使用通讯簿中，加入会议，等等，这是内容要将您的环境中。</span><span class="sxs-lookup"><span data-stu-id="d559c-150">This isn't a Skype for Business Server 2015 component, but if you want to support the sharing of web content for federated users, if you intend to support Mobility traffic, if your remote users want to use the address book, join meetings, and so on, this is something you'll want to have in your environment.</span></span> <span data-ttu-id="d559c-151">没有设置可以签出的详细信息，当您准备好的反向代理服务器主题。</span><span class="sxs-lookup"><span data-stu-id="d559c-151">There's a Setting up Reverse proxy server topic you can check out for more details, when you're ready.</span></span>
    
<span data-ttu-id="d559c-152">有关这些服务器的并置的其他信息，请参见以下内容。</span><span class="sxs-lookup"><span data-stu-id="d559c-152">Additional information on collocation for these servers can be found below.</span></span>
  
<span data-ttu-id="d559c-153">所有前端池和 Standard Edition 服务器部署在中央站点上都共享以下内容，假定您已经部署了它们：</span><span class="sxs-lookup"><span data-stu-id="d559c-153">All the Front End pools and Standard Edition servers deployed at your central site share the following, assuming you've deployed them:</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="d559c-154">控制器或控制器池</span><span class="sxs-lookup"><span data-stu-id="d559c-154">Director or Director pool</span></span>  <br/> |<span data-ttu-id="d559c-155">独立的中介服务器或中介服务器池</span><span class="sxs-lookup"><span data-stu-id="d559c-155">Stand-alone Mediation Server or Mediation Server pool</span></span>  <br/> |<span data-ttu-id="d559c-156">Office Web Apps Server</span><span class="sxs-lookup"><span data-stu-id="d559c-156">Office Web Apps Server</span></span>  <br/> |
|<span data-ttu-id="d559c-157">边缘服务器或边缘池</span><span class="sxs-lookup"><span data-stu-id="d559c-157">Edge Server or Edge pool</span></span>  <br/> |<span data-ttu-id="d559c-158">持久聊天服务器或持久聊天服务器池</span><span class="sxs-lookup"><span data-stu-id="d559c-158">Persistent Chat Server or Persistent Chat Server pool</span></span>  <br/> |<span data-ttu-id="d559c-159">监控</span><span class="sxs-lookup"><span data-stu-id="d559c-159">Monitoring</span></span>  <br/> |
   
<span data-ttu-id="d559c-160">此列表中的 Exchange 统一消息 (UM) 服务器在哪里</span><span class="sxs-lookup"><span data-stu-id="d559c-160">Where is Exchange Unified Messaging (UM) Server in this list?</span></span> <span data-ttu-id="d559c-161">喔，您可以一定使用它 Skype 的业务服务器 2015年如果您希望与 Exchange UM 集成，但它不是业务 Server 网站，Skype 的组件，因此我们不此处提及它。</span><span class="sxs-lookup"><span data-stu-id="d559c-161">Well, you can certainly use it with Skype for Business Server 2015 if you want to integrate with Exchange UM, but it's not a component of the Skype for Business Server site, so we're not mentioning it here.</span></span>
  
<span data-ttu-id="d559c-162">可能规划您具有多个中央站点，并且如果是这样，他们可以共享的以下服务器和角色，如果在管理中心网站上部署：</span><span class="sxs-lookup"><span data-stu-id="d559c-162">You may be planning to have multiple central site, and if that's so, they can share the following servers and roles, if they're deployed on your central site:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="d559c-163">独立的中介服务器或中介服务器池</span><span class="sxs-lookup"><span data-stu-id="d559c-163">Stand-alone Mediation Server or Mediation Server pool</span></span>  <br/> |<span data-ttu-id="d559c-164">边缘服务器或边缘池</span><span class="sxs-lookup"><span data-stu-id="d559c-164">Edge Server or Edge pool</span></span>  <br/> |
|<span data-ttu-id="d559c-165">持久聊天服务器或持久聊天服务器池</span><span class="sxs-lookup"><span data-stu-id="d559c-165">Persistent Chat Server or Persistent Chat Server pool</span></span>  <br/> |<span data-ttu-id="d559c-166">监控</span><span class="sxs-lookup"><span data-stu-id="d559c-166">Monitoring</span></span>  <br/> |
   
<span data-ttu-id="d559c-167">就像最后一个列表中，我们不包括在 Exchange UM 服务器此处，因为它不是业务服务器 2015年部署 Skype 的一部分，但它太属于同一类别此处。</span><span class="sxs-lookup"><span data-stu-id="d559c-167">Just like the last list, we aren't including the Exchange UM Server here because it's not part of the Skype for Business Server 2015 deployment, but it falls into the same category here, too.</span></span>
  
<span data-ttu-id="d559c-168">当然，部署中还包含其他一些组件和选项。</span><span class="sxs-lookup"><span data-stu-id="d559c-168">There are some other components and options that go into deployments, of course.</span></span>
  
|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d559c-169">防火墙</span><span class="sxs-lookup"><span data-stu-id="d559c-169">Firewalls</span></span>  <br/> |<span data-ttu-id="d559c-170">PSTN 网关（如果部署企业语音）</span><span class="sxs-lookup"><span data-stu-id="d559c-170">PSTN gateways (if you deploy Enterprise Voice</span></span>  <br/> |<span data-ttu-id="d559c-171">Exchange UM 服务器 （如果您想要与 Exchange UM 集成）</span><span class="sxs-lookup"><span data-stu-id="d559c-171">Exchange UM Server (if you want to integrate with Exchange UM)</span></span>  <br/> |<span data-ttu-id="d559c-172">DNS 负载平衡</span><span class="sxs-lookup"><span data-stu-id="d559c-172">DNS load balancing</span></span>  <br/> |
|<span data-ttu-id="d559c-173">硬件负载平衡器</span><span class="sxs-lookup"><span data-stu-id="d559c-173">Hardware load balancers</span></span>  <br/> |<span data-ttu-id="d559c-174">SQL Server 数据库</span><span class="sxs-lookup"><span data-stu-id="d559c-174">SQL Server databases</span></span>  <br/> |<span data-ttu-id="d559c-175">文件共享</span><span class="sxs-lookup"><span data-stu-id="d559c-175">File shares</span></span>  <br/> ||
   
## <a name="server-roles"></a><span data-ttu-id="d559c-176">服务器角色</span><span class="sxs-lookup"><span data-stu-id="d559c-176">Server roles</span></span>

<span data-ttu-id="d559c-177">运行 Business Server Skype 每台服务器运行一个或多个服务器角色。</span><span class="sxs-lookup"><span data-stu-id="d559c-177">Each server running Skype for Business Server runs one or more server roles.</span></span> <span data-ttu-id="d559c-178">服务器角色是一组业务服务器功能的服务器所提供的定义的 Skype。</span><span class="sxs-lookup"><span data-stu-id="d559c-178">A server role is a defined set of Skype for Business Server functionalities provided by that server.</span></span> <span data-ttu-id="d559c-179">无需在网络中部署所有可用服务器角色。</span><span class="sxs-lookup"><span data-stu-id="d559c-179">You don't need to deploy all available server roles in your network.</span></span> <span data-ttu-id="d559c-180">只安装包含您想要的功能的服务器角色。</span><span class="sxs-lookup"><span data-stu-id="d559c-180">Install only the server roles that contain the functionality that you want.</span></span>
  
<span data-ttu-id="d559c-181">对于大多数的服务器角色，可伸缩性和高可用性可以部署多台服务器的池运行相同的服务器角色的所有。</span><span class="sxs-lookup"><span data-stu-id="d559c-181">For most server roles, for scalability and high availability you can deploy pools of multiple servers all running the same server role.</span></span> <span data-ttu-id="d559c-182">池中的每台服务器必须运行一个或多个相同的服务器角色。</span><span class="sxs-lookup"><span data-stu-id="d559c-182">Each server in a pool must run an identical server role or roles.</span></span> <span data-ttu-id="d559c-183">对于大多数类型的 Skype 业务服务器中的池，则必须部署负载平衡器分布在池中的各个服务器之间的通信。</span><span class="sxs-lookup"><span data-stu-id="d559c-183">For most types of pools in Skype for Business Server, you must deploy a load balancer to spread traffic between the various servers in the pool.</span></span> <span data-ttu-id="d559c-184">Skype 业务服务器支持域名系统 (DNS) 负载平衡和硬件负载平衡器。</span><span class="sxs-lookup"><span data-stu-id="d559c-184">Skype for Business Server supports both Domain Name System (DNS) load balancing and hardware load balancers.</span></span>
  
### <a name="front-end-server-and-back-end-server"></a><span data-ttu-id="d559c-185">前端服务器和后端服务器</span><span class="sxs-lookup"><span data-stu-id="d559c-185">Front End Server and Back End Server</span></span>

<span data-ttu-id="d559c-186">对于业务 Server Enterprise Edition 的 Skype，在前端服务器是核心服务器角色，并运行许多基本 Skype 的业务服务器功能。</span><span class="sxs-lookup"><span data-stu-id="d559c-186">In Skype for Business Server Enterprise Edition, the Front End Server is the core server role, and runs many basic Skype for Business Server functions.</span></span> <span data-ttu-id="d559c-187">前端服务器、 后端服务器，以及是仅需要出现在任何 Skype 业务 Server Enterprise Edition 部署的服务器角色。</span><span class="sxs-lookup"><span data-stu-id="d559c-187">The Front End Server, along with the Back End Servers, are the only server roles required to be in any Skype for Business Server Enterprise Edition deployment.</span></span> 
  
<span data-ttu-id="d559c-188">前端池是一套前端服务器，配置相同，协同工作为公用组用户提供服务。</span><span class="sxs-lookup"><span data-stu-id="d559c-188">A Front End pool is a set of Front End Servers, configured identically, that work together to provide services for a common group of users.</span></span> <span data-ttu-id="d559c-189">由多个运行同一角色的服务器构成的池提供可伸缩性和故障转移功能。</span><span class="sxs-lookup"><span data-stu-id="d559c-189">A pool of multiple servers running the same role provides scalability and failover capability.</span></span>
  
<span data-ttu-id="d559c-190">前端服务器包括以下组件：</span><span class="sxs-lookup"><span data-stu-id="d559c-190">The Front End Server includes the following:</span></span>
  
- <span data-ttu-id="d559c-191">用户身份验证和注册。</span><span class="sxs-lookup"><span data-stu-id="d559c-191">User authentication and registration.</span></span>
    
- <span data-ttu-id="d559c-192">状态信息和联系人卡片交换。</span><span class="sxs-lookup"><span data-stu-id="d559c-192">Presence information and contact card exchange.</span></span>
    
- <span data-ttu-id="d559c-193">通讯簿服务和通讯组列表扩展。</span><span class="sxs-lookup"><span data-stu-id="d559c-193">Address book services and distribution list expansion.</span></span>
    
- <span data-ttu-id="d559c-194">IM 功能，包括多方 IM 会议。</span><span class="sxs-lookup"><span data-stu-id="d559c-194">IM functionality, including multiparty IM conferences.</span></span>
    
- <span data-ttu-id="d559c-195">Web 会议、PSTN 电话拨入式会议和 A/V 会议（如果部署）。</span><span class="sxs-lookup"><span data-stu-id="d559c-195">Web conferencing, PSTN Dial-in conferencing and A/V conferencing (if deployed).</span></span>
    
- <span data-ttu-id="d559c-196">将承载应用程序的业务服务器 （例如会议助理和响应组应用程序），包括与 Skype 的应用程序和第三方应用程序。</span><span class="sxs-lookup"><span data-stu-id="d559c-196">Application hosting, for both applications included with Skype for Business Server (for example, Conferencing Attendant and Response Group application), and third-party applications.</span></span>
    
- <span data-ttu-id="d559c-197">（可选）监控功能，用于以呼叫详细记录 (CDR) 和呼叫错误记录 (CER) 形式收集使用信息。</span><span class="sxs-lookup"><span data-stu-id="d559c-197">Optionally, Monitoring, to collect usage information in the form of call detail records (CDRs) and call error records (CERs).</span></span> <span data-ttu-id="d559c-198">此信息提供有关 （音频和视频） 的媒体质量指标遍历网络企业语音呼叫和 A / V 会议。</span><span class="sxs-lookup"><span data-stu-id="d559c-198">This information provides metrics about the quality of the media (audio and video) traversing your network for both Enterprise Voice calls and A/V conferences.</span></span>
    
- <span data-ttu-id="d559c-199">用于支持基于 Web 的任务的 Web 组件，如 Web 计划程序和联接启动器。</span><span class="sxs-lookup"><span data-stu-id="d559c-199">Web components to supported web-based tasks such as web scheduler and join launcher.</span></span>
    
- <span data-ttu-id="d559c-200">（可选）存档功能，用于存档 IM 通信和会议内容（出于合规性考虑）。</span><span class="sxs-lookup"><span data-stu-id="d559c-200">Optionally, Archiving, to archive IM communications and meeting content for compliance reasons.</span></span> <span data-ttu-id="d559c-201">有关详细信息，请参阅规划文档中的[Planning for Archiving](http://technet.microsoft.com/library/898b83c1-007b-43be-9484-08fe49c10951.aspx) 。</span><span class="sxs-lookup"><span data-stu-id="d559c-201">For details, see [Planning for Archiving](http://technet.microsoft.com/library/898b83c1-007b-43be-9484-08fe49c10951.aspx) in the Planning documentation.</span></span>
    
    <span data-ttu-id="d559c-202">在 Lync Server 2010 和早期版本中，监控和存档是两个单独的服务器角色，未并置在前端服务器上。</span><span class="sxs-lookup"><span data-stu-id="d559c-202">In Lync Server 2010 and prior versions, Monitoring and Archiving were separate server roles, not collocated on Front End Server.</span></span>
    
- <span data-ttu-id="d559c-203">（可选）如果启用持久聊天，则包括用于聊天室管理的持久聊天 Web 服务和用于文件上载/下载的持久聊天 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="d559c-203">Optionally, if Persistent chat is enabled, Persistent Chat Web Services for Chat Room Management and Persistent Chat Web Services for File Upload/Download.</span></span>
    
<span data-ttu-id="d559c-p120">前端池还是用户和会议数据的主存储。每个用户的相关信息将在池中的三个前端服务器之间复制，并将在后端服务器上进行备份。</span><span class="sxs-lookup"><span data-stu-id="d559c-p120">Front End Pools are also the primary store for user and conference data. Information about each user is replicated among three Front End Servers in the pool, and backed up on the Back End Servers.</span></span>
  
<span data-ttu-id="d559c-206">此外，一台前端服务器部署中也运行中央管理服务器，其管理和运行 Business Server Skype 的所有服务器部署基本配置数据。</span><span class="sxs-lookup"><span data-stu-id="d559c-206">Additionally, one Front End Server in the deployment also runs the Central Management Server, which manages and deploys basic configuration data to all servers running Skype for Business Server.</span></span> <span data-ttu-id="d559c-207">中央管理服务器还提供 Lync Server 命令行管理程序和文件传输功能。</span><span class="sxs-lookup"><span data-stu-id="d559c-207">The Central Management Server also provides Lync Server Management Shell and file transfer capabilities.</span></span>
  
<span data-ttu-id="d559c-208">后端服务器是运行 Microsoft SQL Server 提供的前端池的数据库服务的数据库服务器。</span><span class="sxs-lookup"><span data-stu-id="d559c-208">The Back End Servers are database servers running Microsoft SQL Server that provide the database services for the Front End pool.</span></span> <span data-ttu-id="d559c-209">后端服务器充当备份存储的池的用户和会议数据，并且其他数据库，如数据库响应组的主存储。</span><span class="sxs-lookup"><span data-stu-id="d559c-209">The Back End Servers serve as backup stores for the pool's user and conference data, and are the primary stores for other databases such as the Response Group database.</span></span> <span data-ttu-id="d559c-210">您可以将单个后端服务器，但为故障转移建议使用 SQL Server 镜像的解决方案。</span><span class="sxs-lookup"><span data-stu-id="d559c-210">You can have a single Back End Server, but a solution that uses SQL Server mirroring is recommended for failover.</span></span> <span data-ttu-id="d559c-211">后端服务器不会运行任何 Skype 业务服务器软件。</span><span class="sxs-lookup"><span data-stu-id="d559c-211">Back End Servers do not run any Skype for Business Server software.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="d559c-212">建议不要对业务服务器数据库与其他数据库并置 Skype。</span><span class="sxs-lookup"><span data-stu-id="d559c-212">We do not recommend collocating Skype for Business Server databases with other databases.</span></span> <span data-ttu-id="d559c-213">如果您这样做，可能会影响可用性和性能。</span><span class="sxs-lookup"><span data-stu-id="d559c-213">If you do so, availability and performance may be affected.</span></span> 
  
<span data-ttu-id="d559c-214">存储在后端服务器数据库中的信息包括状态信息、用户的联系人列表、包含所有当前会议状态相关的永久数据的会议数据，以及会议安排数据。</span><span class="sxs-lookup"><span data-stu-id="d559c-214">Information stored in the Back End Server databases includes presence information, users' Contacts lists, conferencing data, including persistent data about the state of all current conferences, and conference scheduling data.</span></span>
  
### <a name="edge-server"></a><span data-ttu-id="d559c-215">边缘服务器</span><span class="sxs-lookup"><span data-stu-id="d559c-215">Edge Server</span></span>

<span data-ttu-id="d559c-216">边缘服务器，您的用户进行通信和协作与组织的防火墙之外的用户。</span><span class="sxs-lookup"><span data-stu-id="d559c-216">Edge Server enables your users to communicate and collaborate with users outside the organization's firewalls.</span></span> <span data-ttu-id="d559c-217">这些外部用户可以包括目前使用非现场、 来自联盟的伙伴组织的用户和外部用户的已被邀请加入您 Skype 业务服务器部署上承载的会议的组织的用户。</span><span class="sxs-lookup"><span data-stu-id="d559c-217">These external users can include the organization's own users who are currently working offsite, users from federated partner organizations, and outside users who have been invited to join conferences hosted on your Skype for Business Server deployment.</span></span>
  
<span data-ttu-id="d559c-218">部署边缘服务器还允许 mobility service 的移动设备上支持 Lync 功能。</span><span class="sxs-lookup"><span data-stu-id="d559c-218">Deploying Edge Server also enables mobility services, which supports Lync functionality on mobile devices.</span></span> <span data-ttu-id="d559c-219">用户可以使用受支持的 Apple iOS、Android、Windows Phone 或 Nokia 移动设备来执行发送和接收即时消息、查看联系人和查看状态等活动。</span><span class="sxs-lookup"><span data-stu-id="d559c-219">Users can use supported Apple iOS, Android, Windows Phone, or Nokia mobile devices to perform activities such as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span> <span data-ttu-id="d559c-220">此外，移动设备支持某些企业语音功能，例如单击加入会议，通过工作，一号通，语音邮件的呼叫和错过的呼叫。</span><span class="sxs-lookup"><span data-stu-id="d559c-220">In addition, mobile devices support some Enterprise Voice features, such as click to join a conference, Call via Work, single number reach, voice mail, and missed calls.</span></span> <span data-ttu-id="d559c-221">移动功能还支持的不支持在后台运行的应用程序的移动设备的推送通知。</span><span class="sxs-lookup"><span data-stu-id="d559c-221">The mobility feature also supports push notifications for mobile devices that do not support applications running in the background.</span></span> <span data-ttu-id="d559c-222">推送通知是一类发送给移动设备的有关当移动设备处于不活动状态时发生的事件的通知。</span><span class="sxs-lookup"><span data-stu-id="d559c-222">A push notification is a notification that is sent to a mobile device about an event that occurs while a mobile application is inactive.</span></span>
  
<span data-ttu-id="d559c-223">边缘服务器还包括完全集成的可扩展消息传递和状态协议 (XMPP) 代理，以及前端服务器上包含的 XMPP 网关。</span><span class="sxs-lookup"><span data-stu-id="d559c-223">Edge Servers also include a fully-integrated Extensible Messaging and Presence Protocol (XMPP) proxy, with an XMPP gateway included on Front End Servers.</span></span> <span data-ttu-id="d559c-224">您可以配置这些 XMPP 组件，才能启用业务 Server 用户您 Skype 即时消息和状态为从基于 XMPP 的合作伙伴添加联系人。</span><span class="sxs-lookup"><span data-stu-id="d559c-224">You can configure these XMPP components to enable your Skype for Business Server users to add contacts from XMPP-based partners for instant messaging and presence.</span></span>
  
### <a name="mediation-server"></a><span data-ttu-id="d559c-225">中介服务器</span><span class="sxs-lookup"><span data-stu-id="d559c-225">Mediation Server</span></span>

<span data-ttu-id="d559c-226">中介服务器是用于实现企业语音、 呼叫通过单位电话和电话拨入式会议的必需组件。</span><span class="sxs-lookup"><span data-stu-id="d559c-226">Mediation Server is a necessary component for implementing Enterprise Voice, Call Via Work, and dial-in conferencing.</span></span> <span data-ttu-id="d559c-227">中介服务器转换信号，以及在某些配置，您内部 Skype Business Server 基础结构之间的媒体和公共交换电话交换网 (PSTN) 网关、 IP-PBX 或会话初始协议 (SIP) 中继。</span><span class="sxs-lookup"><span data-stu-id="d559c-227">Mediation Server translates signaling, and, in some configurations, media between your internal Skype for Business Server infrastructure and a public switched telephone network (PSTN) gateway, IP-PBX, or a Session Initiation Protocol (SIP) trunk.</span></span> <span data-ttu-id="d559c-228">您可以运行中介服务器并置在前端服务器所在的服务器上或分为独立的中介服务器池。</span><span class="sxs-lookup"><span data-stu-id="d559c-228">You can run Mediation Server collocated on the same server as Front End Server, or separated into a stand-alone Mediation Server pool.</span></span>
  
<span data-ttu-id="d559c-229">有关详细信息，请参阅[中的业务服务器 2015 Skype 的中介服务器组件](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md)。</span><span class="sxs-lookup"><span data-stu-id="d559c-229">For details, see [Mediation Server component in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md).</span></span>
  
### <a name="video-interop-server"></a><span data-ttu-id="d559c-230">视频互操作服务器</span><span class="sxs-lookup"><span data-stu-id="d559c-230">Video Interop Server</span></span>

<span data-ttu-id="d559c-231">视频互操作服务器中的业务服务器 2015 Skype 的一个新角色。</span><span class="sxs-lookup"><span data-stu-id="d559c-231">Video Interop Server is a new role in Skype for Business Server 2015.</span></span> <span data-ttu-id="d559c-232">使您可以将您的业务服务器部署的 Skype 集成使用某些第三方 VTC （视频电话会议系统） 解决方案。</span><span class="sxs-lookup"><span data-stu-id="d559c-232">It enables you to integrate your Skype for Business Server deployment with certain third-party VTC (Video Teleconferencing System) solutions.</span></span> <span data-ttu-id="d559c-233">VIS 作为中介的第三方电话会议系统和 Skype 业务服务器部署。</span><span class="sxs-lookup"><span data-stu-id="d559c-233">A VIS acts as an intermediary between a 3rd party teleconference system and a Skype for Business Server deployment.</span></span> <span data-ttu-id="d559c-234">对于此版本，VIS 着重实现了与 Cisco/Tandberg 视频系统之间的互操作性。</span><span class="sxs-lookup"><span data-stu-id="d559c-234">For this release, VIS is focused on interoperability with Cisco/Tandberg video systems.</span></span>
  
<span data-ttu-id="d559c-235">有关详细信息，请参阅[规划视频中的业务服务器 2015 Skype 的互操作服务器](../../plan-your-deployment/video-interop-server.md)。</span><span class="sxs-lookup"><span data-stu-id="d559c-235">For details, see [Plan for Video Interop Server in Skype for Business Server 2015](../../plan-your-deployment/video-interop-server.md).</span></span>
  
### <a name="director"></a><span data-ttu-id="d559c-236">控制器</span><span class="sxs-lookup"><span data-stu-id="d559c-236">Director</span></span>

<span data-ttu-id="d559c-237">控制器可以对进行身份验证 Skype 企业服务器用户请求，但它们不承载用户帐户，或者提供状态或会议服务。</span><span class="sxs-lookup"><span data-stu-id="d559c-237">Directors can authenticate Skype for Business Server user requests, but they do not home user accounts or provide presence or conferencing services.</span></span> <span data-ttu-id="d559c-238">控制器对于增强支持外部用户访问的部署中的安全性最有用。</span><span class="sxs-lookup"><span data-stu-id="d559c-238">Directors are most useful to enhance security in deployments that enable external user access.</span></span> <span data-ttu-id="d559c-239">控制器可在将请求发送到内部服务器之前对请求进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="d559c-239">The Director can authenticate requests before sending them on to internal servers.</span></span> <span data-ttu-id="d559c-240">对于拒绝服务攻击，此攻击将终止于控制器且无法到达前端服务器。</span><span class="sxs-lookup"><span data-stu-id="d559c-240">In the case of a denial-of-service attack, the attack ends with the Director and does not reach the Front End servers.</span></span>
  
### <a name="persistent-chat-server-roles"></a><span data-ttu-id="d559c-241">持久聊天服务器角色</span><span class="sxs-lookup"><span data-stu-id="d559c-241">Persistent Chat Server Roles</span></span>

<span data-ttu-id="d559c-p130">利用持久聊天，用户可以参加持续进行的、基于主题的多方对话。持久聊天前端服务器可运行持久聊天服务。持久聊天后端服务器可存储聊天历史记录数据以及有关类别和聊天室的信息。可选持久聊天合规性后端服务器可存储聊天内容和合规性事件以实现合规性。</span><span class="sxs-lookup"><span data-stu-id="d559c-p130">Persistent chat enables users to participate in multiparty, topic-based conversations that persist over time. The Persistent Chat Front End Server runs the persistent chat service. The Persistent Chat Back End Server stores the chat history data, and information about categories and chat rooms. The optional Persistent Chat Compliance Back End Server can store the chat content and compliance events for the purpose of compliance.</span></span>
  
<span data-ttu-id="d559c-246">运行 Skype 的业务 Server Standard Edition 还可以运行持久聊天服务器并置在同一台服务器上。</span><span class="sxs-lookup"><span data-stu-id="d559c-246">Servers running Skype for Business Server Standard Edition can also run Persistent chat collocated on the same server.</span></span> <span data-ttu-id="d559c-247">不能将持久聊天前端服务器与 Enterprise Edition 前端服务器并置。</span><span class="sxs-lookup"><span data-stu-id="d559c-247">You cannot collocate the Persistent Chat Front End Server with Enterprise Edition Front End Server.</span></span>
  
<span data-ttu-id="d559c-248">有关详细信息，请参阅[Plan for Persistent Chat Server in Skype 的业务服务器 2015年](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)。</span><span class="sxs-lookup"><span data-stu-id="d559c-248">For details, see [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).</span></span>
  
## <a name="high-availability-and-disaster-recovery-support"></a><span data-ttu-id="d559c-249">高可用性和灾难恢复支持</span><span class="sxs-lookup"><span data-stu-id="d559c-249">High availability and disaster recovery support</span></span>

<span data-ttu-id="d559c-250">Skype 业务服务器的服务器冗余性通过池提供高可用性。</span><span class="sxs-lookup"><span data-stu-id="d559c-250">Skype for Business Server provides high availability by server redundancy via pooling.</span></span> <span data-ttu-id="d559c-251">如果运行特定服务器角色的服务器发生故障，则池中运行相同角色的其他服务器将承担该服务器的负载。</span><span class="sxs-lookup"><span data-stu-id="d559c-251">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="d559c-252">这适用于前端服务器、边缘服务器、中介服务器和控制器。</span><span class="sxs-lookup"><span data-stu-id="d559c-252">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span>
  
<span data-ttu-id="d559c-253">Skype 业务服务器还提供了灾难恢复度量值通过启用池配对。</span><span class="sxs-lookup"><span data-stu-id="d559c-253">Skype for Business Server also provides disaster recovery measures by enabling pool pairing.</span></span> <span data-ttu-id="d559c-254">如果您部署了此拓扑，则将指定前端池对，对中的每个池位于不同地理区域的不同数据中心。</span><span class="sxs-lookup"><span data-stu-id="d559c-254">If you deploy this topology, you will designate pairs of Front End pools, with each pool in a pair located in a separate data center, and in a separate geographical area.</span></span> <span data-ttu-id="d559c-255">如果一个池或一个站点不可用，则可将该池中的用户重定向至使用对中的其他池，并且对服务的干扰程度可以忽略不计。</span><span class="sxs-lookup"><span data-stu-id="d559c-255">If one pool or site goes down, you can redirect the users of that pool to use the other pool in the pair, with minimal interruption of service.</span></span>
  
<span data-ttu-id="d559c-256">Skype 业务 server 还支持后端服务器高可用性的几个选项。</span><span class="sxs-lookup"><span data-stu-id="d559c-256">Skype for Business Server also supports several options for Back End Server high availability.</span></span> <span data-ttu-id="d559c-257">其中包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="d559c-257">These include the following:</span></span>
  
- <span data-ttu-id="d559c-258">数据库镜像</span><span class="sxs-lookup"><span data-stu-id="d559c-258">Database mirroring</span></span>
    
- <span data-ttu-id="d559c-259">AlwaysOn 可用性组</span><span class="sxs-lookup"><span data-stu-id="d559c-259">AlwaysOn Availability Groups</span></span>
    
- <span data-ttu-id="d559c-260">AlwaysOn 故障转移集群实例 (FCI)</span><span class="sxs-lookup"><span data-stu-id="d559c-260">AlwaysOn Failover Cluster Instances (FCI)</span></span>
    
- <span data-ttu-id="d559c-261">SQL 故障转移群集</span><span class="sxs-lookup"><span data-stu-id="d559c-261">SQL failover clustering</span></span>
    
<span data-ttu-id="d559c-262">有关池配对和后端服务器高可用性的详细信息，请参阅[规划高可用性和灾难恢复的业务服务器 2015 Skype 中](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。</span><span class="sxs-lookup"><span data-stu-id="d559c-262">For details about pool pairing and Back End Server high availability, see [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  
## <a name="server-collocation-in-skype-for-business-server-2015"></a><span data-ttu-id="d559c-263">Skype 中的业务服务器 2015年的服务器并置</span><span class="sxs-lookup"><span data-stu-id="d559c-263">Server collocation in Skype for Business Server 2015</span></span>

<span data-ttu-id="d559c-264">我们使用术语将并置，但这意味着什么？</span><span class="sxs-lookup"><span data-stu-id="d559c-264">We've used the term collocate already, but what does this mean?</span></span> <span data-ttu-id="d559c-265">Skype 的业务服务器 2015年使您可以在同一服务器上，这是并置，或在不同服务器上定位某些服务器角色和功能，但它可以是令人费解何时您刚开始出，以及是否正在制作 Standard Edition 或 Enterprise Edition服务器部署 （每个附带于自己的规则）。</span><span class="sxs-lookup"><span data-stu-id="d559c-265">Skype for Business Server 2015 allows you to locate some server roles and features on the same server, which is collocation, or on different servers, but it can be confusing when you're starting out, and whether you're doing a Standard Edition or Enterprise Edition server deployment (they each come with their own rules).</span></span> <span data-ttu-id="d559c-266">为了帮助您规划，之所以包括服务器并置在 Standard Edition 服务器部署，Enterprise Edition 前端池部署 （在大多数情况下此信息是相同的并且其中它是不同的它调用专门）。</span><span class="sxs-lookup"><span data-stu-id="d559c-266">To help with your planning, we're including server collocation in Standard Edition server deployments and Enterprise Edition Front End pool deployments (in most cases this information is identical, and where it's different, it's called out specifically).</span></span>
  
### <a name="collocation-of-server-roles"></a><span data-ttu-id="d559c-267">服务器角色的并置</span><span class="sxs-lookup"><span data-stu-id="d559c-267">Collocation of server roles</span></span>

<span data-ttu-id="d559c-268">Standard Edition server 具有以下角色并置在一起 （其他配置为需要上述），在 Enterprise Edition 前端池中，此角色可以并置，或部署到单独的服务器：</span><span class="sxs-lookup"><span data-stu-id="d559c-268">The Standard Edition server has the following role collocated (additional configuration is required though), while in the Enterprise Edition Front End pool, this role can be collocated, or deployed to a separate server:</span></span>
  
- <span data-ttu-id="d559c-269">中介</span><span class="sxs-lookup"><span data-stu-id="d559c-269">Mediation</span></span>
    
<span data-ttu-id="d559c-270">以下服务器角色必须分别部署在不同的服务器上：</span><span class="sxs-lookup"><span data-stu-id="d559c-270">These server roles must each be deployed on a separate server:</span></span>
  
- <span data-ttu-id="d559c-271">控制器</span><span class="sxs-lookup"><span data-stu-id="d559c-271">Director</span></span>
    
- <span data-ttu-id="d559c-272">Edge</span><span class="sxs-lookup"><span data-stu-id="d559c-272">Edge</span></span>
    
- <span data-ttu-id="d559c-273">视频互操作服务器</span><span class="sxs-lookup"><span data-stu-id="d559c-273">Video Interop Server</span></span>
    
- <span data-ttu-id="d559c-274">Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="d559c-274">Office Web Apps</span></span>
    
### <a name="databases"></a><span data-ttu-id="d559c-275">数据库</span><span class="sxs-lookup"><span data-stu-id="d559c-275">Databases</span></span>

<span data-ttu-id="d559c-276">这是实际区别 Standard Edition 服务器部署，Enterprise Edition server 池部署中，区域，因此我们将有两个部分下面，同后跟某些其他规则。</span><span class="sxs-lookup"><span data-stu-id="d559c-276">This is the area with real differences between Standard Edition server deployments and Enterprise Edition server pool deployments, so we'll have two sections below, followed by some additional rules for both.</span></span>
  
#### <a name="standard"></a><span data-ttu-id="d559c-277">Standard</span><span class="sxs-lookup"><span data-stu-id="d559c-277">Standard</span></span>

<span data-ttu-id="d559c-278">由于 SQL Server Express 已并置在 Standard Edition 服务器上，并且不能移动，这是相当简单。</span><span class="sxs-lookup"><span data-stu-id="d559c-278">Since SQL Server Express is collocated on the Standard Edition server, and can't be moved, this is pretty straightforward.</span></span> <span data-ttu-id="d559c-279">此外，如果您在 Standard Edition server 上部署持久聊天服务器，您还可以将持久聊天和 Standard Edition server 上的持久聊天合规性数据库并置，但您没有。</span><span class="sxs-lookup"><span data-stu-id="d559c-279">Furthermore, if you deploy Persistent Chat Server on a Standard Edition server, you're also able to collocate the Persistent Chat and the Persistent Chat compliance database on the Standard Edition server too, but you don't have to.</span></span>
  
<span data-ttu-id="d559c-280">这些不能并置在 Standard Edition 服务器上，但可以继续在自己的一台数据库服务器上：</span><span class="sxs-lookup"><span data-stu-id="d559c-280">These can't be collocated on the Standard Edition server, but can go on a single database server of their own:</span></span>
  
- <span data-ttu-id="d559c-281">监控数据库</span><span class="sxs-lookup"><span data-stu-id="d559c-281">Monitoring database</span></span>
    
- <span data-ttu-id="d559c-282">存档数据库</span><span class="sxs-lookup"><span data-stu-id="d559c-282">Archiving database</span></span>
    
- <span data-ttu-id="d559c-283">对于 Enterprise Edition 前端池的任何后端数据库</span><span class="sxs-lookup"><span data-stu-id="d559c-283">Any back-end database for an Enterprise Edition Front End pool</span></span>
    
#### <a name="enterprise"></a><span data-ttu-id="d559c-284">Enterprise</span><span class="sxs-lookup"><span data-stu-id="d559c-284">Enterprise</span></span>

<span data-ttu-id="d559c-285">以下数据库可以并置在相同的后端 SQL Server 上：</span><span class="sxs-lookup"><span data-stu-id="d559c-285">The following databases can be collocated on the same back end SQL Server:</span></span>
  
- <span data-ttu-id="d559c-286">后端数据库</span><span class="sxs-lookup"><span data-stu-id="d559c-286">Back End database</span></span>
    
- <span data-ttu-id="d559c-287">监控数据库</span><span class="sxs-lookup"><span data-stu-id="d559c-287">Monitoring database</span></span>
    
- <span data-ttu-id="d559c-288">存档数据库</span><span class="sxs-lookup"><span data-stu-id="d559c-288">Archiving database</span></span>
    
- <span data-ttu-id="d559c-289">持久聊天数据库</span><span class="sxs-lookup"><span data-stu-id="d559c-289">Persistent Chat database</span></span>
    
- <span data-ttu-id="d559c-290">持久聊天合规性数据库</span><span class="sxs-lookup"><span data-stu-id="d559c-290">Persistent Chat compliance database</span></span>
    
#### <a name="both"></a><span data-ttu-id="d559c-291">两者</span><span class="sxs-lookup"><span data-stu-id="d559c-291">Both</span></span>

<span data-ttu-id="d559c-292">现在，有其他一些并置在单一的 SQL 实例，或在同一 SQL Server 数据库中的多个 SQL 实例中的业务服务器 2015年数据库的 Skype 时应遵循的规则：</span><span class="sxs-lookup"><span data-stu-id="d559c-292">Now, there are some additional rules to follow when collocating Skype for Business Server 2015 databases in a single SQL instance, or in multiple SQL instances in the same SQL Server database:</span></span>
  
- <span data-ttu-id="d559c-293">每个 SQL 实例只能包含单个后端数据库的 Enterprise Edition 前端池、 一个监控数据库、 一个存档数据库、 一个持久聊天数据库和单个持久聊天合规性数据库。</span><span class="sxs-lookup"><span data-stu-id="d559c-293">Each SQL instance can only contain a single back end database for an Enterprise Edition Front End pool, a single Monitoring database, a single Archiving database, a single Persistent Chat database, and a single Persistent Chat compliance database.</span></span>
    
- <span data-ttu-id="d559c-294">数据库服务器不支持多个 Enterprise Edition 前端池、 一台服务器运行存档，一台服务器运行监控、 一个持久聊天数据库和单个持久聊天合规性数据库，但它可以支持的每个，一个无论是否数据库使用相同的 SQL Server 实例或单独的 SQL Server 实例。</span><span class="sxs-lookup"><span data-stu-id="d559c-294">The database server can't support more than one Enterprise Edition Front End pool, one server running Archiving, one server running Monitoring, a single Persistent Chat database, and a single Persistent Chat compliance database, but it can support one of each, regardless of whether the databases use the same instance of SQL Server or separate instances of SQL Server.</span></span>
    
### <a name="file-shares"></a><span data-ttu-id="d559c-295">文件共享</span><span class="sxs-lookup"><span data-stu-id="d559c-295">File shares</span></span>

<span data-ttu-id="d559c-296">文件共享可以是在独立的服务器上，您也可以将其并置到与以下任何或所有组件相同的服务器上：</span><span class="sxs-lookup"><span data-stu-id="d559c-296">The file share can be on a separate server, or you can collocate it on the same server as any or all of the following:</span></span>
  
- <span data-ttu-id="d559c-297">数据库服务器，包括 Enterprise Edition 前端池的后端服务器</span><span class="sxs-lookup"><span data-stu-id="d559c-297">Database server, including the Back End Server of an Enterprise Edition Front End pool</span></span>
    
- <span data-ttu-id="d559c-298">监控数据库</span><span class="sxs-lookup"><span data-stu-id="d559c-298">Monitoring database</span></span>
    
- <span data-ttu-id="d559c-299">存档数据库</span><span class="sxs-lookup"><span data-stu-id="d559c-299">Archiving database</span></span>
    
- <span data-ttu-id="d559c-300">持久聊天数据库</span><span class="sxs-lookup"><span data-stu-id="d559c-300">Persistent Chat database</span></span>
    
- <span data-ttu-id="d559c-301">持久聊天合规性数据库</span><span class="sxs-lookup"><span data-stu-id="d559c-301">Persistent Chat compliance database</span></span>
    
> [!CAUTION]
> <span data-ttu-id="d559c-p137">请注意，虽然可以在这些服务器上并置文件共享，但是有必要指出的是，我们不建议这样做。如果将文件共享与任何其他服务器角色并置，请确保经常监视磁盘空间和性能问题。</span><span class="sxs-lookup"><span data-stu-id="d559c-p137">Note that while you can collocate the file share on these servers, it's vital to note that we don't recommend it. If you'd collocating the file share with any other server role, please make sure you're monitoring for disk space and performance issues on a regular basis.</span></span> 
  
### <a name="keep-in-mind"></a><span data-ttu-id="d559c-304">请注意</span><span class="sxs-lookup"><span data-stu-id="d559c-304">Keep in mind</span></span>

- <span data-ttu-id="d559c-305">不能并置反向代理服务器，其中不业务服务器 2015年组件 Skype 和甚至可能不是在拓扑中。</span><span class="sxs-lookup"><span data-stu-id="d559c-305">You can't collocate a reverse proxy server, which isn't a Skype for Business Server 2015 component, and may not even be in your topology.</span></span> <span data-ttu-id="d559c-306">如果您想要支持共享的联盟用户，以及其他许多内容的 web 内容，您将需要反向代理。</span><span class="sxs-lookup"><span data-stu-id="d559c-306">You'll need a reverse proxy if you want to support sharing of web content for federated users, among many other things.</span></span> <span data-ttu-id="d559c-307">如果需要继续操作，并通过配置现有反向代理服务器已经是您正在使用其他应用程序的组织中实现业务服务器 2015 Skype 的反向代理支持。</span><span class="sxs-lookup"><span data-stu-id="d559c-307">If you need to, go ahead and implement reverse proxy support for Skype for Business Server 2015 by configuring an existing reverse proxy server that's already in your organization that's being used by other applications.</span></span>
    
- <span data-ttu-id="d559c-308">您不能并置任何 Exchange UM 组件或 SharePoint Server 组件与任何 Skype 业务服务器 2015年角色。</span><span class="sxs-lookup"><span data-stu-id="d559c-308">You can't collocate any Exchange UM component or SharePoint Server component with any Skype for Business Server 2015 role.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="d559c-309">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d559c-309">See also</span></span>

[<span data-ttu-id="d559c-310">为业务服务器 2015 Skype 的参考拓扑</span><span class="sxs-lookup"><span data-stu-id="d559c-310">Reference topologies for Skype for Business Server 2015</span></span>](reference-topologies.md)