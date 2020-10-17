---
title: Lync Server 2013：使用媒体旁路配置中继
description: Lync Server 2013：使用媒体旁路配置中继。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a trunk with media bypass
ms:assetid: 99d729ea-5a4c-4ff2-a4a3-93a24368da6d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398792(v=OCS.15)
ms:contentKeyID: 48184959
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 51bd58a685e1f4c222a863c21022b3c9dc7c70d6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566748"
---
# <a name="configure-a-trunk-with-media-bypass-in-lync-server-2013"></a><span data-ttu-id="4fc3a-103">在 Lync Server 2013 中配置具有媒体旁路功能的中继</span><span class="sxs-lookup"><span data-stu-id="4fc3a-103">Configure a trunk with media bypass in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4fc3a-104">_**上次修改的主题：** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="4fc3a-104">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="4fc3a-105">按照以下步骤配置启用媒体旁路的中继。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-105">Follow these steps to configure a trunk with media bypass enabled.</span></span> <span data-ttu-id="4fc3a-106">若要配置禁用媒体旁路的中继，请参阅 [在 Lync Server 2013 中配置不使用媒体旁路的中继](lync-server-2013-configure-a-trunk-without-media-bypass.md)。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-106">To configure a trunk with media bypass disabled, see [Configure a trunk without media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md).</span></span> <span data-ttu-id="4fc3a-107">如果希望将部署的中介服务器数目降至最低，媒体绕过非常有用。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-107">Media bypass is useful when you want to minimize the number of Mediation Servers deployed.</span></span> <span data-ttu-id="4fc3a-108">通常会在中央站点部署中介服务器池，中介服务器池将控制分支站点的网关。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-108">Typically, a Mediation Server pool will be deployed at a central site, and it will control gateways at branch sites.</span></span> <span data-ttu-id="4fc3a-109">启用媒体旁路后，来自分支站点中客户端的公用电话交换网 (PSTN) 呼叫的媒体可直接通过这些站点中的网关流动。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-109">Enabling media bypass allows media for public switched telephone network (PSTN) calls from clients at branch sites to flow directly through the gateways at those sites.</span></span> <span data-ttu-id="4fc3a-110">必须正确配置 Lync Server 2013 出站呼叫路由和企业语音策略，以便将来自分支站点的客户端的 PSTN 呼叫路由到相应的网关。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-110">Lync Server 2013 outbound call routes and Enterprise Voice policies must be properly configured so that PSTN calls from clients at a branch site are routed to the appropriate gateway.</span></span>

<span data-ttu-id="4fc3a-111">强烈建议您启用媒体旁路功能。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-111">We strongly recommend that you enable media bypass.</span></span> <span data-ttu-id="4fc3a-112">但是，在 SIP 中继上启用媒体旁路之前，请确认限定的 SIP 中继提供程序支持媒体旁路，并且能够满足成功启用方案的要求。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-112">However, before you enable media bypass on a SIP trunk, confirm that your qualified SIP trunk provider supports media bypass and is able to accommodate the requirements for successfully enabling the scenario.</span></span> <span data-ttu-id="4fc3a-113">具体来说，提供程序必须具有组织内部网络中的服务器的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-113">Specifically, the provider must have the IP addresses of servers in your organization’s internal network.</span></span> <span data-ttu-id="4fc3a-114">如果提供商无法支持此方案，则媒体绕过将会失败。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-114">If the provider cannot support this scenario, media bypass will not succeed.</span></span> <span data-ttu-id="4fc3a-115">有关详细信息，请参阅规划文档中的在 [Lync Server 2013 中规划媒体旁路](lync-server-2013-planning-for-media-bypass.md) 。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-115">For details, see [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) in the Planning documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4fc3a-116">媒体旁路将不会与每个公开交换电话网络互操作 (PSTN) 网关、ip-pbx 和会话边界控制器 (SBC) 。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-116">Media bypass will not interoperate with every public switched telephone network (PSTN) gateway, IP-PBX, and Session Border Controller (SBC).</span></span> <span data-ttu-id="4fc3a-117">Microsoft 已使用认证的合作伙伴测试了一组 PSTN 网关和 SBCs，并且已通过 Cisco IP Pbx 进行了一些测试。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-117">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="4fc3a-118">仅在统一通信开放互操作性计划– Lync Server 上列出的产品和版本支持媒体旁路 <A href="https://go.microsoft.com/fwlink/p/?linkid=214406">https://go.microsoft.com/fwlink/p/?linkId=214406</A> 。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-118">Media bypass is supported only with products and versions that are listed on Unified Communications Open Interoperability Program – Lync Server at <A href="https://go.microsoft.com/fwlink/p/?linkid=214406">https://go.microsoft.com/fwlink/p/?linkId=214406</A>.</span></span>



