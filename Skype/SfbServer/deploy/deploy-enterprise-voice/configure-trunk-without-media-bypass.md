---
title: 在 Skype for Business 服务器中配置不使用媒体的主干
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
ms.assetid: 3422e93e-7bd2-4470-968c-dc38345b18ca
description: '摘要: 配置不为 Skype for Business 服务器启用 "媒体绕过媒体" 的主干。'
ms.openlocfilehash: c60217b6dc127616dfbaf9590c43adec25c20eff
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233662"
---
# <a name="configure-a-trunk-without-media-bypass-in-skype-for-business-server"></a><span data-ttu-id="bef5e-103">在 Skype for Business 服务器中配置不使用媒体的主干</span><span class="sxs-lookup"><span data-stu-id="bef5e-103">Configure a trunk without media bypass in Skype for Business Server</span></span>

<span data-ttu-id="bef5e-104">**摘要:** 配置不为 Skype for business 服务器启用 "媒体旁路" 的主干。</span><span class="sxs-lookup"><span data-stu-id="bef5e-104">**Summary:** Configure a trunk without media bypass enabled for Skype for Business Server.</span></span>

<span data-ttu-id="bef5e-105">如果要配置禁用媒体旁路功能的中继，请执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="bef5e-105">If you want to configure a trunk with media bypass disabled, follow these steps.</span></span> <span data-ttu-id="bef5e-106">如果你想要配置支持媒体旁路的主干, 请参阅[在 Skype For Business 服务器中使用媒体旁路配置主干](configure-trunk-with-media-bypass.md)。</span><span class="sxs-lookup"><span data-stu-id="bef5e-106">If you want to configure a trunk with media bypass enabled, see [Configure a trunk with media bypass in Skype for Business Server](configure-trunk-with-media-bypass.md).</span></span>

<span data-ttu-id="bef5e-p102">如下所述，中继配置可对应用于已分配此中继配置的中继的一组参数进行分组。特定中继配置的作用域可以是全局中继（针对没有更多特定站点或池配置的所有中继）、站点或者池。池级中继配置用于将特定中继配置的作用域限制为单个中继。</span><span class="sxs-lookup"><span data-stu-id="bef5e-p102">A trunk configuration, as described below, groups a set of parameters that are applied to trunks assigned this trunk configuration. A particular trunk configuration can be scoped globally (to all trunks that do not have more specific site or pool configuration), or to a site, or to a pool. The pool-level trunk configuration is used to scope a specific trunk configuration to a single trunk.</span></span>

### <a name="to-configure-a-trunk-without-media-bypass"></a><span data-ttu-id="bef5e-110">配置无媒体旁路功能的中继</span><span class="sxs-lookup"><span data-stu-id="bef5e-110">To configure a trunk without media bypass</span></span>

1. <span data-ttu-id="bef5e-111">打开 "Skype for Business 服务器" 控制面板。</span><span class="sxs-lookup"><span data-stu-id="bef5e-111">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="bef5e-112">在左侧导航栏中，单击“语音路由”\*\*\*\*，然后单击“Trunk 配置”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bef5e-112">In the left navigation bar, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

