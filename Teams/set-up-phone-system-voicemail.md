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
ms.openlocfilehash: f448ba79c2451383c0ca85916309bdfab3b69a96
ms.sourcegitcommit: 279ab5236431961c5181e2c01a69e5aa4290d381
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2021
ms.locfileid: "60462366"
---
# <a name="set-up-cloud-voicemail"></a>设置云语音邮件

本文适用于Microsoft 365或Office 365管理员，如关于想要为企业中的云语音邮件设置管理员角色中所述[](/microsoft-365/admin/add-users/about-admin-roles)。 云语音邮件用户Exchange语音邮件的邮箱。 它不支持第三方电子邮件系统。

## <a name="cloud-voicemail-for-teams-users"></a>云语音邮件用户Teams

对于Teams用户，云语音邮件自动设置和预配。 Microsoft Teams 电话不需要许可证云语音邮件。

## <a name="help-your-users-learn-teams-voicemail-features"></a>帮助用户了解Teams语音信箱功能

我们为用户提供了以下信息，说明在 Teams 中使用和管理语音邮件：

- [在语音信箱中检查Teams](https://support.microsoft.com/office/check-your-voicemail-in-teams-f8d568ce-7329-4fe2-a6a2-325ec2e2b419)
- [在通话中管理Teams](https://support.microsoft.com/office/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)

## <a name="setting-up-cloud-voicemail-to-work-with-on-premises-users"></a>设置云语音邮件本地用户

您可以使用 云语音邮件 为在 Exchange 服务器上拥有邮箱的用户或正在使用邮箱的用户提供语音邮件Skype for Business Server。 本部分提供这些方案的信息。 

### <a name="set-up-cloud-voicemail-for-exchange-server-mailbox-users"></a>为邮箱云语音邮件设置Exchange Server组

以下信息用于配置云语音邮件，以便Microsoft Teams 电话邮箱位于 Exchange Server 的用户。

1. 语音邮件通过 SMTP 通过 Exchange 发送到用户的邮箱Exchange Online Protection。 若要成功传递这些消息，请确保在 Exchange 服务器和服务器之间正确Exchange连接器Exchange Online Protection;[使用连接器配置邮件Flow。](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)

2. 若要启用语音邮件功能，例如自定义 Skype for Business 客户端中的问候语和可视语音邮件，需要从 Microsoft 365 或 Office 365 通过 Exchange Web 服务连接到 Exchange 服务器邮箱。 若要启用此连接，必须配置配置 Exchange 与 Exchange Online 组织之间的[OAuth](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)身份验证中所述的新 Exchange Oauth 身份验证协议，或者从 Exchange 2013 CU5 或更高版运行 Exchange 混合向导。 此外，必须在 Skype for Business Online 和 Exchange 服务器之间配置集成和 Oauth，如在 Skype for Business Online 和 Exchange Server[之间配置集成和 OAuth](/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises)中所述。

### <a name="set-up-cloud-voicemail-for-skype-for-business-server-users"></a>为云语音邮件用户Skype for Business Server组

若要Skype for Business服务器用户云语音邮件，请参阅[为云语音邮件用户规划服务](/skypeforbusiness/hybrid/plan-cloud-voicemail)。

## <a name="enabling-protected-voicemail-in-your-organization"></a>在组织中启用受保护的语音邮件

当某人为您的组织中的用户留下语音邮件时，语音邮件作为电子邮件附件传送到用户的邮箱。 使用邮件流规则应用邮件加密，可以防止这些语音邮件转发给其他收件人。 启用受保护的语音邮件后，用户可以通过呼叫进入其语音邮件邮箱或在 Outlook、Outlook 网页版 或 Outlook for Android 或 iOS 中打开该邮件来收听受保护的语音邮件。 受保护的语音邮件无法通过语音信箱或Skype for Business Microsoft Teams。

有关邮件加密详细信息，请参阅定义用于加密 [电子邮件的邮件流规则](/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email)。
