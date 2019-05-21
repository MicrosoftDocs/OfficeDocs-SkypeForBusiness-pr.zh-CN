---
title: Skype for Business 服务器的拓扑基础知识
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 113e8c3f-71de-435c-bc4a-918ac7b50008
description: '摘要: 选择 Skype for business 服务器的拓扑。 了解 Skype for business 服务器的服务器 collocation。'
ms.openlocfilehash: 5c8c4b7cc2a0bf1c392e3fad70a179b838a64606
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296621"
---
# <a name="topology-basics-for-skype-for-business-server"></a><span data-ttu-id="08f07-104">Skype for Business 服务器的拓扑基础知识</span><span class="sxs-lookup"><span data-stu-id="08f07-104">Topology Basics for Skype for Business Server</span></span>

<span data-ttu-id="08f07-105">**摘要:** 选择 Skype for business 服务器的拓扑。</span><span class="sxs-lookup"><span data-stu-id="08f07-105">**Summary:** Choose your topology for Skype for Business Server.</span></span> <span data-ttu-id="08f07-106">了解 Skype for business 服务器的服务器 collocation。</span><span class="sxs-lookup"><span data-stu-id="08f07-106">Learn about server collocation for Skype for Business Server.</span></span>

<span data-ttu-id="08f07-107">在准备任何其他内容之前, 您需要了解您正在为 Skype for business 服务器的部署规划合适的拓扑。</span><span class="sxs-lookup"><span data-stu-id="08f07-107">Before preparing anything else, you'll want to know you're planning for the right topology for your deployment of Skype for Business Server.</span></span> <span data-ttu-id="08f07-108">你需要确定的第一件事是, 如果你打算使用 Skype for Business Server 的内部部署, 或者你想要将其与混合部署中的 Skype for business Server Online 部署结合使用。</span><span class="sxs-lookup"><span data-stu-id="08f07-108">The first thing you need to decide is if you're going to have an on-premises deployment of Skype for Business Server, or if you're going to combine this with a Skype for Business Server Online deployment in a Hybrid deployment.</span></span> <span data-ttu-id="08f07-109">无论是哪种情况, 您都要进一步阅读, 因为我们将在此处详细介绍本地拓扑, 但混合详细信息记录在其各自的部分中。</span><span class="sxs-lookup"><span data-stu-id="08f07-109">Either way, you're going to want to read further, as we'll detail the on-premises topologies here, but the Hybrid details are documented in their own section.</span></span>

<span data-ttu-id="08f07-110">您还可以在[Skype for Business 服务器的参考拓扑](reference-topologies.md)中查看一些示例拓扑。</span><span class="sxs-lookup"><span data-stu-id="08f07-110">You can also see some example topologies in [Reference topologies for Skype for Business Server](reference-topologies.md).</span></span>

## <a name="sites"></a><span data-ttu-id="08f07-111">站点</span><span class="sxs-lookup"><span data-stu-id="08f07-111">Sites</span></span>

<span data-ttu-id="08f07-112">在 Skype for Business 服务器中, 你可以在网络上定义包含 Skype for Business 服务器组件的网站。</span><span class="sxs-lookup"><span data-stu-id="08f07-112">In Skype for Business Server, you define sites on your network that contain Skype for Business Server components.</span></span> <span data-ttu-id="08f07-113">站点是一组由高速度、低延迟网络（例如，单个局域网 (LAN) 或由高速光纤网络连接的两个网络）完美连接的计算机。</span><span class="sxs-lookup"><span data-stu-id="08f07-113">A site is a set of computers that is well-connected by a high-speed, low-latency network, such as a single local area network (LAN) or two networks connected by a high-speed fiber optic network.</span></span> <span data-ttu-id="08f07-114">请注意, Skype for business 服务器网站是来自 Active Directory 域服务站点和 Microsoft Exchange Server 站点的独立概念。</span><span class="sxs-lookup"><span data-stu-id="08f07-114">Note that Skype for Business Server sites are a separate concept from Active Directory Domain Services sites and Microsoft Exchange Server sites.</span></span> <span data-ttu-id="08f07-115">您的 Skype for Business 服务器网站不需要对应于您的 Active Directory 站点。</span><span class="sxs-lookup"><span data-stu-id="08f07-115">Your Skype for Business Server sites do not need to correspond to your Active Directory sites.</span></span>

<span data-ttu-id="08f07-116">Skype for Business 服务器支持可根据高可用性和位置要求进行缩放的一个或多个网站的本地部署。</span><span class="sxs-lookup"><span data-stu-id="08f07-116">Skype for Business Server supports on-premises deployment of one or more sites that can be scaled according to your high availability and location requirements.</span></span>

<span data-ttu-id="08f07-117">你的部署将至少有一个中心网站 (也称为数据中心), 这是所有位于它的服务器的数据中心, 并且你的部署中的每个中心网站都将具有一个标准版服务器或至少一个企业版前端池。</span><span class="sxs-lookup"><span data-stu-id="08f07-117">Your deployment will have at least one central site (also called a datacenter, this is a datacenter for all the servers located in it), and each central site in your deployment will have one Standard Edition server, or at least one Enterprise Edition Front End pool.</span></span> <span data-ttu-id="08f07-118">您可以在以下每个选项中了解其中的差异：</span><span class="sxs-lookup"><span data-stu-id="08f07-118">You can see the differences in each option below:</span></span>

- <span data-ttu-id="08f07-119">标准版服务器包括 collocated SQL Server Express 数据库。</span><span class="sxs-lookup"><span data-stu-id="08f07-119">Standard Edition server includes a collocated SQL Server Express database.</span></span>

- <span data-ttu-id="08f07-120">企业版前端池包括:</span><span class="sxs-lookup"><span data-stu-id="08f07-120">Enterprise Edition Front End pool includes:</span></span>

  - <span data-ttu-id="08f07-121">一个或多个前端服务器 (理想情况下, 至少三个是可伸缩性), 最大值为12。</span><span class="sxs-lookup"><span data-stu-id="08f07-121">One or more Front End Servers (Ideally at least three, for scalability), with a maximum of twelve.</span></span> <span data-ttu-id="08f07-122">对于多个服务器，需要提供负载平衡。</span><span class="sxs-lookup"><span data-stu-id="08f07-122">Load-balancing would be required for more than one server.</span></span>

  - <span data-ttu-id="08f07-123">单独的后端服务器。</span><span class="sxs-lookup"><span data-stu-id="08f07-123">A separate Back End Server.</span></span>

<span data-ttu-id="08f07-124">您可以在此部分了解有关各种服务器角色的更多信息。</span><span class="sxs-lookup"><span data-stu-id="08f07-124">You can learn more about the various server roles a little later in this section.</span></span>

<span data-ttu-id="08f07-125">除了你的中心网站, 你还可能最终拥有一个或多个与你的中心网站相关联的分支网站。</span><span class="sxs-lookup"><span data-stu-id="08f07-125">In addition to your central sites, you may also end up having one or more branch sites associated with your central site.</span></span> <span data-ttu-id="08f07-126">他们在中心网站上的几乎所有功能都依赖于中心网站, 因此它们的用途完全相同？</span><span class="sxs-lookup"><span data-stu-id="08f07-126">They depend on the central site for almost all their functionality, so what are they made up of, exactly?</span></span>

- <span data-ttu-id="08f07-127">Survivable 分支装置, 将公共交换电话网络 (PSTN) 网关与某些 Skype for business 服务器功能结合使用。</span><span class="sxs-lookup"><span data-stu-id="08f07-127">Survivable Branch Appliance, which combines a public switched telephone network (PSTN) gateway, with some Skype for Business Server functionality.</span></span>

