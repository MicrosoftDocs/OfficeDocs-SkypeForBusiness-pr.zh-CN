---
title: Lync Server 2013：User 表
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
ms.openlocfilehash: 8256dec91c93ca6e8f0fd3cfff65280a417324e4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744442"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-table-in-lync-server-2013"></a><span data-ttu-id="3f760-102">Lync Server 2013 中的 User 表</span><span class="sxs-lookup"><span data-stu-id="3f760-102">User table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3f760-103">_**主题上次修改时间：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="3f760-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="3f760-104">用户表是一个支持表，用于存储参与数据库中记录的会话的各种用户的列表。</span><span class="sxs-lookup"><span data-stu-id="3f760-104">The User table is a supporting table that stores a list of the various users who have participated in sessions recorded in the database.</span></span> <span data-ttu-id="3f760-105">表中的每条记录表示一个用户。</span><span class="sxs-lookup"><span data-stu-id="3f760-105">Each record in the table represents one user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3f760-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="3f760-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="3f760-107"><strong>数据类型</strong></span><span class="sxs-lookup"><span data-stu-id="3f760-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="3f760-108"><strong>键/索引</strong></span><span class="sxs-lookup"><span data-stu-id="3f760-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="3f760-109"><strong>详细信息</strong></span><span class="sxs-lookup"><span data-stu-id="3f760-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3f760-110"><strong>UserKey</strong></span><span class="sxs-lookup"><span data-stu-id="3f760-110"><strong>UserKey</strong></span></span></p></td>
<td><p><span data-ttu-id="3f760-111">int</span><span class="sxs-lookup"><span data-stu-id="3f760-111">int</span></span></p></td>
<td><p><span data-ttu-id="3f760-112">Primary</span><span class="sxs-lookup"><span data-stu-id="3f760-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="3f760-113">标识此用户的唯一号码。</span><span class="sxs-lookup"><span data-stu-id="3f760-113">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f760-114"><strong>URI</strong></span><span class="sxs-lookup"><span data-stu-id="3f760-114"><strong>URI</strong></span></span></p></td>
<td><p><span data-ttu-id="3f760-115">nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="3f760-115">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="3f760-116">唯一</span><span class="sxs-lookup"><span data-stu-id="3f760-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="3f760-117">URI 字符串。</span><span class="sxs-lookup"><span data-stu-id="3f760-117">URI string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f760-118"><strong>URIType</strong></span><span class="sxs-lookup"><span data-stu-id="3f760-118"><strong>URIType</strong></span></span></p></td>
<td><p><span data-ttu-id="3f760-119">int</span><span class="sxs-lookup"><span data-stu-id="3f760-119">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3f760-120">1是未知的 URI 类型。</span><span class="sxs-lookup"><span data-stu-id="3f760-120">1 is unknown URI type.</span></span></p>
<p><span data-ttu-id="3f760-121">2是用户 URI。</span><span class="sxs-lookup"><span data-stu-id="3f760-121">2 is user URI.</span></span></p>
<p><span data-ttu-id="3f760-122">4是会议 URI。</span><span class="sxs-lookup"><span data-stu-id="3f760-122">4 is conference URI.</span></span></p>
<p><span data-ttu-id="3f760-123">8是电话 URI。</span><span class="sxs-lookup"><span data-stu-id="3f760-123">8 is phone URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f760-124"><strong>TenantKey</strong></span><span class="sxs-lookup"><span data-stu-id="3f760-124"><strong>TenantKey</strong></span></span></p></td>
<td><p><span data-ttu-id="3f760-125">int</span><span class="sxs-lookup"><span data-stu-id="3f760-125">int</span></span></p></td>
<td><p><span data-ttu-id="3f760-126">外表</span><span class="sxs-lookup"><span data-stu-id="3f760-126">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3f760-127">用户的租户，从租户表引用。</span><span class="sxs-lookup"><span data-stu-id="3f760-127">Tenant of the user, referenced from tenant table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f760-128"><strong>LastPoorCallTime</strong></span><span class="sxs-lookup"><span data-stu-id="3f760-128"><strong>LastPoorCallTime</strong></span></span></p></td>
<td><p><span data-ttu-id="3f760-129">datetime</span><span class="sxs-lookup"><span data-stu-id="3f760-129">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3f760-130">当用户的音频通话较差时的最晚时间戳。</span><span class="sxs-lookup"><span data-stu-id="3f760-130">Latest time stamp when the user had a poor audio call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f760-131"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="3f760-131"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="3f760-132">datetime</span><span class="sxs-lookup"><span data-stu-id="3f760-132">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3f760-133">仅供内部使用。</span><span class="sxs-lookup"><span data-stu-id="3f760-133">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

