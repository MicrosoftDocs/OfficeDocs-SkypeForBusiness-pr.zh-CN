---
title: 配置媒体旁路全局设置以使用站点和区域信息
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure media bypass global settings to use site and region information
ms:assetid: 0a21cdf1-f350-49da-b346-70806f256bea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398150(v=OCS.15)
ms:contentKeyID: 48183360
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cd070e6380a896548b851ac7d3472cd86eeba75b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837359"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-media-bypass-global-settings-in-lync-server-2013-to-use-site-and-region-information"></a><span data-ttu-id="4f142-102">Configure media bypass global settings in Lync Server 2013 to use site and region information</span><span class="sxs-lookup"><span data-stu-id="4f142-102">Configure media bypass global settings in Lync Server 2013 to use site and region information</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4f142-103">_**主题上次修改时间:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="4f142-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="4f142-104">本主题假定你已将来自中介服务器的任何主干连接的所有主干连接配置为 "Internet 电话服务" (公共交换电话网络 (PSTN) 网关、IP PBX 或会话边界控制器 (SBC)) 的媒体旁路您希望媒体绕过中介服务器的特定网站或服务的提供商 (ITSP)。</span><span class="sxs-lookup"><span data-stu-id="4f142-104">This topic assumes that you have already configured media bypass for any trunk connections from the Mediation Server to a peer (a public switched telephone network (PSTN) gateway, an IP-PBX, or a Session Border Controller (SBC) at an Internet Telephony Service Provider (ITSP) for a specific site or service for which you want media to bypass the Mediation Server.</span></span><BR><span data-ttu-id="4f142-105">本主题还假定你已在拓扑生成器中定义了所有中心网站和分支网站, 使其与你根据在中<A href="lync-server-2013-create-or-modify-a-network-region.md">创建或修改网络区域中的步骤所执行的步骤相匹配的网络区域、网络网站和子网配置相匹配。Lync Server 2013</A>,<A href="lync-server-2013-create-or-modify-a-network-site.md">在 lync server 2013 中创建或修改网络网站</A>, 并<A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">将子网与 lync server 2013 中的网络站点相关联</A>。</span><span class="sxs-lookup"><span data-stu-id="4f142-105">This topic also assumes that you have defined all central sites and branch sites in Topology Builder in a way that matches the network region, network site, and subnet configuration that you performed according to the steps in <A href="lync-server-2013-create-or-modify-a-network-region.md">Create or modify a network region in Lync Server 2013</A>, <A href="lync-server-2013-create-or-modify-a-network-site.md">Create or modify a network site in Lync Server 2013</A>, and <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Associate a subnet with a network site in Lync Server 2013</A>.</span></span> <span data-ttu-id="4f142-106">如果它们不匹配, 则 "媒体绕过" 将不会成功。</span><span class="sxs-lookup"><span data-stu-id="4f142-106">If they do not match, then media bypass will not succeed.</span></span>



</div>

<span data-ttu-id="4f142-107">除了为与对等相关联的单个中继连接启用媒体旁路外, 还必须配置全局设置。</span><span class="sxs-lookup"><span data-stu-id="4f142-107">In addition to enabling media bypass for individual trunk connections associated with a peer, you must also configure global settings.</span></span> <span data-ttu-id="4f142-108">如果你使用本主题中的步骤来配置媒体绕过的全局设置, 则假设以下一种或两种情况会影响你的配置:</span><span class="sxs-lookup"><span data-stu-id="4f142-108">If you use the steps in this topic to configure global settings for media bypass, the assumption is that one or both of the following situations affects your configuration:</span></span>

  - <span data-ttu-id="4f142-109">您\*\* 的 Lync 服务器终结点和任何对等的用户在中继连接上配置了媒体旁路的任何对等连接之间没有连接良好的连接。</span><span class="sxs-lookup"><span data-stu-id="4f142-109">You *do not* have good connectivity between Lync Server endpoints and any peers for which you configured media bypass on the trunk connection.</span></span>

  - <span data-ttu-id="4f142-110">启用了 "带宽管理" 的 "呼叫许可控制 (CAC)"。</span><span class="sxs-lookup"><span data-stu-id="4f142-110">Call admission control (CAC) for bandwidth management is enabled.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="4f142-111">有关呼叫许可控制和媒体绕过的注意事项的详细信息, 请参阅规划文档中<A href="lync-server-2013-media-bypass-and-mediation-server.md">Lync server 2013</A>中的 "呼叫对 PSTN 连接的接入控制" 部分。</span><span class="sxs-lookup"><span data-stu-id="4f142-111">For details about the considerations for both call admission control and media bypass, see the "Call Admission Control of PSTN Connections" section in <A href="lync-server-2013-media-bypass-and-mediation-server.md">Media bypass and Mediation Server in Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>

<span data-ttu-id="4f142-p103">启用呼叫允许控制和媒体旁路高级企业语音功能后，会在两者之间共享网络区域和网络站点信息。因此，如果您已配置了呼叫允许控制，则不需要使用以下过程专门为媒体旁路编辑站点和区域信息。如果尚未为呼叫允许控制配置网络区域和站点，并且想要更改媒体旁路设置，请按照该过程中的步骤进行操作。</span><span class="sxs-lookup"><span data-stu-id="4f142-p103">Network region and network site information is shared between call admission control and media bypass advanced Enterprise Voice features when both are enabled. Therefore, if you have already configured call admission control, you are not required to use the following procedure to edit the site and region information specifically for media bypass. Follow the steps in this procedure if you have not yet configured network regions and sites for call admission control, and you want to change media bypass settings.</span></span>

<span data-ttu-id="4f142-115">或者, 如果你想要使用现场和区域信息进行跳过决策, 但不想启用呼叫许可控制, 请按照以下步骤操作。</span><span class="sxs-lookup"><span data-stu-id="4f142-115">Or, follow these steps if you want to use site and region information in making the bypass decision, but have no intention of enabling call admission control.</span></span> <span data-ttu-id="4f142-116">在这种情况下, 带宽受限链接仍需要通过网络站点间策略来表示, 如在[Lync Server 2013 中创建网络站点间策略](lync-server-2013-create-network-intersite-policies.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="4f142-116">In such a case, bandwidth restricted links will still need to be represented through network intersite policies, as described in [Create network intersite policies in Lync Server 2013](lync-server-2013-create-network-intersite-policies.md).</span></span> <span data-ttu-id="4f142-117">在这种情况下, 实际带宽限制不太重要, 因为通话许可控制尚未启用。</span><span class="sxs-lookup"><span data-stu-id="4f142-117">The actual bandwidth constraints are not as important in this case, because call admission control has not been enabled.</span></span> <span data-ttu-id="4f142-118">相反, 这些链接用于对子网进行分区以指定那些没有带宽限制的子网, 因此可以使用媒体旁路。</span><span class="sxs-lookup"><span data-stu-id="4f142-118">Instead, these links are used to partition subnets to specify those that have no bandwidth limits and can, therefore, employ media bypass.</span></span> <span data-ttu-id="4f142-119">请注意, 当同时启用 "呼叫许可控制" 和 "媒体旁路" 时, 也是如此。</span><span class="sxs-lookup"><span data-stu-id="4f142-119">Note that this is also true when call admission control and media bypass are both enabled.</span></span>

<span data-ttu-id="4f142-120">此外, 若要使 "回避" 正常工作, 在拓扑生成器中定义的站点和在配置网络区域和网络站点时定义的站点之间必须保持一致。</span><span class="sxs-lookup"><span data-stu-id="4f142-120">Furthermore, for bypass to work properly there must be consistency between a site as defined in Topology Builder and as it is defined when you configure network regions and network sites.</span></span> <span data-ttu-id="4f142-121">例如, 如果您在拓扑生成器中定义了一个已部署 PSTN 网关的分支站点, 则必须使用企业语音策略配置分支网站, 以便分支站点用户通过 PSTN 路由其 PSTN 呼叫分支站点上的网关。</span><span class="sxs-lookup"><span data-stu-id="4f142-121">For example, if you have a branch site that you defined in Topology Builder as having only a PSTN gateway deployed, then that branch site must be configured with an Enterprise Voice policy that enables branch site users to have their PSTN calls routed through the PSTN gateway at the branch site.</span></span>

<div>

## <a name="to-configure-site-and-region-information-for-media-bypass"></a><span data-ttu-id="4f142-122">为媒体旁路配置站点和区域信息</span><span class="sxs-lookup"><span data-stu-id="4f142-122">To Configure Site and Region Information for Media Bypass</span></span>

1.  <span data-ttu-id="4f142-123">打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="4f142-123">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="4f142-124">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="4f142-124">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="4f142-125">在左侧导航栏中，单击“网络配置”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4f142-125">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="4f142-126">双击表中的“全局”\*\*\*\* 配置。</span><span class="sxs-lookup"><span data-stu-id="4f142-126">Double-click the **Global** configuration in the table.</span></span>

4.  <span data-ttu-id="4f142-127">在“编辑全局设置”\*\*\*\* 页上，选中“启用媒体旁路”\*\*\*\* 复选框。</span><span class="sxs-lookup"><span data-stu-id="4f142-127">On the **Edit Global Setting** page, select the **Enable media bypass** check box.</span></span>

5.  <span data-ttu-id="4f142-128">单击“使用站点和区域配置”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4f142-128">Click **Use sites and region configuration**.</span></span>

6.  <span data-ttu-id="4f142-129">如有必要，请选中“为非映射站点启用旁路”\*\*\*\* 复选框。</span><span class="sxs-lookup"><span data-stu-id="4f142-129">If necessary, select the **Enable bypass for non-mapped sites** check box.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="4f142-p107">仅当具有一个或多个与没有带宽限制的同一区域关联的大型站点，但有一些与有带宽限制的同一区域关联的分支站点时，才应选中该复选框。为未映射的站点启用旁路时可以简化配置，这是因为只需指定与分支站点关联的子网，而无需指定与所有站点关联的所有子网。如果启用了呼叫允许控制，则建议不要选中该复选框。</span><span class="sxs-lookup"><span data-stu-id="4f142-p107">Select this check box only if you have one or more large sites associated with the same region that do not have bandwidth constraints (for example, a large central site), but you also have some branch sites associated with the same region that do have bandwidth constraints. When you enable bypass for non-mapped sites, configuration is streamlined in that you specify only the subnets associated with the branch sites, rather than needing to specify all subnets associated with all sites. We recommend that you do not select this check box if call admission control is enabled.</span></span>

    
    </div>

7.  <span data-ttu-id="4f142-133">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="4f142-133">Click **Commit**.</span></span>

<span data-ttu-id="4f142-134">接下来, 将子网添加到网络站点, 如[将子网与网络站点关联到 Lync Server 2013 中的 "媒体绕过](lync-server-2013-associate-subnets-with-network-sites-for-media-bypass.md)" 中所述。</span><span class="sxs-lookup"><span data-stu-id="4f142-134">Next, add subnets to the network site, as described in [Associate subnets with network sites for media bypass in Lync Server 2013](lync-server-2013-associate-subnets-with-network-sites-for-media-bypass.md).</span></span> <span data-ttu-id="4f142-135">(有关将子网与网络站点相关联的实际过程, 请参阅[将子网与 Lync Server 2013 中的网络站点相关联](lync-server-2013-associate-a-subnet-with-a-network-site.md)。)将所有子网与网络站点关联后, 将完成 "媒体绕过部署"。</span><span class="sxs-lookup"><span data-stu-id="4f142-135">(The actual procedures for associating subnets with network sites are described in [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).) After you associate all subnets with network sites, media bypass deployment is complete.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="4f142-136">如果尚未创建网络区域和网络站点，则必须先创建这些区域和站点，才能部署媒体旁路。</span><span class="sxs-lookup"><span data-stu-id="4f142-136">If you have not already created network regions and network sites, you must first create those before you can proceed with media bypass deployment.</span></span> <span data-ttu-id="4f142-137">有关详细信息, 请参阅<A href="lync-server-2013-create-or-modify-a-network-region.md">在 Lync server 2013 中创建或修改网络区域</A>, 并<A href="lync-server-2013-create-or-modify-a-network-site.md">在 lync Server 2013 中创建或修改网络网站</A>。</span><span class="sxs-lookup"><span data-stu-id="4f142-137">For details, see <A href="lync-server-2013-create-or-modify-a-network-region.md">Create or modify a network region in Lync Server 2013</A> and <A href="lync-server-2013-create-or-modify-a-network-site.md">Create or modify a network site in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4f142-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4f142-138">See Also</span></span>


[<span data-ttu-id="4f142-139">将子网与 Lync Server 2013 中的媒体绕过的网络站点关联</span><span class="sxs-lookup"><span data-stu-id="4f142-139">Associate subnets with network sites for media bypass in Lync Server 2013</span></span>](lync-server-2013-associate-subnets-with-network-sites-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

