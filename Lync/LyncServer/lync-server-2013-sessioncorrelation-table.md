---
title: Lync Server 2013： SessionCorrelation 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SessionCorrelation table
ms:assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398091(v=OCS.15)
ms:contentKeyID: 48183267
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c0f3f7636354915e858016a55389a993f16ec988
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200728"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="sessioncorrelation-table-in-lync-server-2013"></a><span data-ttu-id="500f1-102">Lync Server 2013 中的 SessionCorrelation 表</span><span class="sxs-lookup"><span data-stu-id="500f1-102">SessionCorrelation table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="500f1-103">_**上次修改的主题：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="500f1-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="500f1-104">SessionCorrelation 表是一个支持表格。</span><span class="sxs-lookup"><span data-stu-id="500f1-104">The SessionCorrelation table is a supporting table.</span></span> <span data-ttu-id="500f1-105">每个记录代表一个 CorrelationID，用于关联多个会话。</span><span class="sxs-lookup"><span data-stu-id="500f1-105">Each record represents one CorrelationID which is used to correlate multiple sessions.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="500f1-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="500f1-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="500f1-107"><strong>数据类型</strong></span><span class="sxs-lookup"><span data-stu-id="500f1-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="500f1-108"><strong>键/索引</strong></span><span class="sxs-lookup"><span data-stu-id="500f1-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="500f1-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="500f1-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="500f1-110"><strong>校验和</strong></span><span class="sxs-lookup"><span data-stu-id="500f1-110"><strong>Checksum</strong></span></span></p></td>
<td><p><span data-ttu-id="500f1-111">int</span><span class="sxs-lookup"><span data-stu-id="500f1-111">int</span></span></p></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="500f1-112"><strong>CorrelationKey</strong></span><span class="sxs-lookup"><span data-stu-id="500f1-112"><strong>CorrelationKey</strong></span></span></p></td>
<td><p><span data-ttu-id="500f1-113">int</span><span class="sxs-lookup"><span data-stu-id="500f1-113">int</span></span></p></td>
<td><p><span data-ttu-id="500f1-114">主</span><span class="sxs-lookup"><span data-stu-id="500f1-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="500f1-115">标识此 A/V 会议服务器的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="500f1-115">Unique number identifying this A/V Conferencing Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="500f1-116"><strong>CorrelationID</strong></span><span class="sxs-lookup"><span data-stu-id="500f1-116"><strong>CorrelationID</strong></span></span></p></td>
<td><p><span data-ttu-id="500f1-117">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="500f1-117">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="500f1-118">独特</span><span class="sxs-lookup"><span data-stu-id="500f1-118">Unique</span></span></p></td>
<td><p><span data-ttu-id="500f1-119">与之关联的会话将具有相同的相关 ID。</span><span class="sxs-lookup"><span data-stu-id="500f1-119">Sessions that are correlated will have the same correlation ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="500f1-120"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="500f1-120"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="500f1-121">datetime</span><span class="sxs-lookup"><span data-stu-id="500f1-121">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="500f1-122">仅供内部使用。</span><span class="sxs-lookup"><span data-stu-id="500f1-122">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

