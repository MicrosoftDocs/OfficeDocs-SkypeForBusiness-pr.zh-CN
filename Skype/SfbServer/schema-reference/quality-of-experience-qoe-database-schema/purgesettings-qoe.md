---
title: PurgeSettings 表 (QoE)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 31b85d1c-3f32-4f67-94bf-9389cdd282c5
description: PurgeSettings 表包含用于指定是否 （以及何时） 的信息将自动从 QoE 数据库中删除过时的用户体验质量记录。 请注意，清除相关的信息也可以获得从 Skype 内的业务 Server 命令行管理程序通过运行以下命令：
ms.openlocfilehash: 2b78f066907d6d0763fab7faa9d378e51f3715fc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924785"
---
# <a name="purgesettings-table-qoe"></a><span data-ttu-id="7e336-104">PurgeSettings 表 (QoE)</span><span class="sxs-lookup"><span data-stu-id="7e336-104">PurgeSettings table (QoE)</span></span>
 
<span data-ttu-id="7e336-105">PurgeSettings 表包含用于指定是否 （以及何时） 的信息将自动从 QoE 数据库中删除过时的用户体验质量记录。</span><span class="sxs-lookup"><span data-stu-id="7e336-105">The PurgeSettings table contains information that specifies if (and when) outdated Quality of Experience records will automatically be deleted from the QoE database.</span></span> <span data-ttu-id="7e336-106">请注意，清除相关的信息也可以获得从 Skype 内的业务 Server 命令行管理程序通过运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="7e336-106">Note that purging-related information can also be obtained from within the Skype for Business Server Management Shell by running the following command:</span></span>
  
```
Get-CsQoEConfiguration
```

<span data-ttu-id="7e336-107">此表是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="7e336-107">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="7e336-108">**列**</span><span class="sxs-lookup"><span data-stu-id="7e336-108">**Column**</span></span>|<span data-ttu-id="7e336-109">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="7e336-109">**Data Type**</span></span>|<span data-ttu-id="7e336-110">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="7e336-110">**Key/Index**</span></span>|<span data-ttu-id="7e336-111">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="7e336-111">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7e336-112">**ID**</span><span class="sxs-lookup"><span data-stu-id="7e336-112">**ID**</span></span> <br/> |<span data-ttu-id="7e336-113">int</span><span class="sxs-lookup"><span data-stu-id="7e336-113">int</span></span>  <br/> |<span data-ttu-id="7e336-114">Primary</span><span class="sxs-lookup"><span data-stu-id="7e336-114">Primary</span></span>  <br/> |<span data-ttu-id="7e336-115">唯一标识符集合的 QoE 清除设置。</span><span class="sxs-lookup"><span data-stu-id="7e336-115">Unique identifier for the collection of QoE purge settings.</span></span>  <br/> |
|<span data-ttu-id="7e336-116">**EnablePurge**</span><span class="sxs-lookup"><span data-stu-id="7e336-116">**EnablePurge**</span></span> <br/> |<span data-ttu-id="7e336-117">bit</span><span class="sxs-lookup"><span data-stu-id="7e336-117">bit</span></span>  <br/> ||<span data-ttu-id="7e336-118">当设置为 True （1) Microsoft Lync Server 2013 定期将从 QoE 数据库清除过期的记录。</span><span class="sxs-lookup"><span data-stu-id="7e336-118">When set to True (1) Microsoft Lync Server 2013 will periodically purge outdated records from the QoE database.</span></span> <span data-ttu-id="7e336-119">清除会发生在圣多美 PurgeHour 设置所指定的每一天。</span><span class="sxs-lookup"><span data-stu-id="7e336-119">Purging will take place each day at the tome specified by the PurgeHour setting.</span></span> <span data-ttu-id="7e336-120">如果设置为 False (0) 然后记录不会自动清除从数据库中。</span><span class="sxs-lookup"><span data-stu-id="7e336-120">If set to False (0) then records will not be automatically purged from the database.</span></span> <span data-ttu-id="7e336-121">默认值为 True。</span><span class="sxs-lookup"><span data-stu-id="7e336-121">The default value is True.</span></span>  <br/> |
|<span data-ttu-id="7e336-122">**KeepQoEDataForDays**</span><span class="sxs-lookup"><span data-stu-id="7e336-122">**KeepQoEDataForDays**</span></span> <br/> |<span data-ttu-id="7e336-123">int</span><span class="sxs-lookup"><span data-stu-id="7e336-123">int</span></span>  <br/> ||<span data-ttu-id="7e336-124">指定将从数据库清除的 QoE 记录 （以天为单位） 的期限： 如果启用清除，则将从数据库中删除早于此值的 QoE 记录。</span><span class="sxs-lookup"><span data-stu-id="7e336-124">Specifies the age of QoE records (in days) that will be purged from the database: if purging is enabled, QoE records older than this value will be removed from the database.</span></span> <span data-ttu-id="7e336-125">默认值为 60 天。</span><span class="sxs-lookup"><span data-stu-id="7e336-125">The default value is 60 days.</span></span>  <br/> |
|<span data-ttu-id="7e336-126">**PurgeHour**</span><span class="sxs-lookup"><span data-stu-id="7e336-126">**PurgeHour**</span></span> <br/> |<span data-ttu-id="7e336-127">int</span><span class="sxs-lookup"><span data-stu-id="7e336-127">int</span></span>  <br/> ||<span data-ttu-id="7e336-128">指定当数据库清除将进行本地时间。</span><span class="sxs-lookup"><span data-stu-id="7e336-128">Specifies the local time of day when database purging will take place.</span></span> <span data-ttu-id="7e336-129">该时间使用 24 小时制格式指定，0 表示午夜（晚上 12:00），23 表示晚上 11:00。</span><span class="sxs-lookup"><span data-stu-id="7e336-129">The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM.</span></span> <span data-ttu-id="7e336-130">请注意，您可以仅指定一天的： 允许的值为 10 （指示上午 10:00），但不是允许的值为 10:30 的 10.5 （指示上午 10:30）。</span><span class="sxs-lookup"><span data-stu-id="7e336-130">Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed.</span></span> <span data-ttu-id="7e336-131">默认值为 1 (1:00)。</span><span class="sxs-lookup"><span data-stu-id="7e336-131">The default value is 1 (1:00 AM).</span></span> <span data-ttu-id="7e336-132">指定当数据库清除将进行本地时间。</span><span class="sxs-lookup"><span data-stu-id="7e336-132">Specifies the local time of day when database purging will take place.</span></span> <span data-ttu-id="7e336-133">该时间使用 24 小时制格式指定，0 表示午夜（晚上 12:00），23 表示晚上 11:00。</span><span class="sxs-lookup"><span data-stu-id="7e336-133">The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM.</span></span> <span data-ttu-id="7e336-134">请注意，您可以仅指定一天的： 允许的值为 10 （指示上午 10:00），但不是允许的值为 10:30 的 10.5 （指示上午 10:30）。</span><span class="sxs-lookup"><span data-stu-id="7e336-134">Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed.</span></span> <span data-ttu-id="7e336-135">默认值为 1 (1:00)。</span><span class="sxs-lookup"><span data-stu-id="7e336-135">The default value is 1 (1:00 AM).</span></span>  <br/> |
   

