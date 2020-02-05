---
title: 在 Skype for Business 服务器中配置媒体绕过全局设置以使用网站和区域信息
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.assetid: 0a21cdf1-f350-49da-b346-70806f256bea
description: 将 "绕过媒体" 配置为仅用于 Skype for Business Server Enterprise Voice 中的特定网站和区域。
ms.openlocfilehash: 7a424e6737c1165eb037ca1130e3b87c4d0436e0
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41766935"
---
# <a name="configure-media-bypass-global-settings-in-skype-for-business-server-to-use-site-and-region-information"></a><span data-ttu-id="19d2e-103">在 Skype for Business 服务器中配置媒体绕过全局设置以使用网站和区域信息</span><span class="sxs-lookup"><span data-stu-id="19d2e-103">Configure media bypass global settings in Skype for Business Server to use site and region information</span></span>
 
<span data-ttu-id="19d2e-104">将 "绕过媒体" 配置为仅用于 Skype for Business Server Enterprise Voice 中的特定网站和区域。</span><span class="sxs-lookup"><span data-stu-id="19d2e-104">Configure media bypass to be used for only certain sites and regions in Skype for Business Server Enterprise Voice.</span></span> 
  
 <span data-ttu-id="19d2e-105">如果你使用本主题中的步骤来配置媒体绕过的全局设置，则假设你的所有 Skype for Business 终结点和任何对等的用户在中继连接上配置了媒体旁路的任何对等设备之间没有完好的连接。</span><span class="sxs-lookup"><span data-stu-id="19d2e-105">If you use the steps in this topic to configure global settings for media bypass, the assumption is that you do not have good connectivity between all Skype for Business endpoints and any peer for which you configured media bypass on the trunk connection.</span></span>
  
> [!NOTE]
> <span data-ttu-id="19d2e-p101">启用呼叫允许控制和媒体旁路高级企业语音功能后，会在两者之间共享网络区域和网络站点信息。因此，如果您已配置了呼叫允许控制，则不需要使用以下过程专门为媒体旁路编辑站点和区域信息。如果尚未为呼叫允许控制配置网络区域和站点，并且想要更改媒体旁路设置，请按照该过程中的步骤进行操作。</span><span class="sxs-lookup"><span data-stu-id="19d2e-p101">Network region and network site information is shared between call admission control and media bypass advanced Enterprise Voice features when both are enabled. Therefore, if you have already configured call admission control, you are not required to use the following procedure to edit the site and region information specifically for media bypass. Follow the steps in this procedure if you have not yet configured network regions and sites for call admission control, and you want to change media bypass settings.</span></span> 
  
<span data-ttu-id="19d2e-109">若要使媒体旁路正常工作，在拓扑生成器中定义的网站与在配置网络区域和网络网站时定义的网站之间必须保持一致。</span><span class="sxs-lookup"><span data-stu-id="19d2e-109">For media bypass to work properly there must be consistency between a site as defined in Topology Builder and as it is defined when you configure network regions and network sites.</span></span> <span data-ttu-id="19d2e-110">例如，如果您在拓扑生成器中定义了一个已部署 PSTN 网关的分支站点，则必须使用企业语音策略配置分支网站，以便分支站点用户通过 PSTN 路由其 PSTN 呼叫分支站点上的网关。</span><span class="sxs-lookup"><span data-stu-id="19d2e-110">For example, if you have a branch site that you defined in Topology Builder as having only a PSTN gateway deployed, then that branch site must be configured with an Enterprise Voice policy that enables branch site users to have their PSTN calls routed through the PSTN gateway at the branch site.</span></span>
  
### <a name="to-configure-site-and-region-information-for-media-bypass"></a><span data-ttu-id="19d2e-111">为媒体旁路配置站点和区域信息</span><span class="sxs-lookup"><span data-stu-id="19d2e-111">To Configure Site and Region Information for Media Bypass</span></span>

1. <span data-ttu-id="19d2e-112">打开一个浏览器窗口，然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。</span><span class="sxs-lookup"><span data-stu-id="19d2e-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
2. <span data-ttu-id="19d2e-113">在左侧导航栏中，单击“网络配置”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="19d2e-113">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="19d2e-114">双击表中的“全局”\*\*\*\* 配置。</span><span class="sxs-lookup"><span data-stu-id="19d2e-114">Double-click the **Global** configuration in the table.</span></span>
    
4. <span data-ttu-id="19d2e-115">在“编辑全局设置”\*\*\*\* 页上，选中“启用媒体旁路”\*\*\*\* 复选框。</span><span class="sxs-lookup"><span data-stu-id="19d2e-115">On the **Edit Global Setting** page, select the **Enable media bypass** check box.</span></span>
    
5. <span data-ttu-id="19d2e-116">单击“使用站点和区域配置”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="19d2e-116">Click **Use sites and region configuration**.</span></span>
    
6. <span data-ttu-id="19d2e-117">如有必要，请选中“为非映射站点启用旁路”\*\*\*\* 复选框。</span><span class="sxs-lookup"><span data-stu-id="19d2e-117">If necessary, select the **Enable bypass for non-mapped sites** check box.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="19d2e-p103">仅当具有一个或多个与没有带宽限制的同一区域关联的大型站点，但有一些与有带宽限制的同一区域关联的分支站点时，才应选中该复选框。为未映射的站点启用旁路时可以简化配置，这是因为只需指定与分支站点关联的子网，而无需指定与所有站点关联的所有子网。如果启用了呼叫允许控制，则建议不要选中该复选框。</span><span class="sxs-lookup"><span data-stu-id="19d2e-p103">Select this check box only if you have one or more large sites associated with the same region that do not have bandwidth constraints (for example, a large central site), but you also have some branch sites associated with the same region that do have bandwidth constraints. When you enable bypass for non-mapped sites, configuration is streamlined in that you specify only the subnets associated with the branch sites, rather than needing to specify all subnets associated with all sites. We recommend that you do not select this check box if call admission control is enabled.</span></span> 
  
7. <span data-ttu-id="19d2e-121">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="19d2e-121">Click **Commit**.</span></span>
    
<span data-ttu-id="19d2e-p104">接着，将子网添加到网络站点中，如[Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets)中所述。将所有子网与网络站点相关联后，媒体旁路即部署完成。</span><span class="sxs-lookup"><span data-stu-id="19d2e-p104">Next, add subnets to the network site, as described in [Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets). After you associate all subnets with network sites, media bypass deployment is complete.</span></span>
> [!IMPORTANT]
> <span data-ttu-id="19d2e-124">如果尚未创建网络区域和网络站点，则必须先创建这些区域和站点，才能部署媒体旁路。</span><span class="sxs-lookup"><span data-stu-id="19d2e-124">If you have not already created network regions and network sites, you must first create those before you can proceed with media bypass deployment.</span></span> <span data-ttu-id="19d2e-125">有关详细信息，请参阅[在 Skype For business 中部署网络区域、网站和子网](deploy-network.md)。</span><span class="sxs-lookup"><span data-stu-id="19d2e-125">For details, see [Deploy network regions, sites and subnets in Skype for Business](deploy-network.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="19d2e-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="19d2e-126">See also</span></span>

[<span data-ttu-id="19d2e-127">Associate a subnet with a network site</span><span class="sxs-lookup"><span data-stu-id="19d2e-127">Associate a subnet with a network site</span></span>](deploy-network.md#BKMK_AssociateSubnets)

