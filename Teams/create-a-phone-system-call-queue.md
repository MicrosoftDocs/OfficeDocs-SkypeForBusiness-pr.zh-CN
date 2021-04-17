---
title: 在 Microsoft Teams 创建呼叫队列
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
description: 了解如何使用 Microsoft Teams 为呼叫队列设置电话系统，它提供问候消息、保存音乐、呼叫重定向和其他功能。
ms.openlocfilehash: 1202de31beddb8f70391d40d4e6218942c59cba1
ms.sourcegitcommit: 4e1f5d99c1d0612dc5b50f850280983867ff53d8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2021
ms.locfileid: "51874448"
---
# <a name="create-a-call-queue"></a><span data-ttu-id="2d577-103">创建呼叫队列</span><span class="sxs-lookup"><span data-stu-id="2d577-103">Create a call queue</span></span>

<span data-ttu-id="2d577-104">呼叫队列提供将呼叫者路由到组织中可以解决特定问题或问题的人的方法。</span><span class="sxs-lookup"><span data-stu-id="2d577-104">Call queues provide a method of routing callers to people in your organization who can help with a particular issue or question.</span></span> <span data-ttu-id="2d577-105">呼叫一次一个地分配给队列中 (称为代理 *) 。*</span><span class="sxs-lookup"><span data-stu-id="2d577-105">Calls are distributed one at a time to the people in the queue (who are known as *agents*).</span></span> 

<span data-ttu-id="2d577-106">呼叫队列提供：</span><span class="sxs-lookup"><span data-stu-id="2d577-106">Call queues provide:</span></span>

- <span data-ttu-id="2d577-107">问候消息。</span><span class="sxs-lookup"><span data-stu-id="2d577-107">A greeting message.</span></span>

- <span data-ttu-id="2d577-108">音乐等待队列中等待时，</span><span class="sxs-lookup"><span data-stu-id="2d577-108">Music while people are waiting on hold in a queue.</span></span>

- <span data-ttu-id="2d577-109">调用路由 - 在 *"先* 到先出" (FIFO) 顺序 - 到代理。</span><span class="sxs-lookup"><span data-stu-id="2d577-109">Call routing - in *First In, First Out* (FIFO) order - to agents.</span></span>

- <span data-ttu-id="2d577-110">处理队列溢出和超时的选项。</span><span class="sxs-lookup"><span data-stu-id="2d577-110">Handling options for queue overflow and timeout.</span></span>

