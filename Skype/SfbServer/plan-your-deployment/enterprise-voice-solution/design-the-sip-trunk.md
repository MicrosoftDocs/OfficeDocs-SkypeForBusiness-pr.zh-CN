---
title: 在 Skype for Business Server 中为 E9-1-1 设计 SIP 中继
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
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4f93b974-b460-45c7-a4a8-6f38e34840f5
description: 在 Skype for Business Server 企业语音 中为使用 SIP 中继提供程序的 E9-1-1 部署规划 SIP 中继企业语音。
ms.openlocfilehash: ef30d721b59f29885004ee948055a91ca8af9490
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825792"
---
# <a name="design-the-sip-trunk-for-e9-1-1-in-skype-for-business-server"></a><span data-ttu-id="33c39-103">在 Skype for Business Server 中为 E9-1-1 设计 SIP 中继</span><span class="sxs-lookup"><span data-stu-id="33c39-103">Design the SIP trunk for E9-1-1 in Skype for Business Server</span></span>
 
<span data-ttu-id="33c39-104">在 Skype for Business Server 企业语音 中为使用 SIP 中继提供程序的 E9-1-1 部署规划 SIP 中继企业语音。</span><span class="sxs-lookup"><span data-stu-id="33c39-104">Planning your SIP trunking topologies for an E9-1-1 deployment that uses SIP trunking providers, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="33c39-105">Skype for Business Server 使用 SIP 中继将紧急呼叫连接到 E9-1-1 服务提供商。</span><span class="sxs-lookup"><span data-stu-id="33c39-105">Skype for Business Server uses SIP trunks to connect an emergency call to the E9-1-1 service provider.</span></span> <span data-ttu-id="33c39-106">您可以为一个中央站点、多个中央站点或每个分支站点的 E9-1-1 设置紧急服务 SIP 中继。</span><span class="sxs-lookup"><span data-stu-id="33c39-106">You can set up emergency service SIP trunks for E9-1-1 at one central site, at multiple central sites, or at each branch site.</span></span> <span data-ttu-id="33c39-107">但是，如果呼叫者的站点与承载紧急服务 SIP 中继的站点之间的 WAN 链路不可用，则断开连接的站点中的用户所拨打的呼叫将需要用户的语音策略中的特殊电话用法记录，该呼叫通过本地公用电话交换网 (PSTN) 网关将呼叫路由到 ECRC。</span><span class="sxs-lookup"><span data-stu-id="33c39-107">However, if the WAN link between the caller's site and the site that hosts the emergency service SIP trunk is unavailable, then a call placed by a user at the disconnected site will need a special phone usage record in the user's voice policy that will route the call to the ECRC through the local public switched telephone network (PSTN) gateway.</span></span> <span data-ttu-id="33c39-108">如果呼叫允许控制并发呼叫限制有效，则会出现相同情况。</span><span class="sxs-lookup"><span data-stu-id="33c39-108">The same is true if call admission control concurrent call limits are in effect.</span></span>
  
<span data-ttu-id="33c39-109">在 Skype for Business Server 环境中实现 SIP 中继的方法有两种：</span><span class="sxs-lookup"><span data-stu-id="33c39-109">There are two ways to implement a SIP trunk in a Skype for Business Server environment:</span></span>
  
- <span data-ttu-id="33c39-110">使用多主机中介服务器，这些服务器使用其面向外部的公共路由接口与 SIP 中继提供商进行通信。</span><span class="sxs-lookup"><span data-stu-id="33c39-110">Use multihomed Mediation Servers that use their outward-facing publicly-routed interfaces to communicate with the SIP trunk provider.</span></span>
    
- <span data-ttu-id="33c39-111">使用 SBC (本地会话边界控制器) 中介服务器和 SIP 中继提供商的服务之间提供安全的接入点。</span><span class="sxs-lookup"><span data-stu-id="33c39-111">Use an on-premises Session Border Controller (SBC) to provide a secure demarcation point between the Mediation Servers and the SIP trunk provider's services.</span></span>
    
