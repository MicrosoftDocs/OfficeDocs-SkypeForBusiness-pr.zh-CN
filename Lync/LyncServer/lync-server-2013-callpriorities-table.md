---
title: Lync Server 2013：CallPriorities 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: CallPriorities table
ms:assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398093(v=OCS.15)
ms:contentKeyID: 48183275
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fdf08f1dfa8cd04b29f6edb6604a57ab5ec9e822
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837691"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="callpriorities-table-in-lync-server-2013"></a><span data-ttu-id="8ad25-102">Lync Server 2013 中的 CallPriorities 表</span><span class="sxs-lookup"><span data-stu-id="8ad25-102">CallPriorities table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8ad25-103">_**主题上次修改时间:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="8ad25-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="8ad25-104">CallPriorities 表是一个静态表, 用于存储可能的调用优先级列表, 例如 "紧急"、"紧急" 或 "正常"。</span><span class="sxs-lookup"><span data-stu-id="8ad25-104">The CallPriorities table is a static table that stores the list of possible call priorities, such as ‘emergency’, ‘urgent’, or ‘normal’.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8ad25-105">列</span><span class="sxs-lookup"><span data-stu-id="8ad25-105">Column</span></span></th>
<th><span data-ttu-id="8ad25-106">数据类型</span><span class="sxs-lookup"><span data-stu-id="8ad25-106">Data Type</span></span></th>
<th><span data-ttu-id="8ad25-107">键/索引</span><span class="sxs-lookup"><span data-stu-id="8ad25-107">Key/Index</span></span></th>
<th><span data-ttu-id="8ad25-108">详细信息</span><span class="sxs-lookup"><span data-stu-id="8ad25-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8ad25-109"><strong>PriorityId</strong></span><span class="sxs-lookup"><span data-stu-id="8ad25-109"><strong>PriorityId</strong></span></span></p></td>
<td><p><span data-ttu-id="8ad25-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="8ad25-110">tinyint</span></span></p></td>
<td><p><span data-ttu-id="8ad25-111">Primary</span><span class="sxs-lookup"><span data-stu-id="8ad25-111">Primary</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ad25-112"><strong>优先级</strong></span><span class="sxs-lookup"><span data-stu-id="8ad25-112"><strong>Priority</strong></span></span></p></td>
<td><p><span data-ttu-id="8ad25-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="8ad25-113">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8ad25-114">允许的值:</span><span class="sxs-lookup"><span data-stu-id="8ad25-114">Allowed values:</span></span></p>
<ul>
<li><p><span data-ttu-id="8ad25-115">0-未知</span><span class="sxs-lookup"><span data-stu-id="8ad25-115">0 - Unknown</span></span></p></li>
<li><p><span data-ttu-id="8ad25-116">1-非紧急</span><span class="sxs-lookup"><span data-stu-id="8ad25-116">1 – Non-Urgent</span></span></p></li>
<li><p><span data-ttu-id="8ad25-117">2-正常</span><span class="sxs-lookup"><span data-stu-id="8ad25-117">2 - Normal</span></span></p></li>
<li><p><span data-ttu-id="8ad25-118">3-紧急</span><span class="sxs-lookup"><span data-stu-id="8ad25-118">3 - Urgent</span></span></p></li>
<li><p><span data-ttu-id="8ad25-119">4-紧急情况</span><span class="sxs-lookup"><span data-stu-id="8ad25-119">4 - Emergency</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

