---
title: Endpoint 表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
description: 终结点表是一个支持的表来存储有关记录在数据库中的会话中参与过的终结点信息。 每个表中的记录表示一个终结点。
ms.openlocfilehash: 64eb55a0c1bebe7f2ce992351ce21db2fdc575d7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="endpoint-table"></a><span data-ttu-id="4d2bd-104">Endpoint 表</span><span class="sxs-lookup"><span data-stu-id="4d2bd-104">Endpoint table</span></span>
 
<span data-ttu-id="4d2bd-105">终结点表是一个支持的表来存储有关记录在数据库中的会话中参与过的终结点信息。</span><span class="sxs-lookup"><span data-stu-id="4d2bd-105">The Endpoint table is a supporting table that stores information about the endpoints that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="4d2bd-106">每个表中的记录表示一个终结点。</span><span class="sxs-lookup"><span data-stu-id="4d2bd-106">Each record in the table represents one endpoint.</span></span>
  
|<span data-ttu-id="4d2bd-107">**列**</span><span class="sxs-lookup"><span data-stu-id="4d2bd-107">**Column**</span></span>|<span data-ttu-id="4d2bd-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="4d2bd-108">**Data Type**</span></span>|<span data-ttu-id="4d2bd-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="4d2bd-109">**Key/Index**</span></span>|<span data-ttu-id="4d2bd-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="4d2bd-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4d2bd-111">**EndpointKey**</span><span class="sxs-lookup"><span data-stu-id="4d2bd-111">**EndpointKey**</span></span> <br/> |<span data-ttu-id="4d2bd-112">int</span><span class="sxs-lookup"><span data-stu-id="4d2bd-112">int</span></span>  <br/> |<span data-ttu-id="4d2bd-113">Primary</span><span class="sxs-lookup"><span data-stu-id="4d2bd-113">Primary</span></span>  <br/> |<span data-ttu-id="4d2bd-114">标识此终结点的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="4d2bd-114">Unique number identifying this endpoint.</span></span>  <br/> |
|<span data-ttu-id="4d2bd-115">**名称** - 按 WAN 链路进行筛选（筛选器位于图形右侧）。</span><span class="sxs-lookup"><span data-stu-id="4d2bd-115">**Name**</span></span> <br/> |<span data-ttu-id="4d2bd-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="4d2bd-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="4d2bd-117">唯一</span><span class="sxs-lookup"><span data-stu-id="4d2bd-117">Unique</span></span>  <br/> |<span data-ttu-id="4d2bd-118">终结点名称。</span><span class="sxs-lookup"><span data-stu-id="4d2bd-118">Endpoint name.</span></span>  <br/> |
|<span data-ttu-id="4d2bd-119">**操作系统**</span><span class="sxs-lookup"><span data-stu-id="4d2bd-119">**OS**</span></span> <br/> |<span data-ttu-id="4d2bd-120">nvarchar(128)</span><span class="sxs-lookup"><span data-stu-id="4d2bd-120">nvarchar(128)</span></span>  <br/> | <br/> |<span data-ttu-id="4d2bd-121">操作系统 (OS) 的终结点。</span><span class="sxs-lookup"><span data-stu-id="4d2bd-121">Operating system (OS) of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="4d2bd-122">**CPUName**</span><span class="sxs-lookup"><span data-stu-id="4d2bd-122">**CPUName**</span></span> <br/> |<span data-ttu-id="4d2bd-123">nvarchar(128)</span><span class="sxs-lookup"><span data-stu-id="4d2bd-123">nvarchar(128)</span></span>  <br/> ||<span data-ttu-id="4d2bd-124">CPU 的终结点名称。</span><span class="sxs-lookup"><span data-stu-id="4d2bd-124">CPU name of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="4d2bd-125">**CPUNumberOfCores**</span><span class="sxs-lookup"><span data-stu-id="4d2bd-125">**CPUNumberOfCores**</span></span> <br/> |<span data-ttu-id="4d2bd-126">smallint</span><span class="sxs-lookup"><span data-stu-id="4d2bd-126">smallint</span></span>  <br/> ||<span data-ttu-id="4d2bd-127">终结点的 CPU 内核的数量。</span><span class="sxs-lookup"><span data-stu-id="4d2bd-127">Number of CPU cores of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="4d2bd-128">**CPUProcessorSpeed**</span><span class="sxs-lookup"><span data-stu-id="4d2bd-128">**CPUProcessorSpeed**</span></span> <br/> |<span data-ttu-id="4d2bd-129">int</span><span class="sxs-lookup"><span data-stu-id="4d2bd-129">int</span></span>  <br/> ||<span data-ttu-id="4d2bd-130">终结点的 CPU 处理器速度。</span><span class="sxs-lookup"><span data-stu-id="4d2bd-130">CPU processor speed of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="4d2bd-131">**VirtualizationFlag**</span><span class="sxs-lookup"><span data-stu-id="4d2bd-131">**VirtualizationFlag**</span></span> <br/> |<span data-ttu-id="4d2bd-132">tinyint</span><span class="sxs-lookup"><span data-stu-id="4d2bd-132">tinyint</span></span>  <br/> || <span data-ttu-id="4d2bd-133">位标志，指示系统将在虚拟化环境中运行：</span><span class="sxs-lookup"><span data-stu-id="4d2bd-133">Bit flag that indicates if the system is running in a virtualized environment:</span></span> <br/>  <span data-ttu-id="4d2bd-134">0x0000-无</span><span class="sxs-lookup"><span data-stu-id="4d2bd-134">0x0000 - None</span></span> <br/>  <span data-ttu-id="4d2bd-135">0x0001-HyperV</span><span class="sxs-lookup"><span data-stu-id="4d2bd-135">0x0001 - HyperV</span></span> <br/>  <span data-ttu-id="4d2bd-136">0x0002-VMWare</span><span class="sxs-lookup"><span data-stu-id="4d2bd-136">0x0002 - VMWare</span></span> <br/>  <span data-ttu-id="4d2bd-137">0x0004-虚拟 PC</span><span class="sxs-lookup"><span data-stu-id="4d2bd-137">0x0004 - Virtual PC</span></span> <br/>  <span data-ttu-id="4d2bd-138">0x0008-Xen 的 PC</span><span class="sxs-lookup"><span data-stu-id="4d2bd-138">0x0008 - Xen PC</span></span> <br/> |
   

