---
title: 在 Skype for Business Server 2015 中修改会议配置设置
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 11d1f9ac-0029-429b-be2b-d7591abfc192
description: 摘要： 了解如何修改会议在 Skype 业务服务器 2015年的配置设置。
ms.openlocfilehash: 95f28f35859553f79fc6f74f8850f224bda54deb
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="modify-meeting-configuration-settings-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中修改会议配置设置
 
**摘要：**了解如何修改会议在 Skype 业务服务器 2015年的配置设置。
  
您可以修改会议通过 Skype 业务服务器控件面板或通过 Skype 业务服务器管理外壳程序的配置设置。
  
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>修改会议通过 Skype 业务服务器控制面板配置设置

1. 使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2.  打开 Skype 业务服务器的控制面板。
    
3. 在左侧导航栏中，单击“**会议**”，然后单击“**会议配置**”。
    
4. 在会议配置列表中，单击要更改的配置，再单击“**编辑**”，然后单击“**显示详细信息**”。
    
5. 在“**编辑会议配置**”中，修改除配置名称外的任一配置设置，配置名称不能修改。
    
6. 单击“**提交**”。
    
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>修改会议通过 Skype 业务服务器管理外壳程序的配置设置

若要修改会议配置设置，请使用 **Set-CsMeetingConfiguration** cmdlet。
  
下例所示的命令修改分配给 Redmond 站点 (-Identity site:Redmond) 的会议配置设置。在此示例中，DesignateAsPresenter 属性的值设置为 Everyone：
  
```
Set-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

包括的参数的完整列表的详细信息，请参阅[设置 CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps)。
  

