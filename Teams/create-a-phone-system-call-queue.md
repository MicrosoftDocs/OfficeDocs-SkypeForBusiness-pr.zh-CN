---
title: 创建呼叫队列
ms.author: mikeplum
author: MikePlumleyMSFT
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
- seo-marvel-apr2020
description: 了解如何设置 Microsoft 团队的 "云呼叫" 队列的电话系统，这些团队提供问候语、举行音乐、呼叫重定向和其他功能。
ms.openlocfilehash: be43c2dc378b985b63c47b9322b336eeadfeecb6
ms.sourcegitcommit: 515f6cf7c16c0ab6ea7acbbd59084ac89b57dfb8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2020
ms.locfileid: "47295277"
---
# <a name="create-a-cloud-call-queue"></a><span data-ttu-id="5ed7e-103">创建云呼叫队列</span><span class="sxs-lookup"><span data-stu-id="5ed7e-103">Create a Cloud call queue</span></span>

<span data-ttu-id="5ed7e-104">云呼叫队列可以提供：</span><span class="sxs-lookup"><span data-stu-id="5ed7e-104">Cloud call queues can provide:</span></span>

- <span data-ttu-id="5ed7e-105">一条问候语。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-105">A greeting message.</span></span>

- <span data-ttu-id="5ed7e-106">在呼叫者保持等待时播放的音乐。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-106">Music while people are waiting on hold.</span></span>

- <span data-ttu-id="5ed7e-107">使用启用邮件的通讯组列表和安全组将呼叫重定向到呼叫代理。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-107">Redirecting calls to call agents in mail-enabled distribution lists and security groups.</span></span>

- <span data-ttu-id="5ed7e-108">设置不同的参数，例如队列最大大小、超时和通话处理选项。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-108">Setting different parameters such as queue maximum size, timeout, and call handling options.</span></span>

- <span data-ttu-id="5ed7e-109">面向呼叫者的共享语音邮件为组织留下消息。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-109">Shared voicemail for callers to leave a message for an organization.</span></span>

<span data-ttu-id="5ed7e-110">您不会直接将电话号码与呼叫队列相关联，而是将电话号码与 [资源帐户](manage-resource-accounts.md)相关联。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-110">You don't directly associate a phone number to a call queue, instead the phone number is associated to a [resource account](manage-resource-accounts.md).</span></span> <span data-ttu-id="5ed7e-111">可通过自动助理上的选择直接拨打或访问呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-111">A call queue can be dialed directly or accessed by a selection on an auto attendant.</span></span>

<span data-ttu-id="5ed7e-112">呼叫者在处于暂停状态时，会听到音乐，呼叫将首先连接到 *第一* (FIFO) 订单中的呼叫代理。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-112">The caller hears music while they are on hold, and the call connects to the call agents in *First In, First Out* (FIFO) order.</span></span>

<span data-ttu-id="5ed7e-113">通过以下方法之一将队列中的所有调用发送到代理：</span><span class="sxs-lookup"><span data-stu-id="5ed7e-113">All calls in the queue are sent to agents by one of the following methods:</span></span>

- <span data-ttu-id="5ed7e-114">通过助理路由，队列中的第一个通话将同时响铃所有代理。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-114">With attendant routing, the first call in the queue rings all agents at the same time.</span></span>

- <span data-ttu-id="5ed7e-115">通过串行路由，队列中的第一次呼叫将每个呼叫代理逐一响铃一次。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-115">With serial routing, the first call in the queue rings all call agents one by one.</span></span>

- <span data-ttu-id="5ed7e-116">使用最长空闲路由时，闲置时间最长的呼叫代理会收到下一个可用呼叫。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-116">With longest idle routing, the call agent whose has been idle the longest time receives the next available call.</span></span> <span data-ttu-id="5ed7e-117">在呼叫时，如果) 的时间不到10分钟，则将空闲时间定义为呼叫代理的状态设置为 " **可用** " 或 " **离开** (" 的时间长度。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-117">The idle time is defined as the length of time a call agent's presence state is set to **Available** or **Away** (if less than 10 minutes), at the time of the call.</span></span> <span data-ttu-id="5ed7e-118">如果呼叫代理的状态已 **离开** 超过10分钟，则空闲计时器将重置。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-118">If a call agent's presence is **Away** for more than 10 minutes, the idle timer resets.</span></span>

- <span data-ttu-id="5ed7e-119">通过循环复用，传入呼叫的路由是平衡的，以便每个呼叫代理从队列中获得相同数量的通话。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-119">With round robin, routing of incoming calls is balanced so that each call agent gets the same number of calls from the queue.</span></span>

<span data-ttu-id="5ed7e-120">你可以设置呼叫处理选项，如代理选择加入/选择退出、基于状态的路由、呼叫等待时间以及用上述任何方法调用超时选项。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-120">You can set call handling options, such as agent opt-in/opt-out, presence-based routing, call wait time, and call time-out options with any of the above methods.</span></span>

<span data-ttu-id="5ed7e-121">一次仅有一个传入呼叫通知 (在队列的 head) 呼叫代理。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-121">Only one incoming call notification (for the call at the head of the queue) at a time goes to the call agents.</span></span> <span data-ttu-id="5ed7e-122">呼叫代理接受呼叫后，队列中的下一个传入呼叫开始拨叫所有代理。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-122">After a call agent accepts the call, the next incoming call in the queue will start ringing call agents.</span></span>

> [!NOTE]
> <span data-ttu-id="5ed7e-123">本文适用于 Microsoft 团队和 Skype for business Online。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-123">This article applies to both Microsoft Teams and Skype for Business Online.</span></span>

## <a name="step-1--get-started"></a><span data-ttu-id="5ed7e-124">步骤 1-入门</span><span class="sxs-lookup"><span data-stu-id="5ed7e-124">Step 1 — Get started</span></span>

<span data-ttu-id="5ed7e-125">要开始使用呼叫队列，记住以下几点至关重要：</span><span class="sxs-lookup"><span data-stu-id="5ed7e-125">To get started using call queues, it's important to remember a few things:</span></span>

- <span data-ttu-id="5ed7e-126">通话队列必须具有关联的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-126">A call queue is required to have an associated resource account.</span></span> <span data-ttu-id="5ed7e-127">有关资源帐户的详细信息，请参阅 [管理团队中的资源帐户](manage-resource-accounts.md) 。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-127">See [Manage resource accounts in Teams](manage-resource-accounts.md) for details on resource accounts.</span></span>

- <span data-ttu-id="5ed7e-128">将电话号码分配给资源帐户时，您现在可以使用 "免费电话系统 [虚拟用户" 许可证](teams-add-on-licensing/virtual-user.md)。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-128">When you assign a phone number to a resource account, you can now use the cost-free Phone System [Virtual User license](teams-add-on-licensing/virtual-user.md).</span></span> <span data-ttu-id="5ed7e-129">电话系统允许组织级别的电话号码与低成本的自动助理和呼叫队列服务配合使用。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-129">Phone System allows phone numbers at the organizational level for use with low-cost auto attendant and call queue services.</span></span>

  > [!NOTE]
  > <span data-ttu-id="5ed7e-130">只有 Microsoft 团队用户和代理才支持直接路由呼叫队列服务号码。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-130">Direct Routing service numbers for call queues are supported for Microsoft Teams users and agents only.</span></span>

  > [!NOTE]
  > <span data-ttu-id="5ed7e-131">若要将呼叫重定向到您的组织中联机的人员，他们必须具有 **电话系统** 许可证并启用企业语音或安装 Microsoft 365 或 Office 365 通话计划。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-131">To redirect calls to people in your organization who are online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Microsoft 365 or Office 365 Calling Plans.</span></span> <span data-ttu-id="5ed7e-132">请参阅 [分配 Microsoft 团队附加设备许可证](teams-add-on-licensing/assign-teams-add-on-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-132">See [Assign Microsoft Teams add-on licenses](teams-add-on-licensing/assign-teams-add-on-licenses.md).</span></span> <span data-ttu-id="5ed7e-133">To enable them for Enterprise Voice, you can use Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5ed7e-133">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="5ed7e-134">例如，运行： "Move-csuser-identity" Amos 大理石 "-EnterpriseVoiceEnabled $true。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-134">For example, run: \`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true.</span></span>

