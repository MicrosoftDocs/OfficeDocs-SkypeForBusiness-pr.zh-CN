---
title: Lync Server 2013：tblPrincipalAffiliations
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
ms.openlocfilehash: 3976b98fddc96ad08f3de4413bf8f38ec3525496
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764148"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipalaffiliations-in-lync-server-2013"></a><span data-ttu-id="32912-102">Lync Server 2013 中的 tblPrincipalAffiliations</span><span class="sxs-lookup"><span data-stu-id="32912-102">tblPrincipalAffiliations in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="32912-103">_**主题上次修改时间：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="32912-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="32912-104">tblPrincipalAffiliations 包含描述位置中的成员身份的主体成员，包括 Active directory 域服务安全组，位于 Active Directory 容器中的域中。</span><span class="sxs-lookup"><span data-stu-id="32912-104">tblPrincipalAffiliations contains the principal affiliations that describe memberships in locations, including Active Directory Domain Services security groups, in Active Directory containers, in domains.</span></span>

### <a name="columns"></a><span data-ttu-id="32912-105">多</span><span class="sxs-lookup"><span data-stu-id="32912-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="32912-106">列</span><span class="sxs-lookup"><span data-stu-id="32912-106">Column</span></span></th>
<th><span data-ttu-id="32912-107">类型</span><span class="sxs-lookup"><span data-stu-id="32912-107">Type</span></span></th>
<th><span data-ttu-id="32912-108">说明</span><span class="sxs-lookup"><span data-stu-id="32912-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="32912-109">principalID</span><span class="sxs-lookup"><span data-stu-id="32912-109">principalID</span></span></p></td>
<td><p><span data-ttu-id="32912-110">int，not null</span><span class="sxs-lookup"><span data-stu-id="32912-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="32912-111">关联主体的 ID。</span><span class="sxs-lookup"><span data-stu-id="32912-111">ID of the affiliated principal.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32912-112">affiliationID</span><span class="sxs-lookup"><span data-stu-id="32912-112">affiliationID</span></span></p></td>
<td><p><span data-ttu-id="32912-113">int，not null</span><span class="sxs-lookup"><span data-stu-id="32912-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="32912-114">表示隶属关系的承担者的 ID。</span><span class="sxs-lookup"><span data-stu-id="32912-114">ID of the principal representing the affiliation.</span></span> <span data-ttu-id="32912-115">每个主体（除系统用户类型外）还具有自我隶属关系。</span><span class="sxs-lookup"><span data-stu-id="32912-115">Each principal (except system-user-types) has a self-affiliation as well.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32912-116">食指</span><span class="sxs-lookup"><span data-stu-id="32912-116">index</span></span></p></td>
<td><p><span data-ttu-id="32912-117">int，not null</span><span class="sxs-lookup"><span data-stu-id="32912-117">int, not null</span></span></p></td>
<td><p><span data-ttu-id="32912-118">食指.</span><span class="sxs-lookup"><span data-stu-id="32912-118">Index.</span></span> <span data-ttu-id="32912-119">自隶属关系的值是-1，对于其他隶属关系，在每个&lt;PrincipalID、affiliationId&gt;存储桶中，它将按从1开始递增。</span><span class="sxs-lookup"><span data-stu-id="32912-119">The value for self-affiliations is -1, and for the other affiliations it increases sequentially from 1 within each &lt;principalID, affiliationId&gt; bucket.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32912-120">updatedBy</span><span class="sxs-lookup"><span data-stu-id="32912-120">updatedBy</span></span></p></td>
<td><p><span data-ttu-id="32912-121">int，not null</span><span class="sxs-lookup"><span data-stu-id="32912-121">int, not null</span></span></p></td>
<td><p><span data-ttu-id="32912-122">已进行最新更新的主体。</span><span class="sxs-lookup"><span data-stu-id="32912-122">Principal that did the latest update.</span></span> <span data-ttu-id="32912-123">这通常是1，这意味着 Active Directory 同步。</span><span class="sxs-lookup"><span data-stu-id="32912-123">This is usually 1, which means Active Directory Sync.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="32912-124">标示</span><span class="sxs-lookup"><span data-stu-id="32912-124">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="32912-125">多</span><span class="sxs-lookup"><span data-stu-id="32912-125">Columns</span></span></th>
<th><span data-ttu-id="32912-126">说明</span><span class="sxs-lookup"><span data-stu-id="32912-126">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="32912-127">&lt;principalID、index、affiliationID&gt;</span><span class="sxs-lookup"><span data-stu-id="32912-127">&lt;principalID, index, affiliationID&gt;</span></span></p></td>
<td><p><span data-ttu-id="32912-128">主键。</span><span class="sxs-lookup"><span data-stu-id="32912-128">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32912-129">principalID</span><span class="sxs-lookup"><span data-stu-id="32912-129">principalID</span></span></p></td>
<td><p><span data-ttu-id="32912-130">TblPrincipal 表中的 lookup 的外键。</span><span class="sxs-lookup"><span data-stu-id="32912-130">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32912-131">affiliationID</span><span class="sxs-lookup"><span data-stu-id="32912-131">affiliationID</span></span></p></td>
<td><p><span data-ttu-id="32912-132">TblPrincipal 表中的 lookup 的外键。</span><span class="sxs-lookup"><span data-stu-id="32912-132">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

