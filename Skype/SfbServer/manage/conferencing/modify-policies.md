---
title: 修改会议策略Skype for Business Server
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
ms.assetid: b40ba905-e74a-4456-ac94-65471bc2d66d
description: 摘要：了解如何在 Skype for Business Server 中修改会议策略。
ms.openlocfilehash: 5676a6bc0970a98fa76357deb1403c6b2337920273262c0a76a465b33d5d18c4
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54290350"
---
# <a name="modify-conferencing-policies-in-skype-for-business-server"></a>修改会议策略Skype for Business Server
 
**摘要：** 了解如何在会议策略中修改Skype for Business Server。
  
可以使用控制面板或命令行管理程序Skype for Business Server会议策略Skype for Business Server策略。
  
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>使用控制面板修改Skype for Business Server策略

1. 使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。
    
2.  打开Skype for Business Server控制面板"。
    
3. 在左侧导航栏中，单击 **"会议"，** 然后单击"**会议策略"。**
    
4. 在会议策略列表中，单击要更改的策略，单击“编辑”，然后单击“显示详细信息”。
    
5. 在“编辑会议策略”中，修改任意策略设置（不能修改的策略名称除外）。
    
6. 单击“提交”。
    
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>使用命令行管理程序修改Skype for Business Server策略

若要修改会议策略，请使用 **Set-CsConferencingPolicy** cmdlet。
  
以下示例修改会议策略 SalesConferencingPolicy 的属性值。 该命令将 AllowConferenceRecording 属性的值设置为 False：
  
```PowerShell
Set-CsConferencingPolicy -Identity SalesConferencingPolicy -AllowConferenceRecording $False
```

有关详细信息，包括完整语法和参数列表，请参阅 [Set-CsConferencingPolicy](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)。
