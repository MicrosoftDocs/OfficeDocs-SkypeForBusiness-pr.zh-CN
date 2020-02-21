---
title: Lync Server 2013： CallPriorities 表
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
ms.openlocfilehash: 7804a02995550a550c2916db20f12367466efe4c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198525"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="callpriorities-table-in-lync-server-2013"></a><span data-ttu-id="6577c-102">Lync Server 2013 中的 CallPriorities 表</span><span class="sxs-lookup"><span data-stu-id="6577c-102">CallPriorities table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6577c-103">_**上次修改的主题：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="6577c-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="6577c-104">CallPriorities 表是一个静态表，用于存储可能的呼叫优先级（例如“紧急”、“紧迫”或“普通”）列表。</span><span class="sxs-lookup"><span data-stu-id="6577c-104">The CallPriorities table is a static table that stores the list of possible call priorities, such as ‘emergency’, ‘urgent’, or ‘normal’.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6577c-105">列</span><span class="sxs-lookup"><span data-stu-id="6577c-105">Column</span></span></th>
<th><span data-ttu-id="6577c-106">数据类型</span><span class="sxs-lookup"><span data-stu-id="6577c-106">Data Type</span></span></th>
<th><span data-ttu-id="6577c-107">键/索引</span><span class="sxs-lookup"><span data-stu-id="6577c-107">Key/Index</span></span></th>
<th><span data-ttu-id="6577c-108">详细信息</span><span class="sxs-lookup"><span data-stu-id="6577c-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6577c-109"><strong>PriorityId</strong></span><span class="sxs-lookup"><span data-stu-id="6577c-109"><strong>PriorityId</strong></span></span></p></td>
<td><p><span data-ttu-id="6577c-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="6577c-110">tinyint</span></span></p></td>
<td><p><span data-ttu-id="6577c-111">主</span><span class="sxs-lookup"><span data-stu-id="6577c-111">Primary</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6577c-112"><strong>Priority</strong></span><span class="sxs-lookup"><span data-stu-id="6577c-112"><strong>Priority</strong></span></span></p></td>
<td><p><span data-ttu-id="6577c-113">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="6577c-113">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6577c-114">允许的值：</span><span class="sxs-lookup"><span data-stu-id="6577c-114">Allowed values:</span></span></p>
<ul>
<li><p><span data-ttu-id="6577c-115">0 – 未知</span><span class="sxs-lookup"><span data-stu-id="6577c-115">0 - Unknown</span></span></p></li>
<li><p><span data-ttu-id="6577c-116">1 – 非紧急</span><span class="sxs-lookup"><span data-stu-id="6577c-116">1 – Non-Urgent</span></span></p></li>
<li><p><span data-ttu-id="6577c-117">2 – 普通</span><span class="sxs-lookup"><span data-stu-id="6577c-117">2 - Normal</span></span></p></li>
<li><p><span data-ttu-id="6577c-118">3 – 紧急</span><span class="sxs-lookup"><span data-stu-id="6577c-118">3 - Urgent</span></span></p></li>
<li><p><span data-ttu-id="6577c-119">4 – 紧迫</span><span class="sxs-lookup"><span data-stu-id="6577c-119">4 - Emergency</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

