---
title: Lync Server 2013：Mcus 表
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
ms.openlocfilehash: 522c7babbda63c550679dab1eb8eb03114417169
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737172"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mcus-table-in-lync-server-2013"></a><span data-ttu-id="d697b-102">Lync Server 2013 中的 Mcus 表</span><span class="sxs-lookup"><span data-stu-id="d697b-102">Mcus table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d697b-103">_**主题上次修改时间：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="d697b-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="d697b-104">Mcus 表是支持表。</span><span class="sxs-lookup"><span data-stu-id="d697b-104">The Mcus table is a supporting table.</span></span> <span data-ttu-id="d697b-105">每条记录存储有关一个会议服务的信息。</span><span class="sxs-lookup"><span data-stu-id="d697b-105">Each record stores information about one conferencing service.</span></span> <span data-ttu-id="d697b-106">这些服务可以包括 IM 会议服务和电话会议服务（该服务作为前端服务器上的进程运行）、Web 会议服务和 A/V 会议服务。</span><span class="sxs-lookup"><span data-stu-id="d697b-106">These can include the IM Conferencing service and the Telephony Conferencing service (which run as processes on front-end servers), and the Web Conferencing service and A/V Conferencing service.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d697b-107">列</span><span class="sxs-lookup"><span data-stu-id="d697b-107">Column</span></span></th>
<th><span data-ttu-id="d697b-108">数据类型</span><span class="sxs-lookup"><span data-stu-id="d697b-108">Data Type</span></span></th>
<th><span data-ttu-id="d697b-109">键/索引</span><span class="sxs-lookup"><span data-stu-id="d697b-109">Key/Index</span></span></th>
<th><span data-ttu-id="d697b-110">详细信息</span><span class="sxs-lookup"><span data-stu-id="d697b-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d697b-111"><strong>McuId</strong></span><span class="sxs-lookup"><span data-stu-id="d697b-111"><strong>McuId</strong></span></span></p></td>
<td><p><span data-ttu-id="d697b-112">int</span><span class="sxs-lookup"><span data-stu-id="d697b-112">int</span></span></p></td>
<td><p><span data-ttu-id="d697b-113">Primary</span><span class="sxs-lookup"><span data-stu-id="d697b-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="d697b-114">标识此会议服务器的唯一号码。</span><span class="sxs-lookup"><span data-stu-id="d697b-114">Unique number identifying this conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d697b-115"><strong>McuUri</strong></span><span class="sxs-lookup"><span data-stu-id="d697b-115"><strong>McuUri</strong></span></span></p></td>
<td><p><span data-ttu-id="d697b-116">nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="d697b-116">nvarchar(450)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d697b-117"><strong>McuTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="d697b-117"><strong>McuTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="d697b-118">inyint</span><span class="sxs-lookup"><span data-stu-id="d697b-118">inyint</span></span></p></td>
<td><p><span data-ttu-id="d697b-119"> 外表</span><span class="sxs-lookup"><span data-stu-id="d697b-119"> Foreign</span></span></p></td>
<td><p><span data-ttu-id="d697b-120">会议服务器类型，例如会议：聊天（适用于 Im）或会议：音频视频。</span><span class="sxs-lookup"><span data-stu-id="d697b-120">Conferencing server type, such as conf:chat (for IMs) or conf:audio-video.</span></span> <span data-ttu-id="d697b-121">有关详细信息，请参阅<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a>。</span><span class="sxs-lookup"><span data-stu-id="d697b-121">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

