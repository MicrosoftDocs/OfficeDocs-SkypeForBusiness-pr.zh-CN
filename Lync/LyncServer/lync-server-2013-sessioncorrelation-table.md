---
title: Lync Server 2013：SessionCorrelation 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: SessionCorrelation table
ms:assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398091(v=OCS.15)
ms:contentKeyID: 48183267
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c588a58126fb83df08550a6300ca8db36cceb647
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34821948"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sessioncorrelation-table-in-lync-server-2013"></a><span data-ttu-id="fa567-102">Lync Server 2013 中的 SessionCorrelation 表</span><span class="sxs-lookup"><span data-stu-id="fa567-102">SessionCorrelation table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fa567-103">_**主题上次修改时间:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="fa567-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="fa567-104">SessionCorrelation 表是支持表。</span><span class="sxs-lookup"><span data-stu-id="fa567-104">The SessionCorrelation table is a supporting table.</span></span> <span data-ttu-id="fa567-105">每条记录表示一个 CorrelationID, 用于关联多个会话。</span><span class="sxs-lookup"><span data-stu-id="fa567-105">Each record represents one CorrelationID which is used to correlate multiple sessions.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fa567-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="fa567-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="fa567-107"><strong>数据类型</strong></span><span class="sxs-lookup"><span data-stu-id="fa567-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="fa567-108"><strong>键/索引</strong></span><span class="sxs-lookup"><span data-stu-id="fa567-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="fa567-109"><strong>详细信息</strong></span><span class="sxs-lookup"><span data-stu-id="fa567-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fa567-110"><strong>检查</strong></span><span class="sxs-lookup"><span data-stu-id="fa567-110"><strong>Checksum</strong></span></span></p></td>
<td><p><span data-ttu-id="fa567-111">int</span><span class="sxs-lookup"><span data-stu-id="fa567-111">int</span></span></p></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa567-112"><strong>CorrelationKey</strong></span><span class="sxs-lookup"><span data-stu-id="fa567-112"><strong>CorrelationKey</strong></span></span></p></td>
<td><p><span data-ttu-id="fa567-113">int</span><span class="sxs-lookup"><span data-stu-id="fa567-113">int</span></span></p></td>
<td><p><span data-ttu-id="fa567-114">Primary</span><span class="sxs-lookup"><span data-stu-id="fa567-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="fa567-115">标识此 A/V 会议服务器的唯一号码。</span><span class="sxs-lookup"><span data-stu-id="fa567-115">Unique number identifying this A/V Conferencing Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa567-116"><strong>True&correlationid</strong></span><span class="sxs-lookup"><span data-stu-id="fa567-116"><strong>CorrelationID</strong></span></span></p></td>
<td><p><span data-ttu-id="fa567-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="fa567-117">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fa567-118">唯一</span><span class="sxs-lookup"><span data-stu-id="fa567-118">Unique</span></span></p></td>
<td><p><span data-ttu-id="fa567-119">关联的会话将具有相同的相关性 ID。</span><span class="sxs-lookup"><span data-stu-id="fa567-119">Sessions that are correlated will have the same correlation ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa567-120"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="fa567-120"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="fa567-121">datetime</span><span class="sxs-lookup"><span data-stu-id="fa567-121">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fa567-122">仅供内部使用。</span><span class="sxs-lookup"><span data-stu-id="fa567-122">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

