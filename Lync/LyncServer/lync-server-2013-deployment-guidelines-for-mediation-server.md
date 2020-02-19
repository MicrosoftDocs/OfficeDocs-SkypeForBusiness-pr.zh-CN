---
title: Lync Server 2013：中介服务器的部署指南
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment guidelines for Mediation Server
ms:assetid: 7cc22b87-18d9-45e6-8402-015abd20f2e5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398622(v=OCS.15)
ms:contentKeyID: 48184606
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f55ec3444348b2717721dcad890a4712cd8b9a3b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138193"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-guidelines-for-mediation-server-in-lync-server-2013"></a><span data-ttu-id="db379-102">Lync Server 2013 中的中介服务器的部署指南</span><span class="sxs-lookup"><span data-stu-id="db379-102">Deployment guidelines for Mediation Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="db379-103">_**上次修改的主题：** 2012-10-12_</span><span class="sxs-lookup"><span data-stu-id="db379-103">_**Topic Last Modified:** 2012-10-12_</span></span>

<span data-ttu-id="db379-104">本主题介绍了中介服务器部署的规划准则。</span><span class="sxs-lookup"><span data-stu-id="db379-104">This topic describes planning guidelines for Mediation Server deployment.</span></span> <span data-ttu-id="db379-105">查看这些准则后，我们建议您使用规划工具来创建和查看可能的备用拓扑，这可以作为您决定要部署的最终定制拓扑的模型，如下所示。</span><span class="sxs-lookup"><span data-stu-id="db379-105">After reviewing these guidelines, we recommend that you use the Planning Tool to create and view possible alternative topologies, which can serve as models for what the final tailored topology that you decide to deploy would look like.</span></span>

<div>

## <a name="collocated-or-stand-alone-mediation-server"></a><span data-ttu-id="db379-106">并置还是独立中介服务器？</span><span class="sxs-lookup"><span data-stu-id="db379-106">Collocated or Stand-alone Mediation Server?</span></span>

<span data-ttu-id="db379-107">默认情况下，在中央站点上的 Standard Edition Server 或前端池中的前端服务器上并置中介服务器。</span><span class="sxs-lookup"><span data-stu-id="db379-107">Mediation Server is by default collocated on the Standard Edition server or Front End Server in a Front End pool at central sites.</span></span> <span data-ttu-id="db379-108">可以处理的公共交换电话网络（PSTN）呼叫数和池中所需的计算机数取决于以下几项：</span><span class="sxs-lookup"><span data-stu-id="db379-108">The number of public switched telephone network (PSTN) calls that can be handled and the number of machines required in the pool will depend on the following:</span></span>

  - <span data-ttu-id="db379-109">中介服务器池控制的网关对等方的数量</span><span class="sxs-lookup"><span data-stu-id="db379-109">The number of gateway peers that the Mediation Server pool controls</span></span>

  - <span data-ttu-id="db379-110">通过这些网关的高容量通信周期</span><span class="sxs-lookup"><span data-stu-id="db379-110">The high-volume traffic periods through those gateways</span></span>

  - <span data-ttu-id="db379-111">其媒体绕过中介服务器的呼叫的呼叫百分比</span><span class="sxs-lookup"><span data-stu-id="db379-111">The percentage of calls that are calls whose media bypass the Mediation Server</span></span>

<span data-ttu-id="db379-112">在规划时，请务必考虑 PSTN 呼叫的媒体处理要求以及没有为媒体旁路配置的 A/V 会议，以及处理需要支持的繁忙小时数的信号交互所需的处理。</span><span class="sxs-lookup"><span data-stu-id="db379-112">When planning, be sure to take into account the media processing requirements for PSTN calls and A/V conferences that are not configured for media bypass, as well as the processing needed to handle signaling interactions for the number of busy-hour calls that need to be supported.</span></span> <span data-ttu-id="db379-113">如果没有足够的 CPU，则必须部署一台独立的中介服务器池;而 PSTN 网关、IP Pbx 和 SBCs 需要分成多个子集，这些子集由一个池中的并置中介服务器和一个或多个独立池中的独立中介服务器控制。</span><span class="sxs-lookup"><span data-stu-id="db379-113">If there is not enough CPU, then you must deploy a stand-alone pool of Mediation Servers; and PSTN gateways, IP-PBXs, and SBCs will need to be split into subsets that are controlled by the collocated Mediation Servers in one pool and the stand-alone Mediation Servers in one or more stand-alone pools.</span></span>

