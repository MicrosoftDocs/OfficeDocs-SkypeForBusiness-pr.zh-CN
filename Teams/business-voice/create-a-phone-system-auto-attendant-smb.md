---
title: 为 Microsoft Teams 设置自动助理 - 小型企业教程
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
- Phone System
description: 了解如何为 Microsoft 365 商业语音设置和测试自动助理。
ms.openlocfilehash: 7ee7dad833119778ceb64bd1e52bd30da4529ba8
ms.sourcegitcommit: 50111653f72f6758a3491a4dc3e91160ab75022c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2021
ms.locfileid: "51506649"
---
# <a name="set-up-an-auto-attendant---small-business-tutorial"></a><span data-ttu-id="d78b6-103">设置自动助理 - 小型企业教程</span><span class="sxs-lookup"><span data-stu-id="d78b6-103">Set up an auto attendant - small business tutorial</span></span>

<span data-ttu-id="d78b6-104">自动助理可让你的人呼叫你的组织并导航菜单系统，以与正确的部门、呼叫队列、人员或接线员通话。</span><span class="sxs-lookup"><span data-stu-id="d78b6-104">Auto attendants let people call your organization and navigate a menu system to speak to the right department, call queue, person, or an operator.</span></span> <span data-ttu-id="d78b6-105">可以使用 Microsoft Teams 管理中心为组织创建自动助理。</span><span class="sxs-lookup"><span data-stu-id="d78b6-105">You can create auto attendants for your organization with the Microsoft Teams admin center.</span></span>

#### <a name="before-you-begin"></a><span data-ttu-id="d78b6-106">开始之前</span><span class="sxs-lookup"><span data-stu-id="d78b6-106">Before you begin</span></span>

<span data-ttu-id="d78b6-107">从组织外部直接拨号，获取自动助理所需的服务号码。</span><span class="sxs-lookup"><span data-stu-id="d78b6-107">Get the service numbers that you need for the auto attendants that you want to be accessible by direct dialing from outside your organization.</span></span> <span data-ttu-id="d78b6-108">这可能包括 [从另一个提供商转移号码](../phone-number-calling-plans/transfer-phone-numbers-to-teams.md) 或 [请求新的服务号码](../getting-service-phone-numbers.md)。</span><span class="sxs-lookup"><span data-stu-id="d78b6-108">This might include [transferring numbers from another provider](../phone-number-calling-plans/transfer-phone-numbers-to-teams.md) or [requesting new service numbers](../getting-service-phone-numbers.md).</span></span>

<span data-ttu-id="d78b6-109">获取 [计划创建的每个](../teams-add-on-licensing/virtual-user.md) 自动助理的电话系统 - 虚拟用户许可证。</span><span class="sxs-lookup"><span data-stu-id="d78b6-109">Get a [Phone System - Virtual User license](../teams-add-on-licensing/virtual-user.md) for each auto attendant that you plan to create.</span></span> <span data-ttu-id="d78b6-110">这些许可证是免费的，因此我们建议获取一些额外的许可证，以防你决定在将来对设置进行更改。</span><span class="sxs-lookup"><span data-stu-id="d78b6-110">These licenses are free, so we suggest getting a few extra in case you decide to make changes to your setup in the future.</span></span>

<span data-ttu-id="d78b6-111">如果要让自动助理在假日以不同方式路由呼叫，请创建想要使用的[](../set-up-holidays-in-teams.md)假日，然后再创建自动助理。</span><span class="sxs-lookup"><span data-stu-id="d78b6-111">If you want to have your auto attendant route calls differently on holidays, then [create the holidays that you want to use](../set-up-holidays-in-teams.md) before you create the auto attendant.</span></span>

<a name="steps"></a>

#### <a name="follow-these-steps-to-set-up-your-auto-attendant"></a><span data-ttu-id="d78b6-112">按照以下步骤设置自动助理</span><span class="sxs-lookup"><span data-stu-id="d78b6-112">Follow these steps to set up your auto attendant</span></span>

# <a name="step-1brphone-number"></a>[<span data-ttu-id="d78b6-113">步骤 1 <br> 电话号码</span><span class="sxs-lookup"><span data-stu-id="d78b6-113">Step 1<br>Phone number</span></span>](#tab/phone-number)

