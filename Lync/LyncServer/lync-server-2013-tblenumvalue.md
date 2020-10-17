---
title: Lync Server 2013： tblEnumValue
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblEnumValue
ms:assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615025(v=OCS.15)
ms:contentKeyID: 48185040
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 79d1b68cd10858812a1310ebbd1f2caae913da75
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509319"
---
# <a name="tblenumvalue-in-lync-server-2013"></a><span data-ttu-id="92885-102">Lync Server 2013 中的 tblEnumValue</span><span class="sxs-lookup"><span data-stu-id="92885-102">tblEnumValue in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="92885-103">_**上次修改的主题：** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="92885-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="92885-104">tblEnumValue 表是一个硬编码表，包含节点表使用的属性的“可见性”值和“行为”值。</span><span class="sxs-lookup"><span data-stu-id="92885-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>

### <a name="columns"></a><span data-ttu-id="92885-105">列数</span><span class="sxs-lookup"><span data-stu-id="92885-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="92885-106">列</span><span class="sxs-lookup"><span data-stu-id="92885-106">Column</span></span></th>
<th><span data-ttu-id="92885-107">类型</span><span class="sxs-lookup"><span data-stu-id="92885-107">Type</span></span></th>
<th><span data-ttu-id="92885-108">说明</span><span class="sxs-lookup"><span data-stu-id="92885-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="92885-109">valueID</span><span class="sxs-lookup"><span data-stu-id="92885-109">valueID</span></span></p></td>
<td><p><span data-ttu-id="92885-110">smallint，不为 null</span><span class="sxs-lookup"><span data-stu-id="92885-110">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="92885-111">值的 ID。</span><span class="sxs-lookup"><span data-stu-id="92885-111">ID of the value.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="92885-112">attributeID</span><span class="sxs-lookup"><span data-stu-id="92885-112">attributeID</span></span></p></td>
<td><p><span data-ttu-id="92885-113">smallint，不为 null</span><span class="sxs-lookup"><span data-stu-id="92885-113">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="92885-114">属性的 ID。</span><span class="sxs-lookup"><span data-stu-id="92885-114">ID of the attribute.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="92885-115">attributeValue</span><span class="sxs-lookup"><span data-stu-id="92885-115">attributeValue</span></span></p></td>
<td><p><span data-ttu-id="92885-116">nvarchar  (256)，不为 null</span><span class="sxs-lookup"><span data-stu-id="92885-116">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="92885-117">值名称。</span><span class="sxs-lookup"><span data-stu-id="92885-117">Name of the value.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="92885-118">Keys</span><span class="sxs-lookup"><span data-stu-id="92885-118">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="92885-119">列</span><span class="sxs-lookup"><span data-stu-id="92885-119">Column</span></span></th>
<th><span data-ttu-id="92885-120">说明</span><span class="sxs-lookup"><span data-stu-id="92885-120">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="92885-121">valueID</span><span class="sxs-lookup"><span data-stu-id="92885-121">valueID</span></span></p></td>
<td><p><span data-ttu-id="92885-122">主键。</span><span class="sxs-lookup"><span data-stu-id="92885-122">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="92885-123">attributeID</span><span class="sxs-lookup"><span data-stu-id="92885-123">attributeID</span></span></p></td>
<td><p><span data-ttu-id="92885-124">其查找包含在 tblEnumAttribute.attributeID 表中的外键。</span><span class="sxs-lookup"><span data-stu-id="92885-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-values"></a><span data-ttu-id="92885-125">表值</span><span class="sxs-lookup"><span data-stu-id="92885-125">Table Values</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="92885-126">valueID</span><span class="sxs-lookup"><span data-stu-id="92885-126">valueID</span></span></th>
<th><span data-ttu-id="92885-127">attributeID</span><span class="sxs-lookup"><span data-stu-id="92885-127">attributeID</span></span></th>
<th><span data-ttu-id="92885-128">attributeValue</span><span class="sxs-lookup"><span data-stu-id="92885-128">attributeValue</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="92885-129">双面</span><span class="sxs-lookup"><span data-stu-id="92885-129">2</span></span></p></td>
<td><p><span data-ttu-id="92885-130">1</span><span class="sxs-lookup"><span data-stu-id="92885-130">1</span></span></p></td>
<td><p><span data-ttu-id="92885-131">private</span><span class="sxs-lookup"><span data-stu-id="92885-131">private</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="92885-132">第三章</span><span class="sxs-lookup"><span data-stu-id="92885-132">3</span></span></p></td>
<td><p><span data-ttu-id="92885-133">1</span><span class="sxs-lookup"><span data-stu-id="92885-133">1</span></span></p></td>
<td><p><span data-ttu-id="92885-134">范围</span><span class="sxs-lookup"><span data-stu-id="92885-134">scope</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="92885-135">4 </span><span class="sxs-lookup"><span data-stu-id="92885-135">4</span></span></p></td>
<td><p><span data-ttu-id="92885-136">双面</span><span class="sxs-lookup"><span data-stu-id="92885-136">2</span></span></p></td>
<td><p><span data-ttu-id="92885-137">通用</span><span class="sxs-lookup"><span data-stu-id="92885-137">normal</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="92885-138">5 </span><span class="sxs-lookup"><span data-stu-id="92885-138">5</span></span></p></td>
<td><p><span data-ttu-id="92885-139">双面</span><span class="sxs-lookup"><span data-stu-id="92885-139">2</span></span></p></td>
<td><p><span data-ttu-id="92885-140">大会堂</span><span class="sxs-lookup"><span data-stu-id="92885-140">auditorium</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="92885-141">6 </span><span class="sxs-lookup"><span data-stu-id="92885-141">6</span></span></p></td>
<td><p><span data-ttu-id="92885-142">1</span><span class="sxs-lookup"><span data-stu-id="92885-142">1</span></span></p></td>
<td><p><span data-ttu-id="92885-143">open</span><span class="sxs-lookup"><span data-stu-id="92885-143">open</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="92885-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="92885-144">See Also</span></span>


[<span data-ttu-id="92885-145">Lync Server 2013 中的 tblNode</span><span class="sxs-lookup"><span data-stu-id="92885-145">tblNode in Lync Server 2013</span></span>](lync-server-2013-tblnode.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

