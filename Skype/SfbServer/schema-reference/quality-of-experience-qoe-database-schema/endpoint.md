---
title: Endpoint 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
description: Endpoint 表是一个支持表，用于存储已参与记录数据库中的会话的终结点的信息。 表中的每条记录代表一个终结点。
ms.openlocfilehash: 4917b0817d8fcedbc3a20b2c41d3ed62ce468c5c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920108"
---
# <a name="endpoint-table"></a><span data-ttu-id="ed673-104">Endpoint 表</span><span class="sxs-lookup"><span data-stu-id="ed673-104">Endpoint table</span></span>
 
<span data-ttu-id="ed673-105">Endpoint 表是一个支持表，用于存储已参与记录数据库中的会话的终结点的信息。</span><span class="sxs-lookup"><span data-stu-id="ed673-105">The Endpoint table is a supporting table that stores information about the endpoints that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="ed673-106">表中的每条记录代表一个终结点。</span><span class="sxs-lookup"><span data-stu-id="ed673-106">Each record in the table represents one endpoint.</span></span>
  
|<span data-ttu-id="ed673-107">**列**</span><span class="sxs-lookup"><span data-stu-id="ed673-107">**Column**</span></span>|<span data-ttu-id="ed673-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="ed673-108">**Data Type**</span></span>|<span data-ttu-id="ed673-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="ed673-109">**Key/Index**</span></span>|<span data-ttu-id="ed673-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="ed673-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ed673-111">**EndpointKey**</span><span class="sxs-lookup"><span data-stu-id="ed673-111">**EndpointKey**</span></span> <br/> |<span data-ttu-id="ed673-112">int</span><span class="sxs-lookup"><span data-stu-id="ed673-112">int</span></span>  <br/> |<span data-ttu-id="ed673-113">Primary</span><span class="sxs-lookup"><span data-stu-id="ed673-113">Primary</span></span>  <br/> |<span data-ttu-id="ed673-114">标识此终结点的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="ed673-114">Unique number identifying this endpoint.</span></span>  <br/> |
|<span data-ttu-id="ed673-115">**名称** - 按 WAN 链路进行筛选（筛选器位于图形右侧）。</span><span class="sxs-lookup"><span data-stu-id="ed673-115">**Name**</span></span> <br/> |<span data-ttu-id="ed673-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ed673-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="ed673-117">唯一</span><span class="sxs-lookup"><span data-stu-id="ed673-117">Unique</span></span>  <br/> |<span data-ttu-id="ed673-118">终结点名称。</span><span class="sxs-lookup"><span data-stu-id="ed673-118">Endpoint name.</span></span>  <br/> |
|<span data-ttu-id="ed673-119">**OS**</span><span class="sxs-lookup"><span data-stu-id="ed673-119">**OS**</span></span> <br/> |<span data-ttu-id="ed673-120">nvarchar(128)</span><span class="sxs-lookup"><span data-stu-id="ed673-120">nvarchar(128)</span></span>  <br/> | <br/> |<span data-ttu-id="ed673-121">操作系统 (OS) 的终结点。</span><span class="sxs-lookup"><span data-stu-id="ed673-121">Operating system (OS) of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="ed673-122">**CPUName**</span><span class="sxs-lookup"><span data-stu-id="ed673-122">**CPUName**</span></span> <br/> |<span data-ttu-id="ed673-123">nvarchar(128)</span><span class="sxs-lookup"><span data-stu-id="ed673-123">nvarchar(128)</span></span>  <br/> ||<span data-ttu-id="ed673-124">终结点的 CPU 名称。</span><span class="sxs-lookup"><span data-stu-id="ed673-124">CPU name of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="ed673-125">**CPUNumberOfCores**</span><span class="sxs-lookup"><span data-stu-id="ed673-125">**CPUNumberOfCores**</span></span> <br/> |<span data-ttu-id="ed673-126">smallint</span><span class="sxs-lookup"><span data-stu-id="ed673-126">smallint</span></span>  <br/> ||<span data-ttu-id="ed673-127">终结点的 CPU 内核数。</span><span class="sxs-lookup"><span data-stu-id="ed673-127">Number of CPU cores of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="ed673-128">**CPUProcessorSpeed**</span><span class="sxs-lookup"><span data-stu-id="ed673-128">**CPUProcessorSpeed**</span></span> <br/> |<span data-ttu-id="ed673-129">int</span><span class="sxs-lookup"><span data-stu-id="ed673-129">int</span></span>  <br/> ||<span data-ttu-id="ed673-130">终结点的 CPU 处理器速度。</span><span class="sxs-lookup"><span data-stu-id="ed673-130">CPU processor speed of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="ed673-131">**VirtualizationFlag**</span><span class="sxs-lookup"><span data-stu-id="ed673-131">**VirtualizationFlag**</span></span> <br/> |<span data-ttu-id="ed673-132">tinyint</span><span class="sxs-lookup"><span data-stu-id="ed673-132">tinyint</span></span>  <br/> || <span data-ttu-id="ed673-133">指示系统是否正在运行的虚拟化环境中的位标志：</span><span class="sxs-lookup"><span data-stu-id="ed673-133">Bit flag that indicates if the system is running in a virtualized environment:</span></span> <br/>  <span data-ttu-id="ed673-134">0x0000-无</span><span class="sxs-lookup"><span data-stu-id="ed673-134">0x0000 - None</span></span> <br/>  <span data-ttu-id="ed673-135">0x0001-HyperV</span><span class="sxs-lookup"><span data-stu-id="ed673-135">0x0001 - HyperV</span></span> <br/>  <span data-ttu-id="ed673-136">0x0002-VMWare</span><span class="sxs-lookup"><span data-stu-id="ed673-136">0x0002 - VMWare</span></span> <br/>  <span data-ttu-id="ed673-137">0x0004-虚拟 PC</span><span class="sxs-lookup"><span data-stu-id="ed673-137">0x0004 - Virtual PC</span></span> <br/>  <span data-ttu-id="ed673-138">0x0008-Xen PC</span><span class="sxs-lookup"><span data-stu-id="ed673-138">0x0008 - Xen PC</span></span> <br/> |
   