</div>

<span data-ttu-id="4fc3a-119">下面所述的中继配置将应用于中继的一组参数分配到此中继配置。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-119">A trunk configuration as described below groups a set of parameters that are applied to trunks assigned this trunk configuration.</span></span> <span data-ttu-id="4fc3a-120">特定中继配置的作用域可以是全局中继（针对没有更多特定站点或池配置的所有中继）、站点或者池。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-120">A particular trunk configuration can be scoped globally (to all trunks that do not have more specific site or pool configuration), or to a site, or to a pool.</span></span> <span data-ttu-id="4fc3a-121">池级中继配置用于将特定中继配置的作用域限制为单个中继。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-121">The pool-level trunk configuration is used to scope a specific trunk configuration to a single trunk.</span></span>

<span id="BKMK_ConfigTrunkMediaBypassSteps"></span>

<div>

## <a name="to-configure-a-trunk-with-media-bypass"></a><span data-ttu-id="4fc3a-122">使用媒体旁路配置中继</span><span class="sxs-lookup"><span data-stu-id="4fc3a-122">To configure a trunk with media bypass</span></span>

1.  <span data-ttu-id="4fc3a-123">以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-123">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="4fc3a-124">有关详细信息，请参阅 [Lync Server 2013 中的委派安装权限](lync-server-2013-delegate-setup-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-124">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="4fc3a-125">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-125">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="4fc3a-126">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-126">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="4fc3a-127">在左侧导航栏中，单击“语音路由”\*\*\*\*，然后单击“Trunk 配置”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-127">In the left navigation bar, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

4.  <span data-ttu-id="4fc3a-128">在“Trunk 配置”\*\*\*\* 页上，使用以下方法之一配置中继：</span><span class="sxs-lookup"><span data-stu-id="4fc3a-128">On the **Trunk Configuration** page, use one of the following methods to configure a trunk:</span></span>
    
      - <span data-ttu-id="4fc3a-129">双击某个现有的中继（例如“全局”\*\*\*\* 中继）以显示“编辑 Trunk 配置”\*\*\*\* 对话框。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-129">Double-click an existing trunk (for example, the **Global** trunk) to display the **Edit Trunk Configuration** dialog box.</span></span>
    
      - <span data-ttu-id="4fc3a-130">单击“新建”\*\*\*\*，然后为新的中继配置选择作用域：</span><span class="sxs-lookup"><span data-stu-id="4fc3a-130">Click **New**, and then select a scope for the new trunk configuration:</span></span>
        
          - <span data-ttu-id="4fc3a-131">**站点中继：** 从 " **选择站点**" 中选择此中继配置的站点，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-131">**Site trunk:** Choose the site for this trunk configuration from **Select a Site**, and then click **OK**.</span></span> <span data-ttu-id="4fc3a-132">请注意，如果已经为站点创建了中继配置，则该站点不会显示在“选择站点”\*\*\*\* 中。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-132">Note that if a trunk configuration has already been created for a site, the site does not appear in **Select a Site**.</span></span> <span data-ttu-id="4fc3a-133">此中继配置将应用于站点中的所有中继。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-133">This trunk configuration will be applied to all trunks in the site.</span></span>
        
          - <span data-ttu-id="4fc3a-134">**池中继：** 选择应用此中继配置的中继的名称。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-134">**Pool trunk:** Choose the name of the trunk that this trunk configuration applies to.</span></span> <span data-ttu-id="4fc3a-135">此中继可以是根中继或在拓扑生成器中定义的任何其他中继。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-135">This trunk can be the root trunk or any additional trunks defined in Topology Builder.</span></span> <span data-ttu-id="4fc3a-136">从 " **选择服务**" 中，单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-136">From **Select a Service**, click **OK**.</span></span> <span data-ttu-id="4fc3a-137">请注意，如果已经为特定中继创建了中继配置，则该中继不会显示在“选择服务”\*\*\*\* 中。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-137">Note that if a trunk configuration has already been created for a specific trunk, the trunk does not appear in **Select a Service**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4fc3a-138">选择中继配置的作用域后，无法对其进行更改。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-138">After you select the scope of the trunk configuration, it cannot be changed.</span></span><BR><span data-ttu-id="4fc3a-139">“名称”<STRONG></STRONG>字段将使用中继配置的关联站点或服务的名称进行预填充，且不能更改。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-139">The <STRONG>Name</STRONG> field is prepopulated with the name of the trunk configuration’s associated site or service and cannot be changed.</span></span>

    
    </div>

