---
title: Skype 的服务管理业务服务器
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c99ee134-8294-4481-bb4e-710fe85a39ca
description: 本文介绍如何管理企业服务器拓扑的 Skype 中运行的服务。
ms.openlocfilehash: 4f5e1c4d91d5412470edebf3ed8d320101153da1
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32225326"
---
# <a name="manage-services-for-skype-for-business-server"></a><span data-ttu-id="aac2f-103">Skype 的服务管理业务服务器</span><span class="sxs-lookup"><span data-stu-id="aac2f-103">Manage services for Skype for Business Server</span></span>

<span data-ttu-id="aac2f-104">本文介绍如何管理企业服务器拓扑的 Skype 中运行的服务。</span><span class="sxs-lookup"><span data-stu-id="aac2f-104">This article describes how to manage services running in a Skype for Business Server topology.</span></span>
  
## <a name="view-a-list-of-computers-running-skype-for-business-server"></a><span data-ttu-id="aac2f-105">查看业务服务器运行 Skype 的计算机列表</span><span class="sxs-lookup"><span data-stu-id="aac2f-105">View a list of computers running Skype for Business Server</span></span>
<span data-ttu-id="aac2f-106"><a name="view_list"> </a></span><span class="sxs-lookup"><span data-stu-id="aac2f-106"></span></span>

<span data-ttu-id="aac2f-107">您可以使用业务 Server Control Panel 的 Skype 查看列表的所有计算机的业务服务器拓扑中运行 Skype 并查看每个服务状态。</span><span class="sxs-lookup"><span data-stu-id="aac2f-107">You can use Skype for Business Server Control Panel to view a list of all the computers that are running Skype for Business Server in your topology and see the service status of each.</span></span> <span data-ttu-id="aac2f-108">您可以通过计算机、 池或网站列表进行排序。</span><span class="sxs-lookup"><span data-stu-id="aac2f-108">You can sort the list by computer, pool, or site.</span></span> 
  
### <a name="to-view-a-list-of-computers-running-skype-for-business-server"></a><span data-ttu-id="aac2f-109">若要查看的计算机的业务服务器运行 Skype 列表</span><span class="sxs-lookup"><span data-stu-id="aac2f-109">To view a list of computers running Skype for Business Server</span></span>

1. <span data-ttu-id="aac2f-110">分配给任何预定义管理角色的 Skype 业务服务器的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="aac2f-110">From a user account that is assigned to any of the predefined administrative roles for Skype for Business Server, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="aac2f-111">有关业务服务器 Skype 中提供的预定义管理角色的详细信息，请参阅**Planning for Role-based Access Control**。</span><span class="sxs-lookup"><span data-stu-id="aac2f-111">For details about the predefined administrative roles available in Skype for Business Server, see **Planning for Role-Based Access Control**.</span></span>   
2. <span data-ttu-id="aac2f-112">打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="aac2f-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>   
3. <span data-ttu-id="aac2f-113">在左侧的导航栏中，单击**拓扑**，然后单击**状态**。</span><span class="sxs-lookup"><span data-stu-id="aac2f-113">In the left navigation bar, click **Topology** and then click **Status**.</span></span>   
4. <span data-ttu-id="aac2f-114">在**状态**页上执行根据需要以下任一操作：</span><span class="sxs-lookup"><span data-stu-id="aac2f-114">On the **Status** page, do any of the following as needed:</span></span>
   - <span data-ttu-id="aac2f-115">通过单击**计算机**、**池**或**网站**列标题，然后单击向上箭头或向下箭头对列表。</span><span class="sxs-lookup"><span data-stu-id="aac2f-115">Sort the list by clicking the **Computer**, **Pool**, or **Site** column heading, and then clicking the up arrow or the down arrow.</span></span> 
   - <span data-ttu-id="aac2f-116">单击**刷新**以查看最新的列表。</span><span class="sxs-lookup"><span data-stu-id="aac2f-116">Click **Refresh** to view the most up-to-date list.</span></span>  
   - <span data-ttu-id="aac2f-117">通过在搜索字段中键入计算机名称来搜索特定的计算机。</span><span class="sxs-lookup"><span data-stu-id="aac2f-117">Search for a specific computer by typing the computer name in the search field.</span></span>
    
