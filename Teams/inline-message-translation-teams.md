---
title: 在 Microsoft 团队中启用内联邮件翻译
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 06/21/2019
audience: Admin
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: salilda
localization_priority: Normal
search.appverid: MET150
description: 了解如何在 Microsoft Teams 中使用内联翻译
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: dfd0582837b2e9c9859b44292255e5e42a2f35a4
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/25/2019
ms.locfileid: "35222066"
---
<a name="turn-on-inline-message-translation-in-microsoft-teams"></a>在 Microsoft 团队中启用内联邮件翻译 
=================================================

内联消息翻译是 Microsoft Teams 的一项新功能，让用户可以自动将 Teams 消息翻译为由自己的 Office 365 个人语言设置指定的[语言](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194)。

默认会为贵组织部署内联消息翻译。 如果您希望允许用户在团队客户端中使用此功能, 则必须启用此设置。

> [!NOTE]
>我们的 Office 365 政府社区云和 Office 365 德国环境中的 Office 365 订阅不包括此推出。

## <a name="use-powershell-to-turn-on-inline-message-translation"></a>使用 PowerShell 打开内联消息转换

可以使用消息策略打开内联邮件转换。

使用[CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) cmdlet 打开该策略。 策略需要几分钟才能应用。 用户可能需要注销并重新登录到团队。

## <a name="use-the-microsoft-teams-admin-center-to-turn-on-inline-message-translation"></a>使用 Microsoft 团队管理中心打开内联邮件翻译

在**Microsoft 团队管理中心**中, 从左侧导航中选择 "**邮件策略**", 然后创建新策略或编辑现有策略, 并将 "**允许用户将邮件翻译**为" 选项设置为 **"打开**"。

> [!NOTE]
> 该服务执行翻译, 并将其传递给客户, 而不会影响合规性记录中捕获的内容。 若要了解有关翻译的详细信息, 请参阅[什么是 Microsoft Translator？](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview)。