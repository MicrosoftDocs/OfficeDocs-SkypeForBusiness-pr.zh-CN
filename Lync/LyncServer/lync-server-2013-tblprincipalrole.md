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
ms.openlocfilehash: 76dda06baa4e5fab51ca44586f7f8fce00860695
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523609"
---
# <a name="tblprincipalrole-in-lync-server-2013"></a><span data-ttu-id="22919-102">Lync Server 2013 中的 tblPrincipalRole</span><span class="sxs-lookup"><span data-stu-id="22919-102">tblPrincipalRole in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="22919-103">_**上次修改的主题：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="22919-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="22919-104">tblPrincipalRole 包含分配给节点的显式角色。</span><span class="sxs-lookup"><span data-stu-id="22919-104">tblPrincipalRole contains explicit roles assigned to nodes.</span></span>

### <a name="columns"></a><span data-ttu-id="22919-105">列数</span><span class="sxs-lookup"><span data-stu-id="22919-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="22919-106">列</span><span class="sxs-lookup"><span data-stu-id="22919-106">Column</span></span></th>
<th><span data-ttu-id="22919-107">类型</span><span class="sxs-lookup"><span data-stu-id="22919-107">Type</span></span></th>
<th><span data-ttu-id="22919-108">说明</span><span class="sxs-lookup"><span data-stu-id="22919-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="22919-109">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="22919-109">prinRoleNodeID</span></span></p></td>
<td><p><span data-ttu-id="22919-110">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="22919-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="22919-111">该角色应用于的节点 ID。</span><span class="sxs-lookup"><span data-stu-id="22919-111">Node ID that the role applies to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22919-112">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="22919-112">prinRolePrinID</span></span></p></td>
<td><p><span data-ttu-id="22919-113">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="22919-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="22919-114">主体 ID。</span><span class="sxs-lookup"><span data-stu-id="22919-114">Principal ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22919-115">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="22919-115">prinRoleTypeID</span></span></p></td>
<td><p><span data-ttu-id="22919-116">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="22919-116">int, not null</span></span></p></td>
<td><p><span data-ttu-id="22919-117">从 tblRoleType)  (的角色类型 ID。</span><span class="sxs-lookup"><span data-stu-id="22919-117">Role type ID (from tblRoleType).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22919-118">prinRoleUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="22919-118">prinRoleUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="22919-119">int, 不为 null</span><span class="sxs-lookup"><span data-stu-id="22919-119">int, not null</span></span></p></td>
<td><p><span data-ttu-id="22919-120">上次更新此项的主体的 ID。</span><span class="sxs-lookup"><span data-stu-id="22919-120">ID of the principal that last updated this entry.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="22919-121">Keys</span><span class="sxs-lookup"><span data-stu-id="22919-121">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="22919-122">列</span><span class="sxs-lookup"><span data-stu-id="22919-122">Column</span></span></th>
<th><span data-ttu-id="22919-123">说明</span><span class="sxs-lookup"><span data-stu-id="22919-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="22919-124">&lt;prinRoleNodeID, prinRolePrinID, prinRoleTypeID&gt;</span><span class="sxs-lookup"><span data-stu-id="22919-124">&lt;prinRoleNodeID, prinRolePrinID, prinRoleTypeID&gt;</span></span></p></td>
<td><p><span data-ttu-id="22919-125">主键。</span><span class="sxs-lookup"><span data-stu-id="22919-125">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22919-126">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="22919-126">prinRoleNodeID</span></span></p></td>
<td><p><span data-ttu-id="22919-127">其查找包含在 tblNode.nodeID 表中的外键。</span><span class="sxs-lookup"><span data-stu-id="22919-127">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22919-128">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="22919-128">prinRolePrinID</span></span></p></td>
<td><p><span data-ttu-id="22919-129">其查找包含在 tblPrincipal.prinID 表中的外键。</span><span class="sxs-lookup"><span data-stu-id="22919-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22919-130">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="22919-130">prinRoleTypeID</span></span></p></td>
<td><p><span data-ttu-id="22919-131">包含 tblRoleType 表中的 lookup 的外键。</span><span class="sxs-lookup"><span data-stu-id="22919-131">Foreign key with lookup in tblRoleType.rtypeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

