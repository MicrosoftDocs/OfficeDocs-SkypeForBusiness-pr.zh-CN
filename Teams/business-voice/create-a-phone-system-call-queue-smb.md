---
title: 在企业 - 小型企业Microsoft Teams呼叫队列
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: dobro
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
description: 了解如何在 Microsoft 365 商务语音 中为小型企业设置呼叫Microsoft 365 商务语音。
ms.openlocfilehash: e7141d32015207469346e018bc12bc362254ba2f
ms.sourcegitcommit: d77104d5606ff93a792e8712d6c7780ae247b536
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/25/2021
ms.locfileid: "53126918"
---
# <a name="create-a-call-queue---small-business-tutorial"></a><span data-ttu-id="778fd-103">创建呼叫队列 - 小型企业教程</span><span class="sxs-lookup"><span data-stu-id="778fd-103">Create a call queue - small business tutorial</span></span>

<span data-ttu-id="778fd-104">呼叫队列提供将呼叫者路由到组织中可以解决特定问题或问题的人的方法。</span><span class="sxs-lookup"><span data-stu-id="778fd-104">Call queues provide a method of routing callers to people in your organization who can help with a particular issue or question.</span></span> <span data-ttu-id="778fd-105">呼叫一次一个地分配给队列中 (称为代理 *) 。*</span><span class="sxs-lookup"><span data-stu-id="778fd-105">Calls are distributed one at a time to the people in the queue (who are known as *agents*).</span></span> 

<span data-ttu-id="778fd-106">呼叫队列提供：</span><span class="sxs-lookup"><span data-stu-id="778fd-106">Call queues provide:</span></span>

- <span data-ttu-id="778fd-107">问候消息。</span><span class="sxs-lookup"><span data-stu-id="778fd-107">A greeting message.</span></span>

- <span data-ttu-id="778fd-108">音乐在等待队列中等待时，</span><span class="sxs-lookup"><span data-stu-id="778fd-108">Music while people are waiting on hold in a queue.</span></span>

- <span data-ttu-id="778fd-109">调用路由 - 在 *"先* 到先出" (FIFO) 顺序 - 到代理。</span><span class="sxs-lookup"><span data-stu-id="778fd-109">Call routing - in *First In, First Out* (FIFO) order - to agents.</span></span>

- <span data-ttu-id="778fd-110">处理队列溢出和超时的选项。</span><span class="sxs-lookup"><span data-stu-id="778fd-110">Handling options for queue overflow and timeout.</span></span>

#### <a name="video-demonstration"></a><span data-ttu-id="778fd-111">视频演示</span><span class="sxs-lookup"><span data-stu-id="778fd-111">Video demonstration</span></span>

<span data-ttu-id="778fd-112">此视频演示如何在 Teams。</span><span class="sxs-lookup"><span data-stu-id="778fd-112">This video demonstrates how to create a call queue in Teams.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWCF23?autoplay=false]

#### <a name="before-you-begin"></a><span data-ttu-id="778fd-113">开始之前</span><span class="sxs-lookup"><span data-stu-id="778fd-113">Before you begin</span></span>

<span data-ttu-id="778fd-114">获取电话系统[- 虚拟用户](../teams-add-on-licensing/virtual-user.md)许可证（如果还没有）。</span><span class="sxs-lookup"><span data-stu-id="778fd-114">Get some [Phone System - Virtual User licenses](../teams-add-on-licensing/virtual-user.md) if you don't already have them.</span></span> <span data-ttu-id="778fd-115">为计划设置的每个呼叫队列和自动助理获取一个。</span><span class="sxs-lookup"><span data-stu-id="778fd-115">Get one for each call queue and auto attendant that you plan to set up.</span></span> <span data-ttu-id="778fd-116">这些许可证是免费的，因此我们建议获取一些额外的许可证，以防你决定在将来对设置进行更改。</span><span class="sxs-lookup"><span data-stu-id="778fd-116">These licenses are free, so we suggest getting a few extra in case you decide to make changes to your setup in the future.</span></span>

