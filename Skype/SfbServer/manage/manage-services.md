---
title: 管理业务服务器 2015 Skype 的服务
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c99ee134-8294-4481-bb4e-710fe85a39ca
description: 本文介绍如何管理业务服务器 2015年拓扑 Skype 中运行的服务。
ms.openlocfilehash: f8406d473b1d2ae644ac56d071313d2b488169fa
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="manage-services-for-skype-for-business-server-2015"></a><span data-ttu-id="36619-103">管理业务服务器 2015 Skype 的服务</span><span class="sxs-lookup"><span data-stu-id="36619-103">Manage services for Skype for Business Server 2015</span></span>

<span data-ttu-id="36619-104">本文介绍如何管理业务服务器 2015年拓扑 Skype 中运行的服务。</span><span class="sxs-lookup"><span data-stu-id="36619-104">This article describes how to manage services running in a Skype for Business Server 2015 topology.</span></span>
  
## <a name="view-a-list-of-computers-running-skype-for-business-server-2015"></a><span data-ttu-id="36619-105">查看列表中的计算机运行 Skype 业务服务器 2015</span><span class="sxs-lookup"><span data-stu-id="36619-105">View a list of computers running Skype for Business Server 2015</span></span>
<span data-ttu-id="36619-106"><a name="view_list"> </a></span><span class="sxs-lookup"><span data-stu-id="36619-106"></span></span>

<span data-ttu-id="36619-107">可以使用 Skype 业务服务器控件面板以查看列表中的所有计算机的 Skype 正在为您的拓扑结构中的业务服务器 2015年和查看每个服务的状态。</span><span class="sxs-lookup"><span data-stu-id="36619-107">You can use Skype for Business Server Control Panel to view a list of all the computers that are running Skype for Business Server 2015 in your topology and see the service status of each.</span></span> <span data-ttu-id="36619-108">您可以通过计算机、 池或网站列表进行排序。</span><span class="sxs-lookup"><span data-stu-id="36619-108">You can sort the list by computer, pool, or site.</span></span> 
  
### <a name="to-view-a-list-of-computers-running-skype-for-business-server"></a><span data-ttu-id="36619-109">若要查看运行 Skype 业务服务器的计算机的列表</span><span class="sxs-lookup"><span data-stu-id="36619-109">To view a list of computers running Skype for Business Server</span></span>

1. <span data-ttu-id="36619-110">从分配给任何预定义的管理角色的 Skype 进行业务服务器 2015年的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="36619-110">From a user account that is assigned to any of the predefined administrative roles for Skype for Business Server 2015, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="36619-111">有关业务服务器 2015年的 Skype 中可用的预定义管理角色的详细信息，请参阅**规划基于角色的访问控制**。</span><span class="sxs-lookup"><span data-stu-id="36619-111">For details about the predefined administrative roles available in Skype for Business Server 2015, see **Planning for Role-Based Access Control**.</span></span>   
2. <span data-ttu-id="36619-112">打开浏览器窗口，然后输入管理员 URL 打开 Skype 业务服务器控件面板。</span><span class="sxs-lookup"><span data-stu-id="36619-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>   
3. <span data-ttu-id="36619-113">在左侧的导航栏中，单击**拓扑**，然后单击**状态**。</span><span class="sxs-lookup"><span data-stu-id="36619-113">In the left navigation bar, click **Topology** and then click **Status**.</span></span>   
4. <span data-ttu-id="36619-114">在**状态**页中，执行根据需要以下任一操作：</span><span class="sxs-lookup"><span data-stu-id="36619-114">On the **Status** page, do any of the following as needed:</span></span>
   - <span data-ttu-id="36619-115">对列表排序，单击**计算机**、**池**或**站点**列标题，然后单击向上箭头或向下箭头。</span><span class="sxs-lookup"><span data-stu-id="36619-115">Sort the list by clicking the **Computer**, **Pool**, or **Site** column heading, and then clicking the up arrow or the down arrow.</span></span> 
   - <span data-ttu-id="36619-116">单击**刷新**以查看最新的列表。</span><span class="sxs-lookup"><span data-stu-id="36619-116">Click **Refresh** to view the most up-to-date list.</span></span>  
   - <span data-ttu-id="36619-117">通过在搜索字段中键入计算机名搜索特定的计算机。</span><span class="sxs-lookup"><span data-stu-id="36619-117">Search for a specific computer by typing the computer name in the search field.</span></span>
    
