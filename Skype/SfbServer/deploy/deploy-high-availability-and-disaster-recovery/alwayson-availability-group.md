---
title: 为业务服务器部署在 Skype 的后端服务器上始终在可用性组
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c93c01e6-626c-40ad-92dd-373b0fe9189f
description: 部署 （安装） 始终在可用性组中您 Skype 业务服务器部署。
ms.openlocfilehash: eaf0c935f246cfdd00aa0707475442c88dc89b8a
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25374370"
---
# <a name="deploy-an-always-on-availability-group-on-a-back-end-server-in-skype-for-business-server"></a><span data-ttu-id="a4ad1-103">为业务服务器部署在 Skype 的后端服务器上始终在可用性组</span><span class="sxs-lookup"><span data-stu-id="a4ad1-103">Deploy an Always On Availability Group on a Back End Server in Skype for Business Server</span></span>
 
<span data-ttu-id="a4ad1-104">部署 （安装） 始终在可用性组 (AG) 中您 Skype 业务服务器部署。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-104">Deploy (install) an Always On Availability Group (AG) in your Skype for Business Server deployment.</span></span>
  
<span data-ttu-id="a4ad1-105">AG 的部署方式取决于是否要在新的池、 使用镜像，一个现有池或现有池当前拥有的后端数据库不高可用性部署它。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-105">How you deploy an AG depends on whether you are deploying it in a new pool, an existing pool that uses mirroring, or an existing pool that currently has no high availability for the Back End database.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a4ad1-106">不支持使用 AG 与持久聊天服务器角色。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-106">Using an AG with a Persistent Chat Server role is not supported.</span></span> 
  
