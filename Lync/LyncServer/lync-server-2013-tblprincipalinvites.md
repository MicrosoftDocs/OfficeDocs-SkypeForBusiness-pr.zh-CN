---
title: Lync Server 2013：tblPrincipalInvites
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalInvites
ms:assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558650(v=OCS.15)
ms:contentKeyID: 48184141
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 75d842772c8c0e02352eacf7f80711aa79c29461
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731522"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipalinvites-in-lync-server-2013"></a><span data-ttu-id="dae55-102">Lync Server 2013 中的 tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="dae55-102">tblPrincipalInvites in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dae55-103">_**主题上次修改时间：** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="dae55-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="dae55-104">tblPrincipalInvites 包含所有已预配用户的带有自动邀请的所有节点的邀请。</span><span class="sxs-lookup"><span data-stu-id="dae55-104">tblPrincipalInvites contains invitations for all provisioned users for all nodes with auto-invite on.</span></span>

### <a name="columns"></a><span data-ttu-id="dae55-105">多</span><span class="sxs-lookup"><span data-stu-id="dae55-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dae55-106">列</span><span class="sxs-lookup"><span data-stu-id="dae55-106">Column</span></span></th>
<th><span data-ttu-id="dae55-107">类型</span><span class="sxs-lookup"><span data-stu-id="dae55-107">Type</span></span></th>
<th><span data-ttu-id="dae55-108">说明</span><span class="sxs-lookup"><span data-stu-id="dae55-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dae55-109">prinID</span><span class="sxs-lookup"><span data-stu-id="dae55-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="dae55-110">int，not null</span><span class="sxs-lookup"><span data-stu-id="dae55-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="dae55-111">主体 ID。</span><span class="sxs-lookup"><span data-stu-id="dae55-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dae55-112">invID</span><span class="sxs-lookup"><span data-stu-id="dae55-112">invID</span></span></p></td>
<td><p><span data-ttu-id="dae55-113">int，not null</span><span class="sxs-lookup"><span data-stu-id="dae55-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="dae55-114">从 tblLastInviteId 表生成的唯一序列号（每个主体 ID）。</span><span class="sxs-lookup"><span data-stu-id="dae55-114">Unique sequential number (per principal ID) generated from tblLastInviteId table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dae55-115">a</span><span class="sxs-lookup"><span data-stu-id="dae55-115">nodeID</span></span></p></td>
<td><p><span data-ttu-id="dae55-116">int，not null</span><span class="sxs-lookup"><span data-stu-id="dae55-116">int, not null</span></span></p></td>
<td><p><span data-ttu-id="dae55-117">节点 ID （仅聊天室）。</span><span class="sxs-lookup"><span data-stu-id="dae55-117">Node ID (chat room only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dae55-118">createdOn</span><span class="sxs-lookup"><span data-stu-id="dae55-118">createdOn</span></span></p></td>
<td><p><span data-ttu-id="dae55-119">datetime，not null</span><span class="sxs-lookup"><span data-stu-id="dae55-119">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="dae55-120">创建时间。</span><span class="sxs-lookup"><span data-stu-id="dae55-120">Time of creation.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="dae55-121">标示</span><span class="sxs-lookup"><span data-stu-id="dae55-121">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dae55-122">列</span><span class="sxs-lookup"><span data-stu-id="dae55-122">Column</span></span></th>
<th><span data-ttu-id="dae55-123">说明</span><span class="sxs-lookup"><span data-stu-id="dae55-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dae55-124">&lt;prinID、&gt;</span><span class="sxs-lookup"><span data-stu-id="dae55-124">&lt;prinID, nodeID&gt;</span></span></p></td>
<td><p><span data-ttu-id="dae55-125">主键。</span><span class="sxs-lookup"><span data-stu-id="dae55-125">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dae55-126">prinID</span><span class="sxs-lookup"><span data-stu-id="dae55-126">prinID</span></span></p></td>
<td><p><span data-ttu-id="dae55-127">TblPrincipal 表中的 lookup 的外键。</span><span class="sxs-lookup"><span data-stu-id="dae55-127">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dae55-128">a</span><span class="sxs-lookup"><span data-stu-id="dae55-128">nodeID</span></span></p></td>
<td><p><span data-ttu-id="dae55-129">带有 tblNode 表中的 lookup 的外键。</span><span class="sxs-lookup"><span data-stu-id="dae55-129">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

