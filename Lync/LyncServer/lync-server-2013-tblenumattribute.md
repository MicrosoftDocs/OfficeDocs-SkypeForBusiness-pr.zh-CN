---
title: Lync Server 2013：tblEnumAttribute
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
ms.openlocfilehash: 73ac5a7cf26c97b31daf5785a90fac102c50e480
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764188"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblenumattribute-in-lync-server-2013"></a><span data-ttu-id="63fe7-102">Lync Server 2013 中的 tblEnumAttribute</span><span class="sxs-lookup"><span data-stu-id="63fe7-102">tblEnumAttribute in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="63fe7-103">_**主题上次修改时间：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="63fe7-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="63fe7-104">tblEnumAttribute 是一个硬编码表，其中包含在节点表中使用的 Visibility 和行为属性。</span><span class="sxs-lookup"><span data-stu-id="63fe7-104">tblEnumAttribute is a hardcoded table that contains the Visibility and Behavior attributes that are used in the Node table.</span></span>

### <a name="columns"></a><span data-ttu-id="63fe7-105">多</span><span class="sxs-lookup"><span data-stu-id="63fe7-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="63fe7-106">列</span><span class="sxs-lookup"><span data-stu-id="63fe7-106">Column</span></span></th>
<th><span data-ttu-id="63fe7-107">类型</span><span class="sxs-lookup"><span data-stu-id="63fe7-107">Type</span></span></th>
<th><span data-ttu-id="63fe7-108">说明</span><span class="sxs-lookup"><span data-stu-id="63fe7-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="63fe7-109">attributeID</span><span class="sxs-lookup"><span data-stu-id="63fe7-109">attributeID</span></span></p></td>
<td><p><span data-ttu-id="63fe7-110">smallint，not null</span><span class="sxs-lookup"><span data-stu-id="63fe7-110">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="63fe7-111">属性的 ID。</span><span class="sxs-lookup"><span data-stu-id="63fe7-111">ID of the attribute.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63fe7-112">attributeName</span><span class="sxs-lookup"><span data-stu-id="63fe7-112">attributeName</span></span></p></td>
<td><p><span data-ttu-id="63fe7-113">nvarchar （256），not null</span><span class="sxs-lookup"><span data-stu-id="63fe7-113">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="63fe7-114">属性的名称。</span><span class="sxs-lookup"><span data-stu-id="63fe7-114">Name of the attribute.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="63fe7-115">关键字</span><span class="sxs-lookup"><span data-stu-id="63fe7-115">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="63fe7-116">列</span><span class="sxs-lookup"><span data-stu-id="63fe7-116">Column</span></span></th>
<th><span data-ttu-id="63fe7-117">说明</span><span class="sxs-lookup"><span data-stu-id="63fe7-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="63fe7-118">attributeID</span><span class="sxs-lookup"><span data-stu-id="63fe7-118">attributeID</span></span></p></td>
<td><p><span data-ttu-id="63fe7-119">主键。</span><span class="sxs-lookup"><span data-stu-id="63fe7-119">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-values"></a><span data-ttu-id="63fe7-120">表值</span><span class="sxs-lookup"><span data-stu-id="63fe7-120">Table Values</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="63fe7-121">attributeID</span><span class="sxs-lookup"><span data-stu-id="63fe7-121">attributeID</span></span></th>
<th><span data-ttu-id="63fe7-122">attributeName</span><span class="sxs-lookup"><span data-stu-id="63fe7-122">attributeName</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="63fe7-123">1</span><span class="sxs-lookup"><span data-stu-id="63fe7-123">1</span></span></p></td>
<td><p><span data-ttu-id="63fe7-124">了解.</span><span class="sxs-lookup"><span data-stu-id="63fe7-124">Visibility.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63fe7-125">ppls-2</span><span class="sxs-lookup"><span data-stu-id="63fe7-125">2</span></span></p></td>
<td><p><span data-ttu-id="63fe7-126">现象.</span><span class="sxs-lookup"><span data-stu-id="63fe7-126">Behavior.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="63fe7-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="63fe7-127">See Also</span></span>


[<span data-ttu-id="63fe7-128">Lync Server 2013 中的 tblNode</span><span class="sxs-lookup"><span data-stu-id="63fe7-128">tblNode in Lync Server 2013</span></span>](lync-server-2013-tblnode.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

