---
title: 在 Skype for Business Server 的后端服务器上部署 Always On 可用性组
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c93c01e6-626c-40ad-92dd-373b0fe9189f
description: 部署 (Skype for Business Server) Always On 可用性组。
ms.openlocfilehash: 83565efe850570ac5ab9a0695757e708f3eae566
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830652"
---
# <a name="deploy-an-always-on-availability-group-on-a-back-end-server-in-skype-for-business-server"></a><span data-ttu-id="d2c3f-103">在 Skype for Business Server 的后端服务器上部署 Always On 可用性组</span><span class="sxs-lookup"><span data-stu-id="d2c3f-103">Deploy an Always On Availability Group on a Back End Server in Skype for Business Server</span></span>
 
<span data-ttu-id="d2c3f-104">部署 (Skype for Business Server) Always On 可用性组 (AG) 安装。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-104">Deploy (install) an Always On Availability Group (AG) in your Skype for Business Server deployment.</span></span>
  
<span data-ttu-id="d2c3f-105">如何部署 AG 取决于是将其部署到新池、使用镜像的现有池，还是当前对后端数据库没有高可用性的现有池。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-105">How you deploy an AG depends on whether you are deploying it in a new pool, an existing pool that uses mirroring, or an existing pool that currently has no high availability for the Back End database.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d2c3f-106">不支持将 AG 与持久聊天服务器角色一同使用。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-106">Using an AG with a Persistent Chat Server role is not supported.</span></span> 
  