5.  <span data-ttu-id="4fc3a-140">指定 **最大早期对话框中支持**的值。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-140">Specify a value in **Maximum early dialogs supported**.</span></span> <span data-ttu-id="4fc3a-141">这是公共交换电话网络 (PSTN) 网关、IP-PBX 或 ITSP 会话边界控制器 (SBC) 可以收到发送到中介服务器的邀请的分叉响应的最大数量。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-141">This is the maximum number of forked responses a public switched telephone network (PSTN) gateway, IP-PBX, or ITSP Session Border Controller (SBC) can receive to an INVITE that it sent to the Mediation Server.</span></span> <span data-ttu-id="4fc3a-142">默认值为 20。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-142">The default value is 20.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4fc3a-143">在更改此值之前，请咨询您的服务提供商或设备制造商，以了解有关所用系统功能的详细信息。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-143">Before you change this value, consult your service provider or equipment manufacturer for details about the capabilities of your system.</span></span>

    
    </div>

6.  <span data-ttu-id="4fc3a-144">选择以下 **“加密支持级别”** 选项之一：</span><span class="sxs-lookup"><span data-stu-id="4fc3a-144">Select one of the following **Encryption support level** options:</span></span>
    
      - <span data-ttu-id="4fc3a-145">**必需：** 安全实时传输协议 (SRTP) 加密必须用于帮助保护中介服务器与网关或专用分支 exchange (PBX) 之间的流量。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-145">**Required:** Secure real-time transport protocol (SRTP) encryption must be used to help protect traffic between the Mediation Server and the gateway or private branch exchange (PBX).</span></span>
    
      - <span data-ttu-id="4fc3a-146">**可选：** 如果服务提供商或设备制造商支持，则使用 SRTP 加密。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-146">**Optional:** SRTP encryption will be used if the service provider or equipment manufacturer supports it.</span></span>
    
      - <span data-ttu-id="4fc3a-147">**不支持：** SRTP 加密不受服务提供商或设备制造商支持，因此不会使用。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-147">**Not Supported:** SRTP encryption is not supported by the service provider or equipment manufacturer and therefore will not be used.</span></span>

7.  <span data-ttu-id="4fc3a-148">如果您要绕过中介服务器而通过中继对等方处理媒体，请选中 **“启用媒体绕过”** 复选框。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-148">Select the **Enable media bypass** check box if you want media to bypass the Mediation Server for processing by the trunk peer.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="4fc3a-149">为使媒体绕过功能成功发挥作用，PSTN 网关、IP-PBX 或 ITSP 会话边界控制器必须支持某些功能。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-149">For media bypass to work successfully, the PSTN gateway, IP-PBX, or ITSP Session Border Controller must support certain capabilities.</span></span> <span data-ttu-id="4fc3a-150">有关详细信息，请参阅规划文档中的在 <A href="lync-server-2013-planning-for-media-bypass.md">Lync Server 2013 中规划媒体旁路</A> 。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-150">For details, see <A href="lync-server-2013-planning-for-media-bypass.md">Planning for media bypass in Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>

