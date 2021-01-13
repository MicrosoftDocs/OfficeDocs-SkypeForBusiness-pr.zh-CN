---
title: 将监控存储与 Skype for Business Server 中的前端池关联
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
ms.assetid: d3a20d5e-3f24-4cff-bc9b-4f84fea30e6b
description: 摘要：了解如何将前端池与 Skype for Business Server 使用的监视存储关联。
ms.openlocfilehash: 4ec48e99da9a827cdc40d87c42ec764bda66a416
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830542"
---
# <a name="associate-a-monitoring-store-with-a-front-end-pool-in-skype-for-business-server"></a><span data-ttu-id="4331c-103">将监控存储与 Skype for Business Server 中的前端池关联</span><span class="sxs-lookup"><span data-stu-id="4331c-103">Associate a monitoring store with a Front End pool in Skype for Business Server</span></span> 
<span data-ttu-id="4331c-104">**摘要：** 了解如何将前端池与 Skype for Business Server 使用的监控存储关联。</span><span class="sxs-lookup"><span data-stu-id="4331c-104">**Summary:** Learn how to associate Front End pools with a monitoring store used by Skype for Business Server.</span></span>
  
<span data-ttu-id="4331c-105">在 Skype for Business Server 中，监控数据只能在与监控存储关联的前端池（通常在拓扑生成器中定义前端池时执行）上收集。</span><span class="sxs-lookup"><span data-stu-id="4331c-105">In Skype for Business Server, monitoring data can only be collected on Front End pools that have been associated with a monitoring store, a task typically carried out when you define a Front End pool in Topology Builder.</span></span>
  
## <a name="associate-a-monitoring-store-with-a-front-end-pool"></a><span data-ttu-id="4331c-106">将监控存储与前端池关联</span><span class="sxs-lookup"><span data-stu-id="4331c-106">Associate a monitoring store with a Front End pool</span></span>

 <span data-ttu-id="4331c-107">要将监控存储与新的前端池关联，请确保在“定义新的前端池”向导的“选择功能”页上选择“监控（用户体验质量度量的呼叫详细信息记录）”选项。</span><span class="sxs-lookup"><span data-stu-id="4331c-107">To associate a monitoring store with a new Front End pool, make sure that you select the option **Monitoring (call detail recording and logging of quality of experience metrics)** on the **Select Features** page of the Define New Front End Pool wizard.</span></span> <span data-ttu-id="4331c-108">请注意，如果选择此选项，还必须指定一个 SQL 存储才能完成向导；但是，在运行向导时该存储不必存在。</span><span class="sxs-lookup"><span data-stu-id="4331c-108">Note that, if you select this option, you must also specify a SQL store in order to complete the wizard; however, this store does not have to exist at the time you run the wizard.</span></span> <span data-ttu-id="4331c-109">这意味着可以先将池与监控存储关联，然后再设置和配置该存储。</span><span class="sxs-lookup"><span data-stu-id="4331c-109">That means that you can first associate a pool with a monitoring store, then later setup and configure that store.</span></span>
  
<span data-ttu-id="4331c-110">或者，可以通过完成以下过程将现有前端池与新的或不同的监控存储关联：</span><span class="sxs-lookup"><span data-stu-id="4331c-110">Alternatively, you can associate an existing Front End pool with a new or different monitoring store by completing the following procedure:</span></span>
  
1. <span data-ttu-id="4331c-111">单击 **"开始**"，**单击"所有** 程序"，再单击 **"Skype for Business Server 2015"，** 然后单击 **"Skype for Business Server 拓扑生成器"。**</span><span class="sxs-lookup"><span data-stu-id="4331c-111">Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server Topology Builder**.</span></span>
    
2. <span data-ttu-id="4331c-112">在“拓扑生成器”对话框中，选择“从现有部署下载拓扑”，然后单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="4331c-112">In the **Topology Builder** dialog box, select **Download Topology from existing deployment** and then click **OK**.</span></span>
    
3. <span data-ttu-id="4331c-p102">在“另存为”对话框中，为当前拓扑输入一个文件名，然后单击“保存”。如果新拓扑出现问题，可以取回并重新发布已保存的拓扑。</span><span class="sxs-lookup"><span data-stu-id="4331c-p102">In the **Save As** dialog box, enter a file name for your current topology and then click **Save**. The saved topology can later be retrieved and re-published in case there are problems with the new topology.</span></span>
    
4. <span data-ttu-id="4331c-115">在拓扑生成器中，展开 **Skype for Business Server，** 展开包含前端池的站点的名称，然后单击展开 Enterprise Edition **前端池**。</span><span class="sxs-lookup"><span data-stu-id="4331c-115">In Topology Builder, expand **Skype for Business Server**, expand the name of the site containing the Front End pool, then click expand **Enterprise Edition Front End pools**.</span></span>
    
