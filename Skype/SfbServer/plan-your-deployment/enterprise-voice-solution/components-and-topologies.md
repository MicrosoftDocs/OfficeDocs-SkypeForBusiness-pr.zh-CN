---
title: 组件和拓扑的呼叫允许控制的 Skype for Business
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0beec6be-2431-4255-a3d2-512dd030e66a
description: 在有 MPLS 网络、SIP 中继或第三方 PSTN 网关或 PBX 情况下，规划呼叫允许控制 (CAC)。 适用于 Skype 业务 Server 企业语音。
ms.openlocfilehash: d08d5ca63c02a2ddf12f3f53a5e4952a7a366a71
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "20977705"
---
# <a name="components-and-topologies-for-call-admission-control-in-skype-for-business"></a><span data-ttu-id="6f0e8-104">组件和拓扑的呼叫允许控制的 Skype for Business</span><span class="sxs-lookup"><span data-stu-id="6f0e8-104">Components and topologies for call admission control in Skype for Business</span></span>
 
<span data-ttu-id="6f0e8-105">在有 MPLS 网络、SIP 中继或第三方 PSTN 网关或 PBX 情况下，规划呼叫允许控制 (CAC)。</span><span class="sxs-lookup"><span data-stu-id="6f0e8-105">Planning for call admission control (CAC) if you have an MPLS network, a SIP trunk, or a third-party PSTN gateway or PBX.</span></span> <span data-ttu-id="6f0e8-106">适用于 Skype 业务 Server 企业语音。</span><span class="sxs-lookup"><span data-stu-id="6f0e8-106">Applies to Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="6f0e8-107">本节中的主题提供了有关通过各种类型的网络拓扑部署呼叫允许控制 (CAC) 的特殊注意事项的信息。</span><span class="sxs-lookup"><span data-stu-id="6f0e8-107">The topics in this section provide information about special considerations for deploying call admission control (CAC) with various types of network topologies.</span></span>
  
## <a name="call-admission-control-on-an-mpls-network"></a><span data-ttu-id="6f0e8-108">MPLS 网络上的呼叫允许控制</span><span class="sxs-lookup"><span data-stu-id="6f0e8-108">Call admission control on an MPLS network</span></span>

<span data-ttu-id="6f0e8-p103">在多协议标签交换 (MPLS) 网络中，所有站点均以全连通的方式连接。也就是说，所有站点都直接连接到 Internet 服务提供商的 MPLS 主干线，并且每个站点都设置了带宽，以用于通过 WAN 链路连接到 MPLS 云。没有控制 IP 路由的网络集线器或中心站点。下图显示了基于 MPLS 技术的简单网络。</span><span class="sxs-lookup"><span data-stu-id="6f0e8-p103">In a Multiprotocol Label Switching (MPLS) network, all sites are connected by a full-mesh. That is, all sites are connected directly to the MPLS backbone of the Internet service provider, and each site is provisioned bandwidth to be used across a WAN link to the MPLS cloud. There is no network hub or central site to control IP routing. The following figure shows a simple network based on MPLS technology.</span></span>
  
<span data-ttu-id="6f0e8-113">**MPLS 网络示例**</span><span class="sxs-lookup"><span data-stu-id="6f0e8-113">**Example MPLS network**</span></span>

![使用 MPLS 的 CAC](../../media/CAC_MPLS_1.jpg)
  
<span data-ttu-id="6f0e8-p104">要在 MPLS 网络中部署呼叫允许控制 (CAC)，需创建代表 MPLS 云的网络区域，以及代表每个 MPLS 分支站点的网络站点。下图说明如何配置代表上图中的示例 MPLS 网络的网络区域和网络站点。之后，总体带宽限制和带宽会话限制将取决于从每个网络站点连接到代表 MPLS 云的网络区域的 WAN 链路容量。</span><span class="sxs-lookup"><span data-stu-id="6f0e8-p104">To deploy call admission control (CAC) in an MPLS network, you create a network region to represent the MPLS cloud, and create a network site to represent each MPLS satellite site. The following figure illustrates how the network region and network sites should be configured to represent the example MPLS network in the previous figure. The overall bandwidth limits and bandwidth session limits are then based on the capacity of the WAN link from each network site to the network region that represents the MPLS cloud.</span></span>
  
<span data-ttu-id="6f0e8-118">**MPLS 网络的网络区域和网络站点**</span><span class="sxs-lookup"><span data-stu-id="6f0e8-118">**Network region and network sites for an MPLS network**</span></span>

![使用 MPLS 的呼叫允许控制 (CAC) 图](../../media/CAC_MPLS_2.jpg)
  
