---
title: Lync Server 2013：安装 Lync Server 2013 监视报告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing Lync Server 2013 Monitoring Reports
ms:assetid: 6f417569-b100-442c-ad48-fdd794626cf7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204989(v=OCS.15)
ms:contentKeyID: 48184445
ms.date: 02/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b6b5f9832ddc10d3cea46d09aee6b047595db0f7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726141"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-lync-server-2013-monitoring-reports"></a><span data-ttu-id="58565-102">安装 Lync Server 2013 监视报告</span><span class="sxs-lookup"><span data-stu-id="58565-102">Installing Lync Server 2013 Monitoring Reports</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="58565-103">_**主题上次修改时间：** 2015-02-27_</span><span class="sxs-lookup"><span data-stu-id="58565-103">_**Topic Last Modified:** 2015-02-27_</span></span>

<span data-ttu-id="58565-104">Microsoft Lync Server 2013 监视报告为你提供了有关组织中发生的通信会话的质量和数量的大量信息。</span><span class="sxs-lookup"><span data-stu-id="58565-104">Microsoft Lync Server 2013 Monitoring Reports provide you with a wealth of information about the quality and quantity of the communication sessions that take place in your organization.</span></span> <span data-ttu-id="58565-105">但是，安装 Lync Server 2013 时不会自动安装监视报告;而是必须单独安装监视报告，并且仅在计算机上安装了 Lync Server 后才进行安装。</span><span class="sxs-lookup"><span data-stu-id="58565-105">However, Monitoring Reports are not automatically installed when you install Lync Server 2013; instead, you must install Monitoring Reports separately, and only after Lync Server has been installed on the computer.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="58565-p102">建议您在安装监控数据库的同一台计算机上安装监控报告。这可简化分配用于访问报告的权限的过程：在承载监控存储的计算机上安装监控报告意味着，您无需配置允许一台计算机上的数据库与另一台计算机上正在运行的 Reporting Services 进行交互的权限。</span><span class="sxs-lookup"><span data-stu-id="58565-p102">It is recommended that you install Monitoring Reports on the same computer where the monitoring database is installed. This simplifies the process of assigning permissions for accessing the reports: installing Monitoring Reports on the computer that hosts the monitoring store means that you will not have to configure permissions that allow a database on one computer to interact with Reporting Services running on a second computer.</span></span>



</div>

