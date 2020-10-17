---
title: Lync Server 2013： MediaList 表
description: Lync Server 2013： MediaList 表。
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
ms.openlocfilehash: 4e54535cd4a081657e7dcd59446cf65aaa3af7cd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572068"
---
# <a name="medialist-table-in-lync-server-2013"></a><span data-ttu-id="de872-103">Lync Server 2013 中的 MediaList 表</span><span class="sxs-lookup"><span data-stu-id="de872-103">MediaList table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="de872-104">_**上次修改的主题：** 2016-07-12_</span><span class="sxs-lookup"><span data-stu-id="de872-104">_**Topic Last Modified:** 2016-07-12_</span></span>

<span data-ttu-id="de872-105">MediaList 表是一个静态表，用于存储各种媒体类型的列表。</span><span class="sxs-lookup"><span data-stu-id="de872-105">The MediaList table is a static table that stores the list of various media types.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="de872-106">列</span><span class="sxs-lookup"><span data-stu-id="de872-106">Column</span></span></th>
<th><span data-ttu-id="de872-107">数据类型</span><span class="sxs-lookup"><span data-stu-id="de872-107">Data Type</span></span></th>
<th><span data-ttu-id="de872-108">键/索引</span><span class="sxs-lookup"><span data-stu-id="de872-108">Key/Index</span></span></th>
<th><span data-ttu-id="de872-109">详细信息</span><span class="sxs-lookup"><span data-stu-id="de872-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="de872-110"><strong>MediaId</strong></span><span class="sxs-lookup"><span data-stu-id="de872-110"><strong>MediaId</strong></span></span></p></td>
<td><p><span data-ttu-id="de872-111">tinyint</span><span class="sxs-lookup"><span data-stu-id="de872-111">tinyint</span></span></p></td>
<td><p><span data-ttu-id="de872-112">主</span><span class="sxs-lookup"><span data-stu-id="de872-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="de872-113">值：1-7</span><span class="sxs-lookup"><span data-stu-id="de872-113">Values: 1-7</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="de872-114"><strong>Media</strong></span><span class="sxs-lookup"><span data-stu-id="de872-114"><strong>Media</strong></span></span></p></td>
<td><p><span data-ttu-id="de872-115">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="de872-115">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="de872-116">MediaID 和媒体值的静态映射：</span><span class="sxs-lookup"><span data-stu-id="de872-116">Static mapping of MediaID and Media values:</span></span></p>
<ul>
<li><p><span data-ttu-id="de872-117">1– IM</span><span class="sxs-lookup"><span data-stu-id="de872-117">1 – IM</span></span></p></li>
<li><p><span data-ttu-id="de872-118">2 – 文件传输</span><span class="sxs-lookup"><span data-stu-id="de872-118">2 – File Transfer</span></span></p></li>
<li><p><span data-ttu-id="de872-119">3 – 远程协助</span><span class="sxs-lookup"><span data-stu-id="de872-119">3 – Remote Assistance</span></span></p></li>
<li><p><span data-ttu-id="de872-120">4 – 应用程序共享</span><span class="sxs-lookup"><span data-stu-id="de872-120">4 – Application Sharing</span></span></p></li>
<li><p><span data-ttu-id="de872-121">5–音频</span><span class="sxs-lookup"><span data-stu-id="de872-121">5 – Audio</span></span></p></li>
<li><p><span data-ttu-id="de872-122">6–视频</span><span class="sxs-lookup"><span data-stu-id="de872-122">6 – Video</span></span></p></li>
<li><p><span data-ttu-id="de872-123">7 – 应用程序邀请</span><span class="sxs-lookup"><span data-stu-id="de872-123">7 – App Invite</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="de872-124">如果您尝试为 SessionDetailsView 中的值确定 LcsCDR 类型，则需要使用以下联接代码段：</span><span class="sxs-lookup"><span data-stu-id="de872-124">If you are trying to determine the modality type for the values in LcsCDR.SessionDetailsView.MediaTypes, then you need to use the following Join snippet:</span></span>

    LEFT JOIN on Media.MediaId = MediaList.MediaId

</div>

<span> </span>

</div>

</div>

</div>