<span data-ttu-id="778fd-117">由于呼叫队列中的代理可能会拨出以返回客户呼叫，因此请考虑将呼叫代理的呼叫者 ID 设置为主电话号码或相应的自动助理号码。</span><span class="sxs-lookup"><span data-stu-id="778fd-117">Since agents in a call queue may dial out to return a customer call, consider setting the caller ID for your call agents to your main phone number or the number of an appropriate auto attendant.</span></span> <span data-ttu-id="778fd-118">有关详细信息[，请参阅管理](../caller-id-policies.md)Microsoft Teams 中的来电显示策略。</span><span class="sxs-lookup"><span data-stu-id="778fd-118">See [Manage caller ID policies in Microsoft Teams](../caller-id-policies.md) for more information.</span></span>

<a name="steps"></a>

#### <a name="follow-these-steps-to-set-up-your-call-queue"></a><span data-ttu-id="778fd-119">按照以下步骤设置呼叫队列</span><span class="sxs-lookup"><span data-stu-id="778fd-119">Follow these steps to set up your call queue</span></span>

# <a name="step-1brcreate-a-team"></a>[<span data-ttu-id="778fd-120">步骤 1 <br> 创建团队</span><span class="sxs-lookup"><span data-stu-id="778fd-120">Step 1<br>Create a team</span></span>](#tab/create-team)

<span data-ttu-id="778fd-121">创建呼叫队列时，可以将单个用户添加到队列，或者可以使用现有的安全组、Microsoft 365组或Microsoft Teams团队。</span><span class="sxs-lookup"><span data-stu-id="778fd-121">When creating a call queue, you can add individual users to the queue, or you can use an existing security group, Microsoft 365 group, or Microsoft Teams team.</span></span> <span data-ttu-id="778fd-122">建议使用 [团队频道](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e)。</span><span class="sxs-lookup"><span data-stu-id="778fd-122">We recommend [using a team channel](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e).</span></span> <span data-ttu-id="778fd-123">这样，队列成员可以相互聊天、分享想法以及创建文档或其他资源，以帮助他们帮助客户。</span><span class="sxs-lookup"><span data-stu-id="778fd-123">This allows members of the queue to chat with each other, share ideas, and create documents or other resources to help them help your customers.</span></span> <span data-ttu-id="778fd-124">团队还提供语音邮箱，让呼叫者在数小时后或队列达到最大容量时留下消息。</span><span class="sxs-lookup"><span data-stu-id="778fd-124">A team also provides a voice mailbox for callers to leave a message after hours or if the queue reaches its maximum capacity.</span></span>

<span data-ttu-id="778fd-125">创建团队</span><span class="sxs-lookup"><span data-stu-id="778fd-125">To create a team</span></span>

1. <span data-ttu-id="778fd-126">首先 **，Teams** 左侧的"团队"，然后单击团队列表底部的"加入或创建团队"。</span><span class="sxs-lookup"><span data-stu-id="778fd-126">First, click **Teams** on the left side of the app, then click **Join or create a team** at the bottom of your teams list.</span></span>

2. <span data-ttu-id="778fd-127">然后单击" **创建团队 (** 卡片，左上角显示) 。</span><span class="sxs-lookup"><span data-stu-id="778fd-127">Then click **Create team** (first card, top left corner).</span></span>

3. <span data-ttu-id="778fd-128">选择 **"从头开始构建团队"。**</span><span class="sxs-lookup"><span data-stu-id="778fd-128">Choose **Build a team from scratch**.</span></span>

4. <span data-ttu-id="778fd-129">接下来，选择是需要公共团队还是专用团队。</span><span class="sxs-lookup"><span data-stu-id="778fd-129">Next, choose whether you want a public or private team.</span></span> <span data-ttu-id="778fd-130">建议 **为** 呼叫队列使用"专用"，以避免用户通过加入团队无意中成为队列的一部分。</span><span class="sxs-lookup"><span data-stu-id="778fd-130">We recommend **Private** for your call queue to avoid people unintentionally becoming part of the queue by joining the team.</span></span>

5. <span data-ttu-id="778fd-131">命名团队并添加可选说明。</span><span class="sxs-lookup"><span data-stu-id="778fd-131">Name your team and add an optional description.</span></span>

