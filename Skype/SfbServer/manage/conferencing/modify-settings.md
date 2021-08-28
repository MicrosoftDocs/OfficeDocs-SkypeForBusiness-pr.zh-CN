---
title: 修改会议配置Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 11d1f9ac-0029-429b-be2b-d7591abfc192
description: Summary： Learn how to modify meeting configuration settings in Skype for Business Server.
ms.openlocfilehash: c3da96738e4902be94ed1efc3b5037b105c0771f
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58587068"
---
# <a name="modify-meeting-configuration-settings-in-skype-for-business-server"></a>修改会议配置Skype for Business Server
 
**摘要：** 了解如何在会议环境中修改Skype for Business Server。
  
可以使用控制面板或命令行管理程序Skype for Business Server会议配置Skype for Business Server设置。
  
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>使用"控制面板"Skype for Business Server会议配置设置

1. 使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。
    
2.  打开Skype for Business Server控制面板"。
    
3. 在左侧导航栏中，单击 **"会议"，** 然后单击"会议 **配置"。**
    
4. 在会议配置列表中，单击要更改的配置，再单击"编辑"，然后单击"显示 **详细信息"。**
    
5. 在 **"编辑会议配置**"中，修改任何配置设置，但配置名称除外，不能修改配置名称。
    
6. 单击“提交”。
    
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>使用命令行管理程序Skype for Business Server会议配置设置

若要修改会议配置设置，请使用 **Set-CsMeetingConfiguration** cmdlet。
  
以下示例中显示的命令修改分配给 Redmond 站点 (-Identity site：Redmond) 。 在这种情况下，DesignateAsPresenter 属性的值设置为 Everyone：
  
```PowerShell
Set-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

有关详细信息，包括参数的完整列表，请参阅[Set-CsMeetingConfiguration。](/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps)
