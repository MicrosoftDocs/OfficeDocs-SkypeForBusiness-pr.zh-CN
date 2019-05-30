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
- Teams_ITAdmin_Help
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 了解如何为云呼叫队列设置电话系统, 以便为你提供组织问候语、保持的音乐以及将呼叫重定向到通讯组列表和安全组中的呼叫代理。 You can also set the maximum queue size, time out, and call handling options.
ms.openlocfilehash: 3c98f7c9b8bb96b4c3792e4ec5abe92628d8e914
ms.sourcegitcommit: b5949233f8080a6cf0edb4b5e27272214feb1c22
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34549008"
---
# <a name="create-a-cloud-call-queue"></a><span data-ttu-id="28835-104">创建云呼叫队列</span><span class="sxs-lookup"><span data-stu-id="28835-104">Create a Cloud call queue</span></span>

<span data-ttu-id="28835-105">云呼叫队列包括当某人拨打您的组织的电话号码时使用的问候语、自动保持通话的功能, 以及搜索下一个可用的呼叫代理以处理呼叫, 而通话的人员在保持状态时收听音乐。</span><span class="sxs-lookup"><span data-stu-id="28835-105">Cloud call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold.</span></span> <span data-ttu-id="28835-106">You can create single or multiple call queues for your organization.</span><span class="sxs-lookup"><span data-stu-id="28835-106">You can create single or multiple call queues for your organization.</span></span>
  
<span data-ttu-id="28835-107">云呼叫队列可以提供:</span><span class="sxs-lookup"><span data-stu-id="28835-107">Cloud call queues can provide:</span></span>
  
- <span data-ttu-id="28835-108">组织问候语。</span><span class="sxs-lookup"><span data-stu-id="28835-108">An organizational greeting.</span></span>
- <span data-ttu-id="28835-109">在呼叫者保持等待时播放的音乐。</span><span class="sxs-lookup"><span data-stu-id="28835-109">Music while people are waiting on hold.</span></span>
- <span data-ttu-id="28835-110">将呼叫重定向到启用邮件的通讯组列表和安全组中的呼叫代理。</span><span class="sxs-lookup"><span data-stu-id="28835-110">Redirecting of calls to call agents in mail-enabled distribution lists and security groups.</span></span>
- <span data-ttu-id="28835-111">为呼叫队列设置最大大小、超时和呼叫处理选项。</span><span class="sxs-lookup"><span data-stu-id="28835-111">Making settings for call queue maximum size, timeout, and call handling options.</span></span>

<span data-ttu-id="28835-112">当某人通过[资源帐户](manage-resource-accounts.md)拨打与呼叫队列相关联的电话号码时, 他们将首先听到问候语 (如果已设置), 然后将其放入队列, 然后等待下一个可用的呼叫代理。</span><span class="sxs-lookup"><span data-stu-id="28835-112">When someone calls in to a phone number that is associated  with a call queue via a [resource account](manage-resource-accounts.md), they will hear a greeting first (if any is set up), and then they will be put in the queue and wait for the next available call agent.</span></span> <span data-ttu-id="28835-113">拨入的人员将在处于等待状态时听到音乐, 并且将在先进*先出*(FIFO) 订单中向呼叫代理提供呼叫。</span><span class="sxs-lookup"><span data-stu-id="28835-113">The person calling in will hear music while they are on hold waiting, and the calls will be offered to the call agents in *First In, First Out* (FIFO) order.</span></span>
  
<span data-ttu-id="28835-114">在队列中等待的所有通话都将使用下列方法之一进行分发:</span><span class="sxs-lookup"><span data-stu-id="28835-114">All calls waiting in the queue will be distributed using one of the following methods:</span></span>
  
- <span data-ttu-id="28835-115">通过助理路由, 队列中的第一个呼叫将同时拨打所有代理。</span><span class="sxs-lookup"><span data-stu-id="28835-115">With attendant routing, the first call in the queue will ring all agents at the same time.</span></span>
- <span data-ttu-id="28835-116">使用串行路由时，队列中的第一个呼叫将逐个拨打所有呼叫代理。</span><span class="sxs-lookup"><span data-stu-id="28835-116">With serial routing, the first call in the queue will ring all call agents one by one.</span></span>
- <span data-ttu-id="28835-117">通过循环复用, 传入呼叫的路由将平衡, 以便每个呼叫代理将从队列中获得相同数量的通话。</span><span class="sxs-lookup"><span data-stu-id="28835-117">With round robin, routing of incoming calls is balanced so that each call agent will get the same number of calls from the queue.</span></span>

    > [!NOTE]
    > <span data-ttu-id="28835-118">不会呼叫处于**脱机**状态、已将其状态设置为 **请勿打扰**或已退出呼叫队列的呼叫代理。</span><span class="sxs-lookup"><span data-stu-id="28835-118">Call agents who are **Offline**, have set their presence to **Do not Disturb,** or have opted out of the call queue won't be called.</span></span>
  
- <span data-ttu-id="28835-119">同一时间只会向呼叫代理发送一个传入呼叫通知（队列最前面的呼叫）。</span><span class="sxs-lookup"><span data-stu-id="28835-119">Only one incoming call notification (for the call at the head of the queue) at a time will be sent to the call agents.</span></span>
- <span data-ttu-id="28835-120">呼叫代理接受呼叫后，队列中的下一个传入呼叫开始拨叫所有代理。</span><span class="sxs-lookup"><span data-stu-id="28835-120">After a call agent accepts the call, the next incoming call in the queue will start ringing call agents.</span></span>

> [!NOTE]
> <span data-ttu-id="28835-121">本文适用于 Microsoft 团队和 Skype for business Online。</span><span class="sxs-lookup"><span data-stu-id="28835-121">This article applies to both Microsoft Teams and Skype for Business Online.</span></span>

