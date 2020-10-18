---
title: Lync Server 2013：使用 Microsoft SQL Server 2008 R2 作为 System Center Operations Manager 数据库
description: Lync Server 2013：使用 Microsoft SQL Server 2008 R2 作为 System Center Operations Manager 数据库。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Microsoft SQL Server 2008 R2 as your System Center Operations Manager database
ms:assetid: 0efe76da-8854-499e-bdc7-3623244a8e85
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687969(v=OCS.15)
ms:contentKeyID: 49733555
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 870c079e7e5e871fc62358e9bdd21653193fad7c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580348"
---
# <a name="using-microsoft-sql-server-2008-r2-as-your-system-center-operations-manager-database-for-lync-server-2013"></a><span data-ttu-id="94326-103">使用 Microsoft SQL Server 2008 R2 作为 Lync Server 2013 的 System Center Operations Manager 数据库</span><span class="sxs-lookup"><span data-stu-id="94326-103">Using Microsoft SQL Server 2008 R2 as your System Center Operations Manager database for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="94326-104">_**上次修改的主题：** 2013-07-29_</span><span class="sxs-lookup"><span data-stu-id="94326-104">_**Topic Last Modified:** 2013-07-29_</span></span>

<span data-ttu-id="94326-105">若要将 SQL Server 2008 R2 用作后端数据库，请完成本主题中详细介绍的步骤。</span><span class="sxs-lookup"><span data-stu-id="94326-105">To use SQL Server 2008 R2 as your back-end database, complete the steps detailed in this topic.</span></span>

<div>

## <a name="configuring-sql-server-2008-r2-and-sql-server-reporting-services"></a><span data-ttu-id="94326-106">配置 SQL Server 2008 R2 和 SQL Server Reporting Services</span><span class="sxs-lookup"><span data-stu-id="94326-106">Configuring SQL Server 2008 R2 and SQL Server Reporting Services</span></span>

