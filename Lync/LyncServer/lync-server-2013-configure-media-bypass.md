---
title: Lync Server 2013：配置媒体绕过
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
ms.openlocfilehash: 8be022e5b1b16bff432873e27ddda5f388db02f1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758426"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-media-bypass-in-lync-server-2013"></a><span data-ttu-id="f7a9a-102">在 Lync Server 2013 中配置媒体绕过</span><span class="sxs-lookup"><span data-stu-id="f7a9a-102">Configure media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f7a9a-103">_**主题上次修改时间：** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="f7a9a-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="f7a9a-104">本部分假设你已经发布和配置了至少一个或多个中介服务器（如在[lync server 2013 的拓扑生成器中定义中介服务器](lync-server-2013-define-a-mediation-server-in-topology-builder.md)和在 lync server [2013 中发布拓扑](lync-server-2013-publish-the-topology.md)，或者在 Lync server [2013](lync-server-2013-publish-the-topology.md)中[定义和配置前端池或标准版2013服务器](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md)）中，分别在部署文档中使用。</span><span class="sxs-lookup"><span data-stu-id="f7a9a-104">This section assumes that you have already published and configured either at least one or more Mediation Servers (as described in [Define a Mediation Server in Topology Builder in Lync Server 2013](lync-server-2013-define-a-mediation-server-in-topology-builder.md) and [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md), or in [Define and configure a Front End pool or Standard Edition server in Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) and [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md), respectively, all in the Deployment documentation).</span></span>

<span data-ttu-id="f7a9a-105">此部分还假定你至少已定义一个网关对等，以便提供 PSTN 连接，如在[Lync Server 2013 的拓扑生成器中定义网关](lync-server-2013-define-a-gateway-in-topology-builder.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="f7a9a-105">This section also assumes that you have defined at least one gateway peer to provide PSTN connectivity, as described in [Define a gateway in Topology Builder in Lync Server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md).</span></span> <span data-ttu-id="f7a9a-106">如果您连接到的对等方是 SIP 中继提供商的 SBC，请确保该提供商是合格的提供商，且支持媒体旁路。</span><span class="sxs-lookup"><span data-stu-id="f7a9a-106">If the peer you connect to is the SBC of a SIP trunking provider, make sure that the provider is a qualified provider and that the provider supports media bypass.</span></span> <span data-ttu-id="f7a9a-107">例如，很多 SIP 中继提供商仅允许其 SBC 接收来自中介服务器的流量。</span><span class="sxs-lookup"><span data-stu-id="f7a9a-107">For example, many SIP trunking providers will only allow their SBC to receive traffic from the Mediation Server.</span></span> <span data-ttu-id="f7a9a-108">如果这样，则不得为出现故障的中继启用旁路。</span><span class="sxs-lookup"><span data-stu-id="f7a9a-108">If so, then bypass must not be enabled for the trunk in question.</span></span> <span data-ttu-id="f7a9a-109">同时，只有您的组织向 SIP 中继提供商显示其内部网络 IP 地址后，您才能启用媒体旁路。</span><span class="sxs-lookup"><span data-stu-id="f7a9a-109">Also, you cannot enable media bypass unless your organization reveals its internal network IP addresses to the SIP trunking provider.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f7a9a-110">媒体旁路将不会与每个 PSTN 网关、IP-PBX 和 SBC 进行交互操作。</span><span class="sxs-lookup"><span data-stu-id="f7a9a-110">Media bypass will not interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="f7a9a-111">Microsoft 与认证合作伙伴一起对一组 PSTN 网关和 SBC 进行了测试，另外也对 Cisco IP-PBX 进行了一些测试。</span><span class="sxs-lookup"><span data-stu-id="f7a9a-111">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="f7a9a-112">只有在统一通信中列出的产品和版本才支持媒体绕开互操作性计划- <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>Lync Server at。</span><span class="sxs-lookup"><span data-stu-id="f7a9a-112">Media bypass is supported only with products and versions listed on Unified Communications Open Interoperability Program – Lync Server at <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>.</span></span>



</div>

<span data-ttu-id="f7a9a-113">本部分介绍如何启用 "绕过媒体"，以减少中介服务器所需的处理。</span><span class="sxs-lookup"><span data-stu-id="f7a9a-113">This section describes how to enable media bypass to reduce the processing required of the Mediation Server.</span></span> <span data-ttu-id="f7a9a-114">启用 "绕过媒体" 之前，请确保你的环境满足支持媒体绕过所需的条件，如规划文档中的[Lync Server 2013 中的 "在媒体中跳过](lync-server-2013-planning-for-media-bypass.md)" 中所述。</span><span class="sxs-lookup"><span data-stu-id="f7a9a-114">Before you enable media bypass, make sure that your environment meets the conditions required to support media bypass, as described in [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) in the Planning documentation.</span></span> <span data-ttu-id="f7a9a-115">此外，请确保你使用了在[Lync server 2013 中规划媒体绕过](lync-server-2013-planning-for-media-bypass.md)的信息，以决定是否启用媒体绕过全局设置，以便在确定是否绕过中介服务器时始终绕过中介服务器或使用站点和区域信息。</span><span class="sxs-lookup"><span data-stu-id="f7a9a-115">Also make sure that you used the information in [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) to decide whether to enable media bypass global settings to always bypass the Mediation Server or to use site and region information when determining whether to bypass the Mediation Server.</span></span>

<span data-ttu-id="f7a9a-p104">如果您已选择配置呼叫允许控制 (CAC)（企业语音的另一种高级功能），请注意，呼叫允许控制所执行的带宽保留不会应用于已应用媒体旁路的任何呼叫。首先验证是否应用了媒体旁路，如果已经应用，则不会对该呼叫使用呼叫允许控制；仅当媒体旁路检查失败时，才会检查呼叫允许控制。因此，对于路由至 PSTN 的任何特定呼叫，这两种功能是相互排斥的。这是符合逻辑的，因为媒体旁路假设呼叫中的媒体终结点间不存在带宽约束；无法在带宽受限的链接上执行媒体旁路。因此，会将以下情形之一应用于 PSTN 呼叫：a) 媒体绕过中介服务器，呼叫允许控制不为呼叫保留带宽；或者，b) 呼叫允许控制将带宽保留应用于呼叫，媒体由呼叫中涉及的中介服务器处理。</span><span class="sxs-lookup"><span data-stu-id="f7a9a-p104">If you have already optionally configured call admission control (CAC), another advanced Enterprise Voice feature, note that the bandwidth reservation performed by call admission control does not apply to any calls for which media bypass is employed. The verification of whether to employ media bypass is performed first, and if media bypass is employed, call admission control is not used for the call; only if the media bypass check fails is the check performed for call admission control. The two features are thus mutually exclusive for any particular call that is routed to the PSTN. This is the logic because media bypass assumes that bandwidth constraints do not exist between the media endpoints on a call; media bypass cannot be performed on links with restricted bandwidth. As a result, one of the following will apply to a PSTN call: a) media bypasses the Mediation Server, and call admission control does not reserve bandwidth for the call; or b) call admission control applies bandwidth reservation to the call, and media is processed by the Mediation Server involved in the call.</span></span>

