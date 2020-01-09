---
title: 在 Skype for Business 服务器中分配会议策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f384d19b-0950-4ec6-9d93-2c5958b83e71
description: 摘要：了解如何在 Skype for Business Server 中分配会议策略。
ms.openlocfilehash: f5e88e14c9516785cb3c45b5682bac13865b20ae
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991907"
---
# <a name="assign-conferencing-policies-in-skype-for-business-server"></a>在 Skype for Business 服务器中分配会议策略
 
**摘要：** 了解如何在 Skype for Business Server 中分配会议策略。
  
你可以使用 Skype for Business Server Management Shell 和**CsConferencingPolicy** cmdlet 将会议策略分配给用户。
  
## <a name="assign-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>使用 Skype for Business Server 命令行管理程序分配会议策略

在下面的示例中，将策略 SalesConferencingPolicy 分配给 Identity 为 "Ken Myer" 的用户：
  
```PowerShell
Grant-CsConferencingPolicy -identity "Ken Myer" -PolicyName SalesConferencingPolicy
```

在下一个示例中，将会议策略 FinanceConferencingPolicy 分配给 Finance 组织单位中拥有帐户的所有用户。若要将相同策略分配给指定组织单位 (OU) 中的所有用户，应使用 Get-CsUser cmdlet 来检索该 OU 中的所有帐户。在检索完用户帐户后，将该信息通过管道传递到 Grant-CsConferencingPolicy cmdlet，后者会将 FinanceConferencingPolicy 策略分配给集合中的每个用户：
  
```PowerShell
Get-CsUser -OU "ou=Finance,dc=litwareinc,dc=com" | Grant-CsConferencingPolicy -PolicyName FinanceConferencingPolicy
```

有关详细信息，包括完整语法和参数列表，请参阅[Grant-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps)。
  

