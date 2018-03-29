---
title: Skype for Business Server 2015 的拓扑基础知识
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 113e8c3f-71de-435c-bc4a-918ac7b50008
description: 摘要： 为业务服务器 2015 Skype 选择您的拓扑结构。 了解有关服务器配置的 Skype 业务服务器 2015年个。
ms.openlocfilehash: 5fbb6a490f8ba35d2e16ccbab60a17d788cb92e8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="topology-basics-for-skype-for-business-server-2015"></a><span data-ttu-id="e5b5a-104">Skype for Business Server 2015 的拓扑基础知识</span><span class="sxs-lookup"><span data-stu-id="e5b5a-104">Topology Basics for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="e5b5a-p102">**摘要：**为 Skype for Business Server 2015 选择拓扑。了解 Skype for Business Server 2015 的服务器并置。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-p102">**Summary:** Choose your topology for Skype for Business Server 2015. Learn about server collocation for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="e5b5a-107">之前准备任何其他操作时，您需要知道您打算为适当的拓扑部署的 Skype 的业务服务器 2015年。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-107">Before preparing anything else, you'll want to know you're planning for the right topology for your deployment of Skype for Business Server 2015.</span></span> <span data-ttu-id="e5b5a-108">您需要确定的第一件事是如果您将具有的业务服务器 2015，Skype 的内部部署或如果您打算将这与 Skype 业务服务器在线混合部署中部署结合起来。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-108">The first thing you need to decide is if you're going to have an on-premises deployment of Skype for Business Server 2015, or if you're going to combine this with a Skype for Business Server Online deployment in a Hybrid deployment.</span></span> <span data-ttu-id="e5b5a-109">要想要读更多，无论如何，我们会详细的内部拓扑，在这里，但混合详细信息记录在各自的部分。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-109">Either way, you're going to want to read further, as we'll detail the on-premises topologies here, but the Hybrid details are documented in their own section.</span></span>
  
<span data-ttu-id="e5b5a-110">您还可以查看[业务服务器 2015年的 Skype 的引用拓扑](reference-topologies.md)中的一些示例拓扑。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-110">You can also see some example topologies in [Reference topologies for Skype for Business Server 2015](reference-topologies.md).</span></span>
  
## <a name="sites"></a><span data-ttu-id="e5b5a-111">站点</span><span class="sxs-lookup"><span data-stu-id="e5b5a-111">Sites</span></span>

<span data-ttu-id="e5b5a-112">在 Skype 业务服务器，网络业务服务器组件中包含 Skype 上定义站点。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-112">In Skype for Business Server, you define sites on your network that contain Skype for Business Server components.</span></span> <span data-ttu-id="e5b5a-113">站点是一组由高速度、低延迟网络（例如，单个局域网 (LAN) 或由高速光纤网络连接的两个网络）完美连接的计算机。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-113">A site is a set of computers that is well-connected by a high-speed, low-latency network, such as a single local area network (LAN) or two networks connected by a high-speed fiber optic network.</span></span> <span data-ttu-id="e5b5a-114">请注意，Skype 业务服务器站点的 Active Directory 域服务网站和 Microsoft Exchange Server 网站的一个单独概念。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-114">Note that Skype for Business Server sites are a separate concept from Active Directory Domain Services sites and Microsoft Exchange Server sites.</span></span> <span data-ttu-id="e5b5a-115">您的业务服务器站点的 Skype 不需要对应于 Active Directory 站点。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-115">Your Skype for Business Server sites do not need to correspond to your Active Directory sites.</span></span>
  
<span data-ttu-id="e5b5a-116">Skype 的业务服务器 2015年支持一个或多个站点都可以根据您的高可用性和位置要求扩展到内部部署。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-116">Skype for Business Server 2015 supports on-premises deployment of one or more sites that can be scaled according to your high availability and location requirements.</span></span>
  
<span data-ttu-id="e5b5a-117">部署将具有至少一个中心站点 （也称为数据中心，这是位于它的所有服务器的数据中心），而您的部署中每个中央站点将有一个标准版服务器或至少一个前端企业版池。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-117">Your deployment will have at least one central site (also called a datacenter, this is a datacenter for all the servers located in it), and each central site in your deployment will have one Standard Edition server, or at least one Enterprise Edition Front End pool.</span></span> <span data-ttu-id="e5b5a-118">您可以在以下每个选项中了解其中的差异：</span><span class="sxs-lookup"><span data-stu-id="e5b5a-118">You can see the differences in each option below:</span></span>
  
- <span data-ttu-id="e5b5a-119">标准版服务器包括并入的 SQL Server Express 数据库。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-119">Standard Edition server includes a collocated SQL Server Express database.</span></span>
    
- <span data-ttu-id="e5b5a-120">企业版前端池包括：</span><span class="sxs-lookup"><span data-stu-id="e5b5a-120">Enterprise Edition Front End pool includes:</span></span>
    
  - <span data-ttu-id="e5b5a-121">一个或多个前端服务器 （理想情况下至少三个，对于可扩展性），最多十二个。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-121">One or more Front End Servers (Ideally at least three, for scalability), with a maximum of twelve.</span></span> <span data-ttu-id="e5b5a-122">对于多个服务器，需要提供负载平衡。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-122">Load-balancing would be required for more than one server.</span></span>
    
  - <span data-ttu-id="e5b5a-123">不同后端服务器。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-123">A separate Back End Server.</span></span>
    
<span data-ttu-id="e5b5a-124">您可以在此部分了解有关各种服务器角色的更多信息。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-124">You can learn more about the various server roles a little later in this section.</span></span>
  
<span data-ttu-id="e5b5a-125">除了中央站点，可能也都有与中心站点关联的一个或多个分支站点。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-125">In addition to your central sites, you may also end up having one or more branch sites associated with your central site.</span></span> <span data-ttu-id="e5b5a-126">它们取决于在中心网站上几乎其所有的功能，为因此他们组成的完全是什么？</span><span class="sxs-lookup"><span data-stu-id="e5b5a-126">They depend on the central site for almost all their functionality, so what are they made up of, exactly?</span></span>
  
- <span data-ttu-id="e5b5a-127">高存活力分支装置，将公用交换的电话网络 (PSTN) 网关，与某些 Skype 业务服务器 2015年功能结合起来。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-127">Survivable Branch Appliance, which combines a public switched telephone network (PSTN) gateway, with some Skype for Business Server 2015 functionality.</span></span>
    
