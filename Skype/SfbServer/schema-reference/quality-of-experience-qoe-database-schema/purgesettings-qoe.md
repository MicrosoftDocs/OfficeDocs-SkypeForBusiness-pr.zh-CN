---
title: PurgeSettings table （QoE）
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 31b85d1c-3f32-4f67-94bf-9389cdd282c5
description: PurgeSettings 表包含用于指定是否会自动从 QoE 数据库中删除过时的体验记录质量的信息。 请注意，通过运行以下命令，还可以从 Skype for Business 服务器管理外壳程序内获取清除相关信息：
ms.openlocfilehash: dab1b2ffeab5882d0e459d7957b2817e780fc3a4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41807329"
---
# <a name="purgesettings-table-qoe"></a><span data-ttu-id="6aa30-104">PurgeSettings table （QoE）</span><span class="sxs-lookup"><span data-stu-id="6aa30-104">PurgeSettings table (QoE)</span></span>
 
<span data-ttu-id="6aa30-105">PurgeSettings 表包含用于指定是否会自动从 QoE 数据库中删除过时的体验记录质量的信息。</span><span class="sxs-lookup"><span data-stu-id="6aa30-105">The PurgeSettings table contains information that specifies if (and when) outdated Quality of Experience records will automatically be deleted from the QoE database.</span></span> <span data-ttu-id="6aa30-106">请注意，通过运行以下命令，还可以从 Skype for Business 服务器管理外壳程序内获取清除相关信息：</span><span class="sxs-lookup"><span data-stu-id="6aa30-106">Note that purging-related information can also be obtained from within the Skype for Business Server Management Shell by running the following command:</span></span>
  
```PowerShell
Get-CsQoEConfiguration
```

<span data-ttu-id="6aa30-107">此表是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="6aa30-107">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="6aa30-108">**列**</span><span class="sxs-lookup"><span data-stu-id="6aa30-108">**Column**</span></span>|<span data-ttu-id="6aa30-109">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="6aa30-109">**Data Type**</span></span>|<span data-ttu-id="6aa30-110">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="6aa30-110">**Key/Index**</span></span>|<span data-ttu-id="6aa30-111">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="6aa30-111">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6aa30-112">**ID**</span><span class="sxs-lookup"><span data-stu-id="6aa30-112">**ID**</span></span> <br/> |<span data-ttu-id="6aa30-113">int</span><span class="sxs-lookup"><span data-stu-id="6aa30-113">int</span></span>  <br/> |<span data-ttu-id="6aa30-114">Primary</span><span class="sxs-lookup"><span data-stu-id="6aa30-114">Primary</span></span>  <br/> |<span data-ttu-id="6aa30-115">QoE 清除设置集合的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="6aa30-115">Unique identifier for the collection of QoE purge settings.</span></span>  <br/> |
|<span data-ttu-id="6aa30-116">**EnablePurge**</span><span class="sxs-lookup"><span data-stu-id="6aa30-116">**EnablePurge**</span></span> <br/> |<span data-ttu-id="6aa30-117">bit</span><span class="sxs-lookup"><span data-stu-id="6aa30-117">bit</span></span>  <br/> ||<span data-ttu-id="6aa30-118">当设置为 True （1）时，Microsoft Lync Server 2013 将定期从 QoE 数据库中清除过时的记录。</span><span class="sxs-lookup"><span data-stu-id="6aa30-118">When set to True (1) Microsoft Lync Server 2013 will periodically purge outdated records from the QoE database.</span></span> <span data-ttu-id="6aa30-119">将在 PurgeHour 设置指定的圣多美中每天进行清除。</span><span class="sxs-lookup"><span data-stu-id="6aa30-119">Purging will take place each day at the tome specified by the PurgeHour setting.</span></span> <span data-ttu-id="6aa30-120">如果设置为 False （0），将不会从数据库中自动清除记录。</span><span class="sxs-lookup"><span data-stu-id="6aa30-120">If set to False (0) then records will not be automatically purged from the database.</span></span> <span data-ttu-id="6aa30-121">默认值为 True。</span><span class="sxs-lookup"><span data-stu-id="6aa30-121">The default value is True.</span></span>  <br/> |
|<span data-ttu-id="6aa30-122">**KeepQoEDataForDays**</span><span class="sxs-lookup"><span data-stu-id="6aa30-122">**KeepQoEDataForDays**</span></span> <br/> |<span data-ttu-id="6aa30-123">int</span><span class="sxs-lookup"><span data-stu-id="6aa30-123">int</span></span>  <br/> ||<span data-ttu-id="6aa30-124">指定将从数据库中清除的 QoE 记录的期限（以天为单位）：如果启用清除，将从数据库中删除早于此值的 QoE 记录。</span><span class="sxs-lookup"><span data-stu-id="6aa30-124">Specifies the age of QoE records (in days) that will be purged from the database: if purging is enabled, QoE records older than this value will be removed from the database.</span></span> <span data-ttu-id="6aa30-125">默认值为60天。</span><span class="sxs-lookup"><span data-stu-id="6aa30-125">The default value is 60 days.</span></span>  <br/> |
|<span data-ttu-id="6aa30-126">**PurgeHour**</span><span class="sxs-lookup"><span data-stu-id="6aa30-126">**PurgeHour**</span></span> <br/> |<span data-ttu-id="6aa30-127">int</span><span class="sxs-lookup"><span data-stu-id="6aa30-127">int</span></span>  <br/> ||<span data-ttu-id="6aa30-128">指定每天执行数据库清除的本地时间。</span><span class="sxs-lookup"><span data-stu-id="6aa30-128">Specifies the local time of day when database purging will take place.</span></span> <span data-ttu-id="6aa30-129">该时间使用 24 小时制格式指定，0 表示午夜（晚上 12:00），23 表示晚上 11:00。</span><span class="sxs-lookup"><span data-stu-id="6aa30-129">The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM.</span></span> <span data-ttu-id="6aa30-130">请注意，你只能指定一天中的小时数：值10（表示 10:00 AM）是允许的值，但不允许值 10.5 10:30 （表示 10:30 AM）。</span><span class="sxs-lookup"><span data-stu-id="6aa30-130">Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed.</span></span> <span data-ttu-id="6aa30-131">默认值为1（1:00 AM）。</span><span class="sxs-lookup"><span data-stu-id="6aa30-131">The default value is 1 (1:00 AM).</span></span> <span data-ttu-id="6aa30-132">指定每天执行数据库清除的本地时间。</span><span class="sxs-lookup"><span data-stu-id="6aa30-132">Specifies the local time of day when database purging will take place.</span></span> <span data-ttu-id="6aa30-133">该时间使用 24 小时制格式指定，0 表示午夜（晚上 12:00），23 表示晚上 11:00。</span><span class="sxs-lookup"><span data-stu-id="6aa30-133">The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM.</span></span> <span data-ttu-id="6aa30-134">请注意，你只能指定一天中的小时数：值10（表示 10:00 AM）是允许的值，但不允许值 10.5 10:30 （表示 10:30 AM）。</span><span class="sxs-lookup"><span data-stu-id="6aa30-134">Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed.</span></span> <span data-ttu-id="6aa30-135">默认值为1（1:00 AM）。</span><span class="sxs-lookup"><span data-stu-id="6aa30-135">The default value is 1 (1:00 AM).</span></span>  <br/> |
   

