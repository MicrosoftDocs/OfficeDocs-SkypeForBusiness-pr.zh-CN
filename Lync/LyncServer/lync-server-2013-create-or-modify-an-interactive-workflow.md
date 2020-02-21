---
title: Lync Server 2013：创建或修改交互式工作流
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify an interactive workflow
ms:assetid: bc7bb1bc-bf6a-4636-ae93-c56fa22613fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205213(v=OCS.15)
ms:contentKeyID: 48185260
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 21ce360c523573af90daecca55fba1eb8a52876d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202858"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-an-interactive-workflow-in-lync-server-2013"></a><span data-ttu-id="ecd19-102">在 Lync Server 2013 中创建或修改交互式工作流</span><span class="sxs-lookup"><span data-stu-id="ecd19-102">Create or modify an interactive workflow in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ecd19-103">_**上次修改的主题：** 2013-09-11_</span><span class="sxs-lookup"><span data-stu-id="ecd19-103">_**Topic Last Modified:** 2013-09-11_</span></span>

<span data-ttu-id="ecd19-104">可使用以下其中一个过程来创建或修改互动工作流。</span><span class="sxs-lookup"><span data-stu-id="ecd19-104">Use one of the following procedures to create or modify an interactive workflow.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ecd19-105">您可以使用 Lync Server 命令行管理程序或响应组配置工具来创建和修改交互式工作流。</span><span class="sxs-lookup"><span data-stu-id="ecd19-105">You can use Lync Server Management Shell or the Response Group Configuration Tool to create and modify interactive workflows.</span></span> <span data-ttu-id="ecd19-106">您可以从 Lync Server 控制面板访问响应组配置工具，也可以通过键入以下 URL 直接从 web 浏览器打开网页： <STRONG>https://</STRONG>&lt;webPoolFqdn&gt;<STRONG>/RgsConfig</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="ecd19-106">You can access the Response Group Configuration Tool from Lync Server Control Panel, or by opening the webpage directly from a web browser by typing the following URL: <STRONG>https://</STRONG>&lt;webPoolFqdn&gt;<STRONG>/RgsConfig</STRONG>.</span></span>



</div>

<div>

## <a name="to-use-response-group-configuration-tool-to-create-or-modify-an-interactive-workflow"></a><span data-ttu-id="ecd19-107">使用响应组配置工具创建或修改交互式工作流</span><span class="sxs-lookup"><span data-stu-id="ecd19-107">To use Response Group Configuration Tool to create or modify an Interactive workflow</span></span>

1.  <span data-ttu-id="ecd19-108">以 RTCUniversalServerAdmins 组成员的身份登录，或以支持响应组的预定义管理角色之一的成员身份登录。</span><span class="sxs-lookup"><span data-stu-id="ecd19-108">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="ecd19-109">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="ecd19-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="ecd19-110">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="ecd19-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="ecd19-111">在左侧导航栏中，单击“响应组”\*\*\*\*，然后单击“工作流”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ecd19-111">In the left navigation bar, click **Response Groups**, and then click **Workflow**.</span></span>

4.  <span data-ttu-id="ecd19-112">在“工作流”\*\*\*\* 页上，单击“创建或编辑工作流”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ecd19-112">On the **Workflow** page, click **Create or edit a workflow**.</span></span>

5.  <span data-ttu-id="ecd19-113">在“选择服务”\*\*\*\* 搜索字段中，键入托管要创建或修改的工作流的 **ApplicationServer** 服务的全部或部分名称。</span><span class="sxs-lookup"><span data-stu-id="ecd19-113">In the **Select a Service** search field, type all or part of the name of the **ApplicationServer** service that hosts the workflow that you want to create or modify.</span></span> <span data-ttu-id="ecd19-114">在服务结果列表中，单击想要的服务，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ecd19-114">In the resulting list of services, click the service that you want, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ecd19-115">将打开 "响应组配置" 工具。</span><span class="sxs-lookup"><span data-stu-id="ecd19-115">The Response Group Configuration Tool opens.</span></span> <span data-ttu-id="ecd19-116">您还可以通过键入以下 URL，直接从 web 浏览器打开响应组配置工具： <STRONG>https://</STRONG>&lt;webPoolFqdn&gt;<STRONG>/RgsConfig</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="ecd19-116">You can also open the Response Group Configuration Tool directly from a web browser by typing the following URL: <STRONG>https://</STRONG>&lt;webPoolFqdn&gt;<STRONG>/RgsConfig</STRONG>.</span></span>

    
    </div>

6.  <span data-ttu-id="ecd19-117">请执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="ecd19-117">Do one of the following:</span></span>
    
      - <span data-ttu-id="ecd19-118">在“创建新的工作流”\*\*\*\* 下，单击“交互”\*\*\*\* 旁边的“创建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ecd19-118">Under **Create a New Workflow**, next to **Interactive**, click **Create**.</span></span>
    
      - <span data-ttu-id="ecd19-119">在“管理现有工作流”\*\*\*\* 下，找到要更改的工作流，然后在“操作”\*\*\*\* 下，单击“编辑”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ecd19-119">Under **Manage an Existing Workflow**, locate the workflow you want to change, and then under **Action**, click **Edit**.</span></span>

7.  <span data-ttu-id="ecd19-120">如果尚未准备好让用户开始呼叫工作流，请清除“激活工作流”\*\*\*\* 复选框。</span><span class="sxs-lookup"><span data-stu-id="ecd19-120">If you are not ready for users to start calling the workflow, clear the **Activate the workflow** check box.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ecd19-p105">如果要创建托管工作流，则需要选择“激活工作流”<STRONG></STRONG>。在保存活动、托管的工作流之后，可以修改并停用该工作流。</span><span class="sxs-lookup"><span data-stu-id="ecd19-p105">If you are to creating a managed workflow, you need to select <STRONG>Activate the workflow</STRONG>. After you save the active, managed workflow, you can then modify and deactivate it.</span></span>

    
    </div>

