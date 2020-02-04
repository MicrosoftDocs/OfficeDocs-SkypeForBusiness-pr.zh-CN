---
title: Lync Server 2013：ConferenceUris 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceUris table
ms:assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412854(v=OCS.15)
ms:contentKeyID: 48185160
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3cacbaf4e8c7c826ae2e00e9c86b44cc8387f315
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741572"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferenceuris-table-in-lync-server-2013"></a><span data-ttu-id="04b41-102">Lync Server 2013 中的 ConferenceUris 表</span><span class="sxs-lookup"><span data-stu-id="04b41-102">ConferenceUris table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="04b41-103">_**主题上次修改时间：** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="04b41-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="04b41-104">ConfereneUris 表是一个支持表，用于存储参与数据库中记录的会议会话的各种会议 Uri 的列表。</span><span class="sxs-lookup"><span data-stu-id="04b41-104">The ConfereneUris table is a supporting table that stores a list of the various conference URIs that have participated in conference sessions recorded in the database.</span></span> <span data-ttu-id="04b41-105">表中的每条记录表示一个会议 URI。</span><span class="sxs-lookup"><span data-stu-id="04b41-105">Each record in the table represents one conference URI.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="04b41-106">列</span><span class="sxs-lookup"><span data-stu-id="04b41-106">Column</span></span></th>
<th><span data-ttu-id="04b41-107">数据类型</span><span class="sxs-lookup"><span data-stu-id="04b41-107">Data Type</span></span></th>
<th><span data-ttu-id="04b41-108">键/索引</span><span class="sxs-lookup"><span data-stu-id="04b41-108">Key/Index</span></span></th>
<th><span data-ttu-id="04b41-109">详细信息</span><span class="sxs-lookup"><span data-stu-id="04b41-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="04b41-110"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="04b41-110"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="04b41-111">datetime</span><span class="sxs-lookup"><span data-stu-id="04b41-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="04b41-112">Primary</span><span class="sxs-lookup"><span data-stu-id="04b41-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="04b41-113">时间戳，内部使用。</span><span class="sxs-lookup"><span data-stu-id="04b41-113">Time stamp, Internal used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04b41-114"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="04b41-114"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="04b41-115">int</span><span class="sxs-lookup"><span data-stu-id="04b41-115">int</span></span></p></td>
<td><p><span data-ttu-id="04b41-116">Primary</span><span class="sxs-lookup"><span data-stu-id="04b41-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="04b41-117">标识此会议 URI 的唯一号码。</span><span class="sxs-lookup"><span data-stu-id="04b41-117">Unique number identifying this conference URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="04b41-118"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="04b41-118"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="04b41-119">nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="04b41-119">nvarchar(450)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="04b41-120">会议 URI。</span><span class="sxs-lookup"><span data-stu-id="04b41-120">Conference URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04b41-121"><strong>检查</strong></span><span class="sxs-lookup"><span data-stu-id="04b41-121"><strong>Checksum</strong></span></span></p></td>
<td><p><span data-ttu-id="04b41-122">int</span><span class="sxs-lookup"><span data-stu-id="04b41-122">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="04b41-123">ConferenceUri 的校验和。</span><span class="sxs-lookup"><span data-stu-id="04b41-123">Checksum of ConferenceUri.</span></span> <span data-ttu-id="04b41-124">用于提高数据库搜索的速度。</span><span class="sxs-lookup"><span data-stu-id="04b41-124">Used to increases the speed of database searches.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="04b41-125"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="04b41-125"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="04b41-126">int</span><span class="sxs-lookup"><span data-stu-id="04b41-126">int</span></span></p></td>
<td><p><span data-ttu-id="04b41-127">外表</span><span class="sxs-lookup"><span data-stu-id="04b41-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="04b41-128">URI 类型，例如会议：用于即时消息会议的聊天或会议：音频-音频/视频会议的视频。</span><span class="sxs-lookup"><span data-stu-id="04b41-128">URI type, such as conf:chat for IM conference, or conf:audio-video for audio/video conference.</span></span> <span data-ttu-id="04b41-129">有关详细信息，请参阅<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 表中的 UriTypes 表</a>。</span><span class="sxs-lookup"><span data-stu-id="04b41-129">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> table for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

