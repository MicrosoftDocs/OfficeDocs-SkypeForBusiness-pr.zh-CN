---
title: 创建呼叫队列
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: phans, wasseemh
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.callqueues.overview"
ms.custom:
- Phone System
description: 了解如何为 Microsoft 团队设置云呼叫队列的电话系统。
ms.openlocfilehash: f3eb106c0acb9c79d60f45cc11770f26e3e59a1e
ms.sourcegitcommit: 5695ce88d4a6a8fb9594df8dd1c207e45be067be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/15/2019
ms.locfileid: "37516690"
---
# <a name="create-a-cloud-call-queue"></a><span data-ttu-id="c190c-103">创建云呼叫队列</span><span class="sxs-lookup"><span data-stu-id="c190c-103">Create a Cloud call queue</span></span>

<span data-ttu-id="c190c-104">云呼叫队列可以提供：</span><span class="sxs-lookup"><span data-stu-id="c190c-104">Cloud call queues can provide:</span></span>

- <span data-ttu-id="c190c-105">一条问候语。</span><span class="sxs-lookup"><span data-stu-id="c190c-105">A greeting message.</span></span>
- <span data-ttu-id="c190c-106">在呼叫者保持等待时播放的音乐。</span><span class="sxs-lookup"><span data-stu-id="c190c-106">Music while people are waiting on hold.</span></span>
- <span data-ttu-id="c190c-107">使用启用邮件的通讯组列表和安全组将呼叫重定向到呼叫代理。</span><span class="sxs-lookup"><span data-stu-id="c190c-107">Redirecting calls to call agents in mail-enabled distribution lists and security groups.</span></span>
- <span data-ttu-id="c190c-108">设置不同的参数，例如队列最大大小、超时和通话处理选项。</span><span class="sxs-lookup"><span data-stu-id="c190c-108">Setting different parameters such as queue maximum size, timeout, and call handling options.</span></span>

<span data-ttu-id="c190c-109">您可以使用[资源帐户](manage-resource-accounts.md)将电话号码与呼叫队列相关联。</span><span class="sxs-lookup"><span data-stu-id="c190c-109">You would associate a phone number to a call queue using a [resource account](manage-resource-accounts.md).</span></span> <span data-ttu-id="c190c-110">可通过自动助理上的选择直接拨打或访问呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="c190c-110">A call queue can be dialed directly or accessed by a selection on an auto attendant.</span></span>

<span data-ttu-id="c190c-111">呼叫者在处于暂停状态时将听到音乐，并且呼叫将首先连接到呼叫代理，*即先出*（FIFO）订单。</span><span class="sxs-lookup"><span data-stu-id="c190c-111">The caller hears music while they are on hold, and the call connects to the call agents in *First In, First Out* (FIFO) order.</span></span>

<span data-ttu-id="c190c-112">通过以下方法之一将队列中的所有调用发送到代理：</span><span class="sxs-lookup"><span data-stu-id="c190c-112">All calls in the queue are sent to agents by one of the following methods:</span></span>

- <span data-ttu-id="c190c-113">通过助理路由，队列中的第一个通话将同时响铃所有代理。</span><span class="sxs-lookup"><span data-stu-id="c190c-113">With attendant routing, the first call in the queue  rings all agents at the same time.</span></span>
- <span data-ttu-id="c190c-114">通过串行路由，队列中的第一次呼叫将每个呼叫代理逐一响铃一次。</span><span class="sxs-lookup"><span data-stu-id="c190c-114">With serial routing, the first call in the queue rings all call agents one by one.</span></span>
- <span data-ttu-id="c190c-115">通过循环复用，传入呼叫的路由是平衡的，以便每个呼叫代理从队列中获得相同数量的通话。</span><span class="sxs-lookup"><span data-stu-id="c190c-115">With round robin, routing of incoming calls is balanced so that each call agent gets the same number of calls from the queue.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c190c-116">在**脱机**状态下呼叫代理、将其状态设置为 "请勿**打扰"** 或选择退出呼叫队列将不会收到呼叫。</span><span class="sxs-lookup"><span data-stu-id="c190c-116">Call agents who are **Offline**, have set their presence to **Do not Disturb,** or have opted out of the call queue will not recieve calls.</span></span>

- <span data-ttu-id="c190c-117">一次仅有一个传入呼叫通知（在队列的头呼叫）转到呼叫代理。</span><span class="sxs-lookup"><span data-stu-id="c190c-117">Only one incoming call notification (for the call at the head of the queue) at a time goes to the call agents.</span></span>
- <span data-ttu-id="c190c-118">呼叫代理接受呼叫后，队列中的下一个传入呼叫开始拨叫所有代理。</span><span class="sxs-lookup"><span data-stu-id="c190c-118">After a call agent accepts the call, the next incoming call in the queue will start ringing call agents.</span></span>

> [!NOTE]
> <span data-ttu-id="c190c-119">本文适用于 Microsoft 团队和 Skype for business Online。</span><span class="sxs-lookup"><span data-stu-id="c190c-119">This article applies to both Microsoft Teams and Skype for Business Online.</span></span>

## <a name="step-1--get-started"></a><span data-ttu-id="c190c-120">步骤 1-入门</span><span class="sxs-lookup"><span data-stu-id="c190c-120">Step 1 — Get started</span></span>

<span data-ttu-id="c190c-121">要开始使用呼叫队列，记住以下几点至关重要：</span><span class="sxs-lookup"><span data-stu-id="c190c-121">To get started using call queues, it's important to remember a few things:</span></span>

