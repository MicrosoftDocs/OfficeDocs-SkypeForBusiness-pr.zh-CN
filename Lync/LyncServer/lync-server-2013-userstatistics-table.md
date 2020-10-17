---
title: Lync Server 2013： UserStatistics 表
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
ms.openlocfilehash: 55df55ba8c9953a1efce25269c24b43328472d7f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529989"
---
# <a name="userstatistics-table-in-lync-server-2013"></a><span data-ttu-id="10898-102">Lync Server 2013 中的 UserStatistics 表</span><span class="sxs-lookup"><span data-stu-id="10898-102">UserStatistics table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="10898-103">_**上次修改的主题：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="10898-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="10898-104">UserStatistics 表是一个支持表。</span><span class="sxs-lookup"><span data-stu-id="10898-104">The UserStatistics table is a supporting table.</span></span> <span data-ttu-id="10898-105">该表中的每条记录都存储了单个用户的系统使用情况的信息。</span><span class="sxs-lookup"><span data-stu-id="10898-105">Each record in the table stores information about an individual user’s usage of the system.</span></span> <span data-ttu-id="10898-106">此表是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="10898-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="10898-107">列</span><span class="sxs-lookup"><span data-stu-id="10898-107">Column</span></span></th>
<th><span data-ttu-id="10898-108">数据类型</span><span class="sxs-lookup"><span data-stu-id="10898-108">Data Type</span></span></th>
<th><span data-ttu-id="10898-109">键/索引</span><span class="sxs-lookup"><span data-stu-id="10898-109">Key/Index</span></span></th>
<th><span data-ttu-id="10898-110">详细信息</span><span class="sxs-lookup"><span data-stu-id="10898-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="10898-111"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="10898-111"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="10898-112">int</span><span class="sxs-lookup"><span data-stu-id="10898-112">int</span></span></p></td>
<td><p><span data-ttu-id="10898-113">主</span><span class="sxs-lookup"><span data-stu-id="10898-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="10898-114">用于标识此用户的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="10898-114">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10898-115"><strong>LastLogInTime</strong></span><span class="sxs-lookup"><span data-stu-id="10898-115"><strong>LastLogInTime</strong></span></span></p></td>
<td><p><span data-ttu-id="10898-116">datetime</span><span class="sxs-lookup"><span data-stu-id="10898-116">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="10898-117">用户上次登录时间。</span><span class="sxs-lookup"><span data-stu-id="10898-117">Last time the user logged in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10898-118"><strong>LastConfOrganizedTime</strong></span><span class="sxs-lookup"><span data-stu-id="10898-118"><strong>LastConfOrganizedTime</strong></span></span></p></td>
<td><p><span data-ttu-id="10898-119">datetime</span><span class="sxs-lookup"><span data-stu-id="10898-119">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="10898-120">用户上次组织会议的时间。</span><span class="sxs-lookup"><span data-stu-id="10898-120">Last time the user organized a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10898-121"><strong>LastCallOrganizerCallFailureTime</strong></span><span class="sxs-lookup"><span data-stu-id="10898-121"><strong>LastCallOrganizerCallFailureTime</strong></span></span></p></td>
<td><p><span data-ttu-id="10898-122">datetime</span><span class="sxs-lookup"><span data-stu-id="10898-122">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="10898-123">用户上次遇到呼叫失败的时间。</span><span class="sxs-lookup"><span data-stu-id="10898-123">Last time the user experienced a call failure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10898-124"><strong>LastConfOrganizerCallFailureTime</strong></span><span class="sxs-lookup"><span data-stu-id="10898-124"><strong>LastConfOrganizerCallFailureTime</strong></span></span></p></td>
<td><p><span data-ttu-id="10898-125">datetime</span><span class="sxs-lookup"><span data-stu-id="10898-125">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="10898-126">用户上次以会议组织者身份遇到呼叫失败的时间。</span><span class="sxs-lookup"><span data-stu-id="10898-126">Last time the user experienced a call failure as a conference organizer.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

