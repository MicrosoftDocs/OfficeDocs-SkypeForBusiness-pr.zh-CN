---
title: Skype 通话质量仪表板部署业务服务器 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 287f64f5-0f8a-455a-8979-7b34bf0217bb
description: 摘要： 了解调用质量仪表板的部署过程。 通话质量仪表板是用于业务服务器 2015年的 Skype 的工具。
ms.openlocfilehash: ff8f9bae2c292720bb3fd9943bc541a8eeb6759c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-call-quality-dashboard-for-skype-for-business-server-2015"></a><span data-ttu-id="66314-104">Skype 通话质量仪表板部署业务服务器 2015</span><span class="sxs-lookup"><span data-stu-id="66314-104">Deploy Call Quality Dashboard for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="66314-105">**摘要：**了解调用质量仪表板部署过程。</span><span class="sxs-lookup"><span data-stu-id="66314-105">**Summary:** Learn about the deployment process for Call Quality Dashboard.</span></span> <span data-ttu-id="66314-106">通话质量仪表板是用于业务服务器 2015年的 Skype 的工具。</span><span class="sxs-lookup"><span data-stu-id="66314-106">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
## <a name="deployment-overview"></a><span data-ttu-id="66314-107">部署概述</span><span class="sxs-lookup"><span data-stu-id="66314-107">Deployment Overview</span></span>

<span data-ttu-id="66314-108">通话质量仪表板 (CQD) 由三个主要组件组成：</span><span class="sxs-lookup"><span data-stu-id="66314-108">Call Quality Dashboard (CQD) consists of three major components:</span></span>
  
- <span data-ttu-id="66314-109">**存档数据库**，在其中体验质量 (QoE) 并将数据复制存储。</span><span class="sxs-lookup"><span data-stu-id="66314-109">**Archive Database**, where the Quality of Experience (QoE) data is replicated and stored.</span></span>
    
- <span data-ttu-id="66314-110">**多维数据集**，其中 QoE 存档数据库中的数据进行聚合的优化和快速存取。</span><span class="sxs-lookup"><span data-stu-id="66314-110">**Cube**, where data from QoE Archive database is aggregated for optimized and fast access.</span></span>
    
- <span data-ttu-id="66314-111">**门户网站**，在其中用户可以方便地查询和可视化 QoE 数据。</span><span class="sxs-lookup"><span data-stu-id="66314-111">**Portal**, where users can easily query and visualize QoE data.</span></span>
    
![CQD 组件](../../media/ef3359b1-c98b-4cc5-a549-c84c6e03c011.png)
  
<span data-ttu-id="66314-113">QoE 归档文件的安装过程包括创建 QoE 存档数据库、 部署会将数据从移动源 QoE 指标数据库到 QoE 存档数据库中，SQL Server 存储过程设置 SQL Server 代理作业来执行存储以固定间隔的过程。</span><span class="sxs-lookup"><span data-stu-id="66314-113">The setup process for QoE Archive involves creating the QoE Archive database, deploying a SQL Server stored procedure that will move the data from the source QoE Metrics database into QoE Archive database, and setting up the SQL Server Agent job to execute the stored procedure at a regular interval.</span></span> 
  
<span data-ttu-id="66314-114">多维数据集部署 QoE 存档所在、 部署多维数据集，以及将会定期刷新多维数据集的常规 SQL Server 代理作业设置为在用户获取信息。</span><span class="sxs-lookup"><span data-stu-id="66314-114">Cube deployment gets information from the user on where the QoE Archive is located, deploys the cube, and sets up a regular SQL Server agent job that will refresh the cube at a regular interval.</span></span>
  
<span data-ttu-id="66314-115">门户安装创建存储库数据库，用于存储到每个用户的报告查询的 CQD 用户的映射。</span><span class="sxs-lookup"><span data-stu-id="66314-115">Portal install creates a Repository database that stores the mapping of CQD users to each user's reports/queries.</span></span> <span data-ttu-id="66314-116">然后设置 IIS web 应用程序即仪表板用户查看一组预定义的报告，以及自定义和创建自己的查询可视化数据的多维数据集。</span><span class="sxs-lookup"><span data-stu-id="66314-116">It then sets up an IIS web application which is the dashboard where users can see a pre-defined set of reports as well as customize and create their own queries to visualize data from the cube.</span></span> <span data-ttu-id="66314-117">门户安装创建两个其他 web 应用程序公开 Api，可用于以编程方式访问存储库和多维数据集的用户。</span><span class="sxs-lookup"><span data-stu-id="66314-117">The portal install creates two additional web applications that exposes APIs for users to programmatically access the repository and the cube.</span></span> <span data-ttu-id="66314-118">（这些 Api 使用内部的仪表板）。</span><span class="sxs-lookup"><span data-stu-id="66314-118">(These APIs are used internally by the dashboard as well.)</span></span>
  

|<span data-ttu-id="66314-119">**阶段**</span><span class="sxs-lookup"><span data-stu-id="66314-119">**Phase**</span></span>|<span data-ttu-id="66314-120">**步骤**</span><span class="sxs-lookup"><span data-stu-id="66314-120">**Steps**</span></span>|<span data-ttu-id="66314-121">**角色和组成员资格**</span><span class="sxs-lookup"><span data-stu-id="66314-121">**Roles and group membership**</span></span>|<span data-ttu-id="66314-122">**文档**</span><span class="sxs-lookup"><span data-stu-id="66314-122">**Documentation**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="66314-123">安装系统必备组件的硬件和软件。</span><span class="sxs-lookup"><span data-stu-id="66314-123">Install prerequisite hardware and software.</span></span>  <br/> |<span data-ttu-id="66314-124">决定的 CQD 配置，并选择要从中执行安装 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="66314-124">Decide on the CQD configuration, and choose a SQL Server from which to perform the install.</span></span>  <br/> |<span data-ttu-id="66314-125">属于本地 Administrators 组成员的域用户。</span><span class="sxs-lookup"><span data-stu-id="66314-125">Domain user who is a member of the local administrators group.</span></span>  <br/> |<span data-ttu-id="66314-126">部署文档中的"预安装要求"部分。</span><span class="sxs-lookup"><span data-stu-id="66314-126">"Pre-install Requirements" section in the deployment documentation.</span></span>  <br/> |
|<span data-ttu-id="66314-127">安装 CQD。</span><span class="sxs-lookup"><span data-stu-id="66314-127">Install CQD.</span></span>  <br/> |<span data-ttu-id="66314-128">运行 MSI 下部署文档。</span><span class="sxs-lookup"><span data-stu-id="66314-128">Run the MSI following the deployment document.</span></span>  <br/> |<span data-ttu-id="66314-129">若要执行安装程序，安装的帐户必须是本地管理员组成员的域用户和监视服务器上有读取访问权限 QoE 指标数据库。</span><span class="sxs-lookup"><span data-stu-id="66314-129">To perform the setup, the installing account must be a domain user who is a member of the local administrators group and have read access to QoE Metrics database on the Monitoring Server.</span></span>  <br/> |<span data-ttu-id="66314-130">部署文档中的"帐户和部署步骤"部分。</span><span class="sxs-lookup"><span data-stu-id="66314-130">"Accounts and Deployment Steps" sections in the deployment documentation.</span></span>  <br/> |
|<span data-ttu-id="66314-131">授予用户访问权。</span><span class="sxs-lookup"><span data-stu-id="66314-131">Grant user access.</span></span>  <br/> |<span data-ttu-id="66314-132">用于管理门户的用户身份验证，我们建议使用 URL 授权，IIS 7.0 中引入了。</span><span class="sxs-lookup"><span data-stu-id="66314-132">For managing user authorization to the Portal, we recommend using URL Authorization, which was introduced in IIS 7.0.</span></span> <span data-ttu-id="66314-133">有关详细信息，请参阅[了解 IIS 7.0 的 URL 授权](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization)。</span><span class="sxs-lookup"><span data-stu-id="66314-133">For more information, see [Understanding IIS 7.0 URL Authorization](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).</span></span>  <br/> |<span data-ttu-id="66314-134">属于本地 Administrators 组成员的域用户。</span><span class="sxs-lookup"><span data-stu-id="66314-134">Domain user who is a member of the local administrators group.</span></span>  <br/> |<span data-ttu-id="66314-135">管理门户中部署文档部分的用户访问。</span><span class="sxs-lookup"><span data-stu-id="66314-135">Managing User Access for the Portal section in the deployment documentation.</span></span>  <br/> |
|<span data-ttu-id="66314-136">可选： 提供子网的映射信息。</span><span class="sxs-lookup"><span data-stu-id="66314-136">Optional: Provide subnet mapping information.</span></span>  <br/> |<span data-ttu-id="66314-137">填充网络和构建映射 QoE 存档数据库中的表。</span><span class="sxs-lookup"><span data-stu-id="66314-137">Populate network and building mapping tables in QoE Archive database.</span></span>  <br/> |<span data-ttu-id="66314-138">有到 QoE 存档数据库的写访问权限的帐户。</span><span class="sxs-lookup"><span data-stu-id="66314-138">An account with write access to the QoE Archive database.</span></span>  <br/> |<span data-ttu-id="66314-139">"提供子网信息"一节中的用户文档。</span><span class="sxs-lookup"><span data-stu-id="66314-139">"Supplying Subnet Information" section in the user documentation.</span></span>  <br/> |
   
