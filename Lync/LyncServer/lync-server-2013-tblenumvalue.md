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
ms.openlocfilehash: 984dd5f161b31c40de914f363c0722657d3194ed
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142098"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblenumvalue-in-lync-server-2013"></a><span data-ttu-id="50101-102">Lync Server 2013 中的 tblEnumValue</span><span class="sxs-lookup"><span data-stu-id="50101-102">tblEnumValue in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="50101-103">_**上次修改的主题：** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="50101-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="50101-104">tblEnumValue 表是一个硬编码表，包含节点表使用的属性的“可见性”值和“行为”值。</span><span class="sxs-lookup"><span data-stu-id="50101-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>

### <a name="columns"></a><span data-ttu-id="50101-105">Columns</span><span class="sxs-lookup"><span data-stu-id="50101-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="50101-106">列</span><span class="sxs-lookup"><span data-stu-id="50101-106">Column</span></span></th>
<th><span data-ttu-id="50101-107">类型</span><span class="sxs-lookup"><span data-stu-id="50101-107">Type</span></span></th>
<th><span data-ttu-id="50101-108">说明</span><span class="sxs-lookup"><span data-stu-id="50101-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="50101-109">valueID</span><span class="sxs-lookup"><span data-stu-id="50101-109">valueID</span></span></p></td>
<td><p><span data-ttu-id="50101-110">smallint，不为 null</span><span class="sxs-lookup"><span data-stu-id="50101-110">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="50101-111">值的 ID。</span><span class="sxs-lookup"><span data-stu-id="50101-111">ID of the value.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50101-112">attributeID</span><span class="sxs-lookup"><span data-stu-id="50101-112">attributeID</span></span></p></td>
<td><p><span data-ttu-id="50101-113">smallint，不为 null</span><span class="sxs-lookup"><span data-stu-id="50101-113">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="50101-114">属性的 ID。</span><span class="sxs-lookup"><span data-stu-id="50101-114">ID of the attribute.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50101-115">attributeValue</span><span class="sxs-lookup"><span data-stu-id="50101-115">attributeValue</span></span></p></td>
<td><p><span data-ttu-id="50101-116">nvarchar  (256)，不为 null</span><span class="sxs-lookup"><span data-stu-id="50101-116">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="50101-117">值名称。</span><span class="sxs-lookup"><span data-stu-id="50101-117">Name of the value.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="50101-118">Keys</span><span class="sxs-lookup"><span data-stu-id="50101-118">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="50101-119">列</span><span class="sxs-lookup"><span data-stu-id="50101-119">Column</span></span></th>
<th><span data-ttu-id="50101-120">说明</span><span class="sxs-lookup"><span data-stu-id="50101-120">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="50101-121">valueID</span><span class="sxs-lookup"><span data-stu-id="50101-121">valueID</span></span></p></td>
<td><p><span data-ttu-id="50101-122">主键。</span><span class="sxs-lookup"><span data-stu-id="50101-122">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50101-123">attributeID</span><span class="sxs-lookup"><span data-stu-id="50101-123">attributeID</span></span></p></td>
<td><p><span data-ttu-id="50101-124">其查找包含在 tblEnumAttribute.attributeID 表中的外键。</span><span class="sxs-lookup"><span data-stu-id="50101-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-values"></a><span data-ttu-id="50101-125">表值</span><span class="sxs-lookup"><span data-stu-id="50101-125">Table Values</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="50101-126">valueID</span><span class="sxs-lookup"><span data-stu-id="50101-126">valueID</span></span></th>
<th><span data-ttu-id="50101-127">attributeID</span><span class="sxs-lookup"><span data-stu-id="50101-127">attributeID</span></span></th>
<th><span data-ttu-id="50101-128">attributeValue</span><span class="sxs-lookup"><span data-stu-id="50101-128">attributeValue</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="50101-129">双面</span><span class="sxs-lookup"><span data-stu-id="50101-129">2</span></span></p></td>
<td><p><span data-ttu-id="50101-130">1</span><span class="sxs-lookup"><span data-stu-id="50101-130">1</span></span></p></td>
<td><p><span data-ttu-id="50101-131">private</span><span class="sxs-lookup"><span data-stu-id="50101-131">private</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50101-132">第三章</span><span class="sxs-lookup"><span data-stu-id="50101-132">3</span></span></p></td>
<td><p><span data-ttu-id="50101-133">1</span><span class="sxs-lookup"><span data-stu-id="50101-133">1</span></span></p></td>
<td><p><span data-ttu-id="50101-134">范围</span><span class="sxs-lookup"><span data-stu-id="50101-134">scope</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50101-135">4</span><span class="sxs-lookup"><span data-stu-id="50101-135">4</span></span></p></td>
<td><p><span data-ttu-id="50101-136">双面</span><span class="sxs-lookup"><span data-stu-id="50101-136">2</span></span></p></td>
<td><p><span data-ttu-id="50101-137">通用</span><span class="sxs-lookup"><span data-stu-id="50101-137">normal</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50101-138">5</span><span class="sxs-lookup"><span data-stu-id="50101-138">5</span></span></p></td>
<td><p><span data-ttu-id="50101-139">双面</span><span class="sxs-lookup"><span data-stu-id="50101-139">2</span></span></p></td>
<td><p><span data-ttu-id="50101-140">大会堂</span><span class="sxs-lookup"><span data-stu-id="50101-140">auditorium</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50101-141">6 </span><span class="sxs-lookup"><span data-stu-id="50101-141">6</span></span></p></td>
<td><p><span data-ttu-id="50101-142">1</span><span class="sxs-lookup"><span data-stu-id="50101-142">1</span></span></p></td>
<td><p><span data-ttu-id="50101-143">open</span><span class="sxs-lookup"><span data-stu-id="50101-143">open</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="50101-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="50101-144">See Also</span></span>


[<span data-ttu-id="50101-145">Lync Server 2013 中的 tblNode</span><span class="sxs-lookup"><span data-stu-id="50101-145">tblNode in Lync Server 2013</span></span>](lync-server-2013-tblnode.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

