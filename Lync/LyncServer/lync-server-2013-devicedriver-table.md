---
title: Lync Server 2013：DeviceDriver 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DeviceDriver table
ms:assetid: ca91a0b4-98c0-49f6-af9d-7d0f8ac75f1a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398844(v=OCS.15)
ms:contentKeyID: 48185449
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ea4ab9ad8b2eda5388791c98c1e1da90d9bd5c65
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830416"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="devicedriver-table-in-lync-server-2013"></a><span data-ttu-id="f42a3-102">Lync Server 2013 中的 DeviceDriver 表</span><span class="sxs-lookup"><span data-stu-id="f42a3-102">DeviceDriver table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f42a3-103">_**主题上次修改时间:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="f42a3-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="f42a3-104">DeviceDriver 表是支持表。</span><span class="sxs-lookup"><span data-stu-id="f42a3-104">The DeviceDriver table is a supporting table.</span></span> <span data-ttu-id="f42a3-105">每个记录都表示一个由捕获设备或呈现设备使用的驱动程序。</span><span class="sxs-lookup"><span data-stu-id="f42a3-105">Each record represents a driver used by either a capture device or render device.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f42a3-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="f42a3-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="f42a3-107"><strong>数据类型</strong></span><span class="sxs-lookup"><span data-stu-id="f42a3-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="f42a3-108"><strong>键/索引</strong></span><span class="sxs-lookup"><span data-stu-id="f42a3-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="f42a3-109"><strong>详细信息</strong></span><span class="sxs-lookup"><span data-stu-id="f42a3-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f42a3-110"><strong>DeviceDriverKey</strong></span><span class="sxs-lookup"><span data-stu-id="f42a3-110"><strong>DeviceDriverKey</strong></span></span></p></td>
<td><p><span data-ttu-id="f42a3-111">int</span><span class="sxs-lookup"><span data-stu-id="f42a3-111">int</span></span></p></td>
<td><p><span data-ttu-id="f42a3-112">Primary</span><span class="sxs-lookup"><span data-stu-id="f42a3-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="f42a3-113">标识此设备驱动程序记录的唯一号码。</span><span class="sxs-lookup"><span data-stu-id="f42a3-113">Unique number identifying this device driver record.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f42a3-114"><strong>DeviceDriver</strong></span><span class="sxs-lookup"><span data-stu-id="f42a3-114"><strong>DeviceDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="f42a3-115">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="f42a3-115">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f42a3-116">唯一</span><span class="sxs-lookup"><span data-stu-id="f42a3-116">unique</span></span></p></td>
<td><p><span data-ttu-id="f42a3-117">设备驱动程序名称。</span><span class="sxs-lookup"><span data-stu-id="f42a3-117">Device driver name.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

