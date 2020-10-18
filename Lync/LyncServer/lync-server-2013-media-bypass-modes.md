---
title: Lync Server 2013：媒体绕过模式
description: Lync Server 2013：媒体旁路模式。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media bypass modes
ms:assetid: 38c06c81-7e45-4423-9e00-7fbfa4befe46
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425862(v=OCS.15)
ms:contentKeyID: 48183898
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a7f1a71930df7ef92a29087f42bdb9382b3904c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577898"
---
# <a name="media-bypass-modes-in-lync-server-2013"></a><span data-ttu-id="82494-103">Lync Server 2013 中的媒体旁路模式</span><span class="sxs-lookup"><span data-stu-id="82494-103">Media bypass modes in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="82494-104">_**上次修改的主题：** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="82494-104">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="82494-p101">必须配置全局和每个单个 PSTN 中继的媒体旁路。在全局范围内启用媒体旁路时，有两种选择：“始终绕过”\*\*\*\* 和“使用站点和区域信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="82494-p101">You must configure media bypass both globally and for each individual PSTN trunk. When enabling media bypass globally, you have two choices: **Always Bypass** and **Use Site and Region Information**.</span></span>

<span data-ttu-id="82494-p102">顾名思义，“始终绕过”\*\*\*\* 表示将试图绕过所有 PSTN 呼叫。“始终绕过”\*\*\*\* 用于既不需要启用呼叫允许控制也不需要指定与何时尝试媒体旁路相关的详细配置信息的部署。此外，在客户端和 PSTN 网关之间有完全连接时需使用“始终绕过”\*\*\*\*。在此配置中，所有子网将映射至唯一的绕过 ID，该 ID 由系统计算得出。</span><span class="sxs-lookup"><span data-stu-id="82494-p102">As the name suggests, **Always Bypass** means that bypass will be attempted for all PSTN calls. **Always Bypass** is used for deployments where there is no need to enable call admission control, nor is there a need to specify detailed configuration information regarding when to attempt media bypass. Furthermore, **Always Bypass** is used when there is full connectivity between clients and PSTN gateways. In this configuration, all subnets are mapped to one and only one bypass ID, which is computed by the system.</span></span>

<span data-ttu-id="82494-p103">通过“使用站点和区域信息”\*\*\*\*，与站点和区域配置关联的绕过 ID 将用于做出绕过决定。此配置可使您灵活地配置大部分常用拓扑的绕过，因为除了支持与呼叫允许控制 (CAC) 的交互之外，它还可以使您对何时发生绕过进行精确控制。系统会尝试通过自动分配绕过 ID 简化任务，如下所示。</span><span class="sxs-lookup"><span data-stu-id="82494-p103">With **Use Site and Region Information**, the bypass ID associated with site and region configuration is used to make the bypass decision. This configuration provides the flexibility to configure bypass for most common topologies, as it gives you fine-grained control over when bypass happens, in addition to supporting interactions with call admission control (CAC). The system tries to ease your task by automatically assigning bypass IDs as follows.</span></span>

  - <span data-ttu-id="82494-114">系统会自动为每个区域分配单个唯一的绕过 ID。</span><span class="sxs-lookup"><span data-stu-id="82494-114">The system automatically assigns a single unique bypass ID to each region.</span></span>

  - <span data-ttu-id="82494-115">任何通过 WAN 链路连接到区域的没有带宽限制的站点将继承与该区域相同的绕过 ID。</span><span class="sxs-lookup"><span data-stu-id="82494-115">Any site connected to a region over a WAN link without bandwidth constraints inherits the same bypass ID as the region.</span></span>

  - <span data-ttu-id="82494-116">将为通过 WAN 链路与区域关联的具有带宽限制的站点分配与该区域不同的绕过 ID。</span><span class="sxs-lookup"><span data-stu-id="82494-116">A site associated with the region over a WAN link with constrained bandwidth is assigned a different bypass ID from that of the region.</span></span>

  - <span data-ttu-id="82494-117">与每个站点关联的子网将继承该站点的绕过 ID。</span><span class="sxs-lookup"><span data-stu-id="82494-117">Subnets associated with each site inherit the bypass ID for that site.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="82494-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="82494-118">See Also</span></span>


[<span data-ttu-id="82494-119">Lync Server 2013 中的媒体旁路概述</span><span class="sxs-lookup"><span data-stu-id="82494-119">Overview of media bypass in Lync Server 2013</span></span>](lync-server-2013-overview-of-media-bypass.md)  
[<span data-ttu-id="82494-120">Lync Server 2013 中的媒体旁路和呼叫允许控制</span><span class="sxs-lookup"><span data-stu-id="82494-120">Media bypass and call admission control in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-call-admission-control.md)  
[<span data-ttu-id="82494-121">Lync Server 2013 中媒体旁路的技术要求</span><span class="sxs-lookup"><span data-stu-id="82494-121">Technical requirements for media bypass in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