8.  <span data-ttu-id="ecd19-123">要允许联盟用户呼叫组，请选中“启用联盟”\*\*\*\* 复选框。</span><span class="sxs-lookup"><span data-stu-id="ecd19-123">To allow federated users to call the group, select the **Enable for federation** check box.</span></span> <span data-ttu-id="ecd19-124">您还必须具有一个适用于为联合配置的响应组应用程序的外部访问策略。</span><span class="sxs-lookup"><span data-stu-id="ecd19-124">You must also have an external access policy that applies to the Response Group application configured for federation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ecd19-125">全局外部访问策略适用于响应组应用程序。</span><span class="sxs-lookup"><span data-stu-id="ecd19-125">The global external access policy applies to the Response Group application.</span></span> <span data-ttu-id="ecd19-126">您可以使用 Lync Server 控制面板或使用<STRONG>set-csexternalaccesspolicy</STRONG> Cmdlet 将 EnableOutsideAccess 参数设置为 True，从而为响应组联盟配置全局策略。</span><span class="sxs-lookup"><span data-stu-id="ecd19-126">You can configure the global policy for response group federation by using Lync Server Control Panel or by using the <STRONG>Set-CsExternalAccessPolicy</STRONG> cmdlet to set the EnableOutsideAccess parameter to True.</span></span> <span data-ttu-id="ecd19-127">请记住，除非为全局策略设置分配站点或用户策略，否则这些设置适用于所有用户。</span><span class="sxs-lookup"><span data-stu-id="ecd19-127">Keep in mind that global policy settings apply to all users unless they are assigned a site or user policy.</span></span> <span data-ttu-id="ecd19-128">因此，在针对响应组更改此设置之前，请确保联盟设置满足您的组织的要求。</span><span class="sxs-lookup"><span data-stu-id="ecd19-128">Therefore, before changing this setting for response groups, make sure that the federation setting meets the requirements of your organization.</span></span> <span data-ttu-id="ecd19-129">有关如何将策略应用于用户的详细信息，请参阅<A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">在 Lync Server 2013 中管理外部访问策略</A>。</span><span class="sxs-lookup"><span data-stu-id="ecd19-129">For details about how policies apply to users, see <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">Manage external access policy in Lync Server 2013</A>.</span></span> <span data-ttu-id="ecd19-130">有关联合身份验证设置的详细信息，请参阅 Lync Server Management Shell 文档中的<STRONG>set-csexternalaccesspolicy</STRONG> 。</span><span class="sxs-lookup"><span data-stu-id="ecd19-130">For details about the federation setting, see <STRONG>Set-CsExternalAccessPolicy</STRONG> in Lync Server Management Shell documentation.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ecd19-131">Lync Online 中托管的用户不能将呼叫放到托管在本地部署中的响应组。</span><span class="sxs-lookup"><span data-stu-id="ecd19-131">Users who are hosted in Lync Online can’t place calls to response groups that are hosted in an on-premise deployment.</span></span> <span data-ttu-id="ecd19-132">这在混合部署和本地部署与 Lync Online 部署联合的情况下都是如此。</span><span class="sxs-lookup"><span data-stu-id="ecd19-132">This is true in both hybrid deployments and in cases where an on-premise deployment is federated with a Lync Online deployment.</span></span>

    
    </div>

9.  <span data-ttu-id="ecd19-133">要在呼叫过程中隐藏代理身份，请选中“启用代理匿名”\*\*\*\* 复选框。</span><span class="sxs-lookup"><span data-stu-id="ecd19-133">To hide the identity of agents during calls, select the **Enable agent anonymity** check box.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ecd19-134">尽管建立呼叫后，代理或呼叫者可以添加即时消息 (IM) 和视频，但匿名呼叫无法启动 IM 或视频。</span><span class="sxs-lookup"><span data-stu-id="ecd19-134">Anonymous calls cannot start with instant messaging (IM) or video, although the agent or the caller can add IM and video after the call is established.</span></span> <span data-ttu-id="ecd19-135">匿名代理还可以将呼叫置于保持状态、转接呼叫（盲转接和咨询转接）、寄存和取回呼叫。</span><span class="sxs-lookup"><span data-stu-id="ecd19-135">An anonymous agent can also put calls on hold, transfer calls (both blind and consultative transfers), and park and retrieve calls.</span></span> <span data-ttu-id="ecd19-136">匿名呼叫不支持会议、应用程序共享和桌面共享、文件传输、白板、数据协作和呼叫记录。</span><span class="sxs-lookup"><span data-stu-id="ecd19-136">Anonymous calls do not support conferencing, application sharing and desktop sharing, file transfer, whiteboarding and data collaboration, and call recording.</span></span> <span data-ttu-id="ecd19-137">使用 Lync VDI 插件的代理可以以匿名方式接收传入呼叫，但不能以匿名方式发出传出呼叫。</span><span class="sxs-lookup"><span data-stu-id="ecd19-137">Agents using the Lync VDI Plugin can receive incoming calls anonymously, but they cannot make outgoing calls anonymously.</span></span>

    
    </div>

10. <span data-ttu-id="ecd19-138">在“输入将接收呼叫的组的地址”\*\*\*\* 下，键入将应答工作流呼叫的组的主 SIP 统一资源标识符 (URI) 地址。</span><span class="sxs-lookup"><span data-stu-id="ecd19-138">Under **Enter the address of the group that will receive the calls**, type the primary SIP uniform resource identifier (URI) address of the group that will answer calls to the workflow.</span></span>