- <span data-ttu-id="5ed7e-135">若要了解有关通话计划的详细信息，请参阅 [手机系统和通话计划](calling-plan-landing-page.md) 以及 [Microsoft 365 或 Office 365 的呼叫计划](calling-plans-for-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-135">To learn more about Calling Plans, see [Phone System and Calling Plans](calling-plan-landing-page.md) and [Calling Plans for Microsoft 365 or Office 365](calling-plans-for-office-365.md).</span></span>

- <span data-ttu-id="5ed7e-136">您只能将云呼叫队列分配给您在 **Microsoft 团队管理中心** 或从另一个服务提供商转移的收费电话号码和免费服务电话号码。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-136">You can only assign Cloud call queues toll and toll-free service phone numbers that you got in the **Microsoft Teams admin center** or transferred from another service provider.</span></span> <span data-ttu-id="5ed7e-137">免费服务号码需要通讯信用点数。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-137">Communications Credits are required for toll-free service numbers.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5ed7e-138">[!注释] 不能将用户（订阅者）的电话号码分配给呼叫队列 - 只能使用收费或免费服务电话号码。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-138">User (subscriber) phone numbers can't be assigned to call queues - only service toll or toll-free phone numbers can be used.</span></span>

- <span data-ttu-id="5ed7e-139">以下客户端支持与云呼叫队列关联的呼叫代理：</span><span class="sxs-lookup"><span data-stu-id="5ed7e-139">The following clients are supported for call agents associated to a Cloud call queue:</span></span>

  - <span data-ttu-id="5ed7e-140">Skype for Business 桌面客户端 2016 (32 位和64位版本) </span><span class="sxs-lookup"><span data-stu-id="5ed7e-140">Skype for Business desktop client 2016 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="5ed7e-141">Lync 桌面客户端 2013 (32 位和64位版本) </span><span class="sxs-lookup"><span data-stu-id="5ed7e-141">Lync desktop client 2013 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="5ed7e-142">Microsoft 团队支持的所有 IP 电话模式。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-142">All IP phone models supported for Microsoft Teams.</span></span> <span data-ttu-id="5ed7e-143">请参阅[获取适用于 Skype for Business Online 的电话](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online)。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-143">See [Getting phones for Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span></span>
  - <span data-ttu-id="5ed7e-144">Mac Skype for Business 客户端（版本 16.8.196 及更高版本）</span><span class="sxs-lookup"><span data-stu-id="5ed7e-144">Mac Skype for Business Client (version 16.8.196 and later)</span></span>
  - <span data-ttu-id="5ed7e-145">Android Skype for Business 客户端（版本 6.16.0.9 及更高版本）</span><span class="sxs-lookup"><span data-stu-id="5ed7e-145">Android Skype for Business Client (version 6.16.0.9 and later)</span></span>
  - <span data-ttu-id="5ed7e-146">iPhone Skype for Business 客户端（版本 6.16.0 及更高版本）</span><span class="sxs-lookup"><span data-stu-id="5ed7e-146">iPhone Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="5ed7e-147">iPad Skype for Business 客户端（版本 6.16.0 及更高版本）</span><span class="sxs-lookup"><span data-stu-id="5ed7e-147">iPad Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="5ed7e-148">Microsoft 团队 Windows 客户端 (32 位和64位版本) </span><span class="sxs-lookup"><span data-stu-id="5ed7e-148">Microsoft Teams Windows client (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="5ed7e-149">Microsoft Teams Mac 客户端</span><span class="sxs-lookup"><span data-stu-id="5ed7e-149">Microsoft Teams Mac client</span></span>
  - <span data-ttu-id="5ed7e-150">Microsoft Teams iPhone 应用</span><span class="sxs-lookup"><span data-stu-id="5ed7e-150">Microsoft Teams iPhone app</span></span>
  - <span data-ttu-id="5ed7e-151">Microsoft Teams Android 应用</span><span class="sxs-lookup"><span data-stu-id="5ed7e-151">Microsoft Teams Android app</span></span>

    > [!NOTE]
    > <span data-ttu-id="5ed7e-152">分配了直接路由号码的呼叫队列不支持 Skype for business 客户端、Lync 客户端或 Skype for business IP 手机用作代理。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-152">Call queues that are assigned a direct routing number don't support Skype for Business clients, Lync clients, or Skype for Business IP Phones as agents.</span></span>

## <a name="step-2--get-or-transfer-toll-or-toll-free-service-phone-numbers"></a><span data-ttu-id="5ed7e-153">步骤 2-获取或转移收费或免费服务电话号码</span><span class="sxs-lookup"><span data-stu-id="5ed7e-153">Step 2 — Get or transfer toll or toll-free service phone numbers</span></span>

<span data-ttu-id="5ed7e-154">在创建和设置呼叫队列之前，您需要获取或转移现有收费或免费服务号码。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-154">Before you can create and set up your call queues, you need to get or transfer your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="5ed7e-155">若要获取你的服务号码，请参阅 [获取服务电话号码](getting-service-phone-numbers.md) 或要转移现有服务号码，请参阅 [将电话号码转移到团队](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-155">To get your service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md) or if you want to transfer an existing service number, see [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span> <span data-ttu-id="5ed7e-156">获得收费或免费服务电话号码后，他们将显示在**Microsoft 团队管理中心**的  >  **语音**  >  **电话号码**中。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-156">After you get the toll or toll-free service phone numbers, they will show up in **Microsoft Teams admin center** > **Voice** > **Phone numbers**.</span></span> <span data-ttu-id="5ed7e-157">免费电话将列出一 **种数字类型** 的 **服务-免费电话**号码。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-157">Toll free numbers will be listed with a **Number type** of **Service — Toll-Free**.</span></span>

> [!NOTE]
> <span data-ttu-id="5ed7e-158">如果您在美国以外，则不能使用 Microsoft 团队管理中心获取服务号码。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-158">If you are outside the United States, you can't use the Microsoft Teams admin center to get service numbers.</span></span> <span data-ttu-id="5ed7e-159">转到 " [管理你的组织的电话号码](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) " 以了解如何从美国以外的国家进行管理。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-159">Go to [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) instead to see how to do it from the outside of the United States.</span></span>

<span data-ttu-id="5ed7e-160">设置多个自动助理时，通常会将电话号码分配给主自动助理的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-160">When you set up multiple auto attendants, you would usually assign a phone number to the main auto attendant's resource account.</span></span> <span data-ttu-id="5ed7e-161">与嵌套的自动助理或呼叫队列相关联的资源帐户通常不需要电话号码。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-161">Resource accounts associated to nested auto attendants or call queues often don't need phone numbers.</span></span> <span data-ttu-id="5ed7e-162">该自动助理可以将呼叫者定向到呼叫队列或嵌套的自动助理，即使他们没有电话号码也是如此。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-162">That auto attendant can direct callers to your call queues or nested auto attendants even if they don't have a phone number.</span></span> <span data-ttu-id="5ed7e-163">在这些情况下，你可以在系统中创建所有自动助理和呼叫队列，而无需分配拨号键盘选项，然后在稍后编辑设置。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-163">In those situations, you can create all auto attendants and call queues in your system without assigning dialpad options, and then edit the settings later.</span></span> <span data-ttu-id="5ed7e-164">必须存在呼叫队列或自动助理才能将其设置为菜单选项。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-164">A call queue or auto attendant must exist to set it as a menu option.</span></span>

## <a name="step-3--create-a-call-queue"></a><span data-ttu-id="5ed7e-165">步骤3—创建呼叫队列</span><span class="sxs-lookup"><span data-stu-id="5ed7e-165">Step 3 — Create a call queue</span></span>

[!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

> [!IMPORTANT]
> <span data-ttu-id="5ed7e-166">每个通话队列都必须具有关联的 [资源帐户](manage-resource-accounts.md)。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-166">Every call queue is required to have an associated [resource account](manage-resource-accounts.md).</span></span> <span data-ttu-id="5ed7e-167">必须先创建资源帐户，然后才能将其关联到呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-167">You must create the resource account first, then you can associate it to the call queue.</span></span>

### <a name="use-the-microsoft-teams-admin-center"></a><span data-ttu-id="5ed7e-168">使用 Microsoft 团队管理中心</span><span class="sxs-lookup"><span data-stu-id="5ed7e-168">Use the Microsoft Teams admin center</span></span>

<span data-ttu-id="5ed7e-169">在**Microsoft 团队管理中心**、**语音**  >  **呼叫队列**中，单击 " **+ 添加新**"：</span><span class="sxs-lookup"><span data-stu-id="5ed7e-169">In the **Microsoft Teams admin center**, **Voice** > **Call queues**, then click **+ Add new**:</span></span>

### <a name="set-the-display-name-and-resource-account"></a><span data-ttu-id="5ed7e-170">设置显示名称和资源帐户</span><span class="sxs-lookup"><span data-stu-id="5ed7e-170">Set the display name and resource account</span></span>

![带有编号标注的新通话队列的屏幕截图](media/37ecc300-a108-4294-8463-fce570dfce72.png)

* * *

<span data-ttu-id="5ed7e-172">![数字1的图标引用上一个屏幕截图名称中的标注 ](media/teamscallout1.png)
 **Name**输入呼叫队列的描述性显示名称。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-172">![Icon of the number 1, references a callout in the previous screenshot](media/teamscallout1.png)
**Name** Enter a descriptive display name for the call queue.</span></span> <span data-ttu-id="5ed7e-173">此名称是必需的，最多可包含64个字符，包括空格。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-173">This name is required and can contain up to 64 characters, including spaces.</span></span>

 <span data-ttu-id="5ed7e-174">此名称显示在传入呼叫的通知中。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-174">This name is displayed in the notification for the incoming call.</span></span>

* * *

<span data-ttu-id="5ed7e-175">![数字2的图标在前面的屏幕截图中引用标注 ](media/teamscallout2.png)
 **添加帐户**选择资源帐户。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-175">![Icon of the number 2, references a callout in the previous screenshot](media/teamscallout2.png)
**Add Accounts** Select a resource account.</span></span> <span data-ttu-id="5ed7e-176">所有通话队列都必须有一个资源帐户。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-176">All call queues are required to have a resource account.</span></span> <span data-ttu-id="5ed7e-177">资源帐户不需要拥有服务收费电话号码或免费电话号码。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-177">Resource accounts aren't required to have a service toll or toll-free phone number.</span></span>

<span data-ttu-id="5ed7e-178">如果没有列出任何服务号码，请在创建呼叫队列之前将其分配给资源帐户，如前文所述。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-178">If there aren't any listed,  get service numbers and assign them to a Resource account before you create the call queue, as described earlier.</span></span> <span data-ttu-id="5ed7e-179">若要获取你的服务号码，请参阅 [获取服务电话号码](getting-service-phone-numbers.md)。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-179">To get your service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md).</span></span> <span data-ttu-id="5ed7e-180">有关如何分配电话号码的详细信息，请参阅 [管理团队中的资源帐户](manage-resource-accounts.md) 。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-180">See [Manage resource accounts in Teams](manage-resource-accounts.md) for specifics on how to assign a phone number.</span></span>

> [!NOTE]
> <span data-ttu-id="5ed7e-181">如果你希望或需要分配 **域** ，你可以将其分配给呼叫队列的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-181">If you want or need to assign a **Domain** you would  assign it to the resource account for the call queue.</span></span>

### <a name="set-the-greeting-and-music-played-while-on-hold"></a><span data-ttu-id="5ed7e-182">设置通话保持时播放的问候语和音乐</span><span class="sxs-lookup"><span data-stu-id="5ed7e-182">Set the greeting and music played while on hold</span></span>

![带有编号标注的问候和音乐选项的屏幕截图](media/1d395a93-7cab-4178-9295-12d5379e20de.png)

* * *

<span data-ttu-id="5ed7e-184">![数字1的图标引用上一个屏幕截图中的标注 ](media/teamscallout1.png)
 **问候语**呼叫呼叫队列号码的用户可以播放的可选问候语。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-184">![Icon of the number 1, references a callout in the previous screenshot](media/teamscallout1.png)
**Greeting** the optional greeting played for people who call the call queue number.</span></span>

<span data-ttu-id="5ed7e-185">你可以) 中上载音频文件 ( .wav、mp3 或 .wma 格式。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-185">You can upload an audio file (.wav, .mp3, or .wma formats).</span></span>

<span data-ttu-id="5ed7e-186">![数字2的图标在上一个屏幕截图 ](media/teamscallout2.png)
 **音乐保留**中引用标注你可以使用随呼叫队列提供的默认音乐保持通话。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-186">![Icon of the number 2, references a callout in the previous screenshot](media/teamscallout2.png)
**Music on hold** You can use the default Music on Hold provided with the call queue.</span></span> <span data-ttu-id="5ed7e-187">你还可以将 .wav、mp3 或 .wma 格式中的音频文件上传到保留时使用的自定义音乐。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-187">You can also upload an audio file in .wav, mp3, or .wma formats to use as your custom Music on hold.</span></span>

* * *

### <a name="select-the-call-answering-options"></a><span data-ttu-id="5ed7e-188">选择呼叫应答选项</span><span class="sxs-lookup"><span data-stu-id="5ed7e-188">Select the call answering options</span></span>

![呼叫应答选项的屏幕截图](media/teams-cq-call-answering-options.png)

<span data-ttu-id="5ed7e-190">![数字1的图标引用上一个屏幕截图中的标注 ](media/teamscallout1.png)
 **调用代理和组**直接添加单个代理，而不将它们添加到组中，请单击 "**添加用户**"。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-190">![Icon of the number 1, references a callout in the previous screenshot](media/teamscallout1.png)
**Call agents and groups** To add individual agents directly, without adding them to a group, click **Add users**.</span></span> <span data-ttu-id="5ed7e-191">按希望接收呼叫的顺序放置单个代理。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-191">Put individual agents in the order in which you want them to receive the call.</span></span> <span data-ttu-id="5ed7e-192">您最多可以添加20个单独的代理 (添加超过20个，请将它们放入群组) 。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-192">You can add up to 20 individual agents (to add more than 20, put them in a group).</span></span>

<span data-ttu-id="5ed7e-193">调用首先路由到单个代理，然后路由到组中的代理。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-193">Calls are routed first to individual agents, then to the agents in groups.</span></span> 

<span data-ttu-id="5ed7e-194">你可以选择多达200个呼叫代理，该代理属于以下任意邮件列表或组：</span><span class="sxs-lookup"><span data-stu-id="5ed7e-194">You can select up to 200 call agents who belong to any of the following mailing lists or groups:</span></span>

- <span data-ttu-id="5ed7e-195">Microsoft 365 群组</span><span class="sxs-lookup"><span data-stu-id="5ed7e-195">Microsoft 365 group</span></span>
- <span data-ttu-id="5ed7e-196">安全组</span><span class="sxs-lookup"><span data-stu-id="5ed7e-196">Security group</span></span>
- <span data-ttu-id="5ed7e-197">通讯组列表</span><span class="sxs-lookup"><span data-stu-id="5ed7e-197">Distribution list</span></span>

<span data-ttu-id="5ed7e-198">所选呼叫代理必须是以下各项之一：</span><span class="sxs-lookup"><span data-stu-id="5ed7e-198">Call agents selected must be one of the following:</span></span> 

- <span data-ttu-id="5ed7e-199">使用电话系统许可证和启用企业语音的联机用户</span><span class="sxs-lookup"><span data-stu-id="5ed7e-199">Online users with a Phone System license and Enterprise Voice enabled</span></span>
- <span data-ttu-id="5ed7e-200">使用呼叫计划的在线用户</span><span class="sxs-lookup"><span data-stu-id="5ed7e-200">Online users with a Calling Plan</span></span>
- <span data-ttu-id="5ed7e-201">本地 Skype for Business 服务器用户</span><span class="sxs-lookup"><span data-stu-id="5ed7e-201">On-premises Skype for Business Server users</span></span>

  > [!NOTE]
  > <span data-ttu-id="5ed7e-202">如果您想要将呼叫重定向到您的组织中联机的人员，也可以使用此操作。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-202">This also applies if you want to redirect calls to people in your organization who are online.</span></span> <span data-ttu-id="5ed7e-203">这些人必须具有电话系统许可证，并且已启用企业语音 *或* 有呼叫计划。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-203">These individuals must have a Phone System license and Enterprise Voice enabled *or* have a Calling Plan.</span></span> <span data-ttu-id="5ed7e-204">有关详细信息，请参阅 [分配 Skype for business 许可证](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses)、 [分配 Microsoft 团队许可证](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/assign-teams-add-on-licenses)或适合 [您的通话计划？](https://docs.microsoft.com/microsoftteams/calling-plan-landing-page)</span><span class="sxs-lookup"><span data-stu-id="5ed7e-204">For more information, see [Assign Skype for Business licenses](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses), [Assign Microsoft Teams licenses](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/assign-teams-add-on-licenses), or [Which Calling Plan is right for you?](https://docs.microsoft.com/microsoftteams/calling-plan-landing-page)</span></span>

   <span data-ttu-id="5ed7e-205">若要启用企业语音代理，你可以使用 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-205">To enable an agent for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="5ed7e-206">例如，运行： `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="5ed7e-206">For example, run: `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

- <span data-ttu-id="5ed7e-207">具有电话系统许可证或呼叫计划的用户添加到 Microsoft 365 组、启用邮件的通讯组列表或安全组。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-207">Users with a Phone System license or a Calling Plan that are added to a Microsoft 365 Group, a mail-enabled distribution list, or a security group.</span></span> <span data-ttu-id="5ed7e-208">将通讯组列表或安全组中的代理添加为呼叫队列代理时，首次通话最多可能需要3个小时。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-208">When you add an agent in a distribution list or a security group as a call queue agent, it can take up to three hours for the first call to arrive.</span></span> <span data-ttu-id="5ed7e-209">新创建的通讯组列表或安全组可能需要长达48小时才能与通话队列一起使用。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-209">A newly created distribution list or security group might take up to 48 hours to become available to be used with call queues.</span></span> <span data-ttu-id="5ed7e-210">新创建的 Microsoft 365 组几乎立即可用。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-210">Newly created Microsoft 365 Groups are available almost immediately.</span></span>

- <span data-ttu-id="5ed7e-211">如果你的代理正在使用 Microsoft 团队应用进行呼叫队列呼叫，则他们必须处于 TeamsOnly 模式。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-211">If your agents are using the Microsoft Teams app for call queue calls, they need to be in TeamsOnly mode.</span></span>

<span data-ttu-id="5ed7e-212">![数字2的图标在上一个屏幕截图会议模式下引用标注 ](media/teamscallout2.png)
 **会议**模式将显著减少在代理接受呼叫后将呼叫者连接到代理所需的时间量。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-212">![Icon of the number 2, references a callout in the previous screenshot](media/teamscallout2.png)
**Conference mode** Conference mode significantly reduces the amount of time it takes for a caller to be connected to an agent, after the agent accepts the call.</span></span> <span data-ttu-id="5ed7e-213">如果您有多个通话队列，则可以在某些或所有通话队列中启用会议模式;在一个呼叫队列中启用或禁用会议模式不会影响任何其他呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-213">If you have more than one call queue, you can enable conference mode on some or all of your call queues; enabling or disabling conference mode on one call queue doesn't impact any other call queues.</span></span>

<span data-ttu-id="5ed7e-214">会议模式默认情况下处于禁用状态，但如果满足下列要求，则可以随时启用：</span><span class="sxs-lookup"><span data-stu-id="5ed7e-214">Conference mode is disabled by default but can be enabled at any time if the following requirements are met:</span></span>

- <span data-ttu-id="5ed7e-215">添加到呼叫队列的代理需要使用下列客户端之一：</span><span class="sxs-lookup"><span data-stu-id="5ed7e-215">Agents added to the call queue need to use one of the following clients:</span></span>

  - <span data-ttu-id="5ed7e-216">Microsoft 团队桌面客户端、Android 应用或 iOS 应用的最新版本</span><span class="sxs-lookup"><span data-stu-id="5ed7e-216">The latest version of the Microsoft Teams desktop client, Android app, or iOS app</span></span>
  - <span data-ttu-id="5ed7e-217">Microsoft 团队手机版本 1449/1.0.94.2020051601 或更高版本</span><span class="sxs-lookup"><span data-stu-id="5ed7e-217">Microsoft Teams phone version 1449/1.0.94.2020051601 or later</span></span>
  
- <span data-ttu-id="5ed7e-218">代理的团队帐户需要设置为 "仅限团队" 模式</span><span class="sxs-lookup"><span data-stu-id="5ed7e-218">Agents' Teams accounts need to be set to Teams-only mode</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5ed7e-219">如果上述代理要求未满足，并且在呼叫队列中启用了会议模式，则不满足这些要求的代理不会包含在 "呼叫" 传送列表中。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-219">If the agent requirements above aren't met and conference mode is enabled on a call queue, agents who don't meet the requirements aren't included in the call routing list.</span></span> <span data-ttu-id="5ed7e-220">不在呼叫传送列表中的代理将无法接收呼叫。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-220">Agents who aren't in the call routing list won't receive calls.</span></span> <span data-ttu-id="5ed7e-221">如果代理不满足上述代理要求，请不要在呼叫队列中启用会议模式。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-221">If you have agents who don't meet the agent requirements above, don't enable conference mode on the call queue.</span></span>

<span data-ttu-id="5ed7e-222">在呼叫队列中启用会议模式后，通过以下方法之一接收呼叫将获得更快的连接时间：</span><span class="sxs-lookup"><span data-stu-id="5ed7e-222">After conference mode is enabled on a call queue, calls will benefit from the faster connection time if they're received via one of the following methods:</span></span>

- <span data-ttu-id="5ed7e-223">来自其他 Microsoft 团队桌面客户端的 VoIP 呼叫</span><span class="sxs-lookup"><span data-stu-id="5ed7e-223">VoIP calls from another Microsoft Teams desktop client</span></span>
- <span data-ttu-id="5ed7e-224">通话计划 PSTN 呼叫</span><span class="sxs-lookup"><span data-stu-id="5ed7e-224">Calling Plan PSTN calls</span></span>
- <span data-ttu-id="5ed7e-225">直接路由 PSTN 呼叫</span><span class="sxs-lookup"><span data-stu-id="5ed7e-225">Direct Routing PSTN calls</span></span>

<span data-ttu-id="5ed7e-226">大多数通话都是通过以上列出的一种方法来接收的。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-226">The majority of calls are received via one of the methods listed above.</span></span> <span data-ttu-id="5ed7e-227">如果通过另一种 (方法（例如来自 Skype for Business 客户端) 的 VoIP 呼叫）接收呼叫，则该呼叫仍将添加到呼叫队列，但不会因更快的连接时间而受益。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-227">If a call is received via another method (such as a VoIP call from a Skype for Business client), the call will still be added to the call queue, however, it won't benefit from the faster connection time.</span></span>

> [!NOTE]
> <span data-ttu-id="5ed7e-228">会议模式不支持忙闲。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-228">Busy on Busy is not supported by conference mode.</span></span> <span data-ttu-id="5ed7e-229">如果未启用基于状态的路由，则非呼叫队列呼叫中的代理仍会显示呼叫队列呼叫。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-229">Agents on non-call queue calls may still be presented with a call queue call if presence-based routing is not enabled.</span></span>


<span data-ttu-id="5ed7e-230">![数字3的图标引用上一个屏幕截图 ](media/teamscallout3.png)
 **路由方法**中的标注，你可以选择 "**助理**"、"**串行**"、"**最长空闲**" 或 "**循环复用**" 作为分发方法。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-230">![Icon of the number 3, references a callout in the previous screenshot](media/teamscallout3.png)
**Routing method** You can choose either **Attendant**, **Serial**, **Longest idle**, or **Round Robin** as the distribution method.</span></span> <span data-ttu-id="5ed7e-231">默认情况下，所有新的和现有的通话队列均已选中 "助理路由"。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-231">All new and existing call queues have attendant routing selected by default.</span></span> <span data-ttu-id="5ed7e-232">使用 "助理路由" 时，队列中的第一次呼叫将同时响铃所有呼叫工程师。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-232">When attendant routing is used, the first call in the queue rings all call agents at the same time.</span></span> <span data-ttu-id="5ed7e-233">获取呼叫的第一个呼叫代理将获取呼叫。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-233">The first call agent to pick up the call gets the call.</span></span>

- <span data-ttu-id="5ed7e-234">**助理路由** 使队列中的第一次通话同时拨打所有呼叫工程师。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-234">**Attendant routing** causes the first call in the queue to ring all call agents at the same time.</span></span> <span data-ttu-id="5ed7e-235">获取呼叫的第一个呼叫代理将获取呼叫。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-235">The first call agent to pick up the call gets the call.</span></span>
- <span data-ttu-id="5ed7e-236">**串行路由** 传入呼叫将所有呼叫代理从呼叫代理程序列表的开始处拨打一次。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-236">**Serial routing** incoming calls ring all call agents one by one, from the beginning of the call agent list.</span></span> <span data-ttu-id="5ed7e-237">不能在 "呼叫代理程序" 列表中订购代理。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-237">Agents can't be ordered within the call agent list.</span></span> <span data-ttu-id="5ed7e-238">如果代理程序已关闭或未接听呼叫，则呼叫将拨打下一个代理，并且将尝试所有代理，直到它已被获取或超时。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-238">If an agent dismisses or does not pick up a call, the call will ring the next agent and will try all agents until it is picked up or times out.</span></span>
- <span data-ttu-id="5ed7e-239">**最长空闲** 传送最长时间空闲的呼叫代理的下一次可用通话。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-239">**Longest idle** routes the next available call to the call agent whose has been idle the longest time.</span></span> <span data-ttu-id="5ed7e-240">在呼叫时，如果) 的时间不到10分钟，则将空闲时间定义为呼叫代理的状态设置为 " **可用** " 或 " **离开** (" 的时间长度。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-240">The idle time is defined as the length of time a call agent's presence state is set to **Available** or **Away** (if less than 10 minutes), at the time of the call.</span></span> <span data-ttu-id="5ed7e-241">如果呼叫代理的状态设置为 " **离开** " 超过10分钟，则空闲计时器将重置。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-241">If a call agent's presence is set to **Away** for more than 10 minutes, the idle timer resets.</span></span> <span data-ttu-id="5ed7e-242">每分钟查询用户的状态。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-242">Presence states of users are queried every minute.</span></span>

    <span data-ttu-id="5ed7e-243">请务必了解，启用此设置会强制启用 **基于状态的路由** 。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-243">It's important to know that enabling this setting forces **Presence-based routing** to also be enabled.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="5ed7e-244">启用 Skype for Business 客户端的代理不会在启用最长空闲设置时收到呼叫。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-244">Agents who use the Skype for Business client won't receive calls when the longest idle setting is enabled.</span></span> <span data-ttu-id="5ed7e-245">如果您的代理使用的是 Skype 或商业版，请不要启用此设置。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-245">If you have agents who use Skype or Business, don't enable this setting.</span></span>
- <span data-ttu-id="5ed7e-246">**循环法** 平衡传入呼叫的路由，以便每个呼叫代理从队列中获得相同数量的通话。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-246">**Round robin** balances routing of incoming calls so that each call agent gets the same number of calls from the queue.</span></span> <span data-ttu-id="5ed7e-247">这在入站销售环境中可能需要确保所有呼叫代理的同等机遇。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-247">This may be desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

<span data-ttu-id="5ed7e-248">![数字4的图标在上一个屏幕截图基于状态的路由状态的基于状态的路由中引用标注 ](media/teamscallout4.png)
 **Presence-based routing**使用呼叫代理的可用性状态来确定是否应将代理包括在所选路由方法的 "呼叫路由" 列表中。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-248">![Icon of the number 4, references a callout in the previous screenshot](media/teamscallout4.png)
**Presence-based routing** Presence-based routing uses the availability status of call agents to determine whether an agent should be included in the call routing list for the selected routing method.</span></span> <span data-ttu-id="5ed7e-249">其可用性状态设置为 " **可用** " 的呼叫代理包括在 "呼叫" 传送列表中，并且可以接收呼叫。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-249">Call agents whose availability status is set to **Available** are included in the call routing list and can receive calls.</span></span> <span data-ttu-id="5ed7e-250">其可用性状态设置为任何其他状态的代理将从呼叫路由列表中排除，并且在其可用性状态更改为 " **可用**" 之前不会收到呼叫。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-250">Agents whose availability status is set to any other status are excluded from the call routing list and won't receive calls until their availability status changes back to **Available**.</span></span>  

<span data-ttu-id="5ed7e-251">你可以使用任何路由方法启用基于状态的呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-251">You can enable presence-based call routing with any of the routing methods.</span></span>

<span data-ttu-id="5ed7e-252">如果某个代理选择退出呼叫，则无论其可用性状态如何设置，它们都不会包含在 "呼叫" 传送列表中。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-252">If an agent opts out of getting calls, they won't be included in the call routing list regardless of what their availability status is set to.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="5ed7e-253">启用基于状态的路由时，"呼叫" 传送列表中不包含使用 Skype for Business 客户端的代理，无论其可用性状态如何。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-253">Agents who use the Skype for Business client aren't included in the call routing list when presence-based routing is enabled, regardless of their availability status.</span></span> <span data-ttu-id="5ed7e-254">不在呼叫传送列表中的代理将无法接收呼叫。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-254">Agents who aren't in the call routing list won't receive calls.</span></span> <span data-ttu-id="5ed7e-255">如果您有使用 Skype for Business 的工程师，请不要启用基于状态的呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-255">If you have agents who use Skype for Business, don't enable presence-based call routing.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5ed7e-256">对于高音量通话队列，推荐设置如下：</span><span class="sxs-lookup"><span data-stu-id="5ed7e-256">For high volume calls queues the recommended settings are:</span></span>
>
> <span data-ttu-id="5ed7e-257">会议模式：自动</span><span class="sxs-lookup"><span data-stu-id="5ed7e-257">Conference mode: Auto</span></span><br>
> <span data-ttu-id="5ed7e-258">路由方法：助理路由</span><span class="sxs-lookup"><span data-stu-id="5ed7e-258">Routing method: Attendant routing</span></span><br>
> <span data-ttu-id="5ed7e-259">基于状态的路由：打开</span><span class="sxs-lookup"><span data-stu-id="5ed7e-259">Presence-based routing: On</span></span><br>
> <span data-ttu-id="5ed7e-260">代理警报时间：20秒</span><span class="sxs-lookup"><span data-stu-id="5ed7e-260">Agent alert time: 20 seconds</span></span>


### <a name="select-an-agent-opt-out-option"></a><span data-ttu-id="5ed7e-261">选择代理选择退出选项</span><span class="sxs-lookup"><span data-stu-id="5ed7e-261">Select an agent opt-out option</span></span>

![代理选择退出选项（带有编号标注）的屏幕截图](media/99279eff-db61-4acf-9b62-64be84b6414b.png)

* * *

<span data-ttu-id="5ed7e-263">![数字1的图标，引用上一个屏幕截图代理中的标注 ](media/teamscallout1.png)
 **可以选择不获取呼叫**，您可以选择允许呼叫队列代理通过启用此选项来选择允许呼叫队列代理取消来自特定队列的呼叫。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-263">![Icon of the number 1, references a callout in the previous screenshot](media/teamscallout1.png)
**Agent can opt out of getting calls** You can choose to allow call queue agents to opt-out of taking calls from a particular queue by enabling this option.</span></span>

<span data-ttu-id="5ed7e-264">如果启用此选项，将允许此队列中的所有代理从该呼叫队列开始或停止接收呼叫。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-264">Enabling this option allows all agents in this queue to start or stop receiving calls from this call queue at will.</span></span> <span data-ttu-id="5ed7e-265">通过清除此复选框，你可以随时撤消代理选择退出特权，这将导致所有代理自动选择再加入此队列 （所有代理的默认设置）。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-265">You can revoke the agent opt-out privilege at any time by clearing the check box, causing agents to become automatically opted in for this queue again (the default setting for all agents).</span></span>

<span data-ttu-id="5ed7e-266">若要访问选择退出选项，代理可以：</span><span class="sxs-lookup"><span data-stu-id="5ed7e-266">To access the opt-out option, agents can:</span></span>

 1. <span data-ttu-id="5ed7e-267">在其桌面 Skype for Business 客户端中打开**选项**。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-267">Open **Options** in their desktop Skype for Business client.</span></span>
 2. <span data-ttu-id="5ed7e-268">在**呼叫转移**选项卡中，单击**在线编辑设置**链接。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-268">On the **Call Forwarding** tab, click the **Edit settings online** link.</span></span>
 3. <span data-ttu-id="5ed7e-269">在 "用户设置" 页面上，单击 " **呼叫队列**"，然后清除复选框以选择退出队列。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-269">On the user settings page, click **Call Queues**, and then clear the check boxes to opt-out of queues.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5ed7e-270">使用 Skype for Business 桌面之外的应用或终结点的代理可以从 "用户设置" 门户访问 "退出" 选项 [https://aka.ms/cqsettings](https://aka.ms/cqsettings) 。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-270">Agents using apps or endpoints other than Skype for Business Desktop can access the opt-out option from the user settings portal [https://aka.ms/cqsettings](https://aka.ms/cqsettings).</span></span>
    >
    > <span data-ttu-id="5ed7e-271">如果代理位于 Microsoft 团队桌面客户端，则他们可以使用呼叫设置选择退出。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-271">If the agents are in Microsoft Teams desktop clients, then they can opt-out by using the Call Settings.</span></span> 

<span data-ttu-id="5ed7e-272">![数字2的图标在上一个屏幕截图中引用标注 ](media/teamscallout2.png)
 **Agent 警报设置**</span><span class="sxs-lookup"><span data-stu-id="5ed7e-272">![Icon of the number 2, references a callout in the previous screenshot](media/teamscallout2.png)
**Agent Alert setting**</span></span>

<span data-ttu-id="5ed7e-273">这定义了在串行或循环路由方法移到下一个代理之前通知呼叫的代理的持续时间。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-273">This defines the duration of an agent being notified of a call before the Serial or Round Robin routing methods move to the next agent.</span></span>

<span data-ttu-id="5ed7e-274">默认设置为30秒，但最多可设置3分钟。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-274">The default setting is 30 seconds, but it can be set for up to 3 minutes.</span></span>

* * *

### <a name="set-the-call-overflow-and-timeout-handling-options"></a><span data-ttu-id="5ed7e-275">设置呼叫溢出和超时处理选项</span><span class="sxs-lookup"><span data-stu-id="5ed7e-275">Set the call overflow and timeout handling options</span></span>

![带有编号标注的溢出处理选项的屏幕截图](media/3f018734-16fe-458b-827d-71fc25155cde.png)

* * *

<span data-ttu-id="5ed7e-277">![数字1的图标引用上一个屏幕截图中的标注 ](media/teamscallout1.png)
 **最大通话在队列中**使用此设置可设置可同时在队列中等待的最大通话次数。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-277">![Icon of the number 1, references a callout in the previous screenshot](media/teamscallout1.png)
**Maximum calls in the queue** Use this to set the maximum calls that can wait in the queue at the same time.</span></span> <span data-ttu-id="5ed7e-278">默认值为50，但范围可以从0到200。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-278">The default is 50, but it can range from 0 to 200.</span></span> <span data-ttu-id="5ed7e-279">当达到此限制时，将按照在 " **达到最大通话次数时** " 设置中设置的方式处理呼叫。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-279">When this limit is reached, the call is handled in the way you set on the **When the maximum number of calls is reached** setting below.</span></span>

* * *

<span data-ttu-id="5ed7e-280">![当通话队列达到最大值时，数字2的图标引用上一个屏幕截图中的标注 ](media/teamscallout2.png)
 (使用**队列设置中的最大通话**设置) 中，您可以选择新的传入呼叫发生**的**情况。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-280">![Icon of the number 2, references a callout in the previous screenshot](media/teamscallout2.png)
**When the maximum number of calls is reached** When the call queue reaches its maximum size (set using the **Maximum calls in the queue** setting), you can choose what happens to new incoming calls.</span></span>

- <span data-ttu-id="5ed7e-281">**断开连接** 通话断开。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-281">**Disconnect** The call is disconnected.</span></span>

- <span data-ttu-id="5ed7e-282">**重定向到** 选择此项时，请选择下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="5ed7e-282">**Redirect to** When you choose this, select one of the following:</span></span>

  - <span data-ttu-id="5ed7e-283">**组织中的人员** 具有电话系统许可证且已启用企业语音或具有呼叫计划的在线用户。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-283">**Person in organization** An online user with a Phone System license and is enabled for Enterprise Voice or has a Calling Plan.</span></span>

  - <span data-ttu-id="5ed7e-284">**语音应用** 选择与已创建的呼叫队列或自动助理相关联的资源帐户的名称。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-284">**Voice app** Select the name of a resource account associated to either a call queue or auto attendant that has already been created.</span></span>

  - <span data-ttu-id="5ed7e-285">**外部电话号码** 选择此 "将呼叫转接到您指定的外部电话号码。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-285">**External phone number** Choose this to transfer the caller to an external phone number that you specify.</span></span> <span data-ttu-id="5ed7e-286">请注意以下事项：</span><span class="sxs-lookup"><span data-stu-id="5ed7e-286">Note the following:</span></span>

    - <span data-ttu-id="5ed7e-287">与使 PSTN 传出的应用程序关联的资源帐户必须具有电话号码，并且必须分配有一个虚拟电话系统许可证。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-287">The resource account associated with the application making the PSTN transfer out must have a phone number and be assigned a Virtual Phone System license.</span></span> <span data-ttu-id="5ed7e-288">不支持电话系统许可证。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-288">Phone System licenses aren't supported.</span></span> <span data-ttu-id="5ed7e-289">此外，资源帐户必须具有下列其中一项：</span><span class="sxs-lookup"><span data-stu-id="5ed7e-289">Additionally, the resource account must have one of the following:</span></span>
        - <span data-ttu-id="5ed7e-290">对于带有呼叫计划编号的资源帐户，请分配 [呼叫计划](calling-plans-for-office-365.md) 许可证。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-290">For a resource account with a Calling Plan number, assign a [Calling Plan](calling-plans-for-office-365.md) license.</span></span>
        - <span data-ttu-id="5ed7e-291">对于具有直接路由号码的资源帐户，请分配 [联机语音路由策略](manage-voice-routing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-291">For a resource account with a Direct Routing number, assign an [online voice routing policy](manage-voice-routing-policies.md).</span></span>
    - <span data-ttu-id="5ed7e-292">显示的出站电话号码按如下方式确定：</span><span class="sxs-lookup"><span data-stu-id="5ed7e-292">The outbound phone number that's displayed is determined as follows:</span></span>
        - <span data-ttu-id="5ed7e-293">对于呼叫计划号码，将显示原始呼叫者的电话号码。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-293">For Calling Plan numbers, the original caller's phone number is displayed.</span></span>
        - <span data-ttu-id="5ed7e-294">对于直接路由号码，发送的号码基于 P 宣称的身份 (PAI 在 SBC 上) 设置，如下所示：</span><span class="sxs-lookup"><span data-stu-id="5ed7e-294">For Direct Routing numbers, the number sent is based on the P-Asserted-Identity (PAI) setting on the SBC, as follows:</span></span>
            - <span data-ttu-id="5ed7e-295">如果设置为 "已禁用"，将显示原始呼叫者的电话号码。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-295">If set to Disabled, the original caller's phone number is displayed.</span></span> <span data-ttu-id="5ed7e-296">这是默认和推荐的设置。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-296">This is the default and recommended setting.</span></span>
            - <span data-ttu-id="5ed7e-297">如果设置为 "启用"，则显示资源帐户电话号码。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-297">If set to Enabled, the resource account phone number is displayed.</span></span>
    - <span data-ttu-id="5ed7e-298">不支持在通话计划中继和直接路由中继之间转移。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-298">Transfers between Calling Plan trunks and Direct Routing trunks aren't supported.</span></span>
    
  - <span data-ttu-id="5ed7e-299">**语音邮件** 选择包含组织中需要访问此呼叫队列接收的语音邮件的用户的 Microsoft 365 组，然后选择下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="5ed7e-299">**Voicemail** Select the Microsoft 365 group that contains the users in your organization that need to access voicemail received by this call queue, and then select one of the following:</span></span>
      - <span data-ttu-id="5ed7e-300">**播放音频文件** 如果选择此选项，请选择 " **上传文件** " 以上载录制的问候消息。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-300">**Play an audio file** If you choose this option, select **Upload file** to upload a recorded greeting message.</span></span> <span data-ttu-id="5ed7e-301">录制内容不能大于 5 MB。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-301">The recording can be no larger than 5 MB.</span></span> 
      - <span data-ttu-id="5ed7e-302">**键入问候语** 如果选择此选项，请输入希望系统读取的文本 (多达1000个字符) 。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-302">**Type in a greeting message** If you choose this option, enter text you want the system to read (up to 1000 characters).</span></span> <span data-ttu-id="5ed7e-303">例如，您可以键入 "抱歉，我们现在无法接听您的电话。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-303">For example, you can type "Sorry that we can't take your call at this time.</span></span> <span data-ttu-id="5ed7e-304">您的电话提示后，请留下您的姓名、电话号码和原因。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-304">Please leave your name, phone number, and reason for your call after the beep."</span></span>

      <span data-ttu-id="5ed7e-305">如果想要启用语音文本视频语音消息功能，请打开 "脚本"。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-305">Turn on transcription if you want to enable voice-to-text transcription of voicemail messages.</span></span>

      <span data-ttu-id="5ed7e-306">语音邮件将发送到您指定的 Microsoft 365 组中。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-306">Voicemail messages are sent to the Microsoft 365 group you specify.</span></span> <span data-ttu-id="5ed7e-307">若要访问语音邮件，组成员可以通过导航到 Outlook 中的组来打开它们。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-307">To access voicemail messages, members of the group can open them by navigating to the group in Outlook.</span></span>

* * *

<span data-ttu-id="5ed7e-308">![数字3的图标引用上一个屏幕截图调用超时中的标注 ](media/teamscallout3.png)
 **：最长等待时间**您还可以确定在队列超时和需要重定向或断开连接的情况下，呼叫可以在队列中保留多长时间。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-308">![Icon of the number 3, references a callout in the previous screenshot](media/teamscallout3.png)
**Call Timeout: maximum wait time** You can also decide how much time a call can be on hold in the queue before it times out and needs to be redirected or disconnected.</span></span> <span data-ttu-id="5ed7e-309">重定向的位置取决于设置 **通话超时** 设置的方式。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-309">Where it is redirected is based on how you set the **When a call times out** setting.</span></span> <span data-ttu-id="5ed7e-310">你可以将此时间设置为 0 到 45 分钟。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-310">You can set a time from 0 to 45 minutes.</span></span>

<span data-ttu-id="5ed7e-311">超时值可以以秒为单位按 15 秒间隔进行设置。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-311">The timeout value can be set in seconds, at 15-second intervals.</span></span> <span data-ttu-id="5ed7e-312">这样，你可以以更细的粒度操作呼叫流。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-312">This allows you to manipulate the call flow with finer granularity.</span></span> <span data-ttu-id="5ed7e-313">例如，您可以指定30秒内代理未接听的任何通话转到目录搜索自动助理。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-313">For example, you could specify that any calls that are not answered by an agent within 30 seconds go to a Directory Search auto attendant.</span></span>

<span data-ttu-id="5ed7e-314">![数字4的图标 ](media/teamscallout4.png)
 **当**调用达到您在呼叫**可以在队列设置中等待的时间**时，当调用达到所设置的限制时，将在上一个屏幕截图中引用标注，您可以选择对呼叫执行的操作：</span><span class="sxs-lookup"><span data-stu-id="5ed7e-314">![Icon of the number 4, references a callout in the previous screenshot](media/teamscallout4.png)
**When call times out** When the call reaches the limit you set on the **How long a call can wait in the queue** setting, you can choose what happens to the call:</span></span>

- <span data-ttu-id="5ed7e-315">**断开连接** 通话断开。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-315">**Disconnect** The call is disconnected.</span></span>

- <span data-ttu-id="5ed7e-316">**将此呼叫重定向到** 如果选择此选项，则可以使用以下选项：</span><span class="sxs-lookup"><span data-stu-id="5ed7e-316">**Redirect this call to** When you choose this, you have these options:</span></span>

  - <span data-ttu-id="5ed7e-317">**组织中的人员** 具有电话系统许可证并已启用企业语音或具有通话计划的在线用户。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-317">**Person in organization** An online user with a Phone System license and enabled for Enterprise Voice or have Calling Plans.</span></span>

  - <span data-ttu-id="5ed7e-318">**语音应用** 选择与已创建的通话队列或自动助理相关联的资源帐户的名称。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-318">**Voice app** Select the name of a resource account associated with either a call queue or auto attendant that you already created.</span></span>

  - <span data-ttu-id="5ed7e-319">**外部电话号码** 选择此 "将呼叫转接到您指定的外部电话号码。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-319">**External phone number** Choose this to transfer the caller to an external phone number that you specify.</span></span> <span data-ttu-id="5ed7e-320">请注意以下事项：</span><span class="sxs-lookup"><span data-stu-id="5ed7e-320">Note the following:</span></span>

    - <span data-ttu-id="5ed7e-321">与使 PSTN 传出的应用程序关联的资源帐户必须具有电话号码，并且必须分配有一个虚拟电话系统许可证。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-321">The resource account associated with the application making the PSTN transfer out must have a phone number and be assigned a Virtual Phone System license.</span></span> <span data-ttu-id="5ed7e-322">不支持电话系统许可证。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-322">Phone System licenses aren't supported.</span></span> <span data-ttu-id="5ed7e-323">此外，资源帐户必须具有下列其中一项：</span><span class="sxs-lookup"><span data-stu-id="5ed7e-323">Additionally, the resource account must have one of the following:</span></span>
        - <span data-ttu-id="5ed7e-324">对于带有呼叫计划编号的资源帐户，请分配 [呼叫计划](calling-plans-for-office-365.md) 许可证。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-324">For a resource account with a Calling Plan number, assign a [Calling Plan](calling-plans-for-office-365.md) license.</span></span>
        - <span data-ttu-id="5ed7e-325">对于具有直接路由号码的资源帐户，请分配 [联机语音路由策略](manage-voice-routing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-325">For a resource account with a Direct Routing number, assign an [online voice routing policy](manage-voice-routing-policies.md).</span></span>
    - <span data-ttu-id="5ed7e-326">显示的出站电话号码按如下方式确定：</span><span class="sxs-lookup"><span data-stu-id="5ed7e-326">The outbound phone number that's displayed is determined as follows:</span></span>
        - <span data-ttu-id="5ed7e-327">对于呼叫计划号码，将显示原始呼叫者的电话号码。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-327">For Calling Plan numbers, the original caller's phone number is displayed.</span></span>
        - <span data-ttu-id="5ed7e-328">对于直接路由号码，发送的号码基于 P 宣称的身份 (PAI 在 SBC 上) 设置，如下所示：</span><span class="sxs-lookup"><span data-stu-id="5ed7e-328">For Direct Routing numbers, the number sent is based on the P-Asserted-Identity (PAI) setting on the SBC, as follows:</span></span>
            - <span data-ttu-id="5ed7e-329">如果设置为 "已禁用"，将显示原始呼叫者的电话号码。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-329">If set to Disabled, the original caller's phone number is displayed.</span></span> <span data-ttu-id="5ed7e-330">这是默认和推荐的设置。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-330">This is the default and recommended setting.</span></span>
            - <span data-ttu-id="5ed7e-331">如果设置为 "启用"，则显示资源帐户电话号码。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-331">If set to Enabled, the resource account phone number is displayed.</span></span>
    - <span data-ttu-id="5ed7e-332">不支持在通话计划中继和直接路由中继之间转移。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-332">Transfers between Calling Plan trunks and Direct Routing trunks aren't supported.</span></span>
    - <span data-ttu-id="5ed7e-333">**语音邮件** 选择包含组织中需要访问此呼叫队列接收的语音邮件的用户的 Microsoft 365 组，然后选择下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="5ed7e-333">**Voicemail** Select the Microsoft 365 group that contains the users in your organization that need to access voicemail received by this call queue, and then select one of the following:</span></span>
      - <span data-ttu-id="5ed7e-334">**播放音频文件** 如果选择此选项，请选择 " **上传文件** " 以上载录制的问候消息。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-334">**Play an audio file** If you choose this option, select **Upload file** to upload a recorded greeting message.</span></span> <span data-ttu-id="5ed7e-335">录制内容不能大于 5 MB。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-335">The recording can be no larger than 5 MB.</span></span>
      
      - <span data-ttu-id="5ed7e-336">**键入问候语** 如果选择此选项，请输入希望系统读取的文本 (多达1000个字符) 。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-336">**Type in a greeting message** If you choose this option, enter text you want the system to read (up to 1000 characters).</span></span> <span data-ttu-id="5ed7e-337">例如，您可以键入 "抱歉，我们现在无法接听您的电话。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-337">For example, you can type "Sorry that we can't take your call at this time.</span></span> <span data-ttu-id="5ed7e-338">您的电话提示后，请留下您的姓名、电话号码和原因。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-338">Please leave your name, phone number, and reason for your call after the beep."</span></span>

      <span data-ttu-id="5ed7e-339">如果想要启用语音文本视频语音消息功能，请打开 "脚本"。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-339">Turn on transcription if you want to enable voice-to-text transcription of voicemail messages.</span></span>

      <span data-ttu-id="5ed7e-340">语音邮件将发送到您指定的 Microsoft 365 组中。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-340">Voicemail messages are sent to the Microsoft 365 group you specify.</span></span> <span data-ttu-id="5ed7e-341">若要访问语音邮件，组成员可以通过导航到 Outlook 中的组来打开它们。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-341">To access voicemail messages, members of the group can open them by navigating to the group in Outlook.</span></span>

## <a name="change-caller-id-for-outbound-calls"></a><span data-ttu-id="5ed7e-342">更改出站呼叫的来电显示</span><span class="sxs-lookup"><span data-stu-id="5ed7e-342">Change Caller ID for outbound calls</span></span>

<span data-ttu-id="5ed7e-343">若要保护呼叫代理的身份，请使用 **CsCallingLineIdentity** cmdlet 将呼叫者 ID 更改为拨出电话、自动助理或任何服务号码，如下例所示：</span><span class="sxs-lookup"><span data-stu-id="5ed7e-343">To protect a call agent's identity, change their caller ID for outbound calls to a call queue, auto attendant, or any service number with the **New-CsCallingLineIdentity** cmdlet as in the following example:</span></span>

```powershell
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

<span data-ttu-id="5ed7e-344">然后使用 **CallingLineIdentity** cmdlet 将该策略应用于用户，如下例所示：</span><span class="sxs-lookup"><span data-stu-id="5ed7e-344">Then apply the policy to the user with the **Grant-CallingLineIdentity** cmdlet as in the following example:</span></span> 

```powershell
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

<span data-ttu-id="5ed7e-345">有关详细信息，请参阅 [如何在组织中使用呼叫者 ID](/microsoftteams/how-can-caller-id-be-used-in-your-organization)。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-345">For more information, see [How can caller ID be used in your organization](/microsoftteams/how-can-caller-id-be-used-in-your-organization).</span></span>

## <a name="call-queue-cmdlets"></a><span data-ttu-id="5ed7e-346">呼叫队列 cmdlet</span><span class="sxs-lookup"><span data-stu-id="5ed7e-346">Call queue cmdlets</span></span>

<span data-ttu-id="5ed7e-347">还可以使用 Windows PowerShell 来创建和设置呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-347">You can also use Windows PowerShell to create and set up call queues.</span></span> <span data-ttu-id="5ed7e-348">下面是用于管理呼叫队列的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-348">Here are the cmdlets that you use to manage a call queue.</span></span>

- [<span data-ttu-id="5ed7e-349">新-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="5ed7e-349">New-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="5ed7e-350">Set-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="5ed7e-350">Set-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/set-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="5ed7e-351">CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="5ed7e-351">Get-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/get-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="5ed7e-352">Remove-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="5ed7e-352">Remove-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-CsCallQueue?view=skype-ps)

### <a name="more-about-windows-powershell"></a><span data-ttu-id="5ed7e-353">有关 Windows PowerShell 的详细信息</span><span class="sxs-lookup"><span data-stu-id="5ed7e-353">More about Windows PowerShell</span></span>

- <span data-ttu-id="5ed7e-354">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-354">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="5ed7e-355">使用 Windows PowerShell，你可以通过单个管理点管理 Microsoft 365 或 Office 365 和 Microsoft 团队。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-355">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Microsoft Teams with a single point of administration.</span></span> <span data-ttu-id="5ed7e-356">当有多个任务需要执行时，它可以简化日常工作。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-356">It can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="5ed7e-357">若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="5ed7e-357">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="5ed7e-358">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="5ed7e-358">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [<span data-ttu-id="5ed7e-359">为什么要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="5ed7e-359">Why you need to use Office 365 PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- <span data-ttu-id="5ed7e-360">当您同时为多个用户进行更改时，Windows PowerShell 在速度、简洁性和工作效率方面具有许多优势。</span><span class="sxs-lookup"><span data-stu-id="5ed7e-360">Windows PowerShell has many advantages in speed, simplicity, and productivity over the Microsoft Teams admin center when you make changes for many users at once.</span></span> <span data-ttu-id="5ed7e-361">通过以下主题了解这些优势：</span><span class="sxs-lookup"><span data-stu-id="5ed7e-361">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="5ed7e-362">通过 Windows PowerShell 管理 Microsoft 365 或 Office 365</span><span class="sxs-lookup"><span data-stu-id="5ed7e-362">Manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [<span data-ttu-id="5ed7e-363">为 Windows PowerShell 设置计算机</span><span class="sxs-lookup"><span data-stu-id="5ed7e-363">Set up your computer for Windows PowerShell</span></span>](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a><span data-ttu-id="5ed7e-364">相关主题</span><span class="sxs-lookup"><span data-stu-id="5ed7e-364">Related topics</span></span>

[<span data-ttu-id="5ed7e-365">电话系统的功能</span><span class="sxs-lookup"><span data-stu-id="5ed7e-365">Here's what you get with Phone System</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="5ed7e-366">获取服务电话号码</span><span class="sxs-lookup"><span data-stu-id="5ed7e-366">Getting service phone numbers</span></span>](getting-service-phone-numbers.md)

[<span data-ttu-id="5ed7e-367">音频会议和通话套餐的国家/地区可用性</span><span class="sxs-lookup"><span data-stu-id="5ed7e-367">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="5ed7e-368">新-CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="5ed7e-368">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
