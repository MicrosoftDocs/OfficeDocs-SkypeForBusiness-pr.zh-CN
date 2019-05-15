---
title: Skype for Business Server 2015 的服务器要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 8d47b242-b93d-4c2e-a658-23b78bca30b1
description: 摘要： 使用本主题的业务服务器 2015年服务器准备您的 Skype。 硬件、 操作系统、 数据库、 软件、 所有的系统要求和建议在此处要帮助确保成功安装和部署服务器场。
ms.openlocfilehash: 364542308540e26022bc4e46eba62dcf8e4831c3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929376"
---
# <a name="server-requirements-for-skype-for-business-server-2015"></a>Server requirements for Skype for Business Server 2015
 
**摘要：** 利用本主题准备 Skype for Business Server 2015 服务器。这里提供了硬件、OS、数据库、软件、所有系统要求和建议，可帮助确保服务器场的安装和部署获得成功。

如果您正在寻找环境的要求，如 Active Directory、 DNS 或证书，您可以签出[的业务服务器 2015年的 Skype 环境要求](environmental-requirements.md)doc。
  
如预期的那样，有一些进行准备开始部署业务服务器 2015 Skype 之前。 本文将指导你制定以下规划：
  
- [适用于 Skype for Business Server 2015 的硬件](server-requirements.md#Hardware)
  
- [为业务服务器 2015 Skype 的操作系统](server-requirements.md#OS)
  
- [将与 Skype for Business Server 2015 配合工作的后端数据库](server-requirements.md#DBs)
  
- [应在 Skype for Business Server 2015 部署之前安装的软件](server-requirements.md#Software)
  
## <a name="hardware-for-skype-for-business-server-2015"></a>适用于 Skype for Business Server 2015 的硬件
<a name="Hardware"> </a>

现在，您必须向下您的拓扑 （并否则，您可以签出[的业务服务器 2015年的 Skype 拓扑基础知识](../../plan-your-deployment/topology-basics/topology-basics.md)主题），它具有时间考虑服务器。 Skype 业务服务器 2015年服务器需要 64 位硬件。 下面给出了我们的硬件建议。 这些不要求，但它们反映所必需的最佳性能的要求。 我们的容量规划文档可帮助你根据自己的环境确定是否需要高于此要求的配置。
  
建议的硬件的前端服务器、 后端服务器、 Standard Edition server 和持久聊天服务器：
  
|**硬件组件**|**推荐**|
|:-----|:-----|
|CPU  <br/> |64 位双处理器、六核、2.26 GHz 或更快。  <br/> Intel Itanium 处理器不支持 Skype 业务服务器 2015年角色。  <br/> |
|内存  <br/> |32 GB。  <br/> |
|磁盘  <br/> |以下之一：  <br/> • 8 或更多 10000 RPM 硬盘驱动器具有至少 72 GB 可用磁盘空间 （两个磁盘使用 RAID 1 和 6 使用 RAID 10）。  <br/> 或者  <br/> • 固态驱动器 (Ssd) 能够提供相同的可用空间和类似于 8 10000 RPM 机械磁盘驱动器的性能。  <br/> |
|网络  <br/> |1 个双端口网络适配器，1 Gbps 或更高（可使用 2 个网络适配器，但需要通过一个 MAC 地址和一个 IP 地址配合使用）。  <br/> 双处理器或多宿主配置是**不**支持前端服务器、 后端服务器、 Standard Edition 服务器和持久聊天服务器。 <br/> 只要它们不接触操作系统并且被用于监控和管理服务器硬件，你就能够拥有带外管理系统，如 DRAC 或 ILO。这种情况不会形成多宿主服务器，并且受支持。<br/> |
   
建议的边缘服务器、 独立中介服务器、 视频互操作服务器和控制器的硬件：
  
|**硬件组件**|**推荐**|
|:-----|:-----|
|CPU  <br/> |64 位双处理器、四核、2.26 GHz 或更快。  <br/> Intel Itanium 处理器不支持 Skype 业务服务器 2015年角色。  <br/> |
|内存  <br/> |16 GB。  <br/> |
|磁盘  <br/> |以下之一：  <br/> • 4 个或多个 10000 RPM 硬盘驱动器具有至少 72 GB 可用磁盘的空间 （磁盘应为 2 个 RAID 1 配置中）。  <br/> 或者  <br/> • 固态驱动器 (Ssd) 能够提供相同的可用空间和类似于 4 10000 RPM 机械磁盘驱动器的性能。  <br/> |
|网络  <br/> |1 个双端口网络适配器，1 Gbps 或更高（可使用 2 个网络适配器，但需要通过一个 MAC 地址和一个 IP 地址配合使用）。  <br/> 双处理器或多宿主配置是**不**支持视频互操作服务器和控制器。 <br/> 边缘服务器需要两个网络接口，均为双端口网络适配器、1 Gbps 或更高速度（或两个成对网络适配器，总计 4 个适配器，每一对均与单一 MAC 地址和单一 IP 地址配合使用，总共两对）。  <br/> 在独立中介服务器安装的其他网络接口卡 (Nic) 以允许的特定 PSTN IP 地址配置支持。  <br/> |
   
## <a name="operating-systems-for-skype-for-business-server-2015"></a>为业务服务器 2015 Skype 的操作系统
<a name="OS"> </a>

硬件就地后，您需要安装操作系统 (OS)。 这些是使您可以安装和成功用于业务服务器 2015 Skype 操作系统。
  
|||
|:-----|:-----|
|Windows Server 2016 （需要 Skype 的业务累积更新 5 或更高版本。 有关详细信息检查[KB4015888](https://support.microsoft.com/en-gb/help/4015888/how-to-install-skype-for-business-server-2015-on-windows-server-2016)）  <br/> ||
|Windows Server 2012 R2 Datacenter 操作系统安装的所有必需更新。  <br/> |Windows Server 2012 R2 Standard 操作系统安装的所有必需更新。  <br/> |
|安装所有必需更新的 Windows Server 2012 Datacenter 操作系统。  <br/> |Windows Server 2012 Standard 操作系统安装的所有必需更新。  <br/> |
   
如果它不在此列表中，它将无法正常工作，请不尝试使用它的 Skype 的新安装的业务服务器 2015年。
  
> [!NOTE]
> 您可能已经注意到 Windows Server 2008 R2 不在此列表。 这是因为我们建议 Windows Server 2012 R2 的所有新服务器用于 SFB。 您应仅使用 Windows Server 2008 R2 时必须已安装，Lync Server 2013 中使用的现有服务器和您打算执行就地升级它们。 Windows Server 2008 R2 上 1/13/2015年到达受主要支持生命周期的结尾。 
  
除了最新的 Service Pack 外，您还应确保在相关的地方安装以下更新：
  
- 对于 Windows Server 2012，应首先安装知识库文章 2858668 提供的更新，然后再进行升级。 [获取在此处](https://support.microsoft.com/en-us/kb/2858668/)。
    
- 如果你拥有 Windows Server 2012 R2，请首先安装知识库文章 2982006 提供的更新，然后再进行升级。 [它在此处找到](https://support.microsoft.com/en-us/kb/2982006/)。
    
- 如果你是在 Windows Server 2008 R2 机器上进行升级（参阅上述备注），则你应首先安装知识库文章 2533623 提供的更新。 [它位于此链接](https://support.microsoft.com/en-us/kb/2533623/)。
    
## <a name="back-end-databases-that-will-work-with-skype-for-business-server-2015"></a>将与 Skype for Business Server 2015 配合工作的后端数据库
<a name="DBs"> </a>

安装时 Skype 对于业务 Server 2015 Standard Edition，您将看到 SQL Server 2014 Express 也会自动安装 （64 位版本）。
  
业务 Server 2015 Enterprise Edition 的 Skype 有点复杂，但下面是受支持的列表 (所有内容都是 64 位版本，您会注意到，请不要使用 32 位版本):
  
|||||
|:-----|:-----|:-----|:-----|:-----|
|Microsoft SQL Server 2017 企业版 （64 位版本），以及我们建议最新的 service pack 的运行。 <br/> |Microsoft SQL Server 2016 企业版 （64 位版本） Service Pack 1 或更高版本，并且您必须运行与 Skype 的业务累积更新 7 或更高版本 （[下载业务累积更新的 Skype](https://support.microsoft.com/en-us/help/3061064)）。  <br/> |Microsoft SQL Server 2014 企业版 （64 位版本），并且您必须运行与累积更新 6 或更高版本 （[下载累积更新 6](https://support.microsoft.com/en-us/kb/3031047/)）。  <br/> |Microsoft SQL Server 2012 Enterprise （64 位版本），以及我们建议最新的 service pack 的运行。  <br/> |
|Microsoft SQL Server 2017 标准 （64 位版本），以及我们建议最新的 service pack 的运行。 <br/> |Microsoft SQL Server 2016 标准 （64 位版本） Service Pack 1 或更高版本，并且您必须运行与 Skype 的业务累积更新 7 或更高版本 （[下载业务累积更新的 Skype](https://support.microsoft.com/en-us/help/3061064)）。  <br/> |Microsoft SQL Server 2014 标准 （64 位版本），并且您必须运行与累积更新 6 或更高版本 （[下载累积更新 6](https://support.microsoft.com/en-us/kb/3031047/)）。  <br/> |Microsoft SQL Server 2012 Standard （64 位版本），以及我们建议最新的 service pack 的运行。  <br/> |
   
如果您没有看到要使用此处列出的 SQL Server 版本，则无法使用它。
  
> [!NOTE]
> 您还将需要安装监控服务器角色的 SQL Server Reporting Services。

### <a name="microsoft-exchange-storage"></a>Microsoft Exchange 存储
Meeting content files, such as PowerPoint presentations, are archived as attachments. 如果您想要存储 Skype 业务 Exchange 合规性数据的存档数据，您必须使用 Exchange 部署 Exchange，并确保的最大存储大小支持存储会议内容文件。 您必须部署 Exchange 之前部署和启用存档使用 Microsoft Exchange 集成选项。 
    
    If you choose to use Exchange storage, you do not need to deploy separate SQL Server databases for archiving, unless you have Skype for Business users who are not homed on your Exchange servers. If you deploy archiving using the Microsoft Exchange integration option, Skype for Business archive data is stored with Exchange compliance data only for the users who are homed on your Exchange servers. 
  
## <a name="hardware-and-software-requirements-for-archiving-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 中的存档的硬件和软件要求
  
存档不是定义的服务器角色，您无需安装单独的存档服务器。 统一的数据收集代理是自动安装并激活的每个 Enterprise Edition 前端池和每个 Standard Edition Server 上。 您需要使用拓扑生成器启用和发布存档拓扑。
    
存档使用 Skype Business Server 文件存储临时存储会议内容文件，因此您不设置单独的文件存储的存档。
    
Microsoft 消息队列不是必需的。
    
您需要为存档存储设置基础结构。 这包括选择任一 Exchange 或存档使用 SQL Server 存储。   Skype 业务 Server 存档基础结构要求都与部署 Skype 业务服务器相同。 有关详细信息，请参阅[您 Skype 业务环境要求](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md)。 
  
> [!NOTE]
> 以支持用户均未驻留在 Exchange 服务器上或如果您不希望使用的 Microsoft Exchange 集成选项，则必须部署使用 64 位 SQL Server 数据库的存档存储。 
    
您必须设置之前部署和启用存档的 SQL Server 平台。 如果用于发布拓扑的帐户具有适当的管理员权限，则可在发布拓扑时创建存档数据库 (LcsLog)。 您稍后还可创建数据库（包括在安装过程中）。 有关 SQL Server 的详细信息，请参阅[SQL Server 文档](https://go.microsoft.com/fwlink/p/?linkID=129045)。
    
存档带来的负载提升可能非常显著。 因此，您应确保磁盘空间足够的前端服务器启用存档。

### <a name="sql-mirroring-sql-clustering-and-sql-always-on"></a>SQL 镜像、SQL 群集和 SQL Always On

您可以与 Skype 的业务服务器 2015年使用 SQL 镜像或 SQL 群集，它受支持。 SQL 镜像设置通过 Skype 业务 Server 拓扑生成器。 如果您在设置 SQL 群集的用途，完成在 SQL Server 中。
  
确保您具有主动/被动配置 SQL 群集，，这是受支持的功能。 不与任何其他 SQL 实例共享被动节点。
  
可以为故障转移群集采用以下配置：
  
双节点：
  
- Microsoft SQL Server 2017 标准 （64 位版本），以及我们建议最新的 service pack 的运行。

- Microsoft SQL Server 2016 标准 （64 位版本） Service Pack 1 或更高版本。 我们建议最新的 service pack 的运行。

- Microsoft SQL Server 2014 标准 （64 位版本），以及我们建议最新的 service pack 的运行。
    
-  Microsoft SQL Server 2012 Standard （64 位版本），以及我们建议最新的 service pack 的运行。

16 节点：

- Microsoft SQL Server 2017 企业版 （64 位版本），以及我们建议最新的 service pack 的运行。

- Microsoft SQL Server 2016 企业版 （64 位版本） Service Pack 1 或更高版本。 我们建议最新的 service pack 的运行。
  
- Microsoft SQL Server 2014 企业版 （64 位版本），以及我们建议最新的 service pack 的运行。
    
- Microsoft SQL Server 2012 Enterprise （64 位版本），以及我们建议最新的 service pack 的运行。

> [!IMPORTANT]
> 升级，我们希望您以确保在前端服务器至少具有 SQL Server 2012 SP1 安装之前升级。 到 SP1，如果您想要立即下载[这是一个链接](https://www.microsoft.com/en-us/download/details.aspx?id=35575)。
  
如果您需要阅读 up SQL 镜像的详细信息，我们具有后端服务器高可用性中 Skype 业务服务器 2015年主题。 配置 SQL Server 群集的业务服务器 2015年的 Skype 具有用于获取就绪群集的步骤。 还有更多链接上故障转移群集的 SQL， [2014年](https://technet.microsoft.com/en-us/library/hh231721.aspx)、 [2012年](https://technet.microsoft.com/en-us/library/hh231721%28v=sql.110%29.aspx)和[2008年](https://technet.microsoft.com/en-us/library/ms189134%28v=sql.105%29.aspx)。
  
> [!NOTE]
> 新的 2015年版本中为 SQL Always On 支持。 支持，并且您可以阅读更多有关该产品[中的业务服务器 2015 Skype 的后端服务器高可用性](../../plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md)主题中。

> [!NOTE]
> SQL 镜像的业务服务器 2015 Skype 中可用，但业务服务器 2019年不再支持在 Skype。 AlwaysOn 可用性组、 AlwaysOn 故障转移群集实例 (FCI)，和 SQL 故障转移群集方法是首选与 Skype 的业务服务器 2019年。  

## <a name="software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment"></a>应在 Skype for Business Server 2015 部署之前安装的软件
<a name="Software"> </a>

您将需要安装或配置运行 Skype 业务服务器 2015，任何服务器的一些方法和它们下面列出。 满足这些条件后，还要满足特定服务器角色的额外要求。
  
 **所有服务器：**
  
|**软件/角色**|**详细信息**|
|:-----|:-----|
|Windows PowerShell 3.0  <br/> |为业务 Server 服务器的所有 Skype 都需要安装的 Windows PowerShell 3.0。  <br/> • 如果您正在制作 Windows Server 2012 或 Windows Server 2012 R2 上的安装，您正在设置，因为它已存在。  <br/> • 如果您正在执行 Windows Server 2008 R2 上的升级，您可以下载[Windows Management Framework 3.0](https://www.microsoft.com/en-us/download/details.aspx?id=34595)即可使用它。 <br/> **提示：** 在那里正确 PowerShell 后，确认其 BuildVersion 6.2.9200.0 或更高版本，转到 PowerShell 提示并键入`$PSVersionTable`。 此应显示所需的信息。  <br/> |
|Microsoft .NET Framework  <br/> |WCF 服务是一项**功能**已安装作为 Windows 功能，在**服务器管理器**下没有所需的下载。 <br/> • 所需安装此功能，或者如果它已经安装并正在对其，检查的**HTTP 激活**选项还会检查和安装，以确保，如下所示： <br/> ![显示在.NET Framework 4.5 功能下的 HTTP 激活选项的屏幕截图。](../../media/a4064fa0-fa49-4474-bd98-b9a79ff68f8b.png)不要担心，如果您收到反映其他一些操作需要安装的 HTTP 激活安装其他弹出窗口。 这种情况非常正常，只要单击“确定”，继续操作即可。 如果未看到此弹出信息，则可以假设这些功能均已安装，您可以继续操作。  <br/> 通常安装 Microsoft.NET Framework 安装 Windows Server 2012 R2 或 Windows Server 2016 时。 Skype 业务 server 适用于以下的 Microsoft.NET Framework 版本：  <br/> •.NET 3.5  <br/> •.NET 4.5  <br/> •.NET 4.6.x  <br/> •.NET 4.7.1 及更高 （对于业务 Server 累积更新 5 或更高版本的 Skype)  <br/>  可能将默认情况下，在 Windows Server 2008 R2 计算机上安装.NET framework 3.5 （肯定检查以确保在升级之前），但它实际上不是 Windows Server 2012/Windows Server 2012 R2 服务器 （针对新安装） 上。 若要添加中，您将需要访问安装驱动器或媒体 （Windows Server 从，安装位置或安装文件所在现在）。 然后继续操作，并从服务器管理器将其作为功能进行安装，在提示时指向安装媒体（即 **\sources\sxs** 文件夹），然后继续安装。 <br/> |
|媒体基础  <br/> |Windows Server 2016、 Windows Server 2012 和 Windows Server 2012 R2 与 Microsoft 媒体 Foundation 将安装 Windows Media Format Runtime。  <br/> 用于会议的所有前端服务器和 Standard Edition 服务器需要 Windows Media Format Runtime，若要运行的 Windows Media 音频 (.wma) 文件的呼叫寄存、 通知和响应组应用程序播放通知和保持音乐。  <br/> |
|Windows Identity Foundation  <br/> |我们需要 Windows Identity Foundation 3.5 对业务服务器 2015 Skype 支持服务器到服务器身份验证方案。  <br/> ？ 对于 Windows Server 2012 和 Windows Server 2012 R2，则不需要下载任何内容。 打开**服务器管理器**，转到**添加角色和功能向导**。 **Windows Identity Foundation 3.5** 在**功能**部分列出。 如果选中，您很好。 否则请选中它，并单击“下一步”，然后单击**安装**按钮。 <br/> |
|远程服务器管理工具  <br/> |角色管理工具：AD DS 和 AD LDS 工具  <br/> |
   
 **前端服务器和 Standard Edition server 还需要：**
  
|**软件/角色**|**详细信息**|
|:-----|:-----|
|Internet Information Services (IIS)  <br/> |IIS 的以下模块选择需要的所有前端服务器，以及所有 Standard Edition server 上：  <br/> • 常见 HTTP 功能： 默认文档，HTTP 错误静态内容  <br/> • 运行状况和诊断： HTTP 日志记录，日志记录工具，跟踪  <br/> • 性能： 静态内容压缩、 动态内容压缩  <br/> • 安全： 请求筛选、 客户端证书映射身份验证、 Windows 身份验证  <br/> • 应用程序开发：.NET 扩展性 3.5、.NET 扩展性 4.5、 ASP.NET 3.5、 ASP.NET 4.5，ISAPI 扩展 ISAPI 筛选器  <br/> • 管理工具： IIS 管理控制台、 IIS 管理脚本和工具  <br/> 我们还应注意还需要匿名访问，但在您安装 IIS，以便您无需在列表中选择的位置时，会看到的。  <br/> |
|Windows Media Format Runtime  <br/> | Windows Server 2016、 Windows Server 2012 和 Windows Server 2012 R2，您需要在**服务器管理器**中安装**媒体 Foundation**功能。 现在，您实际可以开始没有此业务服务器 2015年安装您 Skype 系统将提示您安装它，但然后重新启动服务器，业务服务器 2015年 Skype 之前安装继续。 因此最好提前安装。 <br/> |
|Silverlight  <br/> |您可以安装在[此链接](https://www.microsoft.com/silverlight/)Silverlight 的最新版本。  <br/> |
   
> [!NOTE] 
> 您可能还需要启用目录浏览如果您使用的负载平衡器。 否则将加载负载平衡器可能会考虑故障的空白页。 

为帮助您了解相关过程，我们提供了一个示例 PowerShell 脚本，您可以运行此脚本以自动执行此流程：

```
Add-WindowsFeature NET-Framework-Core, RSAT-ADDS, Windows-Identity-Foundation, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Dir-Browsing, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, BITS, Desktop-Experience, Telnet-Client
```

> [!NOTE] 
> 该命令查找特定的顺序的源文件。 如果您处于联机状态，该命令可访问 Windows Update。 但是，如果您处于脱机状态，则需要确保源文件可被该命令使用。 有关使用 PowerShell 安装角色和功能的详细信息，请参阅[安装或卸载角色、 角色服务或功能](https://technet.microsoft.com/en-us/library/hh831809.aspx)不要忘记 Windows 再次运行更新后安装必备组件，即使您使用的 PowerShell 命令。

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
    
（如果您想知道，它是设置为具有动态内容压缩的前端服务器和 Standard Edition 服务器相同模块和管理工具遗漏。）
  
我们还为此提供了以下一些 PowerShell 代码：
  
```
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Scripting-Tools, Web-Mgmt-Compat, Desktop-Experience, Telnet-Client
```

 **持久聊天服务器还需要：**
  
消息队列，也称为 MSMQ。 它是 Windows Server 组件，并将其安装在功能部分的服务器管理器中。 如果您想要了解有关此操作，请签出[安装和管理消息队列](https://technet.microsoft.com/en-us/library/cc771474.aspx)。
  
 **最后注意事项：**
  
请不要安装任何 Microsoft Internet Security and Acceleration (ISA) Server 客户端软件或任何其他 Winsock 层次服务提供程序 (LSP) 软件 （任何第三方防火墙或网络防病毒检查软件应该包含此处） 上前端服务器或独立中介服务器的任何。 质量欠佳的媒体流量性能发生时，该软件的安装。
  

