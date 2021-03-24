---
title: 部署 Skype for Business Server 的呼叫质量仪表板
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 287f64f5-0f8a-455a-8979-7b34bf0217bb
description: 摘要：了解呼叫质量仪表板的部署过程。 呼叫质量仪表板是 Skype for Business Server 的工具。
ms.openlocfilehash: 1f59209575284035fcdca52e4f18220aa05337af
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51114108"
---
# <a name="deploy-call-quality-dashboard-for-skype-for-business-server"></a><span data-ttu-id="85f7a-104">部署 Skype for Business Server 的呼叫质量仪表板</span><span class="sxs-lookup"><span data-stu-id="85f7a-104">Deploy Call Quality Dashboard for Skype for Business Server</span></span>
 
<span data-ttu-id="85f7a-105">**摘要：** 了解呼叫质量仪表板的部署过程。</span><span class="sxs-lookup"><span data-stu-id="85f7a-105">**Summary:** Learn about the deployment process for Call Quality Dashboard.</span></span> <span data-ttu-id="85f7a-106">呼叫质量仪表板是 Skype for Business Server 的工具。</span><span class="sxs-lookup"><span data-stu-id="85f7a-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
## <a name="deployment-overview"></a><span data-ttu-id="85f7a-107">部署概述</span><span class="sxs-lookup"><span data-stu-id="85f7a-107">Deployment Overview</span></span>

<span data-ttu-id="85f7a-108">呼叫质量仪表板 (CQD) 由三个主要组件组成：</span><span class="sxs-lookup"><span data-stu-id="85f7a-108">Call Quality Dashboard (CQD) consists of three major components:</span></span>
  
- <span data-ttu-id="85f7a-109">**存档数据库**，其中将复制 (QoE) 用户体验质量。</span><span class="sxs-lookup"><span data-stu-id="85f7a-109">**Archive Database**, where the Quality of Experience (QoE) data is replicated and stored.</span></span>
    
- <span data-ttu-id="85f7a-110">**多维数据集**，其中聚合 QoE 存档数据库中的数据，以优化快速访问。</span><span class="sxs-lookup"><span data-stu-id="85f7a-110">**Cube**, where data from QoE Archive database is aggregated for optimized and fast access.</span></span>
    
- <span data-ttu-id="85f7a-111">**门户**，用户可在门户中轻松查询和可视化 QoE 数据。</span><span class="sxs-lookup"><span data-stu-id="85f7a-111">**Portal**, where users can easily query and visualize QoE data.</span></span>
    
![CQD 组件](../../media/ef3359b1-c98b-4cc5-a549-c84c6e03c011.png)
  
<span data-ttu-id="85f7a-113">QoE 存档的安装过程涉及创建 QoE 存档数据库、部署将数据从源 QoE 指标数据库移动到 QoE 存档数据库的 SQL Server 存储过程，以及设置 SQL Server 代理作业以定期执行存储过程。</span><span class="sxs-lookup"><span data-stu-id="85f7a-113">The setup process for QoE Archive involves creating the QoE Archive database, deploying a SQL Server stored procedure that will move the data from the source QoE Metrics database into QoE Archive database, and setting up the SQL Server Agent job to execute the stored procedure at a regular interval.</span></span> 
  
<span data-ttu-id="85f7a-114">多维数据集部署从 QoE 存档所在的用户处获取信息，部署多维数据集，并设置定期刷新多维数据集的常规 SQL Server 代理作业。</span><span class="sxs-lookup"><span data-stu-id="85f7a-114">Cube deployment gets information from the user on where the QoE Archive is located, deploys the cube, and sets up a regular SQL Server agent job that will refresh the cube at a regular interval.</span></span>
  
<span data-ttu-id="85f7a-115">门户安装会创建一个存储库数据库，用于存储 CQD 用户到每个用户的报告/查询的映射。</span><span class="sxs-lookup"><span data-stu-id="85f7a-115">Portal install creates a Repository database that stores the mapping of CQD users to each user's reports/queries.</span></span> <span data-ttu-id="85f7a-116">然后，它设置一个 IIS Web 应用程序，这是一个仪表板，用户可以在仪表板中查看一组预定义的报告，并自定义和创建自己的查询以可视化多维数据集数据。</span><span class="sxs-lookup"><span data-stu-id="85f7a-116">It then sets up an IIS web application which is the dashboard where users can see a pre-defined set of reports as well as customize and create their own queries to visualize data from the cube.</span></span> <span data-ttu-id="85f7a-117">门户安装会创建另外两个 Web 应用程序，这些应用程序公开 API，以便用户以编程方式访问存储库和多维数据集。</span><span class="sxs-lookup"><span data-stu-id="85f7a-117">The portal install creates two additional web applications that exposes APIs for users to programmatically access the repository and the cube.</span></span> <span data-ttu-id="85f7a-118"> (仪表板内部也使用这些 API。) </span><span class="sxs-lookup"><span data-stu-id="85f7a-118">(These APIs are used internally by the dashboard as well.)</span></span>
  

|<span data-ttu-id="85f7a-119">**阶段**</span><span class="sxs-lookup"><span data-stu-id="85f7a-119">**Phase**</span></span>|<span data-ttu-id="85f7a-120">**步骤**</span><span class="sxs-lookup"><span data-stu-id="85f7a-120">**Steps**</span></span>|<span data-ttu-id="85f7a-121">**角色和组成员身份**</span><span class="sxs-lookup"><span data-stu-id="85f7a-121">**Roles and group membership**</span></span>|<span data-ttu-id="85f7a-122">**文档**</span><span class="sxs-lookup"><span data-stu-id="85f7a-122">**Documentation**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="85f7a-123">安装必备硬件和软件。</span><span class="sxs-lookup"><span data-stu-id="85f7a-123">Install prerequisite hardware and software.</span></span>  <br/> |<span data-ttu-id="85f7a-124">决定 CQD 配置，然后选择SQL Server安装选项。</span><span class="sxs-lookup"><span data-stu-id="85f7a-124">Decide on the CQD configuration, and choose a SQL Server from which to perform the install.</span></span>  <br/> |<span data-ttu-id="85f7a-125">属于本地 Administrators 组成员的域用户。</span><span class="sxs-lookup"><span data-stu-id="85f7a-125">Domain user who is a member of the local administrators group.</span></span>  <br/> |<span data-ttu-id="85f7a-126">部署文档中的"预安装要求"部分。</span><span class="sxs-lookup"><span data-stu-id="85f7a-126">"Pre-install Requirements" section in the deployment documentation.</span></span>  <br/> |
|<span data-ttu-id="85f7a-127">安装 CQD。</span><span class="sxs-lookup"><span data-stu-id="85f7a-127">Install CQD.</span></span>  <br/> |<span data-ttu-id="85f7a-128">在部署文档后运行 MSI。</span><span class="sxs-lookup"><span data-stu-id="85f7a-128">Run the MSI following the deployment document.</span></span>  <br/> |<span data-ttu-id="85f7a-129">若要执行设置，安装帐户必须是域用户，即本地 Administrators 组的成员，并且对监控服务器上 QoE 指标数据库具有读取访问权限。</span><span class="sxs-lookup"><span data-stu-id="85f7a-129">To perform the setup, the installing account must be a domain user who is a member of the local administrators group and have read access to QoE Metrics database on the Monitoring Server.</span></span>  <br/> |<span data-ttu-id="85f7a-130">部署文档中的"帐户和部署步骤"部分。</span><span class="sxs-lookup"><span data-stu-id="85f7a-130">"Accounts and Deployment Steps" sections in the deployment documentation.</span></span>  <br/> |
|<span data-ttu-id="85f7a-131">授予用户访问权限。</span><span class="sxs-lookup"><span data-stu-id="85f7a-131">Grant user access.</span></span>  <br/> |<span data-ttu-id="85f7a-132">若要管理对门户的用户授权，我们建议使用 IIS 7.0 中引入的 URL 授权。</span><span class="sxs-lookup"><span data-stu-id="85f7a-132">For managing user authorization to the Portal, we recommend using URL Authorization, which was introduced in IIS 7.0.</span></span> <span data-ttu-id="85f7a-133">有关详细信息，请参阅了解 [IIS 7.0 URL 授权](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization)。</span><span class="sxs-lookup"><span data-stu-id="85f7a-133">For more information, see [Understanding IIS 7.0 URL Authorization](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).</span></span>  <br/> |<span data-ttu-id="85f7a-134">属于本地 Administrators 组成员的域用户。</span><span class="sxs-lookup"><span data-stu-id="85f7a-134">Domain user who is a member of the local administrators group.</span></span>  <br/> |<span data-ttu-id="85f7a-135">部署文档中的"管理门户的用户访问"部分。</span><span class="sxs-lookup"><span data-stu-id="85f7a-135">Managing User Access for the Portal section in the deployment documentation.</span></span>  <br/> |
|<span data-ttu-id="85f7a-136">可选：提供子网映射信息。</span><span class="sxs-lookup"><span data-stu-id="85f7a-136">Optional: Provide subnet mapping information.</span></span>  <br/> |<span data-ttu-id="85f7a-137">填充 QoE 存档数据库中的网络和构建映射表。</span><span class="sxs-lookup"><span data-stu-id="85f7a-137">Populate network and building mapping tables in QoE Archive database.</span></span>  <br/> |<span data-ttu-id="85f7a-138">对 QoE 存档数据库具有写访问权限的帐户。</span><span class="sxs-lookup"><span data-stu-id="85f7a-138">An account with write access to the QoE Archive database.</span></span>  <br/> |<span data-ttu-id="85f7a-139">用户文档中的"提供子网信息"部分。</span><span class="sxs-lookup"><span data-stu-id="85f7a-139">"Supplying Subnet Information" section in the user documentation.</span></span>  <br/> |
   


