---
title: Lync Server 2013：查看网络区域信息
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing network region information
ms:assetid: 665740d0-a3ed-460f-8337-5ed945f90589
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688076(v=OCS.15)
ms:contentKeyID: 49733672
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8ba46c4ab3ed7fd6930faf359bc964605285a953
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138143"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="viewing-network-region-information-in-lync-server-2013"></a><span data-ttu-id="a2c3f-102">在 Lync Server 2013 中查看网络区域信息</span><span class="sxs-lookup"><span data-stu-id="a2c3f-102">Viewing network region information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a2c3f-103">_**上次修改的主题：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="a2c3f-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="a2c3f-104">网络区域将跨多个地理区域的网络的各个部分相互连接起来。</span><span class="sxs-lookup"><span data-stu-id="a2c3f-104">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="a2c3f-105">每个网络区域都必须与中央站点关联。</span><span class="sxs-lookup"><span data-stu-id="a2c3f-105">Every network region must be associated with a central site.</span></span> <span data-ttu-id="a2c3f-106">中央站点是运行呼叫允许控制 (CAC) 带宽策略服务的数据中心站点。</span><span class="sxs-lookup"><span data-stu-id="a2c3f-106">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="a2c3f-107">您可以使用 Lync Server 控制面板查看网络区域。</span><span class="sxs-lookup"><span data-stu-id="a2c3f-107">You can use Lync Server Control Panel to view network regions.</span></span> <span data-ttu-id="a2c3f-108">网络区域包括确定音频和视频连接是否可以使用通过 Internet 的备用路径的设置。</span><span class="sxs-lookup"><span data-stu-id="a2c3f-108">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="a2c3f-109">使用本主题可查看现有网络区域。</span><span class="sxs-lookup"><span data-stu-id="a2c3f-109">Use this topic to view existing network regions.</span></span> <span data-ttu-id="a2c3f-110">有关创建或修改现有网络区域的详细信息，请参阅[在 Lync Server 2013 中创建或修改网络区域](lync-server-2013-creating-or-modifying-network-regions.md)。</span><span class="sxs-lookup"><span data-stu-id="a2c3f-110">For details about creating or modifying existing network regions, see [Creating or modifying network regions in Lync Server 2013](lync-server-2013-creating-or-modifying-network-regions.md).</span></span>

<div>

## <a name="to-view-information-about-a-network-region-with-lync-server-control-panel"></a><span data-ttu-id="a2c3f-111">使用 Lync Server 控制面板查看有关网络区域的信息</span><span class="sxs-lookup"><span data-stu-id="a2c3f-111">To view information about a network region with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="a2c3f-112">从作为 RTCUniversalServerAdmins 组成员的用户帐户（或具有等效的用户权限）或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="a2c3f-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a2c3f-113">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="a2c3f-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a2c3f-114">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="a2c3f-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="a2c3f-115">在左侧导航栏中，单击“网络配置”\*\*\*\*，然后单击“区域”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a2c3f-115">In the left navigation bar, click **Network Configuration** and then click **Region**.</span></span>

4.  <span data-ttu-id="a2c3f-116">在“区域”\*\*\*\* 页上，单击要查看的区域。</span><span class="sxs-lookup"><span data-stu-id="a2c3f-116">On the **Region** page, click the region you want to view.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a2c3f-117">您一次只能查看一个区域。</span><span class="sxs-lookup"><span data-stu-id="a2c3f-117">You can only view one region at a time.</span></span>

    
    </div>

5.  <span data-ttu-id="a2c3f-118">在“编辑”\*\*\*\* 菜单上，单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a2c3f-118">On the **Edit** menu, click **Show details**.</span></span>

</div>

<div>

## <a name="viewing-network-region-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="a2c3f-119">使用 Windows PowerShell Cmdlet 查看网络区域信息</span><span class="sxs-lookup"><span data-stu-id="a2c3f-119">Viewing Network Region Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="a2c3f-120">您可以使用 Windows PowerShell 和**CsNetworkRegion** cmdlet 查看网络区域信息。</span><span class="sxs-lookup"><span data-stu-id="a2c3f-120">You can view network region information by using Windows PowerShell and the **Get-CsNetworkRegion** cmdlet.</span></span> <span data-ttu-id="a2c3f-121">您可以从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a2c3f-121">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="a2c3f-122">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)的 Lync Server Windows powershell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"。</span><span class="sxs-lookup"><span data-stu-id="a2c3f-122">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-network-region-information"></a><span data-ttu-id="a2c3f-123">查看网络区域信息</span><span class="sxs-lookup"><span data-stu-id="a2c3f-123">To view network region information</span></span>

  - <span data-ttu-id="a2c3f-124">若要查看有关所有网络区域的信息，请在 Lync Server 命令行管理程序中键入以下命令，然后按 ENTER：</span><span class="sxs-lookup"><span data-stu-id="a2c3f-124">To view information about all your network regions, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkRegion
    
    <span data-ttu-id="a2c3f-125">这将返回与以下类似的信息：</span><span class="sxs-lookup"><span data-stu-id="a2c3f-125">That will return information similar to this:</span></span>
    
        Identity         : Pacific Northwest
        Description      :
        BypassID         : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        CentralSite      : Site:Redmond1
        BWAlternatePaths : {BWPolicyModality=Audio;AlternatePath=True, 
                           BWPolicyModality=Video;AlternatePath=True}
        NetworkRegionID  : Pacific Northwest

</div>

<span data-ttu-id="a2c3f-126">有关详细信息，请参阅 [Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="a2c3f-126">For more information, see the help topic for the [Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a2c3f-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a2c3f-127">See Also</span></span>


[<span data-ttu-id="a2c3f-128">在 Lync Server 2013 中创建或修改网络区域</span><span class="sxs-lookup"><span data-stu-id="a2c3f-128">Creating or modifying network regions in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-network-regions.md)  
[<span data-ttu-id="a2c3f-129">在 Lync Server 2013 中删除现有网络区域</span><span class="sxs-lookup"><span data-stu-id="a2c3f-129">Deleting existing network regions in Lync Server 2013</span></span>](lync-server-2013-deleting-existing-network-regions.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

