---
title: 管理 Skype for Business Server 的服务
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c99ee134-8294-4481-bb4e-710fe85a39ca
description: 本文介绍如何管理在 Skype for Business Server 拓扑中运行的服务。
ms.openlocfilehash: 05bf37248e710424b7540fe0dbcc10338bd1f4bb
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816592"
---
# <a name="manage-services-for-skype-for-business-server"></a><span data-ttu-id="a3ac5-103">管理 Skype for Business Server 的服务</span><span class="sxs-lookup"><span data-stu-id="a3ac5-103">Manage services for Skype for Business Server</span></span>

<span data-ttu-id="a3ac5-104">本文介绍如何管理在 Skype for Business Server 拓扑中运行的服务。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-104">This article describes how to manage services running in a Skype for Business Server topology.</span></span>
  
## <a name="view-a-list-of-computers-running-skype-for-business-server"></a><span data-ttu-id="a3ac5-105">查看运行 Skype for Business Server 的计算机列表</span><span class="sxs-lookup"><span data-stu-id="a3ac5-105">View a list of computers running Skype for Business Server</span></span>
<span data-ttu-id="a3ac5-106"><a name="view_list"> </a></span><span class="sxs-lookup"><span data-stu-id="a3ac5-106"><a name="view_list"> </a></span></span>

<span data-ttu-id="a3ac5-107">可以使用 Skype for Business Server 控制面板查看拓扑中运行 Skype for Business Server 的所有计算机的列表，并查看每台计算机的服务状态。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-107">You can use Skype for Business Server Control Panel to view a list of all the computers that are running Skype for Business Server in your topology and see the service status of each.</span></span> <span data-ttu-id="a3ac5-108">可以按计算机、池或站点对列表进行排序。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-108">You can sort the list by computer, pool, or site.</span></span> 
  
### <a name="to-view-a-list-of-computers-running-skype-for-business-server"></a><span data-ttu-id="a3ac5-109">查看运行 Skype for Business Server 的计算机列表</span><span class="sxs-lookup"><span data-stu-id="a3ac5-109">To view a list of computers running Skype for Business Server</span></span>

1. <span data-ttu-id="a3ac5-110">从分配给 Skype for Business Server 的任何预定义管理角色的用户帐户，登录到内部部署中的任意计算机。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-110">From a user account that is assigned to any of the predefined administrative roles for Skype for Business Server, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="a3ac5-111">有关 Skype for Business Server 中可用的预定义管理角色 **的详细信息**，请参阅规划 Role-Based 访问控制。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-111">For details about the predefined administrative roles available in Skype for Business Server, see **Planning for Role-Based Access Control**.</span></span>   
2. <span data-ttu-id="a3ac5-112">打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>   
3. <span data-ttu-id="a3ac5-113">在左侧导航栏中，单击“拓扑”，然后单击“状态”。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-113">In the left navigation bar, click **Topology** and then click **Status**.</span></span>   
4. <span data-ttu-id="a3ac5-114">根据需要，在“状态”页上执行下列任意操作：</span><span class="sxs-lookup"><span data-stu-id="a3ac5-114">On the **Status** page, do any of the following as needed:</span></span>
   - <span data-ttu-id="a3ac5-115">单击“计算机”、“池”或“站点”列标题，然后单击向上箭头或向下箭头对列表进行排序。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-115">Sort the list by clicking the **Computer**, **Pool**, or **Site** column heading, and then clicking the up arrow or the down arrow.</span></span> 
   - <span data-ttu-id="a3ac5-116">单击“刷新”查看最新列表。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-116">Click **Refresh** to view the most up-to-date list.</span></span>  
   - <span data-ttu-id="a3ac5-117">通过在搜索字段中键入计算机名称来搜索特定的计算机。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-117">Search for a specific computer by typing the computer name in the search field.</span></span>
    
## <a name="view-the-status-of-services-running-on-a-skype-for-business-server"></a><span data-ttu-id="a3ac5-118">查看 Skype for Business 服务器上运行的服务的状态</span><span class="sxs-lookup"><span data-stu-id="a3ac5-118">View the status of services running on a Skype for Business server</span></span>
<span data-ttu-id="a3ac5-119"><a name="view-status"> </a></span><span class="sxs-lookup"><span data-stu-id="a3ac5-119"><a name="view-status"> </a></span></span>

<span data-ttu-id="a3ac5-120">可以使用 Skype for Business Server 控制面板查看 Skype for Business Server 拓扑中特定计算机上运行的所有服务，并查看每个服务的状态。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-120">You can use Skype for Business Server Control Panel to view all the services that are running on a specific computer in your Skype for Business Server topology and see the status of each service.</span></span>
  
