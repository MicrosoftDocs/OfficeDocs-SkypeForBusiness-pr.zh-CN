---
title: 在 Microsoft 团队中创建呼叫队列
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
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
description: 了解如何为具有 Microsoft 团队的呼叫队列设置电话系统，这些团队提供问候语、举行音乐、呼叫重定向和其他功能。
ms.openlocfilehash: b9c611a31550be8dbae541ef24c63c746d5edb86
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2020
ms.locfileid: "49033007"
---
# <a name="create-a-call-queue"></a><span data-ttu-id="d7f5b-103">创建呼叫队列</span><span class="sxs-lookup"><span data-stu-id="d7f5b-103">Create a call queue</span></span>

<span data-ttu-id="d7f5b-104">通话队列提供了一种将呼叫者路由到组织中的人员的方法，可帮助解决特定问题。</span><span class="sxs-lookup"><span data-stu-id="d7f5b-104">Call queues provide a method of routing callers to people in your organization who can help with with a particular issue or question.</span></span> <span data-ttu-id="d7f5b-105">通话将一次分发给队列中的人员， (称为 *代理* ) 的人员。</span><span class="sxs-lookup"><span data-stu-id="d7f5b-105">Calls are distributed one at a time to the people in the queue (who are known as *agents* ).</span></span> 

<span data-ttu-id="d7f5b-106">通话队列提供：</span><span class="sxs-lookup"><span data-stu-id="d7f5b-106">Call queues provide:</span></span>

- <span data-ttu-id="d7f5b-107">一条问候语。</span><span class="sxs-lookup"><span data-stu-id="d7f5b-107">A greeting message.</span></span>

- <span data-ttu-id="d7f5b-108">用户在队列中等待保留的音乐。</span><span class="sxs-lookup"><span data-stu-id="d7f5b-108">Music while people are waiting on hold in a queue.</span></span>

- <span data-ttu-id="d7f5b-109">拨打电话——首先 *推出* (FIFO) 订单到代理。</span><span class="sxs-lookup"><span data-stu-id="d7f5b-109">Call routing - in *First In, First Out* (FIFO) order - to agents.</span></span>

- <span data-ttu-id="d7f5b-110">队列溢出和超时的处理选项。</span><span class="sxs-lookup"><span data-stu-id="d7f5b-110">Handling options for queue overflow and timeout.</span></span>

