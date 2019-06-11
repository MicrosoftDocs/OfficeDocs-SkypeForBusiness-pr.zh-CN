---
title: Lync Server 2013：UserSite 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: UserSite table
ms:assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398256(v=OCS.15)
ms:contentKeyID: 48183552
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9dfb3e3d99775405ce4a09df706bec8eea59f6f9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845465"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="usersite-table-in-lync-server-2013"></a><span data-ttu-id="f9c75-102">Lync Server 2013 中的 UserSite 表</span><span class="sxs-lookup"><span data-stu-id="f9c75-102">UserSite table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f9c75-103">_**主题上次修改时间:** 2010-11-09_</span><span class="sxs-lookup"><span data-stu-id="f9c75-103">_**Topic Last Modified:** 2010-11-09_</span></span>

<span data-ttu-id="f9c75-104">UserSite 表是支持表。</span><span class="sxs-lookup"><span data-stu-id="f9c75-104">The UserSite table is a supporting table.</span></span> <span data-ttu-id="f9c75-105">每条记录表示网络配置设置中定义的一个用户网站。</span><span class="sxs-lookup"><span data-stu-id="f9c75-105">Each record represents one user site defined in network configuration setting.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f9c75-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="f9c75-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="f9c75-107"><strong>数据类型</strong></span><span class="sxs-lookup"><span data-stu-id="f9c75-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="f9c75-108"><strong>键/索引</strong></span><span class="sxs-lookup"><span data-stu-id="f9c75-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="f9c75-109"><strong>详细信息</strong></span><span class="sxs-lookup"><span data-stu-id="f9c75-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f9c75-110"><strong>UserSiteKey</strong></span><span class="sxs-lookup"><span data-stu-id="f9c75-110"><strong>UserSiteKey</strong></span></span></p></td>
<td><p><span data-ttu-id="f9c75-111">int</span><span class="sxs-lookup"><span data-stu-id="f9c75-111">int</span></span></p></td>
<td><p><span data-ttu-id="f9c75-112">Primary</span><span class="sxs-lookup"><span data-stu-id="f9c75-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="f9c75-113">标识用户网站的唯一号码。</span><span class="sxs-lookup"><span data-stu-id="f9c75-113">Unique number identifying the user site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9c75-114"><strong>UserSiteName</strong></span><span class="sxs-lookup"><span data-stu-id="f9c75-114"><strong>UserSiteName</strong></span></span></p></td>
<td><p><span data-ttu-id="f9c75-115">nvarchar</span><span class="sxs-lookup"><span data-stu-id="f9c75-115">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="f9c75-116">唯一</span><span class="sxs-lookup"><span data-stu-id="f9c75-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="f9c75-117">用户网站的名称。</span><span class="sxs-lookup"><span data-stu-id="f9c75-117">User site’s name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9c75-118"><strong>RegionKey</strong></span><span class="sxs-lookup"><span data-stu-id="f9c75-118"><strong>RegionKey</strong></span></span></p></td>
<td><p><span data-ttu-id="f9c75-119">int</span><span class="sxs-lookup"><span data-stu-id="f9c75-119">int</span></span></p></td>
<td><p><span data-ttu-id="f9c75-120">外表</span><span class="sxs-lookup"><span data-stu-id="f9c75-120">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f9c75-121">从<a href="lync-server-2013-region-table.md">Lync Server 2013 中的区域表</a>引用。</span><span class="sxs-lookup"><span data-stu-id="f9c75-121">Referenced from <a href="lync-server-2013-region-table.md">Region table in Lync Server 2013</a>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

