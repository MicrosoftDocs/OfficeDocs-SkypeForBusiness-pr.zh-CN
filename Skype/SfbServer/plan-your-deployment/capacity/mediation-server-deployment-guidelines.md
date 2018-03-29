---
title: Skype for Business Server 2015 中的中介服务器部署准则
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7cc22b87-18d9-45e6-8402-015abd20f2e5
description: 本主题介绍中介服务器部署的规划的准则。
ms.openlocfilehash: e1017e9fab43578fd3c10e8043c7dcc747d313b9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="deployment-guidelines-for-mediation-server-in-skype-for-business-server-2015"></a><span data-ttu-id="edbb3-103">Skype for Business Server 2015 中的中介服务器部署准则</span><span class="sxs-lookup"><span data-stu-id="edbb3-103">Deployment guidelines for Mediation Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="edbb3-104">本主题介绍中介服务器部署的规划的准则。</span><span class="sxs-lookup"><span data-stu-id="edbb3-104">This topic describes planning guidelines for Mediation Server deployment.</span></span>
  
## <a name="collocated-or-stand-alone-mediation-server"></a><span data-ttu-id="edbb3-105">按顺序排列或独立的中介服务器？</span><span class="sxs-lookup"><span data-stu-id="edbb3-105">Collocated or Stand-alone Mediation Server?</span></span>

<span data-ttu-id="edbb3-106">中介服务器，默认情况下，搭配使用标准版服务器或在中心站点的前端池在前端服务器上。</span><span class="sxs-lookup"><span data-stu-id="edbb3-106">Mediation Server is, by default, collocated on the Standard Edition server or Front End Server in a Front End pool at central sites.</span></span> <span data-ttu-id="edbb3-107">可以处理的公用电话交换网 (PSTN) 呼叫数和池中所需的计算机数取决于以下因素：</span><span class="sxs-lookup"><span data-stu-id="edbb3-107">The number of public switched telephone network (PSTN) calls that can be handled and the number of machines required in the pool will depend on:</span></span>
  
- <span data-ttu-id="edbb3-108">网关中介服务器池控制的对等方的数目。</span><span class="sxs-lookup"><span data-stu-id="edbb3-108">The number of gateway peers that the Mediation Server pool controls.</span></span>
    
- <span data-ttu-id="edbb3-109">通过这些网关的高流量时段。</span><span class="sxs-lookup"><span data-stu-id="edbb3-109">The high-volume traffic periods through those gateways.</span></span>
    
- <span data-ttu-id="edbb3-110">其媒体绕过中介服务器的调用的调用的百分比。</span><span class="sxs-lookup"><span data-stu-id="edbb3-110">The percentage of calls that are calls whose media bypass the Mediation Server.</span></span>
    
<span data-ttu-id="edbb3-111">规划时，请确保考虑不支持媒体旁路的 PSTN 呼叫和 A/V 会议的媒体处理要求，同时考虑处理必须支持的忙时呼叫数量的信号交互所需的处理要求。</span><span class="sxs-lookup"><span data-stu-id="edbb3-111">When you're planning, be sure to take into account the media processing requirements for PSTN calls and A/V conferences that don't support media bypass, as well as the processing needed to handle signaling interactions for the number of busy-hour calls that need to be supported.</span></span> <span data-ttu-id="edbb3-112">如果您没有足够的 CPU，您将需要部署独立的中介服务器池。</span><span class="sxs-lookup"><span data-stu-id="edbb3-112">If you don't have enough CPU, you'll need to deploy a stand-alone pool of Mediation Servers.</span></span> <span data-ttu-id="edbb3-113">此外，PSTN 网关，IP 的 Pbx 和 SBCs 需要拆分成将由在一个池中的并入的中介服务器和独立的中介服务器中一个或多个独立的池控制的子集。</span><span class="sxs-lookup"><span data-stu-id="edbb3-113">Additionally, PSTN gateways, IP-PBXs, and SBCs will need to be split into subsets that are controlled by the collocated Mediation Servers in one pool and the stand-alone Mediation Servers in one or more stand-alone pools.</span></span>
  
<span data-ttu-id="edbb3-114">如果您部署 PSTN 网关，IP Pbx 的或会话边框控制器 (SBCs)，缺乏与池的中介服务器进行交互的能力，他们需要与独立池包含单一的中介服务器有关联。</span><span class="sxs-lookup"><span data-stu-id="edbb3-114">If you deployed PSTN gateways, IP-PBXs, or Session Border Controllers (SBCs) that lack the ability to interact with a pool of Mediation Servers, they'll need to be associated with a stand-alone pool consisting of a single Mediation Server.</span></span> <span data-ttu-id="edbb3-115">您的 PSTN 网关、IP-PBX 或 SBC 需要执行的某些操作包括：</span><span class="sxs-lookup"><span data-stu-id="edbb3-115">Some of the things your PSTN gateways, IP-PBXs or SBCs would need to do include:</span></span>
  
