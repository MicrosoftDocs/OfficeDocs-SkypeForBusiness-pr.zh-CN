---
title: Lync Server 2013：日常任务
description: Lync Server 2013：日常任务。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Daily tasks
ms:assetid: f7a5f99e-5d2b-445d-9ba1-cbfcfeff16ae
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720351(v=OCS.15)
ms:contentKeyID: 63969666
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d9e2d62eb29db2bafa23565637bb655ba932c7b6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550178"
---
# <a name="daily-tasks-in-lync-server-2013"></a><span data-ttu-id="c5c9b-103">Lync Server 2013 中的日常任务</span><span class="sxs-lookup"><span data-stu-id="c5c9b-103">Daily tasks in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c5c9b-104">_**上次修改的主题：** 2015-01-26_</span><span class="sxs-lookup"><span data-stu-id="c5c9b-104">_**Topic Last Modified:** 2015-01-26_</span></span>

<span data-ttu-id="c5c9b-105">为了帮助确保 Lync Server 2013 部署的可用性和可靠性，您应成为对系统正常运行的日常监视和测试元素的一部分，其中包括物理平台、操作系统和所有重要的 Lync Server 2013 服务。</span><span class="sxs-lookup"><span data-stu-id="c5c9b-105">To help ensure the availability and reliability of the Lync Server 2013 deployment, you should as part of daily routine monitor and test elements that are very important to the functioning of the system, which includes the physical platform, the operating system, and all important Lync Server 2013 services.</span></span> <span data-ttu-id="c5c9b-106">预防性维护和主动监视将帮助您识别可能会对 Lync Server 2013 部署产生负面影响的潜在错误和问题。</span><span class="sxs-lookup"><span data-stu-id="c5c9b-106">Preventive maintenance and proactive monitoring will help you identify potential errors and issues that may adversely affect the Lync Server 2013 deployment.</span></span>

<span data-ttu-id="c5c9b-107">监视 Lync Server 2013 部署涉及到检查连接、服务、服务器资源和系统资源的问题。</span><span class="sxs-lookup"><span data-stu-id="c5c9b-107">Monitoring the Lync Server 2013 deployment involves checking for issues with connections, services, server resources, and system resources.</span></span> <span data-ttu-id="c5c9b-108">Windows Server 操作系统与 System Center Operations Manager 和 Lync Server 提供了很多监视工具和服务，可帮助确保 Lync Server 组织正常运行。</span><span class="sxs-lookup"><span data-stu-id="c5c9b-108">Windows Server operating systems, together with System Center Operations Manager, and Lync Server give you many monitoring tools and services to help ensure that the Lync Server organization is running smoothly.</span></span> <span data-ttu-id="c5c9b-109">当这些技术一起实施时，管理员将能够在出现问题时或之前收到警报。</span><span class="sxs-lookup"><span data-stu-id="c5c9b-109">When these technologies are implemented together, administrators will be able to receive alerts when or before issues occur.</span></span>

<span data-ttu-id="c5c9b-110">日常监控的主要优势如下：</span><span class="sxs-lookup"><span data-stu-id="c5c9b-110">The key advantages to daily monitoring are as follows:</span></span>

  - <span data-ttu-id="c5c9b-111">满足已定义的 Sla 的性能和可用性要求。</span><span class="sxs-lookup"><span data-stu-id="c5c9b-111">Meeting the performance and availability requirements of defined SLAs.</span></span>

  - <span data-ttu-id="c5c9b-112">成功完成特定管理任务，例如每日备份操作和检查服务器运行状况。</span><span class="sxs-lookup"><span data-stu-id="c5c9b-112">Successfully completing specific administrative tasks, such as daily backup operations, and checking server health.</span></span>

  - <span data-ttu-id="c5c9b-113">检测和解决问题，如服务器性能中的瓶颈或在影响工作效率之前需要额外资源。</span><span class="sxs-lookup"><span data-stu-id="c5c9b-113">Detecting and addressing issues, such as bottlenecks in the server performance, or need for additional resources before they affect productivity.</span></span>

<span data-ttu-id="c5c9b-114">每日维护任务可帮助管理团队为组织内的常规系统操作定义或建立条件或基准，并检测任何异常活动。</span><span class="sxs-lookup"><span data-stu-id="c5c9b-114">Daily maintenance tasks help the administrative team to define or establish a criteria or baseline for normal systems operations within the organization, and to detect any abnormal activity.</span></span> <span data-ttu-id="c5c9b-115">一定要实施这些日常维护任务，以便管理团队可以捕获和维护有关 Lync Server 2013 基础结构的数据，如使用率级别、可能的性能瓶颈和管理更改。</span><span class="sxs-lookup"><span data-stu-id="c5c9b-115">It is important to implement these daily maintenance tasks so that the administrative team can capture and maintain data about the Lync Server 2013 infrastructure, such as usage levels, possible performance bottlenecks, and administrative changes.</span></span>

<span data-ttu-id="c5c9b-116">若要帮助组织日常任务的性能，请使用 [日常任务清单](lync-server-2013-operations-checklists.md)。</span><span class="sxs-lookup"><span data-stu-id="c5c9b-116">To help organize the performance of daily tasks, use the [Daily task checklist](lync-server-2013-operations-checklists.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="c5c9b-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c5c9b-117">See Also</span></span>


[<span data-ttu-id="c5c9b-118">日常任务清单</span><span class="sxs-lookup"><span data-stu-id="c5c9b-118">Daily task checklist</span></span>](lync-server-2013-operations-checklists.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

