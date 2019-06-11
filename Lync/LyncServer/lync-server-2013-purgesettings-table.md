---
title: 'Lync Server 2013: PurgeSettings 表'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: PurgeSettings table
ms:assetid: 9ff2c8fc-4ae8-4f22-96a8-1f4d5eecbf2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205121(v=OCS.15)
ms:contentKeyID: 48184932
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 18b9fc0aa03596677cb73641ed46e86ea133f308
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823768"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="purgesettings-table-in-lync-server-2013"></a><span data-ttu-id="9d922-102">Lync Server 2013 中的 PurgeSettings 表</span><span class="sxs-lookup"><span data-stu-id="9d922-102">PurgeSettings table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9d922-103">_**主题上次修改时间:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="9d922-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="9d922-104">PurgeSettings 表包含指定是否 (和何时) 过期的呼叫详细记录将从 CDR 数据库中自动删除的信息。</span><span class="sxs-lookup"><span data-stu-id="9d922-104">The PurgeSettings table contains information that specifies if (and when) outdated call detail records will automatically be deleted from the CDR database.</span></span> <span data-ttu-id="9d922-105">请注意, 通过运行以下命令, 还可以从 Microsoft Lync Server 2013 管理程序外壳中获取清除相关信息:</span><span class="sxs-lookup"><span data-stu-id="9d922-105">Note that purging-related information can also be obtained from within the Microsoft Lync Server 2013 Management Shell by running the following command:</span></span>

    Get-CsCdrConfiguration

<span data-ttu-id="9d922-106">管理员应将 PurgeSettings 表视为只读: 仅应使用[新的-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration)或[CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) cmdlet 进行对呼叫详细信息清除设置的更改。</span><span class="sxs-lookup"><span data-stu-id="9d922-106">Administrators should treat the PurgeSettings table as read-only: changes to the call detail purge settings should only be made using the [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) or [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) cmdlets.</span></span>

<span data-ttu-id="9d922-107">此表是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="9d922-107">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9d922-108">列</span><span class="sxs-lookup"><span data-stu-id="9d922-108">Column</span></span></th>
<th><span data-ttu-id="9d922-109">数据类型</span><span class="sxs-lookup"><span data-stu-id="9d922-109">Data Type</span></span></th>
<th><span data-ttu-id="9d922-110">键/索引</span><span class="sxs-lookup"><span data-stu-id="9d922-110">Key/Index</span></span></th>
<th><span data-ttu-id="9d922-111">详细信息</span><span class="sxs-lookup"><span data-stu-id="9d922-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9d922-112"><strong>标识号</strong></span><span class="sxs-lookup"><span data-stu-id="9d922-112"><strong>Id</strong></span></span></p></td>
<td><p><span data-ttu-id="9d922-113">int</span><span class="sxs-lookup"><span data-stu-id="9d922-113">int</span></span></p></td>
<td><p><span data-ttu-id="9d922-114">Primary</span><span class="sxs-lookup"><span data-stu-id="9d922-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="9d922-115">CDR 清除设置集合的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="9d922-115">Unique identifier for the collection of CDR purge settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d922-116"><strong>EnablePurge</strong></span><span class="sxs-lookup"><span data-stu-id="9d922-116"><strong>EnablePurge</strong></span></span></p></td>
<td><p><span data-ttu-id="9d922-117">bit</span><span class="sxs-lookup"><span data-stu-id="9d922-117">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9d922-118">当设置为 True (1) 时, Microsoft Lync Server 2013 将定期从 CDR 数据库中清除过时的记录。</span><span class="sxs-lookup"><span data-stu-id="9d922-118">When set to True (1) Microsoft Lync Server 2013 will periodically purge outdated records from the CDR database.</span></span> <span data-ttu-id="9d922-119">将在 PurgeHour 设置指定的圣多美中每天进行清除。</span><span class="sxs-lookup"><span data-stu-id="9d922-119">Purging will take place each day at the tome specified by the PurgeHour setting.</span></span> <span data-ttu-id="9d922-120">如果设置为 False (0), 将不会从数据库中自动清除记录。</span><span class="sxs-lookup"><span data-stu-id="9d922-120">If set to False (0) then records will not be automatically purged from the database.</span></span> <span data-ttu-id="9d922-121">默认值为 True。</span><span class="sxs-lookup"><span data-stu-id="9d922-121">The default value is True.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d922-122"><strong>KeepCallDetailForDays</strong></span><span class="sxs-lookup"><span data-stu-id="9d922-122"><strong>KeepCallDetailForDays</strong></span></span></p></td>
<td><p><span data-ttu-id="9d922-123">int</span><span class="sxs-lookup"><span data-stu-id="9d922-123">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9d922-124">指定将从数据库中清除的 CDR 记录的保留时间 (以天为单位): 如果启用清除, 则早于此值的 CDR 记录将从数据库中删除。</span><span class="sxs-lookup"><span data-stu-id="9d922-124">Specifies the age of CDR records (in days) that will be purged from the database: if purging is enabled, CDR records older than this value will be removed from the database.</span></span> <span data-ttu-id="9d922-125">默认值为60天。</span><span class="sxs-lookup"><span data-stu-id="9d922-125">The default value is 60 days.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d922-126"><strong>KeepErrorReportForDays</strong></span><span class="sxs-lookup"><span data-stu-id="9d922-126"><strong>KeepErrorReportForDays</strong></span></span></p></td>
<td><p><span data-ttu-id="9d922-127">int</span><span class="sxs-lookup"><span data-stu-id="9d922-127">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9d922-128">指定将从数据库中清除的错误报告记录的保留时间 (以天为单位): 如果启用清除, 则早于此值的错误报告记录将从数据库中删除。</span><span class="sxs-lookup"><span data-stu-id="9d922-128">Specifies the age of error report records (in days) that will be purged from the database: if purging is enabled, error report records older than this value will be removed from the database.</span></span> <span data-ttu-id="9d922-129">默认值为60天。</span><span class="sxs-lookup"><span data-stu-id="9d922-129">The default value is 60 days.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d922-130"><strong>PurgeHour</strong></span><span class="sxs-lookup"><span data-stu-id="9d922-130"><strong>PurgeHour</strong></span></span></p></td>
<td><p><span data-ttu-id="9d922-131">int</span><span class="sxs-lookup"><span data-stu-id="9d922-131">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9d922-132">指定每天执行数据库清除的本地时间。</span><span class="sxs-lookup"><span data-stu-id="9d922-132">Specifies the local time of day when database purging will take place.</span></span> <span data-ttu-id="9d922-133">该时间使用 24 小时制格式指定，0 表示午夜（晚上 12:00），23 表示晚上 11:00。</span><span class="sxs-lookup"><span data-stu-id="9d922-133">The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM.</span></span> <span data-ttu-id="9d922-134">请注意, 你只能指定一天中的小时数: 值 10 (表示 10:00 AM) 是允许的值, 但不允许值 10.5 10:30 (表示 10:30 AM)。</span><span class="sxs-lookup"><span data-stu-id="9d922-134">Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed.</span></span> <span data-ttu-id="9d922-135">默认值为 2 (2:00 AM)。</span><span class="sxs-lookup"><span data-stu-id="9d922-135">The default value is 2 (2:00 AM).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