## <a name="view-the-status-of-services-running-on-a-skype-for-business-server"></a><span data-ttu-id="aac2f-118">查看 Business server Skype 上运行的服务的状态</span><span class="sxs-lookup"><span data-stu-id="aac2f-118">View the status of services running on a Skype for Business server</span></span>
<span data-ttu-id="aac2f-119"><a name="view-status"> </a></span><span class="sxs-lookup"><span data-stu-id="aac2f-119"></span></span>

<span data-ttu-id="aac2f-120">您可以使用业务 Server Control Panel 的 Skype 查看您 Skype 企业服务器拓扑中特定计算机上运行并查看每种服务的状态的所有服务。</span><span class="sxs-lookup"><span data-stu-id="aac2f-120">You can use Skype for Business Server Control Panel to view all the services that are running on a specific computer in your Skype for Business Server topology and see the status of each service.</span></span>
  
### <a name="to-view-the-status-of-services-running-on-a-computer"></a><span data-ttu-id="aac2f-121">若要查看的计算机上运行的服务的状态</span><span class="sxs-lookup"><span data-stu-id="aac2f-121">To view the status of services running on a computer</span></span>

1. <span data-ttu-id="aac2f-122">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="aac2f-122">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
2. <span data-ttu-id="aac2f-123">打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="aac2f-123">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
3. <span data-ttu-id="aac2f-124">在左侧的导航栏中，单击**拓扑**。</span><span class="sxs-lookup"><span data-stu-id="aac2f-124">In the left navigation bar, click **Topology**.</span></span> 
4. <span data-ttu-id="aac2f-125">在**状态**页上排序或搜索列表中，根据需要，以查找您感兴趣的计算机，然后单击计算机名称。</span><span class="sxs-lookup"><span data-stu-id="aac2f-125">On the **Status** page, sort or search the list, as required, to find the computer you're interested in, and then click the computer name.</span></span>
5. <span data-ttu-id="aac2f-126">请执行以下任一操作：</span><span class="sxs-lookup"><span data-stu-id="aac2f-126">Do any of the following:</span></span>
   - <span data-ttu-id="aac2f-127">若要查看的计算机上运行的服务的最新状态，请单击**获取服务状态**。</span><span class="sxs-lookup"><span data-stu-id="aac2f-127">To see the latest status of services running on the computer, click **Get service status**.</span></span>
   - <span data-ttu-id="aac2f-128">要查看在每个服务的状态和计算机上运行的特定服务的列表，请单击**属性**，然后单击**关闭**以返回到列表。</span><span class="sxs-lookup"><span data-stu-id="aac2f-128">To see a list of specific services running on the computer and the status of each service, click **Properties**, and then click **Close** to return to the list.</span></span>
    
### <a name="viewing-service-status-with-windows-powershell-cmdlets"></a><span data-ttu-id="aac2f-129">使用 Windows Powershell cmdlet 查看服务状态</span><span class="sxs-lookup"><span data-stu-id="aac2f-129">Viewing service status with Windows Powershell cmdlets</span></span>

