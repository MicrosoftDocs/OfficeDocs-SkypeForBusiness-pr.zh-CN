---
title: 在 Microsoft 团队中启用内联邮件翻译
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
description: 了解如何在 Microsoft Teams 中使用内联翻译
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1926f574977f65181f12ddbb9f0239ad1547d1e5
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836632"
---
<a name="turn-on-inline-message-translation-in-microsoft-teams"></a><span data-ttu-id="deea7-103">在 Microsoft 团队中启用内联邮件翻译</span><span class="sxs-lookup"><span data-stu-id="deea7-103">Turn on inline message translation in Microsoft Teams</span></span> 
=================================================

<span data-ttu-id="deea7-104">内联邮件转换是一种新的 Microsoft 团队功能，可让用户将团队邮件转换为 Office 365 的个人语言设置所指定的[语言](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194)。</span><span class="sxs-lookup"><span data-stu-id="deea7-104">Inline message translation is a new Microsoft Teams feature that lets users translate Teams messages into the [language](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) specified by their personal language settings for Office 365.</span></span>

<span data-ttu-id="deea7-105">默认会为贵组织部署内联消息翻译。</span><span class="sxs-lookup"><span data-stu-id="deea7-105">Inline message translation is being rolled out by default for your organization.</span></span> <span data-ttu-id="deea7-106">如果您希望允许用户在团队客户端中使用此功能，则必须启用此设置。</span><span class="sxs-lookup"><span data-stu-id="deea7-106">If you want to allow users to use this feature within the Teams client, you must turn this setting on.</span></span>

> [!NOTE]
><span data-ttu-id="deea7-107">我们的 Office 365 政府社区云和 Office 365 德国环境中的 Office 365 订阅不包括此推出。</span><span class="sxs-lookup"><span data-stu-id="deea7-107">This rollout is excluded from Office 365 subscriptions in our Office 365 Government Community Cloud and Office 365 Germany environments.</span></span>

## <a name="use-powershell-to-turn-on-inline-message-translation"></a><span data-ttu-id="deea7-108">使用 PowerShell 打开内联消息转换</span><span class="sxs-lookup"><span data-stu-id="deea7-108">Use PowerShell to turn on inline message translation</span></span>

<span data-ttu-id="deea7-109">可以使用消息策略打开内联邮件转换。</span><span class="sxs-lookup"><span data-stu-id="deea7-109">You can use the messaging policy to turn on the inline message translation.</span></span>

<span data-ttu-id="deea7-110">使用[CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) cmdlet 打开该策略。</span><span class="sxs-lookup"><span data-stu-id="deea7-110">Turn on the policy by using the [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="deea7-111">策略需要几分钟才能应用。</span><span class="sxs-lookup"><span data-stu-id="deea7-111">The policy takes a few minutes to apply.</span></span> <span data-ttu-id="deea7-112">用户可能需要注销并重新登录到团队。</span><span class="sxs-lookup"><span data-stu-id="deea7-112">Users might need to sign out and sign back in to Teams.</span></span>

## <a name="use-the-microsoft-teams-admin-center-to-turn-on-inline-message-translation"></a><span data-ttu-id="deea7-113">使用 Microsoft 团队管理中心打开内联邮件翻译</span><span class="sxs-lookup"><span data-stu-id="deea7-113">Use the Microsoft Teams admin center to turn on inline message translation</span></span>

<span data-ttu-id="deea7-114">在**Microsoft 团队管理中心**中，从左侧导航中选择 "**邮件策略**"，然后创建新策略或编辑现有策略，并将 "**允许用户将邮件翻译**为" 选项设置为 **"打开**"。</span><span class="sxs-lookup"><span data-stu-id="deea7-114">In the **Microsoft Teams admin center**, select **Messaging Policies** from the left navigation, then either create a new policy or edit an existing policy, and set the **Allow users to translate messages** option to **On**.</span></span>

> [!NOTE]
> <span data-ttu-id="deea7-115">该服务执行翻译，并将其传递给客户，而不会影响合规性记录中捕获的内容。</span><span class="sxs-lookup"><span data-stu-id="deea7-115">The service does the translation and delivers it to the client with no effect on the content captured in the compliance records.</span></span> <span data-ttu-id="deea7-116">若要了解有关翻译的详细信息，请参阅[什么是 Microsoft Translator？](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview)。</span><span class="sxs-lookup"><span data-stu-id="deea7-116">To learn more about translation, see [What is Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).</span></span>