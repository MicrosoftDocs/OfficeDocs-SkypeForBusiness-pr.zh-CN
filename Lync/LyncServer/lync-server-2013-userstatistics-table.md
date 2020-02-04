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
ms.openlocfilehash: 7609747848e1943a08eff2fa77b87f0168710f81
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744252"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="userstatistics-table-in-lync-server-2013"></a><span data-ttu-id="a407c-102">Lync Server 2013 中的 UserStatistics 表</span><span class="sxs-lookup"><span data-stu-id="a407c-102">UserStatistics table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a407c-103">_**主题上次修改时间：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="a407c-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="a407c-104">UserStatistics 表是支持表。</span><span class="sxs-lookup"><span data-stu-id="a407c-104">The UserStatistics table is a supporting table.</span></span> <span data-ttu-id="a407c-105">表中的每条记录存储有关系统的单个用户使用情况的信息。</span><span class="sxs-lookup"><span data-stu-id="a407c-105">Each record in the table stores information about an individual user’s usage of the system.</span></span> <span data-ttu-id="a407c-106">此表是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="a407c-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a407c-107">列</span><span class="sxs-lookup"><span data-stu-id="a407c-107">Column</span></span></th>
<th><span data-ttu-id="a407c-108">数据类型</span><span class="sxs-lookup"><span data-stu-id="a407c-108">Data Type</span></span></th>
<th><span data-ttu-id="a407c-109">键/索引</span><span class="sxs-lookup"><span data-stu-id="a407c-109">Key/Index</span></span></th>
<th><span data-ttu-id="a407c-110">详细信息</span><span class="sxs-lookup"><span data-stu-id="a407c-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a407c-111"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="a407c-111"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="a407c-112">int</span><span class="sxs-lookup"><span data-stu-id="a407c-112">int</span></span></p></td>
<td><p><span data-ttu-id="a407c-113">Primary</span><span class="sxs-lookup"><span data-stu-id="a407c-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="a407c-114">标识此用户的唯一号码。</span><span class="sxs-lookup"><span data-stu-id="a407c-114">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a407c-115"><strong>LastLogInTime</strong></span><span class="sxs-lookup"><span data-stu-id="a407c-115"><strong>LastLogInTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a407c-116">datetime</span><span class="sxs-lookup"><span data-stu-id="a407c-116">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a407c-117">上次登录用户的时间。</span><span class="sxs-lookup"><span data-stu-id="a407c-117">Last time the user logged in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a407c-118"><strong>LastConfOrganizedTime</strong></span><span class="sxs-lookup"><span data-stu-id="a407c-118"><strong>LastConfOrganizedTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a407c-119">datetime</span><span class="sxs-lookup"><span data-stu-id="a407c-119">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a407c-120">上次用户组织会议的时间。</span><span class="sxs-lookup"><span data-stu-id="a407c-120">Last time the user organized a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a407c-121"><strong>LastCallOrganizerCallFailureTime</strong></span><span class="sxs-lookup"><span data-stu-id="a407c-121"><strong>LastCallOrganizerCallFailureTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a407c-122">datetime</span><span class="sxs-lookup"><span data-stu-id="a407c-122">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a407c-123">上次用户遇到通话失败的时间。</span><span class="sxs-lookup"><span data-stu-id="a407c-123">Last time the user experienced a call failure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a407c-124"><strong>LastConfOrganizerCallFailureTime</strong></span><span class="sxs-lookup"><span data-stu-id="a407c-124"><strong>LastConfOrganizerCallFailureTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a407c-125">datetime</span><span class="sxs-lookup"><span data-stu-id="a407c-125">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a407c-126">上次用户遇到作为会议组织者的呼叫失败的时间。</span><span class="sxs-lookup"><span data-stu-id="a407c-126">Last time the user experienced a call failure as a conference organizer.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

