---
title: Lync Server 2013：附录 B：管理 Survivable 分支设备
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Appendix B: Managing a Survivable Branch Appliance'
ms:assetid: 2ec9d505-6d39-491c-9524-8cf36866b855
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425797(v=OCS.15)
ms:contentKeyID: 48183773
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: df6e2dc473da81177dacb8d53ee673c9a5457c98
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147175"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="appendix-b-managing-a-survivable-branch-appliance-in-lync-server-2013"></a><span data-ttu-id="f2688-102">附录 B：在 Lync Server 2013 中管理 Survivable 分支设备</span><span class="sxs-lookup"><span data-stu-id="f2688-102">Appendix B: Managing a Survivable Branch Appliance in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f2688-103">_**上次修改的主题：** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="f2688-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="f2688-104">本主题介绍管理 Survivable 分支设备的过程。</span><span class="sxs-lookup"><span data-stu-id="f2688-104">This topic describes the procedures for managing a Survivable Branch Appliance.</span></span> <span data-ttu-id="f2688-105">具体而言，如何替换和重命名 Survivable 分支设备，以及如何更改与 Survivable 分支设备关联的 Lync Server 2013 前端池。</span><span class="sxs-lookup"><span data-stu-id="f2688-105">Specifically, how to replace and rename a Survivable Branch Appliance, and how to change the Lync Server 2013 Front End pool that the Survivable Branch Appliance is associated with.</span></span>

<div>

## <a name="to-replace-a-survivable-branch-appliance"></a><span data-ttu-id="f2688-106">替换 Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="f2688-106">To Replace a Survivable Branch Appliance</span></span>

1.  <span data-ttu-id="f2688-107">在 Survivable 分支设备上停止所有 Lync Server 2013 服务。</span><span class="sxs-lookup"><span data-stu-id="f2688-107">Stop all Lync Server 2013 services on the Survivable Branch Appliance.</span></span> <span data-ttu-id="f2688-108">（请参阅 Survivable 分支设备供应商文档。）</span><span class="sxs-lookup"><span data-stu-id="f2688-108">(See the Survivable Branch Appliance vendor documentation.)</span></span>

2.  <span data-ttu-id="f2688-109">适合从域中删除 Survivable 分支设备。</span><span class="sxs-lookup"><span data-stu-id="f2688-109">(Recommended) Remove the Survivable Branch Appliance from the domain.</span></span>

3.  <span data-ttu-id="f2688-110">按照以下步骤在 Active Directory 域服务中删除 Survivable 分支装置计算机对象：</span><span class="sxs-lookup"><span data-stu-id="f2688-110">Delete the Survivable Branch Appliance computer object in Active Directory Domain Services, by following these steps:</span></span>
    
      - <span data-ttu-id="f2688-111">以 Enterprise Admins 组成员的身份登录到成员服务器。</span><span class="sxs-lookup"><span data-stu-id="f2688-111">Log on to a member server as a member of the Enterprise Admins group.</span></span>
    
      - <span data-ttu-id="f2688-112">依次单击"开始"、"管理工具"和"Active Directory 用户和计算机"。</span><span class="sxs-lookup"><span data-stu-id="f2688-112">Click **Start**, click **Administrative Tools**, and then click **Active Directory Users and Computers**.</span></span>
    
      - <span data-ttu-id="f2688-113">右键单击 "Survivable 分支装置" 对象，然后单击 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="f2688-113">Right-click the Survivable Branch Appliance object, and click **Delete**.</span></span>

4.  <span data-ttu-id="f2688-114">再次添加 Survivable 分支装置计算机对象。</span><span class="sxs-lookup"><span data-stu-id="f2688-114">Add the Survivable Branch Appliance computer object again.</span></span> <span data-ttu-id="f2688-115">（请参阅[在 Lync Server 2013 中的 Active Directory 中添加 Survivable 分支设备](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md)。）</span><span class="sxs-lookup"><span data-stu-id="f2688-115">(See [Add a Survivable Branch Appliance to Active Directory in Lync Server 2013](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md).)</span></span>

5.  <span data-ttu-id="f2688-116">等待 Active Directory 复制发生。</span><span class="sxs-lookup"><span data-stu-id="f2688-116">Wait for Active Directory replication to take place.</span></span>

6.  <span data-ttu-id="f2688-117">打开 Lync Server 命令行管理程序，并键入**Enable-enable-cstopology**。</span><span class="sxs-lookup"><span data-stu-id="f2688-117">Open the Lync Server Management Shell, and type **Enable-CSTopology**.</span></span>

