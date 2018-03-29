---
title: 在 Skype for Business Server 2015 中安装监视报告
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 7/21/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6f417569-b100-442c-ad48-fdd794626cf7
description: 摘要： 了解如何安装的服务，将生成监视报告在 Skype 业务服务器 2015年。
ms.openlocfilehash: cfb07f7e36f798e394c7a66bfcd5f2cab018377a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="install-monitoring-reports-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中安装监视报告
 
**摘要：**了解如何安装的服务，将生成监视报告在 Skype 业务服务器 2015年。
  
Skype 的业务服务器 2015年监视报告提供了大量的信息在您的组织进行的通信会话的数量和质量。 
  
## <a name="install-monitoring-reports"></a>安装监控报告

没有业务服务器 2015; 安装 Skype 时自动安装监视报告相反，您必须单独安装监视报告并仅在 Skype 业务服务器已安装在计算机上。
  
> [!NOTE]
> 建议您在安装监控数据库的同一台计算机上安装监控报告。这可简化分配用于访问报告的权限的过程：在承载监控存储的计算机上安装监控报告意味着，您无需配置允许一台计算机上的数据库与另一台计算机上正在运行的 Reporting Services 进行交互的权限。 
  
Skype 的业务服务器监视报告包括 30 多个旨在提供关于会议、 对等 IM 会话、 用户注册、 响应组的应用程序，以及更多详细的信息的报表。 对于 2013年版中，Skype 的业务服务器监视报告包括了许多增强功能：
  
- **新增了语音质量报告**。 这些新的报告将包括[媒体质量比较报表中的业务服务器 2015年的 Skype](../../manage/health-and-monitoring/comparison.md)，比较了不同类型的调用 （例如，之间调用有线和无线呼叫）; 之间的质量并为用户加入会议要求[业务服务器 2015年的 Skype 会议加入时间报表](../../manage/health-and-monitoring/join-time-report.md)，其中提供关于一段时间。 
    
- **改进了用于分析视频和应用程序共享会话并对其进行故障排除的报告。** [媒体质量摘要报表中的业务服务器 2015 Skype](../../manage/health-and-monitoring/summary.md)提供一种方法来分析视频和应用程序共享的调用，而[在业务服务器 2015年的 Skype 的服务器性能报告](../../manage/health-and-monitoring/server-performance.md)详细介绍了服务器的性能生成这些调用。 通过[Skype 的业务服务器 2015年中的对等会话详细信息报告](../../manage/health-and-monitoring/peer-to-peer-session-detail-report.md)和[会议详细信息报表中的业务服务器 2015 Skype](../../manage/health-and-monitoring/detail-report.md)现在还报告视频和应用程序共享的指标。
    
- **改进了报告性能**。这包括更短的响应和数据检索时间，以及更快且更轻松的报告导航。
    
监控报告文档中提供了有关各个报告的详细信息。
  
> [!NOTE]
> 还有另一个报表的 QoE 呼叫细节子-包含在 Skype 业务服务器 2015年个。 但此报告主要供内部使用，且无法直接访问。 
  
有两种方法来安装 Skype 业务服务器监视报告： 您可以为业务服务器部署向导使用 Skype 或您可以使用 Windows PowerShell 脚本附带业务服务器 2015年安装文件的 Skype。 无论您使用哪种方法安装此报告，都必须先确保：
  
- 具有向监控数据库中的用户帐户添加数据库角色的权限。
    
- 担当 SQL Server Reporting Services 中的内容管理器角色。此角色授予您将报告部署到 SQL Server Reporting Services 的权限。
    
若要使用部署向导安装监控报告，请完成下列步骤：
  
1. 单击**开始**，单击**所有程序**， **Skype 业务服务器**，请都单击，然后都单击**Skype 业务服务器部署向导**。
    
2. 在部署向导中，单击“**部署监控报告**”以便启动部署监控报告向导。
    
3. 在部署监控报告向导中的“**指定监控数据库**”页上，确保承载您的监控存储的计算机的完全限定域名显示在“**监控数据库**”下拉列表中。（如果您具有多个监控存储，则需要从该下拉列表中选择适当的服务器。）确认“**SQL Server Reporting Services (SSRS)实例**”框中显示了正确的 SQL Server 实例（例如，“**atl-sql-001.litwareinc.com/archinst**”），然后单击“**下一步**”。
    
4. 在“**指定凭据**”页上的“**用户名**”框中，键入在访问监控报告时要使用的帐户的域名和用户名（例如，“**litwareinc\kenmyer**”）。如果不使用此格式（域\用户名），则将发生错误。
    
    在“**密码**”框中键入用户帐户密码，然后单击“**下一步**”。请注意，此帐户不需要特殊权限。设置完成时，将自动向该帐户授予所需的登录和数据库权限。
    
