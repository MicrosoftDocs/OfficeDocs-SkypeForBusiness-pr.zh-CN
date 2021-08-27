---
title: 查看会议配置Skype for Business Server
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
ms.assetid: 932c7e2d-6de3-4176-ac6e-ec230f8230f2
description: 摘要：了解如何在会议环境中查看Skype for Business Server。
ms.openlocfilehash: 79a05b35d5bdac952d009445b92c9f1b30883027
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58578816"
---
# <a name="view-meeting-configuration-settings-in-skype-for-business-server"></a>查看会议配置Skype for Business Server
 
**摘要：** 了解如何在会议环境中查看会议Skype for Business Server。
  
可以使用控制面板或命令行管理程序Skype for Business Server会议配置Skype for Business Server设置。
  
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>使用"控制面板"Skype for Business Server会议配置设置
<a name="BKMK_ViewJoinSettings"> </a>

1. 使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。
    
2.  打开Skype for Business Server控制面板"。
    
3. 在左侧导航栏中，单击 **"会议"，** 然后单击"会议 **配置"。**
    
4. 在 **"会议配置"** 页上，单击要查看的会议配置。
    
5. 在 **"编辑文件筛选器**"中，选中" **显示详细信息** "复选框。
    
    **编辑会议配置 \<policy\> -** 随即打开，显示所选策略的设置。
    
    有关配置设置的详细信息，请参阅 Create [meeting configuration settings in Skype for Business Server](create-settings.md)。
    
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>使用命令行管理程序Skype for Business Server会议配置设置
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

有关详细信息，包括参数的完整列表，请参阅[Get-CsMeetingConfiguration。](/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps)
