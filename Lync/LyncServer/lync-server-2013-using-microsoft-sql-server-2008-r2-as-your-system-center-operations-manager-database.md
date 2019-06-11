---
title: 'Lync Server 2013: 使用 Microsoft SQL Server 2008 R2 作为 System Center Operations Manager 数据库'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using Microsoft SQL Server 2008 R2 as your System Center Operations Manager database
ms:assetid: 0efe76da-8854-499e-bdc7-3623244a8e85
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687969(v=OCS.15)
ms:contentKeyID: 49733555
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 858134b4d7f2a2fbc4e15c14e121ac12679c9ddc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845426"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-microsoft-sql-server-2008-r2-as-your-system-center-operations-manager-database-for-lync-server-2013"></a><span data-ttu-id="5fdff-102">使用 Microsoft SQL Server 2008 R2 作为 Lync Server 2013 的 System Center Operations Manager 数据库</span><span class="sxs-lookup"><span data-stu-id="5fdff-102">Using Microsoft SQL Server 2008 R2 as your System Center Operations Manager database for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5fdff-103">_**主题上次修改时间:** 2013-07-29_</span><span class="sxs-lookup"><span data-stu-id="5fdff-103">_**Topic Last Modified:** 2013-07-29_</span></span>

<span data-ttu-id="5fdff-104">若要将 SQL Server 2008 R2 用作后端数据库, 请完成本主题中详细介绍的步骤。</span><span class="sxs-lookup"><span data-stu-id="5fdff-104">To use SQL Server 2008 R2 as your back-end database, complete the steps detailed in this topic.</span></span>

<div>

## <a name="configuring-sql-server-2008-r2-and-sql-server-reporting-services"></a><span data-ttu-id="5fdff-105">配置 SQL Server 2008 R2 和 SQL Server Reporting Services</span><span class="sxs-lookup"><span data-stu-id="5fdff-105">Configuring SQL Server 2008 R2 and SQL Server Reporting Services</span></span>

<span data-ttu-id="5fdff-106">开始安装 System Center Operations Manager 之前, 必须对 SQL Server 2008 R2 和 SQL Server Reporting Services 配置进行两处更改。</span><span class="sxs-lookup"><span data-stu-id="5fdff-106">Before you begin installing System Center Operations Manager you must make two changes to your SQL Server 2008 R2 and your SQL Server Reporting Services configuration.</span></span> <span data-ttu-id="5fdff-107">(仅当使用 SQL Server 2008 R2 作为 Operations Manager 数据库时, 才需要这些更改。)首先, 在将托管 Operations Manager 数据库的计算机上执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="5fdff-107">(These changes are required only if you are using SQL Server 2008 R2 as your Operations Manager database.) First, do the following on the computer that will host your Operations Manager database:</span></span>

1.  <span data-ttu-id="5fdff-108">单击 "**开始**", 然后单击 "**运行**"。</span><span class="sxs-lookup"><span data-stu-id="5fdff-108">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="5fdff-109">在 "**运行**" 对话框中, 键入 " **\\C:\\程序文件 Microsoft\\ SQL\_Server MSRS10 50\\. ARCHINST\\Reporting Services ReportServer** ", 然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="5fdff-109">In the **Run** dialog box, type **C:\\Program Files\\Microsoft SQL Server\\ MSRS10\_50.ARCHINST\\Reporting Services\\ReportServer** and then press ENTER.</span></span>

3.  <span data-ttu-id="5fdff-110">在**ReportServer**文件夹中, 在记事本或任何其他文本编辑器中打开文件**rsreportserver** 。</span><span class="sxs-lookup"><span data-stu-id="5fdff-110">In the **ReportServer** folder, open the file **rsreportserver.config** in Notepad or any other text editor.</span></span>

4.  <span data-ttu-id="5fdff-111">在文件的开头附近, 你将看到一系列 "添加键" 节点。</span><span class="sxs-lookup"><span data-stu-id="5fdff-111">Near the beginning of the file you will see a series of "Add Key" nodes.</span></span> <span data-ttu-id="5fdff-112">查找开始\*\* \<Add Key = "SecureConnectionLevel"\*\* 的条目, 并将值设置为**0**:</span><span class="sxs-lookup"><span data-stu-id="5fdff-112">Find the entry that begins **\<Add Key="SecureConnectionLevel"** and set the value to **0**:</span></span>
    
        <Add Key="SecureConnectionLevel" Value="0"/>

5.  <span data-ttu-id="5fdff-113">保存文件**rsreportserver** , 然后关闭文本编辑器。</span><span class="sxs-lookup"><span data-stu-id="5fdff-113">Save the file **rsreportserver.config** and then close your text editor.</span></span>

