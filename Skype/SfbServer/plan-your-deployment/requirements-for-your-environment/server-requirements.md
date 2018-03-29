---
title: Skype for Business Server 2015 的服务器要求
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 8d47b242-b93d-4c2e-a658-23b78bca30b1
description: 摘要： 对于本主题的业务服务器 2015年服务器准备您 Skype。 硬件、 操作系统、 数据库、 软件、 所有系统要求和建议都将帮助确保成功安装和部署的服务器场。
ms.openlocfilehash: 8a86c96554d7aa1be0597c5c82614cd43816540f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="server-requirements-for-skype-for-business-server-2015"></a>Skype for Business Server 2015 的服务器要求
 
**摘要：**利用本主题准备 Skype for Business Server 2015 服务器。这里提供了硬件、OS、数据库、软件、所有系统要求和建议，可帮助确保服务器场的安装和部署获得成功。
  
如您所料，有一些准备，以使您开始部署 Skype 业务服务器 2015年之前。 本文将指导你制定以下规划：
  
- [适用于 Skype for Business Server 2015 的硬件](server-requirements.md#Hardware)
  
- [用于业务服务器 2015年的 Skype 的操作系统](server-requirements.md#OS)
  
- [将与 Skype for Business Server 2015 配合工作的后端数据库](server-requirements.md#DBs)
  
- [应在 Skype for Business Server 2015 部署之前安装的软件](server-requirements.md#Software)
  
## <a name="hardware-for-skype-for-business-server-2015"></a>适用于 Skype for Business Server 2015 的硬件
<a name="Hardware"> </a>

现在，您有您的拓扑结构下，如果不这样做，您可以签出该[业务服务器 2015年的 Skype 的拓扑结构基础知识](../../plan-your-deployment/topology-basics/topology-basics.md)主题） 是时候了，要考虑服务器。 Skype 的业务服务器 2015年服务器需要 64 位硬件。 下面给出了我们的硬件建议。 这些都不是要求，但它们反映了以获得最佳性能所需的要求。 我们的容量规划文档可帮助你根据自己的环境确定是否需要高于此要求的配置。
  
建议为前端服务器后, 端服务器，标准版服务器和持久聊天服务器的硬件：
  
|**硬件组件**|**建议**|
|:-----|:-----|
|CPU  <br/> |64 位双处理器、六核、2.26 GHz 或更快。  <br/> 英特尔安腾处理器不支持 Skype 业务服务器 2015年角色。  <br/> |
|内存  <br/> |32 GB。  <br/> |
|磁盘  <br/> |以下之一：  <br/> • 8 块或更多 10000 RPM 硬盘，至少 72 GB 可用磁盘空间（2 块磁盘使用 RAID 1，6 块磁盘使用 RAID 10）。  <br/> 或  <br/> • 能够提供与 8 块 10000 RPM 机械硬盘相同的可用空间和类似性能的固态硬盘 (SSD)。  <br/> |
|网络  <br/> |1 个双端口网络适配器，1 Gbps 或更高（可使用 2 个网络适配器，但需要通过一个 MAC 地址和一个 IP 地址配合使用）。  <br/> 双站点或多宿主配置的服务器，**不**支持的前端服务器后, 端服务器，标准版和持久聊天服务器。 <br/> 只要它们不接触操作系统并且被用于监控和管理服务器硬件，你就能够拥有带外管理系统，如 DRAC 或 ILO。这种情况不会形成多宿主服务器，并且受支持。<br/> |
   
建议为边缘服务器、 独立中介服务器、 视频互操作服务器和导演的硬件：
  
|**硬件组件**|**建议**|
|:-----|:-----|
|CPU  <br/> |64 位双处理器、四核、2.26 GHz 或更快。  <br/> 英特尔安腾处理器不支持 Skype 业务服务器 2015年角色。  <br/> |
|内存  <br/> |16 GB。  <br/> |
|磁盘  <br/> |以下之一：  <br/> • 4 块或更多 10000 RPM 硬盘，至少 72 GB 可用磁盘空间（磁盘应采用双 RAID 1 配置）。  <br/> 或  <br/> • 能够提供与 4 块 10000 RPM 机械硬盘相同的可用空间和类似性能的固态硬盘 (SSD)。  <br/> |
|网络  <br/> |1 个双端口网络适配器，1 Gbps 或更高（可使用 2 个网络适配器，但需要通过一个 MAC 地址和一个 IP 地址配合使用）。  <br/> 双站点或多宿主配置**不**支持视频互操作服务器和 Director。 <br/> 边缘服务器需要两个网络接口，均为双端口网络适配器、1 Gbps 或更高速度（或两个成对网络适配器，总计 4 个适配器，每一对均与单一 MAC 地址和单一 IP 地址配合使用，总共两对）。  <br/> 支持在独立上中介服务器的其他网络接口卡 (Nic)，以允许特定的 PSTN IP 地址的配置安装。  <br/> |
   
## <a name="operating-systems-for-skype-for-business-server-2015"></a>用于业务服务器 2015年的 Skype 的操作系统
<a name="OS"> </a>

一旦有硬件，您将需要安装操作系统 (OS)。 它们将使您能够安装并成功地用于业务服务器 2015 Skype 的操作系统。
  
|||
|:-----|:-----|
|Windows Server 2016  <br/> ||
|Windows Server 2012 R2 数据中心操作系统与安装所有必需的更新。  <br/> |Windows Server 2012 R2 标准操作系统安装所需的全部更新。  <br/> |
|与安装所需的全部更新，Windows Server 2012 数据中心操作系统。  <br/> |Windows Server 2012 标准操作系统安装所需的全部更新。  <br/> |
   
如果它不在此列表中，它将无法正常工作，请不要试它为全新安装 Skype 的业务服务器 2015年个。
  
> [!NOTE]
> 您或许已经注意到，此列表中未包含 Windows Server 2008 R2。因为我们推荐为所有用于 SFB 的新服务器使用 Windows Server 2012 R2。只有在现有服务器已经安装 Lync Server 2013，并且希望对其执行就地升级的情况下才应使用 Windows Server 2008 R2。Windows Server 2008 R2 已于 2015 年 1 月 13 日结束主流支持生命周期。 
  
除了最新的 Service Pack 外，您还应确保在相关的地方安装以下更新：
  
- 对于 Windows Server 2012，应首先安装知识库文章 2858668 提供的更新，然后再进行升级。 [在此处获得](https://support.microsoft.com/en-us/kb/2858668/)。
    
- 如果你拥有 Windows Server 2012 R2，请首先安装知识库文章 2982006 提供的更新，然后再进行升级。 [这里找到它](https://support.microsoft.com/en-us/kb/2982006/)。
    
- 如果你是在 Windows Server 2008 R2 机器上进行升级（参阅上述备注），则你应首先安装知识库文章 2533623 提供的更新。 [它位于此链接](https://support.microsoft.com/en-us/kb/2533623/)。
    
## <a name="back-end-databases-that-will-work-with-skype-for-business-server-2015"></a>将与 Skype for Business Server 2015 配合工作的后端数据库
<a name="DBs"> </a>

当安装 Skype 业务服务器 2015年标准版，将有 SQL Server 2014年表达也会自动安装 （64 位版）。
  
Skype 业务服务器 2015年企业版是稍微复杂一些，但以下是受支持的列表 (一切都是 64 位版本，您会注意到，请不要使用 32 位版本):
  
||||
|:-----|:-----|:-----|
|Microsoft SQL Server 2014年企业 （64 位版），并且您必须运行与累积更新 6 或更高版本 （[下载累积更新 6](https://support.microsoft.com/en-us/kb/3031047/)）。  <br/> |Microsoft SQL Server 2012年企业 （64 位版），和建议使用最新的服务包运行。  <br/> |Microsoft SQL Server 2008 R2 企业 （64 位版），和建议使用最新的服务包运行。  <br/> |
|Microsoft SQL Server 2014年标准 （64 位版），并且您必须运行与累积更新 6 或更高版本 （[下载累积更新 6](https://support.microsoft.com/en-us/kb/3031047/)）。  <br/> |Microsoft SQL Server 2012年标准 （64 位版），和建议使用最新的服务包运行。  <br/> |Microsoft SQL Server 2008 R2 标准 （64 位版），和建议使用最新的服务包运行  <br/> |
   
如果看不到您要使用此处列出的 SQL Server 版本，则不能使用它。
  
> [!NOTE]
> 您还将需要安装 SQL Server 报表服务监视服务器角色，但我们希望您能够知道这不会与 SQL 总是上才支持 post-RTM。 
  
### <a name="sql-mirroring-sql-clustering-and-sql-always-on"></a>SQL 镜像、SQL 群集和 SQL Always On

您将能够使用 SQL 镜像或 SQL 群集使用 Skype 业务服务器 2015年，此支持。 SQL 镜像设置通过 Skype 业务服务器拓扑生成器。 如果您在设置 SQL 群集上的意图，在 SQL Server 中完成的。
  
确保您具有主动/被动配置 SQL 群集，因为什么都支持。 不与任何其他 SQL 实例共享的被动节点。
  
可以为故障转移群集采用以下配置：
  
双节点：
  
- Microsoft SQL Server 2014年标准 （64 位版），和建议使用最新的服务包运行。
    
-  Microsoft SQL Server 2012年标准 （64 位版），和建议使用最新的服务包运行。
    
- Microsoft SQL Server 2008 R2 标准 （64 位版），和建议使用最新的服务包运行。
    
16 节点：
  
- Microsoft SQL Server 2014年企业 （64 位版），和建议使用最新的服务包运行。
    
- Microsoft SQL Server 2012年企业 （64 位版），和建议使用最新的服务包运行。
    
- Microsoft SQL Server 2008 R2 企业 （64 位版），和建议使用最新的服务包运行。
    
> [!IMPORTANT]
> 进行升级时，我们也希望您可以确保您前端服务器至少具有在 SQL Server 2012 SP1 安装升级之前。 [这是一个链接](https://www.microsoft.com/en-us/download/details.aspx?id=35575)到 SP1 如果您希望立即下载它。
  
如果需要仔细读一下 SQL 镜像的详细信息，我们将后端服务器的高可用性在 Skype 业务服务器 2015年主题。 配置群集 SQL Server 的业务服务器 2015年的 Skype 已获取准备好群集的步骤。 还有更多的链接上的故障转移群集 SQL，为[2014年](https://technet.microsoft.com/en-us/library/hh231721.aspx)、 [2012](https://technet.microsoft.com/en-us/library/hh231721%28v=sql.110%29.aspx)年和[2008 年](https://technet.microsoft.com/en-us/library/ms189134%28v=sql.105%29.aspx)。
  
> [!NOTE]
> 此版本新增了 SQL Always On 支持。 是否支持它，并且您可以阅读更多有关该[业务服务器 2015年的 Skype 在后端服务器高可用性](../../plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md)主题中。
  
## <a name="software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment"></a>应在 Skype for Business Server 2015 部署之前安装的软件
<a name="Software"> </a>

您将需要安装或配置任何服务器运行业务服务器 2015，Skype 的一些方法，它们在下面列出。 满足这些条件后，还要满足特定服务器角色的额外要求。
  
 **所有服务器：**
  
|**软件/角色**|**详细信息**|
|:-----|:-----|
|Windows PowerShell 3.0  <br/> |所有 Skype 业务服务器服务器都需要安装的 Windows PowerShell 3.0。  <br/> • 如果您正在 Windows Server 2012 或 Windows Server 2012 R2 上的安装，您正在设置，因为它已存在。  <br/> • 如果您正在 Windows Server 2008 R2 上的升级，您可以下载[Windows 管理框架 3.0](https://www.microsoft.com/en-us/download/details.aspx?id=34595)即可使用它。 <br/> **提示：**一旦在那里有了正确 PowerShell，确认它是 BuildVersion 6.2.9200.0 或以后转到 PowerShell 提示并键入`$PSVersionTable`。 此操作将显示你所需的信息。  <br/> |
|Microsoft .NET Framework  <br/> |WCF 服务是一种**功能**已安装作为 Windows 功能，请在**服务器管理器**，需要没有下载。 <br/> • 您需要确保，当您安装此功能，或者如果已安装和检查，同时检查和安装，使用**HTTP 激活**选项如下所示： <br/> ![显示.NET Framework 4.5 功能下的 HTTP 激活选项的屏幕截图。](../../media/a4064fa0-fa49-4474-bd98-b9a79ff68f8b.png)不要担心如果您收到指出的一些其他事项需要 HTTP 激活安装的安装其他弹出窗口。 这种情况非常正常，只要单击“确定”，继续操作即可。 如果未看到此弹出信息，则可以假设这些功能均已安装，您可以继续操作。  <br/> Microsoft.NET Framework 通常安装在安装 Windows Server 2012 R2 或 Windows 服务器 2016年。 Skype 业务服务器适用于以下 Microsoft.NET Framework 版本：  <br/> •.NET 3.5  <br/> •.NET 4.5  <br/> •.NET 4.6.x  <br/> •.NET 4.7 （用于 Skype 业务服务器 CU 5 或更高版本)  <br/>  默认情况下，Windows Server 2008 R2 计算机上可能会安装.NET Framework 3.5 （明确检查以确保在升级之前），但实际上它不是您的 Windows Server 2012 / Windows Server 2012 R2 服务器 （对于新安装）。 若要添加中，您需要访问安装驱动器或介质 （位置，安装 Windows 服务器或安装文件现）。 然后继续操作，并从服务器管理器将其作为功能进行安装，在提示时指向安装媒体（即 **\sources\sxs** 文件夹），然后继续安装。 <br/> |
|媒体基础  <br/> |对于 Windows 服务器 2016年、 Windows Server 2012 和 Windows Server 2012 R2 Windows 媒体格式运行时安装与 Microsoft 媒体基础。  <br/> 所有的前端服务器和标准版服务器用于会议要求 Windows 媒体格式运行时运行的 Windows Media 音频 (.wma) 文件调用公园、 公告，并响应组的应用程序播放公告和音乐。  <br/> |
|Windows Identity Foundation  <br/> |我们需要对业务服务器 2015 Skype 支持服务器到服务器的身份验证方案 Windows 身份基础 3.5。  <br/> • 有关 Windows Server 2012 和 Windows Server 2012 R2，则无需下载任何东西。 打开**服务器管理器**，转到**添加角色和功能向导**。 **Windows Identity Foundation 3.5** 在**功能**部分列出。 如果选中该选项，就好了。 否则请选中它，并单击“下一步”，然后单击**安装**按钮。 <br/> |
|远程服务器管理工具  <br/> |角色管理工具：AD DS 和 AD LDS 工具  <br/> |
   
 **前端服务器和标准版服务器还需要：**
  
|**软件/角色**|**详细信息**|
|:-----|:-----|
|Internet Information Services (IIS)  <br/> |IIS 在所有前端服务器，以及所有的标准版服务器需要与以下模块选择：  <br/> • 通用 HTTP 功能： 默认文档，HTTP 错误，静态内容  <br/> • 运行状况和诊断： HTTP 日志记录、 日志记录工具，跟踪  <br/> • 性能： 静态内容压缩、 动态内容压缩  <br/> • 安全： 请求筛选、 客户端证书映射身份验证，Windows 身份验证  <br/> • 应用程序开发：.NET 可扩展性 3.5，.NET 4.5 扩展性、 ASP.NET 3.5，ASP.NET 4.5，ISAPI 扩展的 ISAPI 筛选器  <br/> • 管理工具： IIS 管理控制台中，IIS 管理脚本和工具  <br/> 我们还应注意还需要匿名访问，但在您安装 IIS，因此您不必在列表中，选择一个地方时，会看到的。  <br/> |
|Windows Media Format Runtime  <br/> | 对于 Windows 服务器 2016年、 Windows Server 2012 和 Windows Server 2012 R2，您需要在**服务器管理器**安装**媒体基础**功能。 现在，您实际上可以启动您没有该业务服务器 2015年安装 Skype 但将提示您安装它，然后重新启动服务器，用于业务服务器 2015 Skype 之前安装继续进行。 因此最好提前安装。 <br/> |
|Silverlight  <br/> |您可以安装最新版 Silverlight 在[此链接](https://www.microsoft.com/silverlight/)。  <br/> |
   
为帮助您了解相关过程，我们提供了一个示例 PowerShell 脚本，您可以运行此脚本以自动执行此流程：
  
```
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Desktop-Experience, Telnet-Client
```

 **控制器还需要：**
  
IIS，选择以下模块：
  
- 常见的 HTTP 功能
    
  - 默认文档
    
  - HTTP 错误
    
  - 静态内容
    
- 运行状况和诊断
    
  - HTTP 日志记录
    
  - 日志记录工具
    
  - 跟踪
    
- 性能
    
  - 静态内容压缩
    
- 安全性
    
  - 请求筛选
    
  - 客户端证书映射身份验证
    
  - Windows 身份验证
    
- 应用程序开发
    
  - .NET Extensibility 3.5
    
  - .NET Extensibility 4.5
    
  - ASP.NET 3.5
    
  - ASP.NET 4.5
    
  - ISAPI 扩展
    
  - ISAPI 筛选器
    
（如果您想知道，它是相同的模块设置为具有动态内容压缩的前端服务器和标准版服务器和管理工具遗漏。）
  
我们还为此提供了以下一些 PowerShell 代码：
  
```
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Scripting-Tools, Web-Mgmt-Compat, Desktop-Experience, Telnet-Client
```

 **此外需要持久的聊天服务器：**
  
消息队列，也称为 MSMQ。 它是 Windows 服务器组件，并将其安装在服务器管理器中的功能部分下。 如果您想要阅读更多关于这一点，请查看[安装和管理消息队列](https://technet.microsoft.com/en-us/library/cc771474.aspx)。
  
 **最后注意事项：**
  
请不要安装任何 Microsoft Internet 安全和加速 (ISA) 服务器的客户端软件或任何其他的 Winsock 分层服务提供程序 (LSP) 软件 （任何第三方防火墙或防病毒网络检查软件应该包含此处） 上任何前端服务器或独立中介服务器。 该软件的安装时曾出现不良媒体的通信性能。
  

