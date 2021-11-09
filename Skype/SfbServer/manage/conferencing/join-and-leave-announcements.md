---
title: 管理会议加入和离开Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: cb09f9c2-c6dc-4083-b45a-8b6773341373
description: 摘要：了解如何管理会议加入和离开Skype for Business Server。
ms.openlocfilehash: ee624ee347bb52f4bbdf4fbfae42f5303c8b6a54
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60837664"
---
# <a name="manage-conference-join-and-leave-announcements-in-skype-for-business-server"></a>管理会议加入和离开Skype for Business Server
 
**摘要：** 了解如何管理会议加入和离开Skype for Business Server。
  
当拨入用户加入或离开会议时，会议公告应用程序可以通过播放提示音或说姓名来宣布其进入或退出。 您可以使用命令行管理程序和 **Set-CsDialinConferencing** cmdlet 和 Skype for Business Server Cmdlet 更改通知的运行方式：
  
- EnableNameRecording - 确定是否要求匿名参与者在进入会议之前记录其姓名。 （经过身份验证的参与者不会记录他们的姓名，因为将使用他们的显示名称。 ）
    
- EntryExitAnnouncementsEnabledByDefault - 指示默认情况下是打开还是关闭通知。 默认值为"$false"，这意味着默认情况下，参与者加入或离开会议时没有通知。 在安排会议时，会议组织者可以覆盖此设置。
    
- EntryExitAnnouncementsType - 指示参与者加入或离开启用了通知的会议时采取的操作。 默认值为"UseNames"，这意味着有类似于以下通知："Ken Myer 已加入会议"（当通知打开时）。
    
可以在 global 作用域或 site 作用域配置这些设置。在 site 作用域配置的设置的优先于在 global 作用域配置的设置。
   

### <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a>修改会议加入和离开通知行为

1. 以 RTCUniversalServerAdmins 组成员或者 Cs-ServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。
    
2. 启动命令行Skype for Business Server：单击"开始"，单击"所有程序"，单击 **"Skype for Business 2015"，** 然后单击"Skype for Business Server **命令行管理程序"。**
    
3. 在命令提示符下，运行以下内容：
    
   ```PowerShell
   Get-CsDialinConferencingConfiguration
   ```

此 cmdlet 检索有关在加入会议时是否需要参与者记录其姓名的信息，以及当参与者加入或离开电话拨入式会议时 Skype for Business Server 如何响应。
    
4. 在命令提示符下，运行以下内容：
    
   ```PowerShell
   Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
   [-EnableNameRecording <$true | $false>]
   [-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
   [-EntryExitAnnouncementsType <UseNames | ToneOnly]
   ```

在下面的示例中，在站点范围为 Redmond 配置设置。 通知已打开，但在参与者加入会议时系统未提示他们说出姓名。 参与者进入或离开会议时播放提示音：
  
```PowerShell
Set-CsDialinConferencingConfiguration -Identity site:Redmond
-EnableNameRecording $false
-EntryExitAnnouncementsEnabledByDefault $true
-EntryExitAnnouncementsType ToneOnly
```

有关详细信息，包括语法和完整参数列表，请参阅 [Set-CsDialInConferencingConfiguration](/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps)。
