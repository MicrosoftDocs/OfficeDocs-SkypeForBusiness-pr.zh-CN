---
title: Lync Server 2013： CallPriorities 表
description: Lync Server 2013： CallPriorities 表。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: CallPriorities table
ms:assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398093(v=OCS.15)
ms:contentKeyID: 48183275
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe3cd1639921c63630e157744dbc8af22c50fac7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565178"
---
# <a name="callpriorities-table-in-lync-server-2013"></a><span data-ttu-id="14351-103">Lync Server 2013 中的 CallPriorities 表</span><span class="sxs-lookup"><span data-stu-id="14351-103">CallPriorities table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="14351-104">_**上次修改的主题：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="14351-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="14351-105">CallPriorities 表是一个静态表，用于存储可能的呼叫优先级（例如“紧急”、“紧迫”或“普通”）列表。</span><span class="sxs-lookup"><span data-stu-id="14351-105">The CallPriorities table is a static table that stores the list of possible call priorities, such as ‘emergency’, ‘urgent’, or ‘normal’.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="14351-106">列</span><span class="sxs-lookup"><span data-stu-id="14351-106">Column</span></span></th>
<th><span data-ttu-id="14351-107">数据类型</span><span class="sxs-lookup"><span data-stu-id="14351-107">Data Type</span></span></th>
<th><span data-ttu-id="14351-108">键/索引</span><span class="sxs-lookup"><span data-stu-id="14351-108">Key/Index</span></span></th>
<th><span data-ttu-id="14351-109">详细信息</span><span class="sxs-lookup"><span data-stu-id="14351-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="14351-110"><strong>PriorityId</strong></span><span class="sxs-lookup"><span data-stu-id="14351-110"><strong>PriorityId</strong></span></span></p></td>
<td><p><span data-ttu-id="14351-111">tinyint</span><span class="sxs-lookup"><span data-stu-id="14351-111">tinyint</span></span></p></td>
<td><p><span data-ttu-id="14351-112">主</span><span class="sxs-lookup"><span data-stu-id="14351-112">Primary</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14351-113"><strong>Priority</strong></span><span class="sxs-lookup"><span data-stu-id="14351-113"><strong>Priority</strong></span></span></p></td>
<td><p><span data-ttu-id="14351-114">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="14351-114">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="14351-115">允许的值：</span><span class="sxs-lookup"><span data-stu-id="14351-115">Allowed values:</span></span></p>
<ul>
<li><p><span data-ttu-id="14351-116">0 – 未知</span><span class="sxs-lookup"><span data-stu-id="14351-116">0 - Unknown</span></span></p></li>
<li><p><span data-ttu-id="14351-117">1 – 非紧急</span><span class="sxs-lookup"><span data-stu-id="14351-117">1 – Non-Urgent</span></span></p></li>
<li><p><span data-ttu-id="14351-118">2 – 普通</span><span class="sxs-lookup"><span data-stu-id="14351-118">2 - Normal</span></span></p></li>
<li><p><span data-ttu-id="14351-119">3 – 紧急</span><span class="sxs-lookup"><span data-stu-id="14351-119">3 - Urgent</span></span></p></li>
<li><p><span data-ttu-id="14351-120">4 – 紧迫</span><span class="sxs-lookup"><span data-stu-id="14351-120">4 - Emergency</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

