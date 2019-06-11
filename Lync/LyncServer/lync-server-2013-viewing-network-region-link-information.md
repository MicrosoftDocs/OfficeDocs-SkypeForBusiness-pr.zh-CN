---
title: 'Lync Server 2013: 查看网络区域链接信息'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Viewing network region link information
ms:assetid: 7b6b2ea2-83d8-4376-afb2-70e5d2cf6444
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688102(v=OCS.15)
ms:contentKeyID: 49733701
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce5bec9bdc656a33a34727f29bfc56ad39b2476a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845311"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-network-region-link-information-in-lync-server-2013"></a><span data-ttu-id="e417a-102">在 Lync Server 2013 中查看网络区域链接信息</span><span class="sxs-lookup"><span data-stu-id="e417a-102">Viewing network region link information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e417a-103">_**主题上次修改时间:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="e417a-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="e417a-104">您可以查看两个网络区域之间的链接, 作为呼叫许可控制 (CAC) 的一部分。</span><span class="sxs-lookup"><span data-stu-id="e417a-104">You can view links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="e417a-105">网络中的区域通过物理广域网络 (WAN) 连接进行链接。</span><span class="sxs-lookup"><span data-stu-id="e417a-105">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="e417a-106">可以使用 Lync Server "控制面板" 查看两个网络区域之间的现有链接。</span><span class="sxs-lookup"><span data-stu-id="e417a-106">You can use the Lync Server Control Panel to view an existing link between two network regions.</span></span> <span data-ttu-id="e417a-107">有关创建或修改网络区域链接的详细信息, 请参阅[在 Lync Server 2013 中配置网络区域链接](lync-server-2013-configuring-network-region-links.md)。</span><span class="sxs-lookup"><span data-stu-id="e417a-107">For details about creating or modifying network region link, see [Configuring network region links in Lync Server 2013](lync-server-2013-configuring-network-region-links.md).</span></span>

<div>

## <a name="to-view-a-network-region-link-in-lync-server-control-panel"></a><span data-ttu-id="e417a-108">在 Lync Server "控制面板" 中查看网络区域链接</span><span class="sxs-lookup"><span data-stu-id="e417a-108">To view a network region link in Lync Server Control Panel</span></span>

1.  <span data-ttu-id="e417a-109">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="e417a-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e417a-110">打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="e417a-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e417a-111">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="e417a-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e417a-112">在左侧导航栏中, 单击 "**网络配置**", 然后单击 "**区域链接**"。</span><span class="sxs-lookup"><span data-stu-id="e417a-112">In the left navigation bar, click **Network Configuration** and then click **Region Link**.</span></span>

4.  <span data-ttu-id="e417a-113">在 "**区域链接**" 页面上, 单击要查看的区域链接。</span><span class="sxs-lookup"><span data-stu-id="e417a-113">On the **Region Link** page, click the region link that you want to view.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e417a-114">一次只能查看有关一个区域链接的信息。</span><span class="sxs-lookup"><span data-stu-id="e417a-114">You can only view information about one region link at a time.</span></span>

    
    </div>

5.  <span data-ttu-id="e417a-115">从 "**编辑**" 菜单中, 选择 "**显示详细信息**"。</span><span class="sxs-lookup"><span data-stu-id="e417a-115">From the **Edit** menu, select **Show details**.</span></span>

</div>

<div>

## <a name="viewing-network-region-link-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="e417a-116">使用 Windows PowerShell Cmdlet 查看网络区域链接信息</span><span class="sxs-lookup"><span data-stu-id="e417a-116">Viewing Network Region Link Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="e417a-117">你可以使用 Windows PowerShell 和**CsNetworkRegionLink** cmdlet 查看网络区域链接。</span><span class="sxs-lookup"><span data-stu-id="e417a-117">You can view network region links by using Windows PowerShell and the **Get-CsNetworkRegionLink** cmdlet.</span></span> <span data-ttu-id="e417a-118">你可以从 Lync Server 2013 命令行管理程序或 Windows PowerShell 的远程会话运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e417a-118">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="e417a-119">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息, 请参阅 Lync Server Windows PowerShell 博客文章 "快速入门: 使用远程 PowerShell 管理 Microsoft Lync Server 2010" [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="e417a-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-network-region-link-information"></a><span data-ttu-id="e417a-120">查看网络区域链接信息</span><span class="sxs-lookup"><span data-stu-id="e417a-120">To view network region link information</span></span>

  - <span data-ttu-id="e417a-121">若要查看有关所有网络区域链接的信息, 请在 Lync Server 命令行管理程序中键入以下命令, 然后按 ENTER:</span><span class="sxs-lookup"><span data-stu-id="e417a-121">To view information about all your network region links, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkRegionLink
    
    <span data-ttu-id="e417a-122">此命令会返回类似下列信息：</span><span class="sxs-lookup"><span data-stu-id="e417a-122">This command returns information similar to the following:</span></span>
    
        Identity            : NorthwestToCalifornia
        BWPolicyProfileID   :
        NetworkRegionLinkID : NorthwestToCalifornia
        NetworkRegionID1    : Pacific Northwest
        NetworkRegionID2    : California

</div>

<span data-ttu-id="e417a-123">有关详细信息, 请参阅[CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)。</span><span class="sxs-lookup"><span data-stu-id="e417a-123">For details, see [Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e417a-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e417a-124">See Also</span></span>


[<span data-ttu-id="e417a-125">在 Lync Server 2013 中配置网络站点链接</span><span class="sxs-lookup"><span data-stu-id="e417a-125">Configuring network site links in Lync Server 2013</span></span>](lync-server-2013-configuring-network-site-links.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

