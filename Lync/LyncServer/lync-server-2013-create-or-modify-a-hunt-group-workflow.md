---
title: Lync Server 2013：创建或修改智能寻线工作流
description: Lync Server 2013：创建或修改智能寻线工作流。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a hunt group workflow
ms:assetid: dcb9effb-5d12-4dee-80fc-ab9654222d5a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205321(v=OCS.15)
ms:contentKeyID: 48185596
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 95f6374352c87d13b1e5c09bcef267059016eae0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570718"
---
# <a name="create-or-modify-a-hunt-group-workflow-in-lync-server-2013"></a><span data-ttu-id="a3fa9-103">在 Lync Server 2013 中创建或修改智能寻线工作流</span><span class="sxs-lookup"><span data-stu-id="a3fa9-103">Create or modify a hunt group workflow in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a3fa9-104">_**上次修改的主题：** 2013-09-11_</span><span class="sxs-lookup"><span data-stu-id="a3fa9-104">_**Topic Last Modified:** 2013-09-11_</span></span>

<span data-ttu-id="a3fa9-105">使用以下过程之一可创建或修改智能寻线工作流。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-105">Use one of the following procedures to create or modify a hunt group workflow.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a3fa9-106">您可以使用 Lync Server 命令行管理程序或响应组配置工具来创建和修改智能寻线工作流。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-106">You can use Lync Server Management Shell or the Response Group Configuration Tool to create and modify hunt group workflows.</span></span> <span data-ttu-id="a3fa9-107">您可以从 Lync Server 控制面板访问响应组配置工具，也可以通过键入以下 URL 直接从 web 浏览器打开网页： <STRONG>Https://</STRONG> &lt; webPoolFqdn &gt; <STRONG>/RgsConfig</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-107">You can access the Response Group Configuration Tool from Lync Server Control Panel, or by opening the webpage directly from a web browser by typing the following URL: <STRONG>https://</STRONG>&lt;webPoolFqdn&gt;<STRONG>/RgsConfig</STRONG>.</span></span>



</div>

<div>

## <a name="to-use-response-group-configuration-tool-to-create-or-modify-a-hunt-group-workflow"></a><span data-ttu-id="a3fa9-108">使用响应组配置工具创建或修改智能寻线工作流</span><span class="sxs-lookup"><span data-stu-id="a3fa9-108">To use Response Group Configuration Tool to create or modify a hunt group workflow</span></span>

1.  <span data-ttu-id="a3fa9-109">以 RTCUniversalServerAdmins 组成员的身份登录，或以支持响应组的预定义管理角色之一的成员身份登录。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-109">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="a3fa9-110">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a3fa9-111">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="a3fa9-112">在左侧导航栏中，单击“响应组”\*\*\*\*，然后单击“工作流”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-112">In the left navigation bar, click **Response Groups**, and then click **Workflow**.</span></span>

4.  <span data-ttu-id="a3fa9-113">在“工作流”\*\*\*\* 页上，单击“创建或编辑工作流”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-113">On the **Workflow** page, click **Create or edit a workflow**.</span></span>

5.  <span data-ttu-id="a3fa9-114">在 " **选择服务** 搜索" 字段中，键入承载要创建或更改的工作流的 **ApplicationServer** 服务的全部或部分名称。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-114">In the **Select a Service** search field, type all or part of the name of the **ApplicationServer** service that hosts the workflow that you want to create or change.</span></span> <span data-ttu-id="a3fa9-115">在服务结果列表中，单击想要的服务，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-115">In the resulting list of services, click the service that you want, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a3fa9-116">将打开 "响应组配置" 工具。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-116">The Response Group Configuration Tool opens.</span></span> <span data-ttu-id="a3fa9-117">您还可以通过键入以下 URL，直接从 web 浏览器打开响应组配置工具： <STRONG>Https://</STRONG> &lt; webPoolFqdn &gt; <STRONG>/RgsConfig</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-117">You can also open the Response Group Configuration Tool directly from a web browser by typing the following URL: <STRONG>https://</STRONG>&lt;webPoolFqdn&gt;<STRONG>/RgsConfig</STRONG>.</span></span>

    
    </div>

6.  <span data-ttu-id="a3fa9-118">执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="a3fa9-118">Do one of the following:</span></span>
    
      - <span data-ttu-id="a3fa9-119">在“创建新的工作流”\*\*\*\* 下，单击“智能寻线”\*\*\*\* 旁边的“创建”。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-119">Under **Create a New Workflow**, next to **Hunt Group, click Create**.</span></span>
    
      - <span data-ttu-id="a3fa9-120">在“管理现有工作流”\*\*\*\* 下，找到要更改的工作流，然后在“操作”\*\*\*\* 下，单击“编辑”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-120">Under **Manage an Existing Workflow**, locate the workflow you want to change, and then under **Action**, click **Edit**.</span></span>