8.  <span data-ttu-id="4fc3a-p111">如果存在一个已知的媒体端点（例如 PSTN 网关，其中媒体终端与信号终端具有相同的 IP），则选中 **“集中媒体处理”** 复选框。如果中继没有已知的媒体端点，则清除该复选框。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-p111">Select the **Centralized media processing** check box if there is a well-known media termination point (for example, a PSTN gateway where the media termination has the same IP as the signaling termination). Clear this check box if the trunk does not have a well-known media termination point.</span></span>

9.  <span data-ttu-id="4fc3a-153">如果中继对等方支持接收来自中介服务器的 SIP 引用请求，请选中 " **启用发送引用到网关"** 复选框。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-153">If the trunk peer supports receiving SIP REFER requests from the Mediation Server, select the **Enable sending refer to the gateway** check box.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4fc3a-154">如果禁用此选项而选中<STRONG>“启用媒体绕过”</STRONG>选项，则需要其他设置。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-154">If you disable this option while the <STRONG>Enable media bypass</STRONG> option is selected, additional settings are required.</span></span> <span data-ttu-id="4fc3a-155">如果中继对等方不支持接收来自中介服务器的 SIP REFER 请求且启用了媒体绕过，则为了支持媒体绕过的适当条件，还必须运行 <STRONG>Set-CsTrunkConfiguration</STRONG> cmdlet 以禁用活动呼叫和保留呼叫的 RTCP。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-155">If the trunk peer does not support receiving SIP REFER requests from the Mediation Server and media bypass is enabled, you must also run the <STRONG>Set-CsTrunkConfiguration</STRONG> cmdlet to disable RTCP for active and held calls in order to support proper conditions for media bypass.</span></span> <span data-ttu-id="4fc3a-156">有关详细信息，请参阅 <A href="lync-server-2013-lync-server-management-shell.md">Lync Server 2013 命令行管理</A> 程序文档。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-156">For details, see the <A href="lync-server-2013-lync-server-management-shell.md">Lync Server 2013 Management Shell</A> documentation.</span></span><BR><span data-ttu-id="4fc3a-157">或者，如果您希望转移呼叫成为媒体绕过的，并且网关不支持 SIP 引用请求，则可以选择 " <STRONG>使用第三方呼叫控制启用引用</STRONG> "。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-157">Alternatively, you can select <STRONG>Enable refer using third-party-call control</STRONG> if you want transferred calls to be media bypassed, and the gateway does not support SIP REFER requests.</span></span>

    
    </div>

