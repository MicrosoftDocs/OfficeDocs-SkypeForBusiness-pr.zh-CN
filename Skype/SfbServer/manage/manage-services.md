---
title: 管理 Skype for business 服务器的服务
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c99ee134-8294-4481-bb4e-710fe85a39ca
description: 本文介绍如何管理在 Skype for Business 服务器拓扑中运行的服务。
ms.openlocfilehash: 76628840c37bdb0eb85d58887d8bfdcedd20f27c
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991667"
---
# <a name="manage-services-for-skype-for-business-server"></a><span data-ttu-id="3e7b7-103">管理 Skype for business 服务器的服务</span><span class="sxs-lookup"><span data-stu-id="3e7b7-103">Manage services for Skype for Business Server</span></span>

<span data-ttu-id="3e7b7-104">本文介绍如何管理在 Skype for Business 服务器拓扑中运行的服务。</span><span class="sxs-lookup"><span data-stu-id="3e7b7-104">This article describes how to manage services running in a Skype for Business Server topology.</span></span>
  
## <a name="view-a-list-of-computers-running-skype-for-business-server"></a><span data-ttu-id="3e7b7-105">查看运行 Skype for Business 服务器的计算机列表</span><span class="sxs-lookup"><span data-stu-id="3e7b7-105">View a list of computers running Skype for Business Server</span></span>
<span data-ttu-id="3e7b7-106"><a name="view_list"> </a></span><span class="sxs-lookup"><span data-stu-id="3e7b7-106"></span></span>

<span data-ttu-id="3e7b7-107">你可以使用 Skype for Business Server 控制面板查看你的拓扑中运行 Skype for Business 服务器的所有计算机的列表，并查看每个计算机的服务状态。</span><span class="sxs-lookup"><span data-stu-id="3e7b7-107">You can use Skype for Business Server Control Panel to view a list of all the computers that are running Skype for Business Server in your topology and see the service status of each.</span></span> <span data-ttu-id="3e7b7-108">你可以按计算机、池或网站对列表进行排序。</span><span class="sxs-lookup"><span data-stu-id="3e7b7-108">You can sort the list by computer, pool, or site.</span></span> 
  
### <a name="to-view-a-list-of-computers-running-skype-for-business-server"></a><span data-ttu-id="3e7b7-109">查看运行 Skype for Business 服务器的计算机列表</span><span class="sxs-lookup"><span data-stu-id="3e7b7-109">To view a list of computers running Skype for Business Server</span></span>

1. <span data-ttu-id="3e7b7-110">从分配给 Skype for business 服务器的任何预定义管理角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="3e7b7-110">From a user account that is assigned to any of the predefined administrative roles for Skype for Business Server, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="3e7b7-111">有关 Skype for Business Server 中可用的预定义管理角色的详细信息，请参阅**规划基于角色的访问控制**。</span><span class="sxs-lookup"><span data-stu-id="3e7b7-111">For details about the predefined administrative roles available in Skype for Business Server, see **Planning for Role-Based Access Control**.</span></span>   
2. <span data-ttu-id="3e7b7-112">打开一个浏览器窗口，然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。</span><span class="sxs-lookup"><span data-stu-id="3e7b7-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>   
3. <span data-ttu-id="3e7b7-113">在左侧导航栏中，单击 "**拓扑**"，然后单击 "**状态**"。</span><span class="sxs-lookup"><span data-stu-id="3e7b7-113">In the left navigation bar, click **Topology** and then click **Status**.</span></span>   
4. <span data-ttu-id="3e7b7-114">在 "**状态**" 页面上，根据需要执行下列任一操作：</span><span class="sxs-lookup"><span data-stu-id="3e7b7-114">On the **Status** page, do any of the following as needed:</span></span>
   - <span data-ttu-id="3e7b7-115">单击 "**计算机**"、"**池**" 或 "**网站**" 列标题，然后单击向上键或向下键，对列表进行排序。</span><span class="sxs-lookup"><span data-stu-id="3e7b7-115">Sort the list by clicking the **Computer**, **Pool**, or **Site** column heading, and then clicking the up arrow or the down arrow.</span></span> 
   - <span data-ttu-id="3e7b7-116">单击 "**刷新**" 以查看最新列表。</span><span class="sxs-lookup"><span data-stu-id="3e7b7-116">Click **Refresh** to view the most up-to-date list.</span></span>  
   - <span data-ttu-id="3e7b7-117">通过在 "搜索" 字段中键入计算机名称来搜索特定计算机。</span><span class="sxs-lookup"><span data-stu-id="3e7b7-117">Search for a specific computer by typing the computer name in the search field.</span></span>
    