<span data-ttu-id="5fdff-114">更新报表服务器配置文件后, 必须将正确的证书分配给 SQL Server Reporting Services。</span><span class="sxs-lookup"><span data-stu-id="5fdff-114">After updating the Report Server configuration file you must then assign the correct certificate to SQL Server Reporting Services.</span></span> <span data-ttu-id="5fdff-115">为此, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="5fdff-115">To do that:</span></span>

1.  <span data-ttu-id="5fdff-116">单击 "**开始**", 单击 "**所有程序**", 单击 " **Microsoft SQL Server 2008 R2**", 单击 "**配置工具**", 然后单击 " **Reporting Services 配置管理器**"。</span><span class="sxs-lookup"><span data-stu-id="5fdff-116">Click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 R2**, click **Configuration Tools**, and then click **Reporting Services Configuration Manager**.</span></span>

2.  <span data-ttu-id="5fdff-117">在 " **Reporting Services 配置连接**" 对话框中, 确保服务器名称显示在 "**服务器名称**" 框中。</span><span class="sxs-lookup"><span data-stu-id="5fdff-117">In the **Reporting Services Configuration Connection** dialog box, make sure that the name of your server appears in the **Server Name** box.</span></span> <span data-ttu-id="5fdff-118">从 "**报表服务器实例**" 下拉列表中选择要托管 Operations Manager 数据库 (例如, **ARCHINST**) 的 SQL Server 实例, 然后单击 "**连接**"。</span><span class="sxs-lookup"><span data-stu-id="5fdff-118">Select the SQL Server instance that will host your Operations Manager database (for example, **ARCHINST**) from the **Report Server Instance** drop-down list and then click **Connect**.</span></span>

3.  <span data-ttu-id="5fdff-119">在 Reporting Services 配置管理器中, 单击 " **Web 服务 URL**"。</span><span class="sxs-lookup"><span data-stu-id="5fdff-119">In Reporting Services Configuration Manager, click **Web Service URL**.</span></span>

4.  <span data-ttu-id="5fdff-120">在 " **Web 服务 URL** " 页面上, 从 " **SSL 证书**" 下拉列表中选择要用于你的 Reporting Services 的证书, 然后单击 "**应用**"。</span><span class="sxs-lookup"><span data-stu-id="5fdff-120">On the **Web Service URL** page, select the certificate to be used for your Reporting Services from the **SSL Certificate** dropdown list and then click **Apply**.</span></span> <span data-ttu-id="5fdff-121">几秒钟后, 您将看到 "**报表服务器 Web 服务 url**" 下列出了一对 url。</span><span class="sxs-lookup"><span data-stu-id="5fdff-121">After a few seconds, you will see a pair of URLs listed under **Report Server Web Service URLs**.</span></span>

5.  <span data-ttu-id="5fdff-122">单击两个 Url, 验证您是否可以访问 SQL Server Reporting Services。</span><span class="sxs-lookup"><span data-stu-id="5fdff-122">Click both of the URLs to verify that you can access SQL Server Reporting Services.</span></span>

6.  <span data-ttu-id="5fdff-123">关闭 Reporting Services 配置管理器。</span><span class="sxs-lookup"><span data-stu-id="5fdff-123">Close Reporting Services Configuration Manager.</span></span>

</div>

<div>

## <a name="creating-a-system-center-operations-manager-database-for-use-with-sql-server-2008-r2"></a><span data-ttu-id="5fdff-124">创建用于 SQL Server 2008 R2 的 System Center Operations Manager 数据库</span><span class="sxs-lookup"><span data-stu-id="5fdff-124">Creating a System Center Operations Manager database for use with SQL Server 2008 R2</span></span>

<span data-ttu-id="5fdff-125">如果要将 System Center Operations Manager 配置为使用 SQL Server 2008 R2 数据库, 则需要 "手动" 在运行 SQL Server 2008 R2 的计算机上创建 Operations Manager 数据库。</span><span class="sxs-lookup"><span data-stu-id="5fdff-125">If you want to configure System Center Operations Manager to use a SQL Server 2008 R2 database, you will need to "manually" create the Operations Manager database on the computer running SQL Server 2008 R2.</span></span> <span data-ttu-id="5fdff-126">(同样, 如果使用 SQL Server 2005 或 SQL Server 2008 作为后端数据库, 则不需要这些步骤。)</span><span class="sxs-lookup"><span data-stu-id="5fdff-126">(Again, these steps are not required if you are using SQL Server 2005 or SQL Server 2008 as your back-end database.)</span></span>

<span data-ttu-id="5fdff-127">若要手动创建 Operations Manager 数据库, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="5fdff-127">To manually create an Operations Manager database do the following:</span></span>

