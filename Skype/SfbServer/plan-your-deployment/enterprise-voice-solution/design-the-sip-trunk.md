---
title: 在 Skype for Business 服务器中设计 E9 的 SIP 主干-1-1
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
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4f93b974-b460-45c7-a4a8-6f38e34840f5
description: 为在 Skype for Business Server 企业语音中使用 SIP 中继提供商的 E9 部署计划 SIP 中继拓扑。
ms.openlocfilehash: bd310b39affbea9b4d9328c66b54712c0d388b8d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803072"
---
# <a name="design-the-sip-trunk-for-e9-1-1-in-skype-for-business-server"></a><span data-ttu-id="fb9de-103">在 Skype for Business 服务器中设计 E9 的 SIP 主干-1-1</span><span class="sxs-lookup"><span data-stu-id="fb9de-103">Design the SIP trunk for E9-1-1 in Skype for Business Server</span></span>
 
<span data-ttu-id="fb9de-104">为在 Skype for Business Server 企业语音中使用 SIP 中继提供商的 E9 部署计划 SIP 中继拓扑。</span><span class="sxs-lookup"><span data-stu-id="fb9de-104">Planning your SIP trunking topologies for an E9-1-1 deployment that uses SIP trunking providers, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="fb9de-105">Skype for business 服务器使用 SIP 中继将紧急电话连接到 E9 服务提供商。</span><span class="sxs-lookup"><span data-stu-id="fb9de-105">Skype for Business Server uses SIP trunks to connect an emergency call to the E9-1-1 service provider.</span></span> <span data-ttu-id="fb9de-106">您可以为一个中央站点、多个中央站点或每个分支站点的 E9-1-1 设置紧急服务 SIP 中继。</span><span class="sxs-lookup"><span data-stu-id="fb9de-106">You can set up emergency service SIP trunks for E9-1-1 at one central site, at multiple central sites, or at each branch site.</span></span> <span data-ttu-id="fb9de-107">但是，如果呼叫者的站点和托管紧急服务 SIP 主干的网站之间的 WAN 链接不可用，则由用户在断开连接的站点处发出的呼叫将需要用户语音策略中的特殊电话使用记录，并将呼叫路由到通过本地公共交换电话网络（PSTN）网关 ECRC。</span><span class="sxs-lookup"><span data-stu-id="fb9de-107">However, if the WAN link between the caller's site and the site that hosts the emergency service SIP trunk is unavailable, then a call placed by a user at the disconnected site will need a special phone usage record in the user's voice policy that will route the call to the ECRC through the local public switched telephone network (PSTN) gateway.</span></span> <span data-ttu-id="fb9de-108">如果呼叫允许控制并发呼叫限制有效，则会出现相同情况。</span><span class="sxs-lookup"><span data-stu-id="fb9de-108">The same is true if call admission control concurrent call limits are in effect.</span></span>
  
<span data-ttu-id="fb9de-109">可通过两种方式在 Skype for Business Server 环境中实施 SIP 主干：</span><span class="sxs-lookup"><span data-stu-id="fb9de-109">There are two ways to implement a SIP trunk in a Skype for Business Server environment:</span></span>
  
- <span data-ttu-id="fb9de-110">使用多主中介服务器，这些服务器使用其面向外部的公共路由接口与 SIP 中继提供商通信。</span><span class="sxs-lookup"><span data-stu-id="fb9de-110">Use multihomed Mediation Servers that use their outward-facing publicly-routed interfaces to communicate with the SIP trunk provider.</span></span>
    
- <span data-ttu-id="fb9de-111">使用本地会话边界控制器（SBC）在中介服务器和 SIP 中继提供商的服务之间提供安全的 demarcation 点。</span><span class="sxs-lookup"><span data-stu-id="fb9de-111">Use an on-premises Session Border Controller (SBC) to provide a secure demarcation point between the Mediation Servers and the SIP trunk provider's services.</span></span>
    