## 

<span data-ttu-id="66314-140">设置基础结构和安装软件，涉及到的呼叫质量仪表板部署。</span><span class="sxs-lookup"><span data-stu-id="66314-140">Deployment of Call Quality Dashboard involves setting up the infrastructure and installing the software.</span></span> <span data-ttu-id="66314-141">下面的过程概述了该进程。</span><span class="sxs-lookup"><span data-stu-id="66314-141">The following procedure outlines the process.</span></span>
  
### <a name="deployment-steps"></a><span data-ttu-id="66314-142">部署步骤</span><span class="sxs-lookup"><span data-stu-id="66314-142">Deployment Steps</span></span>

1. <span data-ttu-id="66314-143">将 CallQualityDashboard.msi 复制到 CQD 的存档数据库组件的安装位置的计算机 （这是已安装的 SQL Server 的计算机）。</span><span class="sxs-lookup"><span data-stu-id="66314-143">Copy the CallQualityDashboard.msi to the machine where the archive database component of CQD is to be installed (this is the machine that has SQL Server installed).</span></span> 
    
2. <span data-ttu-id="66314-144">执行 MSI （Windows 会提示使用管理员权限运行，这样做）。</span><span class="sxs-lookup"><span data-stu-id="66314-144">Execute the MSI (Windows will prompt to run with administrator privilege, do so).</span></span> 
    
3. <span data-ttu-id="66314-145">接受最终用户许可协议。</span><span class="sxs-lookup"><span data-stu-id="66314-145">Accept the EULA.</span></span>
    
4. <span data-ttu-id="66314-146">选择目标文件夹位置与调用质量仪表板组件相关的文件将位于或接受默认位置。</span><span class="sxs-lookup"><span data-stu-id="66314-146">Select the destination folder where files related to Call Quality Dashboard components will be located or accept the default location.</span></span>
    
5. <span data-ttu-id="66314-147">选择所有的功能。</span><span class="sxs-lookup"><span data-stu-id="66314-147">Select all features.</span></span>
    
