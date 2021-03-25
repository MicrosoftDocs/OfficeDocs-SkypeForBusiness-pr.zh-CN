---
title: 在 Skype for Business Server 中配置带媒体旁路的中继
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
ms.assetid: 99d729ea-5a4c-4ff2-a4a3-93a24368da6d
description: 摘要：为 Skype for Business Server 配置启用了媒体旁路功能的中继。 这将可以最大程度地减少中介服务器的数量，假设 SIP 中继提供商支持中介服务器的数量。
ms.openlocfilehash: 12f9abc49830e0af9c1934f4da56fe29be861114
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51106388"
---
# <a name="configure-a-trunk-with-media-bypass-in-skype-for-business-server"></a><span data-ttu-id="6f4a2-104">在 Skype for Business Server 中配置带媒体旁路的中继</span><span class="sxs-lookup"><span data-stu-id="6f4a2-104">Configure a trunk with media bypass in Skype for Business Server</span></span>

<span data-ttu-id="6f4a2-105">**摘要：** 为 Skype for Business Server 配置启用了媒体旁路功能的中继。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-105">**Summary:** Configure a trunk with media bypass enabled for Skype for Business Server.</span></span> <span data-ttu-id="6f4a2-106">这将可以最大程度地减少中介服务器的数量，假设 SIP 中继提供商支持中介服务器的数量。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-106">This will let you minimize the number of Mediation Servers, presuming your SIP trunk provider supports it.</span></span>

<span data-ttu-id="6f4a2-107">按照以下步骤配置启用了媒体旁路功能的中继。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-107">Follow these steps to configure a trunk with media bypass enabled.</span></span> <span data-ttu-id="6f4a2-108">若要配置禁用媒体旁路的中继，请参阅在 Skype for Business Server 中配置没有媒体旁路 [的中继](configure-trunk-without-media-bypass.md)。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-108">To configure a trunk with media bypass disabled, see [Configure a trunk without media bypass in Skype for Business Server](configure-trunk-without-media-bypass.md).</span></span>

<span data-ttu-id="6f4a2-109">如果希望将部署的中介服务器数目降至最低，媒体绕过非常有用。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-109">Media bypass is useful when you want to minimize the number of Mediation Servers deployed.</span></span> <span data-ttu-id="6f4a2-110">有关详细信息，请参阅在 [Skype for Business 中规划媒体旁路](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)</span><span class="sxs-lookup"><span data-stu-id="6f4a2-110">For more information, see [Plan for media bypass in Skype for Business](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)</span></span>

<span data-ttu-id="6f4a2-111">我们强烈建议您启用媒体旁路。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-111">We strongly recommend that you enable media bypass.</span></span> <span data-ttu-id="6f4a2-112">但是，在 SIP 中继上启用媒体旁路之前，请确认您的合格 SIP 中继提供商支持媒体旁路，并能够满足成功启用方案的要求。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-112">However, before you enable media bypass on a SIP trunk, confirm that your qualified SIP trunk provider supports media bypass and is able to accommodate the requirements for successfully enabling the scenario.</span></span> <span data-ttu-id="6f4a2-113">具体而言，提供商必须具有组织内部网络中服务器的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-113">Specifically, the provider must have the IP addresses of servers in your organization's internal network.</span></span>

> [!NOTE]
> <span data-ttu-id="6f4a2-114">媒体旁路将不会与 SBC (每个公用电话交换网) IP-PBX 和会话边界控制器 (交互) 。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-114">Media bypass will not interoperate with every Public Switched Telephone Network (PSTN) gateway, IP-PBX, and Session Border Controller (SBC).</span></span> <span data-ttu-id="6f4a2-115">Microsoft 已与认证合作伙伴一起测试了一组 PSTN 网关和 SDC。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-115">Microsoft has tested a set of PSTN gateways and SBCs with certified partners.</span></span> <span data-ttu-id="6f4a2-116">媒体旁路仅支持 Skype [for Business Server](../../../SfbPartnerCertification/certification/infra-gateways.md) 电话基础结构页上列出的产品和版本。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-116">Media bypass is supported only with products and versions that are listed on the [Telephony Infrastructure for Skype for Business Server](../../../SfbPartnerCertification/certification/infra-gateways.md) page.</span></span>

