---
title: Lync Server 2013： tblPrincipalInvites
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
ms.openlocfilehash: 5165adf5b9cb5ddeefe80895217e6b2265784855
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214446"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblprincipalinvites-in-lync-server-2013"></a><span data-ttu-id="e0969-102">Lync Server 2013 中的 tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="e0969-102">tblPrincipalInvites in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e0969-103">_**上次修改的主题：** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="e0969-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="e0969-104">tblPrincipalInvites 包含打开自动邀请的所有节点的所有已设置用户的邀请。</span><span class="sxs-lookup"><span data-stu-id="e0969-104">tblPrincipalInvites contains invitations for all provisioned users for all nodes with auto-invite on.</span></span>

### <a name="columns"></a><span data-ttu-id="e0969-105">Columns</span><span class="sxs-lookup"><span data-stu-id="e0969-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e0969-106">列</span><span class="sxs-lookup"><span data-stu-id="e0969-106">Column</span></span></th>
<th><span data-ttu-id="e0969-107">类型</span><span class="sxs-lookup"><span data-stu-id="e0969-107">Type</span></span></th>
<th><span data-ttu-id="e0969-108">说明</span><span class="sxs-lookup"><span data-stu-id="e0969-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e0969-109">prinID</span><span class="sxs-lookup"><span data-stu-id="e0969-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="e0969-110">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="e0969-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="e0969-111">主体 ID。</span><span class="sxs-lookup"><span data-stu-id="e0969-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0969-112">invID</span><span class="sxs-lookup"><span data-stu-id="e0969-112">invID</span></span></p></td>
<td><p><span data-ttu-id="e0969-113">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="e0969-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="e0969-114">从 tblLastInviteId 表中生成的唯一连续数字（每个主体 ID）。</span><span class="sxs-lookup"><span data-stu-id="e0969-114">Unique sequential number (per principal ID) generated from tblLastInviteId table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0969-115">个</span><span class="sxs-lookup"><span data-stu-id="e0969-115">nodeID</span></span></p></td>
<td><p><span data-ttu-id="e0969-116">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="e0969-116">int, not null</span></span></p></td>
<td><p><span data-ttu-id="e0969-117">节点 ID（仅聊天室）。</span><span class="sxs-lookup"><span data-stu-id="e0969-117">Node ID (chat room only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0969-118">createdOn</span><span class="sxs-lookup"><span data-stu-id="e0969-118">createdOn</span></span></p></td>
<td><p><span data-ttu-id="e0969-119">datetime，不为 null</span><span class="sxs-lookup"><span data-stu-id="e0969-119">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="e0969-120">创建的时间。</span><span class="sxs-lookup"><span data-stu-id="e0969-120">Time of creation.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="e0969-121">Keys</span><span class="sxs-lookup"><span data-stu-id="e0969-121">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e0969-122">列</span><span class="sxs-lookup"><span data-stu-id="e0969-122">Column</span></span></th>
<th><span data-ttu-id="e0969-123">说明</span><span class="sxs-lookup"><span data-stu-id="e0969-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e0969-124">&lt;prinID、&gt;</span><span class="sxs-lookup"><span data-stu-id="e0969-124">&lt;prinID, nodeID&gt;</span></span></p></td>
<td><p><span data-ttu-id="e0969-125">主键。</span><span class="sxs-lookup"><span data-stu-id="e0969-125">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0969-126">prinID</span><span class="sxs-lookup"><span data-stu-id="e0969-126">prinID</span></span></p></td>
<td><p><span data-ttu-id="e0969-127">其查找包含在 tblPrincipal.prinID 表中的外键。</span><span class="sxs-lookup"><span data-stu-id="e0969-127">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0969-128">个</span><span class="sxs-lookup"><span data-stu-id="e0969-128">nodeID</span></span></p></td>
<td><p><span data-ttu-id="e0969-129">其查找包含在 tblNode.nodeID 表中的外键。</span><span class="sxs-lookup"><span data-stu-id="e0969-129">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

