---
title: 翻译规则键入正则表达式
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.VoiceRuleRegexEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5ee83724-b399-4f8d-8f6d-4b53a26296b4
description: 在 "匹配此模式" 字段中，指定将用于匹配要转换的数字的模式。 在 "翻译规则" 字段中，为已翻译数字的格式指定一个模式。 例如，如果在 "匹配此\+模式"{9}字段中输入 "^" （\d \d +） $ 和 "翻译规则" 字段中的 011 $ 1，则规则会将 + 441235551010 转换为011441235551010。
ms.openlocfilehash: b2797d8c37e666d86eb3b25cdcd43f069eb25498
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41821934"
---
# <a name="translation-rule-type-a-regular-expression"></a><span data-ttu-id="a090f-105">转换规则：键入正则表达式</span><span class="sxs-lookup"><span data-stu-id="a090f-105">Translation Rule: Type a Regular Expression</span></span>
 
<span data-ttu-id="a090f-106">在 "**匹配此模式**" 字段中，指定将用于匹配要转换的数字的模式。</span><span class="sxs-lookup"><span data-stu-id="a090f-106">In the **Match this pattern** field, specify the pattern that will be used to match the numbers to be translated.</span></span> <span data-ttu-id="a090f-107">在 "**翻译规则**" 字段中，为已翻译数字的格式指定一个模式。</span><span class="sxs-lookup"><span data-stu-id="a090f-107">In the **Translation rule** field, specify a pattern for the format of translated numbers.</span></span> <span data-ttu-id="a090f-108">例如，如果在 "**匹配此模式**"{9}字段中输入 "^\+" （\d \D +） $ 和 "**翻译规则**" 字段中的 011 $ 1，则规则会将 + 441235551010 转换为011441235551010。</span><span class="sxs-lookup"><span data-stu-id="a090f-108">For example, if you enter ^\+(\d{9}\d+)$ in the **Match this pattern** field and 011$1 in the **Translation rule** field, the rule will translate +441235551010 to 011441235551010.</span></span>
  
<span data-ttu-id="a090f-109">有关可通过使用 Skype for Business 服务器控制面板执行的不同过程的详细信息，请参阅[管理 skype for Business server 2015](../../manage/manage.md)。</span><span class="sxs-lookup"><span data-stu-id="a090f-109">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>
  

