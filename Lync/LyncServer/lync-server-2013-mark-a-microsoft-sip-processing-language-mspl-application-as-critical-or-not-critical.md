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
ms.openlocfilehash: 45f763f9afbb52247bc3571a4d17f415c344e87e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149912"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical-in-lync-server-2013"></a><span data-ttu-id="64458-102">在 Lync Server 2013 中将 Microsoft SIP 处理语言（MSPL）应用程序标记为关键或非关键</span><span class="sxs-lookup"><span data-stu-id="64458-102">Mark a Microsoft SIP Processing Language (MSPL) application as critical or not critical in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="64458-103">_**上次修改的主题：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="64458-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="64458-104">Microsoft SIP 处理语言（MSPL）服务器应用程序是仅脚本的应用程序，使用的是 MSPL 脚本编写语言，而不是 Microsoft Lync 2010 API。</span><span class="sxs-lookup"><span data-stu-id="64458-104">Microsoft SIP Processing Language (MSPL) server applications are script-only applications that use the MSPL scripting language instead of the Microsoft Lync 2010 API.</span></span> <span data-ttu-id="64458-105">某些 MSPL 服务器应用程序被指定为关键。</span><span class="sxs-lookup"><span data-stu-id="64458-105">Some MSPL server applications are specified as critical.</span></span> <span data-ttu-id="64458-106">如果脚本非常关键，则必须在系统启动过程中启动该脚本，才能启动 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="64458-106">If a script is critical, the script must start during system startup in order for Lync Server 2013 to start.</span></span> <span data-ttu-id="64458-107">如果运行 Lync Server 时脚本失败，则服务器不会关闭，但会停止向脚本发送流量，并会在事件日志中写入错误。</span><span class="sxs-lookup"><span data-stu-id="64458-107">If the script fails while Lync Server is running, the server does not shut down, but it stops sending traffic to the script, and it writes errors in the event log.</span></span>

<span data-ttu-id="64458-108">您可以使用 Lync Server 控制面板将 Microsoft SIP 处理语言（MSPL）服务器应用程序标记为关键或取消标记。</span><span class="sxs-lookup"><span data-stu-id="64458-108">You can use Lync Server Control Panel to mark Microsoft SIP Processing Language (MSPL) server applications as critical or unmark them.</span></span>

<span data-ttu-id="64458-109">并非所有脚本都支持此选项。</span><span class="sxs-lookup"><span data-stu-id="64458-109">Not all scripts support this option.</span></span> <span data-ttu-id="64458-110">例如，DefaultRouting 脚本被标记为关键，不能为 DefaultRouting 更改此选项。</span><span class="sxs-lookup"><span data-stu-id="64458-110">For example, the DefaultRouting script is marked as critical, and this option cannot be changed for DefaultRouting.</span></span>

<div>

## <a name="to-mark-or-unmark-an-mspl-server-application-as-critical"></a><span data-ttu-id="64458-111">将 MSPL 服务器应用程序标记或取消标记为关键</span><span class="sxs-lookup"><span data-stu-id="64458-111">To mark or unmark an MSPL server application as critical</span></span>

1.  <span data-ttu-id="64458-112">从作为 RTCUniversalServerAdmins 组成员的用户帐户（或具有等效的用户权限）或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户，登录到您在其中部署了 Lync Server 2013 的网络中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="64458-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="64458-113">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="64458-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="64458-114">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="64458-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="64458-115">在左侧导航栏中，单击“拓扑”\*\*\*\*，然后单击“服务器应用程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="64458-115">In the left navigation bar, click **Topology** and then click **Server Application**.</span></span>

4.  <span data-ttu-id="64458-116">在“服务器应用程序”\*\*\*\* 页上，单击某个列标题对应用程序进行排序（如果需要），然后单击要修改的服务器应用程序。</span><span class="sxs-lookup"><span data-stu-id="64458-116">On the **Server Application** page, click a column heading to sort the applications, if needed, and then click the server application that you want to modify.</span></span>

5.  <span data-ttu-id="64458-117">单击“操作”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="64458-117">Click **Action**.</span></span>

6.  <span data-ttu-id="64458-118">单击 "**标记为关键**" 或 "**取消选择为关键**" （即，如果脚本支持此选项）。</span><span class="sxs-lookup"><span data-stu-id="64458-118">Click **Mark as critical** or **Unselect as critical** (that is, if the script supports this option).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="64458-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="64458-119">See Also</span></span>


[<span data-ttu-id="64458-120">在 Lync Server 2013 中启用或禁用 Microsoft SIP 处理语言（MSPL）服务器应用程序</span><span class="sxs-lookup"><span data-stu-id="64458-120">Enable or disable a Microsoft SIP Processing Language (MSPL) server application in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application.md)  


[<span data-ttu-id="64458-121">在 Lync Server 2013 中查看 Microsoft SIP 处理语言（MSPL）服务器应用程序</span><span class="sxs-lookup"><span data-stu-id="64458-121">View Microsoft SIP Processing Language (MSPL) server applications in Lync Server 2013</span></span>](lync-server-2013-view-microsoft-sip-processing-language-mspl-server-applications.md)  


[<span data-ttu-id="64458-122">管理 Lync Server 2013 拓扑</span><span class="sxs-lookup"><span data-stu-id="64458-122">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

