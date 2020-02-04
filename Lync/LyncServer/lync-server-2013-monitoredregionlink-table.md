---
title: Lync Server 2013：MonitoredRegionLink 表
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
ms.openlocfilehash: e5608aa36a76fe59743ed8bb24e88514822a893e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765993"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoredregionlink-table-in-lync-server-2013"></a><span data-ttu-id="12e70-102">Lync Server 2013 中的 MonitoredRegionLink 表</span><span class="sxs-lookup"><span data-stu-id="12e70-102">MonitoredRegionLink table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="12e70-103">_**主题上次修改时间：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="12e70-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="12e70-104">MonitoredRegionLink 表是支持表。</span><span class="sxs-lookup"><span data-stu-id="12e70-104">The MonitoredRegionLink table is a supporting table.</span></span> <span data-ttu-id="12e70-105">每条记录表示两个国家/地区之间的一个链接。</span><span class="sxs-lookup"><span data-stu-id="12e70-105">Each record represents one link between two countries/regions.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="12e70-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="12e70-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="12e70-107"><strong>数据类型</strong></span><span class="sxs-lookup"><span data-stu-id="12e70-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="12e70-108"><strong>键/索引</strong></span><span class="sxs-lookup"><span data-stu-id="12e70-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="12e70-109"><strong>详细信息</strong></span><span class="sxs-lookup"><span data-stu-id="12e70-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="12e70-110"><strong>Region1Key</strong></span><span class="sxs-lookup"><span data-stu-id="12e70-110"><strong>Region1Key</strong></span></span></p></td>
<td><p><span data-ttu-id="12e70-111">int</span><span class="sxs-lookup"><span data-stu-id="12e70-111">int</span></span></p></td>
<td><p><span data-ttu-id="12e70-112">主、外部</span><span class="sxs-lookup"><span data-stu-id="12e70-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="12e70-113">从<a href="lync-server-2013-region-table.md">Lync Server 2013 中的区域表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="12e70-113">Referenced from the <a href="lync-server-2013-region-table.md">Region table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12e70-114"><strong>Region2Key</strong></span><span class="sxs-lookup"><span data-stu-id="12e70-114"><strong>Region2Key</strong></span></span></p></td>
<td><p><span data-ttu-id="12e70-115">int</span><span class="sxs-lookup"><span data-stu-id="12e70-115">int</span></span></p></td>
<td><p><span data-ttu-id="12e70-116">主、外部</span><span class="sxs-lookup"><span data-stu-id="12e70-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="12e70-117">从<a href="lync-server-2013-region-table.md">Lync Server 2013 中的区域表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="12e70-117">Referenced from the <a href="lync-server-2013-region-table.md">Region table in Lync Server 2013</a>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

