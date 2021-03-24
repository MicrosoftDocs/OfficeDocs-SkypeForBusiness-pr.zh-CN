---
title: Skype for Business Server 的拓扑基础知识
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
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 113e8c3f-71de-435c-bc4a-918ac7b50008
description: 摘要：为 Skype for Business Server 选择拓扑。 了解 Skype for Business Server 的服务器并置。
ms.openlocfilehash: 39a75de6162f51d5d838ace557a546db3500ac01
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103988"
---
# <a name="topology-basics-for-skype-for-business-server"></a><span data-ttu-id="ac282-104">Skype for Business Server 的拓扑基础知识</span><span class="sxs-lookup"><span data-stu-id="ac282-104">Topology Basics for Skype for Business Server</span></span>

<span data-ttu-id="ac282-105">**摘要：** 选择 Skype for Business Server 的拓扑。</span><span class="sxs-lookup"><span data-stu-id="ac282-105">**Summary:** Choose your topology for Skype for Business Server.</span></span> <span data-ttu-id="ac282-106">了解 Skype for Business Server 的服务器并置。</span><span class="sxs-lookup"><span data-stu-id="ac282-106">Learn about server collocation for Skype for Business Server.</span></span>

<span data-ttu-id="ac282-107">在准备任何其他内容之前，你需要知道你正在为 Skype for Business Server 的部署规划正确的拓扑。</span><span class="sxs-lookup"><span data-stu-id="ac282-107">Before preparing anything else, you'll want to know you're planning for the right topology for your deployment of Skype for Business Server.</span></span> <span data-ttu-id="ac282-108">首先需要确定是准备本地部署 Skype for Business Server，还是要将其与混合部署中的 Skype for Business Server Online 部署相结合。</span><span class="sxs-lookup"><span data-stu-id="ac282-108">The first thing you need to decide is if you're going to have an on-premises deployment of Skype for Business Server, or if you're going to combine this with a Skype for Business Server Online deployment in a Hybrid deployment.</span></span> <span data-ttu-id="ac282-109">无论采用哪种方式，您都想进一步阅读，因为我们将在此处详细介绍本地拓扑，但混合详细信息记录在其自己的部分中。</span><span class="sxs-lookup"><span data-stu-id="ac282-109">Either way, you're going to want to read further, as we'll detail the on-premises topologies here, but the Hybrid details are documented in their own section.</span></span>

<span data-ttu-id="ac282-110">You can also see some example topologies in [Reference topologies for Skype for Business Server](reference-topologies.md).</span><span class="sxs-lookup"><span data-stu-id="ac282-110">You can also see some example topologies in [Reference topologies for Skype for Business Server](reference-topologies.md).</span></span>

## <a name="sites"></a><span data-ttu-id="ac282-111">网站</span><span class="sxs-lookup"><span data-stu-id="ac282-111">Sites</span></span>

<span data-ttu-id="ac282-112">在 Skype for Business Server 中，定义网络上包含 Skype for Business Server 组件的站点。</span><span class="sxs-lookup"><span data-stu-id="ac282-112">In Skype for Business Server, you define sites on your network that contain Skype for Business Server components.</span></span> <span data-ttu-id="ac282-113">站点是一组由高速度、低延迟网络（例如，单个局域网 (LAN) 或由高速光纤网络连接的两个网络）完美连接的计算机。</span><span class="sxs-lookup"><span data-stu-id="ac282-113">A site is a set of computers that is well-connected by a high-speed, low-latency network, such as a single local area network (LAN) or two networks connected by a high-speed fiber optic network.</span></span> <span data-ttu-id="ac282-114">请注意，Skype for Business Server 站点是一个独立于 Active Directory 域服务站点和Microsoft Exchange Server概念。</span><span class="sxs-lookup"><span data-stu-id="ac282-114">Note that Skype for Business Server sites are a separate concept from Active Directory Domain Services sites and Microsoft Exchange Server sites.</span></span> <span data-ttu-id="ac282-115">Skype for Business Server 站点不需要与 Active Directory 站点对应。</span><span class="sxs-lookup"><span data-stu-id="ac282-115">Your Skype for Business Server sites do not need to correspond to your Active Directory sites.</span></span>

<span data-ttu-id="ac282-116">Skype for Business Server 支持一个或多个站点本地部署，这些站点可根据你的高可用性和位置要求进行扩展。</span><span class="sxs-lookup"><span data-stu-id="ac282-116">Skype for Business Server supports on-premises deployment of one or more sites that can be scaled according to your high availability and location requirements.</span></span>

<span data-ttu-id="ac282-117">您的部署将具有至少一个中央站点 (也称为数据中心，这是位于) 中所有服务器的数据中心，部署中的每个中央站点将具有一台 Standard Edition Server 或至少一个 Enterprise Edition 前端池。</span><span class="sxs-lookup"><span data-stu-id="ac282-117">Your deployment will have at least one central site (also called a datacenter, this is a datacenter for all the servers located in it), and each central site in your deployment will have one Standard Edition server, or at least one Enterprise Edition Front End pool.</span></span> <span data-ttu-id="ac282-118">您可以在以下每个选项中查看差异：</span><span class="sxs-lookup"><span data-stu-id="ac282-118">You can see the differences in each option below:</span></span>

- <span data-ttu-id="ac282-119">Standard Edition Server 包含并SQL Server Express 数据库。</span><span class="sxs-lookup"><span data-stu-id="ac282-119">Standard Edition server includes a collocated SQL Server Express database.</span></span>

- <span data-ttu-id="ac282-120">Enterprise Edition 前端池包括：</span><span class="sxs-lookup"><span data-stu-id="ac282-120">Enterprise Edition Front End pool includes:</span></span>

  - <span data-ttu-id="ac282-121">一个或多个前端服务器 (至少三台，用于实现可伸缩性) ，最多为 12 台。</span><span class="sxs-lookup"><span data-stu-id="ac282-121">One or more Front End Servers (Ideally at least three, for scalability), with a maximum of twelve.</span></span> <span data-ttu-id="ac282-122">多个服务器需要负载平衡。</span><span class="sxs-lookup"><span data-stu-id="ac282-122">Load-balancing would be required for more than one server.</span></span>

  - <span data-ttu-id="ac282-123">单独的后端服务器。</span><span class="sxs-lookup"><span data-stu-id="ac282-123">A separate Back End Server.</span></span>

<span data-ttu-id="ac282-124">您可以在本节稍后部分了解有关各种服务器角色的更多内容。</span><span class="sxs-lookup"><span data-stu-id="ac282-124">You can learn more about the various server roles a little later in this section.</span></span>

<span data-ttu-id="ac282-125">除了中央站点之外，您最终可能还具有一个或多个与中央站点关联的分支站点。</span><span class="sxs-lookup"><span data-stu-id="ac282-125">In addition to your central sites, you may also end up having one or more branch sites associated with your central site.</span></span> <span data-ttu-id="ac282-126">它们依靠中央网站来几乎实现其所有功能，那么它们由什么具体决定？</span><span class="sxs-lookup"><span data-stu-id="ac282-126">They depend on the central site for almost all their functionality, so what are they made up of, exactly?</span></span>

- <span data-ttu-id="ac282-127">Survivable Branch Appliance，它将公用电话交换网 (PSTN) 网关，以及一些 Skype for Business Server 功能。</span><span class="sxs-lookup"><span data-stu-id="ac282-127">Survivable Branch Appliance, which combines a public switched telephone network (PSTN) gateway, with some Skype for Business Server functionality.</span></span>