10. <span data-ttu-id="4fc3a-p113">（可选）若要启用中继间路由，请对此中继配置关联和配置 PSTN 用法记录。与此中继配置关联的 PSTN 用法将通过源自 Lync 终结点以外终结点的中继应用于所有传入呼叫。若要管理与中继配置关联的 PSTN 用法记录，请使用以下方法之一：</span><span class="sxs-lookup"><span data-stu-id="4fc3a-p113">(Optional) To enable inter-trunk routing, associate and configure PSTN usage records to this trunk configuration. The PSTN usages associated to this trunk configuration will be applied for all incoming calls through the trunk that is not originating from a Lync endpoint. To manage PSTN usage records associated to a trunk configuration, use one of the following methods:</span></span>
    
      - <span data-ttu-id="4fc3a-161">若要从企业语音部署中提供的所有 PSTN 用法记录列表中选择一个或多个记录，请单击 " **选择**"。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-161">To select one or more records from a list of all PSTN usage records available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="4fc3a-162">突出显示要与此中继配置关联的记录，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-162">Highlight the records you want to associate with this trunk configuration and then click **OK**.</span></span>
    
      - <span data-ttu-id="4fc3a-163">要删除此中继配置中的某个 PSTN 用法记录，请选择相应的记录，然后单击“删除”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-163">To remove a PSTN usage record from this trunk configuration, select the record and click **Remove**.</span></span>
    
      - <span data-ttu-id="4fc3a-164">要定义新的 PSTN 用法记录并将其与此中继配置相关联，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="4fc3a-164">To define a new PSTN usage record and associate it with this trunk configuration, do the following:</span></span>
        
        1.  <span data-ttu-id="4fc3a-165">单击“新建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-165">Click **New**.</span></span>
        
        2.  <span data-ttu-id="4fc3a-166">在“名称”\*\*\*\* 字段中，指定记录的唯一描述性名称。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-166">In the **Name** field, specify a descriptive name for the record that is unique.</span></span>
            
            <div>
            

            > [!NOTE]  
            > <span data-ttu-id="4fc3a-p115">PSTN 用法记录名称在企业语音部署中必须是唯一的。保存记录后，将无法编辑“名称”<STRONG></STRONG>字段。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-p115">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the <STRONG>Name</STRONG> field cannot be edited.</span></span>

            
            </div>
        
        3.  <span data-ttu-id="4fc3a-169">使用以下方法之一为此 PSTN 用法记录关联和配置路由：</span><span class="sxs-lookup"><span data-stu-id="4fc3a-169">Use one of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="4fc3a-170">若要从企业语音部署中的所有可用路由列表中选择一个或多个路由，请单击 " **选择**"。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-170">To select one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="4fc3a-171">突出显示要与此 PSTN 用法记录相关联的路由，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-171">Highlight the routes you want to associate with this PSTN usage record, and click **OK**.</span></span>
            
              - <span data-ttu-id="4fc3a-172">要删除 PSTN 用法记录中的某个路由，请选择相应的路由，然后单击“删除”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-172">To remove a route from the PSTN usage record, select the route, and click **Remove**.</span></span>
            
              - <span data-ttu-id="4fc3a-173">要定义新路由并将其与此 PSTN 用法记录相关联，请单击“新建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-173">To define a new route and associate it to this PSTN usage record, click **New**.</span></span> <span data-ttu-id="4fc3a-174">有关详细信息，请参阅 [在 Lync Server 2013 中创建语音路由](lync-server-2013-create-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-174">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="4fc3a-175">要编辑与此 PSTN 用法记录相关联的路由，请选择相应的路由，然后单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-175">To edit a route that is associated with this PSTN usage record, select the route, and click **Show details**.</span></span> <span data-ttu-id="4fc3a-176">有关详细信息，请参阅 [在 Lync Server 2013 中修改语音路由](lync-server-2013-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-176">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        4.  <span data-ttu-id="4fc3a-177">单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-177">Click **OK**.</span></span>
    
      - <span data-ttu-id="4fc3a-178">要编辑已经与此中继配置相关联的 PSTN 用法记录，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="4fc3a-178">To edit a PSTN usage record that is already associated with this trunk configuration, do the following:</span></span>
        
        1.  <span data-ttu-id="4fc3a-179">选择要编辑的 PSTN 用法记录，然后单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-179">Select the PSTN usage record you want to edit, and click **Show details**.</span></span>
        
        2.  <span data-ttu-id="4fc3a-180">使用以下方法之一为此 PSTN 用法记录关联和配置路由：</span><span class="sxs-lookup"><span data-stu-id="4fc3a-180">Use one of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="4fc3a-181">若要从企业语音部署中的所有可用路由列表中选择一个或多个路由，请单击 " **选择**"。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-181">To select one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="4fc3a-182">突出显示要与此 PSTN 用法记录相关联的路由，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-182">Highlight the routes you want to associate with this PSTN usage record, and click **OK**.</span></span>
            
              - <span data-ttu-id="4fc3a-183">要删除 PSTN 用法记录中的某个路由，请选择相应的路由，然后单击“删除”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-183">To remove a route from the PSTN usage record, select the route, and click **Remove**.</span></span>
            
              - <span data-ttu-id="4fc3a-184">要定义新路由并将其与此 PSTN 用法记录相关联，请单击“新建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-184">To define a new route and associate it to this PSTN usage record, click **New**.</span></span> <span data-ttu-id="4fc3a-185">有关详细信息，请参阅 [在 Lync Server 2013 中创建语音路由](lync-server-2013-create-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-185">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="4fc3a-186">要编辑与此 PSTN 用法记录相关联的路由，请选择相应的路由，然后单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-186">To edit a route that is associated with this PSTN usage record, select the route, and click **Show details**.</span></span> <span data-ttu-id="4fc3a-187">有关详细信息，请参阅 [在 Lync Server 2013 中修改语音路由](lync-server-2013-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-187">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        3.  <span data-ttu-id="4fc3a-188">单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-188">Click **OK**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="4fc3a-189">根据与要配置的中继关联的中介服务器对，关联 PSTN 用法记录非常重要。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-189">It important to associate PSTN usage records according to the Mediation Server peer that is associated to the trunk being configured.</span></span> <span data-ttu-id="4fc3a-190">如果中介服务器对等是 PSTN 网关或会话边界控制器 (SBC) ，强烈建议不要将中继配置与路由到 PSTN 目标的 PSTN 使用记录或通过 Lync Server 连接的任何其他下游系统相关联。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-190">If the Mediation Server peer is a PSTN gateway or a Session Border Controller (SBC), it is strongly recommended that the trunk configuration is not associated to a PSTN usage record that routes to a PSTN destination or any other downstream systems connected via Lync Server.</span></span>

    
    </div>

