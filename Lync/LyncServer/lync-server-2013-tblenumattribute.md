---
title: Lync Server 2013： tblEnumAttribute
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblEnumAttribute
ms:assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558617(v=OCS.15)
ms:contentKeyID: 48183523
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f3b015d1148c3c820c27cdbe48e191bd09d2f55e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509349"
---
# <a name="tblenumattribute-in-lync-server-2013"></a><span data-ttu-id="4e841-102">Lync Server 2013 中的 tblEnumAttribute</span><span class="sxs-lookup"><span data-stu-id="4e841-102">tblEnumAttribute in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4e841-103">_**上次修改的主题：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="4e841-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="4e841-104">tblEnumAttribute 是一个硬编码表，包含用于节点表的 Visibility 和 Behavior 属性。</span><span class="sxs-lookup"><span data-stu-id="4e841-104">tblEnumAttribute is a hardcoded table that contains the Visibility and Behavior attributes that are used in the Node table.</span></span>

### <a name="columns"></a><span data-ttu-id="4e841-105">列数</span><span class="sxs-lookup"><span data-stu-id="4e841-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4e841-106">列</span><span class="sxs-lookup"><span data-stu-id="4e841-106">Column</span></span></th>
<th><span data-ttu-id="4e841-107">类型</span><span class="sxs-lookup"><span data-stu-id="4e841-107">Type</span></span></th>
<th><span data-ttu-id="4e841-108">说明</span><span class="sxs-lookup"><span data-stu-id="4e841-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4e841-109">attributeID</span><span class="sxs-lookup"><span data-stu-id="4e841-109">attributeID</span></span></p></td>
<td><p><span data-ttu-id="4e841-110">smallint，不为 null</span><span class="sxs-lookup"><span data-stu-id="4e841-110">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="4e841-111">属性的 ID。</span><span class="sxs-lookup"><span data-stu-id="4e841-111">ID of the attribute.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e841-112">attributeName</span><span class="sxs-lookup"><span data-stu-id="4e841-112">attributeName</span></span></p></td>
<td><p><span data-ttu-id="4e841-113">nvarchar (256)，不为 null</span><span class="sxs-lookup"><span data-stu-id="4e841-113">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="4e841-114">属性的名称。</span><span class="sxs-lookup"><span data-stu-id="4e841-114">Name of the attribute.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="4e841-115">键</span><span class="sxs-lookup"><span data-stu-id="4e841-115">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4e841-116">列</span><span class="sxs-lookup"><span data-stu-id="4e841-116">Column</span></span></th>
<th><span data-ttu-id="4e841-117">说明</span><span class="sxs-lookup"><span data-stu-id="4e841-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4e841-118">attributeID</span><span class="sxs-lookup"><span data-stu-id="4e841-118">attributeID</span></span></p></td>
<td><p><span data-ttu-id="4e841-119">主键。</span><span class="sxs-lookup"><span data-stu-id="4e841-119">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-values"></a><span data-ttu-id="4e841-120">表值</span><span class="sxs-lookup"><span data-stu-id="4e841-120">Table Values</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4e841-121">attributeID</span><span class="sxs-lookup"><span data-stu-id="4e841-121">attributeID</span></span></th>
<th><span data-ttu-id="4e841-122">attributeName</span><span class="sxs-lookup"><span data-stu-id="4e841-122">attributeName</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4e841-123">1</span><span class="sxs-lookup"><span data-stu-id="4e841-123">1</span></span></p></td>
<td><p><span data-ttu-id="4e841-124">深入.</span><span class="sxs-lookup"><span data-stu-id="4e841-124">Visibility.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e841-125">双面</span><span class="sxs-lookup"><span data-stu-id="4e841-125">2</span></span></p></td>
<td><p><span data-ttu-id="4e841-126">性能.</span><span class="sxs-lookup"><span data-stu-id="4e841-126">Behavior.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="4e841-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4e841-127">See Also</span></span>


[<span data-ttu-id="4e841-128">Lync Server 2013 中的 tblNode</span><span class="sxs-lookup"><span data-stu-id="4e841-128">tblNode in Lync Server 2013</span></span>](lync-server-2013-tblnode.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