## <a name="call-admission-control-on-a-sip-trunk"></a><span data-ttu-id="6f0e8-120">SIP 中继上的呼叫允许控制</span><span class="sxs-lookup"><span data-stu-id="6f0e8-120">Call admission control on a SIP trunk</span></span>

<span data-ttu-id="6f0e8-p105">要在 SIP 中继上部署呼叫允许控制 (CAC)，请创建一个代表 Internet 电话服务提供商 (ITSP) 的网络站点。要在 SIP 中继上应用带宽策略值，请创建一个企业内部网络站点和所创建的用于代表 ITSP 的网络站点之间的站点间策略。</span><span class="sxs-lookup"><span data-stu-id="6f0e8-p105">To deploy call admission control (CAC) on a SIP trunk, you create a network site to represent the Internet telephony service provider (ITSP). To apply bandwidth policy values on the SIP trunk, you create an inter-site policy between the network site in your enterprise and the network site that you create to represent the ITSP.</span></span>
  
<span data-ttu-id="6f0e8-123">下图显示 SIP 中继上的 CAC 部署示例。</span><span class="sxs-lookup"><span data-stu-id="6f0e8-123">The following figure shows an example CAC deployment on a SIP trunk.</span></span>
  
<span data-ttu-id="6f0e8-124">**SIP 中继上的 CAC 配置**</span><span class="sxs-lookup"><span data-stu-id="6f0e8-124">**CAC configuration on a SIP trunk**</span></span>

![呼叫允许控制 SIP 中继图](../../media/CAC_SIP_trunk_1.jpg)
  
<span data-ttu-id="6f0e8-126">要在 SIP 中继上配置 CAC，必须在 CAC 部署过程中执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="6f0e8-126">To configure CAC on a SIP trunk, you will have to perform the following tasks during CAC deployment:</span></span>
  
