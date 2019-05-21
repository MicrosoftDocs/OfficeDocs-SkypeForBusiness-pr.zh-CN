---
title: 升级到 Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/14/2016
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 74ce73bc-356b-4705-83b1-341ee010fd19
description: '摘要: 了解如何从 Lync Server 2013 升级到 Skype for business Server 2015。 从 Microsoft 评估中心的以下位置下载 Skype for business Server 2015 的免费试用版https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server:。'
ms.openlocfilehash: f68e944b75af9f921dacd182bab023177a3ab2b1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275512"
---
# <a name="upgrade-to-skype-for-business-server-2015"></a><span data-ttu-id="2bd22-104">Upgrade to Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="2bd22-104">Upgrade to Skype for Business Server 2015</span></span>
 
<span data-ttu-id="2bd22-105">**摘要:** 了解如何从 Lync Server 2013 升级到 Skype for business Server 2015。</span><span class="sxs-lookup"><span data-stu-id="2bd22-105">**Summary:** Learn how to upgrade from Lync Server 2013 to Skype for Business Server 2015.</span></span> <span data-ttu-id="2bd22-106">从[Microsoft 评估中心](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)下载 Skype For business Server 2015 的免费试用版。</span><span class="sxs-lookup"><span data-stu-id="2bd22-106">Download a free trial of Skype for Business Server 2015 from the  [Microsoft Evaluation center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="2bd22-107">使用 "Skype for business 服务器拓扑生成器" 和 "新的就地升级" 功能, 使用本文档中的过程从 Lync Server 2013 升级到 Skype for business Server 2015。</span><span class="sxs-lookup"><span data-stu-id="2bd22-107">Use the procedures in this document to upgrade from Lync Server 2013 to Skype for Business Server 2015 by using the Skype for Business Server Topology Builder and the new In-Place Upgrade feature.</span></span> <span data-ttu-id="2bd22-108">如果要从 Lync Server 2010 或 Office 通信服务器 2007 R2 升级, 请参阅[计划升级到 Skype For Business 服务器 2015](../plan-your-deployment/upgrade.md)。</span><span class="sxs-lookup"><span data-stu-id="2bd22-108">If you want to upgrade from Lync Server 2010 or Office Communications Server 2007 R2, see [Plan to upgrade to Skype for Business Server 2015](../plan-your-deployment/upgrade.md).</span></span>

> [!NOTE]
> <span data-ttu-id="2bd22-109">Skype for business Server 2015 中提供了就地升级, 但 Skype for business Server 2019 不再支持就地升级。</span><span class="sxs-lookup"><span data-stu-id="2bd22-109">In-place upgrades were available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="2bd22-110">支持 "并排 coexistance", 有关详细信息, 请参阅[迁移到 Skype for Business Server 2019](../../SfBServer2019/migration/migration-to-skype-for-business-server-2019.md) 。</span><span class="sxs-lookup"><span data-stu-id="2bd22-110">Side by side coexistance is supported, see [Migration to Skype for Business Server 2019](../../SfBServer2019/migration/migration-to-skype-for-business-server-2019.md) for more information.</span></span>
  
## <a name="upgrade-from-lync-server-2013"></a><span data-ttu-id="2bd22-111">从 Lync Server 2013 升级</span><span class="sxs-lookup"><span data-stu-id="2bd22-111">Upgrade from Lync Server 2013</span></span>

<span data-ttu-id="2bd22-112">将 Lync Server 2013 升级到 Skype for business Server 2015 需要安装必备软件, 使用 Skype for Business Server 拓扑生成器升级池中的数据库, 并使用每个设备上的 Skype for Business 服务器就地升级与池相关联的服务器。</span><span class="sxs-lookup"><span data-stu-id="2bd22-112">Upgrading Lync Server 2013 to Skype for Business Server 2015 involves installing prerequisite software, using the Skype for Business Server Topology Builder to upgrade databases in the pool, and using the Skype for Business Server In-Place Upgrade on each of the servers associated with the pool.</span></span> <span data-ttu-id="2bd22-113">要完成升级，请执行此主题中的八个步骤。</span><span class="sxs-lookup"><span data-stu-id="2bd22-113">To complete the upgrade, go through the eight steps in this topic.</span></span>
  
### <a name="before-you-begin"></a><span data-ttu-id="2bd22-114">开始之前</span><span class="sxs-lookup"><span data-stu-id="2bd22-114">Before you begin</span></span>

- <span data-ttu-id="2bd22-115">查看 [Plan to upgrade to Skype for Business Server 2015](../plan-your-deployment/upgrade.md)。</span><span class="sxs-lookup"><span data-stu-id="2bd22-115">Review [Plan to upgrade to Skype for Business Server 2015](../plan-your-deployment/upgrade.md).</span></span>
    
- <span data-ttu-id="2bd22-116">查看[Skype for Business server 2015 的服务器要求](../plan-your-deployment/requirements-for-your-environment/server-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2bd22-116">Review [Server requirements for Skype for Business Server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span></span>
    
- <span data-ttu-id="2bd22-117">[安装 Skype for Business Server 2015 的先决条件](install/install-prerequisites.md)。</span><span class="sxs-lookup"><span data-stu-id="2bd22-117">[Install prerequisites for Skype for Business Server 2015](install/install-prerequisites.md) .</span></span>
    
- <span data-ttu-id="2bd22-118">[安装 Skype For Business Server 2015](install/install.md) 。</span><span class="sxs-lookup"><span data-stu-id="2bd22-118">[Install Skype for Business Server 2015](install/install.md) .</span></span>
    
### <a name="step-1-install-administrator-tools-and-download-topology"></a><span data-ttu-id="2bd22-119">第 1 步：安装管理员工具并下载拓扑</span><span class="sxs-lookup"><span data-stu-id="2bd22-119">Step 1: Install Administrator tools and download topology</span></span>

1. <span data-ttu-id="2bd22-120">在未安装 Lync OCSCore 或任何其他 Lync 组件的拓扑中连接到计算机。</span><span class="sxs-lookup"><span data-stu-id="2bd22-120">Connect to computer in the topology that does not have Lync OCSCore or any other Lync components installed.</span></span>
    
2. <span data-ttu-id="2bd22-121">从 Skype for Business Server 2015 安装媒体中, \*\*\*\* 从**OCS_Volume\Setup\AMD64**运行 setup.exe。</span><span class="sxs-lookup"><span data-stu-id="2bd22-121">From Skype for Business Server 2015 installation media, run **Setup.exe** from **OCS_Volume\Setup\AMD64**.</span></span> 
    
3. <span data-ttu-id="2bd22-122">单击“**安装**”。</span><span class="sxs-lookup"><span data-stu-id="2bd22-122">Click **Install**.</span></span> 
    
4. <span data-ttu-id="2bd22-123">接受许可协议。</span><span class="sxs-lookup"><span data-stu-id="2bd22-123">Accept the license agreement.</span></span>
    
5. <span data-ttu-id="2bd22-124">在部署向导中，单击“**安装管理员工具**”，按照步骤进行安装。</span><span class="sxs-lookup"><span data-stu-id="2bd22-124">On the Deployment Wizard, click **Install Administrator tools**, and follow the steps to install.</span></span>
    
     ![已调出“安装管理员工具”链接的“部署向导”屏幕截图。](../media/5bbac2d6-a5b3-42b4-a243-7bcf2b04477a.png)
  
6. <span data-ttu-id="2bd22-126">从 Windows "开始" 屏幕中, 打开 "Skype for Business 服务器拓扑生成器"。</span><span class="sxs-lookup"><span data-stu-id="2bd22-126">From the Windows Start screen, open Skype for Business Server Topology Builder.</span></span>
    
7. <span data-ttu-id="2bd22-127">单击“**从现有部署下载拓扑**”，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="2bd22-127">Click **Download topology from existing deployment**, and click **Next**.</span></span>
    
8. <span data-ttu-id="2bd22-128">输入拓扑名称，然后单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="2bd22-128">Enter a name for the topology, and click **Save**.</span></span>
    
9. <span data-ttu-id="2bd22-129">转到保存拓扑的位置，创建一个拓扑副本。</span><span class="sxs-lookup"><span data-stu-id="2bd22-129">Go to location where you saved the topology, and make a copy of the topology.</span></span>
    
### <a name="step-2-upgrade-and-publish-topology-using-topology-builder"></a><span data-ttu-id="2bd22-130">第 2 步：使用拓扑生成器升级和发布拓扑</span><span class="sxs-lookup"><span data-stu-id="2bd22-130">Step 2: Upgrade and publish topology using Topology Builder</span></span>

<span data-ttu-id="2bd22-131">开始升级过程之前, 必须为计划升级的池运行所有服务。</span><span class="sxs-lookup"><span data-stu-id="2bd22-131">Before you start the upgrade process, all services must be running for the pools you plan to upgrade.</span></span> <span data-ttu-id="2bd22-132">这是为了保证拓扑更改复制到池中服务器的本地数据库。</span><span class="sxs-lookup"><span data-stu-id="2bd22-132">This is so the topology changes will be replicated to the local database of the servers in the pool.</span></span>
  
> [!IMPORTANT]
>  <span data-ttu-id="2bd22-133">在升级之前保存拓扑文件副本。</span><span class="sxs-lookup"><span data-stu-id="2bd22-133">Save a copy of your topology file before you upgrade.</span></span> <span data-ttu-id="2bd22-134">升级后, 你将无法降级拓扑。 > 如果你的服务与你的数据库位于同一台服务器上, 如永久聊天服务与持久聊天数据库位于同一台服务器上, 请跳过此步骤, 然后转到步骤4。</span><span class="sxs-lookup"><span data-stu-id="2bd22-134">After you upgrade, you will not be able to downgrade the topology.>  If your services are on the same servers as your databases, like the Persistent Chat service is on the same server as the Persistent Chat database, skip this step, and go to step 4.</span></span> <span data-ttu-id="2bd22-135">停止服务后，请在每台服务器上运行就地升级安装以升级本地数据库。</span><span class="sxs-lookup"><span data-stu-id="2bd22-135">After you stop the services, run the In-Place Upgrade setup on each server to upgrade the local databases.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2bd22-p108">如果拓扑有镜像的后端数据库，那么在使用拓扑生成器**发布拓扑时**，您会看到主数据库和镜像数据库同时出现。发布拓扑时，请确保所有数据库都在主数据库上运行，同时只选择主数据库，而不是镜像数据库，否则，在发布拓扑后，您会看到警告。</span><span class="sxs-lookup"><span data-stu-id="2bd22-p108">If the topology has a back-end database that is mirrored then you will see both the Principal and the Mirrored databases show up **when you publish the topology** using Topology Builder. Make sure all of the databases are running on the Principal and only select the Principal, not the mirror, when publishing the topology otherwise you will see a warning after publishing the topology.</span></span>
  
<span data-ttu-id="2bd22-138">选择以下选项之一, 使用 Skype for Business Server 2015 拓扑生成器升级和发布新拓扑。</span><span class="sxs-lookup"><span data-stu-id="2bd22-138">Pick one of the options below to upgrade and publish a new topology by using the Skype for Business Server 2015 Topology Builder.</span></span> <span data-ttu-id="2bd22-139">在完成这些步骤并发布更新后的拓扑之后，转到本主题中的第 3 步。</span><span class="sxs-lookup"><span data-stu-id="2bd22-139">After you complete the steps and publish the updated topology, move to Step 3 in this topic.</span></span>
  
#### <a name="option-1-upgrade-an-isolated-front-end-pool-and-associated-archiving-and-monitoring-stores"></a><span data-ttu-id="2bd22-140">选项 1：升级隔离的前端池和关联的存档与监控存储</span><span class="sxs-lookup"><span data-stu-id="2bd22-140">Option 1: Upgrade an isolated Front End pool and associated Archiving and Monitoring stores</span></span>

<span data-ttu-id="2bd22-141">如果您升级的池依赖于存档和监控存储，则在使用以下步骤时，存档和监控存储也会随之升级。</span><span class="sxs-lookup"><span data-stu-id="2bd22-141">If the pool you're upgrading has an Archiving and Monitoring store dependency, when you use the following steps, the Archiving and Monitoring store will be upgraded as well.</span></span>
  
1. <span data-ttu-id="2bd22-142">在拓扑生成器中, 右键单击 Lync Server 2013 池, 选择 "**升级到 Skype For Business Server 2015**", 然后按照步骤操作。</span><span class="sxs-lookup"><span data-stu-id="2bd22-142">In Topology Builder, right-click a Lync Server 2013 pool, select **Upgrade to Skype for Business Server 2015**, and follow the steps.</span></span> 
    
     ![包含升级选项的 Lync Server 2013 右键单击菜单屏幕截图。](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
2. <span data-ttu-id="2bd22-144">在拓扑生成器中, 单击 "**操作** > **发布拓扑**" 或 "**操作** > **拓扑** > **发布**"。</span><span class="sxs-lookup"><span data-stu-id="2bd22-144">In Topology Builder, click **Action** > **Publish topology** or **Action** > **Topology** > **Publish**.</span></span> 
    
     ![拓扑生成器中带“发布拓扑”选项的“操作”菜单屏幕截图。](../media/d6712634-9205-401f-a0b0-3ea096ca51bf.png)
  
3. <span data-ttu-id="2bd22-146">在发布期间，选择在存档和监控存储上安装数据库。</span><span class="sxs-lookup"><span data-stu-id="2bd22-146">During publishing, choose to install a database on the Archiving and Monitoring store.</span></span>
    
#### <a name="option-2-upgrade-front-end-pool-without-upgrading-archiving-and-monitoring-stores"></a><span data-ttu-id="2bd22-147">选项 2: 升级前端池而不升级存档和监视存储</span><span class="sxs-lookup"><span data-stu-id="2bd22-147">Option 2: Upgrade Front End pool without upgrading Archiving and Monitoring stores</span></span>

<span data-ttu-id="2bd22-p110">如果您使用以下 步骤，选定池的存档和监控将被禁用。在升级之后，该池将不会有存档和监控存储。</span><span class="sxs-lookup"><span data-stu-id="2bd22-p110">If you use the following steps, archiving and monitoring for the selected pool are disabled. The pool will not have Archiving and Monitoring stores after the upgrade.</span></span>
  
1. <span data-ttu-id="2bd22-150">在拓扑生成器中, 选择要升级的 Lync Server 2013 池。</span><span class="sxs-lookup"><span data-stu-id="2bd22-150">In Topology Builder, select the Lync Server 2013 pool that you want to upgrade.</span></span>
    
2. <span data-ttu-id="2bd22-151">删除 Lync Server 2013 存档和监视存储的相关性。</span><span class="sxs-lookup"><span data-stu-id="2bd22-151">Remove the dependency to the Lync Server 2013 Archiving and Monitoring stores.</span></span> 
    
   - <span data-ttu-id="2bd22-152">转到**操作** > **编辑属性**。</span><span class="sxs-lookup"><span data-stu-id="2bd22-152">Go to **Action** > **Edit properties**.</span></span>
    
   - <span data-ttu-id="2bd22-153">清除“**存档**”复选框。</span><span class="sxs-lookup"><span data-stu-id="2bd22-153">Clear the **Archiving** check box.</span></span>
    
     ![“编辑属性”对话框上的“存档”复选框的屏幕截图。](../media/9a88427e-80ee-49d0-a767-809fa9a5faf1.png)
  
   - <span data-ttu-id="2bd22-155">清除“**监控**”复选框。</span><span class="sxs-lookup"><span data-stu-id="2bd22-155">Clear the **Monitoring** check box.</span></span>
    
     ![显示“监控”复选框的“编辑属性”对话框的屏幕截图。](../media/880acf33-57bb-4521-8717-cf5b67261ed4.png)
  
3. <span data-ttu-id="2bd22-157">右键单击 Lync Server 2013 池, 选择 "**升级到 Skype for Business Server 2015**", 然后按照步骤操作。</span><span class="sxs-lookup"><span data-stu-id="2bd22-157">Right-click the Lync Server 2013 pool, select **Upgrade to Skype for Business Server 2015**, and follow the steps.</span></span> 
    
     ![包含升级选项的 Lync Server 2013 右键单击菜单屏幕截图。](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
4. <span data-ttu-id="2bd22-159">在拓扑生成器中, 单击 "**操作** > **发布拓扑**" 或 "**操作** > **拓扑** > **发布**"。</span><span class="sxs-lookup"><span data-stu-id="2bd22-159">In Topology Builder, click **Action** > **Publish topology** or **Action** > **Topology** > **Publish**.</span></span> 
    
#### <a name="option-3-upgrade-front-end-pool-and-associated-it-to-new-skype-for-business-server-2015-archiving-and-monitoring-stores"></a><span data-ttu-id="2bd22-160">选项 3: 升级前端池并将其关联到新的 Skype for Business Server 2015 存档和监视存储</span><span class="sxs-lookup"><span data-stu-id="2bd22-160">Option 3: Upgrade Front End pool and associated it to new Skype for Business Server 2015 Archiving and Monitoring stores</span></span>

<span data-ttu-id="2bd22-161">如果使用以下步骤，存档和监控将在先前的存储中停止，并在您创建的新存储中启动。</span><span class="sxs-lookup"><span data-stu-id="2bd22-161">If you use the following steps, archiving and monitoring will stop in the previous store and start in the new store you've created.</span></span> 
  
1. <span data-ttu-id="2bd22-162">在拓扑生成器中, 选择要升级的 Lync Server 2013 池。</span><span class="sxs-lookup"><span data-stu-id="2bd22-162">In Topology Builder, select the Lync Server 2013 pool that you want to upgrade.</span></span> 
    
2. <span data-ttu-id="2bd22-163">删除 Lync Server 2013 存档和监视存储的相关性。</span><span class="sxs-lookup"><span data-stu-id="2bd22-163">Remove the dependency to the Lync Server 2013 Archiving and Monitoring stores.</span></span> 
    
   - <span data-ttu-id="2bd22-164">转到**操作** > **编辑属性**。</span><span class="sxs-lookup"><span data-stu-id="2bd22-164">Go to **Action** > **Edit properties**.</span></span>
    
   - <span data-ttu-id="2bd22-165">清除“**存档**”复选框。</span><span class="sxs-lookup"><span data-stu-id="2bd22-165">Clear the **Archiving** check box.</span></span>
    
     ![“编辑属性”对话框上的“存档”复选框的屏幕截图。](../media/9a88427e-80ee-49d0-a767-809fa9a5faf1.png)
  
   - <span data-ttu-id="2bd22-167">清除“**监控**”复选框。</span><span class="sxs-lookup"><span data-stu-id="2bd22-167">Clear the **Monitoring** check box.</span></span>
    
     ![显示“监控”复选框的“编辑属性”对话框的屏幕截图。](../media/880acf33-57bb-4521-8717-cf5b67261ed4.png)
  
3. <span data-ttu-id="2bd22-169">右键单击 Lync Server 2013 池, 选择 "**升级到 Skype for Business Server 2015**", 然后按照步骤操作。</span><span class="sxs-lookup"><span data-stu-id="2bd22-169">Right-click the Lync Server 2013 pool, select **Upgrade to Skype for Business Server 2015**, and follow the steps.</span></span> 
    
     ![包含升级选项的 Lync Server 2013 右键单击菜单屏幕截图。](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
4. <span data-ttu-id="2bd22-171">为存档创建新的 SQL 存储。</span><span class="sxs-lookup"><span data-stu-id="2bd22-171">Create a new SQL store for Archiving.</span></span> 
    
   - <span data-ttu-id="2bd22-172">选择 "池" 和 "**操作** > **编辑" 属性**。</span><span class="sxs-lookup"><span data-stu-id="2bd22-172">Select the pool and **Action** > **Edit properties**.</span></span> 
    
   -  <span data-ttu-id="2bd22-173">选中“**存档**”复选框。</span><span class="sxs-lookup"><span data-stu-id="2bd22-173">Select the **Archiving** check box.</span></span>
    
   - <span data-ttu-id="2bd22-174">单击“新建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2bd22-174">Click **New**.</span></span>
    
     ![显示“存档”部分下的“新建”按钮的“编辑属性”对话框的屏幕截图。](../media/3a4a18e7-8251-4736-837c-2b486f64f896.png)
  
5. <span data-ttu-id="2bd22-176">为监控创建新的 SQL 存储。</span><span class="sxs-lookup"><span data-stu-id="2bd22-176">Create a new SQL store for Monitoring.</span></span> 
    
   - <span data-ttu-id="2bd22-177">选择 "池" 和 "**操作** > **编辑" 属性**。</span><span class="sxs-lookup"><span data-stu-id="2bd22-177">Select the pool and **Action** > **Edit properties**.</span></span> 
    
   -  <span data-ttu-id="2bd22-178">选中“**监控**”复选框。</span><span class="sxs-lookup"><span data-stu-id="2bd22-178">Select the **Monitoring** check box.</span></span>
    
   - <span data-ttu-id="2bd22-179">单击“**新建**”。</span><span class="sxs-lookup"><span data-stu-id="2bd22-179">Click **New**.</span></span>
    
     ![显示“监控”部分下的“新建”按钮的“编辑属性”对话框的屏幕截图。](../media/729c72a7-0068-4e0d-99dc-e480a6bfbf1d.png)
  
6. <span data-ttu-id="2bd22-181">在拓扑生成器中, 单击 "**操作** > **发布拓扑**" 或 "**操作** > **拓扑** > **发布**"。</span><span class="sxs-lookup"><span data-stu-id="2bd22-181">In Topology Builder, click **Action** > **Publish topology** or **Action** > **Topology** > **Publish**.</span></span> 
    
7. <span data-ttu-id="2bd22-182">在发布期间，选择在新的存档和监控存储上安装数据库。</span><span class="sxs-lookup"><span data-stu-id="2bd22-182">During publishing, choose to install the database on the new Archiving and Monitoring store.</span></span>
    
### <a name="step-3-wait-for-replication"></a><span data-ttu-id="2bd22-183">第 3 步：等待复制</span><span class="sxs-lookup"><span data-stu-id="2bd22-183">Step 3: Wait for replication</span></span>

<span data-ttu-id="2bd22-184">留些时间耐心等候复制，以便将更新后的拓扑发布到环境中的所有服务器。</span><span class="sxs-lookup"><span data-stu-id="2bd22-184">Give replication some time to publish the updated topology to all the servers in the environment.</span></span>
  
### <a name="step-4-stop-all-services-in-pool-to-be-upgraded"></a><span data-ttu-id="2bd22-185">第 4 步：停用池中所有需要升级的服务</span><span class="sxs-lookup"><span data-stu-id="2bd22-185">Step 4: Stop all services in pool to be upgraded</span></span>

<span data-ttu-id="2bd22-186">在服务要升级的池的每台服务器上, 在 PowerShell 中运行以下 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="2bd22-186">On each server that is servicing the pool that you're going to upgrade, run the following cmdlet in PowerShell:</span></span>
  
```
Disable-CsComputer -Scorch
```

<span data-ttu-id="2bd22-187">我们建议使用 Disable-CsComputer, 因为在就地升级过程中可能需要重新启动服务器。</span><span class="sxs-lookup"><span data-stu-id="2bd22-187">We recommend using Disable-CsComputer because you may need to reboot the server during the In-Place Upgrade process.</span></span> <span data-ttu-id="2bd22-188">如果您使用 Stop-CsWindowsService，一些服务可能会在重启后自动重新启动。</span><span class="sxs-lookup"><span data-stu-id="2bd22-188">If you use Stop-CsWindowsService, some services may restart automatically after a reboot.</span></span> <span data-ttu-id="2bd22-189">这可能导致就地升级失败。</span><span class="sxs-lookup"><span data-stu-id="2bd22-189">This may cause the In-Place Upgrade to fail.</span></span>
  
### <a name="step-5-upgrade-front-end-pools-and-non-front-end-pool-servers"></a><span data-ttu-id="2bd22-190">第 5 步：升级前端池和非前端池服务器</span><span class="sxs-lookup"><span data-stu-id="2bd22-190">Step 5: Upgrade Front End pools and non-Front End pool servers</span></span>

> [!NOTE]
>  <span data-ttu-id="2bd22-191">升级之前, 请安装 Skype for Business Server 2015 所需的所有新的先决条件, 其中包括: > 至少32GB 的可用空间, 然后再尝试升级。</span><span class="sxs-lookup"><span data-stu-id="2bd22-191">Before upgrading please install all new prerequisites required for Skype for Business Server 2015 which include:>  At least 32GB of free space before attempting an upgrade.</span></span> <span data-ttu-id="2bd22-192">此外, 请确保该驱动器是固定的本地驱动器、未通过 USB 或 Firewire 连接, 但未通过 NTFS 文件系统进行格式化, 也未压缩, 并且不包含页面文件。 > PowerShell 版本6.2.9200.0 或更高版本。 > 最新的 Lync Server 2013已安装累积更新。已安装 > SQL Server 2012 SP1。 > 安装了以下 KB (如果使用 Microsoft Update, 则自动安装): > Windows Server 2008 R2-[KB2533623](https://support.microsoft.com/kb/2533623)_GT_ windows server 2012-[KB2858668](https://support.microsoft.com/kb/2858668)> windows服务器 2012 R2-[KB2982006](https://support.microsoft.com/kb/2982006)</span><span class="sxs-lookup"><span data-stu-id="2bd22-192">In addition, make sure that the drive is a fixed local drive, is not connected by USB or Firewire, is formatted with NTFS file system, is not compressed, and does not contain a page file.>  PowerShell version 6.2.9200.0 or later.>  The latest Lync Server 2013 Cumulative Update installed.>  SQL Server 2012 SP1 installed.>  The following KB's installed (installed automatically if using Microsoft Update):>  Windows Server 2008 R2 -[KB2533623](https://support.microsoft.com/kb/2533623)>  Windows Server 2012 -[KB2858668](https://support.microsoft.com/kb/2858668)>  Windows Server 2012 R2 -[KB2982006](https://support.microsoft.com/kb/2982006)</span></span>
  
<span data-ttu-id="2bd22-193">在每台服务器上使用就地升级来更新前端池、边缘池、中介服务器和持久聊天池。</span><span class="sxs-lookup"><span data-stu-id="2bd22-193">Use the In-Place Upgrade on each server to update the Front End pool, Edge pool, Mediation server, and the Persistent Chat pool.</span></span>
  
1. <span data-ttu-id="2bd22-194">在每台服务器上, 从 Skype for Business Server 2015 安装媒体上的**OCS_Volume\Setup\amd64**运行**setup.exe** 。</span><span class="sxs-lookup"><span data-stu-id="2bd22-194">On each server, run **Setup.exe** from **OCS_Volume\Setup\amd64** on the Skype for Business Server 2015 installation media.</span></span>
    
2. <span data-ttu-id="2bd22-195">接受许可协议并按照提示进行就地升级。</span><span class="sxs-lookup"><span data-stu-id="2bd22-195">Accept the license agreement and follow the prompts for the In-Place Upgrade.</span></span>
    
3. <span data-ttu-id="2bd22-196">对于前端池和每个非前端池服务器上的每个服务器, 重复这些步骤。</span><span class="sxs-lookup"><span data-stu-id="2bd22-196">Repeat these steps for each server in the Front End pool and on each non-Front End pool server.</span></span>
    
> [!NOTE]
> <span data-ttu-id="2bd22-197">系统可能会在就地升级期间提示您重启服务器。</span><span class="sxs-lookup"><span data-stu-id="2bd22-197">You might be prompted to reboot the server during the In-Place Upgrade.</span></span> <span data-ttu-id="2bd22-198">这很正常。</span><span class="sxs-lookup"><span data-stu-id="2bd22-198">That's ok.</span></span> <span data-ttu-id="2bd22-199">重启后, 就地升级将从中断的位置继续。</span><span class="sxs-lookup"><span data-stu-id="2bd22-199">After you reboot, the In-Place Upgrade will continue from where it left off.</span></span> 
  
<span data-ttu-id="2bd22-200">成功完成就地升级时，您将看到以下消息。</span><span class="sxs-lookup"><span data-stu-id="2bd22-200">When the In-Place Upgrade completes successfully, you see the following message.</span></span>
  
![显示就地升级成功完成的屏幕截图。](../media/2f52cb50-9bb4-4714-a982-9c7a0865f78a.png)
  
### <a name="step-6-restart-services-on-all-upgraded-servers"></a><span data-ttu-id="2bd22-202">第 6 步：在所有升级后的服务器上重启服务</span><span class="sxs-lookup"><span data-stu-id="2bd22-202">Step 6: Restart services on all upgraded servers</span></span>

> [!NOTE]
> <span data-ttu-id="2bd22-203">在重新启动服务之前, 请确保%ProgramData%\WindowsFabric 在所有前端服务器上不存在。</span><span class="sxs-lookup"><span data-stu-id="2bd22-203">Before restarting the services, please make sure %ProgramData%\WindowsFabric doesn't exist on all Front End Servers.</span></span> <span data-ttu-id="2bd22-204">如果存在，请在启动服务之前将其删除。</span><span class="sxs-lookup"><span data-stu-id="2bd22-204">If it exists, delete it before starting the services.</span></span> 
  
- <span data-ttu-id="2bd22-205">升级前端池中的所有服务器后, 请使用以下 PowerShell 命令重新启动服务:</span><span class="sxs-lookup"><span data-stu-id="2bd22-205">After you've upgraded all servers in the Front End pool, restart the services by using the following PowerShell command:</span></span> 
    
  ```
  Start-CsPool
  ```

    > [!NOTE]
    > <span data-ttu-id="2bd22-p115">如果在开始运行就地升级之前已存在需要处理的系统重启，则就地升级不会在安装结束时要求您重新启动。在您尝试使用 Start-CSPool cmdlet 启动服务时，这会导致第一台前端服务器出现一些程序集异常。要解决这些错误，请重新启动池中的所有服务器并再次运行该 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="2bd22-p115">If there is already a pending system reboot needed before you start running In-Place Upgrade, then In-Place Upgrade won't ask you to reboot at the end of the installation. This will cause some assembly exceptions to be thrown against the first Front End server when you try to start services using the Start-CSPool cmdlet. To resolve these errors, reboot all of the servers in the pool and run the cmdlet again.</span></span> 
  
- <span data-ttu-id="2bd22-209">在非前端池服务器上，使用以下命令重启服务：</span><span class="sxs-lookup"><span data-stu-id="2bd22-209">On the non-Front End pool servers, restart the services by using the following command:</span></span>
    
  ```
  Start-CsWindowsService
  ```

<span data-ttu-id="2bd22-210">单击就地升级页面上的“**确定**”之后，您将看到提示您完成此步骤的以下信息。</span><span class="sxs-lookup"><span data-stu-id="2bd22-210">After you click **OK** on the In-Place Upgrade page, you'll see the following reminder to complete this step.</span></span>
  
![显示就地升级成功完成后的后续步骤的屏幕截图。](../media/6a7236b6-9ef9-4df3-8682-b0e4021810f9.png)
  
### <a name="step-7-verify-skype-for-business-functionality-works"></a><span data-ttu-id="2bd22-212">步骤 7: 验证 Skype for Business 功能是否正常工作</span><span class="sxs-lookup"><span data-stu-id="2bd22-212">Step 7: Verify Skype for Business functionality works</span></span>

<span data-ttu-id="2bd22-213">若要确保升级成功, 请对已升级的池进行测试, 测试 Skype for business 以确保功能按预期工作。</span><span class="sxs-lookup"><span data-stu-id="2bd22-213">To make sure the upgrade was successful, for the pool that was upgraded, test Skype for Business to make sure the functionality is working as expected.</span></span> 
  
### <a name="step-8-upgrade-secondary-pools"></a><span data-ttu-id="2bd22-214">第 8 步：升级辅助池</span><span class="sxs-lookup"><span data-stu-id="2bd22-214">Step 8: Upgrade secondary pools</span></span>

<span data-ttu-id="2bd22-215">重复本主题中的步骤，升级您的环境中的其他任何池。</span><span class="sxs-lookup"><span data-stu-id="2bd22-215">Repeat the steps in this topic to upgrade any additional pools that you have in your environment.</span></span>
  
## <a name="troubleshoot-issues-with-the-in-place-upgrade"></a><span data-ttu-id="2bd22-216">对就地升级问题进行故障诊断</span><span class="sxs-lookup"><span data-stu-id="2bd22-216">Troubleshoot issues with the In-Place Upgrade</span></span>

<span data-ttu-id="2bd22-217">如果就地升级失败，您可能会看到如下图所示的消息。</span><span class="sxs-lookup"><span data-stu-id="2bd22-217">If the In-Place Upgrade fails, you might see a message similar to what's in the following image.</span></span> 
  
![显示由于未安装所需的累积更新而导致就地升级失败的屏幕截图。](../media/f84db06b-0841-45a9-870d-7ba4b5a463d5.png)
  
<span data-ttu-id="2bd22-219">查看页面底部帮您进行疑难解答的完整消息。</span><span class="sxs-lookup"><span data-stu-id="2bd22-219">Review the full message at the bottom of the page to help you troubleshoot the issue.</span></span> <span data-ttu-id="2bd22-220">单击“**查看日志**”获得更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="2bd22-220">Click **View logs** to get more detail.</span></span>
  
<span data-ttu-id="2bd22-221">如果就地升级在**验证升级准备情况**或**安装缺少的先决条件**时失败, 请确保服务器已应用所有最新的 Windows server、Lync server 和 SQL server 更新, 并且所有必需的软件和角色都是安装.</span><span class="sxs-lookup"><span data-stu-id="2bd22-221">If the In-Place Upgrade fails on **Verifying upgrade readiness** or **Installing missing prerequisites**, make sure the server has all the latest Windows Server, Lync Server, and SQL Server updates applied, and all the required software and roles are installed.</span></span> <span data-ttu-id="2bd22-222">有关所需内容的列表, 请参阅[skype for Business server 2015 的服务器要求](../plan-your-deployment/requirements-for-your-environment/server-requirements.md)和[安装 Skype for business server 2015 的先决条件](install/install-prerequisites.md)。</span><span class="sxs-lookup"><span data-stu-id="2bd22-222">For a list of what's required, see [Server requirements for Skype for Business Server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md) and [Install prerequisites for Skype for Business Server 2015](install/install-prerequisites.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2bd22-223">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2bd22-223">See also</span></span>

[<span data-ttu-id="2bd22-224">Plan to upgrade to Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="2bd22-224">Plan to upgrade to Skype for Business Server 2015</span></span>](../plan-your-deployment/upgrade.md)
  
[<span data-ttu-id="2bd22-225">Server requirements for Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="2bd22-225">Server requirements for Skype for Business Server 2015</span></span>](../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="2bd22-226">Skype for Business Server 2015 的安装先决条件</span><span class="sxs-lookup"><span data-stu-id="2bd22-226">Install prerequisites for Skype for Business Server 2015</span></span>](install/install-prerequisites.md)
  
[<span data-ttu-id="2bd22-227">安装 Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="2bd22-227">Install Skype for Business Server 2015</span></span>](install/install.md)
