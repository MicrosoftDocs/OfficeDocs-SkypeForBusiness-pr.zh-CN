---
title: 安装 Lync Server 2013 监控报告
TOCTitle: 安装 Lync Server 2013 监控报告
ms:assetid: 6f417569-b100-442c-ad48-fdd794626cf7
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204989(v=OCS.15)
ms:contentKeyID: 49313192
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 安装 Lync Server 2013 监控报告

 

_**上一次修改主题：** 2015-03-09_

Microsoft Lync Server 2013 监控报告将为您提供大量有关您组织中进行的通信会话的质量和数量的信息。但是，在安装 Lync Server 2013 时不会自动安装监控报告；相反，您必须在计算机上安装 Lync Server 之后单独安装监控报告。

> [!NOTE]  
> 建议您在安装监控数据库的同一台计算机上安装监控报告。这可简化分配用于访问报告的权限的过程：在承载监控存储的计算机上安装监控报告意味着，您无需配置允许一台计算机上的数据库与另一台计算机上正在运行的 Reporting Services 进行交互的权限。



Lync Server 监控报告包含 30 多种报告，这些报告旨在提供有关会议、点对点 IM 会话、用户注册、响应组应用程序等内容的详细信息。在 2013 版本中，Lync Server 监控报告包括许多增强功能：

  - **新增了语音质量报告**。这些新的报告包括[媒体质量比较报告](lync-server-2013-media-quality-comparison-report.md)和[会议加入时间报告](lync-server-2013-conference-join-time-report.md)，前者将比较不同类型的呼叫（如有线呼叫和无线呼叫）的质量，后者将提供有关用户加入会议所需的时间的信息。

  - **改进了用于分析视频和应用程序共享会话并对其进行故障排除的报告。** 可利用[Lync Server 2013 中的媒体质量摘要报告](lync-server-2013-media-quality-summary-report.md)分析视频和应用程序共享呼叫，而[Lync Server 2013 中的服务器性能报告](lync-server-2013-server-performance-report.md)详细介绍了生成这些呼叫的服务器的性能。此外，现在将通过[Lync Server 2013 中的点对点会话详细信息报告](lync-server-2013-peer-to-peer-session-detail-report.md)和[会议详细信息报告](lync-server-2013-conference-detail-report.md)来报告视频和应用程序共享指标。

  - **改进了报告性能**。这包括更少的响应和数据检索时间，以及更快且更轻松的报告导航。

监控报告文档中提供了有关各个报告的详细信息。

> [!NOTE]  
> Lync Server 2013 中还包括了一个新报告，即 QoE 呼叫详细信息子报告。但此报告主要供内部使用，且无法直接访问。



可通过两种方法安装 Lync Server 监控报告：使用 Lync Server 部署向导或使用 Lync Server 2013 安装文件附带的 Windows PowerShell 脚本。无论您使用哪种方法安装此报告，都必须先确保：

  - 具有向监控数据库中的用户帐户添加数据库角色的权限。

  - 担当 SQL Server Reporting Services 中的内容管理器角色。此角色授予您将报告部署到 SQL Server Reporting Services 的权限。

若要使用部署向导安装监控报告，请完成下列步骤：

1.  依次单击“开始”、“所有程序”、“Microsoft Lync Server 2013”和“Lync Server 部署向导”。

2.  在部署向导中，单击“部署监控报告”以便启动部署监控报告向导。

3.  在部署监控报告向导中的“指定监控数据库”页上，确保承载您的监控存储的计算机的完全限定域名显示在“监控数据库”下拉列表中。（如果您具有多个监控存储，则需要从该下拉列表中选择适当的服务器。）确认“SQL Server Reporting Services (SSRS)实例”框中显示了正确的 SQL Server 实例（例如，“atl-sql-001.litwareinc.com/archinst”），然后单击“下一步”。

4.  在“指定凭据”页上的“用户名”框中，键入在访问监控报告时要使用的帐户的域名和用户名（例如，“litwareinc\\kenmyer”）。如果不使用此格式（域\\用户名），则将发生错误。
    
    在“密码”框中键入用户帐户密码，然后单击“下一步”。请注意，此帐户不需要特殊权限。设置完成时，将自动向该帐户授予所需的登录和数据库权限。

5.  在“指定只读组”页上，输入将为其授予对“用户”分组框中的 SQL Server Reporting Services 的只读访问权的安全组的名称。例如，若要授予对报告的只读管理员访问权，请输入“RTCUniversalReadOnlyAdmins”。单击“下一步”。

