---
title: Lync Server 2013：Endpoint 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Endpoint table
ms:assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398327(v=OCS.15)
ms:contentKeyID: 48184098
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6cedf4d85cefd8a9fefb9f0ee4608f4a290fdc09
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830214"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="endpoint-table-in-lync-server-2013"></a><span data-ttu-id="2bb86-102">Lync Server 2013 中的 Endpoint 表</span><span class="sxs-lookup"><span data-stu-id="2bb86-102">Endpoint table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2bb86-103">_**主题上次修改时间:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="2bb86-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="2bb86-104">终结点表是一个支持表, 用于存储参与数据库中记录的会话的终结点的相关信息。</span><span class="sxs-lookup"><span data-stu-id="2bb86-104">The Endpoint table is a supporting table that stores information about the endpoints that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="2bb86-105">表中的每条记录表示一个终结点。</span><span class="sxs-lookup"><span data-stu-id="2bb86-105">Each record in the table represents one endpoint.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2bb86-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="2bb86-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="2bb86-107"><strong>数据类型</strong></span><span class="sxs-lookup"><span data-stu-id="2bb86-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="2bb86-108"><strong>键/索引</strong></span><span class="sxs-lookup"><span data-stu-id="2bb86-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="2bb86-109"><strong>详细信息</strong></span><span class="sxs-lookup"><span data-stu-id="2bb86-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2bb86-110"><strong>EndpointKey</strong></span><span class="sxs-lookup"><span data-stu-id="2bb86-110"><strong>EndpointKey</strong></span></span></p></td>
<td><p><span data-ttu-id="2bb86-111">int</span><span class="sxs-lookup"><span data-stu-id="2bb86-111">int</span></span></p></td>
<td><p><span data-ttu-id="2bb86-112">Primary</span><span class="sxs-lookup"><span data-stu-id="2bb86-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="2bb86-113">标识此终结点的唯一号码。</span><span class="sxs-lookup"><span data-stu-id="2bb86-113">Unique number identifying this endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2bb86-114"><strong>名称</strong> - 按 WAN 链路进行筛选（筛选器位于图形右侧）。</span><span class="sxs-lookup"><span data-stu-id="2bb86-114"><strong>Name</strong></span></span></p></td>
<td><p><span data-ttu-id="2bb86-115">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="2bb86-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2bb86-116">唯一</span><span class="sxs-lookup"><span data-stu-id="2bb86-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="2bb86-117">终结点名称。</span><span class="sxs-lookup"><span data-stu-id="2bb86-117">Endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2bb86-118"><strong>OS</strong></span><span class="sxs-lookup"><span data-stu-id="2bb86-118"><strong>OS</strong></span></span></p></td>
<td><p><span data-ttu-id="2bb86-119">nvarchar</span><span class="sxs-lookup"><span data-stu-id="2bb86-119">nvarchar(128)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2bb86-120">终结点的操作系统 (OS)。</span><span class="sxs-lookup"><span data-stu-id="2bb86-120">Operating system (OS) of the endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2bb86-121"><strong>CPUName</strong></span><span class="sxs-lookup"><span data-stu-id="2bb86-121"><strong>CPUName</strong></span></span></p></td>
<td><p><span data-ttu-id="2bb86-122">nvarchar</span><span class="sxs-lookup"><span data-stu-id="2bb86-122">nvarchar(128)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2bb86-123">终结点的 CPU 名称。</span><span class="sxs-lookup"><span data-stu-id="2bb86-123">CPU name of the endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2bb86-124"><strong>CPUNumberOfCores</strong></span><span class="sxs-lookup"><span data-stu-id="2bb86-124"><strong>CPUNumberOfCores</strong></span></span></p></td>
<td><p><span data-ttu-id="2bb86-125">smallint</span><span class="sxs-lookup"><span data-stu-id="2bb86-125">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2bb86-126">终结点的 CPU 内核数。</span><span class="sxs-lookup"><span data-stu-id="2bb86-126">Number of CPU cores of the endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2bb86-127"><strong>CPUProcessorSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="2bb86-127"><strong>CPUProcessorSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="2bb86-128">int</span><span class="sxs-lookup"><span data-stu-id="2bb86-128">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2bb86-129">终结点的 CPU 处理器速度。</span><span class="sxs-lookup"><span data-stu-id="2bb86-129">CPU processor speed of the endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2bb86-130"><strong>VirtualizationFlag</strong></span><span class="sxs-lookup"><span data-stu-id="2bb86-130"><strong>VirtualizationFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="2bb86-131">tinyint</span><span class="sxs-lookup"><span data-stu-id="2bb86-131">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2bb86-132">指示系统是否在虚拟化环境中运行的位标志:</span><span class="sxs-lookup"><span data-stu-id="2bb86-132">Bit flag that indicates if the system is running in a virtualized environment:</span></span></p>
<ul>
<li><p><span data-ttu-id="2bb86-133">0x0000 –无</span><span class="sxs-lookup"><span data-stu-id="2bb86-133">0x0000 – None</span></span></p></li>
<li><p><span data-ttu-id="2bb86-134">0x0001-HyperV</span><span class="sxs-lookup"><span data-stu-id="2bb86-134">0x0001 – HyperV</span></span></p></li>
<li><p><span data-ttu-id="2bb86-135">0x0002-VMWare</span><span class="sxs-lookup"><span data-stu-id="2bb86-135">0x0002 – VMWare</span></span></p></li>
<li><p><span data-ttu-id="2bb86-136">0x0004-虚拟电脑</span><span class="sxs-lookup"><span data-stu-id="2bb86-136">0x0004 – Virtual PC</span></span></p></li>
<li><p><span data-ttu-id="2bb86-137">0x0008-Xen 电脑</span><span class="sxs-lookup"><span data-stu-id="2bb86-137">0x0008 – Xen PC</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

