---
title: Lync Server 2013：使用媒体旁路配置主干
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
ms.openlocfilehash: 16c12a5d8cff03f8d5755b5a2b54a6ff4dcf8399
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741352"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-trunk-with-media-bypass-in-lync-server-2013"></a><span data-ttu-id="8e377-102">Configure a trunk with media bypass in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8e377-102">Configure a trunk with media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8e377-103">_**主题上次修改时间：** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="8e377-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="8e377-104">执行以下步骤可配置启用媒体旁路的中继。</span><span class="sxs-lookup"><span data-stu-id="8e377-104">Follow these steps to configure a trunk with media bypass enabled.</span></span> <span data-ttu-id="8e377-105">若要在禁用媒体旁路的情况下配置主干，请参阅[在 Lync Server 2013 中不使用媒体旁路配置主干](lync-server-2013-configure-a-trunk-without-media-bypass.md)。</span><span class="sxs-lookup"><span data-stu-id="8e377-105">To configure a trunk with media bypass disabled, see [Configure a trunk without media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md).</span></span> <span data-ttu-id="8e377-106">当您想要最大程度地减少已部署中介服务器的数量时，媒体绕过非常有用。</span><span class="sxs-lookup"><span data-stu-id="8e377-106">Media bypass is useful when you want to minimize the number of Mediation Servers deployed.</span></span> <span data-ttu-id="8e377-107">通常，将在中心网站上部署中介服务器池，并且它将控制分支站点上的网关。</span><span class="sxs-lookup"><span data-stu-id="8e377-107">Typically, a Mediation Server pool will be deployed at a central site, and it will control gateways at branch sites.</span></span> <span data-ttu-id="8e377-108">启用媒体旁路后，来自分支站点中客户端的公用电话交换网 (PSTN) 呼叫的媒体可直接通过这些站点中的网关流动。</span><span class="sxs-lookup"><span data-stu-id="8e377-108">Enabling media bypass allows media for public switched telephone network (PSTN) calls from clients at branch sites to flow directly through the gateways at those sites.</span></span> <span data-ttu-id="8e377-109">必须正确配置 Lync Server 2013 出站呼叫路由和企业语音策略，以便将来自分支站点的客户端的 PSTN 呼叫路由到相应的网关。</span><span class="sxs-lookup"><span data-stu-id="8e377-109">Lync Server 2013 outbound call routes and Enterprise Voice policies must be properly configured so that PSTN calls from clients at a branch site are routed to the appropriate gateway.</span></span>

<span data-ttu-id="8e377-110">强烈建议您启用媒体旁路。</span><span class="sxs-lookup"><span data-stu-id="8e377-110">We strongly recommend that you enable media bypass.</span></span> <span data-ttu-id="8e377-111">但是在 SIP 中继上启用媒体旁路之前，请确认您的合格 SIP 中继提供商是否支持媒体旁路且能够满足成功启用方案的要求。</span><span class="sxs-lookup"><span data-stu-id="8e377-111">However, before you enable media bypass on a SIP trunk, confirm that your qualified SIP trunk provider supports media bypass and is able to accommodate the requirements for successfully enabling the scenario.</span></span> <span data-ttu-id="8e377-112">具体而言，提供商必须有您组织内部网络中的服务器的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="8e377-112">Specifically, the provider must have the IP addresses of servers in your organization’s internal network.</span></span> <span data-ttu-id="8e377-113">如果提供程序无法支持此方案，则媒体绕过将不会成功。</span><span class="sxs-lookup"><span data-stu-id="8e377-113">If the provider cannot support this scenario, media bypass will not succeed.</span></span> <span data-ttu-id="8e377-114">有关详细信息，请参阅规划文档中的在[Lync Server 2013 中规划媒体旁路](lync-server-2013-planning-for-media-bypass.md)。</span><span class="sxs-lookup"><span data-stu-id="8e377-114">For details, see [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) in the Planning documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8e377-115">媒体旁路不能与每个公共交换式电话网络（PSTN）网关、IP PBX 和会话边界控制器（SBC）互操作。</span><span class="sxs-lookup"><span data-stu-id="8e377-115">Media bypass will not interoperate with every public switched telephone network (PSTN) gateway, IP-PBX, and Session Border Controller (SBC).</span></span> <span data-ttu-id="8e377-116">Microsoft 与认证合作伙伴一起对一组 PSTN 网关和 SBC 进行了测试，另外也对 Cisco IP-PBX 进行了一些测试。</span><span class="sxs-lookup"><span data-stu-id="8e377-116">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="8e377-117">只有在统一通信打开的互操作性计划（Lync Server）上列出的产品和版本才支持<A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>媒体绕过。</span><span class="sxs-lookup"><span data-stu-id="8e377-117">Media bypass is supported only with products and versions that are listed on Unified Communications Open Interoperability Program – Lync Server at <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>.</span></span>