- <span data-ttu-id="ac282-128">Survivable Branch Server 是运行 Windows Server 的服务器，已安装 Skype for Business Server 注册器和中介服务器软件。</span><span class="sxs-lookup"><span data-stu-id="ac282-128">Survivable Branch Server, it's a server running Windows Server that has Skype for Business Server Registrar and Mediation Server software installed.</span></span>

- <span data-ttu-id="ac282-129">独立的 PSTN 网关 (Survivable Branch Appliance 服务中的一) 。</span><span class="sxs-lookup"><span data-stu-id="ac282-129">Stand-alone PSTN gateway (which isn't part of the Survivable Branch Appliance).</span></span>

- <span data-ttu-id="ac282-130">如果您不想将此角色与 Survivable Branch Appliance 服务器并 (独立的中介服务器或独立的中介服务器池) 。</span><span class="sxs-lookup"><span data-stu-id="ac282-130">Stand-alone Mediation Server or stand-alone Mediation Server pool (if you don't want to collocate this role with the Survivable Branch Appliance).</span></span>

## <a name="whats-in-a-skype-for-business-server-site"></a><span data-ttu-id="ac282-131">Skype for Business Server 站点中有什么？</span><span class="sxs-lookup"><span data-stu-id="ac282-131">What's in a Skype for Business Server site?</span></span>

<span data-ttu-id="ac282-132">要获取更多详细信息，中央站点还可以具有：</span><span class="sxs-lookup"><span data-stu-id="ac282-132">To get into more detail, a central site can also have:</span></span>

- <span data-ttu-id="ac282-133">同一个域或不同域中的多个前端池 (请记住，在规划时，前端池中的所有前端服务器以及池的后端服务器必须位于同一个域) 。</span><span class="sxs-lookup"><span data-stu-id="ac282-133">Multiple Front End pools, in the same domain or different domains (remember in planning that all the Front End Servers in a Front End pool, along with the Back End Servers for the pool, do have to be in the same domain).</span></span>

- <span data-ttu-id="ac282-134">多个 Standard Edition 服务器。</span><span class="sxs-lookup"><span data-stu-id="ac282-134">Multiple Standard Edition servers.</span></span>

- <span data-ttu-id="ac282-135">Office Web Apps Server，与 Skype for Business Server 中的 Office Web Apps 一起用于共享和呈现 PowerPoint 演示文稿。</span><span class="sxs-lookup"><span data-stu-id="ac282-135">Office Web Apps Server, which is used with Office Web Apps in Skype for Business Server for sharing and rendering of PowerPoint presentations.</span></span>

- <span data-ttu-id="ac282-136">外围网络中 (边缘服务器或边缘) 。</span><span class="sxs-lookup"><span data-stu-id="ac282-136">Edge Server or Edge pool (in a perimeter network).</span></span> <span data-ttu-id="ac282-137">如果希望部署支持联盟伙伴、公共 IM 连接、可扩展消息传递和状态协议 (XMPP) 网关和远程用户访问，则需要此配置。</span><span class="sxs-lookup"><span data-stu-id="ac282-137">Needed if you want your deployment to support federated partners, public IM connectivity, extensible messaging and presence protocol (XMPP) gateway, and remote user access.</span></span> <span data-ttu-id="ac282-138">可以在边缘服务器规划文档中找到更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="ac282-138">More details can be found in the Edge Server Planning documentation.</span></span>

- <span data-ttu-id="ac282-139">持久聊天服务器。</span><span class="sxs-lookup"><span data-stu-id="ac282-139">Persistent Chat Server.</span></span> <span data-ttu-id="ac282-140">如果你希望用户能够参与基于主题的多方对话，这种对话会持续一段时间，则非常有用。</span><span class="sxs-lookup"><span data-stu-id="ac282-140">Useful if you want users to be able to take part in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="ac282-141">有关详细信息，请参阅规划持久聊天服务器主题。</span><span class="sxs-lookup"><span data-stu-id="ac282-141">There's more information at the Planning for Persistent Chat Server topic.</span></span>

- <span data-ttu-id="ac282-142">监视。</span><span class="sxs-lookup"><span data-stu-id="ac282-142">Monitoring.</span></span> <span data-ttu-id="ac282-143">用于支持为部署中的 企业语音 和 A/V 会议的音频/视频 (A/V) 用户体验质量 (QoE) 和呼叫详细信息记录 (CDR) 。</span><span class="sxs-lookup"><span data-stu-id="ac282-143">Used to support data collection for audio/video (A/V) Quality of Experience (QoE) and call detail recording (CDR) for Enterprise Voice and A/V conferences in your deployment.</span></span> <span data-ttu-id="ac282-144">我们将在规划监控主题中详细讨论此内容。</span><span class="sxs-lookup"><span data-stu-id="ac282-144">We discuss it in detail at the Planning for Monitoring topic.</span></span>

- <span data-ttu-id="ac282-145">控制器或控制器池。</span><span class="sxs-lookup"><span data-stu-id="ac282-145">Director or Director pool.</span></span> <span data-ttu-id="ac282-146">不是必需的，但如果你想要提高恢复能力并启用 Skype for Business 用户请求重定向到用户主池，则非常有用。</span><span class="sxs-lookup"><span data-stu-id="ac282-146">Not required, but useful if you want to improve resiliency and enable redirection of Skype for Business user requests to the user's home pool.</span></span> <span data-ttu-id="ac282-147">如果要部署控制器，则每个池最多支持 10 个控制器。</span><span class="sxs-lookup"><span data-stu-id="ac282-147">If you want to deploy Directors, a maximum of 10 per pool is supported.</span></span> <span data-ttu-id="ac282-148">如果需要这样做，一定要继续阅读规划控制器主题。</span><span class="sxs-lookup"><span data-stu-id="ac282-148">If this is something you need, definitely continue reading at the Planning for Directors topic.</span></span>

- <span data-ttu-id="ac282-149">反向代理。</span><span class="sxs-lookup"><span data-stu-id="ac282-149">Reverse proxy.</span></span> <span data-ttu-id="ac282-150">这不是 Skype for Business Server 组件，但是如果你想要支持联盟用户共享 Web 内容，如果你打算支持移动流量，如果你的远程用户想要使用通讯簿、加入会议等，那么这是你想要在你的环境中拥有的内容。</span><span class="sxs-lookup"><span data-stu-id="ac282-150">This isn't a Skype for Business Server component, but if you want to support the sharing of web content for federated users, if you intend to support Mobility traffic, if your remote users want to use the address book, join meetings, and so on, this is something you'll want to have in your environment.</span></span> <span data-ttu-id="ac282-151">有一个设置反向代理服务器主题，可以在准备就绪时查看更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="ac282-151">There's a Setting up Reverse proxy server topic you can check out for more details, when you're ready.</span></span>

<span data-ttu-id="ac282-152">有关这些服务器并置的其他信息，请参阅下文。</span><span class="sxs-lookup"><span data-stu-id="ac282-152">Additional information on collocation for these servers can be found below.</span></span>

<span data-ttu-id="ac282-153">在中央站点部署的所有前端池和 Standard Edition 服务器都共享以下内容（假定已部署它们）：</span><span class="sxs-lookup"><span data-stu-id="ac282-153">All the Front End pools and Standard Edition servers deployed at your central site share the following, assuming you've deployed them:</span></span>

||||
|:-----|:-----|:-----|
|<span data-ttu-id="ac282-154">控制器或控制器池</span><span class="sxs-lookup"><span data-stu-id="ac282-154">Director or Director pool</span></span>  <br/> |<span data-ttu-id="ac282-155">独立的中介服务器或中介服务器池</span><span class="sxs-lookup"><span data-stu-id="ac282-155">Stand-alone Mediation Server or Mediation Server pool</span></span>  <br/> |<span data-ttu-id="ac282-156">Office Web Apps Server</span><span class="sxs-lookup"><span data-stu-id="ac282-156">Office Web Apps Server</span></span>  <br/> |
|<span data-ttu-id="ac282-157">边缘服务器或边缘池</span><span class="sxs-lookup"><span data-stu-id="ac282-157">Edge Server or Edge pool</span></span>  <br/> |<span data-ttu-id="ac282-158">持久聊天服务器或持久聊天服务器池</span><span class="sxs-lookup"><span data-stu-id="ac282-158">Persistent Chat Server or Persistent Chat Server pool</span></span>  <br/> |<span data-ttu-id="ac282-159">监控</span><span class="sxs-lookup"><span data-stu-id="ac282-159">Monitoring</span></span>  <br/> |

<span data-ttu-id="ac282-160">Exchange 统一消息服务器 (UM) 服务器在此列表中在哪里？</span><span class="sxs-lookup"><span data-stu-id="ac282-160">Where is Exchange Unified Messaging (UM) Server in this list?</span></span> <span data-ttu-id="ac282-161">当然，如果你想要与 Exchange UM 集成，你当然可以将其与 Skype for Business Server 一起使用，但它不是 Skype for Business Server 站点的一个组件，所以我们不会在此处提及它。</span><span class="sxs-lookup"><span data-stu-id="ac282-161">Well, you can certainly use it with Skype for Business Server if you want to integrate with Exchange UM, but it's not a component of the Skype for Business Server site, so we're not mentioning it here.</span></span>

<span data-ttu-id="ac282-162">您可能计划具有多个中央站点，如果是这样，它们可以共享以下服务器和角色（如果它们部署在中央站点上）：</span><span class="sxs-lookup"><span data-stu-id="ac282-162">You may be planning to have multiple central site, and if that's so, they can share the following servers and roles, if they're deployed on your central site:</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="ac282-163">独立的中介服务器或中介服务器池</span><span class="sxs-lookup"><span data-stu-id="ac282-163">Stand-alone Mediation Server or Mediation Server pool</span></span>  <br/> |<span data-ttu-id="ac282-164">边缘服务器或边缘池</span><span class="sxs-lookup"><span data-stu-id="ac282-164">Edge Server or Edge pool</span></span>  <br/> |
|<span data-ttu-id="ac282-165">持久聊天服务器或持久聊天服务器池</span><span class="sxs-lookup"><span data-stu-id="ac282-165">Persistent Chat Server or Persistent Chat Server pool</span></span>  <br/> |<span data-ttu-id="ac282-166">监控</span><span class="sxs-lookup"><span data-stu-id="ac282-166">Monitoring</span></span>  <br/> |

<span data-ttu-id="ac282-167">就像最后一个列表一样，我们这里不包括 Exchange UM Server，因为它不是 Skype for Business Server 部署的一部分，但它在此处也属于同一类别。</span><span class="sxs-lookup"><span data-stu-id="ac282-167">Just like the last list, we aren't including the Exchange UM Server here because it's not part of the Skype for Business Server deployment, but it falls into the same category here, too.</span></span>

<span data-ttu-id="ac282-168">当然，还有一些其他组件和选项会进入部署。</span><span class="sxs-lookup"><span data-stu-id="ac282-168">There are some other components and options that go into deployments, of course.</span></span>

|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ac282-169">防火墙</span><span class="sxs-lookup"><span data-stu-id="ac282-169">Firewalls</span></span>  <br/> |<span data-ttu-id="ac282-170">PSTN 网关 (部署时企业语音</span><span class="sxs-lookup"><span data-stu-id="ac282-170">PSTN gateways (if you deploy Enterprise Voice</span></span>  <br/> |<span data-ttu-id="ac282-171">如果要与 exchange UM (集成，Exchange UM Server) </span><span class="sxs-lookup"><span data-stu-id="ac282-171">Exchange UM Server (if you want to integrate with Exchange UM)</span></span>  <br/> |<span data-ttu-id="ac282-172">DNS 负载平衡</span><span class="sxs-lookup"><span data-stu-id="ac282-172">DNS load balancing</span></span>  <br/> |
|<span data-ttu-id="ac282-173">硬件负载平衡器</span><span class="sxs-lookup"><span data-stu-id="ac282-173">Hardware load balancers</span></span>  <br/> |<span data-ttu-id="ac282-174">SQL Server 数据库</span><span class="sxs-lookup"><span data-stu-id="ac282-174">SQL Server databases</span></span>  <br/> |<span data-ttu-id="ac282-175">文件共享</span><span class="sxs-lookup"><span data-stu-id="ac282-175">File shares</span></span>  <br/> ||

## <a name="server-roles"></a><span data-ttu-id="ac282-176">服务器角色</span><span class="sxs-lookup"><span data-stu-id="ac282-176">Server roles</span></span>

<span data-ttu-id="ac282-177">运行 Skype for Business Server 的每台服务器运行一个或多个服务器角色。</span><span class="sxs-lookup"><span data-stu-id="ac282-177">Each server running Skype for Business Server runs one or more server roles.</span></span> <span data-ttu-id="ac282-178">服务器角色是由该服务器提供的一组定义的 Skype for Business Server 功能。</span><span class="sxs-lookup"><span data-stu-id="ac282-178">A server role is a defined set of Skype for Business Server functionalities provided by that server.</span></span> <span data-ttu-id="ac282-179">无需在网络中部署所有可用的服务器角色。</span><span class="sxs-lookup"><span data-stu-id="ac282-179">You don't need to deploy all available server roles in your network.</span></span> <span data-ttu-id="ac282-180">只安装包含您想要的功能的服务器角色。</span><span class="sxs-lookup"><span data-stu-id="ac282-180">Install only the server roles that contain the functionality that you want.</span></span>

<span data-ttu-id="ac282-181">对于大多数的服务器角色，要获得可伸缩性和高可用性，可部署全部运行同一服务器角色的多台服务器的“池”。</span><span class="sxs-lookup"><span data-stu-id="ac282-181">For most server roles, for scalability and high availability you can deploy pools of multiple servers all running the same server role.</span></span> <span data-ttu-id="ac282-182">池中的每台服务器必须运行一个或多个相同的服务器角色。</span><span class="sxs-lookup"><span data-stu-id="ac282-182">Each server in a pool must run an identical server role or roles.</span></span> <span data-ttu-id="ac282-183">对于 Skype for Business Server 中的大多数类型的池，必须部署负载平衡器以在池中的各个服务器之间分布流量。</span><span class="sxs-lookup"><span data-stu-id="ac282-183">For most types of pools in Skype for Business Server, you must deploy a load balancer to spread traffic between the various servers in the pool.</span></span> <span data-ttu-id="ac282-184">Skype for Business Server 支持域名系统 (DNS) 负载平衡和硬件负载平衡器。</span><span class="sxs-lookup"><span data-stu-id="ac282-184">Skype for Business Server supports both Domain Name System (DNS) load balancing and hardware load balancers.</span></span>

### <a name="front-end-server-and-back-end-server"></a><span data-ttu-id="ac282-185">前端服务器和后端服务器</span><span class="sxs-lookup"><span data-stu-id="ac282-185">Front End Server and Back End Server</span></span>

<span data-ttu-id="ac282-186">在 Skype for Business Server Enterprise Edition 中，前端服务器是核心服务器角色，并运行许多基本的 Skype for Business Server 功能。</span><span class="sxs-lookup"><span data-stu-id="ac282-186">In Skype for Business Server Enterprise Edition, the Front End Server is the core server role, and runs many basic Skype for Business Server functions.</span></span> <span data-ttu-id="ac282-187">前端服务器和后端服务器是任何 Skype for Business Server Enterprise Edition 部署中唯一需要的服务器角色。</span><span class="sxs-lookup"><span data-stu-id="ac282-187">The Front End Server, along with the Back End Servers, are the only server roles required to be in any Skype for Business Server Enterprise Edition deployment.</span></span>

<span data-ttu-id="ac282-188">“前端池”是一组配置相同的前端服务器，其协同工作为公用组用户提供服务。</span><span class="sxs-lookup"><span data-stu-id="ac282-188">A Front End pool is a set of Front End Servers, configured identically, that work together to provide services for a common group of users.</span></span> <span data-ttu-id="ac282-189">由多个运行同一角色的服务器构成的池提供可伸缩性和故障转移功能。</span><span class="sxs-lookup"><span data-stu-id="ac282-189">A pool of multiple servers running the same role provides scalability and failover capability.</span></span>

<span data-ttu-id="ac282-190">前端服务器包括以下功能：</span><span class="sxs-lookup"><span data-stu-id="ac282-190">The Front End Server includes the following:</span></span>

- <span data-ttu-id="ac282-191">用户身份验证和注册。</span><span class="sxs-lookup"><span data-stu-id="ac282-191">User authentication and registration.</span></span>

- <span data-ttu-id="ac282-192">状态信息和联系人卡片交换。</span><span class="sxs-lookup"><span data-stu-id="ac282-192">Presence information and contact card exchange.</span></span>

- <span data-ttu-id="ac282-193">通讯簿服务和通讯组列表扩展。</span><span class="sxs-lookup"><span data-stu-id="ac282-193">Address book services and distribution list expansion.</span></span>

- <span data-ttu-id="ac282-194">IM 功能，包括多方 IM 会议。</span><span class="sxs-lookup"><span data-stu-id="ac282-194">IM functionality, including multiparty IM conferences.</span></span>

- <span data-ttu-id="ac282-195">如果已部署 Web 会议、PSTN 电话拨入式会议和 A/V (，) 。</span><span class="sxs-lookup"><span data-stu-id="ac282-195">Web conferencing, PSTN Dial-in conferencing and A/V conferencing (if deployed).</span></span>

- <span data-ttu-id="ac282-196">应用程序托管，适用于 Skype for Business Server (，例如会议助理和响应组应用程序) 应用程序，以及第三方应用程序。</span><span class="sxs-lookup"><span data-stu-id="ac282-196">Application hosting, for both applications included with Skype for Business Server (for example, Conferencing Attendant and Response Group application), and third-party applications.</span></span>

- <span data-ttu-id="ac282-197">（可选）监控功能，用于以呼叫详细记录 (CDR) 和呼叫错误记录 (CER) 形式收集使用信息。</span><span class="sxs-lookup"><span data-stu-id="ac282-197">Optionally, Monitoring, to collect usage information in the form of call detail records (CDRs) and call error records (CERs).</span></span> <span data-ttu-id="ac282-198">此信息提供有关音频和视频会议 (的媒体) 呼叫和 A/V 企业语音网络的指标。</span><span class="sxs-lookup"><span data-stu-id="ac282-198">This information provides metrics about the quality of the media (audio and video) traversing your network for both Enterprise Voice calls and A/V conferences.</span></span>

- <span data-ttu-id="ac282-199">用于支持基于 Web 的任务的 Web 组件，如 Web 计划程序和联接启动器。</span><span class="sxs-lookup"><span data-stu-id="ac282-199">Web components to supported web-based tasks such as web scheduler and join launcher.</span></span>

- <span data-ttu-id="ac282-200">（可选）存档功能，用于存档 IM 通信和会议内容（出于合规性考虑）。</span><span class="sxs-lookup"><span data-stu-id="ac282-200">Optionally, Archiving, to archive IM communications and meeting content for compliance reasons.</span></span> <span data-ttu-id="ac282-201">有关详细信息，请参阅规划文档中的[Planning for Archiving](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-archiving)。</span><span class="sxs-lookup"><span data-stu-id="ac282-201">For details, see [Planning for Archiving](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-archiving) in the Planning documentation.</span></span>

    <span data-ttu-id="ac282-202">在 Lync Server 2010 和早期版本中，监控和存档是单独的服务器角色，不会并排在前端服务器上。</span><span class="sxs-lookup"><span data-stu-id="ac282-202">In Lync Server 2010 and prior versions, Monitoring and Archiving were separate server roles, not collocated on Front End Server.</span></span>

- <span data-ttu-id="ac282-203">（可选）如果启用持久聊天，则包括用于聊天室管理的持久聊天 Web 服务和用于文件上载/下载的持久聊天 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="ac282-203">Optionally, if Persistent chat is enabled, Persistent Chat Web Services for Chat Room Management and Persistent Chat Web Services for File Upload/Download.</span></span>

<span data-ttu-id="ac282-p120">前端池还是用户和会议数据的主存储。每个用户的相关信息将在池中的三个前端服务器之间复制，并将在后端服务器上进行备份。</span><span class="sxs-lookup"><span data-stu-id="ac282-p120">Front End Pools are also the primary store for user and conference data. Information about each user is replicated among three Front End Servers in the pool, and backed up on the Back End Servers.</span></span>

<span data-ttu-id="ac282-206">此外，部署中的一台前端服务器还运行中央管理服务器，中央管理服务器管理基本配置数据，并部署到所有运行 Skype for Business Server 的服务器。</span><span class="sxs-lookup"><span data-stu-id="ac282-206">Additionally, one Front End Server in the deployment also runs the Central Management Server, which manages and deploys basic configuration data to all servers running Skype for Business Server.</span></span> <span data-ttu-id="ac282-207">中央管理服务器还提供 Lync Server 命令行管理程序和文件传输功能。</span><span class="sxs-lookup"><span data-stu-id="ac282-207">The Central Management Server also provides Lync Server Management Shell and file transfer capabilities.</span></span>

<span data-ttu-id="ac282-208">后端服务器是运行数据库Microsoft SQL Server为前端池提供数据库服务的数据库服务器。</span><span class="sxs-lookup"><span data-stu-id="ac282-208">The Back End Servers are database servers running Microsoft SQL Server that provide the database services for the Front End pool.</span></span> <span data-ttu-id="ac282-209">后端服务器用作池的用户和会议数据的备份存储，是其他数据库（如响应组数据库）的主存储。</span><span class="sxs-lookup"><span data-stu-id="ac282-209">The Back End Servers serve as backup stores for the pool's user and conference data, and are the primary stores for other databases such as the Response Group database.</span></span> <span data-ttu-id="ac282-210">你可以拥有一台后端服务器，但建议故障转移 [Skype for Business Server](../high-availability-and-disaster-recovery/back-end-server.md) 中的后端服务器高可用性。</span><span class="sxs-lookup"><span data-stu-id="ac282-210">You can have a single Back End Server, but [Back End Server high availability in Skype for Business Server](../high-availability-and-disaster-recovery/back-end-server.md) is recommended for failover.</span></span> <span data-ttu-id="ac282-211">后端服务器不运行任何 Skype for Business Server 软件。</span><span class="sxs-lookup"><span data-stu-id="ac282-211">Back End Servers do not run any Skype for Business Server software.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ac282-212">建议不要将 Skype for Business Server 数据库与其他数据库并并。</span><span class="sxs-lookup"><span data-stu-id="ac282-212">We do not recommend collocating Skype for Business Server databases with other databases.</span></span> <span data-ttu-id="ac282-213">如果您这样做，可能会影响可用性和性能。</span><span class="sxs-lookup"><span data-stu-id="ac282-213">If you do so, availability and performance may be affected.</span></span>

> [!NOTE]
> <span data-ttu-id="ac282-214">SQL镜像在 Skype for Business Server 2015 中可用，但在 Skype for Business Server 2019 中不再受支持。</span><span class="sxs-lookup"><span data-stu-id="ac282-214">SQL Mirroring is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="ac282-215">AlwaysOn 可用性组、AlwaysOn 故障转移群集实例 (FCI) 和 SQL 故障转移群集方法在 Skype for Business Server 2019 中是首选。</span><span class="sxs-lookup"><span data-stu-id="ac282-215">The  AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering methods are preferred with Skype for Business Server 2019.</span></span>

<span data-ttu-id="ac282-216">存储在后端服务器数据库中的信息包括状态信息、用户的联系人列表、包含所有当前会议状态相关的永久数据的会议数据，以及会议安排数据。</span><span class="sxs-lookup"><span data-stu-id="ac282-216">Information stored in the Back End Server databases includes presence information, users' Contacts lists, conferencing data, including persistent data about the state of all current conferences, and conference scheduling data.</span></span>

### <a name="edge-server"></a><span data-ttu-id="ac282-217">边缘服务器</span><span class="sxs-lookup"><span data-stu-id="ac282-217">Edge Server</span></span>

<span data-ttu-id="ac282-218">边缘服务器使用户可以与组织防火墙之外的用户进行通信和协作。</span><span class="sxs-lookup"><span data-stu-id="ac282-218">Edge Server enables your users to communicate and collaborate with users outside the organization's firewalls.</span></span> <span data-ttu-id="ac282-219">这些外部用户可以包括当前在外部工作的组织内部用户、联盟伙伴组织的用户以及受邀加入 Skype for Business Server 部署上托管的会议的外部用户。</span><span class="sxs-lookup"><span data-stu-id="ac282-219">These external users can include the organization's own users who are currently working offsite, users from federated partner organizations, and outside users who have been invited to join conferences hosted on your Skype for Business Server deployment.</span></span>

<span data-ttu-id="ac282-220">部署边缘服务器还将启用移动服务，此服务支持移动设备上的 Lync 功能。</span><span class="sxs-lookup"><span data-stu-id="ac282-220">Deploying Edge Server also enables mobility services, which supports Lync functionality on mobile devices.</span></span> <span data-ttu-id="ac282-221">用户可以使用受支持的 Apple iOS、Android、Windows Phone 或 Nokia 移动设备来执行发送和接收即时消息、查看联系人和查看状态等活动。</span><span class="sxs-lookup"><span data-stu-id="ac282-221">Users can use supported Apple iOS, Android, Windows Phone, or Nokia mobile devices to perform activities such as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span> <span data-ttu-id="ac282-222">此外，移动设备还支持某些企业语音功能，例如，“单击加入会议”、“单位电话呼叫”、“一号通”、“语音邮件”和“错过的呼叫”。</span><span class="sxs-lookup"><span data-stu-id="ac282-222">In addition, mobile devices support some Enterprise Voice features, such as click to join a conference, Call via Work, single number reach, voice mail, and missed calls.</span></span> <span data-ttu-id="ac282-223">移动功能还支持针对不支持在后台运行的应用程序的移动设备的推送通知。</span><span class="sxs-lookup"><span data-stu-id="ac282-223">The mobility feature also supports push notifications for mobile devices that do not support applications running in the background.</span></span> <span data-ttu-id="ac282-224">推送通知是一类发送给移动设备的有关当移动设备处于不活动状态时发生的事件的通知。</span><span class="sxs-lookup"><span data-stu-id="ac282-224">A push notification is a notification that is sent to a mobile device about an event that occurs while a mobile application is inactive.</span></span>

<span data-ttu-id="ac282-225">边缘服务器还包括完全集成的可扩展消息传递和状态协议 (XMPP) 代理，以及前端服务器上包含的 XMPP 网关。</span><span class="sxs-lookup"><span data-stu-id="ac282-225">Edge Servers also include a fully-integrated Extensible Messaging and Presence Protocol (XMPP) proxy, with an XMPP gateway included on Front End Servers.</span></span> <span data-ttu-id="ac282-226">你可以配置这些 XMPP 组件以使 Skype for Business Server 用户能够添加来自基于 XMPP 的合作伙伴的联系人，以实现即时消息和状态。</span><span class="sxs-lookup"><span data-stu-id="ac282-226">You can configure these XMPP components to enable your Skype for Business Server users to add contacts from XMPP-based partners for instant messaging and presence.</span></span>

> [!NOTE]
> <span data-ttu-id="ac282-227">XMPP 网关和代理在 Skype for Business Server 2015 中可用，但在 Skype for Business Server 2019 中不再受支持。</span><span class="sxs-lookup"><span data-stu-id="ac282-227">XMPP Gateways and proxies are available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="ac282-228">有关详细信息 [，请参阅迁移 XMPP](../../../SfBServer2019/migration/migrating-xmpp-federation.md) 联盟。</span><span class="sxs-lookup"><span data-stu-id="ac282-228">See [Migrating XMPP federation](../../../SfBServer2019/migration/migrating-xmpp-federation.md) for more information.</span></span>

### <a name="mediation-server"></a><span data-ttu-id="ac282-229">中介服务器</span><span class="sxs-lookup"><span data-stu-id="ac282-229">Mediation Server</span></span>

<span data-ttu-id="ac282-230">中介服务器是实施电话企业语音电话拨入式会议的必要组件。</span><span class="sxs-lookup"><span data-stu-id="ac282-230">Mediation Server is a necessary component for implementing Enterprise Voice, Call Via Work, and dial-in conferencing.</span></span> <span data-ttu-id="ac282-231">中介服务器转换内部 Skype for Business Server 基础结构与公用电话交换网 (PSTN) 网关、IP-PBX 或会话初始协议 (SIP) 中继之间的信号（在某些配置中）媒体。</span><span class="sxs-lookup"><span data-stu-id="ac282-231">Mediation Server translates signaling, and, in some configurations, media between your internal Skype for Business Server infrastructure and a public switched telephone network (PSTN) gateway, IP-PBX, or a Session Initiation Protocol (SIP) trunk.</span></span> <span data-ttu-id="ac282-232">您可以运行在前端服务器所在的服务器上并置的中介服务器，也可以运行分隔到单独的中介服务器池中的中介服务器。</span><span class="sxs-lookup"><span data-stu-id="ac282-232">You can run Mediation Server collocated on the same server as Front End Server, or separated into a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="ac282-233">有关详细信息，请参阅[Mediation Server component in Skype for Business Server。](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md)</span><span class="sxs-lookup"><span data-stu-id="ac282-233">For details, see [Mediation Server component in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md).</span></span>

### <a name="video-interop-server"></a><span data-ttu-id="ac282-234">视频互操作服务器</span><span class="sxs-lookup"><span data-stu-id="ac282-234">Video Interop Server</span></span>

<span data-ttu-id="ac282-235">视频互操作服务器是自 Skype for Business Server 2015 起的新角色。</span><span class="sxs-lookup"><span data-stu-id="ac282-235">Video Interop Server is a new role as of Skype for Business Server 2015.</span></span> <span data-ttu-id="ac282-236">它使你能够将 Skype for Business Server 部署与某些第三方 VTC (视频电话会议系统) 解决方案。</span><span class="sxs-lookup"><span data-stu-id="ac282-236">It enables you to integrate your Skype for Business Server deployment with certain third-party VTC (Video Teleconferencing System) solutions.</span></span> <span data-ttu-id="ac282-237">VIS 充当第三方电话会议系统和 Skype for Business Server 部署之间的中介。</span><span class="sxs-lookup"><span data-stu-id="ac282-237">A VIS acts as an intermediary between a 3rd party teleconference system and a Skype for Business Server deployment.</span></span> <span data-ttu-id="ac282-238">对于此版本，VIS 侧重于与 Cisco/Tandberg 视频系统的互操作性。</span><span class="sxs-lookup"><span data-stu-id="ac282-238">For this release, VIS is focused on interoperability with Cisco/Tandberg video systems.</span></span>

<span data-ttu-id="ac282-239">有关详细信息，请参阅[Plan for Video Interop Server in Skype for Business Server。](../../plan-your-deployment/video-interop-server.md)</span><span class="sxs-lookup"><span data-stu-id="ac282-239">For details, see [Plan for Video Interop Server in Skype for Business Server](../../plan-your-deployment/video-interop-server.md).</span></span>

### <a name="director"></a><span data-ttu-id="ac282-240">主管</span><span class="sxs-lookup"><span data-stu-id="ac282-240">Director</span></span>

<span data-ttu-id="ac282-241">控制器可以验证 Skype for Business Server 用户请求，但它们不驻留用户帐户或提供状态或会议服务。</span><span class="sxs-lookup"><span data-stu-id="ac282-241">Directors can authenticate Skype for Business Server user requests, but they do not home user accounts or provide presence or conferencing services.</span></span> <span data-ttu-id="ac282-242">控制器对于增强支持外部用户访问的部署中的安全性最有用。</span><span class="sxs-lookup"><span data-stu-id="ac282-242">Directors are most useful to enhance security in deployments that enable external user access.</span></span> <span data-ttu-id="ac282-243">控制器可在将请求发送到内部服务器之前对请求进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="ac282-243">The Director can authenticate requests before sending them on to internal servers.</span></span> <span data-ttu-id="ac282-244">对于拒绝服务攻击，此攻击将终止于控制器且无法到达前端服务器。</span><span class="sxs-lookup"><span data-stu-id="ac282-244">In the case of a denial-of-service attack, the attack ends with the Director and does not reach the Front End servers.</span></span>

### <a name="persistent-chat-server-roles"></a><span data-ttu-id="ac282-245">持久聊天服务器角色</span><span class="sxs-lookup"><span data-stu-id="ac282-245">Persistent Chat Server Roles</span></span>

> [!NOTE]
> <span data-ttu-id="ac282-246">持久聊天在 Skype for Business Server 2015 中可用，但在 Skype for Business Server 2019 中不再受支持。</span><span class="sxs-lookup"><span data-stu-id="ac282-246">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="ac282-247">Teams 中提供了相同的功能。</span><span class="sxs-lookup"><span data-stu-id="ac282-247">The same functionality is available in Teams.</span></span> <span data-ttu-id="ac282-248">有关详细信息，请参阅 Microsoft Teams 升级 [入门](/microsoftteams/upgrade-start-here)。</span><span class="sxs-lookup"><span data-stu-id="ac282-248">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="ac282-249">如果需要使用持久聊天，你的选择是：将需要此功能的用户迁移到 Teams，或者继续使用 Skype for Business Server 2015。</span><span class="sxs-lookup"><span data-stu-id="ac282-249">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span>

<span data-ttu-id="ac282-p133">利用持久聊天，用户可以参加持续进行的、基于主题的多方对话。持久聊天前端服务器可运行持久聊天服务。持久聊天后端服务器可存储聊天历史记录数据以及有关类别和聊天室的信息。可选持久聊天合规性后端服务器可存储聊天内容和合规性事件以实现合规性。</span><span class="sxs-lookup"><span data-stu-id="ac282-p133">Persistent chat enables users to participate in multiparty, topic-based conversations that persist over time. The Persistent Chat Front End Server runs the persistent chat service. The Persistent Chat Back End Server stores the chat history data, and information about categories and chat rooms. The optional Persistent Chat Compliance Back End Server can store the chat content and compliance events for the purpose of compliance.</span></span>

<span data-ttu-id="ac282-254">运行 Skype for Business Server Standard Edition 的服务器还可以运行在同一台服务器上并插的持久聊天。</span><span class="sxs-lookup"><span data-stu-id="ac282-254">Servers running Skype for Business Server Standard Edition can also run Persistent chat collocated on the same server.</span></span> <span data-ttu-id="ac282-255">不能将持久聊天前端服务器与 Enterprise Edition 前端服务器并排。</span><span class="sxs-lookup"><span data-stu-id="ac282-255">You cannot collocate the Persistent Chat Front End Server with Enterprise Edition Front End Server.</span></span>

<span data-ttu-id="ac282-256">有关详细信息，请参阅[Plan for Persistent Chat Server in Skype for Business Server 2015。](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)</span><span class="sxs-lookup"><span data-stu-id="ac282-256">For details, see [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).</span></span>

## <a name="high-availability-and-disaster-recovery-support"></a><span data-ttu-id="ac282-257">高可用性和灾难恢复支持</span><span class="sxs-lookup"><span data-stu-id="ac282-257">High availability and disaster recovery support</span></span>

<span data-ttu-id="ac282-258">Skype for Business Server 通过池实现服务器冗余提供了高可用性。</span><span class="sxs-lookup"><span data-stu-id="ac282-258">Skype for Business Server provides high availability by server redundancy via pooling.</span></span> <span data-ttu-id="ac282-259">如果运行特定服务器角色的服务器发生故障，那么池中运行同一角色的其他服务器将接纳该服务器的负荷。</span><span class="sxs-lookup"><span data-stu-id="ac282-259">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="ac282-260">这适用于前端服务器、边缘服务器、中介服务器和控制器。</span><span class="sxs-lookup"><span data-stu-id="ac282-260">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span>

<span data-ttu-id="ac282-261">Skype for Business Server 还通过启用池配对提供灾难恢复措施。</span><span class="sxs-lookup"><span data-stu-id="ac282-261">Skype for Business Server also provides disaster recovery measures by enabling pool pairing.</span></span> <span data-ttu-id="ac282-262">如果您部署了此拓扑，则将指定前端池对，对中的每个池位于不同地理区域的不同数据中心。</span><span class="sxs-lookup"><span data-stu-id="ac282-262">If you deploy this topology, you will designate pairs of Front End pools, with each pool in a pair located in a separate data center, and in a separate geographical area.</span></span> <span data-ttu-id="ac282-263">如果一个池或一个站点不可用，则可将该池中的用户重定向至使用对中的其他池，并且对服务的干扰程度可以忽略不计。</span><span class="sxs-lookup"><span data-stu-id="ac282-263">If one pool or site goes down, you can redirect the users of that pool to use the other pool in the pair, with minimal interruption of service.</span></span>

<span data-ttu-id="ac282-264">Skype for Business Server 还支持用于后端服务器高可用性的几个选项。</span><span class="sxs-lookup"><span data-stu-id="ac282-264">Skype for Business Server also supports several options for Back End Server high availability.</span></span> <span data-ttu-id="ac282-265">其中包括以下项：</span><span class="sxs-lookup"><span data-stu-id="ac282-265">These include the following:</span></span>

- <span data-ttu-id="ac282-266">数据库镜像</span><span class="sxs-lookup"><span data-stu-id="ac282-266">Database mirroring</span></span>

- <span data-ttu-id="ac282-267">AlwaysOn 可用性组</span><span class="sxs-lookup"><span data-stu-id="ac282-267">AlwaysOn Availability Groups</span></span>

- <span data-ttu-id="ac282-268">AlwaysOn 故障转移群集实例 (FCI) </span><span class="sxs-lookup"><span data-stu-id="ac282-268">AlwaysOn Failover Cluster Instances (FCI)</span></span>

- <span data-ttu-id="ac282-269">SQL故障转移群集</span><span class="sxs-lookup"><span data-stu-id="ac282-269">SQL failover clustering</span></span>

<span data-ttu-id="ac282-270">有关池配对和后端服务器高可用性的详细信息，请参阅 Plan [for high availability and disaster recovery in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。</span><span class="sxs-lookup"><span data-stu-id="ac282-270">For details about pool pairing and Back End Server high availability, see [Plan for high availability and disaster recovery in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>

## <a name="server-collocation-in-skype-for-business-server"></a><span data-ttu-id="ac282-271">Skype for Business Server 中的服务器并置</span><span class="sxs-lookup"><span data-stu-id="ac282-271">Server collocation in Skype for Business Server</span></span>

<span data-ttu-id="ac282-272">我们已使用并集术语，但这意味着什么？</span><span class="sxs-lookup"><span data-stu-id="ac282-272">We've used the term collocate already, but what does this mean?</span></span> <span data-ttu-id="ac282-273">Skype for Business Server 允许你在同一台服务器（并置）或不同服务器上查找某些服务器角色和功能，但在你开始部署时，以及进行 Standard Edition 服务器部署还是 Enterprise Edition 服务器部署 (它们各自都有各自的规则) 。</span><span class="sxs-lookup"><span data-stu-id="ac282-273">Skype for Business Server allows you to locate some server roles and features on the same server, which is collocation, or on different servers, but it can be confusing when you're starting out, and whether you're doing a Standard Edition or Enterprise Edition server deployment (they each come with their own rules).</span></span> <span data-ttu-id="ac282-274">为了帮助进行规划，我们将服务器并置包括在 Standard Edition 服务器部署和企业版前端池部署 (在大多数情况下，此信息是相同的，如果该信息不同，则特别在) 中调用此信息。</span><span class="sxs-lookup"><span data-stu-id="ac282-274">To help with your planning, we're including server collocation in Standard Edition server deployments and Enterprise Edition Front End pool deployments (in most cases this information is identical, and where it's different, it's called out specifically).</span></span>

### <a name="collocation-of-server-roles"></a><span data-ttu-id="ac282-275">服务器角色并置</span><span class="sxs-lookup"><span data-stu-id="ac282-275">Collocation of server roles</span></span>

<span data-ttu-id="ac282-276">Standard Edition Server 具有以下角色并 (通过) 进行附加配置，而在 Enterprise Edition 前端池中，可以并并此角色，或将其部署到单独的服务器：</span><span class="sxs-lookup"><span data-stu-id="ac282-276">The Standard Edition server has the following role collocated (additional configuration is required though), while in the Enterprise Edition Front End pool, this role can be collocated, or deployed to a separate server:</span></span>

- <span data-ttu-id="ac282-277">中介</span><span class="sxs-lookup"><span data-stu-id="ac282-277">Mediation</span></span>

<span data-ttu-id="ac282-278">这些服务器角色必须分别部署在单独的服务器上：</span><span class="sxs-lookup"><span data-stu-id="ac282-278">These server roles must each be deployed on a separate server:</span></span>

- <span data-ttu-id="ac282-279">主管</span><span class="sxs-lookup"><span data-stu-id="ac282-279">Director</span></span>

- <span data-ttu-id="ac282-280">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="ac282-280">Edge</span></span>

- <span data-ttu-id="ac282-281">视频互操作服务器</span><span class="sxs-lookup"><span data-stu-id="ac282-281">Video Interop Server</span></span>

- <span data-ttu-id="ac282-282">Office Online</span><span class="sxs-lookup"><span data-stu-id="ac282-282">Office Web Apps</span></span>

### <a name="databases"></a><span data-ttu-id="ac282-283">Databases</span><span class="sxs-lookup"><span data-stu-id="ac282-283">Databases</span></span>

<span data-ttu-id="ac282-284">这是 Standard Edition Server 部署和 Enterprise Edition 服务器池部署之间存在实际差异的区域，因此我们将在下面介绍两个部分，后跟针对这两者的其他一些规则。</span><span class="sxs-lookup"><span data-stu-id="ac282-284">This is the area with real differences between Standard Edition server deployments and Enterprise Edition server pool deployments, so we'll have two sections below, followed by some additional rules for both.</span></span>

#### <a name="standard"></a><span data-ttu-id="ac282-285">标准</span><span class="sxs-lookup"><span data-stu-id="ac282-285">Standard</span></span>

<span data-ttu-id="ac282-286">由于 SQL Server Express 并位于 Standard Edition Server 上且无法移动，因此这非常简单。</span><span class="sxs-lookup"><span data-stu-id="ac282-286">Since SQL Server Express is collocated on the Standard Edition server, and can't be moved, this is pretty straightforward.</span></span> <span data-ttu-id="ac282-287">此外，如果在 Standard Edition 服务器上部署持久聊天服务器，则还可以在 Standard Edition 服务器上并集持久聊天和持久聊天合规性数据库，但不必这样。</span><span class="sxs-lookup"><span data-stu-id="ac282-287">Furthermore, if you deploy Persistent Chat Server on a Standard Edition server, you're also able to collocate the Persistent Chat and the Persistent Chat compliance database on the Standard Edition server too, but you don't have to.</span></span>

> [!NOTE]
> <span data-ttu-id="ac282-288">持久聊天在 Skype for Business Server 2015 中可用，但在 Skype for Business Server 2019 中不再受支持。</span><span class="sxs-lookup"><span data-stu-id="ac282-288">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="ac282-289">Teams 中提供了相同的功能。</span><span class="sxs-lookup"><span data-stu-id="ac282-289">The same functionality is available in Teams.</span></span> <span data-ttu-id="ac282-290">有关详细信息，请参阅 Microsoft Teams 升级 [入门](/microsoftteams/upgrade-start-here)。</span><span class="sxs-lookup"><span data-stu-id="ac282-290">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="ac282-291">如果需要使用持久聊天，你的选择是：将需要此功能的用户迁移到 Teams，或者继续使用 Skype for Business Server 2015。</span><span class="sxs-lookup"><span data-stu-id="ac282-291">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span>

<span data-ttu-id="ac282-292">这些服务器不能并并在 Standard Edition Server 上，但可以单独数据库服务器服务器：</span><span class="sxs-lookup"><span data-stu-id="ac282-292">These can't be collocated on the Standard Edition server, but can go on a single database server of their own:</span></span>

- <span data-ttu-id="ac282-293">监控数据库</span><span class="sxs-lookup"><span data-stu-id="ac282-293">Monitoring database</span></span>

- <span data-ttu-id="ac282-294">存档数据库</span><span class="sxs-lookup"><span data-stu-id="ac282-294">Archiving database</span></span>

- <span data-ttu-id="ac282-295">Enterprise Edition 前端池的任何后端数据库</span><span class="sxs-lookup"><span data-stu-id="ac282-295">Any back-end database for an Enterprise Edition Front End pool</span></span>

#### <a name="enterprise"></a><span data-ttu-id="ac282-296">企业</span><span class="sxs-lookup"><span data-stu-id="ac282-296">Enterprise</span></span>

<span data-ttu-id="ac282-297">以下数据库可以并位于同一后端SQL Server：</span><span class="sxs-lookup"><span data-stu-id="ac282-297">The following databases can be collocated on the same back end SQL Server:</span></span>

- <span data-ttu-id="ac282-298">后端数据库</span><span class="sxs-lookup"><span data-stu-id="ac282-298">Back End database</span></span>

- <span data-ttu-id="ac282-299">监控数据库</span><span class="sxs-lookup"><span data-stu-id="ac282-299">Monitoring database</span></span>

- <span data-ttu-id="ac282-300">存档数据库</span><span class="sxs-lookup"><span data-stu-id="ac282-300">Archiving database</span></span>

- <span data-ttu-id="ac282-301">持久聊天数据库</span><span class="sxs-lookup"><span data-stu-id="ac282-301">Persistent Chat database</span></span>

- <span data-ttu-id="ac282-302">持久聊天合规性数据库</span><span class="sxs-lookup"><span data-stu-id="ac282-302">Persistent Chat compliance database</span></span>

#### <a name="both"></a><span data-ttu-id="ac282-303">两者都有</span><span class="sxs-lookup"><span data-stu-id="ac282-303">Both</span></span>

<span data-ttu-id="ac282-304">现在，在单个 SQL 实例或同一数据库的多个 SQL 实例中并并 Skype for Business Server 数据库时，需要遵循一SQL Server规则：</span><span class="sxs-lookup"><span data-stu-id="ac282-304">Now, there are some additional rules to follow when collocating Skype for Business Server databases in a single SQL instance, or in multiple SQL instances in the same SQL Server database:</span></span>

- <span data-ttu-id="ac282-305">每个SQL实例只能包含 Enterprise Edition 前端池的一个后端数据库、一个监控数据库、一个存档数据库、一个持久聊天数据库和一个持久聊天合规性数据库。</span><span class="sxs-lookup"><span data-stu-id="ac282-305">Each SQL instance can only contain a single back end database for an Enterprise Edition Front End pool, a single Monitoring database, a single Archiving database, a single Persistent Chat database, and a single Persistent Chat compliance database.</span></span>

- <span data-ttu-id="ac282-306">数据库服务器 不能支持多个 Enterprise Edition 前端池、一台存档服务器、一台运行监控的服务器、一个持久聊天数据库和一个持久聊天合规性数据库，但它可以支持其中一个，无论数据库是使用相同的 SQL Server 实例还是使用 SQL Server 的单独实例。</span><span class="sxs-lookup"><span data-stu-id="ac282-306">The database server can't support more than one Enterprise Edition Front End pool, one server running Archiving, one server running Monitoring, a single Persistent Chat database, and a single Persistent Chat compliance database, but it can support one of each, regardless of whether the databases use the same instance of SQL Server or separate instances of SQL Server.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ac282-307">持久聊天在 Skype for Business Server 2015 中可用，但在 Skype for Business Server 2019 中不再受支持。</span><span class="sxs-lookup"><span data-stu-id="ac282-307">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="ac282-308">Teams 中提供了相同的功能。</span><span class="sxs-lookup"><span data-stu-id="ac282-308">The same functionality is available in Teams.</span></span> <span data-ttu-id="ac282-309">有关详细信息，请参阅 Microsoft Teams 升级 [入门](/microsoftteams/upgrade-start-here)。</span><span class="sxs-lookup"><span data-stu-id="ac282-309">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="ac282-310">如果需要使用持久聊天，你的选择是：将需要此功能的用户迁移到 Teams，或者继续使用 Skype for Business Server 2015。</span><span class="sxs-lookup"><span data-stu-id="ac282-310">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span>

### <a name="file-shares"></a><span data-ttu-id="ac282-311">文件共享</span><span class="sxs-lookup"><span data-stu-id="ac282-311">File shares</span></span>

<span data-ttu-id="ac282-312">文件共享可以位于单独的服务器上，也可以与以下任一或所有文件共享在同一服务器上：</span><span class="sxs-lookup"><span data-stu-id="ac282-312">The file share can be on a separate server, or you can collocate it on the same server as any or all of the following:</span></span>

- <span data-ttu-id="ac282-313">数据库服务器，包括 Enterprise Edition 前端池的后端服务器</span><span class="sxs-lookup"><span data-stu-id="ac282-313">Database server, including the Back End Server of an Enterprise Edition Front End pool</span></span>

- <span data-ttu-id="ac282-314">监控数据库</span><span class="sxs-lookup"><span data-stu-id="ac282-314">Monitoring database</span></span>

- <span data-ttu-id="ac282-315">存档数据库</span><span class="sxs-lookup"><span data-stu-id="ac282-315">Archiving database</span></span>

- <span data-ttu-id="ac282-316">持久聊天数据库</span><span class="sxs-lookup"><span data-stu-id="ac282-316">Persistent Chat database</span></span>

- <span data-ttu-id="ac282-317">持久聊天合规性数据库</span><span class="sxs-lookup"><span data-stu-id="ac282-317">Persistent Chat compliance database</span></span>

> [!CAUTION]
> <span data-ttu-id="ac282-318">请注意，虽然可以在这些服务器上并集文件共享，但必须注意，我们不建议这样做。</span><span class="sxs-lookup"><span data-stu-id="ac282-318">Note that while you can collocate the file share on these servers, it's vital to note that we don't recommend it.</span></span> <span data-ttu-id="ac282-319">如果要将文件共享与任何其他服务器角色并并，请确保定期监视磁盘空间和性能问题。</span><span class="sxs-lookup"><span data-stu-id="ac282-319">If you're collocating the file share with any other server role, please make sure you're monitoring for disk space and performance issues on a regular basis.</span></span>

### <a name="keep-in-mind"></a><span data-ttu-id="ac282-320">记住</span><span class="sxs-lookup"><span data-stu-id="ac282-320">Keep in mind</span></span>

- <span data-ttu-id="ac282-321">不能并并反向代理服务器，该服务器不是 Skype for Business Server 组件，甚至可能不在拓扑中。</span><span class="sxs-lookup"><span data-stu-id="ac282-321">You can't collocate a reverse proxy server, which isn't a Skype for Business Server component, and may not even be in your topology.</span></span> <span data-ttu-id="ac282-322">如果您希望支持联盟用户共享 Web 内容，除其他很多内容外，您还需要反向代理。</span><span class="sxs-lookup"><span data-stu-id="ac282-322">You'll need a reverse proxy if you want to support sharing of web content for federated users, among many other things.</span></span> <span data-ttu-id="ac282-323">如果需要，请继续操作，通过配置组织中已有的正由其他应用程序使用的现有反向代理服务器，为 Skype for Business Server 实现反向代理支持。</span><span class="sxs-lookup"><span data-stu-id="ac282-323">If you need to, go ahead and implement reverse proxy support for Skype for Business Server by configuring an existing reverse proxy server that's already in your organization that's being used by other applications.</span></span>

- <span data-ttu-id="ac282-324">不能将任何 Exchange UM 组件或 SharePoint Server 组件与任何 Skype for Business Server 角色并并。</span><span class="sxs-lookup"><span data-stu-id="ac282-324">You can't collocate any Exchange UM component or SharePoint Server component with any Skype for Business Server role.</span></span>

## <a name="see-also"></a><span data-ttu-id="ac282-325">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ac282-325">See also</span></span>

[<span data-ttu-id="ac282-326">Skype for Business Server 参考拓扑</span><span class="sxs-lookup"><span data-stu-id="ac282-326">Reference topologies for Skype for Business Server</span></span>](reference-topologies.md)