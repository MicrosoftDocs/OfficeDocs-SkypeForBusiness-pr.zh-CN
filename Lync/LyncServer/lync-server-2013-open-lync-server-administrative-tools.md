---
title: Lync Server 2013：打开 Lync Server 管理工具
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Open Lync Server administrative tools
ms:assetid: 8c58de94-9e0a-4368-9e14-9afcaa1142d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195741(v=OCS.15)
ms:contentKeyID: 48184778
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f3c1b2eec210b22bc45a27c9635507c7ad83553
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755826"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="open-lync-server-2013-administrative-tools"></a><span data-ttu-id="d2f4f-102">打开 Lync Server 2013 管理工具</span><span class="sxs-lookup"><span data-stu-id="d2f4f-102">Open Lync Server 2013 administrative tools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d2f4f-103">_**主题上次修改时间：** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="d2f4f-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="d2f4f-104">你可以使用本主题中的过程打开管理工具，以部署、配置 Lync Server 2013 拓扑或对其进行故障排除。</span><span class="sxs-lookup"><span data-stu-id="d2f4f-104">You can use the procedures in this topic to open administrative tools to deploy, configure, or troubleshoot your Lync Server 2013 topology.</span></span>

  - <span data-ttu-id="d2f4f-105">部署向导</span><span class="sxs-lookup"><span data-stu-id="d2f4f-105">Deployment Wizard</span></span>

  - <span data-ttu-id="d2f4f-106">拓扑生成器</span><span class="sxs-lookup"><span data-stu-id="d2f4f-106">Topology Builder</span></span>

  - <span data-ttu-id="d2f4f-107">Lync Server 控制面板</span><span class="sxs-lookup"><span data-stu-id="d2f4f-107">Lync Server Control Panel</span></span>

  - <span data-ttu-id="d2f4f-108">Lync Server 命令行管理程序</span><span class="sxs-lookup"><span data-stu-id="d2f4f-108">Lync Server Management Shell</span></span>

<span id="BKMK_OpenDeploymentWizard"></span>

<div>

## <a name="deployment-wizard"></a><span data-ttu-id="d2f4f-109">部署向导</span><span class="sxs-lookup"><span data-stu-id="d2f4f-109">Deployment Wizard</span></span>

<span data-ttu-id="d2f4f-110">使用以下过程在本地启动部署向导以添加或删除 Lync Server 2013 组件文件。</span><span class="sxs-lookup"><span data-stu-id="d2f4f-110">Use the following procedure to start the Deployment Wizard locally to add or remove Lync Server 2013 component files.</span></span>

<div>

## <a name="to-start-lync-server-2013-deployment-wizard"></a><span data-ttu-id="d2f4f-111">启动 Lync Server 2013 部署向导</span><span class="sxs-lookup"><span data-stu-id="d2f4f-111">To start Lync Server 2013 Deployment Wizard</span></span>

1.  <span data-ttu-id="d2f4f-112">登录到安装了 Lync Server 部署向导的计算机，作为 "域管理员" 组和 "RTCUniversalServerAdmins" 组的成员。</span><span class="sxs-lookup"><span data-stu-id="d2f4f-112">Log on to the computer where the Lync Server Deployment Wizard is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="d2f4f-113">单击 "**开始**"，单击 "**所有程序**"，单击 " **Microsoft Lync server 2013**"，然后单击 " **Lync server 部署向导**"。</span><span class="sxs-lookup"><span data-stu-id="d2f4f-113">Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Deployment Wizard**.</span></span>

</div>

</div>

<span id="BKMK_OpenTopologyBuilder"></span>

<div>

## <a name="topology-builder"></a><span data-ttu-id="d2f4f-114">拓扑生成器</span><span class="sxs-lookup"><span data-stu-id="d2f4f-114">Topology Builder</span></span>

<span data-ttu-id="d2f4f-115">使用以下过程打开拓扑生成器以定义要在 Lync Server 2013 拓扑中部署的服务器。</span><span class="sxs-lookup"><span data-stu-id="d2f4f-115">Use the following procedure to open the Topology Builder to define the servers that you want to deploy in your Lync Server 2013 topology.</span></span>

<div>

