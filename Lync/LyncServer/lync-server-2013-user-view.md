---
title: 'Lync Server 2013: 用户视图'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: User view
ms:assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688100(v=OCS.15)
ms:contentKeyID: 49733699
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 21c22bdfbf758545418a821edaba5d8aaf447b87
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845481"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-view-in-lync-server-2013"></a><span data-ttu-id="7c1b2-102">Lync Server 2013 中的用户视图</span><span class="sxs-lookup"><span data-stu-id="7c1b2-102">User view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7c1b2-103">_**主题上次修改时间:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="7c1b2-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="7c1b2-104">"用户" 视图存储与在数据库中具有记录的通话或会话中参与的用户的相关信息。</span><span class="sxs-lookup"><span data-stu-id="7c1b2-104">The User view stores information about users who have been involved in calls or sessions that have records in the database.</span></span> <span data-ttu-id="7c1b2-105">此视图已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="7c1b2-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7c1b2-106">列</span><span class="sxs-lookup"><span data-stu-id="7c1b2-106">Column</span></span></th>
<th><span data-ttu-id="7c1b2-107">数据类型</span><span class="sxs-lookup"><span data-stu-id="7c1b2-107">Data Type</span></span></th>
<th><span data-ttu-id="7c1b2-108">详细信息</span><span class="sxs-lookup"><span data-stu-id="7c1b2-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7c1b2-109">UserId</span><span class="sxs-lookup"><span data-stu-id="7c1b2-109">UserId</span></span></p></td>
<td><p><span data-ttu-id="7c1b2-110">int</span><span class="sxs-lookup"><span data-stu-id="7c1b2-110">int</span></span></p></td>
<td><p><span data-ttu-id="7c1b2-111">标识此用户的唯一号码。</span><span class="sxs-lookup"><span data-stu-id="7c1b2-111">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c1b2-112">UserUri</span><span class="sxs-lookup"><span data-stu-id="7c1b2-112">UserUri</span></span></p></td>
<td><p><span data-ttu-id="7c1b2-113">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="7c1b2-113">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="7c1b2-114">用户的 Uri。</span><span class="sxs-lookup"><span data-stu-id="7c1b2-114">Uri of the user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c1b2-115">TenantKey</span><span class="sxs-lookup"><span data-stu-id="7c1b2-115">TenantKey</span></span></p></td>
<td><p><span data-ttu-id="7c1b2-116">标识符</span><span class="sxs-lookup"><span data-stu-id="7c1b2-116">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="7c1b2-117">用户的租户。</span><span class="sxs-lookup"><span data-stu-id="7c1b2-117">Tenant of user.</span></span> <span data-ttu-id="7c1b2-118">有关详细信息, 请参阅<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的租户表</a>。</span><span class="sxs-lookup"><span data-stu-id="7c1b2-118">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c1b2-119">UriType</span><span class="sxs-lookup"><span data-stu-id="7c1b2-119">UriType</span></span></p></td>
<td><p><span data-ttu-id="7c1b2-120">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="7c1b2-120">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7c1b2-121">用户 URI 的类型。</span><span class="sxs-lookup"><span data-stu-id="7c1b2-121">Type of user URI.</span></span> <span data-ttu-id="7c1b2-122">有关详细信息, 请参阅<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a>。</span><span class="sxs-lookup"><span data-stu-id="7c1b2-122">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

