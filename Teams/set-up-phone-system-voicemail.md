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
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
description: '了解如何为你的用户设置云语音邮件。 '
ms.openlocfilehash: 51e03417d3bdbd09b631fa2bd07b6009bf54693e
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41838002"
---
# <a name="set-up-cloud-voicemail"></a>设置云语音邮件

本文适用于希望为企业中的每个人设置云语音邮件功能的[Office 365 管理员](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)。

> [!NOTE]
> 云语音邮件支持仅在 Exchange 邮箱中发送语音邮件消息，并且不支持任何第三方电子邮件系统。 

## <a name="cloud-only-environments-set-up-cloud-voicemail"></a>仅限云的环境：设置云语音邮件

对于 Skype for Business Online 和通话计划用户，向用户分配**电话系统**许可证和电话号码后，将自动为用户设置和设置云语音邮件。
  
1. 如果您的计划中未包含电话系统功能，您可能需要购买 "**电话系统**加载项" 许可证。 您可能还需要购买 Exchange Online 许可证。 请参阅[Microsoft 团队附加许可](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。
    
2. [分配或删除 Office 365 for business 的许可证](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)，向企业中的人员[分配 Microsoft 团队许可证](assign-teams-licenses.md)和 Exchange Online 许可证。 分配完成后，他们将能够接收语音邮件消息！
    
3. 对语音邮件脚本的支持已添加到2017年3月，并且默认情况下为所有组织和用户启用。 通过使用 Windows PowerShell 并执行以下步骤，你可以为组织禁用转录。

## <a name="phone-system-with-on-premises-environments"></a>本地环境的电话系统

以下信息介绍如何配置云语音邮件以使用本地通话计划环境。
  
1. 如果您的计划中未包含电话系统功能，您可能需要购买 "**电话系统**加载项" 许可证。 您还需要购买 Exchange Online 许可证。 请参阅[Microsoft 团队附加许可](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。
    
2. [分配或删除 Office 365 for business 的许可证](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)，向企业中的人员[分配 Microsoft 团队许可证](assign-teams-licenses.md)和 Exchange Online 许可证。
    
3. 按照为你的用户部署的本地 PSTN 呼叫解决方案匹配说明。 对于云连接器版本，请按照 "[配置 Skype for Business 云连接器](https://technet.microsoft.com/library/mt605228.aspx)的**用户电话语音和语音邮件服务**" 部分中的说明操作。 对于使用 Skype for Business 服务器的 PSTN 呼叫，请遵循[启用企业内部部署企业语音的用户](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-the-users-for-enterprise-voice-on-premises)。 对于团队直接路由，请按照配置电话号码和启用 "[配置直接路由](https://docs.microsoft.com/microsoftteams/direct-routing-configure#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail)" 部分中的 "**启用企业语音和语音邮件**" 部分。

4. 对语音邮件脚本的支持已添加到2017年3月，并且默认情况下为所有组织和用户启用。 通过使用 Windows PowerShell 并执行以下步骤，你可以为组织禁用转录。

5. 语音邮件通过 Exchange Online Protection 通过 SMTP 路由发送到用户的 Exchange 邮箱。 若要支持成功传递这些邮件，请确保 exchange 连接器在 Exchange 服务器和 Exchange Online Protection 之间正确配置;[使用连接器配置邮件流](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)。 

6. 若要启用语音邮件功能（如自定义问候语）和 Skype for business 客户端中的视觉语音邮件，需要通过 Exchange Web 服务将来自 Office 365 的连接到 Exchange server 邮箱。 若要启用此连接，必须配置[exchange 和 Exchange Online 组织之间的 "配置 Oauth 身份验证](https://technet.microsoft.com/library/dn594521(v=exchg.150).aspx)" 中介绍的新 Exchange Oauth 身份验证协议，或者从 EXCHANGE 2013 CU5 或更高版本运行 Exchange 混合向导。 此外，你必须在 Skype for business [online 和 Exchange server 之间配置集成和 oauth](https://docs.microsoft.com/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises)中介绍的 Skype For business Online 和 exchange server 之间配置集成和 oauth。 

## <a name="setting-voicemail-policies-in-your-organization"></a>设置组织的语音邮件策略

> [!WARNING]
> 对于 Skype for Business 客户，通过 Microsoft 团队呼叫策略禁用语音邮件可能还会禁用 Skype for business 用户的语音邮件服务。

默认情况下，为所有组织和用户启用语音邮件转录并禁用转录亵渎屏蔽；但是，你可以使用 [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) 和 [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlet 对其进行控制。

您的组织中的用户收到的语音邮件是 transcribed 在托管 Office 365 租户的区域中。 租户的托管区域可能与接收语音邮件消息的用户所在的区域不同。 若要查看租户的托管区域，请转到 "[组织配置文件](https://go.microsoft.com/fwlink/p/?linkid=2067339)" 页面，然后单击 "**数据位置**" 旁边的 "**查看详细信息**"。

> [!IMPORTANT]
> 您不能使用**且**cmdlet 创建用于脚本的新策略实例并使用脚本猥亵屏蔽，并且不能使用**且**cmdlet 删除现有策略实例。

可以使用语音邮件策略为用户管理转录设置。 若要查看所有可用的语音邮件策略实例，可以使用[且](https://technet.microsoft.com/library/mt798311.aspx)cmdlet。

 **PS C:\\> Get-CsOnlineVoicemailPolicy**
  
![Get-CsOnlineVoiceMailPolic 结果窗口。](media/6cea8310-2d71-4b95-8d36-688472845727.png)
  
### <a name="turning-off-transcription-for-your-organization"></a>为组织禁用转录

由于脚本的默认设置适用于你的组织，你可能希望通过使用[且将](https://technet.microsoft.com/library/mt798310.aspx)其禁用。 若要执行此操作，请运行：

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a>打开组织的转录亵渎屏蔽

默认情况下，为组织禁用转录亵渎屏蔽。 如果有启用它的业务要求，你可以使用 [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) 启用转录亵渎屏蔽。 若要执行此操作，请运行：

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a>为用户禁用转录

用户策略的优先级高于组织默认设置。 例如，如果为所有用户启用语音邮件脚本，则可以使用[且](https://technet.microsoft.com/library/mt798309.aspx)cmdlet 分配策略以禁用特定用户的脚本。

要为单个用户禁用转录，请运行：

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

### <a name="turning-on-transcription-profanity-masking-for-a-user"></a>为用户开启转录亵渎屏蔽

要为特定用户启用转录亵渎屏蔽，你可以使用 [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet 分配一个策略，以便为特定用户启用转录亵渎屏蔽。

要为单个用户启用转录亵渎屏蔽，请运行：

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> [!重要信息] Office 365 中的语音邮件服务缓存语音邮件策略，并每隔 4 小时更新一次缓存。因此，你所作的策略更改最长可能需要 4 小时才能生效。

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a>帮助你的用户了解 Skype for Business 语音邮件的功能

我们有培训信息和文章，可帮助用户成功使用 Skype for Business 语音邮件。 指示他们访问以下文章：

- [检查 skype for business 语音邮件和选项](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8)：本文介绍如何在 Skype for business 中收听语音邮件、更改语音邮件问候语、更改语音邮件设置，以及以不同的速度收听语音邮件。

- [Skype for Business 2016 培训](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a>相关主题
[设置 Skype for Business Online](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[以下是 Office 365 中的电话系统功能](here-s-what-you-get-with-phone-system.md)

[Skype for Business Server 和 Exchange Server 迁移规划](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-um-migration)