6.  在“正在执行命令”页上，单击“完成”。

此外，可以通过运行脚本 DeployReports.ps1 从 Lync Server 命令行管理程序安装监控报告；可在 Lync Server 安装介质中的 \\Setup\\ReportingSetup 文件夹中找到此 Windows PowerShell 脚本。要使用 DeployReports.ps1 安装监控报告，请在命令行管理程序提示符处键入与以下内容类似的命令：

    D:\Setup\AMD64\Setp\ReportingSetup\DeployReports.ps1 -storedUserName "litwareinc\kenmyer" -storedPassword "p@ssw0rd" -readOnlyGroupName "RTCUniversalReadOnlyAdmins" -reportServerSqlInstance "atl-sql-001.litwareinc.com" -monitoringDatabaseId "MonitoringDatabase:atl-sql-001.litwareinc.com"

上面的命令中使用的参数如下表所示：


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>参数名称</th>
<th>是否必需</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>storedUserName</p></td>
<td><p>是</p></td>
<td><p>用于访问监控存储的用户帐户（格式为 domain\username）；例如：</p>
<pre><code>-storedUserName &quot;litwareinc\kenmyer&quot;</code></pre>
<p>此帐户必须具有之前指定的 SQL Server 和 SQL Server Reporting Services 权限，否则脚本将失败。</p></td>
</tr>
<tr class="even">
<td><p>storedPassword</p></td>
<td><p>是</p></td>
<td><p>用于访问监控存储的用户帐户的密码。</p></td>
</tr>
<tr class="odd">
<td><p>readOnlyGroupName</p></td>
<td><p>否</p></td>
<td><p>将向其成员授予对监控报告的只读访问权的域或本地安全组。请注意，如果指定的组不存在，该脚本将失败。如果您稍后决定撤消这些权限，或决定向其他用户或其他组授予访问权限，则可使用 SQL Service Reporting Services 报告管理器完成此操作。</p></td>
</tr>
<tr class="even">
<td><p>reportSqlServerInstance</p></td>
<td><p>否</p></td>
<td><p>承载 Reporting Service 的 SQL Server 实例。必须使用报告服务器的完全限定域名来指定报告实例；例如：</p>
<pre><code>-reportServerSqlInstance atl-sql-001.litwareinc.com</code></pre>
<p>如果脚本中未包含此参数，则假定 Reporting Services 由承载监控数据库的同一 SQL Server 实例承载。</p></td>
</tr>
<tr class="odd">
<td><p>monitoringDatabaseId</p></td>
<td><p>否</p></td>
<td><p>监控数据库的服务标识。可以通过运行此命令返回监控数据库的标识：</p>
<pre><code>Get-CsService -MonitoringDatabase</code></pre></td>
</tr>
</tbody>
</table>


安装监控报告之后，您必须使用 Set-CsReportingConfiguration cmdlet 配置用于访问这些报告的 URL。可通过运行以下 Windows PowerShell 命令从 Lync Server 命令行管理程序执行此任务。请注意，建议（但不要求）您在配置报告 URL 时使用 HTTPS 协议：

    Set-CsReportingConfiguration -Identity "MonitoringDatabase:atl-sql-001.litwareinc.com" -ReportingURL "https://atl-sql-001.litwareinc.com:443/Reports_ARCHINST"

在上面的命令中，ReportingUrl 属性应设置为 SQL Server 2008 R2 Reporting Services 所使用的报告管理器 URL。可以通过在已安装 SQL Server Reporting Services 的计算机上完成以下步骤来确定报告管理器 URL：

1.  依次单击“开始”、“所有程序”、“Microsoft SQL Server 2008 R2”、“配置工具”和“Reporting Services 配置管理器”。

2.  在“Reporting Services 配置连接”对话框中，确保“服务器名称”框中显示 Reporting Services 计算机的名称。从“报告服务器实例”下拉列表中选择 SQL Server 实例，然后单击“连接”。

3.  在“Reporting Services 配置管理器”中，单击“报告管理器 URL”。“报告管理器 URL”窗格中应显示一个或多个 URL。虽然可将其中的任一 URL 用作报告 URL，但再次建议 ReportingUrl 使用 HTTPS 协议。

如果已为您的监控数据库设置镜像数据库，您也必须将监控报告与镜像数据库相关联。有关详细信息，请参阅[将监控报告与镜像数据库相关联](lync-server-2013-associating-monitoring-reports-with-a-mirror-database.md)一文。