11. <span data-ttu-id="ecd19-139">在“显示名称”\*\*\*\* 中，键入希望显示的工作流名称（例如，销售 IVR 响应组）。</span><span class="sxs-lookup"><span data-stu-id="ecd19-139">In **Display name**, type the name that you want to display for the workflow (for example, Sales IVR Response Group).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ecd19-140">不要在显示名称中&lt;包含 ""&gt;或 "" 字符。</span><span class="sxs-lookup"><span data-stu-id="ecd19-140">Do not include the "&lt;" or "&gt;" characters in the display name.</span></span> <span data-ttu-id="ecd19-141">不要使用以下保留的显示名称：RGS Presence Watcher 或 Announcement Service。</span><span class="sxs-lookup"><span data-stu-id="ecd19-141">Do not use the following display names because they are reserved: RGS Presence Watcher or Announcement Service.</span></span>

    
    </div>

12. <span data-ttu-id="ecd19-142">在“电话号码”\*\*\*\* 中，键入响应组的线路 URI（例如，+14255550165）。</span><span class="sxs-lookup"><span data-stu-id="ecd19-142">In **Telephone number**, type the line URI for the response group (for example, +14255550165).</span></span>

13. <span data-ttu-id="ecd19-143">在“显示号码”\*\*\*\* 中，键入希望显示的响应组号码（例如，+1 (425) 555-0165）。</span><span class="sxs-lookup"><span data-stu-id="ecd19-143">In **Display number**, type the number as you want it to appear for the response group (for example, +1 (425) 555-0165).</span></span>

14. <span data-ttu-id="ecd19-144">Optional在 "**说明**" 中，键入要在 Lync 客户端中的联系人卡片上显示的工作流的说明。</span><span class="sxs-lookup"><span data-stu-id="ecd19-144">(Optional) In **Description**, type a description for the workflow that you want to appear on the contact card in the Lync client.</span></span>

15. <span data-ttu-id="ecd19-145">如果工作流将由响应组管理员进行管理，则在“工作流类型”\*\*\*\* 中，选择“受管理”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ecd19-145">In **Workflow Type**, select **Managed** if this workflow will be managed by a Response Group Manager.</span></span> <span data-ttu-id="ecd19-146">执行以下操作可向工作流分配响应组管理员：</span><span class="sxs-lookup"><span data-stu-id="ecd19-146">Do the following to assign Response Group Managers to the workflow:</span></span>
    
    1.  <span data-ttu-id="ecd19-147">键入此工作流的管理员的 SIP URI，然后单击“添加”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ecd19-147">Type the SIP URI of a manager for this workflow, and click **Add**..</span></span>
    
    2.  <span data-ttu-id="ecd19-148">键入要添加到工作流的其他管理员的 SIP URI，然后单击“添加”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ecd19-148">Type the SIP URI of additional managers to add to the workflow, and click **Add**..</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="ecd19-p112">必须为被指定为响应组管理员的每一位用户分配 CsResponseGroupManager 角色。如果没有为用户分配此角色，他们无法管理响应组。</span><span class="sxs-lookup"><span data-stu-id="ecd19-p112">Every user who is designated as a manager of a response group must be assigned the CsResponseGroupManager role. If users are not assigned this role, they cannot manage response groups.</span></span>

    
    </div>

16. <span data-ttu-id="ecd19-151">在“步骤 2 选择语言”\*\*\*\* 下，单击要用于语音识别和文本到语音转换的语言。</span><span class="sxs-lookup"><span data-stu-id="ecd19-151">Under **Step 2 Select a Language**, click the language to use for speech recognition and text-to-speech.</span></span>

17. <span data-ttu-id="ecd19-152">如果要配置欢迎消息，请在“步骤 3 配置欢迎消息”\*\*\*\* 下选中“播放欢迎消息”\*\*\*\* 复选框，然后执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="ecd19-152">If you want to configure a welcome message, under **Step 3 Configure a Welcome Message**, select the **Play a welcome message** check box, and then do one of the following:</span></span>
    
      - <span data-ttu-id="ecd19-153">要为呼叫者输入转换成语音的文本形式的欢迎消息，请单击“使用文本到语音转换”\*\*\*\*，然后在文本框中键入欢迎消息。</span><span class="sxs-lookup"><span data-stu-id="ecd19-153">To enter the welcome message as text that is converted to speech for callers, click **Use text-to-speech**, and then type the welcome message in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="ecd19-154">不要在输入的文本中包含 HTML 标记。</span><span class="sxs-lookup"><span data-stu-id="ecd19-154">Do not include HTML tags in the text you enter.</span></span> <span data-ttu-id="ecd19-155">如果包含 HTML 标记，您将收到一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="ecd19-155">If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
    
      - <span data-ttu-id="ecd19-p114">要使用 Wave 或 Windows Media 音频文件录音作为欢迎消息，请单击“选择录音”\*\*\*\*。如果要上载新的音频文件，请单击“录音”\*\*\*\* 链接。在新浏览器窗口中，单击“浏览”\*\*\*\*，选择要使用的音频文件，然后单击“打开”\*\*\*\*。单击“上载”\*\*\*\*，加载该音频文件。</span><span class="sxs-lookup"><span data-stu-id="ecd19-p114">To use a Wave or Windows Media Audio file recording for the welcome message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the audio file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="ecd19-160">用户提供的所有音频文件都必须满足特定要求。</span><span class="sxs-lookup"><span data-stu-id="ecd19-160">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="ecd19-161">有关受支持的文件格式的详细信息，请参阅<A href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013 中响应组的技术要求</A>。</span><span class="sxs-lookup"><span data-stu-id="ecd19-161">For details about supported file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