5. <span data-ttu-id="4331c-116">右键单击要与监控存储关联的池的名称，然后单击“编辑属性”。</span><span class="sxs-lookup"><span data-stu-id="4331c-116">Right-click the name of the pool to be associated with the monitoring store and then click **Edit Properties**.</span></span>
    
6. <span data-ttu-id="4331c-p103">在“编辑属性”对话框中的“常规”选项卡上，选择选项“监控（CDR 和 QoE 度量）”，然后从“监控 SQL Server 存储”下拉列表中选择现有 SQL Server 数据库。（或者，单击“新建”将池与新的数据库存储关联。）如果选择使用新的数据库存储，则在“定义新的 SQL 存储”对话框中输入“Sql Server FQDN”框中 SQL Server 计算机的完全限定域名。如果想要将默认 SQL Server 实例用于该存储，请选择“默认实例”；否则选择“命名实例”并在“命名实例”框中输入实例名称。</span><span class="sxs-lookup"><span data-stu-id="4331c-p103">In the **Edit Properties** dialog box, on the **General** tab, select the option **Monitoring (CDR and QoE metrics)** and then select an existing SQL Server database from the **Monitoring SQL Server store** dropdown list. (Or, click **New** to associate the pool with a new database store.) If you choose to use a new database store then, in the **Define New SQL Store** dialog box, enter the fully qualified domain name of the SQL Server computer in the **Sql Server FQDN** box. If you want to use the default SQL Server instance for that store select **Default Instance**; otherwise select **Named Instance** and enter the instance name in the **Named Instance** box.</span></span>
    
    <span data-ttu-id="4331c-120">通过“编辑属性”对话框还可以创建监控数据库的 SQL 镜像（通过一个 SQL 镜像可以维护两个监控数据库副本，一个副本存储在监控存储计算机上，另一个存储在 SQL 镜像计算机上）。</span><span class="sxs-lookup"><span data-stu-id="4331c-120">The **Edit Properties** dialog box also gives you the option of creating a SQL mirror for your monitoring database (a SQL mirror enables you to maintain two copies of your monitoring database, one copy stored on the monitoring store computer and the other on the SQL mirror computer).</span></span> <span data-ttu-id="4331c-121">若要启用镜像，请选择其SQL实例为镜像 **关系** ，在镜像端口号框中输入镜像服务器的 **端口** 号。</span><span class="sxs-lookup"><span data-stu-id="4331c-121">To enable mirroring, select T **his SQL instance is in mirroring relation** and enter the port number for the mirror server in the **Mirroring port number** box.</span></span>
    
7. <span data-ttu-id="4331c-122">在“编辑属性”对话框中，单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="4331c-122">In the **Edit Properties** dialog box, click **OK**.</span></span>
    
<span data-ttu-id="4331c-p105">将监控存储与前端池关联后，必须发布新拓扑才能使更改生效。要发布新拓扑，请在拓扑生成器中完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="4331c-p105">After associating the monitoring store with a Front End pool you must publish the new topology before the changes take effect. To publish your new topology, complete the following steps in Topology Builder:</span></span>
  
1. <span data-ttu-id="4331c-125">单击“操作”，指向“拓扑”，然后单击“发布”。</span><span class="sxs-lookup"><span data-stu-id="4331c-125">Click **Action**, point to **Topology**, and then click **Publish**.</span></span>
    
2. <span data-ttu-id="4331c-126">在发布拓扑向导的“发布拓扑”页上，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="4331c-126">In the Publish Topology wizard, on the **Publish the topology** page, click **Next**.</span></span>
    
3. <span data-ttu-id="4331c-127">在“发布向导完成”页上，单击“完成”。</span><span class="sxs-lookup"><span data-stu-id="4331c-127">On the **Publishing wizard complete** page, click **Finish**.</span></span>
    
<span data-ttu-id="4331c-128">拓扑发布完毕后，可以在将要承载监控存储的计算机上安装监控数据库。</span><span class="sxs-lookup"><span data-stu-id="4331c-128">After the topology has been published you can then install the monitoring database on the computer that will host the monitoring store.</span></span> <span data-ttu-id="4331c-129">可以使用 Skype for Business Server 命令行管理程序 安装监控数据库Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="4331c-129">The monitoring database can be installed by using the Skype for Business Server Management Shell and Windows PowerShell.</span></span> <span data-ttu-id="4331c-130">若要在本地安装数据库 (即，若要在运行 Skype for Business Server 命令行管理程序) 的同一计算机上安装数据库，请在相应的计算机上启动命令行管理程序，然后键入以下命令并按 Enter：</span><span class="sxs-lookup"><span data-stu-id="4331c-130">To install the database locally (that is, to install the database on the same computer where you are running the Skype for Business Server Management Shell), start the Management Shell on the appropriate computer, then type in the following command and press ENTER:</span></span>
  
```powershell
Install-CsDatabase -LocalDatabases
```