3. <span data-ttu-id="bef5e-113">在“Trunk 配置”\*\*\*\* 页上，使用以下方法之一配置中继：</span><span class="sxs-lookup"><span data-stu-id="bef5e-113">On the **Trunk Configuration** page, use one of the following methods to configure a trunk:</span></span>

   - <span data-ttu-id="bef5e-114">双击某个现有的中继（例如“全局”\*\*\*\* 中继）以显示“编辑 Trunk 配置”\*\*\*\* 对话框。</span><span class="sxs-lookup"><span data-stu-id="bef5e-114">Double-click an existing trunk (for example, the **Global** trunk) to display the **Edit Trunk Configuration** dialog box.</span></span>

   - <span data-ttu-id="bef5e-115">单击“新建”\*\*\*\*，然后为新的中继配置选择范围：</span><span class="sxs-lookup"><span data-stu-id="bef5e-115">Click **New**, and then select a scope for the new trunk configuration:</span></span>

   - <span data-ttu-id="bef5e-116">**网站主干**: 在 "**选择网站**" 中选择此中继配置的网站, 然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="bef5e-116">**Site trunk**: Choose the site for this trunk configuration in **Select a Site**, and then click **OK**.</span></span> <span data-ttu-id="bef5e-117">请注意，如果已经为站点创建了中继配置，则该站点不会显示在“选择站点”\*\*\*\* 中。</span><span class="sxs-lookup"><span data-stu-id="bef5e-117">Note that if a trunk configuration has already been created for a site, the site does not appear in **Select a Site**.</span></span> <span data-ttu-id="bef5e-118">此中继配置将应用于站点中的所有中继。</span><span class="sxs-lookup"><span data-stu-id="bef5e-118">This trunk configuration will be applied to all trunks in the site.</span></span>

   - <span data-ttu-id="bef5e-119">**池 Trunk**：在“选择服务”\*\*\*\* 中选择此中继配置应用于的中继的名称，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bef5e-119">**Pool trunk**: Choose the name of the trunk that this trunk configuration applies to in **Select a Service** and click **OK**.</span></span> <span data-ttu-id="bef5e-120">此主干可以是根主干, 也可以是拓扑生成器中定义的任何其他中继。</span><span class="sxs-lookup"><span data-stu-id="bef5e-120">This trunk can be the root trunk, or any additional trunks defined in Topology Builder.</span></span> <span data-ttu-id="bef5e-121">请注意，如果已经为特定中继创建了中继配置，则该中继不会显示在“选择服务”\*\*\*\* 中。</span><span class="sxs-lookup"><span data-stu-id="bef5e-121">Note that if a trunk configuration has already been created for a specific trunk, the trunk does not appear in **Select a Service**.</span></span>

     > [!NOTE]
     > <span data-ttu-id="bef5e-122">选择中继配置的范围后无法更改该范围。</span><span class="sxs-lookup"><span data-stu-id="bef5e-122">After you select the scope of the trunk configuration, it cannot be changed.</span></span> <span data-ttu-id="bef5e-123">> "**名称**" 字段中预填充了中继配置的关联站点或服务的名称, 无法更改。</span><span class="sxs-lookup"><span data-stu-id="bef5e-123">> The **Name** field is pre-populated with the name of the trunk configuration's associated site or service and cannot be changed.</span></span>

4. <span data-ttu-id="bef5e-124">选择以下“加密支持级别”\*\*\*\* 选项之一：</span><span class="sxs-lookup"><span data-stu-id="bef5e-124">Select one of the following **Encryption support level** options:</span></span>

   - <span data-ttu-id="bef5e-125">**必需**：必须使用安全实时传输协议 (SRTP) 加密以帮助保护中介服务器与网关或专用交换机 (PBX) 之间的通信。</span><span class="sxs-lookup"><span data-stu-id="bef5e-125">**Required**: Secure Realtime Transport Protocol (SRTP) encryption must be used to help protect traffic between the Mediation Server and the gateway or Private Branch eXchange (PBX).</span></span>

   - <span data-ttu-id="bef5e-126">**可选**：如果服务提供商或设备制造商支持 SRTP，则使用 SRTP 加密。</span><span class="sxs-lookup"><span data-stu-id="bef5e-126">**Optional**: SRTP encryption will be used if the service provider or equipment manufacturer supports it.</span></span>

   - <span data-ttu-id="bef5e-127">**不支持**：SRTP 加密不受服务提供商或设备制造商支持，因此不使用。</span><span class="sxs-lookup"><span data-stu-id="bef5e-127">**Not Supported**: SRTP encryption is not supported by the service provider or equipment manufacturer and therefore will not be used.</span></span>

5. <span data-ttu-id="bef5e-128">确保已清除“启用媒体旁路”\*\*\*\* 复选框。</span><span class="sxs-lookup"><span data-stu-id="bef5e-128">Be sure that the **Enable media bypass** check box is cleared.</span></span>

