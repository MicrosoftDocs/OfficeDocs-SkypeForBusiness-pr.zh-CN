---
title: Lync Server 2013：tblPrincipalMeta
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalMeta
ms:assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615009(v=OCS.15)
ms:contentKeyID: 48184648
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 848f4dc19ddf64c53c2dd30ae6ca4c8036b67c79
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764092"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipalmeta-in-lync-server-2013"></a><span data-ttu-id="79c14-102">Lync Server 2013 中的 tblPrincipalMeta</span><span class="sxs-lookup"><span data-stu-id="79c14-102">tblPrincipalMeta in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="79c14-103">_**主题上次修改时间：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="79c14-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="79c14-104">tblPrincipalMeta 包含必须从 Active Directory 域服务刷新的主体。</span><span class="sxs-lookup"><span data-stu-id="79c14-104">tblPrincipalMeta contains the principals that have to be refreshed from Active Directory Domain Services.</span></span>

### <a name="columns"></a><span data-ttu-id="79c14-105">多</span><span class="sxs-lookup"><span data-stu-id="79c14-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="79c14-106">列</span><span class="sxs-lookup"><span data-stu-id="79c14-106">Column</span></span></th>
<th><span data-ttu-id="79c14-107">类型</span><span class="sxs-lookup"><span data-stu-id="79c14-107">Type</span></span></th>
<th><span data-ttu-id="79c14-108">说明</span><span class="sxs-lookup"><span data-stu-id="79c14-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="79c14-109">prinID</span><span class="sxs-lookup"><span data-stu-id="79c14-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="79c14-110">int，not null</span><span class="sxs-lookup"><span data-stu-id="79c14-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="79c14-111">主体 ID。</span><span class="sxs-lookup"><span data-stu-id="79c14-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79c14-112">prinAffiliationsDirty</span><span class="sxs-lookup"><span data-stu-id="79c14-112">prinAffiliationsDirty</span></span></p></td>
<td><p><span data-ttu-id="79c14-113">位，not null</span><span class="sxs-lookup"><span data-stu-id="79c14-113">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="79c14-114">如果必须刷新主体隶属关系，则为 True。</span><span class="sxs-lookup"><span data-stu-id="79c14-114">True if principal affiliations have to be refreshed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79c14-115">prinAttributesDirty</span><span class="sxs-lookup"><span data-stu-id="79c14-115">prinAttributesDirty</span></span></p></td>
<td><p><span data-ttu-id="79c14-116">位，not null</span><span class="sxs-lookup"><span data-stu-id="79c14-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="79c14-117">如果必须刷新主体属性，则为 True。</span><span class="sxs-lookup"><span data-stu-id="79c14-117">True if principal attributes have to be refreshed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79c14-118">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="79c14-118">prinDeleted</span></span></p></td>
<td><p><span data-ttu-id="79c14-119">位，not null</span><span class="sxs-lookup"><span data-stu-id="79c14-119">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="79c14-120">如果主体已被删除，则为 True。</span><span class="sxs-lookup"><span data-stu-id="79c14-120">True if the principal has been deleted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79c14-121">tryCount</span><span class="sxs-lookup"><span data-stu-id="79c14-121">tryCount</span></span></p></td>
<td><p><span data-ttu-id="79c14-122">int</span><span class="sxs-lookup"><span data-stu-id="79c14-122">int</span></span></p></td>
<td><p><span data-ttu-id="79c14-123">尝试从目前为止发生的 AD DS 刷新主体的次数。</span><span class="sxs-lookup"><span data-stu-id="79c14-123">Number of attempts to refresh the principal from AD DS that have happened so far.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79c14-124">lastTry</span><span class="sxs-lookup"><span data-stu-id="79c14-124">lastTry</span></span></p></td>
<td><p><span data-ttu-id="79c14-125">datetime</span><span class="sxs-lookup"><span data-stu-id="79c14-125">datetime</span></span></p></td>
<td><p><span data-ttu-id="79c14-126">从最新尝试刷新主体的时间戳。</span><span class="sxs-lookup"><span data-stu-id="79c14-126">Time stamp from the latest attempt to refresh the principal.</span></span> <span data-ttu-id="79c14-127">如果尚未尝试刷新，则可以为 null。</span><span class="sxs-lookup"><span data-stu-id="79c14-127">Can be null if no refresh has been attempted yet.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79c14-128">nextTry</span><span class="sxs-lookup"><span data-stu-id="79c14-128">nextTry</span></span></p></td>
<td><p><span data-ttu-id="79c14-129">datetime</span><span class="sxs-lookup"><span data-stu-id="79c14-129">datetime</span></span></p></td>
<td><p><span data-ttu-id="79c14-130">下一次计划刷新的时间戳。</span><span class="sxs-lookup"><span data-stu-id="79c14-130">Time stamp for the next scheduled refresh.</span></span> <span data-ttu-id="79c14-131">如果尚未安排进一步刷新，则可以为 null。</span><span class="sxs-lookup"><span data-stu-id="79c14-131">Can be null if no further refresh has been scheduled.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="79c14-132">标示</span><span class="sxs-lookup"><span data-stu-id="79c14-132">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="79c14-133">列</span><span class="sxs-lookup"><span data-stu-id="79c14-133">Column</span></span></th>
<th><span data-ttu-id="79c14-134">说明</span><span class="sxs-lookup"><span data-stu-id="79c14-134">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="79c14-135">prinID</span><span class="sxs-lookup"><span data-stu-id="79c14-135">prinID</span></span></p></td>
<td><p><span data-ttu-id="79c14-136">主键。</span><span class="sxs-lookup"><span data-stu-id="79c14-136">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79c14-137">prinID</span><span class="sxs-lookup"><span data-stu-id="79c14-137">prinID</span></span></p></td>
<td><p><span data-ttu-id="79c14-138">TblPrincipal 表中的 lookup 的外键。</span><span class="sxs-lookup"><span data-stu-id="79c14-138">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

