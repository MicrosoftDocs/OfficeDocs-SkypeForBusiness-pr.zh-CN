---
title: 在 Skype for Business Server 2015 中的后端服务器上部署 AlwaysOn 可用性组
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 2/14/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c93c01e6-626c-40ad-92dd-373b0fe9189f
description: 部署 （安装） 中您 Skype 的 AlwaysOn 可用性组业务服务器的部署。
ms.openlocfilehash: 858f8cd317ecccde315475bc6489c74d79bf72c6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-an-alwayson-availability-group-on-a-back-end-server-in-skype-for-business-server-2015"></a><span data-ttu-id="435f6-103">在 Skype for Business Server 2015 中的后端服务器上部署 AlwaysOn 可用性组</span><span class="sxs-lookup"><span data-stu-id="435f6-103">Deploy an AlwaysOn Availability Group on a Back End Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="435f6-104">部署 （安装） 中您 Skype 的 AlwaysOn 可用性组业务服务器的部署。</span><span class="sxs-lookup"><span data-stu-id="435f6-104">Deploy (install) an AlwaysOn Availability Group in your Skype for Business Server deployment.</span></span>
  
<span data-ttu-id="435f6-105">AlwaysOn 可用性组的部署方式取决于是否要在一个新的池、 现有池使用镜像或现有池当前具有对后端数据库没有高可用性部署它。</span><span class="sxs-lookup"><span data-stu-id="435f6-105">How you deploy an AlwaysOn Availability Group depends on whether you are deploying it in a new pool, an existing pool that uses mirroring, or an existing pool that currently has no high availability for the Back End database.</span></span>
  
> [!NOTE]
> <span data-ttu-id="435f6-106">不支持使用 AlwaysOn 可用性组与持久聊天服务器角色。</span><span class="sxs-lookup"><span data-stu-id="435f6-106">Using an AlwaysOn Availability Group with a Persistent Chat Server role is not supported.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="435f6-107">AlwaysOn 可用性组的多个实例的实例名称必须相同。</span><span class="sxs-lookup"><span data-stu-id="435f6-107">Instance names for multiple AlwaysOn Availability Group instances must be the same.</span></span> 
  
