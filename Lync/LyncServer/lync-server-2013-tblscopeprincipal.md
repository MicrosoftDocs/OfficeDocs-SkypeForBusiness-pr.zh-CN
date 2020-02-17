---
title: Lync Server 2013： tblScopePrincipal
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
ms.openlocfilehash: ab3faccea0ba914ca17c9aefcd0ea112e5b58a96
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037472"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblscopeprincipal-in-lync-server-2013"></a><span data-ttu-id="48b6d-102">Lync Server 2013 中的 tblScopePrincipal</span><span class="sxs-lookup"><span data-stu-id="48b6d-102">tblScopePrincipal in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="48b6d-103">_**上次修改的主题：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="48b6d-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="48b6d-104">tblScopePrincipal 包含分配至节点的作用域。</span><span class="sxs-lookup"><span data-stu-id="48b6d-104">tblScopePrincipal contains scopes assigned to nodes.</span></span>

### <a name="columns"></a><span data-ttu-id="48b6d-105">Columns</span><span class="sxs-lookup"><span data-stu-id="48b6d-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="48b6d-106">列</span><span class="sxs-lookup"><span data-stu-id="48b6d-106">Column</span></span></th>
<th><span data-ttu-id="48b6d-107">类型</span><span class="sxs-lookup"><span data-stu-id="48b6d-107">Type</span></span></th>
<th><span data-ttu-id="48b6d-108">描述</span><span class="sxs-lookup"><span data-stu-id="48b6d-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="48b6d-109">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="48b6d-109">scopeNodeID</span></span></p></td>
<td><p><span data-ttu-id="48b6d-110">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="48b6d-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="48b6d-111">作用域适用的节点 ID。</span><span class="sxs-lookup"><span data-stu-id="48b6d-111">Node ID that the scope applies to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48b6d-112">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="48b6d-112">scopePrinID</span></span></p></td>
<td><p><span data-ttu-id="48b6d-113">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="48b6d-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="48b6d-114">主体 ID。</span><span class="sxs-lookup"><span data-stu-id="48b6d-114">Principal ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48b6d-115">scopeIsDenied</span><span class="sxs-lookup"><span data-stu-id="48b6d-115">scopeIsDenied</span></span></p></td>
<td><p><span data-ttu-id="48b6d-116">bit，不为 null</span><span class="sxs-lookup"><span data-stu-id="48b6d-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="48b6d-117">如果作用域的类型为 Deny，则为 True；如果作用域的类型为 Allow，则为 False。</span><span class="sxs-lookup"><span data-stu-id="48b6d-117">True if type of scope is Deny; False if Allow.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48b6d-118">scopeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="48b6d-118">scopeUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="48b6d-119">int, 不为 null</span><span class="sxs-lookup"><span data-stu-id="48b6d-119">int, not null</span></span></p></td>
<td><p><span data-ttu-id="48b6d-120">上次更新此项的主体的 ID。</span><span class="sxs-lookup"><span data-stu-id="48b6d-120">ID of the principal that last updated this entry.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="48b6d-121">Keys</span><span class="sxs-lookup"><span data-stu-id="48b6d-121">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="48b6d-122">列</span><span class="sxs-lookup"><span data-stu-id="48b6d-122">Column</span></span></th>
<th><span data-ttu-id="48b6d-123">说明</span><span class="sxs-lookup"><span data-stu-id="48b6d-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="48b6d-124">&lt;scopeNodeID, scopePrinID&gt;</span><span class="sxs-lookup"><span data-stu-id="48b6d-124">&lt;scopeNodeID, scopePrinID&gt;</span></span></p></td>
<td><p><span data-ttu-id="48b6d-125">主键。</span><span class="sxs-lookup"><span data-stu-id="48b6d-125">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48b6d-126">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="48b6d-126">scopeNodeID</span></span></p></td>
<td><p><span data-ttu-id="48b6d-127">其查找包含在 tblNode.nodeID 表中的外键。</span><span class="sxs-lookup"><span data-stu-id="48b6d-127">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48b6d-128">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="48b6d-128">scopePrinID</span></span></p></td>
<td><p><span data-ttu-id="48b6d-129">其查找包含在 tblPrincipal.prinID 表中的外键。</span><span class="sxs-lookup"><span data-stu-id="48b6d-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