## <a name="to-open-lync-server-2013-topology-builder-to-design-the-topology"></a><span data-ttu-id="d2f4f-116">打开 Lync Server 2013 拓扑生成器以设计拓扑</span><span class="sxs-lookup"><span data-stu-id="d2f4f-116">To open Lync Server 2013 Topology Builder to design the topology</span></span>

1.  <span data-ttu-id="d2f4f-117">以 Domain Admins 组和 RTCUniversalServerAdmins 组成员的身份登录安装了拓扑生成器的计算机。</span><span class="sxs-lookup"><span data-stu-id="d2f4f-117">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d2f4f-118">你可以通过使用属于本地用户组的成员的帐户定义拓扑，但要读取、发布或启用拓扑（需要在服务器上安装 Lync Server 2013），必须使用域管理员组和 RTCUniv 的成员帐户。ersalServerAdmins 组，并且具有对要用于存档文件存储的文件共享的完全控制权限（即读取、写入和修改），以便拓扑生成器可以配置所需的随机访问控制列表（Dacl），或具有同等用户权限的帐户。</span><span class="sxs-lookup"><span data-stu-id="d2f4f-118">You can define a topology by using an account that is a member of the local Users group, but to read, publish, or enable a topology, which is required to install Lync Server 2013 on a server, you must use an account that is a member of the Domain Admins group and the RTCUniversalServerAdmins group, and that has full control permissions (that is, read, write, and modify) on the file share that you are going to use for the archiving file store so that Topology Builder can configure the required discretionary access control list (DACLs), or an account with equivalent user rights.</span></span>

    
    </div>

2.  <span data-ttu-id="d2f4f-119">启动拓扑生成器：单击 "**开始**"，单击 "**所有程序**"，单击 " **Microsoft Lync server 2013**"，然后单击 " **Lync server 拓扑生成器**"。</span><span class="sxs-lookup"><span data-stu-id="d2f4f-119">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

</div>

</div>

<span id="BKMK_OpenControlPanel"></span>

<div>

## <a name="lync-server-2013-control-panel"></a><span data-ttu-id="d2f4f-120">Lync Server 2013 控制面板</span><span class="sxs-lookup"><span data-stu-id="d2f4f-120">Lync Server 2013 Control Panel</span></span>

<span data-ttu-id="d2f4f-121">使用以下过程之一打开 Lync Server 2013 控制面板以管理你环境中的服务器、用户、客户端和设备的配置。</span><span class="sxs-lookup"><span data-stu-id="d2f4f-121">Use one of the following procedures to open Lync Server 2013 Control Panel to manage the configuration of servers, users, clients, and devices in your environment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d2f4f-122">你可以使用分配给 CsAdministrator 角色的用户帐户在 Lync Server 2013 "控制面板" 中执行任何任务。</span><span class="sxs-lookup"><span data-stu-id="d2f4f-122">You can use a user account that is assigned to the CsAdministrator role to perform any task in Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="d2f4f-123">你可以使用其他角色登录 Lync Server 2013 控制面板以执行特定的管理任务，具体取决于你需要执行的任务。</span><span class="sxs-lookup"><span data-stu-id="d2f4f-123">You can use other roles to log on to Lync Server 2013 Control Panel to perform specific administration tasks, dependent on the task you need to perform.</span></span> <span data-ttu-id="d2f4f-124">例如，你可以使用 CSArchivingAdministrator 在 Lync Server 2013 控制面板中管理存档。</span><span class="sxs-lookup"><span data-stu-id="d2f4f-124">For example, you can use CSArchivingAdministrator to administer Archiving in Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="d2f4f-125">有关角色的详细信息，请参阅规划文档中的在<A href="lync-server-2013-planning-for-role-based-access-control.md">Lync Server 2013 中规划基于角色的访问控制</A>。</span><span class="sxs-lookup"><span data-stu-id="d2f4f-125">For details about roles, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> in the Planning documentation.</span></span> <span data-ttu-id="d2f4f-126">有关可用于执行特定任务的角色的详细信息，请参阅该任务的文档。</span><span class="sxs-lookup"><span data-stu-id="d2f4f-126">For details about the roles that you can use to perform a specific task, see the documentation for the task.</span></span>



</div>

<div>