- <span data-ttu-id="c190c-122">通话队列必须具有关联的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="c190c-122">A call queue is required to have an associated resource account.</span></span> <span data-ttu-id="c190c-123">有关资源帐户的详细信息，请参阅[管理团队中的资源帐户](manage-resource-accounts.md)。</span><span class="sxs-lookup"><span data-stu-id="c190c-123">See [Manage resource accounts in Teams](manage-resource-accounts.md) for details on resource accounts.</span></span>
- <span data-ttu-id="c190c-124">将电话号码分配给资源帐户时，您现在可以使用 "免费电话系统[虚拟用户" 许可证](teams-add-on-licensing/virtual-user.md)。</span><span class="sxs-lookup"><span data-stu-id="c190c-124">When you assign a phone number to a resource account, you can now use the cost-free Phone System [Virtual User license](teams-add-on-licensing/virtual-user.md).</span></span> <span data-ttu-id="c190c-125">电话系统允许组织级别的电话号码与低成本的自动助理和呼叫队列服务配合使用。</span><span class="sxs-lookup"><span data-stu-id="c190c-125">Phone System allows phone numbers at the organizational level for use with low-cost auto attendant and call queue services.</span></span>

> [!NOTE]
> <span data-ttu-id="c190c-126">只有 Microsoft 团队用户和代理才支持直接路由呼叫队列服务号码。</span><span class="sxs-lookup"><span data-stu-id="c190c-126">Direct Routing service numbers for call queues are supported for Microsoft Teams users and agents only.</span></span>

