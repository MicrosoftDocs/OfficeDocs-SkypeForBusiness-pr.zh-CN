---
title: 直接从 Teams 回答自动助理和呼叫队列
ms.reviewer: waseemh
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/20/2018
ms.topic: conceptual
ms.service: msteams
description: 介绍云自动助理呼叫的队列，并介绍如何可以应答团队中的这些呼叫。
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: beb4b043798ba5348da1d460f49ff93e6aff55e1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33900927"
---
<a name="answer-auto-attendant-and-call-queue-calls-directly-from-teams"></a><span data-ttu-id="f9ffa-103">直接从 Teams 回答自动助理和呼叫队列</span><span class="sxs-lookup"><span data-stu-id="f9ffa-103">Answer auto attendant and call queue calls directly from Teams</span></span>
===========================================================

<span data-ttu-id="f9ffa-104">团队用户可接收和云自动助理和直接从其团队客户端的呼叫队列从应答呼叫。</span><span class="sxs-lookup"><span data-stu-id="f9ffa-104">Teams users can receive and answer calls from Cloud auto attendants and call queues directly from their Teams client.</span></span> <span data-ttu-id="f9ffa-105">团队用户自动助理功能现已可用，并调用队列功能处于预览。</span><span class="sxs-lookup"><span data-stu-id="f9ffa-105">For Teams users, the auto attendant feature is now generally available, and the call queue capability is in preview.</span></span> 

## <a name="what-are-auto-attendants-and-call-queues"></a><span data-ttu-id="f9ffa-106">什么是自动助理，并调用队列？</span><span class="sxs-lookup"><span data-stu-id="f9ffa-106">What are auto attendants and call queues?</span></span>

<span data-ttu-id="f9ffa-107">云自动助理提供了一系列语音提示或组织到呼叫时，呼叫者听到而不是人工接线员音频文件。</span><span class="sxs-lookup"><span data-stu-id="f9ffa-107">Cloud auto attendants provide a series of voice prompts or an audio file that callers hear instead of a human operator when they call in to an organization.</span></span> <span data-ttu-id="f9ffa-108">自动助理使呼叫者能够移动浏览菜单系统，进行呼叫，或者使用电话键盘 (DTMF) 或采用语音识别功能的语音输入找到用户。</span><span class="sxs-lookup"><span data-stu-id="f9ffa-108">An auto attendant lets callers move through the menu system, place calls, or locate users by using a phone keypad (DTMF) or voice inputs using speech recognition.</span></span>

<span data-ttu-id="f9ffa-109">云呼叫队列包括有人呼叫到您的组织、 能够自动将呼叫置于保持状态，并进行搜索的下一个可用呼叫代理处理该呼叫时调用的人员的功能电话号码时使用的问候语收听保持音乐。</span><span class="sxs-lookup"><span data-stu-id="f9ffa-109">Cloud call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold.</span></span> <span data-ttu-id="f9ffa-110">您可以为组织创建单个或多个呼叫的队列。</span><span class="sxs-lookup"><span data-stu-id="f9ffa-110">You can create single or multiple call queues for your organization.</span></span>

## <a name="handling-an-auto-attendant-or-call-queue-call"></a><span data-ttu-id="f9ffa-111">处理的自动助理或呼叫队列呼叫</span><span class="sxs-lookup"><span data-stu-id="f9ffa-111">Handling an auto attendant or call queue call</span></span>

<span data-ttu-id="f9ffa-112">用户将能够它们应答呼叫之前区分传入呼叫自动助理或呼叫的队列。</span><span class="sxs-lookup"><span data-stu-id="f9ffa-112">Users will be able to differentiate incoming calls from an auto attendant or call queue before they answer the call.</span></span> <span data-ttu-id="f9ffa-113">名称和/或将呼叫者数量，以及每个呼叫将包含有关谁将呼叫者尝试通，为用户提供了更好的上下文，解决呼叫者的信息。</span><span class="sxs-lookup"><span data-stu-id="f9ffa-113">Along with the name and/or number of the caller, each call will include information about who the caller was trying to reach, giving users a better context for addressing the caller.</span></span>

<span data-ttu-id="f9ffa-114">下图显示来自自动助理或呼叫队列的传入呼叫到用户的显示方式。</span><span class="sxs-lookup"><span data-stu-id="f9ffa-114">The following illustration shows how an incoming call from an auto attendant or call queue will appear to a user.</span></span>

![传入呼叫通知](media/answer-auto-attendant-and-call-queue-calls-image1.png)

<span data-ttu-id="f9ffa-116">一旦应答自动助理或呼叫队列呼叫时，用户可以处理与任何其他呼叫 & #x 2014; 一样调用他们可以添加或另一个用户或转接到另一方呼叫中的会议。</span><span class="sxs-lookup"><span data-stu-id="f9ffa-116">Once an auto attendant or call queue call is answered, the user can process the call like any other call &#x2014; they can add or conference in another user or transfer the call to another party.</span></span> <span data-ttu-id="f9ffa-117">此外，自动助理将呼叫转接基于用户的配置。</span><span class="sxs-lookup"><span data-stu-id="f9ffa-117">Also, auto attendant calls will be forwarded based on the user’s configuration.</span></span>

