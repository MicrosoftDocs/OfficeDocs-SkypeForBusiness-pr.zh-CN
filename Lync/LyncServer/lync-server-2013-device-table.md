---
title: Lync Server 2013：设备表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Device table
ms:assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398930(v=OCS.15)
ms:contentKeyID: 48185544
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1040642874d2963292744eb2543c9ee265440fd2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197975"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="device-table-in-lync-server-2013"></a><span data-ttu-id="3c391-102">Lync Server 2013 中的设备表</span><span class="sxs-lookup"><span data-stu-id="3c391-102">Device table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3c391-103">_**上次修改的主题：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="3c391-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="3c391-p101">Device 表是一个支持表，用于存储有关各种捕获或呈现设备的信息。该表中的每个记录都代表一台设备。</span><span class="sxs-lookup"><span data-stu-id="3c391-p101">The Device table is a supporting table that stores information about the various capture or render devices. Each record in the table represents one device.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3c391-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="3c391-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="3c391-107"><strong>数据类型</strong></span><span class="sxs-lookup"><span data-stu-id="3c391-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="3c391-108"><strong>键/索引</strong></span><span class="sxs-lookup"><span data-stu-id="3c391-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="3c391-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="3c391-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3c391-110"><strong>DeviceKey</strong></span><span class="sxs-lookup"><span data-stu-id="3c391-110"><strong>DeviceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="3c391-111">int</span><span class="sxs-lookup"><span data-stu-id="3c391-111">int</span></span></p></td>
<td><p><span data-ttu-id="3c391-112">主</span><span class="sxs-lookup"><span data-stu-id="3c391-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="3c391-113">标识此设备的唯一数字。</span><span class="sxs-lookup"><span data-stu-id="3c391-113">Unique number identifying this device.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c391-114"><strong>DeviceName</strong></span><span class="sxs-lookup"><span data-stu-id="3c391-114"><strong>DeviceName</strong></span></span></p></td>
<td><p><span data-ttu-id="3c391-115">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="3c391-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3c391-116">DeviceName + DeviceType 是唯一的</span><span class="sxs-lookup"><span data-stu-id="3c391-116">DeviceName + DeviceType is unique</span></span></p></td>
<td><p><span data-ttu-id="3c391-117">设备名称。</span><span class="sxs-lookup"><span data-stu-id="3c391-117">Device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c391-118"><strong>DeviceType</strong></span><span class="sxs-lookup"><span data-stu-id="3c391-118"><strong>DeviceType</strong></span></span></p></td>
<td><p><span data-ttu-id="3c391-119">位</span><span class="sxs-lookup"><span data-stu-id="3c391-119">bit</span></span></p></td>
<td><p><span data-ttu-id="3c391-120">DeviceName + DeviceType 是唯一的</span><span class="sxs-lookup"><span data-stu-id="3c391-120">DeviceName + DeviceType is unique</span></span></p></td>
<td><p><span data-ttu-id="3c391-p102">设备类型。1 是捕获设备。0 是呈现设备。</span><span class="sxs-lookup"><span data-stu-id="3c391-p102">Device type. 1 is a capture device, 0 is a render device.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

