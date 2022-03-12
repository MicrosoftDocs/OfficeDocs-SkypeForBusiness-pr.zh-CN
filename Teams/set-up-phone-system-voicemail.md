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
description: 了解如何为用户云语音邮件帐户。
ms.openlocfilehash: d78942c5cbfc6af8e921c26c806378b45f480835
ms.sourcegitcommit: c7b95254dec4420ba0a697fd49d11b448364c919
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/11/2022
ms.locfileid: "63442318"
---
# <a name="set-up-cloud-voicemail"></a>设置云语音邮件

本文适用于Microsoft 365用户设置云语音邮件管理员。

云语音邮件将语音邮件置于用户的邮箱Exchange语音邮件。 云语音邮件不支持第三方电子邮件系统。 有关Exchange Online要求，请参阅Exchange Online[说明](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description#features-available-to-all-plans)。 有关管理员角色的信息，请参阅 [关于管理员角色](/microsoft-365/admin/add-users/about-admin-roles)。

## <a name="cloud-voicemail-provisioning"></a>云语音邮件预配

对于Teams用户，云语音邮件自动设置和预配。 *无需Microsoft Teams 电话许可证，云语音邮件。*

为 Teams 用户预配与为联机用户预配Skype for Business不同。 对于 Skype for Business Online 用户，云语音邮件用户分配了一个 电话系统 许可证，并且预配系统企业语音自动设置和预配用户。

对于Skype for Business Server用户，云语音邮件自动设置和预配。 但是，必须将 Skype for Business Server 环境配置为将调用路由到云语音邮件。 有关详细信息，请参阅[为云语音邮件计划服务](/skypeforbusiness/hybrid/plan-cloud-voicemail.md)。

## <a name="cloud-voicemail-storage"></a>云语音邮件存储

由 云语音邮件 生成的语音邮件将传递到用户的 Exchange 邮箱并存储在Exchange Online中或Exchange Server。 没有用于语音邮件的特定存储或其他存储空间。 访问语音邮件的 (例如，Microsoft Outlook、Microsoft Teams 或 Skype for Business) 通过 Exchange 邮箱和提供的 API 来访问语音邮件。

语音邮件包含附加的音频文件，其中包含语音消息和语音邮件听录 (（如果) ）。

用户的Exchange邮箱存储任何自定义录制的问候语。 这些问候语由 云语音邮件传入呼叫期间根据需要检索。

## <a name="cloud-voicemail-processing"></a>云语音邮件处理

从路由到云语音邮件的Microsoft 365开始录制和听录云语音邮件。 然后，邮件将传递到用户的邮箱Exchange邮箱。

例如，如果呼叫通过会话边界控制器 (SBC) 进入不可用的直接路由用户，则语音邮件录制和听录在欧洲完成。 然后，邮件将传递到用户的邮箱Exchange邮箱。 另举一例，假设北美Teams用户调用了欧洲Teams不可用的用户。 在这种情况下，呼叫将在北美开始，处理将在北美进行，然后语音邮件将传递到用户在欧洲Exchange邮箱。

与任何其他电子邮件一样，Exchange使用简单的邮件传输协议 (SMTP) 将语音邮件传递到其他邮箱。

## <a name="manage-cloud-voicemail-for-users"></a>管理云语音邮件用户的用户

若要云语音邮件用户的功能，请使用 powerShell Teams，如下所示。

若要管理云语音邮件组用户的功能，请使用 [New-CsOnlineVoicemailPolicy](/powershell/module/skype/new-csonlinevoicemailpolicy) cmdlet。
你可以为呼叫应答规则、语音邮件听录、听录亵渎内容屏蔽、听录翻译和系统提示语言等功能配置和分配现有或新的语音邮件策略。 有关详细信息，请参阅 [New-CsOnlineVoicemailPolicy](/powershell/module/skype/new-csonlinevoicemailpolicy)。

若要管理云语音邮件用户设置，请使用 [Set-CsOnlineVoicemailUserSettings](/powershell/module/skype/set-csonlinevoicemailusersettings) cmdlet。 云语音邮件用户设置包括呼叫应答规则、提示语言、默认文本到语音和假期问候语。 有关详细信息，请参阅 [Set-CsOnlineVoicemailUserSettings](/powershell/module/skype/set-csonlinevoicemailusersettings)。
 (请注意，最终用户 -> 还可以在 Teams 客户端中配置这些设置，只需设置 **CallsConfigure** ->  **Voicemail**.) 

还可使用 [Set-CsOnlineVoicemailUserSettings](/powershell/module/skype/set-csonlinevoicemailusersettings) cmdlet 云语音邮件将 VoicemailEnabled 参数设置为 $false。 此设置将确保云语音邮件不再为用户录制语音邮件。

## <a name="control-routing-of-calls-to-cloud-voicemail"></a>控制对调用的路由云语音邮件

为 云语音邮件 预配的所有用户的默认设置是允许将调用路由到 云语音邮件，以及允许用户将呼叫转发到 云语音邮件。

可以通过将 Set-CsTeamsCallingPolicy cmdlet 与 AllowVoicemail 参数云语音邮件将调用路由到 Teams。 有关详细信息，请参阅 [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy.md)。

- 如果将 AllowVoicemail 设置为 AlwaysDisabled，则无论用户的呼叫转发或未接听设置如何，呼叫都永远不会路由到语音邮件。 语音邮件不能作为呼叫转发或呼叫呼叫中未Teams。

- 如果将 AllowVoicemail 设置为 AlwaysEnabled，则呼叫始终在响铃 30 秒后转发到未接听的语音邮件 - 无论用户的未接听呼叫转发设置如何。

- 如果将 AllowVoicemail 设置为 UserOverride，则呼叫将基于用户的呼叫转发和/或未答设置转发到语音邮件。

## <a name="set-up-cloud-voicemail-to-work-with-on-premises-users"></a>设置云语音邮件本地用户

您可以使用 云语音邮件 为您的 Exchange 服务器上具有邮箱的用户或正在使用邮箱的用户提供语音邮件Skype for Business Server。

本部分介绍如何为邮箱云语音邮件设置Exchange Server组。 若要了解如何为云语音邮件配置Skype for Business Server，请参阅[为云语音邮件用户规划服务](/skypeforbusiness/hybrid/plan-cloud-voicemail)。

### <a name="set-up-cloud-voicemail-for-exchange-server-mailbox-users"></a>为云语音邮件用户Exchange Server设置邮箱

以下信息用于配置云语音邮件，以便Teams邮箱位于 Exchange Server 的用户。

1. 语音邮件通过 SMTP 通过 Exchange 发送到用户的邮箱Exchange Online Protection。 若要成功传递这些消息，请确保在 Exchange 服务器和服务器之间正确配置Exchange连接器Exchange Online Protection。 有关详细信息，请参阅[使用连接器配置邮件Flow](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)。

2. 若要在客户端中启用语音邮件功能，例如自定义Teams和可视语音邮件，必须在 Microsoft 365 和 Exchange Server 邮箱之间设置连接。 若要启用此连接，必须配置配置 Exchange 与 Exchange Online 组织之间的 [OAuth](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help) 身份验证中所述的新 Exchange Oauth 身份验证协议，或者从 Exchange 2013 CU5 或更高版运行 Exchange 混合向导。 此外，还必须在 Teams 和 Exchange Server 之间配置集成和 [OAuth 中所述Teams OAuth Exchange Server](/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises)。

## <a name="enable-protected-voicemail-in-your-organization"></a>在组织中启用受保护的语音邮件

当某人为您的组织中的用户留下语音邮件时，语音邮件作为电子邮件附件传送到用户的邮箱。 

使用Microsoft 信息保护，您可以加密内部和外部呼叫者留下的语音邮件。 还可以阻止用户转发这些消息。 具有邮箱的用户支持Exchange Online此功能。

若要加密语音邮件，可以创建敏感度标签。 使用自动标记功能，你可以确保自动将标签应用于传入的语音邮件。 

启用受保护的语音邮件后，用户可以通过呼叫进入其语音邮件邮箱或在 Outlook、Outlook 网页版 或 Outlook for Android 或 iOS 中打开该邮件来收听受保护的语音邮件。 对于 Busimes，受保护的语音邮件Microsoft Teams Skype打开。

若要为语音邮件创建敏感度标签，请参阅 [使用敏感度标签](/microsoft-365/compliance/encryption-sensitivity-labels?view=o365-worldwide#let-users-assign-permissions)。 在" **加密** "部分中， **选择"允许用户在应用标签时分配权限"**。 选择 **"Outlook"，强制实施** 以下限制之一，然后选择"**不转发"** 选项。

若要创建自动标记策略以将敏感度标签应用到语音邮件，请参阅如何配置自动 [标记](/microsoft-365/compliance/apply-sensitivity-label-automatically?view=o365-worldwide#how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange)策略，并指定以下特定设置：

-   对于 **"选择要应用此标签的信息"，请选择**" **自定义策略"**。

-   对于 **"选择要应用标签的位置"**，请选择"位置：Exchange **所有用户使用"**

-   对于  **"设置常见规则"或"高级规则"**，请选择" **高级规则"**。

- Exchange规则：
    - 条件：<br>
        - **标头匹配模式：**<br>
              Content-Class = Voice-CA
       -  **发送方 IP 地址为：**<br>
               13.107.64.0/18, 52.112.0.0/14, 52.120.0.0/14, 52.238.119.141/32, 52.244.160.207/32

- 对于 **"选择要自动应用的标签"**，请选择在以上步骤中为语音邮件创建的敏感度标签。

- 有关 **电子邮件的其他设置，请选择****"对从** 组织外部收到的电子邮件应用加密"，并指定权限管理所有者。

发件人 IP 地址中指定的 IP V4 范围基于 URL 和 IP 地址范围中 ID 12 Office 365[列表](/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide#skype-for-business-online-and-microsoft-teams)。

有关邮件加密详细信息，请参阅定义邮件 [流规则以加密电子邮件](/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email)。

## <a name="help-your-users-learn-about-cloud-voicemail-features"></a>帮助用户了解云语音邮件功能

若要帮助用户了解如何使用和管理云语音邮件，可以推荐以下文章：

- [在语音信箱中Teams](https://support.microsoft.com/office/check-your-voicemail-in-teams-f8d568ce-7329-4fe2-a6a2-325ec2e2b419)
- [在通话中管理Teams](https://support.microsoft.com/office/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)
