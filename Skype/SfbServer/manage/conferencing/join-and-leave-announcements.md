---
title: 管理会议加入和离开通知中 Skype 业务服务器
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cb09f9c2-c6dc-4083-b45a-8b6773341373
description: 摘要： 了解如何管理会议加入和离开通知中 Skype 业务服务器。
ms.openlocfilehash: 33c20319142608f38451a547687bc1bc9eae47d1
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25371586"
---
# <a name="manage-conference-join-and-leave-announcements-in-skype-for-business-server"></a>管理会议加入和离开通知中 Skype 业务服务器
 
**摘要：** 了解如何管理会议加入和离开通知中 Skype 业务服务器。
  
电话拨入式用户加入或离开会议时, 的会议通知应用程序可以宣布其进入或退出播放提示音，或反映其名称。 您可以更改通知使用的业务 Server 命令行管理程序和**设置 CsDialinConferencing** cmdlet 与以下参数 Skype 的工作方式：
  
- EnableNameRecording - 确定在匿名参与者进入会议之前是否要求参与者记录其姓名。默认值为“$true”，即系统会提示匿名参与者在加入会议时说出其姓名。（经过身份验证的参与者不会记录他们的姓名，因为将使用他们的显示名称。）
    
- EntryExitAnnouncementsEnabledByDefault - 指示默认打开还是关闭通知。默认值为“$false”，即默认情况下，在参与者加入或离开会议时没有通知。会议组织者在安排会议时可以覆盖此设置。
    
- EntryExitAnnouncementsType - 指示参与者加入或离开启用了通知的会议时将执行的操作。默认值为“UseNames”，即有通知，类似于：“Ken Myer 已加入会议”（如果已打开通知）。
    
可以在 global 作用域或 site 作用域配置这些设置。在 site 作用域配置的设置的优先于在 global 作用域配置的设置。
   

### <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a>修改会议加入和离开通知行为

1. 以  RTCUniversalServerAdmins  组成员或者  Cs-ServerAdministrator  或  CsAdministrator  角色成员的身份登录计算机。
    
2. 启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。
    
3. 在命令提示符下，运行以下内容：
    
   ```
   Get-CsDialinConferencingConfiguration
   ```

此 cmdlet 检索有关参与者是否需要记录其姓名，加入会议时和 Skype 业务服务器的参与者加入或离开电话拨入式会议时的响应方式的信息。
    
4. 在命令提示符下，运行以下内容：
    
   ```
   Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
   [-EnableNameRecording <$true | $false>]
   [-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
   [-EntryExitAnnouncementsType <UseNames | ToneOnly]
   ```

在以下示例中，在 site 作用域为 Redmond 配置设置。通知已打开，但在参与者加入会议时系统未提示他们说出姓名。参与者进入或离开会议时将播放提示音：
  
```
Set-CsDialinConferencingConfiguration -Identity site:Redmond
-EnableNameRecording $false
-EntryExitAnnouncementsEnabledByDefault $true
-EntryExitAnnouncementsType ToneOnly
```

有关详细信息，包括语法和参数的完整列表，请参阅[Set-csdialinconferencingconfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps)。
  

