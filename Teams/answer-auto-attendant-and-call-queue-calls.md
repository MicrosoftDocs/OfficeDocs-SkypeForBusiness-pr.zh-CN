---
title: 应答自动助理并直接从团队呼叫队列呼叫
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/20/2018
ms.topic: article
ms.service: msteams
description: 介绍电话系统自动助理和呼叫的队列，并说明如何可以应答团队中的这些呼叫。
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c010ae5a812cfd3d49279dd3728e948bdb31ca53
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/07/2019
ms.locfileid: "30465329"
---
<a name="answer-auto-attendant-and-call-queue-calls-directly-from-teams"></a><span data-ttu-id="d5d25-103">应答自动助理并直接从团队呼叫队列呼叫</span><span class="sxs-lookup"><span data-stu-id="d5d25-103">Answer auto attendant and call queue calls directly from Teams</span></span>
===========================================================

<span data-ttu-id="d5d25-104">团队用户可接收并从业务 online Skype 应答呼叫自动助理，并直接从其团队客户端调用队列。</span><span class="sxs-lookup"><span data-stu-id="d5d25-104">Teams users can receive and answer calls from Skype for Business Online auto attendant and call queues directly from their Teams client.</span></span> <span data-ttu-id="d5d25-105">团队用户自动助理功能现已可用，并调用队列功能处于预览。</span><span class="sxs-lookup"><span data-stu-id="d5d25-105">For Teams users, the auto attendant feature is now generally available, and the call queue capability is in preview.</span></span> 

## <a name="what-are-auto-attendants-and-call-queues"></a><span data-ttu-id="d5d25-106">什么是自动助理，并调用队列？</span><span class="sxs-lookup"><span data-stu-id="d5d25-106">What are auto attendants and call queues?</span></span>

<span data-ttu-id="d5d25-107">电话系统自动助理提供了一系列语音提示或组织到呼叫时，呼叫者听到而不是人工接线员音频文件。</span><span class="sxs-lookup"><span data-stu-id="d5d25-107">Phone System auto attendants provide a series of voice prompts or an audio file that callers hear instead of a human operator when they call in to an organization.</span></span> <span data-ttu-id="d5d25-108">自动助理使呼叫者能够移动浏览菜单系统，进行呼叫，或者使用电话键盘 (DTMF) 或采用语音识别功能的语音输入找到用户。</span><span class="sxs-lookup"><span data-stu-id="d5d25-108">An auto attendant lets callers move through the menu system, place calls, or locate users by using a phone keypad (DTMF) or voice inputs using speech recognition.</span></span>

<span data-ttu-id="d5d25-109">队列包括问候语有人呼叫您的组织、 能够自动将呼叫置于保持状态，和搜索处理该呼叫的人员时的下一个可用呼叫代理的功能电话号码时所使用的电话系统呼叫者保留音乐侦听呼叫。</span><span class="sxs-lookup"><span data-stu-id="d5d25-109">Phone System call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold.</span></span> <span data-ttu-id="d5d25-110">您可以为组织创建单个或多个呼叫的队列。</span><span class="sxs-lookup"><span data-stu-id="d5d25-110">You can create single or multiple call queues for your organization.</span></span>

## <a name="handling-an-auto-attendant-or-call-queue-call"></a><span data-ttu-id="d5d25-111">处理的自动助理或呼叫队列呼叫</span><span class="sxs-lookup"><span data-stu-id="d5d25-111">Handling an auto attendant or call queue call</span></span>

<span data-ttu-id="d5d25-112">用户将能够它们应答呼叫之前区分传入呼叫自动助理或呼叫的队列。</span><span class="sxs-lookup"><span data-stu-id="d5d25-112">Users will be able to differentiate incoming calls from an auto attendant or call queue before they answer the call.</span></span> <span data-ttu-id="d5d25-113">名称和/或将呼叫者数量，以及每个呼叫将包含有关谁将呼叫者尝试通，为用户提供了更好的上下文，解决呼叫者的信息。</span><span class="sxs-lookup"><span data-stu-id="d5d25-113">Along with the name and/or number of the caller, each call will include information about who the caller was trying to reach, giving users a better context for addressing the caller.</span></span>

<span data-ttu-id="d5d25-114">下图显示来自自动助理或呼叫队列的传入呼叫到用户的显示方式。</span><span class="sxs-lookup"><span data-stu-id="d5d25-114">The following illustration shows how an incoming call from an auto attendant or call queue will appear to a user.</span></span>

![传入呼叫通知](media/answer-auto-attendant-and-call-queue-calls-image1.png)

<span data-ttu-id="d5d25-116">一旦应答自动助理或呼叫队列呼叫时，用户可以处理与任何其他呼叫 & #x 2014; 一样调用他们可以添加或另一个用户或转接到另一方呼叫中的会议。</span><span class="sxs-lookup"><span data-stu-id="d5d25-116">Once an auto attendant or call queue call is answered, the user can process the call like any other call &#x2014; they can add or conference in another user or transfer the call to another party.</span></span> <span data-ttu-id="d5d25-117">此外，自动助理将呼叫转接基于用户的配置。</span><span class="sxs-lookup"><span data-stu-id="d5d25-117">Also, auto attendant calls will be forwarded based on the user’s configuration.</span></span>