<span data-ttu-id="fb9de-112">如果您选择后一种方法，请确保您选择的 SBC 品牌和型号已经过认证并且支持将状态信息数据格式位置对象 (PIDF-LO) 位置数据作为其 SIP INVITE 一部分传递。</span><span class="sxs-lookup"><span data-stu-id="fb9de-112">If you choose the latter method, be sure that the SBC make and model that you choose has been certified and supports passing Presence Information Data Format Location Object (PIDF-LO) location data as part of its SIP INVITE.</span></span> <span data-ttu-id="fb9de-113">否则，呼叫将在缺少位置信息的情况下到达紧急服务的服务提供商。</span><span class="sxs-lookup"><span data-stu-id="fb9de-113">Otherwise, the calls will arrive at the emergency services service provider stripped of their location information.</span></span> <span data-ttu-id="fb9de-114">有关认证的 SBCs 的详细信息，请参阅["适用于 Microsoft Lync 的基础结构认证"](https://go.microsoft.com/fwlink/p/?LinkId=248425)和["Skype For Business 的电话架构"](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways)。</span><span class="sxs-lookup"><span data-stu-id="fb9de-114">For details about certified SBCs, see   ["Infrastructure Qualified for Microsoft Lync"](https://go.microsoft.com/fwlink/p/?LinkId=248425) and ["Telephony Infrastructure for Skype for Business"](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways).</span></span> 
  
<span data-ttu-id="fb9de-115">E9-1-1 的服务提供商会向您提供对 SBC 对的访问权，以实现冗余。</span><span class="sxs-lookup"><span data-stu-id="fb9de-115">E9-1-1 service providers supply you with access to a pair of SBCs for redundancy.</span></span> <span data-ttu-id="fb9de-116">您需要对中介服务器拓扑和呼叫路由配置进行几项决策。</span><span class="sxs-lookup"><span data-stu-id="fb9de-116">You need to make several decisions regarding the Mediation Server topology and call routing configuration.</span></span> <span data-ttu-id="fb9de-117">您是否平等看待两个 SBC 并对它们之间的呼叫使用循环路由，或者您是否以其中一个 SBC 为主，而另一个为辅？</span><span class="sxs-lookup"><span data-stu-id="fb9de-117">Will you treat both SBCs as equal peers and use round-robin routing for calls between them, or will you designate one SBC as primary and the other as secondary?</span></span>
  
<span data-ttu-id="fb9de-118">有关在 Skype for Business 服务器中部署 SIP 主干的详细信息，请参阅[skype For Business 服务器中的 sip 中继](sip-trunking.md)。</span><span class="sxs-lookup"><span data-stu-id="fb9de-118">For details about deploying a SIP trunk in Skype for Business Server, see [SIP trunking in Skype for Business Server](sip-trunking.md).</span></span> <span data-ttu-id="fb9de-119">下列问题将帮助您确定如何部署 E9-1-1 的 SIP 中继。</span><span class="sxs-lookup"><span data-stu-id="fb9de-119">The following questions will help you decide how to deploy the SIP trunks for E9-1-1.</span></span>
  
 <span data-ttu-id="fb9de-120">**应该通过专门租用的 Internet 连接还是共享的 Internet 连接部署 SIP 中继？**</span><span class="sxs-lookup"><span data-stu-id="fb9de-120">**Should you deploy the SIP trunk over a dedicated leased or a shared internet connection?**</span></span>
  
> <span data-ttu-id="fb9de-p105">紧急呼叫必须始终保持连接状态，这一点很重要。专用线路将提供不会被网络中其他流量抢占的连接以及实现服务质量 (QoS) 的功能。请记住，如果通过公共 Internet 连接到紧急服务的服务提供商，并且需要确保紧急呼叫的保密性，则需要 IPSec 加密。</span><span class="sxs-lookup"><span data-stu-id="fb9de-p105">It is important that emergency calls always connect. A dedicated line provides a connection that will not be preempted by other traffic on the network, and gives you the ability to implement Quality of Service (QoS). Remember that if you are connecting to emergency services service providers over the public Internet and you need to guarantee the confidentiality of emergency calls, IPSec encryption is required.</span></span> 
    
 <span data-ttu-id="fb9de-124">**您的 E9 部署是否是为灾难容许而设计的？**</span><span class="sxs-lookup"><span data-stu-id="fb9de-124">**Is your E9-1-1 deployment designed for disaster tolerance?**</span></span>
  
> <span data-ttu-id="fb9de-125">由于这是紧急解决方案，因此复原很重要。</span><span class="sxs-lookup"><span data-stu-id="fb9de-125">Because this is an emergency solution, resiliency is important.</span></span> <span data-ttu-id="fb9de-126">在灾难容错位置部署主要和辅助中介服务器以及 SIP 中继。</span><span class="sxs-lookup"><span data-stu-id="fb9de-126">Deploy your primary and secondary Mediation Servers and SIP trunks in disaster tolerant locations.</span></span> <span data-ttu-id="fb9de-127">最好是部署最接近其支持的用户的主中介服务器，并通过辅助中介服务器（位于不同的地理位置）路由故障转移呼叫。</span><span class="sxs-lookup"><span data-stu-id="fb9de-127">It is a good idea to deploy your primary Mediation Server closest to the users that it is supporting, and route failover calls through the secondary Mediation Server (located in a different geographic location).</span></span> 
    
 <span data-ttu-id="fb9de-128">**是否应该为每个分支机构部署单独的 SIP 中继？**</span><span class="sxs-lookup"><span data-stu-id="fb9de-128">**Should you deploy a separate SIP trunk for each branch office?**</span></span>
  
> <span data-ttu-id="fb9de-129">Skype for Business 服务器提供了多个用于处理分支机构中的语音复原的策略，包括：具有弹性数据网络、在每个分支处部署 SIP 主干或在中断期间将呼叫推送到本地网关。</span><span class="sxs-lookup"><span data-stu-id="fb9de-129">Skype for Business Server provides several strategies for handling voice resiliency in branch offices, including: having resilient data networks, deploying a SIP trunk at each branch, or pushing calls out to the local gateway during outages.</span></span> <span data-ttu-id="fb9de-130">有关详细信息，请参阅[Skype For Business 服务器中的 SIP 中继](sip-trunking.md)。</span><span class="sxs-lookup"><span data-stu-id="fb9de-130">For details, see [SIP trunking in Skype for Business Server](sip-trunking.md).</span></span>
    
 <span data-ttu-id="fb9de-131">**是否已启用呼叫允许控制 (CAC)？**</span><span class="sxs-lookup"><span data-stu-id="fb9de-131">**Is call admission control (CAC) enabled?**</span></span>
  
> <span data-ttu-id="fb9de-132">Skype for Business 服务器不会处理与普通通话不同的紧急呼叫。</span><span class="sxs-lookup"><span data-stu-id="fb9de-132">Skype for Business Server does not handle emergency calls any differently than an ordinary call.</span></span> <span data-ttu-id="fb9de-133">因此，带宽管理或呼叫允许控制 (CAC) 将对 E9-1-1 配置产生负面影响。</span><span class="sxs-lookup"><span data-stu-id="fb9de-133">For this reason, bandwidth management, or call admission control (CAC), can have a negative impact on an E9-1-1 configuration.</span></span> <span data-ttu-id="fb9de-134">如果已启用 CAC，并且路由紧急呼叫的链接上的流量超过配置的限制，那么将阻止紧急呼叫或将其路由至本地 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="fb9de-134">Emergency calls will be blocked or routed to the local PSTN gateway if a CAC is enabled and the configured limit is exceeded on a link where emergency calls are being routed.</span></span> <span data-ttu-id="fb9de-135">如本主题前面所述，此类呼叫不包含位置数据，必须手动将其路由到 ECRC。</span><span class="sxs-lookup"><span data-stu-id="fb9de-135">As indicated earlier in this topic, such calls will not have location data and must be manually routed to the ECRC.</span></span>
    