7.  <span data-ttu-id="a3fa9-121">如果你已准备好让用户开始呼叫工作流，请选择 **"激活工作流"**。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-121">If you are ready for users to start calling the workflow, select **Activate the workflow**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a3fa9-p105">如果要创建托管工作流，则需要选择“激活工作流”<STRONG></STRONG>。在保存活动、托管的工作流之后，可以修改并停用该工作流。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-p105">If you are to creating a managed workflow, you need to select <STRONG>Activate the workflow</STRONG>. After you save the active, managed workflow, you can then modify and deactivate it.</span></span>

    
    </div>

8.  <span data-ttu-id="a3fa9-124">要允许联盟用户呼叫组，请选中“启用联盟”\*\*\*\* 复选框。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-124">To allow federated users to call the group, select the **Enable for federation** check box.</span></span> <span data-ttu-id="a3fa9-125">您还必须具有一个适用于为联合配置的响应组应用程序的外部访问策略。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-125">You must also have an external access policy that applies to the Response Group application configured for federation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a3fa9-126">全局外部访问策略适用于响应组应用程序。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-126">The global external access policy applies to the Response Group application.</span></span> <span data-ttu-id="a3fa9-127">您可以使用 Lync Server 控制面板或使用 <STRONG>set-csexternalaccesspolicy</STRONG> Cmdlet 将 EnableOutsideAccess 参数设置为 True，从而为响应组联盟配置全局策略。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-127">You can configure the global policy for response group federation by using Lync Server Control Panel or by using the <STRONG>Set-CsExternalAccessPolicy</STRONG> cmdlet to set the EnableOutsideAccess parameter to True.</span></span> <span data-ttu-id="a3fa9-128">请记住，除非为全局策略设置分配站点或用户策略，否则这些设置适用于所有用户。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-128">Keep in mind that global policy settings apply to all users unless they are assigned a site or user policy.</span></span> <span data-ttu-id="a3fa9-129">因此，在针对响应组更改此设置之前，请确保联盟设置满足您的组织的要求。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-129">Therefore, before changing this setting for response groups, make sure that the federation setting meets the requirements of your organization.</span></span> <span data-ttu-id="a3fa9-130">有关如何将策略应用于用户的详细信息，请参阅 <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">在 Lync Server 2013 中管理外部访问策略</A>。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-130">For details about how policies apply to users, see <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">Manage external access policy in Lync Server 2013</A>.</span></span> <span data-ttu-id="a3fa9-131">有关联盟设置的详细信息，请参阅 <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy">set-csexternalaccesspolicy</A>。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-131">For details about the federation setting, see <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy">Set-CsExternalAccessPolicy</A>.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a3fa9-132">Lync Online 中托管的用户不能将呼叫放到托管在本地部署中的响应组。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-132">Users who are hosted in Lync Online can’t place calls to response groups that are hosted in an on-premise deployment.</span></span> <span data-ttu-id="a3fa9-133">这在混合部署和本地部署与 Lync Online 部署联合的情况下都是如此。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-133">This is true in both hybrid deployments and in cases where an on-premise deployment is federated with a Lync Online deployment.</span></span>

    
    </div>

9.  <span data-ttu-id="a3fa9-134">要在呼叫过程中隐藏代理身份，请选中“启用代理匿名”\*\*\*\* 复选框。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-134">To hide the identity of agents during calls, select the **Enable agent anonymity** check box.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a3fa9-135">尽管建立呼叫后，代理或呼叫者可以添加即时消息 (IM) 和视频，但匿名呼叫无法启动 IM 或视频。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-135">Anonymous calls cannot start with instant messaging (IM) or video, although the agent or the caller can add IM and video after the call is established.</span></span> <span data-ttu-id="a3fa9-136">匿名代理还可以将呼叫置于保持状态、转接呼叫（盲转接和咨询转接）、寄存和取回呼叫。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-136">An anonymous agent can also put calls on hold, transfer calls (both blind and consultative transfers), and park and retrieve calls.</span></span> <span data-ttu-id="a3fa9-137">匿名呼叫不支持会议、应用程序共享和桌面共享、文件传输、白板、数据协作和呼叫记录。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-137">Anonymous calls do not support conferencing, application sharing and desktop sharing, file transfer, whiteboarding and data collaboration, and call recording.</span></span> <span data-ttu-id="a3fa9-138">使用 Lync VDI 插件的代理可以以匿名方式接收传入呼叫，但不能以匿名方式发出传出呼叫。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-138">Agents using the Lync VDI Plugin can receive incoming calls anonymously, but they cannot make outgoing calls anonymously.</span></span>

    
    </div>

10. <span data-ttu-id="a3fa9-139">在“输入将接收呼叫的组的地址”\*\*\*\* 下，键入将应答工作流呼叫的组的主 SIP 统一资源标识符 (URI) 地址。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-139">Under **Enter the address of the group that will receive the calls**, type the primary SIP uniform resource identifier (URI) address of the group that will answer calls to the workflow.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a3fa9-140">工作流的主 URI 是标识和引用工作流的方式。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-140">The primary URI for a workflow is how the workflow is identified and referenced.</span></span> <span data-ttu-id="a3fa9-141">您输入的 SIP URI 在 Active Directory 域服务中作为联系人对象创建。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-141">The SIP URI that you enter is created as a contact object in Active Directory Domain Services.</span></span> <span data-ttu-id="a3fa9-142">若要创建此 URI，则该对象在 Active Directory 中必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-142">To create the URI, the object must be unique in Active Directory.</span></span>

    
    </div>

