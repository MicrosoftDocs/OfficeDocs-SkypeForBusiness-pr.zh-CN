---
title: Lync Server 2013：部署分支站点
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying branch sites
ms:assetid: 1475dee0-66ae-4ee5-b6f1-7409b4bbff45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398217(v=OCS.15)
ms:contentKeyID: 48183483
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c96a8c99b6f80e7e70f3129e502d33b93a73f42
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830560"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-branch-sites-in-lync-server-2013"></a><span data-ttu-id="e4ee0-102">在 Lync Server 2013 中部署分支站点</span><span class="sxs-lookup"><span data-stu-id="e4ee0-102">Deploying branch sites in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e4ee0-103">_**主题上次修改时间:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="e4ee0-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="e4ee0-104">分支网站用户从与分支站点相关联的中心站点上的服务器获取最大部分 Lync Server 2013 功能。</span><span class="sxs-lookup"><span data-stu-id="e4ee0-104">Branch site users get most of their Lync Server 2013 functionality from the server at the central site that the branch site is associated with.</span></span> <span data-ttu-id="e4ee0-105">每个分支站点只与一个中心站点相关联。</span><span class="sxs-lookup"><span data-stu-id="e4ee0-105">Each branch site is associated with exactly one central site.</span></span> <span data-ttu-id="e4ee0-106">若要提供与公共交换电话网络 (PSTN) 的呼叫, 分支站点可能包含以下任何内容:</span><span class="sxs-lookup"><span data-stu-id="e4ee0-106">To provide calls to and from the public switched telephone network (PSTN), a branch site might contain any of the following:</span></span>

  - <span data-ttu-id="e4ee0-107">PSTN 网关和可能是冥想服务器</span><span class="sxs-lookup"><span data-stu-id="e4ee0-107">A PSTN gateway and possibly a Meditation Server</span></span>

  - <span data-ttu-id="e4ee0-108">SIP 主干</span><span class="sxs-lookup"><span data-stu-id="e4ee0-108">A SIP trunk</span></span>

  - <span data-ttu-id="e4ee0-109">使用专用分支交换 (PBX) 的现有语音基础结构</span><span class="sxs-lookup"><span data-stu-id="e4ee0-109">An existing voice infrastructure with a private branch exchange (PBX)</span></span>

  - <span data-ttu-id="e4ee0-110">Survivable 分支装置</span><span class="sxs-lookup"><span data-stu-id="e4ee0-110">A Survivable Branch Appliance</span></span>

  - <span data-ttu-id="e4ee0-111">Survivable 分支服务器</span><span class="sxs-lookup"><span data-stu-id="e4ee0-111">A Survivable Branch Server</span></span>

<span data-ttu-id="e4ee0-112">具有 Survivable 分支装置或 Survivable 分支服务器的分支站点在广域网或分支服务器上的分支站点比没有这些解决方案的分支站点的广域网或中心站点故障更有弹性。</span><span class="sxs-lookup"><span data-stu-id="e4ee0-112">Branch sites with a Survivable Branch Appliance or a Survivable Branch Server are more resilient in times of wide-area network or central site failures than branch sites without one of these solutions.</span></span> <span data-ttu-id="e4ee0-113">例如, 在具有 Survivable 分支装置或部署的 Survivable 分支服务器的网站中, 如果将分支站点连接到中心站点的网络处于关闭状态, 则用户仍可以发出和接收 PSTN 呼叫。</span><span class="sxs-lookup"><span data-stu-id="e4ee0-113">For example, in a site with a Survivable Branch Appliance or a Survivable Branch Server deployed, users can still make and receive PSTN calls if the network connecting the branch site to the central site is down.</span></span> <span data-ttu-id="e4ee0-114">实现分支站点弹性的另一种方法是在分支站点上使用具有完全规模的 Lync 服务器部署的 PSTN 网关或 SIP 中继。</span><span class="sxs-lookup"><span data-stu-id="e4ee0-114">Another way to achieve branch-site resiliency is by using a PSTN gateway or a SIP trunk with a full-scale Lync Server deployment at the branch site.</span></span>

<span data-ttu-id="e4ee0-115">有关哪些分支站点部署适合你的组织 (包括先决条件和其他规划注意事项) 的详细信息, 请参阅[在 Lync Server 2013 中规划 PSTN 连接](lync-server-2013-planning-for-pstn-connectivity.md)和[规划 lync 中的分支站点语音弹性](lync-server-2013-planning-for-branch-site-voice-resiliency.md)在规划文档中的服务器2013。</span><span class="sxs-lookup"><span data-stu-id="e4ee0-115">For details about which branch site deployment is right for your organization, including prerequisites and other planning considerations, see [Planning for PSTN connectivity in Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md) and [Planning for branch-site voice resiliency in Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md) in the Planning documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e4ee0-116">本节内容</span><span class="sxs-lookup"><span data-stu-id="e4ee0-116">In This Section</span></span>

  - [<span data-ttu-id="e4ee0-117">在 Lync Server 2013 中在分支站点提供 PSTN 连接</span><span class="sxs-lookup"><span data-stu-id="e4ee0-117">Providing PSTN connectivity at a branch site in Lync Server 2013</span></span>](lync-server-2013-providing-pstn-connectivity-at-a-branch-site.md)

  - [<span data-ttu-id="e4ee0-118">使用 Lync Server 2013 部署 Survivable Branch Appliance 或 Survivable Branch Server</span><span class="sxs-lookup"><span data-stu-id="e4ee0-118">Deploying a Survivable Branch Appliance or Server with Lync Server 2013</span></span>](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

