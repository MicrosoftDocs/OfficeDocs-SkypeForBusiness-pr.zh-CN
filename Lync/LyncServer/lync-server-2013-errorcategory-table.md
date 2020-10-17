---
title: Lync Server 2013： ErrorCategory 表
description: Lync Server 2013： ErrorCategory 表。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ErrorCategory table
ms:assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204675(v=OCS.15)
ms:contentKeyID: 48183425
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8154c73f33b5dad62a338335a960553cfc06ec13
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546428"
---
# <a name="errorcategory-table-in-lync-server-2013"></a><span data-ttu-id="31852-103">Lync Server 2013 中的 ErrorCategory 表</span><span class="sxs-lookup"><span data-stu-id="31852-103">ErrorCategory table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="31852-104">_**上次修改的主题：** 2012-08-20_</span><span class="sxs-lookup"><span data-stu-id="31852-104">_**Topic Last Modified:** 2012-08-20_</span></span>

<span data-ttu-id="31852-105">ErrorCategory 表包含每个 Microsoft Lync Server 2013 诊断分类的友好名称。</span><span class="sxs-lookup"><span data-stu-id="31852-105">The ErrorCategory table contains the friendly name for each Microsoft Lync Server 2013 diagnostic classification.</span></span> <span data-ttu-id="31852-106">默认情况下，Lync Server 2013 使用以下分类：</span><span class="sxs-lookup"><span data-stu-id="31852-106">By default, Lync Server 2013 uses the following classifications:</span></span>

  - <span data-ttu-id="31852-107">0 -- 成功</span><span class="sxs-lookup"><span data-stu-id="31852-107">0 -- Success</span></span>

  - <span data-ttu-id="31852-108">1--预期故障</span><span class="sxs-lookup"><span data-stu-id="31852-108">1 -- Expected failure</span></span>

  - <span data-ttu-id="31852-109">2 – 意外失败</span><span class="sxs-lookup"><span data-stu-id="31852-109">2 – Unexpected failure</span></span>

<span data-ttu-id="31852-110">此表是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="31852-110">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="31852-111">列</span><span class="sxs-lookup"><span data-stu-id="31852-111">Column</span></span></th>
<th><span data-ttu-id="31852-112">数据类型</span><span class="sxs-lookup"><span data-stu-id="31852-112">Data Type</span></span></th>
<th><span data-ttu-id="31852-113">键/索引</span><span class="sxs-lookup"><span data-stu-id="31852-113">Key/Index</span></span></th>
<th><span data-ttu-id="31852-114">详细信息</span><span class="sxs-lookup"><span data-stu-id="31852-114">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="31852-115"><strong>CategoryId</strong></span><span class="sxs-lookup"><span data-stu-id="31852-115"><strong>CategoryId</strong></span></span></p></td>
<td><p><span data-ttu-id="31852-116">tinyint</span><span class="sxs-lookup"><span data-stu-id="31852-116">tinyint</span></span></p></td>
<td><p><span data-ttu-id="31852-117">主</span><span class="sxs-lookup"><span data-stu-id="31852-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="31852-118">分类的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="31852-118">Unique identifier for the classification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="31852-119"><strong>名称</strong></span><span class="sxs-lookup"><span data-stu-id="31852-119"><strong>Name</strong></span></span></p></td>
<td><p><span data-ttu-id="31852-120">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="31852-120">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="31852-p102">分配给分类的值和友好名称。允许的值有：</span><span class="sxs-lookup"><span data-stu-id="31852-p102">Value and friendly name assigned to the classification. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="31852-123">0 -- 成功</span><span class="sxs-lookup"><span data-stu-id="31852-123">0 -- Success</span></span></p></li>
<li><p><span data-ttu-id="31852-124">1--预期故障</span><span class="sxs-lookup"><span data-stu-id="31852-124">1 -- Expected failure</span></span></p></li>
<li><p><span data-ttu-id="31852-125">2 – 意外失败</span><span class="sxs-lookup"><span data-stu-id="31852-125">2 – Unexpected failure</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

