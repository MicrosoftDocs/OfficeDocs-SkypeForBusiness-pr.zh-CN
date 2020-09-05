---
title: 打开内联消息转换
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
description: 了解如何使用 Microsoft 团队管理中心或 PowerShell 在 Microsoft 团队中打开内联翻译。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 012f2431ec7fb249a2f2e3b963c41166c4649a5c
ms.sourcegitcommit: 2e6b0930645cd97dbd597e9346a6fe1788c6facf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2020
ms.locfileid: "47395381"
---
<a name="turn-off-inline-message-translation-in-microsoft-teams"></a><span data-ttu-id="6cbdf-103">关闭 Microsoft 团队中的内联邮件翻译</span><span class="sxs-lookup"><span data-stu-id="6cbdf-103">Turn off inline message translation in Microsoft Teams</span></span>
=================================================

<span data-ttu-id="6cbdf-104">内联邮件转换是 Microsoft 团队的一项功能，使用户能够将团队邮件转换为由其个人语言设置指定的 [语言](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) 。</span><span class="sxs-lookup"><span data-stu-id="6cbdf-104">Inline message translation is a Microsoft Teams feature that lets users translate Teams messages into the [language](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) specified by their personal language settings.</span></span>

<span data-ttu-id="6cbdf-105">默认情况下，对于您的组织，内联邮件转换已被默认滚动。</span><span class="sxs-lookup"><span data-stu-id="6cbdf-105">Inline message translation is rolled out by default for your organization.</span></span> <span data-ttu-id="6cbdf-106">如果您希望允许用户在团队客户端中使用此功能，则无需进行更改。</span><span class="sxs-lookup"><span data-stu-id="6cbdf-106">You don't need to make changes if you want to allow users to use this feature within the Teams client.</span></span>

> [!NOTE]
><span data-ttu-id="6cbdf-107">我们的 Office 365 政府社区云和 Office 365 德国环境中的 Office 365 订阅不包括此推出。</span><span class="sxs-lookup"><span data-stu-id="6cbdf-107">This rollout is excluded from Office 365 subscriptions in our Office 365 Government Community Cloud and Office 365 Germany environments.</span></span>

## <a name="use-powershell-to-turn-off-inline-message-translation"></a><span data-ttu-id="6cbdf-108">使用 PowerShell 关闭内联邮件转换</span><span class="sxs-lookup"><span data-stu-id="6cbdf-108">Use PowerShell to turn off inline message translation</span></span>

<span data-ttu-id="6cbdf-109">可以使用消息策略关闭内联邮件转换。</span><span class="sxs-lookup"><span data-stu-id="6cbdf-109">You can use the messaging policy to turn off the inline message translation.</span></span>

<span data-ttu-id="6cbdf-110">使用 [CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) cmdlet 关闭该策略。</span><span class="sxs-lookup"><span data-stu-id="6cbdf-110">Turn off the policy by using the [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="6cbdf-111">策略需要几分钟才能应用。</span><span class="sxs-lookup"><span data-stu-id="6cbdf-111">The policy takes a few minutes to apply.</span></span> <span data-ttu-id="6cbdf-112">用户可能需要注销并重新登录到团队。</span><span class="sxs-lookup"><span data-stu-id="6cbdf-112">Users might need to sign out and sign back in to Teams.</span></span>

## <a name="use-the-microsoft-teams-admin-center-to-turn-off-inline-message-translation"></a><span data-ttu-id="6cbdf-113">使用 Microsoft 团队管理中心关闭内联邮件翻译</span><span class="sxs-lookup"><span data-stu-id="6cbdf-113">Use the Microsoft Teams admin center to turn off inline message translation</span></span>

<span data-ttu-id="6cbdf-114">在 **Microsoft 团队管理中心**中，从左侧导航中选择 " **邮件策略** "，然后创建新策略或编辑现有策略，并将 " **翻译邮件** " 选项设置为 " **关闭**"。</span><span class="sxs-lookup"><span data-stu-id="6cbdf-114">In the **Microsoft Teams admin center**, select **Messaging Policies** from the left navigation, then either create a new policy or edit an existing policy, and set the **Translate messages** option to **Off**.</span></span>

> [!NOTE]
> <span data-ttu-id="6cbdf-115">该服务执行翻译，并将其传递给客户，而不会影响合规性记录中捕获的内容。</span><span class="sxs-lookup"><span data-stu-id="6cbdf-115">The service does the translation and delivers it to the client with no effect on the content captured in the compliance records.</span></span> <span data-ttu-id="6cbdf-116">若要了解有关翻译的详细信息，请参阅 [什么是 Microsoft Translator？](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview)</span><span class="sxs-lookup"><span data-stu-id="6cbdf-116">To learn more about translation, see [What is Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview)</span></span>
