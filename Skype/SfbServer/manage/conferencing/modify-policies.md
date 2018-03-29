---
title: 在 Skype for Business Server 2015 中修改会议策略
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b40ba905-e74a-4456-ac94-65471bc2d66d
description: 摘要： 了解如何修改业务服务器 2015 Skype 会议策略。
ms.openlocfilehash: b0456db5d0c6131b3b3999a87fc824d6ee3b4b30
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="modify-conferencing-policies-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中修改会议策略
 
**摘要：**了解如何修改业务服务器 2015 Skype 会议策略。
  
通过 Skype 业务服务器控件面板或通过 Skype 业务服务器管理外壳，您可以修改会议策略。
  
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>通过 Skype 业务服务器控件面板中修改会议策略

1. 使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2.  打开 Skype 业务服务器的控制面板。
    
3. 在左侧导航栏中，单击“**会议**”，然后单击“**会议策略**”。
    
4. 在会议策略列表中，单击要更改的策略，单击“**编辑**”，然后单击“**显示详细信息**”。
    
5. 在“**编辑会议策略**”中，修改任意策略设置（不能修改的策略名称除外）。
    
6. 单击“**提交**”。
    
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>通过 Skype 业务服务器管理外壳程序修改会议策略

若要修改会议策略，使用**一组 CsConferencingPolicy** cmdlet。
  
下面的示例修改会议策略 SalesConferencingPolicy 的属性值。 该命令将 AllowConferenceRecording 属性的值设置为 False：
  
```
Set-CsConferencingPolicy -Identity SalesConferencingPolicy -AllowConferenceRecording $False
```

包括完整语法和参数的列表的详细信息，请参阅[设置 CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)。
  

