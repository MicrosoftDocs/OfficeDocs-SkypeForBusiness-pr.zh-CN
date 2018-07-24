---
title: 规划业务 Server Skype 的会议拓扑
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7392dfa7-791a-4723-88ff-0ef8a9ef11c8
description: 摘要： 阅读本主题可了解有关规划业务服务器中 Skype 会议拓扑。
ms.openlocfilehash: 3110588585291ccfb55b45750d336863fea7329b
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "21006123"
---
# <a name="plan-your-conferencing-topology-for-skype-for-business-server"></a><span data-ttu-id="80b1f-103">规划业务 Server Skype 的会议拓扑</span><span class="sxs-lookup"><span data-stu-id="80b1f-103">Plan your conferencing topology for Skype for Business Server</span></span>
 
<span data-ttu-id="80b1f-104">**摘要：** 阅读本主题可了解如何规划业务服务器中 Skype 会议拓扑。</span><span class="sxs-lookup"><span data-stu-id="80b1f-104">**Summary:** Read this topic to learn about planning your conferencing topology in Skype for Business Server.</span></span>
  
<span data-ttu-id="80b1f-105">本主题介绍为企业服务器拓扑的 Skype 中的会议的基础知识：</span><span class="sxs-lookup"><span data-stu-id="80b1f-105">This topic describes topology basics for conferencing in Skype for Business Server:</span></span>
  
- <span data-ttu-id="80b1f-106">支持的拓扑</span><span class="sxs-lookup"><span data-stu-id="80b1f-106">Supported topologies</span></span>
    
- <span data-ttu-id="80b1f-107">电话拨入式会议注意事项</span><span class="sxs-lookup"><span data-stu-id="80b1f-107">Dial-in conferencing considerations</span></span>
    
- <span data-ttu-id="80b1f-108">Web 会议注意事项</span><span class="sxs-lookup"><span data-stu-id="80b1f-108">Web conferencing considerations</span></span>
    
- <span data-ttu-id="80b1f-109">大型会议的要求</span><span class="sxs-lookup"><span data-stu-id="80b1f-109">Requirements for large meetings</span></span>
    
