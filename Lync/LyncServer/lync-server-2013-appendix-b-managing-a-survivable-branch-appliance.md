---
title: Lync Server 2013：附录 B：管理 Survivable 分支设备
description: Lync Server 2013：附录 B：管理 Survivable 分支设备。
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
ms.openlocfilehash: e66d97f538ee751d7bf12b0d0f70ff3a3f5576b2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561828"
---
# <a name="appendix-b-managing-a-survivable-branch-appliance-in-lync-server-2013"></a><span data-ttu-id="7c35b-103">附录 B：在 Lync Server 2013 中管理 Survivable 分支设备</span><span class="sxs-lookup"><span data-stu-id="7c35b-103">Appendix B: Managing a Survivable Branch Appliance in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7c35b-104">_**上次修改的主题：** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="7c35b-104">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="7c35b-105">本主题介绍管理 Survivable 分支设备的过程。</span><span class="sxs-lookup"><span data-stu-id="7c35b-105">This topic describes the procedures for managing a Survivable Branch Appliance.</span></span> <span data-ttu-id="7c35b-106">具体而言，如何替换和重命名 Survivable 分支设备，以及如何更改与 Survivable 分支设备关联的 Lync Server 2013 前端池。</span><span class="sxs-lookup"><span data-stu-id="7c35b-106">Specifically, how to replace and rename a Survivable Branch Appliance, and how to change the Lync Server 2013 Front End pool that the Survivable Branch Appliance is associated with.</span></span>

<div>

## <a name="to-replace-a-survivable-branch-appliance"></a><span data-ttu-id="7c35b-107">替换 Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="7c35b-107">To Replace a Survivable Branch Appliance</span></span>

1.  <span data-ttu-id="7c35b-108">在 Survivable 分支设备上停止所有 Lync Server 2013 服务。</span><span class="sxs-lookup"><span data-stu-id="7c35b-108">Stop all Lync Server 2013 services on the Survivable Branch Appliance.</span></span> <span data-ttu-id="7c35b-109"> (参阅 Survivable 分支设备供应商文档。 ) </span><span class="sxs-lookup"><span data-stu-id="7c35b-109">(See the Survivable Branch Appliance vendor documentation.)</span></span>

2.  <span data-ttu-id="7c35b-110"> (建议) 从域中删除 Survivable 分支设备。</span><span class="sxs-lookup"><span data-stu-id="7c35b-110">(Recommended) Remove the Survivable Branch Appliance from the domain.</span></span>

3.  <span data-ttu-id="7c35b-111">按照以下步骤在 Active Directory 域服务中删除 Survivable 分支装置计算机对象：</span><span class="sxs-lookup"><span data-stu-id="7c35b-111">Delete the Survivable Branch Appliance computer object in Active Directory Domain Services, by following these steps:</span></span>
    
      - <span data-ttu-id="7c35b-112">以 Enterprise Admins 组成员的身份登录到成员服务器。</span><span class="sxs-lookup"><span data-stu-id="7c35b-112">Log on to a member server as a member of the Enterprise Admins group.</span></span>
    
      - <span data-ttu-id="7c35b-113">依次单击“开始”\*\*\*\*、“管理工具”\*\*\*\*、“Active Directory 用户和计算机”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7c35b-113">Click **Start**, click **Administrative Tools**, and then click **Active Directory Users and Computers**.</span></span>
    
      - <span data-ttu-id="7c35b-114">右键单击 "Survivable 分支装置" 对象，然后单击 " **删除**"。</span><span class="sxs-lookup"><span data-stu-id="7c35b-114">Right-click the Survivable Branch Appliance object, and click **Delete**.</span></span>

4.  <span data-ttu-id="7c35b-115">再次添加 Survivable 分支装置计算机对象。</span><span class="sxs-lookup"><span data-stu-id="7c35b-115">Add the Survivable Branch Appliance computer object again.</span></span> <span data-ttu-id="7c35b-116"> (参阅 [在 Lync Server 2013 中的 Active Directory 中添加 Survivable 分支设备](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md)。 ) </span><span class="sxs-lookup"><span data-stu-id="7c35b-116">(See [Add a Survivable Branch Appliance to Active Directory in Lync Server 2013](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md).)</span></span>

5.  <span data-ttu-id="7c35b-117">等待 Active Directory 复制发生。</span><span class="sxs-lookup"><span data-stu-id="7c35b-117">Wait for Active Directory replication to take place.</span></span>

6.  <span data-ttu-id="7c35b-118">打开 Lync Server 命令行管理程序，并键入 **Enable-enable-cstopology**。</span><span class="sxs-lookup"><span data-stu-id="7c35b-118">Open the Lync Server Management Shell, and type **Enable-CSTopology**.</span></span>

