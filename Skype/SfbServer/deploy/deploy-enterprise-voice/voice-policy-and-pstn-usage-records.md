---
title: 在 Skype for Business 中创建或修改语音策略和配置 PSTN 用法记录
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e6ff27e0-e2d1-4445-840f-08f738200c20
description: 摘要：使用 Skype for Business Server 控制面板创建或修改语音策略并配置 PSTN 用法记录。
ms.openlocfilehash: ca97c4c75004849f2ea404c083878da6c726c2e6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51105758"
---
# <a name="create-or-modify-a-voice-policy-and-configure-pstn-usage-records-in-skype-for-business"></a><span data-ttu-id="4ec2e-103">在 Skype for Business 中创建或修改语音策略和配置 PSTN 用法记录</span><span class="sxs-lookup"><span data-stu-id="4ec2e-103">Create or modify a voice policy and configure PSTN usage records in Skype for Business</span></span>

<span data-ttu-id="4ec2e-104">**摘要：** 使用 Skype for Business Server 控制面板创建或修改语音策略并配置 PSTN 用法记录。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-104">**Summary:** Create or modify voice policies and configure PSTN usage records by using the Skype for Business Server Control Panel.</span></span>

> [!NOTE]
> <span data-ttu-id="4ec2e-105">每个语音策略都必须至少有一个关联的公用电话交换网 (PSTN) 用法记录。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-105">Each voice policy must have at least one associated Public Switched Telephone Network (PSTN) usage record.</span></span> <span data-ttu-id="4ec2e-106">若要查看所有 PSTN 用法记录在部署中可用的列表，企业语音查看其属性，请参阅在 Skype [for Business 中查看 PSTN 用法记录](view-pstn-usage-records.md)。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-106">To see a listing of all PSTN usage records available in your Enterprise Voice deployment and view their properties, see [View PSTN usage records in Skype for Business](view-pstn-usage-records.md).</span></span>

### <a name="to-create-a-voice-policy"></a><span data-ttu-id="4ec2e-107">创建语音策略</span><span class="sxs-lookup"><span data-stu-id="4ec2e-107">To create a voice policy</span></span>

1. <span data-ttu-id="4ec2e-108">打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-108">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="4ec2e-109">在左侧导航栏中，单击"**语音路由"，** 然后单击"**语音策略"。**</span><span class="sxs-lookup"><span data-stu-id="4ec2e-109">In the left navigation bar, click **Voice Routing** and then click **Voice Policy**.</span></span>

3. <span data-ttu-id="4ec2e-110">在" **语音策略"** 页上，单击" **新建** "，然后选择新策略的范围：</span><span class="sxs-lookup"><span data-stu-id="4ec2e-110">On the **Voice Policy** page, click **New** and then select a scope for the new policy:</span></span>

   - <span data-ttu-id="4ec2e-111">**站点** 策略适用于整个站点，分配给用户策略的任何用户或组除外。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-111">**Site policy** applies to an entire site, except any users or groups that are assigned to a user policy.</span></span> <span data-ttu-id="4ec2e-112">如果选择"站点"作为策略作用域，请从"选择站点 **"对话框中选择** 站点。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-112">If you select Site for a policy scope, choose the site from the **Select a Site** dialog box.</span></span> <span data-ttu-id="4ec2e-113">如果已针对某个站点创建了语音策略，则该网站不会显示在"选择站点 **"** 对话框中。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-113">If a voice policy has already been created for a site, the site does not appear in the **Select a Site** dialog box.</span></span>

   - <span data-ttu-id="4ec2e-114">**用户策略** 可应用于指定的用户或组。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-114">**User policy** can be applied to specified users or groups.</span></span>

4. <span data-ttu-id="4ec2e-115">如果语音策略作用域为"用户"，请在"名称"字段中输入策略 **的描述性** 名称。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-115">If the voice policy scope is User, enter a descriptive name for the policy in the **Name** field.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4ec2e-116">如果语音策略作用域为"站点"，则"新建语音策略"中的"名称"字段会使用站点名称预先填充，并且无法更改。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-116">If the voice policy scope is Site, the **Name** field in **New Voice Policy** is prepopulated with the site name and cannot be changed.</span></span>

5. <span data-ttu-id="4ec2e-117"> (可选) 输入语音策略的其他描述性信息。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-117">(Optional) Enter additional descriptive information for the voice policy.</span></span>

