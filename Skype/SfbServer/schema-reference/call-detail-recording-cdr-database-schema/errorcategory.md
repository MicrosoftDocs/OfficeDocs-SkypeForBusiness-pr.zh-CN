---
title: 在业务服务器 2015年的 Skype 的 ErrorCategory 表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
description: ErrorCategory 表中包含每个 Skype 业务服务器 2015年诊断分类的友好名称。 默认情况下，业务服务器 2015年的 Skype 使用下列类别：
ms.openlocfilehash: 23df7ecb7e10dc104e6274edb762369ad539f8fe
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="errorcategory-table-in-skype-for-business-server-2015"></a><span data-ttu-id="cc854-104">在业务服务器 2015年的 Skype 的 ErrorCategory 表</span><span class="sxs-lookup"><span data-stu-id="cc854-104">ErrorCategory table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="cc854-105">ErrorCategory 表中包含每个 Skype 业务服务器 2015年诊断分类的友好名称。</span><span class="sxs-lookup"><span data-stu-id="cc854-105">The ErrorCategory table contains the friendly name for each Skype for Business Server 2015 diagnostic classification.</span></span> <span data-ttu-id="cc854-106">默认情况下，业务服务器 2015年的 Skype 使用下列类别：</span><span class="sxs-lookup"><span data-stu-id="cc854-106">By default, Skype for Business Server 2015 uses the following classifications:</span></span>
  
- <span data-ttu-id="cc854-107">0--成功</span><span class="sxs-lookup"><span data-stu-id="cc854-107">0 -- Success</span></span>
    
- <span data-ttu-id="cc854-108">1-预期故障</span><span class="sxs-lookup"><span data-stu-id="cc854-108">1 -- Expected failure</span></span>
    
- <span data-ttu-id="cc854-109">2-意外失败</span><span class="sxs-lookup"><span data-stu-id="cc854-109">2 - Unexpected failure</span></span>
    
<span data-ttu-id="cc854-110">在 Microsoft Lync Server 2013 引入了此表。</span><span class="sxs-lookup"><span data-stu-id="cc854-110">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="cc854-111">**列**</span><span class="sxs-lookup"><span data-stu-id="cc854-111">**Column**</span></span>|<span data-ttu-id="cc854-112">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="cc854-112">**Data Type**</span></span>|<span data-ttu-id="cc854-113">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="cc854-113">**Key/Index**</span></span>|<span data-ttu-id="cc854-114">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="cc854-114">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="cc854-115">**类别 id**</span><span class="sxs-lookup"><span data-stu-id="cc854-115">**CategoryId**</span></span> <br/> |<span data-ttu-id="cc854-116">tinyint</span><span class="sxs-lookup"><span data-stu-id="cc854-116">tinyint</span></span>  <br/> |<span data-ttu-id="cc854-117">Primary</span><span class="sxs-lookup"><span data-stu-id="cc854-117">Primary</span></span>  <br/> |<span data-ttu-id="cc854-118">分类的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="cc854-118">Unique identifier for the classification.</span></span>  <br/> |
|<span data-ttu-id="cc854-119">**名称** - 按 WAN 链路进行筛选（筛选器位于图形右侧）。</span><span class="sxs-lookup"><span data-stu-id="cc854-119">**Name**</span></span> <br/> |<span data-ttu-id="cc854-120">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="cc854-120">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="cc854-121">价值和分配给分类的友好名称。</span><span class="sxs-lookup"><span data-stu-id="cc854-121">Value and friendly name assigned to the classification.</span></span> <span data-ttu-id="cc854-122">允许的值包括：</span><span class="sxs-lookup"><span data-stu-id="cc854-122">Allowed values are:</span></span> <br/>  <span data-ttu-id="cc854-123">0--成功</span><span class="sxs-lookup"><span data-stu-id="cc854-123">0 -- Success</span></span> <br/>  <span data-ttu-id="cc854-124">1-预期故障</span><span class="sxs-lookup"><span data-stu-id="cc854-124">1 -- Expected failure</span></span> <br/>  <span data-ttu-id="cc854-125">2-意外失败</span><span class="sxs-lookup"><span data-stu-id="cc854-125">2 - Unexpected failure</span></span> <br/> |
   

