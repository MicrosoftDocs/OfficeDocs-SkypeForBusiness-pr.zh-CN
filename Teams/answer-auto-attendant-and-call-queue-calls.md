---
title: 应答自动助理和呼叫队列呼叫
ms.reviewer: colongma
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.date: 09/20/2018
ms.topic: conceptual
ms.service: msteams
description: 介绍云自动助理和呼叫队列，并说明如何在 Teams。
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
ms.openlocfilehash: 3e1656af8ee457cb4c112d229c2dee03d2590ece
ms.sourcegitcommit: 36bc47b2b9ee0e738fa814c31accacfe816da4a3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/09/2021
ms.locfileid: "52856371"
---
# <a name="answer-auto-attendant-and-call-queue-calls-directly-from-teams"></a><span data-ttu-id="d10d5-103">直接从 Teams 回答自动助理和呼叫队列</span><span class="sxs-lookup"><span data-stu-id="d10d5-103">Answer auto attendant and call queue calls directly from Teams</span></span>

<span data-ttu-id="d10d5-104">Teams用户可以直接从云自动助理接收和接听来自云自动助理的呼叫，并直接从其Teams呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="d10d5-104">Teams users can receive and answer calls from Cloud auto attendants and call queues directly from their Teams client.</span></span>

## <a name="what-are-auto-attendants-and-call-queues"></a><span data-ttu-id="d10d5-105">什么是自动助理和呼叫队列？</span><span class="sxs-lookup"><span data-stu-id="d10d5-105">What are auto attendants and call queues?</span></span>

<span data-ttu-id="d10d5-106">云自动助理提供一系列语音提示或音频文件，呼叫者在呼叫组织时可以听到这些提示或音频文件，而不是人工接线员。</span><span class="sxs-lookup"><span data-stu-id="d10d5-106">Cloud auto attendants provide a series of voice prompts or an audio file that callers hear instead of a human operator when they call in to an organization.</span></span> <span data-ttu-id="d10d5-107">自动助理使呼叫者能够移动浏览菜单系统，进行呼叫，或者使用电话键盘 (DTMF) 或采用语音识别功能的语音输入找到用户。</span><span class="sxs-lookup"><span data-stu-id="d10d5-107">An auto attendant lets callers move through the menu system, place calls, or locate users by using a phone keypad (DTMF) or voice inputs using speech recognition.</span></span>

<span data-ttu-id="d10d5-108">云呼叫队列包括当某人呼叫组织的电话号码时使用的问候语、自动将呼叫置于保持状态的能力，以及搜索下一个可用的呼叫代理以在呼叫者收听保持音乐时处理呼叫的能力。</span><span class="sxs-lookup"><span data-stu-id="d10d5-108">Cloud call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold.</span></span> <span data-ttu-id="d10d5-109">你可以为组织创建单个或多个呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="d10d5-109">You can create single or multiple call queues for your organization.</span></span>

## <a name="handling-an-auto-attendant-or-call-queue-call"></a><span data-ttu-id="d10d5-110">处理自动助理或呼叫队列呼叫</span><span class="sxs-lookup"><span data-stu-id="d10d5-110">Handling an auto attendant or call queue call</span></span>

<span data-ttu-id="d10d5-111">用户在接听呼叫之前，能够区分来自自动助理或呼叫队列的传入呼叫。</span><span class="sxs-lookup"><span data-stu-id="d10d5-111">Users will be able to differentiate incoming calls from an auto attendant or call queue before they answer the call.</span></span> <span data-ttu-id="d10d5-112">除了呼叫者的姓名和/或号码外，每个呼叫都将包含有关呼叫者尝试联系的用户的信息，为用户提供了一个更好的上下文来向呼叫者进行寻址。</span><span class="sxs-lookup"><span data-stu-id="d10d5-112">Along with the name and/or number of the caller, each call will include information about who the caller was trying to reach, giving users a better context for addressing the caller.</span></span>

<span data-ttu-id="d10d5-113">下图显示了来自自动助理或呼叫队列的传入呼叫如何向用户显示。</span><span class="sxs-lookup"><span data-stu-id="d10d5-113">The following illustration shows how an incoming call from an auto attendant or call queue will appear to a user.</span></span>

![传入呼叫通知的屏幕截图](media/answer-auto-attendant-and-call-queue-calls-image1.png)

<span data-ttu-id="d10d5-115">应答自动助理或呼叫队列呼叫后，用户可以像处理任何其他呼叫一样处理呼叫&#x2014;他们可在其他用户中添加或会议，或者将呼叫转接到另一方。</span><span class="sxs-lookup"><span data-stu-id="d10d5-115">Once an auto attendant or call queue call is answered, the user can process the call like any other call &#x2014; they can add or conference in another user or transfer the call to another party.</span></span> <span data-ttu-id="d10d5-116">此外，自动助理呼叫将基于用户的配置进行转发。</span><span class="sxs-lookup"><span data-stu-id="d10d5-116">Also, auto attendant calls will be forwarded based on the user's configuration.</span></span>