6. <span data-ttu-id="4ec2e-118">选中或清除以下复选框，为此语音策略启用或 **禁用每个呼叫** 功能：</span><span class="sxs-lookup"><span data-stu-id="4ec2e-118">Select or clear the following check boxes to enable or disable each of the **Calling features** for this voice policy:</span></span>

   - <span data-ttu-id="4ec2e-119">**语音邮件转** 义可防止在配置同时响铃、电话关闭、电池不足或范围外时将呼叫立即路由到用户的移动电话语音邮件系统。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-119">**Voice mail escape** prevents calls from being immediately routed to the user's mobile phone voice mail system when simultaneous ringing is configured and the phone is turned off, out of battery, or out of range.</span></span>

     > [!NOTE]
     > <span data-ttu-id="4ec2e-120">此功能仅可以通过 Skype for Business Server 命令行管理程序进行配置</span><span class="sxs-lookup"><span data-stu-id="4ec2e-120">This feature is only configurable through the Skype for Business Server Management Shell</span></span>

   - <span data-ttu-id="4ec2e-121">通过 **呼叫转接**，用户可以将呼叫转接到其他电话或客户端设备。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-121">**Call forwarding** enables users to forward calls to other phones and client devices.</span></span> <span data-ttu-id="4ec2e-122">Skype for Business Server 为呼叫转发提供了范围更广的配置选项。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-122">Skype for Business Server provides a significantly wider range of configuration options for call forwarding.</span></span> <span data-ttu-id="4ec2e-123">例如，如果组织不允许将传入呼叫外部转接到 PSTN，则管理员可应用特定语音策略来部署此限制。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-123">For example, if an organization does not want to allow incoming calls to be forwarded externally to the PSTN, an administrator can apply a special voice policy to deploy this restriction.</span></span> <span data-ttu-id="4ec2e-124">默认为启用。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-124">Enabled by default.</span></span>

   - <span data-ttu-id="4ec2e-125">通过 **委派**，用户可以指定其他用户代表他们发送和接收呼叫。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-125">**Delegation** enables users to specify other users to send and receive calls on their behalf.</span></span> <span data-ttu-id="4ec2e-126">在 Skype for Business Server 中，代理人可以配置同时响铃，从而允许呼叫其经理的传入呼叫拨打代理人的所有同时响铃目标。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-126">In Skype for Business Server, a delegate can configure simultaneous ringing that enables incoming calls to his or her manager to ring all of the delegate's simultaneous ringing targets.</span></span> <span data-ttu-id="4ec2e-127">这为代理提供了极大地灵活性以响应定向至管理员的呼叫。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-127">This provides the delegate with greater flexibility in responding to calls directed to the manager.</span></span> <span data-ttu-id="4ec2e-128">默认为启用。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-128">Enabled by default.</span></span>

   - <span data-ttu-id="4ec2e-129">通过 **呼叫转移**，用户可以将呼叫转移到其他用户。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-129">**Call transfer** enables users to transfer calls to other users.</span></span> <span data-ttu-id="4ec2e-130">默认为启用。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-130">Enabled by default.</span></span>

   - <span data-ttu-id="4ec2e-131">**通过呼叫** 保留，用户可以将呼叫保留，然后从其他电话或客户端接听呼叫。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-131">**Call park** enables users to park calls on hold and then pick up the call from a different phone or client.</span></span> <span data-ttu-id="4ec2e-132">默认为禁用。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-132">Disabled by default.</span></span>

   - <span data-ttu-id="4ec2e-133">**同时响铃** 使传入呼叫可以在其他电话（如手机）或其他终结点设备上响铃。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-133">**Simultaneous ringing** enables incoming calls to ring on additional phones (for example, a mobile phone) or other endpoint devices.</span></span> <span data-ttu-id="4ec2e-134">Skype for Business Server 为同时响铃提供了范围更广的配置选项。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-134">Skype for Business Server provides a significantly wider range of configuration options for simultaneous ringing.</span></span> <span data-ttu-id="4ec2e-135">默认为启用。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-135">Enabled by default.</span></span>

   - <span data-ttu-id="4ec2e-136">通过 **团队呼叫**，指定团队中的用户可以为团队中的其他成员应答呼叫。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-136">**Team call** enables users on a defined team to answer calls for other members of the team.</span></span> <span data-ttu-id="4ec2e-137">默认为启用。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-137">Enabled by default.</span></span>

   - <span data-ttu-id="4ec2e-138">**PSTN 重新** 路由使分配了此策略的用户向其他企业用户拨打的呼叫可以在 WAN 变得塞或不可用时在 PSTN 上重新路由。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-138">**PSTN re-route** enables calls made by users who are assigned this policy to other enterprise users to be rerouted on the PSTN if the WAN is congested or unavailable.</span></span> <span data-ttu-id="4ec2e-139">默认为启用。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-139">Enabled by default.</span></span>

   - <span data-ttu-id="4ec2e-140">通过 **带宽策略覆盖**，管理员可以覆盖特定用户的呼叫允许控制策略决策。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-140">**Bandwidth policy override** enables administrators to override call admission control policy decisions for a particular user.</span></span> <span data-ttu-id="4ec2e-141">默认为禁用。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-141">Disabled by default.</span></span>

     > [!NOTE]
     > <span data-ttu-id="4ec2e-142">只能覆盖向用户发出的传入呼叫的策略，而不能覆盖由用户发出的传出呼叫的策略。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-142">The policy will be overridden only for incoming calls to the user and not for outgoing calls that are placed by the user.</span></span> <span data-ttu-id="4ec2e-143">建立会话后，将准确记录带宽消耗。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-143">After the session is established, the bandwidth consumption will be accurately recorded.</span></span> <span data-ttu-id="4ec2e-144">应谨慎使用此设置，并且应保留此设置以做出适当的呼叫允许控制决策。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-144">This setting should be used sparingly and should be reserved for appropriate call admission control decisions.</span></span>

   - <span data-ttu-id="4ec2e-145">通过恶意 **呼叫跟踪，** 用户可以使用客户端 UI 报告恶意呼叫 (如威胁) ，客户端 UI 反过来在呼叫详细信息记录 (CDR 中标记) 。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-145">**Malicious call tracing** enables users to report malicious calls (such as threats) by using the client UI, which in turn flags the calls in the Call Detail Records (CDRs).</span></span> <span data-ttu-id="4ec2e-146">默认情况下处于禁用状态。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-146">Disabled by default.</span></span>

   - <span data-ttu-id="4ec2e-147">**忙碌选项** 启用或禁用指定语音策略的忙碌选项。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-147">**Busy options** enables or disables Busy Options for the specified voice policy.</span></span> <span data-ttu-id="4ec2e-148">忙碌选项允许在呼叫的目标用户接听电话时，将传入呼叫路由到语音邮件，或者通过忙音信号拒绝传入呼叫。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-148">Busy Options allows incoming calls to be routed to voice mail or rejected with a busy signal when the call's target user is on the phone.</span></span> <span data-ttu-id="4ec2e-149">忙碌选项是 2016 年 7 月累积更新中引入的新语音策略。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-149">Busy Options is a new voice policy introduced in the July 2016 Cumulative Update.</span></span> <span data-ttu-id="4ec2e-150">选中此参数将启用忙碌选项，取消选中将禁用忙碌选项。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-150">Checking this parameter enables Busy Options, and unchecking it disables Busy Options.</span></span> <span data-ttu-id="4ec2e-151">有关详细信息，请参阅 Plan [for Busy Options for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/busy-options.md) 和 Install and configure Busy Options for Skype for Business [Server](install-and-configure-busy-options.md)。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-151">For more information, see [Plan for Busy Options for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/busy-options.md) and [Install and configure Busy Options for Skype for Business Server](install-and-configure-busy-options.md).</span></span>