1.  <span data-ttu-id="5fdff-128">在 System Center Operations Manager 2007 R2 设置媒体的 "SupportTools\\AMD64" 文件夹中, 双击 " **DBCreateWizard**"。</span><span class="sxs-lookup"><span data-stu-id="5fdff-128">On the System Center Operations Manager 2007 R2 setup media, in the SupportTools\\AMD64 folder, double-click **DBCreateWizard.exe**.</span></span>

2.  <span data-ttu-id="5fdff-129">在数据库配置向导的 "**欢迎使用数据库配置向导**" 页面上, 单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="5fdff-129">In the Database Configuration Wizard, on the **Welcome to the Database Configuration Wizard** page, click **Next**.</span></span>

3.  <span data-ttu-id="5fdff-130">在**数据库信息**页面上保留所有设置, 然后单击 "**下一步**"</span><span class="sxs-lookup"><span data-stu-id="5fdff-130">On the **Database Information** page leave all the settings as-is and then click **Next**</span></span>

4.  <span data-ttu-id="5fdff-131">在 "**管理组配置**" 页面上, 在 "**管理组名称**" 框中键入管理组的名称 (例如, **Lync Server Monitoring**), 然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="5fdff-131">On the **Management Group Configuration** page type a name for your Management Group (for example, **Lync Server Monitoring**) in the **Management Group name** box and then click **Next**.</span></span>

5.  <span data-ttu-id="5fdff-132">在 " **Operations Manager 错误报告**" 页面上, 单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="5fdff-132">On the **Operations Manager Error Reports** page click **Next**.</span></span>

6.  <span data-ttu-id="5fdff-133">在 "**摘要**" 页面上单击 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="5fdff-133">On the **Summary** page click **Finish**.</span></span>

</div>

<div>

## <a name="creating-a-system-center-operations-manager-data-warehouse-for-use-with-sql-server-2008-r2"></a><span data-ttu-id="5fdff-134">创建用于 SQL Server 2008 R2 的 System Center Operations Manager 数据仓库</span><span class="sxs-lookup"><span data-stu-id="5fdff-134">Creating a System Center Operations Manager data warehouse for use with SQL Server 2008 R2</span></span>

<span data-ttu-id="5fdff-135">Microsoft Lync Server 2013 随附有三个新的 System Center Operations Manager 报告:</span><span class="sxs-lookup"><span data-stu-id="5fdff-135">Microsoft Lync Server 2013 ships with three new System Center Operations Manager reports:</span></span>

  - <span data-ttu-id="5fdff-136">**端到端方案可用性报告**   此报告详细介绍了关键 Lync 服务器服务 (如注册或联机状态) 的可用性/正常运行时间。</span><span class="sxs-lookup"><span data-stu-id="5fdff-136">**End to End Scenario Availability Report**   This report details the availability/uptime for key Lync Server services such as registration or presence.</span></span>

  - <span data-ttu-id="5fdff-137">**容量报告**   使用性能计数器信息, 此报告显示系统组件 (如内存可用性和处理器使用情况) 的趋势。</span><span class="sxs-lookup"><span data-stu-id="5fdff-137">**Capacity Report**   Using performance counter information, this report shows trends for system components such as memory availability and processor usage.</span></span>

  - <span data-ttu-id="5fdff-138">**组件报告**   此报告列出按 Lync Server 组件分组的顶级警报生成器。</span><span class="sxs-lookup"><span data-stu-id="5fdff-138">**Component Report**   This report lists the top alert generators grouped by Lync Server component.</span></span>

<span data-ttu-id="5fdff-139">为了使用这些新报表, 您必须安装 System Center Operations Manager 数据仓库。</span><span class="sxs-lookup"><span data-stu-id="5fdff-139">In order to use these new reports you must install a System Center Operations Manager data warehouse.</span></span> <span data-ttu-id="5fdff-140">(数据仓库提供运营数据的长期存储。)若要将数据仓库与 SQL Server 2008 R2 配合使用, 您必须在托管 SQL Server 数据库的计算机上执行以下步骤:</span><span class="sxs-lookup"><span data-stu-id="5fdff-140">(A data warehouse provides for long-term storage of operations data.) To use a data warehouse with SQL Server 2008 R2 you must carry out the following steps on the computer that hosts your SQL Server database:</span></span>

1.  <span data-ttu-id="5fdff-141">在 System Center Operations Manager 安装程序媒体上的 "设置\\SupportTools\\AMD64" 文件夹中, 双击 " **DBCreateWizard**"。</span><span class="sxs-lookup"><span data-stu-id="5fdff-141">On the System Center Operations Manager setup media, in the Setup\\SupportTools\\AMD64 folder, double-click **DBCreateWizard.exe**.</span></span>

