---
title: 设置云语音邮件
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: wasseemh, phans
ms.topic: article
ms.assetid: 9c590873-b014-4df3-9e27-1bb97322a79d
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: '了解如何为用户设置云语音邮件。 '
ms.openlocfilehash: 3f8729c9737bcbf0e7731ac61b38d56d708e15dc
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32204791"
---
# <a name="set-up-cloud-voicemail"></a>设置云语音邮件

本文适用于[Office 365 管理员](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)想要在企业中设置的所有人云语音邮件功能。

> [!NOTE]
> 云语音邮件 Exchange 邮箱中仅支持放入的语音邮件和不支持任何第三方电子邮件系统。 

## <a name="cloud-only-environments-set-up-cloud-voicemail"></a>仅限云环境： 将云语音邮件设置

对于业务联机和调用计划用户 Skype，云语音邮件是自动设置，然后分配给他们的**电话系统**许可证和电话号码后，为用户设置。
  
1. 如果电话系统功能不包括在您的计划，您可能需要购买附加许可证**电话系统**。 您可能还需要购买 Exchange Online 的许可证。 请参阅[Microsoft 团队加载项授权](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。
    
2. [分配或删除业务的 Office 365 的许可证](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)，[分配的 Microsoft 团队许可证](assign-teams-licenses.md)，以及您企业中的人员的 Exchange Online 许可证。 分配完成后，他们将能够接收语音邮件消息！
    
3. 对语音邮件转录已添加从年 3 月 2017年和支持的所有组织和用户的默认情况下启用。 通过使用 Windows PowerShell 并执行以下步骤，你可以为组织禁用转录。

## <a name="phone-system-with-on-premises-environments"></a>本地环境的电话系统

有关配置云语音邮件，以使用内部部署调用规划环境中的以下信息。
  
1. 如果电话系统功能不包括在您的计划，您可能需要购买附加许可证**电话系统**。 您还需要购买 Exchange Online 的许可证。 请参阅[Microsoft 团队加载项授权](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。
    
2. [分配或删除业务的 Office 365 的许可证](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)，[分配的 Microsoft 团队许可证](assign-teams-licenses.md)，以及您企业中的人员的 Exchange Online 许可证。
    
3. 按照说明匹配本地 PSTN 呼叫的用户部署的解决方案。 对于云连接器 Edition，请按照[商务云连接器版指南配置 Skype](https://technet.microsoft.com/library/mt605228.aspx)的**启用用户电话系统的语音和语音邮件服务**部分中的说明。 对于与 Skype 的业务服务器呼叫 PSTN，按照[为本地的企业语音用户启用](https://docs.microsoft.com/en-us/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-the-users-for-enterprise-voice-on-premises)。 团队直接路由，请按照[配置直接](https://docs.microsoft.com/en-us/microsoftteams/direct-routing-configure#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail)路由**配置的电话号码并启用企业语音和语音邮件**部分。

4. 对语音邮件转录已添加从年 3 月 2017年和支持的所有组织和用户的默认情况下启用。 通过使用 Windows PowerShell 并执行以下步骤，你可以为组织禁用转录。

5. 语音邮件消息传送到通过 SMTP 通过 Exchange Online Protection 路由的用户的 Exchange 邮箱。 若要启用这些邮件成功传递，请确保您的 Exchange 服务器和 Exchange Online Protection 之间正确配置了 Exchange Connectors。 [使用连接器配置邮件流](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)。

6. 若要启用语音邮件功能，如业务客户端中自定义问候语和 Skype 中的可视化语音邮件，不需要从 Office 365 连接到 Exchange 服务器邮箱通过 Exchange Web 服务。 若要启用此连接必须配置新的 Exchange Oauth 身份验证协议介绍在[Exchange 和 Exchange Online 组织之间配置 OAuth 身份验证](https://technet.microsoft.com/en-us/library/dn594521(v=exchg.150).aspx) 

> [!NOTE]
> Exchange 混合向导运行从 Exchange 2013 CU5 或更高版本将自动处理步骤 5 和 6 中的要求。 

## <a name="setting-voicemail-policies-in-your-organization"></a>设置组织的语音邮件策略

默认情况下，为所有组织和用户启用语音邮件转录并禁用转录亵渎屏蔽；但是，你可以使用 [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) 和 [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlet 对其进行控制。

> [!IMPORTANT]
> 无法创建新策略实例转录和转录亵渎屏蔽使用**新建 CsOnlineVoiceMailPolicy** cmdlet，并且您不能删除现有策略实例使用**删除 CsOnlineVoiceMailPolicy** cmdlet.

可以使用语音邮件策略为用户管理转录设置。 若要查看所有可用的语音邮件策略实例，可以使用[Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlet。

 **PS C:\\> Get-CsOnlineVoicemailPolicy**
  
![Get-CsOnlineVoiceMailPolic 结果窗口。](media/6cea8310-2d71-4b95-8d36-688472845727.png)
  
### <a name="turning-off-transcription-for-your-organization"></a>为组织禁用转录

由于转录的默认设置是在您的组织，可能要使用[集 CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx)禁用它。 若要执行此操作，请运行：

```
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a>打开组织的转录亵渎屏蔽

默认情况下，为组织禁用转录亵渎屏蔽。 如果有启用它的业务要求，你可以使用 [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) 启用转录亵渎屏蔽。 若要执行此操作，请运行：

```
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a>为用户禁用转录

用户策略的优先级高于组织默认设置。 例如，如果为所有用户都启用语音邮件转录，您可以分配一个策略来禁用特定用户的转录使用[授予 CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet。

要为单个用户禁用转录，请运行：

```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

### <a name="turning-on-transcription-profanity-masking-for-a-user"></a>为用户开启转录亵渎屏蔽

要为特定用户启用转录亵渎屏蔽，你可以使用 [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet 分配一个策略，以便为特定用户启用转录亵渎屏蔽。

要为单个用户启用转录亵渎屏蔽，请运行：

```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> [!重要信息] Office 365 中的语音邮件服务缓存语音邮件策略，并每隔 4 小时更新一次缓存。因此，你所作的策略更改最长可能需要 4 小时才能生效。

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a>帮助你的用户了解 Skype for Business 语音邮件的功能

我们有培训信息和文章可帮助您成功与 Skype 的业务语音邮件的用户。 指示他们访问以下文章：

- [检查业务语音邮件和选项的 Skype](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8)： 这篇文章介绍如何收听语音邮件中的业务的 Skype、 更改语音邮件问候语，更改您的语音邮件设置和收听语音邮件以不同速度。

- [Skype for Business 2016 培训](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a>相关主题
[设置 Skype for Business Online](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[以下是 Office 365 中的电话系统功能](here-s-what-you-get-with-phone-system.md)

[Skype for Business Server 和 Exchange Server 迁移规划](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/plan-um-migration)


