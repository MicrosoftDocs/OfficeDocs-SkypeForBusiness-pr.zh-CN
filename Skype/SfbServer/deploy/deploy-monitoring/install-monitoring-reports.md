---
title: 安装监控报告Skype for Business Server
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
ms.assetid: 6f417569-b100-442c-ad48-fdd794626cf7
description: 摘要：了解如何安装将在 Skype for Business Server 中生成监控Skype for Business Server。
ms.openlocfilehash: b97dbf30f5077caa5d7fa17850bb9e6bcad6fd016986cae2626ec7083552c874
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54298552"
---
# <a name="install-monitoring-reports-in-skype-for-business-server"></a>安装监控报告Skype for Business Server
 
**摘要：** 了解如何安装将生成监控报告的服务Skype for Business Server。
  
Skype for Business Server监控报告为您提供了大量有关组织中发生通信会话的质量和数量的信息。 
  
## <a name="install-monitoring-reports"></a>安装监控报告

安装监控报告时不会自动安装监控Skype for Business Server;相反，必须单独安装监控报告，并且Skype for Business Server安装监控报告之后。
  
> [!NOTE]
> 建议您在安装监控数据库的同一台计算机上安装监控报告。这可简化分配用于访问报告的权限的过程：在承载监控存储的计算机上安装监控报告意味着，您无需配置允许一台计算机上的数据库与另一台计算机上正在运行的 Reporting Services 进行交互的权限。 
  
Skype for Business Server监控报告包括 30 多个报告，旨在提供有关会议、对等 IM 会话、用户注册、响应组应用程序等的详细信息。 对于 2013 版本，Skype for Business Server监控报告包括许多增强功能：
  
- **新增了语音质量报告**。 这些新报告包括[Skype for Business Server](../../manage/health-and-monitoring/comparison.md)中的媒体质量比较报告，该报告比较不同类型的呼叫的质量 (例如有线呼叫和无线呼叫与) ;和[Skype for Business Server](../../manage/health-and-monitoring/join-time-report.md)中的会议加入时间报告，其中提供了有关用户加入会议所需的时间的信息。 
    
- **改进了用于分析视频和应用程序共享会话并对其进行故障排除的报告。** Skype for Business Server [](../../manage/health-and-monitoring/summary.md)中的媒体质量摘要报告提供了一种分析视频和应用程序共享呼叫的方法，而 Skype for Business Server 中的服务器性能[](../../manage/health-and-monitoring/server-performance.md)报告详细介绍了生成这些调用的服务器的性能。 视频和应用程序共享指标现在也由 Skype for Business Server 中的对等[](../../manage/health-and-monitoring/peer-to-peer-session-detail-report.md)会话详细信息报告以及 Skype for Business Server 中的会议详细信息[报告报告](../../manage/health-and-monitoring/detail-report.md)。
    
- **改进了报告性能**。这包括更少的响应和数据检索时间，以及更快且更轻松的报告导航。
    
监控报告文档中提供了有关各个报告的详细信息。
  
> [!NOTE]
> 还有另一个报告 QoE 呼叫详细信息子报告包含在Skype for Business Server。 但此报告主要供内部使用，且无法直接访问。 
  
可通过两种方法Skype for Business Server监控报告：可以使用 Skype for Business Server 部署向导，或使用 Windows PowerShell 安装文件中包含的 Skype for Business Server 脚本。 无论您使用哪种方法安装此报告，都必须先确保：
  
- 具有向监控数据库中的用户帐户添加数据库角色的权限。
    
- 担当 SQL Server Reporting Services 中的内容管理器角色。此角色授予您将报告部署到 SQL Server Reporting Services 的权限。
    
若要使用部署向导安装监控报告，请完成下列步骤：
  
1. 单击 **"开始**"，**单击"** 所有程序"，Skype for Business Server"，然后单击"Skype for Business Server **部署向导"。** 
    
2. 在部署向导中，单击“部署监控报告”以便启动部署监控报告向导。
    
3. 在部署监控报告向导中的“指定监控数据库”页上，确保承载您的监控存储的计算机的完全限定域名显示在“监控数据库”下拉列表中。（如果您具有多个监控存储，则需要从该下拉列表中选择适当的服务器。）确认“SQL Server Reporting Services (SSRS)实例”框中显示了正确的 SQL Server 实例（例如，“atl-sql-001.litwareinc.com/archinst”），然后单击“下一步”。
    
4. 在“指定凭据”页上的“用户名”框中，键入在访问监控报告时要使用的帐户的域名和用户名（例如，“litwareinc\kenmyer”）。 如果不使用此格式， (域名\用户名) 将发生错误。
    
    在“密码”框中键入用户帐户密码，然后单击“下一步”。 请注意，此帐户不需要任何特殊权限。 安装完成后，将自动向该帐户授予所需的登录和数据库权限。
    
