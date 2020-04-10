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
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.callqueues.overview"
- Phone System
description: 了解如何为 Microsoft 团队设置云呼叫队列的电话系统。
ms.openlocfilehash: e6ff659790159595c86a2aa442bcb20bcff9659a
ms.sourcegitcommit: 1d24b62f41bce4f8d86d6060291af1267f75a2a2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "43213645"
---
# <a name="create-a-cloud-call-queue"></a><span data-ttu-id="3ec35-103">创建云呼叫队列</span><span class="sxs-lookup"><span data-stu-id="3ec35-103">Create a Cloud call queue</span></span>

<span data-ttu-id="3ec35-104">云呼叫队列可以提供：</span><span class="sxs-lookup"><span data-stu-id="3ec35-104">Cloud call queues can provide:</span></span>

- <span data-ttu-id="3ec35-105">一条问候语。</span><span class="sxs-lookup"><span data-stu-id="3ec35-105">A greeting message.</span></span>
- <span data-ttu-id="3ec35-106">在呼叫者保持等待时播放的音乐。</span><span class="sxs-lookup"><span data-stu-id="3ec35-106">Music while people are waiting on hold.</span></span>
- <span data-ttu-id="3ec35-107">使用启用邮件的通讯组列表和安全组将呼叫重定向到呼叫代理。</span><span class="sxs-lookup"><span data-stu-id="3ec35-107">Redirecting calls to call agents in mail-enabled distribution lists and security groups.</span></span>
- <span data-ttu-id="3ec35-108">设置不同的参数，例如队列最大大小、超时和通话处理选项。</span><span class="sxs-lookup"><span data-stu-id="3ec35-108">Setting different parameters such as queue maximum size, timeout, and call handling options.</span></span>
- <span data-ttu-id="3ec35-109">面向呼叫者的共享语音邮件为组织留下消息。</span><span class="sxs-lookup"><span data-stu-id="3ec35-109">Shared voicemail for callers to leave a message for an organization.</span></span>

<span data-ttu-id="3ec35-110">您不会直接将电话号码与呼叫队列相关联，而是将电话号码与[资源帐户](manage-resource-accounts.md)相关联。</span><span class="sxs-lookup"><span data-stu-id="3ec35-110">You don't directly associate a phone number to a call queue, instead the phone number is associated to a [resource account](manage-resource-accounts.md).</span></span> <span data-ttu-id="3ec35-111">可通过自动助理上的选择直接拨打或访问呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="3ec35-111">A call queue can be dialed directly or accessed by a selection on an auto attendant.</span></span>

<span data-ttu-id="3ec35-112">呼叫者在处于暂停状态时将听到音乐，并且呼叫将首先连接到呼叫代理，*即先出*（FIFO）订单。</span><span class="sxs-lookup"><span data-stu-id="3ec35-112">The caller hears music while they are on hold, and the call connects to the call agents in *First In, First Out* (FIFO) order.</span></span>

<span data-ttu-id="3ec35-113">通过以下方法之一将队列中的所有调用发送到代理：</span><span class="sxs-lookup"><span data-stu-id="3ec35-113">All calls in the queue are sent to agents by one of the following methods:</span></span>

- <span data-ttu-id="3ec35-114">通过助理路由，队列中的第一个通话将同时响铃所有代理。</span><span class="sxs-lookup"><span data-stu-id="3ec35-114">With attendant routing, the first call in the queue  rings all agents at the same time.</span></span>
- <span data-ttu-id="3ec35-115">通过串行路由，队列中的第一次呼叫将每个呼叫代理逐一响铃一次。</span><span class="sxs-lookup"><span data-stu-id="3ec35-115">With serial routing, the first call in the queue rings all call agents one by one.</span></span>
- <span data-ttu-id="3ec35-116">通过循环复用，传入呼叫的路由是平衡的，以便每个呼叫代理从队列中获得相同数量的通话。</span><span class="sxs-lookup"><span data-stu-id="3ec35-116">With round robin, routing of incoming calls is balanced so that each call agent gets the same number of calls from the queue.</span></span>

<span data-ttu-id="3ec35-117">你可以设置呼叫处理选项，如代理选择加入/选择退出、基于状态的路由、呼叫等待时间以及用上述任何方法调用超时选项。</span><span class="sxs-lookup"><span data-stu-id="3ec35-117">You can set call handling options, such as agent opt-in/opt-out, presence-based routing, call wait time, and call time-out options with any of the above methods.</span></span>

<span data-ttu-id="3ec35-118">一次仅有一个传入呼叫通知（在队列的头呼叫）转到呼叫代理。</span><span class="sxs-lookup"><span data-stu-id="3ec35-118">Only one incoming call notification (for the call at the head of the queue) at a time goes to the call agents.</span></span> <span data-ttu-id="3ec35-119">呼叫代理接受呼叫后，队列中的下一个传入呼叫开始拨叫所有代理。</span><span class="sxs-lookup"><span data-stu-id="3ec35-119">After a call agent accepts the call, the next incoming call in the queue will start ringing call agents.</span></span>

> [!NOTE]
> <span data-ttu-id="3ec35-120">本文适用于 Microsoft 团队和 Skype for business Online。</span><span class="sxs-lookup"><span data-stu-id="3ec35-120">This article applies to both Microsoft Teams and Skype for Business Online.</span></span>

## <a name="step-1--get-started"></a><span data-ttu-id="3ec35-121">步骤 1-入门</span><span class="sxs-lookup"><span data-stu-id="3ec35-121">Step 1 — Get started</span></span>

<span data-ttu-id="3ec35-122">要开始使用呼叫队列，记住以下几点至关重要：</span><span class="sxs-lookup"><span data-stu-id="3ec35-122">To get started using call queues, it's important to remember a few things:</span></span>

- <span data-ttu-id="3ec35-123">通话队列必须具有关联的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="3ec35-123">A call queue is required to have an associated resource account.</span></span> <span data-ttu-id="3ec35-124">有关资源帐户的详细信息，请参阅[管理团队中的资源帐户](manage-resource-accounts.md)。</span><span class="sxs-lookup"><span data-stu-id="3ec35-124">See [Manage resource accounts in Teams](manage-resource-accounts.md) for details on resource accounts.</span></span>
- <span data-ttu-id="3ec35-125">将电话号码分配给资源帐户时，您现在可以使用 "免费电话系统[虚拟用户" 许可证](teams-add-on-licensing/virtual-user.md)。</span><span class="sxs-lookup"><span data-stu-id="3ec35-125">When you assign a phone number to a resource account, you can now use the cost-free Phone System [Virtual User license](teams-add-on-licensing/virtual-user.md).</span></span> <span data-ttu-id="3ec35-126">电话系统允许组织级别的电话号码与低成本的自动助理和呼叫队列服务配合使用。</span><span class="sxs-lookup"><span data-stu-id="3ec35-126">Phone System allows phone numbers at the organizational level for use with low-cost auto attendant and call queue services.</span></span>

