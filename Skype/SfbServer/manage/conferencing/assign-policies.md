---
title: 为业务服务器分配中 Skype 的会议策略
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f384d19b-0950-4ec6-9d93-2c5958b83e71
description: 摘要： 了解如何为业务服务器分配中 Skype 的会议策略。
ms.openlocfilehash: 44e29842fd11d600aa5a692e98b5ddbb72149ade
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30892630"
---
# <a name="assign-conferencing-policies-in-skype-for-business-server"></a>为业务服务器分配中 Skype 的会议策略
 
**摘要：** 了解如何为业务服务器分配中 Skype 的会议策略。
  
使用 Skype 的业务 Server 命令行管理程序和**Grant-csconferencingpolicy** cmdlet，可以向用户分配会议策略。
  
## <a name="assign-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>使用 Skype 业务 Server 命令行管理程序分配会议策略

在下面的示例中，将策略 SalesConferencingPolicy 分配给 Identity 为 "Ken Myer" 的用户：
  
```
Grant-CsConferencingPolicy -identity "Ken Myer" -PolicyName SalesConferencingPolicy
```

在下一个示例中，将会议策略 FinanceConferencingPolicy 分配给 Finance 组织单位中拥有帐户的所有用户。若要将相同策略分配给指定组织单位 (OU) 中的所有用户，应使用 Get-CsUser cmdlet 来检索该 OU 中的所有帐户。在检索完用户帐户后，将该信息通过管道传递到 Grant-CsConferencingPolicy cmdlet，后者会将 FinanceConferencingPolicy 策略分配给集合中的每个用户：
  
```
Get-CsUser -OU "ou=Finance,dc=litwareinc,dc=com" | Grant-CsConferencingPolicy -PolicyName FinanceConferencingPolicy
```

有关详细信息，包括完成语法和参数的列表，，请参阅[Grant-csconferencingpolicy](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps)。
  