6. <span data-ttu-id="bef5e-p106">如果存在一个已知的媒体端点（例如公用电话交换网 (PSTN) 网关，其中媒体终端与信号终端具有相同的 IP），则选中“集中式媒体处理”\*\*\*\* 复选框。如果中继没有已知的媒体端点，则清除该复选框。</span><span class="sxs-lookup"><span data-stu-id="bef5e-p106">Select the **Centralized media processing** check box if there is a well-known media termination point (for example, a Public Switched Telephone Network (PSTN) gateway where the media termination has the same IP as the signaling termination). Clear this check box if the trunk does not have a well-known media termination point.</span></span>

7. <span data-ttu-id="bef5e-131">如果中继对等支持接收来自中介服务器的 SIP, 请选中 "**启用发送指向网关**的请求" 复选框。</span><span class="sxs-lookup"><span data-stu-id="bef5e-131">If the trunk peer supports receiving SIP REFER requests from the Mediation Server, select the **Enable sending refer to the gateway** check box.</span></span>

8. <span data-ttu-id="bef5e-132">（可选）若要启用中继间路由，请将 PSTN 用法记录关联到此中继配置并进行相应的配置。</span><span class="sxs-lookup"><span data-stu-id="bef5e-132">(Optional) To enable inter-trunk routing, associate and configure PSTN usage records to this trunk configuration.</span></span> <span data-ttu-id="bef5e-133">与此中继配置关联的 PSTN 用法将应用于所有传入呼叫, 该主干不是从 Skype for business 服务器终结点发起的。</span><span class="sxs-lookup"><span data-stu-id="bef5e-133">The PSTN usages associated to this trunk configuration will be applied for all incoming calls through the trunk that is not originating from a Skype for Business Server endpoint.</span></span> <span data-ttu-id="bef5e-134">若要管理与中继配置关联的 PSTN 用法记录，请使用下列方法之一：</span><span class="sxs-lookup"><span data-stu-id="bef5e-134">To manage PSTN usage records associated to a trunk configuration, use one of the following methods:</span></span>

   - <span data-ttu-id="bef5e-135">若要从您的企业语音部署中可用的所有 PSTN 使用记录列表中选择一个或多个记录, 请单击 "**选择**"。</span><span class="sxs-lookup"><span data-stu-id="bef5e-135">To select one or more records from a list of all PSTN usage records available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="bef5e-136">突出显示要与此中继配置关联的记录，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bef5e-136">Highlight the records you want to associate with this trunk configuration and then click **OK**.</span></span>

   - <span data-ttu-id="bef5e-137">要删除此中继配置中的某个 PSTN 用法记录，请选择此记录，并单击“删除”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bef5e-137">To remove a PSTN usage record from this trunk configuration, select the record and click **Remove**.</span></span>

   - <span data-ttu-id="bef5e-138">要定义新的 PSTN 用法记录并将其与此中继配置相关联，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="bef5e-138">To define a new PSTN usage record and associate it with this trunk configuration, do the following:</span></span>

     <span data-ttu-id="bef5e-139">a.</span><span class="sxs-lookup"><span data-stu-id="bef5e-139">a.</span></span> <span data-ttu-id="bef5e-140">单击“新建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bef5e-140">Click **New**.</span></span>

     <span data-ttu-id="bef5e-141">b.</span><span class="sxs-lookup"><span data-stu-id="bef5e-141">b.</span></span> <span data-ttu-id="bef5e-142">在“名称”\*\*\*\* 字段中，为记录指定唯一的描述性名称。</span><span class="sxs-lookup"><span data-stu-id="bef5e-142">In the **Name** field, specify a descriptive name for the record that is unique.</span></span>

     > [!NOTE]
     > <span data-ttu-id="bef5e-p111">PSTN 用法记录名称在企业语音部署中必须是唯一的。保存记录后，将无法编辑“名称”\*\*\*\* 字段。</span><span class="sxs-lookup"><span data-stu-id="bef5e-p111">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the **Name** field cannot be edited.</span></span>

     <span data-ttu-id="bef5e-145">c.</span><span class="sxs-lookup"><span data-stu-id="bef5e-145">c.</span></span> <span data-ttu-id="bef5e-146">使用下列方法之一为此 PSTN 用法记录关联和配置路由：</span><span class="sxs-lookup"><span data-stu-id="bef5e-146">Use one of the following methods to associate and configure routes for this PSTN usage record:</span></span>

     - <span data-ttu-id="bef5e-147">若要从您的企业语音部署中的所有可用路由列表中选择一个或多个路由, 请单击 "**选择**"。</span><span class="sxs-lookup"><span data-stu-id="bef5e-147">To select one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="bef5e-148">突出显示要与此 PSTN 用法记录相关联的路由，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bef5e-148">Highlight the routes you want to associate with this PSTN usage record, and click **OK**.</span></span>

     - <span data-ttu-id="bef5e-149">要删除 PSTN 用法记录中的某个路由，请选择此路由，然后单击“删除”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bef5e-149">To remove a route from the PSTN usage record, select the route, and click **Remove**.</span></span>

     - <span data-ttu-id="bef5e-150">要定义新路由并将其与此 PSTN 用法记录相关联，请单击“新建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bef5e-150">To define a new route and associate it to this PSTN usage record, click **New**.</span></span> <span data-ttu-id="bef5e-151">有关详细信息, 请参阅[在 Skype For business 中创建或修改语音路线](create-or-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="bef5e-151">For details, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span>

     - <span data-ttu-id="bef5e-152">要编辑与此 PSTN 用法记录相关联的路由，请选择此路由，然后单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bef5e-152">To edit a route that is associated with this PSTN usage record, select the route, and click **Show details**.</span></span>

     <span data-ttu-id="bef5e-153">d.</span><span class="sxs-lookup"><span data-stu-id="bef5e-153">d.</span></span> <span data-ttu-id="bef5e-154">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="bef5e-154">Click **OK**.</span></span>

   - <span data-ttu-id="bef5e-155">要编辑已经与此中继配置相关联的 PSTN 用法记录，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="bef5e-155">To edit a PSTN usage record that is already associated with this trunk configuration, do the following:</span></span>

     <span data-ttu-id="bef5e-156">a.</span><span class="sxs-lookup"><span data-stu-id="bef5e-156">a.</span></span> <span data-ttu-id="bef5e-157">选择要编辑的 PSTN 用法记录，然后单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bef5e-157">Select the PSTN usage record you want to edit, and click **Show details**.</span></span>

     <span data-ttu-id="bef5e-158">b.</span><span class="sxs-lookup"><span data-stu-id="bef5e-158">b.</span></span> <span data-ttu-id="bef5e-159">使用下列方法之一为此 PSTN 用法记录关联和配置路由：</span><span class="sxs-lookup"><span data-stu-id="bef5e-159">Use one of the following methods to associate and configure routes for this PSTN usage record:</span></span>

     - <span data-ttu-id="bef5e-160">若要从您的企业语音部署中的所有可用路由列表中选择一个或多个路由, 请单击 "**选择**"。</span><span class="sxs-lookup"><span data-stu-id="bef5e-160">To select one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="bef5e-161">突出显示要与此 PSTN 用法记录相关联的路由，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bef5e-161">Highlight the routes you want to associate with this PSTN usage record, and click **OK**.</span></span>

     - <span data-ttu-id="bef5e-162">要删除 PSTN 用法记录中的某个路由，请选择此路由，然后单击“删除”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bef5e-162">To remove a route from the PSTN usage record, select the route, and click **Remove**.</span></span>

     - <span data-ttu-id="bef5e-163">要定义新路由并将其与此 PSTN 用法记录相关联，请单击“新建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bef5e-163">To define a new route and associate it to this PSTN usage record, click **New**.</span></span> <span data-ttu-id="bef5e-164">有关详细信息, 请参阅[在 Skype For business 中创建或修改语音路线](create-or-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="bef5e-164">For details, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span>

     - <span data-ttu-id="bef5e-165">要编辑与此 PSTN 用法记录相关联的路由，请选择此路由，然后单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bef5e-165">To edit a route that is associated with this PSTN usage record, select the route, and click **Show details**.</span></span>

     <span data-ttu-id="bef5e-166">c.</span><span class="sxs-lookup"><span data-stu-id="bef5e-166">c.</span></span> <span data-ttu-id="bef5e-167">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="bef5e-167">Click **OK**.</span></span>

     > [!IMPORTANT]
     > <span data-ttu-id="bef5e-168">根据与正在配置的主干相关联的中介服务器对, 关联 PSTN 使用记录非常重要。</span><span class="sxs-lookup"><span data-stu-id="bef5e-168">It is important to associate PSTN usage records according to the Mediation Server peer that is associated to the trunk being configured.</span></span> <span data-ttu-id="bef5e-169">如果中介服务器对等是 PSTN 网关或会话边界控制器 (SBC), 强烈建议不要将干线配置与路由到 PSTN 目标或通过 Skype 连接的任何其他下游系统的 PSTN 使用记录相关联适用于企业服务器。</span><span class="sxs-lookup"><span data-stu-id="bef5e-169">If the Mediation Server peer is a PSTN gateway or a Session Border Controller (SBC), it is strongly recommended that the trunk configuration is not associated to a PSTN usage record that routes to a PSTN destination or any other downstream systems connected via Skype for Business Server.</span></span>

