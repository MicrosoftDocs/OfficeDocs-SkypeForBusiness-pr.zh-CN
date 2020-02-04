---
title: Lync Server 2013：Server 表
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
ms.openlocfilehash: c1d0cdb5733e6fc6e21d1dcda1fff6214332de6b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732412"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-table-in-lync-server-2013"></a><span data-ttu-id="78fde-102">Lync Server 2013 中的 Server  表</span><span class="sxs-lookup"><span data-stu-id="78fde-102">Server table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="78fde-103">_**主题上次修改时间：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="78fde-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="78fde-104">服务器表是支持表。</span><span class="sxs-lookup"><span data-stu-id="78fde-104">The Server table is a supporting table.</span></span> <span data-ttu-id="78fde-105">每条记录代表一台服务器。</span><span class="sxs-lookup"><span data-stu-id="78fde-105">Each record represents one server.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="78fde-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="78fde-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="78fde-107"><strong>数据类型</strong></span><span class="sxs-lookup"><span data-stu-id="78fde-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="78fde-108"><strong>键/索引</strong></span><span class="sxs-lookup"><span data-stu-id="78fde-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="78fde-109"><strong>详细信息</strong></span><span class="sxs-lookup"><span data-stu-id="78fde-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="78fde-110"><strong>ServerKey</strong></span><span class="sxs-lookup"><span data-stu-id="78fde-110"><strong>ServerKey</strong></span></span></p></td>
<td><p><span data-ttu-id="78fde-111">int</span><span class="sxs-lookup"><span data-stu-id="78fde-111">int</span></span></p></td>
<td><p><span data-ttu-id="78fde-112">Primary</span><span class="sxs-lookup"><span data-stu-id="78fde-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="78fde-113">标识服务器的唯一号码。</span><span class="sxs-lookup"><span data-stu-id="78fde-113">Unique number identifying the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78fde-114"><strong>FQDNOrIP</strong></span><span class="sxs-lookup"><span data-stu-id="78fde-114"><strong>FQDNOrIP</strong></span></span></p></td>
<td><p><span data-ttu-id="78fde-115">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="78fde-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="78fde-116">食指</span><span class="sxs-lookup"><span data-stu-id="78fde-116">index</span></span></p></td>
<td><p><span data-ttu-id="78fde-117">MAC 地址字符串。</span><span class="sxs-lookup"><span data-stu-id="78fde-117">MAC address string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78fde-118"><strong>ServerType</strong></span><span class="sxs-lookup"><span data-stu-id="78fde-118"><strong>ServerType</strong></span></span></p></td>
<td><p><span data-ttu-id="78fde-119">int</span><span class="sxs-lookup"><span data-stu-id="78fde-119">int</span></span></p></td>
<td><p><span data-ttu-id="78fde-120">外表</span><span class="sxs-lookup"><span data-stu-id="78fde-120">Foreign</span></span></p></td>
<td><p><span data-ttu-id="78fde-121">1：中介服务器</span><span class="sxs-lookup"><span data-stu-id="78fde-121">1: Mediation Server</span></span></p>
<p><span data-ttu-id="78fde-122">2： a/V 会议 Server16394： A/V 边缘 service32769： Gateway</span><span class="sxs-lookup"><span data-stu-id="78fde-122">2: A/V Conferencing Server16394: A/V Edge service32769: Gateway</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78fde-123"><strong>PoolName</strong></span><span class="sxs-lookup"><span data-stu-id="78fde-123"><strong>PoolName</strong></span></span></p></td>
<td><p><span data-ttu-id="78fde-124">nvarchar （512）</span><span class="sxs-lookup"><span data-stu-id="78fde-124">nvarchar(512)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="78fde-125">服务器所属的池。</span><span class="sxs-lookup"><span data-stu-id="78fde-125">Pool the server belongs to.</span></span> <span data-ttu-id="78fde-126">仅适用于 A/V 会议服务器。</span><span class="sxs-lookup"><span data-stu-id="78fde-126">Only applicable for the A/V Conferencing Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78fde-127"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="78fde-127"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="78fde-128">datetime</span><span class="sxs-lookup"><span data-stu-id="78fde-128">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="78fde-129">仅供内部使用。</span><span class="sxs-lookup"><span data-stu-id="78fde-129">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

