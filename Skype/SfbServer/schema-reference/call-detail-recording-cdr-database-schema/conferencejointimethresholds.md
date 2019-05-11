---
title: ConferenceJoinTimeThresholds 表中的业务服务器 2015 Skype
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
description: ConferenceJoinTimeThresholds 表包含会议加入时间摘要报表所使用的分类边界。 会议加入时间摘要报告总结了所需的用户，以便成功加入会议; 的时间量这些时间值报告作为平均和以下类别之一：
ms.openlocfilehash: 75df75e16d2a4ed34f667c94f2b2f0960f56e7ff
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901434"
---
# <a name="conferencejointimethresholds-table-in-skype-for-business-server-2015"></a><span data-ttu-id="a10b4-104">ConferenceJoinTimeThresholds 表中的业务服务器 2015 Skype</span><span class="sxs-lookup"><span data-stu-id="a10b4-104">ConferenceJoinTimeThresholds table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="a10b4-105">ConferenceJoinTimeThresholds 表包含会议加入时间摘要报表所使用的分类边界。</span><span class="sxs-lookup"><span data-stu-id="a10b4-105">The ConferenceJoinTimeThresholds table contains the classification boundaries used by the Conference Join Time Summary Report.</span></span> <span data-ttu-id="a10b4-106">会议加入时间摘要报告总结了所需的用户，以便成功加入会议; 的时间量这些时间值报告作为平均和以下类别之一：</span><span class="sxs-lookup"><span data-stu-id="a10b4-106">The Conference Join Time Summary Report summarizes the amount time required for users to successfully join a conference; these time values are reported both as an average and in one of the following categories:</span></span>
  
- <span data-ttu-id="a10b4-107">少于 2 秒。</span><span class="sxs-lookup"><span data-stu-id="a10b4-107">Less than 2 seconds.</span></span>
    
- <span data-ttu-id="a10b4-108">之间 2 秒到 5 秒。</span><span class="sxs-lookup"><span data-stu-id="a10b4-108">Between 2 second and 5 seconds.</span></span>
    
- <span data-ttu-id="a10b4-109">之间 5 秒到 10 秒。</span><span class="sxs-lookup"><span data-stu-id="a10b4-109">Between 5 seconds and 10 seconds.</span></span>
    
- <span data-ttu-id="a10b4-110">10 秒之上。</span><span class="sxs-lookup"><span data-stu-id="a10b4-110">More than 10 seconds.</span></span>
    
<span data-ttu-id="a10b4-111">ConferenceJoinTimeThresholds 表包含分类值 2 秒、 5 秒到 10 秒。</span><span class="sxs-lookup"><span data-stu-id="a10b4-111">The ConferenceJoinTimeThresholds table contains the classification values 2 seconds, 5 seconds, and 10 seconds.</span></span>
  
<span data-ttu-id="a10b4-112">此表是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="a10b4-112">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="a10b4-113">**列**</span><span class="sxs-lookup"><span data-stu-id="a10b4-113">**Column**</span></span>|<span data-ttu-id="a10b4-114">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="a10b4-114">**Data Type**</span></span>|<span data-ttu-id="a10b4-115">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="a10b4-115">**Key/Index**</span></span>|<span data-ttu-id="a10b4-116">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="a10b4-116">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a10b4-117">**ThresholdId**</span><span class="sxs-lookup"><span data-stu-id="a10b4-117">**ThresholdId**</span></span> <br/> |<span data-ttu-id="a10b4-118">int</span><span class="sxs-lookup"><span data-stu-id="a10b4-118">int</span></span>  <br/> |<span data-ttu-id="a10b4-119">Primary</span><span class="sxs-lookup"><span data-stu-id="a10b4-119">Primary</span></span>  <br/> |<span data-ttu-id="a10b4-120">分类的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="a10b4-120">Unique identifier for the classification.</span></span>  <br/> |
|<span data-ttu-id="a10b4-121">**ThresholdValue**</span><span class="sxs-lookup"><span data-stu-id="a10b4-121">**ThresholdValue**</span></span> <br/> |<span data-ttu-id="a10b4-122">int</span><span class="sxs-lookup"><span data-stu-id="a10b4-122">int</span></span>  <br/> || <span data-ttu-id="a10b4-123">分类的上限。</span><span class="sxs-lookup"><span data-stu-id="a10b4-123">Upper limit for the classification.</span></span> <span data-ttu-id="a10b4-124">允许的值包括：</span><span class="sxs-lookup"><span data-stu-id="a10b4-124">Allowed values are:</span></span> <br/>  <span data-ttu-id="a10b4-125">2</span><span class="sxs-lookup"><span data-stu-id="a10b4-125">2</span></span> <br/>  <span data-ttu-id="a10b4-126">5</span><span class="sxs-lookup"><span data-stu-id="a10b4-126">5</span></span> <br/>  <span data-ttu-id="a10b4-127">10</span><span class="sxs-lookup"><span data-stu-id="a10b4-127">10</span></span> <br/> |
   

