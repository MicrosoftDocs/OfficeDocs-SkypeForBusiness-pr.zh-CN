---
title: 在 Microsoft Teams
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
description: 了解如何在 Microsoft Teams 中为大型组织设置呼叫队列，该队列提供问候消息、保留音乐、呼叫重定向和其他功能。
ms.openlocfilehash: a8dbcddbbc7b0717678f56a2876b617d06f49187
ms.sourcegitcommit: ede53639ac782eb51d7560fc41fb01ec6979dfd9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/14/2021
ms.locfileid: "53428198"
---
# <a name="create-a-call-queue"></a><span data-ttu-id="a0e04-103">创建呼叫队列</span><span class="sxs-lookup"><span data-stu-id="a0e04-103">Create a call queue</span></span>

<span data-ttu-id="a0e04-104">呼叫队列提供将呼叫者路由到组织中可以解决特定问题或问题的人的方法。</span><span class="sxs-lookup"><span data-stu-id="a0e04-104">Call queues provide a method of routing callers to people in your organization who can help with a particular issue or question.</span></span> <span data-ttu-id="a0e04-105">呼叫一次一个地分配给队列中 (称为代理 *) 。*</span><span class="sxs-lookup"><span data-stu-id="a0e04-105">Calls are distributed one at a time to the people in the queue (who are known as *agents*).</span></span> 

> [!TIP]
> <span data-ttu-id="a0e04-106">本文适用于大型组织。</span><span class="sxs-lookup"><span data-stu-id="a0e04-106">This article is for large organizations.</span></span> <span data-ttu-id="a0e04-107">如果你的组织是小型企业，请改为阅读创建 [呼叫队列 - 小型企业](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb) 教程。</span><span class="sxs-lookup"><span data-stu-id="a0e04-107">If your organization is a small business, read [Create a call queue - small business tutorial](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb) instead.</span></span>

<span data-ttu-id="a0e04-108">呼叫队列提供：</span><span class="sxs-lookup"><span data-stu-id="a0e04-108">Call queues provide:</span></span>

- <span data-ttu-id="a0e04-109">问候消息。</span><span class="sxs-lookup"><span data-stu-id="a0e04-109">A greeting message.</span></span>

- <span data-ttu-id="a0e04-110">音乐在等待队列中等待时，</span><span class="sxs-lookup"><span data-stu-id="a0e04-110">Music while people are waiting on hold in a queue.</span></span>

- <span data-ttu-id="a0e04-111">调用路由 - 在 *"先* 到先出" (FIFO) 顺序 - 到代理。</span><span class="sxs-lookup"><span data-stu-id="a0e04-111">Call routing - in *First In, First Out* (FIFO) order - to agents.</span></span>

- <span data-ttu-id="a0e04-112">处理队列溢出和超时的选项。</span><span class="sxs-lookup"><span data-stu-id="a0e04-112">Handling options for queue overflow and timeout.</span></span>

<span data-ttu-id="a0e04-113">请确保已阅读自动[助理Teams](plan-auto-attendant-call-queue.md)呼叫队列的计划，并按照入门步骤操作，然后按照本文中的[](plan-auto-attendant-call-queue.md#getting-started)步骤操作。</span><span class="sxs-lookup"><span data-stu-id="a0e04-113">Be sure you have read [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md) and followed the [getting started steps](plan-auto-attendant-call-queue.md#getting-started) before you follow the procedures in this article.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="a0e04-114">视频演示</span><span class="sxs-lookup"><span data-stu-id="a0e04-114">Video demonstration</span></span>

<span data-ttu-id="a0e04-115">此视频演示了如何在呼叫队列中创建呼叫队列的基本Teams。</span><span class="sxs-lookup"><span data-stu-id="a0e04-115">This video shows a basic example of how to create a call queue in Teams.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWCF23?autoplay=false]

## <a name="create-the-call-queue"></a><span data-ttu-id="a0e04-116">创建呼叫队列</span><span class="sxs-lookup"><span data-stu-id="a0e04-116">Create the call queue</span></span>

<span data-ttu-id="a0e04-117">要设置呼叫队列，请在Teams中心展开 **"** 语音"，单击"呼叫 **队列**"，然后单击"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="a0e04-117">To set up a call queue, in the Teams admin center, expand **Voice**, click **Call queues**, and then click **Add**.</span></span>

<span data-ttu-id="a0e04-118">键入呼叫队列的名称。</span><span class="sxs-lookup"><span data-stu-id="a0e04-118">Type a name for the call queue.</span></span>

## <a name="resource-accounts"></a><span data-ttu-id="a0e04-119">资源帐户</span><span class="sxs-lookup"><span data-stu-id="a0e04-119">Resource accounts</span></span>

![资源帐户设置的屏幕截图](media/call-queue-name-language.png)