### <a name="to-view-the-status-of-services-running-on-a-computer"></a><span data-ttu-id="a3ac5-121">查看计算机上运行的服务的状态</span><span class="sxs-lookup"><span data-stu-id="a3ac5-121">To view the status of services running on a computer</span></span>

1. <span data-ttu-id="a3ac5-122">使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-122">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
2. <span data-ttu-id="a3ac5-123">打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-123">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
3. <span data-ttu-id="a3ac5-124">在左侧导航栏中，单击“拓扑”。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-124">In the left navigation bar, click **Topology**.</span></span> 
4. <span data-ttu-id="a3ac5-125">在 **"状态** "页上，按需要对列表进行排序或搜索以查找您感兴趣的计算机，然后单击计算机名称。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-125">On the **Status** page, sort or search the list, as required, to find the computer you're interested in, and then click the computer name.</span></span>
5. <span data-ttu-id="a3ac5-126">执行下列任意操作：</span><span class="sxs-lookup"><span data-stu-id="a3ac5-126">Do any of the following:</span></span>
   - <span data-ttu-id="a3ac5-127">要查看计算机上运行的服务的最新状态，请单击“获取服务状态”。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-127">To see the latest status of services running on the computer, click **Get service status**.</span></span>
   - <span data-ttu-id="a3ac5-128">要查看计算机上运行的特定服务的列表和每种服务的状态，请单击“属性”，然后单击“关闭”返回到列表。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-128">To see a list of specific services running on the computer and the status of each service, click **Properties**, and then click **Close** to return to the list.</span></span>
    
### <a name="viewing-service-status-with-windows-powershell-cmdlets"></a><span data-ttu-id="a3ac5-129">使用 Windows Powershell cmdlet 查看服务状态</span><span class="sxs-lookup"><span data-stu-id="a3ac5-129">Viewing service status with Windows Powershell cmdlets</span></span>

