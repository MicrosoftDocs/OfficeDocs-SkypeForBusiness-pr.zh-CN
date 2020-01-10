---
title: Skype 会议室系统帐户的会议策略
ms.author: v-lanac
author: lanachin
manager: serdars
ms.reviewer: sohailta
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4dd8be28-5156-411b-8ccd-eff7f75cb897
description: 阅读本主题，了解如何为 Skype 会议室系统帐户分配会议策略。
ms.openlocfilehash: e235ac84b92f770ae16eec3bd99511e4beea8871
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003542"
---
# <a name="conferencing-policy-for-skype-room-system-accounts"></a>Skype 会议室系统帐户的会议策略
 
阅读本主题，了解如何为 Skype 会议室系统帐户分配会议策略。
  
## <a name="conferencing-policy-features"></a>会议策略功能

分配给 Skype 房间系统帐户的会议策略必须具有特定的特征。 大多数情况下，Skype 会议室系统客户加入一个计划会议，因此会议组织者的会议策略将影响会议。 但是，在 Skype for Business 服务器中，某些功能取决于参与者的配置。 例如，如果参与者的策略允许最高视频分辨率为1080p，参与者将在会议中体验此更高分辨率视频功能，即使组织者的策略不允许。 下表介绍了在为组织中的 Skype 会议室系统帐户设置会议策略时应注意的几个设置。 
  
|功能  <br/> |值  <br/> |注释  <br/> |
|:-----|:-----|:-----|
|AllowIPAudio  <br/> |是  <br/> |对于 Skype 会议室系统音频，必须为 true  <br/> |
|AllowIPVideo  <br/> |是  <br/> |必须为 true 才能使 Skype 会议室系统音频在 Skype 会议室系统中的 "立即开会" （临时）白板会话中工作  <br/> |
|AllowMultiView  <br/> |是  <br/> |允许 Skype 会议室系统呈现多视图、多个视频流  <br/> |
|AllowParticipantControl  <br/> |是  <br/> |影响 Skype 会议室系统中的 "立即开会" （临时）白板会话  <br/> |
|AllowAnnotations  <br/> |是  <br/> |影响 Skype 会议室系统中的 "立即开会" （临时）白板会话  <br/> |
|DisablePowerPointAnnotations  <br/> |否  <br/> |影响 Skype 会议室系统中的 "立即开会" （临时）白板会话  <br/> |
|AllowUserToScheduleMeetingsWithAppSharing  <br/> |是  <br/> |影响 Skype 会议室系统中的 "立即开会" （临时）白板会话  <br/> |
|AllowNonEnterpriseVoiceUsersToDialOut  <br/> |否  <br/> |取决于帐户是否已启用企业语音（EV）（请参阅为 Skype for business 启用 Skype 会议室系统帐户）  <br/> |
|AllowAnonymousUsersToDialOut  <br/> |否  <br/> |取决于帐户是否已启用企业语音 (EV)  <br/> |
|AllowAnonymousParticipantsInMeetings  <br/> |是  <br/> |影响 Skype 会议室系统中的 "立即开会" （临时）白板会话  <br/> |
|AllowExternalUsersToSaveContent  <br/> |是  <br/> |影响 Skype 会议室系统中的 "立即开会" （临时）白板会话  <br/> |
|AllowExternalUserControl  <br/> |否  <br/> |影响 Skype 会议室系统中的 "立即开会" （临时）白板会话  <br/> |
|AllowExternalUsersToRecordMeeting  <br/> |否  <br/> |影响 Skype 会议室系统中的 "立即开会" （临时）白板会话  <br/> |
|AllowPolls  <br/> |是  <br/> |N/A 在 "立即开会" （临时）会议中，但 Skype 会议室系统可以在会议室前面的屏幕上响应投票  <br/> |
|AllowSharedNotes  <br/> |是  <br/> |N/A 在 "立即开会" （临时）会议中，但 Skype 会议室系统可以在会议室前面的屏幕上响应投票  <br/> |
|EnableDialInConferencing  <br/> |是  <br/> |影响 Skype 会议室系统中的 "立即开会" （临时）白板会话  <br/> |
|EnableAppDesktopSharing  <br/> |桌面打印机  <br/> |影响 Skype 会议室系统中的 "立即开会" （临时）白板会话  <br/> |
|AllowConferenceRecording  <br/> |否  <br/> |适用于 Skype 会议室系统的 N/A。 如果设为 TRUE，则远程方可以录制  <br/> |
|EnableP2PRecording  <br/> |否  <br/> |适用于 Skype 会议室系统的 N/A。 如果设为 TRUE，则远程方可以录制  <br/> |
|EnableFileTransfer  <br/> |TRUE  <br/> |不适用  <br/> |
|EnableP2PFileTransfer  <br/> |TRUE  <br/> |不适用  <br/> |
|EnableP2PVideo  <br/> |是  <br/> |使 Skype 会议室系统客户可以参与对等视频会话  <br/> |
|AllowLargeMeetings  <br/> |FALSE  <br/> |不适用  <br/> |
|EnableDataCollaboration  <br/> |TRUE  <br/> |影响 Skype 会议室系统中的 "立即开会" （临时）白板会话  <br/> |
|MaxVideoConferenceResolution  <br/> |VGA  <br/> |Skype for business Server 已忽略，Skype 会议室系统使用 HD1080  <br/> |
|MaxMeetingSize  <br/> |250  <br/> |影响 Skype 会议室系统中的 "立即开会" （临时）白板会话  <br/> |
|AudioBitRateKb  <br/> |200  <br/> |请参阅表格末尾的注释\*  <br/> |
|VideoBitRateKB  <br/> |5000  <br/> |这是允许的最大出站视频比特率。 Skype 会议室系统可以发送 1 1080 流以及 pano （如果使用的是圆桌会议），按此位费率收费。 \*  <br/> |
|AppSharingBitRateKb  <br/> |5000  <br/> |请参阅表格末尾的注释\*  <br/> |
|FileTransferBitRateKb  <br/> |5000  <br/> |不适用  <br/> |
|TotalReceiveVideoBitRateKb  <br/> |20000  <br/> |我们建议您尽可能地将此设置为 "高"。 有效带宽取决于会议时的网络条件。\*  <br/> |
|EnableMultiViewJoin  <br/> |TRUE  <br/> |对于 Skype 会议室系统必须成立才能确保多视图视频流  <br/> |
   
* 有关带宽规划的信息，请参阅[媒体流量的网络带宽要求](../../plan-your-deployment/network-requirements/network-requirements.md#network-bandwidth-requirements-for-media-traffic)。
  
> [!NOTE]
> 如果 Skype 会议室系统客户尝试加入由驻留在 Lync Server 2010 池中的用户组织的计划会议，则会议组织者的会议策略可以阻止 Skype 会议室系统客户执行协作。 
  
## <a name="meeting-authentication"></a>会议身份验证

Skype 会议室系统在用户使用会议加入链接加入受限会议时提示用户进行身份验证;例如，在 Outlook 中配置了哪些会议厅选项的会议。 对于自定义会议，此设置始终启用，用户始终会收到提示。 然而，对于不受限制的会议，用户无需身份验证就可以加入会议。 
  
通过以下命令，管理员能够要求对所有会议进行身份验证，包括不受限制的会议在内： 
  
```powershell
Set-CsMeetingConfiguration -RequireRoomSystemsAuthorization $TRUE
```

默认情况下，RequireRoomSystemsAuthorization 设置为 False。 
  