<span data-ttu-id="2d577-111">在按照本文中的步骤操作之前，请确保已阅读[规划 Teams 自动](plan-auto-attendant-call-queue.md)助理[](plan-auto-attendant-call-queue.md#getting-started)和呼叫队列，并按照入门步骤操作。</span><span class="sxs-lookup"><span data-stu-id="2d577-111">Be sure you have read [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md) and followed the [getting started steps](plan-auto-attendant-call-queue.md#getting-started) before you follow the procedures in this article.</span></span>

<span data-ttu-id="2d577-112">若要设置呼叫队列，请在 Teams 管理中心展开"语音"，单击"**呼叫队列**"，然后单击"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="2d577-112">To set up a call queue, in the Teams admin center, expand **Voice**, click **Call queues**, and then click **Add**.</span></span>

## <a name="resource-account-and-language"></a><span data-ttu-id="2d577-113">资源帐户和语言</span><span class="sxs-lookup"><span data-stu-id="2d577-113">Resource account and language</span></span>

![资源帐户和语言设置的屏幕截图](media/call-queue-name-language.png)

1. <span data-ttu-id="2d577-115">键入呼叫队列的名称。</span><span class="sxs-lookup"><span data-stu-id="2d577-115">Type a name for the call queue.</span></span>

2. <span data-ttu-id="2d577-116">单击 **"添加** 帐户"，搜索要用于此呼叫队列的资源帐户，单击"添加 **"，然后单击**"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="2d577-116">Click **Add accounts**, search for the resource account that you want to use with this call queue, click **Add**, and then click **Add**.</span></span> <span data-ttu-id="2d577-117"> (代理收到传入呼叫时，会看到资源帐户名称。) </span><span class="sxs-lookup"><span data-stu-id="2d577-117">(Agents will see the resource account name when they receive an incoming call.)</span></span>

3. <span data-ttu-id="2d577-118">选择 [受支持的语言](create-a-phone-system-call-queue-languages.md)。</span><span class="sxs-lookup"><span data-stu-id="2d577-118">Choose a [supported language](create-a-phone-system-call-queue-languages.md).</span></span> <span data-ttu-id="2d577-119">如果启用语音提示和语音听录，此语言 (系统生成的语音) 。</span><span class="sxs-lookup"><span data-stu-id="2d577-119">This language will be used for system-generated voice prompts and voicemail transcription (if you enable them).</span></span>

## <a name="greetings-and-music-on-hold-in-queue"></a><span data-ttu-id="2d577-120">队列中保留的问候语和音乐</span><span class="sxs-lookup"><span data-stu-id="2d577-120">Greetings and music on hold in queue</span></span>

<span data-ttu-id="2d577-121">指定是否要在呼叫者到达队列时播放问候语。</span><span class="sxs-lookup"><span data-stu-id="2d577-121">Specify if you want to play a greeting to callers when they arrive in the queue.</span></span> <span data-ttu-id="2d577-122">必须上传包含要播放的问候语的 MP3、WAV 或 WMA 文件。</span><span class="sxs-lookup"><span data-stu-id="2d577-122">You must upload an MP3, WAV, or WMA file containing the greeting that you want to play.</span></span>

<span data-ttu-id="2d577-123">当呼叫者在队列中保持时，Teams 会向呼叫者提供默认音乐。</span><span class="sxs-lookup"><span data-stu-id="2d577-123">Teams provides default music to callers while they are on hold in a queue.</span></span> <span data-ttu-id="2d577-124">如果要播放特定音频文件，请选择"播放音频文件 **"并** 上传 MP3、WAV 或 WMA 文件。</span><span class="sxs-lookup"><span data-stu-id="2d577-124">If you want to play a specific audio file, choose **Play an audio file** and upload an MP3, WAV, or WMA file.</span></span>

> [!NOTE]
> <span data-ttu-id="2d577-125">上传的录制内容不能大于 5 MB。</span><span class="sxs-lookup"><span data-stu-id="2d577-125">The uploaded recording can be no larger than 5 MB.</span></span>
> <span data-ttu-id="2d577-126">Teams 呼叫队列中提供的默认音乐不收取组织支付的任何版权费。</span><span class="sxs-lookup"><span data-stu-id="2d577-126">The default music supplied in Teams call queues is free of any royalties payable by your organization.</span></span> 

## <a name="call-agents"></a><span data-ttu-id="2d577-127">呼叫代理</span><span class="sxs-lookup"><span data-stu-id="2d577-127">Call agents</span></span>

<span data-ttu-id="2d577-128">查看 [将代理添加到呼叫队列的先决条件](plan-auto-attendant-call-queue.md#prerequisites)。</span><span class="sxs-lookup"><span data-stu-id="2d577-128">Review the [prerequisites for adding agents to a call queue](plan-auto-attendant-call-queue.md#prerequisites).</span></span>

![呼叫队列的用户和组设置的屏幕截图](media/call-queue-users-groups.png)

##### <a name="teams-channel"></a><span data-ttu-id="2d577-130">Teams 频道</span><span class="sxs-lookup"><span data-stu-id="2d577-130">Teams channel</span></span>

<span data-ttu-id="2d577-131">可以通过 Teams 频道最多添加 200 个代理。</span><span class="sxs-lookup"><span data-stu-id="2d577-131">You can add up to 200 agents via a Teams channel.</span></span>

<span data-ttu-id="2d577-132">如果要使用 [Teams 频道管理](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e)队列，请选择"**选择团队"选项，** 然后单击"**添加频道"。**</span><span class="sxs-lookup"><span data-stu-id="2d577-132">If you want to [use a Teams channel to manage the queue](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e), select the **Choose a team** option and click **Add a channel**.</span></span> <span data-ttu-id="2d577-133">搜索想要使用的团队，将其选中，然后单击"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="2d577-133">Search for the team that you want to use, select it, and click **Add**.</span></span> <span data-ttu-id="2d577-134">选择想要使用的频道，然后单击"应用 **"。**</span><span class="sxs-lookup"><span data-stu-id="2d577-134">Select the channel that you want to use and click **Apply**.</span></span>

<span data-ttu-id="2d577-135">将 Teams 频道用于呼叫队列时，支持以下客户端：</span><span class="sxs-lookup"><span data-stu-id="2d577-135">The following clients are supported when using a Teams channel for call queues:</span></span> 

  - <span data-ttu-id="2d577-136">Microsoft Teams Windows 客户端</span><span class="sxs-lookup"><span data-stu-id="2d577-136">Microsoft Teams Windows client</span></span>
  - <span data-ttu-id="2d577-137">Microsoft Teams Mac 客户端</span><span class="sxs-lookup"><span data-stu-id="2d577-137">Microsoft Teams Mac client</span></span>

##### <a name="users-and-groups"></a><span data-ttu-id="2d577-138">用户和组</span><span class="sxs-lookup"><span data-stu-id="2d577-138">Users and groups</span></span>

<span data-ttu-id="2d577-139">可以单独添加多达 20 个代理，通过组最多添加 200 个代理。</span><span class="sxs-lookup"><span data-stu-id="2d577-139">You can add up to 20 agents individually and up to 200 agents via groups.</span></span>

<span data-ttu-id="2d577-140">如果要将单个用户或组添加到队列，请选择" **选择用户和组"** 选项。</span><span class="sxs-lookup"><span data-stu-id="2d577-140">If you want to add individual users or groups to the queue, select the **Choose users and groups** option.</span></span> 

<span data-ttu-id="2d577-141">若要将用户添加到队列，请单击"**添加** 用户"，搜索该用户，单击"添加 **"，然后单击**"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="2d577-141">To add a user to the queue, click **Add users**, search for the user, click **Add**, and then click **Add**.</span></span>

<span data-ttu-id="2d577-142">若要将组添加到队列，请单击 **"添加组**"，搜索该组，单击"添加 **"，然后单击**"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="2d577-142">To add a group to the queue, click **Add groups**, search for the group, click **Add**, and then click **Add**.</span></span> <span data-ttu-id="2d577-143">可以使用通讯组列表、安全组和 Microsoft 365 组或 Microsoft Teams 团队。</span><span class="sxs-lookup"><span data-stu-id="2d577-143">You can use distribution lists, security groups, and Microsoft 365 groups or Microsoft Teams teams.</span></span>

> [!NOTE]
> <span data-ttu-id="2d577-144">添加到组的新用户可能需要最多八个小时才能进行第一次呼叫。</span><span class="sxs-lookup"><span data-stu-id="2d577-144">New users added to a group can take up to eight hours for their first call to arrive.</span></span>

## <a name="call-routing"></a><span data-ttu-id="2d577-145">呼叫路由</span><span class="sxs-lookup"><span data-stu-id="2d577-145">Call routing</span></span>

![会议模式和路由方法设置的屏幕截图](media/call-queue-conference-mode-routing-method.png)

<span data-ttu-id="2d577-147">**在** 代理接受呼叫后，会议模式可显著减少呼叫者连接到代理所花的时间。</span><span class="sxs-lookup"><span data-stu-id="2d577-147">**Conference mode** significantly reduces the amount of time it takes for a caller to be connected to an agent, after the agent accepts the call.</span></span> <span data-ttu-id="2d577-148">若要使会议模式正常工作，呼叫队列中的代理必须使用以下客户端之一：</span><span class="sxs-lookup"><span data-stu-id="2d577-148">For conference mode to work, agents in the call queue must use one of the following clients:</span></span>

  - <span data-ttu-id="2d577-149">最新版本的 Microsoft Teams 桌面客户端、Android 应用或 iOS 应用</span><span class="sxs-lookup"><span data-stu-id="2d577-149">The latest version of the Microsoft Teams desktop client, Android app, or iOS app</span></span>
  - <span data-ttu-id="2d577-150">Microsoft Teams 手机版本 1449/1.0.94.2020051601 或更高版本</span><span class="sxs-lookup"><span data-stu-id="2d577-150">Microsoft Teams phone version 1449/1.0.94.2020051601 or later</span></span>
  
<span data-ttu-id="2d577-151">代理的 Teams 帐户需要设置为仅 Teams 模式。</span><span class="sxs-lookup"><span data-stu-id="2d577-151">Agents' Teams accounts need to be set to Teams-only mode.</span></span> <span data-ttu-id="2d577-152">不符合要求的代理不包括在呼叫路由列表中。</span><span class="sxs-lookup"><span data-stu-id="2d577-152">Agents who don't meet the requirements aren't included in the call routing list.</span></span> <span data-ttu-id="2d577-153">如果代理都使用兼容的客户端，建议为呼叫队列启用会议模式。</span><span class="sxs-lookup"><span data-stu-id="2d577-153">We recommend enabling conference mode for your call queues if your agents are all using compatible clients.</span></span>

> [!NOTE]
> <span data-ttu-id="2d577-154">如果电话呼叫从为"基于位置的路由"启用的直接路由网关路由到队列，则不支持会议模式。</span><span class="sxs-lookup"><span data-stu-id="2d577-154">Conference mode is not supported if phone calls are routed to the queue from a Direct Routing gateway that is enabled for Location Based Routing.</span></span>

<span data-ttu-id="2d577-155">**路由** 方法确定代理从队列接收调用的顺序。</span><span class="sxs-lookup"><span data-stu-id="2d577-155">**Routing method** determines the order in which agents receive calls from the queue.</span></span> <span data-ttu-id="2d577-156">从以下选项中进行选择：</span><span class="sxs-lookup"><span data-stu-id="2d577-156">Choose from these options:</span></span>

- <span data-ttu-id="2d577-157">**助理路由** 同时将队列中的所有代理环环。</span><span class="sxs-lookup"><span data-stu-id="2d577-157">**Attendant routing** rings all agents in the queue at the same time.</span></span> <span data-ttu-id="2d577-158">第一个接电话的呼叫代理获取呼叫。</span><span class="sxs-lookup"><span data-stu-id="2d577-158">The first call agent to pick up the call gets the call.</span></span>

- <span data-ttu-id="2d577-159">**串行路由** 按"呼叫代理"列表中指定的顺序一个接一个地拨打所有 **呼叫** 代理。</span><span class="sxs-lookup"><span data-stu-id="2d577-159">**Serial routing** rings all call agents one by one in the order specified in the **Call agents** list.</span></span> <span data-ttu-id="2d577-160">如果代理关闭或未接回呼叫，该调用将拨打下一个代理，并尝试所有代理，直到它被选取或退出。</span><span class="sxs-lookup"><span data-stu-id="2d577-160">If an agent dismisses or does not pick up a call, the call will ring the next agent and will try all agents until it is picked up or times out.</span></span>

- <span data-ttu-id="2d577-161">**轮循** 机制平衡传入调用的路由，以便每个调用代理从队列中获取相同数量的调用。</span><span class="sxs-lookup"><span data-stu-id="2d577-161">**Round robin** balances the routing of incoming calls so that each call agent gets the same number of calls from the queue.</span></span> <span data-ttu-id="2d577-162">在入站销售环境中可能需要这样做，以确保所有呼叫代理之间的机会相等。</span><span class="sxs-lookup"><span data-stu-id="2d577-162">This may be desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

- <span data-ttu-id="2d577-163">**最长空闲** 时间将每次调用路由到空闲时间最长的代理。</span><span class="sxs-lookup"><span data-stu-id="2d577-163">**Longest idle** routes each call to the agent who has been idle the longest time.</span></span> <span data-ttu-id="2d577-164">如果代理的状态为"可用"或其状态为"离开"时间少于 10 分钟，则代理被视为空闲状态。</span><span class="sxs-lookup"><span data-stu-id="2d577-164">An agent is considered idle if their presence state is Available or if their presence state has been Away for less than 10 minutes.</span></span> <span data-ttu-id="2d577-165">状态为"离开"超过 10 分钟的代理不被视为空闲状态，在将状态更改为"可用"之前，他们无法接听呼叫。</span><span class="sxs-lookup"><span data-stu-id="2d577-165">Agents whose presence state has been Away for more than 10 minutes are not considered idle and will not be eligible to receive calls until they change their presence to Available.</span></span> 

![路由、选择退出和警报时间设置的屏幕截图](media/call-queue-presence-agents-time.png)


<span data-ttu-id="2d577-167">**基于状态的路由** 使用呼叫代理的可用性状态来确定是否应在所选路由方法的呼叫路由列表中包含代理。</span><span class="sxs-lookup"><span data-stu-id="2d577-167">**Presence-based routing** uses the availability status of call agents to determine whether an agent should be included in the call routing list for the selected routing method.</span></span> <span data-ttu-id="2d577-168">其可用性状态设置为"可用 **"** 的呼叫代理包含在呼叫路由列表中，可以接收呼叫。</span><span class="sxs-lookup"><span data-stu-id="2d577-168">Call agents whose availability status is set to **Available** are included in the call routing list and can receive calls.</span></span> <span data-ttu-id="2d577-169">其可用性状态设置为任何其他状态的代理从呼叫路由列表中排除，并且不会接收呼叫，直到其可用性状态更改回"可用 **"。**</span><span class="sxs-lookup"><span data-stu-id="2d577-169">Agents whose availability status is set to any other status are excluded from the call routing list and won't receive calls until their availability status changes back to **Available**.</span></span> 

<span data-ttu-id="2d577-170">可以使用任何路由方法启用基于状态的呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="2d577-170">You can enable presence-based call routing with any of the routing methods.</span></span>

<span data-ttu-id="2d577-171">如果代理选择不接听呼叫，则无论其可用性状态设置为什么，它们将不会包含在呼叫路由列表中。</span><span class="sxs-lookup"><span data-stu-id="2d577-171">If an agent opts out of getting calls, they won't be included in the call routing list regardless of what their availability status is set to.</span></span> 

> [!NOTE]
> <span data-ttu-id="2d577-172">启用基于状态的路由时，使用 Skype for Business 客户端的代理不包括在呼叫路由列表中。</span><span class="sxs-lookup"><span data-stu-id="2d577-172">Agents who use the Skype for Business client aren't included in the call routing list when presence-based routing is enabled.</span></span> <span data-ttu-id="2d577-173">如果你有使用 Skype for Business 的代理，请不要启用基于状态的电话路由。</span><span class="sxs-lookup"><span data-stu-id="2d577-173">If you have agents who use Skype for Business, don't enable presence-based call routing.</span></span>

<span data-ttu-id="2d577-174">**代理警报** 时间指定在队列将呼叫重定向到下一个代理之前，代理的电话将响铃的时间。</span><span class="sxs-lookup"><span data-stu-id="2d577-174">**Agent alert time** specifies how long an agent's phone will ring before the queue redirects the call to the next agent.</span></span>

<span data-ttu-id="2d577-175">建议设置以下设置：</span><span class="sxs-lookup"><span data-stu-id="2d577-175">The following settings are recommended:</span></span>

- <span data-ttu-id="2d577-176">**"会议模式** "到 **"自动"**</span><span class="sxs-lookup"><span data-stu-id="2d577-176">**Conference mode** to **Auto**</span></span>
- <span data-ttu-id="2d577-177">**路由到轮\*\*\*\*循机制或\*\*\*\*最长空闲时间的方法**</span><span class="sxs-lookup"><span data-stu-id="2d577-177">**Routing method** to **Round robin** or **Longest idle**</span></span>
- <span data-ttu-id="2d577-178">**基于状态到"打开"** 的 **路由**</span><span class="sxs-lookup"><span data-stu-id="2d577-178">**Presence-based routing** to **On**</span></span>
- <span data-ttu-id="2d577-179">**代理警报时间：\*\*\*\*到 20 秒**</span><span class="sxs-lookup"><span data-stu-id="2d577-179">**Agent alert time:** to **20 seconds**</span></span>

> [!NOTE]
> <span data-ttu-id="2d577-180">如果未启用基于状态的路由，并且队列中有多个调用，系统将同时向代理显示这些调用，而不管代理的状态如何。</span><span class="sxs-lookup"><span data-stu-id="2d577-180">If presence-based routing is not enabled and there are multiple calls in the queue, the system will present these calls simultaneously to the agents regardless of their presence status.</span></span> <span data-ttu-id="2d577-181">这会导致向代理发送多个呼叫通知，尤其是当某些代理不应答发送给代理的初始呼叫时。</span><span class="sxs-lookup"><span data-stu-id="2d577-181">This will result in multiple call notifications to agents, particularly if some agents don’t answer the initial call presented to them.</span></span>

## <a name="call-overflow-handling"></a><span data-ttu-id="2d577-182">调用溢出处理</span><span class="sxs-lookup"><span data-stu-id="2d577-182">Call overflow handling</span></span>

![呼叫溢出设置的屏幕截图](media/call-queue-overflow-handling.png)

<span data-ttu-id="2d577-184">**队列中的最大调用** 数指定在任意给定时间可在队列中等待的最大调用数。</span><span class="sxs-lookup"><span data-stu-id="2d577-184">**Maximum calls in the queue** specifies the maximum number of calls that can wait in the queue at any given time.</span></span> <span data-ttu-id="2d577-185">默认值为 50，但范围为 0 到 200。</span><span class="sxs-lookup"><span data-stu-id="2d577-185">The default is 50, but it can range from 0 to 200.</span></span> <span data-ttu-id="2d577-186">达到此限制时，按"达到最大调用数时"设置指定 **处理** 调用。</span><span class="sxs-lookup"><span data-stu-id="2d577-186">When this limit is reached, the call is handled as specified by the **When the maximum number of calls is reached** setting.</span></span>

<span data-ttu-id="2d577-187">可以选择断开呼叫连接或将其重定向到任何呼叫路由目标。</span><span class="sxs-lookup"><span data-stu-id="2d577-187">You can choose to disconnect the call or redirect it to any of the call routing destinations.</span></span> <span data-ttu-id="2d577-188">例如，你可能让呼叫者为队列中的代理留下语音邮件。</span><span class="sxs-lookup"><span data-stu-id="2d577-188">For example, you might have the caller leave a voicemail for the agents in the queue.</span></span> <span data-ttu-id="2d577-189">有关外部传输，请参阅先决条件和外部[](plan-auto-attendant-call-queue.md#prerequisites)电话号码转移[- 号码](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)格式的技术详细信息。</span><span class="sxs-lookup"><span data-stu-id="2d577-189">For external transfers, please refer to [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) and the [external phone number transfers - technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) for number formatting.</span></span>

> [!NOTE]
> <span data-ttu-id="2d577-190">如果最大呼叫数设置为 0，则问候消息将不会播放。</span><span class="sxs-lookup"><span data-stu-id="2d577-190">If the maximum number of calls is set to 0 then the greeting message will not play.</span></span>

## <a name="call-timeout-handling"></a><span data-ttu-id="2d577-191">调用超时处理</span><span class="sxs-lookup"><span data-stu-id="2d577-191">Call timeout handling</span></span>

![通话超时设置的屏幕截图](media/call-queue-timeout-handling.png)

<span data-ttu-id="2d577-193">**调用超时：最长等待时间** 指定在重定向或断开连接之前，呼叫在队列中可以保持的最大时间。</span><span class="sxs-lookup"><span data-stu-id="2d577-193">**Call Timeout: maximum wait time** specifies the maximum time a call can be on hold in the queue before it is redirected or disconnected.</span></span> <span data-ttu-id="2d577-194">可以指定 0 秒到 45 分钟的值。</span><span class="sxs-lookup"><span data-stu-id="2d577-194">You can specify a value from 0 seconds to 45 minutes.</span></span>

<span data-ttu-id="2d577-195">可以选择断开呼叫连接或将其重定向到呼叫路由目标之一。</span><span class="sxs-lookup"><span data-stu-id="2d577-195">You can choose to disconnect the call or redirect it to one of the call routing destinations.</span></span> <span data-ttu-id="2d577-196">例如，你可能让呼叫者为队列中的代理留下语音邮件。</span><span class="sxs-lookup"><span data-stu-id="2d577-196">For example, you might have the caller leave a voicemail for the agents in the queue.</span></span> <span data-ttu-id="2d577-197">有关外部传输，请参阅先决条件和外部[](plan-auto-attendant-call-queue.md#prerequisites)电话号码转移[- 号码](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)格式的技术详细信息。</span><span class="sxs-lookup"><span data-stu-id="2d577-197">For external transfers, please refer to [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) and the [external phone number transfers - technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) for number formatting.</span></span>

<span data-ttu-id="2d577-198">选择通话超时选项后，单击"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="2d577-198">When you have selected your call timeout options, click **Save**.</span></span>

## <a name="caller-id-for-outbound-calls"></a><span data-ttu-id="2d577-199">出站呼叫的来电显示</span><span class="sxs-lookup"><span data-stu-id="2d577-199">Caller ID for outbound calls</span></span>

<span data-ttu-id="2d577-200">由于呼叫队列中的代理可能会拨出以返回客户呼叫，因此请考虑将呼叫队列成员的呼叫者 ID 设置为相应自动助理的服务号码。</span><span class="sxs-lookup"><span data-stu-id="2d577-200">Since agents in a call queue may dial out to return a customer call, consider setting the caller ID for members of a call queue to the service number of an appropriate auto attendant.</span></span> <span data-ttu-id="2d577-201">有关详细信息 [，请参阅在 Microsoft Teams 中](caller-id-policies.md) 管理来电显示策略。</span><span class="sxs-lookup"><span data-stu-id="2d577-201">See [Manage caller ID policies in Microsoft Teams](caller-id-policies.md) for more information.</span></span>

## <a name="supported-clients"></a><span data-ttu-id="2d577-202">支持的客户端</span><span class="sxs-lookup"><span data-stu-id="2d577-202">Supported clients</span></span>

<span data-ttu-id="2d577-203">呼叫队列中的呼叫代理支持以下客户端：</span><span class="sxs-lookup"><span data-stu-id="2d577-203">The following clients are supported for call agents in a call queue:</span></span>

  - <span data-ttu-id="2d577-204">Skype for Business 桌面客户端 2016 (32 位和 64 位版本) </span><span class="sxs-lookup"><span data-stu-id="2d577-204">Skype for Business desktop client 2016 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="2d577-205">Lync 桌面客户端 2013 (32 位和 64 位版本) </span><span class="sxs-lookup"><span data-stu-id="2d577-205">Lync desktop client 2013 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="2d577-206">Microsoft Teams 支持的所有 IP 电话模型。</span><span class="sxs-lookup"><span data-stu-id="2d577-206">All IP phone models supported for Microsoft Teams.</span></span> <span data-ttu-id="2d577-207">请参阅[获取适用于 Skype for Business Online 的电话](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online)。</span><span class="sxs-lookup"><span data-stu-id="2d577-207">See [Getting phones for Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span></span>
  - <span data-ttu-id="2d577-208">Mac Skype for Business 客户端（版本 16.8.196 及更高版本）</span><span class="sxs-lookup"><span data-stu-id="2d577-208">Mac Skype for Business Client (version 16.8.196 and later)</span></span>
  - <span data-ttu-id="2d577-209">Android Skype for Business 客户端（版本 6.16.0.9 及更高版本）</span><span class="sxs-lookup"><span data-stu-id="2d577-209">Android Skype for Business Client (version 6.16.0.9 and later)</span></span>
  - <span data-ttu-id="2d577-210">iPhone Skype for Business 客户端（版本 6.16.0 及更高版本）</span><span class="sxs-lookup"><span data-stu-id="2d577-210">iPhone Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="2d577-211">iPad Skype for Business 客户端（版本 6.16.0 及更高版本）</span><span class="sxs-lookup"><span data-stu-id="2d577-211">iPad Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="2d577-212">Microsoft Teams Windows 客户端 (32 位和 64 位版本) </span><span class="sxs-lookup"><span data-stu-id="2d577-212">Microsoft Teams Windows client (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="2d577-213">Microsoft Teams Mac 客户端</span><span class="sxs-lookup"><span data-stu-id="2d577-213">Microsoft Teams Mac client</span></span>
  - <span data-ttu-id="2d577-214">Microsoft Teams iPhone 应用</span><span class="sxs-lookup"><span data-stu-id="2d577-214">Microsoft Teams iPhone app</span></span>
  - <span data-ttu-id="2d577-215">Microsoft Teams Android 应用</span><span class="sxs-lookup"><span data-stu-id="2d577-215">Microsoft Teams Android app</span></span>

    > [!NOTE]
    > <span data-ttu-id="2d577-216">分配有直接路由号码的呼叫队列不支持作为代理的 Skype for Business 客户端、Lync 客户端或 Skype for Business IP 电话。</span><span class="sxs-lookup"><span data-stu-id="2d577-216">Call queues that are assigned a direct routing number don't support Skype for Business clients, Lync clients, or Skype for Business IP Phones as agents.</span></span>

## <a name="call-queue-cmdlets"></a><span data-ttu-id="2d577-217">呼叫队列 cmdlet</span><span class="sxs-lookup"><span data-stu-id="2d577-217">Call queue cmdlets</span></span>

<span data-ttu-id="2d577-218">还可以使用 Windows PowerShell 来创建和设置呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="2d577-218">You can also use Windows PowerShell to create and set up call queues.</span></span> <span data-ttu-id="2d577-219">下面是用于管理呼叫队列的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="2d577-219">Here are the cmdlets that you use to manage a call queue.</span></span>

- [<span data-ttu-id="2d577-220">New-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="2d577-220">New-CsCallQueue</span></span>](/powershell/module/skype/new-CsCallQueue)

- [<span data-ttu-id="2d577-221">Set-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="2d577-221">Set-CsCallQueue</span></span>](/powershell/module/skype/set-CsCallQueue)

- [<span data-ttu-id="2d577-222">Get-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="2d577-222">Get-CsCallQueue</span></span>](/powershell/module/skype/get-CsCallQueue)

- [<span data-ttu-id="2d577-223">Remove-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="2d577-223">Remove-CsCallQueue</span></span>](/powershell/module/skype/remove-CsCallQueue)

## <a name="related-topics"></a><span data-ttu-id="2d577-224">相关主题</span><span class="sxs-lookup"><span data-stu-id="2d577-224">Related topics</span></span>

[<span data-ttu-id="2d577-225">电话系统的功能</span><span class="sxs-lookup"><span data-stu-id="2d577-225">Here's what you get with Phone System</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="2d577-226">获取服务电话号码</span><span class="sxs-lookup"><span data-stu-id="2d577-226">Getting service phone numbers</span></span>](getting-service-phone-numbers.md)

[<span data-ttu-id="2d577-227">音频会议和通话套餐的国家/地区可用性</span><span class="sxs-lookup"><span data-stu-id="2d577-227">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="2d577-228">New-CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="2d577-228">New-CsOnlineApplicationInstance</span></span>](/powershell/module/skype/new-csonlineapplicationinstance)

[<span data-ttu-id="2d577-229">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="2d577-229">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
