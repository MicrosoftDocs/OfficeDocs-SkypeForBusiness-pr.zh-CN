---
title: 在 Skype for Business Server 2015 中配置无媒体旁路功能的中继
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 3422e93e-7bd2-4470-968c-dc38345b18ca
description: 摘要： 没有启用为 Skype 业务服务器 2015年媒体绕过配置中继。
ms.openlocfilehash: 5e3aa618370d77d9781827dfdfe261f6ed43dd8c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="configure-a-trunk-without-media-bypass-in-skype-for-business-server-2015"></a><span data-ttu-id="9435b-103">在 Skype for Business Server 2015 中配置无媒体旁路功能的中继</span><span class="sxs-lookup"><span data-stu-id="9435b-103">Configure a trunk without media bypass in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="9435b-104">**摘要：**没有启用的 Skype 业务服务器 2015年媒体回避配置中继。</span><span class="sxs-lookup"><span data-stu-id="9435b-104">**Summary:** Configure a trunk without media bypass enabled for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="9435b-105">如果要配置禁用媒体旁路功能的中继，请执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="9435b-105">If you want to configure a trunk with media bypass disabled, follow these steps.</span></span> <span data-ttu-id="9435b-106">如果您想要启用媒体回避与配置中继，请参阅[配置介质与干线业务服务器 2015年的 Skype 在绕过](configure-trunk-with-media-bypass.md)。</span><span class="sxs-lookup"><span data-stu-id="9435b-106">If you want to configure a trunk with media bypass enabled, see [Configure a trunk with media bypass in Skype for Business Server 2015](configure-trunk-with-media-bypass.md).</span></span>
  
<span data-ttu-id="9435b-p102">如下所述，中继配置可对应用于已分配此中继配置的中继的一组参数进行分组。特定中继配置的作用域可以是全局中继（针对没有更多特定站点或池配置的所有中继）、站点或者池。池级中继配置用于将特定中继配置的作用域限制为单个中继。</span><span class="sxs-lookup"><span data-stu-id="9435b-p102">A trunk configuration, as described below, groups a set of parameters that are applied to trunks assigned this trunk configuration. A particular trunk configuration can be scoped globally (to all trunks that do not have more specific site or pool configuration), or to a site, or to a pool. The pool-level trunk configuration is used to scope a specific trunk configuration to a single trunk.</span></span>
  
### <a name="to-configure-a-trunk-without-media-bypass"></a><span data-ttu-id="9435b-110">配置无媒体旁路功能的中继</span><span class="sxs-lookup"><span data-stu-id="9435b-110">To configure a trunk without media bypass</span></span>

1. <span data-ttu-id="9435b-111">打开 Skype 业务服务器的控制面板。</span><span class="sxs-lookup"><span data-stu-id="9435b-111">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="9435b-112">在左侧导航栏中，单击“语音路由”****，然后单击“Trunk 配置”****。</span><span class="sxs-lookup"><span data-stu-id="9435b-112">In the left navigation bar, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>
    
