---
title: 在 Skype for Business Server 2015 中为 E9-1-1 设计 SIP 中继
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 4f93b974-b460-45c7-a4a8-6f38e34840f5
description: 规划中业务服务器企业语音的 Skype 使用 SIP 中继提供商、 E9-1-1 部署您的 SIP 中继拓扑。
ms.openlocfilehash: 588cd32d4c3c7f7aacc9a42d2a2ca8791d036dea
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="design-the-sip-trunk-for-e9-1-1-in-skype-for-business-server-2015"></a><span data-ttu-id="c66f9-103">在 Skype for Business Server 2015 中为 E9-1-1 设计 SIP 中继</span><span class="sxs-lookup"><span data-stu-id="c66f9-103">Design the SIP trunk for E9-1-1 in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="c66f9-104">规划中业务服务器企业语音的 Skype 使用 SIP 中继提供商、 E9-1-1 部署您的 SIP 中继拓扑。</span><span class="sxs-lookup"><span data-stu-id="c66f9-104">Planning your SIP trunking topologies for an E9-1-1 deployment that uses SIP trunking providers, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="c66f9-105">Skype 业务服务器使用 SIP 中继连接到 E9-1-1 的服务提供商紧急呼叫。</span><span class="sxs-lookup"><span data-stu-id="c66f9-105">Skype for Business Server uses SIP trunks to connect an emergency call to the E9-1-1 service provider.</span></span> <span data-ttu-id="c66f9-106">您可以为一个中央站点、多个中央站点或每个分支站点的 E9-1-1 设置紧急服务 SIP 中继。</span><span class="sxs-lookup"><span data-stu-id="c66f9-106">You can set up emergency service SIP trunks for E9-1-1 at one central site, at multiple central sites, or at each branch site.</span></span> <span data-ttu-id="c66f9-107">但是，如果调用方的网站与网站之间承载的 WAN 链路紧急服务 SIP 中继是不可用，则调用放在断开连接的站点的用户将需要特殊的电话使用情况记录用户的语音策略中将路由到该调用通过本地公用交换的电话网络 (PSTN) 网关 ECRC。</span><span class="sxs-lookup"><span data-stu-id="c66f9-107">However, if the WAN link between the caller's site and the site that hosts the emergency service SIP trunk is unavailable, then a call placed by a user at the disconnected site will need a special phone usage record in the user's voice policy that will route the call to the ECRC through the local public switched telephone network (PSTN) gateway.</span></span> <span data-ttu-id="c66f9-108">如果呼叫允许控制并发呼叫限制有效，则会出现相同情况。</span><span class="sxs-lookup"><span data-stu-id="c66f9-108">The same is true if call admission control concurrent call limits are in effect.</span></span>
  
<span data-ttu-id="c66f9-109">有两种方法可以在 Skype 业务服务器环境中实现 SIP 中继：</span><span class="sxs-lookup"><span data-stu-id="c66f9-109">There are two ways to implement a SIP trunk in a Skype for Business Server environment:</span></span>
  
- <span data-ttu-id="c66f9-110">使用多宿主使用公开传送其面向外部的接口与通信的 SIP 中继提供的中介服务器。</span><span class="sxs-lookup"><span data-stu-id="c66f9-110">Use multihomed Mediation Servers that use their outward-facing publicly-routed interfaces to communicate with the SIP trunk provider.</span></span>
    
- <span data-ttu-id="c66f9-111">使用内部会话边框控制器 (SBC) 提供商服务的中介服务器和 SIP 中继之间安全的分界点。</span><span class="sxs-lookup"><span data-stu-id="c66f9-111">Use an on-premises Session Border Controller (SBC) to provide a secure demarcation point between the Mediation Servers and the SIP trunk provider's services.</span></span>
    