<span data-ttu-id="94326-107">在开始安装 System Center Operations Manager 之前，必须对 SQL Server 2008 R2 和 SQL Server Reporting Services 配置进行两处更改。</span><span class="sxs-lookup"><span data-stu-id="94326-107">Before you begin installing System Center Operations Manager you must make two changes to your SQL Server 2008 R2 and your SQL Server Reporting Services configuration.</span></span> <span data-ttu-id="94326-108">仅当您使用 SQL Server 2008 R2 作为 Operations Manager 数据库时，才需要进行这些更改。 ) 首先，在将承载 Operations Manager 数据库的计算机上执行以下操作： (</span><span class="sxs-lookup"><span data-stu-id="94326-108">(These changes are required only if you are using SQL Server 2008 R2 as your Operations Manager database.) First, do the following on the computer that will host your Operations Manager database:</span></span>

1.  <span data-ttu-id="94326-109">单击“开始”\*\*\*\*，再单击“运行”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="94326-109">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="94326-110">在 " **运行** " 对话框中，键入 **C： \\ Program Files \\ Microsoft SQL Server \\ MSRS10 \_ ARCHINST \\ Reporting Services \\ ReportServer** ，然后按 enter。</span><span class="sxs-lookup"><span data-stu-id="94326-110">In the **Run** dialog box, type **C:\\Program Files\\Microsoft SQL Server\\ MSRS10\_50.ARCHINST\\Reporting Services\\ReportServer** and then press ENTER.</span></span>

3.  <span data-ttu-id="94326-111">在 " **ReportServer** " 文件夹中，打开 "记事本" 或任何其他文本编辑器中 **rsreportserver.config** 的文件。</span><span class="sxs-lookup"><span data-stu-id="94326-111">In the **ReportServer** folder, open the file **rsreportserver.config** in Notepad or any other text editor.</span></span>

4.  <span data-ttu-id="94326-112">在文件的开头附近，你将看到一系列 "添加密钥" 节点。</span><span class="sxs-lookup"><span data-stu-id="94326-112">Near the beginning of the file you will see a series of "Add Key" nodes.</span></span> <span data-ttu-id="94326-113">查找开始\*\* \< 添加 Key = "SecureConnectionLevel"\*\* 的条目，并将值设置为**0**：</span><span class="sxs-lookup"><span data-stu-id="94326-113">Find the entry that begins **\<Add Key="SecureConnectionLevel"** and set the value to **0**:</span></span>
    
        <Add Key="SecureConnectionLevel" Value="0"/>

5.  <span data-ttu-id="94326-114">将文件保存 **rsreportserver.config** ，然后关闭文本编辑器。</span><span class="sxs-lookup"><span data-stu-id="94326-114">Save the file **rsreportserver.config** and then close your text editor.</span></span>

<span data-ttu-id="94326-115">更新报表服务器配置文件后，必须将正确的证书分配给 SQL Server Reporting Services。</span><span class="sxs-lookup"><span data-stu-id="94326-115">After updating the Report Server configuration file you must then assign the correct certificate to SQL Server Reporting Services.</span></span> <span data-ttu-id="94326-116">为此，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="94326-116">To do that:</span></span>

1.  <span data-ttu-id="94326-117">依次单击 " **开始**"、" **所有程序**"、" **Microsoft SQL Server 2008 R2**"、" **配置工具**"，然后单击 " **Reporting Services 配置管理器**"。</span><span class="sxs-lookup"><span data-stu-id="94326-117">Click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 R2**, click **Configuration Tools**, and then click **Reporting Services Configuration Manager**.</span></span>

2.  <span data-ttu-id="94326-118">在 " **Reporting Services 配置连接** " 对话框中，确保您的服务器名称显示在 " **服务器名称** " 框中。</span><span class="sxs-lookup"><span data-stu-id="94326-118">In the **Reporting Services Configuration Connection** dialog box, make sure that the name of your server appears in the **Server Name** box.</span></span> <span data-ttu-id="94326-119">选择将承载 Operations Manager 数据库的 SQL Server 实例 (例如， **ARCHINST**) 从 " **报表服务器实例** " 下拉列表中，然后单击 " **连接**"。</span><span class="sxs-lookup"><span data-stu-id="94326-119">Select the SQL Server instance that will host your Operations Manager database (for example, **ARCHINST**) from the **Report Server Instance** drop-down list and then click **Connect**.</span></span>

3.  <span data-ttu-id="94326-120">在 Reporting Services 配置管理器中，单击 " **Web 服务 URL**"。</span><span class="sxs-lookup"><span data-stu-id="94326-120">In Reporting Services Configuration Manager, click **Web Service URL**.</span></span>

4.  <span data-ttu-id="94326-121">在 " **Web 服务 URL** " 页上，从 " **SSL 证书** " 下拉列表中选择要用于您的 Reporting Services 的证书，然后单击 " **应用**"。</span><span class="sxs-lookup"><span data-stu-id="94326-121">On the **Web Service URL** page, select the certificate to be used for your Reporting Services from the **SSL Certificate** dropdown list and then click **Apply**.</span></span> <span data-ttu-id="94326-122">几秒钟后，您将看到 " **报表服务器 Web 服务 url**" 下列出的一对 url。</span><span class="sxs-lookup"><span data-stu-id="94326-122">After a few seconds, you will see a pair of URLs listed under **Report Server Web Service URLs**.</span></span>

5.  <span data-ttu-id="94326-123">单击这两个 Url 以验证您是否可以访问 SQL Server Reporting Services。</span><span class="sxs-lookup"><span data-stu-id="94326-123">Click both of the URLs to verify that you can access SQL Server Reporting Services.</span></span>

6.  <span data-ttu-id="94326-124">关闭 Reporting Services 配置管理器。</span><span class="sxs-lookup"><span data-stu-id="94326-124">Close Reporting Services Configuration Manager.</span></span>

</div>

<div>

## <a name="creating-a-system-center-operations-manager-database-for-use-with-sql-server-2008-r2"></a><span data-ttu-id="94326-125">创建用于 SQL Server 2008 R2 的 System Center Operations Manager 数据库</span><span class="sxs-lookup"><span data-stu-id="94326-125">Creating a System Center Operations Manager database for use with SQL Server 2008 R2</span></span>

<span data-ttu-id="94326-126">如果要将 System Center Operations Manager 配置为使用 SQL Server 2008 R2 数据库，将需要 "手动" 在运行 SQL Server 2008 R2 的计算机上创建 Operations Manager 数据库。</span><span class="sxs-lookup"><span data-stu-id="94326-126">If you want to configure System Center Operations Manager to use a SQL Server 2008 R2 database, you will need to "manually" create the Operations Manager database on the computer running SQL Server 2008 R2.</span></span> <span data-ttu-id="94326-127"> (同样，如果您使用 SQL Server 2005 或 SQL Server 2008 作为后端数据库，则不需要执行这些步骤。 ) </span><span class="sxs-lookup"><span data-stu-id="94326-127">(Again, these steps are not required if you are using SQL Server 2005 or SQL Server 2008 as your back-end database.)</span></span>

<span data-ttu-id="94326-128">若要手动创建 Operations Manager 数据库，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="94326-128">To manually create an Operations Manager database do the following:</span></span>

1.  <span data-ttu-id="94326-129">在 System Center Operations Manager 2007 R2 安装媒体上，在 SupportTools \\ AMD64 文件夹中，双击 **DBCreateWizard.exe**"。</span><span class="sxs-lookup"><span data-stu-id="94326-129">On the System Center Operations Manager 2007 R2 setup media, in the SupportTools\\AMD64 folder, double-click **DBCreateWizard.exe**.</span></span>

2.  <span data-ttu-id="94326-130">在数据库配置向导中的 " **欢迎使用数据库配置向导** " 页上，单击 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="94326-130">In the Database Configuration Wizard, on the **Welcome to the Database Configuration Wizard** page, click **Next**.</span></span>

3.  <span data-ttu-id="94326-131">在**数据库信息**页面上，将所有设置保留为，然后单击 "**下一步**"</span><span class="sxs-lookup"><span data-stu-id="94326-131">On the **Database Information** page leave all the settings as-is and then click **Next**</span></span>

4.  <span data-ttu-id="94326-132">在 "**管理组配置**" 页上，键入管理组的名称 (例如，在 "**管理组名称**" 框中) " **Lync Server 监控**"，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="94326-132">On the **Management Group Configuration** page type a name for your Management Group (for example, **Lync Server Monitoring**) in the **Management Group name** box and then click **Next**.</span></span>

5.  <span data-ttu-id="94326-133">在 " **Operations Manager 错误报告** " 页上单击 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="94326-133">On the **Operations Manager Error Reports** page click **Next**.</span></span>

6.  <span data-ttu-id="94326-134">在 " **摘要** " 页上单击 " **完成**"。</span><span class="sxs-lookup"><span data-stu-id="94326-134">On the **Summary** page click **Finish**.</span></span>

</div>

<div>

## <a name="creating-a-system-center-operations-manager-data-warehouse-for-use-with-sql-server-2008-r2"></a><span data-ttu-id="94326-135">创建用于 SQL Server 2008 R2 的 System Center Operations Manager 数据仓库</span><span class="sxs-lookup"><span data-stu-id="94326-135">Creating a System Center Operations Manager data warehouse for use with SQL Server 2008 R2</span></span>

<span data-ttu-id="94326-136">Microsoft Lync Server 2013 随附三个新的 System Center Operations Manager 报告：</span><span class="sxs-lookup"><span data-stu-id="94326-136">Microsoft Lync Server 2013 ships with three new System Center Operations Manager reports:</span></span>

  - <span data-ttu-id="94326-137">**端到端方案可用性报告**    此报告详细说明了关键 Lync Server 服务（如注册或状态）的可用性/正常运行时间。</span><span class="sxs-lookup"><span data-stu-id="94326-137">**End to End Scenario Availability Report**   This report details the availability/uptime for key Lync Server services such as registration or presence.</span></span>

  - <span data-ttu-id="94326-138">**容量报告**    使用性能计数器信息，此报告显示系统组件（如内存可用性和处理器使用率）的趋势。</span><span class="sxs-lookup"><span data-stu-id="94326-138">**Capacity Report**   Using performance counter information, this report shows trends for system components such as memory availability and processor usage.</span></span>

  - <span data-ttu-id="94326-139">**组件报告**    此报告列出了按 Lync Server 组件分组的顶部警报生成器。</span><span class="sxs-lookup"><span data-stu-id="94326-139">**Component Report**   This report lists the top alert generators grouped by Lync Server component.</span></span>

<span data-ttu-id="94326-140">必须安装 System Center Operations Manager 数据仓库，才能使用这些新报告。</span><span class="sxs-lookup"><span data-stu-id="94326-140">In order to use these new reports you must install a System Center Operations Manager data warehouse.</span></span> <span data-ttu-id="94326-141"> (数据仓库可用于长期存储运营数据。 ) 若要使用包含 SQL Server 2008 R2 的数据仓库，您必须在承载 SQL Server 数据库的计算机上执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="94326-141">(A data warehouse provides for long-term storage of operations data.) To use a data warehouse with SQL Server 2008 R2 you must carry out the following steps on the computer that hosts your SQL Server database:</span></span>

1.  <span data-ttu-id="94326-142">在 System Center Operations Manager 安装程序媒体上的 "Setup \\ SupportTools \\ AMD64" 文件夹中，双击 " **DBCreateWizard.exe**"。</span><span class="sxs-lookup"><span data-stu-id="94326-142">On the System Center Operations Manager setup media, in the Setup\\SupportTools\\AMD64 folder, double-click **DBCreateWizard.exe**.</span></span>

2.  <span data-ttu-id="94326-143">在数据库配置向导中的 " **欢迎使用数据库配置向导** " 页上，单击 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="94326-143">In the Database Configuration Wizard, on the **Welcome to the Database Configuration Wizard** page, click **Next**.</span></span>

3.  <span data-ttu-id="94326-144">在 "**数据库信息**" 页上，从 "**数据库类型**" 下拉列表中选择 " **Operations Manager 数据仓库数据库**"，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="94326-144">On the **Database Information** page, select **Operations Manager Data Warehouse Database** from the **Database Type** dropdown list and then click **Next**.</span></span>

4.  <span data-ttu-id="94326-145">在 " **摘要** " 页上单击 " **完成**"。</span><span class="sxs-lookup"><span data-stu-id="94326-145">On the **Summary** page click **Finish**.</span></span>

</div>

<div>

## <a name="installing-the-system-center-operations-manager-console"></a><span data-ttu-id="94326-146">安装 System Center Operations Manager 控制台</span><span class="sxs-lookup"><span data-stu-id="94326-146">Installing the System Center Operations Manager console</span></span>

<span data-ttu-id="94326-147">Operations Manager 控制台是用于管理 System Center Operations Manager 的主要工具。</span><span class="sxs-lookup"><span data-stu-id="94326-147">The Operations Manager console is the primary tool used to manage System Center Operations Manager.</span></span> <span data-ttu-id="94326-148">在安装 Operations Manager 控制台之前，请确保已安装支持的 SQL Server 版本和 SQL Server Reporting Service。</span><span class="sxs-lookup"><span data-stu-id="94326-148">Before you install the Operations Manager console, make sure that you have installed a supported version of SQL Server along with the SQL Server Reporting Service.</span></span> <span data-ttu-id="94326-149">此外，还建议您运行 SQL Server 的 Reporting Services 配置管理器，以验证是否已正确安装和配置报告服务。</span><span class="sxs-lookup"><span data-stu-id="94326-149">It is also recommended that you run SQL Server's Reporting Services Configuration Manager to verify that the Reporting Service has been correctly installed and configured.</span></span>

<span data-ttu-id="94326-150">若要安装 System Center Operations Manager 控制台，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="94326-150">To install the System Center Operations Manager console:</span></span>

1.  <span data-ttu-id="94326-151">在 System Center Operations Manager 安装程序媒体上，双击 " **SetupOM.exe**"。</span><span class="sxs-lookup"><span data-stu-id="94326-151">On the System Center Operations Manager setup media, double-click **SetupOM.exe**.</span></span>

2.  <span data-ttu-id="94326-152">在 System Center Operations Manager 2007 R2 安装程序中，单击 " **检查必备组件**"。</span><span class="sxs-lookup"><span data-stu-id="94326-152">In System Center Operations Manager 2007 R2 Setup, click **Check Prerequisites**.</span></span>

3.  <span data-ttu-id="94326-153">在 System Center Operations Manager 必备组件查看器中，选择要安装的 System Center 组件： (**服务器**; **控制台**;和 **PowerShell**) 然后单击 " **检查**"。</span><span class="sxs-lookup"><span data-stu-id="94326-153">In the System Center Operations Manager Prerequisite Viewer, select the System Center components to be installed: (**Server**; **Console**; and **PowerShell**) and then click **Check**.</span></span> <span data-ttu-id="94326-154">验证是否未报告任何阻止问题，然后单击 " **关闭**"。</span><span class="sxs-lookup"><span data-stu-id="94326-154">Verify that no blocking issues have been reported and then click **Close**.</span></span> <span data-ttu-id="94326-155">如果已报告阻止问题，请更正问题，然后单击 " **检查** " 以重新运行先决条件测试。</span><span class="sxs-lookup"><span data-stu-id="94326-155">If a blocking issue has been reported, correct the problem and then click **Check** to re-run the prerequisite testing.</span></span>

4.  <span data-ttu-id="94326-156">在 System Center Operations Manager 安装程序中，单击 " **安装 Operations Manager**"。</span><span class="sxs-lookup"><span data-stu-id="94326-156">In System Center Operations Manager Setup, click **Install Operations Manager**.</span></span>

5.  <span data-ttu-id="94326-157">在 System Center Operations Manager 安装向导中，在 " **欢迎使用 System Center Operations Manager 安装向导** " 页上，单击 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="94326-157">In the System Center Operations Manager Setup wizard, on the **Welcome to the System Center Operations Manager Setup Wizard** page, click **Next**.</span></span>

6.  <span data-ttu-id="94326-158">在 " **最终用户许可协议** " 页上，选择 " **我接受许可协议中的条款"** ，然后单击 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="94326-158">On the **End-User License Agreement** page, select **I accept the terms in the license agreement** and then click **Next**.</span></span>

7.  <span data-ttu-id="94326-159">在 " **产品注册** " 页上，在 " **用户名** " 框中键入您的姓名，并在 " **组织** " 框中键入您的组织的名称。</span><span class="sxs-lookup"><span data-stu-id="94326-159">On the **Product Registration** page, type your name in the **User Name** box and name of your organization in the **Organization** box.</span></span> <span data-ttu-id="94326-160">在 " **输入25个数字的 CD 密钥** " 框中键入 System Center Operations Manager 产品密钥，然后单击 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="94326-160">Type your System Center Operations Manager product key in the **Enter your 25 digit CD Key** box and then click **Next**.</span></span>

8.  <span data-ttu-id="94326-161">在 " **自定义安装** " 页上，选择要安装的 System Center 选项，然后单击 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="94326-161">On the **Custom Setup** page select the System Center options to be installed and then click **Next**.</span></span> <span data-ttu-id="94326-162">应选择要安装的 **管理服务器**、 **用户界面**和 **Web 控制台** 。</span><span class="sxs-lookup"><span data-stu-id="94326-162">You should select **Management Server**, **User Interfaces**, and **Web Console** to be installed.</span></span> <span data-ttu-id="94326-163">不应选择**数据库**且不应安装它。</span><span class="sxs-lookup"><span data-stu-id="94326-163">**Database** should not be selected and should not be installed.</span></span>

9.  <span data-ttu-id="94326-164">在 " **SC Database Server Instance** " 页上，验证安装了 Operations Manager 数据库的计算机的名称是否出现在 " **System Center 数据库服务器** " 框中。</span><span class="sxs-lookup"><span data-stu-id="94326-164">On the **SC Database Server Instance** page, verify that the name of the computer where the Operations Manager databases are installed appears in the **System Center Database Server** box.</span></span> <span data-ttu-id="94326-165">单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="94326-165">Click **Next**.</span></span>

10. <span data-ttu-id="94326-166">在 " **管理服务器操作帐户** " 页上，选择 " **域或本地计算机帐户** "，然后在 " **用户帐户**"、" **密码**" 和 " **域" 或 "本地计算机** " 框中输入适当的值。</span><span class="sxs-lookup"><span data-stu-id="94326-166">On the **Management Server Action Account** page, select **Domain or Local Computer Account** and then enter the appropriate values in the **User Account**, **Password**, and **Domain or local computer** boxes.</span></span> <span data-ttu-id="94326-167">单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="94326-167">Click **Next**.</span></span>

11. <span data-ttu-id="94326-168">在 " **SDK 和 Config 服务帐户** " 页上，选择 " **域或本地计算机帐户** "，然后在 " **用户帐户**"、" **密码**" 和 " **域" 或 "本地计算机** " 框中输入适当的值。</span><span class="sxs-lookup"><span data-stu-id="94326-168">On the **SDK and Config Service Account** page, select **Domain or Local Computer Account** and then enter the appropriate values in the **User Account**, **Password**, and **Domain or local computer** boxes.</span></span> <span data-ttu-id="94326-169">单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="94326-169">Click **Next**.</span></span>

12. <span data-ttu-id="94326-170">在 " **Operations Manager 错误报告** " 页上单击 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="94326-170">On the **Operations Manager Error Reports** page click **Next**.</span></span>

13. <span data-ttu-id="94326-171">在 " **客户体验改善计划** " 页上，单击 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="94326-171">On the **Customer Experience Improvement Program** page click **Next**.</span></span>

14. <span data-ttu-id="94326-172">在 " **准备安装程序"** 页上，单击 " **安装**"。</span><span class="sxs-lookup"><span data-stu-id="94326-172">On the **Ready to Install the Program** page, click **Install**.</span></span>

15. <span data-ttu-id="94326-173">在 " **正在完成 System Center Operations Manager 安装程序** " 页上，清除 " **备份加密密钥** " 并 **启动控制台复选框** ，然后单击 " **完成**"。</span><span class="sxs-lookup"><span data-stu-id="94326-173">On the **Completing the System Center Operations Manager Setup** page, clear the **Backup Encryption Key** and **Start the console checkboxes** and then click **Finish**.</span></span>

16. <span data-ttu-id="94326-174">在 System Center Operations Manager 安装程序中，单击 " **退出**"。</span><span class="sxs-lookup"><span data-stu-id="94326-174">In System Center Operations Manager Setup click **Exit**.</span></span>

</div>

<div>

## <a name="installing-system-center-reporting-services"></a><span data-ttu-id="94326-175">安装 System Center Reporting Services</span><span class="sxs-lookup"><span data-stu-id="94326-175">Installing System Center Reporting Services</span></span>

<span data-ttu-id="94326-176">在安装和配置 System Center Operations Manager 控制台之后，必须安装 System Center Reporting Services。</span><span class="sxs-lookup"><span data-stu-id="94326-176">After installing and configuring the System Center Operations Manager console you must then install System Center Reporting Services.</span></span> <span data-ttu-id="94326-177">如果要将 SQL Server 2008 R2 用作 Operations Manager 后端数据库，则意味着必须首先对与 SQL Server Reporting Services 关联的安全组进行临时更改。</span><span class="sxs-lookup"><span data-stu-id="94326-177">If you are using SQL Server 2008 R2 as your Operations Manager back-end database, that means that you must first make a temporary change to the security group associated with SQL Server Reporting Services.</span></span> <span data-ttu-id="94326-178">如果使用的是 SQL Server 2008 R2，则必须执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="94326-178">If you are using SQL Server 2008 R2, you must do the following:</span></span>

1.  <span data-ttu-id="94326-179">单击"开始"，指向"管理工具"，然后单击"服务器管理器"。</span><span class="sxs-lookup"><span data-stu-id="94326-179">Click **Start**, point to **Administrative Tools**, and then click **Server Manager**.</span></span>

2.  <span data-ttu-id="94326-180">在服务器管理器中，展开“配置”\*\*\*\*，展开“本地用户和组”\*\*\*\*，然后单击“组”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="94326-180">In Server Manager, expand **Configuration**, expand **Local Users and Groups**, and then click **Groups**.</span></span>

3.  <span data-ttu-id="94326-181">找到以下组，其中 atl-ws-01-001 表示您的计算机的名称，ARCHINST 表示 System Center 数据库的 SQL Server 实例： **SQLServerReportServerUser $ atl-sc-001 $ MSRS10 \_ 50. ARCHINST**。</span><span class="sxs-lookup"><span data-stu-id="94326-181">Locate the following group, where atl-sc-001 represents the name of your computer and ARCHINST represents the SQL Server instance for the System Center database: **SQLServerReportServerUser$atl-sc-001$MSRS10\_50.ARCHINST**.</span></span>

4.  <span data-ttu-id="94326-182">右键单击该组，然后单击 " **重命名**"。</span><span class="sxs-lookup"><span data-stu-id="94326-182">Right-click the group and then click **Rename**.</span></span> <span data-ttu-id="94326-183">通过从组名称中删除\*\* \_ 50\*\*来重命名组。</span><span class="sxs-lookup"><span data-stu-id="94326-183">Rename the group by deleting **\_50** from the group name.</span></span> <span data-ttu-id="94326-184">例如： **SQLServerReportServerUser $ atl-sc-001 $ MSRS10。ARCHINST**。</span><span class="sxs-lookup"><span data-stu-id="94326-184">For example: **SQLServerReportServerUser$atl-sc-001$MSRS10.ARCHINST**.</span></span>

5.  <span data-ttu-id="94326-185">关闭服务器管理器。</span><span class="sxs-lookup"><span data-stu-id="94326-185">Close Server Manager.</span></span>

<span data-ttu-id="94326-186">此时，你已准备好安装 System Center Reporting Services。</span><span class="sxs-lookup"><span data-stu-id="94326-186">At this point you are ready to install System Center Reporting Services.</span></span> <span data-ttu-id="94326-187">若要执行此操作：</span><span class="sxs-lookup"><span data-stu-id="94326-187">To do this:</span></span>

1.  <span data-ttu-id="94326-188">在 System Center Operations Manager 2007 R2 安装程序媒体上，双击 " **SetupOM.exe**"。</span><span class="sxs-lookup"><span data-stu-id="94326-188">On the System Center Operations Manager 2007 R2 Setup media, double-click **SetupOM.exe**.</span></span>

2.  <span data-ttu-id="94326-189">在 System Center Operations Manager 2007 R2 安装程序中，单击 " **安装 Operations Manager 报告**"。</span><span class="sxs-lookup"><span data-stu-id="94326-189">In System Center Operations Manager 2007 R2 Setup, click **Install Operations Manager Reporting**.</span></span>

3.  <span data-ttu-id="94326-190">在 System Center Operations Manager 2007 R2 报告安装向导中，在 " **欢迎使用 Operations Manager 报告安装程序** " 页上，单击 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="94326-190">In the System Center Operations Manager 2007 R2 Reporting Setup wizard, on the **Welcome to Operations Manager Reporting Setup** page, click **Next**.</span></span>

4.  <span data-ttu-id="94326-191">在 " **最终用户许可协议** " 页上，选择 " **我接受许可协议的条款"** ，然后单击 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="94326-191">On the **End-user License Agreement** page select **I accept the terms of the license agreement** and then click **Next**.</span></span>

5.  <span data-ttu-id="94326-192">在 " **产品注册** " 页上，确保 " **用户名** " 和 " **组织** " 框中显示您的姓名和组织名称，然后单击 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="94326-192">On the **Product Registration** page, ensure that your name and the name of your organization appear in the **User Name** and **Organization** boxes and then click **Next**.</span></span>

6.  <span data-ttu-id="94326-193">在 " **自定义安装** " 页上，单击 " **报告服务器** "，然后选择 " **此组件和所有相关组件将安装在本地磁盘驱动器上**"。</span><span class="sxs-lookup"><span data-stu-id="94326-193">On the **Custom Setup** page, click **Reporting Server** and select **This component, and all dependent components, will be installed on local disk drive**.</span></span> <span data-ttu-id="94326-194">单击 " **数据仓库** "，选择 " **此组件将不可用**"，然后单击 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="94326-194">Click **Data Warehouse** and select **This component will not be available**, and then click **Next**.</span></span>

7.  <span data-ttu-id="94326-195">在 " **连接到根管理服务器** " 页上，在 " **根管理服务器** " 框中键入 Operations Manager 根管理服务器的名称，然后单击 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="94326-195">On the **Connect to the Root Management Server** page, type the name of your Operations Manager root management server in the **Root Management Server** box and then click **Next**.</span></span>

8.  <span data-ttu-id="94326-196">在 " **连接到 Operations Manager 数据仓库** " 页上，在 " **sql server 实例** " 框中键入您的数据仓库所在的 sql server 实例。</span><span class="sxs-lookup"><span data-stu-id="94326-196">On the **Connect to the Operations Manager Data Warehouse** page, type the SQL Server instance where your data warehouse is located in the **SQL Server Instance** box.</span></span> <span data-ttu-id="94326-197"> (如果您的数据仓库位于默认实例中，只需键入服务器名称即可;例如： atl-sql-001. ) 验证数据库名称**OperationsManagerDW**是否出现在 "**名称**" 框中，并显示 " **sql Server 端口**" 框中显示的 "端口**1433** "。</span><span class="sxs-lookup"><span data-stu-id="94326-197">(If your data warehouse is located in the Default instance then simply type the server name; for example: atl-sql-001.) Verify that the database name **OperationsManagerDW** appears in the **Name** box, and that port **1433** appears in the **SQL Server port** box.</span></span> <span data-ttu-id="94326-198">单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="94326-198">Click **Next**.</span></span>

9.  <span data-ttu-id="94326-199">在 " **Sql Server 报告实例** " 页上，从 " **输入 Sql Server reporting Services 服务器** " 下拉列表中选择您的 sql server 报告服务器，然后单击 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="94326-199">On the **SQL Server Reporting Instance** page, select your SQL Server reporting server from the **Enter the SQL Server Reporting Services Server** dropdown list and then click **Next**.</span></span>

10. <span data-ttu-id="94326-200">在 " **数据仓库写入帐户** " 页上，在 " **用户帐户** " 和 " **密码** " 框中输入要最初为其分配的对数据仓库的写入权限的用户的名称和密码。</span><span class="sxs-lookup"><span data-stu-id="94326-200">On the **Data Warehouse Write Account** page, enter the name and password of the user to be initially assigned write permissions to the data warehouse in the **User Account** and **Password** boxes.</span></span> <span data-ttu-id="94326-201">从 " **域** " 下拉列表中选择用户的域，然后单击 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="94326-201">Select the user's domain from the **Domain** dropdown list and then click **Next**.</span></span>

11. <span data-ttu-id="94326-202">在 " **数据读取器帐户** " 页上，输入 SQL Reporting Services 在 " **用户帐户** " 和 " **密码** " 框中查询数据仓库时要使用的用户帐户的名称和密码。</span><span class="sxs-lookup"><span data-stu-id="94326-202">On the **Data Reader Account** page, enter the name and password of the user account to be used when SQL Reporting Services queries the data warehouse in the **User Account** and **Password** boxes.</span></span> <span data-ttu-id="94326-203">从 " **域** " 下拉列表中选择帐户域，然后单击 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="94326-203">Select the account domain from the **Domain** dropdown list and then click **Next**.</span></span>

12. <span data-ttu-id="94326-204">在 " **操作数据报告** " 页上，单击 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="94326-204">On the **Operational Data Reports** page, click **Next**.</span></span>

13. <span data-ttu-id="94326-205">在 " **Microsoft 更新** " 页上，单击 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="94326-205">On the **Microsoft Update** page, click **Next**.</span></span>

14. <span data-ttu-id="94326-206">在 " **准备安装程序"** 页上，单击 " **安装**"。</span><span class="sxs-lookup"><span data-stu-id="94326-206">On the **Ready to Install the Program** page, click **Install**.</span></span>

15. <span data-ttu-id="94326-207">在 " **正在完成 Operations Manager 报告组件安装向导** " 页上，单击 " **完成**"。</span><span class="sxs-lookup"><span data-stu-id="94326-207">On the **Completing the Operations Manager Reporting Components Setup Wizard** page, click **Finish**.</span></span>

16. <span data-ttu-id="94326-208">在 System Center Operations Manager 2007 R2 安装程序中，单击 " **退出**"。</span><span class="sxs-lookup"><span data-stu-id="94326-208">In System Center Operations Manager 2007 R2 Setup, click **Exit**.</span></span>

<span data-ttu-id="94326-209">安装 System Center reporting 后，请使用以下过程重置与 SQL Server 报告关联的安全组的名称。</span><span class="sxs-lookup"><span data-stu-id="94326-209">After System Center reporting has been installed you then use the following procedure to reset the name of the security group associated with SQL Server reporting.</span></span> <span data-ttu-id="94326-210">同样，仅当您使用 SQL Server 时，才需要执行此过程：</span><span class="sxs-lookup"><span data-stu-id="94326-210">Again, this procedure is only required if you are using SQL Server:</span></span>

1.  <span data-ttu-id="94326-211">单击"开始"，指向"管理工具"，然后单击"服务器管理器"。</span><span class="sxs-lookup"><span data-stu-id="94326-211">Click **Start**, point to **Administrative Tools**, and then click **Server Manager**.</span></span>

2.  <span data-ttu-id="94326-212">在服务器管理器中，展开“配置”\*\*\*\*，展开“本地用户和组”\*\*\*\*，然后单击“组”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="94326-212">In Server Manager, expand **Configuration**, expand **Local Users and Groups**, and then click **Groups**.</span></span>

3.  <span data-ttu-id="94326-213">找到以下组，其中 atl-ws-01-001 表示您的计算机的名称，ARCHINST 表示用于存档和监视数据库的 SQL Server 实例： **SQLServerReportServerUser $ atl-ws-01-001 $ MSRS10。ARCHINST**。</span><span class="sxs-lookup"><span data-stu-id="94326-213">Locate the following group, where atl-sc-001 represents the name of your computer and ARCHINST represents the SQL Server instance for the archiving and monitoring databases: **SQLServerReportServerUser$atl-sc-001$MSRS10.ARCHINST**.</span></span>

4.  <span data-ttu-id="94326-214">右键单击该组，然后单击 " **重命名**"。</span><span class="sxs-lookup"><span data-stu-id="94326-214">Right-click the group and then click **Rename**.</span></span> <span data-ttu-id="94326-215">通过将\*\* \_ 50\*\*添加到组名称的末尾，在 SQL Server 实例名称前面添加 "." 对组进行重命名。</span><span class="sxs-lookup"><span data-stu-id="94326-215">Rename the group by adding **\_50** to the end of the group name, right before the SQL Server instance name.</span></span> <span data-ttu-id="94326-216">例如： **SQLServerReportServerUser $ atl-sc-001 $ MSRS10 \_ 50. ARCHINST**。</span><span class="sxs-lookup"><span data-stu-id="94326-216">For example: **SQLServerReportServerUser$atl-sc-001$MSRS10\_50.ARCHINST**.</span></span>

5.  <span data-ttu-id="94326-217">关闭服务器管理器。</span><span class="sxs-lookup"><span data-stu-id="94326-217">Close Server Manager.</span></span>

<span data-ttu-id="94326-218">如果 System Center Operations 控制台处于打开状态，你将需要关闭应用程序，然后重新启动它;如果不执行此操作，则 " **报告** " 选项卡不会显示在操作控制台用户界面中。</span><span class="sxs-lookup"><span data-stu-id="94326-218">If the System Center Operations Console is open you will need to close the application and then restart it; if you do not do this the **Reporting** tab will not appear in the Operations Console user interface.</span></span> <span data-ttu-id="94326-219">请注意，第一次重新启动操作控制台之后，可能需要几分钟的时间，" **报告** " 选项卡上才会显示所有监控报告。</span><span class="sxs-lookup"><span data-stu-id="94326-219">Note that, after restarting the Operations Console the first time, it could take several minutes before all the Monitoring Reports appear on the **Reporting** tab.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