> [!NOTE]
> <span data-ttu-id="3ec35-127">只有 Microsoft 团队用户和代理才支持直接路由呼叫队列服务号码。</span><span class="sxs-lookup"><span data-stu-id="3ec35-127">Direct Routing service numbers for call queues are supported for Microsoft Teams users and agents only.</span></span>

> [!NOTE]
> <span data-ttu-id="3ec35-128">若要将呼叫重定向到您的组织中联机的人员，他们必须具有**电话系统**许可证并启用企业语音或拥有 Office 365 通话计划。</span><span class="sxs-lookup"><span data-stu-id="3ec35-128">To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans.</span></span> <span data-ttu-id="3ec35-129">请参阅[分配 Microsoft 团队许可证](assign-teams-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="3ec35-129">See [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="3ec35-130">To enable them for Enterprise Voice, you can use Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3ec35-130">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="3ec35-131">例如，运行：`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="3ec35-131">For example, run: `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

- <span data-ttu-id="3ec35-132">若要了解有关 Office 365 呼叫计划的详细信息，请参阅[手机系统和通话计划](calling-plan-landing-page.md)和[Office 365 的呼叫计划](calling-plans-for-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="3ec35-132">To learn more about Office 365 Calling Plans, see [Phone System and Calling Plans](calling-plan-landing-page.md) and [Calling Plans for Office 365](calling-plans-for-office-365.md).</span></span>

- <span data-ttu-id="3ec35-133">您只能将云呼叫队列分配给您在**Microsoft 团队管理中心**或从另一个服务提供商转移的收费电话号码和免费服务电话号码。</span><span class="sxs-lookup"><span data-stu-id="3ec35-133">You can only assign Cloud call queues toll and toll-free service phone numbers that you got in the **Microsoft Teams admin center** or transferred from another service provider.</span></span> <span data-ttu-id="3ec35-134">免费服务号码需要通讯信用点数。</span><span class="sxs-lookup"><span data-stu-id="3ec35-134">Communications Credits are required for toll-free service numbers.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3ec35-135">[!注释] 不能将用户（订阅者）的电话号码分配给呼叫队列 - 只能使用收费或免费服务电话号码。</span><span class="sxs-lookup"><span data-stu-id="3ec35-135">User (subscriber) phone numbers can't be assigned to call queues - only service toll or toll-free phone numbers can be used.</span></span>

- <span data-ttu-id="3ec35-136">以下客户端支持与云呼叫队列关联的呼叫代理：</span><span class="sxs-lookup"><span data-stu-id="3ec35-136">The following clients are supported for call agents associated to a Cloud call queue:</span></span>

  - <span data-ttu-id="3ec35-137">Skype for Business 桌面客户端2016（32位和64位版本）</span><span class="sxs-lookup"><span data-stu-id="3ec35-137">Skype for Business desktop client 2016 (32-bit and 64-bit versions)</span></span>

  - <span data-ttu-id="3ec35-138">Lync 桌面客户端2013（32位和64位版本）</span><span class="sxs-lookup"><span data-stu-id="3ec35-138">Lync desktop client 2013 (32-bit and 64-bit versions)</span></span>

  - <span data-ttu-id="3ec35-139">Microsoft 团队支持的所有 IP 电话模式。</span><span class="sxs-lookup"><span data-stu-id="3ec35-139">All IP phone models supported for Microsoft Teams.</span></span> <span data-ttu-id="3ec35-140">请参阅[获取适用于 Skype for Business Online 的电话](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online)。</span><span class="sxs-lookup"><span data-stu-id="3ec35-140">See [Getting phones for Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span></span>

  - <span data-ttu-id="3ec35-141">Mac Skype for Business 客户端（版本 16.8.196 及更高版本）</span><span class="sxs-lookup"><span data-stu-id="3ec35-141">Mac Skype for Business Client (version 16.8.196 and later)</span></span>

  - <span data-ttu-id="3ec35-142">Android Skype for Business 客户端（版本 6.16.0.9 及更高版本）</span><span class="sxs-lookup"><span data-stu-id="3ec35-142">Android Skype for Business Client (version 6.16.0.9 and later)</span></span>

  - <span data-ttu-id="3ec35-143">iPhone Skype for Business 客户端（版本 6.16.0 及更高版本）</span><span class="sxs-lookup"><span data-stu-id="3ec35-143">iPhone Skype for Business Client (version 6.16.0 and later)</span></span>

  - <span data-ttu-id="3ec35-144">iPad Skype for Business 客户端（版本 6.16.0 及更高版本）</span><span class="sxs-lookup"><span data-stu-id="3ec35-144">iPad Skype for Business Client (version 6.16.0 and later)</span></span>

  - <span data-ttu-id="3ec35-145">Microsoft 团队 Windows 客户端（32位和64位版本）</span><span class="sxs-lookup"><span data-stu-id="3ec35-145">Microsoft Teams Windows client (32-bit and 64-bit versions)</span></span>

  - <span data-ttu-id="3ec35-146">Microsoft Teams Mac 客户端</span><span class="sxs-lookup"><span data-stu-id="3ec35-146">Microsoft Teams Mac client</span></span>

  - <span data-ttu-id="3ec35-147">Microsoft Teams iPhone 应用</span><span class="sxs-lookup"><span data-stu-id="3ec35-147">Microsoft Teams iPhone app</span></span>

  - <span data-ttu-id="3ec35-148">Microsoft Teams Android 应用</span><span class="sxs-lookup"><span data-stu-id="3ec35-148">Microsoft Teams Android app</span></span>

    > [!NOTE]
    > <span data-ttu-id="3ec35-149">分配了直接路由号码的呼叫队列将不支持 Skype for business 客户端、Lync 客户端或 Skype for business IP 手机用作代理。</span><span class="sxs-lookup"><span data-stu-id="3ec35-149">Call queues that are assigned a direct routing number will not support Skype for Business clients, Lync clients, or Skype for Business IP Phones as agents.</span></span>

## <a name="step-2--get-or-transfer-toll-or-toll-free-service-phone-numbers"></a><span data-ttu-id="3ec35-150">步骤 2-获取或转移收费或免费服务电话号码</span><span class="sxs-lookup"><span data-stu-id="3ec35-150">Step 2 — Get or transfer toll or toll-free service phone numbers</span></span>

<span data-ttu-id="3ec35-151">在创建和设置呼叫队列之前，您需要获取或转移现有收费或免费服务号码。</span><span class="sxs-lookup"><span data-stu-id="3ec35-151">Before you can create and set up your call queues, you need to get or transfer your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="3ec35-152">若要获取你的服务号码，请参阅[获取服务电话号码](getting-service-phone-numbers.md)或要转移现有服务号码，请参阅[将电话号码转移到 Office 365](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="3ec35-152">To get your service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md) or if you want to transfer an existing service number, see [Transfer phone numbers to Office 365](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span> <span data-ttu-id="3ec35-153">获得收费或免费服务电话号码后，他们将显示在**Microsoft 团队管理中心** > 的**语音** > **电话号码**中。</span><span class="sxs-lookup"><span data-stu-id="3ec35-153">After you get the toll or toll-free service phone numbers, they will show up in **Microsoft Teams admin center** > **Voice** > **Phone numbers**.</span></span> <span data-ttu-id="3ec35-154">免费电话将列出一**种数字类型**的**服务-免费电话**号码。</span><span class="sxs-lookup"><span data-stu-id="3ec35-154">Toll free numbers will be listed with a **Number type** of **Service — Toll-Free**.</span></span>

> [!NOTE]
> <span data-ttu-id="3ec35-155">如果您在美国以外，则不能使用 Microsoft 团队管理中心获取服务号码。</span><span class="sxs-lookup"><span data-stu-id="3ec35-155">If you are outside the United States, you can't use the Microsoft Teams admin center to get service numbers.</span></span> <span data-ttu-id="3ec35-156">转到 "[管理你的组织的电话号码](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)" 以了解如何从美国以外的国家进行管理。</span><span class="sxs-lookup"><span data-stu-id="3ec35-156">Go to [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) instead to see how to do it from the outside of the United States.</span></span>

<span data-ttu-id="3ec35-157">设置多个自动助理时，通常会将电话号码分配给主自动助理的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="3ec35-157">When you set up multiple auto attendants, you would usually assign a phone number to the main auto attendant's resource account.</span></span> <span data-ttu-id="3ec35-158">与嵌套的自动助理或呼叫队列相关联的资源帐户通常不需要电话号码。</span><span class="sxs-lookup"><span data-stu-id="3ec35-158">Resource accounts associated to nested auto attendants or call queues often don't need phone numbers.</span></span> <span data-ttu-id="3ec35-159">该自动助理可以将呼叫者定向到呼叫队列或嵌套的自动助理，即使他们没有电话号码也是如此。</span><span class="sxs-lookup"><span data-stu-id="3ec35-159">That auto attendant can direct callers to your call queues or nested auto attendants even if they don't have a phone number.</span></span> <span data-ttu-id="3ec35-160">在这些情况下，你可以在系统中创建所有自动助理和呼叫队列，而无需分配拨号键盘选项，然后在稍后编辑设置。</span><span class="sxs-lookup"><span data-stu-id="3ec35-160">In those situations, you can create all auto attendants and call queues in your system without assigning dialpad options, and then edit the settings later.</span></span> <span data-ttu-id="3ec35-161">必须存在呼叫队列或自动助理才能将其设置为菜单选项。</span><span class="sxs-lookup"><span data-stu-id="3ec35-161">A call queue or auto attendant must exist to set it as a menu option.</span></span>

## <a name="step-3--create-a-call-queue"></a><span data-ttu-id="3ec35-162">步骤3—创建呼叫队列</span><span class="sxs-lookup"><span data-stu-id="3ec35-162">Step 3 — Create a call queue</span></span>

[!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

> [!IMPORTANT]
> <span data-ttu-id="3ec35-163">每个通话队列都必须具有关联的[资源帐户](manage-resource-accounts.md)。</span><span class="sxs-lookup"><span data-stu-id="3ec35-163">Every call queue is required to have an associated [resource account](manage-resource-accounts.md).</span></span> <span data-ttu-id="3ec35-164">必须先创建资源帐户，然后才能将其关联到呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="3ec35-164">You must create the resource account first, then you can associate it to the call queue.</span></span>

### <a name="use-the-microsoft-teams-admin-center"></a><span data-ttu-id="3ec35-165">使用 Microsoft 团队管理中心</span><span class="sxs-lookup"><span data-stu-id="3ec35-165">Use the Microsoft Teams admin center</span></span>

<span data-ttu-id="3ec35-166">在**Microsoft 团队管理中心**、**语音** > **呼叫队列**中，单击 " **+ 添加新**"：</span><span class="sxs-lookup"><span data-stu-id="3ec35-166">In the **Microsoft Teams admin center**, **Voice** > **Call queues**, then click **+ Add new**:</span></span>

### <a name="set-the-display-name-and-resource-account"></a><span data-ttu-id="3ec35-167">设置显示名称和资源帐户</span><span class="sxs-lookup"><span data-stu-id="3ec35-167">Set the display name and resource account</span></span>

![带有编号标注的新通话队列的屏幕截图](media/37ecc300-a108-4294-8463-fce570dfce72.png)

* * *

<span data-ttu-id="3ec35-169">![数字1的图标引用上一个屏幕截图](media/teamscallout1.png)
**名称**中的标注输入呼叫队列的描述性显示名称。</span><span class="sxs-lookup"><span data-stu-id="3ec35-169">![Icon of the number 1, references a callout in the previous screenshot](media/teamscallout1.png)
**Name** Enter a descriptive display name for the call queue.</span></span> <span data-ttu-id="3ec35-170">此名称是必需的，最多可包含64个字符，包括空格。</span><span class="sxs-lookup"><span data-stu-id="3ec35-170">This name is required and can contain up to 64 characters, including spaces.</span></span>

 <span data-ttu-id="3ec35-171">此名称显示在传入呼叫的通知中。</span><span class="sxs-lookup"><span data-stu-id="3ec35-171">This name is displayed in the notification for the incoming call.</span></span>

* * *

<span data-ttu-id="3ec35-172">![数字2的图标在前面的屏幕截图](media/teamscallout2.png)
中引用标注**添加帐户**选择资源帐户。</span><span class="sxs-lookup"><span data-stu-id="3ec35-172">![Icon of the number 2, references a callout in the previous screenshot](media/teamscallout2.png)
**Add Accounts** Select a resource account.</span></span> <span data-ttu-id="3ec35-173">所有通话队列都必须有一个资源帐户。</span><span class="sxs-lookup"><span data-stu-id="3ec35-173">All call queues are required to have a resource account.</span></span> <span data-ttu-id="3ec35-174">资源帐户不需要拥有服务收费电话号码或免费电话号码。</span><span class="sxs-lookup"><span data-stu-id="3ec35-174">Resource accounts aren't required to have a service toll or toll-free phone number.</span></span>

<span data-ttu-id="3ec35-175">如果没有列出任何服务号码，请在创建呼叫队列之前将其分配给资源帐户，如前文所述。</span><span class="sxs-lookup"><span data-stu-id="3ec35-175">If there aren't any listed,  get service numbers and assign them to a Resource account before you create the call queue, as described earlier.</span></span> <span data-ttu-id="3ec35-176">若要获取你的服务号码，请参阅[获取服务电话号码](getting-service-phone-numbers.md)。</span><span class="sxs-lookup"><span data-stu-id="3ec35-176">To get your service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md).</span></span> <span data-ttu-id="3ec35-177">有关如何分配电话号码的详细信息，请参阅[管理团队中的资源帐户](manage-resource-accounts.md)。</span><span class="sxs-lookup"><span data-stu-id="3ec35-177">See [Manage resource accounts in Teams](manage-resource-accounts.md) for specifics on how to assign a phone number.</span></span>

> [!NOTE]
> <span data-ttu-id="3ec35-178">如果你希望或需要分配**域**，你可以将其分配给呼叫队列的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="3ec35-178">If you want or need to assign a **Domain** you would  assign it to the resource account for the call queue.</span></span>

### <a name="set-the-greeting-and-music-played-while-on-hold"></a><span data-ttu-id="3ec35-179">设置通话保持时播放的问候语和音乐</span><span class="sxs-lookup"><span data-stu-id="3ec35-179">Set the greeting and music played while on hold</span></span>

![带有编号标注的问候和音乐选项的屏幕截图](media/1d395a93-7cab-4178-9295-12d5379e20de.png)

* * *

<span data-ttu-id="3ec35-181">![数字1的图标引用上一个屏幕截图](media/teamscallout1.png)
中的标注**问候语**呼叫呼叫队列号码的用户可以播放的可选问候语。</span><span class="sxs-lookup"><span data-stu-id="3ec35-181">![Icon of the number 1, references a callout in the previous screenshot](media/teamscallout1.png)
**Greeting** the optional greeting played for people who call the call queue number.</span></span>

<span data-ttu-id="3ec35-182">你可以上载音频文件（.wav、mp3 或 .wma 格式）。</span><span class="sxs-lookup"><span data-stu-id="3ec35-182">You can upload an audio file (.wav, .mp3, or .wma formats).</span></span>

<span data-ttu-id="3ec35-183">![数字2的图标在上一个屏幕截图](media/teamscallout2.png)
**音乐保留**中引用标注你可以使用随呼叫队列提供的默认音乐保持通话。</span><span class="sxs-lookup"><span data-stu-id="3ec35-183">![Icon of the number 2, references a callout in the previous screenshot](media/teamscallout2.png)
**Music on hold** You can use the default Music on Hold provided with the call queue.</span></span> <span data-ttu-id="3ec35-184">你还可以将 .wav、mp3 或 .wma 格式中的音频文件上传到保留时使用的自定义音乐。</span><span class="sxs-lookup"><span data-stu-id="3ec35-184">You can also upload an audio file in .wav, mp3, or .wma formats to use as your custom Music on hold.</span></span>

* * *

### <a name="select-the-call-answering-options"></a><span data-ttu-id="3ec35-185">选择呼叫应答选项</span><span class="sxs-lookup"><span data-stu-id="3ec35-185">Select the call answering options</span></span>

![呼叫应答选项的屏幕截图](media/teams-cq-call-answering-options.png)

<span data-ttu-id="3ec35-187">![数字1的图标引用上一个屏幕截图](media/teamscallout1.png)
中的标注**调用代理和组**直接添加单个代理，而不将它们添加到组中，请单击 "**添加用户**"。</span><span class="sxs-lookup"><span data-stu-id="3ec35-187">![Icon of the number 1, references a callout in the previous screenshot](media/teamscallout1.png)
**Call agents and groups** To add individual agents directly, without adding them to a group, click **Add users**.</span></span> <span data-ttu-id="3ec35-188">按希望接收呼叫的顺序放置单个代理。</span><span class="sxs-lookup"><span data-stu-id="3ec35-188">Put individual agents in the order in which you want them to receive the call.</span></span> <span data-ttu-id="3ec35-189">您最多可以添加20个单独的代理（若要添加20个以上的代理，请将它们放在一个组中）。</span><span class="sxs-lookup"><span data-stu-id="3ec35-189">You can add up to 20 individual agents (to add more than 20, put them in a group).</span></span>

<span data-ttu-id="3ec35-190">调用首先路由到单个代理，然后路由到组中的代理。</span><span class="sxs-lookup"><span data-stu-id="3ec35-190">Calls are routed first to individual agents, then to the agents in groups.</span></span> 

<span data-ttu-id="3ec35-191">你可以选择多达200个呼叫代理，该代理属于以下任意邮件列表或组：</span><span class="sxs-lookup"><span data-stu-id="3ec35-191">You can select up to 200 call agents who belong to any of the following mailing lists or groups:</span></span>

- <span data-ttu-id="3ec35-192">Office 365 组</span><span class="sxs-lookup"><span data-stu-id="3ec35-192">Office 365 group</span></span>
- <span data-ttu-id="3ec35-193">安全组</span><span class="sxs-lookup"><span data-stu-id="3ec35-193">Security group</span></span>
- <span data-ttu-id="3ec35-194">通讯组列表</span><span class="sxs-lookup"><span data-stu-id="3ec35-194">Distribution list</span></span>

<span data-ttu-id="3ec35-195">所选呼叫代理必须是以下各项之一：</span><span class="sxs-lookup"><span data-stu-id="3ec35-195">Call agents selected must be one of the following:</span></span>

- <span data-ttu-id="3ec35-196">使用电话系统许可证和启用企业语音的联机用户</span><span class="sxs-lookup"><span data-stu-id="3ec35-196">Online users with a Phone System license and Enterprise Voice enabled</span></span>
- <span data-ttu-id="3ec35-197">使用呼叫计划的在线用户</span><span class="sxs-lookup"><span data-stu-id="3ec35-197">Online users with a Calling Plan</span></span>
- <span data-ttu-id="3ec35-198">本地 Skype for Business 服务器用户</span><span class="sxs-lookup"><span data-stu-id="3ec35-198">On-premises Skype for Business Server users</span></span>

  > [!NOTE]
  > <span data-ttu-id="3ec35-199">如果您想要将呼叫重定向到您的组织中联机的人员，也可以使用此操作。</span><span class="sxs-lookup"><span data-stu-id="3ec35-199">This also applies if you want to redirect calls to people in your organization who are online.</span></span> <span data-ttu-id="3ec35-200">这些人必须具有**电话系统**许可证，并且已启用企业语音*或*有呼叫计划。</span><span class="sxs-lookup"><span data-stu-id="3ec35-200">These individuals must have a **Phone System** license and Enterprise Voice enabled *or* have a Calling Plan.</span></span> <span data-ttu-id="3ec35-201">有关详细信息，请参阅[分配 Skype for business 许可证](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses)、[分配 Microsoft 团队许可证](https://docs.microsoft.com/microsoftteams/assign-teams-licenses)或适合[您的通话计划？](https://docs.microsoft.com/microsoftteams/calling-plan-landing-page)</span><span class="sxs-lookup"><span data-stu-id="3ec35-201">For more information, see [Assign Skype for Business licenses](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses), [Assign Microsoft Teams licenses](https://docs.microsoft.com/microsoftteams/assign-teams-licenses), or [Which Calling Plan is right for you?](https://docs.microsoft.com/microsoftteams/calling-plan-landing-page)</span></span>

 <span data-ttu-id="3ec35-202">若要启用企业语音代理，你可以使用 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="3ec35-202">To enable an agent for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="3ec35-203">例如，运行：`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="3ec35-203">For example, run: `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

- <span data-ttu-id="3ec35-204">具有**电话系统**许可证或添加到 Office 365 组的呼叫计划的用户;启用邮件的通讯组列表;或安全组。</span><span class="sxs-lookup"><span data-stu-id="3ec35-204">Users with a **Phone System** license or a Calling Plan that are added to either an Office 365 Group; a mail-enabled Distribution List; or a Security Group.</span></span> <span data-ttu-id="3ec35-205">将通讯组列表或安全组中的代理添加为呼叫队列代理时，首次通话最多可能需要3个小时。</span><span class="sxs-lookup"><span data-stu-id="3ec35-205">When you add an agent in a distribution list or a security group as a call queue agent, it can take up to three hours for the first call to arrive.</span></span> <span data-ttu-id="3ec35-206">新创建的通讯组列表或安全组可能需要长达48小时才能与通话队列一起使用。</span><span class="sxs-lookup"><span data-stu-id="3ec35-206">A newly created distribution list or security group might take up to 48 hours to become available to be used with call queues.</span></span> <span data-ttu-id="3ec35-207">新创建的 Office 365 组几乎立即就可使用。</span><span class="sxs-lookup"><span data-stu-id="3ec35-207">Newly created Office 365 Groups are available almost immediately.</span></span>

- <span data-ttu-id="3ec35-208">如果你的代理正在使用 Microsoft 团队应用进行呼叫队列呼叫，则他们必须处于 TeamsOnly 模式。</span><span class="sxs-lookup"><span data-stu-id="3ec35-208">If your agents are using the Microsoft Teams app for call queue calls, they need to be in TeamsOnly mode.</span></span>

<span data-ttu-id="3ec35-209">![数字2的图标引用上一个屏幕截图](media/teamscallout2.png)
**路由方法**中的标注，你可以选择 "**助理**"、"**串行**" 或 "**循环" 机制**作为分发方法。</span><span class="sxs-lookup"><span data-stu-id="3ec35-209">![Icon of the number 2, references a callout in the previous screenshot](media/teamscallout2.png)
**Routing method** You can choose either **Attendant**, **Serial**, or **Round Robin** as the distribution method.</span></span> <span data-ttu-id="3ec35-210">默认情况下，所有新的和现有的通话队列均已选中 "助理路由"。</span><span class="sxs-lookup"><span data-stu-id="3ec35-210">All new and existing call queues have attendant routing selected by default.</span></span> <span data-ttu-id="3ec35-211">使用 "助理路由" 时，队列中的第一次呼叫将同时响铃所有呼叫工程师。</span><span class="sxs-lookup"><span data-stu-id="3ec35-211">When attendant routing is used, the first call in the queue rings all call agents at the same time.</span></span> <span data-ttu-id="3ec35-212">获取呼叫的第一个呼叫代理将获取呼叫。</span><span class="sxs-lookup"><span data-stu-id="3ec35-212">The first call agent to pick up the call gets the call.</span></span>

- <span data-ttu-id="3ec35-213">**助理路由**使队列中的第一次通话同时拨打所有呼叫工程师。</span><span class="sxs-lookup"><span data-stu-id="3ec35-213">**Attendant routing** causes the first call in the queue to ring all call agents at the same time.</span></span> <span data-ttu-id="3ec35-214">获取呼叫的第一个呼叫代理将获取呼叫。</span><span class="sxs-lookup"><span data-stu-id="3ec35-214">The first call agent to pick up the call gets the call.</span></span>
- <span data-ttu-id="3ec35-215">**串行路由**传入呼叫将所有呼叫代理从呼叫代理程序列表的开始处拨打一次。</span><span class="sxs-lookup"><span data-stu-id="3ec35-215">**Serial routing** incoming calls ring all call agents one by one, from the beginning of the call agent list.</span></span> <span data-ttu-id="3ec35-216">不能在 "呼叫代理程序" 列表中订购代理。</span><span class="sxs-lookup"><span data-stu-id="3ec35-216">Agents can't be ordered within the call agent list.</span></span> <span data-ttu-id="3ec35-217">如果代理程序已关闭或未接听呼叫，则呼叫将拨打下一个代理，并且将尝试所有代理，直到它已被获取或超时。</span><span class="sxs-lookup"><span data-stu-id="3ec35-217">If an agent dismisses or does not pick up a call, the call will ring the next agent and will try all agents until it is picked up or times out.</span></span>
- <span data-ttu-id="3ec35-218">**循环法**平衡传入呼叫的路由，以便每个呼叫代理从队列中获得相同数量的通话。</span><span class="sxs-lookup"><span data-stu-id="3ec35-218">**Round robin** balances routing of incoming calls so that each call agent gets the same number of calls from the queue.</span></span> <span data-ttu-id="3ec35-219">这在入站销售环境中可能需要确保所有呼叫代理的同等机遇。</span><span class="sxs-lookup"><span data-stu-id="3ec35-219">This may be desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

<span data-ttu-id="3ec35-220">![数字3的图标在上一个屏幕截图](media/teamscallout3.png)
基于状态的路由状态的**基于**状态的路由中引用标注使用呼叫代理的可用性状态来确定是否应将代理包含在所选路由方法的 "呼叫" 路由列表中。</span><span class="sxs-lookup"><span data-stu-id="3ec35-220">![Icon of the number 3, references a callout in the previous screenshot](media/teamscallout3.png)
**Presence-based routing** Presence-based routing uses the availability status of call agents to determine whether an agent should be included in the call routing list for the selected routing method.</span></span> <span data-ttu-id="3ec35-221">其可用性状态设置为 "**可用**" 的呼叫代理包括在 "呼叫" 传送列表中，并且可以接收呼叫。</span><span class="sxs-lookup"><span data-stu-id="3ec35-221">Call agents whose availability status is set to **Available** are included in the call routing list and can receive calls.</span></span> <span data-ttu-id="3ec35-222">其可用性状态设置为任何其他状态的代理将从呼叫路由列表中排除，并且在其可用性状态更改为 "**可用**" 之前不会收到呼叫。</span><span class="sxs-lookup"><span data-stu-id="3ec35-222">Agents whose availability status is set to any other status are excluded from the call routing list and won't receive calls until their availability status changes back to **Available**.</span></span>

<span data-ttu-id="3ec35-223">你可以使用任何路由方法启用基于状态的呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="3ec35-223">You can enable presence-based call routing with any of the routing methods.</span></span>

<span data-ttu-id="3ec35-224">如果某个代理选择退出呼叫，则无论其可用性状态如何设置，它们都不会包含在 "呼叫" 传送列表中。</span><span class="sxs-lookup"><span data-stu-id="3ec35-224">If an agent opts out of getting calls, they won't be included in the call routing list regardless of what their availability status is set to.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3ec35-225">启用基于状态的路由时，"呼叫" 传送列表中不包含使用 Skype for Business 客户端的代理，无论其可用性状态如何。</span><span class="sxs-lookup"><span data-stu-id="3ec35-225">Agents who use the Skype for Business client aren't included in the call routing list when presence-based routing is enabled, regardless of their availability status.</span></span> <span data-ttu-id="3ec35-226">不在呼叫传送列表中的代理将无法接收呼叫。</span><span class="sxs-lookup"><span data-stu-id="3ec35-226">Agents who aren't in the call routing list won't receive calls.</span></span> <span data-ttu-id="3ec35-227">如果您有使用 Skype for Business 的工程师，请不要启用基于状态的呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="3ec35-227">If you have agents who use Skype for Business, don't enable presence-based call routing.</span></span>

### <a name="select-an-agent-opt-out-option"></a><span data-ttu-id="3ec35-228">选择代理选择退出选项</span><span class="sxs-lookup"><span data-stu-id="3ec35-228">Select an agent opt-out option</span></span>

![代理选择退出选项（带有编号标注）的屏幕截图](media/99279eff-db61-4acf-9b62-64be84b6414b.png)

* * *

<span data-ttu-id="3ec35-230">![数字1的图标，引用上一个屏幕截图](media/teamscallout1.png)
代理中的标注可以选择不**获取呼叫**，您可以选择允许呼叫队列代理通过启用此选项来选择允许呼叫队列代理取消来自特定队列的呼叫。</span><span class="sxs-lookup"><span data-stu-id="3ec35-230">![Icon of the number 1, references a callout in the previous screenshot](media/teamscallout1.png)
**Agent can opt out of getting calls** You can choose to allow call queue agents to opt-out of taking calls from a particular queue by enabling this option.</span></span>

<span data-ttu-id="3ec35-231">如果启用此选项，将允许此队列中的所有代理从该呼叫队列开始或停止接收呼叫。</span><span class="sxs-lookup"><span data-stu-id="3ec35-231">Enabling this option allows all agents in this queue to start or stop receiving calls from this call queue at will.</span></span> <span data-ttu-id="3ec35-232">通过清除此复选框，你可以随时撤消代理选择退出特权，这将导致所有代理自动选择再加入此队列 （所有代理的默认设置）。</span><span class="sxs-lookup"><span data-stu-id="3ec35-232">You can revoke the agent opt-out privilege at any time by clearing the check box, causing agents to become automatically opted in for this queue again (the default setting for all agents).</span></span>

<span data-ttu-id="3ec35-233">若要访问选择退出选项，代理可以：</span><span class="sxs-lookup"><span data-stu-id="3ec35-233">To access the opt-out option, agents can:</span></span>

 1. <span data-ttu-id="3ec35-234">在其桌面 Skype for Business 客户端中打开**选项**。</span><span class="sxs-lookup"><span data-stu-id="3ec35-234">Open **Options** in their desktop Skype for Business client.</span></span>
 2. <span data-ttu-id="3ec35-235">在**呼叫转移**选项卡中，单击**在线编辑设置**链接。</span><span class="sxs-lookup"><span data-stu-id="3ec35-235">On the **Call Forwarding** tab, click the **Edit settings online** link.</span></span>
 3. <span data-ttu-id="3ec35-236">在 "用户设置" 页面上，单击 "**呼叫队列**"，然后清除复选框以选择退出队列。</span><span class="sxs-lookup"><span data-stu-id="3ec35-236">On the user settings page, click **Call Queues**, and then clear the check boxes to opt-out of queues.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3ec35-237">使用 Skype for Business 桌面之外的应用或终结点的代理可以从 "用户设置" 门户[https://aka.ms/cqsettings](https://aka.ms/cqsettings)访问 "退出" 选项。</span><span class="sxs-lookup"><span data-stu-id="3ec35-237">Agents using apps or endpoints other than Skype for Business Desktop can access the opt-out option from the user settings portal [https://aka.ms/cqsettings](https://aka.ms/cqsettings).</span></span>
    >
    > <span data-ttu-id="3ec35-238">如果代理位于 Microsoft 团队桌面客户端，则他们可以使用呼叫设置选择退出。</span><span class="sxs-lookup"><span data-stu-id="3ec35-238">If the agents are in Microsoft Teams desktop clients, then they can opt-out by using the Call Settings.</span></span> 

<span data-ttu-id="3ec35-239">![数字2的图标在上一个屏幕截图](media/teamscallout2.png)
中引用标注**Agent 警报设置**</span><span class="sxs-lookup"><span data-stu-id="3ec35-239">![Icon of the number 2, references a callout in the previous screenshot](media/teamscallout2.png)
**Agent Alert setting**</span></span>

<span data-ttu-id="3ec35-240">这定义了在串行或循环路由方法移到下一个代理之前通知呼叫的代理的持续时间。</span><span class="sxs-lookup"><span data-stu-id="3ec35-240">This defines the duration of an agent being notified of a call before the Serial or Round Robin routing methods move to the next agent.</span></span>

<span data-ttu-id="3ec35-241">默认设置为30秒，但最多可设置3分钟。</span><span class="sxs-lookup"><span data-stu-id="3ec35-241">The default setting is 30 seconds, but it can be set for up to 3 minutes.</span></span>

* * *

### <a name="set-the-call-overflow-and-timeout-handling-options"></a><span data-ttu-id="3ec35-242">设置呼叫溢出和超时处理选项</span><span class="sxs-lookup"><span data-stu-id="3ec35-242">Set the call overflow and timeout handling options</span></span>

![带有编号标注的溢出处理选项的屏幕截图](media/3f018734-16fe-458b-827d-71fc25155cde.png)

* * *

<span data-ttu-id="3ec35-244">![数字1的图标引用上一个屏幕截图](media/teamscallout1.png)
中的标注**最大通话在队列中**使用此设置可设置可同时在队列中等待的最大通话次数。</span><span class="sxs-lookup"><span data-stu-id="3ec35-244">![Icon of the number 1, references a callout in the previous screenshot](media/teamscallout1.png)
**Maximum calls in the queue** Use this to set the maximum calls that can wait in the queue at the same time.</span></span> <span data-ttu-id="3ec35-245">默认值为50，但范围可以从0到200。</span><span class="sxs-lookup"><span data-stu-id="3ec35-245">The default is 50, but it can range from 0 to 200.</span></span> <span data-ttu-id="3ec35-246">当达到此限制时，将按照在 "**达到最大通话次数时**" 设置中设置的方式处理呼叫。</span><span class="sxs-lookup"><span data-stu-id="3ec35-246">When this limit is reached, the call is handled in the way you set on the **When the maximum number of calls is reached** setting below.</span></span>

* * *

<span data-ttu-id="3ec35-247">![数字2的图标当呼叫队列达到其最大大小（](media/teamscallout2.png)
使用**队列设置中的最大通话**设置）时，**当达到最大调用数**时，将在上面的屏幕截图中引用标注，您可以选择新的传入呼叫所发生的操作。</span><span class="sxs-lookup"><span data-stu-id="3ec35-247">![Icon of the number 2, references a callout in the previous screenshot](media/teamscallout2.png)
**When the maximum number of calls is reached** When the call queue reaches its maximum size (set using the **Maximum calls in the queue** setting), you can choose what happens to new incoming calls.</span></span>

- <span data-ttu-id="3ec35-248">**断开连接**通话断开。</span><span class="sxs-lookup"><span data-stu-id="3ec35-248">**Disconnect** The call is disconnected.</span></span>
- <span data-ttu-id="3ec35-249">**重定向到**选择此项时，请选择下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="3ec35-249">**Redirect to** When you choose this, select one of the following:</span></span>

  - <span data-ttu-id="3ec35-250">**公司中的人员**具有**电话系统**许可证并启用企业语音或具有呼叫计划的在线用户。</span><span class="sxs-lookup"><span data-stu-id="3ec35-250">**Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have a Calling Plan.</span></span> <span data-ttu-id="3ec35-251">您可以对其进行设置，以便呼叫者可以发送到语音邮件。</span><span class="sxs-lookup"><span data-stu-id="3ec35-251">You can set it up so the caller can be sent to voicemail.</span></span> <span data-ttu-id="3ec35-252">若要执行此操作，请选择**您的公司中的人员**，并将其呼叫直接转发到语音邮件。</span><span class="sxs-lookup"><span data-stu-id="3ec35-252">To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span>

  <span data-ttu-id="3ec35-253">若要了解语音邮件所需的许可证，请参阅[设置云语音邮件](set-up-phone-system-voicemail.md)。</span><span class="sxs-lookup"><span data-stu-id="3ec35-253">To learn about licenses required for voicemail, see [Set up Cloud Voicemail](set-up-phone-system-voicemail.md).</span></span>

  - <span data-ttu-id="3ec35-254">**语音应用程序**选择与已创建的呼叫队列或自动助理相关联的资源帐户的名称。</span><span class="sxs-lookup"><span data-stu-id="3ec35-254">**Voice application** Select the name of a resource account associated to either a call queue or auto attendant that has already been created.</span></span>

* * *

<span data-ttu-id="3ec35-255">![数字3的图标引用上一个屏幕截图](media/teamscallout3.png)
调用超时中的标注 **：最长等待时间**您还可以确定在队列超时和需要重定向或断开连接的情况下，呼叫可以在队列中保留多长时间。</span><span class="sxs-lookup"><span data-stu-id="3ec35-255">![Icon of the number 3, references a callout in the previous screenshot](media/teamscallout3.png)
**Call Timeout: maximum wait time** You can also decide how much time a call can be on hold in the queue before it times out and needs to be redirected or disconnected.</span></span> <span data-ttu-id="3ec35-256">重定向的位置取决于设置**通话超时**设置的方式。</span><span class="sxs-lookup"><span data-stu-id="3ec35-256">Where it is redirected is based on how you set the **When a call times out** setting.</span></span> <span data-ttu-id="3ec35-257">你可以将此时间设置为 0 到 45 分钟。</span><span class="sxs-lookup"><span data-stu-id="3ec35-257">You can set a time from 0 to 45 minutes.</span></span>

<span data-ttu-id="3ec35-258">超时值可以以秒为单位按 15 秒间隔进行设置。</span><span class="sxs-lookup"><span data-stu-id="3ec35-258">The timeout value can be set in seconds, at 15-second intervals.</span></span> <span data-ttu-id="3ec35-259">这样，你可以以更细的粒度操作呼叫流。</span><span class="sxs-lookup"><span data-stu-id="3ec35-259">This allows you to manipulate the call flow with finer granularity.</span></span> <span data-ttu-id="3ec35-260">例如，您可以指定30秒内代理未接听的任何通话转到目录搜索自动助理。</span><span class="sxs-lookup"><span data-stu-id="3ec35-260">For example, you could specify that any calls that are not answered by an agent within 30 seconds go to a Directory Search auto attendant.</span></span>

<span data-ttu-id="3ec35-261">![数字4的图标](media/teamscallout4.png)
**当**调用达到您在呼叫**可以在队列设置中等待的时间**时，当调用达到所设置的限制时，将在上一个屏幕截图中引用标注，您可以选择对呼叫执行的操作：</span><span class="sxs-lookup"><span data-stu-id="3ec35-261">![Icon of the number 4, references a callout in the previous screenshot](media/teamscallout4.png)
**When call times out** When the call reaches the limit you set on the **How long a call can wait in the queue** setting, you can choose what happens to the call:</span></span>

- <span data-ttu-id="3ec35-262">**断开连接**通话断开。</span><span class="sxs-lookup"><span data-stu-id="3ec35-262">**Disconnect** The call is disconnected.</span></span>
- <span data-ttu-id="3ec35-263">**将此呼叫重定向到**如果选择此选项，则可以使用以下选项：</span><span class="sxs-lookup"><span data-stu-id="3ec35-263">**Redirect this call to** When you choose this, you have these options:</span></span>
  - <span data-ttu-id="3ec35-264">**公司中的人员**具有**电话系统**许可证并启用企业语音或具有通话计划的在线用户。</span><span class="sxs-lookup"><span data-stu-id="3ec35-264">**Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have Calling Plans.</span></span> <span data-ttu-id="3ec35-265">若要对其进行设置，以便可以将拨入的人发送到语音邮件，请选择**您公司中的人员**，并将其设置为将呼叫直接转发到语音邮件。</span><span class="sxs-lookup"><span data-stu-id="3ec35-265">To set it up so the person calling in can be sent to voicemail, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span>

  <span data-ttu-id="3ec35-266">若要了解语音邮件所需的许可证，请参阅[设置云语音邮件](set-up-phone-system-voicemail.md)。</span><span class="sxs-lookup"><span data-stu-id="3ec35-266">To learn about licenses required for voicemail, see [Set up Cloud Voicemail](set-up-phone-system-voicemail.md).</span></span>

  - <span data-ttu-id="3ec35-267">**语音应用**选择与已创建的通话队列或自动助理相关联的资源帐户的名称。</span><span class="sxs-lookup"><span data-stu-id="3ec35-267">**Voice app** Select the name of a resource account associated with either a call queue or auto attendant that you already created.</span></span>

## <a name="change-caller-id-for-outbound-calls"></a><span data-ttu-id="3ec35-268">更改出站呼叫的来电显示</span><span class="sxs-lookup"><span data-stu-id="3ec35-268">Change Caller ID for outbound calls</span></span>

<span data-ttu-id="3ec35-269">若要保护呼叫代理的身份，请使用**CsCallingLineIdentity** cmdlet 将呼叫者 ID 更改为拨出电话、自动助理或任何服务号码，如下例所示：</span><span class="sxs-lookup"><span data-stu-id="3ec35-269">To protect a call agent's identity, change their caller ID for outbound calls to a call queue, auto attendant, or any service number with the **New-CsCallingLineIdentity** cmdlet as in the following example:</span></span>

``` Powershell
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

<span data-ttu-id="3ec35-270">然后使用**CallingLineIdentity** cmdlet 将该策略应用于用户，如下例所示：</span><span class="sxs-lookup"><span data-stu-id="3ec35-270">Then apply the policy to the user with the **Grant-CallingLineIdentity** cmdlet as in the following example:</span></span> 

``` Powershell
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

<span data-ttu-id="3ec35-271">有关详细信息，请参阅[如何在组织中使用呼叫者 ID](/microsoftteams/how-can-caller-id-be-used-in-your-organization)。</span><span class="sxs-lookup"><span data-stu-id="3ec35-271">For more information, see [How can caller ID be used in your organization](/microsoftteams/how-can-caller-id-be-used-in-your-organization).</span></span>

## <a name="call-queue-cmdlets"></a><span data-ttu-id="3ec35-272">呼叫队列 cmdlet</span><span class="sxs-lookup"><span data-stu-id="3ec35-272">Call queue cmdlets</span></span>

<span data-ttu-id="3ec35-273">还可以使用 Windows PowerShell 来创建和设置呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="3ec35-273">You can also use Windows PowerShell to create and set up call queues.</span></span> <span data-ttu-id="3ec35-274">下面是用于管理呼叫队列的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="3ec35-274">Here are the cmdlets that you use to manage a call queue.</span></span>

- [<span data-ttu-id="3ec35-275">新-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="3ec35-275">New-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="3ec35-276">Set-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="3ec35-276">Set-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/set-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="3ec35-277">CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="3ec35-277">Get-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/get-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="3ec35-278">Remove-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="3ec35-278">Remove-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-CsCallQueue?view=skype-ps)

### <a name="more-about-windows-powershell"></a><span data-ttu-id="3ec35-279">有关 Windows PowerShell 的详细信息</span><span class="sxs-lookup"><span data-stu-id="3ec35-279">More about Windows PowerShell</span></span>

- <span data-ttu-id="3ec35-280">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。</span><span class="sxs-lookup"><span data-stu-id="3ec35-280">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="3ec35-281">使用 Windows PowerShell，你可以通过单个管理点管理 Office 365 和 Microsoft 团队。</span><span class="sxs-lookup"><span data-stu-id="3ec35-281">With Windows PowerShell, you can manage Office 365 and Microsoft Teams with a single point of administration.</span></span> <span data-ttu-id="3ec35-282">当有多个任务需要执行时，它可以简化日常工作。</span><span class="sxs-lookup"><span data-stu-id="3ec35-282">It can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="3ec35-283">若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="3ec35-283">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="3ec35-284">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="3ec35-284">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [<span data-ttu-id="3ec35-285">为什么要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="3ec35-285">Why you need to use Office 365 PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- <span data-ttu-id="3ec35-286">当您同时为多个用户进行更改时，Windows PowerShell 在速度、简洁性和工作效率方面具有许多优势。</span><span class="sxs-lookup"><span data-stu-id="3ec35-286">Windows PowerShell has many advantages in speed, simplicity, and productivity over the Microsoft Teams admin center when you make changes for many users at once.</span></span> <span data-ttu-id="3ec35-287">通过以下主题了解这些优势：</span><span class="sxs-lookup"><span data-stu-id="3ec35-287">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="3ec35-288">通过 Windows PowerShell 管理 Office 365</span><span class="sxs-lookup"><span data-stu-id="3ec35-288">Manage Office 365 with Windows PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [<span data-ttu-id="3ec35-289">为 Windows PowerShell 设置计算机</span><span class="sxs-lookup"><span data-stu-id="3ec35-289">Set up your computer for Windows PowerShell</span></span>](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a><span data-ttu-id="3ec35-290">相关主题</span><span class="sxs-lookup"><span data-stu-id="3ec35-290">Related topics</span></span>

[<span data-ttu-id="3ec35-291">以下是 Office 365 中的电话系统功能</span><span class="sxs-lookup"><span data-stu-id="3ec35-291">Here's what you get with Phone System in Office 365</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="3ec35-292">获取服务电话号码</span><span class="sxs-lookup"><span data-stu-id="3ec35-292">Getting service phone numbers</span></span>](getting-service-phone-numbers.md)

[<span data-ttu-id="3ec35-293">音频会议和通话套餐的国家/地区可用性</span><span class="sxs-lookup"><span data-stu-id="3ec35-293">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="3ec35-294">新-CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="3ec35-294">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
