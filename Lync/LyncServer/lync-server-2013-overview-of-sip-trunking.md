---
title: Lync Server 2013： SIP 中继概述
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of SIP trunking
ms:assetid: 204f2c21-436f-4b2d-93ea-d6db98fa2952
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398285(v=OCS.15)
ms:contentKeyID: 48183601
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 81690d4f006b5c1df3ed001369cbe5c4b1f560b8
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520849"
---
# <a name="overview-of-sip-trunking-in-lync-server-2013"></a><span data-ttu-id="783e7-102">Lync Server 2013 中的 SIP 中继概述</span><span class="sxs-lookup"><span data-stu-id="783e7-102">Overview of SIP trunking in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="783e7-103">_**上次修改的主题：** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="783e7-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="783e7-p101">部署 SIP 中继对于简化组织的电信和准备实时通信的最新增强功能来说可能是重要的一步。SIP 中继的主要优点之一是可以在中央站点中合并组织的公用电话交换网 (PSTN) 连接，与早期的时分多路复用 (TDM) 中继相反，后者通常要求在每个分支站点部署单独的中继。</span><span class="sxs-lookup"><span data-stu-id="783e7-p101">Deploying SIP trunking can be a big step toward simplifying your organization’s telecommunications and preparing for up-to-date enhancements to real-time communications. One of the primary advantages of SIP trunking is that you can consolidate your organization’s connections to the public switched telephone network (PSTN) at a central site, as opposed to its predecessor, time division multiplexing (TDM) trunking, which typically requires a separate trunk from each branch site.</span></span>

<div>

## <a name="sip-trunking-in-lync-server"></a><span data-ttu-id="783e7-106">Lync Server 中的 SIP 中继</span><span class="sxs-lookup"><span data-stu-id="783e7-106">SIP Trunking in Lync Server</span></span>

<span data-ttu-id="783e7-107">Lync Server 2013 SIP 中继功能可实现以下功能：</span><span class="sxs-lookup"><span data-stu-id="783e7-107">The Lync Server 2013 SIP trunking capabilities enable the following:</span></span>

  - <span data-ttu-id="783e7-108">企业防火墙内外的企业用户可以拨打由符合 E.164 标准的号码指定的本地电话或长途电话，该电话将作为相应服务提供商的一项服务终止于 PSTN 上。</span><span class="sxs-lookup"><span data-stu-id="783e7-108">An enterprise user, whether inside or outside the corporate firewall, can make a local call or a long-distance call that is specified by an E.164-compliant number that is terminated on the PSTN as a service of the corresponding service provider.</span></span>

  - <span data-ttu-id="783e7-109">通过拨打与企业防火墙内外的企业用户关联的外线直拨分机 (DID) 号码，任何 PSTN 订阅者都可以与该企业用户取得联系。</span><span class="sxs-lookup"><span data-stu-id="783e7-109">Any PSTN subscriber can contact an enterprise user inside or outside the corporate firewall by dialing a Direct Inward Dialing (DID) number that is associated with that enterprise user.</span></span>

</div>

<div>

## <a name="cost-savings"></a><span data-ttu-id="783e7-110">节省成本</span><span class="sxs-lookup"><span data-stu-id="783e7-110">Cost Savings</span></span>

