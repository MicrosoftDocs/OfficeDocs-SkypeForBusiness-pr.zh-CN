---
title: Lync Server 2013：启用网络媒体旁路
description: Lync Server 2013：启用网络媒体旁路。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling network media bypass
ms:assetid: 95c4fa06-49d3-41ac-acdc-7dcda66e5508
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182552(v=OCS.15)
ms:contentKeyID: 48184846
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1218376903aa42e1ea55205e3a9e8d16aade9a3a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546548"
---
# <a name="enabling-network-media-bypass-in-lync-server-2013"></a><span data-ttu-id="8d9e2-103">在 Lync Server 2013 中启用网络媒体旁路</span><span class="sxs-lookup"><span data-stu-id="8d9e2-103">Enabling network media bypass in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8d9e2-104">_**上次修改的主题：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="8d9e2-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="8d9e2-105">媒体绕过设置在 Microsoft Lync Server 2013 部署中全局应用。</span><span class="sxs-lookup"><span data-stu-id="8d9e2-105">Media bypass settings apply globally across a Microsoft Lync Server 2013 deployment.</span></span> <span data-ttu-id="8d9e2-106">媒体旁路允许呼叫绕过中介服务器。</span><span class="sxs-lookup"><span data-stu-id="8d9e2-106">Media bypass allows calls to bypass the Mediation Server.</span></span> <span data-ttu-id="8d9e2-107">有关何时使用媒体旁路的详细信息，请参阅规划部分中的在 [Lync Server 2013 中规划媒体旁路](lync-server-2013-planning-for-media-bypass.md) 。</span><span class="sxs-lookup"><span data-stu-id="8d9e2-107">For details about when to use Media bypass, see [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) in the Planning section.</span></span>

<span data-ttu-id="8d9e2-108">您可以从 Lync Server 控制面板启用和配置媒体旁路。</span><span class="sxs-lookup"><span data-stu-id="8d9e2-108">You can enable and configure media bypass from the Lync Server Control Panel.</span></span>

<div>

## <a name="to-enable-and-configure-media-bypass"></a><span data-ttu-id="8d9e2-109">启用和配置媒体旁路</span><span class="sxs-lookup"><span data-stu-id="8d9e2-109">To enable and configure media bypass</span></span>

1.  <span data-ttu-id="8d9e2-110">从作为 RTCUniversalServerAdmins 组成员的用户帐户 (或具有等效的用户权限) 或分配给 CsAdministrator 角色，请登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="8d9e2-110">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="8d9e2-111">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="8d9e2-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="8d9e2-112">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="8d9e2-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="8d9e2-113">在左侧导航栏中，单击“网络配置”\*\*\*\*，然后单击“全局”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8d9e2-113">In the left navigation bar, click **Network Configuration** and then click **Global**.</span></span>

4.  <span data-ttu-id="8d9e2-114">在“全局”\*\*\*\* 页上，单击“全局”\*\*\*\* 配置。</span><span class="sxs-lookup"><span data-stu-id="8d9e2-114">On the **Global** page, click the **Global** configuration.</span></span> <span data-ttu-id="8d9e2-115">始终只有一种配置，并且总是名为 Global。</span><span class="sxs-lookup"><span data-stu-id="8d9e2-115">There is always only one configuration, and it is always named Global.</span></span>

5.  <span data-ttu-id="8d9e2-116">在 " **编辑** " 菜单上，单击 " **查看详细信息**"。</span><span class="sxs-lookup"><span data-stu-id="8d9e2-116">On the **Edit** menu, click **View details**.</span></span>

6.  <span data-ttu-id="8d9e2-117">在 " **编辑全局设置** " 页上，单击 " **启用媒体旁路** " 复选框。</span><span class="sxs-lookup"><span data-stu-id="8d9e2-117">On the **Edit Global Setting** page, click the **Enable media bypass** check box.</span></span>

