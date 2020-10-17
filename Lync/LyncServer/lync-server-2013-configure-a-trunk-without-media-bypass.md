---
title: Lync Server 2013：配置不使用媒体旁路的中继
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a trunk without media bypass
ms:assetid: 3422e93e-7bd2-4470-968c-dc38345b18ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425831(v=OCS.15)
ms:contentKeyID: 48183825
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8fce45563538b41773f76a8733b1c226454e6f76
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523119"
---
# <a name="configure-a-trunk-without-media-bypass-in-lync-server-2013"></a><span data-ttu-id="155c8-102">在 Lync Server 2013 中配置无媒体旁路功能的中继</span><span class="sxs-lookup"><span data-stu-id="155c8-102">Configure a trunk without media bypass in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="155c8-103">_**上次修改的主题：** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="155c8-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="155c8-104">如果要配置禁用媒体旁路功能的中继，请执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="155c8-104">If you want to configure a trunk with media bypass disabled, follow these steps.</span></span> <span data-ttu-id="155c8-105">如果要配置启用了媒体旁路的中继，请参阅 [在 Lync Server 2013 中配置具有媒体旁路的中继](lync-server-2013-configure-a-trunk-with-media-bypass.md)。</span><span class="sxs-lookup"><span data-stu-id="155c8-105">If you want to configure a trunk with media bypass enabled, see [Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md).</span></span>

<span data-ttu-id="155c8-p102">如下所述，中继配置可对应用于已分配此中继配置的中继的一组参数进行分组。特定中继配置的作用域可以是全局中继（针对没有更多特定站点或池配置的所有中继）、站点或者池。池级中继配置用于将特定中继配置的作用域限制为单个中继。</span><span class="sxs-lookup"><span data-stu-id="155c8-p102">A trunk configuration, as described below, groups a set of parameters that are applied to trunks assigned this trunk configuration. A particular trunk configuration can be scoped globally (to all trunks that do not have more specific site or pool configuration), or to a site, or to a pool. The pool-level trunk configuration is used to scope a specific trunk configuration to a single trunk.</span></span>

<span id="BKMK_ConfigTrunkGenericSteps"></span>

<div>

## <a name="to-configure-a-trunk-without-media-bypass"></a><span data-ttu-id="155c8-109">配置无媒体旁路功能的中继</span><span class="sxs-lookup"><span data-stu-id="155c8-109">To configure a trunk without media bypass</span></span>

