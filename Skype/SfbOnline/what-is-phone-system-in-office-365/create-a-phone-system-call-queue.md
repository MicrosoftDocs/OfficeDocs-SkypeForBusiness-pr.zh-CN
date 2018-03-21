---
title: "创建电话系统调用队列"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: makolomi
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
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
- Strat_SB_PSTN
description: 'Learn how to set up phone system for Office 365 (Cloud PBX) call queues to give you an organizational greeting, music on hold, and redirecting calls to call agents in distribution lists and security groups. You can also set the maximum queue size, time out, and call handling options. '
ms.openlocfilehash: 784033005882eeca105fd59a543ce9d1009ea84f
ms.sourcegitcommit: 50446359cd7c359eb2536176545291c723392e47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2018
---
# <a name="create-a-phone-system-call-queue"></a><span data-ttu-id="79a46-104">创建电话系统调用队列</span><span class="sxs-lookup"><span data-stu-id="79a46-104">Create a Phone System call queue</span></span>

<span data-ttu-id="79a46-105">队列包含问候某人连接到您的组织，能够自动将呼叫置于保持状态，并搜索下一个可用的呼叫代理处理该调用时人的能力的电话号码时所使用的电话系统调用者调用欣赏音乐暂候状态。</span><span class="sxs-lookup"><span data-stu-id="79a46-105">Phone System call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold.</span></span> <span data-ttu-id="79a46-106">您可以为您的组织创建单个或多个调用队列。</span><span class="sxs-lookup"><span data-stu-id="79a46-106">You can create single or multiple call queues for your organization.</span></span>
  
<span data-ttu-id="79a46-107">电话系统调用队列可以提供：</span><span class="sxs-lookup"><span data-stu-id="79a46-107">Phone System call queues can provide:</span></span>
  
- <span data-ttu-id="79a46-108">组织问候语。</span><span class="sxs-lookup"><span data-stu-id="79a46-108">An organizational greeting.</span></span>
    
- <span data-ttu-id="79a46-109">在呼叫者保持等待时播放的音乐。</span><span class="sxs-lookup"><span data-stu-id="79a46-109">Music while people are waiting on hold.</span></span>
    
- <span data-ttu-id="79a46-110">重定向的调用来调用已启用邮件的通讯组和安全组中的代理。</span><span class="sxs-lookup"><span data-stu-id="79a46-110">Redirecting of calls to call agents in mail-enabled distribution lists and security groups.</span></span>
    
- <span data-ttu-id="79a46-111">使调用队列最大大小、 超时值，以及调用处理选项设置。</span><span class="sxs-lookup"><span data-stu-id="79a46-111">Making settings for call queue maximum size, timeout, and call handling options.</span></span>
    
<span data-ttu-id="79a46-112">当某人连接到设置电话号码向上与呼叫队列，他们会听到一句问候语第一个 （如果任何设置），然后他们将放入队列中，等待下一个可用的呼叫代理。</span><span class="sxs-lookup"><span data-stu-id="79a46-112">When someone calls in to a phone number that is set up up with a call queue, they will hear a greeting first (if any is set up), and then they will be put in the queue and wait for the next available call agent.</span></span> <span data-ttu-id="79a46-113">呼叫者在等待时会听到音乐，系统将按照 *先进先出*  (FIFO) 的方式为呼叫分配呼叫代理。</span><span class="sxs-lookup"><span data-stu-id="79a46-113">The person calling in will hear music while they are on hold waiting, and the calls will be offered to the call agents in the  *First In, First Out*  (FIFO) manner.</span></span>
  
<span data-ttu-id="79a46-114">队列中等待的所有调用将使用助理路由模式或串行路由模式都分发：</span><span class="sxs-lookup"><span data-stu-id="79a46-114">All calls waiting in the queue will be distributed using an attendant routing mode or serial routing mode:</span></span>
  
- <span data-ttu-id="79a46-115">使用助理路由时，队列中的第一个调用将在同一时间环所有代理。</span><span class="sxs-lookup"><span data-stu-id="79a46-115">With attendant routing, the first call in the queue will ring all agents at the same time.</span></span>
    
- <span data-ttu-id="79a46-116">使用串行路由时，队列中的第一个调用将自动震铃所有调用代理一个一个地。</span><span class="sxs-lookup"><span data-stu-id="79a46-116">With serial routing, the first call in the queue will ring all call agents one by one.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="79a46-117">将不会调用调用代理人员处于**脱机状态**，已将其状态设置为**请勿打扰，**或已退出调用队列。</span><span class="sxs-lookup"><span data-stu-id="79a46-117">Call agents who are **Offline**, have set their presence to **Do not Disturb,** or have opted out of the call queue won't be called.</span></span>
  
- <span data-ttu-id="79a46-118">同一时间只会向呼叫代理发送一个传入呼叫通知（队列最前面的呼叫）。</span><span class="sxs-lookup"><span data-stu-id="79a46-118">Only one incoming call notification (for the call at the head of the queue) at a time will be sent to the call agents.</span></span>
    
- <span data-ttu-id="79a46-119">呼叫代理接受呼叫后，队列中的下一个传入呼叫开始拨叫所有代理。</span><span class="sxs-lookup"><span data-stu-id="79a46-119">After a call agent accepts the call, the next incoming call in the queue will start ringing call agents.</span></span>
    
## <a name="step-1---getting-started"></a><span data-ttu-id="79a46-120">第 1 步 - 开始</span><span class="sxs-lookup"><span data-stu-id="79a46-120">Step 1 - Getting started</span></span>