18. <span data-ttu-id="ecd19-162">在“步骤 4 指定您的工作时间”\*\*\*\* 下的“您所在的时区”\*\*\*\* 框中，单击工作流的时区。</span><span class="sxs-lookup"><span data-stu-id="ecd19-162">Under **Step 4 Specify Your Business Hours**, in the **Your time zone** box, click the time zone of the workflow.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ecd19-p116">该时区是工作流的呼叫者和代理所在的时区。它用于计算开放和关闭的时间点。例如，如果将工作流配置为使用北美东部时间的时区，并安排工作流在上午 7:00 开放，晚上 11:00 关闭，则得出的开放和关闭时间点分别为东部时间 7:00 和东部时间 11:00:00。（必须以 24 小时制输入时间。）</span><span class="sxs-lookup"><span data-stu-id="ecd19-p116">The time zone is the time zone where the callers and agents of the workflow reside. It is used to calculate the open and close hours. For example, if the workflow is configured to use the North American Eastern Time zone and the workflow is scheduled to open at 7:00 A.M. and close at 11:00 P.M., the open and close times are assumed to be 7:00 Eastern Time and 11:00 Eastern Time respectively. (You must enter the times in 24-hour time notation.)</span></span>

    
    </div>

19. <span data-ttu-id="ecd19-168">通过执行下列操作之一选择要使用的工作时间日程表类型：</span><span class="sxs-lookup"><span data-stu-id="ecd19-168">Select the type of business hours schedule you want to use by doing one of the following:</span></span>
    
      - <span data-ttu-id="ecd19-169">要使用预定义工作时间日程表，请单击“使用预设日程表”\*\*\*\*，然后从下拉列表中选择要使用的日程表。</span><span class="sxs-lookup"><span data-stu-id="ecd19-169">To use a predefined schedule of business hours, click **Use a preset schedule**, and then select the schedule you want to use from the drop-down list.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="ecd19-170">之前您必须至少已定义一个预设日程表才能选择该选项。</span><span class="sxs-lookup"><span data-stu-id="ecd19-170">You must have defined at least one preset schedule previously to be able to select this option.</span></span> <span data-ttu-id="ecd19-171">可使用 <STRONG>New-CSRgsHoursOfBusiness</STRONG> cmdlet 来定义预设日程表。</span><span class="sxs-lookup"><span data-stu-id="ecd19-171">You define preset schedules by using the <STRONG>New-CSRgsHoursOfBusiness</STRONG> cmdlet.</span></span> <span data-ttu-id="ecd19-172">有关详细信息，请参阅<A href="lync-server-2013-optional-define-response-group-business-hours.md">（可选）在 Lync Server 2013 中定义响应组工作时间</A>。</span><span class="sxs-lookup"><span data-stu-id="ecd19-172">For details, see <A href="lync-server-2013-optional-define-response-group-business-hours.md">(Optional) Define Response Group business hours in Lync Server 2013</A>.</span></span> <span data-ttu-id="ecd19-173">选择预设日程表时，“天”<STRONG></STRONG>、“开放”<STRONG></STRONG>和“关闭”<STRONG></STRONG>中会自动填写响应组可以应答的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="ecd19-173">When you select a preset schedule, <STRONG>Day</STRONG>, <STRONG>Open</STRONG>, and <STRONG>Close</STRONG> are automatically filled with the days and hours that the response group is available.</span></span>

        
        </div>
    
      - <span data-ttu-id="ecd19-174">要使用仅适用于该工作流的自定义日程表，请单击“使用自定义日程表”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ecd19-174">To use a custom schedule that applies only to this workflow, click **Use a custom schedule**.</span></span>

20. <span data-ttu-id="ecd19-175">如果要创建该工作流的自定义日程表，请单击一周中响应组可以应答的日期对应的复选框。</span><span class="sxs-lookup"><span data-stu-id="ecd19-175">If you are creating a custom schedule for this workflow, click the check boxes for the days of the week that the response group is available.</span></span>

21. <span data-ttu-id="ecd19-176">如果要创建自定义日程表，请键入响应组可以应答的“开放”\*\*\*\* 和“关闭”\*\*\*\* 时间点。</span><span class="sxs-lookup"><span data-stu-id="ecd19-176">If you are creating a custom schedule, type the **Open** and **Close** hours when the response group available.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ecd19-p118">“开放”<STRONG></STRONG>和“关闭”<STRONG></STRONG>时间点必须采用 24 小时制。例如，如果营业时间为朝九晚五，其中午餐时间不办公，则工作时间指定为 9:00“开放”<STRONG></STRONG>、12:00“关闭”<STRONG></STRONG>、13:00“开放”<STRONG></STRONG>及 17:00“关闭”<STRONG></STRONG>。</span><span class="sxs-lookup"><span data-stu-id="ecd19-p118">The <STRONG>Open</STRONG> and <STRONG>Close</STRONG> hours must be in 24-hour time notation. For example, if your office works a 9-to-5 work day and closes at noon for lunch, the business hours are specified as <STRONG>Open</STRONG> 9:00, <STRONG>Close</STRONG> 12:00, <STRONG>Open</STRONG> 13:00, and <STRONG>Close</STRONG> 17:00.</span></span>

    
    </div>

22. <span data-ttu-id="ecd19-179">如果要在办公室未开放时播放消息，请选中“响应组在工作时间以外时播放消息”\*\*\*\* 复选框，然后通过执行以下操作之一指定要播放的消息：</span><span class="sxs-lookup"><span data-stu-id="ecd19-179">If you want to play a message when the office is not open, select the **Play a message when the response group is outside of business hours** check box, and then specify the message to play by doing one of the following:</span></span>
    
      - <span data-ttu-id="ecd19-180">要为呼叫者输入转换成语音的文本形式的消息，请单击“使用文本到语音转换”\*\*\*\*，然后在文本框中键入消息。</span><span class="sxs-lookup"><span data-stu-id="ecd19-180">To enter the message as text that is converted to speech for the caller, click **Use text-to-speech**, and then type the message in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="ecd19-p119">不要在输入的文本中包含 HTML 标记，否则将收到错误消息。</span><span class="sxs-lookup"><span data-stu-id="ecd19-p119">Do not include HTML tags in the text you enter. If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
    
      - <span data-ttu-id="ecd19-p120">要使用音频文件录音作为消息，请单击“选择录音”\*\*\*\*。如果要上载新的音频文件，请单击“录音”\*\*\*\* 链接。在新浏览器窗口中，单击“浏览”\*\*\*\*，选择要使用的文件，然后单击“打开”\*\*\*\*。单击“上载”\*\*\*\*，加载该音频文件。</span><span class="sxs-lookup"><span data-stu-id="ecd19-p120">To use an audio file recording for the message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="ecd19-187">用户提供的所有音频文件都必须满足特定要求。</span><span class="sxs-lookup"><span data-stu-id="ecd19-187">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="ecd19-188">有关受支持的文件格式的详细信息，请参阅<A href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013 中响应组的技术要求</A>。</span><span class="sxs-lookup"><span data-stu-id="ecd19-188">For details about supported file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