- <span data-ttu-id="edbb3-116">执行域名系统 (DNS) 负载平衡在池中的中介服务器之间的网络层 （或否则路由通信统一到池中的所有中介服务器）。</span><span class="sxs-lookup"><span data-stu-id="edbb3-116">Perform network layer Domain Name System (DNS) load balancing across Mediation Servers in a pool (or otherwise route traffic uniformly to all Mediation Servers in a pool).</span></span>
    
- <span data-ttu-id="edbb3-117">接受从池中任何中介服务器的通信流。</span><span class="sxs-lookup"><span data-stu-id="edbb3-117">Accept traffic from any Mediation Server in a pool.</span></span>
    
<span data-ttu-id="edbb3-118">您可以使用 Microsoft Lync Server 2013，规划工具来评估是否配置前端池与中介服务器可以处理的负载。</span><span class="sxs-lookup"><span data-stu-id="edbb3-118">You can use the Microsoft Lync Server 2013, Planning Tool to evaluate whether collocating the Mediation Server with your Front End pool can handle the load.</span></span> <span data-ttu-id="edbb3-119">如果您的环境不能满足这些要求，您将需要部署独立的中介服务器池。</span><span class="sxs-lookup"><span data-stu-id="edbb3-119">If your environment can't meet these requirements, then you'll need to deploy a stand-alone Mediation Server pool.</span></span>
  
## <a name="central-site-and-branch-site-considerations"></a><span data-ttu-id="edbb3-120">中央站点和分支站点注意事项</span><span class="sxs-lookup"><span data-stu-id="edbb3-120">Central Site and Branch Site Considerations</span></span>

 <span data-ttu-id="edbb3-121">场地中央的中介服务器可用于路由呼叫到 IP Pbx 或 PSTN 网关处的分支站点。</span><span class="sxs-lookup"><span data-stu-id="edbb3-121">Mediation Servers at the central site can be used to route calls for IP-PBXs or PSTN gateways at branch sites.</span></span> <span data-ttu-id="edbb3-122">如果部署 SIP 中继，但是，您需要部署中介服务器站点每个中继的终止位置。</span><span class="sxs-lookup"><span data-stu-id="edbb3-122">If you deploy SIP trunks, however, you have to deploy a Mediation Server at the site where each trunk terminates.</span></span> <span data-ttu-id="edbb3-123">中心站点让中介服务器调用路由 IP PBX 或 PSTN 网关在分支站点不需要绕过媒体的使用，但建议媒体回避。</span><span class="sxs-lookup"><span data-stu-id="edbb3-123">Having a Mediation Server at the central site route calls for an IP-PBX or PSTN gateway at a branch site doesn't require the use of media bypass, but a media bypass is recommended.</span></span> <span data-ttu-id="edbb3-124">这是因为，如果可以启用媒体绕过，则可以降低媒体路径延迟，从而改善媒体质量，因为媒体路径不再需要遵循信号路径。</span><span class="sxs-lookup"><span data-stu-id="edbb3-124">That's because, if you can enable media bypass, it'll reduce media path latency and, consequently, result in improved media quality because the media path isn't required to follow the signaling path.</span></span> <span data-ttu-id="edbb3-125">媒体绕过还将减少池中的处理负载。</span><span class="sxs-lookup"><span data-stu-id="edbb3-125">Media bypass will also decrease the processing load on the pool.</span></span>
  
> [!NOTE]
> <span data-ttu-id="edbb3-126">媒体旁路将不会与每个 PSTN 网关、IP-PBX 和 SBC 进行交互操作。</span><span class="sxs-lookup"><span data-stu-id="edbb3-126">Media bypass won't interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="edbb3-127">Microsoft 与认证合作伙伴一起对一组 PSTN 网关和 SBC 进行了测试，另外也对 Cisco IP-PBX 进行了一些测试。</span><span class="sxs-lookup"><span data-stu-id="edbb3-127">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="edbb3-128">媒体回避仅支持产品和版本列入统一通信开放互操作性计划-Lync 服务器[资源管理器测试设备、 基础架构和工具的支持和扩展您的业务体验 Skype](http://partnersolutions.skypeforbusiness.com/solutionscatalog)。</span><span class="sxs-lookup"><span data-stu-id="edbb3-128">Media bypass is supported only with products and versions listed on Unified Communications Open Interoperability Program - Lync Server at [Explore tested devices, infrastructure, and tools that support and extend your Skype for Business experience](http://partnersolutions.skypeforbusiness.com/solutionscatalog).</span></span> 
  
