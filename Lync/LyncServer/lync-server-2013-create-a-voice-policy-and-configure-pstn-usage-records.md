---
title: 'Lync Server 2013: 创建语音策略和配置 PSTN 使用记录'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a voice policy and configure PSTN usage records
ms:assetid: e6ff27e0-e2d1-4445-840f-08f738200c20
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399027(v=OCS.15)
ms:contentKeyID: 48185693
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c11eafa265bf2ba20e8a68a84231092dcb01ffa3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837078"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-voice-policy-and-configure-pstn-usage-records-in-lync-server-2013"></a><span data-ttu-id="ab691-102">在 Lync Server 2013 中创建语音策略和配置 PSTN 使用记录</span><span class="sxs-lookup"><span data-stu-id="ab691-102">Create a voice policy and configure PSTN usage records in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ab691-103">_**主题上次修改时间:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="ab691-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="ab691-104">如果要创建新的语音策略, 请执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="ab691-104">Follow these steps if you want to create a new voice policy.</span></span> <span data-ttu-id="ab691-105">如果要编辑语音策略, 请参阅[在 Lync Server 2013 中的 "修改语音策略" 和 "配置 PSTN 使用记录" 中](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)的过程。</span><span class="sxs-lookup"><span data-stu-id="ab691-105">If you want to edit a voice policy, see [Modify a voice policy and configure PSTN usage records in Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md) for the procedure.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ab691-106">每个语音策略必须至少有一个关联的公共交换电话网络 (PSTN) 使用记录。</span><span class="sxs-lookup"><span data-stu-id="ab691-106">Each voice policy must have at least one associated public switched telephone network (PSTN) usage record.</span></span> <span data-ttu-id="ab691-107">若要查看你的企业语音部署中可用的所有 PSTN 使用记录的列表, 并查看其属性, 请参阅<A href="lync-server-2013-view-pstn-usage-records.md">在 Lync Server 2013 中查看 pstn 使用情况记录</A>。</span><span class="sxs-lookup"><span data-stu-id="ab691-107">To see a listing of all PSTN usage records available in your Enterprise Voice deployment and view their properties, see <A href="lync-server-2013-view-pstn-usage-records.md">View PSTN usage records in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-create-a-voice-policy"></a><span data-ttu-id="ab691-108">创建语音策略</span><span class="sxs-lookup"><span data-stu-id="ab691-108">To create a voice policy</span></span>

