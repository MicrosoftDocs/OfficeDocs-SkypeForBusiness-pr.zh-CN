---
title: 在 Microsoft Teams 中使用内联消息翻译
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 10/30/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.reviewer: salilda
localization_priority: Normal
search.appverid: MET150
description: 了解如何在 Microsoft Teams 中使用内联翻译
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 466160616adea80a2fcb6a3bfd035ca397d73754
ms.sourcegitcommit: 31827526894ffb75d64fcb0a7c76ee874ad3c269
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2019
ms.locfileid: "29754423"
---
<a name="use-inline-message-translation-in-microsoft-teams"></a>在 Microsoft Teams 中使用内联消息翻译 
=================================================

内联消息翻译是 Microsoft Teams 的一项新功能，让用户可以自动将 Teams 消息翻译为由自己的 Office 365 个人语言设置指定的[语言](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194)。

默认会为贵组织部署内联消息翻译。 如果您想要允许用户使用此团队客户端中的功能，您必须启用此设置。

> [!NOTE]
>从我们的 Office 365 政府社区云和 Office 365 德国环境中的 Office 365 订阅排除此推出。

## <a name="enable-by-using-powershell"></a>使用 PowerShell 启用

您可以使用邮件策略来启用内嵌消息转换功能。

1. 使用[组 CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) cmdlet 来启用在策略。
2. 策略所需几分钟时间来应用。 用户可能需要先注销，然后重新登录到团队。

## <a name="enable-by-using-the-microsoft-teams-admin-center"></a>使用 Microsoft 团队管理中心启用

在**Microsoft 团队管理中心**中，从左侧栏中选择**消息的策略**，然后或者是创建新的策略或编辑现有策略，请设置为**上**的**允许用户将邮件**选项。

> [!NOTE]
>翻译是由服务完成和传送到捕获的合规性记录中的内容不影响客户端。 若要了解有关转换的详细信息，请参阅[Microsoft translator （英文） 是什么？](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview)。