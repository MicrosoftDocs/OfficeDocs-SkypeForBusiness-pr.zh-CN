---
title: 删除会议配置设置中 Skype 业务服务器
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ebafb86-13b9-468e-beda-f85f6786da85
description: 摘要： 了解如何删除会议配置设置中 Skype 业务服务器。
ms.openlocfilehash: 47cde99751c90b71a52b70a0bde9aaf15acf0154
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30887468"
---
# <a name="delete-meeting-configuration-settings-in-skype-for-business-server"></a>删除会议配置设置中 Skype 业务服务器
 
**摘要：** 了解如何删除会议配置设置中 Skype 业务服务器。
  
您可以删除会议配置设置，使用的业务 Server Control Panel Skype 或使用 Skype 业务 Server Management Shell。
  
可以删除站点或用户配置，但无法删除全局配置。如果试图删除全局配置，该配置将自动重置为默认值。
  
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>删除会议配置设置，使用 Skype 业务 Server Control Panel

1. 使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2.  打开 Skype 业务 Server Control Panel。
    
3. 在左侧导航栏中，单击“**会议**”，然后单击“**会议配置**”。
    
4. 在会议配置的列表中，单击要删除的站点或池配置，单击“**编辑**”，然后单击“**删除**”。
    
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>删除会议使用 Skype 业务 Server 命令行管理程序配置设置

若要删除会议设置，请使用 **Remove-CsMeetingConfiguration** cmdlet。
  
以下命令将删除应用于 Redmond 站点的会议配置设置：
  
```
Remove-CsMeetingConfiguration -Identity "site:Redmond"
```

下一个命令删除应用于站点作用域的所有会议配置设置：
  
```
Get-CsMeetingConfiguration -Filter "site:*" | Remove-CsMeetingConfiguration
```

有关详细信息，包括完成参数的列表，请参阅[Remove-csmeetingconfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps)。
  

