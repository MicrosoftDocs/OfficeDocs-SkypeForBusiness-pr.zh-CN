---
title: 在 Microsoft Teams 创建呼叫队列 - 小型企业教程
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: colongma
ms.topic: article
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
description: 了解如何使用 Microsoft 365 Business Voice 设置呼叫队列。
ms.openlocfilehash: 10bc19f122daab89c91a01db0ffa31f48739d96d
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909604"
---
# <a name="create-a-call-queue---small-business-tutorial"></a><span data-ttu-id="2a353-103">创建呼叫队列 - 小型企业教程</span><span class="sxs-lookup"><span data-stu-id="2a353-103">Create a call queue - small business tutorial</span></span>

<span data-ttu-id="2a353-104">呼叫队列提供将呼叫者路由到组织中可以帮助解决特定问题或问题的人的方法。</span><span class="sxs-lookup"><span data-stu-id="2a353-104">Call queues provide a method of routing callers to people in your organization who can help with with a particular issue or question.</span></span> <span data-ttu-id="2a353-105">呼叫一次一个地分配给队列中 (称为代理) 。 </span><span class="sxs-lookup"><span data-stu-id="2a353-105">Calls are distributed one at a time to the people in the queue (who are known as *agents*).</span></span> 

<span data-ttu-id="2a353-106">呼叫队列提供：</span><span class="sxs-lookup"><span data-stu-id="2a353-106">Call queues provide:</span></span>

- <span data-ttu-id="2a353-107">问候消息。</span><span class="sxs-lookup"><span data-stu-id="2a353-107">A greeting message.</span></span>

- <span data-ttu-id="2a353-108">音乐排入队列等待等待时，将打开队列。</span><span class="sxs-lookup"><span data-stu-id="2a353-108">Music while people are waiting on hold in a queue.</span></span>

- <span data-ttu-id="2a353-109">将 FIFO 的"先到 *先* 出 (") 调用路由到代理。</span><span class="sxs-lookup"><span data-stu-id="2a353-109">Call routing - in *First In, First Out* (FIFO) order - to agents.</span></span>

- <span data-ttu-id="2a353-110">处理队列溢出和超时的选项。</span><span class="sxs-lookup"><span data-stu-id="2a353-110">Handling options for queue overflow and timeout.</span></span>

#### <a name="before-you-begin"></a><span data-ttu-id="2a353-111">开始之前</span><span class="sxs-lookup"><span data-stu-id="2a353-111">Before you begin</span></span>

<span data-ttu-id="2a353-112">获取一 [些电话系统 - 虚拟](../teams-add-on-licensing/virtual-user.md) 用户许可证（如果还没有）。</span><span class="sxs-lookup"><span data-stu-id="2a353-112">Get some [Phone System - Virtual User licenses](../teams-add-on-licensing/virtual-user.md) if you don't already have them.</span></span> <span data-ttu-id="2a353-113">为计划设置的每个呼叫队列和自动助理获取一个。</span><span class="sxs-lookup"><span data-stu-id="2a353-113">Get one for each call queue and auto attendant that you plan to set up.</span></span> <span data-ttu-id="2a353-114">这些许可证是免费的，因此我们建议额外获取一些许可证，以防你决定在将来更改设置。</span><span class="sxs-lookup"><span data-stu-id="2a353-114">These licenses are free, so we suggest getting a few extra in case you decide to make changes to your setup in the future.</span></span>

