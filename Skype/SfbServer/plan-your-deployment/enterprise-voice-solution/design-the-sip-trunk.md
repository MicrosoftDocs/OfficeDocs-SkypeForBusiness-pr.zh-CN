---
title: SIP 中继的设计 E9-1-1 在 Skype 业务服务器
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4f93b974-b460-45c7-a4a8-6f38e34840f5
description: 规划业务 Server 企业语音的 Skype 中使用 SIP 中继提供商，E9-1-1 部署 SIP 中继拓扑。
ms.openlocfilehash: 25d961c00eb701dce6386ce2a901c1fbe5cf3cde
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30893638"
---
# <a name="design-the-sip-trunk-for-e9-1-1-in-skype-for-business-server"></a><span data-ttu-id="8094b-103">SIP 中继的设计 E9-1-1 在 Skype 业务服务器</span><span class="sxs-lookup"><span data-stu-id="8094b-103">Design the SIP trunk for E9-1-1 in Skype for Business Server</span></span>
 
<span data-ttu-id="8094b-104">规划业务 Server 企业语音的 Skype 中使用 SIP 中继提供商，E9-1-1 部署 SIP 中继拓扑。</span><span class="sxs-lookup"><span data-stu-id="8094b-104">Planning your SIP trunking topologies for an E9-1-1 deployment that uses SIP trunking providers, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="8094b-105">Skype 业务服务器使用 SIP 中继连接到 E9-1-1 服务提供商的紧急呼叫。</span><span class="sxs-lookup"><span data-stu-id="8094b-105">Skype for Business Server uses SIP trunks to connect an emergency call to the E9-1-1 service provider.</span></span> <span data-ttu-id="8094b-106">您可以为一个中央站点、多个中央站点或每个分支站点的 E9-1-1 设置紧急服务 SIP 中继。</span><span class="sxs-lookup"><span data-stu-id="8094b-106">You can set up emergency service SIP trunks for E9-1-1 at one central site, at multiple central sites, or at each branch site.</span></span> <span data-ttu-id="8094b-107">但是，如果呼叫者的站点和站点之间承载的 WAN 链路紧急服务 SIP 中继是不可用，则在断开连接的站点的用户发出的呼叫将需要在将将呼叫路由到的用户的语音策略中的特殊的电话用法记录通过本地公用电话交换网 (pstn) 网关 ECRC。</span><span class="sxs-lookup"><span data-stu-id="8094b-107">However, if the WAN link between the caller's site and the site that hosts the emergency service SIP trunk is unavailable, then a call placed by a user at the disconnected site will need a special phone usage record in the user's voice policy that will route the call to the ECRC through the local public switched telephone network (PSTN) gateway.</span></span> <span data-ttu-id="8094b-108">如果呼叫允许控制并发呼叫限制有效，则会出现相同情况。</span><span class="sxs-lookup"><span data-stu-id="8094b-108">The same is true if call admission control concurrent call limits are in effect.</span></span>
  
<span data-ttu-id="8094b-109">有两种方法在 Skype 业务服务器环境中实现 SIP 中继：</span><span class="sxs-lookup"><span data-stu-id="8094b-109">There are two ways to implement a SIP trunk in a Skype for Business Server environment:</span></span>
  
- <span data-ttu-id="8094b-110">使用多宿主使用其对外公共路由接口与通信 SIP 中继提供商的中介服务器。</span><span class="sxs-lookup"><span data-stu-id="8094b-110">Use multihomed Mediation Servers that use their outward-facing publicly-routed interfaces to communicate with the SIP trunk provider.</span></span>
    
- <span data-ttu-id="8094b-111">使用本地会话边界控制器 (SBC) 提供安全的分界点中介服务器之间的 SIP 中继提供商服务。</span><span class="sxs-lookup"><span data-stu-id="8094b-111">Use an on-premises Session Border Controller (SBC) to provide a secure demarcation point between the Mediation Servers and the SIP trunk provider's services.</span></span>
    
