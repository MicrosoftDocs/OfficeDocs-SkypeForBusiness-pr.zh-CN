---
title: 直接从 Teams 回答自动助理和呼叫队列
ms.reviewer: waseemh
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/20/2018
ms.topic: conceptual
ms.service: msteams
description: 介绍云自动助理和通话队列, 并介绍如何在团队中回答这些呼叫。
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a78ed7e0bb40d83f7b46d4d4a008f964180c32d0
ms.sourcegitcommit: a47f0841b9a14ede65171a817ecb7ebc72f209e5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2019
ms.locfileid: "34185292"
---
<a name="answer-auto-attendant-and-call-queue-calls-directly-from-teams"></a><span data-ttu-id="9b0d5-103">直接从 Teams 回答自动助理和呼叫队列</span><span class="sxs-lookup"><span data-stu-id="9b0d5-103">Answer auto attendant and call queue calls directly from Teams</span></span>
===========================================================

<span data-ttu-id="9b0d5-104">团队用户可以直接从其团队客户端接收和应答来自云自动助理的调用和调用队列。</span><span class="sxs-lookup"><span data-stu-id="9b0d5-104">Teams users can receive and answer calls from Cloud auto attendants and call queues directly from their Teams client.</span></span> <span data-ttu-id="9b0d5-105">对于团队用户, "自动助理" 功能现在通常可用, 并且呼叫队列功能位于 "预览" 中。</span><span class="sxs-lookup"><span data-stu-id="9b0d5-105">For Teams users, the auto attendant feature is now generally available, and the call queue capability is in preview.</span></span> 

## <a name="what-are-auto-attendants-and-call-queues"></a><span data-ttu-id="9b0d5-106">什么是自动助理和呼叫队列？</span><span class="sxs-lookup"><span data-stu-id="9b0d5-106">What are auto attendants and call queues?</span></span>

<span data-ttu-id="9b0d5-107">云自动助理提供一系列语音提示或音频文件, 当呼叫者呼叫组织时, 呼叫者将听到该提示, 而不是人工操作员。</span><span class="sxs-lookup"><span data-stu-id="9b0d5-107">Cloud auto attendants provide a series of voice prompts or an audio file that callers hear instead of a human operator when they call in to an organization.</span></span> <span data-ttu-id="9b0d5-108">自动助理使呼叫者能够移动浏览菜单系统，进行呼叫，或者使用电话键盘 (DTMF) 或采用语音识别功能的语音输入找到用户。</span><span class="sxs-lookup"><span data-stu-id="9b0d5-108">An auto attendant lets callers move through the menu system, place calls, or locate users by using a phone keypad (DTMF) or voice inputs using speech recognition.</span></span>

<span data-ttu-id="9b0d5-109">云呼叫队列包括当某人拨打您的组织的电话号码时使用的问候语、自动保持通话的功能, 以及搜索下一个可用的呼叫代理以处理呼叫, 而通话的人员在保持状态时收听音乐。</span><span class="sxs-lookup"><span data-stu-id="9b0d5-109">Cloud call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold.</span></span> <span data-ttu-id="9b0d5-110">您可以为您的组织创建单个或多个通话队列。</span><span class="sxs-lookup"><span data-stu-id="9b0d5-110">You can create single or multiple call queues for your organization.</span></span>

## <a name="handling-an-auto-attendant-or-call-queue-call"></a><span data-ttu-id="9b0d5-111">处理自动助理或呼叫队列呼叫</span><span class="sxs-lookup"><span data-stu-id="9b0d5-111">Handling an auto attendant or call queue call</span></span>

<span data-ttu-id="9b0d5-112">用户在应答呼叫之前, 将能够在自动助理或呼叫队列中区分来电。</span><span class="sxs-lookup"><span data-stu-id="9b0d5-112">Users will be able to differentiate incoming calls from an auto attendant or call queue before they answer the call.</span></span> <span data-ttu-id="9b0d5-113">除了呼叫者的姓名和/或号码, 每个调用都将包含有关呼叫者试图访问的人员的信息, 从而为用户提供了更好的解决呼叫者的上下文。</span><span class="sxs-lookup"><span data-stu-id="9b0d5-113">Along with the name and/or number of the caller, each call will include information about who the caller was trying to reach, giving users a better context for addressing the caller.</span></span>

<span data-ttu-id="9b0d5-114">下图显示了来自自动助理或呼叫队列的传入呼叫如何显示给用户。</span><span class="sxs-lookup"><span data-stu-id="9b0d5-114">The following illustration shows how an incoming call from an auto attendant or call queue will appear to a user.</span></span>

![传入呼叫通知](media/answer-auto-attendant-and-call-queue-calls-image1.png)

