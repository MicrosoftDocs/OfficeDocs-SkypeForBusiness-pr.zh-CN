---
title: Lync Server 2013：阻止服务会话
description: Lync Server 2013：阻止服务会话。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Prevent sessions for services
ms:assetid: 977dcc5c-2aac-48ef-86a1-a8d47b4d9e74
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182553(v=OCS.15)
ms:contentKeyID: 48184866
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 846a9da5330c3e64f61c27dfadd883f0c43a0ffa
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579808"
---
# <a name="prevent-sessions-for-services-in-lync-server-2013"></a><span data-ttu-id="8fa63-103">在 Lync Server 2013 中阻止服务的会话</span><span class="sxs-lookup"><span data-stu-id="8fa63-103">Prevent sessions for services in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8fa63-104">_**上次修改的主题：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="8fa63-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="8fa63-105">您可以使用 Lync Server 控制面板阻止在特定计算机上运行的所有 Lync Server 2013 服务的新会话或阻止特定 Lync Server 2013 服务的新会话。</span><span class="sxs-lookup"><span data-stu-id="8fa63-105">You can use Lync Server Control Panel to prevent new sessions for all the Lync Server 2013 services running on a specific computer or to prevent new sessions for a specific Lync Server 2013 service.</span></span>

<div>

## <a name="to-prevent-new-sessions-for-all-lync-server-services-on-a-computer"></a><span data-ttu-id="8fa63-106">阻止计算机上所有 Lync Server 服务的新会话</span><span class="sxs-lookup"><span data-stu-id="8fa63-106">To prevent new sessions for all Lync Server services on a computer</span></span>

1.  <span data-ttu-id="8fa63-107">从作为 RTCUniversalServerAdmins 组成员的用户帐户 (或具有等效的用户权限) 或分配给 CsServerAdministrator 或 CsAdministrator 角色，请登录到您在其中部署了 Lync Server 2013 的网络中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="8fa63-107">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="8fa63-108">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="8fa63-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="8fa63-109">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="8fa63-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="8fa63-110">在左侧导航栏中，单击“拓扑”\*\*\*\*，然后单击“状态”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8fa63-110">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="8fa63-111">在“状态”\*\*\*\* 页上，根据需要对列表进行排序或搜索，以查找正在运行要对其阻止新会话的服务的计算机，然后单击该计算机。</span><span class="sxs-lookup"><span data-stu-id="8fa63-111">On the **Status** page, sort or search through the list as needed to find the computer that is running the services for which you want to prevent new sessions, and then click it.</span></span>

5.  <span data-ttu-id="8fa63-112">单击“操作”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8fa63-112">Click **Action**.</span></span>

6.  <span data-ttu-id="8fa63-113">单击“阻止所有服务的新会话”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8fa63-113">Click **Prevent new sessions for all services**.</span></span>

</div>

<div>

## <a name="to-prevent-new-sessions-for-a-specific-service"></a><span data-ttu-id="8fa63-114">阻止特定服务的新会话</span><span class="sxs-lookup"><span data-stu-id="8fa63-114">To prevent new sessions for a specific service</span></span>

1.  <span data-ttu-id="8fa63-115">从作为 RTCUniversalServerAdmins 组成员的用户帐户 (或具有等效的用户权限) 或分配给 CsServerAdministrator 或 CsAdministrator 角色，请登录到您在其中部署了 Lync Server 2013 的网络中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="8fa63-115">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="8fa63-116">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="8fa63-116">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="8fa63-117">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="8fa63-117">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="8fa63-118">在左侧导航栏中，单击“拓扑”\*\*\*\*，然后单击“状态”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8fa63-118">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="8fa63-119">在“状态”\*\*\*\* 页上，根据需要对列表进行排序或搜索列表，以查找正在运行要启动或停止的服务的计算机，然后单击该计算机。</span><span class="sxs-lookup"><span data-stu-id="8fa63-119">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span>

5.  <span data-ttu-id="8fa63-120">单击“属性”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8fa63-120">Click **Properties**.</span></span>

6.  <span data-ttu-id="8fa63-121">如有必要，对服务列表进行排序，然后单击要对其阻止新会话的服务。</span><span class="sxs-lookup"><span data-stu-id="8fa63-121">Sort the list of services, if necessary, and click the service for which you want to prevent new sessions.</span></span>

7.  <span data-ttu-id="8fa63-122">单击“操作”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8fa63-122">Click **Action**.</span></span>

8.  <span data-ttu-id="8fa63-123">单击“阻止服务的新会话”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8fa63-123">Click **Prevent new sessions for service**.</span></span>

9.  <span data-ttu-id="8fa63-124">单击“关闭”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8fa63-124">Click **Close**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8fa63-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8fa63-125">See Also</span></span>


[<span data-ttu-id="8fa63-126">管理 Lync Server 2013 拓扑</span><span class="sxs-lookup"><span data-stu-id="8fa63-126">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