> [!NOTE] 
> <span data-ttu-id="d10d5-117">不会根据用户的配置转发呼叫队列调用。</span><span class="sxs-lookup"><span data-stu-id="d10d5-117">Call queue calls are not forwarded based on the user's configuration.</span></span> <span data-ttu-id="d10d5-118">这是为了确保调用方保留在队列中，直到代理可以应答呼叫并且调用方不会意外转发。</span><span class="sxs-lookup"><span data-stu-id="d10d5-118">This is to ensure callers remain in the queue until an agent can answer the call and the caller isn't forwarded unexpectedly.</span></span>

> <span data-ttu-id="d10d5-119">对于呼叫队列呼叫，代理不会收到任何错过的呼叫或语音邮件的通知。</span><span class="sxs-lookup"><span data-stu-id="d10d5-119">Agents are not notified of any missed calls or voicemails for call queue calls.</span></span>

## <a name="supported-clients"></a><span data-ttu-id="d10d5-120">支持的客户端</span><span class="sxs-lookup"><span data-stu-id="d10d5-120">Supported clients</span></span>

<span data-ttu-id="d10d5-121">以下客户端支持自动助理和呼叫队列呼叫：</span><span class="sxs-lookup"><span data-stu-id="d10d5-121">Support for auto attendant and call queue calls is available in the following clients:</span></span>

-    <span data-ttu-id="d10d5-122">Microsoft Teams Windows 客户端 （32 和 64 位版本）</span><span class="sxs-lookup"><span data-stu-id="d10d5-122">Microsoft Teams Windows client (32 and 64-bit versions)</span></span>
-    <span data-ttu-id="d10d5-123">Microsoft Teams Mac 客户端</span><span class="sxs-lookup"><span data-stu-id="d10d5-123">Microsoft Teams Mac client</span></span>
-    <span data-ttu-id="d10d5-124">Microsoft Teams iPhone 应用</span><span class="sxs-lookup"><span data-stu-id="d10d5-124">Microsoft Teams iPhone app</span></span>
-    <span data-ttu-id="d10d5-125">Microsoft Teams Android 应用</span><span class="sxs-lookup"><span data-stu-id="d10d5-125">Microsoft Teams Android app</span></span>

## <a name="configure-auto-attendant-and-call-queue-support-for-microsoft-teams"></a><span data-ttu-id="d10d5-126">为呼叫配置自动助理和呼叫队列Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d10d5-126">Configure auto attendant and call queue support for Microsoft Teams</span></span>

<span data-ttu-id="d10d5-127">若要在客户端上接收自动助理Microsoft Teams呼叫队列呼叫，需要配置互操作性策略和升级策略。</span><span class="sxs-lookup"><span data-stu-id="d10d5-127">To receive auto attendant and call queue calls on Microsoft Teams, you need to configure your interoperability policy and upgrade policy.</span></span> <span data-ttu-id="d10d5-128">请查看将 Teams 与 Skype for Business[一起用于组织的迁移和Skype for Business。](migration-interop-guidance-for-teams-with-skype.md)</span><span class="sxs-lookup"><span data-stu-id="d10d5-128">Please review [Migration and interoperability for organizations using Teams together with Skype for Business](migration-interop-guidance-for-teams-with-skype.md).</span></span> <span data-ttu-id="d10d5-129">如果没有配置自动助理和/或呼叫队列，并且希望这样做，请参阅设置云自动[助理和](create-a-phone-system-auto-attendant.md)[创建云呼叫队列](create-a-phone-system-call-queue.md)。</span><span class="sxs-lookup"><span data-stu-id="d10d5-129">If you do not have auto attendant and/or call queue configured and would like to do so, see [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md) and [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>

## <a name="known-issues"></a><span data-ttu-id="d10d5-130">已知问题</span><span class="sxs-lookup"><span data-stu-id="d10d5-130">Known Issues</span></span>

<span data-ttu-id="d10d5-131">当呼叫队列代理在移动设备上收到呼叫时，如果设备已锁定，呼叫可能会保持。</span><span class="sxs-lookup"><span data-stu-id="d10d5-131">When a call queue agents receives a call on their mobile device, calls may go on hold if the device is locked.</span></span> <span data-ttu-id="d10d5-132">用户必须先解锁设备，然后接听呼叫。</span><span class="sxs-lookup"><span data-stu-id="d10d5-132">User must unlock device first and then answer the call.</span></span>


## <a name="related-topics"></a><span data-ttu-id="d10d5-133">相关主题</span><span class="sxs-lookup"><span data-stu-id="d10d5-133">Related topics</span></span>

-    [<span data-ttu-id="d10d5-134">电话系统或Microsoft 365中Office 365</span><span class="sxs-lookup"><span data-stu-id="d10d5-134">What is Phone System in Microsoft 365 or Office 365</span></span>](what-is-phone-system-in-office-365.md)
-    [<span data-ttu-id="d10d5-135">创建云呼叫队列</span><span class="sxs-lookup"><span data-stu-id="d10d5-135">Create a Cloud call queue</span></span>](create-a-phone-system-call-queue.md)
-    [<span data-ttu-id="d10d5-136">什么是云自动助理？</span><span class="sxs-lookup"><span data-stu-id="d10d5-136">What are Cloud auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)
-    [<span data-ttu-id="d10d5-137">设置云自动助理</span><span class="sxs-lookup"><span data-stu-id="d10d5-137">Set up a Cloud auto attendant</span></span>](create-a-phone-system-auto-attendant.md)