- [<span data-ttu-id="a4ad1-107">部署始终在可用性组的新的前端池上</span><span class="sxs-lookup"><span data-stu-id="a4ad1-107">Deploy an Always On Availability Group on a new Front End pool</span></span>](alwayson-availability-group.md#BKMK_NewPool_CreateAlwaysOnGroup)
    
- [<span data-ttu-id="a4ad1-108">部署始终在可用性组使用数据库镜像的现有池上</span><span class="sxs-lookup"><span data-stu-id="a4ad1-108">Deploy an Always On Availability Group on an existing pool that uses database mirroring</span></span>](alwayson-availability-group.md#BKMK_MirroredPool_CreateAlwaysOnGroup)
    
- [<span data-ttu-id="a4ad1-109">部署始终在可用性上的组，在不使用数据库镜像的现有池</span><span class="sxs-lookup"><span data-stu-id="a4ad1-109">Deploy an Always On Availability Group on an existing pool that does not use database mirroring</span></span>](alwayson-availability-group.md#BKMK_NoHAPool_CreateAlwaysOnGroup)
    
## <a name="deploy-an-always-on-availability-group-on-a-new-front-end-pool"></a><span data-ttu-id="a4ad1-110">部署始终在可用性组的新的前端池上</span><span class="sxs-lookup"><span data-stu-id="a4ad1-110">Deploy an Always On Availability Group on a new Front End pool</span></span>
<span data-ttu-id="a4ad1-111"><a name="BKMK_NewPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="a4ad1-111"></span></span>

1. <span data-ttu-id="a4ad1-112">启用将 AG 的一部分的所有数据库服务器上的故障转移群集功能。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-112">Enable the Failover Clustering feature on all the database servers which will be part of the AG.</span></span> <span data-ttu-id="a4ad1-113">在每台服务器上，执行以下操作</span><span class="sxs-lookup"><span data-stu-id="a4ad1-113">On each server, do the following</span></span>
    
   - <span data-ttu-id="a4ad1-114">打开“服务器管理器”，然后单击“**添加角色和功能**”。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-114">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="a4ad1-p102">单击“**下一步**”，直至达到“**选择功能**”框。在这里选中“**故障转移群集**”复选框。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-p102">Click **Next** until you reach the **Select features** box. Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="a4ad1-117">在“**添加故障转移群集所需的功能？**”框中，单击“**添加功能**”。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-117">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="a4ad1-118">单击“**安装**”。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-118">Click **Install**.</span></span>
    
2. <span data-ttu-id="a4ad1-119">验证群集配置。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-119">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="a4ad1-120">在“服务器管理器”中，单击“**工具**”菜单，然后单击“**故障转移群集管理器**”。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-120">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="a4ad1-121">在屏幕右侧的“**操作**”中，单击“**验证配置**”。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-121">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="a4ad1-122">在“**在你开始前**”页上，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-122">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="a4ad1-123">选择要添加到群集的服务器，然后单击“**运行所有测试**”。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-123">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="a4ad1-124">在**摘要**框中，选中向导将报告的任何错误。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-124">In the**Summary** box, check any errors that the wizard reports.</span></span> <span data-ttu-id="a4ad1-125">然后单击“**完成**”完成验证。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-125">Then click **Finish** to complete the validation.</span></span>
    
     <span data-ttu-id="a4ad1-p104">向导可能报告多个警告，尤其是在你未使用共享存储的情况下。你不是必须要使用共享存储。但是，如果看到任何**错误**消息，则必须修正这些问题后才能继续。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-p104">The wizard will probably report several warnings, especially if you are not using shared storage. You are not required to use shared storage. However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
3. <span data-ttu-id="a4ad1-129">创建 Windows Server 故障转移群集 (WSFC)。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-129">Create the Windows Server Failover Cluster (WSFC).</span></span>
    
   - <span data-ttu-id="a4ad1-130">在“**故障转移群集管理**”向导中，右键单击“**故障转移群集管理**”，然后单击“**创建群集**”。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-130">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="a4ad1-131">在“**在你开始前**”页上，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-131">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="a4ad1-p105">添加群集名称和 IP 地址。验证设置后，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-p105">Add the cluster name and IP address. When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="a4ad1-134">在“确认”页上，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-134">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="a4ad1-135">创建群集后，单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-135">After the cluster is created, click **Finish**.</span></span>
    
4. <span data-ttu-id="a4ad1-p106">我们建议配置群集仲裁设置来使用文件共享见证。为此，请使用以下步骤：</span><span class="sxs-lookup"><span data-stu-id="a4ad1-p106">We recommend that you configure the cluster quorum settings to use a file share witness. To do so, use these steps:</span></span>
    
   - <span data-ttu-id="a4ad1-138">右键单击群集名称，单击“**更多操作**”，然后单击“**配置群集仲裁设置**”。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-138">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="a4ad1-139">在“**选择仲裁配置选项**”页上，单击“**选择仲裁见证**”。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-139">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="a4ad1-140">在“**选择仲裁见证**”页中，单击“**配置文件共享见证**”。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-140">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="a4ad1-141">在“**配置文件共享见证**”页中，键入要使用的文件共享的路径，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-141">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="a4ad1-142">在“**确认**”页上，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-142">On the **Confirmation** page, click **Next**.</span></span>
    
5. <span data-ttu-id="a4ad1-143">在群集中的每台服务器上启用 AG 功能在 SQL Server 配置管理器。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-143">On each server in the cluster, enable the AG feature in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="a4ad1-p107">打开 SQL Server 配置管理器。在屏幕左侧的树中，单击“**SQL Server 服务**”，然后双击“SQL Server 服务”。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-p107">Open SQL Server Configuration Manager. In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="a4ad1-p108">在“**属性**”框中，选择“**AlwaysOn 高可用性**”选项卡。选中“**启用 AlwaysOn 可用性组**”复选框。出现提示时，重新启动 SQL Server 服务。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-p108">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box. Restart the SQL Server service when prompted.</span></span>
    
6. <span data-ttu-id="a4ad1-148">创建可用性组。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-148">Create the availability group.</span></span>
    
   - <span data-ttu-id="a4ad1-149">打开 SQL Server Management Studio，然后连接到 SQL Server 实例。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-149">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
   - <span data-ttu-id="a4ad1-150">在对象资源管理器中，展开**始终在高可用性**文件夹。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-150">In Object Explorer, expand the **Always On High Availability** folder.</span></span> <span data-ttu-id="a4ad1-151">右键单击“**可用性组**”文件夹，然后单击“**新建可用性组向导**”。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-151">Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
   - <span data-ttu-id="a4ad1-152">如果出现“**简介**”页，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-152">If the **Introduction** page appears, click **Next**.</span></span>
    
   - <span data-ttu-id="a4ad1-153">在“**指定可用性组名称**”页中，输入可用性组的名称，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-153">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
   - <span data-ttu-id="a4ad1-154">在选择数据库页中，选择您想要包括在 AlwaysOn 可用性组的数据库。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-154">In the Select Databases page, select the databases that you want to include in the AlwaysOn Availability Group.</span></span> <span data-ttu-id="a4ad1-155">然后单击" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-155">Then click **Next**.</span></span>
    
     <span data-ttu-id="a4ad1-156">不包括**ReportServer**、 **ReportServerTempDB**或持久聊天数据库 AlwaysOn 可用性组中，为这些不支持此方案中。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-156">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AlwaysOn Availability Group, as these are not supported in this scenario.</span></span> <span data-ttu-id="a4ad1-157">您可以包含业务服务器数据库的所有其他 Skype AlwaysOn 可用性组中。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-157">You can include all other Skype for Business Server databases in the AlwaysOn Availability Group.</span></span>
    
   - <span data-ttu-id="a4ad1-158">在“**指定副本**”页上，单击“**副本**”选项卡。然后单击“**添加副本**”按钮，并连接到你作为 Windows Server 故障转移群集的节点加入的其他 SQL 实例。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-158">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the Windows Server Failover Cluster.</span></span>
    
   - <span data-ttu-id="a4ad1-p112">对于每个实例，选择“**自动故障转移**”和“**同步提交**”选项。不要选择“**可读辅助副本**”选项。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-p112">For each instance, select the **Automatic Failover** and **Synchronous Commit** options. Do not select the **Readable Secondary** option.</span></span>
    
   - <span data-ttu-id="a4ad1-161">单击“**端点**”选项卡，并验证“**端口号**”设为 5022。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-161">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
   - <span data-ttu-id="a4ad1-p113">单击“**侦听器**”选项卡，选择“**创建可用性组侦听器**”选项。在该选项下面，键入侦听器的名称，然后将“**端口**”设置为 1433（对于此选项，不支持其他端口）。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-p113">Click the **Listener** tab, and select the **Create an availability group listener** option. Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
   - <span data-ttu-id="a4ad1-164">单击“**添加**”，然后在“**IPv4 地址**”框中，提供你的首选虚拟 IP 地址，然后单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-164">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
   - <span data-ttu-id="a4ad1-p114">在“**选择初始数据同步**”页上，选择“完全”，然后指定副本可访问，并且两个副本所使用的 SQL Server 服务帐户有写入权限的文件夹。然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-p114">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for. Then click **Next**.</span></span>
    
     <span data-ttu-id="a4ad1-p115">初始化数据库时，会临时使用此文件共享。如果在处理大数据库，我们建议手动初始化数据库，以防网络带宽容不下数据库备份的大小。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-p115">This file share will be used temporarily when you initialize the databases. If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
   - <span data-ttu-id="a4ad1-169">在“验证”页上，确认所有验证检查都已成功，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-169">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
   - <span data-ttu-id="a4ad1-170">在**摘要**页上，验证所有设置并单击完成。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-170">In the**Summary** page, verify all settings and click Finish.</span></span>
    
7. <span data-ttu-id="a4ad1-171">使用拓扑生成器来创建前端池中, 所述[创建和发布新拓扑中 Skype 业务服务器](../../deploy/install/create-and-publish-new-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-171">Use Topology Builder to create the Front End pool, as explained in [Create and publish new topology in Skype for Business Server](../../deploy/install/create-and-publish-new-topology.md).</span></span> <span data-ttu-id="a4ad1-172">执行操作时，指定 AG 为池的 SQL 存储。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-172">When you do, specify the AG as the SQL store for the pool.</span></span>
    
8. <span data-ttu-id="a4ad1-173">部署的池以及 AG 后，执行一些最终的步骤，以确保 SQL 登录名位于每个 AlwaysOn 可用性组中的副本。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-173">After the pool and the AG are deployed, perform some final steps to make sure that the SQL logins are on each of the replicas in the AlwaysOn Availability Group.</span></span> 
    
   - <span data-ttu-id="a4ad1-174">打开拓扑生成器，选择**下载从现有部署的拓扑**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-174">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
   - <span data-ttu-id="a4ad1-175">依次展开 Skype for Business Server、你的拓扑，以及“**SQL Server 存储**”。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-175">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="a4ad1-176">右键单击新 AlwaysOn 可用性组的 SQL 存储，然后单击**编辑属性**。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-176">Right-click the SQL store of the new AlwaysOn Availability Group, and click **Edit Properties**.</span></span>
    
     - <span data-ttu-id="a4ad1-177">在**SQL Server FQDN**框中，页的底部的值更改为 AG 的侦听器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-177">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AG.</span></span>
    
   - <span data-ttu-id="a4ad1-p118">发布拓扑。从“**操作**”菜单中，单击“**拓扑**”，然后单击“**发布**”。在确认页上，单击“**下一步**”。然后等待几分钟，让新拓扑进行复制。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-p118">Publish the topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**. Then wait a few minutes for the new topology to replicate.</span></span>
    
   - <span data-ttu-id="a4ad1-182">打开 SQL Server Management Studio，并导航到 AG。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-182">Open SQL Server Management Studio, and navigate to the AG.</span></span> <span data-ttu-id="a4ad1-183">将其故障转移到辅助副本。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-183">Fail it over to a secondary replica.</span></span>
    
   - <span data-ttu-id="a4ad1-184">打开 Skype 业务 Server Management Shell 并键入以下 cmdlet，以在此副本上创建 SQL 登录名：</span><span class="sxs-lookup"><span data-stu-id="a4ad1-184">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
   ```
   Install-CsDatabase -Update
   ```

   - <span data-ttu-id="a4ad1-185">重复前面两个步骤 (故障转移到辅助副本，组，然后使用`Install-CsDatabase -Update`) 的组中的每个副本。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-185">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
    
## <a name="deploy-an-always-on-availability-group-on-an-existing-pool-that-uses-database-mirroring"></a><span data-ttu-id="a4ad1-186">部署始终在可用性组使用数据库镜像的现有池上</span><span class="sxs-lookup"><span data-stu-id="a4ad1-186">Deploy an Always On Availability Group on an existing pool that uses database mirroring</span></span>
<span data-ttu-id="a4ad1-187"><a name="BKMK_MirroredPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="a4ad1-187"></span></span>

> [!NOTE]
> <span data-ttu-id="a4ad1-188">如果您要升级到 AG 池承载中央管理存储为您的组织，则必须先移动 CMS 到另一个池升级此池之前。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-188">If the pool you are upgrading to an AG hosts the Central Management store for your organization, you must first move the CMS to another pool before you upgrade this pool.</span></span> <span data-ttu-id="a4ad1-189">可使用 Move-CsManagementServer cmdlet 来移动池。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-189">Use the Move-CsManagementServer cmdlet to move the pool.</span></span> <span data-ttu-id="a4ad1-190">如果您的组织中没有另一个池，可以暂时部署 Standard Edition server，并将 CMS 移动到此服务器，然后再升级到 AG 的池。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-190">If you do not have another pool in your organization, you can deploy a Standard Edition server temporarily and move the CMS to this server before you upgrade your pool to the AG.</span></span> 
  
1. <span data-ttu-id="a4ad1-191">通过为业务 Server 命令行管理程序中打开 Skype 并键入以下 cmdlet，故障转移镜像到主体的节点的所有数据。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-191">Fail over all data from the mirror to the principal node by opening Skype for Business Server Management Shell and typing the following cmdlet.</span></span>
    
   ```
   Invoke-CsDatabaseFailover -PoolFqdn <Pool FQDN> -DatabaseType <DatabaseType> -NewPrincipal "Primary"
   ```

    <span data-ttu-id="a4ad1-p121">对池中的每种数据库类型重复此 cmdlet。可以使用下面的 cmdlet 查找存储在此池中的所有数据库类型。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-p121">Repeat this cmdlet for each database type in the pool. You can use the following cmdlet to find all the database types stored in this pool.</span></span>
     
   ```
   Get-CsPool -Identity <Pool FQDN>
   ```

2. <span data-ttu-id="a4ad1-194">使用拓扑生成器从池中删除数据库镜像</span><span class="sxs-lookup"><span data-stu-id="a4ad1-194">Use Topology Builder to remove database mirroring from the pool</span></span>
    
   - <span data-ttu-id="a4ad1-195">打开拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-195">Open Topology Builder.</span></span> <span data-ttu-id="a4ad1-196">在拓扑中，展开“**Enterprise Edition 前端池**”，右键单击池的名称，然后单击“**编辑属性**”。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-196">In your topology, expand **Enterprise Edition Front End Pools**, right-click the name of the pool, and click **Edit Properties**.</span></span>
    
   - <span data-ttu-id="a4ad1-197">对于池中的每种 SQL 存储类型，不要选中“**启用 SQL 存储镜像**”复选框。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-197">For each type of SQL store in the pool, clear the **Enable SQL Store Mirroring** check box.</span></span>
    
3. <span data-ttu-id="a4ad1-p123">发布更改后的拓扑。从“**操作**”菜单中，单击“**拓扑**”，然后单击“**发布**”。然后在确认页中，单击“**下一步**”</span><span class="sxs-lookup"><span data-stu-id="a4ad1-p123">Publish the changed topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**</span></span>
    
4. <span data-ttu-id="a4ad1-201">使用 SQL Server Management Studio 打破镜像。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-201">Use SQL Server Management Studio to break the mirror.</span></span>
    
   - <span data-ttu-id="a4ad1-p124">打开 SQL Server Management Studio，转到数据库，右键单击“**任务**”，再单击“**镜像**”。然后单击“**取消镜像**”，再单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-p124">Open SQL Server Management Studio, navigate to your databases, right-click **Tasks** and click **Mirror**. Then click **Remove Mirroring** and click **OK**.</span></span>
    
   - <span data-ttu-id="a4ad1-204">重复上述过程中将转换为 AG 的池的所有数据库。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-204">Repeat this for all databases in the pool which will be converted to an AG.</span></span>
    
5. <span data-ttu-id="a4ad1-205">设置将 AG 的一部分的所有数据库服务器上的故障转移群集功能。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-205">Set up the Failover Clustering feature on all the database servers which will be part of the AG.</span></span> <span data-ttu-id="a4ad1-206">在每台服务器上，执行以下操作</span><span class="sxs-lookup"><span data-stu-id="a4ad1-206">On each server, do the following</span></span>
    
   - <span data-ttu-id="a4ad1-207">打开“服务器管理器”，然后单击“**添加角色和功能**”。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-207">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="a4ad1-p126">单击“**下一步**”，直至达到“**选择功能**”框。在这里选中“**故障转移群集**”复选框。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-p126">Click **Next** until you reach the **Select features** box. Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="a4ad1-210">在“**添加故障转移群集所需的功能？**”框中，单击“**添加功能**”。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-210">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="a4ad1-211">单击“**安装**”。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-211">Click **Install**.</span></span>
    
6. <span data-ttu-id="a4ad1-212">验证群集配置。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-212">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="a4ad1-213">在“服务器管理器”中，单击“**工具**”菜单，然后单击“**故障转移群集管理器**”。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-213">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="a4ad1-214">在屏幕右侧的“**操作**”中，单击“**验证配置**”。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-214">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="a4ad1-215">在“**在你开始前**”页上，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-215">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="a4ad1-216">选择要添加到群集的服务器，然后单击“**运行所有测试**”。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-216">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="a4ad1-217">在**摘要**框中，选中向导将报告的任何错误。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-217">In the**Summary** box, check any errors that the wizard reports.</span></span> <span data-ttu-id="a4ad1-218">然后单击“**完成**”完成验证。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-218">Then click **Finish** to complete the validation.</span></span>
    
     <span data-ttu-id="a4ad1-p128">向导可能报告多个警告，尤其是在你未使用共享存储的情况下。你不是必须要使用共享存储。但是，如果看到任何**错误**消息，则必须修正这些问题后才能继续。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-p128">The wizard will probably report several warnings, especially if you are not using shared storage. You are not required to use shared storage. However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
7. <span data-ttu-id="a4ad1-222">创建 Windows Server 故障转移群集。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-222">Create the Windows Server Failover Cluster.</span></span>
    
   - <span data-ttu-id="a4ad1-223">在“**故障转移群集管理**”向导中，右键单击“**故障转移群集管理**”，然后单击“**创建群集**”。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-223">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="a4ad1-224">在“**在你开始前**”页上，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-224">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="a4ad1-p129">添加群集名称和 IP 地址。验证设置后，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-p129">Add the cluster name and IP address. When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="a4ad1-227">在“确认”页上，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-227">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="a4ad1-228">创建群集后，单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-228">After the cluster is created, click **Finish**.</span></span>
    
8. <span data-ttu-id="a4ad1-p130">我们建议配置群集仲裁设置来使用文件共享见证。为此，请使用以下步骤：</span><span class="sxs-lookup"><span data-stu-id="a4ad1-p130">We recommend that you configure the cluster quorum settings to use a file share witness. To do so, use these steps:</span></span>
    
   - <span data-ttu-id="a4ad1-231">右键单击群集名称，单击“**更多操作**”，然后单击“**配置群集仲裁设置**”。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-231">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="a4ad1-232">在“**选择仲裁配置选项**”页上，单击“**选择仲裁见证**”。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-232">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="a4ad1-233">在“**选择仲裁见证**”页中，单击“**配置文件共享见证**”。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-233">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="a4ad1-234">在“**配置文件共享见证**”页中，键入要使用的文件共享的路径，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-234">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="a4ad1-235">在“**确认**”页上，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-235">On the **Confirmation** page, click **Next**.</span></span>
    
9. <span data-ttu-id="a4ad1-236">在群集中的每台服务器上启用 AG 功能在 SQL Server 配置管理器。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-236">On each server in the cluster, enable the AG feature in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="a4ad1-p131">打开 SQL Server 配置管理器。在屏幕左侧的树中，单击“**SQL Server 服务**”，然后双击“SQL Server 服务”。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-p131">Open SQL Server Configuration Manager. In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="a4ad1-p132">在“**属性**”框中，选择“**AlwaysOn 高可用性**”选项卡。选中“**启用 AlwaysOn 可用性组**”复选框。出现提示时，重新启动 SQL Server 服务。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-p132">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box. Restart the SQL Server service when prompted.</span></span>
    
10. <span data-ttu-id="a4ad1-241">创建可用性组。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-241">Create the availability group.</span></span>
    
    - <span data-ttu-id="a4ad1-242">打开 SQL Server Management Studio，然后连接到 SQL Server 实例。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-242">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
    - <span data-ttu-id="a4ad1-243">在对象资源管理器中，展开**始终在高可用性**文件夹。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-243">In Object Explorer, expand the **Always On High Availability** folder.</span></span> <span data-ttu-id="a4ad1-244">右键单击“**可用性组**”文件夹，然后单击“**新建可用性组向导**”。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-244">Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
    - <span data-ttu-id="a4ad1-245">如果出现“**简介**”页，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-245">If the **Introduction** page appears, click **Next**.</span></span>
    
    - <span data-ttu-id="a4ad1-246">在“**指定可用性组名称**”页中，输入可用性组的名称，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-246">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
    - <span data-ttu-id="a4ad1-247">在选择数据库页中，选择您想要包括在 AlwaysOn 可用性组的数据库。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-247">In the Select Databases page, select the databases that you want to include in the AlwaysOn Availability Group.</span></span> <span data-ttu-id="a4ad1-248">然后单击" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-248">Then click **Next**.</span></span>
    
    <span data-ttu-id="a4ad1-249">不包括**ReportServer**、 **ReportServerTempDB**或持久聊天数据库 AlwaysOn 可用性组中，为这些不支持此方案中。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-249">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AlwaysOn Availability Group, as these are not supported in this scenario.</span></span> <span data-ttu-id="a4ad1-250">您可以包含业务服务器数据库的所有其他 Skype AlwaysOn 可用性组中。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-250">You can include all other Skype for Business Server databases in the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="a4ad1-251">在“**指定副本**”页上，单击“**副本**”选项卡。然后单击“**添加副本**”按钮，并连接到你作为 Windows Server 故障转移群集的节点加入的其他 SQL 实例。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-251">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the Windows Server Failover Cluster.</span></span>
    
    - <span data-ttu-id="a4ad1-p136">对于每个实例，选择“**自动故障转移**”和“**同步提交**”选项。不要选择“**可读辅助副本**”选项。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-p136">For each instance, select the **Automatic Failover** and **Synchronous Commit** options. Do not select the **Readable Secondary** option.</span></span>
    
    - <span data-ttu-id="a4ad1-254">单击“**端点**”选项卡，并验证“**端口号**”设为 5022。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-254">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
      - <span data-ttu-id="a4ad1-p137">单击“**侦听器**”选项卡，选择“**创建可用性组侦听器**”选项。在该选项下面，键入侦听器的名称，然后将“**端口**”设置为 1433（对于此选项，不支持其他端口）。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-p137">Click the **Listener** tab, and select the **Create an availability group listener** option. Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
    - <span data-ttu-id="a4ad1-257">单击“**添加**”，然后在“**IPv4 地址**”框中，提供你的首选虚拟 IP 地址，然后单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-257">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
    - <span data-ttu-id="a4ad1-p138">在“**选择初始数据同步**”页上，选择“完全”，然后指定副本可访问，并且两个副本所使用的 SQL Server 服务帐户有写入权限的文件夹。然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-p138">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for. Then click **Next**.</span></span>
    
    <span data-ttu-id="a4ad1-p139">初始化数据库时，会临时使用此文件共享。如果在处理大数据库，我们建议手动初始化数据库，以防网络带宽容不下数据库备份的大小。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-p139">This file share will be used temporarily when you initialize the databases. If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
    - <span data-ttu-id="a4ad1-262">在“验证”页上，确认所有验证检查都已成功，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-262">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
    - <span data-ttu-id="a4ad1-263">在“**摘要**”页上，验证所有设置，然后单击“完成”。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-263">In the **Summary** page, verify all settings and click Finish.</span></span>
    
11. <span data-ttu-id="a4ad1-264">创建新的存储指定 AG 侦听器，并为 AG 的主节点中指定的旧镜像的主体。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-264">Create a new store specifying the AG listener, and specifying the principal of the old mirror as the primary node of the AG.</span></span>
    
    - <span data-ttu-id="a4ad1-265">打开拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-265">Open Topology Builder.</span></span> <span data-ttu-id="a4ad1-266">在拓扑中，展开“**共享组件**”，右键单击“**SQL Server 存储**”，然后单击“**新建 SQL Server 存储**”。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-266">In your topology, expand **Shared Components**, right-click **SQL Server Stores**, and click **New SQL Server Store**.</span></span>
    
    - <span data-ttu-id="a4ad1-267">在“**定义新的 SQL 存储**”页上，先选中“**高可用性设置**”复选框，然后确保 SQL AlwaysOn 可用性组出现在下拉框中。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-267">In the **Define New SQL Store** page, first select the **High Availability Settings** check box, and then make sure that SQL AlwaysOn Availability Groups appears in the drop-down box.</span></span>
    
    - <span data-ttu-id="a4ad1-268">在“**SQL Server 可用性侦听器 FQDN**”框中，键入在创建可用性组时创建的侦听器 FQDN。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-268">In the **SQL Server Availability Listener FQDN** box, type the FQDN of the listener you created when you created the availability group.</span></span>
    
    - <span data-ttu-id="a4ad1-269">在**SQL Server FQDN**框中，键入 AG，主节点的 FQDN，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-269">In the **SQL Server FQDN** box, type the FQDN of the primary node of the AG, and then click **OK**.</span></span> <span data-ttu-id="a4ad1-270">这应该是此存储的旧镜像的主节点。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-270">This should be the principal of the old mirror for this store.</span></span>
    
12. <span data-ttu-id="a4ad1-271">将新 AG 与前端池相关联。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-271">Associate the new AG with the Front End pool.</span></span>
    
    - <span data-ttu-id="a4ad1-272">在拓扑生成器中，右键单击要与 AG，关联的池，然后单击**编辑属性**。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-272">In Topology Builder, right-click the pool to associate with the AG, and click **Edit Properties**.</span></span>
    
    - <span data-ttu-id="a4ad1-273">在**关联**下的在**SQL Server 存储**框中，选择 AG。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-273">Under **Associations**, in the **SQL Server Store** box, select the AG.</span></span> <span data-ttu-id="a4ad1-274">选择您要将移动到 AG 池中的任何其他数据库的同一组。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-274">Select the same group for any other databases in the pool which you want to move to the AG.</span></span>
    
    - <span data-ttu-id="a4ad1-275">确保所需的所有数据库都设置为 AG 时，请单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-275">When you're sure that all needed databases are set to the AG, click **OK**.</span></span>
    
13. <span data-ttu-id="a4ad1-p143">发布拓扑。从“**操作**”菜单中，单击“**拓扑**”，然后单击“**发布**”。然后在确认页中，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-p143">Publish the topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**.</span></span>
    
14. <span data-ttu-id="a4ad1-279">执行一些最终的步骤，以确保 SQL 登录名位于每个 AlwaysOn 可用性组中的副本。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-279">Perform some final steps to make sure that the SQL logins are on each of the replicas in the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="a4ad1-280">打开拓扑生成器，选择**下载从现有部署的拓扑**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-280">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
    - <span data-ttu-id="a4ad1-281">依次展开 Skype for Business Server、你的拓扑，以及“**SQL Server 存储**”。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-281">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="a4ad1-282">右键单击新 AG 的 SQL 存储，然后单击**编辑属性**。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-282">Right-click the SQL store of the new AG, and click **Edit Properties**.</span></span>
    
    - <span data-ttu-id="a4ad1-283">在**SQL Server FQDN**框中，页的底部的值更改为 AG 的侦听器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-283">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AG.</span></span>
    
    - <span data-ttu-id="a4ad1-p145">发布拓扑。从“**操作**”菜单中，单击“**拓扑**”，然后单击“**发布**”。在确认页上，单击“**下一步**”。然后等待几分钟，让新拓扑进行复制。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-p145">Publish the topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**. Then wait a few minutes for the new topology to replicate.</span></span>
    
    - <span data-ttu-id="a4ad1-288">打开 SQL Server Management Studio，并导航到 AG。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-288">Open SQL Server Management Studio, and navigate to the AG.</span></span> <span data-ttu-id="a4ad1-289">将其故障转移到辅助副本。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-289">Fail it over to a secondary replica.</span></span>
    
    - <span data-ttu-id="a4ad1-290">打开 Skype 业务 Server Management Shell 并键入以下 cmdlet，以在此副本上创建 SQL 登录名：</span><span class="sxs-lookup"><span data-stu-id="a4ad1-290">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
    ```
    Install-CsDatabase -Update
    ```

    - <span data-ttu-id="a4ad1-291">重复前面两个步骤 (故障转移到辅助副本，组，然后使用`Install-CsDatabase -Update`) 的组中的每个副本。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-291">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
    
## <a name="deploy-an-always-on-availability-group-on-an-existing-pool-that-does-not-use-database-mirroring"></a><span data-ttu-id="a4ad1-292">部署始终在可用性上的组，在不使用数据库镜像的现有池</span><span class="sxs-lookup"><span data-stu-id="a4ad1-292">Deploy an Always On Availability Group on an existing pool that does not use database mirroring</span></span>
<span data-ttu-id="a4ad1-293"><a name="BKMK_NoHAPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="a4ad1-293"></span></span>

> [!NOTE]
> <span data-ttu-id="a4ad1-294">如果您要升级到 AG 池承载中央管理存储为您的组织，则必须先移动 CMS 到另一个池升级此池之前。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-294">If the pool you are upgrading to an AG hosts the Central Management store for your organization, you must first move the CMS to another pool before you upgrade this pool.</span></span> <span data-ttu-id="a4ad1-295">可使用 Move-CsManagementServer cmdlet 来移动池。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-295">Use the Move-CsManagementServer cmdlet to move the pool.</span></span> <span data-ttu-id="a4ad1-296">如果您的组织中没有另一个池，可以暂时部署 Standard Edition server，并将 CMS 移动到此服务器，然后再升级到 AG 的池。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-296">If you do not have another pool in your organization, you can deploy a Standard Edition server temporarily and move the CMS to this server before you upgrade your pool to the AG.</span></span> 
  
1. <span data-ttu-id="a4ad1-297">设置将 AG 的一部分的所有数据库服务器上的故障转移群集功能。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-297">Set up the Failover Clustering feature on all the database servers which will be part of the AG.</span></span> <span data-ttu-id="a4ad1-298">在每台服务器上，执行以下操作</span><span class="sxs-lookup"><span data-stu-id="a4ad1-298">On each server, do the following</span></span>
    
   - <span data-ttu-id="a4ad1-299">打开“服务器管理器”，然后单击“**添加角色和功能**”。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-299">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="a4ad1-p149">单击“**下一步**”，直至达到“**选择功能**”框。在这里选中“**故障转移群集**”复选框。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-p149">Click **Next** until you reach the **Select features** box. Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="a4ad1-302">在“**添加故障转移群集所需的功能？**”框中，单击“**添加功能**”。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-302">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="a4ad1-303">单击“**安装**”。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-303">Click **Install**.</span></span>
    
2. <span data-ttu-id="a4ad1-304">验证群集配置。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-304">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="a4ad1-305">在“服务器管理器”中，单击“**工具**”菜单，然后单击“**故障转移群集管理器**”。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-305">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="a4ad1-306">在屏幕右侧的“**操作**”中，单击“**验证配置**”。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-306">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="a4ad1-307">在“**在你开始前**”页上，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-307">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="a4ad1-308">选择要添加到群集的服务器，然后单击“**运行所有测试**”。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-308">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="a4ad1-309">在**摘要**框中，选中向导将报告的任何错误。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-309">In the**Summary** box, check any errors that the wizard reports.</span></span> <span data-ttu-id="a4ad1-310">然后单击“**完成**”完成验证。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-310">Then click **Finish** to complete the validation.</span></span>
    
     <span data-ttu-id="a4ad1-p151">向导可能报告多个警告，尤其是在你未使用共享存储的情况下。你不是必须要使用共享存储。但是，如果看到任何**错误**消息，则必须修正这些问题后才能继续。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-p151">The wizard will probably report several warnings, especially if you are not using shared storage. You are not required to use shared storage. However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
3. <span data-ttu-id="a4ad1-314">创建 Windows Server 故障转移群集 (WSFC)。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-314">Create the Windows Server Failover Cluster (WSFC).</span></span>
    
   - <span data-ttu-id="a4ad1-315">在“**故障转移群集管理**”向导中，右键单击“**故障转移群集管理**”，然后单击“**创建群集**”。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-315">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="a4ad1-316">在“**在你开始前**”页上，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-316">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="a4ad1-p152">添加群集名称和 IP 地址。验证设置后，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-p152">Add the cluster name and IP address. When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="a4ad1-319">在“确认”页上，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-319">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="a4ad1-320">创建群集后，单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-320">After the cluster is created, click **Finish**.</span></span>
    
4. <span data-ttu-id="a4ad1-p153">我们建议配置群集仲裁设置来使用文件共享见证。为此，请使用以下步骤：</span><span class="sxs-lookup"><span data-stu-id="a4ad1-p153">We recommend that you configure the cluster quorum settings to use a file share witness. To do so, use these steps:</span></span>
    
   - <span data-ttu-id="a4ad1-323">右键单击群集名称，单击“**更多操作**”，然后单击“**配置群集仲裁设置**”。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-323">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="a4ad1-324">在“**选择仲裁配置选项**”页上，单击“**选择仲裁见证**”。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-324">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="a4ad1-325">在“**选择仲裁见证**”页中，单击“**配置文件共享见证**”。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-325">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="a4ad1-326">在“**配置文件共享见证**”页中，键入要使用的文件共享的路径，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-326">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="a4ad1-327">在“**确认**”页上，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-327">On the **Confirmation** page, click **Next**.</span></span>
    
5. <span data-ttu-id="a4ad1-328">在群集中的每台服务器上启用 AG 在 SQL Server 配置管理器。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-328">On each server in the cluster, enable AG in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="a4ad1-p154">打开 SQL Server 配置管理器。在屏幕左侧的树中，单击“**SQL Server 服务**”，然后双击“SQL Server 服务”。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-p154">Open SQL Server Configuration Manager. In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="a4ad1-p155">在“**属性**”框中，选择“**AlwaysOn 高可用性**”选项卡。选中“**启用 AlwaysOn 可用性组**”复选框。出现提示时，重新启动 SQL Server 服务。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-p155">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box. Restart the SQL Server service when prompted.</span></span>
    
6. <span data-ttu-id="a4ad1-333">创建可用性组。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-333">Create the availability group.</span></span>
    
   - <span data-ttu-id="a4ad1-334">打开 SQL Server Management Studio，然后连接到 SQL Server 实例。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-334">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
   - <span data-ttu-id="a4ad1-335">在对象资源管理器中，展开**始终在高可用性**文件夹。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-335">In Object Explorer, expand the **Always On High Availability** folder.</span></span> <span data-ttu-id="a4ad1-336">右键单击“**可用性组**”文件夹，然后单击“**新建可用性组向导**”。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-336">Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
   - <span data-ttu-id="a4ad1-337">如果出现“**简介**”页，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-337">If the **Introduction** page appears, click **Next**.</span></span>
    
   - <span data-ttu-id="a4ad1-338">在“**指定可用性组名称**”页中，输入可用性组的名称，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-338">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
   - <span data-ttu-id="a4ad1-339">在选择数据库页中，选择您想要在 AG 中包含的数据库。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-339">In the Select Databases page, select the databases that you want to include in the AG.</span></span> <span data-ttu-id="a4ad1-340">然后单击" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-340">Then click **Next**.</span></span>
    
     <span data-ttu-id="a4ad1-341">不包括**ReportServer**、 **ReportServerTempDB**或持久聊天数据库中 AG，因为它们不受支持此方案中。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-341">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AG, as these are not supported in this scenario.</span></span> <span data-ttu-id="a4ad1-342">您可以在 AG 包括 Business Server 数据库的所有其他 Skype。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-342">You can include all other Skype for Business Server databases in the AG.</span></span>
    
   - <span data-ttu-id="a4ad1-343">在**指定副本**页上，单击**副本**选项卡。然后单击**添加副本**按钮，并连接到其他为 WSFC 的节点加入的 SQL 实例。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-343">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the WSFC.</span></span>
    
   - <span data-ttu-id="a4ad1-p159">对于每个实例，选择“**自动故障转移**”和“**同步提交**”选项。不要选择“**可读辅助副本**”选项。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-p159">For each instance, select the **Automatic Failover** and **Synchronous Commit** options. Do not select the **Readable Secondary** option.</span></span>
    
   - <span data-ttu-id="a4ad1-346">单击“**端点**”选项卡，并验证“**端口号**”设为 5022。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-346">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
   - <span data-ttu-id="a4ad1-p160">单击“**侦听器**”选项卡，选择“**创建可用性组侦听器**”选项。在该选项下面，键入侦听器的名称，然后将“**端口**”设置为 1433（对于此选项，不支持其他端口）。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-p160">Click the **Listener** tab, and select the **Create an availability group listener** option. Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
   - <span data-ttu-id="a4ad1-349">单击“**添加**”，然后在“**IPv4 地址**”框中，提供你的首选虚拟 IP 地址，然后单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-349">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
   - <span data-ttu-id="a4ad1-p161">在“**选择初始数据同步**”页上，选择“完全”，然后指定副本可访问，并且两个副本所使用的 SQL Server 服务帐户有写入权限的文件夹。然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-p161">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for. Then click **Next**.</span></span>
    
     <span data-ttu-id="a4ad1-p162">初始化数据库时，会临时使用此文件共享。如果在处理大数据库，我们建议手动初始化数据库，以防网络带宽容不下数据库备份的大小。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-p162">This file share will be used temporarily when you initialize the databases. If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
     - <span data-ttu-id="a4ad1-354">在“验证”页上，确认所有验证检查都已成功，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-354">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
   - <span data-ttu-id="a4ad1-355">在“**摘要**”页上，验证所有设置，然后单击“完成”。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-355">In the **Summary** page, verify all settings and click Finish.</span></span>
    
7. <span data-ttu-id="a4ad1-356">创建新的存储指定 AG 侦听器。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-356">Create a new store specifying the AG listener.</span></span>
    
   - <span data-ttu-id="a4ad1-357">打开拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-357">Open Topology Builder.</span></span> <span data-ttu-id="a4ad1-358">在拓扑中，展开“**共享组件**”，右键单击“**SQL Server 存储**”，然后单击“**新建 SQL Server 存储**”。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-358">In your topology, expand **Shared Components**, right-click **SQL Server Stores**, and click **New SQL Server Store**.</span></span>
    
   - <span data-ttu-id="a4ad1-359">在“**定义新的 SQL 存储**”页上，先选中“**高可用性设置**”复选框，然后确保 SQL AlwaysOn 可用性组出现在下拉框中。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-359">In the **Define New SQL Store** page, first select the **High Availability Settings** check box, and then make sure that SQL AlwaysOn Availability Groups appears in the drop-down box.</span></span>
    
   - <span data-ttu-id="a4ad1-360">在“**SQL Server 可用性侦听器 FQDN**”框中，键入在创建可用性组时创建的侦听器 FQDN。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-360">In the **SQL Server Availability Listener FQDN** box, type the FQDN of the listener you created when you created the availability group.</span></span>
    
   - <span data-ttu-id="a4ad1-361">在**SQL Server FQDN**框中，键入 AG，主节点的 FQDN，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-361">In the **SQL Server FQDN** box, type the FQDN of the primary node of the AG, and then click **OK**.</span></span>
    
8. <span data-ttu-id="a4ad1-362">将新始终在可用性组与前端池相关联。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-362">Associate the new Always On Availability Group with the Front End pool.</span></span>
    
   - <span data-ttu-id="a4ad1-363">在拓扑生成器中，右键单击要与 AG，关联的池，然后单击**编辑属性**。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-363">In Topology Builder, right-click the pool to associate with the AG, and click **Edit Properties**.</span></span>
    
   - <span data-ttu-id="a4ad1-364">在**关联**下的在**SQL Server 存储**框中，选择 AG。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-364">Under **Associations**, in the **SQL Server Store** box, select the AG.</span></span> <span data-ttu-id="a4ad1-365">选择您要将移动到 AG 池中的任何其他数据库的同一组。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-365">Select the same group for any other databases in the pool which you want to move to the AG.</span></span>
    
   - <span data-ttu-id="a4ad1-366">确保所需的所有数据库都设置为 AG 时，请单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-366">When you're sure that all needed databases are set to the AG, click **OK**.</span></span>
    
9. <span data-ttu-id="a4ad1-p165">发布拓扑。从“**操作**”菜单中，单击“**拓扑**”，然后单击“**发布**”。然后在确认页中，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-p165">Publish the topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**.</span></span>
    
10. <span data-ttu-id="a4ad1-370">执行一些最终的步骤，以确保 SQL 登录名的副本中 AG 个上。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-370">Perform some final steps to make sure that the SQL logins are on each of the replicas in the AG.</span></span>
    
    - <span data-ttu-id="a4ad1-371">打开拓扑生成器，选择**下载从现有部署的拓扑**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-371">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
    - <span data-ttu-id="a4ad1-372">依次展开 Skype for Business Server、你的拓扑，以及“**SQL Server 存储**”。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-372">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="a4ad1-373">右键单击新 AG 的 SQL 存储，然后单击**编辑属性**。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-373">Right-click the SQL store of the new AG, and click **Edit Properties**.</span></span>
    
    - <span data-ttu-id="a4ad1-374">在**SQL Server FQDN**框中，页的底部的值更改为 AG 的侦听器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-374">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AG.</span></span>
    
    - <span data-ttu-id="a4ad1-p167">发布拓扑。从“**操作**”菜单中，单击“**拓扑**”，然后单击“**发布**”。在确认页上，单击“**下一步**”。然后等待几分钟，让新拓扑进行复制。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-p167">Publish the topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**. Then wait a few minutes for the new topology to replicate.</span></span>
    
    - <span data-ttu-id="a4ad1-379">打开 SQL Server Management Studio，并导航到 AG。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-379">Open SQL Server Management Studio, and navigate to the AG.</span></span> <span data-ttu-id="a4ad1-380">将其故障转移到辅助副本。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-380">Fail it over to a secondary replica.</span></span>
    
    - <span data-ttu-id="a4ad1-381">打开 Skype 业务 Server Management Shell 并键入以下 cmdlet，以在此副本上创建 SQL 登录名：</span><span class="sxs-lookup"><span data-stu-id="a4ad1-381">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
      ```
      Install-CsDatabase -Update
      ```

      - <span data-ttu-id="a4ad1-382">重复前面两个步骤 (故障转移到辅助副本，组，然后使用`Install-CsDatabase -Update`) 的组中的每个副本。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-382">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>