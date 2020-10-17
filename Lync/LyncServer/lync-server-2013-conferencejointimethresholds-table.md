---
title: Lync Server 2013： ConferenceJoinTimeThresholds 表
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
ms.openlocfilehash: 7d8dcf3d8b5f74abe6e145d7ac25e43411ca085c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502309"
---
# <a name="conferencejointimethresholds-table-in-lync-server-2013"></a><span data-ttu-id="a6ce5-102">Lync Server 2013 中的 ConferenceJoinTimeThresholds 表</span><span class="sxs-lookup"><span data-stu-id="a6ce5-102">ConferenceJoinTimeThresholds table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a6ce5-103">_**上次修改的主题：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="a6ce5-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="a6ce5-p101">ConferenceJoinTimeThresholds 表包含会议加入时间摘要报告使用的分类边界。会议加入时间摘要报告总结了用户成功加入会议所需的时间；这些时间值都报告为一个平均值，且采用以下类别之一：</span><span class="sxs-lookup"><span data-stu-id="a6ce5-p101">The ConferenceJoinTimeThresholds table contains the classification boundaries used by the Conference Join Time Summary Report. The Conference Join Time Summary Report summarizes the amount time required for users to successfully join a conference; these time values are reported both as an average and in one of the following categories:</span></span>

  - <span data-ttu-id="a6ce5-106">少于 2 秒。</span><span class="sxs-lookup"><span data-stu-id="a6ce5-106">Less than 2 seconds.</span></span>

  - <span data-ttu-id="a6ce5-107">2 秒到 5 秒之间。</span><span class="sxs-lookup"><span data-stu-id="a6ce5-107">Between 2 second and 5 seconds.</span></span>

  - <span data-ttu-id="a6ce5-108">5 秒到 10 秒之间。</span><span class="sxs-lookup"><span data-stu-id="a6ce5-108">Between 5 seconds and 10 seconds.</span></span>

  - <span data-ttu-id="a6ce5-109">长于 10 秒。</span><span class="sxs-lookup"><span data-stu-id="a6ce5-109">More than 10 seconds.</span></span>

<span data-ttu-id="a6ce5-110">ConferenceJoinTimeThresholds 表包含分类值 2 秒、5 秒和 10 秒。</span><span class="sxs-lookup"><span data-stu-id="a6ce5-110">The ConferenceJoinTimeThresholds table contains the classification values 2 seconds, 5 seconds, and 10 seconds.</span></span>

<span data-ttu-id="a6ce5-111">此表是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="a6ce5-111">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a6ce5-112">列</span><span class="sxs-lookup"><span data-stu-id="a6ce5-112">Column</span></span></th>
<th><span data-ttu-id="a6ce5-113">数据类型</span><span class="sxs-lookup"><span data-stu-id="a6ce5-113">Data Type</span></span></th>
<th><span data-ttu-id="a6ce5-114">键/索引</span><span class="sxs-lookup"><span data-stu-id="a6ce5-114">Key/Index</span></span></th>
<th><span data-ttu-id="a6ce5-115">详细信息</span><span class="sxs-lookup"><span data-stu-id="a6ce5-115">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a6ce5-116"><strong>ThresholdId</strong></span><span class="sxs-lookup"><span data-stu-id="a6ce5-116"><strong>ThresholdId</strong></span></span></p></td>
<td><p><span data-ttu-id="a6ce5-117">int</span><span class="sxs-lookup"><span data-stu-id="a6ce5-117">int</span></span></p></td>
<td><p><span data-ttu-id="a6ce5-118">主</span><span class="sxs-lookup"><span data-stu-id="a6ce5-118">Primary</span></span></p></td>
<td><p><span data-ttu-id="a6ce5-119">分类的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="a6ce5-119">Unique identifier for the classification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a6ce5-120"><strong>ThresholdValue</strong></span><span class="sxs-lookup"><span data-stu-id="a6ce5-120"><strong>ThresholdValue</strong></span></span></p></td>
<td><p><span data-ttu-id="a6ce5-121">int</span><span class="sxs-lookup"><span data-stu-id="a6ce5-121">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a6ce5-p102">分类的上限。允许的值包括：</span><span class="sxs-lookup"><span data-stu-id="a6ce5-p102">Upper limit for the classification. Allowed values are:</span></span></p>
<ol>
<li><p><span data-ttu-id="a6ce5-124">双面</span><span class="sxs-lookup"><span data-stu-id="a6ce5-124">2</span></span></p></li>
<li><p><span data-ttu-id="a6ce5-125">5 </span><span class="sxs-lookup"><span data-stu-id="a6ce5-125">5</span></span></p></li>
<li><p><span data-ttu-id="a6ce5-126">10  </span><span class="sxs-lookup"><span data-stu-id="a6ce5-126">10</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