- <span data-ttu-id="08f07-128">Survivable 分支服务器, 它是运行 Windows Server 且安装了 Skype for Business 服务器注册机构和中介服务器软件的服务器。</span><span class="sxs-lookup"><span data-stu-id="08f07-128">Survivable Branch Server, it's a server running Windows Server that has Skype for Business Server Registrar and Mediation Server software installed.</span></span>

- <span data-ttu-id="08f07-129">独立 PSTN 网关 (不是 Survivable 分支装置的一部分)。</span><span class="sxs-lookup"><span data-stu-id="08f07-129">Stand-alone PSTN gateway (which isn't part of the Survivable Branch Appliance).</span></span>

- <span data-ttu-id="08f07-130">独立中介服务器或独立中介服务器池 (如果你不想将此角色与 Survivable 分支装置 collocate。)</span><span class="sxs-lookup"><span data-stu-id="08f07-130">Stand-alone Mediation Server or stand-alone Mediation Server pool (if you don't want to collocate this role with the Survivable Branch Appliance).</span></span>

## <a name="whats-in-a-skype-for-business-server-site"></a><span data-ttu-id="08f07-131">Skype for business 服务器网站中有哪些内容？</span><span class="sxs-lookup"><span data-stu-id="08f07-131">What's in a Skype for Business Server site?</span></span>

<span data-ttu-id="08f07-132">若要了解更多详细信息, 中心网站还可以具有:</span><span class="sxs-lookup"><span data-stu-id="08f07-132">To get into more detail, a central site can also have:</span></span>

- <span data-ttu-id="08f07-133">多个前端池, 位于同一个域或不同域中 (请记住, 在计划中, 前端池中的所有前端服务器以及池的后端服务器都必须位于同一域中。</span><span class="sxs-lookup"><span data-stu-id="08f07-133">Multiple Front End pools, in the same domain or different domains (remember in planning that all the Front End Servers in a Front End pool, along with the Back End Servers for the pool, do have to be in the same domain).</span></span>

- <span data-ttu-id="08f07-134">多个标准版服务器。</span><span class="sxs-lookup"><span data-stu-id="08f07-134">Multiple Standard Edition servers.</span></span>

- <span data-ttu-id="08f07-135">Office Web Apps 服务器, 与 Skype for Business 服务器中的 Office Web Apps 一起使用, 用于共享和呈现 PowerPoint 演示文稿。</span><span class="sxs-lookup"><span data-stu-id="08f07-135">Office Web Apps Server, which is used with Office Web Apps in Skype for Business Server for sharing and rendering of PowerPoint presentations.</span></span>

- <span data-ttu-id="08f07-136">边缘服务器或边缘池 (在外围网络中)。</span><span class="sxs-lookup"><span data-stu-id="08f07-136">Edge Server or Edge pool (in a perimeter network).</span></span> <span data-ttu-id="08f07-137">如果希望部署支持联盟伙伴、公共 IM 连接、可扩展消息传递和状态协议 (XMPP) 网关以及远程用户访问，则需要此组件。</span><span class="sxs-lookup"><span data-stu-id="08f07-137">Needed if you want your deployment to support federated partners, public IM connectivity, extensible messaging and presence protocol (XMPP) gateway, and remote user access.</span></span> <span data-ttu-id="08f07-138">有关详细信息, 请参阅 Edge 服务器规划文档。</span><span class="sxs-lookup"><span data-stu-id="08f07-138">More details can be found in the Edge Server Planning documentation.</span></span>

- <span data-ttu-id="08f07-139">持久聊天服务器。</span><span class="sxs-lookup"><span data-stu-id="08f07-139">Persistent Chat Server.</span></span> <span data-ttu-id="08f07-140">如果您希望用户能够参与多方、基于主题的持久对话，则此组件将提供帮助。</span><span class="sxs-lookup"><span data-stu-id="08f07-140">Useful if you want users to be able to take part in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="08f07-141">有关规划持久聊天服务器主题的详细信息。</span><span class="sxs-lookup"><span data-stu-id="08f07-141">There's more information at the Planning for Persistent Chat Server topic.</span></span>

- <span data-ttu-id="08f07-142">监控。</span><span class="sxs-lookup"><span data-stu-id="08f07-142">Monitoring.</span></span> <span data-ttu-id="08f07-143">用于支持音频/视频 (A/V) 体验质量 (QoE) 的数据收集, 以及部署中的企业语音和音频/视频会议的详细录制 (CDR)。</span><span class="sxs-lookup"><span data-stu-id="08f07-143">Used to support data collection for audio/video (A/V) Quality of Experience (QoE) and call detail recording (CDR) for Enterprise Voice and A/V conferences in your deployment.</span></span> <span data-ttu-id="08f07-144">我们将在“规划监控”主题中详细谈论这一内容。</span><span class="sxs-lookup"><span data-stu-id="08f07-144">We discuss it in detail at the Planning for Monitoring topic.</span></span>

- <span data-ttu-id="08f07-145">导演或控制器池。</span><span class="sxs-lookup"><span data-stu-id="08f07-145">Director or Director pool.</span></span> <span data-ttu-id="08f07-146">不需要, 但如果你想要提高复原能力并启用将 Skype for Business 用户请求重定向到用户的主池, 这种方法非常有用。</span><span class="sxs-lookup"><span data-stu-id="08f07-146">Not required, but useful if you want to improve resiliency and enable redirection of Skype for Business user requests to the user's home pool.</span></span> <span data-ttu-id="08f07-147">如果你想要部署控制器, 每个池中最多支持10个。</span><span class="sxs-lookup"><span data-stu-id="08f07-147">If you want to deploy Directors, a maximum of 10 per pool is supported.</span></span> <span data-ttu-id="08f07-148">如果这是你需要的内容, 请务必继续阅读 "规划董事" 主题。</span><span class="sxs-lookup"><span data-stu-id="08f07-148">If this is something you need, definitely continue reading at the Planning for Directors topic.</span></span>

- <span data-ttu-id="08f07-149">反向代理。</span><span class="sxs-lookup"><span data-stu-id="08f07-149">Reverse proxy.</span></span> <span data-ttu-id="08f07-150">这不是 Skype for Business 服务器组件, 但是如果你想要支持联合用户共享 web 内容, 如果你想要支持移动通信, 如果你的远程用户想要使用通讯簿、加入会议等, 则可以希望在你的环境中拥有。</span><span class="sxs-lookup"><span data-stu-id="08f07-150">This isn't a Skype for Business Server component, but if you want to support the sharing of web content for federated users, if you intend to support Mobility traffic, if your remote users want to use the address book, join meetings, and so on, this is something you'll want to have in your environment.</span></span> <span data-ttu-id="08f07-151">设置反向代理服务器主题时, 你可以查看更多详细信息, 准备就绪。</span><span class="sxs-lookup"><span data-stu-id="08f07-151">There's a Setting up Reverse proxy server topic you can check out for more details, when you're ready.</span></span>

<span data-ttu-id="08f07-152">有关这些服务器的并置的其他信息，请参见以下内容。</span><span class="sxs-lookup"><span data-stu-id="08f07-152">Additional information on collocation for these servers can be found below.</span></span>

<span data-ttu-id="08f07-153">在中心网站上部署的所有前端池和标准版服务器 (假定已部署) 如下所示:</span><span class="sxs-lookup"><span data-stu-id="08f07-153">All the Front End pools and Standard Edition servers deployed at your central site share the following, assuming you've deployed them:</span></span>

||||
|:-----|:-----|:-----|
|<span data-ttu-id="08f07-154">导演或控制器池</span><span class="sxs-lookup"><span data-stu-id="08f07-154">Director or Director pool</span></span>  <br/> |<span data-ttu-id="08f07-155">独立中介服务器或中介服务器池</span><span class="sxs-lookup"><span data-stu-id="08f07-155">Stand-alone Mediation Server or Mediation Server pool</span></span>  <br/> |<span data-ttu-id="08f07-156">Office Web Apps Server</span><span class="sxs-lookup"><span data-stu-id="08f07-156">Office Web Apps Server</span></span>  <br/> |
|<span data-ttu-id="08f07-157">边缘服务器或边缘池</span><span class="sxs-lookup"><span data-stu-id="08f07-157">Edge Server or Edge pool</span></span>  <br/> |<span data-ttu-id="08f07-158">持久聊天服务器或持久聊天服务器池</span><span class="sxs-lookup"><span data-stu-id="08f07-158">Persistent Chat Server or Persistent Chat Server pool</span></span>  <br/> |<span data-ttu-id="08f07-159">监控</span><span class="sxs-lookup"><span data-stu-id="08f07-159">Monitoring</span></span>  <br/> |

<span data-ttu-id="08f07-160">此列表中的 Exchange 统一消息 (UM) 服务器在哪里？</span><span class="sxs-lookup"><span data-stu-id="08f07-160">Where is Exchange Unified Messaging (UM) Server in this list?</span></span> <span data-ttu-id="08f07-161">当然, 如果您想要与 Exchange UM 集成, 但它不是 Skype for business Server 网站的组件, 则可以使用它与 Skype for business 服务器配合使用, 这样就不会在此处提及。</span><span class="sxs-lookup"><span data-stu-id="08f07-161">Well, you can certainly use it with Skype for Business Server if you want to integrate with Exchange UM, but it's not a component of the Skype for Business Server site, so we're not mentioning it here.</span></span>

<span data-ttu-id="08f07-162">你可能计划有多个中心网站, 如果是这样, 则他们可以共享以下服务器和角色 (如果它们已部署在你的中心网站上):</span><span class="sxs-lookup"><span data-stu-id="08f07-162">You may be planning to have multiple central site, and if that's so, they can share the following servers and roles, if they're deployed on your central site:</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="08f07-163">独立中介服务器或中介服务器池</span><span class="sxs-lookup"><span data-stu-id="08f07-163">Stand-alone Mediation Server or Mediation Server pool</span></span>  <br/> |<span data-ttu-id="08f07-164">边缘服务器或边缘池</span><span class="sxs-lookup"><span data-stu-id="08f07-164">Edge Server or Edge pool</span></span>  <br/> |
|<span data-ttu-id="08f07-165">持久聊天服务器或持久聊天服务器池</span><span class="sxs-lookup"><span data-stu-id="08f07-165">Persistent Chat Server or Persistent Chat Server pool</span></span>  <br/> |<span data-ttu-id="08f07-166">监控</span><span class="sxs-lookup"><span data-stu-id="08f07-166">Monitoring</span></span>  <br/> |

<span data-ttu-id="08f07-167">与最后一个列表一样, 我们不会在此处包括 Exchange UM 服务器, 因为它不是 Skype for Business Server 部署的一部分, 但也属于同一类别。</span><span class="sxs-lookup"><span data-stu-id="08f07-167">Just like the last list, we aren't including the Exchange UM Server here because it's not part of the Skype for Business Server deployment, but it falls into the same category here, too.</span></span>

<span data-ttu-id="08f07-168">当然，部署中还包含其他一些组件和选项。</span><span class="sxs-lookup"><span data-stu-id="08f07-168">There are some other components and options that go into deployments, of course.</span></span>

|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="08f07-169">防火墙</span><span class="sxs-lookup"><span data-stu-id="08f07-169">Firewalls</span></span>  <br/> |<span data-ttu-id="08f07-170">PSTN 网关（如果部署企业语音）</span><span class="sxs-lookup"><span data-stu-id="08f07-170">PSTN gateways (if you deploy Enterprise Voice</span></span>  <br/> |<span data-ttu-id="08f07-171">Exchange UM 服务器 (如果想要与 Exchange UM 集成)</span><span class="sxs-lookup"><span data-stu-id="08f07-171">Exchange UM Server (if you want to integrate with Exchange UM)</span></span>  <br/> |<span data-ttu-id="08f07-172">DNS 负载平衡</span><span class="sxs-lookup"><span data-stu-id="08f07-172">DNS load balancing</span></span>  <br/> |
|<span data-ttu-id="08f07-173">硬件负载平衡器</span><span class="sxs-lookup"><span data-stu-id="08f07-173">Hardware load balancers</span></span>  <br/> |<span data-ttu-id="08f07-174">SQL Server 数据库</span><span class="sxs-lookup"><span data-stu-id="08f07-174">SQL Server databases</span></span>  <br/> |<span data-ttu-id="08f07-175">文件共享</span><span class="sxs-lookup"><span data-stu-id="08f07-175">File shares</span></span>  <br/> ||

## <a name="server-roles"></a><span data-ttu-id="08f07-176">服务器角色</span><span class="sxs-lookup"><span data-stu-id="08f07-176">Server roles</span></span>

<span data-ttu-id="08f07-177">运行 Skype for Business 服务器的每台服务器都运行一个或多个服务器角色。</span><span class="sxs-lookup"><span data-stu-id="08f07-177">Each server running Skype for Business Server runs one or more server roles.</span></span> <span data-ttu-id="08f07-178">服务器角色是指由服务器提供的一组已定义的 Skype for business 服务器功能。</span><span class="sxs-lookup"><span data-stu-id="08f07-178">A server role is a defined set of Skype for Business Server functionalities provided by that server.</span></span> <span data-ttu-id="08f07-179">无需在网络中部署所有可用服务器角色。</span><span class="sxs-lookup"><span data-stu-id="08f07-179">You don't need to deploy all available server roles in your network.</span></span> <span data-ttu-id="08f07-180">只安装包含您想要的功能的服务器角色。</span><span class="sxs-lookup"><span data-stu-id="08f07-180">Install only the server roles that contain the functionality that you want.</span></span>

<span data-ttu-id="08f07-181">对于大多数的服务器角色，要获得可伸缩性和高可用性，可部署全部运行同一服务器角色的多台服务器的“池”。</span><span class="sxs-lookup"><span data-stu-id="08f07-181">For most server roles, for scalability and high availability you can deploy pools of multiple servers all running the same server role.</span></span> <span data-ttu-id="08f07-182">池中的每台服务器必须运行一个或多个相同的服务器角色。</span><span class="sxs-lookup"><span data-stu-id="08f07-182">Each server in a pool must run an identical server role or roles.</span></span> <span data-ttu-id="08f07-183">对于 Skype for Business 服务器中的大多数类型的池, 必须部署负载平衡器以在池中的各种服务器之间传播流量。</span><span class="sxs-lookup"><span data-stu-id="08f07-183">For most types of pools in Skype for Business Server, you must deploy a load balancer to spread traffic between the various servers in the pool.</span></span> <span data-ttu-id="08f07-184">Skype for Business 服务器支持域名系统 (DNS) 负载平衡和硬件负载平衡器。</span><span class="sxs-lookup"><span data-stu-id="08f07-184">Skype for Business Server supports both Domain Name System (DNS) load balancing and hardware load balancers.</span></span>

### <a name="front-end-server-and-back-end-server"></a><span data-ttu-id="08f07-185">前端服务器和后端服务器</span><span class="sxs-lookup"><span data-stu-id="08f07-185">Front End Server and Back End Server</span></span>

<span data-ttu-id="08f07-186">在 Skype for business Server 企业版中, 前端服务器是核心服务器角色, 并且运行许多基本的 Skype for business 服务器功能。</span><span class="sxs-lookup"><span data-stu-id="08f07-186">In Skype for Business Server Enterprise Edition, the Front End Server is the core server role, and runs many basic Skype for Business Server functions.</span></span> <span data-ttu-id="08f07-187">前端服务器和后端服务器是指在任何 Skype for Business Server 部署中都需要的唯一服务器角色。</span><span class="sxs-lookup"><span data-stu-id="08f07-187">The Front End Server, along with the Back End Servers, are the only server roles required to be in any Skype for Business Server Enterprise Edition deployment.</span></span>

<span data-ttu-id="08f07-188">前端池是一组前端服务器 (配置相同), 它们协同工作以为一组常见用户提供服务。</span><span class="sxs-lookup"><span data-stu-id="08f07-188">A Front End pool is a set of Front End Servers, configured identically, that work together to provide services for a common group of users.</span></span> <span data-ttu-id="08f07-189">由多个运行同一角色的服务器构成的池提供可伸缩性和故障转移功能。</span><span class="sxs-lookup"><span data-stu-id="08f07-189">A pool of multiple servers running the same role provides scalability and failover capability.</span></span>

<span data-ttu-id="08f07-190">前端服务器包括以下内容:</span><span class="sxs-lookup"><span data-stu-id="08f07-190">The Front End Server includes the following:</span></span>

- <span data-ttu-id="08f07-191">用户身份验证和注册。</span><span class="sxs-lookup"><span data-stu-id="08f07-191">User authentication and registration.</span></span>

- <span data-ttu-id="08f07-192">状态信息和联系人卡片交换。</span><span class="sxs-lookup"><span data-stu-id="08f07-192">Presence information and contact card exchange.</span></span>

- <span data-ttu-id="08f07-193">通讯簿服务和通讯组列表扩展。</span><span class="sxs-lookup"><span data-stu-id="08f07-193">Address book services and distribution list expansion.</span></span>

- <span data-ttu-id="08f07-194">IM 功能，包括多方 IM 会议。</span><span class="sxs-lookup"><span data-stu-id="08f07-194">IM functionality, including multiparty IM conferences.</span></span>

- <span data-ttu-id="08f07-195">Web 会议、PSTN 电话拨入式会议和 A/V 会议（如果部署）。</span><span class="sxs-lookup"><span data-stu-id="08f07-195">Web conferencing, PSTN Dial-in conferencing and A/V conferencing (if deployed).</span></span>

- <span data-ttu-id="08f07-196">应用程序托管, 适用于 Skype for Business 服务器 (如会议助理和响应组应用程序) 和第三方应用程序随附的两个应用程序。</span><span class="sxs-lookup"><span data-stu-id="08f07-196">Application hosting, for both applications included with Skype for Business Server (for example, Conferencing Attendant and Response Group application), and third-party applications.</span></span>

- <span data-ttu-id="08f07-197">（可选）监控功能，用于以呼叫详细记录 (CDR) 和呼叫错误记录 (CER) 形式收集使用信息。</span><span class="sxs-lookup"><span data-stu-id="08f07-197">Optionally, Monitoring, to collect usage information in the form of call detail records (CDRs) and call error records (CERs).</span></span> <span data-ttu-id="08f07-198">此信息提供有关媒体质量 (音频和视频) 对您的网络进行企业语音通话和 A/V 会议的标准的衡量指标。</span><span class="sxs-lookup"><span data-stu-id="08f07-198">This information provides metrics about the quality of the media (audio and video) traversing your network for both Enterprise Voice calls and A/V conferences.</span></span>

- <span data-ttu-id="08f07-199">用于支持基于 Web 的任务的 Web 组件，如 Web 计划程序和联接启动器。</span><span class="sxs-lookup"><span data-stu-id="08f07-199">Web components to supported web-based tasks such as web scheduler and join launcher.</span></span>

- <span data-ttu-id="08f07-p119">（可选）存档功能，用于存档 IM 通信和会议内容（出于合规性考虑）。有关详细信息，请参阅规划文档中的[Planning for Archiving](https://technet.microsoft.com/library/898b83c1-007b-43be-9484-08fe49c10951.aspx)。</span><span class="sxs-lookup"><span data-stu-id="08f07-p119">Optionally, Archiving, to archive IM communications and meeting content for compliance reasons. For details, see [Planning for Archiving](https://technet.microsoft.com/library/898b83c1-007b-43be-9484-08fe49c10951.aspx) in the Planning documentation.</span></span>

    <span data-ttu-id="08f07-202">在 Lync Server 2010 和早期版本中, 监视和存档是独立的服务器角色, 而不是前端服务器上的 collocated。</span><span class="sxs-lookup"><span data-stu-id="08f07-202">In Lync Server 2010 and prior versions, Monitoring and Archiving were separate server roles, not collocated on Front End Server.</span></span>

- <span data-ttu-id="08f07-203">（可选）如果启用持久聊天，则包括用于聊天室管理的持久聊天 Web 服务和用于文件上载/下载的持久聊天 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="08f07-203">Optionally, if Persistent chat is enabled, Persistent Chat Web Services for Chat Room Management and Persistent Chat Web Services for File Upload/Download.</span></span>

<span data-ttu-id="08f07-p120">前端池还是用户和会议数据的主存储。每个用户的相关信息将在池中的三个前端服务器之间复制，并将在后端服务器上进行备份。</span><span class="sxs-lookup"><span data-stu-id="08f07-p120">Front End Pools are also the primary store for user and conference data. Information about each user is replicated among three Front End Servers in the pool, and backed up on the Back End Servers.</span></span>

<span data-ttu-id="08f07-206">此外, 部署中的一个前端服务器还运行中央管理服务器, 该服务器对运行 Skype for business 服务器的所有服务器管理和部署基本配置数据。</span><span class="sxs-lookup"><span data-stu-id="08f07-206">Additionally, one Front End Server in the deployment also runs the Central Management Server, which manages and deploys basic configuration data to all servers running Skype for Business Server.</span></span> <span data-ttu-id="08f07-207">中央管理服务器还提供 Lync Server 命令行管理程序和文件传输功能。</span><span class="sxs-lookup"><span data-stu-id="08f07-207">The Central Management Server also provides Lync Server Management Shell and file transfer capabilities.</span></span>

<span data-ttu-id="08f07-208">后端服务器是运行 Microsoft SQL Server 的数据库服务器, 它为前端池提供数据库服务。</span><span class="sxs-lookup"><span data-stu-id="08f07-208">The Back End Servers are database servers running Microsoft SQL Server that provide the database services for the Front End pool.</span></span> <span data-ttu-id="08f07-209">后端服务器充当池用户和会议数据的备份存储, 并且是其他数据库 (如响应组数据库) 的主要存储。</span><span class="sxs-lookup"><span data-stu-id="08f07-209">The Back End Servers serve as backup stores for the pool's user and conference data, and are the primary stores for other databases such as the Response Group database.</span></span> <span data-ttu-id="08f07-210">你可以拥有一台后端服务器, 但建议使用[Skype For Business 服务器的后端服务器高可用性](../high-availability-and-disaster-recovery/back-end-server.md)进行故障转移。</span><span class="sxs-lookup"><span data-stu-id="08f07-210">You can have a single Back End Server, but [Back End Server high availability in Skype for Business Server](../high-availability-and-disaster-recovery/back-end-server.md) is recommended for failover.</span></span> <span data-ttu-id="08f07-211">后端服务器不运行任何 Skype for Business 服务器软件。</span><span class="sxs-lookup"><span data-stu-id="08f07-211">Back End Servers do not run any Skype for Business Server software.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="08f07-212">我们不建议将 Skype for business Server 数据库与其他数据库 collocating。</span><span class="sxs-lookup"><span data-stu-id="08f07-212">We do not recommend collocating Skype for Business Server databases with other databases.</span></span> <span data-ttu-id="08f07-213">如果您这样做，可能会影响可用性和性能。</span><span class="sxs-lookup"><span data-stu-id="08f07-213">If you do so, availability and performance may be affected.</span></span>

> [!NOTE]
> <span data-ttu-id="08f07-214">在 Skype for business Server 2015 中提供了 SQL 镜像, 但 Skype for Business Server 2019 不再支持 SQL 镜像。</span><span class="sxs-lookup"><span data-stu-id="08f07-214">SQL Mirroring is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="08f07-215">适用于 Skype for Business Server 2019 的 AlwaysOn 可用性组、AlwaysOn 故障转移群集实例 (FCI) 和 SQL 故障转移群集方法优先。</span><span class="sxs-lookup"><span data-stu-id="08f07-215">The  AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering methods are preferred with Skype for Business Server 2019.</span></span>

<span data-ttu-id="08f07-216">存储在后端服务器数据库中的信息包括状态信息、用户的联系人列表、包含所有当前会议状态相关的永久数据的会议数据，以及会议安排数据。</span><span class="sxs-lookup"><span data-stu-id="08f07-216">Information stored in the Back End Server databases includes presence information, users' Contacts lists, conferencing data, including persistent data about the state of all current conferences, and conference scheduling data.</span></span>

### <a name="edge-server"></a><span data-ttu-id="08f07-217">边缘服务器</span><span class="sxs-lookup"><span data-stu-id="08f07-217">Edge Server</span></span>

<span data-ttu-id="08f07-218">边缘服务器使用户能够与组织防火墙外的用户进行通信和协作。</span><span class="sxs-lookup"><span data-stu-id="08f07-218">Edge Server enables your users to communicate and collaborate with users outside the organization's firewalls.</span></span> <span data-ttu-id="08f07-219">这些外部用户可以包括组织的自己的用户, 这些用户当前正在进行异地工作、来自联盟合作伙伴组织的用户以及已被邀请加入 Skype for business Server 部署中的会议的外部用户。</span><span class="sxs-lookup"><span data-stu-id="08f07-219">These external users can include the organization's own users who are currently working offsite, users from federated partner organizations, and outside users who have been invited to join conferences hosted on your Skype for Business Server deployment.</span></span>

<span data-ttu-id="08f07-220">部署边缘服务器还支持移动服务, 这些服务支持移动设备上的 Lync 功能。</span><span class="sxs-lookup"><span data-stu-id="08f07-220">Deploying Edge Server also enables mobility services, which supports Lync functionality on mobile devices.</span></span> <span data-ttu-id="08f07-221">用户可以使用受支持的 Apple iOS、Android、Windows Phone 或 Nokia 移动设备来执行发送和接收即时消息、查看联系人和查看状态等活动。</span><span class="sxs-lookup"><span data-stu-id="08f07-221">Users can use supported Apple iOS, Android, Windows Phone, or Nokia mobile devices to perform activities such as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span> <span data-ttu-id="08f07-222">此外, 移动设备支持某些企业语音功能, 例如单击加入会议、通过工作、单号码达到、语音邮件和未接来电进行呼叫。</span><span class="sxs-lookup"><span data-stu-id="08f07-222">In addition, mobile devices support some Enterprise Voice features, such as click to join a conference, Call via Work, single number reach, voice mail, and missed calls.</span></span> <span data-ttu-id="08f07-223">移动功能还支持针对不支持在后台运行的应用程序的移动设备的推送通知。</span><span class="sxs-lookup"><span data-stu-id="08f07-223">The mobility feature also supports push notifications for mobile devices that do not support applications running in the background.</span></span> <span data-ttu-id="08f07-224">推送通知是一类发送给移动设备的有关当移动设备处于不活动状态时发生的事件的通知。</span><span class="sxs-lookup"><span data-stu-id="08f07-224">A push notification is a notification that is sent to a mobile device about an event that occurs while a mobile application is inactive.</span></span>

<span data-ttu-id="08f07-225">边缘服务器还包括完全集成的可扩展消息传递和状态协议 (XMPP) 代理，以及前端服务器上包含的 XMPP 网关。</span><span class="sxs-lookup"><span data-stu-id="08f07-225">Edge Servers also include a fully-integrated Extensible Messaging and Presence Protocol (XMPP) proxy, with an XMPP gateway included on Front End Servers.</span></span> <span data-ttu-id="08f07-226">你可以将这些 XMPP 组件配置为允许 Skype for Business 服务器用户从基于 XMPP 的合作伙伴添加联系人, 以便发送即时消息和状态。</span><span class="sxs-lookup"><span data-stu-id="08f07-226">You can configure these XMPP components to enable your Skype for Business Server users to add contacts from XMPP-based partners for instant messaging and presence.</span></span>

> [!NOTE]
> <span data-ttu-id="08f07-227">XMPP 网关和代理在 Skype for business Server 2015 中可用, 但 Skype for business Server 2019 不再支持。</span><span class="sxs-lookup"><span data-stu-id="08f07-227">XMPP Gateways and proxies are available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="08f07-228">有关详细信息, 请参阅[迁移 XMPP 联合身份验证](../../../SfBServer2019/migration/migrating-xmpp-federation.md)。</span><span class="sxs-lookup"><span data-stu-id="08f07-228">See [Migrating XMPP federation](../../../SfBServer2019/migration/migrating-xmpp-federation.md) for more information.</span></span>

### <a name="mediation-server"></a><span data-ttu-id="08f07-229">中介服务器</span><span class="sxs-lookup"><span data-stu-id="08f07-229">Mediation Server</span></span>

<span data-ttu-id="08f07-230">中介服务器是实现企业语音、通过工作电话和拨入式会议进行通话所必需的组件。</span><span class="sxs-lookup"><span data-stu-id="08f07-230">Mediation Server is a necessary component for implementing Enterprise Voice, Call Via Work, and dial-in conferencing.</span></span> <span data-ttu-id="08f07-231">中介服务器转换信号, 在某些配置中, 在内部 Skype for business 服务器基础结构和公共交换电话网络 (PSTN) 网关、IP PBX 或会话初始协议 (SIP) 主干之间的媒体。</span><span class="sxs-lookup"><span data-stu-id="08f07-231">Mediation Server translates signaling, and, in some configurations, media between your internal Skype for Business Server infrastructure and a public switched telephone network (PSTN) gateway, IP-PBX, or a Session Initiation Protocol (SIP) trunk.</span></span> <span data-ttu-id="08f07-232">你可以在前端服务器所在的同一台服务器上运行中介服务器 collocated, 或将其分到独立的中介服务器池中。</span><span class="sxs-lookup"><span data-stu-id="08f07-232">You can run Mediation Server collocated on the same server as Front End Server, or separated into a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="08f07-233">有关详细信息, 请参阅[Skype For Business 服务器中的中介服务器组件](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md)。</span><span class="sxs-lookup"><span data-stu-id="08f07-233">For details, see [Mediation Server component in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md).</span></span>

### <a name="video-interop-server"></a><span data-ttu-id="08f07-234">视频互操作服务器</span><span class="sxs-lookup"><span data-stu-id="08f07-234">Video Interop Server</span></span>

<span data-ttu-id="08f07-235">视频互操作服务器是 Skype for business Server 2015 的新角色。</span><span class="sxs-lookup"><span data-stu-id="08f07-235">Video Interop Server is a new role as of Skype for Business Server 2015.</span></span> <span data-ttu-id="08f07-236">它使您能够将 Skype for Business 服务器部署与特定的第三方 VTC (视频 Teleconferencing 系统) 解决方案集成。</span><span class="sxs-lookup"><span data-stu-id="08f07-236">It enables you to integrate your Skype for Business Server deployment with certain third-party VTC (Video Teleconferencing System) solutions.</span></span> <span data-ttu-id="08f07-237">VIS 充当第三方电话会议系统和 Skype for business 服务器部署之间的媒介。</span><span class="sxs-lookup"><span data-stu-id="08f07-237">A VIS acts as an intermediary between a 3rd party teleconference system and a Skype for Business Server deployment.</span></span> <span data-ttu-id="08f07-238">对于此版本，VIS 专用于实现与 Cisco/Tandberg 视频系统之间的互操作性。</span><span class="sxs-lookup"><span data-stu-id="08f07-238">For this release, VIS is focused on interoperability with Cisco/Tandberg video systems.</span></span>

<span data-ttu-id="08f07-239">有关详细信息, 请参阅[在 Skype For Business 服务器中规划视频互操作服务器](../../plan-your-deployment/video-interop-server.md)。</span><span class="sxs-lookup"><span data-stu-id="08f07-239">For details, see [Plan for Video Interop Server in Skype for Business Server](../../plan-your-deployment/video-interop-server.md).</span></span>

### <a name="director"></a><span data-ttu-id="08f07-240">控制器</span><span class="sxs-lookup"><span data-stu-id="08f07-240">Director</span></span>

<span data-ttu-id="08f07-241">控制器可以验证 Skype for business 服务器用户请求, 但他们不能在家用户帐户或提供状态或会议服务。</span><span class="sxs-lookup"><span data-stu-id="08f07-241">Directors can authenticate Skype for Business Server user requests, but they do not home user accounts or provide presence or conferencing services.</span></span> <span data-ttu-id="08f07-242">控制器对于增强支持外部用户访问的部署中的安全性最有用。</span><span class="sxs-lookup"><span data-stu-id="08f07-242">Directors are most useful to enhance security in deployments that enable external user access.</span></span> <span data-ttu-id="08f07-243">控制器可在将请求发送到内部服务器之前对请求进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="08f07-243">The Director can authenticate requests before sending them on to internal servers.</span></span> <span data-ttu-id="08f07-244">对于拒绝服务攻击，此攻击将终止于控制器且无法到达前端服务器。</span><span class="sxs-lookup"><span data-stu-id="08f07-244">In the case of a denial-of-service attack, the attack ends with the Director and does not reach the Front End servers.</span></span>

### <a name="persistent-chat-server-roles"></a><span data-ttu-id="08f07-245">持久聊天服务器角色</span><span class="sxs-lookup"><span data-stu-id="08f07-245">Persistent Chat Server Roles</span></span>

> [!NOTE]
> <span data-ttu-id="08f07-246">Skype for business Server 2015 中提供了持久聊天, 但 Skype for business Server 2019 不再支持此功能。</span><span class="sxs-lookup"><span data-stu-id="08f07-246">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="08f07-247">团队中提供了相同的功能。</span><span class="sxs-lookup"><span data-stu-id="08f07-247">The same functionality is available in Teams.</span></span> <span data-ttu-id="08f07-248">有关详细信息, 请参阅[从 Skype For Business 迁移到 Microsoft 团队](/microsoftteams/journey-skypeforbusiness-teams)。</span><span class="sxs-lookup"><span data-stu-id="08f07-248">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="08f07-249">如果需要使用持久聊天, 您可以选择将需要此功能的用户迁移到团队, 或继续使用 Skype for Business Server 2015。</span><span class="sxs-lookup"><span data-stu-id="08f07-249">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span>

<span data-ttu-id="08f07-p133">利用持久聊天，用户可以参加持续进行的、基于主题的多方对话。持久聊天前端服务器可运行持久聊天服务。持久聊天后端服务器可存储聊天历史记录数据以及有关类别和聊天室的信息。可选持久聊天合规性后端服务器可存储聊天内容和合规性事件以实现合规性。</span><span class="sxs-lookup"><span data-stu-id="08f07-p133">Persistent chat enables users to participate in multiparty, topic-based conversations that persist over time. The Persistent Chat Front End Server runs the persistent chat service. The Persistent Chat Back End Server stores the chat history data, and information about categories and chat rooms. The optional Persistent Chat Compliance Back End Server can store the chat content and compliance events for the purpose of compliance.</span></span>

<span data-ttu-id="08f07-254">运行 Skype for business Server 标准版的服务器也可以在同一台服务器上运行永久聊天 collocated。</span><span class="sxs-lookup"><span data-stu-id="08f07-254">Servers running Skype for Business Server Standard Edition can also run Persistent chat collocated on the same server.</span></span> <span data-ttu-id="08f07-255">不能将持久聊天前端服务器 collocate 到企业版前端服务器。</span><span class="sxs-lookup"><span data-stu-id="08f07-255">You cannot collocate the Persistent Chat Front End Server with Enterprise Edition Front End Server.</span></span>

<span data-ttu-id="08f07-256">有关详细信息, 请参阅[在 Skype for Business server 2015 中规划持久聊天服务器](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)。</span><span class="sxs-lookup"><span data-stu-id="08f07-256">For details, see [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).</span></span>

## <a name="high-availability-and-disaster-recovery-support"></a><span data-ttu-id="08f07-257">高可用性和灾难恢复支持</span><span class="sxs-lookup"><span data-stu-id="08f07-257">High availability and disaster recovery support</span></span>

<span data-ttu-id="08f07-258">Skype for business 服务器通过池划分提供了服务器冗余的高可用性。</span><span class="sxs-lookup"><span data-stu-id="08f07-258">Skype for Business Server provides high availability by server redundancy via pooling.</span></span> <span data-ttu-id="08f07-259">如果运行特定服务器角色的服务器发生故障，则池中运行相同角色的其他服务器将承担该服务器的负载。</span><span class="sxs-lookup"><span data-stu-id="08f07-259">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="08f07-260">这适用于前端服务器、边缘服务器、中介服务器和控制器。</span><span class="sxs-lookup"><span data-stu-id="08f07-260">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span>

<span data-ttu-id="08f07-261">Skype for business 服务器还通过启用池配对来提供灾难恢复措施。</span><span class="sxs-lookup"><span data-stu-id="08f07-261">Skype for Business Server also provides disaster recovery measures by enabling pool pairing.</span></span> <span data-ttu-id="08f07-262">如果您部署了此拓扑，则将指定前端池对，对中的每个池位于不同地理区域的不同数据中心。</span><span class="sxs-lookup"><span data-stu-id="08f07-262">If you deploy this topology, you will designate pairs of Front End pools, with each pool in a pair located in a separate data center, and in a separate geographical area.</span></span> <span data-ttu-id="08f07-263">如果一个池或一个站点不可用，则可将该池中的用户重定向至使用对中的其他池，并且对服务的干扰程度可以忽略不计。</span><span class="sxs-lookup"><span data-stu-id="08f07-263">If one pool or site goes down, you can redirect the users of that pool to use the other pool in the pair, with minimal interruption of service.</span></span>

<span data-ttu-id="08f07-264">Skype for Business 服务器还支持用于后端服务器高可用性的多个选项。</span><span class="sxs-lookup"><span data-stu-id="08f07-264">Skype for Business Server also supports several options for Back End Server high availability.</span></span> <span data-ttu-id="08f07-265">其中包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="08f07-265">These include the following:</span></span>

- <span data-ttu-id="08f07-266">数据库镜像</span><span class="sxs-lookup"><span data-stu-id="08f07-266">Database mirroring</span></span>

- <span data-ttu-id="08f07-267">AlwaysOn 可用性组</span><span class="sxs-lookup"><span data-stu-id="08f07-267">AlwaysOn Availability Groups</span></span>

- <span data-ttu-id="08f07-268">AlwaysOn 故障转移群集实例 (FCI)</span><span class="sxs-lookup"><span data-stu-id="08f07-268">AlwaysOn Failover Cluster Instances (FCI)</span></span>

- <span data-ttu-id="08f07-269">SQL 故障转移群集</span><span class="sxs-lookup"><span data-stu-id="08f07-269">SQL failover clustering</span></span>

<span data-ttu-id="08f07-270">有关池配对和后端服务器高可用性的详细信息, 请参阅[在 Skype For Business 服务器中规划高可用性和灾难恢复](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。</span><span class="sxs-lookup"><span data-stu-id="08f07-270">For details about pool pairing and Back End Server high availability, see [Plan for high availability and disaster recovery in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>

## <a name="server-collocation-in-skype-for-business-server"></a><span data-ttu-id="08f07-271">Skype for Business 服务器中的服务器 collocation</span><span class="sxs-lookup"><span data-stu-id="08f07-271">Server collocation in Skype for Business Server</span></span>

<span data-ttu-id="08f07-272">我们已使用过术语 collocate, 但这意味着什么？</span><span class="sxs-lookup"><span data-stu-id="08f07-272">We've used the term collocate already, but what does this mean?</span></span> <span data-ttu-id="08f07-273">通过 Skype for Business 服务器, 你可以在同一台服务器 (collocation) 上找到一些服务器角色和功能, 但在启动标准版或企业版服务器时可能会令人混淆。部署 (它们各自都附带有自己的规则)。</span><span class="sxs-lookup"><span data-stu-id="08f07-273">Skype for Business Server allows you to locate some server roles and features on the same server, which is collocation, or on different servers, but it can be confusing when you're starting out, and whether you're doing a Standard Edition or Enterprise Edition server deployment (they each come with their own rules).</span></span> <span data-ttu-id="08f07-274">为帮助你进行规划, 我们在标准版服务器部署和企业版前端池部署中包括服务器 collocation (在大多数情况下, 此信息是相同的, 而在哪里不同, 则特别明确)。</span><span class="sxs-lookup"><span data-stu-id="08f07-274">To help with your planning, we're including server collocation in Standard Edition server deployments and Enterprise Edition Front End pool deployments (in most cases this information is identical, and where it's different, it's called out specifically).</span></span>

### <a name="collocation-of-server-roles"></a><span data-ttu-id="08f07-275">服务器角色的并置</span><span class="sxs-lookup"><span data-stu-id="08f07-275">Collocation of server roles</span></span>

<span data-ttu-id="08f07-276">标准版服务器具有下列角色 collocated (但需要额外配置), 在企业版前端池中, 此角色可以是 collocated, 或者部署到单独的服务器:</span><span class="sxs-lookup"><span data-stu-id="08f07-276">The Standard Edition server has the following role collocated (additional configuration is required though), while in the Enterprise Edition Front End pool, this role can be collocated, or deployed to a separate server:</span></span>

- <span data-ttu-id="08f07-277">中介</span><span class="sxs-lookup"><span data-stu-id="08f07-277">Mediation</span></span>

<span data-ttu-id="08f07-278">以下服务器角色必须分别部署在不同的服务器上：</span><span class="sxs-lookup"><span data-stu-id="08f07-278">These server roles must each be deployed on a separate server:</span></span>

- <span data-ttu-id="08f07-279">控制器</span><span class="sxs-lookup"><span data-stu-id="08f07-279">Director</span></span>

- <span data-ttu-id="08f07-280">Edge</span><span class="sxs-lookup"><span data-stu-id="08f07-280">Edge</span></span>

- <span data-ttu-id="08f07-281">视频互操作服务器</span><span class="sxs-lookup"><span data-stu-id="08f07-281">Video Interop Server</span></span>

- <span data-ttu-id="08f07-282">Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="08f07-282">Office Web Apps</span></span>

### <a name="databases"></a><span data-ttu-id="08f07-283">数据库</span><span class="sxs-lookup"><span data-stu-id="08f07-283">Databases</span></span>

<span data-ttu-id="08f07-284">这是标准版服务器部署和企业版服务器池部署之间的实际差异的区域, 因此我们将有两个部分, 后跟这两个部分的其他规则。</span><span class="sxs-lookup"><span data-stu-id="08f07-284">This is the area with real differences between Standard Edition server deployments and Enterprise Edition server pool deployments, so we'll have two sections below, followed by some additional rules for both.</span></span>

#### <a name="standard"></a><span data-ttu-id="08f07-285">Standard</span><span class="sxs-lookup"><span data-stu-id="08f07-285">Standard</span></span>

<span data-ttu-id="08f07-286">由于 SQL Server Express 在标准版服务器上 collocated, 因此不能移动, 这相当简单。</span><span class="sxs-lookup"><span data-stu-id="08f07-286">Since SQL Server Express is collocated on the Standard Edition server, and can't be moved, this is pretty straightforward.</span></span> <span data-ttu-id="08f07-287">此外, 如果在标准版服务器上部署持久聊天服务器, 你也可以在标准版服务器上 collocate 持久聊天和持久聊天合规性数据库, 但不必这样做。</span><span class="sxs-lookup"><span data-stu-id="08f07-287">Furthermore, if you deploy Persistent Chat Server on a Standard Edition server, you're also able to collocate the Persistent Chat and the Persistent Chat compliance database on the Standard Edition server too, but you don't have to.</span></span>

    > [!NOTE]
    > Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019. The same functionality is available in Teams. For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams). If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.

<span data-ttu-id="08f07-288">这些不能在标准版服务器上 collocated, 但可以在单个数据库服务器上执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="08f07-288">These can't be collocated on the Standard Edition server, but can go on a single database server of their own:</span></span>

- <span data-ttu-id="08f07-289">监控数据库</span><span class="sxs-lookup"><span data-stu-id="08f07-289">Monitoring database</span></span>

- <span data-ttu-id="08f07-290">存档数据库</span><span class="sxs-lookup"><span data-stu-id="08f07-290">Archiving database</span></span>

- <span data-ttu-id="08f07-291">适用于企业版前端池的任何后端数据库</span><span class="sxs-lookup"><span data-stu-id="08f07-291">Any back-end database for an Enterprise Edition Front End pool</span></span>

#### <a name="enterprise"></a><span data-ttu-id="08f07-292">Enterprise</span><span class="sxs-lookup"><span data-stu-id="08f07-292">Enterprise</span></span>

<span data-ttu-id="08f07-293">以下数据库可以在同一后端 SQL Server 上 collocated:</span><span class="sxs-lookup"><span data-stu-id="08f07-293">The following databases can be collocated on the same back end SQL Server:</span></span>

- <span data-ttu-id="08f07-294">后端数据库</span><span class="sxs-lookup"><span data-stu-id="08f07-294">Back End database</span></span>

- <span data-ttu-id="08f07-295">监控数据库</span><span class="sxs-lookup"><span data-stu-id="08f07-295">Monitoring database</span></span>

- <span data-ttu-id="08f07-296">存档数据库</span><span class="sxs-lookup"><span data-stu-id="08f07-296">Archiving database</span></span>

- <span data-ttu-id="08f07-297">持久聊天数据库</span><span class="sxs-lookup"><span data-stu-id="08f07-297">Persistent Chat database</span></span>

- <span data-ttu-id="08f07-298">持久聊天合规性数据库</span><span class="sxs-lookup"><span data-stu-id="08f07-298">Persistent Chat compliance database</span></span>

#### <a name="both"></a><span data-ttu-id="08f07-299">两者</span><span class="sxs-lookup"><span data-stu-id="08f07-299">Both</span></span>

<span data-ttu-id="08f07-300">现在, 在单个 SQL 实例中或在同一 SQL Server 数据库中的多个 SQL 实例中 collocating Skype for business 服务器数据库时, 还需遵循一些其他规则:</span><span class="sxs-lookup"><span data-stu-id="08f07-300">Now, there are some additional rules to follow when collocating Skype for Business Server databases in a single SQL instance, or in multiple SQL instances in the same SQL Server database:</span></span>

- <span data-ttu-id="08f07-301">每个 SQL 实例只能包含企业版前端池、单个监视数据库、单个存档数据库、单个持久聊天数据库和单个持久聊天合规性数据库的单个后端数据库。</span><span class="sxs-lookup"><span data-stu-id="08f07-301">Each SQL instance can only contain a single back end database for an Enterprise Edition Front End pool, a single Monitoring database, a single Archiving database, a single Persistent Chat database, and a single Persistent Chat compliance database.</span></span>

- <span data-ttu-id="08f07-302">数据库服务器无法支持多个企业版前端池、一个运行存档的服务器、一个运行监视的服务器、单个持久聊天数据库和单个持久聊天合规性数据库, 但它可以支持其中一个无论数据库使用的是相同的 SQL Server 实例还是 SQL Server 的单独实例。</span><span class="sxs-lookup"><span data-stu-id="08f07-302">The database server can't support more than one Enterprise Edition Front End pool, one server running Archiving, one server running Monitoring, a single Persistent Chat database, and a single Persistent Chat compliance database, but it can support one of each, regardless of whether the databases use the same instance of SQL Server or separate instances of SQL Server.</span></span>

    > [!NOTE]
    > <span data-ttu-id="08f07-303">Skype for business Server 2015 中提供了持久聊天, 但 Skype for business Server 2019 不再支持此功能。</span><span class="sxs-lookup"><span data-stu-id="08f07-303">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="08f07-304">团队中提供了相同的功能。</span><span class="sxs-lookup"><span data-stu-id="08f07-304">The same functionality is available in Teams.</span></span> <span data-ttu-id="08f07-305">有关详细信息, 请参阅[从 Skype For Business 迁移到 Microsoft 团队](/microsoftteams/journey-skypeforbusiness-teams)。</span><span class="sxs-lookup"><span data-stu-id="08f07-305">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="08f07-306">如果需要使用持久聊天, 您可以选择将需要此功能的用户迁移到团队, 或继续使用 Skype for Business Server 2015。</span><span class="sxs-lookup"><span data-stu-id="08f07-306">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span>

### <a name="file-shares"></a><span data-ttu-id="08f07-307">文件共享</span><span class="sxs-lookup"><span data-stu-id="08f07-307">File shares</span></span>

<span data-ttu-id="08f07-308">文件共享可以是在独立的服务器上，您也可以将其并置到与以下任何或所有组件相同的服务器上：</span><span class="sxs-lookup"><span data-stu-id="08f07-308">The file share can be on a separate server, or you can collocate it on the same server as any or all of the following:</span></span>

- <span data-ttu-id="08f07-309">数据库服务器, 包括企业版前端池的后端服务器</span><span class="sxs-lookup"><span data-stu-id="08f07-309">Database server, including the Back End Server of an Enterprise Edition Front End pool</span></span>

- <span data-ttu-id="08f07-310">监控数据库</span><span class="sxs-lookup"><span data-stu-id="08f07-310">Monitoring database</span></span>

- <span data-ttu-id="08f07-311">存档数据库</span><span class="sxs-lookup"><span data-stu-id="08f07-311">Archiving database</span></span>

- <span data-ttu-id="08f07-312">持久聊天数据库</span><span class="sxs-lookup"><span data-stu-id="08f07-312">Persistent Chat database</span></span>

- <span data-ttu-id="08f07-313">持久聊天合规性数据库</span><span class="sxs-lookup"><span data-stu-id="08f07-313">Persistent Chat compliance database</span></span>

> [!CAUTION]
> <span data-ttu-id="08f07-p141">请注意，虽然可以在这些服务器上并置文件共享，但是有必要指出的是，我们不建议这样做。如果将文件共享与任何其他服务器角色并置，请确保经常监视磁盘空间和性能问题。</span><span class="sxs-lookup"><span data-stu-id="08f07-p141">Note that while you can collocate the file share on these servers, it's vital to note that we don't recommend it. If you'd collocating the file share with any other server role, please make sure you're monitoring for disk space and performance issues on a regular basis.</span></span>

### <a name="keep-in-mind"></a><span data-ttu-id="08f07-316">请注意</span><span class="sxs-lookup"><span data-stu-id="08f07-316">Keep in mind</span></span>

- <span data-ttu-id="08f07-317">不能 collocate 不是 Skype for business Server 组件的反向代理服务器, 也不能在拓扑中使用。</span><span class="sxs-lookup"><span data-stu-id="08f07-317">You can't collocate a reverse proxy server, which isn't a Skype for Business Server component, and may not even be in your topology.</span></span> <span data-ttu-id="08f07-318">如果你想要为联盟用户支持 web 内容的共享以及其他许多其他内容, 则需要反向代理。</span><span class="sxs-lookup"><span data-stu-id="08f07-318">You'll need a reverse proxy if you want to support sharing of web content for federated users, among many other things.</span></span> <span data-ttu-id="08f07-319">如果需要, 可通过配置你的组织中已存在由其他应用程序使用的现有反向代理服务器, 继续执行并为 Skype for business 服务器执行反向代理支持。</span><span class="sxs-lookup"><span data-stu-id="08f07-319">If you need to, go ahead and implement reverse proxy support for Skype for Business Server by configuring an existing reverse proxy server that's already in your organization that's being used by other applications.</span></span>

- <span data-ttu-id="08f07-320">您不能通过任何 Skype for Business 服务器角色 collocate 任何 Exchange UM 组件或 SharePoint Server 组件。</span><span class="sxs-lookup"><span data-stu-id="08f07-320">You can't collocate any Exchange UM component or SharePoint Server component with any Skype for Business Server role.</span></span>

## <a name="see-also"></a><span data-ttu-id="08f07-321">另请参阅</span><span class="sxs-lookup"><span data-stu-id="08f07-321">See also</span></span>

[<span data-ttu-id="08f07-322">Skype for Business 服务器的参考拓扑</span><span class="sxs-lookup"><span data-stu-id="08f07-322">Reference topologies for Skype for Business Server</span></span>](reference-topologies.md)