9. <span data-ttu-id="bef5e-170">排列 PSTN 用法记录以获得最佳性能。</span><span class="sxs-lookup"><span data-stu-id="bef5e-170">Arrange the PSTN usage records for optimum performance.</span></span> <span data-ttu-id="bef5e-171">若要更改记录在列表中的位置, 请选择 PSTN 使用记录, 然后单击向上或向下箭头。</span><span class="sxs-lookup"><span data-stu-id="bef5e-171">To change a record's position in the list, select the PSTN usage record, and click the up or down arrows.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="bef5e-172">PSTN 用法记录在中继配置中列出的顺序很重要。</span><span class="sxs-lookup"><span data-stu-id="bef5e-172">The order in which PSTN usage records are listed in the trunk configuration is significant.</span></span> <span data-ttu-id="bef5e-173">Skype for Business 服务器从上到下遍历列表。</span><span class="sxs-lookup"><span data-stu-id="bef5e-173">Skype for Business Server traverses the list from top to down.</span></span>

10. <span data-ttu-id="bef5e-174">应选择“启用 RTP 闭锁”\*\*\*\*，以便为 NAT 或防火墙之后的客户端以及支持闭锁的 SBC 启用媒体旁路。</span><span class="sxs-lookup"><span data-stu-id="bef5e-174">**Enable RTP Latching** should be selected to enable bypass media for clients behind a NAT or firewall and an SBC that supports latching.</span></span>