5. 在“指定只读组”页上，输入将为其授予对“用户”分组框中的 SQL Server Reporting Services 的只读访问权的安全组的名称。例如，若要授予对报告的只读管理员访问权，请输入“RTCUniversalReadOnlyAdmins”。单击“下一步”。
    
6. 在“正在执行命令”页上，单击“完成”。
    
通过运行脚本命令行管理程序，Skype for Business Server命令行管理程序安装监控DeployReports.ps1;此Windows PowerShell脚本位于 \<install location\> \Skype for Business Server 2015\Deployment\Setup 文件夹中。 若要使用 DeployReports.ps1 安装监控报告，请在命令行管理程序提示符处键入与以下内容类似的命令：
  
```powershell
C:\Program Files\Skype for Business Server 2015\Deployment\Setup\DeployReports.ps1 -storedUserName "litwareinc\kenmyer" -storedPassword "p@ssw0rd" -readOnlyGroupName "RTCUniversalReadOnlyAdmins" -reportServerSqlInstance "atl-sql-001.litwareinc.com" -monitoringDatabaseId "MonitoringDatabase:atl-sql-001.litwareinc.com"
```

上面的命令中使用的参数如下表所示：
  
|**参数名**|**必需**|**描述**|
|:-----|:-----|:-----|
|storedUserName  <br/> |是  <br/> |用于访问监控存储的用户帐户（格式为 domain\username）；例如：  <br/> ```-storedUserName "litwareinc\kenmyer"```此帐户必须具有以前指定的SQL Server SQL Server Reporting Services，否则脚本将失败。  <br/> |
|storedPassword  <br/> |是  <br/> |用于访问监控存储的用户帐户的密码。  <br/> |
|readOnlyGroupName  <br/> |否  <br/> |将向其成员授予对监控报告的只读访问权的域或本地安全组。 请注意，如果指定的组不存在，该脚本将失败。 如果您稍后决定撤消这些权限，或决定向其他用户或其他组授予访问权限，则可使用 SQL Service Reporting Services 报告管理器完成此操作。  <br/> |
|reportSqlServerInstance  <br/> |否  <br/> |承载 Reporting Service 的 SQL Server 实例。必须使用报告服务器的完全限定域名来指定报告实例；例如：<br/> ```-reportServerSqlInstance atl-sql-001.litwareinc.com```如果未包括此参数，脚本将假定报告服务由承载监控数据库的同一SQL Server实例承载。  <br/> |
|monitoringDatabaseId  <br/> |否  <br/> |监控数据库的服务标识。可以通过运行此命令返回监控数据库的标识：<br/> ```Get-CsService -MonitoringDatabase```|
   
安装监控报告后，必须使用 New-CsReportingConfiguration cmdlet 配置用于访问这些报告的 URL。 可以通过运行以下命令行管理程序Skype for Business Server命令行管理程序执行Windows PowerShell任务。 请注意，建议（但不要求）您在配置报告 URL 时使用 HTTPS 协议：
  
```powershell
New-CsReportingConfiguration -Identity 'service:MonitoringDatabase:atl-sql-001.litwareinc.com' -ReportingURL 'https://atl-sql-001.litwareinc.com:443/Reports_ARCHINST'
```

在上面的命令中，ReportingUrl 属性应设置为 SQL Server 2008 R2 Reporting Services 所使用的报告管理器 URL。可以通过在已安装 SQL Server Reporting Services 的计算机上完成以下步骤来确定报告管理器 URL：
  
1. 依次单击“开始”、“所有程序”、“Microsoft SQL Server 2008 R2”、“配置工具”和“Reporting Services 配置管理器”。
    
2. 在“Reporting Services 配置连接”对话框中，确保“服务器名称”框中显示 Reporting Services 计算机的名称。从“报告服务器实例”下拉列表中选择 SQL Server 实例，然后单击“连接”。
    
3. 在“Reporting Services 配置管理器”中，单击“报告管理器 URL”。“报告管理器 URL”窗格中应显示一个或多个 URL。虽然可将其中的任一 URL 用作报告 URL，但再次建议 ReportingUrl 使用 HTTPS 协议。
    
如果为监控数据库设置了镜像数据库，则还必须将监控报告与镜像数据库关联。 有关详细信息，请参阅[文章 Associate Monitoring Reports with a mirror database in Skype for Business Server](monitoring-reports-with-a-mirror-database.md) in Skype for Business Server。
  

