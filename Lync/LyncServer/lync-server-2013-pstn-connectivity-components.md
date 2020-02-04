---
title: Lync Server 2013： PSTN 连接组件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PSTN connectivity components
ms:assetid: 6b2a3f7d-760f-4f09-8432-312c98a7e6b7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398504(v=OCS.15)
ms:contentKeyID: 48184408
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 63b5534b817477ea42dbefd5244c974fc70881f9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724762"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pstn-connectivity-components-in-lync-server-2013"></a><span data-ttu-id="ee5e6-102">Lync Server 2013 中的 PSTN 连接组件</span><span class="sxs-lookup"><span data-stu-id="ee5e6-102">PSTN connectivity components in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ee5e6-103">_**主题上次修改时间：** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="ee5e6-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="ee5e6-104">企业级 VoIP 解决方案必须以始终如一的服务质量 (QoS) 提供来往于公用电话交换网 (PSTN) 的呼叫。</span><span class="sxs-lookup"><span data-stu-id="ee5e6-104">An enterprise-grade VoIP solution must provide for calls to and from the public switched telephone network (PSTN) without any decline in Quality of Service (QoS).</span></span> <span data-ttu-id="ee5e6-105">此外，用户在发起和接收呼叫时应不必了解底层技术。</span><span class="sxs-lookup"><span data-stu-id="ee5e6-105">In addition, users should not be aware of the underlying technology when they place and receive calls.</span></span> <span data-ttu-id="ee5e6-106">从用户的角度来看，企业语音基础结构与 PSTN 之间的通话似乎就像是另一个 SIP 会话。</span><span class="sxs-lookup"><span data-stu-id="ee5e6-106">From the user's perspective, a call between the Enterprise Voice infrastructure and the PSTN should seem like just another SIP session.</span></span>

<span data-ttu-id="ee5e6-107">对于 PSTN 连接，既可以部署 SIP 中继，也可以部署 PSTN 网关（使用 PBX，也称为直接 SIP 链接；或不使用 PBX）。</span><span class="sxs-lookup"><span data-stu-id="ee5e6-107">For PSTN connections, you can either deploy a SIP trunk or a PSTN gateway (with a PBX, also known as a Direct SIP link, or without a PBX).</span></span>

<div>

## <a name="sip-trunking"></a><span data-ttu-id="ee5e6-108">SIP 中继</span><span class="sxs-lookup"><span data-stu-id="ee5e6-108">SIP Trunking</span></span>

<span data-ttu-id="ee5e6-109">作为使用 PSTN 网关的替代方法，你可以使用 SIP 中继将企业语音解决方案连接到 PSTN。</span><span class="sxs-lookup"><span data-stu-id="ee5e6-109">As an alternative to using PSTN gateways, you can connect your Enterprise Voice solution to the PSTN by using SIP trunking.</span></span> <span data-ttu-id="ee5e6-110">SIP 中继可以实现以下方案：</span><span class="sxs-lookup"><span data-stu-id="ee5e6-110">SIP trunking enables the following scenarios:</span></span>

  - <span data-ttu-id="ee5e6-111">企业防火墙内外的企业用户可以拨打由符合 E.164 标准的号码指定的本地或长途电话，该电话将作为相应服务提供商的一项服务终止于 PSTN 上。</span><span class="sxs-lookup"><span data-stu-id="ee5e6-111">An enterprise user inside or outside the corporate firewall can make a local or long-distance call specified by an E.164-compliant number that is terminated on the PSTN as a service of the corresponding service provider.</span></span>

  - <span data-ttu-id="ee5e6-112">通过拨打与企业防火墙内外的企业用户关联的外线直拨分机 (DID) 号码，任何 PSTN 订阅者都可以与该企业用户取得联系。</span><span class="sxs-lookup"><span data-stu-id="ee5e6-112">Any PSTN subscriber can contact an enterprise user inside or outside the corporate firewall by dialing a Direct Inward Dialing (DID) number associated with that enterprise user.</span></span>

<span data-ttu-id="ee5e6-113">使用此部署解决方案需要 SIP 中继服务提供商。</span><span class="sxs-lookup"><span data-stu-id="ee5e6-113">The use of this deployment solution requires a SIP trunking service provider.</span></span>

</div>

<div>

## <a name="pstn-gateways"></a><span data-ttu-id="ee5e6-114">PSTN 网关</span><span class="sxs-lookup"><span data-stu-id="ee5e6-114">PSTN gateways</span></span>

