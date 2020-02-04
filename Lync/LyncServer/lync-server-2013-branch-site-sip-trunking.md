---
title: Lync Server 2013：分支站点 SIP 中继
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Branch site SIP trunking
ms:assetid: c4d9dfcd-8baa-41ea-9677-48b0e429429d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412974(v=OCS.15)
ms:contentKeyID: 48185350
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c31f0f42a10905f784536b08f10370be9694800
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741812"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="branch-site-sip-trunking-in-lync-server-2013"></a><span data-ttu-id="ca600-102">Branch site SIP trunking in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ca600-102">Branch site SIP trunking in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ca600-103">_**主题上次修改时间：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="ca600-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="ca600-104">在某些情况下，你可能需要在选定的分支站点上实施分布式 SIP 中继。</span><span class="sxs-lookup"><span data-stu-id="ca600-104">In some cases, you may need to implement distributed SIP trunking at selected branch sites.</span></span> <span data-ttu-id="ca600-105">若要确定分支站点是否需要 SIP 主干，请查看[如何在 Lync Server 2013 中实现 sip 中继](lync-server-2013-how-do-i-implement-sip-trunking.md)的信息？。</span><span class="sxs-lookup"><span data-stu-id="ca600-105">To determine whether a SIP trunk is needed for a branch site, review the information in [How do I implement SIP trunking in Lync Server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md).</span></span>

<span data-ttu-id="ca600-106">有关在分支站点中部署 SIP 中继支持的拓扑选项的详细信息，请参阅[Lync Server 2013 中的分支站点恢复解决方案](lync-server-2013-branch-site-resiliency-solutions.md)。</span><span class="sxs-lookup"><span data-stu-id="ca600-106">For details about the supported topology options for deploying SIP trunks in branch sites, see [Branch-site resiliency solutions in Lync Server 2013](lync-server-2013-branch-site-resiliency-solutions.md).</span></span>

<div>

## <a name="example-branch-site-sip-trunk-requirements-analysis"></a><span data-ttu-id="ca600-107">示例分支站点 SIP 中继要求分析</span><span class="sxs-lookup"><span data-stu-id="ca600-107">Example Branch Site SIP Trunk Requirements Analysis</span></span>

<span data-ttu-id="ca600-108">当您决定部署分支站点 SIP 主干时，您需要执行特定于站点的成本分析。</span><span class="sxs-lookup"><span data-stu-id="ca600-108">When you decide to deploy a branch site SIP trunk, you need to perform a site-specific cost analysis.</span></span> <span data-ttu-id="ca600-109">例如，在 Redmond、华盛顿和纽约的分支站点中具有中心网站的企业，应执行分析以确定是否要从纽约站点向本地服务提供商实施 SIP 主干。</span><span class="sxs-lookup"><span data-stu-id="ca600-109">For example, an enterprise that has a central site in Redmond, Washington, and a branch site in New York, should do an analysis to determine whether to implement a SIP trunk from the New York site to a local service provider.</span></span>

<span data-ttu-id="ca600-110">为了确定纽约的分布式 SIP 中继是否经济高效，请标识将使用 SIP 中继的外线直拨分机（DID）号码，并分析纽约向雷德蒙德 (425) 以外的地区发出的呼叫数量。</span><span class="sxs-lookup"><span data-stu-id="ca600-110">To determine whether a distributed SIP trunk in New York is cost-effective, identify which Direct Inward Dialing (DID) numbers will use the SIP trunk, and analyze the number of calls New York makes to areas other than Redmond (425).</span></span> <span data-ttu-id="ca600-111">您可以在中心站点上终止分支站点。</span><span class="sxs-lookup"><span data-stu-id="ca600-111">You can have DID termination for the branch site at the central site.</span></span> <span data-ttu-id="ca600-112">例如，Redmond 中心网站可以托管纽约分支网站的号码。</span><span class="sxs-lookup"><span data-stu-id="ca600-112">For example, the Redmond central site can host DID numbers for the New York branch site.</span></span> <span data-ttu-id="ca600-113">如果实施分布式 SIP 主干的费用低于这些呼叫的费用，请考虑在纽约分支机构实施 SIP 中继。</span><span class="sxs-lookup"><span data-stu-id="ca600-113">If the cost of implementing a distributed SIP trunk is less than the cost of those calls, consider implementing a SIP trunk at the New York branch site.</span></span>

</div>

<div>

## <a name="other-branch-site-sip-trunk-requirements"></a><span data-ttu-id="ca600-114">其他分支站点 SIP 中继要求</span><span class="sxs-lookup"><span data-stu-id="ca600-114">Other Branch Site SIP Trunk Requirements</span></span>

<span data-ttu-id="ca600-115">根据每个选项的公用电话交换网（PSTN）长途电话费的差额，选择部署 SIP 中继，而不是网关。</span><span class="sxs-lookup"><span data-stu-id="ca600-115">The choice between a deploying a SIP trunk instead of a gateway is based on the difference between the public switched telephone network (PSTN) long distance toll charges of each option.</span></span> <span data-ttu-id="ca600-116">如果你部署分支网站 SIP 主干，还需要确定你的恢复性和带宽要求。</span><span class="sxs-lookup"><span data-stu-id="ca600-116">If you deploy a branch site SIP trunk, you also need to determine your resiliency and bandwidth requirements.</span></span> <span data-ttu-id="ca600-117">如果分支站点和中心网站之间的链接具有弹性且带宽充足，则可以部署 SIP 主干或网关。</span><span class="sxs-lookup"><span data-stu-id="ca600-117">If the link between your branch site and central site is resilient and has sufficient bandwidth, you can deploy a SIP trunk or a gateway.</span></span> <span data-ttu-id="ca600-118">无需在分支站点上部署 Survivable 分支装置。</span><span class="sxs-lookup"><span data-stu-id="ca600-118">You do not need to deploy a Survivable Branch Appliance at the branch site.</span></span> <span data-ttu-id="ca600-119">如果你的分支站点和中心网站之间的链接不能复原，请部署 Survivable 分支设备，或使用分支站点上的网关或 SIP 中继部署 Survivable 分支服务器。</span><span class="sxs-lookup"><span data-stu-id="ca600-119">If the link between your branch site and central site is not resilient, deploy a Survivable Branch Appliance, or deploy a Survivable Branch Server with either a gateway or SIP trunk at the branch site.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

