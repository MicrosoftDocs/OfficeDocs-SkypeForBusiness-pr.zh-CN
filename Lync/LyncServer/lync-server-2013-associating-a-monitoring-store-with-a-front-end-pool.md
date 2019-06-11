---
title: 'Lync Server 2013: 将监视存储与前端池关联'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Associating a monitoring store with a Front End pool
ms:assetid: d3a20d5e-3f24-4cff-bc9b-4f84fea30e6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205271(v=OCS.15)
ms:contentKeyID: 48185439
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4c1153d0d20cf5a3855a36f8d7aa24a8d9d4680b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837907"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="associating-a-monitoring-store-with-a-front-end-pool-in-lync-server-2013"></a><span data-ttu-id="3defa-102">将监视存储与 Lync Server 2013 中的前端池相关联</span><span class="sxs-lookup"><span data-stu-id="3defa-102">Associating a monitoring store with a Front End pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3defa-103">_**主题上次修改时间:** 2013-04-22_</span><span class="sxs-lookup"><span data-stu-id="3defa-103">_**Topic Last Modified:** 2013-04-22_</span></span>

<span data-ttu-id="3defa-104">在 Microsoft Lync Server 2013 中, 监视数据只能在已与监视存储相关联的前端池上收集, 通常执行的任务是在拓扑生成器中定义一个前端池。</span><span class="sxs-lookup"><span data-stu-id="3defa-104">In Microsoft Lync Server 2013 monitoring data can only be collected on Front End pools that have been associated with a monitoring store, a task typically carried out you define a Front End pool in Topology Builder.</span></span> <span data-ttu-id="3defa-105">要将监控存储与新的前端池关联，请确保在“定义新的前端池”向导的“**选择功能**”页上选择“**监控（用户体验质量度量的呼叫详细信息记录）**”选项。</span><span class="sxs-lookup"><span data-stu-id="3defa-105">To associate a monitoring store with a new Front End pool, make sure that you select the option **Monitoring (call detail recording and logging of quality of experience metrics)** on the **Select Features** page of the Define New Front End Pool wizard.</span></span> <span data-ttu-id="3defa-106">请注意，如果选择此选项，还必须指定一个 SQL 存储才能完成向导；但是，在运行向导时该存储不必存在。</span><span class="sxs-lookup"><span data-stu-id="3defa-106">Note that, if you select this option, you must also specify a SQL store in order to complete the wizard; however, this store does not have to exist at the time you run the wizard.</span></span> <span data-ttu-id="3defa-107">这意味着可以先将池与监控存储关联，然后再设置和配置该存储。</span><span class="sxs-lookup"><span data-stu-id="3defa-107">That means that you can first associate a pool with a monitoring store, then later setup and configure that store.</span></span>

<span data-ttu-id="3defa-108">或者，可以通过完成以下过程将现有前端池与新的或不同的监控存储关联：</span><span class="sxs-lookup"><span data-stu-id="3defa-108">Alternatively, you can associate an existing Front End pool with a new or different monitoring store by completing the following procedure:</span></span>

1.  <span data-ttu-id="3defa-109">单击 "**开始**", 单击 "**所有程序**", 单击 " **Microsoft Lync server 2013**", 然后单击 " **Lync server 拓扑生成器**"。</span><span class="sxs-lookup"><span data-stu-id="3defa-109">Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="3defa-110">在“**拓扑生成器**”对话框中，选择“**从现有部署下载拓扑**”，然后单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="3defa-110">In the **Topology Builder** dialog box, select **Download Topology from existing deployment** and then click **OK**.</span></span>

3.  <span data-ttu-id="3defa-p102">在“**另存为**”对话框中，为当前拓扑输入一个文件名，然后单击“**保存**”。如果新拓扑出现问题，可以取回并重新发布已保存的拓扑。</span><span class="sxs-lookup"><span data-stu-id="3defa-p102">In the **Save As** dialog box, enter a file name for your current topology and then click **Save**. The saved topology can later be retrieved and re-published in case there are problems with the new topology.</span></span>

4.  <span data-ttu-id="3defa-113">在拓扑生成器中, 展开 " **Lync Server 2013**", 展开包含前端池的网站的名称, 然后单击 "扩展**企业版前端池**"。</span><span class="sxs-lookup"><span data-stu-id="3defa-113">In Topology Builder, expand **Lync Server 2013**, expand the name of the site containing the Front End pool, then click expand **Enterprise Edition Front End pools**.</span></span>

5.  <span data-ttu-id="3defa-114">右键单击要与监控存储关联的池的名称，然后单击“**编辑属性**”。</span><span class="sxs-lookup"><span data-stu-id="3defa-114">Right-click the name of the pool to be associated with the monitoring store and then click **Edit Properties**.</span></span>

