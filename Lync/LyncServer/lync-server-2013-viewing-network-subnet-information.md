---
title: 'Lync Server 2013: 查看网络子网信息'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Viewing network subnet information
ms:assetid: 46f165f2-efe3-4cc1-9fee-a78b7f2ed41e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688044(v=OCS.15)
ms:contentKeyID: 49733636
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a157746e40de8f4793fab24e7e91121779d7602e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845303"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-network-subnet-information-in-lync-server-2013"></a><span data-ttu-id="d0580-102">在 Lync Server 2013 中查看网络子网信息</span><span class="sxs-lookup"><span data-stu-id="d0580-102">Viewing network subnet information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d0580-103">_**主题上次修改时间:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="d0580-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="d0580-104">你可以使用以下过程查看网络子网。</span><span class="sxs-lookup"><span data-stu-id="d0580-104">You can use the following procedure to view a network subnet.</span></span> <span data-ttu-id="d0580-105">从 Lync Server 控制面板中, 您可以创建、修改或删除网络子网。</span><span class="sxs-lookup"><span data-stu-id="d0580-105">From the Lync Server Control Panel, you can create, modify, or delete a network subnet.</span></span> <span data-ttu-id="d0580-106">有关创建或修改网络子网的详细信息, 请参阅[在 Lync Server 2013 中创建或修改网络子网](lync-server-2013-create-or-modify-network-subnets.md)。</span><span class="sxs-lookup"><span data-stu-id="d0580-106">For details about creating or modifying network subnets, see [Create or modify network subnets in Lync Server 2013](lync-server-2013-create-or-modify-network-subnets.md).</span></span>

<div>

## <a name="to-view-a-network-subnet"></a><span data-ttu-id="d0580-107">查看网络子网</span><span class="sxs-lookup"><span data-stu-id="d0580-107">To view a network subnet</span></span>

1.  <span data-ttu-id="d0580-108">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="d0580-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d0580-109">打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="d0580-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d0580-110">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="d0580-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d0580-111">在左侧导航栏中, 单击 "**网络配置**", 然后单击 "**子网**"。</span><span class="sxs-lookup"><span data-stu-id="d0580-111">In the left navigation bar, click **Network Configuration** and then click **Subnet**.</span></span>

4.  <span data-ttu-id="d0580-112">在 "**子网**" 页面上, 单击要查看的子网。</span><span class="sxs-lookup"><span data-stu-id="d0580-112">On the **Subnet** page, click the subnet that you want to view.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d0580-113">一次只能查看一个子网。</span><span class="sxs-lookup"><span data-stu-id="d0580-113">You can only view one subnet at a time.</span></span>

    
    </div>

5.  <span data-ttu-id="d0580-114">在 "**编辑**" 菜单上, 单击 "**显示详细信息 ...**"。</span><span class="sxs-lookup"><span data-stu-id="d0580-114">On the **Edit** menu, click **Show details…**.</span></span>

</div>

<div>

## <a name="viewing-network-subnet-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="d0580-115">使用 Windows PowerShell Cmdlet 查看网络子网配置信息</span><span class="sxs-lookup"><span data-stu-id="d0580-115">Viewing Network Subnet Configuration Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="d0580-116">可使用 Windows PowerShell 和 CsNetworkSubnet cmdlet 查看网络子网信息。</span><span class="sxs-lookup"><span data-stu-id="d0580-116">Network subnet information can be viewed by using Windows PowerShell and the Get-CsNetworkSubnet cmdlet.</span></span> <span data-ttu-id="d0580-117">此 cmdlet 既可以从 Lync Server 2013 管理外壳运行, 也可以从 Windows PowerShell 的远程会话运行。</span><span class="sxs-lookup"><span data-stu-id="d0580-117">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="d0580-118">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息, 请参阅 Lync Server Windows PowerShell 博客文章 "快速入门: 使用远程 PowerShell 管理 Microsoft Lync Server 2010" [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="d0580-118">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-network-subnet-information"></a><span data-ttu-id="d0580-119">查看网络子网信息</span><span class="sxs-lookup"><span data-stu-id="d0580-119">To view network subnet information</span></span>

  - <span data-ttu-id="d0580-120">若要查看有关所有网络子网的信息, 请在 Lync Server 命令行管理程序中键入以下命令, 然后按 ENTER:</span><span class="sxs-lookup"><span data-stu-id="d0580-120">To view information about all your network subnets, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkSubnet
    
    <span data-ttu-id="d0580-121">这将返回与以下类似的信息：</span><span class="sxs-lookup"><span data-stu-id="d0580-121">That will return information similar to this:</span></span>
    
        Identity      : 172.11.15.0
        MaskBits      : 28
        Description   :
        NetworkSiteID : Redmond
        SubnetID      : 172.11.15.0

</div>

<span data-ttu-id="d0580-122">有关详细信息, 请参阅[CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="d0580-122">For more information, see the help topic for the [Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d0580-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d0580-123">See Also</span></span>


[<span data-ttu-id="d0580-124">在 Lync Server 2013 中创建或修改网络子网</span><span class="sxs-lookup"><span data-stu-id="d0580-124">Create or modify network subnets in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-network-subnets.md)  
[<span data-ttu-id="d0580-125">在 Lync Server 2013 中删除网络子网</span><span class="sxs-lookup"><span data-stu-id="d0580-125">Deleting network subnets in Lync Server 2013</span></span>](lync-server-2013-deleting-network-subnets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

