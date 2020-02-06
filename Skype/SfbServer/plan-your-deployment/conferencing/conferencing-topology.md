---
title: 规划 Skype for business Server 的会议拓扑
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
ms.assetid: 7392dfa7-791a-4723-88ff-0ef8a9ef11c8
description: 摘要：阅读本主题，了解如何在 Skype for Business 服务器中规划会议拓扑。
ms.openlocfilehash: 1b9d9024d90b4bd847c763747dad7a5f96616aa3
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816011"
---
# <a name="plan-your-conferencing-topology-for-skype-for-business-server"></a><span data-ttu-id="8eb22-103">规划 Skype for business Server 的会议拓扑</span><span class="sxs-lookup"><span data-stu-id="8eb22-103">Plan your conferencing topology for Skype for Business Server</span></span>
 
<span data-ttu-id="8eb22-104">**摘要：** 阅读本主题，了解如何在 Skype for Business 服务器中规划会议拓扑。</span><span class="sxs-lookup"><span data-stu-id="8eb22-104">**Summary:** Read this topic to learn about planning your conferencing topology in Skype for Business Server.</span></span>
  
<span data-ttu-id="8eb22-105">本主题介绍 Skype for business Server 中的会议拓扑基础知识：</span><span class="sxs-lookup"><span data-stu-id="8eb22-105">This topic describes topology basics for conferencing in Skype for Business Server:</span></span>
  
- <span data-ttu-id="8eb22-106">支持的拓扑</span><span class="sxs-lookup"><span data-stu-id="8eb22-106">Supported topologies</span></span>
    
- <span data-ttu-id="8eb22-107">电话拨入式会议注意事项</span><span class="sxs-lookup"><span data-stu-id="8eb22-107">Dial-in conferencing considerations</span></span>
    
- <span data-ttu-id="8eb22-108">Web 会议注意事项</span><span class="sxs-lookup"><span data-stu-id="8eb22-108">Web conferencing considerations</span></span>
    
- <span data-ttu-id="8eb22-109">大型会议的要求</span><span class="sxs-lookup"><span data-stu-id="8eb22-109">Requirements for large meetings</span></span>
    
