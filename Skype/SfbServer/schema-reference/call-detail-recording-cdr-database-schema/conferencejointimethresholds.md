---
title: 在业务服务器 2015年的 Skype 的 ConferenceJoinTimeThresholds 表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
description: ConferenceJoinTimeThresholds 表中包含分类边界使用会议加入时间摘要报告。 会议加入时间摘要报告总结了用户成功加入会议; 所需的时间量两个时间值报告平均，而且在以下几个类别之一：
ms.openlocfilehash: 3646337c9e9f20ac0b1dabfdd5504ce83dfa5c40
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="conferencejointimethresholds-table-in-skype-for-business-server-2015"></a><span data-ttu-id="4445d-104">在业务服务器 2015年的 Skype 的 ConferenceJoinTimeThresholds 表</span><span class="sxs-lookup"><span data-stu-id="4445d-104">ConferenceJoinTimeThresholds table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="4445d-105">ConferenceJoinTimeThresholds 表中包含分类边界使用会议加入时间摘要报告。</span><span class="sxs-lookup"><span data-stu-id="4445d-105">The ConferenceJoinTimeThresholds table contains the classification boundaries used by the Conference Join Time Summary Report.</span></span> <span data-ttu-id="4445d-106">会议加入时间摘要报告总结了用户成功加入会议; 所需的时间量两个时间值报告平均，而且在以下几个类别之一：</span><span class="sxs-lookup"><span data-stu-id="4445d-106">The Conference Join Time Summary Report summarizes the amount time required for users to successfully join a conference; these time values are reported both as an average and in one of the following categories:</span></span>
  
- <span data-ttu-id="4445d-107">2 秒之内。</span><span class="sxs-lookup"><span data-stu-id="4445d-107">Less than 2 seconds.</span></span>
    
- <span data-ttu-id="4445d-108">介于 2 秒到 5 秒。</span><span class="sxs-lookup"><span data-stu-id="4445d-108">Between 2 second and 5 seconds.</span></span>
    
- <span data-ttu-id="4445d-109">之间 5 秒到 10 秒。</span><span class="sxs-lookup"><span data-stu-id="4445d-109">Between 5 seconds and 10 seconds.</span></span>
    
- <span data-ttu-id="4445d-110">10 秒钟以上。</span><span class="sxs-lookup"><span data-stu-id="4445d-110">More than 10 seconds.</span></span>
    
<span data-ttu-id="4445d-111">ConferenceJoinTimeThresholds 表包含分类值 2 秒、 5 秒到 10 秒。</span><span class="sxs-lookup"><span data-stu-id="4445d-111">The ConferenceJoinTimeThresholds table contains the classification values 2 seconds, 5 seconds, and 10 seconds.</span></span>
  
<span data-ttu-id="4445d-112">在 Microsoft Lync Server 2013 引入了此表。</span><span class="sxs-lookup"><span data-stu-id="4445d-112">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="4445d-113">**列**</span><span class="sxs-lookup"><span data-stu-id="4445d-113">**Column**</span></span>|<span data-ttu-id="4445d-114">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="4445d-114">**Data Type**</span></span>|<span data-ttu-id="4445d-115">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="4445d-115">**Key/Index**</span></span>|<span data-ttu-id="4445d-116">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="4445d-116">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4445d-117">**ThresholdId**</span><span class="sxs-lookup"><span data-stu-id="4445d-117">**ThresholdId**</span></span> <br/> |<span data-ttu-id="4445d-118">int</span><span class="sxs-lookup"><span data-stu-id="4445d-118">int</span></span>  <br/> |<span data-ttu-id="4445d-119">Primary</span><span class="sxs-lookup"><span data-stu-id="4445d-119">Primary</span></span>  <br/> |<span data-ttu-id="4445d-120">分类的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="4445d-120">Unique identifier for the classification.</span></span>  <br/> |
|<span data-ttu-id="4445d-121">**ThresholdValue**</span><span class="sxs-lookup"><span data-stu-id="4445d-121">**ThresholdValue**</span></span> <br/> |<span data-ttu-id="4445d-122">int</span><span class="sxs-lookup"><span data-stu-id="4445d-122">int</span></span>  <br/> || <span data-ttu-id="4445d-123">分类的上限。</span><span class="sxs-lookup"><span data-stu-id="4445d-123">Upper limit for the classification.</span></span> <span data-ttu-id="4445d-124">允许的值包括：</span><span class="sxs-lookup"><span data-stu-id="4445d-124">Allowed values are:</span></span> <br/>  <span data-ttu-id="4445d-125">2</span><span class="sxs-lookup"><span data-stu-id="4445d-125">2</span></span> <br/>  <span data-ttu-id="4445d-126">5</span><span class="sxs-lookup"><span data-stu-id="4445d-126">5</span></span> <br/>  <span data-ttu-id="4445d-127">10</span><span class="sxs-lookup"><span data-stu-id="4445d-127">10</span></span> <br/> |
   

