---
title: Lync Server 2013：操作指南
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Operations Guide
ms:assetid: dcb9ddff-6fe3-4077-a2e3-0ba64f65e264
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720467(v=OCS.15)
ms:contentKeyID: 63969658
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a1e6a07b881968f22b9ba36fc217002ea59032d5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153462"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="operations-guide-for-lync-server-2013"></a><span data-ttu-id="6dd84-102">Lync Server 2013 的操作指南</span><span class="sxs-lookup"><span data-stu-id="6dd84-102">Operations Guide for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6dd84-103">_**上次修改的主题：** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="6dd84-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="6dd84-104">本文档介绍维护 Microsoft Lync Server 2013 通信软件环境所需的操作过程、任务和工具。</span><span class="sxs-lookup"><span data-stu-id="6dd84-104">This document describes the operational processes, tasks, and tools that are required for you to maintain a Microsoft Lync Server 2013 communications software environment.</span></span> <span data-ttu-id="6dd84-105">它说明了如何根据 Microsoft 操作框架（MOF）模型管理 Lync Server 2013，它还将帮助您设计高效的运营管理环境，其中包括实施计划、过程和过程来维护高效的工作环境。</span><span class="sxs-lookup"><span data-stu-id="6dd84-105">It explains how to manage Lync Server 2013 according to the Microsoft Operations Framework (MOF) model and it will help you design an efficient operational management environment, which includes implementing schedules, processes and procedures to maintain an efficient working environment.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="6dd84-106">本部分内容</span><span class="sxs-lookup"><span data-stu-id="6dd84-106">In This Section</span></span>

<span data-ttu-id="6dd84-107">包含以下各节：</span><span class="sxs-lookup"><span data-stu-id="6dd84-107">The following sections are included:</span></span>

  - [<span data-ttu-id="6dd84-108">Lync Server 2013 环境的最佳实践</span><span class="sxs-lookup"><span data-stu-id="6dd84-108">Best practices for Lync Server 2013 environments</span></span>](lync-server-2013-best-practices-for-lync-server-environments.md)

  - [<span data-ttu-id="6dd84-109">Lync Server 2013 中的日常任务</span><span class="sxs-lookup"><span data-stu-id="6dd84-109">Daily tasks in Lync Server 2013</span></span>](lync-server-2013-daily-tasks.md)

  - [<span data-ttu-id="6dd84-110">Lync Server 2013 中的每周任务</span><span class="sxs-lookup"><span data-stu-id="6dd84-110">Weekly tasks in Lync Server 2013</span></span>](lync-server-2013-weekly-tasks.md)

  - [<span data-ttu-id="6dd84-111">Lync Server 2013 中的每月任务</span><span class="sxs-lookup"><span data-stu-id="6dd84-111">Monthly tasks in Lync Server 2013</span></span>](lync-server-2013-monthly-tasks.md)

  - [<span data-ttu-id="6dd84-112">Lync Server 2013 中的必需任务</span><span class="sxs-lookup"><span data-stu-id="6dd84-112">As-needed tasks in Lync Server 2013</span></span>](lync-server-2013-as-needed-tasks.md)

  - [<span data-ttu-id="6dd84-113">Lync Server 2013 的操作清单</span><span class="sxs-lookup"><span data-stu-id="6dd84-113">Operations checklists for Lync Server 2013</span></span>](lync-server-2013-operations-checklists.md)

  - [<span data-ttu-id="6dd84-114">使用 System Center Operations Manager 监视 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6dd84-114">Monitoring Lync Server 2013 with System Center Operations Manager</span></span>](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md)

  - [<span data-ttu-id="6dd84-115">Lync Server 2013 中的操作依赖项</span><span class="sxs-lookup"><span data-stu-id="6dd84-115">Operational dependencies in Lync Server 2013</span></span>](lync-server-2013-operational-dependencies.md)

  - [<span data-ttu-id="6dd84-116">Lync Server 2013 中的故障排除和关键运行状况指示器</span><span class="sxs-lookup"><span data-stu-id="6dd84-116">Troubleshooting and Key Health Indicators in Lync Server 2013</span></span>](lync-server-2013-troubleshooting-and-key-health-indicators.md)

<span data-ttu-id="6dd84-117">假定您的 Microsoft Lync Server 2013 部署已完成。</span><span class="sxs-lookup"><span data-stu-id="6dd84-117">It is assumed that your Microsoft Lync Server 2013 deployment is completed.</span></span> <span data-ttu-id="6dd84-118">如果不是这种情况，请参阅 Microsoft Lync Server 2013 的规划和部署内容，然后再继续。</span><span class="sxs-lookup"><span data-stu-id="6dd84-118">If this is not the case, refer to the planning and deployment content for Microsoft Lync Server 2013 before you continue.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6dd84-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6dd84-119">See Also</span></span>


[<span data-ttu-id="6dd84-120">Lync Server 2013 入门</span><span class="sxs-lookup"><span data-stu-id="6dd84-120">Getting started with Lync Server 2013</span></span>](lync-server-2013-getting-started.md)  
[<span data-ttu-id="6dd84-121">规划 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6dd84-121">Planning for Lync Server 2013</span></span>](lync-server-2013-planning.md)  
[<span data-ttu-id="6dd84-122">Lync Server 2013 的部署</span><span class="sxs-lookup"><span data-stu-id="6dd84-122">Deployment of Lync Server 2013</span></span>](lync-server-2013-deployment.md)  
[<span data-ttu-id="6dd84-123">Lync Server 2013 命令行管理程序</span><span class="sxs-lookup"><span data-stu-id="6dd84-123">Lync Server 2013 Management Shell</span></span>](lync-server-2013-lync-server-management-shell.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