6. <span data-ttu-id="778fd-132">完成后，单击"创建 **"。**</span><span class="sxs-lookup"><span data-stu-id="778fd-132">When you're done, click **Create**.</span></span>

8. <span data-ttu-id="778fd-133">键入您希望在呼叫队列中拥有的人的姓名，然后单击"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="778fd-133">Type the names of the people that you want to have in your call queue, and then click **Add**.</span></span>

9. <span data-ttu-id="778fd-134">单击“关闭”。</span><span class="sxs-lookup"><span data-stu-id="778fd-134">Click **Close**.</span></span> <span data-ttu-id="778fd-135">添加到团队的人将收到一封电子邮件，让他们知道他们现在是团队的成员，并且团队会显示在团队列表中。</span><span class="sxs-lookup"><span data-stu-id="778fd-135">People you add to a team will receive an email letting them know they are now a member of your team and the team will show up in their teams list.</span></span>

<span data-ttu-id="778fd-136">接下来，我们将添加用于呼叫队列的通道。</span><span class="sxs-lookup"><span data-stu-id="778fd-136">Next, we'll add a channel to use with the call queue.</span></span>

<span data-ttu-id="778fd-137">添加频道</span><span class="sxs-lookup"><span data-stu-id="778fd-137">To add a channel</span></span>

1. <span data-ttu-id="778fd-138">在Teams中，找到刚创建的团队，单击"更多选项" (...) ，然后单击"添加 **频道"。**</span><span class="sxs-lookup"><span data-stu-id="778fd-138">In Teams, find the team you just created, click **More options** (...), and then click **Add channel**.</span></span>

2. <span data-ttu-id="778fd-139">键入频道的名称和说明，然后单击"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="778fd-139">Type a name and description for the channel, and then click **Add**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="778fd-140">步骤 2 - 资源帐户></span><span class="sxs-lookup"><span data-stu-id="778fd-140">Step 2 - Resource accounts ></span></span>](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=resource-account#steps)

# <a name="step-2brresource-accounts"></a>[<span data-ttu-id="778fd-141">步骤 2 <br> 资源帐户</span><span class="sxs-lookup"><span data-stu-id="778fd-141">Step 2<br>Resource accounts</span></span>](#tab/resource-account)

<span data-ttu-id="778fd-142">创建的每个呼叫队列都需要一个资源帐户。</span><span class="sxs-lookup"><span data-stu-id="778fd-142">Each call queue that you create requires a resource account.</span></span> <span data-ttu-id="778fd-143">这类似于用户帐户，但该帐户与自动助理或呼叫队列（而不是人员）相关联。</span><span class="sxs-lookup"><span data-stu-id="778fd-143">This is similar to a user account, except the account is associated with an auto attendant or call queue instead of a person.</span></span> <span data-ttu-id="778fd-144">在此步骤中，我们将创建帐户，为其分配Microsoft 365 电话系统 - 虚拟 *用户* 许可证，然后使用它开始创建呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="778fd-144">In this step, we'll create the account, assign it a *Microsoft 365 Phone System - Virtual User* license, and then use it to start creating the call queue.</span></span>

### <a name="create-a-resource-account"></a><span data-ttu-id="778fd-145">创建资源帐户</span><span class="sxs-lookup"><span data-stu-id="778fd-145">Create a resource account</span></span>

<span data-ttu-id="778fd-146">可以在管理中心内创建Teams帐户。</span><span class="sxs-lookup"><span data-stu-id="778fd-146">You can create a resource account in the Teams admin center.</span></span>

1. <span data-ttu-id="778fd-147">在Teams管理中心，展开 **"组织范围的设置**"，然后单击"**资源帐户"。**</span><span class="sxs-lookup"><span data-stu-id="778fd-147">In the Teams admin center, expand **Org-wide settings**, and then click **Resource accounts**.</span></span>

2. <span data-ttu-id="778fd-148">单击“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="778fd-148">Click **Add**.</span></span>