> [!NOTE]
> <span data-ttu-id="c190c-127">若要将呼叫重定向到您的组织中联机的人员，他们必须具有**电话系统**许可证并启用企业语音或拥有 Office 365 通话计划。</span><span class="sxs-lookup"><span data-stu-id="c190c-127">To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans.</span></span> <span data-ttu-id="c190c-128">请参阅[分配 Skype For business 许可证](/Skype/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)或[分配 Microsoft 团队许可证](assign-teams-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="c190c-128">See [Assign Skype for Business licenses](/Skype/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) or [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="c190c-129">To enable them for Enterprise Voice, you can use Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c190c-129">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="c190c-130">例如，运行：`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="c190c-130">For example run: `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

- <span data-ttu-id="c190c-131">若要了解有关 Office 365 呼叫计划的详细信息，请参阅[手机系统和通话计划](calling-plan-landing-page.md)和[Office 365 的呼叫计划](calling-plans-for-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="c190c-131">To learn more about Office 365 Calling Plans, see [Phone System and Calling Plans](calling-plan-landing-page.md) and [Calling Plans for Office 365](calling-plans-for-office-365.md).</span></span>

- <span data-ttu-id="c190c-132">您只能将云呼叫队列分配给您在**Microsoft 团队管理中心**或从另一个服务提供商转移的收费电话号码和免费服务电话号码。</span><span class="sxs-lookup"><span data-stu-id="c190c-132">You can only assign Cloud call queues toll and toll-free service phone numbers that you got in the **Microsoft Teams admin center** or transferred from another service provider.</span></span> <span data-ttu-id="c190c-133">免费服务号码需要通讯信用点数。</span><span class="sxs-lookup"><span data-stu-id="c190c-133">Communications Credits are required for toll-free service numbers.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c190c-134">[!注释] 不能将用户（订阅者）的电话号码分配给呼叫队列 - 只能使用收费或免费服务电话号码。</span><span class="sxs-lookup"><span data-stu-id="c190c-134">User (subscriber) phone numbers can't be assigned to call queues - only service toll or toll-free phone numbers can be used.</span></span>

- <span data-ttu-id="c190c-135">以下客户端支持与云呼叫队列关联的呼叫代理：</span><span class="sxs-lookup"><span data-stu-id="c190c-135">The following clients are supported for call agents associated to a Cloud call queue:</span></span>

  - <span data-ttu-id="c190c-136">Skype for Business 桌面客户端2016（32位和64位版本）</span><span class="sxs-lookup"><span data-stu-id="c190c-136">Skype for Business desktop client 2016 (32-bit and 64-bit versions)</span></span>

  - <span data-ttu-id="c190c-137">Lync 桌面客户端2013（32位和64位版本）</span><span class="sxs-lookup"><span data-stu-id="c190c-137">Lync desktop client 2013 (32-bit and 64-bit versions)</span></span>

  - <span data-ttu-id="c190c-138">Microsoft 团队支持的所有 IP 电话模式。</span><span class="sxs-lookup"><span data-stu-id="c190c-138">All IP phone models supported for Microsoft Teams.</span></span> <span data-ttu-id="c190c-139">请参阅[获取适用于 Skype for Business Online 的电话](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online)。</span><span class="sxs-lookup"><span data-stu-id="c190c-139">See [Getting phones for Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span></span>

  - <span data-ttu-id="c190c-140">Mac Skype for Business 客户端（版本 16.8.196 及更高版本）</span><span class="sxs-lookup"><span data-stu-id="c190c-140">Mac Skype for Business Client (version 16.8.196 and later)</span></span>

  - <span data-ttu-id="c190c-141">Android Skype for Business 客户端（版本 6.16.0.9 及更高版本）</span><span class="sxs-lookup"><span data-stu-id="c190c-141">Android Skype for Business Client (version 6.16.0.9 and later)</span></span>

  - <span data-ttu-id="c190c-142">iPhone Skype for Business 客户端（版本 6.16.0 及更高版本）</span><span class="sxs-lookup"><span data-stu-id="c190c-142">iPhone Skype for Business Client (version 6.16.0 and later)</span></span>

  - <span data-ttu-id="c190c-143">iPad Skype for Business 客户端（版本 6.16.0 及更高版本）</span><span class="sxs-lookup"><span data-stu-id="c190c-143">iPad Skype for Business Client (version 6.16.0 and later)</span></span>

  - <span data-ttu-id="c190c-144">Microsoft 团队 Windows 客户端（32位和64位版本）</span><span class="sxs-lookup"><span data-stu-id="c190c-144">Microsoft Teams Windows client (32-bit and 64-bit versions)</span></span>

  - <span data-ttu-id="c190c-145">Microsoft Teams Mac 客户端</span><span class="sxs-lookup"><span data-stu-id="c190c-145">Microsoft Teams Mac client</span></span>

  - <span data-ttu-id="c190c-146">Microsoft Teams iPhone 应用</span><span class="sxs-lookup"><span data-stu-id="c190c-146">Microsoft Teams iPhone app</span></span>

  - <span data-ttu-id="c190c-147">Microsoft Teams Android 应用</span><span class="sxs-lookup"><span data-stu-id="c190c-147">Microsoft Teams Android app</span></span>

    > [!NOTE]
    > <span data-ttu-id="c190c-148">分配了直接路由号码的呼叫队列将不支持 Skype for business 客户端、Lync 客户端或 Skype for business IP 手机用作代理。</span><span class="sxs-lookup"><span data-stu-id="c190c-148">Call queues that are assigned a direct routing number will not support Skype for Business clients, Lync clients, or Skype for Business IP Phones as agents.</span></span> 

## <a name="step-2--getting-or-transferring-toll-or-toll-free-service-phone-numbers"></a><span data-ttu-id="c190c-149">步骤 2-获取或转移收费或免费服务电话号码</span><span class="sxs-lookup"><span data-stu-id="c190c-149">Step 2 — Getting or transferring toll or toll-free service phone numbers</span></span>

<span data-ttu-id="c190c-150">在创建和设置呼叫队列之前，您需要获取或转移现有收费或免费服务号码。</span><span class="sxs-lookup"><span data-stu-id="c190c-150">Before you can create and set up your call queues, you need to get or transfer your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="c190c-151">获取收费或免费服务电话号码后，它们将显示在**Microsoft 团队管理中心** > **旧版门户** > **Voice** > **电话号码**中，并且**数字类型**将列为**服务-** 免费。</span><span class="sxs-lookup"><span data-stu-id="c190c-151">After you get the toll or toll-free service phone numbers, they will show up in **Microsoft Teams admin center** > **Legacy Portal** > **Voice** > **Phone numbers**, and the **Number type** will be listed as **Service — Toll-Free**.</span></span> <span data-ttu-id="c190c-152">若要获取你的服务号码，请参阅[获取服务电话号码](getting-service-phone-numbers.md)或要转移现有服务号码，请参阅[将电话号码转移到 Office 365](transfer-phone-numbers-to-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="c190c-152">To get your service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md) or if you want to transfer an existing service number, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>

> [!NOTE]
> <span data-ttu-id="c190c-153">如果您在美国以外，则不能使用 Microsoft 团队管理中心获取服务号码。</span><span class="sxs-lookup"><span data-stu-id="c190c-153">If you are outside the United States, you can't use the Microsoft Teams admin center to get service numbers.</span></span> <span data-ttu-id="c190c-154">转到 "[管理你的组织的电话号码](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)" 以了解如何从美国以外的国家进行管理。</span><span class="sxs-lookup"><span data-stu-id="c190c-154">Go to [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) instead to see how to do it from the outside of the United States.</span></span>

<span data-ttu-id="c190c-155">设置多个自动助理时，你只能将电话号码分配给主自动助理的资源帐户，该帐户可以将呼叫者定向到呼叫队列或嵌套的自动助理。</span><span class="sxs-lookup"><span data-stu-id="c190c-155">When setting up multiple auto attendants you may only assign a phone number to the main auto attendant's resource account, which can direct callers to your call queues or nested auto attendants.</span></span> <span data-ttu-id="c190c-156">在这些情况下，在系统中创建所有自动助理并调用队列，而不分配拨号键盘选项，然后稍后编辑设置。</span><span class="sxs-lookup"><span data-stu-id="c190c-156">In those situations, you create all auto attendants and call queues in your system without assigning dialpad options, and then edit the settings later.</span></span> <span data-ttu-id="c190c-157">这是必需的，因为不允许创建指向呼叫队列或不存在的自动助理的选项链接。</span><span class="sxs-lookup"><span data-stu-id="c190c-157">This is necessary because you aren't allowed to create an option linking to a call queue or auto attendant that does not yet exist.</span></span>

## <a name="step-3--create-a-new-call-queue"></a><span data-ttu-id="c190c-158">步骤 3-创建新的呼叫队列</span><span class="sxs-lookup"><span data-stu-id="c190c-158">Step 3 — Create a new call queue</span></span>

[!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

> [!IMPORTANT]
> <span data-ttu-id="c190c-159">每个通话队列都必须具有关联的[资源帐户](manage-resource-accounts.md)。</span><span class="sxs-lookup"><span data-stu-id="c190c-159">Every call queue is required to have an associated [resource account](manage-resource-accounts.md).</span></span> <span data-ttu-id="c190c-160">必须先创建资源帐户，然后才能将其关联到呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="c190c-160">You must create the resource account first, then you can associate it to the call queue.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="c190c-161">使用 Microsoft 团队管理中心</span><span class="sxs-lookup"><span data-stu-id="c190c-161">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="c190c-162">在**Microsoft 团队管理中心**、**语音** > **呼叫队列**中，单击 " **+ 添加新**"：</span><span class="sxs-lookup"><span data-stu-id="c190c-162">In the **Microsoft Teams admin center**, **Voice** > **Call queues**, then click **+ Add new**:</span></span>

### <a name="set-the-call-queue-display-name-and-resource-account"></a><span data-ttu-id="c190c-163">设置呼叫队列显示名称和资源帐户</span><span class="sxs-lookup"><span data-stu-id="c190c-163">Set the call queue display name and resource account</span></span>

![带有编号标注的新通话队列的屏幕截图](media/37ecc300-a108-4294-8463-fce570dfce72.png)

* * *

<span data-ttu-id="c190c-165">![数字1的图标，引用上一个屏幕截图](media/sfbcallout1.png)
**名称**中的标注输入呼叫队列的描述性显示名称。</span><span class="sxs-lookup"><span data-stu-id="c190c-165">![Icon of the number 1, referencing a callout in the previous screenshot](media/sfbcallout1.png)
**Name** Enter a descriptive display name for the call queue.</span></span> <span data-ttu-id="c190c-166">此名称是必需的，最多可包含64个字符，包括空格。</span><span class="sxs-lookup"><span data-stu-id="c190c-166">This name is required and can contain up to 64 characters, including spaces.</span></span>

 <span data-ttu-id="c190c-167">此名称显示在传入呼叫的通知中。</span><span class="sxs-lookup"><span data-stu-id="c190c-167">This name is displayed in the notification for the incoming call.</span></span>

* * *

![数字2的图标，引用上一个屏幕截图中的标注](media/sfbcallout2.png)

<span data-ttu-id="c190c-169">**添加帐户**选择资源帐户。</span><span class="sxs-lookup"><span data-stu-id="c190c-169">**Add Accounts** Select a resource account.</span></span> <span data-ttu-id="c190c-170">资源帐户可能与呼叫队列的服务收费或免费电话号码相关联，但是每个通话队列都需要关联的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="c190c-170">The resource account may or may not be associated with a service toll or toll-free phone number for the call queue, but each call queue requires an associated resource account.</span></span>

<span data-ttu-id="c190c-171">如果未列出任何列表，则需要先获取服务号码并将其分配给资源帐户，如前文所述。</span><span class="sxs-lookup"><span data-stu-id="c190c-171">If there aren't any listed, you need to get service numbers and assign them to a Resource account before you can create this call queue, as described earlier.</span></span> <span data-ttu-id="c190c-172">若要获取你的服务号码，请参阅[获取服务电话号码](getting-service-phone-numbers.md)。</span><span class="sxs-lookup"><span data-stu-id="c190c-172">To get your service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md).</span></span> <span data-ttu-id="c190c-173">按照 "[管理团队中的资源帐户](manage-resource-accounts.md)" 中所述创建资源帐户（如果希望呼叫队列具有相关联的电话号码）。</span><span class="sxs-lookup"><span data-stu-id="c190c-173">You create a resource account as described in [Manage resource accounts in Teams](manage-resource-accounts.md) if you want your call queue to have an associated phone number.</span></span>

> [!NOTE]
> <span data-ttu-id="c190c-174">如果你希望或需要分配**域**，你可以通过将其分配给呼叫队列的资源帐户来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="c190c-174">If you want or need to assign a **Domain** you would do so by assigning it to the resource account for the call queue.</span></span>

### <a name="set-the-greeting-and-music-played-while-on-hold"></a><span data-ttu-id="c190c-175">设置通话保持时播放的问候语和音乐</span><span class="sxs-lookup"><span data-stu-id="c190c-175">Set the greeting and music played while on hold</span></span>

![带有编号标注的问候和音乐选项的屏幕截图](media/1d395a93-7cab-4178-9295-12d5379e20de.png)

* * *

![数字1的图标，引用上一个屏幕截图中的标注](media/sfbcallout1.png)

<span data-ttu-id="c190c-178">**问候语**是可选设置。</span><span class="sxs-lookup"><span data-stu-id="c190c-178">**Greeting** is optional.</span></span> <span data-ttu-id="c190c-179">这是呼叫呼叫队列号码的用户所播放的问候语。</span><span class="sxs-lookup"><span data-stu-id="c190c-179">This is the greeting that is played for people who call in to the call queue number.</span></span>

<span data-ttu-id="c190c-180">你可以上载音频文件（.wav、mp3 或 .wma 格式）。</span><span class="sxs-lookup"><span data-stu-id="c190c-180">You can upload an audio file (.wav, .mp3, or .wma formats).</span></span>

![数字2的图标，引用上一个屏幕截图中的标注](media/sfbcallout2.png)

<span data-ttu-id="c190c-182">**暂停的音乐**你可以使用与呼叫队列一起提供的默认音乐保持通话，也可以将音频文件上载为 .wav、mp3 或 .wma 格式，用作保留的自定义音乐。</span><span class="sxs-lookup"><span data-stu-id="c190c-182">**Music on hold** You can either use the default Music on Hold provided with the call queue, or you can upload an audio file in .wav, mp3, or .wma formats to use as your custom Music on Hold.</span></span>

* * *

### <a name="select-the-call-answering-options"></a><span data-ttu-id="c190c-183">选择呼叫应答选项</span><span class="sxs-lookup"><span data-stu-id="c190c-183">Select the call answering options</span></span>

![带有编号标注的呼叫应答选项的屏幕截图](media/5d249515-d532-4af2-90da-011404028b89.png)

![数字1的图标，引用上一个屏幕截图中的标注](media/sfbcallout1.png)

<span data-ttu-id="c190c-186">你可以选择多达200个呼叫代理，该代理属于以下任意邮件列表或组：</span><span class="sxs-lookup"><span data-stu-id="c190c-186">You can select up to 200 call agents who belong to any of the following mailing lists or groups:</span></span>

- <span data-ttu-id="c190c-187">Office 365 组</span><span class="sxs-lookup"><span data-stu-id="c190c-187">Office 365 group</span></span>
- <span data-ttu-id="c190c-188">安全组</span><span class="sxs-lookup"><span data-stu-id="c190c-188">Security group</span></span>
- <span data-ttu-id="c190c-189">通讯组列表</span><span class="sxs-lookup"><span data-stu-id="c190c-189">Distribution list</span></span>

<span data-ttu-id="c190c-190">所选呼叫代理必须是以下各项之一：</span><span class="sxs-lookup"><span data-stu-id="c190c-190">Call agents selected must be one of the following:</span></span> 

- <span data-ttu-id="c190c-191">使用电话系统许可证和启用企业语音的联机用户</span><span class="sxs-lookup"><span data-stu-id="c190c-191">Online users with a Phone System license and Enterprise Voice enabled</span></span> 
- <span data-ttu-id="c190c-192">使用呼叫计划的在线用户</span><span class="sxs-lookup"><span data-stu-id="c190c-192">Online users with a  Calling Plan</span></span>
- <span data-ttu-id="c190c-193">本地 Skype for Business 服务器用户</span><span class="sxs-lookup"><span data-stu-id="c190c-193">On-premises Skype for Business Server users</span></span>

  > [!NOTE]
  > <span data-ttu-id="c190c-194">如果您想要将呼叫重定向到您的组织中联机的人员，也可以使用此操作。</span><span class="sxs-lookup"><span data-stu-id="c190c-194">This also applies if you want to redirect calls to people in your organization who are online.</span></span> <span data-ttu-id="c190c-195">这些人必须具有**电话系统**许可证，并且已启用企业语音**或**有呼叫计划。</span><span class="sxs-lookup"><span data-stu-id="c190c-195">These individuals must have a **Phone System** license and Enterprise Voice enabled **or** have a Calling Plan.</span></span> <span data-ttu-id="c190c-196">有关详细信息，请参阅[分配 Skype for business 许可证](/Skype/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)、[分配 Microsoft 团队许可证](https://docs.microsoft.com/microsoftteams/assign-teams-licenses)或适合[您的通话计划？](https://docs.microsoft.com/microsoftteams/calling-plan-landing-page)</span><span class="sxs-lookup"><span data-stu-id="c190c-196">For more information, see [Assign Skype for Business licenses](/Skype/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md), [Assign Microsoft Teams licenses](https://docs.microsoft.com/microsoftteams/assign-teams-licenses), or [Which Calling Plan is right for you?](https://docs.microsoft.com/microsoftteams/calling-plan-landing-page)</span></span>

 <span data-ttu-id="c190c-197">若要启用企业语音代理，你可以使用 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="c190c-197">To enable an agent for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="c190c-198">例如，运行：`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="c190c-198">For example, run: `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

- <span data-ttu-id="c190c-199">具有**电话系统**许可证或添加到 Office 365 组的呼叫计划的用户;启用邮件的通讯组列表;或安全组。</span><span class="sxs-lookup"><span data-stu-id="c190c-199">Users with a **Phone System** license or a Calling Plan that are added to either an Office 365 Group; a mail-enabled Distribution List; or a Security Group.</span></span> <span data-ttu-id="c190c-200">通讯组列表或安全组中新添加的代理可能需要长达3小时才能开始从呼叫队列接收呼叫。</span><span class="sxs-lookup"><span data-stu-id="c190c-200">It might take up to three hours for a newly added agent in a distribution list, or a security group, to start receiving calls from a call queue.</span></span> <span data-ttu-id="c190c-201">新创建的通讯组列表或安全组可能需要长达48小时才能与通话队列一起使用。</span><span class="sxs-lookup"><span data-stu-id="c190c-201">A newly created distribution list or security group might take up to 48 hours to become available to be used with call queues.</span></span> <span data-ttu-id="c190c-202">新创建的 Office 365 组几乎立即就可使用。</span><span class="sxs-lookup"><span data-stu-id="c190c-202">Newly created Office 365 Groups are available almost immediately.</span></span>

- <span data-ttu-id="c190c-203">如果你的代理使用 Microsoft 团队应用进行呼叫队列呼叫，则他们必须处于 TeamsOnly 模式。</span><span class="sxs-lookup"><span data-stu-id="c190c-203">If your agents are using Microsoft Teams App to take call queue calls, they need to be in TeamsOnly mode.</span></span>

!["添加呼叫代理" 窗格的屏幕截图](media/skype-for-business-add-agents-to-call-queue.png)

![数字2的图标，引用上一个屏幕截图中的标注](media/sfbcallout2.png)

<span data-ttu-id="c190c-206">**路由方法**您可以为您的通话队列分发方法选择 "**助理**"、"**串行**" 或 "**循环**"。</span><span class="sxs-lookup"><span data-stu-id="c190c-206">**Routing method** You can choose either **Attendant**, **Serial**, or **Round Robin** for your call queue distribution method.</span></span> <span data-ttu-id="c190c-207">所有新的和现有呼叫队列将具有默认情况下选中的助理路由。</span><span class="sxs-lookup"><span data-stu-id="c190c-207">All new and existing call queues will have attendant routing selected by default.</span></span> <span data-ttu-id="c190c-208">使用 "助理路由" 时，队列中的第一次呼叫将同时响铃所有呼叫工程师。</span><span class="sxs-lookup"><span data-stu-id="c190c-208">When attendant routing is used, the first call in the queue rings all call agents at the same time.</span></span> <span data-ttu-id="c190c-209">获取呼叫的第一个呼叫代理将获取呼叫。</span><span class="sxs-lookup"><span data-stu-id="c190c-209">The first call agent to pick up the call gets the call.</span></span>

- <span data-ttu-id="c190c-210">**助理路由**使队列中的第一次通话同时拨打所有呼叫工程师。</span><span class="sxs-lookup"><span data-stu-id="c190c-210">**Attendant routing** causes the first call in the queue to ring all call agents at the same time.</span></span> <span data-ttu-id="c190c-211">获取呼叫的第一个呼叫代理将获取呼叫。</span><span class="sxs-lookup"><span data-stu-id="c190c-211">The first call agent to pick up the call gets the call.</span></span>
- <span data-ttu-id="c190c-212">**串行路由**传入呼叫从呼叫代理列表的开始，逐个拨打呼叫工程师。</span><span class="sxs-lookup"><span data-stu-id="c190c-212">**Serial routing** incoming calls ring call agents one by one, starting from the beginning of the call agent list.</span></span> <span data-ttu-id="c190c-213">不能在 "呼叫代理程序" 列表中订购代理。</span><span class="sxs-lookup"><span data-stu-id="c190c-213">Agents cannot be ordered within the call agent list.</span></span> <span data-ttu-id="c190c-214">如果代理挂断或不接听电话，电话将打给列表的下一位代理，并将尝试逐个拨打所有代理，直到有人接听或队列等待超时为止。</span><span class="sxs-lookup"><span data-stu-id="c190c-214">If an agent dismisses or does not pick up a call, the call will ring the next agent on the list and will try all agents one by one until it is picked up or times out waiting in the queue.</span></span>
  > [!NOTE]
  > <span data-ttu-id="c190c-215">串行路由将跳过处于**脱机**状态、已将其状态设置为 **请勿打扰**或**已选择退出**不从此队列获取呼叫的代理。</span><span class="sxs-lookup"><span data-stu-id="c190c-215">Serial routing will skip agents who are **Offline**, have set their presence to **Do not Disturb**, or have **opted out** of getting calls from this queue.</span></span>
- <span data-ttu-id="c190c-216">**循环法**平衡传入呼叫的路由，以便每个呼叫代理从队列中获得相同数量的通话。</span><span class="sxs-lookup"><span data-stu-id="c190c-216">**Round robin** balances routing of incoming calls so that each call agent gets the same number of calls from the queue.</span></span> <span data-ttu-id="c190c-217">这在入站销售环境中可能需要确保所有呼叫代理的同等机遇。</span><span class="sxs-lookup"><span data-stu-id="c190c-217">This may be desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

### <a name="select-an-agent-opt-out-option"></a><span data-ttu-id="c190c-218">选择代理选择退出选项</span><span class="sxs-lookup"><span data-stu-id="c190c-218">Select an agent opt-out option</span></span>

![代理选择退出选项（带有编号标注）的屏幕截图](media/99279eff-db61-4acf-9b62-64be84b6414b.png)

* * *

![数字1的图标，引用上一个屏幕截图中的标注](media/sfbcallout1.png)

<span data-ttu-id="c190c-221">**工程师可以选择退出 "获取" 呼叫**通过启用此选项，您可以选择允许呼叫队列代理选择退出特定队列中的呼叫。</span><span class="sxs-lookup"><span data-stu-id="c190c-221">**Agent can opt out of getting calls** You can choose to allow call queue agents to opt-out of taking calls from a particular queue by enabling this option.</span></span>

<span data-ttu-id="c190c-222">如果启用此选项，将允许此队列中的所有代理从该呼叫队列开始或停止接收呼叫。</span><span class="sxs-lookup"><span data-stu-id="c190c-222">Enabling this option allows all agents in this queue to start or stop receiving calls from this call queue at will.</span></span> <span data-ttu-id="c190c-223">通过清除此复选框，你可以随时撤消代理选择退出特权，这将导致所有代理自动选择再加入此队列 （所有代理的默认设置）。</span><span class="sxs-lookup"><span data-stu-id="c190c-223">You can revoke the agent opt-out privilege at any time by clearing the check box, causing agents to become automatically opted in for this queue again (the default setting for all agents).</span></span>

<span data-ttu-id="c190c-224">若要访问选择退出选项，代理可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="c190c-224">To access the opt-out option, agents can do the following:</span></span>

 1. <span data-ttu-id="c190c-225">在其桌面 Skype for Business 客户端中打开**选项**。</span><span class="sxs-lookup"><span data-stu-id="c190c-225">Open **Options** in their desktop Skype for Business client.</span></span>
 2. <span data-ttu-id="c190c-226">在**呼叫转移**选项卡中，单击**在线编辑设置**链接。</span><span class="sxs-lookup"><span data-stu-id="c190c-226">On the **Call Forwarding** tab, click the **Edit settings online** link.</span></span>
 3. <span data-ttu-id="c190c-227">在 "用户设置" 页面上，单击 "**呼叫队列**"，然后清除要选择退出的任何队列的复选框。</span><span class="sxs-lookup"><span data-stu-id="c190c-227">On the user settings page, click **Call Queues**, and then clear the check boxes for any queues for which they want to opt-out.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c190c-228">使用 Skype for Business 桌面之外的应用或终结点的代理可以从 "用户设置" 门户[https://aka.ms/cqsettings](https://aka.ms/cqsettings)访问 "退出" 选项。</span><span class="sxs-lookup"><span data-stu-id="c190c-228">Agents using apps or endpoints other than Skype for Business Desktop can access the opt-out option from the user settings portal [https://aka.ms/cqsettings](https://aka.ms/cqsettings).</span></span>

<span data-ttu-id="c190c-229">![数字2的图标，在上一个屏幕截图](media/sfbcallout2.png)
中引用标注**Agent 警报设置**</span><span class="sxs-lookup"><span data-stu-id="c190c-229">![Icon of the number 2, referencing a callout in the previous screenshot](media/sfbcallout2.png)
**Agent Alert setting**</span></span>

<span data-ttu-id="c190c-230">这定义了在串行或循环路由方法移到下一个代理之前通知呼叫的代理的持续时间。</span><span class="sxs-lookup"><span data-stu-id="c190c-230">This defines the duration of an agent being notified of a call before the Serial or Round Robin routing methods move to the next agent.</span></span>

<span data-ttu-id="c190c-231">默认设置为30秒，但最多可设置3分钟。</span><span class="sxs-lookup"><span data-stu-id="c190c-231">The default setting is 30 seconds, but it can be set for up to 3 minutes.</span></span>

* * *

### <a name="set-the-call-overflow-and-timeout-handling-options"></a><span data-ttu-id="c190c-232">设置呼叫溢出和超时处理选项</span><span class="sxs-lookup"><span data-stu-id="c190c-232">Set the call overflow and timeout handling options</span></span>

![带有编号标注的溢出处理选项的屏幕截图](media/3f018734-16fe-458b-827d-71fc25155cde.png)

* * *

![数字1的图标，引用上一个屏幕截图中的标注](media/sfbcallout1.png)

<span data-ttu-id="c190c-235">**队列中的最大呼叫数** 使用此字段来设置同一时间可以在队列中等待的最大呼叫数。</span><span class="sxs-lookup"><span data-stu-id="c190c-235">**Maximum calls in the queue** Use this to set the maximum calls that can wait in the queue at the same time.</span></span> <span data-ttu-id="c190c-236">默认值为50，但范围可以从0到200。</span><span class="sxs-lookup"><span data-stu-id="c190c-236">The default is 50, but it can range from 0 to 200.</span></span> <span data-ttu-id="c190c-237">当达到此限制时，将按照在 "**达到最大通话次数时**" 设置中设置的方式处理呼叫。</span><span class="sxs-lookup"><span data-stu-id="c190c-237">When this limit is reached, the call is handled in the way you set on the **When the maximum number of calls is reached** setting below.</span></span>

* * *

![数字2的图标，引用上一个屏幕截图中的标注](media/sfbcallout2.png)

<span data-ttu-id="c190c-239">**达到最大通话次数时**当通话队列达到最大值（使用 **"队列" 设置中的最大通话**设置）时，您可以选择新的传入呼叫发生的情况。</span><span class="sxs-lookup"><span data-stu-id="c190c-239">**When the maximum number of calls is reached** When the call queue reaches its maximum size (set using the **Maximum calls in the queue** setting), you can choose what happens to new incoming calls.</span></span>

- <span data-ttu-id="c190c-240">**断开连接**通话断开。</span><span class="sxs-lookup"><span data-stu-id="c190c-240">**Disconnect** The call is disconnected.</span></span>
- <span data-ttu-id="c190c-241">**重定向到**选择此项时，请选择下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="c190c-241">**Redirect to** When you choose this, select one of the following:</span></span>

  - <span data-ttu-id="c190c-242">**公司中的人员**具有**电话系统**许可证并启用企业语音或具有呼叫计划的在线用户。</span><span class="sxs-lookup"><span data-stu-id="c190c-242">**Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have a Calling Plan.</span></span> <span data-ttu-id="c190c-243">您可以对其进行设置，以便呼叫者可以发送到语音邮件。</span><span class="sxs-lookup"><span data-stu-id="c190c-243">You can set it up so the caller can be sent to voicemail.</span></span> <span data-ttu-id="c190c-244">若要执行此操作，请选择**您的公司中的人员**，并将其呼叫直接转发到语音邮件。</span><span class="sxs-lookup"><span data-stu-id="c190c-244">To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span>

  <span data-ttu-id="c190c-245">若要了解语音邮件所需的许可证，请参阅[设置云语音邮件](set-up-phone-system-voicemail.md)。</span><span class="sxs-lookup"><span data-stu-id="c190c-245">To learn about licenses required for voicemail, see [Set up Cloud Voicemail](set-up-phone-system-voicemail.md).</span></span>

  - <span data-ttu-id="c190c-246">**语音应用程序**选择与已创建的呼叫队列或自动助理相关联的资源帐户的名称。</span><span class="sxs-lookup"><span data-stu-id="c190c-246">**Voice application** Select the name of a resource account associated to either a call queue or auto attendant that has already been created.</span></span>

* * *

![数字3的图标，引用上一个屏幕截图中的标注](media/sfbcallout3.png)

<span data-ttu-id="c190c-248">**呼叫超时：最长等待时间**您还可以决定呼叫在队列中保留多长时间，并且需要重定向或断开连接。</span><span class="sxs-lookup"><span data-stu-id="c190c-248">**Call Timeout: maximum wait time** You can also decide how much time a call can be on hold in the queue before it times out and needs to be redirected or disconnected.</span></span> <span data-ttu-id="c190c-249">重定向的位置取决于设置**通话超时**设置的方式。</span><span class="sxs-lookup"><span data-stu-id="c190c-249">Where it is redirected is based on how you set the **When a call times out** setting.</span></span> <span data-ttu-id="c190c-250">你可以将此时间设置为 0 到 45 分钟。</span><span class="sxs-lookup"><span data-stu-id="c190c-250">You can set a time from 0 to 45 minutes.</span></span>

<span data-ttu-id="c190c-251">超时值可以以秒为单位按 15 秒间隔进行设置。</span><span class="sxs-lookup"><span data-stu-id="c190c-251">The timeout value can be set in seconds, at 15-second intervals.</span></span> <span data-ttu-id="c190c-252">这样，你可以以更细的粒度操作呼叫流。</span><span class="sxs-lookup"><span data-stu-id="c190c-252">This allows you to manipulate the call flow with finer granularity.</span></span> <span data-ttu-id="c190c-253">例如，您可以指定30秒内代理未接听的任何通话转到目录搜索自动助理。</span><span class="sxs-lookup"><span data-stu-id="c190c-253">For example, you could specify that any calls that are not answered by an agent within 30 seconds go to a Directory Search auto attendant.</span></span>

![数字4的图标，引用上一个屏幕截图中的标注](media/sfbcallout4.png)

<span data-ttu-id="c190c-255">**拨出的时间**当呼叫达到您在 "队列" 设置**中呼叫可以等待的时间**限制时，您可以选择对此呼叫执行的操作：</span><span class="sxs-lookup"><span data-stu-id="c190c-255">**When call times out** When the call reaches the limit you set on the **How long a call can wait in the queue** setting, you can choose what happens to this call:</span></span>

- <span data-ttu-id="c190c-256">**断开连接**通话断开。</span><span class="sxs-lookup"><span data-stu-id="c190c-256">**Disconnect** The call is disconnected.</span></span>
- <span data-ttu-id="c190c-257">**将此呼叫重定向到**如果选择此选项，则可以使用以下选项：</span><span class="sxs-lookup"><span data-stu-id="c190c-257">**Redirect this call to** When you choose this, you have these options:</span></span>
  - <span data-ttu-id="c190c-258">**公司中的人员**具有**电话系统**许可证并启用企业语音或具有通话计划的在线用户。</span><span class="sxs-lookup"><span data-stu-id="c190c-258">**Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have Calling Plans.</span></span> <span data-ttu-id="c190c-259">你可以通过此设置将呼叫者直接转到语音邮件。</span><span class="sxs-lookup"><span data-stu-id="c190c-259">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="c190c-260">若要执行此操作，请选择**您的公司中的人员**，并将其呼叫直接转发到语音邮件。</span><span class="sxs-lookup"><span data-stu-id="c190c-260">To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span>

  <span data-ttu-id="c190c-261">若要了解语音邮件所需的许可，请参阅[设置云语音邮件](set-up-phone-system-voicemail.md)。</span><span class="sxs-lookup"><span data-stu-id="c190c-261">To learn about licensing required for voicemail, see [Set up Cloud Voicemail](set-up-phone-system-voicemail.md).</span></span>

  - <span data-ttu-id="c190c-262">**语音应用程序**选择与已创建的通话队列或自动助理相关联的资源帐户的名称。</span><span class="sxs-lookup"><span data-stu-id="c190c-262">**Voice application** Select the name of a resource account associated with either a call queue or auto attendant that has already been created.</span></span>

## <a name="change-a-users-caller-id-for-outbound-calls"></a><span data-ttu-id="c190c-263">更改用于出站呼叫的用户来电显示</span><span class="sxs-lookup"><span data-stu-id="c190c-263">Change a user's Caller ID for outbound calls</span></span>

<span data-ttu-id="c190c-264">你可以通过将呼叫队列、自动助理或任何服务号码的呼叫者 ID 改为使用**CsCallingLineIdentity** cmdlet 来保护用户的身份。</span><span class="sxs-lookup"><span data-stu-id="c190c-264">You can protect a user's identity by changing their caller ID for outbound calls to a call queue, auto attendant, or any service number instead using the **New-CsCallingLineIdentity** cmdlet.</span></span>

<span data-ttu-id="c190c-265">若要执行此操作，请运行：</span><span class="sxs-lookup"><span data-stu-id="c190c-265">To do this, run:</span></span>

``` Powershell
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

<span data-ttu-id="c190c-266">然后使用 **Grant-CallingLineIdentity** cmdlet 将策略应用于用户。</span><span class="sxs-lookup"><span data-stu-id="c190c-266">Then apply the policy to the user using the **Grant-CallingLineIdentity** cmdlet.</span></span> <span data-ttu-id="c190c-267">若要执行此操作，请运行：</span><span class="sxs-lookup"><span data-stu-id="c190c-267">To do this, run:</span></span>

``` Powershell
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

<span data-ttu-id="c190c-268">有关如何在您的组织中设置来电显示设置的详细信息，[请访问如何在您的组织中使用呼叫者 id](/microsoftteams/how-can-caller-id-be-used-in-your-organization)。</span><span class="sxs-lookup"><span data-stu-id="c190c-268">You can get more information on how to set caller ID settings in your organization in the article [How can caller ID be used in your organization](/microsoftteams/how-can-caller-id-be-used-in-your-organization).</span></span>

## <a name="call-queue-cmdlets"></a><span data-ttu-id="c190c-269">呼叫队列 cmdlet</span><span class="sxs-lookup"><span data-stu-id="c190c-269">Call queue cmdlets</span></span>

<span data-ttu-id="c190c-270">还可以使用 Windows PowerShell 来创建和设置呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="c190c-270">You can also use Windows PowerShell to create and set up call queues.</span></span> <span data-ttu-id="c190c-271">下面是用于管理呼叫队列的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c190c-271">Here are the cmdlets that you use to manage a call queue.</span></span>

- [<span data-ttu-id="c190c-272">新-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="c190c-272">New-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="c190c-273">Set-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="c190c-273">Set-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/set-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="c190c-274">CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="c190c-274">Get-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/get-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="c190c-275">Remove-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="c190c-275">Remove-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-CsCallQueue?view=skype-ps)

### <a name="more-about-windows-powershell"></a><span data-ttu-id="c190c-276">有关 Windows PowerShell 的详细信息</span><span class="sxs-lookup"><span data-stu-id="c190c-276">More about Windows PowerShell</span></span>

- <span data-ttu-id="c190c-277">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。</span><span class="sxs-lookup"><span data-stu-id="c190c-277">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="c190c-278">使用 Windows PowerShell，你可以使用单个管理点管理 Office 365 和 Microsoft 团队，这样，当你有多个任务需要执行操作时，可以简化日常工作。</span><span class="sxs-lookup"><span data-stu-id="c190c-278">With Windows PowerShell, you can manage Office 365 and Microsoft Teams with a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="c190c-279">若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="c190c-279">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="c190c-280">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="c190c-280">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [<span data-ttu-id="c190c-281">为什么要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="c190c-281">Why you need to use Office 365 PowerShell</span></span>](https://docs.microsoft.com/en-us/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- <span data-ttu-id="c190c-282">Windows PowerShell 在速度、简单性和工作效率方面具有许多比 Microsoft 团队管理中心更多的优势，例如，当您同时为多个用户设置更改时。</span><span class="sxs-lookup"><span data-stu-id="c190c-282">Windows PowerShell has many advantages in speed, simplicity, and productivity over the Microsoft Teams admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="c190c-283">通过以下主题了解这些优势：</span><span class="sxs-lookup"><span data-stu-id="c190c-283">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="c190c-284">通过 Windows PowerShell 管理 Office 365</span><span class="sxs-lookup"><span data-stu-id="c190c-284">Manage Office 365 with Windows PowerShell</span></span>](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [<span data-ttu-id="c190c-285">为 Windows PowerShell 设置计算机</span><span class="sxs-lookup"><span data-stu-id="c190c-285">Set up your computer for Windows PowerShell</span></span>](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a><span data-ttu-id="c190c-286">相关主题</span><span class="sxs-lookup"><span data-stu-id="c190c-286">Related topics</span></span>

[<span data-ttu-id="c190c-287">以下是 Office 365 中的电话系统功能</span><span class="sxs-lookup"><span data-stu-id="c190c-287">Here's what you get with Phone System in Office 365</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="c190c-288">获取服务电话号码</span><span class="sxs-lookup"><span data-stu-id="c190c-288">Getting service phone numbers</span></span>](getting-service-phone-numbers.md)

[<span data-ttu-id="c190c-289">音频会议和通话套餐的国家/地区可用性</span><span class="sxs-lookup"><span data-stu-id="c190c-289">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="c190c-290">新-CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="c190c-290">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
