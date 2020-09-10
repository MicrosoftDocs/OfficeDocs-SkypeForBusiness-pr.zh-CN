---
title: 团队和 Outlook 电子邮件集成
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
localization_priority: Normal
search.appverid: MET150
description: 了解团队和 Outlook 电子邮件集成功能，包括允许用户在 Outlook 中的电子邮件与团队中的聊天或频道对话之间共享信息的功能。
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 34498b73b70937eefcff267bc7a3b01068ab9557
ms.sourcegitcommit: 430aac8c5848fbcaf680ea447bfa2f9d5fa994e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/09/2020
ms.locfileid: "47420606"
---
# <a name="teams-and-outlook-email-integration"></a>团队和 Outlook 电子邮件集成

Microsoft 团队包含的功能使您的组织中的用户可以轻松地在 Outlook 中共享电子邮件以及团队中的对话或频道对话中的信息，并保持在错过的对话上。 本文概述了这些功能和适用的管理控件。

## <a name="share-to-outlook"></a>共享到 Outlook

"**共享到 outlook** " 允许用户在 outlook 中与电子邮件共享团队对话副本，而无需离开团队。 如果用户需要与直属团队或你的组织之外的用户共享对话或状态更新，此功能会很方便。 转到团队中的对话顶部，选择 **̇̇̇更多选项**，然后选择 " **共享到 Outlook**"。  若要了解详细信息，请参阅 [从团队共享到 Outlook](https://support.office.com/article/share-to-outlook-from-teams-f9dabbe9-9e9b-4e35-99dd-2eeeb67c4f6d)。

![显示团队中的 "共享到 Outlook" 功能的屏幕截图](media/share-to-outlook.png)

若要使用此功能，必须为用户打开 Outlook 网页版。 如果 Outlook 网页版处于关闭状态，则在用户的团队中不会显示 " **共享到 outlook** " 选项。 有关如何打开和关闭 Outlook 网页版的步骤，请参阅 [启用或禁用适用于邮箱的 outlook 网页](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-outlook-web-app)版。

## <a name="actionable-activity-emails"></a>可操作的活动电子邮件

用户会自动获得可操作的错过活动电子邮件，帮助他们在团队中的错过的对话中追赶。 错过的活动电子邮件显示来自对话的最新答复，包括错过邮件后发送的邮件，并且用户可以单击 " **答复** " 以直接在 Outlook 中答复。 若要了解详细信息，请参阅 [从 outlook 中答复错过的活动电子邮件](https://support.office.com/article/reply-to-missed-activity-emails-from-outlook-bc0cf587-db26-4946-aac7-8eebd84f1381) 和 [outlook 和 Office 365 组中的可操作消息](https://docs.microsoft.com/outlook/actionable-messages/)。

![显示错过的活动电子邮件的屏幕截图](media/missed-activity-email.png)

![显示如何答复错过的活动的屏幕截图电子邮件](media/missed-activity-email-reply.png)

你可以将 [get-organizationconfig](https://docs.microsoft.com/powershell/module/exchange/organization/set-organizationconfig) Cmdlet 与 **SmtpActionableMessagesEnabled** 参数结合使用，以关闭可操作的电子邮件。 默认情况下， **SmtpActionableMessagesEnabled** 参数设置为 **true**。 将该参数设置为 **false** 将关闭跨 Office 365 的可操作电子邮件。 对于团队用户，这意味着直接在 Outlook 中 **答复的答复** 选项在错过的活动电子邮件中不可用。 相反，错过的活动电子邮件包括 " **在团队中答复"** 选项，供用户在团队中答复。
