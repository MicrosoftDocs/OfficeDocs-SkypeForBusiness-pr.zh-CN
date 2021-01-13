---
title: Skype 会议室系统帐户的会议策略
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: sohailta
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4dd8be28-5156-411b-8ccd-eff7f75cb897
description: 阅读本主题，了解如何为 Skype 会议室系统帐户分配会议策略。
ms.openlocfilehash: 3fb462168bd4121f5feef365f881ed9f02620e25
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812722"
---
# <a name="conferencing-policy-for-skype-room-system-accounts"></a>Skype 会议室系统帐户的会议策略
 
阅读本主题，了解如何为 Skype 会议室系统帐户分配会议策略。
  
## <a name="conferencing-policy-features"></a>会议策略功能

分配给 Skype 会议室系统帐户的会议策略必须具有某些特征。 大多数情况下，Skype 会议室系统客户端会加入安排的会议，因此会议组织者的会议策略将影响会议。 但是，在 Skype for Business Server 中，某些功能取决于参与者的配置。 例如，如果参与者的策略允许最大视频分辨率为 1080p，参与者将在会议中体验此分辨率更高的视频功能，即使组织者的策略不允许此功能。 下表介绍了在组织中为 Skype 会议室系统帐户设置会议策略时应注意的几个此类设置。 
  
|功能  <br/> |值  <br/> |评论  <br/> |
|:-----|:-----|:-----|
|AllowIPAudio  <br/> |TRUE  <br/> |对于 Skype 会议室系统音频，必须为 true  <br/> |
|AllowIPVideo  <br/> |TRUE  <br/> |Skype 会议室系统音频必须在 Skype 会议室系统临时 (白板) 中工作  <br/> |
|AllowMultiView  <br/> |TRUE  <br/> |允许 Skype 会议室系统呈现多视图、多视频流  <br/> |
|AllowParticipantControl  <br/> |TRUE  <br/> |影响 Skype 会议室 (中的) "现在开会"  <br/> |
|AllowAnnotations  <br/> |TRUE  <br/> |影响 Skype 会议室 (中的) "现在开会"  <br/> |
|DisablePowerPointAnnotations  <br/> |FALSE  <br/> |影响 Skype 会议室 (中的) "现在开会"  <br/> |
|AllowUserToScheduleMeetingsWithAppSharing  <br/> |TRUE  <br/> |影响 Skype 会议室 (中的) "现在开会"  <br/> |
|AllowNonEnterpriseVoiceUsersToDialOut  <br/> |FALSE  <br/> |有关帐户是否企业语音 (EV) 是否 (请参阅"为 Skype for Business 启用 Skype 会议室系统帐户"部分)   <br/> |
|AllowAnonymousUsersToDialOut  <br/> |FALSE  <br/> |取决于帐户是否企业语音 (EV) 启用  <br/> |
|AllowAnonymousParticipantsInMeetings  <br/> |TRUE  <br/> |影响 Skype 会议室 (中的) "现在开会"  <br/> |
|AllowExternalUsersToSaveContent  <br/> |TRUE  <br/> |影响 Skype 会议室 (中的) "现在开会"  <br/> |
|AllowExternalUserControl  <br/> |FALSE  <br/> |影响 Skype 会议室 (中的) "现在开会"  <br/> |
|AllowExternalUsersToRecordMeeting  <br/> |FALSE  <br/> |影响 Skype 会议室 (中的) "现在开会"  <br/> |
|AllowPolls  <br/> |TRUE  <br/> |"立即开会" (会议) 会议，但 Skype 会议室系统可以响应会议室前面的屏幕上的投票  <br/> |
|AllowSharedNotes  <br/> |TRUE  <br/> |"立即开会" (会议) 会议，但 Skype 会议室系统可以响应会议室前面的屏幕上的投票  <br/> |
|EnableDialInConferencing  <br/> |TRUE  <br/> |影响 Skype 会议室 (中的) "现在开会"  <br/> |
|EnableAppDesktopSharing  <br/> |桌面  <br/> |影响 Skype 会议室 (中的) "现在开会"  <br/> |
|AllowConferenceRecording  <br/> |FALSE  <br/> |适用于 Skype 会议室系统的 N/A。 如果为 TRUE，则远程方可以录制  <br/> |
|EnableP2PRecording  <br/> |FALSE  <br/> |适用于 Skype 会议室系统的 N/A。 如果为 TRUE，则远程方可以录制  <br/> |
|EnableFileTransfer  <br/> |TRUE  <br/> |无  <br/> |
|EnableP2PFileTransfer  <br/> |TRUE  <br/> |无  <br/> |
|EnableP2PVideo  <br/> |TRUE  <br/> |使 Skype 会议室系统客户端能够参与对等视频会话  <br/> |
|AllowLargeMeetings  <br/> |FALSE  <br/> |无  <br/> |
|EnableDataCollaboration  <br/> |TRUE  <br/> |影响 Skype 会议室 (中的) "现在开会"  <br/> |
|MaxVideoConferenceResolution  <br/> |VGA  <br/> |Skype for Business Server 忽略，Skype 会议室系统使用 HD1080  <br/> |
|MaxMeetingSize  <br/> |250  <br/> |影响 Skype 会议室 (中的) "现在开会"  <br/> |
|AudioBitRateKb  <br/> |200  <br/> |请参阅表末尾的注释\*  <br/> |
|VideoBitRateKb  <br/> |5000  <br/> |这是允许的最大出站视频比特率。 如果以此比特率使用 Round) Table (Skype 会议室系统可以发送一个 1080 流和平移数据。 \*  <br/> |
|AppSharingBitRateKb  <br/> |5000  <br/> |请参阅表末尾的注释\*  <br/> |
|FileTransferBitRateKb  <br/> |5000  <br/> |无  <br/> |
|TotalReceiveVideoBitRateKb  <br/> |20000  <br/> |我们建议你尽可能设置该设置。 有效带宽取决于会议时的网络条件。\*  <br/> |
|EnableMultiViewJoin  <br/> |TRUE  <br/> |对于 Skype 会议室系统，必须为 TRUE 以确保多视图视频流  <br/> |
   
* 有关带宽规划的信息，请参阅媒体 [流量的网络带宽要求](../../plan-your-deployment/network-requirements/network-requirements.md#network-bandwidth-requirements-for-media-traffic)。
  
> [!NOTE]
> 如果 Skype 会议室系统客户端尝试加入由位于 Lync Server 2010 池上的用户组织的计划会议，会议组织者的会议策略可能会阻止 Skype 会议室系统客户端执行协作。 
  
## <a name="meeting-authentication"></a>会议身份验证

Skype 会议室系统在用户使用与会链接加入受限会议时提示用户进行身份验证;例如，已在 Outlook 中配置会议厅选项的会议。 对于自定义会议，此设置始终启用，并且始终提示用户。 但是，对于不受限制的会议，用户可以在不进行身份验证的情况下加入会议。 
  
以下命令使管理员能够要求对所有会议进行身份验证，包括不受限制的会议： 
  
```powershell
Set-CsMeetingConfiguration -RequireRoomSystemsAuthorization $TRUE
```

默认情况下，RequireRoomSystemsAuthorization 为 FALSE。 
  