<span data-ttu-id="79a46-121">要开始使用呼叫队列，记住以下几点至关重要：</span><span class="sxs-lookup"><span data-stu-id="79a46-121">To get started using call queues, it's important to remember a few things:</span></span>
  
- <span data-ttu-id="79a46-122">企业 E3 以及**电话系统**许可证或企业 E5 许可证，您的组织必须有 （最低要求）。</span><span class="sxs-lookup"><span data-stu-id="79a46-122">Your organization must have (at a minimum) an Enterprise E3 plus **Phone System** license or an Enterprise E5 license.</span></span> <span data-ttu-id="79a46-123">分配的**电话系统**用户许可证的数量会影响服务号可用于调用队列的数目。</span><span class="sxs-lookup"><span data-stu-id="79a46-123">The number of **Phone System** user licenses that are assigned affects the number of service numbers that are available to be used for call queues.</span></span> <span data-ttu-id="79a46-124">您可以调用队列的数目是取决于**电话系统**和**音频会议**在您的组织中分配的许可证的数量。</span><span class="sxs-lookup"><span data-stu-id="79a46-124">The number of call queues you can have is dependent on the number of **Phone System** and **Audio Conferencing** licenses that are assigned in your organization.</span></span> <span data-ttu-id="79a46-125">若要了解有关许可、 转[此处](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="79a46-125">To learn more about licensing, go [here](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="79a46-126">要重定向调用的人在组织中处于在线状态，他们必须**电话系统**许可证和能够使用企业语音或让 Office 365 调用计划。</span><span class="sxs-lookup"><span data-stu-id="79a46-126">To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans.</span></span> <span data-ttu-id="79a46-127">请参阅[指派的 Skype 业务和 Microsoft 小组的许可证](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="79a46-127">See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span> <span data-ttu-id="79a46-128">要为他们启用企业语音，可以使用 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="79a46-128">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="79a46-129">例如运行： `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="79a46-129">For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>
  
- <span data-ttu-id="79a46-130">若要了解有关 Office 365 调用计划的详细信息，请参阅[调用中 Office 365 计划是什么？](../what-are-calling-plans-in-office-365/what-are-calling-plans-in-office-365.md)和[Office 365 调用计划](../skype-for-business-and-microsoft-teams-add-on-licensing/calling-plans-for-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="79a46-130">To learn more about Office 365 Calling Plans, see [What are Calling Plans in Office 365?](../what-are-calling-plans-in-office-365/what-are-calling-plans-in-office-365.md) and [Calling Plans for Office 365](../skype-for-business-and-microsoft-teams-add-on-licensing/calling-plans-for-office-365.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="79a46-131">用户承载内部使用 Lync Server 2010 为调用队列代理不支持。</span><span class="sxs-lookup"><span data-stu-id="79a46-131">Users hosted on-premises using Lync Server 2010 aren't supported as a Call Queue Agents.</span></span> 
  
- <span data-ttu-id="79a46-132">只可以指定收费和免费服务电话号码，陷入**业务管理中心的 Skype**或另一个服务提供商转移到电话系统调用队列。</span><span class="sxs-lookup"><span data-stu-id="79a46-132">You can only assign toll and toll-free service phone numbers that you got in the **Skype for Business admin center** or transferred from another service provider to Phone System call queues.</span></span> <span data-ttu-id="79a46-133">要获取和使用免费电话服务号码，您需要设置通信贷。</span><span class="sxs-lookup"><span data-stu-id="79a46-133">To get and use toll-free service numbers, you need to set up Communications Credits.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="79a46-134">[!注释] 不能将用户（订阅者）的电话号码分配给呼叫队列 - 只能使用收费或免费服务电话号码。</span><span class="sxs-lookup"><span data-stu-id="79a46-134">User (subscriber) phone numbers can't be assigned to call queues - only service toll or toll-free phone numbers can be used.</span></span> 
  
- <span data-ttu-id="79a46-135">当分发从电话系统调用队列的传入呼叫时，呼叫代理支持这些客户端：</span><span class="sxs-lookup"><span data-stu-id="79a46-135">When you are distributing the incoming calls from an Phone System call queue, these clients are supported for call agents:</span></span>
    
  - <span data-ttu-id="79a46-136">Skype for Business 桌面客户端 2016（32 位和 64 位版本）</span><span class="sxs-lookup"><span data-stu-id="79a46-136">Skype for Business desktop client 2016 (32 and 64-bit versions)</span></span>
    
  - <span data-ttu-id="79a46-137">Lync 桌面客户端 2013（32 位和 64 位版本）</span><span class="sxs-lookup"><span data-stu-id="79a46-137">Lync desktop client 2013 (32 and 64-bit versions)</span></span>
    
  - <span data-ttu-id="79a46-138">支持 Skype for Business Online 的所有 IP 电话型号。</span><span class="sxs-lookup"><span data-stu-id="79a46-138">All IP phone models supported for Skype for Business Online.</span></span> <span data-ttu-id="79a46-139">请参阅[获取适用于 Skype for Business Online 的电话](getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online.md)。</span><span class="sxs-lookup"><span data-stu-id="79a46-139">See [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online.md).</span></span>
    
  - <span data-ttu-id="79a46-140">业务客户端的 Mac Skype (版本 16.8.196 或更高版本)</span><span class="sxs-lookup"><span data-stu-id="79a46-140">Mac Skype for Business Client (version 16.8.196 and later)</span></span> 
    
  - <span data-ttu-id="79a46-141">业务客户端 android Skype (版本 6.16.0.9 或更高版本)</span><span class="sxs-lookup"><span data-stu-id="79a46-141">Android Skype for Business Client (version 6.16.0.9 and later)</span></span>
    
  - <span data-ttu-id="79a46-142">iPhone 业务客户端的 Skype (6.16.0 版及更高版本)</span><span class="sxs-lookup"><span data-stu-id="79a46-142">iPhone Skype for Business Client (version 6.16.0 and later)</span></span>
    
  - <span data-ttu-id="79a46-143">iPad Skype 业务客户端 (6.16.0 版及更高版本)</span><span class="sxs-lookup"><span data-stu-id="79a46-143">iPad Skype for Business Client (version 6.16.0 and later)</span></span>
    
## <a name="step-2---getting-or-transferring-toll-or-toll-free-service-phone-numbers"></a><span data-ttu-id="79a46-144">第 2 步 - 获取或转移收费或免费服务电话号码</span><span class="sxs-lookup"><span data-stu-id="79a46-144">Step 2 - Getting or transferring toll or toll-free service phone numbers</span></span>

<span data-ttu-id="79a46-145">Before you can create and set up your call queues, you will need to get or transfer your existing toll or toll-free service numbers.</span><span class="sxs-lookup"><span data-stu-id="79a46-145">Before you can create and set up your call queues, you will need to get or transfer your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="79a46-146">获取的收费或免费电话服务的电话号码后，它们将显示在**业务管理中心的 Skype** > **语音** > **电话号码**和**数字类型**列出将列为**服务-免费**.</span><span class="sxs-lookup"><span data-stu-id="79a46-146">After you get the toll or toll-free service phone numbers, they will show up in **Skype for Business admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**.</span></span> <span data-ttu-id="79a46-147">若要获得服务号码，看到[Skype 业务和 Microsoft 团队的前服务电话号码](getting-service-phone-numbers.md)或者如果要传输和现有服务号码，请参阅[传输到 Office 365 的电话号码](../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="79a46-147">To get your service numbers, see [Getting service phone numbers for Skype for Business and Microsoft Teams](getting-service-phone-numbers.md) or if you want to transfer and existing service number, see [Transfer phone numbers to Office 365](../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="79a46-148">如果您不在美国境内，不能使用业务管理中心为 Skype 来获得服务号码。</span><span class="sxs-lookup"><span data-stu-id="79a46-148">If you are outside the United States, you can't use the Skype for Business admin center to get service numbers.</span></span> <span data-ttu-id="79a46-149">转到[管理您的组织的电话号码](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)改为以查看如何做到从外面的美国。</span><span class="sxs-lookup"><span data-stu-id="79a46-149">Go to [Manage phone numbers for your organization](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) instead to see how to do it from the outside of the United States.</span></span>
  
## <a name="step-3---create-a-new-call-queue"></a><span data-ttu-id="79a46-150">第 3 步 - 创建新的呼叫队列</span><span class="sxs-lookup"><span data-stu-id="79a46-150">Step 3 - Create a new Call Queue</span></span>

<span data-ttu-id="79a46-151">In the **Skype for Business admin center**, click **Call routing** > **Call queues**, then click **Add new**:</span><span class="sxs-lookup"><span data-stu-id="79a46-151">In the **Skype for Business admin center**, click **Call routing** > **Call queues**, then click **Add new**:</span></span>
  
### <a name="set-the-call-queue-display-name-phone-number-and-domain-if-any"></a><span data-ttu-id="79a46-152">设置呼叫队列显示名称、电话号码和域（如有）</span><span class="sxs-lookup"><span data-stu-id="79a46-152">Set the call queue display name, phone number and domain (if any)</span></span>

![Setting up a call queue.](../images/37ecc300-a108-4294-8463-fce570dfce72.png)
***
<span data-ttu-id="79a46-154">![1 号](../images/sfbcallout1.png)</span><span class="sxs-lookup"><span data-stu-id="79a46-154">![Number 1](../images/sfbcallout1.png)</span></span><br/>
<span data-ttu-id="79a46-p110">**名称** 为呼叫队列输入描述性显示名称。此为必填字段，最多可以包含 64 个字符，其中包括空格。</span><span class="sxs-lookup"><span data-stu-id="79a46-p110">**Name** Enter a descriptive display name for the call queue. This is required and can contain up to 64 characters, including spaces. </span></span><br/> <span data-ttu-id="79a46-157">此名称将显示在传入呼叫的通知中。</span><span class="sxs-lookup"><span data-stu-id="79a46-157">This name will be displayed in the notification for the incoming call.</span></span>
***
<span data-ttu-id="79a46-158">![2 号](../images/sfbcallout2.png)</span><span class="sxs-lookup"><span data-stu-id="79a46-158">![Number 2](../images/sfbcallout2.png)</span></span><br/><span data-ttu-id="79a46-159">**电话号码** 为呼叫队列选择收费或免费服务电话号码。</span><span class="sxs-lookup"><span data-stu-id="79a46-159">**Phone number** Select a service toll or toll-free phone number for the call queue.</span></span> <span data-ttu-id="79a46-160">这是可选的。</span><span class="sxs-lookup"><span data-stu-id="79a46-160">This is optional.</span></span> <br/> <span data-ttu-id="79a46-161">如果没有列出任何号码，则需要首先获取服务号码，然后才能创建此服务队列。</span><span class="sxs-lookup"><span data-stu-id="79a46-161">If there aren't any listed, you need to get service numbers before you can create this call queue.</span></span> <span data-ttu-id="79a46-162">若要获得服务号码，请参阅[获得 Skype 业务和 Microsoft 团队的服务电话号码](getting-service-phone-numbers.md)</span><span class="sxs-lookup"><span data-stu-id="79a46-162">To get your service numbers, see [Getting service phone numbers for Skype for Business and Microsoft Teams](getting-service-phone-numbers.md)</span></span>
***
<span data-ttu-id="79a46-163">![数字 3](../images/sfbcallout3.png)</span><span class="sxs-lookup"><span data-stu-id="79a46-163">![Number 3](../images/sfbcallout3.png)</span></span><br/><span data-ttu-id="79a46-p113">**域** 如果此字段可用，请选择要使用的 Office 365 域。仅当你拥有多个用于 Office 365 的域时此字段才可用。如果你拥有多个域，必须从列表中选择域名。</span><span class="sxs-lookup"><span data-stu-id="79a46-p113">**Domain** If this is available, choose the Office 365 domain you want to use. This is only available if you have more than one domain being used with Office 365. If you have more than one, you must chose the domain name from the list. </span></span><br/> <span data-ttu-id="79a46-167">例如，你可能拥有类似以下名称的域： _contoso.com or redmond.contoso.com_</span><span class="sxs-lookup"><span data-stu-id="79a46-167">For example, you could have a domain like:  _contoso.com or redmond.contoso.com_</span></span>
   
### <a name="set-the-greeting-and-music-played-while-on-hold"></a><span data-ttu-id="79a46-168">设置通话保持时播放的问候语和音乐</span><span class="sxs-lookup"><span data-stu-id="79a46-168">Set the greeting and music played while on hold</span></span>

![Setting up a call queue.](../images/1d395a93-7cab-4178-9295-12d5379e20de.png)
  
***
<span data-ttu-id="79a46-170">![1 号](../images/sfbcallout1.png)</span><span class="sxs-lookup"><span data-stu-id="79a46-170">![Number 1](../images/sfbcallout1.png)</span></span><br/><span data-ttu-id="79a46-171">**问候语**是可选设置。</span><span class="sxs-lookup"><span data-stu-id="79a46-171">**Greeting** is optional.</span></span> <span data-ttu-id="79a46-172">这是呼叫队列编号为播放的调用中的人的问候语。</span><span class="sxs-lookup"><span data-stu-id="79a46-172">This is the greeting that is played for people who call in to the call queue number.</span></span> <br/> <span data-ttu-id="79a46-173">您可以上载音频文件 （.wav、.mp3 或.wma 格式）。</span><span class="sxs-lookup"><span data-stu-id="79a46-173">You can upload an audio file (.wav, .mp3, or .wma formats).</span></span>
***
<span data-ttu-id="79a46-174">![2 号](../images/sfbcallout2.png)</span><span class="sxs-lookup"><span data-stu-id="79a46-174">![Number 2](../images/sfbcallout2.png)</span></span><br/><span data-ttu-id="79a46-175">**音乐上保存**您可以提供呼叫队列中，等待使用默认音乐也可以上载.wav、 mp3 或.wma 用作候您自定义音乐格式的音频文件。</span><span class="sxs-lookup"><span data-stu-id="79a46-175">**Music on hold** You can either use the default Music on Hold provided with the call queue, or you can upload an audio file in .wav, mp3, or .wma formats to use as your custom Music on Hold.</span></span> 
   

### <a name="select-the-call-distribution-method"></a><span data-ttu-id="79a46-176">选择呼叫分发方法</span><span class="sxs-lookup"><span data-stu-id="79a46-176">Select the call distribution method</span></span>

![显示呼叫分发方法选项](../images/5d249515-d532-4af2-90da-011404028b89.png)
  
***
<span data-ttu-id="79a46-178">![1 号](../images/sfbcallout1.png)</span><span class="sxs-lookup"><span data-stu-id="79a46-178">![Number 1](../images/sfbcallout1.png)</span></span><br/><span data-ttu-id="79a46-179">**调用分发方法**您可以为您呼叫队列的通讯方法选择**助理**或**串行**。</span><span class="sxs-lookup"><span data-stu-id="79a46-179">**Call distribution method** You can choose either **Attendant** or **Serial** for your call queue distribution method.</span></span> <span data-ttu-id="79a46-180">所有新的和现有的呼叫队列将具有助理路由默认选中的。</span><span class="sxs-lookup"><span data-stu-id="79a46-180">All new and existing call queues will have attendant routing selected by default.</span></span> <span data-ttu-id="79a46-181">要使用串行传送，您必须显式选择在 UI 和 cmdlet 的**串行**路由选择选项。</span><span class="sxs-lookup"><span data-stu-id="79a46-181">To use serial routing, you must explicitly choose the **Serial** routing option in UI and cmdlets.</span></span> <br/><br/> <span data-ttu-id="79a46-182">当串行路由将选择并调用队列保存时，从队列调用将会响铃代理，逐一从代理列表的起始处开始。</span><span class="sxs-lookup"><span data-stu-id="79a46-182">When serial routing is chosen and the call queue is saved, the calls from the queue will ring your agents one by one, starting from the beginning of the agent list.</span></span> <span data-ttu-id="79a46-183">如果代理关闭或不会不拿起电话，呼叫响铃列表上的下一个代理并将尝试所有代理逐个直到它拾取或在队列中等待的时间。</span><span class="sxs-lookup"><span data-stu-id="79a46-183">If an agent dismisses or does not pick up a call, the call will ring the next agent on the list and will try all agents one by one until it is picked up or times out waiting in the queue.</span></span>  <br/><br/>  <span data-ttu-id="79a46-184">**注意：**串行路由将跳过代理处于**脱机状态**，其状态设置为**请勿打扰**，或有从该队列中获取调用的**取消**。</span><span class="sxs-lookup"><span data-stu-id="79a46-184">**Note:** Serial routing will skip agents who are **Offline**, have set their presence to **Do not Disturb**, or have **opted out** of getting calls from this queue.</span></span>  
   
### <a name="select-an-agent-opt-out-option"></a><span data-ttu-id="79a46-185">选择代理选择退出选项</span><span class="sxs-lookup"><span data-stu-id="79a46-185">Select an agent opt out option</span></span>

![显示代理退订复选框](../images/99279eff-db61-4acf-9b62-64be84b6414b.png)
  
***
<span data-ttu-id="79a46-187">![1 号](../images/sfbcallout1.png)</span><span class="sxs-lookup"><span data-stu-id="79a46-187">![Number 1](../images/sfbcallout1.png)</span></span><br/><span data-ttu-id="79a46-188">**代理选择退出选项**您可以选择允许呼叫队列代理选择不采用特定队列中的调用通过选择**代理选择退出选项**。</span><span class="sxs-lookup"><span data-stu-id="79a46-188">**Agent Opt out option** You can choose to allow call queue agents to opt out of taking calls from a particular queue by selecting **Agent Opt out option**.</span></span>  <br/> <span data-ttu-id="79a46-189">启用该选项，将在此队列中的所有代理启动或停止从在此调用队列接收呼叫。</span><span class="sxs-lookup"><span data-stu-id="79a46-189">Enabling this option allows all agents in this queue to start or stop receiving call from this call queue at will.</span></span> <span data-ttu-id="79a46-190">您可以撤消代理退出特权在任何时候通过清除该复选框，导致代理，让它们自动成为让此队列再次 （所有代理程序的默认设置）。</span><span class="sxs-lookup"><span data-stu-id="79a46-190">You can revoke the agent opt-out privilege at any time by clearing the check box, causing agents to become automatically opted in for this queue again (the default setting for all agents).</span></span>  <br/><br/> <span data-ttu-id="79a46-191">若要访问选择退出选项，工程师可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="79a46-191">To access the opt-out option, agents can do the following:</span></span>
 1. <span data-ttu-id="79a46-192">在其桌面 Skype 业务客户端中打开**选项**。</span><span class="sxs-lookup"><span data-stu-id="79a46-192">Open **Options** in their desktop Skype for Business client.</span></span> 
 2. <span data-ttu-id="79a46-193">**来电转接**选项卡上，单击**编辑设置联机**链接。</span><span class="sxs-lookup"><span data-stu-id="79a46-193">On the **Call Forwarding** tab, click the **Edit settings online** link.</span></span>
 3. <span data-ttu-id="79a46-194">在用户设置页上单击**调用队列**，，然后清除他们要退出任何队列对应的复选框。</span><span class="sxs-lookup"><span data-stu-id="79a46-194">On the user settings page, click **Call Queues**, and then clear the check boxes for any queues for which they want to opt out.</span></span>
 
    > [!NOTE] 
    > <span data-ttu-id="79a46-195">代理使用 Mac，移动，或 Lync 2013 的客户端或混合语音用户都承载内部使用 Skype 业务 2015年服务器，可以转到[https://aka.ms/cqsettings](https://aka.ms/cqsettings)访问 opt out 选项。</span><span class="sxs-lookup"><span data-stu-id="79a46-195">Agents using Mac, mobile, or Lync 2013 clients, or Hybrid Voice users who are hosted on-premises using Skype for Business 2015 server, can go to [https://aka.ms/cqsettings](https://aka.ms/cqsettings) to access the opt out option.</span></span>
   
### <a name="add-call-agents-to-a-call-queue"></a><span data-ttu-id="79a46-196">向呼叫队列添加呼叫代理</span><span class="sxs-lookup"><span data-stu-id="79a46-196">Add call agents to a call queue</span></span>

![Set up call queues.](../images/skype-for-business-add-agents-to-call-queue.png)
  
***
![1 号](../images/sfbcallout1.png)<br/><br/><span data-ttu-id="79a46-199">可以调用代理 (最大 50):</span><span class="sxs-lookup"><span data-stu-id="79a46-199">Call agents (50 maximum) can be:</span></span>
*    <span data-ttu-id="79a46-200">在线用户使用**电话系统**许可证并启用企业语音或与调用计划。</span><span class="sxs-lookup"><span data-stu-id="79a46-200">An Online user with a **Phone System** license and enabled for Enterprise Voice or with a Calling Plan.</span></span> <br/><br/> <span data-ttu-id="79a46-201">**注意：** 要重定向调用的人在组织中处于联机状态，它们必须拥有**电话系统**许可证和企业语音为启用或具有一个调用计划。</span><span class="sxs-lookup"><span data-stu-id="79a46-201">**Note:**  To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have a Calling Plan.</span></span> <span data-ttu-id="79a46-202">请参阅[指派的 Skype 业务和 Microsoft 小组的许可证](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="79a46-202">See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span> <span data-ttu-id="79a46-203">要为他们启用企业语音，可以使用 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="79a46-203">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="79a46-204">例如运行： `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="79a46-204">For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span> <br/><br/>
*    <span data-ttu-id="79a46-205">与联机用户与**电话系统**许可证并调用计划添加到 Office 365 组、 已启用邮件的通讯组列表或安全组。</span><span class="sxs-lookup"><span data-stu-id="79a46-205">Online users with a with a **Phone System** license and a Calling Plan that are added to an Office 365 Group, a mail-enabled Distribution List, or a Security Group.</span></span> <span data-ttu-id="79a46-206">It might take up to 30 minutes for a new agent added for a distribution list or a security group to start receiving calls from a call queue.</span><span class="sxs-lookup"><span data-stu-id="79a46-206">It might take up to 30 minutes for a new agent added for a distribution list or a security group to start receiving calls from a call queue.</span></span> <span data-ttu-id="79a46-207">新创建的通讯组列表或安全组可能需要 48 小时变为可用于调用队列。</span><span class="sxs-lookup"><span data-stu-id="79a46-207">A newly created distribution list or security group might take up to 48 hours to become available to be used with call queues.</span></span> <span data-ttu-id="79a46-208">新创建的 Office 365 组会几乎立即可用。</span><span class="sxs-lookup"><span data-stu-id="79a46-208">Newly created Office 365 Groups are available almost immediately.</span></span> <br/> 

    > [!NOTE] 
    > <span data-ttu-id="79a46-209">用户承载内部使用 Lync Server 2010 中不受支持。</span><span class="sxs-lookup"><span data-stu-id="79a46-209">Users hosted on-premises using Lync Server 2010 aren't supported.</span></span>           
   
### <a name="set-the-maximum-queue-size-and-maximum-wait-time"></a><span data-ttu-id="79a46-210">设置队列最大大小和最长等待时间。</span><span class="sxs-lookup"><span data-stu-id="79a46-210">Set the maximum queue size and maximum wait time</span></span>

![Set up a call queue.](../images/3f018734-16fe-458b-827d-71fc25155cde.png)
  
***
<span data-ttu-id="79a46-212">![1 号](../images/sfbcallout1.png)</span><span class="sxs-lookup"><span data-stu-id="79a46-212">![Number 1](../images/sfbcallout1.png)</span></span><br/><br/><span data-ttu-id="79a46-213">**队列中的最大呼叫数** 使用此字段来设置同一时间可以在队列中等待的最大呼叫数。</span><span class="sxs-lookup"><span data-stu-id="79a46-213">**Maximum calls in the queue** Use this to set the maximum calls that can wait in the queue at the same time.</span></span> <span data-ttu-id="79a46-214">默认值为 50，但其范围可以从 0 到 200.达到此限制时，将具有设置在**当达到最大重试次数**设置下面的方式处理呼叫。</span><span class="sxs-lookup"><span data-stu-id="79a46-214">The default is 50, but it can range from 0 to 200.When this limit is reached, the call will be handled in way you have set on the **When the maximum number of calls is reached** setting below.</span></span>
***
<span data-ttu-id="79a46-215">![2 号](../images/sfbcallout2.png)</span><span class="sxs-lookup"><span data-stu-id="79a46-215">![Number 2](../images/sfbcallout2.png)</span></span><br/><br/><span data-ttu-id="79a46-216">**当达到最大重试次数**当调用队列达到最大值 （设置使用**调用队列中的最大值**设置） 时，您可以选择新的传入呼叫会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="79a46-216">**When the maximum number of calls is reached** When the call queue reaches its maximum size (set using the **Maximum calls in the queue** setting), you can choose what happens to new incoming calls.</span></span>
*    <span data-ttu-id="79a46-217">**断开连接并显示繁忙信号** 呼叫将断开连接。</span><span class="sxs-lookup"><span data-stu-id="79a46-217">**Disconnect with a busy signal** The call will be disconnected.</span></span>
*    <span data-ttu-id="79a46-218">**转发到此调用**当您选择此选项时，您将具有下列选项：</span><span class="sxs-lookup"><span data-stu-id="79a46-218">**Forward this call to** When you choose this, you will have these options:</span></span>
     *    <span data-ttu-id="79a46-219">**在您的公司的人**在线用户使用**电话系统**许可证和能够使用企业语音或者具有一个调用计划。</span><span class="sxs-lookup"><span data-stu-id="79a46-219">**Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have a Calling Plan.</span></span> <span data-ttu-id="79a46-220">你可以通过此设置将呼叫者直接转到语音邮件。</span><span class="sxs-lookup"><span data-stu-id="79a46-220">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="79a46-221">这样做，请选择**您的公司中的人**并设置此人让其将直接转发至语音邮件的电话。</span><span class="sxs-lookup"><span data-stu-id="79a46-221">To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span> <br/> <br/><span data-ttu-id="79a46-222">若要了解有关授权所需的语音邮件，请参阅[设置语音邮件电话系统](../what-is-phone-system-in-office-365/phone-system-voicemail/set-up-phone-system-voicemail.md)。</span><span class="sxs-lookup"><span data-stu-id="79a46-222">To learn about licensing required for voicemail, see [Set up Phone System voicemail](../what-is-phone-system-in-office-365/phone-system-voicemail/set-up-phone-system-voicemail.md).</span></span> 
     
        > [!Note]
        > <span data-ttu-id="79a46-223">用户承载内部使用 Lync Server 2010 中不受支持。</span><span class="sxs-lookup"><span data-stu-id="79a46-223">Users hosted on-premises using Lync Server 2010 aren't supported.</span></span><br/>
     
     *    <span data-ttu-id="79a46-224">**调用队列**您必须已创建了另一个调用队列，但执行操作后，您可以选择该呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="79a46-224">**Call Queue** You must have already created another call queue, but after you do, you can select that call queue.</span></span>
     *    <span data-ttu-id="79a46-225">**自动助理**您必须已创建的自动助理，但执行操作后，您可以选择该自动助理。</span><span class="sxs-lookup"><span data-stu-id="79a46-225">**Auto Attendant** You must have already created an auto attendant, but after you do, you can select that auto attendant.</span></span> <span data-ttu-id="79a46-226">请参阅[设置电话系统自动助理](set-up-a-phone-system-auto-attendant.md)。</span><span class="sxs-lookup"><span data-stu-id="79a46-226">See [Set up a Phone System auto attendant](set-up-a-phone-system-auto-attendant.md).</span></span>
***
<span data-ttu-id="79a46-227">![数字 3](../images/sfbcallout3.png)</span><span class="sxs-lookup"><span data-stu-id="79a46-227">![Number 3](../images/sfbcallout3.png)</span></span><br/><br/><span data-ttu-id="79a46-p123">**呼叫在队列中可以等待多长时间** 你还可以决定呼叫在超时和需要重新定向或断开连接前可以在队列中保留的时间。重新定向的目的地取决于" **当呼叫超时时**"中的设置。你可以将此时间设置为 0 到 45 分钟。</span><span class="sxs-lookup"><span data-stu-id="79a46-p123">**How long a call can wait in the queue** You can also decide how much time a call can be on hold in the queue before it times out and needs to be redirected or disconnected. Where it will be redirected is based on how you set the **When a call times out** setting. You can set a time from 0 to 45 minutes. </span></span><br/><br/> <span data-ttu-id="79a46-231">以秒为单位，都可以设置超时值以 15 秒的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="79a46-231">The timeout value can be set in seconds, at 15-second intervals.</span></span> <span data-ttu-id="79a46-232">这使您可以使用细粒度操作调用流。</span><span class="sxs-lookup"><span data-stu-id="79a46-232">This allows you to manipulate the call flow with finer granularity.</span></span> <span data-ttu-id="79a46-233">例如，您可以指定在 30 秒内由代理不回答任何调用进入目录搜索自动助理。</span><span class="sxs-lookup"><span data-stu-id="79a46-233">For example, you could specify that any calls that are not answered by an agent within 30 seconds go to a Directory Search Auto Attendant.</span></span> 

***
<span data-ttu-id="79a46-234">![数字 4](../images/sfbcallout4.png)</span><span class="sxs-lookup"><span data-stu-id="79a46-234">![Number 4](../images/sfbcallout4.png)</span></span><br/><br/><span data-ttu-id="79a46-235">**当呼叫超时时** 当呼叫达到" **呼叫在队列中可以等待多长时间**"中设置的限制时，你可以选择如何处理此呼叫：</span><span class="sxs-lookup"><span data-stu-id="79a46-235">**When a call times out** When the call reaches the limit you set on the **How long a call can wait in the queue** setting, you can choose what happens to this call:</span></span>
*    <span data-ttu-id="79a46-236">**断开连接** 呼叫将断开连接。</span><span class="sxs-lookup"><span data-stu-id="79a46-236">**Disconnect** The call will be disconnected.</span></span>
*    <span data-ttu-id="79a46-237">**转发到此调用**当您选择此选项时，您将具有下列选项：</span><span class="sxs-lookup"><span data-stu-id="79a46-237">**Forward this call to** When you choose this, you will have these options:</span></span>
     *    <span data-ttu-id="79a46-238">**在您的公司的人**在线用户使用**电话系统**许可证和能够使用企业语音或者具有调用计划。</span><span class="sxs-lookup"><span data-stu-id="79a46-238">**Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have Calling Plans.</span></span> <span data-ttu-id="79a46-239">你可以通过此设置将呼叫者直接转到语音邮件。</span><span class="sxs-lookup"><span data-stu-id="79a46-239">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="79a46-240">这样做，请选择**您的公司中的人**并设置此人让其将直接转发至语音邮件的电话。</span><span class="sxs-lookup"><span data-stu-id="79a46-240">To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span> </br><br/>  <span data-ttu-id="79a46-241">若要了解有关授权所需的语音邮件，请参阅[设置语音邮件电话系统](../what-is-phone-system-in-office-365/phone-system-voicemail/set-up-phone-system-voicemail.md)。</span><span class="sxs-lookup"><span data-stu-id="79a46-241">To learn about licensing required for voicemail, see [Set up Phone System voicemail](../what-is-phone-system-in-office-365/phone-system-voicemail/set-up-phone-system-voicemail.md).</span></span> 

        > [!Note]
        > <span data-ttu-id="79a46-242">用户承载内部使用 Lync Server 2010 中不受支持。</span><span class="sxs-lookup"><span data-stu-id="79a46-242">Users hosted on-premises using Lync Server 2010 aren't supported.</span></span><br/>

     *    <span data-ttu-id="79a46-243">**调用队列**您必须已创建了另一个调用队列，但执行操作后，您可以选择该呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="79a46-243">**Call Queue** You must have already created another call queue, but after you do, you can select that call queue.</span></span>
     *    <span data-ttu-id="79a46-244">**自动助理**您必须已创建的自动助理，但执行操作后，您可以选择该自动助理。</span><span class="sxs-lookup"><span data-stu-id="79a46-244">**Auto Attendant** You must have already created an auto attendant, but after you do, you can select that auto attendant.</span></span> <span data-ttu-id="79a46-245">请参阅[设置电话系统自动助理](set-up-a-phone-system-auto-attendant.md)。</span><span class="sxs-lookup"><span data-stu-id="79a46-245">See [Set up a Phone System auto attendant](set-up-a-phone-system-auto-attendant.md).</span></span>
   
## <a name="changing-the-users-caller-id-to-be-a-call-queues-phone-number"></a><span data-ttu-id="79a46-246">更改用户的呼叫方 ID，才能调用队列的电话号码</span><span class="sxs-lookup"><span data-stu-id="79a46-246">Changing the user's Caller ID to be a call queue's phone number</span></span>

<span data-ttu-id="79a46-247">您可以通过更改出站呼叫的呼叫队列及其呼叫方 ID 改为创建使用**New CallingLineIdentity** cmdlet 策略保护用户的标识。</span><span class="sxs-lookup"><span data-stu-id="79a46-247">You can protect a user's identity by changing their caller ID for the outbound calls to a call queue instead by creating a policy using the **New-CallingLineIdentity** cmdlet.</span></span>
  
<span data-ttu-id="79a46-248">若要执行此操作，请运行：</span><span class="sxs-lookup"><span data-stu-id="79a46-248">To do this, run:</span></span>
  
```
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

<span data-ttu-id="79a46-249">然后将策略应用到用户使用**授予 CallingLineIdentity** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="79a46-249">Then apply the policy to the user using the **Grant-CallingLineIdentity** cmdlet.</span></span> <span data-ttu-id="79a46-250">若要执行此操作，请运行：</span><span class="sxs-lookup"><span data-stu-id="79a46-250">To do this, run:</span></span>
  
```
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

<span data-ttu-id="79a46-251">您可以了解有关如何更改您的组织中的呼叫方 ID 设置[此处](../what-are-calling-plans-in-office-365/how-can-caller-id-be-used-in-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="79a46-251">You can get more information on how to make changes to caller ID settings in your organization [here](../what-are-calling-plans-in-office-365/how-can-caller-id-be-used-in-your-organization.md).</span></span>
  
## <a name="want-to-know-more"></a><span data-ttu-id="79a46-252">希望了解更多信息吗？</span><span class="sxs-lookup"><span data-stu-id="79a46-252">Want to know more?</span></span>

<span data-ttu-id="79a46-253">还可以使用 Windows PowerShell 来创建和设置呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="79a46-253">You can also use Windows PowerShell to create and set up call queues.</span></span>
  
### <a name="call-queue-cmdlets"></a><span data-ttu-id="79a46-254">呼叫队列 cmdlet</span><span class="sxs-lookup"><span data-stu-id="79a46-254">Call queue cmdlets</span></span>

<span data-ttu-id="79a46-255">以下是管理呼叫队列时需要使用的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="79a46-255">Here are the cmdlets that you need to manage a call queue.</span></span>
  
- [<span data-ttu-id="79a46-256">新 CsHuntgroup</span><span class="sxs-lookup"><span data-stu-id="79a46-256">New-CsHuntgroup</span></span>](https://technet.microsoft.com/en-us/library/mt796459.aspx)
    
- [<span data-ttu-id="79a46-257">一组 CsHuntgroup</span><span class="sxs-lookup"><span data-stu-id="79a46-257">Set-CsHuntgroup</span></span>](https://technet.microsoft.com/en-us/library/mt796457.aspx)
    
- [<span data-ttu-id="79a46-258">获得 CsHuntgroup</span><span class="sxs-lookup"><span data-stu-id="79a46-258">Get-CsHuntgroup</span></span>](https://technet.microsoft.com/en-us/library/mt796458.aspx)
    
- [<span data-ttu-id="79a46-259">删除 CsHuntgroup</span><span class="sxs-lookup"><span data-stu-id="79a46-259">Remove-CsHuntgroup</span></span>](https://technet.microsoft.com/en-us/library/mt796456.aspx)
    
### <a name="more-about-windows-powershell"></a><span data-ttu-id="79a46-260">有关 Windows PowerShell 的详细信息</span><span class="sxs-lookup"><span data-stu-id="79a46-260">More about Windows PowerShell</span></span>

- <span data-ttu-id="79a46-p128">对于 Windows PowerShell，它全部是关于管理用户以及允许或不允许用户执行的操作。当你有多个要执行的任务时，使用 Windows PowerShell 可以通过能够简化日常工作的单点管理来管理 Office 365 和 Skype for Business Online。若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="79a46-p128">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="79a46-264">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="79a46-264">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="79a46-265">为什么需要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="79a46-265">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="79a46-p129">例如当你一次对多个用户更改设置时，Windows PowerShell 比起仅使用 Office 365 管理中心，在速度、简明性和效率方面具有许多优势。通过以下主题了解这些优势：</span><span class="sxs-lookup"><span data-stu-id="79a46-p129">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="79a46-268">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="79a46-268">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="79a46-269">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="79a46-269">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="79a46-270">使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务</span><span class="sxs-lookup"><span data-stu-id="79a46-270">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="79a46-271">相关主题</span><span class="sxs-lookup"><span data-stu-id="79a46-271">Related topics</span></span>
[<span data-ttu-id="79a46-272">下面是 Office 365 中的电话系统的功能</span><span class="sxs-lookup"><span data-stu-id="79a46-272">Here's what you get with Phone System in Office 365</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="79a46-273">获取 Skype for Business 和 Microsoft Teams 的服务电话号码</span><span class="sxs-lookup"><span data-stu-id="79a46-273">Getting service phone numbers for Skype for Business and Microsoft Teams</span></span>](getting-service-phone-numbers.md)

[<span data-ttu-id="79a46-274">音频会议和通话套餐的国家/地区可用性</span><span class="sxs-lookup"><span data-stu-id="79a46-274">Country and region availability for Audio Conferencing and Calling Plans</span></span>](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

## <a name="feedback"></a><span data-ttu-id="79a46-275">反馈意见？</span><span class="sxs-lookup"><span data-stu-id="79a46-275">Feedback?</span></span>
<span data-ttu-id="79a46-276">提供产品反馈意见或让我们知道我们所执行的信息，请参阅[Skype 业务反馈](https://www.skypefeedback.com)。</span><span class="sxs-lookup"><span data-stu-id="79a46-276">To provide product feedback or to let us know how we're doing, see [Skype for Business Feedback](https://www.skypefeedback.com).</span></span>