7.  <span data-ttu-id="f2688-118">将新的 Survivable 分支设备连接到网络，并按照[使用 Lync server 2013 部署 Survivable 分支设备或服务器中的步骤-中心站点任务](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md)和[部署具有 lync Server 2013 的 Survivable 分支设备或服务器-分支站点任务](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)。</span><span class="sxs-lookup"><span data-stu-id="f2688-118">Connect the new Survivable Branch Appliance to the network, and follow the steps in [Deploying a Survivable Branch Appliance or Server with Lync Server 2013 - central site tasks](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) and [Deploy a Survivable Branch Appliance or Server with Lync Server 2013 - branch site task](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md).</span></span>

</div>

<div>

## <a name="to-rename-a-survivable-branch-appliance"></a><span data-ttu-id="f2688-119">重命名 Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="f2688-119">To Rename a Survivable Branch Appliance</span></span>

1.  <span data-ttu-id="f2688-120">将用户移至中央站点。</span><span class="sxs-lookup"><span data-stu-id="f2688-120">Move users to the central site.</span></span> <span data-ttu-id="f2688-121">有关详细信息，请参阅[在 Lync Server 2013 中将用户移动到另一个池](lync-server-2013-move-users-to-another-pool.md)。</span><span class="sxs-lookup"><span data-stu-id="f2688-121">For details, see [Move users to another pool in Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).</span></span>

2.  <span data-ttu-id="f2688-122">在 Survivable 分支设备上停止所有 Lync Server 2013 服务。</span><span class="sxs-lookup"><span data-stu-id="f2688-122">Stop all Lync Server 2013 services on the Survivable Branch Appliance.</span></span> <span data-ttu-id="f2688-123">（请参阅 Survivable 分支设备供应商文档。）</span><span class="sxs-lookup"><span data-stu-id="f2688-123">(See the Survivable Branch Appliance vendor documentation.)</span></span>

3.  <span data-ttu-id="f2688-124">按照以下步骤操作，从拓扑中删除 Survivable 分支设备：</span><span class="sxs-lookup"><span data-stu-id="f2688-124">Remove the Survivable Branch Appliance from the topology, by following these steps:</span></span>
    
      - <span data-ttu-id="f2688-125">依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server”\*\*\*\*，然后单击“Lync Server 拓扑生成器”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f2688-125">Click **Start**, click **All Programs**, click **Microsoft Lync Server**, and then click **Lync Server Topology Builder**.</span></span>
    
      - <span data-ttu-id="f2688-126">在控制台树中，展开 "**分支站点**"，单击 "Survivable" 分支设备，然后在操作窗格上单击 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="f2688-126">In the console tree, expand **Branch Sites**, click the Survivable Branch Appliance, and then click **Delete** on the Action pane.</span></span>

4.  <span data-ttu-id="f2688-127">从域中删除 Survivable 分支设备。</span><span class="sxs-lookup"><span data-stu-id="f2688-127">Remove the Survivable Branch Appliance from the domain.</span></span>

5.  <span data-ttu-id="f2688-128">按照以下步骤操作，删除 Active Directory 中的 Survivable 分支装置计算机对象：</span><span class="sxs-lookup"><span data-stu-id="f2688-128">Delete the Survivable Branch Appliance computer object in Active Directory, by following these steps:</span></span>
    
      - <span data-ttu-id="f2688-129">以 Enterprise Admins 组成员的身份登录到域控制器。</span><span class="sxs-lookup"><span data-stu-id="f2688-129">Log on to a domain controller as a member of the Enterprise Admins group.</span></span>
    
      - <span data-ttu-id="f2688-130">依次单击“开始”\*\*\*\*、“管理工具”\*\*\*\*、“Active Directory 用户和计算机”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f2688-130">Click **Start**, click **Administrative Tools**, and then click **Active Directory Users and Computers**.</span></span>
    
      - <span data-ttu-id="f2688-131">右键单击 "Survivable 分支装置" 对象，然后单击 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="f2688-131">Right-click the Survivable Branch Appliance object, and click **Delete**.</span></span>

6.  <span data-ttu-id="f2688-132">将 Survivable 分支设备还原为出厂默认值。</span><span class="sxs-lookup"><span data-stu-id="f2688-132">Restore the Survivable Branch Appliance to factory defaults.</span></span> <span data-ttu-id="f2688-133">（请参阅 Survivable 分支设备供应商文档。）</span><span class="sxs-lookup"><span data-stu-id="f2688-133">(See the Survivable Branch Appliance vendor documentation.)</span></span>

7.  <span data-ttu-id="f2688-134">按照[使用 Lync server 2013-中心站点任务](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md)和[部署具有 lync Server 2013 的 Survivable 分支设备或服务器](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)中的步骤操作，Survivable 分支机构或服务器-分支站点任务。</span><span class="sxs-lookup"><span data-stu-id="f2688-134">Follow the steps in [Deploying a Survivable Branch Appliance or Server with Lync Server 2013 - central site tasks](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) and [Deploy a Survivable Branch Appliance or Server with Lync Server 2013 - branch site task](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md).</span></span>

