---
title: Lync Server 2013：配置媒体旁路
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure media bypass
ms:assetid: f50a7a13-c6a0-48f1-bee1-e45fa2b2f9b8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413028(v=OCS.15)
ms:contentKeyID: 48185836
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9bf2fb06f25ccf1871393cf4d80ffa3c33a42fc5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038274"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-media-bypass-in-lync-server-2013"></a><span data-ttu-id="87e14-102">在 Lync Server 2013 中配置媒体旁路</span><span class="sxs-lookup"><span data-stu-id="87e14-102">Configure media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="87e14-103">_**上次修改的主题：** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="87e14-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="87e14-104">本节假定您已发布并配置至少一个或多个中介服务器（如在[Lync server 2013 的拓扑生成器中定义中介服务器](lync-server-2013-define-a-mediation-server-in-topology-builder.md)和在[lync Server 2013 中发布拓扑](lync-server-2013-publish-the-topology.md)，或在 Lync server 2013 中[定义和配置前端池或 Standard Edition 2013 服务器](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md)）中，以及在部署文档中分别[发布拓扑中](lync-server-2013-publish-the-topology.md)所述。</span><span class="sxs-lookup"><span data-stu-id="87e14-104">This section assumes that you have already published and configured either at least one or more Mediation Servers (as described in [Define a Mediation Server in Topology Builder in Lync Server 2013](lync-server-2013-define-a-mediation-server-in-topology-builder.md) and [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md), or in [Define and configure a Front End pool or Standard Edition server in Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) and [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md), respectively, all in the Deployment documentation).</span></span>

<span data-ttu-id="87e14-105">此部分还假定您已定义至少一个网关对等方来提供 PSTN 连接，如在[Lync Server 2013 中的拓扑生成器中定义网关](lync-server-2013-define-a-gateway-in-topology-builder.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="87e14-105">This section also assumes that you have defined at least one gateway peer to provide PSTN connectivity, as described in [Define a gateway in Topology Builder in Lync Server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md).</span></span> <span data-ttu-id="87e14-106">如果您连接到的对等是 SIP 中继提供商的 SBC，请确保该提供程序是一个合格的提供程序，并且该提供程序支持媒体旁路。</span><span class="sxs-lookup"><span data-stu-id="87e14-106">If the peer you connect to is the SBC of a SIP trunking provider, make sure that the provider is a qualified provider and that the provider supports media bypass.</span></span> <span data-ttu-id="87e14-107">例如，很多 SIP 中继提供商仅允许其 SBC 接收来自中介服务器的流量。</span><span class="sxs-lookup"><span data-stu-id="87e14-107">For example, many SIP trunking providers will only allow their SBC to receive traffic from the Mediation Server.</span></span> <span data-ttu-id="87e14-108">如果这样，则不得为出现故障的中继启用绕过。</span><span class="sxs-lookup"><span data-stu-id="87e14-108">If so, then bypass must not be enabled for the trunk in question.</span></span> <span data-ttu-id="87e14-109">同时，只有您的组织向 SIP 中继提供商显示其内部网络 IP 地址后，您才能启用媒体绕过。</span><span class="sxs-lookup"><span data-stu-id="87e14-109">Also, you cannot enable media bypass unless your organization reveals its internal network IP addresses to the SIP trunking provider.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="87e14-110">媒体绕过将不会与每个 PSTN 网关、IP-PBX 和 SBC 进行交互操作。</span><span class="sxs-lookup"><span data-stu-id="87e14-110">Media bypass will not interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="87e14-111">Microsoft 已使用认证的合作伙伴测试了一组 PSTN 网关和 SBCs，并且已通过 Cisco IP Pbx 进行了一些测试。</span><span class="sxs-lookup"><span data-stu-id="87e14-111">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="87e14-112">仅在统一通信开放互操作性计划– Lync Server 上列出的产品和版本支持媒体<A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>旁路。</span><span class="sxs-lookup"><span data-stu-id="87e14-112">Media bypass is supported only with products and versions listed on Unified Communications Open Interoperability Program – Lync Server at <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>.</span></span>



</div>

<span data-ttu-id="87e14-113">本节介绍如何启用媒体绕过，以减少中介服务器所需的处理。</span><span class="sxs-lookup"><span data-stu-id="87e14-113">This section describes how to enable media bypass to reduce the processing required of the Mediation Server.</span></span> <span data-ttu-id="87e14-114">在启用媒体旁路之前，请确保您的环境满足支持媒体旁路所需的条件，如规划文档中的 "在[Lync Server 2013 中规划媒体旁路](lync-server-2013-planning-for-media-bypass.md)" 中所述。</span><span class="sxs-lookup"><span data-stu-id="87e14-114">Before you enable media bypass, make sure that your environment meets the conditions required to support media bypass, as described in [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) in the Planning documentation.</span></span> <span data-ttu-id="87e14-115">此外，请确保使用在[Lync Server 2013 中规划媒体旁路](lync-server-2013-planning-for-media-bypass.md)中的信息，以决定是否启用媒体旁路全局设置以始终绕过中介服务器，或在确定是否绕过中介服务器时使用站点和区域信息。</span><span class="sxs-lookup"><span data-stu-id="87e14-115">Also make sure that you used the information in [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) to decide whether to enable media bypass global settings to always bypass the Mediation Server or to use site and region information when determining whether to bypass the Mediation Server.</span></span>

<span data-ttu-id="87e14-p104">如果您已选择配置呼叫允许控制 (CAC)（企业语音的另一种高级功能），请注意，呼叫允许控制所执行的带宽保留不会应用于已应用媒体绕过的任何呼叫。首先验证是否应用了媒体绕过，如果已经应用，则不会对该呼叫使用呼叫允许控制；仅当媒体绕过检查失败时，才会检查呼叫允许控制。因此，对于路由至 PSTN 的任何特定呼叫，这两种功能是相互排斥的。这是符合逻辑的，因为媒体绕过假设呼叫中的媒体终结点间不存在带宽约束；无法在带宽受限的链接上执行媒体绕过。因此，会将以下情形之一应用于 PSTN 呼叫：a) 媒体绕过中介服务器，呼叫允许控制不为呼叫保留带宽；或者，b) 呼叫允许控制将带宽保留应用于呼叫，媒体由呼叫中涉及的中介服务器处理。</span><span class="sxs-lookup"><span data-stu-id="87e14-p104">If you have already optionally configured call admission control (CAC), another advanced Enterprise Voice feature, note that the bandwidth reservation performed by call admission control does not apply to any calls for which media bypass is employed. The verification of whether to employ media bypass is performed first, and if media bypass is employed, call admission control is not used for the call; only if the media bypass check fails is the check performed for call admission control. The two features are thus mutually exclusive for any particular call that is routed to the PSTN. This is the logic because media bypass assumes that bandwidth constraints do not exist between the media endpoints on a call; media bypass cannot be performed on links with restricted bandwidth. As a result, one of the following will apply to a PSTN call: a) media bypasses the Mediation Server, and call admission control does not reserve bandwidth for the call; or b) call admission control applies bandwidth reservation to the call, and media is processed by the Mediation Server involved in the call.</span></span>

