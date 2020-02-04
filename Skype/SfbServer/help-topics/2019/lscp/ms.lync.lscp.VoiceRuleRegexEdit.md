---
title: 翻译规则键入正则表达式
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.VoiceRuleRegexEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5ee83724-b399-4f8d-8f6d-4b53a26296b4
ROBOTS: NOINDEX, NOFOLLOW
description: '在 "匹配此模式" 字段中，指定将用于匹配要转换的数字的模式。 在 "翻译规则" 字段中，为已翻译数字的格式指定一个模式。 '
ms.openlocfilehash: 5cbf3c0a7956e4061ad7a67cf1681b15981c9946
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2020
ms.locfileid: "41690132"
---
# <a name="translation-rule-type-a-regular-expression"></a><span data-ttu-id="6ac3d-104">转换规则：键入正则表达式</span><span class="sxs-lookup"><span data-stu-id="6ac3d-104">Translation Rule: Type a Regular Expression</span></span>
 
<span data-ttu-id="6ac3d-105">在 "**匹配此模式**" 字段中，指定将用于匹配要转换的数字的模式。</span><span class="sxs-lookup"><span data-stu-id="6ac3d-105">In the **Match this pattern** field, specify the pattern that will be used to match the numbers to be translated.</span></span> <span data-ttu-id="6ac3d-106">在 "**翻译规则**" 字段中，为已翻译数字的格式指定一个模式。</span><span class="sxs-lookup"><span data-stu-id="6ac3d-106">In the **Translation rule** field, specify a pattern for the format of translated numbers.</span></span> <span data-ttu-id="6ac3d-107">例如，如果在 "**匹配此模式**"{9}字段中输入 "^\+" （\d \D +） $ 和 "**翻译规则**" 字段中的 011 $ 1，则规则会将 + 441235551010 转换为011441235551010。</span><span class="sxs-lookup"><span data-stu-id="6ac3d-107">For example, if you enter ^\+(\d{9}\d+)$ in the **Match this pattern** field and 011$1 in the **Translation rule** field, the rule will translate +441235551010 to 011441235551010.</span></span> 
  
 
  