<span data-ttu-id="d7f5b-111">请确保你拥有 [团队自动助理和呼叫队列](plan-auto-attendant-call-queue.md) 的阅读计划，然后按照本文中的步骤操作，然后按照 [入门步骤](plan-auto-attendant-call-queue.md#getting-started) 操作。</span><span class="sxs-lookup"><span data-stu-id="d7f5b-111">Be sure you have read [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md) and followed the [getting started steps](plan-auto-attendant-call-queue.md#getting-started) before you follow the procedures in this articles.</span></span>

<span data-ttu-id="d7f5b-112">若要设置呼叫队列，请在 "团队管理中心" 中，展开 " **语音** "，单击 " **呼叫队列** "，然后单击 " **添加** "。</span><span class="sxs-lookup"><span data-stu-id="d7f5b-112">To set up a call queue, in the Teams admin center, expand **Voice** , click **Call queues** , and then click **Add**.</span></span>

## <a name="resource-account-and-language"></a><span data-ttu-id="d7f5b-113">资源帐户和语言</span><span class="sxs-lookup"><span data-stu-id="d7f5b-113">Resource account and language</span></span>

![资源帐户和语言设置的屏幕截图](media/call-queue-name-language.png)

1. <span data-ttu-id="d7f5b-115">键入呼叫队列的名称。</span><span class="sxs-lookup"><span data-stu-id="d7f5b-115">Type a name for the call queue.</span></span> <span data-ttu-id="d7f5b-116">当代理接收来自队列的传入呼叫时，将看到此名称。</span><span class="sxs-lookup"><span data-stu-id="d7f5b-116">Agents will see this name when they receive an incoming call from the queue.</span></span>

2. <span data-ttu-id="d7f5b-117">单击 " **添加帐户** "，搜索要与此通话队列一起使用的资源帐户，单击 " **添加** "，然后单击 " **添加** "。</span><span class="sxs-lookup"><span data-stu-id="d7f5b-117">Click **Add accounts** , search for the resource account that you want to use with this call queue, click **Add** , and then click **Add**.</span></span>

3. <span data-ttu-id="d7f5b-118">选择一种语言。</span><span class="sxs-lookup"><span data-stu-id="d7f5b-118">Choose a language.</span></span> <span data-ttu-id="d7f5b-119">此语言将用于系统生成的语音提示和语音邮件操作 (如果启用这些功能) 。</span><span class="sxs-lookup"><span data-stu-id="d7f5b-119">This language will be used for system-generated voice prompts and voicemail transcription (if you enable them).</span></span>

## <a name="greetings-and-hold-music"></a><span data-ttu-id="d7f5b-120">问候语和定格音乐</span><span class="sxs-lookup"><span data-stu-id="d7f5b-120">Greetings and hold music</span></span>

<span data-ttu-id="d7f5b-121">指定是否希望在呼叫者到达队列时向其播放问候语。</span><span class="sxs-lookup"><span data-stu-id="d7f5b-121">Specify if you want to play a greeting to callers when they arrive in the queue.</span></span> <span data-ttu-id="d7f5b-122">必须上载包含要播放的问候语的 MP3、WAV 或 WMA 文件。</span><span class="sxs-lookup"><span data-stu-id="d7f5b-122">You must upload an MP3, WAV, or WMA file containing the greeting that you want to play.</span></span>

<span data-ttu-id="d7f5b-123">当呼叫者在队列中保留时，团队向呼叫者提供默认音乐。</span><span class="sxs-lookup"><span data-stu-id="d7f5b-123">Teams provides default music to callers while they are on hold in a queue.</span></span> <span data-ttu-id="d7f5b-124">如果要播放特定音频文件，请选择 " **播放音频文件** " 并上载 MP3、WAV 或 WMA 文件。</span><span class="sxs-lookup"><span data-stu-id="d7f5b-124">If you want to play a specific audio file, choose **Play an audio file** and upload an MP3, WAV, or WMA file.</span></span>

> [!NOTE]
> <span data-ttu-id="d7f5b-125">上载的录制不能大于 5 MB。</span><span class="sxs-lookup"><span data-stu-id="d7f5b-125">The uploaded recording can be no larger than 5 MB.</span></span>
> <span data-ttu-id="d7f5b-126">团队通话队列中提供的默认音乐由您的组织提供的任何版税均免费提供。</span><span class="sxs-lookup"><span data-stu-id="d7f5b-126">The default music supplied in Teams call queues is free of any royalties payable by your organization.</span></span> 

## <a name="call-agents"></a><span data-ttu-id="d7f5b-127">呼叫代理</span><span class="sxs-lookup"><span data-stu-id="d7f5b-127">Call agents</span></span>

<span data-ttu-id="d7f5b-128">所选呼叫代理必须是以下各项之一：</span><span class="sxs-lookup"><span data-stu-id="d7f5b-128">Call agents selected must be one of the following:</span></span> 

- <span data-ttu-id="d7f5b-129">使用电话系统许可证和启用企业语音的联机用户</span><span class="sxs-lookup"><span data-stu-id="d7f5b-129">Online users with a Phone System license and Enterprise Voice enabled</span></span>
- <span data-ttu-id="d7f5b-130">使用呼叫计划的在线用户</span><span class="sxs-lookup"><span data-stu-id="d7f5b-130">Online users with a Calling Plan</span></span>
- <span data-ttu-id="d7f5b-131">本地 Skype for Business 服务器用户</span><span class="sxs-lookup"><span data-stu-id="d7f5b-131">On-premises Skype for Business Server users</span></span>
- <span data-ttu-id="d7f5b-132">如果你的代理正在使用 Microsoft 团队应用进行呼叫队列呼叫，则他们必须处于 TeamsOnly 模式。</span><span class="sxs-lookup"><span data-stu-id="d7f5b-132">If your agents are using the Microsoft Teams app for call queue calls, they need to be in TeamsOnly mode.</span></span>

![呼叫队列的用户和组设置的屏幕截图](media/call-queue-users-groups.png)

<span data-ttu-id="d7f5b-134">你可以通过组将多达20个代理分别和最多添加到200个代理。</span><span class="sxs-lookup"><span data-stu-id="d7f5b-134">You can add up to 20 agents individually and up to 200 agents via groups.</span></span>

<span data-ttu-id="d7f5b-135">若要将用户添加到队列，请依次单击 " **添加用户** "、"搜索用户"、" **添加** "，然后单击 " **添加** "。</span><span class="sxs-lookup"><span data-stu-id="d7f5b-135">To add a user to the queue, click **Add users** , search for the user, click **Add** , and then click **Add**.</span></span>

<span data-ttu-id="d7f5b-136">若要将组添加到队列，请依次单击 " **添加组** "、"搜索组"、" **添加** "，然后单击 " **添加** "。</span><span class="sxs-lookup"><span data-stu-id="d7f5b-136">To add a group to the queue, click **Add groups** , search for the group, click **Add** , and then click **Add**.</span></span> <span data-ttu-id="d7f5b-137">你可以使用通讯组列表、安全组和 Microsoft 365 组或 Microsoft 团队团队。</span><span class="sxs-lookup"><span data-stu-id="d7f5b-137">You can use distribution lists, security groups, and Microsoft 365 groups or Microsoft Teams teams.</span></span>

> [!NOTE]
> <span data-ttu-id="d7f5b-138">添加到组的新用户最多可能需要八个小时才能达到首次通话的时间。</span><span class="sxs-lookup"><span data-stu-id="d7f5b-138">New users added to a group can take up to eight hours for their first call to arrive.</span></span>

## <a name="call-routing"></a><span data-ttu-id="d7f5b-139">呼叫路由</span><span class="sxs-lookup"><span data-stu-id="d7f5b-139">Call routing</span></span>

![会议模式和路由方法设置的屏幕截图](media/call-queue-conference-mode-routing-method.png)

<span data-ttu-id="d7f5b-141">在代理接受呼叫后， **会议模式** 会显著减少呼叫者连接到代理所需的时间量。</span><span class="sxs-lookup"><span data-stu-id="d7f5b-141">**Conference mode** significantly reduces the amount of time it takes for a caller to be connected to an agent, after the agent accepts the call.</span></span> <span data-ttu-id="d7f5b-142">若要使会议模式正常工作，呼叫队列中的代理必须使用下列客户端之一：</span><span class="sxs-lookup"><span data-stu-id="d7f5b-142">For conference mode to work, agents in the call queue must use one of the following clients:</span></span>

  - <span data-ttu-id="d7f5b-143">Microsoft 团队桌面客户端、Android 应用或 iOS 应用的最新版本</span><span class="sxs-lookup"><span data-stu-id="d7f5b-143">The latest version of the Microsoft Teams desktop client, Android app, or iOS app</span></span>
  - <span data-ttu-id="d7f5b-144">Microsoft 团队手机版本 1449/1.0.94.2020051601 或更高版本</span><span class="sxs-lookup"><span data-stu-id="d7f5b-144">Microsoft Teams phone version 1449/1.0.94.2020051601 or later</span></span>
  
<span data-ttu-id="d7f5b-145">代理的团队帐户需要设置为 "仅限团队" 模式。</span><span class="sxs-lookup"><span data-stu-id="d7f5b-145">Agents' Teams accounts need to be set to Teams-only mode.</span></span> <span data-ttu-id="d7f5b-146">不满足要求的工程师不会包含在 "呼叫" 传送列表中。</span><span class="sxs-lookup"><span data-stu-id="d7f5b-146">Agents who don't meet the requirements aren't included in the call routing list.</span></span> <span data-ttu-id="d7f5b-147">如果你的代理全部使用兼容的客户端，我们建议你为通话队列启用会议模式。</span><span class="sxs-lookup"><span data-stu-id="d7f5b-147">We recommend enabling conference mode for your call queues if your agents are all using compatible clients.</span></span>

> [!NOTE]
> <span data-ttu-id="d7f5b-148">会议模式不支持忙闲。</span><span class="sxs-lookup"><span data-stu-id="d7f5b-148">Busy on Busy is not supported by conference mode.</span></span> <span data-ttu-id="d7f5b-149">如果未启用基于状态的路由，则非呼叫队列呼叫中的代理仍会显示呼叫队列呼叫。</span><span class="sxs-lookup"><span data-stu-id="d7f5b-149">Agents on non-call queue calls may still be presented with a call queue call if presence-based routing is not enabled.</span></span>

<span data-ttu-id="d7f5b-150">**路由方法** 确定代理从队列接收呼叫的顺序。</span><span class="sxs-lookup"><span data-stu-id="d7f5b-150">**Routing method** determines the order in which agents receive calls from the queue.</span></span> <span data-ttu-id="d7f5b-151">从以下选项中选择：</span><span class="sxs-lookup"><span data-stu-id="d7f5b-151">Choose from these options:</span></span>

- <span data-ttu-id="d7f5b-152">**助理路由** 同时响铃队列中的所有代理。</span><span class="sxs-lookup"><span data-stu-id="d7f5b-152">**Attendant routing** rings all agents in the queue at the same time.</span></span> <span data-ttu-id="d7f5b-153">获取呼叫的第一个呼叫代理将获取呼叫。</span><span class="sxs-lookup"><span data-stu-id="d7f5b-153">The first call agent to pick up the call gets the call.</span></span>

- <span data-ttu-id="d7f5b-154">**串行路由** 按 " **呼叫代理** " 列表中指定的顺序逐个响铃所有呼叫代理。</span><span class="sxs-lookup"><span data-stu-id="d7f5b-154">**Serial routing** rings all call agents one by one in the order specified in the **Call agents** list.</span></span> <span data-ttu-id="d7f5b-155">如果代理程序已关闭或未接听呼叫，则呼叫将拨打下一个代理，并且将尝试所有代理，直到它已被获取或超时。</span><span class="sxs-lookup"><span data-stu-id="d7f5b-155">If an agent dismisses or does not pick up a call, the call will ring the next agent and will try all agents until it is picked up or times out.</span></span>

- <span data-ttu-id="d7f5b-156">**循环法** 平衡传入呼叫的路由，以便每个呼叫代理从队列中获得相同数量的通话。</span><span class="sxs-lookup"><span data-stu-id="d7f5b-156">**Round robin** balances the routing of incoming calls so that each call agent gets the same number of calls from the queue.</span></span> <span data-ttu-id="d7f5b-157">这在入站销售环境中可能需要确保所有呼叫代理的同等机遇。</span><span class="sxs-lookup"><span data-stu-id="d7f5b-157">This may be desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

- <span data-ttu-id="d7f5b-158">**最长空闲** 路线每次通话时间最长的代理。</span><span class="sxs-lookup"><span data-stu-id="d7f5b-158">**Longest idle** routes each call to the agent who has been idle the longest time.</span></span> <span data-ttu-id="d7f5b-159">如果代理的状态可用或其状态已离开10分钟以内，则会被视为空闲。</span><span class="sxs-lookup"><span data-stu-id="d7f5b-159">An agent is considered idle if their presence state is Available or if their presence state has been Away for less than 10 minutes.</span></span> <span data-ttu-id="d7f5b-160">如果代理的状态已超过10分钟，则不会被视为空闲，并且在他们将其状态更改为 "可用" 之前，不符合接收呼叫的条件。</span><span class="sxs-lookup"><span data-stu-id="d7f5b-160">Agents whose presence state has been Away for more than 10 minutes are not considered idle and will not be eligible to receive calls until they change their presence to Available.</span></span> 

!["路由"、"退出" 和 "警报时间" 设置的屏幕截图](media/call-queue-presence-agents-time.png)


<span data-ttu-id="d7f5b-162">**基于状态的路由** 使用呼叫代理的可用性状态来确定是否应将代理包括在所选路由方法的 "呼叫路由" 列表中。</span><span class="sxs-lookup"><span data-stu-id="d7f5b-162">**Presence-based routing** uses the availability status of call agents to determine whether an agent should be included in the call routing list for the selected routing method.</span></span> <span data-ttu-id="d7f5b-163">其可用性状态设置为 " **可用** " 的呼叫代理包括在 "呼叫" 传送列表中，并且可以接收呼叫。</span><span class="sxs-lookup"><span data-stu-id="d7f5b-163">Call agents whose availability status is set to **Available** are included in the call routing list and can receive calls.</span></span> <span data-ttu-id="d7f5b-164">其可用性状态设置为任何其他状态的代理将从呼叫路由列表中排除，并且在其可用性状态更改为 " **可用** " 之前不会收到呼叫。</span><span class="sxs-lookup"><span data-stu-id="d7f5b-164">Agents whose availability status is set to any other status are excluded from the call routing list and won't receive calls until their availability status changes back to **Available**.</span></span> 

<span data-ttu-id="d7f5b-165">你可以使用任何路由方法启用基于状态的呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="d7f5b-165">You can enable presence-based call routing with any of the routing methods.</span></span>

<span data-ttu-id="d7f5b-166">如果某个代理选择退出呼叫，则无论其可用性状态如何设置，它们都不会包含在 "呼叫" 传送列表中。</span><span class="sxs-lookup"><span data-stu-id="d7f5b-166">If an agent opts out of getting calls, they won't be included in the call routing list regardless of what their availability status is set to.</span></span> 

> [!NOTE]
> <span data-ttu-id="d7f5b-167">启用基于状态的路由时，呼叫传送列表中不包含使用 Skype for Business 客户端的代理。</span><span class="sxs-lookup"><span data-stu-id="d7f5b-167">Agents who use the Skype for Business client aren't included in the call routing list when presence-based routing is enabled.</span></span> <span data-ttu-id="d7f5b-168">如果您有使用 Skype for Business 的工程师，请不要启用基于状态的呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="d7f5b-168">If you have agents who use Skype for Business, don't enable presence-based call routing.</span></span>

<span data-ttu-id="d7f5b-169">**代理警报时间** 指定在队列将呼叫重定向到下一个代理之前，代理电话将响铃的时间。</span><span class="sxs-lookup"><span data-stu-id="d7f5b-169">**Agent alert time** specifies how long an agent's phone will ring before the queue redirects the call to the next agent.</span></span>

<span data-ttu-id="d7f5b-170">对于高音量队列，我们建议采用以下设置：</span><span class="sxs-lookup"><span data-stu-id="d7f5b-170">For high volume queues, we recommend the following settings:</span></span>

- <span data-ttu-id="d7f5b-171">**会议模式\*\*\*\*自动**</span><span class="sxs-lookup"><span data-stu-id="d7f5b-171">**Conference mode** to **Auto**</span></span>
- <span data-ttu-id="d7f5b-172">用于 **助理路由** 的 **路由方法**</span><span class="sxs-lookup"><span data-stu-id="d7f5b-172">**Routing method** to **Attendant routing**</span></span>
- <span data-ttu-id="d7f5b-173">**基于状态的路由** 到 **"开"**</span><span class="sxs-lookup"><span data-stu-id="d7f5b-173">**Presence-based routing** to **On**</span></span>
- <span data-ttu-id="d7f5b-174">**代理警报时间：** 到 **20 秒**</span><span class="sxs-lookup"><span data-stu-id="d7f5b-174">**Agent alert time:** to **20 seconds**</span></span>

## <a name="call-overflow-handling"></a><span data-ttu-id="d7f5b-175">呼叫溢出处理</span><span class="sxs-lookup"><span data-stu-id="d7f5b-175">Call overflow handling</span></span>

![通话溢出设置的屏幕截图](media/call-queue-overflow-handling.png)

<span data-ttu-id="d7f5b-177">**队列中的最大通话** 次数指定可在任何给定时间在队列中等待的最大通话次数。</span><span class="sxs-lookup"><span data-stu-id="d7f5b-177">**Maximum calls in the queue** specifies the maximum number of calls that can wait in the queue at any given time.</span></span> <span data-ttu-id="d7f5b-178">默认值为50，但范围可以从0到200。</span><span class="sxs-lookup"><span data-stu-id="d7f5b-178">The default is 50, but it can range from 0 to 200.</span></span> <span data-ttu-id="d7f5b-179">达到此限制时，将按照 **当达到最大调用次数时** 指定的方式处理调用。</span><span class="sxs-lookup"><span data-stu-id="d7f5b-179">When this limit is reached, the call is handled as specified by the **When the maximum number of calls is reached** setting.</span></span>

<span data-ttu-id="d7f5b-180">您可以选择断开呼叫或将其重定向到除操作员之外的任何 [呼叫传送目的地](create-a-phone-system-auto-attendant.md#call-routing-options) 。</span><span class="sxs-lookup"><span data-stu-id="d7f5b-180">You can choose to disconnect the call or redirect it to any of the [call routing destinations](create-a-phone-system-auto-attendant.md#call-routing-options) except the operator.</span></span> <span data-ttu-id="d7f5b-181">例如，您可能会让呼叫者在队列中留下有关代理的语音邮件。</span><span class="sxs-lookup"><span data-stu-id="d7f5b-181">For example, you might have the caller leave a voicemail for the agents in the queue.</span></span> <span data-ttu-id="d7f5b-182"> (如果您要转移到外部号码，请注意 [这些详细信息](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant#external-phone-number-transfers---technical-details) 。 ) </span><span class="sxs-lookup"><span data-stu-id="d7f5b-182">(Note [these details](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant#external-phone-number-transfers---technical-details) if you're transferring to an external number.)</span></span>

> [!NOTE]
> <span data-ttu-id="d7f5b-183">如果将最大通话次数设置为0，则不会播放问候语。</span><span class="sxs-lookup"><span data-stu-id="d7f5b-183">If the maximum number of calls is set to 0 then the greeting message will not play.</span></span>

## <a name="call-timeout-handling"></a><span data-ttu-id="d7f5b-184">通话超时处理</span><span class="sxs-lookup"><span data-stu-id="d7f5b-184">Call timeout handling</span></span>

![通话超时设置的屏幕截图](media/call-queue-timeout-handling.png)

<span data-ttu-id="d7f5b-186">**呼叫超时：最长等待时间** 指定呼叫在重定向或断开连接之前可以在队列中保留的最长时间。</span><span class="sxs-lookup"><span data-stu-id="d7f5b-186">**Call Timeout: maximum wait time** specifies the maximum time a call can be on hold in the queue before it is redirected or disconnected.</span></span> <span data-ttu-id="d7f5b-187">你可以指定从15秒到45分钟的值。</span><span class="sxs-lookup"><span data-stu-id="d7f5b-187">You can specify a value from 15 seconds to 45 minutes.</span></span>

<span data-ttu-id="d7f5b-188">您可以选择断开呼叫或将其重定向到呼叫传送目的地之一。</span><span class="sxs-lookup"><span data-stu-id="d7f5b-188">You can choose to disconnect the call or redirect it to one of the call routing destinations.</span></span> <span data-ttu-id="d7f5b-189">例如，您可能会让呼叫者在队列中留下有关代理的语音邮件。</span><span class="sxs-lookup"><span data-stu-id="d7f5b-189">For example, you might have the caller leave a voicemail for the agents in the queue.</span></span>

<span data-ttu-id="d7f5b-190">选择您的通话超时选项后，单击 " **保存** "。</span><span class="sxs-lookup"><span data-stu-id="d7f5b-190">When you have selected your call timeout options, click **Save**.</span></span>

## <a name="caller-id-for-outbound-calls"></a><span data-ttu-id="d7f5b-191">用于出站呼叫的来电显示</span><span class="sxs-lookup"><span data-stu-id="d7f5b-191">Caller ID for outbound calls</span></span>

<span data-ttu-id="d7f5b-192">由于呼叫队列中的代理可能会拨出以返回客户呼叫，请考虑将呼叫队列成员的来电显示设置为相应自动助理的服务号码。</span><span class="sxs-lookup"><span data-stu-id="d7f5b-192">Since agents in a call queue may dial out to return a customer call, consider setting the caller ID for members of a call queue to the service number of an appropriate auto attendant.</span></span> <span data-ttu-id="d7f5b-193">有关详细信息，请参阅 [管理 Microsoft 团队中的来电显示策略](caller-id-policies.md) 。</span><span class="sxs-lookup"><span data-stu-id="d7f5b-193">See [Manage caller ID policies in Microsoft Teams](caller-id-policies.md) for more information.</span></span>

## <a name="supported-clients"></a><span data-ttu-id="d7f5b-194">支持的客户端</span><span class="sxs-lookup"><span data-stu-id="d7f5b-194">Supported clients</span></span>

- <span data-ttu-id="d7f5b-195">呼叫队列中的呼叫代理支持下列客户端：</span><span class="sxs-lookup"><span data-stu-id="d7f5b-195">The following clients are supported for call agents in a call queue:</span></span>

  - <span data-ttu-id="d7f5b-196">Skype for Business 桌面客户端 2016 (32 位和64位版本) </span><span class="sxs-lookup"><span data-stu-id="d7f5b-196">Skype for Business desktop client 2016 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="d7f5b-197">Lync 桌面客户端 2013 (32 位和64位版本) </span><span class="sxs-lookup"><span data-stu-id="d7f5b-197">Lync desktop client 2013 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="d7f5b-198">Microsoft 团队支持的所有 IP 电话模式。</span><span class="sxs-lookup"><span data-stu-id="d7f5b-198">All IP phone models supported for Microsoft Teams.</span></span> <span data-ttu-id="d7f5b-199">请参阅[获取适用于 Skype for Business Online 的电话](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online)。</span><span class="sxs-lookup"><span data-stu-id="d7f5b-199">See [Getting phones for Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span></span>
  - <span data-ttu-id="d7f5b-200">Mac Skype for Business 客户端（版本 16.8.196 及更高版本）</span><span class="sxs-lookup"><span data-stu-id="d7f5b-200">Mac Skype for Business Client (version 16.8.196 and later)</span></span>
  - <span data-ttu-id="d7f5b-201">Android Skype for Business 客户端（版本 6.16.0.9 及更高版本）</span><span class="sxs-lookup"><span data-stu-id="d7f5b-201">Android Skype for Business Client (version 6.16.0.9 and later)</span></span>
  - <span data-ttu-id="d7f5b-202">iPhone Skype for Business 客户端（版本 6.16.0 及更高版本）</span><span class="sxs-lookup"><span data-stu-id="d7f5b-202">iPhone Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="d7f5b-203">iPad Skype for Business 客户端（版本 6.16.0 及更高版本）</span><span class="sxs-lookup"><span data-stu-id="d7f5b-203">iPad Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="d7f5b-204">Microsoft 团队 Windows 客户端 (32 位和64位版本) </span><span class="sxs-lookup"><span data-stu-id="d7f5b-204">Microsoft Teams Windows client (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="d7f5b-205">Microsoft Teams Mac 客户端</span><span class="sxs-lookup"><span data-stu-id="d7f5b-205">Microsoft Teams Mac client</span></span>
  - <span data-ttu-id="d7f5b-206">Microsoft Teams iPhone 应用</span><span class="sxs-lookup"><span data-stu-id="d7f5b-206">Microsoft Teams iPhone app</span></span>
  - <span data-ttu-id="d7f5b-207">Microsoft Teams Android 应用</span><span class="sxs-lookup"><span data-stu-id="d7f5b-207">Microsoft Teams Android app</span></span>

    > [!NOTE]
    > <span data-ttu-id="d7f5b-208">分配了直接路由号码的呼叫队列不支持 Skype for business 客户端、Lync 客户端或 Skype for business IP 手机用作代理。</span><span class="sxs-lookup"><span data-stu-id="d7f5b-208">Call queues that are assigned a direct routing number don't support Skype for Business clients, Lync clients, or Skype for Business IP Phones as agents.</span></span>

## <a name="call-queue-cmdlets"></a><span data-ttu-id="d7f5b-209">呼叫队列 cmdlet</span><span class="sxs-lookup"><span data-stu-id="d7f5b-209">Call queue cmdlets</span></span>

<span data-ttu-id="d7f5b-210">还可以使用 Windows PowerShell 来创建和设置呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="d7f5b-210">You can also use Windows PowerShell to create and set up call queues.</span></span> <span data-ttu-id="d7f5b-211">下面是用于管理呼叫队列的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d7f5b-211">Here are the cmdlets that you use to manage a call queue.</span></span>

- [<span data-ttu-id="d7f5b-212">新-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="d7f5b-212">New-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsCallQueue)

- [<span data-ttu-id="d7f5b-213">Set-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="d7f5b-213">Set-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/set-CsCallQueue)

- [<span data-ttu-id="d7f5b-214">CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="d7f5b-214">Get-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/get-CsCallQueue)

- [<span data-ttu-id="d7f5b-215">Remove-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="d7f5b-215">Remove-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-CsCallQueue)

## <a name="related-topics"></a><span data-ttu-id="d7f5b-216">相关主题</span><span class="sxs-lookup"><span data-stu-id="d7f5b-216">Related topics</span></span>

[<span data-ttu-id="d7f5b-217">电话系统的功能</span><span class="sxs-lookup"><span data-stu-id="d7f5b-217">Here's what you get with Phone System</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="d7f5b-218">获取服务电话号码</span><span class="sxs-lookup"><span data-stu-id="d7f5b-218">Getting service phone numbers</span></span>](getting-service-phone-numbers.md)

[<span data-ttu-id="d7f5b-219">音频会议和通话套餐的国家/地区可用性</span><span class="sxs-lookup"><span data-stu-id="d7f5b-219">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="d7f5b-220">新-CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="d7f5b-220">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance)

[<span data-ttu-id="d7f5b-221">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="d7f5b-221">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