7. <span data-ttu-id="4ec2e-152">要为此语音策略关联和配置 PSTN 用法记录，请执行以下任意操作：</span><span class="sxs-lookup"><span data-stu-id="4ec2e-152">To associate and configure PSTN usage records for this voice policy, do any of the following:</span></span>

   - <span data-ttu-id="4ec2e-p114">要从企业语音部署中提供的所有 PSTN 用法记录列表中选择一个或多个记录，请单击“选择”。突出显示要与此语音策略关联的记录，然后单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-p114">To choose one or more records from a list of all PSTN usage records available in your Enterprise Voice deployment, click **Select**. Highlight the records that you want to associate with this voice policy, and then click **OK**.</span></span>

   - <span data-ttu-id="4ec2e-155">要删除此语音策略中的某个 PSTN 用法记录，请突出显示相应的记录，然后单击“删除”。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-155">To remove a PSTN usage record from this voice policy, highlight the record and click **Remove**.</span></span>

   - <span data-ttu-id="4ec2e-156">要定义新的 PSTN 用法记录并将其与此语音策略相关联，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="4ec2e-156">To define a new PSTN usage record and associate it with this voice policy, do the following:</span></span>

     <span data-ttu-id="4ec2e-157">a.</span><span class="sxs-lookup"><span data-stu-id="4ec2e-157">a.</span></span> <span data-ttu-id="4ec2e-158">单击"新建"。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-158">Click **New**.</span></span>

     <span data-ttu-id="4ec2e-159">b.</span><span class="sxs-lookup"><span data-stu-id="4ec2e-159">b.</span></span> <span data-ttu-id="4ec2e-160">在“名称”字段中，输入记录的唯一描述性名称。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-160">In the **Name** field, enter a unique descriptive name for the record.</span></span> <span data-ttu-id="4ec2e-161">例如，您可能需要为 Redmond 的全职员工创建名为Redmond 的 PSTN 用法记录，为临时员工创建另一个名为RedmondTemps 的 PSTN 用法记录。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-161">For example, you may want to create a PSTN usage record namedRedmond for full-time employees located in Redmond, and another namedRedmondTemps for temporary employees.</span></span>

     > [!NOTE]
     > <span data-ttu-id="4ec2e-p117">PSTN 用法记录名称在企业语音部署中必须是唯一的。保存记录后，将无法编辑“名称”字段。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-p117">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the **Name** field cannot be edited.</span></span>

     <span data-ttu-id="4ec2e-164">c.</span><span class="sxs-lookup"><span data-stu-id="4ec2e-164">c.</span></span> <span data-ttu-id="4ec2e-165">使用以下任意方法为此 PSTN 用法记录关联和配置路由：</span><span class="sxs-lookup"><span data-stu-id="4ec2e-165">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>

   - <span data-ttu-id="4ec2e-166">要从企业语音部署中提供的所有路由列表中选择一个或多个路由，请单击“选择”，突出显示要与此 PSTN 用法记录相关联的路由，然后单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-166">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>

   - <span data-ttu-id="4ec2e-167">若要从 PSTN 用法记录中删除路由，请突出显示该路由，然后单击"删除 **"。**</span><span class="sxs-lookup"><span data-stu-id="4ec2e-167">To remove a route from the PSTN usage record, highlight the route, and then click **Remove**.</span></span>

   - <span data-ttu-id="4ec2e-168">要定义新路由并将其与此 PSTN 用法记录相关联，请单击“新建”。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-168">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="4ec2e-169">有关详细信息，请参阅在 Skype for Business 中创建或修改 [语音路由](create-or-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-169">For details, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span>

   - <span data-ttu-id="4ec2e-170">要编辑已经与此 PSTN 用法记录相关联的路由，请突出显示相应的路由，然后单击“显示详细信息”。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-170">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span>

     <span data-ttu-id="4ec2e-171">d.</span><span class="sxs-lookup"><span data-stu-id="4ec2e-171">d.</span></span> <span data-ttu-id="4ec2e-172">单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-172">Click **OK**.</span></span>

   - <span data-ttu-id="4ec2e-173">要编辑已经与此语音策略相关联的 PSTN 用法记录，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="4ec2e-173">To edit a PSTN usage record that is already associated with this voice policy, do the following:</span></span>

     <span data-ttu-id="4ec2e-174">a.</span><span class="sxs-lookup"><span data-stu-id="4ec2e-174">a.</span></span> <span data-ttu-id="4ec2e-175">突出显示要编辑的 PSTN 用法记录，然后单击"显示 **详细信息"。**</span><span class="sxs-lookup"><span data-stu-id="4ec2e-175">Highlight the PSTN usage record that you want to edit, and then click **Show details**.</span></span>

     <span data-ttu-id="4ec2e-176">b.</span><span class="sxs-lookup"><span data-stu-id="4ec2e-176">b.</span></span> <span data-ttu-id="4ec2e-177">使用以下任意方法为此 PSTN 用法记录关联和配置路由：</span><span class="sxs-lookup"><span data-stu-id="4ec2e-177">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>

   - <span data-ttu-id="4ec2e-178">要从企业语音部署中提供的所有路由列表中选择一个或多个路由，请单击“选择”，突出显示要与此 PSTN 用法记录相关联的路由，然后单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-178">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes you want to associate with this PSTN usage record, and then click **OK**.</span></span>

   - <span data-ttu-id="4ec2e-179">若要从此 PSTN 用法记录中删除路由，请突出显示该路由，然后单击"删除 **"。**</span><span class="sxs-lookup"><span data-stu-id="4ec2e-179">To remove a route from this PSTN usage record, highlight the route, and then click **Remove**.</span></span>

   - <span data-ttu-id="4ec2e-180">要定义新路由并将其与此 PSTN 用法记录相关联，请单击“新建”。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-180">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="4ec2e-181">有关详细信息，请参阅在 Skype for Business 中创建或修改 [语音路由](create-or-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-181">For details, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span>

   - <span data-ttu-id="4ec2e-182">若要编辑已与此 PSTN 用法记录关联的路由，请突出显示相应的路由并单击"显示 **详细信息"。**</span><span class="sxs-lookup"><span data-stu-id="4ec2e-182">To edit a route that is already associated with this PSTN usage record, highlight the route and lick **Show details**.</span></span>

     <span data-ttu-id="4ec2e-183">c.</span><span class="sxs-lookup"><span data-stu-id="4ec2e-183">c.</span></span> <span data-ttu-id="4ec2e-184">单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-184">Click **OK**.</span></span>

8. <span data-ttu-id="4ec2e-185">排列 PSTN 用法记录以获得最佳性能。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-185">Arrange the PSTN usage records for optimum performance.</span></span> <span data-ttu-id="4ec2e-186">若要更改记录在列表中的位置，请突出显示记录名称，然后单击向上箭头或向下箭头。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-186">To change a record's position in the list, highlight the record name and click the up or down arrow.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="4ec2e-187">PSTN 用法记录在语音策略中的列出顺序十分重要。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-187">The order in which PSTN usage records are listed in the voice policy is significant.</span></span> <span data-ttu-id="4ec2e-188">Skype for Business Server 从上到下遍历该列表。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-188">Skype for Business Server traverses the list from the top down.</span></span> <span data-ttu-id="4ec2e-189">建议按使用频率来组织该列表，例如：RedmondLocal、RedmondLongDist、RedmondInternational 和 RedmondBackup。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-189">We recommend that you organize the list by frequency of use, for example: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span></span>

