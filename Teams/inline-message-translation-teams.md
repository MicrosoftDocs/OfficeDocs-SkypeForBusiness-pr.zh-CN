---
title: 在 Microsoft Teams 中使用内联消息翻译
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 08/16/2018
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
ms.openlocfilehash: 9097e7421bb65b1a9ce0900df097080a6cfc2023
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2018
ms.locfileid: "26296393"
---
<a name="use-inline-message-translation-in-microsoft-teams"></a>在 Microsoft Teams 中使用内联消息翻译 
=================================================

内联消息翻译是 Microsoft Teams 的一项新功能，让用户可以自动将 Teams 消息翻译为由自己的 Office 365 个人语言设置指定的[语言](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194)。

默认会为贵组织部署内联消息翻译。 如果你希望允许用户在 Teams 客户端中使用此功能，必须使用 PowerShell 开启此设置。 当前，Microsoft Teams 和 Skype for Business 管理中心中未提供此选项，但不久将会提供。

> [!NOTE]
>对于 Office 365 政府版社区云和 Office 365 Germany 环境中的 Office 365 订阅，不会进行此部署。 

## <a name="enable-by-using-powershell"></a>使用 PowerShell 进行启用

可以使用消息策略开启内联消息翻译功能。 

1. 使用 [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) cmdlet 开启该策略。
2. 该策略将在几分钟后应用。 用户可能需要注销并重新登录 Teams。

## <a name="enable-by-using-the-teams-admin-center"></a>使用 Teams 管理中心进行启用

即将提供用于使用 Teams 管理中心开启内联消息翻译功能的选项。

> [!NOTE]
>翻译是完全在客户端上运行的，对在合规性记录中捕获的内容没有任何影响。 要详细了解翻译，请参阅[什么是 Microsoft Translator？](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview)