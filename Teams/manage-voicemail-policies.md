---
title: 管理语音邮件策略
author: dstrome
ms.author: dstrome
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.assetid: 9c590873-b014-4df3-9e27-1bb97322a79d
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
description: 管理用户的语音邮件策略。
ms.openlocfilehash: 213908183c0d1dc608626272c0ea8aa5af308aff
ms.sourcegitcommit: 8ad05b37c0b714adb069bc2503e88366ab75c57d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/07/2021
ms.locfileid: "52796887"
---
# <a name="setting-voicemail-policies-in-your-organization"></a>设置组织的语音邮件策略

> [!WARNING]
> 对于Skype for Business，通过语音信箱呼叫Microsoft Teams禁用语音邮件可能也会为你的Skype for Business禁用语音邮件服务。

默认情况下，为所有组织和用户启用语音邮件转录并禁用转录亵渎屏蔽；但是，你可以使用 [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy) 和 [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Get-CsOnlineVoicemailPolicy) cmdlet 对其进行控制。

您的组织中的用户收到的语音邮件转录在托管您的组织或Microsoft 365 Office 365区域。 托管租户的区域可能与接收语音邮件的用户所在的区域不同。 若要查看托管租户的区域，请转到"组织配置文件"页，然后单击"[](https://go.microsoft.com/fwlink/p/?linkid=2067339)数据位置"旁边的"查看 **详细信息"。**

> [!IMPORTANT]
> 不能使用 **New-CsOnlineVoiceMailPolicy** cmdlet 为听录和听录亵渎内容屏蔽创建新的策略实例，并且不能使用 **Remove-CsOnlineVoiceMailPolicy** cmdlet 删除现有策略实例。

可以使用语音邮件策略为用户管理转录设置。 若要查看所有可用的语音邮件策略实例，可以使用 [Get-CsOnlineVoicemailPolicy](/powershell/module/skype/Get-CsOnlineVoicemailPolicy) cmdlet。

```PowerShell
PS C:\> Get-CsOnlineVoicemailPolicy


Identity                            : Global
EnableTranscription                 : True
ShareData                           : Defer
EnableTranscriptionProfanityMasking : False
EnableEditingCallAnswerRulesSetting : True
MaximumRecordingLength              : 00:05:00
EnableTranscriptionTranslation      : True

Identity                            : Tag:Default
EnableTranscription                 : True
ShareData                           : Defer
EnableTranscriptionProfanityMasking : False
EnableEditingCallAnswerRulesSetting : True
MaximumRecordingLength              : 00:05:00
EnableTranscriptionTranslation      : True

Identity                            : Tag:TranscriptionProfanityMaskingEnabled
EnableTranscription                 : True
ShareData                           : Defer
EnableTranscriptionProfanityMasking : True
EnableEditingCallAnswerRulesSetting : True
MaximumRecordingLength              : 00:05:00
EnableTranscriptionTranslation      : True

Identity                            : Tag:TranscriptionDisabled
EnableTranscription                 : False
ShareData                           : Defer
EnableTranscriptionProfanityMasking : False
EnableEditingCallAnswerRulesSetting : True
MaximumRecordingLength              : 00:05:00
EnableTranscriptionTranslation      : True
```
  
## <a name="turning-off-transcription-for-your-organization"></a>为组织禁用转录

由于组织的听录默认设置为"开"，因此可能需要使用 [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy)禁用它。 为此，请运行：

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

## <a name="turning-on-transcription-profanity-masking-for-your-organization"></a>打开组织的转录亵渎屏蔽

默认情况下，为组织禁用转录亵渎屏蔽。 如果有启用它的业务要求，你可以使用 [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy) 启用转录亵渎屏蔽。 为此，请运行：

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

## <a name="turning-off-transcription-for-a-user"></a>为用户禁用转录

用户策略的优先级高于组织默认设置。 例如，如果为所有用户启用了语音邮件转录，则可以通过 [使用 Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy) cmdlet 为特定用户分配禁用转录的策略。

要为单个用户禁用转录，请运行：

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

## <a name="turning-on-transcription-profanity-masking-for-a-user"></a>为用户开启转录亵渎屏蔽

要为特定用户启用转录亵渎屏蔽，你可以使用 [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy) cmdlet 分配一个策略，以便为特定用户启用转录亵渎屏蔽。

要为单个用户启用转录亵渎屏蔽，请运行：

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> 语音信箱和语音Microsoft 365 Office 365缓存语音邮件策略，并每隔 6 小时更新一次缓存。 因此，你所做的更改最多可能需要 6 小时才能应用。