1. <span data-ttu-id="6f0e8-127">创建一个网络站点，代表 ITSP。</span><span class="sxs-lookup"><span data-stu-id="6f0e8-127">Create a network site to represent the ITSP.</span></span> <span data-ttu-id="6f0e8-128">将网络站点与相应的网络区域相关联，然后为该网络站点的音频和视频分配零带宽。</span><span class="sxs-lookup"><span data-stu-id="6f0e8-128">Associate the network site to an appropriate network region, and allocate bandwidth of zero for audio and video for this network site.</span></span> <span data-ttu-id="6f0e8-129">有关详细信息，请参阅部署文档中的[cac 配置网络站点](http://technet.microsoft.com/library/afcea38f-5789-45ec-97af-c6e38364950c.aspx)。</span><span class="sxs-lookup"><span data-stu-id="6f0e8-129">For details, see [Configure Network Sites for CAC](http://technet.microsoft.com/library/afcea38f-5789-45ec-97af-c6e38364950c.aspx) in the Deployment documentation.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="6f0e8-p107">对于 ITSP，该网络站点配置不起作用。带宽策略值实际是在步骤 2 中应用。</span><span class="sxs-lookup"><span data-stu-id="6f0e8-p107">For the ITSP, this network site configuration is not functional. Bandwidth policy values are actually applied in step 2.</span></span> 
  
2. <span data-ttu-id="6f0e8-132">使用在步骤 1 中创建的站点的相关参数值，为 SIP 中继创建站点间链接。</span><span class="sxs-lookup"><span data-stu-id="6f0e8-132">Create an inter-site link for the SIP trunk using the relevant parameter values for the site you created in step 1.</span></span> <span data-ttu-id="6f0e8-133">例如，使用企业中的网络站点名称作为参数 NetworkSiteID1 的值，并使用 ITSP 网络站点名称作为参数 NetworkSiteID2 的值。</span><span class="sxs-lookup"><span data-stu-id="6f0e8-133">For example, use the name of the network site in your enterprise as the value of the NetworkSiteID1 parameter, and the ITSP network site as the value of the NetworkSiteID2 parameter.</span></span> <span data-ttu-id="6f0e8-134">有关详细信息，请参阅部署文档中[新建 CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps)的[Skype 业务服务器中的创建网络站点间策略](../../deploy/deploy-enterprise-voice/create-network-intersite-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="6f0e8-134">For details, see [Create network intersite policies in Skype for Business Server](../../deploy/deploy-enterprise-voice/create-network-intersite-policies.md) in the Deployment documentation, and [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps).</span></span>
    
3. <span data-ttu-id="6f0e8-135">获取会话边界控制器的 (SCB) 的 IP 地址从 ITSP 媒体端点。</span><span class="sxs-lookup"><span data-stu-id="6f0e8-135">Get the IP address of the Session Border Controller's (SCB) Media Termination Point from your ITSP.</span></span> <span data-ttu-id="6f0e8-136">将子网掩码为 32 的 IP 地址添加到代表 ITSP 的网络站点。</span><span class="sxs-lookup"><span data-stu-id="6f0e8-136">Add that IP address with a subnet mask of 32 to the network site that represents the ITSP.</span></span> <span data-ttu-id="6f0e8-137">有关详细信息，请参阅[将子网与网络站点相关联](http://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx)。</span><span class="sxs-lookup"><span data-stu-id="6f0e8-137">For details, see [Associate a Subnet with a Network Site](http://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).</span></span>
    
## <a name="call-admission-control-with-a-third-party-pstn-gateway-or-pbx"></a><span data-ttu-id="6f0e8-138">使用第三方 PSTN 网关或 PBX 时的呼叫允许控制</span><span class="sxs-lookup"><span data-stu-id="6f0e8-138">Call admission control with a third-party PSTN gateway or PBX</span></span>

<span data-ttu-id="6f0e8-139">本主题介绍如何在中介服务器的网关接口与第三方公用电话交换网 (pstn) 网关或专用交换机 (PBX) 之间的链路上部署呼叫允许控制 (CAC) 的示例。</span><span class="sxs-lookup"><span data-stu-id="6f0e8-139">This topic describes examples of how call admission control (CAC) can be deployed on the link between the Mediation Server's gateway interface and a third-party public switched telephone network (PSTN) gateway or private branch exchange (PBX).</span></span>
  
### <a name="case-1-cac-between-the-mediation-server-and-a-pstn-gateway"></a><span data-ttu-id="6f0e8-140">示例 1：中介服务器与 PSTN 网关之间的 CAC</span><span class="sxs-lookup"><span data-stu-id="6f0e8-140">Case 1: CAC between the Mediation Server and a PSTN gateway</span></span>

<span data-ttu-id="6f0e8-141">可以在 WAN 上部署 CAC 从中介服务器的网关接口到第三方 PBX 或 PSTN 网关的链接。</span><span class="sxs-lookup"><span data-stu-id="6f0e8-141">CAC can be deployed on the WAN link from the Mediation Server's gateway interface to a third-party PBX or PSTN gateway.</span></span>
  
<span data-ttu-id="6f0e8-142">**示例 1：中介服务器与 PSTN 网关之间的 CAC**</span><span class="sxs-lookup"><span data-stu-id="6f0e8-142">**Case 1: CAC between the Mediation Server and a PSTN gateway**</span></span>

![示例 1：中介服务器与 PSTN 网关之间的 CAC](../../media/CAC_gateways_1.jpg)
  
<span data-ttu-id="6f0e8-144">本示例中，中介服务器与 PSTN 网关之间应用 CAC。</span><span class="sxs-lookup"><span data-stu-id="6f0e8-144">In this example, CAC is applied between the Mediation Server and a PSTN gateway.</span></span> <span data-ttu-id="6f0e8-145">如果业务网络站点 1 的客户端用户 Skype 会放置在网络站点 2 的 PSTN 呼叫通过 PSTN 网关，媒体流通过 WAN 链接。</span><span class="sxs-lookup"><span data-stu-id="6f0e8-145">If a Skype for Business client user at Network Site 1 places a PSTN call through the PSTN gateway in Network Site 2, the media flows through the WAN link.</span></span> <span data-ttu-id="6f0e8-146">因此，将对每个 PSTN 会话执行以下两个 CAC 检查：</span><span class="sxs-lookup"><span data-stu-id="6f0e8-146">Therefore, two CAC checks are performed for each PSTN session:</span></span>
  
- <span data-ttu-id="6f0e8-147">Skype 业务客户端应用程序和中介服务器之间</span><span class="sxs-lookup"><span data-stu-id="6f0e8-147">Between the Skype for Business client application and the Mediation Server</span></span>
    
- <span data-ttu-id="6f0e8-148">中介服务器与 PSTN 网关之间</span><span class="sxs-lookup"><span data-stu-id="6f0e8-148">Between the Mediation Server and the PSTN gateway</span></span>
    
<span data-ttu-id="6f0e8-149">这同时适用于网络站点 1 中的客户端接收的传入 PSTN 呼叫，以及网络站点 1 中的客户端应用程序发送的传出 PSTN 呼叫。</span><span class="sxs-lookup"><span data-stu-id="6f0e8-149">This works for both incoming PSTN calls to a client in Network Site 1, and for outgoing PSTN calls originating from a client application in Network Site 1.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6f0e8-150">请确保 PSTN 网关所属的 IP 子网已配置并与网络站点 2 相关联。</span><span class="sxs-lookup"><span data-stu-id="6f0e8-150">Make sure that the IP subnet that the PSTN gateway belongs to is configured and associated with Network Site 2.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="6f0e8-151">请确保中介服务器的两个接口所属的 IP 子网已配置并与网络站点 1 相关联。</span><span class="sxs-lookup"><span data-stu-id="6f0e8-151">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="6f0e8-152">有关详细信息，请参阅[将子网与网络站点相关联](http://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx)。</span><span class="sxs-lookup"><span data-stu-id="6f0e8-152">For details, see [Associate a Subnet with a Network Site](http://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).</span></span> 
  
### <a name="case-2-cac-between-the-mediation-server-and-a-third-party-pbx-with-media-termination-point"></a><span data-ttu-id="6f0e8-153">示例 2： 中介服务器与具有媒体端点的第三方 PBX 之间的 CAC</span><span class="sxs-lookup"><span data-stu-id="6f0e8-153">Case 2: CAC between the Mediation Server and a third-party PBX with Media Termination Point</span></span>

<span data-ttu-id="6f0e8-154">此配置与示例 1 类似。</span><span class="sxs-lookup"><span data-stu-id="6f0e8-154">This configuration is similar to Case 1.</span></span> <span data-ttu-id="6f0e8-155">在这两种情况下，中介服务器知道哪些设备终止的 WAN 链接的另一端的媒体和 PSTN 网关或 PBX 与媒体端点点 (MTP) 的 IP 地址配置下一个跃点的中介服务器上。</span><span class="sxs-lookup"><span data-stu-id="6f0e8-155">In both the cases, the Mediation Server knows what device terminates media at the opposite end of the WAN link, and the IP address of the PSTN gateway or PBX with Media Termination Point (MTP) is configured on the Mediation Server as the next hop.</span></span>
  
<span data-ttu-id="6f0e8-156">**示例 2：中介服务器与具有 MTP 的第三方 PBX 之间的 CAC**</span><span class="sxs-lookup"><span data-stu-id="6f0e8-156">**Case 2: CAC between the Mediation Server and a third-party PBX with MTP**</span></span>

![示例 2：中介服务器与具有 MTP 的 PBX 之间的 CAC](../../media/CAC_gateways_2.jpg)
  
<span data-ttu-id="6f0e8-158">本示例中，中介服务器与 PBX/MTP 之间应用 CAC。</span><span class="sxs-lookup"><span data-stu-id="6f0e8-158">In this example, CAC is applied between the Mediation Server and the PBX/MTP.</span></span> <span data-ttu-id="6f0e8-159">如果业务网络站点 1 的客户端用户 Skype 发出位于网络站点 2 的 PBX/MTP 通过 PSTN 呼叫，媒体流通过 WAN 链接。</span><span class="sxs-lookup"><span data-stu-id="6f0e8-159">If a Skype for Business client user at the Network Site 1 places a PSTN call through the PBX/MTP located in Network Site 2, the media flows through the WAN link.</span></span> <span data-ttu-id="6f0e8-160">因此，将对每个 PSTN 会话执行以下两个 CAC 检查：</span><span class="sxs-lookup"><span data-stu-id="6f0e8-160">Therefore, for each PSTN session two CAC checks are performed:</span></span>
  
- <span data-ttu-id="6f0e8-161">Skype 业务客户端应用程序和中介服务器之间</span><span class="sxs-lookup"><span data-stu-id="6f0e8-161">Between the Skype for Business client application and the Mediation Server</span></span>
    
- <span data-ttu-id="6f0e8-162">中介服务器与 PBX/MTP 之间</span><span class="sxs-lookup"><span data-stu-id="6f0e8-162">Between the Mediation Server and the PBX/MTP</span></span>
    
<span data-ttu-id="6f0e8-163">这同时适用于网络站点 1 中的客户端接收的传入 PSTN 呼叫，以及网络站点 1 中的客户端发送的传出 PSTN 呼叫。</span><span class="sxs-lookup"><span data-stu-id="6f0e8-163">This works for both incoming PSTN calls to a client in Network Site 1, and outgoing PSTN calls originating from a client in Network Site 1.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6f0e8-164">请确保 MTP 所属的 IP 子网已配置并与网络站点 2 相关联。</span><span class="sxs-lookup"><span data-stu-id="6f0e8-164">Make sure that the IP subnet that the MTP belongs to is configured and associated with Network Site 2.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="6f0e8-165">请确保中介服务器的两个接口所属的 IP 子网已配置并与网络站点 1 相关联。</span><span class="sxs-lookup"><span data-stu-id="6f0e8-165">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="6f0e8-166">有关详细信息，请参阅[将子网与网络站点相关联](http://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx)。</span><span class="sxs-lookup"><span data-stu-id="6f0e8-166">For details, see [Associate a Subnet with a Network Site](http://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).</span></span> 
  
### <a name="case-3-cac-between-the-mediation-server-and-a-third-party-pbx-without-a-media-termination-point"></a><span data-ttu-id="6f0e8-167">示例 3： 中介服务器与没有媒体端点的第三方 PBX 之间的 CAC</span><span class="sxs-lookup"><span data-stu-id="6f0e8-167">Case 3: CAC between the Mediation Server and a third-party PBX without a Media Termination Point</span></span>

<span data-ttu-id="6f0e8-168">示例 3 与前两个示例略有不同。</span><span class="sxs-lookup"><span data-stu-id="6f0e8-168">Case 3 is slightly different from the first two cases.</span></span> <span data-ttu-id="6f0e8-169">如果没有不具有 MTP 的第三方 PBX，传出会话请求第三方 PBX 中介服务器不知道其中媒体将终止 PBX 边界中。</span><span class="sxs-lookup"><span data-stu-id="6f0e8-169">If there is no MTP on the third-party PBX, for an outgoing session request to the third-party PBX the Mediation Server does not know where media will terminate in the PBX boundary.</span></span> <span data-ttu-id="6f0e8-170">在这种情况下，媒体直接在中介服务器和第三方终结点设备之间流动。</span><span class="sxs-lookup"><span data-stu-id="6f0e8-170">In this case, the media flows directly between the Mediation Server and the third-party endpoint device.</span></span>
  
<span data-ttu-id="6f0e8-171">**示例 3：中介服务器与没有 MTP 的第三方 PBX 之间的 CAC**</span><span class="sxs-lookup"><span data-stu-id="6f0e8-171">**Case 3: CAC between the Mediation Server and a third-party PBX without MTP**</span></span>

![示例 3：中介服务器与不具有 MTP 的 PBX 之间的 CAC](../../media/CAC_gateways_3.jpg)
  
<span data-ttu-id="6f0e8-173">本示例中，业务网络站点 1 的客户端用户 Skype 发出呼叫给用户通过 PBX，中介服务器能够执行仅在 (业务客户端应用程序的 Skype) 和中介服务器之间的代理线路上的 CAC 检查。</span><span class="sxs-lookup"><span data-stu-id="6f0e8-173">In this example, if a Skype for Business client user at Network Site 1 places a call to a user through the PBX, the Mediation Server is able to perform CAC checks only on the proxy leg (between the Skype for Business client application and Mediation Server).</span></span> <span data-ttu-id="6f0e8-174">由于中介服务器没有终结点设备信息请求会话时，不能在 WAN 上执行 CAC 检查呼叫建立之前 （中介服务器和第三方终结点） 之间的链接。</span><span class="sxs-lookup"><span data-stu-id="6f0e8-174">Because the Mediation Server does not have information about the endpoint device while the session is being requested, CAC checks cannot be performed on the WAN link (between the Mediation Server and the third-party endpoint) prior to call establishment.</span></span> <span data-ttu-id="6f0e8-175">在会话建立之后，但是，中介服务器简化的在中继上使用的带宽核算中。</span><span class="sxs-lookup"><span data-stu-id="6f0e8-175">After the session is established, however, the Mediation Server facilitates in accounting for the bandwidth used on the trunk.</span></span>
  
<span data-ttu-id="6f0e8-176">对于来自第三方终结点的呼叫，该终结点设备有关的信息可在会话请求的时间并且可以中介服务器的双方执行 CAC 检查。</span><span class="sxs-lookup"><span data-stu-id="6f0e8-176">For calls that originate from the third-party endpoint, the information about that endpoint device is available at the time of session request and CAC check can be performed on both the sides of the Mediation Server.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6f0e8-177">请确保终结点设备所属的 IP 子网已配置并与网络站点 2 相关联。</span><span class="sxs-lookup"><span data-stu-id="6f0e8-177">Make sure that the IP subnet that the endpoint devices belong to is configured and associated with Network Site 2.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="6f0e8-178">请确保中介服务器的两个接口所属的 IP 子网已配置并与网络站点 1 相关联。</span><span class="sxs-lookup"><span data-stu-id="6f0e8-178">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="6f0e8-179">有关详细信息，请参阅[将子网与网络站点相关联](http://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx)。</span><span class="sxs-lookup"><span data-stu-id="6f0e8-179">For details, see [Associate a Subnet with a Network Site](http://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).</span></span> 
  

