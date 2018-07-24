---
title: 修改会议配置设置中 Skype 业务服务器
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 11d1f9ac-0029-429b-be2b-d7591abfc192
description: 摘要： 了解如何修改会议配置设置中 Skype 业务服务器。
ms.openlocfilehash: b4b8307711fcf7b120c867debe5ab3e2978f6ef7
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "20978965"
---
# <a name="modify-meeting-configuration-settings-in-skype-for-business-server"></a>修改会议配置设置中 Skype 业务服务器
 
**摘要：** 了解如何修改会议配置设置中 Skype 业务服务器。
  
您可以修改会议配置设置，使用的业务 Server Control Panel Skype 或使用 Skype 业务 Server Management Shell。
  
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>修改使用适用于业务 Server Control Panel Skype 会议配置设置

1. 使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2.  打开 Skype 业务 Server Control Panel。
    
3. 在左侧导航栏中，单击“**会议**”，然后单击“**会议配置**”。
    
4. 在会议配置列表中，单击要更改的配置，再单击“**编辑**”，然后单击“**显示详细信息**”。
    
5. 在“**编辑会议配置**”中，修改除配置名称外的任一配置设置，配置名称不能修改。
    
6. 单击“**提交**”。
    
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>修改会议使用 Skype 业务 Server 命令行管理程序配置设置

若要修改会议配置设置，请使用 **Set-CsMeetingConfiguration** cmdlet。
  
下例所示的命令修改分配给 Redmond 站点 (-Identity site:Redmond) 的会议配置设置。在此示例中，DesignateAsPresenter 属性的值设置为 Everyone：
  
```
Set-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

有关详细信息，包括完成参数的列表，请参阅[Set-csmeetingconfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps)。
  

