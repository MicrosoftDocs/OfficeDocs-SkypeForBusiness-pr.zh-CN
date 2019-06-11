---
title: Lync Server 2013：tblEnumValue
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblEnumValue
ms:assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615025(v=OCS.15)
ms:contentKeyID: 48185040
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1758daf16575491960415647e4c9bc4b43920d26
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845747"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblenumvalue-in-lync-server-2013"></a><span data-ttu-id="d9e10-102">Lync Server 2013 中的 tblEnumValue</span><span class="sxs-lookup"><span data-stu-id="d9e10-102">tblEnumValue in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d9e10-103">_**主题上次修改时间:** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="d9e10-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="d9e10-104">tblEnumValue 是一个硬编码表, 其中包含在节点表中使用的属性的可见性和行为值。</span><span class="sxs-lookup"><span data-stu-id="d9e10-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>

### <a name="columns"></a><span data-ttu-id="d9e10-105">多</span><span class="sxs-lookup"><span data-stu-id="d9e10-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d9e10-106">列</span><span class="sxs-lookup"><span data-stu-id="d9e10-106">Column</span></span></th>
<th><span data-ttu-id="d9e10-107">类型</span><span class="sxs-lookup"><span data-stu-id="d9e10-107">Type</span></span></th>
<th><span data-ttu-id="d9e10-108">说明</span><span class="sxs-lookup"><span data-stu-id="d9e10-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d9e10-109">valueID</span><span class="sxs-lookup"><span data-stu-id="d9e10-109">valueID</span></span></p></td>
<td><p><span data-ttu-id="d9e10-110">smallint, not null</span><span class="sxs-lookup"><span data-stu-id="d9e10-110">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="d9e10-111">值的 ID。</span><span class="sxs-lookup"><span data-stu-id="d9e10-111">ID of the value.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d9e10-112">attributeID</span><span class="sxs-lookup"><span data-stu-id="d9e10-112">attributeID</span></span></p></td>
<td><p><span data-ttu-id="d9e10-113">smallint, not null</span><span class="sxs-lookup"><span data-stu-id="d9e10-113">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="d9e10-114">属性的 ID。</span><span class="sxs-lookup"><span data-stu-id="d9e10-114">ID of the attribute.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d9e10-115">attributeValue</span><span class="sxs-lookup"><span data-stu-id="d9e10-115">attributeValue</span></span></p></td>
<td><p><span data-ttu-id="d9e10-116">nvarchar (256), not null</span><span class="sxs-lookup"><span data-stu-id="d9e10-116">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="d9e10-117">值的名称。</span><span class="sxs-lookup"><span data-stu-id="d9e10-117">Name of the value.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="d9e10-118">标示</span><span class="sxs-lookup"><span data-stu-id="d9e10-118">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d9e10-119">列</span><span class="sxs-lookup"><span data-stu-id="d9e10-119">Column</span></span></th>
<th><span data-ttu-id="d9e10-120">说明</span><span class="sxs-lookup"><span data-stu-id="d9e10-120">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d9e10-121">valueID</span><span class="sxs-lookup"><span data-stu-id="d9e10-121">valueID</span></span></p></td>
<td><p><span data-ttu-id="d9e10-122">主键。</span><span class="sxs-lookup"><span data-stu-id="d9e10-122">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d9e10-123">attributeID</span><span class="sxs-lookup"><span data-stu-id="d9e10-123">attributeID</span></span></p></td>
<td><p><span data-ttu-id="d9e10-124">TblEnumAttribute 表中的 lookup 的外键。</span><span class="sxs-lookup"><span data-stu-id="d9e10-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-values"></a><span data-ttu-id="d9e10-125">表值</span><span class="sxs-lookup"><span data-stu-id="d9e10-125">Table Values</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d9e10-126">valueID</span><span class="sxs-lookup"><span data-stu-id="d9e10-126">valueID</span></span></th>
<th><span data-ttu-id="d9e10-127">attributeID</span><span class="sxs-lookup"><span data-stu-id="d9e10-127">attributeID</span></span></th>
<th><span data-ttu-id="d9e10-128">attributeValue</span><span class="sxs-lookup"><span data-stu-id="d9e10-128">attributeValue</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d9e10-129">2</span><span class="sxs-lookup"><span data-stu-id="d9e10-129">2</span></span></p></td>
<td><p><span data-ttu-id="d9e10-130">1</span><span class="sxs-lookup"><span data-stu-id="d9e10-130">1</span></span></p></td>
<td><p><span data-ttu-id="d9e10-131">专用</span><span class="sxs-lookup"><span data-stu-id="d9e10-131">private</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d9e10-132">3</span><span class="sxs-lookup"><span data-stu-id="d9e10-132">3</span></span></p></td>
<td><p><span data-ttu-id="d9e10-133">1</span><span class="sxs-lookup"><span data-stu-id="d9e10-133">1</span></span></p></td>
<td><p><span data-ttu-id="d9e10-134">范畴</span><span class="sxs-lookup"><span data-stu-id="d9e10-134">scope</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d9e10-135">4</span><span class="sxs-lookup"><span data-stu-id="d9e10-135">4</span></span></p></td>
<td><p><span data-ttu-id="d9e10-136">2</span><span class="sxs-lookup"><span data-stu-id="d9e10-136">2</span></span></p></td>
<td><p><span data-ttu-id="d9e10-137">垂直</span><span class="sxs-lookup"><span data-stu-id="d9e10-137">normal</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d9e10-138">5</span><span class="sxs-lookup"><span data-stu-id="d9e10-138">5</span></span></p></td>
<td><p><span data-ttu-id="d9e10-139">2</span><span class="sxs-lookup"><span data-stu-id="d9e10-139">2</span></span></p></td>
<td><p><span data-ttu-id="d9e10-140">auditorium</span><span class="sxs-lookup"><span data-stu-id="d9e10-140">auditorium</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d9e10-141">6</span><span class="sxs-lookup"><span data-stu-id="d9e10-141">6</span></span></p></td>
<td><p><span data-ttu-id="d9e10-142">1</span><span class="sxs-lookup"><span data-stu-id="d9e10-142">1</span></span></p></td>
<td><p><span data-ttu-id="d9e10-143">公开</span><span class="sxs-lookup"><span data-stu-id="d9e10-143">open</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="d9e10-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d9e10-144">See Also</span></span>


[<span data-ttu-id="d9e10-145">Lync Server 2013 中的 tblNode</span><span class="sxs-lookup"><span data-stu-id="d9e10-145">tblNode in Lync Server 2013</span></span>](lync-server-2013-tblnode.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

