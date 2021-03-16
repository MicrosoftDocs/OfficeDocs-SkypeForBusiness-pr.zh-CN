---
title: Teams 和 Outlook 电子邮件集成
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
localization_priority: Normal
search.appverid: MET150
description: 了解 Teams 和 Outlook 电子邮件集成功能，包括允许用户在 Outlook 中的电子邮件和 Teams 中的聊天或频道对话之间共享信息的功能。
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e469017eb9d03cbba55017ca609f49da9ebfe07a
ms.sourcegitcommit: c6b630f9193d7f82f0416bd567a1de390d4b260f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2021
ms.locfileid: "50819358"
---
# <a name="teams-and-outlook-email-integration"></a>Teams 和 Outlook 电子邮件集成

Microsoft Teams 包括一些功能，使贵组织的用户能够轻松地在 Outlook 中的电子邮件与 Teams 中的聊天或频道对话之间共享信息，以及随时了解错过的对话。 本文概述了这些功能和适用管理控件。

## <a name="share-to-outlook"></a>共享到 Outlook

**"共享到 Outlook"** 允许用户将 Teams 对话的副本共享到 Outlook 中的电子邮件，而无需离开 Teams。 如果用户需要与直接团队甚至组织外部的用户共享对话或状态更新，此功能非常方便。 在 Teams 中转到对话顶部，选择 **"更多选项"，** 然后选择"**共享到 Outlook"。**  有关详细信息，请参阅从[Teams 共享到 Outlook。](https://support.office.com/article/share-to-outlook-from-teams-f9dabbe9-9e9b-4e35-99dd-2eeeb67c4f6d)

![显示 Teams 中的"共享到 Outlook"功能屏幕截图](media/share-to-outlook.png)

若要使用此功能，必须为用户启用 Outlook 网页。 如果 Outlook 网页页面已关闭，则"共享到 **Outlook"** 选项不会在 Teams 中为用户显示。 有关如何打开和关闭 Outlook 网页中的步骤，请参阅为邮箱启用或禁用[Outlook 网页。](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-outlook-web-app)

## <a name="actionable-activity-emails"></a>可操作活动电子邮件

用户会自动收到可操作错过的活动电子邮件，帮助他们在 Teams 中跟进错过的对话。 错过的活动电子邮件显示对话中的最新答复，包括错过的邮件后发送的邮件，用户可以单击"答复"直接从 Outlook 中答复。  有关详细信息，请参阅从 Outlook 回复错过 [的活动电子邮件](https://support.office.com/article/reply-to-missed-activity-emails-from-outlook-bc0cf587-db26-4946-aac7-8eebd84f1381)。 

> [!NOTE]
> Outlook for Mac 或某些较旧版本的 Outlook for Windows 不支持此功能。 有关详细信息，请参阅 [Outlook 和 Office 365](https://docs.microsoft.com/outlook/actionable-messages/)组中的可操作邮件。

![显示错过的活动电子邮件的屏幕截图](media/missed-activity-email.png)

![显示如何答复错过的活动电子邮件的屏幕截图](media/missed-activity-email-reply.png)

可以将 [Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/organization/set-organizationconfig) cmdlet 与 **SmtpActionableMessagesEnabled** 参数一起用于关闭可操作电子邮件。 默认情况下 **，SmtpActionableMessagesEnabled** 参数设置为 **true。** 将 参数设置为 **false** 会关闭 Office 365 中可操作的电子邮件。 对于 Teams 用户，这意味着在Outlook 中直接答复的"回复"选项在错过的活动电子邮件中不可用。 相反，错过的活动电子邮件包括"在 Teams 中答复 **"** 选项，供用户在 Teams 中答复。
