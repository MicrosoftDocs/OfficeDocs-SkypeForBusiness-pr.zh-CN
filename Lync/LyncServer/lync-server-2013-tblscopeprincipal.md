---
title: Lync Server 2013：tblScopePrincipal
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblScopePrincipal
ms:assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558639(v=OCS.15)
ms:contentKeyID: 48184009
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ece5ae542060835aefa05edb6e08b766293e2ac1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845714"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblscopeprincipal-in-lync-server-2013"></a><span data-ttu-id="5f79a-102">Lync Server 2013 中的 tblScopePrincipal</span><span class="sxs-lookup"><span data-stu-id="5f79a-102">tblScopePrincipal in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5f79a-103">_**主题上次修改时间:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="5f79a-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="5f79a-104">tblScopePrincipal 包含分配给节点的作用域。</span><span class="sxs-lookup"><span data-stu-id="5f79a-104">tblScopePrincipal contains scopes assigned to nodes.</span></span>

### <a name="columns"></a><span data-ttu-id="5f79a-105">多</span><span class="sxs-lookup"><span data-stu-id="5f79a-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5f79a-106">列</span><span class="sxs-lookup"><span data-stu-id="5f79a-106">Column</span></span></th>
<th><span data-ttu-id="5f79a-107">类型</span><span class="sxs-lookup"><span data-stu-id="5f79a-107">Type</span></span></th>
<th><span data-ttu-id="5f79a-108">说明</span><span class="sxs-lookup"><span data-stu-id="5f79a-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5f79a-109">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="5f79a-109">scopeNodeID</span></span></p></td>
<td><p><span data-ttu-id="5f79a-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="5f79a-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="5f79a-111">作用域所适用的节点 ID。</span><span class="sxs-lookup"><span data-stu-id="5f79a-111">Node ID that the scope applies to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f79a-112">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="5f79a-112">scopePrinID</span></span></p></td>
<td><p><span data-ttu-id="5f79a-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="5f79a-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="5f79a-114">主体 ID。</span><span class="sxs-lookup"><span data-stu-id="5f79a-114">Principal ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f79a-115">scopeIsDenied</span><span class="sxs-lookup"><span data-stu-id="5f79a-115">scopeIsDenied</span></span></p></td>
<td><p><span data-ttu-id="5f79a-116">位, not null</span><span class="sxs-lookup"><span data-stu-id="5f79a-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="5f79a-117">如果范围的类型为 "拒绝", 则为 True;如果允许, 则为 False。</span><span class="sxs-lookup"><span data-stu-id="5f79a-117">True if type of scope is Deny; False if Allow.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f79a-118">scopeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="5f79a-118">scopeUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="5f79a-119">int, not null</span><span class="sxs-lookup"><span data-stu-id="5f79a-119">int, not null</span></span></p></td>
<td><p><span data-ttu-id="5f79a-120">上次更新此条目的主体的 ID。</span><span class="sxs-lookup"><span data-stu-id="5f79a-120">ID of the principal that last updated this entry.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="5f79a-121">标示</span><span class="sxs-lookup"><span data-stu-id="5f79a-121">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5f79a-122">列</span><span class="sxs-lookup"><span data-stu-id="5f79a-122">Column</span></span></th>
<th><span data-ttu-id="5f79a-123">说明</span><span class="sxs-lookup"><span data-stu-id="5f79a-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5f79a-124">&lt;scopeNodeID, scopePrinID&gt;</span><span class="sxs-lookup"><span data-stu-id="5f79a-124">&lt;scopeNodeID, scopePrinID&gt;</span></span></p></td>
<td><p><span data-ttu-id="5f79a-125">主键。</span><span class="sxs-lookup"><span data-stu-id="5f79a-125">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f79a-126">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="5f79a-126">scopeNodeID</span></span></p></td>
<td><p><span data-ttu-id="5f79a-127">带有 tblNode 表中的 lookup 的外键。</span><span class="sxs-lookup"><span data-stu-id="5f79a-127">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f79a-128">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="5f79a-128">scopePrinID</span></span></p></td>
<td><p><span data-ttu-id="5f79a-129">TblPrincipal 表中的 lookup 的外键。</span><span class="sxs-lookup"><span data-stu-id="5f79a-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

