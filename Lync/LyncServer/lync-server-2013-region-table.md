---
title: Lync Server 2013：区域表
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
ms.openlocfilehash: d48217ff0daa62a8f528829b85620e173626ca06
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536719"
---
# <a name="region-table-in-lync-server-2013"></a><span data-ttu-id="d8762-102">Lync Server 2013 中的区域表</span><span class="sxs-lookup"><span data-stu-id="d8762-102">Region table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d8762-103">_**上次修改的主题：** 2010-11-09_</span><span class="sxs-lookup"><span data-stu-id="d8762-103">_**Topic Last Modified:** 2010-11-09_</span></span>

<span data-ttu-id="d8762-p101">区域表是一个支持表。每条记录代表网络配置设置中定义的一个国家/区域。</span><span class="sxs-lookup"><span data-stu-id="d8762-p101">The Region table is a supporting table. Each record represents one country/region defined in network configuration setting.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d8762-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="d8762-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="d8762-107"><strong>数据类型</strong></span><span class="sxs-lookup"><span data-stu-id="d8762-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="d8762-108"><strong>键/索引</strong></span><span class="sxs-lookup"><span data-stu-id="d8762-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="d8762-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="d8762-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d8762-110"><strong>RegionKey</strong></span><span class="sxs-lookup"><span data-stu-id="d8762-110"><strong>RegionKey</strong></span></span></p></td>
<td><p><span data-ttu-id="d8762-111">int</span><span class="sxs-lookup"><span data-stu-id="d8762-111">int</span></span></p></td>
<td><p><span data-ttu-id="d8762-112">主</span><span class="sxs-lookup"><span data-stu-id="d8762-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="d8762-113">标识国家/区域的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="d8762-113">Unique number identifying the country/region.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8762-114"><strong>RegionName</strong></span><span class="sxs-lookup"><span data-stu-id="d8762-114"><strong>RegionName</strong></span></span></p></td>
<td><p><span data-ttu-id="d8762-115">nvarchar (128) </span><span class="sxs-lookup"><span data-stu-id="d8762-115">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="d8762-116">独特</span><span class="sxs-lookup"><span data-stu-id="d8762-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="d8762-117">国家/区域的名称。</span><span class="sxs-lookup"><span data-stu-id="d8762-117">The name of the country/region.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

