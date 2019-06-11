---
title: 'Lync Server 2013: 查看计算机上运行的服务的状态'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View the status of services running on a computer
ms:assetid: f41918e7-4c02-431e-840a-88a1f36ae499
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182606(v=OCS.15)
ms:contentKeyID: 48185804
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 52f7b1628f9e9fcd99eea84ebda2cbfe934fc7d6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845332"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-the-status-of-services-running-on-a-computer-in-lync-server-2013"></a><span data-ttu-id="aada9-102">在 Lync Server 2013 中查看计算机上运行的服务的状态</span><span class="sxs-lookup"><span data-stu-id="aada9-102">View the status of services running on a computer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aada9-103">_**主题上次修改时间:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="aada9-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="aada9-104">你可以使用 Lync Server 2013 控制面板查看 Lync Server 拓扑中的特定计算机上运行的所有服务, 并查看每个服务的状态。</span><span class="sxs-lookup"><span data-stu-id="aada9-104">You can use Lync Server 2013 Control Panel to view all the services that are running on a specific computer in your Lync Server topology and see the status of each service.</span></span>

<div>

## <a name="to-view-the-status-of-services-running-on-a-computer"></a><span data-ttu-id="aada9-105">查看计算机上运行的服务的状态</span><span class="sxs-lookup"><span data-stu-id="aada9-105">To view the status of services running on a computer</span></span>

1.  <span data-ttu-id="aada9-106">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="aada9-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="aada9-107">打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="aada9-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="aada9-108">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="aada9-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="aada9-109">在左侧导航栏中, 单击 "**拓扑**"。</span><span class="sxs-lookup"><span data-stu-id="aada9-109">In the left navigation bar, click **Topology**.</span></span>

4.  <span data-ttu-id="aada9-110">在 "**状态**" 页面上, 根据需要对列表进行排序或搜索, 以查找感兴趣的计算机, 然后单击计算机名称。</span><span class="sxs-lookup"><span data-stu-id="aada9-110">On the **Status** page, sort or search the list, as required, to find the computer you’re interested in, and then click the computer name.</span></span>

5.  <span data-ttu-id="aada9-111">请执行以下任一操作：</span><span class="sxs-lookup"><span data-stu-id="aada9-111">Do any of the following:</span></span>
    
      - <span data-ttu-id="aada9-112">若要查看计算机上运行的服务的最新状态, 请单击 "**获取服务状态**"。</span><span class="sxs-lookup"><span data-stu-id="aada9-112">To see the latest status of services running on the computer, click **Get service status**.</span></span>
    
      - <span data-ttu-id="aada9-113">若要查看计算机上运行的特定服务的列表和每个服务的状态, 请单击 "**属性**", 然后单击 "**关闭**" 以返回到列表。</span><span class="sxs-lookup"><span data-stu-id="aada9-113">To see a list of specific services running on the computer and the status of each service, click **Properties**, and then click **Close** to return to the list.</span></span>

</div>

<div>

## <a name="viewing-service-status-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="aada9-114">使用 Windows PowerShell Cmdlet 查看服务状态</span><span class="sxs-lookup"><span data-stu-id="aada9-114">Viewing Service Status by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="aada9-115">你还可以使用 Windows PowerShell 和**CsWindowsService** cmdlet 查看服务状态。</span><span class="sxs-lookup"><span data-stu-id="aada9-115">You can also view service status by using Windows PowerShell and the **Get-CsWindowsService** cmdlet.</span></span> <span data-ttu-id="aada9-116">你可以从 Lync Server 2013 命令行管理程序或 Windows PowerShell 的远程会话运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="aada9-116">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="aada9-117">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息, 请参阅 Lync Server Windows PowerShell 博客文章 "快速入门: 使用远程 PowerShell 管理 Microsoft Lync Server 2010" [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="aada9-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-service-status"></a><span data-ttu-id="aada9-118">查看服务状态</span><span class="sxs-lookup"><span data-stu-id="aada9-118">To view service status</span></span>

  - <span data-ttu-id="aada9-119">若要查看计算机上的服务状态, 请在 Lync Server 命令行管理程序中键入类似于以下的命令, 然后按 Enter:</span><span class="sxs-lookup"><span data-stu-id="aada9-119">To view service status on a computer, type a command similar to the following in the Lync Server Management Shell and then press Enter:</span></span>
    
        Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status
    
    <span data-ttu-id="aada9-120">此命令会返回类似下列信息：</span><span class="sxs-lookup"><span data-stu-id="aada9-120">This command returns information similar to the following:</span></span>
    
        RoleName                                  Status
        --------                                  ------
        {W3SVC}                                   Running
        {CentralManagement}                       Running
        {ClsAgent}                                Running
        {Registrar, UserServer, EdgeServer}       Running
        {ApplicationServer}                       Running
        {ConferencingServer}                      Running
        {MediationServer}                         Running

</div>

<span data-ttu-id="aada9-121">有关详细信息, 请参阅[CsWindowsService](https://docs.microsoft.com/powershell/module/skype/Get-CsWindowsService)。</span><span class="sxs-lookup"><span data-stu-id="aada9-121">For details, see [Get-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/Get-CsWindowsService).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="aada9-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="aada9-122">See Also</span></span>


[<span data-ttu-id="aada9-123">在 Lync Server 2013 中管理设备、电话和客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="aada9-123">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

