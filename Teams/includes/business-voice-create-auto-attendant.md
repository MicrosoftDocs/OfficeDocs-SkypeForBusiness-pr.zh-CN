#### <a name="video-demonstration"></a><span data-ttu-id="6058e-101">视频演示</span><span class="sxs-lookup"><span data-stu-id="6058e-101">Video demonstration</span></span>

<span data-ttu-id="6058e-102">此视频演示了如何在 Teams 中创建自动助理的基本示例。</span><span class="sxs-lookup"><span data-stu-id="6058e-102">This video shows a basic example of how to create an auto attendant in Teams.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWEnCG?autoplay=false]

#### <a name="before-you-begin"></a><span data-ttu-id="6058e-103">开始之前</span><span class="sxs-lookup"><span data-stu-id="6058e-103">Before you begin</span></span>

<span data-ttu-id="6058e-104">获取服务号码 (服务号码是自动助理使用的特殊类型电话号码) 你需要自动助理通过直接拨号从组织外部访问这些号码。</span><span class="sxs-lookup"><span data-stu-id="6058e-104">Get the service numbers (service numbers are a special type of phone number that are used by auto attendants) that you need for the auto attendants that you want to be accessible by direct dialing from outside your organization.</span></span> <span data-ttu-id="6058e-105">这可能包括 [从另一个提供商转移号码](../phone-number-calling-plans/transfer-phone-numbers-to-teams.md) 或 [请求新的服务号码](../getting-service-phone-numbers.md)。</span><span class="sxs-lookup"><span data-stu-id="6058e-105">This might include [transferring numbers from another provider](../phone-number-calling-plans/transfer-phone-numbers-to-teams.md) or [requesting new service numbers](../getting-service-phone-numbers.md).</span></span>

<span data-ttu-id="6058e-106">需要为每个自动助理分配一个电话系统 - 虚拟用户许可证。</span><span class="sxs-lookup"><span data-stu-id="6058e-106">Each auto attendant needs to be assigned a Phone System - Virtual User license.</span></span> <span data-ttu-id="6058e-107">购买 Business Voice 时，还收到许多电话系统 - 虚拟用户许可证，因此可能不需要请求更多。</span><span class="sxs-lookup"><span data-stu-id="6058e-107">When you purchased Business Voice, you also received a number of Phone System - Virtual User licenses, so you probably don't need to request more.</span></span> <span data-ttu-id="6058e-108">但是，如果将来需要更多信息，可以按照 电话系统 - 虚拟用户许可证 中的说明获取[它们](../teams-add-on-licensing/virtual-user.md)。</span><span class="sxs-lookup"><span data-stu-id="6058e-108">However, if you need more in the future, you can get them by following the instructions in [Phone System - Virtual User license](../teams-add-on-licensing/virtual-user.md).</span></span>

<span data-ttu-id="6058e-109">如果要让自动助理在假日以不同方式路由呼叫，请创建想要使用的[](../set-up-holidays-in-teams.md)假日，然后再创建自动助理。</span><span class="sxs-lookup"><span data-stu-id="6058e-109">If you want to have your auto attendant route calls differently on holidays, then [create the holidays that you want to use](../set-up-holidays-in-teams.md) before you create the auto attendant.</span></span>

<a name="steps"></a>

#### <a name="follow-these-steps-to-set-up-your-auto-attendant"></a><span data-ttu-id="6058e-110">按照以下步骤设置自动助理</span><span class="sxs-lookup"><span data-stu-id="6058e-110">Follow these steps to set up your auto attendant</span></span>

# <a name="step-1brphone-number"></a>[<span data-ttu-id="6058e-111">步骤 1 <br> 电话编号</span><span class="sxs-lookup"><span data-stu-id="6058e-111">Step 1<br>Phone number</span></span>](#tab/phone-number)

