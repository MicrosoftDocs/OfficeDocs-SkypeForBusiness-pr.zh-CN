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
ms.openlocfilehash: 5c9e34c5e539d32b25259098973e9bfe6795ad7c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120623"
---
<a name="turn-off-inline-message-translation-in-microsoft-teams"></a>在 Microsoft Teams 中关闭内联消息翻译
=================================================

内联消息翻译是 Microsoft Teams 的一项功能，允许用户将[](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194)Teams 消息翻译成其个人语言设置指定的语言。

默认情况下，为组织推出内联邮件翻译。 如果希望允许用户在 Teams 客户端内使用此功能，无需进行更改。

> [!NOTE]
>此推出不包括在我们的 Office 365 政府社区云和 Office 365 Germany 环境的 Office 365 订阅中。

## <a name="use-powershell-to-turn-off-inline-message-translation"></a>使用 PowerShell 关闭内联消息翻译

可以使用消息传送策略关闭内联邮件翻译。

使用 [Set-CsTeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) cmdlet 关闭策略。 应用策略需要几分钟时间。 用户可能需要注销并重新登录到 Teams。

## <a name="use-the-microsoft-teams-admin-center-to-turn-off-inline-message-translation"></a>使用 Microsoft Teams 管理中心关闭内联消息翻译

在 **Microsoft Teams 管理中心** 中，从左侧导航栏中选择"消息传送策略"，然后创建新策略或编辑现有策略，然后将"翻译消息"选项设置为"**关闭"。**

> [!NOTE]
> 服务执行翻译，并传送给客户端，对合规性记录中捕获的内容没有任何影响。 若要详细了解翻译，请参阅什么是 [Microsoft Translator？](/azure/cognitive-services/translator/translator-info-overview)