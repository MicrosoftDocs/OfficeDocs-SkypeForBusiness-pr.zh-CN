---
title: Lync Server 2013： ErrorCategory 表
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
ms.openlocfilehash: 407b7efd00a521e0eec7a6d573368d2f971ce3bc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042099"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="errorcategory-table-in-lync-server-2013"></a><span data-ttu-id="081f4-102">Lync Server 2013 中的 ErrorCategory 表</span><span class="sxs-lookup"><span data-stu-id="081f4-102">ErrorCategory table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="081f4-103">_**上次修改的主题：** 2012-08-20_</span><span class="sxs-lookup"><span data-stu-id="081f4-103">_**Topic Last Modified:** 2012-08-20_</span></span>

<span data-ttu-id="081f4-104">ErrorCategory 表包含每个 Microsoft Lync Server 2013 诊断分类的友好名称。</span><span class="sxs-lookup"><span data-stu-id="081f4-104">The ErrorCategory table contains the friendly name for each Microsoft Lync Server 2013 diagnostic classification.</span></span> <span data-ttu-id="081f4-105">默认情况下，Lync Server 2013 使用以下分类：</span><span class="sxs-lookup"><span data-stu-id="081f4-105">By default, Lync Server 2013 uses the following classifications:</span></span>

  - <span data-ttu-id="081f4-106">0 -- 成功</span><span class="sxs-lookup"><span data-stu-id="081f4-106">0 -- Success</span></span>

  - <span data-ttu-id="081f4-107">1--预期故障</span><span class="sxs-lookup"><span data-stu-id="081f4-107">1 -- Expected failure</span></span>

  - <span data-ttu-id="081f4-108">2 – 意外失败</span><span class="sxs-lookup"><span data-stu-id="081f4-108">2 – Unexpected failure</span></span>

<span data-ttu-id="081f4-109">此表是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="081f4-109">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="081f4-110">列</span><span class="sxs-lookup"><span data-stu-id="081f4-110">Column</span></span></th>
<th><span data-ttu-id="081f4-111">数据类型</span><span class="sxs-lookup"><span data-stu-id="081f4-111">Data Type</span></span></th>
<th><span data-ttu-id="081f4-112">键/索引</span><span class="sxs-lookup"><span data-stu-id="081f4-112">Key/Index</span></span></th>
<th><span data-ttu-id="081f4-113">详细信息</span><span class="sxs-lookup"><span data-stu-id="081f4-113">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="081f4-114"><strong>CategoryId</strong></span><span class="sxs-lookup"><span data-stu-id="081f4-114"><strong>CategoryId</strong></span></span></p></td>
<td><p><span data-ttu-id="081f4-115">tinyint</span><span class="sxs-lookup"><span data-stu-id="081f4-115">tinyint</span></span></p></td>
<td><p><span data-ttu-id="081f4-116">主</span><span class="sxs-lookup"><span data-stu-id="081f4-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="081f4-117">分类的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="081f4-117">Unique identifier for the classification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="081f4-118"><strong>名称</strong></span><span class="sxs-lookup"><span data-stu-id="081f4-118"><strong>Name</strong></span></span></p></td>
<td><p><span data-ttu-id="081f4-119">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="081f4-119">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="081f4-p102">分配给分类的值和友好名称。允许的值有：</span><span class="sxs-lookup"><span data-stu-id="081f4-p102">Value and friendly name assigned to the classification. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="081f4-122">0 -- 成功</span><span class="sxs-lookup"><span data-stu-id="081f4-122">0 -- Success</span></span></p></li>
<li><p><span data-ttu-id="081f4-123">1--预期故障</span><span class="sxs-lookup"><span data-stu-id="081f4-123">1 -- Expected failure</span></span></p></li>
<li><p><span data-ttu-id="081f4-124">2 – 意外失败</span><span class="sxs-lookup"><span data-stu-id="081f4-124">2 – Unexpected failure</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

