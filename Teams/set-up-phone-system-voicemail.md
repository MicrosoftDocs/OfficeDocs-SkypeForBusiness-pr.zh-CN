---
title: 设置云语音邮件
author: dstrome
ms.author: dstrome
manager: serdars
ms.reviewer: wasseemh, phans
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
description: '了解如何为用户设置云语音邮件。 '
ms.openlocfilehash: 4ed61a825ce4e583c71f052020692e4478324003
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117060"
---
# <a name="set-up-cloud-voicemail"></a>设置云语音邮件

本文适用于 Microsoft 365 或 Office 365 管理员[](/microsoft-365/admin/add-users/about-admin-roles)，如关于想要为企业中的每个人设置云语音邮件功能管理员角色中所述。

> [!NOTE]
> 云语音邮件仅支持将语音邮件置于 Exchange 邮箱中，并且不支持任何第三方电子邮件系统。 

> [!NOTE]
> 当代理人代表代理人应答呼叫时，通知在云语音邮件中不可用。 用户可以接收未接来电的通知。

## <a name="cloud-only-environments-set-up-cloud-voicemail-for-online-phone-system-users"></a>仅云环境：为联机电话系统用户设置云语音邮件

对于在线电话系统用户，向用户分配电话系统许可证后，将自动为用户 **设置和预配** 云语音邮件。 

> [!NOTE]
> 对于使用本地提供的电话号码的在线 Skype for Business Phone 系统用户，可能需要使用 [Set-CsUser -HostedVoicemail](/powershell/module/skype/set-csuser?view=skype-ps)$True。 

## <a name="set-up-cloud-voicemail-for-exchange-server-mailbox-users"></a>为邮箱用户Exchange Server云语音邮件

以下信息将有关配置云语音邮件以与在线使用电话系统但其邮箱位于 Exchange Server 的用户一Exchange Server。 
  
1. 语音邮件通过 SMTP 通过 Exchange Online Protection 路由传送到用户的 Exchange 邮箱。 若要成功传递这些邮件，请确保 Exchange 连接器在 Exchange 服务器和 Exchange Online Protection 之间正确配置; [使用连接器配置邮件流](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)。 

2. 若要启用语音邮件功能，例如自定义 Skype for Business 客户端中的问候语和可视语音邮件，需要通过 Exchange Web Services 从 Microsoft 365 或 Office 365 连接到 Exchange 服务器邮箱。 若要启用此连接，必须配置在 Exchange 和 Exchange Online 组织之间配置 [OAuth](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)身份验证中所述的新 Exchange Oauth 身份验证协议，或者从 Exchange 2013 CU5 或更高版运行 Exchange 混合向导。 此外，你必须在 Skype for Business Online 和 Exchange Server 之间配置集成和 Oauth，如在 Skype for Business Online 和 Exchange Server 之间配置 [集成和 OAuth 中所述](/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises)。 

## <a name="set-up-cloud-voicemail-for-skype-for-business-server-users"></a>为 Skype for Business Server 用户设置云语音邮件

若要为云语音邮件配置 Skype for Business 服务器用户，请参阅为本地用户规划 [云语音邮件服务](/skypeforbusiness/hybrid/plan-cloud-voicemail)。

## <a name="enabling-protected-voicemail-in-your-organization"></a>在组织中启用受保护的语音邮件

当某人为您的组织中的用户留下语音邮件时，语音邮件作为电子邮件附件传送到用户的邮箱。 使用邮件流规则应用邮件加密，可以防止这些语音邮件转发给其他收件人。 启用受保护的语音邮件后，用户可以通过呼叫进入语音邮件邮箱或在 Outlook、Outlook 网页版或 Outlook for Android 或 iOS 中打开邮件来收听受保护的语音邮件。 在 Skype for Business 或 Microsoft Teams 中无法打开受保护的语音邮件消息。

有关邮件加密的信息，请参阅 [电子邮件加密](/microsoft-365/compliance/email-encryption?view=o365-worldwide)。

若要设置受保护的语音邮件，请执行下列操作：

