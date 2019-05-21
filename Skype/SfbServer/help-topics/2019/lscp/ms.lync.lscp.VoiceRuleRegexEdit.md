---
title: 翻译规则键入正则表达式
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceRuleRegexEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5ee83724-b399-4f8d-8f6d-4b53a26296b4
ROBOTS: NOINDEX, NOFOLLOW
description: '在 "匹配此模式" 字段中, 指定将用于匹配要转换的数字的模式。 在 "翻译规则" 字段中, 为已翻译数字的格式指定一个模式。 '
ms.openlocfilehash: c6985b8598e85dd9a295a81c2e0476d0e5925ef5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34293548"
---
# <a name="translation-rule-type-a-regular-expression"></a><span data-ttu-id="bcbf4-104">转换规则：键入正则表达式</span><span class="sxs-lookup"><span data-stu-id="bcbf4-104">Translation Rule: Type a Regular Expression</span></span>
 
<span data-ttu-id="bcbf4-105">在 "**匹配此模式**" 字段中, 指定将用于匹配要转换的数字的模式。</span><span class="sxs-lookup"><span data-stu-id="bcbf4-105">In the **Match this pattern** field, specify the pattern that will be used to match the numbers to be translated.</span></span> <span data-ttu-id="bcbf4-106">在 "**翻译规则**" 字段中, 为已翻译数字的格式指定一个模式。</span><span class="sxs-lookup"><span data-stu-id="bcbf4-106">In the **Translation rule** field, specify a pattern for the format of translated numbers.</span></span> <span data-ttu-id="bcbf4-107">例如, 如果在 "**匹配此模式**"{9}字段中输入 "^\+" (\d \D +) $ 和 "**翻译规则**" 字段中的 011 $ 1, 则规则会将 + 441235551010 转换为011441235551010。</span><span class="sxs-lookup"><span data-stu-id="bcbf4-107">For example, if you enter ^\+(\d{9}\d+)$ in the **Match this pattern** field and 011$1 in the **Translation rule** field, the rule will translate +441235551010 to 011441235551010.</span></span> 
  
 
  

