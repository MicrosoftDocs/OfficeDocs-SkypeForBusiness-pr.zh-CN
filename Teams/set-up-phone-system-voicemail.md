---
title: 设置云语音邮件
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jenstr
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
description: 了解如何为用户设置云语音邮件。
ms.openlocfilehash: 96c96f85625d0cda7e6d7a28a59d6c9415f2bb79
ms.sourcegitcommit: 1d990582e2deb5f55ba9adada3e17377f792a141
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/19/2022
ms.locfileid: "64922623"
---
# <a name="set-up-cloud-voicemail"></a>设置云语音邮件

本文适用于想要为其用户设置云语音邮件的Microsoft 365管理员。

云语音邮件将语音邮件存放在用户的Exchange邮箱中。 云语音邮件不支持第三方电子邮件系统。 有关Exchange Online许可要求，[请参阅Exchange Online服务说明](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description#features-available-to-all-plans)。 有关管理员角色的详细信息， [请参阅“关于管理员角色](/microsoft-365/admin/add-users/about-admin-roles)”。

## <a name="cloud-voicemail-provisioning"></a>云语音邮件预配

对于Teams用户，会自动设置和预配云语音邮件。 *云语音邮件不需要Microsoft Teams 电话许可证。*

针对Teams用户的预配与Skype for Business联机用户的预配不同。 对于Skype for Business联机用户，云语音邮件在为用户分配电话系统许可证并由预配系统企业语音启用时自动设置和预配。

对于Skype for Business Server本地用户，会自动设置和预配云语音邮件。 但是，必须将Skype for Business Server环境配置为将调用路由到云语音邮件。 有关详细信息，请参阅[本地用户的计划云语音邮件服务](/skypeforbusiness/hybrid/plan-cloud-voicemail)。

## <a name="cloud-voicemail-storage"></a>云语音邮件存储

云语音邮件生成的语音邮件将传送到用户的Exchange邮箱中，无论是在Exchange Online中还是在Exchange Server中。 语音邮件没有特定存储或附加存储空间。 访问语音邮件 (的客户端，例如 Microsoft Outlook、Microsoft Teams 或Skype for Business) 通过Exchange邮箱和提供的 API 执行此操作。

语音邮件包含附加的音频文件，其中包含语音消息和语音邮件听录 (（如果启用）) 。

用户Exchange邮箱存储任何自定义录制的问候语。 在传入呼叫期间，云语音邮件会根据需要检索这些问候语。

## <a name="cloud-voicemail-processing"></a>云语音邮件处理

云语音邮件的录制和听录从Microsoft 365开始，从路由到云语音邮件的呼叫的来源开始。 然后，邮件将传递到用户的Exchange邮箱。

例如，如果通过会话边界控制器 (欧洲的 SBC) 向不可用的直接路由用户发出呼叫，则语音邮件录制和听录将在欧洲完成。 然后，邮件将传递到用户的Exchange邮箱。 对于另一个示例，假定北美中的Teams用户在欧洲调用不可用的Teams用户。 在这种情况下，呼叫从北美开始，处理在北美中进行，然后语音邮件传送到用户在欧洲的Exchange邮箱。

将语音邮件传递到Exchange邮箱是使用简单邮件传输协议 (SMTP) 执行的，就像任何其他电子邮件一样。

## <a name="manage-cloud-voicemail-for-users"></a>为用户管理云语音邮件

若要为用户管理云语音邮件功能，请使用 Teams PowerShell 模块，如下所示。

若要管理云语音邮件用户组的功能，请使用 [New-CsOnlineVoicemailPolicy](/powershell/module/skype/new-csonlinevoicemailpolicy) cmdlet。
可以针对呼叫应答规则、语音邮件听录、听录亵渎屏蔽、听录翻译和系统提示语言等功能配置和分配现有或新的语音邮件策略。 有关详细信息，请参阅 [New-CsOnlineVoicemailPolicy](/powershell/module/skype/new-csonlinevoicemailpolicy)。

若要管理单个用户的云语音邮件设置，请使用 [Set-CsOnlineVoicemailUserSettings](/powershell/module/skype/set-csonlinevoicemailusersettings) cmdlet。 可以应用于单个用户的云语音邮件设置包括呼叫应答规则、提示语言、语音默认文本和假期问候语。 有关详细信息，请参阅 [Set-CsOnlineVoicemailUserSettings](/powershell/module/skype/set-csonlinevoicemailusersettings)。
 (请注意，最终用户还可以通过转到 **设置****CallsConfigure** ->  Voicemail.) 在 Teams  ->  客户端中配置这些设置

还可以使用 [Set-CsOnlineVoicemailUserSettings](/powershell/module/skype/set-csonlinevoicemailusersettings) cmdlet 将 VoicemailEnabled 参数设置为$false，为用户禁用云语音邮件。 此设置将确保云语音邮件无法再为用户录制语音邮件。

## <a name="control-routing-of-calls-to-cloud-voicemail"></a>控制调用云语音邮件的路由

为云语音邮件预配的所有用户的默认设置是允许路由对云语音邮件的调用，并允许用户将呼叫转发到云语音邮件。

可以通过将Set-CsTeamsCallingPolicy cmdlet 与 AllowVoicemail 参数配合使用，控制是否允许Teams用户路由对云语音邮件的调用。 有关详细信息，请参阅 [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)。

- 如果将 AllowVoicemail 设置为 AlwaysDisabled，则调用永远不会路由到语音邮件，无论用户的呼叫转发或未答复的设置如何。 语音邮件在Teams中不可用作呼叫转接或未应答设置。

- 如果将 AllowVoicemail 设置为 AlwaysEnabled，则在响铃 30 秒后，呼叫始终会转发到未答复的语音邮件中，而不管用户的呼叫转发设置如何。

- 如果将 AllowVoicemail 设置为 UserOverride，则会根据用户的呼叫转接和/或未应答设置将呼叫转发到语音邮件。

## <a name="set-up-cloud-voicemail-to-work-with-on-premises-users"></a>设置云语音邮件以与本地用户协作

可以使用云语音邮件为在Exchange服务器上拥有邮箱的用户或使用Skype for Business Server的用户提供语音邮件功能。

本部分介绍如何为Exchange Server邮箱用户设置云语音邮件。 有关如何为Skype for Business Server用户配置云语音邮件的信息，[请参阅本地用户的计划云语音邮件服务](/skypeforbusiness/hybrid/plan-cloud-voicemail)。

### <a name="set-up-cloud-voicemail-for-exchange-server-mailbox-users"></a>为Exchange Server邮箱用户设置云语音邮件

以下信息介绍如何将云语音邮件配置为与Exchange Server上有邮箱的Teams用户配合使用。

1. 语音邮件通过通过Exchange Online Protection路由的 SMTP 传递到用户的Exchange邮箱。 若要成功传递这些消息，请确保在Exchange服务器和Exchange Online Protection之间正确配置了Exchange连接器。 有关详细信息，请参阅[使用连接器配置邮件Flow](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)。

2. 若要在Teams客户端中启用语音邮件功能（例如自定义问候语和视觉语音邮件），必须设置Microsoft 365与Exchange Server邮箱之间的连接。 若要启用此连接，必须配置Exchange和Exchange Online[组织之间配置 OAuth 身份验证中所述的新Exchange Oauth 身份验证](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)协议，或从 Exchange 2013 CU5 或更高版本运行Exchange混合向导。 还必须在Teams和Exchange Server之间的配置集成和 OAuth 中所述的Teams[和Exchange Server之间配置集成和 Oauth](/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises)。

## <a name="enable-protected-voicemail-in-your-organization"></a>在组织中启用受保护的语音邮件

当某人为组织中的用户留下语音邮件时，语音邮件将作为电子邮件附件传递到用户的邮箱。 

使用 Microsoft Purview 信息保护，可以加密内部和外部调用方留下的语音邮件。 还可以阻止用户转发这些消息。 具有Exchange Online邮箱的用户支持此功能。

若要加密语音邮件，可以创建敏感度标签。 使用自动标记功能，可以确保将标签自动应用于传入的语音邮件。 

启用受保护的语音邮件时，用户可以通过调用语音邮件邮箱或在 Android 或 iOS Outlook、Outlook 网页版 或Outlook中打开邮件来收听受保护的语音邮件。 无法在Microsoft Teams或Skype for Business中打开受保护的语音邮件。

若要为语音邮件创建敏感度标签，请参阅 [“使用敏感度标签](/microsoft-365/compliance/encryption-sensitivity-labels?view=o365-worldwide#let-users-assign-permissions)”。 在 **“加密”** 部分，选择 **“允许用户在应用标签时分配** 权限”。 **在Outlook中选择，强制实施以下限制之一**，然后选择 **“不转发”** 选项。

若要创建自动标记策略以将敏感度标签应用于语音邮件，请参阅 [如何配置自动标记策略](/microsoft-365/compliance/apply-sensitivity-label-automatically?view=o365-worldwide#how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange)，并指定以下特定设置：

-   对于 **要应用此标签的“选择”信息**，请选择 **“自定义策略**”。

-   对于 **要应用标签的“选择位置**”，请选择 **“位置”：所有用户Exchange**。

-   对于  **设置通用或高级规则**，请选择 **“高级规则**”。

- Exchange规则：
    - 条件：<br>
        - **标头匹配模式：**<br>
              Content-Class = Voice-CA
       -  **发件人 IP 地址为：**<br>
               13.107.64.0/18, 52.112.0.0/14, 52.120.0.0/14, 52.238.119.141/32, 52.244.160.207/32

- 若 **要选择要自动应用的标签**，请在上面的步骤中选择为语音邮件创建的敏感度标签。

- 有关 **电子邮件的其他设置**，请选择“ **对从组织外部收到的电子邮件应用加密**”，并指定权限管理所有者。

发件人 IP 地址中指定的 IP V4 范围基于 ID 12 中[Office 365 URL 和 IP 地址范围中的](/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide#skype-for-business-online-and-microsoft-teams)列表。

有关邮件加密的详细信息，请参阅 [“定义邮件流规则”来加密电子邮件](/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email)。

## <a name="help-your-users-learn-about-cloud-voicemail-features"></a>帮助用户了解云语音邮件功能

若要帮助用户了解如何使用和管理云语音邮件功能，可以推荐以下文章：

- [在Teams中检查语音邮件](https://support.microsoft.com/office/check-your-voicemail-in-teams-f8d568ce-7329-4fe2-a6a2-325ec2e2b419)
- [在Teams中管理呼叫设置](https://support.microsoft.com/office/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)