3. <span data-ttu-id="778fd-149">在"**添加资源帐户"** 窗格中，填写"**显示名称**、**用户名"，** 然后选择"呼叫队列 **"作为"** 资源帐户 **类型"。**</span><span class="sxs-lookup"><span data-stu-id="778fd-149">In the **Add resource account** pane, fill out **Display name**, **Username**, and choose **Call queue** for the **Resource account type**.</span></span> <span data-ttu-id="778fd-150">代理收到来自显示名称来电时，会看到消息。</span><span class="sxs-lookup"><span data-stu-id="778fd-150">Agents will see the display name when they receive an incoming call from the queue.</span></span>

    ![添加资源帐户用户界面的屏幕截图](../media/resource-account-add-cq.png)

4. <span data-ttu-id="778fd-152">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="778fd-152">Click **Save**.</span></span>

   <span data-ttu-id="778fd-153">新帐户将显示在帐户列表中。</span><span class="sxs-lookup"><span data-stu-id="778fd-153">The new account will appear in the list of accounts.</span></span>

   ![资源帐户列表的屏幕截图](../media/resource-accounts-page.png)

### <a name="assign-a-license"></a><span data-ttu-id="778fd-155">分配许可证</span><span class="sxs-lookup"><span data-stu-id="778fd-155">Assign a license</span></span>

<span data-ttu-id="778fd-156">必须为资源帐户 *Microsoft 365 电话系统 - 虚拟* 用户许可证。</span><span class="sxs-lookup"><span data-stu-id="778fd-156">You must assign a *Microsoft 365 Phone System - Virtual User* license to the resource account.</span></span>

1. <span data-ttu-id="778fd-157">在Microsoft 365 管理中心"**活动** 用户"列表中，单击要为其分配许可证的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="778fd-157">In the Microsoft 365 admin center, in the **Active users** list, click the resource account to which you want to assign a license.</span></span>

2. <span data-ttu-id="778fd-158">在"**许可证和应用"选项卡上的**"许可证 **"下**，选择 **"Microsoft 365 电话系统 - 虚拟用户"。**</span><span class="sxs-lookup"><span data-stu-id="778fd-158">On the **Licenses and Apps** tab, under **Licenses**, select **Microsoft 365 Phone System - Virtual User**.</span></span>

3. <span data-ttu-id="778fd-159">单击"**保存更改"。**</span><span class="sxs-lookup"><span data-stu-id="778fd-159">Click **Save changes**.</span></span>

    !["许可证分配"用户界面的屏幕截图Microsoft 365 管理中心](../media/resource-account-assign-virtual-user-license.png)

### <a name="create-a-call-queue"></a><span data-ttu-id="778fd-161">创建呼叫队列</span><span class="sxs-lookup"><span data-stu-id="778fd-161">Create a call queue</span></span>

<span data-ttu-id="778fd-162">接下来，我们将开始创建新的呼叫队列并分配资源帐户。</span><span class="sxs-lookup"><span data-stu-id="778fd-162">Next, we'll start creating a new call queue and assign the resource account.</span></span>

1. <span data-ttu-id="778fd-163">在Teams中心，展开"**语音**"，单击"**呼叫队列**"，然后单击"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="778fd-163">In the Teams admin center, expand **Voice**, click **Call queues**, and then click **Add**.</span></span>

1. <span data-ttu-id="778fd-164">键入呼叫队列的名称。</span><span class="sxs-lookup"><span data-stu-id="778fd-164">Type a name for the call queue.</span></span>

2. <span data-ttu-id="778fd-165">单击 **"添加** 帐户"，搜索要用于此呼叫队列的资源帐户，单击"添加 **"，然后单击**"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="778fd-165">Click **Add accounts**, search for the resource account that you want to use with this call queue, click **Add**, and then click **Add**.</span></span>

3. <span data-ttu-id="778fd-166"> (可选) "分配呼叫 **ID"** 下，单击"添加"，搜索为自动助理创建的资源帐户，单击"添加 **"，然后单击**"**添加"。**</span><span class="sxs-lookup"><span data-stu-id="778fd-166">(Optional) Under **Assign calling ID**, click **Add**, search for the resource accounts that you created for your auto attendant, click **Add**, and then click **Add**.</span></span> <span data-ttu-id="778fd-167">这将在呼叫代理进行呼叫时为呼叫代理提供主线呼叫者 ID。</span><span class="sxs-lookup"><span data-stu-id="778fd-167">This will give your call agents the caller ID of your main line when they call out.</span></span>

    ![调用 ID 设置的屏幕截图](../media/call-queue-assign-calling-id.png)

