---
title: Skype for Business Server 中的中介服务器部署指南
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
ms.collection: IT_Skype16
ms.assetid: 7cc22b87-18d9-45e6-8402-015abd20f2e5
description: 本主题介绍了中介服务器部署的规划指南。
ms.openlocfilehash: 806886b7c7c5e8ae367a6e104f7fd9127f25c099
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816051"
---
# <a name="deployment-guidelines-for-mediation-server-in-skype-for-business-server"></a><span data-ttu-id="900bd-103">Skype for Business Server 中的中介服务器部署指南</span><span class="sxs-lookup"><span data-stu-id="900bd-103">Deployment guidelines for Mediation Server in Skype for Business Server</span></span>
 
<span data-ttu-id="900bd-104">本主题介绍了中介服务器部署的规划指南。</span><span class="sxs-lookup"><span data-stu-id="900bd-104">This topic describes planning guidelines for Mediation Server deployment.</span></span>
  
## <a name="collocated-or-stand-alone-mediation-server"></a><span data-ttu-id="900bd-105">Collocated 还是独立中介服务器？</span><span class="sxs-lookup"><span data-stu-id="900bd-105">Collocated or Stand-alone Mediation Server?</span></span>

<span data-ttu-id="900bd-106">默认情况下，中介服务器在中央站点的前端池中的标准版服务器或前端服务器上 collocated。</span><span class="sxs-lookup"><span data-stu-id="900bd-106">Mediation Server is, by default, collocated on the Standard Edition server or Front End Server in a Front End pool at central sites.</span></span> <span data-ttu-id="900bd-107">可以处理的公用电话交换网 (PSTN) 呼叫数和池中所需的计算机数取决于以下因素：</span><span class="sxs-lookup"><span data-stu-id="900bd-107">The number of public switched telephone network (PSTN) calls that can be handled and the number of machines required in the pool will depend on:</span></span>
  
- <span data-ttu-id="900bd-108">中介服务器池控制的网关对等的数量。</span><span class="sxs-lookup"><span data-stu-id="900bd-108">The number of gateway peers that the Mediation Server pool controls.</span></span>
    
- <span data-ttu-id="900bd-109">通过这些网关的高流量时段。</span><span class="sxs-lookup"><span data-stu-id="900bd-109">The high-volume traffic periods through those gateways.</span></span>
    
- <span data-ttu-id="900bd-110">将其媒体绕过中介服务器的呼叫的通话百分比。</span><span class="sxs-lookup"><span data-stu-id="900bd-110">The percentage of calls that are calls whose media bypass the Mediation Server.</span></span>
    
<span data-ttu-id="900bd-111">规划时，请确保考虑不支持媒体旁路的 PSTN 呼叫和 A/V 会议的媒体处理要求，同时考虑处理必须支持的忙时呼叫数量的信号交互所需的处理要求。</span><span class="sxs-lookup"><span data-stu-id="900bd-111">When you're planning, be sure to take into account the media processing requirements for PSTN calls and A/V conferences that don't support media bypass, as well as the processing needed to handle signaling interactions for the number of busy-hour calls that need to be supported.</span></span> <span data-ttu-id="900bd-112">如果您没有足够的 CPU，则需要部署一个独立的中介服务器池。</span><span class="sxs-lookup"><span data-stu-id="900bd-112">If you don't have enough CPU, you'll need to deploy a stand-alone pool of Mediation Servers.</span></span> <span data-ttu-id="900bd-113">此外，PSTN 网关、IP-Pbx 和 SBCs 将需要拆分为由一个池中的 collocated 中介服务器和一个或多个独立的池中的独立中介服务器控制的子集。</span><span class="sxs-lookup"><span data-stu-id="900bd-113">Additionally, PSTN gateways, IP-PBXs, and SBCs will need to be split into subsets that are controlled by the collocated Mediation Servers in one pool and the stand-alone Mediation Servers in one or more stand-alone pools.</span></span>
  
<span data-ttu-id="900bd-114">如果你部署的 PSTN 网关、IP-Pbx 或会话边界控制器（SBCs）缺少与中介服务器池的交互，则它们需要与包含单个中介服务器的独立池相关联。</span><span class="sxs-lookup"><span data-stu-id="900bd-114">If you deployed PSTN gateways, IP-PBXs, or Session Border Controllers (SBCs) that lack the ability to interact with a pool of Mediation Servers, they'll need to be associated with a stand-alone pool consisting of a single Mediation Server.</span></span> <span data-ttu-id="900bd-115">您的 PSTN 网关、IP-PBX 或 SBC 需要执行的某些操作包括：</span><span class="sxs-lookup"><span data-stu-id="900bd-115">Some of the things your PSTN gateways, IP-PBXs or SBCs would need to do include:</span></span>
  