11. <span data-ttu-id="4fc3a-p123">排列 PSTN 用法记录可获得最佳性能。要更改记录在列表中的位置，请选择 PSTN 用法记录，然后单击向上或向下箭头。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-p123">Arrange the PSTN usage records for optimum performance. To change a record’s position in the list, select the PSTN usage record, and click the up or down arrows.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="4fc3a-193">PSTN 用法记录在中继配置中的列出顺序十分重要。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-193">The order in which PSTN usage records are listed in the trunk configuration is significant.</span></span> <span data-ttu-id="4fc3a-194">Lync Server 从上到下遍历列表。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-194">Lync Server traverses the list from top to down.</span></span>

    
    </div>

12. <span data-ttu-id="4fc3a-195">应选择 "**启用 RTP 闩锁**"，以便为网络地址 (转换后的客户端启用绕过媒体。 NAT) 或防火墙以及支持闭锁的 SBC。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-195">**Enable RTP Latching** should be selected to enable bypass media for clients behind a network address translation (NAT) or firewall and an SBC that supports latching.</span></span>

13. <span data-ttu-id="4fc3a-196">应选择 "**启用转接呼叫历史记录**"，以允许向中介服务器的网关对等方发送呼叫历史记录信息。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-196">**Enable forward call history** should be selected to enable sending of call history information to the gateway peer of the Mediation Server.</span></span>

14. <span data-ttu-id="4fc3a-197">**启用前向 p 声明标识数据** 应选中以启用 P 声明标识 (PAI) 调用发起方信息，以便在中介服务器端和网关端 (之间转发，反之亦然) ，如果存在）。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-197">**Enable forward P-Asserted-Identity data** should be selected to enable the P-Asserted-Identity (PAI) call originator information to be forwarded between the Mediation Server side and gateway side (and vice versa), when present.</span></span>

15. <span data-ttu-id="4fc3a-198">应选择“启用出站路由故障转移计时器”\*\*\*\* 以支持快速故障转移。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-198">**Enable outbound routing failover timer** should be selected to enable fast failover.</span></span> <span data-ttu-id="4fc3a-199">与此中继关联的网关可以在 10 秒内发出正在处理出站呼叫的通知。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-199">The gateway associated with this trunk can give notification within 10 seconds that it is processing an outbound call.</span></span> <span data-ttu-id="4fc3a-200">如果中介服务器未收到此通知，则将重新路由到另一个中继。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-200">Rerouting to another trunk will occur if this notification is not received by the Mediation Server.</span></span> <span data-ttu-id="4fc3a-201">在延迟设置可能延迟响应时间或网关需要 10 秒以上时间进行响应的网络中，应禁用快速故障转移。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-201">On networks where latency may delay the response time or the gateway takes longer than 10 seconds to respond, the fast failover should be disabled.</span></span>