- <span data-ttu-id="e5b5a-128">自动恢复分支服务器，则运行 Windows 服务器具有的业务服务器 2015年注册商和中介服务器软件安装 Skype 的服务器。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-128">Survivable Branch Server, it's a server running Windows Server that has Skype for Business Server 2015 Registrar and Mediation Server software installed.</span></span>
    
- <span data-ttu-id="e5b5a-129">独立 PSTN 网关 （这并不是高存活力的分支装置的一部分）。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-129">Stand-alone PSTN gateway (which isn't part of the Survivable Branch Appliance).</span></span>
    
- <span data-ttu-id="e5b5a-130">独立的中介服务器或独立的中介服务器池 （如果您不想与高存活力的分支装置布置此角色）。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-130">Stand-alone Mediation Server or stand-alone Mediation Server pool (if you don't want to collocate this role with the Survivable Branch Appliance).</span></span>
    
## <a name="whats-in-a-skype-for-business-server-site"></a><span data-ttu-id="e5b5a-131">在 Skype 业务服务器网站是什么？</span><span class="sxs-lookup"><span data-stu-id="e5b5a-131">What's in a Skype for Business Server site?</span></span>

<span data-ttu-id="e5b5a-132">若要添加更多细节，中央站点还可以：</span><span class="sxs-lookup"><span data-stu-id="e5b5a-132">To get into more detail, a central site can also have:</span></span>
  
- <span data-ttu-id="e5b5a-133">多个前端池，在同一个域或其他域 （记住在规划所有前端服务器前端池中，以及为池后端服务器不必在同一个域中）。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-133">Multiple Front End pools, in the same domain or different domains (remember in planning that all the Front End Servers in a Front End pool, along with the Back End Servers for the pool, do have to be in the same domain).</span></span>
    
- <span data-ttu-id="e5b5a-134">多个标准版服务器。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-134">Multiple Standard Edition servers.</span></span>
    
- <span data-ttu-id="e5b5a-135">Office Web 应用程序服务器，用于在 Skype 的 Office Web 应用程序与业务服务器 2015年共享和呈现的 PowerPoint 演示文稿。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-135">Office Web Apps Server, which is used with Office Web Apps in Skype for Business Server 2015 for sharing and rendering of PowerPoint presentations.</span></span>
    
- <span data-ttu-id="e5b5a-136">边缘服务器或边池 （在外围网络）。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-136">Edge Server or Edge pool (in a perimeter network).</span></span> <span data-ttu-id="e5b5a-137">如果希望部署支持联盟伙伴、公共 IM 连接、可扩展消息传递和状态协议 (XMPP) 网关以及远程用户访问，则需要此组件。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-137">Needed if you want your deployment to support federated partners, public IM connectivity, extensible messaging and presence protocol (XMPP) gateway, and remote user access.</span></span> <span data-ttu-id="e5b5a-138">边缘服务器规划文档中找不到更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-138">More details can be found in the Edge Server Planning documentation.</span></span>
    
- <span data-ttu-id="e5b5a-139">持久的聊天服务器。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-139">Persistent Chat Server.</span></span> <span data-ttu-id="e5b5a-140">如果您希望用户能够参与多方、基于主题的持久对话，则此组件将提供帮助。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-140">Useful if you want users to be able to take part in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="e5b5a-141">没有在持久聊天服务器主题规划的详细信息。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-141">There's more information at the Planning for Persistent Chat Server topic.</span></span>
    
- <span data-ttu-id="e5b5a-142">监控。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-142">Monitoring.</span></span> <span data-ttu-id="e5b5a-143">用于支持数据收集的音频/视频 (A / V) 体验质量 (QoE) 和呼叫详细记录 (CDR) 企业语音和 A / V 会议中部署。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-143">Used to support data collection for audio/video (A/V) Quality of Experience (QoE) and call detail recording (CDR) for Enterprise Voice and A/V conferences in your deployment.</span></span> <span data-ttu-id="e5b5a-144">我们将在“规划监控”主题中详细谈论这一内容。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-144">We discuss it in detail at the Planning for Monitoring topic.</span></span>
    
- <span data-ttu-id="e5b5a-145">总监或总监池。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-145">Director or Director pool.</span></span> <span data-ttu-id="e5b5a-146">如果不需要，但有用要提高可恢复性并使 Skype 业务 2015年到用户的主池的用户请求的重定向。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-146">Not required, but useful if you want to improve resiliency and enable redirection of Skype for Business 2015 user requests to the user's home pool.</span></span> <span data-ttu-id="e5b5a-147">如果您要部署控制器，支持最多，每个池的 10 个。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-147">If you want to deploy Directors, a maximum of 10 per pool is supported.</span></span> <span data-ttu-id="e5b5a-148">如果这是您需要的内容，明确董事主题规划在继续阅读。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-148">If this is something you need, definitely continue reading at the Planning for Directors topic.</span></span>
    
- <span data-ttu-id="e5b5a-149">反向代理服务器。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-149">Reverse proxy.</span></span> <span data-ttu-id="e5b5a-150">这不是 Skype 业务服务器 2015年组件，但如果您想要支持的 web 内容的共享，为联合用户，如果您打算支持移动通信，如果要使用通讯簿中，您的远程用户加入会议，等等，这是东西您需要在您的环境中。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-150">This isn't a Skype for Business Server 2015 component, but if you want to support the sharing of web content for federated users, if you intend to support Mobility traffic, if your remote users want to use the address book, join meetings, and so on, this is something you'll want to have in your environment.</span></span> <span data-ttu-id="e5b5a-151">没有设置您可以检出的更多详细信息，当您准备好时的反向代理服务器主题。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-151">There's a Setting up Reverse proxy server topic you can check out for more details, when you're ready.</span></span>
    
<span data-ttu-id="e5b5a-152">有关这些服务器的并置的其他信息，请参见以下内容。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-152">Additional information on collocation for these servers can be found below.</span></span>
  
