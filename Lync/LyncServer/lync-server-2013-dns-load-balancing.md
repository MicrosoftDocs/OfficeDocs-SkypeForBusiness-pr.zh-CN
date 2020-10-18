---
title: Lync Server 2013： DNS 负载平衡
description: Lync Server 2013： DNS 负载平衡。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS load balancing
ms:assetid: 7ed0ed20-33ad-4253-926d-21d392590ae7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398634(v=OCS.15)
ms:contentKeyID: 48184625
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba95604ca8f4007c76cedea9bf2a16dbd7db455c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574418"
---
# <a name="dns-load-balancing-in-lync-server-2013"></a><span data-ttu-id="1ac9e-103">Lync Server 2013 中的 DNS 负载平衡</span><span class="sxs-lookup"><span data-stu-id="1ac9e-103">DNS load balancing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1ac9e-104">_**上次修改的主题：** 2014-01-15_</span><span class="sxs-lookup"><span data-stu-id="1ac9e-104">_**Topic Last Modified:** 2014-01-15_</span></span>

<span data-ttu-id="1ac9e-105">Lync Server 支持 DNS 负载平衡，这是一种可显著降低网络上负载平衡的管理开销的软件解决方案。</span><span class="sxs-lookup"><span data-stu-id="1ac9e-105">Lync Server enables DNS load balancing, a software solution that can greatly reduce the administration overhead for load balancing on your network.</span></span> <span data-ttu-id="1ac9e-106">DNS 负载平衡将平衡 Lync Server 特有的网络流量，如 SIP 流量和媒体流量。</span><span class="sxs-lookup"><span data-stu-id="1ac9e-106">DNS load balancing balances the network traffic that is unique to Lync Server, such as SIP traffic and media traffic.</span></span>

<span data-ttu-id="1ac9e-107">如果您部署了 DNS 负载平衡，则组织的硬件负载平衡器的管理开销将会最小化。</span><span class="sxs-lookup"><span data-stu-id="1ac9e-107">If you deploy DNS load balancing, your organization’s administration overhead for hardware load balancers will be minimized.</span></span> <span data-ttu-id="1ac9e-108">此外，还可以免除解决 SIP 流量负载平衡器配置错误相关问题的复杂过程。</span><span class="sxs-lookup"><span data-stu-id="1ac9e-108">Additionally, complex troubleshooting of problems related to misconfiguration of load balancers for SIP traffic will be eliminated.</span></span> <span data-ttu-id="1ac9e-109">您还可以阻止服务器连接以使服务器脱机。</span><span class="sxs-lookup"><span data-stu-id="1ac9e-109">You can also prevent server connections so that you can take servers offline.</span></span> <span data-ttu-id="1ac9e-110">同时，DNS 负载平衡还可确保硬件负载平衡器问题不会影响 SIP 流量的元素，例如基本呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="1ac9e-110">DNS load balancing also ensures that hardware load balancer problems do not affect elements of SIP traffic such as basic call routing.</span></span>

