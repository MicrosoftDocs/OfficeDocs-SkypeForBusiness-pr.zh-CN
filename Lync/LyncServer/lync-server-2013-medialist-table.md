---
title: Lync Server 2013：MediaList 表
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
ms.openlocfilehash: b92c8a0a6957eed00cf4e25f60ce2e0ff24d1fd2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762990"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="medialist-table-in-lync-server-2013"></a><span data-ttu-id="519de-102">Lync Server 2013 中的 MediaList 表</span><span class="sxs-lookup"><span data-stu-id="519de-102">MediaList table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="519de-103">_**主题上次修改时间：** 2016-07-12_</span><span class="sxs-lookup"><span data-stu-id="519de-103">_**Topic Last Modified:** 2016-07-12_</span></span>

<span data-ttu-id="519de-104">MediaList 表是一个静态表，用于存储各种媒体类型的列表。</span><span class="sxs-lookup"><span data-stu-id="519de-104">The MediaList table is a static table that stores the list of various media types.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="519de-105">列</span><span class="sxs-lookup"><span data-stu-id="519de-105">Column</span></span></th>
<th><span data-ttu-id="519de-106">数据类型</span><span class="sxs-lookup"><span data-stu-id="519de-106">Data Type</span></span></th>
<th><span data-ttu-id="519de-107">键/索引</span><span class="sxs-lookup"><span data-stu-id="519de-107">Key/Index</span></span></th>
<th><span data-ttu-id="519de-108">详细信息</span><span class="sxs-lookup"><span data-stu-id="519de-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="519de-109"><strong>MediaId</strong></span><span class="sxs-lookup"><span data-stu-id="519de-109"><strong>MediaId</strong></span></span></p></td>
<td><p><span data-ttu-id="519de-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="519de-110">tinyint</span></span></p></td>
<td><p><span data-ttu-id="519de-111">Primary</span><span class="sxs-lookup"><span data-stu-id="519de-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="519de-112">值：1-7</span><span class="sxs-lookup"><span data-stu-id="519de-112">Values: 1-7</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="519de-113"><strong>媒体</strong></span><span class="sxs-lookup"><span data-stu-id="519de-113"><strong>Media</strong></span></span></p></td>
<td><p><span data-ttu-id="519de-114">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="519de-114">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="519de-115">MediaID 与媒体值的静态映射：</span><span class="sxs-lookup"><span data-stu-id="519de-115">Static mapping of MediaID and Media values:</span></span></p>
<ul>
<li><p><span data-ttu-id="519de-116">1-IM</span><span class="sxs-lookup"><span data-stu-id="519de-116">1 – IM</span></span></p></li>
<li><p><span data-ttu-id="519de-117">2 - 文件传输</span><span class="sxs-lookup"><span data-stu-id="519de-117">2 – File Transfer</span></span></p></li>
<li><p><span data-ttu-id="519de-118">3 – 远程协助</span><span class="sxs-lookup"><span data-stu-id="519de-118">3 – Remote Assistance</span></span></p></li>
<li><p><span data-ttu-id="519de-119">4 – 应用程序共享</span><span class="sxs-lookup"><span data-stu-id="519de-119">4 – Application Sharing</span></span></p></li>
<li><p><span data-ttu-id="519de-120">5-音频</span><span class="sxs-lookup"><span data-stu-id="519de-120">5 – Audio</span></span></p></li>
<li><p><span data-ttu-id="519de-121">6-视频</span><span class="sxs-lookup"><span data-stu-id="519de-121">6 – Video</span></span></p></li>
<li><p><span data-ttu-id="519de-122">7 – 应用程序邀请</span><span class="sxs-lookup"><span data-stu-id="519de-122">7 – App Invite</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="519de-123">如果你尝试确定 LcsCDR.SessionDetailsView.MediaTypes 中的值的形式类型，则需要使用以下加入代码段：</span><span class="sxs-lookup"><span data-stu-id="519de-123">If you are trying to determine the modality type for the values in LcsCDR.SessionDetailsView.MediaTypes, then you need to use the following Join snippet:</span></span>

    LEFT JOIN on Media.MediaId = MediaList.MediaId

</div>

<span> </span>

</div>

</div>

</div>