<div>

## <a name="next-steps-enable-media-bypass-on-the-trunk-connection"></a><span data-ttu-id="87e14-121">后续步骤：在中继连接上启用媒体绕过</span><span class="sxs-lookup"><span data-stu-id="87e14-121">Next Steps: Enable Media Bypass on the Trunk Connection</span></span>

<span data-ttu-id="87e14-122">为 PSTN 连接（拨号计划、语音策略、PSTN 使用记录、出站呼叫路由和转换规则）配置初始设置后，通过使用在[Lync Server 2013 中配置具有媒体旁路的中继](lync-server-2013-configure-a-trunk-with-media-bypass.md)中的步骤开始启用媒体旁路的过程。</span><span class="sxs-lookup"><span data-stu-id="87e14-122">After configuring initial settings for PSTN connectivity (dial plans, voice policies, PSTN usage records, outbound call routes, and translation rules), begin the process of enabling media bypass by using the steps in [Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="87e14-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="87e14-123">See Also</span></span>


[<span data-ttu-id="87e14-124">在 Lync Server 2013 中配置具有媒体旁路功能的中继</span><span class="sxs-lookup"><span data-stu-id="87e14-124">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[<span data-ttu-id="87e14-125">在 Lync Server 2013 中配置媒体旁路以始终绕过中介服务器</span><span class="sxs-lookup"><span data-stu-id="87e14-125">Configure media bypass in Lync Server 2013 to always bypass the Mediation Server</span></span>](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md)  
[<span data-ttu-id="87e14-126">在 Lync Server 2013 中配置媒体旁路全局设置以使用站点和区域信息</span><span class="sxs-lookup"><span data-stu-id="87e14-126">Configure media bypass global settings in Lync Server 2013 to use site and region information</span></span>](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md)  


[<span data-ttu-id="87e14-127">Lync Server 2013 中的全局媒体旁路选项</span><span class="sxs-lookup"><span data-stu-id="87e14-127">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  


[<span data-ttu-id="87e14-128">在 Lync Server 2013 中规划媒体旁路</span><span class="sxs-lookup"><span data-stu-id="87e14-128">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

