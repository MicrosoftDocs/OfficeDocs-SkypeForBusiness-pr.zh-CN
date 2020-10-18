---
title: Lync Server 2013：终结点表
description: Lync Server 2013：终结点表。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Endpoint table
ms:assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398327(v=OCS.15)
ms:contentKeyID: 48184098
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 614872eee41b5d8e56da4b96cf5bbe3a4a1cf4d2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575618"
---
# <a name="endpoint-table-in-lync-server-2013"></a><span data-ttu-id="f9b61-103">Lync Server 2013 中的终结点表</span><span class="sxs-lookup"><span data-stu-id="f9b61-103">Endpoint table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f9b61-104">_**上次修改的主题：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="f9b61-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="f9b61-105">终结点表是一个支持表，它存储有关参与在数据库中记录的会话的终结点的信息。</span><span class="sxs-lookup"><span data-stu-id="f9b61-105">The Endpoint table is a supporting table that stores information about the endpoints that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="f9b61-106">表中的每条记录代表一个终结点。</span><span class="sxs-lookup"><span data-stu-id="f9b61-106">Each record in the table represents one endpoint.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f9b61-107"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="f9b61-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="f9b61-108"><strong>数据类型</strong></span><span class="sxs-lookup"><span data-stu-id="f9b61-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="f9b61-109"><strong>键/索引</strong></span><span class="sxs-lookup"><span data-stu-id="f9b61-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="f9b61-110"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="f9b61-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f9b61-111"><strong>EndpointKey</strong></span><span class="sxs-lookup"><span data-stu-id="f9b61-111"><strong>EndpointKey</strong></span></span></p></td>
<td><p><span data-ttu-id="f9b61-112">int</span><span class="sxs-lookup"><span data-stu-id="f9b61-112">int</span></span></p></td>
<td><p><span data-ttu-id="f9b61-113">主</span><span class="sxs-lookup"><span data-stu-id="f9b61-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="f9b61-114">标识此终结点的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="f9b61-114">Unique number identifying this endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9b61-115"><strong>名称</strong></span><span class="sxs-lookup"><span data-stu-id="f9b61-115"><strong>Name</strong></span></span></p></td>
<td><p><span data-ttu-id="f9b61-116">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="f9b61-116">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f9b61-117">独特</span><span class="sxs-lookup"><span data-stu-id="f9b61-117">Unique</span></span></p></td>
<td><p><span data-ttu-id="f9b61-118">终结点名称。</span><span class="sxs-lookup"><span data-stu-id="f9b61-118">Endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9b61-119"><strong>OS</strong></span><span class="sxs-lookup"><span data-stu-id="f9b61-119"><strong>OS</strong></span></span></p></td>
<td><p><span data-ttu-id="f9b61-120">nvarchar (128) </span><span class="sxs-lookup"><span data-stu-id="f9b61-120">nvarchar(128)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f9b61-121">终结点的操作系统 (OS) 。</span><span class="sxs-lookup"><span data-stu-id="f9b61-121">Operating system (OS) of the endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9b61-122"><strong>CPUName</strong></span><span class="sxs-lookup"><span data-stu-id="f9b61-122"><strong>CPUName</strong></span></span></p></td>
<td><p><span data-ttu-id="f9b61-123">nvarchar (128) </span><span class="sxs-lookup"><span data-stu-id="f9b61-123">nvarchar(128)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f9b61-124">终结点的 CPU 名称。</span><span class="sxs-lookup"><span data-stu-id="f9b61-124">CPU name of the endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9b61-125"><strong>CPUNumberOfCores</strong></span><span class="sxs-lookup"><span data-stu-id="f9b61-125"><strong>CPUNumberOfCores</strong></span></span></p></td>
<td><p><span data-ttu-id="f9b61-126">smallint</span><span class="sxs-lookup"><span data-stu-id="f9b61-126">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f9b61-127">终结点的 CPU 内核数。</span><span class="sxs-lookup"><span data-stu-id="f9b61-127">Number of CPU cores of the endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9b61-128"><strong>CPUProcessorSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="f9b61-128"><strong>CPUProcessorSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="f9b61-129">int</span><span class="sxs-lookup"><span data-stu-id="f9b61-129">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f9b61-130">终结点的 CPU 处理器速度。</span><span class="sxs-lookup"><span data-stu-id="f9b61-130">CPU processor speed of the endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9b61-131"><strong>VirtualizationFlag</strong></span><span class="sxs-lookup"><span data-stu-id="f9b61-131"><strong>VirtualizationFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="f9b61-132">tinyint</span><span class="sxs-lookup"><span data-stu-id="f9b61-132">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f9b61-133">表示系统是否在虚拟化环境中运行的位标志：</span><span class="sxs-lookup"><span data-stu-id="f9b61-133">Bit flag that indicates if the system is running in a virtualized environment:</span></span></p>
<ul>
<li><p><span data-ttu-id="f9b61-134">0x0000 –无</span><span class="sxs-lookup"><span data-stu-id="f9b61-134">0x0000 – None</span></span></p></li>
<li><p><span data-ttu-id="f9b61-135">0x0001 – HyperV</span><span class="sxs-lookup"><span data-stu-id="f9b61-135">0x0001 – HyperV</span></span></p></li>
<li><p><span data-ttu-id="f9b61-136">0x0002 – VMWare</span><span class="sxs-lookup"><span data-stu-id="f9b61-136">0x0002 – VMWare</span></span></p></li>
<li><p><span data-ttu-id="f9b61-137">0x0004 – Virtual 电脑</span><span class="sxs-lookup"><span data-stu-id="f9b61-137">0x0004 – Virtual PC</span></span></p></li>
<li><p><span data-ttu-id="f9b61-138">0x0008 – Xen PC</span><span class="sxs-lookup"><span data-stu-id="f9b61-138">0x0008 – Xen PC</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