3. <span data-ttu-id="9435b-113">在“Trunk 配置”****页上，使用以下方法之一配置中继：</span><span class="sxs-lookup"><span data-stu-id="9435b-113">On the **Trunk Configuration** page, use one of the following methods to configure a trunk:</span></span>
    
   - <span data-ttu-id="9435b-114">双击某个现有的中继（例如“全局”****中继）以显示“编辑 Trunk 配置”****对话框。</span><span class="sxs-lookup"><span data-stu-id="9435b-114">Double-click an existing trunk (for example, the **Global** trunk) to display the **Edit Trunk Configuration** dialog box.</span></span>
    
   - <span data-ttu-id="9435b-115">单击“新建”****，然后为新的中继配置选择范围：</span><span class="sxs-lookup"><span data-stu-id="9435b-115">Click **New**, and then select a scope for the new trunk configuration:</span></span>
    
   - <span data-ttu-id="9435b-116">**网站干线**： 在**选择某一站点**，请选择此中继配置的站点，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="9435b-116">**Site trunk**: Choose the site for this trunk configuration in **Select a Site**, and then click **OK**.</span></span> <span data-ttu-id="9435b-117">请注意，如果已为站点创建中继配置，则该站点不会显示在“选择站点”****中。</span><span class="sxs-lookup"><span data-stu-id="9435b-117">Note that if a trunk configuration has already been created for a site, the site does not appear in **Select a Site**.</span></span> <span data-ttu-id="9435b-118">此中继配置将应用于站点中的所有中继。</span><span class="sxs-lookup"><span data-stu-id="9435b-118">This trunk configuration will be applied to all trunks in the site.</span></span>
    
   - <span data-ttu-id="9435b-119">**池 Trunk**：在“选择服务”****中选择此中继配置应用于的中继的名称，然后单击“确定”****。</span><span class="sxs-lookup"><span data-stu-id="9435b-119">**Pool trunk**: Choose the name of the trunk that this trunk configuration applies to in **Select a Service** and click **OK**.</span></span> <span data-ttu-id="9435b-120">该干线可以根主干或任何其他中继拓扑生成器中定义。</span><span class="sxs-lookup"><span data-stu-id="9435b-120">This trunk can be the root trunk, or any additional trunks defined in Topology Builder.</span></span> <span data-ttu-id="9435b-121">请注意，如果已为特定中继创建中继配置，则此中继不会显示在“选择服务”****中。</span><span class="sxs-lookup"><span data-stu-id="9435b-121">Note that if a trunk configuration has already been created for a specific trunk, the trunk does not appear in **Select a Service**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="9435b-122">选择中继配置的范围后无法更改该范围。</span><span class="sxs-lookup"><span data-stu-id="9435b-122">After you select the scope of the trunk configuration, it cannot be changed.</span></span> <span data-ttu-id="9435b-123">>**名称**字段预先填充的中继配置关联的站点或服务的名称，并且无法更改。</span><span class="sxs-lookup"><span data-stu-id="9435b-123">> The **Name** field is pre-populated with the name of the trunk configuration's associated site or service and cannot be changed.</span></span>
  
4. <span data-ttu-id="9435b-124">选择以下“加密支持级别”****选项之一：</span><span class="sxs-lookup"><span data-stu-id="9435b-124">Select one of the following **Encryption support level** options:</span></span>
    
   - <span data-ttu-id="9435b-125">**必需**：必须使用安全实时传输协议 (SRTP) 加密以帮助保护中介服务器与网关或专用交换机 (PBX) 之间的通信。</span><span class="sxs-lookup"><span data-stu-id="9435b-125">**Required**: Secure Realtime Transport Protocol (SRTP) encryption must be used to help protect traffic between the Mediation Server and the gateway or Private Branch eXchange (PBX).</span></span>
    
   - <span data-ttu-id="9435b-126">**可选**：如果服务提供商或设备制造商支持 SRTP，则使用 SRTP 加密。</span><span class="sxs-lookup"><span data-stu-id="9435b-126">**Optional**: SRTP encryption will be used if the service provider or equipment manufacturer supports it.</span></span>
    
   - <span data-ttu-id="9435b-127">**不支持**：SRTP 加密不受服务提供商或设备制造商支持，因此不使用。</span><span class="sxs-lookup"><span data-stu-id="9435b-127">**Not Supported**: SRTP encryption is not supported by the service provider or equipment manufacturer and therefore will not be used.</span></span>
    
5.  <span data-ttu-id="9435b-128">确保已清除“启用媒体旁路”****复选框。</span><span class="sxs-lookup"><span data-stu-id="9435b-128">Be sure that the **Enable media bypass** check box is cleared.</span></span>
    
6. <span data-ttu-id="9435b-p106">如果存在一个已知的媒体端点（例如公用电话交换网 (PSTN) 网关，其中媒体终端与信号终端具有相同的 IP），则选中“集中式媒体处理”****复选框。如果中继没有已知的媒体端点，则清除该复选框。</span><span class="sxs-lookup"><span data-stu-id="9435b-p106">Select the **Centralized media processing** check box if there is a well-known media termination point (for example, a Public Switched Telephone Network (PSTN) gateway where the media termination has the same IP as the signaling termination). Clear this check box if the trunk does not have a well-known media termination point.</span></span>
    
