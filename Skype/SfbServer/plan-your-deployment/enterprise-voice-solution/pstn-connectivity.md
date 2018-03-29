---
title: Skype for Business Server 2015 中的 PSTN 连接组件
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 6b2a3f7d-760f-4f09-8432-312c98a7e6b7
description: 学习关于 SIP 中继和 PSTN 网关企业语音在 Skype 业务服务器。
ms.openlocfilehash: 051066643649f9f8f872f4a2795e5ea71417d810
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="pstn-connectivity-components-in-skype-for-business-server-2015"></a><span data-ttu-id="fdbcf-103">Skype for Business Server 2015 中的 PSTN 连接组件</span><span class="sxs-lookup"><span data-stu-id="fdbcf-103">PSTN connectivity components in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="fdbcf-104">学习关于 SIP 中继和 PSTN 网关企业语音在 Skype 业务服务器。</span><span class="sxs-lookup"><span data-stu-id="fdbcf-104">Learn about SIP trunking and PSTN gateways for Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="fdbcf-105">企业级 VoIP 解决方案必须以始终如一的服务质量 (QoS) 提供来往于公用电话交换网 (PSTN) 的呼叫。</span><span class="sxs-lookup"><span data-stu-id="fdbcf-105">An enterprise-grade VoIP solution must provide for calls to and from the public switched telephone network (PSTN) without any decline in Quality of Service (QoS).</span></span> <span data-ttu-id="fdbcf-106">此外，用户在发起和接收呼叫时应不必了解底层技术。</span><span class="sxs-lookup"><span data-stu-id="fdbcf-106">In addition, users should not be aware of the underlying technology when they place and receive calls.</span></span> <span data-ttu-id="fdbcf-107">从用户的角度来看，企业语音基础结构之间的 PSTN 电话应该看起来像只是另一个 SIP 会话。</span><span class="sxs-lookup"><span data-stu-id="fdbcf-107">From the user's perspective, a call between the Enterprise Voice infrastructure and the PSTN should seem like just another SIP session.</span></span>
  
<span data-ttu-id="fdbcf-108">对于 PSTN 连接，既可以部署 SIP 中继，也可以部署 PSTN 网关（使用 PBX，也称为直接 SIP 链接；或不使用 PBX）。</span><span class="sxs-lookup"><span data-stu-id="fdbcf-108">For PSTN connections, you can either deploy a SIP trunk or a PSTN gateway (with a PBX, also known as a Direct SIP link, or without a PBX).</span></span>
  
## <a name="sip-trunking"></a><span data-ttu-id="fdbcf-109">SIP 中继</span><span class="sxs-lookup"><span data-stu-id="fdbcf-109">SIP Trunking</span></span>

<span data-ttu-id="fdbcf-110">除了使用 PSTN 网关，可以企业语音解决方案连接到 PSTN 使用 SIP 中继。</span><span class="sxs-lookup"><span data-stu-id="fdbcf-110">As an alternative to using PSTN gateways, you can connect your Enterprise Voice solution to the PSTN by using SIP trunking.</span></span> <span data-ttu-id="fdbcf-111">SIP 中继可以实现以下方案：</span><span class="sxs-lookup"><span data-stu-id="fdbcf-111">SIP trunking enables the following scenarios:</span></span>
  
- <span data-ttu-id="fdbcf-112">企业防火墙内外的企业用户可以拨打由符合 E.164 标准的号码指定的本地或长途电话，该电话将作为相应服务提供商的一项服务终止于 PSTN 上。</span><span class="sxs-lookup"><span data-stu-id="fdbcf-112">An enterprise user inside or outside the corporate firewall can make a local or long-distance call specified by an E.164-compliant number that is terminated on the PSTN as a service of the corresponding service provider.</span></span>
    
- <span data-ttu-id="fdbcf-113">通过拨打与企业防火墙内外的企业用户关联的外线直拨分机 (DID) 号码，任何 PSTN 订阅者都可以与该企业用户取得联系。</span><span class="sxs-lookup"><span data-stu-id="fdbcf-113">Any PSTN subscriber can contact an enterprise user inside or outside the corporate firewall by dialing a Direct Inward Dialing (DID) number associated with that enterprise user.</span></span>
    
<span data-ttu-id="fdbcf-114">使用此部署解决方案需要 SIP 中继服务提供商。</span><span class="sxs-lookup"><span data-stu-id="fdbcf-114">The use of this deployment solution requires a SIP trunking service provider.</span></span> 
  
## <a name="pstn-gateways"></a><span data-ttu-id="fdbcf-115">PSTN 网关</span><span class="sxs-lookup"><span data-stu-id="fdbcf-115">PSTN gateways</span></span>