1.  <span data-ttu-id="155c8-110">以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。</span><span class="sxs-lookup"><span data-stu-id="155c8-110">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="155c8-111">有关详细信息，请参阅 [Lync Server 2013 中的委派安装权限](lync-server-2013-delegate-setup-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="155c8-111">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="155c8-112">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="155c8-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="155c8-113">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="155c8-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="155c8-114">在左侧导航栏中，单击“语音路由”\*\*\*\*，然后单击“Trunk 配置”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="155c8-114">In the left navigation bar, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

4.  <span data-ttu-id="155c8-115">在“Trunk 配置”\*\*\*\* 页上，使用以下方法之一配置中继：</span><span class="sxs-lookup"><span data-stu-id="155c8-115">On the **Trunk Configuration** page, use one of the following methods to configure a trunk:</span></span>
    
      - <span data-ttu-id="155c8-116">双击某个现有的中继（例如“全局”\*\*\*\* 中继）以显示“编辑 Trunk 配置”\*\*\*\* 对话框。</span><span class="sxs-lookup"><span data-stu-id="155c8-116">Double-click an existing trunk (for example, the **Global** trunk) to display the **Edit Trunk Configuration** dialog box.</span></span>
    
      - <span data-ttu-id="155c8-117">单击“新建”\*\*\*\*，然后为新的中继配置选择作用域：</span><span class="sxs-lookup"><span data-stu-id="155c8-117">Click **New**, and then select a scope for the new trunk configuration:</span></span>
        
          - <span data-ttu-id="155c8-118">**站点中继：** 在 " **选择网站** " 中选择此中继配置的网站，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="155c8-118">**Site trunk:** Choose the site for this trunk configuration in **Select a Site** , and then click **OK**.</span></span> <span data-ttu-id="155c8-119">请注意，如果已经为站点创建了中继配置，则该站点不会显示在“选择站点”\*\*\*\* 中。</span><span class="sxs-lookup"><span data-stu-id="155c8-119">Note that if a trunk configuration has already been created for a site, the site does not appear in **Select a Site**.</span></span> <span data-ttu-id="155c8-120">此中继配置将应用于站点中的所有中继。</span><span class="sxs-lookup"><span data-stu-id="155c8-120">This trunk configuration will be applied to all trunks in the site.</span></span>
        
          - <span data-ttu-id="155c8-121">**池中继：** 在 " **选择服务** " 中选择要应用此中继配置的中继的名称，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="155c8-121">**Pool trunk:** Choose the name of the trunk that this trunk configuration applies to in **Select a Service** and click **OK**.</span></span> <span data-ttu-id="155c8-122">此中继可以是根中继，也可以是拓扑生成器中定义的任何其他中继。</span><span class="sxs-lookup"><span data-stu-id="155c8-122">This trunk can be the root trunk, or any additional trunks defined in Topology Builder.</span></span> <span data-ttu-id="155c8-123">请注意，如果已经为特定中继创建了中继配置，则该中继不会显示在“选择服务”\*\*\*\* 中。</span><span class="sxs-lookup"><span data-stu-id="155c8-123">Note that if a trunk configuration has already been created for a specific trunk, the trunk does not appear in **Select a Service**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="155c8-124">选择中继配置的作用域后，无法对其进行更改。</span><span class="sxs-lookup"><span data-stu-id="155c8-124">After you select the scope of the trunk configuration, it cannot be changed.</span></span><BR><span data-ttu-id="155c8-125">“名称”<STRONG></STRONG>字段将使用中继配置的关联站点或服务的名称进行预填充，且不能更改。</span><span class="sxs-lookup"><span data-stu-id="155c8-125">The <STRONG>Name</STRONG> field is prepopulated with the name of the trunk configuration’s associated site or service and cannot be changed.</span></span>

    
    </div>

5.  <span data-ttu-id="155c8-126">选择以下“加密支持级别”\*\*\*\* 选项之一：</span><span class="sxs-lookup"><span data-stu-id="155c8-126">Select one of the following **Encryption support level** options:</span></span>
    
      - <span data-ttu-id="155c8-127">**必需：** 安全实时传输协议 (SRTP) 加密必须用于帮助保护中介服务器与网关或专用分支 exchange (PBX) 之间的流量。</span><span class="sxs-lookup"><span data-stu-id="155c8-127">**Required:** Secure real-time transport protocol (SRTP) encryption must be used to help protect traffic between the Mediation Server and the gateway or private branch exchange (PBX).</span></span>
    
      - <span data-ttu-id="155c8-128">**可选：** 如果服务提供商或设备制造商支持，则使用 SRTP 加密。</span><span class="sxs-lookup"><span data-stu-id="155c8-128">**Optional:** SRTP encryption will be used if the service provider or equipment manufacturer supports it.</span></span>
    
      - <span data-ttu-id="155c8-129">**不支持：** SRTP 加密不受服务提供商或设备制造商支持，因此不会使用。</span><span class="sxs-lookup"><span data-stu-id="155c8-129">**Not Supported:** SRTP encryption is not supported by the service provider or equipment manufacturer and therefore will not be used.</span></span>

6.  <span data-ttu-id="155c8-130">确保已清除“启用媒体旁路”\*\*\*\* 复选框。</span><span class="sxs-lookup"><span data-stu-id="155c8-130">Be sure that the **Enable media bypass** check box is cleared.</span></span>

7.  <span data-ttu-id="155c8-p107">如果存在一个已知的媒体端点（例如公用电话交换网 (PSTN) 网关，其中媒体终端与信号终端具有相同的 IP），则选中“集中式媒体处理”\*\*\*\* 复选框。如果中继没有已知的媒体端点，则清除该复选框。</span><span class="sxs-lookup"><span data-stu-id="155c8-p107">Select the **Centralized media processing** check box if there is a well-known media termination point (for example, a public switched telephone network (PSTN) gateway where the media termination has the same IP as the signaling termination). Clear this check box if the trunk does not have a well-known media termination point.</span></span>

8.  <span data-ttu-id="155c8-133">如果中继对等方支持接收来自中介服务器的 SIP 引用请求，请选中 " **启用发送引用到网关"** 复选框。</span><span class="sxs-lookup"><span data-stu-id="155c8-133">If the trunk peer supports receiving SIP REFER requests from the Mediation Server, select the **Enable sending refer to the gateway** check box.</span></span>

9.  <span data-ttu-id="155c8-p108">（可选）若要启用中继间路由，请对此中继配置关联和配置 PSTN 用法记录。与此中继配置关联的 PSTN 用法将通过源自 Lync 终结点以外终结点的中继应用于所有传入呼叫。若要管理与中继配置关联的 PSTN 用法记录，请使用以下方法之一：</span><span class="sxs-lookup"><span data-stu-id="155c8-p108">(Optional) To enable inter-trunk routing, associate and configure PSTN usage records to this trunk configuration. The PSTN usages associated to this trunk configuration will be applied for all incoming calls through the trunk that is not originating from a Lync endpoint. To manage PSTN usage records associated to a trunk configuration, use one of the following methods:</span></span>
    
      - <span data-ttu-id="155c8-137">若要从企业语音部署中提供的所有 PSTN 用法记录列表中选择一个或多个记录，请单击 " **选择**"。</span><span class="sxs-lookup"><span data-stu-id="155c8-137">To select one or more records from a list of all PSTN usage records available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="155c8-138">突出显示要与此中继配置关联的记录，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="155c8-138">Highlight the records you want to associate with this trunk configuration and then click **OK**.</span></span>
    
      - <span data-ttu-id="155c8-139">要删除此中继配置中的某个 PSTN 用法记录，请选择相应的记录，然后单击“删除”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="155c8-139">To remove a PSTN usage record from this trunk configuration, select the record and click **Remove**.</span></span>
    
      - <span data-ttu-id="155c8-140">要定义新的 PSTN 用法记录并将其与此中继配置相关联，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="155c8-140">To define a new PSTN usage record and associate it with this trunk configuration, do the following:</span></span>
        
        1.  <span data-ttu-id="155c8-141">单击“新建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="155c8-141">Click **New**.</span></span>
        
        2.  <span data-ttu-id="155c8-142">在“名称”\*\*\*\* 字段中，指定记录的唯一描述性名称。</span><span class="sxs-lookup"><span data-stu-id="155c8-142">In the **Name** field, specify a descriptive name for the record that is unique.</span></span>
            
            <div>
            

            > [!NOTE]  
            > <span data-ttu-id="155c8-p110">PSTN 用法记录名称在企业语音部署中必须是唯一的。保存记录后，将无法编辑“名称”<STRONG></STRONG>字段。</span><span class="sxs-lookup"><span data-stu-id="155c8-p110">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the <STRONG>Name</STRONG> field cannot be edited.</span></span>

            
            </div>
        
        3.  <span data-ttu-id="155c8-145">使用以下方法之一为此 PSTN 用法记录关联和配置路由：</span><span class="sxs-lookup"><span data-stu-id="155c8-145">Use one of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="155c8-146">若要从企业语音部署中的所有可用路由列表中选择一个或多个路由，请单击 " **选择**"。</span><span class="sxs-lookup"><span data-stu-id="155c8-146">To select one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="155c8-147">突出显示要与此 PSTN 用法记录相关联的路由，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="155c8-147">Highlight the routes you want to associate with this PSTN usage record, and click **OK**.</span></span>
            
              - <span data-ttu-id="155c8-148">要删除 PSTN 用法记录中的某个路由，请选择相应的路由，然后单击“删除”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="155c8-148">To remove a route from the PSTN usage record, select the route, and click **Remove**.</span></span>
            
              - <span data-ttu-id="155c8-149">要定义新路由并将其与此 PSTN 用法记录相关联，请单击“新建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="155c8-149">To define a new route and associate it to this PSTN usage record, click **New**.</span></span> <span data-ttu-id="155c8-150">有关详细信息，请参阅 [在 Lync Server 2013 中创建语音路由](lync-server-2013-create-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="155c8-150">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="155c8-151">要编辑与此 PSTN 用法记录相关联的路由，请选择相应的路由，然后单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="155c8-151">To edit a route that is associated with this PSTN usage record, select the route, and click **Show details**.</span></span> <span data-ttu-id="155c8-152">有关详细信息，请参阅 [在 Lync Server 2013 中修改语音路由](lync-server-2013-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="155c8-152">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        4.  <span data-ttu-id="155c8-153">单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="155c8-153">Click **OK**.</span></span>
    
      - <span data-ttu-id="155c8-154">要编辑已经与此中继配置相关联的 PSTN 用法记录，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="155c8-154">To edit a PSTN usage record that is already associated with this trunk configuration, do the following:</span></span>
        
        1.  <span data-ttu-id="155c8-155">选择要编辑的 PSTN 用法记录，然后单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="155c8-155">Select the PSTN usage record you want to edit, and click **Show details**.</span></span>
        
        2.  <span data-ttu-id="155c8-156">使用以下方法之一为此 PSTN 用法记录关联和配置路由：</span><span class="sxs-lookup"><span data-stu-id="155c8-156">Use one of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="155c8-157">若要从企业语音部署中的所有可用路由列表中选择一个或多个路由，请单击 " **选择**"。</span><span class="sxs-lookup"><span data-stu-id="155c8-157">To select one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="155c8-158">突出显示要与此 PSTN 用法记录相关联的路由，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="155c8-158">Highlight the routes you want to associate with this PSTN usage record, and click **OK**.</span></span>
            
              - <span data-ttu-id="155c8-159">要删除 PSTN 用法记录中的某个路由，请选择相应的路由，然后单击“删除”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="155c8-159">To remove a route from the PSTN usage record, select the route, and click **Remove**.</span></span>
            
              - <span data-ttu-id="155c8-160">要定义新路由并将其与此 PSTN 用法记录相关联，请单击“新建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="155c8-160">To define a new route and associate it to this PSTN usage record, click **New**.</span></span> <span data-ttu-id="155c8-161">有关详细信息，请参阅 [在 Lync Server 2013 中创建语音路由](lync-server-2013-create-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="155c8-161">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="155c8-162">要编辑与此 PSTN 用法记录相关联的路由，请选择相应的路由，然后单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="155c8-162">To edit a route that is associated with this PSTN usage record, select the route, and click **Show details**.</span></span> <span data-ttu-id="155c8-163">有关详细信息，请参阅 [在 Lync Server 2013 中修改语音路由](lync-server-2013-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="155c8-163">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        3.  <span data-ttu-id="155c8-164">单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="155c8-164">Click **OK**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="155c8-165">根据与要配置的中继关联的中介服务器对，关联 PSTN 用法记录非常重要。</span><span class="sxs-lookup"><span data-stu-id="155c8-165">It important to associate PSTN usage records according to the Mediation Server peer that is associated to the trunk being configured.</span></span> <span data-ttu-id="155c8-166">如果中介服务器对等是 PSTN 网关或会话边界控制器 (SBC) ，强烈建议不要将中继配置与路由到 PSTN 目标的 PSTN 使用记录或通过 Lync Server 连接的任何其他下游系统相关联。</span><span class="sxs-lookup"><span data-stu-id="155c8-166">If the Mediation Server peer is a PSTN gateway or a Session Border Controller (SBC), it is strongly recommended that the trunk configuration is not associated to a PSTN usage record that routes to a PSTN destination or any other downstream systems connected via Lync Server.</span></span>

    
    </div>

10. <span data-ttu-id="155c8-p118">排列 PSTN 用法记录可获得最佳性能。要更改记录在列表中的位置，请选择 PSTN 用法记录，然后单击向上或向下箭头。</span><span class="sxs-lookup"><span data-stu-id="155c8-p118">Arrange the PSTN usage records for optimum performance. To change a record’s position in the list, select the PSTN usage record, and click the up or down arrows.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="155c8-169">PSTN 用法记录在中继配置中的列出顺序十分重要。</span><span class="sxs-lookup"><span data-stu-id="155c8-169">The order in which PSTN usage records are listed in the trunk configuration is significant.</span></span> <span data-ttu-id="155c8-170">Lync Server 从上到下遍历列表。</span><span class="sxs-lookup"><span data-stu-id="155c8-170">Lync Server traverses the list from top to down.</span></span>

    
    </div>

11. <span data-ttu-id="155c8-171">应选择“启用 RTP 闭锁”\*\*\*\*，以便为 NAT 或防火墙之后的客户端以及支持闭锁的 SBC 启用媒体旁路。</span><span class="sxs-lookup"><span data-stu-id="155c8-171">**Enable RTP Latching** should be selected to enable bypass media for clients behind a NAT or firewall and an SBC that supports latching.</span></span>

12. <span data-ttu-id="155c8-172">应选择 "**启用转接呼叫历史记录**"，以允许向中介服务器的网关对等方发送呼叫历史记录信息。</span><span class="sxs-lookup"><span data-stu-id="155c8-172">**Enable forward call history** should be selected to enable sending of call history information to the gateway peer of the Mediation Server.</span></span>

13. <span data-ttu-id="155c8-173">应选择 "**启用前向 P 声明标识数据**" 以使 PAI 呼叫发起人信息能够在中介服务器端和网关端之间转发 (，反之亦然) （如果存在）。</span><span class="sxs-lookup"><span data-stu-id="155c8-173">**Enable forward P-Asserted-Identity data** should be selected to enable PAI call originator information to be forwarded between the Mediation Server side and gateway side (and vice versa), when present.</span></span>

14. <span data-ttu-id="155c8-174">应选择“启用出站路由故障转移计时器”\*\*\*\* 以支持快速故障转移。</span><span class="sxs-lookup"><span data-stu-id="155c8-174">**Enable outbound routing failover timer** should be selected to enable fast failover.</span></span> <span data-ttu-id="155c8-175">与此中继关联的网关可以在 10 秒内发出正在处理出站呼叫的通知。</span><span class="sxs-lookup"><span data-stu-id="155c8-175">The gateway associated with this trunk can give notification within 10 seconds that it is processing an outbound call.</span></span> <span data-ttu-id="155c8-176">如果中介服务器未收到此通知，则将重新路由到另一个中继。</span><span class="sxs-lookup"><span data-stu-id="155c8-176">Rerouting to another trunk will occur if this notification is not received by the Mediation Server.</span></span> <span data-ttu-id="155c8-177">在延迟设置可能延迟响应时间或网关需要 10 秒以上时间进行响应的网络中，应禁用快速故障转移。</span><span class="sxs-lookup"><span data-stu-id="155c8-177">On networks where latency may delay the response time or the gateway takes longer than 10 seconds to respond, the fast failover should be disabled.</span></span>

15. <span data-ttu-id="155c8-178">（可选）关联和配置中继的“呼叫号码转换规则”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="155c8-178">(Optional) Associate and configure **calling number translation rules** for the trunk.</span></span> <span data-ttu-id="155c8-179">这些转换规则适用于出站呼叫的呼叫号码</span><span class="sxs-lookup"><span data-stu-id="155c8-179">These translation rules apply to the calling number for outbound calls</span></span>
    
      - <span data-ttu-id="155c8-180">若要从企业语音部署中可用的所有转换规则列表中选择一个或多个规则，请单击 " **选择**"。</span><span class="sxs-lookup"><span data-stu-id="155c8-180">To choose one or more rules from a list of all translation rules that are available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="155c8-181">在“选择转换规则”\*\*\*\* 中，单击要与中继关联的规则，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="155c8-181">In **Select Translation Rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>
    
      - <span data-ttu-id="155c8-182">要定义新的转换规则并将其与中继关联，请单击“新建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="155c8-182">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="155c8-183">有关定义新规则的详细信息，请参阅部署文档中的 [在 Lync Server 2013 中定义转换规则](lync-server-2013-defining-translation-rules.md) 。</span><span class="sxs-lookup"><span data-stu-id="155c8-183">For details about defining a new rule, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="155c8-184">要编辑已经与中继关联的转换规则，请单击相应的规则名称，然后单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="155c8-184">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span> <span data-ttu-id="155c8-185">有关详细信息，请参阅部署文档中的 [在 Lync Server 2013 中定义转换规则](lync-server-2013-defining-translation-rules.md) 。</span><span class="sxs-lookup"><span data-stu-id="155c8-185">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="155c8-186">要复制现有的转换规则以作为定义新规则的起点，请单击相应的规则名称，再单击“复制”\*\*\*\*，然后单击“粘贴”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="155c8-186">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="155c8-187">有关详细信息，请参阅 [在 Lync Server 2013 中定义转换规则](lync-server-2013-defining-translation-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="155c8-187">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span></span>
    
      - <span data-ttu-id="155c8-188">要从中继中删除某个转换规则，请突出显示相应的规则名称，然后单击“删除”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="155c8-188">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398321.security(OCS.15).gif" title="保护" alt="security" /><span data-ttu-id="155c8-190">安全说明：</span><span class="sxs-lookup"><span data-stu-id="155c8-190">Security Note:</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><span data-ttu-id="155c8-191">如果已在关联的中继对等方上配置了转换规则，则不要将任何转换规则与中继相关联，因为这两种规则可能会发生冲突。</span><span class="sxs-lookup"><span data-stu-id="155c8-191">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span></td>
    </tr>
    </tbody>
    </table>
    
    </div>

16. <span data-ttu-id="155c8-p126">（可选）关联和配置中继的“已呼叫号码转换规则”\*\*\*\*。这些转换规则适用于出站呼叫中的已呼叫号码。</span><span class="sxs-lookup"><span data-stu-id="155c8-p126">(Optional) Associate and configure **called number translation rules** for the trunk. The translation rules apply to the called number in an outbound call.</span></span>
    
      - <span data-ttu-id="155c8-194">若要从企业语音部署中可用的所有转换规则列表中选择一个或多个规则，请单击 " **选择**"。</span><span class="sxs-lookup"><span data-stu-id="155c8-194">To choose one or more rules from a list of all translation rules that are available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="155c8-195">在“选择转换规则”\*\*\*\* 中，单击要与中继关联的规则，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="155c8-195">In **Select Translation Rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>
    
      - <span data-ttu-id="155c8-196">要定义新的转换规则并将其与中继关联，请单击“新建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="155c8-196">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="155c8-197">有关定义新规则的详细信息，请参阅部署文档中的 [在 Lync Server 2013 中定义转换规则](lync-server-2013-defining-translation-rules.md) 。</span><span class="sxs-lookup"><span data-stu-id="155c8-197">For details about defining a new rule, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="155c8-198">要编辑已经与中继关联的转换规则，请单击相应的规则名称，然后单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="155c8-198">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span> <span data-ttu-id="155c8-199">有关详细信息，请参阅部署文档中的 [在 Lync Server 2013 中定义转换规则](lync-server-2013-defining-translation-rules.md) 。</span><span class="sxs-lookup"><span data-stu-id="155c8-199">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="155c8-200">要复制现有的转换规则以作为定义新规则的起点，请单击相应的规则名称，再单击“复制”\*\*\*\*，然后单击“粘贴”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="155c8-200">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="155c8-201">有关详细信息，请参阅 [在 Lync Server 2013 中定义转换规则](lync-server-2013-defining-translation-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="155c8-201">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span></span>
    
      - <span data-ttu-id="155c8-202">要从中继中删除某个转换规则，请突出显示相应的规则名称，然后单击“删除”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="155c8-202">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="155c8-203">如果已在关联的中继对等方上配置了转换规则，则不要将任何转换规则与中继相关联，因为这两种规则可能会发生冲突。</span><span class="sxs-lookup"><span data-stu-id="155c8-203">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>

    
    </div>

17. <span data-ttu-id="155c8-204">请确保该中继的转换规则按正确的顺序排列。</span><span class="sxs-lookup"><span data-stu-id="155c8-204">Make sure that the trunk’s translation rules are arranged in the correct order.</span></span> <span data-ttu-id="155c8-205">要更改规则在列表中的位置，请突出显示相应的规则名称，然后单击向上或向下箭头。</span><span class="sxs-lookup"><span data-stu-id="155c8-205">To change a rule’s position in the list, highlight the rule name, and then click the up or down arrow.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="155c8-206">Lync Server 从上到下遍历转换规则列表，并使用第一个与拨打的号码相匹配的规则。</span><span class="sxs-lookup"><span data-stu-id="155c8-206">Lync Server traverses the translation rule list from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="155c8-207">如果要配置中继以使拨打号码可以匹配多个转换规则，请确保限制较严格的规则排在限制较宽松的规则上方。</span><span class="sxs-lookup"><span data-stu-id="155c8-207">If you configure a trunk so that a dialed number can match more than one translation rule, be sure that the more restrictive rules are sorted above the less restrictive rules.</span></span> <span data-ttu-id="155c8-208">例如，如果具有与任何 11 位数字相匹配的转换规则和只与以 +1425 开头的 11 位数字相匹配的转换规则，请确保与任何 11 位数字相匹配的规则排在更加严格的规则<EM>下方</EM>。</span><span class="sxs-lookup"><span data-stu-id="155c8-208">For example, if you have included a translation rule that matches any 11-digit number and a translation rule that matches only 11-digit numbers that start with +1425, be sure that the rule that matches any 11-digit number is sorted <EM>below</EM> the more restrictive rule.</span></span>

    
    </div>

18. <span data-ttu-id="155c8-209">完成中继的配置后，单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="155c8-209">When you are finished configuring the trunk, click **OK**.</span></span>

19. <span data-ttu-id="155c8-210">在“Trunk 配置”\*\*\*\* 页上，单击“提交”\*\*\*\*，然后单击“全部提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="155c8-210">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="155c8-211">任何时候创建或修改中继配置，都必须运行“全部提交”<STRONG></STRONG>命令以发布配置更改。</span><span class="sxs-lookup"><span data-stu-id="155c8-211">Whenever you create or modify a trunk configuration, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="155c8-212">有关详细信息，请参阅操作文档中的在 <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 中发布待处理的语音路由配置的更改</A> 。</span><span class="sxs-lookup"><span data-stu-id="155c8-212">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="155c8-213">另请参阅</span><span class="sxs-lookup"><span data-stu-id="155c8-213">See Also</span></span>


[<span data-ttu-id="155c8-214">在 Lync Server 2013 中配置具有媒体旁路功能的中继</span><span class="sxs-lookup"><span data-stu-id="155c8-214">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  


[<span data-ttu-id="155c8-215">在 Lync Server 2013 中定义转换规则</span><span class="sxs-lookup"><span data-stu-id="155c8-215">Defining translation rules in Lync Server 2013</span></span>](lync-server-2013-defining-translation-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

