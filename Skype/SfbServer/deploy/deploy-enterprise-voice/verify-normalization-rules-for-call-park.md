---
title: 在 Skype for Business 中验证呼叫寄存的规范化规则
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: deaa170f-041e-45cb-8eab-f02931ab541e
description: 了解 Skype for business Server Enterprise Voice 中的呼叫寄存的规范化规则。
ms.openlocfilehash: 38de300970341d563f2a532847a39c2fe98e15e7
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240015"
---
# <a name="verify-normalization-rules-for-call-park-in-skype-for-business"></a><span data-ttu-id="e7261-103">在 Skype for Business 中验证呼叫寄存的规范化规则</span><span class="sxs-lookup"><span data-stu-id="e7261-103">Verify normalization rules for Call Park in Skype for Business</span></span>
 
<span data-ttu-id="e7261-104">了解 Skype for business Server Enterprise Voice 中的呼叫寄存的规范化规则。</span><span class="sxs-lookup"><span data-stu-id="e7261-104">Learn about normalization rules for Call Park in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="e7261-105">调用寄存轨道式不得正常化。</span><span class="sxs-lookup"><span data-stu-id="e7261-105">Call Park orbits must not be normalized.</span></span> <span data-ttu-id="e7261-106">检查拨号计划以确保未对通道号码进行规范化。</span><span class="sxs-lookup"><span data-stu-id="e7261-106">Check your dial plans to be sure that your orbit numbers are not normalized.</span></span> <span data-ttu-id="e7261-107">如果必须创建另一个规范化规则来防止你的轨道式被正常化, 请按照在[Skype For Business 服务器中创建或修改拨号计划中](dial-plans.md)的过程定义新的规范化规则, 以便**匹配模式**标识 "轨道" 区域和**翻译模式**为 **$1**。</span><span class="sxs-lookup"><span data-stu-id="e7261-107">If you must create an additional normalization rule to prevent your orbits from being normalized, follow the procedure in [Create or modify a dial plan in Skype for Business Server](dial-plans.md) to define a new normalization rule, so that **Pattern to match** identifies the orbit range and **Translation pattern** is **$1**.</span></span> <span data-ttu-id="e7261-108">例如, 如果您的呼叫公园的 "轨道" 范围为 7000-7999, 则**要匹配的模式**为 **^{3}(7 \ d) $** 和**转换模式**为 **$1**。</span><span class="sxs-lookup"><span data-stu-id="e7261-108">For example, if your Call Park orbit range is 7000 - 7999, the **Pattern to match** is **^(7\d{3})$** and **Translation pattern** is **$1**.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e7261-109">请确保你的拨号计划中的默认规范化规则不包含 **^ (\d\*)**。</span><span class="sxs-lookup"><span data-stu-id="e7261-109">Be sure that the default normalization rule in your dial plans does not contain **^(\d\*)**.</span></span> <span data-ttu-id="e7261-110">否则, 您的通话寄存规范化规则将永远不会运行。</span><span class="sxs-lookup"><span data-stu-id="e7261-110">Otherwise, your Call Park normalization rule will never run.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e7261-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e7261-111">See also</span></span>

[<span data-ttu-id="e7261-112">在 Skype for Business 服务器中创建或修改拨号计划</span><span class="sxs-lookup"><span data-stu-id="e7261-112">Create or modify a dial plan in Skype for Business Server</span></span>](dial-plans.md)