9. <span data-ttu-id="4ec2e-190">要为此语音策略中的呼叫转接和同时响铃关联和配置 PSTN 用法记录，请执行以下任一操作：</span><span class="sxs-lookup"><span data-stu-id="4ec2e-190">To associate and configure PSTN usage records for call forwarding and simultaneous ringing in this voice policy, do any of the following:</span></span>

   - <span data-ttu-id="4ec2e-191">若要对呼叫转接和同时响铃使用与此语音策略相同的 PSTN 用法记录，请从下拉菜单中选择“使用呼叫 PSTN 用法进行路由”。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-191">To use the same PSTN usage records for call forwarding and simultaneous ringing as this voice policy, select the option **Route using the call PSTN usages** from the drop-down menu.</span></span>

   - <span data-ttu-id="4ec2e-192">若要仅允许向内部 Skype for Business 用户进行呼叫转发和同时响铃，请从下拉菜单中选择"仅路由到内部 **Skype for Business** 用户"选项。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-192">To allow call forwarding and simultaneous ringing to internal Skype for Business users only, select the option **Route to internal Skype for Business users only** from the drop-down menu.</span></span> <span data-ttu-id="4ec2e-193">呼叫将不会转接到外部 PSTN 号码。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-193">Calls will not be forwarded to external PSTN numbers.</span></span>

   - <span data-ttu-id="4ec2e-194">若要为呼叫转发和同时响铃指定与用于此语音策略不同的 PSTN 用法记录，请从下拉菜单中选择"使用自定义 **PSTN** 用法路由"。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-194">To specify different PSTN usage records for call forwarding and simultaneous ringing than used for this voice policy, select the option **Route using custom PSTN usages** from the drop-down menu.</span></span> <span data-ttu-id="4ec2e-195">此选项显示一个控件，用于选择现有 PSTN 用法记录或专门为呼叫转发和同时响铃创建新的 PSTN 用法记录。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-195">This option displays a control to select existing PSTN usage records or create new PSTN usage records specifically for call forwarding and simultaneous ringing.</span></span>

   - <span data-ttu-id="4ec2e-p129">要从呼叫转接和同时响铃的 PSTN 用法记录列表中选择一个或多个记录，请单击“选择”。突出显示要与此呼叫转接和同时响铃策略关联的记录，然后单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-p129">To choose one or more records from a list of PSTN usage records for call forwarding and simultaneous ringing, click **Select**. Highlight the records that you want to associate with this call forwarding and simultaneous ringing policy, and then click **OK**.</span></span>

   - <span data-ttu-id="4ec2e-198">要从此呼叫转接和同时响铃策略中删除某个 PSTN 用法记录，请突出显示相应的记录，然后单击“删除”。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-198">To remove a PSTN usage record from this call forwarding and simultaneous ringing policy, highlight the record and click **Remove**.</span></span>

   - <span data-ttu-id="4ec2e-199">要定义新的 PSTN 用法记录并将其与此呼叫转接和同时响铃策略相关联，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="4ec2e-199">To define a new PSTN usage record and associate it with this call forwarding and simultaneous ringing policy, do the following:</span></span>

     <span data-ttu-id="4ec2e-200">a.</span><span class="sxs-lookup"><span data-stu-id="4ec2e-200">a.</span></span> <span data-ttu-id="4ec2e-201">单击"新建"。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-201">Click **New**.</span></span>

     <span data-ttu-id="4ec2e-202">b.</span><span class="sxs-lookup"><span data-stu-id="4ec2e-202">b.</span></span> <span data-ttu-id="4ec2e-203">在“名称”字段中，输入记录的唯一描述性名称。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-203">In the **Name** field, enter a unique descriptive name for the record.</span></span>

     > [!NOTE]
     > <span data-ttu-id="4ec2e-p132">PSTN 用法记录名称在企业语音部署中必须是唯一的。保存记录后，将无法编辑“名称”字段。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-p132">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the **Name** field cannot be edited.</span></span>

     <span data-ttu-id="4ec2e-206">c.</span><span class="sxs-lookup"><span data-stu-id="4ec2e-206">c.</span></span> <span data-ttu-id="4ec2e-207">使用以下任意方法为此 PSTN 用法记录关联和配置路由：</span><span class="sxs-lookup"><span data-stu-id="4ec2e-207">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>

   - <span data-ttu-id="4ec2e-208">要从企业语音部署中提供的所有路由列表中选择一个或多个路由，请单击“选择”，突出显示要与此 PSTN 用法记录相关联的路由，然后单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-208">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>

   - <span data-ttu-id="4ec2e-209">要删除 PSTN 用法记录中的某个路由，请突出显示相应的路由，然后单击“删除”。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-209">To remove a route from the PSTN usage record, highlight the route and click **Remove**.</span></span>

   - <span data-ttu-id="4ec2e-210">要定义新路由并将其与此 PSTN 用法记录相关联，请单击“新建”。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-210">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="4ec2e-211">有关详细信息，请参阅在 Skype for Business 中创建或修改 [语音路由](create-or-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-211">For details, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span>

   - <span data-ttu-id="4ec2e-212">要编辑已经与此 PSTN 用法记录相关联的路由，请突出显示相应的路由，然后单击“显示详细信息”。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-212">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span>

     <span data-ttu-id="4ec2e-213">d.</span><span class="sxs-lookup"><span data-stu-id="4ec2e-213">d.</span></span> <span data-ttu-id="4ec2e-214">单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-214">Click **OK**.</span></span>

   - <span data-ttu-id="4ec2e-215">要编辑已经与此语音策略相关联的 PSTN 用法记录，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="4ec2e-215">To edit a PSTN usage record that is already associated with this voice policy, do the following:</span></span>

     <span data-ttu-id="4ec2e-216">a.</span><span class="sxs-lookup"><span data-stu-id="4ec2e-216">a.</span></span> <span data-ttu-id="4ec2e-217">突出显示要编辑的 PSTN 用法记录，然后单击"显示 **详细信息"。**</span><span class="sxs-lookup"><span data-stu-id="4ec2e-217">Highlight the PSTN usage record you want to edit and click **Show details**.</span></span>

     <span data-ttu-id="4ec2e-218">b.</span><span class="sxs-lookup"><span data-stu-id="4ec2e-218">b.</span></span> <span data-ttu-id="4ec2e-219">使用以下任意方法为此 PSTN 用法记录关联和配置路由：</span><span class="sxs-lookup"><span data-stu-id="4ec2e-219">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>

   - <span data-ttu-id="4ec2e-220">要从企业语音部署中提供的所有路由列表中选择一个或多个路由，请单击“选择”，突出显示要与此 PSTN 用法记录相关联的路由，然后单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-220">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>

   - <span data-ttu-id="4ec2e-221">要删除此 PSTN 用法记录中的某个路由，请突出显示相应的路由，然后单击“删除”。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-221">To remove a route from this PSTN usage record, highlight the route and click **Remove**.</span></span>

   - <span data-ttu-id="4ec2e-222">要定义新路由并将其与此 PSTN 用法记录相关联，请单击“新建”。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-222">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="4ec2e-223">有关详细信息，请参阅在 Skype for Business 中创建或修改 [语音路由](create-or-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-223">For details, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span>

   - <span data-ttu-id="4ec2e-224">要编辑已经与此 PSTN 用法记录相关联的路由，请突出显示相应的路由，然后单击“显示详细信息”。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-224">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span>

     <span data-ttu-id="4ec2e-225">c.</span><span class="sxs-lookup"><span data-stu-id="4ec2e-225">c.</span></span> <span data-ttu-id="4ec2e-226">单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-226">Click **OK**.</span></span>

