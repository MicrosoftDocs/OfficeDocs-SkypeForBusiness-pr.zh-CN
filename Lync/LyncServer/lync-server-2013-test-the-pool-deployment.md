---
title: Lync Server 2013：测试池部署
description: Lync Server 2013：测试池部署。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test the pool deployment
ms:assetid: ffd80617-155a-4041-bbeb-74503e7938dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413092(v=OCS.15)
ms:contentKeyID: 48185976
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 28101a252eda5048ded9f1eaf76c092c5cb7f986
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576038"
---
# <a name="test-the-pool-deployment-in-lync-server-2013"></a><span data-ttu-id="02f45-103">在 Lync Server 2013 中测试池部署</span><span class="sxs-lookup"><span data-stu-id="02f45-103">Test the pool deployment in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="02f45-104">_**上次修改的主题：** 2013-09-25_</span><span class="sxs-lookup"><span data-stu-id="02f45-104">_**Topic Last Modified:** 2013-09-25_</span></span>

<span data-ttu-id="02f45-105">以下过程介绍如何测试前端池的部署。</span><span class="sxs-lookup"><span data-stu-id="02f45-105">The following procedure describes how to test the deployment of the Front End pool.</span></span>

<div>

## <a name="to-test-the-pool-deployment"></a><span data-ttu-id="02f45-106">测试池部署</span><span class="sxs-lookup"><span data-stu-id="02f45-106">To test the pool deployment</span></span>

1.  <span data-ttu-id="02f45-107">使用 Active Directory 计算机和用户将 lync Server 2013 控制面板上安装的 lync server 2013 部署 (的 "管理员" 角色的 Active Directory 用户对象添加) 到 **CSAdministrator** 组中。</span><span class="sxs-lookup"><span data-stu-id="02f45-107">Use Active Directory Computers and Users to add the Active Directory user object of the administrator role for the Lync Server 2013 deployment (on which Lync Server 2013 Control Panel is installed) to the **CSAdministrator** group.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="02f45-108">如果不将相应的用户和组添加到 CsAdministors 组，则在打开 Lync Server 控制面板时将收到错误，这表明 "未授权：由于基于角色的访问控制 (RBAC) 授权失败而拒绝访问。"</span><span class="sxs-lookup"><span data-stu-id="02f45-108">If you do not add the appropriate users and groups to the CsAdministors group, you will receive an error when opening Lync Server Control Panel, which states that “Unauthorized: Access is denied due to a role-based access control (RBAC) authorization failure.”</span></span>

    
    </div>

2.  <span data-ttu-id="02f45-109">如果用户对象当前已登录，则注销后重新登录，以注册新的组分配。</span><span class="sxs-lookup"><span data-stu-id="02f45-109">If the user object is currently logged on, log off and then log on again to register the new group assignment.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="02f45-110">用户帐户不能是运行 Lync Server 2013 的任何服务器的本地管理员。</span><span class="sxs-lookup"><span data-stu-id="02f45-110">The user account cannot be the local administrator of any server running Lync Server 2013.</span></span>

    
    </div>

3.  <span data-ttu-id="02f45-111">使用管理帐户登录到安装了 Lync Server 控制面板的计算机。</span><span class="sxs-lookup"><span data-stu-id="02f45-111">Use the administrative account to log on to the computer where Lync Server Control Panel is installed.</span></span>

4.  <span data-ttu-id="02f45-112">启动 Lync Server 控制面板，然后提供凭据（如果出现提示）。</span><span class="sxs-lookup"><span data-stu-id="02f45-112">Start Lync Server Control Panel, and then provide credentials, if prompted.</span></span> <span data-ttu-id="02f45-113">Lync Server "控制面板" 显示部署信息。</span><span class="sxs-lookup"><span data-stu-id="02f45-113">Lync Server Control Panel displays deployment information.</span></span>

5.  <span data-ttu-id="02f45-114">在左侧导航栏中，单击 " **拓扑**"，然后确认服务状态显示计算机带有绿色箭头，并且复制状态的绿色复选标记位于已部署并联机的每个 Lync server 服务器角色的旁边。</span><span class="sxs-lookup"><span data-stu-id="02f45-114">In the left navigation bar, click **Topology**, and then confirm that the service status shows a computer with a green arrow and that a green check mark for replication status is next to each Lync Server server role that has been deployed and brought online.</span></span>

6.  <span data-ttu-id="02f45-115">在左侧导航栏中，单击 " **用户**"，然后单击 " **启用用户**"。</span><span class="sxs-lookup"><span data-stu-id="02f45-115">In the left navigation bar, click **Users**, and then click **Enable users**.</span></span>

7.  <span data-ttu-id="02f45-116">在 " **新建 Lync Server 用户** " 页上，单击 " **添加**"。</span><span class="sxs-lookup"><span data-stu-id="02f45-116">On the **New Lync Server User** page, click **Add**.</span></span>

