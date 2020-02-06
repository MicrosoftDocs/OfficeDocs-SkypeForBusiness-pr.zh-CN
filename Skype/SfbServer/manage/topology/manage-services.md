---
title: 管理 Skype for Business 服务器中的服务
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 了解如何查看服务状态、启动和停止服务以及阻止服务的会话。
ms.openlocfilehash: 154c7b2d5ff858e22be4159ec1797ef6a6724445
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817113"
---
# <a name="manage-services-in-skype-for-business-server"></a><span data-ttu-id="77262-103">管理 Skype for Business 服务器中的服务</span><span class="sxs-lookup"><span data-stu-id="77262-103">Manage services in Skype for Business Server</span></span>

<span data-ttu-id="77262-104">可以使用 Skype for Business Server 控制面板查看拓扑中运行 Skype for Business 服务器的所有计算机的列表、查看服务状态、启动或停止服务以及阻止服务会话。</span><span class="sxs-lookup"><span data-stu-id="77262-104">You can use the Skype for Business Server Control Panel to view a list of all the computers that are running Skype for Business Server in your topology, view the status of services, start or stop services, and prevent sessions for services.</span></span>

- [<span data-ttu-id="77262-105">查看运行 Skype for Business 服务器的计算机列表</span><span class="sxs-lookup"><span data-stu-id="77262-105">View a list of computers running Skype for Business Server</span></span>](#view-a-list-of-computers-running-skype-for-business-server)
- [<span data-ttu-id="77262-106">查看 Skype for Business 计算机上运行的服务的状态</span><span class="sxs-lookup"><span data-stu-id="77262-106">View the status of services running on a computer in Skype for Business</span></span>](#view-the-status-of-services-running-on-a-computer-in-skype-for-business)
- [<span data-ttu-id="77262-107">启动或停止 Skype for Business 服务</span><span class="sxs-lookup"><span data-stu-id="77262-107">Start or stop Skype for Business services</span></span>](#start-or-stop-skype-for-business-services)
- [<span data-ttu-id="77262-108">阻止服务的会话</span><span class="sxs-lookup"><span data-stu-id="77262-108">Prevent sessions for services</span></span>](#prevent-sessions-for-services)

## <a name="view-a-list-of-computers-running-skype-for-business-server"></a><span data-ttu-id="77262-109">查看运行 Skype for Business 服务器的计算机列表</span><span class="sxs-lookup"><span data-stu-id="77262-109">View a list of computers running Skype for Business Server</span></span>

<span data-ttu-id="77262-110">使用 Skype for Business 服务器控制面板查看在你的拓扑中运行 Skype for Business 的所有计算机的列表，并查看每个计算机的服务状态。</span><span class="sxs-lookup"><span data-stu-id="77262-110">Use the Skype for Business Server Control Panel to view a list of all the computers that are running Skype for Business in your topology and see the service status of each.</span></span> <span data-ttu-id="77262-111">你可以按计算机、池或网站对列表进行排序。</span><span class="sxs-lookup"><span data-stu-id="77262-111">You can sort the list by computer, pool, or site.</span></span> 

1. <span data-ttu-id="77262-112">从分配给 Skype for business 服务器的任何预定义管理角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="77262-112">From a user account that is assigned to any of the predefined administrative roles for Skype for Business Server, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="77262-113">有关详细信息，请参阅[Skype for Business 服务器的基于角色的访问控制（RBAC）](../../plan-your-deployment/security/role-based-access-control-rbac.md)。</span><span class="sxs-lookup"><span data-stu-id="77262-113">For more information, see [Role-based access control (RBAC) for Skype for Business Server](../../plan-your-deployment/security/role-based-access-control-rbac.md).</span></span>
2. <span data-ttu-id="77262-114">打开一个浏览器窗口，然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。</span><span class="sxs-lookup"><span data-stu-id="77262-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="77262-115">有关可用于启动 Skype for Business 服务器控制面板的不同方法的详细信息，请参阅[安装和打开 "管理工具](../../management-tools/install-and-open-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="77262-115">For details about the different methods you can use to start the Skype for Business Server Control Panel, see [Install and open administrative tools](../../management-tools/install-and-open-administrative-tools.md).</span></span>
3. <span data-ttu-id="77262-116">在左侧导航栏中，单击“**拓扑**”，然后单击“**状态**”。</span><span class="sxs-lookup"><span data-stu-id="77262-116">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>
4. <span data-ttu-id="77262-117">在 "状态" 页面上，根据需要执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="77262-117">On the Status page, do either of the following as needed:</span></span>
    - <span data-ttu-id="77262-118">单击 "**计算机**"、"**池**" 或 "**网站**" 列标题，然后单击向上键或向下键，对列表进行排序。</span><span class="sxs-lookup"><span data-stu-id="77262-118">Sort the list by clicking the **Computer**, **Pool**, or **Site** column heading, and then clicking the up arrow or the down arrow.</span></span>
    - <span data-ttu-id="77262-119">单击 "**刷新**" 以查看最新列表。</span><span class="sxs-lookup"><span data-stu-id="77262-119">Click **Refresh** to view the most up-to-date list.</span></span>
    - <span data-ttu-id="77262-120">通过在 "搜索" 字段中键入计算机名称来搜索特定计算机。</span><span class="sxs-lookup"><span data-stu-id="77262-120">Search for a specific computer by typing the computer name in the search field.</span></span>
   
## <a name="view-the-status-of-services-running-on-a-computer-in-skype-for-business"></a><span data-ttu-id="77262-121">查看 Skype for Business 计算机上运行的服务的状态</span><span class="sxs-lookup"><span data-stu-id="77262-121">View the status of services running on a computer in Skype for Business</span></span>

<span data-ttu-id="77262-122">使用 Skype for Business 服务器控制面板查看 Skype for Business Server 拓扑中的特定计算机上运行的所有服务，并查看每个服务的状态。</span><span class="sxs-lookup"><span data-stu-id="77262-122">Use the Skype for Business Server Control Panel to view all the services that are running on a specific computer in your Skype for Business Server topology and see the status of each service.</span></span>

1. <span data-ttu-id="77262-123">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="77262-123">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
2. <span data-ttu-id="77262-124">打开一个浏览器窗口，然后输入管理员 URL 以打开 "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="77262-124">Open a browser window, and then enter the Admin URL to open the Control Panel.</span></span> <span data-ttu-id="77262-125">有关可用于启动 Skype for Business 服务器控制面板的不同方法的详细信息，请参阅[安装和打开 "管理工具](../../management-tools/install-and-open-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="77262-125">For details about the different methods you can use to start the Skype for Business Server Control Panel, see [Install and open administrative tools](../../management-tools/install-and-open-administrative-tools.md).</span></span>
3. <span data-ttu-id="77262-126">在左侧导航栏中，单击 "**拓扑**"。</span><span class="sxs-lookup"><span data-stu-id="77262-126">In the left navigation bar, click **Topology**.</span></span>
4. <span data-ttu-id="77262-127">在 "状态" 页面上，根据需要对列表进行排序或搜索，以查找感兴趣的计算机，然后单击计算机名称。</span><span class="sxs-lookup"><span data-stu-id="77262-127">On the Status page, sort or search the list, as required, to find the computer you’re interested in, and then click the computer name.</span></span>
5. <span data-ttu-id="77262-128">执行下列任一操作：</span><span class="sxs-lookup"><span data-stu-id="77262-128">Do either of the following:</span></span>
    - <span data-ttu-id="77262-129">若要查看计算机上运行的服务的最新状态，请单击 "**获取服务状态**"。</span><span class="sxs-lookup"><span data-stu-id="77262-129">To see the latest status of services running on the computer, click **Get service status**.</span></span>
    - <span data-ttu-id="77262-130">若要查看计算机上运行的特定服务的列表和每个服务的状态，请单击 "**属性**"，然后单击 "**关闭**" 以返回到列表。</span><span class="sxs-lookup"><span data-stu-id="77262-130">To see a list of specific services running on the computer and the status of each service, click **Properties**, and then click **Close** to return to the list.</span></span>

### <a name="viewing-service-status-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="77262-131">使用 Windows PowerShell Cmdlet 查看服务状态</span><span class="sxs-lookup"><span data-stu-id="77262-131">Viewing service status by using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="77262-132">你还可以使用 Windows PowerShell 和 CsWindowsService cmdlet 查看服务状态。</span><span class="sxs-lookup"><span data-stu-id="77262-132">You can also view service status by using Windows PowerShell and the Get-CsWindowsService cmdlet.</span></span> <span data-ttu-id="77262-133">你可以从 Skype for Business Server Management Shell 或从 Windows PowerShell 的远程会话运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="77262-133">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="77262-134">有关详细信息，请参阅[Skype For Business Server 命令行管理程序](../management-shell.md)。</span><span class="sxs-lookup"><span data-stu-id="77262-134">For more information, see [Skype for Business Server Management Shell](../management-shell.md).</span></span>

<span data-ttu-id="77262-135">**查看服务状态**</span><span class="sxs-lookup"><span data-stu-id="77262-135">**To view service status**</span></span>

<span data-ttu-id="77262-136">若要查看计算机上的服务状态，请在 Skype for business Server 命令行管理器中键入类似于以下内容的命令，然后按 Enter：</span><span class="sxs-lookup"><span data-stu-id="77262-136">To view service status on a computer, type a command similar to the following in the Skype for Business Server Management Shell, and then press Enter:</span></span>

`Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status`

<span data-ttu-id="77262-137">此命令会返回类似下列信息：</span><span class="sxs-lookup"><span data-stu-id="77262-137">This command returns information similar to the following:</span></span>

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

<span data-ttu-id="77262-138">有关详细信息，请参阅[CsWindowsService](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsWindowsService)。</span><span class="sxs-lookup"><span data-stu-id="77262-138">For details, see [Get-CsWindowsService](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsWindowsService).</span></span>

## <a name="start-or-stop-skype-for-business-services"></a><span data-ttu-id="77262-139">启动或停止 Skype for Business 服务</span><span class="sxs-lookup"><span data-stu-id="77262-139">Start or stop Skype for Business services</span></span>

<span data-ttu-id="77262-140">使用 Skype for Business 服务器控制面板启动或停止在特定计算机上运行的所有 Skype for business 服务器服务，或者启动或停止特定服务。</span><span class="sxs-lookup"><span data-stu-id="77262-140">Use the Skype for Business Server Control Panel to start or stop all the Skype for Business Server services running on a specific computer or to start or stop a specific service.</span></span>

### <a name="start-or-stop-all-skype-for-business-server-services-on-a-computer"></a><span data-ttu-id="77262-141">启动或停止计算机上的所有 Skype for Business 服务器服务</span><span class="sxs-lookup"><span data-stu-id="77262-141">Start or stop all Skype for Business Server services on a computer</span></span>

1. <span data-ttu-id="77262-142">从 RTCUniversalServerAdmins 组的成员（或具有等效用户权限）或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户，登录到你部署了 Skype for Business 服务器的网络中的任何计算机.</span><span class="sxs-lookup"><span data-stu-id="77262-142">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span> <span data-ttu-id="77262-143">你可以通过运行如下所示的命令来确定你是否已分配 CsServerAdministrator 或 CsAdministrator RBAC 角色：</span><span class="sxs-lookup"><span data-stu-id="77262-143">You can determine whether you have been assigned the CsServerAdministrator or the CsAdministrator RBAC role by running a command similar to the following:</span></span>

    `Get-CsAdminRoleAssignment -Identity "kenmyer"`

2. <span data-ttu-id="77262-144">打开一个浏览器窗口，然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。</span><span class="sxs-lookup"><span data-stu-id="77262-144">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="77262-145">有关可用于启动 Skype for Business 服务器控制面板的不同方法的详细信息，请参阅[安装和打开 "管理工具](../../management-tools/install-and-open-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="77262-145">For details about the different methods you can use to start the Skype for Business Server Control Panel, see [Install and open administrative tools](../../management-tools/install-and-open-administrative-tools.md).</span></span>
3. <span data-ttu-id="77262-146">在左侧导航栏中，单击“**拓扑**”，然后单击“**状态**”。</span><span class="sxs-lookup"><span data-stu-id="77262-146">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>
4. <span data-ttu-id="77262-147">在 "状态" 页面上，根据需要对列表进行排序或搜索以查找运行要启动或停止的服务的计算机，然后单击它。</span><span class="sxs-lookup"><span data-stu-id="77262-147">On the Status page, sort or search through the list as needed to find the computer that is running the services you want to start or stop, and then click it.</span></span>
5. <span data-ttu-id="77262-148">单击 "**操作**"。</span><span class="sxs-lookup"><span data-stu-id="77262-148">Click **Action**.</span></span>
6. <span data-ttu-id="77262-149">单击 "**启动所有服务**" 或 "**停止所有服务**"。</span><span class="sxs-lookup"><span data-stu-id="77262-149">Click **Start All services** or **Stop All services**.</span></span>

### <a name="start-or-stop-a-specific-service"></a><span data-ttu-id="77262-150">启动或停止特定服务</span><span class="sxs-lookup"><span data-stu-id="77262-150">Start or stop a specific service</span></span>

1. <span data-ttu-id="77262-151">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="77262-151">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
2. <span data-ttu-id="77262-152">打开一个浏览器窗口，然后输入管理员 URL 以打开 "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="77262-152">Open a browser window, and then enter the Admin URL to open the Control Panel.</span></span> <span data-ttu-id="77262-153">有关可用于启动 Skype for Business 服务器控制面板的不同方法的详细信息，请参阅[安装和打开 "管理工具](../../management-tools/install-and-open-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="77262-153">For details about the different methods you can use to start the Skype for Business Server Control Panel, see [Install and open administrative tools](../../management-tools/install-and-open-administrative-tools.md).</span></span>
3. <span data-ttu-id="77262-154">在左侧导航栏中，单击“**拓扑**”，然后单击“**状态**”。</span><span class="sxs-lookup"><span data-stu-id="77262-154">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>
4. <span data-ttu-id="77262-155">在 "状态" 页面上，根据需要对列表进行排序或搜索以查找运行要启动或停止的服务的计算机，然后单击它。</span><span class="sxs-lookup"><span data-stu-id="77262-155">On the Status page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span>
5. <span data-ttu-id="77262-156">单击 "**属性**"。</span><span class="sxs-lookup"><span data-stu-id="77262-156">Click **Properties**.</span></span>
6. <span data-ttu-id="77262-157">对服务列表进行排序（如有必要），然后单击要启动或停止的服务。</span><span class="sxs-lookup"><span data-stu-id="77262-157">Sort the list of services, if necessary, and click the service you want to start or stop.</span></span>
7. <span data-ttu-id="77262-158">单击 "**操作**"。</span><span class="sxs-lookup"><span data-stu-id="77262-158">Click **Action**.</span></span>
8. <span data-ttu-id="77262-159">单击 "**开始服务**" 或 "**停止服务**"。</span><span class="sxs-lookup"><span data-stu-id="77262-159">Click **Start service** or **Stop service**.</span></span>
9. <span data-ttu-id="77262-160">单击“关闭”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="77262-160">Click **Close**.</span></span>


## <a name="prevent-sessions-for-services"></a><span data-ttu-id="77262-161">阻止服务的会话</span><span class="sxs-lookup"><span data-stu-id="77262-161">Prevent sessions for services</span></span>

<span data-ttu-id="77262-162">使用 "Skype for Business 控制面板" 阻止在特定计算机上运行的所有 Skype for business 服务器服务的新会话或阻止特定服务的新会话。</span><span class="sxs-lookup"><span data-stu-id="77262-162">Use the Skype for Business Control Panel to prevent new sessions for all the Skype for Business Server services running on a specific computer or to prevent new sessions for a specific service.</span></span>

### <a name="prevent-new-sessions-for-all--skype-for-business-server-services-on-a-computer"></a><span data-ttu-id="77262-163">阻止计算机上所有 Skype for Business 服务器服务的新会话</span><span class="sxs-lookup"><span data-stu-id="77262-163">Prevent new sessions for all  Skype for Business Server services on a computer</span></span>

1. <span data-ttu-id="77262-164">从 RTCUniversalServerAdmins 组的成员（或具有等效用户权限）或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户，登录到你部署了 Skype for Business 服务器的网络中的任何计算机.</span><span class="sxs-lookup"><span data-stu-id="77262-164">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
2. <span data-ttu-id="77262-165">打开一个浏览器窗口，然后输入管理员 URL 以打开 "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="77262-165">Open a browser window, and then enter the Admin URL to open the Control Panel.</span></span> <span data-ttu-id="77262-166">有关可用于启动 Skype for Business 服务器控制面板的不同方法的详细信息，请参阅[安装和打开 "管理工具](../../management-tools/install-and-open-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="77262-166">For details about the different methods you can use to start the Skype for Business Server Control Panel, see [Install and open administrative tools](../../management-tools/install-and-open-administrative-tools.md).</span></span>
3. <span data-ttu-id="77262-167">在左侧导航栏中，单击 "**拓扑**"，然后单击 "**状态**"。</span><span class="sxs-lookup"><span data-stu-id="77262-167">In the left navigation bar, click **Topology** and then click **Status**.</span></span>
4. <span data-ttu-id="77262-168">在 "状态" 页面上，根据需要对列表进行排序或搜索以查找运行要阻止新会话的服务的计算机，然后单击该计算机。</span><span class="sxs-lookup"><span data-stu-id="77262-168">On the Status page, sort or search through the list as needed to find the computer that is running the services for which you want to prevent new sessions, and then click it.</span></span>
5. <span data-ttu-id="77262-169">单击 "**操作**"。</span><span class="sxs-lookup"><span data-stu-id="77262-169">Click **Action**.</span></span>
6. <span data-ttu-id="77262-170">单击 "**阻止所有服务的新会话**"。</span><span class="sxs-lookup"><span data-stu-id="77262-170">Click **Prevent new sessions for all services**.</span></span>

### <a name="prevent-new-sessions-for-a-specific-service"></a><span data-ttu-id="77262-171">阻止针对特定服务的新会话</span><span class="sxs-lookup"><span data-stu-id="77262-171">Prevent new sessions for a specific service</span></span>

1. <span data-ttu-id="77262-172">从 RTCUniversalServerAdmins 组的成员（或具有等效用户权限）或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户，登录到你部署了 Skype for Business 服务器的网络中的任何计算机.</span><span class="sxs-lookup"><span data-stu-id="77262-172">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
2. <span data-ttu-id="77262-173">打开一个浏览器窗口，然后输入管理员 URL 以打开 "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="77262-173">Open a browser window, and then enter the Admin URL to open the Control Panel.</span></span> <span data-ttu-id="77262-174">有关可用于启动 Skype for Business 服务器控制面板的不同方法的详细信息，请参阅[安装和打开 "管理工具](../../management-tools/install-and-open-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="77262-174">For details about the different methods you can use to start the Skype for Business Server Control Panel, see [Install and open administrative tools](../../management-tools/install-and-open-administrative-tools.md).</span></span>
3. <span data-ttu-id="77262-175">在左侧导航栏中，单击“**拓扑**”，然后单击“**状态**”。</span><span class="sxs-lookup"><span data-stu-id="77262-175">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>
4. <span data-ttu-id="77262-176">单击 "**属性**"。</span><span class="sxs-lookup"><span data-stu-id="77262-176">Click **Properties**.</span></span>
5. <span data-ttu-id="77262-177">对服务列表进行排序（如有必要），然后单击要阻止新会话的服务。</span><span class="sxs-lookup"><span data-stu-id="77262-177">Sort the list of services, if necessary, and click the service for which you want to prevent new sessions.</span></span>
6. <span data-ttu-id="77262-178">单击 "**操作**"。</span><span class="sxs-lookup"><span data-stu-id="77262-178">Click **Action**.</span></span>
7. <span data-ttu-id="77262-179">单击 "**阻止新的服务会话**"。</span><span class="sxs-lookup"><span data-stu-id="77262-179">Click **Prevent new sessions for service**.</span></span>
8. <span data-ttu-id="77262-180">单击“关闭”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="77262-180">Click **Close**.</span></span>