2.  <span data-ttu-id="5fdff-142">在数据库配置向导的 "**欢迎使用数据库配置向导**" 页面上, 单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="5fdff-142">In the Database Configuration Wizard, on the **Welcome to the Database Configuration Wizard** page, click **Next**.</span></span>

3.  <span data-ttu-id="5fdff-143">在 "**数据库信息**" 页面上, 从 "**数据库类型**" 下拉列表中选择 " **Operations Manager 数据仓库数据库**", 然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="5fdff-143">On the **Database Information** page, select **Operations Manager Data Warehouse Database** from the **Database Type** dropdown list and then click **Next**.</span></span>

4.  <span data-ttu-id="5fdff-144">在 "**摘要**" 页面上单击 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="5fdff-144">On the **Summary** page click **Finish**.</span></span>

</div>

<div>

## <a name="installing-the-system-center-operations-manager-console"></a><span data-ttu-id="5fdff-145">安装 System Center Operations Manager 控制台</span><span class="sxs-lookup"><span data-stu-id="5fdff-145">Installing the System Center Operations Manager console</span></span>

<span data-ttu-id="5fdff-146">Operations Manager 控制台是用于管理 System Center Operations Manager 的主要工具。</span><span class="sxs-lookup"><span data-stu-id="5fdff-146">The Operations Manager console is the primary tool used to manage System Center Operations Manager.</span></span> <span data-ttu-id="5fdff-147">在安装 Operations Manager 控制台之前, 请确保已安装支持的 SQL Server 版本以及 SQL Server Reporting Service。</span><span class="sxs-lookup"><span data-stu-id="5fdff-147">Before you install the Operations Manager console, make sure that you have installed a supported version of SQL Server along with the SQL Server Reporting Service.</span></span> <span data-ttu-id="5fdff-148">还建议你运行 SQL Server 的 Reporting Services 配置管理器, 以验证是否已正确安装和配置报告服务。</span><span class="sxs-lookup"><span data-stu-id="5fdff-148">It is also recommended that you run SQL Server's Reporting Services Configuration Manager to verify that the Reporting Service has been correctly installed and configured.</span></span>

<span data-ttu-id="5fdff-149">要安装 System Center Operations Manager 控制台, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="5fdff-149">To install the System Center Operations Manager console:</span></span>

1.  <span data-ttu-id="5fdff-150">在 System Center Operations Manager 安装程序媒体上, 双击 " **SetupOM**"。</span><span class="sxs-lookup"><span data-stu-id="5fdff-150">On the System Center Operations Manager setup media, double-click **SetupOM.exe**.</span></span>

2.  <span data-ttu-id="5fdff-151">在 System Center Operations Manager 2007 R2 设置中, 单击 "**检查必备项**"。</span><span class="sxs-lookup"><span data-stu-id="5fdff-151">In System Center Operations Manager 2007 R2 Setup, click **Check Prerequisites**.</span></span>

3.  <span data-ttu-id="5fdff-152">在 System Center Operations Manager 必备组件查看器中, 选择要安装的 System Center 组件: (**服务器**;**控制台**;和**PowerShell**), 然后单击 "**检查**"。</span><span class="sxs-lookup"><span data-stu-id="5fdff-152">In the System Center Operations Manager Prerequisite Viewer, select the System Center components to be installed: (**Server**; **Console**; and **PowerShell**) and then click **Check**.</span></span> <span data-ttu-id="5fdff-153">验证未报告任何阻止问题, 然后单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="5fdff-153">Verify that no blocking issues have been reported and then click **Close**.</span></span> <span data-ttu-id="5fdff-154">如果已报告阻止问题, 请更正问题, 然后单击 "**检查**" 以重新运行先决条件测试。</span><span class="sxs-lookup"><span data-stu-id="5fdff-154">If a blocking issue has been reported, correct the problem and then click **Check** to re-run the prerequisite testing.</span></span>

4.  <span data-ttu-id="5fdff-155">在 System Center Operations Manager 安装程序中, 单击 "**安装 Operations Manager**"。</span><span class="sxs-lookup"><span data-stu-id="5fdff-155">In System Center Operations Manager Setup, click **Install Operations Manager**.</span></span>

5.  <span data-ttu-id="5fdff-156">在 System Center Operations Manager 设置向导中的 "**欢迎使用 System Center Operations Manager 安装程序向导**" 页面上, 单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="5fdff-156">In the System Center Operations Manager Setup wizard, on the **Welcome to the System Center Operations Manager Setup Wizard** page, click **Next**.</span></span>

6.  <span data-ttu-id="5fdff-157">在 "**最终用户许可协议**" 页面上, 选择 "**我接受许可协议中的条款"** , 然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="5fdff-157">On the **End-User License Agreement** page, select **I accept the terms in the license agreement** and then click **Next**.</span></span>