11. <span data-ttu-id="a3fa9-143">在“显示名称”\*\*\*\* 中，键入希望显示的工作流名称（例如，销售响应组）。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-143">In **Display name**, type the name that you want to display for the workflow (for example, Sales Response Group).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a3fa9-144">不要 &lt; 在显示名称中包含 "" 或 " &gt; " 字符。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-144">Do not include the "&lt;" or "&gt;" characters in the display name.</span></span> <span data-ttu-id="a3fa9-145">请勿使用以下显示名称，因为它们已被保留： <STRONG>RGS 状态观察</STRONG> 程序或 <STRONG>通知服务</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-145">Do not use the following display names because they are reserved: <STRONG>RGS Presence Watcher</STRONG> or <STRONG>Announcement Service</STRONG>.</span></span>

    
    </div>

12. <span data-ttu-id="a3fa9-146">在“电话号码”\*\*\*\* 下，键入响应组的线路 URI（例如，+14255550165）。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-146">Under **Telephone number**, type the line URI for the response group (for example, +14255550165).</span></span>

13. <span data-ttu-id="a3fa9-147">在“显示号码”\*\*\*\* 中，键入希望显示的响应组号码（例如，+1 (425) 555-0165）。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-147">In **Display number**, type the number as you want it to appear for the response group (for example, +1 (425) 555-0165).</span></span>

14. <span data-ttu-id="a3fa9-148"> (可选) 在 " **说明**" 中，键入要在 Lync 客户端中的联系人卡片上显示的工作流的说明。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-148">(Optional) In **Description**, type a description for the workflow as you want it to appear on the contact card in Lync client.</span></span>

15. <span data-ttu-id="a3fa9-149">如果工作流将由响应组管理员进行管理，则在“工作流类型”\*\*\*\* 中，选择“受管理”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-149">In **Workflow Type**, select **Managed** if this workflow will be managed by a Response Group Manager.</span></span> <span data-ttu-id="a3fa9-150">执行以下操作可向工作流分配响应组管理员：</span><span class="sxs-lookup"><span data-stu-id="a3fa9-150">Do the following to assign Response Group Managers to the workflow:</span></span>
    
    1.  <span data-ttu-id="a3fa9-151">键入此工作流的管理员的 SIP URI，然后单击 " **添加**"。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-151">Type the SIP URI of a manager for this workflow, and click **Add**.</span></span>
    
    2.  <span data-ttu-id="a3fa9-152">键入要添加到工作流的其他管理员的 SIP URI，然后单击 " **添加**"。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-152">Type the SIP URI of additional managers to add to the workflow, and click **Add**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="a3fa9-p113">必须为被指定为响应组管理员的每一位用户分配 CsResponseGroupManager 角色。如果没有为用户分配此角色，他们无法管理响应组。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-p113">Every user who is designated as a manager of a response group must be assigned the CsResponseGroupManager role. If users are not assigned this role, they cannot manage response groups.</span></span>

    
    </div>

16. <span data-ttu-id="a3fa9-155">在“步骤 2 选择语言”\*\*\*\* 下，单击要用于语音识别和文本到语音转换的语言。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-155">Under **Step 2 Select a Language**, click the language that you want to use for speech recognition and text-to-speech.</span></span>

17. <span data-ttu-id="a3fa9-156">如果要配置欢迎消息，请在“步骤 3 配置欢迎消息”\*\*\*\* 下选中“播放欢迎消息”\*\*\*\* 复选框，然后执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="a3fa9-156">If you want to configure a welcome message, under **Step 3 Configure a Welcome Message**, select the **Play a welcome message** check box, and then do one of the following:</span></span>
    
      - <span data-ttu-id="a3fa9-157">要为呼叫者输入转换成语音的文本形式的欢迎消息，请单击“使用文本到语音转换”\*\*\*\*，然后在文本框中键入欢迎消息。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-157">To enter the welcome message as text that is converted to speech for callers, click **Use text-to-speech**, and then type the welcome message in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="a3fa9-p114">不要在输入的文本中包含 HTML 标记，否则将收到错误消息。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-p114">Do not include HTML tags in the text you enter. If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
    
      - <span data-ttu-id="a3fa9-p115">要使用 Wave (.wav) 或 Windows Media 音频 (.wma) 文件录音作为欢迎消息，请单击“选择录音”\*\*\*\*。如果要上载新的音频文件，请单击“录音”\*\*\*\* 链接。在新浏览器窗口中，单击“浏览”\*\*\*\*，选择要使用的音频文件，然后单击“打开”\*\*\*\*。单击“上载”\*\*\*\*，加载该音频文件。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-p115">To use a wave (.wav) or Windows Media audio (.wma) file recording for the welcome message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the audio file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="a3fa9-164">用户提供的所有音频文件都必须满足特定要求。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-164">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="a3fa9-165">有关受支持的文件格式的详细信息，请参阅 <A href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013 中响应组的技术要求</A>。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-165">For details about supported file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

