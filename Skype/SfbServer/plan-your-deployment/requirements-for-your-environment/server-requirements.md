---
title: Skype for business Server 2015 的服务器要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 摘要：使用本主题准备 Skype for Business Server 2015 服务器。 硬件、操作系统、数据库、软件、所有系统要求和建议都可帮助确保成功安装和部署服务器场。
ms.openlocfilehash: f1898fc9de5999276b963a78c181e3b098876b69
ms.sourcegitcommit: 10046048a670b66d93e8ac3ba7c3ebc9c3c5fc2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/20/2020
ms.locfileid: "42160389"
---
# <a name="server-requirements-for-skype-for-business-server-2015"></a>Skype for business Server 2015 的服务器要求
 
**摘要：** 使用本主题准备 Skype for business Server 2015 服务器。 硬件、操作系统、数据库、软件、所有系统要求和建议都可帮助确保成功安装和部署服务器场。

如果要查找环境要求（如 Active Directory、DNS 或证书），可以查看[Skype for Business Server 2015 doc 的环境要求](environmental-requirements.md)。
  
如您所料，开始部署 Skype for Business Server 2015 之前，还需要做一些准备工作。 本文将指导您规划以下内容：
  
- [Skype for business Server 2015 的硬件](server-requirements.md#Hardware)
  
- [适用于 Skype for business Server 2015 的操作系统](server-requirements.md#OS)
  
- [将与 Skype for Business Server 2015 配合使用的后端数据库](server-requirements.md#DBs)
  
- [在 Skype for business Server 2015 部署之前应安装的软件](server-requirements.md#Software)
  
## <a name="hardware-for-skype-for-business-server-2015"></a>Skype for business Server 2015 的硬件
<a name="Hardware"> </a>

现在，您已将拓扑关闭（如果没有，您可以查看[Skype for Business Server 2015 主题的拓扑基础知识](../../plan-your-deployment/topology-basics/topology-basics.md)），那就是考虑使用服务器的时间了。 Skype for Business Server 2015 服务器将需要64位硬件。 我们的硬件建议如下。 这些不是要求，但它们反映了实现最佳性能所需的要求。 我们有容量规划文档，它将根据您的环境，帮助您确定是否需要更多。
  
适用于前端服务器、后端服务器、Standard Edition 服务器和持久聊天服务器的建议硬件：
  
|**硬件组件**|**适合**|
|:-----|:-----|
|CPU  <br/> |64位双处理器、hex-core、2.26 千兆赫兹（GHz）或更高版本。  <br/> Skype for business Server 2015 角色不支持 Intel Itanium 处理器。  <br/> |
|内存  <br/> |32千兆字节（GB）。  <br/> |
|磁盘  <br/> |请  <br/> •8个或更多 10000 RPM 硬盘，至少有 72 GB 的可用磁盘空间（两个磁盘使用 RAID 1，6个磁盘使用 RAID 10）。  <br/> 或  <br/> •稳定状态驱动器（Ssd）能够为 8 10000 RPM 机械磁盘驱动器提供相同的可用空间和类似的性能。  <br/> |
|网络  <br/> |1个双端口网络适配器，1 Gbps 或更高（2个网络适配器可以使用，但需要使用一个 MAC 地址和一个 IP 地址进行分组）。  <br/> 前端服务器、后端服务器、Standard Edition 服务器和持久聊天服务器**不**支持双宿主或多宿主配置。 <br/> 只要不向操作系统公开并使用它来监视和管理服务器硬件，您就可以拥有带外管理系统，如 DRAC 或 ILO。 此方案不构成多穴服务器，并且受支持。  <br/> |
   
适用于边缘服务器、独立中介服务器、视频互操作服务器和控制器的推荐硬件：
  
|**硬件组件**|**适合**|
|:-----|:-----|
|CPU  <br/> |64位双处理器、四核、2.26 千兆位（GHz）或更高版本。  <br/> Skype for business Server 2015 角色不支持 Intel Itanium 处理器。  <br/> |
|内存  <br/> |16 gb。  <br/> |
|磁盘  <br/> |请  <br/> •4个或更多 10000 RPM 硬盘，至少有 72 GB 的可用磁盘空间（磁盘应采用 2x RAID 1 配置）。  <br/> 或  <br/> •稳定状态驱动器（Ssd）能够为 4 10000 RPM 机械磁盘驱动器提供相同的可用空间和类似的性能。  <br/> |
|网络  <br/> |1个双端口网络适配器，1 Gbps 或更高（2个网络适配器可以使用，但需要使用一个 MAC 地址和一个 IP 地址进行分组）。  <br/> 视频互操作服务器和控制器**不**支持双宿主或多宿主配置。 <br/> 边缘服务器需要两个分别为双端口网络适配器、1 Gbps 或更高（或两个配对的网络适配器）的网络接口（或两个配对的网络适配器），每个端口包含一个 MAC 地址和一个 IP 地址，共有两对。  <br/> 在独立中介服务器上，支持安装额外的网络接口卡（Nic），以允许配置特定的 PSTN IP 地址。  <br/> |
   
## <a name="operating-systems-for-skype-for-business-server-2015"></a>适用于 Skype for business Server 2015 的操作系统
<a name="OS"> </a>

硬件准备就绪后，您需要安装操作系统（OS）。 这些是将允许您安装和成功使用 Skype for Business Server 2015 的操作系统。
  
|||
|:-----|:-----|
|Windows Server 2019 （需要 Skype for Business 累积更新9或更高版本）。 <br/> |Windows Server 2016 （你需要 Skype for Business 累积更新5或更高版本。 有关详细信息，请检查[KB4015888](https://support.microsoft.com/help/4015888/how-to-install-skype-for-business-server-2015-on-windows-server-2016)）  <br/> ||
|Windows Server 2012 R2 Datacenter OS，安装了所有必需的更新。  <br/> |Windows Server 2012 R2 Standard OS，安装了所有必需的更新。  <br/> |
|Windows Server 2012 Datacenter OS，安装了所有必需的更新。  <br/> |Windows Server 2012 Standard OS，安装了所有必需的更新。  <br/> |
   
如果不在此列表中，它将无法正常运行，请不要在新安装的 Skype for Business Server 2015 中试用它。 请注意，Lync Server 2013 不支持就地升级操作系统。  您必须部署单独的池，并将用户迁移到具有不同操作系统的新池。
  
> [!NOTE]
> 您可能已注意到 Windows Server 2008 R2 不在此列表中。 这是因为我们建议将所有新服务器的 Windows Server 2012 R2 用于 SFB。 只有在安装了已安装 Lync Server 2013 的现有服务器，并且您要执行它们的就地升级时，才应使用 Windows Server 2008 R2。 Windows Server 2008 R2 已到达1/13/2015 的主流支持生命周期的结尾，并将在1/14/2020 上到达其支持生命周期的结尾。
  
除了最新的 service pack 之外，还需要确保安装了以下与您相关的更新：
  
- 对于 Windows Server 2012，应在升级之前安装知识库文章2858668。 请在[此处获取](https://support.microsoft.com/kb/2858668/)。
    
- 如果你有 Windows Server 2012 R2，请先安装知识库文章2982006，然后再升级。 [它位于此处](https://support.microsoft.com/kb/2982006/)。
    
- 如果要在 Windows Server 2008 R2 框上升级（请参阅上面的注释），则需要先安装知识库文章2533623。 [它位于此链接上](https://support.microsoft.com/kb/2533623/)。
    
## <a name="back-end-databases-that-will-work-with-skype-for-business-server-2015"></a>将与 Skype for Business Server 2015 配合使用的后端数据库
<a name="DBs"> </a>


安装 Skype for Business Server 2015 Standard Edition 时，将同时自动安装 SQL Server 2014 Express （64位版本）。
  
Skype for Business Server 2015 Enterprise Edition 稍微复杂一些，但受支持的列表如下所示（一切都是64位版本，您会注意到，请勿使用32位版本）：
  
||||||
|:-----|:-----|:-----|:-----|:-----|
|Microsoft SQL Server 2019 企业版（64版），我们建议使用最新的 service pack 运行。 <br/> |Microsoft SQL Server 2017 企业版（64版），我们建议使用最新的 service pack 运行。 <br/> |Microsoft SQL Server 2016 Enterprise （64-bit edition） Service Pack 1 或更高版本，必须运行 Skype for Business 累积更新7或更高版本（[下载 skype For Business 累积更新](https://support.microsoft.com/help/3061064)）。  <br/> |Microsoft SQL Server 2014 Enterprise （64-bit edition），必须运行累积更新6或更高版本（[下载累积更新 6](https://support.microsoft.com/kb/3031047/)）。  <br/> |Microsoft SQL Server 2012 企业版（64版），我们建议使用最新的 service pack 运行。  <br/> |
|Microsoft SQL Server 2019 Standard （64-bit edition），我们建议使用最新的 service pack 运行。 <br/> |Microsoft SQL Server 2017 Standard （64-bit edition），我们建议使用最新的 service pack 运行。 <br/> |Microsoft SQL Server 2016 Standard （64-bit edition） Service Pack 1 或更高版本，必须运行 Skype for Business 累积更新7或更高版本（[下载 skype For Business 累积更新](https://support.microsoft.com/help/3061064)）。  <br/> |Microsoft SQL Server 2014 Standard （64-bit edition），必须运行累积更新6或更高版本（[下载累积更新 6](https://support.microsoft.com/kb/3031047/)）。  <br/> |Microsoft SQL Server 2012 Standard （64-bit edition），我们建议使用最新的 service pack 运行。  <br/> |
   
如果您在此处看不到要使用的 SQL Server 版本，则不能使用它。
  
- 您还需要为监视服务器角色安装 SQL Server Reporting Services。
- 对于连接良好的 SQL 后端，与 Skype for Business 前端的连接应是本地的，而不是通过低速链路。 
- 不支持在两个或多个池之间共享 SQL 后端。

### <a name="microsoft-exchange-storage"></a>Microsoft Exchange 存储
会议内容文件（如 PowerPoint 演示文稿）将作为附件存档。 如果要将 Skype for Business 存档数据与 Exchange 合规性数据一起存储，则必须将 Exchange 用于 Exchange 部署，并确保最大存储大小支持会议内容文件的存储。 必须先部署 Exchange，然后才能使用 Microsoft Exchange 集成选项部署和启用存档。 
    
    If you choose to use Exchange storage, you do not need to deploy separate SQL Server databases for archiving, unless you have Skype for Business users who are not homed on your Exchange servers. If you deploy archiving using the Microsoft Exchange integration option, Skype for Business archive data is stored with Exchange compliance data only for the users who are homed on your Exchange servers. 
  
## <a name="hardware-and-software-requirements-for-archiving-in-skype-for-business-server-2015"></a>Skype for business Server 2015 中的存档的硬件和软件要求
  
存档不是定义的服务器角色，无需安装单独的服务器来进行存档。 统一数据收集代理在每个企业版前端池和每个 Standard Edition 服务器上自动安装和激活。 你将需要使用拓扑生成器启用和发布存档拓扑。
    
存档使用 Skype for Business 服务器文件存储来存储会议内容文件的临时存储，因此您无需设置单独的文件存储来进行存档。
    
Microsoft 消息队列不是必需的。
    
你将需要设置用于存档存储的基础结构。 这包括使用 SQL Server 选择 "Exchange" 或 "存档存储"。   Skype for business Server 存档基础结构要求与部署 Skype for business Server 的要求相同。 有关详细信息，请参阅[Skype For business 环境的要求](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md)。 
  
> [!NOTE]
> 若要支持不驻留在 Exchange 服务器上的用户，或者如果您不想使用 Microsoft Exchange 集成选项，则必须使用64位 SQL Server 数据库部署存档存储。 
    
在部署和启用存档之前，必须设置 SQL Server 平台。 如果用于发布拓扑的帐户具有适当的管理员权限，则可在发布拓扑时创建存档数据库 (LcsLog)。 您还可以在以后创建数据库，包括在安装过程中。 有关 SQL Server 的详细信息，请参阅[Sql server 文档](https://go.microsoft.com/fwlink/p/?linkID=129045)。
    
存档的负载增加可能非常显著。 因此，应确保磁盘空间足以满足启用了存档的前端服务器的需要。

### <a name="sql-mirroring-sql-clustering-and-sql-always-on"></a>SQL 镜像、SQL 群集和 SQL Always On

您可以将 SQL 镜像或 SQL 群集与 Skype for Business Server 2015 结合使用，这是受支持的。 通过 Skype for Business Server 拓扑生成器设置 SQL 镜像。 如果你打算设置 SQL 群集，则在 SQL Server 中执行此操作。
  
请确保您具有 SQL 群集的主动/被动配置，因为这是 what's 支持的。 不要与任何其他 SQL 实例共享被动节点。
  
您可以对故障转移群集使用以下各项：
  
双节点：
  
- Microsoft SQL Server 2019 Standard （64-bit edition），我们建议使用最新的 service pack 运行。

- Microsoft SQL Server 2017 Standard （64-bit edition），我们建议使用最新的 service pack 运行。

- Microsoft SQL Server 2016 Standard （64-bit edition） Service Pack 1 或更高版本。 我们建议使用最新的 service pack 运行。

- Microsoft SQL Server 2014 Standard （64-bit edition），我们建议使用最新的 service pack 运行。
    
-  Microsoft SQL Server 2012 Standard （64-bit edition），我们建议使用最新的 service pack 运行。

十六节点：

- Microsoft SQL Server 2019 企业版（64版），我们建议使用最新的 service pack 运行。

- Microsoft SQL Server 2017 企业版（64版），我们建议使用最新的 service pack 运行。

- Microsoft SQL Server 2016 Enterprise （64-bit edition） Service Pack 1 或更高版本。 我们建议使用最新的 service pack 运行。
  
- Microsoft SQL Server 2014 企业版（64版），我们建议使用最新的 service pack 运行。
    
- Microsoft SQL Server 2012 企业版（64版），我们建议使用最新的 service pack 运行。

> [!IMPORTANT]
> 为了进行升级，我们确实希望你确保在前端服务器上至少安装了 SQL Server 2012 SP1，然后再升级。 如果要立即下载 SP1，下面是指向 SP1 的[链接](https://www.microsoft.com/download/details.aspx?id=35575)。
  
如果需要了解有关 SQL 镜像的详细信息，请参阅 Skype for Business Server 2015 主题中的后端服务器高可用性。 为 Skype for business Server 2015 配置 SQL Server 群集具有准备群集的步骤。 有关 SQL 的故障转移群集的进一步链接，请参阅[2014](https://technet.microsoft.com/library/hh231721.aspx)、 [2012](https://technet.microsoft.com/library/hh231721%28v=sql.110%29.aspx)和[2008](https://technet.microsoft.com/library/ms189134%28v=sql.105%29.aspx)。
  
> [!NOTE]
> 2015版本的新增支持 SQL Always On。 它受支持，你可以在[Skype for Business server 2015 主题的后端服务器高可用性](../../plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md)中了解有关它的详细信息。

> [!NOTE]
> SQL 镜像在 Skype for business Server 2015 中可用，但在 Skype for Business Server 2019 中不再受支持。 对于 Skype for Business Server 2019，AlwaysOn 可用性组、AlwaysOn 故障转移群集实例（FCI）和 SQL 故障转移群集方法是首选方法。  

## <a name="software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment"></a>在 Skype for business Server 2015 部署之前应安装的软件
<a name="Software"> </a>

您需要为运行 Skype for Business Server 2015 的任何服务器安装或配置一些内容，如下所示。 之后是特定服务器角色的其他要求。
  
> [注释！]Skype For Business server 2015 不支持 .NET Framework 4.8。
  
 **所有服务器：**
  
|**软件/角色**|**Details**|
|:-----|:-----|
|Windows PowerShell 3.0  <br/> |所有 Skype for Business 服务器服务器都需要安装 Windows PowerShell 3.0。  <br/> •如果您正在执行 Windows Server 2012 或 Windows Server 2012 R2 上的安装，则您已进行设置，因为它已存在。  <br/> •如果要在 Windows Server 2008 R2 上执行升级，可以下载[Windows Management Framework 3.0](https://www.microsoft.com/download/details.aspx?id=34595)获取它。 <br/> **提示：** 拥有正确的 PowerShell 后，请转到 PowerShell 提示符并键入`$PSVersionTable`，确认它已为6.2.9200.0 或更高版本。 这将显示所需的信息。  <br/> |
|Microsoft .NET Framework  <br/> |WCF 服务是一种作为 Windows 功能安装的**功能**，在**服务器管理器**下，无需下载。 <br/> •您需要确保在安装此功能时，或者如果已安装此功能并对其进行检查，也会检查并安装**HTTP 激活**选项，如下所示： <br/> ![显示 .NET Framework 4.5 功能下的 HTTP 激活选项的屏幕截图。](../../media/a4064fa0-fa49-4474-bd98-b9a79ff68f8b.png)如果你还需要安装其他一些提示，以便安装 HTTP 激活，请不要担心。 这是正常的，请单击 "确定" 并继续。 如果你没有看到此弹出窗口，请假设已安装这些内容，然后继续。  <br/> 安装 Windows Server 2012 R2 或 Windows Server 2016 时，通常会安装 Microsoft .NET Framework。 Skype for Business Server 适用于以下 Microsoft .NET Framework 版本：  <br/> • .NET 3。5  <br/> • .NET 4。5  <br/> • .NET 4.6. x  <br/> • .NET 4.7.1 （适用于 Skype for business Server CU 5 或更高版本）  <br/> • .NET 4.7.2 （适用于 Skype for business Server CU 6 或更高版本）  <br/>  .NET Framework 3.5 在 Windows Server 2008 R2 计算机上可能会默认安装（明确确保在升级之前进行检查），但实际上不是在 Windows Server 2012/Windows Server 2012 R2 服务器上（针对新安装）。 若要将其添加到中，你将需要访问你的安装驱动器或媒体（安装 Windows Server 的位置或安装文件现在所在的位置）。 然后，在服务器管理器中将其安装为一项功能，并在系统提示时指向安装媒体（尤其是**\sources\sxs**文件夹），然后继续安装它。 <br/> |
|媒体基础  <br/> |对于 Windows Server 2016、Windows Server 2012 和 Windows Server 2012 R2，Windows Media Format Runtime 在 Microsoft Media Foundation 中安装。  <br/> 所有前端服务器和用于会议的 Standard Edition 服务器要求 Windows Media Format Runtime 运行 Windows Media 音频（.wma）文件，这些文件是呼叫寄存、公告和响应组应用程序，用于通知和音乐。  <br/> |
|Windows Identity Foundation  <br/> |我们需要 Windows Identity Foundation 3.5 以支持 Skype for business Server 2015 的服务器到服务器身份验证方案。  <br/> •对于 Windows Server 2012 和 Windows Server 2012 R2，无需下载任何内容。 打开 "**服务器管理器**"，然后转到 "**添加角色和功能向导**"。 **Windows Identity Foundation 3.5**在 "**功能**" 部分下列出。 如果已被选中，则您是个合适的。 否则选择它并单击 "下一步"，进入 "**安装**" 按钮。 <br/> |
|远程服务器管理工具  <br/> |角色管理工具： AD DS 和 AD LDS 工具  <br/> |
   
 **前端服务器和 Standard Edition server 还需要：**
  
|**软件/角色**|**Details**|
|:-----|:-----|
|Internet Information Services (IIS)  <br/> |在所有前端服务器和所有 Standard Edition 服务器上都需要使用 IIS，并选择以下模块：  <br/> •常见的 HTTP 功能：默认文档、HTTP 错误、静态内容  <br/> •运行状况和诊断： HTTP 日志记录、日志记录工具、跟踪  <br/> •性能：静态内容压缩、动态内容压缩  <br/> •安全性：请求筛选、客户端证书映射身份验证、Windows 身份验证  <br/> •应用程序开发： .NET 扩展性3.5、.NET 扩展性4.5、ASP.NET 3.5、ASP.NET 4.5、ISAPI Extension、ISAPI 筛选器  <br/> •管理工具： IIS 管理控制台、IIS 管理脚本和工具  <br/> 我们还应注意，还需要进行匿名访问，但在您安装 IIS 时，您没有在列表中选择该位置的地方。  <br/> |
|Windows Media Format Runtime  <br/> | 对于 Windows Server 2016、Windows Server 2012 和 Windows Server 2012 R2，您需要在**服务器管理器**中安装**媒体基础**功能。 现在，您实际上可以在没有此安装的情况下启动 Skype for business Server 2015 安装，但在 Skype for Business Server 2015 安装继续之前，系统将提示您安装它，然后重新启动服务器。 在提前执行时更好。 <br/> |
|Silverlight  <br/> |你可以在[此链接](https://www.microsoft.com/silverlight/)上安装最新版本的 Silverlight。  <br/> |
   
> [!NOTE] 
> 如果使用的是负载平衡器，则可能还需要启用目录浏览。 否则，空白页将加载负载平衡器可能会考虑故障的情况。 

为了帮助您完成此过程，您可以运行以下示例 PowerShell 脚本来自动执行此操作：

```PowerShell
Add-WindowsFeature NET-Framework-Core, RSAT-ADDS, Windows-Identity-Foundation, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Dir-Browsing, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, BITS, Desktop-Experience, Telnet-Client
```

> [!NOTE] 
> 该命令将按特定顺序查找源文件。 如果你处于联机状态，该命令将访问 Windows 更新。 但是，如果您处于脱机状态，则需要确保源文件可用于该命令。 有关使用 PowerShell 安装角色和功能的详细信息，请参阅安装[或卸载角色、角色服务或功能](https://technet.microsoft.com/library/hh831809.aspx)在安装必备组件后不会忘记再次运行 Windows Update，即使您使用 PowerShell 命令也是如此。

 **控制器还需要：**
  
IIS 中，选择以下模块：
  
- 常见的 HTTP 功能
    
  - 默认文档
    
  - HTTP 错误
    
  - 静态内容
    
- 运行状况和诊断
    
  - HTTP 日志记录
    
  - 日志记录工具
    
  - 追踪
    
- 性能
    
  - 静态内容压缩
    
- 安全性
    
  - 请求筛选
    
  - 客户端证书映射身份验证
    
  - Windows 身份验证
    
- 应用程序开发
    
  - .NET 扩展性3。5
    
  - .NET Extensibility 4.5
    
  - ASP.NET 3。5
    
  - ASP.NET 4。5
    
  - ISAPI 扩展
    
  - ISAPI 筛选器
    
（如果您想知道，它与前端服务器和 Standard Edition 服务器的模块集相同，动态内容压缩和管理工具将被留给。）
  
此外，我们还提供了下面的一些 PowerShell 代码：
  
```PowerShell
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Scripting-Tools, Web-Mgmt-Compat, Desktop-Experience, Telnet-Client
```

 **持久聊天服务器还需要：**
  
消息队列，也称为 MSMQ。 它是一个 Windows Server 组件，您可以在服务器管理器的 "功能" 部分下安装它。 若要了解有关详细信息，请参阅[安装和管理消息队列](https://technet.microsoft.com/library/cc771474.aspx)。
  
 **上次想法：**
  
请勿在上安装任何 Microsoft Internet 安全性和加速（ISA） Server 客户端软件或任何其他 Winsock 分层服务提供程序（LSP）软件（此处包含第三方防火墙或防病毒网络检查软件）任何前端服务器或独立中介服务器。 安装该软件时，会看到较差的媒体流量性能。
  