<span data-ttu-id="6f4a2-117">如下所述中继配置对应用于分配了此中继配置的中继的一组参数进行分组。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-117">A trunk configuration as described below groups a set of parameters that are applied to trunks assigned this trunk configuration.</span></span> <span data-ttu-id="6f4a2-118">特定中继配置的作用域可以是全局中继（针对没有更多特定站点或池配置的所有中继）、站点或者池。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-118">A particular trunk configuration can be scoped globally (to all trunks that do not have more specific site or pool configuration), or to a site, or to a pool.</span></span> <span data-ttu-id="6f4a2-119">池级中继配置用于将特定中继配置的作用域限制为单个中继。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-119">The pool-level trunk configuration is used to scope a specific trunk configuration to a single trunk.</span></span>

### <a name="to-configure-a-trunk-with-media-bypass"></a><span data-ttu-id="6f4a2-120">配置带媒体旁路的中继</span><span class="sxs-lookup"><span data-stu-id="6f4a2-120">To configure a trunk with media bypass</span></span>

1. <span data-ttu-id="6f4a2-121">打开 Skype for Business Server 控制面板</span><span class="sxs-lookup"><span data-stu-id="6f4a2-121">Open Skype for Business Server Control Panel</span></span>

2. <span data-ttu-id="6f4a2-122">在左侧导航栏中，单击“语音路由”，然后单击“Trunk 配置”。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-122">In the left navigation bar, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

3. <span data-ttu-id="6f4a2-123">在“Trunk 配置”页上，使用以下方法之一配置中继：</span><span class="sxs-lookup"><span data-stu-id="6f4a2-123">On the **Trunk Configuration** page, use one of the following methods to configure a trunk:</span></span>

   - <span data-ttu-id="6f4a2-124">双击某个现有的中继（例如“全局”中继）以显示“编辑 Trunk 配置”对话框。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-124">Double-click an existing trunk (for example, the **Global** trunk) to display the **Edit Trunk Configuration** dialog box.</span></span>

   - <span data-ttu-id="6f4a2-125">单击“新建”，然后为新的中继配置选择作用域：</span><span class="sxs-lookup"><span data-stu-id="6f4a2-125">Click **New**, and then select a scope for the new trunk configuration:</span></span>

   - <span data-ttu-id="6f4a2-126">**站点中继**：从"选择站点"中选择此中继 **配置的** 站点，然后单击"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="6f4a2-126">**Site trunk**: Choose the site for this trunk configuration from **Select a Site**, and then click **OK**.</span></span> <span data-ttu-id="6f4a2-127">请注意，如果已经为站点创建了中继配置，则该站点不会显示在“选择站点”中。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-127">Note that if a trunk configuration has already been created for a site, the site does not appear in **Select a Site**.</span></span> <span data-ttu-id="6f4a2-128">此中继配置将应用于站点中的所有中继。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-128">This trunk configuration will be applied to all trunks in the site.</span></span>

   - <span data-ttu-id="6f4a2-129">**池中继**：选择应用此中继配置的中继的名称。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-129">**Pool trunk**: Choose the name of the trunk that this trunk configuration applies to.</span></span> <span data-ttu-id="6f4a2-130">此中继可以是根中继或在拓扑生成器中定义的任何附加中继。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-130">This trunk can be the root trunk or any additional trunks defined in Topology Builder.</span></span> <span data-ttu-id="6f4a2-131">从 **"选择服务"中，** 单击"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="6f4a2-131">From **Select a Service**, click **OK**.</span></span> <span data-ttu-id="6f4a2-132">请注意，如果已经为特定中继创建了中继配置，则该中继不会显示在“选择服务”中。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-132">Note that if a trunk configuration has already been created for a specific trunk, the trunk does not appear in **Select a Service**.</span></span>

      > [!NOTE]
      > <span data-ttu-id="6f4a2-133">选择中继配置的作用域后，无法对其进行更改。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-133">After you select the scope of the trunk configuration, it cannot be changed.</span></span> <span data-ttu-id="6f4a2-134">>" **名称** "字段会使用中继配置的关联站点或服务的名称预先填充，并且无法更改。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-134">> The **Name** field is prepopulated with the name of the trunk configuration's associated site or service and cannot be changed.</span></span>

