---
title: 在 Skype for Business 中创建或修改语音策略和配置 PSTN 使用记录
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
ms.assetid: e6ff27e0-e2d1-4445-840f-08f738200c20
description: '摘要: 使用 Skype for Business 服务器控制面板创建或修改语音策略和配置 PSTN 使用记录。'
ms.openlocfilehash: 76ce531eab2eb88b9a62c4bc38aae1e899802084
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239927"
---
# <a name="create-or-modify-a-voice-policy-and-configure-pstn-usage-records-in-skype-for-business"></a><span data-ttu-id="add85-103">在 Skype for Business 中创建或修改语音策略和配置 PSTN 使用记录</span><span class="sxs-lookup"><span data-stu-id="add85-103">Create or modify a voice policy and configure PSTN usage records in Skype for Business</span></span>

<span data-ttu-id="add85-104">**摘要:** 使用 Skype for Business 服务器控制面板创建或修改语音策略和配置 PSTN 使用记录。</span><span class="sxs-lookup"><span data-stu-id="add85-104">**Summary:** Create or modify voice policies and configure PSTN usage records by using the Skype for Business Server Control Panel.</span></span>

> [!NOTE]
> <span data-ttu-id="add85-105">每个语音策略必须至少具有一条关联的公用电话交换网 (PSTN) 用法记录。</span><span class="sxs-lookup"><span data-stu-id="add85-105">Each voice policy must have at least one associated Public Switched Telephone Network (PSTN) usage record.</span></span> <span data-ttu-id="add85-106">若要查看企业语音部署中可用的所有 PSTN 使用记录的列表, 并查看其属性, 请参阅[在 Skype For business 中查看 pstn 使用记录](view-pstn-usage-records.md)。</span><span class="sxs-lookup"><span data-stu-id="add85-106">To see a listing of all PSTN usage records available in your Enterprise Voice deployment and view their properties, see [View PSTN usage records in Skype for Business](view-pstn-usage-records.md).</span></span>

### <a name="to-create-a-voice-policy"></a><span data-ttu-id="add85-107">创建语音策略</span><span class="sxs-lookup"><span data-stu-id="add85-107">To create a voice policy</span></span>

1. <span data-ttu-id="add85-108">打开 "Skype for Business 服务器" 控制面板。</span><span class="sxs-lookup"><span data-stu-id="add85-108">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="add85-109">在左侧导航栏中，单击“语音路由”\*\*\*\*，然后单击“语音策略”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="add85-109">In the left navigation bar, click **Voice Routing** and then click **Voice Policy**.</span></span>

3. <span data-ttu-id="add85-110">在“语音策略”\*\*\*\* 页上，单击“新建”\*\*\*\*，然后选择新策略的作用域：</span><span class="sxs-lookup"><span data-stu-id="add85-110">On the **Voice Policy** page, click **New** and then select a scope for the new policy:</span></span>

   - <span data-ttu-id="add85-p102">**站点策略**将应用于整个站点，分配给用户策略的任何用户或组除外。如果选择了“Site”作为策略作用域，请从“选择站点”\*\*\*\* 对话框中选择站点。如果已经为站点创建了语音策略，则该站点不会显示在“选择站点”\*\*\*\* 对话框中。</span><span class="sxs-lookup"><span data-stu-id="add85-p102">**Site policy** applies to an entire site, except any users or groups that are assigned to a user policy. If you select Site for a policy scope, choose the site from the **Select a Site** dialog box. If a voice policy has already been created for a site, the site does not appear in the **Select a Site** dialog box.</span></span>

   - <span data-ttu-id="add85-114">**用户策略**可应用于指定的用户或组。</span><span class="sxs-lookup"><span data-stu-id="add85-114">**User policy** can be applied to specified users or groups.</span></span>

4. <span data-ttu-id="add85-115">如果语音策略作用域为“用户”，请在“名称”\*\*\*\* 字段中输入策略的描述性名称。</span><span class="sxs-lookup"><span data-stu-id="add85-115">If the voice policy scope is User, enter a descriptive name for the policy in the **Name** field.</span></span>

    > [!NOTE]
    > <span data-ttu-id="add85-116">如果语音策略作用域为“Site”，将用站点名称填充“新建语音策略”\*\*\*\* 中的“名称”\*\*\*\* 字段，并且无法更改。</span><span class="sxs-lookup"><span data-stu-id="add85-116">If the voice policy scope is Site, the **Name** field in **New Voice Policy** is prepopulated with the site name and cannot be changed.</span></span>

5. <span data-ttu-id="add85-117">（可选）输入语音策略的其他描述性信息。</span><span class="sxs-lookup"><span data-stu-id="add85-117">(Optional) Enter additional descriptive information for the voice policy.</span></span>

