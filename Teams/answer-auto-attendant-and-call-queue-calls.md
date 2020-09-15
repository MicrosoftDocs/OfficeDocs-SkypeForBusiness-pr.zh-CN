---
title: 应答自动助理和呼叫队列呼叫
ms.reviewer: waseemh
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.date: 09/20/2018
ms.topic: conceptual
ms.service: msteams
description: 介绍云自动助理和通话队列，并介绍如何在团队中回答这些呼叫。
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 95719bc95cc752888964a5f404e6f8050ebf3fa4
ms.sourcegitcommit: 67c686810d37bffda72a6e92155d9c8ec86bfae6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/15/2020
ms.locfileid: "47766856"
---
<a name="answer-auto-attendant-and-call-queue-calls-directly-from-teams"></a><span data-ttu-id="a50e1-103">直接从 Teams 回答自动助理和呼叫队列</span><span class="sxs-lookup"><span data-stu-id="a50e1-103">Answer auto attendant and call queue calls directly from Teams</span></span>
===========================================================

<span data-ttu-id="a50e1-104">团队用户可以直接从其团队客户端接收和应答来自云自动助理的调用和调用队列。</span><span class="sxs-lookup"><span data-stu-id="a50e1-104">Teams users can receive and answer calls from Cloud auto attendants and call queues directly from their Teams client.</span></span>

## <a name="what-are-auto-attendants-and-call-queues"></a><span data-ttu-id="a50e1-105">什么是自动助理和呼叫队列？</span><span class="sxs-lookup"><span data-stu-id="a50e1-105">What are auto attendants and call queues?</span></span>

<span data-ttu-id="a50e1-106">云自动助理提供一系列语音提示或音频文件，当呼叫者呼叫组织时，呼叫者将听到该提示，而不是人工操作员。</span><span class="sxs-lookup"><span data-stu-id="a50e1-106">Cloud auto attendants provide a series of voice prompts or an audio file that callers hear instead of a human operator when they call in to an organization.</span></span> <span data-ttu-id="a50e1-107">自动助理使呼叫者能够移动浏览菜单系统，进行呼叫，或者使用电话键盘 (DTMF) 或采用语音识别功能的语音输入找到用户。</span><span class="sxs-lookup"><span data-stu-id="a50e1-107">An auto attendant lets callers move through the menu system, place calls, or locate users by using a phone keypad (DTMF) or voice inputs using speech recognition.</span></span>

<span data-ttu-id="a50e1-108">云呼叫队列包括当某人拨入到您的组织的电话号码时使用的问候语、自动将呼叫置于保持状态的功能，以及搜索下一个可用的呼叫代理以处理呼叫的功能，同时呼叫正在收听音乐的用户。</span><span class="sxs-lookup"><span data-stu-id="a50e1-108">Cloud call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold.</span></span> <span data-ttu-id="a50e1-109">您可以为您的组织创建单个或多个通话队列。</span><span class="sxs-lookup"><span data-stu-id="a50e1-109">You can create single or multiple call queues for your organization.</span></span>

## <a name="handling-an-auto-attendant-or-call-queue-call"></a><span data-ttu-id="a50e1-110">处理自动助理或呼叫队列呼叫</span><span class="sxs-lookup"><span data-stu-id="a50e1-110">Handling an auto attendant or call queue call</span></span>

<span data-ttu-id="a50e1-111">用户在应答呼叫之前，将能够在自动助理或呼叫队列中区分来电。</span><span class="sxs-lookup"><span data-stu-id="a50e1-111">Users will be able to differentiate incoming calls from an auto attendant or call queue before they answer the call.</span></span> <span data-ttu-id="a50e1-112">除了呼叫者的姓名和/或号码，每个调用都将包含有关呼叫者试图访问的人员的信息，从而为用户提供了更好的解决呼叫者的上下文。</span><span class="sxs-lookup"><span data-stu-id="a50e1-112">Along with the name and/or number of the caller, each call will include information about who the caller was trying to reach, giving users a better context for addressing the caller.</span></span>

<span data-ttu-id="a50e1-113">下图显示了来自自动助理或呼叫队列的传入呼叫如何显示给用户。</span><span class="sxs-lookup"><span data-stu-id="a50e1-113">The following illustration shows how an incoming call from an auto attendant or call queue will appear to a user.</span></span>

![传入呼叫通知的屏幕截图](media/answer-auto-attendant-and-call-queue-calls-image1.png)

<span data-ttu-id="a50e1-115">应答自动助理或呼叫队列呼叫后，用户可以像处理任何其他呼叫一样处理呼叫，&#x2014; 他们可以在其他用户中添加或加入会议，或者将呼叫转接到另一方。</span><span class="sxs-lookup"><span data-stu-id="a50e1-115">Once an auto attendant or call queue call is answered, the user can process the call like any other call &#x2014; they can add or conference in another user or transfer the call to another party.</span></span> <span data-ttu-id="a50e1-116">此外，将根据用户的配置转发自动助理呼叫。</span><span class="sxs-lookup"><span data-stu-id="a50e1-116">Also, auto attendant calls will be forwarded based on the user's configuration.</span></span>