6.  <span data-ttu-id="3defa-p103">在“**编辑属性**”对话框中的“**常规**”选项卡上，选择选项“**监控（CDR 和 QoE 度量）**”，然后从“**监控 SQL Server 存储**”下拉列表中选择现有 SQL Server 数据库。（或者，单击“**新建**”将池与新的数据库存储关联。）如果选择使用新的数据库存储，则在“**定义新的 SQL 存储**”对话框中输入“**Sql Server FQDN**”框中 SQL Server 计算机的完全限定域名。如果想要将默认 SQL Server 实例用于该存储，请选择“**默认实例**”；否则选择“**命名实例**”并在“**命名实例**”框中输入实例名称。</span><span class="sxs-lookup"><span data-stu-id="3defa-p103">In the **Edit Properties** dialog box, on the **General** tab, select the option **Monitoring (CDR and QoE metrics)** and then select an existing SQL Server database from the **Monitoring SQL Server store** dropdown list. (Or, click **New** to associate the pool with a new database store.) If you choose to use a new database store then, in the **Define New SQL Store** dialog box, enter the fully qualified domain name of the SQL Server computer in the **Sql Server FQDN** box. If you want to use the default SQL Server instance for that store select **Default Instance**; otherwise select **Named Instance** and enter the instance name in the **Named Instance** box.</span></span>
    
    <span data-ttu-id="3defa-p104">通过“**编辑属性**”对话框还可以创建监控数据库的 SQL 镜像（通过一个 SQL 镜像可以维护两个监控数据库副本，一个副本存储在监控存储计算机上，另一个存储在 SQL 镜像计算机上）。要启用镜像，请选择“**此 SQL 实例处于镜像关系中**”，然后在“**镜像端口号**”框中输入镜像服务器的端口号。</span><span class="sxs-lookup"><span data-stu-id="3defa-p104">The **Edit Properties** dialog box also gives you the option of creating a SQL mirror for your monitoring database (a SQL mirror enables you to maintain two copies of your monitoring database, one copy stored on the monitoring store computer and the other on the SQL mirror computer). To enable mirroring, select T**his SQL instance is in mirroring relation** and enter the port number for the mirror server in the **Mirroring port number** box.</span></span>

7.  <span data-ttu-id="3defa-120">在“**编辑属性**”对话框中，单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="3defa-120">In the **Edit Properties** dialog box, click **OK**.</span></span>

<span data-ttu-id="3defa-121">将监控存储与前端池关联后，必须发布新拓扑才能使更改生效。</span><span class="sxs-lookup"><span data-stu-id="3defa-121">After associating the monitoring store with a Front End pool you must publish the new topology before the changes take effect.</span></span> <span data-ttu-id="3defa-122">若要发布新拓扑, 请在拓扑生成器中完成以下步骤:</span><span class="sxs-lookup"><span data-stu-id="3defa-122">To publish your new topology, complete the following steps in Topology Builder:</span></span>

1.  <span data-ttu-id="3defa-123">单击“**操作**”，指向“**拓扑**”，然后单击“**发布**”。</span><span class="sxs-lookup"><span data-stu-id="3defa-123">Click **Action**, point to **Topology**, and then click **Publish**.</span></span>

2.  <span data-ttu-id="3defa-124">在发布拓扑向导的“**发布拓扑**”页上，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="3defa-124">In the Publish Topology wizard, on the **Publish the topology** page, click **Next**.</span></span>

3.  <span data-ttu-id="3defa-125">在“**发布向导完成**”页上，单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="3defa-125">On the **Publishing wizard complete** page, click **Finish**.</span></span>

<span data-ttu-id="3defa-126">拓扑发布完毕后，可以在将要承载监控存储的计算机上安装监控数据库。</span><span class="sxs-lookup"><span data-stu-id="3defa-126">After the topology has been published you can then install the monitoring database on the computer that will host the monitoring store.</span></span> <span data-ttu-id="3defa-127">可以使用 Lync Server Management Shell 和 Windows PowerShell 安装监视数据库。</span><span class="sxs-lookup"><span data-stu-id="3defa-127">The monitoring database can be installed by using the Lync Server Management Shell and Windows PowerShell.</span></span> <span data-ttu-id="3defa-128">若要在运行 Lync Server 命令行管理程序的同一台计算机上安装数据库 (即, 要在运行 Lync Server 命令行管理程序的同一台计算机上安装数据库), 请在相应的计算机上启动管理外壳程序, 然后键入以下命令, 然后按 ENTER:</span><span class="sxs-lookup"><span data-stu-id="3defa-128">To install the database locally (that is, to install the database on the same computer where you are running the Lync Server Management Shell), start the Management Shell on the appropriate computer, then type in the following command and press ENTER:</span></span>

    Install-CsDatabase -LocalDatabases

