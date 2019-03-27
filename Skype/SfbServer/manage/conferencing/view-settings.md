---
title: 查看会议中 Skype 业务服务器的配置设置
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 932c7e2d-6de3-4176-ac6e-ec230f8230f2
description: 摘要： 了解如何查看会议中 Skype 业务服务器的配置设置。
ms.openlocfilehash: d7ef617050b31bd85732ee4a30d0faaed41f50d1
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899396"
---
# <a name="view-meeting-configuration-settings-in-skype-for-business-server"></a>查看会议中 Skype 业务服务器的配置设置
 
**摘要：** 了解如何查看会议中 Skype 业务服务器的配置设置。
  
您可以查看会议配置设置，使用的业务 Server Control Panel Skype 或使用 Skype 业务 Server Management Shell。
  
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>查看使用适用于业务 Server Control Panel Skype 会议配置设置
<a name="BKMK_ViewJoinSettings"> </a>

1. 使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2.  打开 Skype 业务 Server Control Panel。
    
3. 在左侧导航栏中，单击“**会议**”，然后单击“**会议配置**”。
    
4. 在“**会议配置**”页上，单击要查看的会议配置。
    
5. 在“**编辑文件筛选器**”中，选中“**显示详细信息**”复选框。
    
    **编辑会议配置-\<策略\>** 打开显示所选策略的设置。
    
    有关配置设置的详细信息，请参阅[创建会议配置设置中的业务服务器 Skype](create-settings.md)。
    
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>查看会议配置设置，使用 Skype 业务 Server 命令行管理程序
<a name="BKMK_ViewJoinSettings"> </a>

若要查看有关所有会议配置设置的信息，可使用 **Get-CsMeetingConfiguration** cmdlet：
  
```
Get-CsMeetingConfiguration
```

此命令会返回类似下面的信息：
  
<pre>
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
</pre>

有关详细信息，包括完成参数的列表，请参阅[Get-csmeetingconfiguration](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps)。
  

