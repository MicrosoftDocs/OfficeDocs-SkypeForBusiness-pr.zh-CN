---
title: Lync Server 2013：Pool 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Pool table
ms:assetid: 92ded8fd-d0ad-4f8a-9e6f-2e8a690fda3a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398746(v=OCS.15)
ms:contentKeyID: 48184803
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 08f878b9eefef86fba0fed4dd039b9a60b6f035d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824230"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pool-table-in-lync-server-2013"></a><span data-ttu-id="7de0d-102">Lync Server 2013 中的 Pool 表</span><span class="sxs-lookup"><span data-stu-id="7de0d-102">Pool table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7de0d-103">_**主题上次修改时间:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="7de0d-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="7de0d-104">Pool 表是一个支持表, 用于存储各种前端池的相关信息。</span><span class="sxs-lookup"><span data-stu-id="7de0d-104">The Pool table is a supporting table that stores information about the various Front End pools.</span></span> <span data-ttu-id="7de0d-105">表中的每条记录表示一个池。</span><span class="sxs-lookup"><span data-stu-id="7de0d-105">Each record in the table represents one pool.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7de0d-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="7de0d-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="7de0d-107"><strong>数据类型</strong></span><span class="sxs-lookup"><span data-stu-id="7de0d-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="7de0d-108"><strong>键/索引</strong></span><span class="sxs-lookup"><span data-stu-id="7de0d-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="7de0d-109"><strong>详细信息</strong></span><span class="sxs-lookup"><span data-stu-id="7de0d-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7de0d-110"><strong>PoolKey</strong></span><span class="sxs-lookup"><span data-stu-id="7de0d-110"><strong>PoolKey</strong></span></span></p></td>
<td><p><span data-ttu-id="7de0d-111">int</span><span class="sxs-lookup"><span data-stu-id="7de0d-111">int</span></span></p></td>
<td><p><span data-ttu-id="7de0d-112">Primary</span><span class="sxs-lookup"><span data-stu-id="7de0d-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="7de0d-113">标识此池的唯一号码。</span><span class="sxs-lookup"><span data-stu-id="7de0d-113">Unique number identifying this pool.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7de0d-114"><strong>PoolName</strong></span><span class="sxs-lookup"><span data-stu-id="7de0d-114"><strong>PoolName</strong></span></span></p></td>
<td><p><span data-ttu-id="7de0d-115">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="7de0d-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7de0d-116">唯一 </span><span class="sxs-lookup"><span data-stu-id="7de0d-116">Unique </span></span></p></td>
<td><p><span data-ttu-id="7de0d-117">池 FQDN。</span><span class="sxs-lookup"><span data-stu-id="7de0d-117">Pool FQDN.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