<span data-ttu-id="edbb3-129">如果需要分支站点恢复能力，高存活力的分支装置或前端服务器、 中介服务器和网关的组合必须部署在分支站点。</span><span class="sxs-lookup"><span data-stu-id="edbb3-129">If branch site resiliency is required, a Survivable Branch Appliance or combination of a Front End Server, a Mediation Server, and a gateway must be deployed at the branch site.</span></span> <span data-ttu-id="edbb3-130">（分支站点恢复能力与假设是存在和会议不适应性在站点。）有关分支站点规划的语音指导，请参见[分支站点语音留存能力的规划](https://technet.microsoft.com/en-us/library/gg398477%28v=ocs.15%29.aspx)文档，如仍应与相关的业务服务器 2015年的 Skype。</span><span class="sxs-lookup"><span data-stu-id="edbb3-130">(The assumption with branch site resiliency is that presence and conferencing are not resilient at the site.) For guidance on branch site planning for voice, see our [Planning for Branch-Site Voice Resiliency](https://technet.microsoft.com/en-us/library/gg398477%28v=ocs.15%29.aspx) documentation, as it should still be relevant for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="edbb3-131">对于 IP PBX 与交互，如果 IP PBX 无法正常支持与多个早期对话的早期媒体交互和 RFC 3960 交互，可以有剪辑的第一个传入呼叫从 IP PBX Lync 终结点为问候几句。</span><span class="sxs-lookup"><span data-stu-id="edbb3-131">For interactions with an IP-PBX, if the IP-PBX does not correctly support early media interactions with multiple early dialogs and RFC 3960 interactions, there can be clipping of the first few words of the greeting for incoming calls from the IP-PBX to Lync endpoints.</span></span> <span data-ttu-id="edbb3-132">此行为可能更严重，如果中央站点的中介服务器路由的 IP PBX 电话路由分支地点，将终止，因为信号来完成需要更多的时间。</span><span class="sxs-lookup"><span data-stu-id="edbb3-132">This behavior can be more severe if a Mediation Server at a central site is routing calls for an IP-PBX where the route terminates at a branch site, because more time is needed for signaling to complete.</span></span> <span data-ttu-id="edbb3-133">如果您遇到这种情况，部署中介服务器在分部地点是第的唯一的方法，以减少修剪几个字。</span><span class="sxs-lookup"><span data-stu-id="edbb3-133">If you experience this behavior, deploying a Mediation Server at the branch site is the only way to reduce clipping of the first few words.</span></span>
  
<span data-ttu-id="edbb3-134">最后，如果中心站点 TDM PBX，或者您 IP PBX 并不能排除需要 PSTN 网关，则必须部署上连接中介服务器和 PBX 的呼叫路由的网关。</span><span class="sxs-lookup"><span data-stu-id="edbb3-134">Finally, if your central site has a TDM PBX, or if your IP-PBX does not eliminate the need for a PSTN gateway, then you must deploy a gateway on the call route connecting Mediation Server and the PBX.</span></span>
  
> [!NOTE]
> <span data-ttu-id="edbb3-135">要提高独立的中介服务器的媒体性能，应在这些服务器的网络适配器上启用接收方缩放 (RSS)。</span><span class="sxs-lookup"><span data-stu-id="edbb3-135">To improve the media performance of standalone Mediation Server, you should enable receive-side scaling (RSS) on the network adapters on these servers.</span></span> <span data-ttu-id="edbb3-136">通过启用 RSS，服务器上的多个处理器能够以并行方式处理传入数据包。</span><span class="sxs-lookup"><span data-stu-id="edbb3-136">RSS enables incoming packets to be handled in parallel by multiple processors on the server.</span></span> <span data-ttu-id="edbb3-137">有关详细信息，请参阅"[Windows 服务器中接收端扩展增强功能](https://go.microsoft.com/fwlink/p/?LinkId=268731)"。</span><span class="sxs-lookup"><span data-stu-id="edbb3-137">For details, see "[Receive-Side Scaling Enhancements in Windows Server](https://go.microsoft.com/fwlink/p/?LinkId=268731)".</span></span> <span data-ttu-id="edbb3-138">有关如何启用 RSS 的详细信息，请参阅网络适配器文档。</span><span class="sxs-lookup"><span data-stu-id="edbb3-138">For details about how to enable RSS, see your network adapter documentation.</span></span> 
  