7.  <span data-ttu-id="8d9e2-118">选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="8d9e2-118">Select one of the following options:</span></span>
    
      - <span data-ttu-id="8d9e2-119">**始终绕过**    选择此选项可在所有呼叫中尝试媒体旁路。</span><span class="sxs-lookup"><span data-stu-id="8d9e2-119">**Always bypass**   Select this option to attempt media bypass on all calls.</span></span> <span data-ttu-id="8d9e2-120">如果已启用呼叫允许控制 (CAC) ，此选项将不可用。</span><span class="sxs-lookup"><span data-stu-id="8d9e2-120">This option will be unavailable if call admission control (CAC) is enabled.</span></span> <span data-ttu-id="8d9e2-121">如果未启用 CAC，请在以下情况下选择此选项：</span><span class="sxs-lookup"><span data-stu-id="8d9e2-121">If CAC is not enabled, select this option in the following situations:</span></span>
        
          - <span data-ttu-id="8d9e2-122">无需带宽控制。</span><span class="sxs-lookup"><span data-stu-id="8d9e2-122">There is no need for bandwidth control.</span></span>
        
          - <span data-ttu-id="8d9e2-123">不需要进行细粒度配置来确定何时应应何时发生绕过。</span><span class="sxs-lookup"><span data-stu-id="8d9e2-123">There is no need for fine-grained configuration to determine when bypass should happen.</span></span>
        
          - <span data-ttu-id="8d9e2-124">网关和客户端之间存在完全连接。</span><span class="sxs-lookup"><span data-stu-id="8d9e2-124">There is full connectivity between gateways and clients.</span></span>
    
      - <span data-ttu-id="8d9e2-125">**使用网站和区域配置**    如果启用 CAC，则默认情况下此选项处于选中状态，并且无法更改。</span><span class="sxs-lookup"><span data-stu-id="8d9e2-125">**Use sites and region configuration**   If CAC is enabled, this option is selected by default and cannot be changed.</span></span> <span data-ttu-id="8d9e2-126">选择此选项后，将使用网络配置网站和区域确定何时可以使用媒体旁路。</span><span class="sxs-lookup"><span data-stu-id="8d9e2-126">When this option is selected, network configuration sites and regions will be used to determine when media bypass is possible.</span></span> <span data-ttu-id="8d9e2-127">如果选择此选项，则可以选择对未映射的网站启用旁路。</span><span class="sxs-lookup"><span data-stu-id="8d9e2-127">If you select this option, you can choose to enable bypass for sites that are not mapped.</span></span> <span data-ttu-id="8d9e2-128">仅当您具有一个或多个与不具有带宽约束的相同区域相关联的大型网站时，单击 "为 **非映射网站启用旁路** " 复选框 (例如，大型中央网站) ，并且您也有一些与具有带宽限制的相同区域相关联的分支站点。</span><span class="sxs-lookup"><span data-stu-id="8d9e2-128">Click the **Enable bypass for non-mapped sites** check box only if you have one or more large sites associated with the same region that do not have bandwidth constraints (for example, a large central site) and you also have some branch sites associated with the same region that do have bandwidth constraints.</span></span> <span data-ttu-id="8d9e2-129">为非映射网站启用旁路时，将简化配置，因为您仅指定与分支站点关联的子网，而不需要指定与所有站点关联的所有子网。</span><span class="sxs-lookup"><span data-stu-id="8d9e2-129">When you enable bypass for non-mapped sites, configuration is streamlined because you specify only the subnets associated with the branch sites rather than needing to specify all subnets associated with all sites.</span></span> <span data-ttu-id="8d9e2-130">如果启用了 CAC，我们建议您不要选中 "为 **非映射网站启用旁路** " 复选框。</span><span class="sxs-lookup"><span data-stu-id="8d9e2-130">We recommend that you do not select the **Enable bypass for non-mapped sites** check box if CAC is enabled.</span></span>

8.  <span data-ttu-id="8d9e2-131">单击 " **提交** " 以保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="8d9e2-131">Click **Commit** to save your changes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8d9e2-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8d9e2-132">See Also</span></span>


[<span data-ttu-id="8d9e2-133">在 Lync Server 2013 中禁用网络媒体旁路</span><span class="sxs-lookup"><span data-stu-id="8d9e2-133">Disabling network media bypass in Lync Server 2013</span></span>](lync-server-2013-disabling-network-media-bypass.md)  


[<span data-ttu-id="8d9e2-134">Lync Server 2013 中的全局媒体旁路选项</span><span class="sxs-lookup"><span data-stu-id="8d9e2-134">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  


[<span data-ttu-id="8d9e2-135">在 Lync Server 2013 中规划媒体旁路</span><span class="sxs-lookup"><span data-stu-id="8d9e2-135">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

