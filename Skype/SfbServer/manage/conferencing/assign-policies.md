---
title: 在 Skype for Business Server 中分配会议策略
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: f384d19b-0950-4ec6-9d93-2c5958b83e71
description: 摘要：了解如何在 Skype for Business Server 中分配会议策略。
ms.openlocfilehash: 61082a9189b085c852e7593207fc86dcc6509139
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51099158"
---
# <a name="assign-conferencing-policies-in-skype-for-business-server"></a>在 Skype for Business Server 中分配会议策略
 
**摘要：** 了解如何在 Skype for Business Server 中分配会议策略。
  
可以使用 Skype for Business Server 命令行管理程序和 **Grant-CsConferencingPolicy** cmdlet 将会议策略分配给用户。
  
## <a name="assign-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>使用 Skype for Business Server 命令行管理程序分配会议策略

在下面的示例中，将策略 SalesConferencingPolicy 分配给 Identity 为"Ken Myer"的用户：
  
```PowerShell
Grant-CsConferencingPolicy -identity "Ken Myer" -PolicyName SalesConferencingPolicy
```

下一个示例将会议策略 FinanceConferencingPolicy 分配给在 Finance 组织单位中拥有帐户的所有用户。 要将相同策略分配到给定组织单位 (OU) 中的所有用户，应使用 Get-CsUser cmdlet 来检索该 OU 中的所有帐户。 检索用户帐户后，该信息随后会通过管道通过管道通过 Grant-CsConferencingPolicy cmdlet，该 cmdlet 将 FinanceConferencingPolicy 策略分配给集合中的每个用户：
  
```PowerShell
Get-CsUser -OU "ou=Finance,dc=litwareinc,dc=com" | Grant-CsConferencingPolicy -PolicyName FinanceConferencingPolicy
```

有关详细信息，包括完整语法和参数列表，请参阅 [Grant-CsConferencingPolicy](/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps)。
