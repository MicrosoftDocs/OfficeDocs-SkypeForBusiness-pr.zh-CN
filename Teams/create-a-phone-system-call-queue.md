---
title: 创建电话系统呼叫队列
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: phans, wasseemh
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
- Strat_SB_PSTN
- M365-voice
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Learn how to set up phone system for Office 365 (Cloud PBX) call queues to give you an organizational greeting, music on hold, and redirecting calls to call agents in distribution lists and security groups. You can also set the maximum queue size, time out, and call handling options.
ms.openlocfilehash: 59054c1d73e002065db00ff1045ed8453fafa929
ms.sourcegitcommit: 59eda0c17ff39a3e6632810391d78bbadc214419
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/01/2019
ms.locfileid: "30351687"
---
# <a name="create-a-phone-system-call-queue"></a><span data-ttu-id="b2bbd-104">创建电话系统呼叫队列</span><span class="sxs-lookup"><span data-stu-id="b2bbd-104">Create a Phone System call queue</span></span>

<span data-ttu-id="b2bbd-105">队列包括问候语有人呼叫您的组织、 能够自动将呼叫置于保持状态，和搜索处理该呼叫的人员时的下一个可用呼叫代理的功能电话号码时所使用的电话系统呼叫者保留音乐侦听呼叫。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-105">Phone System call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold.</span></span> <span data-ttu-id="b2bbd-106">您可以为组织创建单个或多个呼叫的队列。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-106">You can create single or multiple call queues for your organization.</span></span>
  
<span data-ttu-id="b2bbd-107">电话系统呼叫队列可提供：</span><span class="sxs-lookup"><span data-stu-id="b2bbd-107">Phone System call queues can provide:</span></span>
  
- <span data-ttu-id="b2bbd-108">组织问候语。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-108">An organizational greeting.</span></span>
- <span data-ttu-id="b2bbd-109">在呼叫者保持等待时播放的音乐。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-109">Music while people are waiting on hold.</span></span>
- <span data-ttu-id="b2bbd-110">重定向的呼叫已启用邮件的通讯组列表和安全组中代理的呼叫。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-110">Redirecting of calls to call agents in mail-enabled distribution lists and security groups.</span></span>
- <span data-ttu-id="b2bbd-111">发出呼叫队列最大大小、 超时和呼叫处理选项设置。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-111">Making settings for call queue maximum size, timeout, and call handling options.</span></span>

<span data-ttu-id="b2bbd-112">当有人呼叫到与调用队列通过[资源帐户](manage-resource-accounts.md)相关联的电话号码时，它们将听到问候语 （如果任何设置），然后再它们都将在队列中并等待下一个可用呼叫代理。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-112">When someone calls in to a phone number that is associated  with a call queue via a [resource account](manage-resource-accounts.md), they will hear a greeting first (if any is set up), and then they will be put in the queue and wait for the next available call agent.</span></span> <span data-ttu-id="b2bbd-113">保持等待，它们是和呼叫将拨打给*第一个中，先出*（先进先出） 顺序中的呼叫代理时，呼叫的人将听到保持音乐。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-113">The person calling in will hear music while they are on hold waiting, and the calls will be offered to the call agents in *First In, First Out* (FIFO) order.</span></span>
  
<span data-ttu-id="b2bbd-114">将使用 attendant 的路由模式或串行路由模式分发队列中等待的所有呼叫：</span><span class="sxs-lookup"><span data-stu-id="b2bbd-114">All calls waiting in the queue will be distributed using an attendant routing mode or serial routing mode:</span></span>
  
- <span data-ttu-id="b2bbd-115">助理路由队列中的第一个呼叫将同时拨打所有代理。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-115">With attendant routing, the first call in the queue will ring all agents at the same time.</span></span>
- <span data-ttu-id="b2bbd-116">使用串行路由时，队列中的第一个呼叫将逐个拨打所有呼叫代理。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-116">With serial routing, the first call in the queue will ring all call agents one by one.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b2bbd-117">不会呼叫处于**脱机**状态、已将其状态设置为 **请勿打扰**或已退出呼叫队列的呼叫代理。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-117">Call agents who are **Offline**, have set their presence to **Do not Disturb,** or have opted out of the call queue won't be called.</span></span>
  
- <span data-ttu-id="b2bbd-118">同一时间只会向呼叫代理发送一个传入呼叫通知（队列最前面的呼叫）。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-118">Only one incoming call notification (for the call at the head of the queue) at a time will be sent to the call agents.</span></span>
- <span data-ttu-id="b2bbd-119">呼叫代理接受呼叫后，队列中的下一个传入呼叫开始拨叫所有代理。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-119">After a call agent accepts the call, the next incoming call in the queue will start ringing call agents.</span></span>

> [!NOTE]
> <span data-ttu-id="b2bbd-120">本文同时适用于 Microsoft 团队和 Skype 业务 online。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-120">This article applies to both Microsoft Teams and Skype for Business Online.</span></span>

## <a name="step-1---getting-started"></a><span data-ttu-id="b2bbd-121">第 1 步 - 开始</span><span class="sxs-lookup"><span data-stu-id="b2bbd-121">Step 1 - Getting started</span></span>

