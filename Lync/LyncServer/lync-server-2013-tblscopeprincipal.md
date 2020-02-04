---
title: Lync Server 2013：tblScopePrincipal
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
ms.openlocfilehash: 72c6f15b2f0a219871436fe4451984abfddc947a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764072"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblscopeprincipal-in-lync-server-2013"></a><span data-ttu-id="d160b-102">Lync Server 2013 中的 tblScopePrincipal</span><span class="sxs-lookup"><span data-stu-id="d160b-102">tblScopePrincipal in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d160b-103">_**主题上次修改时间：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="d160b-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="d160b-104">tblScopePrincipal 包含分配给节点的作用域。</span><span class="sxs-lookup"><span data-stu-id="d160b-104">tblScopePrincipal contains scopes assigned to nodes.</span></span>

### <a name="columns"></a><span data-ttu-id="d160b-105">多</span><span class="sxs-lookup"><span data-stu-id="d160b-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d160b-106">列</span><span class="sxs-lookup"><span data-stu-id="d160b-106">Column</span></span></th>
<th><span data-ttu-id="d160b-107">类型</span><span class="sxs-lookup"><span data-stu-id="d160b-107">Type</span></span></th>
<th><span data-ttu-id="d160b-108">说明</span><span class="sxs-lookup"><span data-stu-id="d160b-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d160b-109">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="d160b-109">scopeNodeID</span></span></p></td>
<td><p><span data-ttu-id="d160b-110">int，not null</span><span class="sxs-lookup"><span data-stu-id="d160b-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="d160b-111">作用域所适用的节点 ID。</span><span class="sxs-lookup"><span data-stu-id="d160b-111">Node ID that the scope applies to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d160b-112">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="d160b-112">scopePrinID</span></span></p></td>
<td><p><span data-ttu-id="d160b-113">int，not null</span><span class="sxs-lookup"><span data-stu-id="d160b-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="d160b-114">主体 ID。</span><span class="sxs-lookup"><span data-stu-id="d160b-114">Principal ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d160b-115">scopeIsDenied</span><span class="sxs-lookup"><span data-stu-id="d160b-115">scopeIsDenied</span></span></p></td>
<td><p><span data-ttu-id="d160b-116">位，not null</span><span class="sxs-lookup"><span data-stu-id="d160b-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="d160b-117">如果范围的类型为 "拒绝"，则为 True;如果允许，则为 False。</span><span class="sxs-lookup"><span data-stu-id="d160b-117">True if type of scope is Deny; False if Allow.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d160b-118">scopeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="d160b-118">scopeUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="d160b-119">int，not null</span><span class="sxs-lookup"><span data-stu-id="d160b-119">int, not null</span></span></p></td>
<td><p><span data-ttu-id="d160b-120">上次更新此条目的主体的 ID。</span><span class="sxs-lookup"><span data-stu-id="d160b-120">ID of the principal that last updated this entry.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="d160b-121">标示</span><span class="sxs-lookup"><span data-stu-id="d160b-121">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d160b-122">列</span><span class="sxs-lookup"><span data-stu-id="d160b-122">Column</span></span></th>
<th><span data-ttu-id="d160b-123">说明</span><span class="sxs-lookup"><span data-stu-id="d160b-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d160b-124">&lt;scopeNodeID, scopePrinID&gt;</span><span class="sxs-lookup"><span data-stu-id="d160b-124">&lt;scopeNodeID, scopePrinID&gt;</span></span></p></td>
<td><p><span data-ttu-id="d160b-125">主键。</span><span class="sxs-lookup"><span data-stu-id="d160b-125">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d160b-126">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="d160b-126">scopeNodeID</span></span></p></td>
<td><p><span data-ttu-id="d160b-127">带有 tblNode 表中的 lookup 的外键。</span><span class="sxs-lookup"><span data-stu-id="d160b-127">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d160b-128">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="d160b-128">scopePrinID</span></span></p></td>
<td><p><span data-ttu-id="d160b-129">TblPrincipal 表中的 lookup 的外键。</span><span class="sxs-lookup"><span data-stu-id="d160b-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

