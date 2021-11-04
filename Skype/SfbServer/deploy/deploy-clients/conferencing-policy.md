---
title: 会议室系统帐户Skype会议策略
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.reviewer: sohailta
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 4dd8be28-5156-411b-8ccd-eff7f75cb897
description: 阅读本主题，了解如何为会议室系统帐户Skype会议策略。
ms.openlocfilehash: 9e6bab608ab68b3f0e0d5075ae1caf8cb16d4c0b
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60771674"
---
# <a name="conferencing-policy-for-skype-room-system-accounts"></a>会议室系统帐户Skype会议策略
 
阅读本主题，了解如何为会议室系统帐户Skype会议策略。
  
## <a name="conferencing-policy-features"></a>会议策略功能

分配给会议室系统帐户Skype会议策略必须具有某些特征。 大多数情况下，会议室Skype客户端会加入安排的会议，因此会议组织者的会议策略将影响会议。 但是，Skype for Business Server，某些功能取决于参与者的配置。 例如，如果参与者的策略允许最大视频分辨率为 1080p，参与者将在会议中体验此分辨率更高的视频功能，即使组织者的策略不允许该功能。 下表介绍了在组织中为会议室系统帐户设置Skype会议策略时应注意的几个此类设置。 
  
|功能  <br/> |值  <br/> |评论  <br/> |
|:-----|:-----|:-----|
|AllowIPAudio  <br/> |TRUE  <br/> |对于会议室系统Skype必须为 true  <br/> |
|AllowIPVideo  <br/> |TRUE  <br/> |必须为 true，Skype会议室系统音频在会议室系统中的"现在开会 (临时) 白板会话Skype工作  <br/> |
|AllowMultiView  <br/> |TRUE  <br/> |允许Skype系统呈现多视图、多个视频流  <br/> |
|AllowParticipantControl  <br/> |TRUE  <br/> |影响会议室 (中的) "现在开会"Skype白板会话  <br/> |
|AllowAnnotations  <br/> |TRUE  <br/> |影响会议室 (中的) "现在开会"Skype白板会话  <br/> |
|DisablePowerPointAnnotations  <br/> |FALSE  <br/> |影响会议室 (中的) "现在开会"Skype白板会话  <br/> |
|AllowUserToScheduleMeetingsWithAppSharing  <br/> |TRUE  <br/> |影响会议室 (中的) "现在开会"Skype白板会话  <br/> |
|AllowNonEnterpriseVoiceUsersToDialOut  <br/> |FALSE  <br/> |有关帐户是否已启用 EV 企业语音 ()  (请参阅为 SKYPE 会议室系统帐户Skype for Business部分)   <br/> |
|AllowAnonymousUsersToDialOut  <br/> |FALSE  <br/> |取决于帐户是否企业语音 (EV) 启用  <br/> |
|AllowAnonymousParticipantsInMeetings  <br/> |TRUE  <br/> |影响会议室 (中的) "现在开会"Skype白板会话  <br/> |
|AllowExternalUsersToSaveContent  <br/> |TRUE  <br/> |影响会议室 (中的) "现在开会"Skype白板会话  <br/> |
|AllowExternalUserControl  <br/> |FALSE  <br/> |影响会议室 (中的) "现在开会"Skype白板会话  <br/> |
|AllowExternalUsersToRecordMeeting  <br/> |FALSE  <br/> |影响会议室 (中的) "现在开会"Skype白板会话  <br/> |
|AllowPolls  <br/> |TRUE  <br/> |"立即开会" (会议) 会议，Skype会议室系统可以响应会议室前面的屏幕上的投票  <br/> |
|AllowSharedNotes  <br/> |TRUE  <br/> |"立即开会" (会议) 会议，Skype会议室系统可以响应会议室前面的屏幕上的投票  <br/> |
|EnableDialInConferencing  <br/> |TRUE  <br/> |影响会议室 (中的) "现在开会"Skype白板会话  <br/> |
|EnableAppDesktopSharing  <br/> |桌面  <br/> |影响会议室 (中的) "现在开会"Skype白板会话  <br/> |
|AllowConferenceRecording  <br/> |FALSE  <br/> |会议室系统Skype/A。 如果为 TRUE，则远程方可以录制  <br/> |
|EnableP2PRecording  <br/> |FALSE  <br/> |会议室系统Skype/A。 如果为 TRUE，则远程方可以录制  <br/> |
|EnableFileTransfer  <br/> |TRUE  <br/> |不适用  <br/> |
|EnableP2PFileTransfer  <br/> |TRUE  <br/> |不适用  <br/> |
|EnableP2PVideo  <br/> |TRUE  <br/> |允许Skype会议室系统客户端参与对等视频会话  <br/> |
|AllowLargeMeetings  <br/> |FALSE  <br/> |不适用  <br/> |
|EnableDataCollaboration  <br/> |TRUE  <br/> |影响会议室 (中的) "现在开会"Skype白板会话  <br/> |
|MaxVideoConferenceResolution  <br/> |VGA  <br/> |被设备Skype for Business Server，Skype系统使用 HD1080  <br/> |
|MaxMeetingSize  <br/> |250  <br/> |影响会议室 (中的) "现在开会"Skype白板会话  <br/> |
|AudioBitRateKb  <br/> |200  <br/> |请参阅表格末尾的注释\*  <br/> |
|VideoBitRateKb  <br/> |5000  <br/> |这是允许的最大出站视频比特率。 Skype如果以此比特率使用 RoundTable (，会议室系统可以发送一个 1080 流和 pano) 。 \*  <br/> |
|AppSharingBitRateKb  <br/> |5000  <br/> |请参阅表格末尾的注释\*  <br/> |
|FileTransferBitRateKb  <br/> |5000  <br/> |不适用  <br/> |
|TotalReceiveVideoBitRateKb  <br/> |20000  <br/> |我们建议你尽可能设置该设置。 有效带宽取决于会议时的网络条件。\*  <br/> |
|EnableMultiViewJoin  <br/> |TRUE  <br/> |对于会议室系统Skype必须为 TRUE，以确保多视图视频流  <br/> |
   
* 有关带宽规划的信息，请参阅 [媒体流量的网络带宽要求](../../plan-your-deployment/network-requirements/network-requirements.md#network-bandwidth-requirements-for-media-traffic)。
  
> [!NOTE]
> 如果 Skype 会议室系统客户端尝试加入由位于 Lync Server 2010 池上的用户组织的计划会议，会议组织者的会议策略可能会阻止 Skype 会议室系统客户端执行协作。 
  
## <a name="meeting-authentication"></a>会议身份验证

Skype会议室系统在用户使用与会链接加入受限制的会议时提示用户进行身份验证;例如，已在"会议"中配置了会议厅选项Outlook。 对于自定义会议，此设置始终启用，并且始终提示用户。 但是，对于不受限制的会议，用户无需身份验证即可加入会议。 
  
以下命令使管理员能够要求对所有会议进行身份验证，包括不受限制的会议： 
  
```powershell
Set-CsMeetingConfiguration -RequireRoomSystemsAuthorization $TRUE
```

默认情况下，RequireRoomSystemsAuthorization 为 FALSE。 
  

