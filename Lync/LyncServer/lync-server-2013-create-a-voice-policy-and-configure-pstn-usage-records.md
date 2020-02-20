---
title: Lync Server 2013：创建语音策略和配置 PSTN 用法记录
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a voice policy and configure PSTN usage records
ms:assetid: e6ff27e0-e2d1-4445-840f-08f738200c20
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399027(v=OCS.15)
ms:contentKeyID: 48185693
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1a4a240334dd83fd226586ac409c1bd91a871be
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145531"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-a-voice-policy-and-configure-pstn-usage-records-in-lync-server-2013"></a><span data-ttu-id="7b826-102">在 Lync Server 2013 中创建语音策略和配置 PSTN 用法记录</span><span class="sxs-lookup"><span data-stu-id="7b826-102">Create a voice policy and configure PSTN usage records in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7b826-103">_**上次修改的主题：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="7b826-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="7b826-104">如果要创建新的语音策略，请执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="7b826-104">Follow these steps if you want to create a new voice policy.</span></span> <span data-ttu-id="7b826-105">如果要编辑语音策略，请参阅[在 Lync Server 2013 中修改语音策略和配置 PSTN 用法记录中](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)的过程。</span><span class="sxs-lookup"><span data-stu-id="7b826-105">If you want to edit a voice policy, see [Modify a voice policy and configure PSTN usage records in Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md) for the procedure.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7b826-106">每个语音策略必须至少有一个关联的公用电话交换网（PSTN）用法记录。</span><span class="sxs-lookup"><span data-stu-id="7b826-106">Each voice policy must have at least one associated public switched telephone network (PSTN) usage record.</span></span> <span data-ttu-id="7b826-107">若要查看企业语音部署中提供的所有 PSTN 用法记录的列表并查看其属性，请参阅<A href="lync-server-2013-view-pstn-usage-records.md">在 Lync Server 2013 中查看 pstn 用法记录</A>。</span><span class="sxs-lookup"><span data-stu-id="7b826-107">To see a listing of all PSTN usage records available in your Enterprise Voice deployment and view their properties, see <A href="lync-server-2013-view-pstn-usage-records.md">View PSTN usage records in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-create-a-voice-policy"></a><span data-ttu-id="7b826-108">创建语音策略</span><span class="sxs-lookup"><span data-stu-id="7b826-108">To create a voice policy</span></span>

