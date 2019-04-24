---
title: 查看会议策略中的业务服务器 Skype
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1c0976e-2bfb-475b-9255-ed6b093d8798
description: 摘要： 了解如何为业务服务器在 Skype 中查看会议策略。
ms.openlocfilehash: 034de4e8d1a5d1a4a89589d3f6361d22e5a783be
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32197868"
---
# <a name="view-conferencing-policies-in-skype-for-business-server"></a>查看会议策略中的业务服务器 Skype
 
**摘要：** 了解如何为业务服务器在 Skype 中查看会议策略。
  
使用适用于业务 Server Control Panel Skype 或使用 Skype 业务 Server 命令行管理程序，您可以查看会议策略。
  
## <a name="view-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>使用适用于业务 Server Control Panel Skype 查看会议策略

1. 使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2.  打开 Skype 业务 Server Control Panel。
    
3. 在左侧导航栏中，单击“**会议**”，然后单击“**会议策略**”。
    
4. 在“**会议策略**”页面上，双击你要查看的会议策略。
    
5. 在“**编辑文件筛选器**”中，选中“**显示详细信息**”复选框。
    
    **编辑会议策略-\<策略\>** 打开显示所选策略的设置。
    
    有关配置设置的详细信息，请参阅[Skype 业务服务器中的创建会议策略](create-policies.md)。
    
## <a name="view-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>使用 Skype 业务 Server 命令行管理程序查看会议策略

若要查看会议策略，请使用 **Get-CsConferencingPolicy** cmdlet：
  
```
Get-CsConferencingPolicy
```

该 cmdlet 将返回类似如下的信息：
  
<pre>
Identity                                  : Global
AllowIPAudio                              : True
AllowIPVideo                              : True
AllowMultiView                            : True
Description                               :
AllowParticipantControl                   : True
AllowAnnotations                          : True
DisablePowerPointAnnotations              : False
AllowUserToScheduleMeetingsWithAppSharing : True
AllowNonEnterpriseVoiceUsersToDialOut     : False
AllowAnonymousUsersToDialOut              : False
AllowAnonymousParticipantsInMeetings      : True
AllowExternalUsersToSaveContent           : True
AllowExternalUserControl                  : False
AllowExternalUsersToRecordMeeting         : False
AllowPolls                                : True
AllowSharedNotes                          : True
EnableDialInConferencing                  : True
EnableAppDesktopSharing                   : Desktop
AllowConferenceRecording                  : False
EnableP2PRecording                        : False
EnableFileTransfer                        : True
EnableP2PFileTransfer                     : True
EnableP2PVideo                            : True
AllowLargeMeetings                        : False
EnableDataCollaboration                   : True
MaxVideoConferenceResolution              : VGA
MaxMeetingSize                            : 250
AudioBitRateKb                            : 200
VideoBitRateKb                            : 50000
AppSharingBitRateKb                       : 50000
FileTransferBitRateKb                     : 50000
TotalReceiveVideoBitRateKb                : 6000
EnableMultiViewJoin                       : True
</pre>

有关详细信息，包括完整语法说明和参数的列表，，请参阅[Get-csconferencingpolicy](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps)。
  

