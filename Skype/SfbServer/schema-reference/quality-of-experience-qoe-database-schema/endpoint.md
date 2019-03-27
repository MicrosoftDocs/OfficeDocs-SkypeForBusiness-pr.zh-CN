---
title: Endpoint 表
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
description: Endpoint 表是一个支持表，用于存储已参与记录数据库中的会话的终结点的信息。 表中的每条记录代表一个终结点。
ms.openlocfilehash: f9c304408006ef9caf5521b8f0bbe28c2d917abe
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30882995"
---
# <a name="endpoint-table"></a><span data-ttu-id="8fcdc-104">Endpoint 表</span><span class="sxs-lookup"><span data-stu-id="8fcdc-104">Endpoint table</span></span>
 
<span data-ttu-id="8fcdc-105">Endpoint 表是一个支持表，用于存储已参与记录数据库中的会话的终结点的信息。</span><span class="sxs-lookup"><span data-stu-id="8fcdc-105">The Endpoint table is a supporting table that stores information about the endpoints that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="8fcdc-106">表中的每条记录代表一个终结点。</span><span class="sxs-lookup"><span data-stu-id="8fcdc-106">Each record in the table represents one endpoint.</span></span>
  
|<span data-ttu-id="8fcdc-107">**列**</span><span class="sxs-lookup"><span data-stu-id="8fcdc-107">**Column**</span></span>|<span data-ttu-id="8fcdc-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="8fcdc-108">**Data Type**</span></span>|<span data-ttu-id="8fcdc-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="8fcdc-109">**Key/Index**</span></span>|<span data-ttu-id="8fcdc-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="8fcdc-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8fcdc-111">**EndpointKey**</span><span class="sxs-lookup"><span data-stu-id="8fcdc-111">**EndpointKey**</span></span> <br/> |<span data-ttu-id="8fcdc-112">int</span><span class="sxs-lookup"><span data-stu-id="8fcdc-112">int</span></span>  <br/> |<span data-ttu-id="8fcdc-113">Primary</span><span class="sxs-lookup"><span data-stu-id="8fcdc-113">Primary</span></span>  <br/> |<span data-ttu-id="8fcdc-114">标识此终结点的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="8fcdc-114">Unique number identifying this endpoint.</span></span>  <br/> |
|<span data-ttu-id="8fcdc-115">**名称** - 按 WAN 链路进行筛选（筛选器位于图形右侧）。</span><span class="sxs-lookup"><span data-stu-id="8fcdc-115">**Name**</span></span> <br/> |<span data-ttu-id="8fcdc-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="8fcdc-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="8fcdc-117">唯一</span><span class="sxs-lookup"><span data-stu-id="8fcdc-117">Unique</span></span>  <br/> |<span data-ttu-id="8fcdc-118">终结点名称。</span><span class="sxs-lookup"><span data-stu-id="8fcdc-118">Endpoint name.</span></span>  <br/> |
|<span data-ttu-id="8fcdc-119">**OS**</span><span class="sxs-lookup"><span data-stu-id="8fcdc-119">**OS**</span></span> <br/> |<span data-ttu-id="8fcdc-120">nvarchar(128)</span><span class="sxs-lookup"><span data-stu-id="8fcdc-120">nvarchar(128)</span></span>  <br/> | <br/> |<span data-ttu-id="8fcdc-121">操作系统 (OS) 的终结点。</span><span class="sxs-lookup"><span data-stu-id="8fcdc-121">Operating system (OS) of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="8fcdc-122">**CPUName**</span><span class="sxs-lookup"><span data-stu-id="8fcdc-122">**CPUName**</span></span> <br/> |<span data-ttu-id="8fcdc-123">nvarchar(128)</span><span class="sxs-lookup"><span data-stu-id="8fcdc-123">nvarchar(128)</span></span>  <br/> ||<span data-ttu-id="8fcdc-124">终结点的 CPU 名称。</span><span class="sxs-lookup"><span data-stu-id="8fcdc-124">CPU name of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="8fcdc-125">**CPUNumberOfCores**</span><span class="sxs-lookup"><span data-stu-id="8fcdc-125">**CPUNumberOfCores**</span></span> <br/> |<span data-ttu-id="8fcdc-126">smallint</span><span class="sxs-lookup"><span data-stu-id="8fcdc-126">smallint</span></span>  <br/> ||<span data-ttu-id="8fcdc-127">终结点的 CPU 内核数。</span><span class="sxs-lookup"><span data-stu-id="8fcdc-127">Number of CPU cores of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="8fcdc-128">**CPUProcessorSpeed**</span><span class="sxs-lookup"><span data-stu-id="8fcdc-128">**CPUProcessorSpeed**</span></span> <br/> |<span data-ttu-id="8fcdc-129">int</span><span class="sxs-lookup"><span data-stu-id="8fcdc-129">int</span></span>  <br/> ||<span data-ttu-id="8fcdc-130">终结点的 CPU 处理器速度。</span><span class="sxs-lookup"><span data-stu-id="8fcdc-130">CPU processor speed of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="8fcdc-131">**VirtualizationFlag**</span><span class="sxs-lookup"><span data-stu-id="8fcdc-131">**VirtualizationFlag**</span></span> <br/> |<span data-ttu-id="8fcdc-132">tinyint</span><span class="sxs-lookup"><span data-stu-id="8fcdc-132">tinyint</span></span>  <br/> || <span data-ttu-id="8fcdc-133">指示系统是否正在运行的虚拟化环境中的位标志：</span><span class="sxs-lookup"><span data-stu-id="8fcdc-133">Bit flag that indicates if the system is running in a virtualized environment:</span></span> <br/>  <span data-ttu-id="8fcdc-134">0x0000-无</span><span class="sxs-lookup"><span data-stu-id="8fcdc-134">0x0000 - None</span></span> <br/>  <span data-ttu-id="8fcdc-135">0x0001-HyperV</span><span class="sxs-lookup"><span data-stu-id="8fcdc-135">0x0001 - HyperV</span></span> <br/>  <span data-ttu-id="8fcdc-136">0x0002-VMWare</span><span class="sxs-lookup"><span data-stu-id="8fcdc-136">0x0002 - VMWare</span></span> <br/>  <span data-ttu-id="8fcdc-137">0x0004-虚拟 PC</span><span class="sxs-lookup"><span data-stu-id="8fcdc-137">0x0004 - Virtual PC</span></span> <br/>  <span data-ttu-id="8fcdc-138">0x0008-Xen PC</span><span class="sxs-lookup"><span data-stu-id="8fcdc-138">0x0008 - Xen PC</span></span> <br/> |
   

