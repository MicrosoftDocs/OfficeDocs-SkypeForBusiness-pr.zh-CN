---
title: 'Lync Server 2013: UserStatistics 表'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: UserStatistics table
ms:assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721893(v=OCS.15)
ms:contentKeyID: 49733827
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f0f684850625f61ca72bbcc9c4bc53b56fcc6b38
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845462"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="userstatistics-table-in-lync-server-2013"></a><span data-ttu-id="d1c47-102">Lync Server 2013 中的 UserStatistics 表</span><span class="sxs-lookup"><span data-stu-id="d1c47-102">UserStatistics table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d1c47-103">_**主题上次修改时间:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="d1c47-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="d1c47-104">UserStatistics 表是支持表。</span><span class="sxs-lookup"><span data-stu-id="d1c47-104">The UserStatistics table is a supporting table.</span></span> <span data-ttu-id="d1c47-105">表中的每条记录存储有关系统的单个用户使用情况的信息。</span><span class="sxs-lookup"><span data-stu-id="d1c47-105">Each record in the table stores information about an individual user’s usage of the system.</span></span> <span data-ttu-id="d1c47-106">此表是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="d1c47-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d1c47-107">列</span><span class="sxs-lookup"><span data-stu-id="d1c47-107">Column</span></span></th>
<th><span data-ttu-id="d1c47-108">数据类型</span><span class="sxs-lookup"><span data-stu-id="d1c47-108">Data Type</span></span></th>
<th><span data-ttu-id="d1c47-109">键/索引</span><span class="sxs-lookup"><span data-stu-id="d1c47-109">Key/Index</span></span></th>
<th><span data-ttu-id="d1c47-110">详细信息</span><span class="sxs-lookup"><span data-stu-id="d1c47-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d1c47-111"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="d1c47-111"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="d1c47-112">int</span><span class="sxs-lookup"><span data-stu-id="d1c47-112">int</span></span></p></td>
<td><p><span data-ttu-id="d1c47-113">Primary</span><span class="sxs-lookup"><span data-stu-id="d1c47-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="d1c47-114">标识此用户的唯一号码。</span><span class="sxs-lookup"><span data-stu-id="d1c47-114">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1c47-115"><strong>LastLogInTime</strong></span><span class="sxs-lookup"><span data-stu-id="d1c47-115"><strong>LastLogInTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d1c47-116">datetime</span><span class="sxs-lookup"><span data-stu-id="d1c47-116">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d1c47-117">上次登录用户的时间。</span><span class="sxs-lookup"><span data-stu-id="d1c47-117">Last time the user logged in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1c47-118"><strong>LastConfOrganizedTime</strong></span><span class="sxs-lookup"><span data-stu-id="d1c47-118"><strong>LastConfOrganizedTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d1c47-119">datetime</span><span class="sxs-lookup"><span data-stu-id="d1c47-119">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d1c47-120">上次用户组织会议的时间。</span><span class="sxs-lookup"><span data-stu-id="d1c47-120">Last time the user organized a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1c47-121"><strong>LastCallOrganizerCallFailureTime</strong></span><span class="sxs-lookup"><span data-stu-id="d1c47-121"><strong>LastCallOrganizerCallFailureTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d1c47-122">datetime</span><span class="sxs-lookup"><span data-stu-id="d1c47-122">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d1c47-123">上次用户遇到通话失败的时间。</span><span class="sxs-lookup"><span data-stu-id="d1c47-123">Last time the user experienced a call failure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1c47-124"><strong>LastConfOrganizerCallFailureTime</strong></span><span class="sxs-lookup"><span data-stu-id="d1c47-124"><strong>LastConfOrganizerCallFailureTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d1c47-125">datetime</span><span class="sxs-lookup"><span data-stu-id="d1c47-125">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d1c47-126">上次用户遇到作为会议组织者的呼叫失败的时间。</span><span class="sxs-lookup"><span data-stu-id="d1c47-126">Last time the user experienced a call failure as a conference organizer.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