7.  <span data-ttu-id="5fdff-158">在 "**产品注册**" 页面上, 在 "**用户名**" 框中键入您的姓名, 在 "**组织**" 框中键入您的组织的名称。</span><span class="sxs-lookup"><span data-stu-id="5fdff-158">On the **Product Registration** page, type your name in the **User Name** box and name of your organization in the **Organization** box.</span></span> <span data-ttu-id="5fdff-159">在 "**输入25个数字的 CD 密钥**" 框中键入 System Center Operations Manager 产品密钥, 然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="5fdff-159">Type your System Center Operations Manager product key in the **Enter your 25 digit CD Key** box and then click **Next**.</span></span>

8.  <span data-ttu-id="5fdff-160">在 "**自定义设置**" 页面上, 选择要安装的 System Center 选项, 然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="5fdff-160">On the **Custom Setup** page select the System Center options to be installed and then click **Next**.</span></span> <span data-ttu-id="5fdff-161">应选择要安装的**管理服务器**、**用户界面**和**Web 控制台**。</span><span class="sxs-lookup"><span data-stu-id="5fdff-161">You should select **Management Server**, **User Interfaces**, and **Web Console** to be installed.</span></span> <span data-ttu-id="5fdff-162">不应选择 "数据库", 也不应安装该**数据库**。</span><span class="sxs-lookup"><span data-stu-id="5fdff-162">**Database** should not be selected and should not be installed.</span></span>

9.  <span data-ttu-id="5fdff-163">在 " **SC 数据库服务器实例**" 页面上, 验证安装了 Operations Manager 数据库的计算机的名称是否显示在 " **System Center 数据库服务器**" 框中。</span><span class="sxs-lookup"><span data-stu-id="5fdff-163">On the **SC Database Server Instance** page, verify that the name of the computer where the Operations Manager databases are installed appears in the **System Center Database Server** box.</span></span> <span data-ttu-id="5fdff-164">单击" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="5fdff-164">Click **Next**.</span></span>

10. <span data-ttu-id="5fdff-165">在 "**管理服务器操作帐户**" 页面上, 选择 "**域或本地计算机帐户**", 然后在 "**用户帐户**"、"**密码**" 和 "**域" 或 "本地计算机**" 框中输入相应的值。</span><span class="sxs-lookup"><span data-stu-id="5fdff-165">On the **Management Server Action Account** page, select **Domain or Local Computer Account** and then enter the appropriate values in the **User Account**, **Password**, and **Domain or local computer** boxes.</span></span> <span data-ttu-id="5fdff-166">单击" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="5fdff-166">Click **Next**.</span></span>

11. <span data-ttu-id="5fdff-167">在 " **SDK 和配置服务帐户**" 页面上, 选择 "**域或本地计算机帐户**", 然后在 "**用户帐户**"、"**密码**" 和 "**域" 或 "本地计算机**" 框中输入相应值。</span><span class="sxs-lookup"><span data-stu-id="5fdff-167">On the **SDK and Config Service Account** page, select **Domain or Local Computer Account** and then enter the appropriate values in the **User Account**, **Password**, and **Domain or local computer** boxes.</span></span> <span data-ttu-id="5fdff-168">单击" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="5fdff-168">Click **Next**.</span></span>

12. <span data-ttu-id="5fdff-169">在 " **Operations Manager 错误报告**" 页面上, 单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="5fdff-169">On the **Operations Manager Error Reports** page click **Next**.</span></span>

13. <span data-ttu-id="5fdff-170">在 "**客户体验改善计划**" 页面上, 单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="5fdff-170">On the **Customer Experience Improvement Program** page click **Next**.</span></span>

14. <span data-ttu-id="5fdff-171">在 "**准备好安装程序**" 页面上, 单击 "**安装**"。</span><span class="sxs-lookup"><span data-stu-id="5fdff-171">On the **Ready to Install the Program** page, click **Install**.</span></span>

15. <span data-ttu-id="5fdff-172">在 "**正在完成 System Center Operations Manager 设置**" 页面上, 清除 "**备份加密密钥**" 并**启动控制台复选框**, 然后单击 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="5fdff-172">On the **Completing the System Center Operations Manager Setup** page, clear the **Backup Encryption Key** and **Start the console checkboxes** and then click **Finish**.</span></span>

16. <span data-ttu-id="5fdff-173">在 System Center Operations Manager 设置中, 单击 "**退出**"。</span><span class="sxs-lookup"><span data-stu-id="5fdff-173">In System Center Operations Manager Setup click **Exit**.</span></span>

</div>

<div>

## <a name="installing-system-center-reporting-services"></a><span data-ttu-id="5fdff-174">安装 System Center Reporting Services</span><span class="sxs-lookup"><span data-stu-id="5fdff-174">Installing System Center Reporting Services</span></span>

