---
title: 更改问候语和电子邮件的默认语言
author: dstrome
ms.author: dstrome
manager: serdars
ms.reviewer: jenstr
ms.topic: article
ms.assetid: 820c3892-1b7e-47d3-ae8d-6e27e7cbcf38
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
- seo-marvel-mar2020
description: 了解如何设置Microsoft Teams和Skype for Business以使用组织默认语音邮件问候语的另一种语言。
ms.openlocfilehash: 5e486e94470fd6303d132fdaa9c23b0ca6f65b98
ms.sourcegitcommit: 4435ac0efcb95e4e5e1f21289e46761e79482ab5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2022
ms.locfileid: "65624086"
---
# <a name="change-the-default-language-for-greetings-and-emails"></a>更改问候语和电子邮件的默认语言

云语音邮件使用各种语言设置播放问候语、生成听录翻译和生成语音邮件。 默认情况下，可以在租户级别、策略或给定用户上单独指定语言设置。

## <a name="greetings"></a>问候
向离开语音邮件的呼叫者播放问候语，可以是以下类型：

- 系统问候语
- 被调用的用户录制的自定义问候语
- 在被调用的用户上指定的自定义文本转语音问候语

用于播放系统问候语的语言是优先级顺序，即分配给用户的联机语音邮件策略中指定的主要和辅助提示语言、为用户指定的首选语言或默认租户语言。

自定义和外出问候语由用户使用用户选择的语言进行记录。

如果用户或租户管理员为用户指定了自定义文本转语音问候语，则用于生成语音的语言是与文本转语音问候一起指定的 PromptLanguage。

仅当没有为用户录制自定义问候时，才使用自定义文本转语音问候语。

## <a name="transcription"></a>转录
如果被调用用户的联机语音邮件策略启用，云语音邮件将尝试转录呼叫方留下的语音邮件。 它将使用语音检测来了解音频内容中使用的语言，并尽可能使用检测到的语言转录内容。

## <a name="transcription-translation"></a>听录翻译
如果被调用用户的联机语音邮件策略启用，云语音邮件将翻译转录的语音邮件。 它将从语音检测期间检测到的语言按优先顺序转换为为用户指定的首选语言或默认租户语言。

## <a name="voicemail-message-template"></a>语音邮件模板
云语音邮件将根据为用户指定的首选语言或默认租户语言的优先顺序，使用语言模板生成语音邮件。

## <a name="setting-the-preferred-language-for-a-user"></a>为用户设置首选语言
可以在Azure Active Directory或本地 Active Directory中使用 PowerShell 为用户设置首选语言。 有关详细信息，请参阅[如何为Microsoft 365或Office 365设置语言和区域设置](/office365/troubleshoot/access-management/set-language-and-region)。

用户可以在登录后通过自己的设置更改自己的首选语言。 有关详细信息，请参阅 [Microsoft 365 for Business 中更改显示语言和时区](https://support.office.com/article/change-your-display-language-and-time-zone-in-microsoft-365-for-business-6f238bff-5252-441e-b32b-655d5d85d15b?ui=en-US&rs=en-US&ad=US)

## <a name="change-the-system-language-for-everyone-in-your-organization"></a>更改组织内所有用户的系统语言

1. 使用 [全局管理员](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) 帐户 [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home)登录。

2. 在Microsoft 365 管理中心中，选择 **设置** > **Org settingsOrganization** >  **配置文件**。
3. 选择 **组织信息**。
4. 从“**首选语言**”列表中为组织中的所有用户选择语言。
5. 选择“**保存**”。

**对你可用的语言取决于组织所在的位置**。 例如，如果你的组织位于美国，你可以将默认语言设置为英语或西班牙语。 如果你的组织位于加拿大，你可以在英语和法语之间选择。

## <a name="supported-languages-in-cloud-voicemail"></a>云语音邮件中支持的语言
有关云语音邮件Microsoft Teams和Skype for Business支持的语言列表，[请参阅云语音邮件支持的语言](languages-for-voicemail-greetings-and-messages.md)。
  

## <a name="custom-greeting-recorded-by-a-user"></a>用户录制的自定义问候语
用户可以记录自己的自定义和外出自定义问候语。 请参阅[Teams桌面客户端设置](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)，[并检查Skype for Business语音邮件和选项](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8)。

## <a name="custom-text-to-speech-greeting-specified-for-a-user"></a>为用户指定的自定义文本转语音问候语
租户管理员可以使用 [Set-CsOnlineVoicemailUserSettings](/powershell/module/skype/set-csonlinevoicemailusersettings) cmdlet 为用户指定自定义文本转语音问候语和提示语言。

## <a name="custom-text-to-speech-greeting-specified-by-a-user"></a>用户指定的自定义文本转语音问候语
用户可以指定自己的自定义文本转语音问候语和用于问候语的语言。 对于Microsoft Teams - 用户可以从[Teams桌面客户端设置](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)更改其语音邮件问候语。 对于Skype for Business - [https://mysettings.lync.com/voicemail](https://mysettings.lync.com/voicemail) 在 **“提示语言**”下选择新语言。 


## <a name="related-articles"></a>相关文章

[Set-CsOnlineVoicemailUserSettings](/powershell/module/skype/set-csonlinevoicemailusersettings)

[Get-CsOnlineVoicemailUserSettings](/powershell/module/skype/get-csonlinevoicemailusersettings)

[Set-CsOnlineVoicemailPolicy](/powershell/module/skype/set-csonlinevoicemailpolicy)

[Get-CsOnlineVoicemailPolicy](/powershell/module/skype/get-csonlinevoicemailpolicy)