<span data-ttu-id="e5b5a-153">所有的前端池和标准版服务器在中央站点上部署共享所示，假定您已经部署了它们：</span><span class="sxs-lookup"><span data-stu-id="e5b5a-153">All the Front End pools and Standard Edition servers deployed at your central site share the following, assuming you've deployed them:</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="e5b5a-154">总监或总监池</span><span class="sxs-lookup"><span data-stu-id="e5b5a-154">Director or Director pool</span></span>  <br/> |<span data-ttu-id="e5b5a-155">独立的中介服务器或中介服务器池</span><span class="sxs-lookup"><span data-stu-id="e5b5a-155">Stand-alone Mediation Server or Mediation Server pool</span></span>  <br/> |<span data-ttu-id="e5b5a-156">Office Web Apps Server</span><span class="sxs-lookup"><span data-stu-id="e5b5a-156">Office Web Apps Server</span></span>  <br/> |
|<span data-ttu-id="e5b5a-157">边缘服务器或边池</span><span class="sxs-lookup"><span data-stu-id="e5b5a-157">Edge Server or Edge pool</span></span>  <br/> |<span data-ttu-id="e5b5a-158">持久的聊天服务器或持久聊天服务器池</span><span class="sxs-lookup"><span data-stu-id="e5b5a-158">Persistent Chat Server or Persistent Chat Server pool</span></span>  <br/> |<span data-ttu-id="e5b5a-159">监控</span><span class="sxs-lookup"><span data-stu-id="e5b5a-159">Monitoring</span></span>  <br/> |
   
<span data-ttu-id="e5b5a-160">在此列表中的 Exchange 统一消息 (UM) 服务器在哪里</span><span class="sxs-lookup"><span data-stu-id="e5b5a-160">Where is Exchange Unified Messaging (UM) Server in this list?</span></span> <span data-ttu-id="e5b5a-161">嗯，您可以肯定使用它 Skype 的业务服务器 2015年如果要集成与交换嗯，但不受业务服务器站点，Skype 是组件使这里我们就不提。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-161">Well, you can certainly use it with Skype for Business Server 2015 if you want to integrate with Exchange UM, but it's not a component of the Skype for Business Server site, so we're not mentioning it here.</span></span>
  
<span data-ttu-id="e5b5a-162">您可能打算有多个中心站点，以及如果是这样，它们可以共享以下服务器和角色，如果他们要部署在中心网站上：</span><span class="sxs-lookup"><span data-stu-id="e5b5a-162">You may be planning to have multiple central site, and if that's so, they can share the following servers and roles, if they're deployed on your central site:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="e5b5a-163">独立的中介服务器或中介服务器池</span><span class="sxs-lookup"><span data-stu-id="e5b5a-163">Stand-alone Mediation Server or Mediation Server pool</span></span>  <br/> |<span data-ttu-id="e5b5a-164">边缘服务器或边池</span><span class="sxs-lookup"><span data-stu-id="e5b5a-164">Edge Server or Edge pool</span></span>  <br/> |
|<span data-ttu-id="e5b5a-165">持久的聊天服务器或持久聊天服务器池</span><span class="sxs-lookup"><span data-stu-id="e5b5a-165">Persistent Chat Server or Persistent Chat Server pool</span></span>  <br/> |<span data-ttu-id="e5b5a-166">监控</span><span class="sxs-lookup"><span data-stu-id="e5b5a-166">Monitoring</span></span>  <br/> |
   
<span data-ttu-id="e5b5a-167">就像上一次的列表中，我们不因为它不属于业务服务器 2015年部署 Skype 但太落在这里，同一类别包括 Exchange UM 服务器。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-167">Just like the last list, we aren't including the Exchange UM Server here because it's not part of the Skype for Business Server 2015 deployment, but it falls into the same category here, too.</span></span>
  
<span data-ttu-id="e5b5a-168">当然，部署中还包含其他一些组件和选项。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-168">There are some other components and options that go into deployments, of course.</span></span>
  
|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e5b5a-169">防火墙</span><span class="sxs-lookup"><span data-stu-id="e5b5a-169">Firewalls</span></span>  <br/> |<span data-ttu-id="e5b5a-170">PSTN 网关（如果部署企业语音）</span><span class="sxs-lookup"><span data-stu-id="e5b5a-170">PSTN gateways (if you deploy Enterprise Voice</span></span>  <br/> |<span data-ttu-id="e5b5a-171">交换 UM 服务器 （如果您要集成与交换 UM）</span><span class="sxs-lookup"><span data-stu-id="e5b5a-171">Exchange UM Server (if you want to integrate with Exchange UM)</span></span>  <br/> |<span data-ttu-id="e5b5a-172">DNS 负载平衡</span><span class="sxs-lookup"><span data-stu-id="e5b5a-172">DNS load balancing</span></span>  <br/> |
|<span data-ttu-id="e5b5a-173">硬件负载平衡器</span><span class="sxs-lookup"><span data-stu-id="e5b5a-173">Hardware load balancers</span></span>  <br/> |<span data-ttu-id="e5b5a-174">SQL Server 数据库</span><span class="sxs-lookup"><span data-stu-id="e5b5a-174">SQL Server databases</span></span>  <br/> |<span data-ttu-id="e5b5a-175">文件共享</span><span class="sxs-lookup"><span data-stu-id="e5b5a-175">File shares</span></span>  <br/> ||
   
## <a name="server-roles"></a><span data-ttu-id="e5b5a-176">服务器角色</span><span class="sxs-lookup"><span data-stu-id="e5b5a-176">Server roles</span></span>

<span data-ttu-id="e5b5a-177">运行 Skype 业务服务器每个服务器运行一个或多个服务器角色。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-177">Each server running Skype for Business Server runs one or more server roles.</span></span> <span data-ttu-id="e5b5a-178">服务器角色是一组由该服务器提供的业务服务器功能的定义的 Skype。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-178">A server role is a defined set of Skype for Business Server functionalities provided by that server.</span></span> <span data-ttu-id="e5b5a-179">无需在网络中部署所有可用服务器角色。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-179">You don't need to deploy all available server roles in your network.</span></span> <span data-ttu-id="e5b5a-180">只安装包含您想要的功能的服务器角色。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-180">Install only the server roles that contain the functionality that you want.</span></span>
  