8.  <span data-ttu-id="02f45-117">若要定义要查找的对象的搜索参数，请在 " **从 Active Directory 中选择** " 页面上，选择 " **搜索**"，然后选择 " **添加筛选器**"。</span><span class="sxs-lookup"><span data-stu-id="02f45-117">To define search parameters for the objects you want to find, on the **Select from Active Directory** page, you can select **Search**, and then optionally click **Add Filter**.</span></span> <span data-ttu-id="02f45-118">您还可以选择 " **ldap 搜索** " 并输入 ldap 表达式以筛选或限制将返回的对象。</span><span class="sxs-lookup"><span data-stu-id="02f45-118">You can also select **LDAP search** and enter an LDAP expression to filter or limit the objects that will be returned.</span></span> <span data-ttu-id="02f45-119">在确定了搜索选项之后，clink **Find**。</span><span class="sxs-lookup"><span data-stu-id="02f45-119">After you have decided on your Search options, clink **Find**.</span></span>

9.  <span data-ttu-id="02f45-120">在 "搜索结果" 窗格中，选择此搜索会话的所有对象，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="02f45-120">In the Search results pane, select all the objects for this search session, and then click **OK**.</span></span>

10. <span data-ttu-id="02f45-121">在 " **新建 Lync Server 用户** " 页上，所选的一个或一些对象将显示在 **用户** 的显示中。</span><span class="sxs-lookup"><span data-stu-id="02f45-121">On the **New Lync Server User** page, the object or objects you selected are in the **Users** display.</span></span> <span data-ttu-id="02f45-122">在 " **将用户分配给池** " 列表中，选择对象应驻留在其中的服务器。</span><span class="sxs-lookup"><span data-stu-id="02f45-122">In the **Assign users to a pool** list, select the server where the objects should be homed.</span></span>
    
    <span data-ttu-id="02f45-123">以下是用于配置对象的多种选项。</span><span class="sxs-lookup"><span data-stu-id="02f45-123">Following are a number of options for configuring the objects.</span></span>
    
      - <span data-ttu-id="02f45-124">**生成用户的 SIP URI**</span><span class="sxs-lookup"><span data-stu-id="02f45-124">**Generate user’s SIP URI**</span></span>
    
      - <span data-ttu-id="02f45-125">**电话**</span><span class="sxs-lookup"><span data-stu-id="02f45-125">**Telephony**</span></span>
    
      - <span data-ttu-id="02f45-126">**行 URI**</span><span class="sxs-lookup"><span data-stu-id="02f45-126">**Line URI**</span></span>
    
      - <span data-ttu-id="02f45-127">**会议策略**</span><span class="sxs-lookup"><span data-stu-id="02f45-127">**Conferencing policy**</span></span>
    
      - <span data-ttu-id="02f45-128">**客户端版本策略**</span><span class="sxs-lookup"><span data-stu-id="02f45-128">**Client version policy**</span></span>
    
      - <span data-ttu-id="02f45-129">**PIN 策略**</span><span class="sxs-lookup"><span data-stu-id="02f45-129">**PIN policy**</span></span>
    
      - <span data-ttu-id="02f45-130">**外部访问策略**</span><span class="sxs-lookup"><span data-stu-id="02f45-130">**External access policy**</span></span>
    
      - <span data-ttu-id="02f45-131">**存档策略**</span><span class="sxs-lookup"><span data-stu-id="02f45-131">**Archiving policy**</span></span>
    
      - <span data-ttu-id="02f45-132">**位置策略**</span><span class="sxs-lookup"><span data-stu-id="02f45-132">**Location policy**</span></span>
    
      - <span data-ttu-id="02f45-133">**客户端策略**</span><span class="sxs-lookup"><span data-stu-id="02f45-133">**Client policy**</span></span>
    
    <span data-ttu-id="02f45-134">出于测试基本功能的目的，请选择 " **生成用户的 SIP URI** " 设置所需的选项 (配置中的其他选项将使用默认设置) ，然后单击 " **启用**"。</span><span class="sxs-lookup"><span data-stu-id="02f45-134">For the purposes of testing the basic functionality, select the option you prefer for the **Generate user’s SIP URI** setting (the other options in the configuration will use default settings), and then click **Enable**.</span></span>

11. <span data-ttu-id="02f45-135">将显示一个摘要页，其中显示 " **已启用** " 列中的复选标记，指示这些对象现在可以使用。</span><span class="sxs-lookup"><span data-stu-id="02f45-135">A summary page is displayed that shows a check mark in the **Enabled** column to indicate that the objects are now ready for use.</span></span> <span data-ttu-id="02f45-136">" **SIP 地址** " 列显示用户登录配置所需的地址。</span><span class="sxs-lookup"><span data-stu-id="02f45-136">The **SIP address** column displays the address you need for the user sign-in configuration.</span></span>

12. <span data-ttu-id="02f45-137">将一个用户登录到加入域的计算机，另一个用户登录到域中的另一台计算机上。</span><span class="sxs-lookup"><span data-stu-id="02f45-137">Log one user on to a computer that is joined to the domain, and another user on to another computer in the domain.</span></span>

13. <span data-ttu-id="02f45-138">在两台客户端计算机上安装 Lync 2013，然后验证这两个用户是否都可以登录 Lync Server 2013 并可以向对方发送即时消息。</span><span class="sxs-lookup"><span data-stu-id="02f45-138">Install Lync 2013 on each of the two client computers, and then verify that both users can sign in to Lync Server 2013 and can send instant messages to each other.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="02f45-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="02f45-139">See Also</span></span>


[<span data-ttu-id="02f45-140">在 Lync Server 2013 中部署客户端和设备</span><span class="sxs-lookup"><span data-stu-id="02f45-140">Deploying clients and devices in Lync Server 2013</span></span>](lync-server-2013-deploying-clients-and-devices.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

