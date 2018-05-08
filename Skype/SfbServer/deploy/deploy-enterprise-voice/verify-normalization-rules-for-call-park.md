---
title: 在 Skype for Business 2015 中验证呼叫寄存的规范化规则
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: deaa170f-041e-45cb-8eab-f02931ab541e
description: 了解有关在 Skype 的呼叫寄存的规范化规则的业务 Server 企业语音。
ms.openlocfilehash: c637240d4c193bbec05228d167d77f7bd18c0d04
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="verify-normalization-rules-for-call-park-in-skype-for-business-2015"></a><span data-ttu-id="c976a-103">在 Skype for Business 2015 中验证呼叫寄存的规范化规则</span><span class="sxs-lookup"><span data-stu-id="c976a-103">Verify normalization rules for Call Park in Skype for Business 2015</span></span>
 
<span data-ttu-id="c976a-104">了解有关在 Skype 的呼叫寄存的规范化规则的业务 Server 企业语音。</span><span class="sxs-lookup"><span data-stu-id="c976a-104">Learn about normalization rules for Call Park in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="c976a-105">呼叫寄存轨道必须未标准化。</span><span class="sxs-lookup"><span data-stu-id="c976a-105">Call Park orbits must not be normalized.</span></span> <span data-ttu-id="c976a-106">检查拨号计划以确保未对通道号码进行规范化。</span><span class="sxs-lookup"><span data-stu-id="c976a-106">Check your dial plans to be sure that your orbit numbers are not normalized.</span></span> <span data-ttu-id="c976a-107">如果您必须创建要进行规范化阻止您轨道其他规范化规则，请按照中的过程[创建或修改拨号计划中 Skype 业务服务器 2015年](dial-plans.md)因此定义新的规范化规则，该**模式与之匹配**标识的通道范围和**转换模式**是 **$1**。</span><span class="sxs-lookup"><span data-stu-id="c976a-107">If you must create an additional normalization rule to prevent your orbits from being normalized, follow the procedure in [Create or modify a dial plan in Skype for Business Server 2015](dial-plans.md) to define a new normalization rule, so that **Pattern to match** identifies the orbit range and **Translation pattern** is **$1**.</span></span> <span data-ttu-id="c976a-108">例如，如果您呼叫寄存通道范围为 7000 7999**模式与之匹配**将 **^(7\d{3})$** **转换模式**， **$1**。</span><span class="sxs-lookup"><span data-stu-id="c976a-108">For example, if your Call Park orbit range is 7000 - 7999, the **Pattern to match** is **^(7\d{3})$** and **Translation pattern** is **$1**.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="c976a-109">确保拨号计划中的默认规范化规则不包含 **^(\d\*)**。</span><span class="sxs-lookup"><span data-stu-id="c976a-109">Be sure that the default normalization rule in your dial plans does not contain **^(\d\*)**.</span></span> <span data-ttu-id="c976a-110">否则，您呼叫寄存的规范化规则不会运行。</span><span class="sxs-lookup"><span data-stu-id="c976a-110">Otherwise, your Call Park normalization rule will never run.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c976a-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c976a-111">See also</span></span>

#### 

[<span data-ttu-id="c976a-112">创建或修改拨号计划中 Skype 业务服务器 2015</span><span class="sxs-lookup"><span data-stu-id="c976a-112">Create or modify a dial plan in Skype for Business Server 2015</span></span>](dial-plans.md)

