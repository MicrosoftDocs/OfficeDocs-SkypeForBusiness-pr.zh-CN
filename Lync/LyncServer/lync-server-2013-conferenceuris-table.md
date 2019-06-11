---
title: Lync Server 2013：ConferenceUris 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ConferenceUris table
ms:assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412854(v=OCS.15)
ms:contentKeyID: 48185160
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e2b1ab44b564d649b6c8fb812077645c6dc13093
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837482"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferenceuris-table-in-lync-server-2013"></a><span data-ttu-id="45d69-102">Lync Server 2013 中的 ConferenceUris 表</span><span class="sxs-lookup"><span data-stu-id="45d69-102">ConferenceUris table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="45d69-103">_**主题上次修改时间:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="45d69-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="45d69-104">ConfereneUris 表是一个支持表, 用于存储参与数据库中记录的会议会话的各种会议 Uri 的列表。</span><span class="sxs-lookup"><span data-stu-id="45d69-104">The ConfereneUris table is a supporting table that stores a list of the various conference URIs that have participated in conference sessions recorded in the database.</span></span> <span data-ttu-id="45d69-105">表中的每条记录表示一个会议 URI。</span><span class="sxs-lookup"><span data-stu-id="45d69-105">Each record in the table represents one conference URI.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="45d69-106">列</span><span class="sxs-lookup"><span data-stu-id="45d69-106">Column</span></span></th>
<th><span data-ttu-id="45d69-107">数据类型</span><span class="sxs-lookup"><span data-stu-id="45d69-107">Data Type</span></span></th>
<th><span data-ttu-id="45d69-108">键/索引</span><span class="sxs-lookup"><span data-stu-id="45d69-108">Key/Index</span></span></th>
<th><span data-ttu-id="45d69-109">详细信息</span><span class="sxs-lookup"><span data-stu-id="45d69-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="45d69-110"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="45d69-110"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="45d69-111">datetime</span><span class="sxs-lookup"><span data-stu-id="45d69-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="45d69-112">Primary</span><span class="sxs-lookup"><span data-stu-id="45d69-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="45d69-113">时间戳, 内部使用。</span><span class="sxs-lookup"><span data-stu-id="45d69-113">Time stamp, Internal used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45d69-114"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="45d69-114"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="45d69-115">int</span><span class="sxs-lookup"><span data-stu-id="45d69-115">int</span></span></p></td>
<td><p><span data-ttu-id="45d69-116">Primary</span><span class="sxs-lookup"><span data-stu-id="45d69-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="45d69-117">标识此会议 URI 的唯一号码。</span><span class="sxs-lookup"><span data-stu-id="45d69-117">Unique number identifying this conference URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45d69-118"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="45d69-118"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="45d69-119">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="45d69-119">nvarchar(450)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="45d69-120">会议 URI。</span><span class="sxs-lookup"><span data-stu-id="45d69-120">Conference URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45d69-121"><strong>检查</strong></span><span class="sxs-lookup"><span data-stu-id="45d69-121"><strong>Checksum</strong></span></span></p></td>
<td><p><span data-ttu-id="45d69-122">int</span><span class="sxs-lookup"><span data-stu-id="45d69-122">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="45d69-123">ConferenceUri 的校验和。</span><span class="sxs-lookup"><span data-stu-id="45d69-123">Checksum of ConferenceUri.</span></span> <span data-ttu-id="45d69-124">用于提高数据库搜索的速度。</span><span class="sxs-lookup"><span data-stu-id="45d69-124">Used to increases the speed of database searches.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45d69-125"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="45d69-125"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="45d69-126">int</span><span class="sxs-lookup"><span data-stu-id="45d69-126">int</span></span></p></td>
<td><p><span data-ttu-id="45d69-127">外表</span><span class="sxs-lookup"><span data-stu-id="45d69-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="45d69-128">URI 类型, 例如会议: 用于即时消息会议的聊天或会议: 音频-音频/视频会议的视频。</span><span class="sxs-lookup"><span data-stu-id="45d69-128">URI type, such as conf:chat for IM conference, or conf:audio-video for audio/video conference.</span></span> <span data-ttu-id="45d69-129">有关详细信息, 请参阅<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 表中的 UriTypes 表</a>。</span><span class="sxs-lookup"><span data-stu-id="45d69-129">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> table for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

