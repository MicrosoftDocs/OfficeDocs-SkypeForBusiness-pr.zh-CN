---
title: Lync Server 2013： tblScopePrincipal
description: Lync Server 2013： tblScopePrincipal。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblScopePrincipal
ms:assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558639(v=OCS.15)
ms:contentKeyID: 48184009
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 63315f8525e5c2f05fe54a0f9ed9e8a97b9e8bce
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555608"
---
# <a name="tblscopeprincipal-in-lync-server-2013"></a><span data-ttu-id="11ee8-103">Lync Server 2013 中的 tblScopePrincipal</span><span class="sxs-lookup"><span data-stu-id="11ee8-103">tblScopePrincipal in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="11ee8-104">_**上次修改的主题：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="11ee8-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="11ee8-105">tblScopePrincipal 包含分配至节点的作用域。</span><span class="sxs-lookup"><span data-stu-id="11ee8-105">tblScopePrincipal contains scopes assigned to nodes.</span></span>

### <a name="columns"></a><span data-ttu-id="11ee8-106">列数</span><span class="sxs-lookup"><span data-stu-id="11ee8-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="11ee8-107">列</span><span class="sxs-lookup"><span data-stu-id="11ee8-107">Column</span></span></th>
<th><span data-ttu-id="11ee8-108">类型</span><span class="sxs-lookup"><span data-stu-id="11ee8-108">Type</span></span></th>
<th><span data-ttu-id="11ee8-109">说明</span><span class="sxs-lookup"><span data-stu-id="11ee8-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="11ee8-110">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="11ee8-110">scopeNodeID</span></span></p></td>
<td><p><span data-ttu-id="11ee8-111">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="11ee8-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="11ee8-112">作用域适用的节点 ID。</span><span class="sxs-lookup"><span data-stu-id="11ee8-112">Node ID that the scope applies to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11ee8-113">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="11ee8-113">scopePrinID</span></span></p></td>
<td><p><span data-ttu-id="11ee8-114">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="11ee8-114">int, not null</span></span></p></td>
<td><p><span data-ttu-id="11ee8-115">主体 ID。</span><span class="sxs-lookup"><span data-stu-id="11ee8-115">Principal ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11ee8-116">scopeIsDenied</span><span class="sxs-lookup"><span data-stu-id="11ee8-116">scopeIsDenied</span></span></p></td>
<td><p><span data-ttu-id="11ee8-117">bit，不为 null</span><span class="sxs-lookup"><span data-stu-id="11ee8-117">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="11ee8-118">如果作用域的类型为 Deny，则为 True；如果作用域的类型为 Allow，则为 False。</span><span class="sxs-lookup"><span data-stu-id="11ee8-118">True if type of scope is Deny; False if Allow.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11ee8-119">scopeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="11ee8-119">scopeUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="11ee8-120">int, 不为 null</span><span class="sxs-lookup"><span data-stu-id="11ee8-120">int, not null</span></span></p></td>
<td><p><span data-ttu-id="11ee8-121">上次更新此项的主体的 ID。</span><span class="sxs-lookup"><span data-stu-id="11ee8-121">ID of the principal that last updated this entry.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="11ee8-122">Keys</span><span class="sxs-lookup"><span data-stu-id="11ee8-122">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="11ee8-123">列</span><span class="sxs-lookup"><span data-stu-id="11ee8-123">Column</span></span></th>
<th><span data-ttu-id="11ee8-124">说明</span><span class="sxs-lookup"><span data-stu-id="11ee8-124">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="11ee8-125">&lt;scopeNodeID, scopePrinID&gt;</span><span class="sxs-lookup"><span data-stu-id="11ee8-125">&lt;scopeNodeID, scopePrinID&gt;</span></span></p></td>
<td><p><span data-ttu-id="11ee8-126">主键。</span><span class="sxs-lookup"><span data-stu-id="11ee8-126">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11ee8-127">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="11ee8-127">scopeNodeID</span></span></p></td>
<td><p><span data-ttu-id="11ee8-128">其查找包含在 tblNode.nodeID 表中的外键。</span><span class="sxs-lookup"><span data-stu-id="11ee8-128">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11ee8-129">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="11ee8-129">scopePrinID</span></span></p></td>
<td><p><span data-ttu-id="11ee8-130">其查找包含在 tblPrincipal.prinID 表中的外键。</span><span class="sxs-lookup"><span data-stu-id="11ee8-130">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

