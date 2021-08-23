---
title: Skype for Business Server 2015 的服务器要求
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 8d47b242-b93d-4c2e-a658-23b78bca30b1
description: 摘要：使用本主题Skype for Business Server 2015 服务器。 硬件、操作系统、数据库、软件、所有系统要求和建议均在此处，可帮助确保成功安装和部署服务器场。
ms.openlocfilehash: 2c709dbc3afa2290cc9260dd71b73ab5da898d88
ms.sourcegitcommit: 6a87a4180519e493ac115c2faadb9ccae26d5a35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/17/2021
ms.locfileid: "58372072"
---
# <a name="server-requirements-for-skype-for-business-server-2015"></a>Skype for Business Server 2015 的服务器要求
 
**摘要：** 使用本主题Skype for Business Server 2015 服务器。 硬件、操作系统、数据库、软件、所有系统要求和建议均在此处，可帮助确保成功安装和部署服务器场。

如果要查找环境要求（如 Active Directory、DNS 或证书），请查看 environmental requirements [for Skype for Business Server 2015](environmental-requirements.md)文档。
  
正如您预期，在开始部署 2015 年 10 月之前，需要做一些Skype for Business Server准备工作。 本文将介绍规划以下内容：
  
- [2015 Skype for Business Server的硬件](server-requirements.md#Hardware)
  
- [Skype for Business Server 2015 的操作系统](server-requirements.md#OS)
  
- [与 2015 Skype for Business Server数据库](server-requirements.md#DBs)
  
- [应在部署 2015 年 Skype for Business Server之前安装的软件](server-requirements.md#Software)
  
## <a name="hardware-for-skype-for-business-server-2015"></a>2015 Skype for Business Server的硬件
<a name="Hardware"> </a>

现在，您的拓扑已关闭 (如果不关闭，您可以查看[Topology Basics for Skype for Business Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md)主题) ，是时候考虑服务器了。 Skype for Business Server 2015 服务器将需要 64 位硬件。 我们针对硬件的建议如下。 这些并非要求，但反映了实现最佳性能所需的要求。 我们具有容量规划文档，可帮助您确定是否需要超过此要求，具体取决于您的环境。
  
前端服务器、后端服务器、Standard Edition服务器和持久聊天服务器的推荐硬件：
  
|**硬件组件**|**建议**|
|:-----|:-----|
|CPU  <br/> |64 位双处理器、十六核、2.26 GHz (GHz) 或更高。  <br/> Intel Itanium 处理器不受 Skype for Business Server 2015 角色支持。  <br/> |
|内存  <br/> |32 GB (GB) 。  <br/> |
|磁盘  <br/> |任一：  <br/> • 具有至少 72 GB 可用磁盘空间的 8 个或多个 10000 RPM 硬盘驱动器 (两个磁盘使用 RAID 1，6 个磁盘使用 RAID 10) 。  <br/> 或  <br/> • 固态硬盘 (SSD) 提供与 8 个 10000 RPM 机械磁盘驱动器相同的可用空间和类似性能。  <br/> |
|网络  <br/> |1 个双端口网络适配器，1 Gbps 或更高 (2 个网络适配器，但它们需要与一个 MAC 地址和一个 IP 地址) 。  <br/> 前端服务器、后端服务器、Standard Edition服务器和持久聊天服务器不支持双主或多主配置。 <br/> 只要它们未向操作系统公开并且用于监视和管理服务器硬件，就可以拥有带外管理系统，如 DRAC 或 BAND。 此方案不构成多主服务器，并且受支持。  <br/> |
   
边缘服务器、独立中介服务器、视频互操作服务器和控制器的建议硬件：
  
|**硬件组件**|**建议**|
|:-----|:-----|
|CPU  <br/> |64 位双处理器、四核、2.26 GHz (GHz) 或更高。  <br/> Intel Itanium 处理器不受 Skype for Business Server 2015 角色支持。  <br/> |
|内存  <br/> |16 GB。  <br/> |
|磁盘  <br/> |任一：  <br/> • 具有至少 72 GB 可用磁盘空间的 4 个或多个 10000 RPM 硬盘驱动器 (磁盘应处于 2x RAID 1 配置) 。  <br/> 或  <br/> • 固态硬盘 (SSD) 提供与 4 个 10000 RPM 机械磁盘驱动器相同的可用空间和类似性能。  <br/> |
|网络  <br/> |1 个双端口网络适配器，1 Gbps 或更高 (2 个网络适配器，但它们需要与一个 MAC 地址和一个 IP 地址) 。  <br/> 视频互操作服务器 **和控制器不支持** 双主或多主配置。 <br/> 边缘服务器需要两个网络接口，即两个双端口网络适配器（1 Gbps 或更高 (）或两个成对网络适配器，总共 4 个，每个对与一个 MAC 地址和一个 IP 地址组合在一起，总共两对) 。  <br/> 在独立中介服务器上，支持安装其他网络接口 (NIC) 允许配置特定的 PSTN IP 地址。  <br/> |
   
## <a name="operating-systems-for-skype-for-business-server-2015"></a>Skype for Business Server 2015 的操作系统
<a name="OS"> </a>

在硬件就位后，你需要在操作系统安装 (操作系统) 。 这些操作系统将允许你安装并成功使用 Skype for Business Server 2015。
  
|&nbsp;|&nbsp;|
|:-----|:-----|
|WindowsServer 2019 (需要Skype for Business累积更新 9 或更高版本) 。 <br/> |Windows Server 2016 (需要Skype for Business累积更新 5 或更高版本。 有关详细信息，请查看[KB4015888) ](https://support.microsoft.com/help/4015888/how-to-install-skype-for-business-server-2015-on-windows-server-2016)  <br/> ||
|Windows Server 2012安装了所有必需更新的 R2 Datacenter OS。  <br/> |Windows Server 2012R2 已安装所有所需更新的标准操作系统。  <br/> |
|Windows Server 2012 Datacenter安装了所有必需更新的操作系统。  <br/> |Windows Server 2012 Standard安装了所有必需更新的操作系统。  <br/> |
   
如果未在此列表上，它将无法正常工作，请不要在 2015 年 10 月的新安装中Skype for Business Server它。

> [!NOTE]
> Lync Server 2013 不支持操作系统的就地升级。 您必须部署单独的池，并使用不同的操作系统将用户迁移到新池。 池中的所有服务器必须具有相同的操作系统版本。
  
> [!NOTE]
> 你可能已经注意到Windows Server 2008 R2 不在此列表上。 这是因为我们建议将 Windows Server 2012 R2 用于 SFB 的所有新服务器。 只有在已经安装了 Lync Server 2013 的现有服务器，并且打算就地升级它们时，才应该使用 Windows Server 2008 R2。 Windows服务器 2008 R2 于 2015 年 1 月 13 日结束主流支持生命周期，并将于 2020 年 1 月 14 日结束其支持生命周期。
  
除了最新的 Service Pack 之外，你还希望确保在与自己相关的位置安装以下更新：
  
- 例如Windows Server 2012，应在2858668之前安装知识库文章。 [在此处获取](https://support.microsoft.com/kb/2858668/)。
    
- 如果您拥有 Windows Server 2012 R2，请在升级之前2982006知识库文章。 [它在此处找到](https://support.microsoft.com/kb/2982006/)。
    
- 如果要在 Windows Server 2008 R2 框中进行升级 (请参阅上面的) 注释，则首先需要安装知识库2533623文章。 [它位于此链接](https://support.microsoft.com/kb/2533623/)。
    
## <a name="back-end-databases-that-will-work-with-skype-for-business-server-2015"></a>与 2015 Skype for Business Server数据库
<a name="DBs"> </a>


安装 Skype for Business Server 2015 Standard Edition 时，也会自动安装 SQL Server 2014 Express (64 位) 。
  
Skype for Business Server 2015 Enterprise Edition更复杂一些，但受支持的列表位于 (所有内容都是 64 位版本，你会注意到，请不要使用 32 位版本) ：
  
|&nbsp;|&nbsp;|&nbsp;|&nbsp;|&nbsp;|
|:-----|:-----|:-----|:-----|:-----|
|Microsoft SQL Server 2019 Enterprise (64 位) ，建议运行最新 Service Pack。 <br/> |Microsoft SQL Server 2017 Enterprise (64 位) ，建议运行最新 Service Pack。 <br/> |Microsoft SQL Server 2016 Enterprise (64 位版本) Service Pack 1 或更高版本，并且必须运行 Skype for Business 累积更新 7 或更高版本 (下载 Skype for Business[累积](https://support.microsoft.com/help/3061064)更新) 。  <br/> |Microsoft SQL Server 2014 Enterprise (64 位版本) ，并且必须运行累积更新 6 或更高版本 (下载累积更新[6](https://support.microsoft.com/kb/3031047/)) 。  <br/> |Microsoft SQL Server 2012 Enterprise (64 位) ，建议运行最新 Service Pack。  <br/> |
|Microsoft SQL Server 2019 Standard (64 位) ，建议运行最新 Service Pack。 <br/> |Microsoft SQL Server 2017 Standard (64 位) ，建议运行最新 Service Pack。 <br/> |Microsoft SQL Server 2016 Standard (64 位版本) Service Pack 1 或更高版本，并且必须通过 Skype for Business 累积更新 7 或更高版本运行 ([下载 Skype for Business 累积](https://support.microsoft.com/help/3061064)更新) 。  <br/> |Microsoft SQL Server 2014 Standard (64 位版本) ，并且必须运行累积更新 6 或更高版本 (下载累积更新[6](https://support.microsoft.com/kb/3031047/)) 。  <br/> |Microsoft SQL Server 2012 Standard (64 位) ，建议运行最新 Service Pack。  <br/> |
   
如果你在此处未SQL Server想要使用的版本，则你无法使用它。
  
- 您还需要安装监控服务器SQL Server Reporting Services角色的证书。
- 对于连接良好的SQL后端，与前端的连接Skype for Business应为本地连接，而不是通过低速链接。 
- 不支持SQL池之间的后端共享。

### <a name="microsoft-exchange-storage"></a>Microsoft Exchange 存储
会议内容文件（如 PowerPoint 演示文稿）将作为附件存档。 如果要将 Skype for Business 存档数据与 Exchange 合规性数据一起存储，则必须对 Exchange 部署使用 Exchange，并确保最大存储大小支持存储会议内容文件。 在使用 Microsoft Exchange集成选项部署和启用存档之前，Exchange部署存档。 
    
如果您选择使用Exchange存储，则无需部署单独的 SQL Server 数据库进行存档，除非您有 Skype for Business 用户未位于 Exchange 服务器上。 如果使用 Microsoft Exchange 集成选项部署存档，Skype for Business存档数据仅与 Exchange 合规性数据存储在一起，供您的 Exchange 用户使用。 
  
## <a name="hardware-and-software-requirements-for-archiving-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 中存档的硬件和软件要求
  
存档不是定义的服务器角色，无需安装单独的存档服务器。 统一数据收集代理在前端池和每个 Enterprise Edition 服务器上自动安装并Standard Edition代理。 您需要使用拓扑生成器启用和发布存档拓扑。
    
存档使用Skype for Business Server文件存储来临时存储会议内容文件，因此不要为存档设置单独的文件存储。
    
不需要 Microsoft 消息队列。
    
您需要设置存档存储的基础结构。 这包括选择Exchange存档存储或SQL Server。   Skype for Business Server存档基础结构要求与部署存档基础结构Skype for Business Server。 有关详细信息，请参阅[环境Skype for Business要求](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md)。 
  
> [!NOTE]
> 若要支持未位于 Exchange 服务器的用户，或者如果您不想使用 Microsoft Exchange 集成选项，则必须使用 64 位 SQL Server 数据库部署存档存储。 
    
在部署和启用SQL Server之前，必须设置存档平台。 如果用于发布拓扑的帐户具有适当的管理员权限，则可在发布拓扑时创建存档数据库 (LcsLog)。 您还可以稍后创建数据库，该数据库包含在安装过程中。 有关此SQL Server的详细信息，请参阅SQL Server[文档](/sql/sql-server/)。
    
存档的负载可能会显著增加。 因此，应确保磁盘空间足以供启用存档的前端服务器使用。

### <a name="sql-mirroring-sql-clustering-and-sql-always-on"></a>SQL镜像、SQL群集和SQL始终打开

支持将SQL镜像SQL 2015 Skype for Business Server群集。 SQL通过拓扑生成器设置Skype for Business Server镜像。 如果你打算设置群集SQL，则使用 SQL Server。
  
确保你拥有用于群集的主动/SQL配置，因为这是受支持的配置。 不要与任何其他被动实例共享被动SQL实例。
  
你可以将以下内容用于故障转移群集：
  
双节点：
  
- Microsoft SQL Server 2019 Standard (64 位) ，建议运行最新 Service Pack。

- Microsoft SQL Server 2017 Standard (64 位) ，建议运行最新 Service Pack。

- Microsoft SQL Server 2016 Standard (Service Pack 1) 更高版本的 64 位版本。 我们建议使用最新的 Service Pack 运行。

- Microsoft SQL Server 2014 Standard (64 位) ，建议运行最新 Service Pack。
    
-  Microsoft SQL Server 2012 Standard (64 位) ，建议运行最新 Service Pack。

16 节点：

- Microsoft SQL Server 2019 Enterprise (64 位) ，建议运行最新 Service Pack。

- Microsoft SQL Server 2017 Enterprise (64 位) ，建议运行最新 Service Pack。

- Microsoft SQL Server 2016 Enterprise (Service Pack 1) 64 位版本。 我们建议使用最新的 Service Pack 运行。
  
- Microsoft SQL Server 2014 Enterprise (64 位) ，建议运行最新 Service Pack。
    
- Microsoft SQL Server 2012 Enterprise (64 位) ，建议运行最新 Service Pack。

> [!IMPORTANT]
> 对于升级，我们希望您确保在升级之前在前端服务器上至少安装了 SQL Server 2012 SP1。 [如果您要立即下载](https://www.microsoft.com/download/details.aspx?id=35575) SP1，请在此处查看此链接。
  
如果您需要阅读有关镜像的详细信息SQL，我们在 Skype for Business Server 2015 主题中具有后端服务器高可用性。 Configure SQL Server clustering for Skype for Business Server 2015 具有准备群集的步骤。 对于[2014、2012 和 2008，SQL](/sql/sql-server/failover-clusters/install/sql-server-failover-cluster-installation)故障转移群集上也有其他[链接](/previous-versions/sql/sql-server-2008-r2/ms189134(v=sql.105))。 [](/previous-versions/sql/sql-server-2012/hh231721(v=sql.110))
  
> [!NOTE]
> 2015 发行版的新增功能是支持 SQL Always On。 它受支持，您可以在 Back [End Server high availability in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md)主题中阅读有关它的详细信息。

> [!NOTE]
> SQL镜像在 Skype for Business Server 2015 中可用，但在 Skype for Business Server 2019 中不再受支持。 AlwaysOn 可用性组、AlwaysOn 故障转移群集实例 (FCI) 和 SQL 故障转移群集方法在 Skype for Business Server 2019 中Skype for Business Server首选。  

## <a name="software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment"></a>应在部署 2015 年 Skype for Business Server之前安装的软件
<a name="Software"> </a>

你需要为运行 Skype for Business Server 2015 的任何服务器安装或配置一些内容，如下所示。 之后是特定服务器角色的其他要求。

  
 **所有服务器：**
  
|**软件/角色**|**Details**|
|:-----|:-----|
|Windows PowerShell 3.0  <br/> |所有Skype for Business Server服务器都需要Windows PowerShell 3.0。  <br/> • 如果在 R2 或 R2 Windows Server 2012 Windows Server 2012安装，则已设置，因为它已存在。  <br/> • 如果要在 Windows Server 2008 R2 上执行升级，可以下载 Windows Management Framework [3.0](https://www.microsoft.com/download/details.aspx?id=34595)获取它。 <br/> **提示：** 一旦拥有正确的 PowerShell，请通过进入 PowerShell 提示符并键入 ，确认它是 BuildVersion 6.2.9200.0 或更高版本 `$PSVersionTable` 。 这应该会显示你需要的信息。  <br/> |
|Microsoft .NET Framework  <br/> |WCF **服务是服务器** 管理器下作为一项Windows功能安装的功能，无需下载。  <br/> • 在安装此功能时，或如果已安装此功能并且正在检查它，您需要确保还选中并安装了 **HTTP** 激活选项，如下所示： <br/> ![Screenshot showing HTTP Activation option under the .NET Framework 4.5 Features. ](../../media/a4064fa0-fa49-4474-bd98-b9a79ff68f8b.png)如果收到其他弹出消息，指出需要安装其他一些内容才能安装 HTTP 激活，请不要担心。 这是正常情况，单击"确定"，然后继续操作。 如果未显示此弹出窗口，则假定已安装了上述内容，然后继续操作。  <br/> 安装 .NET Framework R2 Windows Server 2012安装 Microsoft Windows Server 2016。 Skype for Business Server适用于以下 Microsoft .NET Framework版本：  <br/> • .NET 3.5  <br/> • .NET 4.5  <br/> • .NET 4.6.x  <br/> • 适用于 (CU 5 Skype for Business Server更高版本的 .NET 4.7.1)   <br/> • 适用于 (CU 6 Skype for Business Server更高版本的 .NET 4.7.2)   <br/>  • 适用于 (CU 9 Skype for Business Server更高版本的 .NET 4.8)  <br/>  .NET Framework 3.5 可能会默认安装在 Windows Server 2008 R2 计算机上 (在升级) 之前请务必检查以确保，但实际上它不会在 Windows Server 2012/Windows Server 2012 R2 服务器上 (用于新安装) 。 若要添加它，你需要访问安装驱动器或媒体 (安装 Windows Server 的位置，或安装文件现已) 。 然后继续作为服务器管理器中的一项功能安装它，并指向安装媒体 (特别是 **\sources\sxs** 文件夹) 在系统要求时，继续安装它。 <br/> |
|Media Foundation  <br/> |For Windows Server 2016， Windows Server 2012 and Windows Server 2012 R2 the Windows Media Format Runtime installs with Microsoft Media Foundation.  <br/> 用于会议的所有前端服务器和 Standard Edition 服务器都需要 Windows Media Format Runtime 来运行呼叫库、通知和响应组应用程序播放通知和音乐的 Windows Media Audio (.wma) 文件。  <br/> |
|Windows Identity Foundation  <br/> |我们需要使用 Windows Identity Foundation 3.5 来支持 Skype for Business Server 2015 的服务器到服务器身份验证方案。  <br/> • Windows Server 2012 Windows Server 2012 R2，无需下载任何内容。 打开 **服务器管理器**，然后转到添加 **角色和功能向导**。 **Windows Identity Foundation 3.5"** 列于"功能 **"** 部分下。 如果已选中，则没有问题。 否则，请选择它并单击"下一步"以到达 **"安装"** 按钮。 <br/> |
|远程服务器管理工具  <br/> |角色管理工具：AD DS 和 AD LDS 工具  <br/> |
   
 **前端服务器和Standard Edition服务器还需要：**
  
|**软件/角色**|**Details**|
|:-----|:-----|
|Internet Information Services (IIS)  <br/> |选择以下模块后，所有前端服务器以及所有 Standard Edition 服务器都需要 IIS：  <br/> • 常见的 HTTP 功能：默认文档、HTTP 错误、静态内容  <br/> • 运行状况和诊断：HTTP 日志记录、日志记录工具、跟踪  <br/> • 性能：静态内容压缩、动态内容压缩  <br/> • 安全性：请求筛选、客户端证书映射身份验证Windows身份验证  <br/> • 应用程序开发：.NET Extensibility 3.5、.NET Extensibility 4.5、ASP.NET 3.5、ASP.NET 4.5、ISAPI 扩展、ISAPI 筛选器  <br/> • 管理工具：IIS 管理控制台、IIS 管理脚本和工具  <br/> 我们还应注意，还需要匿名访问，但您可以在安装 IIS 时获得此权限，因此在列表中没有选择它的位置。  <br/> |
|Windows Media Format Runtime  <br/> | 对于 Windows Server 2016、Windows Server 2012 和 Windows Server 2012 R2，你需要在服务器管理器 中安装 **媒体****基础功能**。 现在，您实际上无需此安装即可启动 Skype for Business Server 2015 安装，但系统会提示您安装它，然后在继续安装 Skype for Business Server 2015 之前重新启动服务器。 最好提前完成。 <br/> |
|Silverlight  <br/> |你可以在此链接中安装最新版本的[Silverlight。](https://www.microsoft.com/silverlight/)  <br/> |
   
> [!NOTE] 
> 如果使用的是负载平衡器，可能还需要启用目录浏览。 否则，将加载一个空白页，负载平衡器可能会认为该页失败。 

为了帮助你完成此操作，可以运行下面的 PowerShell 脚本示例来自动执行此操作：

```PowerShell
Add-WindowsFeature NET-Framework-Core, RSAT-ADDS, Windows-Identity-Foundation, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Dir-Browsing, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, BITS, Desktop-Experience, Telnet-Client
```

> [!NOTE] 
> 该命令按特定顺序查找源文件。 如果联机，该命令将访问 Windows Update。 但是，如果您处于脱机状态，则需要确保源文件对命令可用。 有关使用 PowerShell 安装角色和功能的信息，请参阅安装或[](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831809(v=ws.11))卸载角色、角色服务或功能 不要忘记在安装必备组件后再次运行 Windows Update，即使使用 PowerShell 命令。

 **控制器还需要：**
  
IIS，已选择以下模块：
  
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
    
 (如果想知道，此模块集与前端服务器和 Standard Edition 服务器相同，而动态内容压缩和管理工具将) 
  
我们在下面也具有一些 PowerShell 代码：
  
```PowerShell
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Scripting-Tools, Web-Mgmt-Compat, Desktop-Experience, Telnet-Client
```

 **持久聊天服务器还需要：**
  
消息队列，也称为 MSMQ。 它是一个Windows服务器组件，您可以在服务器管理器的"功能"部分下安装它。 如果要阅读有关此内容的信息，请参阅安装 [和管理消息队列](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc771474(v=ws.11))。
  
 **最后一些想法：**
  
请不要在任何前端服务器或独立中介服务器上安装任何 Microsoft Internet Security and Acceleration (ISA) Server 客户端软件，或其他任何 Winsock 分层服务提供商 (LSP) 软件 (任何第三方防火墙或防病毒网络检查软件将包含在此处) 中。 安装该软件时，可以看到较差的媒体流量性能。