1. 转到 https://admin.microsoft.com ，使用具有全局管理员权限的帐户登录。
2. 选择 **"全部显示**"，然后转到管理 **中心**  >  **Exchange。**
3. 在 Exchange 管理中心中，选择"**邮件流**  >  **规则"。**
4. 选择 **+** **"添加**"，然后选择 **"对邮件应用 Office 365 邮件加密和权限保护"。**
5. 提供新邮件流规则的名称，然后在"如果应用此规则 **"** 下，选择"邮件 **属性**  >  **包括邮件类型**  >  **""语音邮件"。** 选择"**确定"。**
6. 在 **"执行下列操作"** 下，选择"对邮件应用 **Office 365** 邮件加密和权限保护"，然后选择"选择 **一个"。** 在 **"RMS 模板"** 下，选择 **"不转发"。** 选择 **"确定**"，然后选择"**保存"。**
    > [!NOTE]
    > 如果 **RMS 模板** 列表为空，则需要设置消息加密。 有关设置消息加密的信息，请参阅以下文章：
    > - [设置新的消息加密功能](/microsoft-365/compliance/set-up-new-message-encryption-capabilities?view=o365-worldwide)
    > - [配置和管理 Azure 信息保护的模板](/information-protection/deploy-use/configure-policy-templates)
    > - [电子邮件的"不转发"选项](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)

## <a name="setting-voicemail-policies-in-your-organization"></a>设置组织的语音邮件策略

> [!WARNING]
> 对于 Skype for Business 客户，通过 Microsoft Teams 呼叫策略禁用语音邮件也可能禁用 Skype for Business 用户的语音邮件服务。

默认情况下，为所有组织和用户启用语音邮件转录并禁用转录亵渎屏蔽；但是，你可以使用 [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy) 和 [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Get-CsOnlineVoicemailPolicy) cmdlet 对其进行控制。

您的组织中的用户收到的语音邮件在托管 Microsoft 365 或 Office 365 组织的区域进行转录。 托管租户的区域可能与接收语音邮件的用户所在的区域不同。 若要查看托管租户的区域，请转到"组织配置文件"页，然后单击"[](https://go.microsoft.com/fwlink/p/?linkid=2067339)数据位置"旁边的"查看 **详细信息"。**

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
  
### <a name="turning-off-transcription-for-your-organization"></a>为组织禁用转录

由于组织的听录默认设置为"开"，因此可能需要使用 [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy)禁用它。 为此，请运行：

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a>打开组织的转录亵渎屏蔽

默认情况下，为组织禁用转录亵渎屏蔽。 如果有启用它的业务要求，你可以使用 [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy) 启用转录亵渎屏蔽。 为此，请运行：

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a>为用户禁用转录

用户策略的优先级高于组织默认设置。 例如，如果为所有用户启用了语音邮件转录，则可以通过 [使用 Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy) cmdlet 为特定用户分配禁用转录的策略。

要为单个用户禁用转录，请运行：

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

### <a name="turning-on-transcription-profanity-masking-for-a-user"></a>为用户开启转录亵渎屏蔽

要为特定用户启用转录亵渎屏蔽，你可以使用 [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy) cmdlet 分配一个策略，以便为特定用户启用转录亵渎屏蔽。

要为单个用户启用转录亵渎屏蔽，请运行：

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> Microsoft 365 和 Office 365 中的语音邮件服务每 4 小时缓存一次语音邮件策略并更新缓存。 因此，你所作的策略更改最长可能需要 4 小时才能生效。

## <a name="help-your-users-learn-teams-voicemail-features"></a>帮助用户了解 Teams 语音邮件功能

我们在 Teams 中为用户提供有关管理语音邮件设置和其他呼叫功能的以下信息：

- [在 Teams 中管理通话设置](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)。 本文介绍如何管理所有最终用户 Teams 呼叫功能。 

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a>帮助你的用户了解 Skype for Business 语音邮件的功能

我们提供培训信息和文章来帮助你的用户成功使用 Skype for Business 语音邮件。 指示他们访问以下文章：

- [检查 Skype for Business](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8)语音邮件和选项：本文介绍如何在 Skype for Business 中收听语音邮件、更改语音邮件问候语、更改语音邮件设置以及以不同速度收听语音邮件。

- [Skype for Business 2016 培训](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a>相关主题
[设置 Skype for Business Online](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[电话系统的功能](here-s-what-you-get-with-phone-system.md)

[Skype for Business Server 和 Exchange Server 迁移规划](/SkypeForBusiness/hybrid/plan-um-migration)