---
title: 删除会议策略Skype for Business Server
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
ms.assetid: 497e6ca0-7a49-4f3e-9804-14414cf87b57
description: 摘要：了解如何删除会议策略Skype for Business Server。
ms.openlocfilehash: d0447facef0f94b4e2a9c073b23f51438db7080a
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2022
ms.locfileid: "62391164"
---
# <a name="delete-conferencing-policies-in-skype-for-business-server"></a>删除会议策略Skype for Business Server
 
**摘要：** 了解如何删除会议策略中的Skype for Business Server。
  
可以使用控制面板或命令行管理程序Skype for Business Server会议策略Skype for Business Server策略。
  
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>使用控制面板删除Skype for Business Server策略

1. 使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。
    
2.  打开Skype for Business Server控制面板"。
    
3. 在左侧导航栏中，单击 **"会议"**，然后单击" **会议策略"**。
    
4. 在会议策略列表中，单击要删除的站点或用户策略，再单击"编辑"，然后单击"删除 **"**。
    
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>使用命令行管理程序删除Skype for Business Server策略

若要删除会议策略，请使用 **Remove-CsConferencingPolicy** cmdlet。
  
以下命令删除 Identity 为 RedmondConferencingPolicy 的会议策略：
  
```PowerShell
Remove-CsConferencingPolicy -Identity "RedmondConferencingPolicy"
```

下一个命令将删除允许外部用户录制会议的任何会议策略：
  
```PowerShell
Get-CsConferencingPolicy | Where-Object {$_.AllowExternalUsersToRecordMeetings -eq $True} | Remove-CsConferencingPolicy
```

有关详细信息，包括完整语法和参数列表，请参阅 [Remove-CsConferencingPolicy](/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps)。
