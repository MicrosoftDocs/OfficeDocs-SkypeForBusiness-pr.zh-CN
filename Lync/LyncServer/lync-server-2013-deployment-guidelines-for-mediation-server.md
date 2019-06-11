---
title: 'Lync Server 2013: 中介服务器的部署指南'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment guidelines for Mediation Server
ms:assetid: 7cc22b87-18d9-45e6-8402-015abd20f2e5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398622(v=OCS.15)
ms:contentKeyID: 48184606
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 400f8cceeb86d407297b3f564c01266a477ca0ef
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830495"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-guidelines-for-mediation-server-in-lync-server-2013"></a><span data-ttu-id="0b858-102">Lync Server 2013 中的中介服务器部署指南</span><span class="sxs-lookup"><span data-stu-id="0b858-102">Deployment guidelines for Mediation Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0b858-103">_**主题上次修改时间:** 2012-10-12_</span><span class="sxs-lookup"><span data-stu-id="0b858-103">_**Topic Last Modified:** 2012-10-12_</span></span>

<span data-ttu-id="0b858-104">本主题介绍了中介服务器部署的规划指南。</span><span class="sxs-lookup"><span data-stu-id="0b858-104">This topic describes planning guidelines for Mediation Server deployment.</span></span> <span data-ttu-id="0b858-105">查看这些指南后, 我们建议你使用计划工具来创建和查看可能的替代拓扑, 这些拓扑可以用作你确定要部署的最终定制拓扑的模型。</span><span class="sxs-lookup"><span data-stu-id="0b858-105">After reviewing these guidelines, we recommend that you use the Planning Tool to create and view possible alternative topologies, which can serve as models for what the final tailored topology that you decide to deploy would look like.</span></span>

<div>

## <a name="collocated-or-stand-alone-mediation-server"></a><span data-ttu-id="0b858-106">Collocated 还是独立中介服务器？</span><span class="sxs-lookup"><span data-stu-id="0b858-106">Collocated or Stand-alone Mediation Server?</span></span>

<span data-ttu-id="0b858-107">默认情况下, 在中央站点的前端池中的标准版服务器或前端服务器上 collocated 中介服务器。</span><span class="sxs-lookup"><span data-stu-id="0b858-107">Mediation Server is by default collocated on the Standard Edition server or Front End Server in a Front End pool at central sites.</span></span> <span data-ttu-id="0b858-108">可以处理的公用电话交换网 (PSTN) 呼叫数和池中所需的计算机数取决于以下因素：</span><span class="sxs-lookup"><span data-stu-id="0b858-108">The number of public switched telephone network (PSTN) calls that can be handled and the number of machines required in the pool will depend on the following:</span></span>

  - <span data-ttu-id="0b858-109">中介服务器池控制的网关对等的数量</span><span class="sxs-lookup"><span data-stu-id="0b858-109">The number of gateway peers that the Mediation Server pool controls</span></span>

  - <span data-ttu-id="0b858-110">通过这些网关的高流量时段</span><span class="sxs-lookup"><span data-stu-id="0b858-110">The high-volume traffic periods through those gateways</span></span>

  - <span data-ttu-id="0b858-111">媒体绕过中介服务器的呼叫的通话百分比</span><span class="sxs-lookup"><span data-stu-id="0b858-111">The percentage of calls that are calls whose media bypass the Mediation Server</span></span>

<span data-ttu-id="0b858-112">规划时，请确保考虑未进行媒体旁路配置的 PSTN 呼叫和 A/V 会议的媒体处理要求，同时考虑处理必须支持的忙时呼叫数量的信号交互所需的处理要求。</span><span class="sxs-lookup"><span data-stu-id="0b858-112">When planning, be sure to take into account the media processing requirements for PSTN calls and A/V conferences that are not configured for media bypass, as well as the processing needed to handle signaling interactions for the number of busy-hour calls that need to be supported.</span></span> <span data-ttu-id="0b858-113">如果没有足够的 CPU, 则必须部署一个单独的中介池服务器池;PSTN 网关、IP-Pbx 和 SBCs 需要拆分为多个子集, 这些子集由一个池中的 collocated 中介服务器和一个或多个独立的池内的独立中介服务器控制。</span><span class="sxs-lookup"><span data-stu-id="0b858-113">If there is not enough CPU, then you must deploy a stand-alone pool of Mediation Servers; and PSTN gateways, IP-PBXs, and SBCs will need to be split into subsets that are controlled by the collocated Mediation Servers in one pool and the stand-alone Mediation Servers in one or more stand-alone pools.</span></span>

