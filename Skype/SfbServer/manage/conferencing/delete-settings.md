---
title: 在 Skype for Business Server 2015 中删除会议配置设置
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ebafb86-13b9-468e-beda-f85f6786da85
description: 摘要： 了解如何删除会议在 Skype 业务服务器 2015年的配置设置。
ms.openlocfilehash: dec2e51dfe6ae0b9983515d849bc9fc416e9bcc4
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="delete-meeting-configuration-settings-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中删除会议配置设置
 
**摘要：**了解如何删除会议在 Skype 业务服务器 2015年的配置设置。
  
您可以删除会议通过 Skype 业务服务器控件面板或通过 Skype 业务服务器管理外壳程序的配置设置。
  
可以删除站点或用户配置，但无法删除全局配置。如果试图删除全局配置，该配置将自动重置为默认值。
  
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>删除会议通过 Skype 业务服务器控制面板配置设置

1. 使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2.  打开 Skype 业务服务器的控制面板。
    
3. 在左侧导航栏中，单击“**会议**”，然后单击“**会议配置**”。
    
4. 在会议配置的列表中，单击要删除的站点或池配置，单击“**编辑**”，然后单击“**删除**”。
    
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>删除会议通过 Skype 业务服务器管理外壳程序的配置设置

若要删除会议设置，请使用 **Remove-CsMeetingConfiguration** cmdlet。
  
以下命令将删除应用于 Redmond 站点的会议配置设置：
  
```
Remove-CsMeetingConfiguration -Identity "site:Redmond"
```

下一个命令删除应用于站点作用域的所有会议配置设置：
  
```
Get-CsMeetingConfiguration -Filter "site:*" | Remove-CsMeetingConfiguration
```

有关详细信息，包括参数的完整列表，请参阅[删除 CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps)。
  

