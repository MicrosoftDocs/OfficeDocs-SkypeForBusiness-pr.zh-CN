---
title: 删除 Skype for Business 服务器中的会议配置设置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ebafb86-13b9-468e-beda-f85f6786da85
description: 摘要：了解如何在 Skype for Business Server 中删除会议配置设置。
ms.openlocfilehash: cbf63ba635077dd61599d4bc84a740906b662a6c
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991857"
---
# <a name="delete-meeting-configuration-settings-in-skype-for-business-server"></a>删除 Skype for Business 服务器中的会议配置设置
 
**摘要：** 了解如何在 Skype for Business Server 中删除会议配置设置。
  
可以使用 Skype for Business Server 控制面板或使用 Skype for business Server 命令行管理器删除会议配置设置。
  
可以删除站点或用户配置，但无法删除全局配置。如果试图删除全局配置，该配置将自动重置为默认值。
  
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>使用 Skype for Business 服务器控制面板删除会议配置设置

1. 使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2.  打开 "Skype for Business 服务器" 控制面板。
    
3. 在左侧导航栏中，单击“**会议**”，然后单击“**会议配置**”。
    
4. 在会议配置的列表中，单击要删除的站点或池配置，单击“**编辑**”，然后单击“**删除**”。
    
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>使用 Skype for Business Server 命令行管理程序删除会议配置设置

若要删除会议设置，请使用 **Remove-CsMeetingConfiguration** cmdlet。
  
以下命令将删除应用于 Redmond 站点的会议配置设置：
  
```PowerShell
Remove-CsMeetingConfiguration -Identity "site:Redmond"
```

下一个命令删除应用于站点作用域的所有会议配置设置：
  
```PowerShell
Get-CsMeetingConfiguration -Filter "site:*" | Remove-CsMeetingConfiguration
```

有关详细信息，包括参数的完整列表，请参阅[Remove-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps)。
  