18. <span data-ttu-id="a3fa9-166">在“步骤 4 指定您的工作时间”\*\*\*\* 下的“您所在的时区”\*\*\*\* 中，单击工作流的时区。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-166">Under **Step 4 Specify Your Business Hours**, in **Your time zone**, click the time zone for the workflow.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a3fa9-p117">该时区是工作流的呼叫者和代理所在的时区。它用于计算开放和关闭的时间点。例如，如果将工作流配置为使用北美东部时间的时区，并安排工作流在上午 7:00 开放，晚上 11:00 关闭，则得出的开放和关闭时间点分别为东部时间 7:00 和东部时间 23:00。（必须以 24 小时制输入时间。)</span><span class="sxs-lookup"><span data-stu-id="a3fa9-p117">The time zone is the time zone where the callers and agents of the workflow reside. It is used to calculate the open and close hours. For example, if the workflow is configured to use the North American Eastern Time zone and the workflow is scheduled to open at 7:00 A.M. and close at 11:00 P.M., the open and close times are assumed to be 7:00 Eastern Time and 23:00 Eastern Time respectively. (You must enter the times in 24-hour time notation.)</span></span>

    
    </div>

19. <span data-ttu-id="a3fa9-172">通过执行下列操作之一选择要使用的工作时间日程表类型：</span><span class="sxs-lookup"><span data-stu-id="a3fa9-172">Select the type of business hours schedule you want to use by doing one of the following:</span></span>
    
      - <span data-ttu-id="a3fa9-173">要使用预定义工作时间日程表，请单击“使用预设日程表”\*\*\*\*，然后从下拉列表中选择要使用的日程表。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-173">To use a predefined schedule of business hours, click **Use a preset schedule**, and then select the schedule you want to use from the drop-down list.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="a3fa9-174">之前您必须至少已定义一个预设日程表才能选择该选项。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-174">You must have defined at least one preset schedule previously to be able to select this option.</span></span> <span data-ttu-id="a3fa9-175">可使用 <STRONG>New-CSRgsHoursOfBusiness</STRONG> cmdlet 来定义预设日程表。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-175">You define preset schedules by using the <STRONG>New-CSRgsHoursOfBusiness</STRONG> cmdlet.</span></span> <span data-ttu-id="a3fa9-176">有关详细信息，请参阅 <A href="lync-server-2013-optional-define-response-group-business-hours.md"> (Optional) 在 Lync Server 2013 中定义响应组工作时间</A>。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-176">For details, see <A href="lync-server-2013-optional-define-response-group-business-hours.md">(Optional) Define Response Group business hours in Lync Server 2013</A>.</span></span>

        
        </div>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="a3fa9-177">选择预设日程表时，“天”<STRONG></STRONG>、“开放”<STRONG></STRONG>和“关闭”<STRONG></STRONG>中会自动填写响应组可以应答的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-177">When you select a preset schedule, <STRONG>Day</STRONG>, <STRONG>Open</STRONG>, and <STRONG>Close</STRONG> are automatically filled with the days and hours that the response group is available.</span></span>

        
        </div>
    
      - <span data-ttu-id="a3fa9-178">要使用仅适用于该工作流的自定义日程表，请单击“使用自定义日程表”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-178">To use a custom schedule that applies only to this workflow, click **Use a custom schedule**.</span></span>

20. <span data-ttu-id="a3fa9-179">如果要创建该工作流的自定义日程表，请单击一周中响应组可以应答的日期对应的复选框。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-179">If you are creating a custom schedule for this workflow, click the check boxes for the days of the week that the response group is available.</span></span>

21. <span data-ttu-id="a3fa9-180">如果要创建自定义日程表，请键入一周中每一天响应组可以应答的“开放”\*\*\*\* 和“关闭”\*\*\*\* 时间点。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-180">If you are creating a custom schedule, type the **Open** and **Close** hours for each day of the week that the response group available.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a3fa9-p119">“开放”<STRONG></STRONG>和“关闭”<STRONG></STRONG>时间点必须采用 24 小时制。例如，如果营业时间为朝九晚五，其中午餐时间不办公，则工作时间指定为 9:00“开放”<STRONG></STRONG>、12:00“关闭”<STRONG></STRONG>、13:00“开放”<STRONG></STRONG>及 17:00“关闭”<STRONG></STRONG>。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-p119">The <STRONG>Open</STRONG> and <STRONG>Close</STRONG> hours must be in 24-hour time notation. For example, if your office works a 9-to-5 work day and closes at noon for lunch, the business hours are specified as <STRONG>Open</STRONG> 9:00, <STRONG>Close</STRONG> 12:00, <STRONG>Open</STRONG> 13:00, and <STRONG>Close</STRONG> 17:00.</span></span>

    
    </div>