<span data-ttu-id="80b1f-110">有关硬件和软件要求的详细信息，请参阅[Skype 业务服务器中的会议的硬件和软件要求](hardware-and-software-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="80b1f-110">For more information about hardware and software requirements, see [Hardware and software requirements for conferencing in Skype for Business Server](hardware-and-software-requirements.md).</span></span>
  
## <a name="supported-topologies"></a><span data-ttu-id="80b1f-111">支持的拓扑</span><span class="sxs-lookup"><span data-stu-id="80b1f-111">Supported topologies</span></span>

<span data-ttu-id="80b1f-112">在业务服务器 Skype，运行会议服务的服务器是始终与并置的前端服务器或 Standard Edition 服务器。</span><span class="sxs-lookup"><span data-stu-id="80b1f-112">In Skype for Business Server, the server running conferencing services is always collocated with the Front End Servers or Standard Edition servers.</span></span> <span data-ttu-id="80b1f-113">在部署 Skype 业务服务器时，会自动部署 IM 会议功能。</span><span class="sxs-lookup"><span data-stu-id="80b1f-113">When you deploy Skype for Business Server, IM conferencing capabilities are automatically deployed.</span></span> <span data-ttu-id="80b1f-114">可以使用拓扑生成器来指定是否要部署 Web、音频和视频 (A/V) 以及电话拨入式会议。</span><span class="sxs-lookup"><span data-stu-id="80b1f-114">You can specify whether to deploy web, audio and video (A/V), and dial-in conferencing by using the Topology Builder.</span></span> <span data-ttu-id="80b1f-115">还可以使用拓扑生成器将会议添加到现有部署。</span><span class="sxs-lookup"><span data-stu-id="80b1f-115">You can also use Topology Builder to add conferencing to an existing deployment.</span></span> <span data-ttu-id="80b1f-116">有关详细信息拓扑基础知识和并置方案，请参阅[拓扑的 Skype 业务服务器的基础知识](../../plan-your-deployment/topology-basics/topology-basics.md)。</span><span class="sxs-lookup"><span data-stu-id="80b1f-116">For details about topology basics and collocation scenarios, see [Topology Basics for Skype for Business Server](../../plan-your-deployment/topology-basics/topology-basics.md).</span></span>
  
<span data-ttu-id="80b1f-117">可以在以下拓扑和配置中部署会议：</span><span class="sxs-lookup"><span data-stu-id="80b1f-117">You can deploy conferencing in the following topologies and configurations:</span></span>
  
- <span data-ttu-id="80b1f-118">对于业务 Server Standard Edition 的 Skype</span><span class="sxs-lookup"><span data-stu-id="80b1f-118">Skype for Business Server Standard Edition</span></span>
    
- <span data-ttu-id="80b1f-119">对于业务 Server Enterprise Edition 的 Skype</span><span class="sxs-lookup"><span data-stu-id="80b1f-119">Skype for Business Server Enterprise Edition</span></span>
    
- <span data-ttu-id="80b1f-120">使用或不使用企业语音</span><span class="sxs-lookup"><span data-stu-id="80b1f-120">With or without Enterprise Voice</span></span>
    
## <a name="dial-in-conferencing-considerations"></a><span data-ttu-id="80b1f-121">电话拨入式会议注意事项</span><span class="sxs-lookup"><span data-stu-id="80b1f-121">Dial-in conferencing considerations</span></span>

<span data-ttu-id="80b1f-122">如果要部署电话拨入式会议，必须考虑以下事项：</span><span class="sxs-lookup"><span data-stu-id="80b1f-122">If you are deploying dial-in conferencing, you must consider the following:</span></span>
  
-  <span data-ttu-id="80b1f-123">电话拨入式会议 Skype 业务服务器和 PSTN 网关和 PSTN 网关翻译中介服务器与 PSTN 网关之间信号和媒体之间需要中介服务器转换信号 （和媒体的一些配置）.</span><span class="sxs-lookup"><span data-stu-id="80b1f-123">Dial-in conferencing requires a Mediation Server to translate signaling (and media in some configurations) between Skype for Business Server and the PSTN gateway, and a PSTN gateway to translate signaling and media between the Mediation Server and the PSTN gateway.</span></span>
    
    <span data-ttu-id="80b1f-124">需要先部署企业语音或中介服务器以及至少以下某项，然后才能配置电话拨入式会议：</span><span class="sxs-lookup"><span data-stu-id="80b1f-124">Before you can configure dial-in conferencing, you need to deploy either Enterprise Voice or a Mediation Server and at least one of the following:</span></span>
    
  - <span data-ttu-id="80b1f-125">PSTN 网关</span><span class="sxs-lookup"><span data-stu-id="80b1f-125">PSTN gateway</span></span>
    
  - <span data-ttu-id="80b1f-126">IP-PBX</span><span class="sxs-lookup"><span data-stu-id="80b1f-126">IP-PBX</span></span>
    
  - <span data-ttu-id="80b1f-127">会话边界控制器 (SBC)（用于通过配置 SIP 中继进行连接的 Internet 电话服务提供商）</span><span class="sxs-lookup"><span data-stu-id="80b1f-127">Session Border Controller (SBC) (for an Internet telephony service provider to which you connect by configuring a SIP trunk)</span></span>
    
- <span data-ttu-id="80b1f-128">可以在中央站点上部署应用程序服务、会议助理应用程序和会议通知应用程序，但不能部署在分支站点上。</span><span class="sxs-lookup"><span data-stu-id="80b1f-128">You can deploy the Application service, Conferencing Attendant application, and Conferencing Announcement application in a central site, but not in a branch site.</span></span>
    
- <span data-ttu-id="80b1f-129">您必须部署中每个池部署 Skype Business Server 会议电话拨入式会议。</span><span class="sxs-lookup"><span data-stu-id="80b1f-129">You must deploy dial-in conferencing in every pool where you deploy Skype for Business Server conferencing.</span></span> <span data-ttu-id="80b1f-130">无需在每个池中分配访问号码，但必须在每个池中部署电话拨入式会议功能。</span><span class="sxs-lookup"><span data-stu-id="80b1f-130">You do not need to assign access numbers in every pool, but you must deploy the dial-in conferencing feature in every pool.</span></span> <span data-ttu-id="80b1f-131">当用户从一个池加入 Business Server 会议池中不同 Skype 呼叫访问号码，这一要求支持录制的名称功能。</span><span class="sxs-lookup"><span data-stu-id="80b1f-131">This requirement supports the recorded name feature when a user calls an access number from one pool to join a Skype for Business Server conference in a different pool.</span></span> 
    
<span data-ttu-id="80b1f-132">有关详细信息，请参阅[规划中的业务服务器的 Skype 电话拨入式会议](dial-in-conferencing.md)。</span><span class="sxs-lookup"><span data-stu-id="80b1f-132">For more information, see [Plan for dial-in conferencing in Skype for Business Server](dial-in-conferencing.md).</span></span>
  
## <a name="web-conferencing-considerations"></a><span data-ttu-id="80b1f-133">Web 会议注意事项</span><span class="sxs-lookup"><span data-stu-id="80b1f-133">Web conferencing considerations</span></span>

<span data-ttu-id="80b1f-134">Web 会议需要以下条件：</span><span class="sxs-lookup"><span data-stu-id="80b1f-134">Web conferencing requires the following:</span></span> 
  
- <span data-ttu-id="80b1f-135">访问文件存储，文件存储用于存储 Web 会议内容。</span><span class="sxs-lookup"><span data-stu-id="80b1f-135">Access to the file store, which is used for storing web conferencing content.</span></span>
    
- <span data-ttu-id="80b1f-136">与 Office Web Apps Server/Office Online Server 集成，这是在会议期间要共享 PowerPoint 文件时需执行的步骤。</span><span class="sxs-lookup"><span data-stu-id="80b1f-136">Integration with Office Web Apps Server/Office Online Server, which is necessary in order to share PowerPoint files during a conference.</span></span>
    
> [!NOTE]
> <span data-ttu-id="80b1f-137">Office Web Apps Server 的最新小名为 Office Online Server，业务服务器支持的 Skype。</span><span class="sxs-lookup"><span data-stu-id="80b1f-137">The latest iteration of Office Web Apps Server is named Office Online Server, which is supported by Skype for Business Server.</span></span> <span data-ttu-id="80b1f-138">有关详细信息，请参阅[Office Online Server 文档](https://technet.microsoft.com/en-us/library/jj219456%28v=office.16%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="80b1f-138">For more detail, refer to the [Office Online Server documentation](https://technet.microsoft.com/en-us/library/jj219456%28v=office.16%29.aspx).</span></span> 
  
<span data-ttu-id="80b1f-139">Skype 业务服务器提供了下列方式来配置 Office Web Apps Server/Office Online Server。</span><span class="sxs-lookup"><span data-stu-id="80b1f-139">Skype for Business Server provides the following ways to configure Office Web Apps Server/Office Online Server.</span></span> <span data-ttu-id="80b1f-140">根据你的需要，你可以：</span><span class="sxs-lookup"><span data-stu-id="80b1f-140">Depending on your needs you can:</span></span>
  
- <span data-ttu-id="80b1f-141">**安装 Business Server 和 Office Web Apps Server/Office Online Server 内部部署组织的防火墙背后处于和相同的网络区域中的两个 Skype。**</span><span class="sxs-lookup"><span data-stu-id="80b1f-141">**Install both Skype for Business Server and Office Web Apps Server/Office Online Server on-premises behind your organization's firewall, and in the same network zone.**</span></span> <span data-ttu-id="80b1f-142">借助此拓扑，将通过反向代理服务器提供对 Office Web Apps Server/Office Online Server 的外部访问权限。</span><span class="sxs-lookup"><span data-stu-id="80b1f-142">With this topology, external access to Office Web Apps Server/Office Online Server will be provided through your reverse proxy server.</span></span> <span data-ttu-id="80b1f-143">理想情况下，您应安装 Office Web Apps Server/Office Online Server 在同一个网络区域中作为 Skype 业务服务器。</span><span class="sxs-lookup"><span data-stu-id="80b1f-143">Ideally, you should install Office Web Apps Server/Office Online Server in the same network zone as Skype for Business Server.</span></span>
    
    <span data-ttu-id="80b1f-144">外部 Skype 业务客户端可以使用反向代理服务器，它是从 Internet 接受请求，并将它们转发到内部网络的服务器连接到业务服务器 Skype 和 Office Web Apps Server/Office Online Server。</span><span class="sxs-lookup"><span data-stu-id="80b1f-144">External Skype for Business clients can connect to Skype for Business Server and to Office Web Apps Server/Office Online Server by using a reverse proxy server, which is a server that takes requests from the Internet and forwards them to the internal network.</span></span> <span data-ttu-id="80b1f-145">（内部客户端不需要使用反向代理服务器，因为他们可以直接连接到 Office Web Apps Server/Office Online Server。）如果您想要使用的业务服务器仅由 Skype 使用专用的 Office Web Apps Server/Office Online Server 服务器场，这种拓扑最有效。</span><span class="sxs-lookup"><span data-stu-id="80b1f-145">(Internal clients do not need to use the reverse proxy server because they can connect to Office Web Apps Server/Office Online Server directly.) This topology works best if you want to use a dedicated Office Web Apps Server/Office Online Server farm that is only used by Skype for Business Server.</span></span>
    
- <span data-ttu-id="80b1f-146">**使用外部部署的 Office Web Apps Server/Office Online 服务器。**</span><span class="sxs-lookup"><span data-stu-id="80b1f-146">**Use an externally deployed Office Web Apps Server/Office Online Server.**</span></span> <span data-ttu-id="80b1f-147">在此拓扑中，Skype 业务服务器部署在内部部署，并使用 Office Web Apps Server/Office Online Server Business Server 网络区域的 Skype 外部部署。</span><span class="sxs-lookup"><span data-stu-id="80b1f-147">In this topology, Skype for Business Server is deployed on-premises, and uses an Office Web Apps Server/Office Online Server that is deployed outside of the Skype for Business Server network zone.</span></span> <span data-ttu-id="80b1f-148">Office Web Apps Server/Office Online Server 跨公司中的多个应用程序共享和需要 Skype 供业务服务器使用 Office Web Apps Server/Office Online 服务器的外部接口的网络中部署时可能发生这种情况反之亦然。</span><span class="sxs-lookup"><span data-stu-id="80b1f-148">This may happen when Office Web Apps Server/Office Online Server is shared across multiple applications in the corporation and is deployed in a network requiring Skype for Business Server to use the external interface of Office Web Apps Server/Office Online Server and vice versa.</span></span>
    
    <span data-ttu-id="80b1f-149">不需要安装一个反向代理服务器。相反，所有与 Office Web Apps Server/Office Online Server 对请求的企业服务器的 Skype 通过边缘服务器进行路由。</span><span class="sxs-lookup"><span data-stu-id="80b1f-149">You do not need to install a reverse proxy server; instead, all the requests from the Office Web Apps Server/Office Online Server to Skype for Business Server are routed through your Edge Server.</span></span> <span data-ttu-id="80b1f-150">内部和您的业务客户端的外部 Skype 连接到 Office 应用程序服务器/Office Online 使用 Web 服务器的外部 URL。</span><span class="sxs-lookup"><span data-stu-id="80b1f-150">Both your internal and your external Skype for Business clients connect to Office Web Apps Server/Office Online Server using the external URL.</span></span>
    
    <span data-ttu-id="80b1f-151">如果 Office Web Apps Server/Office Online Server 部署在内部防火墙之外，那么在拓扑生成器中，请选择选项“**在外部网络(即，外围/Internet)中部署 Office Web Apps Server**”。</span><span class="sxs-lookup"><span data-stu-id="80b1f-151">If the Office Web Apps Server/Office Online Server is deployed outside your internal firewall, then select the option **Office Web Apps Server is deployed in an external network** (that is, perimeter/Internet) in Topology Builder.</span></span>
    
<span data-ttu-id="80b1f-152">有关详细信息，请参阅[配置与 Skype 的业务服务器中的 Office Web Apps Server 的集成](../../deploy/deploy-conferencing/office-web-app-server.md)。</span><span class="sxs-lookup"><span data-stu-id="80b1f-152">For more information, see [Configure integration with Office Web Apps Server in Skype for Business Server](../../deploy/deploy-conferencing/office-web-app-server.md).</span></span> 
  
<span data-ttu-id="80b1f-153">无论你选择什么拓扑，打开正确的防火墙端口至关重要。</span><span class="sxs-lookup"><span data-stu-id="80b1f-153">Regardless of the topology you select, it is critical that the correct firewall ports be opened.</span></span> <span data-ttu-id="80b1f-154">您必须确保的 DNS 名称、 IP 地址和端口不会被阻止的 Office Web Apps Server/Office Online Server、 负载平衡器或 Skype 上的防火墙业务服务器。</span><span class="sxs-lookup"><span data-stu-id="80b1f-154">You must make sure that DNS names, IP addresses, and ports are not blocked by firewalls on the Office Web Apps Server/Office Online Server, the load balancer, or Skype for Business Server.</span></span>
  
> [!NOTE]
> <span data-ttu-id="80b1f-p110">提供对 Office Web Apps Server/Office Online Server 外部访问权限的另一个选项是在外围网络中部署服务器。如果选择执行此操作，请记住，Office Web Apps Server/Office Online Server 安装要求该服务器计算机是 Active Directory 域的成员。除非网络策略允许外围网络中的计算机成为 Active Directory 域成员，否则，建议不要在外围网络中安装 Office Web Apps Server/Office Online Server，而应在内部网络中安装 Office Web Apps Server/Office Online Server，并向外部用户提供通过反向代理服务器的访问权限。</span><span class="sxs-lookup"><span data-stu-id="80b1f-p110">Another option for providing external access to Office Web Apps Server/Office Online Server is to deploy the server in the perimeter network. If you elect to do this, keep in mind that Office Web Apps Server/Office Online Server setup requires the server computer to be a member of your Active Directory domain. Unless your network policy allows computers in the perimeter network to be Active Directory domain members, it is recommended that you do not install Office Web Apps Server/Office Online Server in the perimeter network. Instead, you should install Office Web Apps Server/Office Online Server in the internal network and provide external user access through your reverse proxy server.</span></span> 
  
## <a name="topology-requirements-for-large-meetings"></a><span data-ttu-id="80b1f-159">大型会议的拓扑要求</span><span class="sxs-lookup"><span data-stu-id="80b1f-159">Topology requirements for large meetings</span></span>

<span data-ttu-id="80b1f-p111">一个大型会议至少需要一个前端服务器和一个后端服务器。但为了提供高可用性，建议采用带镜像后端服务器的双前端服务器池，如下图所示：</span><span class="sxs-lookup"><span data-stu-id="80b1f-p111">A single large meeting requires at least one Front End Server and one Back End Server. However, to provide high availability, we recommend a two Front End Server pool with mirrored Back End Servers as shown in the following diagram:</span></span>
  
<span data-ttu-id="80b1f-162">**大型会议拓扑**</span><span class="sxs-lookup"><span data-stu-id="80b1f-162">**Large meeting topology**</span></span>

![大型会议拓扑](../../media/06858900-a262-4a47-96d0-51abd6827064.png)
  
<span data-ttu-id="80b1f-164">承载大型会议的用户必须具有其用户帐户驻留在前端池。</span><span class="sxs-lookup"><span data-stu-id="80b1f-164">The user who hosts the large meetings must have their user account homed in Front End pool.</span></span> <span data-ttu-id="80b1f-165">但是，我们不建议您承载此池中的其他用户帐户。</span><span class="sxs-lookup"><span data-stu-id="80b1f-165">However, we do not recommend that you host other user accounts in this pool.</span></span> <span data-ttu-id="80b1f-166">相反，仅对大型会议使用它。</span><span class="sxs-lookup"><span data-stu-id="80b1f-166">Instead, use it only for the large meetings.</span></span> <span data-ttu-id="80b1f-167">最佳做法是仅对主机大型会议使用此池中创建特殊用户帐户。</span><span class="sxs-lookup"><span data-stu-id="80b1f-167">The best practice is to create a special user account in this pool to be used only to host large meetings.</span></span> <span data-ttu-id="80b1f-168">由于性能进行了优化的大型会议设置，使用作为普通用户可能会遇到问题，如无法升级到会议的 P2P 会话时涉及的 PSTN 方终结点。</span><span class="sxs-lookup"><span data-stu-id="80b1f-168">Since the large meeting setting is optimized for performance, using it as a normal user could have problems such as the inability to promote a P2P session to a meeting when a PSTN endpoint is involved.</span></span>
  
<span data-ttu-id="80b1f-169">在管理恰好包含两个前端服务器的池时，有一些特别注意事项。</span><span class="sxs-lookup"><span data-stu-id="80b1f-169">Managing a pool with exactly two Front End Servers requires some special considerations.</span></span> <span data-ttu-id="80b1f-170">有关详细信息，请参阅[拓扑的业务服务器 2015年的 Skype 的基础知识](../../plan-your-deployment/topology-basics/topology-basics.md)和[业务服务器 2015年的 Skype 的参考拓扑](../../plan-your-deployment/topology-basics/reference-topologies.md)。</span><span class="sxs-lookup"><span data-stu-id="80b1f-170">For more information, see [Topology Basics for Skype for Business Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md) and [Reference topologies for Skype for Business Server 2015](../../plan-your-deployment/topology-basics/reference-topologies.md).</span></span>
  
<span data-ttu-id="80b1f-171">此外，如果您希望选择性地提供针对用于大型会议的池的灾难恢复备份和故障转移，您可以将该池与其他数据中心内类似的设置专用池配对。</span><span class="sxs-lookup"><span data-stu-id="80b1f-171">Additionally, if you want to optionally provide disaster recovery backup and failover for the pool used for large meetings, you can pair it with a similarly set up dedicated pool in a different data center.</span></span> <span data-ttu-id="80b1f-172">有关详细信息，请参阅[规划高可用性和灾难恢复 Skype 业务服务器中](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。</span><span class="sxs-lookup"><span data-stu-id="80b1f-172">For details, see [Plan for high availability and disaster recovery in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  
<span data-ttu-id="80b1f-173">有关拓扑的其他说明包括：</span><span class="sxs-lookup"><span data-stu-id="80b1f-173">Additional notes about the topology include:</span></span>
  
- <span data-ttu-id="80b1f-174">文件共享是存储会议内容所必需的，如果已部署和启用存档服务器，则文件共享是存储存档文件所必需的。</span><span class="sxs-lookup"><span data-stu-id="80b1f-174">A file share is required for storing meeting content and, if Archiving Server is deployed and enabled, for storing the archiving files.</span></span> <span data-ttu-id="80b1f-175">文件共享可专用于池，也可以是已部署该池的站点中的另一个池所使用的同一文件共享。</span><span class="sxs-lookup"><span data-stu-id="80b1f-175">The file share can be dedicated to the pool or can be the same file share used by another pool at the site in which the pool is deployed.</span></span> <span data-ttu-id="80b1f-176">有关配置文件共享的详细信息，请参阅[创建文件共享中的业务服务器 2015 Skype](../../deploy/install/create-a-file-share.md)。</span><span class="sxs-lookup"><span data-stu-id="80b1f-176">For details about configuring the file share, see [Create a file share in Skype for Business Server 2015](../../deploy/install/create-a-file-share.md).</span></span>
    
- <span data-ttu-id="80b1f-177">Office Web Apps Server/Office Online Server 是在大型会议中启用 PowerPoint 演示文稿功能所必需的。</span><span class="sxs-lookup"><span data-stu-id="80b1f-177">An Office Web Apps Server/Office Online Server is required for enabling the PowerPoint presentation functionality in large meetings.</span></span> <span data-ttu-id="80b1f-178">Office Web Apps Server/Office Online Server 可专用于大型会议池，也可以是已部署专用池的站点中的其他池所使用的同一个 Office Web Apps Server/Office Online Server。</span><span class="sxs-lookup"><span data-stu-id="80b1f-178">The Office Web Apps Server/Office Online Server can be dedicated to the large meeting pool or, it can be the same Office Web Apps Server/Office Online Server used by other pools at the site in which the dedicated pool is deployed.</span></span> <span data-ttu-id="80b1f-179">有关详细信息，请参阅[配置与 Skype 的业务服务器中的 Office Web Apps Server 的集成](../../deploy/deploy-conferencing/office-web-app-server.md)。</span><span class="sxs-lookup"><span data-stu-id="80b1f-179">For more information, see [Configure integration with Office Web Apps Server in Skype for Business Server](../../deploy/deploy-conferencing/office-web-app-server.md).</span></span> 
    
- <span data-ttu-id="80b1f-180">若要实现前端服务器的负载平衡，需要实现 HTTP 流量（如会议内容下载）的硬件负载平衡。</span><span class="sxs-lookup"><span data-stu-id="80b1f-180">Load balancing of the Front End Servers requires hardware load balancing for the HTTP traffic (such as meeting content download).</span></span> <span data-ttu-id="80b1f-181">建议对 SIP 流量实现 DNS 负载平衡。</span><span class="sxs-lookup"><span data-stu-id="80b1f-181">DNS load balancing is recommended for SIP traffic.</span></span> <span data-ttu-id="80b1f-182">有关详细信息，请参阅[负载平衡的 Skype 的业务要求](../../plan-your-deployment/network-requirements/load-balancing.md)。</span><span class="sxs-lookup"><span data-stu-id="80b1f-182">For details see [Load balancing requirements for Skype for Business](../../plan-your-deployment/network-requirements/load-balancing.md).</span></span> 
    
- <span data-ttu-id="80b1f-183">如果您想要使用专用的大型会议池的监控服务器，我们建议对业务服务器部署中您 Skype 的前端服务器池的所有使用监控服务器和共享其数据库。</span><span class="sxs-lookup"><span data-stu-id="80b1f-183">If you want to use Monitoring Server for the dedicated large-meeting pool, we recommend using the Monitoring Server and its database that are shared across all of the Front End Server pools in your Skype for Business Server deployment.</span></span> <span data-ttu-id="80b1f-184">有关详细信息，请参阅[规划中的业务服务器 Skype 监控](../../plan-your-deployment/monitoring.md)。</span><span class="sxs-lookup"><span data-stu-id="80b1f-184">For more information, see [Plan for monitoring in Skype for Business Server](../../plan-your-deployment/monitoring.md).</span></span>
    