16. <span data-ttu-id="4fc3a-202">（可选）关联和配置中继的“呼叫号码转换规则”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-202">(Optional) Associate and configure **calling number translation rules** for the trunk.</span></span> <span data-ttu-id="4fc3a-203">这些转换规则适用于出站呼叫的呼叫号码</span><span class="sxs-lookup"><span data-stu-id="4fc3a-203">These translation rules apply to the calling number for outbound calls</span></span>
    
      - <span data-ttu-id="4fc3a-204">若要从企业语音部署中可用的所有转换规则列表中选择一个或多个规则，请单击 " **选择**"。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-204">To choose one or more rules from a list of all translation rules that are available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="4fc3a-205">在“选择转换规则”\*\*\*\* 中，单击要与中继关联的规则，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-205">In **Select Translation Rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>
    
      - <span data-ttu-id="4fc3a-206">要定义新的转换规则并将其与中继关联，请单击“新建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-206">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="4fc3a-207">有关定义新规则的详细信息，请参阅部署文档中的 [在 Lync Server 2013 中定义转换规则](lync-server-2013-defining-translation-rules.md) 。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-207">For details about defining a new rule, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="4fc3a-208">要编辑已经与中继关联的转换规则，请单击相应的规则名称，然后单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-208">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span> <span data-ttu-id="4fc3a-209">有关详细信息，请参阅部署文档中的 [在 Lync Server 2013 中定义转换规则](lync-server-2013-defining-translation-rules.md) 。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-209">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="4fc3a-210">要复制现有的转换规则以作为定义新规则的起点，请单击相应的规则名称，再单击“复制”\*\*\*\*，然后单击“粘贴”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-210">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="4fc3a-211">有关详细信息，请参阅 [在 Lync Server 2013 中定义转换规则](lync-server-2013-defining-translation-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-211">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span></span>
    
      - <span data-ttu-id="4fc3a-212">要从中继中删除某个转换规则，请突出显示相应的规则名称，然后单击“删除”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-212">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="4fc3a-213">如果已在关联的中继对等方上配置了转换规则，则不要将任何转换规则与中继相关联，因为这两种规则可能会发生冲突。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-213">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>

    
    </div>

17. <span data-ttu-id="4fc3a-p131">（可选）关联和配置中继的“已呼叫号码转换规则”\*\*\*\*。这些转换规则适用于出站呼叫中的已呼叫号码。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-p131">(Optional) Associate and configure **called number translation rules** for the trunk. The translation rules apply to the called number in an outbound call.</span></span>
    
      - <span data-ttu-id="4fc3a-216">若要从企业语音部署中可用的所有转换规则列表中选择一个或多个规则，请单击 " **选择**"。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-216">To choose one or more rules from a list of all translation rules that are available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="4fc3a-217">在“选择转换规则”\*\*\*\* 中，单击要与中继关联的规则，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-217">In **Select Translation Rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>
    
      - <span data-ttu-id="4fc3a-218">要定义新的转换规则并将其与中继关联，请单击“新建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-218">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="4fc3a-219">有关定义新规则的详细信息，请参阅部署文档中的 [在 Lync Server 2013 中定义转换规则](lync-server-2013-defining-translation-rules.md) 。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-219">For details about defining a new rule, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="4fc3a-220">要编辑已经与中继关联的转换规则，请单击相应的规则名称，然后单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-220">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span> <span data-ttu-id="4fc3a-221">有关详细信息，请参阅部署文档中的 [在 Lync Server 2013 中定义转换规则](lync-server-2013-defining-translation-rules.md) 。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-221">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="4fc3a-222">要复制现有的转换规则以作为定义新规则的起点，请单击相应的规则名称，再单击“复制”\*\*\*\*，然后单击“粘贴”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-222">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="4fc3a-223">有关详细信息，请参阅 [在 Lync Server 2013 中定义转换规则](lync-server-2013-defining-translation-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-223">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span></span>
    
      - <span data-ttu-id="4fc3a-224">要从中继中删除某个转换规则，请突出显示相应的规则名称，然后单击“删除”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-224">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="4fc3a-225">如果已在关联的中继对等方上配置了转换规则，则不要将任何转换规则与中继相关联，因为这两种规则可能会发生冲突。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-225">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>

    
    </div>

