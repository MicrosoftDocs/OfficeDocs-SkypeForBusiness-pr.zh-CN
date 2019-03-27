---
title: 删除业务服务器中 Skype 的会议策略
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 497e6ca0-7a49-4f3e-9804-14414cf87b57
description: 摘要： 了解如何删除 Business Server Skype 中的会议策略。
ms.openlocfilehash: 404e981af46b29bd95b36ca402c9f691e34737a5
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30873364"
---
# <a name="delete-conferencing-policies-in-skype-for-business-server"></a>删除业务服务器中 Skype 的会议策略
 
**摘要：** 了解如何删除 Business Server Skype 中的会议策略。
  
可以使用适用于业务 Server Control Panel Skype 或使用 Skype 业务 Server 命令行管理程序中删除会议策略。
  
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>使用适用于业务 Server Control Panel Skype 删除会议策略

1. 使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2.  打开 Skype 业务 Server Control Panel。
    
3. 在左侧导航栏中，单击“**会议**”，然后单击“**会议策略**”。
    
4. 在会议策略列表中，单击要删除的站点策略或用户策略，再单击“**编辑**”，然后单击“**删除**”。
    
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>使用 Skype 业务 Server 命令行管理程序删除会议策略

若要删除会议策略，请使用 **Remove-CsConferencingPolicy** cmdlet。
  
以下命令删除 Identity 为 RedmondConferencingPolicy 的会议策略：
  
```
Remove-CsConferencingPolicy -Identity "RedmondConferencingPolicy"
```

下一个命令删除允许外部用户记录会议的所有会议策略：
  
```
Get-CsConferencingPolicy | Where-Object {$_.AllowExternalUsersToRecordMeetings -eq $True} | Remove-CsConferencingPolicy
```

有关详细信息，包括完成语法和参数的列表，，请参阅[Remove-csconferencingpolicy](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps)。
  

