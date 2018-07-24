---
title: 为业务服务器在 Skype 安装监控报告
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6f417569-b100-442c-ad48-fdd794626cf7
description: 摘要： 了解如何安装将监控报告中生成 Skype 业务服务器服务。
ms.openlocfilehash: 51d7e452be546c41daacbb0a0a77c142bace6e31
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "21016596"
---
# <a name="install-monitoring-reports-in-skype-for-business-server"></a>为业务服务器在 Skype 安装监控报告
 
**摘要：** 了解如何安装将监控报告中生成 Skype 业务服务器服务。
  
Skype 业务服务器监控报告为您提供了大量有关组织中进行通信会话的数量和质量的信息。 
  
## <a name="install-monitoring-reports"></a>安装监控报告

未为业务服务器; 安装 Skype 时自动安装监控报告相反，您必须单独安装监控报告，并在计算机上安装了仅后的 Skype 业务服务器。
  
> [!NOTE]
> 建议您在安装监控数据库的同一台计算机上安装监控报告。这可简化分配用于访问报告的权限的过程：在承载监控存储的计算机上安装监控报告意味着，您无需配置允许一台计算机上的数据库与另一台计算机上正在运行的 Reporting Services 进行交互的权限。 
  
Skype 业务服务器监控报告包括 30 报告旨在提供有关会议、 对等 IM 会话、 用户注册、 响应组应用程序，和更多详细的信息。 2013 版本中，业务服务器监控报告的 Skype 包括大量的增强功能：
  
- **新增了语音质量报告**。 这些新报表包括[媒体质量比较报告中的业务服务器 Skype](../../manage/health-and-monitoring/comparison.md)，它比较不同类型的呼叫 （例如，之间有线的呼叫和无线呼叫）; 之间的质量和加入会议的用户需要[Skype 业务服务器中的会议加入时间报告](../../manage/health-and-monitoring/join-time-report.md)，它提供信息的时间量。 
    
- **改进了用于分析视频和应用程序共享会话并对其进行故障排除的报告。** [Media Quality Summary Report 中的业务服务器 Skype](../../manage/health-and-monitoring/summary.md)提供分析视频和应用程序共享呼叫时[Skype 业务服务器中的服务器性能报告](../../manage/health-and-monitoring/server-performance.md)详细信息生成这些服务器的性能的方式呼叫。 通过[对等会话详细信息报告中的业务服务器 Skype](../../manage/health-and-monitoring/peer-to-peer-session-detail-report.md)和[会议详细信息报告中的业务服务器 Skype](../../manage/health-and-monitoring/detail-report.md)现在还报告视频和应用程序共享指标。
    
- **改进了报告性能**。这包括更短的响应和数据检索时间，以及更快且更轻松的报告导航。
    
监控报告文档中提供了有关各个报告的详细信息。
  
> [!NOTE]
> 没有另一报表-QoE 呼叫详细信息子报表-Skype 中包含业务服务器。 但此报告主要供内部使用，且无法直接访问。 
  
有两种方法安装业务服务器监控报告 Skype： 您可用于业务 Server 部署向导的 Skype 或者您可以使用 Windows PowerShell 脚本包含业务服务器安装文件的 Skype。 无论您使用哪种方法安装此报告，都必须先确保：
  
- 具有向监控数据库中的用户帐户添加数据库角色的权限。
    
- 担当 SQL Server Reporting Services 中的内容管理器角色。此角色授予您将报告部署到 SQL Server Reporting Services 的权限。
    
若要使用部署向导安装监控报告，请完成下列步骤：
  
1. 单击**开始**，单击**所有程序**、 都单击**Skype 业务服务器**，，然后都单击**Skype 的业务 Server 部署向导**。
    
2. 在部署向导中，单击“**部署监控报告**”以便启动部署监控报告向导。
    
3. 在部署监控报告向导中的“**指定监控数据库**”页上，确保承载您的监控存储的计算机的完全限定域名显示在“**监控数据库**”下拉列表中。（如果您具有多个监控存储，则需要从该下拉列表中选择适当的服务器。）确认“**SQL Server Reporting Services (SSRS)实例**”框中显示了正确的 SQL Server 实例（例如，“**atl-sql-001.litwareinc.com/archinst**”），然后单击“**下一步**”。
    
4. 在“**指定凭据**”页上的“**用户名**”框中，键入在访问监控报告时要使用的帐户的域名和用户名（例如，“**litwareinc\kenmyer**”）。如果不使用此格式（域\用户名），则将发生错误。
    
    在“**密码**”框中键入用户帐户密码，然后单击“**下一步**”。请注意，此帐户不需要特殊权限。设置完成时，将自动向该帐户授予所需的登录和数据库权限。
    