<span data-ttu-id="3defa-129">运行前面的命令时, 安装 CsDatabase 将读取当前的 Lync Server 拓扑, 确定需要在本地计算机上安装的数据库, 然后自动安装并配置每个数据库。</span><span class="sxs-lookup"><span data-stu-id="3defa-129">When you run the preceding command, Install-CsDatabase will read the current Lync Server topology, determine which databases need to be installed on the local computer, and then automatically install and configure each of those databases.</span></span>

<span data-ttu-id="3defa-130">要在远程计算机（即，没有运行命令行管理程序的计算机）上安装数据库，必须包含至少两个参数：ConfiguredDatabases 参数和 SqlServerFqdn 参数。</span><span class="sxs-lookup"><span data-stu-id="3defa-130">To install the database on a remote computer (that is, a computer other than the computer where the Management Shell is running) you must include at least two parameters: the ConfiguredDatabases parameter and the SqlServerFqdn parameter.</span></span> <span data-ttu-id="3defa-131">这些参数告诉 CsDatabase cmdlet 检索 Lync Server 拓扑, 然后在 SqlServerFqdn 参数指定的计算机上安装和配置所需的数据库。</span><span class="sxs-lookup"><span data-stu-id="3defa-131">These parameters tell the Install-CsDatabase cmdlet to retrieve the Lync Server topology and then install and configure the required databases on the computer specified by the SqlServerFqdn parameter.</span></span> <span data-ttu-id="3defa-132">SqlServerFqdn 参数使用的参数值必须表示要安装数据库的计算机的完全限定域名。</span><span class="sxs-lookup"><span data-stu-id="3defa-132">The SqlServerFqdn parameter must use a parameter value representing the fully qualified domain name of the computer where the databases are to be installed.</span></span>

<span data-ttu-id="3defa-133">例如，以下命令在计算机 atl-sql-001.litwareinc.com 上安装监控数据库：</span><span class="sxs-lookup"><span data-stu-id="3defa-133">For example, this command installs the monitoring database on the computer atl-sql-001.litwareinc.com:</span></span>

    Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn atl-sql-001.litwareinc.com

<span data-ttu-id="3defa-134">或者, 你可以通过在将承载监视存储的计算机上运行 Lync Server 部署向导来安装监视数据库。</span><span class="sxs-lookup"><span data-stu-id="3defa-134">Alternatively, you can install the monitoring database by running the Lync Server Deployment Wizard on the computer that will host the monitoring store.</span></span> <span data-ttu-id="3defa-135">为此，请登录到相应的计算机并完成以下过程：</span><span class="sxs-lookup"><span data-stu-id="3defa-135">To do this, log on to the appropriate computer and complete the following procedure:</span></span>

1.  <span data-ttu-id="3defa-136">单击 "**开始**", 单击 "**所有程序**", 单击 " **Microsoft Lync server 2013**", 然后单击 " **Lync server 部署向导**"。</span><span class="sxs-lookup"><span data-stu-id="3defa-136">Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Deployment Wizard**.</span></span>

2.  <span data-ttu-id="3defa-137">在部署向导中, 单击 "**安装或更新 Lync Server 系统**"。</span><span class="sxs-lookup"><span data-stu-id="3defa-137">In the Deployment Wizard, click **Install or Update Lync Server System**.</span></span>

3.  <span data-ttu-id="3defa-138">在 "**部署**" 页面上的 "**步骤 2: 设置" 或 "删除 Lync Server 组件**" 下, 再次单击 "**运行**"。</span><span class="sxs-lookup"><span data-stu-id="3defa-138">On the **Deploy** page, under **Step 2: Setup or Remove Lync Server Components**, click **Run Again**.</span></span>

4.  <span data-ttu-id="3defa-139">在 "安装 Lync 服务器组件向导" 的 "**安装 Lync 服务器组件**" 页面上, 单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="3defa-139">In the Setup Lync Server components wizard, on the **Setup Lync Server components** page, click **Next**.</span></span>

5.  <span data-ttu-id="3defa-140">在 "**指定指向 MSIs 的路径**" 页面上, 键入文件 Ocscore 的路径 (Lync Server 安装媒体附带的文件), 然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="3defa-140">On the **Specify path to MSIs** page, type the path to the file Ocscore.msi (a file included with your Lync Server installation media) and then click **Next**.</span></span>

6.  <span data-ttu-id="3defa-141">在“**正在执行命令**”页上，单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="3defa-141">On the **Executing Commands** page, click **Finish**.</span></span>

<span data-ttu-id="3defa-142">若要确保所有所需的 Lync 服务器服务均已启动, 请单击标题下的 "**运行**" 下的 "**步骤 4:** 在**部署**页面上启动服务"</span><span class="sxs-lookup"><span data-stu-id="3defa-142">To ensure that all the required Lync Server services have started, click **Run** under the heading **Step 4: Start Services** on the **Deploy** page</span></span>

</div>

<span> </span>

</div>

</div>

</div>