<span data-ttu-id="a0e04-121">单击 **"添加** 帐户"，搜索要用于此呼叫队列的资源帐户，单击"添加 **"，然后单击**"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="a0e04-121">Click **Add accounts**, search for the resource account that you want to use with this call queue, click **Add**, and then click **Add**.</span></span> <span data-ttu-id="a0e04-122"> (代理收到传入呼叫时，会看到资源帐户名称。) </span><span class="sxs-lookup"><span data-stu-id="a0e04-122">(Agents will see the resource account name when they receive an incoming call.)</span></span>

### <a name="assign-calling-id"></a><span data-ttu-id="a0e04-123">分配呼叫 ID</span><span class="sxs-lookup"><span data-stu-id="a0e04-123">Assign calling ID</span></span>

![调用 ID 设置的屏幕截图](media/call-queue-assign-calling-id.png)

<span data-ttu-id="a0e04-125">如果计划为呼叫代理Teams呼叫代理，可以通过指定一个或多个具有电话号码的资源帐户来为代理分配出站呼叫者 ID 号码。</span><span class="sxs-lookup"><span data-stu-id="a0e04-125">If you plan to use a Teams channel for your call agents, you can assign an outbound caller ID number for the agents by specifying one or more resource accounts with a phone number.</span></span>

<span data-ttu-id="a0e04-126">单击 **"** 添加"，在进行出站调用时搜索要允许代理调用 ID 的资源帐户，单击"添加 **"，然后单击**"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="a0e04-126">Click **Add**, search for the resource accounts that you want to allow agents to for calling ID purposes when making outbound calls, click **Add**, and then click **Add**.</span></span>

<span data-ttu-id="a0e04-127">如果不使用呼叫Teams控制代理成员身份，请考虑直接将呼叫队列成员的呼叫者 ID 设置为呼叫队列的服务号码或相应的自动助理。</span><span class="sxs-lookup"><span data-stu-id="a0e04-127">If you are not using a Teams channel to control agent membership, consider directly setting the caller ID for members of the call queue to the service number of the call queue or appropriate auto attendant.</span></span> <span data-ttu-id="a0e04-128">有关详细信息[，请参阅管理](caller-id-policies.md)Microsoft Teams 中的来电显示策略。</span><span class="sxs-lookup"><span data-stu-id="a0e04-128">See [Manage caller ID policies in Microsoft Teams](caller-id-policies.md) for more information.</span></span>

## <a name="language"></a><span data-ttu-id="a0e04-129">语言</span><span class="sxs-lookup"><span data-stu-id="a0e04-129">Language</span></span>

![语言设置的屏幕截图](media/call-queue-language.png)

<span data-ttu-id="a0e04-131">选择 [受支持的语言](create-a-phone-system-call-queue-languages.md)。</span><span class="sxs-lookup"><span data-stu-id="a0e04-131">Choose a [supported language](create-a-phone-system-call-queue-languages.md).</span></span> <span data-ttu-id="a0e04-132">如果启用语音提示和语音听录，此语言 (系统生成的语音) 。</span><span class="sxs-lookup"><span data-stu-id="a0e04-132">This language will be used for system-generated voice prompts and voicemail transcription (if you enable them).</span></span>

## <a name="greetings-and-music-on-hold-in-queue"></a><span data-ttu-id="a0e04-133">队列中保留的问候语和音乐</span><span class="sxs-lookup"><span data-stu-id="a0e04-133">Greetings and music on hold in queue</span></span>

![队列设置中保持的问候语和音乐的屏幕截图](media/call-queue-greetings-music.png)

<span data-ttu-id="a0e04-135">指定是否要在呼叫者到达队列时播放问候语。</span><span class="sxs-lookup"><span data-stu-id="a0e04-135">Specify if you want to play a greeting to callers when they arrive in the queue.</span></span> <span data-ttu-id="a0e04-136">必须上传包含要播放的问候语的 MP3、WAV 或 WMA 文件。</span><span class="sxs-lookup"><span data-stu-id="a0e04-136">You must upload an MP3, WAV, or WMA file containing the greeting that you want to play.</span></span> <span data-ttu-id="a0e04-137">上传的录制内容不能大于 5 MB。</span><span class="sxs-lookup"><span data-stu-id="a0e04-137">The uploaded recording can be no larger than 5 MB.</span></span>

<span data-ttu-id="a0e04-138">Teams在队列中保持时向呼叫者提供默认音乐。</span><span class="sxs-lookup"><span data-stu-id="a0e04-138">Teams provides default music to callers while they are on hold in a queue.</span></span> <span data-ttu-id="a0e04-139">呼叫队列中提供的默认Teams不收取组织支付的任何版权费。</span><span class="sxs-lookup"><span data-stu-id="a0e04-139">The default music supplied in Teams call queues is free of any royalties payable by your organization.</span></span> <span data-ttu-id="a0e04-140">如果要播放特定音频文件，请选择"播放音频文件 **"并** 上传 MP3、WAV 或 WMA 文件。</span><span class="sxs-lookup"><span data-stu-id="a0e04-140">If you want to play a specific audio file, choose **Play an audio file** and upload an MP3, WAV, or WMA file.</span></span>

