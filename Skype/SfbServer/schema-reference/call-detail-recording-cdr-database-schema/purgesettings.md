---
title: PurgeSettings 表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9ff2c8fc-4ae8-4f22-96a8-1f4d5eecbf2d
description: PurgeSettings 表中的信息，如果 （并且当） 指定将自动从 CDR 数据库中删除过时的呼叫详细记录。 请注意，清除相关信息也可以获得从在 Skype 的业务服务器 2015年通过运行以下命令：
ms.openlocfilehash: a28ac592fb1d5d2001e7f297f37fdc1938f25643
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="purgesettings-table"></a><span data-ttu-id="9915b-104">PurgeSettings 表</span><span class="sxs-lookup"><span data-stu-id="9915b-104">PurgeSettings table</span></span>
 
<span data-ttu-id="9915b-105">PurgeSettings 表中的信息，如果 （并且当） 指定将自动从 CDR 数据库中删除过时的呼叫详细记录。</span><span class="sxs-lookup"><span data-stu-id="9915b-105">The PurgeSettings table contains information that specifies if (and when) outdated call detail records will automatically be deleted from the CDR database.</span></span> <span data-ttu-id="9915b-106">请注意，清除相关信息也可以获得从在 Skype 的业务服务器 2015年通过运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="9915b-106">Note that purging-related information can also be obtained from within the Skype for Business Server 2015 by running the following command:</span></span>
  
```
Get-CsCdrConfiguration
```

<span data-ttu-id="9915b-107">管理员应以只读方式处理 PurgeSettings 表： 只应使用[New CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps)或[设置 CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlet 进行呼叫细节清除设置的更改。</span><span class="sxs-lookup"><span data-stu-id="9915b-107">Administrators should treat the PurgeSettings table as read-only: changes to the call detail purge settings should only be made using the [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) or [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlets.</span></span>
  
<span data-ttu-id="9915b-108">在 Microsoft Lync Server 2013 引入了此表。</span><span class="sxs-lookup"><span data-stu-id="9915b-108">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="9915b-109">**列**</span><span class="sxs-lookup"><span data-stu-id="9915b-109">**Column**</span></span>|<span data-ttu-id="9915b-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="9915b-110">**Data Type**</span></span>|<span data-ttu-id="9915b-111">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="9915b-111">**Key/Index**</span></span>|<span data-ttu-id="9915b-112">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="9915b-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9915b-113">**标识**</span><span class="sxs-lookup"><span data-stu-id="9915b-113">**Id**</span></span> <br/> |<span data-ttu-id="9915b-114">int</span><span class="sxs-lookup"><span data-stu-id="9915b-114">int</span></span>  <br/> |<span data-ttu-id="9915b-115">Primary</span><span class="sxs-lookup"><span data-stu-id="9915b-115">Primary</span></span>  <br/> |<span data-ttu-id="9915b-116">唯一标识符集合的 CDR 清除设置。</span><span class="sxs-lookup"><span data-stu-id="9915b-116">Unique identifier for the collection of CDR purge settings.</span></span>  <br/> |
|<span data-ttu-id="9915b-117">**EnablePurge**</span><span class="sxs-lookup"><span data-stu-id="9915b-117">**EnablePurge**</span></span> <br/> |<span data-ttu-id="9915b-118">bit</span><span class="sxs-lookup"><span data-stu-id="9915b-118">bit</span></span>  <br/> ||<span data-ttu-id="9915b-119">如果设置为 True (1) Skype 的业务服务器 2015年将定期清除过时的 CDR 数据库中的记录。</span><span class="sxs-lookup"><span data-stu-id="9915b-119">When set to True (1) Skype for Business Server 2015 will periodically purge outdated records from the CDR database.</span></span> <span data-ttu-id="9915b-120">清除操作会在圣多美 PurgeHour 设置所指定的每一天。</span><span class="sxs-lookup"><span data-stu-id="9915b-120">Purging will take place each day at the tome specified by the PurgeHour setting.</span></span> <span data-ttu-id="9915b-121">如果设置为 False (0) 然后记录将不会自动清除数据库中。</span><span class="sxs-lookup"><span data-stu-id="9915b-121">If set to False (0) then records will not be automatically purged from the database.</span></span> <span data-ttu-id="9915b-122">默认值为 True。</span><span class="sxs-lookup"><span data-stu-id="9915b-122">The default value is True.</span></span>  <br/> |
|<span data-ttu-id="9915b-123">**KeepCallDetailForDays**</span><span class="sxs-lookup"><span data-stu-id="9915b-123">**KeepCallDetailForDays**</span></span> <br/> |<span data-ttu-id="9915b-124">int</span><span class="sxs-lookup"><span data-stu-id="9915b-124">int</span></span>  <br/> ||<span data-ttu-id="9915b-125">指定的时间 （以天为单位） 将从数据库中清除的 CDR 记录： 如果启用了清除，将从数据库中删除早于此值的 CDR 记录。</span><span class="sxs-lookup"><span data-stu-id="9915b-125">Specifies the age of CDR records (in days) that will be purged from the database: if purging is enabled, CDR records older than this value will be removed from the database.</span></span> <span data-ttu-id="9915b-126">默认值为 60 天。</span><span class="sxs-lookup"><span data-stu-id="9915b-126">The default value is 60 days.</span></span>  <br/> |
|<span data-ttu-id="9915b-127">**KeepErrorReportForDays**</span><span class="sxs-lookup"><span data-stu-id="9915b-127">**KeepErrorReportForDays**</span></span> <br/> |<span data-ttu-id="9915b-128">int</span><span class="sxs-lookup"><span data-stu-id="9915b-128">int</span></span>  <br/> ||<span data-ttu-id="9915b-129">指定将从数据库中清除的错误报告记录 （以天为单位） 的年龄： 如果启用了清除，将从数据库中删除早于此值的错误报告记录。</span><span class="sxs-lookup"><span data-stu-id="9915b-129">Specifies the age of error report records (in days) that will be purged from the database: if purging is enabled, error report records older than this value will be removed from the database.</span></span> <span data-ttu-id="9915b-130">默认值为 60 天。</span><span class="sxs-lookup"><span data-stu-id="9915b-130">The default value is 60 days.</span></span>  <br/> |
|<span data-ttu-id="9915b-131">**PurgeHour**</span><span class="sxs-lookup"><span data-stu-id="9915b-131">**PurgeHour**</span></span> <br/> |<span data-ttu-id="9915b-132">int</span><span class="sxs-lookup"><span data-stu-id="9915b-132">int</span></span>  <br/> ||<span data-ttu-id="9915b-133">指定当数据库清除将会发生一天的当地时间。</span><span class="sxs-lookup"><span data-stu-id="9915b-133">Specifies the local time of day when database purging will take place.</span></span> <span data-ttu-id="9915b-134">该时间使用 24 小时制格式指定，0 表示午夜（晚上 12:00），23 表示晚上 11:00。</span><span class="sxs-lookup"><span data-stu-id="9915b-134">The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM.</span></span> <span data-ttu-id="9915b-135">请注意，您可以只指定一天中的小时： 允许值 （指示上午 10:00） 10，但不是允许的值为 10:30 的 10.5 （指明上午 10:30）。</span><span class="sxs-lookup"><span data-stu-id="9915b-135">Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed.</span></span> <span data-ttu-id="9915b-136">默认值为 2 (2:00 AM)。</span><span class="sxs-lookup"><span data-stu-id="9915b-136">The default value is 2 (2:00 AM).</span></span>  <br/> |
   

