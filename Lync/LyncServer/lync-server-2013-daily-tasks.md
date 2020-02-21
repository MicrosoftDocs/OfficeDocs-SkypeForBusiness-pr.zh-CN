---
title: Lync Server 2013：日常任务
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
ms.openlocfilehash: 87653490036c55a5f8b60925c988775c881a7326
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42209139"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="daily-tasks-in-lync-server-2013"></a><span data-ttu-id="6f30f-102">Lync Server 2013 中的日常任务</span><span class="sxs-lookup"><span data-stu-id="6f30f-102">Daily tasks in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6f30f-103">_**上次修改的主题：** 2015-01-26_</span><span class="sxs-lookup"><span data-stu-id="6f30f-103">_**Topic Last Modified:** 2015-01-26_</span></span>

<span data-ttu-id="6f30f-104">为了帮助确保 Lync Server 2013 部署的可用性和可靠性，您应作为日常例行监视和测试元素的一部分，这些元素对系统的正常运行非常重要，包括物理平台、操作系统和所有重要的 Lync Server 2013 服务。</span><span class="sxs-lookup"><span data-stu-id="6f30f-104">To help ensure the availability and reliability of the Lync Server 2013 deployment, you should as part of daily routine monitor and test elements that are very important to the functioning of the system, which includes the physical platform, the operating system, and all important Lync Server 2013 services.</span></span> <span data-ttu-id="6f30f-105">预防性维护和主动监视将帮助您识别可能会对 Lync Server 2013 部署产生负面影响的潜在错误和问题。</span><span class="sxs-lookup"><span data-stu-id="6f30f-105">Preventive maintenance and proactive monitoring will help you identify potential errors and issues that may adversely affect the Lync Server 2013 deployment.</span></span>

<span data-ttu-id="6f30f-106">监视 Lync Server 2013 部署涉及到检查连接、服务、服务器资源和系统资源的问题。</span><span class="sxs-lookup"><span data-stu-id="6f30f-106">Monitoring the Lync Server 2013 deployment involves checking for issues with connections, services, server resources, and system resources.</span></span> <span data-ttu-id="6f30f-107">Windows Server 操作系统与 System Center Operations Manager 和 Lync Server 提供了很多监视工具和服务，可帮助确保 Lync Server 组织正常运行。</span><span class="sxs-lookup"><span data-stu-id="6f30f-107">Windows Server operating systems, together with System Center Operations Manager, and Lync Server give you many monitoring tools and services to help ensure that the Lync Server organization is running smoothly.</span></span> <span data-ttu-id="6f30f-108">当这些技术一起实施时，管理员将能够在出现问题时或之前收到警报。</span><span class="sxs-lookup"><span data-stu-id="6f30f-108">When these technologies are implemented together, administrators will be able to receive alerts when or before issues occur.</span></span>

<span data-ttu-id="6f30f-109">日常监控的主要优势如下：</span><span class="sxs-lookup"><span data-stu-id="6f30f-109">The key advantages to daily monitoring are as follows:</span></span>

  - <span data-ttu-id="6f30f-110">满足已定义的 Sla 的性能和可用性要求。</span><span class="sxs-lookup"><span data-stu-id="6f30f-110">Meeting the performance and availability requirements of defined SLAs.</span></span>

  - <span data-ttu-id="6f30f-111">成功完成特定管理任务，例如每日备份操作和检查服务器运行状况。</span><span class="sxs-lookup"><span data-stu-id="6f30f-111">Successfully completing specific administrative tasks, such as daily backup operations, and checking server health.</span></span>

  - <span data-ttu-id="6f30f-112">检测和解决问题，如服务器性能中的瓶颈或在影响工作效率之前需要额外资源。</span><span class="sxs-lookup"><span data-stu-id="6f30f-112">Detecting and addressing issues, such as bottlenecks in the server performance, or need for additional resources before they affect productivity.</span></span>

<span data-ttu-id="6f30f-113">每日维护任务可帮助管理团队为组织内的常规系统操作定义或建立条件或基准，并检测任何异常活动。</span><span class="sxs-lookup"><span data-stu-id="6f30f-113">Daily maintenance tasks help the administrative team to define or establish a criteria or baseline for normal systems operations within the organization, and to detect any abnormal activity.</span></span> <span data-ttu-id="6f30f-114">一定要实施这些日常维护任务，以便管理团队可以捕获和维护有关 Lync Server 2013 基础结构的数据，如使用率级别、可能的性能瓶颈和管理更改。</span><span class="sxs-lookup"><span data-stu-id="6f30f-114">It is important to implement these daily maintenance tasks so that the administrative team can capture and maintain data about the Lync Server 2013 infrastructure, such as usage levels, possible performance bottlenecks, and administrative changes.</span></span>

<span data-ttu-id="6f30f-115">若要帮助组织日常任务的性能，请使用[日常任务清单](lync-server-2013-operations-checklists.md)。</span><span class="sxs-lookup"><span data-stu-id="6f30f-115">To help organize the performance of daily tasks, use the [Daily task checklist](lync-server-2013-operations-checklists.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="6f30f-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6f30f-116">See Also</span></span>


[<span data-ttu-id="6f30f-117">日常任务清单</span><span class="sxs-lookup"><span data-stu-id="6f30f-117">Daily task checklist</span></span>](lync-server-2013-operations-checklists.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