<span data-ttu-id="db379-114">如果部署的 PSTN 网关、IP Pbx 或会话边界控制器（SBCs）不支持与中介服务器池进行交互的正确功能（包括以下各项），则需要将它们与包含以下各项的独立池相关联：在单个中介服务器上：</span><span class="sxs-lookup"><span data-stu-id="db379-114">If you deployed PSTN gateways, IP-PBXs, or Session Border Controllers (SBCs) that do not support the correct capabilities to interact with a pool of Mediation Servers, including the following, then they will need to be associated with a stand-alone pool consisting of a single Mediation Server:</span></span>

  - <span data-ttu-id="db379-115">在池中的中介服务器之间执行网络层域名系统（DNS）负载平衡（或者以统一方式将流量统一路由到池中的所有中介服务器）</span><span class="sxs-lookup"><span data-stu-id="db379-115">Perform network layer Domain Name System (DNS) load balancing across Mediation Servers in a pool (or otherwise route traffic uniformly to all Mediation Servers in a pool)</span></span>

  - <span data-ttu-id="db379-116">接受来自池中任意中介服务器的流量</span><span class="sxs-lookup"><span data-stu-id="db379-116">Accept traffic from any Mediation Server in a pool</span></span>

<span data-ttu-id="db379-117">您可以使用 Microsoft Lync Server 2013、规划工具来评估并置使用前端池的中介服务器是否可以处理负载。</span><span class="sxs-lookup"><span data-stu-id="db379-117">You can use the Microsoft Lync Server 2013, Planning Tool to evaluate whether collocating the Mediation Server with your Front End pool can handle the load.</span></span> <span data-ttu-id="db379-118">如果您的环境不能满足这些要求，则必须部署独立的中介服务器池。</span><span class="sxs-lookup"><span data-stu-id="db379-118">If your environment cannot meet these requirements, then you must deploy a stand-alone Mediation Server pool.</span></span>

</div>

<div>

## <a name="central-site-and-branch-site-considerations"></a><span data-ttu-id="db379-119">中央站点和分支站点注意事项</span><span class="sxs-lookup"><span data-stu-id="db379-119">Central Site and Branch Site Considerations</span></span>

<span data-ttu-id="db379-p105">中央站点的中介服务器可用于为分支站点的 IP-PBX 或 PSTN 网关路由呼叫。但是，如果部署 SIP 中继，则必须在每个中继终止的站点上部署一台中介服务器。使用中央站点的中介服务器为分支站点的 IP-PBX 或 PSTN 网关路由呼叫时，不需要使用媒体绕过。但是，如果可以启用媒体绕过，则可以降低媒体路径延迟，从而改善媒体质量，因为媒体路径不再需要遵循信号路径。媒体绕过还将减少池中的处理负载。</span><span class="sxs-lookup"><span data-stu-id="db379-p105">Mediation Servers at the central site can be used to route calls for IP-PBXs or PSTN gateways at branch sites. If you deploy SIP trunks, however, you must deploy a Mediation Server at the site where each trunk terminates. Having a Mediation Server at the central site route calls for an IP-PBX or PSTN gateway at a branch site does not require the use of media bypass. However, if you can enable media bypass, doing so will reduce media path latency and, consequently, result in improved media quality because the media path is no longer required to follow the signaling path. Media bypass will also decrease the processing load on the pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="db379-125">媒体绕过将不会与每个 PSTN 网关、IP-PBX 和 SBC 进行交互操作。</span><span class="sxs-lookup"><span data-stu-id="db379-125">Media bypass will not interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="db379-126">Microsoft 已使用认证的合作伙伴测试了一组 PSTN 网关和 SBCs，并且已通过 Cisco IP Pbx 进行了一些测试。</span><span class="sxs-lookup"><span data-stu-id="db379-126">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="db379-127">仅在统一通信开放互操作性计划– Lync Server 上列出的产品和版本支持媒体<A href="https://go.microsoft.com/fwlink/p/?linkid=268730">https://go.microsoft.com/fwlink/p/?LinkId=268730</A>旁路。</span><span class="sxs-lookup"><span data-stu-id="db379-127">Media bypass is supported only with products and versions listed on Unified Communications Open Interoperability Program – Lync Server at <A href="https://go.microsoft.com/fwlink/p/?linkid=268730">https://go.microsoft.com/fwlink/p/?LinkId=268730</A>.</span></span>