11. <span data-ttu-id="bef5e-175">应选择 "**启用转发呼叫" 历史记录**, 以便为中介服务器的网关对等发送呼叫历史记录信息。</span><span class="sxs-lookup"><span data-stu-id="bef5e-175">**Enable forward call history** should be selected to enable sending of call history information to the gateway peer of the Mediation Server.</span></span>

12. <span data-ttu-id="bef5e-176">**启用前向 P 声明的标识数据**应选中以启用 PAI 呼叫发起人信息, 以便在中介服务器端和网关端 (反之亦然) 之间转发。</span><span class="sxs-lookup"><span data-stu-id="bef5e-176">**Enable forward P-Asserted-Identity data** should be selected to enable PAI call originator information to be forwarded between the Mediation Server side and gateway side (and vice versa), when present.</span></span>

13. <span data-ttu-id="bef5e-177">应选择“启用出站路由故障转移计时器”\*\*\*\* 以启用快速故障转移。</span><span class="sxs-lookup"><span data-stu-id="bef5e-177">**Enable outbound routing failover timer** should be selected to enable fast failover.</span></span> <span data-ttu-id="bef5e-178">与此中继关联的网关会在 10 秒内发送通知，告知正在处理出站呼叫。</span><span class="sxs-lookup"><span data-stu-id="bef5e-178">The gateway associated with this trunk can give notification within 10 seconds that it is processing an outbound call.</span></span> <span data-ttu-id="bef5e-179">如果中介服务器未收到此通知, 将会重新路由到另一个主干。</span><span class="sxs-lookup"><span data-stu-id="bef5e-179">Rerouting to another trunk will occur if this notification is not received by the Mediation Server.</span></span> <span data-ttu-id="bef5e-180">在延迟可能推迟响应时间或网关需要花费 10 秒以上的时间才能响应，应禁用快速故障转移。</span><span class="sxs-lookup"><span data-stu-id="bef5e-180">On networks where latency may delay the response time or the gateway takes longer than 10 seconds to respond, the fast failover should be disabled.</span></span>

