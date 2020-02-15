---
title: Lync Server 2013： PayloadDescription 表
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
ms.openlocfilehash: 44edea16dc4874b797dd69402709a880c530147c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "41989697"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="payloaddescription-table-in-lync-server-2013"></a><span data-ttu-id="bfae4-102">Lync Server 2013 中的 PayloadDescription 表</span><span class="sxs-lookup"><span data-stu-id="bfae4-102">PayloadDescription table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bfae4-103">_**上次修改的主题：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="bfae4-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="bfae4-p101">PayloadDescription 表是一个支持表。每条记录都代表一个音频或视频会话使用的编解码器。</span><span class="sxs-lookup"><span data-stu-id="bfae4-p101">The PayloadDescription table is a supporting table. Each record represents one Codec, which is used in an audio or video session.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bfae4-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="bfae4-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="bfae4-107"><strong>数据类型</strong></span><span class="sxs-lookup"><span data-stu-id="bfae4-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="bfae4-108"><strong>键/索引</strong></span><span class="sxs-lookup"><span data-stu-id="bfae4-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="bfae4-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="bfae4-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bfae4-110"><strong>PayloadDescriptionKey</strong></span><span class="sxs-lookup"><span data-stu-id="bfae4-110"><strong>PayloadDescriptionKey</strong></span></span></p></td>
<td><p><span data-ttu-id="bfae4-111">int</span><span class="sxs-lookup"><span data-stu-id="bfae4-111">int</span></span></p></td>
<td><p><span data-ttu-id="bfae4-112">主</span><span class="sxs-lookup"><span data-stu-id="bfae4-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="bfae4-113">用于标识该编解码器的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="bfae4-113">Unique number identifying the Codec.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfae4-114"><strong>PayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="bfae4-114"><strong>PayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="bfae4-115">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="bfae4-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="bfae4-116">独特</span><span class="sxs-lookup"><span data-stu-id="bfae4-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="bfae4-117">编解码器的名称。</span><span class="sxs-lookup"><span data-stu-id="bfae4-117">Codec name.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

