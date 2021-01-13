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
description: PurgeSettings 表包括用于指定是否（以及何时）自动从 CDR 数据库中删除过时的呼叫详细信息记录的信息。 请注意，通过运行以下命令，还可以从 Skype for Business Server 2015 中获取清除相关信息：
ms.openlocfilehash: c90c36dc91eaaac6fe38c6eea8e2a5617264e200
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823162"
---
# <a name="purgesettings-table"></a><span data-ttu-id="d880f-104">PurgeSettings 表</span><span class="sxs-lookup"><span data-stu-id="d880f-104">PurgeSettings table</span></span>
 
<span data-ttu-id="d880f-105">PurgeSettings 表包括用于指定是否（以及何时）自动从 CDR 数据库中删除过时的呼叫详细信息记录的信息。</span><span class="sxs-lookup"><span data-stu-id="d880f-105">The PurgeSettings table contains information that specifies if (and when) outdated call detail records will automatically be deleted from the CDR database.</span></span> <span data-ttu-id="d880f-106">请注意，通过运行以下命令，还可以从 Skype for Business Server 2015 中获取清除相关信息：</span><span class="sxs-lookup"><span data-stu-id="d880f-106">Note that purging-related information can also be obtained from within the Skype for Business Server 2015 by running the following command:</span></span>
  
```PowerShell
Get-CsCdrConfiguration
```

<span data-ttu-id="d880f-107">管理员应将 PurgeSettings 表视为只读：只能使用 [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) 或 [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlet 更改呼叫详细信息清除设置。</span><span class="sxs-lookup"><span data-stu-id="d880f-107">Administrators should treat the PurgeSettings table as read-only: changes to the call detail purge settings should only be made using the [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) or [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlets.</span></span>
  
<span data-ttu-id="d880f-108">此表在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="d880f-108">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="d880f-109">**列**</span><span class="sxs-lookup"><span data-stu-id="d880f-109">**Column**</span></span>|<span data-ttu-id="d880f-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="d880f-110">**Data Type**</span></span>|<span data-ttu-id="d880f-111">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="d880f-111">**Key/Index**</span></span>|<span data-ttu-id="d880f-112">**Details**</span><span class="sxs-lookup"><span data-stu-id="d880f-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d880f-113">**Id**</span><span class="sxs-lookup"><span data-stu-id="d880f-113">**Id**</span></span> <br/> |<span data-ttu-id="d880f-114">int</span><span class="sxs-lookup"><span data-stu-id="d880f-114">int</span></span>  <br/> |<span data-ttu-id="d880f-115">主</span><span class="sxs-lookup"><span data-stu-id="d880f-115">Primary</span></span>  <br/> |<span data-ttu-id="d880f-116">CDR 清除设置集的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="d880f-116">Unique identifier for the collection of CDR purge settings.</span></span>  <br/> |
|<span data-ttu-id="d880f-117">**EnablePurge**</span><span class="sxs-lookup"><span data-stu-id="d880f-117">**EnablePurge**</span></span> <br/> |<span data-ttu-id="d880f-118">bit</span><span class="sxs-lookup"><span data-stu-id="d880f-118">bit</span></span>  <br/> ||<span data-ttu-id="d880f-119">设置为 True (1 时) Skype for Business Server 2015 将定期清除 CDR 数据库中的过时记录。</span><span class="sxs-lookup"><span data-stu-id="d880f-119">When set to True (1) Skype for Business Server 2015 will periodically purge outdated records from the CDR database.</span></span> <span data-ttu-id="d880f-120">将每天在 PurgeHour 设置所指定的时间执行清除。</span><span class="sxs-lookup"><span data-stu-id="d880f-120">Purging will take place each day at the tome specified by the PurgeHour setting.</span></span> <span data-ttu-id="d880f-121">如果设置为 False (0)，则不会从数据库中自动清除记录。</span><span class="sxs-lookup"><span data-stu-id="d880f-121">If set to False (0) then records will not be automatically purged from the database.</span></span> <span data-ttu-id="d880f-122">默认值为 True。</span><span class="sxs-lookup"><span data-stu-id="d880f-122">The default value is True.</span></span>  <br/> |
|<span data-ttu-id="d880f-123">**KeepCallDetailForDays**</span><span class="sxs-lookup"><span data-stu-id="d880f-123">**KeepCallDetailForDays**</span></span> <br/> |<span data-ttu-id="d880f-124">int</span><span class="sxs-lookup"><span data-stu-id="d880f-124">int</span></span>  <br/> ||<span data-ttu-id="d880f-p104">指定将从数据库中清除的 CDR 记录的时限（以天为单位）：如果启用清除，则将从数据库中清除时限超过此值的 CDR 记录。默认值为 60 天。</span><span class="sxs-lookup"><span data-stu-id="d880f-p104">Specifies the age of CDR records (in days) that will be purged from the database: if purging is enabled, CDR records older than this value will be removed from the database. The default value is 60 days.</span></span>  <br/> |
|<span data-ttu-id="d880f-127">**KeepErrorReportForDays**</span><span class="sxs-lookup"><span data-stu-id="d880f-127">**KeepErrorReportForDays**</span></span> <br/> |<span data-ttu-id="d880f-128">int</span><span class="sxs-lookup"><span data-stu-id="d880f-128">int</span></span>  <br/> ||<span data-ttu-id="d880f-p105">指定将从数据库中清除的错误报告记录的时限（以天为单位）：如果启用清除，则将从数据库中清除时限超过此值的错误报告记录。默认值为 60 天。</span><span class="sxs-lookup"><span data-stu-id="d880f-p105">Specifies the age of error report records (in days) that will be purged from the database: if purging is enabled, error report records older than this value will be removed from the database. The default value is 60 days.</span></span>  <br/> |
|<span data-ttu-id="d880f-131">**PurgeHour**</span><span class="sxs-lookup"><span data-stu-id="d880f-131">**PurgeHour**</span></span> <br/> |<span data-ttu-id="d880f-132">int</span><span class="sxs-lookup"><span data-stu-id="d880f-132">int</span></span>  <br/> ||<span data-ttu-id="d880f-p106">指定将执行数据库清除的本地时间。时间以 24 小时制的形式指定，0 表示午夜 (12:00 AM)，23 表示 11:00 PM。请注意，您只能指定小时时间：允许值 10（指示 10:00 AM），但不允许值 10.5（指示 10:30 AM）。默认值为 2 (2:00 AM)。</span><span class="sxs-lookup"><span data-stu-id="d880f-p106">Specifies the local time of day when database purging will take place. The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM. Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed. The default value is 2 (2:00 AM).</span></span>  <br/> |
   

