---
title: 'Lync Server 2013: PurgeSettings table (QoE)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: PurgeSettings table (QoE)
ms:assetid: 31b85d1c-3f32-4f67-94bf-9389cdd282c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204788(v=OCS.15)
ms:contentKeyID: 48183777
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a3cc227d11ee723acb5a49c50d5b8d4d7e819062
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823614"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="purgesettings-table-qoe-in-lync-server-2013"></a><span data-ttu-id="6a0e7-102">Lync Server 2013 中的 PurgeSettings 表 (QoE)</span><span class="sxs-lookup"><span data-stu-id="6a0e7-102">PurgeSettings table (QoE) in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6a0e7-103">_**主题上次修改时间:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="6a0e7-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="6a0e7-104">PurgeSettings 表包含用于指定是否会自动从 QoE 数据库中删除过时的体验记录质量的信息。</span><span class="sxs-lookup"><span data-stu-id="6a0e7-104">The PurgeSettings table contains information that specifies if (and when) outdated Quality of Experience records will automatically be deleted from the QoE database.</span></span> <span data-ttu-id="6a0e7-105">请注意, 通过运行以下命令, 还可以从 Microsoft Lync Server 2013 管理程序外壳中获取清除相关信息:</span><span class="sxs-lookup"><span data-stu-id="6a0e7-105">Note that purging-related information can also be obtained from within the Microsoft Lync Server 2013 Management Shell by running the following command:</span></span>

    Get-CsQoEConfiguration

<span data-ttu-id="6a0e7-106">此表是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="6a0e7-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6a0e7-107"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="6a0e7-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="6a0e7-108"><strong>数据类型</strong></span><span class="sxs-lookup"><span data-stu-id="6a0e7-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="6a0e7-109"><strong>键/索引</strong></span><span class="sxs-lookup"><span data-stu-id="6a0e7-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="6a0e7-110"><strong>详细信息</strong></span><span class="sxs-lookup"><span data-stu-id="6a0e7-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6a0e7-111"><strong>ID</strong></span><span class="sxs-lookup"><span data-stu-id="6a0e7-111"><strong>ID</strong></span></span></p></td>
<td><p><span data-ttu-id="6a0e7-112">int</span><span class="sxs-lookup"><span data-stu-id="6a0e7-112">int</span></span></p></td>
<td><p><span data-ttu-id="6a0e7-113">Primary</span><span class="sxs-lookup"><span data-stu-id="6a0e7-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="6a0e7-114">QoE 清除设置集合的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="6a0e7-114">Unique identifier for the collection of QoE purge settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6a0e7-115"><strong>EnablePurge</strong></span><span class="sxs-lookup"><span data-stu-id="6a0e7-115"><strong>EnablePurge</strong></span></span></p></td>
<td><p><span data-ttu-id="6a0e7-116">bit</span><span class="sxs-lookup"><span data-stu-id="6a0e7-116">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6a0e7-117">当设置为 True (1) 时, Microsoft Lync Server 2013 将定期从 QoE 数据库中清除过时的记录。</span><span class="sxs-lookup"><span data-stu-id="6a0e7-117">When set to True (1) Microsoft Lync Server 2013 will periodically purge outdated records from the QoE database.</span></span> <span data-ttu-id="6a0e7-118">将在 PurgeHour 设置指定的圣多美中每天进行清除。</span><span class="sxs-lookup"><span data-stu-id="6a0e7-118">Purging will take place each day at the tome specified by the PurgeHour setting.</span></span> <span data-ttu-id="6a0e7-119">如果设置为 False (0), 将不会从数据库中自动清除记录。</span><span class="sxs-lookup"><span data-stu-id="6a0e7-119">If set to False (0) then records will not be automatically purged from the database.</span></span> <span data-ttu-id="6a0e7-120">默认值为 True。</span><span class="sxs-lookup"><span data-stu-id="6a0e7-120">The default value is True.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6a0e7-121"><strong>KeepQoEDataForDays</strong></span><span class="sxs-lookup"><span data-stu-id="6a0e7-121"><strong>KeepQoEDataForDays</strong></span></span></p></td>
<td><p><span data-ttu-id="6a0e7-122">int</span><span class="sxs-lookup"><span data-stu-id="6a0e7-122">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6a0e7-123">指定将从数据库中清除的 QoE 记录的期限 (以天为单位): 如果启用清除, 将从数据库中删除早于此值的 QoE 记录。</span><span class="sxs-lookup"><span data-stu-id="6a0e7-123">Specifies the age of QoE records (in days) that will be purged from the database: if purging is enabled, QoE records older than this value will be removed from the database.</span></span> <span data-ttu-id="6a0e7-124">默认值为60天。</span><span class="sxs-lookup"><span data-stu-id="6a0e7-124">The default value is 60 days.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6a0e7-125"><strong>PurgeHour</strong></span><span class="sxs-lookup"><span data-stu-id="6a0e7-125"><strong>PurgeHour</strong></span></span></p></td>
<td><p><span data-ttu-id="6a0e7-126">int</span><span class="sxs-lookup"><span data-stu-id="6a0e7-126">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6a0e7-127">指定每天执行数据库清除的本地时间。</span><span class="sxs-lookup"><span data-stu-id="6a0e7-127">Specifies the local time of day when database purging will take place.</span></span> <span data-ttu-id="6a0e7-128">该时间使用 24 小时制格式指定，0 表示午夜（晚上 12:00），23 表示晚上 11:00。</span><span class="sxs-lookup"><span data-stu-id="6a0e7-128">The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM.</span></span> <span data-ttu-id="6a0e7-129">请注意, 你只能指定一天中的小时数: 值 10 (表示 10:00 AM) 是允许的值, 但不允许值 10.5 10:30 (表示 10:30 AM)。</span><span class="sxs-lookup"><span data-stu-id="6a0e7-129">Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed.</span></span> <span data-ttu-id="6a0e7-130">默认值为 1 (1:00 AM)。</span><span class="sxs-lookup"><span data-stu-id="6a0e7-130">The default value is 1 (1:00 AM).</span></span> <span data-ttu-id="6a0e7-131">指定每天执行数据库清除的本地时间。</span><span class="sxs-lookup"><span data-stu-id="6a0e7-131">Specifies the local time of day when database purging will take place.</span></span> <span data-ttu-id="6a0e7-132">该时间使用 24 小时制格式指定，0 表示午夜（晚上 12:00），23 表示晚上 11:00。</span><span class="sxs-lookup"><span data-stu-id="6a0e7-132">The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM.</span></span> <span data-ttu-id="6a0e7-133">请注意, 你只能指定一天中的小时数: 值 10 (表示 10:00 AM) 是允许的值, 但不允许值 10.5 10:30 (表示 10:30 AM)。</span><span class="sxs-lookup"><span data-stu-id="6a0e7-133">Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed.</span></span> <span data-ttu-id="6a0e7-134">默认值为 1 (1:00 AM)。</span><span class="sxs-lookup"><span data-stu-id="6a0e7-134">The default value is 1 (1:00 AM).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

