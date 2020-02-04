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
ms.openlocfilehash: 21b4f3e0a9beaae9419b11bf7353319b3b3ad2b0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755786"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="operations-guide-for-lync-server-2013"></a><span data-ttu-id="fb857-102">Operations Guide for Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb857-102">Operations Guide for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fb857-103">_**主题上次修改时间：** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="fb857-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="fb857-104">本文档介绍维护 Microsoft Lync Server 2013 通信软件环境所需的操作过程、任务和工具。</span><span class="sxs-lookup"><span data-stu-id="fb857-104">This document describes the operational processes, tasks, and tools that are required for you to maintain a Microsoft Lync Server 2013 communications software environment.</span></span> <span data-ttu-id="fb857-105">它介绍了如何根据 Microsoft 操作框架（MOF）模型管理 Lync Server 2013，它将帮助你设计高效的运营管理环境，其中包括实施计划、流程和过程来维护高效的工作环境。</span><span class="sxs-lookup"><span data-stu-id="fb857-105">It explains how to manage Lync Server 2013 according to the Microsoft Operations Framework (MOF) model and it will help you design an efficient operational management environment, which includes implementing schedules, processes and procedures to maintain an efficient working environment.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="fb857-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="fb857-106">In This Section</span></span>

<span data-ttu-id="fb857-107">包括以下部分：</span><span class="sxs-lookup"><span data-stu-id="fb857-107">The following sections are included:</span></span>

  - [<span data-ttu-id="fb857-108">Lync Server 2013 环境的最佳做法</span><span class="sxs-lookup"><span data-stu-id="fb857-108">Best practices for Lync Server 2013 environments</span></span>](lync-server-2013-best-practices-for-lync-server-environments.md)

  - [<span data-ttu-id="fb857-109">Lync Server 2013 中的日常任务</span><span class="sxs-lookup"><span data-stu-id="fb857-109">Daily tasks in Lync Server 2013</span></span>](lync-server-2013-daily-tasks.md)

  - [<span data-ttu-id="fb857-110">Lync Server 2013 中的周任务</span><span class="sxs-lookup"><span data-stu-id="fb857-110">Weekly tasks in Lync Server 2013</span></span>](lync-server-2013-weekly-tasks.md)

  - [<span data-ttu-id="fb857-111">Lync Server 2013 中的每月任务</span><span class="sxs-lookup"><span data-stu-id="fb857-111">Monthly tasks in Lync Server 2013</span></span>](lync-server-2013-monthly-tasks.md)

  - [<span data-ttu-id="fb857-112">Lync Server 2013 中的 "需要" 任务</span><span class="sxs-lookup"><span data-stu-id="fb857-112">As-needed tasks in Lync Server 2013</span></span>](lync-server-2013-as-needed-tasks.md)

  - [<span data-ttu-id="fb857-113">Lync Server 2013 的操作清单</span><span class="sxs-lookup"><span data-stu-id="fb857-113">Operations checklists for Lync Server 2013</span></span>](lync-server-2013-operations-checklists.md)

  - [<span data-ttu-id="fb857-114">通过 System Center Operations Manager 监视 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb857-114">Monitoring Lync Server 2013 with System Center Operations Manager</span></span>](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md)

  - [<span data-ttu-id="fb857-115">Lync Server 2013 中的操作相关性</span><span class="sxs-lookup"><span data-stu-id="fb857-115">Operational dependencies in Lync Server 2013</span></span>](lync-server-2013-operational-dependencies.md)

  - [<span data-ttu-id="fb857-116">Lync Server 2013 中的故障排除和关键运行状况指示器</span><span class="sxs-lookup"><span data-stu-id="fb857-116">Troubleshooting and Key Health Indicators in Lync Server 2013</span></span>](lync-server-2013-troubleshooting-and-key-health-indicators.md)

<span data-ttu-id="fb857-117">假设您的 Microsoft Lync Server 2013 部署已完成。</span><span class="sxs-lookup"><span data-stu-id="fb857-117">It is assumed that your Microsoft Lync Server 2013 deployment is completed.</span></span> <span data-ttu-id="fb857-118">如果不是这种情况，请参阅 Microsoft Lync Server 2013 的规划和部署内容，然后再继续。</span><span class="sxs-lookup"><span data-stu-id="fb857-118">If this is not the case, refer to the planning and deployment content for Microsoft Lync Server 2013 before you continue.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="fb857-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fb857-119">See Also</span></span>


[<span data-ttu-id="fb857-120">Lync Server 2013 入门</span><span class="sxs-lookup"><span data-stu-id="fb857-120">Getting started with Lync Server 2013</span></span>](lync-server-2013-getting-started.md)  
[<span data-ttu-id="fb857-121">规划 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb857-121">Planning for Lync Server 2013</span></span>](lync-server-2013-planning.md)  
[<span data-ttu-id="fb857-122">Lync Server 2013 的部署</span><span class="sxs-lookup"><span data-stu-id="fb857-122">Deployment of Lync Server 2013</span></span>](lync-server-2013-deployment.md)  
[<span data-ttu-id="fb857-123">Lync Server 2013 命令行管理程序</span><span class="sxs-lookup"><span data-stu-id="fb857-123">Lync Server 2013 Management Shell</span></span>](lync-server-2013-lync-server-management-shell.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

