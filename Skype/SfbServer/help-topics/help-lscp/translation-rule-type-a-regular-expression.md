---
title: 转换规则 键入正则表达式
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.VoiceRuleRegexEdit
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 5ee83724-b399-4f8d-8f6d-4b53a26296b4
description: 在“匹配此模式”字段中，指定将用于匹配要转换的号码的模式。 在“转换规则”字段中，指定转换号码格式的模式。 例如，如果在"匹配此模式"字段中输入 ^\+ (\d{9}\d+) $，在"转换规则"字段中输入 011$1，则规则将 +441235551010 转换为 011441235551010。
ms.openlocfilehash: 6018784593c45711e012a3855bcc18b274a0bbc2
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2022
ms.locfileid: "62410175"
---
# <a name="translation-rule-type-a-regular-expression"></a>转换规则：键入正则表达式
 
在“匹配此模式”字段中，指定将用于匹配要转换的号码的模式。 在“转换规则”字段中，指定转换号码格式的模式。 例如，如果在"匹配此模式"字段中输入 ^\+ (\d  {9}\d+) $，在"转换规则"字段中输入 011$1，则规则将 +441235551010 转换为 011441235551010。
  
有关可以使用控制面板执行的不同过程的详细信息，Skype for Business Server Manage [Skype for Business Server 2015](../../manage/manage.md)。
  