- [<span data-ttu-id="d2c3f-107">在新的前端池上部署 Always On 可用性组</span><span class="sxs-lookup"><span data-stu-id="d2c3f-107">Deploy an Always On Availability Group on a new Front End pool</span></span>](alwayson-availability-group.md#BKMK_NewPool_CreateAlwaysOnGroup)
    
- [<span data-ttu-id="d2c3f-108">在使用数据库镜像的现有池上部署 Always On 可用性组</span><span class="sxs-lookup"><span data-stu-id="d2c3f-108">Deploy an Always On Availability Group on an existing pool that uses database mirroring</span></span>](alwayson-availability-group.md#BKMK_MirroredPool_CreateAlwaysOnGroup)
    
- [<span data-ttu-id="d2c3f-109">在不使用数据库镜像的现有池上部署 Always On 可用性组</span><span class="sxs-lookup"><span data-stu-id="d2c3f-109">Deploy an Always On Availability Group on an existing pool that does not use database mirroring</span></span>](alwayson-availability-group.md#BKMK_NoHAPool_CreateAlwaysOnGroup)
    
## <a name="deploy-an-always-on-availability-group-on-a-new-front-end-pool"></a><span data-ttu-id="d2c3f-110">在新的前端池上部署 Always On 可用性组</span><span class="sxs-lookup"><span data-stu-id="d2c3f-110">Deploy an Always On Availability Group on a new Front End pool</span></span>
<span data-ttu-id="d2c3f-111"><a name="BKMK_NewPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="d2c3f-111"><a name="BKMK_NewPool_CreateAlwaysOnGroup"> </a></span></span>

1. <span data-ttu-id="d2c3f-112">在将成为 AG 一部分的所有数据库服务器上启用故障转移群集功能。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-112">Enable the Failover Clustering feature on all the database servers which will be part of the AG.</span></span> <span data-ttu-id="d2c3f-113">在每台服务器上，执行以下操作</span><span class="sxs-lookup"><span data-stu-id="d2c3f-113">On each server, do the following</span></span>
    
   - <span data-ttu-id="d2c3f-114">打开服务器管理器，然后单击 **"添加角色和功能"。**</span><span class="sxs-lookup"><span data-stu-id="d2c3f-114">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="d2c3f-115">单击 **"下** 一步"，直到到达 **"选择功能"** 框。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-115">Click **Next** until you reach the **Select features** box.</span></span> <span data-ttu-id="d2c3f-116">在此处，选中 **"故障转移群集"** 复选框。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-116">Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="d2c3f-117">在 **"添加故障转移群集所需的功能？"** 框中，单击"**添加功能"。**</span><span class="sxs-lookup"><span data-stu-id="d2c3f-117">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="d2c3f-118">单击“**安装**”。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-118">Click **Install**.</span></span>
    
2. <span data-ttu-id="d2c3f-119">验证群集配置。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-119">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="d2c3f-120">在服务器管理器中，单击 **"工具** "菜单，然后单击 **故障转移群集管理器**。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-120">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="d2c3f-121">在 **屏幕** 右侧"操作"下，单击"**验证配置"。**</span><span class="sxs-lookup"><span data-stu-id="d2c3f-121">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="d2c3f-122">在“开始之前”页中，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-122">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="d2c3f-123">选择要添加到群集的服务器，然后单击"运行 **所有测试"。**</span><span class="sxs-lookup"><span data-stu-id="d2c3f-123">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="d2c3f-124">在 **"摘要"** 框中，检查向导报告的任何错误。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-124">In the **Summary** box, check any errors that the wizard reports.</span></span> <span data-ttu-id="d2c3f-125">然后单击 **"完成** "完成验证。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-125">Then click **Finish** to complete the validation.</span></span>
    
     <span data-ttu-id="d2c3f-126">向导可能会报告多个警告，尤其是在你未使用共享存储时。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-126">The wizard will probably report several warnings, especially if you are not using shared storage.</span></span> <span data-ttu-id="d2c3f-127">无需使用共享存储。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-127">You are not required to use shared storage.</span></span> <span data-ttu-id="d2c3f-128">但是，如果 **看到任何错误消息** ，则必须修复这些问题，然后才能继续。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-128">However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
3. <span data-ttu-id="d2c3f-129">创建 Windows Server 故障转移群集 (WSFC) 。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-129">Create the Windows Server Failover Cluster (WSFC).</span></span>
    
   - <span data-ttu-id="d2c3f-130">在 **故障转移群集管理向导** 中，右键单击 **"故障转移群集管理**"，然后单击"**创建群集"。**</span><span class="sxs-lookup"><span data-stu-id="d2c3f-130">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="d2c3f-131">在“开始之前”页中，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-131">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="d2c3f-132">添加群集名称和 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-132">Add the cluster name and IP address.</span></span> <span data-ttu-id="d2c3f-133">验证设置后，单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="d2c3f-133">When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="d2c3f-134">在" 确认"页上单击" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-134">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="d2c3f-135">创建群集后，单击"完成 **"。**</span><span class="sxs-lookup"><span data-stu-id="d2c3f-135">After the cluster is created, click **Finish**.</span></span>
    
4. <span data-ttu-id="d2c3f-136">建议您将群集仲裁设置配置为使用文件共享见证。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-136">We recommend that you configure the cluster quorum settings to use a file share witness.</span></span> <span data-ttu-id="d2c3f-137">为此，请使用以下步骤：</span><span class="sxs-lookup"><span data-stu-id="d2c3f-137">To do so, use these steps:</span></span>
    
   - <span data-ttu-id="d2c3f-138">右键单击群集名称，单击 **"更多操作**"，然后单击"**配置群集仲裁设置"。**</span><span class="sxs-lookup"><span data-stu-id="d2c3f-138">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="d2c3f-139">在 **"选择仲裁配置选项"页** 中，单击"**选择仲裁见证"。**</span><span class="sxs-lookup"><span data-stu-id="d2c3f-139">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="d2c3f-140">在 **"选择仲裁见证"页** 中，单击 **"配置文件共享见证"。**</span><span class="sxs-lookup"><span data-stu-id="d2c3f-140">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="d2c3f-141">在 **"配置文件共享见证**"页中，键入想要使用的文件共享的路径，然后单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="d2c3f-141">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="d2c3f-142">在" **确认**"页上单击" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-142">On the **Confirmation** page, click **Next**.</span></span>
    
5. <span data-ttu-id="d2c3f-143">在群集中的每台服务器上，在配置管理器中SQL Server AG 功能。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-143">On each server in the cluster, enable the AG feature in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="d2c3f-144">打开 SQL Server 配置管理器。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-144">Open SQL Server Configuration Manager.</span></span> <span data-ttu-id="d2c3f-145">在屏幕左侧的树中，单击SQL Server **服务**，然后双击SQL Server服务。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-145">In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="d2c3f-146">在" **属性"** 框中，选择 **"AlwaysOn 高可用性"** 选项卡。选中 **"启用 AlwaysOn 可用性组"** 复选框。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-146">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box.</span></span> <span data-ttu-id="d2c3f-147">当系统SQL Server重新启动服务。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-147">Restart the SQL Server service when prompted.</span></span>
   
6. <span data-ttu-id="d2c3f-148">使用拓扑生成器创建前端池，如 Skype for Business Server 中的"创建和发布新拓扑"[中介绍。](../../deploy/install/create-and-publish-new-topology.md)</span><span class="sxs-lookup"><span data-stu-id="d2c3f-148">Use Topology Builder to create the Front End pool, as explained in [Create and publish new topology in Skype for Business Server](../../deploy/install/create-and-publish-new-topology.md).</span></span> <span data-ttu-id="d2c3f-149">这样做时，请指定 AG 作为SQL存储。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-149">When you do, specify the AG as the SQL store for the pool.</span></span>
    
7. <span data-ttu-id="d2c3f-150">创建可用性组。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-150">Create the availability group.</span></span>
    
   - <span data-ttu-id="d2c3f-151">打开 SQL Server Management Studio，并连接到SQL Server实例。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-151">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
   - <span data-ttu-id="d2c3f-152">在对象资源管理器中，展开 **Always On High Availability** 文件夹。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-152">In Object Explorer, expand the **Always On High Availability** folder.</span></span> <span data-ttu-id="d2c3f-153">右键单击 **可用性组** 文件夹，然后单击 **"新建可用性组向导"。**</span><span class="sxs-lookup"><span data-stu-id="d2c3f-153">Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
   - <span data-ttu-id="d2c3f-154">如果显示 **"简介"** 页，请单击"下 **一步"。**</span><span class="sxs-lookup"><span data-stu-id="d2c3f-154">If the **Introduction** page appears, click **Next**.</span></span>
    
   - <span data-ttu-id="d2c3f-155">在 **"指定可用性组名称**"页中，键入可用性组的名称，然后单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="d2c3f-155">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
   - <span data-ttu-id="d2c3f-156">在"选择数据库"页中，选择要包括在 AlwaysOn 可用性组的数据库。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-156">In the Select Databases page, select the databases that you want to include in the AlwaysOn Availability Group.</span></span> <span data-ttu-id="d2c3f-157">然后，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-157">Then click **Next**.</span></span>
    
     <span data-ttu-id="d2c3f-158">请勿将 **ReportServer、ReportServerTempDB** 或持久聊天数据库包括在 AlwaysOn 可用性组中，因为此方案不支持这些数据库。 </span><span class="sxs-lookup"><span data-stu-id="d2c3f-158">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AlwaysOn Availability Group, as these are not supported in this scenario.</span></span> <span data-ttu-id="d2c3f-159">你可以将所有其他 Skype for Business Server 数据库包括在 AlwaysOn 可用性组中。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-159">You can include all other Skype for Business Server databases in the AlwaysOn Availability Group.</span></span>
    
   - <span data-ttu-id="d2c3f-160">在 **"指定副本"** 页中，单击 **"副本"** 选项卡。然后单击" **添加副本** "按钮，并连接到SQL Windows Server 故障转移群集节点加入的其他实例。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-160">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the Windows Server Failover Cluster.</span></span>
    
   - <span data-ttu-id="d2c3f-161">对于每个实例，选择 **"自动故障转移"和\*\*\*\*"同步提交"** 选项。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-161">For each instance, select the **Automatic Failover** and **Synchronous Commit** options.</span></span> <span data-ttu-id="d2c3f-162">不要选择" **可读辅助"** 选项。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-162">Do not select the **Readable Secondary** option.</span></span>
    
   - <span data-ttu-id="d2c3f-163">单击 **"终结点"** 选项卡并验证端口 **号** 是否设置为 5022。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-163">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
   - <span data-ttu-id="d2c3f-164">单击" **侦听器"** 选项卡，然后选择" **创建可用性组侦听器"** 选项。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-164">Click the **Listener** tab, and select the **Create an availability group listener** option.</span></span> <span data-ttu-id="d2c3f-165">在该选项下，键入侦听器的名称，将端口设置为 1433 (此选项不支持其他端口) 。 </span><span class="sxs-lookup"><span data-stu-id="d2c3f-165">Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
   - <span data-ttu-id="d2c3f-166">单击 **"添加"，** 然后在 **"IPv4** 地址"框中提供首选的虚拟 IP 地址，然后单击"**确定"。**</span><span class="sxs-lookup"><span data-stu-id="d2c3f-166">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
   - <span data-ttu-id="d2c3f-167">在"选择初始数据 **同步** "页中，选择"完全"，并指定副本可访问的文件夹，以及两个副本使用的 SQL Server 服务帐户具有写入权限的文件夹。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-167">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for.</span></span> <span data-ttu-id="d2c3f-168">然后，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-168">Then click **Next**.</span></span>
    
     <span data-ttu-id="d2c3f-169">初始化数据库时，将临时使用此文件共享。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-169">This file share will be used temporarily when you initialize the databases.</span></span> <span data-ttu-id="d2c3f-170">如果要处理大型数据库，建议您手动初始化它们，以防网络带宽无法容纳数据库备份的大小。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-170">If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
   - <span data-ttu-id="d2c3f-171">在"验证"页中，验证所有验证检查是否成功，然后单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="d2c3f-171">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
   - <span data-ttu-id="d2c3f-172">在 **"摘要"页** 中，验证所有设置并单击"完成"。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-172">In the **Summary** page, verify all settings and click Finish.</span></span>
      
8. <span data-ttu-id="d2c3f-173">部署池和 AG 后，执行一些最后步骤，以确保SQL登录名位于 AlwaysOn 可用性组的每个副本上。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-173">After the pool and the AG are deployed, perform some final steps to make sure that the SQL logins are on each of the replicas in the AlwaysOn Availability Group.</span></span> 
    
   - <span data-ttu-id="d2c3f-174">打开拓扑生成器，从现有 **部署** 中选择"下载拓扑"，然后单击"**确定"。**</span><span class="sxs-lookup"><span data-stu-id="d2c3f-174">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
   - <span data-ttu-id="d2c3f-175">展开 Skype for Business Server、扩展拓扑和SQL Server **应用商店**。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-175">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="d2c3f-176">右键单击SQL AlwaysOn 可用性组的新存储，然后单击"**编辑属性"。**</span><span class="sxs-lookup"><span data-stu-id="d2c3f-176">Right-click the SQL store of the new AlwaysOn Availability Group, and click **Edit Properties**.</span></span>
    
     - <span data-ttu-id="d2c3f-177">在页面底部，在SQL Server **FQDN** 框中，将值更改为 AG 侦听器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-177">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AG.</span></span>
    
   - <span data-ttu-id="d2c3f-178">发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-178">Publish the topology.</span></span> <span data-ttu-id="d2c3f-179">从" **操作"** 菜单中，单击 **"拓扑** "，然后 **发布**。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-179">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="d2c3f-180">然后在确认页中单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="d2c3f-180">Then in the confirmation page click **Next**.</span></span> <span data-ttu-id="d2c3f-181">然后等待几分钟，以便复制新拓扑。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-181">Then wait a few minutes for the new topology to replicate.</span></span>
    
   - <span data-ttu-id="d2c3f-182">打开 SQL Server Management Studio，然后导航到 AG。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-182">Open SQL Server Management Studio, and navigate to the AG.</span></span> <span data-ttu-id="d2c3f-183">故障转移到辅助副本。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-183">Fail it over to a secondary replica.</span></span>
    
   - <span data-ttu-id="d2c3f-184">打开 Skype for Business Server 命令行管理程序 并键入以下 cmdlet，以SQL此副本上的登录名：</span><span class="sxs-lookup"><span data-stu-id="d2c3f-184">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
   ```powershell
   Install-CsDatabase -Update
   ```

   - <span data-ttu-id="d2c3f-185">重复上述两个步骤 (将组故障转移到辅助副本，然后对)  `Install-CsDatabase -Update` 副本使用前两个步骤。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-185">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
    
## <a name="deploy-an-always-on-availability-group-on-an-existing-pool-that-uses-database-mirroring"></a><span data-ttu-id="d2c3f-186">在使用数据库镜像的现有池上部署 Always On 可用性组</span><span class="sxs-lookup"><span data-stu-id="d2c3f-186">Deploy an Always On Availability Group on an existing pool that uses database mirroring</span></span>
<span data-ttu-id="d2c3f-187"><a name="BKMK_MirroredPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="d2c3f-187"><a name="BKMK_MirroredPool_CreateAlwaysOnGroup"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="d2c3f-188">如果要升级到 AG 的池托管组织的中央管理存储，则必须先将 CMS 移动到另一个池，然后才能升级此池。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-188">If the pool you are upgrading to an AG hosts the Central Management store for your organization, you must first move the CMS to another pool before you upgrade this pool.</span></span> <span data-ttu-id="d2c3f-189">使用 Move-CsManagementServer cmdlet 移动池。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-189">Use the Move-CsManagementServer cmdlet to move the pool.</span></span> <span data-ttu-id="d2c3f-190">如果组织中没有另一个池，可以在将池升级到 AG 之前临时部署 Standard Edition Server，将 CMS 移动到该服务器。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-190">If you do not have another pool in your organization, you can deploy a Standard Edition server temporarily and move the CMS to this server before you upgrade your pool to the AG.</span></span> 
  
1. <span data-ttu-id="d2c3f-191">通过打开 Skype for Business Server 命令行管理程序并键入以下 cmdlet，将镜像中所有数据故障转移到主体节点。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-191">Fail over all data from the mirror to the principal node by opening Skype for Business Server Management Shell and typing the following cmdlet.</span></span>
    
   ```powershell
   Invoke-CsDatabaseFailover -PoolFqdn <Pool FQDN> -DatabaseType <DatabaseType> -NewPrincipal "Primary"
   ```

    <span data-ttu-id="d2c3f-192">对池中的每个数据库类型重复此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-192">Repeat this cmdlet for each database type in the pool.</span></span> <span data-ttu-id="d2c3f-193">您可以使用以下 cmdlet 查找存储在此池中的所有数据库类型。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-193">You can use the following cmdlet to find all the database types stored in this pool.</span></span>
     
   ```powershell
   Get-CsPool -Identity <Pool FQDN>
   ```

2. <span data-ttu-id="d2c3f-194">使用拓扑生成器从池中删除数据库镜像。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-194">Use Topology Builder to remove database mirroring from the pool.</span></span>
    
   - <span data-ttu-id="d2c3f-195">打开拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-195">Open Topology Builder.</span></span> <span data-ttu-id="d2c3f-196">在拓扑中，展开 **Enterprise Edition 前端池，** 右键单击池的名称，然后单击"**编辑属性"。**</span><span class="sxs-lookup"><span data-stu-id="d2c3f-196">In your topology, expand **Enterprise Edition Front End Pools**, right-click the name of the pool, and click **Edit Properties**.</span></span>
    
   - <span data-ttu-id="d2c3f-197">对于池中的SQL类型的存储，清除"启用SQL **存储镜像** "复选框。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-197">For each type of SQL store in the pool, clear the **Enable SQL Store Mirroring** check box.</span></span>
    
3. <span data-ttu-id="d2c3f-198">发布已更改的拓扑。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-198">Publish the changed topology.</span></span> <span data-ttu-id="d2c3f-199">从" **操作"** 菜单中，单击 **"拓扑** "，然后 **发布**。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-199">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="d2c3f-200">然后在确认页中单击"下 **一步"**</span><span class="sxs-lookup"><span data-stu-id="d2c3f-200">Then in the confirmation page click **Next**</span></span>
    
4. <span data-ttu-id="d2c3f-201">使用 SQL Server Management Studio 中断镜像。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-201">Use SQL Server Management Studio to break the mirror.</span></span>
    
   - <span data-ttu-id="d2c3f-202">打开 SQL Server Management Studio，导航到数据库，**右键单击**"任务"，然后单击"**镜像"。**</span><span class="sxs-lookup"><span data-stu-id="d2c3f-202">Open SQL Server Management Studio, navigate to your databases, right-click **Tasks** and click **Mirror**.</span></span> <span data-ttu-id="d2c3f-203">然后单击 **"删除镜像"，** 然后单击"**确定"。**</span><span class="sxs-lookup"><span data-stu-id="d2c3f-203">Then click **Remove Mirroring** and click **OK**.</span></span>
    
   - <span data-ttu-id="d2c3f-204">对池中将转换为 AG 的所有数据库重复此操作。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-204">Repeat this for all databases in the pool which will be converted to an AG.</span></span>
    
5. <span data-ttu-id="d2c3f-205">在将成为 AG 一部分的所有数据库服务器上设置故障转移群集功能。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-205">Set up the Failover Clustering feature on all the database servers which will be part of the AG.</span></span> <span data-ttu-id="d2c3f-206">在每台服务器上，执行以下操作</span><span class="sxs-lookup"><span data-stu-id="d2c3f-206">On each server, do the following</span></span>
    
   - <span data-ttu-id="d2c3f-207">打开服务器管理器，然后单击 **"添加角色和功能"。**</span><span class="sxs-lookup"><span data-stu-id="d2c3f-207">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="d2c3f-208">单击 **"下** 一步"，直到到达 **"选择功能"** 框。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-208">Click **Next** until you reach the **Select features** box.</span></span> <span data-ttu-id="d2c3f-209">在此处，选中 **"故障转移群集"** 复选框。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-209">Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="d2c3f-210">在 **"添加故障转移群集所需的功能？"** 框中，单击"**添加功能"。**</span><span class="sxs-lookup"><span data-stu-id="d2c3f-210">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="d2c3f-211">单击“**安装**”。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-211">Click **Install**.</span></span>
    
6. <span data-ttu-id="d2c3f-212">验证群集配置。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-212">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="d2c3f-213">在服务器管理器中，单击 **"工具** "菜单，然后单击 **故障转移群集管理器**。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-213">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="d2c3f-214">在 **屏幕** 右侧"操作"下，单击"**验证配置"。**</span><span class="sxs-lookup"><span data-stu-id="d2c3f-214">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="d2c3f-215">在“开始之前”页中，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-215">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="d2c3f-216">选择要添加到群集的服务器，然后单击"运行 **所有测试"。**</span><span class="sxs-lookup"><span data-stu-id="d2c3f-216">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="d2c3f-217">在 **"摘要"** 框中，检查向导报告的任何错误。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-217">In the **Summary** box, check any errors that the wizard reports.</span></span> <span data-ttu-id="d2c3f-218">然后单击 **"完成** "完成验证。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-218">Then click **Finish** to complete the validation.</span></span>
    
     <span data-ttu-id="d2c3f-219">向导可能会报告多个警告，尤其是在你未使用共享存储时。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-219">The wizard will probably report several warnings, especially if you are not using shared storage.</span></span> <span data-ttu-id="d2c3f-220">无需使用共享存储。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-220">You are not required to use shared storage.</span></span> <span data-ttu-id="d2c3f-221">但是，如果 **看到任何错误消息** ，则必须修复这些问题，然后才能继续。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-221">However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
7. <span data-ttu-id="d2c3f-222">创建 Windows Server 故障转移群集。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-222">Create the Windows Server Failover Cluster.</span></span>
    
   - <span data-ttu-id="d2c3f-223">在 **故障转移群集管理向导** 中，右键单击 **"故障转移群集管理**"，然后单击"**创建群集"。**</span><span class="sxs-lookup"><span data-stu-id="d2c3f-223">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="d2c3f-224">在“开始之前”页中，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-224">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="d2c3f-225">添加群集名称和 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-225">Add the cluster name and IP address.</span></span> <span data-ttu-id="d2c3f-226">验证设置后，单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="d2c3f-226">When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="d2c3f-227">在" 确认"页上单击" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-227">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="d2c3f-228">创建群集后，单击"完成 **"。**</span><span class="sxs-lookup"><span data-stu-id="d2c3f-228">After the cluster is created, click **Finish**.</span></span>
    
8. <span data-ttu-id="d2c3f-229">建议您将群集仲裁设置配置为使用文件共享见证。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-229">We recommend that you configure the cluster quorum settings to use a file share witness.</span></span> <span data-ttu-id="d2c3f-230">为此，请使用以下步骤：</span><span class="sxs-lookup"><span data-stu-id="d2c3f-230">To do so, use these steps:</span></span>
    
   - <span data-ttu-id="d2c3f-231">右键单击群集名称，单击 **"更多操作**"，然后单击"**配置群集仲裁设置"。**</span><span class="sxs-lookup"><span data-stu-id="d2c3f-231">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="d2c3f-232">在 **"选择仲裁配置选项"页** 中，单击"**选择仲裁见证"。**</span><span class="sxs-lookup"><span data-stu-id="d2c3f-232">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="d2c3f-233">在 **"选择仲裁见证"页** 中，单击 **"配置文件共享见证"。**</span><span class="sxs-lookup"><span data-stu-id="d2c3f-233">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="d2c3f-234">在 **"配置文件共享见证**"页中，键入想要使用的文件共享的路径，然后单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="d2c3f-234">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="d2c3f-235">在" **确认**"页上单击" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-235">On the **Confirmation** page, click **Next**.</span></span>
    
9. <span data-ttu-id="d2c3f-236">在群集中的每台服务器上，在配置管理器中SQL Server AG 功能。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-236">On each server in the cluster, enable the AG feature in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="d2c3f-237">打开 SQL Server 配置管理器。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-237">Open SQL Server Configuration Manager.</span></span> <span data-ttu-id="d2c3f-238">在屏幕左侧的树中，单击SQL Server **服务**，然后双击SQL Server服务。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-238">In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="d2c3f-239">在" **属性"** 框中，选择 **"AlwaysOn 高可用性"** 选项卡。选中 **"启用 AlwaysOn 可用性组"** 复选框。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-239">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box.</span></span> <span data-ttu-id="d2c3f-240">当系统SQL Server重新启动服务。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-240">Restart the SQL Server service when prompted.</span></span>
    
10. <span data-ttu-id="d2c3f-241">创建可用性组。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-241">Create the availability group.</span></span>
    
    - <span data-ttu-id="d2c3f-242">打开 SQL Server Management Studio，并连接到SQL Server实例。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-242">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
    - <span data-ttu-id="d2c3f-243">在对象资源管理器中，展开 **Always On High Availability** 文件夹。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-243">In Object Explorer, expand the **Always On High Availability** folder.</span></span> <span data-ttu-id="d2c3f-244">右键单击 **可用性组** 文件夹，然后单击 **"新建可用性组向导"。**</span><span class="sxs-lookup"><span data-stu-id="d2c3f-244">Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
    - <span data-ttu-id="d2c3f-245">如果显示 **"简介"** 页，请单击"下 **一步"。**</span><span class="sxs-lookup"><span data-stu-id="d2c3f-245">If the **Introduction** page appears, click **Next**.</span></span>
    
    - <span data-ttu-id="d2c3f-246">在 **"指定可用性组名称**"页中，键入可用性组的名称，然后单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="d2c3f-246">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
    - <span data-ttu-id="d2c3f-247">在"选择数据库"页中，选择要包括在 AlwaysOn 可用性组的数据库。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-247">In the Select Databases page, select the databases that you want to include in the AlwaysOn Availability Group.</span></span> <span data-ttu-id="d2c3f-248">然后，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-248">Then click **Next**.</span></span>
    
    <span data-ttu-id="d2c3f-249">请勿将 **ReportServer、ReportServerTempDB** 或持久聊天数据库包括在 AlwaysOn 可用性组中，因为此方案不支持这些数据库。 </span><span class="sxs-lookup"><span data-stu-id="d2c3f-249">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AlwaysOn Availability Group, as these are not supported in this scenario.</span></span> <span data-ttu-id="d2c3f-250">你可以将所有其他 Skype for Business Server 数据库包括在 AlwaysOn 可用性组中。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-250">You can include all other Skype for Business Server databases in the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="d2c3f-251">在 **"指定副本"** 页中，单击 **"副本"** 选项卡。然后单击" **添加副本** "按钮，并连接到SQL Windows Server 故障转移群集节点加入的其他实例。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-251">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the Windows Server Failover Cluster.</span></span>
    
    - <span data-ttu-id="d2c3f-252">对于每个实例，选择 **"自动故障转移"和\*\*\*\*"同步提交"** 选项。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-252">For each instance, select the **Automatic Failover** and **Synchronous Commit** options.</span></span> <span data-ttu-id="d2c3f-253">不要选择" **可读辅助"** 选项。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-253">Do not select the **Readable Secondary** option.</span></span>
    
    - <span data-ttu-id="d2c3f-254">单击 **"终结点"** 选项卡并验证端口 **号** 是否设置为 5022。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-254">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
      - <span data-ttu-id="d2c3f-255">单击" **侦听器"** 选项卡，然后选择" **创建可用性组侦听器"** 选项。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-255">Click the **Listener** tab, and select the **Create an availability group listener** option.</span></span> <span data-ttu-id="d2c3f-256">在该选项下，键入侦听器的名称，将端口设置为 1433 (此选项不支持其他端口) 。 </span><span class="sxs-lookup"><span data-stu-id="d2c3f-256">Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
    - <span data-ttu-id="d2c3f-257">单击 **"添加"，** 然后在 **"IPv4** 地址"框中提供首选的虚拟 IP 地址，然后单击"**确定"。**</span><span class="sxs-lookup"><span data-stu-id="d2c3f-257">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
    - <span data-ttu-id="d2c3f-258">在"选择初始数据 **同步** "页中，选择"完全"，并指定副本可访问的文件夹，以及两个副本使用的 SQL Server 服务帐户具有写入权限的文件夹。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-258">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for.</span></span> <span data-ttu-id="d2c3f-259">然后，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-259">Then click **Next**.</span></span>
    
    <span data-ttu-id="d2c3f-260">初始化数据库时，将临时使用此文件共享。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-260">This file share will be used temporarily when you initialize the databases.</span></span> <span data-ttu-id="d2c3f-261">如果要处理大型数据库，建议您手动初始化它们，以防网络带宽无法容纳数据库备份的大小。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-261">If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
    - <span data-ttu-id="d2c3f-262">在"验证"页中，验证所有验证检查是否成功，然后单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="d2c3f-262">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
    - <span data-ttu-id="d2c3f-263">在 **"摘要"页** 中，验证所有设置并单击"完成"。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-263">In the **Summary** page, verify all settings and click Finish.</span></span>
    
11. <span data-ttu-id="d2c3f-264">创建一个新存储，指定 AG 侦听器，并指定旧镜像的主体作为 AG 的主节点。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-264">Create a new store specifying the AG listener, and specifying the principal of the old mirror as the primary node of the AG.</span></span>
    
    - <span data-ttu-id="d2c3f-265">打开拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-265">Open Topology Builder.</span></span> <span data-ttu-id="d2c3f-266">在拓扑中，展开 **"共享组件**"，右键 **SQL Server应用商店**，然后单击"新建SQL Server **应用商店"。**</span><span class="sxs-lookup"><span data-stu-id="d2c3f-266">In your topology, expand **Shared Components**, right-click **SQL Server Stores**, and click **New SQL Server Store**.</span></span>
    
    - <span data-ttu-id="d2c3f-267">在"**定义** SQL应用商店"页中，首先选中"高可用性设置"复选框，然后确保SQL下拉框中显示"AlwaysOn 可用性组"。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-267">In the **Define New SQL Store** page, first select the **High Availability Settings** check box, and then make sure that SQL AlwaysOn Availability Groups appears in the drop-down box.</span></span>
    
    - <span data-ttu-id="d2c3f-268">在 **SQL Server侦听器 FQDN"** 框中，键入创建可用性组时创建的侦听器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-268">In the **SQL Server Availability Listener FQDN** box, type the FQDN of the listener you created when you created the availability group.</span></span>
    
    - <span data-ttu-id="d2c3f-269">在 **SQL Server FQDN** 框中，键入 AG 的主节点的 FQDN，然后单击"**确定"。**</span><span class="sxs-lookup"><span data-stu-id="d2c3f-269">In the **SQL Server FQDN** box, type the FQDN of the primary node of the AG, and then click **OK**.</span></span> <span data-ttu-id="d2c3f-270">这应该是此存储的旧镜像的主体。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-270">This should be the principal of the old mirror for this store.</span></span>
    
12. <span data-ttu-id="d2c3f-271">将新 AG 与前端池关联。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-271">Associate the new AG with the Front End pool.</span></span>
    
    - <span data-ttu-id="d2c3f-272">在拓扑生成器中，右键单击要与 AG 关联的池，然后单击"**编辑属性"。**</span><span class="sxs-lookup"><span data-stu-id="d2c3f-272">In Topology Builder, right-click the pool to associate with the AG, and click **Edit Properties**.</span></span>
    
    - <span data-ttu-id="d2c3f-273">在 **"关联"\*\*\*\*下的SQL Server"应用商店"** 框中，选择 AG。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-273">Under **Associations**, in the **SQL Server Store** box, select the AG.</span></span> <span data-ttu-id="d2c3f-274">为池中要移动到 AG 的其他任何数据库选择同一组。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-274">Select the same group for any other databases in the pool which you want to move to the AG.</span></span>
    
    - <span data-ttu-id="d2c3f-275">当你确定所有所需的数据库都设置为 AG 时，请单击"**确定"。**</span><span class="sxs-lookup"><span data-stu-id="d2c3f-275">When you're sure that all needed databases are set to the AG, click **OK**.</span></span>
    
13. <span data-ttu-id="d2c3f-276">发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-276">Publish the topology.</span></span> <span data-ttu-id="d2c3f-277">从" **操作"** 菜单中，单击 **"拓扑** "，然后 **发布**。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-277">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="d2c3f-278">然后在确认页中单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="d2c3f-278">Then in the confirmation page click **Next**.</span></span>
    
14. <span data-ttu-id="d2c3f-279">执行一些最后的步骤，以确保SQL登录名位于 AlwaysOn 可用性组的每个副本上。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-279">Perform some final steps to make sure that the SQL logins are on each of the replicas in the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="d2c3f-280">打开拓扑生成器，从现有 **部署** 中选择"下载拓扑"，然后单击"**确定"。**</span><span class="sxs-lookup"><span data-stu-id="d2c3f-280">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
    - <span data-ttu-id="d2c3f-281">展开 Skype for Business Server、扩展拓扑和SQL Server **应用商店**。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-281">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="d2c3f-282">右键单击SQL AG 的应用商店，然后单击"编辑 **属性"。**</span><span class="sxs-lookup"><span data-stu-id="d2c3f-282">Right-click the SQL store of the new AG, and click **Edit Properties**.</span></span>
    
    - <span data-ttu-id="d2c3f-283">在页面底部，在SQL Server **FQDN** 框中，将值更改为 AG 侦听器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-283">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AG.</span></span>
    
    - <span data-ttu-id="d2c3f-284">发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-284">Publish the topology.</span></span> <span data-ttu-id="d2c3f-285">从" **操作"** 菜单中，单击 **"拓扑** "，然后 **发布**。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-285">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="d2c3f-286">然后在确认页中单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="d2c3f-286">Then in the confirmation page click **Next**.</span></span> <span data-ttu-id="d2c3f-287">然后等待几分钟，以便复制新拓扑。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-287">Then wait a few minutes for the new topology to replicate.</span></span>
    
    - <span data-ttu-id="d2c3f-288">打开 SQL Server Management Studio，然后导航到 AG。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-288">Open SQL Server Management Studio, and navigate to the AG.</span></span> <span data-ttu-id="d2c3f-289">故障转移到辅助副本。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-289">Fail it over to a secondary replica.</span></span>
    
    - <span data-ttu-id="d2c3f-290">打开 Skype for Business Server 命令行管理程序 并键入以下 cmdlet，以SQL此副本上的登录名：</span><span class="sxs-lookup"><span data-stu-id="d2c3f-290">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
    ```powershell
    Install-CsDatabase -Update
    ```

    - <span data-ttu-id="d2c3f-291">重复上述两个步骤 (将组故障转移到辅助副本，然后对)  `Install-CsDatabase -Update` 副本使用前两个步骤。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-291">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
    
## <a name="deploy-an-always-on-availability-group-on-an-existing-pool-that-does-not-use-database-mirroring"></a><span data-ttu-id="d2c3f-292">在不使用数据库镜像的现有池上部署 Always On 可用性组</span><span class="sxs-lookup"><span data-stu-id="d2c3f-292">Deploy an Always On Availability Group on an existing pool that does not use database mirroring</span></span>
<span data-ttu-id="d2c3f-293"><a name="BKMK_NoHAPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="d2c3f-293"><a name="BKMK_NoHAPool_CreateAlwaysOnGroup"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="d2c3f-294">如果要升级到 AG 的池托管组织的中央管理存储，则必须先将 CMS 移动到另一个池，然后才能升级此池。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-294">If the pool you are upgrading to an AG hosts the Central Management store for your organization, you must first move the CMS to another pool before you upgrade this pool.</span></span> <span data-ttu-id="d2c3f-295">使用 Move-CsManagementServer cmdlet 移动池。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-295">Use the Move-CsManagementServer cmdlet to move the pool.</span></span> <span data-ttu-id="d2c3f-296">如果组织中没有另一个池，可以在将池升级到 AG 之前临时部署 Standard Edition Server，将 CMS 移动到该服务器。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-296">If you do not have another pool in your organization, you can deploy a Standard Edition server temporarily and move the CMS to this server before you upgrade your pool to the AG.</span></span> 
  
1. <span data-ttu-id="d2c3f-297">在将成为 AG 一部分的所有数据库服务器上设置故障转移群集功能。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-297">Set up the Failover Clustering feature on all the database servers which will be part of the AG.</span></span> <span data-ttu-id="d2c3f-298">在每台服务器上，执行以下操作</span><span class="sxs-lookup"><span data-stu-id="d2c3f-298">On each server, do the following</span></span>
    
   - <span data-ttu-id="d2c3f-299">打开服务器管理器，然后单击 **"添加角色和功能"。**</span><span class="sxs-lookup"><span data-stu-id="d2c3f-299">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="d2c3f-300">单击 **"下** 一步"，直到到达 **"选择功能"** 框。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-300">Click **Next** until you reach the **Select features** box.</span></span> <span data-ttu-id="d2c3f-301">在此处，选中 **"故障转移群集"** 复选框。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-301">Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="d2c3f-302">在 **"添加故障转移群集所需的功能？"** 框中，单击"**添加功能"。**</span><span class="sxs-lookup"><span data-stu-id="d2c3f-302">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="d2c3f-303">单击“**安装**”。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-303">Click **Install**.</span></span>
    
2. <span data-ttu-id="d2c3f-304">验证群集配置。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-304">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="d2c3f-305">在服务器管理器中，单击 **"工具** "菜单，然后单击 **故障转移群集管理器**。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-305">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="d2c3f-306">在 **屏幕** 右侧"操作"下，单击"**验证配置"。**</span><span class="sxs-lookup"><span data-stu-id="d2c3f-306">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="d2c3f-307">在“开始之前”页中，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-307">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="d2c3f-308">选择要添加到群集的服务器，然后单击"运行 **所有测试"。**</span><span class="sxs-lookup"><span data-stu-id="d2c3f-308">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="d2c3f-309">在 **"摘要"** 框中，检查向导报告的任何错误。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-309">In the **Summary** box, check any errors that the wizard reports.</span></span> <span data-ttu-id="d2c3f-310">然后单击 **"完成** "完成验证。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-310">Then click **Finish** to complete the validation.</span></span>
    
     <span data-ttu-id="d2c3f-311">向导可能会报告多个警告，尤其是在你未使用共享存储时。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-311">The wizard will probably report several warnings, especially if you are not using shared storage.</span></span> <span data-ttu-id="d2c3f-312">无需使用共享存储。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-312">You are not required to use shared storage.</span></span> <span data-ttu-id="d2c3f-313">但是，如果 **看到任何错误消息** ，则必须修复这些问题，然后才能继续。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-313">However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
3. <span data-ttu-id="d2c3f-314">创建 Windows Server 故障转移群集 (WSFC) 。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-314">Create the Windows Server Failover Cluster (WSFC).</span></span>
    
   - <span data-ttu-id="d2c3f-315">在 **故障转移群集管理向导** 中，右键单击 **"故障转移群集管理**"，然后单击"**创建群集"。**</span><span class="sxs-lookup"><span data-stu-id="d2c3f-315">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="d2c3f-316">在“开始之前”页中，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-316">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="d2c3f-317">添加群集名称和 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-317">Add the cluster name and IP address.</span></span> <span data-ttu-id="d2c3f-318">验证设置后，单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="d2c3f-318">When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="d2c3f-319">在" 确认"页上单击" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-319">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="d2c3f-320">创建群集后，单击"完成 **"。**</span><span class="sxs-lookup"><span data-stu-id="d2c3f-320">After the cluster is created, click **Finish**.</span></span>
    
4. <span data-ttu-id="d2c3f-321">建议您将群集仲裁设置配置为使用文件共享见证。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-321">We recommend that you configure the cluster quorum settings to use a file share witness.</span></span> <span data-ttu-id="d2c3f-322">为此，请使用以下步骤：</span><span class="sxs-lookup"><span data-stu-id="d2c3f-322">To do so, use these steps:</span></span>
    
   - <span data-ttu-id="d2c3f-323">右键单击群集名称，单击 **"更多操作**"，然后单击"**配置群集仲裁设置"。**</span><span class="sxs-lookup"><span data-stu-id="d2c3f-323">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="d2c3f-324">在 **"选择仲裁配置选项"页** 中，单击"**选择仲裁见证"。**</span><span class="sxs-lookup"><span data-stu-id="d2c3f-324">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="d2c3f-325">在 **"选择仲裁见证"页** 中，单击 **"配置文件共享见证"。**</span><span class="sxs-lookup"><span data-stu-id="d2c3f-325">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="d2c3f-326">在 **"配置文件共享见证**"页中，键入想要使用的文件共享的路径，然后单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="d2c3f-326">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="d2c3f-327">在" **确认**"页上单击" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-327">On the **Confirmation** page, click **Next**.</span></span>
    
5. <span data-ttu-id="d2c3f-328">在群集中的每台服务器上，在配置管理器SQL Server AG。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-328">On each server in the cluster, enable AG in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="d2c3f-329">打开 SQL Server 配置管理器。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-329">Open SQL Server Configuration Manager.</span></span> <span data-ttu-id="d2c3f-330">在屏幕左侧的树中，单击SQL Server **服务**，然后双击SQL Server服务。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-330">In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="d2c3f-331">在" **属性"** 框中，选择 **"AlwaysOn 高可用性"** 选项卡。选中 **"启用 AlwaysOn 可用性组"** 复选框。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-331">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box.</span></span> <span data-ttu-id="d2c3f-332">当系统SQL Server重新启动服务。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-332">Restart the SQL Server service when prompted.</span></span>
    
6. <span data-ttu-id="d2c3f-333">创建可用性组。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-333">Create the availability group.</span></span>
    
   - <span data-ttu-id="d2c3f-334">打开 SQL Server Management Studio，并连接到SQL Server实例。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-334">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
   - <span data-ttu-id="d2c3f-335">在对象资源管理器中，展开 **Always On High Availability** 文件夹。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-335">In Object Explorer, expand the **Always On High Availability** folder.</span></span> <span data-ttu-id="d2c3f-336">右键单击 **可用性组** 文件夹，然后单击 **"新建可用性组向导"。**</span><span class="sxs-lookup"><span data-stu-id="d2c3f-336">Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
   - <span data-ttu-id="d2c3f-337">如果显示 **"简介"** 页，请单击"下 **一步"。**</span><span class="sxs-lookup"><span data-stu-id="d2c3f-337">If the **Introduction** page appears, click **Next**.</span></span>
    
   - <span data-ttu-id="d2c3f-338">在 **"指定可用性组名称**"页中，键入可用性组的名称，然后单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="d2c3f-338">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
   - <span data-ttu-id="d2c3f-339">在"选择数据库"页中，选择要包括在 AG 中的数据库。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-339">In the Select Databases page, select the databases that you want to include in the AG.</span></span> <span data-ttu-id="d2c3f-340">然后，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-340">Then click **Next**.</span></span>
    
     <span data-ttu-id="d2c3f-341">请勿在 AG 中包括 ReportServer、ReportServerTempDB 或持久聊天数据库，因为此方案不支持这些数据库。  </span><span class="sxs-lookup"><span data-stu-id="d2c3f-341">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AG, as these are not supported in this scenario.</span></span> <span data-ttu-id="d2c3f-342">你可以将所有其他 Skype for Business Server 数据库包括在 AG 中。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-342">You can include all other Skype for Business Server databases in the AG.</span></span>
    
   - <span data-ttu-id="d2c3f-343">在 **"指定副本"** 页中，单击 **"副本"** 选项卡。然后单击" **添加副本** "按钮，并连接到SQL WSFC 节点加入的其他实例。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-343">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the WSFC.</span></span>
    
   - <span data-ttu-id="d2c3f-344">对于每个实例，选择 **"自动故障转移"和\*\*\*\*"同步提交"** 选项。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-344">For each instance, select the **Automatic Failover** and **Synchronous Commit** options.</span></span> <span data-ttu-id="d2c3f-345">不要选择" **可读辅助"** 选项。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-345">Do not select the **Readable Secondary** option.</span></span>
    
   - <span data-ttu-id="d2c3f-346">单击 **"终结点"** 选项卡并验证端口 **号** 是否设置为 5022。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-346">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
   - <span data-ttu-id="d2c3f-347">单击" **侦听器"** 选项卡，然后选择" **创建可用性组侦听器"** 选项。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-347">Click the **Listener** tab, and select the **Create an availability group listener** option.</span></span> <span data-ttu-id="d2c3f-348">在该选项下，键入侦听器的名称，将端口设置为 1433 (此选项不支持其他端口) 。 </span><span class="sxs-lookup"><span data-stu-id="d2c3f-348">Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
   - <span data-ttu-id="d2c3f-349">单击 **"添加"，** 然后在 **"IPv4** 地址"框中提供首选的虚拟 IP 地址，然后单击"**确定"。**</span><span class="sxs-lookup"><span data-stu-id="d2c3f-349">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
   - <span data-ttu-id="d2c3f-350">在"选择初始数据 **同步** "页中，选择"完全"，并指定副本可访问的文件夹，以及两个副本使用的 SQL Server 服务帐户具有写入权限的文件夹。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-350">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for.</span></span> <span data-ttu-id="d2c3f-351">然后，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-351">Then click **Next**.</span></span>
    
     <span data-ttu-id="d2c3f-352">初始化数据库时，将临时使用此文件共享。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-352">This file share will be used temporarily when you initialize the databases.</span></span> <span data-ttu-id="d2c3f-353">如果要处理大型数据库，建议您手动初始化它们，以防网络带宽无法容纳数据库备份的大小。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-353">If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
     - <span data-ttu-id="d2c3f-354">在"验证"页中，验证所有验证检查是否成功，然后单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="d2c3f-354">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
   - <span data-ttu-id="d2c3f-355">在 **"摘要"页** 中，验证所有设置并单击"完成"。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-355">In the **Summary** page, verify all settings and click Finish.</span></span>
    
7. <span data-ttu-id="d2c3f-356">创建指定 AG 侦听器的新存储。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-356">Create a new store specifying the AG listener.</span></span>
    
   - <span data-ttu-id="d2c3f-357">打开拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-357">Open Topology Builder.</span></span> <span data-ttu-id="d2c3f-358">在拓扑中，展开 **"共享组件**"，右键 **SQL Server应用商店**，然后单击"新建SQL Server **应用商店"。**</span><span class="sxs-lookup"><span data-stu-id="d2c3f-358">In your topology, expand **Shared Components**, right-click **SQL Server Stores**, and click **New SQL Server Store**.</span></span>
    
   - <span data-ttu-id="d2c3f-359">在"**定义** SQL应用商店"页中，首先选中"高可用性设置"复选框，然后确保SQL下拉框中显示"AlwaysOn 可用性组"。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-359">In the **Define New SQL Store** page, first select the **High Availability Settings** check box, and then make sure that SQL AlwaysOn Availability Groups appears in the drop-down box.</span></span>
    
   - <span data-ttu-id="d2c3f-360">在 **SQL Server侦听器 FQDN"** 框中，键入创建可用性组时创建的侦听器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-360">In the **SQL Server Availability Listener FQDN** box, type the FQDN of the listener you created when you created the availability group.</span></span>
    
   - <span data-ttu-id="d2c3f-361">在 **SQL Server FQDN** 框中，键入 AG 的主节点的 FQDN，然后单击"**确定"。**</span><span class="sxs-lookup"><span data-stu-id="d2c3f-361">In the **SQL Server FQDN** box, type the FQDN of the primary node of the AG, and then click **OK**.</span></span>
    
8. <span data-ttu-id="d2c3f-362">将新的 Always On 可用性组与前端池关联。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-362">Associate the new Always On Availability Group with the Front End pool.</span></span>
    
   - <span data-ttu-id="d2c3f-363">在拓扑生成器中，右键单击要与 AG 关联的池，然后单击"**编辑属性"。**</span><span class="sxs-lookup"><span data-stu-id="d2c3f-363">In Topology Builder, right-click the pool to associate with the AG, and click **Edit Properties**.</span></span>
    
   - <span data-ttu-id="d2c3f-364">在 **"关联"\*\*\*\*下的SQL Server"应用商店"** 框中，选择 AG。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-364">Under **Associations**, in the **SQL Server Store** box, select the AG.</span></span> <span data-ttu-id="d2c3f-365">为池中要移动到 AG 的其他任何数据库选择同一组。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-365">Select the same group for any other databases in the pool which you want to move to the AG.</span></span>
    
   - <span data-ttu-id="d2c3f-366">当你确定所有所需的数据库都设置为 AG 时，请单击"**确定"。**</span><span class="sxs-lookup"><span data-stu-id="d2c3f-366">When you're sure that all needed databases are set to the AG, click **OK**.</span></span>
    
9. <span data-ttu-id="d2c3f-367">发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-367">Publish the topology.</span></span> <span data-ttu-id="d2c3f-368">从" **操作"** 菜单中，单击 **"拓扑** "，然后 **发布**。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-368">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="d2c3f-369">然后在确认页中单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="d2c3f-369">Then in the confirmation page click **Next**.</span></span>
    
10. <span data-ttu-id="d2c3f-370">执行一些最后步骤，确保SQL登录名位于 AG 的每个副本上。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-370">Perform some final steps to make sure that the SQL logins are on each of the replicas in the AG.</span></span>
    
    - <span data-ttu-id="d2c3f-371">打开拓扑生成器，从现有 **部署** 中选择"下载拓扑"，然后单击"**确定"。**</span><span class="sxs-lookup"><span data-stu-id="d2c3f-371">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
    - <span data-ttu-id="d2c3f-372">展开 Skype for Business Server、扩展拓扑和SQL Server **应用商店**。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-372">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="d2c3f-373">右键单击SQL AG 的应用商店，然后单击"编辑 **属性"。**</span><span class="sxs-lookup"><span data-stu-id="d2c3f-373">Right-click the SQL store of the new AG, and click **Edit Properties**.</span></span>
    
    - <span data-ttu-id="d2c3f-374">在页面底部，在SQL Server **FQDN** 框中，将值更改为 AG 侦听器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-374">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AG.</span></span>
    
    - <span data-ttu-id="d2c3f-375">发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-375">Publish the topology.</span></span> <span data-ttu-id="d2c3f-376">从" **操作"** 菜单中，单击 **"拓扑** "，然后 **发布**。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-376">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="d2c3f-377">然后在确认页中单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="d2c3f-377">Then in the confirmation page click **Next**.</span></span> <span data-ttu-id="d2c3f-378">然后等待几分钟，以便复制新拓扑。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-378">Then wait a few minutes for the new topology to replicate.</span></span>
    
    - <span data-ttu-id="d2c3f-379">打开 SQL Server Management Studio，然后导航到 AG。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-379">Open SQL Server Management Studio, and navigate to the AG.</span></span> <span data-ttu-id="d2c3f-380">故障转移到辅助副本。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-380">Fail it over to a secondary replica.</span></span>
    
    - <span data-ttu-id="d2c3f-381">打开 Skype for Business Server 命令行管理程序 并键入以下 cmdlet，以SQL此副本上的登录名：</span><span class="sxs-lookup"><span data-stu-id="d2c3f-381">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
      ```powershell
      Install-CsDatabase -Update
      ```

      - <span data-ttu-id="d2c3f-382">重复上述两个步骤 (将组故障转移到辅助副本，然后对)  `Install-CsDatabase -Update` 副本使用前两个步骤。</span><span class="sxs-lookup"><span data-stu-id="d2c3f-382">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
