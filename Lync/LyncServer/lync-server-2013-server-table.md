---
title: Lync Server 2013： Server 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server table
ms:assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398801(v=OCS.15)
ms:contentKeyID: 48184890
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b1a400387d88637fc45bcd3342ebbadb2bec6edf
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049114"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-table-in-lync-server-2013"></a><span data-ttu-id="7fca2-102">Lync Server 2013 中的服务器表</span><span class="sxs-lookup"><span data-stu-id="7fca2-102">Server table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7fca2-103">_**上次修改的主题：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="7fca2-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="7fca2-p101">Server 表是一个支持表。每个记录表示一台服务器。</span><span class="sxs-lookup"><span data-stu-id="7fca2-p101">The Server table is a supporting table. Each record represents one server.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7fca2-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="7fca2-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="7fca2-107"><strong>数据类型</strong></span><span class="sxs-lookup"><span data-stu-id="7fca2-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="7fca2-108"><strong>键/索引</strong></span><span class="sxs-lookup"><span data-stu-id="7fca2-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="7fca2-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="7fca2-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7fca2-110"><strong>ServerKey</strong></span><span class="sxs-lookup"><span data-stu-id="7fca2-110"><strong>ServerKey</strong></span></span></p></td>
<td><p><span data-ttu-id="7fca2-111">int</span><span class="sxs-lookup"><span data-stu-id="7fca2-111">int</span></span></p></td>
<td><p><span data-ttu-id="7fca2-112">主</span><span class="sxs-lookup"><span data-stu-id="7fca2-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="7fca2-113">标识服务器的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="7fca2-113">Unique number identifying the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7fca2-114"><strong>FQDNOrIP</strong></span><span class="sxs-lookup"><span data-stu-id="7fca2-114"><strong>FQDNOrIP</strong></span></span></p></td>
<td><p><span data-ttu-id="7fca2-115">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="7fca2-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7fca2-116">index</span><span class="sxs-lookup"><span data-stu-id="7fca2-116">index</span></span></p></td>
<td><p><span data-ttu-id="7fca2-117">MAC 地址字符串。</span><span class="sxs-lookup"><span data-stu-id="7fca2-117">MAC address string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7fca2-118"><strong>ServerType</strong></span><span class="sxs-lookup"><span data-stu-id="7fca2-118"><strong>ServerType</strong></span></span></p></td>
<td><p><span data-ttu-id="7fca2-119">int</span><span class="sxs-lookup"><span data-stu-id="7fca2-119">int</span></span></p></td>
<td><p><span data-ttu-id="7fca2-120">对外</span><span class="sxs-lookup"><span data-stu-id="7fca2-120">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7fca2-121">1：中介服务器</span><span class="sxs-lookup"><span data-stu-id="7fca2-121">1: Mediation Server</span></span></p>
<p><span data-ttu-id="7fca2-122">2：A/V 会议服务器 16394：A/V 边缘服务 32769：网关</span><span class="sxs-lookup"><span data-stu-id="7fca2-122">2: A/V Conferencing Server16394: A/V Edge service32769: Gateway</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7fca2-123"><strong>PoolName</strong></span><span class="sxs-lookup"><span data-stu-id="7fca2-123"><strong>PoolName</strong></span></span></p></td>
<td><p><span data-ttu-id="7fca2-124">nvarchar （512）</span><span class="sxs-lookup"><span data-stu-id="7fca2-124">nvarchar(512)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7fca2-p102">服务器所属的池。仅适用于 A/V 会议服务器。</span><span class="sxs-lookup"><span data-stu-id="7fca2-p102">Pool the server belongs to. Only applicable for the A/V Conferencing Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7fca2-127"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="7fca2-127"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="7fca2-128">datetime</span><span class="sxs-lookup"><span data-stu-id="7fca2-128">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7fca2-129">仅供内部使用。</span><span class="sxs-lookup"><span data-stu-id="7fca2-129">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

