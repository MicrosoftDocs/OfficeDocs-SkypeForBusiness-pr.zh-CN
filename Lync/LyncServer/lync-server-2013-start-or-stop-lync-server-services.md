---
title: Lync Server 2013：启动或停止 Lync Server 服务
description: Lync Server 2013：启动或停止 Lync Server 服务。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Start or stop Lync Server 2013 services
ms:assetid: 1c70b4ec-9de5-4f7a-a3c9-c0eb76710505
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520958(v=OCS.15)
ms:contentKeyID: 48183554
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1d6e6520cbf6fda38676beab984c2d006061b019
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48541858"
---
# <a name="start-or-stop-lync-server-2013-services"></a><span data-ttu-id="200ed-103">启动或停止 Lync Server 2013 服务</span><span class="sxs-lookup"><span data-stu-id="200ed-103">Start or stop Lync Server 2013 services</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="200ed-104">_**上次修改的主题：** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="200ed-104">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="200ed-105">您可以使用 Lync Server 控制面板启动或停止在特定计算机上运行的所有 Lync Server 2013 服务，或者启动或停止特定服务。</span><span class="sxs-lookup"><span data-stu-id="200ed-105">You can use Lync Server Control Panel to start or stop all the Lync Server 2013 services running on a specific computer or to start or stop a specific service.</span></span>

<div>

## <a name="to-start-or-stop-all-lync-server-services-on-a-computer"></a><span data-ttu-id="200ed-106">启动或停止计算机上的所有 Lync Server 服务</span><span class="sxs-lookup"><span data-stu-id="200ed-106">To start or stop all Lync Server services on a computer</span></span>

1.  <span data-ttu-id="200ed-107">从作为 RTCUniversalServerAdmins 组成员的用户帐户 (或具有等效的用户权限) 或分配给 CsServerAdministrator 或 CsAdministrator 角色，请登录到您在其中部署了 Lync Server 2013 的网络中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="200ed-107">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span> <span data-ttu-id="200ed-108">您可以通过运行与以下内容类似的命令来确定您是否已分配 CsServerAdministrator 或 CsAdministrator RBAC 角色：</span><span class="sxs-lookup"><span data-stu-id="200ed-108">You can determine whether you have been assigned the CsServerAdministrator or the CsAdministrator RBAC role by running a command similar to the following:</span></span>
    
        Get-CsAdminRoleAssignment -Identity "kenmyer"

2.  <span data-ttu-id="200ed-109">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="200ed-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="200ed-110">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="200ed-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="200ed-111">在左侧导航栏中，单击“拓扑”\*\*\*\*，然后单击“状态”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="200ed-111">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="200ed-112">在“状态”\*\*\*\* 页上，根据需要对列表进行排序或搜索列表，以查找正在运行要启动或停止的服务的计算机，然后单击该计算机。</span><span class="sxs-lookup"><span data-stu-id="200ed-112">On the **Status** page, sort or search through the list as needed to find the computer that is running the services you want to start or stop, and then click it.</span></span>

5.  <span data-ttu-id="200ed-113">单击“操作”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="200ed-113">Click **Action**.</span></span>

6.  <span data-ttu-id="200ed-114">单击“启动所有服务”\*\*\*\* 或“停止所有服务”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="200ed-114">Click **Start All services** or **Stop All services**.</span></span>

</div>

<div>

## <a name="to-start-or-stop-a-specific-service"></a><span data-ttu-id="200ed-115">启动或停止特定服务</span><span class="sxs-lookup"><span data-stu-id="200ed-115">To start or stop a specific service</span></span>

1.  <span data-ttu-id="200ed-116">使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="200ed-116">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="200ed-117">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="200ed-117">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="200ed-118">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="200ed-118">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="200ed-119">在左侧导航栏中，单击“拓扑”\*\*\*\*，然后单击“状态”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="200ed-119">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="200ed-120">在“状态”\*\*\*\* 页上，根据需要对列表进行排序或搜索列表，以查找正在运行要启动或停止的服务的计算机，然后单击该计算机。</span><span class="sxs-lookup"><span data-stu-id="200ed-120">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span>

5.  <span data-ttu-id="200ed-121">单击“属性”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="200ed-121">Click **Properties**.</span></span>

6.  <span data-ttu-id="200ed-122">如有必要，对服务列表进行排序，然后单击要启动或停止的服务。</span><span class="sxs-lookup"><span data-stu-id="200ed-122">Sort the list of services, if necessary, and click the service you want to start or stop.</span></span>

7.  <span data-ttu-id="200ed-123">单击“操作”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="200ed-123">Click **Action**.</span></span>

8.  <span data-ttu-id="200ed-124">单击“启动服务”\*\*\*\* 或“停止服务”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="200ed-124">Click **Start service** or **Stop service**.</span></span>

9.  <span data-ttu-id="200ed-125">单击“关闭”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="200ed-125">Click **Close**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="200ed-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="200ed-126">See Also</span></span>


[<span data-ttu-id="200ed-127">在 Lync Server 2013 中阻止服务的会话</span><span class="sxs-lookup"><span data-stu-id="200ed-127">Prevent sessions for services in Lync Server 2013</span></span>](lync-server-2013-prevent-sessions-for-services.md)  


[<span data-ttu-id="200ed-128">管理 Lync Server 2013 拓扑</span><span class="sxs-lookup"><span data-stu-id="200ed-128">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