> [!NOTE]
> <span data-ttu-id="a0e04-141">你负责独立清除和保护使用任何音乐或音频文件的一切必要权限Microsoft Teams服务， 其中可能包括来自所有相关权利持有者的任何音乐、声音效果、音频、品牌、名称和其他内容中的知识产权和其他权利，其中可能包括艺术家、执行者、执行者、艺术家、歌曲作者、作曲者、录制标签、音乐发布者、联盟、团体、权利代理人、集体管理组织以及拥有、控制或许可音乐版权、声音效果、音频和其他知识产权的其他任何方。</span><span class="sxs-lookup"><span data-stu-id="a0e04-141">You are responsible for independently clearing and securing all necessary rights and permissions to use any music or audio file with your Microsoft Teams service, which may include intellectual property and other rights in any music, sound effects, audio, brands, names, and other content in the audio file from all relevant rights holders, which may include artists, actors, performers, musicians, songwriters, composers, record labels, music publishers, unions, guilds, rights societies, collective management organizations and any other parties who own, control or license the music copyrights, sound effects, audio and other intellectual property rights.</span></span>

## <a name="call-agents"></a><span data-ttu-id="a0e04-142">呼叫代理</span><span class="sxs-lookup"><span data-stu-id="a0e04-142">Call agents</span></span>

