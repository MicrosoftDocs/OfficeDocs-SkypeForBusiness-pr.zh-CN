---
title: 查看 Skype for Business 服务器中的会议配置设置
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
ms.assetid: 932c7e2d-6de3-4176-ac6e-ec230f8230f2
description: 摘要：了解如何在 Skype for Business Server 中查看会议配置设置。
ms.openlocfilehash: 858d1a3d786cb9fe3c6b33daaca8667cab2390f8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818453"
---
# <a name="view-meeting-configuration-settings-in-skype-for-business-server"></a>查看 Skype for Business 服务器中的会议配置设置
 
**摘要：** 了解如何在 Skype for Business Server 中查看会议配置设置。
  
可以使用 Skype for Business Server 控制面板或使用 Skype for business Server 命令行管理器查看会议配置设置。
  
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>使用 Skype for Business 服务器控制面板查看会议配置设置
<a name="BKMK_ViewJoinSettings"> </a>

1. 使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2.  打开 "Skype for Business 服务器" 控制面板。
    
3. 在左侧导航栏中，单击“**会议**”，然后单击“**会议配置**”。
    
4. 在“**会议配置**”页上，单击要查看的会议配置。
    
5. 在“**编辑文件筛选器**”中，选中“**显示详细信息**”复选框。
    
    **编辑会议配置- \<策略\> **将打开，显示所选策略的设置。
    
    有关配置设置的详细信息，请参阅[在 Skype For Business 服务器中创建会议配置设置](create-settings.md)。
    
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>使用 Skype for Business Server Management Shell 查看会议配置设置
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

有关详细信息，包括参数的完整列表，请参阅[CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps)。
  

