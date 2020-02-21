---
title: Lync Server 2013： PurgeSettings 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PurgeSettings table
ms:assetid: 9ff2c8fc-4ae8-4f22-96a8-1f4d5eecbf2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205121(v=OCS.15)
ms:contentKeyID: 48184932
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7cbe8543f1d26f42186654d2988258e796d7eebb
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183395"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="purgesettings-table-in-lync-server-2013"></a><span data-ttu-id="899a7-102">Lync Server 2013 中的 PurgeSettings 表</span><span class="sxs-lookup"><span data-stu-id="899a7-102">PurgeSettings table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="899a7-103">_**上次修改的主题：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="899a7-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="899a7-104">PurgeSettings 表包括用于指定是否（以及何时）自动从 CDR 数据库中删除过时的呼叫详细信息记录的信息。</span><span class="sxs-lookup"><span data-stu-id="899a7-104">The PurgeSettings table contains information that specifies if (and when) outdated call detail records will automatically be deleted from the CDR database.</span></span> <span data-ttu-id="899a7-105">请注意，还可以通过运行以下命令，在 Microsoft Lync Server 2013 命令行管理程序中获取清除相关信息：</span><span class="sxs-lookup"><span data-stu-id="899a7-105">Note that purging-related information can also be obtained from within the Microsoft Lync Server 2013 Management Shell by running the following command:</span></span>

    Get-CsCdrConfiguration

<span data-ttu-id="899a7-106">管理员应将 PurgeSettings 表视为只读：对呼叫详细信息清除设置所做的更改只应使用[新的-set-cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration)或[set-cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) cmdlet 进行。</span><span class="sxs-lookup"><span data-stu-id="899a7-106">Administrators should treat the PurgeSettings table as read-only: changes to the call detail purge settings should only be made using the [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) or [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) cmdlets.</span></span>

<span data-ttu-id="899a7-107">此表是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="899a7-107">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="899a7-108">列</span><span class="sxs-lookup"><span data-stu-id="899a7-108">Column</span></span></th>
<th><span data-ttu-id="899a7-109">数据类型</span><span class="sxs-lookup"><span data-stu-id="899a7-109">Data Type</span></span></th>
<th><span data-ttu-id="899a7-110">键/索引</span><span class="sxs-lookup"><span data-stu-id="899a7-110">Key/Index</span></span></th>
<th><span data-ttu-id="899a7-111">详细信息</span><span class="sxs-lookup"><span data-stu-id="899a7-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="899a7-112"><strong>Id</strong></span><span class="sxs-lookup"><span data-stu-id="899a7-112"><strong>Id</strong></span></span></p></td>
<td><p><span data-ttu-id="899a7-113">int</span><span class="sxs-lookup"><span data-stu-id="899a7-113">int</span></span></p></td>
<td><p><span data-ttu-id="899a7-114">主</span><span class="sxs-lookup"><span data-stu-id="899a7-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="899a7-115">CDR 清除设置集的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="899a7-115">Unique identifier for the collection of CDR purge settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="899a7-116"><strong>EnablePurge</strong></span><span class="sxs-lookup"><span data-stu-id="899a7-116"><strong>EnablePurge</strong></span></span></p></td>
<td><p><span data-ttu-id="899a7-117">位</span><span class="sxs-lookup"><span data-stu-id="899a7-117">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="899a7-118">当设置为 True （1）时，Microsoft Lync Server 2013 将定期从 CDR 数据库中清除过期的记录。</span><span class="sxs-lookup"><span data-stu-id="899a7-118">When set to True (1) Microsoft Lync Server 2013 will periodically purge outdated records from the CDR database.</span></span> <span data-ttu-id="899a7-119">将每天在 PurgeHour 设置所指定的时间执行清除。</span><span class="sxs-lookup"><span data-stu-id="899a7-119">Purging will take place each day at the tome specified by the PurgeHour setting.</span></span> <span data-ttu-id="899a7-120">如果设置为 False (0)，则不会从数据库中自动清除记录。</span><span class="sxs-lookup"><span data-stu-id="899a7-120">If set to False (0) then records will not be automatically purged from the database.</span></span> <span data-ttu-id="899a7-121">默认值为 True。</span><span class="sxs-lookup"><span data-stu-id="899a7-121">The default value is True.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="899a7-122"><strong>KeepCallDetailForDays</strong></span><span class="sxs-lookup"><span data-stu-id="899a7-122"><strong>KeepCallDetailForDays</strong></span></span></p></td>
<td><p><span data-ttu-id="899a7-123">int</span><span class="sxs-lookup"><span data-stu-id="899a7-123">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="899a7-p103">指定将从数据库中清除的 CDR 记录的时限（以天为单位）：如果启用清除，则将从数据库中清除时限超过此值的 CDR 记录。默认值为 60 天。</span><span class="sxs-lookup"><span data-stu-id="899a7-p103">Specifies the age of CDR records (in days) that will be purged from the database: if purging is enabled, CDR records older than this value will be removed from the database. The default value is 60 days.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="899a7-126"><strong>KeepErrorReportForDays</strong></span><span class="sxs-lookup"><span data-stu-id="899a7-126"><strong>KeepErrorReportForDays</strong></span></span></p></td>
<td><p><span data-ttu-id="899a7-127">int</span><span class="sxs-lookup"><span data-stu-id="899a7-127">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="899a7-p104">指定将从数据库中清除的错误报告记录的时限（以天为单位）：如果启用清除，则将从数据库中清除时限超过此值的错误报告记录。默认值为 60 天。</span><span class="sxs-lookup"><span data-stu-id="899a7-p104">Specifies the age of error report records (in days) that will be purged from the database: if purging is enabled, error report records older than this value will be removed from the database. The default value is 60 days.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="899a7-130"><strong>PurgeHour</strong></span><span class="sxs-lookup"><span data-stu-id="899a7-130"><strong>PurgeHour</strong></span></span></p></td>
<td><p><span data-ttu-id="899a7-131">int</span><span class="sxs-lookup"><span data-stu-id="899a7-131">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="899a7-p105">指定将执行数据库清除的本地时间。时间以 24 小时制的形式指定，0 表示午夜 (12:00 AM)，23 表示 11:00 PM。请注意，您只能指定小时时间：允许值 10（指示 10:00 AM），但不允许值 10.5（指示 10:30 AM）。默认值为 2 (2:00 AM)。</span><span class="sxs-lookup"><span data-stu-id="899a7-p105">Specifies the local time of day when database purging will take place. The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM. Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed. The default value is 2 (2:00 AM).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