<span data-ttu-id="8094b-112">如果您选择后一种方法，请确保您选择的 SBC 品牌和型号已经过认证并且支持将状态信息数据格式位置对象 (PIDF-LO) 位置数据作为其 SIP INVITE 一部分传递。</span><span class="sxs-lookup"><span data-stu-id="8094b-112">If you choose the latter method, be sure that the SBC make and model that you choose has been certified and supports passing Presence Information Data Format Location Object (PIDF-LO) location data as part of its SIP INVITE.</span></span> <span data-ttu-id="8094b-113">否则，呼叫将在缺少位置信息的情况下到达紧急服务的服务提供商。</span><span class="sxs-lookup"><span data-stu-id="8094b-113">Otherwise, the calls will arrive at the emergency services service provider stripped of their location information.</span></span> <span data-ttu-id="8094b-114">有关认证 SBCs 详细信息，请参阅["基础结构限定针对 Microsoft Lync"](https://go.microsoft.com/fwlink/p/?LinkId=248425)和["电话基础结构的 Skype 的业务"](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways)。</span><span class="sxs-lookup"><span data-stu-id="8094b-114">For details about certified SBCs, see   ["Infrastructure Qualified for Microsoft Lync"](https://go.microsoft.com/fwlink/p/?LinkId=248425) and ["Telephony Infrastructure for Skype for Business"](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways).</span></span> 
  
<span data-ttu-id="8094b-115">E9-1-1 的服务提供商会向您提供对 SBC 对的访问权，以实现冗余。</span><span class="sxs-lookup"><span data-stu-id="8094b-115">E9-1-1 service providers supply you with access to a pair of SBCs for redundancy.</span></span> <span data-ttu-id="8094b-116">您需要决定几个有关中介服务器拓扑结构和呼叫路由配置。</span><span class="sxs-lookup"><span data-stu-id="8094b-116">You need to make several decisions regarding the Mediation Server topology and call routing configuration.</span></span> <span data-ttu-id="8094b-117">您是否平等看待两个 SBC 并对它们之间的呼叫使用循环路由，或者您是否以其中一个 SBC 为主，而另一个为辅？</span><span class="sxs-lookup"><span data-stu-id="8094b-117">Will you treat both SBCs as equal peers and use round-robin routing for calls between them, or will you designate one SBC as primary and the other as secondary?</span></span>
  
<span data-ttu-id="8094b-118">有关业务服务器部署中 Skype 的 SIP 中继的详细信息，请参阅[Skype 业务服务器中的 SIP 中继](sip-trunking.md)。</span><span class="sxs-lookup"><span data-stu-id="8094b-118">For details about deploying a SIP trunk in Skype for Business Server, see [SIP trunking in Skype for Business Server](sip-trunking.md).</span></span> <span data-ttu-id="8094b-119">下列问题将帮助您确定如何部署 E9-1-1 的 SIP 中继。</span><span class="sxs-lookup"><span data-stu-id="8094b-119">The following questions will help you decide how to deploy the SIP trunks for E9-1-1.</span></span>
  
 <span data-ttu-id="8094b-120">**应该通过专门租用的 Internet 连接还是共享的 Internet 连接部署 SIP 中继？**</span><span class="sxs-lookup"><span data-stu-id="8094b-120">**Should you deploy the SIP trunk over a dedicated leased or a shared internet connection?**</span></span>
  
> <span data-ttu-id="8094b-p105">紧急呼叫必须始终保持连接状态，这一点很重要。专用线路将提供不会被网络中其他流量抢占的连接以及实现服务质量 (QoS) 的功能。请记住，如果通过公共 Internet 连接到紧急服务的服务提供商，并且需要确保紧急呼叫的保密性，则需要 IPSec 加密。</span><span class="sxs-lookup"><span data-stu-id="8094b-p105">It is important that emergency calls always connect. A dedicated line provides a connection that will not be preempted by other traffic on the network, and gives you the ability to implement Quality of Service (QoS). Remember that if you are connecting to emergency services service providers over the public Internet and you need to guarantee the confidentiality of emergency calls, IPSec encryption is required.</span></span> 
    
 <span data-ttu-id="8094b-124">**是您 E9-1-1 部署是否设计用于容灾？**</span><span class="sxs-lookup"><span data-stu-id="8094b-124">**Is your E9-1-1 deployment designed for disaster tolerance?**</span></span>
  
> <span data-ttu-id="8094b-125">由于这是紧急解决方案，因此复原很重要。</span><span class="sxs-lookup"><span data-stu-id="8094b-125">Because this is an emergency solution, resiliency is important.</span></span> <span data-ttu-id="8094b-126">部署您主要和辅助中介服务器和 SIP 中继灾难容错位置。</span><span class="sxs-lookup"><span data-stu-id="8094b-126">Deploy your primary and secondary Mediation Servers and SIP trunks in disaster tolerant locations.</span></span> <span data-ttu-id="8094b-127">最好将主中介服务器支持，用户最接近部署和路由故障转移呼叫通过辅助中介服务器 （位于不同地理位置）。</span><span class="sxs-lookup"><span data-stu-id="8094b-127">It is a good idea to deploy your primary Mediation Server closest to the users that it is supporting, and route failover calls through the secondary Mediation Server (located in a different geographic location).</span></span> 
    
 <span data-ttu-id="8094b-128">**是否应该为每个分支机构部署单独的 SIP 中继？**</span><span class="sxs-lookup"><span data-stu-id="8094b-128">**Should you deploy a separate SIP trunk for each branch office?**</span></span>
  
> <span data-ttu-id="8094b-129">Skype 业务服务器提供用于处理，包括为分支机构中的语音恢复能力的多个策略： 具有可恢复的数据网络、 部署在每个分支中，SIP 中继或推送呼叫到本地网关在中断期间。</span><span class="sxs-lookup"><span data-stu-id="8094b-129">Skype for Business Server provides several strategies for handling voice resiliency in branch offices, including: having resilient data networks, deploying a SIP trunk at each branch, or pushing calls out to the local gateway during outages.</span></span> <span data-ttu-id="8094b-130">有关详细信息，请参阅[Skype 业务服务器中的 SIP 中继](sip-trunking.md)。</span><span class="sxs-lookup"><span data-stu-id="8094b-130">For details, see [SIP trunking in Skype for Business Server](sip-trunking.md).</span></span>
    
 <span data-ttu-id="8094b-131">**是否已启用呼叫允许控制 (CAC)？**</span><span class="sxs-lookup"><span data-stu-id="8094b-131">**Is call admission control (CAC) enabled?**</span></span>
  
> <span data-ttu-id="8094b-132">Skype 业务服务器句柄紧急呼叫任何不同于普通的呼叫。</span><span class="sxs-lookup"><span data-stu-id="8094b-132">Skype for Business Server does not handle emergency calls any differently than an ordinary call.</span></span> <span data-ttu-id="8094b-133">因此，带宽管理或呼叫允许控制 (CAC) 将对 E9-1-1 配置产生负面影响。</span><span class="sxs-lookup"><span data-stu-id="8094b-133">For this reason, bandwidth management, or call admission control (CAC), can have a negative impact on an E9-1-1 configuration.</span></span> <span data-ttu-id="8094b-134">如果已启用 CAC，并且路由紧急呼叫的链接上的流量超过配置的限制，那么将阻止紧急呼叫或将其路由至本地 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="8094b-134">Emergency calls will be blocked or routed to the local PSTN gateway if a CAC is enabled and the configured limit is exceeded on a link where emergency calls are being routed.</span></span> <span data-ttu-id="8094b-135">如本主题前面所述，此类呼叫不包含位置数据，必须手动将其路由到 ECRC。</span><span class="sxs-lookup"><span data-stu-id="8094b-135">As indicated earlier in this topic, such calls will not have location data and must be manually routed to the ECRC.</span></span>
    

