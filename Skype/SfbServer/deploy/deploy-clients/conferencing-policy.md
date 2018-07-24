---
title: Skype 会议室系统帐户的会议策略
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4dd8be28-5156-411b-8ccd-eff7f75cb897
description: 阅读本主题，了解如何为 Skype 会议室系统帐户分配会议策略。
ms.openlocfilehash: a9eb05c8e29a3db216bc74e5e016c2c6a8413a33
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "20973421"
---
# <a name="conferencing-policy-for-skype-room-system-accounts"></a>Skype 会议室系统帐户的会议策略
 
阅读本主题，了解如何为 Skype 会议室系统帐户分配会议策略。
  
## <a name="conferencing-policy-features"></a>会议策略功能

会议策略分配给 Skype 会议室系统帐户必须具有下列特点。 大多数情况下的 Skype 会议室 System 客户端加入预定的会议，并因此会议组织者的会议策略将影响会议。 但是，在业务服务器 Skype，某些功能依赖参与者的配置。 例如，如果参与者的策略允许 1080p 的最大视频分辨率，参与者会遇到此更高分辨率视频功能在会议中的，即使组织者的策略不允许其一样。 下表介绍了其应注意的设置为在组织中的 Skype 会议室系统帐户的会议策略时的多个此类设置。 
  
|功能  <br/> |值  <br/> |注释  <br/> |
|:-----|:-----|:-----|
|AllowIPAudio  <br/> |TRUE  <br/> |必须满足的 Skype 会议室系统音频  <br/> |
|AllowIPVideo  <br/> |TRUE  <br/> |必须满足 Skype 会议室系统音频工作中的立即开会 （临时） 白板会话中 Skype 会议室系统  <br/> |
|AllowMultiView  <br/> |TRUE  <br/> |允许 Skype 会议室系统呈现多视图，多个视频流  <br/> |
|AllowParticipantControl  <br/> |TRUE  <br/> |影响立即开会 （临时） 白板会话 Skype 会议室系统  <br/> |
|AllowAnnotations  <br/> |TRUE  <br/> |影响立即开会 （临时） 白板会话 Skype 会议室系统  <br/> |
|DisablePowerPointAnnotations  <br/> |FALSE  <br/> |影响立即开会 （临时） 白板会话 Skype 会议室系统  <br/> |
|AllowUserToScheduleMeetingsWithAppSharing  <br/> |TRUE  <br/> |影响立即开会 （临时） 白板会话 Skype 会议室系统  <br/> |
|AllowNonEnterpriseVoiceUsersToDialOut  <br/> |FALSE  <br/> |取决于该帐户是企业语音 (EV) 启用 （请参阅启用 Skype 会议室系统帐户的 Skype 业务部分）  <br/> |
|AllowAnonymousUsersToDialOut  <br/> |FALSE  <br/> |取决于帐户是否已启用企业语音 (EV)  <br/> |
|AllowAnonymousParticipantsInMeetings  <br/> |TRUE  <br/> |影响立即开会 （临时） 白板会话 Skype 会议室系统  <br/> |
|AllowExternalUsersToSaveContent  <br/> |TRUE  <br/> |影响立即开会 （临时） 白板会话 Skype 会议室系统  <br/> |
|AllowExternalUserControl  <br/> |FALSE  <br/> |影响立即开会 （临时） 白板会话 Skype 会议室系统  <br/> |
|AllowExternalUsersToRecordMeeting  <br/> |FALSE  <br/> |影响立即开会 （临时） 白板会话 Skype 会议室系统  <br/> |
|AllowPolls  <br/> |TRUE  <br/> |N/A 立即开会 （临时） 会议，但 Skype 会议室系统可以在前面的聊天室在屏幕上的投票响应  <br/> |
|AllowSharedNotes  <br/> |TRUE  <br/> |N/A 立即开会 （临时） 会议，但 Skype 会议室系统可以在前面的聊天室在屏幕上的投票响应  <br/> |
|EnableDialInConferencing  <br/> |TRUE  <br/> |影响立即开会 （临时） 白板会话 Skype 会议室系统  <br/> |
|EnableAppDesktopSharing  <br/> |桌面打印机  <br/> |影响立即开会 （临时） 白板会话 Skype 会议室系统  <br/> |
|AllowConferenceRecording  <br/> |FALSE  <br/> |Skype 会议室系统 n/A。 如果设为 TRUE，则远程方可以录制  <br/> |
|EnableP2PRecording  <br/> |FALSE  <br/> |Skype 会议室系统 n/A。 如果设为 TRUE，则远程方可以录制  <br/> |
|EnableFileTransfer  <br/> |TRUE  <br/> |不适用  <br/> |
|EnableP2PFileTransfer  <br/> |TRUE  <br/> |不适用  <br/> |
|EnableP2PVideo  <br/> |TRUE  <br/> |允许 Skype 会议室系统客户端参加对等视频会话  <br/> |
|AllowLargeMeetings  <br/> |FALSE  <br/> |不适用  <br/> |
|EnableDataCollaboration  <br/> |TRUE  <br/> |影响立即开会 （临时） 白板会话 Skype 会议室系统  <br/> |
|MaxVideoConferenceResolution  <br/> |VGA  <br/> |忽略 Skype 业务服务器，Skype 会议室系统使用 HD1080  <br/> |
|MaxMeetingSize  <br/> |250  <br/> |影响立即开会 （临时） 白板会话 Skype 会议室系统  <br/> |
|AudioBitRateKb  <br/> |200  <br/> |请参阅表末尾的注释\*  <br/> |
|VideoBitRateKb  <br/> |5000  <br/> |这是允许的最大出站视频比特率。 Skype 会议室系统可以发送一个 1080 stream 以及将全景 （如果使用 RoundTable） 在此比特率。 \*  <br/> |
|AppSharingBitRateKb  <br/> |5000  <br/> |请参阅表末尾的注释\*  <br/> |
|FileTransferBitRateKb  <br/> |5000  <br/> |不适用  <br/> |
|TotalReceiveVideoBitRateKb  <br/> |20000  <br/> |我们建议您设置此尽可能高。 有效的带宽在会议时间取决于网络条件。\*  <br/> |
|EnableMultiViewJoin  <br/> |TRUE  <br/> |必须为 TRUE 的 Skype 会议室系统，以确保多视图视频流  <br/> |
   
* 有关带宽规划的信息，请参阅[媒体流量的网络带宽要求](../../plan-your-deployment/network-requirements/network-requirements.md#network-bandwidth-requirements-for-media-traffic)。
  
> [!NOTE]
> 如果尝试加入计划的会议在 Lync Server 2010 池上驻留的用户组织的 Skype 会议室 System 客户端，会议组织者的会议策略会阻止的 Skype 会议室 System 客户端执行协作。 
  
## <a name="meeting-authentication"></a>会议身份验证

Skype 会议室系统会提示用户进行身份验证，使用会议时加入链接加入受限的会议;例如，对于哪些会议厅选项已配置在 Outlook 中会议。 对于自定义会议，此设置始终启用，用户始终会收到提示。 然而，对于不受限制的会议，用户无需身份验证就可以加入会议。 
  
通过以下命令，管理员能够要求对所有会议进行身份验证，包括不受限制的会议在内： 
  
```
Set-CsMeetingConfiguration -RequireRoomSystemsAuthorization $TRUE
```

默认情况下，RequireRoomSystemsAuthorization 设置为 False。 
  