<span data-ttu-id="5fdff-175">安装并配置 System Center Operations Manager 控制台后, 必须安装 System Center Reporting Services。</span><span class="sxs-lookup"><span data-stu-id="5fdff-175">After installing and configuring the System Center Operations Manager console you must then install System Center Reporting Services.</span></span> <span data-ttu-id="5fdff-176">如果你将 SQL Server 2008 R2 用作 Operations Manager 后端数据库, 这意味着你必须首先对与 SQL Server Reporting Services 关联的安全组进行临时更改。</span><span class="sxs-lookup"><span data-stu-id="5fdff-176">If you are using SQL Server 2008 R2 as your Operations Manager back-end database, that means that you must first make a temporary change to the security group associated with SQL Server Reporting Services.</span></span> <span data-ttu-id="5fdff-177">如果您使用的是 SQL Server 2008 R2, 则必须执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="5fdff-177">If you are using SQL Server 2008 R2, you must do the following:</span></span>

1.  <span data-ttu-id="5fdff-178">单击 "**开始**", 指向 "**管理工具**", 然后单击 "**服务器管理器**"。</span><span class="sxs-lookup"><span data-stu-id="5fdff-178">Click **Start**, point to **Administrative Tools**, and then click **Server Manager**.</span></span>

2.  <span data-ttu-id="5fdff-179">在服务器管理器中, 展开 "**配置**", 展开 "**本地用户和组**", 然后单击 "**组**"。</span><span class="sxs-lookup"><span data-stu-id="5fdff-179">In Server Manager, expand **Configuration**, expand **Local Users and Groups**, and then click **Groups**.</span></span>

3.  <span data-ttu-id="5fdff-180">找到以下组, 其中 atl-ws-01-001 表示计算机的名称, ARCHINST 表示 System Center 数据库的 SQL Server 实例: **SQLServerReportServerUser $ atl-ws-01-001-001 $ MSRS10\_50. ARCHINST**。</span><span class="sxs-lookup"><span data-stu-id="5fdff-180">Locate the following group, where atl-sc-001 represents the name of your computer and ARCHINST represents the SQL Server instance for the System Center database: **SQLServerReportServerUser$atl-sc-001$MSRS10\_50.ARCHINST**.</span></span>

4.  <span data-ttu-id="5fdff-181">右键单击该组, 然后单击 "**重命名**"。</span><span class="sxs-lookup"><span data-stu-id="5fdff-181">Right-click the group and then click **Rename**.</span></span> <span data-ttu-id="5fdff-182">通过从组名称中删除\*\* \_50\*\*来重命名组。</span><span class="sxs-lookup"><span data-stu-id="5fdff-182">Rename the group by deleting **\_50** from the group name.</span></span> <span data-ttu-id="5fdff-183">例如: **SQLServerReportServerUser $ atl-sc-001 $ MSRS10。ARCHINST**。</span><span class="sxs-lookup"><span data-stu-id="5fdff-183">For example: **SQLServerReportServerUser$atl-sc-001$MSRS10.ARCHINST**.</span></span>

5.  <span data-ttu-id="5fdff-184">关闭服务器管理器。</span><span class="sxs-lookup"><span data-stu-id="5fdff-184">Close Server Manager.</span></span>

<span data-ttu-id="5fdff-185">此时, 你已准备好安装 System Center Reporting Services。</span><span class="sxs-lookup"><span data-stu-id="5fdff-185">At this point you are ready to install System Center Reporting Services.</span></span> <span data-ttu-id="5fdff-186">为此, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="5fdff-186">To do this:</span></span>

1.  <span data-ttu-id="5fdff-187">在 System Center Operations Manager 2007 R2 设置媒体上, 双击 " **SetupOM**"。</span><span class="sxs-lookup"><span data-stu-id="5fdff-187">On the System Center Operations Manager 2007 R2 Setup media, double-click **SetupOM.exe**.</span></span>

2.  <span data-ttu-id="5fdff-188">在 System Center Operations Manager 2007 R2 设置中, 单击 "**安装 Operations Manager Reporting**"。</span><span class="sxs-lookup"><span data-stu-id="5fdff-188">In System Center Operations Manager 2007 R2 Setup, click **Install Operations Manager Reporting**.</span></span>

3.  <span data-ttu-id="5fdff-189">在 System Center Operations Manager 2007 R2 报告设置向导中的 "**欢迎使用 Operations Manager 报告设置**" 页面上, 单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="5fdff-189">In the System Center Operations Manager 2007 R2 Reporting Setup wizard, on the **Welcome to Operations Manager Reporting Setup** page, click **Next**.</span></span>

