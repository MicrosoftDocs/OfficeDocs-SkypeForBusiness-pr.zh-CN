---
title: Lync Server 2013： tblPrincipalAffiliations
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
ms.openlocfilehash: 0a57e4a3c7a5fdcc1825c140cb6e26f8cede8dc1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214438"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblprincipalaffiliations-in-lync-server-2013"></a><span data-ttu-id="9b28f-102">Lync Server 2013 中的 tblPrincipalAffiliations</span><span class="sxs-lookup"><span data-stu-id="9b28f-102">tblPrincipalAffiliations in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9b28f-103">_**上次修改的主题：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="9b28f-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="9b28f-104">tblPrincipalAffiliations 包含描述位置中的成员身份的主体隶属关系，包括 Active directory 域服务安全组，在 Active Directory 容器中的域中。</span><span class="sxs-lookup"><span data-stu-id="9b28f-104">tblPrincipalAffiliations contains the principal affiliations that describe memberships in locations, including Active Directory Domain Services security groups, in Active Directory containers, in domains.</span></span>

### <a name="columns"></a><span data-ttu-id="9b28f-105">Columns</span><span class="sxs-lookup"><span data-stu-id="9b28f-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9b28f-106">列</span><span class="sxs-lookup"><span data-stu-id="9b28f-106">Column</span></span></th>
<th><span data-ttu-id="9b28f-107">类型</span><span class="sxs-lookup"><span data-stu-id="9b28f-107">Type</span></span></th>
<th><span data-ttu-id="9b28f-108">说明</span><span class="sxs-lookup"><span data-stu-id="9b28f-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9b28f-109">principalID</span><span class="sxs-lookup"><span data-stu-id="9b28f-109">principalID</span></span></p></td>
<td><p><span data-ttu-id="9b28f-110">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="9b28f-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="9b28f-111">附属主体的 ID。</span><span class="sxs-lookup"><span data-stu-id="9b28f-111">ID of the affiliated principal.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b28f-112">affiliationID</span><span class="sxs-lookup"><span data-stu-id="9b28f-112">affiliationID</span></span></p></td>
<td><p><span data-ttu-id="9b28f-113">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="9b28f-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="9b28f-p101">表示附属关系的主体的 ID。每个主体（系统用户类型除外）还具有自附属关系。</span><span class="sxs-lookup"><span data-stu-id="9b28f-p101">ID of the principal representing the affiliation. Each principal (except system-user-types) has a self-affiliation as well.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b28f-116">index</span><span class="sxs-lookup"><span data-stu-id="9b28f-116">index</span></span></p></td>
<td><p><span data-ttu-id="9b28f-117">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="9b28f-117">int, not null</span></span></p></td>
<td><p><span data-ttu-id="9b28f-118">索引.</span><span class="sxs-lookup"><span data-stu-id="9b28f-118">Index.</span></span> <span data-ttu-id="9b28f-119">自隶属关系的值是-1，对于其他隶属关系，它会从每个&lt;PrincipalID、affiliationId&gt;存储桶内的1依次增加。</span><span class="sxs-lookup"><span data-stu-id="9b28f-119">The value for self-affiliations is -1, and for the other affiliations it increases sequentially from 1 within each &lt;principalID, affiliationId&gt; bucket.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b28f-120">updatedBy</span><span class="sxs-lookup"><span data-stu-id="9b28f-120">updatedBy</span></span></p></td>
<td><p><span data-ttu-id="9b28f-121">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="9b28f-121">int, not null</span></span></p></td>
<td><p><span data-ttu-id="9b28f-p103">进行最新更新的主体。这通常为 1，表示 Active Directory 同步。</span><span class="sxs-lookup"><span data-stu-id="9b28f-p103">Principal that did the latest update. This is usually 1, which means Active Directory Sync.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="9b28f-124">Keys</span><span class="sxs-lookup"><span data-stu-id="9b28f-124">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9b28f-125">Columns</span><span class="sxs-lookup"><span data-stu-id="9b28f-125">Columns</span></span></th>
<th><span data-ttu-id="9b28f-126">说明</span><span class="sxs-lookup"><span data-stu-id="9b28f-126">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9b28f-127">&lt;principalID、index、affiliationID&gt;</span><span class="sxs-lookup"><span data-stu-id="9b28f-127">&lt;principalID, index, affiliationID&gt;</span></span></p></td>
<td><p><span data-ttu-id="9b28f-128">主键。</span><span class="sxs-lookup"><span data-stu-id="9b28f-128">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b28f-129">principalID</span><span class="sxs-lookup"><span data-stu-id="9b28f-129">principalID</span></span></p></td>
<td><p><span data-ttu-id="9b28f-130">其查找包含在 tblPrincipal.prinID 表中的外键。</span><span class="sxs-lookup"><span data-stu-id="9b28f-130">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b28f-131">affiliationID</span><span class="sxs-lookup"><span data-stu-id="9b28f-131">affiliationID</span></span></p></td>
<td><p><span data-ttu-id="9b28f-132">其查找包含在 tblPrincipal.prinID 表中的外键。</span><span class="sxs-lookup"><span data-stu-id="9b28f-132">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