<span data-ttu-id="a3ac5-130">您还可以使用 Windows PowerShell **和 Get-CsWindowsService** cmdlet 查看服务状态。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-130">You can also view service status by using Windows PowerShell and the **Get-CsWindowsService** cmdlet.</span></span> <span data-ttu-id="a3ac5-131">还可从 Skype for Business Server Management Shell 或 Windows PowerShell 远程会话运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-131">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="a3ac5-132">有关使用远程部署Windows PowerShell Skype for Business Server 的详细信息，请参阅博客文章"[快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"。](https://go.microsoft.com/fwlink/p/?linkId=255876)</span><span class="sxs-lookup"><span data-stu-id="a3ac5-132">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="a3ac5-133">此过程在 Skype for Business Server 中相同。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-133">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-view-service-status"></a><span data-ttu-id="a3ac5-134">查看服务状态</span><span class="sxs-lookup"><span data-stu-id="a3ac5-134">To view service status</span></span>

<span data-ttu-id="a3ac5-135">若要查看计算机上服务状态，请在 Skype for Business Server 命令行管理程序 中键入类似如下的命令，然后按 Enter：</span><span class="sxs-lookup"><span data-stu-id="a3ac5-135">To view service status on a computer, type a command similar to the following in the Skype for Business Server Management Shell and then press Enter:</span></span>
  
```PowerShell
Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status
```

<span data-ttu-id="a3ac5-136">此命令会返回类似下列信息：</span><span class="sxs-lookup"><span data-stu-id="a3ac5-136">This command returns information similar to the following:</span></span>
  
|<span data-ttu-id="a3ac5-137">**RoleName**</span><span class="sxs-lookup"><span data-stu-id="a3ac5-137">**RoleName**</span></span>|<span data-ttu-id="a3ac5-138">"状态"</span><span class="sxs-lookup"><span data-stu-id="a3ac5-138">**Status**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a3ac5-139">{W3SVC}</span><span class="sxs-lookup"><span data-stu-id="a3ac5-139">{W3SVC}</span></span>  <br/> |<span data-ttu-id="a3ac5-140">正在运行</span><span class="sxs-lookup"><span data-stu-id="a3ac5-140">Running</span></span>  <br/> |
|<span data-ttu-id="a3ac5-141">{CentralManagement}</span><span class="sxs-lookup"><span data-stu-id="a3ac5-141">{CentralManagement}</span></span>  <br/> | <span data-ttu-id="a3ac5-142">正在运行</span><span class="sxs-lookup"><span data-stu-id="a3ac5-142">Running</span></span> <br/> |
|<span data-ttu-id="a3ac5-143">{ClsAgent}</span><span class="sxs-lookup"><span data-stu-id="a3ac5-143">{ClsAgent}</span></span>  <br/> |<span data-ttu-id="a3ac5-144">正在运行</span><span class="sxs-lookup"><span data-stu-id="a3ac5-144">Running</span></span>  <br/> |
|<span data-ttu-id="a3ac5-145">{Registrar、UserServer、EdgeServer}</span><span class="sxs-lookup"><span data-stu-id="a3ac5-145">{Registrar, UserServer, EdgeServer}</span></span>  <br/> |<span data-ttu-id="a3ac5-146">正在运行</span><span class="sxs-lookup"><span data-stu-id="a3ac5-146">Running</span></span>  <br/> |
|<span data-ttu-id="a3ac5-147">{ApplicationServer}</span><span class="sxs-lookup"><span data-stu-id="a3ac5-147">{ApplicationServer}</span></span>  <br/> |<span data-ttu-id="a3ac5-148">正在运行</span><span class="sxs-lookup"><span data-stu-id="a3ac5-148">Running</span></span>  <br/> |
|<span data-ttu-id="a3ac5-149">{ConferencingServer}</span><span class="sxs-lookup"><span data-stu-id="a3ac5-149">{ConferencingServer}</span></span>  <br/> |<span data-ttu-id="a3ac5-150">正在运行</span><span class="sxs-lookup"><span data-stu-id="a3ac5-150">Running</span></span>  <br/> |
|<span data-ttu-id="a3ac5-151">{MediationServer}</span><span class="sxs-lookup"><span data-stu-id="a3ac5-151">{MediationServer}</span></span>  <br/> |<span data-ttu-id="a3ac5-152">正在运行</span><span class="sxs-lookup"><span data-stu-id="a3ac5-152">Running</span></span>  <br/> |
   
<span data-ttu-id="a3ac5-153">有关详细信息，请参阅[Get-CsWindowsService。](https://docs.microsoft.com/powershell/module/skype/get-cswindowsservice.md?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="a3ac5-153">For details, see [Get-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/get-cswindowsservice.md?view=skype-ps).</span></span>
  
## <a name="view-details-about-a-service"></a><span data-ttu-id="a3ac5-154">查看有关服务的详细信息</span><span class="sxs-lookup"><span data-stu-id="a3ac5-154">View details about a service</span></span>
<span data-ttu-id="a3ac5-155"><a name="view_details"> </a></span><span class="sxs-lookup"><span data-stu-id="a3ac5-155"><a name="view_details"> </a></span></span>

<span data-ttu-id="a3ac5-156">可以使用 Skype for Business Server 控制面板查看有关拓扑中特定计算机上运行的每个服务的详细信息。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-156">You can use Skype for Business Server Control Panel to view details about each service that is running on a specific computer in your topology.</span></span> <span data-ttu-id="a3ac5-157">可以查看每个服务的状态和详细信息（如关联的数据库、端口和相关服务）。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-157">You can view the status of each service and details such as the associated databases, ports, and dependent services.</span></span>
  
### <a name="to-view-details-for-a-service"></a><span data-ttu-id="a3ac5-158">查看服务的详细信息</span><span class="sxs-lookup"><span data-stu-id="a3ac5-158">To view details for a service</span></span>

1. <span data-ttu-id="a3ac5-159">从分配给 Skype for Business Server 的任何预定义管理角色的用户帐户，登录到内部部署中的任意计算机。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-159">From a user account that is assigned to any of the predefined administrative roles for Skype for Business Server, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="a3ac5-160">有关 Skype for Business Server 中可用的预定义管理角色 **的详细信息**，请参阅规划 Role-Based 访问控制。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-160">For details about the predefined administrative roles available in Skype for Business Server, see **Planning for Role-Based Access Control**.</span></span>
2. <span data-ttu-id="a3ac5-161">打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-161">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
3. <span data-ttu-id="a3ac5-162">在左侧导航栏中，单击“拓扑”，然后单击“状态”。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-162">In the left navigation bar, click **Topology** and then click **Status**.</span></span>
4. <span data-ttu-id="a3ac5-163">在“状态”页中，对列表进行排序或搜索列表，然后单击要查看的计算机。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-163">In the **Status** page, sort or search through the list and then click the computer that you want to view.</span></span>
5. <span data-ttu-id="a3ac5-164">单击“属性”。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-164">Click **Properties**.</span></span>
6. <span data-ttu-id="a3ac5-165">在“查看计算机详细信息”窗口中，根据需要对服务列表进行排序，然后单击要查看的服务。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-165">In the **View Computer Detail** window, sort the list of services, if necessary, and click the service you want to view.</span></span>
7. <span data-ttu-id="a3ac5-166">根据需要执行下列任意操作：</span><span class="sxs-lookup"><span data-stu-id="a3ac5-166">Do any of the following as needed:</span></span>
   - <span data-ttu-id="a3ac5-167">要查看特定服务的最新状态，请单击“获取服务状态”。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-167">To see the latest status of that specific service, click **Get service status**.</span></span>
   - <span data-ttu-id="a3ac5-168">要查看特定服务的详细信息，请单击“属性”，然后单击“关闭”。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-168">To see the details for that specific service, click **Properties** and then click **Close**.</span></span>
   - <span data-ttu-id="a3ac5-169">要返回拓扑中所有计算机的列表，请单击“关闭”。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-169">To return to the list of all computers in your topology, click **Close**.</span></span>
    
## <a name="start-or-stop-skype-for-business-server-services"></a><span data-ttu-id="a3ac5-170">启动或停止 Skype for Business Server 服务</span><span class="sxs-lookup"><span data-stu-id="a3ac5-170">Start or stop Skype for Business Server services</span></span>
<span data-ttu-id="a3ac5-171"><a name="StartStop"> </a></span><span class="sxs-lookup"><span data-stu-id="a3ac5-171"><a name="StartStop"> </a></span></span>

<span data-ttu-id="a3ac5-172">可以使用 Skype for Business Server 控制面板启动或停止特定计算机上运行的所有 Skype for Business Server 服务，或者启动或停止特定服务。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-172">You can use Skype for Business Server Control Panel to start or stop all the Skype for Business Server services running on a specific computer or to start or stop a specific service.</span></span>
  
### <a name="to-start-or-stop-all-skype-for-business-services-on-a-computer"></a><span data-ttu-id="a3ac5-173">启动或停止计算机上所有 Skype for Business 服务</span><span class="sxs-lookup"><span data-stu-id="a3ac5-173">To start or stop all Skype for Business services on a computer</span></span>

1. <span data-ttu-id="a3ac5-174">从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户，登录到部署 Skype for Business Server 的网络内的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-174">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span> <span data-ttu-id="a3ac5-175">通过运行类似于以下的命令，可以确定你已分配有 CsServerAdministrator 还是 CsAdministrator RBAC 角色：</span><span class="sxs-lookup"><span data-stu-id="a3ac5-175">You can determine whether you have been assigned the CsServerAdministrator or the CsAdministrator RBAC role by running a command similar to the following:</span></span>
    
   ```PowerShell
   Get-CsAdminRoleAssignment -Identity "kenmyer"
   ```

2. <span data-ttu-id="a3ac5-176">打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-176">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
3. <span data-ttu-id="a3ac5-177">在左侧导航栏中，单击“拓扑”，然后单击“状态”。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-177">In the left navigation bar, click **Topology** and then click **Status**.</span></span>
4. <span data-ttu-id="a3ac5-178">在“状态”页上，根据需要对列表进行排序或搜索列表，以查找正在运行要启动或停止的服务的计算机，然后单击该计算机。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-178">On the **Status** page, sort or search through the list as needed to find the computer that is running the services you want to start or stop, and then click it.</span></span>
5. <span data-ttu-id="a3ac5-179">单击“操作”。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-179">Click **Action**.</span></span>
6. <span data-ttu-id="a3ac5-180">单击“启动所有服务”或“停止所有服务”。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-180">Click **Start All services** or **Stop All services**.</span></span>
    
### <a name="to-start-or-stop-a-specific-service"></a><span data-ttu-id="a3ac5-181">启动或停止特定服务</span><span class="sxs-lookup"><span data-stu-id="a3ac5-181">To start or stop a specific service</span></span>

1. <span data-ttu-id="a3ac5-182">使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-182">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
2. <span data-ttu-id="a3ac5-183">打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-183">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
3. <span data-ttu-id="a3ac5-184">在左侧导航栏中，单击“拓扑”，然后单击“状态”。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-184">In the left navigation bar, click **Topology** and then click **Status**.</span></span>
4. <span data-ttu-id="a3ac5-185">在“状态”页上，根据需要对列表进行排序或搜索列表，以查找正在运行要启动或停止的服务的计算机，然后单击该计算机。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-185">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span>
5. <span data-ttu-id="a3ac5-186">单击“属性”。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-186">Click **Properties**.</span></span>
6. <span data-ttu-id="a3ac5-187">如有必要，对服务列表进行排序，然后单击要启动或停止的服务。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-187">Sort the list of services, if necessary, and click the service you want to start or stop.</span></span>
7. <span data-ttu-id="a3ac5-188">单击“操作”。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-188">Click **Action**.</span></span>
8. <span data-ttu-id="a3ac5-189">单击“启动服务”或“停止服务”。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-189">Click **Start service** or **Stop service**.</span></span>
9. <span data-ttu-id="a3ac5-190">单击“关闭”。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-190">Click **Close**.</span></span>
    
## <a name="prevent-sessions-for-services"></a><span data-ttu-id="a3ac5-191">阻止服务的会话</span><span class="sxs-lookup"><span data-stu-id="a3ac5-191">Prevent sessions for services</span></span>
<span data-ttu-id="a3ac5-192"><a name="prevent_session"> </a></span><span class="sxs-lookup"><span data-stu-id="a3ac5-192"><a name="prevent_session"> </a></span></span>

<span data-ttu-id="a3ac5-193">可以使用 Skype for Business Server 控制面板阻止特定计算机上运行的所有 Skype for Business Server 服务的新会话，或阻止特定 Skype for Business Server 服务的新会话。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-193">You can use Skype for Business Server Control Panel to prevent new sessions for all the Skype for Business Server services running on a specific computer or to prevent new sessions for a specific Skype for Business Server service.</span></span>
  
### <a name="to-prevent-new-sessions-for-all-skype-for-business-services-on-a-computer"></a><span data-ttu-id="a3ac5-194">阻止计算机上所有 Skype for Business 服务的新会话</span><span class="sxs-lookup"><span data-stu-id="a3ac5-194">To prevent new sessions for all Skype for Business services on a computer</span></span>

1. <span data-ttu-id="a3ac5-195">从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户，登录到部署 Skype for Business Server 的网络内的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-195">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
2. <span data-ttu-id="a3ac5-196">打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-196">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
3. <span data-ttu-id="a3ac5-197">在左侧导航栏中，单击“拓扑”，然后单击“状态”。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-197">In the left navigation bar, click **Topology** and then click **Status**.</span></span>
4. <span data-ttu-id="a3ac5-198">在“状态”页上，根据需要对列表进行排序或搜索，以查找正在运行要对其阻止新会话的服务的计算机，然后单击该计算机。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-198">On the **Status** page, sort or search through the list as needed to find the computer that is running the services for which you want to prevent new sessions, and then click it.</span></span>
5. <span data-ttu-id="a3ac5-199">单击“操作”。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-199">Click **Action**.</span></span>
6. <span data-ttu-id="a3ac5-200">单击“阻止所有服务的新会话”。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-200">Click **Prevent new sessions for all services**.</span></span>
    
### <a name="to-prevent-new-sessions-for-a-specific-service"></a><span data-ttu-id="a3ac5-201">阻止特定服务的新会话</span><span class="sxs-lookup"><span data-stu-id="a3ac5-201">To prevent new sessions for a specific service</span></span>

1. <span data-ttu-id="a3ac5-202">从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户，登录到部署 Skype for Business Server 的网络内的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-202">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
2. <span data-ttu-id="a3ac5-203">打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-203">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
3. <span data-ttu-id="a3ac5-204">在左侧导航栏中，单击“拓扑”，然后单击“状态”。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-204">In the left navigation bar, click **Topology** and then click **Status**.</span></span>
4. <span data-ttu-id="a3ac5-205">在“状态”页上，根据需要对列表进行排序或搜索列表，以查找正在运行要启动或停止的服务的计算机，然后单击该计算机。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-205">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span> 
5. <span data-ttu-id="a3ac5-206">单击“属性”。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-206">Click **Properties**.</span></span>
6. <span data-ttu-id="a3ac5-207">如有必要，对服务列表进行排序，然后单击要对其阻止新会话的服务。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-207">Sort the list of services, if necessary, and click the service for which you want to prevent new sessions.</span></span>
7. <span data-ttu-id="a3ac5-208">单击“操作”。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-208">Click **Action**.</span></span>
8. <span data-ttu-id="a3ac5-209">单击“阻止服务的新会话”。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-209">Click **Prevent new sessions for service**.</span></span>
9. <span data-ttu-id="a3ac5-210">单击“关闭”。</span><span class="sxs-lookup"><span data-stu-id="a3ac5-210">Click **Close**.</span></span>
    

