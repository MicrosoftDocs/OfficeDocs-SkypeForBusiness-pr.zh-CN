---
title: 在 Skype for Business 服务器中删除会议策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 497e6ca0-7a49-4f3e-9804-14414cf87b57
description: '摘要: 了解如何在 Skype for Business Server 中删除会议策略。'
ms.openlocfilehash: 2d02fa580acbc11c1b41643ab25cecba618ed09a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294248"
---
# <a name="delete-conferencing-policies-in-skype-for-business-server"></a>在 Skype for Business 服务器中删除会议策略
 
**摘要:** 了解如何在 Skype for Business Server 中删除会议策略。
  
你可以使用 Skype for Business Server 控制面板或使用 Skype for business Server 命令行管理器删除会议策略。
  
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>使用 Skype for Business Server "控制面板" 删除会议策略

1. 使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2.  打开 "Skype for Business 服务器" 控制面板。
    
3. 在左侧导航栏中，单击“**会议**”，然后单击“**会议策略**”。
    
4. 在会议策略列表中，单击要删除的站点策略或用户策略，再单击“**编辑**”，然后单击“**删除**”。
    
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>使用 Skype for Business Server 命令行管理程序删除会议策略

若要删除会议策略，请使用 **Remove-CsConferencingPolicy** cmdlet。
  
以下命令删除 Identity 为 RedmondConferencingPolicy 的会议策略：
  
```
Remove-CsConferencingPolicy -Identity "RedmondConferencingPolicy"
```

下一个命令删除允许外部用户记录会议的所有会议策略：
  
```
Get-CsConferencingPolicy | Where-Object {$_.AllowExternalUsersToRecordMeetings -eq $True} | Remove-CsConferencingPolicy
```

有关详细信息, 包括完整语法和参数列表, 请参阅[Remove-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps)。
  

