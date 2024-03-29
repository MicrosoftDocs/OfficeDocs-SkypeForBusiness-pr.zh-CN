---
title: 在会议部署中分配Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: f384d19b-0950-4ec6-9d93-2c5958b83e71
description: 摘要：了解如何在 Skype for Business Server 中分配会议策略。
ms.openlocfilehash: fe8483abe2a581668b5f5463f588b051e40c7771
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2022
ms.locfileid: "62399736"
---
# <a name="assign-conferencing-policies-in-skype-for-business-server"></a>在会议部署中分配Skype for Business Server
 
**摘要：** 了解如何在会议部署中分配Skype for Business Server。
  
可以使用命令行管理程序和 **Grant-CsConferencingPolicy** cmdlet 将Skype for Business Server策略分配给用户。
  
## <a name="assign-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>使用命令行管理程序分配Skype for Business Server策略

在下面的示例中，将策略 SalesConferencingPolicy 分配给 Identity 为"Ken Myer"的用户：
  
```PowerShell
Grant-CsConferencingPolicy -identity "Ken Myer" -PolicyName SalesConferencingPolicy
```

下一个示例将会议策略 FinanceConferencingPolicy 分配给在 Finance 组织单位中拥有帐户的所有用户。 要将相同策略分配到给定组织单位 (OU) 中的所有用户，应使用 Get-CsUser cmdlet 来检索该 OU 中的所有帐户。 检索用户帐户后，该信息随后会通过管道被通过管道通过 Grant-CsConferencingPolicy cmdlet，该 cmdlet 将 FinanceConferencingPolicy 策略分配给集合中的每个用户：
  
```PowerShell
Get-CsUser -OU "ou=Finance,dc=litwareinc,dc=com" | Grant-CsConferencingPolicy -PolicyName FinanceConferencingPolicy
```

有关详细信息，包括完整语法和参数列表，请参阅 [Grant-CsConferencingPolicy](/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps)。