3. <span data-ttu-id="778fd-169">选择一种语言。</span><span class="sxs-lookup"><span data-stu-id="778fd-169">Choose a language.</span></span> <span data-ttu-id="778fd-170">如果启用语音提示和语音听录，此语言 (系统生成的语音) 。</span><span class="sxs-lookup"><span data-stu-id="778fd-170">This language will be used for system-generated voice prompts and voicemail transcription (if you enable them).</span></span>

    ![资源帐户设置的屏幕截图](../media/call-queue-name-language.png)

4. <span data-ttu-id="778fd-172">指定是否要在呼叫者到达队列时播放问候语。</span><span class="sxs-lookup"><span data-stu-id="778fd-172">Specify if you want to play a greeting to callers when they arrive in the queue.</span></span> <span data-ttu-id="778fd-173">必须上传包含要播放的问候语的 MP3、WAV 或 WMA 文件。</span><span class="sxs-lookup"><span data-stu-id="778fd-173">You must upload an MP3, WAV, or WMA file containing the greeting that you want to play.</span></span>

5. <span data-ttu-id="778fd-174">Teams在队列中保持时向呼叫者提供默认音乐。</span><span class="sxs-lookup"><span data-stu-id="778fd-174">Teams provides default music to callers while they are on hold in a queue.</span></span> <span data-ttu-id="778fd-175">如果要播放特定音频文件，请选择"播放音频文件 **"并** 上传 MP3、WAV 或 WMA 文件。</span><span class="sxs-lookup"><span data-stu-id="778fd-175">If you want to play a specific audio file, choose **Play an audio file** and upload an MP3, WAV, or WMA file.</span></span>

   > [!NOTE]
   > <span data-ttu-id="778fd-176">上传的录制内容不能大于 5 MB。</span><span class="sxs-lookup"><span data-stu-id="778fd-176">The uploaded recording can be no larger than 5 MB.</span></span>
   > <span data-ttu-id="778fd-177">呼叫队列中提供的默认Teams不收取组织支付的任何版权费。</span><span class="sxs-lookup"><span data-stu-id="778fd-177">The default music supplied in Teams call queues is free of any royalties payable by your organization.</span></span> 