7. <span data-ttu-id="9435b-131">如果对干线等支持接收来自中介服务器的 SIP 引用请求，选择**发送到网关，请启用**复选框。</span><span class="sxs-lookup"><span data-stu-id="9435b-131">If the trunk peer supports receiving SIP REFER requests from the Mediation Server, select the **Enable sending refer to the gateway** check box.</span></span>
    
8. <span data-ttu-id="9435b-132">（可选）若要启用中继间路由，请将 PSTN 用法记录关联到此中继配置并进行相应的配置。</span><span class="sxs-lookup"><span data-stu-id="9435b-132">(Optional) To enable inter-trunk routing, associate and configure PSTN usage records to this trunk configuration.</span></span> <span data-ttu-id="9435b-133">将所有传入呼叫不源自业务服务器终结点的 Skype 干线通过应用此中继配置相关联的 PSTN 用法。</span><span class="sxs-lookup"><span data-stu-id="9435b-133">The PSTN usages associated to this trunk configuration will be applied for all incoming calls through the trunk that is not originating from a Skype for Business Server endpoint.</span></span> <span data-ttu-id="9435b-134">若要管理与中继配置关联的 PSTN 用法记录，请使用下列方法之一：</span><span class="sxs-lookup"><span data-stu-id="9435b-134">To manage PSTN usage records associated to a trunk configuration, use one of the following methods:</span></span>
    
   - <span data-ttu-id="9435b-135">要从所有 PSTN 使用记录企业语音部署中可用的列表中选择一个或多个记录，请单击**选择**。</span><span class="sxs-lookup"><span data-stu-id="9435b-135">To select one or more records from a list of all PSTN usage records available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="9435b-136">突出显示要与此中继配置关联的记录，然后单击“确定”****。</span><span class="sxs-lookup"><span data-stu-id="9435b-136">Highlight the records you want to associate with this trunk configuration and then click **OK**.</span></span>
    
   - <span data-ttu-id="9435b-137">要删除此中继配置中的某个 PSTN 用法记录，请选择此记录，并单击“删除”****。</span><span class="sxs-lookup"><span data-stu-id="9435b-137">To remove a PSTN usage record from this trunk configuration, select the record and click **Remove**.</span></span>
    
   - <span data-ttu-id="9435b-138">要定义新的 PSTN 用法记录并将其与此中继配置相关联，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="9435b-138">To define a new PSTN usage record and associate it with this trunk configuration, do the following:</span></span>
    
     <span data-ttu-id="9435b-139">a.</span><span class="sxs-lookup"><span data-stu-id="9435b-139">a.</span></span> <span data-ttu-id="9435b-140">单击“新建”****。</span><span class="sxs-lookup"><span data-stu-id="9435b-140">Click **New**.</span></span>
    
     <span data-ttu-id="9435b-141">b.</span><span class="sxs-lookup"><span data-stu-id="9435b-141">b.</span></span> <span data-ttu-id="9435b-142">在“名称”****字段中，为记录指定唯一的描述性名称。</span><span class="sxs-lookup"><span data-stu-id="9435b-142">In the **Name** field, specify a descriptive name for the record that is unique.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="9435b-p111">PSTN 用法记录名称在企业语音部署中必须是唯一的。保存记录后，将无法编辑“名称”****字段。</span><span class="sxs-lookup"><span data-stu-id="9435b-p111">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the **Name** field cannot be edited.</span></span>
  
     <span data-ttu-id="9435b-145">c.</span><span class="sxs-lookup"><span data-stu-id="9435b-145">c.</span></span> <span data-ttu-id="9435b-146">使用下列方法之一为此 PSTN 用法记录关联和配置路由：</span><span class="sxs-lookup"><span data-stu-id="9435b-146">Use one of the following methods to associate and configure routes for this PSTN usage record:</span></span>
    
     - <span data-ttu-id="9435b-147">要从企业语音部署中的所有可用的路由列表中选择一个或多个路由，请单击**选择**。</span><span class="sxs-lookup"><span data-stu-id="9435b-147">To select one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="9435b-148">突出显示要与此 PSTN 用法记录相关联的路由，然后单击“确定”****。</span><span class="sxs-lookup"><span data-stu-id="9435b-148">Highlight the routes you want to associate with this PSTN usage record, and click **OK**.</span></span> 
    
     - <span data-ttu-id="9435b-149">要删除 PSTN 用法记录中的某个路由，请选择此路由，然后单击“删除”****。</span><span class="sxs-lookup"><span data-stu-id="9435b-149">To remove a route from the PSTN usage record, select the route, and click **Remove**.</span></span>
    
     - <span data-ttu-id="9435b-150">要定义新路由并将其与此 PSTN 用法记录相关联，请单击“新建”****。</span><span class="sxs-lookup"><span data-stu-id="9435b-150">To define a new route and associate it to this PSTN usage record, click **New**.</span></span> <span data-ttu-id="9435b-151">有关详细信息，请参阅[创建或修改在企业 2015年的 Skype 语音路由](create-or-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="9435b-151">For details, see [Create or modify a voice route in Skype for Business 2015](create-or-modify-a-voice-route.md).</span></span>
    
     - <span data-ttu-id="9435b-152">要编辑与此 PSTN 用法记录相关联的路由，请选择此路由，然后单击“显示详细信息”****。</span><span class="sxs-lookup"><span data-stu-id="9435b-152">To edit a route that is associated with this PSTN usage record, select the route, and click **Show details**.</span></span>
    
     <span data-ttu-id="9435b-153">d.</span><span class="sxs-lookup"><span data-stu-id="9435b-153">d.</span></span> <span data-ttu-id="9435b-154">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="9435b-154">Click **OK**.</span></span>
    
   - <span data-ttu-id="9435b-155">要编辑已经与此中继配置相关联的 PSTN 用法记录，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="9435b-155">To edit a PSTN usage record that is already associated with this trunk configuration, do the following:</span></span>
    
    <span data-ttu-id="9435b-156">a.</span><span class="sxs-lookup"><span data-stu-id="9435b-156">a.</span></span> <span data-ttu-id="9435b-157">选择要编辑的 PSTN 用法记录，然后单击“显示详细信息”****。</span><span class="sxs-lookup"><span data-stu-id="9435b-157">Select the PSTN usage record you want to edit, and click **Show details**.</span></span>
    
    <span data-ttu-id="9435b-158">b.</span><span class="sxs-lookup"><span data-stu-id="9435b-158">b.</span></span> <span data-ttu-id="9435b-159">使用下列方法之一为此 PSTN 用法记录关联和配置路由：</span><span class="sxs-lookup"><span data-stu-id="9435b-159">Use one of the following methods to associate and configure routes for this PSTN usage record:</span></span>
    
     - <span data-ttu-id="9435b-160">要从企业语音部署中的所有可用的路由列表中选择一个或多个路由，请单击**选择**。</span><span class="sxs-lookup"><span data-stu-id="9435b-160">To select one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="9435b-161">突出显示要与此 PSTN 用法记录相关联的路由，然后单击“确定”****。</span><span class="sxs-lookup"><span data-stu-id="9435b-161">Highlight the routes you want to associate with this PSTN usage record, and click **OK**.</span></span> 
    
     - <span data-ttu-id="9435b-162">要删除 PSTN 用法记录中的某个路由，请选择此路由，然后单击“删除”****。</span><span class="sxs-lookup"><span data-stu-id="9435b-162">To remove a route from the PSTN usage record, select the route, and click **Remove**.</span></span>
    
     - <span data-ttu-id="9435b-163">要定义新路由并将其与此 PSTN 用法记录相关联，请单击“新建”****。</span><span class="sxs-lookup"><span data-stu-id="9435b-163">To define a new route and associate it to this PSTN usage record, click **New**.</span></span> <span data-ttu-id="9435b-164">有关详细信息，请参阅[创建或修改在企业 2015年的 Skype 语音路由](create-or-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="9435b-164">For details, see [Create or modify a voice route in Skype for Business 2015](create-or-modify-a-voice-route.md).</span></span>
    
     - <span data-ttu-id="9435b-165">要编辑与此 PSTN 用法记录相关联的路由，请选择此路由，然后单击“显示详细信息”****。</span><span class="sxs-lookup"><span data-stu-id="9435b-165">To edit a route that is associated with this PSTN usage record, select the route, and click **Show details**.</span></span>
    
    <span data-ttu-id="9435b-166">c.</span><span class="sxs-lookup"><span data-stu-id="9435b-166">c.</span></span> <span data-ttu-id="9435b-167">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="9435b-167">Click **OK**.</span></span>
    
     > [!IMPORTANT]
     > <span data-ttu-id="9435b-168">请务必将根据关联到配置主干的中介服务器对等方的 PSTN 使用记录相关联。</span><span class="sxs-lookup"><span data-stu-id="9435b-168">It is important to associate PSTN usage records according to the Mediation Server peer that is associated to the trunk being configured.</span></span> <span data-ttu-id="9435b-169">如果中介服务器等，PSTN 网关或会话边框控制器 (SBC) 强烈建议中继配置不是通过 Skype 连接到 PSTN 目的或任何其他下游系统路由的 PSTN 使用记录相关联对于业务服务器。</span><span class="sxs-lookup"><span data-stu-id="9435b-169">If the Mediation Server peer is a PSTN gateway or a Session Border Controller (SBC), it is strongly recommended that the trunk configuration is not associated to a PSTN usage record that routes to a PSTN destination or any other downstream systems connected via Skype for Business Server.</span></span> 
  
9. <span data-ttu-id="9435b-170">排列 PSTN 用法记录以获得最佳性能。</span><span class="sxs-lookup"><span data-stu-id="9435b-170">Arrange the PSTN usage records for optimum performance.</span></span> <span data-ttu-id="9435b-171">若要更改列表中的记录的位置，选择 PSTN 使用记录，并单击向上或向下箭头。</span><span class="sxs-lookup"><span data-stu-id="9435b-171">To change a record's position in the list, select the PSTN usage record, and click the up or down arrows.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="9435b-172">PSTN 用法记录在中继配置中列出的顺序很重要。</span><span class="sxs-lookup"><span data-stu-id="9435b-172">The order in which PSTN usage records are listed in the trunk configuration is significant.</span></span> <span data-ttu-id="9435b-173">Skype 业务服务器从上到下遍历该列表。</span><span class="sxs-lookup"><span data-stu-id="9435b-173">Skype for Business Server traverses the list from top to down.</span></span> 
  
10. <span data-ttu-id="9435b-174">应选择“启用 RTP 闭锁”****，以便为 NAT 或防火墙之后的客户端以及支持闭锁的 SBC 启用媒体旁路。</span><span class="sxs-lookup"><span data-stu-id="9435b-174">**Enable RTP Latching** should be selected to enable bypass media for clients behind a NAT or firewall and an SBC that supports latching.</span></span>
    
11. <span data-ttu-id="9435b-175">**启用正向通话历史记录**应选择以启用的通话记录信息发送到中介服务器的网关等。</span><span class="sxs-lookup"><span data-stu-id="9435b-175">**Enable forward call history** should be selected to enable sending of call history information to the gateway peer of the Mediation Server.</span></span>
    
12. <span data-ttu-id="9435b-176">**启用正向 P 断言标识数据**应选择以启用 PAI 调用原始发件人信息中介服务器端和网关端之间转发 （反之亦然），当存在。</span><span class="sxs-lookup"><span data-stu-id="9435b-176">**Enable forward P-Asserted-Identity data** should be selected to enable PAI call originator information to be forwarded between the Mediation Server side and gateway side (and vice versa), when present.</span></span>
    
13. <span data-ttu-id="9435b-177">应选择“启用出站路由故障转移计时器”****以启用快速故障转移。</span><span class="sxs-lookup"><span data-stu-id="9435b-177">**Enable outbound routing failover timer** should be selected to enable fast failover.</span></span> <span data-ttu-id="9435b-178">与此中继关联的网关会在 10 秒内发送通知，告知正在处理出站呼叫。</span><span class="sxs-lookup"><span data-stu-id="9435b-178">The gateway associated with this trunk can give notification within 10 seconds that it is processing an outbound call.</span></span> <span data-ttu-id="9435b-179">如果由中介服务器不接收此通知，重新路由到其他干线将发生。</span><span class="sxs-lookup"><span data-stu-id="9435b-179">Rerouting to another trunk will occur if this notification is not received by the Mediation Server.</span></span> <span data-ttu-id="9435b-180">在延迟可能推迟响应时间或网关需要花费 10 秒以上的时间才能响应，应禁用快速故障转移。</span><span class="sxs-lookup"><span data-stu-id="9435b-180">On networks where latency may delay the response time or the gateway takes longer than 10 seconds to respond, the fast failover should be disabled.</span></span>
    
14. <span data-ttu-id="9435b-p125">（可选）为中继关联和配置“主叫号码转换规则”****。这些转换规则适用于出站呼叫的主叫号码</span><span class="sxs-lookup"><span data-stu-id="9435b-p125">(Optional) Associate and configure **calling number translation rules** for the trunk. These translation rules apply to the calling number for outbound calls</span></span>
    
   - <span data-ttu-id="9435b-183">要从可用企业语音部署中的所有翻译规则列表中选择一个或多个规则，请单击**选择**。</span><span class="sxs-lookup"><span data-stu-id="9435b-183">To choose one or more rules from a list of all translation rules that are available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="9435b-184">在“选择转换规则”****中，单击要与中继关联的规则，然后单击“确定”****。</span><span class="sxs-lookup"><span data-stu-id="9435b-184">In **Select Translation Rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>
    
   - <span data-ttu-id="9435b-185">要定义新的转换规则并将其与中继相关联，请单击“新建”****。</span><span class="sxs-lookup"><span data-stu-id="9435b-185">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="9435b-186">转换规则的详细信息，请参阅[在业务服务器 2015年的 Skype 的转换规则](../../plan-your-deployment/enterprise-voice-solution/translation-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="9435b-186">For details about translation rules, see [Translation rules in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/translation-rules.md).</span></span>
    
   - <span data-ttu-id="9435b-187">要编辑已与中继关联的转换规则，请单击相应的规则名称，然后单击“显示详细信息”****。</span><span class="sxs-lookup"><span data-stu-id="9435b-187">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span> 
    
   - <span data-ttu-id="9435b-188">要复制现有的转换规则以作为定义新规则的起点，请单击相应的规则名称，再单击“复制”****，然后单击“粘贴”****。</span><span class="sxs-lookup"><span data-stu-id="9435b-188">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span> 
    
   - <span data-ttu-id="9435b-189">要从中继删除某个转换规则，请突出显示相应的规则名称，然后单击“删除”****。</span><span class="sxs-lookup"><span data-stu-id="9435b-189">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>
    
     > [!CAUTION]
     > <span data-ttu-id="9435b-190">如果已在关联的中继对等方上配置了转换规则，则不要将任何转换规则与中继相关联，因为这两种规则可能会发生冲突。</span><span class="sxs-lookup"><span data-stu-id="9435b-190">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span> 
  
15. <span data-ttu-id="9435b-p128">（可选）为中继关联和配置“被叫号码转换规则”****。这些转换规则适用于出站呼叫的被叫号码。</span><span class="sxs-lookup"><span data-stu-id="9435b-p128">(Optional) Associate and configure **called number translation rules** for the trunk. The translation rules apply to the called number in an outbound call.</span></span>
    
   - <span data-ttu-id="9435b-193">要从可用企业语音部署中的所有翻译规则列表中选择一个或多个规则，请单击**选择**。</span><span class="sxs-lookup"><span data-stu-id="9435b-193">To choose one or more rules from a list of all translation rules that are available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="9435b-194">在“选择转换规则”****中，单击要与中继关联的规则，然后单击“确定”****。</span><span class="sxs-lookup"><span data-stu-id="9435b-194">In **Select Translation Rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>
    
  - <span data-ttu-id="9435b-195">要定义新的转换规则并将其与中继相关联，请单击“新建”****。</span><span class="sxs-lookup"><span data-stu-id="9435b-195">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="9435b-196">转换规则的详细信息，请参阅[在业务服务器 2015年的 Skype 的转换规则](../../plan-your-deployment/enterprise-voice-solution/translation-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="9435b-196">For details about translation rules, see [Translation rules in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/translation-rules.md).</span></span>
    
   - <span data-ttu-id="9435b-197">要编辑已与中继关联的转换规则，请单击相应的规则名称，然后单击“显示详细信息”****。</span><span class="sxs-lookup"><span data-stu-id="9435b-197">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span> 
    
   - <span data-ttu-id="9435b-198">要复制现有的转换规则以作为定义新规则的起点，请单击相应的规则名称，再单击“复制”****，然后单击“粘贴”****。</span><span class="sxs-lookup"><span data-stu-id="9435b-198">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span> 
    
   - <span data-ttu-id="9435b-199">要从中继删除某个转换规则，请突出显示相应的规则名称，然后单击“删除”****。</span><span class="sxs-lookup"><span data-stu-id="9435b-199">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>
    
     > [!CAUTION]
     > <span data-ttu-id="9435b-200">如果已在关联的中继对等方上配置了转换规则，则不要将任何转换规则与中继相关联，因为这两种规则可能会发生冲突。</span><span class="sxs-lookup"><span data-stu-id="9435b-200">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span> 
  
16. <span data-ttu-id="9435b-201">请确保干线的转换规则，按正确的顺序排列。</span><span class="sxs-lookup"><span data-stu-id="9435b-201">Make sure that the trunk's translation rules are arranged in the correct order.</span></span> <span data-ttu-id="9435b-202">要更改列表中规则的位置，请突出显示该规则名称，然后单击向上或向下箭头。</span><span class="sxs-lookup"><span data-stu-id="9435b-202">To change a rule's position in the list, highlight the rule name, and then click the up or down arrow.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="9435b-203">Skype 业务服务器向下遍历从顶部的翻译规则列表，并使用与拨叫的号码相匹配的第一个规则。</span><span class="sxs-lookup"><span data-stu-id="9435b-203">Skype for Business Server traverses the translation rule list from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="9435b-204">如果要配置中继以使拨打号码可以匹配多个转换规则，则确保限制较严格的规则排在限制较宽松的规则上方。</span><span class="sxs-lookup"><span data-stu-id="9435b-204">If you configure a trunk so that a dialed number can match more than one translation rule, be sure that the more restrictive rules are sorted above the less restrictive rules.</span></span> <span data-ttu-id="9435b-205">例如，如果包含了匹配任何 11 位数字的翻译规则和转换规则相匹配以 +1425 开头的 11 位号码，请确保匹配任何 11 位数字的规则排序*下面*更严格规则。</span><span class="sxs-lookup"><span data-stu-id="9435b-205">For example, if you have included a translation rule that matches any 11-digit number and a translation rule that matches only 11-digit numbers that start with +1425, be sure that the rule that matches any 11-digit number is sorted  *below*  the more restrictive rule.</span></span>
  
17. <span data-ttu-id="9435b-206">完成中继的配置后，单击“确定”****。</span><span class="sxs-lookup"><span data-stu-id="9435b-206">When you are finished configuring the trunk, click **OK**.</span></span>
    
18. <span data-ttu-id="9435b-207">在“Trunk 配置”****页上，单击“提交”****，然后单击“全部提交”****。</span><span class="sxs-lookup"><span data-stu-id="9435b-207">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="9435b-208">任何时候创建或修改中继配置，都必须运行“全部提交”****命令以发布配置更改。</span><span class="sxs-lookup"><span data-stu-id="9435b-208">Whenever you create or modify a trunk configuration, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="9435b-209">有关详细信息，请参阅[挂起更改的业务 2015年的 Skype 语音路由配置发布](voice-route-config-changes.md)操作文档。</span><span class="sxs-lookup"><span data-stu-id="9435b-209">For details, see [Publish pending changes to the voice routing configuration in Skype for Business 2015](voice-route-config-changes.md) in the Operations documentation.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9435b-210">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9435b-210">See also</span></span>

#### 

[<span data-ttu-id="9435b-211">配置中继与媒体回避在 Skype 业务服务器 2015</span><span class="sxs-lookup"><span data-stu-id="9435b-211">Configure a trunk with media bypass in Skype for Business Server 2015</span></span>](configure-trunk-with-media-bypass.md)
#### 

[<span data-ttu-id="9435b-212">定义转换规则</span><span class="sxs-lookup"><span data-stu-id="9435b-212">Defining Translation Rules</span></span>](http://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx)