23. <span data-ttu-id="ecd19-189">指定播放消息后如何处理呼叫（如果配置了消息）：</span><span class="sxs-lookup"><span data-stu-id="ecd19-189">Specify how to handle calls after the message is played (if a message is configured):</span></span>
    
      - <span data-ttu-id="ecd19-190">要断开呼叫，请单击“断开呼叫”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ecd19-190">To disconnect the call, click **Disconnect Call**.</span></span>
    
      - <span data-ttu-id="ecd19-191">要将呼叫转接到语音邮件，请单击“转接到语音邮件”\*\*\*\*，然后键入语音邮件地址。</span><span class="sxs-lookup"><span data-stu-id="ecd19-191">To forward the call to voice mail, click **Forward to voice mail**, and then type the voice mail address.</span></span> <span data-ttu-id="ecd19-192">语音\<邮件地址的格式为用户名\>@\<域名\> （例如，bob@contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="ecd19-192">The format for the voice mail address is \<username\>@\<domainname\> (for example, bob@contoso.com).</span></span>
    
      - <span data-ttu-id="ecd19-193">要将呼叫转接到另一个用户，请单击“转接到 SIP URI”\*\*\*\*，然后键入该用户的地址。</span><span class="sxs-lookup"><span data-stu-id="ecd19-193">To forward the call to another user, click **Forward to SIP URI**, and then type a user address.</span></span> <span data-ttu-id="ecd19-194">用户\<地址的格式为 username\>@\<域名。\></span><span class="sxs-lookup"><span data-stu-id="ecd19-194">The format for the user address is \<username\>@\<domainname\>.</span></span>
    
      - <span data-ttu-id="ecd19-195">要将呼叫转接到另一个电话号码，请单击“转接到电话号码”\*\*\*\*，然后键入该电话号码。</span><span class="sxs-lookup"><span data-stu-id="ecd19-195">To forward the call to another telephone number, click **Forward to telephone number**, and then type the telephone number.</span></span> <span data-ttu-id="ecd19-196">电话\<号码的格式为号码\>@\<域名\> （例如，+ 14255550121@contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="ecd19-196">The format for the telephone number is \<number\>@\<domainname\> (for example, +14255550121@contoso.com).</span></span> <span data-ttu-id="ecd19-197">域名可用来将呼叫者路由至正确的目标。</span><span class="sxs-lookup"><span data-stu-id="ecd19-197">The domain name is used to route the caller to the correct destination.</span></span>

24. <span data-ttu-id="ecd19-198">在“步骤 5 指定您的假日”\*\*\*\* 下，单击定义响应组停止营业日期的一个或多个假日集对应的复选框。</span><span class="sxs-lookup"><span data-stu-id="ecd19-198">Under **Step 5 Specify Your Holidays**, click the check boxes for one or more sets of holidays that define the days when the response group is closed for business.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ecd19-199">配置工作流之前，您需要先定义假日和假日集。</span><span class="sxs-lookup"><span data-stu-id="ecd19-199">You need to define holidays and holiday sets before you configure the workflow.</span></span> <span data-ttu-id="ecd19-200">使用 <STRONG>New-CsRgsHoliday</STRONG> 和 <STRONG>New-CsRgsHolidaySet</STRONG> cmdlet 可定义假日和假日集。</span><span class="sxs-lookup"><span data-stu-id="ecd19-200">Use the <STRONG>New-CsRgsHoliday</STRONG> and <STRONG>New-CsRgsHolidaySet</STRONG> cmdlets to define holidays and holiday sets.</span></span> <span data-ttu-id="ecd19-201">有关详细信息，请参阅<A href="lync-server-2013-optional-define-response-group-holiday-sets.md">（可选）在 Lync Server 2013 中定义响应组假日集</A>。</span><span class="sxs-lookup"><span data-stu-id="ecd19-201">For details, see <A href="lync-server-2013-optional-define-response-group-holiday-sets.md">(Optional) Define Response Group holiday sets in Lync Server 2013</A>.</span></span>

    
    </div>

25. <span data-ttu-id="ecd19-202">如果要在假日播放消息，请选中“假期播放消息”\*\*\*\* 复选框，然后通过执行以下操作之一指定要播放的消息：</span><span class="sxs-lookup"><span data-stu-id="ecd19-202">If you want to play a message on holidays, select the **Play a message during holidays** check box, and then specify the message to play by doing one of the following:</span></span>
    
      - <span data-ttu-id="ecd19-203">要为呼叫者输入转换成语音的文本形式的消息，请单击“使用文本到语音转换”\*\*\*\*，然后在文本框中键入消息。</span><span class="sxs-lookup"><span data-stu-id="ecd19-203">To enter the message as text that is converted to speech for the caller, click **Use text-to-speech**, and then type the message in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="ecd19-p126">不要在输入的文本中包含 HTML 标记，否则将收到错误消息。</span><span class="sxs-lookup"><span data-stu-id="ecd19-p126">Do not include HTML tags in the text you enter. If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
    
      - <span data-ttu-id="ecd19-p127">要使用音频文件录音作为消息，请单击“选择录音”\*\*\*\*。如果要上载新的音频文件，请单击“录音”\*\*\*\* 链接。在新浏览器窗口中，单击“浏览”\*\*\*\*，选择要使用的文件，然后单击“打开”\*\*\*\*。单击“上载”\*\*\*\*，加载该音频文件。</span><span class="sxs-lookup"><span data-stu-id="ecd19-p127">To use an audio file recording for the message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="ecd19-210">用户提供的所有音频文件都必须满足特定要求。</span><span class="sxs-lookup"><span data-stu-id="ecd19-210">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="ecd19-211">有关受支持的音频文件格式的详细信息，请参阅<A href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013 中响应组的技术要求</A>。</span><span class="sxs-lookup"><span data-stu-id="ecd19-211">For details about supported audio file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

