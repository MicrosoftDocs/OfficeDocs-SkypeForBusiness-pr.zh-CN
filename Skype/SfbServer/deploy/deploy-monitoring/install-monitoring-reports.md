---
title: 在 Skype for Business 服务器中安装监视报告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6f417569-b100-442c-ad48-fdd794626cf7
description: 摘要：了解如何安装将在 Skype for Business 服务器中生成监视报告的服务。
ms.openlocfilehash: 6c8b7089a66abc3e0b1dcacb4bfa5c840f57ed36
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41789990"
---
# <a name="install-monitoring-reports-in-skype-for-business-server"></a>在 Skype for Business 服务器中安装监视报告
 
**摘要：** 了解如何安装将在 Skype for Business 服务器中生成监视报告的服务。
  
Skype for Business 服务器监视报告可为你提供有关组织中发生的通信会话的质量和数量的大量信息。 
  
## <a name="install-monitoring-reports"></a>安装监控报告

安装 Skype for Business 服务器时不会自动安装监视报告;而是必须单独安装监视报告，并且仅在计算机上安装了 Skype for business 服务器之后。
  
> [!NOTE]
> 建议您在安装监控数据库的同一台计算机上安装监控报告。这可简化分配用于访问报告的权限的过程：在承载监控存储的计算机上安装监控报告意味着，您无需配置允许一台计算机上的数据库与另一台计算机上正在运行的 Reporting Services 进行交互的权限。 
  
Skype for Business 服务器监控报告包括30多个报告，旨在提供有关会议、对等 IM 会话、用户注册、响应组应用程序以及更多相关信息的详细信息。 对于2013版本，Skype for business Server Monitoring Reports 包含许多增强功能：
  
- **新增了语音质量报告**。 这些新报表包括[Skype For Business Server 中的 "媒体质量比较" 报告](../../manage/health-and-monitoring/comparison.md)，该报告比较不同类型的呼叫（例如，有线呼叫和无线呼叫之间）的质量。" [Skype For business" 服务器中的 "会议加入时间" 报表](../../manage/health-and-monitoring/join-time-report.md)，提供有关需要用户加入会议的时间量的信息。 
    
