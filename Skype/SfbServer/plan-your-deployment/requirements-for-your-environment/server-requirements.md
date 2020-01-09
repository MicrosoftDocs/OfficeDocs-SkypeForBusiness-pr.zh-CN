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
description: 摘要：利用本主题准备 Skype for Business Server 2015 服务器。 硬件、操作系统、数据库、软件、所有系统要求和建议均可帮助确保服务器场的安装和部署获得成功。
ms.openlocfilehash: a028ce7265718c0ce14b103bca8dcdb416e72885
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2020
ms.locfileid: "40989277"
---
# <a name="server-requirements-for-skype-for-business-server-2015"></a>Skype for Business Server 2015 的服务器要求
 
**摘要：** 利用本主题准备 Skype for Business Server 2015 服务器。这里提供了硬件、OS、数据库、软件、所有系统要求和建议，可帮助确保服务器场的安装和部署获得成功。

如果要查找环境要求（例如 Active Directory、DNS 或证书），可查看 [Skype for Business Server 2015 的环境要求](environmental-requirements.md)文档。
  
正如你所料，开始部署 Skype for Business Server 2015 之前，需要做一些准备工作。 本文将指导你制定以下规划：
  
- [适用于 Skype for Business Server 2015 的硬件](server-requirements.md#Hardware)
  
- [适用于 Skype for Business Server 2015 的操作系统](server-requirements.md#OS)
  
- [将与 Skype for Business Server 2015 配合工作的后端数据库](server-requirements.md#DBs)
  
- [应在 Skype for Business Server 2015 部署之前安装的软件](server-requirements.md#Software)
  
## <a name="hardware-for-skype-for-business-server-2015"></a>适用于 Skype for Business Server 2015 的硬件
<a name="Hardware"> </a>

在关闭拓扑后（如果还没有，请参阅 [Skype for Business Server 2015 的拓扑基础知识](../../plan-your-deployment/topology-basics/topology-basics.md)主题），下面就该考虑服务器了。 Skype for Business Server 2015 服务器需要 64 位硬件。 下面是针对硬件的建议。 这些并非强制要求，但它反映了实现最优性能所需要满足的要求。 我们提供了容量规划文档，可帮助你根据自身情况确定是否需要更多容量。
  
前端服务器、后端服务器、Standard Edition 服务器和持久聊天服务器的推荐硬件：
  
|**硬件组件**|**推荐**|
|:-----|:-----|
|CPU  <br/> |64 位双处理器、六核、2.26 GHz 或更快。  <br/> Skype for Business Server 2015 角色不支持 Intel Itanium 处理器。  <br/> |
|内存  <br/> |32 GB。  <br/> |
|磁盘  <br/> |以下之一：  <br/> • 8 块或更多 10000 RPM 硬盘，至少 72 GB 可用磁盘空间（2 块磁盘使用 RAID 1，6 块磁盘使用 RAID 10）。  <br/> 或  <br/> • 能够提供与 8 块 10000 RPM 机械硬盘相同的可用空间和类似性能的固态硬盘 (SSD)。  <br/> |
|网络  <br/> |1 个双端口网络适配器，1 Gbps 或更高（可使用 2 个网络适配器，但需要通过一个 MAC 地址和一个 IP 地址配合使用）。  <br/> 前端服务器、后端服务器、Standard Edition 服务器和持久聊天服务器**不**支持双宿主或多宿主配置。 <br/> 只要它们不接触操作系统并且被用于监控和管理服务器硬件，你就能够拥有带外管理系统，如 DRAC 或 ILO。这种情况不会形成多宿主服务器，并且受支持。  <br/> |
   
边缘服务器、独立中介服务器、视频互操作服务器和控制器的推荐硬件：
  
|**硬件组件**|**推荐**|
|:-----|:-----|
|CPU  <br/> |64 位双处理器、四核、2.26 GHz 或更快。  <br/> Skype for Business Server 2015 角色不支持 Intel Itanium 处理器。  <br/> |
|内存  <br/> |16 GB。  <br/> |
|磁盘  <br/> |以下之一：  <br/> • 4 块或更多 10000 RPM 硬盘，至少 72 GB 可用磁盘空间（磁盘应采用双 RAID 1 配置）。  <br/> 或  <br/> • 能够提供与 4 块 10000 RPM 机械硬盘相同的可用空间和类似性能的固态硬盘 (SSD)。  <br/> |
|网络  <br/> |1 个双端口网络适配器，1 Gbps 或更高（可使用 2 个网络适配器，但需要通过一个 MAC 地址和一个 IP 地址配合使用）。  <br/> 视频互操作服务器和控制器**不**支持双宿主或多宿主配置。 <br/> 边缘服务器需要两个网络接口，均为双端口网络适配器、1 Gbps 或更高速度（或两个成对网络适配器，总计 4 个适配器，每一对均与单一 MAC 地址和单一 IP 地址配合使用，总共两对）。  <br/> 在独立中介服务器上，支持安装额外的网络接口卡 (NIC) 以允许配置特定的 PSTN IP 地址。  <br/> |
   
## <a name="operating-systems-for-skype-for-business-server-2015"></a>适用于 Skype for Business Server 2015 的操作系统
<a name="OS"> </a>

具备硬件之后，你需要安装操作系统 (OS)。 这些操作系统将允许你安装并成功使用 Skype for Business Server 2015。
  
|||
|:-----|:-----|
|Windows Server 2019（需要 Skype for Business 累积更新 9 或更高版本）。 <br/> |Windows Server 2016（需要 Skype for Business 累积更新 5 或更高版本。 有关详细信息，请查看 [KB4015888](https://support.microsoft.com/help/4015888/how-to-install-skype-for-business-server-2015-on-windows-server-2016)）  <br/> ||
|Windows Server 2012 R2 Datacenter OS，已安装所有必需的更新。  <br/> |Windows Server 2012 R2 Standard OS，已安装所有必需的更新。  <br/> |
|Windows Server 2012 Datacenter OS，已安装所有必需的更新。  <br/> |Windows Server 2012 Standard OS，已安装所有必需的更新。  <br/> |
   
如果操作系统不在此列表中，则不会正常运行，请勿对新安装的 Skype for Business Server 2015 进行尝试。
  
> [!NOTE]
> 你或许已经注意到，此列表中未包含 Windows Server 2008 R2。 因为我们建议为所有用于 SFB 的新服务器使用 Windows Server 2012 R2。 只有在现有服务器已经安装 Lync Server 2013，并且希望对其执行就地升级的情况下，才应使用 Windows Server 2008 R2。 Windows Server 2008 R2 已于 2015 年 1 月 13 日终止主流支持生命周期，并将于 2020 年 1 月 14 日终止支持生命周期。
  
除了最新的 Service Pack 外，您还应确保在相关的地方安装以下更新：
  
- 对于 Windows Server 2012，应首先安装知识库文章 2858668 提供的更新，然后再进行升级。 [可在此处获取](https://support.microsoft.com/kb/2858668/)。
    
- 如果使用的是 Windows Server 2012 R2，请首先安装知识库文章 2982006 提供的更新，然后再进行升级。 [可在此处查找](https://support.microsoft.com/kb/2982006/)。
    
- 如果是在 Windows Server 2008 R2 机器上进行升级（参阅上述备注），则应首先安装知识库文章 2533623 提供的更新。 [可通过此链接获取](https://support.microsoft.com/kb/2533623/)。
    
## <a name="back-end-databases-that-will-work-with-skype-for-business-server-2015"></a>将与 Skype for Business Server 2015 配合工作的后端数据库
<a name="DBs"> </a>


安装 Skype for Business Server 2015 Standard Edition 时，SQL Server 2014 Express（64 位版本）也将自动安装。
  
Skype for Business Server 2015 Enterprise Edition 略为复杂，但下方给出了支持列表（请注意，均为 64 位版，请勿使用 32 位版）：
  
||||||
|:-----|:-----|:-----|:-----|:-----|
|Microsoft SQL Server 2019 Enterprise（64 位版），建议运行最新 Service Pack。 <br/> |Microsoft SQL Server 2017 Enterprise（64 位版），建议运行最新 Service Pack。 <br/> |带有 Service Pack 1 或更高版本的 Microsoft SQL Server 2016 Enterprise（64 位版），并且必须运行 Skype for Business 累积更新 7 或更高版本（[下载 Skype for Business 累积更新](https://support.microsoft.com/help/3061064)）。  <br/> |Microsoft SQL Server 2014 Enterprise（64 位版），并且必须运行累积更新 6 或更高版本（[下载累积更新 6](https://support.microsoft.com/kb/3031047/)）。  <br/> |Microsoft SQL Server 2012 Enterprise（64 位版），建议运行最新 Service Pack。  <br/> |
|Microsoft SQL Server 2019 Standard（64 位版），建议运行最新 Service Pack。 <br/> |Microsoft SQL Server 2017 Standard（64 位版），建议运行最新 Service Pack。 <br/> |带有 Service Pack 1 或更高版本的 Microsoft SQL Server 2016 Standard（64 位版），并且必须运行 Skype for Business 累积更新 7 或更高版本（[下载 Skype for Business 累积更新](https://support.microsoft.com/help/3061064)）。  <br/> |Microsoft SQL Server 2014 Standard（64 位版），并且必须运行累积更新 6 或更高版本（[下载累积更新 6](https://support.microsoft.com/kb/3031047/)）。  <br/> |Microsoft SQL Server 2012 Standard（64 位版），建议运行最新 Service Pack。  <br/> |
   
如果你想使用的 SQL Server 版本未列于此处，则不能使用。
  
- 你还需要为“监控服务器”角色安装 SQL Server Reporting Services。
- 对于连接良好的 SQL 后端，与 Skype for Business 前端的连接应该是本地连接，而不是通过低速链路进行连接。 
- 不支持在两个或多个池之间共享 SQL 后端。

### <a name="microsoft-exchange-storage"></a>Microsoft Exchange 存储
会议内容文件（如 PowerPoint 演示文稿）将作为附件存档。 如果要将 Skype for Business 存档数据与 Exchange 合规性数据一起存储，则必须将 Exchange 用于 Exchange 部署，并确保最大存储空间支持会议内容文件的存储。 必须先部署 Exchange，然后才能使用 Exchange 集成选项部署和启用存档。 
    
    If you choose to use Exchange storage, you do not need to deploy separate SQL Server databases for archiving, unless you have Skype for Business users who are not homed on your Exchange servers. If you deploy archiving using the Microsoft Exchange integration option, Skype for Business archive data is stored with Exchange compliance data only for the users who are homed on your Exchange servers. 
  
## <a name="hardware-and-software-requirements-for-archiving-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 中的存档的硬件和软件要求
  
存档不是定义的服务器角色，无需安装单独的存档服务器。 在每个 Enterprise Edition 前端池和每个 Standard Edition 服务器上将自动安装和激活统一数据收集代理。 你需要使用拓扑生成器启用并发布存档拓扑。
    
存档使用 Skype for Business Server 文件存储来临时存储会议内容文件，因此你无需为存档设置单独的文件存储。
    
无需 Microsoft 消息队列。
    
你需要设置存档存储基础结构。 这包括选择“Exchange”或“使用 SQL Server 的存档存储”。   Skype for Business Server 的存档基础结构要求与 Skype for Business Server 的部署要求相同。 有关详细信息，请参阅 [Skype for Business 环境要求](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md)。 
  
> [!NOTE]
> 若要支持未托管在 Exchange 服务器上的用户，或者如果你不想使用 Microsoft Exchange 集成选项，则必须使用 64 位 SQL Server 数据库来部署存档存储。 
    
你必须先设置 SQL Server 平台，然后才能部署和启用存档。 如果用于发布拓扑的帐户具有适当的管理员权限，则可在发布拓扑时创建存档数据库 (LcsLog)。 也可以稍后创建数据库（包括在安装过程中）。 有关 SQL Server 的详细信息，请参阅 [SQL Server 文档](https://go.microsoft.com/fwlink/p/?linkID=129045)。
    
存档的负载增长可能非常显著。 因此，应确保磁盘空间足以容纳启用了存档的前端服务器。

### <a name="sql-mirroring-sql-clustering-and-sql-always-on"></a>SQL 镜像、SQL 群集和 SQL Always On

你可以将 SQL 镜像或 SQL 群集与 Skype for Business Server 2015 结合使用，这是支持的。 通过 Skype for Business Server 拓扑生成器设置 SQL 镜像。 如果要设置 SQL 群集，则应在 SQL Server 中进行。
  
确保为 SQL 群集提供主动/被动配置，因为只有此配置才受支持。 请勿与任何其他 SQL 实例共享被动节点。
  
可以为故障转移群集采用以下配置：
  
双节点：
  
- Microsoft SQL Server 2019 标准版（64 位版本），建议运行最新的 Service Pack。

- Microsoft SQL Server 2017 Standard（64 位版），建议运行最新 Service Pack。

- 带有 Service Pack 1 或更高版本的 Microsoft SQL Server 2016 Standard（64 位版）。 建议运行最新 Service Pack。

- Microsoft SQL Server 2014 Standard（64 位版），建议运行最新 Service Pack。
    
-  Microsoft SQL Server 2012 Standard（64 位版），建议运行最新 Service Pack。

16 节点：

- Microsoft SQL Server 2019 企业版（64 位版本），建议运行最新的 Service Pack。

- Microsoft SQL Server 2017 Enterprise（64 位版），建议运行最新 Service Pack。

- 带有 Service Pack 1 或更高版本的 Microsoft SQL Server 2016 Enterprise（64 位版）。 建议运行最新 Service Pack。
  
- Microsoft SQL Server 2014 Enterprise（64 位版），建议运行最新 Service Pack。
    
- Microsoft SQL Server 2012 Enterprise（64 位版），建议运行最新 Service Pack。

> [!IMPORTANT]
> 对于升级，我们希望你在进行升级前确保前端服务器上至少安装了 SQL Server 2012 SP1。 如果想立即下载 SP1，请单击[此处的链接](https://www.microsoft.com/download/details.aspx?id=35575)。
  
如果你需要进一步了解 SQL 镜像，我们在 Skype for Business Server 2015 主题中介绍了后端服务器高可用性。 为 Skype for Business Server 2015 配置 SQL Server 群集的过程包括准备群集的步骤。 此处还有 SQL 故障转移群集的更多链接：[2014](https://technet.microsoft.com/library/hh231721.aspx)、[2012](https://technet.microsoft.com/library/hh231721%28v=sql.110%29.aspx) 和 [2008](https://technet.microsoft.com/library/ms189134%28v=sql.105%29.aspx)。
  
> [!NOTE]
> 2015 版本新增了 SQL Always On 支持。 支持该功能，你可以在 [Skype for Business Server 2015 中的后端服务器高可用性](../../plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md)主题中了解更多相关信息。

> [!NOTE]
> 在 Skype for Business Server 2015 中可以使用 SQL 镜像，但 Skype for Business Server 2019 不再支持该功能。 对于 Skype for Business Server 2019，首选 AlwaysOn 可用性组、AlwaysOn 故障转移群集实例 (FCI) 和 SQL 故障转移群集方法。  

## <a name="software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment"></a>应在 Skype for Business Server 2015 部署之前安装的软件
<a name="Software"> </a>

要为任何运行 Skype for Business Server 2015 的服务器进行安装和配置，你需要满足一些条件，如下所示。 满足这些条件后，还要满足特定服务器角色的额外要求。
  
> [注意！] Skype for Business Server 2015 不支持 .NET Framework 4.8。
  
 **所有服务器：**
  
|**软件/角色**|**详细信息**|
|:-----|:-----|
|Windows PowerShell 3.0  <br/> |所有 Skype for Business Server 服务器均需安装 Windows PowerShell 3.0。  <br/> • 如果你在 Windows Server 2012 或 Windows Server 2012 R2 上执行安装，那么你就不必担心，因为其中已经包含了此功能。  <br/> • 如果你在 Windows Server 2008 R2 上执行升级，则可以下载 [Windows Management Framework 3.0](https://www.microsoft.com/download/details.aspx?id=34595) 以获取它。 <br/> **提示**：安装正确的 PowerShell 后，请确认其内部版本号为 6.2.9200.0 或更高版本，方法是转至 PowerShell 命令提示符并键入 `$PSVersionTable`。 此操作将显示你所需的信息。  <br/> |
|Microsoft .NET Framework  <br/> |WCF 服务**功能**作为**服务器管理器**下的 Windows 功能安装，无需下载。 <br/> • 在安装此功能时，或者在系统中已经安装此功能而你在执行检查时，务必确保还已选中并且安装了 **HTTP 激活**选项，如下所示： <br/> ![屏幕截图显示 .NET Framework 4.5 功能下的 HTTP 激活选项。](../../media/a4064fa0-fa49-4474-bd98-b9a79ff68f8b.png)如果你看到另一个弹出框，指出还需要安装其他某些功能才能安装“HTTP 激活”，请不必担心。 这种情况非常正常，只要单击“确定”，继续操作即可。 如果未看到此弹出信息，则可以假设这些功能均已安装，您可以继续操作。  <br/> 安装 Windows Server 2012 R2 或 Windows Server 2016 时，通常会安装 Microsoft .NET Framework。 Skype for Business Server 支持下列 Microsoft .NET Framework 版本：  <br/> • .NET 3.5  <br/> • .NET 4.5  <br/> • .NET 4.6.x  <br/> • .NET 4.7.1（适用于 Skype for Business Server CU 5 或更高版本）  <br/>  .NET Framework 3.5 很可能会默认安装在你的 Windows Server 2008 R2 计算机上（升级前请务必检查以进行确认），但实际不会位于 Windows Server 2012/Windows Server 2012 R2 服务器上（对于新安装）。 要进行添加，你需要访问安装驱动器或媒体（从其安装 Windows Server 的位置，或者安装文件现在所在的位置）。 然后继续操作，并从服务器管理器将其作为功能进行安装，在提示时指向安装媒体（即 **\sources\sxs** 文件夹），然后继续安装。 <br/> |
|媒体基础  <br/> |对于 Windows Server 2016、Windows Server 2012 和 Windows Server 2012 R2，Windows Media Format Runtime 随 Microsoft 媒体基础一起安装。  <br/> 所有用于会议的前端服务器和 Standard Edition 服务器都需要 Windows Media Format Runtime 来运行 Windows Media Audio (.wma) 文件，呼叫寄存、公告和响应组应用程序将通过该文件来播放公告和音乐。  <br/> |
|Windows Identity Foundation  <br/> |我们需要 Windows Identity Foundation 3.5 来支持 Skype for Business Server 2015 的服务器到服务器身份验证情景。  <br/> • 对于 Windows Server 2012 和 Windows Server 2012 R2，不需要下载任何内容。 打开**服务器管理器**，转到**添加角色和功能向导**。 **Windows Identity Foundation 3.5** 在**功能**部分列出。 如果它已经处于选中状态，则没有问题。 否则请选中它，并单击“下一步”，然后单击**安装**按钮。 <br/> |
|远程服务器管理工具  <br/> |角色管理工具：AD DS 和 AD LDS 工具  <br/> |
   
 **前端服务器和 Standard Edition 服务器也需要：**
  
|**软件/角色**|**详细信息**|
|:-----|:-----|
|Internet 信息服务 (IIS)  <br/> |所有前端服务器以及所有标准版服务器都需要 IIS，选择以下模块：  <br/> • 常用 HTTP 功能：默认文档、HTTP 错误、静态内容  <br/> • 运行状况和诊断：HTTP 日志记录、日志记录工具、跟踪  <br/> • 性能：静态内容压缩、动态内容压缩  <br/> • 安全性：请求筛选、客户端证书映射身份验证、Windows 身份验证  <br/> • 应用程序开发：.NET Extensibility 3.5、.NET Extensibility 4.5、ASP.NET 3.5、ASP.NET 4.5、ISAPI 扩展、ISAPI 筛选器  <br/> • 管理工具：IIS 管理控制台、IIS 管理脚本和工具  <br/> 我们还要提醒你，还需要使用匿名访问，但在安装 IIS 时即可安装此功能，因此该列表中未提供选择此项功能的选项。  <br/> |
|Windows Media Format Runtime  <br/> | 对于 Windows Server 2016、Windows Server 2012 和 Windows Server 2012 R2，你需要在**服务器管理器**中安装**媒体基础**功能。 现在，你可以在无此项功能的情况下启动 Skype for Business Server 2015 安装，但系统会提示你安装此功能，随后重新启动服务器，之后才能继续安装 Skype for Business Server 2015。 因此最好提前安装。 <br/> |
|Silverlight  <br/> |你可以通过[此链接](https://www.microsoft.com/silverlight/)安装最新版本的 Silverlight。  <br/> |
   
> [!NOTE] 
> 如果要使用负载平衡器，可能还需要启用“目录浏览”。 否则将加载空白页，而负载平衡器可能会将此情况视为失败。 

为帮助您了解相关过程，我们提供了一个示例 PowerShell 脚本，您可以运行此脚本以自动执行此流程：

```PowerShell
Add-WindowsFeature NET-Framework-Core, RSAT-ADDS, Windows-Identity-Foundation, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Dir-Browsing, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, BITS, Desktop-Experience, Telnet-Client
```

> [!NOTE] 
> 该命令会按特定顺序查找源文件。 如果您处于联机状态，该命令可访问 Windows Update。 但是，如果您处于脱机状态，则需要确保源文件可被该命令使用。 有关使用 PowerShell 安装角色和功能的详细信息，请参阅[安装或卸载角色、角色服务或功能](https://technet.microsoft.com/library/hh831809.aspx)。不要忘记在安装必备组件后再次运行 Windows Update，即便使用 PowerShell 命令也是如此。

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
    
（你或许会感到好奇，此模块集合确实与前端服务器和标准版服务器相同，只是没有包含动态内容压缩和管理工具。）
  
我们还为此提供了以下一些 PowerShell 代码：
  
```PowerShell
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Scripting-Tools, Web-Mgmt-Compat, Desktop-Experience, Telnet-Client
```

 **持久聊天服务器还需要：**
  
消息队列，也称为 MSMQ。 这是一个 Windows Server 组件，你可以在“服务器管理器”的“功能”部分下安装。 如果想进一步了解相关信息，请参阅[安装和管理消息队列](https://technet.microsoft.com/library/cc771474.aspx)。
  
 **最后注意事项：**
  
请勿在任何前端服务器或独立中介服务器上安装任何 Microsoft Internet Security and Acceleration (ISA) Server 客户端软件或其他任何 Winsock 分层服务提供程序 (LSP) 软件（包括任何第三方防火墙或防病毒网络监测软件）。 我们注意到安装此类软件会导致媒体流性能低下。
  