## <a name="view-the-status-of-services-running-on-a-skype-for-business-2015-server"></a><span data-ttu-id="36619-118">查看在 Skype 业务 2015年服务器上运行的服务的状态</span><span class="sxs-lookup"><span data-stu-id="36619-118">View the status of services running on a Skype for Business 2015 server</span></span>
<span data-ttu-id="36619-119"><a name="view-status"> </a></span><span class="sxs-lookup"><span data-stu-id="36619-119"></span></span>

<span data-ttu-id="36619-120">可以使用 Skype 业务服务器控件面板来查看所有的服务的业务服务器拓扑结构您 Skype 在特定计算机上正在运行的每个服务的状态，请参阅。</span><span class="sxs-lookup"><span data-stu-id="36619-120">You can use Skype for Business Server Control Panel to view all the services that are running on a specific computer in your Skype for Business Server topology and see the status of each service.</span></span>
  
### <a name="to-view-the-status-of-services-running-on-a-computer"></a><span data-ttu-id="36619-121">若要查看计算机上运行的服务的状态</span><span class="sxs-lookup"><span data-stu-id="36619-121">To view the status of services running on a computer</span></span>

1. <span data-ttu-id="36619-122">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="36619-122">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
2. <span data-ttu-id="36619-123">打开浏览器窗口，然后输入管理员 URL 打开 Skype 业务服务器控件面板。</span><span class="sxs-lookup"><span data-stu-id="36619-123">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
3. <span data-ttu-id="36619-124">在左侧的导航栏中，单击**拓扑**。</span><span class="sxs-lookup"><span data-stu-id="36619-124">In the left navigation bar, click **Topology**.</span></span> 
4. <span data-ttu-id="36619-125">在**状态**页面上进行排序或搜索列表中的，根据需要，找到您感兴趣，该计算机，然后单击计算机名称。</span><span class="sxs-lookup"><span data-stu-id="36619-125">On the **Status** page, sort or search the list, as required, to find the computer you're interested in, and then click the computer name.</span></span>
5. <span data-ttu-id="36619-126">请执行以下任一操作：</span><span class="sxs-lookup"><span data-stu-id="36619-126">Do any of the following:</span></span>
   - <span data-ttu-id="36619-127">若要查看在计算机上运行的服务的最新状态，请单击**获取服务状态**。</span><span class="sxs-lookup"><span data-stu-id="36619-127">To see the latest status of services running on the computer, click **Get service status**.</span></span>
   - <span data-ttu-id="36619-128">若要查看特定计算机和每个服务的状态上运行的服务的列表，单击**属性**，然后单击**关闭**返回到列表。</span><span class="sxs-lookup"><span data-stu-id="36619-128">To see a list of specific services running on the computer and the status of each service, click **Properties**, and then click **Close** to return to the list.</span></span>
    
### <a name="viewing-service-status-with-windows-powershell-cmdlets"></a><span data-ttu-id="36619-129">查看 Windows Powershell cmdlet 的服务状态</span><span class="sxs-lookup"><span data-stu-id="36619-129">Viewing service status with Windows Powershell cmdlets</span></span>

