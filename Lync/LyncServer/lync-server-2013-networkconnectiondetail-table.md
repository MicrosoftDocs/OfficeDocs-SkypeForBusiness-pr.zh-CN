---
title: 'Lync Server 2013: NetworkConnectionDetail 表'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: NetworkConnectionDetail table
ms:assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205185(v=OCS.15)
ms:contentKeyID: 48185170
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 281e2d87088a56fdf46c045171772df00b1d9cf6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826421"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="networkconnectiondetail-table-in-lync-server-2013"></a><span data-ttu-id="6c48f-102">Lync Server 2013 中的 NetworkConnectionDetail 表</span><span class="sxs-lookup"><span data-stu-id="6c48f-102">NetworkConnectionDetail table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6c48f-103">_**主题上次修改时间:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="6c48f-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="6c48f-104">NetworkConnectionDetail 表将网络连接类型映射到 "体验质量" 数据库中其他位置使用的网络连接标识符。</span><span class="sxs-lookup"><span data-stu-id="6c48f-104">The NetworkConnectionDetail table maps network connection types to the network connection identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="6c48f-105">此表是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="6c48f-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6c48f-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="6c48f-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="6c48f-107"><strong>数据类型</strong></span><span class="sxs-lookup"><span data-stu-id="6c48f-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="6c48f-108"><strong>键/索引</strong></span><span class="sxs-lookup"><span data-stu-id="6c48f-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="6c48f-109"><strong>详细信息</strong></span><span class="sxs-lookup"><span data-stu-id="6c48f-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6c48f-110"><strong>NetworkConnectionDetailKey</strong></span><span class="sxs-lookup"><span data-stu-id="6c48f-110"><strong>NetworkConnectionDetailKey</strong></span></span></p></td>
<td><p><span data-ttu-id="6c48f-111">tinyint</span><span class="sxs-lookup"><span data-stu-id="6c48f-111">tinyint</span></span></p></td>
<td><p><span data-ttu-id="6c48f-112">Primary</span><span class="sxs-lookup"><span data-stu-id="6c48f-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="6c48f-113">网络连接类型的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="6c48f-113">Unique identifier for the network connection type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c48f-114"><strong>NetworkConnectionDetail</strong></span><span class="sxs-lookup"><span data-stu-id="6c48f-114"><strong>NetworkConnectionDetail</strong></span></span></p></td>
<td><p><span data-ttu-id="6c48f-115">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="6c48f-115">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="6c48f-116">唯一</span><span class="sxs-lookup"><span data-stu-id="6c48f-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="6c48f-117">与 NetworkConnectionDetailKey 对应的网络连接类型。</span><span class="sxs-lookup"><span data-stu-id="6c48f-117">Network connection type that corresponds to the NetworkConnectionDetailKey.</span></span> <span data-ttu-id="6c48f-118">允许的值包括：</span><span class="sxs-lookup"><span data-stu-id="6c48f-118">Allowed values are:</span></span></p>
<ol>
<li><p><span data-ttu-id="6c48f-119">0--有线</span><span class="sxs-lookup"><span data-stu-id="6c48f-119">0 -- Wired</span></span></p></li>
<li><p><span data-ttu-id="6c48f-120">1--WiFi</span><span class="sxs-lookup"><span data-stu-id="6c48f-120">1 -- WiFi</span></span></p></li>
<li><p><span data-ttu-id="6c48f-121">2--以太网</span><span class="sxs-lookup"><span data-stu-id="6c48f-121">2 -- Ethernet</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