14. <span data-ttu-id="bef5e-181">（可选）为中继关联和配置“主叫号码转换规则”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bef5e-181">(Optional) Associate and configure **calling number translation rules** for the trunk.</span></span> <span data-ttu-id="bef5e-182">这些转换规则适用于出站呼叫的主叫号码</span><span class="sxs-lookup"><span data-stu-id="bef5e-182">These translation rules apply to the calling number for outbound calls</span></span>

    - <span data-ttu-id="bef5e-183">若要从您的企业语音部署中可用的所有翻译规则列表中选择一个或多个规则, 请单击 "**选择**"。</span><span class="sxs-lookup"><span data-stu-id="bef5e-183">To choose one or more rules from a list of all translation rules that are available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="bef5e-184">在“选择转换规则”\*\*\*\* 中，单击要与中继关联的规则，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bef5e-184">In **Select Translation Rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>

    - <span data-ttu-id="bef5e-185">要定义新的转换规则并将其与中继相关联，请单击“新建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bef5e-185">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="bef5e-186">有关翻译规则的详细信息, 请参阅[Skype For Business 服务器中的翻译规则](../../plan-your-deployment/enterprise-voice-solution/translation-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="bef5e-186">For details about translation rules, see [Translation rules in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/translation-rules.md).</span></span>

    - <span data-ttu-id="bef5e-187">要编辑已与中继关联的转换规则，请单击相应的规则名称，然后单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bef5e-187">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span>

    - <span data-ttu-id="bef5e-188">要复制现有的转换规则以作为定义新规则的起点，请单击相应的规则名称，再单击“复制”\*\*\*\*，然后单击“粘贴”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bef5e-188">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span>

    - <span data-ttu-id="bef5e-189">要从中继删除某个转换规则，请突出显示相应的规则名称，然后单击“删除”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bef5e-189">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>

      > [!CAUTION]
      > <span data-ttu-id="bef5e-190">如果已在关联的中继对等方上配置了转换规则，则不要将任何转换规则与中继相关联，因为这两种规则可能会发生冲突。</span><span class="sxs-lookup"><span data-stu-id="bef5e-190">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>

15. <span data-ttu-id="bef5e-p128">（可选）为中继关联和配置“被叫号码转换规则”\*\*\*\*。这些转换规则适用于出站呼叫的被叫号码。</span><span class="sxs-lookup"><span data-stu-id="bef5e-p128">(Optional) Associate and configure **called number translation rules** for the trunk. The translation rules apply to the called number in an outbound call.</span></span>

    - <span data-ttu-id="bef5e-193">若要从您的企业语音部署中可用的所有翻译规则列表中选择一个或多个规则, 请单击 "**选择**"。</span><span class="sxs-lookup"><span data-stu-id="bef5e-193">To choose one or more rules from a list of all translation rules that are available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="bef5e-194">在“选择转换规则”\*\*\*\* 中，单击要与中继关联的规则，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bef5e-194">In **Select Translation Rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>

    - <span data-ttu-id="bef5e-195">要定义新的转换规则并将其与中继相关联，请单击“新建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bef5e-195">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="bef5e-196">有关翻译规则的详细信息, 请参阅[Skype For Business 服务器中的翻译规则](../../plan-your-deployment/enterprise-voice-solution/translation-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="bef5e-196">For details about translation rules, see [Translation rules in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/translation-rules.md).</span></span>

    - <span data-ttu-id="bef5e-197">要编辑已与中继关联的转换规则，请单击相应的规则名称，然后单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bef5e-197">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span>

    - <span data-ttu-id="bef5e-198">要复制现有的转换规则以作为定义新规则的起点，请单击相应的规则名称，再单击“复制”\*\*\*\*，然后单击“粘贴”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bef5e-198">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span>

    - <span data-ttu-id="bef5e-199">要从中继删除某个转换规则，请突出显示相应的规则名称，然后单击“删除”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bef5e-199">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>

      > [!CAUTION]
      > <span data-ttu-id="bef5e-200">如果已在关联的中继对等方上配置了转换规则，则不要将任何转换规则与中继相关联，因为这两种规则可能会发生冲突。</span><span class="sxs-lookup"><span data-stu-id="bef5e-200">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>

