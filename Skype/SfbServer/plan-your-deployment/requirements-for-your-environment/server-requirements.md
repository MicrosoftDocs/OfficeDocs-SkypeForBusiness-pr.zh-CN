---
title: Skype for Business Server 2015 的服务器要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 8d47b242-b93d-4c2e-a658-23b78bca30b1
description: '摘要: 准备本主题的 Skype for business Server 2015 服务器。 硬件、操作系统、数据库、软件、所有系统要求和建议均可用于帮助确保成功安装和部署你的服务器场。'
ms.openlocfilehash: 74b1a26f38a0055c8222b980754106011a86ce34
ms.sourcegitcommit: 7d85a6784a21aec20dcaddd8940ffe95d532c2f4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/22/2019
ms.locfileid: "35134259"
---
# <a name="server-requirements-for-skype-for-business-server-2015"></a>Server requirements for Skype for Business Server 2015
 
**摘要：** 利用本主题准备 Skype for Business Server 2015 服务器。这里提供了硬件、OS、数据库、软件、所有系统要求和建议，可帮助确保服务器场的安装和部署获得成功。

如果你要查找环境要求 (如 Active Directory、DNS 或证书), 可以查看[Skype for Business Server 2015 文档的环境要求](environmental-requirements.md)。
  
正如你所料, 开始部署 Skype for Business Server 2015 之前, 需要做一些准备。 本文将指导你制定以下规划：
  
