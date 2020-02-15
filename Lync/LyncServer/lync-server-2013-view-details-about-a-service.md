---
title: Lync Server 2013：查看有关服务的详细信息
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View details about a service
ms:assetid: bc8e8202-cd68-47e4-95b2-bb36e51cc124
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182578(v=OCS.15)
ms:contentKeyID: 48185253
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f8268720754f0f34fa24a5a5c7beef9ac21b5d3e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048256"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-details-about-a-service-in-lync-server-2013"></a><span data-ttu-id="df19d-102">在 Lync Server 2013 中查看有关服务的详细信息</span><span class="sxs-lookup"><span data-stu-id="df19d-102">View details about a service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="df19d-103">_**上次修改的主题：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="df19d-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="df19d-104">您可以使用 Lync Server 控制面板查看有关在拓扑中的特定计算机上运行的每个服务的详细信息。</span><span class="sxs-lookup"><span data-stu-id="df19d-104">You can use Lync Server Control Panel to view details about each service that is running on a specific computer in your topology.</span></span> <span data-ttu-id="df19d-105">可以查看每个服务的状态和详细信息（如关联的数据库、端口和相关服务）。</span><span class="sxs-lookup"><span data-stu-id="df19d-105">You can view the status of each service and details such as the associated databases, ports, and dependent services.</span></span>

<div>

## <a name="to-view-details-for-a-service"></a><span data-ttu-id="df19d-106">查看服务的详细信息</span><span class="sxs-lookup"><span data-stu-id="df19d-106">To view details for a service</span></span>

1.  <span data-ttu-id="df19d-107">从分配给任何适用于 Lync Server 2013 的任何预定义管理角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="df19d-107">From a user account that is assigned to any of the predefined administrative roles for Lync Server 2013, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="df19d-108">有关 Lync Server 2013 中提供的预定义管理角色的详细信息，请参阅[在 Lync server 2013 中规划基于角色的访问控制](lync-server-2013-planning-for-role-based-access-control.md)。</span><span class="sxs-lookup"><span data-stu-id="df19d-108">For details about the predefined administrative roles available in Lync Server 2013, see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md).</span></span>

2.  <span data-ttu-id="df19d-109">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="df19d-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="df19d-110">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="df19d-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="df19d-111">在左侧导航栏中，单击“拓扑”\*\*\*\*，然后单击“状态”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="df19d-111">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="df19d-112">在“状态”\*\*\*\* 页中，对列表进行排序或搜索列表，然后单击要查看的计算机。</span><span class="sxs-lookup"><span data-stu-id="df19d-112">In the **Status** page, sort or search through the list and then click the computer that you want to view.</span></span>

5.  <span data-ttu-id="df19d-113">单击“属性”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="df19d-113">Click **Properties**.</span></span>

6.  <span data-ttu-id="df19d-114">在“查看计算机详细信息”\*\*\*\* 窗口中，根据需要对服务列表进行排序，然后单击要查看的服务。</span><span class="sxs-lookup"><span data-stu-id="df19d-114">In the **View Computer Detail** window, sort the list of services, if necessary, and click the service you want to view.</span></span>

7.  <span data-ttu-id="df19d-115">根据需要执行下列任意操作：</span><span class="sxs-lookup"><span data-stu-id="df19d-115">Do any of the following as needed:</span></span>
    
      - <span data-ttu-id="df19d-116">要查看特定服务的最新状态，请单击“获取服务状态”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="df19d-116">To see the latest status of that specific service, click **Get service status**.</span></span>
    
      - <span data-ttu-id="df19d-117">要查看特定服务的详细信息，请单击“属性”\*\*\*\*，然后单击“关闭”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="df19d-117">To see the details for that specific service, click **Properties** and then click **Close**.</span></span>
    
      - <span data-ttu-id="df19d-118">要返回拓扑中所有计算机的列表，请单击“关闭”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="df19d-118">To return to the list of all computers in your topology, click **Close**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="df19d-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="df19d-119">See Also</span></span>


[<span data-ttu-id="df19d-120">管理 Lync Server 2013 拓扑</span><span class="sxs-lookup"><span data-stu-id="df19d-120">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