- **改进了用于分析视频和应用程序共享会话并对其进行故障排除的报告。** Skype for business [server 中的 "媒体质量摘要" 报表](../../manage/health-and-monitoring/summary.md)提供了一种方法来分析视频和应用程序共享调用，而[Skype for business 服务器中的服务器性能报告](../../manage/health-and-monitoring/server-performance.md)将详细介绍生成这些调用的服务器的性能。 视频和应用程序共享指标现在还由 skype for business [server 中的 "对等会话详细信息" 报告](../../manage/health-and-monitoring/peer-to-peer-session-detail-report.md)和[Skype for business 服务器中的 "会议详细信息](../../manage/health-and-monitoring/detail-report.md)" 报告进行报告。
    
- **改进了报告性能**。这包括更短的响应和数据检索时间，以及更快且更轻松的报告导航。
    
监控报告文档中提供了有关各个报告的详细信息。
  
> [!NOTE]
> Skype for Business 服务器中包含另一个报表 QoE 呼叫详细信息子报表。 但此报告主要供内部使用，且无法直接访问。 
  
安装 Skype for Business 服务器监视报告有两种方法：您可以使用 Skype for Business 服务器部署向导，也可以使用 Skype for business 服务器安装文件附带的 Windows PowerShell 脚本。 无论您使用哪种方法安装此报告，都必须先确保：
  
- 具有向监控数据库中的用户帐户添加数据库角色的权限。
    
- 担当 SQL Server Reporting Services 中的内容管理器角色。此角色授予您将报告部署到 SQL Server Reporting Services 的权限。
    
若要使用部署向导安装监控报告，请完成下列步骤：
  
1. 单击 "**开始**"，单击 "**所有程序**"，单击 "skype for business**服务器**"，然后单击 " **skype for business 服务器部署向导**"。
    
2. 在部署向导中，单击“**部署监控报告**”以便启动部署监控报告向导。
    
3. 在部署监控报告向导中的“**指定监控数据库**”页上，确保承载您的监控存储的计算机的完全限定域名显示在“**监控数据库**”下拉列表中。（如果您具有多个监控存储，则需要从该下拉列表中选择适当的服务器。）确认“**SQL Server Reporting Services (SSRS)实例**”框中显示了正确的 SQL Server 实例（例如，“**atl-sql-001.litwareinc.com/archinst**”），然后单击“**下一步**”。
    
4. 在“**指定凭据**”页上的“**用户名**”框中，键入在访问监控报告时要使用的帐户的域名和用户名（例如，“**litwareinc\kenmyer**”）。如果不使用此格式（域\用户名），则将发生错误。
    
    在“**密码**”框中键入用户帐户密码，然后单击“**下一步**”。请注意，此帐户不需要特殊权限。设置完成时，将自动向该帐户授予所需的登录和数据库权限。
    
5. 在“**指定只读组**”页上，输入将为其授予对“用户”分组框中的 SQL Server Reporting Services 的只读访问权的安全组的名称。例如，若要授予对报告的只读管理员访问权，请输入“**RTCUniversalReadOnlyAdmins**”。单击“**下一步**”。
    
6. 在“**正在执行命令**”页上，单击“**完成**”。
    
通过运行脚本 DeployReports，还可以从 Skype for Business Server Management Shell 安装监控报告。此 Windows PowerShell 脚本可在 "Business Server \<2015 \Skype\>安装位置" Deployment\Setup 文件夹中找到。 要使用 DeployReports.ps1 安装监控报告，请在命令行管理程序提示符处键入与以下内容类似的命令：
  
```powershell
C:\Program Files\Skype for Business Server 2015\Deployment\Setup\DeployReports.ps1 -storedUserName "litwareinc\kenmyer" -storedPassword "p@ssw0rd" -readOnlyGroupName "RTCUniversalReadOnlyAdmins" -reportServerSqlInstance "atl-sql-001.litwareinc.com" -monitoringDatabaseId "MonitoringDatabase:atl-sql-001.litwareinc.com"
```

上面的命令中使用的参数如下表所示：
  
|**参数名称**|**必需**|**说明**|
|:-----|:-----|:-----|
|storedUserName  <br/> |是  <br/> |用于访问监控存储的用户帐户（格式为 domain\username）；例如：  <br/> ```-storedUserName "litwareinc\kenmyer"```此帐户必须具有以前指定的 SQL Server 和 SQL Server Reporting Services 权限，否则脚本将失败。  <br/> |
|storedPassword  <br/> |是  <br/> |用于访问监控存储的用户帐户的密码。  <br/> |
|readOnlyGroupName  <br/> |否  <br/> |将向其成员授予对监控报告的只读访问权的域或本地安全组。请注意，如果指定的组不存在，该脚本将失败。如果您稍后决定撤消这些权限，或决定向其他用户或其他组授予访问权限，则可使用 SQL Service Reporting Services 报告管理器完成此操作。  <br/> |
|reportSqlServerInstance  <br/> |否  <br/> |承载 Reporting Service 的 SQL Server 实例。必须使用报告服务器的完全限定域名来指定报告实例；例如：<br/> ```-reportServerSqlInstance atl-sql-001.litwareinc.com```如果未包括此参数，脚本将假定报告服务由承载监视数据库的同一 SQL Server 实例托管。  <br/> |
|monitoringDatabaseId  <br/> |否  <br/> |监控数据库的服务标识。可以通过运行此命令返回监控数据库的标识：<br/> ```Get-CsService -MonitoringDatabase```|
   
安装监控报告之后，你必须使用 New-CsReportingConfiguration 配置用于访问这些报告的 URL。 可通过运行以下 Windows PowerShell 命令，从 Skype for Business Server Management Shell 执行此任务。 请注意，建议（但不要求）你在配置报告 URL 时使用 HTTPS 协议：
  
```powershell
New-CsReportingConfiguration -Identity 'service:MonitoringDatabase:atl-sql-001.litwareinc.com' -ReportingURL 'https://atl-sql-001.litwareinc.com:443/Reports_ARCHINST'
```

在上面的命令中，ReportingUrl 属性应设置为 SQL Server 2008 R2 Reporting Services 所使用的报告管理器 URL。可以通过在已安装 SQL Server Reporting Services 的计算机上完成以下步骤来确定报告管理器 URL：
  
1. 依次单击“开始”、“所有程序”、“Microsoft SQL Server 2008 R2”、“配置工具”和“Reporting Services 配置管理器”。
    
2. 在“Reporting Services 配置连接”对话框中，确保“服务器名称”框中显示 Reporting Services 计算机的名称。从“报告服务器实例”下拉列表中选择 SQL Server 实例，然后单击“连接”。
    
3. 在“Reporting Services 配置管理器”中，单击“报告管理器 URL”。“报告管理器 URL”窗格中应显示一个或多个 URL。虽然可将其中的任一 URL 用作报告 URL，但再次建议 ReportingUrl 使用 HTTPS 协议。
    
如果已为您的监控数据库设置镜像数据库，您也必须将监控报告与镜像数据库相关联。 有关详细信息，请参阅[在 Skype For Business 服务器中将监视报告与镜像数据库相关联](monitoring-reports-with-a-mirror-database.md)的文章。
  