10. <span data-ttu-id="4ec2e-227">（可选）输入一个号码来测试语音策略，然后单击“执行”。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-227">(Optional) Enter a number to test the voice policy and click **Go**.</span></span> <span data-ttu-id="4ec2e-228">测试结果会显示在“要测试的转换号码”下。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-228">The test results are displayed under **Translated number to test**.</span></span>

11. <span data-ttu-id="4ec2e-229">单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-229">Click **OK**.</span></span>

12. <span data-ttu-id="4ec2e-230">在“语音策略”页上，单击“提交”，然后单击“全部提交”。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-230">On the **Voice Policy** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4ec2e-231">每次创建或修改语音策略时，都必须运行 **"全部提交** "命令以发布配置更改。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-231">Any time you create or modify a voice policy, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="4ec2e-232">有关详细信息，请参阅操作文档中的 Publish [pending changes to the voice routing configuration in Skype for Business。](voice-route-config-changes.md)</span><span class="sxs-lookup"><span data-stu-id="4ec2e-232">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

13. <span data-ttu-id="4ec2e-233"> (可选) 语音邮件转义"检测到用户的移动电话语音邮件立即应答了呼叫，并且断开了对移动电话语音邮件的呼叫。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-233">(Optional) Voicemail Escape detects that a call was immediately answered by the user's mobile phone voice mail, and disconnects the call to the mobile phone voice mail.</span></span> <span data-ttu-id="4ec2e-234">这允许呼叫继续在用户的其他终结点上响铃，从而让用户有机会应答呼叫。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-234">This allows the call to continue to ring on the user's other endpoints giving the user the opportunity to answer the call.</span></span> <span data-ttu-id="4ec2e-235">若要详细了解如何配置语音邮件策略，请参阅在 Skype for Business 中配置 [语音邮件转义](configure-voice-mail-escape.md)。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-235">For details on how to configure a voice mail policy, see [Configure voice mail escape in Skype for Business](configure-voice-mail-escape.md).</span></span>

### <a name="to-modify-a-voice-policy"></a><span data-ttu-id="4ec2e-236">修改语音策略</span><span class="sxs-lookup"><span data-stu-id="4ec2e-236">To modify a voice policy</span></span>

1. <span data-ttu-id="4ec2e-237">打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-237">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="4ec2e-238">在左侧导航栏中，单击“语音路由”，然后单击“语音策略”。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-238">In the left navigation bar, click **Voice Routing**, and then click **Voice Policy**.</span></span>

3. <span data-ttu-id="4ec2e-239">在“语音策略”页上，双击某个语音策略名称。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-239">On the **Voice Policy** page, double-click a voice policy name.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4ec2e-p143">作用域和名称是在创建语音策略时设置的，且不能更改。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-p143">The scope and name were set when the voice policy was created. They cannot be changed.</span></span>

4. <span data-ttu-id="4ec2e-242">（可选）在“编辑语音策略”中，输入语音策略的其他描述性信息。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-242">(Optional) In **Edit Voice Policy**, enter additional descriptive information for the voice policy.</span></span>

5. <span data-ttu-id="4ec2e-243">选中或清除以下复选框以启用或禁用每种“呼叫功能”：</span><span class="sxs-lookup"><span data-stu-id="4ec2e-243">Select or clear the following check boxes to enable or disable each of the **Calling features**:</span></span>

   - <span data-ttu-id="4ec2e-244">**语音邮件转** 义可防止在配置同时响铃、电话关闭、电池不足或范围外时将呼叫立即路由到用户的移动电话语音邮件系统。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-244">**Voice mail escape** prevents calls from being immediately routed to the user's mobile phone voice mail system when simultaneous ringing is configured and the phone is turned off, out of battery, or out of range.</span></span>

     > [!NOTE]
     > <span data-ttu-id="4ec2e-245">此功能仅可以通过 Skype for Business Server 命令行管理程序进行配置</span><span class="sxs-lookup"><span data-stu-id="4ec2e-245">This feature is only configurable through the Skype for Business Server Management Shell</span></span>

   - <span data-ttu-id="4ec2e-246">通过 **呼叫转接**，用户可以将呼叫转接到其他电话或客户端设备。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-246">**Call forwarding** enables users to forward calls to other phones and client devices.</span></span> <span data-ttu-id="4ec2e-247">Skype for Business Server 为呼叫转发提供了范围更广的配置选项。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-247">Skype for Business Server provides a significantly wider range of configuration options for call forwarding.</span></span> <span data-ttu-id="4ec2e-248">例如，如果组织不允许将传入呼叫外部转接到 PSTN，则管理员可应用特定语音策略来部署此限制。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-248">For example, if an organization does not want to allow incoming calls to be forwarded externally to the PSTN, an administrator can apply a special voice policy to deploy this restriction.</span></span> <span data-ttu-id="4ec2e-249">默认为启用。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-249">Enabled by default.</span></span>

   - <span data-ttu-id="4ec2e-250">通过 **委派**，用户可以指定其他用户代表他们发送和接收呼叫。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-250">**Delegation** enables users to specify other users to send and receive calls on their behalf.</span></span> <span data-ttu-id="4ec2e-251">在 Skype for Business Server 中，代理人可以配置同时响铃，从而允许呼叫其经理的传入呼叫拨打代理人的所有同时响铃目标。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-251">In Skype for Business Server, a delegate can configure simultaneous ringing that enables incoming calls to his or her manager to ring all of the delegate's simultaneous ringing targets.</span></span> <span data-ttu-id="4ec2e-252">这为代理提供了极大地灵活性以响应定向至管理员的呼叫。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-252">This provides the delegate with greater flexibility in responding to calls directed to the manager.</span></span> <span data-ttu-id="4ec2e-253">默认为启用。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-253">Enabled by default.</span></span>

   - <span data-ttu-id="4ec2e-p146">通过 **呼叫转移**，用户可以将呼叫转移到其他用户。默认为启用。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-p146">**Call transfer** enables users to transfer calls to other users. Enabled by default.</span></span>

   - <span data-ttu-id="4ec2e-p147">通过 **呼叫寄存**，用户可以寄存呼叫，将其置于保持状态，然后从其他电话或客户端接听呼叫。默认为禁用。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-p147">**Call park** enables users to park calls on hold, and then pick up the call from a different phone or client. Disabled by default.</span></span>

   - <span data-ttu-id="4ec2e-258">**同时响铃** 使传入呼叫可以在其他电话（如手机）或其他终结点设备上响铃。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-258">**Simultaneous ringing** enables incoming calls to ring on additional phones (for example, a mobile phone) or other endpoint devices.</span></span> <span data-ttu-id="4ec2e-259">Skype for Business Server 为同时响铃提供了范围更广的配置选项。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-259">Skype for Business Server provides a significantly wider range of configuration options for simultaneous ringing.</span></span> <span data-ttu-id="4ec2e-260">默认为启用。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-260">Enabled by default.</span></span>

   - <span data-ttu-id="4ec2e-261">通过 **团队呼叫**，指定团队中的用户可以为团队中的其他成员应答呼叫。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-261">**Team call** enables users on a defined team to answer calls for other members of the team.</span></span> <span data-ttu-id="4ec2e-262">默认为启用。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-262">Enabled by default.</span></span>

   - <span data-ttu-id="4ec2e-263">**PSTN 重新** 路由使分配了此策略的用户向其他企业用户拨打的呼叫可以在 WAN 变得塞或不可用时在 PSTN 上重新路由。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-263">**PSTN re-route** enables calls made by users who are assigned this policy to other enterprise users to be rerouted on the PSTN if the WAN is congested or unavailable.</span></span> <span data-ttu-id="4ec2e-264">默认为启用。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-264">Enabled by default.</span></span>

   - <span data-ttu-id="4ec2e-265">**通过带宽策略** 覆盖，管理员可以覆盖特定用户的 CAC 策略决策。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-265">**Bandwidth policy override** enables administrators to override CAC policy decisions for a particular user.</span></span> <span data-ttu-id="4ec2e-266">默认为禁用。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-266">Disabled by default.</span></span>

     > [!NOTE]
     > <span data-ttu-id="4ec2e-p152">只能覆盖向用户发出的传入呼叫的策略，而不能覆盖由用户发出的传出呼叫的策略。建立会话后，将准确记录带宽消耗。应慎用此设置。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-p152">The policy will be overridden only for incoming calls to the user and not for outgoing calls that are placed by the user. After the session is established, the bandwidth consumption will be accurately recorded. This setting should be used sparingly.</span></span>

   - <span data-ttu-id="4ec2e-270">**通过恶意** 呼叫跟踪，用户可以报告恶意 (，如) UI 发送的威胁，进而标记 CDR 中的呼叫。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-270">**Malicious call tracing** enables users to report malicious calls (such as threats) using the client UI, which in turn flags the calls in the CDRs.</span></span> <span data-ttu-id="4ec2e-271">默认为禁用。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-271">Disabled by default.</span></span>