22. <span data-ttu-id="a3fa9-183">如果要在办公室未开放时播放消息，请选中“响应组在工作时间以外时播放消息”\*\*\*\* 复选框，然后通过执行以下操作之一指定要播放的消息：</span><span class="sxs-lookup"><span data-stu-id="a3fa9-183">If you want to play a message when the office is not open, select the **Play a message when the response group is outside of business hours** check box, and then specify the message to play by doing one of the following:</span></span>
    
      - <span data-ttu-id="a3fa9-184">要为呼叫者输入转换成语音的文本形式的消息，请单击“使用文本到语音转换”\*\*\*\*，然后在文本框中键入消息。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-184">To enter the message as text that is converted to speech for the caller, click **Use text-to-speech**, and then type the message in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="a3fa9-p120">不要在输入的文本中包含 HTML 标记，否则将收到错误消息。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-p120">Do not include HTML tags in the text you enter. If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
    
      - <span data-ttu-id="a3fa9-p121">要使用音频文件录音作为消息，请单击“选择录音”\*\*\*\*。如果要上载新的音频文件，请单击“录音”\*\*\*\* 链接。在新浏览器窗口中，单击“浏览”\*\*\*\*，选择要使用的文件，然后单击“打开”\*\*\*\*。单击“上载”\*\*\*\*，加载该音频文件。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-p121">To use an audio file recording for the message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="a3fa9-191">用户提供的所有音频文件都必须满足特定要求。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-191">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="a3fa9-192">有关受支持的音频文件格式的详细信息，请参阅 <A href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013 中响应组的技术要求</A>。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-192">For details about supported audio file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

23. <span data-ttu-id="a3fa9-193">指定播放消息后如何处理呼叫（如果配置了消息）：</span><span class="sxs-lookup"><span data-stu-id="a3fa9-193">Specify how to handle calls after the message is played (if a message is configured):</span></span>
    
      - <span data-ttu-id="a3fa9-194">要断开呼叫，请单击“断开呼叫”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-194">To disconnect the call, click **Disconnect Call**.</span></span>
    
      - <span data-ttu-id="a3fa9-195">要将呼叫转接到语音邮件，请单击“转接到语音邮件”\*\*\*\*，然后键入语音邮件地址。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-195">To forward the call to voice mail, click **Forward to voice mail**, and then type the voice mail address.</span></span> <span data-ttu-id="a3fa9-196">语音邮件地址的格式为 \<username\> @ \<domainName\> (例如，bob@contoso.com) 。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-196">The format for the voice mail address is \<username\>@\<domainName\> (for example, bob@contoso.com).</span></span>
    
      - <span data-ttu-id="a3fa9-197">要将呼叫转接到另一个用户，请单击“转接到 SIP URI”\*\*\*\*，然后键入该用户的地址。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-197">To forward the call to another user, click **Forward to SIP URI**, and then type a user address.</span></span> <span data-ttu-id="a3fa9-198">用户地址的格式为 \<username\> @ \<domainName\> 。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-198">The format for the user address is \<username\>@\<domainName\>.</span></span>
    
      - <span data-ttu-id="a3fa9-199">要将呼叫转接到另一个电话号码，请单击“转接到电话号码”\*\*\*\*，然后键入该电话号码。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-199">To forward the call to another telephone number, click **Forward to telephone number**, and then type the telephone number.</span></span> <span data-ttu-id="a3fa9-200">电话号码的格式为 \<number\> @ \<domainName\> (例如，+ 14255550121@contoso.com) 。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-200">The format for the telephone number is \<number\>@\<domainName\> (for example, +14255550121@contoso.com).</span></span> <span data-ttu-id="a3fa9-201">域名可用来将呼叫者路由至正确的目标。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-201">The domain name is used to route the caller to the correct destination.</span></span>

24. <span data-ttu-id="a3fa9-202">在“步骤 5 指定您的假日”\*\*\*\* 下，单击定义响应组停止营业日期的一个或多个假日集对应的复选框。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-202">Under **Step 5 Specify Your Holidays**, click the check boxes for one or more sets of holidays that define the days when the response group is closed for business.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a3fa9-203">配置工作流之前，您需要先定义假日和假日集。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-203">You need to define holidays and holiday sets before you configure the workflow.</span></span> <span data-ttu-id="a3fa9-204">使用 <STRONG>New-CsRgsHoliday</STRONG> 和 <STRONG>New-CsRgsHolidaySet</STRONG> cmdlet 可定义假日和假日集。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-204">Use the <STRONG>New-CsRgsHoliday</STRONG> and <STRONG>New-CsRgsHolidaySet</STRONG> cmdlets to define holidays and holiday sets.</span></span> <span data-ttu-id="a3fa9-205">有关详细信息，请参阅 <A href="lync-server-2013-optional-define-response-group-holiday-sets.md"> (Optional) 在 Lync Server 2013 中定义响应组假日集</A>。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-205">For details, see <A href="lync-server-2013-optional-define-response-group-holiday-sets.md">(Optional) Define Response Group holiday sets in Lync Server 2013</A>.</span></span>

    
    </div>

