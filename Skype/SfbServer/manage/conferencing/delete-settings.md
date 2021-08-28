---
title: 删除会议配置Skype for Business Server
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
ms.assetid: 8ebafb86-13b9-468e-beda-f85f6786da85
description: 摘要：了解如何删除会议配置设置Skype for Business Server。
ms.openlocfilehash: 8aa83668be612e2c35d2f0c541c0494ca5cbd24b
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58595544"
---
# <a name="delete-meeting-configuration-settings-in-skype-for-business-server"></a>删除会议配置Skype for Business Server
 
**摘要：** 了解如何删除会议配置设置Skype for Business Server。
  
可以使用控制面板或命令行管理程序Skype for Business Server会议配置Skype for Business Server设置。
  
可以删除站点或用户配置，但不能删除全局配置。 如果您尝试删除全局配置，则会自动将其重置为默认值。
  
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>使用"控制面板"Skype for Business Server会议配置设置

1. 使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。
    
2.  打开Skype for Business Server控制面板"。
    
3. 在左侧导航栏中，单击 **"会议"，** 然后单击"会议 **配置"。**
    
4. 在会议配置列表中，单击要删除的站点或池配置，再单击"编辑"，然后单击"删除 **"。**
    
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>使用命令行管理程序Skype for Business Server会议配置设置

若要删除会议设置，请使用 **Remove-CsMeetingConfiguration** cmdlet。
  
以下命令删除应用于 Redmond 站点的会议配置设置：
  
```PowerShell
Remove-CsMeetingConfiguration -Identity "site:Redmond"
```

下一个命令将删除应用于站点范围的所有会议配置设置：
  
```PowerShell
Get-CsMeetingConfiguration -Filter "site:*" | Remove-CsMeetingConfiguration
```

有关详细信息，包括参数的完整列表，请参阅[Remove-CsMeetingConfiguration。](/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps)
