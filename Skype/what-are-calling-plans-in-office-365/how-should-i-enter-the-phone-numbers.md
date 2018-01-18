---
title: "应输入电话号码的方式"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 28aa24b4-8c81-4327-9752-989ea7540db2
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords: ms.lync.lac.PortOrderNumbers
ms.custom: Calling Plans
description: "了解如何设置电话号码，当您将它们到 Skype 的业务。 "
ms.openlocfilehash: 1906fc98f47402ec740d71ff69b67b07392ae57d
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/15/2017
---
# <a name="how-should-i-enter-the-phone-numbers"></a>应输入电话号码的方式

当移植电话号码时，您必须以正确的格式输入它们。 
  
> [!NOTE]
> 每个电话号码或电话号码的范围必须分别输入每个行上。 
  
- 当您正在输入一个电话号码：
    
  - 将忽略所有特殊字符 (包括破折号"-")。 例如：
    
  - 10 位号码： ** &amp; \*(425\*（) (\*&amp;4&amp;\*（)） (\*250649**将修正为**+14255550649**。
    
  - 11 位号码： **1\*（) (\*&amp;42&amp;\*（) (\*&amp;55550649**将修正为**+14255550649**。
    
  - 如果有 10 或 11 位，所有的标记将被忽略。 例如， ** \<div > 4255551234\</div >**将是**+14255551234**。
    
  - "-"，空间和括号将被忽略。 例如：
    
  - 为一个 10 位数字： **(425) 555-6776**将修正为**+14255556776**。
    
  - 11 位号码： **1(425) 555 6776**将修正为**+14255556776**。
    
  - 将视为特殊字符，如果 10 位或 11 位数字的电话号码，则忽略所有字母。 例如：
    
  - 为一个 10 位数字： **14jaosia2reoij05jof55506ajfoj49isdjf**将修正为**+14255550649**。
    
  - 11 位号码： **1ade4jaoda2rfoij05ojof55506dsfoj49if**将修正为**+14255550649**。
    
  - 即使在其他语言中的特殊字符的任意组合将得到纠正。 例如： 
    
  - 10 位号码：**中文4中文2ajj5\*（) (\*(5()...551345**将修正为**+14555551345**。
    
  - 11 位号码：**中文4中文2 美元 a5\*（) (\*(5()...55 (.1345**将修正为**+14555551345**。
    
  - 如果任何数字包含少于 10 位或多于 11 位，他们将会突出显示为用户纠正：
    
  - \*\*5551245\* \*将突出显示，需要进行更正。
    
  - **1234567891011**将突出显示，需要进行更正。
    
  - 将突出显示任何数字的位数少于 10 个或多于 11 位，与任何特殊的字符，而不被自动更正。
    
  - 不含特殊字符输入的 7 位数编号为： **123456abcdefg7**将突出显示，需要进行更正，但不会忽略字母。
    
  - 特殊字符与输入的 7 位数编号为： **12345!@#$%^&amp;\*（)-@# $%^&amp;\*（7)**将突出以修正。 特殊字符不会被忽略。
    
- 当您输入电话号码的范围。
    
  - 允许仅有两个电话号码。 较小的数字必须是该区域的第一个数字。
    
  - 所有特殊字符 (除连字符"-") 是一个数字被同等对待。 例如， **(425) 555 0&amp;\*(123-（1425年) 5557899nm**将修正为**+14255550123-+13202040659**。
    
  - "-"用于只分隔两个数字。 它不支持包含多个"-"号范围内。 例如，应作为输入**(425) 555-0649-(425) 555-1115** **(425) 5550649-（425) 5551115**。
    
 **完整的逐步说明，请参阅[传输到 Office 365 的电话号码](transfer-phone-numbers-to-office-365.md)。**

 > [!NOTE]
> 如果您需要得到比这更多的电话号码，请[联系支持业务产品的管理帮助](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)

  
## <a name="related-topics"></a>相关主题
[传送电话号码的常见问题](transferring-phone-numbers-common-questions.md)

[不同种类的用于调用计划的电话号码](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[管理您的组织的电话号码](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[紧急呼叫条款和条件](emergency-calling-terms-and-conditions.md)

[Skype for Business Online：紧急呼叫免责标签](https://go.microsoft.com/fwlink/?LinkID=692099)