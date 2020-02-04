---
title: Lync Server 2013：Endpoint 表
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
ms.openlocfilehash: 11da225da1a8120f5de7ac21b3beb318326601f9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735582"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="endpoint-table-in-lync-server-2013"></a><span data-ttu-id="d56a5-102">Lync Server 2013 中的 Endpoint 表</span><span class="sxs-lookup"><span data-stu-id="d56a5-102">Endpoint table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d56a5-103">_**主题上次修改时间：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="d56a5-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="d56a5-104">终结点表是一个支持表，用于存储参与数据库中记录的会话的终结点的相关信息。</span><span class="sxs-lookup"><span data-stu-id="d56a5-104">The Endpoint table is a supporting table that stores information about the endpoints that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="d56a5-105">表中的每条记录表示一个终结点。</span><span class="sxs-lookup"><span data-stu-id="d56a5-105">Each record in the table represents one endpoint.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d56a5-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="d56a5-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="d56a5-107"><strong>数据类型</strong></span><span class="sxs-lookup"><span data-stu-id="d56a5-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="d56a5-108"><strong>键/索引</strong></span><span class="sxs-lookup"><span data-stu-id="d56a5-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="d56a5-109"><strong>详细信息</strong></span><span class="sxs-lookup"><span data-stu-id="d56a5-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d56a5-110"><strong>EndpointKey</strong></span><span class="sxs-lookup"><span data-stu-id="d56a5-110"><strong>EndpointKey</strong></span></span></p></td>
<td><p><span data-ttu-id="d56a5-111">int</span><span class="sxs-lookup"><span data-stu-id="d56a5-111">int</span></span></p></td>
<td><p><span data-ttu-id="d56a5-112">Primary</span><span class="sxs-lookup"><span data-stu-id="d56a5-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="d56a5-113">标识此终结点的唯一号码。</span><span class="sxs-lookup"><span data-stu-id="d56a5-113">Unique number identifying this endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d56a5-114"><strong>名称</strong> - 按 WAN 链路进行筛选（筛选器位于图形右侧）。</span><span class="sxs-lookup"><span data-stu-id="d56a5-114"><strong>Name</strong></span></span></p></td>
<td><p><span data-ttu-id="d56a5-115">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="d56a5-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d56a5-116">唯一</span><span class="sxs-lookup"><span data-stu-id="d56a5-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="d56a5-117">终结点名称。</span><span class="sxs-lookup"><span data-stu-id="d56a5-117">Endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d56a5-118"><strong>OS</strong></span><span class="sxs-lookup"><span data-stu-id="d56a5-118"><strong>OS</strong></span></span></p></td>
<td><p><span data-ttu-id="d56a5-119">nvarchar</span><span class="sxs-lookup"><span data-stu-id="d56a5-119">nvarchar(128)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d56a5-120">终结点的操作系统（OS）。</span><span class="sxs-lookup"><span data-stu-id="d56a5-120">Operating system (OS) of the endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d56a5-121"><strong>CPUName</strong></span><span class="sxs-lookup"><span data-stu-id="d56a5-121"><strong>CPUName</strong></span></span></p></td>
<td><p><span data-ttu-id="d56a5-122">nvarchar</span><span class="sxs-lookup"><span data-stu-id="d56a5-122">nvarchar(128)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d56a5-123">终结点的 CPU 名称。</span><span class="sxs-lookup"><span data-stu-id="d56a5-123">CPU name of the endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d56a5-124"><strong>CPUNumberOfCores</strong></span><span class="sxs-lookup"><span data-stu-id="d56a5-124"><strong>CPUNumberOfCores</strong></span></span></p></td>
<td><p><span data-ttu-id="d56a5-125">smallint</span><span class="sxs-lookup"><span data-stu-id="d56a5-125">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d56a5-126">终结点的 CPU 内核数。</span><span class="sxs-lookup"><span data-stu-id="d56a5-126">Number of CPU cores of the endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d56a5-127"><strong>CPUProcessorSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="d56a5-127"><strong>CPUProcessorSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="d56a5-128">int</span><span class="sxs-lookup"><span data-stu-id="d56a5-128">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d56a5-129">终结点的 CPU 处理器速度。</span><span class="sxs-lookup"><span data-stu-id="d56a5-129">CPU processor speed of the endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d56a5-130"><strong>VirtualizationFlag</strong></span><span class="sxs-lookup"><span data-stu-id="d56a5-130"><strong>VirtualizationFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="d56a5-131">tinyint</span><span class="sxs-lookup"><span data-stu-id="d56a5-131">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d56a5-132">指示系统是否在虚拟化环境中运行的位标志：</span><span class="sxs-lookup"><span data-stu-id="d56a5-132">Bit flag that indicates if the system is running in a virtualized environment:</span></span></p>
<ul>
<li><p><span data-ttu-id="d56a5-133">0x0000 –无</span><span class="sxs-lookup"><span data-stu-id="d56a5-133">0x0000 – None</span></span></p></li>
<li><p><span data-ttu-id="d56a5-134">0x0001-HyperV</span><span class="sxs-lookup"><span data-stu-id="d56a5-134">0x0001 – HyperV</span></span></p></li>
<li><p><span data-ttu-id="d56a5-135">0x0002-VMWare</span><span class="sxs-lookup"><span data-stu-id="d56a5-135">0x0002 – VMWare</span></span></p></li>
<li><p><span data-ttu-id="d56a5-136">0x0004-虚拟电脑</span><span class="sxs-lookup"><span data-stu-id="d56a5-136">0x0004 – Virtual PC</span></span></p></li>
<li><p><span data-ttu-id="d56a5-137">0x0008-Xen 电脑</span><span class="sxs-lookup"><span data-stu-id="d56a5-137">0x0008 – Xen PC</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

