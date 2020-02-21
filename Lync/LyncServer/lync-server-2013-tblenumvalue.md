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
ms.openlocfilehash: 4166e25375c7ddd631b1ee7944ac703f21c9ba80
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207168"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblenumvalue-in-lync-server-2013"></a><span data-ttu-id="0042c-102">Lync Server 2013 中的 tblEnumValue</span><span class="sxs-lookup"><span data-stu-id="0042c-102">tblEnumValue in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0042c-103">_**上次修改的主题：** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="0042c-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="0042c-104">tblEnumValue 表是一个硬编码表，包含节点表使用的属性的“可见性”值和“行为”值。</span><span class="sxs-lookup"><span data-stu-id="0042c-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>

### <a name="columns"></a><span data-ttu-id="0042c-105">Columns</span><span class="sxs-lookup"><span data-stu-id="0042c-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0042c-106">列</span><span class="sxs-lookup"><span data-stu-id="0042c-106">Column</span></span></th>
<th><span data-ttu-id="0042c-107">类型</span><span class="sxs-lookup"><span data-stu-id="0042c-107">Type</span></span></th>
<th><span data-ttu-id="0042c-108">说明</span><span class="sxs-lookup"><span data-stu-id="0042c-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0042c-109">valueID</span><span class="sxs-lookup"><span data-stu-id="0042c-109">valueID</span></span></p></td>
<td><p><span data-ttu-id="0042c-110">smallint，不为 null</span><span class="sxs-lookup"><span data-stu-id="0042c-110">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="0042c-111">值的 ID。</span><span class="sxs-lookup"><span data-stu-id="0042c-111">ID of the value.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0042c-112">attributeID</span><span class="sxs-lookup"><span data-stu-id="0042c-112">attributeID</span></span></p></td>
<td><p><span data-ttu-id="0042c-113">smallint，不为 null</span><span class="sxs-lookup"><span data-stu-id="0042c-113">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="0042c-114">属性的 ID。</span><span class="sxs-lookup"><span data-stu-id="0042c-114">ID of the attribute.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0042c-115">attributeValue</span><span class="sxs-lookup"><span data-stu-id="0042c-115">attributeValue</span></span></p></td>
<td><p><span data-ttu-id="0042c-116">nvarchar  (256)，不为 null</span><span class="sxs-lookup"><span data-stu-id="0042c-116">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="0042c-117">值名称。</span><span class="sxs-lookup"><span data-stu-id="0042c-117">Name of the value.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="0042c-118">Keys</span><span class="sxs-lookup"><span data-stu-id="0042c-118">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0042c-119">列</span><span class="sxs-lookup"><span data-stu-id="0042c-119">Column</span></span></th>
<th><span data-ttu-id="0042c-120">说明</span><span class="sxs-lookup"><span data-stu-id="0042c-120">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0042c-121">valueID</span><span class="sxs-lookup"><span data-stu-id="0042c-121">valueID</span></span></p></td>
<td><p><span data-ttu-id="0042c-122">主键。</span><span class="sxs-lookup"><span data-stu-id="0042c-122">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0042c-123">attributeID</span><span class="sxs-lookup"><span data-stu-id="0042c-123">attributeID</span></span></p></td>
<td><p><span data-ttu-id="0042c-124">其查找包含在 tblEnumAttribute.attributeID 表中的外键。</span><span class="sxs-lookup"><span data-stu-id="0042c-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-values"></a><span data-ttu-id="0042c-125">表值</span><span class="sxs-lookup"><span data-stu-id="0042c-125">Table Values</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0042c-126">valueID</span><span class="sxs-lookup"><span data-stu-id="0042c-126">valueID</span></span></th>
<th><span data-ttu-id="0042c-127">attributeID</span><span class="sxs-lookup"><span data-stu-id="0042c-127">attributeID</span></span></th>
<th><span data-ttu-id="0042c-128">attributeValue</span><span class="sxs-lookup"><span data-stu-id="0042c-128">attributeValue</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0042c-129">双面</span><span class="sxs-lookup"><span data-stu-id="0042c-129">2</span></span></p></td>
<td><p><span data-ttu-id="0042c-130">1</span><span class="sxs-lookup"><span data-stu-id="0042c-130">1</span></span></p></td>
<td><p><span data-ttu-id="0042c-131">private</span><span class="sxs-lookup"><span data-stu-id="0042c-131">private</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0042c-132">第三章</span><span class="sxs-lookup"><span data-stu-id="0042c-132">3</span></span></p></td>
<td><p><span data-ttu-id="0042c-133">1</span><span class="sxs-lookup"><span data-stu-id="0042c-133">1</span></span></p></td>
<td><p><span data-ttu-id="0042c-134">范围</span><span class="sxs-lookup"><span data-stu-id="0042c-134">scope</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0042c-135">4</span><span class="sxs-lookup"><span data-stu-id="0042c-135">4</span></span></p></td>
<td><p><span data-ttu-id="0042c-136">双面</span><span class="sxs-lookup"><span data-stu-id="0042c-136">2</span></span></p></td>
<td><p><span data-ttu-id="0042c-137">通用</span><span class="sxs-lookup"><span data-stu-id="0042c-137">normal</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0042c-138">5</span><span class="sxs-lookup"><span data-stu-id="0042c-138">5</span></span></p></td>
<td><p><span data-ttu-id="0042c-139">双面</span><span class="sxs-lookup"><span data-stu-id="0042c-139">2</span></span></p></td>
<td><p><span data-ttu-id="0042c-140">大会堂</span><span class="sxs-lookup"><span data-stu-id="0042c-140">auditorium</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0042c-141">6 </span><span class="sxs-lookup"><span data-stu-id="0042c-141">6</span></span></p></td>
<td><p><span data-ttu-id="0042c-142">1</span><span class="sxs-lookup"><span data-stu-id="0042c-142">1</span></span></p></td>
<td><p><span data-ttu-id="0042c-143">open</span><span class="sxs-lookup"><span data-stu-id="0042c-143">open</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="0042c-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0042c-144">See Also</span></span>


[<span data-ttu-id="0042c-145">Lync Server 2013 中的 tblNode</span><span class="sxs-lookup"><span data-stu-id="0042c-145">tblNode in Lync Server 2013</span></span>](lync-server-2013-tblnode.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