26. <span data-ttu-id="ecd19-212">指定播放消息后如何处理呼叫（如果配置了消息）：</span><span class="sxs-lookup"><span data-stu-id="ecd19-212">Specify how to handle calls after the message is played (if a message is configured):</span></span>
    
      - <span data-ttu-id="ecd19-213">要断开呼叫，请单击“断开呼叫”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ecd19-213">To disconnect the call, click **Disconnect Call**.</span></span>
    
      - <span data-ttu-id="ecd19-214">要将呼叫转接到语音邮件，请单击“转接到语音邮件”\*\*\*\*，然后键入语音邮件地址。</span><span class="sxs-lookup"><span data-stu-id="ecd19-214">To forward the call to voice mail, click **Forward to voice mail**, and then type the voice mail address.</span></span> <span data-ttu-id="ecd19-215">语音\<邮件地址的格式为用户名\>@\<域名\> （例如，bob@contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="ecd19-215">The format for the voice mail address is \<username\>@\<domainname\> (for example, bob@contoso.com).</span></span>
    
      - <span data-ttu-id="ecd19-216">要将呼叫转接到另一个用户，请单击“转接到 SIP URI”\*\*\*\*，然后键入该用户的地址。</span><span class="sxs-lookup"><span data-stu-id="ecd19-216">To forward the call to another user, click **Forward to SIP URI**, and then type a user address.</span></span> <span data-ttu-id="ecd19-217">用户\<地址的格式为 username\>@\<域名。\></span><span class="sxs-lookup"><span data-stu-id="ecd19-217">The format for the user address is \<username\>@\<domainname\>.</span></span>
    
      - <span data-ttu-id="ecd19-218">要将呼叫转接到另一个电话号码，请单击“转接到电话号码”\*\*\*\*，然后键入该电话号码。</span><span class="sxs-lookup"><span data-stu-id="ecd19-218">To forward the call to another telephone number, click **Forward to telephone number**, and then type the telephone number.</span></span> <span data-ttu-id="ecd19-219">电话\<号码的格式为号码\>@\<域名\> （例如，+ 14255550121@contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="ecd19-219">The format for the telephone number is \<number\>@\<domainname\> (for example, +14255550121@contoso.com).</span></span> <span data-ttu-id="ecd19-220">域名可用来将呼叫者路由至正确的目标。</span><span class="sxs-lookup"><span data-stu-id="ecd19-220">The domain name is used to route the caller to the correct destination.</span></span>

27. <span data-ttu-id="ecd19-221">在“步骤 6 配置保持音乐”\*\*\*\* 下，执行以下操作之一，选择希望呼叫者在等待代理时听到的音乐：</span><span class="sxs-lookup"><span data-stu-id="ecd19-221">Under **Step 6 Configure Music on Hold**, choose what you want callers to listen to while waiting for an agent by doing one of the following:</span></span>
    
      - <span data-ttu-id="ecd19-222">要使用默认保持音乐录音，请单击“使用默认值”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ecd19-222">To use the default music on-hold recording, click **Use default**.</span></span>
    
      - <span data-ttu-id="ecd19-p132">要使用音频文件录音作为保持音乐，请单击“选择音乐文件”\*\*\*\*。如果要上载新的音频文件，请单击“音乐文件”\*\*\*\* 链接。在新浏览器窗口中，单击“浏览”\*\*\*\*，选择要使用的文件，然后单击“打开”\*\*\*\*。单击“上载”\*\*\*\*，加载该音频文件。</span><span class="sxs-lookup"><span data-stu-id="ecd19-p132">To use an audio file recording for the on-hold music, click **Select a music file**. If you want to upload a new audio file, click the **a music file** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="ecd19-227">用户提供的所有音频文件都必须满足特定要求。</span><span class="sxs-lookup"><span data-stu-id="ecd19-227">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="ecd19-228">有关受支持的文件格式的详细信息，请参阅<A href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013 中响应组的技术要求</A>。</span><span class="sxs-lookup"><span data-stu-id="ecd19-228">For details about supported file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

