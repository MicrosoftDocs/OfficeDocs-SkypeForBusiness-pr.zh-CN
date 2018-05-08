---
title: 设置电话系统的语音邮件
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
description: 'Learn how to set up the phone system (Cloud PBX) voicemail for your Skype for Business users. '
ms.openlocfilehash: 93dd33eefe587c548e346974cc86fe2608b392ec
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="set-up-phone-system-voicemail"></a>设置电话系统的语音邮件

本文适用于[Office 365 管理员](http://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)想要在企业中设置的每个人的电话系统的语音邮件功能。
  
> [!NOTE]
> 电话系统的语音邮件 Exchange 邮箱中仅支持放入的语音邮件消息，并且不支持任何第三方电子邮件系统。 作为一回退机制，电话系统的语音邮件可以重新发送邮件使用 SMTP，这意味着与第三方电子邮件系统上的邮箱的用户将收到与不保证的服务正常运行时间或其他语音邮件功能，如更改其语音邮件消息其问候语和其他设置。 
  
## <a name="cloud-only-environments-set-up-phone-system-voicemail"></a>仅限云环境： 设置电话系统的语音邮件

对于业务联机和调用计划用户 Skype，电话系统的语音邮件是自动设置，然后分配给他们的**电话系统**许可证和电话号码后，为用户设置。
  
1. 如果电话系统功能不包括在您的计划，您可能需要购买附加许可证**电话系统**。 您可能还需要购买 Exchange Online 的许可证。 请参阅[业务和 Microsoft 团队授权加载项的 Skype](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)。
    
2. [分配或删除业务的 Office 365 的许可证](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)，[业务和 Microsoft 团队许可证分配 Skype](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)，以及您企业中的人员的 Exchange Online 许可证。 分配完成后，他们将能够接收语音邮件消息！
    
3. 对语音邮件转录已添加从年 3 月 2017年和支持的所有组织和用户的默认情况下启用。 通过使用 Windows PowerShell 并执行以下步骤，您可以为组织禁用转录。
    
## <a name="phone-system-with-on-premises-environments"></a>内部部署环境与电话系统

有关配置电话系统语音邮件，以使用内部部署调用规划环境中的以下信息。
  
1. 如果电话系统功能不包括在您的计划，您可能需要购买附加许可证**电话系统**。 您还需要购买 Exchange Online 的许可证。 请参阅[业务和 Microsoft 团队授权加载项的 Skype](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)。
    
2. [分配或删除业务的 Office 365 的许可证](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)，[业务和 Microsoft 团队许可证分配 Skype](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)，以及您企业中的人员的 Exchange Online 许可证。
    
3. 按照[配置商务云连接器版指南的 Skype](https://technet.microsoft.com/en-us/library/mt605228.aspx)**为用户启用电话系统语音和语音邮件服务**部分中的说明。
    
4. 对语音邮件转录已添加从年 3 月 2017年和支持的所有组织和用户的默认情况下启用。 通过使用 Windows PowerShell 并执行以下步骤，您可以为组织禁用转录。 
    
5. 您还可以参见[Exchange server 支持的 Azure PBX 语音邮件](https://support.microsoft.com/en-us/kb/3195158)以了解如何配置的电话系统的用户具有内部部署邮箱中的 Azure 语音邮件的传递。
    
## <a name="setting-voicemail-policies-in-your-organization"></a>设置组织的语音邮件策略

默认情况下启用语音邮件转录和转录亵渎隐蔽的所有组织和用户; 默认情况下禁用但是，您可以控制其使用[集 CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx)和[授予 CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798311.aspx) cmdlet。
  
> [!IMPORTANT]
> 无法创建新策略实例转录和转录亵渎屏蔽使用**新建 CsOnlineVoiceMailPolicy** cmdlet，并且您不能删除现有策略实例使用**删除 CsOnlineVoiceMailPolicy** cmdlet.
  
可以使用语音邮件策略为用户管理转录设置。 若要查看所有可用的语音邮件策略实例，可以使用[Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlet。
  
 **PS C:\\> Get-CsOnlineVoicemailPolicy**
  
![Get-CsOnlineVoiceMailPolicy results window.](../../images/6cea8310-2d71-4b95-8d36-688472845727.png)
  
### <a name="turning-off-transcription-for-your-organization"></a>为组织禁用转录

由于转录的默认设置是在您的组织，可能要使用[集 CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx)禁用它。 若要执行此操作，请运行：
  
```
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a>打开您的组织转录亵渎蒙

默认情况下，为组织禁用转录亵渎屏蔽。 如果没有启用它业务要求，您可以使用[集 CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx)屏蔽转录亵渎。 若要执行此操作，请运行：
  
```
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a>为用户禁用转录

用户策略的优先级高于组织默认设置。 例如，如果您的用户的所有已启用语音邮件转录，您可以分配一个策略来禁用转录使用[授予 CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet 为特定用户。
  
要为单个用户禁用转录，请运行：
  
```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

### <a name="turning-on-transcription-profanity-masking-for-a-user"></a>开启转录亵渎隐蔽的用户

若要启用特定用户的转录亵渎遮蔽，您可以分配一个策略来启用转录亵渎屏蔽使用[授予 CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798309.aspx) cmdlet 为特定用户。
  
若要启用转录亵渎屏蔽单个用户，请运行：
  
```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> [!重要信息] Office 365 中的语音邮件服务缓存语音邮件策略，并每隔 4 小时更新一次缓存。因此，你所作的策略更改最长可能需要 4 小时才能生效。 
  
## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a>帮助你的用户了解 Skype for Business 语音邮件的功能

我们有培训信息和文章可帮助您成功与 Skype 的业务语音邮件的用户。 指示他们访问以下文章：
  
- [检查业务语音邮件和选项的 Skype](http://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8)： 这篇文章介绍如何收听语音邮件中的业务的 Skype、 更改语音邮件问候语，更改您的语音邮件设置和收听语音邮件以不同速度。
    
- [Skype for Business 2016 培训](http://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)
    
## <a name="related-topics"></a>相关主题
[设置 Skype for Business Online](../../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

[Office 365 中的电话系统的功能](../../what-is-phone-system-in-office-365/here-s-what-you-get-with-phone-system.md)

  
 