<span data-ttu-id="d78b6-114">创建的每个自动助理都需要一个资源帐户。</span><span class="sxs-lookup"><span data-stu-id="d78b6-114">Each auto attendant that you create requires a resource account.</span></span> <span data-ttu-id="d78b6-115">这类似于用户帐户，但该帐户与自动助理或呼叫队列（而不是人员）相关联。</span><span class="sxs-lookup"><span data-stu-id="d78b6-115">This is similar to a user account, except the account is associated with an auto attendant or call queue instead of a person.</span></span> <span data-ttu-id="d78b6-116">在此步骤中，我们将创建帐户，为其分配 *Microsoft 365 电话系统 - 虚拟用户* 许可证，然后分配服务号码。</span><span class="sxs-lookup"><span data-stu-id="d78b6-116">In this step, we'll create the account, assign it a *Microsoft 365 Phone System - Virtual User* license, and then assign a service number.</span></span>

### <a name="create-a-resource-account"></a><span data-ttu-id="d78b6-117">创建资源帐户</span><span class="sxs-lookup"><span data-stu-id="d78b6-117">Create a resource account</span></span>

<span data-ttu-id="d78b6-118">可以在 Teams 管理中心创建资源帐户。</span><span class="sxs-lookup"><span data-stu-id="d78b6-118">You can create a resource account in the Teams admin center.</span></span>

1. <span data-ttu-id="d78b6-119">在 Teams 管理中心中，展开 **"组织范围的设置"，** 然后单击"**资源帐户"。**</span><span class="sxs-lookup"><span data-stu-id="d78b6-119">In the Teams admin center, expand **Org-wide settings**, and then click **Resource accounts**.</span></span>

2. <span data-ttu-id="d78b6-120">单击“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="d78b6-120">Click **Add**.</span></span>

3. <span data-ttu-id="d78b6-121">在" **添加资源帐户"** 窗格中，填写" **显示** 名称"和" **用户名"，** 然后选择" **自动助理"** 作为"资源帐户 **类型"**</span><span class="sxs-lookup"><span data-stu-id="d78b6-121">In the **Add resource account** pane, fill out **Display name**, **Username**, and choose **Auto attendant** for the **Resource account type**</span></span>

    ![添加资源帐户用户界面的屏幕截图](../media/resource-account-add.png)

4. <span data-ttu-id="d78b6-123">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="d78b6-123">Click **Save**.</span></span>

<span data-ttu-id="d78b6-124">新帐户将显示在帐户列表中。</span><span class="sxs-lookup"><span data-stu-id="d78b6-124">The new account will appear in the list of accounts.</span></span>

![资源帐户列表的屏幕截图](../media/resource-accounts-page.png)

### <a name="assign-a-license"></a><span data-ttu-id="d78b6-126">分配许可证</span><span class="sxs-lookup"><span data-stu-id="d78b6-126">Assign a license</span></span>

<span data-ttu-id="d78b6-127">必须将 Microsoft *365 Phone System - 虚拟用户许可证* 分配给资源帐户。</span><span class="sxs-lookup"><span data-stu-id="d78b6-127">You must assign a *Microsoft 365 Phone System - Virtual User* license to the resource account.</span></span>

1. <span data-ttu-id="d78b6-128">在 Microsoft 365 管理中心中，单击要为其分配许可证的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="d78b6-128">In the Microsoft 365 admin center, click the resource account to which you want to assign a license.</span></span>

2. <span data-ttu-id="d78b6-129">在"**许可证和应用"选项卡上的**"许可证 **"下**，选择 **"Microsoft 365 手机系统 - 虚拟用户"。**</span><span class="sxs-lookup"><span data-stu-id="d78b6-129">On the **Licenses and Apps** tab, under **Licenses**, select **Microsoft 365 Phone System - Virtual User**.</span></span>

3. <span data-ttu-id="d78b6-130">单击"**保存更改"。**</span><span class="sxs-lookup"><span data-stu-id="d78b6-130">Click **Save changes**.</span></span>

    ![Microsoft 365 管理中心中分配许可证用户界面的屏幕截图](../media/resource-account-assign-virtual-user-license.png)

### <a name="assign-a-service-number"></a><span data-ttu-id="d78b6-132">分配服务编号</span><span class="sxs-lookup"><span data-stu-id="d78b6-132">Assign a service number</span></span>

<span data-ttu-id="d78b6-133">如果需要通过电话号码访问此自动助理，请将其分配给资源帐户。</span><span class="sxs-lookup"><span data-stu-id="d78b6-133">If you need this auto attendant to be reachable by a phone number, then assign that number to the resource account.</span></span>

