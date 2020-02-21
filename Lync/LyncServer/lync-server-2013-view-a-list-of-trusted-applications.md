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
ms.openlocfilehash: 8678ed12269f7f78d6d169b518e7f1208d92a7fd
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211598"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-a-list-of-trusted-applications-in-lync-server-2013"></a><span data-ttu-id="9c11c-102">在 Lync Server 2013 中查看受信任的应用程序列表</span><span class="sxs-lookup"><span data-stu-id="9c11c-102">View a list of trusted applications in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9c11c-103">_**上次修改的主题：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="9c11c-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="9c11c-104">您可以使用 Lync Server 2013 控制面板查看您在 Lync Server 2013 环境中部署的受信任应用程序的列表。</span><span class="sxs-lookup"><span data-stu-id="9c11c-104">You can use Lync Server 2013 Control Panel to view a list of the trusted applications that you have deployed in your Lync Server 2013 environment.</span></span> <span data-ttu-id="9c11c-105">受信任的应用程序是基于 Microsoft 统一通信托管 API （UCMA） 3.0 Core SDK 的应用程序，受 Lync Server 2013 信任。</span><span class="sxs-lookup"><span data-stu-id="9c11c-105">A trusted application is an application based on Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK that is trusted by Lync Server 2013.</span></span> <span data-ttu-id="9c11c-106">以下列表概述了此信任关系：</span><span class="sxs-lookup"><span data-stu-id="9c11c-106">This trust relationship is summarized in the following list:</span></span>

  - <span data-ttu-id="9c11c-107">受信任的应用程序不会受到 Lync Server 身份验证的挑战。</span><span class="sxs-lookup"><span data-stu-id="9c11c-107">Trusted applications are not challenged for authentication by Lync Server.</span></span>

  - <span data-ttu-id="9c11c-108">Lync Server 不会对 SIP 事务、连接或传出的 Internet 协议（VoIP）呼叫限制受信任的应用程序。</span><span class="sxs-lookup"><span data-stu-id="9c11c-108">Trusted applications are not throttled by Lync Server for SIP transactions, connections or outgoing Voice over Internet Protocol (VoIP) calls.</span></span>

  - <span data-ttu-id="9c11c-109">受信任应用程序可模拟任何用户，并能在不出现在名单中的情况下参加会议。</span><span class="sxs-lookup"><span data-stu-id="9c11c-109">Trusted applications can impersonate any user and can join conferences without appearing in rosters.</span></span>

  - <span data-ttu-id="9c11c-110">受信任应用程序具有高可用性和恢复能力。</span><span class="sxs-lookup"><span data-stu-id="9c11c-110">Trusted applications are highly available and resilient.</span></span>

<span data-ttu-id="9c11c-111">在 Lync Server 控制面板中，可以看到应用程序的名称、运行的池以及它们所使用的端口。</span><span class="sxs-lookup"><span data-stu-id="9c11c-111">In Lync Server Control Panel, you can see the name of the applications, the pool where they run, and the port they use.</span></span>

<div>

## <a name="to-view-a-list-of-trusted-applications"></a><span data-ttu-id="9c11c-112">查看受信任应用程序列表</span><span class="sxs-lookup"><span data-stu-id="9c11c-112">To view a list of trusted applications</span></span>

1.  <span data-ttu-id="9c11c-113">从分配给 CsServerAdministrator、CsAdministrator、CsHelpDesk 或 CsViewOnlyAdministrator 角色的用户帐户中，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="9c11c-113">From a user account that is assigned to the CsServerAdministrator, CsAdministrator, CsHelpDesk, or CsViewOnlyAdministrator role, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="9c11c-114">有关 Lync Server 2013 中提供的预定义管理角色的详细信息，请参阅[在 Lync server 2013 中规划基于角色的访问控制](lync-server-2013-planning-for-role-based-access-control.md)。</span><span class="sxs-lookup"><span data-stu-id="9c11c-114">For details about the predefined administrative roles available in Lync Server 2013, see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md).</span></span>

2.  <span data-ttu-id="9c11c-115">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="9c11c-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="9c11c-116">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="9c11c-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="9c11c-117">在左侧导航栏中，单击“拓扑”\*\*\*\*，然后单击“受信任应用程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9c11c-117">In the left navigation bar, click **Topology** and the click **Trusted Application**.</span></span>

4.  <span data-ttu-id="9c11c-118">在“受信任应用程序”\*\*\*\* 页上，单击某个列标题对应用程序进行排序（如果需要）。</span><span class="sxs-lookup"><span data-stu-id="9c11c-118">On the **Trusted Application** page, click a column heading to sort the applications, if needed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9c11c-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9c11c-119">See Also</span></span>


[<span data-ttu-id="9c11c-120">管理 Lync Server 2013 拓扑</span><span class="sxs-lookup"><span data-stu-id="9c11c-120">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

