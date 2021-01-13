---
title: 在 Skype for Business Server 中管理会议加入和离开通知
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
ms.assetid: cb09f9c2-c6dc-4083-b45a-8b6773341373
description: 摘要：了解如何在 Skype for Business Server 中管理会议加入和离开通知。
ms.openlocfilehash: 9ca73d3d32ce03a8119d805b5e7260c0a871eb27
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828102"
---
# <a name="manage-conference-join-and-leave-announcements-in-skype-for-business-server"></a>在 Skype for Business Server 中管理会议加入和离开通知
 
**摘要：** 了解如何在 Skype for Business Server 中管理会议加入和离开通知。
  
当电话拨入用户加入或离开会议时，会议通知应用程序可以通过播放提示音或说其姓名来宣布其进入或退出。 可以使用具有以下参数的 Skype for Business Server 命令行管理程序和 **Set-CsDialinConferencing** cmdlet 更改通知的运行方式：
  
- EnableNameRecording - 确定是否要求匿名参与者在进入会议之前记录其姓名。 （经过身份验证的参与者不会记录他们的姓名，因为将使用他们的显示名称。 ）
    
- EntryExitAnnouncementsEnabledByDefault - 指示默认情况下是打开还是关闭通知。 默认值为"$false"，这意味着默认情况下，参与者加入或离开会议时没有通知。 在安排会议时，会议组织者可以覆盖此设置。
    
- EntryExitAnnouncementsType - 指示参与者加入或离开启用了通知的会议时采取的操作。 默认值为"UseNames"，这意味着在打开通知时有类似如下通知："Ken Myer 已加入会议"。
    
可以在 global 作用域或 site 作用域配置这些设置。在 site 作用域配置的设置的优先于在 global 作用域配置的设置。
   

### <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a>修改会议加入和离开通知行为

1. 以 RTCUniversalServerAdmins 组成员或者 Cs-ServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。
    
2. 启动 Skype for Business Server命令行管理程序：单击"开始"，**单击"所有** 程序"，再单击 **"Skype for Business 2015"，** 然后单击 **"Skype for Business Server 命令行管理程序"。**
    
3. 在命令提示符下，运行以下内容：
    
   ```PowerShell
   Get-CsDialinConferencingConfiguration
   ```

此 cmdlet 检索有关在加入会议时是否要求参与者记录其姓名的信息，以及参与者加入或离开电话拨入式会议时 Skype for Business Server 如何响应的信息。
    
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

有关详细信息，包括语法和参数的完整列表，请参阅[Set-CsDialInConferencingConfiguration。](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps)
  