4.  <span data-ttu-id="5fdff-190">在 "**最终用户许可协议**" 页面上, 选择 "**我接受许可协议的条款"** , 然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="5fdff-190">On the **End-user License Agreement** page select **I accept the terms of the license agreement** and then click **Next**.</span></span>

5.  <span data-ttu-id="5fdff-191">在 "**产品注册**" 页面上, 确保你的名称和组织名称显示在 "**用户名**" 和 "**组织**" 框中, 然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="5fdff-191">On the **Product Registration** page, ensure that your name and the name of your organization appear in the **User Name** and **Organization** boxes and then click **Next**.</span></span>

6.  <span data-ttu-id="5fdff-192">在 "**自定义设置**" 页面上, 单击 "**报告服务器**", 然后选择 "**此组件和所有相关组件" 将安装在本地磁盘驱动器上**。</span><span class="sxs-lookup"><span data-stu-id="5fdff-192">On the **Custom Setup** page, click **Reporting Server** and select **This component, and all dependent components, will be installed on local disk drive**.</span></span> <span data-ttu-id="5fdff-193">单击 "**数据仓库**", 选择 "**此组件将不可用**", 然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="5fdff-193">Click **Data Warehouse** and select **This component will not be available**, and then click **Next**.</span></span>

7.  <span data-ttu-id="5fdff-194">在 "**连接到根管理服务器**" 页面上, 在 "**根管理服务器**" 框中键入 Operations Manager 根管理服务器的名称, 然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="5fdff-194">On the **Connect to the Root Management Server** page, type the name of your Operations Manager root management server in the **Root Management Server** box and then click **Next**.</span></span>

8.  <span data-ttu-id="5fdff-195">在 "**连接到 Operations Manager 数据仓库**" 页面上, 在 " **sql server 实例**" 框中键入您的数据仓库所在的 sql server 实例。</span><span class="sxs-lookup"><span data-stu-id="5fdff-195">On the **Connect to the Operations Manager Data Warehouse** page, type the SQL Server instance where your data warehouse is located in the **SQL Server Instance** box.</span></span> <span data-ttu-id="5fdff-196">(如果数据仓库位于默认实例中, 只需键入服务器名称, 例如: atl-sql-001。)验证 "**名称**" 框中是否显示 "数据库名称**OperationsManagerDW** ", 以及 " **SQL Server 端口**" 框中是否显示 "端口**1433** "。</span><span class="sxs-lookup"><span data-stu-id="5fdff-196">(If your data warehouse is located in the Default instance then simply type the server name; for example: atl-sql-001.) Verify that the database name **OperationsManagerDW** appears in the **Name** box, and that port **1433** appears in the **SQL Server port** box.</span></span> <span data-ttu-id="5fdff-197">单击" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="5fdff-197">Click **Next**.</span></span>

9.  <span data-ttu-id="5fdff-198">在 " **Sql Server 报告实例**" 页面上, 从 "**输入 Sql server reporting Services** " 下拉列表中选择你的 sql server 报告服务器, 然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="5fdff-198">On the **SQL Server Reporting Instance** page, select your SQL Server reporting server from the **Enter the SQL Server Reporting Services Server** dropdown list and then click **Next**.</span></span>

10. <span data-ttu-id="5fdff-199">在 "**数据仓库写入帐户**" 页面上, 在 "**用户帐户**" 和 "**密码**" 框中输入用户最初被分配给数据仓库的 "写入" 权限的用户的名称和密码。</span><span class="sxs-lookup"><span data-stu-id="5fdff-199">On the **Data Warehouse Write Account** page, enter the name and password of the user to be initially assigned write permissions to the data warehouse in the **User Account** and **Password** boxes.</span></span> <span data-ttu-id="5fdff-200">从 "**域**" 下拉列表中选择用户的域, 然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="5fdff-200">Select the user's domain from the **Domain** dropdown list and then click **Next**.</span></span>

11. <span data-ttu-id="5fdff-201">在 "**数据阅读器帐户**" 页面上, 输入 SQL Reporting Services 在 "**用户帐户**" 和 "**密码**" 框中查询数据仓库时要使用的用户帐户的名称和密码。</span><span class="sxs-lookup"><span data-stu-id="5fdff-201">On the **Data Reader Account** page, enter the name and password of the user account to be used when SQL Reporting Services queries the data warehouse in the **User Account** and **Password** boxes.</span></span> <span data-ttu-id="5fdff-202">从 "**域**" 下拉列表中选择帐户域, 然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="5fdff-202">Select the account domain from the **Domain** dropdown list and then click **Next**.</span></span>

12. <span data-ttu-id="5fdff-203">在 "**操作数据报告**" 页面上, 单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="5fdff-203">On the **Operational Data Reports** page, click **Next**.</span></span>