<span data-ttu-id="0b858-114">如果你部署的 PSTN 网关、IP-Pbx 或会话边界控制器 (SBCs) 不支持与中介服务器池进行交互的正确功能 (包括以下情况), 则需要将它们与一个独立的池相关联, 包括在单个中介服务器中:</span><span class="sxs-lookup"><span data-stu-id="0b858-114">If you deployed PSTN gateways, IP-PBXs, or Session Border Controllers (SBCs) that do not support the correct capabilities to interact with a pool of Mediation Servers, including the following, then they will need to be associated with a stand-alone pool consisting of a single Mediation Server:</span></span>

  - <span data-ttu-id="0b858-115">在池中的中介服务器上执行网络层域名系统 (DNS) 负载平衡 (或以统一方式将流量统一到池中的所有中介服务器)</span><span class="sxs-lookup"><span data-stu-id="0b858-115">Perform network layer Domain Name System (DNS) load balancing across Mediation Servers in a pool (or otherwise route traffic uniformly to all Mediation Servers in a pool)</span></span>

  - <span data-ttu-id="0b858-116">接受来自池中的任何中介服务器的流量</span><span class="sxs-lookup"><span data-stu-id="0b858-116">Accept traffic from any Mediation Server in a pool</span></span>

<span data-ttu-id="0b858-117">你可以使用 Microsoft Lync Server 2013、计划工具评估 collocating 前端池的中介服务器是否可以处理负载。</span><span class="sxs-lookup"><span data-stu-id="0b858-117">You can use the Microsoft Lync Server 2013, Planning Tool to evaluate whether collocating the Mediation Server with your Front End pool can handle the load.</span></span> <span data-ttu-id="0b858-118">如果你的环境无法满足这些要求, 则必须部署独立的中介服务器池。</span><span class="sxs-lookup"><span data-stu-id="0b858-118">If your environment cannot meet these requirements, then you must deploy a stand-alone Mediation Server pool.</span></span>

</div>

<div>

## <a name="central-site-and-branch-site-considerations"></a><span data-ttu-id="0b858-119">中央站点和分支站点注意事项</span><span class="sxs-lookup"><span data-stu-id="0b858-119">Central Site and Branch Site Considerations</span></span>

<span data-ttu-id="0b858-120">中心站点上的中介服务器可用于路由分支站点上的 IP-Pbx 或 PSTN 网关的呼叫。</span><span class="sxs-lookup"><span data-stu-id="0b858-120">Mediation Servers at the central site can be used to route calls for IP-PBXs or PSTN gateways at branch sites.</span></span> <span data-ttu-id="0b858-121">但是, 如果你部署 SIP 中继, 则必须在每个主干终止的站点上部署中介服务器。</span><span class="sxs-lookup"><span data-stu-id="0b858-121">If you deploy SIP trunks, however, you must deploy a Mediation Server at the site where each trunk terminates.</span></span> <span data-ttu-id="0b858-122">对于分支站点上的 IP PBX 或 PSTN 网关, 在中心站点路由呼叫中拥有中介服务器不需要使用媒体旁路。</span><span class="sxs-lookup"><span data-stu-id="0b858-122">Having a Mediation Server at the central site route calls for an IP-PBX or PSTN gateway at a branch site does not require the use of media bypass.</span></span> <span data-ttu-id="0b858-123">但是, 如果你可以启用媒体绕过, 这样做将减少媒体路径延迟, 因此, 由于不再需要媒体路径来跟踪信号路径, 因此提高了媒体质量。</span><span class="sxs-lookup"><span data-stu-id="0b858-123">However, if you can enable media bypass, doing so will reduce media path latency and, consequently, result in improved media quality because the media path is no longer required to follow the signaling path.</span></span> <span data-ttu-id="0b858-124">媒体绕过还将减少池中的处理负载。</span><span class="sxs-lookup"><span data-stu-id="0b858-124">Media bypass will also decrease the processing load on the pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0b858-125">媒体旁路将不会与每个 PSTN 网关、IP-PBX 和 SBC 进行交互操作。</span><span class="sxs-lookup"><span data-stu-id="0b858-125">Media bypass will not interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="0b858-126">Microsoft 与认证合作伙伴一起对一组 PSTN 网关和 SBC 进行了测试，另外也对 Cisco IP-PBX 进行了一些测试。</span><span class="sxs-lookup"><span data-stu-id="0b858-126">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="0b858-127">只有在统一通信中列出的产品和版本才支持媒体绕开互操作性计划- <A href="http://go.microsoft.com/fwlink/p/?linkid=268730">http://go.microsoft.com/fwlink/p/?LinkId=268730</A>Lync Server at。</span><span class="sxs-lookup"><span data-stu-id="0b858-127">Media bypass is supported only with products and versions listed on Unified Communications Open Interoperability Program – Lync Server at <A href="http://go.microsoft.com/fwlink/p/?linkid=268730">http://go.microsoft.com/fwlink/p/?LinkId=268730</A>.</span></span>



