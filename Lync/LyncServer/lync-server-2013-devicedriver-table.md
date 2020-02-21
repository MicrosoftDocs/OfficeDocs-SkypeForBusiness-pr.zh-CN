---
title: Lync Server 2013： DeviceDriver 表
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
ms.openlocfilehash: 2813ac26bbfd21aa35dbe71c9c4477e8107b8967
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214379"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="devicedriver-table-in-lync-server-2013"></a><span data-ttu-id="531a5-102">Lync Server 2013 中的 DeviceDriver 表</span><span class="sxs-lookup"><span data-stu-id="531a5-102">DeviceDriver table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="531a5-103">_**上次修改的主题：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="531a5-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="531a5-p101">DeviceDriver 表是一个支持表。每条记录都代表捕获设备或呈现设备所使用的一个驱动程序。</span><span class="sxs-lookup"><span data-stu-id="531a5-p101">The DeviceDriver table is a supporting table. Each record represents a driver used by either a capture device or render device.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="531a5-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="531a5-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="531a5-107"><strong>数据类型</strong></span><span class="sxs-lookup"><span data-stu-id="531a5-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="531a5-108"><strong>键/索引</strong></span><span class="sxs-lookup"><span data-stu-id="531a5-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="531a5-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="531a5-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="531a5-110"><strong>DeviceDriverKey</strong></span><span class="sxs-lookup"><span data-stu-id="531a5-110"><strong>DeviceDriverKey</strong></span></span></p></td>
<td><p><span data-ttu-id="531a5-111">int</span><span class="sxs-lookup"><span data-stu-id="531a5-111">int</span></span></p></td>
<td><p><span data-ttu-id="531a5-112">主</span><span class="sxs-lookup"><span data-stu-id="531a5-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="531a5-113">用于标识此设备驱动程序记录的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="531a5-113">Unique number identifying this device driver record.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="531a5-114"><strong>DeviceDriver</strong></span><span class="sxs-lookup"><span data-stu-id="531a5-114"><strong>DeviceDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="531a5-115">varchar （256）</span><span class="sxs-lookup"><span data-stu-id="531a5-115">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="531a5-116">unique</span><span class="sxs-lookup"><span data-stu-id="531a5-116">unique</span></span></p></td>
<td><p><span data-ttu-id="531a5-117">设备驱动程序的名称。</span><span class="sxs-lookup"><span data-stu-id="531a5-117">Device driver name.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

