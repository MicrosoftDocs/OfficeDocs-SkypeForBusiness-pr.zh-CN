---
title: Skype for Business Server 中的中介服务器的部署指南
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
ms.collection: IT_Skype16
ms.assetid: 7cc22b87-18d9-45e6-8402-015abd20f2e5
description: 本主题介绍中介服务器部署的规划准则。
ms.openlocfilehash: ffb60abaf3027541f13fe73294eafda51e5d1d0f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118531"
---
# <a name="deployment-guidelines-for-mediation-server-in-skype-for-business-server"></a><span data-ttu-id="a44dd-103">Skype for Business Server 中的中介服务器的部署指南</span><span class="sxs-lookup"><span data-stu-id="a44dd-103">Deployment guidelines for Mediation Server in Skype for Business Server</span></span>
 
<span data-ttu-id="a44dd-104">本主题介绍中介服务器部署的规划准则。</span><span class="sxs-lookup"><span data-stu-id="a44dd-104">This topic describes planning guidelines for Mediation Server deployment.</span></span>
  
## <a name="collocated-or-stand-alone-mediation-server"></a><span data-ttu-id="a44dd-105">并站中介服务器还是独立中介服务器？</span><span class="sxs-lookup"><span data-stu-id="a44dd-105">Collocated or Stand-alone Mediation Server?</span></span>

<span data-ttu-id="a44dd-106">默认情况下，中介服务器并位于中央站点前端池中的 Standard Edition Server 或前端服务器上。</span><span class="sxs-lookup"><span data-stu-id="a44dd-106">Mediation Server is, by default, collocated on the Standard Edition server or Front End Server in a Front End pool at central sites.</span></span> <span data-ttu-id="a44dd-107">可以处理的公用电话交换网 (PSTN) 呼叫的数量，池中所需的计算机数量将取决于：</span><span class="sxs-lookup"><span data-stu-id="a44dd-107">The number of public switched telephone network (PSTN) calls that can be handled and the number of machines required in the pool will depend on:</span></span>
  
- <span data-ttu-id="a44dd-108">中介服务器池控制对等网关的数量。</span><span class="sxs-lookup"><span data-stu-id="a44dd-108">The number of gateway peers that the Mediation Server pool controls.</span></span>
    
- <span data-ttu-id="a44dd-109">通过这些网关的高流量时段。</span><span class="sxs-lookup"><span data-stu-id="a44dd-109">The high-volume traffic periods through those gateways.</span></span>
    
- <span data-ttu-id="a44dd-110">媒体绕过中介服务器的呼叫所占的呼叫百分比。</span><span class="sxs-lookup"><span data-stu-id="a44dd-110">The percentage of calls that are calls whose media bypass the Mediation Server.</span></span>
    
<span data-ttu-id="a44dd-111">在规划时，请务必考虑不支持媒体旁路的 PSTN 呼叫和 A/V 会议的媒体处理要求，以及处理需要支持的忙时呼叫数的信号交互所需的处理。</span><span class="sxs-lookup"><span data-stu-id="a44dd-111">When you're planning, be sure to take into account the media processing requirements for PSTN calls and A/V conferences that don't support media bypass, as well as the processing needed to handle signaling interactions for the number of busy-hour calls that need to be supported.</span></span> <span data-ttu-id="a44dd-112">如果没有足够的 CPU，则需要部署中介服务器独立池。</span><span class="sxs-lookup"><span data-stu-id="a44dd-112">If you don't have enough CPU, you'll need to deploy a stand-alone pool of Mediation Servers.</span></span> <span data-ttu-id="a44dd-113">此外，PSTN 网关、IP-PBX 和 SDC 将需要拆分为子集，这些子集由一个池中的并站中介服务器和一个或多个独立池中独立的中介服务器控制。</span><span class="sxs-lookup"><span data-stu-id="a44dd-113">Additionally, PSTN gateways, IP-PBXs, and SBCs will need to be split into subsets that are controlled by the collocated Mediation Servers in one pool and the stand-alone Mediation Servers in one or more stand-alone pools.</span></span>
  
<span data-ttu-id="a44dd-114">如果部署的 PSTN 网关、IP-PBX 或会话边界控制器 (SDC) 缺少与中介服务器池交互的能力，则需要将其与由单个中介服务器组成的独立池相关联。</span><span class="sxs-lookup"><span data-stu-id="a44dd-114">If you deployed PSTN gateways, IP-PBXs, or Session Border Controllers (SBCs) that lack the ability to interact with a pool of Mediation Servers, they'll need to be associated with a stand-alone pool consisting of a single Mediation Server.</span></span> <span data-ttu-id="a44dd-115">PSTN 网关、IP-PBXs SDC 需要执行以下一些操作：</span><span class="sxs-lookup"><span data-stu-id="a44dd-115">Some of the things your PSTN gateways, IP-PBXs or SBCs would need to do include:</span></span>
  
