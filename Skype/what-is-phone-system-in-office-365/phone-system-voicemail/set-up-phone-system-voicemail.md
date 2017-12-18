---
title: "设置电话系统语音邮件-管理员帮助"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/15/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom: Adm_O365_FullSet
ms.assetid: 9c590873-b014-4df3-9e27-1bb97322a79d
description: "Learn how to set up the phone system (Cloud PBX) voicemail for your Skype for Business users. "
---

# 设置电话系统语音邮件-管理员帮助

> [!IMPORTANT]
> 本文是由机器翻译的，请参阅[免责声明]。
  
本文适用于[关于 Office 365 管理员角色](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)想要在企业版中设置的所有人电话系统语音邮件功能。
  
> [!NOTE]
> 语音邮件系统支持只能在 Exchange 邮箱中放入语音邮件和不支持任何第三方电子邮件系统。回退机制，为电话系统语音邮件可以重新使用 SMTP，这意味着与第三方电子邮件系统上的邮箱的用户将收到不保证的服务运行时间或其他语音邮件功能，例如更改其语音邮件的邮件的邮件发送其问候语和其他设置。 
  
## 仅基于云的环境： 设置电话系统语音邮件

为 Skype for Business Online 和呼叫计划的用户，电话系统语音邮件自动设置并为其分配 **电话系统**许可证和电话号码后，为用户设置。
  
1. 如果电话系统功能未包括在您的计划，您可能需要购买 **电话系统**加载项许可证。您可能需要购买 Exchange Online 的许可证。请参阅[Skype for Business 和 Microsoft 团队许可加载项](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)。
    
2. [如何分配或取消分配 Office 365 商业版适用的用户许可证](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)、[分配 Skype for Business 和 Microsoft 团队合作的用户许可证](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)和 Exchange Online 许可证分配给您的企业内的人员。执行该操作后，他们将能够收到语音邮件 ！
    
3. 语音邮件抄写的支持已添加年 3 月 2017年，并启用默认情况下对所有组织和用户。您可以通过使用 Windows PowerShell，并执行下面的步骤为您的组织中禁用抄写。
    
## 与本地环境的电话系统

有关配置电话系统语音邮件，使用本地调用规划环境是以下信息。
  
1. 如果电话系统功能未包括在您的计划，您可能需要购买 **电话系统**加载项许可证。您还需要购买 Exchange Online 的许可证。请参阅[Skype for Business 和 Microsoft 团队许可加载项](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)。
    
2. [如何分配或取消分配 Office 365 商业版适用的用户许可证](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)、[分配 Skype for Business 和 Microsoft 团队合作的用户许可证](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)和 Exchange Online 许可证分配给您的企业内的人员。
    
3. 按照[配置的 Skype for Business 云连接线版本指南](https://technet.microsoft.com/en-us/library/mt605228.aspx)的 **启用电话系统语音和语音邮件服务的用户** 部分中的说明进行操作。
    
4. 语音邮件抄写的支持已添加年 3 月 2017年，并启用默认情况下对所有组织和用户。您可以通过使用 Windows PowerShell，并执行下面的步骤为您的组织中禁用抄写。
    
5. 您还可以看到[Azure PBX 语音邮件的 Exchange 服务器支持](https://support.microsoft.com/en-us/kb/3195158)若要了解如何配置为具有本地邮箱电话系统用户 Azure 语音邮件的传递。
    
## 设置组织的语音邮件策略

默认情况下为所有组织和用户; 启用语音邮件抄写但是，您可以控制其使用[设置 CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx)和[授予 CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798311.aspx) cmdlet。
  
> [!IMPORTANT]
> 不能创建新策略实例的抄写使用 **New-CsOnlineVoiceMailPolicy** cmdlet，并且您不能删除现有策略实例使用 **Remove-CsOnlineVoiceMailPolicy** cmdlet。
  
您可以为您使用的语音邮件策略的用户管理抄写设置。若要查看所有可用的语音邮件策略实例，可以使用[获取 CsOnlineVoicemailPolicy](https://technet.microsoft.com/en-us/library/mt798311.aspx)[]()cmdlet。
  
 **PS C:\\> Get-CsOnlineVoicemailPolicy**
  
![Get-CsOnlineVoiceMailPolicy results window.](../../images/6cea8310-2d71-4b95-8d36-688472845727.png)
  
### 为组织禁用转录

因为抄写的默认设置是在为您的组织，您可能想要使用[设置 CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx)禁用它。若要执行此操作，运行：
  
```
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### 为用户禁用转录

用户策略之前的组织的默认设置会进行求值。例如，如果为您的所有用户都启用语音邮件抄写，则您可以分配了策略来禁用抄写特定用户使用[授予 CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798309.aspx) cmdlet。
  
要为单个用户禁用转录，请运行：
  
```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> Office 365 中的语音邮件服务缓存语音邮件策略，并每隔 4 小时更新一次缓存。因此，你所作的策略更改最长可能需要 4 小时才能生效。 
  
## 帮助你的用户了解 Skype for Business 语音邮件的功能

我们有培训信息和文章，以帮助您成功与Skype for Business语音邮件的用户。指导他们访问下列文章：
  
- [检查 Skype for Business 语音邮件和选项](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8)： 本文介绍如何在 Skype for Business 语音收听、 更改您的语音邮件问候语、 更改您的语音邮件设置，和收听语音邮件以不同速度。
    
- [Skype for Business 2016 培训](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)
    
## 相关主题

[设置 Skype for Business Online](../../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
[下面是可以在 Office 365 中的电话系统获得](../../what-is-phone-system-in-office-365/here-s-what-you-get-with-phone-system-in-office-365.md)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **机器翻译免责声明**：本文是由无人工介入的计算机系统翻译的。Microsoft 提供机器翻译是为了帮助非英语国家/地区用户方便阅读有关 Microsoft 产品、服务和技术的内容。由于机器翻译的原因，本文可能包含词汇、语法或文法方面的错误。 
  