13. <span data-ttu-id="5fdff-204">在 " **Microsoft 更新**" 页面上, 单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="5fdff-204">On the **Microsoft Update** page, click **Next**.</span></span>

14. <span data-ttu-id="5fdff-205">在 "**准备好安装程序**" 页面上, 单击 "**安装**"。</span><span class="sxs-lookup"><span data-stu-id="5fdff-205">On the **Ready to Install the Program** page, click **Install**.</span></span>

15. <span data-ttu-id="5fdff-206">在 "**完成 Operations Manager 报告组件设置向导**" 页面上, 单击 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="5fdff-206">On the **Completing the Operations Manager Reporting Components Setup Wizard** page, click **Finish**.</span></span>

16. <span data-ttu-id="5fdff-207">在 System Center Operations Manager 2007 R2 设置中, 单击 "**退出**"。</span><span class="sxs-lookup"><span data-stu-id="5fdff-207">In System Center Operations Manager 2007 R2 Setup, click **Exit**.</span></span>

<span data-ttu-id="5fdff-208">安装 System Center reporting 后, 你可以使用以下过程重置与 SQL Server 报告关联的安全组的名称。</span><span class="sxs-lookup"><span data-stu-id="5fdff-208">After System Center reporting has been installed you then use the following procedure to reset the name of the security group associated with SQL Server reporting.</span></span> <span data-ttu-id="5fdff-209">同样, 仅当使用 SQL Server 时才需要此过程:</span><span class="sxs-lookup"><span data-stu-id="5fdff-209">Again, this procedure is only required if you are using SQL Server:</span></span>

1.  <span data-ttu-id="5fdff-210">单击 "**开始**", 指向 "**管理工具**", 然后单击 "**服务器管理器**"。</span><span class="sxs-lookup"><span data-stu-id="5fdff-210">Click **Start**, point to **Administrative Tools**, and then click **Server Manager**.</span></span>

2.  <span data-ttu-id="5fdff-211">在服务器管理器中, 展开 "**配置**", 展开 "**本地用户和组**", 然后单击 "**组**"。</span><span class="sxs-lookup"><span data-stu-id="5fdff-211">In Server Manager, expand **Configuration**, expand **Local Users and Groups**, and then click **Groups**.</span></span>

3.  <span data-ttu-id="5fdff-212">找到以下组, 其中 atl-ws-01-001 表示计算机的名称, ARCHINST 表示用于存档和监视数据库的 SQL Server 实例: **SQLServerReportServerUser $ atl-ws-01-001 $ MSRS10。ARCHINST**。</span><span class="sxs-lookup"><span data-stu-id="5fdff-212">Locate the following group, where atl-sc-001 represents the name of your computer and ARCHINST represents the SQL Server instance for the archiving and monitoring databases: **SQLServerReportServerUser$atl-sc-001$MSRS10.ARCHINST**.</span></span>

4.  <span data-ttu-id="5fdff-213">右键单击该组, 然后单击 "**重命名**"。</span><span class="sxs-lookup"><span data-stu-id="5fdff-213">Right-click the group and then click **Rename**.</span></span> <span data-ttu-id="5fdff-214">通过将\*\* \_50\*\*添加到组名称的末尾 (在 SQL Server 实例名称之前), 对组进行重命名。</span><span class="sxs-lookup"><span data-stu-id="5fdff-214">Rename the group by adding **\_50** to the end of the group name, right before the SQL Server instance name.</span></span> <span data-ttu-id="5fdff-215">例如: **SQLServerReportServerUser $ atl-sc-001 $ MSRS10\_50. ARCHINST**。</span><span class="sxs-lookup"><span data-stu-id="5fdff-215">For example: **SQLServerReportServerUser$atl-sc-001$MSRS10\_50.ARCHINST**.</span></span>

5.  <span data-ttu-id="5fdff-216">关闭服务器管理器。</span><span class="sxs-lookup"><span data-stu-id="5fdff-216">Close Server Manager.</span></span>

<span data-ttu-id="5fdff-217">如果 System Center 操作控制台已打开, 你将需要关闭应用程序, 然后重新启动它;如果不执行此操作, "**报告**" 选项卡将不会在操作控制台用户界面中显示。</span><span class="sxs-lookup"><span data-stu-id="5fdff-217">If the System Center Operations Console is open you will need to close the application and then restart it; if you do not do this the **Reporting** tab will not appear in the Operations Console user interface.</span></span> <span data-ttu-id="5fdff-218">请注意, 首次重新启动操作控制台后, 在 "**报告**" 选项卡上显示所有监视报告之前, 可能需要几分钟的时间。</span><span class="sxs-lookup"><span data-stu-id="5fdff-218">Note that, after restarting the Operations Console the first time, it could take several minutes before all the Monitoring Reports appear on the **Reporting** tab.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

