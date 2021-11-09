---
title: Teams Outlook电子邮件集成
author: HowlinWolf-92
ms.author: v-mahoffman
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
ms.localizationpriority: medium
search.appverid: MET150
description: 了解Teams电子邮件Outlook功能，包括允许用户在电子邮件之间共享信息的功能Outlook Teams聊天或频道对话。
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c6f41d26a2d87d1c95b99534a866f64cd9f30eb8
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60837454"
---
# <a name="teams-and-outlook-email-integration"></a>Teams Outlook电子邮件集成

Microsoft Teams包括一些功能，使您的组织中的用户能够轻松地在 Outlook 中的电子邮件与 Teams 中的聊天或频道对话之间共享信息，以及随时了解错过的对话。 本文概述了这些功能和适用管理控件。

## <a name="share-to-outlook"></a>共享到Outlook

**共享到Outlook** 允许用户将对话的副本Teams共享到 Outlook 中的电子邮件，而无需离开Teams。 如果用户需要与直接团队甚至组织外部的用户共享对话或状态更新，此功能非常方便。 转到对话顶部，选择 **"Teams"，选择"Teams""更多** 选项"，然后选择"共享 **Outlook"。**  若要了解有关详细信息，请参阅[从 Outlook 共享Teams。](https://support.office.com/article/share-to-outlook-from-teams-f9dabbe9-9e9b-4e35-99dd-2eeeb67c4f6d)

![屏幕截图，显示"共享到Outlook"功能Teams。](media/share-to-outlook.png)

若要使用此功能，Outlook 网页版用户必须启用此功能。 如果Outlook 网页版关闭，则"共享到Outlook"选项不会显示在Teams中。 有关如何打开和关闭邮箱Outlook 网页版，请参阅启用或Outlook 网页版[邮箱的邮箱](/exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-outlook-web-app)。

## <a name="actionable-activity-emails"></a>可操作活动电子邮件

用户会自动收到可操作错过的活动电子邮件，帮助用户在对话中跟进错过Teams。 错过的活动电子邮件显示对话的最新答复，包括错过的邮件后发送的邮件，用户可以单击"答复"直接从Outlook。  若要了解有关详细信息，请参阅回复来自 Outlook[的错过Outlook。](https://support.office.com/article/reply-to-missed-activity-emails-from-outlook-bc0cf587-db26-4946-aac7-8eebd84f1381) 

> [!NOTE]
> 此功能在 Outlook for Mac 或某些较旧版本的 Outlook 中不受Windows。 有关详细信息，请参阅组和组中的[Outlook Office 365消息](/outlook/actionable-messages/)。

![显示错过的活动电子邮件的屏幕截图。](media/missed-activity-email.png)

![显示如何答复错过的活动电子邮件的屏幕截图。](media/missed-activity-email-reply.png)

可以将 [Set-OrganizationConfig](/powershell/module/exchange/organization/set-organizationconfig) cmdlet 与 **SmtpActionableMessagesEnabled** 参数一起用于关闭可操作电子邮件。 默认情况下 **，SmtpActionableMessagesEnabled** 参数设置为 **true。** 将 参数设置为 **false** 会关闭整个 Office 365。 对于Teams用户，这意味着在错过的活动电子邮件中Outlook直接答复的"答复"选项不可用。 相反，错过的活动电子邮件包括"答复"Teams"选项，供用户在电子邮件Teams。 

另请参阅[组和组Outlook Office 365邮件](/outlook/actionable-messages/)。
