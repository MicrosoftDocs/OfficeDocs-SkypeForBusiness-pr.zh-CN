---
title: PurgeSettings 表 (QoE)
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 31b85d1c-3f32-4f67-94bf-9389cdd282c5
description: PurgeSettings 表中的信息，如果 （并且当） 指定将自动从 QoE 数据库中删除过时的体验质量记录。 请注意，清除相关信息也可以获得从在 Skype 的业务服务器管理外壳程序通过运行以下命令：
ms.openlocfilehash: 1acccbd796e20f099df895260cb34f9597718cdd
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="purgesettings-table-qoe"></a><span data-ttu-id="89856-104">PurgeSettings 表 (QoE)</span><span class="sxs-lookup"><span data-stu-id="89856-104">PurgeSettings table (QoE)</span></span>
 
<span data-ttu-id="89856-105">PurgeSettings 表中的信息，如果 （并且当） 指定将自动从 QoE 数据库中删除过时的体验质量记录。</span><span class="sxs-lookup"><span data-stu-id="89856-105">The PurgeSettings table contains information that specifies if (and when) outdated Quality of Experience records will automatically be deleted from the QoE database.</span></span> <span data-ttu-id="89856-106">请注意，清除相关信息也可以获得从在 Skype 的业务服务器管理外壳程序通过运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="89856-106">Note that purging-related information can also be obtained from within the Skype for Business Server Management Shell by running the following command:</span></span>
  
```
Get-CsQoEConfiguration
```

<span data-ttu-id="89856-107">在 Microsoft Lync Server 2013 引入了此表。</span><span class="sxs-lookup"><span data-stu-id="89856-107">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="89856-108">**列**</span><span class="sxs-lookup"><span data-stu-id="89856-108">**Column**</span></span>|<span data-ttu-id="89856-109">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="89856-109">**Data Type**</span></span>|<span data-ttu-id="89856-110">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="89856-110">**Key/Index**</span></span>|<span data-ttu-id="89856-111">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="89856-111">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="89856-112">**标识**</span><span class="sxs-lookup"><span data-stu-id="89856-112">**ID**</span></span> <br/> |<span data-ttu-id="89856-113">int</span><span class="sxs-lookup"><span data-stu-id="89856-113">int</span></span>  <br/> |<span data-ttu-id="89856-114">Primary</span><span class="sxs-lookup"><span data-stu-id="89856-114">Primary</span></span>  <br/> |<span data-ttu-id="89856-115">唯一标识符集合的 QoE 清除设置。</span><span class="sxs-lookup"><span data-stu-id="89856-115">Unique identifier for the collection of QoE purge settings.</span></span>  <br/> |
|<span data-ttu-id="89856-116">**EnablePurge**</span><span class="sxs-lookup"><span data-stu-id="89856-116">**EnablePurge**</span></span> <br/> |<span data-ttu-id="89856-117">bit</span><span class="sxs-lookup"><span data-stu-id="89856-117">bit</span></span>  <br/> ||<span data-ttu-id="89856-118">如果设置为 True （1) Microsoft Lync Server 2013 将定期清除过时的 QoE 数据库中的记录。</span><span class="sxs-lookup"><span data-stu-id="89856-118">When set to True (1) Microsoft Lync Server 2013 will periodically purge outdated records from the QoE database.</span></span> <span data-ttu-id="89856-119">清除操作会在圣多美 PurgeHour 设置所指定的每一天。</span><span class="sxs-lookup"><span data-stu-id="89856-119">Purging will take place each day at the tome specified by the PurgeHour setting.</span></span> <span data-ttu-id="89856-120">如果设置为 False (0) 然后记录将不会自动清除数据库中。</span><span class="sxs-lookup"><span data-stu-id="89856-120">If set to False (0) then records will not be automatically purged from the database.</span></span> <span data-ttu-id="89856-121">默认值为 True。</span><span class="sxs-lookup"><span data-stu-id="89856-121">The default value is True.</span></span>  <br/> |
|<span data-ttu-id="89856-122">**KeepQoEDataForDays**</span><span class="sxs-lookup"><span data-stu-id="89856-122">**KeepQoEDataForDays**</span></span> <br/> |<span data-ttu-id="89856-123">int</span><span class="sxs-lookup"><span data-stu-id="89856-123">int</span></span>  <br/> ||<span data-ttu-id="89856-124">指定了多长时间 （以天为单位） 将从数据库中清除的 QoE 记录： 如果启用了清除，将从数据库中删除早于此值 QoE 记录。</span><span class="sxs-lookup"><span data-stu-id="89856-124">Specifies the age of QoE records (in days) that will be purged from the database: if purging is enabled, QoE records older than this value will be removed from the database.</span></span> <span data-ttu-id="89856-125">默认值为 60 天。</span><span class="sxs-lookup"><span data-stu-id="89856-125">The default value is 60 days.</span></span>  <br/> |
|<span data-ttu-id="89856-126">**PurgeHour**</span><span class="sxs-lookup"><span data-stu-id="89856-126">**PurgeHour**</span></span> <br/> |<span data-ttu-id="89856-127">int</span><span class="sxs-lookup"><span data-stu-id="89856-127">int</span></span>  <br/> ||<span data-ttu-id="89856-128">指定当数据库清除将会发生一天的当地时间。</span><span class="sxs-lookup"><span data-stu-id="89856-128">Specifies the local time of day when database purging will take place.</span></span> <span data-ttu-id="89856-129">该时间使用 24 小时制格式指定，0 表示午夜（晚上 12:00），23 表示晚上 11:00。</span><span class="sxs-lookup"><span data-stu-id="89856-129">The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM.</span></span> <span data-ttu-id="89856-130">请注意，您可以只指定一天中的小时： 允许值 （指示上午 10:00） 10，但不是允许的值为 10:30 的 10.5 （指明上午 10:30）。</span><span class="sxs-lookup"><span data-stu-id="89856-130">Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed.</span></span> <span data-ttu-id="89856-131">默认值为 1 (1:00 AM)。</span><span class="sxs-lookup"><span data-stu-id="89856-131">The default value is 1 (1:00 AM).</span></span> <span data-ttu-id="89856-132">指定当数据库清除将会发生一天的当地时间。</span><span class="sxs-lookup"><span data-stu-id="89856-132">Specifies the local time of day when database purging will take place.</span></span> <span data-ttu-id="89856-133">该时间使用 24 小时制格式指定，0 表示午夜（晚上 12:00），23 表示晚上 11:00。</span><span class="sxs-lookup"><span data-stu-id="89856-133">The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM.</span></span> <span data-ttu-id="89856-134">请注意，您可以只指定一天中的小时： 允许值 （指示上午 10:00） 10，但不是允许的值为 10:30 的 10.5 （指明上午 10:30）。</span><span class="sxs-lookup"><span data-stu-id="89856-134">Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed.</span></span> <span data-ttu-id="89856-135">默认值为 1 (1:00 AM)。</span><span class="sxs-lookup"><span data-stu-id="89856-135">The default value is 1 (1:00 AM).</span></span>  <br/> |
   

