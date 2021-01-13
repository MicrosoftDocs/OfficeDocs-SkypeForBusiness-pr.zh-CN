---
title: 验证 Skype for Business 中呼叫等待的规范化规则
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: deaa170f-041e-45cb-8eab-f02931ab541e
description: 了解 Skype for Business Server 企业语音 中的呼叫企业语音。
ms.openlocfilehash: d1bcd6817b1f59f73a8c4ef1562e90253a99bd30
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830572"
---
# <a name="verify-normalization-rules-for-call-park-in-skype-for-business"></a><span data-ttu-id="88d30-103">验证 Skype for Business 中呼叫等待的规范化规则</span><span class="sxs-lookup"><span data-stu-id="88d30-103">Verify normalization rules for Call Park in Skype for Business</span></span>
 
<span data-ttu-id="88d30-104">了解 Skype for Business Server 企业语音 中的呼叫企业语音。</span><span class="sxs-lookup"><span data-stu-id="88d30-104">Learn about normalization rules for Call Park in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="88d30-105">不得对呼叫停叫通道进行规范化。</span><span class="sxs-lookup"><span data-stu-id="88d30-105">Call Park orbits must not be normalized.</span></span> <span data-ttu-id="88d30-106">请检查拨号计划以确保通道号码未规范化。</span><span class="sxs-lookup"><span data-stu-id="88d30-106">Check your dial plans to be sure that your orbit numbers are not normalized.</span></span> <span data-ttu-id="88d30-107">如果必须创建其他规范化规则以防止对通道进行规范化，请按照 Skype [for Business Server](dial-plans.md)中的"创建或修改拨号计划"中的过程定义新的规范化规则，以便匹配的模式标识通道范围，转换模式为 **$1。** </span><span class="sxs-lookup"><span data-stu-id="88d30-107">If you must create an additional normalization rule to prevent your orbits from being normalized, follow the procedure in [Create or modify a dial plan in Skype for Business Server](dial-plans.md) to define a new normalization rule, so that **Pattern to match** identifies the orbit range and **Translation pattern** is **$1**.</span></span> <span data-ttu-id="88d30-108">例如，如果你的呼叫等待通道范围是 7000 - 7999，要 **匹配的** 模式是 **^ (7\d {3}) $** 和转换模式是 **$1。** </span><span class="sxs-lookup"><span data-stu-id="88d30-108">For example, if your Call Park orbit range is 7000 - 7999, the **Pattern to match** is **^(7\d{3})$** and **Translation pattern** is **$1**.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="88d30-109">请确保拨号计划中的默认规范化规则不包含 **^ (\d \*) 。**</span><span class="sxs-lookup"><span data-stu-id="88d30-109">Be sure that the default normalization rule in your dial plans does not contain **^(\d\*)**.</span></span> <span data-ttu-id="88d30-110">否则，您的呼叫停止规范化规则将永远不会运行。</span><span class="sxs-lookup"><span data-stu-id="88d30-110">Otherwise, your Call Park normalization rule will never run.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="88d30-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="88d30-111">See also</span></span>

[<span data-ttu-id="88d30-112">在 Skype for Business Server 中创建或修改拨号计划</span><span class="sxs-lookup"><span data-stu-id="88d30-112">Create or modify a dial plan in Skype for Business Server</span></span>](dial-plans.md)