6. <span data-ttu-id="add85-118">选中或清除以下复选框以启用或禁用该语音策略的每种“呼叫功能”\*\*\*\*：</span><span class="sxs-lookup"><span data-stu-id="add85-118">Select or clear the following check boxes to enable or disable each of the **Calling features** for this voice policy:</span></span>

   - <span data-ttu-id="add85-119">**语音邮件转义**可防止呼叫直接路由到用户的移动电话语音邮件系统, 同时拨打同时拨打的电话、关闭电池或超出范围。</span><span class="sxs-lookup"><span data-stu-id="add85-119">**Voice mail escape** prevents calls from being immediately routed to the user's mobile phone voice mail system when simultaneous ringing is configured and the phone is turned off, out of battery, or out of range.</span></span>

     > [!NOTE]
     > <span data-ttu-id="add85-120">此功能只能通过 Skype for Business Server Management Shell 进行配置</span><span class="sxs-lookup"><span data-stu-id="add85-120">This feature is only configurable through the Skype for Business Server Management Shell</span></span>

   - <span data-ttu-id="add85-121">通过**呼叫转接**，用户可以将呼叫转接到其他电话或客户端设备。</span><span class="sxs-lookup"><span data-stu-id="add85-121">**Call forwarding** enables users to forward calls to other phones and client devices.</span></span> <span data-ttu-id="add85-122">Skype for business 服务器为呼叫转接提供了一系列更广泛的配置选项。</span><span class="sxs-lookup"><span data-stu-id="add85-122">Skype for Business Server provides a significantly wider range of configuration options for call forwarding.</span></span> <span data-ttu-id="add85-123">例如，如果组织不允许将传入呼叫外部转接到 PSTN，则管理员可应用特定语音策略来部署此限制。</span><span class="sxs-lookup"><span data-stu-id="add85-123">For example, if an organization does not want to allow incoming calls to be forwarded externally to the PSTN, an administrator can apply a special voice policy to deploy this restriction.</span></span> <span data-ttu-id="add85-124">默认为启用。</span><span class="sxs-lookup"><span data-stu-id="add85-124">Enabled by default.</span></span>

   - <span data-ttu-id="add85-125">通过**委派**，用户可以指定其他用户代表他们发送和接收呼叫。</span><span class="sxs-lookup"><span data-stu-id="add85-125">**Delegation** enables users to specify other users to send and receive calls on their behalf.</span></span> <span data-ttu-id="add85-126">在 Skype for Business 服务器中, 代理人可以配置同时拨打的电话, 让他/她的经理拨出所有代理人同时拨打的目标电话。</span><span class="sxs-lookup"><span data-stu-id="add85-126">In Skype for Business Server, a delegate can configure simultaneous ringing that enables incoming calls to his or her manager to ring all of the delegate's simultaneous ringing targets.</span></span> <span data-ttu-id="add85-127">这会向委派提供极大的灵活性以响应直接传到经理的呼叫。</span><span class="sxs-lookup"><span data-stu-id="add85-127">This provides the delegate with greater flexibility in responding to calls directed to the manager.</span></span> <span data-ttu-id="add85-128">默认为启用。</span><span class="sxs-lookup"><span data-stu-id="add85-128">Enabled by default.</span></span>

   - <span data-ttu-id="add85-129">通过**呼叫转移**，用户可以将呼叫转移到其他用户。</span><span class="sxs-lookup"><span data-stu-id="add85-129">**Call transfer** enables users to transfer calls to other users.</span></span> <span data-ttu-id="add85-130">默认为启用。</span><span class="sxs-lookup"><span data-stu-id="add85-130">Enabled by default.</span></span>

   - <span data-ttu-id="add85-p106">通过 **呼叫寄存**，用户可以寄存呼叫，将其置于保持状态，然后从其他电话或客户端接听呼叫。默认为禁用。</span><span class="sxs-lookup"><span data-stu-id="add85-p106">**Call park** enables users to park calls on hold and then pick up the call from a different phone or client. Disabled by default.</span></span>

   - <span data-ttu-id="add85-133">**同时响铃**使来电可以在其他电话（例如，移动电话）或其他终结点设备上响铃。</span><span class="sxs-lookup"><span data-stu-id="add85-133">**Simultaneous ringing** enables incoming calls to ring on additional phones (for example, a mobile phone) or other endpoint devices.</span></span> <span data-ttu-id="add85-134">Skype for business 服务器为同时拨打的配置选项提供了一系列更广泛的配置选项。</span><span class="sxs-lookup"><span data-stu-id="add85-134">Skype for Business Server provides a significantly wider range of configuration options for simultaneous ringing.</span></span> <span data-ttu-id="add85-135">默认为启用。</span><span class="sxs-lookup"><span data-stu-id="add85-135">Enabled by default.</span></span>

   - <span data-ttu-id="add85-p108">通过**团队呼叫**，指定团队中的用户可以为团队中的其他成员应答呼叫。默认为启用。</span><span class="sxs-lookup"><span data-stu-id="add85-p108">**Team call** enables users on a defined team to answer calls for other members of the team. Enabled by default.</span></span>

   - <span data-ttu-id="add85-p109">**PSTN 重新路由**可以在 WAN 拥堵或不可用时在 PSTN 上重新路由分配有此策略的用户向其他企业用户发出的呼叫。默认为启用。</span><span class="sxs-lookup"><span data-stu-id="add85-p109">**PSTN re-route** enables calls made by users who are assigned this policy to other enterprise users to be rerouted on the PSTN if the WAN is congested or unavailable. Enabled by default.</span></span>

   - <span data-ttu-id="add85-p110">通过**带宽策略覆盖**，管理员可以覆盖特定用户的呼叫允许控制策略决策。默认为禁用。</span><span class="sxs-lookup"><span data-stu-id="add85-p110">**Bandwidth policy override** enables administrators to override call admission control policy decisions for a particular user. Disabled by default.</span></span>

     > [!NOTE]
     > <span data-ttu-id="add85-p111">只能覆盖向用户发出的传入呼叫的策略，而不能覆盖由用户发出的传出呼叫的策略。建立会话后，将准确记录带宽消耗。应慎用此设置，且应保留对恰当的呼叫允许控制决策使用此设置。</span><span class="sxs-lookup"><span data-stu-id="add85-p111">The policy will be overridden only for incoming calls to the user and not for outgoing calls that are placed by the user. After the session is established, the bandwidth consumption will be accurately recorded. This setting should be used sparingly and should be reserved for appropriate call admission control decisions.</span></span>

   - <span data-ttu-id="add85-p112">通过**恶意呼叫跟踪**，用户可以通过使用客户端 UI 报告恶意呼叫（如威胁），接下来在呼叫详细记录 (CDR) 中标记呼叫。默认为禁用。</span><span class="sxs-lookup"><span data-stu-id="add85-p112">**Malicious call tracing** enables users to report malicious calls (such as threats) by using the client UI, which in turn flags the calls in the Call Detail Records (CDRs). Disabled by default.</span></span>

   - <span data-ttu-id="add85-147">"**忙碌" 选项**启用或禁用指定语音策略的 "忙" 选项。</span><span class="sxs-lookup"><span data-stu-id="add85-147">**Busy options** enables or disables Busy Options for the specified voice policy.</span></span> <span data-ttu-id="add85-148">如果呼叫的目标用户在手机上, 则 "忙碌" 选项允许将传入呼叫路由到语音邮件或使用占线信号拒绝传入呼叫。</span><span class="sxs-lookup"><span data-stu-id="add85-148">Busy Options allows incoming calls to be routed to voice mail or rejected with a busy signal when the call's target user is on the phone.</span></span> <span data-ttu-id="add85-149">"忙碌" 选项是2016年7月累积更新中引入的新语音策略。</span><span class="sxs-lookup"><span data-stu-id="add85-149">Busy Options is a new voice policy introduced in the July 2016 Cumulative Update.</span></span> <span data-ttu-id="add85-150">选中此参数可启用 Busy 选项, 并且取消选中它将禁用 "忙" 选项。</span><span class="sxs-lookup"><span data-stu-id="add85-150">Checking this parameter enables Busy Options, and unchecking it disables Busy Options.</span></span> <span data-ttu-id="add85-151">有关详细信息, 请参阅为 Skype for business[服务器计划 "忙碌选项](../../plan-your-deployment/enterprise-voice-solution/busy-options.md)" 和 "为[Skype For business 服务器安装和配置 busy 选项](install-and-configure-busy-options.md)"。</span><span class="sxs-lookup"><span data-stu-id="add85-151">For more information, see [Plan for Busy Options for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/busy-options.md) and [Install and configure Busy Options for Skype for Business Server](install-and-configure-busy-options.md).</span></span>