28. <span data-ttu-id="ecd19-229">在“步骤 7 配置互动语音响应”\*\*\*\* 下的“用户将听到以下文本或录制的消息”\*\*\*\* 标题中，指定要向呼叫者提出的问题，具体操作如下所示：</span><span class="sxs-lookup"><span data-stu-id="ecd19-229">Under **Step 7 Configure Interactive Voice Response**, under the **The user will hear the following text or recorded message** heading, specify the question to ask callers as follows:</span></span>
    
      - <span data-ttu-id="ecd19-230">要输入文本格式的问题，请单击“使用文本到语音转换”\*\*\*\*，然后在文本框中键入问题。</span><span class="sxs-lookup"><span data-stu-id="ecd19-230">To enter the question in text format, click **Use text-to-speech**, and type the question in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="ecd19-p134">不要在输入的文本中包含 HTML 标记，否则将收到错误消息。</span><span class="sxs-lookup"><span data-stu-id="ecd19-p134">Do not include HTML tags in the text you enter. If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="ecd19-233">文本到语音转换引擎会将符号“#”转换为“号码”这个词。</span><span class="sxs-lookup"><span data-stu-id="ecd19-233">The "#" symbol is translated by the text-to-speech engine as the word "number".</span></span> <span data-ttu-id="ecd19-234">如果需要指代 # 键，则应该在提示语中使用键名代替符号。</span><span class="sxs-lookup"><span data-stu-id="ecd19-234">If you need to refer to the # key, you should use the key name, rather than the symbol, in your prompt.</span></span> <span data-ttu-id="ecd19-235">例如，“要与销售人员交谈，请按井号键”。</span><span class="sxs-lookup"><span data-stu-id="ecd19-235">For example, "To talk to sales, press the pound key."</span></span>

        
        </div>
    
      - <span data-ttu-id="ecd19-p136">要使用预先录制的包含问题的音频文件，请单击“选择录音”\*\*\*\*，然后单击“录音”\*\*\*\* 链接以上载该文件。在新浏览器窗口中，单击“浏览”\*\*\*\*，选择所需音频文件，然后单击“打开”\*\*\*\*。单击“上载”\*\*\*\* 加载该文件，然后可以选择在文本框中键入问题。这样便可将问题及呼叫者的响应转接到响应代理。</span><span class="sxs-lookup"><span data-stu-id="ecd19-p136">To use a prerecorded audio file that contains the question, click **Select a recording**, and then click the **a recording** link to upload the file. In the new browser window, click **Browse**, select the audio file, and then click **Open**. Click **Upload** to load the file, and then optionally you can type the question in the text box (this enables the question, and the caller’s response, to be forwarded to the responding agent).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="ecd19-239">用户提供的所有音频文件都必须满足特定要求。</span><span class="sxs-lookup"><span data-stu-id="ecd19-239">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="ecd19-240">有关受支持的文件格式的详细信息，请参阅<A href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013 中响应组的技术要求</A>。</span><span class="sxs-lookup"><span data-stu-id="ecd19-240">For details about supported file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

29. <span data-ttu-id="ecd19-241">在“响应 1”\*\*\*\* 下，指定第一个可能的问题答案，具体操作如下：</span><span class="sxs-lookup"><span data-stu-id="ecd19-241">Under **Response 1**, specify the first possible answer to the question by doing the following:</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="ecd19-p138">不要在任何语音响应中使用引号 (")。引号会导致 IVR 失败。</span><span class="sxs-lookup"><span data-stu-id="ecd19-p138">Do not use quotation marks (") in any voice responses. Quotation marks cause the IVR to fail.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ecd19-244">可以选择允许呼叫者使用语音、字母数字键盘输入或同时使用两者进行回答。</span><span class="sxs-lookup"><span data-stu-id="ecd19-244">You can choose to allow callers to answer using speech, alphanumeric keypad input, or both.</span></span>

    
    </div>
    
      - <span data-ttu-id="ecd19-245">如果要允许呼叫者使用语音进行响应，请在“输入语音响应”\*\*\*\* 中输入答案。</span><span class="sxs-lookup"><span data-stu-id="ecd19-245">If you want to allow the caller to respond using speech, enter the answer in **Enter a voice response**.</span></span>
    
      - <span data-ttu-id="ecd19-246">如果要允许呼叫者通过按小键盘上的键进行响应，请在“数字”\*\*\*\* 中单击小键盘的数字。</span><span class="sxs-lookup"><span data-stu-id="ecd19-246">If you want to allow the caller to respond by pressing a key on the keypad, in **Digit**, click the keypad digit.</span></span>

30. <span data-ttu-id="ecd19-247">指定将呼叫者路由至队列，还是提出其他问题，如下所示：</span><span class="sxs-lookup"><span data-stu-id="ecd19-247">Specify whether to route the caller to a queue, or to ask another question as follows:</span></span>
    
      - <span data-ttu-id="ecd19-248">要将呼叫者路由至某个队列，请单击“发送到队列”\*\*\*\*，然后在“选择队列”\*\*\*\* 中单击要使用的队列。</span><span class="sxs-lookup"><span data-stu-id="ecd19-248">To route the caller to a queue, click **Send to a queue**, and in **Select a queue**, click the queue that you want to use.</span></span>
    
      - <span data-ttu-id="ecd19-p139">要提出其他问题，请单击“提出其他问题”\*\*\*\*，然后单击“使用文本到语音转换”\*\*\*\* 并键入问题，或单击“选择录音”\*\*\*\*。使用本节中的响应分组指定其他问题的可能响应（最多四个），以及用于每个响应的队列。要指定第三个或第四个可能的响应，请单击“响应 3”\*\*\*\* 或“响应 4”\*\*\*\* 复选框。</span><span class="sxs-lookup"><span data-stu-id="ecd19-p139">To ask another question, click **Ask another question**, and then click **Use text-to-speech** and type the question, or click **Select a recording**. Use the response groupings in this section to specify up to four possible responses to the additional question and the queue to use for each response. To specify a third or fourth possible response, click the **Response 3** check box or the **Response 4** check box.</span></span>

31. <span data-ttu-id="ecd19-p140">通过重复步骤 28 和 29 为原题指定多达三个以上可能的答案，以指定可能的响应以及对于每个响应要采取的操作。要指定第三个或第四个可能的答案，请单击“响应 3”\*\*\*\* 或“响应 4”\*\*\*\* 复选框。</span><span class="sxs-lookup"><span data-stu-id="ecd19-p140">Specify up to three more possible answers to the original question by repeating steps 28 and 29 to specify the possible responses and the action to take for each response. To specify a third or fourth possible answer, click the **Response 3** check box or the **Response 4** check box.</span></span>

32. <span data-ttu-id="ecd19-254">单击“部署”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ecd19-254">Click **Deploy**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-an-interactive-workflow"></a><span data-ttu-id="ecd19-255">使用 Windows PowerShell 创建或修改交互式工作流</span><span class="sxs-lookup"><span data-stu-id="ecd19-255">To use Windows PowerShell to create or modify an Interactive workflow</span></span>