<span data-ttu-id="2a353-115">由于呼叫队列中的代理可能会拨出以返回客户呼叫，因此请考虑将呼叫代理的呼叫者 ID 设置为主电话号码或相应的自动助理号码。</span><span class="sxs-lookup"><span data-stu-id="2a353-115">Since agents in a call queue may dial out to return a customer call, consider setting the caller ID for your call agents to your main phone number or the number of an appropriate auto attendant.</span></span> <span data-ttu-id="2a353-116">有关详细信息 [，请参阅"在 Microsoft Teams 中管理来电](../caller-id-policies.md) 显示策略"。</span><span class="sxs-lookup"><span data-stu-id="2a353-116">See [Manage caller ID policies in Microsoft Teams](../caller-id-policies.md) for more information.</span></span>

<a name="steps"></a>

#### <a name="follow-these-steps-to-set-up-your-call-queue"></a><span data-ttu-id="2a353-117">按照以下步骤设置呼叫队列</span><span class="sxs-lookup"><span data-stu-id="2a353-117">Follow these steps to set up your call queue</span></span>

# <a name="step-1brcreate-a-team"></a>[<span data-ttu-id="2a353-118">步骤 <br> 1：创建团队</span><span class="sxs-lookup"><span data-stu-id="2a353-118">Step 1<br>Create a team</span></span>](#tab/create-team)

<span data-ttu-id="2a353-119">创建呼叫队列时，可以将单个用户添加到队列，或者可以使用现有的安全组、Microsoft 365 组或 Microsoft Teams 团队。</span><span class="sxs-lookup"><span data-stu-id="2a353-119">When creating a call queue, you can add individual users to the queue, or you can use an existing security group, Microsoft 365 group, or Microsoft Teams team.</span></span> <span data-ttu-id="2a353-120">建议使用团队。</span><span class="sxs-lookup"><span data-stu-id="2a353-120">We recommend using a team.</span></span> <span data-ttu-id="2a353-121">这样，队列的成员可以彼此聊天、共享想法以及创建文档或其他资源，以帮助他们帮助客户。</span><span class="sxs-lookup"><span data-stu-id="2a353-121">This allows members of the queue to chat with each other, share ideas, and create documents or other resources to help them help your customers.</span></span> <span data-ttu-id="2a353-122">团队还提供语音邮箱，让呼叫者在数小时后或在队列达到最大容量时留下消息。</span><span class="sxs-lookup"><span data-stu-id="2a353-122">A team also provides a voice mailbox for callers to leave a message after hours or if the queue reaches its maximum capacity.</span></span>

<span data-ttu-id="2a353-123">创建团队</span><span class="sxs-lookup"><span data-stu-id="2a353-123">To create a team</span></span>

1. <span data-ttu-id="2a353-124">首先，单击应用左侧的 **Teams，** 然后单击"加入"或在团队列表底部创建团队。</span><span class="sxs-lookup"><span data-stu-id="2a353-124">First, click **Teams** on the left side of the app, then click **Join or create a team** at the bottom of your teams list.</span></span>

2. <span data-ttu-id="2a353-125">然后单击" **创建团队 (** 第一张卡片，左上角) 。</span><span class="sxs-lookup"><span data-stu-id="2a353-125">Then click **Create team** (first card, top left corner).</span></span>

3. <span data-ttu-id="2a353-126">从头开始 **选择"构建团队"。**</span><span class="sxs-lookup"><span data-stu-id="2a353-126">Choose **Build a team from scratch**.</span></span>

4. <span data-ttu-id="2a353-127">接下来，选择是需要公共团队还是私人团队。</span><span class="sxs-lookup"><span data-stu-id="2a353-127">Next, choose whether you want a public or private team.</span></span> <span data-ttu-id="2a353-128">建议 **为** 呼叫队列使用"专用"，以避免人员通过加入团队无意中成为队列的一部分。</span><span class="sxs-lookup"><span data-stu-id="2a353-128">We recommend **Private** for your call queue to avoid people unintentionally becoming part of the queue by joining the team.</span></span>

5. <span data-ttu-id="2a353-129">为团队命名并添加可选说明。</span><span class="sxs-lookup"><span data-stu-id="2a353-129">Name your team and add an optional description.</span></span>

6. <span data-ttu-id="2a353-130">完成后，单击"创建 **"。**</span><span class="sxs-lookup"><span data-stu-id="2a353-130">When you're done, click **Create**.</span></span>

8. <span data-ttu-id="2a353-131">键入要加入呼叫队列的人的姓名，然后单击"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="2a353-131">Type the names of the people that you want to have in your call queue, and then click **Add**.</span></span>

9. <span data-ttu-id="2a353-132">单击“关闭”。</span><span class="sxs-lookup"><span data-stu-id="2a353-132">Click **Close**.</span></span> <span data-ttu-id="2a353-133">您添加到团队的人将收到一封电子邮件，让他们知道他们现在是团队的成员，并且团队会显示在团队列表中。</span><span class="sxs-lookup"><span data-stu-id="2a353-133">People you add to a team will receive an email letting them know they are now a member of your team and the team will show up in their teams list.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="2a353-134">步骤 2 - 资源帐户></span><span class="sxs-lookup"><span data-stu-id="2a353-134">Step 2 - Resource accounts ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?branch=mikeplum-smb-voice&tabs=resource-account#steps)

# <a name="step-2brresource-accounts"></a>[<span data-ttu-id="2a353-135">步骤 2 <br> 资源帐户</span><span class="sxs-lookup"><span data-stu-id="2a353-135">Step 2<br>Resource accounts</span></span>](#tab/resource-account)

<span data-ttu-id="2a353-136">创建的每个呼叫队列都需要一个资源帐户。</span><span class="sxs-lookup"><span data-stu-id="2a353-136">Each call queue that you create requires a resource account.</span></span> <span data-ttu-id="2a353-137">这类似于用户帐户，但该帐户与自动助理或呼叫队列（而不是人员）相关联。</span><span class="sxs-lookup"><span data-stu-id="2a353-137">This is similar to a user account, except the account is associated with an auto attendant or call queue instead of a person.</span></span> <span data-ttu-id="2a353-138">在此步骤中，我们将创建帐户，为其分配 *Microsoft 365 电话* 系统 - 虚拟用户许可证，然后使用它开始创建呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="2a353-138">In this step, we'll create the account, assign it a *Microsoft 365 Phone System - Virtual User* license, and then use it to start creating the call queue.</span></span>

### <a name="create-a-resource-account"></a><span data-ttu-id="2a353-139">创建资源帐户</span><span class="sxs-lookup"><span data-stu-id="2a353-139">Create a resource account</span></span>

<span data-ttu-id="2a353-140">可以在 Teams 管理中心创建资源帐户。</span><span class="sxs-lookup"><span data-stu-id="2a353-140">You can create a resource account in the Teams admin center.</span></span>

1. <span data-ttu-id="2a353-141">在 Teams 管理中心中，展开 **组织范围的设置**，然后单击"**资源帐户"。**</span><span class="sxs-lookup"><span data-stu-id="2a353-141">In the Teams admin center, expand **Org-wide settings**, and then click **Resource accounts**.</span></span>

2. <span data-ttu-id="2a353-142">单击“添加”。</span><span class="sxs-lookup"><span data-stu-id="2a353-142">Click **Add**.</span></span>

3. <span data-ttu-id="2a353-143">在"**添加资源帐户"** 窗格中，填写 **显示名称**、**用户名**，并选择"呼叫队列 **"作为资源\*\*\*\*帐户类型**。</span><span class="sxs-lookup"><span data-stu-id="2a353-143">In the **Add resource account** pane, fill out **Display name**, **Username**, and choose **Call queue** for the **Resource account type**.</span></span>

    ![添加资源帐户用户界面的屏幕截图](../media/resource-account-add-cq.png)

4. <span data-ttu-id="2a353-145">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="2a353-145">Click **Save**.</span></span>

<span data-ttu-id="2a353-146">新帐户将显示在帐户列表中。</span><span class="sxs-lookup"><span data-stu-id="2a353-146">The new account will appear in the list of accounts.</span></span>

![资源帐户列表的屏幕截图](../media/resource-accounts-page.png)

### <a name="assign-a-license"></a><span data-ttu-id="2a353-148">分配许可证</span><span class="sxs-lookup"><span data-stu-id="2a353-148">Assign a license</span></span>

<span data-ttu-id="2a353-149">必须将 Microsoft *365 手机系统 - 虚拟用户* 许可证分配给资源帐户。</span><span class="sxs-lookup"><span data-stu-id="2a353-149">You must assign a *Microsoft 365 Phone System - Virtual User* license to the resource account.</span></span>

1. <span data-ttu-id="2a353-150">在 Microsoft 365 管理中心中，单击要为其分配许可证的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="2a353-150">In the Microsoft 365 admin center, click the resource account to which you want to assign a license.</span></span>

2. <span data-ttu-id="2a353-151">在"**许可证和应用"选项卡** 上的"**许可证"** 下，选择 **"Microsoft 365 手机系统 - 虚拟用户"。**</span><span class="sxs-lookup"><span data-stu-id="2a353-151">On the **Licenses and Apps** tab, under **Licenses**, select **Microsoft 365 Phone System - Virtual User**.</span></span>

3. <span data-ttu-id="2a353-152">单击 **"保存更改"。**</span><span class="sxs-lookup"><span data-stu-id="2a353-152">Click **Save changes**.</span></span>

    ![Microsoft 365 管理中心中分配许可证用户界面的屏幕截图](../media/resource-account-assign-virtual-user-license.png)

### <a name="create-a-call-queue"></a><span data-ttu-id="2a353-154">创建呼叫队列</span><span class="sxs-lookup"><span data-stu-id="2a353-154">Create a call queue</span></span>

<span data-ttu-id="2a353-155">接下来，我们将开始创建新的呼叫队列并分配资源帐户。</span><span class="sxs-lookup"><span data-stu-id="2a353-155">Next, we'll start creating a new call queue and assign the resource account.</span></span>

1. <span data-ttu-id="2a353-156">在 Teams 管理中心，展开 **"语音**"，单击"呼叫 **队列**"，然后单击"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="2a353-156">In the Teams admin center, expand **Voice**, click **Call queues**, and then click **Add**.</span></span>

1. <span data-ttu-id="2a353-157">键入呼叫队列的名称。</span><span class="sxs-lookup"><span data-stu-id="2a353-157">Type a name for the call queue.</span></span> <span data-ttu-id="2a353-158">代理收到来自队列的传入呼叫时，会看到此名称。</span><span class="sxs-lookup"><span data-stu-id="2a353-158">Agents will see this name when they receive an incoming call from the queue.</span></span>

2. <span data-ttu-id="2a353-159">单击 **"添加** 帐户"，搜索要用于此呼叫队列的资源帐户，单击"添加"，然后单击"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="2a353-159">Click **Add accounts**, search for the resource account that you want to use with this call queue, click **Add**, and then click **Add**.</span></span>

3. <span data-ttu-id="2a353-160">选择一种语言。</span><span class="sxs-lookup"><span data-stu-id="2a353-160">Choose a language.</span></span> <span data-ttu-id="2a353-161">如果启用系统生成的语音提示和语音邮件听录， (此语言) 。</span><span class="sxs-lookup"><span data-stu-id="2a353-161">This language will be used for system-generated voice prompts and voicemail transcription (if you enable them).</span></span>

    ![资源帐户和语言设置的屏幕截图](../media/call-queue-name-language.png)

4. <span data-ttu-id="2a353-163">指定是否要在呼叫者到达队列时播放问候语。</span><span class="sxs-lookup"><span data-stu-id="2a353-163">Specify if you want to play a greeting to callers when they arrive in the queue.</span></span> <span data-ttu-id="2a353-164">必须上传包含要播放的问候语的 MP3、WAV 或 WMA 文件。</span><span class="sxs-lookup"><span data-stu-id="2a353-164">You must upload an MP3, WAV, or WMA file containing the greeting that you want to play.</span></span>

5. <span data-ttu-id="2a353-165">当呼叫者在队列中保持时，Teams 会向他们提供默认音乐。</span><span class="sxs-lookup"><span data-stu-id="2a353-165">Teams provides default music to callers while they are on hold in a queue.</span></span> <span data-ttu-id="2a353-166">如果要播放特定音频文件，请选择"播放音频文件"并上传 MP3、WAV 或 WMA 文件。</span><span class="sxs-lookup"><span data-stu-id="2a353-166">If you want to play a specific audio file, choose **Play an audio file** and upload an MP3, WAV, or WMA file.</span></span>

> [!NOTE]
> <span data-ttu-id="2a353-167">上传的录制内容不能大于 5 MB。</span><span class="sxs-lookup"><span data-stu-id="2a353-167">The uploaded recording can be no larger than 5 MB.</span></span>
> <span data-ttu-id="2a353-168">Teams 呼叫队列中提供的默认音乐不收取组织支付的任何版权费。</span><span class="sxs-lookup"><span data-stu-id="2a353-168">The default music supplied in Teams call queues is free of any royalties payable by your organization.</span></span> 

> [!div class="nextstepaction"]
> [<span data-ttu-id="2a353-169">步骤 3 - 呼叫></span><span class="sxs-lookup"><span data-stu-id="2a353-169">Step 3 - Call agents ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?branch=mikeplum-smb-voice&tabs=call-agents#steps)

# <a name="step-3brcall-agents"></a>[<span data-ttu-id="2a353-170">步骤 3 <br> 呼叫代理</span><span class="sxs-lookup"><span data-stu-id="2a353-170">Step 3<br>Call agents</span></span>](#tab/call-agents)

<span data-ttu-id="2a353-171">若要将代理添加到呼叫队列，我们将添加我们之前创建的团队。</span><span class="sxs-lookup"><span data-stu-id="2a353-171">To add agents to the call queue, we'll add the team that we created earlier.</span></span>

1. <span data-ttu-id="2a353-172">单击 **"添加组"。**</span><span class="sxs-lookup"><span data-stu-id="2a353-172">Click **Add groups**.</span></span>
2. <span data-ttu-id="2a353-173">键入创建的团队的名称。</span><span class="sxs-lookup"><span data-stu-id="2a353-173">Type the name of the team that you created.</span></span>
3. <span data-ttu-id="2a353-174">单击 **"添加**"，然后单击"**添加"。**</span><span class="sxs-lookup"><span data-stu-id="2a353-174">Click **Add**, and then click **Add**.</span></span>

    ![呼叫队列的用户和组设置的屏幕截图](../media/call-queue-users-groups-smb.png)

<span data-ttu-id="2a353-176">可以单独添加多达 20 个代理，通过组或团队最多添加 200 个代理。</span><span class="sxs-lookup"><span data-stu-id="2a353-176">You can add up to 20 agents individually and up to 200 agents via groups or teams.</span></span>

> [!NOTE]
> <span data-ttu-id="2a353-177">将新用户添加到团队后，最多可能需要 8 小时才能进行第一次呼叫。</span><span class="sxs-lookup"><span data-stu-id="2a353-177">When new users are added to the team, it can take up to eight hours for their first call to arrive.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="2a353-178">步骤 4 - 资源帐户></span><span class="sxs-lookup"><span data-stu-id="2a353-178">Step 4 - Resource accounts ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?branch=mikeplum-smb-voice&tabs=call-routing#steps)

# <a name="step-4brcall-routing"></a>[<span data-ttu-id="2a353-179">步骤 4 <br> 呼叫路由</span><span class="sxs-lookup"><span data-stu-id="2a353-179">Step 4<br>Call routing</span></span>](#tab/call-routing)

<span data-ttu-id="2a353-180">选择想要使用的呼叫路由方法。</span><span class="sxs-lookup"><span data-stu-id="2a353-180">Choose the call routing method that you want to use.</span></span>

1. <span data-ttu-id="2a353-181">将 **会议模式设置为\*\*\*\*"自动"。**</span><span class="sxs-lookup"><span data-stu-id="2a353-181">Set **Conference mode** to **Auto**.</span></span>

2. <span data-ttu-id="2a353-182">选择 **想要使用的** 路由方法。</span><span class="sxs-lookup"><span data-stu-id="2a353-182">Choose the **Routing method** you want to use.</span></span> <span data-ttu-id="2a353-183">这会确定代理从队列接收调用的顺序。</span><span class="sxs-lookup"><span data-stu-id="2a353-183">This determines the order in which agents receive calls from the queue.</span></span> <span data-ttu-id="2a353-184">我们建议使用 **串行路由** 或  **轮循机制**。</span><span class="sxs-lookup"><span data-stu-id="2a353-184">We recommend **Serial routing** or  **Round robin**.</span></span> <span data-ttu-id="2a353-185">从以下选项中选择：</span><span class="sxs-lookup"><span data-stu-id="2a353-185">Choose from these options:</span></span>

    - <span data-ttu-id="2a353-186">**助理路由** 同时会圈出队列中的所有代理。</span><span class="sxs-lookup"><span data-stu-id="2a353-186">**Attendant routing** rings all agents in the queue at the same time.</span></span> <span data-ttu-id="2a353-187">第一个接电话的呼叫代理获取呼叫。</span><span class="sxs-lookup"><span data-stu-id="2a353-187">The first call agent to pick up the call gets the call.</span></span>

    - <span data-ttu-id="2a353-188">**串行路由** 将一个接一个地拨打所有呼叫代理。</span><span class="sxs-lookup"><span data-stu-id="2a353-188">**Serial routing** rings all call agents one by one.</span></span> <span data-ttu-id="2a353-189">如果代理关闭或未接回呼叫，该调用将拨打下一个代理，并尝试所有代理，直到它被选取或退出。</span><span class="sxs-lookup"><span data-stu-id="2a353-189">If an agent dismisses or does not pick up a call, the call will ring the next agent and will try all agents until it is picked up or times out.</span></span>

    - <span data-ttu-id="2a353-190">**轮循** 机制对传入调用的路由进行平衡，以便每个调用代理从队列中获取相同数量的调用。</span><span class="sxs-lookup"><span data-stu-id="2a353-190">**Round robin** balances the routing of incoming calls so that each call agent gets the same number of calls from the queue.</span></span> <span data-ttu-id="2a353-191">在入站销售环境中可能需要这样做，以确保所有呼叫代理之间的机会相等。</span><span class="sxs-lookup"><span data-stu-id="2a353-191">This may be desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

    - <span data-ttu-id="2a353-192">**最长空闲** 将每次调用路由到空闲时间最长的代理。</span><span class="sxs-lookup"><span data-stu-id="2a353-192">**Longest idle** routes each call to the agent who has been idle the longest time.</span></span> <span data-ttu-id="2a353-193"> (状态为"离开"超过 10 分钟，则不包括其状态为"离开"的代理。) </span><span class="sxs-lookup"><span data-stu-id="2a353-193">(Agents whose presence state has been Away for more than 10 minutes are not included.)</span></span>

    ![会议模式和路由方法设置的屏幕截图](../media/call-queue-conference-mode-routing-method.png)

3. <span data-ttu-id="2a353-195">打开 **基于状态路由** 。</span><span class="sxs-lookup"><span data-stu-id="2a353-195">Turn **Presence-based routing** on.</span></span> <span data-ttu-id="2a353-196">这会将调用路由到其状态为"可用"的 **代理**。</span><span class="sxs-lookup"><span data-stu-id="2a353-196">This routes calls to agents whose presence status is **Available**.</span></span>

4. <span data-ttu-id="2a353-197">选择是否允许代理选择退出呼叫。</span><span class="sxs-lookup"><span data-stu-id="2a353-197">Choose if you want to allow agents to opt out of calls.</span></span>

5. <span data-ttu-id="2a353-198">设置 **代理警报时间** ，指定代理的电话在队列将呼叫重定向到下一个代理之前响铃的时间。</span><span class="sxs-lookup"><span data-stu-id="2a353-198">Set an **Agent alert time** to specify how long an agent's phone will ring before the queue redirects the call to the next agent.</span></span>

    ![路由、选择退出和警报时间设置的屏幕截图](../media/call-queue-presence-agents-time.png)

> [!div class="nextstepaction"]
> [<span data-ttu-id="2a353-200">步骤 5 - 调用溢出></span><span class="sxs-lookup"><span data-stu-id="2a353-200">Step 5 - Call overflow ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?branch=mikeplum-smb-voice&tabs=call-overflow#steps)

# <a name="step-5brcall-overflow"></a>[<span data-ttu-id="2a353-201">步骤 5 <br> 调用溢出</span><span class="sxs-lookup"><span data-stu-id="2a353-201">Step 5<br>Call overflow</span></span>](#tab/call-overflow)

<span data-ttu-id="2a353-202">选择要如何处理队列中超出最大值的调用。</span><span class="sxs-lookup"><span data-stu-id="2a353-202">Choose how you want to handle calls that exceed the maximum in the queue.</span></span>

1. <span data-ttu-id="2a353-203">设置 **队列中的最大调用数**。</span><span class="sxs-lookup"><span data-stu-id="2a353-203">Set the **Maximum calls in the queue**.</span></span>

2. <span data-ttu-id="2a353-204">选择在达到最大呼叫数时要执行哪些工作。</span><span class="sxs-lookup"><span data-stu-id="2a353-204">Choose what you want to do when the maximum number of calls is reached.</span></span> <span data-ttu-id="2a353-205">您可以断开呼叫或重定向呼叫。</span><span class="sxs-lookup"><span data-stu-id="2a353-205">You can disconnect the call or redirect it.</span></span> <span data-ttu-id="2a353-206">建议将调用重定向到以下目标之一：</span><span class="sxs-lookup"><span data-stu-id="2a353-206">We recommend that you redirect the call to one of the following destinations:</span></span>
    - <span data-ttu-id="2a353-207">**组织中的人** - 组织中能够接收语音呼叫的人</span><span class="sxs-lookup"><span data-stu-id="2a353-207">**Person in the organization** - a person in your organization who is able to receive voice calls</span></span>
    - <span data-ttu-id="2a353-208">**语音应用** - 自动助理或其他呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="2a353-208">**Voice app** - an auto attendant or another call queue.</span></span> <span data-ttu-id="2a353-209"> (选择此目标时与自动助理或呼叫队列关联的资源帐户。) </span><span class="sxs-lookup"><span data-stu-id="2a353-209">(Choose the resource account associated with the auto attendant or call queue when choosing this destination.)</span></span>
    - <span data-ttu-id="2a353-210">**外部电话号码** - 任何电话号码。</span><span class="sxs-lookup"><span data-stu-id="2a353-210">**External phone number** - any phone number.</span></span> <span data-ttu-id="2a353-211">使用此格式：+[国家/地区代码][区号][电话号码]</span><span class="sxs-lookup"><span data-stu-id="2a353-211">Use this format: +[country code][area code][phone number]</span></span>
    - <span data-ttu-id="2a353-212">**语音邮件** - 可以使用创建的团队的语音邮箱。</span><span class="sxs-lookup"><span data-stu-id="2a353-212">**Voicemail** - you can use the voice mailbox of the team that you created.</span></span>

    ![呼叫溢出设置的屏幕截图](../media/call-queue-overflow-handling.png)

> [!div class="nextstepaction"]
> [<span data-ttu-id="2a353-214">步骤 6 - 调用超时></span><span class="sxs-lookup"><span data-stu-id="2a353-214">Step 6 - Call timeout ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?branch=mikeplum-smb-voice&tabs=call-timeout#steps)

# <a name="step-6brcall-timeout"></a>[<span data-ttu-id="2a353-215">步骤 6 <br> 调用超时</span><span class="sxs-lookup"><span data-stu-id="2a353-215">Step 6<br>Call timeout</span></span>](#tab/call-timeout)

<span data-ttu-id="2a353-216">选择要在通话在队列中等待太长时间时发生的情况。</span><span class="sxs-lookup"><span data-stu-id="2a353-216">Choose what you want to happen when calls have been waiting in the queue for too long.</span></span>

1. <span data-ttu-id="2a353-217">设置调用 **超时：最长等待时间**。</span><span class="sxs-lookup"><span data-stu-id="2a353-217">Set the **Call Timeout: maximum wait time**.</span></span>

2. <span data-ttu-id="2a353-218">选择通话打时要执行哪些工作。您可以断开呼叫或重定向呼叫。</span><span class="sxs-lookup"><span data-stu-id="2a353-218">Choose what you want to do when a call times out. You can disconnect the call or redirect it.</span></span> <span data-ttu-id="2a353-219">建议将调用重定向到以下目标之一：</span><span class="sxs-lookup"><span data-stu-id="2a353-219">We recommend that you redirect the call to one of the following destinations:</span></span>
    - <span data-ttu-id="2a353-220">**组织中的人** - 组织中能够接收语音呼叫的人</span><span class="sxs-lookup"><span data-stu-id="2a353-220">**Person in the organization** - a person in your organization who is able to receive voice calls</span></span>
    - <span data-ttu-id="2a353-221">**语音应用** - 自动助理或其他呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="2a353-221">**Voice app** - an auto attendant or another call queue.</span></span> <span data-ttu-id="2a353-222"> (选择此目标时与自动助理或呼叫队列关联的资源帐户。) </span><span class="sxs-lookup"><span data-stu-id="2a353-222">(Choose the resource account associated with the auto attendant or call queue when choosing this destination.)</span></span>
    - <span data-ttu-id="2a353-223">**外部电话号码** - 任何电话号码。</span><span class="sxs-lookup"><span data-stu-id="2a353-223">**External phone number** - any phone number.</span></span> <span data-ttu-id="2a353-224">使用此格式：+[国家/地区代码][区号][电话号码]</span><span class="sxs-lookup"><span data-stu-id="2a353-224">Use this format: +[country code][area code][phone number]</span></span>
    - <span data-ttu-id="2a353-225">**语音邮件** - 可以使用创建的团队的语音邮箱。</span><span class="sxs-lookup"><span data-stu-id="2a353-225">**Voicemail** - you can use the voice mailbox of the team that you created.</span></span>

    ![通话超时设置的屏幕截图](../media/call-queue-timeout-handling.png)

3. <span data-ttu-id="2a353-227">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="2a353-227">Click **Save**.</span></span>

<span data-ttu-id="2a353-228">这将完成呼叫队列的设置。</span><span class="sxs-lookup"><span data-stu-id="2a353-228">This completes the setup of your call queue.</span></span> <span data-ttu-id="2a353-229">接下来，你可能想要 [设置自动助理](create-a-phone-system-auto-attendant-smb.md)。</span><span class="sxs-lookup"><span data-stu-id="2a353-229">Next, you may want to [set up an auto attendant](create-a-phone-system-auto-attendant-smb.md).</span></span>

---

