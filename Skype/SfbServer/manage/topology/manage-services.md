---
title: Skype 中的服务管理业务服务器
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 了解如何查看服务状态，启动和停止服务，并阻止服务的会话。
ms.openlocfilehash: 6913ce2cbef6c12a61d7d4751b35a71371ffb991
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30875058"
---
# <a name="manage-services-in-skype-for-business-server"></a><span data-ttu-id="2fa2f-103">Skype 中的服务管理业务服务器</span><span class="sxs-lookup"><span data-stu-id="2fa2f-103">Manage services in Skype for Business Server</span></span>

<span data-ttu-id="2fa2f-104">可以使用业务 Server Control Panel 的 Skype 查看列表的所有计算机的业务服务器拓扑中运行 Skype、 查看的服务的状态、 启动或停止服务，并阻止服务的会话。</span><span class="sxs-lookup"><span data-stu-id="2fa2f-104">You can use the Skype for Business Server Control Panel to view a list of all the computers that are running Skype for Business Server in your topology, view the status of services, start or stop services, and prevent sessions for services.</span></span>

- [<span data-ttu-id="2fa2f-105">查看业务服务器运行 Skype 的计算机列表</span><span class="sxs-lookup"><span data-stu-id="2fa2f-105">View a list of computers running Skype for Business Server</span></span>](#view-a-list-of-computers-running-skype-for-business-server)
- [<span data-ttu-id="2fa2f-106">查看 Skype for Business 中的计算机上运行的服务的状态</span><span class="sxs-lookup"><span data-stu-id="2fa2f-106">View the status of services running on a computer in Skype for Business</span></span>](#view-the-status-of-services-running-on-a-computer-in-skype-for-business)
- [<span data-ttu-id="2fa2f-107">启动或停止 Skype 业务服务</span><span class="sxs-lookup"><span data-stu-id="2fa2f-107">Start or stop Skype for Business services</span></span>](#start-or-stop-skype-for-business-services)
- [<span data-ttu-id="2fa2f-108">阻止服务的会话</span><span class="sxs-lookup"><span data-stu-id="2fa2f-108">Prevent sessions for services</span></span>](#prevent-sessions-for-services)

## <a name="view-a-list-of-computers-running-skype-for-business-server"></a><span data-ttu-id="2fa2f-109">查看业务服务器运行 Skype 的计算机列表</span><span class="sxs-lookup"><span data-stu-id="2fa2f-109">View a list of computers running Skype for Business Server</span></span>

<span data-ttu-id="2fa2f-110">使用业务 Server Control Panel Skype 查看您的拓扑中运行 for Business 的 Skype 并查看每个服务状态的所有计算机的列表。</span><span class="sxs-lookup"><span data-stu-id="2fa2f-110">Use the Skype for Business Server Control Panel to view a list of all the computers that are running Skype for Business in your topology and see the service status of each.</span></span> <span data-ttu-id="2fa2f-111">您可以通过计算机、 池或网站列表进行排序。</span><span class="sxs-lookup"><span data-stu-id="2fa2f-111">You can sort the list by computer, pool, or site.</span></span> 

1. <span data-ttu-id="2fa2f-112">分配给任何预定义管理角色的 Skype 业务服务器的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="2fa2f-112">From a user account that is assigned to any of the predefined administrative roles for Skype for Business Server, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="2fa2f-113">有关详细信息，请参阅[基于角色的访问控制 (RBAC) 的 Skype 业务服务器](../../plan-your-deployment/security/role-based-access-control-rbac.md)。</span><span class="sxs-lookup"><span data-stu-id="2fa2f-113">For more information, see [Role-based access control (RBAC) for Skype for Business Server](../../plan-your-deployment/security/role-based-access-control-rbac.md).</span></span>
2. <span data-ttu-id="2fa2f-114">打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="2fa2f-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="2fa2f-115">有关可用于为业务 Server Control Panel 启动 Skype 的不同方法的详细信息，请参阅[安装和打开管理工具](../../management-tools/install-and-open-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="2fa2f-115">For details about the different methods you can use to start the Skype for Business Server Control Panel, see [Install and open administrative tools](../../management-tools/install-and-open-administrative-tools.md).</span></span>
3. <span data-ttu-id="2fa2f-116">在左侧导航栏中，单击“**拓扑**”，然后单击“**状态**”。</span><span class="sxs-lookup"><span data-stu-id="2fa2f-116">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>
4. <span data-ttu-id="2fa2f-117">在状态页上，执行根据需要以下任一操作：</span><span class="sxs-lookup"><span data-stu-id="2fa2f-117">On the Status page, do either of the following as needed:</span></span>
    - <span data-ttu-id="2fa2f-118">通过单击**计算机**、**池**或**网站**列标题，然后单击向上箭头或向下箭头对列表。</span><span class="sxs-lookup"><span data-stu-id="2fa2f-118">Sort the list by clicking the **Computer**, **Pool**, or **Site** column heading, and then clicking the up arrow or the down arrow.</span></span>
    - <span data-ttu-id="2fa2f-119">单击**刷新**以查看最新的列表。</span><span class="sxs-lookup"><span data-stu-id="2fa2f-119">Click **Refresh** to view the most up-to-date list.</span></span>
    - <span data-ttu-id="2fa2f-120">通过在搜索字段中键入计算机名称来搜索特定的计算机。</span><span class="sxs-lookup"><span data-stu-id="2fa2f-120">Search for a specific computer by typing the computer name in the search field.</span></span>
   
## <a name="view-the-status-of-services-running-on-a-computer-in-skype-for-business"></a><span data-ttu-id="2fa2f-121">查看 Skype for Business 中的计算机上运行的服务的状态</span><span class="sxs-lookup"><span data-stu-id="2fa2f-121">View the status of services running on a computer in Skype for Business</span></span>

<span data-ttu-id="2fa2f-122">使用业务 Server Control Panel Skype 可以查看您 Skype 企业服务器拓扑中特定计算机上运行并查看每种服务的状态的所有服务。</span><span class="sxs-lookup"><span data-stu-id="2fa2f-122">Use the Skype for Business Server Control Panel to view all the services that are running on a specific computer in your Skype for Business Server topology and see the status of each service.</span></span>

1. <span data-ttu-id="2fa2f-123">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="2fa2f-123">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
2. <span data-ttu-id="2fa2f-124">打开一个浏览器窗口，然后输入管理 URL 以打开控制面板。</span><span class="sxs-lookup"><span data-stu-id="2fa2f-124">Open a browser window, and then enter the Admin URL to open the Control Panel.</span></span> <span data-ttu-id="2fa2f-125">有关可用于为业务 Server Control Panel 启动 Skype 的不同方法的详细信息，请参阅[安装和打开管理工具](../../management-tools/install-and-open-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="2fa2f-125">For details about the different methods you can use to start the Skype for Business Server Control Panel, see [Install and open administrative tools](../../management-tools/install-and-open-administrative-tools.md).</span></span>
3. <span data-ttu-id="2fa2f-126">在左侧的导航栏中，单击**拓扑**。</span><span class="sxs-lookup"><span data-stu-id="2fa2f-126">In the left navigation bar, click **Topology**.</span></span>
4. <span data-ttu-id="2fa2f-127">在状态页上排序或搜索列表中，根据需要，以查找您感兴趣的计算机，然后单击计算机名称。</span><span class="sxs-lookup"><span data-stu-id="2fa2f-127">On the Status page, sort or search the list, as required, to find the computer you’re interested in, and then click the computer name.</span></span>
5. <span data-ttu-id="2fa2f-128">请执行以下任一操作：</span><span class="sxs-lookup"><span data-stu-id="2fa2f-128">Do either of the following:</span></span>
    - <span data-ttu-id="2fa2f-129">若要查看的计算机上运行的服务的最新状态，请单击**获取服务状态**。</span><span class="sxs-lookup"><span data-stu-id="2fa2f-129">To see the latest status of services running on the computer, click **Get service status**.</span></span>
    - <span data-ttu-id="2fa2f-130">要查看在每个服务的状态和计算机上运行的特定服务的列表，请单击**属性**，然后单击**关闭**以返回到列表。</span><span class="sxs-lookup"><span data-stu-id="2fa2f-130">To see a list of specific services running on the computer and the status of each service, click **Properties**, and then click **Close** to return to the list.</span></span>

### <a name="viewing-service-status-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="2fa2f-131">通过使用 Windows PowerShell Cmdlet 查看服务状态</span><span class="sxs-lookup"><span data-stu-id="2fa2f-131">Viewing service status by using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="2fa2f-132">您还可以使用 Windows PowerShell 和 Get-cswindowsservice cmdlet 查看服务状态。</span><span class="sxs-lookup"><span data-stu-id="2fa2f-132">You can also view service status by using Windows PowerShell and the Get-CsWindowsService cmdlet.</span></span> <span data-ttu-id="2fa2f-133">从业务 Server 命令行管理程序 Skype 或 Windows PowerShell 远程会话，您可以运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="2fa2f-133">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="2fa2f-134">有关详细信息，请参阅[业务 Server Management Shell 的 Skype](../management-shell.md)。</span><span class="sxs-lookup"><span data-stu-id="2fa2f-134">For more information, see [Skype for Business Server Management Shell](../management-shell.md).</span></span>

<span data-ttu-id="2fa2f-135">**若要查看服务状态**</span><span class="sxs-lookup"><span data-stu-id="2fa2f-135">**To view service status**</span></span>

<span data-ttu-id="2fa2f-136">若要查看的计算机上的服务状态，Skype 的业务 Server Management Shell 中，键入类似于以下命令，然后按 Enter:</span><span class="sxs-lookup"><span data-stu-id="2fa2f-136">To view service status on a computer, type a command similar to the following in the Skype for Business Server Management Shell, and then press Enter:</span></span>

`Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status`

<span data-ttu-id="2fa2f-137">此命令会返回类似下列信息：</span><span class="sxs-lookup"><span data-stu-id="2fa2f-137">This command returns information similar to the following:</span></span>

```
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

<span data-ttu-id="2fa2f-138">有关详细信息，请参阅[Get-cswindowsservice](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsWindowsService)。</span><span class="sxs-lookup"><span data-stu-id="2fa2f-138">For details, see [Get-CsWindowsService](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsWindowsService).</span></span>

## <a name="start-or-stop-skype-for-business-services"></a><span data-ttu-id="2fa2f-139">启动或停止 Skype 业务服务</span><span class="sxs-lookup"><span data-stu-id="2fa2f-139">Start or stop Skype for Business services</span></span>

<span data-ttu-id="2fa2f-140">使用业务 Server Control Panel Skype 启动或停止特定计算机上运行的业务服务器服务的所有 Skype 或者启动或都停止特定服务。</span><span class="sxs-lookup"><span data-stu-id="2fa2f-140">Use the Skype for Business Server Control Panel to start or stop all the Skype for Business Server services running on a specific computer or to start or stop a specific service.</span></span>

### <a name="start-or-stop-all-skype-for-business-server-services-on-a-computer"></a><span data-ttu-id="2fa2f-141">启动或停止所有 Skype 业务 Server 服务的计算机上</span><span class="sxs-lookup"><span data-stu-id="2fa2f-141">Start or stop all Skype for Business Server services on a computer</span></span>

1. <span data-ttu-id="2fa2f-142">从用户帐户是 RTCUniversalServerAdmins 组的成员 （或具有同等用户权限），或分配给 CsServerAdministrator 或 CsAdministrator 角色，登录到在其中在部署 Skype Business Server 网络中的任一计算机.</span><span class="sxs-lookup"><span data-stu-id="2fa2f-142">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span> <span data-ttu-id="2fa2f-143">您可以确定是否已将您分配 CsServerAdministrator 或 CsAdministrator RBAC 角色通过运行类似于以下命令：</span><span class="sxs-lookup"><span data-stu-id="2fa2f-143">You can determine whether you have been assigned the CsServerAdministrator or the CsAdministrator RBAC role by running a command similar to the following:</span></span>

    `Get-CsAdminRoleAssignment -Identity "kenmyer"`

2. <span data-ttu-id="2fa2f-144">打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="2fa2f-144">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="2fa2f-145">有关可用于为业务 Server Control Panel 启动 Skype 的不同方法的详细信息，请参阅[安装和打开管理工具](../../management-tools/install-and-open-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="2fa2f-145">For details about the different methods you can use to start the Skype for Business Server Control Panel, see [Install and open administrative tools](../../management-tools/install-and-open-administrative-tools.md).</span></span>
3. <span data-ttu-id="2fa2f-146">在左侧导航栏中，单击“**拓扑**”，然后单击“**状态**”。</span><span class="sxs-lookup"><span data-stu-id="2fa2f-146">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>
4. <span data-ttu-id="2fa2f-147">状态页、 排序或搜索列表根据需要查找运行服务的计算机上要启动或停止，然后单击它。</span><span class="sxs-lookup"><span data-stu-id="2fa2f-147">On the Status page, sort or search through the list as needed to find the computer that is running the services you want to start or stop, and then click it.</span></span>
5. <span data-ttu-id="2fa2f-148">单击**操作**。</span><span class="sxs-lookup"><span data-stu-id="2fa2f-148">Click **Action**.</span></span>
6. <span data-ttu-id="2fa2f-149">单击**启动所有服务**或**停止所有服务**。</span><span class="sxs-lookup"><span data-stu-id="2fa2f-149">Click **Start All services** or **Stop All services**.</span></span>

### <a name="start-or-stop-a-specific-service"></a><span data-ttu-id="2fa2f-150">启动或停止特定服务</span><span class="sxs-lookup"><span data-stu-id="2fa2f-150">Start or stop a specific service</span></span>

1. <span data-ttu-id="2fa2f-151">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="2fa2f-151">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
2. <span data-ttu-id="2fa2f-152">打开一个浏览器窗口，然后输入管理 URL 以打开控制面板。</span><span class="sxs-lookup"><span data-stu-id="2fa2f-152">Open a browser window, and then enter the Admin URL to open the Control Panel.</span></span> <span data-ttu-id="2fa2f-153">有关可用于为业务 Server Control Panel 启动 Skype 的不同方法的详细信息，请参阅[安装和打开管理工具](../../management-tools/install-and-open-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="2fa2f-153">For details about the different methods you can use to start the Skype for Business Server Control Panel, see [Install and open administrative tools](../../management-tools/install-and-open-administrative-tools.md).</span></span>
3. <span data-ttu-id="2fa2f-154">在左侧导航栏中，单击“**拓扑**”，然后单击“**状态**”。</span><span class="sxs-lookup"><span data-stu-id="2fa2f-154">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>
4. <span data-ttu-id="2fa2f-155">状态页、 排序或搜索列表根据需要查找运行服务的计算机上要启动或停止，然后单击它。</span><span class="sxs-lookup"><span data-stu-id="2fa2f-155">On the Status page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span>
5. <span data-ttu-id="2fa2f-156">单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="2fa2f-156">Click **Properties**.</span></span>
6. <span data-ttu-id="2fa2f-157">服务列表进行排序，如有必要，然后单击要启动或停止的服务。</span><span class="sxs-lookup"><span data-stu-id="2fa2f-157">Sort the list of services, if necessary, and click the service you want to start or stop.</span></span>
7. <span data-ttu-id="2fa2f-158">单击**操作**。</span><span class="sxs-lookup"><span data-stu-id="2fa2f-158">Click **Action**.</span></span>
8. <span data-ttu-id="2fa2f-159">单击**启动服务**或**停止服务**。</span><span class="sxs-lookup"><span data-stu-id="2fa2f-159">Click **Start service** or **Stop service**.</span></span>
9. <span data-ttu-id="2fa2f-160">单击“关闭”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2fa2f-160">Click **Close**.</span></span>


## <a name="prevent-sessions-for-services"></a><span data-ttu-id="2fa2f-161">阻止服务的会话</span><span class="sxs-lookup"><span data-stu-id="2fa2f-161">Prevent sessions for services</span></span>

<span data-ttu-id="2fa2f-162">使用业务控制面板的 Skype 的业务服务器运行的服务特定计算机上的所有 Skype 阻止新会话或阻止特定服务的新会话。</span><span class="sxs-lookup"><span data-stu-id="2fa2f-162">Use the Skype for Business Control Panel to prevent new sessions for all the Skype for Business Server services running on a specific computer or to prevent new sessions for a specific service.</span></span>

### <a name="prevent-new-sessions-for-all--skype-for-business-server-services-on-a-computer"></a><span data-ttu-id="2fa2f-163">为业务 Server 服务的计算机上的所有 Skype 阻止新会话</span><span class="sxs-lookup"><span data-stu-id="2fa2f-163">Prevent new sessions for all  Skype for Business Server services on a computer</span></span>

1. <span data-ttu-id="2fa2f-164">从用户帐户是 RTCUniversalServerAdmins 组的成员 （或具有同等用户权限），或分配给 CsServerAdministrator 或 CsAdministrator 角色，登录到在其中在部署 Skype Business Server 网络中的任一计算机.</span><span class="sxs-lookup"><span data-stu-id="2fa2f-164">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
2. <span data-ttu-id="2fa2f-165">打开一个浏览器窗口，然后输入管理 URL 以打开控制面板。</span><span class="sxs-lookup"><span data-stu-id="2fa2f-165">Open a browser window, and then enter the Admin URL to open the Control Panel.</span></span> <span data-ttu-id="2fa2f-166">有关可用于为业务 Server Control Panel 启动 Skype 的不同方法的详细信息，请参阅[安装和打开管理工具](../../management-tools/install-and-open-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="2fa2f-166">For details about the different methods you can use to start the Skype for Business Server Control Panel, see [Install and open administrative tools](../../management-tools/install-and-open-administrative-tools.md).</span></span>
3. <span data-ttu-id="2fa2f-167">在左侧的导航栏中，单击**拓扑**，然后单击**状态**。</span><span class="sxs-lookup"><span data-stu-id="2fa2f-167">In the left navigation bar, click **Topology** and then click **Status**.</span></span>
4. <span data-ttu-id="2fa2f-168">在状态页上排序或列表作为搜索所需找到正在运行要为其阻止新会话，然后单击的服务的计算机。</span><span class="sxs-lookup"><span data-stu-id="2fa2f-168">On the Status page, sort or search through the list as needed to find the computer that is running the services for which you want to prevent new sessions, and then click it.</span></span>
5. <span data-ttu-id="2fa2f-169">单击**操作**。</span><span class="sxs-lookup"><span data-stu-id="2fa2f-169">Click **Action**.</span></span>
6. <span data-ttu-id="2fa2f-170">单击**阻止所有服务的新会话**。</span><span class="sxs-lookup"><span data-stu-id="2fa2f-170">Click **Prevent new sessions for all services**.</span></span>

### <a name="prevent-new-sessions-for-a-specific-service"></a><span data-ttu-id="2fa2f-171">阻止特定服务的新会话</span><span class="sxs-lookup"><span data-stu-id="2fa2f-171">Prevent new sessions for a specific service</span></span>

1. <span data-ttu-id="2fa2f-172">从用户帐户是 RTCUniversalServerAdmins 组的成员 （或具有同等用户权限），或分配给 CsServerAdministrator 或 CsAdministrator 角色，登录到在其中在部署 Skype Business Server 网络中的任一计算机.</span><span class="sxs-lookup"><span data-stu-id="2fa2f-172">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
2. <span data-ttu-id="2fa2f-173">打开一个浏览器窗口，然后输入管理 URL 以打开控制面板。</span><span class="sxs-lookup"><span data-stu-id="2fa2f-173">Open a browser window, and then enter the Admin URL to open the Control Panel.</span></span> <span data-ttu-id="2fa2f-174">有关可用于为业务 Server Control Panel 启动 Skype 的不同方法的详细信息，请参阅[安装和打开管理工具](../../management-tools/install-and-open-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="2fa2f-174">For details about the different methods you can use to start the Skype for Business Server Control Panel, see [Install and open administrative tools](../../management-tools/install-and-open-administrative-tools.md).</span></span>
3. <span data-ttu-id="2fa2f-175">在左侧导航栏中，单击“**拓扑**”，然后单击“**状态**”。</span><span class="sxs-lookup"><span data-stu-id="2fa2f-175">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>
4. <span data-ttu-id="2fa2f-176">单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="2fa2f-176">Click **Properties**.</span></span>
5. <span data-ttu-id="2fa2f-177">如有必要，对服务，对列表进行排序，然后单击您要为其阻止新会话的服务。</span><span class="sxs-lookup"><span data-stu-id="2fa2f-177">Sort the list of services, if necessary, and click the service for which you want to prevent new sessions.</span></span>
6. <span data-ttu-id="2fa2f-178">单击**操作**。</span><span class="sxs-lookup"><span data-stu-id="2fa2f-178">Click **Action**.</span></span>
7. <span data-ttu-id="2fa2f-179">单击**阻止服务的新会话**。</span><span class="sxs-lookup"><span data-stu-id="2fa2f-179">Click **Prevent new sessions for service**.</span></span>
8. <span data-ttu-id="2fa2f-180">单击“关闭”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2fa2f-180">Click **Close**.</span></span>
