---
title: Lync Server 2013：终结点表
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
ms.openlocfilehash: 201e2ae3b44f59f0edb128f58af6c18e18e51931
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042229"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="endpoint-table-in-lync-server-2013"></a><span data-ttu-id="adf04-102">Lync Server 2013 中的终结点表</span><span class="sxs-lookup"><span data-stu-id="adf04-102">Endpoint table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="adf04-103">_**上次修改的主题：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="adf04-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="adf04-104">终结点表是一个支持表，它存储有关参与在数据库中记录的会话的终结点的信息。</span><span class="sxs-lookup"><span data-stu-id="adf04-104">The Endpoint table is a supporting table that stores information about the endpoints that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="adf04-105">表中的每条记录代表一个终结点。</span><span class="sxs-lookup"><span data-stu-id="adf04-105">Each record in the table represents one endpoint.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="adf04-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="adf04-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="adf04-107"><strong>数据类型</strong></span><span class="sxs-lookup"><span data-stu-id="adf04-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="adf04-108"><strong>键/索引</strong></span><span class="sxs-lookup"><span data-stu-id="adf04-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="adf04-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="adf04-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="adf04-110"><strong>EndpointKey</strong></span><span class="sxs-lookup"><span data-stu-id="adf04-110"><strong>EndpointKey</strong></span></span></p></td>
<td><p><span data-ttu-id="adf04-111">int</span><span class="sxs-lookup"><span data-stu-id="adf04-111">int</span></span></p></td>
<td><p><span data-ttu-id="adf04-112">主</span><span class="sxs-lookup"><span data-stu-id="adf04-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="adf04-113">标识此终结点的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="adf04-113">Unique number identifying this endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="adf04-114"><strong>名称</strong></span><span class="sxs-lookup"><span data-stu-id="adf04-114"><strong>Name</strong></span></span></p></td>
<td><p><span data-ttu-id="adf04-115">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="adf04-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="adf04-116">独特</span><span class="sxs-lookup"><span data-stu-id="adf04-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="adf04-117">终结点名称。</span><span class="sxs-lookup"><span data-stu-id="adf04-117">Endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="adf04-118"><strong>OS</strong></span><span class="sxs-lookup"><span data-stu-id="adf04-118"><strong>OS</strong></span></span></p></td>
<td><p><span data-ttu-id="adf04-119">nvarchar</span><span class="sxs-lookup"><span data-stu-id="adf04-119">nvarchar(128)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="adf04-120">终结点的操作系统（OS）。</span><span class="sxs-lookup"><span data-stu-id="adf04-120">Operating system (OS) of the endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="adf04-121"><strong>CPUName</strong></span><span class="sxs-lookup"><span data-stu-id="adf04-121"><strong>CPUName</strong></span></span></p></td>
<td><p><span data-ttu-id="adf04-122">nvarchar</span><span class="sxs-lookup"><span data-stu-id="adf04-122">nvarchar(128)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="adf04-123">终结点的 CPU 名称。</span><span class="sxs-lookup"><span data-stu-id="adf04-123">CPU name of the endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="adf04-124"><strong>CPUNumberOfCores</strong></span><span class="sxs-lookup"><span data-stu-id="adf04-124"><strong>CPUNumberOfCores</strong></span></span></p></td>
<td><p><span data-ttu-id="adf04-125">smallint</span><span class="sxs-lookup"><span data-stu-id="adf04-125">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="adf04-126">终结点的 CPU 内核数。</span><span class="sxs-lookup"><span data-stu-id="adf04-126">Number of CPU cores of the endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="adf04-127"><strong>CPUProcessorSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="adf04-127"><strong>CPUProcessorSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="adf04-128">int</span><span class="sxs-lookup"><span data-stu-id="adf04-128">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="adf04-129">终结点的 CPU 处理器速度。</span><span class="sxs-lookup"><span data-stu-id="adf04-129">CPU processor speed of the endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="adf04-130"><strong>VirtualizationFlag</strong></span><span class="sxs-lookup"><span data-stu-id="adf04-130"><strong>VirtualizationFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="adf04-131">tinyint</span><span class="sxs-lookup"><span data-stu-id="adf04-131">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="adf04-132">表示系统是否在虚拟化环境中运行的位标志：</span><span class="sxs-lookup"><span data-stu-id="adf04-132">Bit flag that indicates if the system is running in a virtualized environment:</span></span></p>
<ul>
<li><p><span data-ttu-id="adf04-133">0x0000 –无</span><span class="sxs-lookup"><span data-stu-id="adf04-133">0x0000 – None</span></span></p></li>
<li><p><span data-ttu-id="adf04-134">0x0001 – HyperV</span><span class="sxs-lookup"><span data-stu-id="adf04-134">0x0001 – HyperV</span></span></p></li>
<li><p><span data-ttu-id="adf04-135">0x0002 – VMWare</span><span class="sxs-lookup"><span data-stu-id="adf04-135">0x0002 – VMWare</span></span></p></li>
<li><p><span data-ttu-id="adf04-136">0x0004 – Virtual 电脑</span><span class="sxs-lookup"><span data-stu-id="adf04-136">0x0004 – Virtual PC</span></span></p></li>
<li><p><span data-ttu-id="adf04-137">0x0008 – Xen PC</span><span class="sxs-lookup"><span data-stu-id="adf04-137">0x0008 – Xen PC</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

