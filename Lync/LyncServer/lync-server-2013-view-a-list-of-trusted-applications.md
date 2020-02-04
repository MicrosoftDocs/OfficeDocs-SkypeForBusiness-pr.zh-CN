---
title: Lync Server 2013：查看受信任的应用程序列表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View a list of trusted applications
ms:assetid: f09300b3-67cf-4e70-a51a-23d62479b913
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182604(v=OCS.15)
ms:contentKeyID: 48185844
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3d5f9d112e045e753147f7fcffa875177a6feb0d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757496"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-a-list-of-trusted-applications-in-lync-server-2013"></a><span data-ttu-id="8f66e-102">在 Lync Server 2013 中查看受信任的应用程序列表</span><span class="sxs-lookup"><span data-stu-id="8f66e-102">View a list of trusted applications in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8f66e-103">_**主题上次修改时间：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="8f66e-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="8f66e-104">你可以使用 Lync Server 2013 控制面板查看你在 Lync Server 2013 环境中部署的受信任的应用程序的列表。</span><span class="sxs-lookup"><span data-stu-id="8f66e-104">You can use Lync Server 2013 Control Panel to view a list of the trusted applications that you have deployed in your Lync Server 2013 environment.</span></span> <span data-ttu-id="8f66e-105">受信任的应用程序是基于 Microsoft 统一通信托管 API （UCMA） 3.0 Core SDK 受 Lync Server 2013 信任的应用程序。</span><span class="sxs-lookup"><span data-stu-id="8f66e-105">A trusted application is an application based on Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK that is trusted by Lync Server 2013.</span></span> <span data-ttu-id="8f66e-106">下表总结了此信任关系：</span><span class="sxs-lookup"><span data-stu-id="8f66e-106">This trust relationship is summarized in the following list:</span></span>

  - <span data-ttu-id="8f66e-107">受信任的应用程序不会挑战 Lync Server 的身份验证。</span><span class="sxs-lookup"><span data-stu-id="8f66e-107">Trusted applications are not challenged for authentication by Lync Server.</span></span>

  - <span data-ttu-id="8f66e-108">Lync Server 不会阻止受信任的应用程序进行 SIP 事务、连接或通过 Internet 协议（VoIP）呼叫发出语音。</span><span class="sxs-lookup"><span data-stu-id="8f66e-108">Trusted applications are not throttled by Lync Server for SIP transactions, connections or outgoing Voice over Internet Protocol (VoIP) calls.</span></span>

  - <span data-ttu-id="8f66e-109">受信任的应用程序可以模拟任何用户，并且可以加入会议，而无需出现在海报中。</span><span class="sxs-lookup"><span data-stu-id="8f66e-109">Trusted applications can impersonate any user and can join conferences without appearing in rosters.</span></span>

  - <span data-ttu-id="8f66e-110">受信任的应用程序高度可用且具有弹性。</span><span class="sxs-lookup"><span data-stu-id="8f66e-110">Trusted applications are highly available and resilient.</span></span>

<span data-ttu-id="8f66e-111">在 Lync Server 控制面板中，你可以看到应用程序的名称、运行的池以及它们所使用的端口。</span><span class="sxs-lookup"><span data-stu-id="8f66e-111">In Lync Server Control Panel, you can see the name of the applications, the pool where they run, and the port they use.</span></span>

<div>

## <a name="to-view-a-list-of-trusted-applications"></a><span data-ttu-id="8f66e-112">查看受信任的应用程序列表</span><span class="sxs-lookup"><span data-stu-id="8f66e-112">To view a list of trusted applications</span></span>

1.  <span data-ttu-id="8f66e-113">使用分配给 CsServerAdministrator、CsAdministrator、CsHelpDesk 或 CsViewOnlyAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="8f66e-113">From a user account that is assigned to the CsServerAdministrator, CsAdministrator, CsHelpDesk, or CsViewOnlyAdministrator role, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="8f66e-114">有关 Lync Server 2013 中可用的预定义管理角色的详细信息，请参阅[在 Lync server 2013 中规划基于角色的访问控制](lync-server-2013-planning-for-role-based-access-control.md)。</span><span class="sxs-lookup"><span data-stu-id="8f66e-114">For details about the predefined administrative roles available in Lync Server 2013, see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md).</span></span>

2.  <span data-ttu-id="8f66e-115">打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="8f66e-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="8f66e-116">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="8f66e-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="8f66e-117">在左侧导航栏中，单击 "**拓扑**"，然后单击 "**受信任的应用程序**"。</span><span class="sxs-lookup"><span data-stu-id="8f66e-117">In the left navigation bar, click **Topology** and the click **Trusted Application**.</span></span>

4.  <span data-ttu-id="8f66e-118">如果需要，请在 "**受信任的应用程序**" 页面上，单击列标题以对应用程序进行排序。</span><span class="sxs-lookup"><span data-stu-id="8f66e-118">On the **Trusted Application** page, click a column heading to sort the applications, if needed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8f66e-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8f66e-119">See Also</span></span>


[<span data-ttu-id="8f66e-120">管理 Lync Server 2013 拓扑</span><span class="sxs-lookup"><span data-stu-id="8f66e-120">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