<div>

## <a name="next-steps-enable-media-bypass-on-the-trunk-connection"></a><span data-ttu-id="f7a9a-121">后续步骤：在中继连接上启用绕过媒体</span><span class="sxs-lookup"><span data-stu-id="f7a9a-121">Next Steps: Enable Media Bypass on the Trunk Connection</span></span>

<span data-ttu-id="f7a9a-122">为 PSTN 连接（拨号计划、语音策略、PSTN 使用记录、出站呼叫路由和翻译规则）配置初始设置后，通过使用在[Lync Server 2013 中使用 "媒体绕过" 配置主干](lync-server-2013-configure-a-trunk-with-media-bypass.md)中的步骤开始启用媒体绕过的过程。</span><span class="sxs-lookup"><span data-stu-id="f7a9a-122">After configuring initial settings for PSTN connectivity (dial plans, voice policies, PSTN usage records, outbound call routes, and translation rules), begin the process of enabling media bypass by using the steps in [Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f7a9a-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f7a9a-123">See Also</span></span>


[<span data-ttu-id="f7a9a-124">Configure a trunk with media bypass in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f7a9a-124">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[<span data-ttu-id="f7a9a-125">Configure media bypass in Lync Server 2013 to always bypass the Mediation Server</span><span class="sxs-lookup"><span data-stu-id="f7a9a-125">Configure media bypass in Lync Server 2013 to always bypass the Mediation Server</span></span>](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md)  
[<span data-ttu-id="f7a9a-126">Configure media bypass global settings in Lync Server 2013 to use site and region information</span><span class="sxs-lookup"><span data-stu-id="f7a9a-126">Configure media bypass global settings in Lync Server 2013 to use site and region information</span></span>](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md)  


[<span data-ttu-id="f7a9a-127">Lync Server 2013 中的全局媒体绕过选项</span><span class="sxs-lookup"><span data-stu-id="f7a9a-127">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  


[<span data-ttu-id="f7a9a-128">在 Lync Server 2013 中规划媒体旁路</span><span class="sxs-lookup"><span data-stu-id="f7a9a-128">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