<span data-ttu-id="4331c-131">运行上述命令时，Install-CsDatabase读取当前的 Skype for Business Server 拓扑，确定需要在本地计算机上安装哪些数据库，然后自动安装和配置其中每个数据库。</span><span class="sxs-lookup"><span data-stu-id="4331c-131">When you run the preceding command, Install-CsDatabase will read the current Skype for Business Server topology, determine which databases need to be installed on the local computer, and then automatically install and configure each of those databases.</span></span>
  
<span data-ttu-id="4331c-132">要在远程计算机（即，没有运行命令行管理程序的计算机）上安装数据库，必须包含至少两个参数：ConfiguredDatabases 参数和 SqlServerFqdn 参数。</span><span class="sxs-lookup"><span data-stu-id="4331c-132">To install the database on a remote computer (that is, a computer other than the computer where the Management Shell is running) you must include at least two parameters: the ConfiguredDatabases parameter and the SqlServerFqdn parameter.</span></span> <span data-ttu-id="4331c-133">这些参数告知 Install-CsDatabase cmdlet 检索 Skype for Business Server 拓扑，然后在 SqlServerFqdn 参数指定的计算机上安装和配置所需的数据库。</span><span class="sxs-lookup"><span data-stu-id="4331c-133">These parameters tell the Install-CsDatabase cmdlet to retrieve the Skype for Business Server topology and then install and configure the required databases on the computer specified by the SqlServerFqdn parameter.</span></span> <span data-ttu-id="4331c-134">SqlServerFqdn 参数使用的参数值必须表示要安装数据库的计算机的完全限定域名。</span><span class="sxs-lookup"><span data-stu-id="4331c-134">The SqlServerFqdn parameter must use a parameter value representing the fully qualified domain name of the computer where the databases are to be installed.</span></span>
  
<span data-ttu-id="4331c-135">例如，以下命令在计算机 atl-sql-001.litwareinc.com 上安装监控数据库：</span><span class="sxs-lookup"><span data-stu-id="4331c-135">For example, this command installs the monitoring database on the computer atl-sql-001.litwareinc.com:</span></span>
  
```powershell
Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn atl-sql-001.litwareinc.com
```

<span data-ttu-id="4331c-136">或者，您可以通过在将承载监控存储的计算机上运行 Skype for Business Server 部署向导来安装监控数据库。</span><span class="sxs-lookup"><span data-stu-id="4331c-136">Alternatively, you can install the monitoring database by running the Skype for Business Server Deployment Wizard on the computer that will host the monitoring store.</span></span> <span data-ttu-id="4331c-137">为此，请登录到相应的计算机并完成以下过程：</span><span class="sxs-lookup"><span data-stu-id="4331c-137">To do this, log on to the appropriate computer and complete the following procedure:</span></span>
  
1. <span data-ttu-id="4331c-138">单击 **"开始**"，**单击"所有** 程序"，再单击 **"Skype for Business Server 2015"，** 然后单击 **"Skype for Business Server 部署向导"。**</span><span class="sxs-lookup"><span data-stu-id="4331c-138">Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server Deployment Wizard**.</span></span>
    
2. <span data-ttu-id="4331c-139">在部署向导中，单击 **"安装或更新 Skype for Business Server 系统"。**</span><span class="sxs-lookup"><span data-stu-id="4331c-139">In the Deployment Wizard, click **Install or Update Skype for Business Server System**.</span></span>
    
3. <span data-ttu-id="4331c-140">在"**部署**"页上的"**步骤 2： 安装或删除 Skype for Business Server 组件**"下，单击"**再次运行"。**</span><span class="sxs-lookup"><span data-stu-id="4331c-140">On the **Deploy** page, under **Step 2: Setup or Remove Skype for Business Server Components**, click **Run Again**.</span></span>
    
4. <span data-ttu-id="4331c-141">在"安装 Skype for Business Server 组件"向导中的"设置 **Skype for Business Server 组件**"页上，单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="4331c-141">In the Setup Skype for Business Server components wizard, on the **Setup Skype for Business Server components** page, click **Next**.</span></span>
    
5. <span data-ttu-id="4331c-142">在"指定 **MSIs** 的路径"页上，键入文件的路径Ocscore.msi (Skype for Business Server 安装媒体中包含的文件，然后单击) 下一 **步**"。</span><span class="sxs-lookup"><span data-stu-id="4331c-142">On the **Specify path to MSIs** page, type the path to the file Ocscore.msi (a file included with your Skype for Business Server installation media) and then click **Next**.</span></span>
    
6. <span data-ttu-id="4331c-143">在“正在执行命令”页上，单击“完成”。</span><span class="sxs-lookup"><span data-stu-id="4331c-143">On the **Executing Commands** page, click **Finish**.</span></span>
    
<span data-ttu-id="4331c-144">若要确保所有所需的 Skype for Business Server 服务已启动，请单击"部署"页上的标题"步骤 **4： 启动** 服务 **"下的"** 运行"</span><span class="sxs-lookup"><span data-stu-id="4331c-144">To ensure that all the required Skype for Business Server services have started, click **Run** under the heading **Step 4: Start Services** on the **Deploy** page</span></span>
  