## <a name="to-open-lync-server-2013-control-panel-from-any-computer-inside-your-organizations-firewall"></a><span data-ttu-id="d2f4f-127">从组织防火墙内的任何计算机打开 Lync Server 2013 控制面板</span><span class="sxs-lookup"><span data-stu-id="d2f4f-127">To open Lync Server 2013 Control Panel from any computer inside your organization’s firewall</span></span>

1.  <span data-ttu-id="d2f4f-128">从分配给 CsAdministrator 角色的用户帐户或具有要执行的任务的相应权限的其他角色，使用 1024 x 768 的最低屏幕分辨率登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="d2f4f-128">From a user account that is assigned to the CsAdministrator role or other role that has appropriate user rights and permissions for the task to be performed, log on to any computer in your internal deployment with a minimum screen resolution of 1024 x 768.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="d2f4f-129">如果已配置了管理简单的统一资源定位器（URL），则可以从组织防火墙内任何计算机上运行的 Internet 浏览器访问 Lync Server 2013 控制面板。</span><span class="sxs-lookup"><span data-stu-id="d2f4f-129">If you have configured an administration simple uniform resource locator (URL), you can access Lync Server 2013 Control Panel from an Internet browser that is running on any computer within your organization’s firewall.</span></span> <span data-ttu-id="d2f4f-130">有关配置管理简单 URL 的详细信息，请参阅规划文档中的 "<A href="lync-server-2013-planning-for-simple-urls.md">在 Lync server 2013 中规划简单 url</A> " 和 "在部署文档中在<A href="lync-server-2013-edit-or-configure-simple-urls.md">lync Server 2013 中编辑或配置简单 url</A> "。</span><span class="sxs-lookup"><span data-stu-id="d2f4f-130">For details about configuring the administration simple URL, see <A href="lync-server-2013-planning-for-simple-urls.md">Planning for simple URLs in Lync Server 2013</A> in the Planning documentation and <A href="lync-server-2013-edit-or-configure-simple-urls.md">Edit or configure simple URLs in Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

2.  <span data-ttu-id="d2f4f-131">打开一个浏览器窗口，然后输入为你的组织配置的管理员 URL。</span><span class="sxs-lookup"><span data-stu-id="d2f4f-131">Open a browser window, and then enter the Admin URL configured for your organization.</span></span>

</div>

<div>

## <a name="to-open-lync-server-2013-control-panel-on-a-computer-running-lync-server-2013"></a><span data-ttu-id="d2f4f-132">在运行 Lync Server 2013 的计算机上打开 Lync Server 2013 控制面板</span><span class="sxs-lookup"><span data-stu-id="d2f4f-132">To open Lync Server 2013 Control Panel on a computer running Lync Server 2013</span></span>

1.  <span data-ttu-id="d2f4f-133">从属于 CsAdministrator 角色的用户帐户或其他具有要执行任务的相应权限的角色的用户帐户，登录到已安装 Lync Server 2013 的计算机，或者至少是 Lync Server 2013 administrat我的工具。</span><span class="sxs-lookup"><span data-stu-id="d2f4f-133">From a user account that is a member of the CsAdministrator role or other role that has appropriate user rights and permissions for the task to be performed, log on to a computer on which you have installed Lync Server 2013 or, at a minimum, the Lync Server 2013 administrative tools.</span></span> <span data-ttu-id="d2f4f-134">要配置设置，计算机必须具有最小的屏幕分辨率 1024 x 768。</span><span class="sxs-lookup"><span data-stu-id="d2f4f-134">To configure settings, the computer must have a minimum screen resolution of 1024 x 768.</span></span>

2.  <span data-ttu-id="d2f4f-135">启动 Lync Server 2013 控制面板：单击 "**开始**"，单击 "**所有程序**"，指向 "**管理工具**"，指向 " **Microsoft Lync Server 2013**"，然后单击 " **Lync server 2013 控制面板**"。</span><span class="sxs-lookup"><span data-stu-id="d2f4f-135">Start Lync Server 2013 Control Panel: Click **Start**, click **All Programs**, point to **Administrative Tools**, point to **Microsoft Lync Server 2013**, and then click **Lync Server 2013 Control Panel**.</span></span>

</div>

</div>

<span id="BKMK_OpenManagementShell"></span>

<div>

## <a name="lync-server-2013-management-shell"></a><span data-ttu-id="d2f4f-136">Lync Server 2013 命令行管理程序</span><span class="sxs-lookup"><span data-stu-id="d2f4f-136">Lync Server 2013 Management Shell</span></span>

