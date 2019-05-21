---
title: Skype for Business Server 2015 中的 ConferenceJoinTimeThresholds 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
description: 'ConferenceJoinTimeThresholds 表包含 "会议加入时间摘要" 报表使用的分类边界。 "会议加入时间摘要" 报表汇总了用户成功加入会议所需的时间量;这些时间值以平均值和以下类别之一报告:'
ms.openlocfilehash: 4b2f27b6ab826ff95c1478cf54e8a21c148b1d3c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296495"
---
# <a name="conferencejointimethresholds-table-in-skype-for-business-server-2015"></a><span data-ttu-id="2eb3d-104">Skype for Business Server 2015 中的 ConferenceJoinTimeThresholds 表</span><span class="sxs-lookup"><span data-stu-id="2eb3d-104">ConferenceJoinTimeThresholds table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="2eb3d-105">ConferenceJoinTimeThresholds 表包含 "会议加入时间摘要" 报表使用的分类边界。</span><span class="sxs-lookup"><span data-stu-id="2eb3d-105">The ConferenceJoinTimeThresholds table contains the classification boundaries used by the Conference Join Time Summary Report.</span></span> <span data-ttu-id="2eb3d-106">"会议加入时间摘要" 报表汇总了用户成功加入会议所需的时间量;这些时间值以平均值和以下类别之一报告:</span><span class="sxs-lookup"><span data-stu-id="2eb3d-106">The Conference Join Time Summary Report summarizes the amount time required for users to successfully join a conference; these time values are reported both as an average and in one of the following categories:</span></span>
  
- <span data-ttu-id="2eb3d-107">不到2秒。</span><span class="sxs-lookup"><span data-stu-id="2eb3d-107">Less than 2 seconds.</span></span>
    
- <span data-ttu-id="2eb3d-108">介于2秒和5秒之间。</span><span class="sxs-lookup"><span data-stu-id="2eb3d-108">Between 2 second and 5 seconds.</span></span>
    
- <span data-ttu-id="2eb3d-109">介于5秒和10秒之间。</span><span class="sxs-lookup"><span data-stu-id="2eb3d-109">Between 5 seconds and 10 seconds.</span></span>
    
- <span data-ttu-id="2eb3d-110">10秒以上。</span><span class="sxs-lookup"><span data-stu-id="2eb3d-110">More than 10 seconds.</span></span>
    
<span data-ttu-id="2eb3d-111">ConferenceJoinTimeThresholds 表包含分类值2秒、5秒和10秒钟。</span><span class="sxs-lookup"><span data-stu-id="2eb3d-111">The ConferenceJoinTimeThresholds table contains the classification values 2 seconds, 5 seconds, and 10 seconds.</span></span>
  
<span data-ttu-id="2eb3d-112">此表是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="2eb3d-112">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="2eb3d-113">**列**</span><span class="sxs-lookup"><span data-stu-id="2eb3d-113">**Column**</span></span>|<span data-ttu-id="2eb3d-114">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="2eb3d-114">**Data Type**</span></span>|<span data-ttu-id="2eb3d-115">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="2eb3d-115">**Key/Index**</span></span>|<span data-ttu-id="2eb3d-116">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="2eb3d-116">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2eb3d-117">**ThresholdId**</span><span class="sxs-lookup"><span data-stu-id="2eb3d-117">**ThresholdId**</span></span> <br/> |<span data-ttu-id="2eb3d-118">int</span><span class="sxs-lookup"><span data-stu-id="2eb3d-118">int</span></span>  <br/> |<span data-ttu-id="2eb3d-119">Primary</span><span class="sxs-lookup"><span data-stu-id="2eb3d-119">Primary</span></span>  <br/> |<span data-ttu-id="2eb3d-120">分类的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="2eb3d-120">Unique identifier for the classification.</span></span>  <br/> |
|<span data-ttu-id="2eb3d-121">**ThresholdValue**</span><span class="sxs-lookup"><span data-stu-id="2eb3d-121">**ThresholdValue**</span></span> <br/> |<span data-ttu-id="2eb3d-122">int</span><span class="sxs-lookup"><span data-stu-id="2eb3d-122">int</span></span>  <br/> || <span data-ttu-id="2eb3d-123">分类的上限。</span><span class="sxs-lookup"><span data-stu-id="2eb3d-123">Upper limit for the classification.</span></span> <span data-ttu-id="2eb3d-124">允许的值包括：</span><span class="sxs-lookup"><span data-stu-id="2eb3d-124">Allowed values are:</span></span> <br/>  <span data-ttu-id="2eb3d-125">2</span><span class="sxs-lookup"><span data-stu-id="2eb3d-125">2</span></span> <br/>  <span data-ttu-id="2eb3d-126">5</span><span class="sxs-lookup"><span data-stu-id="2eb3d-126">5</span></span> <br/>  <span data-ttu-id="2eb3d-127">10</span><span class="sxs-lookup"><span data-stu-id="2eb3d-127">10</span></span> <br/> |
   