<span data-ttu-id="b2bbd-122">要开始使用呼叫队列，记住以下几点至关重要：</span><span class="sxs-lookup"><span data-stu-id="b2bbd-122">To get started using call queues, it's important to remember a few things:</span></span>
  
- <span data-ttu-id="b2bbd-123">企业版 E3 以及**电话系统**的许可证或企业 E5 许可证，您的组织必须 （最低要求）。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-123">Your organization must have (at a minimum) an Enterprise E3 plus **Phone System** license or an Enterprise E5 license.</span></span> <span data-ttu-id="b2bbd-124">已分配的**电话系统**用户许可证数量影响服务号码可用于呼叫的队列数。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-124">The number of **Phone System** user licenses that are assigned affects the number of service numbers that are available to be used for call queues.</span></span> <span data-ttu-id="b2bbd-125">您可以呼叫队列数是取决于您的组织中分配的**电话系统**和**音频会议**的许可证数量。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-125">The number of call queues you can have is dependent on the number of **Phone System** and **Audio Conferencing** licenses that are assigned in your organization.</span></span> <span data-ttu-id="b2bbd-126">若要了解有关授权的详细信息，请参阅[业务和 Microsoft 团队授权加载项的 Skype](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-126">To learn more about licensing, see [Skype for Business and Microsoft Teams add-on licensing](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>

    > [!NOTE]
    > <span data-ttu-id="b2bbd-127">要重定向呼叫的人员在组织中联机，它们必须具有**电话系统**许可证和启用了企业语音或其 Office 365 调用计划。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-127">To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans.</span></span> <span data-ttu-id="b2bbd-128">请参阅[业务和 Microsoft 团队许可证分配 Skype](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-128">See  [Assign Skype for Business and Microsoft Teams licenses](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span> <span data-ttu-id="b2bbd-129">要为他们启用企业语音，可以使用 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-129">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="b2bbd-130">例如运行： `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="b2bbd-130">For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>
  
- <span data-ttu-id="b2bbd-131">若要了解有关 Office 365 通话套餐的详细信息，请参阅 [Office 365 中有哪些通话套餐？](what-are-calling-plans-in-office-365.md) 和 [Office 365 的通话套餐](calling-plans-for-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-131">To learn more about Office 365 Calling Plans, see [What are Calling Plans in Office 365?](what-are-calling-plans-in-office-365.md) and [Calling Plans for Office 365](calling-plans-for-office-365.md).</span></span>

    > [!NOTE]
    > <span data-ttu-id="b2bbd-132">用户托管在本地作为呼叫队列代理不支持使用 Lync Server 2010。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-132">Users hosted on-premises using Lync Server 2010 aren't supported as a call queue Agents.</span></span>
  
- <span data-ttu-id="b2bbd-133">您可以仅分配收费和免费电话服务电话号码的**Microsoft 团队管理中心**中获得或从另一个服务提供商转接到电话系统呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-133">You can only assign toll and toll-free service phone numbers that you got in the **Microsoft Teams admin center** or transferred from another service provider to Phone System call queues.</span></span> <span data-ttu-id="b2bbd-134">若要获取并使用免费电话号码，则需要设置通信点数。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-134">To get and use toll-free service numbers, you need to set up Communications Credits.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b2bbd-135">[!注释] 不能将用户（订阅者）的电话号码分配给呼叫队列 - 只能使用收费或免费服务电话号码。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-135">User (subscriber) phone numbers can't be assigned to call queues - only service toll or toll-free phone numbers can be used.</span></span>
  
- <span data-ttu-id="b2bbd-136">当您要分发从电话系统呼叫队列的传入呼叫时，呼叫代理支持这些客户端：</span><span class="sxs-lookup"><span data-stu-id="b2bbd-136">When you are distributing the incoming calls from an Phone System call queue, these clients are supported for call agents:</span></span>

  - <span data-ttu-id="b2bbd-137">Skype for Business 桌面客户端 2016（32 位和 64 位版本）</span><span class="sxs-lookup"><span data-stu-id="b2bbd-137">Skype for Business desktop client 2016 (32 and 64-bit versions)</span></span>

  - <span data-ttu-id="b2bbd-138">Lync 桌面客户端 2013（32 位和 64 位版本）</span><span class="sxs-lookup"><span data-stu-id="b2bbd-138">Lync desktop client 2013 (32 and 64-bit versions)</span></span>

  - <span data-ttu-id="b2bbd-139">支持的 Microsoft 团队的所有 IP 电话型号。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-139">All IP phone models supported for Microsoft Teams.</span></span> <span data-ttu-id="b2bbd-140">请参阅[获取适用于 Skype for Business Online 的电话](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online.md)。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-140">See [Getting phones for Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online.md).</span></span>

  - <span data-ttu-id="b2bbd-141">Mac Skype for Business 客户端（版本 16.8.196 及更高版本）</span><span class="sxs-lookup"><span data-stu-id="b2bbd-141">Mac Skype for Business Client (version 16.8.196 and later)</span></span>

  - <span data-ttu-id="b2bbd-142">Android Skype for Business 客户端（版本 6.16.0.9 及更高版本）</span><span class="sxs-lookup"><span data-stu-id="b2bbd-142">Android Skype for Business Client (version 6.16.0.9 and later)</span></span>

  - <span data-ttu-id="b2bbd-143">iPhone Skype for Business 客户端（版本 6.16.0 及更高版本）</span><span class="sxs-lookup"><span data-stu-id="b2bbd-143">iPhone Skype for Business Client (version 6.16.0 and later)</span></span>

  - <span data-ttu-id="b2bbd-144">iPad Skype for Business 客户端（版本 6.16.0 及更高版本）</span><span class="sxs-lookup"><span data-stu-id="b2bbd-144">iPad Skype for Business Client (version 6.16.0 and later)</span></span>

  - <span data-ttu-id="b2bbd-145">Microsoft Teams Windows 客户端 （32 和 64 位版本）</span><span class="sxs-lookup"><span data-stu-id="b2bbd-145">Microsoft Teams Windows client (32 and 64-bit versions)</span></span>

  - <span data-ttu-id="b2bbd-146">Microsoft Teams Mac 客户端</span><span class="sxs-lookup"><span data-stu-id="b2bbd-146">Microsoft Teams Mac client</span></span>

  - <span data-ttu-id="b2bbd-147">Microsoft Teams iPhone 应用</span><span class="sxs-lookup"><span data-stu-id="b2bbd-147">Microsoft Teams iPhone app</span></span>

  - <span data-ttu-id="b2bbd-148">Microsoft Teams Android 应用</span><span class="sxs-lookup"><span data-stu-id="b2bbd-148">Microsoft Teams Android app</span></span>

## <a name="step-2---getting-or-transferring-toll-or-toll-free-service-phone-numbers"></a><span data-ttu-id="b2bbd-149">第 2 步 - 获取或转移收费或免费服务电话号码</span><span class="sxs-lookup"><span data-stu-id="b2bbd-149">Step 2 - Getting or transferring toll or toll-free service phone numbers</span></span>

<span data-ttu-id="b2bbd-150">在创建和设置呼叫队列之前，您需要获取或转移现有的收费或免费服务号码。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-150">Before you can create and set up your call queues, you will need to get or transfer your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="b2bbd-151">获得收费电话或免费电话服务电话号码后，他们会显示在**Microsoft 团队管理中心** > **语音** > **电话号码**，以及被列为**Service-免费电话\*\*\*\*号码类型**列出将。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-151">After you get the toll or toll-free service phone numbers, they will show up in **Microsoft Teams admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**.</span></span> <span data-ttu-id="b2bbd-152">若要获取服务号码，请参阅[Getting 服务电话号码](/skypeforbusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers.md)或如果您想要传输的现有服务号码，请参阅[传输到 Office 365 的电话号码](transfer-phone-numbers-to-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-152">To get your service numbers, see [Getting service phone numbers](/skypeforbusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers.md) or if you want to transfer an existing service number, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="b2bbd-153">如果您在美国以外，您无法使用的 Microsoft 团队管理中心获取服务号码。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-153">If you are outside the United States, you can't use the Microsoft Teams admin center to get service numbers.</span></span> <span data-ttu-id="b2bbd-154">转到[管理您的组织的电话号码](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)而是以了解如何执行从美国的外部。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-154">Go to [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) instead to see how to do it from the outside of the United States.</span></span>

<span data-ttu-id="b2bbd-155">如果您要设置自动助理，您可能只需要将电话号码分配给主自动助理的资源帐户，并使其直接主叫方到呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-155">If you are also setting up auto attendants, you may only need to assign a phone number to the main auto attendant's resource account, and then have it direct callers to your call queue.</span></span> <span data-ttu-id="b2bbd-156">如果是这样，需要之前可以创建一个选项中选择呼叫队列的自动助理创建呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-156">If that's the case, the call queue will need to be created before you can create an option in the auto attendant that selects the call queue.</span></span>
  
## <a name="step-3---create-a-new-call-queue"></a><span data-ttu-id="b2bbd-157">步骤 3-创建新的呼叫队列</span><span class="sxs-lookup"><span data-stu-id="b2bbd-157">Step 3 - Create a new call queue</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b2bbd-158">每个呼叫队列需要具有关联的[资源帐户](manage-resource-accounts.md)。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-158">Every call queue is required to have an associated [resource account](manage-resource-accounts.md).</span></span> <span data-ttu-id="b2bbd-159">您必须首先，创建资源帐户，然后将其至呼叫的队列相关联。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-159">You must create the resource account first, then you can associate it to the call queue.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="b2bbd-160">使用 Microsoft 团队管理中心</span><span class="sxs-lookup"><span data-stu-id="b2bbd-160">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="b2bbd-161">在**Microsoft 团队管理中心**，**语音** >  **呼叫队列**，然后单击 **+ 添加新**：</span><span class="sxs-lookup"><span data-stu-id="b2bbd-161">In the **Microsoft Teams admin center**, **Voice** >  **Call queues**, then click **+ Add new**:</span></span>

### <a name="set-the-call-queue-display-name-and-resource-account"></a><span data-ttu-id="b2bbd-162">设置呼叫的队列显示名称和资源帐户</span><span class="sxs-lookup"><span data-stu-id="b2bbd-162">Set the call queue display name and resource account</span></span>

![Setting up a call queue.](media/37ecc300-a108-4294-8463-fce570dfce72.png)

* * *

<span data-ttu-id="b2bbd-164">![1 号](media/sfbcallout1.png)
**名称**输入呼叫队列的描述性的显示名称。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-164">![Number 1](media/sfbcallout1.png)
**Name** Enter a descriptive display name for the call queue.</span></span> <span data-ttu-id="b2bbd-165">此为必填字段，最多可以包含 64 个字符，其中包括空格。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-165">This is required and can contain up to 64 characters, including spaces.</span></span>

 <span data-ttu-id="b2bbd-166">此名称将显示在传入呼叫的通知中。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-166">This name will be displayed in the notification for the incoming call.</span></span>

* * *

![第二](media/sfbcallout2.png)

<span data-ttu-id="b2bbd-168">**添加帐户**选择一个资源帐户。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-168">**Add Accounts** Select a resource account.</span></span> <span data-ttu-id="b2bbd-169">资源帐户可能也可能不与服务收费电话或免费电话号码呼叫队列，但每个呼叫队列需要关联的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-169">The resource account may or may not be associated with a service toll or toll-free phone number for the call queue, but each call queue requires an associated resource account.</span></span>

<span data-ttu-id="b2bbd-170">如果没有任何列出，您需要获取服务号码并将其分配给资源帐户才能创建此呼叫队列，如前面所述。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-170">If there aren't any listed, you need to get service numbers and assign them to a Resource account before you can create this call queue, as described earlier.</span></span> <span data-ttu-id="b2bbd-171">若要获取服务号码，请参阅[Getting 服务电话号码](/skypeforbusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers.md)。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-171">To get your service numbers, see [Getting service phone numbers](/skypeforbusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers.md).</span></span> <span data-ttu-id="b2bbd-172">您需要创建资源帐户中所述[在团队中的管理资源帐户](manage-resource-accounts.md)如果您希望您呼叫的队列具有关联的电话号码。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-172">You'll need to create a resource account as described in [Manage resource accounts in Teams](manage-resource-accounts.md) if you want your call queue to have an associated phone number.</span></span>

> [!NOTE]
> <span data-ttu-id="b2bbd-173">如果您希望或需要分配**域**可以执行，将它分配给呼叫队列的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-173">If you want or need to assign a **Domain** you would do so by assigning it to the resource account for the call queue.</span></span>

### <a name="set-the-greeting-and-music-played-while-on-hold"></a><span data-ttu-id="b2bbd-174">设置通话保持时播放的问候语和音乐</span><span class="sxs-lookup"><span data-stu-id="b2bbd-174">Set the greeting and music played while on hold</span></span>

![Setting up a call queue.](media/1d395a93-7cab-4178-9295-12d5379e20de.png)
  
* * *

![第一](media/sfbcallout1.png)

<span data-ttu-id="b2bbd-177">**问候语**是可选设置。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-177">**Greeting** is optional.</span></span> <span data-ttu-id="b2bbd-178">这是呼叫队列号码的呼叫中的人员播放问候语。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-178">This is the greeting that is played for people who call in to the call queue number.</span></span>

<span data-ttu-id="b2bbd-179">您可以上载音频文件 （.wav、.mp3 或.wma 格式）。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-179">You can upload an audio file (.wav, .mp3, or .wma formats).</span></span>

![第二](media/sfbcallout2.png)

<span data-ttu-id="b2bbd-181">**音乐**您可以使用默认保持音乐置于保持状态提供与呼叫队列，或者可以上载.wav、 mp3 或.wma 格式用作您自定义保留音乐音频文件。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-181">**Music on hold** You can either use the default Music on Hold provided with the call queue, or you can upload an audio file in .wav, mp3, or .wma formats to use as your custom Music on Hold.</span></span>

* * *

### <a name="select-the-call-answering-options"></a><span data-ttu-id="b2bbd-182">选择呼叫应答选项</span><span class="sxs-lookup"><span data-stu-id="b2bbd-182">Select the call answering options</span></span>

![显示呼叫分发方法选项](media/5d249515-d532-4af2-90da-011404028b89.png)

![第一](media/sfbcallout1.png)

<span data-ttu-id="b2bbd-185">您可以选择最多 200 属于指定的邮件列表或组的呼叫代理。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-185">You can select up to 200 call agents belonging to specified mailing lists or groups.</span></span> <span data-ttu-id="b2bbd-186">呼叫代理必须是：</span><span class="sxs-lookup"><span data-stu-id="b2bbd-186">Call agents must be either:</span></span>

- <span data-ttu-id="b2bbd-187">拥有**电话系统**许可证和启用了企业语音或拥有通话套餐的在线用户。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-187">An Online user with a **Phone System** license and enabled for Enterprise Voice or with a Calling Plan.</span></span>

  > [!NOTE]
  > <span data-ttu-id="b2bbd-188">要重定向呼叫的人员在组织中联机，它们必须具有**电话系统**许可证和启用了企业语音或其调用规划。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-188">To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have a Calling Plan.</span></span> <span data-ttu-id="b2bbd-189">请参阅[业务和 Microsoft 团队许可证分配 Skype](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-189">See [Assign Skype for Business and Microsoft Teams licenses](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>

 <span data-ttu-id="b2bbd-190">要为他们启用企业语音，可以使用 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-190">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="b2bbd-191">例如运行： `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="b2bbd-191">For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

- <span data-ttu-id="b2bbd-192">拥有**电话系统**许可证和通话套餐（已添加到 Office 365 组、已启用邮件的通讯组列表或安全组）的在线用户。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-192">Online users with a **Phone System** license and a Calling Plan that are added to an Office 365 Group, a mail-enabled Distribution List, or a Security Group.</span></span> <span data-ttu-id="b2bbd-193">为通讯组列表或安全组添加一位新代理，以便开始接收来自呼叫队列的呼叫，这可能需要 30 分钟的时间。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-193">It might take up to 30 minutes for a new agent added for a distribution list or a security group to start receiving calls from a call queue.</span></span> <span data-ttu-id="b2bbd-194">新建通讯组列表或安全组可能需要长达 48 小时成为可用于呼叫的队列。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-194">A newly created distribution list or security group might take up to 48 hours to become available to be used with call queues.</span></span> <span data-ttu-id="b2bbd-195">新创建的 Office 365 组几乎立即就可使用。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-195">Newly created Office 365 Groups are available almost immediately.</span></span>

  > [!NOTE]
  > <span data-ttu-id="b2bbd-196">用户托管在本地不支持使用 Lync Server 2010。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-196">Users hosted on-premises using Lync Server 2010 aren't supported.</span></span>

![Set up call queues.](media/skype-for-business-add-agents-to-call-queue.png)

![第二](media/sfbcallout2.png)

<span data-ttu-id="b2bbd-199">**路由方法**呼叫队列分发方法，可以选择**Attendant**、**串行**、 或**轮循机制**。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-199">**Routing method** You can choose either **Attendant**,  **Serial**, or **Round Robin** for your call queue distribution method.</span></span> <span data-ttu-id="b2bbd-200">所有新的和现有呼叫队列将具有默认情况下选中的助理路由。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-200">All new and existing call queues will have attendant routing selected by default.</span></span> <span data-ttu-id="b2bbd-201">使用助理路由时，在队列中的第一个呼叫将拨打的所有呼叫代理在同一时间。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-201">When attendant routing is used, the first call in the queue will ring all of the call agents at the same time.</span></span> <span data-ttu-id="b2bbd-202">若要选取呼叫的第一个呼叫代理获取呼叫。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-202">The first call agent to pick up the call gets the call.</span></span>

- <span data-ttu-id="b2bbd-203">**助理路由**使要同时拨打所有呼叫代理的队列中的第一个呼叫。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-203">**Attendant routing** causes the first call in the queue to ring all call agents at the same time.</span></span> <span data-ttu-id="b2bbd-204">若要选取呼叫的第一个呼叫代理获取呼叫。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-204">The first call agent to pick up the call gets the call.</span></span>
- <span data-ttu-id="b2bbd-205">**串行路由**使传入呼叫拨打呼叫代理，逐个的开始处的呼叫代理列表。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-205">**Serial routing** causes incoming calls to ring call agents one by one, starting from the beginning of the call agent list.</span></span> <span data-ttu-id="b2bbd-206">如果代理挂断或不接听电话，电话将打给列表的下一位代理，并将尝试逐个拨打所有代理，直到有人接听或队列等待超时为止。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-206">If an agent dismisses or does not pick up a call, the call will ring the next agent on the list and will try all agents one by one until it is picked up or times out waiting in the queue.</span></span>
  > [!NOTE]
  > <span data-ttu-id="b2bbd-207">串行路由将跳过处于**脱机**状态、已将其状态设置为 **请勿打扰**或**已选择退出**不从此队列获取呼叫的代理。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-207">Serial routing will skip agents who are **Offline**, have set their presence to **Do not Disturb**, or have **opted out** of getting calls from this queue.</span></span>
- <span data-ttu-id="b2bbd-208">使每个呼叫代理将获得相同的呼叫数从队列路由的传入呼叫的负载平衡**循环**。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-208">**Round robin** balances routing of incoming calls so that each call agent will get the same number of calls from the queue.</span></span> <span data-ttu-id="b2bbd-209">这可能是非常可取中的入站的销售环境，以确保所有呼叫代理之间的等于机会。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-209">This may be very desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

### <a name="select-an-agent-opt-out-option"></a><span data-ttu-id="b2bbd-210">选择代理退出选项</span><span class="sxs-lookup"><span data-stu-id="b2bbd-210">Select an agent opt out option</span></span>

![显示代理退出复选框](media/99279eff-db61-4acf-9b62-64be84b6414b.png)
  
* * *

![第一](media/sfbcallout1.png)

<span data-ttu-id="b2bbd-213">**代理退出选项**你可以选择允许呼叫队列代理通过选择**代理退出选项**，不接收来自特定队列的呼叫。
。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-213">**Agent Opt out option** You can choose to allow call queue agents to opt out of taking calls from a particular queue by selecting **Agent Opt out option**.</span></span>

<span data-ttu-id="b2bbd-214">启用此选项允许将在此队列中的所有代理启动或停止在此呼叫队列接收呼叫。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-214">Enabling this option allows all agents in this queue to start or stop receiving calls from this call queue at will.</span></span> <span data-ttu-id="b2bbd-215">通过清除此复选框，你可以随时撤消代理选择退出特权，这将导致所有代理自动选择再加入此队列 （所有代理的默认设置）。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-215">You can revoke the agent opt-out privilege at any time by clearing the check box, causing agents to become automatically opted in for this queue again (the default setting for all agents).</span></span>

<span data-ttu-id="b2bbd-216">若要访问选择退出选项，代理可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b2bbd-216">To access the opt-out option, agents can do the following:</span></span>

 1. <span data-ttu-id="b2bbd-217">在其桌面 Skype for Business 客户端中打开**选项**。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-217">Open **Options** in their desktop Skype for Business client.</span></span>
 2. <span data-ttu-id="b2bbd-218">在**呼叫转移**选项卡中，单击**在线编辑设置**链接。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-218">On the **Call Forwarding** tab, click the **Edit settings online** link.</span></span>
 3. <span data-ttu-id="b2bbd-219">在用户设置页中，单击**呼叫队列**，然后清除他们想要退出的任何队列对应的复选框。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-219">On the user settings page, click **Call Queues**, and then clear the check boxes for any queues for which they want to opt out.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b2bbd-220">使用 Mac、移动、Lync 2013 客户端的代理，或使用 Skype for Business 2015 服务器托管在本地的混合语音用户，可转到[https://aka.ms/cqsettings](https://aka.ms/cqsettings) 访问退出选项。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-220">Agents using Mac, mobile, or Lync 2013 clients, or Hybrid Voice users who are hosted on-premises using Skype for Business 2015 server, can go to [https://aka.ms/cqsettings](https://aka.ms/cqsettings) to access the opt out option.</span></span>

<span data-ttu-id="b2bbd-221">![2 号](media/sfbcallout2.png)
**代理警报设置**</span><span class="sxs-lookup"><span data-stu-id="b2bbd-221">![Number 2](media/sfbcallout2.png)
**Agent Alert setting**</span></span>

<span data-ttu-id="b2bbd-222">这定义的调用序列之前收到通知代理的持续时间或循环路由方法将移至下一个代理。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-222">This defines the duration of an agent being notified of a call before the Serial or Round Robin routing methods move to the next agent.</span></span>

<span data-ttu-id="b2bbd-223">默认设置为 30 秒，但为最多为 3 分钟。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-223">The default setting is 30 seconds, but it can be set for up to 3 minutes.</span></span>

* * *

### <a name="set-the-call-overflow-and-timeout-handling-options"></a><span data-ttu-id="b2bbd-224">设置呼叫溢出和超时处理选项</span><span class="sxs-lookup"><span data-stu-id="b2bbd-224">Set the call overflow and timeout handling options</span></span>

![Set up a call queue.](media/3f018734-16fe-458b-827d-71fc25155cde.png)
  
* * *

![第一](media/sfbcallout1.png)

<span data-ttu-id="b2bbd-227">**队列中的最大呼叫数** 使用此字段来设置同一时间可以在队列中等待的最大呼叫数。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-227">**Maximum calls in the queue** Use this to set the maximum calls that can wait in the queue at the same time.</span></span> <span data-ttu-id="b2bbd-228">默认值为 50，但它可以介于 0 到 200。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-228">The default is 50, but it can range from 0 to 200.</span></span> <span data-ttu-id="b2bbd-229">达到此限制后，将按照在后面的" **达到最大呼叫次数时**"设置中指定的方式来处理呼叫。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-229">When this limit is reached, the call will be handled in way you have set on the **When the maximum number of calls is reached** setting below.</span></span>

* * *

![第二](media/sfbcallout2.png)

<span data-ttu-id="b2bbd-231">**当达到的最大呼叫数**当呼叫队列达到其最大大小 （设置使用的**队列中的最大呼叫**设置） 时，您可以选择新的传入呼叫会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-231">**When the maximum number of calls is reached** When the call queue reaches its maximum size (set using the **Maximum calls in the queue** setting), you can choose what happens to new incoming calls.</span></span>

- <span data-ttu-id="b2bbd-232">**断开连接** 呼叫将断开连接。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-232">**Disconnect** The call will be disconnected.</span></span>
- <span data-ttu-id="b2bbd-233">**重定向到**当选择此操作时，选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="b2bbd-233">**Redirect to** When you choose this, select one of the following:</span></span>

  - <span data-ttu-id="b2bbd-234">**公司内的人员**与**电话系统**许可证联机用户和启用了企业语音或其调用规划。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-234">**Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have a Calling Plan.</span></span> <span data-ttu-id="b2bbd-235">你可以通过此设置将呼叫者直接转到语音邮件。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-235">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="b2bbd-236">要执行此操作，选择**您的公司的人员**，并设置此人要使其呼叫直接转接到语音邮件。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-236">To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span>

  <span data-ttu-id="b2bbd-237">若要了解有关语音邮件所需授权的信息，请参阅[设置电话系统的语音邮件](set-up-phone-system-voicemail.md)。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-237">To learn about licensing required for voicemail, see [Set up Phone System voicemail](set-up-phone-system-voicemail.md).</span></span>

    > [!Note]
    > <span data-ttu-id="b2bbd-238">用户托管在本地不支持使用 Lync Server 2010。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-238">Users hosted on-premises using Lync Server 2010 aren't supported.</span></span>
  - <span data-ttu-id="b2bbd-239">**语音应用程序**选择呼叫队列的之一的名称或自动助理已创建。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-239">**Voice application** Select the name of either a call queue or auto attendant that has already been created.</span></span>

* * *

![第三](media/sfbcallout3.png)

<span data-ttu-id="b2bbd-241">**呼叫超时： 最长等待时间**您还可以决定呼叫多长时间可以保持在队列中之前超时和需要重定向或断开连接。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-241">**Call Timeout: maximum wait time** You can also decide how much time a call can be on hold in the queue before it times out and needs to be redirected or disconnected.</span></span> <span data-ttu-id="b2bbd-242">重新定向的目的地取决于" **当呼叫超时时**"中的设置。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-242">Where it will be redirected is based on how you set the **When a call times out** setting.</span></span> <span data-ttu-id="b2bbd-243">你可以将此时间设置为 0 到 45 分钟。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-243">You can set a time from 0 to 45 minutes.</span></span>

<span data-ttu-id="b2bbd-244">超时值可以以秒为单位按 15 秒间隔进行设置。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-244">The timeout value can be set in seconds, at 15-second intervals.</span></span> <span data-ttu-id="b2bbd-245">这样，你可以以更细的粒度操作呼叫流。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-245">This allows you to manipulate the call flow with finer granularity.</span></span> <span data-ttu-id="b2bbd-246">例如，您可以指定在 30 秒内不被代理应答任何呼叫转到目录搜索自动助理。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-246">For example, you could specify that any calls that are not answered by an agent within 30 seconds go to a Directory Search auto attendant.</span></span>

![第四](media/sfbcallout4.png)

<span data-ttu-id="b2bbd-248">**呼叫超时时**当呼叫到达设置的**长呼叫可以在队列中等待**的设置的限制后时，您可以选择此呼叫时会发生什么情况：</span><span class="sxs-lookup"><span data-stu-id="b2bbd-248">**When call times out** When the call reaches the limit you set on the **How long a call can wait in the queue** setting, you can choose what happens to this call:</span></span>

- <span data-ttu-id="b2bbd-249">**断开连接** 呼叫将断开连接。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-249">**Disconnect** The call will be disconnected.</span></span>
- <span data-ttu-id="b2bbd-250">**重定向到此呼叫**选择此，您可以在这些选项：</span><span class="sxs-lookup"><span data-stu-id="b2bbd-250">**Redirect this call to** When you choose this, you will have these options:</span></span>
  - <span data-ttu-id="b2bbd-251">**公司内的人员**与**电话系统**许可证联机用户和启用了企业语音或其调用计划。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-251">**Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have Calling Plans.</span></span> <span data-ttu-id="b2bbd-252">你可以通过此设置将呼叫者直接转到语音邮件。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-252">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="b2bbd-253">要执行此操作，选择**您的公司的人员**，并设置此人要使其呼叫直接转接到语音邮件。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-253">To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span>

  <span data-ttu-id="b2bbd-254">若要了解有关语音邮件所需授权的信息，请参阅[设置电话系统的语音邮件](set-up-phone-system-voicemail.md)。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-254">To learn about licensing required for voicemail, see [Set up Phone System voicemail](set-up-phone-system-voicemail.md).</span></span>

    > [!Note]
    > <span data-ttu-id="b2bbd-255">用户托管在本地不支持使用 Lync Server 2010。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-255">Users hosted on-premises using Lync Server 2010 aren't supported.</span></span>

  - <span data-ttu-id="b2bbd-256">**语音应用程序**选择呼叫队列的之一的名称或自动助理已创建。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-256">**Voice application** Select the name of either a call queue or auto attendant that has already been created.</span></span>

## <a name="changing-a-users-caller-id-to-be-a-call-queues-phone-number"></a><span data-ttu-id="b2bbd-257">更改用户的呼叫者 ID，可调用队列的电话号码</span><span class="sxs-lookup"><span data-stu-id="b2bbd-257">Changing a user's Caller ID to be a call queue's phone number</span></span>

<span data-ttu-id="b2bbd-258">通过使用**新建 CallingLineIdentity** cmdlet 创建策略，可将出站呼叫的来电显示更改为呼叫队列，从而保护用户的身份。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-258">You can protect a user's identity by changing their caller ID for the outbound calls to a call queue instead by creating a policy using the **New-CallingLineIdentity** cmdlet.</span></span>

<span data-ttu-id="b2bbd-259">若要执行此操作，请运行：</span><span class="sxs-lookup"><span data-stu-id="b2bbd-259">To do this, run:</span></span>

``` Powershell
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

<span data-ttu-id="b2bbd-260">然后使用 **Grant-CallingLineIdentity** cmdlet 将策略应用于用户。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-260">Then apply the policy to the user using the **Grant-CallingLineIdentity** cmdlet.</span></span> <span data-ttu-id="b2bbd-261">若要执行此操作，请运行：</span><span class="sxs-lookup"><span data-stu-id="b2bbd-261">To do this, run:</span></span>
  
``` Powershell
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

<span data-ttu-id="b2bbd-262">您可以获取有关如何对您[如何可以呼叫者 ID 是您组织中使用](/skypeforbusiness/what-are-calling-plans-in-office-365/how-can-caller-id-be-used-in-your-organization.md)一文中的组织中的呼叫者 ID 设置进行更改的详细信息。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-262">You can get more information on how to make changes to caller ID settings in your organization in the article [How can caller ID be used in your organization](/skypeforbusiness/what-are-calling-plans-in-office-365/how-can-caller-id-be-used-in-your-organization.md).</span></span>
  
## <a name="want-to-know-more"></a><span data-ttu-id="b2bbd-263">希望了解更多信息吗？</span><span class="sxs-lookup"><span data-stu-id="b2bbd-263">Want to know more?</span></span>

<span data-ttu-id="b2bbd-264">还可以使用 Windows PowerShell 来创建和设置呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-264">You can also use Windows PowerShell to create and set up call queues.</span></span>
  
### <a name="call-queue-cmdlets"></a><span data-ttu-id="b2bbd-265">呼叫队列 cmdlet</span><span class="sxs-lookup"><span data-stu-id="b2bbd-265">Call queue cmdlets</span></span>

<span data-ttu-id="b2bbd-266">以下是管理呼叫队列时需要使用的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-266">Here are the cmdlets that you need to manage a call queue.</span></span>
  
- [<span data-ttu-id="b2bbd-267">New-CsHuntgroup</span><span class="sxs-lookup"><span data-stu-id="b2bbd-267">New-CsHuntgroup</span></span>](https://technet.microsoft.com/en-us/library/mt796459.aspx)

- [<span data-ttu-id="b2bbd-268">Set-CsHuntgroup</span><span class="sxs-lookup"><span data-stu-id="b2bbd-268">Set-CsHuntgroup</span></span>](https://technet.microsoft.com/en-us/library/mt796457.aspx)

- [<span data-ttu-id="b2bbd-269">Get-CsHuntgroup</span><span class="sxs-lookup"><span data-stu-id="b2bbd-269">Get-CsHuntgroup</span></span>](https://technet.microsoft.com/en-us/library/mt796458.aspx)

- [<span data-ttu-id="b2bbd-270">Remove-CsHuntgroup</span><span class="sxs-lookup"><span data-stu-id="b2bbd-270">Remove-CsHuntgroup</span></span>](https://technet.microsoft.com/en-us/library/mt796456.aspx)

### <a name="more-about-windows-powershell"></a><span data-ttu-id="b2bbd-271">有关 Windows PowerShell 的详细信息</span><span class="sxs-lookup"><span data-stu-id="b2bbd-271">More about Windows PowerShell</span></span>

- <span data-ttu-id="b2bbd-272">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-272">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="b2bbd-273">使用 Windows PowerShell，您可以管理 Office 365 和 Microsoft 团队使用单点管理，可以简化您的日常工作，如果您有多个要执行的任务。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-273">With Windows PowerShell, you can manage Office 365 and Microsoft Teams using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="b2bbd-274">若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="b2bbd-274">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="b2bbd-275">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="b2bbd-275">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [<span data-ttu-id="b2bbd-276">为什么要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="b2bbd-276">Why you need to use Office 365 PowerShell</span></span>](https://docs.microsoft.com/en-us/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- <span data-ttu-id="b2bbd-277">Windows PowerShell 具有很多好处中快速、 简便起见和生产力通过仅使用在 Microsoft 团队管理中心内，如时要进行设置更改多个用户一次。</span><span class="sxs-lookup"><span data-stu-id="b2bbd-277">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft Teams admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="b2bbd-278">通过以下主题了解这些优势：</span><span class="sxs-lookup"><span data-stu-id="b2bbd-278">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="b2bbd-279">管理 Office 365 使用 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b2bbd-279">Manage Office 365 with Windows PowerShell</span></span>](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [<span data-ttu-id="b2bbd-280">为 Windows PowerShell 设置计算机</span><span class="sxs-lookup"><span data-stu-id="b2bbd-280">Set up your computer for Windows PowerShell</span></span>](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a><span data-ttu-id="b2bbd-281">相关主题</span><span class="sxs-lookup"><span data-stu-id="b2bbd-281">Related topics</span></span>

[<span data-ttu-id="b2bbd-282">以下是 Office 365 中的电话系统功能</span><span class="sxs-lookup"><span data-stu-id="b2bbd-282">Here's what you get with Phone System in Office 365</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="b2bbd-283">获取服务电话号码</span><span class="sxs-lookup"><span data-stu-id="b2bbd-283">Getting service phone numbers</span></span>](/Skypeforbusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers.md)

[<span data-ttu-id="b2bbd-284">音频会议和通话套餐的国家/地区可用性</span><span class="sxs-lookup"><span data-stu-id="b2bbd-284">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="b2bbd-285">新 CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="b2bbd-285">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