<span data-ttu-id="1ac9e-111">与为所有类型的流量使用硬件负载平衡器相比，使用 DNS 负载平衡还可以降低您购买硬件负载平衡器的成本。</span><span class="sxs-lookup"><span data-stu-id="1ac9e-111">If you use DNS load balancing, you may also be able to purchase lower-cost hardware load balancers than if you used the hardware load balancers for all types of traffic.</span></span> <span data-ttu-id="1ac9e-112">应使用与 Lync Server 的互操作性限定测试的负载平衡器。</span><span class="sxs-lookup"><span data-stu-id="1ac9e-112">You should use load balancers that have passed interoperability qualification testing with Lync Server.</span></span> <span data-ttu-id="1ac9e-113">有关负载平衡器互操作性测试的详细信息，请参阅 at 中的 "Lync Server 2010 负载平衡器合作伙伴" [https://go.microsoft.com/fwlink/p/?linkId=202452](https://go.microsoft.com/fwlink/p/?linkid=202452) 。</span><span class="sxs-lookup"><span data-stu-id="1ac9e-113">For details about load balancer interoperability testing, see "Lync Server 2010 Load Balancer Partners" at [https://go.microsoft.com/fwlink/p/?linkId=202452](https://go.microsoft.com/fwlink/p/?linkid=202452).</span></span>

<span data-ttu-id="1ac9e-114">前端池、边缘服务器池、控制器池和独立的中介服务器池都支持 DNS 负载平衡。</span><span class="sxs-lookup"><span data-stu-id="1ac9e-114">DNS load balancing is supported for Front End pools, Edge Server pools, Director pools, and stand-alone Mediation Server pools.</span></span>

<div>

## <a name="dns-load-balancing-on-front-end-pools-and-director-pools"></a><span data-ttu-id="1ac9e-115">前端池和控制器池中的 DNS 负载平衡</span><span class="sxs-lookup"><span data-stu-id="1ac9e-115">DNS Load Balancing on Front End Pools and Director Pools</span></span>

<span data-ttu-id="1ac9e-p104">您可以使用 DNS 负载平衡来平衡前端池和控制器池中的 SIP 流量。部署 DNS 负载平衡后，仍需要对这些池使用硬件负载平衡器，但仅用于客户端到服务器的 HTTPS 流量。硬件负载平衡器用于通过端口 443 和 80 从客户端传入的 HTTPS 流量。</span><span class="sxs-lookup"><span data-stu-id="1ac9e-p104">You can use DNS load balancing for the SIP traffic on Front End pools and Director pools. With DNS load balancing deployed, you still need to also use hardware load balancers for these pools, but only for client-to-server HTTPS traffic. The hardware load balancer is used for HTTPS traffic from clients over ports 443 and 80.</span></span>

<span data-ttu-id="1ac9e-119">尽管这些池中仍需要硬件负载平衡器，但这些负载平衡器的安装和管理主要用于硬件负载平衡器管理员熟悉的 HTTPS 流量。</span><span class="sxs-lookup"><span data-stu-id="1ac9e-119">Although you still need hardware load balancers for these pools, their setup and administration will be primarily for HTTPS traffic, which the administrators of hardware load balancers are accustomed to.</span></span>

<div>

## <a name="dns-load-balancing-and-supporting-older-clients-and-servers"></a><span data-ttu-id="1ac9e-120">支持旧客户端和服务器并对其进行 DNS 负载平衡</span><span class="sxs-lookup"><span data-stu-id="1ac9e-120">DNS Load Balancing and Supporting Older Clients and Servers</span></span>

<span data-ttu-id="1ac9e-121">DNS 负载平衡仅支持运行 Lync Server 2013 或 Lync Server 2010 的服务器以及 Lync 2013 和 Lync 2010 客户端的自动故障转移。</span><span class="sxs-lookup"><span data-stu-id="1ac9e-121">DNS load balancing supports automatic failover only for servers running Lync Server 2013 or Lync Server 2010, and for Lync 2013 and Lync 2010 clients.</span></span> <span data-ttu-id="1ac9e-122">早期版本的客户端和 Office 通信服务器仍可以连接到运行 DNS 负载平衡的池，但如果无法连接到 DNS 负载平衡所引用的第一台服务器，则它们无法故障转移到池中的另一台服务器。</span><span class="sxs-lookup"><span data-stu-id="1ac9e-122">Earlier versions of clients and Office Communications Server can still connect to pools running DNS load balancing, but if they cannot make a connection to the first server that DNS load balancing refers them to, they are unable to fail over to another server in the pool.</span></span>

<span data-ttu-id="1ac9e-123">此外，如果您使用的是 Exchange UM，则必须至少使用 Exchange 2010 SP1 以获取对 Lync Server DNS 负载平衡的支持。</span><span class="sxs-lookup"><span data-stu-id="1ac9e-123">Additionally, if you are using Exchange UM, you must use a minimum of Exchange 2010 SP1 to get support for Lync Server DNS load balancing.</span></span> <span data-ttu-id="1ac9e-124">如果使用的是早期版本的 Exchange，则用户将不会具有这些 Exchange UM 方案的故障转移功能：</span><span class="sxs-lookup"><span data-stu-id="1ac9e-124">If you use an earlier version of Exchange, your users will not have failover capabilities for these Exchange UM scenarios:</span></span>

  - <span data-ttu-id="1ac9e-125">在其电话上播放“企业语音”语音邮件</span><span class="sxs-lookup"><span data-stu-id="1ac9e-125">Playing their Enterprise Voice voice mail on their phone</span></span>

  - <span data-ttu-id="1ac9e-126">转接来自 Exchange UM 自动助理的呼叫</span><span class="sxs-lookup"><span data-stu-id="1ac9e-126">Transferring calls from an Exchange UM Auto Attendant</span></span>

<span data-ttu-id="1ac9e-127">其他所有 Exchange UM 方案将正常工作。</span><span class="sxs-lookup"><span data-stu-id="1ac9e-127">All other Exchange UM scenarios will work properly.</span></span>

</div>

<div>

## <a name="deploying-dns-load-balancing-on-front-end-pools-and-director-pools"></a><span data-ttu-id="1ac9e-128">在前端池和控制器池中部署 DNS 负载平衡</span><span class="sxs-lookup"><span data-stu-id="1ac9e-128">Deploying DNS Load Balancing on Front End Pools and Director Pools</span></span>

<span data-ttu-id="1ac9e-129">在前端池和控制器池中部署 DNS 负载平衡时，需要使用 FQDN 和 DNS 记录执行一些额外步骤。</span><span class="sxs-lookup"><span data-stu-id="1ac9e-129">Deploying DNS load balancing on Front End pools and Director pools requires you to perform a couple of extra steps with FQDNs and DNS records.</span></span>

  - <span data-ttu-id="1ac9e-130">使用 DNS 负载平衡的池必须具有两个 FQDN：一个是 DNS 负载平衡使用的常规池 FQDN（例如 pool01.contoso.com），它解析为该池中服务器的物理 IP；另一个是池的 Web 服务的 FQDN（例如 web01.contoso.com），它解析为该池的虚拟 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="1ac9e-130">A pool that uses DNS load balancing must have two FQDNs: the regular pool FQDN that is used by DNS load balancing (such as pool01.contoso.com), and resolves to the physical IPs of the servers in the pool, and another FQDN for the pool’s Web services (such as web01.contoso.com), which resolves to virtual IP address of the pool.</span></span>
    
    <span data-ttu-id="1ac9e-131">在拓扑生成器中，如果要为池部署 DNS 负载平衡，若要为池的 Web 服务创建此额外的 FQDN，必须选中 " **覆盖内部 Web 服务池 FQDN** " 复选框，并在 " **指定此池的 Web 服务 url** " 页中键入 FQDN。</span><span class="sxs-lookup"><span data-stu-id="1ac9e-131">In Topology Builder, if you want to deploy DNS load balancing for a pool, to create this extra FQDN for the pool’s Web services you must select the **Override internal Web Services pool FQDN** check box and type the FQDN, in the **Specify the Web Services URLs for this Pool** page.</span></span>

  - <span data-ttu-id="1ac9e-p107">要支持 DNS 负载平衡使用的 FQDN，必须设置 DNS，以便将池 FQDN（例如 pool01.contoso.com）解析为该池中所有服务器的 IP 地址（例如，192.168.1.1、192.168.1.2 等）。您应该仅包含当前部署的服务器的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="1ac9e-p107">To support the FQDN used by DNS load balancing, you must provision DNS to resolve the pool FQDN (such as pool01.contoso.com) to the IP addresses of all the servers in the pool (for example, 192.168.1.1, 192.168.1.2, and so on). You should include only the IP addresses of servers that are currently deployed.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="1ac9e-134">如果您有多个前端池或前端服务器，则外部 Web 服务 FQDN 必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="1ac9e-134">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="1ac9e-135">例如，如果将前端服务器的外部 Web 服务 FQDN 定义为 <STRONG>pool01.contoso.com</STRONG>，则不能将 <STRONG>pool01.contoso.com</STRONG> 用于另一个前端池或前端服务器。</span><span class="sxs-lookup"><span data-stu-id="1ac9e-135">For example, if you define the external Web services FQDN of a Front End Server as <STRONG>pool01.contoso.com</STRONG>, you cannot use <STRONG>pool01.contoso.com</STRONG> for another Front End pool or Front End Server.</span></span> <span data-ttu-id="1ac9e-136">如果还部署控制器，则为任何控制器或控制器池定义的外部 Web 服务 FQDN 必须与任何其他控制器或控制器池以及任何前端池或前端服务器都是唯一的。</span><span class="sxs-lookup"><span data-stu-id="1ac9e-136">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span> <span data-ttu-id="1ac9e-137">如果决定使用自定义的 FQDN 覆盖内部 web 服务，则每个 FQDN 必须与任何其他前端池、控制器或控制器池都是唯一的。</span><span class="sxs-lookup"><span data-stu-id="1ac9e-137">If decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>

    
    </div>

</div>

</div>

<div>

## <a name="dns-load-balancing-on-edge-server-pools"></a><span data-ttu-id="1ac9e-138">边缘服务器池中的 DNS 负载平衡</span><span class="sxs-lookup"><span data-stu-id="1ac9e-138">DNS Load Balancing on Edge Server Pools</span></span>

<span data-ttu-id="1ac9e-p109">您可以在边缘服务器池中部署 DNS 负载平衡。如果要进行部署，则必须了解以下注意事项。</span><span class="sxs-lookup"><span data-stu-id="1ac9e-p109">You can deploy DNS load balancing on Edge Server pools. If you do, you must be aware of some considerations.</span></span>

<span data-ttu-id="1ac9e-141">在边缘服务器中使用 DNS 负载平衡会导致以下方案中丧失故障转移功能：</span><span class="sxs-lookup"><span data-stu-id="1ac9e-141">Using DNS load balancing on your Edge Servers causes a loss of failover ability in the following scenarios:</span></span>

  - <span data-ttu-id="1ac9e-142">与运行在 Lync Server 2010 之前发布的 Office 通信服务器版本的组织进行联盟。</span><span class="sxs-lookup"><span data-stu-id="1ac9e-142">Federation with organizations that are running versions of Office Communications Server released prior to Lync Server 2010.</span></span>

  - <span data-ttu-id="1ac9e-143">\!除了基于 XMPP 的提供商和服务器（如 Google 谈话）之外，与公共即时消息用户 (IM) Services AOLand Yahoo 的即时消息交换。</span><span class="sxs-lookup"><span data-stu-id="1ac9e-143">Instant message exchange with users of public instant messaging (IM) services AOLand Yahoo\!, in addition to XMPP-based providers and servers, such as Google Talk.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="1ac9e-144">Google 谈话目前是唯一受支持的 XMPP 合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="1ac9e-144">Google Talk is currently the only supported XMPP partner.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="1ac9e-145">从2012年9月1日起，Microsoft Lync 公共 IM 连接用户订阅许可证 ( "PIC USL" ) 不再可用于购买新的或更新的协议。</span><span class="sxs-lookup"><span data-stu-id="1ac9e-145">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="1ac9e-146">拥有主动许可证的客户将能够继续与 Yahoo！联合联合</span><span class="sxs-lookup"><span data-stu-id="1ac9e-146">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="1ac9e-147">信使，直到服务关闭日期。</span><span class="sxs-lookup"><span data-stu-id="1ac9e-147">Messenger until the service shut down date.</span></span> <span data-ttu-id="1ac9e-148">AOL 和 Yahoo！的生命周期结束日期为2014年6月</span><span class="sxs-lookup"><span data-stu-id="1ac9e-148">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="1ac9e-149">已宣布。</span><span class="sxs-lookup"><span data-stu-id="1ac9e-149">has been announced.</span></span> <span data-ttu-id="1ac9e-150">有关详细信息，请参阅 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的支持公用即时信使连接</A>。</span><span class="sxs-lookup"><span data-stu-id="1ac9e-150">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P></LI></UL>

    
    </div>

<span data-ttu-id="1ac9e-151">只要池中的所有边缘服务器都在运行，这些方案就会正常工作；但是如果某台边缘服务器不可用，则发送到该服务器的对这些方案的所有请求都将失败，而不会路由到其他边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="1ac9e-151">These scenarios will work as long as all Edge Servers in the pool are up and running, but if one Edge Server is unavailable, any requests for these scenarios that are sent to it will fail, instead of routing to another Edge Server.</span></span>

<span data-ttu-id="1ac9e-152">如果使用的是 Exchange UM，则必须至少使用 Exchange 2013 以获取对边缘上的 Lync Server DNS 负载平衡的支持。</span><span class="sxs-lookup"><span data-stu-id="1ac9e-152">If you are using Exchange UM, you must use a minimum of Exchange 2013 to get support for Lync Server DNS load balancing on Edge.</span></span> <span data-ttu-id="1ac9e-153">如果使用较早版本的 Exchange，则远程用户对这些 Exchange UM 方案不具有故障转移功能：</span><span class="sxs-lookup"><span data-stu-id="1ac9e-153">If you use an earlier version of Exchange, your remote users will not have failover capabilities for these Exchange UM scenarios:</span></span>

  - <span data-ttu-id="1ac9e-154">在其电话上播放“企业语音”语音邮件</span><span class="sxs-lookup"><span data-stu-id="1ac9e-154">Playing their Enterprise Voice voice mail on their phone</span></span>

  - <span data-ttu-id="1ac9e-155">转接来自 Exchange UM 自动助理的呼叫</span><span class="sxs-lookup"><span data-stu-id="1ac9e-155">Transferring calls from an Exchange UM Auto Attendant</span></span>

<span data-ttu-id="1ac9e-156">其他所有 Exchange UM 方案将正常工作。</span><span class="sxs-lookup"><span data-stu-id="1ac9e-156">All other Exchange UM scenarios will work properly.</span></span>

<span data-ttu-id="1ac9e-p112">内部边缘接口和外部边缘接口必须使用同一类型的负载平衡。您不能对一个边缘接口使用 DNS 负载平衡，而对另一个边缘接口使用硬件负载平衡。</span><span class="sxs-lookup"><span data-stu-id="1ac9e-p112">The internal Edge interface and external Edge interface must use the same type of load balancing. You cannot use DNS load balancing on one Edge interface and hardware load balancing on the other Edge interface.</span></span>

<div>

## <a name="deploying-dns-load-balancing-on-edge-server-pools"></a><span data-ttu-id="1ac9e-159">在边缘服务器池中部署 DNS 负载平衡</span><span class="sxs-lookup"><span data-stu-id="1ac9e-159">Deploying DNS Load Balancing on Edge Server Pools</span></span>

<span data-ttu-id="1ac9e-160">要在边缘服务器池的外部接口上部署 DNS 负载平衡，需要具有以下 DNS 条目：</span><span class="sxs-lookup"><span data-stu-id="1ac9e-160">To deploy DNS load balancing on the external interface of your Edge Server pool, you need the following DNS entries:</span></span>

  - <span data-ttu-id="1ac9e-161">对于访问边缘服务，池中的每台服务器都需要一个条目。</span><span class="sxs-lookup"><span data-stu-id="1ac9e-161">For the Access Edge service, you need one entry for each server in the pool.</span></span> <span data-ttu-id="1ac9e-162">每个条目都必须解析访问边缘服务 (的 FQDN，例如，sip.contoso.com) 到池中某一台边缘服务器上的访问边缘服务的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="1ac9e-162">Each entry must resolve the FQDN of the Access Edge service (for example, sip.contoso.com) to the IP address of the Access Edge service on one of the Edge Servers in the pool.</span></span>

  - <span data-ttu-id="1ac9e-163">对于 Web 会议边缘服务，池中的每台服务器都需要一个条目。</span><span class="sxs-lookup"><span data-stu-id="1ac9e-163">For the Web Conferencing Edge service, you need one entry for each server in the pool.</span></span> <span data-ttu-id="1ac9e-164">每个条目都必须解析 Web 会议边缘服务的 FQDN (例如，webconf.contoso.com) 到池中某一台边缘服务器上的 Web 会议边缘服务的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="1ac9e-164">Each entry must resolve the FQDN of the Web Conferencing Edge service (for example, webconf.contoso.com) to the IP address of the Web Conferencing Edge service on one of the Edge Servers in the pool.</span></span>

  - <span data-ttu-id="1ac9e-165">对于 "音频/视频边缘" 服务，池中的每台服务器都需要一个条目。</span><span class="sxs-lookup"><span data-stu-id="1ac9e-165">For the Audio/Video Edge service, you need one entry for each server in the pool.</span></span> <span data-ttu-id="1ac9e-166">每个条目都必须解析音频/视频边缘服务 (的 FQDN，例如，av.contoso.com) 到池中某个边缘服务器上的 A/V 边缘服务的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="1ac9e-166">Each entry must resolve the FQDN of the Audio/Video Edge service (for example, av.contoso.com) to the IP address of the A/V Edge service on one of the Edge Servers in the pool.</span></span>

<span data-ttu-id="1ac9e-167">要在边缘服务器池的内部接口上部署 DNS 负载平衡，必须添加一条将此边缘服务器池的内部 FQDN 解析为该池中每台服务器的 IP 地址的 DNS A 记录。</span><span class="sxs-lookup"><span data-stu-id="1ac9e-167">To deploy DNS load balancing on the internal interface of your Edge Server pool, you must add one DNS A record, which resolves the internal FQDN of the Edge Server pool to the IP address of each server in the pool.</span></span>

</div>

</div>

<div>

## <a name="using-dns-load-balancing-on-mediation-server-pools"></a><span data-ttu-id="1ac9e-168">在中介服务器池中使用 DNS 负载平衡</span><span class="sxs-lookup"><span data-stu-id="1ac9e-168">Using DNS Load Balancing on Mediation Server Pools</span></span>

<span data-ttu-id="1ac9e-p116">可以在独立的中介服务器池上使用 DNS 负载平衡。所有 SIP 和媒体流量都通过 DNS 负载平衡进行平衡。</span><span class="sxs-lookup"><span data-stu-id="1ac9e-p116">You can use DNS load balancing on stand-alone Mediation Server pools. All SIP and media traffic is balanced by DNS load balancing.</span></span>

<span data-ttu-id="1ac9e-171">要在中介服务器池中部署 DNS 负载平衡，必须设置 DNS，以便将池 FQDN（例如 mediationpool1.contoso.com）解析为该池中所有服务器的 IP 地址（例如，192.168.1.1、192.168.1.2 等）。</span><span class="sxs-lookup"><span data-stu-id="1ac9e-171">To deploy DNS load balancing on a Mediation Server pool, you must provision DNS to resolve the pool FQDN (for example, mediationpool1.contoso.com) to the IP addresses of all the servers in the pool (for example, 192.168.1.1, 192.168.1.2, and so on).</span></span>

</div>

<div>

## <a name="blocking-traffic-to-a-server-with-dns-load-balancing"></a><span data-ttu-id="1ac9e-172">使用 DNS 负载平衡阻止到服务器的通信</span><span class="sxs-lookup"><span data-stu-id="1ac9e-172">Blocking Traffic to a Server With DNS Load Balancing</span></span>

<span data-ttu-id="1ac9e-173">如果使用 DNS 负载平衡，并且需要阻止到特定计算机的流量，则只需从池 FQDN 中删除 IP 地址条目是不够的。</span><span class="sxs-lookup"><span data-stu-id="1ac9e-173">If you use DNS load balancing and you need to block traffic to a specific computer, it is not sufficient to just remove the IP address entries from the Pool FQDN.</span></span> <span data-ttu-id="1ac9e-174">您还必须删除计算机的 DNS 条目。</span><span class="sxs-lookup"><span data-stu-id="1ac9e-174">You must remove the DNS entry for the computer as well.</span></span>

<span data-ttu-id="1ac9e-175">请注意，对于服务器到服务器的流量，Lync Server 2013 使用拓扑感知负载平衡。</span><span class="sxs-lookup"><span data-stu-id="1ac9e-175">Note that for server-to-server traffic, Lync Server 2013 uses topology-aware load balancing.</span></span> <span data-ttu-id="1ac9e-176">服务器在中央管理存储中读取已发布的拓扑，以获取拓扑中的服务器的 Fqdn，并自动在服务器之间分布流量。</span><span class="sxs-lookup"><span data-stu-id="1ac9e-176">Servers read the published topology in the Central Management store to obtain the FQDNs of servers in the topology, and automatically distribute the traffic among the servers.</span></span> <span data-ttu-id="1ac9e-177">若要阻止服务器接收服务器到服务器的流量，则必须从拓扑中删除该服务器。</span><span class="sxs-lookup"><span data-stu-id="1ac9e-177">To block a server from receiving server-to-server traffic, you must remove the server from the topology.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

