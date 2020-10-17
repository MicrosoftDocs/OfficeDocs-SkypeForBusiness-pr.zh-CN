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
ms.openlocfilehash: fc67c4096cde54252cec432fd8ad2196b05c00e0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536939"
---
# <a name="devicedriver-table-in-lync-server-2013"></a><span data-ttu-id="373a3-102">Lync Server 2013 中的 DeviceDriver 表</span><span class="sxs-lookup"><span data-stu-id="373a3-102">DeviceDriver table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="373a3-103">_**上次修改的主题：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="373a3-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="373a3-p101">DeviceDriver 表是一个支持表。每条记录都代表捕获设备或呈现设备所使用的一个驱动程序。</span><span class="sxs-lookup"><span data-stu-id="373a3-p101">The DeviceDriver table is a supporting table. Each record represents a driver used by either a capture device or render device.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="373a3-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="373a3-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="373a3-107"><strong>数据类型</strong></span><span class="sxs-lookup"><span data-stu-id="373a3-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="373a3-108"><strong>键/索引</strong></span><span class="sxs-lookup"><span data-stu-id="373a3-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="373a3-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="373a3-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="373a3-110"><strong>DeviceDriverKey</strong></span><span class="sxs-lookup"><span data-stu-id="373a3-110"><strong>DeviceDriverKey</strong></span></span></p></td>
<td><p><span data-ttu-id="373a3-111">int</span><span class="sxs-lookup"><span data-stu-id="373a3-111">int</span></span></p></td>
<td><p><span data-ttu-id="373a3-112">主</span><span class="sxs-lookup"><span data-stu-id="373a3-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="373a3-113">用于标识此设备驱动程序记录的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="373a3-113">Unique number identifying this device driver record.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="373a3-114"><strong>DeviceDriver</strong></span><span class="sxs-lookup"><span data-stu-id="373a3-114"><strong>DeviceDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="373a3-115">varchar (256) </span><span class="sxs-lookup"><span data-stu-id="373a3-115">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="373a3-116">unique</span><span class="sxs-lookup"><span data-stu-id="373a3-116">unique</span></span></p></td>
<td><p><span data-ttu-id="373a3-117">设备驱动程序的名称。</span><span class="sxs-lookup"><span data-stu-id="373a3-117">Device driver name.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

