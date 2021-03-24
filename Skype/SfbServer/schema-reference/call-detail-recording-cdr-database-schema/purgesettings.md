---
title: PurgeSettings 表
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9ff2c8fc-4ae8-4f22-96a8-1f4d5eecbf2d
description: PurgeSettings 表包括用于指定是否（以及何时）自动从 CDR 数据库中删除过时的呼叫详细信息记录的信息。 请注意，还可通过运行以下命令从 Skype for Business Server 2015 中获取清除相关信息：
ms.openlocfilehash: 2e834f64ca5500f8d8bab1d89fb263d2708fa60c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098658"
---
# <a name="purgesettings-table"></a><span data-ttu-id="372e1-104">PurgeSettings 表</span><span class="sxs-lookup"><span data-stu-id="372e1-104">PurgeSettings table</span></span>
 
<span data-ttu-id="372e1-105">PurgeSettings 表包括用于指定是否（以及何时）自动从 CDR 数据库中删除过时的呼叫详细信息记录的信息。</span><span class="sxs-lookup"><span data-stu-id="372e1-105">The PurgeSettings table contains information that specifies if (and when) outdated call detail records will automatically be deleted from the CDR database.</span></span> <span data-ttu-id="372e1-106">请注意，还可通过运行以下命令从 Skype for Business Server 2015 中获取清除相关信息：</span><span class="sxs-lookup"><span data-stu-id="372e1-106">Note that purging-related information can also be obtained from within the Skype for Business Server 2015 by running the following command:</span></span>
  
```PowerShell
Get-CsCdrConfiguration
```

<span data-ttu-id="372e1-107">管理员应将 PurgeSettings 表视为只读：只能使用 [New-CsCdrConfiguration](/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) 或 [Set-CsCdrConfiguration](/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlet 更改呼叫详细信息清除设置。</span><span class="sxs-lookup"><span data-stu-id="372e1-107">Administrators should treat the PurgeSettings table as read-only: changes to the call detail purge settings should only be made using the [New-CsCdrConfiguration](/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) or [Set-CsCdrConfiguration](/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlets.</span></span>
  
<span data-ttu-id="372e1-108">此表在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="372e1-108">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="372e1-109">**列**</span><span class="sxs-lookup"><span data-stu-id="372e1-109">**Column**</span></span>|<span data-ttu-id="372e1-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="372e1-110">**Data Type**</span></span>|<span data-ttu-id="372e1-111">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="372e1-111">**Key/Index**</span></span>|<span data-ttu-id="372e1-112">**Details**</span><span class="sxs-lookup"><span data-stu-id="372e1-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="372e1-113">**Id**</span><span class="sxs-lookup"><span data-stu-id="372e1-113">**Id**</span></span> <br/> |<span data-ttu-id="372e1-114">int</span><span class="sxs-lookup"><span data-stu-id="372e1-114">int</span></span>  <br/> |<span data-ttu-id="372e1-115">主</span><span class="sxs-lookup"><span data-stu-id="372e1-115">Primary</span></span>  <br/> |<span data-ttu-id="372e1-116">CDR 清除设置集的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="372e1-116">Unique identifier for the collection of CDR purge settings.</span></span>  <br/> |
|<span data-ttu-id="372e1-117">**EnablePurge**</span><span class="sxs-lookup"><span data-stu-id="372e1-117">**EnablePurge**</span></span> <br/> |<span data-ttu-id="372e1-118">bit</span><span class="sxs-lookup"><span data-stu-id="372e1-118">bit</span></span>  <br/> ||<span data-ttu-id="372e1-119">设置为 True 时 (1) Skype for Business Server 2015 将定期清除 CDR 数据库中的过时记录。</span><span class="sxs-lookup"><span data-stu-id="372e1-119">When set to True (1) Skype for Business Server 2015 will periodically purge outdated records from the CDR database.</span></span> <span data-ttu-id="372e1-120">将每天在 PurgeHour 设置所指定的时间执行清除。</span><span class="sxs-lookup"><span data-stu-id="372e1-120">Purging will take place each day at the tome specified by the PurgeHour setting.</span></span> <span data-ttu-id="372e1-121">如果设置为 False (0)，则不会从数据库中自动清除记录。</span><span class="sxs-lookup"><span data-stu-id="372e1-121">If set to False (0) then records will not be automatically purged from the database.</span></span> <span data-ttu-id="372e1-122">默认值为 True。</span><span class="sxs-lookup"><span data-stu-id="372e1-122">The default value is True.</span></span>  <br/> |
|<span data-ttu-id="372e1-123">**KeepCallDetailForDays**</span><span class="sxs-lookup"><span data-stu-id="372e1-123">**KeepCallDetailForDays**</span></span> <br/> |<span data-ttu-id="372e1-124">int</span><span class="sxs-lookup"><span data-stu-id="372e1-124">int</span></span>  <br/> ||<span data-ttu-id="372e1-p104">指定将从数据库中清除的 CDR 记录的时限（以天为单位）：如果启用清除，则将从数据库中清除时限超过此值的 CDR 记录。默认值为 60 天。</span><span class="sxs-lookup"><span data-stu-id="372e1-p104">Specifies the age of CDR records (in days) that will be purged from the database: if purging is enabled, CDR records older than this value will be removed from the database. The default value is 60 days.</span></span>  <br/> |
|<span data-ttu-id="372e1-127">**KeepErrorReportForDays**</span><span class="sxs-lookup"><span data-stu-id="372e1-127">**KeepErrorReportForDays**</span></span> <br/> |<span data-ttu-id="372e1-128">int</span><span class="sxs-lookup"><span data-stu-id="372e1-128">int</span></span>  <br/> ||<span data-ttu-id="372e1-p105">指定将从数据库中清除的错误报告记录的时限（以天为单位）：如果启用清除，则将从数据库中清除时限超过此值的错误报告记录。默认值为 60 天。</span><span class="sxs-lookup"><span data-stu-id="372e1-p105">Specifies the age of error report records (in days) that will be purged from the database: if purging is enabled, error report records older than this value will be removed from the database. The default value is 60 days.</span></span>  <br/> |
|<span data-ttu-id="372e1-131">**PurgeHour**</span><span class="sxs-lookup"><span data-stu-id="372e1-131">**PurgeHour**</span></span> <br/> |<span data-ttu-id="372e1-132">int</span><span class="sxs-lookup"><span data-stu-id="372e1-132">int</span></span>  <br/> ||<span data-ttu-id="372e1-p106">指定将执行数据库清除的本地时间。时间以 24 小时制的形式指定，0 表示午夜 (12:00 AM)，23 表示 11:00 PM。请注意，您只能指定小时时间：允许值 10（指示 10:00 AM），但不允许值 10.5（指示 10:30 AM）。默认值为 2 (2:00 AM)。</span><span class="sxs-lookup"><span data-stu-id="372e1-p106">Specifies the local time of day when database purging will take place. The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM. Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed. The default value is 2 (2:00 AM).</span></span>  <br/> |
