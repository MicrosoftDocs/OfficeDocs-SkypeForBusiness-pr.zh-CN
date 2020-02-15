---
title: Lync Server 2013： MonitoredRegionLink 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: MonitoredRegionLink table
ms:assetid: cebda194-7be3-42d6-b6f0-c86f8b0f200a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398874(v=OCS.15)
ms:contentKeyID: 48185487
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 521996e17c3827b0d2c7e7796a8e95b73f805a04
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051204"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoredregionlink-table-in-lync-server-2013"></a><span data-ttu-id="5f89d-102">Lync Server 2013 中的 MonitoredRegionLink 表</span><span class="sxs-lookup"><span data-stu-id="5f89d-102">MonitoredRegionLink table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5f89d-103">_**上次修改的主题：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="5f89d-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="5f89d-104">MonitoredRegionLink 表是一个支持表格。</span><span class="sxs-lookup"><span data-stu-id="5f89d-104">The MonitoredRegionLink table is a supporting table.</span></span> <span data-ttu-id="5f89d-105">每个记录表示两个国家/地区之间的一个链接。</span><span class="sxs-lookup"><span data-stu-id="5f89d-105">Each record represents one link between two countries/regions.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5f89d-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="5f89d-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="5f89d-107"><strong>数据类型</strong></span><span class="sxs-lookup"><span data-stu-id="5f89d-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="5f89d-108"><strong>键/索引</strong></span><span class="sxs-lookup"><span data-stu-id="5f89d-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="5f89d-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="5f89d-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5f89d-110"><strong>Region1Key</strong></span><span class="sxs-lookup"><span data-stu-id="5f89d-110"><strong>Region1Key</strong></span></span></p></td>
<td><p><span data-ttu-id="5f89d-111">int</span><span class="sxs-lookup"><span data-stu-id="5f89d-111">int</span></span></p></td>
<td><p><span data-ttu-id="5f89d-112">主、外</span><span class="sxs-lookup"><span data-stu-id="5f89d-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="5f89d-113">从<a href="lync-server-2013-region-table.md">Lync Server 2013 中的区域表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="5f89d-113">Referenced from the <a href="lync-server-2013-region-table.md">Region table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f89d-114"><strong>Region2Key</strong></span><span class="sxs-lookup"><span data-stu-id="5f89d-114"><strong>Region2Key</strong></span></span></p></td>
<td><p><span data-ttu-id="5f89d-115">int</span><span class="sxs-lookup"><span data-stu-id="5f89d-115">int</span></span></p></td>
<td><p><span data-ttu-id="5f89d-116">主、外</span><span class="sxs-lookup"><span data-stu-id="5f89d-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="5f89d-117">从<a href="lync-server-2013-region-table.md">Lync Server 2013 中的区域表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="5f89d-117">Referenced from the <a href="lync-server-2013-region-table.md">Region table in Lync Server 2013</a>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

