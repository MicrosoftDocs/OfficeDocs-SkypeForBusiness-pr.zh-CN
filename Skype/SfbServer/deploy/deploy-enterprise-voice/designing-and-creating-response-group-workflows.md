---
title: 在 Skype for Business 中设计和创建响应组工作流
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: dcb9effb-5d12-4dee-80fc-ab9654222d5a
description: 在 Skype for Business Server Enterprise Voice 中设计和创建响应组工作流。 包括智能寻线工作流和互动工作流。
ms.openlocfilehash: 9e056070bb01b5ee3cc7f32a8f9d07520fcb2030
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240523"
---
# <a name="designing-and-creating-response-group-workflows-in-skype-for-business"></a><span data-ttu-id="a04bf-104">在 Skype for Business 中设计和创建响应组工作流</span><span class="sxs-lookup"><span data-stu-id="a04bf-104">Designing and creating response group workflows in Skype for Business</span></span>

<span data-ttu-id="a04bf-105">在 Skype for Business Server Enterprise Voice 中设计和创建响应组工作流。</span><span class="sxs-lookup"><span data-stu-id="a04bf-105">Design and create Response Group workflows, in Skype for Business Server Enterprise Voice.</span></span> <span data-ttu-id="a04bf-106">包括智能寻线工作流和互动工作流。</span><span class="sxs-lookup"><span data-stu-id="a04bf-106">Both hunt group workflows and interactive workflows are covered.</span></span>

<span data-ttu-id="a04bf-107">工作流定义了从电话响铃到有人接听电话这段时间内呼叫的行为。</span><span class="sxs-lookup"><span data-stu-id="a04bf-107">A workflow defines the behavior of a call from the time that the phone rings to the time that someone answers the call.</span></span> <span data-ttu-id="a04bf-108">工作流指定用于保留呼叫的队列，并指定用于 智能寻线工作流的路由方法或用于 互动响应组工作流的问题和答案。</span><span class="sxs-lookup"><span data-stu-id="a04bf-108">The workflow specifies the queue to use for holding the call, and specifies the routing method to use for hunt group workflows or the questions and answers to use for interactive response group workflows.</span></span>

<span data-ttu-id="a04bf-109">工作流还定义了诸如欢迎消息、保持音乐、工作时间和假日等设置。</span><span class="sxs-lookup"><span data-stu-id="a04bf-109">A workflow also defines settings such as a welcome message, music on hold, business hours, and holidays.</span></span>

> [!NOTE]
> <span data-ttu-id="a04bf-110">必须先创建代理组和队列，然后再创建使用这些组和队列的工作流。</span><span class="sxs-lookup"><span data-stu-id="a04bf-110">You must create agent groups and queues before you create a workflow that uses them.</span></span>

## <a name="creating-or-modifying-a-hunt-group-workflow"></a><span data-ttu-id="a04bf-111">创建或修改查寻组工作流</span><span class="sxs-lookup"><span data-stu-id="a04bf-111">Creating or modifying a hunt group workflow</span></span>

### <a name="to-use-response-group-configuration-tool-to-create-or-modify-a-hunt-group-workflow"></a><span data-ttu-id="a04bf-112">使用 "响应组配置" 工具创建或修改查寻组工作流</span><span class="sxs-lookup"><span data-stu-id="a04bf-112">To use Response Group Configuration Tool to create or modify a hunt group workflow</span></span>

1. <span data-ttu-id="a04bf-113">以 RTCUniversalServerAdmins 组成员的身份，或支持响应组的某个预定义管理角色的成员身份登录。</span><span class="sxs-lookup"><span data-stu-id="a04bf-113">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2. <span data-ttu-id="a04bf-114">打开一个浏览器窗口, 然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。</span><span class="sxs-lookup"><span data-stu-id="a04bf-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="a04bf-115">在左侧导航栏中，单击“响应组”\*\*\*\*，然后单击“工作流”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a04bf-115">In the left navigation bar, click **Response Groups**, and then click **Workflow**.</span></span>

4. <span data-ttu-id="a04bf-116">在“工作流”\*\*\*\* 页上，单击“创建或编辑工作流”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a04bf-116">On the **Workflow** page, click **Create or edit a workflow**.</span></span>

5. <span data-ttu-id="a04bf-117">在“选择服务”\*\*\*\* 搜索字段中，键入承载您想要创建或修改的工作流的 **ApplicationServer** 服务的全部或部分名称。</span><span class="sxs-lookup"><span data-stu-id="a04bf-117">In the **Select a Service** search field, type all or part of the name of the **ApplicationServer** service that hosts the workflow that you want to create or change.</span></span> <span data-ttu-id="a04bf-118">在服务结果列表中，单击想要的服务，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a04bf-118">In the resulting list of services, click the service that you want, and then click **OK**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a04bf-119">此时将打开 "响应组配置" 工具。</span><span class="sxs-lookup"><span data-stu-id="a04bf-119">The Response Group Configuration Tool opens.</span></span> <span data-ttu-id="a04bf-120">您也可以通过键入以下 URL 直接从 web 浏览器打开 "响应组配置" 工具: https://\<webPoolFqdn\>/RgsConfig。</span><span class="sxs-lookup"><span data-stu-id="a04bf-120">You can also open the Response Group Configuration Tool directly from a web browser by typing the following URL: https://\<webPoolFqdn\>/RgsConfig.</span></span>

6. <span data-ttu-id="a04bf-121">请执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="a04bf-121">Do one of the following:</span></span>

   - <span data-ttu-id="a04bf-122">在 "新建**工作流**" 下的 "**查寻组**" 旁边, 单击 "**创建**"。</span><span class="sxs-lookup"><span data-stu-id="a04bf-122">Under **Create a New Workflow**, next to **Hunt Group**, click **Create**.</span></span>

   - <span data-ttu-id="a04bf-123">在“管理现有工作流”\*\*\*\* 下，找到想要更改的工作流，然后在“操作”\*\*\*\* 下单击“编辑”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a04bf-123">Under **Manage an Existing Workflow**, locate the workflow you want to change, and then under **Action**, click **Edit**.</span></span>

7. <span data-ttu-id="a04bf-124">如果已准备好让用户开始呼叫工作流，请选中“激活工作流”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a04bf-124">If you are ready for users to start calling the workflow, select **Activate the workflow**.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="a04bf-125">如果你要创建托管工作流, 你需要选择 "**激活工作流"**。</span><span class="sxs-lookup"><span data-stu-id="a04bf-125">If you are creating a managed workflow, you need to select **Activate the workflow**.</span></span> <span data-ttu-id="a04bf-126">在保存活动、受管理的工作流之后，则可以修改并停用该工作流。</span><span class="sxs-lookup"><span data-stu-id="a04bf-126">After you save the active, managed workflow, you can then modify and deactivate it.</span></span>

8. <span data-ttu-id="a04bf-127">要允许联盟用户呼叫组，请选中“启用联盟”\*\*\*\* 复选框。</span><span class="sxs-lookup"><span data-stu-id="a04bf-127">To allow federated users to call the group, select the **Enable for federation** check box.</span></span> <span data-ttu-id="a04bf-128">还必须具有适用于为联盟配置的响应组应用程序的外部访问策略。</span><span class="sxs-lookup"><span data-stu-id="a04bf-128">You must also have an external access policy that applies to the Response Group application configured for federation.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a04bf-129">全局外部访问策略适用于响应组应用程序。</span><span class="sxs-lookup"><span data-stu-id="a04bf-129">The global external access policy applies to the Response Group application.</span></span> <span data-ttu-id="a04bf-130">你可以使用 Skype for Business Server 控制面板或通过使用**CsExternalAccessPolicy** Cmdlet 将 EnableOutsideAccess 参数设置为 True, 为响应组联盟配置全局策略。</span><span class="sxs-lookup"><span data-stu-id="a04bf-130">You can configure the global policy for response group federation by using Skype for Business Server Control Panel or by using the **Set-CsExternalAccessPolicy** cmdlet to set the EnableOutsideAccess parameter to True.</span></span> <span data-ttu-id="a04bf-131">请记住，除非为全局策略设置分配站点或用户策略，否则这些设置适用于所有用户。</span><span class="sxs-lookup"><span data-stu-id="a04bf-131">Keep in mind that global policy settings apply to all users unless they are assigned a site or user policy.</span></span> <span data-ttu-id="a04bf-132">因此，在针对响应组更改此设置之前，请确保联盟设置满足您的组织的要求。</span><span class="sxs-lookup"><span data-stu-id="a04bf-132">Therefore, before changing this setting for response groups, make sure that the federation setting meets the requirements of your organization.</span></span> <span data-ttu-id="a04bf-133">有关策略如何适用于用户的详细信息，请参阅[Manage External Access Policy for Your Organization](https://technet.microsoft.com/library/5571811e-34c8-443a-b94c-1ab5d4275581.aspx)。</span><span class="sxs-lookup"><span data-stu-id="a04bf-133">For details about how policies apply to users, see [Manage External Access Policy for Your Organization](https://technet.microsoft.com/library/5571811e-34c8-443a-b94c-1ab5d4275581.aspx).</span></span> <span data-ttu-id="a04bf-134">有关联盟设置的详细信息, 请参阅[Set-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/set-csexternalaccesspolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="a04bf-134">For details about the federation setting, see [Set-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/set-csexternalaccesspolicy?view=skype-ps).</span></span>

    > [!NOTE]
    > <span data-ttu-id="a04bf-135">Skype for Business Online 中托管的用户不能将调用放到内部部署中托管的响应组。</span><span class="sxs-lookup"><span data-stu-id="a04bf-135">Users who are hosted in Skype for Business Online can't place calls to response groups that are hosted in an on-premises deployment.</span></span> <span data-ttu-id="a04bf-136">这在混合部署中以及内部部署与 Skype for Business Online 部署联合的情况下是如此。</span><span class="sxs-lookup"><span data-stu-id="a04bf-136">This is true in both hybrid deployments and in cases where an on-premises deployment is federated with a Skype for Business Online deployment.</span></span>

9. <span data-ttu-id="a04bf-137">要在呼叫过程中隐藏代理身份，请选中“启用代理匿名”\*\*\*\* 复选框。</span><span class="sxs-lookup"><span data-stu-id="a04bf-137">To hide the identity of agents during calls, select the **Enable agent anonymity** check box.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a04bf-p110">尽管建立呼叫后，代理或呼叫者可以添加即时消息 (IM) 和视频，但匿名呼叫无法启动 IM 或视频。匿名代理还可以将呼叫置于保持状态、转接呼叫（盲转接和咨询转接）、寄存和取回呼叫。匿名呼叫不支持会议、应用程序共享和桌面共享、文件传输、白板、数据协作和呼叫记录。使用 Lync VDI 插件的代理可以匿名方式接听来电，但他们无法以匿名方式拨出电话。</span><span class="sxs-lookup"><span data-stu-id="a04bf-p110">Anonymous calls cannot start with instant messaging (IM) or video, although the agent or the caller can add IM and video after the call is established. An anonymous agent can also put calls on hold, transfer calls (both blind and consultative transfers), and park and retrieve calls. Anonymous calls do not support conferencing, application sharing and desktop sharing, file transfer, whiteboarding and data collaboration, and call recording. Agents using the Lync VDI Plugin can receive incoming calls anonymously, but they cannot make outgoing calls anonymously.</span></span>

10. <span data-ttu-id="a04bf-142">在“输入将接收呼叫的组的地址”\*\*\*\* 下，键入将应答工作流呼叫的组的主 SIP 统一资源标识符 (URI) 地址。</span><span class="sxs-lookup"><span data-stu-id="a04bf-142">Under **Enter the address of the group that will receive the calls**, type the primary SIP uniform resource identifier (URI) address of the group that will answer calls to the workflow.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a04bf-143">工作流的主 URI 是标识和引用工作流的方式。</span><span class="sxs-lookup"><span data-stu-id="a04bf-143">The primary URI for a workflow is how the workflow is identified and referenced.</span></span> <span data-ttu-id="a04bf-144">您输入的 SIP URI 在 Active Directory 域服务中创建为联系人对象。</span><span class="sxs-lookup"><span data-stu-id="a04bf-144">The SIP URI that you enter is created as a contact object in Active Directory Domain Services.</span></span> <span data-ttu-id="a04bf-145">若要创建 URI, 对象在 Active Directory 中必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="a04bf-145">To create the URI, the object must be unique in Active Directory.</span></span>

11. <span data-ttu-id="a04bf-146">在 "**显示名称**" 中, 键入要为工作流显示的名称 (例如, "销售" 响应组)。</span><span class="sxs-lookup"><span data-stu-id="a04bf-146">In **Display name**, type the name that you want to display for the workflow (for example, Sales Response Group).</span></span>

    > [!NOTE]
    > <span data-ttu-id="a04bf-p112">不要在显示名称中包含“<”或“>”字符。不要使用以下保留的显示名称：“RGS Presence Watcher”\*\*\*\* 或“Announcement Service”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a04bf-p112">Do not include the "<" or ">" characters in the display name. Do not use the following display names because they are reserved: **RGS Presence Watcher** or **Announcement Service**.</span></span>

12. <span data-ttu-id="a04bf-149">在“电话号码”\*\*\*\* 下，键入响应组的线路 URI（例如，+14255550165）。</span><span class="sxs-lookup"><span data-stu-id="a04bf-149">Under **Telephone number**, type the line URI for the response group (for example, +14255550165).</span></span>

13. <span data-ttu-id="a04bf-150">在“显示号码”\*\*\*\* 下，键入希望显示的响应组号码（例如，+1 (425) 555-0165）。</span><span class="sxs-lookup"><span data-stu-id="a04bf-150">In **Display number**, type the number as you want it to appear for the response group (for example, +1 (425) 555-0165).</span></span>

