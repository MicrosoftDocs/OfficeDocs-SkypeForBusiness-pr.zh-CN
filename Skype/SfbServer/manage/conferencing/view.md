---
title: 在 Skype for Business Server 中查看会议策略
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
ms.assetid: c1c0976e-2bfb-475b-9255-ed6b093d8798
description: 摘要：了解如何在 Skype for Business Server 中查看会议策略。
ms.openlocfilehash: afe86f0a77e73c3fa7bf96339c4865598a7bc609
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119401"
---
# <a name="view-conferencing-policies-in-skype-for-business-server"></a>在 Skype for Business Server 中查看会议策略
 
**摘要：** 了解如何在 Skype for Business Server 中查看会议策略。
  
可以使用 Skype for Business Server 控制面板或 Skype for Business Server 命令行管理程序查看会议策略。
  
## <a name="view-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>使用 Skype for Business Server 控制面板查看会议策略

1. 使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。
    
2.  打开 Skype for Business Server 控制面板。
    
3. 在左侧导航栏中，单击 **"会议"，** 然后单击"**会议策略"。**
    
4. 在“会议策略”页面上，双击您要查看的会议策略。
    
5. 在 **"编辑文件筛选器**"中，选中" **显示详细信息** "复选框。
    
    **编辑会议策略 - \<policy\>** 随即打开，显示所选策略的设置。
    
    有关配置设置的详细信息，请参阅在 Skype for Business Server 中创建 [会议策略](create-policies.md)。
    
## <a name="view-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>使用 Skype for Business Server 命令行管理程序查看会议策略

若要查看会议策略，请使用 **Get-CsConferencingPolicy** cmdlet：
  
```PowerShell
Get-CsConferencingPolicy
```

此 cmdlet 返回以下信息：
  
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

有关详细信息，包括完整的语法说明和参数列表，请参阅 [Get-CsConferencingPolicy](/powershell/module/skype/get-csconferencingpolicy?view=skype-ps)。
