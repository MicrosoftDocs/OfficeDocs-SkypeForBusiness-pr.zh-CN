---
title: Lync Server 2013：将 Microsoft SIP 处理语言（MSPL）应用程序标记为关键或非关键应用程序
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mark a Microsoft SIP Processing Language (MSPL) application as critical or not critical
ms:assetid: df68fdc6-b7e6-4f07-acdc-0cd4c2c888a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182598(v=OCS.15)
ms:contentKeyID: 48185622
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 54d8b0858145930e0a2144ade55934b39394dcaf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757946"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical-in-lync-server-2013"></a><span data-ttu-id="cc92b-102">在 Lync Server 2013 中将 Microsoft SIP 处理语言（MSPL）应用程序标记为关键或非关键应用程序</span><span class="sxs-lookup"><span data-stu-id="cc92b-102">Mark a Microsoft SIP Processing Language (MSPL) application as critical or not critical in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cc92b-103">_**主题上次修改时间：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="cc92b-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="cc92b-104">Microsoft SIP 处理语言（MSPL）服务器应用程序是仅限脚本的应用程序，使用 MSPL 脚本语言而不是 Microsoft Lync 2010 API。</span><span class="sxs-lookup"><span data-stu-id="cc92b-104">Microsoft SIP Processing Language (MSPL) server applications are script-only applications that use the MSPL scripting language instead of the Microsoft Lync 2010 API.</span></span> <span data-ttu-id="cc92b-105">某些 MSPL 服务器应用程序被指定为关键。</span><span class="sxs-lookup"><span data-stu-id="cc92b-105">Some MSPL server applications are specified as critical.</span></span> <span data-ttu-id="cc92b-106">如果脚本非常重要，则必须在系统启动期间启动脚本，才能启动 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="cc92b-106">If a script is critical, the script must start during system startup in order for Lync Server 2013 to start.</span></span> <span data-ttu-id="cc92b-107">如果脚本在 Lync Server 运行时失败，则服务器不会关闭，但会停止向脚本发送流量，并且会在事件日志中写入错误。</span><span class="sxs-lookup"><span data-stu-id="cc92b-107">If the script fails while Lync Server is running, the server does not shut down, but it stops sending traffic to the script, and it writes errors in the event log.</span></span>

<span data-ttu-id="cc92b-108">你可以使用 Lync Server "控制面板" 将 Microsoft SIP 处理语言（MSPL）服务器应用程序标记为关键或取消标记。</span><span class="sxs-lookup"><span data-stu-id="cc92b-108">You can use Lync Server Control Panel to mark Microsoft SIP Processing Language (MSPL) server applications as critical or unmark them.</span></span>

<span data-ttu-id="cc92b-109">并非所有脚本都支持此选项。</span><span class="sxs-lookup"><span data-stu-id="cc92b-109">Not all scripts support this option.</span></span> <span data-ttu-id="cc92b-110">例如，DefaultRouting 脚本标记为关键，不能为 DefaultRouting 更改此选项。</span><span class="sxs-lookup"><span data-stu-id="cc92b-110">For example, the DefaultRouting script is marked as critical, and this option cannot be changed for DefaultRouting.</span></span>

<div>

## <a name="to-mark-or-unmark-an-mspl-server-application-as-critical"></a><span data-ttu-id="cc92b-111">将 MSPL 服务器应用程序标记或取消标记为关键</span><span class="sxs-lookup"><span data-stu-id="cc92b-111">To mark or unmark an MSPL server application as critical</span></span>

1.  <span data-ttu-id="cc92b-112">从 RTCUniversalServerAdmins 组的成员（或具有等效用户权限）或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户，登录到你在其中部署 Lync Server 2013 的网络中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="cc92b-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="cc92b-113">打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="cc92b-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="cc92b-114">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="cc92b-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="cc92b-115">在左侧导航栏中，单击 "**拓扑**"，然后单击 "**服务器应用程序**"。</span><span class="sxs-lookup"><span data-stu-id="cc92b-115">In the left navigation bar, click **Topology** and then click **Server Application**.</span></span>

4.  <span data-ttu-id="cc92b-116">在 "**服务器应用程序**" 页面上，单击列标题以对应用程序进行排序，然后单击要修改的服务器应用程序。</span><span class="sxs-lookup"><span data-stu-id="cc92b-116">On the **Server Application** page, click a column heading to sort the applications, if needed, and then click the server application that you want to modify.</span></span>

5.  <span data-ttu-id="cc92b-117">单击 "**操作**"。</span><span class="sxs-lookup"><span data-stu-id="cc92b-117">Click **Action**.</span></span>

6.  <span data-ttu-id="cc92b-118">单击 "**标记为关键**" 或 "**取消选择为关键**" （即，如果脚本支持此选项）。</span><span class="sxs-lookup"><span data-stu-id="cc92b-118">Click **Mark as critical** or **Unselect as critical** (that is, if the script supports this option).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="cc92b-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cc92b-119">See Also</span></span>


[<span data-ttu-id="cc92b-120">在 Lync Server 2013 中启用或禁用 Microsoft SIP 处理语言（MSPL）服务器应用程序</span><span class="sxs-lookup"><span data-stu-id="cc92b-120">Enable or disable a Microsoft SIP Processing Language (MSPL) server application in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application.md)  


[<span data-ttu-id="cc92b-121">在 Lync Server 2013 中查看 Microsoft SIP 处理语言 (MSPL) 服务器应用程序</span><span class="sxs-lookup"><span data-stu-id="cc92b-121">View Microsoft SIP Processing Language (MSPL) server applications in Lync Server 2013</span></span>](lync-server-2013-view-microsoft-sip-processing-language-mspl-server-applications.md)  


[<span data-ttu-id="cc92b-122">管理 Lync Server 2013 拓扑</span><span class="sxs-lookup"><span data-stu-id="cc92b-122">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