<span data-ttu-id="e5b5a-181">对于大多数的服务器角色，可扩展性和高可用性可以部署池的多个服务器运行同一服务器角色的所有。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-181">For most server roles, for scalability and high availability you can deploy pools of multiple servers all running the same server role.</span></span> <span data-ttu-id="e5b5a-182">池中的每台服务器必须运行一个或多个相同的服务器角色。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-182">Each server in a pool must run an identical server role or roles.</span></span> <span data-ttu-id="e5b5a-183">对于大多数类型的 Skype 业务服务器池，您必须部署负载平衡器来传播在池中的各服务器之间的通信。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-183">For most types of pools in Skype for Business Server, you must deploy a load balancer to spread traffic between the various servers in the pool.</span></span> <span data-ttu-id="e5b5a-184">支持 Skype 业务服务器的域名系统 (DNS) 负载平衡和硬件负载平衡器。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-184">Skype for Business Server supports both Domain Name System (DNS) load balancing and hardware load balancers.</span></span>
  
### <a name="front-end-server-and-back-end-server"></a><span data-ttu-id="e5b5a-185">前端服务器和后端服务器</span><span class="sxs-lookup"><span data-stu-id="e5b5a-185">Front End Server and Back End Server</span></span>

<span data-ttu-id="e5b5a-186">在 Skype 业务服务器的企业版，前端服务器是核心服务器角色，并运行许多基本 Skype 业务服务器功能。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-186">In Skype for Business Server Enterprise Edition, the Front End Server is the core server role, and runs many basic Skype for Business Server functions.</span></span> <span data-ttu-id="e5b5a-187">前端服务器和后端服务器，都需要在任何 Skype 业务服务器的企业版部署的唯一服务器角色。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-187">The Front End Server, along with the Back End Servers, are the only server roles required to be in any Skype for Business Server Enterprise Edition deployment.</span></span> 
  
<span data-ttu-id="e5b5a-188">前端池是一套前端服务器，配置都完全相同，协同工作以提供服务的一组常见的用户。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-188">A Front End pool is a set of Front End Servers, configured identically, that work together to provide services for a common group of users.</span></span> <span data-ttu-id="e5b5a-189">由多个运行同一角色的服务器构成的池提供可伸缩性和故障转移功能。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-189">A pool of multiple servers running the same role provides scalability and failover capability.</span></span>
  
<span data-ttu-id="e5b5a-190">前端服务器包含下列内容：</span><span class="sxs-lookup"><span data-stu-id="e5b5a-190">The Front End Server includes the following:</span></span>
  
- <span data-ttu-id="e5b5a-191">用户身份验证和注册。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-191">User authentication and registration.</span></span>
    
- <span data-ttu-id="e5b5a-192">状态信息和联系人卡片交换。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-192">Presence information and contact card exchange.</span></span>
    
- <span data-ttu-id="e5b5a-193">通讯簿服务和通讯组列表扩展。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-193">Address book services and distribution list expansion.</span></span>
    
- <span data-ttu-id="e5b5a-194">IM 功能，包括多方 IM 会议。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-194">IM functionality, including multiparty IM conferences.</span></span>
    
- <span data-ttu-id="e5b5a-195">Web 会议、PSTN 电话拨入式会议和 A/V 会议（如果部署）。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-195">Web conferencing, PSTN Dial-in conferencing and A/V conferencing (if deployed).</span></span>
    
- <span data-ttu-id="e5b5a-196">将宿主应用程序的业务服务器 （例如，会议助理和响应组应用程序），包括与 Skype 应用程序和第三方应用程序。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-196">Application hosting, for both applications included with Skype for Business Server (for example, Conferencing Attendant and Response Group application), and third-party applications.</span></span>
    
- <span data-ttu-id="e5b5a-197">（可选）监控功能，用于以呼叫详细记录 (CDR) 和呼叫错误记录 (CER) 形式收集使用信息。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-197">Optionally, Monitoring, to collect usage information in the form of call detail records (CDRs) and call error records (CERs).</span></span> <span data-ttu-id="e5b5a-198">此信息提供有关媒体 （音频和视频） 的质量指标遍历网络中的企业语音联络和 A / V 会议。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-198">This information provides metrics about the quality of the media (audio and video) traversing your network for both Enterprise Voice calls and A/V conferences.</span></span>
    
- <span data-ttu-id="e5b5a-199">用于支持基于 Web 的任务的 Web 组件，如 Web 计划程序和联接启动器。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-199">Web components to supported web-based tasks such as web scheduler and join launcher.</span></span>
    