</div>

<span data-ttu-id="8e377-p104">如下所述的中继组合了一组应用于分配了此中继配置的中继的参数。可以将特定的中继配置的范围限定为全局（没有更特定的站点或池配置的所有中继）、一个站点或一个池。池级别中继配置用于将特定中继配置的范围限定为单个中继。</span><span class="sxs-lookup"><span data-stu-id="8e377-p104">A trunk configuration as described below groups a set of parameters that are applied to trunks assigned this trunk configuration. A particular trunk configuration can be scoped globally (to all trunks that do not have more specific site or pool configuration), or to a site, or to a pool. The pool-level trunk configuration is used to scope a specific trunk configuration to a single trunk.</span></span>

<span id="BKMK_ConfigTrunkMediaBypassSteps"></span>

<div>

## <a name="to-configure-a-trunk-with-media-bypass"></a><span data-ttu-id="8e377-121">配置带媒体旁路的中继</span><span class="sxs-lookup"><span data-stu-id="8e377-121">To configure a trunk with media bypass</span></span>

1.  <span data-ttu-id="8e377-122">以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。</span><span class="sxs-lookup"><span data-stu-id="8e377-122">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="8e377-123">有关详细信息，请参阅[在 Lync Server 2013 中委派设置权限](lync-server-2013-delegate-setup-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="8e377-123">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="8e377-124">打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="8e377-124">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="8e377-125">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="8e377-125">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="8e377-126">在左侧导航栏中，单击“语音路由”\*\*\*\*，然后单击“Trunk 配置”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8e377-126">In the left navigation bar, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

4.  <span data-ttu-id="8e377-127">在“Trunk 配置”\*\*\*\* 页上，使用以下方法之一配置中继：</span><span class="sxs-lookup"><span data-stu-id="8e377-127">On the **Trunk Configuration** page, use one of the following methods to configure a trunk:</span></span>
    
      - <span data-ttu-id="8e377-128">双击某个现有的中继（例如“全局”\*\*\*\* 中继）以显示“编辑 Trunk 配置”\*\*\*\* 对话框。</span><span class="sxs-lookup"><span data-stu-id="8e377-128">Double-click an existing trunk (for example, the **Global** trunk) to display the **Edit Trunk Configuration** dialog box.</span></span>
    
      - <span data-ttu-id="8e377-129">单击“新建”\*\*\*\*，然后为新的中继配置选择范围：</span><span class="sxs-lookup"><span data-stu-id="8e377-129">Click **New**, and then select a scope for the new trunk configuration:</span></span>
        
          - <span data-ttu-id="8e377-130">**网站主干：** 从 "**选择网站**" 中选择此中继配置的网站，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="8e377-130">**Site trunk:** Choose the site for this trunk configuration from **Select a Site**, and then click **OK**.</span></span> <span data-ttu-id="8e377-131">请注意，如果已经为站点创建了中继配置，则该站点不会显示在“选择站点”\*\*\*\* 中。</span><span class="sxs-lookup"><span data-stu-id="8e377-131">Note that if a trunk configuration has already been created for a site, the site does not appear in **Select a Site**.</span></span> <span data-ttu-id="8e377-132">此中继配置将应用于站点中的所有中继。</span><span class="sxs-lookup"><span data-stu-id="8e377-132">This trunk configuration will be applied to all trunks in the site.</span></span>
        
          - <span data-ttu-id="8e377-133">**池干线：** 选择此中继配置适用的主干的名称。</span><span class="sxs-lookup"><span data-stu-id="8e377-133">**Pool trunk:** Choose the name of the trunk that this trunk configuration applies to.</span></span> <span data-ttu-id="8e377-134">此主干可以是 "根主干" 或 "拓扑生成器" 中定义的任何其他中继。</span><span class="sxs-lookup"><span data-stu-id="8e377-134">This trunk can be the root trunk or any additional trunks defined in Topology Builder.</span></span> <span data-ttu-id="8e377-135">从“选择服务”\*\*\*\* 中，单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8e377-135">From **Select a Service**, click **OK**.</span></span> <span data-ttu-id="8e377-136">请注意，如果已为特定中继创建中继配置，则此中继不会显示在“选择服务”\*\*\*\* 中。</span><span class="sxs-lookup"><span data-stu-id="8e377-136">Note that if a trunk configuration has already been created for a specific trunk, the trunk does not appear in **Select a Service**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8e377-137">选择中继配置的范围后无法更改该范围。</span><span class="sxs-lookup"><span data-stu-id="8e377-137">After you select the scope of the trunk configuration, it cannot be changed.</span></span><BR><span data-ttu-id="8e377-138">“名称”<STRONG></STRONG>字段会使用中继配置的关联站点或服务的名称进行预填充，且不能更改。</span><span class="sxs-lookup"><span data-stu-id="8e377-138">The <STRONG>Name</STRONG> field is prepopulated with the name of the trunk configuration’s associated site or service and cannot be changed.</span></span>

    
    </div>

5.  <span data-ttu-id="8e377-p109">在“支持的最大早期对话数”\*\*\*\* 中指定一个值。这是公用电话交换网 (PSTN) 网关、IP-PBX 或 ITSP 会话边界控制器 (SBC) 可以接收的分叉响应的最大数目，这些响应针对的是发送到中介服务器的邀请。默认值为 20。</span><span class="sxs-lookup"><span data-stu-id="8e377-p109">Specify a value in **Maximum early dialogs supported**. This is the maximum number of forked responses a public switched telephone network (PSTN) gateway, IP-PBX, or ITSP Session Border Controller (SBC) can receive to an INVITE that it sent to the Mediation Server. The default value is 20.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8e377-142">在更改此值之前，请咨询您的服务提供商或设备制造商，以了解有关所用系统功能的详细信息。</span><span class="sxs-lookup"><span data-stu-id="8e377-142">Before you change this value, consult your service provider or equipment manufacturer for details about the capabilities of your system.</span></span>

    
    </div>

6.  <span data-ttu-id="8e377-143">选择以下“加密支持级别”\*\*\*\* 选项之一：</span><span class="sxs-lookup"><span data-stu-id="8e377-143">Select one of the following **Encryption support level** options:</span></span>
    
      - <span data-ttu-id="8e377-144">**必需：** 安全实时传输协议（SRTP）加密必须用于帮助保护中介服务器与网关或专用分支交换（PBX）之间的流量。</span><span class="sxs-lookup"><span data-stu-id="8e377-144">**Required:** Secure real-time transport protocol (SRTP) encryption must be used to help protect traffic between the Mediation Server and the gateway or private branch exchange (PBX).</span></span>
    
      - <span data-ttu-id="8e377-145">**可选：** 如果服务提供商或设备制造商支持，则使用 SRTP 加密。</span><span class="sxs-lookup"><span data-stu-id="8e377-145">**Optional:** SRTP encryption will be used if the service provider or equipment manufacturer supports it.</span></span>
    
      - <span data-ttu-id="8e377-146">**不支持：** SRTP 加密不受服务提供商或设备制造商支持，因此不会使用。</span><span class="sxs-lookup"><span data-stu-id="8e377-146">**Not Supported:** SRTP encryption is not supported by the service provider or equipment manufacturer and therefore will not be used.</span></span>

7.  <span data-ttu-id="8e377-147">如果您要绕过中介服务器而通过中继对等方处理媒体，请选中“启用媒体旁路”\*\*\*\* 复选框。</span><span class="sxs-lookup"><span data-stu-id="8e377-147">Select the **Enable media bypass** check box if you want media to bypass the Mediation Server for processing by the trunk peer.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="8e377-148">为使媒体旁路功能成功发挥作用，PSTN 网关、IP-PBX 或 ITSP 会话边界控制器必须支持某些功能。</span><span class="sxs-lookup"><span data-stu-id="8e377-148">For media bypass to work successfully, the PSTN gateway, IP-PBX, or ITSP Session Border Controller must support certain capabilities.</span></span> <span data-ttu-id="8e377-149">有关详细信息，请参阅规划文档中的在<A href="lync-server-2013-planning-for-media-bypass.md">Lync Server 2013 中规划媒体旁路</A>。</span><span class="sxs-lookup"><span data-stu-id="8e377-149">For details, see <A href="lync-server-2013-planning-for-media-bypass.md">Planning for media bypass in Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>

8.  <span data-ttu-id="8e377-p111">如果存在一个已知的媒体端点（例如 PSTN 网关，其中媒体终端与信号终端具有相同的 IP），则选中“集中式媒体处理”\*\*\*\* 复选框。如果中继没有已知的媒体端点，则清除该复选框。</span><span class="sxs-lookup"><span data-stu-id="8e377-p111">Select the **Centralized media processing** check box if there is a well-known media termination point (for example, a PSTN gateway where the media termination has the same IP as the signaling termination). Clear this check box if the trunk does not have a well-known media termination point.</span></span>

9.  <span data-ttu-id="8e377-152">如果中继对等支持接收来自中介服务器的 SIP，请选中 "**启用发送指向网关**的请求" 复选框。</span><span class="sxs-lookup"><span data-stu-id="8e377-152">If the trunk peer supports receiving SIP REFER requests from the Mediation Server, select the **Enable sending refer to the gateway** check box.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8e377-153">如果禁用此选项而选中“启用媒体旁路”<STRONG></STRONG>选项，则需要其他设置。</span><span class="sxs-lookup"><span data-stu-id="8e377-153">If you disable this option while the <STRONG>Enable media bypass</STRONG> option is selected, additional settings are required.</span></span> <span data-ttu-id="8e377-154">如果中继对等方不支持接收来自中介服务器的 SIP REFER 请求且启用了媒体旁路，则为了支持媒体旁路的适当条件，还必须运行 <STRONG>Set-CsTrunkConfiguration</STRONG> cmdlet 以禁用活动呼叫和保留呼叫的 RTCP。</span><span class="sxs-lookup"><span data-stu-id="8e377-154">If the trunk peer does not support receiving SIP REFER requests from the Mediation Server and media bypass is enabled, you must also run the <STRONG>Set-CsTrunkConfiguration</STRONG> cmdlet to disable RTCP for active and held calls in order to support proper conditions for media bypass.</span></span> <span data-ttu-id="8e377-155">有关详细信息，请参阅<A href="lync-server-2013-lync-server-management-shell.md">Lync Server 2013 管理外壳</A>文档。</span><span class="sxs-lookup"><span data-stu-id="8e377-155">For details, see the <A href="lync-server-2013-lync-server-management-shell.md">Lync Server 2013 Management Shell</A> documentation.</span></span><BR><span data-ttu-id="8e377-156">此外，如果您希望转移的呼叫传输支持媒体旁路，并且网关不支持 SIP REFER 请求，则您可以选择“允许使用第三方呼叫控制的引用”<STRONG></STRONG>。</span><span class="sxs-lookup"><span data-stu-id="8e377-156">Alternatively, you can select <STRONG>Enable refer using third-party-call control</STRONG> if you want transferred calls to be media bypassed, and the gateway does not support SIP REFER requests.</span></span>

    
    </div>

10. <span data-ttu-id="8e377-157">（可选）若要启用中继间路由，请将 PSTN 用法记录关联到此中继配置并进行相应的配置。</span><span class="sxs-lookup"><span data-stu-id="8e377-157">(Optional) To enable inter-trunk routing, associate and configure PSTN usage records to this trunk configuration.</span></span> <span data-ttu-id="8e377-158">与此干线配置关联的 PSTN 用法将应用于所有传入呼叫，该主干不是从 Lync 终结点发起的。</span><span class="sxs-lookup"><span data-stu-id="8e377-158">The PSTN usages associated to this trunk configuration will be applied for all incoming calls through the trunk that is not originating from a Lync endpoint.</span></span> <span data-ttu-id="8e377-159">若要管理与中继配置关联的 PSTN 用法记录，请使用下列方法之一：</span><span class="sxs-lookup"><span data-stu-id="8e377-159">To manage PSTN usage records associated to a trunk configuration, use one of the following methods:</span></span>
    
      - <span data-ttu-id="8e377-160">若要从您的企业语音部署中可用的所有 PSTN 使用记录列表中选择一个或多个记录，请单击 "**选择**"。</span><span class="sxs-lookup"><span data-stu-id="8e377-160">To select one or more records from a list of all PSTN usage records available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="8e377-161">突出显示要与此中继配置关联的记录，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8e377-161">Highlight the records you want to associate with this trunk configuration and then click **OK**.</span></span>
    
      - <span data-ttu-id="8e377-162">要删除此中继配置中的某个 PSTN 用法记录，请选择此记录，并单击“删除”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8e377-162">To remove a PSTN usage record from this trunk configuration, select the record and click **Remove**.</span></span>
    
      - <span data-ttu-id="8e377-163">要定义新的 PSTN 用法记录并将其与此中继配置相关联，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="8e377-163">To define a new PSTN usage record and associate it with this trunk configuration, do the following:</span></span>
        
        1.  <span data-ttu-id="8e377-164">单击“新建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8e377-164">Click **New**.</span></span>
        
        2.  <span data-ttu-id="8e377-165">在“名称”\*\*\*\* 字段中，为记录指定唯一的描述性名称。</span><span class="sxs-lookup"><span data-stu-id="8e377-165">In the **Name** field, specify a descriptive name for the record that is unique.</span></span>
            
            <div>
            

            > [!NOTE]  
            > <span data-ttu-id="8e377-p115">PSTN 用法记录名称在企业语音部署中必须是唯一的。保存记录后，将无法编辑“名称”<STRONG></STRONG>字段。</span><span class="sxs-lookup"><span data-stu-id="8e377-p115">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the <STRONG>Name</STRONG> field cannot be edited.</span></span>

            
            </div>
        
        3.  <span data-ttu-id="8e377-168">使用下列方法之一为此 PSTN 用法记录关联和配置路由：</span><span class="sxs-lookup"><span data-stu-id="8e377-168">Use one of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="8e377-169">若要从您的企业语音部署中的所有可用路由列表中选择一个或多个路由，请单击 "**选择**"。</span><span class="sxs-lookup"><span data-stu-id="8e377-169">To select one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="8e377-170">突出显示要与此 PSTN 用法记录相关联的路由，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8e377-170">Highlight the routes you want to associate with this PSTN usage record, and click **OK**.</span></span>
            
              - <span data-ttu-id="8e377-171">要删除 PSTN 用法记录中的某个路由，请选择此路由，然后单击“删除”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8e377-171">To remove a route from the PSTN usage record, select the route, and click **Remove**.</span></span>
            
              - <span data-ttu-id="8e377-172">要定义新路由并将其与此 PSTN 用法记录相关联，请单击“新建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8e377-172">To define a new route and associate it to this PSTN usage record, click **New**.</span></span> <span data-ttu-id="8e377-173">有关详细信息，请参阅[在 Lync Server 2013 中创建语音路由](lync-server-2013-create-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="8e377-173">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="8e377-174">要编辑与此 PSTN 用法记录相关联的路由，请选择此路由，然后单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8e377-174">To edit a route that is associated with this PSTN usage record, select the route, and click **Show details**.</span></span> <span data-ttu-id="8e377-175">有关详细信息，请参阅[在 Lync Server 2013 中修改语音路由](lync-server-2013-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="8e377-175">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        4.  <span data-ttu-id="8e377-176">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="8e377-176">Click **OK**.</span></span>
    
      - <span data-ttu-id="8e377-177">要编辑已经与此中继配置相关联的 PSTN 用法记录，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="8e377-177">To edit a PSTN usage record that is already associated with this trunk configuration, do the following:</span></span>
        
        1.  <span data-ttu-id="8e377-178">选择要编辑的 PSTN 用法记录，然后单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8e377-178">Select the PSTN usage record you want to edit, and click **Show details**.</span></span>
        
        2.  <span data-ttu-id="8e377-179">使用下列方法之一为此 PSTN 用法记录关联和配置路由：</span><span class="sxs-lookup"><span data-stu-id="8e377-179">Use one of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="8e377-180">若要从您的企业语音部署中的所有可用路由列表中选择一个或多个路由，请单击 "**选择**"。</span><span class="sxs-lookup"><span data-stu-id="8e377-180">To select one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="8e377-181">突出显示要与此 PSTN 用法记录相关联的路由，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8e377-181">Highlight the routes you want to associate with this PSTN usage record, and click **OK**.</span></span>
            
              - <span data-ttu-id="8e377-182">要删除 PSTN 用法记录中的某个路由，请选择此路由，然后单击“删除”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8e377-182">To remove a route from the PSTN usage record, select the route, and click **Remove**.</span></span>
            
              - <span data-ttu-id="8e377-183">要定义新路由并将其与此 PSTN 用法记录相关联，请单击“新建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8e377-183">To define a new route and associate it to this PSTN usage record, click **New**.</span></span> <span data-ttu-id="8e377-184">有关详细信息，请参阅[在 Lync Server 2013 中创建语音路由](lync-server-2013-create-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="8e377-184">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="8e377-185">要编辑与此 PSTN 用法记录相关联的路由，请选择此路由，然后单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8e377-185">To edit a route that is associated with this PSTN usage record, select the route, and click **Show details**.</span></span> <span data-ttu-id="8e377-186">有关详细信息，请参阅[在 Lync Server 2013 中修改语音路由](lync-server-2013-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="8e377-186">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        3.  <span data-ttu-id="8e377-187">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="8e377-187">Click **OK**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="8e377-188">根据与正在配置的主干相关联的中介服务器对，关联 PSTN 使用记录非常重要。</span><span class="sxs-lookup"><span data-stu-id="8e377-188">It important to associate PSTN usage records according to the Mediation Server peer that is associated to the trunk being configured.</span></span> <span data-ttu-id="8e377-189">如果中介服务器对等是 PSTN 网关或会话边界控制器（SBC），强烈建议不要将干线配置与路由到 PSTN 目标或通过 Lync 连接的任何其他下游系统的 PSTN 使用记录相关联服务.</span><span class="sxs-lookup"><span data-stu-id="8e377-189">If the Mediation Server peer is a PSTN gateway or a Session Border Controller (SBC), it is strongly recommended that the trunk configuration is not associated to a PSTN usage record that routes to a PSTN destination or any other downstream systems connected via Lync Server.</span></span>

    
    </div>

11. <span data-ttu-id="8e377-p123">排列 PSTN 用法记录以获得最佳性能。要更改记录在列表中的位置，请选择 PSTN 用法记录，并单击向上箭头或向下箭头。</span><span class="sxs-lookup"><span data-stu-id="8e377-p123">Arrange the PSTN usage records for optimum performance. To change a record’s position in the list, select the PSTN usage record, and click the up or down arrows.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="8e377-192">PSTN 用法记录在中继配置中列出的顺序很重要。</span><span class="sxs-lookup"><span data-stu-id="8e377-192">The order in which PSTN usage records are listed in the trunk configuration is significant.</span></span> <span data-ttu-id="8e377-193">Lync 服务器从上到下遍历列表。</span><span class="sxs-lookup"><span data-stu-id="8e377-193">Lync Server traverses the list from top to down.</span></span>

    
    </div>

12. <span data-ttu-id="8e377-194">应选择“启用 RTP 闭锁”\*\*\*\* 为网络地址转换 (NAT) 或防火墙以及支持闭锁的 SBC 后面的客户端启用媒体旁路。</span><span class="sxs-lookup"><span data-stu-id="8e377-194">**Enable RTP Latching** should be selected to enable bypass media for clients behind a network address translation (NAT) or firewall and an SBC that supports latching.</span></span>

13. <span data-ttu-id="8e377-195">应选择 "**启用转发呼叫" 历史记录**，以便为中介服务器的网关对等发送呼叫历史记录信息。</span><span class="sxs-lookup"><span data-stu-id="8e377-195">**Enable forward call history** should be selected to enable sending of call history information to the gateway peer of the Mediation Server.</span></span>

14. <span data-ttu-id="8e377-196">**启用前向 p 声明标识数据**应选中以启用 P 声明标识（PAI）调用发起方信息，以便在中介服务器端和网关端（反之亦然）之间转发。</span><span class="sxs-lookup"><span data-stu-id="8e377-196">**Enable forward P-Asserted-Identity data** should be selected to enable the P-Asserted-Identity (PAI) call originator information to be forwarded between the Mediation Server side and gateway side (and vice versa), when present.</span></span>

15. <span data-ttu-id="8e377-197">应选择“启用出站路由故障转移计时器”\*\*\*\* 以启用快速故障转移。</span><span class="sxs-lookup"><span data-stu-id="8e377-197">**Enable outbound routing failover timer** should be selected to enable fast failover.</span></span> <span data-ttu-id="8e377-198">与此中继关联的网关会在 10 秒内发送通知，告知正在处理出站呼叫。</span><span class="sxs-lookup"><span data-stu-id="8e377-198">The gateway associated with this trunk can give notification within 10 seconds that it is processing an outbound call.</span></span> <span data-ttu-id="8e377-199">如果中介服务器未收到此通知，将会重新路由到另一个主干。</span><span class="sxs-lookup"><span data-stu-id="8e377-199">Rerouting to another trunk will occur if this notification is not received by the Mediation Server.</span></span> <span data-ttu-id="8e377-200">在延迟可能推迟响应时间或网关需要花费 10 秒以上的时间才能响应，应禁用快速故障转移。</span><span class="sxs-lookup"><span data-stu-id="8e377-200">On networks where latency may delay the response time or the gateway takes longer than 10 seconds to respond, the fast failover should be disabled.</span></span>

16. <span data-ttu-id="8e377-201">（可选）为中继关联和配置“主叫号码转换规则”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8e377-201">(Optional) Associate and configure **calling number translation rules** for the trunk.</span></span> <span data-ttu-id="8e377-202">这些转换规则适用于出站呼叫的主叫号码</span><span class="sxs-lookup"><span data-stu-id="8e377-202">These translation rules apply to the calling number for outbound calls</span></span>
    
      - <span data-ttu-id="8e377-203">若要从您的企业语音部署中可用的所有翻译规则列表中选择一个或多个规则，请单击 "**选择**"。</span><span class="sxs-lookup"><span data-stu-id="8e377-203">To choose one or more rules from a list of all translation rules that are available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="8e377-204">在“选择转换规则”\*\*\*\* 中，单击要与中继关联的规则，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8e377-204">In **Select Translation Rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>
    
      - <span data-ttu-id="8e377-205">要定义新的转换规则并将其与中继相关联，请单击“新建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8e377-205">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="8e377-206">有关定义新规则的详细信息，请参阅部署文档中[Lync Server 2013 中的 "定义翻译规则](lync-server-2013-defining-translation-rules.md)"。</span><span class="sxs-lookup"><span data-stu-id="8e377-206">For details about defining a new rule, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="8e377-207">要编辑已与中继关联的转换规则，请单击相应的规则名称，然后单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8e377-207">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span> <span data-ttu-id="8e377-208">有关详细信息，请参阅部署文档中[Lync Server 2013 中的 "定义翻译规则](lync-server-2013-defining-translation-rules.md)"。</span><span class="sxs-lookup"><span data-stu-id="8e377-208">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="8e377-209">要复制现有的转换规则以作为定义新规则的起点，请单击相应的规则名称，再单击“复制”\*\*\*\*，然后单击“粘贴”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8e377-209">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="8e377-210">有关详细信息，请参阅[在 Lync Server 2013 中定义翻译规则](lync-server-2013-defining-translation-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="8e377-210">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span></span>
    
      - <span data-ttu-id="8e377-211">要从中继删除某个转换规则，请突出显示相应的规则名称，然后单击“删除”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8e377-211">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="8e377-212">如果已在关联的中继对等方上配置了转换规则，则不要将任何转换规则与中继相关联，因为这两种规则可能会发生冲突。</span><span class="sxs-lookup"><span data-stu-id="8e377-212">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>

    
    </div>

17. <span data-ttu-id="8e377-p131">（可选）为中继关联和配置“被叫号码转换规则”\*\*\*\*。这些转换规则适用于出站呼叫的被叫号码。</span><span class="sxs-lookup"><span data-stu-id="8e377-p131">(Optional) Associate and configure **called number translation rules** for the trunk. The translation rules apply to the called number in an outbound call.</span></span>
    
      - <span data-ttu-id="8e377-215">若要从您的企业语音部署中可用的所有翻译规则列表中选择一个或多个规则，请单击 "**选择**"。</span><span class="sxs-lookup"><span data-stu-id="8e377-215">To choose one or more rules from a list of all translation rules that are available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="8e377-216">在“选择转换规则”\*\*\*\* 中，单击要与中继关联的规则，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8e377-216">In **Select Translation Rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>
    
      - <span data-ttu-id="8e377-217">要定义新的转换规则并将其与中继相关联，请单击“新建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8e377-217">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="8e377-218">有关定义新规则的详细信息，请参阅部署文档中[Lync Server 2013 中的 "定义翻译规则](lync-server-2013-defining-translation-rules.md)"。</span><span class="sxs-lookup"><span data-stu-id="8e377-218">For details about defining a new rule, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="8e377-219">要编辑已与中继关联的转换规则，请单击相应的规则名称，然后单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8e377-219">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span> <span data-ttu-id="8e377-220">有关详细信息，请参阅部署文档中[Lync Server 2013 中的 "定义翻译规则](lync-server-2013-defining-translation-rules.md)"。</span><span class="sxs-lookup"><span data-stu-id="8e377-220">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="8e377-221">要复制现有的转换规则以作为定义新规则的起点，请单击相应的规则名称，再单击“复制”\*\*\*\*，然后单击“粘贴”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8e377-221">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="8e377-222">有关详细信息，请参阅[在 Lync Server 2013 中定义翻译规则](lync-server-2013-defining-translation-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="8e377-222">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span></span>
    
      - <span data-ttu-id="8e377-223">要从中继删除某个转换规则，请突出显示相应的规则名称，然后单击“删除”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8e377-223">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="8e377-224">如果已在关联的中继对等方上配置了转换规则，则不要将任何转换规则与中继相关联，因为这两种规则可能会发生冲突。</span><span class="sxs-lookup"><span data-stu-id="8e377-224">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>

    
    </div>

18. <span data-ttu-id="8e377-p136">确保中继的转换规则按正确的顺序排列。要更改规则在列表中的位置，请突出显示相应的规则名称，然后单击向上箭头或向下箭头。</span><span class="sxs-lookup"><span data-stu-id="8e377-p136">Make sure that the trunk’s translation rules are arranged in the correct order. To change a rule’s position in the list, highlight the rule name and then click the up or down arrow.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="8e377-227">Lync Server 2013 从上到下遍历翻译规则列表，并使用与所拨号码匹配的第一个规则。</span><span class="sxs-lookup"><span data-stu-id="8e377-227">Lync Server 2013 traverses the translation rule list from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="8e377-228">如果要配置中继以使拨打号码可以匹配多个转换规则，则确保限制较严格的规则排在限制较宽松的规则上方。</span><span class="sxs-lookup"><span data-stu-id="8e377-228">If you configure a trunk so that a dialed number can match more than one translation rule, be sure that the more restrictive rules are sorted above the less restrictive rules.</span></span> <span data-ttu-id="8e377-229">例如，如果具有与任何 11 位数字相匹配的转换规则和只与以 +1425 开头的 11 位数字相匹配的转换规则，则确保与任何 11 位数字相匹配的规则排在更加严格的规则<EM>下方</EM>。</span><span class="sxs-lookup"><span data-stu-id="8e377-229">For example, if you have included a translation rule that matches any 11-digit number and a translation rule that matches only 11-digit numbers that start with +1425, be sure that the rule that matches any 11-digit number is sorted <EM>below</EM> the more restrictive rule.</span></span>

    
    </div>

19. <span data-ttu-id="8e377-230">完成中继的配置后，单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8e377-230">When you are finished configuring the trunk, click **OK**.</span></span>

20. <span data-ttu-id="8e377-231">在“Trunk 配置”\*\*\*\* 页上，单击“提交”\*\*\*\*，然后单击“全部提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8e377-231">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8e377-232">任何时候创建或修改中继配置，都必须运行“全部提交”<STRONG></STRONG>命令以发布配置更改。</span><span class="sxs-lookup"><span data-stu-id="8e377-232">Whenever you create or modify a trunk configuration, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="8e377-233">有关详细信息，请参阅操作文档中的<A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 中的 "发布待处理的语音路由配置更改"</A> 。</span><span class="sxs-lookup"><span data-stu-id="8e377-233">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

<span data-ttu-id="8e377-234">配置主干后，通过选择全局媒体绕过选项来继续配置 "绕过媒体"，如部署文档中[Lync Server 2013 中的全局媒体旁路选项](lync-server-2013-global-media-bypass-options.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="8e377-234">After you have configured the trunk, continue configuring media bypass by choosing between global media bypass options, as described in [Global media bypass options in Lync Server 2013](lync-server-2013-global-media-bypass-options.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8e377-235">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8e377-235">See Also</span></span>


[<span data-ttu-id="8e377-236">在 Lync Server 2013 中配置不使用 "媒体旁路" 的主干</span><span class="sxs-lookup"><span data-stu-id="8e377-236">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)  


[<span data-ttu-id="8e377-237">在 Lync Server 2013 中配置媒体绕过</span><span class="sxs-lookup"><span data-stu-id="8e377-237">Configure media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-media-bypass.md)  
[<span data-ttu-id="8e377-238">Lync Server 2013 中的全局媒体绕过选项</span><span class="sxs-lookup"><span data-stu-id="8e377-238">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  


[<span data-ttu-id="8e377-239">在 Lync Server 2013 中定义转换规则</span><span class="sxs-lookup"><span data-stu-id="8e377-239">Defining translation rules in Lync Server 2013</span></span>](lync-server-2013-defining-translation-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