</div>

<span data-ttu-id="0b858-128">如果需要分支站点弹性, 必须在分支站点上部署 Survivable 分支装置或前端服务器、中介服务器和网关的组合。</span><span class="sxs-lookup"><span data-stu-id="0b858-128">If branch site resiliency is required, a Survivable Branch Appliance or combination of a Front End Server, a Mediation Server, and a gateway must be deployed at the branch site.</span></span> <span data-ttu-id="0b858-129">(具有分支站点弹性的假设是状态和会议在网站上不能复原。)有关针对语音进行分支站点规划的指南, 请参阅[Lync Server 2013 中的规划分支站点语音复原](lync-server-2013-planning-for-branch-site-voice-resiliency.md)。</span><span class="sxs-lookup"><span data-stu-id="0b858-129">(The assumption with branch site resiliency is that presence and conferencing are not resilient at the site.) For guidance on branch site planning for voice, see [Planning for branch-site voice resiliency in Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md).</span></span>

<span data-ttu-id="0b858-130">对于与 IP PBX 的交互, 如果 IP PBX 不能正确支持具有多个早期对话框和 RFC 3960 交互的早期媒体交互, 则可以将来自 IP PBX 的来电的前几个字与 Lync 终结点进行剪辑。</span><span class="sxs-lookup"><span data-stu-id="0b858-130">For interactions with an IP-PBX, if the IP-PBX does not correctly support early media interactions with multiple early dialogs and RFC 3960 interactions, there can be clipping of the first few words of the greeting for incoming calls from the IP-PBX to Lync endpoints.</span></span> <span data-ttu-id="0b858-131">如果中央站点上的中介服务器是路由在分支站点上终止的 IP-PBX 的路由呼叫, 则这种行为可能更严重, 因为发送信号需要更多的时间才能完成。</span><span class="sxs-lookup"><span data-stu-id="0b858-131">This behavior can be more severe if a Mediation Server at a central site is routing calls for an IP-PBX where the route terminates at a branch site, because more time is needed for signaling to complete.</span></span> <span data-ttu-id="0b858-132">如果你遇到此行为, 则在分支站点上部署中介服务器是减少前几个字词的剪辑的唯一方法。</span><span class="sxs-lookup"><span data-stu-id="0b858-132">If you experience this behavior, deploying a Mediation Server at the branch site is the only way to reduce clipping of the first few words.</span></span>

<span data-ttu-id="0b858-133">最后, 如果你的中心网站具有 TDM PBX, 或者如果你的 IP PBX 不能消除 PSTN 网关的需要, 则必须在连接中介服务器和 PBX 的呼叫路由上部署网关。</span><span class="sxs-lookup"><span data-stu-id="0b858-133">Finally, if your central site has a TDM PBX, or if your IP-PBX does not eliminate the need for a PSTN gateway, then you must deploy a gateway on the call route connecting Mediation Server and the PBX.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0b858-134">要提高独立的中介服务器的媒体性能，应在这些服务器的网络适配器上启用接收方缩放 (RSS)。</span><span class="sxs-lookup"><span data-stu-id="0b858-134">To improve the media performance of standalone Mediation Server, you should enable receive-side scaling (RSS) on the network adapters on these servers.</span></span> <span data-ttu-id="0b858-135">通过启用 RSS，服务器上的多个处理器能够以并行方式处理传入数据包。</span><span class="sxs-lookup"><span data-stu-id="0b858-135">RSS enables incoming packets to be handled in parallel by multiple processors on the server.</span></span> <span data-ttu-id="0b858-136">有关详细信息, 请参阅的 "Windows Server 中的接收端缩放<A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?LinkId=268731</A>增强功能增强"。</span><span class="sxs-lookup"><span data-stu-id="0b858-136">For details, see "Receive-Side Scaling Enhancements in Windows Server" at <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?LinkId=268731</A>.</span></span> <span data-ttu-id="0b858-137">有关如何启用 RSS 的详细信息，请参阅网络适配器文档。</span><span class="sxs-lookup"><span data-stu-id="0b858-137">For details about how to enable RSS, see your network adapter documentation.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

