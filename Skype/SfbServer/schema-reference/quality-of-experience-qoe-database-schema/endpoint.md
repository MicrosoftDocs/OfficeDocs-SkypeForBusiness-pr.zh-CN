---
title: Endpoint 表
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
description: Endpoint 表是一个支持表，用于存储有关已参与数据库中记录的会话的终结点的信息。 表中的每条记录表示一个终结点。
ms.openlocfilehash: 9caa0571e562a84c1678208f0e70c27317deda3c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823062"
---
# <a name="endpoint-table"></a><span data-ttu-id="e0b08-104">Endpoint 表</span><span class="sxs-lookup"><span data-stu-id="e0b08-104">Endpoint table</span></span>
 
<span data-ttu-id="e0b08-105">Endpoint 表是一个支持表，用于存储有关已参与数据库中记录的会话的终结点的信息。</span><span class="sxs-lookup"><span data-stu-id="e0b08-105">The Endpoint table is a supporting table that stores information about the endpoints that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="e0b08-106">表中的每条记录表示一个终结点。</span><span class="sxs-lookup"><span data-stu-id="e0b08-106">Each record in the table represents one endpoint.</span></span>
  
|<span data-ttu-id="e0b08-107">**列**</span><span class="sxs-lookup"><span data-stu-id="e0b08-107">**Column**</span></span>|<span data-ttu-id="e0b08-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="e0b08-108">**Data Type**</span></span>|<span data-ttu-id="e0b08-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="e0b08-109">**Key/Index**</span></span>|<span data-ttu-id="e0b08-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="e0b08-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e0b08-111">**EndpointKey**</span><span class="sxs-lookup"><span data-stu-id="e0b08-111">**EndpointKey**</span></span> <br/> |<span data-ttu-id="e0b08-112">int</span><span class="sxs-lookup"><span data-stu-id="e0b08-112">int</span></span>  <br/> |<span data-ttu-id="e0b08-113">主</span><span class="sxs-lookup"><span data-stu-id="e0b08-113">Primary</span></span>  <br/> |<span data-ttu-id="e0b08-114">标识此终结点的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="e0b08-114">Unique number identifying this endpoint.</span></span>  <br/> |
|<span data-ttu-id="e0b08-115">**名称**</span><span class="sxs-lookup"><span data-stu-id="e0b08-115">**Name**</span></span> <br/> |<span data-ttu-id="e0b08-116">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="e0b08-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="e0b08-117">独特</span><span class="sxs-lookup"><span data-stu-id="e0b08-117">Unique</span></span>  <br/> |<span data-ttu-id="e0b08-118">终结点名称。</span><span class="sxs-lookup"><span data-stu-id="e0b08-118">Endpoint name.</span></span>  <br/> |
|<span data-ttu-id="e0b08-119">**操作系统**</span><span class="sxs-lookup"><span data-stu-id="e0b08-119">**OS**</span></span> <br/> |<span data-ttu-id="e0b08-120">nvarchar (128) </span><span class="sxs-lookup"><span data-stu-id="e0b08-120">nvarchar(128)</span></span>  <br/> | <br/> |<span data-ttu-id="e0b08-121">操作系统 (终结点) 操作系统。</span><span class="sxs-lookup"><span data-stu-id="e0b08-121">Operating system (OS) of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="e0b08-122">**CPUName**</span><span class="sxs-lookup"><span data-stu-id="e0b08-122">**CPUName**</span></span> <br/> |<span data-ttu-id="e0b08-123">nvarchar (128) </span><span class="sxs-lookup"><span data-stu-id="e0b08-123">nvarchar(128)</span></span>  <br/> ||<span data-ttu-id="e0b08-124">终结点的 CPU 名称。</span><span class="sxs-lookup"><span data-stu-id="e0b08-124">CPU name of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="e0b08-125">**CPUNumberOfCores**</span><span class="sxs-lookup"><span data-stu-id="e0b08-125">**CPUNumberOfCores**</span></span> <br/> |<span data-ttu-id="e0b08-126">smallint</span><span class="sxs-lookup"><span data-stu-id="e0b08-126">smallint</span></span>  <br/> ||<span data-ttu-id="e0b08-127">终结点的 CPU 内核数。</span><span class="sxs-lookup"><span data-stu-id="e0b08-127">Number of CPU cores of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="e0b08-128">**CPUProcessorSpeed**</span><span class="sxs-lookup"><span data-stu-id="e0b08-128">**CPUProcessorSpeed**</span></span> <br/> |<span data-ttu-id="e0b08-129">int</span><span class="sxs-lookup"><span data-stu-id="e0b08-129">int</span></span>  <br/> ||<span data-ttu-id="e0b08-130">终结点的 CPU 处理器速度。</span><span class="sxs-lookup"><span data-stu-id="e0b08-130">CPU processor speed of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="e0b08-131">**VirtualizationFlag**</span><span class="sxs-lookup"><span data-stu-id="e0b08-131">**VirtualizationFlag**</span></span> <br/> |<span data-ttu-id="e0b08-132">tinyint</span><span class="sxs-lookup"><span data-stu-id="e0b08-132">tinyint</span></span>  <br/> || <span data-ttu-id="e0b08-133">指示系统是否正在虚拟化环境中运行的位标志：</span><span class="sxs-lookup"><span data-stu-id="e0b08-133">Bit flag that indicates if the system is running in a virtualized environment:</span></span> <br/>  <span data-ttu-id="e0b08-134">0x0000 - 无</span><span class="sxs-lookup"><span data-stu-id="e0b08-134">0x0000 - None</span></span> <br/>  <span data-ttu-id="e0b08-135">0x0001 - HyperV</span><span class="sxs-lookup"><span data-stu-id="e0b08-135">0x0001 - HyperV</span></span> <br/>  <span data-ttu-id="e0b08-136">0x0002 - VMWare</span><span class="sxs-lookup"><span data-stu-id="e0b08-136">0x0002 - VMWare</span></span> <br/>  <span data-ttu-id="e0b08-137">0x0004 - 虚拟电脑</span><span class="sxs-lookup"><span data-stu-id="e0b08-137">0x0004 - Virtual PC</span></span> <br/>  <span data-ttu-id="e0b08-138">0x0008 - Xen PC</span><span class="sxs-lookup"><span data-stu-id="e0b08-138">0x0008 - Xen PC</span></span> <br/> |
   