## <a name="view-the-status-of-services-running-on-a-skype-for-business-server"></a><span data-ttu-id="3e7b7-118">查看 Skype for business 服务器上运行的服务的状态</span><span class="sxs-lookup"><span data-stu-id="3e7b7-118">View the status of services running on a Skype for Business server</span></span>
<span data-ttu-id="3e7b7-119"><a name="view-status"> </a></span><span class="sxs-lookup"><span data-stu-id="3e7b7-119"></span></span>

<span data-ttu-id="3e7b7-120">你可以使用 Skype for Business Server 控制面板查看 Skype for Business Server 拓扑中的特定计算机上运行的所有服务，并查看每个服务的状态。</span><span class="sxs-lookup"><span data-stu-id="3e7b7-120">You can use Skype for Business Server Control Panel to view all the services that are running on a specific computer in your Skype for Business Server topology and see the status of each service.</span></span>
  
### <a name="to-view-the-status-of-services-running-on-a-computer"></a><span data-ttu-id="3e7b7-121">查看计算机上运行的服务的状态</span><span class="sxs-lookup"><span data-stu-id="3e7b7-121">To view the status of services running on a computer</span></span>

1. <span data-ttu-id="3e7b7-122">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="3e7b7-122">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
2. <span data-ttu-id="3e7b7-123">打开一个浏览器窗口，然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。</span><span class="sxs-lookup"><span data-stu-id="3e7b7-123">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
3. <span data-ttu-id="3e7b7-124">在左侧导航栏中，单击 "**拓扑**"。</span><span class="sxs-lookup"><span data-stu-id="3e7b7-124">In the left navigation bar, click **Topology**.</span></span> 
4. <span data-ttu-id="3e7b7-125">在 "**状态**" 页面上，根据需要对列表进行排序或搜索，以查找感兴趣的计算机，然后单击计算机名称。</span><span class="sxs-lookup"><span data-stu-id="3e7b7-125">On the **Status** page, sort or search the list, as required, to find the computer you're interested in, and then click the computer name.</span></span>
5. <span data-ttu-id="3e7b7-126">请执行以下任一操作：</span><span class="sxs-lookup"><span data-stu-id="3e7b7-126">Do any of the following:</span></span>
   - <span data-ttu-id="3e7b7-127">若要查看计算机上运行的服务的最新状态，请单击 "**获取服务状态**"。</span><span class="sxs-lookup"><span data-stu-id="3e7b7-127">To see the latest status of services running on the computer, click **Get service status**.</span></span>
   - <span data-ttu-id="3e7b7-128">若要查看计算机上运行的特定服务的列表和每个服务的状态，请单击 "**属性**"，然后单击 "**关闭**" 以返回到列表。</span><span class="sxs-lookup"><span data-stu-id="3e7b7-128">To see a list of specific services running on the computer and the status of each service, click **Properties**, and then click **Close** to return to the list.</span></span>
    
### <a name="viewing-service-status-with-windows-powershell-cmdlets"></a><span data-ttu-id="3e7b7-129">通过 Windows Powershell cmdlet 查看服务状态</span><span class="sxs-lookup"><span data-stu-id="3e7b7-129">Viewing service status with Windows Powershell cmdlets</span></span>