<span data-ttu-id="c66f9-112">如果您选择后一种方法，请确保您选择的 SBC 品牌和型号已经过认证并且支持将状态信息数据格式位置对象 (PIDF-LO) 位置数据作为其 SIP INVITE 一部分传递。</span><span class="sxs-lookup"><span data-stu-id="c66f9-112">If you choose the latter method, be sure that the SBC make and model that you choose has been certified and supports passing Presence Information Data Format Location Object (PIDF-LO) location data as part of its SIP INVITE.</span></span> <span data-ttu-id="c66f9-113">否则，呼叫将在缺少位置信息的情况下到达紧急服务的服务提供商。</span><span class="sxs-lookup"><span data-stu-id="c66f9-113">Otherwise, the calls will arrive at the emergency services service provider stripped of their location information.</span></span> <span data-ttu-id="c66f9-114">经认证的 SBCs 有关详细信息，请参阅["基础架构限定为 Microsoft Lync"](https://go.microsoft.com/fwlink/p/?LinkId=248425)和["电话基础架构的 Skype 的业务"](https://technet.microsoft.com/en-us/office/dn947483)。</span><span class="sxs-lookup"><span data-stu-id="c66f9-114">For details about certified SBCs, see   ["Infrastructure Qualified for Microsoft Lync"](https://go.microsoft.com/fwlink/p/?LinkId=248425) and ["Telephony Infrastructure for Skype for Business"](https://technet.microsoft.com/en-us/office/dn947483).</span></span>
  
<span data-ttu-id="c66f9-115">E9-1-1 的服务提供商会向您提供对 SBC 对的访问权，以实现冗余。</span><span class="sxs-lookup"><span data-stu-id="c66f9-115">E9-1-1 service providers supply you with access to a pair of SBCs for redundancy.</span></span> <span data-ttu-id="c66f9-116">您需要做出几个有关中介服务器拓扑结构和调用路由配置。</span><span class="sxs-lookup"><span data-stu-id="c66f9-116">You need to make several decisions regarding the Mediation Server topology and call routing configuration.</span></span> <span data-ttu-id="c66f9-117">您是否平等看待两个 SBC 并对它们之间的呼叫使用循环路由，或者您是否以其中一个 SBC 为主，而另一个为辅？</span><span class="sxs-lookup"><span data-stu-id="c66f9-117">Will you treat both SBCs as equal peers and use round-robin routing for calls between them, or will you designate one SBC as primary and the other as secondary?</span></span>
  
<span data-ttu-id="c66f9-118">有关部署 Skype 在 SIP 中继业务服务器的详细信息，请参阅[SIP 中继业务服务器 2015年的 Skype 中](sip-trunking.md)。</span><span class="sxs-lookup"><span data-stu-id="c66f9-118">For details about deploying a SIP trunk in Skype for Business Server, see [SIP trunking in Skype for Business Server 2015](sip-trunking.md).</span></span> <span data-ttu-id="c66f9-119">下列问题将帮助您确定如何部署 E9-1-1 的 SIP 中继。</span><span class="sxs-lookup"><span data-stu-id="c66f9-119">The following questions will help you decide how to deploy the SIP trunks for E9-1-1.</span></span>
  
 <span data-ttu-id="c66f9-120">**应该通过专门租用的 Internet 连接还是共享的 Internet 连接部署 SIP 中继？**</span><span class="sxs-lookup"><span data-stu-id="c66f9-120">**Should you deploy the SIP trunk over a dedicated leased or a shared internet connection?**</span></span>
  
> <span data-ttu-id="c66f9-p105">紧急呼叫必须始终保持连接状态，这一点很重要。专用线路将提供不会被网络中其他流量抢占的连接以及实现服务质量 (QoS) 的功能。请记住，如果通过公共 Internet 连接到紧急服务的服务提供商，并且需要确保紧急呼叫的保密性，则需要 IPSec 加密。</span><span class="sxs-lookup"><span data-stu-id="c66f9-p105">It is important that emergency calls always connect. A dedicated line provides a connection that will not be preempted by other traffic on the network, and gives you the ability to implement Quality of Service (QoS). Remember that if you are connecting to emergency services service providers over the public Internet and you need to guarantee the confidentiality of emergency calls, IPSec encryption is required.</span></span> 
    
 <span data-ttu-id="c66f9-124">**E9-1-1 部署专为灾难容受能力？**</span><span class="sxs-lookup"><span data-stu-id="c66f9-124">**Is your E9-1-1 deployment designed for disaster tolerance?**</span></span>
  
> <span data-ttu-id="c66f9-125">由于这是紧急解决方案，因此复原很重要。</span><span class="sxs-lookup"><span data-stu-id="c66f9-125">Because this is an emergency solution, resiliency is important.</span></span> <span data-ttu-id="c66f9-126">部署您主要和次要中介服务器和 SIP 中继灾难容错位置中。</span><span class="sxs-lookup"><span data-stu-id="c66f9-126">Deploy your primary and secondary Mediation Servers and SIP trunks in disaster tolerant locations.</span></span> <span data-ttu-id="c66f9-127">最好将最接近用户的支持，主要中介服务器部署，通过辅助中介服务器 （位于不同的地理位置） 调用路由故障转移。</span><span class="sxs-lookup"><span data-stu-id="c66f9-127">It is a good idea to deploy your primary Mediation Server closest to the users that it is supporting, and route failover calls through the secondary Mediation Server (located in a different geographic location).</span></span> 
    
 <span data-ttu-id="c66f9-128">**是否应该为每个分支机构部署单独的 SIP 中继？**</span><span class="sxs-lookup"><span data-stu-id="c66f9-128">**Should you deploy a separate SIP trunk for each branch office?**</span></span>
  
> <span data-ttu-id="c66f9-129">Skype 业务服务器提供几种策略，用于处理语音留存能力在分支机构，其中包括： 具有弹性数据网络、 部署在每个分支中，SIP 中继或推出电话本地网关在停机期间。</span><span class="sxs-lookup"><span data-stu-id="c66f9-129">Skype for Business Server provides several strategies for handling voice resiliency in branch offices, including: having resilient data networks, deploying a SIP trunk at each branch, or pushing calls out to the local gateway during outages.</span></span> <span data-ttu-id="c66f9-130">有关详细信息，请参阅[SIP 中继业务服务器 2015年的 Skype 中](sip-trunking.md)。</span><span class="sxs-lookup"><span data-stu-id="c66f9-130">For details, see [SIP trunking in Skype for Business Server 2015](sip-trunking.md).</span></span>
    
 <span data-ttu-id="c66f9-131">**是否已启用呼叫允许控制 (CAC)？**</span><span class="sxs-lookup"><span data-stu-id="c66f9-131">**Is call admission control (CAC) enabled?**</span></span>
  
> <span data-ttu-id="c66f9-132">Skype 业务服务器处理紧急调用任何不同于普通的电话。</span><span class="sxs-lookup"><span data-stu-id="c66f9-132">Skype for Business Server does not handle emergency calls any differently than an ordinary call.</span></span> <span data-ttu-id="c66f9-133">因此，带宽管理或呼叫允许控制 (CAC) 将对 E9-1-1 配置产生负面影响。</span><span class="sxs-lookup"><span data-stu-id="c66f9-133">For this reason, bandwidth management, or call admission control (CAC), can have a negative impact on an E9-1-1 configuration.</span></span> <span data-ttu-id="c66f9-134">如果已启用 CAC，并且路由紧急呼叫的链接上的流量超过配置的限制，那么将阻止紧急呼叫或将其路由至本地 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="c66f9-134">Emergency calls will be blocked or routed to the local PSTN gateway if a CAC is enabled and the configured limit is exceeded on a link where emergency calls are being routed.</span></span> <span data-ttu-id="c66f9-135">如本主题前面所述，此类呼叫不包含位置数据，必须手动将其路由到 ECRC。</span><span class="sxs-lookup"><span data-stu-id="c66f9-135">As indicated earlier in this topic, such calls will not have location data and must be manually routed to the ECRC.</span></span>
    

