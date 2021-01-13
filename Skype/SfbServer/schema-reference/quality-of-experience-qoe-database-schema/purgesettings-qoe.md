---
title: 'QoE (PurgeSettings) '
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 31b85d1c-3f32-4f67-94bf-9389cdd282c5
description: PurgeSettings 表包含指定是否（以及何时）将过时的用户体验质量记录从 QoE 数据库中自动删除。 请注意，通过运行以下命令，还可以从 Skype for Business Server 命令行管理程序 内获取与清除有关的信息：
ms.openlocfilehash: eef723298b04aecf633368d767623488a53ac6ce
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815802"
---
# <a name="purgesettings-table-qoe"></a><span data-ttu-id="7add1-104">QoE (PurgeSettings) </span><span class="sxs-lookup"><span data-stu-id="7add1-104">PurgeSettings table (QoE)</span></span>
 
<span data-ttu-id="7add1-105">PurgeSettings 表包含指定是否（以及何时）将过时的用户体验质量记录从 QoE 数据库中自动删除。</span><span class="sxs-lookup"><span data-stu-id="7add1-105">The PurgeSettings table contains information that specifies if (and when) outdated Quality of Experience records will automatically be deleted from the QoE database.</span></span> <span data-ttu-id="7add1-106">请注意，通过运行以下命令，还可以从 Skype for Business Server 命令行管理程序 内获取与清除有关的信息：</span><span class="sxs-lookup"><span data-stu-id="7add1-106">Note that purging-related information can also be obtained from within the Skype for Business Server Management Shell by running the following command:</span></span>
  
```PowerShell
Get-CsQoEConfiguration
```

<span data-ttu-id="7add1-107">此表在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="7add1-107">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="7add1-108">**列**</span><span class="sxs-lookup"><span data-stu-id="7add1-108">**Column**</span></span>|<span data-ttu-id="7add1-109">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="7add1-109">**Data Type**</span></span>|<span data-ttu-id="7add1-110">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="7add1-110">**Key/Index**</span></span>|<span data-ttu-id="7add1-111">**Details**</span><span class="sxs-lookup"><span data-stu-id="7add1-111">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7add1-112">**ID**</span><span class="sxs-lookup"><span data-stu-id="7add1-112">**ID**</span></span> <br/> |<span data-ttu-id="7add1-113">int</span><span class="sxs-lookup"><span data-stu-id="7add1-113">int</span></span>  <br/> |<span data-ttu-id="7add1-114">主</span><span class="sxs-lookup"><span data-stu-id="7add1-114">Primary</span></span>  <br/> |<span data-ttu-id="7add1-115">QoE 清除设置集合的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="7add1-115">Unique identifier for the collection of QoE purge settings.</span></span>  <br/> |
|<span data-ttu-id="7add1-116">**EnablePurge**</span><span class="sxs-lookup"><span data-stu-id="7add1-116">**EnablePurge**</span></span> <br/> |<span data-ttu-id="7add1-117">bit</span><span class="sxs-lookup"><span data-stu-id="7add1-117">bit</span></span>  <br/> ||<span data-ttu-id="7add1-118">设置为 True (1 时) Microsoft Lync Server 2013 将定期清除 QoE 数据库中的过时记录。</span><span class="sxs-lookup"><span data-stu-id="7add1-118">When set to True (1) Microsoft Lync Server 2013 will periodically purge outdated records from the QoE database.</span></span> <span data-ttu-id="7add1-119">将每天在 PurgeHour 设置所指定的时间执行清除。</span><span class="sxs-lookup"><span data-stu-id="7add1-119">Purging will take place each day at the tome specified by the PurgeHour setting.</span></span> <span data-ttu-id="7add1-120">如果设置为 False (0)，则不会从数据库中自动清除记录。</span><span class="sxs-lookup"><span data-stu-id="7add1-120">If set to False (0) then records will not be automatically purged from the database.</span></span> <span data-ttu-id="7add1-121">默认值为 True。</span><span class="sxs-lookup"><span data-stu-id="7add1-121">The default value is True.</span></span>  <br/> |
|<span data-ttu-id="7add1-122">**KeepQoEDataForDays**</span><span class="sxs-lookup"><span data-stu-id="7add1-122">**KeepQoEDataForDays**</span></span> <br/> |<span data-ttu-id="7add1-123">int</span><span class="sxs-lookup"><span data-stu-id="7add1-123">int</span></span>  <br/> ||<span data-ttu-id="7add1-p104">指定将从数据库中清除的 QoE 记录的保留时间（以天为单位）：如果启用了清除，将从数据库中移除高于此值的 QoE 记录。默认值为 60 天。</span><span class="sxs-lookup"><span data-stu-id="7add1-p104">Specifies the age of QoE records (in days) that will be purged from the database: if purging is enabled, QoE records older than this value will be removed from the database. The default value is 60 days.</span></span>  <br/> |
|<span data-ttu-id="7add1-126">**PurgeHour**</span><span class="sxs-lookup"><span data-stu-id="7add1-126">**PurgeHour**</span></span> <br/> |<span data-ttu-id="7add1-127">int</span><span class="sxs-lookup"><span data-stu-id="7add1-127">int</span></span>  <br/> ||<span data-ttu-id="7add1-p105">指定将执行数据库清除的本地时间。将采用 24 小时制指定时间，其中 0 表示午夜 (12:00 AM)，23 表示 11:00 PM。请注意，您只能指定小时：允许值 10（指示 10:00 AM），但不允许值 10:30（即 10.5）（指示 10:30 AM）。默认值为 1 (1:00 AM)。</span><span class="sxs-lookup"><span data-stu-id="7add1-p105">Specifies the local time of day when database purging will take place. The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM. Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed. The default value is 1 (1:00 AM). Specifies the local time of day when database purging will take place. The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM. Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed. The default value is 1 (1:00 AM).</span></span>  <br/> |
   