## <a name="step-1---get-started"></a><span data-ttu-id="28835-122">步骤 1-入门</span><span class="sxs-lookup"><span data-stu-id="28835-122">Step 1 - Get started</span></span>

<span data-ttu-id="28835-123">要开始使用呼叫队列，记住以下几点至关重要：</span><span class="sxs-lookup"><span data-stu-id="28835-123">To get started using call queues, it's important to remember a few things:</span></span>
  
- <span data-ttu-id="28835-124">通话队列必须具有关联的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="28835-124">A call queue is required to have an associated resource account.</span></span> <span data-ttu-id="28835-125">有关资源帐户的详细信息, 请参阅[管理团队中的资源帐户](manage-resource-accounts.md)。</span><span class="sxs-lookup"><span data-stu-id="28835-125">See [Manage resource accounts in Teams](manage-resource-accounts.md) for details on resource accounts.</span></span>
- <span data-ttu-id="28835-126">如果你计划分配直接路由号码, 你需要使用手机系统加载项获取以下许可证并将其分配给\(你的资源帐户 Office 365 企业版 E1、E3 或 E5\)。</span><span class="sxs-lookup"><span data-stu-id="28835-126">If you plan to assign a Direct Routing number, you need to acquire and assign the following licenses to your resource accounts \(Office 365 Enterprise E1, E3 or E5, with the Phone System add-on\).</span></span>
- <span data-ttu-id="28835-127">如果你改为分配 Microsoft 服务号码, 你需要使用手机系统加载项和呼叫计划\(\)获取并将以下许可证分配给你的资源帐户 Office 365 企业版 E1、E3 或 E5。</span><span class="sxs-lookup"><span data-stu-id="28835-127">If you are assigning a Microsoft service number instead, you need to acquire and assign the following licenses to your resource account \(Office 365 Enterprise E1, E3 or E5, with the Phone System add-on and a Calling Plan\).</span></span>
- <span data-ttu-id="28835-128">您只需向分配了电话号码的资源帐户授予许可证。</span><span class="sxs-lookup"><span data-stu-id="28835-128">You only need to license the resource accounts with a phone number assigned to them.</span></span> <span data-ttu-id="28835-129">在嵌套的自动助理或呼叫队列中, 如果自动助理或呼叫队列没有与之关联的电话号码, 则无需向其授予许可证。</span><span class="sxs-lookup"><span data-stu-id="28835-129">In a nested auto attendant or call queue, you do not need to license the rest of the auto attendants or call queues if they do not have phone numbers associated with them.</span></span> 

> [!NOTE] 
> <span data-ttu-id="28835-130">只有 Microsoft 团队用户和代理才支持自动助理和呼叫队列的直接路由服务号码。</span><span class="sxs-lookup"><span data-stu-id="28835-130">Direct Routing service numbers for auto attendant and call queues are supported for Microsoft Teams users and agents only.</span></span>

> [!NOTE] 
> <span data-ttu-id="28835-131">Microsoft 正在致力于应用程序 (如云自动助理和呼叫队列) 的无成本许可模型, 现在您需要使用用户许可模型。</span><span class="sxs-lookup"><span data-stu-id="28835-131">Microsoft is working on a cost-free licensing model for applications such as Cloud auto attendants and call queues, for now you need to use the user-licensing model.</span></span>