<span data-ttu-id="aac2f-130">您还可以使用 Windows PowerShell 和**Get-cswindowsservice** cmdlet 查看服务状态。</span><span class="sxs-lookup"><span data-stu-id="aac2f-130">You can also view service status by using Windows PowerShell and the **Get-CsWindowsService** cmdlet.</span></span> <span data-ttu-id="aac2f-131">从业务 Server 命令行管理程序 Skype 或 Windows PowerShell 远程会话，您可以运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="aac2f-131">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="aac2f-132">有关使用远程 Windows PowerShell 连接到 Skype 业务服务器的详细信息，请参阅博客文章["快速启动:: 管理 Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876)。</span><span class="sxs-lookup"><span data-stu-id="aac2f-132">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="aac2f-133">过程是相同的 Skype 业务服务器。</span><span class="sxs-lookup"><span data-stu-id="aac2f-133">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-view-service-status"></a><span data-ttu-id="aac2f-134">若要查看服务状态</span><span class="sxs-lookup"><span data-stu-id="aac2f-134">To view service status</span></span>

<span data-ttu-id="aac2f-135">若要查看的计算机上的服务状态，业务 Server 命令行管理程序中 Skype 键入类似于以下命令，然后按 Enter:</span><span class="sxs-lookup"><span data-stu-id="aac2f-135">To view service status on a computer, type a command similar to the following in the Skype for Business Server Management Shell and then press Enter:</span></span>
  
```
Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status
```

<span data-ttu-id="aac2f-136">此命令会返回类似下列信息：</span><span class="sxs-lookup"><span data-stu-id="aac2f-136">This command returns information similar to the following:</span></span>
  
|<span data-ttu-id="aac2f-137">**RoleName**</span><span class="sxs-lookup"><span data-stu-id="aac2f-137">**RoleName**</span></span>|<span data-ttu-id="aac2f-138">**状态**</span><span class="sxs-lookup"><span data-stu-id="aac2f-138">**Status**</span></span>|
|:-----|:-----|
|<span data-ttu-id="aac2f-139">{W3SVC}</span><span class="sxs-lookup"><span data-stu-id="aac2f-139">{W3SVC}</span></span>  <br/> |<span data-ttu-id="aac2f-140">运行</span><span class="sxs-lookup"><span data-stu-id="aac2f-140">Running</span></span>  <br/> |
|<span data-ttu-id="aac2f-141">{CentralManagement}</span><span class="sxs-lookup"><span data-stu-id="aac2f-141">{CentralManagement}</span></span>  <br/> | <span data-ttu-id="aac2f-142">运行</span><span class="sxs-lookup"><span data-stu-id="aac2f-142">Running</span></span> <br/> |
|<span data-ttu-id="aac2f-143">{Clsagent 的通信}</span><span class="sxs-lookup"><span data-stu-id="aac2f-143">{ClsAgent}</span></span>  <br/> |<span data-ttu-id="aac2f-144">运行</span><span class="sxs-lookup"><span data-stu-id="aac2f-144">Running</span></span>  <br/> |
|<span data-ttu-id="aac2f-145">{注册器，UserServer，EdgeServer}</span><span class="sxs-lookup"><span data-stu-id="aac2f-145">{Registrar, UserServer, EdgeServer}</span></span>  <br/> |<span data-ttu-id="aac2f-146">运行</span><span class="sxs-lookup"><span data-stu-id="aac2f-146">Running</span></span>  <br/> |
|<span data-ttu-id="aac2f-147">{ApplicationServer}</span><span class="sxs-lookup"><span data-stu-id="aac2f-147">{ApplicationServer}</span></span>  <br/> |<span data-ttu-id="aac2f-148">运行</span><span class="sxs-lookup"><span data-stu-id="aac2f-148">Running</span></span>  <br/> |
|<span data-ttu-id="aac2f-149">{ConferencingServer}</span><span class="sxs-lookup"><span data-stu-id="aac2f-149">{ConferencingServer}</span></span>  <br/> |<span data-ttu-id="aac2f-150">运行</span><span class="sxs-lookup"><span data-stu-id="aac2f-150">Running</span></span>  <br/> |
|<span data-ttu-id="aac2f-151">{MediationServer}</span><span class="sxs-lookup"><span data-stu-id="aac2f-151">{MediationServer}</span></span>  <br/> |<span data-ttu-id="aac2f-152">运行</span><span class="sxs-lookup"><span data-stu-id="aac2f-152">Running</span></span>  <br/> |
   
<span data-ttu-id="aac2f-153">有关详细信息，请参阅[Get-cswindowsservice](https://docs.microsoft.com/powershell/module/skype/get-cswindowsservice.md?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="aac2f-153">For details, see [Get-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/get-cswindowsservice.md?view=skype-ps).</span></span>
  
## <a name="view-details-about-a-service"></a><span data-ttu-id="aac2f-154">查看有关服务的详细信息</span><span class="sxs-lookup"><span data-stu-id="aac2f-154">View details about a service</span></span>
<span data-ttu-id="aac2f-155"><a name="view_details"> </a></span><span class="sxs-lookup"><span data-stu-id="aac2f-155"></span></span>

<span data-ttu-id="aac2f-156">您可以使用业务 Server Control Panel 的 Skype 查看有关您的拓扑中特定计算机运行每个服务的详细信息。</span><span class="sxs-lookup"><span data-stu-id="aac2f-156">You can use Skype for Business Server Control Panel to view details about each service that is running on a specific computer in your topology.</span></span> <span data-ttu-id="aac2f-157">您可以查看每个服务和详细信息，如关联的数据库、 端口和相关服务的状态。</span><span class="sxs-lookup"><span data-stu-id="aac2f-157">You can view the status of each service and details such as the associated databases, ports, and dependent services.</span></span>
  
### <a name="to-view-details-for-a-service"></a><span data-ttu-id="aac2f-158">若要查看服务详细信息</span><span class="sxs-lookup"><span data-stu-id="aac2f-158">To view details for a service</span></span>

1. <span data-ttu-id="aac2f-159">分配给任何预定义管理角色的 Skype 业务服务器的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="aac2f-159">From a user account that is assigned to any of the predefined administrative roles for Skype for Business Server, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="aac2f-160">有关业务服务器 Skype 中提供的预定义管理角色的详细信息，请参阅**Planning for Role-based Access Control**。</span><span class="sxs-lookup"><span data-stu-id="aac2f-160">For details about the predefined administrative roles available in Skype for Business Server, see **Planning for Role-Based Access Control**.</span></span>
2. <span data-ttu-id="aac2f-161">打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="aac2f-161">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
3. <span data-ttu-id="aac2f-162">在左侧的导航栏中，单击**拓扑**，然后单击**状态**。</span><span class="sxs-lookup"><span data-stu-id="aac2f-162">In the left navigation bar, click **Topology** and then click **Status**.</span></span>
4. <span data-ttu-id="aac2f-163">在**状态**页中，进行排序或搜索列表，然后单击您想要查看的计算机。</span><span class="sxs-lookup"><span data-stu-id="aac2f-163">In the **Status** page, sort or search through the list and then click the computer that you want to view.</span></span>
5. <span data-ttu-id="aac2f-164">单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="aac2f-164">Click **Properties**.</span></span>
6. <span data-ttu-id="aac2f-165">在**查看计算机详细信息**窗口中，有必要，对服务，对列表进行排序，然后单击您想要查看的服务。</span><span class="sxs-lookup"><span data-stu-id="aac2f-165">In the **View Computer Detail** window, sort the list of services, if necessary, and click the service you want to view.</span></span>
7. <span data-ttu-id="aac2f-166">执行根据需要以下任一操作：</span><span class="sxs-lookup"><span data-stu-id="aac2f-166">Do any of the following as needed:</span></span>
   - <span data-ttu-id="aac2f-167">若要查看特定服务的最新状态，请单击**获取服务状态**。</span><span class="sxs-lookup"><span data-stu-id="aac2f-167">To see the latest status of that specific service, click **Get service status**.</span></span>
   - <span data-ttu-id="aac2f-168">要查看特定服务的详细信息，请单击**属性**，然后单击**关闭**。</span><span class="sxs-lookup"><span data-stu-id="aac2f-168">To see the details for that specific service, click **Properties** and then click **Close**.</span></span>
   - <span data-ttu-id="aac2f-169">要返回拓扑中的所有计算机的列表，请单击**关闭**。</span><span class="sxs-lookup"><span data-stu-id="aac2f-169">To return to the list of all computers in your topology, click **Close**.</span></span>
    
## <a name="start-or-stop-skype-for-business-server-services"></a><span data-ttu-id="aac2f-170">启动或停止 Skype 业务 Server 服务</span><span class="sxs-lookup"><span data-stu-id="aac2f-170">Start or stop Skype for Business Server services</span></span>
<span data-ttu-id="aac2f-171"><a name="StartStop"> </a></span><span class="sxs-lookup"><span data-stu-id="aac2f-171"></span></span>

<span data-ttu-id="aac2f-172">您可以使用业务 Server Control Panel 的 Skype 启动或停止特定计算机上运行的业务服务器服务的所有 Skype 或者启动或都停止特定服务。</span><span class="sxs-lookup"><span data-stu-id="aac2f-172">You can use Skype for Business Server Control Panel to start or stop all the Skype for Business Server services running on a specific computer or to start or stop a specific service.</span></span>
  
### <a name="to-start-or-stop-all-skype-for-business-services-on-a-computer"></a><span data-ttu-id="aac2f-173">若要启动或停止所有 Skype 业务服务的计算机上</span><span class="sxs-lookup"><span data-stu-id="aac2f-173">To start or stop all Skype for Business services on a computer</span></span>

1. <span data-ttu-id="aac2f-174">从用户帐户是 RTCUniversalServerAdmins 组的成员 （或具有同等用户权限），或分配给 CsServerAdministrator 或 CsAdministrator 角色，登录到在其中在部署 Skype Business Server 网络中的任一计算机.</span><span class="sxs-lookup"><span data-stu-id="aac2f-174">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span> <span data-ttu-id="aac2f-175">您可以确定是否已将您分配 CsServerAdministrator 或 CsAdministrator RBAC 角色通过运行类似于以下命令：</span><span class="sxs-lookup"><span data-stu-id="aac2f-175">You can determine whether you have been assigned the CsServerAdministrator or the CsAdministrator RBAC role by running a command similar to the following:</span></span>
    
   ```
   Get-CsAdminRoleAssignment -Identity "kenmyer"
   ```

2. <span data-ttu-id="aac2f-176">打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="aac2f-176">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
3. <span data-ttu-id="aac2f-177">在左侧的导航栏中，单击**拓扑**，然后单击**状态**。</span><span class="sxs-lookup"><span data-stu-id="aac2f-177">In the left navigation bar, click **Topology** and then click **Status**.</span></span>
4. <span data-ttu-id="aac2f-178">**状态**页、 排序或搜索列表根据需要查找运行服务的计算机上要启动或停止，然后单击它。</span><span class="sxs-lookup"><span data-stu-id="aac2f-178">On the **Status** page, sort or search through the list as needed to find the computer that is running the services you want to start or stop, and then click it.</span></span>
5. <span data-ttu-id="aac2f-179">单击**操作**。</span><span class="sxs-lookup"><span data-stu-id="aac2f-179">Click **Action**.</span></span>
6. <span data-ttu-id="aac2f-180">单击**启动所有服务**或**停止所有服务**。</span><span class="sxs-lookup"><span data-stu-id="aac2f-180">Click **Start All services** or **Stop All services**.</span></span>
    
### <a name="to-start-or-stop-a-specific-service"></a><span data-ttu-id="aac2f-181">若要启动或停止特定服务</span><span class="sxs-lookup"><span data-stu-id="aac2f-181">To start or stop a specific service</span></span>

1. <span data-ttu-id="aac2f-182">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="aac2f-182">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
2. <span data-ttu-id="aac2f-183">打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="aac2f-183">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
3. <span data-ttu-id="aac2f-184">在左侧的导航栏中，单击**拓扑**，然后单击**状态**。</span><span class="sxs-lookup"><span data-stu-id="aac2f-184">In the left navigation bar, click **Topology** and then click **Status**.</span></span>
4. <span data-ttu-id="aac2f-185">**状态**页、 排序或搜索列表根据需要查找运行服务的计算机上要启动或停止，然后单击它。</span><span class="sxs-lookup"><span data-stu-id="aac2f-185">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span>
5. <span data-ttu-id="aac2f-186">单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="aac2f-186">Click **Properties**.</span></span>
6. <span data-ttu-id="aac2f-187">服务列表进行排序，如有必要，然后单击要启动或停止的服务。</span><span class="sxs-lookup"><span data-stu-id="aac2f-187">Sort the list of services, if necessary, and click the service you want to start or stop.</span></span>
7. <span data-ttu-id="aac2f-188">单击**操作**。</span><span class="sxs-lookup"><span data-stu-id="aac2f-188">Click **Action**.</span></span>
8. <span data-ttu-id="aac2f-189">单击**启动服务**或**停止服务**。</span><span class="sxs-lookup"><span data-stu-id="aac2f-189">Click **Start service** or **Stop service**.</span></span>
9. <span data-ttu-id="aac2f-190">单击“关闭”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="aac2f-190">Click **Close**.</span></span>
    
## <a name="prevent-sessions-for-services"></a><span data-ttu-id="aac2f-191">阻止服务的会话</span><span class="sxs-lookup"><span data-stu-id="aac2f-191">Prevent sessions for services</span></span>
<span data-ttu-id="aac2f-192"><a name="prevent_session"> </a></span><span class="sxs-lookup"><span data-stu-id="aac2f-192"></span></span>

<span data-ttu-id="aac2f-193">为特定计算机上运行的业务服务器服务的所有 Skype 阻止新会话或阻止新会话的特定业务服务器服务的 Skype，可以使用 Skype 的业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="aac2f-193">You can use Skype for Business Server Control Panel to prevent new sessions for all the Skype for Business Server services running on a specific computer or to prevent new sessions for a specific Skype for Business Server service.</span></span>
  
### <a name="to-prevent-new-sessions-for-all-skype-for-business-services-on-a-computer"></a><span data-ttu-id="aac2f-194">为业务服务的计算机上的所有 Skype 阻止新会话</span><span class="sxs-lookup"><span data-stu-id="aac2f-194">To prevent new sessions for all Skype for Business services on a computer</span></span>

1. <span data-ttu-id="aac2f-195">从用户帐户是 RTCUniversalServerAdmins 组的成员 （或具有同等用户权限），或分配给 CsServerAdministrator 或 CsAdministrator 角色，登录到在其中在部署 Skype Business Server 网络中的任一计算机.</span><span class="sxs-lookup"><span data-stu-id="aac2f-195">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
2. <span data-ttu-id="aac2f-196">打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="aac2f-196">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
3. <span data-ttu-id="aac2f-197">在左侧的导航栏中，单击**拓扑**，然后单击**状态**。</span><span class="sxs-lookup"><span data-stu-id="aac2f-197">In the left navigation bar, click **Topology** and then click **Status**.</span></span>
4. <span data-ttu-id="aac2f-198">在**状态**页上排序或列表作为搜索所需找到正在运行要为其阻止新会话，然后单击的服务的计算机。</span><span class="sxs-lookup"><span data-stu-id="aac2f-198">On the **Status** page, sort or search through the list as needed to find the computer that is running the services for which you want to prevent new sessions, and then click it.</span></span>
5. <span data-ttu-id="aac2f-199">单击**操作**。</span><span class="sxs-lookup"><span data-stu-id="aac2f-199">Click **Action**.</span></span>
6. <span data-ttu-id="aac2f-200">单击**阻止所有服务的新会话**。</span><span class="sxs-lookup"><span data-stu-id="aac2f-200">Click **Prevent new sessions for all services**.</span></span>
    
### <a name="to-prevent-new-sessions-for-a-specific-service"></a><span data-ttu-id="aac2f-201">阻止特定服务的新会话</span><span class="sxs-lookup"><span data-stu-id="aac2f-201">To prevent new sessions for a specific service</span></span>

1. <span data-ttu-id="aac2f-202">从用户帐户是 RTCUniversalServerAdmins 组的成员 （或具有同等用户权限），或分配给 CsServerAdministrator 或 CsAdministrator 角色，登录到在其中在部署 Skype Business Server 网络中的任一计算机.</span><span class="sxs-lookup"><span data-stu-id="aac2f-202">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
2. <span data-ttu-id="aac2f-203">打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="aac2f-203">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
3. <span data-ttu-id="aac2f-204">在左侧的导航栏中，单击**拓扑**，然后单击**状态**。</span><span class="sxs-lookup"><span data-stu-id="aac2f-204">In the left navigation bar, click **Topology** and then click **Status**.</span></span>
4. <span data-ttu-id="aac2f-205">**状态**页、 排序或搜索列表根据需要查找运行服务的计算机上要启动或停止，然后单击它。</span><span class="sxs-lookup"><span data-stu-id="aac2f-205">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span> 
5. <span data-ttu-id="aac2f-206">单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="aac2f-206">Click **Properties**.</span></span>
6. <span data-ttu-id="aac2f-207">如有必要，对服务，对列表进行排序，然后单击您要为其阻止新会话的服务。</span><span class="sxs-lookup"><span data-stu-id="aac2f-207">Sort the list of services, if necessary, and click the service for which you want to prevent new sessions.</span></span>
7. <span data-ttu-id="aac2f-208">单击**操作**。</span><span class="sxs-lookup"><span data-stu-id="aac2f-208">Click **Action**.</span></span>
8. <span data-ttu-id="aac2f-209">单击**阻止服务的新会话**。</span><span class="sxs-lookup"><span data-stu-id="aac2f-209">Click **Prevent new sessions for service**.</span></span>
9. <span data-ttu-id="aac2f-210">单击“关闭”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="aac2f-210">Click **Close**.</span></span>
    