<span data-ttu-id="8eb22-110">有关硬件和软件要求的详细信息，请参阅[Skype For Business 服务器中的会议硬件和软件要求](hardware-and-software-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8eb22-110">For more information about hardware and software requirements, see [Hardware and software requirements for conferencing in Skype for Business Server](hardware-and-software-requirements.md).</span></span>
  
## <a name="supported-topologies"></a><span data-ttu-id="8eb22-111">支持的拓扑</span><span class="sxs-lookup"><span data-stu-id="8eb22-111">Supported topologies</span></span>

<span data-ttu-id="8eb22-112">在 Skype for Business 服务器中，运行会议服务的服务器始终与前端服务器或标准版服务器 collocated。</span><span class="sxs-lookup"><span data-stu-id="8eb22-112">In Skype for Business Server, the server running conferencing services is always collocated with the Front End Servers or Standard Edition servers.</span></span> <span data-ttu-id="8eb22-113">部署 Skype for Business 服务器时，将自动部署即时消息会议功能。</span><span class="sxs-lookup"><span data-stu-id="8eb22-113">When you deploy Skype for Business Server, IM conferencing capabilities are automatically deployed.</span></span> <span data-ttu-id="8eb22-114">可以使用拓扑生成器来指定是否要部署 Web、音频和视频 (A/V) 以及电话拨入式会议。</span><span class="sxs-lookup"><span data-stu-id="8eb22-114">You can specify whether to deploy web, audio and video (A/V), and dial-in conferencing by using the Topology Builder.</span></span> <span data-ttu-id="8eb22-115">还可以使用拓扑生成器将会议添加到现有部署。</span><span class="sxs-lookup"><span data-stu-id="8eb22-115">You can also use Topology Builder to add conferencing to an existing deployment.</span></span> <span data-ttu-id="8eb22-116">有关拓扑基础知识和 collocation 方案的详细信息，请参阅[Skype for Business 服务器的拓扑基础知识](../../plan-your-deployment/topology-basics/topology-basics.md)。</span><span class="sxs-lookup"><span data-stu-id="8eb22-116">For details about topology basics and collocation scenarios, see [Topology Basics for Skype for Business Server](../../plan-your-deployment/topology-basics/topology-basics.md).</span></span>
  
<span data-ttu-id="8eb22-117">可以在以下拓扑和配置中部署会议：</span><span class="sxs-lookup"><span data-stu-id="8eb22-117">You can deploy conferencing in the following topologies and configurations:</span></span>
  
- <span data-ttu-id="8eb22-118">Skype for business 服务器标准版</span><span class="sxs-lookup"><span data-stu-id="8eb22-118">Skype for Business Server Standard Edition</span></span>
    
- <span data-ttu-id="8eb22-119">Skype for business Server 企业版</span><span class="sxs-lookup"><span data-stu-id="8eb22-119">Skype for Business Server Enterprise Edition</span></span>
    
- <span data-ttu-id="8eb22-120">使用或不使用企业语音</span><span class="sxs-lookup"><span data-stu-id="8eb22-120">With or without Enterprise Voice</span></span>
    
## <a name="dial-in-conferencing-considerations"></a><span data-ttu-id="8eb22-121">电话拨入式会议注意事项</span><span class="sxs-lookup"><span data-stu-id="8eb22-121">Dial-in conferencing considerations</span></span>

<span data-ttu-id="8eb22-122">如果要部署电话拨入式会议，必须考虑以下事项：</span><span class="sxs-lookup"><span data-stu-id="8eb22-122">If you are deploying dial-in conferencing, you must consider the following:</span></span>
  
- <span data-ttu-id="8eb22-123">电话拨入式会议需要中介服务器才能在 Skype for Business 服务器和 PSTN 网关之间转换信号（和媒体），以及用于在中介服务器和 PSTN 网关之间转换信号和媒体的 PSTN 网关.</span><span class="sxs-lookup"><span data-stu-id="8eb22-123">Dial-in conferencing requires a Mediation Server to translate signaling (and media in some configurations) between Skype for Business Server and the PSTN gateway, and a PSTN gateway to translate signaling and media between the Mediation Server and the PSTN gateway.</span></span>
    
   <span data-ttu-id="8eb22-124">需要先部署企业语音或中介服务器以及至少以下某项，然后才能配置电话拨入式会议：</span><span class="sxs-lookup"><span data-stu-id="8eb22-124">Before you can configure dial-in conferencing, you need to deploy either Enterprise Voice or a Mediation Server and at least one of the following:</span></span>
    
  - <span data-ttu-id="8eb22-125">PSTN 网关</span><span class="sxs-lookup"><span data-stu-id="8eb22-125">PSTN gateway</span></span>
    
  - <span data-ttu-id="8eb22-126">IP-PBX</span><span class="sxs-lookup"><span data-stu-id="8eb22-126">IP-PBX</span></span>
    
  - <span data-ttu-id="8eb22-127">会话边界控制器 (SBC)（用于通过配置 SIP 中继进行连接的 Internet 电话服务提供商）</span><span class="sxs-lookup"><span data-stu-id="8eb22-127">Session Border Controller (SBC) (for an Internet telephony service provider to which you connect by configuring a SIP trunk)</span></span>
    
- <span data-ttu-id="8eb22-128">可以在中央站点上部署应用程序服务、会议助理应用程序和会议通知应用程序，但不能部署在分支站点上。</span><span class="sxs-lookup"><span data-stu-id="8eb22-128">You can deploy the Application service, Conferencing Attendant application, and Conferencing Announcement application in a central site, but not in a branch site.</span></span>
    
- <span data-ttu-id="8eb22-129">您必须在部署 Skype for Business Server 会议的每个池中部署电话拨入式会议。</span><span class="sxs-lookup"><span data-stu-id="8eb22-129">You must deploy dial-in conferencing in every pool where you deploy Skype for Business Server conferencing.</span></span> <span data-ttu-id="8eb22-130">无需在每个池中分配访问号码，但必须在每个池中部署电话拨入式会议功能。</span><span class="sxs-lookup"><span data-stu-id="8eb22-130">You do not need to assign access numbers in every pool, but you must deploy the dial-in conferencing feature in every pool.</span></span> <span data-ttu-id="8eb22-131">当用户从一个池中调用访问号码以加入另一个池中的 Skype for Business Server 会议时，此要求支持录制的名称功能。</span><span class="sxs-lookup"><span data-stu-id="8eb22-131">This requirement supports the recorded name feature when a user calls an access number from one pool to join a Skype for Business Server conference in a different pool.</span></span> 
    
<span data-ttu-id="8eb22-132">有关详细信息，请参阅[在 Skype For Business 服务器中规划电话拨入式会议](dial-in-conferencing.md)。</span><span class="sxs-lookup"><span data-stu-id="8eb22-132">For more information, see [Plan for dial-in conferencing in Skype for Business Server](dial-in-conferencing.md).</span></span>
  
## <a name="web-conferencing-considerations"></a><span data-ttu-id="8eb22-133">Web 会议注意事项</span><span class="sxs-lookup"><span data-stu-id="8eb22-133">Web conferencing considerations</span></span>

<span data-ttu-id="8eb22-134">Web 会议需要以下条件：</span><span class="sxs-lookup"><span data-stu-id="8eb22-134">Web conferencing requires the following:</span></span> 
  
- <span data-ttu-id="8eb22-135">访问文件存储，文件存储用于存储 Web 会议内容。</span><span class="sxs-lookup"><span data-stu-id="8eb22-135">Access to the file store, which is used for storing web conferencing content.</span></span>
    
- <span data-ttu-id="8eb22-136">与 Office Web Apps Server/Office Online Server 集成，这是在会议期间要共享 PowerPoint 文件时需执行的步骤。</span><span class="sxs-lookup"><span data-stu-id="8eb22-136">Integration with Office Web Apps Server/Office Online Server, which is necessary in order to share PowerPoint files during a conference.</span></span>
    
> [!NOTE]
> <span data-ttu-id="8eb22-137">Office Web Apps 服务器的最新小版本称为 "Office Online Server"，该服务器受 Skype for Business 服务器支持。</span><span class="sxs-lookup"><span data-stu-id="8eb22-137">The latest iteration of Office Web Apps Server is named Office Online Server, which is supported by Skype for Business Server.</span></span> <span data-ttu-id="8eb22-138">有关更多详细信息，请参阅[Office Online Server 文档](https://technet.microsoft.com/en-us/library/jj219456%28v=office.16%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="8eb22-138">For more detail, refer to the [Office Online Server documentation](https://technet.microsoft.com/en-us/library/jj219456%28v=office.16%29.aspx).</span></span> 
  
<span data-ttu-id="8eb22-139">Skype for business 服务器提供以下方法来配置 Office Web Apps Server/Office Online Server。</span><span class="sxs-lookup"><span data-stu-id="8eb22-139">Skype for Business Server provides the following ways to configure Office Web Apps Server/Office Online Server.</span></span> <span data-ttu-id="8eb22-140">根据你的需要，你可以：</span><span class="sxs-lookup"><span data-stu-id="8eb22-140">Depending on your needs you can:</span></span>
  
- <span data-ttu-id="8eb22-141">**在组织的防火墙后面和同一网络区域中安装本地的 Skype for business Server 和 Office Web Apps 服务器/Office Online 服务器。**</span><span class="sxs-lookup"><span data-stu-id="8eb22-141">**Install both Skype for Business Server and Office Web Apps Server/Office Online Server on-premises behind your organization's firewall, and in the same network zone.**</span></span> <span data-ttu-id="8eb22-142">With this topology, external access to Office Web Apps Server/Office Online Server will be provided through your reverse proxy server.</span><span class="sxs-lookup"><span data-stu-id="8eb22-142">With this topology, external access to Office Web Apps Server/Office Online Server will be provided through your reverse proxy server.</span></span> <span data-ttu-id="8eb22-143">理想情况下，你应该在与 Skype for business 服务器相同的网络区域中安装 Office Web Apps Server/Office Online 服务器。</span><span class="sxs-lookup"><span data-stu-id="8eb22-143">Ideally, you should install Office Web Apps Server/Office Online Server in the same network zone as Skype for Business Server.</span></span>
    
    <span data-ttu-id="8eb22-144">外部 Skype for business 客户端可以使用反向代理服务器连接到 Skype for business 服务器和 Office Web Apps 服务器/Office Online 服务器，这是一个服务器，该服务器接受来自 Internet 的请求并将其转发到内部网络。</span><span class="sxs-lookup"><span data-stu-id="8eb22-144">External Skype for Business clients can connect to Skype for Business Server and to Office Web Apps Server/Office Online Server by using a reverse proxy server, which is a server that takes requests from the Internet and forwards them to the internal network.</span></span> <span data-ttu-id="8eb22-145">（内部客户端不需要使用反向代理服务器，因为它们可以直接连接到 Office Web Apps Server/Office Online 服务器。）如果你想要使用仅由 Skype for Business Server 使用的专用 Office Web Apps 服务器/Office Online 服务器场，此拓扑效果最佳。</span><span class="sxs-lookup"><span data-stu-id="8eb22-145">(Internal clients do not need to use the reverse proxy server because they can connect to Office Web Apps Server/Office Online Server directly.) This topology works best if you want to use a dedicated Office Web Apps Server/Office Online Server farm that is only used by Skype for Business Server.</span></span>
    
- <span data-ttu-id="8eb22-146">**使用外部部署的 Office Web Apps Server/Office Online 服务器。**</span><span class="sxs-lookup"><span data-stu-id="8eb22-146">**Use an externally deployed Office Web Apps Server/Office Online Server.**</span></span> <span data-ttu-id="8eb22-147">在此拓扑中，将在本地部署 Skype for business 服务器，并使用在 Skype for business 服务器网络区域外部部署的 Office Web Apps Server/Office Online 服务器。</span><span class="sxs-lookup"><span data-stu-id="8eb22-147">In this topology, Skype for Business Server is deployed on-premises, and uses an Office Web Apps Server/Office Online Server that is deployed outside of the Skype for Business Server network zone.</span></span> <span data-ttu-id="8eb22-148">如果 Office Web Apps 服务器/Office Online Server 在公司中的多个应用程序之间共享，并且部署在需要 Skype for Business 服务器的网络中使用 Office Web Apps Server/Office Online 服务器的外部接口，则可能会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="8eb22-148">This may happen when Office Web Apps Server/Office Online Server is shared across multiple applications in the corporation and is deployed in a network requiring Skype for Business Server to use the external interface of Office Web Apps Server/Office Online Server and vice versa.</span></span>
    
    <span data-ttu-id="8eb22-149">无需安装反向代理服务器;而是从 Office Web Apps Server/Office Online server 到 Skype for Business 服务器的所有请求都通过 Edge 服务器进行路由。</span><span class="sxs-lookup"><span data-stu-id="8eb22-149">You do not need to install a reverse proxy server; instead, all the requests from the Office Web Apps Server/Office Online Server to Skype for Business Server are routed through your Edge Server.</span></span> <span data-ttu-id="8eb22-150">您的内部和外部 Skype for business 客户端都使用外部 URL 连接到 Office Web Apps 服务器/Office Online 服务器。</span><span class="sxs-lookup"><span data-stu-id="8eb22-150">Both your internal and your external Skype for Business clients connect to Office Web Apps Server/Office Online Server using the external URL.</span></span>
    
    <span data-ttu-id="8eb22-151">如果 Office Web Apps Server/Office Online Server 部署在内部防火墙之外，那么在拓扑生成器中，请选择选项“**在外部网络(即，外围/Internet)中部署 Office Web Apps Server**”。</span><span class="sxs-lookup"><span data-stu-id="8eb22-151">If the Office Web Apps Server/Office Online Server is deployed outside your internal firewall, then select the option **Office Web Apps Server is deployed in an external network** (that is, perimeter/Internet) in Topology Builder.</span></span>
    
<span data-ttu-id="8eb22-152">有关详细信息，请参阅[在 Skype For Business 服务器中配置与 Office Web Apps 服务器的集成](../../deploy/deploy-conferencing/office-web-app-server.md)。</span><span class="sxs-lookup"><span data-stu-id="8eb22-152">For more information, see [Configure integration with Office Web Apps Server in Skype for Business Server](../../deploy/deploy-conferencing/office-web-app-server.md).</span></span> 
  
<span data-ttu-id="8eb22-153">无论你选择什么拓扑，打开正确的防火墙端口至关重要。</span><span class="sxs-lookup"><span data-stu-id="8eb22-153">Regardless of the topology you select, it is critical that the correct firewall ports be opened.</span></span> <span data-ttu-id="8eb22-154">你必须确保 DNS 名称、IP 地址和端口未被 Office Web Apps 服务器/Office Online 服务器、负载平衡器或 Skype for business 服务器上的防火墙阻止。</span><span class="sxs-lookup"><span data-stu-id="8eb22-154">You must make sure that DNS names, IP addresses, and ports are not blocked by firewalls on the Office Web Apps Server/Office Online Server, the load balancer, or Skype for Business Server.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8eb22-p110">提供对 Office Web Apps Server/Office Online Server 外部访问权限的另一个选项是在外围网络中部署服务器。如果选择执行此操作，请记住，Office Web Apps Server/Office Online Server 安装要求该服务器计算机是 Active Directory 域的成员。除非网络策略允许外围网络中的计算机成为 Active Directory 域成员，否则，建议不要在外围网络中安装 Office Web Apps Server/Office Online Server，而应在内部网络中安装 Office Web Apps Server/Office Online Server，并向外部用户提供通过反向代理服务器的访问权限。</span><span class="sxs-lookup"><span data-stu-id="8eb22-p110">Another option for providing external access to Office Web Apps Server/Office Online Server is to deploy the server in the perimeter network. If you elect to do this, keep in mind that Office Web Apps Server/Office Online Server setup requires the server computer to be a member of your Active Directory domain. Unless your network policy allows computers in the perimeter network to be Active Directory domain members, it is recommended that you do not install Office Web Apps Server/Office Online Server in the perimeter network. Instead, you should install Office Web Apps Server/Office Online Server in the internal network and provide external user access through your reverse proxy server.</span></span> 
  
## <a name="topology-requirements-for-large-meetings"></a><span data-ttu-id="8eb22-159">大型会议的拓扑要求</span><span class="sxs-lookup"><span data-stu-id="8eb22-159">Topology requirements for large meetings</span></span>

<span data-ttu-id="8eb22-p111">一个大型会议至少需要一个前端服务器和一个后端服务器。但为了提供高可用性，建议采用带镜像后端服务器的双前端服务器池，如下图所示：</span><span class="sxs-lookup"><span data-stu-id="8eb22-p111">A single large meeting requires at least one Front End Server and one Back End Server. However, to provide high availability, we recommend a two Front End Server pool with mirrored Back End Servers as shown in the following diagram:</span></span>
  
<span data-ttu-id="8eb22-162">**大型会议拓扑**</span><span class="sxs-lookup"><span data-stu-id="8eb22-162">**Large meeting topology**</span></span>

![大型会议拓扑](../../media/06858900-a262-4a47-96d0-51abd6827064.png)
  
<span data-ttu-id="8eb22-164">托管大型会议的用户必须将其用户帐户托管在前端池中。</span><span class="sxs-lookup"><span data-stu-id="8eb22-164">The user who hosts the large meetings must have their user account homed in Front End pool.</span></span> <span data-ttu-id="8eb22-165">但是，我们不建议你在此池中托管其他用户帐户。</span><span class="sxs-lookup"><span data-stu-id="8eb22-165">However, we do not recommend that you host other user accounts in this pool.</span></span> <span data-ttu-id="8eb22-166">而只是将其用于大型会议。</span><span class="sxs-lookup"><span data-stu-id="8eb22-166">Instead, use it only for the large meetings.</span></span> <span data-ttu-id="8eb22-167">最佳做法是在此池中创建一个仅用于托管大型会议的特殊用户帐户。</span><span class="sxs-lookup"><span data-stu-id="8eb22-167">The best practice is to create a special user account in this pool to be used only to host large meetings.</span></span> <span data-ttu-id="8eb22-168">由于大型会议设置已针对性能进行优化，因此将其用作普通用户可能会遇到问题，例如在涉及 PSTN 终结点时无法将 P2P 会话提升到会议。</span><span class="sxs-lookup"><span data-stu-id="8eb22-168">Since the large meeting setting is optimized for performance, using it as a normal user could have problems such as the inability to promote a P2P session to a meeting when a PSTN endpoint is involved.</span></span>
  
<span data-ttu-id="8eb22-p113">在管理恰好包含两个前端服务器的池时，有一些特别注意事项。有关详细信息，请参阅 [Topology Basics for Skype for Business Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md) 和 [Reference topologies for Skype for Business Server 2015](../../plan-your-deployment/topology-basics/reference-topologies.md)。</span><span class="sxs-lookup"><span data-stu-id="8eb22-p113">Managing a pool with exactly two Front End Servers requires some special considerations. For more information, see [Topology Basics for Skype for Business Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md) and [Reference topologies for Skype for Business Server 2015](../../plan-your-deployment/topology-basics/reference-topologies.md).</span></span>
  
<span data-ttu-id="8eb22-171">此外，如果您希望选择性地提供针对用于大型会议的池的灾难恢复备份和故障转移，您可以将该池与其他数据中心内类似的设置专用池配对。</span><span class="sxs-lookup"><span data-stu-id="8eb22-171">Additionally, if you want to optionally provide disaster recovery backup and failover for the pool used for large meetings, you can pair it with a similarly set up dedicated pool in a different data center.</span></span> <span data-ttu-id="8eb22-172">有关详细信息，请参阅[在 Skype For Business 服务器中规划高可用性和灾难恢复](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。</span><span class="sxs-lookup"><span data-stu-id="8eb22-172">For details, see [Plan for high availability and disaster recovery in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  
<span data-ttu-id="8eb22-173">有关拓扑的其他说明包括：</span><span class="sxs-lookup"><span data-stu-id="8eb22-173">Additional notes about the topology include:</span></span>
  
- <span data-ttu-id="8eb22-174">文件共享是存储会议内容所必需的，如果已部署和启用存档服务器，则文件共享是存储存档文件所必需的。</span><span class="sxs-lookup"><span data-stu-id="8eb22-174">A file share is required for storing meeting content and, if Archiving Server is deployed and enabled, for storing the archiving files.</span></span> <span data-ttu-id="8eb22-175">文件共享可专用于池，也可以是已部署该池的站点中的另一个池所使用的同一文件共享。</span><span class="sxs-lookup"><span data-stu-id="8eb22-175">The file share can be dedicated to the pool or can be the same file share used by another pool at the site in which the pool is deployed.</span></span> <span data-ttu-id="8eb22-176">有关配置文件共享的详细信息，请参阅[在 Skype For Business Server 2015 中创建文件共享](../../deploy/install/create-a-file-share.md)。</span><span class="sxs-lookup"><span data-stu-id="8eb22-176">For details about configuring the file share, see [Create a file share in Skype for Business Server 2015](../../deploy/install/create-a-file-share.md).</span></span>
    
- <span data-ttu-id="8eb22-177">Office Web Apps Server/Office Online Server 是在大型会议中启用 PowerPoint 演示文稿功能所必需的。</span><span class="sxs-lookup"><span data-stu-id="8eb22-177">An Office Web Apps Server/Office Online Server is required for enabling the PowerPoint presentation functionality in large meetings.</span></span> <span data-ttu-id="8eb22-178">Office Web Apps Server/Office Online Server 可专用于大型会议池，也可以是已部署专用池的站点中的其他池所使用的同一个 Office Web Apps Server/Office Online Server。</span><span class="sxs-lookup"><span data-stu-id="8eb22-178">The Office Web Apps Server/Office Online Server can be dedicated to the large meeting pool or, it can be the same Office Web Apps Server/Office Online Server used by other pools at the site in which the dedicated pool is deployed.</span></span> <span data-ttu-id="8eb22-179">有关详细信息，请参阅[在 Skype For Business 服务器中配置与 Office Web Apps 服务器的集成](../../deploy/deploy-conferencing/office-web-app-server.md)。</span><span class="sxs-lookup"><span data-stu-id="8eb22-179">For more information, see [Configure integration with Office Web Apps Server in Skype for Business Server](../../deploy/deploy-conferencing/office-web-app-server.md).</span></span> 
    
- <span data-ttu-id="8eb22-p117">若要实现前端服务器的负载平衡，需要实现 HTTP 流量（如会议内容下载）的硬件负载平衡。建议对 SIP 流量实现 DNS 负载平衡。有关详细信息，请参阅 [Load balancing requirements for Skype for Business](../../plan-your-deployment/network-requirements/load-balancing.md)。</span><span class="sxs-lookup"><span data-stu-id="8eb22-p117">Load balancing of the Front End Servers requires hardware load balancing for the HTTP traffic (such as meeting content download). DNS load balancing is recommended for SIP traffic. For details see [Load balancing requirements for Skype for Business](../../plan-your-deployment/network-requirements/load-balancing.md).</span></span> 
    
- <span data-ttu-id="8eb22-183">如果要对专用大型会议池使用监视服务器，我们建议使用监视服务器及其在 Skype for Business Server 部署中的所有前端服务器池共享的数据库。</span><span class="sxs-lookup"><span data-stu-id="8eb22-183">If you want to use Monitoring Server for the dedicated large-meeting pool, we recommend using the Monitoring Server and its database that are shared across all of the Front End Server pools in your Skype for Business Server deployment.</span></span> <span data-ttu-id="8eb22-184">有关详细信息，请参阅[在 Skype For Business 服务器中规划监视](../../plan-your-deployment/monitoring.md)。</span><span class="sxs-lookup"><span data-stu-id="8eb22-184">For more information, see [Plan for monitoring in Skype for Business Server](../../plan-your-deployment/monitoring.md).</span></span>
    

