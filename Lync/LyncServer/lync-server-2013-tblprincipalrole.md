---
title: Lync Server 2013：tblPrincipalRole
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
ms.openlocfilehash: de125c0f314bd0ba72b9bbd463201b12d3e19eea
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731172"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipalrole-in-lync-server-2013"></a><span data-ttu-id="2afc1-102">Lync Server 2013 中的 tblPrincipalRole</span><span class="sxs-lookup"><span data-stu-id="2afc1-102">tblPrincipalRole in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2afc1-103">_**主题上次修改时间：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="2afc1-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="2afc1-104">tblPrincipalRole 包含分配给节点的显式角色。</span><span class="sxs-lookup"><span data-stu-id="2afc1-104">tblPrincipalRole contains explicit roles assigned to nodes.</span></span>

### <a name="columns"></a><span data-ttu-id="2afc1-105">多</span><span class="sxs-lookup"><span data-stu-id="2afc1-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2afc1-106">列</span><span class="sxs-lookup"><span data-stu-id="2afc1-106">Column</span></span></th>
<th><span data-ttu-id="2afc1-107">类型</span><span class="sxs-lookup"><span data-stu-id="2afc1-107">Type</span></span></th>
<th><span data-ttu-id="2afc1-108">说明</span><span class="sxs-lookup"><span data-stu-id="2afc1-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2afc1-109">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="2afc1-109">prinRoleNodeID</span></span></p></td>
<td><p><span data-ttu-id="2afc1-110">int，not null</span><span class="sxs-lookup"><span data-stu-id="2afc1-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="2afc1-111">角色所应用的节点 ID。</span><span class="sxs-lookup"><span data-stu-id="2afc1-111">Node ID that the role applies to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2afc1-112">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="2afc1-112">prinRolePrinID</span></span></p></td>
<td><p><span data-ttu-id="2afc1-113">int，not null</span><span class="sxs-lookup"><span data-stu-id="2afc1-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="2afc1-114">主体 ID。</span><span class="sxs-lookup"><span data-stu-id="2afc1-114">Principal ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2afc1-115">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="2afc1-115">prinRoleTypeID</span></span></p></td>
<td><p><span data-ttu-id="2afc1-116">int，not null</span><span class="sxs-lookup"><span data-stu-id="2afc1-116">int, not null</span></span></p></td>
<td><p><span data-ttu-id="2afc1-117">角色类型 ID （来自 tblRoleType）。</span><span class="sxs-lookup"><span data-stu-id="2afc1-117">Role type ID (from tblRoleType).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2afc1-118">prinRoleUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="2afc1-118">prinRoleUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="2afc1-119">int，not null</span><span class="sxs-lookup"><span data-stu-id="2afc1-119">int, not null</span></span></p></td>
<td><p><span data-ttu-id="2afc1-120">上次更新此条目的主体的 ID。</span><span class="sxs-lookup"><span data-stu-id="2afc1-120">ID of the principal that last updated this entry.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="2afc1-121">标示</span><span class="sxs-lookup"><span data-stu-id="2afc1-121">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2afc1-122">列</span><span class="sxs-lookup"><span data-stu-id="2afc1-122">Column</span></span></th>
<th><span data-ttu-id="2afc1-123">说明</span><span class="sxs-lookup"><span data-stu-id="2afc1-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2afc1-124">&lt;prinRoleNodeID, prinRolePrinID, prinRoleTypeID&gt;</span><span class="sxs-lookup"><span data-stu-id="2afc1-124">&lt;prinRoleNodeID, prinRolePrinID, prinRoleTypeID&gt;</span></span></p></td>
<td><p><span data-ttu-id="2afc1-125">主键。</span><span class="sxs-lookup"><span data-stu-id="2afc1-125">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2afc1-126">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="2afc1-126">prinRoleNodeID</span></span></p></td>
<td><p><span data-ttu-id="2afc1-127">带有 tblNode 表中的 lookup 的外键。</span><span class="sxs-lookup"><span data-stu-id="2afc1-127">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2afc1-128">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="2afc1-128">prinRolePrinID</span></span></p></td>
<td><p><span data-ttu-id="2afc1-129">TblPrincipal 表中的 lookup 的外键。</span><span class="sxs-lookup"><span data-stu-id="2afc1-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2afc1-130">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="2afc1-130">prinRoleTypeID</span></span></p></td>
<td><p><span data-ttu-id="2afc1-131">TblRoleType 表中的 lookup 的外键。</span><span class="sxs-lookup"><span data-stu-id="2afc1-131">Foreign key with lookup in tblRoleType.rtypeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