> [!NOTE] 
> <span data-ttu-id="d5d25-118">调用基于用户的配置不转接呼叫的队列。</span><span class="sxs-lookup"><span data-stu-id="d5d25-118">Call queue calls are not forwarded based on the user’s configuration.</span></span> <span data-ttu-id="d5d25-119">这是为了确保代理可以应答呼叫之前，呼叫者保持队列中没有意外转接呼叫者。</span><span class="sxs-lookup"><span data-stu-id="d5d25-119">This is to ensure callers remain in the queue until an agent can answer the call and the caller isn’t forwarded unexpectedly.</span></span>

## <a name="supported-clients"></a><span data-ttu-id="d5d25-120">支持的客户端</span><span class="sxs-lookup"><span data-stu-id="d5d25-120">Supported clients</span></span>

<span data-ttu-id="d5d25-121">对于自动助理和呼叫队列呼叫支持以下客户端有：</span><span class="sxs-lookup"><span data-stu-id="d5d25-121">Support for auto attendant and call queue calls is available in the following clients:</span></span>

-   <span data-ttu-id="d5d25-122">Microsoft Teams Windows 客户端 （32 和 64 位版本）</span><span class="sxs-lookup"><span data-stu-id="d5d25-122">Microsoft Teams Windows client (32 and 64-bit versions)</span></span>
-   <span data-ttu-id="d5d25-123">Microsoft Teams Mac 客户端</span><span class="sxs-lookup"><span data-stu-id="d5d25-123">Microsoft Teams Mac client</span></span>
-   <span data-ttu-id="d5d25-124">Microsoft Teams iPhone 应用</span><span class="sxs-lookup"><span data-stu-id="d5d25-124">Microsoft Teams iPhone app</span></span>
-   <span data-ttu-id="d5d25-125">Microsoft Teams Android 应用</span><span class="sxs-lookup"><span data-stu-id="d5d25-125">Microsoft Teams Android app</span></span>

## <a name="configure-auto-attendant-and-call-queue-support-for-microsoft-teams"></a><span data-ttu-id="d5d25-126">配置支持的 Microsoft 团队的自动助理和呼叫队列</span><span class="sxs-lookup"><span data-stu-id="d5d25-126">Configure auto attendant and call queue support for Microsoft Teams</span></span>

<span data-ttu-id="d5d25-127">若要接收自动助理和上的 Microsoft 团队呼叫队列呼叫，您需要配置您的互操作性策略和升级策略。</span><span class="sxs-lookup"><span data-stu-id="d5d25-127">To receive auto attendant and call queue calls on Microsoft Teams, you need to configure your interoperability policy and upgrade policy.</span></span> <span data-ttu-id="d5d25-128">请查看[迁移和组织使用团队一起 for Business 的 Skype 的互操作性](migration-interop-guidance-for-teams-with-skype.md)。</span><span class="sxs-lookup"><span data-stu-id="d5d25-128">Please review [Migration and interoperability for organizations using Teams together with Skype for Business](migration-interop-guidance-for-teams-with-skype.md).</span></span> <span data-ttu-id="d5d25-129">如果您没有自动助理和/或呼叫队列配置，并且想要这样做，请参阅[设置电话系统自动助理](https://docs.microsoft.com/skypeforbusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant)和[创建电话系统呼叫队列](https://docs.microsoft.com/skypeforbusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)。</span><span class="sxs-lookup"><span data-stu-id="d5d25-129">If you do not have auto attendant and/or call queue configured and would like to do so, see [Set up a Phone System auto attendant](https://docs.microsoft.com/skypeforbusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant) and [Create a Phone System call queue](https://docs.microsoft.com/skypeforbusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue).</span></span>

## <a name="related-topics"></a><span data-ttu-id="d5d25-130">相关主题</span><span class="sxs-lookup"><span data-stu-id="d5d25-130">Related topics</span></span>

-   [<span data-ttu-id="d5d25-131">什么是 Office 365 中的电话系统</span><span class="sxs-lookup"><span data-stu-id="d5d25-131">What is Phone System in Office 365</span></span>](what-is-phone-system-in-office-365.md)
-   [<span data-ttu-id="d5d25-132">创建电话系统呼叫队列</span><span class="sxs-lookup"><span data-stu-id="d5d25-132">Create a Phone System call queue</span></span>](https://docs.microsoft.com/skypeforbusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)
-   [<span data-ttu-id="d5d25-133">什么是电话系统自动助理？</span><span class="sxs-lookup"><span data-stu-id="d5d25-133">What are Phone System auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)
-   [<span data-ttu-id="d5d25-134">设置电话系统自动助理</span><span class="sxs-lookup"><span data-stu-id="d5d25-134">Set up a Phone System auto attendant</span></span>](https://docs.microsoft.com/skypeforbusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant)

