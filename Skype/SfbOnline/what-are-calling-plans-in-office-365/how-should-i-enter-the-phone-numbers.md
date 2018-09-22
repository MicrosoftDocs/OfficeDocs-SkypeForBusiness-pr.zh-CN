---
title: 我应该如何输入电话号码？
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
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords: ms.lync.lac.PortOrderNumbers
ms.custom:
- Calling Plans
description: '了解如何设置电话号码，当您对业务的 Skype 端口它们。 '
ms.openlocfilehash: 8d214ea7cf21ea713de28763f36b9995160fb395
ms.sourcegitcommit: c5940ef2674a00281604045baf8b2a320c4b189d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/21/2018
ms.locfileid: "24958138"
---
# <a name="how-should-i-enter-the-phone-numbers"></a>我应该如何输入电话号码？

当移植电话号码时，您必须按正确格式输入它们。 
  
> [!NOTE]
> 每个电话号码或电话号码的范围必须分别输入每一行上。 
  
- 当您输入一个电话号码：
    
  - 将忽略所有特殊字符 (包括划线"-")。 例如：
    
  - 为 10 位数字： ** &amp; \*(425\*（) (\*&amp;4&amp;\*（)） (\*250649**将纠正到 **+14255550649**。
    
  - 11 位数字的号码： **1\*（) (\*&amp;42&amp;\*（) (\*&amp;55550649**将纠正到 **+14255550649**。
    
  - 如果有 10 或 11 位，则将忽略所有标记。 例如， ** \<div > 4255551234\</div >** 将 **+14255551234**。
    
  - "-"，将忽略空格和括号。 例如：
    
  - 为 10 位数字： **(425) 555-6776**将纠正到 **+14255556776**。
    
  - 11 位数字的号码： **1(425) 555-6776**将纠正到 **+14255556776**。
    
  - 将视为特殊字符和如果 10 位数字或 11 位数字的电话号码，则忽略所有字母。 例如：
    
  - 为 10 位数字： **14jaosia2reoij05jof55506ajfoj49isdjf**将纠正到 **+14255550649**。
    
  - 11 位数字的号码： **1ade4jaoda2rfoij05ojof55506dsfoj49if**将纠正到 **+14255550649**。
    
  - 将更正特殊字符，即使在其他语言的任意组合。 例如： 
    
  - 为 10 位数字：**中文4中文2ajj5\*（) (\*(5()...551345**将纠正到 **+14555551345**。
    
  - 11 位数字的号码：**中文4中文2$ a5\*（) (\*(5()...55 (.1345**将纠正到 **+14555551345**。
    
  - 如果少于 10 位数字或多个 11 位数字不包含任何数字，他们将会突出显示正确的用户：
    
  - \*\*5551245\* \*将突出显示和需要更正。
    
  - **1234567891011**将突出显示，并需要更正。
    
  - 少于 10 位数字或多个 11 位数字，与任何特殊字符，任何数字将被自动更正不突出显示。
    
  - 输入 7 位号码不包含特殊字符： **123456abcdefg7**将突出显示和需要更正，但不会忽略字母。
    
  - 输入 7 位号码与特殊字符： **12345!@#$%^&amp;\*（)-@# $%^&amp;\*（7)** 将突出显示要更正。 特殊字符不会被忽略。
    
- 当您正在输入电话号码的范围。
    
  - 允许只有两个电话号码。 较小的数字必须是范围中的第一个数字。
    
  - 所有特殊字符 (除划线"-") 是相同视为单个数字。 例如， **(425) 555 0&amp;\*(123-（1425年) 5557899nm**将纠正到 **+ 14255550123-+13202040659**。
    
  - "-"用于仅分隔的两个数字。 它不支持以包括多个"-"中的号码范围。 例如，应作为输入 **(425) 555-0649-(425) 555-1115** **(425) 5550649-（425) 5551115**。
    
 **有关完整的分步说明，请参阅[传输到 Office 365 的电话号码](/microsoftteams/transfer-phone-numbers-to-office-365)。**

 > [!NOTE]
> 如果需要获取更多电话号码，请[联系商业版产品支持人员 - 管理员帮助](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)

  
## <a name="related-topics"></a>相关主题
[关于转移电话号码的常见问题](/microsoftteams/transferring-phone-numbers-common-questions)

[用于通话套餐的不同类型的电话号码](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[管理你的组织的电话号码](/microsoftteams/manage-phone-numbers-for-your-organization)

[紧急呼叫条款和条件](/microsoftteams/emergency-calling-terms-and-conditions)

[Skype for Business Online：紧急呼叫免责声明标签](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 