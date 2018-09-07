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
localization_priority: Priority
search.appverid: MET150
description: 了解如何使用中的 Microsoft 团队内联转换。
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: eb7876d015fb736785fdaab99b1ed71b8e05b9dc
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23855818"
---
<a name="use-inline-message-translation-in-microsoft-teams"></a><span data-ttu-id="90fc1-103">使用中的 Microsoft 团队的内嵌消息转换</span><span class="sxs-lookup"><span data-stu-id="90fc1-103">Use inline message translation in Microsoft Teams</span></span> 
=================================================

<span data-ttu-id="90fc1-104">内嵌消息转换为新的 Microsoft 团队功能，它允许用户自动将团队邮件转换为所指定的 Office 365 其个人语言设置的[语言](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194)。</span><span class="sxs-lookup"><span data-stu-id="90fc1-104">Inline message translation is a new Microsoft Teams feature that lets users automatically translate Teams messages into the [language](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) specified by their personal language settings for Office 365.</span></span>

<span data-ttu-id="90fc1-105">内嵌消息转换为要推出默认情况下，为您的组织。</span><span class="sxs-lookup"><span data-stu-id="90fc1-105">Inline message translation is being rolled out by default for your organization.</span></span> <span data-ttu-id="90fc1-106">如果您想要允许用户使用此团队客户端中的功能，您必须启用此设置使用 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="90fc1-106">If you want to allow users to use this feature within the Teams client, you must turn this setting on by using PowerShell.</span></span> <span data-ttu-id="90fc1-107">目前，此选项不可用的 Microsoft 团队和 Skype 的业务管理中心中，但将很快。</span><span class="sxs-lookup"><span data-stu-id="90fc1-107">Currently, this option is not available in the Microsoft Teams and Skype for Business Admin Center, but will be soon.</span></span>

> [!NOTE]
><span data-ttu-id="90fc1-108">从我们的 Office 365 政府社区云和 Office 365 德国环境中的 Office 365 订阅排除此推出。</span><span class="sxs-lookup"><span data-stu-id="90fc1-108">This rollout is excluded from Office 365 subscriptions in our Office 365 Government Community Cloud and Office 365 Germany environments.</span></span> 

## <a name="enable-by-using-powershell"></a><span data-ttu-id="90fc1-109">使用 PowerShell 启用</span><span class="sxs-lookup"><span data-stu-id="90fc1-109">Enable by using PowerShell</span></span>

<span data-ttu-id="90fc1-110">您可以使用邮件策略来启用内嵌消息转换功能。</span><span class="sxs-lookup"><span data-stu-id="90fc1-110">You can turn on the inline message translation feature by using the Messaging Policy.</span></span> 

1. <span data-ttu-id="90fc1-111">使用[组 CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) cmdlet 来启用在策略。</span><span class="sxs-lookup"><span data-stu-id="90fc1-111">Turn on the policy by using the [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) cmdlet.</span></span>
2. <span data-ttu-id="90fc1-112">策略所需几分钟时间来应用。</span><span class="sxs-lookup"><span data-stu-id="90fc1-112">The policy takes a few minutes to apply.</span></span> <span data-ttu-id="90fc1-113">用户可能需要先注销，然后重新登录到团队。</span><span class="sxs-lookup"><span data-stu-id="90fc1-113">Users might need to sign out and sign back in to Teams.</span></span>

## <a name="enable-by-using-the-teams-admin-center"></a><span data-ttu-id="90fc1-114">使用团队 Admin Center 启用</span><span class="sxs-lookup"><span data-stu-id="90fc1-114">Enable by using the Teams Admin Center</span></span>

<span data-ttu-id="90fc1-115">通过使用团队管理中心打开内嵌消息转换功能的选项即将提供。</span><span class="sxs-lookup"><span data-stu-id="90fc1-115">The option to turn on the inline message translation feature by using the Teams Admin Center is coming soon.</span></span>

> [!NOTE]
><span data-ttu-id="90fc1-116">翻译严格的客户端，已在合规性的记录中捕获内容没有影响。</span><span class="sxs-lookup"><span data-stu-id="90fc1-116">Translation is strictly client-side and has no effect on the content captured in the compliance records.</span></span> <span data-ttu-id="90fc1-117">若要了解有关转换的详细信息，请参阅[Microsoft translator （英文） 是什么？](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview)。</span><span class="sxs-lookup"><span data-stu-id="90fc1-117">To learn more about translation, see [What is Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).</span></span>