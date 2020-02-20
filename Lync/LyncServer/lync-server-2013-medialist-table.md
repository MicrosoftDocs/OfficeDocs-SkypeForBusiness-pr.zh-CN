---
title: Lync Server 2013： MediaList 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: MediaList table
ms:assetid: 1f440590-c1bc-483e-b7bc-6cc763847768
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398279(v=OCS.15)
ms:contentKeyID: 48183579
ms.date: 07/12/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7d36b399ca6071d8c4d057d02c0814cd03629a5e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149722"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="medialist-table-in-lync-server-2013"></a><span data-ttu-id="5bf32-102">Lync Server 2013 中的 MediaList 表</span><span class="sxs-lookup"><span data-stu-id="5bf32-102">MediaList table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5bf32-103">_**上次修改的主题：** 2016-07-12_</span><span class="sxs-lookup"><span data-stu-id="5bf32-103">_**Topic Last Modified:** 2016-07-12_</span></span>

<span data-ttu-id="5bf32-104">MediaList 表是一个静态表，用于存储各种媒体类型的列表。</span><span class="sxs-lookup"><span data-stu-id="5bf32-104">The MediaList table is a static table that stores the list of various media types.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5bf32-105">列</span><span class="sxs-lookup"><span data-stu-id="5bf32-105">Column</span></span></th>
<th><span data-ttu-id="5bf32-106">数据类型</span><span class="sxs-lookup"><span data-stu-id="5bf32-106">Data Type</span></span></th>
<th><span data-ttu-id="5bf32-107">键/索引</span><span class="sxs-lookup"><span data-stu-id="5bf32-107">Key/Index</span></span></th>
<th><span data-ttu-id="5bf32-108">详细信息</span><span class="sxs-lookup"><span data-stu-id="5bf32-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5bf32-109"><strong>MediaId</strong></span><span class="sxs-lookup"><span data-stu-id="5bf32-109"><strong>MediaId</strong></span></span></p></td>
<td><p><span data-ttu-id="5bf32-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="5bf32-110">tinyint</span></span></p></td>
<td><p><span data-ttu-id="5bf32-111">主</span><span class="sxs-lookup"><span data-stu-id="5bf32-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="5bf32-112">值：1-7</span><span class="sxs-lookup"><span data-stu-id="5bf32-112">Values: 1-7</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5bf32-113"><strong>媒体</strong></span><span class="sxs-lookup"><span data-stu-id="5bf32-113"><strong>Media</strong></span></span></p></td>
<td><p><span data-ttu-id="5bf32-114">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="5bf32-114">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5bf32-115">MediaID 和媒体值的静态映射：</span><span class="sxs-lookup"><span data-stu-id="5bf32-115">Static mapping of MediaID and Media values:</span></span></p>
<ul>
<li><p><span data-ttu-id="5bf32-116">1– IM</span><span class="sxs-lookup"><span data-stu-id="5bf32-116">1 – IM</span></span></p></li>
<li><p><span data-ttu-id="5bf32-117">2 – 文件传输</span><span class="sxs-lookup"><span data-stu-id="5bf32-117">2 – File Transfer</span></span></p></li>
<li><p><span data-ttu-id="5bf32-118">3 – 远程协助</span><span class="sxs-lookup"><span data-stu-id="5bf32-118">3 – Remote Assistance</span></span></p></li>
<li><p><span data-ttu-id="5bf32-119">4 – 应用程序共享</span><span class="sxs-lookup"><span data-stu-id="5bf32-119">4 – Application Sharing</span></span></p></li>
<li><p><span data-ttu-id="5bf32-120">5–音频</span><span class="sxs-lookup"><span data-stu-id="5bf32-120">5 – Audio</span></span></p></li>
<li><p><span data-ttu-id="5bf32-121">6–视频</span><span class="sxs-lookup"><span data-stu-id="5bf32-121">6 – Video</span></span></p></li>
<li><p><span data-ttu-id="5bf32-122">7 – 应用程序邀请</span><span class="sxs-lookup"><span data-stu-id="5bf32-122">7 – App Invite</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="5bf32-123">如果您尝试为 SessionDetailsView 中的值确定 LcsCDR 类型，则需要使用以下联接代码段：</span><span class="sxs-lookup"><span data-stu-id="5bf32-123">If you are trying to determine the modality type for the values in LcsCDR.SessionDetailsView.MediaTypes, then you need to use the following Join snippet:</span></span>

    LEFT JOIN on Media.MediaId = MediaList.MediaId

</div>

<span> </span>

</div>

</div>

</div>