6. <span data-ttu-id="66314-148">在 QoE 存档配置页上，提供了以下信息：</span><span class="sxs-lookup"><span data-stu-id="66314-148">At the QoE Archive Configuration page, provide the following information:</span></span>
    
   - <span data-ttu-id="66314-149">**QoE 标准 SQL Server:**QoE 指标数据库所在的 SQL Server 实例名称 （这将是数据源）。</span><span class="sxs-lookup"><span data-stu-id="66314-149">**QoE Metrics SQL Server:** SQL Server instance name for where the QoE Metrics DB is located (this will be the data source).</span></span>
    
   - <span data-ttu-id="66314-150">**QoE 存档 SQL Server 名称：**这是只读字段并固定到本地计算机的完全合格的域名称。</span><span class="sxs-lookup"><span data-stu-id="66314-150">**QoE Archive SQL Server Name:** This is read-only field and fixed to the fully qualified domain name of the local machine.</span></span> <span data-ttu-id="66314-151">只能在本地计算机上可以安装存档数据库。</span><span class="sxs-lookup"><span data-stu-id="66314-151">Archive DB can be installed only on the local machine.</span></span>
    
   - <span data-ttu-id="66314-152">**QoE 存档的 SQL Server 实例：**为存档数据库旨在创建一个本地 SQL Server 实例名称。</span><span class="sxs-lookup"><span data-stu-id="66314-152">**QoE Archive SQL Server Instance:** A local SQL Server instance name for where the Archive DB is to be created.</span></span> <span data-ttu-id="66314-153">若要使用默认的 SQL Server 实例，请将此字段留空。</span><span class="sxs-lookup"><span data-stu-id="66314-153">To use a default SQL Server instance, leave this field blank.</span></span> <span data-ttu-id="66314-154">若要使用 SQL Server 的命名的实例，请指定实例名称 (例如后的名称"\")。</span><span class="sxs-lookup"><span data-stu-id="66314-154">To use a named SQL Server instance, specify the instance name (e.g. the name after the "\").</span></span>
    
   - <span data-ttu-id="66314-155">**QoE 存档数据库：**默认情况下，此选项设置为"创建新数据库"。</span><span class="sxs-lookup"><span data-stu-id="66314-155">**QoE Archive Database:** By default, this option is set to "Create new database".</span></span> <span data-ttu-id="66314-156">由于不支持存档数据库升级，可以在其下使用了"使用现有数据库"选项的唯一事物是现有的存档数据库是否具有相同的架构生成安装。</span><span class="sxs-lookup"><span data-stu-id="66314-156">Since Archive DB upgrade is not supported, the only circumstance under which the "Use existing database" option can be used is if the existing Archive database has the same schema as the build to be installed.</span></span>
    
   - <span data-ttu-id="66314-157">**数据库文件目录：**存档数据库的数据库文件 （.mdf 和.ldf） 应放置的位置的路径。</span><span class="sxs-lookup"><span data-stu-id="66314-157">**Database File Directory:** Path to where the database files (.mdf and .ldf) for the Archive DB should be placed.</span></span> <span data-ttu-id="66314-158">这应该是在一个驱动器上 (推荐使用的硬件配置中的 HDD2) 独立于操作系统。</span><span class="sxs-lookup"><span data-stu-id="66314-158">This should be on a drive (HDD2 in the recommended hardware configuration) separate from the OS.</span></span> <span data-ttu-id="66314-159">请注意，因为文件的名称安装在固定的以避免任何潜在的冲突，建议空白目录与文件不能使用。</span><span class="sxs-lookup"><span data-stu-id="66314-159">Note that since the file names are fixed in the install, to avoid any potential conflict, it is recommended that a blank directory with no files be used.</span></span>
    
   - <span data-ttu-id="66314-160">**使用多个分区：**默认设置为"多个分区"，这需要商业智能版或企业版的 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="66314-160">**Use Multiple Partitions:** The default is set to "Multiple partition", which requires Business Intelligence edition or Enterprise edition of SQL Server.</span></span> <span data-ttu-id="66314-161">标准版中，请选择"单个分区"选项。</span><span class="sxs-lookup"><span data-stu-id="66314-161">For Standard edition, select "Single Partition" option.</span></span> <span data-ttu-id="66314-162">请注意，是否使用单个分区，则多维数据集的处理性能可能会受到影响。</span><span class="sxs-lookup"><span data-stu-id="66314-162">Note that cube processing performance may be impacted if Single Partition is used.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="66314-163">完成安装程序后，使用多个分区选项对所选内容不能更改。</span><span class="sxs-lookup"><span data-stu-id="66314-163">The selection for Use Multiple Partitions option cannot be changed once Setup completes.</span></span> <span data-ttu-id="66314-164">要更改它，该多维数据集功能必须是第一个卸载并重新安装使用控制面板中的"更改"选项。</span><span class="sxs-lookup"><span data-stu-id="66314-164">In order to change it, the Cube feature needs to be first uninstalled and then reinstalled using "Change" option in Control Panel.</span></span> 
  
   - <span data-ttu-id="66314-165">**分区文件目录：**QoE 存档数据库的分区的放置位置的路径。</span><span class="sxs-lookup"><span data-stu-id="66314-165">**Partition File Directory:** Path to where the partitions for the QoE Archive database should be placed.</span></span> <span data-ttu-id="66314-166">这应该是在一个驱动器上 (推荐使用的硬件配置中的 HDD3) 独立于操作系统驱动器和 SQL 数据库日志文件驱动器。</span><span class="sxs-lookup"><span data-stu-id="66314-166">This should be on a drive (HDD3 in the recommended hardware configuration) separate from the OS drive and SQL database log files drive.</span></span> <span data-ttu-id="66314-167">请注意，因为文件的名称安装在固定的以避免任何潜在的冲突，建议空白目录与文件不能使用。</span><span class="sxs-lookup"><span data-stu-id="66314-167">Note that since the file names are fixed in the install, to avoid any potential conflict, it is recommended that a blank directory with no files be used.</span></span>
    
   - <span data-ttu-id="66314-168">**SQL 代理作业用户用户名&amp;密码：**域服务帐户名和密码 （遮蔽） 将用来运行"QoE 存档数据"（它将运行该存储的过程获取数据从 QoE 指标数据库到存档数据库，因此，该帐户必须具有读取访问权限 QoE 指标数据库，SQL Server 代理作业的步骤 如在帐户部分所示。</span><span class="sxs-lookup"><span data-stu-id="66314-168">**SQL Agent Job User - User Name &amp; Password:** Domain service account name and password (masked) that will be used to run the "QoE Archive Data" step of the SQL Server Agent job (which will run the stored procedure to fetch data from QoE Metrics DB into Archive DB, so this account must have read access to QoE Metrics DB, as indicated under Accounts section.</span></span> <span data-ttu-id="66314-169">此帐户还需要有一个登录 QoE 存档的 SQL Server 实例中）。</span><span class="sxs-lookup"><span data-stu-id="66314-169">This account also needs to have a login in the QoE Archive SQL Server Instance).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="66314-170">如 NT SERVICE\MSSQLSERVER 下运行 SQL Server 实例的帐户必须具有访问/安装成功上面给出的目录的权限。</span><span class="sxs-lookup"><span data-stu-id="66314-170">The account that the SQL Server instance is running under, such as NT SERVICE\MSSQLSERVER, must have access/permission to the directories given above for the installation to succeed.</span></span> <span data-ttu-id="66314-171">有关详细信息，请参阅[配置文件系统数据库引擎访问权限](https://msdn.microsoft.com/en-us/library/jj219062%28v=sql.110%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="66314-171">For details, see [Configure File System Permissions for Database Engine Access](https://msdn.microsoft.com/en-us/library/jj219062%28v=sql.110%29.aspx)</span></span>
  
7. <span data-ttu-id="66314-172">在单击下一步，安装程序将执行系统必备检查和报告，如果遇到任何问题。</span><span class="sxs-lookup"><span data-stu-id="66314-172">Upon clicking next, the installer will perform pre-requisite checks and report if any issues are encountered.</span></span> <span data-ttu-id="66314-173">当所有系统必备检查处理过程中，安装程序将转到多维数据集配置页。</span><span class="sxs-lookup"><span data-stu-id="66314-173">When all pre-requisite checks pass, the installer will go to the Cube Configuration page.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="66314-174">如果安装程序显示 QoE 存档的 SQL Server 实例的 SQL Server 代理服务当前未运行一条警告消息，可以继续安装，但安装后，请确保 SQL 代理服务正在运行，并将启动类型设置为自动运行计划的作业。</span><span class="sxs-lookup"><span data-stu-id="66314-174">If the installer shows a warning message that the SQL Server Agent service for the QoE Archive SQL Server instance is currently not running, installation can proceed, but post installation please make sure that SQL Agent service is running and set the Startup type to Automatic so that the scheduled Job runs.</span></span> 
  
8. <span data-ttu-id="66314-175">在多维数据集配置页上，提供了以下信息：</span><span class="sxs-lookup"><span data-stu-id="66314-175">At Cube Configuration page, provide the following information:</span></span>
    
   - <span data-ttu-id="66314-176">**QoE 存档 SQL Server 名称：**这是只读字段并固定到本地计算机的完全合格的域名称。</span><span class="sxs-lookup"><span data-stu-id="66314-176">**QoE Archive SQL Server Name:** This is read-only field and fixed to the fully qualified domain name of the local machine.</span></span> <span data-ttu-id="66314-177">多维数据集可以安装仅从机器具有 QoE 存档数据库 （请注意。</span><span class="sxs-lookup"><span data-stu-id="66314-177">Cube can be installed only from the machine that has QoE Archive database (Note.</span></span> <span data-ttu-id="66314-178">多维数据集本身可能安装在远程计算机上。</span><span class="sxs-lookup"><span data-stu-id="66314-178">Cube itself may be installed on a remote machine.</span></span> <span data-ttu-id="66314-179">请参见下文）</span><span class="sxs-lookup"><span data-stu-id="66314-179">See below)</span></span>
    
   - <span data-ttu-id="66314-180">**QoE 存档的 SQL Server 实例：**QoE 存档数据库所在的 SQL Server 实例名称。</span><span class="sxs-lookup"><span data-stu-id="66314-180">**QoE Archive SQL Server Instance:** SQL Server instance name for where the QoE Archive DB is located.</span></span> <span data-ttu-id="66314-181">若要指定默认的 SQL Server 实例，请将此字段留空。</span><span class="sxs-lookup"><span data-stu-id="66314-181">To specify a default SQL Server instance, leave this field blank.</span></span> <span data-ttu-id="66314-182">若要指定命名的 SQL Server 实例，输入实例名称 (例如后的名称"\")。</span><span class="sxs-lookup"><span data-stu-id="66314-182">To specify a named SQL Server instance, enter the instance name (e.g. the name after the "\").</span></span> <span data-ttu-id="66314-183">如果选择 QoE 档案组件的安装，此字段将预先填充 QoE 存档配置页面上提供的值。</span><span class="sxs-lookup"><span data-stu-id="66314-183">If QoE Archive component was selected for the install, this field will be pre-populated with the value provided on the QoE Archive Configuration page.</span></span>
    
   - <span data-ttu-id="66314-184">**多维数据集的分析服务器：**创建多维数据集所在的 SQL Server 分析服务实例名称。</span><span class="sxs-lookup"><span data-stu-id="66314-184">**Cube Analysis Server:** SQL Server Analysis Service instance name for where the cube is to be created.</span></span> <span data-ttu-id="66314-185">这可以是另一台计算机，但执行安装的用户必须是服务器管理员的目标 SQL Server 分析服务实例的成员。</span><span class="sxs-lookup"><span data-stu-id="66314-185">This can be a different machine but the installing user has to be a member of Server administrators of the target SQL Server Analysis Service instance.</span></span>
    
    > [!NOTE]
    >  <span data-ttu-id="66314-186">有关配置 Analysis Services 服务器管理员权限的详细信息，请参阅[授予服务器管理员权限 (Analysis Services)](https://msdn.microsoft.com/en-us/library/ms174561.aspx)</span><span class="sxs-lookup"><span data-stu-id="66314-186">For more information about configuring Analysis Services Server Administrator Permissions, see [Grant Server Administrator Permissions (Analysis Services)](https://msdn.microsoft.com/en-us/library/ms174561.aspx)</span></span>
  
   - <span data-ttu-id="66314-187">**使用多个分区：**默认设置为"多个分区"，这需要商业智能版或企业版的 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="66314-187">**Use Multiple Partitions:** The default is set to "Multiple partition", which requires Business Intelligence edition or Enterprise edition of SQL Server.</span></span> <span data-ttu-id="66314-188">标准版中，请选择"单个分区"选项。</span><span class="sxs-lookup"><span data-stu-id="66314-188">For Standard edition, select "Single Partition" option.</span></span> <span data-ttu-id="66314-189">请注意，是否使用单个分区，则多维数据集的处理性能可能会受到影响。</span><span class="sxs-lookup"><span data-stu-id="66314-189">Note that cube processing performance may be impacted if Single Partition is used .</span></span>
    
    > [!NOTE]
    >  <span data-ttu-id="66314-190">完成安装程序后，使用多个分区选项对所选内容不能更改。</span><span class="sxs-lookup"><span data-stu-id="66314-190">The selection for Use Multiple Partitions option cannot be changed once Setup completes.</span></span> <span data-ttu-id="66314-191">要更改它，该多维数据集功能必须是第一个卸载并重新安装使用控制面板中的"更改"选项。</span><span class="sxs-lookup"><span data-stu-id="66314-191">In order to change it, the Cube feature needs to be first uninstalled and then reinstalled using "Change" option in Control Panel.</span></span>
  
   - <span data-ttu-id="66314-192">**多维数据集的用户的用户名&amp;密码：**域服务帐户名和密码 （遮蔽） 将触发处理多维数据集。</span><span class="sxs-lookup"><span data-stu-id="66314-192">**Cube User - User Name &amp; Password:** Domain service account name and password (masked) that will trigger the cube processing.</span></span> <span data-ttu-id="66314-193">如果选择 QoE 档案组件的安装，此字段将 SQL 代理作业用户提供存档配置页上的值预先填充但建议，以便安装程序可以授予指定一个不同的域服务帐户对其最低所需的权限。</span><span class="sxs-lookup"><span data-stu-id="66314-193">If QoE Archive component was selected for the install, this field will be pre-populated with the value provided on the Archive Configuration page for the SQL Agent Job User, but we recommend specifying a different domain service account so that Setup can grant the least required privilege to it.</span></span>
    
9. <span data-ttu-id="66314-194">当单击下一步，将执行另一轮验证，将报告任何问题。</span><span class="sxs-lookup"><span data-stu-id="66314-194">When clicking next, another round of validation will be performed and any issue will be reported.</span></span> <span data-ttu-id="66314-195">在成功完成验证，安装程序将进入门户配置页。</span><span class="sxs-lookup"><span data-stu-id="66314-195">Upon successful completion of the validation, the installer will go to the Portal Configuration page.</span></span> 
    
10. <span data-ttu-id="66314-196">在入口配置页上，提供了以下信息：</span><span class="sxs-lookup"><span data-stu-id="66314-196">At Portal Configuration page, provide the following information:</span></span>
    
    - <span data-ttu-id="66314-197">**QoE 存档的 SQL Server:**QoE 存档数据库所在的 SQL Server 实例名称。</span><span class="sxs-lookup"><span data-stu-id="66314-197">**QoE Archive SQL Server:** SQL Server instance name for where the QoE Archive database is located.</span></span> <span data-ttu-id="66314-198">注意，与 QoE 存档配置页和多维数据集配置页，不同的计算机名称不固定的必须提供。</span><span class="sxs-lookup"><span data-stu-id="66314-198">Note that unlike the QoE Archive Configuration page and the Cube Configuration page, the machine name is not fixed and must be provided.</span></span> <span data-ttu-id="66314-199">如果选择 QoE 档案组件的安装，此字段将预先填充 QoE 存档配置页面上提供的值。</span><span class="sxs-lookup"><span data-stu-id="66314-199">If QoE Archive component was selected for the install, this field will be pre-populated with the value provided on the QoE Archive Configuration page.</span></span>
    
    - <span data-ttu-id="66314-200">**多维数据集的分析服务器：**SQL Server 分析服务实例名称设置为该多维数据集所在的位置。</span><span class="sxs-lookup"><span data-stu-id="66314-200">**Cube Analysis Server:** SQL Server Analysis Service instance name for where the cube is located.</span></span> <span data-ttu-id="66314-201">如果安装选择多维数据集的组件，此字段将预先填充多维数据集配置页面上提供的值。</span><span class="sxs-lookup"><span data-stu-id="66314-201">If Cube component was selected for the install, this field will be pre-populated with the value provided on the Cube Configuration page.</span></span>
    
    - <span data-ttu-id="66314-202">**存储库 SQL Server:**创建存储库数据库所在的 SQL Server 实例名称。</span><span class="sxs-lookup"><span data-stu-id="66314-202">**Repository SQL Server:** SQL Server instance name where the Repository database is to be created.</span></span> <span data-ttu-id="66314-203">如果前面的设置 （在其他组件） 提供了 QoE 存档数据库所在的 SQL Server 实例名称，此字段将预先填充 QoE 存档数据库的 SQL Server 实例名称。</span><span class="sxs-lookup"><span data-stu-id="66314-203">If the SQL Server instance name for where the QoE Archive database is located has been provided earlier in the setup (in other components), this field will be pre-populated with the QoE Archive DB SQL Server instance name.</span></span> <span data-ttu-id="66314-204">这可以是任何 SQL Server 实例。</span><span class="sxs-lookup"><span data-stu-id="66314-204">This can be any SQL Server instance.</span></span>
    
    - <span data-ttu-id="66314-205">**存储库数据库：**默认情况下该选项设置为"创建新数据库"。</span><span class="sxs-lookup"><span data-stu-id="66314-205">**Repository Database:** By default the option is set to "Create new database".</span></span> <span data-ttu-id="66314-206">由于不支持存储库数据库升级，在"使用现有数据库"选项可以使用机制的唯一情况是如果现有存储库数据库具有相同的架构生成安装。</span><span class="sxs-lookup"><span data-stu-id="66314-206">Since Repository DB upgrade is not supported, the only circumstance under which the "Use existing database" option can be used is if the existing Repository DB has the same schema as the build to be installed.</span></span>
    
    - <span data-ttu-id="66314-207">**IIS 应用程序池用户的用户名&amp;密码：**下应执行 IIS 应用程序池帐户。</span><span class="sxs-lookup"><span data-stu-id="66314-207">**IIS App Pool User - User Name &amp; Password:** The account that the IIS application pool should execute under.</span></span> <span data-ttu-id="66314-208">如果选择了内置的系统帐户，用户名称和密码字段将灰显。</span><span class="sxs-lookup"><span data-stu-id="66314-208">The User Name and Password fields will be grayed out if built-in system accounts are selected.</span></span> <span data-ttu-id="66314-209">如果"其他"选择从下拉框中，以便用户可以输入域服务帐户信息，仅将启用这些字段。</span><span class="sxs-lookup"><span data-stu-id="66314-209">These fields will only be enabled if "Other" is selected from the drop down box so the user can enter the domain service account information.</span></span>
    
11. <span data-ttu-id="66314-210">当单击下一步，将进行验证的最终轮以确保 SQL Server 实例都可以访问使用提供的凭据，并且 IIS 的计算机上可用。</span><span class="sxs-lookup"><span data-stu-id="66314-210">When clicking next, the final round of validation will be done to ensure that the SQL Server instances are accessible using the credentials provided and that IIS is available on the machine.</span></span> <span data-ttu-id="66314-211">在成功完成验证，安装程序将继续安装。</span><span class="sxs-lookup"><span data-stu-id="66314-211">Upon successful completion of the validation, the installer will proceed with the setup.</span></span> 
    
<span data-ttu-id="66314-212">完成安装程序后，很可能 SQL Server 代理作业将在进行中，执行初始加载 QoE 数据和多维数据集处理。</span><span class="sxs-lookup"><span data-stu-id="66314-212">When the installer is done, most likely the SQL Server Agent job will be in progress, doing the initial load of the QoE data and the cube processing.</span></span> <span data-ttu-id="66314-213">根据中 QoE 数据量，门户将没有数据可供查看尚未。</span><span class="sxs-lookup"><span data-stu-id="66314-213">Depending on the amount of data in QoE, the portal will not have data available for viewing yet.</span></span> <span data-ttu-id="66314-214">要检查的数据负载和多维数据集处理的状态，请转到`http://<machinename>/CQD/#/Health`。</span><span class="sxs-lookup"><span data-stu-id="66314-214">To check on the status of the data load and cube processing, go to  `http://<machinename>/CQD/#/Health`.</span></span> 
> [!NOTE]
> <span data-ttu-id="66314-215">请注意，检查下载多维数据集处理的状态的 URL 区分大小写。</span><span class="sxs-lookup"><span data-stu-id="66314-215">Note that the URL for checking the status of the download cube processing is case sensitive.</span></span> <span data-ttu-id="66314-216">如果您输入的 URL 不起健康。</span><span class="sxs-lookup"><span data-stu-id="66314-216">If you enter 'health' the URL will not work.</span></span> <span data-ttu-id="66314-217">您必须输入 '健康' 结尾的 URL 以大写 h。</span><span class="sxs-lookup"><span data-stu-id="66314-217">You must enter 'Health' at the end of the URL with a capital H.</span></span> 
  
<span data-ttu-id="66314-218">如果启用了调试模式将显示详细的日志消息。</span><span class="sxs-lookup"><span data-stu-id="66314-218">Detailed log messages will be shown if debug mode is enabled.</span></span> <span data-ttu-id="66314-219">要启用调试模式，转到**为企业 2015 CQD\QoEDataService\web.config Files\Skype %SYSTEMDRIVE%\Program**，并更新下面的行，因此值设置为**True**:</span><span class="sxs-lookup"><span data-stu-id="66314-219">To enable debug mode, go to **%SYSTEMDRIVE%\Program Files\Skype For Business 2015 CQD\QoEDataService\web.config**, and update the following line so the value is set to **True**:</span></span>

```
<add key="QoEDataLib.DebugMode" value="True" /> 
```

<span data-ttu-id="66314-220">门户的主页是通过可访问`http://<machinename>/CQD`。</span><span class="sxs-lookup"><span data-stu-id="66314-220">The main portal page is accessible via  `http://<machinename>/CQD`.</span></span> 
## <a name="managing-user-access-for-the-portal"></a><span data-ttu-id="66314-221">管理门户的用户访问</span><span class="sxs-lookup"><span data-stu-id="66314-221">Managing User Access for the Portal</span></span>

<span data-ttu-id="66314-222">用于管理门户的用户身份验证，我们建议使用 URL 授权，IIS 7.0 中引入了。</span><span class="sxs-lookup"><span data-stu-id="66314-222">For managing user authorization to the Portal, we recommend using URL Authorization, which was introduced in IIS 7.0.</span></span> <span data-ttu-id="66314-223">有关 IIS 安全性的详细信息，请参阅[了解 IIS 7.0 的 URL 授权](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization)。</span><span class="sxs-lookup"><span data-stu-id="66314-223">For more information on IIS security, see [Understanding IIS 7.0 URL Authorization ](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).</span></span>
  
<span data-ttu-id="66314-224">任何 web 站点或 web 应用程序继承的默认 URL 授权配置整个 iis，这通常是"允许所有用户"。</span><span class="sxs-lookup"><span data-stu-id="66314-224">Any web site or web application inherit the default URL Authorization configured for the entire IIS, which is typically "Allow All Users".</span></span> <span data-ttu-id="66314-225">如果需要更具限制性访问门户，然后管理员可以授予访问只有特定的用户组通过编辑"授权规则"。</span><span class="sxs-lookup"><span data-stu-id="66314-225">If access to the Portal needs to be more restrictive, then administrators can grant access to only the specific group of users by editing the "Authorization Rules".</span></span>
  
![部署呼叫质量 - IIS 中的授权规则](../../media/0da80c28-58fe-4aca-94b4-db684389468c.png)
  
> [!NOTE]
> <span data-ttu-id="66314-227">授权规则图标是不会混淆与 ASP.NET 部分，是一种不同的授权机制下".NET 授权"。</span><span class="sxs-lookup"><span data-stu-id="66314-227">The Authorization Rules icon is not to be confused with the ".NET Authorization" under the ASP.NET section, which is a different authorization mechanism.</span></span> 
  
<span data-ttu-id="66314-228">管理员应该首先删除继承"允许所有用户"规则。</span><span class="sxs-lookup"><span data-stu-id="66314-228">Administrators should first remove the inherited "Allow All Users" rule.</span></span> <span data-ttu-id="66314-229">这可以防止任何未经授权的用户访问门户网站。</span><span class="sxs-lookup"><span data-stu-id="66314-229">This prevents any non-authorized users from accessing the Portal.</span></span>
  
![部署 CQD](../../media/fa17ad19-d303-40f8-8324-d13fd67936ab.png)
  
<span data-ttu-id="66314-231">下一步，管理员应添加新的允许规则并授予特定用户访问门户网站的权限。</span><span class="sxs-lookup"><span data-stu-id="66314-231">Next, administrators should add new Allow Rules and give specific users the permission to access the Portal.</span></span> <span data-ttu-id="66314-232">建议创建一个名为"CQDPortalUsers"的本地组来管理用户。</span><span class="sxs-lookup"><span data-stu-id="66314-232">It is recommended that a local Group called "CQDPortalUsers" be created to manage the users.</span></span>
  
![部署呼叫质量仪表板](../../media/8cfdc141-ec89-4552-921b-53196f497cbf.png)
  
<span data-ttu-id="66314-234">配置详细信息都存储在 web.config 位于门户的物理目录。</span><span class="sxs-lookup"><span data-stu-id="66314-234">The configuration details are stored in the web.config located at the Portal's physical directory.</span></span>
  
```
<?xml version="1.0" encoding="UTF-8"?> <configuration> <system.webServer> <security> <authorization> <remove users="*" roles="" verbs="" /> <add accessType="Allow" roles="CQDPortalUsers" /> </authorization> </security> </system.webServer> </configuration> 
```

<span data-ttu-id="66314-235">下一步是配置的 CQD 的仪表板。</span><span class="sxs-lookup"><span data-stu-id="66314-235">The next step is to configure the dashboard of the CQD.</span></span> <span data-ttu-id="66314-236">用户在通过 IIS 进行身份验证后，他们将不得不具有 CQD 目录的文件权限，才能访问 web 入口网站的内容。</span><span class="sxs-lookup"><span data-stu-id="66314-236">After users are authenticated by IIS, they will have to have file permissions on the CQD directory in order to access the web portal content.</span></span> <span data-ttu-id="66314-237">可以更改通过 CQD 目录属性的安全选项卡上的 Acl 添加个别用户或组;但是建议的方法是保持不变的文件权限。</span><span class="sxs-lookup"><span data-stu-id="66314-237">It is possible to change the ACLs through the security tab of the CQD directory properties to add individual users or groups; however the recommended approach is to leave the file permissions untouched.</span></span> <span data-ttu-id="66314-238">相反，更改 IIS 设置以使用 IIS 工作进程访问的 CQD 目录，无论该用户进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="66314-238">Instead, change the IIS setting to use the IIS worker process to access the CQD directory no matter which user is authenticated.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="66314-239">很重要的只需更改此设置的 CQD 的应用程序，而不是针对两个 API 应用程序： QoEDataService 和 QoERepositoryService。</span><span class="sxs-lookup"><span data-stu-id="66314-239">It is important to only change this setting for the CQD application, and not for the two API applications: QoEDataService and QoERepositoryService.</span></span> 
  
### <a name="configuring-file-access-for-the-cqd-dashboard"></a><span data-ttu-id="66314-240">配置文件访问的 CQD （仪表板）</span><span class="sxs-lookup"><span data-stu-id="66314-240">Configuring File Access for the CQD (Dashboard)</span></span>

1. <span data-ttu-id="66314-241">打开 CQD 的配置编辑器。</span><span class="sxs-lookup"><span data-stu-id="66314-241">Open the Configuration Editor for CQD.</span></span>
    
     ![部署呼叫质量仪表板](../../media/544056eb-3090-434e-bae6-321c984029fa.png)
  
2. <span data-ttu-id="66314-243">在部分，选择**system.webServer/serverRuntime**。</span><span class="sxs-lookup"><span data-stu-id="66314-243">Under Section, choose **system.webServer/serverRuntime**.</span></span>
    
     ![部署呼叫质量仪表板](../../media/b0af0e56-21b0-45dd-b610-5381b39319d3.png)
  
3. <span data-ttu-id="66314-245">将 authenticatedUserOverride 更改为**UseWorkerProcessUser**。</span><span class="sxs-lookup"><span data-stu-id="66314-245">Change authenticatedUserOverride to **UseWorkerProcessUser**.</span></span>
    
     ![部署呼叫质量仪表板 - 配置编辑器](../../media/a7c127f5-9a90-4710-afba-1d1e588efb37.png)
  
4. <span data-ttu-id="66314-247">单击右侧的页上的**应用**。</span><span class="sxs-lookup"><span data-stu-id="66314-247">Click **Apply** on the right-hand side of the page.</span></span>
    
## <a name="known-issues"></a><span data-ttu-id="66314-248">已知的问题</span><span class="sxs-lookup"><span data-stu-id="66314-248">Known Issues</span></span>

<span data-ttu-id="66314-249">在极少数情况下，安装程序无法在 IIS 中创建了正确的设置。</span><span class="sxs-lookup"><span data-stu-id="66314-249">In rare cases, the installer fails to create the correct settings in IIS.</span></span> <span data-ttu-id="66314-250">允许用户登录到 CQD 需要手动更改。</span><span class="sxs-lookup"><span data-stu-id="66314-250">Manual change is required to allow users to log into the CQD.</span></span> <span data-ttu-id="66314-251">如果用户在登录时遇到问题，请按照下列步骤操作：</span><span class="sxs-lookup"><span data-stu-id="66314-251">If users are having trouble logging in, please follow these steps:</span></span>
  
1. <span data-ttu-id="66314-252">打开启动 IIS 管理器中，然后定位到默认的 Web 站点。</span><span class="sxs-lookup"><span data-stu-id="66314-252">Open up IIS Manager, and navigate to Default Web Site.</span></span>
    
     ![部署呼叫质量仪表板](../../media/dc6007aa-870b-4d70-867d-32ffd937063b.png)
  
2. <span data-ttu-id="66314-254">单击"身份验证"。</span><span class="sxs-lookup"><span data-stu-id="66314-254">Click on "Authentication".</span></span> <span data-ttu-id="66314-255">如果"匿名身份验证"、"ASP.NET 模拟"、"表单身份验证"和"Windows 身份验证"与以下所示的设置不匹配，手动进行更改以匹配下面的设置。</span><span class="sxs-lookup"><span data-stu-id="66314-255">If the "Anonymous Authentication", "ASP.NET Impersonation", "Form Authentication", and "Windows Authentication" do not match the settings shown below, manually change them to match the settings below.</span></span> <span data-ttu-id="66314-256">应禁用所有其他身份验证机制。</span><span class="sxs-lookup"><span data-stu-id="66314-256">All other authentication mechanisms should be disabled.</span></span>
    
     ![部署呼叫质量仪表板](../../media/5d9e38fb-8a50-41a2-a423-3ce983a83d0c.png)
  
3. <span data-ttu-id="66314-258">有关"Windows 身份验证"，请单击高级设置在右侧。</span><span class="sxs-lookup"><span data-stu-id="66314-258">For "Windows Authentication", click on Advanced Settings on the right-hand side.</span></span>
    
     ![部署呼叫质量仪表板](../../media/cad29486-df40-4cc9-82f3-bbdaca52d9ca.png)
  
4. <span data-ttu-id="66314-260">将"扩展保护"设置为接受，请选中"启用内核模式身份验证"框。</span><span class="sxs-lookup"><span data-stu-id="66314-260">Set "Extended Protection" to Accept and check the "Enable Kernel-mode authentication" box.</span></span>
    
     ![部署呼叫质量仪表板](../../media/0ab2dda1-0001-4747-8cfc-072e9368b6cb.png)
  
5. <span data-ttu-id="66314-262">重复上述步骤为每个"CQD"、"QoEDataService"和"QoERepositoryService"项下"默认 Web 站点"。</span><span class="sxs-lookup"><span data-stu-id="66314-262">Repeat the above steps for each of the "CQD", "QoEDataService", and "QoERepositoryService" entries below "Default Web Site".</span></span>
    
<span data-ttu-id="66314-263">HTTP 和 HTTPS 端口绑定安装程序将在默认端口号 （端口 80 (http） 和 HTTPS 端口 443 上创建端口绑定。</span><span class="sxs-lookup"><span data-stu-id="66314-263">For HTTP and HTTPS port bindings the installer will create port bindings on the default port numbers (port 80 for HTTP and port 443 for HTTPS).</span></span> <span data-ttu-id="66314-264">如果使用这些绑定的计算机上没有另一个网站，将有冲突和无法预测的 IIS 行为。</span><span class="sxs-lookup"><span data-stu-id="66314-264">If there is another website on the machine that uses these bindings, there will be a conflict and the IIS behavior cannot be predicted.</span></span> <span data-ttu-id="66314-265">若要避免此问题的最佳方法是请确保没有其他网站都映射到端口 80 和 443 安装 CQD 之前。</span><span class="sxs-lookup"><span data-stu-id="66314-265">The best way to avoid this problem is to make sure that no other websites are mapped to ports 80 and 443 before installing CQD.</span></span> 
  
<span data-ttu-id="66314-266">若要启用 SSL/TLS 在 IIS 中，强迫用户通过安全的 HTTPS，而不是 HTTP 连接：</span><span class="sxs-lookup"><span data-stu-id="66314-266">To enable SSL/TLS in IIS and force users to connect via secure HTTPS instead of HTTP:</span></span>
  
1. <span data-ttu-id="66314-267">在 IIS 中配置安全套接字层，请参见[IIS 7 中配置安全套接字层](https://technet.microsoft.com/en-us/library/cc771438%28v=ws.10%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="66314-267">Configure Secure Sockets Layer in IIS, see [Configuring Secure Sockets Layer in IIS 7](https://technet.microsoft.com/en-us/library/cc771438%28v=ws.10%29.aspx).</span></span> <span data-ttu-id="66314-268">完成后，替换`http`与`https`。</span><span class="sxs-lookup"><span data-stu-id="66314-268">Once done, replace  `http` with `https`.</span></span>
    
2. <span data-ttu-id="66314-269">在 SQL Server 连接启用 TLS 的说明，请参阅[如何启用 SSL 加密技术，通过使用 Microsoft 管理控制台的 SQL Server 的实例](https://support.microsoft.com/en-us/kb/316898/)。</span><span class="sxs-lookup"><span data-stu-id="66314-269">For instructions on enabling TLS in the SQL Server connections, see [How to enable SSL encryption for an instance of SQL Server by using Microsoft Management Console ](https://support.microsoft.com/en-us/kb/316898/).</span></span>
    
### <a name="cube-sync-fails"></a><span data-ttu-id="66314-270">多维数据集同步失败</span><span class="sxs-lookup"><span data-stu-id="66314-270">Cube Sync Fails</span></span>

<span data-ttu-id="66314-271">QoEMetrics 可能包含一些无效的记录基于最终用户时钟。</span><span class="sxs-lookup"><span data-stu-id="66314-271">QoEMetrics may contain some invalid records based on end user clocks.</span></span> <span data-ttu-id="66314-272">如果时间偏差大于 60 年，多维数据集导入将失败。</span><span class="sxs-lookup"><span data-stu-id="66314-272">If the time skew is greater than 60 yrs, the cube import will fail.</span></span>
  
 <span data-ttu-id="66314-273">检查最小和最大值开始时间/结束时间使用下面的选定内容。</span><span class="sxs-lookup"><span data-stu-id="66314-273">Check the Min and Max StartTime/EndTime using the selections below.</span></span> <span data-ttu-id="66314-274">寻找和删除记录得过去和很远的将来可以忽略它们，它们会分解同步进程。</span><span class="sxs-lookup"><span data-stu-id="66314-274">Look for and delete records in the far past and very distant future, they can be disregarded and they will break up the sync processes.</span></span>
  
- <span data-ttu-id="66314-275">选择 MIN(StartTime) 从 CqdPartitionedStreamView</span><span class="sxs-lookup"><span data-stu-id="66314-275">Select MIN(StartTime) FROM CqdPartitionedStreamView</span></span>
    
- <span data-ttu-id="66314-276">选择 MAX(StartTime) 从 CqdPartitionedStreamView</span><span class="sxs-lookup"><span data-stu-id="66314-276">Select MAX(StartTime) FROM CqdPartitionedStreamView</span></span>
    
- <span data-ttu-id="66314-277">选择 MIN(EndTime) 从 CqdPartitionedStreamView</span><span class="sxs-lookup"><span data-stu-id="66314-277">Select MIN(EndTime) FROM CqdPartitionedStreamView</span></span>
    
- <span data-ttu-id="66314-278">选择 MAX(EndTime) 从 CqdPartitionedStreamView</span><span class="sxs-lookup"><span data-stu-id="66314-278">Select MAX(EndTime) FROM CqdPartitionedStreamView</span></span>
    
## <a name="post-install-tasks"></a><span data-ttu-id="66314-279">安装后任务</span><span class="sxs-lookup"><span data-stu-id="66314-279">Post-install tasks</span></span>

### <a name="importing-buildings-and-networks"></a><span data-ttu-id="66314-280">导入建筑物和网络</span><span class="sxs-lookup"><span data-stu-id="66314-280">Importing Buildings and Networks</span></span>

<span data-ttu-id="66314-281">后安装 CQD，请执行以下配置任务：</span><span class="sxs-lookup"><span data-stu-id="66314-281">After Installing CQD, perform the following configuration tasks:</span></span>
  
1. <span data-ttu-id="66314-282">定义生成类型 （推荐）</span><span class="sxs-lookup"><span data-stu-id="66314-282">Define Building types (recommended)</span></span>
    
2. <span data-ttu-id="66314-283">定义构建所有权类型 （推荐）</span><span class="sxs-lookup"><span data-stu-id="66314-283">Define Building Ownership types (recommended)</span></span>
    
3. <span data-ttu-id="66314-284">定义网络类型 （强烈推荐）</span><span class="sxs-lookup"><span data-stu-id="66314-284">Define Network types (highly recommended)</span></span>
    
4. <span data-ttu-id="66314-285">导入建筑物 （推荐）</span><span class="sxs-lookup"><span data-stu-id="66314-285">Import Buildings (recommended)</span></span>
    
5. <span data-ttu-id="66314-286">导入子网 （推荐）</span><span class="sxs-lookup"><span data-stu-id="66314-286">Import Subnets (recommended)</span></span>
    
### <a name="define-building-types"></a><span data-ttu-id="66314-287">定义生成类型</span><span class="sxs-lookup"><span data-stu-id="66314-287">Define Building Types</span></span>

<span data-ttu-id="66314-288">建筑类型用于描述不同建筑物定义或您的组织的类型。</span><span class="sxs-lookup"><span data-stu-id="66314-288">Building types are used to describe the different buildings definitions or types within your organization.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="66314-289">此步骤是可选的但建议这样做。</span><span class="sxs-lookup"><span data-stu-id="66314-289">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="66314-290">示例</span><span class="sxs-lookup"><span data-stu-id="66314-290">Examples</span></span>
  
- <span data-ttu-id="66314-291">总部</span><span class="sxs-lookup"><span data-stu-id="66314-291">Headquarters</span></span>
    
- <span data-ttu-id="66314-292">远程办公室</span><span class="sxs-lookup"><span data-stu-id="66314-292">Remote Office</span></span>
    
- <span data-ttu-id="66314-293">合资的位置</span><span class="sxs-lookup"><span data-stu-id="66314-293">Joint-venture location</span></span>
    
 <span data-ttu-id="66314-294">**SQL 语法示例**</span><span class="sxs-lookup"><span data-stu-id="66314-294">**Sample SQL Syntax**</span></span>
  
```
INSERT INTO
[dbo].[CqdBuildingType]
([BuildingTypeId],
[BuildingTypeDesc])
VALUES
(1, 
'Headquarters') 
  
```

<span data-ttu-id="66314-295">BuildingTypeId 和 BuildingTypeDesc 参数是必需的。</span><span class="sxs-lookup"><span data-stu-id="66314-295">The BuildingTypeId and BuildingTypeDesc parameters are required.</span></span>
  
### <a name="define-building-ownership-types"></a><span data-ttu-id="66314-296">定义构建所有权类型</span><span class="sxs-lookup"><span data-stu-id="66314-296">Define Building Ownership Types</span></span>

<span data-ttu-id="66314-297">所有权类型用于区分拥有的与租赁的资产。</span><span class="sxs-lookup"><span data-stu-id="66314-297">Ownership types are used to distinguish owned vs leased assets.</span></span>
  
> [!NOTE]
> <span data-ttu-id="66314-298">此步骤是可选的但建议这样做。</span><span class="sxs-lookup"><span data-stu-id="66314-298">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="66314-299">示例</span><span class="sxs-lookup"><span data-stu-id="66314-299">Examples</span></span>
  
- <span data-ttu-id="66314-300">Contoso 租借非-RE&amp;F</span><span class="sxs-lookup"><span data-stu-id="66314-300">Contoso Leased non-RE&amp;F</span></span>
    
- <span data-ttu-id="66314-301">Contoso 租用 RE&amp;F</span><span class="sxs-lookup"><span data-stu-id="66314-301">Contoso Leased RE&amp;F</span></span>
    
- <span data-ttu-id="66314-302">Contoso 拥有</span><span class="sxs-lookup"><span data-stu-id="66314-302">Contoso Owned</span></span>
    
- <span data-ttu-id="66314-303">租用的子公司</span><span class="sxs-lookup"><span data-stu-id="66314-303">Subsidiary Leased</span></span>
    
 <span data-ttu-id="66314-304">**SQL 语法示例**</span><span class="sxs-lookup"><span data-stu-id="66314-304">**Sample SQL Syntax**</span></span>
  
```
INSERT INTO
[dbo].[CqdBuildingOwnershipType]
([OwnershipTypeId],
[OwnershipTypeDesc],
)

VALUES
(1,
'Contoso Owned',
)
```

<span data-ttu-id="66314-305">OwnershipTypeId 和 OwnershipTypeDesc 参数是必需的。</span><span class="sxs-lookup"><span data-stu-id="66314-305">The OwnershipTypeId and OwnershipTypeDesc parameters are required.</span></span> 
  
### <a name="define-network-names"></a><span data-ttu-id="66314-306">定义网络名称</span><span class="sxs-lookup"><span data-stu-id="66314-306">Define Network Names</span></span>

<span data-ttu-id="66314-307">网络类型用来描述不同类型的组织中的网络。</span><span class="sxs-lookup"><span data-stu-id="66314-307">Network Types are used to describe different types of networks within the organization.</span></span> <span data-ttu-id="66314-308">这使您能够筛选 （或筛选出） 特定网络类型。</span><span class="sxs-lookup"><span data-stu-id="66314-308">This gives you the ability to filter on (or filter out) specific Network Types.</span></span>
  
> [!NOTE]
> <span data-ttu-id="66314-309">强烈建议来定义网络名称，但它是可选的。</span><span class="sxs-lookup"><span data-stu-id="66314-309">It is highly recommended to define Network Names, but it is optional.</span></span> <span data-ttu-id="66314-310">如果您决定定义网络名称，请确保每个 CqdNetwork 条目具有 0 BuildingId。</span><span class="sxs-lookup"><span data-stu-id="66314-310">If you decide to not define network names, ensure the each CqdNetwork entry has a BuildingId of 0.</span></span> 
  
<span data-ttu-id="66314-311">示例</span><span class="sxs-lookup"><span data-stu-id="66314-311">Examples</span></span>
  
- <span data-ttu-id="66314-312">VPN</span><span class="sxs-lookup"><span data-stu-id="66314-312">VPN</span></span>
    
- <span data-ttu-id="66314-313">实验室</span><span class="sxs-lookup"><span data-stu-id="66314-313">LAB</span></span>
    
 <span data-ttu-id="66314-314">**SQL 语法示例**</span><span class="sxs-lookup"><span data-stu-id="66314-314">**Sample SQL Syntax**</span></span>
  
```
INSERT INTO [dbo].[CqdNetworkName] 
( [NetworkName]
,[NetworkType]
 ) 
VALUES
('VPN','VPN') 
```

<span data-ttu-id="66314-315">NetworkNameID 和 NetworkName 参数需要，NetworkType 参数是可选的但建议。</span><span class="sxs-lookup"><span data-stu-id="66314-315">The NetworkNameID and NetworkName parameters are required, the NetworkType parameter is optional but recommended.</span></span>
  
### <a name="import-buildings"></a><span data-ttu-id="66314-316">导入建筑物</span><span class="sxs-lookup"><span data-stu-id="66314-316">Import Buildings</span></span>

<span data-ttu-id="66314-317">导入建筑物可以获取生成特定的见解 （每个构建 WiFi/有线等差调用。） 的能力。</span><span class="sxs-lookup"><span data-stu-id="66314-317">Importing Buildings gives you the ability to get building specific insights (poor calls per building on WiFi/Wired, etc.).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="66314-318">此步骤是可选的但建议这样做。</span><span class="sxs-lookup"><span data-stu-id="66314-318">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="66314-319">在导入之前新构建您应该已经标识预定义的 BuildingKey。</span><span class="sxs-lookup"><span data-stu-id="66314-319">Before you Import a new building you should already have a predefined BuildingKey identified.</span></span> <span data-ttu-id="66314-320">为此，发出"从 CqdBuilding 中选择 MAX(BuildingKey)"SQL 命令，若要确定当前值并添加到结果 1。</span><span class="sxs-lookup"><span data-stu-id="66314-320">To do that, issue the "SELECT MAX(BuildingKey) FROM CqdBuilding" SQL command to identify the current value and add 1 to the result.</span></span>
  
 <span data-ttu-id="66314-321">**SQL 语法示例**</span><span class="sxs-lookup"><span data-stu-id="66314-321">**Sample SQL Syntax**</span></span>
  
```
INSERT INTO [dbo].[CqdBuilding] 
( [BuildingKey]
,[BuildingName]
,[BuildingShortName]
,[OwnershipTypeId],
[BuildingTypeId]
)
VALUES
(2, 'Ann Arbor', 'AA', 0, 0)
```

<span data-ttu-id="66314-322">BuildingKey、 BuildingName、 BuildingShortName、 OwnershipTypeId，BuildingTypeId 参数是必需的其他参数是可选的。</span><span class="sxs-lookup"><span data-stu-id="66314-322">The BuildingKey, BuildingName, BuildingShortName, OwnershipTypeId, BuildingTypeId parameters are required, the other parameters are optional.</span></span>
  
### <a name="import-subnets"></a><span data-ttu-id="66314-323">导入子网</span><span class="sxs-lookup"><span data-stu-id="66314-323">Import Subnets</span></span>

<span data-ttu-id="66314-324">导入建筑物可以获取生成特定的见解 （每个构建 WiFi/有线等差调用。） 的能力。</span><span class="sxs-lookup"><span data-stu-id="66314-324">Importing Buildings gives you the ability to get building specific insights (poor calls per building on WiFi/Wired, etc.).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="66314-325">此步骤是可选的但建议这样做。</span><span class="sxs-lookup"><span data-stu-id="66314-325">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="66314-326">导入子网，然后将它们映射到的最后一步导入建筑物。</span><span class="sxs-lookup"><span data-stu-id="66314-326">Import Subnets and map them to the Buildings imported in the last step.</span></span> <span data-ttu-id="66314-327">如果您决定不填充 NetworkName，请确保在此表中的每个条目使用 0 NetworkNameID。</span><span class="sxs-lookup"><span data-stu-id="66314-327">If you decided not to populate NetworkName, ensure each entry in this table uses a NetworkNameID of 0.</span></span>
  
 <span data-ttu-id="66314-328">**SQL 语法示例**</span><span class="sxs-lookup"><span data-stu-id="66314-328">**Sample SQL Syntax**</span></span>
  
```
INSERT INTO [dbo].[CqdNetwork] 
([Network]
,[NetworkNameID]
,[BuildingKey]
,[UpdatedDate]
)

VALUES
 ('172.16.254.0',0,1,'2015-11-11')
```

<span data-ttu-id="66314-329">网络上，并且 UpdatedDate 参数是必需的其他参数是可选的。</span><span class="sxs-lookup"><span data-stu-id="66314-329">The Network, and UpdatedDate parameters are required, the other parameters are optional.</span></span>
  
### <a name="optional-bssid"></a><span data-ttu-id="66314-330">可选： BSSID</span><span class="sxs-lookup"><span data-stu-id="66314-330">Optional: BSSID</span></span>

<span data-ttu-id="66314-331">填充 BSSID 信息为您提供了额外的 WiFi 流关联的控制器或无线电。</span><span class="sxs-lookup"><span data-stu-id="66314-331">Populating BSSID information gives you additional WiFi stream correlation by controller or radio.</span></span> <span data-ttu-id="66314-332">这是加上建筑物或子网的筛选。</span><span class="sxs-lookup"><span data-stu-id="66314-332">This is in addition to filtering by building or subnet.</span></span> 
  
 <span data-ttu-id="66314-333">**SQL 语法示例**</span><span class="sxs-lookup"><span data-stu-id="66314-333">**Sample SQL Syntax**</span></span>
  
```
INSERT INTO [dbo].[CqdBssid]
([Ap],
[Bss],
[Building],
[ess],
[phy]
)
VALUES
('AP1','00-00-00-00-00-00','Aruba AP 1','Controller1','bgn')
```

<span data-ttu-id="66314-334">**CqdBssidTable 的详细信息**</span><span class="sxs-lookup"><span data-stu-id="66314-334">**CqdBssidTable Details**</span></span>

|<span data-ttu-id="66314-335">**CQD 所示**</span><span class="sxs-lookup"><span data-stu-id="66314-335">**As shown in CQD**</span></span>|<span data-ttu-id="66314-336">**CQDBssid 表**</span><span class="sxs-lookup"><span data-stu-id="66314-336">**CQDBssid Table**</span></span>|<span data-ttu-id="66314-337">**示例输入**</span><span class="sxs-lookup"><span data-stu-id="66314-337">**Example inputs**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="66314-338">Ap NName</span><span class="sxs-lookup"><span data-stu-id="66314-338">Ap NName</span></span>  <br/> |<span data-ttu-id="66314-339">接入点</span><span class="sxs-lookup"><span data-stu-id="66314-339">AP</span></span>  <br/> |<span data-ttu-id="66314-340">AP1</span><span class="sxs-lookup"><span data-stu-id="66314-340">AP1</span></span>  <br/> |
|<span data-ttu-id="66314-341">BBssid</span><span class="sxs-lookup"><span data-stu-id="66314-341">BBssid</span></span>  <br/> |<span data-ttu-id="66314-342">BSS</span><span class="sxs-lookup"><span data-stu-id="66314-342">BSS</span></span>  <br/> |<span data-ttu-id="66314-343">00-00-00-00-00-00 （必须使用分隔符的 fformat）</span><span class="sxs-lookup"><span data-stu-id="66314-343">00-00-00-00-00-00 (you must use the delimited fformat)</span></span>  <br/> |
|<span data-ttu-id="66314-344">控制器</span><span class="sxs-lookup"><span data-stu-id="66314-344">Controller</span></span>  <br/> |<span data-ttu-id="66314-345">大楼</span><span class="sxs-lookup"><span data-stu-id="66314-345">Building</span></span>  <br/> |<span data-ttu-id="66314-346">阿鲁巴岛 AP 7</span><span class="sxs-lookup"><span data-stu-id="66314-346">Aruba AP 7</span></span>  <br/> |
|<span data-ttu-id="66314-347">设备</span><span class="sxs-lookup"><span data-stu-id="66314-347">Device</span></span>  <br/> |<span data-ttu-id="66314-348">ess</span><span class="sxs-lookup"><span data-stu-id="66314-348">ess</span></span>  <br/> |<span data-ttu-id="66314-349">Controller1</span><span class="sxs-lookup"><span data-stu-id="66314-349">Controller1</span></span>  <br/> |
|<span data-ttu-id="66314-350">无线电</span><span class="sxs-lookup"><span data-stu-id="66314-350">Radio</span></span>  <br/> |<span data-ttu-id="66314-351">phy</span><span class="sxs-lookup"><span data-stu-id="66314-351">phy</span></span>  <br/> |<span data-ttu-id="66314-352">bgn</span><span class="sxs-lookup"><span data-stu-id="66314-352">bgn</span></span>  <br/> |
   
### <a name="processing-the-imported-data"></a><span data-ttu-id="66314-353">处理导入的数据</span><span class="sxs-lookup"><span data-stu-id="66314-353">Processing the imported data</span></span>

<span data-ttu-id="66314-354">默认情况下，导入构建/网络数据后它将仅适用于生成后的时间点的记录。</span><span class="sxs-lookup"><span data-stu-id="66314-354">By default, after you import building/network data it will only apply to records generated after that point in time.</span></span> 
  
<span data-ttu-id="66314-355">标记此新数据与所有以前的记录，您将需要运行 CqdUpdateBuilding 存储过程，如下所示：</span><span class="sxs-lookup"><span data-stu-id="66314-355">To tag all the previous records with this new data, you will need to run the CqdUpdateBuilding stored procedure as shown below:</span></span> 
  
<span data-ttu-id="66314-356">为它提供您的第一个记录的日期 （标识使用来自 CqdPartitionedStreamView SQL 选择 MIN(StartTime) 命令），明天，然后最后两个值为空的结束日期。</span><span class="sxs-lookup"><span data-stu-id="66314-356">Give it the date of your first record( identify that using the Select MIN(StartTime) FROM CqdPartitionedStreamView SQL command ), an EndDate of tomorrow, then NULL for the last two values.</span></span>
  
<span data-ttu-id="66314-357">流数据与关联数据后，SSIS 多维数据集必须重新处理的所有记录。</span><span class="sxs-lookup"><span data-stu-id="66314-357">Once the data is associated with stream data, the SSIS Cube needs to reprocess all records.</span></span> <span data-ttu-id="66314-358">这同样适用时批量添加 BSSID/ISP 数据。</span><span class="sxs-lookup"><span data-stu-id="66314-358">This also applies when bulk adding BSSID/ISP data.</span></span> <span data-ttu-id="66314-359">确保选中"全过程"的了。</span><span class="sxs-lookup"><span data-stu-id="66314-359">Ensure that "Process Full" is selected.</span></span>
  