7.  <span data-ttu-id="7c35b-119">将新的 Survivable 分支设备连接到网络，并按照 [使用 Lync server 2013 部署 Survivable 分支设备或服务器中的步骤-中心站点任务](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) 和 [部署具有 lync Server 2013 的 Survivable 分支设备或服务器-分支站点任务](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)。</span><span class="sxs-lookup"><span data-stu-id="7c35b-119">Connect the new Survivable Branch Appliance to the network, and follow the steps in [Deploying a Survivable Branch Appliance or Server with Lync Server 2013 - central site tasks](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) and [Deploy a Survivable Branch Appliance or Server with Lync Server 2013 - branch site task](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md).</span></span>

</div>

<div>

## <a name="to-rename-a-survivable-branch-appliance"></a><span data-ttu-id="7c35b-120">重命名 Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="7c35b-120">To Rename a Survivable Branch Appliance</span></span>

1.  <span data-ttu-id="7c35b-121">将用户移至中央站点。</span><span class="sxs-lookup"><span data-stu-id="7c35b-121">Move users to the central site.</span></span> <span data-ttu-id="7c35b-122">有关详细信息，请参阅 [在 Lync Server 2013 中将用户移动到另一个池](lync-server-2013-move-users-to-another-pool.md)。</span><span class="sxs-lookup"><span data-stu-id="7c35b-122">For details, see [Move users to another pool in Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).</span></span>

2.  <span data-ttu-id="7c35b-123">在 Survivable 分支设备上停止所有 Lync Server 2013 服务。</span><span class="sxs-lookup"><span data-stu-id="7c35b-123">Stop all Lync Server 2013 services on the Survivable Branch Appliance.</span></span> <span data-ttu-id="7c35b-124"> (参阅 Survivable 分支设备供应商文档。 ) </span><span class="sxs-lookup"><span data-stu-id="7c35b-124">(See the Survivable Branch Appliance vendor documentation.)</span></span>

3.  <span data-ttu-id="7c35b-125">按照以下步骤操作，从拓扑中删除 Survivable 分支设备：</span><span class="sxs-lookup"><span data-stu-id="7c35b-125">Remove the Survivable Branch Appliance from the topology, by following these steps:</span></span>
    
      - <span data-ttu-id="7c35b-126">依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server”\*\*\*\*，然后单击“Lync Server 拓扑生成器”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7c35b-126">Click **Start**, click **All Programs**, click **Microsoft Lync Server**, and then click **Lync Server Topology Builder**.</span></span>
    
      - <span data-ttu-id="7c35b-127">在控制台树中，展开 " **分支站点**"，单击 "Survivable" 分支设备，然后在操作窗格上单击 " **删除** "。</span><span class="sxs-lookup"><span data-stu-id="7c35b-127">In the console tree, expand **Branch Sites**, click the Survivable Branch Appliance, and then click **Delete** on the Action pane.</span></span>

4.  <span data-ttu-id="7c35b-128">从域中删除 Survivable 分支设备。</span><span class="sxs-lookup"><span data-stu-id="7c35b-128">Remove the Survivable Branch Appliance from the domain.</span></span>

5.  <span data-ttu-id="7c35b-129">按照以下步骤操作，删除 Active Directory 中的 Survivable 分支装置计算机对象：</span><span class="sxs-lookup"><span data-stu-id="7c35b-129">Delete the Survivable Branch Appliance computer object in Active Directory, by following these steps:</span></span>
    
      - <span data-ttu-id="7c35b-130">以 Enterprise Admins 组成员的身份登录到域控制器。</span><span class="sxs-lookup"><span data-stu-id="7c35b-130">Log on to a domain controller as a member of the Enterprise Admins group.</span></span>
    
      - <span data-ttu-id="7c35b-131">依次单击“开始”\*\*\*\*、“管理工具”\*\*\*\*、“Active Directory 用户和计算机”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7c35b-131">Click **Start**, click **Administrative Tools**, and then click **Active Directory Users and Computers**.</span></span>
    
      - <span data-ttu-id="7c35b-132">右键单击 "Survivable 分支装置" 对象，然后单击 " **删除**"。</span><span class="sxs-lookup"><span data-stu-id="7c35b-132">Right-click the Survivable Branch Appliance object, and click **Delete**.</span></span>

6.  <span data-ttu-id="7c35b-133">将 Survivable 分支设备还原为出厂默认值。</span><span class="sxs-lookup"><span data-stu-id="7c35b-133">Restore the Survivable Branch Appliance to factory defaults.</span></span> <span data-ttu-id="7c35b-134"> (参阅 Survivable 分支设备供应商文档。 ) </span><span class="sxs-lookup"><span data-stu-id="7c35b-134">(See the Survivable Branch Appliance vendor documentation.)</span></span>

7.  <span data-ttu-id="7c35b-135">按照 [使用 Lync server 2013-中心站点任务](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) 和 [部署具有 lync Server 2013 的 Survivable 分支设备或服务器](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)中的步骤操作，Survivable 分支机构或服务器-分支站点任务。</span><span class="sxs-lookup"><span data-stu-id="7c35b-135">Follow the steps in [Deploying a Survivable Branch Appliance or Server with Lync Server 2013 - central site tasks](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) and [Deploy a Survivable Branch Appliance or Server with Lync Server 2013 - branch site task](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md).</span></span>