> [!NOTE] 
> <span data-ttu-id="a50e1-117">呼叫队列呼叫不会根据用户的配置转发。</span><span class="sxs-lookup"><span data-stu-id="a50e1-117">Call queue calls are not forwarded based on the user's configuration.</span></span> <span data-ttu-id="a50e1-118">这是为了确保呼叫者保留在队列中，直到工程师可以接听呼叫且呼叫者不会被意外转发。</span><span class="sxs-lookup"><span data-stu-id="a50e1-118">This is to ensure callers remain in the queue until an agent can answer the call and the caller isn't forwarded unexpectedly.</span></span>

## <a name="supported-clients"></a><span data-ttu-id="a50e1-119">支持的客户端</span><span class="sxs-lookup"><span data-stu-id="a50e1-119">Supported clients</span></span>

<span data-ttu-id="a50e1-120">自动助理和呼叫队列呼叫支持在以下客户端中可用：</span><span class="sxs-lookup"><span data-stu-id="a50e1-120">Support for auto attendant and call queue calls is available in the following clients:</span></span>

-    <span data-ttu-id="a50e1-121">Microsoft Teams Windows 客户端 （32 和 64 位版本）</span><span class="sxs-lookup"><span data-stu-id="a50e1-121">Microsoft Teams Windows client (32 and 64-bit versions)</span></span>
-    <span data-ttu-id="a50e1-122">Microsoft Teams Mac 客户端</span><span class="sxs-lookup"><span data-stu-id="a50e1-122">Microsoft Teams Mac client</span></span>
-    <span data-ttu-id="a50e1-123">Microsoft Teams iPhone 应用</span><span class="sxs-lookup"><span data-stu-id="a50e1-123">Microsoft Teams iPhone app</span></span>
-    <span data-ttu-id="a50e1-124">Microsoft Teams Android 应用</span><span class="sxs-lookup"><span data-stu-id="a50e1-124">Microsoft Teams Android app</span></span>

## <a name="configure-auto-attendant-and-call-queue-support-for-microsoft-teams"></a><span data-ttu-id="a50e1-125">为 Microsoft 团队配置自动助理和呼叫队列支持</span><span class="sxs-lookup"><span data-stu-id="a50e1-125">Configure auto attendant and call queue support for Microsoft Teams</span></span>

<span data-ttu-id="a50e1-126">若要在 Microsoft 团队中接收自动助理和呼叫队列呼叫，需要配置你的互操作性策略和升级策略。</span><span class="sxs-lookup"><span data-stu-id="a50e1-126">To receive auto attendant and call queue calls on Microsoft Teams, you need to configure your interoperability policy and upgrade policy.</span></span> <span data-ttu-id="a50e1-127">请查看 [与 Skype For business 一起使用团队的组织的迁移和互操作性](migration-interop-guidance-for-teams-with-skype.md)。</span><span class="sxs-lookup"><span data-stu-id="a50e1-127">Please review [Migration and interoperability for organizations using Teams together with Skype for Business](migration-interop-guidance-for-teams-with-skype.md).</span></span> <span data-ttu-id="a50e1-128">如果您没有配置自动助理和/或呼叫队列，请参阅 [设置云自动助理](create-a-phone-system-auto-attendant.md) 和 [创建云呼叫队列](create-a-phone-system-call-queue.md)。</span><span class="sxs-lookup"><span data-stu-id="a50e1-128">If you do not have auto attendant and/or call queue configured and would like to do so, see [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md) and [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>

## <a name="known-issues"></a><span data-ttu-id="a50e1-129">已知问题</span><span class="sxs-lookup"><span data-stu-id="a50e1-129">Known Issues</span></span>

<span data-ttu-id="a50e1-130">当呼叫队列代理在其移动设备上收到呼叫时，如果设备处于锁定状态，则呼叫可能会继续保持通话。</span><span class="sxs-lookup"><span data-stu-id="a50e1-130">When a call queue agents receives a call on their mobile device, calls may go on hold if the device is locked.</span></span> <span data-ttu-id="a50e1-131">用户必须先解锁设备，然后再接听呼叫。</span><span class="sxs-lookup"><span data-stu-id="a50e1-131">User must unlock device first and then answer the call.</span></span>


## <a name="related-topics"></a><span data-ttu-id="a50e1-132">相关主题</span><span class="sxs-lookup"><span data-stu-id="a50e1-132">Related topics</span></span>

-    [<span data-ttu-id="a50e1-133">什么是 Microsoft 365 或 Office 365 中的电话系统</span><span class="sxs-lookup"><span data-stu-id="a50e1-133">What is Phone System in Microsoft 365 or Office 365</span></span>](what-is-phone-system-in-office-365.md)
-    [<span data-ttu-id="a50e1-134">创建云呼叫队列</span><span class="sxs-lookup"><span data-stu-id="a50e1-134">Create a Cloud call queue</span></span>](create-a-phone-system-call-queue.md)
-    [<span data-ttu-id="a50e1-135">什么是云自动助理？</span><span class="sxs-lookup"><span data-stu-id="a50e1-135">What are Cloud auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)
-    [<span data-ttu-id="a50e1-136">设置云自动助理</span><span class="sxs-lookup"><span data-stu-id="a50e1-136">Set up a Cloud auto attendant</span></span>](create-a-phone-system-auto-attendant.md)

