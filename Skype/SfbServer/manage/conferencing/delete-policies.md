---
title: 删除 Skype for Business Server 中的会议策略
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
ms.assetid: 497e6ca0-7a49-4f3e-9804-14414cf87b57
description: 摘要：了解如何删除 Skype for Business Server 中的会议策略。
ms.openlocfilehash: 9aadaf82aea7f057cf1969f06d4257992b64a86a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119501"
---
# <a name="delete-conferencing-policies-in-skype-for-business-server"></a>删除 Skype for Business Server 中的会议策略
 
**摘要：** 了解如何删除 Skype for Business Server 中的会议策略。
  
可以使用 Skype for Business Server 控制面板或 Skype for Business Server 命令行管理程序删除会议策略。
  
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>使用 Skype for Business Server 控制面板删除会议策略

1. 使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。
    
2.  打开 Skype for Business Server 控制面板。
    
3. 在左侧导航栏中，单击 **"会议"，** 然后单击"**会议策略"。**
    
4. 在会议策略列表中，单击要删除的站点或用户策略，再单击"编辑"，然后单击"删除 **"。**
    
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>使用 Skype for Business Server 命令行管理程序删除会议策略

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
