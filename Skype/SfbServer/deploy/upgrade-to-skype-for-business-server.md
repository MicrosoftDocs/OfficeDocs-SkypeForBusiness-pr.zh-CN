---
title: 升级到 Skype for Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 7/14/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 74ce73bc-356b-4705-83b1-341ee010fd19
description: 摘要： 了解如何从 Lync Server 2013 升级到 Skype 的业务服务器 2015年。 下载免费试用版 Skype 业务服务器 2015 从 Microsoft 评估中心，网址为： https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server。
ms.openlocfilehash: 0c869527fe9e07187149b63ed3c360b0290c8a87
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="upgrade-to-skype-for-business-server-2015"></a><span data-ttu-id="a7264-104">升级到 Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="a7264-104">Upgrade to Skype for Business Server 2015</span></span>
 
<span data-ttu-id="a7264-105">**摘要：**了解如何从 Lync Server 2013 升级到 Skype 的业务服务器 2015年。</span><span class="sxs-lookup"><span data-stu-id="a7264-105">**Summary:** Learn how to upgrade from Lync Server 2013 to Skype for Business Server 2015.</span></span> <span data-ttu-id="a7264-106">下载[Microsoft 评估中心](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)中的业务服务器 2015 Skype 的免费试用版。</span><span class="sxs-lookup"><span data-stu-id="a7264-106">Download a free trial of Skype for Business Server 2015 from the  [Microsoft Evaluation center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="a7264-107">使用本文档中的过程以从 Lync Server 2013 使用升级到 Skype 的业务服务器 2015年 Skype 业务 Server 拓扑生成器和就地升级的新功能。</span><span class="sxs-lookup"><span data-stu-id="a7264-107">Use the procedures in this document to upgrade from Lync Server 2013 to Skype for Business Server 2015 by using the Skype for Business Server Topology Builder and the new In-Place Upgrade feature.</span></span> <span data-ttu-id="a7264-108">如果您想要从 Lync Server 2010 或 Office Communications Server 2007 R2 升级，请参阅[计划升级到业务服务器 2015年的 Skype](../plan-your-deployment/upgrade.md)。</span><span class="sxs-lookup"><span data-stu-id="a7264-108">If you want to upgrade from Lync Server 2010 or Office Communications Server 2007 R2, see [Plan to upgrade to Skype for Business Server 2015](../plan-your-deployment/upgrade.md).</span></span>
  
## <a name="upgrade-from-lync-server-2013"></a><span data-ttu-id="a7264-109">从 Lync Server 2013 升级</span><span class="sxs-lookup"><span data-stu-id="a7264-109">Upgrade from Lync Server 2013</span></span>

<span data-ttu-id="a7264-110">将 Lync Server 2013 升级到 Skype，业务服务器 2015年涉及安装必备软件和使用业务 Server 拓扑生成器的 Skype 池中，数据库升级业务服务器就地升级的每个使用 Skype与池关联的服务器。</span><span class="sxs-lookup"><span data-stu-id="a7264-110">Upgrading Lync Server 2013 to Skype for Business Server 2015 involves installing prerequisite software, using the Skype for Business Server Topology Builder to upgrade databases in the pool, and using the Skype for Business Server In-Place Upgrade on each of the servers associated with the pool.</span></span> <span data-ttu-id="a7264-111">要完成升级，请执行此主题中的八个步骤。</span><span class="sxs-lookup"><span data-stu-id="a7264-111">To complete the upgrade, go through the eight steps in this topic.</span></span>
  
### <a name="before-you-begin"></a><span data-ttu-id="a7264-112">开始之前</span><span class="sxs-lookup"><span data-stu-id="a7264-112">Before you begin</span></span>

- <span data-ttu-id="a7264-113">查看[规划升级到业务服务器 2015年的 Skype](../plan-your-deployment/upgrade.md)。</span><span class="sxs-lookup"><span data-stu-id="a7264-113">Review [Plan to upgrade to Skype for Business Server 2015](../plan-your-deployment/upgrade.md).</span></span>
    
- <span data-ttu-id="a7264-114">查看[Business Server 2015 的 Skype 服务器要求](../plan-your-deployment/requirements-for-your-environment/server-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a7264-114">Review [Server requirements for Skype for Business Server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span></span>
    
- <span data-ttu-id="a7264-115">[安装必备组件的业务服务器 2015 Skype](install/install-prerequisites.md) 。</span><span class="sxs-lookup"><span data-stu-id="a7264-115">[Install prerequisites for Skype for Business Server 2015](install/install-prerequisites.md) .</span></span>
    
- <span data-ttu-id="a7264-116">[安装 Business server 2015 Skype](install/install.md) 。</span><span class="sxs-lookup"><span data-stu-id="a7264-116">[Install Skype for Business Server 2015](install/install.md) .</span></span>
    
### <a name="step-1-install-administrator-tools-and-download-topology"></a><span data-ttu-id="a7264-117">第 1 步：安装管理员工具并下载拓扑</span><span class="sxs-lookup"><span data-stu-id="a7264-117">Step 1: Install Administrator tools and download topology</span></span>

1. <span data-ttu-id="a7264-118">连接到计算机中不具有 Lync OCSCore 或安装的任何其他 Lync 组件的拓扑。</span><span class="sxs-lookup"><span data-stu-id="a7264-118">Connect to computer in the topology that does not have Lync OCSCore or any other Lync components installed.</span></span>
    
2. <span data-ttu-id="a7264-119">从业务服务器 2015年安装媒体的 Skype，从**OCS_Volume\Setup\AMD64**运行**Setup.exe** 。</span><span class="sxs-lookup"><span data-stu-id="a7264-119">From Skype for Business Server 2015 installation media, run **Setup.exe** from **OCS_Volume\Setup\AMD64**.</span></span> 
    
3. <span data-ttu-id="a7264-120">单击“**安装**”。</span><span class="sxs-lookup"><span data-stu-id="a7264-120">Click **Install**.</span></span> 
    
4. <span data-ttu-id="a7264-121">接受许可协议。</span><span class="sxs-lookup"><span data-stu-id="a7264-121">Accept the license agreement.</span></span>
    
5. <span data-ttu-id="a7264-122">在部署向导中，单击“**安装管理员工具**”，按照步骤进行安装。</span><span class="sxs-lookup"><span data-stu-id="a7264-122">On the Deployment Wizard, click **Install Administrator tools**, and follow the steps to install.</span></span>
    
     ![已调出“安装管理员工具”链接的“部署向导”屏幕截图。](../media/5bbac2d6-a5b3-42b4-a243-7bcf2b04477a.png)
  
6. <span data-ttu-id="a7264-124">在 Windows 开始屏幕中，打开业务 Server 拓扑生成器 Skype。</span><span class="sxs-lookup"><span data-stu-id="a7264-124">From the Windows Start screen, open Skype for Business Server Topology Builder.</span></span>
    
7. <span data-ttu-id="a7264-125">单击“**从现有部署下载拓扑**”，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="a7264-125">Click **Download topology from existing deployment**, and click **Next**.</span></span>
    
8. <span data-ttu-id="a7264-126">输入拓扑名称，然后单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="a7264-126">Enter a name for the topology, and click **Save**.</span></span>
    
9. <span data-ttu-id="a7264-127">转到保存拓扑的位置，创建一个拓扑副本。</span><span class="sxs-lookup"><span data-stu-id="a7264-127">Go to location where you saved the topology, and make a copy of the topology.</span></span>
    
### <a name="step-2-upgrade-and-publish-topology-using-topology-builder"></a><span data-ttu-id="a7264-128">第 2 步：使用拓扑生成器升级和发布拓扑</span><span class="sxs-lookup"><span data-stu-id="a7264-128">Step 2: Upgrade and publish topology using Topology Builder</span></span>

<span data-ttu-id="a7264-129">在开始升级过程之前，必须在计划升级的池运行所有服务。</span><span class="sxs-lookup"><span data-stu-id="a7264-129">Before you start the upgrade process, all services must be running for the pools you plan to upgrade.</span></span> <span data-ttu-id="a7264-130">这是为了保证拓扑更改复制到池中服务器的本地数据库。</span><span class="sxs-lookup"><span data-stu-id="a7264-130">This is so the topology changes will be replicated to the local database of the servers in the pool.</span></span>
  
> [!IMPORTANT]
>  <span data-ttu-id="a7264-131">在升级之前保存拓扑文件副本。</span><span class="sxs-lookup"><span data-stu-id="a7264-131">Save a copy of your topology file before you upgrade.</span></span> <span data-ttu-id="a7264-132">升级后，您将不能降级拓扑。 > 如果服务位于相同的服务器，如数据库，如持久聊天服务位于相同的服务器的持久聊天数据库，请跳过此步骤中，并转到步骤 4。</span><span class="sxs-lookup"><span data-stu-id="a7264-132">After you upgrade, you will not be able to downgrade the topology.>  If your services are on the same servers as your databases, like the Persistent Chat service is on the same server as the Persistent Chat database, skip this step, and go to step 4.</span></span> <span data-ttu-id="a7264-133">停止服务后，请在每台服务器上运行就地升级安装以升级本地数据库。</span><span class="sxs-lookup"><span data-stu-id="a7264-133">After you stop the services, run the In-Place Upgrade setup on each server to upgrade the local databases.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a7264-p107">如果拓扑有镜像的后端数据库，那么在使用拓扑生成器**发布拓扑时**，您会看到主数据库和镜像数据库同时出现。发布拓扑时，请确保所有数据库都在主数据库上运行，同时只选择主数据库，而不是镜像数据库，否则，在发布拓扑后，您会看到警告。</span><span class="sxs-lookup"><span data-stu-id="a7264-p107">If the topology has a back-end database that is mirrored then you will see both the Principal and the Mirrored databases show up **when you publish the topology** using Topology Builder. Make sure all of the databases are running on the Principal and only select the Principal, not the mirror, when publishing the topology otherwise you will see a warning after publishing the topology.</span></span>
  
<span data-ttu-id="a7264-136">选择一个选项以升级并使用 Skype 业务 Server 2015 拓扑生成器发布新拓扑。</span><span class="sxs-lookup"><span data-stu-id="a7264-136">Pick one of the options below to upgrade and publish a new topology by using the Skype for Business Server 2015 Topology Builder.</span></span> <span data-ttu-id="a7264-137">在完成这些步骤并发布更新后的拓扑之后，转到本主题中的第 3 步。</span><span class="sxs-lookup"><span data-stu-id="a7264-137">After you complete the steps and publish the updated topology, move to Step 3 in this topic.</span></span>
  
#### <a name="option-1-upgrade-an-isolated-front-end-pool-and-associated-archiving-and-monitoring-stores"></a><span data-ttu-id="a7264-138">选项 1：升级隔离的前端池和关联的存档与监控存储</span><span class="sxs-lookup"><span data-stu-id="a7264-138">Option 1: Upgrade an isolated Front End pool and associated Archiving and Monitoring stores</span></span>

<span data-ttu-id="a7264-139">如果您升级的池依赖于存档和监控存储，则在使用以下步骤时，存档和监控存储也会随之升级。</span><span class="sxs-lookup"><span data-stu-id="a7264-139">If the pool you're upgrading has an Archiving and Monitoring store dependency, when you use the following steps, the Archiving and Monitoring store will be upgraded as well.</span></span>
  
1. <span data-ttu-id="a7264-140">在拓扑生成器中，右键单击 Lync Server 2013 池，选择**升级到业务服务器 2015年的 Skype**，并按照步骤。</span><span class="sxs-lookup"><span data-stu-id="a7264-140">In Topology Builder, right-click a Lync Server 2013 pool, select **Upgrade to Skype for Business Server 2015**, and follow the steps.</span></span> 
    
     ![包含升级选项的 Lync Server 2013 右键单击菜单屏幕截图。](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
2. <span data-ttu-id="a7264-142">在拓扑生成器中，单击**操作** > **发布拓扑**或**操作** > **拓扑** > **发布**。</span><span class="sxs-lookup"><span data-stu-id="a7264-142">In Topology Builder, click **Action** > **Publish topology** or **Action** > **Topology** > **Publish**.</span></span> 
    
     ![拓扑生成器中带“发布拓扑”选项的“操作”菜单屏幕截图。](../media/d6712634-9205-401f-a0b0-3ea096ca51bf.png)
  
3. <span data-ttu-id="a7264-144">在发布期间，选择在存档和监控存储上安装数据库。</span><span class="sxs-lookup"><span data-stu-id="a7264-144">During publishing, choose to install a database on the Archiving and Monitoring store.</span></span>
    
#### <a name="option-2-upgrade-front-end-pool-without-upgrading-archiving-and-monitoring-stores"></a><span data-ttu-id="a7264-145">选项 2： 不存档和监控存储升级的升级的前端池</span><span class="sxs-lookup"><span data-stu-id="a7264-145">Option 2: Upgrade Front End pool without upgrading Archiving and Monitoring stores</span></span>

<span data-ttu-id="a7264-p109">如果您使用以下 步骤，选定池的存档和监控将被禁用。在升级之后，该池将不会有存档和监控存储。</span><span class="sxs-lookup"><span data-stu-id="a7264-p109">If you use the following steps, archiving and monitoring for the selected pool are disabled. The pool will not have Archiving and Monitoring stores after the upgrade.</span></span>
  
1. <span data-ttu-id="a7264-148">在拓扑生成器中，选择您想要升级的 Lync Server 2013 池。</span><span class="sxs-lookup"><span data-stu-id="a7264-148">In Topology Builder, select the Lync Server 2013 pool that you want to upgrade.</span></span>
    
2. <span data-ttu-id="a7264-149">删除 Lync Server 2013 存档和监控存储相关性。</span><span class="sxs-lookup"><span data-stu-id="a7264-149">Remove the dependency to the Lync Server 2013 Archiving and Monitoring stores.</span></span> 
    
   - <span data-ttu-id="a7264-150">转到**操作** > **编辑属性**。</span><span class="sxs-lookup"><span data-stu-id="a7264-150">Go to **Action** > **Edit properties**.</span></span>
    
   - <span data-ttu-id="a7264-151">清除“**存档**”复选框。</span><span class="sxs-lookup"><span data-stu-id="a7264-151">Clear the **Archiving** check box.</span></span>
    
     ![“编辑属性”对话框上的“存档”复选框的屏幕截图。](../media/9a88427e-80ee-49d0-a767-809fa9a5faf1.png)
  
   - <span data-ttu-id="a7264-153">清除“**监控**”复选框。</span><span class="sxs-lookup"><span data-stu-id="a7264-153">Clear the **Monitoring** check box.</span></span>
    
     ![显示“监控”复选框的“编辑属性”对话框的屏幕截图。](../media/880acf33-57bb-4521-8717-cf5b67261ed4.png)
  
3. <span data-ttu-id="a7264-155">右键单击 Lync Server 2013 池选择**升级到业务服务器 2015年的 Skype**，然后按照的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="a7264-155">Right-click the Lync Server 2013 pool, select **Upgrade to Skype for Business Server 2015**, and follow the steps.</span></span> 
    
     ![包含升级选项的 Lync Server 2013 右键单击菜单屏幕截图。](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
4. <span data-ttu-id="a7264-157">在拓扑生成器中，单击**操作** > **发布拓扑**或**操作** > **拓扑** > **发布**。</span><span class="sxs-lookup"><span data-stu-id="a7264-157">In Topology Builder, click **Action** > **Publish topology** or **Action** > **Topology** > **Publish**.</span></span> 
    
#### <a name="option-3-upgrade-front-end-pool-and-associated-it-to-new-skype-for-business-server-2015-archiving-and-monitoring-stores"></a><span data-ttu-id="a7264-158">选项 3： 升级前端池和关联到新的业务 Server 2015 存档和监控存储的 Skype</span><span class="sxs-lookup"><span data-stu-id="a7264-158">Option 3: Upgrade Front End pool and associated it to new Skype for Business Server 2015 Archiving and Monitoring stores</span></span>

<span data-ttu-id="a7264-159">如果使用以下步骤，存档和监控将在先前的存储中停止，并在您创建的新存储中启动。</span><span class="sxs-lookup"><span data-stu-id="a7264-159">If you use the following steps, archiving and monitoring will stop in the previous store and start in the new store you've created.</span></span> 
  
1. <span data-ttu-id="a7264-160">在拓扑生成器中，选择您想要升级的 Lync Server 2013 池。</span><span class="sxs-lookup"><span data-stu-id="a7264-160">In Topology Builder, select the Lync Server 2013 pool that you want to upgrade.</span></span> 
    
2. <span data-ttu-id="a7264-161">删除 Lync Server 2013 存档和监控存储相关性。</span><span class="sxs-lookup"><span data-stu-id="a7264-161">Remove the dependency to the Lync Server 2013 Archiving and Monitoring stores.</span></span> 
    
   - <span data-ttu-id="a7264-162">转到**操作** > **编辑属性**。</span><span class="sxs-lookup"><span data-stu-id="a7264-162">Go to **Action** > **Edit properties**.</span></span>
    
   - <span data-ttu-id="a7264-163">清除“**存档**”复选框。</span><span class="sxs-lookup"><span data-stu-id="a7264-163">Clear the **Archiving** check box.</span></span>
    
     ![“编辑属性”对话框上的“存档”复选框的屏幕截图。](../media/9a88427e-80ee-49d0-a767-809fa9a5faf1.png)
  
   - <span data-ttu-id="a7264-165">清除“**监控**”复选框。</span><span class="sxs-lookup"><span data-stu-id="a7264-165">Clear the **Monitoring** check box.</span></span>
    
     ![显示“监控”复选框的“编辑属性”对话框的屏幕截图。](../media/880acf33-57bb-4521-8717-cf5b67261ed4.png)
  
3. <span data-ttu-id="a7264-167">右键单击 Lync Server 2013 池选择**升级到业务服务器 2015年的 Skype**，然后按照的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="a7264-167">Right-click the Lync Server 2013 pool, select **Upgrade to Skype for Business Server 2015**, and follow the steps.</span></span> 
    
     ![包含升级选项的 Lync Server 2013 右键单击菜单屏幕截图。](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
4. <span data-ttu-id="a7264-169">为存档创建新的 SQL 存储。</span><span class="sxs-lookup"><span data-stu-id="a7264-169">Create a new SQL store for Archiving.</span></span> 
    
   - <span data-ttu-id="a7264-170">选择的池和**操作** > **编辑属性**。</span><span class="sxs-lookup"><span data-stu-id="a7264-170">Select the pool and **Action** > **Edit properties**.</span></span> 
    
   -  <span data-ttu-id="a7264-171">选中“**存档**”复选框。</span><span class="sxs-lookup"><span data-stu-id="a7264-171">Select the **Archiving** check box.</span></span>
    
   - <span data-ttu-id="a7264-172">单击“**新建**”。</span><span class="sxs-lookup"><span data-stu-id="a7264-172">Click **New**.</span></span>
    
     ![显示“存档”部分下的“新建”按钮的“编辑属性”对话框的屏幕截图。](../media/3a4a18e7-8251-4736-837c-2b486f64f896.png)
  
5. <span data-ttu-id="a7264-174">为监控创建新的 SQL 存储。</span><span class="sxs-lookup"><span data-stu-id="a7264-174">Create a new SQL store for Monitoring.</span></span> 
    
   - <span data-ttu-id="a7264-175">选择的池和**操作** > **编辑属性**。</span><span class="sxs-lookup"><span data-stu-id="a7264-175">Select the pool and **Action** > **Edit properties**.</span></span> 
    
   -  <span data-ttu-id="a7264-176">选中“**监控**”复选框。</span><span class="sxs-lookup"><span data-stu-id="a7264-176">Select the **Monitoring** check box.</span></span>
    
   - <span data-ttu-id="a7264-177">单击“**新建**”。</span><span class="sxs-lookup"><span data-stu-id="a7264-177">Click **New**.</span></span>
    
     ![显示“监控”部分下的“新建”按钮的“编辑属性”对话框的屏幕截图。](../media/729c72a7-0068-4e0d-99dc-e480a6bfbf1d.png)
  
6. <span data-ttu-id="a7264-179">在拓扑生成器中，单击**操作** > **发布拓扑**或**操作** > **拓扑** > **发布**。</span><span class="sxs-lookup"><span data-stu-id="a7264-179">In Topology Builder, click **Action** > **Publish topology** or **Action** > **Topology** > **Publish**.</span></span> 
    
7. <span data-ttu-id="a7264-180">在发布期间，选择在新的存档和监控存储上安装数据库。</span><span class="sxs-lookup"><span data-stu-id="a7264-180">During publishing, choose to install the database on the new Archiving and Monitoring store.</span></span>
    
### <a name="step-3-wait-for-replication"></a><span data-ttu-id="a7264-181">第 3 步：等待复制</span><span class="sxs-lookup"><span data-stu-id="a7264-181">Step 3: Wait for replication</span></span>

<span data-ttu-id="a7264-182">留些时间耐心等候复制，以便将更新后的拓扑发布到环境中的所有服务器。</span><span class="sxs-lookup"><span data-stu-id="a7264-182">Give replication some time to publish the updated topology to all the servers in the environment.</span></span>
  
### <a name="step-4-stop-all-services-in-pool-to-be-upgraded"></a><span data-ttu-id="a7264-183">第 4 步：停用池中所有需要升级的服务</span><span class="sxs-lookup"><span data-stu-id="a7264-183">Step 4: Stop all services in pool to be upgraded</span></span>

<span data-ttu-id="a7264-184">每台服务器上的服务于您打算升级，请在 PowerShell 中运行以下 cmdlet 的池：</span><span class="sxs-lookup"><span data-stu-id="a7264-184">On each server that is servicing the pool that you're going to upgrade, run the following cmdlet in PowerShell:</span></span>
  
```
Disable-CsComputer -Scorch
```

<span data-ttu-id="a7264-185">我们建议使用 Disable-cscomputer，因为您可能需要在就地升级过程中重新启动服务器。</span><span class="sxs-lookup"><span data-stu-id="a7264-185">We recommend using Disable-CsComputer because you may need to reboot the server during the In-Place Upgrade process.</span></span> <span data-ttu-id="a7264-186">如果您使用 Stop-CsWindowsService，一些服务可能会在重启后自动重新启动。</span><span class="sxs-lookup"><span data-stu-id="a7264-186">If you use Stop-CsWindowsService, some services may restart automatically after a reboot.</span></span> <span data-ttu-id="a7264-187">这可能导致就地升级失败。</span><span class="sxs-lookup"><span data-stu-id="a7264-187">This may cause the In-Place Upgrade to fail.</span></span>
  
### <a name="step-5-upgrade-front-end-pools-and-non-front-end-pool-servers"></a><span data-ttu-id="a7264-188">第 5 步：升级前端池和非前端池服务器</span><span class="sxs-lookup"><span data-stu-id="a7264-188">Step 5: Upgrade Front End pools and non-Front End pool servers</span></span>

> [!NOTE]
>  <span data-ttu-id="a7264-189">请升级安装的所有新必备组件所需的 Skype 业务服务器 2015年其中包括之前： > 至少 32 GB 的可用空间之前尝试升级。</span><span class="sxs-lookup"><span data-stu-id="a7264-189">Before upgrading please install all new prerequisites required for Skype for Business Server 2015 which include:>  At least 32GB of free space before attempting an upgrade.</span></span> <span data-ttu-id="a7264-190">此外，请确保驱动器是固定的本地驱动器、 未连接通过 USB 或防火墙、 格式化为 NTFS 文件系统、 不压缩，并不包含页面文件。 > PowerShell 版本 6.2.9200.0 或更高版本。 > 最新的 Lync Server 2013安装累积更新。 > 安装 SQL Server 2012 SP1。 > 下列 KB 的安装 （自动安装如果使用 Microsoft Update）： > Windows Server 2008 R2[KB2533623](https://support.microsoft.com/kb/2533623)> Windows Server 2012-[KB2858668](https://support.microsoft.com/kb/2858668)> WindowsServer 2012 R2-[KB2982006](https://support.microsoft.com/kb/2982006)</span><span class="sxs-lookup"><span data-stu-id="a7264-190">In addition, make sure that the drive is a fixed local drive, is not connected by USB or Firewire, is formatted with NTFS file system, is not compressed, and does not contain a page file.>  PowerShell version 6.2.9200.0 or later.>  The latest Lync Server 2013 Cumulative Update installed.>  SQL Server 2012 SP1 installed.>  The following KB's installed (installed automatically if using Microsoft Update):>  Windows Server 2008 R2 -[KB2533623](https://support.microsoft.com/kb/2533623)>  Windows Server 2012 -[KB2858668](https://support.microsoft.com/kb/2858668)>  Windows Server 2012 R2 -[KB2982006](https://support.microsoft.com/kb/2982006)</span></span>
  
<span data-ttu-id="a7264-191">使用就地升级每台服务器上更新的前端池、 边缘池、 中介服务器和持久聊天池。</span><span class="sxs-lookup"><span data-stu-id="a7264-191">Use the In-Place Upgrade on each server to update the Front End pool, Edge pool, Mediation server, and the Persistent Chat pool.</span></span>
  
1. <span data-ttu-id="a7264-192">在每台服务器上，从运行**Setup.exe **OCS_Volume\Setup\amd64** ** Skype 业务服务器 2015年安装媒体上。</span><span class="sxs-lookup"><span data-stu-id="a7264-192">On each server, run **Setup.exe** from **OCS_Volume\Setup\amd64** on the Skype for Business Server 2015 installation media.</span></span>
    
2. <span data-ttu-id="a7264-193">接受许可协议，并按照提示操作的就地升级。</span><span class="sxs-lookup"><span data-stu-id="a7264-193">Accept the license agreement and follow the prompts for the In-Place Upgrade.</span></span>
    
3. <span data-ttu-id="a7264-194">在前端池和每台非-前端池服务器的每台服务器重复这些步骤。</span><span class="sxs-lookup"><span data-stu-id="a7264-194">Repeat these steps for each server in the Front End pool and on each non-Front End pool server.</span></span>
    
> [!NOTE]
> <span data-ttu-id="a7264-195">系统可能会在就地升级期间提示您重启服务器。</span><span class="sxs-lookup"><span data-stu-id="a7264-195">You might be prompted to reboot the server during the In-Place Upgrade.</span></span> <span data-ttu-id="a7264-196">这很正常。</span><span class="sxs-lookup"><span data-stu-id="a7264-196">That's ok.</span></span> <span data-ttu-id="a7264-197">就地升级将您重新启动后，继续从其停止。</span><span class="sxs-lookup"><span data-stu-id="a7264-197">After you reboot, the In-Place Upgrade will continue from where it left off.</span></span> 
  
<span data-ttu-id="a7264-198">成功完成就地升级时，您将看到以下消息。</span><span class="sxs-lookup"><span data-stu-id="a7264-198">When the In-Place Upgrade completes successfully, you see the following message.</span></span>
  
![显示就地升级成功完成的屏幕截图。](../media/2f52cb50-9bb4-4714-a982-9c7a0865f78a.png)
  
### <a name="step-6-restart-services-on-all-upgraded-servers"></a><span data-ttu-id="a7264-200">第 6 步：在所有升级后的服务器上重启服务</span><span class="sxs-lookup"><span data-stu-id="a7264-200">Step 6: Restart services on all upgraded servers</span></span>

> [!NOTE]
> <span data-ttu-id="a7264-201">之前重新启动这些服务，请确保在所有前端服务器上不存在 %ProgramData%\WindowsFabric。</span><span class="sxs-lookup"><span data-stu-id="a7264-201">Before restarting the services, please make sure %ProgramData%\WindowsFabric doesn't exist on all Front End Servers.</span></span> <span data-ttu-id="a7264-202">如果存在，请在启动服务之前将其删除。</span><span class="sxs-lookup"><span data-stu-id="a7264-202">If it exists, delete it before starting the services.</span></span> 
  
- <span data-ttu-id="a7264-203">升级中的前端池的所有服务器之后，重新启动服务，通过使用以下 PowerShell 命令：</span><span class="sxs-lookup"><span data-stu-id="a7264-203">After you've upgraded all servers in the Front End pool, restart the services by using the following PowerShell command:</span></span> 
    
  ```
  Start-CsPool
  ```

    > [!NOTE]
    > <span data-ttu-id="a7264-p114">如果在开始运行就地升级之前已存在需要处理的系统重启，则就地升级不会在安装结束时要求您重新启动。在您尝试使用 Start-CSPool cmdlet 启动服务时，这会导致第一台前端服务器出现一些程序集异常。要解决这些错误，请重新启动池中的所有服务器并再次运行该 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a7264-p114">If there is already a pending system reboot needed before you start running In-Place Upgrade, then In-Place Upgrade won't ask you to reboot at the end of the installation. This will cause some assembly exceptions to be thrown against the first Front End server when you try to start services using the Start-CSPool cmdlet. To resolve these errors, reboot all of the servers in the pool and run the cmdlet again.</span></span> 
  
- <span data-ttu-id="a7264-207">在非前端池服务器上，使用以下命令重启服务：</span><span class="sxs-lookup"><span data-stu-id="a7264-207">On the non-Front End pool servers, restart the services by using the following command:</span></span>
    
  ```
  Start-CsWindowsService
  ```

<span data-ttu-id="a7264-208">单击就地升级页面上的“**确定**”之后，您将看到提示您完成此步骤的以下信息。</span><span class="sxs-lookup"><span data-stu-id="a7264-208">After you click **OK** on the In-Place Upgrade page, you'll see the following reminder to complete this step.</span></span>
  
![显示就地升级成功完成后的后续步骤的屏幕截图。](../media/6a7236b6-9ef9-4df3-8682-b0e4021810f9.png)
  
### <a name="step-7-verify-skype-for-business-functionality-works"></a><span data-ttu-id="a7264-210">步骤 7： 验证 Skype 业务功能可以正常运行</span><span class="sxs-lookup"><span data-stu-id="a7264-210">Step 7: Verify Skype for Business functionality works</span></span>

<span data-ttu-id="a7264-211">若要确保升级已成功完成，已升级的池，测试 Skype for Business 以确保该功能可以正常工作。</span><span class="sxs-lookup"><span data-stu-id="a7264-211">To make sure the upgrade was successful, for the pool that was upgraded, test Skype for Business to make sure the functionality is working as expected.</span></span> 
  
### <a name="step-8-upgrade-secondary-pools"></a><span data-ttu-id="a7264-212">第 8 步：升级辅助池</span><span class="sxs-lookup"><span data-stu-id="a7264-212">Step 8: Upgrade secondary pools</span></span>

<span data-ttu-id="a7264-213">重复本主题中的步骤，升级您的环境中的其他任何池。</span><span class="sxs-lookup"><span data-stu-id="a7264-213">Repeat the steps in this topic to upgrade any additional pools that you have in your environment.</span></span>
  
## <a name="troubleshoot-issues-with-the-in-place-upgrade"></a><span data-ttu-id="a7264-214">对就地升级问题进行故障诊断</span><span class="sxs-lookup"><span data-stu-id="a7264-214">Troubleshoot issues with the In-Place Upgrade</span></span>

<span data-ttu-id="a7264-215">如果就地升级失败，您可能会看到如下图所示的消息。</span><span class="sxs-lookup"><span data-stu-id="a7264-215">If the In-Place Upgrade fails, you might see a message similar to what's in the following image.</span></span> 
  
![显示由于未安装所需的累积更新而导致就地升级失败的屏幕截图。](../media/f84db06b-0841-45a9-870d-7ba4b5a463d5.png)
  
<span data-ttu-id="a7264-p115">查看页面底部帮您进行疑难解答的完整消息。单击“**查看日志**”获得更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="a7264-p115">Review the full message at the bottom of the page to help you troubleshoot the issue. Click **View logs** to get more detail.</span></span>
  
<span data-ttu-id="a7264-219">如果上**Verifying 升级准备情况**的就地升级失败或 * * 安装缺少系统必备组件 * *，请确保服务器有所有的最新的 Windows Server、 Lync Server 和 SQL Server 更新应用，并且所有所需的软件和角色安装。</span><span class="sxs-lookup"><span data-stu-id="a7264-219">If the In-Place Upgrade fails on **Verifying upgrade readiness** or ** Installing missing prerequisites**, make sure the server has all the latest Windows Server, Lync Server, and SQL Server updates applied, and all the required software and roles are installed.</span></span> <span data-ttu-id="a7264-220">有什么要求的列表，请参阅[安装必备组件的业务服务器 2015 Skype](install/install-prerequisites.md)和[Skype 的业务服务器 2015年服务器要求](../plan-your-deployment/requirements-for-your-environment/server-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a7264-220">For a list of what's required, see [Server requirements for Skype for Business Server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md) and [Install prerequisites for Skype for Business Server 2015](install/install-prerequisites.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a7264-221">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a7264-221">See also</span></span>

#### 

[<span data-ttu-id="a7264-222">Plan to upgrade to Skype 的业务服务器 2015</span><span class="sxs-lookup"><span data-stu-id="a7264-222">Plan to upgrade to Skype for Business Server 2015</span></span>](../plan-your-deployment/upgrade.md)
  
[<span data-ttu-id="a7264-223">Skype for Business Server 2015 服务器要求</span><span class="sxs-lookup"><span data-stu-id="a7264-223">Server requirements for Skype for Business Server 2015</span></span>](../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="a7264-224">安装 Business Server 2015 Skype 的先决条件</span><span class="sxs-lookup"><span data-stu-id="a7264-224">Install prerequisites for Skype for Business Server 2015</span></span>](install/install-prerequisites.md)
  
[<span data-ttu-id="a7264-225">安装 Business 服务器 2015 Skype</span><span class="sxs-lookup"><span data-stu-id="a7264-225">Install Skype for Business Server 2015</span></span>](install/install.md)

