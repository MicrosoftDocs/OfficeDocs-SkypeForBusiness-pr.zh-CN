---
title: 转换规则键入正则表达式
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 在“匹配此模式”字段中，指定将用于匹配要转换的号码的模式。 在“转换规则”字段中，指定转换号码格式的模式。 例如，如果在"匹配此模式"字段中输入 ^ (\d \d+) $ ，在"转换规则"字段中输入 \+ {9} 011$1，则规则将 +441235551010 转换为 011441235551010。
ms.openlocfilehash: badbc5a34325e6bc2b5bef7e67ae39a4c8f02dc7
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49818852"
---
# <a name="translation-rule-type-a-regular-expression"></a><span data-ttu-id="46f2a-105">转换规则：键入正则表达式</span><span class="sxs-lookup"><span data-stu-id="46f2a-105">Translation Rule: Type a Regular Expression</span></span>
 
<span data-ttu-id="46f2a-106">在“匹配此模式”字段中，指定将用于匹配要转换的号码的模式。</span><span class="sxs-lookup"><span data-stu-id="46f2a-106">In the **Match this pattern** field, specify the pattern that will be used to match the numbers to be translated.</span></span> <span data-ttu-id="46f2a-107">在“转换规则”字段中，指定转换号码格式的模式。</span><span class="sxs-lookup"><span data-stu-id="46f2a-107">In the **Translation rule** field, specify a pattern for the format of translated numbers.</span></span> <span data-ttu-id="46f2a-108">例如，如果在"匹配此模式"字段中输入 ^ (\d \d+) $ ，在"转换规则"字段中输入 \+ {9} 011$1，则规则将 +441235551010 转换为 011441235551010。  </span><span class="sxs-lookup"><span data-stu-id="46f2a-108">For example, if you enter ^\+(\d{9}\d+)$ in the **Match this pattern** field and 011$1 in the **Translation rule** field, the rule will translate +441235551010 to 011441235551010.</span></span>
  
<span data-ttu-id="46f2a-109">有关可以使用 Skype for Business Server 控制面板执行的不同过程的详细信息，请参阅["管理 Skype for Business Server 2015"。](../../manage/manage.md)</span><span class="sxs-lookup"><span data-stu-id="46f2a-109">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>
  

