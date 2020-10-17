---
title: Lync Server 2013： tblPrincipalAffiliations
description: Lync Server 2013： tblPrincipalAffiliations。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalAffiliations
ms:assetid: 45fd8484-5837-44d2-85bb-45c83546607c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558642(v=OCS.15)
ms:contentKeyID: 48183993
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 01c373147a58300e64f22e60e989a777c59b2653
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547478"
---
# <a name="tblprincipalaffiliations-in-lync-server-2013"></a><span data-ttu-id="ac8ce-103">Lync Server 2013 中的 tblPrincipalAffiliations</span><span class="sxs-lookup"><span data-stu-id="ac8ce-103">tblPrincipalAffiliations in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ac8ce-104">_**上次修改的主题：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="ac8ce-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="ac8ce-105">tblPrincipalAffiliations 包含描述位置中的成员身份的主体隶属关系，包括 Active directory 域服务安全组，在 Active Directory 容器中的域中。</span><span class="sxs-lookup"><span data-stu-id="ac8ce-105">tblPrincipalAffiliations contains the principal affiliations that describe memberships in locations, including Active Directory Domain Services security groups, in Active Directory containers, in domains.</span></span>

### <a name="columns"></a><span data-ttu-id="ac8ce-106">列数</span><span class="sxs-lookup"><span data-stu-id="ac8ce-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ac8ce-107">列</span><span class="sxs-lookup"><span data-stu-id="ac8ce-107">Column</span></span></th>
<th><span data-ttu-id="ac8ce-108">类型</span><span class="sxs-lookup"><span data-stu-id="ac8ce-108">Type</span></span></th>
<th><span data-ttu-id="ac8ce-109">说明</span><span class="sxs-lookup"><span data-stu-id="ac8ce-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ac8ce-110">principalID</span><span class="sxs-lookup"><span data-stu-id="ac8ce-110">principalID</span></span></p></td>
<td><p><span data-ttu-id="ac8ce-111">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="ac8ce-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="ac8ce-112">附属主体的 ID。</span><span class="sxs-lookup"><span data-stu-id="ac8ce-112">ID of the affiliated principal.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac8ce-113">affiliationID</span><span class="sxs-lookup"><span data-stu-id="ac8ce-113">affiliationID</span></span></p></td>
<td><p><span data-ttu-id="ac8ce-114">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="ac8ce-114">int, not null</span></span></p></td>
<td><p><span data-ttu-id="ac8ce-p101">表示附属关系的主体的 ID。每个主体（系统用户类型除外）还具有自附属关系。</span><span class="sxs-lookup"><span data-stu-id="ac8ce-p101">ID of the principal representing the affiliation. Each principal (except system-user-types) has a self-affiliation as well.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac8ce-117">index</span><span class="sxs-lookup"><span data-stu-id="ac8ce-117">index</span></span></p></td>
<td><p><span data-ttu-id="ac8ce-118">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="ac8ce-118">int, not null</span></span></p></td>
<td><p><span data-ttu-id="ac8ce-119">索引.</span><span class="sxs-lookup"><span data-stu-id="ac8ce-119">Index.</span></span> <span data-ttu-id="ac8ce-120">自隶属关系的值是-1，对于其他隶属关系，它会从每个 &lt; principalID、affiliationId 存储桶内的1依次增加 &gt; 。</span><span class="sxs-lookup"><span data-stu-id="ac8ce-120">The value for self-affiliations is -1, and for the other affiliations it increases sequentially from 1 within each &lt;principalID, affiliationId&gt; bucket.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac8ce-121">updatedBy</span><span class="sxs-lookup"><span data-stu-id="ac8ce-121">updatedBy</span></span></p></td>
<td><p><span data-ttu-id="ac8ce-122">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="ac8ce-122">int, not null</span></span></p></td>
<td><p><span data-ttu-id="ac8ce-p103">进行最新更新的主体。这通常为 1，表示 Active Directory 同步。</span><span class="sxs-lookup"><span data-stu-id="ac8ce-p103">Principal that did the latest update. This is usually 1, which means Active Directory Sync.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="ac8ce-125">Keys</span><span class="sxs-lookup"><span data-stu-id="ac8ce-125">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ac8ce-126">列数</span><span class="sxs-lookup"><span data-stu-id="ac8ce-126">Columns</span></span></th>
<th><span data-ttu-id="ac8ce-127">说明</span><span class="sxs-lookup"><span data-stu-id="ac8ce-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ac8ce-128">&lt;principalID、index、affiliationID&gt;</span><span class="sxs-lookup"><span data-stu-id="ac8ce-128">&lt;principalID, index, affiliationID&gt;</span></span></p></td>
<td><p><span data-ttu-id="ac8ce-129">主键。</span><span class="sxs-lookup"><span data-stu-id="ac8ce-129">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac8ce-130">principalID</span><span class="sxs-lookup"><span data-stu-id="ac8ce-130">principalID</span></span></p></td>
<td><p><span data-ttu-id="ac8ce-131">其查找包含在 tblPrincipal.prinID 表中的外键。</span><span class="sxs-lookup"><span data-stu-id="ac8ce-131">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac8ce-132">affiliationID</span><span class="sxs-lookup"><span data-stu-id="ac8ce-132">affiliationID</span></span></p></td>
<td><p><span data-ttu-id="ac8ce-133">其查找包含在 tblPrincipal.prinID 表中的外键。</span><span class="sxs-lookup"><span data-stu-id="ac8ce-133">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