- <span data-ttu-id="900bd-116">在池中的中介服务器上执行网络层域名系统（DNS）负载平衡（或以统一方式将流量统一到池中的所有中介服务器）。</span><span class="sxs-lookup"><span data-stu-id="900bd-116">Perform network layer Domain Name System (DNS) load balancing across Mediation Servers in a pool (or otherwise route traffic uniformly to all Mediation Servers in a pool).</span></span>
    
- <span data-ttu-id="900bd-117">接受来自池中的任何中介服务器的流量。</span><span class="sxs-lookup"><span data-stu-id="900bd-117">Accept traffic from any Mediation Server in a pool.</span></span>
    
<span data-ttu-id="900bd-118">你可以使用 Skype for Business 计划工具评估 collocating 的中介服务器是否可以处理负载。</span><span class="sxs-lookup"><span data-stu-id="900bd-118">You can use the Skype for Business Planning Tool to evaluate whether collocating the Mediation Server with your Front End pool can handle the load.</span></span> <span data-ttu-id="900bd-119">如果你的环境无法满足这些要求，则你需要部署独立的中介服务器池。</span><span class="sxs-lookup"><span data-stu-id="900bd-119">If your environment can't meet these requirements, then you'll need to deploy a stand-alone Mediation Server pool.</span></span>
  
## <a name="central-site-and-branch-site-considerations"></a><span data-ttu-id="900bd-120">中央站点和分支站点注意事项</span><span class="sxs-lookup"><span data-stu-id="900bd-120">Central Site and Branch Site Considerations</span></span>

 <span data-ttu-id="900bd-121">中心站点上的中介服务器可用于路由分支站点上的 IP-Pbx 或 PSTN 网关的呼叫。</span><span class="sxs-lookup"><span data-stu-id="900bd-121">Mediation Servers at the central site can be used to route calls for IP-PBXs or PSTN gateways at branch sites.</span></span> <span data-ttu-id="900bd-122">但是，如果你部署 SIP 中继，则必须在每个主干终止的站点上部署中介服务器。</span><span class="sxs-lookup"><span data-stu-id="900bd-122">If you deploy SIP trunks, however, you have to deploy a Mediation Server at the site where each trunk terminates.</span></span> <span data-ttu-id="900bd-123">对于分支站点上的 IP PBX 或 PSTN 网关，在中心站点路由呼叫中拥有中介服务器不需要使用媒体绕过，但建议使用媒体绕过。</span><span class="sxs-lookup"><span data-stu-id="900bd-123">Having a Mediation Server at the central site route calls for an IP-PBX or PSTN gateway at a branch site doesn't require the use of media bypass, but a media bypass is recommended.</span></span> <span data-ttu-id="900bd-124">这是因为，如果可以启用媒体绕过，则可以降低媒体路径延迟，从而改善媒体质量，因为媒体路径不再需要遵循信号路径。</span><span class="sxs-lookup"><span data-stu-id="900bd-124">That's because, if you can enable media bypass, it'll reduce media path latency and, consequently, result in improved media quality because the media path isn't required to follow the signaling path.</span></span> <span data-ttu-id="900bd-125">媒体绕过还将减少池中的处理负载。</span><span class="sxs-lookup"><span data-stu-id="900bd-125">Media bypass will also decrease the processing load on the pool.</span></span>
  
> [!NOTE]
> <span data-ttu-id="900bd-126">媒体旁路将不会与每个 PSTN 网关、IP-PBX 和 SBC 进行交互操作。</span><span class="sxs-lookup"><span data-stu-id="900bd-126">Media bypass won't interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="900bd-127">Microsoft 与认证合作伙伴一起对一组 PSTN 网关和 SBC 进行了测试，另外也对 Cisco IP-PBX 进行了一些测试。</span><span class="sxs-lookup"><span data-stu-id="900bd-127">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="900bd-128">只有在统一通信中列出的产品和版本才支持媒体旁路打开互操作性计划-Lync Server 在[探索已测试的设备、基础结构和支持和扩展 Skype For business 体验的工具](http://partnersolutions.skypeforbusiness.com/solutionscatalog)。</span><span class="sxs-lookup"><span data-stu-id="900bd-128">Media bypass is supported only with products and versions listed on Unified Communications Open Interoperability Program - Lync Server at [Explore tested devices, infrastructure, and tools that support and extend your Skype for Business experience](http://partnersolutions.skypeforbusiness.com/solutionscatalog).</span></span> 
  
