---
title: Lync Server 2013： tblPrincipalRole
description: Lync Server 2013： tblPrincipalRole。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalRole
ms:assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615039(v=OCS.15)
ms:contentKeyID: 48185597
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f58ffda3136c254ee77f14d33dcb42af5d172c4a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573628"
---
# <a name="tblprincipalrole-in-lync-server-2013"></a><span data-ttu-id="8df10-103">Lync Server 2013 中的 tblPrincipalRole</span><span class="sxs-lookup"><span data-stu-id="8df10-103">tblPrincipalRole in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8df10-104">_**上次修改的主题：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="8df10-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="8df10-105">tblPrincipalRole 包含分配给节点的显式角色。</span><span class="sxs-lookup"><span data-stu-id="8df10-105">tblPrincipalRole contains explicit roles assigned to nodes.</span></span>

### <a name="columns"></a><span data-ttu-id="8df10-106">列数</span><span class="sxs-lookup"><span data-stu-id="8df10-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8df10-107">列</span><span class="sxs-lookup"><span data-stu-id="8df10-107">Column</span></span></th>
<th><span data-ttu-id="8df10-108">类型</span><span class="sxs-lookup"><span data-stu-id="8df10-108">Type</span></span></th>
<th><span data-ttu-id="8df10-109">说明</span><span class="sxs-lookup"><span data-stu-id="8df10-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8df10-110">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="8df10-110">prinRoleNodeID</span></span></p></td>
<td><p><span data-ttu-id="8df10-111">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="8df10-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="8df10-112">该角色应用于的节点 ID。</span><span class="sxs-lookup"><span data-stu-id="8df10-112">Node ID that the role applies to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8df10-113">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="8df10-113">prinRolePrinID</span></span></p></td>
<td><p><span data-ttu-id="8df10-114">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="8df10-114">int, not null</span></span></p></td>
<td><p><span data-ttu-id="8df10-115">主体 ID。</span><span class="sxs-lookup"><span data-stu-id="8df10-115">Principal ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8df10-116">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="8df10-116">prinRoleTypeID</span></span></p></td>
<td><p><span data-ttu-id="8df10-117">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="8df10-117">int, not null</span></span></p></td>
<td><p><span data-ttu-id="8df10-118">从 tblRoleType)  (的角色类型 ID。</span><span class="sxs-lookup"><span data-stu-id="8df10-118">Role type ID (from tblRoleType).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8df10-119">prinRoleUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="8df10-119">prinRoleUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="8df10-120">int, 不为 null</span><span class="sxs-lookup"><span data-stu-id="8df10-120">int, not null</span></span></p></td>
<td><p><span data-ttu-id="8df10-121">上次更新此项的主体的 ID。</span><span class="sxs-lookup"><span data-stu-id="8df10-121">ID of the principal that last updated this entry.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="8df10-122">Keys</span><span class="sxs-lookup"><span data-stu-id="8df10-122">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8df10-123">列</span><span class="sxs-lookup"><span data-stu-id="8df10-123">Column</span></span></th>
<th><span data-ttu-id="8df10-124">说明</span><span class="sxs-lookup"><span data-stu-id="8df10-124">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8df10-125">&lt;prinRoleNodeID, prinRolePrinID, prinRoleTypeID&gt;</span><span class="sxs-lookup"><span data-stu-id="8df10-125">&lt;prinRoleNodeID, prinRolePrinID, prinRoleTypeID&gt;</span></span></p></td>
<td><p><span data-ttu-id="8df10-126">主键。</span><span class="sxs-lookup"><span data-stu-id="8df10-126">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8df10-127">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="8df10-127">prinRoleNodeID</span></span></p></td>
<td><p><span data-ttu-id="8df10-128">其查找包含在 tblNode.nodeID 表中的外键。</span><span class="sxs-lookup"><span data-stu-id="8df10-128">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8df10-129">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="8df10-129">prinRolePrinID</span></span></p></td>
<td><p><span data-ttu-id="8df10-130">其查找包含在 tblPrincipal.prinID 表中的外键。</span><span class="sxs-lookup"><span data-stu-id="8df10-130">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8df10-131">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="8df10-131">prinRoleTypeID</span></span></p></td>
<td><p><span data-ttu-id="8df10-132">包含 tblRoleType 表中的 lookup 的外键。</span><span class="sxs-lookup"><span data-stu-id="8df10-132">Foreign key with lookup in tblRoleType.rtypeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