7. <span data-ttu-id="add85-152">要为此语音策略关联和配置 PSTN 用法记录，请执行以下任意操作：</span><span class="sxs-lookup"><span data-stu-id="add85-152">To associate and configure PSTN usage records for this voice policy, do any of the following:</span></span>

   - <span data-ttu-id="add85-p114">要从企业语音部署中提供的所有 PSTN 用法记录列表中选择一个或多个记录，请单击“选择”\*\*\*\*。突出显示要与此语音策略关联的记录，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="add85-p114">To choose one or more records from a list of all PSTN usage records available in your Enterprise Voice deployment, click **Select**. Highlight the records that you want to associate with this voice policy, and then click **OK**.</span></span>

   - <span data-ttu-id="add85-155">要删除此语音策略中的某个 PSTN 用法记录，请突出显示相应的记录，然后单击“删除”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="add85-155">To remove a PSTN usage record from this voice policy, highlight the record and click **Remove**.</span></span>

   - <span data-ttu-id="add85-156">要定义新的 PSTN 用法记录并将其与此语音策略相关联，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="add85-156">To define a new PSTN usage record and associate it with this voice policy, do the following:</span></span>

     <span data-ttu-id="add85-157">a.</span><span class="sxs-lookup"><span data-stu-id="add85-157">a.</span></span> <span data-ttu-id="add85-158">单击“新建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="add85-158">Click **New**.</span></span>

     <span data-ttu-id="add85-159">b.</span><span class="sxs-lookup"><span data-stu-id="add85-159">b.</span></span> <span data-ttu-id="add85-160">在“名称”\*\*\*\* 字段中，输入记录的唯一描述性名称。</span><span class="sxs-lookup"><span data-stu-id="add85-160">In the **Name** field, enter a unique descriptive name for the record.</span></span> <span data-ttu-id="add85-161">例如, 你可能希望为位于 Redmond 的全职员工创建 PSTN 使用记录 namedRedmond, 并为临时员工创建另一个 namedRedmondTemps。</span><span class="sxs-lookup"><span data-stu-id="add85-161">For example, you may want to create a PSTN usage record namedRedmond for full-time employees located in Redmond, and another namedRedmondTemps for temporary employees.</span></span>

     > [!NOTE]
     > <span data-ttu-id="add85-p117">PSTN 用法记录名称在企业语音部署中必须是唯一的。保存记录后，将无法编辑“名称”\*\*\*\* 字段。</span><span class="sxs-lookup"><span data-stu-id="add85-p117">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the **Name** field cannot be edited.</span></span>

     <span data-ttu-id="add85-164">c.</span><span class="sxs-lookup"><span data-stu-id="add85-164">c.</span></span> <span data-ttu-id="add85-165">使用以下任意方法为此 PSTN 用法记录关联和配置路由：</span><span class="sxs-lookup"><span data-stu-id="add85-165">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>

   - <span data-ttu-id="add85-166">要从企业语音部署中提供的所有路由列表中选择一个或多个路由，请单击“选择”\*\*\*\*，突出显示要与此 PSTN 用法记录相关联的路由，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="add85-166">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>

   - <span data-ttu-id="add85-167">要删除 PSTN 用法记录中的某个路由，请突出显示该路由，然后单击“删除”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="add85-167">To remove a route from the PSTN usage record, highlight the route, and then click **Remove**.</span></span>

   - <span data-ttu-id="add85-168">要定义新路由并将其与此 PSTN 用法记录关联，请单击“新建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="add85-168">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="add85-169">有关详细信息, 请参阅[在 Skype For business 中创建或修改语音路线](create-or-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="add85-169">For details, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span>

   - <span data-ttu-id="add85-170">要编辑已经与此 PSTN 用法记录相关联的路由，请突出显示相应的路由，然后单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="add85-170">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span>

     <span data-ttu-id="add85-171">d.</span><span class="sxs-lookup"><span data-stu-id="add85-171">d.</span></span> <span data-ttu-id="add85-172">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="add85-172">Click **OK**.</span></span>

   - <span data-ttu-id="add85-173">要编辑已经与此语音策略相关联的 PSTN 用法记录，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="add85-173">To edit a PSTN usage record that is already associated with this voice policy, do the following:</span></span>

     <span data-ttu-id="add85-174">a.</span><span class="sxs-lookup"><span data-stu-id="add85-174">a.</span></span> <span data-ttu-id="add85-175">突出显示要编辑的 PSTN 用法记录，然后单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="add85-175">Highlight the PSTN usage record that you want to edit, and then click **Show details**.</span></span>

     <span data-ttu-id="add85-176">b.</span><span class="sxs-lookup"><span data-stu-id="add85-176">b.</span></span> <span data-ttu-id="add85-177">使用以下任意方法为此 PSTN 用法记录关联和配置路由：</span><span class="sxs-lookup"><span data-stu-id="add85-177">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>

   - <span data-ttu-id="add85-178">要从企业语音部署中提供的所有路由列表中选择一个或多个路由，请单击“选择”\*\*\*\*，突出显示要与此 PSTN 用法记录相关联的路由，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="add85-178">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes you want to associate with this PSTN usage record, and then click **OK**.</span></span>

   - <span data-ttu-id="add85-179">要删除 PSTN 用法记录中的某个路由，请突出显示该路由，然后单击“删除”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="add85-179">To remove a route from this PSTN usage record, highlight the route, and then click **Remove**.</span></span>

   - <span data-ttu-id="add85-180">要定义新路由并将其与此 PSTN 用法记录关联，请单击“新建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="add85-180">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="add85-181">有关详细信息, 请参阅[在 Skype For business 中创建或修改语音路线](create-or-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="add85-181">For details, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span>

   - <span data-ttu-id="add85-182">要编辑已经与此 PSTN 用法记录相关联的路由，请突出显示相应的路由，然后单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="add85-182">To edit a route that is already associated with this PSTN usage record, highlight the route and lick **Show details**.</span></span>

     <span data-ttu-id="add85-183">c.</span><span class="sxs-lookup"><span data-stu-id="add85-183">c.</span></span> <span data-ttu-id="add85-184">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="add85-184">Click **OK**.</span></span>

8. <span data-ttu-id="add85-185">排列 PSTN 用法记录以获得最佳性能。</span><span class="sxs-lookup"><span data-stu-id="add85-185">Arrange the PSTN usage records for optimum performance.</span></span> <span data-ttu-id="add85-186">若要更改记录在列表中的位置, 请突出显示记录名称, 然后单击向上或向下箭头。</span><span class="sxs-lookup"><span data-stu-id="add85-186">To change a record's position in the list, highlight the record name and click the up or down arrow.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="add85-187">PSTN 用法记录在语音策略中的列出顺序十分重要。</span><span class="sxs-lookup"><span data-stu-id="add85-187">The order in which PSTN usage records are listed in the voice policy is significant.</span></span> <span data-ttu-id="add85-188">Skype for Business 服务器从上到下遍历列表。</span><span class="sxs-lookup"><span data-stu-id="add85-188">Skype for Business Server traverses the list from the top down.</span></span> <span data-ttu-id="add85-189">建议按使用频率来组织该列表，例如：RedmondLocal、RedmondLongDist、RedmondInternational 和 RedmondBackup。</span><span class="sxs-lookup"><span data-stu-id="add85-189">We recommend that you organize the list by frequency of use, for example: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span></span>

9. <span data-ttu-id="add85-190">要在此语音策略中为呼叫转接和同时响铃关联和配置 PSTN 用法记录，请执行以下任意操作：</span><span class="sxs-lookup"><span data-stu-id="add85-190">To associate and configure PSTN usage records for call forwarding and simultaneous ringing in this voice policy, do any of the following:</span></span>

   - <span data-ttu-id="add85-191">要作为此语音策略将相同的 PSTN 用法记录用于呼叫转接和同时响铃，请从下拉菜单选择“使用呼叫 PSTN 用法进行路由”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="add85-191">To use the same PSTN usage records for call forwarding and simultaneous ringing as this voice policy, select the option **Route using the call PSTN usages** from the drop-down menu.</span></span>

   - <span data-ttu-id="add85-192">若要允许呼叫转接和同时拨打内部 Skype for Business 用户, 请从下拉菜单中选择**仅限内部 skype for business 用户**的 "发送" 选项。</span><span class="sxs-lookup"><span data-stu-id="add85-192">To allow call forwarding and simultaneous ringing to internal Skype for Business users only, select the option **Route to internal Skype for Business users only** from the drop-down menu.</span></span> <span data-ttu-id="add85-193">Calls will not be forwarded to external PSTN numbers.</span><span class="sxs-lookup"><span data-stu-id="add85-193">Calls will not be forwarded to external PSTN numbers.</span></span>

   - <span data-ttu-id="add85-p128">要为呼叫转接和同时响铃指定不同的 PSTN 用法记录，而不是用于此语音策略，请从下拉菜单选择选项“使用自定义 PSTN 用法路由”\*\*\*\*。此选项显示控制来选择现有的 PSTN 用法记录或创建专门用于呼叫转接和同时响铃的新 PSTN 用法记录。</span><span class="sxs-lookup"><span data-stu-id="add85-p128">To specify different PSTN usage records for call forwarding and simultaneous ringing than used for this voice policy, select the option **Route using custom PSTN usages** from the drop-down menu. This option displays a control to select existing PSTN usage records or create new PSTN usage records specifically for call forwarding and simultaneous ringing.</span></span>

   - <span data-ttu-id="add85-p129">要从用于呼叫转接和同时响铃 PSTN 用法记录列表中选择一个或多个记录，请单击“选择”\*\*\*\*。突出显示要与此呼叫转接和同时响铃策略关联的记录，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="add85-p129">To choose one or more records from a list of PSTN usage records for call forwarding and simultaneous ringing, click **Select**. Highlight the records that you want to associate with this call forwarding and simultaneous ringing policy, and then click **OK**.</span></span>

   - <span data-ttu-id="add85-198">要从此呼叫转接和同时响铃策略删除 PSTN 用法记录，请突出显示该记录，然后单击“删除”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="add85-198">To remove a PSTN usage record from this call forwarding and simultaneous ringing policy, highlight the record and click **Remove**.</span></span>

   - <span data-ttu-id="add85-199">要定义新的 PSTN 用法记录并将其与此呼叫转接和同时响铃策略相关联，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="add85-199">To define a new PSTN usage record and associate it with this call forwarding and simultaneous ringing policy, do the following:</span></span>

     <span data-ttu-id="add85-200">a.</span><span class="sxs-lookup"><span data-stu-id="add85-200">a.</span></span> <span data-ttu-id="add85-201">单击“新建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="add85-201">Click **New**.</span></span>

     <span data-ttu-id="add85-202">b.</span><span class="sxs-lookup"><span data-stu-id="add85-202">b.</span></span> <span data-ttu-id="add85-203">在“名称”\*\*\*\* 字段中，输入记录的唯一描述性名称。</span><span class="sxs-lookup"><span data-stu-id="add85-203">In the **Name** field, enter a unique descriptive name for the record.</span></span>

     > [!NOTE]
     > <span data-ttu-id="add85-p132">PSTN 用法记录名称在企业语音部署中必须是唯一的。保存记录后，将无法编辑“名称”\*\*\*\* 字段。</span><span class="sxs-lookup"><span data-stu-id="add85-p132">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the **Name** field cannot be edited.</span></span>

     <span data-ttu-id="add85-206">c.</span><span class="sxs-lookup"><span data-stu-id="add85-206">c.</span></span> <span data-ttu-id="add85-207">使用以下任意方法为此 PSTN 用法记录关联和配置路由：</span><span class="sxs-lookup"><span data-stu-id="add85-207">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>

   - <span data-ttu-id="add85-208">要从企业语音部署中提供的所有路由列表中选择一个或多个路由，请单击“选择”\*\*\*\*，突出显示要与此 PSTN 用法记录相关联的路由，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="add85-208">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>

   - <span data-ttu-id="add85-209">要删除 PSTN 用法记录中的某个路由，请突出显示相应的路由，然后单击“删除”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="add85-209">To remove a route from the PSTN usage record, highlight the route and click **Remove**.</span></span>

   - <span data-ttu-id="add85-210">要定义新路由并将其与此 PSTN 用法记录关联，请单击“新建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="add85-210">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="add85-211">有关详细信息, 请参阅[在 Skype For business 中创建或修改语音路线](create-or-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="add85-211">For details, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span>

   - <span data-ttu-id="add85-212">要编辑已经与此 PSTN 用法记录相关联的路由，请突出显示相应的路由，然后单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="add85-212">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span>

     <span data-ttu-id="add85-213">d.</span><span class="sxs-lookup"><span data-stu-id="add85-213">d.</span></span> <span data-ttu-id="add85-214">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="add85-214">Click **OK**.</span></span>

   - <span data-ttu-id="add85-215">要编辑已经与此语音策略相关联的 PSTN 用法记录，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="add85-215">To edit a PSTN usage record that is already associated with this voice policy, do the following:</span></span>

     <span data-ttu-id="add85-216">a.</span><span class="sxs-lookup"><span data-stu-id="add85-216">a.</span></span> <span data-ttu-id="add85-217">突出显示要编辑的 PSTN 用法记录，然后单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="add85-217">Highlight the PSTN usage record you want to edit and click **Show details**.</span></span>

     <span data-ttu-id="add85-218">b.</span><span class="sxs-lookup"><span data-stu-id="add85-218">b.</span></span> <span data-ttu-id="add85-219">使用以下任意方法为此 PSTN 用法记录关联和配置路由：</span><span class="sxs-lookup"><span data-stu-id="add85-219">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>

   - <span data-ttu-id="add85-220">要从企业语音部署中提供的所有路由列表中选择一个或多个路由，请单击“选择”\*\*\*\*，突出显示要与此 PSTN 用法记录相关联的路由，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="add85-220">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>

   - <span data-ttu-id="add85-221">要删除此 PSTN 用法记录中的某个路由，请突出显示相应的路由，然后单击“删除”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="add85-221">To remove a route from this PSTN usage record, highlight the route and click **Remove**.</span></span>

   - <span data-ttu-id="add85-222">要定义新路由并将其与此 PSTN 用法记录关联，请单击“新建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="add85-222">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="add85-223">有关详细信息, 请参阅[在 Skype For business 中创建或修改语音路线](create-or-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="add85-223">For details, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span>

   - <span data-ttu-id="add85-224">要编辑已经与此 PSTN 用法记录相关联的路由，请突出显示相应的路由，然后单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="add85-224">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span>

     <span data-ttu-id="add85-225">c.</span><span class="sxs-lookup"><span data-stu-id="add85-225">c.</span></span> <span data-ttu-id="add85-226">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="add85-226">Click **OK**.</span></span>

10. <span data-ttu-id="add85-p140">（可选）输入一个号码来测试语音策略，然后单击“执行”\*\*\*\*。测试结果会显示在“要测试的转换号码”\*\*\*\* 下。</span><span class="sxs-lookup"><span data-stu-id="add85-p140">(Optional) Enter a number to test the voice policy and click **Go**. The test results are displayed under **Translated number to test**.</span></span>

11. <span data-ttu-id="add85-229">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="add85-229">Click **OK**.</span></span>

12. <span data-ttu-id="add85-230">在“语音策略”\*\*\*\* 页上，单击“提交”\*\*\*\*，然后单击“全部提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="add85-230">On the **Voice Policy** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="add85-231">任何时候创建或修改语音策略，都必须运行“全部提交”\*\*\*\* 命令以发布配置更改。</span><span class="sxs-lookup"><span data-stu-id="add85-231">Any time you create or modify a voice policy, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="add85-232">有关详细信息, 请参阅操作文档中的[Skype For business 中的 "发布待处理的语音路由配置更改"](voice-route-config-changes.md) 。</span><span class="sxs-lookup"><span data-stu-id="add85-232">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

13. <span data-ttu-id="add85-233">可选语音邮件 Escape 检测到呼叫已由用户的移动电话语音邮件立即应答, 并断开与移动电话语音邮件的通话。</span><span class="sxs-lookup"><span data-stu-id="add85-233">(Optional) Voicemail Escape detects that a call was immediately answered by the user's mobile phone voice mail, and disconnects the call to the mobile phone voice mail.</span></span> <span data-ttu-id="add85-234">这允许呼叫继续拨打用户的其他终结点, 让用户有机会接听呼叫。</span><span class="sxs-lookup"><span data-stu-id="add85-234">This allows the call to continue to ring on the user's other endpoints giving the user the opportunity to answer the call.</span></span> <span data-ttu-id="add85-235">有关如何配置语音邮件策略的详细信息, 请参阅[在 Skype For business 中配置语音邮件转义](configure-voice-mail-escape.md)。</span><span class="sxs-lookup"><span data-stu-id="add85-235">For details on how to configure a voice mail policy, see [Configure voice mail escape in Skype for Business](configure-voice-mail-escape.md).</span></span>

### <a name="to-modify-a-voice-policy"></a><span data-ttu-id="add85-236">修改语音策略</span><span class="sxs-lookup"><span data-stu-id="add85-236">To modify a voice policy</span></span>

1. <span data-ttu-id="add85-237">打开 "Skype for Business 服务器" 控制面板。</span><span class="sxs-lookup"><span data-stu-id="add85-237">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="add85-238">在左侧导航栏中，单击“语音路由”\*\*\*\*，然后单击“语音策略”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="add85-238">In the left navigation bar, click **Voice Routing**, and then click **Voice Policy**.</span></span>

3. <span data-ttu-id="add85-239">在“语音策略”\*\*\*\* 页上，双击某个语音策略名称。</span><span class="sxs-lookup"><span data-stu-id="add85-239">On the **Voice Policy** page, double-click a voice policy name.</span></span>

    > [!NOTE]
    > <span data-ttu-id="add85-p143">作用域和名称是在创建语音策略时设置的，且不能更改。</span><span class="sxs-lookup"><span data-stu-id="add85-p143">The scope and name were set when the voice policy was created. They cannot be changed.</span></span>

4. <span data-ttu-id="add85-242">（可选）在“编辑语音策略”\*\*\*\* 中，输入语音策略的其他描述性信息。</span><span class="sxs-lookup"><span data-stu-id="add85-242">(Optional) In **Edit Voice Policy**, enter additional descriptive information for the voice policy.</span></span>

5. <span data-ttu-id="add85-243">选中或清除以下复选框以启用或禁用每种“呼叫功能”\*\*\*\*：</span><span class="sxs-lookup"><span data-stu-id="add85-243">Select or clear the following check boxes to enable or disable each of the **Calling features**:</span></span>

   - <span data-ttu-id="add85-244">**语音邮件转义**可防止呼叫直接路由到用户的移动电话语音邮件系统, 同时拨打同时拨打的电话、关闭电池或超出范围。</span><span class="sxs-lookup"><span data-stu-id="add85-244">**Voice mail escape** prevents calls from being immediately routed to the user's mobile phone voice mail system when simultaneous ringing is configured and the phone is turned off, out of battery, or out of range.</span></span>

     > [!NOTE]
     > <span data-ttu-id="add85-245">此功能只能通过 Skype for Business Server Management Shell 进行配置</span><span class="sxs-lookup"><span data-stu-id="add85-245">This feature is only configurable through the Skype for Business Server Management Shell</span></span>

   - <span data-ttu-id="add85-246">通过**呼叫转接**，用户可以将呼叫转接到其他电话或客户端设备。</span><span class="sxs-lookup"><span data-stu-id="add85-246">**Call forwarding** enables users to forward calls to other phones and client devices.</span></span> <span data-ttu-id="add85-247">Skype for business 服务器为呼叫转接提供了一系列更广泛的配置选项。</span><span class="sxs-lookup"><span data-stu-id="add85-247">Skype for Business Server provides a significantly wider range of configuration options for call forwarding.</span></span> <span data-ttu-id="add85-248">例如，如果组织不允许将传入呼叫外部转接到 PSTN，则管理员可应用特定语音策略来部署此限制。</span><span class="sxs-lookup"><span data-stu-id="add85-248">For example, if an organization does not want to allow incoming calls to be forwarded externally to the PSTN, an administrator can apply a special voice policy to deploy this restriction.</span></span> <span data-ttu-id="add85-249">默认为启用。</span><span class="sxs-lookup"><span data-stu-id="add85-249">Enabled by default.</span></span>

   - <span data-ttu-id="add85-250">通过**委派**，用户可以指定其他用户代表他们发送和接收呼叫。</span><span class="sxs-lookup"><span data-stu-id="add85-250">**Delegation** enables users to specify other users to send and receive calls on their behalf.</span></span> <span data-ttu-id="add85-251">在 Skype for Business 服务器中, 代理人可以配置同时拨打的电话, 让他/她的经理拨出所有代理人同时拨打的目标电话。</span><span class="sxs-lookup"><span data-stu-id="add85-251">In Skype for Business Server, a delegate can configure simultaneous ringing that enables incoming calls to his or her manager to ring all of the delegate's simultaneous ringing targets.</span></span> <span data-ttu-id="add85-252">这会向委派提供极大的灵活性以响应直接传到经理的呼叫。</span><span class="sxs-lookup"><span data-stu-id="add85-252">This provides the delegate with greater flexibility in responding to calls directed to the manager.</span></span> <span data-ttu-id="add85-253">默认为启用。</span><span class="sxs-lookup"><span data-stu-id="add85-253">Enabled by default.</span></span>

   - <span data-ttu-id="add85-p146">通过**呼叫转移**，用户可以将呼叫转移到其他用户。默认为启用。</span><span class="sxs-lookup"><span data-stu-id="add85-p146">**Call transfer** enables users to transfer calls to other users. Enabled by default.</span></span>

   - <span data-ttu-id="add85-p147">通过**呼叫寄存**，用户可以寄存呼叫，将其置于保持状态，然后从其他电话或客户端接听呼叫。默认为禁用。</span><span class="sxs-lookup"><span data-stu-id="add85-p147">**Call park** enables users to park calls on hold, and then pick up the call from a different phone or client. Disabled by default.</span></span>

   - <span data-ttu-id="add85-258">**同时响铃**使来电可以在其他电话（例如，移动电话）或其他终结点设备上响铃。</span><span class="sxs-lookup"><span data-stu-id="add85-258">**Simultaneous ringing** enables incoming calls to ring on additional phones (for example, a mobile phone) or other endpoint devices.</span></span> <span data-ttu-id="add85-259">Skype for business 服务器为同时拨打的配置选项提供了一系列更广泛的配置选项。</span><span class="sxs-lookup"><span data-stu-id="add85-259">Skype for Business Server provides a significantly wider range of configuration options for simultaneous ringing.</span></span> <span data-ttu-id="add85-260">默认为启用。</span><span class="sxs-lookup"><span data-stu-id="add85-260">Enabled by default.</span></span>

   - <span data-ttu-id="add85-p149">通过**团队呼叫**，指定团队中的用户可以为团队中的其他成员应答呼叫。默认为启用。</span><span class="sxs-lookup"><span data-stu-id="add85-p149">**Team call** enables users on a defined team to answer calls for other members of the team. Enabled by default.</span></span>

   - <span data-ttu-id="add85-p150">**PSTN 重新路由**可以在 WAN 拥堵或不可用时在 PSTN 上重新路由分配有此策略的用户向其他企业用户发出的呼叫。默认为启用。</span><span class="sxs-lookup"><span data-stu-id="add85-p150">**PSTN re-route** enables calls made by users who are assigned this policy to other enterprise users to be rerouted on the PSTN if the WAN is congested or unavailable. Enabled by default.</span></span>

   - <span data-ttu-id="add85-p151">通过**带宽策略覆盖**，管理员可以覆盖特定用户的 CAC 策略决策。默认为禁用。</span><span class="sxs-lookup"><span data-stu-id="add85-p151">**Bandwidth policy override** enables administrators to override CAC policy decisions for a particular user. Disabled by default.</span></span>

     > [!NOTE]
     > <span data-ttu-id="add85-p152">只能覆盖向用户发出的传入呼叫的策略，而不能覆盖由用户发出的传出呼叫的策略。建立会话后，将准确记录带宽消耗。应慎用此设置。</span><span class="sxs-lookup"><span data-stu-id="add85-p152">The policy will be overridden only for incoming calls to the user and not for outgoing calls that are placed by the user. After the session is established, the bandwidth consumption will be accurately recorded. This setting should be used sparingly.</span></span>

   - <span data-ttu-id="add85-p153">通过**恶意呼叫跟踪**，用户可以通过使用客户端 UI 报告恶意呼叫（如威胁），接下来在 CDR 中标记呼叫。默认为禁用。</span><span class="sxs-lookup"><span data-stu-id="add85-p153">**Malicious call tracing** enables users to report malicious calls (such as threats) using the client UI, which in turn flags the calls in the CDRs. Disabled by default.</span></span>

6. <span data-ttu-id="add85-272">要为此语音策略关联和配置 PSTN 用法记录，请执行以下任意操作：</span><span class="sxs-lookup"><span data-stu-id="add85-272">To associate and configure PSTN usage records for this voice policy, do any of the following:</span></span>

   - <span data-ttu-id="add85-p154">要从企业语音部署中提供的所有 PSTN 用法记录列表中选择一个或多个记录，请单击“选择”\*\*\*\*。突出显示要与此语音策略关联的记录，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="add85-p154">To choose one or more records from a list of all PSTN usage records available in your Enterprise Voice deployment, click **Select**. Highlight the records that you want to associate with this voice policy, and then click **OK**.</span></span>

   - <span data-ttu-id="add85-275">要删除此语音策略中的某个 PSTN 用法记录，请突出显示相应的记录，然后单击“删除”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="add85-275">To remove a PSTN usage record from this voice policy, highlight the record and click **Remove**.</span></span>

   - <span data-ttu-id="add85-276">要定义新的 PSTN 用法记录并将其与此语音策略相关联，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="add85-276">To define a new PSTN usage record and associate it with this voice policy, do the following:</span></span>

     <span data-ttu-id="add85-277">a.</span><span class="sxs-lookup"><span data-stu-id="add85-277">a.</span></span> <span data-ttu-id="add85-278">单击“新建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="add85-278">Click **New**.</span></span>

     <span data-ttu-id="add85-279">b.</span><span class="sxs-lookup"><span data-stu-id="add85-279">b.</span></span> <span data-ttu-id="add85-280">在“名称”\*\*\*\* 字段中，输入记录的唯一描述性名称。</span><span class="sxs-lookup"><span data-stu-id="add85-280">In the **Name** field, enter a unique descriptive name for the record.</span></span> <span data-ttu-id="add85-281">例如, 你可能希望为位于 Redmond 的全职员工创建 PSTN 使用记录 namedRedmond, 并为临时员工创建另一个记录 namedRedmondTemps。</span><span class="sxs-lookup"><span data-stu-id="add85-281">For example, you may want to create a PSTN usage record namedRedmond for full-time employees located in Redmond, and another record namedRedmondTemps for temporary employees.</span></span>

     > [!NOTE]
     > <span data-ttu-id="add85-p157">PSTN 用法记录名称在企业语音部署中必须是唯一的。保存记录后，将无法编辑“名称”\*\*\*\* 字段。</span><span class="sxs-lookup"><span data-stu-id="add85-p157">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the **Name** field cannot be edited.</span></span>

     <span data-ttu-id="add85-284">c.</span><span class="sxs-lookup"><span data-stu-id="add85-284">c.</span></span> <span data-ttu-id="add85-285">使用以下任意方法为此 PSTN 用法记录关联和配置路由：</span><span class="sxs-lookup"><span data-stu-id="add85-285">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>

   - <span data-ttu-id="add85-286">要从企业语音部署中提供的所有路由列表中选择一个或多个路由，请单击“选择”\*\*\*\*，突出显示要与此 PSTN 用法记录相关联的路由，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="add85-286">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>

   - <span data-ttu-id="add85-287">要删除 PSTN 用法记录中的某个路由，请突出显示相应的路由，然后单击“删除”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="add85-287">To remove a route from the PSTN usage record, highlight the route and click **Remove**.</span></span>

   - <span data-ttu-id="add85-288">要定义新路由并将其与此 PSTN 用法记录关联，请单击“新建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="add85-288">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="add85-289">有关详细信息, 请参阅[在 Skype For business 中创建或修改语音路线](create-or-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="add85-289">For details, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span>

   - <span data-ttu-id="add85-290">要编辑已经与此 PSTN 用法记录相关联的路由，请突出显示相应的路由，然后单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="add85-290">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span>

     <span data-ttu-id="add85-291">d.</span><span class="sxs-lookup"><span data-stu-id="add85-291">d.</span></span> <span data-ttu-id="add85-292">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="add85-292">Click **OK**.</span></span>

   - <span data-ttu-id="add85-293">要编辑已经与此语音策略相关联的 PSTN 用法记录，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="add85-293">To edit a PSTN usage record that is already associated with this voice policy, do the following:</span></span>

     <span data-ttu-id="add85-294">a.</span><span class="sxs-lookup"><span data-stu-id="add85-294">a.</span></span> <span data-ttu-id="add85-295">突出显示要编辑的 PSTN 用法记录，然后单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="add85-295">Highlight the PSTN usage record that you want to edit and click **Show details**.</span></span>

     <span data-ttu-id="add85-296">b.</span><span class="sxs-lookup"><span data-stu-id="add85-296">b.</span></span> <span data-ttu-id="add85-297">使用以下任意方法为此 PSTN 用法记录关联和配置路由：</span><span class="sxs-lookup"><span data-stu-id="add85-297">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>

   - <span data-ttu-id="add85-298">要从企业语音部署中提供的所有路由列表中选择一个或多个路由，请单击“选择”\*\*\*\*，突出显示要与此 PSTN 用法记录相关联的路由，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="add85-298">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>

   - <span data-ttu-id="add85-299">要删除此 PSTN 用法记录中的某个路由，请突出显示相应的路由，然后单击“删除”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="add85-299">To remove a route from this PSTN usage record, highlight the route and click **Remove**.</span></span>

   - <span data-ttu-id="add85-300">要定义新路由并将其与此 PSTN 用法记录关联，请单击“新建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="add85-300">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="add85-301">有关详细信息, 请参阅[在 Skype For business 中创建或修改语音路线](create-or-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="add85-301">For details, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span>

   - <span data-ttu-id="add85-302">要编辑已经与此 PSTN 用法记录相关联的路由，请突出显示相应的路由，然后单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="add85-302">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span>

     <span data-ttu-id="add85-303">c.</span><span class="sxs-lookup"><span data-stu-id="add85-303">c.</span></span> <span data-ttu-id="add85-304">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="add85-304">Click **OK**.</span></span>

7. <span data-ttu-id="add85-305">排列 PSTN 用法记录以获得最佳性能。</span><span class="sxs-lookup"><span data-stu-id="add85-305">Arrange the PSTN usage records for optimum performance.</span></span> <span data-ttu-id="add85-306">若要更改记录在列表中的位置, 请突出显示记录名称, 然后单击向上或向下箭头。</span><span class="sxs-lookup"><span data-stu-id="add85-306">To change a record's position in the list, highlight the record name and click the up or down arrow.</span></span>

    > [!NOTE]
    > <span data-ttu-id="add85-307">PSTN 用法记录在语音策略中的列出顺序十分重要。</span><span class="sxs-lookup"><span data-stu-id="add85-307">The order in which PSTN usage records are listed in the voice policy is significant.</span></span> <span data-ttu-id="add85-308">Skype for Business 服务器从上到下遍历列表。</span><span class="sxs-lookup"><span data-stu-id="add85-308">Skype for Business Server traverses the list from the top down.</span></span> <span data-ttu-id="add85-309">建议按使用频率来组织该列表，例如：RedmondLocal、RedmondLongDist、RedmondInternational 和 RedmondBackup。</span><span class="sxs-lookup"><span data-stu-id="add85-309">We recommend that you organize the list by frequency of use, for example: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span></span>

8. <span data-ttu-id="add85-310">要在此语音策略中为呼叫转接和同时响铃关联和配置 PSTN 用法记录，请执行以下任意操作：</span><span class="sxs-lookup"><span data-stu-id="add85-310">To associate and configure PSTN usage records for call forwarding and simultaneous ringing in this voice policy, do any of the following:</span></span>

   - <span data-ttu-id="add85-311">要作为此语音策略将相同的 PSTN 用法记录用于呼叫转接和同时响铃，请从下拉菜单选择“使用呼叫 PSTN 用法进行路由”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="add85-311">To use the same PSTN usage records for call forwarding and simultaneous ringing as this voice policy, select the option **Route using the call PSTN usages** from the drop-down menu.</span></span>

   - <span data-ttu-id="add85-312">若要允许呼叫转接和同时拨打内部 Skype for Business 用户, 请选择 "仅从下拉菜单**传送到内部 skype for business 用户**"。</span><span class="sxs-lookup"><span data-stu-id="add85-312">To allow call forwarding and simultaneous ringing to internal Skype for Business users only, select **Route to internal Skype for Business users only** from the drop-down menu.</span></span> <span data-ttu-id="add85-313">Calls will not be forwarded to external PSTN numbers.</span><span class="sxs-lookup"><span data-stu-id="add85-313">Calls will not be forwarded to external PSTN numbers.</span></span>

   - <span data-ttu-id="add85-p168">若要为呼叫转接和同时响铃指定与此语音策略所用的 PSTN 用法记录不同的 PSTN 用法记录，请从下拉菜单中选择“使用自定义 PSTN 用法进行路由”\*\*\*\*。此选项显示一个控件，此控件专用于为呼叫转接和同时响铃选择现有 PSTN 用法记录或创建新的 PSTN 用法记录。</span><span class="sxs-lookup"><span data-stu-id="add85-p168">To specify different PSTN usage records for call forwarding and simultaneous ringing than those used for this voice policy, select the option **Route using custom PSTN usages** from the drop-down menu. This option displays a control to select existing PSTN usage records or to create new PSTN usage records, specifically for call forwarding and simultaneous ringing.</span></span>

   - <span data-ttu-id="add85-p169">要从用于呼叫转接和同时响铃 PSTN 用法记录列表中选择一个或多个记录，请单击“选择”\*\*\*\*。突出显示要与此呼叫转接和同时响铃策略关联的记录，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="add85-p169">To choose one or more records from a list of PSTN usage records for call forwarding and simultaneous ringing, click **Select**. Highlight the records that you want to associate with this call forwarding and simultaneous ringing policy, and then click **OK**.</span></span>

   - <span data-ttu-id="add85-318">要从此呼叫转接和同时响铃策略删除 PSTN 用法记录，请突出显示该记录，然后单击“删除”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="add85-318">To remove a PSTN usage record from this call forwarding and simultaneous ringing policy, highlight the record and click **Remove**.</span></span>

   - <span data-ttu-id="add85-319">要定义新的 PSTN 用法记录并将其与此呼叫转接和同时响铃策略相关联，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="add85-319">To define a new PSTN usage record and associate it with this call forwarding and simultaneous ringing policy, do the following:</span></span>

     <span data-ttu-id="add85-320">a.</span><span class="sxs-lookup"><span data-stu-id="add85-320">a.</span></span> <span data-ttu-id="add85-321">单击“新建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="add85-321">Click **New**.</span></span>

     <span data-ttu-id="add85-322">b.</span><span class="sxs-lookup"><span data-stu-id="add85-322">b.</span></span> <span data-ttu-id="add85-323">在“名称”\*\*\*\* 字段中，输入记录的唯一描述性名称。</span><span class="sxs-lookup"><span data-stu-id="add85-323">In the **Name** field, enter a unique descriptive name for the record.</span></span>

     > [!NOTE]
     > <span data-ttu-id="add85-p172">PSTN 用法记录名称在企业语音部署中必须是唯一的。保存记录后，将无法编辑“名称”\*\*\*\* 字段。</span><span class="sxs-lookup"><span data-stu-id="add85-p172">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the **Name** field cannot be edited.</span></span>

     <span data-ttu-id="add85-326">c.</span><span class="sxs-lookup"><span data-stu-id="add85-326">c.</span></span> <span data-ttu-id="add85-327">使用以下任意方法为此 PSTN 用法记录关联和配置路由：</span><span class="sxs-lookup"><span data-stu-id="add85-327">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>

   - <span data-ttu-id="add85-328">要从企业语音部署中提供的所有路由列表中选择一个或多个路由，请单击“选择”\*\*\*\*，突出显示要与此 PSTN 用法记录相关联的路由，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="add85-328">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>

   - <span data-ttu-id="add85-329">要删除 PSTN 用法记录中的某个路由，请突出显示相应的路由，然后单击“删除”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="add85-329">To remove a route from the PSTN usage record, highlight the route and click **Remove**.</span></span>

   - <span data-ttu-id="add85-330">要定义新路由并将其与此 PSTN 用法记录关联，请单击“新建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="add85-330">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="add85-331">有关详细信息, 请参阅[在 Skype For business 中创建或修改语音路线](create-or-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="add85-331">For details, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span>

   - <span data-ttu-id="add85-p175">要编辑已经与此 PSTN 用法记录相关联的路由，请突出显示相应的路由，然后单击“显示详细信息”\*\*\*\*。有关详细信息，请参阅[Modify a Voice Route](https://technet.microsoft.com/library/afc562cc-8807-489b-8850-dbbe1c1ab9f5.aspx)。</span><span class="sxs-lookup"><span data-stu-id="add85-p175">To edit a route that is already associated with this PSTN usage record, highlight the route, and then click **Show details**. For details, see [Modify a Voice Route](https://technet.microsoft.com/library/afc562cc-8807-489b-8850-dbbe1c1ab9f5.aspx).</span></span>

     <span data-ttu-id="add85-334">d.</span><span class="sxs-lookup"><span data-stu-id="add85-334">d.</span></span> <span data-ttu-id="add85-335">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="add85-335">Click **OK**.</span></span>

   - <span data-ttu-id="add85-336">要编辑已经与此语音策略相关联的 PSTN 用法记录，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="add85-336">To edit a PSTN usage record that is already associated with this voice policy, do the following:</span></span>

     <span data-ttu-id="add85-337">a.</span><span class="sxs-lookup"><span data-stu-id="add85-337">a.</span></span> <span data-ttu-id="add85-338">突出显示要编辑的 PSTN 用法记录，然后单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="add85-338">Highlight the PSTN usage record that you want to edit and click **Show details**.</span></span>

     <span data-ttu-id="add85-339">b.</span><span class="sxs-lookup"><span data-stu-id="add85-339">b.</span></span> <span data-ttu-id="add85-340">使用以下任意方法为此 PSTN 用法记录关联和配置路由：</span><span class="sxs-lookup"><span data-stu-id="add85-340">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>

     - <span data-ttu-id="add85-341">要从企业语音部署中提供的所有路由列表中选择一个或多个路由，请单击“选择”\*\*\*\*，突出显示要与此 PSTN 用法记录相关联的路由，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="add85-341">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes you want to associate with this PSTN usage record, and then click **OK**.</span></span>

     - <span data-ttu-id="add85-342">要删除此 PSTN 用法记录中的某个路由，请突出显示相应的路由，然后单击“删除”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="add85-342">To remove a route from this PSTN usage record, highlight the route and click **Remove**.</span></span>

     - <span data-ttu-id="add85-343">要定义新路由并将其与此 PSTN 用法记录关联，请单击“新建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="add85-343">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="add85-344">有关详细信息, 请参阅[在 Skype For business 中创建或修改语音路线](create-or-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="add85-344">For details, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span>

     - <span data-ttu-id="add85-p180">要编辑已经与此 PSTN 用法记录相关联的路由，请突出显示相应的路由，然后单击“显示详细信息”\*\*\*\*。有关详细信息，请参阅[Modify a Voice Route](https://technet.microsoft.com/library/afc562cc-8807-489b-8850-dbbe1c1ab9f5.aspx)。</span><span class="sxs-lookup"><span data-stu-id="add85-p180">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**. For details, see [Modify a Voice Route](https://technet.microsoft.com/library/afc562cc-8807-489b-8850-dbbe1c1ab9f5.aspx).</span></span>

     <span data-ttu-id="add85-347">c.</span><span class="sxs-lookup"><span data-stu-id="add85-347">c.</span></span> <span data-ttu-id="add85-348">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="add85-348">Click **OK**.</span></span>

9. <span data-ttu-id="add85-p182">（可选）输入一个号码来测试语音策略，然后单击“执行”\*\*\*\*。测试结果会显示在“要测试的转换号码”\*\*\*\* 下。</span><span class="sxs-lookup"><span data-stu-id="add85-p182">(Optional) Enter a number to test the voice policy and click **Go**. The test results are displayed under **Translated number to test**.</span></span>

10. <span data-ttu-id="add85-351">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="add85-351">Click **OK**.</span></span>

11. <span data-ttu-id="add85-352">在“语音策略”\*\*\*\* 页上，单击“提交”\*\*\*\*，然后单击“全部提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="add85-352">On the **Voice Policy** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="add85-353">只要创建或修改语音策略，就必须运行“全部提交”\*\*\*\* 命令以发布配置更改。</span><span class="sxs-lookup"><span data-stu-id="add85-353">Whenever you create or modify a voice policy, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="add85-354">有关详细信息, 请参阅操作文档中的[Skype For business 中的 "发布待处理的语音路由配置更改"](voice-route-config-changes.md) 。</span><span class="sxs-lookup"><span data-stu-id="add85-354">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

12. <span data-ttu-id="add85-355">可选语音邮件 Escape 检测到呼叫已由用户的移动电话语音邮件立即应答, 并断开与移动电话语音邮件的通话。</span><span class="sxs-lookup"><span data-stu-id="add85-355">(Optional) Voicemail Escape detects that a call was immediately answered by the user's mobile phone voice mail, and disconnects the call to the mobile phone voice mail.</span></span> <span data-ttu-id="add85-356">这允许呼叫继续拨打用户的其他终结点, 让用户有机会接听呼叫。</span><span class="sxs-lookup"><span data-stu-id="add85-356">This allows the call to continue to ring on the user's other endpoints giving the user the opportunity to answer the call.</span></span> <span data-ttu-id="add85-357">有关如何配置语音邮件策略的详细信息, 请参阅[在 Skype For business 中配置语音邮件转义](configure-voice-mail-escape.md)。</span><span class="sxs-lookup"><span data-stu-id="add85-357">For details about how to configure a voice mail policy, see [Configure voice mail escape in Skype for Business](configure-voice-mail-escape.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="add85-358">另请参阅</span><span class="sxs-lookup"><span data-stu-id="add85-358">See also</span></span>

[<span data-ttu-id="add85-359">查看 Skype for Business 中的 PSTN 使用记录</span><span class="sxs-lookup"><span data-stu-id="add85-359">View PSTN usage records in Skype for Business</span></span>](view-pstn-usage-records.md)

[<span data-ttu-id="add85-360">在 Skype for Business 中创建或修改语音路线</span><span class="sxs-lookup"><span data-stu-id="add85-360">Create or modify a voice route in Skype for Business</span></span>](create-or-modify-a-voice-route.md)

[<span data-ttu-id="add85-361">发布 Skype for Business 中的语音路由配置的待处理更改</span><span class="sxs-lookup"><span data-stu-id="add85-361">Publish pending changes to the voice routing configuration in Skype for Business</span></span>](voice-route-config-changes.md)

[<span data-ttu-id="add85-362">在 Skype for Business 中配置语音邮件转义</span><span class="sxs-lookup"><span data-stu-id="add85-362">Configure voice mail escape in Skype for Business</span></span>](configure-voice-mail-escape.md)

