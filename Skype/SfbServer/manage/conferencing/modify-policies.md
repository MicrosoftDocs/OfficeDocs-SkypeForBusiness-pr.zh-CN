---
title: 修改业务服务器中 Skype 的会议策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b40ba905-e74a-4456-ac94-65471bc2d66d
description: 摘要： 了解如何修改业务服务器中 Skype 的会议策略。
ms.openlocfilehash: 0ca232398c9133c3340cbae909ac43d44ba641dd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33911985"
---
# <a name="modify-conferencing-policies-in-skype-for-business-server"></a>修改业务服务器中 Skype 的会议策略
 
**摘要：** 了解如何修改业务服务器中 Skype 的会议策略。
  
使用适用于业务 Server Control Panel Skype 或使用 Skype 业务 Server 命令行管理程序，您可以修改会议策略。
  
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>使用适用于业务 Server Control Panel Skype 修改会议策略

1. 使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2.  打开 Skype 业务 Server Control Panel。
    
3. 在左侧导航栏中，单击“**会议**”，然后单击“**会议策略**”。
    
4. 在会议策略列表中，单击要更改的策略，单击“**编辑**”，然后单击“**显示详细信息**”。
    
5. 在“**编辑会议策略**”中，修改任意策略设置（不能修改的策略名称除外）。
    
6. 单击“**提交**”。
    
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>使用 Skype 业务 Server 命令行管理程序修改会议策略

若要修改的会议策略，请使用**Set-csconferencingpolicy** cmdlet。
  
下面的示例修改会议策略 SalesConferencingPolicy 的属性值。 该命令将 AllowConferenceRecording 属性的值设置为 False：
  
```
Set-CsConferencingPolicy -Identity SalesConferencingPolicy -AllowConferenceRecording $False
```

有关详细信息，包括完成语法和参数的列表，，请参阅[Set-csconferencingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)。
  