- <span data-ttu-id="a44dd-116">在池 (中的中介服务器之间执行网络层域名系统 (DNS) 负载平衡，或者将流量统一路由到池中所有中介服务器) 。</span><span class="sxs-lookup"><span data-stu-id="a44dd-116">Perform network layer Domain Name System (DNS) load balancing across Mediation Servers in a pool (or otherwise route traffic uniformly to all Mediation Servers in a pool).</span></span>
    
- <span data-ttu-id="a44dd-117">接受来自池中任何中介服务器的流量。</span><span class="sxs-lookup"><span data-stu-id="a44dd-117">Accept traffic from any Mediation Server in a pool.</span></span>
    
<span data-ttu-id="a44dd-118">Skype for Business 规划工具可用于评估将中介服务器与前端池并排是否可以处理负载。</span><span class="sxs-lookup"><span data-stu-id="a44dd-118">You can use the Skype for Business Planning Tool to evaluate whether collocating the Mediation Server with your Front End pool can handle the load.</span></span> <span data-ttu-id="a44dd-119">如果您的环境不能满足这些要求，则需要部署独立的中介服务器池。</span><span class="sxs-lookup"><span data-stu-id="a44dd-119">If your environment can't meet these requirements, then you'll need to deploy a stand-alone Mediation Server pool.</span></span>
  
## <a name="central-site-and-branch-site-considerations"></a><span data-ttu-id="a44dd-120">中央站点和分支站点注意事项</span><span class="sxs-lookup"><span data-stu-id="a44dd-120">Central Site and Branch Site Considerations</span></span>

 <span data-ttu-id="a44dd-121">中央站点的中介服务器可用于为分支站点的 IP-PBX 或 PSTN 网关路由呼叫。</span><span class="sxs-lookup"><span data-stu-id="a44dd-121">Mediation Servers at the central site can be used to route calls for IP-PBXs or PSTN gateways at branch sites.</span></span> <span data-ttu-id="a44dd-122">但是，如果部署 SIP 中继，您必须在每个中继终止的站点上部署中介服务器。</span><span class="sxs-lookup"><span data-stu-id="a44dd-122">If you deploy SIP trunks, however, you have to deploy a Mediation Server at the site where each trunk terminates.</span></span> <span data-ttu-id="a44dd-123">在中央站点部署中介服务器为分支站点上的 IP-PBX 或 PSTN 网关路由呼叫不需要使用媒体旁路，但建议使用媒体旁路。</span><span class="sxs-lookup"><span data-stu-id="a44dd-123">Having a Mediation Server at the central site route calls for an IP-PBX or PSTN gateway at a branch site doesn't require the use of media bypass, but a media bypass is recommended.</span></span> <span data-ttu-id="a44dd-124">这是因为，如果可以启用媒体旁路，它将减少媒体路径延迟，从而改善媒体质量，因为媒体路径不需要遵循信号路径。</span><span class="sxs-lookup"><span data-stu-id="a44dd-124">That's because, if you can enable media bypass, it'll reduce media path latency and, consequently, result in improved media quality because the media path isn't required to follow the signaling path.</span></span> <span data-ttu-id="a44dd-125">媒体绕过还将减少池中的处理负载。</span><span class="sxs-lookup"><span data-stu-id="a44dd-125">Media bypass will also decrease the processing load on the pool.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a44dd-126">媒体旁路不会与每个 PSTN 网关、IP-PBX 和 SBC 互操作。</span><span class="sxs-lookup"><span data-stu-id="a44dd-126">Media bypass won't interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="a44dd-127">Microsoft 已经与认证合作伙伴一起测试了一组 PSTN 网关和 SDC，并且已经使用 Cisco IP-PBX 进行了一些测试。</span><span class="sxs-lookup"><span data-stu-id="a44dd-127">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="a44dd-128">只有统一通信开放式互操作性计划 - Lync Server 中列出的产品和版本才支持媒体旁路功能，这些版本位于探索支持并扩展 Skype for Business 体验的经测试的设备、基础结构和[工具。](http://partnersolutions.skypeforbusiness.com/solutionscatalog)</span><span class="sxs-lookup"><span data-stu-id="a44dd-128">Media bypass is supported only with products and versions listed on Unified Communications Open Interoperability Program - Lync Server at [Explore tested devices, infrastructure, and tools that support and extend your Skype for Business experience](http://partnersolutions.skypeforbusiness.com/solutionscatalog).</span></span> 
  