<span data-ttu-id="58565-108">Lync Server 监视报告包括30多个报告，旨在提供有关会议、对等 IM 会话、用户注册、响应组应用程序等详细信息。</span><span class="sxs-lookup"><span data-stu-id="58565-108">Lync Server Monitoring Reports include over 30 reports designed to provide detailed information about conferences, peer-to-peer IM sessions, user registrations, the Response Group application, and much more.</span></span> <span data-ttu-id="58565-109">对于2013版本，Lync Server Monitoring 报表包含许多增强功能：</span><span class="sxs-lookup"><span data-stu-id="58565-109">For the 2013 version, Lync Server Monitoring Reports include a number of enhancements:</span></span>

  - <span data-ttu-id="58565-110">**新增了语音质量报告**。</span><span class="sxs-lookup"><span data-stu-id="58565-110">**New voice quality reports**.</span></span> <span data-ttu-id="58565-111">这些新报表包括[Lync Server 2013 中的 "媒体质量比较" 报告](lync-server-2013-media-quality-comparison-report.md)，该报告比较不同类型的呼叫（例如，有线呼叫和无线呼叫之间）的质量。[Lync Server 2013 中的 "会议加入时间" 报表](lync-server-2013-conference-join-time-report.md)，提供有关需要用户加入会议的时间量的信息。</span><span class="sxs-lookup"><span data-stu-id="58565-111">These new reports include the [Media Quality Comparison Report in Lync Server 2013](lync-server-2013-media-quality-comparison-report.md), which compares quality between different types of calls (for example, between wired calls and wireless calls); and the [Conference Join Time Report in Lync Server 2013](lync-server-2013-conference-join-time-report.md), which provides information regarding the amount of time requires for users to join a conference.</span></span>

  - <span data-ttu-id="58565-112">**改进了用于分析视频和应用程序共享会话并对其进行故障排除的报告。**</span><span class="sxs-lookup"><span data-stu-id="58565-112">**Improved reports for analyzing and troubleshooting both video and application sharing sessions.**</span></span> <span data-ttu-id="58565-113">[Lync server 2013 中的 "媒体质量摘要" 报表](lync-server-2013-media-quality-summary-report.md)提供了一种方法来分析视频和应用程序共享呼叫，而[lync server 2013 中的服务器性能报告](lync-server-2013-server-performance-report.md)将详细介绍生成这些调用的服务器的性能。</span><span class="sxs-lookup"><span data-stu-id="58565-113">The [Media Quality Summary Report in Lync Server 2013](lync-server-2013-media-quality-summary-report.md) provides a way to analyze video and application sharing calls, while the [Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md) details the performance of servers generating these calls.</span></span> <span data-ttu-id="58565-114">视频和应用程序共享指标现在也由[Lync server 2013 中的 "对等会话详细信息" 报告](lync-server-2013-peer-to-peer-session-detail-report.md)和[lync server 2013 中的 "会议详细信息](lync-server-2013-conference-detail-report.md)" 报告进行报告。</span><span class="sxs-lookup"><span data-stu-id="58565-114">Video and application sharing metrics are also now reported by the [Peer-to-Peer Session Detail Report in Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) and the [Conference Detail Report in Lync Server 2013](lync-server-2013-conference-detail-report.md).</span></span>

  - <span data-ttu-id="58565-p106">**改进了报告性能**。这包括更短的响应和数据检索时间，以及更快且更轻松的报告导航。</span><span class="sxs-lookup"><span data-stu-id="58565-p106">**Improved report performance**. This includes faster response and data retrieval time, as well as faster and easier navigation through the reports.</span></span>

<span data-ttu-id="58565-117">监控报告文档中提供了有关各个报告的详细信息。</span><span class="sxs-lookup"><span data-stu-id="58565-117">More information on the individual reports can be found in the Monitoring Reports documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="58565-118">Lync Server 2013 中包含另一个新报表-QoE 呼叫详细信息子报表。</span><span class="sxs-lookup"><span data-stu-id="58565-118">There is another new report – QoE Call Detail Subreport – included in Lync Server 2013.</span></span> <span data-ttu-id="58565-119">但此报告主要供内部使用，且无法直接访问。</span><span class="sxs-lookup"><span data-stu-id="58565-119">However, this report is primarily for internal use, and is not intended to be directly accessed.</span></span>



</div>

<span data-ttu-id="58565-120">安装 Lync Server 监视报告有两种方法：您可以使用 Lync Server 部署向导，也可以使用 Lync Server 2013 安装文件附带的 Windows PowerShell 脚本。</span><span class="sxs-lookup"><span data-stu-id="58565-120">There are two ways to install Lync Server Monitoring Reports: you can use the Lync Server Deployment Wizard or you can use a Windows PowerShell script included with the Lync Server 2013 installation files.</span></span> <span data-ttu-id="58565-121">无论您使用哪种方法安装此报告，都必须先确保：</span><span class="sxs-lookup"><span data-stu-id="58565-121">Regardless of the method you use to install the reports you must first make sure that you:</span></span>

  - <span data-ttu-id="58565-122">具有向监控数据库中的用户帐户添加数据库角色的权限。</span><span class="sxs-lookup"><span data-stu-id="58565-122">Have the right to add a database role to a user account in the monitoring database.</span></span>

  - <span data-ttu-id="58565-p109">担当 SQL Server Reporting Services 中的内容管理器角色。此角色授予您将报告部署到 SQL Server Reporting Services 的权限。</span><span class="sxs-lookup"><span data-stu-id="58565-p109">Hold the Content Manager role in SQL Server Reporting Services. This role gives you the right to deploy reports to SQL Server Reporting Services.</span></span>

<span data-ttu-id="58565-125">若要使用部署向导安装监控报告，请完成下列步骤：</span><span class="sxs-lookup"><span data-stu-id="58565-125">To install the Monitoring Reports by using the Deployment Wizard, complete the following steps:</span></span>

1.  <span data-ttu-id="58565-126">单击 "**开始**"，单击 "**所有程序**"，单击 " **Microsoft Lync server 2013**"，然后单击 " **Lync server 部署向导**"。</span><span class="sxs-lookup"><span data-stu-id="58565-126">Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Deployment Wizard**.</span></span>

2.  <span data-ttu-id="58565-127">在部署向导中，单击“**部署监控报告**”以便启动部署监控报告向导。</span><span class="sxs-lookup"><span data-stu-id="58565-127">In the Deployment Wizard, click **Deploy Monitoring Reports** in order to start the Deploy Monitoring Reports wizard.</span></span>

3.  <span data-ttu-id="58565-p110">在部署监控报告向导中的“**指定监控数据库**”页上，确保承载您的监控存储的计算机的完全限定域名显示在“**监控数据库**”下拉列表中。（如果您具有多个监控存储，则需要从该下拉列表中选择适当的服务器。）确认“**SQL Server Reporting Services (SSRS)实例**”框中显示了正确的 SQL Server 实例（例如，“**atl-sql-001.litwareinc.com/archinst**”），然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="58565-p110">In the Deploy Monitoring Reports wizard, on the **Specify Monitoring Database** page, make sure that the fully qualified domain name of the computer hosting your monitoring store appears in the **Monitoring database** dropdown list. (If you have multiple monitoring stores you will need to select the appropriate server from the dropdown list.) Verify that the correct SQL Server instance appears in the **SQL Server Reporting Services (SSRS) instance** box (for example, **atl-sql-001.litwareinc.com/archinst**) and then click **Next**.</span></span>

4.  <span data-ttu-id="58565-130">在 "**指定凭据**" 页面上的 "**用户名**" 框中，键入访问监视报告时要使用的帐户的域名和用户名（例如， **\\litwareinc kenmyer**）。</span><span class="sxs-lookup"><span data-stu-id="58565-130">On the **Specify Credentials** page, in the **User name** box, type the domain name and user name of the account to be used when accessing the Monitoring Reports (for example, **litwareinc\\kenmyer**).</span></span> <span data-ttu-id="58565-131">如果不使用此格式（域\\用户名），将出现错误。</span><span class="sxs-lookup"><span data-stu-id="58565-131">If you do not use this format (domain\\user name) an error will occur.</span></span>
    
    <span data-ttu-id="58565-p112">在“**密码**”框中键入用户帐户密码，然后单击“**下一步**”。请注意，此帐户不需要特殊权限。设置完成时，将自动向该帐户授予所需的登录和数据库权限。</span><span class="sxs-lookup"><span data-stu-id="58565-p112">Type the user account password in the **Password** box, and then click **Next**. Note that no special rights are required for this account. The account will automatically be granted the required logon and database permissions when setup completes.</span></span>

5.  <span data-ttu-id="58565-p113">在“**指定只读组**”页上，输入将为其授予对“用户”分组框中的 SQL Server Reporting Services 的只读访问权的安全组的名称。例如，若要授予对报告的只读管理员访问权，请输入“**RTCUniversalReadOnlyAdmins**”。单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="58565-p113">On the **Specify Read-Only Group** page enter the name of a security group that will be granted read-only access to the SQL Server Reporting Services in the User group box. For example, to give read-only administrators access to the reports enter **RTCUniversalReadOnlyAdmins**. Click **Next**.</span></span>

6.  <span data-ttu-id="58565-138">在“**正在执行命令**”页上，单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="58565-138">On the **Executing Commands** page, click **Finish**.</span></span>

<span data-ttu-id="58565-139">通过运行脚本 DeployReports，还可以从 Lync Server Management Shell 安装监控报告。此 Windows PowerShell 脚本可在 Lync Server 安装媒体上的 "设置\\\\ReportingSetup" 文件夹中找到。</span><span class="sxs-lookup"><span data-stu-id="58565-139">Monitoring Reports can also be installed from the Lync Server Management Shell by running the script DeployReports.ps1; this Windows PowerShell script can be found on the Lync Server installation media in the \\Setup\\ReportingSetup folder.</span></span> <span data-ttu-id="58565-140">要使用 DeployReports.ps1 安装监控报告，请在命令行管理程序提示符处键入与以下内容类似的命令：</span><span class="sxs-lookup"><span data-stu-id="58565-140">To install Monitoring Reports using DeployReports.ps1, type a command similar to the following at the Management Shell prompt:</span></span>

    C:\Program Files\Microsoft Lync Server 2013\Deployment\Setup\DeployReports.ps1 -storedUserName "litwareinc\kenmyer" -storedPassword "p@ssw0rd" -readOnlyGroupName "RTCUniversalReadOnlyAdmins" -reportServerSqlInstance "atl-sql-001.litwareinc.com" -monitoringDatabaseId "MonitoringDatabase:atl-sql-001.litwareinc.com"

<span data-ttu-id="58565-141">上面的命令中使用的参数如下表所示：</span><span class="sxs-lookup"><span data-stu-id="58565-141">The parameters used in the preceding command are described in the following table:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="58565-142">参数名称</span><span class="sxs-lookup"><span data-stu-id="58565-142">Parameter Name</span></span></th>
<th><span data-ttu-id="58565-143">是否必需</span><span class="sxs-lookup"><span data-stu-id="58565-143">Required</span></span></th>
<th><span data-ttu-id="58565-144">描述</span><span class="sxs-lookup"><span data-stu-id="58565-144">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="58565-145">storedUserName</span><span class="sxs-lookup"><span data-stu-id="58565-145">storedUserName</span></span></p></td>
<td><p><span data-ttu-id="58565-146">是</span><span class="sxs-lookup"><span data-stu-id="58565-146">Yes</span></span></p></td>
<td><p><span data-ttu-id="58565-147">用于访问监控存储的用户帐户（格式为 domain\username）；例如：</span><span class="sxs-lookup"><span data-stu-id="58565-147">User account (in the format domain\username) used to access the monitoring store; for example:</span></span></p>
<pre><code>-storedUserName &quot;litwareinc\kenmyer&quot;</code></pre>
<p><span data-ttu-id="58565-148">此帐户必须具有之前指定的 SQL Server 和 SQL Server Reporting Services 权限，否则脚本将失败。</span><span class="sxs-lookup"><span data-stu-id="58565-148">This account must have the previously-specified SQL Server and SQL Server Reporting Services permissions or the script will fail.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58565-149">storedPassword</span><span class="sxs-lookup"><span data-stu-id="58565-149">storedPassword</span></span></p></td>
<td><p><span data-ttu-id="58565-150">是</span><span class="sxs-lookup"><span data-stu-id="58565-150">Yes</span></span></p></td>
<td><p><span data-ttu-id="58565-151">用于访问监控存储的用户帐户的密码。</span><span class="sxs-lookup"><span data-stu-id="58565-151">Password for the user account used to access the monitoring store.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58565-152">readOnlyGroupName</span><span class="sxs-lookup"><span data-stu-id="58565-152">readOnlyGroupName</span></span></p></td>
<td><p><span data-ttu-id="58565-153">否</span><span class="sxs-lookup"><span data-stu-id="58565-153">No</span></span></p></td>
<td><p><span data-ttu-id="58565-p115">将向其成员授予对监控报告的只读访问权的域或本地安全组。请注意，如果指定的组不存在，该脚本将失败。如果您稍后决定撤消这些权限，或决定向其他用户或其他组授予访问权限，则可使用 SQL Service Reporting Services 报告管理器完成此操作。</span><span class="sxs-lookup"><span data-stu-id="58565-p115">Domain or local security group whose members will be granted read-only access to the Monitoring Reports. Note that the script will fail if the specified group does not exist. If you later decide to revoke these permissions, or if you decide to grant other users or other groups access permissions, you can do so using the SQL Service Reporting Services Report Manager.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58565-157">reportSqlServerInstance</span><span class="sxs-lookup"><span data-stu-id="58565-157">reportSqlServerInstance</span></span></p></td>
<td><p><span data-ttu-id="58565-158">否</span><span class="sxs-lookup"><span data-stu-id="58565-158">No</span></span></p></td>
<td><p><span data-ttu-id="58565-p116">承载 Reporting Service 的 SQL Server 实例。必须使用报告服务器的完全限定域名来指定报告实例；例如：</span><span class="sxs-lookup"><span data-stu-id="58565-p116">SQL Server instance that hosts the Reporting Service. The Reporting instance must be specified using the fully qualified domain name of the Report Server; for example:</span></span></p>
<pre><code>-reportServerSqlInstance atl-sql-001.litwareinc.com</code></pre>
<p><span data-ttu-id="58565-161">如果脚本中未包含此参数，则假定 Reporting Services 由承载监控数据库的同一 SQL Server 实例承载。</span><span class="sxs-lookup"><span data-stu-id="58565-161">If this parameter is not included the script will assume that the reporting services are hosted by the same SQL Server instance that hosts the monitoring database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58565-162">monitoringDatabaseId</span><span class="sxs-lookup"><span data-stu-id="58565-162">monitoringDatabaseId</span></span></p></td>
<td><p><span data-ttu-id="58565-163">否</span><span class="sxs-lookup"><span data-stu-id="58565-163">No</span></span></p></td>
<td><p><span data-ttu-id="58565-p117">监控数据库的服务标识。可以通过运行此命令返回监控数据库的标识：</span><span class="sxs-lookup"><span data-stu-id="58565-p117">Service Identity for the monitoring database. You can return the Identities for your monitoring databases by running this command:</span></span></p>
<pre><code>Get-CsService -MonitoringDatabase</code></pre></td>
</tr>
</tbody>
</table>


<span data-ttu-id="58565-166">安装监视报告后，必须使用 CsReportingConfiguration cmdlet 配置用于访问这些报表的 URL。</span><span class="sxs-lookup"><span data-stu-id="58565-166">After the Monitoring Reports have been installed you must then use the Set-CsReportingConfiguration cmdlet to configure the URL used to access these reports.</span></span> <span data-ttu-id="58565-167">可通过运行以下 Windows PowerShell 命令，从 Lync Server Management Shell 执行此任务。</span><span class="sxs-lookup"><span data-stu-id="58565-167">This task can be carried out from the Lync Server Management Shell by running the following Windows PowerShell command.</span></span> <span data-ttu-id="58565-168">请注意，建议（但不要求）你在配置报告 URL 时使用 HTTPS 协议：</span><span class="sxs-lookup"><span data-stu-id="58565-168">Note that it is recommended, but not required, that you use the HTTPS protocol when configuring the reporting URL:</span></span>

    Set-CsReportingConfiguration -Identity "MonitoringDatabase:atl-sql-001.litwareinc.com" -ReportingURL "https://atl-sql-001.litwareinc.com:443/Reports_ARCHINST"

<span data-ttu-id="58565-p119">在上面的命令中，ReportingUrl 属性应设置为 SQL Server 2008 R2 Reporting Services 所使用的报告管理器 URL。可以通过在已安装 SQL Server Reporting Services 的计算机上完成以下步骤来确定报告管理器 URL：</span><span class="sxs-lookup"><span data-stu-id="58565-p119">In the preceding command, the ReportingUrl property should be set to the Report Manager URL used by SQL Server 2008 R2 Reporting Services. You can determine the Report Manager URL by completing the following steps on the computer where SQL Server Reporting Services has been installed:</span></span>

1.  <span data-ttu-id="58565-171">依次单击“开始”、“所有程序”、“Microsoft SQL Server 2008 R2”、“配置工具”和“Reporting Services 配置管理器”。</span><span class="sxs-lookup"><span data-stu-id="58565-171">Click Start, click All Programs, click Microsoft SQL Server 2008 R2, click Configuration Tools, and then click Reporting Services Configuration Manager.</span></span>

2.  <span data-ttu-id="58565-p120">在“Reporting Services 配置连接”对话框中，确保“服务器名称”框中显示 Reporting Services 计算机的名称。从“报告服务器实例”下拉列表中选择 SQL Server 实例，然后单击“连接”。</span><span class="sxs-lookup"><span data-stu-id="58565-p120">In the Reporting Services Configuration Connection dialog box, make sure that the name of the Reporting Services computer appears in the Server Name box. Select the SQL Server instance from the Report Server Instance dropdown list and then click Connect.</span></span>

3.  <span data-ttu-id="58565-p121">在“Reporting Services 配置管理器”中，单击“报告管理器 URL”。“报告管理器 URL”窗格中应显示一个或多个 URL。虽然可将其中的任一 URL 用作报告 URL，但再次建议 ReportingUrl 使用 HTTPS 协议。</span><span class="sxs-lookup"><span data-stu-id="58565-p121">In Reporting Services Configuration Manager, click Report Manager URL. One or more URLs should appear in the Report Manager URL pane. Any of these URLs can be used as the Reporting URL although, again, it is recommended that the ReportingUrl use the HTTPS protocol.</span></span>

<span data-ttu-id="58565-177">如果已为您的监控数据库设置镜像数据库，您也必须将监控报告与镜像数据库相关联。</span><span class="sxs-lookup"><span data-stu-id="58565-177">If you have set up a mirror database for your monitoring database then you must also associate the Monitoring Reports with the mirror database.</span></span> <span data-ttu-id="58565-178">有关详细信息，请参阅[在 Lync Server 2013 中将监视报告与镜像数据库相关联](lync-server-2013-associating-monitoring-reports-with-a-mirror-database.md)的文章。</span><span class="sxs-lookup"><span data-stu-id="58565-178">See the article [Associating Monitoring Reports with a mirror database in Lync Server 2013](lync-server-2013-associating-monitoring-reports-with-a-mirror-database.md) for details.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