6. <span data-ttu-id="4ec2e-272">要为此语音策略关联和配置 PSTN 用法记录，请执行以下任意操作：</span><span class="sxs-lookup"><span data-stu-id="4ec2e-272">To associate and configure PSTN usage records for this voice policy, do any of the following:</span></span>

   - <span data-ttu-id="4ec2e-p154">要从企业语音部署中提供的所有 PSTN 用法记录列表中选择一个或多个记录，请单击“选择”。突出显示要与此语音策略关联的记录，然后单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-p154">To choose one or more records from a list of all PSTN usage records available in your Enterprise Voice deployment, click **Select**. Highlight the records that you want to associate with this voice policy, and then click **OK**.</span></span>

   - <span data-ttu-id="4ec2e-275">要删除此语音策略中的某个 PSTN 用法记录，请突出显示相应的记录，然后单击“删除”。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-275">To remove a PSTN usage record from this voice policy, highlight the record and click **Remove**.</span></span>

   - <span data-ttu-id="4ec2e-276">要定义新的 PSTN 用法记录并将其与此语音策略相关联，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="4ec2e-276">To define a new PSTN usage record and associate it with this voice policy, do the following:</span></span>

     <span data-ttu-id="4ec2e-277">a.</span><span class="sxs-lookup"><span data-stu-id="4ec2e-277">a.</span></span> <span data-ttu-id="4ec2e-278">单击"新建"。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-278">Click **New**.</span></span>

     <span data-ttu-id="4ec2e-279">b.</span><span class="sxs-lookup"><span data-stu-id="4ec2e-279">b.</span></span> <span data-ttu-id="4ec2e-280">在“名称”字段中，输入记录的唯一描述性名称。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-280">In the **Name** field, enter a unique descriptive name for the record.</span></span> <span data-ttu-id="4ec2e-281">例如，您可能需要为 Redmond 的全职员工创建名为Redmond 的 PSTN 用法记录，为临时员工创建另一个名为RedmondTemps 的 PSTN 用法记录。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-281">For example, you may want to create a PSTN usage record namedRedmond for full-time employees located in Redmond, and another record namedRedmondTemps for temporary employees.</span></span>

     > [!NOTE]
     > <span data-ttu-id="4ec2e-p157">PSTN 用法记录名称在企业语音部署中必须是唯一的。保存记录后，将无法编辑“名称”字段。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-p157">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the **Name** field cannot be edited.</span></span>

     <span data-ttu-id="4ec2e-284">c.</span><span class="sxs-lookup"><span data-stu-id="4ec2e-284">c.</span></span> <span data-ttu-id="4ec2e-285">使用以下任意方法为此 PSTN 用法记录关联和配置路由：</span><span class="sxs-lookup"><span data-stu-id="4ec2e-285">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>

   - <span data-ttu-id="4ec2e-286">要从企业语音部署中提供的所有路由列表中选择一个或多个路由，请单击“选择”，突出显示要与此 PSTN 用法记录相关联的路由，然后单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-286">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>

   - <span data-ttu-id="4ec2e-287">要删除 PSTN 用法记录中的某个路由，请突出显示相应的路由，然后单击“删除”。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-287">To remove a route from the PSTN usage record, highlight the route and click **Remove**.</span></span>

   - <span data-ttu-id="4ec2e-288">要定义新路由并将其与此 PSTN 用法记录相关联，请单击“新建”。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-288">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="4ec2e-289">有关详细信息，请参阅在 Skype for Business 中创建或修改 [语音路由](create-or-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-289">For details, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span>

   - <span data-ttu-id="4ec2e-290">要编辑已经与此 PSTN 用法记录相关联的路由，请突出显示相应的路由，然后单击“显示详细信息”。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-290">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span>

     <span data-ttu-id="4ec2e-291">d.</span><span class="sxs-lookup"><span data-stu-id="4ec2e-291">d.</span></span> <span data-ttu-id="4ec2e-292">单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-292">Click **OK**.</span></span>

   - <span data-ttu-id="4ec2e-293">要编辑已经与此语音策略相关联的 PSTN 用法记录，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="4ec2e-293">To edit a PSTN usage record that is already associated with this voice policy, do the following:</span></span>

     <span data-ttu-id="4ec2e-294">a.</span><span class="sxs-lookup"><span data-stu-id="4ec2e-294">a.</span></span> <span data-ttu-id="4ec2e-295">突出显示要编辑的 PSTN 用法记录，然后单击“显示详细信息”。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-295">Highlight the PSTN usage record that you want to edit and click **Show details**.</span></span>

     <span data-ttu-id="4ec2e-296">b.</span><span class="sxs-lookup"><span data-stu-id="4ec2e-296">b.</span></span> <span data-ttu-id="4ec2e-297">使用以下任意方法为此 PSTN 用法记录关联和配置路由：</span><span class="sxs-lookup"><span data-stu-id="4ec2e-297">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>

   - <span data-ttu-id="4ec2e-298">要从企业语音部署中提供的所有路由列表中选择一个或多个路由，请单击“选择”，突出显示要与此 PSTN 用法记录相关联的路由，然后单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-298">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>

   - <span data-ttu-id="4ec2e-299">要删除此 PSTN 用法记录中的某个路由，请突出显示相应的路由，然后单击“删除”。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-299">To remove a route from this PSTN usage record, highlight the route and click **Remove**.</span></span>

   - <span data-ttu-id="4ec2e-300">要定义新路由并将其与此 PSTN 用法记录相关联，请单击“新建”。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-300">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="4ec2e-301">有关详细信息，请参阅在 Skype for Business 中创建或修改 [语音路由](create-or-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-301">For details, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span>

   - <span data-ttu-id="4ec2e-302">要编辑已经与此 PSTN 用法记录相关联的路由，请突出显示相应的路由，然后单击“显示详细信息”。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-302">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span>

     <span data-ttu-id="4ec2e-303">c.</span><span class="sxs-lookup"><span data-stu-id="4ec2e-303">c.</span></span> <span data-ttu-id="4ec2e-304">单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-304">Click **OK**.</span></span>

