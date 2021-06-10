---
title: 启用内联消息翻译
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 06/21/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: salilda
localization_priority: Normal
search.appverid: MET150
description: 了解如何使用 Microsoft Teams 管理中心或 PowerShell 在 Microsoft Teams 中启用内联翻译。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 78282b464dd1d9cb25c5d4d2b338c74a2c91d374
ms.sourcegitcommit: 36bc47b2b9ee0e738fa814c31accacfe816da4a3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/09/2021
ms.locfileid: "52855921"
---
# <a name="turn-off-inline-message-translation-in-microsoft-teams"></a>在邮件中关闭内联Microsoft Teams

内联邮件翻译Microsoft Teams一项功能，允许用户将Teams翻译成[其个人语言](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194)设置指定的语言。

默认情况下，为组织推出内联邮件翻译。 如果希望允许用户在客户端客户端内使用此功能，Teams更改。

> [!NOTE]
>此推出不包括在我们的 Office 365 德国云Office 365 政府版 Community订阅Office 365订阅。

## <a name="use-powershell-to-turn-off-inline-message-translation"></a>使用 PowerShell 关闭内联消息翻译

可以使用消息传送策略关闭内联邮件翻译。

使用 [Set-CsTeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) cmdlet 关闭策略。 应用策略需要几分钟时间。 用户可能需要注销并重新登录到Teams。

## <a name="use-the-microsoft-teams-admin-center-to-turn-off-inline-message-translation"></a>使用 Microsoft Teams 管理中心关闭内联邮件翻译

在 **Microsoft Teams** 管理中心中，从左侧导航栏中选择"消息传送策略"，然后创建新策略或编辑现有策略，然后将"翻译邮件"选项设置为"**关闭"。**

> [!NOTE]
> 服务执行翻译，并传送给客户端，对合规性记录中捕获的内容没有任何影响。 若要详细了解翻译，请参阅什么是[Microsoft 翻译工具？](/azure/cognitive-services/translator/translator-info-overview)