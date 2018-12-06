---
title: 创建电话系统呼叫队列
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: phans, wasseemh
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 'Learn how to set up phone system for Office 365 (Cloud PBX) call queues to give you an organizational greeting, music on hold, and redirecting calls to call agents in distribution lists and security groups. You can also set the maximum queue size, time out, and call handling options. '
ms.openlocfilehash: ec3cbc89a0a8ab07d7936d604d1f38a5d99ed2b6
ms.sourcegitcommit: 969a71ef0ac0030c27bd2455c3bf9d536dbcd752
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/06/2018
ms.locfileid: "27182390"
---
# <a name="create-a-phone-system-call-queue"></a><span data-ttu-id="529aa-104">创建电话系统呼叫队列</span><span class="sxs-lookup"><span data-stu-id="529aa-104">Create a Phone System call queue</span></span>

<span data-ttu-id="529aa-105">队列包括问候语有人呼叫您的组织、 能够自动将呼叫置于保持状态，和搜索处理该呼叫的人员时的下一个可用呼叫代理的功能电话号码时所使用的电话系统呼叫者保留音乐侦听呼叫。</span><span class="sxs-lookup"><span data-stu-id="529aa-105">Phone System call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold.</span></span> <span data-ttu-id="529aa-106">您可以为组织创建单个或多个呼叫的队列。</span><span class="sxs-lookup"><span data-stu-id="529aa-106">You can create single or multiple call queues for your organization.</span></span>
  
<span data-ttu-id="529aa-107">电话系统呼叫队列可提供：</span><span class="sxs-lookup"><span data-stu-id="529aa-107">Phone System call queues can provide:</span></span>
  
- <span data-ttu-id="529aa-108">组织问候语。</span><span class="sxs-lookup"><span data-stu-id="529aa-108">An organizational greeting.</span></span>
- <span data-ttu-id="529aa-109">在呼叫者保持等待时播放的音乐。</span><span class="sxs-lookup"><span data-stu-id="529aa-109">Music while people are waiting on hold.</span></span>
- <span data-ttu-id="529aa-110">重定向的呼叫已启用邮件的通讯组列表和安全组中代理的呼叫。</span><span class="sxs-lookup"><span data-stu-id="529aa-110">Redirecting of calls to call agents in mail-enabled distribution lists and security groups.</span></span>
- <span data-ttu-id="529aa-111">发出呼叫队列最大大小、 超时和呼叫处理选项设置。</span><span class="sxs-lookup"><span data-stu-id="529aa-111">Making settings for call queue maximum size, timeout, and call handling options.</span></span>

<span data-ttu-id="529aa-112">当有人呼叫到电话号码的呼叫的队列设置时，它们将听到问候语 （如果任何设置），然后再它们都将在队列中并等待下一个可用呼叫代理。</span><span class="sxs-lookup"><span data-stu-id="529aa-112">When someone calls in to a phone number that is set up with a call queue, they will hear a greeting first (if any is set up), and then they will be put in the queue and wait for the next available call agent.</span></span> <span data-ttu-id="529aa-113">呼叫者在等待时会听到音乐，系统将按照 *先进先出*  (FIFO) 的方式为呼叫分配呼叫代理。</span><span class="sxs-lookup"><span data-stu-id="529aa-113">The person calling in will hear music while they are on hold waiting, and the calls will be offered to the call agents in the  *First In, First Out*  (FIFO) manner.</span></span>
  
<span data-ttu-id="529aa-114">将使用 attendant 的路由模式或串行路由模式分发队列中等待的所有呼叫：</span><span class="sxs-lookup"><span data-stu-id="529aa-114">All calls waiting in the queue will be distributed using an attendant routing mode or serial routing mode:</span></span>
  
- <span data-ttu-id="529aa-115">助理路由队列中的第一个呼叫将同时拨打所有代理。</span><span class="sxs-lookup"><span data-stu-id="529aa-115">With attendant routing, the first call in the queue will ring all agents at the same time.</span></span>
- <span data-ttu-id="529aa-116">使用串行路由时，队列中的第一个呼叫将逐个拨打所有呼叫代理。</span><span class="sxs-lookup"><span data-stu-id="529aa-116">With serial routing, the first call in the queue will ring all call agents one by one.</span></span>

    > [!NOTE]
    > <span data-ttu-id="529aa-117">不会呼叫处于**脱机**状态、已将其状态设置为 **请勿打扰**或已退出呼叫队列的呼叫代理。</span><span class="sxs-lookup"><span data-stu-id="529aa-117">Call agents who are **Offline**, have set their presence to **Do not Disturb,** or have opted out of the call queue won't be called.</span></span>
  
- <span data-ttu-id="529aa-118">同一时间只会向呼叫代理发送一个传入呼叫通知（队列最前面的呼叫）。</span><span class="sxs-lookup"><span data-stu-id="529aa-118">Only one incoming call notification (for the call at the head of the queue) at a time will be sent to the call agents.</span></span>
- <span data-ttu-id="529aa-119">呼叫代理接受呼叫后，队列中的下一个传入呼叫开始拨叫所有代理。</span><span class="sxs-lookup"><span data-stu-id="529aa-119">After a call agent accepts the call, the next incoming call in the queue will start ringing call agents.</span></span>

## <a name="step-1---getting-started"></a><span data-ttu-id="529aa-120">第 1 步 - 开始</span><span class="sxs-lookup"><span data-stu-id="529aa-120">Step 1 - Getting started</span></span>

<span data-ttu-id="529aa-121">要开始使用呼叫队列，记住以下几点至关重要：</span><span class="sxs-lookup"><span data-stu-id="529aa-121">To get started using call queues, it's important to remember a few things:</span></span>
  
