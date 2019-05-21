---
title: Skype for Business Server 2015 中的 ErrorCategory 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
description: 'ErrorCategory 表包含每个 Skype for Business Server 2015 诊断分类的友好名称。 默认情况下, Skype for business Server 2015 使用以下分类:'
ms.openlocfilehash: bafeb75ee9e6ae0f96b08e26909828f1b36f7e7b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296285"
---
# <a name="errorcategory-table-in-skype-for-business-server-2015"></a><span data-ttu-id="004e6-104">Skype for Business Server 2015 中的 ErrorCategory 表</span><span class="sxs-lookup"><span data-stu-id="004e6-104">ErrorCategory table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="004e6-105">ErrorCategory 表包含每个 Skype for Business Server 2015 诊断分类的友好名称。</span><span class="sxs-lookup"><span data-stu-id="004e6-105">The ErrorCategory table contains the friendly name for each Skype for Business Server 2015 diagnostic classification.</span></span> <span data-ttu-id="004e6-106">默认情况下, Skype for business Server 2015 使用以下分类:</span><span class="sxs-lookup"><span data-stu-id="004e6-106">By default, Skype for Business Server 2015 uses the following classifications:</span></span>
  
- <span data-ttu-id="004e6-107">0--成功</span><span class="sxs-lookup"><span data-stu-id="004e6-107">0 -- Success</span></span>
    
- <span data-ttu-id="004e6-108">1--预期故障</span><span class="sxs-lookup"><span data-stu-id="004e6-108">1 -- Expected failure</span></span>
    
- <span data-ttu-id="004e6-109">2-意外故障</span><span class="sxs-lookup"><span data-stu-id="004e6-109">2 - Unexpected failure</span></span>
    
<span data-ttu-id="004e6-110">此表是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="004e6-110">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="004e6-111">**列**</span><span class="sxs-lookup"><span data-stu-id="004e6-111">**Column**</span></span>|<span data-ttu-id="004e6-112">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="004e6-112">**Data Type**</span></span>|<span data-ttu-id="004e6-113">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="004e6-113">**Key/Index**</span></span>|<span data-ttu-id="004e6-114">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="004e6-114">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="004e6-115">**CategoryId**</span><span class="sxs-lookup"><span data-stu-id="004e6-115">**CategoryId**</span></span> <br/> |<span data-ttu-id="004e6-116">tinyint</span><span class="sxs-lookup"><span data-stu-id="004e6-116">tinyint</span></span>  <br/> |<span data-ttu-id="004e6-117">Primary</span><span class="sxs-lookup"><span data-stu-id="004e6-117">Primary</span></span>  <br/> |<span data-ttu-id="004e6-118">分类的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="004e6-118">Unique identifier for the classification.</span></span>  <br/> |
|<span data-ttu-id="004e6-119">**名称** - 按 WAN 链路进行筛选（筛选器位于图形右侧）。</span><span class="sxs-lookup"><span data-stu-id="004e6-119">**Name**</span></span> <br/> |<span data-ttu-id="004e6-120">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="004e6-120">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="004e6-121">分配给分类的值和友好名称。</span><span class="sxs-lookup"><span data-stu-id="004e6-121">Value and friendly name assigned to the classification.</span></span> <span data-ttu-id="004e6-122">允许的值包括：</span><span class="sxs-lookup"><span data-stu-id="004e6-122">Allowed values are:</span></span> <br/>  <span data-ttu-id="004e6-123">0--成功</span><span class="sxs-lookup"><span data-stu-id="004e6-123">0 -- Success</span></span> <br/>  <span data-ttu-id="004e6-124">1--预期故障</span><span class="sxs-lookup"><span data-stu-id="004e6-124">1 -- Expected failure</span></span> <br/>  <span data-ttu-id="004e6-125">2-意外故障</span><span class="sxs-lookup"><span data-stu-id="004e6-125">2 - Unexpected failure</span></span> <br/> |
   