4. <span data-ttu-id="6f4a2-135">在"支持的最大 **早期对话数"中指定值**。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-135">Specify a value in **Maximum early dialogs supported**.</span></span> <span data-ttu-id="6f4a2-136">这是公用电话交换网 (PSTN) 网关、IP-PBX 或 ITSP 会话边界控制器 (SBC) 可以接收的分叉响应的最大数目，这些响应发送到中介服务器。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-136">This is the maximum number of forked responses a public switched telephone network (PSTN) gateway, IP-PBX, or ITSP Session Border Controller (SBC) can receive to an INVITE that it sent to the Mediation Server.</span></span> <span data-ttu-id="6f4a2-137">默认值为 20。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-137">The default value is 20.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6f4a2-138">在更改此值之前，请咨询您的服务提供商或设备制造商，以了解有关所用系统功能的详细信息。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-138">Before you change this value, consult your service provider or equipment manufacturer for details about the capabilities of your system.</span></span>

5. <span data-ttu-id="6f4a2-139">选择以下“加密支持级别”选项之一：</span><span class="sxs-lookup"><span data-stu-id="6f4a2-139">Select one of the following **Encryption support level** options:</span></span>

   - <span data-ttu-id="6f4a2-140">**必需**：必须使用安全实时传输协议 (SRTP) 加密以帮助保护中介服务器与网关或专用交换机 (PBX) 之间的通信。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-140">**Required**: Secure real-time transport protocol (SRTP) encryption must be used to help protect traffic between the Mediation Server and the gateway or private branch exchange (PBX).</span></span>

   - <span data-ttu-id="6f4a2-141">**可选**：如果服务提供商或设备制造商支持 SRTP，则使用 SRTP 加密。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-141">**Optional**: SRTP encryption will be used if the service provider or equipment manufacturer supports it.</span></span>

   - <span data-ttu-id="6f4a2-142">**不支持**：SRTP 加密不受服务提供商或设备制造商支持，因此不使用。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-142">**Not Supported**: SRTP encryption is not supported by the service provider or equipment manufacturer and therefore will not be used.</span></span>

