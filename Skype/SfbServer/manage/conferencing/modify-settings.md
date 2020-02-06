---
title: 在 Skype for Business 服务器中修改会议配置设置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 11d1f9ac-0029-429b-be2b-d7591abfc192
description: 摘要：了解如何在 Skype for Business Server 中修改会议配置设置。
ms.openlocfilehash: 893e3fb8c9c441f8dc515eaf3a8a4aaa1ff04620
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818493"
---
# <a name="modify-meeting-configuration-settings-in-skype-for-business-server"></a>在 Skype for Business 服务器中修改会议配置设置
 
**摘要：** 了解如何在 Skype for Business Server 中修改会议配置设置。
  
可以使用 Skype for Business Server 控制面板或使用 Skype for business Server 命令行管理器修改会议配置设置。
  
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>使用 Skype for Business Server "控制面板" 修改会议配置设置

1. 使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2.  打开 "Skype for Business 服务器" 控制面板。
    
3. 在左侧导航栏中，单击“**会议**”，然后单击“**会议配置**”。
    
4. 在会议配置列表中，单击要更改的配置，再单击“**编辑**”，然后单击“**显示详细信息**”。
    
5. 在“**编辑会议配置**”中，修改除配置名称外的任一配置设置，配置名称不能修改。
    
6. 单击“**提交**”。
    
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>使用 Skype for Business Server 命令行管理程序修改会议配置设置

若要修改会议配置设置，请使用 **Set-CsMeetingConfiguration** cmdlet。
  
下例所示的命令修改分配给 Redmond 站点 (-Identity site:Redmond) 的会议配置设置。在此示例中，DesignateAsPresenter 属性的值设置为 Everyone：
  
```PowerShell
Set-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

有关详细信息，包括参数的完整列表，请参阅[Set-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps)。
  

