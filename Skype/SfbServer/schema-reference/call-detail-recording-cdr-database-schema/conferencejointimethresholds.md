---
title: Skype for Business Server 2015 中的 ConferenceJoinTimeThresholds 表
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
description: ConferenceJoinTimeThresholds 表包含会议加入时间摘要报告使用的分类边界。会议加入时间摘要报告总结了用户成功加入会议所需的时间；这些时间值都报告为一个平均值，且采用以下类别之一：
ms.openlocfilehash: dfa7293307376b5fb5c86cec6f7504d363b005f5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813302"
---
# <a name="conferencejointimethresholds-table-in-skype-for-business-server-2015"></a><span data-ttu-id="26737-104">Skype for Business Server 2015 中的 ConferenceJoinTimeThresholds 表</span><span class="sxs-lookup"><span data-stu-id="26737-104">ConferenceJoinTimeThresholds table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="26737-p102">ConferenceJoinTimeThresholds 表包含会议加入时间摘要报告使用的分类边界。会议加入时间摘要报告总结了用户成功加入会议所需的时间；这些时间值都报告为一个平均值，且采用以下类别之一：</span><span class="sxs-lookup"><span data-stu-id="26737-p102">The ConferenceJoinTimeThresholds table contains the classification boundaries used by the Conference Join Time Summary Report. The Conference Join Time Summary Report summarizes the amount time required for users to successfully join a conference; these time values are reported both as an average and in one of the following categories:</span></span>
  
- <span data-ttu-id="26737-107">少于 2 秒。</span><span class="sxs-lookup"><span data-stu-id="26737-107">Less than 2 seconds.</span></span>
    
- <span data-ttu-id="26737-108">2 秒到 5 秒之间。</span><span class="sxs-lookup"><span data-stu-id="26737-108">Between 2 second and 5 seconds.</span></span>
    
- <span data-ttu-id="26737-109">5 秒到 10 秒之间。</span><span class="sxs-lookup"><span data-stu-id="26737-109">Between 5 seconds and 10 seconds.</span></span>
    
- <span data-ttu-id="26737-110">长于 10 秒。</span><span class="sxs-lookup"><span data-stu-id="26737-110">More than 10 seconds.</span></span>
    
<span data-ttu-id="26737-111">ConferenceJoinTimeThresholds 表包含分类值 2 秒、5 秒和 10 秒。</span><span class="sxs-lookup"><span data-stu-id="26737-111">The ConferenceJoinTimeThresholds table contains the classification values 2 seconds, 5 seconds, and 10 seconds.</span></span>
  
<span data-ttu-id="26737-112">此表在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="26737-112">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="26737-113">**列**</span><span class="sxs-lookup"><span data-stu-id="26737-113">**Column**</span></span>|<span data-ttu-id="26737-114">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="26737-114">**Data Type**</span></span>|<span data-ttu-id="26737-115">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="26737-115">**Key/Index**</span></span>|<span data-ttu-id="26737-116">**Details**</span><span class="sxs-lookup"><span data-stu-id="26737-116">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="26737-117">**ThresholdId**</span><span class="sxs-lookup"><span data-stu-id="26737-117">**ThresholdId**</span></span> <br/> |<span data-ttu-id="26737-118">int</span><span class="sxs-lookup"><span data-stu-id="26737-118">int</span></span>  <br/> |<span data-ttu-id="26737-119">主</span><span class="sxs-lookup"><span data-stu-id="26737-119">Primary</span></span>  <br/> |<span data-ttu-id="26737-120">分类的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="26737-120">Unique identifier for the classification.</span></span>  <br/> |
|<span data-ttu-id="26737-121">**ThresholdValue**</span><span class="sxs-lookup"><span data-stu-id="26737-121">**ThresholdValue**</span></span> <br/> |<span data-ttu-id="26737-122">int</span><span class="sxs-lookup"><span data-stu-id="26737-122">int</span></span>  <br/> || <span data-ttu-id="26737-p103">分类的上限。允许的值包括：</span><span class="sxs-lookup"><span data-stu-id="26737-p103">Upper limit for the classification. Allowed values are:</span></span> <br/>  <span data-ttu-id="26737-125">2 </span><span class="sxs-lookup"><span data-stu-id="26737-125">2</span></span> <br/>  <span data-ttu-id="26737-126">5 </span><span class="sxs-lookup"><span data-stu-id="26737-126">5</span></span> <br/>  <span data-ttu-id="26737-127">10 </span><span class="sxs-lookup"><span data-stu-id="26737-127">10</span></span> <br/> |
   