1.  <span data-ttu-id="7b826-109">以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。</span><span class="sxs-lookup"><span data-stu-id="7b826-109">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="7b826-110">有关详细信息，请参阅[Lync Server 2013 中的委派安装权限](lync-server-2013-delegate-setup-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="7b826-110">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="7b826-111">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="7b826-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="7b826-112">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="7b826-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="7b826-113">在左侧导航栏中，单击 "**语音路由**"，然后单击 "**语音策略**"。</span><span class="sxs-lookup"><span data-stu-id="7b826-113">In the left navigation bar, click **Voice Routing** and then click **Voice Policy**.</span></span>

4.  <span data-ttu-id="7b826-114">在 "**语音策略**" 页上，单击 "**新建**"，然后选择新策略的范围：</span><span class="sxs-lookup"><span data-stu-id="7b826-114">On the **Voice Policy** page, click **New** and then select a scope for the new policy:</span></span>
    
      - <span data-ttu-id="7b826-115">**网站策略**适用于整个网站，但分配给用户策略的任何用户或组除外。</span><span class="sxs-lookup"><span data-stu-id="7b826-115">**Site policy** applies to an entire site, except any users or groups that are assigned to a user policy.</span></span> <span data-ttu-id="7b826-116">如果为策略作用域选择 "站点"，请从 "**选择站点**" 对话框中选择站点。</span><span class="sxs-lookup"><span data-stu-id="7b826-116">If you select Site for a policy scope, choose the site from the **Select a Site** dialog box.</span></span> <span data-ttu-id="7b826-117">如果已为网站创建了语音策略，则该网站不会显示在 "**选择网站**" 对话框中。</span><span class="sxs-lookup"><span data-stu-id="7b826-117">If a voice policy has already been created for a site, the site does not appear in the **Select a Site** dialog box.</span></span>
    
      - <span data-ttu-id="7b826-118">**用户策略**可应用于指定的用户或组。</span><span class="sxs-lookup"><span data-stu-id="7b826-118">**User policy** can be applied to specified users or groups.</span></span>

5.  <span data-ttu-id="7b826-119">如果语音策略作用域为 User，请在 "**名称**" 字段中为策略输入一个描述性名称。</span><span class="sxs-lookup"><span data-stu-id="7b826-119">If the voice policy scope is User, enter a descriptive name for the policy in the **Name** field.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7b826-120">如果语音策略作用域为 "网站"，则<STRONG>新语音策略</STRONG>中的 "<STRONG>名称</STRONG>" 字段将预填充网站名称，且不能更改。</span><span class="sxs-lookup"><span data-stu-id="7b826-120">If the voice policy scope is Site, the <STRONG>Name</STRONG> field in <STRONG>New Voice Policy</STRONG> is prepopulated with the site name and cannot be changed.</span></span>

    
    </div>

6.  <span data-ttu-id="7b826-121">Optional输入语音策略的其他描述性信息。</span><span class="sxs-lookup"><span data-stu-id="7b826-121">(Optional) Enter additional descriptive information for the voice policy.</span></span>

7.  <span data-ttu-id="7b826-122">选中或清除以下复选框以启用或禁用此语音策略的每个**呼叫功能**：</span><span class="sxs-lookup"><span data-stu-id="7b826-122">Select or clear the following check boxes to enable or disable each of the **Calling features** for this voice policy:</span></span>
    
      - <span data-ttu-id="7b826-123">**语音邮件规避**可在配置了同时响铃且移动电话已关机、没电或接收不到信号时，阻止将呼叫立即路由到用户移动电话的语音邮件系统。</span><span class="sxs-lookup"><span data-stu-id="7b826-123">**Voice mail escape** prevents calls from being immediately routed to the user’s mobile phone voice mail system when simultaneous ringing is configured and the phone is turned off, out of battery, or out of range.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="7b826-124">此功能只能通过 Lync Server 命令行管理程序进行配置</span><span class="sxs-lookup"><span data-stu-id="7b826-124">This feature is only configurable through the Lync Server Management Shell</span></span>

        
        </div>
    
      - <span data-ttu-id="7b826-125">通过**呼叫转接**，用户可以将呼叫转接到其他电话或客户端设备。</span><span class="sxs-lookup"><span data-stu-id="7b826-125">**Call forwarding** enables users to forward calls to other phones and client devices.</span></span> <span data-ttu-id="7b826-126">Lync Server 2013 提供了范围更广的呼叫转发配置选项。</span><span class="sxs-lookup"><span data-stu-id="7b826-126">Lync Server 2013 provides a significantly wider range of configuration options for call forwarding.</span></span> <span data-ttu-id="7b826-127">例如，如果组织不允许将传入呼叫外部转接到 PSTN，则管理员可应用特定语音策略来部署此限制。</span><span class="sxs-lookup"><span data-stu-id="7b826-127">For example, if an organization does not want to allow incoming calls to be forwarded externally to the PSTN, an administrator can apply a special voice policy to deploy this restriction.</span></span> <span data-ttu-id="7b826-128">默认为启用。</span><span class="sxs-lookup"><span data-stu-id="7b826-128">Enabled by default.</span></span>
    
      - <span data-ttu-id="7b826-129">通过**委派**，用户可以指定其他用户代表他们发送和接收呼叫。</span><span class="sxs-lookup"><span data-stu-id="7b826-129">**Delegation** enables users to specify other users to send and receive calls on their behalf.</span></span> <span data-ttu-id="7b826-130">在 Lync Server 2013 中，代理可以配置同时响铃，使传入呼叫他或她的经理能够拨打所有代理同时拨打的目标。</span><span class="sxs-lookup"><span data-stu-id="7b826-130">In Lync Server 2013, a delegate can configure simultaneous ringing that enables incoming calls to his or her manager to ring all of the delegate’s simultaneous ringing targets.</span></span> <span data-ttu-id="7b826-131">这为代理提供了极大地灵活性以响应定向至管理员的呼叫。</span><span class="sxs-lookup"><span data-stu-id="7b826-131">This provides the delegate with greater flexibility in responding to calls directed to the manager.</span></span> <span data-ttu-id="7b826-132">默认为启用。</span><span class="sxs-lookup"><span data-stu-id="7b826-132">Enabled by default.</span></span>
    
      - <span data-ttu-id="7b826-133">通过**呼叫转移**，用户可以将呼叫转移到其他用户。</span><span class="sxs-lookup"><span data-stu-id="7b826-133">**Call transfer** enables users to transfer calls to other users.</span></span> <span data-ttu-id="7b826-134">默认为启用。</span><span class="sxs-lookup"><span data-stu-id="7b826-134">Enabled by default.</span></span>
    
      - <span data-ttu-id="7b826-135">通过**呼叫寄存**，用户可以寄存呼叫处于保留状态，然后从其他电话或客户端接听呼叫。</span><span class="sxs-lookup"><span data-stu-id="7b826-135">**Call park** enables users to park calls on hold and then pick up the call from a different phone or client.</span></span> <span data-ttu-id="7b826-136">默认情况下处于禁用状态。</span><span class="sxs-lookup"><span data-stu-id="7b826-136">Disabled by default.</span></span>
    
      - <span data-ttu-id="7b826-137">**同时响铃**使传入呼叫可以在其他电话（如手机）或其他终结点设备上响铃。</span><span class="sxs-lookup"><span data-stu-id="7b826-137">**Simultaneous ringing** enables incoming calls to ring on additional phones (for example, a mobile phone) or other endpoint devices.</span></span> <span data-ttu-id="7b826-138">Lync Server 2013 为同时响铃提供了更为广泛的配置选项。</span><span class="sxs-lookup"><span data-stu-id="7b826-138">Lync Server 2013 provides a significantly wider range of configuration options for simultaneous ringing.</span></span> <span data-ttu-id="7b826-139">默认为启用。</span><span class="sxs-lookup"><span data-stu-id="7b826-139">Enabled by default.</span></span>
    
      - <span data-ttu-id="7b826-p111">通过**团队呼叫**，指定团队中的用户可以为团队中的其他成员应答呼叫。默认为启用。</span><span class="sxs-lookup"><span data-stu-id="7b826-p111">**Team call** enables users on a defined team to answer calls for other members of the team. Enabled by default.</span></span>
    
      - <span data-ttu-id="7b826-p112">如果 WAN 拥堵或不可用，通过 **PSTN 重新路由**，可以在公用电话交换网 (PSTN) 上重新路由分配有此策略的用户向其他企业用户发出的呼叫。默认为启用。</span><span class="sxs-lookup"><span data-stu-id="7b826-p112">**PSTN re-route** enables calls made by users who are assigned this policy to other enterprise users to be rerouted on the public switched telephone network (PSTN) if the WAN is congested or unavailable. Enabled by default.</span></span>
    
      - <span data-ttu-id="7b826-144">通过**带宽策略覆盖**，管理员可以覆盖特定用户的呼叫允许控制策略决策。</span><span class="sxs-lookup"><span data-stu-id="7b826-144">**Bandwidth policy override** enables administrators to override call admission control policy decisions for a particular user.</span></span> <span data-ttu-id="7b826-145">默认为禁用。</span><span class="sxs-lookup"><span data-stu-id="7b826-145">Disabled by default.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="7b826-146">只能覆盖向用户发出的传入呼叫的策略，而不能覆盖由用户发出的传出呼叫的策略。</span><span class="sxs-lookup"><span data-stu-id="7b826-146">The policy will be overridden only for incoming calls to the user and not for outgoing calls that are placed by the user.</span></span> <span data-ttu-id="7b826-147">建立会话后，将准确记录带宽消耗。</span><span class="sxs-lookup"><span data-stu-id="7b826-147">After the session is established, the bandwidth consumption will be accurately recorded.</span></span> <span data-ttu-id="7b826-148">应谨慎使用此设置，应为适当的呼叫允许控制决定预留此设置。</span><span class="sxs-lookup"><span data-stu-id="7b826-148">This setting should be used sparingly and should be reserved for appropriate call admission control decisions.</span></span>

        
        </div>
    
      - <span data-ttu-id="7b826-149">通过**恶意呼叫跟踪**，用户可以通过使用客户端 UI 报告恶意呼叫（如炸弹威胁），后者又对呼叫详细信息记录（cdr）中的呼叫进行了标记。</span><span class="sxs-lookup"><span data-stu-id="7b826-149">**Malicious call tracing** enables users to report malicious calls (such as bomb threats) by using the client UI, which in turn flags the calls in the call detail records (CDRs).</span></span> <span data-ttu-id="7b826-150">默认情况下处于禁用状态。</span><span class="sxs-lookup"><span data-stu-id="7b826-150">Disabled by default.</span></span>

8.  <span data-ttu-id="7b826-151">要为此语音策略关联和配置 PSTN 用法记录，请执行以下任意操作：</span><span class="sxs-lookup"><span data-stu-id="7b826-151">To associate and configure PSTN usage records for this voice policy, do any of the following:</span></span>
    
      - <span data-ttu-id="7b826-p116">要从企业语音部署中提供的所有 PSTN 用法记录列表中选择一个或多个记录，请单击“选择”\*\*\*\*。突出显示要与此语音策略关联的记录，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7b826-p116">To choose one or more records from a list of all PSTN usage records available in your Enterprise Voice deployment, click **Select**. Highlight the records that you want to associate with this voice policy, and then click **OK**.</span></span>
    
      - <span data-ttu-id="7b826-154">要删除此语音策略中的某个 PSTN 用法记录，请突出显示相应的记录，然后单击“删除”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7b826-154">To remove a PSTN usage record from this voice policy, highlight the record and click **Remove**.</span></span>
    
      - <span data-ttu-id="7b826-155">要定义新的 PSTN 用法记录并将其与此语音策略相关联，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="7b826-155">To define a new PSTN usage record and associate it with this voice policy, do the following:</span></span>
        
        1.  <span data-ttu-id="7b826-156">单击“新建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7b826-156">Click **New**.</span></span>
        
        2.  <span data-ttu-id="7b826-157">在“名称”\*\*\*\* 字段中，输入记录的唯一描述性名称。</span><span class="sxs-lookup"><span data-stu-id="7b826-157">In the **Name** field, enter a unique descriptive name for the record.</span></span> <span data-ttu-id="7b826-158">例如，您可能希望为位于 Redmond 的全职员工创建名为**redmond**的 PSTN 用法记录，并为临时员工创建另一个已命名的**RedmondTemps** 。</span><span class="sxs-lookup"><span data-stu-id="7b826-158">For example, you may want to create a PSTN usage record named **Redmond** for full-time employees located in Redmond, and another named **RedmondTemps** for temporary employees.</span></span>
            
            <div>
            

            > [!NOTE]  
            > <span data-ttu-id="7b826-p118">PSTN 用法记录名称在企业语音部署中必须是唯一的。保存记录后，将无法编辑“名称”<STRONG></STRONG>字段。</span><span class="sxs-lookup"><span data-stu-id="7b826-p118">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the <STRONG>Name</STRONG> field cannot be edited.</span></span>

            
            </div>
        
        3.  <span data-ttu-id="7b826-161">使用以下任意方法为此 PSTN 用法记录关联和配置路由：</span><span class="sxs-lookup"><span data-stu-id="7b826-161">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="7b826-162">要从企业语音部署中提供的所有路由列表中选择一个或多个路由，请单击“选择”\*\*\*\*，突出显示要与此 PSTN 用法记录相关联的路由，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7b826-162">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>
            
              - <span data-ttu-id="7b826-163">若要从 PSTN 用法记录中删除路由，请突出显示该路由，然后单击 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="7b826-163">To remove a route from the PSTN usage record, highlight the route, and then click **Remove**.</span></span>
            
              - <span data-ttu-id="7b826-164">要定义新路由并将其与此 PSTN 用法记录相关联，请单击“新建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7b826-164">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="7b826-165">有关详细信息，请参阅[在 Lync Server 2013 中创建语音路由](lync-server-2013-create-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="7b826-165">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="7b826-166">要编辑已经与此 PSTN 用法记录相关联的路由，请突出显示相应的路由，然后单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7b826-166">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="7b826-167">有关详细信息，请参阅[在 Lync Server 2013 中修改语音路由](lync-server-2013-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="7b826-167">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        4.  <span data-ttu-id="7b826-168">单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="7b826-168">Click **OK**.</span></span>
    
      - <span data-ttu-id="7b826-169">要编辑已经与此语音策略相关联的 PSTN 用法记录，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="7b826-169">To edit a PSTN usage record that is already associated with this voice policy, do the following:</span></span>
        
        1.  <span data-ttu-id="7b826-170">突出显示要编辑的 PSTN 用法记录，然后单击 "**显示详细信息**"。</span><span class="sxs-lookup"><span data-stu-id="7b826-170">Highlight the PSTN usage record that you want to edit, and then click **Show details**.</span></span>
        
        2.  <span data-ttu-id="7b826-171">使用以下任意方法为此 PSTN 用法记录关联和配置路由：</span><span class="sxs-lookup"><span data-stu-id="7b826-171">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="7b826-172">要从企业语音部署中提供的所有路由列表中选择一个或多个路由，请单击“选择”\*\*\*\*，突出显示要与此 PSTN 用法记录相关联的路由，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7b826-172">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes you want to associate with this PSTN usage record, and then click **OK**.</span></span>
            
              - <span data-ttu-id="7b826-173">若要从此 PSTN 用法记录中删除路由，请突出显示该路由，然后单击 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="7b826-173">To remove a route from this PSTN usage record, highlight the route, and then click **Remove**.</span></span>
            
              - <span data-ttu-id="7b826-174">要定义新路由并将其与此 PSTN 用法记录相关联，请单击“新建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7b826-174">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="7b826-175">有关详细信息，请参阅[在 Lync Server 2013 中创建语音路由](lync-server-2013-create-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="7b826-175">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="7b826-176">若要编辑已与此 PSTN 用法记录相关联的路由，请突出显示该路由并单击**显示详细信息**。</span><span class="sxs-lookup"><span data-stu-id="7b826-176">To edit a route that is already associated with this PSTN usage record, highlight the route and lick **Show details**.</span></span> <span data-ttu-id="7b826-177">有关详细信息，请参阅[在 Lync Server 2013 中修改语音路由](lync-server-2013-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="7b826-177">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        3.  <span data-ttu-id="7b826-178">单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7b826-178">Click **OK**.</span></span>

9.  <span data-ttu-id="7b826-p123">排列 PSTN 用法记录以获得最佳性能。要更改记录在列表中的位置，请突出显示相应的记录名称，然后单击向上箭头或向下箭头。</span><span class="sxs-lookup"><span data-stu-id="7b826-p123">Arrange the PSTN usage records for optimum performance. To change a record’s position in the list, highlight the record name and click the up or down arrow.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="7b826-181">PSTN 用法记录在语音策略中的列出顺序十分重要。</span><span class="sxs-lookup"><span data-stu-id="7b826-181">The order in which PSTN usage records are listed in the voice policy is significant.</span></span> <span data-ttu-id="7b826-182">Lync Server 从上到下遍历列表。</span><span class="sxs-lookup"><span data-stu-id="7b826-182">Lync Server traverses the list from the top down.</span></span> <span data-ttu-id="7b826-183">建议按使用频率来组织该列表，例如：RedmondLocal、RedmondLongDist、RedmondInternational 和 RedmondBackup。</span><span class="sxs-lookup"><span data-stu-id="7b826-183">We recommend that you organize the list by frequency of use, for example: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span></span>

    
    </div>

10. <span data-ttu-id="7b826-184">要为此语音策略中的呼叫转接和同时响铃关联和配置 PSTN 用法记录，请执行以下任一操作：</span><span class="sxs-lookup"><span data-stu-id="7b826-184">To associate and configure PSTN usage records for call forwarding and simultaneous ringing in this voice policy, do any of the following:</span></span>
    
      - <span data-ttu-id="7b826-185">若要对呼叫转接和同时响铃使用与此语音策略相同的 PSTN 用法记录，请从下拉菜单中选择“使用呼叫 PSTN 用法进行路由”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7b826-185">To use the same PSTN usage records for call forwarding and simultaneous ringing as this voice policy, select the option **Route using the call PSTN usages** from the drop-down menu.</span></span>
    
      - <span data-ttu-id="7b826-186">若要仅允许呼叫转接和同时响铃到内部 Lync 用户，请从下拉菜单中选择 "**仅发送到内部 lync 用户**" 的选项。</span><span class="sxs-lookup"><span data-stu-id="7b826-186">To allow call forwarding and simultaneous ringing to internal Lync users only, select the option **Route to internal Lync users only** from the drop-down menu.</span></span> <span data-ttu-id="7b826-187">呼叫将不会转接到外部 PSTN 号码。</span><span class="sxs-lookup"><span data-stu-id="7b826-187">Calls will not be forwarded to external PSTN numbers.</span></span>
    
      - <span data-ttu-id="7b826-188">若要为呼叫转接和同时响铃指定不同的 PSTN 用法记录，而不是用于此语音策略，请从下拉菜单中选择 "**使用自定义 PSTN**使用的选项" 路由。</span><span class="sxs-lookup"><span data-stu-id="7b826-188">To specify different PSTN usage records for call forwarding and simultaneous ringing than used for this voice policy, select the option **Route using custom PSTN usages** from the drop-down menu.</span></span> <span data-ttu-id="7b826-189">此选项显示用于选择现有 PSTN 用法记录或创建专用于呼叫转接和同时响铃的新 PSTN 用法记录的控件。</span><span class="sxs-lookup"><span data-stu-id="7b826-189">This option displays a control to select existing PSTN usage records or create new PSTN usage records specifically for call forwarding and simultaneous ringing.</span></span>
        
          - <span data-ttu-id="7b826-p127">要从呼叫转接和同时响铃的 PSTN 用法记录列表中选择一个或多个记录，请单击“选择”\*\*\*\*。突出显示要与此呼叫转接和同时响铃策略关联的记录，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7b826-p127">To choose one or more records from a list of PSTN usage records for call forwarding and simultaneous ringing, click **Select**. Highlight the records that you want to associate with this call forwarding and simultaneous ringing policy, and then click **OK**.</span></span>
        
          - <span data-ttu-id="7b826-192">要从此呼叫转接和同时响铃策略中删除某个 PSTN 用法记录，请突出显示相应的记录，然后单击“删除”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7b826-192">To remove a PSTN usage record from this call forwarding and simultaneous ringing policy, highlight the record and click **Remove**.</span></span>
        
          - <span data-ttu-id="7b826-193">要定义新的 PSTN 用法记录并将其与此呼叫转接和同时响铃策略相关联，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="7b826-193">To define a new PSTN usage record and associate it with this call forwarding and simultaneous ringing policy, do the following:</span></span>
            
            1.  <span data-ttu-id="7b826-194">单击“新建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7b826-194">Click **New**.</span></span>
            
            2.  <span data-ttu-id="7b826-195">在“名称”\*\*\*\* 字段中，输入记录的唯一描述性名称。</span><span class="sxs-lookup"><span data-stu-id="7b826-195">In the **Name** field, enter a unique descriptive name for the record.</span></span>
                
                <div>
                

                > [!NOTE]  
                > <span data-ttu-id="7b826-p128">PSTN 用法记录名称在企业语音部署中必须是唯一的。保存记录后，将无法编辑“名称”<STRONG></STRONG>字段。</span><span class="sxs-lookup"><span data-stu-id="7b826-p128">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the <STRONG>Name</STRONG> field cannot be edited.</span></span>

                
                </div>
            
            3.  <span data-ttu-id="7b826-198">使用以下任意方法为此 PSTN 用法记录关联和配置路由：</span><span class="sxs-lookup"><span data-stu-id="7b826-198">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
                
                  - <span data-ttu-id="7b826-199">要从企业语音部署中提供的所有路由列表中选择一个或多个路由，请单击“选择”\*\*\*\*，突出显示要与此 PSTN 用法记录相关联的路由，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7b826-199">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>
                
                  - <span data-ttu-id="7b826-200">要删除 PSTN 用法记录中的某个路由，请突出显示相应的路由，然后单击“删除”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7b826-200">To remove a route from the PSTN usage record, highlight the route and click **Remove**.</span></span>
                
                  - <span data-ttu-id="7b826-201">要定义新路由并将其与此 PSTN 用法记录相关联，请单击“新建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7b826-201">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="7b826-202">有关详细信息，请参阅[在 Lync Server 2013 中创建语音路由](lync-server-2013-create-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="7b826-202">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
                
                  - <span data-ttu-id="7b826-203">要编辑已经与此 PSTN 用法记录相关联的路由，请突出显示相应的路由，然后单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7b826-203">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="7b826-204">有关详细信息，请参阅[在 Lync Server 2013 中修改语音路由](lync-server-2013-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="7b826-204">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
            
            4.  <span data-ttu-id="7b826-205">单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="7b826-205">Click **OK**.</span></span>
        
          - <span data-ttu-id="7b826-206">要编辑已经与此语音策略相关联的 PSTN 用法记录，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="7b826-206">To edit a PSTN usage record that is already associated with this voice policy, do the following:</span></span>
            
            1.  <span data-ttu-id="7b826-207">突出显示要编辑的 PSTN 用法记录，然后单击 "**显示详细信息**"。</span><span class="sxs-lookup"><span data-stu-id="7b826-207">Highlight the PSTN usage record you want to edit and click **Show details**.</span></span>
            
            2.  <span data-ttu-id="7b826-208">使用以下任意方法为此 PSTN 用法记录关联和配置路由：</span><span class="sxs-lookup"><span data-stu-id="7b826-208">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
                
                  - <span data-ttu-id="7b826-209">要从企业语音部署中提供的所有路由列表中选择一个或多个路由，请单击“选择”\*\*\*\*，突出显示要与此 PSTN 用法记录相关联的路由，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7b826-209">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>
                
                  - <span data-ttu-id="7b826-210">要删除此 PSTN 用法记录中的某个路由，请突出显示相应的路由，然后单击“删除”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7b826-210">To remove a route from this PSTN usage record, highlight the route and click **Remove**.</span></span>
                
                  - <span data-ttu-id="7b826-211">要定义新路由并将其与此 PSTN 用法记录相关联，请单击“新建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7b826-211">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="7b826-212">有关详细信息，请参阅[在 Lync Server 2013 中创建语音路由](lync-server-2013-create-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="7b826-212">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
                
                  - <span data-ttu-id="7b826-213">要编辑已经与此 PSTN 用法记录相关联的路由，请突出显示相应的路由，然后单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7b826-213">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="7b826-214">有关详细信息，请参阅[在 Lync Server 2013 中修改语音路由](lync-server-2013-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="7b826-214">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
            
            3.  <span data-ttu-id="7b826-215">单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="7b826-215">Click **OK**.</span></span>

11. <span data-ttu-id="7b826-p133">（可选）输入一个号码来测试语音策略，然后单击“执行”\*\*\*\*。测试结果会显示在“要测试的转换号码”\*\*\*\* 下。</span><span class="sxs-lookup"><span data-stu-id="7b826-p133">(Optional) Enter a number to test the voice policy and click **Go**. The test results are displayed under **Translated number to test**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7b826-218">您可以保存尚未通过测试的语音策略，并在稍后对其进行重新配置。</span><span class="sxs-lookup"><span data-stu-id="7b826-218">You can save a voice policy that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="7b826-219">有关详细信息，请参阅<A href="lync-server-2013-test-voice-routing.md">在 Lync Server 2013 中测试语音路由</A>。</span><span class="sxs-lookup"><span data-stu-id="7b826-219">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

12. <span data-ttu-id="7b826-220">单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7b826-220">Click **OK**.</span></span>

13. <span data-ttu-id="7b826-221">在“语音策略”\*\*\*\* 页上，单击“提交”\*\*\*\*，然后单击“全部提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7b826-221">On the **Voice Policy** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7b826-222">无论何时创建或修改语音策略，都必须运行 "<STRONG>全部提交</STRONG>" 命令以发布配置更改。</span><span class="sxs-lookup"><span data-stu-id="7b826-222">Any time you create or modify a voice policy, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="7b826-223">有关详细信息，请参阅操作文档中的在<A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 中发布待处理的语音路由配置的更改</A>。</span><span class="sxs-lookup"><span data-stu-id="7b826-223">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

14. <span data-ttu-id="7b826-224">（可选）语音邮件规避检测到用户的手机语音邮件立即应答了一个呼叫，因此将断开至移动电话语音邮件的呼叫。</span><span class="sxs-lookup"><span data-stu-id="7b826-224">(Optional) Voicemail Escape detects that a call was immediately answered by the user’s mobile phone voice mail, and disconnects the call to the mobile phone voice mail.</span></span> <span data-ttu-id="7b826-225">这将允许此呼叫继续在用户的其他终结点上响铃，以使用户能够应答呼叫。</span><span class="sxs-lookup"><span data-stu-id="7b826-225">This allows the call to continue to ring on the user’s other endpoints giving the user the opportunity to answer the call.</span></span> <span data-ttu-id="7b826-226">有关如何配置语音邮件策略的详细信息，请参阅[Lync Server 2013 中的配置语音邮件转义](lync-server-2013-configuring-voice-mail-escape.md)。</span><span class="sxs-lookup"><span data-stu-id="7b826-226">For details on how to configure a voice mail policy, see [Configuring voice mail escape in Lync Server 2013](lync-server-2013-configuring-voice-mail-escape.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7b826-227">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7b826-227">See Also</span></span>


[<span data-ttu-id="7b826-228">在 Lync Server 2013 中修改语音策略和配置 PSTN 用法记录</span><span class="sxs-lookup"><span data-stu-id="7b826-228">Modify a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
[<span data-ttu-id="7b826-229">在 Lync Server 2013 中查看 PSTN 用法记录</span><span class="sxs-lookup"><span data-stu-id="7b826-229">View PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-view-pstn-usage-records.md)  
[<span data-ttu-id="7b826-230">在 Lync Server 2013 中创建语音路由</span><span class="sxs-lookup"><span data-stu-id="7b826-230">Create a voice route in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-route.md)  
[<span data-ttu-id="7b826-231">在 Lync Server 2013 中修改语音路由</span><span class="sxs-lookup"><span data-stu-id="7b826-231">Modify a voice route in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-route.md)  
[<span data-ttu-id="7b826-232">在 Lync Server 2013 中发布对语音路由配置所做的挂起更改</span><span class="sxs-lookup"><span data-stu-id="7b826-232">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  
[<span data-ttu-id="7b826-233">在 Lync Server 2013 中配置语音邮件转义</span><span class="sxs-lookup"><span data-stu-id="7b826-233">Configuring voice mail escape in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-mail-escape.md)  


[<span data-ttu-id="7b826-234">在 Lync Server 2013 中测试语音路由</span><span class="sxs-lookup"><span data-stu-id="7b826-234">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

