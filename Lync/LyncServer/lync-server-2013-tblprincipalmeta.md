---
title: Lync Server 2013： tblPrincipalMeta
description: Lync Server 2013： tblPrincipalMeta。
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
ms.openlocfilehash: 899fd1e450dac52afa56c1ee1de86da82b2db309
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573638"
---
# <a name="tblprincipalmeta-in-lync-server-2013"></a><span data-ttu-id="69a29-103">Lync Server 2013 中的 tblPrincipalMeta</span><span class="sxs-lookup"><span data-stu-id="69a29-103">tblPrincipalMeta in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="69a29-104">_**上次修改的主题：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="69a29-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="69a29-105">tblPrincipalMeta 包含必须从 Active Directory 域服务刷新的主体。</span><span class="sxs-lookup"><span data-stu-id="69a29-105">tblPrincipalMeta contains the principals that have to be refreshed from Active Directory Domain Services.</span></span>

### <a name="columns"></a><span data-ttu-id="69a29-106">列数</span><span class="sxs-lookup"><span data-stu-id="69a29-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="69a29-107">列</span><span class="sxs-lookup"><span data-stu-id="69a29-107">Column</span></span></th>
<th><span data-ttu-id="69a29-108">类型</span><span class="sxs-lookup"><span data-stu-id="69a29-108">Type</span></span></th>
<th><span data-ttu-id="69a29-109">说明</span><span class="sxs-lookup"><span data-stu-id="69a29-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="69a29-110">prinID</span><span class="sxs-lookup"><span data-stu-id="69a29-110">prinID</span></span></p></td>
<td><p><span data-ttu-id="69a29-111">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="69a29-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="69a29-112">主体 ID。</span><span class="sxs-lookup"><span data-stu-id="69a29-112">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69a29-113">prinAffiliationsDirty</span><span class="sxs-lookup"><span data-stu-id="69a29-113">prinAffiliationsDirty</span></span></p></td>
<td><p><span data-ttu-id="69a29-114">bit，不为 null</span><span class="sxs-lookup"><span data-stu-id="69a29-114">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="69a29-115">如果必须刷新主体附属关系，则为 True。</span><span class="sxs-lookup"><span data-stu-id="69a29-115">True if principal affiliations have to be refreshed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69a29-116">prinAttributesDirty</span><span class="sxs-lookup"><span data-stu-id="69a29-116">prinAttributesDirty</span></span></p></td>
<td><p><span data-ttu-id="69a29-117">bit，不为 null</span><span class="sxs-lookup"><span data-stu-id="69a29-117">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="69a29-118">如果必须刷新主体属性，则为 True。</span><span class="sxs-lookup"><span data-stu-id="69a29-118">True if principal attributes have to be refreshed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69a29-119">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="69a29-119">prinDeleted</span></span></p></td>
<td><p><span data-ttu-id="69a29-120">bit，不为 null</span><span class="sxs-lookup"><span data-stu-id="69a29-120">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="69a29-121">如果主体已删除，则为 True。</span><span class="sxs-lookup"><span data-stu-id="69a29-121">True if the principal has been deleted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69a29-122">tryCount</span><span class="sxs-lookup"><span data-stu-id="69a29-122">tryCount</span></span></p></td>
<td><p><span data-ttu-id="69a29-123">int</span><span class="sxs-lookup"><span data-stu-id="69a29-123">int</span></span></p></td>
<td><p><span data-ttu-id="69a29-124">截止目前，已发生的尝试从 AD DS 刷新主体的次数。</span><span class="sxs-lookup"><span data-stu-id="69a29-124">Number of attempts to refresh the principal from AD DS that have happened so far.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69a29-125">lastTry</span><span class="sxs-lookup"><span data-stu-id="69a29-125">lastTry</span></span></p></td>
<td><p><span data-ttu-id="69a29-126">datetime</span><span class="sxs-lookup"><span data-stu-id="69a29-126">datetime</span></span></p></td>
<td><p><span data-ttu-id="69a29-p101">最近尝试刷新主体的时间戳。如果尚未尝试任何刷新，可以为 null。</span><span class="sxs-lookup"><span data-stu-id="69a29-p101">Time stamp from the latest attempt to refresh the principal. Can be null if no refresh has been attempted yet.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69a29-129">nextTry</span><span class="sxs-lookup"><span data-stu-id="69a29-129">nextTry</span></span></p></td>
<td><p><span data-ttu-id="69a29-130">datetime</span><span class="sxs-lookup"><span data-stu-id="69a29-130">datetime</span></span></p></td>
<td><p><span data-ttu-id="69a29-p102">计划的下一次刷新的时间戳。如果尚未计划进一步刷新，可以为 null。</span><span class="sxs-lookup"><span data-stu-id="69a29-p102">Time stamp for the next scheduled refresh. Can be null if no further refresh has been scheduled.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="69a29-133">Keys</span><span class="sxs-lookup"><span data-stu-id="69a29-133">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="69a29-134">列</span><span class="sxs-lookup"><span data-stu-id="69a29-134">Column</span></span></th>
<th><span data-ttu-id="69a29-135">说明</span><span class="sxs-lookup"><span data-stu-id="69a29-135">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="69a29-136">prinID</span><span class="sxs-lookup"><span data-stu-id="69a29-136">prinID</span></span></p></td>
<td><p><span data-ttu-id="69a29-137">主键。</span><span class="sxs-lookup"><span data-stu-id="69a29-137">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69a29-138">prinID</span><span class="sxs-lookup"><span data-stu-id="69a29-138">prinID</span></span></p></td>
<td><p><span data-ttu-id="69a29-139">其查找包含在 tblPrincipal.prinID 表中的外键。</span><span class="sxs-lookup"><span data-stu-id="69a29-139">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

