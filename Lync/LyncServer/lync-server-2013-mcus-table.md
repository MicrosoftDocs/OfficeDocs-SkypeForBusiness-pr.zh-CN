---
title: Lync Server 2013： Mcu 表
description: Lync Server 2013： Mcu 表。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mcus table
ms:assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425742(v=OCS.15)
ms:contentKeyID: 48183674
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b0b5d0bcbebb5efc1d767776b4581b18d9f2ed18
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556478"
---
# <a name="mcus-table-in-lync-server-2013"></a><span data-ttu-id="88eb7-103">Lync Server 2013 中的 mcu 表</span><span class="sxs-lookup"><span data-stu-id="88eb7-103">Mcus table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="88eb7-104">_**上次修改的主题：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="88eb7-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="88eb7-105">Mcu 表是一个支持表格。</span><span class="sxs-lookup"><span data-stu-id="88eb7-105">The Mcus table is a supporting table.</span></span> <span data-ttu-id="88eb7-106">每个记录存储有关一个会议服务的信息。</span><span class="sxs-lookup"><span data-stu-id="88eb7-106">Each record stores information about one conferencing service.</span></span> <span data-ttu-id="88eb7-107">这些服务可以包括 IM 会议服务和电话会议服务 (，它在前端服务器上运行为进程) ，以及 Web 会议服务和 A/V 会议服务。</span><span class="sxs-lookup"><span data-stu-id="88eb7-107">These can include the IM Conferencing service and the Telephony Conferencing service (which run as processes on front-end servers), and the Web Conferencing service and A/V Conferencing service.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="88eb7-108">列</span><span class="sxs-lookup"><span data-stu-id="88eb7-108">Column</span></span></th>
<th><span data-ttu-id="88eb7-109">数据类型</span><span class="sxs-lookup"><span data-stu-id="88eb7-109">Data Type</span></span></th>
<th><span data-ttu-id="88eb7-110">键/索引</span><span class="sxs-lookup"><span data-stu-id="88eb7-110">Key/Index</span></span></th>
<th><span data-ttu-id="88eb7-111">详细信息</span><span class="sxs-lookup"><span data-stu-id="88eb7-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="88eb7-112"><strong>McuId</strong></span><span class="sxs-lookup"><span data-stu-id="88eb7-112"><strong>McuId</strong></span></span></p></td>
<td><p><span data-ttu-id="88eb7-113">int</span><span class="sxs-lookup"><span data-stu-id="88eb7-113">int</span></span></p></td>
<td><p><span data-ttu-id="88eb7-114">主</span><span class="sxs-lookup"><span data-stu-id="88eb7-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="88eb7-115">标识此会议服务器的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="88eb7-115">Unique number identifying this conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88eb7-116"><strong>McuUri</strong></span><span class="sxs-lookup"><span data-stu-id="88eb7-116"><strong>McuUri</strong></span></span></p></td>
<td><p><span data-ttu-id="88eb7-117">nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="88eb7-117">nvarchar(450)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88eb7-118"><strong>McuTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="88eb7-118"><strong>McuTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="88eb7-119">inyint</span><span class="sxs-lookup"><span data-stu-id="88eb7-119">inyint</span></span></p></td>
<td><p><span data-ttu-id="88eb7-120"> 对外</span><span class="sxs-lookup"><span data-stu-id="88eb7-120"> Foreign</span></span></p></td>
<td><p><span data-ttu-id="88eb7-121">会议服务器类型，如会议： Im 的聊天 () 或会议：音频-视频。</span><span class="sxs-lookup"><span data-stu-id="88eb7-121">Conferencing server type, such as conf:chat (for IMs) or conf:audio-video.</span></span> <span data-ttu-id="88eb7-122">有关详细信息，请参阅 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="88eb7-122">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