1.  <span data-ttu-id="ecd19-256">以 RTCUniversalServerAdmins 组成员的身份登录，或以支持响应组的预定义管理角色之一的成员身份登录。</span><span class="sxs-lookup"><span data-stu-id="ecd19-256">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="ecd19-257">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ecd19-257">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="ecd19-p141">检索响应组服务的服务名称，并将其分配给变量。在命令行中运行：</span><span class="sxs-lookup"><span data-stu-id="ecd19-p141">Retrieve the service name for the Response Group service and assign it to a variable. At the command line, run:</span></span>
    
        $serviceId="service:"+(Get-CSService | ?{$_.Applications -like "*RGS*"}).ServiceId;

4.  <span data-ttu-id="ecd19-p142">互动工作流需要两个或多个队列，以及两个或多个代理组。首先，创建代理组。运行：</span><span class="sxs-lookup"><span data-stu-id="ecd19-p142">An interactive workflow requires two or more queues and two or more agent groups. First, create the agent groups. Run:</span></span>
    
        $AGSupport = New-CsRgsAgentGroup -Parent $serviceId -Name "Technical Support" [-AgentAlertTime "20"] [-ParticipationPolicy "Informal"] [-RoutingMethod LongestIdle] [-AgentsByUri("sip:agent1@contoso.com", "sip:agent2@contoso.com")]
        $AGSales = New-CsRgsAgentGroup -Parent $serviceId -Name "Sales Team" [-AgentAlertTime "20"] [-ParticipationPolicy "Informal"] [-RoutingMethod LongestIdle] [-AgentsByUri("sip:bob@contoso.com", "sip:alice@contoso.com")]

5.  <span data-ttu-id="ecd19-p143">创建队列。运行：</span><span class="sxs-lookup"><span data-stu-id="ecd19-p143">Create the queues. Run:</span></span>
    
        $QSupport = New-CsRgsQueue -Parent $ServiceId -Name "Contoso Support" -AgentGroupIDList($AG-Support.Identity)
        $QSales = New-CsRgsQueue -Parent $ServiceId -Name "Contoso Sales" -AgentGroupIDList($AG-Sales.Identity)

6.  <span data-ttu-id="ecd19-p144">创建第一个响应组提示。运行：</span><span class="sxs-lookup"><span data-stu-id="ecd19-p144">Create the first response group prompt. Run:</span></span>
    
        $SupportPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Please be patient while we connect you with Contoso Technical Support."

7.  <span data-ttu-id="ecd19-p145">然后，创建在提示后要执行的操作。运行：</span><span class="sxs-lookup"><span data-stu-id="ecd19-p145">Then create the action to be performed after the prompt. Run:</span></span>
    
        $SupportAction = New-CsRgsCallAction -Prompt $SupportPrompt -Action TransferToQueue -QueueID $QSupport.Identity

8.  <span data-ttu-id="ecd19-p146">创建第一个响应组应答。运行：</span><span class="sxs-lookup"><span data-stu-id="ecd19-p146">Create the first response group answer. Run:</span></span>
    
        $SupportAnswer = New-CsRgsAnswer -Action $SupportAction [-DtmfResponse 1]

9.  <span data-ttu-id="ecd19-p147">现在，创建第二个提示、呼叫操作和应答。首先创建提示。运行：</span><span class="sxs-lookup"><span data-stu-id="ecd19-p147">Now create the second prompt, call action, and answer. First create the prompt. Run:</span></span>
    
        $SalesPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Please hold while we connect you with Contoso Sales."

10. <span data-ttu-id="ecd19-p148">创建第二个呼叫操作。运行：</span><span class="sxs-lookup"><span data-stu-id="ecd19-p148">Create the second call action. Run:</span></span>
    
        $SalesAction = New-CsRgsCallAction -Prompt $SalesPrompt -Action TransferToQueue -QueueID $QSales.Identity

11. <span data-ttu-id="ecd19-p149">创建第二个响应组应答。运行：</span><span class="sxs-lookup"><span data-stu-id="ecd19-p149">Create the second response group answer. Run:</span></span>
    
        $SalesAnswer = New-CsRgsAnswer -Action $SalesAction [-DtmfResponse 2]

12. <span data-ttu-id="ecd19-p150">创建顶级提示。运行：</span><span class="sxs-lookup"><span data-stu-id="ecd19-p150">Create the top-level prompt. Run:</span></span>
    
        $TopLevelPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Thank you for calling Contoso. For Technical Support, press 1. For a Sales Representative, press 2."

13. <span data-ttu-id="ecd19-p151">创建顶级问题。运行：</span><span class="sxs-lookup"><span data-stu-id="ecd19-p151">Create the top-level question. Run:</span></span>
    
        $TopLevelQuestion = New-CsRgsQuestion -Prompt $TopLevelPrompt [-AnswerList ($SupportAnswer, $SalesAnswer)]

14. <span data-ttu-id="ecd19-p152">现在，创建工作流。运行：</span><span class="sxs-lookup"><span data-stu-id="ecd19-p152">Now create the workflow. Run:</span></span>
    
        $IVRAction = New-CsRgsCallAction -Action TransferToQuestion [-Question $Question]
        $IVRWorkflow = New-CsRgsWorkflow -Parent $ServiceId -Name "Contoso Helpdesk" [-Description "The Contoso Helpdesk line."] -PrimaryUri "sip:helpdesk@contoso.com" [-LineUri tel:+14255554321] [-DisplayNumber "+1 (425) 555-4321"] [-Active $true] [-Anonymous $true] [-DefaultAction $IVRAction] [-Managed $true] [-ManagersByURI ("sip:mindy@contoso.com", "sip:bob@contoso.com")]
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ecd19-p153">必须为被指定为响应组管理员的所有用户分配 CsResponseGroupManager 角色。如果没有为用户分配此角色，他们无法管理响应组。</span><span class="sxs-lookup"><span data-stu-id="ecd19-p153">All users who have been designated as manager of a response group must be assigned th CsResponseGroupManager role. If users are not assigned this role, they cannot manage response groups.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

