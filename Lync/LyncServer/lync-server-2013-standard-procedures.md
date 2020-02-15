---
title: Lync Server 2013：标准过程
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Standard procedures
ms:assetid: 1b45d610-9840-4568-89e5-004ba31a15cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720323(v=OCS.15)
ms:contentKeyID: 63969581
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e59c3c4a1b76b7f3549f53721e29aa1e34085334
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038814"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="standard-procedures-in-lync-server-2013"></a><span data-ttu-id="115e2-102">Lync Server 2013 中的标准过程</span><span class="sxs-lookup"><span data-stu-id="115e2-102">Standard procedures in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="115e2-103">_**上次修改的主题：** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="115e2-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="115e2-104">有几个资源可帮助您定义组织中所需的标准过程以及如何执行这些过程。</span><span class="sxs-lookup"><span data-stu-id="115e2-104">Several resources can help you define what standard procedures are required in the organization, and how to perform them.</span></span> <span data-ttu-id="115e2-105">由于每个组织都是唯一的，因此您可能需要进一步自定义和调整这些资源以满足日常要求。标准操作过程更改，并且文档偶尔必须修订。</span><span class="sxs-lookup"><span data-stu-id="115e2-105">Because each organization is unique, you may have to additionally customize and adapt these resources to suit everyday requirements.Standard operational procedures change, and documentation occasionally has to be revised.</span></span> <span data-ttu-id="115e2-106">在进行更改后，更改管理过程在 Microsoft 操作框架的服务管理功能中定义，应确定每个更改可能对执行管理任务的方式和时间有何影响。</span><span class="sxs-lookup"><span data-stu-id="115e2-106">As changes are made, the change management process, as defined in the Service Management Functions of the Microsoft Operational Framework, should identify how each change is likely to affect how and when administrative tasks are performed.</span></span> <span data-ttu-id="115e2-107">使用更改管理功能来更新和控制过程文档。我们建议将操作任务分为易于管理的工作负载，其中任务在每天、每周、每月和需要的基础上执行。</span><span class="sxs-lookup"><span data-stu-id="115e2-107">Use the change management function to update and control the procedural documentation.We recommend that operational tasks be separated into manageable workloads, where tasks are performed on a daily, weekly, monthly, and as-needed basis.</span></span> <span data-ttu-id="115e2-108">每日任务将重点放在对系统的正常运行非常重要的方面，并且每月任务的详细情况将重点放在确保系统长期运行的情况。</span><span class="sxs-lookup"><span data-stu-id="115e2-108">Daily tasks would focus efforts on aspects that are very important to the functioning of a system and monthly tasks would focus more on ensuring the long-term health of a system.</span></span> <span data-ttu-id="115e2-109">必须执行的任务可以分为以下几类：</span><span class="sxs-lookup"><span data-stu-id="115e2-109">The tasks that must be performed can be separated into the following categories:</span></span>

  - [<span data-ttu-id="115e2-110">Lync Server 2013 中的日常任务</span><span class="sxs-lookup"><span data-stu-id="115e2-110">Daily tasks in Lync Server 2013</span></span>](lync-server-2013-daily-tasks.md)

  - [<span data-ttu-id="115e2-111">Lync Server 2013 中的每周任务</span><span class="sxs-lookup"><span data-stu-id="115e2-111">Weekly tasks in Lync Server 2013</span></span>](lync-server-2013-weekly-tasks.md)

  - [<span data-ttu-id="115e2-112">Lync Server 2013 中的每月任务</span><span class="sxs-lookup"><span data-stu-id="115e2-112">Monthly tasks in Lync Server 2013</span></span>](lync-server-2013-monthly-tasks.md)

  - [<span data-ttu-id="115e2-113">Lync Server 2013 中的必需任务</span><span class="sxs-lookup"><span data-stu-id="115e2-113">As-needed tasks in Lync Server 2013</span></span>](lync-server-2013-as-needed-tasks.md)

<span data-ttu-id="115e2-114">在为操作管理准备文档时，请使用清单来帮助确保在适当的时间执行所需的任务。</span><span class="sxs-lookup"><span data-stu-id="115e2-114">When preparing documentation for operations management, use checklists to help ensure that the required tasks are performed at the appropriate time.</span></span> <span data-ttu-id="115e2-115">有关如何准备操作清单的详细信息，请参阅位于操作清单中的示例检查表。</span><span class="sxs-lookup"><span data-stu-id="115e2-115">For detailed information about how to prepare operations checklists, see the sample checklists located in Operations Checklists.</span></span>

<span data-ttu-id="115e2-116">通常情况下，更改管理将接管系统管理完成的位置。</span><span class="sxs-lookup"><span data-stu-id="115e2-116">Frequently, change management takes over where system administration finishes.</span></span> <span data-ttu-id="115e2-117">如果某个任务由标准过程覆盖，则它是系统管理功能的一部分。</span><span class="sxs-lookup"><span data-stu-id="115e2-117">If a task is covered by a standard procedure, it is part of the system administration function.</span></span> <span data-ttu-id="115e2-118">如果没有针对任务的标准过程，则应使用更改管理功能来处理该任务。</span><span class="sxs-lookup"><span data-stu-id="115e2-118">If there is no standard procedure for a task, it should be handled by using the change management function.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="115e2-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="115e2-119">See Also</span></span>


[<span data-ttu-id="115e2-120">日常任务清单</span><span class="sxs-lookup"><span data-stu-id="115e2-120">Daily task checklist</span></span>](lync-server-2013-operations-checklists.md)  
[<span data-ttu-id="115e2-121">每周任务清单</span><span class="sxs-lookup"><span data-stu-id="115e2-121">Weekly task checklist</span></span>](lync-server-2013-operations-checklists.md)  
[<span data-ttu-id="115e2-122">每月任务清单</span><span class="sxs-lookup"><span data-stu-id="115e2-122">Monthly task checklist</span></span>](lync-server-2013-operations-checklists.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

