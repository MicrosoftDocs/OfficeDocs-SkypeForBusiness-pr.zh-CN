---
title: 'Lync Server 2013: 启用网络媒体旁路'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enabling network media bypass
ms:assetid: 95c4fa06-49d3-41ac-acdc-7dcda66e5508
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182552(v=OCS.15)
ms:contentKeyID: 48184846
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ff18c69d6d257a520d2413bff266c97879d4963e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830256"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-network-media-bypass-in-lync-server-2013"></a><span data-ttu-id="a0b43-102">在 Lync Server 2013 中启用网络媒体旁路</span><span class="sxs-lookup"><span data-stu-id="a0b43-102">Enabling network media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a0b43-103">_**主题上次修改时间:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="a0b43-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="a0b43-104">媒体绕过设置在 Microsoft Lync Server 2013 部署中全局应用。</span><span class="sxs-lookup"><span data-stu-id="a0b43-104">Media bypass settings apply globally across a Microsoft Lync Server 2013 deployment.</span></span> <span data-ttu-id="a0b43-105">媒体绕过允许呼叫绕过中介服务器。</span><span class="sxs-lookup"><span data-stu-id="a0b43-105">Media bypass allows calls to bypass the Mediation Server.</span></span> <span data-ttu-id="a0b43-106">有关何时使用 "媒体绕过" 的详细信息, 请参阅 "规划" 部分中的 "[在 Lync Server 2013 中规划媒体旁路](lync-server-2013-planning-for-media-bypass.md)"。</span><span class="sxs-lookup"><span data-stu-id="a0b43-106">For details about when to use Media bypass, see [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) in the Planning section.</span></span>

<span data-ttu-id="a0b43-107">你可以从 Lync Server 控制面板启用和配置 "绕过媒体"。</span><span class="sxs-lookup"><span data-stu-id="a0b43-107">You can enable and configure media bypass from the Lync Server Control Panel.</span></span>

<div>

## <a name="to-enable-and-configure-media-bypass"></a><span data-ttu-id="a0b43-108">启用和配置绕过媒体</span><span class="sxs-lookup"><span data-stu-id="a0b43-108">To enable and configure media bypass</span></span>

1.  <span data-ttu-id="a0b43-109">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="a0b43-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a0b43-110">打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="a0b43-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a0b43-111">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="a0b43-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="a0b43-112">在左侧导航栏中, 单击 "**网络配置**", 然后单击 "**全局**"。</span><span class="sxs-lookup"><span data-stu-id="a0b43-112">In the left navigation bar, click **Network Configuration** and then click **Global**.</span></span>

4.  <span data-ttu-id="a0b43-113">在 "**全局**" 页面上, 单击 "**全局**配置"。</span><span class="sxs-lookup"><span data-stu-id="a0b43-113">On the **Global** page, click the **Global** configuration.</span></span> <span data-ttu-id="a0b43-114">始终只有一种配置, 它始终名为 Global。</span><span class="sxs-lookup"><span data-stu-id="a0b43-114">There is always only one configuration, and it is always named Global.</span></span>

5.  <span data-ttu-id="a0b43-115">在 "**编辑**" 菜单上, 单击 "**查看详细信息**"。</span><span class="sxs-lookup"><span data-stu-id="a0b43-115">On the **Edit** menu, click **View details**.</span></span>

6.  <span data-ttu-id="a0b43-116">在 "**编辑全局设置**" 页面上, 单击 "**启用绕过媒体**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="a0b43-116">On the **Edit Global Setting** page, click the **Enable media bypass** check box.</span></span>

