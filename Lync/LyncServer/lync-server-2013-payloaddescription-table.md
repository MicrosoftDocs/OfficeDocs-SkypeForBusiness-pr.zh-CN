---
title: Lync Server 2013：PayloadDescription 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: PayloadDescription table
ms:assetid: c49d61c0-305a-4770-a5d2-5d9f05decc6d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412971(v=OCS.15)
ms:contentKeyID: 48185353
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2a8d18f87b9a4f5de556ec827447f0020b7a47f2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825371"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="payloaddescription-table-in-lync-server-2013"></a><span data-ttu-id="5fd0f-102">Lync Server 2013 中的 PayloadDescription 表</span><span class="sxs-lookup"><span data-stu-id="5fd0f-102">PayloadDescription table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5fd0f-103">_**主题上次修改时间:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="5fd0f-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="5fd0f-104">PayloadDescription 表是支持表。</span><span class="sxs-lookup"><span data-stu-id="5fd0f-104">The PayloadDescription table is a supporting table.</span></span> <span data-ttu-id="5fd0f-105">每条记录表示一个编解码器, 用于音频或视频会话。</span><span class="sxs-lookup"><span data-stu-id="5fd0f-105">Each record represents one Codec, which is used in an audio or video session.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5fd0f-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="5fd0f-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="5fd0f-107"><strong>数据类型</strong></span><span class="sxs-lookup"><span data-stu-id="5fd0f-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="5fd0f-108"><strong>键/索引</strong></span><span class="sxs-lookup"><span data-stu-id="5fd0f-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="5fd0f-109"><strong>详细信息</strong></span><span class="sxs-lookup"><span data-stu-id="5fd0f-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5fd0f-110"><strong>PayloadDescriptionKey</strong></span><span class="sxs-lookup"><span data-stu-id="5fd0f-110"><strong>PayloadDescriptionKey</strong></span></span></p></td>
<td><p><span data-ttu-id="5fd0f-111">int</span><span class="sxs-lookup"><span data-stu-id="5fd0f-111">int</span></span></p></td>
<td><p><span data-ttu-id="5fd0f-112">Primary</span><span class="sxs-lookup"><span data-stu-id="5fd0f-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="5fd0f-113">标识编解码器的唯一号码。</span><span class="sxs-lookup"><span data-stu-id="5fd0f-113">Unique number identifying the Codec.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fd0f-114"><strong>PayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="5fd0f-114"><strong>PayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="5fd0f-115">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="5fd0f-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5fd0f-116">唯一</span><span class="sxs-lookup"><span data-stu-id="5fd0f-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="5fd0f-117">编解码器名称。</span><span class="sxs-lookup"><span data-stu-id="5fd0f-117">Codec name.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