<span data-ttu-id="783e7-111">可以大大节省与 SIP 中继有关的成本：</span><span class="sxs-lookup"><span data-stu-id="783e7-111">The cost savings associated with SIP trunking can be substantial:</span></span>

  - <span data-ttu-id="783e7-112">通过 SIP 中继拨打长途电话通常可以大幅降低成本。</span><span class="sxs-lookup"><span data-stu-id="783e7-112">Long distance calls typically cost much less through a SIP trunk.</span></span>

  - <span data-ttu-id="783e7-113">可以节省可管理性成本并降低部署的复杂性。</span><span class="sxs-lookup"><span data-stu-id="783e7-113">You can cut manageability costs and reduce the complexity of deployment.</span></span>

  - <span data-ttu-id="783e7-p102">如果可以以极低的成本将 SIP 中继直接连接到 ITSP，则可以消除基本速率接口 (BRI) 和主速率接口 (PRI) 的费用。在 TDM 中继中，服务提供商按分钟对呼叫计费。SIP 中继的成本可能基于带宽使用，能够以更小、更经济的增量购买带宽。（实际成本取决于选择的 ITSP 的服务模型。）</span><span class="sxs-lookup"><span data-stu-id="783e7-p102">Basic rate interface (BRI) and primary rate interface (PRI) fees can be eliminated if you connect a SIP trunk directly to your ITSP at significantly lower cost. In TDM trunking, service providers charge for calls by the minute. The cost of SIP trunking may be based on bandwidth usage, which you can buy in smaller, more economical increments. (The actual cost depends on the service model of the ITSP you choose.)</span></span>

<div>

## <a name="sip-trunking-vs-hosting-a-pstn-gateway-or-ip-pbx"></a><span data-ttu-id="783e7-118">SIP 中继与承载 PSTN 网关或 IP-PBX</span><span class="sxs-lookup"><span data-stu-id="783e7-118">SIP Trunking vs. Hosting a PSTN Gateway or IP-PBX</span></span>

<span data-ttu-id="783e7-p103">由于 SIP 中继直接连接到服务提供商，因此可以消除 PSTN 网关及其管理成本和复杂性。使用 SIP 中继可以减少维护和管理工作，从而大幅节省成本。</span><span class="sxs-lookup"><span data-stu-id="783e7-p103">Because SIP trunks connect directly to your service provider, you can eliminate your PSTN gateways and their management cost and complexity. Using a SIP trunk can lead to substantial cost savings through reduced maintenance and administration.</span></span>

</div>

</div>

<div>

## <a name="expanded-voip-services"></a><span data-ttu-id="783e7-121">扩展的 VoIP 服务</span><span class="sxs-lookup"><span data-stu-id="783e7-121">Expanded VoIP Services</span></span>

<span data-ttu-id="783e7-122">语音功能通常是部署 SIP 中继的主要动机，但是语音支持只是第一步。</span><span class="sxs-lookup"><span data-stu-id="783e7-122">Voice features are often the primary motivation for deploying SIP trunking, but voice support is just the first step.</span></span> <span data-ttu-id="783e7-123">使用 SIP 中继，可以扩展 VoIP 功能并启用 Lync Server 2013，以提供更丰富的服务集。</span><span class="sxs-lookup"><span data-stu-id="783e7-123">With SIP trunking, you can extend VoIP capabilities and enable Lync Server 2013 to deliver a richer set of services.</span></span> <span data-ttu-id="783e7-124">例如：</span><span class="sxs-lookup"><span data-stu-id="783e7-124">For example:</span></span>

  - <span data-ttu-id="783e7-125">未运行 Lync Server 2013 的设备的增强状态检测可以提供与移动电话更好的集成，使你能够查看用户何时在移动电话呼叫。</span><span class="sxs-lookup"><span data-stu-id="783e7-125">Enhanced presence detection for devices that are not running Lync Server 2013 can provide better integration with mobile phones, enabling you to see when a user is on a mobile phone call.</span></span>

  - <span data-ttu-id="783e7-126">通过使用 E9-1-1 紧急呼叫，应答 911 呼叫的机构可以通过电话号码确定呼叫者的位置。</span><span class="sxs-lookup"><span data-stu-id="783e7-126">E9-1-1 emergency calling enables the authorities who answer 911 calls to determine the caller’s location from his or her telephone number.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="783e7-127">与 ITSP 联系以获取他们支持并且可以为贵组织启用的服务列表。</span><span class="sxs-lookup"><span data-stu-id="783e7-127">Contact your ITSP for a list of services that they support and can enable for your organization.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