7. <span data-ttu-id="4ec2e-305">排列 PSTN 用法记录以获得最佳性能。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-305">Arrange the PSTN usage records for optimum performance.</span></span> <span data-ttu-id="4ec2e-306">若要更改记录在列表中的位置，请突出显示记录名称，然后单击向上箭头或向下箭头。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-306">To change a record's position in the list, highlight the record name and click the up or down arrow.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4ec2e-307">PSTN 用法记录在语音策略中的列出顺序十分重要。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-307">The order in which PSTN usage records are listed in the voice policy is significant.</span></span> <span data-ttu-id="4ec2e-308">Skype for Business Server 从上到下遍历该列表。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-308">Skype for Business Server traverses the list from the top down.</span></span> <span data-ttu-id="4ec2e-309">建议按使用频率来组织该列表，例如：RedmondLocal、RedmondLongDist、RedmondInternational 和 RedmondBackup。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-309">We recommend that you organize the list by frequency of use, for example: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span></span>

8. <span data-ttu-id="4ec2e-310">要为此语音策略中的呼叫转接和同时响铃关联和配置 PSTN 用法记录，请执行以下任一操作：</span><span class="sxs-lookup"><span data-stu-id="4ec2e-310">To associate and configure PSTN usage records for call forwarding and simultaneous ringing in this voice policy, do any of the following:</span></span>

   - <span data-ttu-id="4ec2e-311">若要对呼叫转接和同时响铃使用与此语音策略相同的 PSTN 用法记录，请从下拉菜单中选择“使用呼叫 PSTN 用法进行路由”。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-311">To use the same PSTN usage records for call forwarding and simultaneous ringing as this voice policy, select the option **Route using the call PSTN usages** from the drop-down menu.</span></span>

   - <span data-ttu-id="4ec2e-312">若要仅允许向内部 Skype for Business 用户进行呼叫转发和同时响铃，请仅从下拉菜单中选择路由到内部 **Skype for Business** 用户。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-312">To allow call forwarding and simultaneous ringing to internal Skype for Business users only, select **Route to internal Skype for Business users only** from the drop-down menu.</span></span> <span data-ttu-id="4ec2e-313">呼叫将不会转接到外部 PSTN 号码。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-313">Calls will not be forwarded to external PSTN numbers.</span></span>

   - <span data-ttu-id="4ec2e-p168">若要为呼叫转接和同时响铃指定与此语音策略所用的 PSTN 用法记录不同的 PSTN 用法记录，请从下拉菜单中选择“使用自定义 PSTN 用法进行路由”。此选项显示一个控件，此控件专用于为呼叫转接和同时响铃选择现有 PSTN 用法记录或创建新的 PSTN 用法记录。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-p168">To specify different PSTN usage records for call forwarding and simultaneous ringing than those used for this voice policy, select the option **Route using custom PSTN usages** from the drop-down menu. This option displays a control to select existing PSTN usage records or to create new PSTN usage records, specifically for call forwarding and simultaneous ringing.</span></span>

   - <span data-ttu-id="4ec2e-p169">要从呼叫转接和同时响铃的 PSTN 用法记录列表中选择一个或多个记录，请单击“选择”。突出显示要与此呼叫转接和同时响铃策略关联的记录，然后单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-p169">To choose one or more records from a list of PSTN usage records for call forwarding and simultaneous ringing, click **Select**. Highlight the records that you want to associate with this call forwarding and simultaneous ringing policy, and then click **OK**.</span></span>

   - <span data-ttu-id="4ec2e-318">要从此呼叫转接和同时响铃策略中删除某个 PSTN 用法记录，请突出显示相应的记录，然后单击“删除”。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-318">To remove a PSTN usage record from this call forwarding and simultaneous ringing policy, highlight the record and click **Remove**.</span></span>

   - <span data-ttu-id="4ec2e-319">要定义新的 PSTN 用法记录并将其与此呼叫转接和同时响铃策略相关联，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="4ec2e-319">To define a new PSTN usage record and associate it with this call forwarding and simultaneous ringing policy, do the following:</span></span>

     <span data-ttu-id="4ec2e-320">a.</span><span class="sxs-lookup"><span data-stu-id="4ec2e-320">a.</span></span> <span data-ttu-id="4ec2e-321">单击"新建"。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-321">Click **New**.</span></span>

     <span data-ttu-id="4ec2e-322">b.</span><span class="sxs-lookup"><span data-stu-id="4ec2e-322">b.</span></span> <span data-ttu-id="4ec2e-323">在“名称”字段中，输入记录的唯一描述性名称。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-323">In the **Name** field, enter a unique descriptive name for the record.</span></span>

     > [!NOTE]
     > <span data-ttu-id="4ec2e-p172">PSTN 用法记录名称在企业语音部署中必须是唯一的。保存记录后，将无法编辑“名称”字段。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-p172">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the **Name** field cannot be edited.</span></span>

     <span data-ttu-id="4ec2e-326">c.</span><span class="sxs-lookup"><span data-stu-id="4ec2e-326">c.</span></span> <span data-ttu-id="4ec2e-327">使用以下任意方法为此 PSTN 用法记录关联和配置路由：</span><span class="sxs-lookup"><span data-stu-id="4ec2e-327">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>

   - <span data-ttu-id="4ec2e-328">要从企业语音部署中提供的所有路由列表中选择一个或多个路由，请单击“选择”，突出显示要与此 PSTN 用法记录相关联的路由，然后单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-328">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>

   - <span data-ttu-id="4ec2e-329">要删除 PSTN 用法记录中的某个路由，请突出显示相应的路由，然后单击“删除”。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-329">To remove a route from the PSTN usage record, highlight the route and click **Remove**.</span></span>

   - <span data-ttu-id="4ec2e-330">要定义新路由并将其与此 PSTN 用法记录相关联，请单击“新建”。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-330">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="4ec2e-331">有关详细信息，请参阅在 Skype for Business 中创建或修改 [语音路由](create-or-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-331">For details, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span>

   - <span data-ttu-id="4ec2e-332">要编辑已经与此 PSTN 用法记录相关联的路由，请突出显示相应的路由，然后单击“显示详细信息”。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-332">To edit a route that is already associated with this PSTN usage record, highlight the route, and then click **Show details**.</span></span> <span data-ttu-id="4ec2e-333">有关详细信息，请参阅[Modify a Voice Route](/previous-versions/office/lync-server-2013/lync-server-2013-modify-a-voice-route)。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-333">For details, see [Modify a Voice Route](/previous-versions/office/lync-server-2013/lync-server-2013-modify-a-voice-route).</span></span>

     <span data-ttu-id="4ec2e-334">d.</span><span class="sxs-lookup"><span data-stu-id="4ec2e-334">d.</span></span> <span data-ttu-id="4ec2e-335">单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-335">Click **OK**.</span></span>

   - <span data-ttu-id="4ec2e-336">要编辑已经与此语音策略相关联的 PSTN 用法记录，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="4ec2e-336">To edit a PSTN usage record that is already associated with this voice policy, do the following:</span></span>

     <span data-ttu-id="4ec2e-337">a.</span><span class="sxs-lookup"><span data-stu-id="4ec2e-337">a.</span></span> <span data-ttu-id="4ec2e-338">突出显示要编辑的 PSTN 用法记录，然后单击“显示详细信息”。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-338">Highlight the PSTN usage record that you want to edit and click **Show details**.</span></span>

     <span data-ttu-id="4ec2e-339">b.</span><span class="sxs-lookup"><span data-stu-id="4ec2e-339">b.</span></span> <span data-ttu-id="4ec2e-340">使用以下任意方法为此 PSTN 用法记录关联和配置路由：</span><span class="sxs-lookup"><span data-stu-id="4ec2e-340">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>

     - <span data-ttu-id="4ec2e-341">要从企业语音部署中提供的所有路由列表中选择一个或多个路由，请单击“选择”，突出显示要与此 PSTN 用法记录相关联的路由，然后单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-341">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes you want to associate with this PSTN usage record, and then click **OK**.</span></span>

     - <span data-ttu-id="4ec2e-342">要删除此 PSTN 用法记录中的某个路由，请突出显示相应的路由，然后单击“删除”。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-342">To remove a route from this PSTN usage record, highlight the route and click **Remove**.</span></span>

     - <span data-ttu-id="4ec2e-343">要定义新路由并将其与此 PSTN 用法记录相关联，请单击“新建”。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-343">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="4ec2e-344">有关详细信息，请参阅在 Skype for Business 中创建或修改 [语音路由](create-or-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-344">For details, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span>

     - <span data-ttu-id="4ec2e-345">要编辑已经与此 PSTN 用法记录相关联的路由，请突出显示相应的路由，然后单击“显示详细信息”。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-345">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="4ec2e-346">有关详细信息，请参阅[Modify a Voice Route](/previous-versions/office/lync-server-2013/lync-server-2013-modify-a-voice-route)。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-346">For details, see [Modify a Voice Route](/previous-versions/office/lync-server-2013/lync-server-2013-modify-a-voice-route).</span></span>

     <span data-ttu-id="4ec2e-347">c.</span><span class="sxs-lookup"><span data-stu-id="4ec2e-347">c.</span></span> <span data-ttu-id="4ec2e-348">单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-348">Click **OK**.</span></span>

