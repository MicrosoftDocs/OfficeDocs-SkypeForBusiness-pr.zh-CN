---
title: Lync Server 2013：设备表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Devices table
ms:assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398351(v=OCS.15)
ms:contentKeyID: 48184169
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8906519253445ea67f3fa674a9a1315f8f6cf18b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213498"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="devices-table-in-lync-server-2013"></a><span data-ttu-id="53d23-102">Lync Server 2013 中的 "设备" 表</span><span class="sxs-lookup"><span data-stu-id="53d23-102">Devices table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="53d23-103">_**上次修改的主题：** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="53d23-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="53d23-p101">Devices 表是一个支持表。每条记录存储有关一个设备（桌面电话）的信息。</span><span class="sxs-lookup"><span data-stu-id="53d23-p101">The Devices table is a supporting table. Each record stores information about one device (desk phone).</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="53d23-106">列</span><span class="sxs-lookup"><span data-stu-id="53d23-106">Column</span></span></th>
<th><span data-ttu-id="53d23-107">数据类型</span><span class="sxs-lookup"><span data-stu-id="53d23-107">Data Type</span></span></th>
<th><span data-ttu-id="53d23-108">键/索引</span><span class="sxs-lookup"><span data-stu-id="53d23-108">Key/Index</span></span></th>
<th><span data-ttu-id="53d23-109">详细信息</span><span class="sxs-lookup"><span data-stu-id="53d23-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="53d23-110"><strong>DeviceId</strong></span><span class="sxs-lookup"><span data-stu-id="53d23-110"><strong>DeviceId</strong></span></span></p></td>
<td><p><span data-ttu-id="53d23-111">int</span><span class="sxs-lookup"><span data-stu-id="53d23-111">int</span></span></p></td>
<td><p><span data-ttu-id="53d23-112">主</span><span class="sxs-lookup"><span data-stu-id="53d23-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="53d23-113">用于标识此硬件版本的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="53d23-113">Unique number identifying this hardware version.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d23-114"><strong>ManufacturerId</strong></span><span class="sxs-lookup"><span data-stu-id="53d23-114"><strong>ManufacturerId</strong></span></span></p></td>
<td><p><span data-ttu-id="53d23-115">int</span><span class="sxs-lookup"><span data-stu-id="53d23-115">int</span></span></p></td>
<td><p><span data-ttu-id="53d23-116">对外</span><span class="sxs-lookup"><span data-stu-id="53d23-116">Foreign</span></span></p></td>
<td><p><span data-ttu-id="53d23-117">此设备的制造商。</span><span class="sxs-lookup"><span data-stu-id="53d23-117">Manufacturer of this device.</span></span> <span data-ttu-id="53d23-118">有关详细信息，请参阅<a href="lync-server-2013-manufacturers-table.md">Lync Server 2013 中的制造商表</a>。</span><span class="sxs-lookup"><span data-stu-id="53d23-118">See the <a href="lync-server-2013-manufacturers-table.md">Manufacturers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d23-119"><strong>HardwareVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="53d23-119"><strong>HardwareVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="53d23-120">int</span><span class="sxs-lookup"><span data-stu-id="53d23-120">int</span></span></p></td>
<td><p><span data-ttu-id="53d23-121">对外</span><span class="sxs-lookup"><span data-stu-id="53d23-121">Foreign</span></span></p></td>
<td><p><span data-ttu-id="53d23-122">此设备的硬件版本。</span><span class="sxs-lookup"><span data-stu-id="53d23-122">Hardware version of this device.</span></span> <span data-ttu-id="53d23-123">有关详细信息，请参阅<a href="lync-server-2013-hardwareversions-table.md">Lync Server 2013 中的 HardwareVersions 表</a>。</span><span class="sxs-lookup"><span data-stu-id="53d23-123">See the <a href="lync-server-2013-hardwareversions-table.md">HardwareVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d23-124"><strong>MacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="53d23-124"><strong>MacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="53d23-125">bigint</span><span class="sxs-lookup"><span data-stu-id="53d23-125">bigint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="53d23-126">MAC 地址</span><span class="sxs-lookup"><span data-stu-id="53d23-126">MAC Address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