8.  <span data-ttu-id="7c35b-136">将用户移动到重命名的 Survivable 分支设备。</span><span class="sxs-lookup"><span data-stu-id="7c35b-136">Move users to the renamed Survivable Branch Appliance.</span></span> <span data-ttu-id="7c35b-137">有关详细信息，请参阅 [在 Lync Server 2013 中将用户移动到另一个池](lync-server-2013-move-users-to-another-pool.md)。</span><span class="sxs-lookup"><span data-stu-id="7c35b-137">For details, see [Move users to another pool in Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).</span></span>

</div>

<div>

## <a name="to-change-the-lync-server-front-end-pool-that-the-survivable-branch-appliance-is-associated-with"></a><span data-ttu-id="7c35b-138">更改与 Survivable 分支设备关联的 Lync Server 前端池</span><span class="sxs-lookup"><span data-stu-id="7c35b-138">To Change the Lync Server Front End Pool that the Survivable Branch Appliance Is Associated With</span></span>

1.  <span data-ttu-id="7c35b-139">将用户从 Survivable 分支设备移动到中央站点上的 Lync Server 前端池。</span><span class="sxs-lookup"><span data-stu-id="7c35b-139">Move users from the Survivable Branch Appliance to the Lync Server Front End pool at the central site.</span></span> <span data-ttu-id="7c35b-140">有关详细信息，请参阅 [在 Lync Server 2013 中将用户移动到另一个池](lync-server-2013-move-users-to-another-pool.md)。</span><span class="sxs-lookup"><span data-stu-id="7c35b-140">For details, see [Move users to another pool in Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).</span></span>

2.  <span data-ttu-id="7c35b-141">停止 Survivable 分支设备上的所有 Lync Server 服务。</span><span class="sxs-lookup"><span data-stu-id="7c35b-141">Stop all Lync Server services on the Survivable Branch Appliance.</span></span> <span data-ttu-id="7c35b-142"> (参阅 Survivable Branch 设备供应商文档) 。</span><span class="sxs-lookup"><span data-stu-id="7c35b-142">(See the Survivable Branch Appliance vendor documentation).</span></span>

3.  <span data-ttu-id="7c35b-143">若要更新与 Survivable 分支设备关联的 Lync Server 前端池，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="7c35b-143">Update the Lync Server Front End pool that the Survivable Branch Appliance is associated with, by following these steps:</span></span>
    
      - <span data-ttu-id="7c35b-144">依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server”\*\*\*\*，然后单击“Lync Server 拓扑生成器”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7c35b-144">Click **Start**, click **All Programs**, click **Microsoft Lync Server**, and then click **Lync Server Topology Builder**.</span></span>
    
      - <span data-ttu-id="7c35b-145">展开 " **分支站点**"。</span><span class="sxs-lookup"><span data-stu-id="7c35b-145">Expand **Branch Sites**.</span></span>
    
      - <span data-ttu-id="7c35b-146">右键单击要修改的 Survivable 分支装置对象，然后单击 "**编辑属性**"</span><span class="sxs-lookup"><span data-stu-id="7c35b-146">Right-click the Survivable Branch Appliance object to modify, and click **Edit Properties**</span></span>
    
      - <span data-ttu-id="7c35b-147">在 "弹性" 下，选择要与 Survivable 分支设备关联的新的前端池，然后单击 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="7c35b-147">Under Resiliency, select the new Front End pool the Survivable Branch Appliance is to be associated to, and then click **Next**.</span></span>
    
      - <span data-ttu-id="7c35b-148">在控制台树中，右键单击新的 Survivable 分支设备，单击 " **拓扑**"，然后单击 " **发布**"。</span><span class="sxs-lookup"><span data-stu-id="7c35b-148">In the console tree, right-click the new Survivable Branch Appliance, click **Topology**, and then click **Publish**.</span></span>

4.  <span data-ttu-id="7c35b-149">在 Survivable 分支设备上重新启动所有 Lync Server 服务。</span><span class="sxs-lookup"><span data-stu-id="7c35b-149">Restart all Lync Server Services on the Survivable Branch Appliance.</span></span>

5.  <span data-ttu-id="7c35b-150">测试 Survivable 分支设备。</span><span class="sxs-lookup"><span data-stu-id="7c35b-150">Test the Survivable Branch Appliance.</span></span> <span data-ttu-id="7c35b-151">有关详细信息，请参阅在 [Lync Server 2013 中的 Survivable 分支装置或服务器上的家庭用户](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md)。</span><span class="sxs-lookup"><span data-stu-id="7c35b-151">For details, see [Home users on a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md).</span></span>

6.  <span data-ttu-id="7c35b-152">将用户从中央站点的 Lync Server 前端池移动到 Survivable 分支设备。</span><span class="sxs-lookup"><span data-stu-id="7c35b-152">Move users from the Lync Server Front End pool at the central site to the Survivable Branch Appliance.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