5. 在“**指定只读组**”页上，输入将为其授予对“用户”分组框中的 SQL Server Reporting Services 的只读访问权的安全组的名称。例如，若要授予对报告的只读管理员访问权，请输入“**RTCUniversalReadOnlyAdmins**”。单击“**下一步**”。
    
6. 在“**正在执行命令**”页上，单击“**完成**”。
    
监控报告也可以安装从 Skype 的业务服务器管理外壳程序通过运行脚本 DeployReports.ps1;在中找不到此 Windows PowerShell 脚本\<安装位置的\>\Skype 业务服务器 2015\Deployment\Setup 文件夹。 要使用 DeployReports.ps1 安装监控报告，请在命令行管理程序提示符处键入与以下内容类似的命令：
  
```
C:\Program Files\Skype for Business Server 2015\Deployment\Setup\DeployReports.ps1 -storedUserName "litwareinc\kenmyer" -storedPassword "p@ssw0rd" -readOnlyGroupName "RTCUniversalReadOnlyAdmins" -reportServerSqlInstance "atl-sql-001.litwareinc.com" -monitoringDatabaseId "MonitoringDatabase:atl-sql-001.litwareinc.com"
```

上面的命令中使用的参数如下表所示：
  
|**参数名称**|**必填**|**说明**|
|:-----|:-----|:-----|
|storedUserName  <br/> |是  <br/> |用于访问监控存储的用户帐户（格式为 domain\username）；例如：  <br/> ```-storedUserName "litwareinc\kenmyer"```该帐户必须具有以前指定的 SQL Server 和 SQL Server 报表服务权限或脚本将失败。  <br/> |
|storedPassword  <br/> |是  <br/> |用于访问监控存储的用户帐户的密码。  <br/> |
|readOnlyGroupName  <br/> |否  <br/> |将向其成员授予对监控报告的只读访问权的域或本地安全组。请注意，如果指定的组不存在，该脚本将失败。如果您稍后决定撤消这些权限，或决定向其他用户或其他组授予访问权限，则可使用 SQL Service Reporting Services 报告管理器完成此操作。  <br/> |
|reportSqlServerInstance  <br/> |否  <br/> |承载 Reporting Service 的 SQL Server 实例。必须使用报告服务器的完全限定域名来指定报告实例；例如：<br/> ```-reportServerSqlInstance atl-sql-001.litwareinc.com```如果此参数不包含脚本将假定报告服务由主机监视数据库的同一个 SQL Server 实例。  <br/> |
|monitoringDatabaseId  <br/> |否  <br/> |监控数据库的服务标识。可以通过运行此命令返回监控数据库的标识：<br/> ```Get-CsService -MonitoringDatabase```|
   
安装监控报告之后，你必须使用 New-CsReportingConfiguration 配置用于访问这些报告的 URL。 此任务可以执行从 Skype 的业务服务器管理外壳程序通过运行下面的 Windows PowerShell 命令。 请注意，建议（但不要求）你在配置报告 URL 时使用 HTTPS 协议：
  
```
New-CsReportingConfiguration -Identity 'service:MonitoringDatabase:atl-sql-001.litwareinc.com' -ReportingURL 'https://atl-sql-001.litwareinc.com:443/Reports_ARCHINST'
```

在上面的命令中，ReportingUrl 属性应设置为 SQL Server 2008 R2 Reporting Services 所使用的报告管理器 URL。可以通过在已安装 SQL Server Reporting Services 的计算机上完成以下步骤来确定报告管理器 URL：
  
1. 依次单击“开始”、“所有程序”、“Microsoft SQL Server 2008 R2”、“配置工具”和“Reporting Services 配置管理器”。
    
2. 在“Reporting Services 配置连接”对话框中，确保“服务器名称”框中显示 Reporting Services 计算机的名称。从“报告服务器实例”下拉列表中选择 SQL Server 实例，然后单击“连接”。
    
3. 在“Reporting Services 配置管理器”中，单击“报告管理器 URL”。“报告管理器 URL”窗格中应显示一个或多个 URL。虽然可将其中的任一 URL 用作报告 URL，但再次建议 ReportingUrl 使用 HTTPS 协议。
    
如果已为您的监控数据库设置镜像数据库，您也必须将监控报告与镜像数据库相关联。 文章[关联的业务服务器 2015年的 Skype 在镜像数据库监控报表](monitoring-reports-with-a-mirror-database.md)的详细信息，请参阅。
  

