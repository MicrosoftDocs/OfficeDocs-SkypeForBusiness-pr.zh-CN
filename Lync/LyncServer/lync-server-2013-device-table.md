---
title: Lync Server 2013：Device 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Device table
ms:assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398930(v=OCS.15)
ms:contentKeyID: 48185544
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 974898f6c3fa96dd9356a0a9eed1e3fab09d288b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830430"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="device-table-in-lync-server-2013"></a><span data-ttu-id="e84fe-102">Lync Server 2013 中的 Device 表</span><span class="sxs-lookup"><span data-stu-id="e84fe-102">Device table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e84fe-103">_**主题上次修改时间:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="e84fe-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="e84fe-104">Device 表是一个支持表, 用于存储有关各种捕获或呈现设备的信息。</span><span class="sxs-lookup"><span data-stu-id="e84fe-104">The Device table is a supporting table that stores information about the various capture or render devices.</span></span> <span data-ttu-id="e84fe-105">表中的每条记录表示一个设备。</span><span class="sxs-lookup"><span data-stu-id="e84fe-105">Each record in the table represents one device.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e84fe-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="e84fe-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="e84fe-107"><strong>数据类型</strong></span><span class="sxs-lookup"><span data-stu-id="e84fe-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="e84fe-108"><strong>键/索引</strong></span><span class="sxs-lookup"><span data-stu-id="e84fe-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="e84fe-109"><strong>详细信息</strong></span><span class="sxs-lookup"><span data-stu-id="e84fe-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e84fe-110"><strong>DeviceKey</strong></span><span class="sxs-lookup"><span data-stu-id="e84fe-110"><strong>DeviceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="e84fe-111">int</span><span class="sxs-lookup"><span data-stu-id="e84fe-111">int</span></span></p></td>
<td><p><span data-ttu-id="e84fe-112">Primary</span><span class="sxs-lookup"><span data-stu-id="e84fe-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="e84fe-113">标识此设备的唯一号码。</span><span class="sxs-lookup"><span data-stu-id="e84fe-113">Unique number identifying this device.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e84fe-114"><strong>DeviceName</strong></span><span class="sxs-lookup"><span data-stu-id="e84fe-114"><strong>DeviceName</strong></span></span></p></td>
<td><p><span data-ttu-id="e84fe-115">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e84fe-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e84fe-116">DeviceName + DeviceType 是唯一的</span><span class="sxs-lookup"><span data-stu-id="e84fe-116">DeviceName + DeviceType is unique</span></span></p></td>
<td><p><span data-ttu-id="e84fe-117">设备名称。</span><span class="sxs-lookup"><span data-stu-id="e84fe-117">Device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e84fe-118"><strong>DeviceType</strong></span><span class="sxs-lookup"><span data-stu-id="e84fe-118"><strong>DeviceType</strong></span></span></p></td>
<td><p><span data-ttu-id="e84fe-119">bit</span><span class="sxs-lookup"><span data-stu-id="e84fe-119">bit</span></span></p></td>
<td><p><span data-ttu-id="e84fe-120">DeviceName + DeviceType 是唯一的</span><span class="sxs-lookup"><span data-stu-id="e84fe-120">DeviceName + DeviceType is unique</span></span></p></td>
<td><p><span data-ttu-id="e84fe-121">设备类型。</span><span class="sxs-lookup"><span data-stu-id="e84fe-121">Device type.</span></span> <span data-ttu-id="e84fe-122">1是捕获设备, 0 是呈现设备。</span><span class="sxs-lookup"><span data-stu-id="e84fe-122">1 is a capture device, 0 is a render device.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