- <span data-ttu-id="529aa-122">企业版 E3 以及**电话系统**的许可证或企业 E5 许可证，您的组织必须 （最低要求）。</span><span class="sxs-lookup"><span data-stu-id="529aa-122">Your organization must have (at a minimum) an Enterprise E3 plus **Phone System** license or an Enterprise E5 license.</span></span> <span data-ttu-id="529aa-123">已分配的**电话系统**用户许可证数量影响服务号码可用于呼叫的队列数。</span><span class="sxs-lookup"><span data-stu-id="529aa-123">The number of **Phone System** user licenses that are assigned affects the number of service numbers that are available to be used for call queues.</span></span> <span data-ttu-id="529aa-124">您可以呼叫队列数是取决于您的组织中分配的**电话系统**和**音频会议**的许可证数量。</span><span class="sxs-lookup"><span data-stu-id="529aa-124">The number of call queues you can have is dependent on the number of **Phone System** and **Audio Conferencing** licenses that are assigned in your organization.</span></span> <span data-ttu-id="529aa-125">若要了解有关授权的详细信息转[此处](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="529aa-125">To learn more about licensing, go [here](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>

    > [!NOTE]
    > <span data-ttu-id="529aa-126">要重定向呼叫的人员在组织中联机，它们必须具有**电话系统**许可证和启用了企业语音或其 Office 365 调用计划。</span><span class="sxs-lookup"><span data-stu-id="529aa-126">To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans.</span></span> <span data-ttu-id="529aa-127">请参阅[业务和 Microsoft 团队许可证分配 Skype](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="529aa-127">See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span> <span data-ttu-id="529aa-128">要为他们启用企业语音，可以使用 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="529aa-128">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="529aa-129">例如运行： `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="529aa-129">For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>
  
- <span data-ttu-id="529aa-130">若要了解有关 Office 365 通话套餐的详细信息，请参阅 [Office 365 中有哪些通话套餐？](/microsoftteams/what-are-calling-plans-in-office-365) 和 [Office 365 的通话套餐](/microsoftteams/calling-plans-for-office-365)。</span><span class="sxs-lookup"><span data-stu-id="529aa-130">To learn more about Office 365 Calling Plans, see [What are Calling Plans in Office 365?](/microsoftteams/what-are-calling-plans-in-office-365) and [Calling Plans for Office 365](/microsoftteams/calling-plans-for-office-365).</span></span>

    > [!NOTE]
    > <span data-ttu-id="529aa-131">用户托管在本地为呼叫队列代理不支持使用 Lync Server 2010。</span><span class="sxs-lookup"><span data-stu-id="529aa-131">Users hosted on-premises using Lync Server 2010 aren't supported as a Call Queue Agents.</span></span> 
  
- <span data-ttu-id="529aa-132">你可以只分配在 **Skype for Business 管理中心**获取的或从另一个服务提供商转接到电话系统呼叫队列的收费和免费电话服务电话号码。</span><span class="sxs-lookup"><span data-stu-id="529aa-132">You can only assign toll and toll-free service phone numbers that you got in the **Skype for Business admin center** or transferred from another service provider to Phone System call queues.</span></span> <span data-ttu-id="529aa-133">若要获取并使用免费电话号码，则需要设置通信点数。</span><span class="sxs-lookup"><span data-stu-id="529aa-133">To get and use toll-free service numbers, you need to set up Communications Credits.</span></span>

    > [!NOTE]
    > <span data-ttu-id="529aa-134">[!注释] 不能将用户（订阅者）的电话号码分配给呼叫队列 - 只能使用收费或免费服务电话号码。</span><span class="sxs-lookup"><span data-stu-id="529aa-134">User (subscriber) phone numbers can't be assigned to call queues - only service toll or toll-free phone numbers can be used.</span></span> 
  
- <span data-ttu-id="529aa-135">当您要分发从电话系统呼叫队列的传入呼叫时，呼叫代理支持这些客户端：</span><span class="sxs-lookup"><span data-stu-id="529aa-135">When you are distributing the incoming calls from an Phone System call queue, these clients are supported for call agents:</span></span>

  - <span data-ttu-id="529aa-136">Skype for Business 桌面客户端 2016（32 位和 64 位版本）</span><span class="sxs-lookup"><span data-stu-id="529aa-136">Skype for Business desktop client 2016 (32 and 64-bit versions)</span></span>

  - <span data-ttu-id="529aa-137">Lync 桌面客户端 2013（32 位和 64 位版本）</span><span class="sxs-lookup"><span data-stu-id="529aa-137">Lync desktop client 2013 (32 and 64-bit versions)</span></span>

  - <span data-ttu-id="529aa-138">支持 Skype for Business Online 的所有 IP 电话型号。</span><span class="sxs-lookup"><span data-stu-id="529aa-138">All IP phone models supported for Skype for Business Online.</span></span> <span data-ttu-id="529aa-139">请参阅[获取适用于 Skype for Business Online 的电话](getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online.md)。</span><span class="sxs-lookup"><span data-stu-id="529aa-139">See [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online.md).</span></span>

  - <span data-ttu-id="529aa-140">Mac Skype for Business 客户端（版本 16.8.196 及更高版本）</span><span class="sxs-lookup"><span data-stu-id="529aa-140">Mac Skype for Business Client (version 16.8.196 and later)</span></span> 

  - <span data-ttu-id="529aa-141">Android Skype for Business 客户端（版本 6.16.0.9 及更高版本）</span><span class="sxs-lookup"><span data-stu-id="529aa-141">Android Skype for Business Client (version 6.16.0.9 and later)</span></span>

  - <span data-ttu-id="529aa-142">iPhone Skype for Business 客户端（版本 6.16.0 及更高版本）</span><span class="sxs-lookup"><span data-stu-id="529aa-142">iPhone Skype for Business Client (version 6.16.0 and later)</span></span>

  - <span data-ttu-id="529aa-143">iPad Skype for Business 客户端（版本 6.16.0 及更高版本）</span><span class="sxs-lookup"><span data-stu-id="529aa-143">iPad Skype for Business Client (version 6.16.0 and later)</span></span>

  - <span data-ttu-id="529aa-144">Microsoft Teams Windows 客户端 （32 和 64 位版本）</span><span class="sxs-lookup"><span data-stu-id="529aa-144">Microsoft Teams Windows client (32 and 64-bit versions)</span></span>

  - <span data-ttu-id="529aa-145">Microsoft Teams Mac 客户端</span><span class="sxs-lookup"><span data-stu-id="529aa-145">Microsoft Teams Mac client</span></span>

  - <span data-ttu-id="529aa-146">Microsoft Teams iPhone 应用</span><span class="sxs-lookup"><span data-stu-id="529aa-146">Microsoft Teams iPhone app</span></span>

  - <span data-ttu-id="529aa-147">Microsoft Teams Android 应用</span><span class="sxs-lookup"><span data-stu-id="529aa-147">Microsoft Teams Android app</span></span>

## <a name="step-2---getting-or-transferring-toll-or-toll-free-service-phone-numbers"></a><span data-ttu-id="529aa-148">第 2 步 - 获取或转移收费或免费服务电话号码</span><span class="sxs-lookup"><span data-stu-id="529aa-148">Step 2 - Getting or transferring toll or toll-free service phone numbers</span></span>

<span data-ttu-id="529aa-149">在创建和设置呼叫队列之前，您需要获取或转移现有的收费或免费服务号码。</span><span class="sxs-lookup"><span data-stu-id="529aa-149">Before you can create and set up your call queues, you will need to get or transfer your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="529aa-150">获得收费电话或免费电话服务电话号码后，他们会显示在 **Skype for Business 管理中心** > **语音** > **电话号码**，**号码类型**将列出**服务—免费电话**。</span><span class="sxs-lookup"><span data-stu-id="529aa-150">After you get the toll or toll-free service phone numbers, they will show up in **Skype for Business admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**.</span></span> <span data-ttu-id="529aa-151">若要获取服务号码，请参阅 [从 Skype for Business 和 Microsoft Teams 获取服务电话号码](getting-service-phone-numbers.md) 或如果您希望进行转移现有服务号码，请参阅  [传输电话号码到 Office 365](/microsoftteams/transfer-phone-numbers-to-office-365) 。</span><span class="sxs-lookup"><span data-stu-id="529aa-151">To get your service numbers, see [Getting service phone numbers for Skype for Business and Microsoft Teams](getting-service-phone-numbers.md) or if you want to transfer and existing service number, see [Transfer phone numbers to Office 365](/microsoftteams/transfer-phone-numbers-to-office-365).</span></span>
  
> [!NOTE]
> <span data-ttu-id="529aa-152">如果您在美国以外，您无法使用业务管理中心的 Skype 获取服务号码。</span><span class="sxs-lookup"><span data-stu-id="529aa-152">If you are outside the United States, you can't use the Skype for Business admin center to get service numbers.</span></span> <span data-ttu-id="529aa-153">转到[管理您的组织的电话号码](/microsoftteams/manage-phone-numbers-for-your-organization)而是以了解如何执行从美国的外部。</span><span class="sxs-lookup"><span data-stu-id="529aa-153">Go to [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) instead to see how to do it from the outside of the United States.</span></span>
  
## <a name="step-3---create-a-new-call-queue"></a><span data-ttu-id="529aa-154">第 3 步 - 创建新的呼叫队列</span><span class="sxs-lookup"><span data-stu-id="529aa-154">Step 3 - Create a new Call Queue</span></span>

 <span data-ttu-id="529aa-155">**使用 Microsoft 团队 Skype 业务管理中心的**</span><span class="sxs-lookup"><span data-stu-id="529aa-155">**Using the Microsoft Teams & Skype for Business Admin Center**</span></span>

<span data-ttu-id="529aa-156">在**Microsoft 团队和 Skype 的业务管理中心**，单击![sfb-徽标-30x30.png](../images/sfb-logo-30x30.png) **旧门户** >  **呼叫路由** > **呼叫队列**，然后单击 **+ 添加新**：</span><span class="sxs-lookup"><span data-stu-id="529aa-156">In the **Microsoft Teams & Skype for Business Admin Center**, click ![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Legacy Portal** >  **Call routing** > **Call queues**, then click **+ Add new**:</span></span>
  
### <a name="set-the-call-queue-display-name-phone-number-and-domain-if-any"></a><span data-ttu-id="529aa-157">设置呼叫队列显示名称、电话号码和域（如有）</span><span class="sxs-lookup"><span data-stu-id="529aa-157">Set the call queue display name, phone number and domain (if any)</span></span>

![Setting up a call queue.](../images/37ecc300-a108-4294-8463-fce570dfce72.png)
***
<span data-ttu-id="529aa-159">![第一](../images/sfbcallout1.png)</span><span class="sxs-lookup"><span data-stu-id="529aa-159">![Number 1](../images/sfbcallout1.png)</span></span><br/>
<span data-ttu-id="529aa-p110">**名称** 为呼叫队列输入描述性显示名称。此为必填字段，最多可以包含 64 个字符，其中包括空格。</span><span class="sxs-lookup"><span data-stu-id="529aa-p110">**Name** Enter a descriptive display name for the call queue. This is required and can contain up to 64 characters, including spaces. </span></span><br/> <span data-ttu-id="529aa-162">此名称将显示在传入呼叫的通知中。</span><span class="sxs-lookup"><span data-stu-id="529aa-162">This name will be displayed in the notification for the incoming call.</span></span>
***
<span data-ttu-id="529aa-163">![第二](../images/sfbcallout2.png)</span><span class="sxs-lookup"><span data-stu-id="529aa-163">![Number 2](../images/sfbcallout2.png)</span></span><br/><span data-ttu-id="529aa-164">**电话号码** 为呼叫队列选择收费或免费服务电话号码。</span><span class="sxs-lookup"><span data-stu-id="529aa-164">**Phone number** Select a service toll or toll-free phone number for the call queue.</span></span> <span data-ttu-id="529aa-165">这是可选的。</span><span class="sxs-lookup"><span data-stu-id="529aa-165">This is optional.</span></span> <br/> <span data-ttu-id="529aa-166">如果没有列出任何号码，则需要首先获取服务号码，然后才能创建此服务队列。</span><span class="sxs-lookup"><span data-stu-id="529aa-166">If there aren't any listed, you need to get service numbers before you can create this call queue.</span></span> <span data-ttu-id="529aa-167">若要获取服务号码，请参阅[业务和 Microsoft 团队的 Skype 获取服务电话号码](getting-service-phone-numbers.md)</span><span class="sxs-lookup"><span data-stu-id="529aa-167">To get your service numbers, see [Getting service phone numbers for Skype for Business and Microsoft Teams](getting-service-phone-numbers.md)</span></span>
***
<span data-ttu-id="529aa-168">![第三](../images/sfbcallout3.png)</span><span class="sxs-lookup"><span data-stu-id="529aa-168">![Number 3](../images/sfbcallout3.png)</span></span><br/><span data-ttu-id="529aa-p113">**域** 如果此字段可用，请选择要使用的 Office 365 域。仅当你拥有多个用于 Office 365 的域时此字段才可用。如果你拥有多个域，必须从列表中选择域名。 </span><span class="sxs-lookup"><span data-stu-id="529aa-p113">**Domain** If this is available, choose the Office 365 domain you want to use. This is only available if you have more than one domain being used with Office 365. If you have more than one, you must chose the domain name from the list. </span></span><br/> <span data-ttu-id="529aa-172">例如，你可能拥有类似以下名称的域： _contoso.com or redmond.contoso.com_</span><span class="sxs-lookup"><span data-stu-id="529aa-172">For example, you could have a domain like:  _contoso.com or redmond.contoso.com_</span></span>

### <a name="set-the-greeting-and-music-played-while-on-hold"></a><span data-ttu-id="529aa-173">设置通话保持时播放的问候语和音乐</span><span class="sxs-lookup"><span data-stu-id="529aa-173">Set the greeting and music played while on hold</span></span>

![Setting up a call queue.](../images/1d395a93-7cab-4178-9295-12d5379e20de.png)
  
***
<span data-ttu-id="529aa-175">![第一](../images/sfbcallout1.png)</span><span class="sxs-lookup"><span data-stu-id="529aa-175">![Number 1](../images/sfbcallout1.png)</span></span><br/><span data-ttu-id="529aa-176">**问候语**是可选设置。</span><span class="sxs-lookup"><span data-stu-id="529aa-176">**Greeting** is optional.</span></span> <span data-ttu-id="529aa-177">这是呼叫队列号码的呼叫中的人员播放问候语。</span><span class="sxs-lookup"><span data-stu-id="529aa-177">This is the greeting that is played for people who call in to the call queue number.</span></span> <br/> <span data-ttu-id="529aa-178">您可以上载音频文件 （.wav、.mp3 或.wma 格式）。</span><span class="sxs-lookup"><span data-stu-id="529aa-178">You can upload an audio file (.wav, .mp3, or .wma formats).</span></span>
***
<span data-ttu-id="529aa-179">![第二](../images/sfbcallout2.png)</span><span class="sxs-lookup"><span data-stu-id="529aa-179">![Number 2](../images/sfbcallout2.png)</span></span><br/><span data-ttu-id="529aa-180">**音乐**您可以使用默认保持音乐置于保持状态提供与呼叫队列，或者可以上载.wav、 mp3 或.wma 格式用作您自定义保留音乐音频文件。</span><span class="sxs-lookup"><span data-stu-id="529aa-180">**Music on hold** You can either use the default Music on Hold provided with the call queue, or you can upload an audio file in .wav, mp3, or .wma formats to use as your custom Music on Hold.</span></span>

### <a name="select-the-call-distribution-method"></a><span data-ttu-id="529aa-181">选择呼叫分发方法</span><span class="sxs-lookup"><span data-stu-id="529aa-181">Select the call distribution method</span></span>

![显示呼叫分发方法选项](../images/5d249515-d532-4af2-90da-011404028b89.png)
  
***
<span data-ttu-id="529aa-183">![第一](../images/sfbcallout1.png)</span><span class="sxs-lookup"><span data-stu-id="529aa-183">![Number 1](../images/sfbcallout1.png)</span></span><br/><span data-ttu-id="529aa-184">**呼叫分发方法**呼叫队列分发方法，可以选择**助理**或**串行**。</span><span class="sxs-lookup"><span data-stu-id="529aa-184">**Call distribution method** You can choose either **Attendant** or **Serial** for your call queue distribution method.</span></span> <span data-ttu-id="529aa-185">所有新的和现有呼叫队列将具有默认情况下选中的助理路由。</span><span class="sxs-lookup"><span data-stu-id="529aa-185">All new and existing call queues will have attendant routing selected by default.</span></span> <span data-ttu-id="529aa-186">若要使用串行路由，必须明确在 UI 和 cmdlet 中选择 **串行** 路由选项。</span><span class="sxs-lookup"><span data-stu-id="529aa-186">To use serial routing, you must explicitly choose the **Serial** routing option in UI and cmdlets.</span></span> <br/><br/> <span data-ttu-id="529aa-187">当选取串行路由并保存呼叫队列时，来自队列的呼叫将从代理列表的开头开始逐个拨打各位代理。</span><span class="sxs-lookup"><span data-stu-id="529aa-187">When serial routing is chosen and the call queue is saved, the calls from the queue will ring your agents one by one, starting from the beginning of the agent list.</span></span> <span data-ttu-id="529aa-188">如果代理挂断或不接听电话，电话将打给列表的下一位代理，并将尝试逐个拨打所有代理，直到有人接听或队列等待超时为止。</span><span class="sxs-lookup"><span data-stu-id="529aa-188">If an agent dismisses or does not pick up a call, the call will ring the next agent on the list and will try all agents one by one until it is picked up or times out waiting in the queue.</span></span>   

> [!NOTE]
> <span data-ttu-id="529aa-189">串行路由将跳过处于**脱机**状态、已将其状态设置为 **请勿打扰**或**已选择退出**不从此队列获取呼叫的代理。</span><span class="sxs-lookup"><span data-stu-id="529aa-189">Serial routing will skip agents who are **Offline**, have set their presence to **Do not Disturb**, or have **opted out** of getting calls from this queue.</span></span> 

### <a name="select-an-agent-opt-out-option"></a><span data-ttu-id="529aa-190">选择代理退出选项</span><span class="sxs-lookup"><span data-stu-id="529aa-190">Select an agent opt out option</span></span>

![显示代理退出复选框](../images/99279eff-db61-4acf-9b62-64be84b6414b.png)
  
***
<span data-ttu-id="529aa-192">![第一](../images/sfbcallout1.png)</span><span class="sxs-lookup"><span data-stu-id="529aa-192">![Number 1](../images/sfbcallout1.png)</span></span><br/><span data-ttu-id="529aa-193">**代理退出选项**你可以选择允许呼叫队列代理通过选择**代理退出选项**，不接收来自特定队列的呼叫。
。</span><span class="sxs-lookup"><span data-stu-id="529aa-193">**Agent Opt out option** You can choose to allow call queue agents to opt out of taking calls from a particular queue by selecting **Agent Opt out option**.</span></span>  <br/> <span data-ttu-id="529aa-194">启用此选项允许此队列中的所有代理随意开始或停止接收来自此呼叫队列的呼叫。</span><span class="sxs-lookup"><span data-stu-id="529aa-194">Enabling this option allows all agents in this queue to start or stop receiving call from this call queue at will.</span></span> <span data-ttu-id="529aa-195">通过清除此复选框，你可以随时撤消代理选择退出特权，这将导致所有代理自动选择再加入此队列 （所有代理的默认设置）。</span><span class="sxs-lookup"><span data-stu-id="529aa-195">You can revoke the agent opt-out privilege at any time by clearing the check box, causing agents to become automatically opted in for this queue again (the default setting for all agents).</span></span>  <br/><br/> <span data-ttu-id="529aa-196">若要访问选择退出选项，代理可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="529aa-196">To access the opt-out option, agents can do the following:</span></span>
 1. <span data-ttu-id="529aa-197">在其桌面 Skype for Business 客户端中打开**选项**。</span><span class="sxs-lookup"><span data-stu-id="529aa-197">Open **Options** in their desktop Skype for Business client.</span></span> 
 2. <span data-ttu-id="529aa-198">在**呼叫转移**选项卡中，单击**在线编辑设置**链接。</span><span class="sxs-lookup"><span data-stu-id="529aa-198">On the **Call Forwarding** tab, click the **Edit settings online** link.</span></span>
 3. <span data-ttu-id="529aa-199">在用户设置页中，单击**呼叫队列**，然后清除他们想要退出的任何队列对应的复选框。</span><span class="sxs-lookup"><span data-stu-id="529aa-199">On the user settings page, click **Call Queues**, and then clear the check boxes for any queues for which they want to opt out.</span></span>

    > [!NOTE] 
    > <span data-ttu-id="529aa-200">使用 Mac、移动、Lync 2013 客户端的代理，或使用 Skype for Business 2015 服务器托管在本地的混合语音用户，可转到[https://aka.ms/cqsettings](https://aka.ms/cqsettings) 访问退出选项。</span><span class="sxs-lookup"><span data-stu-id="529aa-200">Agents using Mac, mobile, or Lync 2013 clients, or Hybrid Voice users who are hosted on-premises using Skype for Business 2015 server, can go to [https://aka.ms/cqsettings](https://aka.ms/cqsettings) to access the opt out option.</span></span>

### <a name="add-call-agents-to-a-call-queue"></a><span data-ttu-id="529aa-201">向呼叫队列添加呼叫代理</span><span class="sxs-lookup"><span data-stu-id="529aa-201">Add call agents to a call queue</span></span>

![Set up call queues.](../images/skype-for-business-add-agents-to-call-queue.png)
  
***
![第一](../images/sfbcallout1.png)<br/><br/><span data-ttu-id="529aa-204">呼叫代理 (200 最大)，可以：</span><span class="sxs-lookup"><span data-stu-id="529aa-204">Call agents (200 maximum) can be:</span></span>
* <span data-ttu-id="529aa-205">拥有**电话系统**许可证和启用了企业语音或拥有通话套餐的在线用户。</span><span class="sxs-lookup"><span data-stu-id="529aa-205">An Online user with a **Phone System** license and enabled for Enterprise Voice or with a Calling Plan.</span></span> <br/><br/> <span data-ttu-id="529aa-206">**注意：** 要重定向呼叫的人员在组织中联机，它们必须具有**电话系统**许可证和启用了企业语音或其调用规划。</span><span class="sxs-lookup"><span data-stu-id="529aa-206">**Note:**  To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have a Calling Plan.</span></span> <span data-ttu-id="529aa-207">请参阅[业务和 Microsoft 团队许可证分配 Skype](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="529aa-207">See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span> <span data-ttu-id="529aa-208">要为他们启用企业语音，可以使用 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="529aa-208">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="529aa-209">例如运行： `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="529aa-209">For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span> <br/><br/>
* <span data-ttu-id="529aa-210">拥有**电话系统**许可证和通话套餐（已添加到 Office 365 组、已启用邮件的通讯组列表或安全组）的在线用户。</span><span class="sxs-lookup"><span data-stu-id="529aa-210">Online users with a **Phone System** license and a Calling Plan that are added to an Office 365 Group, a mail-enabled Distribution List, or a Security Group.</span></span> <span data-ttu-id="529aa-211">为通讯组列表或安全组添加一位新代理，以便开始接收来自呼叫队列的呼叫，这可能需要 30 分钟的时间。</span><span class="sxs-lookup"><span data-stu-id="529aa-211">It might take up to 30 minutes for a new agent added for a distribution list or a security group to start receiving calls from a call queue.</span></span> <span data-ttu-id="529aa-212">新建通讯组列表或安全组可能需要长达 48 小时成为可用于呼叫的队列。</span><span class="sxs-lookup"><span data-stu-id="529aa-212">A newly created distribution list or security group might take up to 48 hours to become available to be used with call queues.</span></span> <span data-ttu-id="529aa-213">新创建的 Office 365 组几乎立即就可使用。</span><span class="sxs-lookup"><span data-stu-id="529aa-213">Newly created Office 365 Groups are available almost immediately.</span></span> <br/> 

  > [!NOTE] 
  > <span data-ttu-id="529aa-214">用户托管在本地不支持使用 Lync Server 2010。</span><span class="sxs-lookup"><span data-stu-id="529aa-214">Users hosted on-premises using Lync Server 2010 aren't supported.</span></span>

### <a name="set-the-maximum-queue-size-and-maximum-wait-time"></a><span data-ttu-id="529aa-215">设置队列最大大小和最长等待时间。</span><span class="sxs-lookup"><span data-stu-id="529aa-215">Set the maximum queue size and maximum wait time</span></span>

![Set up a call queue.](../images/3f018734-16fe-458b-827d-71fc25155cde.png)
  
***
<span data-ttu-id="529aa-217">![第一](../images/sfbcallout1.png)</span><span class="sxs-lookup"><span data-stu-id="529aa-217">![Number 1](../images/sfbcallout1.png)</span></span><br/><br/><span data-ttu-id="529aa-218">**队列中的最大呼叫数** 使用此字段来设置同一时间可以在队列中等待的最大呼叫数。</span><span class="sxs-lookup"><span data-stu-id="529aa-218">**Maximum calls in the queue** Use this to set the maximum calls that can wait in the queue at the same time.</span></span> <span data-ttu-id="529aa-219">默认值为 50，但它可以介于 0 到 200.达到此限制时，将设置下的**时达到的最大呼叫数**设置的方式处理呼叫。</span><span class="sxs-lookup"><span data-stu-id="529aa-219">The default is 50, but it can range from 0 to 200.When this limit is reached, the call will be handled in way you have set on the **When the maximum number of calls is reached** setting below.</span></span>
***
<span data-ttu-id="529aa-220">![第二](../images/sfbcallout2.png)</span><span class="sxs-lookup"><span data-stu-id="529aa-220">![Number 2](../images/sfbcallout2.png)</span></span><br/><br/><span data-ttu-id="529aa-221">**当达到的最大呼叫数**当呼叫队列达到其最大大小 （设置使用的**队列中的最大呼叫**设置） 时，您可以选择新的传入呼叫会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="529aa-221">**When the maximum number of calls is reached** When the call queue reaches its maximum size (set using the **Maximum calls in the queue** setting), you can choose what happens to new incoming calls.</span></span>
* <span data-ttu-id="529aa-222">**断开连接并显示繁忙信号** 呼叫将断开连接。</span><span class="sxs-lookup"><span data-stu-id="529aa-222">**Disconnect with a busy signal** The call will be disconnected.</span></span>
* <span data-ttu-id="529aa-223">**此将呼叫转移到**选择此，您可以在这些选项：</span><span class="sxs-lookup"><span data-stu-id="529aa-223">**Forward this call to** When you choose this, you will have these options:</span></span>
  * <span data-ttu-id="529aa-224">**公司内的人员**与**电话系统**许可证联机用户和启用了企业语音或其调用规划。</span><span class="sxs-lookup"><span data-stu-id="529aa-224">**Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have a Calling Plan.</span></span> <span data-ttu-id="529aa-225">你可以通过此设置将呼叫者直接转到语音邮件。</span><span class="sxs-lookup"><span data-stu-id="529aa-225">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="529aa-226">要执行此操作，选择**您的公司的人员**，并设置此人要使其呼叫直接转接到语音邮件。</span><span class="sxs-lookup"><span data-stu-id="529aa-226">To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span> <br/> <br/><span data-ttu-id="529aa-227">若要了解有关语音邮件所需授权的信息，请参阅[设置电话系统的语音邮件](/microsoftteams/set-up-phone-system-voicemail)。</span><span class="sxs-lookup"><span data-stu-id="529aa-227">To learn about licensing required for voicemail, see [Set up Phone System voicemail](/microsoftteams/set-up-phone-system-voicemail).</span></span> 

    > [!Note]
    > <span data-ttu-id="529aa-228">用户托管在本地不支持使用 Lync Server 2010。</span><span class="sxs-lookup"><span data-stu-id="529aa-228">Users hosted on-premises using Lync Server 2010 aren't supported.</span></span><br/>

  * <span data-ttu-id="529aa-229">**呼叫队列**您必须已创建另一个呼叫队列，但执行操作后，您可以选择该呼叫的队列。</span><span class="sxs-lookup"><span data-stu-id="529aa-229">**Call Queue** You must have already created another call queue, but after you do, you can select that call queue.</span></span>
  * <span data-ttu-id="529aa-230">**自动助理**您必须已创建自动助理，但您执行操作后，您可以选择的自动助理。</span><span class="sxs-lookup"><span data-stu-id="529aa-230">**Auto Attendant** You must have already created an auto attendant, but after you do, you can select that auto attendant.</span></span> <span data-ttu-id="529aa-231">请参阅[设置电话系统自动助理](set-up-a-phone-system-auto-attendant.md)。</span><span class="sxs-lookup"><span data-stu-id="529aa-231">See [Set up a Phone System auto attendant](set-up-a-phone-system-auto-attendant.md).</span></span>
***
<span data-ttu-id="529aa-232">![第三](../images/sfbcallout3.png)</span><span class="sxs-lookup"><span data-stu-id="529aa-232">![Number 3](../images/sfbcallout3.png)</span></span><br/><br/><span data-ttu-id="529aa-p123">**呼叫在队列中可以等待多长时间** 你还可以决定呼叫在超时和需要重新定向或断开连接前可以在队列中保留的时间。重新定向的目的地取决于" **当呼叫超时时**"中的设置。你可以将此时间设置为 0 到 45 分钟。 </span><span class="sxs-lookup"><span data-stu-id="529aa-p123">**How long a call can wait in the queue** You can also decide how much time a call can be on hold in the queue before it times out and needs to be redirected or disconnected. Where it will be redirected is based on how you set the **When a call times out** setting. You can set a time from 0 to 45 minutes. </span></span><br/><br/> <span data-ttu-id="529aa-236">超时值可以以秒为单位按 15 秒间隔进行设置。</span><span class="sxs-lookup"><span data-stu-id="529aa-236">The timeout value can be set in seconds, at 15-second intervals.</span></span> <span data-ttu-id="529aa-237">这样，你可以以更细的粒度操作呼叫流。</span><span class="sxs-lookup"><span data-stu-id="529aa-237">This allows you to manipulate the call flow with finer granularity.</span></span> <span data-ttu-id="529aa-238">例如，你可以指定在 30 秒内代理不作应答的所有呼叫转到目录搜索自动助理。</span><span class="sxs-lookup"><span data-stu-id="529aa-238">For example, you could specify that any calls that are not answered by an agent within 30 seconds go to a Directory Search Auto Attendant.</span></span> 

***
<span data-ttu-id="529aa-239">![第四](../images/sfbcallout4.png)</span><span class="sxs-lookup"><span data-stu-id="529aa-239">![Number 4](../images/sfbcallout4.png)</span></span><br/><br/><span data-ttu-id="529aa-240">**当呼叫超时时** 当呼叫达到" **呼叫在队列中可以等待多长时间**"中设置的限制时，你可以选择如何处理此呼叫：</span><span class="sxs-lookup"><span data-stu-id="529aa-240">**When a call times out** When the call reaches the limit you set on the **How long a call can wait in the queue** setting, you can choose what happens to this call:</span></span>
* <span data-ttu-id="529aa-241">**断开连接** 呼叫将断开连接。</span><span class="sxs-lookup"><span data-stu-id="529aa-241">**Disconnect** The call will be disconnected.</span></span>
* <span data-ttu-id="529aa-242">**此将呼叫转移到**选择此，您可以在这些选项：</span><span class="sxs-lookup"><span data-stu-id="529aa-242">**Forward this call to** When you choose this, you will have these options:</span></span>
  * <span data-ttu-id="529aa-243">**公司内的人员**与**电话系统**许可证联机用户和启用了企业语音或其调用计划。</span><span class="sxs-lookup"><span data-stu-id="529aa-243">**Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have Calling Plans.</span></span> <span data-ttu-id="529aa-244">你可以通过此设置将呼叫者直接转到语音邮件。</span><span class="sxs-lookup"><span data-stu-id="529aa-244">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="529aa-245">要执行此操作，选择**您的公司的人员**，并设置此人要使其呼叫直接转接到语音邮件。</span><span class="sxs-lookup"><span data-stu-id="529aa-245">To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span> </br><br/>  <span data-ttu-id="529aa-246">若要了解有关语音邮件所需授权的信息，请参阅[设置电话系统的语音邮件](/microsoftteams/set-up-phone-system-voicemail)。</span><span class="sxs-lookup"><span data-stu-id="529aa-246">To learn about licensing required for voicemail, see [Set up Phone System voicemail](/microsoftteams/set-up-phone-system-voicemail).</span></span> 

    > [!Note]
    > <span data-ttu-id="529aa-247">用户托管在本地不支持使用 Lync Server 2010。</span><span class="sxs-lookup"><span data-stu-id="529aa-247">Users hosted on-premises using Lync Server 2010 aren't supported.</span></span><br/>

  * <span data-ttu-id="529aa-248">**呼叫队列**您必须已创建另一个呼叫队列，但执行操作后，您可以选择该呼叫的队列。</span><span class="sxs-lookup"><span data-stu-id="529aa-248">**Call Queue** You must have already created another call queue, but after you do, you can select that call queue.</span></span>
  * <span data-ttu-id="529aa-249">**自动助理**您必须已创建自动助理，但您执行操作后，您可以选择的自动助理。</span><span class="sxs-lookup"><span data-stu-id="529aa-249">**Auto Attendant** You must have already created an auto attendant, but after you do, you can select that auto attendant.</span></span> <span data-ttu-id="529aa-250">请参阅[设置电话系统自动助理](set-up-a-phone-system-auto-attendant.md)。</span><span class="sxs-lookup"><span data-stu-id="529aa-250">See [Set up a Phone System auto attendant](set-up-a-phone-system-auto-attendant.md).</span></span>
   
## <a name="changing-the-users-caller-id-to-be-a-call-queues-phone-number"></a><span data-ttu-id="529aa-251">更改用户的来电显示为呼叫队列的电话号码</span><span class="sxs-lookup"><span data-stu-id="529aa-251">Changing the user's Caller ID to be a call queue's phone number</span></span>

<span data-ttu-id="529aa-252">通过使用**新建 CallingLineIdentity** cmdlet 创建策略，可将出站呼叫的来电显示更改为呼叫队列，从而保护用户的身份。</span><span class="sxs-lookup"><span data-stu-id="529aa-252">You can protect a user's identity by changing their caller ID for the outbound calls to a call queue instead by creating a policy using the **New-CallingLineIdentity** cmdlet.</span></span>
  
<span data-ttu-id="529aa-253">若要执行此操作，请运行：</span><span class="sxs-lookup"><span data-stu-id="529aa-253">To do this, run:</span></span>
  
```
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

<span data-ttu-id="529aa-254">然后使用 **Grant-CallingLineIdentity** cmdlet 将策略应用于用户。</span><span class="sxs-lookup"><span data-stu-id="529aa-254">Then apply the policy to the user using the **Grant-CallingLineIdentity** cmdlet.</span></span> <span data-ttu-id="529aa-255">若要执行此操作，请运行：</span><span class="sxs-lookup"><span data-stu-id="529aa-255">To do this, run:</span></span>
  
```
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

<span data-ttu-id="529aa-256">有关如何在组织中对来电显示设置进行更改的详细信息，可访问 [此处](../what-are-calling-plans-in-office-365/how-can-caller-id-be-used-in-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="529aa-256">You can get more information on how to make changes to caller ID settings in your organization [here](../what-are-calling-plans-in-office-365/how-can-caller-id-be-used-in-your-organization.md).</span></span>
  
## <a name="want-to-know-more"></a><span data-ttu-id="529aa-257">希望了解更多信息吗？</span><span class="sxs-lookup"><span data-stu-id="529aa-257">Want to know more?</span></span>

<span data-ttu-id="529aa-258">还可以使用 Windows PowerShell 来创建和设置呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="529aa-258">You can also use Windows PowerShell to create and set up call queues.</span></span>
  
### <a name="call-queue-cmdlets"></a><span data-ttu-id="529aa-259">呼叫队列 cmdlet</span><span class="sxs-lookup"><span data-stu-id="529aa-259">Call queue cmdlets</span></span>

<span data-ttu-id="529aa-260">以下是管理呼叫队列时需要使用的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="529aa-260">Here are the cmdlets that you need to manage a call queue.</span></span>
  
- [<span data-ttu-id="529aa-261">New-CsHuntgroup</span><span class="sxs-lookup"><span data-stu-id="529aa-261">New-CsHuntgroup</span></span>](https://technet.microsoft.com/en-us/library/mt796459.aspx)

- [<span data-ttu-id="529aa-262">Set-CsHuntgroup</span><span class="sxs-lookup"><span data-stu-id="529aa-262">Set-CsHuntgroup</span></span>](https://technet.microsoft.com/en-us/library/mt796457.aspx)

- [<span data-ttu-id="529aa-263">Get-CsHuntgroup</span><span class="sxs-lookup"><span data-stu-id="529aa-263">Get-CsHuntgroup</span></span>](https://technet.microsoft.com/en-us/library/mt796458.aspx)

- [<span data-ttu-id="529aa-264">Remove-CsHuntgroup</span><span class="sxs-lookup"><span data-stu-id="529aa-264">Remove-CsHuntgroup</span></span>](https://technet.microsoft.com/en-us/library/mt796456.aspx)

### <a name="more-about-windows-powershell"></a><span data-ttu-id="529aa-265">有关 Windows PowerShell 的详细信息</span><span class="sxs-lookup"><span data-stu-id="529aa-265">More about Windows PowerShell</span></span>

- <span data-ttu-id="529aa-266">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。</span><span class="sxs-lookup"><span data-stu-id="529aa-266">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="529aa-267">当你有多个要执行的任务时，使用 Windows PowerShell 可以通过能够简化日常工作的单点管理来管理 Office 365 和 Skype for Business Online。</span><span class="sxs-lookup"><span data-stu-id="529aa-267">With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="529aa-268">若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="529aa-268">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="529aa-269">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="529aa-269">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [<span data-ttu-id="529aa-270">为什么要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="529aa-270">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

- <span data-ttu-id="529aa-p129">例如当你一次对多个用户更改设置时，Windows PowerShell 比起仅使用 Office 365 管理中心，在速度、简明性和效率方面具有许多优势。通过以下主题了解这些优势：</span><span class="sxs-lookup"><span data-stu-id="529aa-p129">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="529aa-273">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="529aa-273">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [<span data-ttu-id="529aa-274">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="529aa-274">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [<span data-ttu-id="529aa-275">使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务</span><span class="sxs-lookup"><span data-stu-id="529aa-275">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="529aa-276">相关主题</span><span class="sxs-lookup"><span data-stu-id="529aa-276">Related topics</span></span>
[<span data-ttu-id="529aa-277">Office 365 中的电话系统的功能</span><span class="sxs-lookup"><span data-stu-id="529aa-277">Here's what you get with Phone System in Office 365</span></span>](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[<span data-ttu-id="529aa-278">获取 Skype for Business 和 Microsoft Teams 的服务电话号码</span><span class="sxs-lookup"><span data-stu-id="529aa-278">Getting service phone numbers for Skype for Business and Microsoft Teams</span></span>](getting-service-phone-numbers.md)

[<span data-ttu-id="529aa-279">音频会议和通话套餐的国家/地区可用性</span><span class="sxs-lookup"><span data-stu-id="529aa-279">Country and region availability for Audio Conferencing and Calling Plans</span></span>](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)
