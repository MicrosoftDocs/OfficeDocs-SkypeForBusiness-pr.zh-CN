---
title: 在 Skype for Business 2015 中验证呼叫寄存的规范化规则
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: deaa170f-041e-45cb-8eab-f02931ab541e
description: 对于业务服务器企业语音了解在 Skype 呼叫公园的规范化规则。
ms.openlocfilehash: 4f3651394bbdb5556a83aa34739a86f8d06f1396
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="verify-normalization-rules-for-call-park-in-skype-for-business-2015"></a><span data-ttu-id="62559-103">在 Skype for Business 2015 中验证呼叫寄存的规范化规则</span><span class="sxs-lookup"><span data-stu-id="62559-103">Verify normalization rules for Call Park in Skype for Business 2015</span></span>
 
<span data-ttu-id="62559-104">对于业务服务器企业语音了解在 Skype 呼叫公园的规范化规则。</span><span class="sxs-lookup"><span data-stu-id="62559-104">Learn about normalization rules for Call Park in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="62559-105">调用公园轨道式必须正常化。</span><span class="sxs-lookup"><span data-stu-id="62559-105">Call Park orbits must not be normalized.</span></span> <span data-ttu-id="62559-106">检查拨号计划以确保未对通道号码进行规范化。</span><span class="sxs-lookup"><span data-stu-id="62559-106">Check your dial plans to be sure that your orbit numbers are not normalized.</span></span> <span data-ttu-id="62559-107">如果您必须创建其他规范化规则可以防止您轨道式正在规范化，按照中的步骤[创建或修改的业务服务器 2015年的 Skype 的拨号计划](dial-plans.md)来定义新的规范化规则，因此该**模式以匹配**标识运行轨道范围和**翻译模式**是**1 美元**。</span><span class="sxs-lookup"><span data-stu-id="62559-107">If you must create an additional normalization rule to prevent your orbits from being normalized, follow the procedure in [Create or modify a dial plan in Skype for Business Server 2015](dial-plans.md) to define a new normalization rule, so that **Pattern to match** identifies the orbit range and **Translation pattern** is **$1**.</span></span> <span data-ttu-id="62559-108">例如，如果您调用公园轨道范围 7000-7999**要匹配的模式**是**^ (7\d {3}) $**和**翻译模式**是**1 美元**。</span><span class="sxs-lookup"><span data-stu-id="62559-108">For example, if your Call Park orbit range is 7000 - 7999, the **Pattern to match** is **^(7\d{3})$** and **Translation pattern** is **$1**.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="62559-109">请确保您拨号计划中的默认规范化规则不包含**^(\d\*)**。</span><span class="sxs-lookup"><span data-stu-id="62559-109">Be sure that the default normalization rule in your dial plans does not contain **^(\d\*)**.</span></span> <span data-ttu-id="62559-110">否则，您调用公园的规范化规则将永远不会运行。</span><span class="sxs-lookup"><span data-stu-id="62559-110">Otherwise, your Call Park normalization rule will never run.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="62559-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="62559-111">See also</span></span>

#### 

[<span data-ttu-id="62559-112">创建或修改业务服务器 2015 Skype 的拨号计划</span><span class="sxs-lookup"><span data-stu-id="62559-112">Create or modify a dial plan in Skype for Business Server 2015</span></span>](dial-plans.md)