- [适用于 Skype for Business Server 2015 的硬件](server-requirements.md#Hardware)
  
- [Skype for business Server 2015 的操作系统](server-requirements.md#OS)
  
- [将与 Skype for Business Server 2015 配合工作的后端数据库](server-requirements.md#DBs)
  
- [应在 Skype for Business Server 2015 部署之前安装的软件](server-requirements.md#Software)
  
## <a name="hardware-for-skype-for-business-server-2015"></a>适用于 Skype for Business Server 2015 的硬件
<a name="Hardware"> </a>

既然你已将拓扑下移 (如果不是, 你可以查看[Skype for Business Server 2015 主题的拓扑基础知识](../../plan-your-deployment/topology-basics/topology-basics.md)), 就可以思考一下服务器。 Skype for business 服务器2015服务器将需要64位硬件。 下面给出了我们的硬件建议。 这些不是要求, 但它们反映了最佳性能所需的要求。 我们的容量规划文档可帮助你根据自己的环境确定是否需要高于此要求的配置。
  
适用于前端服务器、后端服务器、标准版服务器和持久聊天服务器的推荐硬件:
  
|**硬件组件**|**推荐**|
|:-----|:-----|
|CPU  <br/> |64 位双处理器、六核、2.26 GHz 或更快。  <br/> Skype for business Server 2015 角色不支持英特尔安腾处理器。  <br/> |
|内存  <br/> |32 GB。  <br/> |
|磁盘  <br/> |以下之一：  <br/> •8个或更多 10000 RPM 硬盘, 至少有 72 GB 的可用磁盘空间 (使用 RAID 1 和6的两个磁盘使用 RAID 10)。  <br/> 或者  <br/> •固态硬盘 (SSDs) 能够为 8 10000 RPM 机械磁盘驱动器提供同样的可用空间和类似的性能。  <br/> |
|网络  <br/> |1 个双端口网络适配器，1 Gbps 或更高（可使用 2 个网络适配器，但需要通过一个 MAC 地址和一个 IP 地址配合使用）。  <br/> 前端服务器、后端服务器、标准版服务器和持久聊天服务器**不**支持双重或多穴配置。 <br/> 只要它们不接触操作系统并且被用于监控和管理服务器硬件，你就能够拥有带外管理系统，如 DRAC 或 ILO。这种情况不会形成多宿主服务器，并且受支持。<br/> |
   
适用于 Edge 服务器、独立中介服务器、视频互操作服务器和控制器的推荐硬件:
  
|**硬件组件**|**推荐**|
|:-----|:-----|
|CPU  <br/> |64 位双处理器、四核、2.26 GHz 或更快。  <br/> Skype for business Server 2015 角色不支持英特尔安腾处理器。  <br/> |
|内存  <br/> |16 GB。  <br/> |
|磁盘  <br/> |以下之一：  <br/> •4个或更多 10000 RPM 硬盘, 至少有 72 GB 的可用磁盘空间 (磁盘应位于 2x RAID 1 配置中)。  <br/> 或者  <br/> •固态硬盘 (SSDs) 能够为 4 10000 RPM 机械磁盘驱动器提供同样的可用空间和类似的性能。  <br/> |
|网络  <br/> |1 个双端口网络适配器，1 Gbps 或更高（可使用 2 个网络适配器，但需要通过一个 MAC 地址和一个 IP 地址配合使用）。  <br/> 视频互操作服务器和控制器**不**支持双重或多穴配置。 <br/> 边缘服务器需要两个网络接口，均为双端口网络适配器、1 Gbps 或更高速度（或两个成对网络适配器，总计 4 个适配器，每一对均与单一 MAC 地址和单一 IP 地址配合使用，总共两对）。  <br/> 在独立中介服务器上, 支持安装其他网络接口卡 (Nic) 以允许配置特定的 PSTN IP 地址。  <br/> |
   
## <a name="operating-systems-for-skype-for-business-server-2015"></a>Skype for business Server 2015 的操作系统
<a name="OS"> </a>

硬件准备好后, 您需要安装操作系统 (OS)。 这些操作系统将允许你安装并成功使用 Skype for Business Server 2015。
  
|||
|:-----|:-----|
|Windows Server 2019 (需要 Skype for Business 累积更新9或更高版本)。 <br/> |Windows Server 2016 (需要 Skype for Business 累积更新5或更高版本。 有关详细信息, 请检查[KB4015888](https://support.microsoft.com/en-gb/help/4015888/how-to-install-skype-for-business-server-2015-on-windows-server-2016)  <br/> ||
|Windows Server 2012 R2 Datacenter OS 已安装所有必需的更新。  <br/> |Windows Server 2012 R2 标准操作系统安装了所有必需的更新。  <br/> |
|Windows Server 2012 Datacenter OS 已安装所有必需的更新。  <br/> |Windows Server 2012 标准操作系统安装了所有必需的更新。  <br/> |
   
如果它不在此列表中, 它将无法正常工作, 请不要尝试安装 Skype for business Server 2015 的新安装。
  
> [!NOTE]
> 你可能已注意到 Windows Server 2008 R2 不在此列表中。 这是因为我们建议将所有新服务器的 Windows Server 2012 R2 用于 SFB。 只有安装了安装了 Lync Server 2013 的现有服务器, 并且你想要执行它们的就地升级时, 才应使用 Windows Server 2008 R2。 Windows Server 2008 R2 已达到1/13/2015 上主流支持生命周期的结尾。 
  
除了最新的 Service Pack 外，您还应确保在相关的地方安装以下更新：
  
- 对于 Windows Server 2012，应首先安装知识库文章 2858668 提供的更新，然后再进行升级。 [在此处获取](https://support.microsoft.com/en-us/kb/2858668/)。
    
- 如果你拥有 Windows Server 2012 R2，请首先安装知识库文章 2982006 提供的更新，然后再进行升级。 [它位于此处](https://support.microsoft.com/en-us/kb/2982006/)。
    
- 如果你是在 Windows Server 2008 R2 机器上进行升级（参阅上述备注），则你应首先安装知识库文章 2533623 提供的更新。 [它在此链接](https://support.microsoft.com/en-us/kb/2533623/)中。
    
## <a name="back-end-databases-that-will-work-with-skype-for-business-server-2015"></a>将与 Skype for Business Server 2015 配合工作的后端数据库
<a name="DBs"> </a>

安装 Skype for Business Server 2015 标准版时, 将同时自动安装 SQL Server 2014 Express (64 位)。
  
Skype for Business Server 2015 企业版的版本稍有复杂, 但受支持的列表如下所示 (所有内容都是64位版本, 你会注意到, 请不要使用32位版本):
  
||||||
|:-----|:-----|:-----|:-----|:-----|
|Microsoft SQL Server 2019 企业版 (64 位版), 我们建议通过最新的服务包运行。 <br/> |Microsoft SQL Server 2017 企业版 (64 位版), 我们建议通过最新的服务包运行。 <br/> |Microsoft SQL Server 2016 Enterprise (64 位版) Service Pack 1 或更高版本, 必须运行 Skype for Business 累积更新7或更高版本 ([下载 skype for Business 累积更新](https://support.microsoft.com/en-us/help/3061064))。  <br/> |Microsoft SQL Server 2014 企业版 (64 位版), 必须运行累积更新6或更高版本 ([下载累积更新 6](https://support.microsoft.com/en-us/kb/3031047/))。  <br/> |Microsoft SQL Server 2012 企业版 (64 位版), 我们建议通过最新的服务包运行。  <br/> |
|Microsoft SQL Server 2019 标准版 (64 位版), 我们建议通过最新的 service pack 运行。 <br/> |Microsoft SQL Server 2017 标准版 (64 位版), 我们建议通过最新的 service pack 运行。 <br/> |Microsoft SQL Server 2016 标准版 (64 位版) Service Pack 1 或更高版本, 必须运行 Skype for Business 累积更新7或更高版本 ([下载 skype for Business 累积更新](https://support.microsoft.com/en-us/help/3061064))。  <br/> |Microsoft SQL Server 2014 标准版 (64 位版), 必须运行累积更新6或更高版本 ([下载累积更新 6](https://support.microsoft.com/en-us/kb/3031047/))。  <br/> |Microsoft SQL Server 2012 标准版 (64 位版), 我们建议通过最新的 service pack 运行。  <br/> |
   
如果在此处看不到要使用的 SQL Server 版本, 则无法使用它。
  
> [!NOTE]
> 你还需要为监视服务器角色安装 SQL Server Reporting Services。

### <a name="microsoft-exchange-storage"></a>Microsoft Exchange 存储
Meeting content files, such as PowerPoint presentations, are archived as attachments. 如果要将 Skype for Business 存档数据与 Exchange 合规性数据一起存储, 则必须将 Exchange 用于 Exchange 部署, 并确保最大存储空间支持存储会议内容文件。 必须先部署 Exchange, 然后才能使用 Microsoft Exchange 集成选项部署和启用存档。 
    
    If you choose to use Exchange storage, you do not need to deploy separate SQL Server databases for archiving, unless you have Skype for Business users who are not homed on your Exchange servers. If you deploy archiving using the Microsoft Exchange integration option, Skype for Business archive data is stored with Exchange compliance data only for the users who are homed on your Exchange servers. 
  
## <a name="hardware-and-software-requirements-for-archiving-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 中的存档的硬件和软件要求
  
存档不是已定义的服务器角色, 无需安装单独的服务器进行存档。 统一数据收集代理在每个企业版前端池和每个标准版服务器上自动安装和激活。 您需要使用拓扑生成器启用和发布存档拓扑。
    
存档使用 Skype for Business 服务器文件存储来临时存储会议内容文件, 因此不会为存档设置单独的文件存储。
    
不需要 Microsoft 消息队列。
    
您需要为存档存储设置基础结构。 这包括使用 SQL Server 选择 "Exchange" 或 "存档" 存储。   Skype for business 服务器存档基础结构要求与部署 Skype for Business 服务器的要求相同。 有关详细信息, 请参阅[Skype for business 环境的要求](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md)。 
  
> [!NOTE]
> 若要支持未托管在 Exchange 服务器上的用户, 或者如果你不想使用 Microsoft Exchange 集成选项, 则必须使用64位 SQL Server 数据库部署存档存储。 
    
在部署和启用存档之前, 必须设置 SQL Server 平台。 如果用于发布拓扑的帐户具有适当的管理员权限，则可在发布拓扑时创建存档数据库 (LcsLog)。 您稍后还可创建数据库（包括在安装过程中）。 有关 SQL Server 的详细信息, 请参阅[Sql server 文档](https://go.microsoft.com/fwlink/p/?linkID=129045)。
    
存档带来的负载提升可能非常显著。 因此, 你应该确保磁盘空间足以满足启用了存档的前端服务器的需要。

### <a name="sql-mirroring-sql-clustering-and-sql-always-on"></a>SQL 镜像、SQL 群集和 SQL Always On

你可以将 SQL 镜像或 SQL 群集与 Skype for Business Server 2015 结合使用, 这是受支持的。 通过 Skype for Business 服务器拓扑生成器设置 SQL 镜像。 如果你打算设置 SQL 群集, 则会在 SQL Server 中完成。
  
请确保你拥有 SQL 群集的主动/被动配置, 因为这是支持的是新增。 不要与任何其他 SQL 实例共享被动节点。
  
可以为故障转移群集采用以下配置：
  
双节点：
  
- Microsoft SQL Server 2019 标准版 (64 位版), 我们建议通过最新的 service pack 运行。

- Microsoft SQL Server 2017 标准版 (64 位版), 我们建议通过最新的 service pack 运行。

- Microsoft SQL Server 2016 标准版 (64 位版) Service Pack 1 或更高版本。 我们建议通过最新的服务包运行。

- Microsoft SQL Server 2014 标准版 (64 位版), 我们建议通过最新的 service pack 运行。
    
-  Microsoft SQL Server 2012 标准版 (64 位版), 我们建议通过最新的 service pack 运行。

16 节点：

- Microsoft SQL Server 2019 企业版 (64 位版), 我们建议通过最新的服务包运行。

- Microsoft SQL Server 2017 企业版 (64 位版), 我们建议通过最新的服务包运行。

- Microsoft SQL Server 2016 企业版 (64 位版) Service Pack 1 或更高版本。 我们建议通过最新的服务包运行。
  
- Microsoft SQL Server 2014 企业版 (64 位版), 我们建议通过最新的服务包运行。
    
- Microsoft SQL Server 2012 企业版 (64 位版), 我们建议通过最新的服务包运行。

> [!IMPORTANT]
> 对于升级, 我们确实希望你在前端服务器上确保在升级前至少安装 SQL Server 2012 SP1。 [下面是一个](https://www.microsoft.com/en-us/download/details.aspx?id=35575)指向 SP1 的链接 (如果要立即下载)。
  
如果需要阅读有关 SQL 镜像的详细信息, 我们在 Skype for Business Server 2015 主题中提供了后端服务器高可用性。 配置 Skype for business Server 2015 的 SQL Server 群集是否具有准备好群集的步骤。 对于[2014](https://technet.microsoft.com/en-us/library/hh231721.aspx)、 [2012](https://technet.microsoft.com/en-us/library/hh231721%28v=sql.110%29.aspx)和[2008](https://technet.microsoft.com/en-us/library/ms189134%28v=sql.105%29.aspx), 还有针对 SQL 的故障转移群集的进一步链接。
  
> [!NOTE]
> 2015版本的新增功能是支持 SQL Always On。 它受支持, 你可以在[Skype for Business server 2015 主题的后端服务器高可用性](../../plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md)中阅读更多相关信息。

> [!NOTE]
> 在 Skype for business Server 2015 中提供了 SQL 镜像, 但 Skype for Business Server 2019 不再支持 SQL 镜像。 适用于 Skype for Business Server 2019 的 AlwaysOn 可用性组、AlwaysOn 故障转移群集实例 (FCI) 和 SQL 故障转移群集方法优先。  

## <a name="software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment"></a>应在 Skype for Business Server 2015 部署之前安装的软件
<a name="Software"> </a>

对于运行 Skype for Business Server 2015 的任何服务器, 你需要安装或配置一些操作, 如下所示。 满足这些条件后，还要满足特定服务器角色的额外要求。
  
 **所有服务器：**
  
|**软件/角色**|**详细信息**|
|:-----|:-----|
|Windows PowerShell 3.0  <br/> |所有 Skype for business 服务器服务器都需要安装 Windows PowerShell 3.0。  <br/> •如果你在 Windows Server 2012 或 Windows Server 2012 R2 上执行安装, 则你已设置, 因为它已经存在。  <br/> •如果你要在 Windows Server 2008 R2 上进行升级, 可以下载[Windows Management Framework 3.0](https://www.microsoft.com/en-us/download/details.aspx?id=34595)以获取它。 <br/> **提示:** 在该位置上安装了正确的 PowerShell 后, 请转到 PowerShell 提示和键入`$PSVersionTable`, 确认它 BuildVersion 6.2.9200.0 或更高版本。 这应该会弹出您需要的信息。  <br/> |
|Microsoft .NET Framework  <br/> |WCF 服务是作为 Windows 功能安装的**功能**, 在**服务器管理器**下, 无需下载。 <br/> •你需要确保在安装此功能时, 或者在已安装此功能且正在进行检查时, 也会检查和安装**HTTP 激活**选项, 如下所示: <br/> ![显示 .NET Framework 4.5 功能下的 HTTP 激活选项的屏幕截图。](../../media/a4064fa0-fa49-4474-bd98-b9a79ff68f8b.png)如果您收到一个额外的弹出窗口, 提示要安装 HTTP 激活, 则不要担心需要安装一些其他事项。 这种情况非常正常，只要单击“确定”，继续操作即可。 如果未看到此弹出信息，则可以假设这些功能均已安装，您可以继续操作。  <br/> Microsoft .NET Framework 通常在安装 Windows Server 2012 R2 或 Windows Server 2016 时安装。 Skype for business 服务器适用于以下 Microsoft .NET Framework 版本:  <br/> • .NET 3。5  <br/> • .NET 4。5  <br/> • .NET 4.6 x  <br/> • .NET 4.7.1 和更高版本 (适用于 Skype for business Server CU 5 或更高版本)  <br/>  默认情况下, .NET Framework 3.5 可能会安装在 Windows Server 2008 R2 计算机上 (明确检查升级之前), 但实际上不在 Windows Server 2012/Windows Server 2012 R2 服务器 (适用于新安装) 上。 若要在中添加它, 你需要访问安装驱动器或媒体 (安装 Windows Server 的位置或安装文件现在所在的位置)。 然后继续操作，并从服务器管理器将其作为功能进行安装，在提示时指向安装媒体（即 **\sources\sxs** 文件夹），然后继续安装。 <br/> |
|媒体基础  <br/> |对于 Windows Server 2016、Windows Server 2012 和 Windows Server 2012 R2 Windows Media 格式运行时与 Microsoft Media Foundation 一起安装。  <br/> 用于会议的所有前端服务器和标准版服务器都需要 Windows Media 格式运行时运行 Windows Media 音频 (.wma) 文件, 该文件中的 "呼叫驻留"、"通知" 和 "响应" 组应用程序将在公告和音乐中播放。  <br/> |
|Windows Identity Foundation  <br/> |我们需要 Windows Identity Foundation 3.5 以支持 Skype for business Server 2015 的服务器到服务器身份验证方案。  <br/> •适用于 Windows Server 2012 和 Windows Server 2012 R2, 无需下载任何内容。 打开**服务器管理器**，转到**添加角色和功能向导**。 **Windows Identity Foundation 3.5** 在**功能**部分列出。 如果已选中, 则您好! 否则请选中它，并单击“下一步”，然后单击**安装**按钮。 <br/> |
|远程服务器管理工具  <br/> |角色管理工具：AD DS 和 AD LDS 工具  <br/> |
   
 **前端服务器和标准版服务器还需要:**
  
|**软件/角色**|**详细信息**|
|:-----|:-----|
|Internet Information Services (IIS)  <br/> |在所有前端服务器以及所有标准版服务器上都需要 IIS, 并且选择了以下模块:  <br/> •常见的 HTTP 功能: 默认文档、HTTP 错误、静态内容  <br/> •运行状况和诊断: HTTP 日志记录、日志记录工具、跟踪  <br/> •性能: 静态内容压缩, 动态内容压缩  <br/> •安全: 请求筛选、客户端证书映射身份验证、Windows 身份验证  <br/> •应用程序开发: .NET 扩展性3.5、.NET 扩展性4.5、ASP.NET 3.5、ASP.NET 4.5、ISAPI 扩展、ISAPI 筛选器  <br/> •管理工具: IIS 管理控制台、IIS 管理脚本和工具  <br/> 我们还应注意, 还需要匿名访问, 但你可以在安装 IIS 时收到, 因此你没有在列表中选择的位置。  <br/> |
|Windows Media Format Runtime  <br/> | 对于 Windows Server 2016、Windows Server 2012 和 Windows Server 2012 R2, 你需要在**服务器管理器**中安装**Media Foundation**功能。 现在, 你实际上可以在没有此安装的情况下启动 Skype for business Server 2015 安装, 但在 Skype for business Server 2015 安装继续之前, 系统将提示你安装它, 然后重新启动服务器。 因此最好提前安装。 <br/> |
|Silverlight  <br/> |你可以在[此链接](https://www.microsoft.com/silverlight/)上安装最新版本的 Silverlight。  <br/> |
   
> [!NOTE] 
> 如果使用负载平衡器, 可能还需要启用目录浏览。 否则, 将加载一个空白页, 负载平衡器可能会考虑到失败。 

为帮助您了解相关过程，我们提供了一个示例 PowerShell 脚本，您可以运行此脚本以自动执行此流程：

```
Add-WindowsFeature NET-Framework-Core, RSAT-ADDS, Windows-Identity-Foundation, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Dir-Browsing, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, BITS, Desktop-Experience, Telnet-Client
```

> [!NOTE] 
> 该命令将按特定顺序查找源文件。 如果您处于联机状态，该命令可访问 Windows Update。 但是，如果您处于脱机状态，则需要确保源文件可被该命令使用。 有关使用 PowerShell 安装角色和功能的详细信息, 请参阅安装[或卸载角色、角色服务或功能](https://technet.microsoft.com/en-us/library/hh831809.aspx)不会忘记在安装必备组件后再次运行 Windows 更新, 即使使用 PowerShell 命令也是如此。

 **董事还需要:**
  
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
    
(如果您想知道, 它是与前端服务器和标准版服务器相同的模块, 可将动态内容压缩和管理工具留给。)
  
我们还为此提供了以下一些 PowerShell 代码：
  
```
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Scripting-Tools, Web-Mgmt-Compat, Desktop-Experience, Telnet-Client
```

 **持久聊天服务器还需要:**
  
消息队列，也称为 MSMQ。 它是 Windows Server 组件, 你可以在服务器管理器的 "功能" 部分中安装它。 若要阅读有关此操作的详细信息, 请参阅[安装和管理消息队列](https://technet.microsoft.com/en-us/library/cc771474.aspx)。
  
 **最后注意事项：**
  
请不要安装任何 Microsoft Internet 安全和加速 (ISA) 服务器客户端软件或任何其他 Winsock 分层服务提供商 (LSP) 软件 (此处包含任何第三方防火墙或防病毒网络检查软件)任何前端服务器或独立中介服务器。 在安装该软件时, 已发现较差的媒体流量性能。
  

