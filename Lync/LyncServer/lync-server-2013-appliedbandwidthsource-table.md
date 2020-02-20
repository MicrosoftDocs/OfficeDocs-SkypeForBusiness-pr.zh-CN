---
title: Lync Server 2013： AppliedBandwidthSource 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AppliedBandwidthSource table
ms:assetid: 24fb3caf-19b3-4c0a-90d7-ca5d53de32ad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425725(v=OCS.15)
ms:contentKeyID: 48183638
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f251f507a11c2254487a99d6e6ea217e8918fe4d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147135"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="appliedbandwidthsource-table-in-lync-server-2013"></a><span data-ttu-id="63c50-102">Lync Server 2013 中的 AppliedBandwidthSource 表</span><span class="sxs-lookup"><span data-stu-id="63c50-102">AppliedBandwidthSource table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="63c50-103">_**上次修改的主题：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="63c50-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="63c50-p101">AppliedBandwidthSource 表是一个支持表。每条记录分别表示一个来源。</span><span class="sxs-lookup"><span data-stu-id="63c50-p101">The AppliedBandwidthSource table is a supporting table. Each record represents one source.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="63c50-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="63c50-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="63c50-107"><strong>数据类型</strong></span><span class="sxs-lookup"><span data-stu-id="63c50-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="63c50-108"><strong>键/索引</strong></span><span class="sxs-lookup"><span data-stu-id="63c50-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="63c50-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="63c50-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="63c50-110"><strong>AppliedBandwidthSourceKey</strong></span><span class="sxs-lookup"><span data-stu-id="63c50-110"><strong>AppliedBandwidthSourceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="63c50-111">int</span><span class="sxs-lookup"><span data-stu-id="63c50-111">int</span></span></p></td>
<td><p><span data-ttu-id="63c50-112">主</span><span class="sxs-lookup"><span data-stu-id="63c50-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="63c50-113">标识来源的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="63c50-113">Unique number identifying the source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63c50-114"><strong>AppliedBandwidthSource</strong></span><span class="sxs-lookup"><span data-stu-id="63c50-114"><strong>AppliedBandwidthSource</strong></span></span></p></td>
<td><p><span data-ttu-id="63c50-115">varchar （256）</span><span class="sxs-lookup"><span data-stu-id="63c50-115">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="63c50-116">独特</span><span class="sxs-lookup"><span data-stu-id="63c50-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="63c50-p102">这是所设定的带宽限制的来源。它描述带宽限制源自的位置（例如，“策略服务器”、“TURN 服务器”或“形式”）。</span><span class="sxs-lookup"><span data-stu-id="63c50-p102">This is the source of the bandwidth cap being imposed. It describes where the bandwidth limit is coming from (for example, “Policy Server”, “TURN Server”, or “Modality”).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

