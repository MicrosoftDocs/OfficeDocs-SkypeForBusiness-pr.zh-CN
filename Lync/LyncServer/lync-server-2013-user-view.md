---
title: Lync Server 2013：用户视图
description: Lync Server 2013：用户视图。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User view
ms:assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688100(v=OCS.15)
ms:contentKeyID: 49733699
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aa606887e8050a51f1e5a87656bb74a7cd58bbc3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558908"
---
# <a name="user-view-in-lync-server-2013"></a><span data-ttu-id="f456e-103">Lync Server 2013 中的用户视图</span><span class="sxs-lookup"><span data-stu-id="f456e-103">User view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f456e-104">_**上次修改的主题：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="f456e-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="f456e-105">用户视图存储有关数据库中记录的呼叫或会话所涉及的用户的信息。</span><span class="sxs-lookup"><span data-stu-id="f456e-105">The User view stores information about users who have been involved in calls or sessions that have records in the database.</span></span> <span data-ttu-id="f456e-106">此视图是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="f456e-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f456e-107">列</span><span class="sxs-lookup"><span data-stu-id="f456e-107">Column</span></span></th>
<th><span data-ttu-id="f456e-108">数据类型</span><span class="sxs-lookup"><span data-stu-id="f456e-108">Data Type</span></span></th>
<th><span data-ttu-id="f456e-109">详细信息</span><span class="sxs-lookup"><span data-stu-id="f456e-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f456e-110">UserID</span><span class="sxs-lookup"><span data-stu-id="f456e-110">UserId</span></span></p></td>
<td><p><span data-ttu-id="f456e-111">int</span><span class="sxs-lookup"><span data-stu-id="f456e-111">int</span></span></p></td>
<td><p><span data-ttu-id="f456e-112">用于标识此用户的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="f456e-112">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f456e-113">UserUri</span><span class="sxs-lookup"><span data-stu-id="f456e-113">UserUri</span></span></p></td>
<td><p><span data-ttu-id="f456e-114">nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="f456e-114">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="f456e-115">用户的 URI。</span><span class="sxs-lookup"><span data-stu-id="f456e-115">Uri of the user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f456e-116">TenantKey</span><span class="sxs-lookup"><span data-stu-id="f456e-116">TenantKey</span></span></p></td>
<td><p><span data-ttu-id="f456e-117">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="f456e-117">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="f456e-118">用户的租户。</span><span class="sxs-lookup"><span data-stu-id="f456e-118">Tenant of user.</span></span> <span data-ttu-id="f456e-119">有关详细信息，请参阅 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的租户表</a> 。</span><span class="sxs-lookup"><span data-stu-id="f456e-119">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f456e-120">UriType</span><span class="sxs-lookup"><span data-stu-id="f456e-120">UriType</span></span></p></td>
<td><p><span data-ttu-id="f456e-121">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="f456e-121">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f456e-122">用户 URI 的类型。</span><span class="sxs-lookup"><span data-stu-id="f456e-122">Type of user URI.</span></span> <span data-ttu-id="f456e-123">有关详细信息，请参阅 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="f456e-123">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

