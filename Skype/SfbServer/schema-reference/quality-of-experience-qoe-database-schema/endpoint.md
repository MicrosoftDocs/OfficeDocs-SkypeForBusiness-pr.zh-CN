---
title: Endpoint 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
description: 终结点表是一个支持表，用于存储参与数据库中记录的会话的终结点的相关信息。 表中的每条记录表示一个终结点。
ms.openlocfilehash: b64b19a3149fa3d490ea8dc957699c0a114f763c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41809550"
---
# <a name="endpoint-table"></a><span data-ttu-id="3dd25-104">Endpoint 表</span><span class="sxs-lookup"><span data-stu-id="3dd25-104">Endpoint table</span></span>
 
<span data-ttu-id="3dd25-105">终结点表是一个支持表，用于存储参与数据库中记录的会话的终结点的相关信息。</span><span class="sxs-lookup"><span data-stu-id="3dd25-105">The Endpoint table is a supporting table that stores information about the endpoints that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="3dd25-106">表中的每条记录表示一个终结点。</span><span class="sxs-lookup"><span data-stu-id="3dd25-106">Each record in the table represents one endpoint.</span></span>
  
|<span data-ttu-id="3dd25-107">**列**</span><span class="sxs-lookup"><span data-stu-id="3dd25-107">**Column**</span></span>|<span data-ttu-id="3dd25-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="3dd25-108">**Data Type**</span></span>|<span data-ttu-id="3dd25-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="3dd25-109">**Key/Index**</span></span>|<span data-ttu-id="3dd25-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="3dd25-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3dd25-111">**EndpointKey**</span><span class="sxs-lookup"><span data-stu-id="3dd25-111">**EndpointKey**</span></span> <br/> |<span data-ttu-id="3dd25-112">int</span><span class="sxs-lookup"><span data-stu-id="3dd25-112">int</span></span>  <br/> |<span data-ttu-id="3dd25-113">Primary</span><span class="sxs-lookup"><span data-stu-id="3dd25-113">Primary</span></span>  <br/> |<span data-ttu-id="3dd25-114">标识此终结点的唯一号码。</span><span class="sxs-lookup"><span data-stu-id="3dd25-114">Unique number identifying this endpoint.</span></span>  <br/> |
|<span data-ttu-id="3dd25-115">**名称** - 按 WAN 链路进行筛选（筛选器位于图形右侧）。</span><span class="sxs-lookup"><span data-stu-id="3dd25-115">**Name**</span></span> <br/> |<span data-ttu-id="3dd25-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="3dd25-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="3dd25-117">唯一</span><span class="sxs-lookup"><span data-stu-id="3dd25-117">Unique</span></span>  <br/> |<span data-ttu-id="3dd25-118">终结点名称。</span><span class="sxs-lookup"><span data-stu-id="3dd25-118">Endpoint name.</span></span>  <br/> |
|<span data-ttu-id="3dd25-119">**OS**</span><span class="sxs-lookup"><span data-stu-id="3dd25-119">**OS**</span></span> <br/> |<span data-ttu-id="3dd25-120">nvarchar</span><span class="sxs-lookup"><span data-stu-id="3dd25-120">nvarchar(128)</span></span>  <br/> | <br/> |<span data-ttu-id="3dd25-121">终结点的操作系统（OS）。</span><span class="sxs-lookup"><span data-stu-id="3dd25-121">Operating system (OS) of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="3dd25-122">**CPUName**</span><span class="sxs-lookup"><span data-stu-id="3dd25-122">**CPUName**</span></span> <br/> |<span data-ttu-id="3dd25-123">nvarchar</span><span class="sxs-lookup"><span data-stu-id="3dd25-123">nvarchar(128)</span></span>  <br/> ||<span data-ttu-id="3dd25-124">终结点的 CPU 名称。</span><span class="sxs-lookup"><span data-stu-id="3dd25-124">CPU name of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="3dd25-125">**CPUNumberOfCores**</span><span class="sxs-lookup"><span data-stu-id="3dd25-125">**CPUNumberOfCores**</span></span> <br/> |<span data-ttu-id="3dd25-126">smallint</span><span class="sxs-lookup"><span data-stu-id="3dd25-126">smallint</span></span>  <br/> ||<span data-ttu-id="3dd25-127">终结点的 CPU 内核数。</span><span class="sxs-lookup"><span data-stu-id="3dd25-127">Number of CPU cores of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="3dd25-128">**CPUProcessorSpeed**</span><span class="sxs-lookup"><span data-stu-id="3dd25-128">**CPUProcessorSpeed**</span></span> <br/> |<span data-ttu-id="3dd25-129">int</span><span class="sxs-lookup"><span data-stu-id="3dd25-129">int</span></span>  <br/> ||<span data-ttu-id="3dd25-130">终结点的 CPU 处理器速度。</span><span class="sxs-lookup"><span data-stu-id="3dd25-130">CPU processor speed of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="3dd25-131">**VirtualizationFlag**</span><span class="sxs-lookup"><span data-stu-id="3dd25-131">**VirtualizationFlag**</span></span> <br/> |<span data-ttu-id="3dd25-132">tinyint</span><span class="sxs-lookup"><span data-stu-id="3dd25-132">tinyint</span></span>  <br/> || <span data-ttu-id="3dd25-133">指示系统是否在虚拟化环境中运行的位标志：</span><span class="sxs-lookup"><span data-stu-id="3dd25-133">Bit flag that indicates if the system is running in a virtualized environment:</span></span> <br/>  <span data-ttu-id="3dd25-134">0x0000-无</span><span class="sxs-lookup"><span data-stu-id="3dd25-134">0x0000 - None</span></span> <br/>  <span data-ttu-id="3dd25-135">0x0001-HyperV</span><span class="sxs-lookup"><span data-stu-id="3dd25-135">0x0001 - HyperV</span></span> <br/>  <span data-ttu-id="3dd25-136">0x0002-VMWare</span><span class="sxs-lookup"><span data-stu-id="3dd25-136">0x0002 - VMWare</span></span> <br/>  <span data-ttu-id="3dd25-137">0x0004-虚拟电脑</span><span class="sxs-lookup"><span data-stu-id="3dd25-137">0x0004 - Virtual PC</span></span> <br/>  <span data-ttu-id="3dd25-138">0x0008-Xen 电脑</span><span class="sxs-lookup"><span data-stu-id="3dd25-138">0x0008 - Xen PC</span></span> <br/> |
   

