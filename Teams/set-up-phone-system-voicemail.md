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
description: 了解如何为云语音邮件设置帐户。
ms.openlocfilehash: f1645ec9a14a5b201809cbe12219d7b1e437d355
ms.sourcegitcommit: edf68b7ac4f1861259a0990157ee6ae84f68ca42
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/26/2022
ms.locfileid: "62974469"
---
# <a name="set-up-cloud-voicemail"></a>设置云语音邮件

本文适用于Microsoft 365用户设置云语音邮件管理员。 

云语音邮件将语音邮件置于用户的邮箱Exchange语音邮件。 云语音邮件不支持第三方电子邮件系统。 有关Exchange Online要求，请参阅Exchange Online[说明](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description#features-available-to-all-plans)。 有关管理员角色的信息，请参阅 [关于管理员角色](/microsoft-365/admin/add-users/about-admin-roles)。

## <a name="cloud-voicemail-provisioning"></a>云语音邮件预配

对于Teams用户，云语音邮件自动设置和预配。 *Microsoft Teams 电话不需要许可证云语音邮件。*

为 Teams 用户的预配与为联机用户预配Skype for Business不同。 对于 Skype for Business Online 用户，云语音邮件为用户分配 电话系统 许可证并且预配系统企业语音自动设置和预配。

对于Skype for Business Server本地用户，云语音邮件自动设置和预配。 但是，必须将 Skype for Business Server 环境配置为将调用路由到云语音邮件。 有关详细信息，请参阅[为云语音邮件计划服务](/skypeforbusiness/hybrid/plan-cloud-voicemail.md)。 

## <a name="cloud-voicemail-storage"></a>云语音邮件存储

由云语音邮件的语音邮件将传递到用户的 Exchange 邮箱并存储在Exchange Online或Exchange Server。 没有用于语音邮件的特定存储或其他存储空间。 访问语音邮件的客户端 (例如，Microsoft Outlook、Microsoft Teams 或 Skype for Business) 通过 Exchange 邮箱和提供的 API 来访问语音邮件。 

语音邮件包含附加的音频文件，其中包含语音消息和语音邮件听录 (（如果) ）。 

用户的Exchange邮箱存储任何自定义录制的问候语。 在传入呼叫期间，云语音邮件按需要检索这些问候语。 

## <a name="cloud-voicemail-processing"></a>云语音邮件处理 

从路由到云语音邮件的Microsoft 365开始录制和听录云语音邮件。 然后，邮件将传递到用户的邮箱Exchange邮箱。 

例如，如果呼叫通过会话边界控制器 (SBC) 进入不可用的直接路由用户，则语音邮件录制和听录在欧洲完成。 然后，邮件将传递到用户的邮箱Exchange邮箱。 另举一例，假设北美Teams用户在欧洲调用Teams不可用的用户。 在这种情况下，呼叫将在北美开始，处理将在北美进行，然后语音邮件将传递到用户在欧洲Exchange邮箱。 

与任何其他电子邮件一样，Exchange使用简单邮件传输协议 (SMTP) 将语音邮件传递到邮箱。 

## <a name="manage-cloud-voicemail-for-users"></a>管理云语音邮件用户的用户 

若要云语音邮件用户的功能，请使用 powerShell Teams，如下所示。 

若要管理云语音邮件组用户的功能，请使用 [New-CsOnlineVoicemailPolicy](/powershell/module/skype/new-csonlinevoicemailpolicy) cmdlet。 你可以为呼叫应答规则、语音邮件听录、听录亵渎内容屏蔽、听录翻译和系统提示语言等功能配置和分配现有或新的语音邮件策略。 有关详细信息，请参阅 [New-CsOnlineVoicemailPolicy](/powershell/module/skype/new-csonlinevoicemailpolicy)。

若要管理云语音邮件用户设置，请使用 [Set-CsOnlineVoicemailUserSettings](/powershell/module/skype/set-csonlinevoicemailusersettings) cmdlet。 云语音邮件用户设置包括呼叫应答规则、提示语言、默认文本到语音和假期问候语。 有关详细信息，请参阅 [Set-CsOnlineVoicemailUserSettings](/powershell/module/skype/set-csonlinevoicemailusersettings)。
 (请注意，最终用户 -> 也可在 Teams 客户端中配置这些设置，只需设置 **CallsConfigure** ->  **Voicemail**.) 

还可使用 [Set-CsOnlineVoicemailUserSettings](/powershell/module/skype/set-csonlinevoicemailusersettings) cmdlet 云语音邮件将 VoicemailEnabled 参数设置为 $false。 此设置将确保云语音邮件不再为用户录制语音邮件。



## <a name="control-routing-of-calls-to-cloud-voicemail"></a>控制对 云语音邮件 的调用路由 

为 云语音邮件 预配的所有用户的默认设置是允许将调用路由到 云语音邮件，以及允许用户将呼叫转发到 云语音邮件。 

可以通过将 Set-CsTeamsCallingPolicy cmdlet 与 AllowVoicemail 参数云语音邮件将调用路由到 Teams。 有关详细信息，请参阅 [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy.md)。 

- 如果将 AllowVoicemail 设置为 AlwaysDisabled，则无论用户的呼叫转发或未接听设置如何，呼叫都永远不会路由到语音邮件。 语音邮件不能作为呼叫转发或呼叫呼叫中未Teams。  

- 如果将 AllowVoicemail 设置为 AlwaysEnabled，则呼叫始终在响铃 30 秒后转发到未接听的语音邮件 - 无论用户的未接听呼叫转发设置如何。  

- 如果将 AllowVoicemail 设置为 UserOverride，则呼叫将基于用户的呼叫转发和/或未答设置转发到语音邮件。 



## <a name="set-up-cloud-voicemail-to-work-with-on-premises-users"></a>设置云语音邮件本地用户

您可以使用 云语音邮件 为您的 Exchange 服务器上具有邮箱的用户或正在使用邮箱的用户提供语音邮件Skype for Business Server。 

本部分介绍如何为邮箱云语音邮件设置Exchange Server组。 若要了解如何为云语音邮件用户Skype for Business Server，请参阅[为云语音邮件用户规划服务](/skypeforbusiness/hybrid/plan-cloud-voicemail)。

### <a name="set-up-cloud-voicemail-for-exchange-server-mailbox-users"></a>为云语音邮件用户设置Exchange Server组

以下信息将有关配置云语音邮件，以便与Teams邮箱位于同一Exchange Server的用户一起Exchange Server。

1. 语音邮件通过 SMTP 通过 Exchange Online Protection 路由发送到用户的 Exchange 邮箱。 若要成功传递这些消息，请确保在 Exchange 服务器和服务器之间正确Exchange连接器Exchange Online Protection。 有关详细信息，请参阅[使用连接器配置邮件Flow](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)。

2. 若要在客户端中启用语音邮件功能，例如自定义Teams和可视语音邮件，必须在 Microsoft 365 和 Exchange Server 邮箱之间设置连接。 若要启用此连接，必须配置在 Exchange 和 Exchange Online 组织之间配置 [OAuth](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help) 身份验证中所述的新 Exchange Oauth 身份验证协议，或者从 Exchange 2013 CU5 或更高版运行 Exchange 混合向导。 此外，还必须在 Teams 和 Exchange Server 之间配置集成和 [OAuth Teams OAuth](/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises) Exchange Server。


## <a name="enable-protected-voicemail-in-your-organization"></a>在组织中启用受保护的语音邮件

当某人为您的组织中的用户留下语音邮件时，语音邮件作为电子邮件附件传送到用户的邮箱。 使用邮件流规则应用邮件加密，可以防止这些语音邮件转发给其他收件人。 启用受保护的语音邮件后，用户可以通过呼叫进入其语音邮件邮箱或在 Outlook、Outlook 网页版 或 Outlook for Android 或 iOS 中打开该邮件来收听受保护的语音邮件。 受保护的语音邮件无法通过语音信箱或Skype for Business Microsoft Teams。

有关邮件加密详细信息，请参阅定义邮件 [流规则以加密电子邮件](/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email)。



## <a name="help-your-users-learn-about-cloud-voicemail-features"></a>帮助用户了解云语音邮件功能

若要帮助用户了解如何使用和管理云语音邮件，可以推荐以下文章： 

- [在语音信箱中Teams](https://support.microsoft.com/office/check-your-voicemail-in-teams-f8d568ce-7329-4fe2-a6a2-325ec2e2b419)
- [在通话中管理Teams](https://support.microsoft.com/office/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)
