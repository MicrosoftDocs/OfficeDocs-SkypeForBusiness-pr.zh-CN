---
title: Lync Server 2013：Server 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Server table
ms:assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398801(v=OCS.15)
ms:contentKeyID: 48184890
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 363c07a6ab3be8f5acdf0286a4223f96a8bd3700
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822004"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-table-in-lync-server-2013"></a><span data-ttu-id="1c682-102">Lync Server 2013 中的 Server  表</span><span class="sxs-lookup"><span data-stu-id="1c682-102">Server table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1c682-103">_**主题上次修改时间:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="1c682-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="1c682-104">服务器表是支持表。</span><span class="sxs-lookup"><span data-stu-id="1c682-104">The Server table is a supporting table.</span></span> <span data-ttu-id="1c682-105">每条记录代表一台服务器。</span><span class="sxs-lookup"><span data-stu-id="1c682-105">Each record represents one server.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1c682-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="1c682-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="1c682-107"><strong>数据类型</strong></span><span class="sxs-lookup"><span data-stu-id="1c682-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="1c682-108"><strong>键/索引</strong></span><span class="sxs-lookup"><span data-stu-id="1c682-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="1c682-109"><strong>详细信息</strong></span><span class="sxs-lookup"><span data-stu-id="1c682-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1c682-110"><strong>ServerKey</strong></span><span class="sxs-lookup"><span data-stu-id="1c682-110"><strong>ServerKey</strong></span></span></p></td>
<td><p><span data-ttu-id="1c682-111">int</span><span class="sxs-lookup"><span data-stu-id="1c682-111">int</span></span></p></td>
<td><p><span data-ttu-id="1c682-112">Primary</span><span class="sxs-lookup"><span data-stu-id="1c682-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="1c682-113">标识服务器的唯一号码。</span><span class="sxs-lookup"><span data-stu-id="1c682-113">Unique number identifying the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1c682-114"><strong>FQDNOrIP</strong></span><span class="sxs-lookup"><span data-stu-id="1c682-114"><strong>FQDNOrIP</strong></span></span></p></td>
<td><p><span data-ttu-id="1c682-115">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="1c682-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1c682-116">食指</span><span class="sxs-lookup"><span data-stu-id="1c682-116">index</span></span></p></td>
<td><p><span data-ttu-id="1c682-117">MAC 地址字符串。</span><span class="sxs-lookup"><span data-stu-id="1c682-117">MAC address string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1c682-118"><strong>ServerType</strong></span><span class="sxs-lookup"><span data-stu-id="1c682-118"><strong>ServerType</strong></span></span></p></td>
<td><p><span data-ttu-id="1c682-119">int</span><span class="sxs-lookup"><span data-stu-id="1c682-119">int</span></span></p></td>
<td><p><span data-ttu-id="1c682-120">外表</span><span class="sxs-lookup"><span data-stu-id="1c682-120">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1c682-121">1: 中介服务器</span><span class="sxs-lookup"><span data-stu-id="1c682-121">1: Mediation Server</span></span></p>
<p><span data-ttu-id="1c682-122">2: a/V 会议 Server16394: A/V 边缘 service32769: Gateway</span><span class="sxs-lookup"><span data-stu-id="1c682-122">2: A/V Conferencing Server16394: A/V Edge service32769: Gateway</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1c682-123"><strong>PoolName</strong></span><span class="sxs-lookup"><span data-stu-id="1c682-123"><strong>PoolName</strong></span></span></p></td>
<td><p><span data-ttu-id="1c682-124">nvarchar (512)</span><span class="sxs-lookup"><span data-stu-id="1c682-124">nvarchar(512)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1c682-125">服务器所属的池。</span><span class="sxs-lookup"><span data-stu-id="1c682-125">Pool the server belongs to.</span></span> <span data-ttu-id="1c682-126">仅适用于 A/V 会议服务器。</span><span class="sxs-lookup"><span data-stu-id="1c682-126">Only applicable for the A/V Conferencing Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1c682-127"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="1c682-127"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="1c682-128">datetime</span><span class="sxs-lookup"><span data-stu-id="1c682-128">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1c682-129">仅供内部使用。</span><span class="sxs-lookup"><span data-stu-id="1c682-129">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