> [!NOTE] 
> <span data-ttu-id="f9ffa-118">调用基于用户的配置不转接呼叫的队列。</span><span class="sxs-lookup"><span data-stu-id="f9ffa-118">Call queue calls are not forwarded based on the user’s configuration.</span></span> <span data-ttu-id="f9ffa-119">这是为了确保代理可以应答呼叫之前，呼叫者保持队列中没有意外转接呼叫者。</span><span class="sxs-lookup"><span data-stu-id="f9ffa-119">This is to ensure callers remain in the queue until an agent can answer the call and the caller isn’t forwarded unexpectedly.</span></span>

## <a name="supported-clients"></a><span data-ttu-id="f9ffa-120">支持的客户端</span><span class="sxs-lookup"><span data-stu-id="f9ffa-120">Supported clients</span></span>

<span data-ttu-id="f9ffa-121">对于自动助理和呼叫队列呼叫支持以下客户端有：</span><span class="sxs-lookup"><span data-stu-id="f9ffa-121">Support for auto attendant and call queue calls is available in the following clients:</span></span>

-   <span data-ttu-id="f9ffa-122">Microsoft Teams Windows 客户端 （32 和 64 位版本）</span><span class="sxs-lookup"><span data-stu-id="f9ffa-122">Microsoft Teams Windows client (32 and 64-bit versions)</span></span>
-   <span data-ttu-id="f9ffa-123">Microsoft Teams Mac 客户端</span><span class="sxs-lookup"><span data-stu-id="f9ffa-123">Microsoft Teams Mac client</span></span>
-   <span data-ttu-id="f9ffa-124">Microsoft Teams iPhone 应用</span><span class="sxs-lookup"><span data-stu-id="f9ffa-124">Microsoft Teams iPhone app</span></span>
-   <span data-ttu-id="f9ffa-125">Microsoft Teams Android 应用</span><span class="sxs-lookup"><span data-stu-id="f9ffa-125">Microsoft Teams Android app</span></span>

## <a name="configure-auto-attendant-and-call-queue-support-for-microsoft-teams"></a><span data-ttu-id="f9ffa-126">配置支持的 Microsoft 团队的自动助理和呼叫队列</span><span class="sxs-lookup"><span data-stu-id="f9ffa-126">Configure auto attendant and call queue support for Microsoft Teams</span></span>

<span data-ttu-id="f9ffa-127">若要接收自动助理和上的 Microsoft 团队呼叫队列呼叫，您需要配置您的互操作性策略和升级策略。</span><span class="sxs-lookup"><span data-stu-id="f9ffa-127">To receive auto attendant and call queue calls on Microsoft Teams, you need to configure your interoperability policy and upgrade policy.</span></span> <span data-ttu-id="f9ffa-128">请查看[迁移和组织使用团队一起 for Business 的 Skype 的互操作性](migration-interop-guidance-for-teams-with-skype.md)。</span><span class="sxs-lookup"><span data-stu-id="f9ffa-128">Please review [Migration and interoperability for organizations using Teams together with Skype for Business](migration-interop-guidance-for-teams-with-skype.md).</span></span> <span data-ttu-id="f9ffa-129">如果您没有自动助理和/或呼叫队列配置，并且想要为此，请参阅[设置云自动助理](https://docs.microsoft.com/skypeforbusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant)和[创建云呼叫队列](https://docs.microsoft.com/skypeforbusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)。</span><span class="sxs-lookup"><span data-stu-id="f9ffa-129">If you do not have auto attendant and/or call queue configured and would like to do so, see [Set up a Cloud auto attendant](https://docs.microsoft.com/skypeforbusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant) and [Create a Cloud call queue](https://docs.microsoft.com/skypeforbusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue).</span></span>

## <a name="related-topics"></a><span data-ttu-id="f9ffa-130">相关主题</span><span class="sxs-lookup"><span data-stu-id="f9ffa-130">Related topics</span></span>

-   [<span data-ttu-id="f9ffa-131">什么是 Office 365 中的电话系统</span><span class="sxs-lookup"><span data-stu-id="f9ffa-131">What is Phone System in Office 365</span></span>](what-is-phone-system-in-office-365.md)
-   [<span data-ttu-id="f9ffa-132">创建云呼叫队列</span><span class="sxs-lookup"><span data-stu-id="f9ffa-132">Create a Cloud call queue</span></span>](https://docs.microsoft.com/skypeforbusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)
-   [<span data-ttu-id="f9ffa-133">什么是云自动助理？</span><span class="sxs-lookup"><span data-stu-id="f9ffa-133">What are Cloud auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)
-   [<span data-ttu-id="f9ffa-134">设置云自动助理</span><span class="sxs-lookup"><span data-stu-id="f9ffa-134">Set up a Cloud auto attendant</span></span>](https://docs.microsoft.com/skypeforbusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant)