</div>

<span data-ttu-id="db379-128">如果要求具有分支站点恢复能力，则必须在分支站点部署 Survivable Branch Appliance 或部署前端服务器、中介服务器和网关的组合。</span><span class="sxs-lookup"><span data-stu-id="db379-128">If branch site resiliency is required, a Survivable Branch Appliance or combination of a Front End Server, a Mediation Server, and a gateway must be deployed at the branch site.</span></span> <span data-ttu-id="db379-129">（具有分支站点恢复能力的假设是网站上的状态和会议不是可恢复的。有关分支站点规划语音的指南，请参阅[Lync Server 2013 中的规划分支站点语音恢复](lync-server-2013-planning-for-branch-site-voice-resiliency.md)。</span><span class="sxs-lookup"><span data-stu-id="db379-129">(The assumption with branch site resiliency is that presence and conferencing are not resilient at the site.) For guidance on branch site planning for voice, see [Planning for branch-site voice resiliency in Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md).</span></span>

<span data-ttu-id="db379-130">对于与 ip-pbx 的交互，如果 ip-pbx 不能正确支持与多个早期对话框和 RFC 3960 交互的早期媒体交互，则可以将来自 ip-pbx 的传入呼叫的问候语的前几个字剪辑到 Lync 终结点。</span><span class="sxs-lookup"><span data-stu-id="db379-130">For interactions with an IP-PBX, if the IP-PBX does not correctly support early media interactions with multiple early dialogs and RFC 3960 interactions, there can be clipping of the first few words of the greeting for incoming calls from the IP-PBX to Lync endpoints.</span></span> <span data-ttu-id="db379-131">如果中央站点上的中介服务器为 IP-PBX 路由呼叫，其中路由终止于分支站点，这种行为可能更为严重，因为完成信号需要更长时间。</span><span class="sxs-lookup"><span data-stu-id="db379-131">This behavior can be more severe if a Mediation Server at a central site is routing calls for an IP-PBX where the route terminates at a branch site, because more time is needed for signaling to complete.</span></span> <span data-ttu-id="db379-132">如果您遇到此行为，在分支站点部署中介服务器是减少前几个词的修剪的唯一方法。</span><span class="sxs-lookup"><span data-stu-id="db379-132">If you experience this behavior, deploying a Mediation Server at the branch site is the only way to reduce clipping of the first few words.</span></span>

<span data-ttu-id="db379-133">最后，如果中央站点具有 TDM PBX，或者 IP-PBX 仍然需要 PSTN 网关，则必须在连接中介服务器和 PBX 的呼叫路由上部署网关。</span><span class="sxs-lookup"><span data-stu-id="db379-133">Finally, if your central site has a TDM PBX, or if your IP-PBX does not eliminate the need for a PSTN gateway, then you must deploy a gateway on the call route connecting Mediation Server and the PBX.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="db379-134">若要提高独立中介服务器的媒体性能，应在这些服务器上的网络适配器上启用接收端扩展（RSS）。</span><span class="sxs-lookup"><span data-stu-id="db379-134">To improve the media performance of standalone Mediation Server, you should enable receive-side scaling (RSS) on the network adapters on these servers.</span></span> <span data-ttu-id="db379-135">通过启用 RSS，服务器上的多个处理器能够以并行方式处理传入数据包。</span><span class="sxs-lookup"><span data-stu-id="db379-135">RSS enables incoming packets to be handled in parallel by multiple processors on the server.</span></span> <span data-ttu-id="db379-136">有关详细信息，请参阅中的 "在<A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?LinkId=268731</A>Windows Server 中接收端扩展功能增强"。</span><span class="sxs-lookup"><span data-stu-id="db379-136">For details, see "Receive-Side Scaling Enhancements in Windows Server" at <A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?LinkId=268731</A>.</span></span> <span data-ttu-id="db379-137">有关如何启用 RSS 的详细信息，请参阅网络适配器文档。</span><span class="sxs-lookup"><span data-stu-id="db379-137">For details about how to enable RSS, see your network adapter documentation.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

