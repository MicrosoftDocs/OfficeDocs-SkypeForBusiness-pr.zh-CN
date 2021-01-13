---
title: 在 Skype for Business Server 中查看会议配置设置
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 932c7e2d-6de3-4176-ac6e-ec230f8230f2
description: 摘要：了解如何在 Skype for Business Server 中查看会议配置设置。
ms.openlocfilehash: e30543c566775d38e20e2103c4cc0f41278c1020
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827922"
---
# <a name="view-meeting-configuration-settings-in-skype-for-business-server"></a>在 Skype for Business Server 中查看会议配置设置
 
**摘要：** 了解如何在 Skype for Business Server 中查看会议配置设置。
  
可以使用 Skype for Business Server 控制面板或 Skype for Business Server 命令行管理程序查看会议配置设置。
  
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>使用 Skype for Business Server 控制面板查看会议配置设置
<a name="BKMK_ViewJoinSettings"> </a>

1. 使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。
    
2.  打开 Skype for Business Server 控制面板。
    
3. 在左侧导航栏中，单击 **"会议"，** 然后单击"**会议配置"。**
    
4. 在 **"会议配置** "页上，单击要查看的会议配置。
    
5. 在 **"编辑文件筛选器**"中，选中" **显示详细信息"** 复选框。
    
    **编辑会议配置 \<policy\> -** 打开，显示所选策略的设置。
    
    有关配置设置的详细信息，请参阅在 Skype for Business Server 中创建 [会议配置设置](create-settings.md)。
    
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>使用 Skype for Business Server 命令行管理程序查看会议配置设置
<a name="BKMK_ViewJoinSettings"> </a>

若要查看有关所有会议配置设置的信息，请使用 **Get-CsMeetingConfiguration** cmdlet：
  
```
Get-CsMeetingConfiguration
```

此命令将返回与以下内容类似的信息：
  
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

有关详细信息，包括参数的完整列表，请参阅[Get-CsMeetingConfiguration。](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps)
  