8.  <span data-ttu-id="f2688-135">将用户移动到重命名的 Survivable 分支设备。</span><span class="sxs-lookup"><span data-stu-id="f2688-135">Move users to the renamed Survivable Branch Appliance.</span></span> <span data-ttu-id="f2688-136">有关详细信息，请参阅[在 Lync Server 2013 中将用户移动到另一个池](lync-server-2013-move-users-to-another-pool.md)。</span><span class="sxs-lookup"><span data-stu-id="f2688-136">For details, see [Move users to another pool in Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).</span></span>

</div>

<div>

## <a name="to-change-the-lync-server-front-end-pool-that-the-survivable-branch-appliance-is-associated-with"></a><span data-ttu-id="f2688-137">更改与 Survivable 分支设备关联的 Lync Server 前端池</span><span class="sxs-lookup"><span data-stu-id="f2688-137">To Change the Lync Server Front End Pool that the Survivable Branch Appliance Is Associated With</span></span>

1.  <span data-ttu-id="f2688-138">将用户从 Survivable 分支设备移动到中央站点上的 Lync Server 前端池。</span><span class="sxs-lookup"><span data-stu-id="f2688-138">Move users from the Survivable Branch Appliance to the Lync Server Front End pool at the central site.</span></span> <span data-ttu-id="f2688-139">有关详细信息，请参阅[在 Lync Server 2013 中将用户移动到另一个池](lync-server-2013-move-users-to-another-pool.md)。</span><span class="sxs-lookup"><span data-stu-id="f2688-139">For details, see [Move users to another pool in Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).</span></span>

2.  <span data-ttu-id="f2688-140">停止 Survivable 分支设备上的所有 Lync Server 服务。</span><span class="sxs-lookup"><span data-stu-id="f2688-140">Stop all Lync Server services on the Survivable Branch Appliance.</span></span> <span data-ttu-id="f2688-141">（请参阅 Survivable 分支设备供应商文档）。</span><span class="sxs-lookup"><span data-stu-id="f2688-141">(See the Survivable Branch Appliance vendor documentation).</span></span>

3.  <span data-ttu-id="f2688-142">若要更新与 Survivable 分支设备关联的 Lync Server 前端池，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="f2688-142">Update the Lync Server Front End pool that the Survivable Branch Appliance is associated with, by following these steps:</span></span>
    
      - <span data-ttu-id="f2688-143">依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server”\*\*\*\*，然后单击“Lync Server 拓扑生成器”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f2688-143">Click **Start**, click **All Programs**, click **Microsoft Lync Server**, and then click **Lync Server Topology Builder**.</span></span>
    
      - <span data-ttu-id="f2688-144">展开 "**分支站点**"。</span><span class="sxs-lookup"><span data-stu-id="f2688-144">Expand **Branch Sites**.</span></span>
    
      - <span data-ttu-id="f2688-145">右键单击要修改的 Survivable 分支装置对象，然后单击 "**编辑属性**"</span><span class="sxs-lookup"><span data-stu-id="f2688-145">Right-click the Survivable Branch Appliance object to modify, and click **Edit Properties**</span></span>
    
      - <span data-ttu-id="f2688-146">在 "弹性" 下，选择要与 Survivable 分支设备关联的新的前端池，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="f2688-146">Under Resiliency, select the new Front End pool the Survivable Branch Appliance is to be associated to, and then click **Next**.</span></span>
    
      - <span data-ttu-id="f2688-147">在控制台树中，右键单击新的 Survivable 分支设备，单击 "**拓扑**"，然后单击 "**发布**"。</span><span class="sxs-lookup"><span data-stu-id="f2688-147">In the console tree, right-click the new Survivable Branch Appliance, click **Topology**, and then click **Publish**.</span></span>

4.  <span data-ttu-id="f2688-148">在 Survivable 分支设备上重新启动所有 Lync Server 服务。</span><span class="sxs-lookup"><span data-stu-id="f2688-148">Restart all Lync Server Services on the Survivable Branch Appliance.</span></span>

5.  <span data-ttu-id="f2688-149">测试 Survivable 分支设备。</span><span class="sxs-lookup"><span data-stu-id="f2688-149">Test the Survivable Branch Appliance.</span></span> <span data-ttu-id="f2688-150">有关详细信息，请参阅在[Lync Server 2013 中的 Survivable 分支装置或服务器上的家庭用户](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md)。</span><span class="sxs-lookup"><span data-stu-id="f2688-150">For details, see [Home users on a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md).</span></span>

6.  <span data-ttu-id="f2688-151">将用户从中央站点的 Lync Server 前端池移动到 Survivable 分支设备。</span><span class="sxs-lookup"><span data-stu-id="f2688-151">Move users from the Lync Server Front End pool at the central site to the Survivable Branch Appliance.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

