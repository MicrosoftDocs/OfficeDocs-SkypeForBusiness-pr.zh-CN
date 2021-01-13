---
title: 在 Skype for Business Server 中管理服务
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
description: 了解如何查看服务状态、启动和停止服务以及阻止服务会话。
ms.openlocfilehash: 6071526febcd3a4c1cb925ae3fb704eca6db575c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826312"
---
# <a name="manage-services-in-skype-for-business-server"></a><span data-ttu-id="71302-103">在 Skype for Business Server 中管理服务</span><span class="sxs-lookup"><span data-stu-id="71302-103">Manage services in Skype for Business Server</span></span>

<span data-ttu-id="71302-104">可以使用 Skype for Business Server 控制面板查看拓扑中运行 Skype for Business Server 的所有计算机的列表，查看服务状态，启动或停止服务，以及阻止服务会话。</span><span class="sxs-lookup"><span data-stu-id="71302-104">You can use the Skype for Business Server Control Panel to view a list of all the computers that are running Skype for Business Server in your topology, view the status of services, start or stop services, and prevent sessions for services.</span></span>

- [<span data-ttu-id="71302-105">查看运行 Skype for Business Server 的计算机列表</span><span class="sxs-lookup"><span data-stu-id="71302-105">View a list of computers running Skype for Business Server</span></span>](#view-a-list-of-computers-running-skype-for-business-server)
- [<span data-ttu-id="71302-106">查看 Skype for Business 中计算机上运行的服务的状态</span><span class="sxs-lookup"><span data-stu-id="71302-106">View the status of services running on a computer in Skype for Business</span></span>](#view-the-status-of-services-running-on-a-computer-in-skype-for-business)
- [<span data-ttu-id="71302-107">启动或停止 Skype for Business 服务</span><span class="sxs-lookup"><span data-stu-id="71302-107">Start or stop Skype for Business services</span></span>](#start-or-stop-skype-for-business-services)
- [<span data-ttu-id="71302-108">阻止服务的会话</span><span class="sxs-lookup"><span data-stu-id="71302-108">Prevent sessions for services</span></span>](#prevent-sessions-for-services)

## <a name="view-a-list-of-computers-running-skype-for-business-server"></a><span data-ttu-id="71302-109">查看运行 Skype for Business Server 的计算机列表</span><span class="sxs-lookup"><span data-stu-id="71302-109">View a list of computers running Skype for Business Server</span></span>

<span data-ttu-id="71302-110">使用 Skype for Business Server 控制面板查看拓扑中运行 Skype for Business 的所有计算机的列表，并查看每台计算机的服务状态。</span><span class="sxs-lookup"><span data-stu-id="71302-110">Use the Skype for Business Server Control Panel to view a list of all the computers that are running Skype for Business in your topology and see the service status of each.</span></span> <span data-ttu-id="71302-111">可以按计算机、池或站点对列表进行排序。</span><span class="sxs-lookup"><span data-stu-id="71302-111">You can sort the list by computer, pool, or site.</span></span> 

1. <span data-ttu-id="71302-112">从分配给 Skype for Business Server 的任何预定义管理角色的用户帐户，登录到内部部署中的任意计算机。</span><span class="sxs-lookup"><span data-stu-id="71302-112">From a user account that is assigned to any of the predefined administrative roles for Skype for Business Server, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="71302-113">有关详细信息，请参阅基于角色[的访问控制 (RBAC) For Skype for Business Server。](../../plan-your-deployment/security/role-based-access-control-rbac.md)</span><span class="sxs-lookup"><span data-stu-id="71302-113">For more information, see [Role-based access control (RBAC) for Skype for Business Server](../../plan-your-deployment/security/role-based-access-control-rbac.md).</span></span>
2. <span data-ttu-id="71302-114">打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="71302-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="71302-115">有关可用于启动 Skype for Business Server 控制面板的不同方法的详细信息，请参阅安装和 [打开管理工具](../../management-tools/install-and-open-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="71302-115">For details about the different methods you can use to start the Skype for Business Server Control Panel, see [Install and open administrative tools](../../management-tools/install-and-open-administrative-tools.md).</span></span>
3. <span data-ttu-id="71302-116">在左侧导航栏中，单击“拓扑”，然后单击“状态”。</span><span class="sxs-lookup"><span data-stu-id="71302-116">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>
4. <span data-ttu-id="71302-117">在"状态"页上，根据需要执行下列任一操作：</span><span class="sxs-lookup"><span data-stu-id="71302-117">On the Status page, do either of the following as needed:</span></span>
    - <span data-ttu-id="71302-118">单击“计算机”、“池”或“站点”列标题，然后单击向上箭头或向下箭头对列表进行排序。</span><span class="sxs-lookup"><span data-stu-id="71302-118">Sort the list by clicking the **Computer**, **Pool**, or **Site** column heading, and then clicking the up arrow or the down arrow.</span></span>
    - <span data-ttu-id="71302-119">单击“刷新”查看最新列表。</span><span class="sxs-lookup"><span data-stu-id="71302-119">Click **Refresh** to view the most up-to-date list.</span></span>
    - <span data-ttu-id="71302-120">通过在搜索字段中键入计算机名称来搜索特定的计算机。</span><span class="sxs-lookup"><span data-stu-id="71302-120">Search for a specific computer by typing the computer name in the search field.</span></span>
   
## <a name="view-the-status-of-services-running-on-a-computer-in-skype-for-business"></a><span data-ttu-id="71302-121">查看 Skype for Business 中计算机上运行的服务的状态</span><span class="sxs-lookup"><span data-stu-id="71302-121">View the status of services running on a computer in Skype for Business</span></span>

<span data-ttu-id="71302-122">使用 Skype for Business Server 控制面板查看在 Skype for Business Server 拓扑中的特定计算机上运行的所有服务，并查看每个服务的状态。</span><span class="sxs-lookup"><span data-stu-id="71302-122">Use the Skype for Business Server Control Panel to view all the services that are running on a specific computer in your Skype for Business Server topology and see the status of each service.</span></span>

1. <span data-ttu-id="71302-123">使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="71302-123">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
2. <span data-ttu-id="71302-124">打开浏览器窗口，然后输入管理 URL 以打开控制面板。</span><span class="sxs-lookup"><span data-stu-id="71302-124">Open a browser window, and then enter the Admin URL to open the Control Panel.</span></span> <span data-ttu-id="71302-125">有关可用于启动 Skype for Business Server 控制面板的不同方法的详细信息，请参阅安装和 [打开管理工具](../../management-tools/install-and-open-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="71302-125">For details about the different methods you can use to start the Skype for Business Server Control Panel, see [Install and open administrative tools](../../management-tools/install-and-open-administrative-tools.md).</span></span>
3. <span data-ttu-id="71302-126">在左侧导航栏中，单击“拓扑”。</span><span class="sxs-lookup"><span data-stu-id="71302-126">In the left navigation bar, click **Topology**.</span></span>
4. <span data-ttu-id="71302-127">在“状态”页上，根据需要对列表进行分类或搜索以查找您感兴趣的计算机，然后单击该计算机的名称。</span><span class="sxs-lookup"><span data-stu-id="71302-127">On the Status page, sort or search the list, as required, to find the computer you’re interested in, and then click the computer name.</span></span>
5. <span data-ttu-id="71302-128">执行下列任一操作：</span><span class="sxs-lookup"><span data-stu-id="71302-128">Do either of the following:</span></span>
    - <span data-ttu-id="71302-129">要查看计算机上运行的服务的最新状态，请单击“获取服务状态”。</span><span class="sxs-lookup"><span data-stu-id="71302-129">To see the latest status of services running on the computer, click **Get service status**.</span></span>
    - <span data-ttu-id="71302-130">要查看计算机上运行的特定服务的列表和每种服务的状态，请单击“属性”，然后单击“关闭”返回到列表。</span><span class="sxs-lookup"><span data-stu-id="71302-130">To see a list of specific services running on the computer and the status of each service, click **Properties**, and then click **Close** to return to the list.</span></span>

### <a name="viewing-service-status-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="71302-131">使用 Cmdlet Windows PowerShell服务状态</span><span class="sxs-lookup"><span data-stu-id="71302-131">Viewing service status by using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="71302-132">您还可以使用 Windows PowerShell 和 Get-CsWindowsService cmdlet 查看服务状态。</span><span class="sxs-lookup"><span data-stu-id="71302-132">You can also view service status by using Windows PowerShell and the Get-CsWindowsService cmdlet.</span></span> <span data-ttu-id="71302-133">还可从 Skype for Business Server Management Shell 或 Windows PowerShell 远程会话运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="71302-133">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="71302-134">有关详细信息，请参阅 [Skype for Business Server 命令行管理程序](../management-shell.md)。</span><span class="sxs-lookup"><span data-stu-id="71302-134">For more information, see [Skype for Business Server Management Shell](../management-shell.md).</span></span>

<span data-ttu-id="71302-135">**查看服务状态**</span><span class="sxs-lookup"><span data-stu-id="71302-135">**To view service status**</span></span>

<span data-ttu-id="71302-136">若要查看计算机上服务状态，请在 Skype for Business Server 命令行管理程序 中键入类似如下的命令，然后按 Enter：</span><span class="sxs-lookup"><span data-stu-id="71302-136">To view service status on a computer, type a command similar to the following in the Skype for Business Server Management Shell, and then press Enter:</span></span>

```powershell
Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status
```

<span data-ttu-id="71302-137">此命令会返回类似下列信息：</span><span class="sxs-lookup"><span data-stu-id="71302-137">This command returns information similar to the following:</span></span>

```console
RoleName                                  Status
--------                                  ------
{W3SVC}                                   Running
{CentralManagement}                       Running
{ClsAgent}                                Running
{Registrar, UserServer, EdgeServer}       Running
{ApplicationServer}                       Running
{ConferencingServer}                      Running
{MediationServer}                         Running
```

<span data-ttu-id="71302-138">有关详细信息，请参阅[Get-CsWindowsService。](https://docs.microsoft.com/powershell/module/skype/Get-CsWindowsService)</span><span class="sxs-lookup"><span data-stu-id="71302-138">For details, see [Get-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/Get-CsWindowsService).</span></span>

## <a name="start-or-stop-skype-for-business-services"></a><span data-ttu-id="71302-139">启动或停止 Skype for Business 服务</span><span class="sxs-lookup"><span data-stu-id="71302-139">Start or stop Skype for Business services</span></span>

<span data-ttu-id="71302-140">使用 Skype for Business Server 控制面板启动或停止特定计算机上运行的所有 Skype for Business Server 服务，或启动或停止特定服务。</span><span class="sxs-lookup"><span data-stu-id="71302-140">Use the Skype for Business Server Control Panel to start or stop all the Skype for Business Server services running on a specific computer or to start or stop a specific service.</span></span>

### <a name="start-or-stop-all-skype-for-business-server-services-on-a-computer"></a><span data-ttu-id="71302-141">在计算机上启动或停止所有 Skype for Business Server 服务</span><span class="sxs-lookup"><span data-stu-id="71302-141">Start or stop all Skype for Business Server services on a computer</span></span>

1. <span data-ttu-id="71302-142">从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户，登录到部署 Skype for Business Server 的网络内的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="71302-142">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span> <span data-ttu-id="71302-143">通过运行类似于以下的命令，可以确定你已分配有 CsServerAdministrator 还是 CsAdministrator RBAC 角色：</span><span class="sxs-lookup"><span data-stu-id="71302-143">You can determine whether you have been assigned the CsServerAdministrator or the CsAdministrator RBAC role by running a command similar to the following:</span></span>

    ```powershell
    Get-CsAdminRoleAssignment -Identity "kenmyer"`
    ```

2. <span data-ttu-id="71302-144">打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="71302-144">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="71302-145">有关可用于启动 Skype for Business Server 控制面板的不同方法的详细信息，请参阅安装和 [打开管理工具](../../management-tools/install-and-open-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="71302-145">For details about the different methods you can use to start the Skype for Business Server Control Panel, see [Install and open administrative tools](../../management-tools/install-and-open-administrative-tools.md).</span></span>
3. <span data-ttu-id="71302-146">在左侧导航栏中，单击“拓扑”，然后单击“状态”。</span><span class="sxs-lookup"><span data-stu-id="71302-146">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>
4. <span data-ttu-id="71302-147">在“状态”页上，根据需要对列表进行排序或搜索列表，以查找正在运行要启动或停止的服务的计算机，然后单击该计算机。</span><span class="sxs-lookup"><span data-stu-id="71302-147">On the Status page, sort or search through the list as needed to find the computer that is running the services you want to start or stop, and then click it.</span></span>
5. <span data-ttu-id="71302-148">单击“操作”。</span><span class="sxs-lookup"><span data-stu-id="71302-148">Click **Action**.</span></span>
6. <span data-ttu-id="71302-149">单击“启动所有服务”或“停止所有服务”。</span><span class="sxs-lookup"><span data-stu-id="71302-149">Click **Start All services** or **Stop All services**.</span></span>

### <a name="start-or-stop-a-specific-service"></a><span data-ttu-id="71302-150">启动或停止特定服务</span><span class="sxs-lookup"><span data-stu-id="71302-150">Start or stop a specific service</span></span>

1. <span data-ttu-id="71302-151">使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="71302-151">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
2. <span data-ttu-id="71302-152">打开浏览器窗口，然后输入管理 URL 以打开控制面板。</span><span class="sxs-lookup"><span data-stu-id="71302-152">Open a browser window, and then enter the Admin URL to open the Control Panel.</span></span> <span data-ttu-id="71302-153">有关可用于启动 Skype for Business Server 控制面板的不同方法的详细信息，请参阅安装和 [打开管理工具](../../management-tools/install-and-open-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="71302-153">For details about the different methods you can use to start the Skype for Business Server Control Panel, see [Install and open administrative tools](../../management-tools/install-and-open-administrative-tools.md).</span></span>
3. <span data-ttu-id="71302-154">在左侧导航栏中，单击“拓扑”，然后单击“状态”。</span><span class="sxs-lookup"><span data-stu-id="71302-154">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>
4. <span data-ttu-id="71302-155">在“状态”页上，根据需要对列表进行排序或搜索列表，以查找正在运行要启动或停止的服务的计算机，然后单击该计算机。</span><span class="sxs-lookup"><span data-stu-id="71302-155">On the Status page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span>
5. <span data-ttu-id="71302-156">单击“属性”。</span><span class="sxs-lookup"><span data-stu-id="71302-156">Click **Properties**.</span></span>
6. <span data-ttu-id="71302-157">如有必要，对服务列表进行排序，然后单击要启动或停止的服务。</span><span class="sxs-lookup"><span data-stu-id="71302-157">Sort the list of services, if necessary, and click the service you want to start or stop.</span></span>
7. <span data-ttu-id="71302-158">单击“操作”。</span><span class="sxs-lookup"><span data-stu-id="71302-158">Click **Action**.</span></span>
8. <span data-ttu-id="71302-159">单击“启动服务”或“停止服务”。</span><span class="sxs-lookup"><span data-stu-id="71302-159">Click **Start service** or **Stop service**.</span></span>
9. <span data-ttu-id="71302-160">单击“关闭”。</span><span class="sxs-lookup"><span data-stu-id="71302-160">Click **Close**.</span></span>


## <a name="prevent-sessions-for-services"></a><span data-ttu-id="71302-161">阻止服务的会话</span><span class="sxs-lookup"><span data-stu-id="71302-161">Prevent sessions for services</span></span>

<span data-ttu-id="71302-162">使用 Skype for Business 控制面板阻止特定计算机上运行的所有 Skype for Business Server 服务的新会话，或阻止特定服务的新会话。</span><span class="sxs-lookup"><span data-stu-id="71302-162">Use the Skype for Business Control Panel to prevent new sessions for all the Skype for Business Server services running on a specific computer or to prevent new sessions for a specific service.</span></span>

### <a name="prevent-new-sessions-for-all--skype-for-business-server-services-on-a-computer"></a><span data-ttu-id="71302-163">阻止计算机上所有 Skype for Business Server 服务的新会话</span><span class="sxs-lookup"><span data-stu-id="71302-163">Prevent new sessions for all  Skype for Business Server services on a computer</span></span>

1. <span data-ttu-id="71302-164">从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户，登录到部署 Skype for Business Server 的网络内的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="71302-164">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
2. <span data-ttu-id="71302-165">打开浏览器窗口，然后输入管理 URL 以打开控制面板。</span><span class="sxs-lookup"><span data-stu-id="71302-165">Open a browser window, and then enter the Admin URL to open the Control Panel.</span></span> <span data-ttu-id="71302-166">有关可用于启动 Skype for Business Server 控制面板的不同方法的详细信息，请参阅安装和 [打开管理工具](../../management-tools/install-and-open-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="71302-166">For details about the different methods you can use to start the Skype for Business Server Control Panel, see [Install and open administrative tools](../../management-tools/install-and-open-administrative-tools.md).</span></span>
3. <span data-ttu-id="71302-167">在左侧导航栏中，单击“拓扑”，然后单击“状态”。</span><span class="sxs-lookup"><span data-stu-id="71302-167">In the left navigation bar, click **Topology** and then click **Status**.</span></span>
4. <span data-ttu-id="71302-168">在“状态”页上，根据需要对列表进行排序或搜索，以查找正在运行要对其阻止新会话的服务的计算机，然后单击该计算机。</span><span class="sxs-lookup"><span data-stu-id="71302-168">On the Status page, sort or search through the list as needed to find the computer that is running the services for which you want to prevent new sessions, and then click it.</span></span>
5. <span data-ttu-id="71302-169">单击“操作”。</span><span class="sxs-lookup"><span data-stu-id="71302-169">Click **Action**.</span></span>
6. <span data-ttu-id="71302-170">单击“阻止所有服务的新会话”。</span><span class="sxs-lookup"><span data-stu-id="71302-170">Click **Prevent new sessions for all services**.</span></span>

### <a name="prevent-new-sessions-for-a-specific-service"></a><span data-ttu-id="71302-171">阻止特定服务的新会话</span><span class="sxs-lookup"><span data-stu-id="71302-171">Prevent new sessions for a specific service</span></span>

1. <span data-ttu-id="71302-172">从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户，登录到部署 Skype for Business Server 的网络内的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="71302-172">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
2. <span data-ttu-id="71302-173">打开浏览器窗口，然后输入管理 URL 以打开控制面板。</span><span class="sxs-lookup"><span data-stu-id="71302-173">Open a browser window, and then enter the Admin URL to open the Control Panel.</span></span> <span data-ttu-id="71302-174">有关可用于启动 Skype for Business Server 控制面板的不同方法的详细信息，请参阅安装和 [打开管理工具](../../management-tools/install-and-open-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="71302-174">For details about the different methods you can use to start the Skype for Business Server Control Panel, see [Install and open administrative tools](../../management-tools/install-and-open-administrative-tools.md).</span></span>
3. <span data-ttu-id="71302-175">在左侧导航栏中，单击“拓扑”，然后单击“状态”。</span><span class="sxs-lookup"><span data-stu-id="71302-175">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>
4. <span data-ttu-id="71302-176">单击“属性”。</span><span class="sxs-lookup"><span data-stu-id="71302-176">Click **Properties**.</span></span>
5. <span data-ttu-id="71302-177">如有必要，对服务列表进行排序，然后单击要对其阻止新会话的服务。</span><span class="sxs-lookup"><span data-stu-id="71302-177">Sort the list of services, if necessary, and click the service for which you want to prevent new sessions.</span></span>
6. <span data-ttu-id="71302-178">单击“操作”。</span><span class="sxs-lookup"><span data-stu-id="71302-178">Click **Action**.</span></span>
7. <span data-ttu-id="71302-179">单击“阻止服务的新会话”。</span><span class="sxs-lookup"><span data-stu-id="71302-179">Click **Prevent new sessions for service**.</span></span>
8. <span data-ttu-id="71302-180">单击“关闭”。</span><span class="sxs-lookup"><span data-stu-id="71302-180">Click **Close**.</span></span>