<span data-ttu-id="85f7a-140">呼叫质量仪表板的部署涉及设置基础结构和安装软件。</span><span class="sxs-lookup"><span data-stu-id="85f7a-140">Deployment of Call Quality Dashboard involves setting up the infrastructure and installing the software.</span></span> <span data-ttu-id="85f7a-141">以下过程概述了该过程。</span><span class="sxs-lookup"><span data-stu-id="85f7a-141">The following procedure outlines the process.</span></span>
  
## <a name="deployment-steps"></a><span data-ttu-id="85f7a-142">部署步骤</span><span class="sxs-lookup"><span data-stu-id="85f7a-142">Deployment Steps</span></span>

1. <span data-ttu-id="85f7a-143">将CallQualityDashboard.msi复制到要安装 CQD 存档数据库组件的计算机 (这是已安装SQL Server的计算机) 。</span><span class="sxs-lookup"><span data-stu-id="85f7a-143">Copy the CallQualityDashboard.msi to the machine where the archive database component of CQD is to be installed (this is the machine that has SQL Server installed).</span></span> 
    
2. <span data-ttu-id="85f7a-144">执行 MSI (Windows 将提示使用管理员权限运行，) 。</span><span class="sxs-lookup"><span data-stu-id="85f7a-144">Execute the MSI (Windows will prompt to run with administrator privilege, do so).</span></span> 
    
3. <span data-ttu-id="85f7a-145">接受 EULA。</span><span class="sxs-lookup"><span data-stu-id="85f7a-145">Accept the EULA.</span></span>
    
4. <span data-ttu-id="85f7a-146">选择与呼叫质量仪表板组件相关的文件将位于的目标文件夹或接受默认位置。</span><span class="sxs-lookup"><span data-stu-id="85f7a-146">Select the destination folder where files related to Call Quality Dashboard components will be located or accept the default location.</span></span>
    
5. <span data-ttu-id="85f7a-147">选择所有功能。</span><span class="sxs-lookup"><span data-stu-id="85f7a-147">Select all features.</span></span>
    
