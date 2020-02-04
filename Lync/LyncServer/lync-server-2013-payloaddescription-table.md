---
title: Lync Server 2013：PayloadDescription 表
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
ms.openlocfilehash: 2fe905db80edae74e81cc496c9ad70ca3148854f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755386"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="payloaddescription-table-in-lync-server-2013"></a><span data-ttu-id="5f7c8-102">Lync Server 2013 中的 PayloadDescription 表</span><span class="sxs-lookup"><span data-stu-id="5f7c8-102">PayloadDescription table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5f7c8-103">_**主题上次修改时间：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="5f7c8-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="5f7c8-104">PayloadDescription 表是支持表。</span><span class="sxs-lookup"><span data-stu-id="5f7c8-104">The PayloadDescription table is a supporting table.</span></span> <span data-ttu-id="5f7c8-105">每条记录表示一个编解码器，用于音频或视频会话。</span><span class="sxs-lookup"><span data-stu-id="5f7c8-105">Each record represents one Codec, which is used in an audio or video session.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5f7c8-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="5f7c8-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="5f7c8-107"><strong>数据类型</strong></span><span class="sxs-lookup"><span data-stu-id="5f7c8-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="5f7c8-108"><strong>键/索引</strong></span><span class="sxs-lookup"><span data-stu-id="5f7c8-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="5f7c8-109"><strong>详细信息</strong></span><span class="sxs-lookup"><span data-stu-id="5f7c8-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5f7c8-110"><strong>PayloadDescriptionKey</strong></span><span class="sxs-lookup"><span data-stu-id="5f7c8-110"><strong>PayloadDescriptionKey</strong></span></span></p></td>
<td><p><span data-ttu-id="5f7c8-111">int</span><span class="sxs-lookup"><span data-stu-id="5f7c8-111">int</span></span></p></td>
<td><p><span data-ttu-id="5f7c8-112">Primary</span><span class="sxs-lookup"><span data-stu-id="5f7c8-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="5f7c8-113">标识编解码器的唯一号码。</span><span class="sxs-lookup"><span data-stu-id="5f7c8-113">Unique number identifying the Codec.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f7c8-114"><strong>PayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="5f7c8-114"><strong>PayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="5f7c8-115">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="5f7c8-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5f7c8-116">唯一</span><span class="sxs-lookup"><span data-stu-id="5f7c8-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="5f7c8-117">编解码器名称。</span><span class="sxs-lookup"><span data-stu-id="5f7c8-117">Codec name.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

