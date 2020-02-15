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
ms.openlocfilehash: d182a3689ae38d4117b45d6590bb2ccd08c0a8b7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42027053"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblenumvalue-in-lync-server-2013"></a><span data-ttu-id="d3e0b-102">Lync Server 2013 中的 tblEnumValue</span><span class="sxs-lookup"><span data-stu-id="d3e0b-102">tblEnumValue in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d3e0b-103">_**上次修改的主题：** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="d3e0b-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="d3e0b-104">tblEnumValue 表是一个硬编码表，包含节点表使用的属性的“可见性”值和“行为”值。</span><span class="sxs-lookup"><span data-stu-id="d3e0b-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>

### <a name="columns"></a><span data-ttu-id="d3e0b-105">Columns</span><span class="sxs-lookup"><span data-stu-id="d3e0b-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d3e0b-106">列</span><span class="sxs-lookup"><span data-stu-id="d3e0b-106">Column</span></span></th>
<th><span data-ttu-id="d3e0b-107">类型</span><span class="sxs-lookup"><span data-stu-id="d3e0b-107">Type</span></span></th>
<th><span data-ttu-id="d3e0b-108">说明</span><span class="sxs-lookup"><span data-stu-id="d3e0b-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d3e0b-109">valueID</span><span class="sxs-lookup"><span data-stu-id="d3e0b-109">valueID</span></span></p></td>
<td><p><span data-ttu-id="d3e0b-110">smallint，不为 null</span><span class="sxs-lookup"><span data-stu-id="d3e0b-110">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="d3e0b-111">值的 ID。</span><span class="sxs-lookup"><span data-stu-id="d3e0b-111">ID of the value.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3e0b-112">attributeID</span><span class="sxs-lookup"><span data-stu-id="d3e0b-112">attributeID</span></span></p></td>
<td><p><span data-ttu-id="d3e0b-113">smallint，不为 null</span><span class="sxs-lookup"><span data-stu-id="d3e0b-113">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="d3e0b-114">属性的 ID。</span><span class="sxs-lookup"><span data-stu-id="d3e0b-114">ID of the attribute.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d3e0b-115">attributeValue</span><span class="sxs-lookup"><span data-stu-id="d3e0b-115">attributeValue</span></span></p></td>
<td><p><span data-ttu-id="d3e0b-116">nvarchar  (256)，不为 null</span><span class="sxs-lookup"><span data-stu-id="d3e0b-116">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="d3e0b-117">值名称。</span><span class="sxs-lookup"><span data-stu-id="d3e0b-117">Name of the value.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="d3e0b-118">Keys</span><span class="sxs-lookup"><span data-stu-id="d3e0b-118">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d3e0b-119">列</span><span class="sxs-lookup"><span data-stu-id="d3e0b-119">Column</span></span></th>
<th><span data-ttu-id="d3e0b-120">说明</span><span class="sxs-lookup"><span data-stu-id="d3e0b-120">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d3e0b-121">valueID</span><span class="sxs-lookup"><span data-stu-id="d3e0b-121">valueID</span></span></p></td>
<td><p><span data-ttu-id="d3e0b-122">主键。</span><span class="sxs-lookup"><span data-stu-id="d3e0b-122">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3e0b-123">attributeID</span><span class="sxs-lookup"><span data-stu-id="d3e0b-123">attributeID</span></span></p></td>
<td><p><span data-ttu-id="d3e0b-124">其查找包含在 tblEnumAttribute.attributeID 表中的外键。</span><span class="sxs-lookup"><span data-stu-id="d3e0b-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-values"></a><span data-ttu-id="d3e0b-125">表值</span><span class="sxs-lookup"><span data-stu-id="d3e0b-125">Table Values</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d3e0b-126">valueID</span><span class="sxs-lookup"><span data-stu-id="d3e0b-126">valueID</span></span></th>
<th><span data-ttu-id="d3e0b-127">attributeID</span><span class="sxs-lookup"><span data-stu-id="d3e0b-127">attributeID</span></span></th>
<th><span data-ttu-id="d3e0b-128">attributeValue</span><span class="sxs-lookup"><span data-stu-id="d3e0b-128">attributeValue</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d3e0b-129">2 </span><span class="sxs-lookup"><span data-stu-id="d3e0b-129">2</span></span></p></td>
<td><p><span data-ttu-id="d3e0b-130">1 </span><span class="sxs-lookup"><span data-stu-id="d3e0b-130">1</span></span></p></td>
<td><p><span data-ttu-id="d3e0b-131">private</span><span class="sxs-lookup"><span data-stu-id="d3e0b-131">private</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3e0b-132">3 </span><span class="sxs-lookup"><span data-stu-id="d3e0b-132">3</span></span></p></td>
<td><p><span data-ttu-id="d3e0b-133">1 </span><span class="sxs-lookup"><span data-stu-id="d3e0b-133">1</span></span></p></td>
<td><p><span data-ttu-id="d3e0b-134">范围</span><span class="sxs-lookup"><span data-stu-id="d3e0b-134">scope</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d3e0b-135">4 </span><span class="sxs-lookup"><span data-stu-id="d3e0b-135">4</span></span></p></td>
<td><p><span data-ttu-id="d3e0b-136">2 </span><span class="sxs-lookup"><span data-stu-id="d3e0b-136">2</span></span></p></td>
<td><p><span data-ttu-id="d3e0b-137">通用</span><span class="sxs-lookup"><span data-stu-id="d3e0b-137">normal</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3e0b-138">5 </span><span class="sxs-lookup"><span data-stu-id="d3e0b-138">5</span></span></p></td>
<td><p><span data-ttu-id="d3e0b-139">2 </span><span class="sxs-lookup"><span data-stu-id="d3e0b-139">2</span></span></p></td>
<td><p><span data-ttu-id="d3e0b-140">大会堂</span><span class="sxs-lookup"><span data-stu-id="d3e0b-140">auditorium</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d3e0b-141">6 </span><span class="sxs-lookup"><span data-stu-id="d3e0b-141">6</span></span></p></td>
<td><p><span data-ttu-id="d3e0b-142">1 </span><span class="sxs-lookup"><span data-stu-id="d3e0b-142">1</span></span></p></td>
<td><p><span data-ttu-id="d3e0b-143">open</span><span class="sxs-lookup"><span data-stu-id="d3e0b-143">open</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="d3e0b-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d3e0b-144">See Also</span></span>


[<span data-ttu-id="d3e0b-145">Lync Server 2013 中的 tblNode</span><span class="sxs-lookup"><span data-stu-id="d3e0b-145">tblNode in Lync Server 2013</span></span>](lync-server-2013-tblnode.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

