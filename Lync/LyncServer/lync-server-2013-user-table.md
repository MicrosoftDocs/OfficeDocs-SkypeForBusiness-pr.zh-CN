---
title: Lync Server 2013：用户表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User table
ms:assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398505(v=OCS.15)
ms:contentKeyID: 48184437
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d9ccf7fad4b7b84746c70384269c2a903b840b6f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140765"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="user-table-in-lync-server-2013"></a><span data-ttu-id="58ee7-102">Lync Server 2013 中的用户表</span><span class="sxs-lookup"><span data-stu-id="58ee7-102">User table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="58ee7-103">_**上次修改的主题：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="58ee7-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="58ee7-p101">User 表是一个支持表，用于存储已参与数据库中记录的会话的各种用户的列表。该表中的每条记录表示一个用户。</span><span class="sxs-lookup"><span data-stu-id="58ee7-p101">The User table is a supporting table that stores a list of the various users who have participated in sessions recorded in the database. Each record in the table represents one user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="58ee7-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="58ee7-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="58ee7-107"><strong>数据类型</strong></span><span class="sxs-lookup"><span data-stu-id="58ee7-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="58ee7-108"><strong>键/索引</strong></span><span class="sxs-lookup"><span data-stu-id="58ee7-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="58ee7-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="58ee7-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="58ee7-110"><strong>UserKey</strong></span><span class="sxs-lookup"><span data-stu-id="58ee7-110"><strong>UserKey</strong></span></span></p></td>
<td><p><span data-ttu-id="58ee7-111">int</span><span class="sxs-lookup"><span data-stu-id="58ee7-111">int</span></span></p></td>
<td><p><span data-ttu-id="58ee7-112">主</span><span class="sxs-lookup"><span data-stu-id="58ee7-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="58ee7-113">用于标识此用户的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="58ee7-113">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58ee7-114"><strong>URI</strong></span><span class="sxs-lookup"><span data-stu-id="58ee7-114"><strong>URI</strong></span></span></p></td>
<td><p><span data-ttu-id="58ee7-115">nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="58ee7-115">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="58ee7-116">独特</span><span class="sxs-lookup"><span data-stu-id="58ee7-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="58ee7-117">URI 字符串。</span><span class="sxs-lookup"><span data-stu-id="58ee7-117">URI string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58ee7-118"><strong>URIType</strong></span><span class="sxs-lookup"><span data-stu-id="58ee7-118"><strong>URIType</strong></span></span></p></td>
<td><p><span data-ttu-id="58ee7-119">int</span><span class="sxs-lookup"><span data-stu-id="58ee7-119">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="58ee7-120">1 是未知 URI 类型。</span><span class="sxs-lookup"><span data-stu-id="58ee7-120">1 is unknown URI type.</span></span></p>
<p><span data-ttu-id="58ee7-121">2 是用户 URI。</span><span class="sxs-lookup"><span data-stu-id="58ee7-121">2 is user URI.</span></span></p>
<p><span data-ttu-id="58ee7-122">4 是会议 URI。</span><span class="sxs-lookup"><span data-stu-id="58ee7-122">4 is conference URI.</span></span></p>
<p><span data-ttu-id="58ee7-123">8 是电话 URI。</span><span class="sxs-lookup"><span data-stu-id="58ee7-123">8 is phone URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58ee7-124"><strong>TenantKey</strong></span><span class="sxs-lookup"><span data-stu-id="58ee7-124"><strong>TenantKey</strong></span></span></p></td>
<td><p><span data-ttu-id="58ee7-125">int</span><span class="sxs-lookup"><span data-stu-id="58ee7-125">int</span></span></p></td>
<td><p><span data-ttu-id="58ee7-126">对外</span><span class="sxs-lookup"><span data-stu-id="58ee7-126">Foreign</span></span></p></td>
<td><p><span data-ttu-id="58ee7-127">用户的租户，被 Tenant 表引用。</span><span class="sxs-lookup"><span data-stu-id="58ee7-127">Tenant of the user, referenced from tenant table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58ee7-128"><strong>LastPoorCallTime</strong></span><span class="sxs-lookup"><span data-stu-id="58ee7-128"><strong>LastPoorCallTime</strong></span></span></p></td>
<td><p><span data-ttu-id="58ee7-129">datetime</span><span class="sxs-lookup"><span data-stu-id="58ee7-129">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="58ee7-130">用户具有较差音频呼叫时的最新时间戳。</span><span class="sxs-lookup"><span data-stu-id="58ee7-130">Latest time stamp when the user had a poor audio call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58ee7-131"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="58ee7-131"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="58ee7-132">datetime</span><span class="sxs-lookup"><span data-stu-id="58ee7-132">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="58ee7-133">仅供内部使用。</span><span class="sxs-lookup"><span data-stu-id="58ee7-133">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

