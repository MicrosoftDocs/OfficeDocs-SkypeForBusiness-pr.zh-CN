---
title: Lync Server 2013： Users 表
description: Lync Server 2013： Users 表。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Users table
ms:assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412791(v=OCS.15)
ms:contentKeyID: 48185032
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9b1418e162a04e46ee0dfeca082aa66b0665fc77
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548628"
---
# <a name="users-table-in-lync-server-2013"></a><span data-ttu-id="35b76-103">Lync Server 2013 中的 Users 表</span><span class="sxs-lookup"><span data-stu-id="35b76-103">Users table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="35b76-104">_**上次修改的主题：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="35b76-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="35b76-105">"用户" 表是一个支持表格。</span><span class="sxs-lookup"><span data-stu-id="35b76-105">The Users table is a supporting table.</span></span> <span data-ttu-id="35b76-106">表中的每条记录存储有关在数据库中包含记录的呼叫或会话中涉及的一个用户的信息。</span><span class="sxs-lookup"><span data-stu-id="35b76-106">Each record in the table stores information about one user involved in calls or sessions that have records in the database.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="35b76-107">列</span><span class="sxs-lookup"><span data-stu-id="35b76-107">Column</span></span></th>
<th><span data-ttu-id="35b76-108">数据类型</span><span class="sxs-lookup"><span data-stu-id="35b76-108">Data Type</span></span></th>
<th><span data-ttu-id="35b76-109">键/索引</span><span class="sxs-lookup"><span data-stu-id="35b76-109">Key/Index</span></span></th>
<th><span data-ttu-id="35b76-110">详细信息</span><span class="sxs-lookup"><span data-stu-id="35b76-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="35b76-111"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="35b76-111"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="35b76-112">datetime</span><span class="sxs-lookup"><span data-stu-id="35b76-112">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="35b76-113">供内部使用的时间戳。</span><span class="sxs-lookup"><span data-stu-id="35b76-113">Time stamp for internal use.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="35b76-114"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="35b76-114"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="35b76-115">int</span><span class="sxs-lookup"><span data-stu-id="35b76-115">int</span></span></p></td>
<td><p><span data-ttu-id="35b76-116">主</span><span class="sxs-lookup"><span data-stu-id="35b76-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="35b76-117">用于标识此用户的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="35b76-117">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="35b76-118"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="35b76-118"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="35b76-119">nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="35b76-119">nvarchar(450)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="35b76-120">用户 URI。</span><span class="sxs-lookup"><span data-stu-id="35b76-120">User URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="35b76-121"><strong>TenantId</strong></span><span class="sxs-lookup"><span data-stu-id="35b76-121"><strong>TenantId</strong></span></span></p></td>
<td><p><span data-ttu-id="35b76-122">int</span><span class="sxs-lookup"><span data-stu-id="35b76-122">int</span></span></p></td>
<td><p><span data-ttu-id="35b76-123">对外</span><span class="sxs-lookup"><span data-stu-id="35b76-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="35b76-124">此用户的租户 ID。</span><span class="sxs-lookup"><span data-stu-id="35b76-124">This user’s Tenant ID.</span></span> <span data-ttu-id="35b76-125">有关详细信息，请参阅 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的租户表</a> 。</span><span class="sxs-lookup"><span data-stu-id="35b76-125">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="35b76-126"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="35b76-126"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="35b76-127">int</span><span class="sxs-lookup"><span data-stu-id="35b76-127">int</span></span></p></td>
<td><p><span data-ttu-id="35b76-128">对外</span><span class="sxs-lookup"><span data-stu-id="35b76-128">Foreign</span></span></p></td>
<td><p><span data-ttu-id="35b76-129">此用户的 URI 类型。</span><span class="sxs-lookup"><span data-stu-id="35b76-129">This user’s URI type.</span></span> <span data-ttu-id="35b76-130">有关详细信息，请参阅 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="35b76-130">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

