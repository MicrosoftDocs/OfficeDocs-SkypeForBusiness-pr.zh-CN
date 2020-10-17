---
title: Lync Server 2013： UserStatistics 表
description: Lync Server 2013： UserStatistics 表。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UserStatistics table
ms:assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721893(v=OCS.15)
ms:contentKeyID: 49733827
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 75b34fa3c34af4cc9cf2cacc6ae7feb4d217114c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548528"
---
# <a name="userstatistics-table-in-lync-server-2013"></a><span data-ttu-id="a4603-103">Lync Server 2013 中的 UserStatistics 表</span><span class="sxs-lookup"><span data-stu-id="a4603-103">UserStatistics table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a4603-104">_**上次修改的主题：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="a4603-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="a4603-105">UserStatistics 表是一个支持表。</span><span class="sxs-lookup"><span data-stu-id="a4603-105">The UserStatistics table is a supporting table.</span></span> <span data-ttu-id="a4603-106">该表中的每条记录都存储了单个用户的系统使用情况的信息。</span><span class="sxs-lookup"><span data-stu-id="a4603-106">Each record in the table stores information about an individual user’s usage of the system.</span></span> <span data-ttu-id="a4603-107">此表是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="a4603-107">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a4603-108">列</span><span class="sxs-lookup"><span data-stu-id="a4603-108">Column</span></span></th>
<th><span data-ttu-id="a4603-109">数据类型</span><span class="sxs-lookup"><span data-stu-id="a4603-109">Data Type</span></span></th>
<th><span data-ttu-id="a4603-110">键/索引</span><span class="sxs-lookup"><span data-stu-id="a4603-110">Key/Index</span></span></th>
<th><span data-ttu-id="a4603-111">详细信息</span><span class="sxs-lookup"><span data-stu-id="a4603-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a4603-112"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="a4603-112"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="a4603-113">int</span><span class="sxs-lookup"><span data-stu-id="a4603-113">int</span></span></p></td>
<td><p><span data-ttu-id="a4603-114">主</span><span class="sxs-lookup"><span data-stu-id="a4603-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="a4603-115">用于标识此用户的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="a4603-115">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4603-116"><strong>LastLogInTime</strong></span><span class="sxs-lookup"><span data-stu-id="a4603-116"><strong>LastLogInTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a4603-117">datetime</span><span class="sxs-lookup"><span data-stu-id="a4603-117">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a4603-118">用户上次登录时间。</span><span class="sxs-lookup"><span data-stu-id="a4603-118">Last time the user logged in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4603-119"><strong>LastConfOrganizedTime</strong></span><span class="sxs-lookup"><span data-stu-id="a4603-119"><strong>LastConfOrganizedTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a4603-120">datetime</span><span class="sxs-lookup"><span data-stu-id="a4603-120">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a4603-121">用户上次组织会议的时间。</span><span class="sxs-lookup"><span data-stu-id="a4603-121">Last time the user organized a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4603-122"><strong>LastCallOrganizerCallFailureTime</strong></span><span class="sxs-lookup"><span data-stu-id="a4603-122"><strong>LastCallOrganizerCallFailureTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a4603-123">datetime</span><span class="sxs-lookup"><span data-stu-id="a4603-123">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a4603-124">用户上次遇到呼叫失败的时间。</span><span class="sxs-lookup"><span data-stu-id="a4603-124">Last time the user experienced a call failure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4603-125"><strong>LastConfOrganizerCallFailureTime</strong></span><span class="sxs-lookup"><span data-stu-id="a4603-125"><strong>LastConfOrganizerCallFailureTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a4603-126">datetime</span><span class="sxs-lookup"><span data-stu-id="a4603-126">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a4603-127">用户上次以会议组织者身份遇到呼叫失败的时间。</span><span class="sxs-lookup"><span data-stu-id="a4603-127">Last time the user experienced a call failure as a conference organizer.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

