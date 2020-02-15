---
title: Lync Server 2013： UriTypes 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UriTypes table
ms:assetid: 77c4dfae-1b29-4e81-ba05-609e61643998
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398587(v=OCS.15)
ms:contentKeyID: 48184553
ms.date: 06/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03d4b2af9c0d746c713a2e98019f278ceb3df6e5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034002"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="uritypes-table-in-lync-server-2013"></a><span data-ttu-id="db4c6-102">Lync Server 2013 中的 UriTypes 表</span><span class="sxs-lookup"><span data-stu-id="db4c6-102">UriTypes table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="db4c6-103">_**上次修改的主题：** 2015-06-16_</span><span class="sxs-lookup"><span data-stu-id="db4c6-103">_**Topic Last Modified:** 2015-06-16_</span></span>

<span data-ttu-id="db4c6-104">UriTypes 表包含在 Microsoft Lync Server 2013 中监视的不同 URI （统一资源标识符）类型。</span><span class="sxs-lookup"><span data-stu-id="db4c6-104">The UriTypes Table contains the different URI (Uniform resource identifier) types monitored in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="db4c6-105">列</span><span class="sxs-lookup"><span data-stu-id="db4c6-105">Column</span></span></th>
<th><span data-ttu-id="db4c6-106">数据类型</span><span class="sxs-lookup"><span data-stu-id="db4c6-106">Data Type</span></span></th>
<th><span data-ttu-id="db4c6-107">键/索引</span><span class="sxs-lookup"><span data-stu-id="db4c6-107">Key/Index</span></span></th>
<th><span data-ttu-id="db4c6-108">详细信息</span><span class="sxs-lookup"><span data-stu-id="db4c6-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="db4c6-109"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="db4c6-109"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="db4c6-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="db4c6-110">tinyint</span></span></p></td>
<td><p><span data-ttu-id="db4c6-111">主</span><span class="sxs-lookup"><span data-stu-id="db4c6-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="db4c6-112">分配给 URI 类型的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="db4c6-112">Unique identifier assigned to a URI type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db4c6-113"><strong>UriType</strong></span><span class="sxs-lookup"><span data-stu-id="db4c6-113"><strong>UriType</strong></span></span></p></td>
<td><p><span data-ttu-id="db4c6-114">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="db4c6-114">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="db4c6-p101">不同的 URI 类型的描述。允许的值包括：</span><span class="sxs-lookup"><span data-stu-id="db4c6-p101">Descriptions of the different URI types. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="db4c6-117">1–电话 Uri</span><span class="sxs-lookup"><span data-stu-id="db4c6-117">1 – Phone Uri</span></span></p></li>
<li><p><span data-ttu-id="db4c6-118">0–用户 Uri</span><span class="sxs-lookup"><span data-stu-id="db4c6-118">0 – User Uri</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

