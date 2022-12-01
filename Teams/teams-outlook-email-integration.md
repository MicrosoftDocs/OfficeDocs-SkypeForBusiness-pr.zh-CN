---
title: 管理可操作的活动电子邮件
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
ms.localizationpriority: medium
search.appverid: MET150
description: 了解如何启用和禁用Microsoft Teams 对话的可操作活动电子邮件
ms.collection:
- M365-collaboration
ms.custom: chat-teams-channels-revamp
appliesto:
- Microsoft Teams
ms.openlocfilehash: de1bd12a0f079154a37156e3a01c3e5791bef10c
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198504"
---
# <a name="manage-actionable-activity-emails"></a>管理可操作的活动电子邮件

默认情况下，可操作活动电子邮件处于启用状态，并通知组织中的用户在 Microsoft Teams 上错过的对话。

错过的活动电子邮件显示对对话的最新答复，包括错过邮件后发送的邮件。 此功能允许用户通过选择“答复”直接从 Outlook **进行答复**。

## <a name="disable-actionability-in-missed-activity-emails"></a>在错过的活动电子邮件中禁用可操作性

虽然此功能默认设置为启用，但可以通过运行以下命令来关闭整个组织的活动电子邮件中的可操作性：

```Powershell
Set-OrganizationConfig -SmtpActionableMessagesEnabled $false
```

禁用此功能后， **Teams 中的“答复** ”选项将替换为 **“答复** ”，使错过的活动电子邮件不再被视为可操作。 用户将无法再直接从 Outlook 做出响应，并被指示在 Teams 上继续对话。

> [!NOTE]
> Outlook for Mac或某些较旧版本的 Outlook for Windows 不支持此功能。 有关详细信息，请参阅 [Outlook 中的可操作邮件和Office 365组中](/outlook/actionable-messages/)的邮件。

## <a name="related-topics"></a>相关主题

[回复 Outlook 中错过的活动电子邮件](https://support.office.com/article/reply-to-missed-activity-emails-from-outlook-bc0cf587-db26-4946-aac7-8eebd84f1381)。

[Outlook 和 Office 365 组中的可操作邮件](/outlook/actionable-messages/)。