<span data-ttu-id="3e7b7-130">你还可以使用 Windows PowerShell 和**CsWindowsService** cmdlet 查看服务状态。</span><span class="sxs-lookup"><span data-stu-id="3e7b7-130">You can also view service status by using Windows PowerShell and the **Get-CsWindowsService** cmdlet.</span></span> <span data-ttu-id="3e7b7-131">你可以从 Skype for Business Server Management Shell 或从 Windows PowerShell 的远程会话运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="3e7b7-131">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="3e7b7-132">有关使用远程 Windows PowerShell 连接到 Skype for Business 服务器的详细信息，请参阅博客文章["快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"](https://go.microsoft.com/fwlink/p/?linkId=255876)。</span><span class="sxs-lookup"><span data-stu-id="3e7b7-132">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="3e7b7-133">在 Skype for Business 服务器中，此过程是相同的。</span><span class="sxs-lookup"><span data-stu-id="3e7b7-133">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-view-service-status"></a><span data-ttu-id="3e7b7-134">查看服务状态</span><span class="sxs-lookup"><span data-stu-id="3e7b7-134">To view service status</span></span>

<span data-ttu-id="3e7b7-135">若要查看计算机上的服务状态，请在 Skype for Business Server 命令行管理器中键入类似于以下内容的命令，然后按 Enter：</span><span class="sxs-lookup"><span data-stu-id="3e7b7-135">To view service status on a computer, type a command similar to the following in the Skype for Business Server Management Shell and then press Enter:</span></span>
  
```PowerShell
Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status
```

<span data-ttu-id="3e7b7-136">此命令会返回类似下列信息：</span><span class="sxs-lookup"><span data-stu-id="3e7b7-136">This command returns information similar to the following:</span></span>
  
|<span data-ttu-id="3e7b7-137">**拥有**</span><span class="sxs-lookup"><span data-stu-id="3e7b7-137">**RoleName**</span></span>|<span data-ttu-id="3e7b7-138">**状态栏**</span><span class="sxs-lookup"><span data-stu-id="3e7b7-138">**Status**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3e7b7-139">W3SVC</span><span class="sxs-lookup"><span data-stu-id="3e7b7-139">{W3SVC}</span></span>  <br/> |<span data-ttu-id="3e7b7-140">运行</span><span class="sxs-lookup"><span data-stu-id="3e7b7-140">Running</span></span>  <br/> |
|<span data-ttu-id="3e7b7-141">{CentralManagement}</span><span class="sxs-lookup"><span data-stu-id="3e7b7-141">{CentralManagement}</span></span>  <br/> | <span data-ttu-id="3e7b7-142">运行</span><span class="sxs-lookup"><span data-stu-id="3e7b7-142">Running</span></span> <br/> |
|<span data-ttu-id="3e7b7-143">{ClsAgent}</span><span class="sxs-lookup"><span data-stu-id="3e7b7-143">{ClsAgent}</span></span>  <br/> |<span data-ttu-id="3e7b7-144">运行</span><span class="sxs-lookup"><span data-stu-id="3e7b7-144">Running</span></span>  <br/> |
|<span data-ttu-id="3e7b7-145">{注册机构，UserServer，EdgeServer}</span><span class="sxs-lookup"><span data-stu-id="3e7b7-145">{Registrar, UserServer, EdgeServer}</span></span>  <br/> |<span data-ttu-id="3e7b7-146">运行</span><span class="sxs-lookup"><span data-stu-id="3e7b7-146">Running</span></span>  <br/> |
|<span data-ttu-id="3e7b7-147">{ApplicationServer}</span><span class="sxs-lookup"><span data-stu-id="3e7b7-147">{ApplicationServer}</span></span>  <br/> |<span data-ttu-id="3e7b7-148">运行</span><span class="sxs-lookup"><span data-stu-id="3e7b7-148">Running</span></span>  <br/> |
|<span data-ttu-id="3e7b7-149">{ConferencingServer}</span><span class="sxs-lookup"><span data-stu-id="3e7b7-149">{ConferencingServer}</span></span>  <br/> |<span data-ttu-id="3e7b7-150">运行</span><span class="sxs-lookup"><span data-stu-id="3e7b7-150">Running</span></span>  <br/> |
|<span data-ttu-id="3e7b7-151">{MediationServer}</span><span class="sxs-lookup"><span data-stu-id="3e7b7-151">{MediationServer}</span></span>  <br/> |<span data-ttu-id="3e7b7-152">运行</span><span class="sxs-lookup"><span data-stu-id="3e7b7-152">Running</span></span>  <br/> |
   
<span data-ttu-id="3e7b7-153">有关详细信息，请参阅[CsWindowsService](https://docs.microsoft.com/powershell/module/skype/get-cswindowsservice.md?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="3e7b7-153">For details, see [Get-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/get-cswindowsservice.md?view=skype-ps).</span></span>
  
## <a name="view-details-about-a-service"></a><span data-ttu-id="3e7b7-154">查看有关服务的详细信息</span><span class="sxs-lookup"><span data-stu-id="3e7b7-154">View details about a service</span></span>
<span data-ttu-id="3e7b7-155"><a name="view_details"> </a></span><span class="sxs-lookup"><span data-stu-id="3e7b7-155"></span></span>

<span data-ttu-id="3e7b7-156">可以使用 Skype for Business Server 控制面板查看拓扑中特定计算机上运行的每个服务的详细信息。</span><span class="sxs-lookup"><span data-stu-id="3e7b7-156">You can use Skype for Business Server Control Panel to view details about each service that is running on a specific computer in your topology.</span></span> <span data-ttu-id="3e7b7-157">你可以查看每个服务的状态以及相关联的数据库、端口和依赖服务等详细信息。</span><span class="sxs-lookup"><span data-stu-id="3e7b7-157">You can view the status of each service and details such as the associated databases, ports, and dependent services.</span></span>
  
### <a name="to-view-details-for-a-service"></a><span data-ttu-id="3e7b7-158">查看服务的详细信息</span><span class="sxs-lookup"><span data-stu-id="3e7b7-158">To view details for a service</span></span>

1. <span data-ttu-id="3e7b7-159">从分配给 Skype for business 服务器的任何预定义管理角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="3e7b7-159">From a user account that is assigned to any of the predefined administrative roles for Skype for Business Server, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="3e7b7-160">有关 Skype for Business Server 中可用的预定义管理角色的详细信息，请参阅**规划基于角色的访问控制**。</span><span class="sxs-lookup"><span data-stu-id="3e7b7-160">For details about the predefined administrative roles available in Skype for Business Server, see **Planning for Role-Based Access Control**.</span></span>
2. <span data-ttu-id="3e7b7-161">打开一个浏览器窗口，然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。</span><span class="sxs-lookup"><span data-stu-id="3e7b7-161">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
3. <span data-ttu-id="3e7b7-162">在左侧导航栏中，单击 "**拓扑**"，然后单击 "**状态**"。</span><span class="sxs-lookup"><span data-stu-id="3e7b7-162">In the left navigation bar, click **Topology** and then click **Status**.</span></span>
4. <span data-ttu-id="3e7b7-163">在 "**状态**" 页面中，对列表进行排序或搜索，然后单击要查看的计算机。</span><span class="sxs-lookup"><span data-stu-id="3e7b7-163">In the **Status** page, sort or search through the list and then click the computer that you want to view.</span></span>
5. <span data-ttu-id="3e7b7-164">单击 "**属性**"。</span><span class="sxs-lookup"><span data-stu-id="3e7b7-164">Click **Properties**.</span></span>
6. <span data-ttu-id="3e7b7-165">在 "**查看计算机详细信息**" 窗口中，对服务列表进行排序（如有必要），然后单击要查看的服务。</span><span class="sxs-lookup"><span data-stu-id="3e7b7-165">In the **View Computer Detail** window, sort the list of services, if necessary, and click the service you want to view.</span></span>
7. <span data-ttu-id="3e7b7-166">根据需要执行下列任一操作：</span><span class="sxs-lookup"><span data-stu-id="3e7b7-166">Do any of the following as needed:</span></span>
   - <span data-ttu-id="3e7b7-167">若要查看该特定服务的最新状态，请单击 "**获取服务状态**"。</span><span class="sxs-lookup"><span data-stu-id="3e7b7-167">To see the latest status of that specific service, click **Get service status**.</span></span>
   - <span data-ttu-id="3e7b7-168">若要查看特定服务的详细信息，请单击 "**属性**"，然后单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="3e7b7-168">To see the details for that specific service, click **Properties** and then click **Close**.</span></span>
   - <span data-ttu-id="3e7b7-169">若要返回到拓扑中的所有计算机的列表，请单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="3e7b7-169">To return to the list of all computers in your topology, click **Close**.</span></span>
    
## <a name="start-or-stop-skype-for-business-server-services"></a><span data-ttu-id="3e7b7-170">启动或停止 Skype for Business 服务器服务</span><span class="sxs-lookup"><span data-stu-id="3e7b7-170">Start or stop Skype for Business Server services</span></span>
<span data-ttu-id="3e7b7-171"><a name="StartStop"> </a></span><span class="sxs-lookup"><span data-stu-id="3e7b7-171"></span></span>

<span data-ttu-id="3e7b7-172">可以使用 Skype for Business Server 控制面板启动或停止在特定计算机上运行的所有 Skype for business 服务器服务，或者启动或停止特定服务。</span><span class="sxs-lookup"><span data-stu-id="3e7b7-172">You can use Skype for Business Server Control Panel to start or stop all the Skype for Business Server services running on a specific computer or to start or stop a specific service.</span></span>
  
### <a name="to-start-or-stop-all-skype-for-business-services-on-a-computer"></a><span data-ttu-id="3e7b7-173">启动或停止计算机上的所有 Skype for Business 服务</span><span class="sxs-lookup"><span data-stu-id="3e7b7-173">To start or stop all Skype for Business services on a computer</span></span>

1. <span data-ttu-id="3e7b7-174">从 RTCUniversalServerAdmins 组的成员（或具有等效用户权限）或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户，登录到你部署了 Skype for Business 服务器的网络中的任何计算机.</span><span class="sxs-lookup"><span data-stu-id="3e7b7-174">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span> <span data-ttu-id="3e7b7-175">你可以通过运行如下所示的命令来确定你是否已分配 CsServerAdministrator 或 CsAdministrator RBAC 角色：</span><span class="sxs-lookup"><span data-stu-id="3e7b7-175">You can determine whether you have been assigned the CsServerAdministrator or the CsAdministrator RBAC role by running a command similar to the following:</span></span>
    
   ```PowerShell
   Get-CsAdminRoleAssignment -Identity "kenmyer"
   ```

2. <span data-ttu-id="3e7b7-176">打开一个浏览器窗口，然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。</span><span class="sxs-lookup"><span data-stu-id="3e7b7-176">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
3. <span data-ttu-id="3e7b7-177">在左侧导航栏中，单击 "**拓扑**"，然后单击 "**状态**"。</span><span class="sxs-lookup"><span data-stu-id="3e7b7-177">In the left navigation bar, click **Topology** and then click **Status**.</span></span>
4. <span data-ttu-id="3e7b7-178">在 "**状态**" 页面上，根据需要对列表进行排序或搜索以查找运行要启动或停止的服务的计算机，然后单击它。</span><span class="sxs-lookup"><span data-stu-id="3e7b7-178">On the **Status** page, sort or search through the list as needed to find the computer that is running the services you want to start or stop, and then click it.</span></span>
5. <span data-ttu-id="3e7b7-179">单击 "**操作**"。</span><span class="sxs-lookup"><span data-stu-id="3e7b7-179">Click **Action**.</span></span>
6. <span data-ttu-id="3e7b7-180">单击 "**启动所有服务**" 或 "**停止所有服务**"。</span><span class="sxs-lookup"><span data-stu-id="3e7b7-180">Click **Start All services** or **Stop All services**.</span></span>
    
### <a name="to-start-or-stop-a-specific-service"></a><span data-ttu-id="3e7b7-181">启动或停止特定服务</span><span class="sxs-lookup"><span data-stu-id="3e7b7-181">To start or stop a specific service</span></span>

1. <span data-ttu-id="3e7b7-182">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="3e7b7-182">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
2. <span data-ttu-id="3e7b7-183">打开一个浏览器窗口，然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。</span><span class="sxs-lookup"><span data-stu-id="3e7b7-183">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
3. <span data-ttu-id="3e7b7-184">在左侧导航栏中，单击 "**拓扑**"，然后单击 "**状态**"。</span><span class="sxs-lookup"><span data-stu-id="3e7b7-184">In the left navigation bar, click **Topology** and then click **Status**.</span></span>
4. <span data-ttu-id="3e7b7-185">在 "**状态**" 页面上，根据需要对列表进行排序或搜索以查找运行要启动或停止的服务的计算机，然后单击它。</span><span class="sxs-lookup"><span data-stu-id="3e7b7-185">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span>
5. <span data-ttu-id="3e7b7-186">单击 "**属性**"。</span><span class="sxs-lookup"><span data-stu-id="3e7b7-186">Click **Properties**.</span></span>
6. <span data-ttu-id="3e7b7-187">对服务列表进行排序（如有必要），然后单击要启动或停止的服务。</span><span class="sxs-lookup"><span data-stu-id="3e7b7-187">Sort the list of services, if necessary, and click the service you want to start or stop.</span></span>
7. <span data-ttu-id="3e7b7-188">单击 "**操作**"。</span><span class="sxs-lookup"><span data-stu-id="3e7b7-188">Click **Action**.</span></span>
8. <span data-ttu-id="3e7b7-189">单击 "**开始服务**" 或 "**停止服务**"。</span><span class="sxs-lookup"><span data-stu-id="3e7b7-189">Click **Start service** or **Stop service**.</span></span>
9. <span data-ttu-id="3e7b7-190">单击“关闭”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3e7b7-190">Click **Close**.</span></span>
    
## <a name="prevent-sessions-for-services"></a><span data-ttu-id="3e7b7-191">阻止服务的会话</span><span class="sxs-lookup"><span data-stu-id="3e7b7-191">Prevent sessions for services</span></span>
<span data-ttu-id="3e7b7-192"><a name="prevent_session"> </a></span><span class="sxs-lookup"><span data-stu-id="3e7b7-192"></span></span>

<span data-ttu-id="3e7b7-193">可以使用 Skype for Business Server 控制面板阻止在特定计算机上运行的所有 Skype for business 服务器服务的新会话或阻止特定 Skype for Business 服务器服务的新会话。</span><span class="sxs-lookup"><span data-stu-id="3e7b7-193">You can use Skype for Business Server Control Panel to prevent new sessions for all the Skype for Business Server services running on a specific computer or to prevent new sessions for a specific Skype for Business Server service.</span></span>
  
### <a name="to-prevent-new-sessions-for-all-skype-for-business-services-on-a-computer"></a><span data-ttu-id="3e7b7-194">阻止计算机上所有 Skype for Business 服务的新会话</span><span class="sxs-lookup"><span data-stu-id="3e7b7-194">To prevent new sessions for all Skype for Business services on a computer</span></span>

1. <span data-ttu-id="3e7b7-195">从 RTCUniversalServerAdmins 组的成员（或具有等效用户权限）或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户，登录到你部署了 Skype for Business 服务器的网络中的任何计算机.</span><span class="sxs-lookup"><span data-stu-id="3e7b7-195">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
2. <span data-ttu-id="3e7b7-196">打开一个浏览器窗口，然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。</span><span class="sxs-lookup"><span data-stu-id="3e7b7-196">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
3. <span data-ttu-id="3e7b7-197">在左侧导航栏中，单击 "**拓扑**"，然后单击 "**状态**"。</span><span class="sxs-lookup"><span data-stu-id="3e7b7-197">In the left navigation bar, click **Topology** and then click **Status**.</span></span>
4. <span data-ttu-id="3e7b7-198">在 "**状态**" 页面上，根据需要对列表进行排序或搜索以查找运行要阻止新会话的服务的计算机，然后单击该计算机。</span><span class="sxs-lookup"><span data-stu-id="3e7b7-198">On the **Status** page, sort or search through the list as needed to find the computer that is running the services for which you want to prevent new sessions, and then click it.</span></span>
5. <span data-ttu-id="3e7b7-199">单击 "**操作**"。</span><span class="sxs-lookup"><span data-stu-id="3e7b7-199">Click **Action**.</span></span>
6. <span data-ttu-id="3e7b7-200">单击 "**阻止所有服务的新会话**"。</span><span class="sxs-lookup"><span data-stu-id="3e7b7-200">Click **Prevent new sessions for all services**.</span></span>
    
### <a name="to-prevent-new-sessions-for-a-specific-service"></a><span data-ttu-id="3e7b7-201">阻止特定服务的新会话</span><span class="sxs-lookup"><span data-stu-id="3e7b7-201">To prevent new sessions for a specific service</span></span>

1. <span data-ttu-id="3e7b7-202">从 RTCUniversalServerAdmins 组的成员（或具有等效用户权限）或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户，登录到你部署了 Skype for Business 服务器的网络中的任何计算机.</span><span class="sxs-lookup"><span data-stu-id="3e7b7-202">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
2. <span data-ttu-id="3e7b7-203">打开一个浏览器窗口，然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。</span><span class="sxs-lookup"><span data-stu-id="3e7b7-203">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
3. <span data-ttu-id="3e7b7-204">在左侧导航栏中，单击 "**拓扑**"，然后单击 "**状态**"。</span><span class="sxs-lookup"><span data-stu-id="3e7b7-204">In the left navigation bar, click **Topology** and then click **Status**.</span></span>
4. <span data-ttu-id="3e7b7-205">在 "**状态**" 页面上，根据需要对列表进行排序或搜索以查找运行要启动或停止的服务的计算机，然后单击它。</span><span class="sxs-lookup"><span data-stu-id="3e7b7-205">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span> 
5. <span data-ttu-id="3e7b7-206">单击 "**属性**"。</span><span class="sxs-lookup"><span data-stu-id="3e7b7-206">Click **Properties**.</span></span>
6. <span data-ttu-id="3e7b7-207">对服务列表进行排序（如有必要），然后单击要阻止新会话的服务。</span><span class="sxs-lookup"><span data-stu-id="3e7b7-207">Sort the list of services, if necessary, and click the service for which you want to prevent new sessions.</span></span>
7. <span data-ttu-id="3e7b7-208">单击 "**操作**"。</span><span class="sxs-lookup"><span data-stu-id="3e7b7-208">Click **Action**.</span></span>
8. <span data-ttu-id="3e7b7-209">单击 "**阻止新的服务会话**"。</span><span class="sxs-lookup"><span data-stu-id="3e7b7-209">Click **Prevent new sessions for service**.</span></span>
9. <span data-ttu-id="3e7b7-210">单击“关闭”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3e7b7-210">Click **Close**.</span></span>
    