1. <span data-ttu-id="d78b6-134">在 Teams 管理中心的"**资源** 帐户"页上，选择要为其分配服务号码的资源帐户，然后单击"分配 **/取消分配"。**</span><span class="sxs-lookup"><span data-stu-id="d78b6-134">In the Teams admin center, on the **Resource accounts** page, select the resource account to which you want to assign a service number, and then click **Assign/unassign**.</span></span>

2. <span data-ttu-id="d78b6-135">在 **"电话号码类型** "下拉列表中，选择想要使用的号码类型。</span><span class="sxs-lookup"><span data-stu-id="d78b6-135">In the **Phone number type** dropdown, choose the type of number that you want to use.</span></span>

3. <span data-ttu-id="d78b6-136">在 **"分配的电话号码"** 框中，搜索想要使用的号码，然后单击"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="d78b6-136">In the **Assigned phone number** box, search for the number you want to use and click **Add**.</span></span>

    ![分配服务编号用户界面的屏幕截图](../media/resource-account-assign-phone-number.png)

4. <span data-ttu-id="d78b6-138">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="d78b6-138">Click **Save**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="d78b6-139">步骤 2 - 自动助理常规信息></span><span class="sxs-lookup"><span data-stu-id="d78b6-139">Step 2 - Auto attendant general info ></span></span>](/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?tabs=general-info#steps)

# <a name="step-2brattendant-general-info"></a>[<span data-ttu-id="d78b6-140">步骤 2 <br> Attendant 常规信息</span><span class="sxs-lookup"><span data-stu-id="d78b6-140">Step 2<br>Attendant general info</span></span>](#tab/general-info)

<span data-ttu-id="d78b6-141">设置自动助理</span><span class="sxs-lookup"><span data-stu-id="d78b6-141">To set up an auto attendant</span></span>

1. <span data-ttu-id="d78b6-142">在 Teams 管理中心中，展开 **"语音"，** 单击 **"自动助理"，** 然后单击"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="d78b6-142">In the Teams admin center, expand **Voice**, click **Auto attendants**, and then click **Add**.</span></span>

2. <span data-ttu-id="d78b6-143">在顶部的框中键入自动助理的名称。</span><span class="sxs-lookup"><span data-stu-id="d78b6-143">Type a name for the auto attendant in the box at the top.</span></span>

3. <span data-ttu-id="d78b6-144">如果要指定操作员，请指定调用操作员的目标。</span><span class="sxs-lookup"><span data-stu-id="d78b6-144">If you want to designate an operator, specify the destination for calls to the operator.</span></span> <span data-ttu-id="d78b6-145">这是可选的 (，但建议) 。</span><span class="sxs-lookup"><span data-stu-id="d78b6-145">This is optional (but recommended).</span></span> <span data-ttu-id="d78b6-146">你可以设置 **"接线员** "选项，允许呼叫者离开菜单，与指定人员通话。</span><span class="sxs-lookup"><span data-stu-id="d78b6-146">You can set the **Operator** option to allow callers to break out of the menus and speak to a designated person.</span></span>

4. <span data-ttu-id="d78b6-147">指定此自动助理的时区。</span><span class="sxs-lookup"><span data-stu-id="d78b6-147">Specify the time zone for this auto attendant.</span></span> <span data-ttu-id="d78b6-148">如果为营业时间创建单独的呼叫流，则时区用于计算营业时间。</span><span class="sxs-lookup"><span data-stu-id="d78b6-148">The time zone is used for calculating business hours if you create a separate call flow for after hours.</span></span>

5. <span data-ttu-id="d78b6-149">为此自动助理指定语言。</span><span class="sxs-lookup"><span data-stu-id="d78b6-149">Specify a language for this auto attendant.</span></span> <span data-ttu-id="d78b6-150">此语言将用于系统生成的语音提示。</span><span class="sxs-lookup"><span data-stu-id="d78b6-150">This the language that will be used for system-generated voice prompts.</span></span>

6. <span data-ttu-id="d78b6-151">选择是否要启用语音输入。</span><span class="sxs-lookup"><span data-stu-id="d78b6-151">Choose if you want to enable voice inputs.</span></span> <span data-ttu-id="d78b6-152">启用后，每个菜单选项的名称将成为语音识别关键字。</span><span class="sxs-lookup"><span data-stu-id="d78b6-152">When enabled, the name of every menu option becomes a speech-recognition keyword.</span></span> <span data-ttu-id="d78b6-153">例如，呼叫者可以说"一"来选择映射到键 1 的菜单选项，也可以说"销售"来选择名为"销售"的菜单选项。</span><span class="sxs-lookup"><span data-stu-id="d78b6-153">For example, callers can say "One" to select the menu option mapped to key 1, or they can say "Sales" to select the menu option named "Sales."</span></span>

    ![姓名、操作员、时区、语言和语音输入的自动助理设置的屏幕截图](../media/auto-attendant-general-info-page-new.png)

7. <span data-ttu-id="d78b6-155">单击" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="d78b6-155">Click **Next**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="d78b6-156">步骤 3 - 呼叫流></span><span class="sxs-lookup"><span data-stu-id="d78b6-156">Step 3 - Call flow ></span></span>](/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?tabs=call-flow#steps)

# <a name="step-3brcall-flow"></a>[<span data-ttu-id="d78b6-157">步骤 3 <br> 呼叫流</span><span class="sxs-lookup"><span data-stu-id="d78b6-157">Step 3<br>Call flow</span></span>](#tab/call-flow)

<span data-ttu-id="d78b6-158">选择呼叫流选项</span><span class="sxs-lookup"><span data-stu-id="d78b6-158">Choose your call flow options</span></span>

1. <span data-ttu-id="d78b6-159">选择当自动助理应答呼叫时是否要播放问候语。</span><span class="sxs-lookup"><span data-stu-id="d78b6-159">Choose if you want to play a greeting when the auto attendant answers a call.</span></span>

    <span data-ttu-id="d78b6-160">如果选择"**播放音频文件"，** 可以使用"上传文件"按钮上传在 中另存为音频的录制问候消息。WAV、 。MP3 或 。WMA 格式。</span><span class="sxs-lookup"><span data-stu-id="d78b6-160">If you select **Play an audio file** you can use the **Upload file** button to upload a recorded greeting message saved as audio in .WAV, .MP3, or .WMA format.</span></span> <span data-ttu-id="d78b6-161">录制内容不能大于 5 MB。</span><span class="sxs-lookup"><span data-stu-id="d78b6-161">The recording can be no larger than 5 MB.</span></span>

    <span data-ttu-id="d78b6-162">如果选择 **"键入** 问候消息"，系统将在自动助理应答呼叫时朗读你键入 (最多 1000 个字符) 文本。</span><span class="sxs-lookup"><span data-stu-id="d78b6-162">If you select **Type a greeting message** the system will read the text you the text that you type (up to 1000 characters) when the auto attendant answers a call.</span></span>

    ![问候消息设置的屏幕截图](../media/auto-attendant-call-flow-greeting-message.png)

2. <span data-ttu-id="d78b6-164">选择要如何路由呼叫。</span><span class="sxs-lookup"><span data-stu-id="d78b6-164">Choose how you want to route the call.</span></span>

    <span data-ttu-id="d78b6-165">如果选择" **断开连接"，** 自动助理将挂断呼叫。</span><span class="sxs-lookup"><span data-stu-id="d78b6-165">If you select **Disconnect**, the auto attendant will hang up the call.</span></span>

    <span data-ttu-id="d78b6-166">如果选择" **重定向呼叫"，** 可以选择其中一个呼叫路由目标。</span><span class="sxs-lookup"><span data-stu-id="d78b6-166">If you select **Redirect call**, you can choose one of the call routing destinations.</span></span>

    <span data-ttu-id="d78b6-167">如果选择"**播放菜单选项**"，可以选择"播放音频文件"或"键入问候语"，然后在菜单选项和目录搜索之间选择。</span><span class="sxs-lookup"><span data-stu-id="d78b6-167">If you select **Play menu options**, you can choose to **Play an audio file** or **Type in a greeting message** and then choose between menu options and directory search.</span></span>

    ![呼叫路由设置的屏幕截图](../media/auto-attendant-call-flow-route-call-message.png)

3. <span data-ttu-id="d78b6-169">如果希望呼叫者使用拨号键进行导航，那么在"设置菜单选项"下，选择当呼叫者按拨号键时要发生的情况。</span><span class="sxs-lookup"><span data-stu-id="d78b6-169">If you want callers to use dial keys to navigate, then under **Set menu options**, choose what you want to happen when callers press a dial key.</span></span> <span data-ttu-id="d78b6-170"> (如果要以公司目录创建此自动助理，请保留"拨号键"选项为空。) </span><span class="sxs-lookup"><span data-stu-id="d78b6-170">(If you're creating this auto attendant as a company directory, leave the dial key options blank.)</span></span>

    <span data-ttu-id="d78b6-171">可以将任何拨号键设置为以下目标：</span><span class="sxs-lookup"><span data-stu-id="d78b6-171">You can set any of the dial keys to the following destinations:</span></span>

    - <span data-ttu-id="d78b6-172">**组织中的人** - 组织中能够接收语音呼叫的人。</span><span class="sxs-lookup"><span data-stu-id="d78b6-172">**Person in the organization** - a person in your organization who is able to receive voice calls.</span></span>
    - <span data-ttu-id="d78b6-173">**语音应用** - 另一个自动助理或呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="d78b6-173">**Voice app** - another auto attendant or a call queue.</span></span>
    - <span data-ttu-id="d78b6-174">**外部电话号码** - 任何电话号码。</span><span class="sxs-lookup"><span data-stu-id="d78b6-174">**External phone number** - any phone number.</span></span> <span data-ttu-id="d78b6-175">使用此格式：+[国家/地区代码][区号][电话号码]</span><span class="sxs-lookup"><span data-stu-id="d78b6-175">Use this format: +[country code][area code][phone number]</span></span>
    - <span data-ttu-id="d78b6-176">**语音邮件** - 与指定的 Microsoft 365 组关联的语音邮箱。</span><span class="sxs-lookup"><span data-stu-id="d78b6-176">**Voicemail** - the voice mailbox associated with a Microsoft 365 group that you specify.</span></span>
    - <span data-ttu-id="d78b6-177">**接线** 员 - 为自动助理定义的操作员。</span><span class="sxs-lookup"><span data-stu-id="d78b6-177">**Operator** - the operator defined for the auto attendant.</span></span> <span data-ttu-id="d78b6-178">定义运算符是可选的。</span><span class="sxs-lookup"><span data-stu-id="d78b6-178">Defining an operator is optional.</span></span> <span data-ttu-id="d78b6-179">运算符可定义为此列表中的任何其他目标。</span><span class="sxs-lookup"><span data-stu-id="d78b6-179">The operator can be defined as any of the other destinations in this list.</span></span>

    <span data-ttu-id="d78b6-180">建议为运算符设置 0 个键。</span><span class="sxs-lookup"><span data-stu-id="d78b6-180">We recommend setting 0 key to the operator.</span></span>

    <span data-ttu-id="d78b6-181">对于每个菜单选项，请指定以下内容：</span><span class="sxs-lookup"><span data-stu-id="d78b6-181">For each menu option, specify the following:</span></span>

    - <span data-ttu-id="d78b6-182">**拨号键** - 电话键盘上的按键，用于访问此选项。</span><span class="sxs-lookup"><span data-stu-id="d78b6-182">**Dial key** - the key on the telephone keypad to access this option.</span></span>

    - <span data-ttu-id="d78b6-183">**语音** 命令 - 定义如果启用了语音输入，呼叫者可以授予用于访问此选项的语音命令。</span><span class="sxs-lookup"><span data-stu-id="d78b6-183">**Voice command** - defines the voice command that a caller can give to access this option, if voice inputs are enabled.</span></span> <span data-ttu-id="d78b6-184">它可以包含多个字词，例如"客户服务"或"运营与订单"。</span><span class="sxs-lookup"><span data-stu-id="d78b6-184">It can contain multiple words like "Customer Service" or "Operations and Grounds."</span></span> 

    - <span data-ttu-id="d78b6-185">**重定向到** - 当呼叫者选择此选项时希望呼叫转到的地方。</span><span class="sxs-lookup"><span data-stu-id="d78b6-185">**Redirect to** - where you want the call to go when callers choose this option.</span></span> <span data-ttu-id="d78b6-186">如果要重定向到自动助理或呼叫队列，请选择与其关联的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="d78b6-186">If you are redirecting to an auto attendant or call queue, choose the resource account associated with it.</span></span>

    ![拨号键选项的屏幕截图](../media/auto-attendant-call-flow-menu-options-complete.png)

4. <span data-ttu-id="d78b6-188">如果要使用此自动助理作为公司目录，请在"目录搜索"下，选择"**按名称拨号"。**</span><span class="sxs-lookup"><span data-stu-id="d78b6-188">If you want to use this auto attendant as a company directory, then under **Directory search**, select **Dial by name**.</span></span> <span data-ttu-id="d78b6-189">启用此选项后，呼叫者可以说出用户的姓名或在电话键盘上键入用户名。</span><span class="sxs-lookup"><span data-stu-id="d78b6-189">When you enable this option, callers can say the user's name or type it on the telephone keypad.</span></span> <span data-ttu-id="d78b6-190">任何具有电话系统许可证的联机用户都是符合条件的用户，可以使用"按姓名拨叫"找到。</span><span class="sxs-lookup"><span data-stu-id="d78b6-190">Any online user with a Phone System license is an eligible user and can be found with Dial by name.</span></span> 

    <span data-ttu-id="d78b6-191"> (可以选择" **按分机号码拨** 叫"，但必须在 Azure Active Directory.) </span><span class="sxs-lookup"><span data-stu-id="d78b6-191">(You can choose **Dial by extension**, however the extension must be configured in Azure Active Directory.)</span></span>

5. <span data-ttu-id="d78b6-192">选择目录 **搜索选项后**，单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="d78b6-192">Once you have selected a **Directory search** option, click **Next**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="d78b6-193">步骤 4 - 非工作时间呼叫流></span><span class="sxs-lookup"><span data-stu-id="d78b6-193">Step 4 - After hours call flow ></span></span>](/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?tabs=after-hours#steps)

# <a name="step-4brafter-hours"></a>[<span data-ttu-id="d78b6-194">步骤 4 <br> 小时之后</span><span class="sxs-lookup"><span data-stu-id="d78b6-194">Step 4<br>After hours</span></span>](#tab/after-hours)

<span data-ttu-id="d78b6-195">可以针对每个自动助理设置营业时间。</span><span class="sxs-lookup"><span data-stu-id="d78b6-195">Business hours can be set for each auto attendant.</span></span> <span data-ttu-id="d78b6-196">如果没有设置营业时间，所有日期以及每天的所有时间均视为营业时间，因为默认情况下设置为全天候时间表。</span><span class="sxs-lookup"><span data-stu-id="d78b6-196">If business hours aren't set, all days and all hours in the day are considered business hours because a 24/7 schedule is set by default.</span></span> <span data-ttu-id="d78b6-197">营业时间可以设置为一天中的休息时间，所有未设置为营业时间的营业时间均视为非营业时间。</span><span class="sxs-lookup"><span data-stu-id="d78b6-197">Business hours can be set with breaks in time during the day, and all of the hours that are not set as business hours are considered after-hours.</span></span> <span data-ttu-id="d78b6-198">您可以为非工作时间设置不同的传入呼叫处理选项和问候语。</span><span class="sxs-lookup"><span data-stu-id="d78b6-198">You can set different incoming call-handling options and greetings for after-hours.</span></span>

<span data-ttu-id="d78b6-199">根据自动助理和呼叫队列的配置方式，可能只需为具有直接电话号码的自动助理指定非工作时间呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="d78b6-199">Depending on how you have configured your auto attendants and call queues, you may only need to specify after-hours call routing for auto attendants with direct phone numbers.</span></span>

<span data-ttu-id="d78b6-200">如果希望为非工作时间呼叫者单独进行呼叫路由，请指定每天的营业时间。</span><span class="sxs-lookup"><span data-stu-id="d78b6-200">If you want separate call routing for after-hours callers, then specify your business hours for each day.</span></span> <span data-ttu-id="d78b6-201">例如 **，单击** "添加新时间"以指定给定一天的多个小时集，以指定午餐休息时间。</span><span class="sxs-lookup"><span data-stu-id="d78b6-201">Click **Add new time** to specify multiple sets of hours for a given day, for example, to specify a lunch break.</span></span>

!["工作时间"和"时间"设置的屏幕截图](../media/auto-attendant-business-hours.png)

<span data-ttu-id="d78b6-203">指定营业时间后，选择营业时间的呼叫路由选项。</span><span class="sxs-lookup"><span data-stu-id="d78b6-203">Once you have specified your business hours, then choose your call routing options for after hours.</span></span> <span data-ttu-id="d78b6-204">与在步骤 **3**- 呼叫流 中指定的营业时间呼叫路由相同。</span><span class="sxs-lookup"><span data-stu-id="d78b6-204">The same options are available as for the business hours call routing that you specified in **Step 3 - Call flow**.</span></span>

<span data-ttu-id="d78b6-205">完成后 **，** 单击"下一步"。</span><span class="sxs-lookup"><span data-stu-id="d78b6-205">Click **Next** when you're done.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="d78b6-206">步骤 5 - 假日呼叫流></span><span class="sxs-lookup"><span data-stu-id="d78b6-206">Step 5 - Holiday call flow ></span></span>](/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?tabs=holidays#steps)

# <a name="step-5brholidays"></a>[<span data-ttu-id="d78b6-207">步骤 5 <br> 假日</span><span class="sxs-lookup"><span data-stu-id="d78b6-207">Step 5<br>Holidays</span></span>](#tab/holidays)

<span data-ttu-id="d78b6-208">你可以让自动助理的呼叫在节假日的路由方式与其他日期不同。</span><span class="sxs-lookup"><span data-stu-id="d78b6-208">You can have calls to your auto attendant routed differently on holidays than on other days.</span></span> <span data-ttu-id="d78b6-209"> (如果不希望对假日使用不同的呼叫流，可以跳过此步骤。) </span><span class="sxs-lookup"><span data-stu-id="d78b6-209">(If you don't want to have a different call flow for holidays, you can skip this step.)</span></span>



<span data-ttu-id="d78b6-210">你的自动助理可以针对你设置的每个假日设置呼叫流。</span><span class="sxs-lookup"><span data-stu-id="d78b6-210">Your auto attendant can have a call flow for each holiday you've set up.</span></span> <span data-ttu-id="d78b6-211">可以为每个自动助理添加最多 20 个计划假日。</span><span class="sxs-lookup"><span data-stu-id="d78b6-211">You can add up to 20 scheduled holidays to each auto attendant.</span></span>

1. <span data-ttu-id="d78b6-212">在"假日呼叫设置"页上，单击"**添加"。**</span><span class="sxs-lookup"><span data-stu-id="d78b6-212">On the Holiday call settings page, click **Add**.</span></span>

2. <span data-ttu-id="d78b6-213">键入此假日设置的名称。</span><span class="sxs-lookup"><span data-stu-id="d78b6-213">Type a name for this holiday setting.</span></span>

3. <span data-ttu-id="d78b6-214">从 **"假日** "下拉列表中，选择想要使用的假日。</span><span class="sxs-lookup"><span data-stu-id="d78b6-214">From the **Holiday** dropdown, choose the holiday that you want to use.</span></span>

4. <span data-ttu-id="d78b6-215">选择想要使用的问候语类型。</span><span class="sxs-lookup"><span data-stu-id="d78b6-215">Choose the type of greeting that you want to use.</span></span>

    ![节日和节日问候设置的屏幕截图](../media/auto-attendant-holiday-greeting.png)

5. <span data-ttu-id="d78b6-217">选择是否要断开连接 **或\*\*\*\*重定向** 呼叫。</span><span class="sxs-lookup"><span data-stu-id="d78b6-217">Choose if you want to **Disconnect** or **Redirect** the call.</span></span>

6. <span data-ttu-id="d78b6-218">如果选择重定向，请选择呼叫的呼叫路由目标。</span><span class="sxs-lookup"><span data-stu-id="d78b6-218">If you chose to redirect, choose the call routing destination for the call.</span></span>

    ![假日通话操作设置的屏幕截图](../media/auto-attendant-holiday-actions.png)

7. <span data-ttu-id="d78b6-220">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="d78b6-220">Click **Save**.</span></span>

<span data-ttu-id="d78b6-221">根据需要对每个额外的假日重复该过程。</span><span class="sxs-lookup"><span data-stu-id="d78b6-221">Repeat the procedure as needed for each additional holiday.</span></span>

![假日设置的屏幕截图，其中列出了假日](../media/auto-attendant-holiday-call-settings.png)

<span data-ttu-id="d78b6-223">添加所有假日后，单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="d78b6-223">When you've added all your holidays, click **Next**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="d78b6-224">步骤 6 - 选择目录中></span><span class="sxs-lookup"><span data-stu-id="d78b6-224">Step 6 - Choose who's in the directory ></span></span>](/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?tabs=dial-scope#steps)

# <a name="step-6brdirectory-members"></a>[<span data-ttu-id="d78b6-225">步骤 6 <br> 目录成员</span><span class="sxs-lookup"><span data-stu-id="d78b6-225">Step 6<br>Directory members</span></span>](#tab/dial-scope)

<span data-ttu-id="d78b6-226">拨号 *范围* 定义当呼叫者使用按名称拨叫或按分机拨叫时，哪些用户在目录中可用。</span><span class="sxs-lookup"><span data-stu-id="d78b6-226">The *dial scope* defines which users are available in the directory when a caller uses dial-by-name or dial-by-extension.</span></span> <span data-ttu-id="d78b6-227">"所有 **联机用户"的** 默认值包括组织中具有电话系统许可证的联机用户的所有用户。</span><span class="sxs-lookup"><span data-stu-id="d78b6-227">The default of **All online users** includes all users in your organization that are Online users with a Phone System license.</span></span>

<span data-ttu-id="d78b6-228">可以通过在"包括"或"排除"下选择"自定义用户组"并选择一个或多个 Microsoft 365 组、通讯组列表或安全组来包括或排除特定用户。 </span><span class="sxs-lookup"><span data-stu-id="d78b6-228">You can include or exclude specific users by selecting **Custom user group** under **Include** or **Exclude** and choosing one or more Microsoft 365 groups, distribution lists, or security groups.</span></span> <span data-ttu-id="d78b6-229">例如，你可能希望从拨号目录中排除组织中高层。</span><span class="sxs-lookup"><span data-stu-id="d78b6-229">For example, you might want to exclude executives in your organization from the dialing directory.</span></span> <span data-ttu-id="d78b6-230"> (如果用户同时在两个列表中，则他们将被排除在 directory.) </span><span class="sxs-lookup"><span data-stu-id="d78b6-230">(If a user is in both lists, they will be excluded from the directory.)</span></span>

![拨号范围包括和排除选项的屏幕截图](../media/auto-attendant-dial-scope.png)

> [!NOTE]
> <span data-ttu-id="d78b6-232">新用户可能需要最多 36 小时才能在目录中列出其名称。</span><span class="sxs-lookup"><span data-stu-id="d78b6-232">It might take up to 36 hours for a new user to have their name listed in the directory.</span></span>

<span data-ttu-id="d78b6-233">设置完拨号范围后，单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="d78b6-233">When you're done setting the dial scope, click **Next**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="d78b6-234">步骤 7 - 分配资源帐户></span><span class="sxs-lookup"><span data-stu-id="d78b6-234">Step 7 - Assign a resource account ></span></span>](/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?tabs=resource-accounts#steps)

# <a name="step-7brresource-accounts"></a>[<span data-ttu-id="d78b6-235">步骤 7 <br> 资源帐户</span><span class="sxs-lookup"><span data-stu-id="d78b6-235">Step 7<br>Resource accounts</span></span>](#tab/resource-accounts)

<span data-ttu-id="d78b6-236">所有自动助理必须具有关联的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="d78b6-236">All auto attendants must have an associated resource account.</span></span>  <span data-ttu-id="d78b6-237">一级自动助理至少需要一个具有关联服务编号的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="d78b6-237">First level auto attendants will need at least one resource account that has an associated service number.</span></span> <span data-ttu-id="d78b6-238">如果需要，可以将多个资源帐户分配给自动助理，每个帐户都有单独的服务编号。</span><span class="sxs-lookup"><span data-stu-id="d78b6-238">If you wish, you can assign several resource accounts to an auto attendant, each with a separate service number.</span></span>

<span data-ttu-id="d78b6-239">添加资源帐户</span><span class="sxs-lookup"><span data-stu-id="d78b6-239">To add a resource account</span></span>

1. <span data-ttu-id="d78b6-240">单击 **"添加** 帐户"并搜索要添加的帐户。</span><span class="sxs-lookup"><span data-stu-id="d78b6-240">Click **Add account** and search for the account that you want to add.</span></span> <span data-ttu-id="d78b6-241">单击 **"添加**"，然后单击"**添加"。**</span><span class="sxs-lookup"><span data-stu-id="d78b6-241">Click **Add**, and then click **Add**.</span></span>

    ![资源帐户"添加帐户"面板的屏幕截图](../media/auto-attendant-add-resource-account.png)

2. <span data-ttu-id="d78b6-243">添加完服务帐户后，单击"提交 **"。**</span><span class="sxs-lookup"><span data-stu-id="d78b6-243">When you have finished adding service accounts, click **Submit**.</span></span>

    ![显示具有已分配服务编号的资源帐户列表的屏幕截图](../media/auto-attendant-resource-account-assigned.png)

<span data-ttu-id="d78b6-245">这会完成自动助理配置。</span><span class="sxs-lookup"><span data-stu-id="d78b6-245">This completes the auto attendant configuration.</span></span>

---


