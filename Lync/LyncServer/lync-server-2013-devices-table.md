---
title: Lync Server 2013：Devices 表
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
ms.openlocfilehash: 381b03fc5680276a64fc327f423f74c6773c2ed3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762350"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="devices-table-in-lync-server-2013"></a><span data-ttu-id="b1cb7-102">Lync Server 2013 中的 Devices 表</span><span class="sxs-lookup"><span data-stu-id="b1cb7-102">Devices table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b1cb7-103">_**主题上次修改时间：** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="b1cb7-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="b1cb7-104">"设备" 表是支持表。</span><span class="sxs-lookup"><span data-stu-id="b1cb7-104">The Devices table is a supporting table.</span></span> <span data-ttu-id="b1cb7-105">每条记录存储有关一个设备（桌面电话）的信息。</span><span class="sxs-lookup"><span data-stu-id="b1cb7-105">Each record stores information about one device (desk phone).</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b1cb7-106">列</span><span class="sxs-lookup"><span data-stu-id="b1cb7-106">Column</span></span></th>
<th><span data-ttu-id="b1cb7-107">数据类型</span><span class="sxs-lookup"><span data-stu-id="b1cb7-107">Data Type</span></span></th>
<th><span data-ttu-id="b1cb7-108">键/索引</span><span class="sxs-lookup"><span data-stu-id="b1cb7-108">Key/Index</span></span></th>
<th><span data-ttu-id="b1cb7-109">详细信息</span><span class="sxs-lookup"><span data-stu-id="b1cb7-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b1cb7-110"><strong>Keyroutedeventargs.deviceid</strong></span><span class="sxs-lookup"><span data-stu-id="b1cb7-110"><strong>DeviceId</strong></span></span></p></td>
<td><p><span data-ttu-id="b1cb7-111">int</span><span class="sxs-lookup"><span data-stu-id="b1cb7-111">int</span></span></p></td>
<td><p><span data-ttu-id="b1cb7-112">Primary</span><span class="sxs-lookup"><span data-stu-id="b1cb7-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="b1cb7-113">标识此硬件版本的唯一号码。</span><span class="sxs-lookup"><span data-stu-id="b1cb7-113">Unique number identifying this hardware version.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b1cb7-114"><strong>ManufacturerId</strong></span><span class="sxs-lookup"><span data-stu-id="b1cb7-114"><strong>ManufacturerId</strong></span></span></p></td>
<td><p><span data-ttu-id="b1cb7-115">int</span><span class="sxs-lookup"><span data-stu-id="b1cb7-115">int</span></span></p></td>
<td><p><span data-ttu-id="b1cb7-116">外表</span><span class="sxs-lookup"><span data-stu-id="b1cb7-116">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b1cb7-117">此设备的制造商。</span><span class="sxs-lookup"><span data-stu-id="b1cb7-117">Manufacturer of this device.</span></span> <span data-ttu-id="b1cb7-118">有关详细信息，请参阅<a href="lync-server-2013-manufacturers-table.md">Lync Server 2013 中的制造商表</a>。</span><span class="sxs-lookup"><span data-stu-id="b1cb7-118">See the <a href="lync-server-2013-manufacturers-table.md">Manufacturers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b1cb7-119"><strong>HardwareVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="b1cb7-119"><strong>HardwareVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="b1cb7-120">int</span><span class="sxs-lookup"><span data-stu-id="b1cb7-120">int</span></span></p></td>
<td><p><span data-ttu-id="b1cb7-121">外表</span><span class="sxs-lookup"><span data-stu-id="b1cb7-121">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b1cb7-122">此设备的硬件版本。</span><span class="sxs-lookup"><span data-stu-id="b1cb7-122">Hardware version of this device.</span></span> <span data-ttu-id="b1cb7-123">有关详细信息，请参阅<a href="lync-server-2013-hardwareversions-table.md">Lync Server 2013 中的 HardwareVersions 表</a>。</span><span class="sxs-lookup"><span data-stu-id="b1cb7-123">See the <a href="lync-server-2013-hardwareversions-table.md">HardwareVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b1cb7-124"><strong>MacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="b1cb7-124"><strong>MacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="b1cb7-125">bigint</span><span class="sxs-lookup"><span data-stu-id="b1cb7-125">bigint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b1cb7-126">MAC 地址</span><span class="sxs-lookup"><span data-stu-id="b1cb7-126">MAC Address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

