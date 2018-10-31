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
ms.openlocfilehash: 69c6e8046b185cc8dbc85ac0c99dc5b4cfa6fe2a
ms.sourcegitcommit: bb3f235265cddae9578ec1bf605c4edc7f14fb30
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25851565"
---
<a name="use-inline-message-translation-in-microsoft-teams"></a><span data-ttu-id="df072-103">在 Microsoft Teams 中使用内联消息翻译</span><span class="sxs-lookup"><span data-stu-id="df072-103">Use inline message translation in Microsoft Teams</span></span> 
=================================================

<span data-ttu-id="df072-104">内联消息翻译是 Microsoft Teams 的一项新功能，让用户可以自动将 Teams 消息翻译为由自己的 Office 365 个人语言设置指定的[语言](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194)。</span><span class="sxs-lookup"><span data-stu-id="df072-104">Inline message translation is a new Microsoft Teams feature that lets users automatically translate Teams messages into the [language](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) specified by their personal language settings for Office 365.</span></span>

<span data-ttu-id="df072-105">默认会为贵组织部署内联消息翻译。</span><span class="sxs-lookup"><span data-stu-id="df072-105">Inline message translation is being rolled out by default for your organization.</span></span> <span data-ttu-id="df072-106">如果你希望允许用户在 Teams 客户端中使用此功能，必须使用 PowerShell 开启此设置。</span><span class="sxs-lookup"><span data-stu-id="df072-106">If you want to allow users to use this feature within the Teams client, you must turn this setting on by using PowerShell.</span></span> <span data-ttu-id="df072-107">当前，Microsoft Teams 和 Skype for Business 管理中心中未提供此选项，但不久将会提供。</span><span class="sxs-lookup"><span data-stu-id="df072-107">Currently, this option is not available in the Microsoft Teams and Skype for Business Admin Center, but will be soon.</span></span>

> [!NOTE]
><span data-ttu-id="df072-108">对于 Office 365 政府版社区云和 Office 365 Germany 环境中的 Office 365 订阅，不会进行此部署。</span><span class="sxs-lookup"><span data-stu-id="df072-108">This rollout is excluded from Office 365 subscriptions in our Office 365 Government Community Cloud and Office 365 Germany environments.</span></span> 

## <a name="enable-by-using-powershell"></a><span data-ttu-id="df072-109">使用 PowerShell 进行启用</span><span class="sxs-lookup"><span data-stu-id="df072-109">Enable by using PowerShell</span></span>

<span data-ttu-id="df072-110">可以使用消息策略开启内联消息翻译功能。</span><span class="sxs-lookup"><span data-stu-id="df072-110">You can turn on the inline message translation feature by using the Messaging Policy.</span></span> 

1. <span data-ttu-id="df072-111">使用 [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) cmdlet 开启该策略。</span><span class="sxs-lookup"><span data-stu-id="df072-111">Turn on the policy by using the [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) cmdlet.</span></span>
2. <span data-ttu-id="df072-112">该策略将在几分钟后应用。</span><span class="sxs-lookup"><span data-stu-id="df072-112">The policy takes a few minutes to apply.</span></span> <span data-ttu-id="df072-113">用户可能需要注销并重新登录 Teams。</span><span class="sxs-lookup"><span data-stu-id="df072-113">Users might need to sign out and sign back in to Teams.</span></span>

## <a name="enable-by-using-the-microsoft-teams--skype-for-business-admin-center"></a><span data-ttu-id="df072-114">使用 Microsoft 团队和 Skype for Business Admin Center 启用</span><span class="sxs-lookup"><span data-stu-id="df072-114">Enable by using the Microsoft Teams & Skype for Business Admin Center</span></span>

<span data-ttu-id="df072-115">选项可打开内嵌消息转换功能使用的 Microsoft 团队 Skype for Business Admin Center 即将提供。</span><span class="sxs-lookup"><span data-stu-id="df072-115">The option to turn on the inline message translation feature using the Microsoft Teams & Skype for Business Admin Center is coming soon.</span></span>

> [!NOTE]
><span data-ttu-id="df072-116">翻译是完全在客户端上运行的，对在合规性记录中捕获的内容没有任何影响。</span><span class="sxs-lookup"><span data-stu-id="df072-116">Translation is strictly client-side and has no effect on the content captured in the compliance records.</span></span> <span data-ttu-id="df072-117">要详细了解翻译，请参阅[什么是 Microsoft Translator？](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview)</span><span class="sxs-lookup"><span data-stu-id="df072-117">To learn more about translation, see [What is Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).</span></span>