25. <span data-ttu-id="a3fa9-206">如果要在假日播放消息，请选中“假期播放消息”\*\*\*\* 复选框，然后通过执行以下操作之一指定要播放的消息：</span><span class="sxs-lookup"><span data-stu-id="a3fa9-206">If you want to play a message on holidays, select the **Play a message during holidays** check box, and then specify the message to play by doing one of the following:</span></span>
    
      - <span data-ttu-id="a3fa9-207">要为呼叫者输入转换成语音的文本形式的消息，请单击“使用文本到语音转换”\*\*\*\*，然后在文本框中键入消息。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-207">To enter the message as text that is converted to speech for the caller, click **Use text-to-speech**, and then type the message in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="a3fa9-p127">不要在输入的文本中包含 HTML 标记，否则将收到错误消息。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-p127">Do not include HTML tags in the text you enter. If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
    
      - <span data-ttu-id="a3fa9-p128">要使用音频文件录音作为消息，请单击“选择录音”\*\*\*\*。如果要上载新的音频文件，请单击“录音”\*\*\*\* 链接。在新浏览器窗口中，单击“浏览”\*\*\*\*，选择要使用的文件，然后单击“打开”\*\*\*\*。单击“上载”\*\*\*\*，加载该音频文件。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-p128">To use an audio file recording for the message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="a3fa9-214">用户提供的所有音频文件都必须满足特定要求。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-214">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="a3fa9-215">有关受支持的音频文件格式的详细信息，请参阅 <A href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013 中响应组的技术要求</A>。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-215">For details about supported audio file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

26. <span data-ttu-id="a3fa9-216">指定播放消息后如何处理呼叫（如果配置了消息）：</span><span class="sxs-lookup"><span data-stu-id="a3fa9-216">Specify how to handle calls after the message is played (if a message is configured):</span></span>
    
      - <span data-ttu-id="a3fa9-217">要断开呼叫，请单击“断开呼叫”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-217">To disconnect the call, click **Disconnect Call**.</span></span>
    
      - <span data-ttu-id="a3fa9-218">要将呼叫转接到语音邮件，请单击“转接到语音邮件”\*\*\*\*，然后键入语音邮件地址。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-218">To forward the call to voice mail, click **Forward to voice mail**, and then type the voice mail address.</span></span> <span data-ttu-id="a3fa9-219">语音邮件地址的格式为 \<username\> @ \<domainName\> (例如，bob@contoso.com) 。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-219">The format for the voice mail address is \<username\>@\<domainName\> (for example, bob@contoso.com).</span></span>
    
      - <span data-ttu-id="a3fa9-220">要将呼叫转接到另一个用户，请单击“转接到 SIP URI”\*\*\*\*，然后键入该用户的地址。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-220">To forward the call to another user, click **Forward to SIP URI**, and then type a user address.</span></span> <span data-ttu-id="a3fa9-221">用户地址的格式为 \<username\> @ \<domainName\> 。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-221">The format for the user address is \<username\>@\<domainName\>.</span></span>
    
      - <span data-ttu-id="a3fa9-222">要将呼叫转接到另一个电话号码，请单击“转接到电话号码”\*\*\*\*，然后键入该电话号码。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-222">To forward the call to another telephone number, click **Forward to telephone number**, and then type the telephone number.</span></span> <span data-ttu-id="a3fa9-223">电话号码的格式为 \<number\> @ \<domainName\> (例如，+ 14255550121@contoso.com) 。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-223">The format for the telephone number is \<number\>@\<domainName\> (for example, +14255550121@contoso.com).</span></span> <span data-ttu-id="a3fa9-224">域名用于将呼叫者路由至正确的目标。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-224">The domain name is used to route the caller to the correct destination.</span></span>

27. <span data-ttu-id="a3fa9-225">在“步骤 6 配置队列”\*\*\*\* 下的“选择将接收呼叫的队列”\*\*\*\* 中，选择在出现可以应答的代理之前，使呼叫者处于保持状态的队列。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-225">Under **Step 6 Configure a Queue**, in **Select the queue that will receive the calls**, select the queue that you want to hold callers until an agent becomes available.</span></span>

28. <span data-ttu-id="a3fa9-226">在“步骤 7 配置保持音乐”\*\*\*\* 下，执行以下操作之一，选择希望呼叫者在等待代理时听到的音乐：</span><span class="sxs-lookup"><span data-stu-id="a3fa9-226">Under **Step 7 Configure Music on Hold**, choose the music you want callers to listen to while waiting for an agent by doing one of the following:</span></span>
    
      - <span data-ttu-id="a3fa9-227">要使用默认录音作为保持音乐，请单击“使用默认值”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-227">To use the default music-on-hold recording, click **Use default**.</span></span>
    
      - <span data-ttu-id="a3fa9-p133">要使用音频文件录音作为保持音乐，请单击“选择音乐文件”\*\*\*\*。如果要上载新的音频文件，请单击“音乐文件”\*\*\*\* 链接。在新浏览器窗口中，单击“浏览”\*\*\*\*，选择要使用的文件，然后单击“打开”\*\*\*\*。单击“上载”\*\*\*\*，加载该音频文件。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-p133">To use an audio file recording for the music on hold, click **Select a music file**. If you want to upload a new audio file, click the **a music file** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="a3fa9-232">用户提供的所有音频文件都必须满足特定要求。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-232">All user provided audio files must meet certain requirements.</span></span> <span data-ttu-id="a3fa9-233">有关受支持的音频文件格式的详细信息，请参阅 <A href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013 中响应组的技术要求</A>。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-233">For details about supported audio file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

