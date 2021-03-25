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
<a name="turn-off-inline-message-translation-in-microsoft-teams"></a><span data-ttu-id="dfd34-103">在 Microsoft Teams 中关闭内联消息翻译</span><span class="sxs-lookup"><span data-stu-id="dfd34-103">Turn off inline message translation in Microsoft Teams</span></span>
=================================================

<span data-ttu-id="dfd34-104">内联消息翻译是 Microsoft Teams 的一项功能，允许用户将[](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194)Teams 消息翻译成其个人语言设置指定的语言。</span><span class="sxs-lookup"><span data-stu-id="dfd34-104">Inline message translation is a Microsoft Teams feature that lets users translate Teams messages into the [language](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) specified by their personal language settings.</span></span>

<span data-ttu-id="dfd34-105">默认情况下，为组织推出内联邮件翻译。</span><span class="sxs-lookup"><span data-stu-id="dfd34-105">Inline message translation is rolled out by default for your organization.</span></span> <span data-ttu-id="dfd34-106">如果希望允许用户在 Teams 客户端内使用此功能，无需进行更改。</span><span class="sxs-lookup"><span data-stu-id="dfd34-106">You don't need to make changes if you want to allow users to use this feature within the Teams client.</span></span>

> [!NOTE]
><span data-ttu-id="dfd34-107">此推出不包括在我们的 Office 365 政府社区云和 Office 365 Germany 环境的 Office 365 订阅中。</span><span class="sxs-lookup"><span data-stu-id="dfd34-107">This rollout is excluded from Office 365 subscriptions in our Office 365 Government Community Cloud and Office 365 Germany environments.</span></span>

## <a name="use-powershell-to-turn-off-inline-message-translation"></a><span data-ttu-id="dfd34-108">使用 PowerShell 关闭内联消息翻译</span><span class="sxs-lookup"><span data-stu-id="dfd34-108">Use PowerShell to turn off inline message translation</span></span>

<span data-ttu-id="dfd34-109">可以使用消息传送策略关闭内联邮件翻译。</span><span class="sxs-lookup"><span data-stu-id="dfd34-109">You can use the messaging policy to turn off the inline message translation.</span></span>

<span data-ttu-id="dfd34-110">使用 [Set-CsTeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) cmdlet 关闭策略。</span><span class="sxs-lookup"><span data-stu-id="dfd34-110">Turn off the policy by using the [Set-CsTeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="dfd34-111">应用策略需要几分钟时间。</span><span class="sxs-lookup"><span data-stu-id="dfd34-111">The policy takes a few minutes to apply.</span></span> <span data-ttu-id="dfd34-112">用户可能需要注销并重新登录到 Teams。</span><span class="sxs-lookup"><span data-stu-id="dfd34-112">Users might need to sign out and sign back in to Teams.</span></span>

## <a name="use-the-microsoft-teams-admin-center-to-turn-off-inline-message-translation"></a><span data-ttu-id="dfd34-113">使用 Microsoft Teams 管理中心关闭内联消息翻译</span><span class="sxs-lookup"><span data-stu-id="dfd34-113">Use the Microsoft Teams admin center to turn off inline message translation</span></span>

<span data-ttu-id="dfd34-114">在 **Microsoft Teams 管理中心** 中，从左侧导航栏中选择"消息传送策略"，然后创建新策略或编辑现有策略，然后将"翻译消息"选项设置为"**关闭"。**</span><span class="sxs-lookup"><span data-stu-id="dfd34-114">In the **Microsoft Teams admin center**, select **Messaging Policies** from the left navigation, then either create a new policy or edit an existing policy, and set the **Translate messages** option to **Off**.</span></span>

> [!NOTE]
> <span data-ttu-id="dfd34-115">服务执行翻译，并传送给客户端，对合规性记录中捕获的内容没有任何影响。</span><span class="sxs-lookup"><span data-stu-id="dfd34-115">The service does the translation and delivers it to the client with no effect on the content captured in the compliance records.</span></span> <span data-ttu-id="dfd34-116">若要详细了解翻译，请参阅什么是 [Microsoft Translator？](/azure/cognitive-services/translator/translator-info-overview)</span><span class="sxs-lookup"><span data-stu-id="dfd34-116">To learn more about translation, see [What is Microsoft Translator?](/azure/cognitive-services/translator/translator-info-overview)</span></span>