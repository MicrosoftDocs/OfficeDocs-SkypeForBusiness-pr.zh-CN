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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
description: ConferenceJoinTimeThresholds 表包含 "会议加入时间摘要" 报表使用的分类边界。 "会议加入时间摘要" 报表汇总了用户成功加入会议所需的时间量;这些时间值以平均值和以下类别之一报告：
ms.openlocfilehash: 1874a94448be5957079b1c53944bc127df761e5e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815390"
---
# <a name="conferencejointimethresholds-table-in-skype-for-business-server-2015"></a><span data-ttu-id="8d783-104">Skype for Business Server 2015 中的 ConferenceJoinTimeThresholds 表</span><span class="sxs-lookup"><span data-stu-id="8d783-104">ConferenceJoinTimeThresholds table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="8d783-105">ConferenceJoinTimeThresholds 表包含 "会议加入时间摘要" 报表使用的分类边界。</span><span class="sxs-lookup"><span data-stu-id="8d783-105">The ConferenceJoinTimeThresholds table contains the classification boundaries used by the Conference Join Time Summary Report.</span></span> <span data-ttu-id="8d783-106">"会议加入时间摘要" 报表汇总了用户成功加入会议所需的时间量;这些时间值以平均值和以下类别之一报告：</span><span class="sxs-lookup"><span data-stu-id="8d783-106">The Conference Join Time Summary Report summarizes the amount time required for users to successfully join a conference; these time values are reported both as an average and in one of the following categories:</span></span>
  
- <span data-ttu-id="8d783-107">不到2秒。</span><span class="sxs-lookup"><span data-stu-id="8d783-107">Less than 2 seconds.</span></span>
    
- <span data-ttu-id="8d783-108">介于2秒和5秒之间。</span><span class="sxs-lookup"><span data-stu-id="8d783-108">Between 2 second and 5 seconds.</span></span>
    
- <span data-ttu-id="8d783-109">介于5秒和10秒之间。</span><span class="sxs-lookup"><span data-stu-id="8d783-109">Between 5 seconds and 10 seconds.</span></span>
    
- <span data-ttu-id="8d783-110">10秒以上。</span><span class="sxs-lookup"><span data-stu-id="8d783-110">More than 10 seconds.</span></span>
    
<span data-ttu-id="8d783-111">ConferenceJoinTimeThresholds 表包含分类值2秒、5秒和10秒钟。</span><span class="sxs-lookup"><span data-stu-id="8d783-111">The ConferenceJoinTimeThresholds table contains the classification values 2 seconds, 5 seconds, and 10 seconds.</span></span>
  
<span data-ttu-id="8d783-112">此表是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="8d783-112">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="8d783-113">**列**</span><span class="sxs-lookup"><span data-stu-id="8d783-113">**Column**</span></span>|<span data-ttu-id="8d783-114">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="8d783-114">**Data Type**</span></span>|<span data-ttu-id="8d783-115">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="8d783-115">**Key/Index**</span></span>|<span data-ttu-id="8d783-116">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="8d783-116">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8d783-117">**ThresholdId**</span><span class="sxs-lookup"><span data-stu-id="8d783-117">**ThresholdId**</span></span> <br/> |<span data-ttu-id="8d783-118">int</span><span class="sxs-lookup"><span data-stu-id="8d783-118">int</span></span>  <br/> |<span data-ttu-id="8d783-119">Primary</span><span class="sxs-lookup"><span data-stu-id="8d783-119">Primary</span></span>  <br/> |<span data-ttu-id="8d783-120">分类的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="8d783-120">Unique identifier for the classification.</span></span>  <br/> |
|<span data-ttu-id="8d783-121">**ThresholdValue**</span><span class="sxs-lookup"><span data-stu-id="8d783-121">**ThresholdValue**</span></span> <br/> |<span data-ttu-id="8d783-122">int</span><span class="sxs-lookup"><span data-stu-id="8d783-122">int</span></span>  <br/> || <span data-ttu-id="8d783-123">分类的上限。</span><span class="sxs-lookup"><span data-stu-id="8d783-123">Upper limit for the classification.</span></span> <span data-ttu-id="8d783-124">允许的值包括：</span><span class="sxs-lookup"><span data-stu-id="8d783-124">Allowed values are:</span></span> <br/>  <span data-ttu-id="8d783-125">ppls-2</span><span class="sxs-lookup"><span data-stu-id="8d783-125">2</span></span> <br/>  <span data-ttu-id="8d783-126">5</span><span class="sxs-lookup"><span data-stu-id="8d783-126">5</span></span> <br/>  <span data-ttu-id="8d783-127">10</span><span class="sxs-lookup"><span data-stu-id="8d783-127">10</span></span> <br/> |
   

