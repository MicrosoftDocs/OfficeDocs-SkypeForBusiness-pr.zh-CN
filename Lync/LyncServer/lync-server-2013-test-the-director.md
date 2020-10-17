---
title: Lync Server 2013：测试控制器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test the Director
ms:assetid: 9627a7e2-28cc-429c-b79b-7c7a27573bb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398767(v=OCS.15)
ms:contentKeyID: 48184856
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ae7f2945cd3a21ea93969e098110fadec710cb98
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519089"
---
# <a name="test-the-director-in-lync-server-2013"></a><span data-ttu-id="68a4c-102">在 Lync Server 2013 中测试控制器</span><span class="sxs-lookup"><span data-stu-id="68a4c-102">Test the Director in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="68a4c-103">_**上次修改的主题：** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="68a4c-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="68a4c-104">在此阶段，您配置了控制器或控制器池，但域名系统 (DNS) SRV 条目仍指向客户端使用池或 Standard Edition 服务器登录。</span><span class="sxs-lookup"><span data-stu-id="68a4c-104">At this stage, you have a Director or Director pool configured, but your Domain Name System (DNS) SRV entries still point clients to log on by using a pool or Standard Edition server.</span></span> <span data-ttu-id="68a4c-105">在将 DNS 记录更改为使 Lync 2013 客户端通过使用控制器自动登录之前，请通过将客户端手动指向控制器来测试该客户端。</span><span class="sxs-lookup"><span data-stu-id="68a4c-105">Before changing the DNS record to make Lync 2013 clients log on automatically by using the Director, test a client by manually pointing it to the Director.</span></span>

<div>

## <a name="to-test-the-deployment"></a><span data-ttu-id="68a4c-106">测试部署</span><span class="sxs-lookup"><span data-stu-id="68a4c-106">To test the deployment</span></span>

1.  <span data-ttu-id="68a4c-107">使用属于 **CSAdministrator** 组的域帐户登录到已安装 Lync Server 控制面板的计算机上。</span><span class="sxs-lookup"><span data-stu-id="68a4c-107">Log on to the computer on which you have the Lync Server Control Panel installed with a domain account that is part of the **CSAdministrator** group.</span></span>

2.  <span data-ttu-id="68a4c-108">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="68a4c-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="68a4c-109">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="68a4c-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="68a4c-110">在导航窗格中，单击 " **拓扑**"，然后在 " **状态** " 列中确认是否存在带有箭头的绿色服务器 (即控制器或控制器池的 ![带有绿色箭头的服务器图标](images/Gg398767.2263cdb7-7e60-457a-a528-a3a082bd051b(OCS.15).jpg "带有绿色箭头的服务器图标")) 。</span><span class="sxs-lookup"><span data-stu-id="68a4c-110">In the navigation pane, click **Topology**, and in the **Status** column confirm that there is a green server with an arrow (that is, ![Server icon with green arrow](images/Gg398767.2263cdb7-7e60-457a-a528-a3a082bd051b(OCS.15).jpg "Server icon with green arrow")) for your Director or Director pool.</span></span>

4.  <span data-ttu-id="68a4c-111">将安装了 Lync Server 2013 客户端的两台客户端计算机连接，并使用为 Lync Server 2013 启用的不同用户帐户登录到每台计算机。</span><span class="sxs-lookup"><span data-stu-id="68a4c-111">Connect two client computers that have the Lync Server 2013 client installed and log on with a different user account enabled for Lync Server 2013 to each computer.</span></span>

5.  <span data-ttu-id="68a4c-112">在其中一台客户端计算机上，单击 " **选项** " 菜单，选择 " **个人** 设置" 组，单击 " **高级**"，单击 " **手动配置**"，然后将 **内部服务器名称或 IP 地址** 设置为新控制器或控制器池 (FQDN) 的完全限定的域名称。</span><span class="sxs-lookup"><span data-stu-id="68a4c-112">On one of the client computers, click the **Options** menu, select the **Personal** settings group, click **Advanced**, click **Manual Configuration**, and then set the **Internal Server name or IP address** to the fully qualified domain name (FQDN) of the new Director or Director pool.</span></span>

6.  <span data-ttu-id="68a4c-113">登录到这两个客户端，并验证使用控制器登录的客户端是否能够成功登录、查看其他用户的状态以及他们是否可以 exchange 即时消息。</span><span class="sxs-lookup"><span data-stu-id="68a4c-113">Log on to both clients and verify that the client logging on by using the Director is able to log on successfully, see the presence status of the other user, and that they can exchange instant messages.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

