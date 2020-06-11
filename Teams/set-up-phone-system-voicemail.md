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
ms.openlocfilehash: 62729794ff1e23ce29b3e3aad86fa09b63a428e5
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691048"
---
# <a name="set-up-cloud-voicemail"></a>设置云语音邮件

本文介绍 Microsoft 365 或 Office 365 管理员，如[关于管理员角色，这些管理员角色](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)希望为企业中的每个人设置云语音邮件功能。

> [!NOTE]
> 云语音邮件支持仅在 Exchange 邮箱中发送语音邮件消息，并且不支持任何第三方电子邮件系统。 

> [!NOTE]
> 当代理人代表委托人进行通话应答呼叫时，通知在云语音邮件中不可用。 用户可以接收有关未接来电的通知。

## <a name="cloud-only-environments-set-up-cloud-voicemail-for-online-phone-system-users"></a>仅限云的环境：为联机电话系统用户设置云语音邮件

对于联机电话系统用户，向用户分配**电话系统**许可证后，将自动为用户设置和设置云语音邮件。 

> [!NOTE]
> 对于使用本地提供的电话号码的联机 Skype for Business 电话系统用户，您可能需要启用[move-csuser-HostedVoicemail $True](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps)的托管语音邮件。 

## <a name="set-up-cloud-voicemail-for-exchange-server-mailbox-users"></a>为 Exchange Server 邮箱用户设置云语音邮件

以下信息介绍了如何配置云语音邮件，以便与联机电话系统的用户进行协作，但其邮箱位于 Exchange 服务器上。 
  
1. 语音邮件通过 Exchange Online Protection 通过 SMTP 路由发送到用户的 Exchange 邮箱。 若要支持成功传递这些邮件，请确保 exchange 连接器在 Exchange 服务器和 Exchange Online Protection 之间正确配置;[使用连接器配置邮件流](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)。 

2. 若要在 Skype for Business 客户端中启用语音邮件功能（如自定义问候语和视觉语音邮件），需要通过 Exchange Web 服务将来自 Microsoft 365 或 Office 365 的连接到 Exchange server 邮箱。 若要启用此连接，必须配置[exchange 与 Exchange Online 组织之间的 "配置 Oauth 身份验证](https://technet.microsoft.com/library/dn594521(v=exchg.150).aspx)" 中描述的新 Exchange Oauth 身份验证协议，或者从 EXCHANGE 2013 CU5 或更高版本运行 Exchange 混合向导。 此外，你必须在 Skype for business [online 和 Exchange server 之间配置集成和 oauth](https://docs.microsoft.com/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises)中介绍的 Skype For business Online 和 exchange server 之间配置集成和 oauth。 

## <a name="set-up-cloud-voicemail-for-skype-for-business-server-users"></a>为 Skype for business Server 用户设置云语音邮件

若要为云语音邮件配置 Skype for Business 服务器用户，请参阅为[本地用户规划云语音邮件服务](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-cloud-voicemail)。

## <a name="enabling-protected-voicemail-in-your-organization"></a>在你的组织中启用受保护的语音邮件

当某人为您的组织中的用户留下语音邮件时，语音邮件将作为电子邮件附件发送到用户的邮箱。 使用邮件流规则应用邮件加密，可以防止将这些语音邮件转发给其他收件人。 当您启用受保护的语音邮件时，用户可以通过呼叫其语音邮件邮箱或打开 outlook、Outlook 网页版或适用于 Android 或 iOS 中的邮件来收听受保护的语音邮件。 不能在 Skype for Business 中打开受保护的语音邮件。

有关邮件加密的详细信息，请参阅[电子邮件加密](https://docs.microsoft.com/microsoft-365/compliance/email-encryption?view=o365-worldwide)。

若要设置受保护的语音邮件，请执行下列操作：

1. 转到 https://admin.microsoft.com 使用具有全局管理员权限的帐户登录并登录。
2. 选择 "**全部显示**"，然后转到 "**管理中心**  >  **Exchange**"。
3. 在 Exchange 管理中心中，选择 "**邮件流**  >  **规则**"。
4. 选择 **+** "**添加**"，然后选择 "向**邮件应用 Office 365 邮件加密和权限保护**"。
5. 为新邮件流规则提供一个名称，然后在 "**应用此规则条件**" 下，选择**邮件属性**  >  **包括 "**  >  **语音邮件**" 这一邮件类型。 选择 **"确定"**。
6. 在 "**执行以下操作**" 下，选择 **"向邮件应用 Office 365 邮件加密和权限保护"** ，然后选择 "**选择一个**"。 在 " **RMS 模板**" 下，选择 "**不转发**"。 选择 **"确定"** ，然后单击 "**保存**"。
    > [!NOTE]
    > 如果**RMS 模板**列表为空，则需要设置邮件加密。 有关设置邮件加密的详细信息，请参阅以下文章：
    > - [设置新的邮件加密功能](https://docs.microsoft.com/microsoft-365/compliance/set-up-new-message-encryption-capabilities?view=o365-worldwide)
    > - [配置和管理 Azure 信息保护模板](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)
    > - [电子邮件的 "不转发" 选项](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)

## <a name="setting-voicemail-policies-in-your-organization"></a>设置组织的语音邮件策略

> [!WARNING]
> 对于 Skype for Business 客户，通过 Microsoft 团队呼叫策略禁用语音邮件可能还会禁用 Skype for business 用户的语音邮件服务。

默认情况下，为所有组织和用户启用语音邮件转录并禁用转录亵渎屏蔽；但是，你可以使用 [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) 和 [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlet 对其进行控制。

您的组织中的用户收到的语音邮件在托管 Microsoft 365 或 Office 365 组织的区域中 transcribed。 租户的托管区域可能与接收语音邮件消息的用户所在的区域不同。 若要查看租户的托管区域，请转到 "[组织配置文件](https://go.microsoft.com/fwlink/p/?linkid=2067339)" 页面，然后单击 "**数据位置**" 旁边的 "**查看详细信息**"。

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
> Microsoft 365 和 Office 365 中的语音邮件服务缓存语音邮件策略，每隔4小时更新缓存。 因此，你所作的策略更改最长可能需要 4 小时才能生效。

## <a name="help-your-users-learn-teams-voicemail-features"></a>帮助用户了解团队语音邮件功能

我们为你的用户提供了以下信息，用于管理其语音邮件设置以及团队中的其他呼叫功能：

- [管理团队的通话设置](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)。 本文介绍如何管理所有最终用户团队通话功能。 

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a>帮助你的用户了解 Skype for Business 语音邮件的功能

我们有培训信息和文章，可帮助用户成功使用 Skype for Business 语音邮件。 指示他们访问以下文章：

- [检查 skype for business 语音邮件和选项](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8)：本文介绍如何在 Skype for business 中收听语音邮件、更改语音邮件问候语、更改语音邮件设置，以及以不同的速度收听语音邮件。

- [Skype for Business 2016 培训](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a>相关主题
[设置 Skype for Business Online](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[电话系统的功能](here-s-what-you-get-with-phone-system.md)

[Skype for Business Server 和 Exchange Server 迁移规划](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-um-migration)
