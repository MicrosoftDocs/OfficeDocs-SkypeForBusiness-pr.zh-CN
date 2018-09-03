---
title: 设置电话系统语音邮件
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.topic: article
ms.assetid: 9c590873-b014-4df3-9e27-1bb97322a79d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Phone System
description: '了解如何为 Skype for Business 用户设置电话系统（云 PBX）语音邮件。 '
ms.openlocfilehash: d311c6d0c0f6965d81f557c2080a9bb331de557b
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/28/2018
ms.locfileid: "23252886"
---
# <a name="set-up-phone-system-voicemail"></a>设置电话系统语音邮件

本文适用于想要为企业中的每位用户设置电话系统语音邮件功能的 [Office 365 管理员](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)。

> [!NOTE]
> 电话系统语音邮件仅支持在 Exchange 邮箱中存储语音邮件消息，不支持任何第三方电子邮件系统。 作为一种回退机制，电话系统语音邮件可以使用 SMTP 重新发送消息，这意味着使用第三方电子邮件系统的邮箱的用户将收到其语音邮件消息，但服务运行时间和其他语音邮件功能（例如更改其问候语和其他设置）没有保证。

## <a name="cloud-only-environments-set-up-phone-system-voicemail"></a>仅限云环境：设置电话系统语音邮件

对于 Skype for Business Online 和通话套餐用户，在你为其分配 **电话系统** 许可证和电话号码后，系统自动为他们设置和配置电话系统语音邮件。

1. 如果你的套餐不包含电话系统功能，你可能需要购买 **电话系统** 加载项许可证。 你可能还需要购买 Exchange Online 许可证。 请参阅 [Skype for Business 和 Microsoft Teams 加载项授权](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)。

2. 为企业员工[分配或删除 Office 365 商业版许可证](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)、[分配 Skype for Business 和 Microsoft Teams 许可证](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)以及 Exchange Online 许可证。 操作完成后，他们将能够接收语音邮件消息！

3. 从 2017 年 3 月开始增加了对语音邮件转录的支持，默认情况下为所有组织和用户启用此功能。 通过使用 Windows PowerShell 并执行以下步骤，你可以为组织禁用转录。

## <a name="phone-system-with-on-premises-environments"></a>本地环境的电话系统

下面是有关配置电话系统语音邮件以用于本地通话套餐环境的信息。

1. 如果你的套餐不包含电话系统功能，你可能需要购买 **电话系统** 加载项许可证。 你可能还需要购买 Exchange Online 许可证。 请参阅 [Skype for Business 和 Microsoft Teams 加载项授权](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)。

2. 为企业员工[分配或删除 Office 365 商业版许可证](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)、[分配 Skype for Business 和 Microsoft Teams 许可证](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)以及 Exchange Online 许可证。

3. 按照 [配置商业云连接器 Edition 指南](https://technet.microsoft.com/en-us/library/mt605228.aspx) 的 **为用户启用电话系统语音和语音邮件服务** 部分的说明操作。

4. 从 2017 年 3 月开始增加了对语音邮件转录的支持，默认情况下为所有组织和用户启用此功能。 通过使用 Windows PowerShell 并执行以下步骤，你可以为组织禁用转录。

5. 你还可以参阅 [Exchange Server 的 azure PBX 的语音邮件支持](https://support.microsoft.com/en-us/kb/3195158)，了解如何为拥有本地邮箱的电话系统用户配置 Azure 语音邮件消息的传递方式。

## <a name="setting-voicemail-policies-in-your-organization"></a>设置组织的语音邮件策略

默认情况下，为所有组织和用户启用语音邮件转录并禁用转录亵渎屏蔽；但是，你可以使用 [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx) 和 [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798311.aspx) cmdlet 对其进行控制。

> [!IMPORTANT]
> 无法使用 **New-CsOnlineVoiceMailPolicy** cmdlet 为转录和转录亵渎屏蔽创建新的策略实例，且无法使用 **Remove-CsOnlineVoiceMailPolicy** cmdlet 删除现有策略实例。

可以使用语音邮件策略为用户管理转录设置。 要查看所有可用的语音邮件策略实例，可以使用 [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlet。

 **PS C:\\> Get-CsOnlineVoicemailPolicy**

![Get-CsOnlineVoiceMailPolic 结果窗口。](../../images/6cea8310-2d71-4b95-8d36-688472845727.png)

### <a name="turning-off-transcription-for-your-organization"></a>为组织禁用转录

由于默认情况下为组织启用转录，你可能会希望通过使用 [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx) 来禁用此功能。 要执行此操作，请运行：

```
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a>打开组织的转录亵渎屏蔽

默认情况下，为组织禁用转录亵渎屏蔽。 如果有启用它的业务要求，你可以使用 [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx) 启用转录亵渎屏蔽。 要执行此操作，请运行：

```
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a>为用户禁用转录

用户策略的优先级高于组织默认设置。 例如，如果为所有用户启用了语音邮件转录，你可以使用 [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet 分配一个策略，以便为特定用户禁用转录。

要为单个用户禁用转录，请运行：

```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

### <a name="turning-on-transcription-profanity-masking-for-a-user"></a>为用户开启转录亵渎屏蔽

要为特定用户启用转录亵渎屏蔽，你可以使用 [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798309.aspx) cmdlet 分配一个策略，以便为特定用户启用转录亵渎屏蔽。

要为单个用户启用转录亵渎屏蔽，请运行：

```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> [!重要信息] Office 365 中的语音邮件服务缓存语音邮件策略，并每隔 4 小时更新一次缓存。因此，你所作的策略更改最长可能需要 4 小时才能生效。

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a>帮助你的用户了解 Skype for Business 语音邮件的功能

我们拥有培训信息和文章，可帮助你的用户成功使用 Skype for Business 语音邮件。 指示他们访问以下文章：

- [检查 Skype for Business 语音邮件和选项](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8)：本文介绍如何在 Skype for Business 中收听语音邮件、更改语音邮件问候语、更改语音邮件设置并以不同速度收听语音邮件。

- [Skype for Business 2016 培训](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a>相关主题
[设置 Skype for Business Online](../../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

[Office 365 中的电话系统的功能](../../what-is-phone-system-in-office-365/here-s-what-you-get-with-phone-system.md)