<span data-ttu-id="33c39-112">如果您选择后一种方法，请确保您选择的 SBC 品牌和型号已经过认证并且支持将状态信息数据格式位置对象 (PIDF-LO) 位置数据作为其 SIP INVITE 一部分传递。</span><span class="sxs-lookup"><span data-stu-id="33c39-112">If you choose the latter method, be sure that the SBC make and model that you choose has been certified and supports passing Presence Information Data Format Location Object (PIDF-LO) location data as part of its SIP INVITE.</span></span> <span data-ttu-id="33c39-113">否则，呼叫将在缺少位置信息的情况下到达紧急服务的服务提供商。</span><span class="sxs-lookup"><span data-stu-id="33c39-113">Otherwise, the calls will arrive at the emergency services service provider stripped of their location information.</span></span> <span data-ttu-id="33c39-114">有关认证的 SDC 的详细信息，请参阅["Infrastructure Qualified for Microsoft Lync"](https://go.microsoft.com/fwlink/p/?LinkId=248425)和["Telephony Infrastructure for Skype for Business"。](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways)</span><span class="sxs-lookup"><span data-stu-id="33c39-114">For details about certified SBCs, see   ["Infrastructure Qualified for Microsoft Lync"](https://go.microsoft.com/fwlink/p/?LinkId=248425) and ["Telephony Infrastructure for Skype for Business"](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways).</span></span> 
  
<span data-ttu-id="33c39-115">E9-1-1 的服务提供商会向您提供对 SBC 对的访问权，以实现冗余。</span><span class="sxs-lookup"><span data-stu-id="33c39-115">E9-1-1 service providers supply you with access to a pair of SBCs for redundancy.</span></span> <span data-ttu-id="33c39-116">您需要做出有关中介服务器拓扑和呼叫路由配置的几个决策。</span><span class="sxs-lookup"><span data-stu-id="33c39-116">You need to make several decisions regarding the Mediation Server topology and call routing configuration.</span></span> <span data-ttu-id="33c39-117">您是否平等看待两个 SBC 并对它们之间的呼叫使用循环路由，或者您是否以其中一个 SBC 为主，而另一个为辅？</span><span class="sxs-lookup"><span data-stu-id="33c39-117">Will you treat both SBCs as equal peers and use round-robin routing for calls between them, or will you designate one SBC as primary and the other as secondary?</span></span>
  
<span data-ttu-id="33c39-118">有关在 Skype for Business Server 中部署 SIP 中继的详细信息，请参阅 [Skype for Business Server 中的 SIP 中继](sip-trunking.md)。</span><span class="sxs-lookup"><span data-stu-id="33c39-118">For details about deploying a SIP trunk in Skype for Business Server, see [SIP trunking in Skype for Business Server](sip-trunking.md).</span></span> <span data-ttu-id="33c39-119">下列问题将帮助您确定如何部署 E9-1-1 的 SIP 中继。</span><span class="sxs-lookup"><span data-stu-id="33c39-119">The following questions will help you decide how to deploy the SIP trunks for E9-1-1.</span></span>
  
 <span data-ttu-id="33c39-120">**应该通过专门租用的 Internet 连接还是共享的 Internet 连接部署 SIP 中继？**</span><span class="sxs-lookup"><span data-stu-id="33c39-120">**Should you deploy the SIP trunk over a dedicated leased or a shared internet connection?**</span></span>
  
> <span data-ttu-id="33c39-p105">紧急呼叫必须始终保持连接状态，这一点很重要。专用线路将提供不会被网络中其他流量抢占的连接以及实现服务质量 (QoS) 的功能。请记住，如果通过公共 Internet 连接到紧急服务的服务提供商，并且需要确保紧急呼叫的保密性，则需要 IPSec 加密。</span><span class="sxs-lookup"><span data-stu-id="33c39-p105">It is important that emergency calls always connect. A dedicated line provides a connection that will not be preempted by other traffic on the network, and gives you the ability to implement Quality of Service (QoS). Remember that if you are connecting to emergency services service providers over the public Internet and you need to guarantee the confidentiality of emergency calls, IPSec encryption is required.</span></span> 
    
 <span data-ttu-id="33c39-124">**E9-1-1 部署是否设计用于容限？**</span><span class="sxs-lookup"><span data-stu-id="33c39-124">**Is your E9-1-1 deployment designed for disaster tolerance?**</span></span>
  
> <span data-ttu-id="33c39-125">由于这是紧急解决方案，因此复原很重要。</span><span class="sxs-lookup"><span data-stu-id="33c39-125">Because this is an emergency solution, resiliency is important.</span></span> <span data-ttu-id="33c39-126">在容容位置部署主中介服务器和辅助中介服务器和 SIP 中继。</span><span class="sxs-lookup"><span data-stu-id="33c39-126">Deploy your primary and secondary Mediation Servers and SIP trunks in disaster tolerant locations.</span></span> <span data-ttu-id="33c39-127">建议部署最靠近其支持的用户的主中介服务器，并通过位于不同地理位置的辅助中介服务器 (路由故障转移呼叫) 。</span><span class="sxs-lookup"><span data-stu-id="33c39-127">It is a good idea to deploy your primary Mediation Server closest to the users that it is supporting, and route failover calls through the secondary Mediation Server (located in a different geographic location).</span></span> 
    
 <span data-ttu-id="33c39-128">**是否应该为每个分支机构部署单独的 SIP 中继？**</span><span class="sxs-lookup"><span data-stu-id="33c39-128">**Should you deploy a separate SIP trunk for each branch office?**</span></span>
  
> <span data-ttu-id="33c39-129">Skype for Business Server 提供了几种用于处理分支机构中的语音恢复的策略，包括：拥有可恢复的数据网络、在每个分支部署 SIP 中继或在中断期间将呼叫推送到本地网关。</span><span class="sxs-lookup"><span data-stu-id="33c39-129">Skype for Business Server provides several strategies for handling voice resiliency in branch offices, including: having resilient data networks, deploying a SIP trunk at each branch, or pushing calls out to the local gateway during outages.</span></span> <span data-ttu-id="33c39-130">有关详细信息，请参阅 [Skype for Business Server 中的 SIP 中继](sip-trunking.md)。</span><span class="sxs-lookup"><span data-stu-id="33c39-130">For details, see [SIP trunking in Skype for Business Server](sip-trunking.md).</span></span>
    
 <span data-ttu-id="33c39-131">**是否已启用呼叫允许控制 (CAC)？**</span><span class="sxs-lookup"><span data-stu-id="33c39-131">**Is call admission control (CAC) enabled?**</span></span>
  
> <span data-ttu-id="33c39-132">Skype for Business Server 不会处理与普通呼叫任何不同的紧急呼叫。</span><span class="sxs-lookup"><span data-stu-id="33c39-132">Skype for Business Server does not handle emergency calls any differently than an ordinary call.</span></span> <span data-ttu-id="33c39-133">因此，带宽管理或呼叫允许控制 (CAC) 将对 E9-1-1 配置产生负面影响。</span><span class="sxs-lookup"><span data-stu-id="33c39-133">For this reason, bandwidth management, or call admission control (CAC), can have a negative impact on an E9-1-1 configuration.</span></span> <span data-ttu-id="33c39-134">如果已启用 CAC，并且路由紧急呼叫的链接上的流量超过配置的限制，那么将阻止紧急呼叫或将其路由至本地 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="33c39-134">Emergency calls will be blocked or routed to the local PSTN gateway if a CAC is enabled and the configured limit is exceeded on a link where emergency calls are being routed.</span></span> <span data-ttu-id="33c39-135">如本主题前面所述，此类呼叫不包含位置数据，必须手动将其路由到 ECRC。</span><span class="sxs-lookup"><span data-stu-id="33c39-135">As indicated earlier in this topic, such calls will not have location data and must be manually routed to the ECRC.</span></span>
    

