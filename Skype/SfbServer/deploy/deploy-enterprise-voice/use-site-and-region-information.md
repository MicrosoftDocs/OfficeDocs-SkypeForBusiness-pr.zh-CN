---
title: 配置媒体绕过全局设置中的业务服务器 2015 以使用站点和区域信息的 Skype
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0a21cdf1-f350-49da-b346-70806f256bea
description: 配置媒体绕过以用于某些网站和区域中 Skype 业务 Server 企业语音。
ms.openlocfilehash: ce9daafdde21bc2d30a942ce6b888f2cc7c4e2ff
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="configure-media-bypass-global-settings-in-skype-for-business-server-2015-to-use-site-and-region-information"></a><span data-ttu-id="081ee-103">配置媒体绕过全局设置中的业务服务器 2015 以使用站点和区域信息的 Skype</span><span class="sxs-lookup"><span data-stu-id="081ee-103">Configure media bypass global settings in Skype for Business Server 2015 to use site and region information</span></span>
 
<span data-ttu-id="081ee-104">配置媒体绕过以用于某些网站和区域中 Skype 业务 Server 企业语音。</span><span class="sxs-lookup"><span data-stu-id="081ee-104">Configure media bypass to be used for only certain sites and regions in Skype for Business Server Enterprise Voice.</span></span> 
  
 <span data-ttu-id="081ee-105">如果您使用绕过本主题可配置为媒体的全局设置中的步骤，假设您没有良好所有 Skype 业务终结点和任何在中继连接为其配置媒体绕过的对等方之间的连接性。</span><span class="sxs-lookup"><span data-stu-id="081ee-105">If you use the steps in this topic to configure global settings for media bypass, the assumption is that you do not have good connectivity between all Skype for Business endpoints and any peer for which you configured media bypass on the trunk connection.</span></span>
  
> [!NOTE]
> <span data-ttu-id="081ee-p101">启用呼叫允许控制和媒体旁路高级企业语音功能后，会在两者之间共享网络区域和网络站点信息。因此，如果您已配置了呼叫允许控制，则不需要使用以下过程专门为媒体旁路编辑站点和区域信息。如果尚未为呼叫允许控制配置网络区域和站点，并且想要更改媒体旁路设置，请按照该过程中的步骤进行操作。</span><span class="sxs-lookup"><span data-stu-id="081ee-p101">Network region and network site information is shared between call admission control and media bypass advanced Enterprise Voice features when both are enabled. Therefore, if you have already configured call admission control, you are not required to use the following procedure to edit the site and region information specifically for media bypass. Follow the steps in this procedure if you have not yet configured network regions and sites for call admission control, and you want to change media bypass settings.</span></span> 
  
<span data-ttu-id="081ee-109">为媒体绕过以正确之间必须存在一致性网站随着拓扑生成器中定义以及定义当您配置网络区域和网络站点。</span><span class="sxs-lookup"><span data-stu-id="081ee-109">For media bypass to work properly there must be consistency between a site as defined in Topology Builder and as it is defined when you configure network regions and network sites.</span></span> <span data-ttu-id="081ee-110">例如，如果已在拓扑生成器中定义为具有分支站点部署 PSTN 网关，则必须使用企业语音策略，以使其 PSTN 呼叫路由到 PSTN 的分支站点用户配置该分支站点在分支站点的网关。</span><span class="sxs-lookup"><span data-stu-id="081ee-110">For example, if you have a branch site that you defined in Topology Builder as having only a PSTN gateway deployed, then that branch site must be configured with an Enterprise Voice policy that enables branch site users to have their PSTN calls routed through the PSTN gateway at the branch site.</span></span>
  
### <a name="to-configure-site-and-region-information-for-media-bypass"></a><span data-ttu-id="081ee-111">为媒体旁路配置站点和区域信息</span><span class="sxs-lookup"><span data-stu-id="081ee-111">To Configure Site and Region Information for Media Bypass</span></span>

1. <span data-ttu-id="081ee-112">打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="081ee-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
2. <span data-ttu-id="081ee-113">在左侧导航栏中，单击“网络配置”****。</span><span class="sxs-lookup"><span data-stu-id="081ee-113">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="081ee-114">双击表中的“全局”**** 配置。</span><span class="sxs-lookup"><span data-stu-id="081ee-114">Double-click the **Global** configuration in the table.</span></span>
    
4. <span data-ttu-id="081ee-115">在“编辑全局设置”**** 页上，选中“启用媒体旁路”**** 复选框。</span><span class="sxs-lookup"><span data-stu-id="081ee-115">On the **Edit Global Setting** page, select the **Enable media bypass** check box.</span></span>
    
5. <span data-ttu-id="081ee-116">单击“使用站点和区域配置”****。</span><span class="sxs-lookup"><span data-stu-id="081ee-116">Click **Use sites and region configuration**.</span></span>
    
6. <span data-ttu-id="081ee-117">如有必要，请选中“为非映射站点启用旁路”**** 复选框。</span><span class="sxs-lookup"><span data-stu-id="081ee-117">If necessary, select the **Enable bypass for non-mapped sites** check box.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="081ee-p103">仅当具有一个或多个与没有带宽限制的同一区域关联的大型站点，但有一些与有带宽限制的同一区域关联的分支站点时，才应选中该复选框。为未映射的站点启用旁路时可以简化配置，这是因为只需指定与分支站点关联的子网，而无需指定与所有站点关联的所有子网。如果启用了呼叫允许控制，则建议不要选中该复选框。</span><span class="sxs-lookup"><span data-stu-id="081ee-p103">Select this check box only if you have one or more large sites associated with the same region that do not have bandwidth constraints (for example, a large central site), but you also have some branch sites associated with the same region that do have bandwidth constraints. When you enable bypass for non-mapped sites, configuration is streamlined in that you specify only the subnets associated with the branch sites, rather than needing to specify all subnets associated with all sites. We recommend that you do not select this check box if call admission control is enabled.</span></span> 
  
7. <span data-ttu-id="081ee-121">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="081ee-121">Click **Commit**.</span></span>
    
<span data-ttu-id="081ee-p104">接着，将子网添加到网络站点中，如[Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets)中所述。将所有子网与网络站点相关联后，媒体旁路即部署完成。</span><span class="sxs-lookup"><span data-stu-id="081ee-p104">Next, add subnets to the network site, as described in [Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets). After you associate all subnets with network sites, media bypass deployment is complete.</span></span>
> [!IMPORTANT]
> <span data-ttu-id="081ee-124">如果尚未创建网络区域和网络站点，则必须先创建这些区域和站点，才能部署媒体旁路。</span><span class="sxs-lookup"><span data-stu-id="081ee-124">If you have not already created network regions and network sites, you must first create those before you can proceed with media bypass deployment.</span></span> <span data-ttu-id="081ee-125">有关详细信息，请参阅[Deploy 网络区域、 网站和业务 2015年的 Skype 中的子网](deploy-network.md)。</span><span class="sxs-lookup"><span data-stu-id="081ee-125">For details, see [Deploy network regions, sites and subnets in Skype for Business 2015](deploy-network.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="081ee-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="081ee-126">See also</span></span>

#### 

[<span data-ttu-id="081ee-127">Associate a subnet with a network site</span><span class="sxs-lookup"><span data-stu-id="081ee-127">Associate a subnet with a network site</span></span>](deploy-network.md#BKMK_AssociateSubnets)

