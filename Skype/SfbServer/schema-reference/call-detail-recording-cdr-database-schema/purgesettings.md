---
title: PurgeSettings 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9ff2c8fc-4ae8-4f22-96a8-1f4d5eecbf2d
description: PurgeSettings 表包含用于指定是否 （以及何时） 的信息将自动从 CDR 数据库中删除过时的呼叫详细记录。 请注意，清除相关的信息也可以获得从 Skype 内的业务服务器 2015年通过运行以下命令：
ms.openlocfilehash: f1e982d50ab029ec2756e8fb4a92f5c01dc327b8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930719"
---
# <a name="purgesettings-table"></a><span data-ttu-id="5a51c-104">PurgeSettings 表</span><span class="sxs-lookup"><span data-stu-id="5a51c-104">PurgeSettings table</span></span>
 
<span data-ttu-id="5a51c-105">PurgeSettings 表包含用于指定是否 （以及何时） 的信息将自动从 CDR 数据库中删除过时的呼叫详细记录。</span><span class="sxs-lookup"><span data-stu-id="5a51c-105">The PurgeSettings table contains information that specifies if (and when) outdated call detail records will automatically be deleted from the CDR database.</span></span> <span data-ttu-id="5a51c-106">请注意，清除相关的信息也可以获得从 Skype 内的业务服务器 2015年通过运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="5a51c-106">Note that purging-related information can also be obtained from within the Skype for Business Server 2015 by running the following command:</span></span>
  
```
Get-CsCdrConfiguration
```

<span data-ttu-id="5a51c-107">管理员应将 PurgeSettings 表视为只读： 仅应使用[New-cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps)或[Set-cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlet 进行更改呼叫详细信息清除设置。</span><span class="sxs-lookup"><span data-stu-id="5a51c-107">Administrators should treat the PurgeSettings table as read-only: changes to the call detail purge settings should only be made using the [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) or [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlets.</span></span>
  
<span data-ttu-id="5a51c-108">此表是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="5a51c-108">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="5a51c-109">**列**</span><span class="sxs-lookup"><span data-stu-id="5a51c-109">**Column**</span></span>|<span data-ttu-id="5a51c-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="5a51c-110">**Data Type**</span></span>|<span data-ttu-id="5a51c-111">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="5a51c-111">**Key/Index**</span></span>|<span data-ttu-id="5a51c-112">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="5a51c-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5a51c-113">**Id**</span><span class="sxs-lookup"><span data-stu-id="5a51c-113">**Id**</span></span> <br/> |<span data-ttu-id="5a51c-114">int</span><span class="sxs-lookup"><span data-stu-id="5a51c-114">int</span></span>  <br/> |<span data-ttu-id="5a51c-115">Primary</span><span class="sxs-lookup"><span data-stu-id="5a51c-115">Primary</span></span>  <br/> |<span data-ttu-id="5a51c-116">清除设置集合的 CDR 的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="5a51c-116">Unique identifier for the collection of CDR purge settings.</span></span>  <br/> |
|<span data-ttu-id="5a51c-117">**EnablePurge**</span><span class="sxs-lookup"><span data-stu-id="5a51c-117">**EnablePurge**</span></span> <br/> |<span data-ttu-id="5a51c-118">bit</span><span class="sxs-lookup"><span data-stu-id="5a51c-118">bit</span></span>  <br/> ||<span data-ttu-id="5a51c-119">当设置为 True (1) 的 Skype 业务服务器 2015年将定期清除过时的 CDR 数据库中的记录。</span><span class="sxs-lookup"><span data-stu-id="5a51c-119">When set to True (1) Skype for Business Server 2015 will periodically purge outdated records from the CDR database.</span></span> <span data-ttu-id="5a51c-120">清除会发生在圣多美 PurgeHour 设置所指定的每一天。</span><span class="sxs-lookup"><span data-stu-id="5a51c-120">Purging will take place each day at the tome specified by the PurgeHour setting.</span></span> <span data-ttu-id="5a51c-121">如果设置为 False (0) 然后记录不会自动清除从数据库中。</span><span class="sxs-lookup"><span data-stu-id="5a51c-121">If set to False (0) then records will not be automatically purged from the database.</span></span> <span data-ttu-id="5a51c-122">默认值为 True。</span><span class="sxs-lookup"><span data-stu-id="5a51c-122">The default value is True.</span></span>  <br/> |
|<span data-ttu-id="5a51c-123">**KeepCallDetailForDays**</span><span class="sxs-lookup"><span data-stu-id="5a51c-123">**KeepCallDetailForDays**</span></span> <br/> |<span data-ttu-id="5a51c-124">int</span><span class="sxs-lookup"><span data-stu-id="5a51c-124">int</span></span>  <br/> ||<span data-ttu-id="5a51c-125">指定将从数据库清除的 CDR 记录 （以天为单位） 的期限： 如果启用清除，则将从数据库中删除 CDR 记录超过此值。</span><span class="sxs-lookup"><span data-stu-id="5a51c-125">Specifies the age of CDR records (in days) that will be purged from the database: if purging is enabled, CDR records older than this value will be removed from the database.</span></span> <span data-ttu-id="5a51c-126">默认值为 60 天。</span><span class="sxs-lookup"><span data-stu-id="5a51c-126">The default value is 60 days.</span></span>  <br/> |
|<span data-ttu-id="5a51c-127">**KeepErrorReportForDays**</span><span class="sxs-lookup"><span data-stu-id="5a51c-127">**KeepErrorReportForDays**</span></span> <br/> |<span data-ttu-id="5a51c-128">int</span><span class="sxs-lookup"><span data-stu-id="5a51c-128">int</span></span>  <br/> ||<span data-ttu-id="5a51c-129">指定将从数据库清除的错误报告记录 （以天为单位） 的期限： 如果启用清除，则将从数据库中删除错误报告记录超过此值。</span><span class="sxs-lookup"><span data-stu-id="5a51c-129">Specifies the age of error report records (in days) that will be purged from the database: if purging is enabled, error report records older than this value will be removed from the database.</span></span> <span data-ttu-id="5a51c-130">默认值为 60 天。</span><span class="sxs-lookup"><span data-stu-id="5a51c-130">The default value is 60 days.</span></span>  <br/> |
|<span data-ttu-id="5a51c-131">**PurgeHour**</span><span class="sxs-lookup"><span data-stu-id="5a51c-131">**PurgeHour**</span></span> <br/> |<span data-ttu-id="5a51c-132">int</span><span class="sxs-lookup"><span data-stu-id="5a51c-132">int</span></span>  <br/> ||<span data-ttu-id="5a51c-133">指定当数据库清除将进行本地时间。</span><span class="sxs-lookup"><span data-stu-id="5a51c-133">Specifies the local time of day when database purging will take place.</span></span> <span data-ttu-id="5a51c-134">该时间使用 24 小时制格式指定，0 表示午夜（晚上 12:00），23 表示晚上 11:00。</span><span class="sxs-lookup"><span data-stu-id="5a51c-134">The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM.</span></span> <span data-ttu-id="5a51c-135">请注意，您可以仅指定一天的： 允许的值为 10 （指示上午 10:00），但不是允许的值为 10:30 的 10.5 （指示上午 10:30）。</span><span class="sxs-lookup"><span data-stu-id="5a51c-135">Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed.</span></span> <span data-ttu-id="5a51c-136">默认值为 2 (2:00 AM)。</span><span class="sxs-lookup"><span data-stu-id="5a51c-136">The default value is 2 (2:00 AM).</span></span>  <br/> |
   

