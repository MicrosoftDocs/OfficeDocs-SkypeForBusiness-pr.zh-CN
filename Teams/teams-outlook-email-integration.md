---
title: Teams和Outlook电子邮件集成
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
ms.localizationpriority: medium
search.appverid: MET150
description: 了解Teams和Outlook电子邮件集成功能，包括允许用户在Outlook中的电子邮件和Teams中的聊天或频道对话之间共享信息的功能。
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: cd1226cddb41ee40139029b64c65d6c151c3993b
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/25/2022
ms.locfileid: "65681753"
---
# <a name="teams-and-outlook-email-integration"></a>Teams和Outlook电子邮件集成

Microsoft Teams包括一些功能，使组织中的用户能够轻松地在Outlook中的电子邮件与Teams中的聊天或频道对话之间共享信息，并随时了解错过的对话。 本文概述了这些功能和适用的管理员控件。

## <a name="share-to-outlook"></a>共享到Outlook

**共享到Outlook** 允许用户在Outlook中将Teams对话的副本共享到电子邮件，而无需离开Teams。 如果用户需要与其直接团队外部的用户或组织外部的用户共享对话或状态更新，则此功能非常方便。 在Teams中转到对话的顶部，选择 **...更多选项**，然后选择 **“共享”以Outlook**。  若要了解详细信息，请参阅[“共享”从Teams Outlook](https://support.office.com/article/share-to-outlook-from-teams-f9dabbe9-9e9b-4e35-99dd-2eeeb67c4f6d)。

![显示Teams中的“共享到Outlook”功能的屏幕截图。](media/share-to-outlook.png)

若要使用此功能，必须为用户启用Outlook 网页版。 如果关闭Outlook 网页版，则不会在用户的Teams中显示“**共享到Outlook**”选项。 有关如何打开和关闭Outlook 网页版的步骤，请参阅[启用或禁用邮箱Outlook 网页版](/exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-outlook-web-app)。

## <a name="actionable-activity-emails"></a>可操作的活动电子邮件

用户会自动获取可操作的错过活动电子邮件，以帮助他们赶上Teams中错过的对话。 错过的活动电子邮件显示来自对话的最新答复，包括遗漏邮件后发送的邮件，用户可以单击 **“回复**”直接从Outlook内部回复。 若要了解详细信息，请参阅[Outlook中对错过的活动电子邮件的回复](https://support.office.com/article/reply-to-missed-activity-emails-from-outlook-bc0cf587-db26-4946-aac7-8eebd84f1381)。 

> [!NOTE]
> Outlook for Mac或Windows的一些较旧版本的Outlook不支持此功能。 有关详细信息，请参阅[Outlook和Office 365组中的可操作消息](/outlook/actionable-messages/)。

![显示错过的活动电子邮件的屏幕截图。](media/missed-activity-email.png)

![显示如何回复错过的活动电子邮件的屏幕截图。](media/missed-activity-email-reply.png)

可以将 [Set-OrganizationConfig](/powershell/module/exchange/organization/set-organizationconfig) cmdlet 与 **SmtpActionableMessagesEnabled** 参数一起使用，以关闭可操作的电子邮件。 默认情况下， **SmtpActionableMessagesEnabled** 参数设置为 **true**。 将参数设置为 **false** 会关闭跨Office 365的可操作电子邮件。 对于Teams用户，这意味着在错过的活动电子邮件中无法使用直接在Outlook中响应的 **“回复**”选项。 相反，错过的活动电子邮件包括一个 **答复Teams** 选项，供用户在Teams中答复。

另请参阅[Outlook和Office 365组中的可操作消息](/outlook/actionable-messages/)。
