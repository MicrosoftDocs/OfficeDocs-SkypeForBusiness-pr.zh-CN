---
title: Lync Server 2013： PayloadDescription 表
description: Lync Server 2013： PayloadDescription 表。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PayloadDescription table
ms:assetid: c49d61c0-305a-4770-a5d2-5d9f05decc6d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412971(v=OCS.15)
ms:contentKeyID: 48185353
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 90ba6b3b85060601487b5b6d0d8747c5fbfa2a9a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557358"
---
# <a name="payloaddescription-table-in-lync-server-2013"></a><span data-ttu-id="77b18-103">Lync Server 2013 中的 PayloadDescription 表</span><span class="sxs-lookup"><span data-stu-id="77b18-103">PayloadDescription table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="77b18-104">_**上次修改的主题：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="77b18-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="77b18-p101">PayloadDescription 表是一个支持表。每条记录都代表一个音频或视频会话使用的编解码器。</span><span class="sxs-lookup"><span data-stu-id="77b18-p101">The PayloadDescription table is a supporting table. Each record represents one Codec, which is used in an audio or video session.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="77b18-107"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="77b18-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="77b18-108"><strong>数据类型</strong></span><span class="sxs-lookup"><span data-stu-id="77b18-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="77b18-109"><strong>键/索引</strong></span><span class="sxs-lookup"><span data-stu-id="77b18-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="77b18-110"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="77b18-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="77b18-111"><strong>PayloadDescriptionKey</strong></span><span class="sxs-lookup"><span data-stu-id="77b18-111"><strong>PayloadDescriptionKey</strong></span></span></p></td>
<td><p><span data-ttu-id="77b18-112">int</span><span class="sxs-lookup"><span data-stu-id="77b18-112">int</span></span></p></td>
<td><p><span data-ttu-id="77b18-113">主</span><span class="sxs-lookup"><span data-stu-id="77b18-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="77b18-114">用于标识该编解码器的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="77b18-114">Unique number identifying the Codec.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77b18-115"><strong>PayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="77b18-115"><strong>PayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="77b18-116">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="77b18-116">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="77b18-117">独特</span><span class="sxs-lookup"><span data-stu-id="77b18-117">Unique</span></span></p></td>
<td><p><span data-ttu-id="77b18-118">编解码器的名称。</span><span class="sxs-lookup"><span data-stu-id="77b18-118">Codec name.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

