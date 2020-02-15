---
title: Lync Server 2013： Users 表
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
ms.openlocfilehash: 67663afbd9e5b61b1b24478e003db91c5be511e3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046055"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="users-table-in-lync-server-2013"></a><span data-ttu-id="f7832-102">Lync Server 2013 中的 Users 表</span><span class="sxs-lookup"><span data-stu-id="f7832-102">Users table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f7832-103">_**上次修改的主题：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="f7832-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="f7832-104">"用户" 表是一个支持表格。</span><span class="sxs-lookup"><span data-stu-id="f7832-104">The Users table is a supporting table.</span></span> <span data-ttu-id="f7832-105">表中的每条记录存储有关在数据库中包含记录的呼叫或会话中涉及的一个用户的信息。</span><span class="sxs-lookup"><span data-stu-id="f7832-105">Each record in the table stores information about one user involved in calls or sessions that have records in the database.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f7832-106">列</span><span class="sxs-lookup"><span data-stu-id="f7832-106">Column</span></span></th>
<th><span data-ttu-id="f7832-107">数据类型</span><span class="sxs-lookup"><span data-stu-id="f7832-107">Data Type</span></span></th>
<th><span data-ttu-id="f7832-108">键/索引</span><span class="sxs-lookup"><span data-stu-id="f7832-108">Key/Index</span></span></th>
<th><span data-ttu-id="f7832-109">详细信息</span><span class="sxs-lookup"><span data-stu-id="f7832-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f7832-110"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="f7832-110"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="f7832-111">datetime</span><span class="sxs-lookup"><span data-stu-id="f7832-111">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f7832-112">供内部使用的时间戳。</span><span class="sxs-lookup"><span data-stu-id="f7832-112">Time stamp for internal use.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f7832-113"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="f7832-113"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="f7832-114">int</span><span class="sxs-lookup"><span data-stu-id="f7832-114">int</span></span></p></td>
<td><p><span data-ttu-id="f7832-115">主</span><span class="sxs-lookup"><span data-stu-id="f7832-115">Primary</span></span></p></td>
<td><p><span data-ttu-id="f7832-116">用于标识此用户的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="f7832-116">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f7832-117"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="f7832-117"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="f7832-118">nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="f7832-118">nvarchar(450)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f7832-119">用户 URI。</span><span class="sxs-lookup"><span data-stu-id="f7832-119">User URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f7832-120"><strong>TenantId</strong></span><span class="sxs-lookup"><span data-stu-id="f7832-120"><strong>TenantId</strong></span></span></p></td>
<td><p><span data-ttu-id="f7832-121">int</span><span class="sxs-lookup"><span data-stu-id="f7832-121">int</span></span></p></td>
<td><p><span data-ttu-id="f7832-122">对外</span><span class="sxs-lookup"><span data-stu-id="f7832-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f7832-123">此用户的租户 ID。</span><span class="sxs-lookup"><span data-stu-id="f7832-123">This user’s Tenant ID.</span></span> <span data-ttu-id="f7832-124">有关详细信息，请参阅<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的租户表</a>。</span><span class="sxs-lookup"><span data-stu-id="f7832-124">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f7832-125"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="f7832-125"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="f7832-126">int</span><span class="sxs-lookup"><span data-stu-id="f7832-126">int</span></span></p></td>
<td><p><span data-ttu-id="f7832-127">对外</span><span class="sxs-lookup"><span data-stu-id="f7832-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f7832-128">此用户的 URI 类型。</span><span class="sxs-lookup"><span data-stu-id="f7832-128">This user’s URI type.</span></span> <span data-ttu-id="f7832-129">有关详细信息，请参阅<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a>。</span><span class="sxs-lookup"><span data-stu-id="f7832-129">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

