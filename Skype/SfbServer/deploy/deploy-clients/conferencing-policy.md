---
title: Skype 会议室系统帐户的会议策略
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/4/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4dd8be28-5156-411b-8ccd-eff7f75cb897
description: 阅读本主题，了解如何为 Skype 会议室系统帐户分配会议策略。
ms.openlocfilehash: 73ab8f48bc399f4478b0a9c22aceb68d7a54a11b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="conferencing-policy-for-skype-room-system-accounts"></a>Skype 会议室系统帐户的会议策略
 
阅读本主题，了解如何为 Skype 会议室系统帐户分配会议策略。
  
## <a name="conferencing-policy-features"></a>会议策略功能

会议策略分配到 Skype 的空间系统帐户必须具有某些特征。 大多数情况下，Skype 的空间系统客户端加入计划的会议，并因此为会议组织者的会议策略会影响会议。 但是，在 Skype 业务服务器，某些功能取决于参与者的配置。 例如，如果参与者的策略允许 1080p 的视频分辨率，参与者将在会议中的此高分辨率视频功能即使遇到组织者的策略不允许它。 下表描述了几个应注意的会议组织中的 Skype 的空间系统帐户策略设置时此类设置。 
  
||||
|:-----|:-----|:-----|
|功能  <br/> |值  <br/> |注释  <br/> |
|AllowIPAudio  <br/> |TRUE  <br/> |必须满足 Skype 的空间系统音频  <br/> |
|AllowIPVideo  <br/> |TRUE  <br/> |必须满足 Skype 的空间系统音频工作中立即开会 (ad hoc) 白板会话中 Skype 的空间系统  <br/> |
|AllowMultiView  <br/> |TRUE  <br/> |让 Skype 的空间系统呈现多视图中，多个视频流  <br/> |
|AllowParticipantControl  <br/> |TRUE  <br/> |影响在 Skype 的空间系统立即开会 (ad hoc) 白板会话  <br/> |
|AllowAnnotations  <br/> |TRUE  <br/> |影响在 Skype 的空间系统立即开会 (ad hoc) 白板会话  <br/> |
|DisablePowerPointAnnotations  <br/> |FALSE  <br/> |影响在 Skype 的空间系统立即开会 (ad hoc) 白板会话  <br/> |
|AllowUserToScheduleMeetingsWithAppSharing  <br/> |TRUE  <br/> |影响在 Skype 的空间系统立即开会 (ad hoc) 白板会话  <br/> |
|AllowNonEnterpriseVoiceUsersToDialOut  <br/> |FALSE  <br/> |取决于客户是否企业语音 (EV) 启用 （请参阅启用 Skype 的空间系统帐户时为 Skype 业务部分）  <br/> |
|AllowAnonymousUsersToDialOut  <br/> |FALSE  <br/> |取决于帐户是否已启用企业语音 (EV)  <br/> |
|AllowAnonymousParticipantsInMeetings  <br/> |TRUE  <br/> |影响在 Skype 的空间系统立即开会 (ad hoc) 白板会话  <br/> |
|AllowExternalUsersToSaveContent  <br/> |TRUE  <br/> |影响在 Skype 的空间系统立即开会 (ad hoc) 白板会话  <br/> |
|AllowExternalUserControl  <br/> |FALSE  <br/> |影响在 Skype 的空间系统立即开会 (ad hoc) 白板会话  <br/> |
|AllowExternalUsersToRecordMeeting  <br/> |FALSE  <br/> |影响在 Skype 的空间系统立即开会 (ad hoc) 白板会话  <br/> |
|AllowPolls  <br/> |TRUE  <br/> |立即开会 （临时） 会议，在不适用，但 Skype 的空间系统可以响应在前面的房间在屏幕上的轮询  <br/> |
|AllowSharedNotes  <br/> |TRUE  <br/> |立即开会 （临时） 会议，在不适用，但 Skype 的空间系统可以响应在前面的房间在屏幕上的轮询  <br/> |
|EnableDialInConferencing  <br/> |TRUE  <br/> |影响在 Skype 的空间系统立即开会 (ad hoc) 白板会话  <br/> |
|EnableAppDesktopSharing  <br/> |桌面打印机  <br/> |影响在 Skype 的空间系统立即开会 (ad hoc) 白板会话  <br/> |
|AllowConferenceRecording  <br/> |FALSE  <br/> |Skype 的空间系统的 n/A。 如果设为 TRUE，则远程方可以录制  <br/> |
|EnableP2PRecording  <br/> |FALSE  <br/> |Skype 的空间系统的 n/A。 如果设为 TRUE，则远程方可以录制  <br/> |
|EnableFileTransfer  <br/> |TRUE  <br/> |不适用  <br/> |
|EnableP2PFileTransfer  <br/> |TRUE  <br/> |不适用  <br/> |
|EnableP2PVideo  <br/> |TRUE  <br/> |Skype 的空间系统客户机参与对等视频会话  <br/> |
|AllowLargeMeetings  <br/> |FALSE  <br/> |不适用  <br/> |
|EnableDataCollaboration  <br/> |TRUE  <br/> |影响在 Skype 的空间系统立即开会 (ad hoc) 白板会话  <br/> |
|MaxVideoConferenceResolution  <br/> |VGA  <br/> |忽略由 Skype 业务服务器，Skype 的空间系统使用 HD1080  <br/> |
|MaxMeetingSize  <br/> |250  <br/> |影响在 Skype 的空间系统立即开会 (ad hoc) 白板会话  <br/> |
|AudioBitRateKb  <br/> |200  <br/> |请参阅表末尾的注释\*  <br/> |
|VideoBitRateKb  <br/> |5000  <br/> |这是允许的最大出站视频比特率。 Skype 的空间系统可以发送一个 1080年流动以及全景 （如果使用圆桌会议） 速度比特率。 \*  <br/> |
|AppSharingBitRateKb  <br/> |5000  <br/> |请参阅表末尾的注释\*  <br/> |
|FileTransferBitRateKb  <br/> |5000  <br/> |不适用  <br/> |
|TotalReceiveVideoBitRateKb  <br/> |20000  <br/> |我们建议，将此参数设置尽可能高。 有效的带宽在会议的时间取决于网络条件。\*  <br/> |
|EnableMultiViewJoin  <br/> |TRUE  <br/> |值必须为 TRUE 的 Skype 的空间系统，以确保多视图视频流  <br/> |
   
* 有关带宽规划信息，请参阅[媒体流量的网络带宽要求](https://technet.microsoft.com/en-us/library/jj688118%28v=ocs.15%29.aspx)。
  
> [!NOTE]
> 如果 Skype 的空间系统客户端试图加入计划位于 Lync Server 2010 池的用户组织的会议，会议组织者的会议策略无法阻止 Skype 的空间系统客户端执行协作。 
  
## <a name="meeting-authentication"></a>会议身份验证

Skype 的空间系统会提示用户进行身份验证，使用会议时联接链接加入受限的会议;例如，对于哪些会议厅选项已配置 Outlook 中的会议。 对于自定义会议，此设置始终启用，用户始终会收到提示。 然而，对于不受限制的会议，用户无需身份验证就可以加入会议。 
  
通过以下命令，管理员能够要求对所有会议进行身份验证，包括不受限制的会议在内： 
  
```
Set-CsMeetingConfiguration -RequireRoomSystemsAuthorization $TRUE
```

默认情况下，RequireRoomSystemsAuthorization 设置为 False。 
  