<span data-ttu-id="a44dd-129">如果要求具有分支站点恢复能力，则必须在分支站点部署 Survivable Branch Appliance 或部署前端服务器、中介服务器和网关的组合。</span><span class="sxs-lookup"><span data-stu-id="a44dd-129">If branch site resiliency is required, a Survivable Branch Appliance or combination of a Front End Server, a Mediation Server, and a gateway must be deployed at the branch site.</span></span> <span data-ttu-id="a44dd-130"> (分支站点恢复能力的假设是，状态和会议在站点中无法恢复。) 有关分支站点语音规划的指导，请参阅 Plan [for 企业语音 resiliency in Skype for Business Server。](../enterprise-voice-solution/enterprise-voice-resiliency.md)</span><span class="sxs-lookup"><span data-stu-id="a44dd-130">(The assumption with branch site resiliency is that presence and conferencing are not resilient at the site.) For guidance on branch site planning for voice, see [Plan for Enterprise Voice resiliency in Skype for Business Server](../enterprise-voice-solution/enterprise-voice-resiliency.md).</span></span>
  
<span data-ttu-id="a44dd-131">对于与 IP-PBX 的交互，如果 IP-PBX 不能正确支持与多个早期对话的早期媒体交互和 RFC 3960 交互，则对于从 IP-PBX 到 Lync 终结点的传入呼叫，可能会截断问候语的前几个单词。</span><span class="sxs-lookup"><span data-stu-id="a44dd-131">For interactions with an IP-PBX, if the IP-PBX does not correctly support early media interactions with multiple early dialogs and RFC 3960 interactions, there can be clipping of the first few words of the greeting for incoming calls from the IP-PBX to Lync endpoints.</span></span> <span data-ttu-id="a44dd-132">如果中央站点上的中介服务器为 IP-PBX 路由呼叫，其中路由终止于分支站点，这种行为可能更为严重，因为完成信号需要更长时间。</span><span class="sxs-lookup"><span data-stu-id="a44dd-132">This behavior can be more severe if a Mediation Server at a central site is routing calls for an IP-PBX where the route terminates at a branch site, because more time is needed for signaling to complete.</span></span> <span data-ttu-id="a44dd-133">如果遇到此行为，在分支站点部署中介服务器是减少截断前几个单词的唯一方法。</span><span class="sxs-lookup"><span data-stu-id="a44dd-133">If you experience this behavior, deploying a Mediation Server at the branch site is the only way to reduce clipping of the first few words.</span></span>
  
<span data-ttu-id="a44dd-134">最后，如果中央站点具有 TDM PBX，或者 IP-PBX 仍然需要 PSTN 网关，则必须在连接中介服务器和 PBX 的呼叫路由上部署网关。</span><span class="sxs-lookup"><span data-stu-id="a44dd-134">Finally, if your central site has a TDM PBX, or if your IP-PBX does not eliminate the need for a PSTN gateway, then you must deploy a gateway on the call route connecting Mediation Server and the PBX.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a44dd-135">若要提高独立中介服务器的媒体性能，您应在这些服务器上网络适配器 (RSS) 启用接收端缩放。</span><span class="sxs-lookup"><span data-stu-id="a44dd-135">To improve the media performance of standalone Mediation Server, you should enable receive-side scaling (RSS) on the network adapters on these servers.</span></span> <span data-ttu-id="a44dd-136">通过启用 RSS，服务器上的多个处理器能够以并行方式处理传入数据包。</span><span class="sxs-lookup"><span data-stu-id="a44dd-136">RSS enables incoming packets to be handled in parallel by multiple processors on the server.</span></span> <span data-ttu-id="a44dd-137">有关详细信息，请参阅"[Windows Server 中的接收端缩放](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh997036(v=ws.11))增强功能"。</span><span class="sxs-lookup"><span data-stu-id="a44dd-137">For details, see "[Receive-Side Scaling Enhancements in Windows Server](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh997036(v=ws.11))".</span></span> <span data-ttu-id="a44dd-138">若要详细了解如何启用 RSS，请参阅网络适配器文档。</span><span class="sxs-lookup"><span data-stu-id="a44dd-138">For details about how to enable RSS, see your network adapter documentation.</span></span> 
