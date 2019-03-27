---
title: PurgeSettings 表 (QoE)
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 31b85d1c-3f32-4f67-94bf-9389cdd282c5
description: PurgeSettings 表包含用于指定是否 （以及何时） 的信息将自动从 QoE 数据库中删除过时的用户体验质量记录。 请注意，清除相关的信息也可以获得从 Skype 内的业务 Server 命令行管理程序通过运行以下命令：
ms.openlocfilehash: b9aaa8b5fd988e1fb1476ec75077507b55aaf9d1
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30873617"
---
# <a name="purgesettings-table-qoe"></a><span data-ttu-id="46487-104">PurgeSettings 表 (QoE)</span><span class="sxs-lookup"><span data-stu-id="46487-104">PurgeSettings table (QoE)</span></span>
 
<span data-ttu-id="46487-105">PurgeSettings 表包含用于指定是否 （以及何时） 的信息将自动从 QoE 数据库中删除过时的用户体验质量记录。</span><span class="sxs-lookup"><span data-stu-id="46487-105">The PurgeSettings table contains information that specifies if (and when) outdated Quality of Experience records will automatically be deleted from the QoE database.</span></span> <span data-ttu-id="46487-106">请注意，清除相关的信息也可以获得从 Skype 内的业务 Server 命令行管理程序通过运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="46487-106">Note that purging-related information can also be obtained from within the Skype for Business Server Management Shell by running the following command:</span></span>
  
```
Get-CsQoEConfiguration
```

<span data-ttu-id="46487-107">此表是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="46487-107">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="46487-108">**列**</span><span class="sxs-lookup"><span data-stu-id="46487-108">**Column**</span></span>|<span data-ttu-id="46487-109">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="46487-109">**Data Type**</span></span>|<span data-ttu-id="46487-110">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="46487-110">**Key/Index**</span></span>|<span data-ttu-id="46487-111">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="46487-111">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="46487-112">**ID**</span><span class="sxs-lookup"><span data-stu-id="46487-112">**ID**</span></span> <br/> |<span data-ttu-id="46487-113">int</span><span class="sxs-lookup"><span data-stu-id="46487-113">int</span></span>  <br/> |<span data-ttu-id="46487-114">Primary</span><span class="sxs-lookup"><span data-stu-id="46487-114">Primary</span></span>  <br/> |<span data-ttu-id="46487-115">唯一标识符集合的 QoE 清除设置。</span><span class="sxs-lookup"><span data-stu-id="46487-115">Unique identifier for the collection of QoE purge settings.</span></span>  <br/> |
|<span data-ttu-id="46487-116">**EnablePurge**</span><span class="sxs-lookup"><span data-stu-id="46487-116">**EnablePurge**</span></span> <br/> |<span data-ttu-id="46487-117">bit</span><span class="sxs-lookup"><span data-stu-id="46487-117">bit</span></span>  <br/> ||<span data-ttu-id="46487-118">当设置为 True （1) Microsoft Lync Server 2013 定期将从 QoE 数据库清除过期的记录。</span><span class="sxs-lookup"><span data-stu-id="46487-118">When set to True (1) Microsoft Lync Server 2013 will periodically purge outdated records from the QoE database.</span></span> <span data-ttu-id="46487-119">清除会发生在圣多美 PurgeHour 设置所指定的每一天。</span><span class="sxs-lookup"><span data-stu-id="46487-119">Purging will take place each day at the tome specified by the PurgeHour setting.</span></span> <span data-ttu-id="46487-120">如果设置为 False (0) 然后记录不会自动清除从数据库中。</span><span class="sxs-lookup"><span data-stu-id="46487-120">If set to False (0) then records will not be automatically purged from the database.</span></span> <span data-ttu-id="46487-121">默认值为 True。</span><span class="sxs-lookup"><span data-stu-id="46487-121">The default value is True.</span></span>  <br/> |
|<span data-ttu-id="46487-122">**KeepQoEDataForDays**</span><span class="sxs-lookup"><span data-stu-id="46487-122">**KeepQoEDataForDays**</span></span> <br/> |<span data-ttu-id="46487-123">int</span><span class="sxs-lookup"><span data-stu-id="46487-123">int</span></span>  <br/> ||<span data-ttu-id="46487-124">指定将从数据库清除的 QoE 记录 （以天为单位） 的期限： 如果启用清除，则将从数据库中删除早于此值的 QoE 记录。</span><span class="sxs-lookup"><span data-stu-id="46487-124">Specifies the age of QoE records (in days) that will be purged from the database: if purging is enabled, QoE records older than this value will be removed from the database.</span></span> <span data-ttu-id="46487-125">默认值为 60 天。</span><span class="sxs-lookup"><span data-stu-id="46487-125">The default value is 60 days.</span></span>  <br/> |
|<span data-ttu-id="46487-126">**PurgeHour**</span><span class="sxs-lookup"><span data-stu-id="46487-126">**PurgeHour**</span></span> <br/> |<span data-ttu-id="46487-127">int</span><span class="sxs-lookup"><span data-stu-id="46487-127">int</span></span>  <br/> ||<span data-ttu-id="46487-128">指定当数据库清除将进行本地时间。</span><span class="sxs-lookup"><span data-stu-id="46487-128">Specifies the local time of day when database purging will take place.</span></span> <span data-ttu-id="46487-129">该时间使用 24 小时制格式指定，0 表示午夜（晚上 12:00），23 表示晚上 11:00。</span><span class="sxs-lookup"><span data-stu-id="46487-129">The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM.</span></span> <span data-ttu-id="46487-130">请注意，您可以仅指定一天的： 允许的值为 10 （指示上午 10:00），但不是允许的值为 10:30 的 10.5 （指示上午 10:30）。</span><span class="sxs-lookup"><span data-stu-id="46487-130">Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed.</span></span> <span data-ttu-id="46487-131">默认值为 1 (1:00)。</span><span class="sxs-lookup"><span data-stu-id="46487-131">The default value is 1 (1:00 AM).</span></span> <span data-ttu-id="46487-132">指定当数据库清除将进行本地时间。</span><span class="sxs-lookup"><span data-stu-id="46487-132">Specifies the local time of day when database purging will take place.</span></span> <span data-ttu-id="46487-133">该时间使用 24 小时制格式指定，0 表示午夜（晚上 12:00），23 表示晚上 11:00。</span><span class="sxs-lookup"><span data-stu-id="46487-133">The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM.</span></span> <span data-ttu-id="46487-134">请注意，您可以仅指定一天的： 允许的值为 10 （指示上午 10:00），但不是允许的值为 10:30 的 10.5 （指示上午 10:30）。</span><span class="sxs-lookup"><span data-stu-id="46487-134">Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed.</span></span> <span data-ttu-id="46487-135">默认值为 1 (1:00)。</span><span class="sxs-lookup"><span data-stu-id="46487-135">The default value is 1 (1:00 AM).</span></span>  <br/> |
   