5. 在“**指定只读组**”页上，输入将为其授予对“用户”分组框中的 SQL Server Reporting Services 的只读访问权的安全组的名称。例如，若要授予对报告的只读管理员访问权，请输入“**RTCUniversalReadOnlyAdmins**”。单击“**下一步**”。
    
6. 在“**正在执行命令**”页上，单击“**完成**”。
    
监控报告还可以安装从 Skype 的业务 Server 命令行管理程序通过运行该脚本 DeployReports.ps1;此 Windows PowerShell 脚本可以中找到\<安装位置\>\Skype 业务 Server 2015\Deployment\Setup 文件夹。 要使用 DeployReports.ps1 安装监控报告，请在命令行管理程序提示符处键入与以下内容类似的命令：
  
```
C:\Program Files\Skype for Business Server 2015\Deployment\Setup\DeployReports.ps1 -storedUserName "litwareinc\kenmyer" -storedPassword "p@ssw0rd" -readOnlyGroupName "RTCUniversalReadOnlyAdmins" -reportServerSqlInstance "atl-sql-001.litwareinc.com" -monitoringDatabaseId "MonitoringDatabase:atl-sql-001.litwareinc.com"
```

上面的命令中使用的参数如下表所示：
  
|**参数名称**|**必需**|**说明**|
|:-----|:-----|:-----|
|storedUserName  <br/> |是  <br/> |用于访问监控存储的用户帐户（格式为 domain\username）；例如：  <br/> ```-storedUserName "litwareinc\kenmyer"```此帐户必须具有之前指定的 SQL Server 和 SQL Server Reporting Services 权限，否则脚本将失败。  <br/> |
|storedPassword  <br/> |是  <br/> |用于访问监控存储的用户帐户的密码。  <br/> |
|readOnlyGroupName  <br/> |否  <br/> |将向其成员授予对监控报告的只读访问权的域或本地安全组。请注意，如果指定的组不存在，该脚本将失败。如果您稍后决定撤消这些权限，或决定向其他用户或其他组授予访问权限，则可使用 SQL Service Reporting Services 报告管理器完成此操作。  <br/> |
|reportSqlServerInstance  <br/> |否  <br/> |承载 Reporting Service 的 SQL Server 实例。必须使用报告服务器的完全限定域名来指定报告实例；例如：<br/> ```-reportServerSqlInstance atl-sql-001.litwareinc.com```如果不加入此参数，则该脚本将假定 reporting services 所承载的承载监控数据库的同一 SQL Server 实例。  <br/> |
|monitoringDatabaseId  <br/> |否  <br/> |监控数据库的服务标识。可以通过运行此命令返回监控数据库的标识：<br/> ```Get-CsService -MonitoringDatabase```|
   
安装监控报告之后，你必须使用 New-CsReportingConfiguration 配置用于访问这些报告的 URL。 此任务可以执行从 Skype 的业务 Server 命令行管理程序通过运行以下 Windows PowerShell 命令。 请注意，建议（但不要求）你在配置报告 URL 时使用 HTTPS 协议：
  
```
New-CsReportingConfiguration -Identity 'service:MonitoringDatabase:atl-sql-001.litwareinc.com' -ReportingURL 'https://atl-sql-001.litwareinc.com:443/Reports_ARCHINST'
```

在上面的命令中，ReportingUrl 属性应设置为 SQL Server 2008 R2 Reporting Services 所使用的报告管理器 URL。可以通过在已安装 SQL Server Reporting Services 的计算机上完成以下步骤来确定报告管理器 URL：
  
1. 依次单击“开始”、“所有程序”、“Microsoft SQL Server 2008 R2”、“配置工具”和“Reporting Services 配置管理器”。
    
2. 在“Reporting Services 配置连接”对话框中，确保“服务器名称”框中显示 Reporting Services 计算机的名称。从“报告服务器实例”下拉列表中选择 SQL Server 实例，然后单击“连接”。
    
3. 在“Reporting Services 配置管理器”中，单击“报告管理器 URL”。“报告管理器 URL”窗格中应显示一个或多个 URL。虽然可将其中的任一 URL 用作报告 URL，但再次建议 ReportingUrl 使用 HTTPS 协议。
    
如果已为您的监控数据库设置镜像数据库，您也必须将监控报告与镜像数据库相关联。 请参阅文章[关联的镜像数据库中的业务服务器 Skype 监控报告](monitoring-reports-with-a-mirror-database.md)的详细信息。
  

