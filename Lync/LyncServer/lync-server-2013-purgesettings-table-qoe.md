---
title: Lync Server 2013： PurgeSettings 表（QoE）
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PurgeSettings table (QoE)
ms:assetid: 31b85d1c-3f32-4f67-94bf-9389cdd282c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204788(v=OCS.15)
ms:contentKeyID: 48183777
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bda217ec2711189439cfe6396faa5ba23872da9d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152246"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="purgesettings-table-qoe-in-lync-server-2013"></a><span data-ttu-id="a2112-102">Lync Server 2013 中的 PurgeSettings 表（QoE）</span><span class="sxs-lookup"><span data-stu-id="a2112-102">PurgeSettings table (QoE) in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a2112-103">_**上次修改的主题：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="a2112-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="a2112-104">PurgeSettings 表包含指定是否（以及何时）将过时的用户体验质量记录从 QoE 数据库中自动删除。</span><span class="sxs-lookup"><span data-stu-id="a2112-104">The PurgeSettings table contains information that specifies if (and when) outdated Quality of Experience records will automatically be deleted from the QoE database.</span></span> <span data-ttu-id="a2112-105">请注意，还可以通过运行以下命令，在 Microsoft Lync Server 2013 命令行管理程序中获取清除相关信息：</span><span class="sxs-lookup"><span data-stu-id="a2112-105">Note that purging-related information can also be obtained from within the Microsoft Lync Server 2013 Management Shell by running the following command:</span></span>

    Get-CsQoEConfiguration

<span data-ttu-id="a2112-106">此表是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="a2112-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a2112-107"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="a2112-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="a2112-108"><strong>数据类型</strong></span><span class="sxs-lookup"><span data-stu-id="a2112-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="a2112-109"><strong>键/索引</strong></span><span class="sxs-lookup"><span data-stu-id="a2112-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="a2112-110"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="a2112-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a2112-111"><strong>ID</strong></span><span class="sxs-lookup"><span data-stu-id="a2112-111"><strong>ID</strong></span></span></p></td>
<td><p><span data-ttu-id="a2112-112">int</span><span class="sxs-lookup"><span data-stu-id="a2112-112">int</span></span></p></td>
<td><p><span data-ttu-id="a2112-113">主</span><span class="sxs-lookup"><span data-stu-id="a2112-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="a2112-114">QoE 清除设置集合的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="a2112-114">Unique identifier for the collection of QoE purge settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2112-115"><strong>EnablePurge</strong></span><span class="sxs-lookup"><span data-stu-id="a2112-115"><strong>EnablePurge</strong></span></span></p></td>
<td><p><span data-ttu-id="a2112-116">位</span><span class="sxs-lookup"><span data-stu-id="a2112-116">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a2112-117">当设置为 True （1）时，Microsoft Lync Server 2013 将定期从 QoE 数据库中清除过期的记录。</span><span class="sxs-lookup"><span data-stu-id="a2112-117">When set to True (1) Microsoft Lync Server 2013 will periodically purge outdated records from the QoE database.</span></span> <span data-ttu-id="a2112-118">将每天在 PurgeHour 设置所指定的时间执行清除。</span><span class="sxs-lookup"><span data-stu-id="a2112-118">Purging will take place each day at the tome specified by the PurgeHour setting.</span></span> <span data-ttu-id="a2112-119">如果设置为 False (0)，则不会从数据库中自动清除记录。</span><span class="sxs-lookup"><span data-stu-id="a2112-119">If set to False (0) then records will not be automatically purged from the database.</span></span> <span data-ttu-id="a2112-120">默认值为 True。</span><span class="sxs-lookup"><span data-stu-id="a2112-120">The default value is True.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2112-121"><strong>KeepQoEDataForDays</strong></span><span class="sxs-lookup"><span data-stu-id="a2112-121"><strong>KeepQoEDataForDays</strong></span></span></p></td>
<td><p><span data-ttu-id="a2112-122">int</span><span class="sxs-lookup"><span data-stu-id="a2112-122">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a2112-p103">指定将从数据库中清除的 QoE 记录的保留时间（以天为单位）：如果启用了清除，将从数据库中移除高于此值的 QoE 记录。默认值为 60 天。</span><span class="sxs-lookup"><span data-stu-id="a2112-p103">Specifies the age of QoE records (in days) that will be purged from the database: if purging is enabled, QoE records older than this value will be removed from the database. The default value is 60 days.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2112-125"><strong>PurgeHour</strong></span><span class="sxs-lookup"><span data-stu-id="a2112-125"><strong>PurgeHour</strong></span></span></p></td>
<td><p><span data-ttu-id="a2112-126">int</span><span class="sxs-lookup"><span data-stu-id="a2112-126">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a2112-p104">指定将执行数据库清除的本地时间。将采用 24 小时制指定时间，其中 0 表示午夜 (12:00 AM)，23 表示 11:00 PM。请注意，您只能指定小时：允许值 10（指示 10:00 AM），但不允许值 10:30（即 10.5）（指示 10:30 AM）。默认值为 1 (1:00 AM)。</span><span class="sxs-lookup"><span data-stu-id="a2112-p104">Specifies the local time of day when database purging will take place. The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM. Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed. The default value is 1 (1:00 AM). Specifies the local time of day when database purging will take place. The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM. Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed. The default value is 1 (1:00 AM).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