29. <span data-ttu-id="a3fa9-234">单击“部署”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-234">Click **Deploy**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-a-hunt-group-workflow"></a><span data-ttu-id="a3fa9-235">使用 Windows PowerShell 创建或修改智能寻线工作流</span><span class="sxs-lookup"><span data-stu-id="a3fa9-235">To use Windows PowerShell to create or modify a hunt group workflow</span></span>

1.  <span data-ttu-id="a3fa9-236">以 RTCUniversalServerAdmins 组成员的身份登录，或以支持响应组的预定义管理角色之一的成员身份登录。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-236">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="a3fa9-237">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-237">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="a3fa9-238">创建要为欢迎邮件播放的提示，并将其保存在变量中。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-238">Create the prompt to be played for the welcome message, and save it in a variable.</span></span> <span data-ttu-id="a3fa9-239">在命令行中运行：</span><span class="sxs-lookup"><span data-stu-id="a3fa9-239">At the command line, run:</span></span>
    
        $promptWM = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
    
    <span data-ttu-id="a3fa9-240">例如：</span><span class="sxs-lookup"><span data-stu-id="a3fa9-240">For example:</span></span>
    
        $promptWM = New-CsRgsPrompt -TextToSpeechPrompt "Welcome to Contoso. Please wait for an available agent."
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a3fa9-241">要针对提示使用音频文件，请使用 <STRONG>Import-CsRgsAudioFile</STRONG> cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-241">To use an audio file for the prompt, use the <STRONG>Import-CsRgsAudioFile</STRONG> cmdlet.</span></span> <span data-ttu-id="a3fa9-242">有关详细信息，请参阅 <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">CsRgsAudioFile</A>。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-242">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">Import-CsRgsAudioFile</A>.</span></span>

    
    </div>

4.  <span data-ttu-id="a3fa9-243">获取将定向到呼叫的队列或问题的标识。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-243">Get the identity of the queue or question where the calls will be directed.</span></span> <span data-ttu-id="a3fa9-244">在命令行中运行：</span><span class="sxs-lookup"><span data-stu-id="a3fa9-244">At the command line, run:</span></span>
    
        $qid = (Get-CsRgsQueue -Name "Help Desk").Identity
    
    <span data-ttu-id="a3fa9-245">有关创建队列的详细信息，请参阅 [CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/New-CsRgsQueue)。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-245">For details about creating the queue, see [New-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/New-CsRgsQueue).</span></span>

5.  <span data-ttu-id="a3fa9-246">定义在营业时间打开工作流时要执行的默认操作，并将其保存在变量中。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-246">Define the default action to be taken when a workflow is opened during business hours, and save it in a variable.</span></span> <span data-ttu-id="a3fa9-247">在命令行中运行：</span><span class="sxs-lookup"><span data-stu-id="a3fa9-247">At the command line, run:</span></span>
    
        $actionWM = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken> -QueueID $qid
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a3fa9-248">对于智能寻线工作流，默认操作必须将呼叫定向到队列。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-248">For hunt group workflows, the default action must direct the call to a queue.</span></span> <span data-ttu-id="a3fa9-249">此参数是活动工作流所必需的。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-249">This is parameter is required for active workflows.</span></span> <span data-ttu-id="a3fa9-250">非活动工作流不需要此属性。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-250">It is not required for inactive workflows.</span></span>

    
    </div>
    
    <span data-ttu-id="a3fa9-251">例如：</span><span class="sxs-lookup"><span data-stu-id="a3fa9-251">For example:</span></span>
    
        $actionWM = New-CsRgsCallAction -Prompt $promptWM -Action TransferToQueue -QueueID $qid.Identity

6.  <span data-ttu-id="a3fa9-252">如果要定义营业时间和假日，您需要在创建或修改工作流之前创建它们。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-252">If you want to define business hours and holidays, you need to create them before you create or modify the workflow.</span></span> <span data-ttu-id="a3fa9-253">有关详细信息，请参阅 [ (optional) 在 Lync server 2013 中定义响应组工作时间](lync-server-2013-optional-define-response-group-business-hours.md) 和 [ (可选的) 在 lync Server 2013 中定义响应组假日集](lync-server-2013-optional-define-response-group-holiday-sets.md)。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-253">For details, see [(Optional) Define Response Group business hours in Lync Server 2013](lync-server-2013-optional-define-response-group-business-hours.md) and [(Optional) Define Response Group holiday sets in Lync Server 2013](lync-server-2013-optional-define-response-group-holiday-sets.md).</span></span>

