---
title: Lync Server 2013：查看运行 Lync Server 2013 的计算机的列表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View a list of computers running Lync Server 2013
ms:assetid: 44eeec27-8b99-44f0-b0bd-622c12393d34
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520987(v=OCS.15)
ms:contentKeyID: 48184030
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eca6cc07cd8936f228eb8443eb79c44e5d6b4dc7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211608"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-a-list-of-computers-running-lync-server-2013"></a><span data-ttu-id="a21f6-102">查看运行 Lync Server 2013 的计算机的列表</span><span class="sxs-lookup"><span data-stu-id="a21f6-102">View a list of computers running Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a21f6-103">_**上次修改的主题：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="a21f6-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="a21f6-104">您可以使用 Lync Server 2013 控制面板查看拓扑中运行 Lync Server 2013 的所有计算机的列表，并查看每个计算机的服务状态。</span><span class="sxs-lookup"><span data-stu-id="a21f6-104">You can use Lync Server 2013 Control Panel to view a list of all the computers that are running Lync Server 2013 in your topology and see the service status of each.</span></span> <span data-ttu-id="a21f6-105">可以按计算机、池或站点对列表进行排序。</span><span class="sxs-lookup"><span data-stu-id="a21f6-105">You can sort the list by computer, pool, or site.</span></span>

<div>

## <a name="to-view-a-list-of-computers-running-lync-server"></a><span data-ttu-id="a21f6-106">查看运行 Lync Server 的计算机列表</span><span class="sxs-lookup"><span data-stu-id="a21f6-106">To view a list of computers running Lync Server</span></span>

1.  <span data-ttu-id="a21f6-107">从分配给任何适用于 Lync Server 2013 的任何预定义管理角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="a21f6-107">From a user account that is assigned to any of the predefined administrative roles for Lync Server 2013, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="a21f6-108">有关 Lync Server 2013 中提供的预定义管理角色的详细信息，请参阅[在 Lync server 2013 中规划基于角色的访问控制](lync-server-2013-planning-for-role-based-access-control.md)。</span><span class="sxs-lookup"><span data-stu-id="a21f6-108">For details about the predefined administrative roles available in Lync Server 2013, see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md).</span></span>

2.  <span data-ttu-id="a21f6-109">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="a21f6-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a21f6-110">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="a21f6-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="a21f6-111">在左侧导航栏中，单击“拓扑”\*\*\*\*，然后单击“状态”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a21f6-111">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="a21f6-112">根据需要，在“状态”\*\*\*\* 页上执行下列任意操作：</span><span class="sxs-lookup"><span data-stu-id="a21f6-112">On the **Status** page, do any of the following as needed:</span></span>
    
      - <span data-ttu-id="a21f6-113">单击“计算机”\*\*\*\*、“池”\*\*\*\* 或“站点”\*\*\*\* 列标题，然后单击向上箭头或向下箭头对列表进行排序。</span><span class="sxs-lookup"><span data-stu-id="a21f6-113">Sort the list by clicking the **Computer**, **Pool**, or **Site** column heading, and then clicking the up arrow or the down arrow.</span></span>
    
      - <span data-ttu-id="a21f6-114">单击“刷新”\*\*\*\* 查看最新列表。</span><span class="sxs-lookup"><span data-stu-id="a21f6-114">Click **Refresh** to view the most up-to-date list.</span></span>
    
      - <span data-ttu-id="a21f6-115">通过在搜索字段中键入计算机名称来搜索特定的计算机。</span><span class="sxs-lookup"><span data-stu-id="a21f6-115">Search for a specific computer by typing the computer name in the search field.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a21f6-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a21f6-116">See Also</span></span>


[<span data-ttu-id="a21f6-117">管理 Lync Server 2013 拓扑</span><span class="sxs-lookup"><span data-stu-id="a21f6-117">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