<span data-ttu-id="d2f4f-137">使用以下过程打开 Lync Server 2013 管理外壳程序，以使用命令行管理你环境中的服务器、用户、客户端和设备。</span><span class="sxs-lookup"><span data-stu-id="d2f4f-137">Use the following procedure to open Lync Server 2013 Management Shell to administer servers, users, clients, and devices in your environment by using the command line.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d2f4f-138">你可以使用分配给 CsAdministrator 角色的用户帐户在 Lync Server 2013 命令行管理程序中执行任何任务。</span><span class="sxs-lookup"><span data-stu-id="d2f4f-138">You can use a user account that is assigned to the CsAdministrator role to perform any task in Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="d2f4f-139">你可以使用其他角色登录，以执行特定的管理任务，具体取决于你需要执行的任务。</span><span class="sxs-lookup"><span data-stu-id="d2f4f-139">You can log on using other roles to perform specific administration tasks, depending on the task you need to perform.</span></span> <span data-ttu-id="d2f4f-140">例如，你可以使用 CSArchivingAdministrator 来运行与存档管理相关的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d2f4f-140">For example, you can use CSArchivingAdministrator to run cmdlets related to Archiving administration.</span></span> <span data-ttu-id="d2f4f-141">有关角色的详细信息，请参阅规划文档中的在<A href="lync-server-2013-planning-for-role-based-access-control.md">Lync Server 2013 中规划基于角色的访问控制</A>。</span><span class="sxs-lookup"><span data-stu-id="d2f4f-141">For details about roles, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> in the Planning documentation.</span></span> <span data-ttu-id="d2f4f-142">有关可用于运行特定 cmdlet 的角色的详细信息，请参阅 cmdlet 的文档。</span><span class="sxs-lookup"><span data-stu-id="d2f4f-142">For details about the roles that you can use to run a specific cmdlet, see the documentation for the cmdlet.</span></span><BR><span data-ttu-id="d2f4f-143">你还可以使用 RTCUniversalServerAdmins、RTCUniversalUserAdmins 或 RTCUniversalReadOnlyAdmins 组中的用户帐户（具体取决于 cmdlet）运行某些 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d2f4f-143">You can also run certain cmdlets by using a user account in the RTCUniversalServerAdmins, RTCUniversalUserAdmins, or RTCUniversalReadOnlyAdmins groups, depending on the cmdlet.</span></span>



</div>

<div>

## <a name="to-open-the-lync-server-2013-management-shell"></a><span data-ttu-id="d2f4f-144">打开 Lync Server 2013 命令行管理程序</span><span class="sxs-lookup"><span data-stu-id="d2f4f-144">To open the Lync Server 2013 Management Shell</span></span>

  - <span data-ttu-id="d2f4f-145">如果打开的是 Windows PowerShell 窗口，而不是 Lync Server 2013 管理程序外壳，则默认情况下无法运行 Lync Server 2013 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d2f4f-145">If you open a Windows PowerShell window rather than the Lync Server 2013 Management Shell, by default you cannot run the Lync Server 2013 cmdlets.</span></span> <span data-ttu-id="d2f4f-146">若要从 Windows PowerShell 中运行 Lync Server 2013 cmdlet，请在 Windows PowerShell 命令提示符处键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="d2f4f-146">To run the Lync Server 2013 cmdlets from within Windows PowerShell, type the following at the Windows PowerShell command prompt:</span></span>
    
    `Import-Module Lync`

  - <span data-ttu-id="d2f4f-147">启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management shell**"。</span><span class="sxs-lookup"><span data-stu-id="d2f4f-147">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d2f4f-148">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d2f4f-148">See Also</span></span>


[<span data-ttu-id="d2f4f-149">安装 Lync Server 2013 管理工具</span><span class="sxs-lookup"><span data-stu-id="d2f4f-149">Install Lync Server 2013 administrative tools</span></span>](lync-server-2013-install-lync-server-administrative-tools.md)  


[<span data-ttu-id="d2f4f-150">Lync Server 2013 管理工具</span><span class="sxs-lookup"><span data-stu-id="d2f4f-150">Lync Server 2013 administrative tools</span></span>](lync-server-2013-lync-server-administrative-tools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