6. <span data-ttu-id="6f4a2-143">如果您要绕过中介服务器而通过中继对等方处理媒体，请选中 **“启用媒体绕过”** 复选框。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-143">Select the **Enable media bypass** check box if you want media to bypass the Mediation Server for processing by the trunk peer.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="6f4a2-144">为使媒体绕过功能成功发挥作用，PSTN 网关、IP-PBX 或 ITSP 会话边界控制器必须支持某些功能。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-144">For media bypass to work successfully, the PSTN gateway, IP-PBX, or ITSP Session Border Controller must support certain capabilities.</span></span> <span data-ttu-id="6f4a2-145">有关详细信息，请参阅 [在 Skype for Business 中规划媒体旁路](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-145">For details, see [Plan for media bypass in Skype for Business](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span></span>

7. <span data-ttu-id="6f4a2-p113">如果存在一个已知的媒体端点（例如 PSTN 网关，其中媒体终端与信号终端具有相同的 IP），则选中 **“集中媒体处理”** 复选框。如果中继没有已知的媒体端点，则清除该复选框。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-p113">Select the **Centralized media processing** check box if there is a well-known media termination point (for example, a PSTN gateway where the media termination has the same IP as the signaling termination). Clear this check box if the trunk does not have a well-known media termination point.</span></span>

8. <span data-ttu-id="6f4a2-148">如果中继对等方支持接收来自中介服务器的 SIP REFER 请求，请选中" **允许向** 网关发送参考"复选框。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-148">If the trunk peer supports receiving SIP REFER requests from the Mediation Server, select the **Enable sending refer to the gateway** check box.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6f4a2-149">如果禁用此选项而选中 **“启用媒体绕过”** 选项，则需要其他设置。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-149">If you disable this option while the **Enable media bypass** option is selected, additional settings are required.</span></span> <span data-ttu-id="6f4a2-150">如果中继对等方不支持接收来自中介服务器的 SIP REFER 请求且启用了媒体绕过，则为了支持媒体绕过的适当条件，还必须运行 **Set-CsTrunkConfiguration** cmdlet 以禁用活动呼叫和保留呼叫的 RTCP。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-150">If the trunk peer does not support receiving SIP REFER requests from the Mediation Server and media bypass is enabled, you must also run the **Set-CsTrunkConfiguration** cmdlet to disable RTCP for active and held calls in order to support proper conditions for media bypass.</span></span> <span data-ttu-id="6f4a2-151">或者，如果要使转接的呼叫绕过媒体，并且网关不支持 SIP REFER 请求，可以选择"使用第三方 **呼叫** 控制启用参考"。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-151">Alternatively, you can select **Enable refer using third-party-call control** if you want transferred calls to be media bypassed, and the gateway does not support SIP REFER requests.</span></span>

9. <span data-ttu-id="6f4a2-152">（可选）若要启用中继间路由，请对此中继配置关联和配置 PSTN 用法记录。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-152">(Optional) To enable inter-trunk routing, associate and configure PSTN usage records to this trunk configuration.</span></span> <span data-ttu-id="6f4a2-153">与此中继配置关联的 PSTN 用法将应用于通过并非源自 Skype for Business Server 终结点的中继的所有传入呼叫。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-153">The PSTN usages associated to this trunk configuration will be applied for all incoming calls through the trunk that is not originating from a Skype for Business Server endpoint.</span></span> <span data-ttu-id="6f4a2-154">若要管理与中继配置关联的 PSTN 用法记录，请使用以下方法之一：</span><span class="sxs-lookup"><span data-stu-id="6f4a2-154">To manage PSTN usage records associated to a trunk configuration, use one of the following methods:</span></span>

   - <span data-ttu-id="6f4a2-155">若要从部署中提供的所有 PSTN 用法记录列表中选择一个或多个企业语音，请单击"选择 **"。**</span><span class="sxs-lookup"><span data-stu-id="6f4a2-155">To select one or more records from a list of all PSTN usage records available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="6f4a2-156">突出显示要与此中继配置关联的记录，然后单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-156">Highlight the records you want to associate with this trunk configuration and then click **OK**.</span></span>

   - <span data-ttu-id="6f4a2-157">要删除此中继配置中的某个 PSTN 用法记录，请选择相应的记录，然后单击“删除”。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-157">To remove a PSTN usage record from this trunk configuration, select the record and click **Remove**.</span></span>

   - <span data-ttu-id="6f4a2-158">要定义新的 PSTN 用法记录并将其与此中继配置相关联，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="6f4a2-158">To define a new PSTN usage record and associate it with this trunk configuration, do the following:</span></span>

     <span data-ttu-id="6f4a2-159">a.</span><span class="sxs-lookup"><span data-stu-id="6f4a2-159">a.</span></span> <span data-ttu-id="6f4a2-160">单击"新建"。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-160">Click **New**.</span></span>

     <span data-ttu-id="6f4a2-161">b.</span><span class="sxs-lookup"><span data-stu-id="6f4a2-161">b.</span></span> <span data-ttu-id="6f4a2-162">在“名称”字段中，指定记录的唯一描述性名称。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-162">In the **Name** field, specify a descriptive name for the record that is unique.</span></span>

     > [!NOTE]
     > <span data-ttu-id="6f4a2-p119">PSTN 用法记录名称在企业语音部署中必须是唯一的。保存记录后，将无法编辑“名称”字段。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-p119">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the **Name** field cannot be edited.</span></span>

     <span data-ttu-id="6f4a2-165">c.</span><span class="sxs-lookup"><span data-stu-id="6f4a2-165">c.</span></span> <span data-ttu-id="6f4a2-166">使用以下方法之一为此 PSTN 用法记录关联和配置路由：</span><span class="sxs-lookup"><span data-stu-id="6f4a2-166">Use one of the following methods to associate and configure routes for this PSTN usage record:</span></span>

     - <span data-ttu-id="6f4a2-167">若要从部署中所有可用路由列表中选择一个或多个路由企业语音，请单击"选择 **"。**</span><span class="sxs-lookup"><span data-stu-id="6f4a2-167">To select one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="6f4a2-168">突出显示要与此 PSTN 用法记录相关联的路由，然后单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-168">Highlight the routes you want to associate with this PSTN usage record, and click **OK**.</span></span>

     - <span data-ttu-id="6f4a2-169">要删除 PSTN 用法记录中的某个路由，请选择相应的路由，然后单击“删除”。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-169">To remove a route from the PSTN usage record, select the route, and click **Remove**.</span></span>

   - <span data-ttu-id="6f4a2-170">要定义新路由并将其与此 PSTN 用法记录相关联，请单击“新建”。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-170">To define a new route and associate it to this PSTN usage record, click **New**.</span></span> <span data-ttu-id="6f4a2-171">有关详细信息，请参阅在 Skype for Business 中创建或修改 [语音路由](create-or-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-171">For details, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span>

     - <span data-ttu-id="6f4a2-172">要编辑与此 PSTN 用法记录相关联的路由，请选择相应的路由，然后单击“显示详细信息”。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-172">To edit a route that is associated with this PSTN usage record, select the route, and click **Show details**.</span></span>

     <span data-ttu-id="6f4a2-173">d.</span><span class="sxs-lookup"><span data-stu-id="6f4a2-173">d.</span></span> <span data-ttu-id="6f4a2-174">单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-174">Click **OK**.</span></span>

     - <span data-ttu-id="6f4a2-175">要编辑已经与此中继配置相关联的 PSTN 用法记录，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="6f4a2-175">To edit a PSTN usage record that is already associated with this trunk configuration, do the following:</span></span>

       <span data-ttu-id="6f4a2-176">a.</span><span class="sxs-lookup"><span data-stu-id="6f4a2-176">a.</span></span> <span data-ttu-id="6f4a2-177">选择要编辑的 PSTN 用法记录，然后单击“显示详细信息”。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-177">Select the PSTN usage record you want to edit, and click **Show details**.</span></span>

       <span data-ttu-id="6f4a2-178">b.</span><span class="sxs-lookup"><span data-stu-id="6f4a2-178">b.</span></span> <span data-ttu-id="6f4a2-179">使用以下方法之一为此 PSTN 用法记录关联和配置路由：</span><span class="sxs-lookup"><span data-stu-id="6f4a2-179">Use one of the following methods to associate and configure routes for this PSTN usage record:</span></span>

   - <span data-ttu-id="6f4a2-180">若要从部署中所有可用路由列表中选择一个或多个路由企业语音，请单击"选择 **"。**</span><span class="sxs-lookup"><span data-stu-id="6f4a2-180">To select one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="6f4a2-181">突出显示要与此 PSTN 用法记录相关联的路由，然后单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-181">Highlight the routes you want to associate with this PSTN usage record, and click **OK**.</span></span>

   - <span data-ttu-id="6f4a2-182">要删除 PSTN 用法记录中的某个路由，请选择相应的路由，然后单击“删除”。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-182">To remove a route from the PSTN usage record, select the route, and click **Remove**.</span></span>

   - <span data-ttu-id="6f4a2-183">要定义新路由并将其与此 PSTN 用法记录相关联，请单击“新建”。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-183">To define a new route and associate it to this PSTN usage record, click **New**.</span></span> <span data-ttu-id="6f4a2-184">有关详细信息，请参阅在 Skype for Business 中创建或修改 [语音路由](create-or-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-184">For details, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span>

   - <span data-ttu-id="6f4a2-185">要编辑与此 PSTN 用法记录相关联的路由，请选择相应的路由，然后单击“显示详细信息”。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-185">To edit a route that is associated with this PSTN usage record, select the route, and click **Show details**.</span></span>

     <span data-ttu-id="6f4a2-186">c.</span><span class="sxs-lookup"><span data-stu-id="6f4a2-186">c.</span></span> <span data-ttu-id="6f4a2-187">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-187">Click **OK**.</span></span>

     > [!IMPORTANT]
     > <span data-ttu-id="6f4a2-188">根据与要配置的中继关联的中介服务器对等方关联 PSTN 用法记录非常重要。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-188">It is important to associate PSTN usage records according to the Mediation Server peer that is associated to the trunk being configured.</span></span> <span data-ttu-id="6f4a2-189">如果中介服务器对等方是 PSTN 网关或会话边界控制器 (SBC) ，则强烈建议不要将中继配置与路由到 PSTN 目标或通过 Skype for Business Server 连接的其他下游系统的 PSTN 用法记录关联。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-189">If the Mediation Server peer is a PSTN gateway or a Session Border Controller (SBC), it is strongly recommended that the trunk configuration is not associated to a PSTN usage record that routes to a PSTN destination or any other downstream systems connected via Skype for Business Server.</span></span>

10. <span data-ttu-id="6f4a2-190">排列 PSTN 用法记录以获得最佳性能。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-190">Arrange the PSTN usage records for optimum performance.</span></span> <span data-ttu-id="6f4a2-191">若要更改记录在列表中的位置，请选择 PSTN 用法记录，然后单击向上或向下箭头。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-191">To change a record's position in the list, select the PSTN usage record, and click the up or down arrows.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="6f4a2-192">PSTN 用法记录在中继配置中的列出顺序十分重要。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-192">The order in which PSTN usage records are listed in the trunk configuration is significant.</span></span> <span data-ttu-id="6f4a2-193">Skype for Business Server 从上到下遍历该列表。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-193">Skype for Business Server traverses the list from top to down.</span></span>

11. <span data-ttu-id="6f4a2-194">**应选择"启用 RTP** 闭锁"，为网络地址转换 (NAT) 防火墙和支持闭锁的 SBC 后面的客户端启用旁路媒体。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-194">**Enable RTP Latching** should be selected to enable bypass media for clients behind a network address translation (NAT) or firewall and an SBC that supports latching.</span></span>

12. <span data-ttu-id="6f4a2-195">**应选择"** 启用前向呼叫历史记录"以允许将呼叫历史记录信息发送到中介服务器的对等网关。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-195">**Enable forward call history** should be selected to enable sending of call history information to the gateway peer of the Mediation Server.</span></span>

13. <span data-ttu-id="6f4a2-196">应选择"启用转发 **P-Asserted-Identity"** 数据，以使 P-Asserted-Identity (PAI) 呼叫发起方信息可以在中介服务器端和网关端 (之间转发，反之亦然) （存在）。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-196">**Enable forward P-Asserted-Identity data** should be selected to enable the P-Asserted-Identity (PAI) call originator information to be forwarded between the Mediation Server side and gateway side (and vice versa), when present.</span></span>

14. <span data-ttu-id="6f4a2-197">应选择“启用出站路由故障转移计时器”以支持快速故障转移。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-197">**Enable outbound routing failover timer** should be selected to enable fast failover.</span></span> <span data-ttu-id="6f4a2-198">与此中继关联的网关可以在 10 秒内发出正在处理出站呼叫的通知。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-198">The gateway associated with this trunk can give notification within 10 seconds that it is processing an outbound call.</span></span> <span data-ttu-id="6f4a2-199">如果中介服务器未收到此通知，将重新路由到另一个中继。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-199">Rerouting to another trunk will occur if this notification is not received by the Mediation Server.</span></span> <span data-ttu-id="6f4a2-200">在延迟设置可能延迟响应时间或网关需要 10 秒以上时间进行响应的网络中，应禁用快速故障转移。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-200">On networks where latency may delay the response time or the gateway takes longer than 10 seconds to respond, the fast failover should be disabled.</span></span>

15. <span data-ttu-id="6f4a2-201">（可选）关联和配置中继的“呼叫号码转换规则”。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-201">(Optional) Associate and configure **calling number translation rules** for the trunk.</span></span> <span data-ttu-id="6f4a2-202">这些转换规则适用于出站呼叫的呼叫号码</span><span class="sxs-lookup"><span data-stu-id="6f4a2-202">These translation rules apply to the calling number for outbound calls</span></span>

    - <span data-ttu-id="6f4a2-203">若要从部署中提供的所有转换规则列表中选择一个或多个企业语音，请单击"选择 **"。**</span><span class="sxs-lookup"><span data-stu-id="6f4a2-203">To choose one or more rules from a list of all translation rules that are available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="6f4a2-204">在“选择转换规则”中，单击要与中继关联的规则，然后单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-204">In **Select Translation Rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>

    - <span data-ttu-id="6f4a2-205">要定义新的转换规则并将其与中继关联，请单击“新建”。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-205">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="6f4a2-206">有关转换规则的详细信息，请参阅[Translation rules in Skype for Business Server。](../../plan-your-deployment/enterprise-voice-solution/translation-rules.md)</span><span class="sxs-lookup"><span data-stu-id="6f4a2-206">For details about translation rules, see [Translation rules in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/translation-rules.md).</span></span>

    - <span data-ttu-id="6f4a2-207">要编辑已经与中继关联的转换规则，请单击相应的规则名称，然后单击“显示详细信息”。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-207">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span>

    - <span data-ttu-id="6f4a2-208">要复制现有的转换规则以作为定义新规则的起点，请单击相应的规则名称，再单击“复制”，然后单击“粘贴”。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-208">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span>

    - <span data-ttu-id="6f4a2-209">要从中继中删除某个转换规则，请突出显示相应的规则名称，然后单击“删除”。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-209">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>

    > [!CAUTION]
    > <span data-ttu-id="6f4a2-210">如果已在关联的中继对等方上配置了转换规则，则不要将任何转换规则与中继相关联，因为这两种规则可能会发生冲突。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-210">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>

16. <span data-ttu-id="6f4a2-p136">（可选）关联和配置中继的“已呼叫号码转换规则”。这些转换规则适用于出站呼叫中的已呼叫号码。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-p136">(Optional) Associate and configure **called number translation rules** for the trunk. The translation rules apply to the called number in an outbound call.</span></span>

    - <span data-ttu-id="6f4a2-213">若要从部署中提供的所有转换规则列表中选择一个或多个企业语音，请单击"选择 **"。**</span><span class="sxs-lookup"><span data-stu-id="6f4a2-213">To choose one or more rules from a list of all translation rules that are available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="6f4a2-214">在“选择转换规则”中，单击要与中继关联的规则，然后单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-214">In **Select Translation Rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>

    - <span data-ttu-id="6f4a2-215">要定义新的转换规则并将其与中继关联，请单击“新建”。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-215">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="6f4a2-216">有关转换规则的详细信息，请参阅[Translation rules in Skype for Business Server。](../../plan-your-deployment/enterprise-voice-solution/translation-rules.md)</span><span class="sxs-lookup"><span data-stu-id="6f4a2-216">For details about translation rules, see [Translation rules in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/translation-rules.md).</span></span>

    - <span data-ttu-id="6f4a2-217">要编辑已经与中继关联的转换规则，请单击相应的规则名称，然后单击“显示详细信息”。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-217">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span>

    - <span data-ttu-id="6f4a2-218">要复制现有的转换规则以作为定义新规则的起点，请单击相应的规则名称，再单击“复制”，然后单击“粘贴”。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-218">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span>

    - <span data-ttu-id="6f4a2-219">要从中继中删除某个转换规则，请突出显示相应的规则名称，然后单击“删除”。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-219">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>

    > [!CAUTION]
    > <span data-ttu-id="6f4a2-220">如果已在关联的中继对等方上配置了转换规则，则不要将任何转换规则与中继相关联，因为这两种规则可能会发生冲突。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-220">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>

17. <span data-ttu-id="6f4a2-221">确保中继的转换规则按正确的顺序排列。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-221">Make sure that the trunk's translation rules are arranged in the correct order.</span></span> <span data-ttu-id="6f4a2-222">若要更改规则在列表中的位置，请突出显示规则名称，然后单击向上箭头或向下箭头。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-222">To change a rule's position in the list, highlight the rule name and then click the up or down arrow.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="6f4a2-223">Skype for Business Server 从上到下遍历转换规则列表，并使用第一个匹配拨打号码的规则。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-223">Skype for Business Server traverses the translation rule list from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="6f4a2-224">如果要配置中继以使拨打号码可以匹配多个转换规则，请确保限制较严格的规则排在限制较宽松的规则上方。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-224">If you configure a trunk so that a dialed number can match more than one translation rule, be sure that the more restrictive rules are sorted above the less restrictive rules.</span></span> <span data-ttu-id="6f4a2-225">例如，如果包含的转换规则与任意 11 位数字匹配，而转换规则仅与以 +1425 开头的 11 位数字匹配，请确保匹配任意 11 位数字的规则排序在限制较严格的规则下面。 </span><span class="sxs-lookup"><span data-stu-id="6f4a2-225">For example, if you have included a translation rule that matches any 11-digit number and a translation rule that matches only 11-digit numbers that start with +1425, be sure that the rule that matches any 11-digit number is sorted  *below*  the more restrictive rule.</span></span>

18. <span data-ttu-id="6f4a2-226">完成中继的配置后，单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-226">When you are finished configuring the trunk, click **OK**.</span></span>

19. <span data-ttu-id="6f4a2-227">在“Trunk 配置”页上，单击“提交”，然后单击“全部提交”。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-227">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6f4a2-228">任何时候创建或修改中继配置，都必须运行“全部提交”命令以发布配置更改。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-228">Whenever you create or modify a trunk configuration, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="6f4a2-229">有关详细信息，请参阅操作文档中的 Publish [pending changes to the voice routing configuration in Skype for Business。](voice-route-config-changes.md)</span><span class="sxs-lookup"><span data-stu-id="6f4a2-229">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

<span data-ttu-id="6f4a2-230">配置中继后，继续通过选择全局媒体旁路选项来配置媒体旁路，如部署文档中的在 [Skype for Business Server](deploy-media-bypass.md) 中部署媒体旁路中所述。</span><span class="sxs-lookup"><span data-stu-id="6f4a2-230">After you have configured the trunk, continue configuring media bypass by choosing between global media bypass options, as described in [Deploy media bypass in Skype for Business Server](deploy-media-bypass.md) in the Deployment documentation.</span></span>
## <a name="see-also"></a><span data-ttu-id="6f4a2-231">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6f4a2-231">See also</span></span>

[<span data-ttu-id="6f4a2-232">在 Skype for Business Server 中配置无媒体旁路的中继</span><span class="sxs-lookup"><span data-stu-id="6f4a2-232">Configure a trunk without media bypass in Skype for Business Server</span></span>](configure-trunk-without-media-bypass.md)

[<span data-ttu-id="6f4a2-233">在 Skype for Business Server 中部署媒体旁路</span><span class="sxs-lookup"><span data-stu-id="6f4a2-233">Deploy media bypass in Skype for Business Server</span></span>](deploy-media-bypass.md)

[<span data-ttu-id="6f4a2-234">定义转换规则</span><span class="sxs-lookup"><span data-stu-id="6f4a2-234">Defining Translation Rules</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-defining-translation-rules)

[<span data-ttu-id="6f4a2-235">配置媒体绕过</span><span class="sxs-lookup"><span data-stu-id="6f4a2-235">Configure Media Bypass</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-configure-media-bypass)