<span data-ttu-id="fdbcf-116">PSTN 网关是转换信号的第三方设备和企业语音基础结构和 PSTN 或 PBX 之间的媒体。</span><span class="sxs-lookup"><span data-stu-id="fdbcf-116">PSTN gateways are third-party devices that translate signaling and media between the Enterprise Voice infrastructure and a PSTN or a PBX.</span></span> <span data-ttu-id="fdbcf-117">PSTN 网关使用中介服务器提供 PSTN 或 PBX 的企业语音客户端调用。</span><span class="sxs-lookup"><span data-stu-id="fdbcf-117">PSTN gateways work with the Mediation Server to present a PSTN or PBX call to an Enterprise Voice client.</span></span> <span data-ttu-id="fdbcf-118">中介服务器还提供了从企业语音客户端路由到 PSTN 或 PBX 的 PSTN 网关对的调用。</span><span class="sxs-lookup"><span data-stu-id="fdbcf-118">The Mediation Server also presents calls from Enterprise Voice clients to the PSTN gateway for routing to the PSTN or PBX.</span></span> <span data-ttu-id="fdbcf-119">使用 Microsoft 提供设备使用 Skype 业务服务器的合作伙伴的列表，请参阅[Microsoft 统一通信合作伙伴网站](https://go.microsoft.com/fwlink/p/?linkId=202836)。</span><span class="sxs-lookup"><span data-stu-id="fdbcf-119">For a list of partners who work with Microsoft to provide devices that work with Skype for Business Server, see  [the Microsoft Unified Communications Partners website](https://go.microsoft.com/fwlink/p/?linkId=202836).</span></span> 
  
## <a name="private-branch-exchanges"></a><span data-ttu-id="fdbcf-120">专用交换机</span><span class="sxs-lookup"><span data-stu-id="fdbcf-120">Private Branch Exchanges</span></span>

 <span data-ttu-id="fdbcf-121">如果您有现有的语音基础架构使用专用分组交换机 (PBX)，可以使用企业语音与您 PBX。</span><span class="sxs-lookup"><span data-stu-id="fdbcf-121">If you have an existing voice infrastructure that uses a private branch exchange (PBX), you can use your PBX with Enterprise Voice.</span></span>
  
<span data-ttu-id="fdbcf-122">支持的企业语音 PBX 集成方案如下所示：</span><span class="sxs-lookup"><span data-stu-id="fdbcf-122">The supported Enterprise Voice-PBX integration scenarios are as follows:</span></span>
  
- <span data-ttu-id="fdbcf-123">与中介服务器的支持介质的 IP PBX 绕过。</span><span class="sxs-lookup"><span data-stu-id="fdbcf-123">IP-PBX that supports media bypass, with a Mediation Server.</span></span>
    
- <span data-ttu-id="fdbcf-124">要求使用单独的 PSTN 网关的 IP-PBX。</span><span class="sxs-lookup"><span data-stu-id="fdbcf-124">IP-PBX that requires a stand-alone PSTN gateway.</span></span>
    
- <span data-ttu-id="fdbcf-125">时分多路复用 (TDM) PBX，使用单独的 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="fdbcf-125">Time division multiplexing (TDM) PBX, with a stand-alone PSTN gateway.</span></span>
    
> [!NOTE]
> <span data-ttu-id="fdbcf-126">媒体旁路将不会与每个 PSTN 网关、IP-PBX 和 SBC 进行交互操作。</span><span class="sxs-lookup"><span data-stu-id="fdbcf-126">Media bypass will not interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="fdbcf-127">Microsoft 与认证合作伙伴一起对一组 PSTN 网关和 SBC 进行了测试，另外也对 Cisco IP-PBX 进行了一些测试。</span><span class="sxs-lookup"><span data-stu-id="fdbcf-127">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="fdbcf-128">绕过媒体仅支持产品和版本中列出[统一通信开放互操作性计划-Lync Server](https://go.microsoft.com/fwlink/p/?linkId=214406)。</span><span class="sxs-lookup"><span data-stu-id="fdbcf-128">Media bypass is supported only with products and versions listed at [Unified Communications Open Interoperability Program - Lync Server](https://go.microsoft.com/fwlink/p/?linkId=214406).</span></span> 
  
<span data-ttu-id="fdbcf-129">合作伙伴提供的企业语音解决方案的详细信息，请参阅[Microsoft 统一通信合作伙伴网站](https://go.microsoft.com/fwlink/p/?linkId=202836)。</span><span class="sxs-lookup"><span data-stu-id="fdbcf-129">For details about partners who offer Enterprise Voice solutions, see the [Microsoft Unified Communications Partners website](https://go.microsoft.com/fwlink/p/?linkId=202836).</span></span>
  
<span data-ttu-id="fdbcf-130">有关合作伙伴提供企业语音的硬件解决方案，包括 PSTN 网关人员的详细信息，请参阅[Microsoft 统一通信合作伙伴网站](https://go.microsoft.com/fwlink/p/?linkId=202836)。</span><span class="sxs-lookup"><span data-stu-id="fdbcf-130">For details about partners who offer Enterprise Voice hardware solutions, including PSTN gateways, see the [Microsoft Unified Communications Partners website](https://go.microsoft.com/fwlink/p/?linkId=202836).</span></span>
  