<span data-ttu-id="ee5e6-115">PSTN 网关是在企业语音基础结构和 PSTN 或 PBX 之间转换信号和媒体的第三方设备。</span><span class="sxs-lookup"><span data-stu-id="ee5e6-115">PSTN gateways are third-party devices that translate signaling and media between the Enterprise Voice infrastructure and a PSTN or a PBX.</span></span> <span data-ttu-id="ee5e6-116">PSTN 网关与中介服务器配合使用，向企业语音客户端提供 PSTN 或 PBX 呼叫。</span><span class="sxs-lookup"><span data-stu-id="ee5e6-116">PSTN gateways work with the Mediation Server to present a PSTN or PBX call to an Enterprise Voice client.</span></span> <span data-ttu-id="ee5e6-117">中介服务器还将来自企业语音客户端的呼叫提供给 PSTN 网关，以便路由到 PSTN 或 PBX。</span><span class="sxs-lookup"><span data-stu-id="ee5e6-117">The Mediation Server also presents calls from Enterprise Voice clients to the PSTN gateway for routing to the PSTN or PBX.</span></span> <span data-ttu-id="ee5e6-118">有关与 Microsoft 配合使用以提供与 Lync Server 配合使用的设备的合作伙伴的列表，请参阅 Microsoft 统一通信合作伙伴网站[http://go.microsoft.com/fwlink/p/?linkId=202836](http://go.microsoft.com/fwlink/p/?linkid=202836)。</span><span class="sxs-lookup"><span data-stu-id="ee5e6-118">For a list of partners who work with Microsoft to provide devices that work with Lync Server, see the Microsoft Unified Communications Partners website at [http://go.microsoft.com/fwlink/p/?linkId=202836](http://go.microsoft.com/fwlink/p/?linkid=202836).</span></span>

</div>

<div>

## <a name="private-branch-exchanges"></a><span data-ttu-id="ee5e6-119">专用交换机</span><span class="sxs-lookup"><span data-stu-id="ee5e6-119">Private Branch Exchanges</span></span>

<span data-ttu-id="ee5e6-120">如果您有一个使用专用分支交换（PBX）的语音基础结构，则可以将 PBX 与 Lync Server 企业语音配合使用。</span><span class="sxs-lookup"><span data-stu-id="ee5e6-120">If you have an existing voice infrastructure that uses a private branch exchange (PBX), you can use your PBX with Lync Server Enterprise Voice.</span></span>

<span data-ttu-id="ee5e6-121">支持的企业语音 PBX 集成方案如下所示：</span><span class="sxs-lookup"><span data-stu-id="ee5e6-121">The supported Enterprise Voice-PBX integration scenarios are as follows:</span></span>

  - <span data-ttu-id="ee5e6-122">使用中介服务器支持媒体旁路的 IP PBX。</span><span class="sxs-lookup"><span data-stu-id="ee5e6-122">IP-PBX that supports media bypass, with a Mediation Server.</span></span>

  - <span data-ttu-id="ee5e6-123">要求使用单独的 PSTN 网关的 IP-PBX。</span><span class="sxs-lookup"><span data-stu-id="ee5e6-123">IP-PBX that requires a stand-alone PSTN gateway.</span></span>

  - <span data-ttu-id="ee5e6-124">时分多路复用 (TDM) PBX，使用单独的 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="ee5e6-124">Time division multiplexing (TDM) PBX, with a stand-alone PSTN gateway.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ee5e6-125">媒体旁路将不会与每个 PSTN 网关、IP-PBX 和 SBC 进行交互操作。</span><span class="sxs-lookup"><span data-stu-id="ee5e6-125">Media bypass will not interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="ee5e6-126">Microsoft 与认证合作伙伴一起对一组 PSTN 网关和 SBC 进行了测试，另外也对 Cisco IP-PBX 进行了一些测试。</span><span class="sxs-lookup"><span data-stu-id="ee5e6-126">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="ee5e6-127">只有在统一通信中列出的产品和版本才支持媒体绕开互操作性计划- <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>Lync Server at。</span><span class="sxs-lookup"><span data-stu-id="ee5e6-127">Media bypass is supported only with products and versions listed on Unified Communications Open Interoperability Program – Lync Server at <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>.</span></span>



</div>

<span data-ttu-id="ee5e6-128">有关提供企业语音解决方案的合作伙伴的详细信息，请参阅 Microsoft 统一通信合作伙伴网站[http://go.microsoft.com/fwlink/p/?linkId=202836](http://go.microsoft.com/fwlink/p/?linkid=202836)。</span><span class="sxs-lookup"><span data-stu-id="ee5e6-128">For details about partners who offer Enterprise Voice solutions, see the Microsoft Unified Communications Partners website at [http://go.microsoft.com/fwlink/p/?linkId=202836](http://go.microsoft.com/fwlink/p/?linkid=202836).</span></span>

<span data-ttu-id="ee5e6-129">有关提供企业语音硬件解决方案（包括 PSTN 网关）的合作伙伴的详细信息，请参阅 Microsoft 统一[http://go.microsoft.com/fwlink/p/?linkId=202836](http://go.microsoft.com/fwlink/p/?linkid=202836)通信合作伙伴网站。</span><span class="sxs-lookup"><span data-stu-id="ee5e6-129">For details about partners who offer Enterprise Voice hardware solutions, including PSTN gateways, see the Microsoft Unified Communications Partners website [http://go.microsoft.com/fwlink/p/?linkId=202836](http://go.microsoft.com/fwlink/p/?linkid=202836).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