14. <span data-ttu-id="a04bf-151">可选在 "**说明**" 中, 键入要在 Skype for business 的联系人卡片上显示的工作流的说明。</span><span class="sxs-lookup"><span data-stu-id="a04bf-151">(Optional) In **Description**, type a description for the workflow as you want it to appear on the contact card in Skype for Business.</span></span>

15. <span data-ttu-id="a04bf-152">如果此工作流将由响应组管理员管理，则在“工作流类型”\*\*\*\* 中选择“托管”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a04bf-152">In **Workflow Type**, select **Managed** if this workflow will be managed by a Response Group Manager.</span></span> <span data-ttu-id="a04bf-153">执行以下操作以将响应组管理器分配给工作流:</span><span class="sxs-lookup"><span data-stu-id="a04bf-153">Do the following to assign Response Group Managers to the workflow:</span></span>

    <span data-ttu-id="a04bf-154">a.</span><span class="sxs-lookup"><span data-stu-id="a04bf-154">a.</span></span> <span data-ttu-id="a04bf-155">键入此工作流的管理员的 SIP URI，单击“添加”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a04bf-155">Type the SIP URI of a manager for this workflow, and click **Add**.</span></span>

    <span data-ttu-id="a04bf-156">b.</span><span class="sxs-lookup"><span data-stu-id="a04bf-156">b.</span></span> <span data-ttu-id="a04bf-157">键入要添加到工作流的其他管理员的 SIP URI，单击“添加”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a04bf-157">Type the SIP URI of additional managers to add to the workflow, and click **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="a04bf-p116">必须为被指定为响应组管理员的每一位用户分配 CsResponseGroupManager 角色。如果没有为用户分配此角色，他们无法管理响应组。</span><span class="sxs-lookup"><span data-stu-id="a04bf-p116">Every user who is designated as a manager of a response group must be assigned the CsResponseGroupManager role. If users are not assigned this role, they cannot manage response groups.</span></span>

16. <span data-ttu-id="a04bf-160">在“步骤 2 选择语言”\*\*\*\* 下，单击要用于语音识别和文本到语音转换的语言。</span><span class="sxs-lookup"><span data-stu-id="a04bf-160">Under **Step 2 Select a Language**, click the language that you want to use for speech recognition and text-to-speech.</span></span>

17. <span data-ttu-id="a04bf-161">如果要配置欢迎消息，则在“步骤 3 配置欢迎消息”\*\*\*\* 下选中“播放欢迎消息”\*\*\*\* 复选框，然后执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="a04bf-161">If you want to configure a welcome message, under **Step 3 Configure a Welcome Message**, select the **Play a welcome message** check box, and then do one of the following:</span></span>

    - <span data-ttu-id="a04bf-162">要为呼叫者输入转换成语音的文本形式的欢迎消息，请单击“使用文本到语音转换”\*\*\*\*，然后在文本框中键入欢迎消息。</span><span class="sxs-lookup"><span data-stu-id="a04bf-162">To enter the welcome message as text that is converted to speech for callers, click **Use text-to-speech**, and then type the welcome message in the text box.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a04bf-163">不要在输入的文本中包含 HTML 标记。</span><span class="sxs-lookup"><span data-stu-id="a04bf-163">Do not include HTML tags in the text you enter.</span></span> <span data-ttu-id="a04bf-164">如果包含 HTML 标记, 则会收到一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="a04bf-164">If you include HTML tags, you will receive an error message.</span></span>

    - <span data-ttu-id="a04bf-p118">要使用 Wave (.wav) 或 Windows Media 音频 (.wma) 文件录音作为欢迎消息，请单击“选择录音”\*\*\*\*。如果要上载新的音频文件，请单击“录音”\*\*\*\* 链接。在新浏览器窗口中，单击“浏览”\*\*\*\*，选择要使用的音频文件，然后单击“打开”\*\*\*\*。单击“上载”\*\*\*\* 加载该音频文件。</span><span class="sxs-lookup"><span data-stu-id="a04bf-p118">To use a wave (.wav) or Windows Media audio (.wma) file recording for the welcome message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the audio file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a04bf-169">用户提供的所有音频文件都必须满足特定要求。</span><span class="sxs-lookup"><span data-stu-id="a04bf-169">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="a04bf-170">有关受支持的音频文件格式的详细信息，请参阅 [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx)。</span><span class="sxs-lookup"><span data-stu-id="a04bf-170">For details about supported file formats, see [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).</span></span>

18. <span data-ttu-id="a04bf-171">在“步骤 4 指定您的工作时间”\*\*\*\* 下的“您所在的时区”\*\*\*\* 中，单击工作流的时区。</span><span class="sxs-lookup"><span data-stu-id="a04bf-171">Under **Step 4 Specify Your Business Hours**, in **Your time zone**, click the time zone for the workflow.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a04bf-p120">该时区是工作流的呼叫者和代理所在的时区。它用于计算工作流开放和关闭的时间点。例如，如果将工作流配置为使用北美东部时间的时区，并安排工作流在上午 7:00 开放，晚上 11:00 关闭，则得出的开放和关闭时间点分别为东部时间 7:00 和东部时间 23:00。（必须以 24 小时制输入时间。）</span><span class="sxs-lookup"><span data-stu-id="a04bf-p120">The time zone is the time zone where the callers and agents of the workflow reside. It is used to calculate the open and close hours. For example, if the workflow is configured to use the North American Eastern Time zone and the workflow is scheduled to open at 7:00 A.M. and close at 11:00 P.M., the open and close times are assumed to be 7:00 Eastern Time and 23:00 Eastern Time respectively. (You must enter the times in 24-hour time notation.)</span></span>

19. <span data-ttu-id="a04bf-177">通过执行下列操作之一选择要使用的工作时间日程表类型：</span><span class="sxs-lookup"><span data-stu-id="a04bf-177">Select the type of business hours schedule you want to use by doing one of the following:</span></span>

    - <span data-ttu-id="a04bf-178">要使用预定义工作时间日程表，请单击“使用预设日程表”\*\*\*\*，然后从下拉列表中选择要使用的日程表。</span><span class="sxs-lookup"><span data-stu-id="a04bf-178">To use a predefined schedule of business hours, click **Use a preset schedule**, and then select the schedule you want to use from the drop-down list.</span></span>

      > [!NOTE]
      > <span data-ttu-id="a04bf-179">之前您必须至少已定义一个预设日程表才能选择该选项。</span><span class="sxs-lookup"><span data-stu-id="a04bf-179">You must have defined at least one preset schedule previously to be able to select this option.</span></span> <span data-ttu-id="a04bf-180">可使用  **New-CSRgsHoursOfBusiness** cmdlet 来定义预设日程表。</span><span class="sxs-lookup"><span data-stu-id="a04bf-180">You define preset schedules by using the **New-CSRgsHoursOfBusiness** cmdlet.</span></span> <span data-ttu-id="a04bf-181">有关详细信息, 请参阅[(可选) 在 Skype For business 中定义响应组工作时间](optional-define-response-group-business-hours.md)。</span><span class="sxs-lookup"><span data-stu-id="a04bf-181">For details, see [(Optional) Define Response Group business hours in Skype for Business](optional-define-response-group-business-hours.md).</span></span>

      > [!NOTE]
      > <span data-ttu-id="a04bf-182">选择预设日程表时，“天”\*\*\*\*、“开放”\*\*\*\* 和“关闭”\*\*\*\* 中会自动填写响应组可以应答的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="a04bf-182">When you select a preset schedule, **Day**, **Open**, and **Close** are automatically filled with the days and hours that the response group is available.</span></span>

    - <span data-ttu-id="a04bf-183">要使用仅适用于该工作流的自定义日程表，请单击“使用自定义日程表”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a04bf-183">To use a custom schedule that applies only to this workflow, click **Use a custom schedule**.</span></span>

20. <span data-ttu-id="a04bf-184">如果要创建该工作流的自定义日程表，请单击一周中响应组可以应答的日期对应的复选框。</span><span class="sxs-lookup"><span data-stu-id="a04bf-184">If you are creating a custom schedule for this workflow, click the check boxes for the days of the week that the response group is available.</span></span>

21. <span data-ttu-id="a04bf-185">如果要创建自定义计划, 请键入响应组可用的一周中的每一天的 "**打开**" 和 "**关闭**" 小时数。</span><span class="sxs-lookup"><span data-stu-id="a04bf-185">If you are creating a custom schedule, type the **Open** and **Close** hours for each day of the week that the response group is available.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a04bf-p122">“开放”\*\*\*\* 和“关闭”\*\*\*\* 时间点必须采用 24 小时制。例如，如果营业时间为朝九晚五，其中午餐时间不办公，则工作时间指定为 9:00“开放”\*\*\*\*、12:00“关闭”\*\*\*\*、13:00“开放”\*\*\*\* 及 17:00“关闭”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a04bf-p122">The **Open** and **Close** hours must be in 24-hour time notation. For example, if your office works a 9-to-5 work day and closes at noon for lunch, the business hours are specified as **Open** 9:00, **Close** 12:00, **Open** 13:00, and **Close** 17:00.</span></span>

22. <span data-ttu-id="a04bf-188">如果要在办公室未开放时播放消息，请选中“响应组在工作时间以外时播放消息”\*\*\*\* 复选框，然后通过执行以下操作之一指定要播放的消息：</span><span class="sxs-lookup"><span data-stu-id="a04bf-188">If you want to play a message when the office is not open, select the **Play a message when the response group is outside of business hours** check box, and then specify the message to play by doing one of the following:</span></span>

    - <span data-ttu-id="a04bf-189">要为呼叫者输入转换成语音的文本形式的消息，请单击“使用文本到语音转换”\*\*\*\*，然后在文本框中键入消息。</span><span class="sxs-lookup"><span data-stu-id="a04bf-189">To enter the message as text that is converted to speech for the caller, click **Use text-to-speech**, and then type the message in the text box.</span></span>

      > [!NOTE]
      > <span data-ttu-id="a04bf-190">不要在输入的文本中包含 HTML 标记。</span><span class="sxs-lookup"><span data-stu-id="a04bf-190">Do not include HTML tags in the text you enter.</span></span> <span data-ttu-id="a04bf-191">如果包含 HTML 标记, 则会收到一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="a04bf-191">If you include HTML tags, you will receive an error message.</span></span>

    - <span data-ttu-id="a04bf-p124">要使用音频文件录音作为消息，请单击“选择录音”\*\*\*\*。如果要上载新的音频文件，请单击“录音”\*\*\*\* 链接。在新浏览器窗口中，单击“浏览”\*\*\*\*，选择要使用的文件，然后单击“打开”\*\*\*\*。单击“上载”\*\*\*\*，加载该音频文件。</span><span class="sxs-lookup"><span data-stu-id="a04bf-p124">To use an audio file recording for the message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>

      > [!NOTE]
      > <span data-ttu-id="a04bf-p125">用户提供的所有音频文件都必须满足特定要求。有关受支持的音频文件格式的详细信息，请参阅 [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx)。</span><span class="sxs-lookup"><span data-stu-id="a04bf-p125">All user-provided audio files must meet certain requirements. For details about supported audio file formats, see [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).</span></span>