<span data-ttu-id="a0e04-143">查看 [将代理添加到呼叫队列的先决条件](plan-auto-attendant-call-queue.md#prerequisites)。</span><span class="sxs-lookup"><span data-stu-id="a0e04-143">Review the [prerequisites for adding agents to a call queue](plan-auto-attendant-call-queue.md#prerequisites).</span></span>

![呼叫队列的用户和组设置的屏幕截图](media/call-queue-users-groups.png)

##### <a name="teams-channel"></a><span data-ttu-id="a0e04-145">Teams频道</span><span class="sxs-lookup"><span data-stu-id="a0e04-145">Teams channel</span></span>

<span data-ttu-id="a0e04-146">可以通过一个客户端通道添加多达 200 Teams代理。</span><span class="sxs-lookup"><span data-stu-id="a0e04-146">You can add up to 200 agents via a Teams channel.</span></span>

<span data-ttu-id="a0e04-147">如果要使用 [频道管理Teams，](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e)请选择"**选择团队"选项，** 然后单击"**添加频道"。**</span><span class="sxs-lookup"><span data-stu-id="a0e04-147">If you want to [use a Teams channel to manage the queue](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e), select the **Choose a team** option and click **Add a channel**.</span></span> <span data-ttu-id="a0e04-148">搜索想要使用的团队，将其选中，然后单击"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="a0e04-148">Search for the team that you want to use, select it, and click **Add**.</span></span> <span data-ttu-id="a0e04-149">选择想要使用的频道，然后单击"应用 **"。**</span><span class="sxs-lookup"><span data-stu-id="a0e04-149">Select the channel that you want to use and click **Apply**.</span></span> <span data-ttu-id="a0e04-150">您必须是团队的成员、频道的创建者或所有者。</span><span class="sxs-lookup"><span data-stu-id="a0e04-150">You must be a member of the team or the creator of or an owner of the channel.</span></span>

<span data-ttu-id="a0e04-151">使用呼叫队列的 Teams支持以下客户端：</span><span class="sxs-lookup"><span data-stu-id="a0e04-151">The following clients are supported when using a Teams channel for call queues:</span></span> 

  - <span data-ttu-id="a0e04-152">Microsoft Teams Windows客户端</span><span class="sxs-lookup"><span data-stu-id="a0e04-152">Microsoft Teams Windows client</span></span>
  - <span data-ttu-id="a0e04-153">Microsoft Teams Mac 客户端</span><span class="sxs-lookup"><span data-stu-id="a0e04-153">Microsoft Teams Mac client</span></span>

> [!NOTE]
> <span data-ttu-id="a0e04-154">如果使用此选项，则呼叫队列可能需要 24 小时才能完全正常运行。</span><span class="sxs-lookup"><span data-stu-id="a0e04-154">If you use this option, it can take up to 24 hours for the call queue to be fully operational.</span></span>

##### <a name="users-and-groups"></a><span data-ttu-id="a0e04-155">用户和组</span><span class="sxs-lookup"><span data-stu-id="a0e04-155">Users and groups</span></span>

<span data-ttu-id="a0e04-156">可以单独添加多达 20 个代理，通过组最多添加 200 个代理。</span><span class="sxs-lookup"><span data-stu-id="a0e04-156">You can add up to 20 agents individually and up to 200 agents via groups.</span></span>

<span data-ttu-id="a0e04-157">如果要将单个用户或组添加到队列，请选择" **选择用户和组"** 选项。</span><span class="sxs-lookup"><span data-stu-id="a0e04-157">If you want to add individual users or groups to the queue, select the **Choose users and groups** option.</span></span> 

<span data-ttu-id="a0e04-158">若要将用户添加到队列，请单击"**添加** 用户"，搜索该用户，单击"添加 **"，然后单击**"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="a0e04-158">To add a user to the queue, click **Add users**, search for the user, click **Add**, and then click **Add**.</span></span>

<span data-ttu-id="a0e04-159">若要将组添加到队列，请单击 **"添加组**"，搜索该组，单击"添加 **"，然后单击**"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="a0e04-159">To add a group to the queue, click **Add groups**, search for the group, click **Add**, and then click **Add**.</span></span> <span data-ttu-id="a0e04-160">可以使用通讯组列表、安全组和Microsoft 365组Microsoft Teams团队。</span><span class="sxs-lookup"><span data-stu-id="a0e04-160">You can use distribution lists, security groups, and Microsoft 365 groups or Microsoft Teams teams.</span></span>

> [!NOTE]
> <span data-ttu-id="a0e04-161">添加到组的新用户可能需要最多八个小时才能进行第一次呼叫。</span><span class="sxs-lookup"><span data-stu-id="a0e04-161">New users added to a group can take up to eight hours for their first call to arrive.</span></span>

## <a name="call-routing"></a><span data-ttu-id="a0e04-162">呼叫路由</span><span class="sxs-lookup"><span data-stu-id="a0e04-162">Call routing</span></span>

![会议模式和路由方法设置的屏幕截图](media/call-queue-conference-mode-routing-method.png)

<span data-ttu-id="a0e04-164">**在** 代理接受呼叫后，会议模式可显著减少呼叫者连接到代理所花的时间。</span><span class="sxs-lookup"><span data-stu-id="a0e04-164">**Conference mode** significantly reduces the amount of time it takes for a caller to be connected to an agent, after the agent accepts the call.</span></span> <span data-ttu-id="a0e04-165">若要使会议模式正常工作，呼叫队列中的代理必须使用以下客户端之一：</span><span class="sxs-lookup"><span data-stu-id="a0e04-165">For conference mode to work, agents in the call queue must use one of the following clients:</span></span>

  - <span data-ttu-id="a0e04-166">最新版本的桌面Microsoft Teams Android 应用或 iOS 应用</span><span class="sxs-lookup"><span data-stu-id="a0e04-166">The latest version of the Microsoft Teams desktop client, Android app, or iOS app</span></span>
  - <span data-ttu-id="a0e04-167">Microsoft Teams 1449/1.0.94.2020051601 或更高版本</span><span class="sxs-lookup"><span data-stu-id="a0e04-167">Microsoft Teams phone version 1449/1.0.94.2020051601 or later</span></span>
  
<span data-ttu-id="a0e04-168">代理Teams帐户需要设置为Teams模式。</span><span class="sxs-lookup"><span data-stu-id="a0e04-168">Agents' Teams accounts need to be set to Teams-only mode.</span></span> <span data-ttu-id="a0e04-169">不符合要求的代理不包括在呼叫路由列表中。</span><span class="sxs-lookup"><span data-stu-id="a0e04-169">Agents who don't meet the requirements aren't included in the call routing list.</span></span> <span data-ttu-id="a0e04-170">如果代理都使用兼容的客户端，建议为呼叫队列启用会议模式。</span><span class="sxs-lookup"><span data-stu-id="a0e04-170">We recommend enabling conference mode for your call queues if your agents are all using compatible clients.</span></span>

> [!NOTE]
> <span data-ttu-id="a0e04-171">如果电话呼叫从为"基于位置的路由"启用的直接路由网关路由到队列，则不支持会议模式。</span><span class="sxs-lookup"><span data-stu-id="a0e04-171">Conference mode is not supported if phone calls are routed to the queue from a Direct Routing gateway that is enabled for Location Based Routing.</span></span>

> [!TIP]
> <span data-ttu-id="a0e04-172">建议 **将"会议\*\*\*\*模式"设置为**"自动"。</span><span class="sxs-lookup"><span data-stu-id="a0e04-172">Setting **Conference mode** to **Auto** is the recommended setting.</span></span>

<span data-ttu-id="a0e04-173">**路由** 方法确定代理从队列接收调用的顺序。</span><span class="sxs-lookup"><span data-stu-id="a0e04-173">**Routing method** determines the order in which agents receive calls from the queue.</span></span> <span data-ttu-id="a0e04-174">从以下选项中进行选择：</span><span class="sxs-lookup"><span data-stu-id="a0e04-174">Choose from these options:</span></span>

- <span data-ttu-id="a0e04-175">**助理路由** 同时将队列中的所有代理环环。</span><span class="sxs-lookup"><span data-stu-id="a0e04-175">**Attendant routing** rings all agents in the queue at the same time.</span></span> <span data-ttu-id="a0e04-176">第一个接电话的呼叫代理获取呼叫。</span><span class="sxs-lookup"><span data-stu-id="a0e04-176">The first call agent to pick up the call gets the call.</span></span>

- <span data-ttu-id="a0e04-177">**串行路由** 按"呼叫代理"列表中指定的顺序一个接一个地拨打所有 **呼叫** 代理。</span><span class="sxs-lookup"><span data-stu-id="a0e04-177">**Serial routing** rings all call agents one by one in the order specified in the **Call agents** list.</span></span> <span data-ttu-id="a0e04-178">如果代理关闭或未接回呼叫，该调用将拨打下一个代理，并尝试所有代理，直到它被选取或退出。</span><span class="sxs-lookup"><span data-stu-id="a0e04-178">If an agent dismisses or does not pick up a call, the call will ring the next agent and will try all agents until it is picked up or times out.</span></span>

- <span data-ttu-id="a0e04-179">**轮循** 机制平衡传入调用的路由，以便每个调用代理从队列中获取相同数量的调用。</span><span class="sxs-lookup"><span data-stu-id="a0e04-179">**Round robin** balances the routing of incoming calls so that each call agent gets the same number of calls from the queue.</span></span> <span data-ttu-id="a0e04-180">在入站销售环境中可能需要这样做，以确保所有呼叫代理之间的机会相等。</span><span class="sxs-lookup"><span data-stu-id="a0e04-180">This may be desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

- <span data-ttu-id="a0e04-181">**最长空闲** 时间将每次调用路由到空闲时间最长的代理。</span><span class="sxs-lookup"><span data-stu-id="a0e04-181">**Longest idle** routes each call to the agent who has been idle the longest time.</span></span> <span data-ttu-id="a0e04-182">如果代理的状态为"可用"或其状态为"离开"时间少于 10 分钟，则代理被视为空闲状态。</span><span class="sxs-lookup"><span data-stu-id="a0e04-182">An agent is considered idle if their presence state is Available or if their presence state has been Away for less than 10 minutes.</span></span> <span data-ttu-id="a0e04-183">状态为"离开"超过 10 分钟的代理不被视为空闲状态，在将状态更改为"可用"之前，他们无法接听呼叫。</span><span class="sxs-lookup"><span data-stu-id="a0e04-183">Agents whose presence state has been Away for more than 10 minutes are not considered idle and will not be eligible to receive calls until they change their presence to Available.</span></span> 

> [!TIP]
> <span data-ttu-id="a0e04-184">建议 **将路由方法\*\*\*\*设置为轮循机制\*\*\*\*或** 最长空闲时间。</span><span class="sxs-lookup"><span data-stu-id="a0e04-184">Setting **Routing Method** to **Round robin** or **Longest idle** is the recommended setting.</span></span>

![路由、选择退出和警报时间设置的屏幕截图](media/call-queue-presence-agents-time.png)

<span data-ttu-id="a0e04-186">**基于状态的路由** 使用呼叫代理的可用性状态来确定是否应在所选路由方法的呼叫路由列表中包含代理。</span><span class="sxs-lookup"><span data-stu-id="a0e04-186">**Presence-based routing** uses the availability status of call agents to determine whether an agent should be included in the call routing list for the selected routing method.</span></span> <span data-ttu-id="a0e04-187">其可用性状态设置为"可用 **"** 的呼叫代理包含在呼叫路由列表中，可以接收呼叫。</span><span class="sxs-lookup"><span data-stu-id="a0e04-187">Call agents whose availability status is set to **Available** are included in the call routing list and can receive calls.</span></span> <span data-ttu-id="a0e04-188">其可用性状态设置为任何其他状态的代理从呼叫路由列表中排除，并且不会接收呼叫，直到其可用性状态更改回"可用 **"。**</span><span class="sxs-lookup"><span data-stu-id="a0e04-188">Agents whose availability status is set to any other status are excluded from the call routing list and won't receive calls until their availability status changes back to **Available**.</span></span> 

<span data-ttu-id="a0e04-189">可以使用任何路由方法启用基于状态的呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="a0e04-189">You can enable presence-based call routing with any of the routing methods.</span></span>

<span data-ttu-id="a0e04-190">如果代理选择不接听呼叫，则无论其可用性状态设置为什么，它们将不会包含在呼叫路由列表中。</span><span class="sxs-lookup"><span data-stu-id="a0e04-190">If an agent opts out of getting calls, they won't be included in the call routing list regardless of what their availability status is set to.</span></span> 

> [!NOTE]
> <span data-ttu-id="a0e04-191">选择 **"最长** 空闲时间"作为路由方法时，需要并自动启用基于状态的路由，即使基于状态的路由切换将关闭并灰显。</span><span class="sxs-lookup"><span data-stu-id="a0e04-191">When **Longest idle** is selected as the routing method, presence-based routing is required and automatically enabled even though the Presence-based routing toggle will be **Off** and grayed out.</span></span>
>
> <span data-ttu-id="a0e04-192">如果未启用基于状态的路由，并且队列中有多个调用，系统将同时向代理显示这些调用，而不管代理的状态如何。</span><span class="sxs-lookup"><span data-stu-id="a0e04-192">If presence-based routing is not enabled and there are multiple calls in the queue, the system will present these calls simultaneously to the agents regardless of their presence status.</span></span> <span data-ttu-id="a0e04-193">这会导致向代理发送多个呼叫通知，尤其是当某些代理不应答发送给代理的初始呼叫时。</span><span class="sxs-lookup"><span data-stu-id="a0e04-193">This will result in multiple call notifications to agents, particularly if some agents don’t answer the initial call presented to them.</span></span>
> 
> <span data-ttu-id="a0e04-194">启用基于Skype for Business路由时，使用客户端的代理不会包含在呼叫路由列表中。</span><span class="sxs-lookup"><span data-stu-id="a0e04-194">Agents who use the Skype for Business client aren't included in the call routing list when presence-based routing is enabled.</span></span> <span data-ttu-id="a0e04-195">如果代理使用 Skype for Business，请不要启用基于状态的呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="a0e04-195">If you have agents who use Skype for Business, don't enable presence-based call routing.</span></span>

> [!TIP]
> <span data-ttu-id="a0e04-196">建议 **将基于状态路由设置为\*\*\*\*"** 打开"。</span><span class="sxs-lookup"><span data-stu-id="a0e04-196">Setting **Presence-based routing** to **On** is the recommended setting.</span></span>

<span data-ttu-id="a0e04-197">**代理警报** 时间指定在队列将呼叫重定向到下一个代理之前，代理的电话将响铃的时间。</span><span class="sxs-lookup"><span data-stu-id="a0e04-197">**Agent alert time** specifies how long an agent's phone will ring before the queue redirects the call to the next agent.</span></span>

> [!TIP]
> <span data-ttu-id="a0e04-198">建议 **将代理警报时间\*\*\*\*设置为 20** 秒。</span><span class="sxs-lookup"><span data-stu-id="a0e04-198">Setting **Agent alert time** to **20 seconds** is the recommended setting.</span></span>

## <a name="call-overflow-handling"></a><span data-ttu-id="a0e04-199">调用溢出处理</span><span class="sxs-lookup"><span data-stu-id="a0e04-199">Call overflow handling</span></span>

![呼叫溢出设置的屏幕截图](media/call-queue-overflow-handling.png)

<span data-ttu-id="a0e04-201">**队列中的最大调用** 数指定在任意给定时间可在队列中等待的最大调用数。</span><span class="sxs-lookup"><span data-stu-id="a0e04-201">**Maximum calls in the queue** specifies the maximum number of calls that can wait in the queue at any given time.</span></span> <span data-ttu-id="a0e04-202">默认值为 50，但范围为 0 到 200。</span><span class="sxs-lookup"><span data-stu-id="a0e04-202">The default is 50, but it can range from 0 to 200.</span></span> <span data-ttu-id="a0e04-203">达到此限制时，按"达到最大调用数时"设置指定 **处理** 调用。</span><span class="sxs-lookup"><span data-stu-id="a0e04-203">When this limit is reached, the call is handled as specified by the **When the maximum number of calls is reached** setting.</span></span>

<span data-ttu-id="a0e04-204">可以选择断开呼叫连接或将其重定向到任何呼叫路由目标。</span><span class="sxs-lookup"><span data-stu-id="a0e04-204">You can choose to disconnect the call or redirect it to any of the call routing destinations.</span></span> <span data-ttu-id="a0e04-205">例如，你可能让呼叫者为队列中的代理留下语音邮件。</span><span class="sxs-lookup"><span data-stu-id="a0e04-205">For example, you might have the caller leave a voicemail for the agents in the queue.</span></span> <span data-ttu-id="a0e04-206">有关外部传输，请参阅先决条件和外部[](plan-auto-attendant-call-queue.md#prerequisites)电话号码转移[- 号码](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)格式的技术详细信息。</span><span class="sxs-lookup"><span data-stu-id="a0e04-206">For external transfers, please refer to [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) and the [external phone number transfers - technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) for number formatting.</span></span>

> [!NOTE]
> <span data-ttu-id="a0e04-207">如果最大呼叫数设置为 0，则问候消息将不会播放。</span><span class="sxs-lookup"><span data-stu-id="a0e04-207">If the maximum number of calls is set to 0 then the greeting message will not play.</span></span>

## <a name="call-timeout-handling"></a><span data-ttu-id="a0e04-208">调用超时处理</span><span class="sxs-lookup"><span data-stu-id="a0e04-208">Call timeout handling</span></span>

![通话超时设置的屏幕截图](media/call-queue-timeout-handling.png)

<span data-ttu-id="a0e04-210">**调用超时：最长等待时间** 指定在重定向或断开连接之前，呼叫在队列中可以保持的最大时间。</span><span class="sxs-lookup"><span data-stu-id="a0e04-210">**Call Timeout: maximum wait time** specifies the maximum time a call can be on hold in the queue before it is redirected or disconnected.</span></span> <span data-ttu-id="a0e04-211">可以指定 0 秒到 45 分钟的值。</span><span class="sxs-lookup"><span data-stu-id="a0e04-211">You can specify a value from 0 seconds to 45 minutes.</span></span>

<span data-ttu-id="a0e04-212">可以选择断开呼叫连接或将其重定向到呼叫路由目标之一。</span><span class="sxs-lookup"><span data-stu-id="a0e04-212">You can choose to disconnect the call or redirect it to one of the call routing destinations.</span></span> <span data-ttu-id="a0e04-213">例如，你可能让呼叫者为队列中的代理留下语音邮件。</span><span class="sxs-lookup"><span data-stu-id="a0e04-213">For example, you might have the caller leave a voicemail for the agents in the queue.</span></span> <span data-ttu-id="a0e04-214">有关外部传输，请参阅先决条件和外部[](plan-auto-attendant-call-queue.md#prerequisites)电话号码转移[- 号码](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)格式的技术详细信息。</span><span class="sxs-lookup"><span data-stu-id="a0e04-214">For external transfers, please refer to [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) and the [external phone number transfers - technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) for number formatting.</span></span>

<span data-ttu-id="a0e04-215">选择通话超时选项后，单击"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="a0e04-215">When you have selected your call timeout options, click **Save**.</span></span>

## <a name="summary-of-recommended-call-queue-settings"></a><span data-ttu-id="a0e04-216">建议的呼叫队列设置摘要</span><span class="sxs-lookup"><span data-stu-id="a0e04-216">Summary of recommended call queue settings</span></span>

<span data-ttu-id="a0e04-217">建议设置以下设置：</span><span class="sxs-lookup"><span data-stu-id="a0e04-217">The following settings are recommended:</span></span>

- <span data-ttu-id="a0e04-218">**"会议模式** "到 **"自动"**</span><span class="sxs-lookup"><span data-stu-id="a0e04-218">**Conference mode** to **Auto**</span></span>
- <span data-ttu-id="a0e04-219">**路由到轮\*\*\*\*循机制或\*\*\*\*最长空闲时间的方法**</span><span class="sxs-lookup"><span data-stu-id="a0e04-219">**Routing method** to **Round robin** or **Longest idle**</span></span>
- <span data-ttu-id="a0e04-220">**基于状态到"打开"** 的 **路由**</span><span class="sxs-lookup"><span data-stu-id="a0e04-220">**Presence-based routing** to **On**</span></span>
- <span data-ttu-id="a0e04-221">**代理警报时间：\*\*\*\*到 20 秒**</span><span class="sxs-lookup"><span data-stu-id="a0e04-221">**Agent alert time:** to **20 seconds**</span></span>

## <a name="supported-clients"></a><span data-ttu-id="a0e04-222">支持的客户端</span><span class="sxs-lookup"><span data-stu-id="a0e04-222">Supported clients</span></span>

<span data-ttu-id="a0e04-223">呼叫队列中的呼叫代理支持以下客户端：</span><span class="sxs-lookup"><span data-stu-id="a0e04-223">The following clients are supported for call agents in a call queue:</span></span>

  - <span data-ttu-id="a0e04-224">Skype for Business桌面客户端 2016 (32 位和 64 位版本) </span><span class="sxs-lookup"><span data-stu-id="a0e04-224">Skype for Business desktop client 2016 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="a0e04-225">Lync 桌面客户端 2013 (32 位和 64 位版本) </span><span class="sxs-lookup"><span data-stu-id="a0e04-225">Lync desktop client 2013 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="a0e04-226">支持所有 IP 电话型号Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="a0e04-226">All IP phone models supported for Microsoft Teams.</span></span> <span data-ttu-id="a0e04-227">请参阅[获取适用于 Skype for Business Online 的电话](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online)。</span><span class="sxs-lookup"><span data-stu-id="a0e04-227">See [Getting phones for Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span></span>
  - <span data-ttu-id="a0e04-228">Mac Skype for Business 客户端（版本 16.8.196 及更高版本）</span><span class="sxs-lookup"><span data-stu-id="a0e04-228">Mac Skype for Business Client (version 16.8.196 and later)</span></span>
  - <span data-ttu-id="a0e04-229">Android Skype for Business 客户端（版本 6.16.0.9 及更高版本）</span><span class="sxs-lookup"><span data-stu-id="a0e04-229">Android Skype for Business Client (version 6.16.0.9 and later)</span></span>
  - <span data-ttu-id="a0e04-230">iPhone Skype for Business 客户端（版本 6.16.0 及更高版本）</span><span class="sxs-lookup"><span data-stu-id="a0e04-230">iPhone Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="a0e04-231">iPad Skype for Business 客户端（版本 6.16.0 及更高版本）</span><span class="sxs-lookup"><span data-stu-id="a0e04-231">iPad Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="a0e04-232">Microsoft Teams Windows客户端 (32 位和 64 位) </span><span class="sxs-lookup"><span data-stu-id="a0e04-232">Microsoft Teams Windows client (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="a0e04-233">Microsoft Teams Mac 客户端</span><span class="sxs-lookup"><span data-stu-id="a0e04-233">Microsoft Teams Mac client</span></span>
  - <span data-ttu-id="a0e04-234">Microsoft Teams[虚拟桌面、Citrix](/microsoftteams/teams-for-vdi)和 VMware (Windows虚拟桌面基础结构) </span><span class="sxs-lookup"><span data-stu-id="a0e04-234">Microsoft Teams on [Virtualized Desktop Infrastructure](/microsoftteams/teams-for-vdi) (Windows Virtual Desktop, Citrix, and VMware)</span></span>
  - <span data-ttu-id="a0e04-235">Microsoft Teams iPhone 应用</span><span class="sxs-lookup"><span data-stu-id="a0e04-235">Microsoft Teams iPhone app</span></span>
  - <span data-ttu-id="a0e04-236">Microsoft Teams Android 应用</span><span class="sxs-lookup"><span data-stu-id="a0e04-236">Microsoft Teams Android app</span></span>

    > [!NOTE]
    > <span data-ttu-id="a0e04-237">分配有直接路由号码的呼叫队列不支持将 Skype for Business、Lync 客户端或 Skype for Business IP 电话作为代理。</span><span class="sxs-lookup"><span data-stu-id="a0e04-237">Call queues that are assigned a direct routing number don't support Skype for Business clients, Lync clients, or Skype for Business IP Phones as agents.</span></span>

## <a name="call-queue-cmdlets"></a><span data-ttu-id="a0e04-238">呼叫队列 cmdlet</span><span class="sxs-lookup"><span data-stu-id="a0e04-238">Call queue cmdlets</span></span>

<span data-ttu-id="a0e04-239">还可以使用 Windows PowerShell 来创建和设置呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="a0e04-239">You can also use Windows PowerShell to create and set up call queues.</span></span> <span data-ttu-id="a0e04-240">下面是用于管理呼叫队列的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a0e04-240">Here are the cmdlets that you use to manage a call queue.</span></span>

- [<span data-ttu-id="a0e04-241">New-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="a0e04-241">New-CsCallQueue</span></span>](/powershell/module/skype/new-CsCallQueue)

- [<span data-ttu-id="a0e04-242">Set-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="a0e04-242">Set-CsCallQueue</span></span>](/powershell/module/skype/set-CsCallQueue)

- [<span data-ttu-id="a0e04-243">Get-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="a0e04-243">Get-CsCallQueue</span></span>](/powershell/module/skype/get-CsCallQueue)

- [<span data-ttu-id="a0e04-244">Remove-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="a0e04-244">Remove-CsCallQueue</span></span>](/powershell/module/skype/remove-CsCallQueue)

## <a name="related-topics"></a><span data-ttu-id="a0e04-245">相关主题</span><span class="sxs-lookup"><span data-stu-id="a0e04-245">Related topics</span></span>

[<span data-ttu-id="a0e04-246">电话系统的功能</span><span class="sxs-lookup"><span data-stu-id="a0e04-246">Here's what you get with Phone System</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="a0e04-247">获取服务电话号码</span><span class="sxs-lookup"><span data-stu-id="a0e04-247">Getting service phone numbers</span></span>](getting-service-phone-numbers.md)

[<span data-ttu-id="a0e04-248">音频会议和通话套餐的国家/地区可用性</span><span class="sxs-lookup"><span data-stu-id="a0e04-248">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="a0e04-249">New-CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="a0e04-249">New-CsOnlineApplicationInstance</span></span>](/powershell/module/skype/new-csonlineapplicationinstance)

[<span data-ttu-id="a0e04-250">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="a0e04-250">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
