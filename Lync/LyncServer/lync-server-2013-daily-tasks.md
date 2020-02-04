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
ms.openlocfilehash: 9d63aff308b23e52284988a184e5e9d72beaca26
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728672"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="daily-tasks-in-lync-server-2013"></a><span data-ttu-id="23801-102">Lync Server 2013 中的日常任务</span><span class="sxs-lookup"><span data-stu-id="23801-102">Daily tasks in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="23801-103">_**主题上次修改时间：** 2015-01-26_</span><span class="sxs-lookup"><span data-stu-id="23801-103">_**Topic Last Modified:** 2015-01-26_</span></span>

<span data-ttu-id="23801-104">为了帮助确保 Lync Server 2013 部署的可用性和可靠性，你应该作为日常例行监视器和测试元素的一部分，这些元素对系统的运行非常重要，其中包括物理平台、操作系统和所有重要的 Lync Server 2013 服务。</span><span class="sxs-lookup"><span data-stu-id="23801-104">To help ensure the availability and reliability of the Lync Server 2013 deployment, you should as part of daily routine monitor and test elements that are very important to the functioning of the system, which includes the physical platform, the operating system, and all important Lync Server 2013 services.</span></span> <span data-ttu-id="23801-105">预防性维护和主动预防性监视将帮助你识别可能会对 Lync Server 2013 部署产生负面影响的潜在错误和问题。</span><span class="sxs-lookup"><span data-stu-id="23801-105">Preventive maintenance and proactive monitoring will help you identify potential errors and issues that may adversely affect the Lync Server 2013 deployment.</span></span>

<span data-ttu-id="23801-106">监视 Lync Server 2013 部署涉及检查与连接、服务、服务器资源和系统资源相关的问题。</span><span class="sxs-lookup"><span data-stu-id="23801-106">Monitoring the Lync Server 2013 deployment involves checking for issues with connections, services, server resources, and system resources.</span></span> <span data-ttu-id="23801-107">Windows Server 操作系统与 System Center Operations Manager 以及 Lync 服务器一起提供了许多监视工具和服务，可帮助确保 Lync 服务器组织顺利运行。</span><span class="sxs-lookup"><span data-stu-id="23801-107">Windows Server operating systems, together with System Center Operations Manager, and Lync Server give you many monitoring tools and services to help ensure that the Lync Server organization is running smoothly.</span></span> <span data-ttu-id="23801-108">当一起实施这些技术时，管理员能够在问题发生时或之前收到警报。</span><span class="sxs-lookup"><span data-stu-id="23801-108">When these technologies are implemented together, administrators will be able to receive alerts when or before issues occur.</span></span>

<span data-ttu-id="23801-109">日常监视的关键好处如下所示：</span><span class="sxs-lookup"><span data-stu-id="23801-109">The key advantages to daily monitoring are as follows:</span></span>

  - <span data-ttu-id="23801-110">满足定义的 SLA 的性能和可用性要求。</span><span class="sxs-lookup"><span data-stu-id="23801-110">Meeting the performance and availability requirements of defined SLAs.</span></span>

  - <span data-ttu-id="23801-111">成功完成特定管理任务（如日常备份操作）和检查服务器运行状况。</span><span class="sxs-lookup"><span data-stu-id="23801-111">Successfully completing specific administrative tasks, such as daily backup operations, and checking server health.</span></span>

  - <span data-ttu-id="23801-112">在其他资源的问题（例如服务器性能方面的瓶颈）或需求影响生产效率之前检测和解决它们。</span><span class="sxs-lookup"><span data-stu-id="23801-112">Detecting and addressing issues, such as bottlenecks in the server performance, or need for additional resources before they affect productivity.</span></span>

<span data-ttu-id="23801-113">日常管理任务可帮助管理团队针对组织内的正常系统运作定义或设立条件或基准，并检测任何异常活动。</span><span class="sxs-lookup"><span data-stu-id="23801-113">Daily maintenance tasks help the administrative team to define or establish a criteria or baseline for normal systems operations within the organization, and to detect any abnormal activity.</span></span> <span data-ttu-id="23801-114">执行这些日常维护任务非常重要，这样管理团队可以捕获和维护有关 Lync Server 2013 基础结构的数据，例如使用级别、可能的性能瓶颈和管理更改。</span><span class="sxs-lookup"><span data-stu-id="23801-114">It is important to implement these daily maintenance tasks so that the administrative team can capture and maintain data about the Lync Server 2013 infrastructure, such as usage levels, possible performance bottlenecks, and administrative changes.</span></span>

<span data-ttu-id="23801-115">为帮助整理日常任务的性能，请使用[日常任务清单](lync-server-2013-operations-checklists.md)。</span><span class="sxs-lookup"><span data-stu-id="23801-115">To help organize the performance of daily tasks, use the [Daily task checklist](lync-server-2013-operations-checklists.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="23801-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="23801-116">See Also</span></span>


[<span data-ttu-id="23801-117">日常任务清单</span><span class="sxs-lookup"><span data-stu-id="23801-117">Daily task checklist</span></span>](lync-server-2013-operations-checklists.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