> [!div class="nextstepaction"]
> [<span data-ttu-id="778fd-178">步骤 3 - 呼叫></span><span class="sxs-lookup"><span data-stu-id="778fd-178">Step 3 - Call agents ></span></span>](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=call-agents#steps)

# <a name="step-3brcall-agents"></a>[<span data-ttu-id="778fd-179">步骤 3 <br> 呼叫代理</span><span class="sxs-lookup"><span data-stu-id="778fd-179">Step 3<br>Call agents</span></span>](#tab/call-agents)

<span data-ttu-id="778fd-180">若要将代理添加到呼叫队列，我们会将它们添加到我们之前创建的团队和频道。</span><span class="sxs-lookup"><span data-stu-id="778fd-180">To add agents to the call queue, we'll add them to the team and channel that we created earlier.</span></span> <span data-ttu-id="778fd-181">你需要是团队的成员来这样做。</span><span class="sxs-lookup"><span data-stu-id="778fd-181">You need to be a member of the team to do this.</span></span>

1. <span data-ttu-id="778fd-182">选择"**选择团队"选项，** 然后单击 **"添加频道"。**</span><span class="sxs-lookup"><span data-stu-id="778fd-182">Select the **Choose a team** option and click **Add a channel**.</span></span>
2. <span data-ttu-id="778fd-183">键入创建的团队的名称，将其选中，然后单击"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="778fd-183">Type the name of the team that you created, select it, and click **Add**.</span></span>
3. <span data-ttu-id="778fd-184">选择为队列创建的通道。</span><span class="sxs-lookup"><span data-stu-id="778fd-184">Select the channel that you created for the queue.</span></span>
3. <span data-ttu-id="778fd-185">单击“**应用**”。</span><span class="sxs-lookup"><span data-stu-id="778fd-185">Click **Apply**.</span></span>

    ![呼叫队列的用户和组设置的屏幕截图](../media/call-queue-users-groups.png)

> [!NOTE]
> <span data-ttu-id="778fd-187">将新用户添加到团队后，最多可能需要八个小时才能第一次呼叫到达。</span><span class="sxs-lookup"><span data-stu-id="778fd-187">When new users are added to the team, it can take up to eight hours for their first call to arrive.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="778fd-188">步骤 4 - 资源帐户></span><span class="sxs-lookup"><span data-stu-id="778fd-188">Step 4 - Resource accounts ></span></span>](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=call-routing#steps)

# <a name="step-4brcall-routing"></a>[<span data-ttu-id="778fd-189">步骤 4 <br> 呼叫路由</span><span class="sxs-lookup"><span data-stu-id="778fd-189">Step 4<br>Call routing</span></span>](#tab/call-routing)

<span data-ttu-id="778fd-190">选择想要使用的呼叫路由方法。</span><span class="sxs-lookup"><span data-stu-id="778fd-190">Choose the call routing method that you want to use.</span></span>

1. <span data-ttu-id="778fd-191">将 **"会议模式"设置为**"**自动"。**</span><span class="sxs-lookup"><span data-stu-id="778fd-191">Set **Conference mode** to **Auto**.</span></span>

2. <span data-ttu-id="778fd-192">选择 **想要使用的** 路由方法。</span><span class="sxs-lookup"><span data-stu-id="778fd-192">Choose the **Routing method** you want to use.</span></span> <span data-ttu-id="778fd-193">这会确定代理从队列接收调用的顺序。</span><span class="sxs-lookup"><span data-stu-id="778fd-193">This determines the order in which agents receive calls from the queue.</span></span> <span data-ttu-id="778fd-194">我们建议使用 **串行路由或\*\*\*\*轮循机制**。</span><span class="sxs-lookup"><span data-stu-id="778fd-194">We recommend **Serial routing** or  **Round robin**.</span></span> <span data-ttu-id="778fd-195">从以下选项中进行选择：</span><span class="sxs-lookup"><span data-stu-id="778fd-195">Choose from these options:</span></span>

    - <span data-ttu-id="778fd-196">**助理路由** 同时将队列中的所有代理环环。</span><span class="sxs-lookup"><span data-stu-id="778fd-196">**Attendant routing** rings all agents in the queue at the same time.</span></span> <span data-ttu-id="778fd-197">第一个接电话的呼叫代理获取呼叫。</span><span class="sxs-lookup"><span data-stu-id="778fd-197">The first call agent to pick up the call gets the call.</span></span>

    - <span data-ttu-id="778fd-198">**串行路由** 将一个接一个地拨打所有呼叫代理。</span><span class="sxs-lookup"><span data-stu-id="778fd-198">**Serial routing** rings all call agents one by one.</span></span> <span data-ttu-id="778fd-199">如果代理关闭或未接回呼叫，该调用将拨打下一个代理，并尝试所有代理，直到它被选取或退出。</span><span class="sxs-lookup"><span data-stu-id="778fd-199">If an agent dismisses or does not pick up a call, the call will ring the next agent and will try all agents until it is picked up or times out.</span></span>

    - <span data-ttu-id="778fd-200">**轮循** 机制平衡传入调用的路由，以便每个调用代理从队列中获取相同数量的调用。</span><span class="sxs-lookup"><span data-stu-id="778fd-200">**Round robin** balances the routing of incoming calls so that each call agent gets the same number of calls from the queue.</span></span> <span data-ttu-id="778fd-201">在入站销售环境中可能需要这样做，以确保所有呼叫代理之间的机会相等。</span><span class="sxs-lookup"><span data-stu-id="778fd-201">This may be desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

    - <span data-ttu-id="778fd-202">**最长空闲** 时间将每次调用路由到空闲时间最长的代理。</span><span class="sxs-lookup"><span data-stu-id="778fd-202">**Longest idle** routes each call to the agent who has been idle the longest time.</span></span> <span data-ttu-id="778fd-203"> (状态为"离开"超过 10 分钟的代理不包括。) </span><span class="sxs-lookup"><span data-stu-id="778fd-203">(Agents whose presence state has been Away for more than 10 minutes are not included.)</span></span>

    ![会议模式和路由方法设置的屏幕截图](../media/call-queue-conference-mode-routing-method.png)

3. <span data-ttu-id="778fd-205">打开 **基于状态路由** 。</span><span class="sxs-lookup"><span data-stu-id="778fd-205">Turn **Presence-based routing** on.</span></span> <span data-ttu-id="778fd-206">这会将调用路由到状态为"可用"的 **代理**。</span><span class="sxs-lookup"><span data-stu-id="778fd-206">This routes calls to agents whose presence status is **Available**.</span></span>

4. <span data-ttu-id="778fd-207">选择是否允许代理选择退出呼叫。</span><span class="sxs-lookup"><span data-stu-id="778fd-207">Choose if you want to allow agents to opt out of calls.</span></span>

5. <span data-ttu-id="778fd-208">设置 **代理警报** 时间，指定在队列将呼叫重定向到下一个代理之前，代理的电话响铃的时间。</span><span class="sxs-lookup"><span data-stu-id="778fd-208">Set an **Agent alert time** to specify how long an agent's phone will ring before the queue redirects the call to the next agent.</span></span>

    ![路由、选择退出和警报时间设置的屏幕截图](../media/call-queue-presence-agents-time.png)

> [!div class="nextstepaction"]
> [<span data-ttu-id="778fd-210">步骤 5 - 调用溢出></span><span class="sxs-lookup"><span data-stu-id="778fd-210">Step 5 - Call overflow ></span></span>](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=call-overflow#steps)

# <a name="step-5brcall-overflow"></a>[<span data-ttu-id="778fd-211">步骤 5 <br> 调用溢出</span><span class="sxs-lookup"><span data-stu-id="778fd-211">Step 5<br>Call overflow</span></span>](#tab/call-overflow)

<span data-ttu-id="778fd-212">选择要如何处理队列中超过最大值的调用。</span><span class="sxs-lookup"><span data-stu-id="778fd-212">Choose how you want to handle calls that exceed the maximum in the queue.</span></span>

1. <span data-ttu-id="778fd-213">在 **队列中设置最大调用数**。</span><span class="sxs-lookup"><span data-stu-id="778fd-213">Set the **Maximum calls in the queue**.</span></span>

2. <span data-ttu-id="778fd-214">选择达到最大呼叫数时要执行哪些工作。</span><span class="sxs-lookup"><span data-stu-id="778fd-214">Choose what you want to do when the maximum number of calls is reached.</span></span> <span data-ttu-id="778fd-215">你可以断开呼叫或重定向它。</span><span class="sxs-lookup"><span data-stu-id="778fd-215">You can disconnect the call or redirect it.</span></span> <span data-ttu-id="778fd-216">建议将调用重定向到以下目标之一：</span><span class="sxs-lookup"><span data-stu-id="778fd-216">We recommend that you redirect the call to one of the following destinations:</span></span>
    - <span data-ttu-id="778fd-217">**组织中的人** - 组织中能够接收语音呼叫的人</span><span class="sxs-lookup"><span data-stu-id="778fd-217">**Person in the organization** - a person in your organization who is able to receive voice calls</span></span>
    - <span data-ttu-id="778fd-218">**语音应用** - 自动助理或其他呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="778fd-218">**Voice app** - an auto attendant or another call queue.</span></span> <span data-ttu-id="778fd-219"> (选择此目标时选择与自动助理或呼叫队列关联的资源帐户) </span><span class="sxs-lookup"><span data-stu-id="778fd-219">(Choose the resource account associated with the auto attendant or call queue when choosing this destination.)</span></span>
    - <span data-ttu-id="778fd-220">**外部电话号码** - 任何电话号码。</span><span class="sxs-lookup"><span data-stu-id="778fd-220">**External phone number** - any phone number.</span></span> <span data-ttu-id="778fd-221">使用此格式：+[国家/地区代码][区号][电话号码]</span><span class="sxs-lookup"><span data-stu-id="778fd-221">Use this format: +[country code][area code][phone number]</span></span>
    - <span data-ttu-id="778fd-222">**语音邮件** - 您可以使用创建的团队的语音邮箱。</span><span class="sxs-lookup"><span data-stu-id="778fd-222">**Voicemail** - you can use the voice mailbox of the team that you created.</span></span>

    ![呼叫溢出设置的屏幕截图](../media/call-queue-overflow-handling.png)

> [!div class="nextstepaction"]
> [<span data-ttu-id="778fd-224">步骤 6 - 调用超时></span><span class="sxs-lookup"><span data-stu-id="778fd-224">Step 6 - Call timeout ></span></span>](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=call-timeout#steps)

# <a name="step-6brcall-timeout"></a>[<span data-ttu-id="778fd-225">步骤 6 <br> 调用超时</span><span class="sxs-lookup"><span data-stu-id="778fd-225">Step 6<br>Call timeout</span></span>](#tab/call-timeout)

<span data-ttu-id="778fd-226">选择当通话在队列中等待太长时间时要发生的情况。</span><span class="sxs-lookup"><span data-stu-id="778fd-226">Choose what you want to happen when calls have been waiting in the queue for too long.</span></span>

1. <span data-ttu-id="778fd-227">设置"**最长等待时间"。**</span><span class="sxs-lookup"><span data-stu-id="778fd-227">Set the **Maximum wait time**.</span></span>

2. <span data-ttu-id="778fd-228">选择通话打时要执行哪些工作。你可以断开呼叫或重定向它。</span><span class="sxs-lookup"><span data-stu-id="778fd-228">Choose what you want to do when a call times out. You can disconnect the call or redirect it.</span></span> <span data-ttu-id="778fd-229">建议将调用重定向到以下目标之一：</span><span class="sxs-lookup"><span data-stu-id="778fd-229">We recommend that you redirect the call to one of the following destinations:</span></span>
    - <span data-ttu-id="778fd-230">**组织中的人** - 组织中能够接收语音呼叫的人</span><span class="sxs-lookup"><span data-stu-id="778fd-230">**Person in the organization** - a person in your organization who is able to receive voice calls</span></span>
    - <span data-ttu-id="778fd-231">**语音应用** - 自动助理或其他呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="778fd-231">**Voice app** - an auto attendant or another call queue.</span></span> <span data-ttu-id="778fd-232"> (选择此目标时选择与自动助理或呼叫队列关联的资源帐户) </span><span class="sxs-lookup"><span data-stu-id="778fd-232">(Choose the resource account associated with the auto attendant or call queue when choosing this destination.)</span></span>
    - <span data-ttu-id="778fd-233">**外部电话号码** - 任何电话号码。</span><span class="sxs-lookup"><span data-stu-id="778fd-233">**External phone number** - any phone number.</span></span> <span data-ttu-id="778fd-234">使用此格式：+[国家/地区代码][区号][电话号码]</span><span class="sxs-lookup"><span data-stu-id="778fd-234">Use this format: +[country code][area code][phone number]</span></span>
    - <span data-ttu-id="778fd-235">**语音邮件** - 您可以使用创建的团队的语音邮箱。</span><span class="sxs-lookup"><span data-stu-id="778fd-235">**Voicemail** - you can use the voice mailbox of the team that you created.</span></span>

    ![通话超时设置的屏幕截图](../media/call-queue-timeout-handling.png)

3. <span data-ttu-id="778fd-237">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="778fd-237">Click **Save**.</span></span>

<span data-ttu-id="778fd-238">这将完成呼叫队列的设置。</span><span class="sxs-lookup"><span data-stu-id="778fd-238">This completes the setup of your call queue.</span></span> <span data-ttu-id="778fd-239">接下来，你可能希望 [设置自动助理](create-a-phone-system-auto-attendant-smb.md)。</span><span class="sxs-lookup"><span data-stu-id="778fd-239">Next, you may want to [set up an auto attendant](create-a-phone-system-auto-attendant-smb.md).</span></span>

---

