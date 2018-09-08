---
title: 使用中的 Microsoft 团队的内嵌消息转换
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 08/16/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: salilda
localization_priority: Normal
search.appverid: MET150
description: 了解如何使用中的 Microsoft 团队内联转换。
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 191fe1e5517fdce9aba6fd17e084c866df200e82
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23882905"
---
<a name="use-inline-message-translation-in-microsoft-teams"></a>使用中的 Microsoft 团队的内嵌消息转换 
=================================================

内嵌消息转换为新的 Microsoft 团队功能，它允许用户自动将团队邮件转换为所指定的 Office 365 其个人语言设置的[语言](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194)。

内嵌消息转换为要推出默认情况下，为您的组织。 如果您想要允许用户使用此团队客户端中的功能，您必须启用此设置使用 PowerShell。 目前，此选项不可用的 Microsoft 团队和 Skype 的业务管理中心中，但将很快。

> [!NOTE]
>从我们的 Office 365 政府社区云和 Office 365 德国环境中的 Office 365 订阅排除此推出。 

## <a name="enable-by-using-powershell"></a>使用 PowerShell 启用

您可以使用邮件策略来启用内嵌消息转换功能。 

1. 使用[组 CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) cmdlet 来启用在策略。
2. 策略所需几分钟时间来应用。 用户可能需要先注销，然后重新登录到团队。

## <a name="enable-by-using-the-teams-admin-center"></a>使用团队 Admin Center 启用

通过使用团队管理中心打开内嵌消息转换功能的选项即将提供。

> [!NOTE]
>翻译严格的客户端，已在合规性的记录中捕获内容没有影响。 若要了解有关转换的详细信息，请参阅[Microsoft translator （英文） 是什么？](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview)。