7.  <span data-ttu-id="a0b43-117">选择下列选项之一:</span><span class="sxs-lookup"><span data-stu-id="a0b43-117">Select one of the following options:</span></span>
    
      - <span data-ttu-id="a0b43-118">**"始终绕过**   " 选择此选项可在所有呼叫中尝试媒体绕过。</span><span class="sxs-lookup"><span data-stu-id="a0b43-118">**Always bypass**   Select this option to attempt media bypass on all calls.</span></span> <span data-ttu-id="a0b43-119">如果启用了 "呼叫许可控制 (CAC)", 此选项将不可用。</span><span class="sxs-lookup"><span data-stu-id="a0b43-119">This option will be unavailable if call admission control (CAC) is enabled.</span></span> <span data-ttu-id="a0b43-120">如果未启用 CAC, 请在以下情况下选择此选项:</span><span class="sxs-lookup"><span data-stu-id="a0b43-120">If CAC is not enabled, select this option in the following situations:</span></span>
        
          - <span data-ttu-id="a0b43-121">无需带宽控制。</span><span class="sxs-lookup"><span data-stu-id="a0b43-121">There is no need for bandwidth control.</span></span>
        
          - <span data-ttu-id="a0b43-122">不需要精确的配置来确定何时应发生绕过。</span><span class="sxs-lookup"><span data-stu-id="a0b43-122">There is no need for fine-grained configuration to determine when bypass should happen.</span></span>
        
          - <span data-ttu-id="a0b43-123">网关和客户端之间存在完全连接。</span><span class="sxs-lookup"><span data-stu-id="a0b43-123">There is full connectivity between gateways and clients.</span></span>
    
      - <span data-ttu-id="a0b43-124">**使用网站和区域配置**   如果启用了 CAC, 则默认情况下此选项处于选中状态, 并且不能更改。</span><span class="sxs-lookup"><span data-stu-id="a0b43-124">**Use sites and region configuration**   If CAC is enabled, this option is selected by default and cannot be changed.</span></span> <span data-ttu-id="a0b43-125">选中此选项时, 将使用网络配置网站和区域确定何时可能使用媒体绕过。</span><span class="sxs-lookup"><span data-stu-id="a0b43-125">When this option is selected, network configuration sites and regions will be used to determine when media bypass is possible.</span></span> <span data-ttu-id="a0b43-126">如果选择此选项, 则可以选择对未映射的网站启用 "绕过"。</span><span class="sxs-lookup"><span data-stu-id="a0b43-126">If you select this option, you can choose to enable bypass for sites that are not mapped.</span></span> <span data-ttu-id="a0b43-127">仅当您有一个或多个大型网站与不具有带宽约束的同一区域 (例如, 大型中央网站) 相关联, 并且您还具有与之关联的一些分支网站时, 单击 "**为非映射网站启用旁路**" 复选框。具有带宽限制的同一区域。</span><span class="sxs-lookup"><span data-stu-id="a0b43-127">Click the **Enable bypass for non-mapped sites** check box only if you have one or more large sites associated with the same region that do not have bandwidth constraints (for example, a large central site) and you also have some branch sites associated with the same region that do have bandwidth constraints.</span></span> <span data-ttu-id="a0b43-128">为非映射网站启用 "绕过" 时, 将简化配置, 因为你只需指定与分支网站相关联的子网, 而无需指定与所有网站相关联的所有子网。</span><span class="sxs-lookup"><span data-stu-id="a0b43-128">When you enable bypass for non-mapped sites, configuration is streamlined because you specify only the subnets associated with the branch sites rather than needing to specify all subnets associated with all sites.</span></span> <span data-ttu-id="a0b43-129">如果启用了 CAC, 我们建议您不要选中 "为**未映射的网站启用旁路**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="a0b43-129">We recommend that you do not select the **Enable bypass for non-mapped sites** check box if CAC is enabled.</span></span>

8.  <span data-ttu-id="a0b43-130">单击 "**提交**" 保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="a0b43-130">Click **Commit** to save your changes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a0b43-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a0b43-131">See Also</span></span>


[<span data-ttu-id="a0b43-132">在 Lync Server 2013 中禁用网络媒体旁路</span><span class="sxs-lookup"><span data-stu-id="a0b43-132">Disabling network media bypass in Lync Server 2013</span></span>](lync-server-2013-disabling-network-media-bypass.md)  


[<span data-ttu-id="a0b43-133">Lync Server 2013 中的全局媒体绕过选项</span><span class="sxs-lookup"><span data-stu-id="a0b43-133">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  


[<span data-ttu-id="a0b43-134">在 Lync Server 2013 中规划媒体旁路</span><span class="sxs-lookup"><span data-stu-id="a0b43-134">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