> [!NOTE]
> <span data-ttu-id="6058e-112">如果你第一次按照步骤设置 Business Voice，并且你正在执行步骤 **6：** 为公司的主电话号码设置自动助理，则你已完成此选项卡上的步骤。移动到下一选项卡： [自动助理常规信息](?tabs=general-info#steps)。</span><span class="sxs-lookup"><span data-stu-id="6058e-112">If you're following the steps to set up Business Voice for the first time and you're on **Step 6: Set up an auto attendant for your company's main phone number**, you've already finished the steps on this tab. Move to the next tab: [Auto attendant general info](?tabs=general-info#steps).</span></span>

<span data-ttu-id="6058e-113">创建的每个自动助理都需要一个资源帐户。</span><span class="sxs-lookup"><span data-stu-id="6058e-113">Each auto attendant that you create requires a resource account.</span></span> <span data-ttu-id="6058e-114">这类似于用户帐户，但该帐户与自动助理或呼叫队列（而不是人员）相关联。</span><span class="sxs-lookup"><span data-stu-id="6058e-114">This is similar to a user account, except the account is associated with an auto attendant or call queue instead of a person.</span></span> <span data-ttu-id="6058e-115">在此步骤中，我们将创建帐户，为其分配Microsoft 365 电话系统 - 虚拟 *用户* 许可证，然后分配服务编号。</span><span class="sxs-lookup"><span data-stu-id="6058e-115">In this step, we'll create the account, assign it a *Microsoft 365 Phone System - Virtual User* license, and then assign a service number.</span></span>

### <a name="create-a-resource-account"></a><span data-ttu-id="6058e-116">创建资源帐户</span><span class="sxs-lookup"><span data-stu-id="6058e-116">Create a resource account</span></span>

<span data-ttu-id="6058e-117">可以在管理中心内创建Teams帐户。</span><span class="sxs-lookup"><span data-stu-id="6058e-117">You can create a resource account in the Teams admin center.</span></span>

1. <span data-ttu-id="6058e-118">在Teams管理中心，展开 **"组织范围的设置**"，然后单击"**资源帐户"。**</span><span class="sxs-lookup"><span data-stu-id="6058e-118">In the Teams admin center, expand **Org-wide settings**, and then click **Resource accounts**.</span></span>

2. <span data-ttu-id="6058e-119">单击“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="6058e-119">Click **Add**.</span></span>

3. <span data-ttu-id="6058e-120">在" **添加资源帐户"** 窗格中，填写" **显示** 名称"和" **用户名"，** 然后选择" **自动助理"** 作为"资源帐户 **类型"**</span><span class="sxs-lookup"><span data-stu-id="6058e-120">In the **Add resource account** pane, fill out **Display name**, **Username**, and choose **Auto attendant** for the **Resource account type**</span></span>

    ![添加资源帐户用户界面的屏幕截图](../media/resource-account-add.png)

4. <span data-ttu-id="6058e-122">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="6058e-122">Click **Save**.</span></span>

    <span data-ttu-id="6058e-123">新帐户将显示在帐户列表中。</span><span class="sxs-lookup"><span data-stu-id="6058e-123">The new account will appear in the list of accounts.</span></span>

    ![资源帐户列表的屏幕截图](../media/resource-accounts-page.png)

### <a name="assign-a-license"></a><span data-ttu-id="6058e-125">分配许可证</span><span class="sxs-lookup"><span data-stu-id="6058e-125">Assign a license</span></span>

<span data-ttu-id="6058e-126">必须为资源帐户 *Microsoft 365 电话系统 - 虚拟* 用户许可证。</span><span class="sxs-lookup"><span data-stu-id="6058e-126">You must assign a *Microsoft 365 Phone System - Virtual User* license to the resource account.</span></span>

1. <span data-ttu-id="6058e-127">在Microsoft 365管理中心，单击要为其分配许可证的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="6058e-127">In the Microsoft 365 admin center, click the resource account to which you want to assign a license.</span></span>

2. <span data-ttu-id="6058e-128">在"**许可证和应用"选项卡上的**"许可证 **"下**，选择 **"Microsoft 365 电话系统 - 虚拟用户"。**</span><span class="sxs-lookup"><span data-stu-id="6058e-128">On the **Licenses and Apps** tab, under **Licenses**, select **Microsoft 365 Phone System - Virtual User**.</span></span>

3. <span data-ttu-id="6058e-129">单击"**保存更改"。**</span><span class="sxs-lookup"><span data-stu-id="6058e-129">Click **Save changes**.</span></span>

    ![在管理中心内分配许可证Microsoft 365屏幕截图](../media/resource-account-assign-virtual-user-license.png)

### <a name="assign-a-service-number"></a><span data-ttu-id="6058e-131">分配服务编号</span><span class="sxs-lookup"><span data-stu-id="6058e-131">Assign a service number</span></span>

<span data-ttu-id="6058e-132">如果需要通过电话号码访问此自动助理，请将其分配给资源帐户。</span><span class="sxs-lookup"><span data-stu-id="6058e-132">If you need this auto attendant to be reachable by a phone number, then assign that number to the resource account.</span></span>

1. <span data-ttu-id="6058e-133">在Teams管理中心的"资源帐户"页上，选择要为其分配服务编号的资源帐户，然后单击"**分配/取消分配"。**</span><span class="sxs-lookup"><span data-stu-id="6058e-133">In the Teams admin center, on the **Resource accounts** page, select the resource account to which you want to assign a service number, and then click **Assign/unassign**.</span></span>

2. <span data-ttu-id="6058e-134">在 **电话类型**"下拉列表中，选择想要使用的编号类型。</span><span class="sxs-lookup"><span data-stu-id="6058e-134">In the **Phone number type** dropdown, choose the type of number that you want to use.</span></span>

3. <span data-ttu-id="6058e-135">在 **"分配的电话号码"** 框中，搜索想要使用的号码，然后单击"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="6058e-135">In the **Assigned phone number** box, search for the number you want to use and click **Add**.</span></span>

    ![分配服务编号用户界面的屏幕截图](../media/resource-account-assign-phone-number.png)

4. <span data-ttu-id="6058e-137">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="6058e-137">Click **Save**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="6058e-138">步骤 2 - 自动助理常规信息></span><span class="sxs-lookup"><span data-stu-id="6058e-138">Step 2 - Auto attendant general info ></span></span>](?tabs=general-info#steps)

# <a name="step-2brattendant-general-info"></a>[<span data-ttu-id="6058e-139">步骤 2 <br> Attendant 常规信息</span><span class="sxs-lookup"><span data-stu-id="6058e-139">Step 2<br>Attendant general info</span></span>](#tab/general-info)

<span data-ttu-id="6058e-140">设置自动助理</span><span class="sxs-lookup"><span data-stu-id="6058e-140">To set up an auto attendant</span></span>

1. <span data-ttu-id="6058e-141">在 Teams管理中心，展开 **"语音"，** 单击"**自动助理"，** 然后单击"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="6058e-141">In the Teams admin center, expand **Voice**, click **Auto attendants**, and then click **Add**.</span></span>

2. <span data-ttu-id="6058e-142">在顶部的框中键入自动助理的名称。</span><span class="sxs-lookup"><span data-stu-id="6058e-142">Type a name for the auto attendant in the box at the top.</span></span>

3. <span data-ttu-id="6058e-143">如果要指定操作员，请指定调用操作员的目标。</span><span class="sxs-lookup"><span data-stu-id="6058e-143">If you want to designate an operator, specify the destination for calls to the operator.</span></span> <span data-ttu-id="6058e-144">这是可选的 (，但建议) 。</span><span class="sxs-lookup"><span data-stu-id="6058e-144">This is optional (but recommended).</span></span> <span data-ttu-id="6058e-145">你可以设置 **"接线员** "选项，允许呼叫者离开菜单，与指定人员通话。</span><span class="sxs-lookup"><span data-stu-id="6058e-145">You can set the **Operator** option to allow callers to break out of the menus and speak to a designated person.</span></span>

4. <span data-ttu-id="6058e-146">指定此自动助理的时区。</span><span class="sxs-lookup"><span data-stu-id="6058e-146">Specify the time zone for this auto attendant.</span></span> <span data-ttu-id="6058e-147">如果为营业时间创建单独的呼叫流，则时区用于计算营业时间。</span><span class="sxs-lookup"><span data-stu-id="6058e-147">The time zone is used for calculating business hours if you create a separate call flow for after hours.</span></span>

5. <span data-ttu-id="6058e-148">为此自动助理指定语言。</span><span class="sxs-lookup"><span data-stu-id="6058e-148">Specify a language for this auto attendant.</span></span> <span data-ttu-id="6058e-149">这是将用于系统生成的语音提示的语言。</span><span class="sxs-lookup"><span data-stu-id="6058e-149">This is the language that will be used for system-generated voice prompts.</span></span>

6. <span data-ttu-id="6058e-150">选择是否要启用语音输入。</span><span class="sxs-lookup"><span data-stu-id="6058e-150">Choose if you want to enable voice inputs.</span></span> <span data-ttu-id="6058e-151">启用后，每个菜单选项的名称将成为语音识别关键字。</span><span class="sxs-lookup"><span data-stu-id="6058e-151">When enabled, the name of every menu option becomes a speech-recognition keyword.</span></span> <span data-ttu-id="6058e-152">例如，呼叫者可以说"一"来选择映射到键 1 的菜单选项，也可以说"销售"来选择名为"销售"的菜单选项。</span><span class="sxs-lookup"><span data-stu-id="6058e-152">For example, callers can say "One" to select the menu option mapped to key 1, or they can say "Sales" to select the menu option named "Sales."</span></span>

    ![姓名、操作员、时区、语言和语音输入的自动助理设置的屏幕截图](../media/auto-attendant-general-info-page-new.png)

7. <span data-ttu-id="6058e-154">单击" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="6058e-154">Click **Next**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="6058e-155">步骤 3 - 呼叫流></span><span class="sxs-lookup"><span data-stu-id="6058e-155">Step 3 - Call flow ></span></span>](?tabs=call-flow#steps)

# <a name="step-3brcall-flow"></a>[<span data-ttu-id="6058e-156">步骤 3 <br> 呼叫流</span><span class="sxs-lookup"><span data-stu-id="6058e-156">Step 3<br>Call flow</span></span>](#tab/call-flow)

<span data-ttu-id="6058e-157">选择呼叫流选项</span><span class="sxs-lookup"><span data-stu-id="6058e-157">Choose your call flow options</span></span>

1. <span data-ttu-id="6058e-158">选择当自动助理应答呼叫时是否要播放问候语。</span><span class="sxs-lookup"><span data-stu-id="6058e-158">Choose if you want to play a greeting when the auto attendant answers a call.</span></span>

    <span data-ttu-id="6058e-159">如果选择"**播放音频文件"，** 可以使用"Upload"按钮上传在 中另存为音频的录制问候消息。WAV、.MP3 或 。WMA 格式。</span><span class="sxs-lookup"><span data-stu-id="6058e-159">If you select **Play an audio file** you can use the **Upload file** button to upload a recorded greeting message saved as audio in .WAV, .MP3, or .WMA format.</span></span> <span data-ttu-id="6058e-160">录制内容不能大于 5 MB。</span><span class="sxs-lookup"><span data-stu-id="6058e-160">The recording can be no larger than 5 MB.</span></span>

    <span data-ttu-id="6058e-161">如果选择 **"键入** 问候消息"，系统将在自动助理应答呼叫时朗读你键入 (最多 1000 个字符) 文本。</span><span class="sxs-lookup"><span data-stu-id="6058e-161">If you select **Type a greeting message** the system will read the text you the text that you type (up to 1000 characters) when the auto attendant answers a call.</span></span>

    ![问候消息设置的屏幕截图](../media/auto-attendant-call-flow-greeting-message.png)

2. <span data-ttu-id="6058e-163">选择要如何路由呼叫。</span><span class="sxs-lookup"><span data-stu-id="6058e-163">Choose how you want to route the call.</span></span>

    <span data-ttu-id="6058e-164">如果选择" **断开连接"，** 自动助理将挂断呼叫。</span><span class="sxs-lookup"><span data-stu-id="6058e-164">If you select **Disconnect**, the auto attendant will hang up the call.</span></span>

    <span data-ttu-id="6058e-165">如果选择" **重定向呼叫"，** 可以选择其中一个呼叫路由目标。</span><span class="sxs-lookup"><span data-stu-id="6058e-165">If you select **Redirect call**, you can choose one of the call routing destinations.</span></span>

    <span data-ttu-id="6058e-166">如果选择"**播放菜单选项**"，可以选择"播放音频文件"或"键入问候语"，然后在菜单选项和目录搜索之间选择。</span><span class="sxs-lookup"><span data-stu-id="6058e-166">If you select **Play menu options**, you can choose to **Play an audio file** or **Type in a greeting message** and then choose between menu options and directory search.</span></span>

    ![呼叫路由设置的屏幕截图](../media/auto-attendant-call-flow-route-call-message.png)

3. <span data-ttu-id="6058e-168">如果希望呼叫者使用拨号键进行导航，那么在"设置菜单选项"下，选择当呼叫者按拨号键时要发生的情况。</span><span class="sxs-lookup"><span data-stu-id="6058e-168">If you want callers to use dial keys to navigate, then under **Set menu options**, choose what you want to happen when callers press a dial key.</span></span> <span data-ttu-id="6058e-169"> (如果要以公司目录创建此自动助理，请保留"拨号键"选项为空。) </span><span class="sxs-lookup"><span data-stu-id="6058e-169">(If you're creating this auto attendant as a company directory, leave the dial key options blank.)</span></span>

    <span data-ttu-id="6058e-170">可以将任何拨号键设置为以下目标：</span><span class="sxs-lookup"><span data-stu-id="6058e-170">You can set any of the dial keys to the following destinations:</span></span>

    - <span data-ttu-id="6058e-171">**组织中的人** - 组织中能够接收语音呼叫的人。</span><span class="sxs-lookup"><span data-stu-id="6058e-171">**Person in the organization** - a person in your organization who is able to receive voice calls.</span></span>
    - <span data-ttu-id="6058e-172">**语音应用** - 另一个自动助理或呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="6058e-172">**Voice app** - another auto attendant or a call queue.</span></span>
    - <span data-ttu-id="6058e-173">**外部电话号码** - 任何电话号码。</span><span class="sxs-lookup"><span data-stu-id="6058e-173">**External phone number** - any phone number.</span></span> <span data-ttu-id="6058e-174">使用此格式：+[国家/地区代码][区号][电话号码]</span><span class="sxs-lookup"><span data-stu-id="6058e-174">Use this format: +[country code][area code][phone number]</span></span>
    - <span data-ttu-id="6058e-175">**语音邮件**- 与指定的Microsoft 365关联的语音邮箱。</span><span class="sxs-lookup"><span data-stu-id="6058e-175">**Voicemail** - the voice mailbox associated with a Microsoft 365 group that you specify.</span></span>
    - <span data-ttu-id="6058e-176">**接线** 员 - 为自动助理定义的操作员。</span><span class="sxs-lookup"><span data-stu-id="6058e-176">**Operator** - the operator defined for the auto attendant.</span></span> <span data-ttu-id="6058e-177">定义运算符是可选的。</span><span class="sxs-lookup"><span data-stu-id="6058e-177">Defining an operator is optional.</span></span> <span data-ttu-id="6058e-178">运算符可定义为此列表中的任何其他目标。</span><span class="sxs-lookup"><span data-stu-id="6058e-178">The operator can be defined as any of the other destinations in this list.</span></span>

    <span data-ttu-id="6058e-179">建议为运算符设置 0 个键。</span><span class="sxs-lookup"><span data-stu-id="6058e-179">We recommend setting 0 key to the operator.</span></span>

    <span data-ttu-id="6058e-180">对于每个菜单选项，请指定以下内容：</span><span class="sxs-lookup"><span data-stu-id="6058e-180">For each menu option, specify the following:</span></span>

    - <span data-ttu-id="6058e-181">**拨号键** - 电话键盘上的按键，用于访问此选项。</span><span class="sxs-lookup"><span data-stu-id="6058e-181">**Dial key** - the key on the telephone keypad to access this option.</span></span>

    - <span data-ttu-id="6058e-182">**语音** 命令 - 定义如果启用了语音输入，呼叫者可以授予用于访问此选项的语音命令。</span><span class="sxs-lookup"><span data-stu-id="6058e-182">**Voice command** - defines the voice command that a caller can give to access this option, if voice inputs are enabled.</span></span> <span data-ttu-id="6058e-183">它可以包含多个字词，例如"客户服务"或"运营与订单"。</span><span class="sxs-lookup"><span data-stu-id="6058e-183">It can contain multiple words like "Customer Service" or "Operations and Grounds."</span></span> 

    - <span data-ttu-id="6058e-184">**重定向到** - 当呼叫者选择此选项时希望呼叫转到的地方。</span><span class="sxs-lookup"><span data-stu-id="6058e-184">**Redirect to** - where you want the call to go when callers choose this option.</span></span> <span data-ttu-id="6058e-185">如果要重定向到自动助理或呼叫队列，请选择与其关联的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="6058e-185">If you are redirecting to an auto attendant or call queue, choose the resource account associated with it.</span></span>

    ![拨号键选项的屏幕截图](../media/auto-attendant-call-flow-menu-options-complete.png)

4. <span data-ttu-id="6058e-187">如果要使用此自动助理作为公司目录，请在"目录搜索"下，选择"**按名称拨号"。**</span><span class="sxs-lookup"><span data-stu-id="6058e-187">If you want to use this auto attendant as a company directory, then under **Directory search**, select **Dial by name**.</span></span> <span data-ttu-id="6058e-188">启用此选项后，呼叫者可以说出用户的姓名或在电话键盘上键入用户名。</span><span class="sxs-lookup"><span data-stu-id="6058e-188">When you enable this option, callers can say the user's name or type it on the telephone keypad.</span></span> <span data-ttu-id="6058e-189">任何具有"按电话系统在线用户都是符合条件的用户，可以使用"按姓名拨叫"找到。</span><span class="sxs-lookup"><span data-stu-id="6058e-189">Any online user with a Phone System license is an eligible user and can be found with Dial by name.</span></span> 

    <span data-ttu-id="6058e-190"> (可以选择"按分机 **号码** 拨叫"，但是必须在 Azure Active Directory.) </span><span class="sxs-lookup"><span data-stu-id="6058e-190">(You can choose **Dial by extension**, however the extension must be configured in Azure Active Directory.)</span></span>

5. <span data-ttu-id="6058e-191">选择目录 **搜索选项后**，单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="6058e-191">Once you have selected a **Directory search** option, click **Next**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="6058e-192">步骤 4 - 非工作时间呼叫流></span><span class="sxs-lookup"><span data-stu-id="6058e-192">Step 4 - After hours call flow ></span></span>](?tabs=after-hours#steps)

# <a name="step-4brafter-hours"></a>[<span data-ttu-id="6058e-193">步骤 4 <br> 小时之后</span><span class="sxs-lookup"><span data-stu-id="6058e-193">Step 4<br>After hours</span></span>](#tab/after-hours)

<span data-ttu-id="6058e-194">可以针对每个自动助理设置营业时间。</span><span class="sxs-lookup"><span data-stu-id="6058e-194">Business hours can be set for each auto attendant.</span></span> <span data-ttu-id="6058e-195">如果没有设置营业时间，所有日期以及每天的所有时间均视为营业时间，因为默认情况下设置为全天候时间表。</span><span class="sxs-lookup"><span data-stu-id="6058e-195">If business hours aren't set, all days and all hours in the day are considered business hours because a 24/7 schedule is set by default.</span></span> <span data-ttu-id="6058e-196">营业时间可以设置为一天中的休息时间，所有未设置为营业时间的营业时间均视为非营业时间。</span><span class="sxs-lookup"><span data-stu-id="6058e-196">Business hours can be set with breaks in time during the day, and all of the hours that are not set as business hours are considered after-hours.</span></span> <span data-ttu-id="6058e-197">您可以为非工作时间设置不同的传入呼叫处理选项和问候语。</span><span class="sxs-lookup"><span data-stu-id="6058e-197">You can set different incoming call-handling options and greetings for after-hours.</span></span>

<span data-ttu-id="6058e-198">根据自动助理和呼叫队列的配置方式，可能只需为具有直接电话号码的自动助理指定非工作时间呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="6058e-198">Depending on how you have configured your auto attendants and call queues, you may only need to specify after-hours call routing for auto attendants with direct phone numbers.</span></span>

<span data-ttu-id="6058e-199">如果希望为非工作时间呼叫者单独进行呼叫路由，请指定每天的营业时间。</span><span class="sxs-lookup"><span data-stu-id="6058e-199">If you want separate call routing for after-hours callers, then specify your business hours for each day.</span></span> <span data-ttu-id="6058e-200">例如 **，单击** "添加新时间"以指定给定一天的多个小时集，以指定午餐休息时间。</span><span class="sxs-lookup"><span data-stu-id="6058e-200">Click **Add new time** to specify multiple sets of hours for a given day, for example, to specify a lunch break.</span></span>

!["工作时间"和"时间"设置的屏幕截图](../media/auto-attendant-business-hours.png)

<span data-ttu-id="6058e-202">指定营业时间后，选择营业时间的呼叫路由选项。</span><span class="sxs-lookup"><span data-stu-id="6058e-202">Once you have specified your business hours, then choose your call routing options for after hours.</span></span> <span data-ttu-id="6058e-203">与在步骤 **3**- 呼叫流 中指定的营业时间呼叫路由相同。</span><span class="sxs-lookup"><span data-stu-id="6058e-203">The same options are available as for the business hours call routing that you specified in **Step 3 - Call flow**.</span></span>

<span data-ttu-id="6058e-204">完成后 **，** 单击"下一步"。</span><span class="sxs-lookup"><span data-stu-id="6058e-204">Click **Next** when you're done.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="6058e-205">步骤 5 - 假日呼叫流></span><span class="sxs-lookup"><span data-stu-id="6058e-205">Step 5 - Holiday call flow ></span></span>](?tabs=holidays#steps)

# <a name="step-5brholidays"></a>[<span data-ttu-id="6058e-206">步骤 5 <br> 假日</span><span class="sxs-lookup"><span data-stu-id="6058e-206">Step 5<br>Holidays</span></span>](#tab/holidays)

<span data-ttu-id="6058e-207">你可以让自动助理的呼叫在节假日的路由方式与其他日期不同。</span><span class="sxs-lookup"><span data-stu-id="6058e-207">You can have calls to your auto attendant routed differently on holidays than on other days.</span></span> <span data-ttu-id="6058e-208"> (如果不希望对假日使用不同的呼叫流，可以跳过此步骤。) </span><span class="sxs-lookup"><span data-stu-id="6058e-208">(If you don't want to have a different call flow for holidays, you can skip this step.)</span></span>

<span data-ttu-id="6058e-209">你的自动助理可以针对你设置的每个假日设置呼叫流。</span><span class="sxs-lookup"><span data-stu-id="6058e-209">Your auto attendant can have a call flow for each holiday you've set up.</span></span> <span data-ttu-id="6058e-210">可以为每个自动助理添加最多 20 个计划假日。</span><span class="sxs-lookup"><span data-stu-id="6058e-210">You can add up to 20 scheduled holidays to each auto attendant.</span></span>

1. <span data-ttu-id="6058e-211">在"假日呼叫设置"页上，单击"**添加"。**</span><span class="sxs-lookup"><span data-stu-id="6058e-211">On the Holiday call settings page, click **Add**.</span></span>

2. <span data-ttu-id="6058e-212">键入此假日设置的名称。</span><span class="sxs-lookup"><span data-stu-id="6058e-212">Type a name for this holiday setting.</span></span>

3. <span data-ttu-id="6058e-213">从 **"假日** "下拉列表中，选择想要使用的假日。</span><span class="sxs-lookup"><span data-stu-id="6058e-213">From the **Holiday** dropdown, choose the holiday that you want to use.</span></span>

4. <span data-ttu-id="6058e-214">选择想要使用的问候语类型。</span><span class="sxs-lookup"><span data-stu-id="6058e-214">Choose the type of greeting that you want to use.</span></span>

    ![节日和节日问候设置的屏幕截图](../media/auto-attendant-holiday-greeting.png)

5. <span data-ttu-id="6058e-216">选择是否要断开连接 **或\*\*\*\*重定向** 呼叫。</span><span class="sxs-lookup"><span data-stu-id="6058e-216">Choose if you want to **Disconnect** or **Redirect** the call.</span></span>

6. <span data-ttu-id="6058e-217">如果选择重定向，请选择呼叫的呼叫路由目标。</span><span class="sxs-lookup"><span data-stu-id="6058e-217">If you chose to redirect, choose the call routing destination for the call.</span></span>

    ![假日通话操作设置的屏幕截图](../media/auto-attendant-holiday-actions.png)

7. <span data-ttu-id="6058e-219">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="6058e-219">Click **Save**.</span></span>

    <span data-ttu-id="6058e-220">根据需要对每个额外的假日重复该过程。</span><span class="sxs-lookup"><span data-stu-id="6058e-220">Repeat the procedure as needed for each additional holiday.</span></span>

    ![假日设置的屏幕截图，其中列出了假日](../media/auto-attendant-holiday-call-settings.png)

    <span data-ttu-id="6058e-222">添加所有假日后，单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="6058e-222">When you've added all your holidays, click **Next**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="6058e-223">步骤 6 - 选择目录中></span><span class="sxs-lookup"><span data-stu-id="6058e-223">Step 6 - Choose who's in the directory ></span></span>](?tabs=dial-scope#steps)

# <a name="step-6brdirectory-members"></a>[<span data-ttu-id="6058e-224">步骤 6 <br> 目录成员</span><span class="sxs-lookup"><span data-stu-id="6058e-224">Step 6<br>Directory members</span></span>](#tab/dial-scope)

<span data-ttu-id="6058e-225">拨号 *范围* 定义当呼叫者使用按名称拨叫或按分机拨叫时，哪些用户在目录中可用。</span><span class="sxs-lookup"><span data-stu-id="6058e-225">The *dial scope* defines which users are available in the directory when a caller uses dial-by-name or dial-by-extension.</span></span> <span data-ttu-id="6058e-226">"所有 **联机用户"的** 默认值包括组织中具有"联机"许可证的电话系统用户。</span><span class="sxs-lookup"><span data-stu-id="6058e-226">The default of **All online users** includes all users in your organization that are Online users with a Phone System license.</span></span>

<span data-ttu-id="6058e-227">可以通过在"包括"或"排除"下选择"自定义用户组"，并选择一个或多个组、通讯组列表Microsoft 365安全组，来包括或排除特定用户。 </span><span class="sxs-lookup"><span data-stu-id="6058e-227">You can include or exclude specific users by selecting **Custom user group** under **Include** or **Exclude** and choosing one or more Microsoft 365 groups, distribution lists, or security groups.</span></span> <span data-ttu-id="6058e-228">例如，你可能希望从拨号目录中排除组织中高层。</span><span class="sxs-lookup"><span data-stu-id="6058e-228">For example, you might want to exclude executives in your organization from the dialing directory.</span></span> <span data-ttu-id="6058e-229"> (如果用户同时在两个列表中，则他们将被排除在 directory.) </span><span class="sxs-lookup"><span data-stu-id="6058e-229">(If a user is in both lists, they will be excluded from the directory.)</span></span>

![拨号范围包括和排除选项的屏幕截图](../media/auto-attendant-dial-scope.png)

> [!NOTE]
> <span data-ttu-id="6058e-231">新用户可能需要最多 36 小时才能在目录中列出其名称。</span><span class="sxs-lookup"><span data-stu-id="6058e-231">It might take up to 36 hours for a new user to have their name listed in the directory.</span></span>

<span data-ttu-id="6058e-232">设置完拨号范围后，单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="6058e-232">When you're done setting the dial scope, click **Next**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="6058e-233">步骤 7 - 分配资源帐户></span><span class="sxs-lookup"><span data-stu-id="6058e-233">Step 7 - Assign a resource account ></span></span>](?tabs=resource-accounts#steps)

# <a name="step-7brresource-accounts"></a>[<span data-ttu-id="6058e-234">步骤 7 <br> 资源帐户</span><span class="sxs-lookup"><span data-stu-id="6058e-234">Step 7<br>Resource accounts</span></span>](#tab/resource-accounts)

<span data-ttu-id="6058e-235">所有自动助理必须具有关联的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="6058e-235">All auto attendants must have an associated resource account.</span></span>  <span data-ttu-id="6058e-236">一级自动助理至少需要一个具有关联服务编号的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="6058e-236">First level auto attendants will need at least one resource account that has an associated service number.</span></span> <span data-ttu-id="6058e-237">如果需要，可以将多个资源帐户分配给自动助理，每个帐户都有单独的服务编号。</span><span class="sxs-lookup"><span data-stu-id="6058e-237">If you wish, you can assign several resource accounts to an auto attendant, each with a separate service number.</span></span>

<span data-ttu-id="6058e-238">添加资源帐户</span><span class="sxs-lookup"><span data-stu-id="6058e-238">To add a resource account</span></span>

1. <span data-ttu-id="6058e-239">单击 **"** 添加"并搜索要添加的帐户。</span><span class="sxs-lookup"><span data-stu-id="6058e-239">Click **Add** and search for the account that you want to add.</span></span> <span data-ttu-id="6058e-240">单击 **"添加**"，然后单击"**添加"。**</span><span class="sxs-lookup"><span data-stu-id="6058e-240">Click **Add**, and then click **Add**.</span></span>

    ![资源帐户"添加帐户"面板的屏幕截图](../media/auto-attendant-add-resource-account.png)

2. <span data-ttu-id="6058e-242">添加完服务帐户后，单击"提交 **"。**</span><span class="sxs-lookup"><span data-stu-id="6058e-242">When you have finished adding service accounts, click **Submit**.</span></span>

    ![显示具有已分配服务编号的资源帐户列表的屏幕截图](../media/auto-attendant-resource-account-assigned.png)

    <span data-ttu-id="6058e-244">这会完成自动助理配置。</span><span class="sxs-lookup"><span data-stu-id="6058e-244">This completes the auto attendant configuration.</span></span>

---