6. <span data-ttu-id="85f7a-148">在"QoE 存档配置"页上，提供以下信息：</span><span class="sxs-lookup"><span data-stu-id="85f7a-148">At the QoE Archive Configuration page, provide the following information:</span></span>
    
   - <span data-ttu-id="85f7a-149">**QoE 指标SQL Server：** SQL Server QoE 指标 DB 所在的实例 (将成为数据源) 。</span><span class="sxs-lookup"><span data-stu-id="85f7a-149">**QoE Metrics SQL Server:** SQL Server instance name for where the QoE Metrics DB is located (this will be the data source).</span></span>
    
   - <span data-ttu-id="85f7a-150">**QoE 存档SQL Server名称：** 这是只读字段，并修复为本地计算机完全限定的域名。</span><span class="sxs-lookup"><span data-stu-id="85f7a-150">**QoE Archive SQL Server Name:** This is read-only field and fixed to the fully qualified domain name of the local machine.</span></span> <span data-ttu-id="85f7a-151">存档 DB 只能安装在本地计算机上。</span><span class="sxs-lookup"><span data-stu-id="85f7a-151">Archive DB can be installed only on the local machine.</span></span>
    
   - <span data-ttu-id="85f7a-152">**QoE 存档SQL Server实例：** 要SQL Server存档数据库的本地数据库实例名称。</span><span class="sxs-lookup"><span data-stu-id="85f7a-152">**QoE Archive SQL Server Instance:** A local SQL Server instance name for where the Archive DB is to be created.</span></span> <span data-ttu-id="85f7a-153">若要使用默认实例SQL Server，请保留此字段为空。</span><span class="sxs-lookup"><span data-stu-id="85f7a-153">To use a default SQL Server instance, leave this field blank.</span></span> <span data-ttu-id="85f7a-154">若要使用命名SQL Server实例，请指定实例 (，例如"名称"之后 \") 。</span><span class="sxs-lookup"><span data-stu-id="85f7a-154">To use a named SQL Server instance, specify the instance name (e.g. the name after the "\").</span></span>
    
   - <span data-ttu-id="85f7a-155">**QoE 存档数据库：** 默认情况下，此选项设置为"新建数据库"。</span><span class="sxs-lookup"><span data-stu-id="85f7a-155">**QoE Archive Database:** By default, this option is set to "Create new database".</span></span> <span data-ttu-id="85f7a-156">由于不支持存档数据库升级，因此可以使用"使用现有数据库"选项的唯一情形是，现有存档数据库与要安装内部版本具有相同的架构。</span><span class="sxs-lookup"><span data-stu-id="85f7a-156">Since Archive DB upgrade is not supported, the only circumstance under which the "Use existing database" option can be used is if the existing Archive database has the same schema as the build to be installed.</span></span>
    
   - <span data-ttu-id="85f7a-157">**数据库文件目录：** 存档数据库的数据库文件 (.mdf 和 .ldf) 的位置的路径。</span><span class="sxs-lookup"><span data-stu-id="85f7a-157">**Database File Directory:** Path to where the database files (.mdf and .ldf) for the Archive DB should be placed.</span></span> <span data-ttu-id="85f7a-158">这应该位于推荐的硬件配置 (HDD2 的驱动器) 操作系统。</span><span class="sxs-lookup"><span data-stu-id="85f7a-158">This should be on a drive (HDD2 in the recommended hardware configuration) separate from the OS.</span></span> <span data-ttu-id="85f7a-159">请注意，由于文件名在安装中是固定的，为了避免任何潜在的冲突，建议使用没有文件的空白目录。</span><span class="sxs-lookup"><span data-stu-id="85f7a-159">Note that since the file names are fixed in the install, to avoid any potential conflict, it is recommended that a blank directory with no files be used.</span></span>
    
   - <span data-ttu-id="85f7a-160">**使用多个分区：** 默认设置为"多个分区"，这需要商业智能版本或企业版SQL Server。</span><span class="sxs-lookup"><span data-stu-id="85f7a-160">**Use Multiple Partitions:** The default is set to "Multiple partition", which requires Business Intelligence edition or Enterprise edition of SQL Server.</span></span> <span data-ttu-id="85f7a-161">对于 Standard Edition，选择"单分区"选项。</span><span class="sxs-lookup"><span data-stu-id="85f7a-161">For Standard edition, select "Single Partition" option.</span></span> <span data-ttu-id="85f7a-162">请注意，如果使用单个分区，则多维数据集处理性能可能会受到影响。</span><span class="sxs-lookup"><span data-stu-id="85f7a-162">Note that cube processing performance may be impacted if Single Partition is used.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="85f7a-163">安装程序完成后，无法更改"使用多个分区"选项的选择。</span><span class="sxs-lookup"><span data-stu-id="85f7a-163">The selection for Use Multiple Partitions option cannot be changed once Setup completes.</span></span> <span data-ttu-id="85f7a-164">若要更改它，需要首先卸载多维数据集功能，然后使用控制面板中的"更改"选项重新安装。</span><span class="sxs-lookup"><span data-stu-id="85f7a-164">In order to change it, the Cube feature needs to be first uninstalled and then reinstalled using "Change" option in Control Panel.</span></span> 
  
   - <span data-ttu-id="85f7a-165">**分区文件目录：** QoE 存档数据库的分区应放置的位置的路径。</span><span class="sxs-lookup"><span data-stu-id="85f7a-165">**Partition File Directory:** Path to where the partitions for the QoE Archive database should be placed.</span></span> <span data-ttu-id="85f7a-166">这应该位于推荐硬件配置 (HDD3 的驱动器上) 操作系统驱动器和SQL日志文件驱动器。</span><span class="sxs-lookup"><span data-stu-id="85f7a-166">This should be on a drive (HDD3 in the recommended hardware configuration) separate from the OS drive and SQL database log files drive.</span></span> <span data-ttu-id="85f7a-167">请注意，由于文件名在安装中是固定的，为了避免任何潜在的冲突，建议使用没有文件的空白目录。</span><span class="sxs-lookup"><span data-stu-id="85f7a-167">Note that since the file names are fixed in the install, to avoid any potential conflict, it is recommended that a blank directory with no files be used.</span></span>
    
   - <span data-ttu-id="85f7a-168">**SQL代理作业用户 - 用户名 &amp;** 密码：域服务帐户名和密码 (已屏蔽) 将用于运行 SQL Server 代理作业 (该作业将运行存储过程以将数据从 QoE 指标数据库提取到存档 DB 的"QoE 存档数据"步骤，因此此帐户必须具有对 QoE 指标 DB 的读取访问权限，如"帐户"部分所述。</span><span class="sxs-lookup"><span data-stu-id="85f7a-168">**SQL Agent Job User - User Name &amp; Password:** Domain service account name and password (masked) that will be used to run the "QoE Archive Data" step of the SQL Server Agent job (which will run the stored procedure to fetch data from QoE Metrics DB into Archive DB, so this account must have read access to QoE Metrics DB, as indicated under Accounts section.</span></span> <span data-ttu-id="85f7a-169">此帐户还需要在 QoE 存档实例SQL Server登录) 。</span><span class="sxs-lookup"><span data-stu-id="85f7a-169">This account also needs to have a login in the QoE Archive SQL Server Instance).</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="85f7a-170">运行实例SQL Server的帐户（如 NT SERVICE\MSSQLSERVER）必须具有对上述给定目录的访问/权限，安装才能成功。</span><span class="sxs-lookup"><span data-stu-id="85f7a-170">The account that the SQL Server instance is running under, such as NT SERVICE\MSSQLSERVER, must have access/permission to the directories given above for the installation to succeed.</span></span> <span data-ttu-id="85f7a-171">有关详细信息，请参阅 [为数据库引擎访问配置文件系统权限](/previous-versions/sql/sql-server-2012/jj219062(v=sql.110))</span><span class="sxs-lookup"><span data-stu-id="85f7a-171">For details, see [Configure File System Permissions for Database Engine Access](/previous-versions/sql/sql-server-2012/jj219062(v=sql.110))</span></span>
  
7. <span data-ttu-id="85f7a-172">单击下一步后，安装程序将执行先决条件检查并报告是否遇到任何问题。</span><span class="sxs-lookup"><span data-stu-id="85f7a-172">Upon clicking next, the installer will perform pre-requisite checks and report if any issues are encountered.</span></span> <span data-ttu-id="85f7a-173">当所有先决条件检查通过时，安装程序将转到"多维数据集配置"页。</span><span class="sxs-lookup"><span data-stu-id="85f7a-173">When all pre-requisite checks pass, the installer will go to the Cube Configuration page.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="85f7a-174">如果安装程序显示一条警告消息，指出 QoE 存档 SQL Server 实例的 SQL Server 代理服务当前未运行，则安装可以继续，但安装后请确保 SQL 代理服务正在运行，并且将启动类型设置为"自动"，以便计划的作业运行。</span><span class="sxs-lookup"><span data-stu-id="85f7a-174">If the installer shows a warning message that the SQL Server Agent service for the QoE Archive SQL Server instance is currently not running, installation can proceed, but post installation please make sure that SQL Agent service is running and set the Startup type to Automatic so that the scheduled Job runs.</span></span> 
  
8. <span data-ttu-id="85f7a-175">在"多维数据集配置"页上，提供以下信息：</span><span class="sxs-lookup"><span data-stu-id="85f7a-175">At Cube Configuration page, provide the following information:</span></span>
    
   - <span data-ttu-id="85f7a-176">**QoE 存档SQL Server名称：** 这是只读字段，并修复为本地计算机完全限定的域名。</span><span class="sxs-lookup"><span data-stu-id="85f7a-176">**QoE Archive SQL Server Name:** This is read-only field and fixed to the fully qualified domain name of the local machine.</span></span> <span data-ttu-id="85f7a-177">只能从具有 QoE 存档数据库的计算机安装多维数据集 (注意。</span><span class="sxs-lookup"><span data-stu-id="85f7a-177">Cube can be installed only from the machine that has QoE Archive database (Note.</span></span> <span data-ttu-id="85f7a-178">多维数据集本身可以安装在远程计算机上。</span><span class="sxs-lookup"><span data-stu-id="85f7a-178">Cube itself may be installed on a remote machine.</span></span> <span data-ttu-id="85f7a-179">请参阅下面的) </span><span class="sxs-lookup"><span data-stu-id="85f7a-179">See below)</span></span>
    
   - <span data-ttu-id="85f7a-180">**QoE 存档SQL Server实例：** SQL Server QoE 存档 DB 所在的实例名称。</span><span class="sxs-lookup"><span data-stu-id="85f7a-180">**QoE Archive SQL Server Instance:** SQL Server instance name for where the QoE Archive DB is located.</span></span> <span data-ttu-id="85f7a-181">若要指定默认实例SQL Server，请保留此字段为空。</span><span class="sxs-lookup"><span data-stu-id="85f7a-181">To specify a default SQL Server instance, leave this field blank.</span></span> <span data-ttu-id="85f7a-182">若要指定SQL Server实例，请输入实例名称 (例如"名称"之后 \") 。</span><span class="sxs-lookup"><span data-stu-id="85f7a-182">To specify a named SQL Server instance, enter the instance name (e.g. the name after the "\").</span></span> <span data-ttu-id="85f7a-183">如果选择了 QoE 存档组件进行安装，则此字段将预填充"QoE 存档配置"页上提供的值。</span><span class="sxs-lookup"><span data-stu-id="85f7a-183">If QoE Archive component was selected for the install, this field will be pre-populated with the value provided on the QoE Archive Configuration page.</span></span>
    
   - <span data-ttu-id="85f7a-184">**多维数据集分析服务器：** SQL Server创建多维数据集的 Analysis Service 实例名称。</span><span class="sxs-lookup"><span data-stu-id="85f7a-184">**Cube Analysis Server:** SQL Server Analysis Service instance name for where the cube is to be created.</span></span> <span data-ttu-id="85f7a-185">这可以是其他计算机，但安装用户必须是 Analysis Service 实例的目标服务器SQL Server的成员。</span><span class="sxs-lookup"><span data-stu-id="85f7a-185">This can be a different machine but the installing user has to be a member of Server administrators of the target SQL Server Analysis Service instance.</span></span>
    
     > [!NOTE]
     >  <span data-ttu-id="85f7a-186">有关配置服务器管理员Analysis Services，请参阅授予 [服务器管理员权限 (Analysis Services) ](/analysis-services/instances/grant-server-admin-rights-to-an-analysis-services-instance?viewFallbackFrom=sql-server-ver15)</span><span class="sxs-lookup"><span data-stu-id="85f7a-186">For more information about configuring Analysis Services Server Administrator Permissions, see [Grant Server Administrator Permissions (Analysis Services)](/analysis-services/instances/grant-server-admin-rights-to-an-analysis-services-instance?viewFallbackFrom=sql-server-ver15)</span></span>
  
   - <span data-ttu-id="85f7a-187">**使用多个分区：** 默认设置为"多个分区"，这需要商业智能版本或企业版SQL Server。</span><span class="sxs-lookup"><span data-stu-id="85f7a-187">**Use Multiple Partitions:** The default is set to "Multiple partition", which requires Business Intelligence edition or Enterprise edition of SQL Server.</span></span> <span data-ttu-id="85f7a-188">对于 Standard Edition，选择"单分区"选项。</span><span class="sxs-lookup"><span data-stu-id="85f7a-188">For Standard edition, select "Single Partition" option.</span></span> <span data-ttu-id="85f7a-189">请注意，如果使用"单个分区"，则多维数据集处理性能可能会受到影响。</span><span class="sxs-lookup"><span data-stu-id="85f7a-189">Note that cube processing performance may be impacted if Single Partition is used .</span></span>
    
     > [!NOTE]
     >  <span data-ttu-id="85f7a-190">安装程序完成后，无法更改"使用多个分区"选项的选择。</span><span class="sxs-lookup"><span data-stu-id="85f7a-190">The selection for Use Multiple Partitions option cannot be changed once Setup completes.</span></span> <span data-ttu-id="85f7a-191">若要更改它，需要首先卸载多维数据集功能，然后使用控制面板中的"更改"选项重新安装。</span><span class="sxs-lookup"><span data-stu-id="85f7a-191">In order to change it, the Cube feature needs to be first uninstalled and then reinstalled using "Change" option in Control Panel.</span></span>
  
   - <span data-ttu-id="85f7a-192">**多维数据集用户 - &amp; 用户名密码：** 域服务帐户名和密码 (将) 多维数据集处理的掩码。</span><span class="sxs-lookup"><span data-stu-id="85f7a-192">**Cube User - User Name &amp; Password:** Domain service account name and password (masked) that will trigger the cube processing.</span></span> <span data-ttu-id="85f7a-193">如果选择了 QoE 存档组件进行安装，则此字段将预填充"SQL 代理作业用户"的"存档配置"页上提供的值，但我们建议指定其他域服务帐户，以便安装程序可以授予最低要求的特权。</span><span class="sxs-lookup"><span data-stu-id="85f7a-193">If QoE Archive component was selected for the install, this field will be pre-populated with the value provided on the Archive Configuration page for the SQL Agent Job User, but we recommend specifying a different domain service account so that Setup can grant the least required privilege to it.</span></span>
    
9. <span data-ttu-id="85f7a-194">单击下一步时，将执行另一轮验证，并报告任何问题。</span><span class="sxs-lookup"><span data-stu-id="85f7a-194">When clicking next, another round of validation will be performed and any issue will be reported.</span></span> <span data-ttu-id="85f7a-195">成功完成验证后，安装程序将转到"门户配置"页。</span><span class="sxs-lookup"><span data-stu-id="85f7a-195">Upon successful completion of the validation, the installer will go to the Portal Configuration page.</span></span> 
    
10. <span data-ttu-id="85f7a-196">在"门户配置"页上，提供以下信息：</span><span class="sxs-lookup"><span data-stu-id="85f7a-196">At Portal Configuration page, provide the following information:</span></span>
    
    - <span data-ttu-id="85f7a-197">**QoE 存档SQL Server：** SQL Server QoE 存档数据库所在的实例名称。</span><span class="sxs-lookup"><span data-stu-id="85f7a-197">**QoE Archive SQL Server:** SQL Server instance name for where the QoE Archive database is located.</span></span> <span data-ttu-id="85f7a-198">请注意，与"QoE 存档配置"页和"多维数据集配置"页不同，计算机名称不是固定的，必须提供。</span><span class="sxs-lookup"><span data-stu-id="85f7a-198">Note that unlike the QoE Archive Configuration page and the Cube Configuration page, the machine name is not fixed and must be provided.</span></span> <span data-ttu-id="85f7a-199">如果选择了 QoE 存档组件进行安装，则此字段将预填充"QoE 存档配置"页上提供的值。</span><span class="sxs-lookup"><span data-stu-id="85f7a-199">If QoE Archive component was selected for the install, this field will be pre-populated with the value provided on the QoE Archive Configuration page.</span></span>
    
    - <span data-ttu-id="85f7a-200">**多维数据集分析服务器：** SQL Server多维数据集所在的 Analysis Service 实例名称。</span><span class="sxs-lookup"><span data-stu-id="85f7a-200">**Cube Analysis Server:** SQL Server Analysis Service instance name for where the cube is located.</span></span> <span data-ttu-id="85f7a-201">如果选择了多维数据集组件进行安装，则此字段将预填充"多维数据集配置"页上提供的值。</span><span class="sxs-lookup"><span data-stu-id="85f7a-201">If Cube component was selected for the install, this field will be pre-populated with the value provided on the Cube Configuration page.</span></span>
    
    - <span data-ttu-id="85f7a-202">**存储库SQL Server：** SQL Server存储库数据库的位置的实例名称。</span><span class="sxs-lookup"><span data-stu-id="85f7a-202">**Repository SQL Server:** SQL Server instance name where the Repository database is to be created.</span></span> <span data-ttu-id="85f7a-203">如果 QoE 存档数据库所在的 SQL Server 实例名称已在其他组件) 的安装 (中先前提供，则此字段将预先填充 QoE 存档数据库 SQL Server 实例名称。</span><span class="sxs-lookup"><span data-stu-id="85f7a-203">If the SQL Server instance name for where the QoE Archive database is located has been provided earlier in the setup (in other components), this field will be pre-populated with the QoE Archive DB SQL Server instance name.</span></span> <span data-ttu-id="85f7a-204">这可以是任何SQL Server实例。</span><span class="sxs-lookup"><span data-stu-id="85f7a-204">This can be any SQL Server instance.</span></span>
    
    - <span data-ttu-id="85f7a-205">**存储库数据库：** 默认情况下，该选项设置为"新建数据库"。</span><span class="sxs-lookup"><span data-stu-id="85f7a-205">**Repository Database:** By default the option is set to "Create new database".</span></span> <span data-ttu-id="85f7a-206">由于不支持 Repository DB 升级，因此可以使用"使用现有数据库"选项的唯一情形是，现有 Repository DB 与要安装内部版本具有相同的架构。</span><span class="sxs-lookup"><span data-stu-id="85f7a-206">Since Repository DB upgrade is not supported, the only circumstance under which the "Use existing database" option can be used is if the existing Repository DB has the same schema as the build to be installed.</span></span>
    
    - <span data-ttu-id="85f7a-207">**IIS 应用程序池用户 - 用户名 &amp; 密码** ：IIS 应用程序池应执行的帐户。</span><span class="sxs-lookup"><span data-stu-id="85f7a-207">**IIS App Pool User - User Name &amp; Password:** The account that the IIS application pool should execute under.</span></span> <span data-ttu-id="85f7a-208">如果选择内置系统帐户，则"用户名"和"密码"字段将灰显。</span><span class="sxs-lookup"><span data-stu-id="85f7a-208">The User Name and Password fields will be grayed out if built-in system accounts are selected.</span></span> <span data-ttu-id="85f7a-209">只有在从下拉框中选择"其他"时，才能启用这些字段，以便用户可以输入域服务帐户信息。</span><span class="sxs-lookup"><span data-stu-id="85f7a-209">These fields will only be enabled if "Other" is selected from the drop down box so the user can enter the domain service account information.</span></span>
    
11. <span data-ttu-id="85f7a-210">单击下一步时，将完成最后一轮验证，以确保可以使用提供的凭据访问 SQL Server 实例，并确保 IIS 在计算机中可用。</span><span class="sxs-lookup"><span data-stu-id="85f7a-210">When clicking next, the final round of validation will be done to ensure that the SQL Server instances are accessible using the credentials provided and that IIS is available on the machine.</span></span> <span data-ttu-id="85f7a-211">成功完成验证后，安装程序将继续安装。</span><span class="sxs-lookup"><span data-stu-id="85f7a-211">Upon successful completion of the validation, the installer will proceed with the setup.</span></span> 
    
<span data-ttu-id="85f7a-212">安装程序完成后，很可能SQL Server代理作业正在进行中，同时执行 QoE 数据的初始负载和多维数据集处理。</span><span class="sxs-lookup"><span data-stu-id="85f7a-212">When the installer is done, most likely the SQL Server Agent job will be in progress, doing the initial load of the QoE data and the cube processing.</span></span> <span data-ttu-id="85f7a-213">根据 QoE 中数据的数量，门户尚没有可供查看的数据。</span><span class="sxs-lookup"><span data-stu-id="85f7a-213">Depending on the amount of data in QoE, the portal will not have data available for viewing yet.</span></span> <span data-ttu-id="85f7a-214">若要检查数据加载和多维数据集处理的状态，请转到  `http://<machinename>/CQD/#/Health` 。</span><span class="sxs-lookup"><span data-stu-id="85f7a-214">To check on the status of the data load and cube processing, go to  `http://<machinename>/CQD/#/Health`.</span></span> 
> [!NOTE]
> <span data-ttu-id="85f7a-215">请注意，用于检查下载多维数据集处理状态的 URL 区分大小写。</span><span class="sxs-lookup"><span data-stu-id="85f7a-215">Note that the URL for checking the status of the download cube processing is case sensitive.</span></span> <span data-ttu-id="85f7a-216">如果输入"运行状况"，URL 将不起作用。</span><span class="sxs-lookup"><span data-stu-id="85f7a-216">If you enter 'health' the URL will not work.</span></span> <span data-ttu-id="85f7a-217">必须在 URL 末尾输入大写 H 的"Health"。</span><span class="sxs-lookup"><span data-stu-id="85f7a-217">You must enter 'Health' at the end of the URL with a capital H.</span></span> 
  
<span data-ttu-id="85f7a-218">如果启用调试模式，将显示详细的日志消息。</span><span class="sxs-lookup"><span data-stu-id="85f7a-218">Detailed log messages will be shown if debug mode is enabled.</span></span> <span data-ttu-id="85f7a-219">若要启用调试模式，请转到 **%SYSTEMDRIVE%\Program Files\Skype For Business 2015 CQD\QoEDataService\web.config，** 并更新以下行，以便值设置为 **True**：</span><span class="sxs-lookup"><span data-stu-id="85f7a-219">To enable debug mode, go to **%SYSTEMDRIVE%\Program Files\Skype For Business 2015 CQD\QoEDataService\web.config**, and update the following line so the value is set to **True**:</span></span>

```xml
<add key="QoEDataLib.DebugMode" value="True" /> 
```

<span data-ttu-id="85f7a-220">主门户页面可通过 访问  `http://<machinename>/CQD` 。</span><span class="sxs-lookup"><span data-stu-id="85f7a-220">The main portal page is accessible via  `http://<machinename>/CQD`.</span></span> 
## <a name="managing-user-access-for-the-portal"></a><span data-ttu-id="85f7a-221">管理门户的用户访问</span><span class="sxs-lookup"><span data-stu-id="85f7a-221">Managing User Access for the Portal</span></span>

<span data-ttu-id="85f7a-222">若要管理对门户的用户授权，我们建议使用 IIS 7.0 中引入的 URL 授权。</span><span class="sxs-lookup"><span data-stu-id="85f7a-222">For managing user authorization to the Portal, we recommend using URL Authorization, which was introduced in IIS 7.0.</span></span> <span data-ttu-id="85f7a-223">有关 IIS 安全性详细信息，请参阅 [了解 IIS 7.0 URL 授权](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization)。</span><span class="sxs-lookup"><span data-stu-id="85f7a-223">For more information on IIS security, see [Understanding IIS 7.0 URL Authorization](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).</span></span>
  
<span data-ttu-id="85f7a-224">任何网站或 Web 应用程序都继承为整个 IIS 配置的默认 URL 授权，通常为"允许所有用户"。</span><span class="sxs-lookup"><span data-stu-id="85f7a-224">Any web site or web application inherit the default URL Authorization configured for the entire IIS, which is typically "Allow All Users".</span></span> <span data-ttu-id="85f7a-225">如果对门户的访问需要更加严格，则管理员可通过编辑"授权规则"仅向特定组用户授予访问权限。</span><span class="sxs-lookup"><span data-stu-id="85f7a-225">If access to the Portal needs to be more restrictive, then administrators can grant access to only the specific group of users by editing the "Authorization Rules".</span></span>
  
![部署呼叫质量 - IIS 中的授权规则](../../media/0da80c28-58fe-4aca-94b4-db684389468c.png)
  
> [!NOTE]
> <span data-ttu-id="85f7a-227">"授权规则"图标不要与"授权规则"部分下的".NET 授权 ASP.NET 混淆，这是一种不同的授权机制。</span><span class="sxs-lookup"><span data-stu-id="85f7a-227">The Authorization Rules icon is not to be confused with the ".NET Authorization" under the ASP.NET section, which is a different authorization mechanism.</span></span> 
  
<span data-ttu-id="85f7a-228">管理员应首先删除继承的"允许所有用户"规则。</span><span class="sxs-lookup"><span data-stu-id="85f7a-228">Administrators should first remove the inherited "Allow All Users" rule.</span></span> <span data-ttu-id="85f7a-229">这将阻止任何未经授权的用户访问门户。</span><span class="sxs-lookup"><span data-stu-id="85f7a-229">This prevents any non-authorized users from accessing the Portal.</span></span>
  
![部署 CQD](../../media/fa17ad19-d303-40f8-8324-d13fd67936ab.png)
  
<span data-ttu-id="85f7a-231">接下来，管理员应添加新的允许规则，并授予特定用户访问门户的权限。</span><span class="sxs-lookup"><span data-stu-id="85f7a-231">Next, administrators should add new Allow Rules and give specific users the permission to access the Portal.</span></span> <span data-ttu-id="85f7a-232">建议创建名为"CQDPortalUsers"的本地组来管理用户。</span><span class="sxs-lookup"><span data-stu-id="85f7a-232">It is recommended that a local Group called "CQDPortalUsers" be created to manage the users.</span></span>
  
![部署通话质量仪表板](../../media/8cfdc141-ec89-4552-921b-53196f497cbf.png)
  
<span data-ttu-id="85f7a-234">配置详细信息存储在门户web.config中的位置。</span><span class="sxs-lookup"><span data-stu-id="85f7a-234">The configuration details are stored in the web.config located at the Portal's physical directory.</span></span>
  
```xml
<?xml version="1.0" encoding="UTF-8"?> <configuration> <system.webServer> <security> <authorization> <remove users="*" roles="" verbs="" /> <add accessType="Allow" roles="CQDPortalUsers" /> </authorization> </security> </system.webServer> </configuration> 
```

<span data-ttu-id="85f7a-235">下一步是配置 CQD 的仪表板。</span><span class="sxs-lookup"><span data-stu-id="85f7a-235">The next step is to configure the dashboard of the CQD.</span></span> <span data-ttu-id="85f7a-236">在 IIS 对用户进行身份验证后，他们必须拥有对 CQD 目录的文件权限才能访问 Web 门户内容。</span><span class="sxs-lookup"><span data-stu-id="85f7a-236">After users are authenticated by IIS, they will have to have file permissions on the CQD directory in order to access the web portal content.</span></span> <span data-ttu-id="85f7a-237">可以通过 CQD 目录属性的安全选项卡更改 ACL，以添加单个用户或组;但是，建议的方法是保持文件权限不变。</span><span class="sxs-lookup"><span data-stu-id="85f7a-237">It is possible to change the ACLs through the security tab of the CQD directory properties to add individual users or groups; however the recommended approach is to leave the file permissions untouched.</span></span> <span data-ttu-id="85f7a-238">相反，将 IIS 设置更改为使用 IIS 工作进程访问 CQD 目录，而不管哪个用户已经过身份验证。</span><span class="sxs-lookup"><span data-stu-id="85f7a-238">Instead, change the IIS setting to use the IIS worker process to access the CQD directory no matter which user is authenticated.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="85f7a-239">必须仅更改 CQD 应用程序的此设置，而不要更改这两个 API 应用程序的此设置：QoEDataService 和 QoERepositoryService。</span><span class="sxs-lookup"><span data-stu-id="85f7a-239">It is important to only change this setting for the CQD application, and not for the two API applications: QoEDataService and QoERepositoryService.</span></span> 
  
## <a name="configuring-file-access-for-the-cqd-dashboard"></a><span data-ttu-id="85f7a-240">Configuring File Access for the CQD (Dashboard) </span><span class="sxs-lookup"><span data-stu-id="85f7a-240">Configuring File Access for the CQD (Dashboard)</span></span>

1. <span data-ttu-id="85f7a-241">打开 CQD 的配置编辑器。</span><span class="sxs-lookup"><span data-stu-id="85f7a-241">Open the Configuration Editor for CQD.</span></span>
    
     ![部署通话质量仪表板](../../media/544056eb-3090-434e-bae6-321c984029fa.png)
  
2. <span data-ttu-id="85f7a-243">在"部分"下，**选择"system.webServer/serverRuntime"。**</span><span class="sxs-lookup"><span data-stu-id="85f7a-243">Under Section, choose **system.webServer/serverRuntime**.</span></span>
    
     ![部署通话质量仪表板](../../media/b0af0e56-21b0-45dd-b610-5381b39319d3.png)
  
3. <span data-ttu-id="85f7a-245">将 authenticatedUserOverride 更改为 **UseWorkerProcessUser**。</span><span class="sxs-lookup"><span data-stu-id="85f7a-245">Change authenticatedUserOverride to **UseWorkerProcessUser**.</span></span>
    
     ![部署呼叫质量仪表板 - 配置编辑器](../../media/a7c127f5-9a90-4710-afba-1d1e588efb37.png)
  
4. <span data-ttu-id="85f7a-247">单击 **页面** 右侧上的"应用"。</span><span class="sxs-lookup"><span data-stu-id="85f7a-247">Click **Apply** on the right-hand side of the page.</span></span>
    
## <a name="known-issues"></a><span data-ttu-id="85f7a-248">已知问题</span><span class="sxs-lookup"><span data-stu-id="85f7a-248">Known Issues</span></span>

### <a name="the-cqd-shows-no-data-after-deployment"></a><span data-ttu-id="85f7a-249">CQD 在部署后未显示任何数据</span><span class="sxs-lookup"><span data-stu-id="85f7a-249">The CQD shows no data after deployment</span></span>

<span data-ttu-id="85f7a-250">您可能会收到以下错误：</span><span class="sxs-lookup"><span data-stu-id="85f7a-250">You may receive the following error:</span></span>

<span data-ttu-id="85f7a-251">*在多维数据集上运行查询时，无法执行查询。使用查询编辑器修改查询并修复任何问题。此外，请确保多维数据集是可访问的。*</span><span class="sxs-lookup"><span data-stu-id="85f7a-251">*We couldn’t perform the query while running it on the Cube. Use the Query Editor to modify the query and fix any issues. Also make sure that the Cube is accessible.*</span></span>

<span data-ttu-id="85f7a-252">这意味着必须先在 CQD 中SQL Server Analysis Services处理多维数据集。</span><span class="sxs-lookup"><span data-stu-id="85f7a-252">This means that the cube must be processed in SQL Server Analysis Services prior to being used in CQD.</span></span> <span data-ttu-id="85f7a-253">可以按照以下步骤解决此问题：</span><span class="sxs-lookup"><span data-stu-id="85f7a-253">You can resolve this by following these steps:</span></span>

1. <span data-ttu-id="85f7a-254">打开 SQL Management Studio 并选择 **"Analysis Services"。**</span><span class="sxs-lookup"><span data-stu-id="85f7a-254">Open SQL Management Studio and select **Analysis Services**.</span></span>

2. <span data-ttu-id="85f7a-255">展开 **QoECube** 对象，选择 **"QoE** 指标"，右键单击，然后选择"浏览 **"。**</span><span class="sxs-lookup"><span data-stu-id="85f7a-255">Expand the **QoECube** object, select **QoE Metric**, right-click, and then choose **Browse**.</span></span> 

    <span data-ttu-id="85f7a-256">如果返回空浏览器，则多维数据集尚未继续。</span><span class="sxs-lookup"><span data-stu-id="85f7a-256">If this returns empty browser, the cube hasn’t been proceed yet.</span></span>

3. <span data-ttu-id="85f7a-257">右键单击 **"QoE 指标**"，然后选择"进程 **"。**</span><span class="sxs-lookup"><span data-stu-id="85f7a-257">Right-click **QoE Metric** angain and choose **Process**.</span></span>

4. <span data-ttu-id="85f7a-258">处理完成后，再次右键单击该对象，然后选择"浏览"以确认浏览器页面现在显示数据。</span><span class="sxs-lookup"><span data-stu-id="85f7a-258">When processing is complete, right-click the object again, and choose **Browse** to confirm that the browser page now shows data.</span></span> 


### <a name="users-have-trouble-logging-in-because-installer-fails-to-create-the-correct-settings-in-iis"></a><span data-ttu-id="85f7a-259">用户登录时遇到问题，因为安装程序在 IIS 中无法创建正确的设置</span><span class="sxs-lookup"><span data-stu-id="85f7a-259">Users have trouble logging in because installer fails to create the correct settings in IIS</span></span>

<span data-ttu-id="85f7a-260">在极少数情况下，安装程序在 IIS 中无法创建正确的设置。</span><span class="sxs-lookup"><span data-stu-id="85f7a-260">In rare cases, the installer fails to create the correct settings in IIS.</span></span> <span data-ttu-id="85f7a-261">需要手动更改才能允许用户登录 CQD。</span><span class="sxs-lookup"><span data-stu-id="85f7a-261">Manual change is required to allow users to log into the CQD.</span></span> <span data-ttu-id="85f7a-262">如果用户登录时遇到问题，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="85f7a-262">If users are having trouble logging in, please follow these steps:</span></span>
  
1. <span data-ttu-id="85f7a-263">打开 IIS 管理器，然后导航到"默认网站"。</span><span class="sxs-lookup"><span data-stu-id="85f7a-263">Open up IIS Manager, and navigate to Default Web Site.</span></span>
    
     ![部署通话质量仪表板](../../media/dc6007aa-870b-4d70-867d-32ffd937063b.png)
  
2. <span data-ttu-id="85f7a-265">单击"身份验证"。</span><span class="sxs-lookup"><span data-stu-id="85f7a-265">Click on "Authentication".</span></span> <span data-ttu-id="85f7a-266">如果"匿名身份验证"、"ASP.NET 模拟"、"表单身份验证"和"Windows 身份验证"与下面显示的设置不匹配，请手动更改它们以匹配以下设置。</span><span class="sxs-lookup"><span data-stu-id="85f7a-266">If the "Anonymous Authentication", "ASP.NET Impersonation", "Form Authentication", and "Windows Authentication" do not match the settings shown below, manually change them to match the settings below.</span></span> <span data-ttu-id="85f7a-267">应禁用所有其他身份验证机制。</span><span class="sxs-lookup"><span data-stu-id="85f7a-267">All other authentication mechanisms should be disabled.</span></span>
    
     ![部署通话质量仪表板](../../media/5d9e38fb-8a50-41a2-a423-3ce983a83d0c.png)
  
3. <span data-ttu-id="85f7a-269">对于"Windows 身份验证"，单击右侧"高级设置"。</span><span class="sxs-lookup"><span data-stu-id="85f7a-269">For "Windows Authentication", click on Advanced Settings on the right-hand side.</span></span>
    
     ![部署通话质量仪表板](../../media/cad29486-df40-4cc9-82f3-bbdaca52d9ca.png)
  
4. <span data-ttu-id="85f7a-271">将"扩展保护"设置为"接受"并选中"启用内核模式身份验证"框。</span><span class="sxs-lookup"><span data-stu-id="85f7a-271">Set "Extended Protection" to Accept and check the "Enable Kernel-mode authentication" box.</span></span>
    
     ![部署通话质量仪表板](../../media/0ab2dda1-0001-4747-8cfc-072e9368b6cb.png)
  
5. <span data-ttu-id="85f7a-273">对"默认网站"下面的每个"CQD"、"QoEDataService"和"QoERepositoryService"条目重复上述步骤。</span><span class="sxs-lookup"><span data-stu-id="85f7a-273">Repeat the above steps for each of the "CQD", "QoEDataService", and "QoERepositoryService" entries below "Default Web Site".</span></span>
    
<span data-ttu-id="85f7a-274">对于 HTTP 和 HTTPS 端口绑定，安装程序将在默认端口号上创建端口绑定 (端口 80（对于 HTTP）和端口 443（对于 HTTPS) ）。</span><span class="sxs-lookup"><span data-stu-id="85f7a-274">For HTTP and HTTPS port bindings the installer will create port bindings on the default port numbers (port 80 for HTTP and port 443 for HTTPS).</span></span> <span data-ttu-id="85f7a-275">如果计算机上还有一个使用这些绑定的网站，则存在冲突，并且无法预测 IIS 行为。</span><span class="sxs-lookup"><span data-stu-id="85f7a-275">If there is another website on the machine that uses these bindings, there will be a conflict and the IIS behavior cannot be predicted.</span></span> <span data-ttu-id="85f7a-276">避免此问题的最佳方法就是确保在安装 CQD 之前没有将任何其他网站映射到端口 80 和 443。</span><span class="sxs-lookup"><span data-stu-id="85f7a-276">The best way to avoid this problem is to make sure that no other websites are mapped to ports 80 and 443 before installing CQD.</span></span> 
  
<span data-ttu-id="85f7a-277">若要在 IIS 中启用 SSL/TLS 并强制用户通过安全 HTTPS（而不是 HTTP）进行连接：</span><span class="sxs-lookup"><span data-stu-id="85f7a-277">To enable SSL/TLS in IIS and force users to connect via secure HTTPS instead of HTTP:</span></span>
  
1. <span data-ttu-id="85f7a-278">在 IIS 中配置安全套接字层，请参阅在 [IIS 7](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc771438(v=ws.10))中配置安全套接字层。</span><span class="sxs-lookup"><span data-stu-id="85f7a-278">Configure Secure Sockets Layer in IIS, see [Configuring Secure Sockets Layer in IIS 7](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc771438(v=ws.10)).</span></span> <span data-ttu-id="85f7a-279">完成后，将  `http` 替换为 `https` 。</span><span class="sxs-lookup"><span data-stu-id="85f7a-279">Once done, replace  `http` with `https`.</span></span>
    
2. <span data-ttu-id="85f7a-280">有关在连接连接中启用 TLS SQL Server，请参阅如何使用 [Microsoft](https://support.microsoft.com/kb/316898/)管理控制台为 SQL Server 实例启用 SSL 加密。</span><span class="sxs-lookup"><span data-stu-id="85f7a-280">For instructions on enabling TLS in the SQL Server connections, see [How to enable SSL encryption for an instance of SQL Server by using Microsoft Management Console](https://support.microsoft.com/kb/316898/).</span></span>
    
## <a name="cube-sync-fails"></a><span data-ttu-id="85f7a-281">多维数据集同步失败</span><span class="sxs-lookup"><span data-stu-id="85f7a-281">Cube Sync Fails</span></span>

<span data-ttu-id="85f7a-282">QoEMetrics 可能包含一些基于最终用户时钟的无效记录。</span><span class="sxs-lookup"><span data-stu-id="85f7a-282">QoEMetrics may contain some invalid records based on end user clocks.</span></span> <span data-ttu-id="85f7a-283">如果时间斜线大于 60 年，多维数据集导入将失败。</span><span class="sxs-lookup"><span data-stu-id="85f7a-283">If the time skew is greater than 60 yrs, the cube import will fail.</span></span>
  
 <span data-ttu-id="85f7a-284">使用下面的选择检查 Min 和 Max StartTime/EndTime。</span><span class="sxs-lookup"><span data-stu-id="85f7a-284">Check the Min and Max StartTime/EndTime using the selections below.</span></span> <span data-ttu-id="85f7a-285">查找和删除过去和非常远的未来记录，可以忽略这些记录，并且会中断同步过程。</span><span class="sxs-lookup"><span data-stu-id="85f7a-285">Look for and delete records in the far past and very distant future, they can be disregarded and they will break up the sync processes.</span></span>
  
- <span data-ttu-id="85f7a-286">选择 MIN (StartTime) FROM CqdPartitionedStreamView</span><span class="sxs-lookup"><span data-stu-id="85f7a-286">Select MIN(StartTime) FROM CqdPartitionedStreamView</span></span>
    
- <span data-ttu-id="85f7a-287">Select MAX (StartTime) FROM CqdPartitionedStreamView</span><span class="sxs-lookup"><span data-stu-id="85f7a-287">Select MAX(StartTime) FROM CqdPartitionedStreamView</span></span>
    
- <span data-ttu-id="85f7a-288">Select MIN (EndTime) FROM CqdPartitionedStreamView</span><span class="sxs-lookup"><span data-stu-id="85f7a-288">Select MIN(EndTime) FROM CqdPartitionedStreamView</span></span>
    
- <span data-ttu-id="85f7a-289">Select MAX (EndTime) FROM CqdPartitionedStreamView</span><span class="sxs-lookup"><span data-stu-id="85f7a-289">Select MAX(EndTime) FROM CqdPartitionedStreamView</span></span>
    
## <a name="post-install-tasks"></a><span data-ttu-id="85f7a-290">安装后任务</span><span class="sxs-lookup"><span data-stu-id="85f7a-290">Post-install tasks</span></span>

### <a name="importing-buildings-and-networks"></a><span data-ttu-id="85f7a-291">导入大楼和网络</span><span class="sxs-lookup"><span data-stu-id="85f7a-291">Importing Buildings and Networks</span></span>

<span data-ttu-id="85f7a-292">安装 CQD 后，执行以下配置任务：</span><span class="sxs-lookup"><span data-stu-id="85f7a-292">After Installing CQD, perform the following configuration tasks:</span></span>
  
1. <span data-ttu-id="85f7a-293">定义生成类型 (推荐) </span><span class="sxs-lookup"><span data-stu-id="85f7a-293">Define Building types (recommended)</span></span>
    
2. <span data-ttu-id="85f7a-294">定义生成所有权类型 (推荐) </span><span class="sxs-lookup"><span data-stu-id="85f7a-294">Define Building Ownership types (recommended)</span></span>
    
3. <span data-ttu-id="85f7a-295">定义强烈建议 (网络) </span><span class="sxs-lookup"><span data-stu-id="85f7a-295">Define Network types (highly recommended)</span></span>
    
4. <span data-ttu-id="85f7a-296">导入大楼 (推荐) </span><span class="sxs-lookup"><span data-stu-id="85f7a-296">Import Buildings (recommended)</span></span>
    
5. <span data-ttu-id="85f7a-297">导入子网 (推荐) </span><span class="sxs-lookup"><span data-stu-id="85f7a-297">Import Subnets (recommended)</span></span>
    
### <a name="define-building-types"></a><span data-ttu-id="85f7a-298">定义生成类型</span><span class="sxs-lookup"><span data-stu-id="85f7a-298">Define Building Types</span></span>

<span data-ttu-id="85f7a-299">建筑物类型用于描述组织中不同的建筑物定义或类型。</span><span class="sxs-lookup"><span data-stu-id="85f7a-299">Building types are used to describe the different buildings definitions or types within your organization.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="85f7a-300">此步骤是可选的，但建议执行此步骤。</span><span class="sxs-lookup"><span data-stu-id="85f7a-300">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="85f7a-301">示例</span><span class="sxs-lookup"><span data-stu-id="85f7a-301">Examples</span></span>
  
- <span data-ttu-id="85f7a-302">总部</span><span class="sxs-lookup"><span data-stu-id="85f7a-302">Headquarters</span></span>
    
- <span data-ttu-id="85f7a-303">远程 Office</span><span class="sxs-lookup"><span data-stu-id="85f7a-303">Remote Office</span></span>
    
- <span data-ttu-id="85f7a-304">联合位置</span><span class="sxs-lookup"><span data-stu-id="85f7a-304">Joint-venture location</span></span>
    
  <span data-ttu-id="85f7a-305">**示例SQL语法**</span><span class="sxs-lookup"><span data-stu-id="85f7a-305">**Sample SQL Syntax**</span></span>
  
```SQL
INSERT INTO
[dbo].[CqdBuildingType]
([BuildingTypeId],
[BuildingTypeDesc])
VALUES
(1, 
'Headquarters')   
```

<span data-ttu-id="85f7a-306">BuildingTypeId 和 BuildingTypeDesc 参数是必需的。</span><span class="sxs-lookup"><span data-stu-id="85f7a-306">The BuildingTypeId and BuildingTypeDesc parameters are required.</span></span>
  
### <a name="define-building-ownership-types"></a><span data-ttu-id="85f7a-307">定义构建所有权类型</span><span class="sxs-lookup"><span data-stu-id="85f7a-307">Define Building Ownership Types</span></span>

<span data-ttu-id="85f7a-308">所有权类型用于区分拥有的资产和租用的资产。</span><span class="sxs-lookup"><span data-stu-id="85f7a-308">Ownership types are used to distinguish owned vs leased assets.</span></span>
  
> [!NOTE]
> <span data-ttu-id="85f7a-309">此步骤是可选的，但建议执行此步骤。</span><span class="sxs-lookup"><span data-stu-id="85f7a-309">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="85f7a-310">示例</span><span class="sxs-lookup"><span data-stu-id="85f7a-310">Examples</span></span>
  
- <span data-ttu-id="85f7a-311">Contoso 租用的非 RE &amp; F</span><span class="sxs-lookup"><span data-stu-id="85f7a-311">Contoso Leased non-RE&amp;F</span></span>
    
- <span data-ttu-id="85f7a-312">Contoso Leased RE &amp; F</span><span class="sxs-lookup"><span data-stu-id="85f7a-312">Contoso Leased RE&amp;F</span></span>
    
- <span data-ttu-id="85f7a-313">Contoso Owned</span><span class="sxs-lookup"><span data-stu-id="85f7a-313">Contoso Owned</span></span>
    
- <span data-ttu-id="85f7a-314">子公司租用</span><span class="sxs-lookup"><span data-stu-id="85f7a-314">Subsidiary Leased</span></span>
    
  <span data-ttu-id="85f7a-315">**示例SQL语法**</span><span class="sxs-lookup"><span data-stu-id="85f7a-315">**Sample SQL Syntax**</span></span>
  
```SQL
INSERT INTO
[dbo].[CqdBuildingOwnershipType]
([OwnershipTypeId],
[OwnershipTypeDesc]
)

VALUES
(1,
'Contoso Owned'
)
```

<span data-ttu-id="85f7a-316">OwnershipTypeId 和 OwnershipTypeDesc 参数是必需的。</span><span class="sxs-lookup"><span data-stu-id="85f7a-316">The OwnershipTypeId and OwnershipTypeDesc parameters are required.</span></span> 
  
### <a name="define-network-names"></a><span data-ttu-id="85f7a-317">定义网络名称</span><span class="sxs-lookup"><span data-stu-id="85f7a-317">Define Network Names</span></span>

<span data-ttu-id="85f7a-318">网络类型用于描述组织中不同类型的网络。</span><span class="sxs-lookup"><span data-stu-id="85f7a-318">Network Types are used to describe different types of networks within the organization.</span></span> <span data-ttu-id="85f7a-319">这样，您能够基于特定网络 (筛选出) 网络类型。</span><span class="sxs-lookup"><span data-stu-id="85f7a-319">This gives you the ability to filter on (or filter out) specific Network Types.</span></span>
  
> [!NOTE]
> <span data-ttu-id="85f7a-320">强烈建议定义网络名称，但它是可选的。</span><span class="sxs-lookup"><span data-stu-id="85f7a-320">It is highly recommended to define Network Names, but it is optional.</span></span> <span data-ttu-id="85f7a-321">如果您决定不定义网络名称，请确保每个 CqdNetwork 条目的 BuildingId 为 0。</span><span class="sxs-lookup"><span data-stu-id="85f7a-321">If you decide to not define network names, ensure the each CqdNetwork entry has a BuildingId of 0.</span></span> 
  
<span data-ttu-id="85f7a-322">示例</span><span class="sxs-lookup"><span data-stu-id="85f7a-322">Examples</span></span>
  
- <span data-ttu-id="85f7a-323">VPN</span><span class="sxs-lookup"><span data-stu-id="85f7a-323">VPN</span></span>
    
- <span data-ttu-id="85f7a-324">实验室</span><span class="sxs-lookup"><span data-stu-id="85f7a-324">LAB</span></span>
    
  <span data-ttu-id="85f7a-325">**示例SQL语法**</span><span class="sxs-lookup"><span data-stu-id="85f7a-325">**Sample SQL Syntax**</span></span>
  
```SQL
INSERT INTO [dbo].[CqdNetworkName] 
( [NetworkName]
,[NetworkType]
 ) 
VALUES
('VPN','VPN') 
```

<span data-ttu-id="85f7a-326">NetworkNameID 和 NetworkName 参数是必需的，NetworkType 参数是可选的，但建议这样做。</span><span class="sxs-lookup"><span data-stu-id="85f7a-326">The NetworkNameID and NetworkName parameters are required, the NetworkType parameter is optional but recommended.</span></span>
  
### <a name="import-buildings"></a><span data-ttu-id="85f7a-327">导入大楼</span><span class="sxs-lookup"><span data-stu-id="85f7a-327">Import Buildings</span></span>

<span data-ttu-id="85f7a-328">通过导入大楼，你可以获取建筑物特定见解， (WiFi/有线等上的通话质量欠佳) 。</span><span class="sxs-lookup"><span data-stu-id="85f7a-328">Importing Buildings gives you the ability to get building specific insights (poor calls per building on WiFi/Wired, etc.).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="85f7a-329">此步骤是可选的，但建议执行此步骤。</span><span class="sxs-lookup"><span data-stu-id="85f7a-329">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="85f7a-330">在导入新建筑物之前，应该已经标识了预定义的 BuildingKey。</span><span class="sxs-lookup"><span data-stu-id="85f7a-330">Before you Import a new building you should already have a predefined BuildingKey identified.</span></span> <span data-ttu-id="85f7a-331">为此，请发出"SELECT MAX (BuildingKey) FROM CqdBuilding"SQL 命令来标识当前值，并将其添加到结果中。</span><span class="sxs-lookup"><span data-stu-id="85f7a-331">To do that, issue the "SELECT MAX(BuildingKey) FROM CqdBuilding" SQL command to identify the current value and add 1 to the result.</span></span>
  
 <span data-ttu-id="85f7a-332">**示例SQL语法**</span><span class="sxs-lookup"><span data-stu-id="85f7a-332">**Sample SQL Syntax**</span></span>
  
```SQL
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

<span data-ttu-id="85f7a-333">BuildingKey、BuildingName、BuildingShortName、OwnershipTypeId、BuildingTypeId 参数是必需的，其他参数是可选的。</span><span class="sxs-lookup"><span data-stu-id="85f7a-333">The BuildingKey, BuildingName, BuildingShortName, OwnershipTypeId, BuildingTypeId parameters are required, the other parameters are optional.</span></span>
  
### <a name="import-subnets"></a><span data-ttu-id="85f7a-334">导入子网</span><span class="sxs-lookup"><span data-stu-id="85f7a-334">Import Subnets</span></span>

<span data-ttu-id="85f7a-335">通过导入大楼，你可以获取建筑物特定见解， (WiFi/有线等上的通话质量欠佳) 。</span><span class="sxs-lookup"><span data-stu-id="85f7a-335">Importing Buildings gives you the ability to get building specific insights (poor calls per building on WiFi/Wired, etc.).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="85f7a-336">此步骤是可选的，但建议执行此步骤。</span><span class="sxs-lookup"><span data-stu-id="85f7a-336">This step is optional, but recommended.</span></span>
  
<span data-ttu-id="85f7a-337">导入子网，然后将它们映射到上一步中导入的大楼。</span><span class="sxs-lookup"><span data-stu-id="85f7a-337">Import Subnets and map them to the Buildings imported in the last step.</span></span> <span data-ttu-id="85f7a-338">如果您决定不填充 NetworkName，请确保此表中的每个条目都使用 NetworkNameID 0。</span><span class="sxs-lookup"><span data-stu-id="85f7a-338">If you decided not to populate NetworkName, ensure each entry in this table uses a NetworkNameID of 0.</span></span> <span data-ttu-id="85f7a-339">有关呼叫质量SQL语法和参数的信息，请参阅使用 Skype for Business Server 的呼叫 [质量仪表板](./use.md)。</span><span class="sxs-lookup"><span data-stu-id="85f7a-339">For more information on SQL syntax and parameters for the Call Quality Dashboard, see [Use Call Quality Dashboard for Skype for Business Server](./use.md).</span></span>
  
 <span data-ttu-id="85f7a-340">**示例SQL语法**</span><span class="sxs-lookup"><span data-stu-id="85f7a-340">**Sample SQL Syntax**</span></span>
  
```SQL
INSERT INTO [dbo].[CqdNetwork] 
([Network]
,[NetworkRange]
,[NetworkNameID]
,[BuildingKey]
,[UpdatedDate]
)

VALUES
 ('172.16.254.0',32,0,1,'2015-11-11')
```

<span data-ttu-id="85f7a-341">Network 和 UpdatedDate 参数是必需的，其他参数是可选的。</span><span class="sxs-lookup"><span data-stu-id="85f7a-341">The Network, and UpdatedDate parameters are required, the other parameters are optional.</span></span>
  
### <a name="optional-bssid"></a><span data-ttu-id="85f7a-342">可选：BSSID</span><span class="sxs-lookup"><span data-stu-id="85f7a-342">Optional: BSSID</span></span>

<span data-ttu-id="85f7a-343">填充 BSSID 信息可为你提供控制器或无线设备的其他 WiFi 流关联。</span><span class="sxs-lookup"><span data-stu-id="85f7a-343">Populating BSSID information gives you additional WiFi stream correlation by controller or radio.</span></span> <span data-ttu-id="85f7a-344">这是通过构建或子网进行筛选之外。</span><span class="sxs-lookup"><span data-stu-id="85f7a-344">This is in addition to filtering by building or subnet.</span></span> 
  
 <span data-ttu-id="85f7a-345">**示例SQL语法**</span><span class="sxs-lookup"><span data-stu-id="85f7a-345">**Sample SQL Syntax**</span></span>
  
```SQL
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

<span data-ttu-id="85f7a-346">**CqdBssidTable 详细信息**</span><span class="sxs-lookup"><span data-stu-id="85f7a-346">**CqdBssidTable Details**</span></span>

|<span data-ttu-id="85f7a-347">**如 CQD 中所示**</span><span class="sxs-lookup"><span data-stu-id="85f7a-347">**As shown in CQD**</span></span>|<span data-ttu-id="85f7a-348">**CQDBssid 表**</span><span class="sxs-lookup"><span data-stu-id="85f7a-348">**CQDBssid Table**</span></span>|<span data-ttu-id="85f7a-349">**示例输入**</span><span class="sxs-lookup"><span data-stu-id="85f7a-349">**Example inputs**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="85f7a-350">Ap NName</span><span class="sxs-lookup"><span data-stu-id="85f7a-350">Ap NName</span></span>  <br/> |<span data-ttu-id="85f7a-351">AP</span><span class="sxs-lookup"><span data-stu-id="85f7a-351">AP</span></span>  <br/> |<span data-ttu-id="85f7a-352">AP1</span><span class="sxs-lookup"><span data-stu-id="85f7a-352">AP1</span></span>  <br/> |
|<span data-ttu-id="85f7a-353">BBssid</span><span class="sxs-lookup"><span data-stu-id="85f7a-353">BBssid</span></span>  <br/> |<span data-ttu-id="85f7a-354">BSS</span><span class="sxs-lookup"><span data-stu-id="85f7a-354">BSS</span></span>  <br/> |<span data-ttu-id="85f7a-355">00-00-00-00-00-00-00 (必须使用分隔的 fformat) </span><span class="sxs-lookup"><span data-stu-id="85f7a-355">00-00-00-00-00-00 (you must use the delimited fformat)</span></span>  <br/> |
|<span data-ttu-id="85f7a-356">控制器</span><span class="sxs-lookup"><span data-stu-id="85f7a-356">Controller</span></span>  <br/> |<span data-ttu-id="85f7a-357">生成</span><span class="sxs-lookup"><span data-stu-id="85f7a-357">Building</span></span>  <br/> |<span data-ttu-id="85f7a-358">阿鲁巴岛 AP 7</span><span class="sxs-lookup"><span data-stu-id="85f7a-358">Aruba AP 7</span></span>  <br/> |
|<span data-ttu-id="85f7a-359">设备</span><span class="sxs-lookup"><span data-stu-id="85f7a-359">Device</span></span>  <br/> |<span data-ttu-id="85f7a-360">ess</span><span class="sxs-lookup"><span data-stu-id="85f7a-360">ess</span></span>  <br/> |<span data-ttu-id="85f7a-361">Controller1</span><span class="sxs-lookup"><span data-stu-id="85f7a-361">Controller1</span></span>  <br/> |
|<span data-ttu-id="85f7a-362">无线电广播</span><span class="sxs-lookup"><span data-stu-id="85f7a-362">Radio</span></span>  <br/> |<span data-ttu-id="85f7a-363">phy</span><span class="sxs-lookup"><span data-stu-id="85f7a-363">phy</span></span>  <br/> |<span data-ttu-id="85f7a-364">bgn</span><span class="sxs-lookup"><span data-stu-id="85f7a-364">bgn</span></span>  <br/> |
   
### <a name="processing-the-imported-data"></a><span data-ttu-id="85f7a-365">处理导入的数据</span><span class="sxs-lookup"><span data-stu-id="85f7a-365">Processing the imported data</span></span>

<span data-ttu-id="85f7a-366">默认情况下，导入生成/网络数据后，它仅适用于在此时间点之后生成的记录。</span><span class="sxs-lookup"><span data-stu-id="85f7a-366">By default, after you import building/network data it will only apply to records generated after that point in time.</span></span> 
  
<span data-ttu-id="85f7a-367">若要用此新数据标记所有以前的记录，您需要运行 CqdUpdateBuilding 存储过程，如下所示：</span><span class="sxs-lookup"><span data-stu-id="85f7a-367">To tag all the previous records with this new data, you will need to run the CqdUpdateBuilding stored procedure as shown below:</span></span> 
  
<span data-ttu-id="85f7a-368">为记录提供第一个记录的日期 (使用 Select MIN (StartTime) FROM CqdPartitionedStreamView SQL 命令 ) ，即明天的 EndDate，然后为后两个值选择 NULL。</span><span class="sxs-lookup"><span data-stu-id="85f7a-368">Give it the date of your first record (identify that using the Select MIN(StartTime) FROM CqdPartitionedStreamView SQL command ), an EndDate of tomorrow, then NULL for the last two values.</span></span>
  
<span data-ttu-id="85f7a-369">将数据与流数据关联后，SSIS 多维数据集需要重新处理所有记录。</span><span class="sxs-lookup"><span data-stu-id="85f7a-369">Once the data is associated with stream data, the SSIS Cube needs to reprocess all records.</span></span> <span data-ttu-id="85f7a-370">这同样适用于批量添加 BSSID/ISP 数据的情况。</span><span class="sxs-lookup"><span data-stu-id="85f7a-370">This also applies when bulk adding BSSID/ISP data.</span></span> <span data-ttu-id="85f7a-371">确保选中"进程已满"。</span><span class="sxs-lookup"><span data-stu-id="85f7a-371">Ensure that "Process Full" is selected.</span></span>