- <span data-ttu-id="e5b5a-200">（可选）存档功能，用于存档 IM 通信和会议内容（出于合规性考虑）。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-200">Optionally, Archiving, to archive IM communications and meeting content for compliance reasons.</span></span> <span data-ttu-id="e5b5a-201">有关详细信息，请参阅规划文档中的[存档计划](http://technet.microsoft.com/library/898b83c1-007b-43be-9484-08fe49c10951.aspx)。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-201">For details, see [Planning for Archiving](http://technet.microsoft.com/library/898b83c1-007b-43be-9484-08fe49c10951.aspx) in the Planning documentation.</span></span>
    
    <span data-ttu-id="e5b5a-202">在 Lync Server 2010 和以前的版本中，监视和存档是单独的服务器角色，在前端服务器上不搭配。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-202">In Lync Server 2010 and prior versions, Monitoring and Archiving were separate server roles, not collocated on Front End Server.</span></span>
    
- <span data-ttu-id="e5b5a-203">（可选）如果启用持久聊天，则包括用于聊天室管理的持久聊天 Web 服务和用于文件上载/下载的持久聊天 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-203">Optionally, if Persistent chat is enabled, Persistent Chat Web Services for Chat Room Management and Persistent Chat Web Services for File Upload/Download.</span></span>
    
<span data-ttu-id="e5b5a-p120">前端池还是用户和会议数据的主存储。每个用户的相关信息将在池中的三个前端服务器之间复制，并将在后端服务器上进行备份。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-p120">Front End Pools are also the primary store for user and conference data. Information about each user is replicated among three Front End Servers in the pool, and backed up on the Back End Servers.</span></span>
  
<span data-ttu-id="e5b5a-206">此外，一个前端服务器部署中还运行中心管理服务器，其中管理和部署到运行 Skype 业务服务器的所有服务器的基本配置数据。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-206">Additionally, one Front End Server in the deployment also runs the Central Management Server, which manages and deploys basic configuration data to all servers running Skype for Business Server.</span></span> <span data-ttu-id="e5b5a-207">Lync 服务器管理外壳程序和文件传输功能，还提供了中央管理服务器。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-207">The Central Management Server also provides Lync Server Management Shell and file transfer capabilities.</span></span>
  
<span data-ttu-id="e5b5a-208">后端服务器数据库服务器是运行 Microsoft SQL Server 提供数据库服务的前端池。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-208">The Back End Servers are database servers running Microsoft SQL Server that provide the database services for the Front End pool.</span></span> <span data-ttu-id="e5b5a-209">后端服务器作为备份存储池的用户和会议数据，并且响应组数据库等其他数据库的主存储区。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-209">The Back End Servers serve as backup stores for the pool's user and conference data, and are the primary stores for other databases such as the Response Group database.</span></span> <span data-ttu-id="e5b5a-210">您可以有一个后端服务器，但使用镜像 SQL Server 的解决方案，适用于故障转移。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-210">You can have a single Back End Server, but a solution that uses SQL Server mirroring is recommended for failover.</span></span> <span data-ttu-id="e5b5a-211">后端服务器不运行任何 Skype 业务服务器软件。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-211">Back End Servers do not run any Skype for Business Server software.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e5b5a-212">我们不建议为业务服务器数据库与其他数据库配置 Skype。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-212">We do not recommend collocating Skype for Business Server databases with other databases.</span></span> <span data-ttu-id="e5b5a-213">如果您这样做，可能会影响可用性和性能。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-213">If you do so, availability and performance may be affected.</span></span> 
  
<span data-ttu-id="e5b5a-214">存储在后端服务器数据库中的信息包括状态信息、用户的联系人列表、包含所有当前会议状态相关的永久数据的会议数据，以及会议安排数据。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-214">Information stored in the Back End Server databases includes presence information, users' Contacts lists, conferencing data, including persistent data about the state of all current conferences, and conference scheduling data.</span></span>
  
### <a name="edge-server"></a><span data-ttu-id="e5b5a-215">边缘服务器</span><span class="sxs-lookup"><span data-stu-id="e5b5a-215">Edge Server</span></span>

<span data-ttu-id="e5b5a-216">边缘服务器使您的用户进行通信和协作与组织的防火墙之外的用户。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-216">Edge Server enables your users to communicate and collaborate with users outside the organization's firewalls.</span></span> <span data-ttu-id="e5b5a-217">这些外部用户可以包括的组织的用户的当前工作现场、 联盟的伙伴组织中的用户和外部用户的已被邀请加入您的业务服务器部署 Skype 上的会议。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-217">These external users can include the organization's own users who are currently working offsite, users from federated partner organizations, and outside users who have been invited to join conferences hosted on your Skype for Business Server deployment.</span></span>
  
<span data-ttu-id="e5b5a-218">部署边缘服务器还允许移动服务 Lync 功能支持在移动设备上。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-218">Deploying Edge Server also enables mobility services, which supports Lync functionality on mobile devices.</span></span> <span data-ttu-id="e5b5a-219">用户可以使用受支持的 Apple iOS、Android、Windows Phone 或 Nokia 移动设备来执行发送和接收即时消息、查看联系人和查看状态等活动。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-219">Users can use supported Apple iOS, Android, Windows Phone, or Nokia mobile devices to perform activities such as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span> <span data-ttu-id="e5b5a-220">此外，移动设备支持企业语音的一些特征，例如单击加入会议、 通过工作、 一个数字范围、 语音邮件、 呼叫和接的电话。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-220">In addition, mobile devices support some Enterprise Voice features, such as click to join a conference, Call via Work, single number reach, voice mail, and missed calls.</span></span> <span data-ttu-id="e5b5a-221">移动功能的移动设备不支持在后台运行的应用程序还支持推式通知。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-221">The mobility feature also supports push notifications for mobile devices that do not support applications running in the background.</span></span> <span data-ttu-id="e5b5a-222">推送通知是一类发送给移动设备的有关当移动设备处于不活动状态时发生的事件的通知。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-222">A push notification is a notification that is sent to a mobile device about an event that occurs while a mobile application is inactive.</span></span>
  
<span data-ttu-id="e5b5a-223">边缘服务器还包括完全集成的可扩展消息传递和状态协议 (XMPP) 代理，以及前端服务器上包含的 XMPP 网关。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-223">Edge Servers also include a fully-integrated Extensible Messaging and Presence Protocol (XMPP) proxy, with an XMPP gateway included on Front End Servers.</span></span> <span data-ttu-id="e5b5a-224">您可以配置这些 XMPP 组件以启用业务服务器用户您 Skype 为即时消息和状态从基于 XMPP 伙伴添加联系人。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-224">You can configure these XMPP components to enable your Skype for Business Server users to add contacts from XMPP-based partners for instant messaging and presence.</span></span>
  
### <a name="mediation-server"></a><span data-ttu-id="e5b5a-225">中介服务器</span><span class="sxs-lookup"><span data-stu-id="e5b5a-225">Mediation Server</span></span>

<span data-ttu-id="e5b5a-226">中介服务器是用于实现企业语音，调用通过的工作，并拨入会议的必要组件。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-226">Mediation Server is a necessary component for implementing Enterprise Voice, Call Via Work, and dial-in conferencing.</span></span> <span data-ttu-id="e5b5a-227">中介服务器转换信号传输，并且，在某些配置中，您的业务服务器基础结构的内部 Skype 之间的媒体和公众交换电话网络 (PSTN) 网关，IP PBX 或会话启动协议 (SIP) 干线。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-227">Mediation Server translates signaling, and, in some configurations, media between your internal Skype for Business Server infrastructure and a public switched telephone network (PSTN) gateway, IP-PBX, or a Session Initiation Protocol (SIP) trunk.</span></span> <span data-ttu-id="e5b5a-228">您可以将中介服务器运行在同一台服务器作为前端服务器，搭配或分成独立的中介服务器池。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-228">You can run Mediation Server collocated on the same server as Front End Server, or separated into a stand-alone Mediation Server pool.</span></span>
  
<span data-ttu-id="e5b5a-229">有关详细信息，请参阅[中业务服务器 2015年的 Skype 的中介服务器组件](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md)。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-229">For details, see [Mediation Server component in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md).</span></span>
  
### <a name="video-interop-server"></a><span data-ttu-id="e5b5a-230">视频互操作服务器</span><span class="sxs-lookup"><span data-stu-id="e5b5a-230">Video Interop Server</span></span>

<span data-ttu-id="e5b5a-231">互操作的视频服务器是 Skype 的业务服务器 2015年中的新角色。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-231">Video Interop Server is a new role in Skype for Business Server 2015.</span></span> <span data-ttu-id="e5b5a-232">它使您能够将业务服务器部署您 Skype 与某些第三方 VTC （视频电话会议系统） 解决方案集成。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-232">It enables you to integrate your Skype for Business Server deployment with certain third-party VTC (Video Teleconferencing System) solutions.</span></span> <span data-ttu-id="e5b5a-233">VIS 作为第三方电话会议系统和业务服务器部署 Skype 之间的媒介。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-233">A VIS acts as an intermediary between a 3rd party teleconference system and a Skype for Business Server deployment.</span></span> <span data-ttu-id="e5b5a-234">对于此版本，VIS 着重实现了与 Cisco/Tandberg 视频系统之间的互操作性。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-234">For this release, VIS is focused on interoperability with Cisco/Tandberg video systems.</span></span>
  
<span data-ttu-id="e5b5a-235">有关详细信息，请参阅[规划业务服务器 2015年的 Skype 视频互操作服务器](../../plan-your-deployment/video-interop-server.md)。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-235">For details, see [Plan for Video Interop Server in Skype for Business Server 2015](../../plan-your-deployment/video-interop-server.md).</span></span>
  
### <a name="director"></a><span data-ttu-id="e5b5a-236">控制器</span><span class="sxs-lookup"><span data-stu-id="e5b5a-236">Director</span></span>

<span data-ttu-id="e5b5a-237">董事可以验证 Skype 业务服务器的用户请求，但它们不家庭用户帐户或提供会议服务存在。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-237">Directors can authenticate Skype for Business Server user requests, but they do not home user accounts or provide presence or conferencing services.</span></span> <span data-ttu-id="e5b5a-238">控制器对于增强支持外部用户访问的部署中的安全性最有用。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-238">Directors are most useful to enhance security in deployments that enable external user access.</span></span> <span data-ttu-id="e5b5a-239">控制器可在将请求发送到内部服务器之前对请求进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-239">The Director can authenticate requests before sending them on to internal servers.</span></span> <span data-ttu-id="e5b5a-240">对于拒绝服务攻击，此攻击将终止于控制器且无法到达前端服务器。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-240">In the case of a denial-of-service attack, the attack ends with the Director and does not reach the Front End servers.</span></span>
  
### <a name="persistent-chat-server-roles"></a><span data-ttu-id="e5b5a-241">持久的聊天服务器角色</span><span class="sxs-lookup"><span data-stu-id="e5b5a-241">Persistent Chat Server Roles</span></span>

<span data-ttu-id="e5b5a-p130">利用持久聊天，用户可以参加持续进行的、基于主题的多方对话。持久聊天前端服务器可运行持久聊天服务。持久聊天后端服务器可存储聊天历史记录数据以及有关类别和聊天室的信息。可选持久聊天合规性后端服务器可存储聊天内容和合规性事件以实现合规性。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-p130">Persistent chat enables users to participate in multiparty, topic-based conversations that persist over time. The Persistent Chat Front End Server runs the persistent chat service. The Persistent Chat Back End Server stores the chat history data, and information about categories and chat rooms. The optional Persistent Chat Compliance Back End Server can store the chat content and compliance events for the purpose of compliance.</span></span>
  
<span data-ttu-id="e5b5a-246">服务器运行 Skype 业务 Server 标准版还可以运行持续聊天的搭配在同一台服务器上。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-246">Servers running Skype for Business Server Standard Edition can also run Persistent chat collocated on the same server.</span></span> <span data-ttu-id="e5b5a-247">不能配置持久聊天前端服务器的企业版前端服务器。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-247">You cannot collocate the Persistent Chat Front End Server with Enterprise Edition Front End Server.</span></span>
  
<span data-ttu-id="e5b5a-248">有关详细信息，请参阅[规划业务服务器 2015年的 Skype 的持久聊天服务器](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-248">For details, see [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).</span></span>
  
## <a name="high-availability-and-disaster-recovery-support"></a><span data-ttu-id="e5b5a-249">高可用性和灾难恢复支持</span><span class="sxs-lookup"><span data-stu-id="e5b5a-249">High availability and disaster recovery support</span></span>

<span data-ttu-id="e5b5a-250">Skype 业务服务器提供高可用性服务器冗余通过池。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-250">Skype for Business Server provides high availability by server redundancy via pooling.</span></span> <span data-ttu-id="e5b5a-251">如果运行特定服务器角色的服务器发生故障，则池中运行相同角色的其他服务器将承担该服务器的负载。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-251">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="e5b5a-252">这适用于前端服务器、边缘服务器、中介服务器和控制器。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-252">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span>
  
<span data-ttu-id="e5b5a-253">Skype 业务服务器还提供灾难恢复措施通过启用池配对。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-253">Skype for Business Server also provides disaster recovery measures by enabling pool pairing.</span></span> <span data-ttu-id="e5b5a-254">如果您部署了此拓扑，则将指定前端池对，对中的每个池位于不同地理区域的不同数据中心。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-254">If you deploy this topology, you will designate pairs of Front End pools, with each pool in a pair located in a separate data center, and in a separate geographical area.</span></span> <span data-ttu-id="e5b5a-255">如果一个池或一个站点不可用，则可将该池中的用户重定向至使用对中的其他池，并且对服务的干扰程度可以忽略不计。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-255">If one pool or site goes down, you can redirect the users of that pool to use the other pool in the pair, with minimal interruption of service.</span></span>
  
<span data-ttu-id="e5b5a-256">Skype 业务服务器还支持后端服务器高可用性的几个选项。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-256">Skype for Business Server also supports several options for Back End Server high availability.</span></span> <span data-ttu-id="e5b5a-257">其中包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="e5b5a-257">These include the following:</span></span>
  
- <span data-ttu-id="e5b5a-258">数据库镜像</span><span class="sxs-lookup"><span data-stu-id="e5b5a-258">Database mirroring</span></span>
    
- <span data-ttu-id="e5b5a-259">AlwaysOn 可用性组</span><span class="sxs-lookup"><span data-stu-id="e5b5a-259">AlwaysOn Availability Groups</span></span>
    
- <span data-ttu-id="e5b5a-260">AlwaysOn 故障转移群集实例 (FCI)</span><span class="sxs-lookup"><span data-stu-id="e5b5a-260">AlwaysOn Failover Cluster Instances (FCI)</span></span>
    
- <span data-ttu-id="e5b5a-261">SQL 故障转移群集</span><span class="sxs-lookup"><span data-stu-id="e5b5a-261">SQL failover clustering</span></span>
    
<span data-ttu-id="e5b5a-262">有关池的配对以及后端服务器的高可用性的详细信息，请参阅[规划高可用性和灾难恢复业务服务器 2015年的 Skype](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-262">For details about pool pairing and Back End Server high availability, see [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  
## <a name="server-collocation-in-skype-for-business-server-2015"></a><span data-ttu-id="e5b5a-263">在 Skype 的业务服务器 2015年的服务器配置</span><span class="sxs-lookup"><span data-stu-id="e5b5a-263">Server collocation in Skype for Business Server 2015</span></span>

<span data-ttu-id="e5b5a-264">我们使用了术语布置，但这意味着什么呢？</span><span class="sxs-lookup"><span data-stu-id="e5b5a-264">We've used the term collocate already, but what does this mean?</span></span> <span data-ttu-id="e5b5a-265">业务服务器 2015年的 Skype 允许您在同一个服务器上，这是配置，或不同的服务器上找到某些服务器角色和功能，但您刚开始出，何时以及是否要做标准版或企业版可能引起混乱服务器部署 （它们都附带了它们自己的规则）。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-265">Skype for Business Server 2015 allows you to locate some server roles and features on the same server, which is collocation, or on different servers, but it can be confusing when you're starting out, and whether you're doing a Standard Edition or Enterprise Edition server deployment (they each come with their own rules).</span></span> <span data-ttu-id="e5b5a-266">若要帮助规划过程中，我们正在服务器配置包括在标准版服务器部署和前端企业版池部署 （在大多数情况下，此信息是相同的和它时不同，就是专门）。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-266">To help with your planning, we're including server collocation in Standard Edition server deployments and Enterprise Edition Front End pool deployments (in most cases this information is identical, and where it's different, it's called out specifically).</span></span>
  
### <a name="collocation-of-server-roles"></a><span data-ttu-id="e5b5a-267">服务器角色的并置</span><span class="sxs-lookup"><span data-stu-id="e5b5a-267">Collocation of server roles</span></span>

<span data-ttu-id="e5b5a-268">标准版服务器具有以下角色搭配 （额外的配置是必需的但），而在该前端企业版池，此角色可以搭配使用，或部署到单独的服务器：</span><span class="sxs-lookup"><span data-stu-id="e5b5a-268">The Standard Edition server has the following role collocated (additional configuration is required though), while in the Enterprise Edition Front End pool, this role can be collocated, or deployed to a separate server:</span></span>
  
- <span data-ttu-id="e5b5a-269">中介</span><span class="sxs-lookup"><span data-stu-id="e5b5a-269">Mediation</span></span>
    
<span data-ttu-id="e5b5a-270">以下服务器角色必须分别部署在不同的服务器上：</span><span class="sxs-lookup"><span data-stu-id="e5b5a-270">These server roles must each be deployed on a separate server:</span></span>
  
- <span data-ttu-id="e5b5a-271">控制器</span><span class="sxs-lookup"><span data-stu-id="e5b5a-271">Director</span></span>
    
- <span data-ttu-id="e5b5a-272">Edge</span><span class="sxs-lookup"><span data-stu-id="e5b5a-272">Edge</span></span>
    
- <span data-ttu-id="e5b5a-273">视频互操作服务器</span><span class="sxs-lookup"><span data-stu-id="e5b5a-273">Video Interop Server</span></span>
    
- <span data-ttu-id="e5b5a-274">Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="e5b5a-274">Office Web Apps</span></span>
    
### <a name="databases"></a><span data-ttu-id="e5b5a-275">数据库</span><span class="sxs-lookup"><span data-stu-id="e5b5a-275">Databases</span></span>

<span data-ttu-id="e5b5a-276">这是该区域真正区别服务器部署标准版和企业版服务器池部署，所以，我们有两个部分，两个跟其他一些规则。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-276">This is the area with real differences between Standard Edition server deployments and Enterprise Edition server pool deployments, so we'll have two sections below, followed by some additional rules for both.</span></span>
  
#### <a name="standard"></a><span data-ttu-id="e5b5a-277">Standard</span><span class="sxs-lookup"><span data-stu-id="e5b5a-277">Standard</span></span>

<span data-ttu-id="e5b5a-278">由于 SQL Server Express 搭配在标准版服务器上，而不能移动，这是相当简单的。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-278">Since SQL Server Express is collocated on the Standard Edition server, and can't be moved, this is pretty straightforward.</span></span> <span data-ttu-id="e5b5a-279">此外，如果您在标准版服务器上部署永久性的聊天服务器，你还能够过，布置持久聊天和标准版服务器上的持续对话法规遵从性数据库，但您不必。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-279">Furthermore, if you deploy Persistent Chat Server on a Standard Edition server, you're also able to collocate the Persistent Chat and the Persistent Chat compliance database on the Standard Edition server too, but you don't have to.</span></span>
  
<span data-ttu-id="e5b5a-280">这些不能搭配在标准版服务器上，但可以在自己的一个数据库服务器:</span><span class="sxs-lookup"><span data-stu-id="e5b5a-280">These can't be collocated on the Standard Edition server, but can go on a single database server of their own:</span></span>
  
- <span data-ttu-id="e5b5a-281">监控数据库</span><span class="sxs-lookup"><span data-stu-id="e5b5a-281">Monitoring database</span></span>
    
- <span data-ttu-id="e5b5a-282">存档数据库</span><span class="sxs-lookup"><span data-stu-id="e5b5a-282">Archiving database</span></span>
    
- <span data-ttu-id="e5b5a-283">任何后端数据库的前端企业版池</span><span class="sxs-lookup"><span data-stu-id="e5b5a-283">Any back-end database for an Enterprise Edition Front End pool</span></span>
    
#### <a name="enterprise"></a><span data-ttu-id="e5b5a-284">Enterprise</span><span class="sxs-lookup"><span data-stu-id="e5b5a-284">Enterprise</span></span>

<span data-ttu-id="e5b5a-285">可以在同一个后端 SQL Server 搭配使用下列数据库：</span><span class="sxs-lookup"><span data-stu-id="e5b5a-285">The following databases can be collocated on the same back end SQL Server:</span></span>
  
- <span data-ttu-id="e5b5a-286">后端数据库</span><span class="sxs-lookup"><span data-stu-id="e5b5a-286">Back End database</span></span>
    
- <span data-ttu-id="e5b5a-287">监控数据库</span><span class="sxs-lookup"><span data-stu-id="e5b5a-287">Monitoring database</span></span>
    
- <span data-ttu-id="e5b5a-288">存档数据库</span><span class="sxs-lookup"><span data-stu-id="e5b5a-288">Archiving database</span></span>
    
- <span data-ttu-id="e5b5a-289">聊天中的持久性数据库</span><span class="sxs-lookup"><span data-stu-id="e5b5a-289">Persistent Chat database</span></span>
    
- <span data-ttu-id="e5b5a-290">聊天的法规遵从性的持久性数据库</span><span class="sxs-lookup"><span data-stu-id="e5b5a-290">Persistent Chat compliance database</span></span>
    
#### <a name="both"></a><span data-ttu-id="e5b5a-291">两者</span><span class="sxs-lookup"><span data-stu-id="e5b5a-291">Both</span></span>

<span data-ttu-id="e5b5a-292">现在，有了其他一些业务服务器 2015年数据库中单个 SQL 实例，或在同一 SQL Server 数据库中的多个 SQL 实例的配置 Skype 时要遵循的规则：</span><span class="sxs-lookup"><span data-stu-id="e5b5a-292">Now, there are some additional rules to follow when collocating Skype for Business Server 2015 databases in a single SQL instance, or in multiple SQL instances in the same SQL Server database:</span></span>
  
- <span data-ttu-id="e5b5a-293">每个 SQL 实例只能包含单个后端数据库的前端企业版池、 一个监视数据库、 一个存档数据库、 一个持久聊天数据库和一个持久聊天的法规遵从性数据库。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-293">Each SQL instance can only contain a single back end database for an Enterprise Edition Front End pool, a single Monitoring database, a single Archiving database, a single Persistent Chat database, and a single Persistent Chat compliance database.</span></span>
    
- <span data-ttu-id="e5b5a-294">数据库服务器不能支持多个前端企业版池、 一台服务器运行存档，一台服务器运行监控、 一个持久聊天数据库和一个持久聊天的法规遵从性的数据库，但它可以支持一种每个，无论是否数据库使用相同的 SQL Server 实例或单独的 SQL Server 实例。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-294">The database server can't support more than one Enterprise Edition Front End pool, one server running Archiving, one server running Monitoring, a single Persistent Chat database, and a single Persistent Chat compliance database, but it can support one of each, regardless of whether the databases use the same instance of SQL Server or separate instances of SQL Server.</span></span>
    
### <a name="file-shares"></a><span data-ttu-id="e5b5a-295">文件共享</span><span class="sxs-lookup"><span data-stu-id="e5b5a-295">File shares</span></span>

<span data-ttu-id="e5b5a-296">文件共享可以是在独立的服务器上，您也可以将其并置到与以下任何或所有组件相同的服务器上：</span><span class="sxs-lookup"><span data-stu-id="e5b5a-296">The file share can be on a separate server, or you can collocate it on the same server as any or all of the following:</span></span>
  
- <span data-ttu-id="e5b5a-297">数据库服务器，包括前端企业版池的后端服务器</span><span class="sxs-lookup"><span data-stu-id="e5b5a-297">Database server, including the Back End Server of an Enterprise Edition Front End pool</span></span>
    
- <span data-ttu-id="e5b5a-298">监控数据库</span><span class="sxs-lookup"><span data-stu-id="e5b5a-298">Monitoring database</span></span>
    
- <span data-ttu-id="e5b5a-299">存档数据库</span><span class="sxs-lookup"><span data-stu-id="e5b5a-299">Archiving database</span></span>
    
- <span data-ttu-id="e5b5a-300">聊天中的持久性数据库</span><span class="sxs-lookup"><span data-stu-id="e5b5a-300">Persistent Chat database</span></span>
    
- <span data-ttu-id="e5b5a-301">聊天的法规遵从性的持久性数据库</span><span class="sxs-lookup"><span data-stu-id="e5b5a-301">Persistent Chat compliance database</span></span>
    
> [!CAUTION]
> <span data-ttu-id="e5b5a-p137">请注意，虽然可以在这些服务器上并置文件共享，但是有必要指出的是，我们不建议这样做。如果将文件共享与任何其他服务器角色并置，请确保经常监视磁盘空间和性能问题。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-p137">Note that while you can collocate the file share on these servers, it's vital to note that we don't recommend it. If you'd collocating the file share with any other server role, please make sure you're monitoring for disk space and performance issues on a regular basis.</span></span> 
  
### <a name="keep-in-mind"></a><span data-ttu-id="e5b5a-304">请注意</span><span class="sxs-lookup"><span data-stu-id="e5b5a-304">Keep in mind</span></span>

- <span data-ttu-id="e5b5a-305">不能配置反向代理服务器，而不是业务服务器 2015年组件，Skype 甚至可能不是在您的拓扑结构。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-305">You can't collocate a reverse proxy server, which isn't a Skype for Business Server 2015 component, and may not even be in your topology.</span></span> <span data-ttu-id="e5b5a-306">如果您想要支持联盟的用户，以及其他许多内容的 web 内容的共享，您将需要反向代理。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-306">You'll need a reverse proxy if you want to support sharing of web content for federated users, among many other things.</span></span> <span data-ttu-id="e5b5a-307">如果需要请继续操作并配置已在贵组织中的其他应用程序正在使用现有的反向代理服务器以实现对 Skype 的业务服务器 2015年的反向代理服务器支持。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-307">If you need to, go ahead and implement reverse proxy support for Skype for Business Server 2015 by configuring an existing reverse proxy server that's already in your organization that's being used by other applications.</span></span>
    
- <span data-ttu-id="e5b5a-308">无法配置任何 UM Exchange 组件或具有任何 Skype 业务服务器 2015年角色的 SharePoint 服务器组件。</span><span class="sxs-lookup"><span data-stu-id="e5b5a-308">You can't collocate any Exchange UM component or SharePoint Server component with any Skype for Business Server 2015 role.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="e5b5a-309">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e5b5a-309">See also</span></span>

#### 

[<span data-ttu-id="e5b5a-310">Skype 的业务服务器 2015年的引用拓扑</span><span class="sxs-lookup"><span data-stu-id="e5b5a-310">Reference topologies for Skype for Business Server 2015</span></span>](reference-topologies.md)

