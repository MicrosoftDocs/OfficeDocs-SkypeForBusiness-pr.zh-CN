---
title: Lync Server 2013： UserSite 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UserSite table
ms:assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398256(v=OCS.15)
ms:contentKeyID: 48183552
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 39119f423f1bc06b6f51f9f18cbbf39d670c7270
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212918"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="usersite-table-in-lync-server-2013"></a><span data-ttu-id="80f40-102">Lync Server 2013 中的 UserSite 表</span><span class="sxs-lookup"><span data-stu-id="80f40-102">UserSite table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="80f40-103">_**上次修改的主题：** 2010-11-09_</span><span class="sxs-lookup"><span data-stu-id="80f40-103">_**Topic Last Modified:** 2010-11-09_</span></span>

<span data-ttu-id="80f40-p101">UserSite 表是一个支持表。每条记录代表一个在网络配置设置中定义的用户站点。</span><span class="sxs-lookup"><span data-stu-id="80f40-p101">The UserSite table is a supporting table. Each record represents one user site defined in network configuration setting.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="80f40-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="80f40-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="80f40-107"><strong>数据类型</strong></span><span class="sxs-lookup"><span data-stu-id="80f40-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="80f40-108"><strong>键/索引</strong></span><span class="sxs-lookup"><span data-stu-id="80f40-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="80f40-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="80f40-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="80f40-110"><strong>UserSiteKey</strong></span><span class="sxs-lookup"><span data-stu-id="80f40-110"><strong>UserSiteKey</strong></span></span></p></td>
<td><p><span data-ttu-id="80f40-111">int</span><span class="sxs-lookup"><span data-stu-id="80f40-111">int</span></span></p></td>
<td><p><span data-ttu-id="80f40-112">主</span><span class="sxs-lookup"><span data-stu-id="80f40-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="80f40-113">标识用户站点的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="80f40-113">Unique number identifying the user site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80f40-114"><strong>UserSiteName</strong></span><span class="sxs-lookup"><span data-stu-id="80f40-114"><strong>UserSiteName</strong></span></span></p></td>
<td><p><span data-ttu-id="80f40-115">nvarchar</span><span class="sxs-lookup"><span data-stu-id="80f40-115">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="80f40-116">独特</span><span class="sxs-lookup"><span data-stu-id="80f40-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="80f40-117">用户站点的名称。</span><span class="sxs-lookup"><span data-stu-id="80f40-117">User site’s name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80f40-118"><strong>RegionKey</strong></span><span class="sxs-lookup"><span data-stu-id="80f40-118"><strong>RegionKey</strong></span></span></p></td>
<td><p><span data-ttu-id="80f40-119">int</span><span class="sxs-lookup"><span data-stu-id="80f40-119">int</span></span></p></td>
<td><p><span data-ttu-id="80f40-120">对外</span><span class="sxs-lookup"><span data-stu-id="80f40-120">Foreign</span></span></p></td>
<td><p><span data-ttu-id="80f40-121"><a href="lync-server-2013-region-table.md">在 Lync Server 2013 中的 "区域" 表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="80f40-121">Referenced from <a href="lync-server-2013-region-table.md">Region table in Lync Server 2013</a>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

