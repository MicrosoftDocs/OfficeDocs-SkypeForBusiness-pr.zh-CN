---
title: Lync Server 2013： ConferenceJoinTimeThresholds 表
description: Lync Server 2013： ConferenceJoinTimeThresholds 表。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceJoinTimeThresholds table
ms:assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204809(v=OCS.15)
ms:contentKeyID: 48183855
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5e38c8b99f444e16309882b6a8885d166fdceb9b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561668"
---
# <a name="conferencejointimethresholds-table-in-lync-server-2013"></a><span data-ttu-id="b3834-103">Lync Server 2013 中的 ConferenceJoinTimeThresholds 表</span><span class="sxs-lookup"><span data-stu-id="b3834-103">ConferenceJoinTimeThresholds table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b3834-104">_**上次修改的主题：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="b3834-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="b3834-p101">ConferenceJoinTimeThresholds 表包含会议加入时间摘要报告使用的分类边界。会议加入时间摘要报告总结了用户成功加入会议所需的时间；这些时间值都报告为一个平均值，且采用以下类别之一：</span><span class="sxs-lookup"><span data-stu-id="b3834-p101">The ConferenceJoinTimeThresholds table contains the classification boundaries used by the Conference Join Time Summary Report. The Conference Join Time Summary Report summarizes the amount time required for users to successfully join a conference; these time values are reported both as an average and in one of the following categories:</span></span>

  - <span data-ttu-id="b3834-107">少于 2 秒。</span><span class="sxs-lookup"><span data-stu-id="b3834-107">Less than 2 seconds.</span></span>

  - <span data-ttu-id="b3834-108">2 秒到 5 秒之间。</span><span class="sxs-lookup"><span data-stu-id="b3834-108">Between 2 second and 5 seconds.</span></span>

  - <span data-ttu-id="b3834-109">5 秒到 10 秒之间。</span><span class="sxs-lookup"><span data-stu-id="b3834-109">Between 5 seconds and 10 seconds.</span></span>

  - <span data-ttu-id="b3834-110">长于 10 秒。</span><span class="sxs-lookup"><span data-stu-id="b3834-110">More than 10 seconds.</span></span>

<span data-ttu-id="b3834-111">ConferenceJoinTimeThresholds 表包含分类值 2 秒、5 秒和 10 秒。</span><span class="sxs-lookup"><span data-stu-id="b3834-111">The ConferenceJoinTimeThresholds table contains the classification values 2 seconds, 5 seconds, and 10 seconds.</span></span>

<span data-ttu-id="b3834-112">此表是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="b3834-112">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b3834-113">列</span><span class="sxs-lookup"><span data-stu-id="b3834-113">Column</span></span></th>
<th><span data-ttu-id="b3834-114">数据类型</span><span class="sxs-lookup"><span data-stu-id="b3834-114">Data Type</span></span></th>
<th><span data-ttu-id="b3834-115">键/索引</span><span class="sxs-lookup"><span data-stu-id="b3834-115">Key/Index</span></span></th>
<th><span data-ttu-id="b3834-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="b3834-116">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b3834-117"><strong>ThresholdId</strong></span><span class="sxs-lookup"><span data-stu-id="b3834-117"><strong>ThresholdId</strong></span></span></p></td>
<td><p><span data-ttu-id="b3834-118">int</span><span class="sxs-lookup"><span data-stu-id="b3834-118">int</span></span></p></td>
<td><p><span data-ttu-id="b3834-119">主</span><span class="sxs-lookup"><span data-stu-id="b3834-119">Primary</span></span></p></td>
<td><p><span data-ttu-id="b3834-120">分类的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="b3834-120">Unique identifier for the classification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3834-121"><strong>ThresholdValue</strong></span><span class="sxs-lookup"><span data-stu-id="b3834-121"><strong>ThresholdValue</strong></span></span></p></td>
<td><p><span data-ttu-id="b3834-122">int</span><span class="sxs-lookup"><span data-stu-id="b3834-122">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b3834-p102">分类的上限。允许的值包括：</span><span class="sxs-lookup"><span data-stu-id="b3834-p102">Upper limit for the classification. Allowed values are:</span></span></p>
<ol>
<li><p><span data-ttu-id="b3834-125">双面</span><span class="sxs-lookup"><span data-stu-id="b3834-125">2</span></span></p></li>
<li><p><span data-ttu-id="b3834-126">5 </span><span class="sxs-lookup"><span data-stu-id="b3834-126">5</span></span></p></li>
<li><p><span data-ttu-id="b3834-127">10  </span><span class="sxs-lookup"><span data-stu-id="b3834-127">10</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

