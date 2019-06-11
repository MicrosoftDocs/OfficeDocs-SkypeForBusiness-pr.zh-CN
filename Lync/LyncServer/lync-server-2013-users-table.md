---
title: Lync Server 2013：Users 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Users table
ms:assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412791(v=OCS.15)
ms:contentKeyID: 48185032
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6acc63c2271b5ab58e168d0f0f662c6cb3653aac
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845471"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="users-table-in-lync-server-2013"></a><span data-ttu-id="16255-102">Lync Server 2013 中的 Users 表</span><span class="sxs-lookup"><span data-stu-id="16255-102">Users table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="16255-103">_**主题上次修改时间:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="16255-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="16255-104">"用户" 表是支持表。</span><span class="sxs-lookup"><span data-stu-id="16255-104">The Users table is a supporting table.</span></span> <span data-ttu-id="16255-105">表中的每条记录存储有关在数据库中具有记录的通话或会话中涉及的一个用户的信息。</span><span class="sxs-lookup"><span data-stu-id="16255-105">Each record in the table stores information about one user involved in calls or sessions that have records in the database.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="16255-106">列</span><span class="sxs-lookup"><span data-stu-id="16255-106">Column</span></span></th>
<th><span data-ttu-id="16255-107">数据类型</span><span class="sxs-lookup"><span data-stu-id="16255-107">Data Type</span></span></th>
<th><span data-ttu-id="16255-108">键/索引</span><span class="sxs-lookup"><span data-stu-id="16255-108">Key/Index</span></span></th>
<th><span data-ttu-id="16255-109">详细信息</span><span class="sxs-lookup"><span data-stu-id="16255-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="16255-110"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="16255-110"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="16255-111">datetime</span><span class="sxs-lookup"><span data-stu-id="16255-111">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="16255-112">供内部使用的时间戳。</span><span class="sxs-lookup"><span data-stu-id="16255-112">Time stamp for internal use.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16255-113"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="16255-113"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="16255-114">int</span><span class="sxs-lookup"><span data-stu-id="16255-114">int</span></span></p></td>
<td><p><span data-ttu-id="16255-115">Primary</span><span class="sxs-lookup"><span data-stu-id="16255-115">Primary</span></span></p></td>
<td><p><span data-ttu-id="16255-116">标识此用户的唯一号码。</span><span class="sxs-lookup"><span data-stu-id="16255-116">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16255-117"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="16255-117"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="16255-118">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="16255-118">nvarchar(450)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="16255-119">用户 URI。</span><span class="sxs-lookup"><span data-stu-id="16255-119">User URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16255-120"><strong>TenantId</strong></span><span class="sxs-lookup"><span data-stu-id="16255-120"><strong>TenantId</strong></span></span></p></td>
<td><p><span data-ttu-id="16255-121">int</span><span class="sxs-lookup"><span data-stu-id="16255-121">int</span></span></p></td>
<td><p><span data-ttu-id="16255-122">外表</span><span class="sxs-lookup"><span data-stu-id="16255-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="16255-123">此用户的租户 ID。</span><span class="sxs-lookup"><span data-stu-id="16255-123">This user’s Tenant ID.</span></span> <span data-ttu-id="16255-124">有关详细信息, 请参阅<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的租户表</a>。</span><span class="sxs-lookup"><span data-stu-id="16255-124">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16255-125"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="16255-125"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="16255-126">int</span><span class="sxs-lookup"><span data-stu-id="16255-126">int</span></span></p></td>
<td><p><span data-ttu-id="16255-127">外表</span><span class="sxs-lookup"><span data-stu-id="16255-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="16255-128">此用户的 URI 类型。</span><span class="sxs-lookup"><span data-stu-id="16255-128">This user’s URI type.</span></span> <span data-ttu-id="16255-129">有关详细信息, 请参阅<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a>。</span><span class="sxs-lookup"><span data-stu-id="16255-129">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