23. <span data-ttu-id="a04bf-198">指定播放消息后如何处理呼叫（如果配置了消息）：</span><span class="sxs-lookup"><span data-stu-id="a04bf-198">Specify how to handle calls after the message is played (if a message is configured):</span></span>

    - <span data-ttu-id="a04bf-199">要断开呼叫，请单击“断开呼叫”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a04bf-199">To disconnect the call, click **Disconnect Call**.</span></span>

    - <span data-ttu-id="a04bf-200">要将呼叫转接到语音邮件，请单击“转接到语音邮件”\*\*\*\*，然后键入语音邮件地址。</span><span class="sxs-lookup"><span data-stu-id="a04bf-200">To forward the call to voice mail, click **Forward to voice mail**, and then type the voice mail address.</span></span> <span data-ttu-id="a04bf-201">语音邮件地址的格式是\* \<用户名\>*@*\<域名\> \* (例如, bob@contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="a04bf-201">The format for the voice mail address is  *\<username\>*@*\<domainName\>* (for example, bob@contoso.com).</span></span>

    - <span data-ttu-id="a04bf-202">要将呼叫转接到另一个用户，请单击“转接到 SIP URI”\*\*\*\*，然后键入用户地址。</span><span class="sxs-lookup"><span data-stu-id="a04bf-202">To forward the call to another user, click **Forward to SIP URI**, and then type a user address.</span></span> <span data-ttu-id="a04bf-203">用户地址的格式是_ \<用户名\>_@_\<域名\>_。</span><span class="sxs-lookup"><span data-stu-id="a04bf-203">The format for the user address is  _\<username\>_@_\<domainName\>_.</span></span>

    - <span data-ttu-id="a04bf-204">要将呼叫转接到另一个电话号码，请单击“转接到电话号码”\*\*\*\*，然后键入该电话号码。</span><span class="sxs-lookup"><span data-stu-id="a04bf-204">To forward the call to another telephone number, click **Forward to telephone number**, and then type the telephone number.</span></span> <span data-ttu-id="a04bf-205">电话号码的格式为\* \<\>*@"*\<域名域名\> \* " (例如 + 14255550121@contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="a04bf-205">The format for the telephone number is  *\<number\>*@*\<domainName\>* (for example, +14255550121@contoso.com).</span></span> <span data-ttu-id="a04bf-206">域名可用来将呼叫者路由至正确的目标。</span><span class="sxs-lookup"><span data-stu-id="a04bf-206">The domain name is used to route the caller to the correct destination.</span></span>

24. <span data-ttu-id="a04bf-207">在“步骤 5 指定您的假日”\*\*\*\* 下，单击定义响应组停止营业日期的一个或多个假日集对应的复选框。</span><span class="sxs-lookup"><span data-stu-id="a04bf-207">Under **Step 5 Specify Your Holidays**, click the check boxes for one or more sets of holidays that define the days when the response group is closed for business.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a04bf-208">配置工作流之前，您需要先定义假日和假日集。</span><span class="sxs-lookup"><span data-stu-id="a04bf-208">You need to define holidays and holiday sets before you configure the workflow.</span></span> <span data-ttu-id="a04bf-209">使用 **New-CsRgsHoliday** 和 **New-CsRgsHolidaySet** cmdlet 可定义假日和假日集。</span><span class="sxs-lookup"><span data-stu-id="a04bf-209">Use the **New-CsRgsHoliday** and **New-CsRgsHolidaySet** cmdlets to define holidays and holiday sets.</span></span> <span data-ttu-id="a04bf-210">有关详细信息, 请参阅[(可选) 在 Skype For business 中定义 "响应组" 假日集](optional-define-response-group-holiday-sets.md)。</span><span class="sxs-lookup"><span data-stu-id="a04bf-210">For details, see [(Optional) Define Response Group holiday sets in Skype for Business](optional-define-response-group-holiday-sets.md).</span></span>

25. <span data-ttu-id="a04bf-211">如果要在假日播放消息，请选中“假期播放消息”\*\*\*\* 复选框，然后通过执行以下操作之一指定要播放的消息：</span><span class="sxs-lookup"><span data-stu-id="a04bf-211">If you want to play a message on holidays, select the **Play a message during holidays** check box, and then specify the message to play by doing one of the following:</span></span>

    - <span data-ttu-id="a04bf-212">要为呼叫者输入转换成语音的文本形式的消息，请单击“使用文本到语音转换”\*\*\*\*，然后在文本框中键入消息。</span><span class="sxs-lookup"><span data-stu-id="a04bf-212">To enter the message as text that is converted to speech for the caller, click **Use text-to-speech**, and then type the message in the text box.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a04bf-213">不要在输入的文本中包含 HTML 标记。</span><span class="sxs-lookup"><span data-stu-id="a04bf-213">Do not include HTML tags in the text you enter.</span></span> <span data-ttu-id="a04bf-214">如果包含 HTML 标记, 则会收到一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="a04bf-214">If you include HTML tags, you will receive an error message.</span></span>

    - <span data-ttu-id="a04bf-p131">要使用音频文件录音作为消息，请单击“选择录音”\*\*\*\*。如果要上载新的音频文件，请单击“录音”\*\*\*\* 链接。在新浏览器窗口中，单击“浏览”\*\*\*\*，选择要使用的文件，然后单击“打开”\*\*\*\*。单击“上载”\*\*\*\*，加载该音频文件。</span><span class="sxs-lookup"><span data-stu-id="a04bf-p131">To use an audio file recording for the message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>

      > [!NOTE]
      > <span data-ttu-id="a04bf-p132">用户提供的所有音频文件都必须满足特定要求。有关受支持的音频文件格式的详细信息，请参阅 [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx)。</span><span class="sxs-lookup"><span data-stu-id="a04bf-p132">All user-provided audio files must meet certain requirements. For details about supported audio file formats, see [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).</span></span>

26. <span data-ttu-id="a04bf-221">指定播放消息后如何处理呼叫（如果配置了消息）：</span><span class="sxs-lookup"><span data-stu-id="a04bf-221">Specify how to handle calls after the message is played (if a message is configured):</span></span>

    - <span data-ttu-id="a04bf-222">要断开呼叫，请单击“断开呼叫”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a04bf-222">To disconnect the call, click **Disconnect Call**.</span></span>

    - <span data-ttu-id="a04bf-223">要将呼叫转接到语音邮件，请单击“转接到语音邮件”\*\*\*\*，然后键入语音邮件地址。</span><span class="sxs-lookup"><span data-stu-id="a04bf-223">To forward the call to voice mail, click **Forward to voice mail**, and then type the voice mail address.</span></span> <span data-ttu-id="a04bf-224">语音邮件地址的格式是\* \<用户名\>*@*\<域名\> \* (例如, bob@contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="a04bf-224">The format for the voice mail address is  *\<username\>*@*\<domainName\>* (for example, bob@contoso.com).</span></span>

    - <span data-ttu-id="a04bf-225">要将呼叫转接到另一个用户，请单击“转接到 SIP URI”\*\*\*\*，然后键入用户地址。</span><span class="sxs-lookup"><span data-stu-id="a04bf-225">To forward the call to another user, click **Forward to SIP URI**, and then type a user address.</span></span> <span data-ttu-id="a04bf-226">用户地址的格式是_ \<用户名\>_@_\<域名\>_。</span><span class="sxs-lookup"><span data-stu-id="a04bf-226">The format for the user address is  _\<username\>_@_\<domainName\>_.</span></span>

    - <span data-ttu-id="a04bf-227">要将呼叫转接到另一个电话号码，请单击“转接到电话号码”\*\*\*\*，然后键入该电话号码。</span><span class="sxs-lookup"><span data-stu-id="a04bf-227">To forward the call to another telephone number, click **Forward to telephone number**, and then type the telephone number.</span></span> <span data-ttu-id="a04bf-228">电话号码的格式为\* \<\>*@"*\<域名域名\> \* " (例如 + 14255550121@contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="a04bf-228">The format for the telephone number is  *\<number\>*@*\<domainName\>* (for example, +14255550121@contoso.com).</span></span> <span data-ttu-id="a04bf-229">域名可用来将呼叫者路由至正确的目标。</span><span class="sxs-lookup"><span data-stu-id="a04bf-229">The domain name is used to route the caller to the correct destination.</span></span>

27. <span data-ttu-id="a04bf-230">在“步骤 6 配置队列”\*\*\*\* 下的“选择将接收呼叫的队列”\*\*\*\* 中，选择在出现可以应答的代理之前，使呼叫者处于保持状态的队列。</span><span class="sxs-lookup"><span data-stu-id="a04bf-230">Under **Step 6 Configure a Queue**, in **Select the queue that will receive the calls**, select the queue that you want to hold callers until an agent becomes available.</span></span>

28. <span data-ttu-id="a04bf-231">在“步骤 7 配置保持音乐”\*\*\*\* 下，执行以下操作之一，选择希望呼叫者在等待代理时听到的音乐：</span><span class="sxs-lookup"><span data-stu-id="a04bf-231">Under **Step 7 Configure Music on Hold**, choose the music you want callers to listen to while waiting for an agent by doing one of the following:</span></span>

    - <span data-ttu-id="a04bf-232">要使用默认录音作为保持音乐，请单击“使用默认值”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a04bf-232">To use the default music-on-hold recording, click **Use default**.</span></span>

    - <span data-ttu-id="a04bf-p136">要使用音频文件录音作为保持音乐，请单击“选择音乐文件”\*\*\*\*。如果要上载新的音频文件，请单击“音乐文件”\*\*\*\* 链接。在新浏览器窗口中，单击“浏览”\*\*\*\*，选择要使用的文件，然后单击“打开”\*\*\*\*。单击“上载”\*\*\*\*，加载该音频文件。</span><span class="sxs-lookup"><span data-stu-id="a04bf-p136">To use an audio file recording for the music on hold, click **Select a music file**. If you want to upload a new audio file, click the **a music file** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>

      > [!NOTE]
      > <span data-ttu-id="a04bf-p137">用户提供的所有音频文件都必须满足特定要求。有关受支持的音频文件格式的详细信息，请参阅 [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx)。</span><span class="sxs-lookup"><span data-stu-id="a04bf-p137">All user provided audio files must meet certain requirements. For details about supported audio file formats, see [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).</span></span>

29. <span data-ttu-id="a04bf-239">单击“部署”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a04bf-239">Click **Deploy**.</span></span>

### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-hunt-group-workflow"></a><span data-ttu-id="a04bf-240">使用 Skype for Business Server 命令行管理程序创建或修改查寻组工作流</span><span class="sxs-lookup"><span data-stu-id="a04bf-240">To use Skype for Business Server Management Shell to create or modify a hunt group workflow</span></span>

1. <span data-ttu-id="a04bf-241">以 RTCUniversalServerAdmins 组成员的身份，或支持响应组的某个预定义管理角色的成员身份登录。</span><span class="sxs-lookup"><span data-stu-id="a04bf-241">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2. <span data-ttu-id="a04bf-242">启动 Skype for Business Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\* 和“Skype for Business 2015”\*\*\*\*，然后单击“Skype for Business Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a04bf-242">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

3. <span data-ttu-id="a04bf-p138">为欢迎消息创建要播放的提示，然后将其保存在变量中。在命令行中运行：</span><span class="sxs-lookup"><span data-stu-id="a04bf-p138">Create the prompt to be played for the welcome message, and save it in a variable. At the command line, run:</span></span>

   ```
   $promptWM = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
   ```

    <span data-ttu-id="a04bf-245">例如：</span><span class="sxs-lookup"><span data-stu-id="a04bf-245">For example:</span></span>

   ```
   $promptWM = New-CsRgsPrompt -TextToSpeechPrompt "Welcome to Contoso. Please wait for an available agent."
   ```

     > [!NOTE]
     > <span data-ttu-id="a04bf-246">要针对提示使用音频文件，请使用 **Import-CsRgsAudioFile** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a04bf-246">To use an audio file for the prompt, use the **Import-CsRgsAudioFile** cmdlet.</span></span> <span data-ttu-id="a04bf-247">有关详细信息, 请参阅[导入-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="a04bf-247">For details, see [Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps).</span></span>

4. <span data-ttu-id="a04bf-248">获取将在其中定向呼叫的队列或问题的标识。</span><span class="sxs-lookup"><span data-stu-id="a04bf-248">Get the identity of the queue or question where the calls will be directed.</span></span> <span data-ttu-id="a04bf-249">在命令行中运行：</span><span class="sxs-lookup"><span data-stu-id="a04bf-249">At the command line, run:</span></span>

   ```
   $qid = (Get-CsRgsQueue -Name "Help Desk").Identity
   ```

    <span data-ttu-id="a04bf-250">有关创建队列的详细信息, 请参阅[CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/new-csrgsqueue?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="a04bf-250">For details about creating the queue, see [New-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/new-csrgsqueue?view=skype-ps).</span></span>

5. <span data-ttu-id="a04bf-p141">定义在工作时间打开工作流时要执行的默认操作，并将其保存在变量中。在命令行中运行：</span><span class="sxs-lookup"><span data-stu-id="a04bf-p141">Define the default action to be taken when a workflow is opened during business hours, and save it in a variable. At the command line, run:</span></span>

   ```
   $actionWM = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken> -QueueID $qid
   ```

    > [!NOTE]
    > <span data-ttu-id="a04bf-253">对于智能寻线工作流，默认操作必须将呼叫定向到队列。</span><span class="sxs-lookup"><span data-stu-id="a04bf-253">For hunt group workflows, the default action must direct the call to a queue.</span></span> <span data-ttu-id="a04bf-254">此参数是活动工作流所必需的。</span><span class="sxs-lookup"><span data-stu-id="a04bf-254">This parameter is required for active workflows.</span></span> <span data-ttu-id="a04bf-255">对于非活动工作流则不需要。</span><span class="sxs-lookup"><span data-stu-id="a04bf-255">It is not required for inactive workflows.</span></span>

    <span data-ttu-id="a04bf-256">例如：</span><span class="sxs-lookup"><span data-stu-id="a04bf-256">For example:</span></span>

   ```
   $actionWM = New-CsRgsCallAction -Prompt $promptWM -Action TransferToQueue -QueueID $qid.Identity
   ```

6. <span data-ttu-id="a04bf-257">如果要定义工作时间和假日，则需要在创建或修改工作流之前创建工作时间和假日。</span><span class="sxs-lookup"><span data-stu-id="a04bf-257">If you want to define business hours and holidays, you need to create them before you create or modify the workflow.</span></span> <span data-ttu-id="a04bf-258">有关详细信息, 请参阅[(可选) 在 skype For business 中定义响应组工作时间](optional-define-response-group-business-hours.md)和[(可选) 在 skype For business 中定义 "响应组" 假日集](optional-define-response-group-holiday-sets.md)。</span><span class="sxs-lookup"><span data-stu-id="a04bf-258">For details, see [(Optional) Define Response Group business hours in Skype for Business](optional-define-response-group-business-hours.md) and [(Optional) Define Response Group holiday sets in Skype for Business](optional-define-response-group-holiday-sets.md).</span></span>

7. <span data-ttu-id="a04bf-259">如果您希望在工作时间之外或在假日收到的呼叫带有提示，请使用  **New-CsRgsPrompt** cmdlet 定义该提示，并使用  **New-CsRgsCallAction** 定义要在提示后执行的操作。</span><span class="sxs-lookup"><span data-stu-id="a04bf-259">If you want to have prompts for calls that are received out of business hours or on holidays, use the **New-CsRgsPrompt** cmdlet to define the prompt, and use the **New-CsRgsCallAction** to define the action to be taken after the prompt.</span></span> <span data-ttu-id="a04bf-260">有关详细信息, 请参阅[CsRgsPrompt](https://docs.microsoft.com/powershell/module/skype/new-csrgsprompt?view=skype-ps)和[CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="a04bf-260">For details, see [New-CsRgsPrompt](https://docs.microsoft.com/powershell/module/skype/new-csrgsprompt?view=skype-ps) and [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps).</span></span>

8. <span data-ttu-id="a04bf-261">检索 Lync Server 响应组服务的服务名称, 并将其分配给变量。</span><span class="sxs-lookup"><span data-stu-id="a04bf-261">Retrieve the service name for the Lync Server Response Group service and assign it to a variable.</span></span> <span data-ttu-id="a04bf-262">在命令行中运行：</span><span class="sxs-lookup"><span data-stu-id="a04bf-262">At the command, run:</span></span>

   ```
   $serviceId = "service:" + (Get-CsService | ?{$_.Applications -like "*RGS*"}).ServiceId;
   ```

9. <span data-ttu-id="a04bf-263">创建或修改工作流。</span><span class="sxs-lookup"><span data-stu-id="a04bf-263">Create or modify the workflow.</span></span> <span data-ttu-id="a04bf-264">要创建工作流，请使用  **New-CsRgsWorkflow**。</span><span class="sxs-lookup"><span data-stu-id="a04bf-264">To create a workflow, use **New-CsRgsWorkflow**.</span></span> <span data-ttu-id="a04bf-265">要修改工作流，请使用  **Set-CsRgsWorkflow**。</span><span class="sxs-lookup"><span data-stu-id="a04bf-265">To modify a workflow, use **Set-CsRgsWorkflow**.</span></span> <span data-ttu-id="a04bf-266">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="a04bf-266">At the command line, type:</span></span>

   ```
   $workflowHG = New-CsRgsWorkflow -Parent <service ID for the Response Group service> -Name "<hunt group name>" [-Description "<hunt group description>"] -PrimaryUri "<SIP address for the workflow>" [-LineUri "<Phone number for the workflow>"] [-DisplayNumber "<Phone number displayed in Lync>"] [-Active <$true | $false>] [-Anonymous <$true | $false>] [-DefaultAction <variable from preceding step>] [-EnabledForFederation <$true | $false>] [-Managed <$true | $false>] [-ManagersByUri <SIP addresses for Response Group Managers who can manage the workflow>]
   ```

    <span data-ttu-id="a04bf-267">例如：</span><span class="sxs-lookup"><span data-stu-id="a04bf-267">For example:</span></span>

   ```
   $workflowHG = New-CsRgsWorkflow -Parent $serviceID -Name "Human Resources" -Description "Human Resources workflow" -PrimaryUri "sip:humanresources@contoso.com" -LineUri "TEL:+14255551219" -DisplayNumber "555-1219" -Active $true -Anonymous $true -DefaultAction $actionWM -EnabledForFederation $false -Managed $true -ManagersByUri "sip:bob@contoso.com", "mindy@contoso.com"
   ```

     > [!IMPORTANT]
     > <span data-ttu-id="a04bf-268">必须为所有指定为工作流管理员的用户分配 CsResponseGroupManager 角色。</span><span class="sxs-lookup"><span data-stu-id="a04bf-268">All users who are designated managers for workflows must be assigned the CsResponseGroupManager role.</span></span>

     > [!NOTE]
     > <span data-ttu-id="a04bf-269">有关其他可选参数的详细信息, 请参阅[CsRgsWorkflow](https://docs.microsoft.com/powershell/module/skype/new-csrgsworkflow?view=skype-ps)或[Set-CsRgsWorkflow](https://docs.microsoft.com/powershell/module/skype/set-csrgsworkflow?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="a04bf-269">For details about additional optional parameters, see [New-CsRgsWorkflow](https://docs.microsoft.com/powershell/module/skype/new-csrgsworkflow?view=skype-ps) or [Set-CsRgsWorkflow](https://docs.microsoft.com/powershell/module/skype/set-csrgsworkflow?view=skype-ps)</span></span>

## <a name="designing-an-interactive-workflow"></a><span data-ttu-id="a04bf-270">设计互动工作流</span><span class="sxs-lookup"><span data-stu-id="a04bf-270">Designing an interactive workflow</span></span>

<span data-ttu-id="a04bf-271">使用互动语音响应 (IVR) 可从呼叫者获取信息，并将呼叫引导到相应的队列。</span><span class="sxs-lookup"><span data-stu-id="a04bf-271">You can use interactive voice response (IVR) to obtain information from callers and direct the call to the appropriate queue.</span></span> <span data-ttu-id="a04bf-272">问题/答案对确定要使用哪个队列。</span><span class="sxs-lookup"><span data-stu-id="a04bf-272">Question-and-answer pairs determine which queue to use.</span></span> <span data-ttu-id="a04bf-273">根据呼叫者的响应, 呼叫者可以听到后续问题, 或者路由到相应的队列。</span><span class="sxs-lookup"><span data-stu-id="a04bf-273">Depending on the caller's response, the caller either hears a follow-up question, or is routed to the appropriate queue.</span></span> <span data-ttu-id="a04bf-274">IVR 问题和呼叫者的答复将提供给接受呼叫的响应代理, 向该代理提供有价值的信息。</span><span class="sxs-lookup"><span data-stu-id="a04bf-274">The IVR questions and the caller's responses are provided to the responding agent who accepts the call, providing valuable information to the agent.</span></span>

### <a name="overview-of-ivr-features"></a><span data-ttu-id="a04bf-275">IVR 功能概述</span><span class="sxs-lookup"><span data-stu-id="a04bf-275">Overview of IVR Features</span></span>

<span data-ttu-id="a04bf-276">响应组应用程序提供了在26种语言中的语音识别和文本到语音功能。</span><span class="sxs-lookup"><span data-stu-id="a04bf-276">The Response Group application offers speech recognition and text-to-speech capabilities in 26 languages.</span></span> <span data-ttu-id="a04bf-277">可以使用文本到语音转换功能或 Wave (.wav) 或 Windows Media 音频 (.wma) 文件输入 IVR 问题。</span><span class="sxs-lookup"><span data-stu-id="a04bf-277">You can enter IVR questions using text-to-speech or a wave (.wav) or Windows Media audio (.wma) file.</span></span> <span data-ttu-id="a04bf-278">呼叫者可以使用语音或双音多频 (DTMF) 响应进行响应。</span><span class="sxs-lookup"><span data-stu-id="a04bf-278">Callers can respond by using voice or dual-tone multifrequency (DTMF) responses.</span></span>

<span data-ttu-id="a04bf-279">互动工作流最多支持两级问题，每个问题最多有四个可能的答案。</span><span class="sxs-lookup"><span data-stu-id="a04bf-279">Interactive workflows support up to two levels of questions, with each question having up to four possible answers.</span></span> <span data-ttu-id="a04bf-280">IVR 将询问呼叫者一个问题, 具体取决于呼叫者的响应、将呼叫者路由到队列或提出第二个问题。</span><span class="sxs-lookup"><span data-stu-id="a04bf-280">The IVR asks the caller a question, and depending on the caller's response, routes the caller to a queue or asks a second question.</span></span> <span data-ttu-id="a04bf-281">第二个问题也可以有四个可能的答案。</span><span class="sxs-lookup"><span data-stu-id="a04bf-281">The second question can also have four possible answers.</span></span> <span data-ttu-id="a04bf-282">根据呼叫者对第二级问题的回答，将呼叫者路由至相应的队列。</span><span class="sxs-lookup"><span data-stu-id="a04bf-282">Depending on the answer to the second-level question, the caller is routed to the appropriate queue.</span></span>

> [!NOTE]
> <span data-ttu-id="a04bf-283">使用 Skype for Business Server Management Shell 设计通话流时, 可以定义任意数量的 IVR 问题和任意数量的答案。</span><span class="sxs-lookup"><span data-stu-id="a04bf-283">When you design call flows by using Skype for Business Server Management Shell, you can define any number of levels of IVR questions and any number of answers.</span></span> <span data-ttu-id="a04bf-284">但是，为了方便呼叫者使用，建议不要使用三个级别以上的问题，并且每个问题的答案不要超过五个。</span><span class="sxs-lookup"><span data-stu-id="a04bf-284">However, for caller usability, we recommend that you not use more than three levels of questions, with not more than five answers each.</span></span> <span data-ttu-id="a04bf-285">此外, 如果你设计的通话流程的两个级别的问题超过四个级别, 则不能使用 Skype for Business Server 控制面板编辑通话流。</span><span class="sxs-lookup"><span data-stu-id="a04bf-285">In addition, if you design a call flow that has more than two levels of questions with more than four answers each, you cannot edit the call flow by using Skype for Business Server Control Panel.</span></span>

<span data-ttu-id="a04bf-286">IVR 问题和呼叫者的答复将提供给接受呼叫的响应代理。</span><span class="sxs-lookup"><span data-stu-id="a04bf-286">The IVR questions and the caller's responses are provided to the responding agent who accepts the call.</span></span>

### <a name="working-with-speech-technologies"></a><span data-ttu-id="a04bf-287">使用语音技术</span><span class="sxs-lookup"><span data-stu-id="a04bf-287">Working with Speech Technologies</span></span>

<span data-ttu-id="a04bf-p151">语音识别和文本到语音转换等语音技术可以增强用户体验，并使用户能够更自然和更有效地获得信息。但是，语音引擎在有些情况下无法正确识别所指定的文本或用户语音响应。例如，文本到语音转换引擎会将“#”符号转换为“编号”这个词。通过以下方式可以缓解这一问题：</span><span class="sxs-lookup"><span data-stu-id="a04bf-p151">Speech technologies, such as speech recognition and text-to-speech, can enhance customer experience and let people access information more naturally and effectively. However, there can be cases where the specified text or the user voice response is not recognized correctly by the speech engine. For example, the "#" symbol is translated by the text-to-speech engine as the word "number." This issue can be mitigated by the following:</span></span>

- <span data-ttu-id="a04bf-p152">语音引擎让呼叫者尝试回答问题五次。如果呼叫者回答问题有误（即答案不是所指定的响应之一）或根本未提供答案，则呼叫者将再获得一次回答问题的机会。呼叫者有五次机会来回答问题，然后才会被挂断。可以将 IVR 配置为呼叫者每次出错后播放自定义消息。每次都将重复该问题。</span><span class="sxs-lookup"><span data-stu-id="a04bf-p152">The speech engine gives the caller five attempts to answer the question. If the caller answers the question incorrectly (that is, the answer is not one of the specified responses) or does not provide an answer at all, the caller gets another chance to answer the question. The caller has five attempts to answer the question before being disconnected. You can configure the IVR to play a customized message after each caller error. The question is repeated each time.</span></span>

- <span data-ttu-id="a04bf-p153">为了尽量避免语音引擎将环境噪声识别为响应，请使用长一点的响应。例如，响应应包含多个音节，并且不同响应之间应有明显的发音区别。</span><span class="sxs-lookup"><span data-stu-id="a04bf-p153">To minimize the potential for ambient noise to be interpreted by the speech engine as a response, use longer responses. For example, responses should have more than one syllable and should sound significantly different from each other.</span></span>

- <span data-ttu-id="a04bf-p154">如果问题同时包括语音和 DTMF 响应，请将语音响应配置为表示具体概念的语句，而不是 DTMF 响应。例如，不要使用“请按或说 1”，而应使用“请按 1 或说出帐单”。</span><span class="sxs-lookup"><span data-stu-id="a04bf-p154">If your questions have both speech and DTMF responses, configure the speech responses with words that represent the concept rather than the DTMF response. For example, instead of using "Press or say one" use "Press 1 or say billing."</span></span>

- <span data-ttu-id="a04bf-p155">设计 IVR 之后，请呼叫工作流、收听提示、使用语音对每个提示做出响应，并确认 IVR 的声音和行为符合预期。然后，可以修改 IVR 以更正任何释读问题。在前一个示例中，如果需要指代 # 键，则可以重新编写 IVR 提示，使用键名代替 # 符号。例如，“要与销售人员交谈，请按井号键”。</span><span class="sxs-lookup"><span data-stu-id="a04bf-p155">After you design your IVR, call the workflow, listen to the prompts, respond to each of the prompts using voice, and verify that the IVR sounds and behaves as expected. You can then modify the IVR to fix any interpretation issues. Following the previous example, if you need to refer to the # key, you can rewrite your IVR prompt to use the key name, rather than the # symbol. For example, "To talk to sales, press the pound key."</span></span>

### <a name="ivr-design-examples"></a><span data-ttu-id="a04bf-305">IVR 设计示例</span><span class="sxs-lookup"><span data-stu-id="a04bf-305">IVR Design Examples</span></span>

<span data-ttu-id="a04bf-306">以下各节包含不同 IVR 方案和问题/答案对的示例。</span><span class="sxs-lookup"><span data-stu-id="a04bf-306">The following sections contain examples of different IVR scenarios and question-and-answer pairs.</span></span>

#### <a name="ivr-with-one-level-of-questions"></a><span data-ttu-id="a04bf-307">只有单级问题的 IVR</span><span class="sxs-lookup"><span data-stu-id="a04bf-307">IVR with One Level of Questions</span></span>

<span data-ttu-id="a04bf-308">下例介绍使用单级问题的 IVR。</span><span class="sxs-lookup"><span data-stu-id="a04bf-308">The following example shows an IVR that uses one level of questions.</span></span> <span data-ttu-id="a04bf-309">它使用语音识别检测呼叫方的响应。</span><span class="sxs-lookup"><span data-stu-id="a04bf-309">It uses speech recognition to detect the caller's response.</span></span>

 <span data-ttu-id="a04bf-p157">**问题：**“感谢您致电人力资源部。如果要与薪酬组通话，请说‘薪酬’。否则，请说‘人力资源’。”</span><span class="sxs-lookup"><span data-stu-id="a04bf-p157">**Question:** "Thank you for calling Human Resources. If you would like to speak to payroll, say payroll. Otherwise, say HR."</span></span>

- <span data-ttu-id="a04bf-313">**选择选项 1：** 将呼叫者路由至薪酬组。</span><span class="sxs-lookup"><span data-stu-id="a04bf-313">**Option 1 is selected:** The caller is routed to the payroll team.</span></span>

- <span data-ttu-id="a04bf-314">**选择选项 2：** 将呼叫者路由至人力资源组。</span><span class="sxs-lookup"><span data-stu-id="a04bf-314">**Option 2 is selected:** The caller is routed to the human resources team.</span></span>

<span data-ttu-id="a04bf-315">下图显示了相应的呼叫流。</span><span class="sxs-lookup"><span data-stu-id="a04bf-315">The following figure shows the call flow.</span></span>

 <span data-ttu-id="a04bf-316">**单级互动呼叫流**</span><span class="sxs-lookup"><span data-stu-id="a04bf-316">**One-level interactive call flow**</span></span>

![使用互动语音响应设计呼叫流](../../media/Ops_OCS_RGS_IVRLevel1.jpg)

#### <a name="ivr-with-two-levels-of-questions"></a><span data-ttu-id="a04bf-318">含有两级问题的 IVR</span><span class="sxs-lookup"><span data-stu-id="a04bf-318">IVR with Two Levels of Questions</span></span>

<span data-ttu-id="a04bf-p158">下例介绍使用两级问题的 IVR。该 IVR 允许呼叫者使用语音或 DTMF 小键盘输入进行响应。</span><span class="sxs-lookup"><span data-stu-id="a04bf-p158">The following example shows an IVR that uses two levels of questions. It allows callers to respond using either speech or DTMF keypad input.</span></span>

 <span data-ttu-id="a04bf-p159">**问题：**“感谢您致电 IT 技术支持。如果有网络访问问题，请按 1 或说网络。如果有软件问题，则按 2 或说软件。如果有硬件问题，则按 3 或说硬件。”</span><span class="sxs-lookup"><span data-stu-id="a04bf-p159">**Question:** "Thank you for calling the IT Help Desk. If you have a network access problem, press 1 or say network. If you have a software problem, press 2 or say software. If you have a hardware problem, press 3 or say hardware."</span></span>

- <span data-ttu-id="a04bf-325">**选择选项 1：** 将呼叫者路由至网络支持组。</span><span class="sxs-lookup"><span data-stu-id="a04bf-325">**Option 1 is selected:** The caller is routed to the network support team.</span></span>

- <span data-ttu-id="a04bf-326">**选择选项 2：** 向呼叫者提出后续问题：</span><span class="sxs-lookup"><span data-stu-id="a04bf-326">**Option 2 is selected:** The caller is asked a follow-up question:</span></span>

    <span data-ttu-id="a04bf-p160">**问题：**“如果是操作系统的问题，请按 1 或说操作系统。如果是内部应用程序的问题，请按 2 或说内部应用程序。否则，请按 3 或说其他。”</span><span class="sxs-lookup"><span data-stu-id="a04bf-p160">**Question:** "If this is an operating system problem, press 1 or say operating system. If this is a problem with an internal application, press 2 or say internal application. Otherwise, press 3 or say other."</span></span>

  - <span data-ttu-id="a04bf-330">**选择选项 1：** 将呼叫者路由至操作系统支持组。</span><span class="sxs-lookup"><span data-stu-id="a04bf-330">**Option 1 is selected:** The caller is routed to the operating systems support team.</span></span>

  - <span data-ttu-id="a04bf-331">**选择选项 2：** 将呼叫者路由至内部应用程序支持组。</span><span class="sxs-lookup"><span data-stu-id="a04bf-331">**Option 2 is selected:** The caller is routed to the internal applications support team.</span></span>

  - <span data-ttu-id="a04bf-332">**选择选项 3：** 将呼叫者路由至软件支持组。</span><span class="sxs-lookup"><span data-stu-id="a04bf-332">**Option 3 is selected:** The caller is routed to the software support team.</span></span>

- <span data-ttu-id="a04bf-333">**选择选项 3：** 向呼叫者提出后续问题：</span><span class="sxs-lookup"><span data-stu-id="a04bf-333">**Option 3 is selected:** The caller is asked a follow-up question:</span></span>

    <span data-ttu-id="a04bf-p161">**问题：**“如果是打印机问题，请按 1。否则，请按 2。”</span><span class="sxs-lookup"><span data-stu-id="a04bf-p161">**Question:** "If this is a printer problem press 1. Otherwise, press 2."</span></span>

  - <span data-ttu-id="a04bf-336">**选择选项 1：** 将呼叫者路由至打印机支持组。</span><span class="sxs-lookup"><span data-stu-id="a04bf-336">**Option 1 is selected:** The caller is routed to the printer support team.</span></span>

  - <span data-ttu-id="a04bf-337">**选择选项 2：** 将呼叫者路由至硬件支持组。</span><span class="sxs-lookup"><span data-stu-id="a04bf-337">**Option 2 is selected:** The caller is routed to the hardware support team.</span></span>

<span data-ttu-id="a04bf-338">下图显示了相应的呼叫流。</span><span class="sxs-lookup"><span data-stu-id="a04bf-338">The following figure shows the call flow.</span></span>

 <span data-ttu-id="a04bf-339">**两级互动呼叫流**</span><span class="sxs-lookup"><span data-stu-id="a04bf-339">**Two-level interactive call flow**</span></span>

![使用互动语音响应设计呼叫流](../../media/Ops_OCS_RGS_IVRLevel2.jpg)

### <a name="best-practices"></a><span data-ttu-id="a04bf-341">最佳做法</span><span class="sxs-lookup"><span data-stu-id="a04bf-341">Best Practices</span></span>

<span data-ttu-id="a04bf-342">下面列出了用于设计 IVR 的一些最佳做法：</span><span class="sxs-lookup"><span data-stu-id="a04bf-342">The following list describes some best practices for designing your IVR:</span></span>

- <span data-ttu-id="a04bf-p162">让呼叫者快速开始任务。避免在 IVR 中提供过多信息或过长的营销消息。</span><span class="sxs-lookup"><span data-stu-id="a04bf-p162">Let the caller get to the task quickly. Avoid providing too much information or lengthy marketing messages in your IVR.</span></span>

- <span data-ttu-id="a04bf-p163">如果要包含过长的消息，可以考虑将其附加到第一个问题后面，而不要附加到欢迎消息中。如果该消息作为第一个问题的一部分，呼叫者可以通过回答问题来跳过该消息，但是呼叫者无法跳过欢迎消息。</span><span class="sxs-lookup"><span data-stu-id="a04bf-p163">If you want to include a lengthy message, consider appending it to the first question instead of to the welcome message. Callers can bypass the message if it is part of the first question by answering the question, but they cannot bypass the welcome message.</span></span>

- <span data-ttu-id="a04bf-347">用呼叫者的语言讲话。</span><span class="sxs-lookup"><span data-stu-id="a04bf-347">Speak in the caller's language.</span></span> <span data-ttu-id="a04bf-348">避免造作的语言。</span><span class="sxs-lookup"><span data-stu-id="a04bf-348">Avoid stilted language.</span></span> <span data-ttu-id="a04bf-349">自然地讲话。</span><span class="sxs-lookup"><span data-stu-id="a04bf-349">Speak naturally.</span></span>

- <span data-ttu-id="a04bf-350">高效书写和有效提示。</span><span class="sxs-lookup"><span data-stu-id="a04bf-350">Write efficient and effective prompts.</span></span> <span data-ttu-id="a04bf-351">删除任何不必要的选项。</span><span class="sxs-lookup"><span data-stu-id="a04bf-351">Remove any unnecessary options.</span></span> <span data-ttu-id="a04bf-352">对信息进行结构, 以便调用方的预期响应位于句子的末尾。</span><span class="sxs-lookup"><span data-stu-id="a04bf-352">Structure the information so that the caller's expected response is at the end of the sentence.</span></span> <span data-ttu-id="a04bf-353">例如, "要向销售团队讲话, 请按1。"</span><span class="sxs-lookup"><span data-stu-id="a04bf-353">For example, "To speak to the sales team, press 1."</span></span>

- <span data-ttu-id="a04bf-p166">使语音响应用户友好。例如，如果同时指定 DTMF 和语音响应，请使用与此类似的格式：“要与销售团队通话，请按 1 或说销售。”</span><span class="sxs-lookup"><span data-stu-id="a04bf-p166">Make voice responses user friendly. For example, if you specify both DTMF and voice responses, use something like: "To speak to the sales team, press 1 or say sales."</span></span>

- <span data-ttu-id="a04bf-356">在组织中部署 IVR 之前，请先对一组用户测试该 IVR。</span><span class="sxs-lookup"><span data-stu-id="a04bf-356">Test the IVR on a group of users before you deploy it across your organization.</span></span>

## <a name="creating-or-modifying-an-interactive-workflow"></a><span data-ttu-id="a04bf-357">创建或修改互动工作流</span><span class="sxs-lookup"><span data-stu-id="a04bf-357">Creating or modifying an interactive workflow</span></span>

### <a name="to-use-response-group-configuration-tool-to-create-or-modify-an-interactive-workflow"></a><span data-ttu-id="a04bf-358">使用 "响应组配置" 工具创建或修改交互式工作流</span><span class="sxs-lookup"><span data-stu-id="a04bf-358">To use Response Group Configuration Tool to create or modify an Interactive workflow</span></span>

1. <span data-ttu-id="a04bf-359">以 RTCUniversalServerAdmins 组成员的身份，或支持响应组的某个预定义管理角色的成员身份登录。</span><span class="sxs-lookup"><span data-stu-id="a04bf-359">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2. <span data-ttu-id="a04bf-360">打开一个浏览器窗口, 然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。</span><span class="sxs-lookup"><span data-stu-id="a04bf-360">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="a04bf-361">在左侧导航栏中，单击“响应组”\*\*\*\*，然后单击“工作流”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a04bf-361">In the left navigation bar, click **Response Groups**, and then click **Workflow**.</span></span>

4. <span data-ttu-id="a04bf-362">在“工作流”\*\*\*\* 页上，单击“创建或编辑工作流”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a04bf-362">On the **Workflow** page, click **Create or edit a workflow**.</span></span>

5. <span data-ttu-id="a04bf-363">在“选择服务”\*\*\*\* 搜索字段中，键入托管要创建或修改的工作流的  **ApplicationServer** 服务的全部或部分名称。</span><span class="sxs-lookup"><span data-stu-id="a04bf-363">In the **Select a Service** search field, type all or part of the name of the **ApplicationServer** service that hosts the workflow that you want to create or modify.</span></span> <span data-ttu-id="a04bf-364">在服务结果列表中，单击想要的服务，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a04bf-364">In the resulting list of services, click the service that you want, and then click **OK**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a04bf-365">此时将打开 "响应组配置" 工具。</span><span class="sxs-lookup"><span data-stu-id="a04bf-365">The Response Group Configuration Tool opens.</span></span> <span data-ttu-id="a04bf-366">您也可以通过键入以下 URL 直接从 web 浏览器打开 "响应组配置" 工具: https://\<webPoolFqdn\>/RgsConfig。</span><span class="sxs-lookup"><span data-stu-id="a04bf-366">You can also open the Response Group Configuration Tool directly from a web browser by typing the following URL: https://\<webPoolFqdn\>/RgsConfig.</span></span>

6. <span data-ttu-id="a04bf-367">请执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="a04bf-367">Do one of the following:</span></span>

   - <span data-ttu-id="a04bf-368">在“创建新的工作流”\*\*\*\* 下，单击“交互”\*\*\*\* 旁边的“创建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a04bf-368">Under **Create a New Workflow**, next to **Interactive**, click **Create**.</span></span>

   - <span data-ttu-id="a04bf-369">在“管理现有工作流”\*\*\*\* 下，找到想要更改的工作流，然后在“操作”\*\*\*\* 下单击“编辑”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a04bf-369">Under **Manage an Existing Workflow**, locate the workflow you want to change, and then under **Action**, click **Edit**.</span></span>

7. <span data-ttu-id="a04bf-370">如果尚未准备好让用户开始呼叫工作流，请清除“激活工作流”\*\*\*\* 复选框。</span><span class="sxs-lookup"><span data-stu-id="a04bf-370">If you are not ready for users to start calling the workflow, clear the **Activate the workflow** check box.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="a04bf-371">如果你要创建托管工作流, 你需要选择 "**激活工作流"**。</span><span class="sxs-lookup"><span data-stu-id="a04bf-371">If you are creating a managed workflow, you need to select **Activate the workflow**.</span></span> <span data-ttu-id="a04bf-372">在保存活动、受管理的工作流之后，则可以修改并停用该工作流。</span><span class="sxs-lookup"><span data-stu-id="a04bf-372">After you save the active, managed workflow, you can then modify and deactivate it.</span></span>

8. <span data-ttu-id="a04bf-373">要允许联盟用户呼叫组，请选中“启用联盟”\*\*\*\* 复选框。</span><span class="sxs-lookup"><span data-stu-id="a04bf-373">To allow federated users to call the group, select the **Enable for federation** check box.</span></span> <span data-ttu-id="a04bf-374">还必须具有适用于为联盟配置的响应组应用程序的外部访问策略。</span><span class="sxs-lookup"><span data-stu-id="a04bf-374">You must also have an external access policy that applies to the Response Group application configured for federation.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a04bf-375">全局外部访问策略适用于响应组应用程序。</span><span class="sxs-lookup"><span data-stu-id="a04bf-375">The global external access policy applies to the Response Group application.</span></span> <span data-ttu-id="a04bf-376">你可以使用 Skype for Business Server 控制面板或通过使用**CsExternalAccessPolicy** Cmdlet 将 EnableOutsideAccess 参数设置为 True, 为响应组联盟配置全局策略。</span><span class="sxs-lookup"><span data-stu-id="a04bf-376">You can configure the global policy for response group federation by using Skype for Business Server Control Panel or by using the **Set-CsExternalAccessPolicy** cmdlet to set the EnableOutsideAccess parameter to True.</span></span> <span data-ttu-id="a04bf-377">请记住，除非为全局策略设置分配站点或用户策略，否则这些设置适用于所有用户。</span><span class="sxs-lookup"><span data-stu-id="a04bf-377">Keep in mind that global policy settings apply to all users unless they are assigned a site or user policy.</span></span> <span data-ttu-id="a04bf-378">因此，在针对响应组更改此设置之前，请确保联盟设置满足您的组织的要求。</span><span class="sxs-lookup"><span data-stu-id="a04bf-378">Therefore, before changing this setting for response groups, make sure that the federation setting meets the requirements of your organization.</span></span> <span data-ttu-id="a04bf-379">有关策略如何适用于用户的详细信息，请参阅[Manage External Access Policy for Your Organization](https://technet.microsoft.com/library/5571811e-34c8-443a-b94c-1ab5d4275581.aspx)。</span><span class="sxs-lookup"><span data-stu-id="a04bf-379">For details about how policies apply to users, see [Manage External Access Policy for Your Organization](https://technet.microsoft.com/library/5571811e-34c8-443a-b94c-1ab5d4275581.aspx).</span></span> <span data-ttu-id="a04bf-380">有关联盟设置的详细信息, 请参阅文档中的 "**设置 CsExternalAccessPolicy** "。。</span><span class="sxs-lookup"><span data-stu-id="a04bf-380">For details about the federation setting, see **Set-CsExternalAccessPolicy** in documentation..</span></span>

    > [!NOTE]
    > <span data-ttu-id="a04bf-381">Skype for Business Online 中托管的用户不能将调用放到内部部署中托管的响应组。</span><span class="sxs-lookup"><span data-stu-id="a04bf-381">Users who are hosted in Skype for Business Online can't place calls to response groups that are hosted in an on-premises deployment.</span></span> <span data-ttu-id="a04bf-382">这在混合部署中以及内部部署与 Skype for Business Online 部署联合的情况下是如此。</span><span class="sxs-lookup"><span data-stu-id="a04bf-382">This is true in both hybrid deployments and in cases where an on-premises deployment is federated with a Skype for Business Online deployment.</span></span>

9. <span data-ttu-id="a04bf-383">要在呼叫过程中隐藏代理身份，请选中“启用代理匿名”\*\*\*\* 复选框。</span><span class="sxs-lookup"><span data-stu-id="a04bf-383">To hide the identity of agents during calls, select the **Enable agent anonymity** check box.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a04bf-p173">尽管建立呼叫后，代理或呼叫者可以添加即时消息 (IM) 和视频，但匿名呼叫无法启动 IM 或视频。匿名代理还可以将呼叫置于保持状态、转接呼叫（盲转接和咨询转接）、寄存和取回呼叫。匿名呼叫不支持会议、应用程序共享和桌面共享、文件传输、白板、数据协作和呼叫记录。使用 Lync VDI 插件的代理可以匿名方式接听来电，但他们无法以匿名方式拨出电话。</span><span class="sxs-lookup"><span data-stu-id="a04bf-p173">Anonymous calls cannot start with instant messaging (IM) or video, although the agent or the caller can add IM and video after the call is established. An anonymous agent can also put calls on hold, transfer calls (both blind and consultative transfers), and park and retrieve calls. Anonymous calls do not support conferencing, application sharing and desktop sharing, file transfer, whiteboarding and data collaboration, and call recording. Agents using the Lync VDI Plugin can receive incoming calls anonymously, but they cannot make outgoing calls anonymously.</span></span>

10. <span data-ttu-id="a04bf-388">在“输入将接收呼叫的组的地址”\*\*\*\* 下，键入将应答工作流呼叫的组的主 SIP 统一资源标识符 (URI) 地址。</span><span class="sxs-lookup"><span data-stu-id="a04bf-388">Under **Enter the address of the group that will receive the calls**, type the primary SIP uniform resource identifier (URI) address of the group that will answer calls to the workflow.</span></span>

11. <span data-ttu-id="a04bf-389">在“显示名称”\*\*\*\* 中，键入希望显示的工作流名称（例如，销售 IVR 响应组）。</span><span class="sxs-lookup"><span data-stu-id="a04bf-389">In **Display name**, type the name that you want to display for the workflow (for example, Sales IVR Response Group).</span></span>

    > [!NOTE]
    > <span data-ttu-id="a04bf-390">不要在显示名称中\<包含 ""\>或 "" 字符。</span><span class="sxs-lookup"><span data-stu-id="a04bf-390">Do not include the "\<" or "\>" characters in the display name.</span></span> <span data-ttu-id="a04bf-391">不要使用以下保留的显示名称：“RGS Presence Watcher”\*\*\*\* 或“Announcement Service”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a04bf-391">Do not use the following display names because they are reserved: **RGS Presence Watcher** or **Announcement Service**.</span></span>

12. <span data-ttu-id="a04bf-392">在“电话号码”\*\*\*\* 中，键入响应组的线路 URI（例如，+14255550165）。</span><span class="sxs-lookup"><span data-stu-id="a04bf-392">In **Telephone number**, type the line URI for the response group (for example, +14255550165).</span></span>

13. <span data-ttu-id="a04bf-393">在“显示号码”\*\*\*\* 下，键入希望显示的响应组号码（例如，+1 (425) 555-0165）。</span><span class="sxs-lookup"><span data-stu-id="a04bf-393">In **Display number**, type the number as you want it to appear for the response group (for example, +1 (425) 555-0165).</span></span>

14. <span data-ttu-id="a04bf-394">可选在 "**说明**" 中, 键入要在 Skype for business 中的联系人卡片上显示的工作流的说明。</span><span class="sxs-lookup"><span data-stu-id="a04bf-394">(Optional) In **Description**, type a description for the workflow that you want to appear on the contact card in Skype for Business.</span></span>

15. <span data-ttu-id="a04bf-395">如果此工作流将由响应组管理员管理，则在“工作流类型”\*\*\*\* 中选择“托管”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a04bf-395">In **Workflow Type**, select **Managed** if this workflow will be managed by a Response Group Manager.</span></span> <span data-ttu-id="a04bf-396">执行以下操作以将响应组管理器分配给工作流:</span><span class="sxs-lookup"><span data-stu-id="a04bf-396">Do the following to assign Response Group Managers to the workflow:</span></span>

    <span data-ttu-id="a04bf-397">a.</span><span class="sxs-lookup"><span data-stu-id="a04bf-397">a.</span></span> <span data-ttu-id="a04bf-398">键入此工作流的管理员的 SIP URI，单击“添加”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a04bf-398">Type the SIP URI of a manager for this workflow, and click **Add**.</span></span>

    <span data-ttu-id="a04bf-399">b.</span><span class="sxs-lookup"><span data-stu-id="a04bf-399">b.</span></span> <span data-ttu-id="a04bf-400">键入要添加到工作流的其他管理员的 SIP URI，单击“添加”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a04bf-400">Type the SIP URI of additional managers to add to the workflow, and click **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="a04bf-p178">必须为被指定为响应组管理员的每一位用户分配 CsResponseGroupManager 角色。如果没有为用户分配此角色，他们无法管理响应组。</span><span class="sxs-lookup"><span data-stu-id="a04bf-p178">Every user who is designated as a manager of a response group must be assigned the CsResponseGroupManager role. If users are not assigned this role, they cannot manage response groups.</span></span>

16. <span data-ttu-id="a04bf-403">在“步骤 2 选择语言”\*\*\*\* 下，单击要用于语音识别和文本到语音转换的语言。</span><span class="sxs-lookup"><span data-stu-id="a04bf-403">Under **Step 2 Select a Language**, click the language to use for speech recognition and text-to-speech.</span></span>

17. <span data-ttu-id="a04bf-404">如果要配置欢迎消息，则在“步骤 3 配置欢迎消息”\*\*\*\* 下选中“播放欢迎消息”\*\*\*\* 复选框，然后执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="a04bf-404">If you want to configure a welcome message, under **Step 3 Configure a Welcome Message**, select the **Play a welcome message** check box, and then do one of the following:</span></span>

    - <span data-ttu-id="a04bf-405">要为呼叫者输入转换成语音的文本形式的欢迎消息，请单击“使用文本到语音转换”\*\*\*\*，然后在文本框中键入欢迎消息。</span><span class="sxs-lookup"><span data-stu-id="a04bf-405">To enter the welcome message as text that is converted to speech for callers, click **Use text-to-speech**, and then type the welcome message in the text box.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a04bf-p179">不要在输入的文本中包含 HTML 标记，否则将收到错误消息。</span><span class="sxs-lookup"><span data-stu-id="a04bf-p179">Do not include HTML tags in the text you enter. If you include HTML tags, you will receive an error message.</span></span>

    - <span data-ttu-id="a04bf-p180">要使用 Wave 或 Windows Media 音频文件录音作为欢迎消息，请单击“选择录音”\*\*\*\*。如果要上载新的音频文件，请单击“录音”\*\*\*\* 链接。在新浏览器窗口中，单击“浏览”\*\*\*\*，选择要使用的音频文件，然后单击“打开”\*\*\*\*。单击“上载”\*\*\*\*，加载该音频文件。</span><span class="sxs-lookup"><span data-stu-id="a04bf-p180">To use a Wave or Windows Media Audio file recording for the welcome message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the audio file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a04bf-412">用户提供的所有音频文件都必须满足特定要求。</span><span class="sxs-lookup"><span data-stu-id="a04bf-412">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="a04bf-413">有关受支持的音频文件格式的详细信息，请参阅 [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx)。</span><span class="sxs-lookup"><span data-stu-id="a04bf-413">For details about supported file formats, see [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).</span></span>

18. <span data-ttu-id="a04bf-414">在“步骤 4 指定您的工作时间”\*\*\*\* 下的“您所在的时区”\*\*\*\* 框中，单击工作流的时区。</span><span class="sxs-lookup"><span data-stu-id="a04bf-414">Under **Step 4 Specify Your Business Hours**, in the **Your time zone** box, click the time zone of the workflow.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a04bf-p182">该时区是工作流的呼叫者和代理所在的时区。它用于计算工作流开放和关闭的时间点。例如，如果将工作流配置为使用北美东部时间的时区，并安排工作流在上午 7:00 开放，晚上 11:00 关闭，则得出的开放和关闭时间点分别为东部时间 7:00 和东部时间 11:00。（必须以 24 小时制输入时间。）</span><span class="sxs-lookup"><span data-stu-id="a04bf-p182">The time zone is the time zone where the callers and agents of the workflow reside. It is used to calculate the open and close hours. For example, if the workflow is configured to use the North American Eastern Time zone and the workflow is scheduled to open at 7:00 A.M. and close at 11:00 P.M., the open and close times are assumed to be 7:00 Eastern Time and 11:00 Eastern Time respectively. (You must enter the times in 24-hour time notation.)</span></span>

19. <span data-ttu-id="a04bf-420">通过执行下列操作之一选择要使用的工作时间日程表类型：</span><span class="sxs-lookup"><span data-stu-id="a04bf-420">Select the type of business hours schedule you want to use by doing one of the following:</span></span>

    - <span data-ttu-id="a04bf-421">要使用预定义工作时间日程表，请单击“使用预设日程表”\*\*\*\*，然后从下拉列表中选择要使用的日程表。</span><span class="sxs-lookup"><span data-stu-id="a04bf-421">To use a predefined schedule of business hours, click **Use a preset schedule**, and then select the schedule you want to use from the drop-down list.</span></span>

      > [!NOTE]
      > <span data-ttu-id="a04bf-422">之前您必须至少已定义一个预设日程表才能选择该选项。</span><span class="sxs-lookup"><span data-stu-id="a04bf-422">You must have defined at least one preset schedule previously to be able to select this option.</span></span> <span data-ttu-id="a04bf-423">使用**CsRgsHoursOfBusiness** cmdlet 定义预置的计划。</span><span class="sxs-lookup"><span data-stu-id="a04bf-423">You define preset schedules by using the **New-CsRgsHoursOfBusiness** cmdlet.</span></span> <span data-ttu-id="a04bf-424">有关详细信息, 请参阅[(可选) 在 Skype For business 中定义响应组工作时间](optional-define-response-group-business-hours.md)。</span><span class="sxs-lookup"><span data-stu-id="a04bf-424">For details, see [(Optional) Define Response Group business hours in Skype for Business](optional-define-response-group-business-hours.md).</span></span> <span data-ttu-id="a04bf-425">选择预设日程表时，“天”\*\*\*\*、“开放”\*\*\*\* 和“关闭”\*\*\*\* 中会自动填写响应组可以应答的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="a04bf-425">When you select a preset schedule, **Day**, **Open**, and **Close** are automatically filled with the days and hours that the response group is available.</span></span>

    - <span data-ttu-id="a04bf-426">要使用仅适用于该工作流的自定义日程表，请单击“使用自定义日程表”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a04bf-426">To use a custom schedule that applies only to this workflow, click **Use a custom schedule**.</span></span>

20. <span data-ttu-id="a04bf-427">如果要创建该工作流的自定义日程表，请单击一周中响应组可以应答的日期对应的复选框。</span><span class="sxs-lookup"><span data-stu-id="a04bf-427">If you are creating a custom schedule for this workflow, click the check boxes for the days of the week that the response group is available.</span></span>

21. <span data-ttu-id="a04bf-428">如果要创建自定义计划, 请在 "响应" 组可用时键入 "**打开**" 和 "**关闭**" 时间。</span><span class="sxs-lookup"><span data-stu-id="a04bf-428">If you are creating a custom schedule, type the **Open** and **Close** hours when the response group will be available.</span></span>

     > [!NOTE]
     > <span data-ttu-id="a04bf-p184">“开放”\*\*\*\* 和“关闭”\*\*\*\* 时间点必须采用 24 小时制。例如，如果营业时间为朝九晚五，其中午餐时间不办公，则工作时间指定为 9:00“开放”\*\*\*\*、12:00“关闭”\*\*\*\*、13:00“开放”\*\*\*\* 及 17:00“关闭”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a04bf-p184">The **Open** and **Close** hours must be in 24-hour time notation. For example, if your office works a 9-to-5 work day and closes at noon for lunch, the business hours are specified as **Open** 9:00, **Close** 12:00, **Open** 13:00, and **Close** 17:00.</span></span>

22. <span data-ttu-id="a04bf-431">如果要在办公室未开放时播放消息，请选中“响应组在工作时间以外时播放消息”\*\*\*\* 复选框，然后通过执行以下操作之一指定要播放的消息：</span><span class="sxs-lookup"><span data-stu-id="a04bf-431">If you want to play a message when the office is not open, select the **Play a message when the response group is outside of business hours** check box, and then specify the message to play by doing one of the following:</span></span>

    - <span data-ttu-id="a04bf-432">要为呼叫者输入转换成语音的文本形式的消息，请单击“使用文本到语音转换”\*\*\*\*，然后在文本框中键入消息。</span><span class="sxs-lookup"><span data-stu-id="a04bf-432">To enter the message as text that is converted to speech for the caller, click **Use text-to-speech**, and then type the message in the text box.</span></span>

      > [!NOTE]
      > <span data-ttu-id="a04bf-433">不要在输入的文本中包含 HTML 标记。</span><span class="sxs-lookup"><span data-stu-id="a04bf-433">Do not include HTML tags in the text you enter.</span></span> <span data-ttu-id="a04bf-434">如果包含 HTML 标记, 则会收到一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="a04bf-434">If you include HTML tags, you will receive an error message.</span></span>

    - <span data-ttu-id="a04bf-p186">要使用音频文件录音作为消息，请单击“选择录音”\*\*\*\*。如果要上载新的音频文件，请单击“录音”\*\*\*\* 链接。在新浏览器窗口中，单击“浏览”\*\*\*\*，选择要使用的文件，然后单击“打开”\*\*\*\*。单击“上载”\*\*\*\*，加载该音频文件。</span><span class="sxs-lookup"><span data-stu-id="a04bf-p186">To use an audio file recording for the message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a04bf-439">用户提供的所有音频文件都必须满足特定要求。</span><span class="sxs-lookup"><span data-stu-id="a04bf-439">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="a04bf-440">有关受支持的音频文件格式的详细信息，请参阅 [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx)。</span><span class="sxs-lookup"><span data-stu-id="a04bf-440">For details about supported file formats, see [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).</span></span>

23. <span data-ttu-id="a04bf-441">指定播放消息后如何处理呼叫（如果配置了消息）：</span><span class="sxs-lookup"><span data-stu-id="a04bf-441">Specify how to handle calls after the message is played (if a message is configured):</span></span>

    - <span data-ttu-id="a04bf-442">要断开呼叫，请单击“断开呼叫”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a04bf-442">To disconnect the call, click **Disconnect Call**.</span></span>

    - <span data-ttu-id="a04bf-443">要将呼叫转接到语音邮件，请单击“转接到语音邮件”\*\*\*\*，然后键入语音邮件地址。</span><span class="sxs-lookup"><span data-stu-id="a04bf-443">To forward the call to voice mail, click **Forward to voice mail**, and then type the voice mail address.</span></span> <span data-ttu-id="a04bf-444">语音邮件地址的格式是\* \<用户名\>*@*\<域名\> \* (例如, bob@contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="a04bf-444">The format for the voice mail address is  *\<username\>*@*\<domainname\>* (for example, bob@contoso.com).</span></span>

    - <span data-ttu-id="a04bf-445">要将呼叫转接到另一个用户，请单击“转接到 SIP URI”\*\*\*\*，然后键入用户地址。</span><span class="sxs-lookup"><span data-stu-id="a04bf-445">To forward the call to another user, click **Forward to SIP URI**, and then type a user address.</span></span> <span data-ttu-id="a04bf-446">用户地址的格式是_ \<用户名\>_@_\<域名\>_。</span><span class="sxs-lookup"><span data-stu-id="a04bf-446">The format for the user address is  _\<username\>_@_\<domainname\>_.</span></span>

    - <span data-ttu-id="a04bf-447">要将呼叫转接到另一个电话号码，请单击“转接到电话号码”\*\*\*\*，然后键入该电话号码。</span><span class="sxs-lookup"><span data-stu-id="a04bf-447">To forward the call to another telephone number, click **Forward to telephone number**, and then type the telephone number.</span></span> <span data-ttu-id="a04bf-448">电话号码的格式为\* \<\>*@"*\<域名域名\> \* " (例如 + 14255550121@contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="a04bf-448">The format for the telephone number is  *\<number\>*@*\<domainname\>* (for example, +14255550121@contoso.com).</span></span> <span data-ttu-id="a04bf-449">域名可用来将呼叫者路由至正确的目标。</span><span class="sxs-lookup"><span data-stu-id="a04bf-449">The domain name is used to route the caller to the correct destination.</span></span>

24. <span data-ttu-id="a04bf-450">在“步骤 5 指定您的假日”\*\*\*\* 下，单击定义响应组停止营业日期的一个或多个假日集对应的复选框。</span><span class="sxs-lookup"><span data-stu-id="a04bf-450">Under **Step 5 Specify Your Holidays**, click the check boxes for one or more sets of holidays that define the days when the response group is closed for business.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a04bf-451">配置工作流之前，您需要先定义假日和假日集。</span><span class="sxs-lookup"><span data-stu-id="a04bf-451">You need to define holidays and holiday sets before you configure the workflow.</span></span> <span data-ttu-id="a04bf-452">使用 **New-CsRgsHoliday** 和 **New-CsRgsHolidaySet** cmdlet 可定义假日和假日集。</span><span class="sxs-lookup"><span data-stu-id="a04bf-452">Use the **New-CsRgsHoliday** and **New-CsRgsHolidaySet** cmdlets to define holidays and holiday sets.</span></span> <span data-ttu-id="a04bf-453">有关详细信息, 请参阅[(可选) 在 Skype For business 中定义 "响应组" 假日集](optional-define-response-group-holiday-sets.md)。</span><span class="sxs-lookup"><span data-stu-id="a04bf-453">For details, see [(Optional) Define Response Group holiday sets in Skype for Business](optional-define-response-group-holiday-sets.md).</span></span>

25. <span data-ttu-id="a04bf-454">如果要在假日播放消息，请选中“假期播放消息”\*\*\*\* 复选框，然后通过执行以下操作之一指定要播放的消息：</span><span class="sxs-lookup"><span data-stu-id="a04bf-454">If you want to play a message on holidays, select the **Play a message during holidays** check box, and then specify the message to play by doing one of the following:</span></span>

    - <span data-ttu-id="a04bf-455">要为呼叫者输入转换成语音的文本形式的消息，请单击“使用文本到语音转换”\*\*\*\*，然后在文本框中键入消息。</span><span class="sxs-lookup"><span data-stu-id="a04bf-455">To enter the message as text that is converted to speech for the caller, click **Use text-to-speech**, and then type the message in the text box.</span></span>

      > [!NOTE]
      > <span data-ttu-id="a04bf-456">不要在输入的文本中包含 HTML 标记。</span><span class="sxs-lookup"><span data-stu-id="a04bf-456">Do not include HTML tags in the text you enter.</span></span> <span data-ttu-id="a04bf-457">如果包含 HTML 标记, 则会收到一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="a04bf-457">If you include HTML tags, you will receive an error message.</span></span>

    - <span data-ttu-id="a04bf-p193">要使用音频文件录音作为消息，请单击“选择录音”\*\*\*\*。如果要上载新的音频文件，请单击“录音”\*\*\*\* 链接。在新浏览器窗口中，单击“浏览”\*\*\*\*，选择要使用的文件，然后单击“打开”\*\*\*\*。单击“上载”\*\*\*\*，加载该音频文件。</span><span class="sxs-lookup"><span data-stu-id="a04bf-p193">To use an audio file recording for the message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>

      > [!NOTE]
      > <span data-ttu-id="a04bf-p194">用户提供的所有音频文件都必须满足特定要求。有关受支持的音频文件格式的详细信息，请参阅 [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx)。</span><span class="sxs-lookup"><span data-stu-id="a04bf-p194">All user-provided audio files must meet certain requirements. For details about supported audio file formats, see [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).</span></span>

26. <span data-ttu-id="a04bf-464">指定播放消息后如何处理呼叫（如果配置了消息）：</span><span class="sxs-lookup"><span data-stu-id="a04bf-464">Specify how to handle calls after the message is played (if a message is configured):</span></span>

    - <span data-ttu-id="a04bf-465">要断开呼叫，请单击“断开呼叫”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a04bf-465">To disconnect the call, click **Disconnect Call**.</span></span>

    - <span data-ttu-id="a04bf-466">要将呼叫转接到语音邮件，请单击“转接到语音邮件”\*\*\*\*，然后键入语音邮件地址。</span><span class="sxs-lookup"><span data-stu-id="a04bf-466">To forward the call to voice mail, click **Forward to voice mail**, and then type the voice mail address.</span></span> <span data-ttu-id="a04bf-467">语音邮件地址的格式是\* \<用户名\>*@*\<域名\> \* (例如, bob@contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="a04bf-467">The format for the voice mail address is  *\<username\>*@*\<domainname\>* (for example, bob@contoso.com).</span></span>

    - <span data-ttu-id="a04bf-468">要将呼叫转接到另一个用户，请单击“转接到 SIP URI”\*\*\*\*，然后键入用户地址。</span><span class="sxs-lookup"><span data-stu-id="a04bf-468">To forward the call to another user, click **Forward to SIP URI**, and then type a user address.</span></span> <span data-ttu-id="a04bf-469">用户地址的格式是_ \<用户名\>_@_\<域名\>_。</span><span class="sxs-lookup"><span data-stu-id="a04bf-469">The format for the user address is  _\<username\>_@_\<domainname\>_.</span></span>

    - <span data-ttu-id="a04bf-470">要将呼叫转接到另一个电话号码，请单击“转接到电话号码”\*\*\*\*，然后键入该电话号码。</span><span class="sxs-lookup"><span data-stu-id="a04bf-470">To forward the call to another telephone number, click **Forward to telephone number**, and then type the telephone number.</span></span> <span data-ttu-id="a04bf-471">电话号码的格式为\* \<\>*@"*\<域名域名\> \* " (例如 + 14255550121@contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="a04bf-471">The format for the telephone number is  *\<number\>*@*\<domainname\>* (for example, +14255550121@contoso.com).</span></span> <span data-ttu-id="a04bf-472">域名可用来将呼叫者路由至正确的目标。</span><span class="sxs-lookup"><span data-stu-id="a04bf-472">The domain name is used to route the caller to the correct destination.</span></span>

27. <span data-ttu-id="a04bf-473">在“步骤 6 配置保持音乐”\*\*\*\* 下，执行以下操作之一，选择希望呼叫者在等待代理时听到的音乐：</span><span class="sxs-lookup"><span data-stu-id="a04bf-473">Under **Step 6 Configure Music on Hold**, choose what you want callers to listen to while waiting for an agent by doing one of the following:</span></span>

    - <span data-ttu-id="a04bf-474">要使用默认保持音乐录音，请单击“使用默认值”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a04bf-474">To use the default music on-hold recording, click **Use default**.</span></span>

    - <span data-ttu-id="a04bf-p198">要使用音频文件录音作为保持音乐，请单击“选择音乐文件”\*\*\*\*。如果要上载新的音频文件，请单击“音乐文件”\*\*\*\* 链接。在新浏览器窗口中，单击“浏览”\*\*\*\*，选择要使用的文件，然后单击“打开”\*\*\*\*。单击“上载”\*\*\*\*，加载该音频文件。</span><span class="sxs-lookup"><span data-stu-id="a04bf-p198">To use an audio file recording for the on-hold music, click **Select a music file**. If you want to upload a new audio file, click the **a music file** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a04bf-p199">用户提供的所有音频文件都必须满足特定要求。有关受支持的音频文件格式的详细信息，请参阅 [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx)。</span><span class="sxs-lookup"><span data-stu-id="a04bf-p199">All user-provided audio files must meet certain requirements. For details about supported file formats, see [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).</span></span>

28. <span data-ttu-id="a04bf-481">在“步骤 7 配置互动语音响应”\*\*\*\* 下的“用户将听到以下文本或录制的消息”\*\*\*\* 标题中，指定要向呼叫者提出的问题，具体操作如下所示：</span><span class="sxs-lookup"><span data-stu-id="a04bf-481">Under **Step 7 Configure Interactive Voice Response**, under the **The user will hear the following text or recorded message** heading, specify the question to ask callers as follows:</span></span>

    - <span data-ttu-id="a04bf-482">要输入文本格式的问题，请单击“使用文本到语音转换”\*\*\*\*，然后在文本框中键入问题。</span><span class="sxs-lookup"><span data-stu-id="a04bf-482">To enter the question in text format, click **Use text-to-speech**, and type the question in the text box.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a04bf-p200">不要在输入的文本中包含 HTML 标记，否则将收到错误消息。</span><span class="sxs-lookup"><span data-stu-id="a04bf-p200">Do not include HTML tags in the text you enter. If you include HTML tags, you will receive an error message.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a04bf-485">文本到语音转换引擎会将符号“#”转换为“号码”这个词。</span><span class="sxs-lookup"><span data-stu-id="a04bf-485">The "#" symbol is translated by the text-to-speech engine as the word "number".</span></span> <span data-ttu-id="a04bf-486">如果需要指代 # 键，则应该在提示语中使用键名代替符号。</span><span class="sxs-lookup"><span data-stu-id="a04bf-486">If you need to refer to the # key, you should use the key name, rather than the symbol, in your prompt.</span></span> <span data-ttu-id="a04bf-487">例如，“要与销售人员交谈，请按井号键”。</span><span class="sxs-lookup"><span data-stu-id="a04bf-487">For example, "To talk to sales, press the pound key."</span></span>

    - <span data-ttu-id="a04bf-488">若要使用包含问题的预先录制音频文件, 请单击 "**选择录制**", 然后单击 "**录制**" 链接以上载文件。</span><span class="sxs-lookup"><span data-stu-id="a04bf-488">To use a prerecorded audio file that contains the question, click **Select a recording**, and then click the **a recording** link to upload the file.</span></span> <span data-ttu-id="a04bf-489">在新浏览器窗口中, 单击 "**浏览**", 选择音频文件, 然后单击 "**打开**"。</span><span class="sxs-lookup"><span data-stu-id="a04bf-489">In the new browser window, click **Browse**, select the audio file, and then click **Open**.</span></span> <span data-ttu-id="a04bf-490">单击 "**上载**" 加载文件, 然后可以选择在文本框中键入问题 (这将允许问题以及呼叫者的响应被转发到响应的代理)。</span><span class="sxs-lookup"><span data-stu-id="a04bf-490">Click **Upload** to load the file, and then optionally you can type the question in the text box (this enables the question, and the caller's response, to be forwarded to the responding agent).</span></span>

      > [!NOTE]
      > <span data-ttu-id="a04bf-p203">用户提供的所有音频文件都必须满足特定要求。有关受支持的音频文件格式的详细信息，请参阅 [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx)。</span><span class="sxs-lookup"><span data-stu-id="a04bf-p203">All user-provided audio files must meet certain requirements. For details about supported file formats, see [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).</span></span>

29. <span data-ttu-id="a04bf-493">在“响应 1”\*\*\*\* 下，指定第一个可能的问题答案，具体操作如下：</span><span class="sxs-lookup"><span data-stu-id="a04bf-493">Under **Response 1**, specify the first possible answer to the question by doing the following:</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="a04bf-p204">不要在任何语音响应中使用引号 (")。引号会导致 IVR 失败。</span><span class="sxs-lookup"><span data-stu-id="a04bf-p204">Do not use quotation marks (") in any voice responses. Quotation marks cause the IVR to fail.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a04bf-496">可以选择允许呼叫者使用语音、字母数字键盘输入或同时使用两者进行回答。</span><span class="sxs-lookup"><span data-stu-id="a04bf-496">You can choose to allow callers to answer using speech, alphanumeric keypad input, or both.</span></span>

    - <span data-ttu-id="a04bf-497">如果要允许呼叫者使用语音进行响应，请在“输入语音响应”\*\*\*\* 中输入答案。</span><span class="sxs-lookup"><span data-stu-id="a04bf-497">If you want to allow the caller to respond using speech, enter the answer in **Enter a voice response**.</span></span>

    - <span data-ttu-id="a04bf-498">如果要允许呼叫者通过按小键盘上的键进行响应，请在“数字”\*\*\*\* 中单击小键盘的数字。</span><span class="sxs-lookup"><span data-stu-id="a04bf-498">If you want to allow the caller to respond by pressing a key on the keypad, in **Digit**, click the keypad digit.</span></span>

30. <span data-ttu-id="a04bf-499">指定将呼叫者路由至队列，还是提出其他问题，如下所示：</span><span class="sxs-lookup"><span data-stu-id="a04bf-499">Specify whether to route the caller to a queue, or to ask another question as follows:</span></span>

    - <span data-ttu-id="a04bf-500">要将呼叫者路由至某个队列，请单击“发送到队列”\*\*\*\*，然后在“选择队列”\*\*\*\* 中单击要使用的队列。</span><span class="sxs-lookup"><span data-stu-id="a04bf-500">To route the caller to a queue, click **Send to a queue**, and in **Select a queue**, click the queue that you want to use.</span></span>

    - <span data-ttu-id="a04bf-p205">要提出其他问题，请单击“提出其他问题”\*\*\*\*，然后单击“使用文本到语音转换”\*\*\*\* 并键入问题，或单击“选择录音”\*\*\*\*。使用本节中的响应分组指定其他问题的可能响应（最多四个），以及用于每个响应的队列。要指定第三个或第四个可能的响应，请单击“响应 3”\*\*\*\* 或“响应 4”\*\*\*\* 复选框。</span><span class="sxs-lookup"><span data-stu-id="a04bf-p205">To ask another question, click **Ask another question**, and then click **Use text-to-speech** and type the question, or click **Select a recording**. Use the response groupings in this section to specify up to four possible responses to the additional question and the queue to use for each response. To specify a third or fourth possible response, click the **Response 3** check box or the **Response 4** check box.</span></span>

31. <span data-ttu-id="a04bf-p206">通过重复步骤 28 和 29 为原题指定多达三个以上可能的答案，以指定可能的响应以及对于每个响应要采取的操作。要指定第三个或第四个可能的答案，请单击“响应 3”\*\*\*\* 或“响应 4”\*\*\*\* 复选框。</span><span class="sxs-lookup"><span data-stu-id="a04bf-p206">Specify up to three more possible answers to the original question by repeating steps 28 and 29 to specify the possible responses and the action to take for each response. To specify a third or fourth possible answer, click the **Response 3** check box or the **Response 4** check box.</span></span>

32. <span data-ttu-id="a04bf-506">单击“部署”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a04bf-506">Click **Deploy**.</span></span>

### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-an-interactive-workflow"></a><span data-ttu-id="a04bf-507">使用 Skype for Business Server Management Shell 创建或修改交互式工作流</span><span class="sxs-lookup"><span data-stu-id="a04bf-507">To use Skype for Business Server Management Shell to create or modify an Interactive workflow</span></span>

1.  <span data-ttu-id="a04bf-508">以 RTCUniversalServerAdmins 组成员的身份，或支持响应组的某个预定义管理角色的成员身份登录。</span><span class="sxs-lookup"><span data-stu-id="a04bf-508">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2. <span data-ttu-id="a04bf-509">启动 Skype for Business Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\* 和“Skype for Business 2015”\*\*\*\*，然后单击“Skype for Business Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a04bf-509">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

3. <span data-ttu-id="a04bf-p207">检索响应组服务的服务名称，并将其分配到某个变量。在该命令行处，运行：</span><span class="sxs-lookup"><span data-stu-id="a04bf-p207">Retrieve the service name for the Response Group service and assign it to a variable. At the command line, run:</span></span>

   ```
   $serviceId = "service:" + (Get-CsService | ?{$_.Applications -like "*RGS*"}).ServiceId;
   ```

4. <span data-ttu-id="a04bf-p208">互动工作流需要两个或多个队列，以及两个或多个代理组。首先，创建代理组。运行：</span><span class="sxs-lookup"><span data-stu-id="a04bf-p208">An interactive workflow requires two or more queues and two or more agent groups. First, create the agent groups. Run:</span></span>

   ```
   $AGSupport = New-CsRgsAgentGroup -Parent $serviceId -Name "Technical Support" [-AgentAlertTime "20"] [-ParticipationPolicy "Informal"] [-RoutingMethod LongestIdle] [-AgentsByUri("sip:agent1@contoso.com", "sip:agent2@contoso.com")]
   $AGSales = New-CsRgsAgentGroup -Parent $serviceId -Name "Sales Team" [-AgentAlertTime "20"] [-ParticipationPolicy "Informal"] [-RoutingMethod LongestIdle] [-AgentsByUri("sip:bob@contoso.com", "sip:alice@contoso.com")]
   ```

5. <span data-ttu-id="a04bf-p209">创建队列。运行：</span><span class="sxs-lookup"><span data-stu-id="a04bf-p209">Create the queues. Run:</span></span>

   ```
   $QSupport = New-CsRgsQueue -Parent $ServiceId -Name "Contoso Support" -AgentGroupIDList($AG-Support.Identity)
   $QSales = New-CsRgsQueue -Parent $ServiceId -Name "Contoso Sales" -AgentGroupIDList($AG-Sales.Identity)
   ```

6. <span data-ttu-id="a04bf-p210">创建第一个响应组提示。运行：</span><span class="sxs-lookup"><span data-stu-id="a04bf-p210">Create the first response group prompt. Run:</span></span>

   ```
   $SupportPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Please be patient while we connect you with Contoso Technical Support."
   ```

7. <span data-ttu-id="a04bf-p211">然后，创建在提示后要执行的操作。运行：</span><span class="sxs-lookup"><span data-stu-id="a04bf-p211">Then create the action to be performed after the prompt. Run:</span></span>

   ```
   $SupportAction = New-CsRgsCallAction -Prompt $SupportPrompt -Action TransferToQueue -QueueID $QSupport.Identity
   ```

8. <span data-ttu-id="a04bf-p212">创建第一个响应组应答。运行：</span><span class="sxs-lookup"><span data-stu-id="a04bf-p212">Create the first response group answer. Run:</span></span>

   ```
   $SupportAnswer = New-CsRgsAnswer -Action $SupportAction [-DtmfResponse 1]
   ```

9. <span data-ttu-id="a04bf-p213">现在，创建第二个提示、呼叫操作和应答。首先创建提示。运行：</span><span class="sxs-lookup"><span data-stu-id="a04bf-p213">Now create the second prompt, call action, and answer. First create the prompt. Run:</span></span>

   ```
   $SalesPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Please hold while we connect you with Contoso Sales."
   ```

10. <span data-ttu-id="a04bf-p214">创建第二个呼叫操作。运行：</span><span class="sxs-lookup"><span data-stu-id="a04bf-p214">Create the second call action. Run:</span></span>

    ```
    $SalesAction = New-CsRgsCallAction -Prompt $SalesPrompt -Action TransferToQueue -QueueID $QSales.Identity
    ```

11. <span data-ttu-id="a04bf-p215">创建第二个响应组应答。运行：</span><span class="sxs-lookup"><span data-stu-id="a04bf-p215">Create the second response group answer. Run:</span></span>

    ```
    $SalesAnswer = New-CsRgsAnswer -Action $SalesAction [-DtmfResponse 2]
    ```

12. <span data-ttu-id="a04bf-p216">创建顶级提示。运行：</span><span class="sxs-lookup"><span data-stu-id="a04bf-p216">Create the top-level prompt. Run:</span></span>

    ```
    $TopLevelPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Thank you for calling Contoso. For Technical Support, press 1. For a Sales Representative, press 2."
    ```

13. <span data-ttu-id="a04bf-p217">创建顶级问题。运行：</span><span class="sxs-lookup"><span data-stu-id="a04bf-p217">Create the top-level question. Run:</span></span>

    ```
    $TopLevelQuestion = New-CsRgsQuestion -Prompt $TopLevelPrompt [-AnswerList ($SupportAnswer, $SalesAnswer)]
    ```

14. <span data-ttu-id="a04bf-p218">现在，创建工作流。运行：</span><span class="sxs-lookup"><span data-stu-id="a04bf-p218">Now create the workflow. Run:</span></span>

    ```
    $IVRAction = New-CsRgsCallAction -Action TransferToQuestion [-Question $Question]
    $IVRWorkflow = New-CsRgsWorkflow -Parent $ServiceId -Name "Contoso Helpdesk" [-Description "The Contoso Helpdesk line."] -PrimaryUri "sip:helpdesk@contoso.com" [-LineUri tel:+14255554321] [-DisplayNumber "+1 (425) 555-4321"] [-Active $true] [-Anonymous $true] [-DefaultAction $IVRAction] [-Managed $true] [-ManagersByURI ("sip:mindy@contoso.com", "sip:bob@contoso.com")]
    ```

     > [!NOTE]
     > <span data-ttu-id="a04bf-536">必须向已被指定为响应组管理者的所有用户分配 CsResponseGroupManager 角色。</span><span class="sxs-lookup"><span data-stu-id="a04bf-536">All users who have been designated as manager of a response group must be assigned the CsResponseGroupManager role.</span></span> <span data-ttu-id="a04bf-537">如果没有为用户分配此角色，他们无法管理响应组。</span><span class="sxs-lookup"><span data-stu-id="a04bf-537">If users are not assigned this role, they cannot manage response groups.</span></span>

## <a name="see-also"></a><span data-ttu-id="a04bf-538">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a04bf-538">See also</span></span>

[<span data-ttu-id="a04bf-539">可选在 Skype for Business 中定义响应组假日集</span><span class="sxs-lookup"><span data-stu-id="a04bf-539">(Optional) Define Response Group holiday sets in Skype for Business</span></span>](optional-define-response-group-holiday-sets.md)

[<span data-ttu-id="a04bf-540">可选在 Skype for Business 中定义响应组工作时间</span><span class="sxs-lookup"><span data-stu-id="a04bf-540">(Optional) Define Response Group business hours in Skype for Business</span></span>](optional-define-response-group-business-hours.md)

[<span data-ttu-id="a04bf-541">新-CsRgsWorkflow</span><span class="sxs-lookup"><span data-stu-id="a04bf-541">New-CsRgsWorkflow</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgsworkflow?view=skype-ps)

[<span data-ttu-id="a04bf-542">Set-CsRgsWorkflow</span><span class="sxs-lookup"><span data-stu-id="a04bf-542">Set-CsRgsWorkflow</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csrgsworkflow?view=skype-ps)

[<span data-ttu-id="a04bf-543">New-CsRgsPrompt</span><span class="sxs-lookup"><span data-stu-id="a04bf-543">New-CsRgsPrompt</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgsprompt?view=skype-ps)

[<span data-ttu-id="a04bf-544">新-CsRgsCallAction</span><span class="sxs-lookup"><span data-stu-id="a04bf-544">New-CsRgsCallAction</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps)