18. <span data-ttu-id="4fc3a-226">请确保该中继的转换规则按正确的顺序排列。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-226">Make sure that the trunk’s translation rules are arranged in the correct order.</span></span> <span data-ttu-id="4fc3a-227">要更改规则在列表中的位置，请突出显示相应的规则名称，然后单击向上箭头或向下箭头。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-227">To change a rule’s position in the list, highlight the rule name and then click the up or down arrow.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="4fc3a-228">Lync Server 2013 从上到下遍历翻译规则列表，并使用第一个与拨打的号码相匹配的规则。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-228">Lync Server 2013 traverses the translation rule list from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="4fc3a-229">如果要配置中继以使拨打号码可以匹配多个转换规则，请确保限制较严格的规则排在限制较宽松的规则上方。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-229">If you configure a trunk so that a dialed number can match more than one translation rule, be sure that the more restrictive rules are sorted above the less restrictive rules.</span></span> <span data-ttu-id="4fc3a-230">例如，如果具有与任何 11 位数字相匹配的转换规则和只与以 +1425 开头的 11 位数字相匹配的转换规则，请确保与任何 11 位数字相匹配的规则排在更加严格的规则<EM>下方</EM>。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-230">For example, if you have included a translation rule that matches any 11-digit number and a translation rule that matches only 11-digit numbers that start with +1425, be sure that the rule that matches any 11-digit number is sorted <EM>below</EM> the more restrictive rule.</span></span>

    
    </div>

19. <span data-ttu-id="4fc3a-231">完成中继的配置后，单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-231">When you are finished configuring the trunk, click **OK**.</span></span>

20. <span data-ttu-id="4fc3a-232">在“Trunk 配置”\*\*\*\* 页上，单击“提交”\*\*\*\*，然后单击“全部提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-232">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4fc3a-233">任何时候创建或修改中继配置，都必须运行“全部提交”<STRONG></STRONG>命令以发布配置更改。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-233">Whenever you create or modify a trunk configuration, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="4fc3a-234">有关详细信息，请参阅操作文档中的在 <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 中发布待处理的语音路由配置的更改</A> 。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-234">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

<span data-ttu-id="4fc3a-235">配置中继后，通过选择全局媒体旁路选项继续配置媒体旁路，如部署文档中的 [Lync Server 2013 中的全局媒体旁路选项](lync-server-2013-global-media-bypass-options.md) 中所述。</span><span class="sxs-lookup"><span data-stu-id="4fc3a-235">After you have configured the trunk, continue configuring media bypass by choosing between global media bypass options, as described in [Global media bypass options in Lync Server 2013](lync-server-2013-global-media-bypass-options.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4fc3a-236">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4fc3a-236">See Also</span></span>


[<span data-ttu-id="4fc3a-237">在 Lync Server 2013 中配置无媒体旁路功能的中继</span><span class="sxs-lookup"><span data-stu-id="4fc3a-237">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)  


[<span data-ttu-id="4fc3a-238">在 Lync Server 2013 中配置媒体旁路</span><span class="sxs-lookup"><span data-stu-id="4fc3a-238">Configure media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-media-bypass.md)  
[<span data-ttu-id="4fc3a-239">Lync Server 2013 中的全局媒体旁路选项</span><span class="sxs-lookup"><span data-stu-id="4fc3a-239">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  


[<span data-ttu-id="4fc3a-240">在 Lync Server 2013 中定义转换规则</span><span class="sxs-lookup"><span data-stu-id="4fc3a-240">Defining translation rules in Lync Server 2013</span></span>](lync-server-2013-defining-translation-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