<span data-ttu-id="9b0d5-116">自动应答自动助理或呼叫队列呼叫后, 用户可以像处理任何其他呼叫 & # x2014 一样处理呼叫。他们可以在其他用户中添加或加入会议, 或者将呼叫转接到另一方。</span><span class="sxs-lookup"><span data-stu-id="9b0d5-116">Once an auto attendant or call queue call is answered, the user can process the call like any other call &#x2014; they can add or conference in another user or transfer the call to another party.</span></span> <span data-ttu-id="9b0d5-117">此外, 将根据用户的配置转发自动助理呼叫。</span><span class="sxs-lookup"><span data-stu-id="9b0d5-117">Also, auto attendant calls will be forwarded based on the user’s configuration.</span></span>

> [!NOTE] 
> <span data-ttu-id="9b0d5-118">呼叫队列呼叫不会根据用户的配置转发。</span><span class="sxs-lookup"><span data-stu-id="9b0d5-118">Call queue calls are not forwarded based on the user’s configuration.</span></span> <span data-ttu-id="9b0d5-119">这是为了确保呼叫者保留在队列中, 直到工程师可以接听呼叫且呼叫者不会被意外转发。</span><span class="sxs-lookup"><span data-stu-id="9b0d5-119">This is to ensure callers remain in the queue until an agent can answer the call and the caller isn’t forwarded unexpectedly.</span></span>

## <a name="supported-clients"></a><span data-ttu-id="9b0d5-120">支持的客户端</span><span class="sxs-lookup"><span data-stu-id="9b0d5-120">Supported clients</span></span>

<span data-ttu-id="9b0d5-121">自动助理和呼叫队列呼叫支持在以下客户端中可用:</span><span class="sxs-lookup"><span data-stu-id="9b0d5-121">Support for auto attendant and call queue calls is available in the following clients:</span></span>

-   <span data-ttu-id="9b0d5-122">Microsoft Teams Windows 客户端 （32 和 64 位版本）</span><span class="sxs-lookup"><span data-stu-id="9b0d5-122">Microsoft Teams Windows client (32 and 64-bit versions)</span></span>
-   <span data-ttu-id="9b0d5-123">Microsoft Teams Mac 客户端</span><span class="sxs-lookup"><span data-stu-id="9b0d5-123">Microsoft Teams Mac client</span></span>
-   <span data-ttu-id="9b0d5-124">Microsoft Teams iPhone 应用</span><span class="sxs-lookup"><span data-stu-id="9b0d5-124">Microsoft Teams iPhone app</span></span>
-   <span data-ttu-id="9b0d5-125">Microsoft Teams Android 应用</span><span class="sxs-lookup"><span data-stu-id="9b0d5-125">Microsoft Teams Android app</span></span>

## <a name="configure-auto-attendant-and-call-queue-support-for-microsoft-teams"></a><span data-ttu-id="9b0d5-126">为 Microsoft 团队配置自动助理和呼叫队列支持</span><span class="sxs-lookup"><span data-stu-id="9b0d5-126">Configure auto attendant and call queue support for Microsoft Teams</span></span>

<span data-ttu-id="9b0d5-127">若要在 Microsoft 团队中接收自动助理和呼叫队列呼叫, 需要配置你的互操作性策略和升级策略。</span><span class="sxs-lookup"><span data-stu-id="9b0d5-127">To receive auto attendant and call queue calls on Microsoft Teams, you need to configure your interoperability policy and upgrade policy.</span></span> <span data-ttu-id="9b0d5-128">请查看[与 Skype For business 一起使用团队的组织的迁移和互操作性](migration-interop-guidance-for-teams-with-skype.md)。</span><span class="sxs-lookup"><span data-stu-id="9b0d5-128">Please review [Migration and interoperability for organizations using Teams together with Skype for Business](migration-interop-guidance-for-teams-with-skype.md).</span></span> <span data-ttu-id="9b0d5-129">如果您没有配置自动助理和/或呼叫队列, 请参阅[设置云自动助理](create-a-phone-system-auto-attendant.md)和[创建云呼叫队列](create-a-phone-system-call-queue.md)。</span><span class="sxs-lookup"><span data-stu-id="9b0d5-129">If you do not have auto attendant and/or call queue configured and would like to do so, see [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md) and [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="9b0d5-130">相关主题</span><span class="sxs-lookup"><span data-stu-id="9b0d5-130">Related topics</span></span>

-   [<span data-ttu-id="9b0d5-131">什么是 Office 365 中的电话系统</span><span class="sxs-lookup"><span data-stu-id="9b0d5-131">What is Phone System in Office 365</span></span>](what-is-phone-system-in-office-365.md)
-   [<span data-ttu-id="9b0d5-132">创建云呼叫队列</span><span class="sxs-lookup"><span data-stu-id="9b0d5-132">Create a Cloud call queue</span></span>](create-a-phone-system-call-queue.md)
-   [<span data-ttu-id="9b0d5-133">什么是云自动助理？</span><span class="sxs-lookup"><span data-stu-id="9b0d5-133">What are Cloud auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)
-   [<span data-ttu-id="9b0d5-134">设置云自动助理</span><span class="sxs-lookup"><span data-stu-id="9b0d5-134">Set up a Cloud auto attendant</span></span>](create-a-phone-system-auto-attendant.md)

