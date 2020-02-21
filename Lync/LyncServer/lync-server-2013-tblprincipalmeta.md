---
title: Lync Server 2013： tblPrincipalMeta
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
ms.openlocfilehash: 04ad0fbdb9a4e3bb2e5962089fe1c30f960bdc91
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195215"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblprincipalmeta-in-lync-server-2013"></a><span data-ttu-id="e022f-102">Lync Server 2013 中的 tblPrincipalMeta</span><span class="sxs-lookup"><span data-stu-id="e022f-102">tblPrincipalMeta in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e022f-103">_**上次修改的主题：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="e022f-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="e022f-104">tblPrincipalMeta 包含必须从 Active Directory 域服务刷新的主体。</span><span class="sxs-lookup"><span data-stu-id="e022f-104">tblPrincipalMeta contains the principals that have to be refreshed from Active Directory Domain Services.</span></span>

### <a name="columns"></a><span data-ttu-id="e022f-105">Columns</span><span class="sxs-lookup"><span data-stu-id="e022f-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e022f-106">列</span><span class="sxs-lookup"><span data-stu-id="e022f-106">Column</span></span></th>
<th><span data-ttu-id="e022f-107">类型</span><span class="sxs-lookup"><span data-stu-id="e022f-107">Type</span></span></th>
<th><span data-ttu-id="e022f-108">说明</span><span class="sxs-lookup"><span data-stu-id="e022f-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e022f-109">prinID</span><span class="sxs-lookup"><span data-stu-id="e022f-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="e022f-110">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="e022f-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="e022f-111">主体 ID。</span><span class="sxs-lookup"><span data-stu-id="e022f-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e022f-112">prinAffiliationsDirty</span><span class="sxs-lookup"><span data-stu-id="e022f-112">prinAffiliationsDirty</span></span></p></td>
<td><p><span data-ttu-id="e022f-113">bit，不为 null</span><span class="sxs-lookup"><span data-stu-id="e022f-113">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="e022f-114">如果必须刷新主体附属关系，则为 True。</span><span class="sxs-lookup"><span data-stu-id="e022f-114">True if principal affiliations have to be refreshed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e022f-115">prinAttributesDirty</span><span class="sxs-lookup"><span data-stu-id="e022f-115">prinAttributesDirty</span></span></p></td>
<td><p><span data-ttu-id="e022f-116">bit，不为 null</span><span class="sxs-lookup"><span data-stu-id="e022f-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="e022f-117">如果必须刷新主体属性，则为 True。</span><span class="sxs-lookup"><span data-stu-id="e022f-117">True if principal attributes have to be refreshed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e022f-118">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="e022f-118">prinDeleted</span></span></p></td>
<td><p><span data-ttu-id="e022f-119">bit，不为 null</span><span class="sxs-lookup"><span data-stu-id="e022f-119">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="e022f-120">如果主体已删除，则为 True。</span><span class="sxs-lookup"><span data-stu-id="e022f-120">True if the principal has been deleted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e022f-121">tryCount</span><span class="sxs-lookup"><span data-stu-id="e022f-121">tryCount</span></span></p></td>
<td><p><span data-ttu-id="e022f-122">int</span><span class="sxs-lookup"><span data-stu-id="e022f-122">int</span></span></p></td>
<td><p><span data-ttu-id="e022f-123">截止目前，已发生的尝试从 AD DS 刷新主体的次数。</span><span class="sxs-lookup"><span data-stu-id="e022f-123">Number of attempts to refresh the principal from AD DS that have happened so far.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e022f-124">lastTry</span><span class="sxs-lookup"><span data-stu-id="e022f-124">lastTry</span></span></p></td>
<td><p><span data-ttu-id="e022f-125">datetime</span><span class="sxs-lookup"><span data-stu-id="e022f-125">datetime</span></span></p></td>
<td><p><span data-ttu-id="e022f-p101">最近尝试刷新主体的时间戳。如果尚未尝试任何刷新，可以为 null。</span><span class="sxs-lookup"><span data-stu-id="e022f-p101">Time stamp from the latest attempt to refresh the principal. Can be null if no refresh has been attempted yet.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e022f-128">nextTry</span><span class="sxs-lookup"><span data-stu-id="e022f-128">nextTry</span></span></p></td>
<td><p><span data-ttu-id="e022f-129">datetime</span><span class="sxs-lookup"><span data-stu-id="e022f-129">datetime</span></span></p></td>
<td><p><span data-ttu-id="e022f-p102">计划的下一次刷新的时间戳。如果尚未计划进一步刷新，可以为 null。</span><span class="sxs-lookup"><span data-stu-id="e022f-p102">Time stamp for the next scheduled refresh. Can be null if no further refresh has been scheduled.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="e022f-132">Keys</span><span class="sxs-lookup"><span data-stu-id="e022f-132">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e022f-133">列</span><span class="sxs-lookup"><span data-stu-id="e022f-133">Column</span></span></th>
<th><span data-ttu-id="e022f-134">说明</span><span class="sxs-lookup"><span data-stu-id="e022f-134">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e022f-135">prinID</span><span class="sxs-lookup"><span data-stu-id="e022f-135">prinID</span></span></p></td>
<td><p><span data-ttu-id="e022f-136">主键。</span><span class="sxs-lookup"><span data-stu-id="e022f-136">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e022f-137">prinID</span><span class="sxs-lookup"><span data-stu-id="e022f-137">prinID</span></span></p></td>
<td><p><span data-ttu-id="e022f-138">其查找包含在 tblPrincipal.prinID 表中的外键。</span><span class="sxs-lookup"><span data-stu-id="e022f-138">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