> [!NOTE]
> <span data-ttu-id="28835-132">若要将呼叫重定向到您的组织中联机的人员, 他们必须具有**电话系统**许可证并启用企业语音或拥有 Office 365 通话计划。</span><span class="sxs-lookup"><span data-stu-id="28835-132">To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans.</span></span> <span data-ttu-id="28835-133">请参阅[分配 Skype For business 许可证](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)或[分配 Microsoft 团队许可证](assign-teams-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="28835-133">See  [Assign Skype for Business licenses](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) or [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="28835-134">要为他们启用企业语音，可以使用 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="28835-134">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="28835-135">例如运行： `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="28835-135">For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>
  
- <span data-ttu-id="28835-136">若要了解有关 Office 365 呼叫计划的详细信息, 请参阅[手机系统和通话计划](calling-plan-landing-page.md)和[Office 365 的呼叫计划](calling-plans-for-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="28835-136">To learn more about Office 365 Calling Plans, see [Phone System and Calling Plans](calling-plan-landing-page.md) and [Calling Plans for Office 365](calling-plans-for-office-365.md).</span></span>

- <span data-ttu-id="28835-137">您只能分配您在**Microsoft 团队管理中心**或从另一个服务提供商转移到云呼叫队列的收费和免费服务电话号码。</span><span class="sxs-lookup"><span data-stu-id="28835-137">You can only assign toll and toll-free service phone numbers that you got in the **Microsoft Teams admin center** or transferred from another service provider to Cloud call queues.</span></span> <span data-ttu-id="28835-138">若要获取并使用免费电话号码，则需要设置通信点数。</span><span class="sxs-lookup"><span data-stu-id="28835-138">To get and use toll-free service numbers, you need to set up Communications Credits.</span></span>

    > [!NOTE]
    > <span data-ttu-id="28835-139">[!注释] 不能将用户（订阅者）的电话号码分配给呼叫队列 - 只能使用收费或免费服务电话号码。</span><span class="sxs-lookup"><span data-stu-id="28835-139">User (subscriber) phone numbers can't be assigned to call queues - only service toll or toll-free phone numbers can be used.</span></span>
  
- <span data-ttu-id="28835-140">当您从云呼叫队列分配传入呼叫时, 呼叫代理支持这些客户端:</span><span class="sxs-lookup"><span data-stu-id="28835-140">When you are distributing the incoming calls from a Cloud call queue, these clients are supported for call agents:</span></span>

  - <span data-ttu-id="28835-141">Skype for Business 桌面客户端 2016（32 位和 64 位版本）</span><span class="sxs-lookup"><span data-stu-id="28835-141">Skype for Business desktop client 2016 (32 and 64-bit versions)</span></span>

  - <span data-ttu-id="28835-142">Lync 桌面客户端 2013（32 位和 64 位版本）</span><span class="sxs-lookup"><span data-stu-id="28835-142">Lync desktop client 2013 (32 and 64-bit versions)</span></span>

  - <span data-ttu-id="28835-143">Microsoft 团队支持的所有 IP 电话模式。</span><span class="sxs-lookup"><span data-stu-id="28835-143">All IP phone models supported for Microsoft Teams.</span></span> <span data-ttu-id="28835-144">请参阅[获取适用于 Skype for Business Online 的电话](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online)。</span><span class="sxs-lookup"><span data-stu-id="28835-144">See [Getting phones for Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span></span>

  - <span data-ttu-id="28835-145">Mac Skype for Business 客户端（版本 16.8.196 及更高版本）</span><span class="sxs-lookup"><span data-stu-id="28835-145">Mac Skype for Business Client (version 16.8.196 and later)</span></span>

  - <span data-ttu-id="28835-146">Android Skype for Business 客户端（版本 6.16.0.9 及更高版本）</span><span class="sxs-lookup"><span data-stu-id="28835-146">Android Skype for Business Client (version 6.16.0.9 and later)</span></span>

  - <span data-ttu-id="28835-147">iPhone Skype for Business 客户端（版本 6.16.0 及更高版本）</span><span class="sxs-lookup"><span data-stu-id="28835-147">iPhone Skype for Business Client (version 6.16.0 and later)</span></span>

  - <span data-ttu-id="28835-148">iPad Skype for Business 客户端（版本 6.16.0 及更高版本）</span><span class="sxs-lookup"><span data-stu-id="28835-148">iPad Skype for Business Client (version 6.16.0 and later)</span></span>

  - <span data-ttu-id="28835-149">Microsoft Teams Windows 客户端 （32 和 64 位版本）</span><span class="sxs-lookup"><span data-stu-id="28835-149">Microsoft Teams Windows client (32 and 64-bit versions)</span></span>

  - <span data-ttu-id="28835-150">Microsoft Teams Mac 客户端</span><span class="sxs-lookup"><span data-stu-id="28835-150">Microsoft Teams Mac client</span></span>

  - <span data-ttu-id="28835-151">Microsoft Teams iPhone 应用</span><span class="sxs-lookup"><span data-stu-id="28835-151">Microsoft Teams iPhone app</span></span>

  - <span data-ttu-id="28835-152">Microsoft Teams Android 应用</span><span class="sxs-lookup"><span data-stu-id="28835-152">Microsoft Teams Android app</span></span>

## <a name="step-2---getting-or-transferring-toll-or-toll-free-service-phone-numbers"></a><span data-ttu-id="28835-153">第 2 步 - 获取或转移收费或免费服务电话号码</span><span class="sxs-lookup"><span data-stu-id="28835-153">Step 2 - Getting or transferring toll or toll-free service phone numbers</span></span>

<span data-ttu-id="28835-154">在创建和设置呼叫队列之前，您需要获取或转移现有的收费或免费服务号码。</span><span class="sxs-lookup"><span data-stu-id="28835-154">Before you can create and set up your call queues, you will need to get or transfer your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="28835-155">获得收费或免费服务电话号码后, 这些电话号码将显示在**Microsoft 团队管理中心** > **的语音** > **电话号码**中, 并且列出的**号码类型**将按**服务免费**列出。</span><span class="sxs-lookup"><span data-stu-id="28835-155">After you get the toll or toll-free service phone numbers, they will show up in **Microsoft Teams admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**.</span></span> <span data-ttu-id="28835-156">若要获取你的服务号码, 请参阅[获取服务电话号码](getting-service-phone-numbers.md)或要转移现有服务号码, 请参阅[将电话号码转移到 Office 365](transfer-phone-numbers-to-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="28835-156">To get your service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md) or if you want to transfer an existing service number, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="28835-157">如果您在美国以外, 则不能使用 Microsoft 团队管理中心获取服务号码。</span><span class="sxs-lookup"><span data-stu-id="28835-157">If you are outside the United States, you can't use the Microsoft Teams admin center to get service numbers.</span></span> <span data-ttu-id="28835-158">转到 "[管理你的组织的电话号码](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)" 以了解如何从美国以外的国家进行管理。</span><span class="sxs-lookup"><span data-stu-id="28835-158">Go to [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) instead to see how to do it from the outside of the United States.</span></span>

<span data-ttu-id="28835-159">如果你还设置自动助理, 你可能只需要将电话号码分配给主自动助理的资源帐户, 然后将呼叫者直接加入呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="28835-159">If you are also setting up auto attendants, you may only need to assign a phone number to the main auto attendant's resource account, and then have it direct callers to your call queue.</span></span> <span data-ttu-id="28835-160">如果是这种情况, 则需要创建呼叫队列, 然后才能在自动助理中创建选择呼叫队列的选项。</span><span class="sxs-lookup"><span data-stu-id="28835-160">If that's the case, the call queue will need to be created before you can create an option in the auto attendant that selects the call queue.</span></span>
  
## <a name="step-3---create-a-new-call-queue"></a><span data-ttu-id="28835-161">步骤 3-创建新的呼叫队列</span><span class="sxs-lookup"><span data-stu-id="28835-161">Step 3 - Create a new call queue</span></span>

[!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

> [!IMPORTANT]
> <span data-ttu-id="28835-162">每个通话队列都必须具有关联的[资源帐户](manage-resource-accounts.md)。</span><span class="sxs-lookup"><span data-stu-id="28835-162">Every call queue is required to have an associated [resource account](manage-resource-accounts.md).</span></span> <span data-ttu-id="28835-163">必须先创建资源帐户, 然后才能将其关联到呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="28835-163">You must create the resource account first, then you can associate it to the call queue.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="28835-164">使用 Microsoft 团队管理中心</span><span class="sxs-lookup"><span data-stu-id="28835-164">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="28835-165">在**Microsoft 团队管理中心**、**语音** >  **呼叫队列**中, 单击 " **+ 添加新**":</span><span class="sxs-lookup"><span data-stu-id="28835-165">In the **Microsoft Teams admin center**, **Voice** >  **Call queues**, then click **+ Add new**:</span></span>

### <a name="set-the-call-queue-display-name-and-resource-account"></a><span data-ttu-id="28835-166">设置呼叫队列显示名称和资源帐户</span><span class="sxs-lookup"><span data-stu-id="28835-166">Set the call queue display name and resource account</span></span>

![带有编号标注的新通话队列的屏幕截图](media/37ecc300-a108-4294-8463-fce570dfce72.png)

* * *

<span data-ttu-id="28835-168">![数字1的图标, 引用上一个屏幕截图](media/sfbcallout1.png)
**名称**中的标注输入呼叫队列的描述性显示名称。</span><span class="sxs-lookup"><span data-stu-id="28835-168">![Icon of the number 1, referencing a callout in the previous screenshot](media/sfbcallout1.png)
**Name** Enter a descriptive display name for the call queue.</span></span> <span data-ttu-id="28835-169">此为必填字段，最多可以包含 64 个字符，其中包括空格。</span><span class="sxs-lookup"><span data-stu-id="28835-169">This is required and can contain up to 64 characters, including spaces.</span></span>

 <span data-ttu-id="28835-170">此名称将显示在传入呼叫的通知中。</span><span class="sxs-lookup"><span data-stu-id="28835-170">This name will be displayed in the notification for the incoming call.</span></span>

* * *

![数字2的图标, 引用上一个屏幕截图中的标注](media/sfbcallout2.png)

<span data-ttu-id="28835-172">**添加帐户**选择资源帐户。</span><span class="sxs-lookup"><span data-stu-id="28835-172">**Add Accounts** Select a resource account.</span></span> <span data-ttu-id="28835-173">资源帐户可能与呼叫队列的服务收费或免费电话号码相关联, 但是每个通话队列都需要关联的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="28835-173">The resource account may or may not be associated with a service toll or toll-free phone number for the call queue, but each call queue requires an associated resource account.</span></span>

<span data-ttu-id="28835-174">如果未列出任何列表, 则需要先获取服务号码并将其分配给资源帐户, 如前文所述。</span><span class="sxs-lookup"><span data-stu-id="28835-174">If there aren't any listed, you need to get service numbers and assign them to a Resource account before you can create this call queue, as described earlier.</span></span> <span data-ttu-id="28835-175">若要获取你的服务号码, 请参阅[获取服务电话号码](getting-service-phone-numbers.md)。</span><span class="sxs-lookup"><span data-stu-id="28835-175">To get your service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md).</span></span> <span data-ttu-id="28835-176">如果您希望通话队列具有相关联的电话号码, 请按照在[团队中管理资源帐户](manage-resource-accounts.md)中所述创建资源帐户。</span><span class="sxs-lookup"><span data-stu-id="28835-176">You'll need to create a resource account as described in [Manage resource accounts in Teams](manage-resource-accounts.md) if you want your call queue to have an associated phone number.</span></span>

> [!NOTE]
> <span data-ttu-id="28835-177">如果你希望或需要分配**域**, 你可以通过将其分配给呼叫队列的资源帐户来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="28835-177">If you want or need to assign a **Domain** you would do so by assigning it to the resource account for the call queue.</span></span>

### <a name="set-the-greeting-and-music-played-while-on-hold"></a><span data-ttu-id="28835-178">设置通话保持时播放的问候语和音乐</span><span class="sxs-lookup"><span data-stu-id="28835-178">Set the greeting and music played while on hold</span></span>

![带有编号标注的问候和音乐选项的屏幕截图](media/1d395a93-7cab-4178-9295-12d5379e20de.png)
  
* * *

![数字1的图标, 引用上一个屏幕截图中的标注](media/sfbcallout1.png)

<span data-ttu-id="28835-181">**问候语**是可选设置。</span><span class="sxs-lookup"><span data-stu-id="28835-181">**Greeting** is optional.</span></span> <span data-ttu-id="28835-182">这是呼叫呼叫队列号码的用户所播放的问候语。</span><span class="sxs-lookup"><span data-stu-id="28835-182">This is the greeting that is played for people who call in to the call queue number.</span></span>

<span data-ttu-id="28835-183">你可以上载音频文件 (.wav、mp3 或 .wma 格式)。</span><span class="sxs-lookup"><span data-stu-id="28835-183">You can upload an audio file (.wav, .mp3, or .wma formats).</span></span>

![数字2的图标, 引用上一个屏幕截图中的标注](media/sfbcallout2.png)

<span data-ttu-id="28835-185">**暂停的音乐**你可以使用与呼叫队列一起提供的默认音乐保持通话, 也可以将音频文件上载为 .wav、mp3 或 .wma 格式, 用作保留的自定义音乐。</span><span class="sxs-lookup"><span data-stu-id="28835-185">**Music on hold** You can either use the default Music on Hold provided with the call queue, or you can upload an audio file in .wav, mp3, or .wma formats to use as your custom Music on Hold.</span></span>

* * *

### <a name="select-the-call-answering-options"></a><span data-ttu-id="28835-186">选择呼叫应答选项</span><span class="sxs-lookup"><span data-stu-id="28835-186">Select the call answering options</span></span>

![带有编号标注的呼叫应答选项的屏幕截图](media/5d249515-d532-4af2-90da-011404028b89.png)

![数字1的图标, 引用上一个屏幕截图中的标注](media/sfbcallout1.png)

<span data-ttu-id="28835-189">您最多可以选择属于指定邮寄列表或组的200呼叫代理。</span><span class="sxs-lookup"><span data-stu-id="28835-189">You can select up to 200 call agents belonging to specified mailing lists or groups.</span></span> <span data-ttu-id="28835-190">通话代理必须是:</span><span class="sxs-lookup"><span data-stu-id="28835-190">Call agents must be either:</span></span>

- <span data-ttu-id="28835-191">拥有**电话系统**许可证和启用了企业语音或拥有通话套餐的在线用户。</span><span class="sxs-lookup"><span data-stu-id="28835-191">An Online user with a **Phone System** license and enabled for Enterprise Voice or with a Calling Plan.</span></span>

  > [!NOTE]
  > <span data-ttu-id="28835-192">若要将呼叫重定向到您的组织中联机的人员, 他们必须具有**电话系统**许可证并启用企业语音或有呼叫计划。</span><span class="sxs-lookup"><span data-stu-id="28835-192">To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have a Calling Plan.</span></span> <span data-ttu-id="28835-193">请参阅[分配 Skype For business 许可证](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses)或[分配 Microsoft 团队许可证](assign-teams-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="28835-193">See [Assign Skype for Business licenses](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses) or [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span>

 <span data-ttu-id="28835-194">要为他们启用企业语音，可以使用 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="28835-194">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="28835-195">例如运行： `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="28835-195">For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

- <span data-ttu-id="28835-196">拥有**电话系统**许可证和通话套餐（已添加到 Office 365 组、已启用邮件的通讯组列表或安全组）的在线用户。</span><span class="sxs-lookup"><span data-stu-id="28835-196">Online users with a **Phone System** license and a Calling Plan that are added to an Office 365 Group, a mail-enabled Distribution List, or a Security Group.</span></span> <span data-ttu-id="28835-197">为通讯组列表或安全组添加的新代理最多可能需要3小时才能开始从呼叫队列接收呼叫。</span><span class="sxs-lookup"><span data-stu-id="28835-197">It might take up to 3 hours for a new agent added for a distribution list or a security group to start receiving calls from a call queue.</span></span> <span data-ttu-id="28835-198">新创建的通讯组列表或安全组可能需要长达48小时才能与通话队列一起使用。</span><span class="sxs-lookup"><span data-stu-id="28835-198">A newly created distribution list or security group might take up to 48 hours to become available to be used with call queues.</span></span> <span data-ttu-id="28835-199">新创建的 Office 365 组几乎立即就可使用。</span><span class="sxs-lookup"><span data-stu-id="28835-199">Newly created Office 365 Groups are available almost immediately.</span></span>

- <span data-ttu-id="28835-200">如果你的代理使用 Microsoft 团队应用接收呼叫队列呼叫, 则他们必须处于 TeamsOnly 模式。</span><span class="sxs-lookup"><span data-stu-id="28835-200">If your agents are using Microsoft Teams App to receive call queue calls, they need to be in TeamsOnly mode.</span></span>

!["添加呼叫代理" 窗格的屏幕截图](media/skype-for-business-add-agents-to-call-queue.png)

![数字2的图标, 引用上一个屏幕截图中的标注](media/sfbcallout2.png)

<span data-ttu-id="28835-203">**路由方法**您可以为您的通话队列分发方法选择 "**助理**"、"**串行**" 或 "**循环**"。</span><span class="sxs-lookup"><span data-stu-id="28835-203">**Routing method** You can choose either **Attendant**,  **Serial**, or **Round Robin** for your call queue distribution method.</span></span> <span data-ttu-id="28835-204">所有新的和现有呼叫队列将具有默认情况下选中的助理路由。</span><span class="sxs-lookup"><span data-stu-id="28835-204">All new and existing call queues will have attendant routing selected by default.</span></span> <span data-ttu-id="28835-205">使用 "助理路由" 时, 队列中的首次呼叫将同时拨打所有呼叫代理。</span><span class="sxs-lookup"><span data-stu-id="28835-205">When attendant routing is used, the first call in the queue will ring all of the call agents at the same time.</span></span> <span data-ttu-id="28835-206">获取呼叫的第一个呼叫代理将获取呼叫。</span><span class="sxs-lookup"><span data-stu-id="28835-206">The first call agent to pick up the call gets the call.</span></span>

- <span data-ttu-id="28835-207">**助理路由**使队列中的第一次通话同时拨打所有呼叫工程师。</span><span class="sxs-lookup"><span data-stu-id="28835-207">**Attendant routing** causes the first call in the queue to ring all call agents at the same time.</span></span> <span data-ttu-id="28835-208">获取呼叫的第一个呼叫代理将获取呼叫。</span><span class="sxs-lookup"><span data-stu-id="28835-208">The first call agent to pick up the call gets the call.</span></span>
- <span data-ttu-id="28835-209">**串行路由**传入呼叫将从呼叫代理列表的开头开始, 逐个拨打呼叫代理。</span><span class="sxs-lookup"><span data-stu-id="28835-209">**Serial routing** incoming calls will ring call agents one by one, starting from the beginning of the call agent list.</span></span> <span data-ttu-id="28835-210">不能在 "呼叫代理程序" 列表中订购代理。</span><span class="sxs-lookup"><span data-stu-id="28835-210">Agents cannot be ordered within the call agent list.</span></span> <span data-ttu-id="28835-211">如果代理挂断或不接听电话，电话将打给列表的下一位代理，并将尝试逐个拨打所有代理，直到有人接听或队列等待超时为止。</span><span class="sxs-lookup"><span data-stu-id="28835-211">If an agent dismisses or does not pick up a call, the call will ring the next agent on the list and will try all agents one by one until it is picked up or times out waiting in the queue.</span></span>
  > [!NOTE]
  > <span data-ttu-id="28835-212">串行路由将跳过处于**脱机**状态、已将其状态设置为 **请勿打扰**或**已选择退出**不从此队列获取呼叫的代理。</span><span class="sxs-lookup"><span data-stu-id="28835-212">Serial routing will skip agents who are **Offline**, have set their presence to **Do not Disturb**, or have **opted out** of getting calls from this queue.</span></span>
- <span data-ttu-id="28835-213">**循环法**平衡传入呼叫的路由, 以便每个呼叫代理将从队列中获得相同数量的通话。</span><span class="sxs-lookup"><span data-stu-id="28835-213">**Round robin** balances routing of incoming calls so that each call agent will get the same number of calls from the queue.</span></span> <span data-ttu-id="28835-214">这在入站销售环境中可能非常可取, 可确保所有呼叫代理中的同等商机。</span><span class="sxs-lookup"><span data-stu-id="28835-214">This may be very desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

### <a name="select-an-agent-opt-out-option"></a><span data-ttu-id="28835-215">选择代理退出选项</span><span class="sxs-lookup"><span data-stu-id="28835-215">Select an agent opt out option</span></span>

![代理选择退出选项的屏幕截图, 带有编号标注](media/99279eff-db61-4acf-9b62-64be84b6414b.png)
  
* * *

![数字1的图标, 引用上一个屏幕截图中的标注](media/sfbcallout1.png)

<span data-ttu-id="28835-218">**代理退出选项**你可以选择允许呼叫队列代理通过选择**代理退出选项**，不接收来自特定队列的呼叫。
。</span><span class="sxs-lookup"><span data-stu-id="28835-218">**Agent Opt out option** You can choose to allow call queue agents to opt out of taking calls from a particular queue by selecting **Agent Opt out option**.</span></span>

<span data-ttu-id="28835-219">如果启用此选项, 将允许此队列中的所有代理从该呼叫队列开始或停止接收呼叫。</span><span class="sxs-lookup"><span data-stu-id="28835-219">Enabling this option allows all agents in this queue to start or stop receiving calls from this call queue at will.</span></span> <span data-ttu-id="28835-220">通过清除此复选框，你可以随时撤消代理选择退出特权，这将导致所有代理自动选择再加入此队列 （所有代理的默认设置）。</span><span class="sxs-lookup"><span data-stu-id="28835-220">You can revoke the agent opt-out privilege at any time by clearing the check box, causing agents to become automatically opted in for this queue again (the default setting for all agents).</span></span>

<span data-ttu-id="28835-221">若要访问选择退出选项，代理可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="28835-221">To access the opt-out option, agents can do the following:</span></span>

 1. <span data-ttu-id="28835-222">在其桌面 Skype for Business 客户端中打开**选项**。</span><span class="sxs-lookup"><span data-stu-id="28835-222">Open **Options** in their desktop Skype for Business client.</span></span>
 2. <span data-ttu-id="28835-223">在**呼叫转移**选项卡中，单击**在线编辑设置**链接。</span><span class="sxs-lookup"><span data-stu-id="28835-223">On the **Call Forwarding** tab, click the **Edit settings online** link.</span></span>
 3. <span data-ttu-id="28835-224">在用户设置页中，单击**呼叫队列**，然后清除他们想要退出的任何队列对应的复选框。</span><span class="sxs-lookup"><span data-stu-id="28835-224">On the user settings page, click **Call Queues**, and then clear the check boxes for any queues for which they want to opt out.</span></span>

    > [!NOTE]
    > <span data-ttu-id="28835-225">使用 Skype for Business 桌面之外的应用或终结点的代理可以从 "用户设置" 门户[https://aka.ms/cqsettings](https://aka.ms/cqsettings)访问 "退出" 选项。</span><span class="sxs-lookup"><span data-stu-id="28835-225">Agents using apps or endpoints other than Skype for Business Desktop can access the opt out option from the user settings portal [https://aka.ms/cqsettings](https://aka.ms/cqsettings).</span></span>

<span data-ttu-id="28835-226">![数字2的图标, 在上一个屏幕截图](media/sfbcallout2.png)
中引用标注**Agent 警报设置**</span><span class="sxs-lookup"><span data-stu-id="28835-226">![Icon of the number 2, referencing a callout in the previous screenshot](media/sfbcallout2.png)
**Agent Alert setting**</span></span>

<span data-ttu-id="28835-227">这定义了在串行或循环路由方法移到下一个代理之前通知呼叫的代理的持续时间。</span><span class="sxs-lookup"><span data-stu-id="28835-227">This defines the duration of an agent being notified of a call before the Serial or Round Robin routing methods move to the next agent.</span></span>

<span data-ttu-id="28835-228">默认设置为30秒, 但最多可设置3分钟。</span><span class="sxs-lookup"><span data-stu-id="28835-228">The default setting is 30 seconds, but it can be set for up to 3 minutes.</span></span>

* * *

### <a name="set-the-call-overflow-and-timeout-handling-options"></a><span data-ttu-id="28835-229">设置呼叫溢出和超时处理选项</span><span class="sxs-lookup"><span data-stu-id="28835-229">Set the call overflow and timeout handling options</span></span>

![溢出处理选项 (带有编号标注) 的屏幕截图](media/3f018734-16fe-458b-827d-71fc25155cde.png)
  
* * *

![数字1的图标, 引用上一个屏幕截图中的标注](media/sfbcallout1.png)

<span data-ttu-id="28835-232">**队列中的最大呼叫数** 使用此字段来设置同一时间可以在队列中等待的最大呼叫数。</span><span class="sxs-lookup"><span data-stu-id="28835-232">**Maximum calls in the queue** Use this to set the maximum calls that can wait in the queue at the same time.</span></span> <span data-ttu-id="28835-233">默认值为 50, 但范围可以从0到200。</span><span class="sxs-lookup"><span data-stu-id="28835-233">The default is 50, but it can range from 0 to 200.</span></span> <span data-ttu-id="28835-234">达到此限制后，将按照在后面的" **达到最大呼叫次数时**"设置中指定的方式来处理呼叫。</span><span class="sxs-lookup"><span data-stu-id="28835-234">When this limit is reached, the call will be handled in way you have set on the **When the maximum number of calls is reached** setting below.</span></span>

* * *

![数字2的图标, 引用上一个屏幕截图中的标注](media/sfbcallout2.png)

<span data-ttu-id="28835-236">**达到最大通话次数时**当通话队列达到最大值 (使用 **"队列" 设置中的最大通话**设置) 时, 您可以选择新的传入呼叫发生的情况。</span><span class="sxs-lookup"><span data-stu-id="28835-236">**When the maximum number of calls is reached** When the call queue reaches its maximum size (set using the **Maximum calls in the queue** setting), you can choose what happens to new incoming calls.</span></span>

- <span data-ttu-id="28835-237">**断开连接** 呼叫将断开连接。</span><span class="sxs-lookup"><span data-stu-id="28835-237">**Disconnect** The call will be disconnected.</span></span>
- <span data-ttu-id="28835-238">**重定向到**选择此项时, 请选择下列操作之一:</span><span class="sxs-lookup"><span data-stu-id="28835-238">**Redirect to** When you choose this, select one of the following:</span></span>

  - <span data-ttu-id="28835-239">**公司中的人员**具有**电话系统**许可证并启用企业语音或具有呼叫计划的在线用户。</span><span class="sxs-lookup"><span data-stu-id="28835-239">**Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have a Calling Plan.</span></span> <span data-ttu-id="28835-240">你可以通过此设置将呼叫者直接转到语音邮件。</span><span class="sxs-lookup"><span data-stu-id="28835-240">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="28835-241">若要执行此操作, 请选择**您的公司中的人员**, 并将其呼叫直接转发到语音邮件。</span><span class="sxs-lookup"><span data-stu-id="28835-241">To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span>

  <span data-ttu-id="28835-242">若要了解语音邮件所需的许可, 请参阅[设置云语音邮件](set-up-phone-system-voicemail.md)。</span><span class="sxs-lookup"><span data-stu-id="28835-242">To learn about licensing required for voicemail, see [Set up Cloud Voicemail](set-up-phone-system-voicemail.md).</span></span>

  - <span data-ttu-id="28835-243">**语音应用程序**选择已创建的通话队列或自动助理的名称。</span><span class="sxs-lookup"><span data-stu-id="28835-243">**Voice application** Select the name of either a call queue or auto attendant that has already been created.</span></span>

* * *

![数字3的图标, 引用上一个屏幕截图中的标注](media/sfbcallout3.png)

<span data-ttu-id="28835-245">**呼叫超时: 最长等待时间**您还可以决定呼叫在队列中保留多长时间, 并且需要重定向或断开连接。</span><span class="sxs-lookup"><span data-stu-id="28835-245">**Call Timeout: maximum wait time** You can also decide how much time a call can be on hold in the queue before it times out and needs to be redirected or disconnected.</span></span> <span data-ttu-id="28835-246">重新定向的目的地取决于" **当呼叫超时时**"中的设置。</span><span class="sxs-lookup"><span data-stu-id="28835-246">Where it will be redirected is based on how you set the **When a call times out** setting.</span></span> <span data-ttu-id="28835-247">你可以将此时间设置为 0 到 45 分钟。</span><span class="sxs-lookup"><span data-stu-id="28835-247">You can set a time from 0 to 45 minutes.</span></span>

<span data-ttu-id="28835-248">超时值可以以秒为单位按 15 秒间隔进行设置。</span><span class="sxs-lookup"><span data-stu-id="28835-248">The timeout value can be set in seconds, at 15-second intervals.</span></span> <span data-ttu-id="28835-249">这样，你可以以更细的粒度操作呼叫流。</span><span class="sxs-lookup"><span data-stu-id="28835-249">This allows you to manipulate the call flow with finer granularity.</span></span> <span data-ttu-id="28835-250">例如, 您可以指定30秒内代理未接听的任何通话转到目录搜索自动助理。</span><span class="sxs-lookup"><span data-stu-id="28835-250">For example, you could specify that any calls that are not answered by an agent within 30 seconds go to a Directory Search auto attendant.</span></span>

![数字4的图标, 引用上一个屏幕截图中的标注](media/sfbcallout4.png)

<span data-ttu-id="28835-252">**拨出的时间**当呼叫达到您在 "队列" 设置**中呼叫可以等待的时间**限制时, 您可以选择对此呼叫执行的操作:</span><span class="sxs-lookup"><span data-stu-id="28835-252">**When call times out** When the call reaches the limit you set on the **How long a call can wait in the queue** setting, you can choose what happens to this call:</span></span>

- <span data-ttu-id="28835-253">**断开连接** 呼叫将断开连接。</span><span class="sxs-lookup"><span data-stu-id="28835-253">**Disconnect** The call will be disconnected.</span></span>
- <span data-ttu-id="28835-254">**将此呼叫重定向到**如果选择此选项, 将使用以下选项:</span><span class="sxs-lookup"><span data-stu-id="28835-254">**Redirect this call to** When you choose this, you will have these options:</span></span>
  - <span data-ttu-id="28835-255">**公司中的人员**具有**电话系统**许可证并启用企业语音或具有通话计划的在线用户。</span><span class="sxs-lookup"><span data-stu-id="28835-255">**Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have Calling Plans.</span></span> <span data-ttu-id="28835-256">你可以通过此设置将呼叫者直接转到语音邮件。</span><span class="sxs-lookup"><span data-stu-id="28835-256">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="28835-257">若要执行此操作, 请选择**您的公司中的人员**, 并将其呼叫直接转发到语音邮件。</span><span class="sxs-lookup"><span data-stu-id="28835-257">To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span>

  <span data-ttu-id="28835-258">若要了解语音邮件所需的许可, 请参阅[设置云语音邮件](set-up-phone-system-voicemail.md)。</span><span class="sxs-lookup"><span data-stu-id="28835-258">To learn about licensing required for voicemail, see [Set up Cloud Voicemail](set-up-phone-system-voicemail.md).</span></span>

  - <span data-ttu-id="28835-259">**语音应用程序**选择已创建的通话队列或自动助理的名称。</span><span class="sxs-lookup"><span data-stu-id="28835-259">**Voice application** Select the name of either a call queue or auto attendant that has already been created.</span></span>

## <a name="changing-a-users-caller-id-for-outbound-calls"></a><span data-ttu-id="28835-260">更改用于出站呼叫的用户来电显示</span><span class="sxs-lookup"><span data-stu-id="28835-260">Changing a user's Caller ID for outbound calls</span></span> 

<span data-ttu-id="28835-261">你可以通过使用**CsCallingLineIdentity** cmdlet 创建策略来将呼叫者的呼叫方 ID 更改为呼叫队列、自动助理或任何服务号码, 从而保护用户的身份。</span><span class="sxs-lookup"><span data-stu-id="28835-261">You can protect a user's identity by changing their caller ID for outbound calls to a call queue, auto attendant, or any service number instead by creating a policy using the **New-CsCallingLineIdentity** cmdlet.</span></span>

<span data-ttu-id="28835-262">若要执行此操作, 请运行:</span><span class="sxs-lookup"><span data-stu-id="28835-262">To do this, run:</span></span>

``` Powershell
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

<span data-ttu-id="28835-263">然后使用 **Grant-CallingLineIdentity** cmdlet 将策略应用于用户。</span><span class="sxs-lookup"><span data-stu-id="28835-263">Then apply the policy to the user using the **Grant-CallingLineIdentity** cmdlet.</span></span> <span data-ttu-id="28835-264">若要执行此操作, 请运行:</span><span class="sxs-lookup"><span data-stu-id="28835-264">To do this, run:</span></span>
  
``` Powershell
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

<span data-ttu-id="28835-265">有关如何在[组织中使用来电](/microsoftteams/how-can-caller-id-be-used-in-your-organization)显示功能的详细信息, 请了解如何在组织中对呼叫方 id 设置进行更改。</span><span class="sxs-lookup"><span data-stu-id="28835-265">You can get more information on how to make changes to caller ID settings in your organization in the article [How can caller ID be used in your organization](/microsoftteams/how-can-caller-id-be-used-in-your-organization).</span></span>
  
## <a name="want-to-know-more"></a><span data-ttu-id="28835-266">希望了解更多信息吗？</span><span class="sxs-lookup"><span data-stu-id="28835-266">Want to know more?</span></span>

<span data-ttu-id="28835-267">还可以使用 Windows PowerShell 来创建和设置呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="28835-267">You can also use Windows PowerShell to create and set up call queues.</span></span>
  
### <a name="call-queue-cmdlets"></a><span data-ttu-id="28835-268">呼叫队列 cmdlet</span><span class="sxs-lookup"><span data-stu-id="28835-268">Call queue cmdlets</span></span>

<span data-ttu-id="28835-269">以下是管理呼叫队列时需要使用的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="28835-269">Here are the cmdlets that you need to manage a call queue.</span></span>
  
- [<span data-ttu-id="28835-270">新-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="28835-270">New-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="28835-271">Set-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="28835-271">Set-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/set-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="28835-272">CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="28835-272">Get-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/get-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="28835-273">Remove-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="28835-273">Remove-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-CsCallQueue?view=skype-ps)

### <a name="more-about-windows-powershell"></a><span data-ttu-id="28835-274">有关 Windows PowerShell 的详细信息</span><span class="sxs-lookup"><span data-stu-id="28835-274">More about Windows PowerShell</span></span>

- <span data-ttu-id="28835-275">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。</span><span class="sxs-lookup"><span data-stu-id="28835-275">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="28835-276">使用 Windows PowerShell, 你可以使用单一的管理点管理 Office 365 和 Microsoft 团队, 这样你有多个任务需要执行这些任务即可。</span><span class="sxs-lookup"><span data-stu-id="28835-276">With Windows PowerShell, you can manage Office 365 and Microsoft Teams using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="28835-277">若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="28835-277">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="28835-278">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="28835-278">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [<span data-ttu-id="28835-279">为什么要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="28835-279">Why you need to use Office 365 PowerShell</span></span>](https://docs.microsoft.com/en-us/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- <span data-ttu-id="28835-280">Windows PowerShell 在速度、简洁性和效率方面具有许多优势, 仅限于使用 Microsoft 团队管理中心, 例如当你同时为多个用户设置更改时。</span><span class="sxs-lookup"><span data-stu-id="28835-280">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft Teams admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="28835-281">通过以下主题了解这些优势：</span><span class="sxs-lookup"><span data-stu-id="28835-281">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="28835-282">通过 Windows PowerShell 管理 Office 365</span><span class="sxs-lookup"><span data-stu-id="28835-282">Manage Office 365 with Windows PowerShell</span></span>](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [<span data-ttu-id="28835-283">为 Windows PowerShell 设置计算机</span><span class="sxs-lookup"><span data-stu-id="28835-283">Set up your computer for Windows PowerShell</span></span>](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a><span data-ttu-id="28835-284">相关主题</span><span class="sxs-lookup"><span data-stu-id="28835-284">Related topics</span></span>

[<span data-ttu-id="28835-285">以下是 Office 365 中的电话系统功能</span><span class="sxs-lookup"><span data-stu-id="28835-285">Here's what you get with Phone System in Office 365</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="28835-286">获取服务电话号码</span><span class="sxs-lookup"><span data-stu-id="28835-286">Getting service phone numbers</span></span>](getting-service-phone-numbers.md)

[<span data-ttu-id="28835-287">音频会议和通话套餐的国家/地区可用性</span><span class="sxs-lookup"><span data-stu-id="28835-287">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="28835-288">新-CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="28835-288">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
