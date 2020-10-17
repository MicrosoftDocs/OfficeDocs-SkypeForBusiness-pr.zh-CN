---
title: Lync Server 2013： tblPrincipalInvites
description: Lync Server 2013： tblPrincipalInvites。
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
ms.openlocfilehash: d30d741864ed2a3cfbec8329215be33c21b3b262
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564668"
---
# <a name="tblprincipalinvites-in-lync-server-2013"></a><span data-ttu-id="c6adc-103">Lync Server 2013 中的 tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="c6adc-103">tblPrincipalInvites in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c6adc-104">_**上次修改的主题：** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="c6adc-104">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="c6adc-105">tblPrincipalInvites 包含打开自动邀请的所有节点的所有已设置用户的邀请。</span><span class="sxs-lookup"><span data-stu-id="c6adc-105">tblPrincipalInvites contains invitations for all provisioned users for all nodes with auto-invite on.</span></span>

### <a name="columns"></a><span data-ttu-id="c6adc-106">列数</span><span class="sxs-lookup"><span data-stu-id="c6adc-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c6adc-107">列</span><span class="sxs-lookup"><span data-stu-id="c6adc-107">Column</span></span></th>
<th><span data-ttu-id="c6adc-108">类型</span><span class="sxs-lookup"><span data-stu-id="c6adc-108">Type</span></span></th>
<th><span data-ttu-id="c6adc-109">说明</span><span class="sxs-lookup"><span data-stu-id="c6adc-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c6adc-110">prinID</span><span class="sxs-lookup"><span data-stu-id="c6adc-110">prinID</span></span></p></td>
<td><p><span data-ttu-id="c6adc-111">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="c6adc-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="c6adc-112">主体 ID。</span><span class="sxs-lookup"><span data-stu-id="c6adc-112">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6adc-113">invID</span><span class="sxs-lookup"><span data-stu-id="c6adc-113">invID</span></span></p></td>
<td><p><span data-ttu-id="c6adc-114">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="c6adc-114">int, not null</span></span></p></td>
<td><p><span data-ttu-id="c6adc-115">从 tblLastInviteId 表中生成的唯一连续数字（每个主体 ID）。</span><span class="sxs-lookup"><span data-stu-id="c6adc-115">Unique sequential number (per principal ID) generated from tblLastInviteId table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6adc-116">个</span><span class="sxs-lookup"><span data-stu-id="c6adc-116">nodeID</span></span></p></td>
<td><p><span data-ttu-id="c6adc-117">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="c6adc-117">int, not null</span></span></p></td>
<td><p><span data-ttu-id="c6adc-118">节点 ID（仅聊天室）。</span><span class="sxs-lookup"><span data-stu-id="c6adc-118">Node ID (chat room only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6adc-119">createdOn</span><span class="sxs-lookup"><span data-stu-id="c6adc-119">createdOn</span></span></p></td>
<td><p><span data-ttu-id="c6adc-120">datetime，不为 null</span><span class="sxs-lookup"><span data-stu-id="c6adc-120">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="c6adc-121">创建的时间。</span><span class="sxs-lookup"><span data-stu-id="c6adc-121">Time of creation.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="c6adc-122">Keys</span><span class="sxs-lookup"><span data-stu-id="c6adc-122">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c6adc-123">列</span><span class="sxs-lookup"><span data-stu-id="c6adc-123">Column</span></span></th>
<th><span data-ttu-id="c6adc-124">说明</span><span class="sxs-lookup"><span data-stu-id="c6adc-124">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c6adc-125">&lt;prinID、&gt;</span><span class="sxs-lookup"><span data-stu-id="c6adc-125">&lt;prinID, nodeID&gt;</span></span></p></td>
<td><p><span data-ttu-id="c6adc-126">主键。</span><span class="sxs-lookup"><span data-stu-id="c6adc-126">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6adc-127">prinID</span><span class="sxs-lookup"><span data-stu-id="c6adc-127">prinID</span></span></p></td>
<td><p><span data-ttu-id="c6adc-128">其查找包含在 tblPrincipal.prinID 表中的外键。</span><span class="sxs-lookup"><span data-stu-id="c6adc-128">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6adc-129">个</span><span class="sxs-lookup"><span data-stu-id="c6adc-129">nodeID</span></span></p></td>
<td><p><span data-ttu-id="c6adc-130">其查找包含在 tblNode.nodeID 表中的外键。</span><span class="sxs-lookup"><span data-stu-id="c6adc-130">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

