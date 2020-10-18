---
title: Lync Server 2013：测试 Standard Edition server
description: Lync Server 2013：测试 Standard Edition server。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test the Standard Edition server
ms:assetid: b6ef67bb-9665-43e4-b8b3-eac8898eebf6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412890(v=OCS.15)
ms:contentKeyID: 48185220
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 35dc13fc01979cc8b293d0647a7886b7d65d7669
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576005"
---
# <a name="test-the-standard-edition-server-in-lync-server-2013"></a><span data-ttu-id="2b870-103">在 Lync Server 2013 中测试 Standard Edition 服务器</span><span class="sxs-lookup"><span data-stu-id="2b870-103">Test the Standard Edition server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2b870-104">_**上次修改的主题：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="2b870-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="2b870-105">以下过程介绍如何测试 Standard Edition server 的部署。</span><span class="sxs-lookup"><span data-stu-id="2b870-105">The following procedure describes how to test the deployment of a Standard Edition server.</span></span>

<div>

## <a name="to-test-the-deployment-of-a-standard-edition-server"></a><span data-ttu-id="2b870-106">测试 Standard Edition Server 的部署</span><span class="sxs-lookup"><span data-stu-id="2b870-106">To test the deployment of a Standard Edition Server</span></span>

1.  <span data-ttu-id="2b870-107">使用 Active Directory 计算机和用户将 lync Server 控制面板安装 (上的 "Lync server 2013 部署" 的 "管理员" 角色的 Active Directory 用户对象添加) 到 **CSAdministrator** 组。</span><span class="sxs-lookup"><span data-stu-id="2b870-107">Use Active Directory Computers and Users to add the Active Directory user object of the administrator role for the Lync Server 2013 deployment (on which Lync Server Control Panel is installed) to the **CSAdministrator** group.</span></span>

2.  <span data-ttu-id="2b870-108">如果用户对象当前已登录，则注销后重新登录，以注册新的组分配。</span><span class="sxs-lookup"><span data-stu-id="2b870-108">If the user object is currently logged on, log off and then log on again to register the new group assignment.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2b870-109">用户帐户不能是运行 Lync Server 2013 Standard Edition 的服务器的本地管理员。</span><span class="sxs-lookup"><span data-stu-id="2b870-109">The user account cannot be the local administrator of the server running Lync Server 2013, Standard Edition.</span></span> <span data-ttu-id="2b870-110">如果不将相应的用户和组添加到 CsAdministors 组，则在打开 Lync Server 2013 控制面板时，将收到错误消息，指出 "未经授权：由于基于角色的访问控制 (RBAC) 授权失败而拒绝访问。"</span><span class="sxs-lookup"><span data-stu-id="2b870-110">If you do not add the appropriate users and groups to the CsAdministors group, you will receive an error when opening Lync Server 2013 Control Panel, which states that “Unauthorized: Access is denied due to a role-based access control (RBAC) authorization failure.”</span></span>

    
    </div>

3.  <span data-ttu-id="2b870-111">使用管理帐户登录到安装了 Lync Server 控制面板的计算机。</span><span class="sxs-lookup"><span data-stu-id="2b870-111">Use the administrative account to log on to the computer where Lync Server Control Panel is installed.</span></span>

4.  <span data-ttu-id="2b870-112">如果出现提示，请启动 Lync Server 控制面板并提供凭据。</span><span class="sxs-lookup"><span data-stu-id="2b870-112">Start Lync Server Control Panel and provide credentials, if prompted.</span></span> <span data-ttu-id="2b870-113">Lync Server 2013 控制面板显示部署信息。</span><span class="sxs-lookup"><span data-stu-id="2b870-113">Lync Server 2013 Control Panel displays deployment information.</span></span>

5.  <span data-ttu-id="2b870-114">在左侧导航栏中，单击 " **拓扑**"，然后确认服务状态是否为带有绿色箭头的计算机图标，并且每个已部署并联机的 Lync server 服务器角色旁边都有一个绿色的复选标记。</span><span class="sxs-lookup"><span data-stu-id="2b870-114">In the left navigation bar, click **Topology**, and then confirm that the service status is a computer icon with a green arrow and there is a green check mark next to each Lync Server server role that has been deployed and brought online.</span></span>

6.  <span data-ttu-id="2b870-115">在左侧导航栏中，单击 " **用户**"，然后为两个用户启用 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="2b870-115">In the left navigation bar, click **Users**, and then enable the two users for Lync Server 2013.</span></span>

7.  <span data-ttu-id="2b870-116">使其中一个用户登录已加入域的计算机，另一个用户登录域中的其他计算机。</span><span class="sxs-lookup"><span data-stu-id="2b870-116">Log one user on to a computer that is joined to the domain, and the other user on to another computer in the domain.</span></span>

8.  <span data-ttu-id="2b870-117">在两台客户端计算机上安装 Lync Server 2013，然后验证这两个用户是否都可以登录 Lync Server 2013 并可以向对方发送即时消息。</span><span class="sxs-lookup"><span data-stu-id="2b870-117">Install Lync Server 2013 on each of the two client computers, and then verify that both users can sign in to Lync Server 2013 and can send instant messages to each other.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2b870-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2b870-118">See Also</span></span>


[<span data-ttu-id="2b870-119">在 Lync Server 2013 中部署客户端和设备</span><span class="sxs-lookup"><span data-stu-id="2b870-119">Deploying clients and devices in Lync Server 2013</span></span>](lync-server-2013-deploying-clients-and-devices.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

