---
title: Lync Server 2013： tblPrincipalRole
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
ms.openlocfilehash: d4da9525e81856989c5d5046e43b2277ca6a8b2a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141978"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblprincipalrole-in-lync-server-2013"></a><span data-ttu-id="8f1a5-102">Lync Server 2013 中的 tblPrincipalRole</span><span class="sxs-lookup"><span data-stu-id="8f1a5-102">tblPrincipalRole in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8f1a5-103">_**上次修改的主题：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="8f1a5-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="8f1a5-104">tblPrincipalRole 包含分配给节点的显式角色。</span><span class="sxs-lookup"><span data-stu-id="8f1a5-104">tblPrincipalRole contains explicit roles assigned to nodes.</span></span>

### <a name="columns"></a><span data-ttu-id="8f1a5-105">Columns</span><span class="sxs-lookup"><span data-stu-id="8f1a5-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8f1a5-106">列</span><span class="sxs-lookup"><span data-stu-id="8f1a5-106">Column</span></span></th>
<th><span data-ttu-id="8f1a5-107">类型</span><span class="sxs-lookup"><span data-stu-id="8f1a5-107">Type</span></span></th>
<th><span data-ttu-id="8f1a5-108">说明</span><span class="sxs-lookup"><span data-stu-id="8f1a5-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8f1a5-109">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="8f1a5-109">prinRoleNodeID</span></span></p></td>
<td><p><span data-ttu-id="8f1a5-110">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="8f1a5-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="8f1a5-111">该角色应用于的节点 ID。</span><span class="sxs-lookup"><span data-stu-id="8f1a5-111">Node ID that the role applies to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f1a5-112">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="8f1a5-112">prinRolePrinID</span></span></p></td>
<td><p><span data-ttu-id="8f1a5-113">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="8f1a5-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="8f1a5-114">主体 ID。</span><span class="sxs-lookup"><span data-stu-id="8f1a5-114">Principal ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f1a5-115">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="8f1a5-115">prinRoleTypeID</span></span></p></td>
<td><p><span data-ttu-id="8f1a5-116">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="8f1a5-116">int, not null</span></span></p></td>
<td><p><span data-ttu-id="8f1a5-117">角色类型 ID （从 tblRoleType）。</span><span class="sxs-lookup"><span data-stu-id="8f1a5-117">Role type ID (from tblRoleType).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f1a5-118">prinRoleUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="8f1a5-118">prinRoleUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="8f1a5-119">int, 不为 null</span><span class="sxs-lookup"><span data-stu-id="8f1a5-119">int, not null</span></span></p></td>
<td><p><span data-ttu-id="8f1a5-120">上次更新此项的主体的 ID。</span><span class="sxs-lookup"><span data-stu-id="8f1a5-120">ID of the principal that last updated this entry.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="8f1a5-121">Keys</span><span class="sxs-lookup"><span data-stu-id="8f1a5-121">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8f1a5-122">列</span><span class="sxs-lookup"><span data-stu-id="8f1a5-122">Column</span></span></th>
<th><span data-ttu-id="8f1a5-123">说明</span><span class="sxs-lookup"><span data-stu-id="8f1a5-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8f1a5-124">&lt;prinRoleNodeID, prinRolePrinID, prinRoleTypeID&gt;</span><span class="sxs-lookup"><span data-stu-id="8f1a5-124">&lt;prinRoleNodeID, prinRolePrinID, prinRoleTypeID&gt;</span></span></p></td>
<td><p><span data-ttu-id="8f1a5-125">主键。</span><span class="sxs-lookup"><span data-stu-id="8f1a5-125">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f1a5-126">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="8f1a5-126">prinRoleNodeID</span></span></p></td>
<td><p><span data-ttu-id="8f1a5-127">其查找包含在 tblNode.nodeID 表中的外键。</span><span class="sxs-lookup"><span data-stu-id="8f1a5-127">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f1a5-128">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="8f1a5-128">prinRolePrinID</span></span></p></td>
<td><p><span data-ttu-id="8f1a5-129">其查找包含在 tblPrincipal.prinID 表中的外键。</span><span class="sxs-lookup"><span data-stu-id="8f1a5-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f1a5-130">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="8f1a5-130">prinRoleTypeID</span></span></p></td>
<td><p><span data-ttu-id="8f1a5-131">包含 tblRoleType 表中的 lookup 的外键。</span><span class="sxs-lookup"><span data-stu-id="8f1a5-131">Foreign key with lookup in tblRoleType.rtypeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