<span data-ttu-id="900bd-129">如果需要分支站点弹性，必须在分支站点上部署 Survivable 分支装置或前端服务器、中介服务器和网关的组合。</span><span class="sxs-lookup"><span data-stu-id="900bd-129">If branch site resiliency is required, a Survivable Branch Appliance or combination of a Front End Server, a Mediation Server, and a gateway must be deployed at the branch site.</span></span> <span data-ttu-id="900bd-130">（具有分支站点弹性的假设是状态和会议在网站上不能复原。）有关针对语音进行分支站点计划的指南，请参阅[Skype For Business 服务器中的 "规划企业语音弹性](../enterprise-voice-solution/enterprise-voice-resiliency.md)"。</span><span class="sxs-lookup"><span data-stu-id="900bd-130">(The assumption with branch site resiliency is that presence and conferencing are not resilient at the site.) For guidance on branch site planning for voice, see [Plan for Enterprise Voice resiliency in Skype for Business Server](../enterprise-voice-solution/enterprise-voice-resiliency.md).</span></span>
  
<span data-ttu-id="900bd-131">对于与 IP PBX 的交互，如果 IP PBX 不能正确支持具有多个早期对话框和 RFC 3960 交互的早期媒体交互，则可以将来自 IP PBX 的来电的前几个字与 Lync 终结点进行剪辑。</span><span class="sxs-lookup"><span data-stu-id="900bd-131">For interactions with an IP-PBX, if the IP-PBX does not correctly support early media interactions with multiple early dialogs and RFC 3960 interactions, there can be clipping of the first few words of the greeting for incoming calls from the IP-PBX to Lync endpoints.</span></span> <span data-ttu-id="900bd-132">如果中央站点上的中介服务器是路由在分支站点上终止的 IP-PBX 的路由呼叫，则这种行为可能更严重，因为发送信号需要更多的时间才能完成。</span><span class="sxs-lookup"><span data-stu-id="900bd-132">This behavior can be more severe if a Mediation Server at a central site is routing calls for an IP-PBX where the route terminates at a branch site, because more time is needed for signaling to complete.</span></span> <span data-ttu-id="900bd-133">如果你遇到此行为，则在分支站点上部署中介服务器是减少前几个字词的剪辑的唯一方法。</span><span class="sxs-lookup"><span data-stu-id="900bd-133">If you experience this behavior, deploying a Mediation Server at the branch site is the only way to reduce clipping of the first few words.</span></span>
  
<span data-ttu-id="900bd-134">最后，如果你的中心网站具有 TDM PBX，或者如果你的 IP PBX 不能消除 PSTN 网关的需要，则必须在连接中介服务器和 PBX 的呼叫路由上部署网关。</span><span class="sxs-lookup"><span data-stu-id="900bd-134">Finally, if your central site has a TDM PBX, or if your IP-PBX does not eliminate the need for a PSTN gateway, then you must deploy a gateway on the call route connecting Mediation Server and the PBX.</span></span>
  
> [!NOTE]
> <span data-ttu-id="900bd-135">要提高独立的中介服务器的媒体性能，应在这些服务器的网络适配器上启用接收方缩放 (RSS)。</span><span class="sxs-lookup"><span data-stu-id="900bd-135">To improve the media performance of standalone Mediation Server, you should enable receive-side scaling (RSS) on the network adapters on these servers.</span></span> <span data-ttu-id="900bd-136">通过启用 RSS，服务器上的多个处理器能够以并行方式处理传入数据包。</span><span class="sxs-lookup"><span data-stu-id="900bd-136">RSS enables incoming packets to be handled in parallel by multiple processors on the server.</span></span> <span data-ttu-id="900bd-137">有关详细信息，请参阅[Windows Server 中的接收端缩放增强功能](https://go.microsoft.com/fwlink/p/?LinkId=268731)。</span><span class="sxs-lookup"><span data-stu-id="900bd-137">For details, see "[Receive-Side Scaling Enhancements in Windows Server](https://go.microsoft.com/fwlink/p/?LinkId=268731)".</span></span> <span data-ttu-id="900bd-138">有关如何启用 RSS 的详细信息，请参阅网络适配器文档。</span><span class="sxs-lookup"><span data-stu-id="900bd-138">For details about how to enable RSS, see your network adapter documentation.</span></span> 
  

