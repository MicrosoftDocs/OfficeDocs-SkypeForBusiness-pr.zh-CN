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
description: PurgeSettings 表包含指定是否（和何时）过期的呼叫详细记录将从 CDR 数据库中自动删除的信息。 请注意，通过运行以下命令，还可以从 Skype for Business Server 2015 中获取清除相关信息：
ms.openlocfilehash: fbbd7908446fdb042c8fdfa2f0c8bec2d83b24d9
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992912"
---
# <a name="purgesettings-table"></a><span data-ttu-id="30575-104">PurgeSettings 表</span><span class="sxs-lookup"><span data-stu-id="30575-104">PurgeSettings table</span></span>
 
<span data-ttu-id="30575-105">PurgeSettings 表包含指定是否（和何时）过期的呼叫详细记录将从 CDR 数据库中自动删除的信息。</span><span class="sxs-lookup"><span data-stu-id="30575-105">The PurgeSettings table contains information that specifies if (and when) outdated call detail records will automatically be deleted from the CDR database.</span></span> <span data-ttu-id="30575-106">请注意，通过运行以下命令，还可以从 Skype for Business Server 2015 中获取清除相关信息：</span><span class="sxs-lookup"><span data-stu-id="30575-106">Note that purging-related information can also be obtained from within the Skype for Business Server 2015 by running the following command:</span></span>
  
```PowerShell
Get-CsCdrConfiguration
```

<span data-ttu-id="30575-107">管理员应将 PurgeSettings 表视为只读：仅应使用[新的-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps)或[CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlet 进行对呼叫详细信息清除设置的更改。</span><span class="sxs-lookup"><span data-stu-id="30575-107">Administrators should treat the PurgeSettings table as read-only: changes to the call detail purge settings should only be made using the [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) or [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlets.</span></span>
  
<span data-ttu-id="30575-108">此表是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="30575-108">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="30575-109">**列**</span><span class="sxs-lookup"><span data-stu-id="30575-109">**Column**</span></span>|<span data-ttu-id="30575-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="30575-110">**Data Type**</span></span>|<span data-ttu-id="30575-111">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="30575-111">**Key/Index**</span></span>|<span data-ttu-id="30575-112">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="30575-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="30575-113">**标识号**</span><span class="sxs-lookup"><span data-stu-id="30575-113">**Id**</span></span> <br/> |<span data-ttu-id="30575-114">int</span><span class="sxs-lookup"><span data-stu-id="30575-114">int</span></span>  <br/> |<span data-ttu-id="30575-115">Primary</span><span class="sxs-lookup"><span data-stu-id="30575-115">Primary</span></span>  <br/> |<span data-ttu-id="30575-116">CDR 清除设置集合的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="30575-116">Unique identifier for the collection of CDR purge settings.</span></span>  <br/> |
|<span data-ttu-id="30575-117">**EnablePurge**</span><span class="sxs-lookup"><span data-stu-id="30575-117">**EnablePurge**</span></span> <br/> |<span data-ttu-id="30575-118">bit</span><span class="sxs-lookup"><span data-stu-id="30575-118">bit</span></span>  <br/> ||<span data-ttu-id="30575-119">设置为 True （1） Skype for Business Server 2015 将定期从 CDR 数据库中清除过时的记录。</span><span class="sxs-lookup"><span data-stu-id="30575-119">When set to True (1) Skype for Business Server 2015 will periodically purge outdated records from the CDR database.</span></span> <span data-ttu-id="30575-120">将在 PurgeHour 设置指定的圣多美中每天进行清除。</span><span class="sxs-lookup"><span data-stu-id="30575-120">Purging will take place each day at the tome specified by the PurgeHour setting.</span></span> <span data-ttu-id="30575-121">如果设置为 False （0），将不会从数据库中自动清除记录。</span><span class="sxs-lookup"><span data-stu-id="30575-121">If set to False (0) then records will not be automatically purged from the database.</span></span> <span data-ttu-id="30575-122">默认值为 True。</span><span class="sxs-lookup"><span data-stu-id="30575-122">The default value is True.</span></span>  <br/> |
|<span data-ttu-id="30575-123">**KeepCallDetailForDays**</span><span class="sxs-lookup"><span data-stu-id="30575-123">**KeepCallDetailForDays**</span></span> <br/> |<span data-ttu-id="30575-124">int</span><span class="sxs-lookup"><span data-stu-id="30575-124">int</span></span>  <br/> ||<span data-ttu-id="30575-125">指定将从数据库中清除的 CDR 记录的保留时间（以天为单位）：如果启用清除，则早于此值的 CDR 记录将从数据库中删除。</span><span class="sxs-lookup"><span data-stu-id="30575-125">Specifies the age of CDR records (in days) that will be purged from the database: if purging is enabled, CDR records older than this value will be removed from the database.</span></span> <span data-ttu-id="30575-126">默认值为60天。</span><span class="sxs-lookup"><span data-stu-id="30575-126">The default value is 60 days.</span></span>  <br/> |
|<span data-ttu-id="30575-127">**KeepErrorReportForDays**</span><span class="sxs-lookup"><span data-stu-id="30575-127">**KeepErrorReportForDays**</span></span> <br/> |<span data-ttu-id="30575-128">int</span><span class="sxs-lookup"><span data-stu-id="30575-128">int</span></span>  <br/> ||<span data-ttu-id="30575-129">指定将从数据库中清除的错误报告记录的保留时间（以天为单位）：如果启用清除，则早于此值的错误报告记录将从数据库中删除。</span><span class="sxs-lookup"><span data-stu-id="30575-129">Specifies the age of error report records (in days) that will be purged from the database: if purging is enabled, error report records older than this value will be removed from the database.</span></span> <span data-ttu-id="30575-130">默认值为60天。</span><span class="sxs-lookup"><span data-stu-id="30575-130">The default value is 60 days.</span></span>  <br/> |
|<span data-ttu-id="30575-131">**PurgeHour**</span><span class="sxs-lookup"><span data-stu-id="30575-131">**PurgeHour**</span></span> <br/> |<span data-ttu-id="30575-132">int</span><span class="sxs-lookup"><span data-stu-id="30575-132">int</span></span>  <br/> ||<span data-ttu-id="30575-133">指定每天执行数据库清除的本地时间。</span><span class="sxs-lookup"><span data-stu-id="30575-133">Specifies the local time of day when database purging will take place.</span></span> <span data-ttu-id="30575-134">该时间使用 24 小时制格式指定，0 表示午夜（晚上 12:00），23 表示晚上 11:00。</span><span class="sxs-lookup"><span data-stu-id="30575-134">The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM.</span></span> <span data-ttu-id="30575-135">请注意，你只能指定一天中的小时数：值10（表示 10:00 AM）是允许的值，但不允许值 10.5 10:30 （表示 10:30 AM）。</span><span class="sxs-lookup"><span data-stu-id="30575-135">Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed.</span></span> <span data-ttu-id="30575-136">默认值为 2 (2:00 AM)。</span><span class="sxs-lookup"><span data-stu-id="30575-136">The default value is 2 (2:00 AM).</span></span>  <br/> |
   

