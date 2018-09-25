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
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2018
ms.locfileid: "25016834"
---
<a name="use-inline-message-translation-in-microsoft-teams"></a><span data-ttu-id="e0195-103">在 Microsoft Teams 中使用内联消息翻译</span><span class="sxs-lookup"><span data-stu-id="e0195-103">Use inline message translation in Microsoft Teams</span></span> 
=================================================

<span data-ttu-id="e0195-104">内联消息翻译是 Microsoft Teams 的一项新功能，让用户可以自动将 Teams 消息翻译为由自己的 Office 365 个人语言设置指定的[语言](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194)。</span><span class="sxs-lookup"><span data-stu-id="e0195-104">Inline message translation is a new Microsoft Teams feature that lets users automatically translate Teams messages into the [language](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) specified by their personal language settings for Office 365.</span></span>

<span data-ttu-id="e0195-105">内嵌消息转换为要推出默认情况下，为您的组织。</span><span class="sxs-lookup"><span data-stu-id="e0195-105">Inline message translation is being rolled out by default for your organization.</span></span> <span data-ttu-id="e0195-106">如果您想要允许用户使用此团队客户端中的功能，您必须启用此设置使用 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="e0195-106">If you want to allow users to use this feature within the Teams client, you must turn this setting on by using PowerShell.</span></span> <span data-ttu-id="e0195-107">目前，此选项不可用的 Microsoft 团队和 Skype 的业务管理中心中，但将很快。</span><span class="sxs-lookup"><span data-stu-id="e0195-107">Currently, this option is not available in the Microsoft Teams and Skype for Business Admin Center, but will be soon.</span></span>

> [!NOTE]
><span data-ttu-id="e0195-108">对于 Office 365 政府版社区云和 Office 365 Germany 环境中的 Office 365 订阅，不会进行此部署。</span><span class="sxs-lookup"><span data-stu-id="e0195-108">This rollout is excluded from Office 365 subscriptions in our Office 365 Government Community Cloud and Office 365 Germany environments.</span></span> 

## <a name="enable-by-using-powershell"></a><span data-ttu-id="e0195-109">使用 PowerShell 进行启用</span><span class="sxs-lookup"><span data-stu-id="e0195-109">Enable by using PowerShell</span></span>

<span data-ttu-id="e0195-110">可以使用消息策略开启内联消息翻译功能。</span><span class="sxs-lookup"><span data-stu-id="e0195-110">You can turn on the inline message translation feature by using the Messaging Policy.</span></span> 

1. <span data-ttu-id="e0195-111">使用 [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) cmdlet 开启该策略。</span><span class="sxs-lookup"><span data-stu-id="e0195-111">Turn on the policy by using the [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) cmdlet.</span></span>
2. <span data-ttu-id="e0195-112">策略所需几分钟时间来应用。</span><span class="sxs-lookup"><span data-stu-id="e0195-112">The policy takes a few minutes to apply.</span></span> <span data-ttu-id="e0195-113">用户可能需要先注销，然后重新登录到团队。</span><span class="sxs-lookup"><span data-stu-id="e0195-113">Users might need to sign out and sign back in to Teams.</span></span>

## <a name="enable-by-using-the-teams-admin-center"></a><span data-ttu-id="e0195-114">使用 Teams 管理中心进行启用</span><span class="sxs-lookup"><span data-stu-id="e0195-114">Enable by using the Teams Admin Center</span></span>

<span data-ttu-id="e0195-115">即将提供用于使用 Teams 管理中心开启内联消息翻译功能的选项。</span><span class="sxs-lookup"><span data-stu-id="e0195-115">The option to turn on the inline message translation feature by using the Teams Admin Center is coming soon.</span></span>

> [!NOTE]
><span data-ttu-id="e0195-116">翻译严格的客户端，已在合规性的记录中捕获内容没有影响。</span><span class="sxs-lookup"><span data-stu-id="e0195-116">Translation is strictly client-side and has no effect on the content captured in the compliance records.</span></span> <span data-ttu-id="e0195-117">若要了解有关转换的详细信息，请参阅[Microsoft translator （英文） 是什么？](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview)。</span><span class="sxs-lookup"><span data-stu-id="e0195-117">To learn more about translation, see [What is Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).</span></span>