<span data-ttu-id="36619-130">使用 Windows PowerShell 和**Get CsWindowsService** cmdlet，您还可以查看服务状态。</span><span class="sxs-lookup"><span data-stu-id="36619-130">You can also view service status by using Windows PowerShell and the **Get-CsWindowsService** cmdlet.</span></span> <span data-ttu-id="36619-131">从业务服务器管理外壳的 Skype 或 Windows PowerShell 的远程会话，您可以运行该 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="36619-131">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="36619-132">有关使用远程 Windows PowerShell Skype 业务服务器的连接的详细信息，请参阅博客文章["快速启动:: 管理 Microsoft Lync 服务器 2010年使用远程 PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876)。</span><span class="sxs-lookup"><span data-stu-id="36619-132">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="36619-133">该过程是相同的 Skype 业务服务器。</span><span class="sxs-lookup"><span data-stu-id="36619-133">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-view-service-status"></a><span data-ttu-id="36619-134">若要查看服务状态</span><span class="sxs-lookup"><span data-stu-id="36619-134">To view service status</span></span>

<span data-ttu-id="36619-135">若要查看计算机上的服务状态，键入类似于以下命令 Skype 业务服务器管理外壳程序，然后按 enter 键：</span><span class="sxs-lookup"><span data-stu-id="36619-135">To view service status on a computer, type a command similar to the following in the Skype for Business Server Management Shell and then press Enter:</span></span>
  
```
Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status
```

<span data-ttu-id="36619-136">此命令会返回类似下列信息：</span><span class="sxs-lookup"><span data-stu-id="36619-136">This command returns information similar to the following:</span></span>
  
|<span data-ttu-id="36619-137">**角色名**</span><span class="sxs-lookup"><span data-stu-id="36619-137">**RoleName**</span></span>|<span data-ttu-id="36619-138">**状态**</span><span class="sxs-lookup"><span data-stu-id="36619-138">**Status**</span></span>|
|:-----|:-----|
|<span data-ttu-id="36619-139">{W3SVC}</span><span class="sxs-lookup"><span data-stu-id="36619-139">{W3SVC}</span></span>  <br/> |<span data-ttu-id="36619-140">运行</span><span class="sxs-lookup"><span data-stu-id="36619-140">Running</span></span>  <br/> |
|<span data-ttu-id="36619-141">{CentralManagement}</span><span class="sxs-lookup"><span data-stu-id="36619-141">{CentralManagement}</span></span>  <br/> | <span data-ttu-id="36619-142">运行</span><span class="sxs-lookup"><span data-stu-id="36619-142">Running</span></span> <br/> |
|<span data-ttu-id="36619-143">{ClsAgent}</span><span class="sxs-lookup"><span data-stu-id="36619-143">{ClsAgent}</span></span>  <br/> |<span data-ttu-id="36619-144">运行</span><span class="sxs-lookup"><span data-stu-id="36619-144">Running</span></span>  <br/> |
|<span data-ttu-id="36619-145">{注册，UserServer，EdgeServer}</span><span class="sxs-lookup"><span data-stu-id="36619-145">{Registrar, UserServer, EdgeServer}</span></span>  <br/> |<span data-ttu-id="36619-146">运行</span><span class="sxs-lookup"><span data-stu-id="36619-146">Running</span></span>  <br/> |
|<span data-ttu-id="36619-147">{应用程序服务器}</span><span class="sxs-lookup"><span data-stu-id="36619-147">{ApplicationServer}</span></span>  <br/> |<span data-ttu-id="36619-148">运行</span><span class="sxs-lookup"><span data-stu-id="36619-148">Running</span></span>  <br/> |
|<span data-ttu-id="36619-149">{ConferencingServer}</span><span class="sxs-lookup"><span data-stu-id="36619-149">{ConferencingServer}</span></span>  <br/> |<span data-ttu-id="36619-150">运行</span><span class="sxs-lookup"><span data-stu-id="36619-150">Running</span></span>  <br/> |
|<span data-ttu-id="36619-151">{MediationServer}</span><span class="sxs-lookup"><span data-stu-id="36619-151">{MediationServer}</span></span>  <br/> |<span data-ttu-id="36619-152">运行</span><span class="sxs-lookup"><span data-stu-id="36619-152">Running</span></span>  <br/> |
   
<span data-ttu-id="36619-153">有关详细信息，请参阅[获取 CsWindowsService](https://docs.microsoft.com/powershell/module/skype/get-cswindowsservice.md?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="36619-153">For details, see [Get-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/get-cswindowsservice.md?view=skype-ps).</span></span>
  
## <a name="view-details-about-a-service"></a><span data-ttu-id="36619-154">查看有关服务的详细信息</span><span class="sxs-lookup"><span data-stu-id="36619-154">View details about a service</span></span>
<span data-ttu-id="36619-155"><a name="view_details"> </a></span><span class="sxs-lookup"><span data-stu-id="36619-155"></span></span>

<span data-ttu-id="36619-156">Skype 业务服务器控件面板用于查看有关每个服务的拓扑结构中的特定计算机上运行的详细信息。</span><span class="sxs-lookup"><span data-stu-id="36619-156">You can use Skype for Business Server Control Panel to view details about each service that is running on a specific computer in your topology.</span></span> <span data-ttu-id="36619-157">您可以查看每个服务和详细信息，如关联的数据库、 端口和相关服务的状态。</span><span class="sxs-lookup"><span data-stu-id="36619-157">You can view the status of each service and details such as the associated databases, ports, and dependent services.</span></span>
  
### <a name="to-view-details-for-a-service"></a><span data-ttu-id="36619-158">若要查看服务详细信息</span><span class="sxs-lookup"><span data-stu-id="36619-158">To view details for a service</span></span>

1. <span data-ttu-id="36619-159">从分配给任何预定义的管理角色的 Skype 进行业务服务器 2015年的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="36619-159">From a user account that is assigned to any of the predefined administrative roles for Skype for Business Server 2015, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="36619-160">有关业务服务器 2015年的 Skype 中可用的预定义管理角色的详细信息，请参阅**规划基于角色的访问控制**。</span><span class="sxs-lookup"><span data-stu-id="36619-160">For details about the predefined administrative roles available in Skype for Business Server 2015, see **Planning for Role-Based Access Control**.</span></span>
2. <span data-ttu-id="36619-161">打开浏览器窗口，然后输入管理员 URL 打开 Skype 业务服务器控件面板。</span><span class="sxs-lookup"><span data-stu-id="36619-161">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
3. <span data-ttu-id="36619-162">在左侧的导航栏中，单击**拓扑**，然后单击**状态**。</span><span class="sxs-lookup"><span data-stu-id="36619-162">In the left navigation bar, click **Topology** and then click **Status**.</span></span>
4. <span data-ttu-id="36619-163">在**状态**页面排序或搜索列表，然后单击您想要查看的计算机。</span><span class="sxs-lookup"><span data-stu-id="36619-163">In the **Status** page, sort or search through the list and then click the computer that you want to view.</span></span>
5. <span data-ttu-id="36619-164">单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="36619-164">Click **Properties**.</span></span>
6. <span data-ttu-id="36619-165">在**查看计算机详细信息**窗口中，排序列表中的服务，如有必要，并单击您要查看的服务。</span><span class="sxs-lookup"><span data-stu-id="36619-165">In the **View Computer Detail** window, sort the list of services, if necessary, and click the service you want to view.</span></span>
7. <span data-ttu-id="36619-166">执行根据需要下列任一操作：</span><span class="sxs-lookup"><span data-stu-id="36619-166">Do any of the following as needed:</span></span>
   - <span data-ttu-id="36619-167">若要查看该特定服务的最新状态，请单击**获取服务状态**。</span><span class="sxs-lookup"><span data-stu-id="36619-167">To see the latest status of that specific service, click **Get service status**.</span></span>
   - <span data-ttu-id="36619-168">若要查看有关该特定服务的详细信息，请单击**属性**，然后单击**关闭**。</span><span class="sxs-lookup"><span data-stu-id="36619-168">To see the details for that specific service, click **Properties** and then click **Close**.</span></span>
   - <span data-ttu-id="36619-169">若要返回到您的拓扑中的所有计算机的列表，请单击**关闭**。</span><span class="sxs-lookup"><span data-stu-id="36619-169">To return to the list of all computers in your topology, click **Close**.</span></span>
    
## <a name="start-or-stop-skype-for-business-server-2015-services"></a><span data-ttu-id="36619-170">启动或停止 Skype 业务服务器 2015年服务</span><span class="sxs-lookup"><span data-stu-id="36619-170">Start or stop Skype for Business Server 2015 services</span></span>
<span data-ttu-id="36619-171"><a name="StartStop"> </a></span><span class="sxs-lookup"><span data-stu-id="36619-171"></span></span>

<span data-ttu-id="36619-172">可以使用 Skype 业务服务器控制面板启动或停止的业务服务器 2015年服务在特定计算机上运行的所有 Skype 或要启动或都停止某个特定服务。</span><span class="sxs-lookup"><span data-stu-id="36619-172">You can use Skype for Business Server Control Panel to start or stop all the Skype for Business Server 2015 services running on a specific computer or to start or stop a specific service.</span></span>
  
### <a name="to-start-or-stop-all-skype-for-business-services-on-a-computer"></a><span data-ttu-id="36619-173">若要启动或停止计算机上的所有 Skype 业务服务</span><span class="sxs-lookup"><span data-stu-id="36619-173">To start or stop all Skype for Business services on a computer</span></span>

1. <span data-ttu-id="36619-174">从一个用户帐户，是 RTCUniversalServerAdmins 组的成员 （或具有相当的用户的权限），或者是指派到 CsServerAdministrator 或 CsAdministrator 的角色，在其中您部署 Skype 业务服务器的网络中任何计算机的登录2015。</span><span class="sxs-lookup"><span data-stu-id="36619-174">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2015.</span></span> <span data-ttu-id="36619-175">您可以确定是否您分配了 CsServerAdministrator 或 CsAdministrator RBAC 角色通过运行与以下类似的命令：</span><span class="sxs-lookup"><span data-stu-id="36619-175">You can determine whether you have been assigned the CsServerAdministrator or the CsAdministrator RBAC role by running a command similar to the following:</span></span>
    
  ```
  Get-CsAdminRoleAssignment -Identity "kenmyer"

  ```

2. <span data-ttu-id="36619-176">打开浏览器窗口，然后输入管理员 URL 打开 Skype 业务服务器控件面板。</span><span class="sxs-lookup"><span data-stu-id="36619-176">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
3. <span data-ttu-id="36619-177">在左侧的导航栏中，单击**拓扑**，然后单击**状态**。</span><span class="sxs-lookup"><span data-stu-id="36619-177">In the left navigation bar, click **Topology** and then click **Status**.</span></span>
4. <span data-ttu-id="36619-178">**状态**页面、 排序或搜索列表根据需要找到运行服务的计算机上您要开始或停止，然后再单击它。</span><span class="sxs-lookup"><span data-stu-id="36619-178">On the **Status** page, sort or search through the list as needed to find the computer that is running the services you want to start or stop, and then click it.</span></span>
5. <span data-ttu-id="36619-179">单击**操作**。</span><span class="sxs-lookup"><span data-stu-id="36619-179">Click **Action**.</span></span>
6. <span data-ttu-id="36619-180">单击**启动所有服务**或**全部停止服务**。</span><span class="sxs-lookup"><span data-stu-id="36619-180">Click **Start All services** or **Stop All services**.</span></span>
    
### <a name="to-start-or-stop-a-specific-service"></a><span data-ttu-id="36619-181">若要启动或停止特定服务</span><span class="sxs-lookup"><span data-stu-id="36619-181">To start or stop a specific service</span></span>

1. <span data-ttu-id="36619-182">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="36619-182">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
2. <span data-ttu-id="36619-183">打开浏览器窗口，然后输入管理员 URL 打开 Skype 业务服务器控件面板。</span><span class="sxs-lookup"><span data-stu-id="36619-183">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
3. <span data-ttu-id="36619-184">在左侧的导航栏中，单击**拓扑**，然后单击**状态**。</span><span class="sxs-lookup"><span data-stu-id="36619-184">In the left navigation bar, click **Topology** and then click **Status**.</span></span>
4. <span data-ttu-id="36619-185">**状态**页面、 排序或搜索列表根据需要找到正在运行服务的计算机上您要开始或停止，然后再单击它。</span><span class="sxs-lookup"><span data-stu-id="36619-185">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span>
5. <span data-ttu-id="36619-186">单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="36619-186">Click **Properties**.</span></span>
6. <span data-ttu-id="36619-187">排序列表中的服务，如有必要，并单击您要启动或停止的服务。</span><span class="sxs-lookup"><span data-stu-id="36619-187">Sort the list of services, if necessary, and click the service you want to start or stop.</span></span>
7. <span data-ttu-id="36619-188">单击**操作**。</span><span class="sxs-lookup"><span data-stu-id="36619-188">Click **Action**.</span></span>
8. <span data-ttu-id="36619-189">单击**启动服务**或**停止服务**。</span><span class="sxs-lookup"><span data-stu-id="36619-189">Click **Start service** or **Stop service**.</span></span>
9. <span data-ttu-id="36619-190">单击“关闭”****。</span><span class="sxs-lookup"><span data-stu-id="36619-190">Click **Close**.</span></span>
    
## <a name="prevent-sessions-for-services"></a><span data-ttu-id="36619-191">防止会话服务</span><span class="sxs-lookup"><span data-stu-id="36619-191">Prevent sessions for services</span></span>
<span data-ttu-id="36619-192"><a name="prevent_session"> </a></span><span class="sxs-lookup"><span data-stu-id="36619-192"></span></span>

<span data-ttu-id="36619-193">可以使用业务服务器控件面板的 Skype 业务服务器 2015年服务在特定计算机上运行的所有 Skype 为防止新的会话，或为特定业务服务器 2015年服务 Skype 防止新的会话。</span><span class="sxs-lookup"><span data-stu-id="36619-193">You can use Skype for Business Server Control Panel to prevent new sessions for all the Skype for Business Server 2015 services running on a specific computer or to prevent new sessions for a specific Skype for Business Server 2015 service.</span></span>
  
### <a name="to-prevent-new-sessions-for-all-skype-for-business-services-on-a-computer"></a><span data-ttu-id="36619-194">为所有业务服务的计算机上的 Skype 防止新会话</span><span class="sxs-lookup"><span data-stu-id="36619-194">To prevent new sessions for all Skype for Business services on a computer</span></span>

1. <span data-ttu-id="36619-195">从一个用户帐户，是 RTCUniversalServerAdmins 组的成员 （或具有相当的用户的权限），或者是指派到 CsServerAdministrator 或 CsAdministrator 的角色，在其中您部署 Skype 业务服务器的网络中任何计算机的登录2015。</span><span class="sxs-lookup"><span data-stu-id="36619-195">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2015.</span></span>
2. <span data-ttu-id="36619-196">打开浏览器窗口，然后输入管理员 URL 打开 Skype 业务服务器控件面板。</span><span class="sxs-lookup"><span data-stu-id="36619-196">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
3. <span data-ttu-id="36619-197">在左侧的导航栏中，单击**拓扑**，然后单击**状态**。</span><span class="sxs-lookup"><span data-stu-id="36619-197">In the left navigation bar, click **Topology** and then click **Status**.</span></span>
4. <span data-ttu-id="36619-198">在**状态**页面上进行排序或搜索列表需要找到该计算机正在运行的服务，要防止新的会话，然后单击它。</span><span class="sxs-lookup"><span data-stu-id="36619-198">On the **Status** page, sort or search through the list as needed to find the computer that is running the services for which you want to prevent new sessions, and then click it.</span></span>
5. <span data-ttu-id="36619-199">单击**操作**。</span><span class="sxs-lookup"><span data-stu-id="36619-199">Click **Action**.</span></span>
6. <span data-ttu-id="36619-200">单击**防止新会话中的所有服务**。</span><span class="sxs-lookup"><span data-stu-id="36619-200">Click **Prevent new sessions for all services**.</span></span>
    
### <a name="to-prevent-new-sessions-for-a-specific-service"></a><span data-ttu-id="36619-201">若要防止特定服务的新会话</span><span class="sxs-lookup"><span data-stu-id="36619-201">To prevent new sessions for a specific service</span></span>

1. <span data-ttu-id="36619-202">从一个用户帐户，是 RTCUniversalServerAdmins 组的成员 （或具有相当的用户的权限），或者是指派到 CsServerAdministrator 或 CsAdministrator 的角色，在其中您部署 Skype 业务服务器的网络中任何计算机的登录2015。</span><span class="sxs-lookup"><span data-stu-id="36619-202">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2015.</span></span>
2. <span data-ttu-id="36619-203">打开浏览器窗口，然后输入管理员 URL 打开 Skype 业务服务器控件面板。</span><span class="sxs-lookup"><span data-stu-id="36619-203">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
3. <span data-ttu-id="36619-204">在左侧的导航栏中，单击**拓扑**，然后单击**状态**。</span><span class="sxs-lookup"><span data-stu-id="36619-204">In the left navigation bar, click **Topology** and then click **Status**.</span></span>
4. <span data-ttu-id="36619-205">**状态**页面、 排序或搜索列表根据需要找到正在运行服务的计算机上您要开始或停止，然后再单击它。</span><span class="sxs-lookup"><span data-stu-id="36619-205">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span> 
5. <span data-ttu-id="36619-206">单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="36619-206">Click **Properties**.</span></span>
6. <span data-ttu-id="36619-207">排序列表中的服务，如有必要，并单击您要防止新会话的服务。</span><span class="sxs-lookup"><span data-stu-id="36619-207">Sort the list of services, if necessary, and click the service for which you want to prevent new sessions.</span></span>
7. <span data-ttu-id="36619-208">单击**操作**。</span><span class="sxs-lookup"><span data-stu-id="36619-208">Click **Action**.</span></span>
8. <span data-ttu-id="36619-209">单击**防止新会话的服务**。</span><span class="sxs-lookup"><span data-stu-id="36619-209">Click **Prevent new sessions for service**.</span></span>
9. <span data-ttu-id="36619-210">单击“关闭”****。</span><span class="sxs-lookup"><span data-stu-id="36619-210">Click **Close**.</span></span>
    