16. <span data-ttu-id="bef5e-201">请确保主干的转换规则按正确的顺序排列。</span><span class="sxs-lookup"><span data-stu-id="bef5e-201">Make sure that the trunk's translation rules are arranged in the correct order.</span></span> <span data-ttu-id="bef5e-202">若要更改规则在列表中的位置, 请突出显示规则名称, 然后单击向上或向下箭头。</span><span class="sxs-lookup"><span data-stu-id="bef5e-202">To change a rule's position in the list, highlight the rule name, and then click the up or down arrow.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="bef5e-203">Skype for Business 服务器从上到下遍历翻译规则列表, 并使用与所拨号码匹配的第一个规则。</span><span class="sxs-lookup"><span data-stu-id="bef5e-203">Skype for Business Server traverses the translation rule list from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="bef5e-204">如果要配置中继以使拨打号码可以匹配多个转换规则，则确保限制较严格的规则排在限制较宽松的规则上方。</span><span class="sxs-lookup"><span data-stu-id="bef5e-204">If you configure a trunk so that a dialed number can match more than one translation rule, be sure that the more restrictive rules are sorted above the less restrictive rules.</span></span> <span data-ttu-id="bef5e-205">例如, 如果你已包括与任何11位数字匹配的翻译规则和仅匹配以 + 1425 开头的11位数字的翻译规则, 请确保与任何11位数字匹配的规则按限制性更强的顺序排列\*\* 规则.</span><span class="sxs-lookup"><span data-stu-id="bef5e-205">For example, if you have included a translation rule that matches any 11-digit number and a translation rule that matches only 11-digit numbers that start with +1425, be sure that the rule that matches any 11-digit number is sorted  *below*  the more restrictive rule.</span></span>

17. <span data-ttu-id="bef5e-206">完成中继的配置后，单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bef5e-206">When you are finished configuring the trunk, click **OK**.</span></span>

18. <span data-ttu-id="bef5e-207">在“Trunk 配置”\*\*\*\* 页上，单击“提交”\*\*\*\*，然后单击“全部提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bef5e-207">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="bef5e-208">任何时候创建或修改中继配置，都必须运行“全部提交”\*\*\*\* 命令以发布配置更改。</span><span class="sxs-lookup"><span data-stu-id="bef5e-208">Whenever you create or modify a trunk configuration, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="bef5e-209">有关详细信息, 请参阅操作文档中的[Skype For business 中的 "发布待处理的语音路由配置更改"](voice-route-config-changes.md) 。</span><span class="sxs-lookup"><span data-stu-id="bef5e-209">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="bef5e-210">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bef5e-210">See also</span></span>

[<span data-ttu-id="bef5e-211">在 Skype for Business 服务器中使用 "媒体绕过" 配置主干</span><span class="sxs-lookup"><span data-stu-id="bef5e-211">Configure a trunk with media bypass in Skype for Business Server</span></span>](configure-trunk-with-media-bypass.md)

[<span data-ttu-id="bef5e-212">定义翻译规则</span><span class="sxs-lookup"><span data-stu-id="bef5e-212">Defining Translation Rules</span></span>](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx)

