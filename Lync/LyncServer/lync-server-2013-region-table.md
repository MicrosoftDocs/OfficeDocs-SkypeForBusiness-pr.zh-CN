---
title: Lync Server 2013：Region 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Region table
ms:assetid: 1751a6aa-a6e8-4f16-8eb7-ae731c2e3ee3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398235(v=OCS.15)
ms:contentKeyID: 48183518
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 005722b28b6ea93d89873d45e7a9284f44643bde
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724422"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="region-table-in-lync-server-2013"></a><span data-ttu-id="dc721-102">Lync Server 2013 中的 Region 表</span><span class="sxs-lookup"><span data-stu-id="dc721-102">Region table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dc721-103">_**主题上次修改时间：** 2010-11-09_</span><span class="sxs-lookup"><span data-stu-id="dc721-103">_**Topic Last Modified:** 2010-11-09_</span></span>

<span data-ttu-id="dc721-104">区域表是支持表。</span><span class="sxs-lookup"><span data-stu-id="dc721-104">The Region table is a supporting table.</span></span> <span data-ttu-id="dc721-105">每条记录表示在 "网络配置" 设置中定义的一个国家/地区。</span><span class="sxs-lookup"><span data-stu-id="dc721-105">Each record represents one country/region defined in network configuration setting.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dc721-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="dc721-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="dc721-107"><strong>数据类型</strong></span><span class="sxs-lookup"><span data-stu-id="dc721-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="dc721-108"><strong>键/索引</strong></span><span class="sxs-lookup"><span data-stu-id="dc721-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="dc721-109"><strong>详细信息</strong></span><span class="sxs-lookup"><span data-stu-id="dc721-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dc721-110"><strong>RegionKey</strong></span><span class="sxs-lookup"><span data-stu-id="dc721-110"><strong>RegionKey</strong></span></span></p></td>
<td><p><span data-ttu-id="dc721-111">int</span><span class="sxs-lookup"><span data-stu-id="dc721-111">int</span></span></p></td>
<td><p><span data-ttu-id="dc721-112">Primary</span><span class="sxs-lookup"><span data-stu-id="dc721-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="dc721-113">标识国家/地区的唯一号码。</span><span class="sxs-lookup"><span data-stu-id="dc721-113">Unique number identifying the country/region.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc721-114"><strong>RegionName</strong></span><span class="sxs-lookup"><span data-stu-id="dc721-114"><strong>RegionName</strong></span></span></p></td>
<td><p><span data-ttu-id="dc721-115">nvarchar</span><span class="sxs-lookup"><span data-stu-id="dc721-115">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="dc721-116">唯一</span><span class="sxs-lookup"><span data-stu-id="dc721-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="dc721-117">国家/地区的名称。</span><span class="sxs-lookup"><span data-stu-id="dc721-117">The name of the country/region.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

