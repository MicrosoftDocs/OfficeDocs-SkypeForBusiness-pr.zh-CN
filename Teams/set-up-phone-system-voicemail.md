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
- highpri
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
ms.openlocfilehash: c34b95db32906e81f60fc68dff6fce36e5913140
ms.sourcegitcommit: e09591a0df9848b50bfeda29650e91e9d35724af
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2023
ms.locfileid: "69981797"
---
# <a name="set-up-cloud-voicemail"></a>设置云语音邮件

本文适用于希望为其用户设置云语音邮件的 Microsoft 365 管理员。

云语音邮件将语音邮件存入用户的 Exchange 邮箱中。 云语音邮件不支持第三方电子邮件系统。 有关Exchange Online许可要求，请参阅[Exchange Online服务说明](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description#features-available-to-all-plans)。 有关管理员角色的详细信息，请参阅 [关于管理员角色](/microsoft-365/admin/add-users/about-admin-roles)。

## <a name="cloud-voicemail-provisioning"></a>云语音邮件预配

对于 Teams 用户，会自动设置和预配云语音邮件。 *云语音邮件不需要Microsoft Teams 电话许可证。*

Teams 用户的预配与Skype for Business Online 用户的预配不同。 对于 Skype for Business Online 用户，云语音邮件在为用户分配了电话系统许可证并企业语音预配系统时自动设置和预配。

对于Skype for Business Server本地用户，会自动设置和预配云语音邮件。 但是，必须将Skype for Business Server环境配置为将呼叫路由到云语音邮件。 有关详细信息，请参阅[为本地用户规划云语音邮件服务](/skypeforbusiness/hybrid/plan-cloud-voicemail)。

## <a name="cloud-voicemail-storage"></a>云语音邮件存储

云语音邮件生成的语音邮件将传递到用户的 Exchange 邮箱并存储在 Exchange Online 或 Exchange Server 中。 语音邮件没有特定或额外的存储空间。 访问语音邮件的客户端 (例如 Microsoft Outlook、Microsoft Teams 或 Skype for Business) 通过 Exchange 邮箱和提供的 API 执行此操作。

语音邮件包含附加的音频文件，其中包含语音邮件和语音邮件听录 (（如果启用) ）。

用户的 Exchange 邮箱存储任何自定义录制的问候语。 在传入呼叫期间，云语音邮件根据需要检索这些问候语。

## <a name="cloud-voicemail-processing"></a>云语音邮件处理

云语音邮件的录制和听录从 Microsoft 365 开始，该呼叫将路由到云语音邮件。 然后，邮件将传递到用户的 Exchange 邮箱。

例如，如果通过会话边界控制器 (SBC) 在欧洲向不可用的直接路由用户发出呼叫，则语音邮件录制和听录在欧洲完成。 然后，邮件将传递到用户的 Exchange 邮箱。 对于另一个示例，假设 北美 中的 Teams 用户调用欧洲不可用的 Teams 用户。 在这种情况下，呼叫从 北美 开始，处理过程在北美进行，然后语音邮件将传递到用户的欧洲 Exchange 邮箱。

使用简单邮件传输协议 (SMTP) 将语音邮件传递到 Exchange 邮箱，就像使用任何其他电子邮件一样。

## <a name="manage-cloud-voicemail-for-users"></a>管理用户的云语音邮件

可以通过指定语音邮件策略和配置语音邮件设置来管理用户的云语音邮件。  

- **语音邮件策略** 允许你管理用户组的功能。 可以为呼叫应答规则、语音邮件听录、听录猥亵内容掩码、听录翻译和系统提示语言等功能配置和分配现有或新的语音邮件策略。 有关管理语音邮件策略的信息，请参阅 [管理语音邮件策略](manage-voicemail-policies.md)。

- **语音邮件设置** 允许你为单个用户配置设置。 可以配置呼叫应答规则、提示语言、文本转语音默认值和休假问候语等设置。 有关为单个用户配置设置的信息，请参阅 [管理语音邮件设置](manage-voicemail-settings.md)。 请注意，最终用户还可以通过转到 **“设置”-“>呼叫”->“配置语音邮件”，** 在 Teams 客户端中配置这些设置。

## <a name="control-routing-of-calls-to-cloud-voicemail"></a>控制对云语音邮件的呼叫路由

为云语音邮件预配的所有用户的默认设置是允许将呼叫路由到云语音邮件，并允许用户将呼叫转发到云语音邮件。

可以使用 Teams 管理中心或使用 PowerShell 控制是否允许 Teams 用户将呼叫路由到 云语音邮件。 

- 若要使用 Teams 管理中心，请转到 **语音** -> **呼叫策略** ->添加新策略或编辑现有策略 -> **语音邮件可用于路由入站呼叫**。  

- 在 PowerShell 中，将 Set-CsTeamsCallingPolicy cmdlet 与 AllowVoicemail 参数配合使用。 有关详细信息，请参阅 [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)。

  - 如果将 AllowVoicemail 设置为 AlwaysDisabled，则无论用户的呼叫转接或未接听设置如何，呼叫都不会路由到语音邮件。 在 Teams 中，语音邮件不可用作呼叫转接或未接听设置。

  - 如果将 AllowVoicemail 设置为 AlwaysEnabled，呼叫始终在响铃 30 秒后转发到语音邮件，而不考虑用户的未接听呼叫转接设置。

  - 如果将 AllowVoicemail 设置为 UserOverride，则会根据用户的呼叫转接和/或未接听设置将呼叫转发到语音邮件。

## <a name="set-up-cloud-voicemail-to-work-with-on-premises-users"></a>设置云语音邮件以使用本地用户

可以使用 云语音邮件 为 Exchange Server 上具有邮箱的用户或使用 Skype for Business Server 的用户提供语音邮件功能。

本部分介绍如何为Exchange Server邮箱用户设置云语音邮件。 有关如何为Skype for Business Server用户配置云语音邮件的信息，请参阅[为本地用户规划云语音邮件服务](/skypeforbusiness/hybrid/plan-cloud-voicemail)。

### <a name="set-up-cloud-voicemail-for-exchange-server-mailbox-users"></a>为Exchange Server邮箱用户设置云语音邮件

以下信息介绍如何配置云语音邮件，以便与在 Exchange Server 上拥有邮箱的 Teams 用户一起工作。

1. 语音邮件通过通过Exchange Online Protection路由的 SMTP 传递到用户的 Exchange 邮箱。 若要成功传递这些邮件，请确保在 Exchange 服务器和Exchange Online Protection之间正确配置了 Exchange 连接器。 有关详细信息，请参阅 [使用连接器配置邮件流](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)。

2. 若要启用语音邮件功能，例如在 Teams 客户端中自定义问候语和可视语音邮件，必须在 Microsoft 365 与 Exchange Server 邮箱之间建立连接。 若要启用此连接，必须配置配置 Exchange [与 Exchange Online 组织之间的 OAuth 身份验证中所述的新 Exchange Oauth 身份验证](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)协议，或者从 Exchange 2013 CU5 或更高版本运行 Exchange 混合向导。 还必须在 Teams 和 Exchange Server 之间配置集成和 OAuth 中所述的 [Teams 和Exchange Server集成和 Oauth](/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises)。

## <a name="enable-protected-voicemail-in-your-organization"></a>在组织中启用受保护的语音邮件

当某人为组织中的用户留下语音邮件时，语音邮件将作为电子邮件附件传递到用户的邮箱。

使用Microsoft Purview 信息保护，可以加密内部和外部呼叫者留下的语音邮件。 还可以阻止用户转发这些消息。 具有Exchange Online邮箱的用户支持此功能。

若要加密语音邮件，可以创建敏感度标签。 使用自动标记功能，可以确保标签将自动应用于传入的语音邮件。

启用受保护的语音邮件后，用户可以通过在 Outlook、Outlook 网页版 或 Outlook for Android 或 iOS 中打开邮件来收听受保护的语音邮件。 无法在 Microsoft Teams 或Skype for Business中打开受保护的语音邮件。

若要为语音邮件创建敏感度标签，请参阅 [使用敏感度标签](/microsoft-365/compliance/encryption-sensitivity-labels#let-users-assign-permissions)。 在 **“加密** ”部分中， **选择“允许用户在应用标签时分配权限**”。 选择“ **在 Outlook 中，强制实施以下限制之一**”，然后选择“ **请勿转发** ”选项。

若要创建自动标记策略以将敏感度标签应用于语音邮件，请参阅 [如何配置自动标记策略](/microsoft-365/compliance/apply-sensitivity-label-automatically#how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange)，并指定以下特定设置：

- 对于 **“选择要应用此标签的信息**”，选择“ **自定义策略**”。

- 对于 **“选择要应用标签的位置**”，选择“ **位置：所有用户的 Exchange**”。

- 对于  **“设置通用或高级规则**”，请选择“ **高级规则**”。

- Exchange 规则：
  - 条件：
    - **标头匹配模式**：Content-Class = Voice-CA
    - **发件人 IP 地址为**：13.107.64.0/18、52.112.0.0/14、52.122.0.0/15、52.238.119.141/32、52.244.160.207/32

- 对于 **“选择要自动应用的标签**”，请选择在上述步骤中为语音邮件创建的敏感度标签。

- 有关 **电子邮件的其他设置**，请选择“ **对从组织外部接收的电子邮件应用加密**”，并指定 Rights Management 所有者。

发件人 IP 地址中指定的 IP V4 范围基于[OFFICE 365 URL 和 IP 地址范围](/microsoft-365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)中的 ID 12 中的列表。

有关邮件加密的详细信息，请参阅 [定义邮件流规则以加密电子邮件](/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email)。

## <a name="help-your-users-learn-about-cloud-voicemail-features"></a>帮助用户了解云语音邮件功能

若要帮助用户了解如何使用和管理云语音邮件功能，可以推荐以下文章：

- [在 Teams 中检查语音邮件](https://support.microsoft.com/office/check-your-voicemail-in-teams-f8d568ce-7329-4fe2-a6a2-325ec2e2b419)
- [在 Teams 中管理通话设置](https://support.microsoft.com/office/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)
