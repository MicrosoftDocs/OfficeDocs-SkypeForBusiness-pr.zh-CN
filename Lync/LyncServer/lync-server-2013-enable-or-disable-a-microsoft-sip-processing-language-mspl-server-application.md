---
title: Lync Server 2013：启用或禁用 Microsoft SIP 处理语言（MSPL）服务器应用程序
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable a Microsoft SIP Processing Language (MSPL) server application
ms:assetid: b20af38d-224a-4459-991d-0b7eabb3ca7c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182573(v=OCS.15)
ms:contentKeyID: 48185145
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5e8aac965a375520ac46534846a65b67e6d9f92c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042569"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application-in-lync-server-2013"></a><span data-ttu-id="67e36-102">在 Lync Server 2013 中启用或禁用 Microsoft SIP 处理语言（MSPL）服务器应用程序</span><span class="sxs-lookup"><span data-stu-id="67e36-102">Enable or disable a Microsoft SIP Processing Language (MSPL) server application in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="67e36-103">_**上次修改的主题：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="67e36-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="67e36-104">您可以使用 Lync Server 控制面板启用或禁用在 Lync Server 2013 环境中运行的 Microsoft SIP 处理语言（MSPL）服务器应用程序。</span><span class="sxs-lookup"><span data-stu-id="67e36-104">You can use Lync Server Control Panel to enable or disable Microsoft SIP Processing Language (MSPL) server applications that run in your Lync Server 2013 environment.</span></span> <span data-ttu-id="67e36-105">这些应用程序是仅包含脚本的应用程序，使用脚本语言而非 Microsoft Lync 2013 Preview API。</span><span class="sxs-lookup"><span data-stu-id="67e36-105">These applications are script-only applications that use a scripting language instead of the Microsoft Lync 2013 Preview API.</span></span>

<span data-ttu-id="67e36-p102">并非所有脚本都能启用或禁用。例如，DefaultRouting 脚本为启用状态，无法为 DefaultRouting 更改此选项。</span><span class="sxs-lookup"><span data-stu-id="67e36-p102">Not all scripts can be enabled or disabled. For instance, the DefaultRouting script is enabled and this option cannot be changed for DefaultRouting.</span></span>

<div>

## <a name="to-enable-or-disable-an-mspl-server-application"></a><span data-ttu-id="67e36-108">启用或禁用 MSPL 服务器应用程序</span><span class="sxs-lookup"><span data-stu-id="67e36-108">To enable or disable an MSPL server application</span></span>

1.  <span data-ttu-id="67e36-109">从作为 RTCUniversalServerAdmins 组成员的用户帐户（或具有等效的用户权限）或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户，登录到您在其中部署了 Lync Server 2013 的网络中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="67e36-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="67e36-110">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="67e36-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="67e36-111">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="67e36-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="67e36-112">在左侧导航栏中，单击“拓扑”\*\*\*\*，然后单击“服务器应用程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="67e36-112">In the left navigation bar, click **Topology** and then click **Server Application**.</span></span>

4.  <span data-ttu-id="67e36-113">在“服务器应用程序”\*\*\*\* 页上，单击某个列标题对应用程序进行排序（如果需要），然后单击要修改的服务器应用程序。</span><span class="sxs-lookup"><span data-stu-id="67e36-113">On the **Server Application** page, click a column heading to sort the applications, if needed, and then click the server application that you want to modify.</span></span>

5.  <span data-ttu-id="67e36-114">单击“操作”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="67e36-114">Click **Action**.</span></span>

6.  <span data-ttu-id="67e36-115">单击“启用应用程序”\*\*\*\* 或“禁用应用程序”\*\*\*\*（前提是该脚本支持此选项）。</span><span class="sxs-lookup"><span data-stu-id="67e36-115">Click **Enable application** or **Disable application** (that is, if the script supports this option).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="67e36-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="67e36-116">See Also</span></span>


[<span data-ttu-id="67e36-117">在 Lync Server 2013 中将 Microsoft SIP 处理语言（MSPL）应用程序标记为关键或非关键</span><span class="sxs-lookup"><span data-stu-id="67e36-117">Mark a Microsoft SIP Processing Language (MSPL) application as critical or not critical in Lync Server 2013</span></span>](lync-server-2013-mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical.md)  


[<span data-ttu-id="67e36-118">在 Lync Server 2013 中查看 Microsoft SIP 处理语言（MSPL）服务器应用程序</span><span class="sxs-lookup"><span data-stu-id="67e36-118">View Microsoft SIP Processing Language (MSPL) server applications in Lync Server 2013</span></span>](lync-server-2013-view-microsoft-sip-processing-language-mspl-server-applications.md)  


[<span data-ttu-id="67e36-119">管理 Lync Server 2013 拓扑</span><span class="sxs-lookup"><span data-stu-id="67e36-119">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