7.  <span data-ttu-id="a3fa9-254">如果您想要对在营业时间内或在假期内收到的呼叫发出提示，请使用 **CsRgsPrompt** cmdlet 定义提示，并使用 **new-csrgscallaction** 定义在提示后要执行的操作。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-254">If you want to have prompts for calls that are received out of business hours or on holidays, use the **New-CsRgsPrompt** cmdlet to define the prompt, and use the **New-CsRgsCallAction** to define the action to be taken after the prompt.</span></span> <span data-ttu-id="a3fa9-255">有关详细信息，请参阅 [CsRgsPrompt](https://docs.microsoft.com/powershell/module/skype/New-CsRgsPrompt) 和 [new-csrgscallaction](https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction)。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-255">For details, see [New-CsRgsPrompt](https://docs.microsoft.com/powershell/module/skype/New-CsRgsPrompt) and [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction).</span></span>

8.  <span data-ttu-id="a3fa9-256">检索 Lync Server 响应组服务的服务名称，并将其分配给一个变量。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-256">Retrieve the service name for the Lync Server Response Group service and assign it to a variable.</span></span> <span data-ttu-id="a3fa9-257">在命令中，运行：</span><span class="sxs-lookup"><span data-stu-id="a3fa9-257">At the command, run:</span></span>
    
        $serviceId="service:"+(Get-CSService | ?{$_.Applications -like "*RGS*"}).ServiceId;

9.  <span data-ttu-id="a3fa9-258">创建或修改工作流。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-258">Create or modify the workflow.</span></span> <span data-ttu-id="a3fa9-259">若要创建工作流，请使用 **CsRgsWorkflow**。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-259">To create a workflow, use **New-CsRgsWorkflow**.</span></span> <span data-ttu-id="a3fa9-260">若要修改工作流，请使用 **CsRgsWorkflow**。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-260">To modify a workflow, use **Set-CsRgsWorkflow**.</span></span> <span data-ttu-id="a3fa9-261">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="a3fa9-261">At the command line, type:</span></span>
    
        $workflowHG = New-CsRgsWorkflow -Parent <service ID for the Response Group service> -Name "<hunt group name>" [-Description "<hunt group description>"] -PrimaryUri "<SIP address for the workflow>" [-LineUri "<Phone number for the workflow>"] [-DisplayNumber "<Phone number displayed in Lync>"] [-Active <$true | $false>] [-Anonymous <$true | $false>] [-DefaultAction <variable from preceding step>] [-EnabledForFederation <$true | $false>] [-Managed <$true | $false>] [-MangersByUri <SIP addresses for Response Group Managers who can manage the workflow>]
    
    <span data-ttu-id="a3fa9-262">例如：</span><span class="sxs-lookup"><span data-stu-id="a3fa9-262">For example:</span></span>
    
        $workflowHG = New-CsRgsWorkflow -Parent $serviceID -Name "Human Resources" -Description "Human Resources workflow" -PrimaryUri "sip:humanresources@contoso.com" -LineUri "TEL:+14255551219" -DisplayNumber "555-1219" -Active $true -Anonymous $true -DefaultAction $actionWM -EnabledForFederation $false -Managed $true -ManagersByUri "sip:bob@contoso.com", "mindy@contoso.com"
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="a3fa9-263">必须为指定了工作流管理员的所有用户分配 CsResponseGroupManager 角色。</span><span class="sxs-lookup"><span data-stu-id="a3fa9-263">All users who are designated managers for workflows must be assigned the CsResponseGroupManager role.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a3fa9-264">有关其他可选参数的详细信息，请参阅 <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsWorkflow">CsRgsWorkflow</A> 或 <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsRgsWorkflow">CsRgsWorkflow</A></span><span class="sxs-lookup"><span data-stu-id="a3fa9-264">For details about additional optional parameters, see <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsWorkflow">New-CsRgsWorkflow</A> or <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsRgsWorkflow">Set-CsRgsWorkflow</A></span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a3fa9-265">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a3fa9-265">See Also</span></span>


[<span data-ttu-id="a3fa9-266"> (可选) 在 Lync Server 2013 中定义响应组假日集</span><span class="sxs-lookup"><span data-stu-id="a3fa9-266">(Optional) Define Response Group holiday sets in Lync Server 2013</span></span>](lync-server-2013-optional-define-response-group-holiday-sets.md)  


[<span data-ttu-id="a3fa9-267"> (可选) 在 Lync Server 2013 中定义响应组工作时间</span><span class="sxs-lookup"><span data-stu-id="a3fa9-267">(Optional) Define Response Group business hours in Lync Server 2013</span></span>](lync-server-2013-optional-define-response-group-business-hours.md)  


[<span data-ttu-id="a3fa9-268">新 CsRgsWorkflow</span><span class="sxs-lookup"><span data-stu-id="a3fa9-268">New-CsRgsWorkflow</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsWorkflow)  
[<span data-ttu-id="a3fa9-269">CsRgsWorkflow</span><span class="sxs-lookup"><span data-stu-id="a3fa9-269">Set-CsRgsWorkflow</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsRgsWorkflow)  
[<span data-ttu-id="a3fa9-270">新 CsRgsPrompt</span><span class="sxs-lookup"><span data-stu-id="a3fa9-270">New-CsRgsPrompt</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsPrompt)  
[<span data-ttu-id="a3fa9-271">新 New-csrgscallaction</span><span class="sxs-lookup"><span data-stu-id="a3fa9-271">New-CsRgsCallAction</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

