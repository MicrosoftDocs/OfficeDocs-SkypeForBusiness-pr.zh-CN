---
title: 在 Skype for Business Server 2015 中查看会议配置设置
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 932c7e2d-6de3-4176-ac6e-ec230f8230f2
description: 摘要： 了解如何查看会议在 Skype 业务服务器 2015年的配置设置。
ms.openlocfilehash: 382e50a0f41301953f4313c5019d1eb0d27804e5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="view-meeting-configuration-settings-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中查看会议配置设置
 
**摘要：**了解如何查看会议在 Skype 业务服务器 2015年的配置设置。
  
您可以查看会议通过 Skype 业务服务器控件面板或通过 Skype 业务服务器管理外壳程序的配置设置。
  
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>查看会议通过 Skype 业务服务器控制面板配置设置
<a name="BKMK_ViewJoinSettings"> </a>

1. 使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2.  打开 Skype 业务服务器的控制面板。
    
3. 在左侧导航栏中，单击“**会议**”，然后单击“**会议配置**”。
    
4. 在“**会议配置**”页上，单击要查看的会议配置。
    
5. 在“**编辑文件筛选器**”中，选中“**显示详细信息**”复选框。
    
    **编辑会议配置-\<策略\>**将打开并显示所选策略的设置。
    
    有关配置设置的详细信息，请参阅[创建会议中业务服务器 2015年的 Skype 的配置设置](create-settings.md)。
    
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>查看会议通过 Skype 业务服务器管理外壳程序的配置设置
<a name="BKMK_ViewJoinSettings"> </a>

若要查看有关所有会议配置设置的信息，可使用 **Get-CsMeetingConfiguration** cmdlet：
  
```
Get-CsMeetingConfiguration
```

此命令会返回类似下面的信息：
  
```
Identity                        : Global
PstnCallersBypassLobby          : True
EnableAssignedConferenceType    : True
DesignateAsPresenter            : Company
AssignedConferenceTypeByDefault : True
AdmitAnonymousUsersByDefault    : True
RequireRoomSystemsAuthorization : False
LogoURL                         :
LegalURL                        :
HelpURL                         :
CustomFooterText                :
AllowConferenceRecording        : True

```

有关详细信息，包括参数的完整列表，请参见[获取 CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps)
  

