---
title: 如何输入电话号码？
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 28aa24b4-8c81-4327-9752-989ea7540db2
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords: ms.lync.lac.PortOrderNumbers
ms.custom:
- Calling Plans
description: '了解如何在将电话号码移植到 Skype for Business 时设置电话号码。 '
ms.openlocfilehash: df9d82a6e785954a95a455f0e43aa0e077f40bcf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280527"
---
# <a name="how-should-i-enter-the-phone-numbers"></a>如何输入电话号码？

当您移植电话号码时, 您必须以正确的格式输入它们。 
  
> [!NOTE]
> 每个电话号码或电话号码的范围必须在每一行上单独输入。 
  
- 输入单个电话号码时:
    
  - 将忽略所有特殊字符 (包括短划线 "-")。 例如：
    
  - 对于10位号码: ** &amp; \*(\*425 (\*&amp;) (&amp;\*4 ()) (\*250649**将更正为 **+ 14255550649**。
    
  - 对于11位号码: **1\*() (\*&amp;&amp;\*42 () (\*&amp;55550649**将更正为 **+ 14255550649**)。
    
  - 如果有10个或11个数字, 将忽略所有标记。 例如, ** \<div> 4255551234\</div>** 将是 **+ 14255551234**。
    
  - 将忽略 "-"、空格和括号。 例如：
    
  - 对于10位数字: **(425) 555-6776**将更正为 **+ 14255556776**。
    
  - 对于11位号码: **1 (425) 555-6776**将更正为 **+ 14255556776**。
    
  - 如果有10位或11位的电话号码, 则所有字母都将被视为特殊字符且被忽略。 例如：
    
  - 对于10位号码: **14jaosia2reoij05jof55506ajfoj49isdjf**将更正为 **+ 14255550649**。
    
  - 对于11位号码: **1ade4jaoda2rfoij05ojof55506dsfoj49if**将更正为 **+ 14255550649**。
    
  - 将更正特殊字符 (甚至其他语言) 的任意组合。 例如： 
    
  - 对于10位号码:**中文4中文2ajj5\*() (\*(5,) .。。551345**将更正为 **+ 14555551345**。
    
  - 对于一个11位数字:**中文4中文 2\*$ a5 () (\*(5 () .。。55 (. 1345**将更正为 **+ 14555551345**。
    
  - 如果任何数字中包含的数字少于10个或大于11个数字, 将突出显示这些数字以供用户更正:
    
  - \*\*5551245\* \*将突出显示并需要更正。
    
  - **1234567891011**将突出显示并需要更正。
    
  - 任何小于10位或大于11位且包含任何特殊字符的数字都将突出显示, 而不会自动更正。
    
  - 对于不带输入特殊字符的7位数字: 将突出显示**123456abcdefg7**并需要更正, 但不会忽略字母。
    
  - 对于输入了特殊字符的7位数字: **&amp;\*12345! @ # $% ^ (), 将突出显示 @ # $%&amp;\*^ () 7** 。 特殊字符不会被忽略。
    
- 输入电话号码范围时。
    
  - 仅允许两个电话号码。 较小的数字必须是区域中的第一个数字。
    
  - 所有特殊字符 (短划线 "-" 除外) 的处理方式与单个数字相同。 例如, **(425) 555 0&amp;\*(123-(1425) 5557899nm**将更正为 **+ 14255550123-+ 13202040659**。
    
  - "-" 用于分隔两个数字。 不支持在数字范围中包含多个 "-"。 例如, **(425) 555-0649-(425) 555-1115**应输入为 **(425) 5550649-(425) 5551115**。
    
  **有关完整的分步说明, 请参阅[将电话号码转移到 Office 365](/microsoftteams/transfer-phone-numbers-to-office-365)。**

  > [!NOTE]
  > 如果需要获取更多电话号码，请[联系商业版产品支持人员 - 管理员帮助](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)

  
## <a name="related-topics"></a>相关主题
[关于转移电话号码的常见问题](/microsoftteams/transferring-phone-numbers-common-questions)

[用于通话套餐的不同类型的电话号码](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[管理你的组织的电话号码](/microsoftteams/manage-phone-numbers-for-your-organization)

[紧急呼叫条款和条件](/microsoftteams/emergency-calling-terms-and-conditions)

[Skype for Business Online：紧急呼叫免责声明标签](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 