9. <span data-ttu-id="4ec2e-349">（可选）输入一个号码来测试语音策略，然后单击“执行”。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-349">(Optional) Enter a number to test the voice policy and click **Go**.</span></span> <span data-ttu-id="4ec2e-350">测试结果会显示在“要测试的转换号码”下。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-350">The test results are displayed under **Translated number to test**.</span></span>

10. <span data-ttu-id="4ec2e-351">单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-351">Click **OK**.</span></span>

11. <span data-ttu-id="4ec2e-352">在“语音策略”页上，单击“提交”，然后单击“全部提交”。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-352">On the **Voice Policy** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4ec2e-353">只要创建或修改语音策略，就必须运行“全部提交”命令以发布配置更改。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-353">Whenever you create or modify a voice policy, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="4ec2e-354">有关详细信息，请参阅操作文档中的 Publish [pending changes to the voice routing configuration in Skype for Business。](voice-route-config-changes.md)</span><span class="sxs-lookup"><span data-stu-id="4ec2e-354">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

12. <span data-ttu-id="4ec2e-355"> (可选) 语音邮件转义"检测到用户的移动电话语音邮件立即应答了呼叫，并且断开了对移动电话语音邮件的呼叫。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-355">(Optional) Voicemail Escape detects that a call was immediately answered by the user's mobile phone voice mail, and disconnects the call to the mobile phone voice mail.</span></span> <span data-ttu-id="4ec2e-356">这允许呼叫继续在用户的其他终结点上响铃，从而让用户有机会应答呼叫。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-356">This allows the call to continue to ring on the user's other endpoints giving the user the opportunity to answer the call.</span></span> <span data-ttu-id="4ec2e-357">若要详细了解如何配置语音邮件策略，请参阅在 Skype for Business 中配置 [语音邮件转义](configure-voice-mail-escape.md)。</span><span class="sxs-lookup"><span data-stu-id="4ec2e-357">For details about how to configure a voice mail policy, see [Configure voice mail escape in Skype for Business](configure-voice-mail-escape.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="4ec2e-358">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4ec2e-358">See also</span></span>

[<span data-ttu-id="4ec2e-359">在 Skype for Business 中查看 PSTN 用法记录</span><span class="sxs-lookup"><span data-stu-id="4ec2e-359">View PSTN usage records in Skype for Business</span></span>](view-pstn-usage-records.md)

[<span data-ttu-id="4ec2e-360">在 Skype for Business 中创建或修改语音路由</span><span class="sxs-lookup"><span data-stu-id="4ec2e-360">Create or modify a voice route in Skype for Business</span></span>](create-or-modify-a-voice-route.md)

[<span data-ttu-id="4ec2e-361">在 Skype for Business 中发布对语音路由配置的挂起更改</span><span class="sxs-lookup"><span data-stu-id="4ec2e-361">Publish pending changes to the voice routing configuration in Skype for Business</span></span>](voice-route-config-changes.md)

[<span data-ttu-id="4ec2e-362">在 Skype for Business 中配置语音邮件转义</span><span class="sxs-lookup"><span data-stu-id="4ec2e-362">Configure voice mail escape in Skype for Business</span></span>](configure-voice-mail-escape.md)