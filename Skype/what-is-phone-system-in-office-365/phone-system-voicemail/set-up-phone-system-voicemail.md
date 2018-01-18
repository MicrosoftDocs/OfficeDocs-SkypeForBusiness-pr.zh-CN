---
title: "设置电话系统语音邮件"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 9c590873-b014-4df3-9e27-1bb97322a79d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Phone System
- Strat_SB_PSTN
description: 'Learn how to set up the phone system (Cloud PBX) voicemail for your Skype for Business users. '
ms.openlocfilehash: 7d4ad9fa310ee8b90b813bfe949401c602c6a2f2
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/15/2017
---
# <a name="set-up-phone-system-voicemail"></a>设置电话系统语音邮件

本文是针对[Office 365 管理](http://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)者想要在业务的每个人设置了电话系统的语音邮件功能。
  
> [!NOTE]
> 电话系统语音邮件支持仅在 Exchange 邮箱中放入的语音邮件消息，并不支持所有第三方电子邮件系统。 作为一种回退机制，电话系统语音邮件可以重新发送邮件使用 SMTP，这意味着有一个第三方电子邮件系统上的邮箱的用户将收到与无保证的服务的正常运行时间或其他语音邮件功能，例如更改其语音邮件消息他们问候和其他设置。 
  
## <a name="cloud-only-environments-set-up-phone-system-voicemail"></a>仅云环境： 设置电话系统语音邮件

为业务联机并调用计划用户的 Skype，电话系统语音邮件自动设置和分配给他们的**电话系统**许可证及电话号码后为用户提供。
  
1. 如果电话系统功能不包含在您的计划，可能需要购买附加许可证**电话系统**。 您可能还需要购买 Exchange Online 的许可证。 请参阅[附加业务和 Microsoft 小组授权的 Skype](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)。
    
2. [分配或删除业务的 Office 365 的许可证](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)、[业务和 Microsoft 小组许可证分配 Skype](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)和 Exchange Online 许可证给在您的业务的人。 做到这一点后，他们将能够接收语音邮件消息 ！
    
3. 语音邮件抄写的支持已添加 3 月 2017 年和所有组织和用户的默认启用的。 通过使用 Windows PowerShell 并执行以下步骤，您可以为您的组织中禁用抄写。
    
## <a name="phone-system-with-on-premises-environments"></a>电话系统与内部部署环境

以下信息是关于配置电话系统语音邮件使用内部调用计划环境。
  
1. 如果电话系统功能不包含在您的计划，可能需要购买附加许可证**电话系统**。 您还需要购买一个 Exchange Online 的许可证。 请参阅[附加业务和 Microsoft 小组授权的 Skype](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)。
    
2. [分配或删除业务的 Office 365 的许可证](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)、[业务和 Microsoft 小组许可证分配 Skype](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)和 Exchange Online 许可证给在您的业务的人。
    
3. 按照[商务云连接器版指南配置 Skype](https://technet.microsoft.com/en-us/library/mt605228.aspx)的**用户语音电话系统和语音邮件服务启用**部分中的说明进行操作。
    
4. 语音邮件抄写的支持已添加 3 月 2017 年和所有组织和用户的默认启用的。 通过使用 Windows PowerShell 并执行以下步骤，您可以为您的组织中禁用抄写。 
    
5. 您还可以查看[Azure PBX 语音邮件的 Exchange Server 支持](https://support.microsoft.com/en-us/kb/3195158)以了解如何配置电话系统用户拥有本地邮箱的 Azure 的语音邮件消息的传递。
    
## <a name="setting-voicemail-policies-in-your-organization"></a>设置组织的语音邮件策略

语音邮件抄写是默认启用的所有组织和用户;但是，您可以通过[设置 CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx)和[授予 CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798311.aspx) cmdlet 控制它。
  
> [!IMPORTANT]
> 不能创建使用**New CsOnlineVoiceMailPolicy** cmdlet，抄写新建策略实例，您不能删除现有策略实例使用**删除 CsOnlineVoiceMailPolicy** cmdlet。
  
您可以为您的用户使用语音邮件策略管理抄写设置。 若要查看所有可用的语音邮件策略实例，您可以使用[Get CsOnlineVoicemailPolicy](https://technet.microsoft.com/en-us/library/mt798311.aspx) cmdlet。
  
 **PS C:\\> Get-CsOnlineVoicemailPolicy**
  
![Get-CsOnlineVoiceMailPolicy results window.](../../images/6cea8310-2d71-4b95-8d36-688472845727.png)
  
### <a name="turning-off-transcription-for-your-organization"></a>为组织禁用转录

由于抄写的默认设置是在为您的组织，您可以通过[设置 CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx)禁用它。 若要执行此操作，请运行：
  
```
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-off-transcription-for-a-user"></a>为用户禁用转录

用户策略被评估之前组织的默认设置。 例如，如果为所有用户都启用了语音邮件抄写，可以分配一个策略以禁用对特定用户使用[授予 CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798309.aspx) cmdlet 的抄写。
  
要为单个用户禁用转录，请运行：
  
```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> [!重要信息] Office 365 中的语音邮件服务缓存语音邮件策略，并每隔 4 小时更新一次缓存。因此，你所作的策略更改最长可能需要 4 小时才能生效。 
  
## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a>帮助你的用户了解 Skype for Business 语音邮件的功能

我们必须培训信息和文章，以帮助用户能成功与 Skype 业务语音邮件。 其指向下列文章：
  
- [检查业务语音邮件和选项的 Skype](http://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8)： 这篇文章解释了如何收听语音邮件中业务的 Skype、 更改您的语音邮件问候语、 更改您的语音邮件设置和收听语音邮件以不同的速度。
    
- [Skype for Business 2016 培训](http://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)
    
## <a name="related-topics"></a>相关主题
[设置 Skype for Business Online](../../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

[以下是您所获得的与 Office 365 中的电话系统](../../what-is-phone-system-in-office-365/here-s-what-you-get-with-phone-system.md)
