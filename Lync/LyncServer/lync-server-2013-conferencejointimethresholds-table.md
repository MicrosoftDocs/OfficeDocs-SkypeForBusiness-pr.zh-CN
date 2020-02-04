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
ms.openlocfilehash: baf29af4b9d1f2b026271b84cb54436e8f4b233f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740052"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencejointimethresholds-table-in-lync-server-2013"></a><span data-ttu-id="4f771-102">Lync Server 2013 中的 ConferenceJoinTimeThresholds 表</span><span class="sxs-lookup"><span data-stu-id="4f771-102">ConferenceJoinTimeThresholds table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4f771-103">_**主题上次修改时间：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="4f771-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="4f771-104">ConferenceJoinTimeThresholds 表包含 "会议加入时间摘要" 报表使用的分类边界。</span><span class="sxs-lookup"><span data-stu-id="4f771-104">The ConferenceJoinTimeThresholds table contains the classification boundaries used by the Conference Join Time Summary Report.</span></span> <span data-ttu-id="4f771-105">"会议加入时间摘要" 报表汇总了用户成功加入会议所需的时间量;这些时间值以平均值和以下类别之一报告：</span><span class="sxs-lookup"><span data-stu-id="4f771-105">The Conference Join Time Summary Report summarizes the amount time required for users to successfully join a conference; these time values are reported both as an average and in one of the following categories:</span></span>

  - <span data-ttu-id="4f771-106">不到2秒。</span><span class="sxs-lookup"><span data-stu-id="4f771-106">Less than 2 seconds.</span></span>

  - <span data-ttu-id="4f771-107">介于2秒和5秒之间。</span><span class="sxs-lookup"><span data-stu-id="4f771-107">Between 2 second and 5 seconds.</span></span>

  - <span data-ttu-id="4f771-108">介于5秒和10秒之间。</span><span class="sxs-lookup"><span data-stu-id="4f771-108">Between 5 seconds and 10 seconds.</span></span>

  - <span data-ttu-id="4f771-109">10秒以上。</span><span class="sxs-lookup"><span data-stu-id="4f771-109">More than 10 seconds.</span></span>

<span data-ttu-id="4f771-110">ConferenceJoinTimeThresholds 表包含分类值2秒、5秒和10秒钟。</span><span class="sxs-lookup"><span data-stu-id="4f771-110">The ConferenceJoinTimeThresholds table contains the classification values 2 seconds, 5 seconds, and 10 seconds.</span></span>

<span data-ttu-id="4f771-111">此表是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="4f771-111">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4f771-112">列</span><span class="sxs-lookup"><span data-stu-id="4f771-112">Column</span></span></th>
<th><span data-ttu-id="4f771-113">数据类型</span><span class="sxs-lookup"><span data-stu-id="4f771-113">Data Type</span></span></th>
<th><span data-ttu-id="4f771-114">键/索引</span><span class="sxs-lookup"><span data-stu-id="4f771-114">Key/Index</span></span></th>
<th><span data-ttu-id="4f771-115">详细信息</span><span class="sxs-lookup"><span data-stu-id="4f771-115">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4f771-116"><strong>ThresholdId</strong></span><span class="sxs-lookup"><span data-stu-id="4f771-116"><strong>ThresholdId</strong></span></span></p></td>
<td><p><span data-ttu-id="4f771-117">int</span><span class="sxs-lookup"><span data-stu-id="4f771-117">int</span></span></p></td>
<td><p><span data-ttu-id="4f771-118">Primary</span><span class="sxs-lookup"><span data-stu-id="4f771-118">Primary</span></span></p></td>
<td><p><span data-ttu-id="4f771-119">分类的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="4f771-119">Unique identifier for the classification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f771-120"><strong>ThresholdValue</strong></span><span class="sxs-lookup"><span data-stu-id="4f771-120"><strong>ThresholdValue</strong></span></span></p></td>
<td><p><span data-ttu-id="4f771-121">int</span><span class="sxs-lookup"><span data-stu-id="4f771-121">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4f771-122">分类的上限。</span><span class="sxs-lookup"><span data-stu-id="4f771-122">Upper limit for the classification.</span></span> <span data-ttu-id="4f771-123">允许的值包括：</span><span class="sxs-lookup"><span data-stu-id="4f771-123">Allowed values are:</span></span></p>
<ol>
<li><p><span data-ttu-id="4f771-124">ppls-2</span><span class="sxs-lookup"><span data-stu-id="4f771-124">2</span></span></p></li>
<li><p><span data-ttu-id="4f771-125">5</span><span class="sxs-lookup"><span data-stu-id="4f771-125">5</span></span></p></li>
<li><p><span data-ttu-id="4f771-126">10</span><span class="sxs-lookup"><span data-stu-id="4f771-126">10</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

