---
title: Lync Server 2013： ConferenceMessageCount 表
description: Lync Server 2013： ConferenceMessageCount 表。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceMessageCount table
ms:assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398590(v=OCS.15)
ms:contentKeyID: 48184570
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 271b654c09ab1aef194eb613e660de208aea1534
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561618"
---
# <a name="conferencemessagecount-table-in-lync-server-2013"></a><span data-ttu-id="7da48-103">Lync Server 2013 中的 ConferenceMessageCount 表</span><span class="sxs-lookup"><span data-stu-id="7da48-103">ConferenceMessageCount table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7da48-104">_**上次修改的主题：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="7da48-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="7da48-105">此表中的每条记录代表一个 IM 会议中的一个用户，并包含该用户发送的邮件数。</span><span class="sxs-lookup"><span data-stu-id="7da48-105">Each record in this table represents one user in one IM conference and includes the number of messages sent by that user.</span></span> <span data-ttu-id="7da48-106">每个会议在此表中由多个记录表示;每个用户一个记录。</span><span class="sxs-lookup"><span data-stu-id="7da48-106">Each conference is represented by multiple records in this table; one record for each user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7da48-107">列</span><span class="sxs-lookup"><span data-stu-id="7da48-107">Column</span></span></th>
<th><span data-ttu-id="7da48-108">数据类型</span><span class="sxs-lookup"><span data-stu-id="7da48-108">Data Type</span></span></th>
<th><span data-ttu-id="7da48-109">键/索引</span><span class="sxs-lookup"><span data-stu-id="7da48-109">Key/Index</span></span></th>
<th><span data-ttu-id="7da48-110">详细信息</span><span class="sxs-lookup"><span data-stu-id="7da48-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7da48-111"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="7da48-111"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="7da48-112">datetime</span><span class="sxs-lookup"><span data-stu-id="7da48-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="7da48-113">主、外</span><span class="sxs-lookup"><span data-stu-id="7da48-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="7da48-114">会议实例的时间。</span><span class="sxs-lookup"><span data-stu-id="7da48-114">Time of conference instance.</span></span> <span data-ttu-id="7da48-115">与 <strong>SessionIdSeq</strong> 结合使用，以唯一标识会议实例。</span><span class="sxs-lookup"><span data-stu-id="7da48-115">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="7da48-116">有关详细信息，请参阅 <a href="lync-server-2013-conferences-table.md">Lync Server 2013 中</a> 的 "会议" 表。</span><span class="sxs-lookup"><span data-stu-id="7da48-116">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7da48-117"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="7da48-117"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="7da48-118">int</span><span class="sxs-lookup"><span data-stu-id="7da48-118">int</span></span></p></td>
<td><p><span data-ttu-id="7da48-119">主、外</span><span class="sxs-lookup"><span data-stu-id="7da48-119">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="7da48-120">用于标识会议实例的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="7da48-120">ID number to identify the conference instance.</span></span> <span data-ttu-id="7da48-121">与 <strong>SessionIdTime</strong> 结合使用，以唯一标识会议实例。</span><span class="sxs-lookup"><span data-stu-id="7da48-121">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="7da48-122">有关详细信息，请参阅 <a href="lync-server-2013-conferences-table.md">Lync Server 2013 中</a> 的 "会议" 表。</span><span class="sxs-lookup"><span data-stu-id="7da48-122">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7da48-123"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="7da48-123"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="7da48-124">int</span><span class="sxs-lookup"><span data-stu-id="7da48-124">int</span></span></p></td>
<td><p><span data-ttu-id="7da48-125">对外</span><span class="sxs-lookup"><span data-stu-id="7da48-125">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7da48-126">标识此用户的唯一编号， <a href="lync-server-2013-users-table.md">在 Lync Server 2013 中的 "用户" 表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="7da48-126">Unique number identifying this user, referenced from the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7da48-127"><strong>MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="7da48-127"><strong>MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="7da48-128">smallint</span><span class="sxs-lookup"><span data-stu-id="7da48-128">smallint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7da48-129">此用户在此会议期间发送的邮件数。</span><span class="sxs-lookup"><span data-stu-id="7da48-129">The number of messages sent by this user during this conference.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