1.  <span data-ttu-id="ab691-109">以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。</span><span class="sxs-lookup"><span data-stu-id="ab691-109">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="ab691-110">有关详细信息, 请参阅[在 Lync Server 2013 中委派设置权限](lync-server-2013-delegate-setup-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="ab691-110">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="ab691-111">打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="ab691-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="ab691-112">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="ab691-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="ab691-113">在左侧导航栏中，单击“语音路由”\*\*\*\*，然后单击“语音策略”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ab691-113">In the left navigation bar, click **Voice Routing** and then click **Voice Policy**.</span></span>

4.  <span data-ttu-id="ab691-114">在“语音策略”\*\*\*\* 页上，单击“新建”\*\*\*\*，然后选择新策略的作用域：</span><span class="sxs-lookup"><span data-stu-id="ab691-114">On the **Voice Policy** page, click **New** and then select a scope for the new policy:</span></span>
    
      - <span data-ttu-id="ab691-p105">**站点策略**将应用于整个站点，分配给用户策略的任何用户或组除外。如果选择了“Site”作为策略作用域，请从“选择站点”\*\*\*\* 对话框中选择站点。如果已经为站点创建了语音策略，则该站点不会显示在“选择站点”\*\*\*\* 对话框中。</span><span class="sxs-lookup"><span data-stu-id="ab691-p105">**Site policy** applies to an entire site, except any users or groups that are assigned to a user policy. If you select Site for a policy scope, choose the site from the **Select a Site** dialog box. If a voice policy has already been created for a site, the site does not appear in the **Select a Site** dialog box.</span></span>
    
      - <span data-ttu-id="ab691-118">**用户策略**可应用于指定的用户或组。</span><span class="sxs-lookup"><span data-stu-id="ab691-118">**User policy** can be applied to specified users or groups.</span></span>

5.  <span data-ttu-id="ab691-119">如果语音策略作用域为“用户”，请在“名称”\*\*\*\* 字段中输入策略的描述性名称。</span><span class="sxs-lookup"><span data-stu-id="ab691-119">If the voice policy scope is User, enter a descriptive name for the policy in the **Name** field.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ab691-120">如果语音策略作用域为“Site”，将用站点名称填充“新建语音策略”<STRONG></STRONG>中的“名称”<STRONG></STRONG>字段，并且无法更改。</span><span class="sxs-lookup"><span data-stu-id="ab691-120">If the voice policy scope is Site, the <STRONG>Name</STRONG> field in <STRONG>New Voice Policy</STRONG> is prepopulated with the site name and cannot be changed.</span></span>

    
    </div>

6.  <span data-ttu-id="ab691-121">（可选）输入语音策略的其他描述性信息。</span><span class="sxs-lookup"><span data-stu-id="ab691-121">(Optional) Enter additional descriptive information for the voice policy.</span></span>

7.  <span data-ttu-id="ab691-122">选中或清除以下复选框以启用或禁用该语音策略的每种“呼叫功能”\*\*\*\*：</span><span class="sxs-lookup"><span data-stu-id="ab691-122">Select or clear the following check boxes to enable or disable each of the **Calling features** for this voice policy:</span></span>
    
      - <span data-ttu-id="ab691-123">当配置同时响铃，且电话关闭，电池耗尽或超出服务范围时，**语音邮件转义**可阻止立即将呼叫路由到用户的移动电话语音电子邮件系统。</span><span class="sxs-lookup"><span data-stu-id="ab691-123">**Voice mail escape** prevents calls from being immediately routed to the user’s mobile phone voice mail system when simultaneous ringing is configured and the phone is turned off, out of battery, or out of range.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="ab691-124">此功能只能通过 Lync Server 命令行管理程序进行配置</span><span class="sxs-lookup"><span data-stu-id="ab691-124">This feature is only configurable through the Lync Server Management Shell</span></span>

        
        </div>
    
      - <span data-ttu-id="ab691-125">通过**呼叫转接**，用户可以将呼叫转接到其他电话或客户端设备。</span><span class="sxs-lookup"><span data-stu-id="ab691-125">**Call forwarding** enables users to forward calls to other phones and client devices.</span></span> <span data-ttu-id="ab691-126">Lync Server 2013 为呼叫转接提供了一系列更广泛的配置选项。</span><span class="sxs-lookup"><span data-stu-id="ab691-126">Lync Server 2013 provides a significantly wider range of configuration options for call forwarding.</span></span> <span data-ttu-id="ab691-127">例如，如果组织不允许将传入呼叫外部转接到 PSTN，则管理员可应用特定语音策略来部署此限制。</span><span class="sxs-lookup"><span data-stu-id="ab691-127">For example, if an organization does not want to allow incoming calls to be forwarded externally to the PSTN, an administrator can apply a special voice policy to deploy this restriction.</span></span> <span data-ttu-id="ab691-128">默认为启用。</span><span class="sxs-lookup"><span data-stu-id="ab691-128">Enabled by default.</span></span>
    
      - <span data-ttu-id="ab691-129">通过**委派**，用户可以指定其他用户代表他们发送和接收呼叫。</span><span class="sxs-lookup"><span data-stu-id="ab691-129">**Delegation** enables users to specify other users to send and receive calls on their behalf.</span></span> <span data-ttu-id="ab691-130">在 Lync Server 2013 中, 代理人可以配置同时拨打的电话, 让他/她的经理拨出所有代理人同时拨打的目标电话。</span><span class="sxs-lookup"><span data-stu-id="ab691-130">In Lync Server 2013, a delegate can configure simultaneous ringing that enables incoming calls to his or her manager to ring all of the delegate’s simultaneous ringing targets.</span></span> <span data-ttu-id="ab691-131">这会向委派提供极大的灵活性以响应直接传到经理的呼叫。</span><span class="sxs-lookup"><span data-stu-id="ab691-131">This provides the delegate with greater flexibility in responding to calls directed to the manager.</span></span> <span data-ttu-id="ab691-132">默认为启用。</span><span class="sxs-lookup"><span data-stu-id="ab691-132">Enabled by default.</span></span>
    
      - <span data-ttu-id="ab691-p108">通过**呼叫转移**，用户可以将呼叫转移到其他用户。默认为启用。</span><span class="sxs-lookup"><span data-stu-id="ab691-p108">**Call transfer** enables users to transfer calls to other users. Enabled by default.</span></span>
    
      - <span data-ttu-id="ab691-p109">通过 **呼叫寄存**，用户可以寄存呼叫，将其置于保持状态，然后从其他电话或客户端接听呼叫。默认为禁用。</span><span class="sxs-lookup"><span data-stu-id="ab691-p109">**Call park** enables users to park calls on hold and then pick up the call from a different phone or client. Disabled by default.</span></span>
    
      - <span data-ttu-id="ab691-137">**同时响铃**使来电可以在其他电话（例如，移动电话）或其他终结点设备上响铃。</span><span class="sxs-lookup"><span data-stu-id="ab691-137">**Simultaneous ringing** enables incoming calls to ring on additional phones (for example, a mobile phone) or other endpoint devices.</span></span> <span data-ttu-id="ab691-138">Lync Server 2013 为同时拨打的配置选项提供了明显范围的更广泛的配置选项。</span><span class="sxs-lookup"><span data-stu-id="ab691-138">Lync Server 2013 provides a significantly wider range of configuration options for simultaneous ringing.</span></span> <span data-ttu-id="ab691-139">默认为启用。</span><span class="sxs-lookup"><span data-stu-id="ab691-139">Enabled by default.</span></span>
    
      - <span data-ttu-id="ab691-140">通过**团队呼叫**，指定团队中的用户可以为团队中的其他成员应答呼叫。</span><span class="sxs-lookup"><span data-stu-id="ab691-140">**Team call** enables users on a defined team to answer calls for other members of the team.</span></span> <span data-ttu-id="ab691-141">默认为启用。</span><span class="sxs-lookup"><span data-stu-id="ab691-141">Enabled by default.</span></span>
    
      - <span data-ttu-id="ab691-142">**PSTN 重新路由**允许向其他企业用户分配此策略的用户发出呼叫, 如果 WAN 拥挤或不可用, 则将其重新路由到公共交换电话网络 (PSTN)。</span><span class="sxs-lookup"><span data-stu-id="ab691-142">**PSTN re-route** enables calls made by users who are assigned this policy to other enterprise users to be rerouted on the public switched telephone network (PSTN) if the WAN is congested or unavailable.</span></span> <span data-ttu-id="ab691-143">默认为启用。</span><span class="sxs-lookup"><span data-stu-id="ab691-143">Enabled by default.</span></span>
    
      - <span data-ttu-id="ab691-p113">通过**带宽策略覆盖**，管理员可以覆盖特定用户的呼叫允许控制策略决策。默认为禁用。</span><span class="sxs-lookup"><span data-stu-id="ab691-p113">**Bandwidth policy override** enables administrators to override call admission control policy decisions for a particular user. Disabled by default.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="ab691-p114">只能覆盖向用户发出的传入呼叫的策略，而不能覆盖由用户发出的传出呼叫的策略。建立会话后，将准确记录带宽消耗。应慎用此设置，且应保留对恰当的呼叫允许控制决策使用此设置。</span><span class="sxs-lookup"><span data-stu-id="ab691-p114">The policy will be overridden only for incoming calls to the user and not for outgoing calls that are placed by the user. After the session is established, the bandwidth consumption will be accurately recorded. This setting should be used sparingly and should be reserved for appropriate call admission control decisions.</span></span>

        
        </div>
    
      - <span data-ttu-id="ab691-149">**恶意的呼叫跟踪**使用户能够使用客户端 UI 报告恶意呼叫 (如炸弹威胁), 后者又将呼叫详细记录 (CDRs) 中的呼叫标记为。</span><span class="sxs-lookup"><span data-stu-id="ab691-149">**Malicious call tracing** enables users to report malicious calls (such as bomb threats) by using the client UI, which in turn flags the calls in the call detail records (CDRs).</span></span> <span data-ttu-id="ab691-150">默认为禁用。</span><span class="sxs-lookup"><span data-stu-id="ab691-150">Disabled by default.</span></span>

8.  <span data-ttu-id="ab691-151">要为此语音策略关联和配置 PSTN 用法记录，请执行以下任意操作：</span><span class="sxs-lookup"><span data-stu-id="ab691-151">To associate and configure PSTN usage records for this voice policy, do any of the following:</span></span>
    
      - <span data-ttu-id="ab691-p116">要从企业语音部署中提供的所有 PSTN 用法记录列表中选择一个或多个记录，请单击“选择”\*\*\*\*。突出显示要与此语音策略关联的记录，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ab691-p116">To choose one or more records from a list of all PSTN usage records available in your Enterprise Voice deployment, click **Select**. Highlight the records that you want to associate with this voice policy, and then click **OK**.</span></span>
    
      - <span data-ttu-id="ab691-154">要删除此语音策略中的某个 PSTN 用法记录，请突出显示相应的记录，然后单击“删除”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ab691-154">To remove a PSTN usage record from this voice policy, highlight the record and click **Remove**.</span></span>
    
      - <span data-ttu-id="ab691-155">要定义新的 PSTN 用法记录并将其与此语音策略相关联，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="ab691-155">To define a new PSTN usage record and associate it with this voice policy, do the following:</span></span>
        
        1.  <span data-ttu-id="ab691-156">单击“新建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ab691-156">Click **New**.</span></span>
        
        2.  <span data-ttu-id="ab691-p117">在“名称”\*\*\*\* 字段中，输入记录的唯一描述性名称。例如，您可能要为 Redmond 的全职员工创建名为 **Redmond** 的 PSTN 用法记录，而为临时员工创建名为 **RedmondTemps** 的 PSTN 用法记录。</span><span class="sxs-lookup"><span data-stu-id="ab691-p117">In the **Name** field, enter a unique descriptive name for the record. For example, you may want to create a PSTN usage record named **Redmond** for full-time employees located in Redmond, and another named **RedmondTemps** for temporary employees.</span></span>
            
            <div>
            

            > [!NOTE]  
            > <span data-ttu-id="ab691-p118">PSTN 用法记录名称在企业语音部署中必须是唯一的。保存记录后，将无法编辑“名称”<STRONG></STRONG>字段。</span><span class="sxs-lookup"><span data-stu-id="ab691-p118">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the <STRONG>Name</STRONG> field cannot be edited.</span></span>

            
            </div>
        
        3.  <span data-ttu-id="ab691-161">使用以下任意方法为此 PSTN 用法记录关联和配置路由：</span><span class="sxs-lookup"><span data-stu-id="ab691-161">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="ab691-162">要从企业语音部署中提供的所有路由列表中选择一个或多个路由，请单击“选择”\*\*\*\*，突出显示要与此 PSTN 用法记录相关联的路由，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ab691-162">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>
            
              - <span data-ttu-id="ab691-163">要删除 PSTN 用法记录中的某个路由，请突出显示该路由，然后单击“删除”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ab691-163">To remove a route from the PSTN usage record, highlight the route, and then click **Remove**.</span></span>
            
              - <span data-ttu-id="ab691-164">要定义新路由并将其与此 PSTN 用法记录关联，请单击“新建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ab691-164">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="ab691-165">有关详细信息, 请参阅[在 Lync Server 2013 中创建语音路由](lync-server-2013-create-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="ab691-165">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="ab691-166">要编辑已经与此 PSTN 用法记录相关联的路由，请突出显示相应的路由，然后单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ab691-166">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="ab691-167">有关详细信息, 请参阅[在 Lync Server 2013 中修改语音路由](lync-server-2013-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="ab691-167">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        4.  <span data-ttu-id="ab691-168">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="ab691-168">Click **OK**.</span></span>
    
      - <span data-ttu-id="ab691-169">要编辑已经与此语音策略相关联的 PSTN 用法记录，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="ab691-169">To edit a PSTN usage record that is already associated with this voice policy, do the following:</span></span>
        
        1.  <span data-ttu-id="ab691-170">突出显示要编辑的 PSTN 用法记录，然后单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ab691-170">Highlight the PSTN usage record that you want to edit, and then click **Show details**.</span></span>
        
        2.  <span data-ttu-id="ab691-171">使用以下任意方法为此 PSTN 用法记录关联和配置路由：</span><span class="sxs-lookup"><span data-stu-id="ab691-171">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="ab691-172">要从企业语音部署中提供的所有路由列表中选择一个或多个路由，请单击“选择”\*\*\*\*，突出显示要与此 PSTN 用法记录相关联的路由，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ab691-172">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes you want to associate with this PSTN usage record, and then click **OK**.</span></span>
            
              - <span data-ttu-id="ab691-173">要删除 PSTN 用法记录中的某个路由，请突出显示该路由，然后单击“删除”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ab691-173">To remove a route from this PSTN usage record, highlight the route, and then click **Remove**.</span></span>
            
              - <span data-ttu-id="ab691-174">要定义新路由并将其与此 PSTN 用法记录关联，请单击“新建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ab691-174">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="ab691-175">有关详细信息, 请参阅[在 Lync Server 2013 中创建语音路由](lync-server-2013-create-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="ab691-175">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="ab691-176">要编辑已经与此 PSTN 用法记录相关联的路由，请突出显示相应的路由，然后单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ab691-176">To edit a route that is already associated with this PSTN usage record, highlight the route and lick **Show details**.</span></span> <span data-ttu-id="ab691-177">有关详细信息, 请参阅[在 Lync Server 2013 中修改语音路由](lync-server-2013-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="ab691-177">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        3.  <span data-ttu-id="ab691-178">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="ab691-178">Click **OK**.</span></span>

9.  <span data-ttu-id="ab691-p123">排列 PSTN 用法记录以获得最佳性能。要更改记录在列表中的位置，请突出显示相应的记录名称，然后单击向上箭头或向下箭头。</span><span class="sxs-lookup"><span data-stu-id="ab691-p123">Arrange the PSTN usage records for optimum performance. To change a record’s position in the list, highlight the record name and click the up or down arrow.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="ab691-181">PSTN 用法记录在语音策略中的列出顺序十分重要。</span><span class="sxs-lookup"><span data-stu-id="ab691-181">The order in which PSTN usage records are listed in the voice policy is significant.</span></span> <span data-ttu-id="ab691-182">Lync 服务器从上到下遍历列表。</span><span class="sxs-lookup"><span data-stu-id="ab691-182">Lync Server traverses the list from the top down.</span></span> <span data-ttu-id="ab691-183">建议按使用频率来组织该列表，例如：RedmondLocal、RedmondLongDist、RedmondInternational 和 RedmondBackup。</span><span class="sxs-lookup"><span data-stu-id="ab691-183">We recommend that you organize the list by frequency of use, for example: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span></span>

    
    </div>

10. <span data-ttu-id="ab691-184">要在此语音策略中为呼叫转接和同时响铃关联和配置 PSTN 用法记录，请执行以下任意操作：</span><span class="sxs-lookup"><span data-stu-id="ab691-184">To associate and configure PSTN usage records for call forwarding and simultaneous ringing in this voice policy, do any of the following:</span></span>
    
      - <span data-ttu-id="ab691-185">要作为此语音策略将相同的 PSTN 用法记录用于呼叫转接和同时响铃，请从下拉菜单选择“使用呼叫 PSTN 用法进行路由”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ab691-185">To use the same PSTN usage records for call forwarding and simultaneous ringing as this voice policy, select the option **Route using the call PSTN usages** from the drop-down menu.</span></span>
    
      - <span data-ttu-id="ab691-186">若要仅允许呼叫转接和同时拨打内部 Lync 用户, 请从下拉菜单中选择 "**仅限内部 lync 用户的路由**" 选项。</span><span class="sxs-lookup"><span data-stu-id="ab691-186">To allow call forwarding and simultaneous ringing to internal Lync users only, select the option **Route to internal Lync users only** from the drop-down menu.</span></span> <span data-ttu-id="ab691-187">Calls will not be forwarded to external PSTN numbers.</span><span class="sxs-lookup"><span data-stu-id="ab691-187">Calls will not be forwarded to external PSTN numbers.</span></span>
    
      - <span data-ttu-id="ab691-p126">要为呼叫转接和同时响铃指定不同的 PSTN 用法记录，而不是用于此语音策略，请从下拉菜单选择选项“使用自定义 PSTN 用法路由”\*\*\*\*。此选项显示控制来选择现有的 PSTN 用法记录或创建专门用于呼叫转接和同时响铃的新 PSTN 用法记录。</span><span class="sxs-lookup"><span data-stu-id="ab691-p126">To specify different PSTN usage records for call forwarding and simultaneous ringing than used for this voice policy, select the option **Route using custom PSTN usages** from the drop-down menu. This option displays a control to select existing PSTN usage records or create new PSTN usage records specifically for call forwarding and simultaneous ringing.</span></span>
        
          - <span data-ttu-id="ab691-p127">要从用于呼叫转接和同时响铃 PSTN 用法记录列表中选择一个或多个记录，请单击“选择”\*\*\*\*。突出显示要与此呼叫转接和同时响铃策略关联的记录，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ab691-p127">To choose one or more records from a list of PSTN usage records for call forwarding and simultaneous ringing, click **Select**. Highlight the records that you want to associate with this call forwarding and simultaneous ringing policy, and then click **OK**.</span></span>
        
          - <span data-ttu-id="ab691-192">要从此呼叫转接和同时响铃策略删除 PSTN 用法记录，请突出显示该记录，然后单击“删除”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ab691-192">To remove a PSTN usage record from this call forwarding and simultaneous ringing policy, highlight the record and click **Remove**.</span></span>
        
          - <span data-ttu-id="ab691-193">要定义新的 PSTN 用法记录并将其与此呼叫转接和同时响铃策略相关联，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="ab691-193">To define a new PSTN usage record and associate it with this call forwarding and simultaneous ringing policy, do the following:</span></span>
            
            1.  <span data-ttu-id="ab691-194">单击“新建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ab691-194">Click **New**.</span></span>
            
            2.  <span data-ttu-id="ab691-195">在“名称”\*\*\*\* 字段中，输入记录的唯一描述性名称。</span><span class="sxs-lookup"><span data-stu-id="ab691-195">In the **Name** field, enter a unique descriptive name for the record.</span></span>
                
                <div>
                

                > [!NOTE]  
                > <span data-ttu-id="ab691-p128">PSTN 用法记录名称在企业语音部署中必须是唯一的。保存记录后，将无法编辑“名称”<STRONG></STRONG>字段。</span><span class="sxs-lookup"><span data-stu-id="ab691-p128">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the <STRONG>Name</STRONG> field cannot be edited.</span></span>

                
                </div>
            
            3.  <span data-ttu-id="ab691-198">使用以下任意方法为此 PSTN 用法记录关联和配置路由：</span><span class="sxs-lookup"><span data-stu-id="ab691-198">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
                
                  - <span data-ttu-id="ab691-199">要从企业语音部署中提供的所有路由列表中选择一个或多个路由，请单击“选择”\*\*\*\*，突出显示要与此 PSTN 用法记录相关联的路由，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ab691-199">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>
                
                  - <span data-ttu-id="ab691-200">要删除 PSTN 用法记录中的某个路由，请突出显示相应的路由，然后单击“删除”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ab691-200">To remove a route from the PSTN usage record, highlight the route and click **Remove**.</span></span>
                
                  - <span data-ttu-id="ab691-201">要定义新路由并将其与此 PSTN 用法记录关联，请单击“新建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ab691-201">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="ab691-202">有关详细信息, 请参阅[在 Lync Server 2013 中创建语音路由](lync-server-2013-create-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="ab691-202">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
                
                  - <span data-ttu-id="ab691-203">要编辑已经与此 PSTN 用法记录相关联的路由，请突出显示相应的路由，然后单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ab691-203">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="ab691-204">有关详细信息, 请参阅[在 Lync Server 2013 中修改语音路由](lync-server-2013-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="ab691-204">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
            
            4.  <span data-ttu-id="ab691-205">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="ab691-205">Click **OK**.</span></span>
        
          - <span data-ttu-id="ab691-206">要编辑已经与此语音策略相关联的 PSTN 用法记录，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="ab691-206">To edit a PSTN usage record that is already associated with this voice policy, do the following:</span></span>
            
            1.  <span data-ttu-id="ab691-207">突出显示要编辑的 PSTN 用法记录，然后单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ab691-207">Highlight the PSTN usage record you want to edit and click **Show details**.</span></span>
            
            2.  <span data-ttu-id="ab691-208">使用以下任意方法为此 PSTN 用法记录关联和配置路由：</span><span class="sxs-lookup"><span data-stu-id="ab691-208">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
                
                  - <span data-ttu-id="ab691-209">要从企业语音部署中提供的所有路由列表中选择一个或多个路由，请单击“选择”\*\*\*\*，突出显示要与此 PSTN 用法记录相关联的路由，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ab691-209">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>
                
                  - <span data-ttu-id="ab691-210">要删除此 PSTN 用法记录中的某个路由，请突出显示相应的路由，然后单击“删除”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ab691-210">To remove a route from this PSTN usage record, highlight the route and click **Remove**.</span></span>
                
                  - <span data-ttu-id="ab691-211">要定义新路由并将其与此 PSTN 用法记录关联，请单击“新建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ab691-211">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="ab691-212">有关详细信息, 请参阅[在 Lync Server 2013 中创建语音路由](lync-server-2013-create-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="ab691-212">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
                
                  - <span data-ttu-id="ab691-213">要编辑已经与此 PSTN 用法记录相关联的路由，请突出显示相应的路由，然后单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ab691-213">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="ab691-214">有关详细信息, 请参阅[在 Lync Server 2013 中修改语音路由](lync-server-2013-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="ab691-214">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
            
            3.  <span data-ttu-id="ab691-215">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="ab691-215">Click **OK**.</span></span>

11. <span data-ttu-id="ab691-p133">（可选）输入一个号码来测试语音策略，然后单击“执行”\*\*\*\*。测试结果会显示在“要测试的转换号码”\*\*\*\* 下。</span><span class="sxs-lookup"><span data-stu-id="ab691-p133">(Optional) Enter a number to test the voice policy and click **Go**. The test results are displayed under **Translated number to test**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ab691-218">你可以保存尚未通过测试的语音策略, 然后在稍后重新配置它。</span><span class="sxs-lookup"><span data-stu-id="ab691-218">You can save a voice policy that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="ab691-219">有关详细信息, 请参阅<A href="lync-server-2013-test-voice-routing.md">在 Lync Server 2013 中测试语音路由</A>。</span><span class="sxs-lookup"><span data-stu-id="ab691-219">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

12. <span data-ttu-id="ab691-220">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="ab691-220">Click **OK**.</span></span>

13. <span data-ttu-id="ab691-221">在“语音策略”\*\*\*\* 页上，单击“提交”\*\*\*\*，然后单击“全部提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ab691-221">On the **Voice Policy** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ab691-222">任何时候创建或修改语音策略，都必须运行“全部提交”<STRONG></STRONG>命令以发布配置更改。</span><span class="sxs-lookup"><span data-stu-id="ab691-222">Any time you create or modify a voice policy, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="ab691-223">有关详细信息, 请参阅操作文档中的<A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 中的 "发布待处理的语音路由配置更改"</A> 。</span><span class="sxs-lookup"><span data-stu-id="ab691-223">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

14. <span data-ttu-id="ab691-224">（可选）语音邮件规避检测到用户的手机语音邮件立即应答了一个呼叫，因此将断开至移动电话语音邮件的呼叫。</span><span class="sxs-lookup"><span data-stu-id="ab691-224">(Optional) Voicemail Escape detects that a call was immediately answered by the user’s mobile phone voice mail, and disconnects the call to the mobile phone voice mail.</span></span> <span data-ttu-id="ab691-225">这将允许此呼叫继续在用户的其他终结点上响铃，以使用户能够应答呼叫。</span><span class="sxs-lookup"><span data-stu-id="ab691-225">This allows the call to continue to ring on the user’s other endpoints giving the user the opportunity to answer the call.</span></span> <span data-ttu-id="ab691-226">有关如何配置语音邮件策略的详细信息, 请参阅[在 Lync Server 2013 中配置语音邮件转义](lync-server-2013-configuring-voice-mail-escape.md)。</span><span class="sxs-lookup"><span data-stu-id="ab691-226">For details on how to configure a voice mail policy, see [Configuring voice mail escape in Lync Server 2013](lync-server-2013-configuring-voice-mail-escape.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ab691-227">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ab691-227">See Also</span></span>


[<span data-ttu-id="ab691-228">在 Lync Server 2013 中修改语音策略和配置 PSTN 使用记录</span><span class="sxs-lookup"><span data-stu-id="ab691-228">Modify a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
[<span data-ttu-id="ab691-229">在 Lync Server 2013 中查看 PSTN 使用记录</span><span class="sxs-lookup"><span data-stu-id="ab691-229">View PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-view-pstn-usage-records.md)  
[<span data-ttu-id="ab691-230">在 Lync Server 2013 中创建语音路由</span><span class="sxs-lookup"><span data-stu-id="ab691-230">Create a voice route in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-route.md)  
[<span data-ttu-id="ab691-231">在 Lync Server 2013 中修改语音路由</span><span class="sxs-lookup"><span data-stu-id="ab691-231">Modify a voice route in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-route.md)  
[<span data-ttu-id="ab691-232">将挂起的更改发布到 Lync Server 2013 中的语音路由配置</span><span class="sxs-lookup"><span data-stu-id="ab691-232">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  
[<span data-ttu-id="ab691-233">在 Lync Server 2013 中配置语音邮件转义</span><span class="sxs-lookup"><span data-stu-id="ab691-233">Configuring voice mail escape in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-mail-escape.md)  


[<span data-ttu-id="ab691-234">在 Lync Server 2013 中测试语音路由</span><span class="sxs-lookup"><span data-stu-id="ab691-234">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

