---
title: Lync Server 2013： DeviceDriver 表
description: Lync Server 2013： DeviceDriver 表。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DeviceDriver table
ms:assetid: ca91a0b4-98c0-49f6-af9d-7d0f8ac75f1a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398844(v=OCS.15)
ms:contentKeyID: 48185449
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3d81e2e27ff5196112c6057c429f924e5b1c3e4b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565968"
---
# <a name="devicedriver-table-in-lync-server-2013"></a><span data-ttu-id="aa010-103">Lync Server 2013 中的 DeviceDriver 表</span><span class="sxs-lookup"><span data-stu-id="aa010-103">DeviceDriver table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aa010-104">_**上次修改的主题：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="aa010-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="aa010-p101">DeviceDriver 表是一个支持表。每条记录都代表捕获设备或呈现设备所使用的一个驱动程序。</span><span class="sxs-lookup"><span data-stu-id="aa010-p101">The DeviceDriver table is a supporting table. Each record represents a driver used by either a capture device or render device.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="aa010-107"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="aa010-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="aa010-108"><strong>数据类型</strong></span><span class="sxs-lookup"><span data-stu-id="aa010-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="aa010-109"><strong>键/索引</strong></span><span class="sxs-lookup"><span data-stu-id="aa010-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="aa010-110"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="aa010-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aa010-111"><strong>DeviceDriverKey</strong></span><span class="sxs-lookup"><span data-stu-id="aa010-111"><strong>DeviceDriverKey</strong></span></span></p></td>
<td><p><span data-ttu-id="aa010-112">int</span><span class="sxs-lookup"><span data-stu-id="aa010-112">int</span></span></p></td>
<td><p><span data-ttu-id="aa010-113">主</span><span class="sxs-lookup"><span data-stu-id="aa010-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="aa010-114">用于标识此设备驱动程序记录的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="aa010-114">Unique number identifying this device driver record.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa010-115"><strong>DeviceDriver</strong></span><span class="sxs-lookup"><span data-stu-id="aa010-115"><strong>DeviceDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="aa010-116">varchar (256) </span><span class="sxs-lookup"><span data-stu-id="aa010-116">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="aa010-117">unique</span><span class="sxs-lookup"><span data-stu-id="aa010-117">unique</span></span></p></td>
<td><p><span data-ttu-id="aa010-118">设备驱动程序的名称。</span><span class="sxs-lookup"><span data-stu-id="aa010-118">Device driver name.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

