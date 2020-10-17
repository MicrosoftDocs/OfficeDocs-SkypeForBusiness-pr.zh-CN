---
title: Lync Server 2013：部署分支站点
description: Lync Server 2013：部署分支站点。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying branch sites
ms:assetid: 1475dee0-66ae-4ee5-b6f1-7409b4bbff45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398217(v=OCS.15)
ms:contentKeyID: 48183483
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d653e3f06de832693d97bfb229f122a67c28640e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552638"
---
# <a name="deploying-branch-sites-in-lync-server-2013"></a><span data-ttu-id="8a2f9-103">在 Lync Server 2013 中部署分支站点</span><span class="sxs-lookup"><span data-stu-id="8a2f9-103">Deploying branch sites in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8a2f9-104">_**上次修改的主题：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="8a2f9-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="8a2f9-105">分支站点用户从与分支站点相关联的中心站点上的服务器获取其大多数 Lync Server 2013 功能。</span><span class="sxs-lookup"><span data-stu-id="8a2f9-105">Branch site users get most of their Lync Server 2013 functionality from the server at the central site that the branch site is associated with.</span></span> <span data-ttu-id="8a2f9-106">每个分支站点都只与一个中央站点关联。</span><span class="sxs-lookup"><span data-stu-id="8a2f9-106">Each branch site is associated with exactly one central site.</span></span> <span data-ttu-id="8a2f9-107">要提供来往于公用电话交换网 (PSTN) 的呼叫，分支站点可以包含以下任一项：</span><span class="sxs-lookup"><span data-stu-id="8a2f9-107">To provide calls to and from the public switched telephone network (PSTN), a branch site might contain any of the following:</span></span>

  - <span data-ttu-id="8a2f9-108">PSTN 网关和可选的中介服务器</span><span class="sxs-lookup"><span data-stu-id="8a2f9-108">A PSTN gateway and possibly a Meditation Server</span></span>

  - <span data-ttu-id="8a2f9-109">SIP 中继</span><span class="sxs-lookup"><span data-stu-id="8a2f9-109">A SIP trunk</span></span>

  - <span data-ttu-id="8a2f9-110">具有专用交换机 (PBX) 的现有语音基础结构</span><span class="sxs-lookup"><span data-stu-id="8a2f9-110">An existing voice infrastructure with a private branch exchange (PBX)</span></span>

  - <span data-ttu-id="8a2f9-111">Survivable 分支设备</span><span class="sxs-lookup"><span data-stu-id="8a2f9-111">A Survivable Branch Appliance</span></span>

  - <span data-ttu-id="8a2f9-112">Survivable 分支服务器</span><span class="sxs-lookup"><span data-stu-id="8a2f9-112">A Survivable Branch Server</span></span>

<span data-ttu-id="8a2f9-113">具有 Survivable 分支设备或 Survivable 分支服务器的分支站点在广域网或分支服务器上的工作方式比不包含这些解决方案中的分支站点的时间更具弹性。</span><span class="sxs-lookup"><span data-stu-id="8a2f9-113">Branch sites with a Survivable Branch Appliance or a Survivable Branch Server are more resilient in times of wide-area network or central site failures than branch sites without one of these solutions.</span></span> <span data-ttu-id="8a2f9-114">例如，在部署了 Survivable 分支机构或 Survivable 分支服务器的站点中，如果将分支站点连接到中心站点的网络处于关闭状态，则用户仍可以发出和接收 PSTN 呼叫。</span><span class="sxs-lookup"><span data-stu-id="8a2f9-114">For example, in a site with a Survivable Branch Appliance or a Survivable Branch Server deployed, users can still make and receive PSTN calls if the network connecting the branch site to the central site is down.</span></span> <span data-ttu-id="8a2f9-115">实现分支站点恢复的另一种方法是在分支站点上使用具有完全规模的 Lync Server 部署的 PSTN 网关或 SIP 中继。</span><span class="sxs-lookup"><span data-stu-id="8a2f9-115">Another way to achieve branch-site resiliency is by using a PSTN gateway or a SIP trunk with a full-scale Lync Server deployment at the branch site.</span></span>

<span data-ttu-id="8a2f9-116">若要详细了解哪个分支站点部署适合您的组织，包括先决条件和其他规划注意事项，请参阅规划文档中的在 lync server [2013 中规划 PSTN 连接](lync-server-2013-planning-for-pstn-connectivity.md) 和 [规划分支站点语音2013恢复](lync-server-2013-planning-for-branch-site-voice-resiliency.md) 。</span><span class="sxs-lookup"><span data-stu-id="8a2f9-116">For details about which branch site deployment is right for your organization, including prerequisites and other planning considerations, see [Planning for PSTN connectivity in Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md) and [Planning for branch-site voice resiliency in Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md) in the Planning documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="8a2f9-117">本部分内容</span><span class="sxs-lookup"><span data-stu-id="8a2f9-117">In This Section</span></span>

  - [<span data-ttu-id="8a2f9-118">在 Lync Server 2013 中提供分支站点的 PSTN 连接</span><span class="sxs-lookup"><span data-stu-id="8a2f9-118">Providing PSTN connectivity at a branch site in Lync Server 2013</span></span>](lync-server-2013-providing-pstn-connectivity-at-a-branch-site.md)

  - [<span data-ttu-id="8a2f9-119">使用 Lync Server 2013 部署 Survivable 分支设备或服务器</span><span class="sxs-lookup"><span data-stu-id="8a2f9-119">Deploying a Survivable Branch Appliance or Server with Lync Server 2013</span></span>](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

