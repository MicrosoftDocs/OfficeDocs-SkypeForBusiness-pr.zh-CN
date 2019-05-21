---
title: PurgeSettings 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9ff2c8fc-4ae8-4f22-96a8-1f4d5eecbf2d
description: 'PurgeSettings 表包含指定是否 (和何时) 过期的呼叫详细记录将从 CDR 数据库中自动删除的信息。 请注意, 通过运行以下命令, 还可以从 Skype for Business Server 2015 中获取清除相关信息:'
ms.openlocfilehash: 6aac92555dda6875f23a177bb09384f453369846
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295921"
---
# <a name="purgesettings-table"></a><span data-ttu-id="62840-104">PurgeSettings 表</span><span class="sxs-lookup"><span data-stu-id="62840-104">PurgeSettings table</span></span>
 
<span data-ttu-id="62840-105">PurgeSettings 表包含指定是否 (和何时) 过期的呼叫详细记录将从 CDR 数据库中自动删除的信息。</span><span class="sxs-lookup"><span data-stu-id="62840-105">The PurgeSettings table contains information that specifies if (and when) outdated call detail records will automatically be deleted from the CDR database.</span></span> <span data-ttu-id="62840-106">请注意, 通过运行以下命令, 还可以从 Skype for Business Server 2015 中获取清除相关信息:</span><span class="sxs-lookup"><span data-stu-id="62840-106">Note that purging-related information can also be obtained from within the Skype for Business Server 2015 by running the following command:</span></span>
  
```
Get-CsCdrConfiguration
```

<span data-ttu-id="62840-107">管理员应将 PurgeSettings 表视为只读: 仅应使用[新的-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps)或[CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlet 进行对呼叫详细信息清除设置的更改。</span><span class="sxs-lookup"><span data-stu-id="62840-107">Administrators should treat the PurgeSettings table as read-only: changes to the call detail purge settings should only be made using the [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) or [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlets.</span></span>
  
<span data-ttu-id="62840-108">此表是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="62840-108">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="62840-109">**列**</span><span class="sxs-lookup"><span data-stu-id="62840-109">**Column**</span></span>|<span data-ttu-id="62840-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="62840-110">**Data Type**</span></span>|<span data-ttu-id="62840-111">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="62840-111">**Key/Index**</span></span>|<span data-ttu-id="62840-112">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="62840-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="62840-113">**标识号**</span><span class="sxs-lookup"><span data-stu-id="62840-113">**Id**</span></span> <br/> |<span data-ttu-id="62840-114">int</span><span class="sxs-lookup"><span data-stu-id="62840-114">int</span></span>  <br/> |<span data-ttu-id="62840-115">Primary</span><span class="sxs-lookup"><span data-stu-id="62840-115">Primary</span></span>  <br/> |<span data-ttu-id="62840-116">CDR 清除设置集合的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="62840-116">Unique identifier for the collection of CDR purge settings.</span></span>  <br/> |
|<span data-ttu-id="62840-117">**EnablePurge**</span><span class="sxs-lookup"><span data-stu-id="62840-117">**EnablePurge**</span></span> <br/> |<span data-ttu-id="62840-118">bit</span><span class="sxs-lookup"><span data-stu-id="62840-118">bit</span></span>  <br/> ||<span data-ttu-id="62840-119">设置为 True (1) Skype for Business Server 2015 将定期从 CDR 数据库中清除过时的记录。</span><span class="sxs-lookup"><span data-stu-id="62840-119">When set to True (1) Skype for Business Server 2015 will periodically purge outdated records from the CDR database.</span></span> <span data-ttu-id="62840-120">将在 PurgeHour 设置指定的圣多美中每天进行清除。</span><span class="sxs-lookup"><span data-stu-id="62840-120">Purging will take place each day at the tome specified by the PurgeHour setting.</span></span> <span data-ttu-id="62840-121">如果设置为 False (0), 将不会从数据库中自动清除记录。</span><span class="sxs-lookup"><span data-stu-id="62840-121">If set to False (0) then records will not be automatically purged from the database.</span></span> <span data-ttu-id="62840-122">默认值为 True。</span><span class="sxs-lookup"><span data-stu-id="62840-122">The default value is True.</span></span>  <br/> |
|<span data-ttu-id="62840-123">**KeepCallDetailForDays**</span><span class="sxs-lookup"><span data-stu-id="62840-123">**KeepCallDetailForDays**</span></span> <br/> |<span data-ttu-id="62840-124">int</span><span class="sxs-lookup"><span data-stu-id="62840-124">int</span></span>  <br/> ||<span data-ttu-id="62840-125">指定将从数据库中清除的 CDR 记录的保留时间 (以天为单位): 如果启用清除, 则早于此值的 CDR 记录将从数据库中删除。</span><span class="sxs-lookup"><span data-stu-id="62840-125">Specifies the age of CDR records (in days) that will be purged from the database: if purging is enabled, CDR records older than this value will be removed from the database.</span></span> <span data-ttu-id="62840-126">默认值为60天。</span><span class="sxs-lookup"><span data-stu-id="62840-126">The default value is 60 days.</span></span>  <br/> |
|<span data-ttu-id="62840-127">**KeepErrorReportForDays**</span><span class="sxs-lookup"><span data-stu-id="62840-127">**KeepErrorReportForDays**</span></span> <br/> |<span data-ttu-id="62840-128">int</span><span class="sxs-lookup"><span data-stu-id="62840-128">int</span></span>  <br/> ||<span data-ttu-id="62840-129">指定将从数据库中清除的错误报告记录的保留时间 (以天为单位): 如果启用清除, 则早于此值的错误报告记录将从数据库中删除。</span><span class="sxs-lookup"><span data-stu-id="62840-129">Specifies the age of error report records (in days) that will be purged from the database: if purging is enabled, error report records older than this value will be removed from the database.</span></span> <span data-ttu-id="62840-130">默认值为60天。</span><span class="sxs-lookup"><span data-stu-id="62840-130">The default value is 60 days.</span></span>  <br/> |
|<span data-ttu-id="62840-131">**PurgeHour**</span><span class="sxs-lookup"><span data-stu-id="62840-131">**PurgeHour**</span></span> <br/> |<span data-ttu-id="62840-132">int</span><span class="sxs-lookup"><span data-stu-id="62840-132">int</span></span>  <br/> ||<span data-ttu-id="62840-133">指定每天执行数据库清除的本地时间。</span><span class="sxs-lookup"><span data-stu-id="62840-133">Specifies the local time of day when database purging will take place.</span></span> <span data-ttu-id="62840-134">该时间使用 24 小时制格式指定，0 表示午夜（晚上 12:00），23 表示晚上 11:00。</span><span class="sxs-lookup"><span data-stu-id="62840-134">The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM.</span></span> <span data-ttu-id="62840-135">请注意, 你只能指定一天中的小时数: 值 10 (表示 10:00 am) 是允许的值, 但不允许值 10.5 10:30 (表示 10:30 am)。</span><span class="sxs-lookup"><span data-stu-id="62840-135">Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed.</span></span> <span data-ttu-id="62840-136">默认值为 2 (2:00 AM)。</span><span class="sxs-lookup"><span data-stu-id="62840-136">The default value is 2 (2:00 AM).</span></span>  <br/> |
   

