---
title: Lync Server 2013：ConferenceMessageCount 表
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
ms.openlocfilehash: 426ae4abca9f91fcabaedfb5a363703523d6aa94
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740022"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencemessagecount-table-in-lync-server-2013"></a><span data-ttu-id="ef946-102">Lync Server 2013 中的 ConferenceMessageCount 表</span><span class="sxs-lookup"><span data-stu-id="ef946-102">ConferenceMessageCount table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ef946-103">_**主题上次修改时间：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="ef946-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="ef946-104">此表中的每条记录表示一个 IM 会议中的一个用户，包括该用户发送的消息数。</span><span class="sxs-lookup"><span data-stu-id="ef946-104">Each record in this table represents one user in one IM conference and includes the number of messages sent by that user.</span></span> <span data-ttu-id="ef946-105">每个会议都由该表中的多条记录表示;每个用户一条记录。</span><span class="sxs-lookup"><span data-stu-id="ef946-105">Each conference is represented by multiple records in this table; one record for each user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ef946-106">列</span><span class="sxs-lookup"><span data-stu-id="ef946-106">Column</span></span></th>
<th><span data-ttu-id="ef946-107">数据类型</span><span class="sxs-lookup"><span data-stu-id="ef946-107">Data Type</span></span></th>
<th><span data-ttu-id="ef946-108">键/索引</span><span class="sxs-lookup"><span data-stu-id="ef946-108">Key/Index</span></span></th>
<th><span data-ttu-id="ef946-109">详细信息</span><span class="sxs-lookup"><span data-stu-id="ef946-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ef946-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="ef946-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ef946-111">datetime</span><span class="sxs-lookup"><span data-stu-id="ef946-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="ef946-112">主、外部</span><span class="sxs-lookup"><span data-stu-id="ef946-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="ef946-113">会议实例的时间。</span><span class="sxs-lookup"><span data-stu-id="ef946-113">Time of conference instance.</span></span> <span data-ttu-id="ef946-114">与<strong>SessionIdSeq</strong>结合使用以唯一标识会议实例。</span><span class="sxs-lookup"><span data-stu-id="ef946-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="ef946-115">有关详细信息，请参阅<a href="lync-server-2013-conferences-table.md">Lync Server 2013 中</a>的 "会议" 表。</span><span class="sxs-lookup"><span data-stu-id="ef946-115">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef946-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="ef946-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="ef946-117">int</span><span class="sxs-lookup"><span data-stu-id="ef946-117">int</span></span></p></td>
<td><p><span data-ttu-id="ef946-118">主、外部</span><span class="sxs-lookup"><span data-stu-id="ef946-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="ef946-119">标识会议实例的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="ef946-119">ID number to identify the conference instance.</span></span> <span data-ttu-id="ef946-120">与<strong>SessionIdTime</strong>结合使用以唯一标识会议实例。</span><span class="sxs-lookup"><span data-stu-id="ef946-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="ef946-121">有关详细信息，请参阅<a href="lync-server-2013-conferences-table.md">Lync Server 2013 中</a>的 "会议" 表。</span><span class="sxs-lookup"><span data-stu-id="ef946-121">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ef946-122"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="ef946-122"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="ef946-123">int</span><span class="sxs-lookup"><span data-stu-id="ef946-123">int</span></span></p></td>
<td><p><span data-ttu-id="ef946-124">外表</span><span class="sxs-lookup"><span data-stu-id="ef946-124">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ef946-125">标识此用户的唯一号码，从<a href="lync-server-2013-users-table.md">Lync Server 2013 的 "用户" 表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="ef946-125">Unique number identifying this user, referenced from the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef946-126"><strong>MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="ef946-126"><strong>MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="ef946-127">smallint</span><span class="sxs-lookup"><span data-stu-id="ef946-127">smallint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ef946-128">此用户在此会议期间发送的消息数。</span><span class="sxs-lookup"><span data-stu-id="ef946-128">The number of messages sent by this user during this conference.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