- [<span data-ttu-id="435f6-108">在新的前端池上部署 AlwaysOn 可用性组</span><span class="sxs-lookup"><span data-stu-id="435f6-108">Deploy an AlwaysOn Availability Group on a new Front End pool</span></span>](alwayson-availability-group.md#BKMK_NewPool_CreateAlwaysOnGroup)
    
- [<span data-ttu-id="435f6-109">在使用数据库镜像的现有池上部署 AlwaysOn 可用性组</span><span class="sxs-lookup"><span data-stu-id="435f6-109">Deploy an AlwaysOn Availability Group on an existing pool that uses database mirroring</span></span>](alwayson-availability-group.md#BKMK_MirroredPool_CreateAlwaysOnGroup)
    
- [<span data-ttu-id="435f6-110">在不使用数据库镜像的现有池上部署 AlwaysOn 可用性组</span><span class="sxs-lookup"><span data-stu-id="435f6-110">Deploy an AlwaysOn Availability Group on an existing pool that does not use database mirroring</span></span>](alwayson-availability-group.md#BKMK_NoHAPool_CreateAlwaysOnGroup)
    
## <a name="deploy-an-alwayson-availability-group-on-a-new-front-end-pool"></a><span data-ttu-id="435f6-111">在新的前端池上部署 AlwaysOn 可用性组</span><span class="sxs-lookup"><span data-stu-id="435f6-111">Deploy an AlwaysOn Availability Group on a new Front End pool</span></span>
<span data-ttu-id="435f6-112"><a name="BKMK_NewPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="435f6-112"></span></span>

1. <span data-ttu-id="435f6-113">Windows 服务器故障转移群集上设置所有数据库服务器将 AlwaysOn 可用性组的一部分。</span><span class="sxs-lookup"><span data-stu-id="435f6-113">Set up Windows Server Failover Clustering on all the database servers which will be part of the AlwaysOn Availability Group.</span></span> <span data-ttu-id="435f6-114">在每台服务器上，执行以下操作</span><span class="sxs-lookup"><span data-stu-id="435f6-114">On each server, do the following</span></span>
    
   - <span data-ttu-id="435f6-115">打开“服务器管理器”，然后单击“**添加角色和功能**”。</span><span class="sxs-lookup"><span data-stu-id="435f6-115">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="435f6-p102">单击“**下一步**”，直至达到“**选择功能**”框。在这里选中“**故障转移群集**”复选框。</span><span class="sxs-lookup"><span data-stu-id="435f6-p102">Click **Next** until you reach the **Select features** box. Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="435f6-118">在“**添加故障转移群集所需的功能？**”框中，单击“**添加功能**”。</span><span class="sxs-lookup"><span data-stu-id="435f6-118">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="435f6-119">单击“**安装**”。</span><span class="sxs-lookup"><span data-stu-id="435f6-119">Click **Install**.</span></span>
    
2. <span data-ttu-id="435f6-120">验证群集配置。</span><span class="sxs-lookup"><span data-stu-id="435f6-120">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="435f6-121">在“服务器管理器”中，单击“**工具**”菜单，然后单击“**故障转移群集管理器**”。</span><span class="sxs-lookup"><span data-stu-id="435f6-121">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="435f6-122">在屏幕右侧的“**操作**”中，单击“**验证配置**”。</span><span class="sxs-lookup"><span data-stu-id="435f6-122">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="435f6-123">在“**在你开始前**”页上，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="435f6-123">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="435f6-124">选择要添加到群集的服务器，然后单击“**运行所有测试**”。</span><span class="sxs-lookup"><span data-stu-id="435f6-124">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="435f6-125">在**摘要**框中，检查该向导将报告任何错误。</span><span class="sxs-lookup"><span data-stu-id="435f6-125">In the**Summary** box, check any errors that the wizard reports.</span></span> <span data-ttu-id="435f6-126">然后单击“**完成**”完成验证。</span><span class="sxs-lookup"><span data-stu-id="435f6-126">Then click **Finish** to complete the validation.</span></span>
    
    <span data-ttu-id="435f6-p104">向导可能报告多个警告，尤其是在你未使用共享存储的情况下。你不是必须要使用共享存储。但是，如果看到任何**错误**消息，则必须修正这些问题后才能继续。</span><span class="sxs-lookup"><span data-stu-id="435f6-p104">The wizard will probably report several warnings, especially if you are not using shared storage. You are not required to use shared storage. However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
3. <span data-ttu-id="435f6-130">创建群集。</span><span class="sxs-lookup"><span data-stu-id="435f6-130">Create the cluster.</span></span>
    
   - <span data-ttu-id="435f6-131">在“**故障转移群集管理**”向导中，右键单击“**故障转移群集管理**”，然后单击“**创建群集**”。</span><span class="sxs-lookup"><span data-stu-id="435f6-131">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="435f6-132">在“**在你开始前**”页上，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="435f6-132">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="435f6-p105">添加群集名称和 IP 地址。验证设置后，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="435f6-p105">Add the cluster name and IP address. When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="435f6-135">在“确认”页上，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="435f6-135">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="435f6-136">创建群集后，单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="435f6-136">After the cluster is created, click **Finish**.</span></span>
    
4. <span data-ttu-id="435f6-p106">我们建议配置群集仲裁设置来使用文件共享见证。为此，请使用以下步骤：</span><span class="sxs-lookup"><span data-stu-id="435f6-p106">We recommend that you configure the cluster quorum settings to use a file share witness. To do so, use these steps:</span></span>
    
   - <span data-ttu-id="435f6-139">右键单击群集名称，单击“**更多操作**”，然后单击“**配置群集仲裁设置**”。</span><span class="sxs-lookup"><span data-stu-id="435f6-139">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="435f6-140">在“**选择仲裁配置选项**”页上，单击“**选择仲裁见证**”。</span><span class="sxs-lookup"><span data-stu-id="435f6-140">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="435f6-141">在“**选择仲裁见证**”页中，单击“**配置文件共享见证**”。</span><span class="sxs-lookup"><span data-stu-id="435f6-141">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="435f6-142">在“**配置文件共享见证**”页中，键入要使用的文件共享的路径，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="435f6-142">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="435f6-143">在“**确认**”页上，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="435f6-143">On the **Confirmation** page, click **Next**.</span></span>
    
5. <span data-ttu-id="435f6-144">在群集中的每台服务器上，在 SQL Server 配置管理器中，启用“始终启用”。</span><span class="sxs-lookup"><span data-stu-id="435f6-144">On each server in the cluster, enable Always On in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="435f6-p107">打开 SQL Server 配置管理器。在屏幕左侧的树中，单击“**SQL Server 服务**”，然后双击“SQL Server 服务”。</span><span class="sxs-lookup"><span data-stu-id="435f6-p107">Open SQL Server Configuration Manager. In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="435f6-p108">在“**属性**”框中，选择“**AlwaysOn 高可用性**”选项卡。选中“**启用 AlwaysOn 可用性组**”复选框。出现提示时，重新启动 SQL Server 服务。</span><span class="sxs-lookup"><span data-stu-id="435f6-p108">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box. Restart the SQL Server service when prompted.</span></span>
    
6. <span data-ttu-id="435f6-149">创建可用性组。</span><span class="sxs-lookup"><span data-stu-id="435f6-149">Create the availability group.</span></span>
    
   - <span data-ttu-id="435f6-150">打开 SQL Server Management Studio，然后连接到 SQL Server 实例。</span><span class="sxs-lookup"><span data-stu-id="435f6-150">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
   - <span data-ttu-id="435f6-p109">在对象资源管理器中，展开“**AlwaysOn 高可用性**”文件夹。右键单击“**可用性组**”文件夹，然后单击“**新建可用性组向导**”。</span><span class="sxs-lookup"><span data-stu-id="435f6-p109">In Object Explorer, expand the **AlwaysOn High Availability** folder. Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
   - <span data-ttu-id="435f6-153">如果出现“**简介**”页，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="435f6-153">If the **Introduction** page appears, click **Next**.</span></span>
    
   - <span data-ttu-id="435f6-154">在“**指定可用性组名称**”页中，输入可用性组的名称，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="435f6-154">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
   - <span data-ttu-id="435f6-155">在选择数据库页上，选择想要包括 AlwaysOn 可用性组中的数据库。</span><span class="sxs-lookup"><span data-stu-id="435f6-155">In the Select Databases page, select the databases that you want to include in the AlwaysOn Availability Group.</span></span> <span data-ttu-id="435f6-156">然后单击" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="435f6-156">Then click **Next**.</span></span>
    
    <span data-ttu-id="435f6-157">不包括**报表服务器**、 **ReportServerTempDB**或持续聊天数据库 AlwaysOn 可用性组中，因为在这种情况下不支持这些。</span><span class="sxs-lookup"><span data-stu-id="435f6-157">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AlwaysOn Availability Group, as these are not supported in this scenario.</span></span> <span data-ttu-id="435f6-158">AlwaysOn 可用性组中可以包含所有其他 Skype 业务服务器数据库。</span><span class="sxs-lookup"><span data-stu-id="435f6-158">You can include all other Skype for Business Server databases in the AlwaysOn Availability Group.</span></span>
    
   - <span data-ttu-id="435f6-159">在“**指定副本**”页上，单击“**副本**”选项卡。然后单击“**添加副本**”按钮，并连接到你作为 Windows Server 故障转移群集的节点加入的其他 SQL 实例。</span><span class="sxs-lookup"><span data-stu-id="435f6-159">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the Windows Server Failover Cluster.</span></span>
    
   - <span data-ttu-id="435f6-p112">对于每个实例，选择“**自动故障转移**”和“**同步提交**”选项。不要选择“**可读辅助副本**”选项。</span><span class="sxs-lookup"><span data-stu-id="435f6-p112">For each instance, select the **Automatic Failover** and **Synchronous Commit** options. Do not select the **Readable Secondary** option.</span></span>
    
   - <span data-ttu-id="435f6-162">单击“**端点**”选项卡，并验证“**端口号**”设为 5022。</span><span class="sxs-lookup"><span data-stu-id="435f6-162">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
   - <span data-ttu-id="435f6-p113">单击“**侦听器**”选项卡，选择“**创建可用性组侦听器**”选项。在该选项下面，键入侦听器的名称，然后将“**端口**”设置为 1433（对于此选项，不支持其他端口）。</span><span class="sxs-lookup"><span data-stu-id="435f6-p113">Click the **Listener** tab, and select the **Create an availability group listener** option. Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
   - <span data-ttu-id="435f6-165">单击“**添加**”，然后在“**IPv4 地址**”框中，提供你的首选虚拟 IP 地址，然后单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="435f6-165">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
   - <span data-ttu-id="435f6-p114">在“**选择初始数据同步**”页上，选择“完全”，然后指定副本可访问，并且两个副本所使用的 SQL Server 服务帐户有写入权限的文件夹。然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="435f6-p114">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for. Then click **Next**.</span></span>
    
    <span data-ttu-id="435f6-p115">初始化数据库时，会临时使用此文件共享。如果在处理大数据库，我们建议手动初始化数据库，以防网络带宽容不下数据库备份的大小。</span><span class="sxs-lookup"><span data-stu-id="435f6-p115">This file share will be used temporarily when you initialize the databases. If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
   - <span data-ttu-id="435f6-170">在“验证”页上，确认所有验证检查都已成功，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="435f6-170">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
   - <span data-ttu-id="435f6-171">在**摘要**页中，验证所有的设置，然后单击完成。</span><span class="sxs-lookup"><span data-stu-id="435f6-171">In the**Summary** page, verify all settings and click Finish.</span></span>
    
7. <span data-ttu-id="435f6-172">使用拓扑生成器来创建前端池，如中所述[创建并发布新的拓扑结构在 Skype 业务服务器 2015年](../../deploy/install/create-and-publish-new-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="435f6-172">Use Topology Builder to create the Front End pool, as explained in [Create and publish new topology in Skype for Business Server 2015](../../deploy/install/create-and-publish-new-topology.md).</span></span> <span data-ttu-id="435f6-173">执行操作时，指定为 SQL 存储池 AlwaysOn 可用性组。</span><span class="sxs-lookup"><span data-stu-id="435f6-173">When you do, specify the AlwaysOn Availability Group as the SQL store for the pool.</span></span>
    
8. <span data-ttu-id="435f6-174">池和 AlwaysOn 可用性组进行部署后，执行一些最终的步骤，以确保 SQL 登录名是每个 AlwaysOn 可用性组的副本。</span><span class="sxs-lookup"><span data-stu-id="435f6-174">After the pool and the AlwaysOn Availability Group are deployed, perform some final steps to make sure that the SQL logins are on each of the replicas in the AlwaysOn Availability Group.</span></span> 
    
   - <span data-ttu-id="435f6-175">打开拓扑生成器、 选择**下载从现有部署的拓扑结构**，并单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="435f6-175">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
   - <span data-ttu-id="435f6-176">依次展开 Skype for Business Server、你的拓扑，以及“**SQL Server 存储**”。</span><span class="sxs-lookup"><span data-stu-id="435f6-176">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="435f6-177">右键单击 SQL 存储新 AlwaysOn 可用性组，然后单击 * * 编辑属性 * *。</span><span class="sxs-lookup"><span data-stu-id="435f6-177">Right-click the SQL store of the new AlwaysOn Availability Group, and click ** Edit Properties**.</span></span>
    
    - <span data-ttu-id="435f6-178">底部的页的**SQL Server FQDN**框中，将值更改侦听器的 AlwaysOn 可用性组的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="435f6-178">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AlwaysOn Availability Group.</span></span>
    
   - <span data-ttu-id="435f6-p118">发布拓扑。从“**操作**”菜单中，单击“**拓扑**”，然后单击“**发布**”。在确认页上，单击“**下一步**”。然后等待几分钟，让新拓扑进行复制。</span><span class="sxs-lookup"><span data-stu-id="435f6-p118">Publish the topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**. Then wait a few minutes for the new topology to replicate.</span></span>
    
   - <span data-ttu-id="435f6-183">打开 SQL Server 管理 Studio，然后定位到 AlwaysOn 可用性组。</span><span class="sxs-lookup"><span data-stu-id="435f6-183">Open SQL Server Management Studio, and navigate to the AlwaysOn Availability Group.</span></span> <span data-ttu-id="435f6-184">将其故障转移到辅助副本。</span><span class="sxs-lookup"><span data-stu-id="435f6-184">Fail it over to a secondary replica.</span></span>
    
   - <span data-ttu-id="435f6-185">打开 Skype 业务服务器管理外壳程序，然后键入以下 cmdlet 上此复制副本创建 SQL 登录名：</span><span class="sxs-lookup"><span data-stu-id="435f6-185">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
   ```
   Install-CsDatabase -Update
   ```

   - <span data-ttu-id="435f6-186">重复前面两个步骤 (这个组故障转移到辅助副本，然后使用`Install-CsDatabase -Update`) 为组中的每个副本。</span><span class="sxs-lookup"><span data-stu-id="435f6-186">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
    
## <a name="deploy-an-alwayson-availability-group-on-an-existing-pool-that-uses-database-mirroring"></a><span data-ttu-id="435f6-187">在使用数据库镜像的现有池上部署 AlwaysOn 可用性组</span><span class="sxs-lookup"><span data-stu-id="435f6-187">Deploy an AlwaysOn Availability Group on an existing pool that uses database mirroring</span></span>
<span data-ttu-id="435f6-188"><a name="BKMK_MirroredPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="435f6-188"></span></span>

> [!NOTE]
> <span data-ttu-id="435f6-189">如果您要升级到 AlwaysOn 可用性组主机集中管理池存储为您的组织，则必须首先移动 CMS 到另一个池之前升级该池。</span><span class="sxs-lookup"><span data-stu-id="435f6-189">If the pool you are upgrading to an AlwaysOn Availability Group hosts the Central Management store for your organization, you must first move the CMS to another pool before you upgrade this pool.</span></span> <span data-ttu-id="435f6-190">可使用 Move-CsManagementServer cmdlet 来移动池。</span><span class="sxs-lookup"><span data-stu-id="435f6-190">Use the Move-CsManagementServer cmdlet to move the pool.</span></span> <span data-ttu-id="435f6-191">如果您的组织中没有另一个池，可以暂时部署标准版服务器并将 CMS 移到此服务器，再到 AlwaysOn 可用性组升级您的池。</span><span class="sxs-lookup"><span data-stu-id="435f6-191">If you do not have another pool in your organization, you can deploy a Standard Edition server temporarily and move the CMS to this server before you upgrade your pool to the AlwaysOn Availability Group.</span></span> 
  
1. <span data-ttu-id="435f6-192">通过为业务服务器管理外壳程序打开 Skype 并键入以下 cmdlet，故障转移与镜像到主节点的所有数据。</span><span class="sxs-lookup"><span data-stu-id="435f6-192">Fail over all data from the mirror to the principal node by opening Skype for Business Server Management Shell and typing the following cmdlet.</span></span>
    
   ```
   Invoke-CsDatabaseFailover -PoolFqdn <Pool FQDN> -DatabaseType <DatabaseType> -NewPrincipal "Primary"
   ```

    <span data-ttu-id="435f6-p121">对池中的每种数据库类型重复此 cmdlet。可以使用下面的 cmdlet 查找存储在此池中的所有数据库类型。</span><span class="sxs-lookup"><span data-stu-id="435f6-p121">Repeat this cmdlet for each database type in the pool. You can use the following cmdlet to find all the database types stored in this pool.</span></span>
     
   ```
   Get-CsPool -Identity <Pool FQDN>
   ```

2. <span data-ttu-id="435f6-195">使用拓扑生成器从池中删除数据库镜像</span><span class="sxs-lookup"><span data-stu-id="435f6-195">Use Topology Builder to remove database mirroring from the pool</span></span>
    
   - <span data-ttu-id="435f6-196">打开拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="435f6-196">Open Topology Builder.</span></span> <span data-ttu-id="435f6-197">在拓扑中，展开“**Enterprise Edition 前端池**”，右键单击池的名称，然后单击“**编辑属性**”。</span><span class="sxs-lookup"><span data-stu-id="435f6-197">In your topology, expand **Enterprise Edition Front End Pools**, right-click the name of the pool, and click **Edit Properties**.</span></span>
    
   - <span data-ttu-id="435f6-198">对于池中的每种 SQL 存储类型，不要选中“**启用 SQL 存储镜像**”复选框。</span><span class="sxs-lookup"><span data-stu-id="435f6-198">For each type of SQL store in the pool, clear the **Enable SQL Store Mirroring** check box.</span></span>
    
3. <span data-ttu-id="435f6-p123">发布更改后的拓扑。从“**操作**”菜单中，单击“**拓扑**”，然后单击“**发布**”。然后在确认页中，单击“**下一步**”</span><span class="sxs-lookup"><span data-stu-id="435f6-p123">Publish the changed topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**</span></span>
    
4. <span data-ttu-id="435f6-202">使用 SQL Server Management Studio 打破镜像。</span><span class="sxs-lookup"><span data-stu-id="435f6-202">Use SQL Server Management Studio to break the mirror.</span></span>
    
   - <span data-ttu-id="435f6-p124">打开 SQL Server Management Studio，转到数据库，右键单击“**任务**”，再单击“**镜像**”。然后单击“**取消镜像**”，再单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="435f6-p124">Open SQL Server Management Studio, navigate to your databases, right-click **Tasks** and click **Mirror**. Then click **Remove Mirroring** and click **OK**.</span></span>
    
   - <span data-ttu-id="435f6-205">重复此过程池中将转换为 AlwaysOn 可用性组中的所有数据库。</span><span class="sxs-lookup"><span data-stu-id="435f6-205">Repeat this for all databases in the pool which will be converted to an AlwaysOn Availability Group.</span></span>
    
5. <span data-ttu-id="435f6-206">Windows 服务器故障转移群集上设置所有数据库服务器将 AlwaysOn 可用性组的一部分。</span><span class="sxs-lookup"><span data-stu-id="435f6-206">Set up Windows Server Failover Clustering on all the database servers which will be part of the AlwaysOn Availability Group.</span></span> <span data-ttu-id="435f6-207">在每台服务器上，执行以下操作</span><span class="sxs-lookup"><span data-stu-id="435f6-207">On each server, do the following</span></span>
    
   - <span data-ttu-id="435f6-208">打开“服务器管理器”，然后单击“**添加角色和功能**”。</span><span class="sxs-lookup"><span data-stu-id="435f6-208">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="435f6-p126">单击“**下一步**”，直至达到“**选择功能**”框。在这里选中“**故障转移群集**”复选框。</span><span class="sxs-lookup"><span data-stu-id="435f6-p126">Click **Next** until you reach the **Select features** box. Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="435f6-211">在“**添加故障转移群集所需的功能？**”框中，单击“**添加功能**”。</span><span class="sxs-lookup"><span data-stu-id="435f6-211">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="435f6-212">单击“**安装**”。</span><span class="sxs-lookup"><span data-stu-id="435f6-212">Click **Install**.</span></span>
    
6. <span data-ttu-id="435f6-213">验证群集配置。</span><span class="sxs-lookup"><span data-stu-id="435f6-213">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="435f6-214">在“服务器管理器”中，单击“**工具**”菜单，然后单击“**故障转移群集管理器**”。</span><span class="sxs-lookup"><span data-stu-id="435f6-214">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="435f6-215">在屏幕右侧的“**操作**”中，单击“**验证配置**”。</span><span class="sxs-lookup"><span data-stu-id="435f6-215">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="435f6-216">在“**在你开始前**”页上，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="435f6-216">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="435f6-217">选择要添加到群集的服务器，然后单击“**运行所有测试**”。</span><span class="sxs-lookup"><span data-stu-id="435f6-217">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="435f6-218">在**摘要**框中，检查该向导将报告任何错误。</span><span class="sxs-lookup"><span data-stu-id="435f6-218">In the**Summary** box, check any errors that the wizard reports.</span></span> <span data-ttu-id="435f6-219">然后单击“**完成**”完成验证。</span><span class="sxs-lookup"><span data-stu-id="435f6-219">Then click **Finish** to complete the validation.</span></span>
    
    <span data-ttu-id="435f6-p128">向导可能报告多个警告，尤其是在你未使用共享存储的情况下。你不是必须要使用共享存储。但是，如果看到任何**错误**消息，则必须修正这些问题后才能继续。</span><span class="sxs-lookup"><span data-stu-id="435f6-p128">The wizard will probably report several warnings, especially if you are not using shared storage. You are not required to use shared storage. However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
7. <span data-ttu-id="435f6-223">创建群集。</span><span class="sxs-lookup"><span data-stu-id="435f6-223">Create the cluster.</span></span>
    
   - <span data-ttu-id="435f6-224">在“**故障转移群集管理**”向导中，右键单击“**故障转移群集管理**”，然后单击“**创建群集**”。</span><span class="sxs-lookup"><span data-stu-id="435f6-224">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="435f6-225">在“**在你开始前**”页上，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="435f6-225">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="435f6-p129">添加群集名称和 IP 地址。验证设置后，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="435f6-p129">Add the cluster name and IP address. When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="435f6-228">在“确认”页上，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="435f6-228">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="435f6-229">创建群集后，单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="435f6-229">After the cluster is created, click **Finish**.</span></span>
    
8. <span data-ttu-id="435f6-p130">我们建议配置群集仲裁设置来使用文件共享见证。为此，请使用以下步骤：</span><span class="sxs-lookup"><span data-stu-id="435f6-p130">We recommend that you configure the cluster quorum settings to use a file share witness. To do so, use these steps:</span></span>
    
   - <span data-ttu-id="435f6-232">右键单击群集名称，单击“**更多操作**”，然后单击“**配置群集仲裁设置**”。</span><span class="sxs-lookup"><span data-stu-id="435f6-232">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="435f6-233">在“**选择仲裁配置选项**”页上，单击“**选择仲裁见证**”。</span><span class="sxs-lookup"><span data-stu-id="435f6-233">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="435f6-234">在“**选择仲裁见证**”页中，单击“**配置文件共享见证**”。</span><span class="sxs-lookup"><span data-stu-id="435f6-234">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="435f6-235">在“**配置文件共享见证**”页中，键入要使用的文件共享的路径，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="435f6-235">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="435f6-236">在“**确认**”页上，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="435f6-236">On the **Confirmation** page, click **Next**.</span></span>
    
9. <span data-ttu-id="435f6-237">在群集中的每台服务器上，在 SQL Server 配置管理器中，启用“始终启用”。</span><span class="sxs-lookup"><span data-stu-id="435f6-237">On each server in the cluster, enable Always On in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="435f6-p131">打开 SQL Server 配置管理器。在屏幕左侧的树中，单击“**SQL Server 服务**”，然后双击“SQL Server 服务”。</span><span class="sxs-lookup"><span data-stu-id="435f6-p131">Open SQL Server Configuration Manager. In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="435f6-p132">在“**属性**”框中，选择“**AlwaysOn 高可用性**”选项卡。选中“**启用 AlwaysOn 可用性组**”复选框。出现提示时，重新启动 SQL Server 服务。</span><span class="sxs-lookup"><span data-stu-id="435f6-p132">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box. Restart the SQL Server service when prompted.</span></span>
    
10. <span data-ttu-id="435f6-242">创建可用性组。</span><span class="sxs-lookup"><span data-stu-id="435f6-242">Create the availability group.</span></span>
    
    - <span data-ttu-id="435f6-243">打开 SQL Server Management Studio，然后连接到 SQL Server 实例。</span><span class="sxs-lookup"><span data-stu-id="435f6-243">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
    - <span data-ttu-id="435f6-p133">在对象资源管理器中，展开“**AlwaysOn 高可用性**”文件夹。右键单击“**可用性组**”文件夹，然后单击“**新建可用性组向导**”。</span><span class="sxs-lookup"><span data-stu-id="435f6-p133">In Object Explorer, expand the **AlwaysOn High Availability** folder. Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
    - <span data-ttu-id="435f6-246">如果出现“**简介**”页，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="435f6-246">If the **Introduction** page appears, click **Next**.</span></span>
    
    - <span data-ttu-id="435f6-247">在“**指定可用性组名称**”页中，输入可用性组的名称，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="435f6-247">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
    - <span data-ttu-id="435f6-248">在选择数据库页上，选择想要包括 AlwaysOn 可用性组中的数据库。</span><span class="sxs-lookup"><span data-stu-id="435f6-248">In the Select Databases page, select the databases that you want to include in the AlwaysOn Availability Group.</span></span> <span data-ttu-id="435f6-249">然后单击" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="435f6-249">Then click **Next**.</span></span>
    
    <span data-ttu-id="435f6-250">不包括**报表服务器**、 **ReportServerTempDB**或持续聊天数据库 AlwaysOn 可用性组中，因为在这种情况下不支持这些。</span><span class="sxs-lookup"><span data-stu-id="435f6-250">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AlwaysOn Availability Group, as these are not supported in this scenario.</span></span> <span data-ttu-id="435f6-251">AlwaysOn 可用性组中可以包含所有其他 Skype 业务服务器数据库。</span><span class="sxs-lookup"><span data-stu-id="435f6-251">You can include all other Skype for Business Server databases in the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="435f6-252">在“**指定副本**”页上，单击“**副本**”选项卡。然后单击“**添加副本**”按钮，并连接到你作为 Windows Server 故障转移群集的节点加入的其他 SQL 实例。</span><span class="sxs-lookup"><span data-stu-id="435f6-252">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the Windows Server Failover Cluster.</span></span>
    
    - <span data-ttu-id="435f6-p136">对于每个实例，选择“**自动故障转移**”和“**同步提交**”选项。不要选择“**可读辅助副本**”选项。</span><span class="sxs-lookup"><span data-stu-id="435f6-p136">For each instance, select the **Automatic Failover** and **Synchronous Commit** options. Do not select the **Readable Secondary** option.</span></span>
    
    - <span data-ttu-id="435f6-255">单击“**端点**”选项卡，并验证“**端口号**”设为 5022。</span><span class="sxs-lookup"><span data-stu-id="435f6-255">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
     - <span data-ttu-id="435f6-p137">单击“**侦听器**”选项卡，选择“**创建可用性组侦听器**”选项。在该选项下面，键入侦听器的名称，然后将“**端口**”设置为 1433（对于此选项，不支持其他端口）。</span><span class="sxs-lookup"><span data-stu-id="435f6-p137">Click the **Listener** tab, and select the **Create an availability group listener** option. Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
    - <span data-ttu-id="435f6-258">单击“**添加**”，然后在“**IPv4 地址**”框中，提供你的首选虚拟 IP 地址，然后单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="435f6-258">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
    - <span data-ttu-id="435f6-p138">在“**选择初始数据同步**”页上，选择“完全”，然后指定副本可访问，并且两个副本所使用的 SQL Server 服务帐户有写入权限的文件夹。然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="435f6-p138">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for. Then click **Next**.</span></span>
    
    <span data-ttu-id="435f6-p139">初始化数据库时，会临时使用此文件共享。如果在处理大数据库，我们建议手动初始化数据库，以防网络带宽容不下数据库备份的大小。</span><span class="sxs-lookup"><span data-stu-id="435f6-p139">This file share will be used temporarily when you initialize the databases. If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
    - <span data-ttu-id="435f6-263">在“验证”页上，确认所有验证检查都已成功，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="435f6-263">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
    - <span data-ttu-id="435f6-264">在“**摘要**”页上，验证所有设置，然后单击“完成”。</span><span class="sxs-lookup"><span data-stu-id="435f6-264">In the **Summary** page, verify all settings and click Finish.</span></span>
    
11. <span data-ttu-id="435f6-265">创建新的存储指定 AlwaysOn 可用性组侦听程序，并作为主节点的 AlwaysOn 可用性组指定旧镜像的主体。</span><span class="sxs-lookup"><span data-stu-id="435f6-265">Create a new store specifying the AlwaysOn Availability Group listener, and specifying the principal of the old mirror as the primary node of the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="435f6-266">打开拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="435f6-266">Open Topology Builder.</span></span> <span data-ttu-id="435f6-267">在拓扑中，展开“**共享组件**”，右键单击“**SQL Server 存储**”，然后单击“**新建 SQL Server 存储**”。</span><span class="sxs-lookup"><span data-stu-id="435f6-267">In your topology, expand **Shared Components**, right-click **SQL Server Stores**, and click **New SQL Server Store**.</span></span>
    
    - <span data-ttu-id="435f6-268">在“**定义新的 SQL 存储**”页上，先选中“**高可用性设置**”复选框，然后确保 SQL AlwaysOn 可用性组出现在下拉框中。</span><span class="sxs-lookup"><span data-stu-id="435f6-268">In the **Define New SQL Store** page, first select the **High Availability Settings** check box, and then make sure that SQL AlwaysOn Availability Groups appears in the drop-down box.</span></span>
    
    - <span data-ttu-id="435f6-269">在“**SQL Server 可用性侦听器 FQDN**”框中，键入在创建可用性组时创建的侦听器 FQDN。</span><span class="sxs-lookup"><span data-stu-id="435f6-269">In the **SQL Server Availability Listener FQDN** box, type the FQDN of the listener you created when you created the availability group.</span></span>
    
    - <span data-ttu-id="435f6-270">**SQL Server FQDN**的框中，键入 AlwaysOn 可用性组，主节点的 FQDN，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="435f6-270">In the **SQL Server FQDN** box, type the FQDN of the primary node of the AlwaysOn Availability Group, and then click **OK**.</span></span> <span data-ttu-id="435f6-271">这应该是此存储的旧镜像的主节点。</span><span class="sxs-lookup"><span data-stu-id="435f6-271">This should be the principal of the old mirror for this store.</span></span>
    
12. <span data-ttu-id="435f6-272">将新的 AlwaysOn 可用性组与前端池相关联。</span><span class="sxs-lookup"><span data-stu-id="435f6-272">Associate the new AlwaysOn Availability Group with the Front End pool.</span></span>
    
    - <span data-ttu-id="435f6-273">拓扑生成器中右键单击该池与 AlwaysOn 可用性组，并单击**编辑属性**。</span><span class="sxs-lookup"><span data-stu-id="435f6-273">In Topology Builder, right-click the pool to associate with the AlwaysOn Availability Group, and click **Edit Properties**.</span></span>
    
    - <span data-ttu-id="435f6-274">在**关联**， **SQL Server 存储**框中，选择 AlwaysOn 可用性组。</span><span class="sxs-lookup"><span data-stu-id="435f6-274">Under **Associations**, in the **SQL Server Store** box, select the AlwaysOn Availability Group.</span></span> <span data-ttu-id="435f6-275">选择要移到 AlwaysOn 可用性组池中的任何其他数据库的同一组。</span><span class="sxs-lookup"><span data-stu-id="435f6-275">Select the same group for any other databases in the pool which you want to move to the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="435f6-276">确保所有所需的数据库设置为 AlwaysOn 可用性组时，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="435f6-276">When you're sure that all needed databases are set to the AlwaysOn Availability Group, click **OK**.</span></span>
    
13. <span data-ttu-id="435f6-p143">发布拓扑。从“**操作**”菜单中，单击“**拓扑**”，然后单击“**发布**”。然后在确认页中，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="435f6-p143">Publish the topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**.</span></span>
    
14. <span data-ttu-id="435f6-280">执行一些最终的步骤，以确保每个 AlwaysOn 可用性组的副本上的 SQL 登录名。</span><span class="sxs-lookup"><span data-stu-id="435f6-280">Perform some final steps to make sure that the SQL logins are on each of the replicas in the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="435f6-281">打开拓扑生成器、 选择**下载从现有部署的拓扑结构**，并单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="435f6-281">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
    - <span data-ttu-id="435f6-282">依次展开 Skype for Business Server、你的拓扑，以及“**SQL Server 存储**”。</span><span class="sxs-lookup"><span data-stu-id="435f6-282">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="435f6-283">右键单击 SQL 存储新 AlwaysOn 可用性组，并单击**编辑属性**。</span><span class="sxs-lookup"><span data-stu-id="435f6-283">Right-click the SQL store of the new AlwaysOn Availability Group, and click **Edit Properties**.</span></span>
    
    - <span data-ttu-id="435f6-284">底部的页的**SQL Server FQDN**框中，将值更改侦听器的 AlwaysOn 可用性组的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="435f6-284">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="435f6-p145">发布拓扑。从“**操作**”菜单中，单击“**拓扑**”，然后单击“**发布**”。在确认页上，单击“**下一步**”。然后等待几分钟，让新拓扑进行复制。</span><span class="sxs-lookup"><span data-stu-id="435f6-p145">Publish the topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**. Then wait a few minutes for the new topology to replicate.</span></span>
    
    - <span data-ttu-id="435f6-289">打开 SQL Server 管理 Studio，然后定位到 AlwaysOn 可用性组。</span><span class="sxs-lookup"><span data-stu-id="435f6-289">Open SQL Server Management Studio, and navigate to the AlwaysOn Availability Group.</span></span> <span data-ttu-id="435f6-290">将其故障转移到辅助副本。</span><span class="sxs-lookup"><span data-stu-id="435f6-290">Fail it over to a secondary replica.</span></span>
    
    - <span data-ttu-id="435f6-291">打开 Skype 业务服务器管理外壳程序，然后键入以下 cmdlet 上此复制副本创建 SQL 登录名：</span><span class="sxs-lookup"><span data-stu-id="435f6-291">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
    ```
    Install-CsDatabase -Update
    ```

    - <span data-ttu-id="435f6-292">重复前面两个步骤 (这个组故障转移到辅助副本，然后使用`Install-CsDatabase -Update`) 为组中的每个副本。</span><span class="sxs-lookup"><span data-stu-id="435f6-292">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
    
## <a name="deploy-an-alwayson-availability-group-on-an-existing-pool-that-does-not-use-database-mirroring"></a><span data-ttu-id="435f6-293">在不使用数据库镜像的现有池上部署 AlwaysOn 可用性组</span><span class="sxs-lookup"><span data-stu-id="435f6-293">Deploy an AlwaysOn Availability Group on an existing pool that does not use database mirroring</span></span>
<span data-ttu-id="435f6-294"><a name="BKMK_NoHAPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="435f6-294"></span></span>

> [!NOTE]
> <span data-ttu-id="435f6-295">如果您要升级到 AlwaysOn 可用性组主机集中管理池存储为您的组织，则必须首先移动 CMS 到另一个池之前升级该池。</span><span class="sxs-lookup"><span data-stu-id="435f6-295">If the pool you are upgrading to an AlwaysOn Availability Group hosts the Central Management store for your organization, you must first move the CMS to another pool before you upgrade this pool.</span></span> <span data-ttu-id="435f6-296">可使用 Move-CsManagementServer cmdlet 来移动池。</span><span class="sxs-lookup"><span data-stu-id="435f6-296">Use the Move-CsManagementServer cmdlet to move the pool.</span></span> <span data-ttu-id="435f6-297">如果您的组织中没有另一个池，可以暂时部署标准版服务器并将 CMS 移到此服务器，再到 AlwaysOn 可用性组升级您的池。</span><span class="sxs-lookup"><span data-stu-id="435f6-297">If you do not have another pool in your organization, you can deploy a Standard Edition server temporarily and move the CMS to this server before you upgrade your pool to the AlwaysOn Availability Group.</span></span> 
  
1. <span data-ttu-id="435f6-298">Windows 服务器故障转移群集上设置所有数据库服务器将 AlwaysOn 可用性组的一部分。</span><span class="sxs-lookup"><span data-stu-id="435f6-298">Set up Windows Server Failover Clustering on all the database servers which will be part of the AlwaysOn Availability Group.</span></span> <span data-ttu-id="435f6-299">在每台服务器上，执行以下操作</span><span class="sxs-lookup"><span data-stu-id="435f6-299">On each server, do the following</span></span>
    
   - <span data-ttu-id="435f6-300">打开“服务器管理器”，然后单击“**添加角色和功能**”。</span><span class="sxs-lookup"><span data-stu-id="435f6-300">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="435f6-p149">单击“**下一步**”，直至达到“**选择功能**”框。在这里选中“**故障转移群集**”复选框。</span><span class="sxs-lookup"><span data-stu-id="435f6-p149">Click **Next** until you reach the **Select features** box. Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="435f6-303">在“**添加故障转移群集所需的功能？**”框中，单击“**添加功能**”。</span><span class="sxs-lookup"><span data-stu-id="435f6-303">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="435f6-304">单击“**安装**”。</span><span class="sxs-lookup"><span data-stu-id="435f6-304">Click **Install**.</span></span>
    
2. <span data-ttu-id="435f6-305">验证群集配置。</span><span class="sxs-lookup"><span data-stu-id="435f6-305">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="435f6-306">在“服务器管理器”中，单击“**工具**”菜单，然后单击“**故障转移群集管理器**”。</span><span class="sxs-lookup"><span data-stu-id="435f6-306">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="435f6-307">在屏幕右侧的“**操作**”中，单击“**验证配置**”。</span><span class="sxs-lookup"><span data-stu-id="435f6-307">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="435f6-308">在“**在你开始前**”页上，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="435f6-308">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="435f6-309">选择要添加到群集的服务器，然后单击“**运行所有测试**”。</span><span class="sxs-lookup"><span data-stu-id="435f6-309">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="435f6-310">在**摘要**框中，检查该向导将报告任何错误。</span><span class="sxs-lookup"><span data-stu-id="435f6-310">In the**Summary** box, check any errors that the wizard reports.</span></span> <span data-ttu-id="435f6-311">然后单击“**完成**”完成验证。</span><span class="sxs-lookup"><span data-stu-id="435f6-311">Then click **Finish** to complete the validation.</span></span>
    
    <span data-ttu-id="435f6-p151">向导可能报告多个警告，尤其是在你未使用共享存储的情况下。你不是必须要使用共享存储。但是，如果看到任何**错误**消息，则必须修正这些问题后才能继续。</span><span class="sxs-lookup"><span data-stu-id="435f6-p151">The wizard will probably report several warnings, especially if you are not using shared storage. You are not required to use shared storage. However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
3. <span data-ttu-id="435f6-315">创建群集。</span><span class="sxs-lookup"><span data-stu-id="435f6-315">Create the cluster.</span></span>
    
   - <span data-ttu-id="435f6-316">在“**故障转移群集管理**”向导中，右键单击“**故障转移群集管理**”，然后单击“**创建群集**”。</span><span class="sxs-lookup"><span data-stu-id="435f6-316">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="435f6-317">在“**在你开始前**”页上，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="435f6-317">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="435f6-p152">添加群集名称和 IP 地址。验证设置后，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="435f6-p152">Add the cluster name and IP address. When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="435f6-320">在“确认”页上，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="435f6-320">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="435f6-321">创建群集后，单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="435f6-321">After the cluster is created, click **Finish**.</span></span>
    
4. <span data-ttu-id="435f6-p153">我们建议配置群集仲裁设置来使用文件共享见证。为此，请使用以下步骤：</span><span class="sxs-lookup"><span data-stu-id="435f6-p153">We recommend that you configure the cluster quorum settings to use a file share witness. To do so, use these steps:</span></span>
    
   - <span data-ttu-id="435f6-324">右键单击群集名称，单击“**更多操作**”，然后单击“**配置群集仲裁设置**”。</span><span class="sxs-lookup"><span data-stu-id="435f6-324">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="435f6-325">在“**选择仲裁配置选项**”页上，单击“**选择仲裁见证**”。</span><span class="sxs-lookup"><span data-stu-id="435f6-325">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="435f6-326">在“**选择仲裁见证**”页中，单击“**配置文件共享见证**”。</span><span class="sxs-lookup"><span data-stu-id="435f6-326">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="435f6-327">在“**配置文件共享见证**”页中，键入要使用的文件共享的路径，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="435f6-327">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="435f6-328">在“**确认**”页上，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="435f6-328">On the **Confirmation** page, click **Next**.</span></span>
    
5. <span data-ttu-id="435f6-329">在群集中的每台服务器上，在 SQL Server 配置管理器中，启用“始终启用”。</span><span class="sxs-lookup"><span data-stu-id="435f6-329">On each server in the cluster, enable Always On in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="435f6-p154">打开 SQL Server 配置管理器。在屏幕左侧的树中，单击“**SQL Server 服务**”，然后双击“SQL Server 服务”。</span><span class="sxs-lookup"><span data-stu-id="435f6-p154">Open SQL Server Configuration Manager. In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="435f6-p155">在“**属性**”框中，选择“**AlwaysOn 高可用性**”选项卡。选中“**启用 AlwaysOn 可用性组**”复选框。出现提示时，重新启动 SQL Server 服务。</span><span class="sxs-lookup"><span data-stu-id="435f6-p155">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box. Restart the SQL Server service when prompted.</span></span>
    
6. <span data-ttu-id="435f6-334">创建可用性组。</span><span class="sxs-lookup"><span data-stu-id="435f6-334">Create the availability group.</span></span>
    
   - <span data-ttu-id="435f6-335">打开 SQL Server Management Studio，然后连接到 SQL Server 实例。</span><span class="sxs-lookup"><span data-stu-id="435f6-335">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
   - <span data-ttu-id="435f6-p156">在对象资源管理器中，展开“**AlwaysOn 高可用性**”文件夹。右键单击“**可用性组**”文件夹，然后单击“**新建可用性组向导**”。</span><span class="sxs-lookup"><span data-stu-id="435f6-p156">In Object Explorer, expand the **AlwaysOn High Availability** folder. Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
   - <span data-ttu-id="435f6-338">如果出现“**简介**”页，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="435f6-338">If the **Introduction** page appears, click **Next**.</span></span>
    
   - <span data-ttu-id="435f6-339">在“**指定可用性组名称**”页中，输入可用性组的名称，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="435f6-339">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
   - <span data-ttu-id="435f6-340">在选择数据库页上，选择想要包括 AlwaysOn 可用性组中的数据库。</span><span class="sxs-lookup"><span data-stu-id="435f6-340">In the Select Databases page, select the databases that you want to include in the AlwaysOn Availability Group.</span></span> <span data-ttu-id="435f6-341">然后单击" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="435f6-341">Then click **Next**.</span></span>
    
    <span data-ttu-id="435f6-342">不包括**报表服务器**、 **ReportServerTempDB**或持续聊天数据库 AlwaysOn 可用性组中，因为在这种情况下不支持这些。</span><span class="sxs-lookup"><span data-stu-id="435f6-342">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AlwaysOn Availability Group, as these are not supported in this scenario.</span></span> <span data-ttu-id="435f6-343">AlwaysOn 可用性组中可以包含所有其他 Skype 业务服务器数据库。</span><span class="sxs-lookup"><span data-stu-id="435f6-343">You can include all other Skype for Business Server databases in the AlwaysOn Availability Group.</span></span>
    
   - <span data-ttu-id="435f6-344">在“**指定副本**”页上，单击“**副本**”选项卡。然后单击“**添加副本**”按钮，并连接到你作为 Windows Server 故障转移群集的节点加入的其他 SQL 实例。</span><span class="sxs-lookup"><span data-stu-id="435f6-344">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the Windows Server Failover Cluster.</span></span>
    
   - <span data-ttu-id="435f6-p159">对于每个实例，选择“**自动故障转移**”和“**同步提交**”选项。不要选择“**可读辅助副本**”选项。</span><span class="sxs-lookup"><span data-stu-id="435f6-p159">For each instance, select the **Automatic Failover** and **Synchronous Commit** options. Do not select the **Readable Secondary** option.</span></span>
    
   - <span data-ttu-id="435f6-347">单击“**端点**”选项卡，并验证“**端口号**”设为 5022。</span><span class="sxs-lookup"><span data-stu-id="435f6-347">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
   - <span data-ttu-id="435f6-p160">单击“**侦听器**”选项卡，选择“**创建可用性组侦听器**”选项。在该选项下面，键入侦听器的名称，然后将“**端口**”设置为 1433（对于此选项，不支持其他端口）。</span><span class="sxs-lookup"><span data-stu-id="435f6-p160">Click the **Listener** tab, and select the **Create an availability group listener** option. Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
   - <span data-ttu-id="435f6-350">单击“**添加**”，然后在“**IPv4 地址**”框中，提供你的首选虚拟 IP 地址，然后单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="435f6-350">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
   - <span data-ttu-id="435f6-p161">在“**选择初始数据同步**”页上，选择“完全”，然后指定副本可访问，并且两个副本所使用的 SQL Server 服务帐户有写入权限的文件夹。然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="435f6-p161">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for. Then click **Next**.</span></span>
    
    <span data-ttu-id="435f6-p162">初始化数据库时，会临时使用此文件共享。如果在处理大数据库，我们建议手动初始化数据库，以防网络带宽容不下数据库备份的大小。</span><span class="sxs-lookup"><span data-stu-id="435f6-p162">This file share will be used temporarily when you initialize the databases. If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
    - <span data-ttu-id="435f6-355">在“验证”页上，确认所有验证检查都已成功，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="435f6-355">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
   - <span data-ttu-id="435f6-356">在“**摘要**”页上，验证所有设置，然后单击“完成”。</span><span class="sxs-lookup"><span data-stu-id="435f6-356">In the **Summary** page, verify all settings and click Finish.</span></span>
    
7. <span data-ttu-id="435f6-357">创建新的存储指定 AlwaysOn 可用性组侦听器。</span><span class="sxs-lookup"><span data-stu-id="435f6-357">Create a new store specifying the AlwaysOn Availability Group listener.</span></span>
    
   - <span data-ttu-id="435f6-358">打开拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="435f6-358">Open Topology Builder.</span></span> <span data-ttu-id="435f6-359">在拓扑中，展开“**共享组件**”，右键单击“**SQL Server 存储**”，然后单击“**新建 SQL Server 存储**”。</span><span class="sxs-lookup"><span data-stu-id="435f6-359">In your topology, expand **Shared Components**, right-click **SQL Server Stores**, and click **New SQL Server Store**.</span></span>
    
   - <span data-ttu-id="435f6-360">在“**定义新的 SQL 存储**”页上，先选中“**高可用性设置**”复选框，然后确保 SQL AlwaysOn 可用性组出现在下拉框中。</span><span class="sxs-lookup"><span data-stu-id="435f6-360">In the **Define New SQL Store** page, first select the **High Availability Settings** check box, and then make sure that SQL AlwaysOn Availability Groups appears in the drop-down box.</span></span>
    
   - <span data-ttu-id="435f6-361">在“**SQL Server 可用性侦听器 FQDN**”框中，键入在创建可用性组时创建的侦听器 FQDN。</span><span class="sxs-lookup"><span data-stu-id="435f6-361">In the **SQL Server Availability Listener FQDN** box, type the FQDN of the listener you created when you created the availability group.</span></span>
    
   - <span data-ttu-id="435f6-362">**SQL Server FQDN**的框中，键入 AlwaysOn 可用性组，主节点的 FQDN，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="435f6-362">In the **SQL Server FQDN** box, type the FQDN of the primary node of the AlwaysOn Availability Group, and then click **OK**.</span></span>
    
8. <span data-ttu-id="435f6-363">将新的 AlwaysOn 可用性组与前端池相关联。</span><span class="sxs-lookup"><span data-stu-id="435f6-363">Associate the new AlwaysOn Availability Group with the Front End pool.</span></span>
    
   - <span data-ttu-id="435f6-364">拓扑生成器中右键单击该池与 AlwaysOn 可用性组，并单击**编辑属性**。</span><span class="sxs-lookup"><span data-stu-id="435f6-364">In Topology Builder, right-click the pool to associate with the AlwaysOn Availability Group, and click **Edit Properties**.</span></span>
    
   - <span data-ttu-id="435f6-365">在**关联**， **SQL Server 存储**框中，选择 AlwaysOn 可用性组。</span><span class="sxs-lookup"><span data-stu-id="435f6-365">Under **Associations**, in the **SQL Server Store** box, select the AlwaysOn Availability Group.</span></span> <span data-ttu-id="435f6-366">选择要移到 AlwaysOn 可用性组池中的任何其他数据库的同一组。</span><span class="sxs-lookup"><span data-stu-id="435f6-366">Select the same group for any other databases in the pool which you want to move to the AlwaysOn Availability Group.</span></span>
    
   - <span data-ttu-id="435f6-367">确保所有所需的数据库设置为 AlwaysOn 可用性组时，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="435f6-367">When you're sure that all needed databases are set to the AlwaysOn Availability Group, click **OK**.</span></span>
    
9. <span data-ttu-id="435f6-p165">发布拓扑。从“**操作**”菜单中，单击“**拓扑**”，然后单击“**发布**”。然后在确认页中，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="435f6-p165">Publish the topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**.</span></span>
    
10. <span data-ttu-id="435f6-371">执行一些最终的步骤，以确保每个 AlwaysOn 可用性组的副本上的 SQL 登录名。</span><span class="sxs-lookup"><span data-stu-id="435f6-371">Perform some final steps to make sure that the SQL logins are on each of the replicas in the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="435f6-372">打开拓扑生成器、 选择**下载从现有部署的拓扑结构**，并单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="435f6-372">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
    - <span data-ttu-id="435f6-373">依次展开 Skype for Business Server、你的拓扑，以及“**SQL Server 存储**”。</span><span class="sxs-lookup"><span data-stu-id="435f6-373">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="435f6-374">右键单击 SQL 存储新 AlwaysOn 可用性组，然后单击 * * 编辑属性 * *。</span><span class="sxs-lookup"><span data-stu-id="435f6-374">Right-click the SQL store of the new AlwaysOn Availability Group, and click ** Edit Properties**.</span></span>
    
    - <span data-ttu-id="435f6-375">底部的页的**SQL Server FQDN**框中，将值更改侦听器的 AlwaysOn 可用性组的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="435f6-375">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="435f6-p167">发布拓扑。从“**操作**”菜单中，单击“**拓扑**”，然后单击“**发布**”。在确认页上，单击“**下一步**”。然后等待几分钟，让新拓扑进行复制。</span><span class="sxs-lookup"><span data-stu-id="435f6-p167">Publish the topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**. Then wait a few minutes for the new topology to replicate.</span></span>
    
    - <span data-ttu-id="435f6-380">打开 SQL Server 管理 Studio，然后定位到 AlwaysOn 可用性组。</span><span class="sxs-lookup"><span data-stu-id="435f6-380">Open SQL Server Management Studio, and navigate to the AlwaysOn Availability Group.</span></span> <span data-ttu-id="435f6-381">将其故障转移到辅助副本。</span><span class="sxs-lookup"><span data-stu-id="435f6-381">Fail it over to a secondary replica.</span></span>
    
    - <span data-ttu-id="435f6-382">打开 Skype 业务服务器管理外壳程序，然后键入以下 cmdlet 上此复制副本创建 SQL 登录名：</span><span class="sxs-lookup"><span data-stu-id="435f6-382">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
     ```
     Install-CsDatabase -Update
     ```

     - <span data-ttu-id="435f6-383">重复前面两个步骤 (这个组故障转移到辅助副本，然后使用`Install-CsDatabase -Update`) 为组中的每个副本。</span><span class="sxs-lookup"><span data-stu-id="435f6-383">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
    

