---
title: Skype for business Server 2019 的系统要求
ms.reviewer: ''
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: '摘要: 通过本主题准备 Skype for Business Server 2019 服务器和域基础结构。 硬件、操作系统、数据库、软件、所有系统要求和建议, 以及证书 DNS、文件共享和 Active Directory 信息, 可帮助确保成功安装和部署你的服务器场。'
ms.openlocfilehash: 94b95f97021a4633a6dbcbf300426731cefc85fe
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34283918"
---
# <a name="system-requirements-for-skype-for-business-server-2019"></a>Skype for business Server 2019 的系统要求
 
**摘要:** 准备安装本主题的 Skype for business Server 2019。 此处介绍了硬件、操作系统、软件、数据库、证书、活动 Diretory、DNS 和 fileshares。 此处的所有系统要求和建议均可帮助确保成功安装和部署你的服务器场。
  
正如你所料, 开始部署 Skype for Business Server 2019 之前, 需要做一些准备。 本文将指导你制定以下规划：
  
- [硬件](system-requirements.md#Hardware)
  
- [操作系统](system-requirements.md#OS)
  
- [软件](system-requirements.md#Software)

- [后端 SQL 数据库](system-requirements.md#DBs)
  
- [Active Directory](system-requirements.md#AD)
  
- [域名系统 (DNS)](system-requirements.md#DNS)
  
- [证书](system-requirements.md#Certs)
  
- [文件共享](system-requirements.md#Fileshare)

  
## <a name="hardware-for-skype-for-business-server-2019"></a>Skype for business Server 2019 的硬件
<a name="Hardware"> </a>

当你的拓扑关闭后 (如果不是, 你可以查看[Skype for Business Server 2019 主题的拓扑基础知识](../../SfbServer/plan-your-deployment/topology-basics/topology-basics.md)), 现在就可以思考一下服务器。 Skype for Business Server 2019 服务器需要64位硬件。 下面给出了我们的硬件建议。 这些不是要求, 但它们反映了最佳性能所需的要求。 我们的容量规划文档可帮助你根据自己的环境确定是否需要高于此要求的配置。
  
适用于标准版服务器的推荐硬件:

|**硬件组件**|**推荐**|
|:-----|:-----|
|CPU  <br/> |英特尔至强 2673 v3 双处理器、6核、2.4 千兆位 (GHz) 或更高版本。  <br/> Skype for business Server 2019 角色不支持英特尔安腾处理器。  <br/> |
|内存  <br/> |32 GB。  <br/> |
|磁盘  <br/> |以下之一：  <br/> •8个或更多 10000 RPM 硬盘, 至少有 72 GB 的可用磁盘空间 (使用 RAID 1 和6的两个磁盘使用 RAID 10)。  <br/> 或者  <br/> •固态硬盘 (SSDs) 能够为 8 10000 RPM 机械磁盘驱动器提供同样的可用空间和类似的性能。  <br/> |
|网络  <br/> |1 个双端口网络适配器，1 Gbps 或更高（可使用 2 个网络适配器，但需要通过一个 MAC 地址和一个 IP 地址配合使用）。  <br/> 前端服务器、后端服务器和标准版服务器**不**支持双重或多穴配置。 <br/> 只要这些用户未向操作系统公开, 并且用于监视和管理服务器硬件, 您就可以拥有带外管理系统, 如 DRAC 或 ILO。 这种情况不会形成多宿主服务器，并且受支持。  <br/> |


适用于前端服务器和后端服务器的推荐硬件:
  
|**硬件组件**|**推荐**|
|:-----|:-----|
|CPU  <br/> |英特尔至强 2673 v3 双处理器、6核、2.4 千兆位 (GHz) 或更高版本。 <br/> Skype for business Server 2019 角色不支持英特尔安腾处理器。  <br/> |
|内存  <br/> |64千兆字节 (GB)。  <br/> |
|磁盘  <br/> |以下之一：  <br/> •8个或更多 10000 RPM 硬盘, 至少有 72 GB 的可用磁盘空间 (使用 RAID 1 和6的两个磁盘使用 RAID 10)。  <br/> 或者  <br/> •固态硬盘 (SSDs) 能够为 8 10000 RPM 机械磁盘驱动器提供同样的可用空间和类似的性能。  <br/> |
|网络  <br/> |1 个双端口网络适配器，1 Gbps 或更高（可使用 2 个网络适配器，但需要通过一个 MAC 地址和一个 IP 地址配合使用）。  <br/> 前端服务器、后端服务器和标准版服务器**不**支持双重或多穴配置。 <br/> 只要这些用户未向操作系统公开, 并且用于监视和管理服务器硬件, 您就可以拥有带外管理系统, 如 DRAC 或 ILO。 这种情况不会形成多宿主服务器，并且受支持。  <br/> |
   
适用于 Edge 服务器、独立中介服务器和控制器的推荐硬件:
  
|**硬件组件**|**推荐**|
|:-----|:-----|
|CPU  <br/> |英特尔至强 2673 v3 双处理器、6核、2.4 千兆位 (GHz) 或更高版本。  <br/> Skype for business Server 2019 角色不支持英特尔安腾处理器。  <br/> |
|内存  <br/> |32千兆字节。  <br/> |
|磁盘  <br/> |以下之一：  <br/> •4个或更多 10000 RPM 硬盘, 至少有 72 GB 的可用磁盘空间 (磁盘应位于 2x RAID 1 配置中)。  <br/> 或者  <br/> •固态硬盘 (SSDs) 能够为 4 10000 RPM 机械磁盘驱动器提供同样的可用空间和类似的性能。  <br/> |
|网络  <br/> |1 个双端口网络适配器，1 Gbps 或更高（可使用 2 个网络适配器，但需要通过一个 MAC 地址和一个 IP 地址配合使用）。  <br/> 视频互操作服务器和控制器**不**支持双重或多穴配置。 <br/> 边缘服务器需要两个网络接口，均为双端口网络适配器、1 Gbps 或更高速度（或两个成对网络适配器，总计 4 个适配器，每一对均与单一 MAC 地址和单一 IP 地址配合使用，总共两对）。  <br/> 在独立中介服务器上, 支持安装其他网络接口卡 (Nic) 以允许配置特定的 PSTN IP 地址。  <br/> |


> [!NOTE]
> 无论服务器角色如何, 我们还建议针对 Skype for Business Server 2019 的以下硬件设置 (这可能会有所不同, 具体取决于你购买的硬件品牌, 请参阅制造商文档了解详细信息):
> - BIOS 配置-应设置为 "单层", 即 "从 NUMA"。
> - 启用超线程。
> - "RSS 队列" 设置应设置为 "8 个队列"。

   
## <a name="operating-systems-for-skype-for-business-server-2019"></a>Skype for business Server 2019 的操作系统
<a name="OS"> </a>

准备好硬件后, 您需要安装操作系统 (OS), 该操作系统将允许您安装并成功使用 Skype for Business Server 2019。
  
|||
|:-----|:-----|
|Windows Server 2019 <br/> |
|Windows Server 2016 <br/> ||
||
   
除此处列出的操作系统以外的任何操作系统将无法正常工作;请不要尝试安装 Skype for Business Server 2019。 例如, "服务器核心" 选项未列出, 因此不受支持。

> [!NOTE]
> 
> 如果在 Windows Server 2019 计算机上安装 Windows 管理中心 2019, 它将提示你提供侦听端口。 你可能会选择端口 443, 但如果该计算机上安装了 Skype for business Server 2019, 或者要在其上安装了 Skype for business Server 2019, 则必须选择不同的端口号。
> 
>为什么是这种情况？ 如果 Windows 管理中心2019是在端口443上运行, 您将无法使用 Skype for Business 控制面板连接到服务器, 也不能连接到服务器上运行的任何内部 web 服务 (通讯簿 Web 服务)。、自动发现服务、WebTicket 服务等)。  事实上, 您将无法连接到任何内部 Web 服务 URL。 请选择其他端口, 在你需要的事件中, 或者希望将 Windows 管理中心2019放置在使用 Skype for Business Server 2019 的服务器上。
> 

  
## <a name="software-that-should-be-installed-before-a-skype-for-business-server-2019-deployment"></a>在 Skype for Business Server 2019 部署之前应安装的软件
<a name="Software"> </a>

对于运行 Skype for Business Server 2019 的任何服务器, 你需要安装或配置一些事项。 下面列出了这些详细要求, 后跟特定服务器角色的其他要求。
  
 **所有服务器:**
  
|**软件/角色**|**详细信息**|
|:-----|:-----|
|Windows PowerShell 3.0  <br/> |所有 Skype for business 服务器服务器都需要安装 Windows PowerShell 3.0。  <br/> •默认情况下应安装 Windows Server 2016。<br/> |
|Microsoft .NET Framework  <br/> |WCF 服务是作为 Windows 功能安装的**功能**, 在**服务器管理器**下, 无需下载。 <br/> •你需要确保在安装此功能时, 或者在已安装此功能且正在进行检查时, 也会检查和安装**HTTP 激活**选项, 如下所示: <br/> ![屏幕截图显示 .NET Framework 4.5 功能下的 HTTP 激活选项。](../../SfbServer/media/a4064fa0-fa49-4474-bd98-b9a79ff68f8b.png) <br/> 如果您看到另一则弹出信息，表示要安装“HTTP 激活”，还需要安装其他某些功能，请不必担心。 这是正常的;单击 "确定", 然后继续。 如果您没有看到此弹出窗口, 则可以假设已安装这些项目并继续。  <br/> 安装 Windows Server 2016 时, 通常会安装 Microsoft .NET Framework。 Skype for business 服务器适用于以下 Microsoft .NET Framework 版本:  <br/> • .NET 3。5  <br/> • .NET 4。5  <br/> • .NET 4.6 x  <br/> • .NET 4。7 <br/> |
|媒体基础  <br/> |对于 Windows Server 2016, Windows Media 格式运行时将与 Microsoft Media Foundation 一起安装。  <br/> 用于会议的所有前端服务器和标准版服务器都需要 Windows Media 格式运行时运行 Windows Media 音频 (.wma) 文件, 该文件中的 "呼叫驻留"、"通知" 和 "响应" 组应用程序将在公告和音乐中播放。  <br/> |
|Windows Identity Foundation  <br/> |我们需要 Windows Identity Foundation 3.5 以支持 Skype for business Server 2019 的服务器到服务器身份验证方案。  <br/> •适用于 Windows Server 2016, 无需下载任何内容。 打开**服务器管理器**，转到**添加角色和功能向导**。 **Windows Identity Foundation 3.5** 在**功能**部分列出。 如果已选中, 则很好。 否则选择它, 然后单击 "**下一步**" 以到达 "**安装**" 按钮。 <br/> |
|远程服务器管理工具  <br/> |角色管理工具：AD DS 和 AD LDS 工具  <br/> |
   
 **前端服务器和标准版服务器还需要:**
  
|**软件/角色**|**详细信息**|
|:-----|:-----|
|Internet Information Services (IIS)  <br/> |在所有前端服务器以及所有标准版服务器上都需要 IIS, 并且选择了以下模块:  <br/> •常见的 HTTP 功能: 默认文档、HTTP 错误、静态内容  <br/> •运行状况和诊断: HTTP 日志记录、日志记录工具、跟踪  <br/> •性能: 静态内容压缩, 动态内容压缩  <br/> •安全: 请求筛选、客户端证书映射身份验证、Windows 身份验证  <br/> •应用程序开发: .NET 扩展性3.5、.NET 扩展性4.5、ASP.NET 3.5、ASP.NET 4.5、ISAPI 扩展、ISAPI 筛选器  <br/> •管理工具: IIS 管理控制台、IIS 管理脚本和工具  <br/> 请注意, 还需要匿名访问, 但你可以在安装 IIS 时收到, 因此你没有位置在列表中选择它。  <br/> |
|Windows Media Format Runtime  <br/> | 对于 Windows Server 2016, 你需要在**服务器管理器**中安装**Media Foundation**功能。 您实际上可以启动 Skype for Business Server 2019 安装, 但在 Skype for business Server 2019 安装继续之前, 系统将提示您安装它, 然后重新启动服务器。 最好提前完成。 <br/> |
|Silverlight  <br/> |你可以[在此处](https://www.microsoft.com/silverlight/)安装最新版本的 Silverlight。  <br/> |
   
为帮助您了解相关过程，我们提供了一个示例 PowerShell 脚本，您可以运行此脚本以自动执行此流程：
  
```
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, Telnet-Client
```

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
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, Telnet-Client
```

## <a name="back-end-databases-that-will-work-with-skype-for-business-server-2019"></a>将与 Skype for Business Server 2019 配合使用的后端数据库
<a name="DBs"> </a>

安装 Skype for Business Server 2019 标准版时, 你将拥有 SQL Server 2016 Express (64 位版本)。

Skype for Business Server 2019 企业版将需要完整的 SQL Server, 如下所示 (仅64位版本; 请不要使用32位版本):
  
||||
|:-----|:-----|:-----|
|Microsoft SQL Server 2016 (64 位版), 您必须运行最新的更新。  <br/> |
Microsoft SQL Server 2017 (64 位版), 您必须运行最新的更新。|
 |

如果在此处看不到要使用的 SQL Server 版本, 则无法使用它。
  
> [!NOTE]
> 你还需要为监视服务器角色安装 SQL Server Reporting Services。 
  
### <a name="sql-clustering-and-sql-always-on"></a>SQL 群集和 SQL Always On

支持支持 Skype for Business Server 2019 的 SQL 群集。 如果要设置 SQL 群集, 则在 SQL Server 中完成。
  
请确保你有支持 SQL 群集的主动/被动配置。 不要与任何其他 SQL 实例共享被动节点。
  
可以为故障转移群集采用以下配置：
  
双节点：
  
- Microsoft SQL Server 2016 标准版 (64 位版), 我们建议通过最新的 service pack 运行。
- Microsoft SQL Server 2017 标准版 (64 位版), 我们建议通过最新的 service pack 运行。

16 节点：
  
- Microsoft SQL Server 2016 企业版 (64 位版), 我们建议通过最新的服务包运行。
- Microsoft SQL Server 2017 企业版 (64 位版), 我们建议通过最新的服务包运行。

SQL Always On 受支持, 你可以在[Skype for Business server 2019 的后端服务器高可用性](../../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md)中阅读更多相关信息。
  

###  <a name="additional-server-installation-recommendations"></a>其他服务器安装建议:
  
请不要安装任何 Microsoft Internet 安全和加速 (ISA) 服务器客户端软件或任何其他 Winsock 分层服务提供商 (LSP) 软件 (此处包含任何第三方防火墙或防病毒网络检查软件)任何前端服务器或独立中介服务器。 安装该软件时, 有较差的媒体流量性能已被发现。
  

## <a name="active-directory"></a>Active Directory
<a name="AD"> </a>

虽然服务器和服务的大部分配置数据存储在 Skype for business Server 2019 中央管理存储中, 但仍有一些内容存储在 Active Directory 中:
  
|**Active Directory 对象**|**对象类型**|
|:-----|:-----|
|架构扩展  <br/> |用户对象扩展  <br/> |
||Skype for business Server 2015 和 Lync Server 2013 的扩展可保持与以前支持的版本的向后兼容性  <br/> |
|数据  <br/> |用户 SIP URI 和其他用户设置  <br/> |
||应用程序的联系人对象 (如响应组应用程序和会议助理应用程序)  <br/> |
||发布数据以实现向后兼容性  <br/> |
||中央管理存储的服务控制点 (SCP)  <br/> |
||Kerberos 身份验证帐户 (可选的计算机对象)  <br/> |
   
### <a name="os-for-domain-controllers"></a>域控制器的操作系统

可以使用以下域控制器操作系统:
  
- Windows Server 2019

- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
你将 Skype for business Server 2019 部署到的任何域的域功能级别以及你将 Skype for business Server 2019 部署到的任何林的林功能级别必须是以下各项之一:
  
- Windows Server 2019

- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
这些环境中能否有只读域控制器？ 当然, 只要有可写的域控制器也是如此。
  
请务必了解 Skype for business 服务器2019不支持单标记的域。 单标签域是什么？ 如果您有一个名为 "contoso" 的根域, 那么它就会很好。 如果你有一个仅命名为本地的根域, 则它将不起作用, 因此不受支持。 有关这方面的详细信息, 请查阅[本知识库文章](https://support.microsoft.com/kb/300684/en-us)。
  
Skype for Business Server 2019 也不支持重命名域。 如果您确实需要重命名您的域, 则需要卸载 Skype for business Server 2019, 执行域重命名, 然后重新安装 Skype for Business Server 2019。
  
最后, 你可能正在处理具有锁定的 AD DS 环境的域, 这种情况好。 有关如何在部署文档中将 Skype for business Server 2019 部署到锁定的 AD DS 环境的详细信息。
  
### <a name="ad-topologies"></a>AD 拓扑

Skype for Business Server 2019 中支持的拓扑包括:
  
- 具有单个域的单林
    
- 具有单个树和多个域的单林
    
- 具有多个树和互不连接的命名空间的单林
    
- 中央林拓扑中的多林
    
- 资源林拓扑中的多林
    
- 具有 Exchange Online 的 Skype for Business 资源林拓扑中的多个林
    
- 有 Skype for Business Online 和 Azure Active Directory Connect 的资源林拓扑中的多个林
    
我们有一些图表和说明, 可帮助你确定你的环境中所拥有的拓扑, 或者在安装 Skype for Business Server 2019 之前可能需要安装哪些内容。 为了保持简单, 我们还包括一个键:
  
![这是用于 Skype for Business 拓扑图的图标的关键](../../SfbServer/media/cc0dbc17-cf81-4b79-bf99-4614cc6828a0.png)
  
#### <a name="single-forest-with-single-domain"></a>具有单个域的单林

![支持的 SFB 与 MA 拓扑，仅限云。](../../SfbServer/media/24921a0b-3a3e-4bad-8427-49300e2e3f7a.png)
  
它不会比此更容易;它是单个域林, 一个通用拓扑。
  
#### <a name="single-forest-with-a-single-tree-and-multiple-domains"></a>具有单个树和多个域的单林

![单林、单树和多个域图表](../../SfbServer/media/63b9f0dd-6bac-4ba9-ae68-8be032d09dcb.png)
  
此图表同样显示了一个林，但其中还有一个或多个子域（本例中为 3 个）。 因此, 在其中创建用户的域可能不同于将 Skype for business Server 2019 部署到的域。 为什么要考虑这一点？ 请务必记住, 在部署 Skype for business 服务器前端池时, 该池中的所有服务器都必须位于单个域中。 通过 Windows 通用管理员组的 Skype for Business 服务器支持, 你可以拥有跨域管理。
  
在上面的图表中, 你可以看到一个域中的用户可以从同一域或不同域访问 Skype for Business 服务器池, 即使这些用户位于子域中也是如此。
  
#### <a name="single-forest-with-multiple-trees-and-disjoint-namespaces"></a>具有多个树和互不连接的命名空间的单林

![单林、多个树和互不连接的命名空间图表](../../SfbServer/media/5ede77a1-f5d2-499c-a2c8-d02f3c2f7cd7.png)
  
你可能具有类似于此图表的拓扑, 其中你有一个林, 但在该林内是多个域, 具有单独的广告命名空间。 在这种情况下, 此图是一个很好的说明, 因为它包括访问 Skype for Business Server 2019 的三个不同域中的用户。 实线指示他们正在访问其自己的域中的 Skype for business 服务器池, 而虚线指示他们将转到其他树中的池。
  
正如你所见, 相同域、相同树, 甚至不同树的用户可以成功访问池。
  
#### <a name="multiple-forests-in-a-central-forest-topology"></a>中央林拓扑中的多林

![中央林拓扑中的多林图表](../../SfbServer/media/fec40746-4254-4c84-86b9-aad4a616ea2f.png)
  
Skype for Business Server 2019 支持在中央林拓扑中配置的多个林。 如果不确定你所拥有的内容, 则拓扑中的中央林将使用其中的对象来表示其他林中的用户, 并为林中的任何用户托管用户帐户。
  
工作原理是什么？ 目录同步产品 (如 Forefront Identity Manager 或 FIM) 在其现有范围内管理你的组织的用户帐户。 在林中创建或删除帐户时，更改将同步到中央林中的对应联系人。
  
很明显, 如果你的广告基础结构已就位, 则移动到此拓扑可能不太简单, 但是如果你已经存在, 或者仍在规划林基础结构, 则这可能是一个不错的选择。 你可以将 Skype for Business Server 2019 部署集中在单个林中, 用户可以搜索、通信和查看任何林中的其他用户的状态。 所有用户联系人更新都会通过同步软件自动得到处理。
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology"></a>Skype for Business 资源林拓扑中的多个林
<a name="BKMK_multipleforestopology"> </a>

![资源林拓扑图表中的多林](../../SfbServer/media/41efa3b6-d9e6-47df-992b-fefcfc39a80d.png)
  
还支持资源林拓扑;林专用于运行服务器应用程序的位置, 如 Microsoft Exchange Server 和 Skype for business Server 2019。 此资源林还承载着活动用户对象的同步表示形式，但不包含启用了登录的用户帐户。 因此资源林用作用户对象所驻留的其他林的共享服务环境，这些林与资源林之间存在林级信任关系。
  
请注意, Exchange Server 可以部署在与 Skype for Business 服务器相同的资源林中, 也可以部署在不同的林中。
  
若要在此类型的拓扑中部署 Skype for Business Server 2019, 你可以在资源目录林中为用户目录林中的每个用户帐户创建一个已禁用的用户对象 (如果 Microsoft Exchange Server 已在环境中, 可能会为你完成此操作)。 然后, 你需要目录同步工具 (如 Forefront Identity Manager 或 FIM), 以便通过其生命周期管理用户帐户。
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology-with-exchange-online"></a>具有 Exchange Online 的 Skype for Business 资源林拓扑中的多个林
<a name="BKMK_multipleforestopology"> </a>

此拓扑与 [Skype for Business 资源林拓扑中的多个林](system-requirements.md#BKMK_multipleforestopology)中所述的拓扑类似。
  
在此拓扑中, 有一个或多个用户林, 并且 Skype for business 服务器部署在专用资源目录林中。 Exchange Server 可以在同一资源林或不同的林中部署, 并且可以为混合与 Exchange Online 进行配置, 也可以专门为本地帐户提供 Exchange Online 提供的电子邮件服务。 目前没有该拓扑的示意图。
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-skype-for-business-online-and-azure-active-directory-connect"></a>有 Skype for Business Online 和 Azure Active Directory Connect 的资源林拓扑中的多个林
<a name="BKMK_multipleforestopology"> </a>

![显示两个 AD 林，一个用户林和一个资源林。这两个林具有信任关系。它们使用 Azure AD Connect 与 Office 365 同步。通过 Office 365 为所有用户启用 Skype for Business。](../../SfbServer/media/6d54558d-8786-4ebf-90f6-55ae3fdb5ae7.jpg)
  
在此方案中，一个资源林拓扑中有多个本地林。Active Directory 林之间为完全信任关系。Azure Active Directory Connect 工具用于在本地用户林和 Office 365 之间同步帐户。
  
 组织还具有 Office 365, 并使用[Azure Active Directory Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)将其本地帐户与 Office 365 同步。 已启用 Skype for business 的用户通过 Office 365 和 Skype for business Online 启用。 不在本地部署 Skype for business 服务器。
  
单一登录身份验证由位于用户林中的 Active Directory 联合身份验证服务场提供。
  
在此方案中, 支持部署 Exchange 本地、Exchange Online、混合 Exchange 解决方案, 或者根本不部署 Exchange。 (图表仅显示本地 Exchange, 但也完全支持其他 Exchange 解决方案。)
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-hybrid-skype-for-business"></a>有混合 Skype for Business 的资源林拓扑中的多个林
<a name="BKMK_multipleforestopology"> </a>

在此方案中, 有一个或多个本地用户林, 并且 Skype for business 部署在专用资源目录林中, 并针对具有 Skype for Business Online 的混合模式进行配置。 Exchange Server 可以在同一资源林或不同林中部署, 并且可以为混合使用 Exchange Online 进行配置。 或者, 电子邮件服务可能专为本地帐户的 Exchange Online 提供。
  
有关详细信息, 请参阅[为混合 Skype for Business 配置多林环境](../../SfbServer/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/configure-a-multi-forest-environment-for-hybrid.md)。
  
## <a name="domain-name-system-dns"></a>域名系统 (DNS)
<a name="DNS"> </a>

Skype for business 服务器2019需要 DNS, 原因如下:
  
- DNS 使 Skype for business Server 2019 能够发现内部服务器或池, 从而实现服务器到服务器的通信。
    
- DNS 允许客户端计算机发现用于 SIP 事务的前端池或标准版服务器。
    
- 它会将会议的简单 URL 与托管这些会议的服务器相关联。
    
- DNS 允许外部用户和客户端计算机连接到边缘服务器或 HTTP 反向代理, 以便发送即时消息 (IM) 或会议。
    
- 它允许未登录的统一通信 (UC) 设备发现运行设备更新 web 服务的前端池或标准版服务器以获取更新和发送日志。
    
- 使用 DNS 使移动客户端可以自动发现 Web 服务资源，而无需用户在设备设置中手动输入 URL。
    
- 它在 DNS 负载平衡中使用。
    
请务必注意, Skype for business 服务器2019不支持国际化域名 (IDNs)。
  
这一点非常重要, 请记住, DNS 中的任何名称与 Skype for business Server 2019 使用的任何服务器上配置的计算机名称相同。 具体说来, 在环境中不能有任何短名称, 并且拓扑生成器必须具有 Fqdn。
  
这似乎是已加入域的任何计算机的逻辑, 但如果你有未加入到你的域的边缘服务器, 则它可能具有一个短名称的默认值, 没有域后缀。 请确保在 DNS 或边缘服务器上, 或在此情况下的任何 Skype for business Server 2019 服务器或池中都不是这种情况。
  
绝对不要使用 Unicode 字符或下划线。 标准字符 (Z、A-z、0-9 和连字符) 受外部 DNS 和公共证书颁发机构支持 (需要将 Fqdn 分配给证书中的 SN), 因此, 如果您使用名称, 您将会在很大程度上为您带来许多麻烦。在开始时, 请注意这一点。
  
若要进一步了解网络 DNS 要求，请查看我们的规划文档的[Networking](../../SfbServer/plan-your-deployment/network-requirements/network-requirements.md)部分。
  
## <a name="certificates"></a>证书
<a name="Certs"> </a>

在部署之前，您要做的一件最重要的事情就是确保证书有条不紊。 Skype for Business Server 2019 需要用于传输层安全 (TLS) 和相互传输层安全性 (MTLS) 连接的公钥基础结构 (PKI)。 基本上, 若要以标准化方式安全地通信, Skype for business 服务器将使用由证书颁发机构 (Ca) 颁发的证书。
  
以下是 Skype for Business Server 2019 使用证书的一些内容:
  
- 客户端与服务器之间的 TLS 连接
    
- 服务器之间的 MTLS 连接
    
- 使用合作伙伴的自动 DNS 发现的联盟
    
- 远程用户访问即时消息 (IM)
    
- 外部用户访问音频/视频 (AV) 会话、应用程序共享和会议
    
- 与 web 应用程序和 Outlook Web Access (OWA) 通话
    
因此, 认证计划是必需的。 现在, 我们来看一下申请证书时需要记住的一些事项的列表:
  
- 所有服务器证书都必须支持服务器授权（服务器 EKU）。
    
- 所有服务器证书都必须包含一个 CRL 分发点 (CDP)。
    
- 所有证书必须使用操作系统支持的签名算法进行签名。 Skype for Business Server 2019 支持 SHA-1 和 SHA-1 系列的摘要大小 (224、256、384和 512), 并且满足或超过操作系统要求。
    
- 对于运行 Skype for Business Server 2019 的内部服务器, 自动注册受支持。
    
- Skype for business Server 2019 Edge 服务器不支持自动注册。
    
> [!NOTE]
> 不支持使用 RSASSA-PSS 签名算法，否则可能导致登录错误、呼叫转接问题及其他问题。 
  
- 加密密钥长度为 1024、2048 和 4096。建议使用密钥长度 2048 和更大值。
    
- 默认的摘要式或哈希签名算法是 RSA。还支持 ECDH_P256、ECDH_P384 和 ECDH_P521 算法。
    
需要考虑的很多, 并且从 CA 申请证书有各种舒适的级别。 下面我们将向您提供进一步的指导, 让您的计划尽可能顺利。
  
### <a name="certificates-for-your-internal-servers"></a>内部服务器的证书

你将需要大多数内部服务器的证书, 并且很可能会收到来自内部 CA 的证书 (这是您的域中的 CA)。 如果需要, 您可以从外部 CA (位于 Internet 上的 CA) 申请这些证书。 如果想知道应该转到的公共 CA, 可以查看 "[统一通信证书合作伙伴](https://support.microsoft.com/kb/929395/en-us)" 列表。
  
当 Skype for Business Server 2019 与其他应用程序和服务器 (如 Microsoft Exchange Server) 通信时, 你还将需要证书。 显然, 这将需要成为其他这些应用和服务器可以以受支持的方式使用的证书。 Skype for Business Server 2019 和其他 Microsoft 产品支持用于服务器到服务器身份验证和授权的开放授权 (OAuth) 协议。 如果你对此感兴趣, 我们将为 OAuth 和 Skype for business Server 2019 添加一个计划文章。
  
Skype for Business Server 2019 还包括对 (不需要) 使用 SHA-256 加密哈希函数签名的证书的支持。 要支持使用 SHA-256 进行外部访问，外部证书必须由公共 CA 使用 SHA-256 颁发。
  
为使内容保持简单明了, 我们已将标准版服务器、前端池和其他角色的证书要求置于下表中, 使用虚构的 contoso.com 用于示例 (你可能会使用其他内容你的环境)。 这些均为标准 Web 服务器证书，使用不可导出的私钥。 此外还应注意：
  
- 使用证书向导请求证书时会自动配置服务器增强型密钥使用 (EKU)。
    
- 每个证书友好名称在计算机存储中均必须是唯一的。
    
- 根据下面的示例名称, 如果你已在 DNS 中配置了 sipinternal.contoso.com 或 sipexternal.contoso.com, 则需要将它们添加到证书的使用者备用名称 (SAN)。
    
标准版服务器的证书:
  
|**证书**|**使用者名称/常用名称**|**使用者替代名称**|**示例**|**注释**|
|:-----|:-----|:-----|:-----|:-----|
|默认  <br/> |池的 FQDN  <br/> |池的 FQDN 和服务器的 FQDN  <br/> 如果具有多个 SIP 域并已启用自动客户端配置，则证书向导会检测并添加所有受支持的 SIP 域 FQDN。  <br/> 如果此池是客户端的自动登录服务器，而且组策略要求执行严格的域名系统 (DNS) 匹配，那么还需要 sip.sipdomain 条目（对应于您拥有的每个 SIP 域）。  <br/> |SN=se01.contoso.com; SAN=se01.contoso.com  <br/> 如果此池是客户端的自动登录服务器，而且组策略要求执行严格的 DNS 匹配，则还需要 SAN=sip.contoso.com; SAN=sip.fabrikam.com。  <br/> |在标准版服务器上, 服务器 FQDN 与池 FQDN 相同。  <br/> 证书向导会检测您在安装过程中所指定的任何 SIP 域，然后自动将它们添加到使用者可选名称中。  <br/> 也可将此证书用于服务器到服务器身份验证。  <br/> |
|Web 内部  <br/> |服务器的 FQDN  <br/> |以下各项：  <br/> •内部 web FQDN (与服务器的 FQDN 相同)  <br/> 和  <br/> •满足简单的 Url  <br/> •拨入式简单 URL  <br/> •管理员简单 URL  <br/> 或者  <br/> •简单 Url 的通配符条目  <br/> |SN=se01.contoso.com; SAN=se01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> 使用通配符证书：  <br/> SN = se01;SAN = se01;SAN =\*contoso.com  <br/> |不能在拓扑生成器中替代内部 web FQDN。  <br/> 如果你有多个符合简单的 Url, 则必须将它们作为 SANs 包括在内。  <br/> 简单 URL 条目支持通配符条目。  <br/> |
|Web 外部  <br/> |服务器的 FQDN  <br/> |以下各项：  <br/> •外部 web FQDN  <br/> 和  <br/> •拨入式简单 URL  <br/> •满足每个 SIP 域的简单 Url  <br/> 或者  <br/> •简单 Url 的通配符条目  <br/> |SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> 使用通配符证书：  <br/> SN = se01;SAN = webcon01;SAN =\*contoso.com  <br/> |如果你有多个满足简单的简单 Url, 则必须将它们全部包含为主题备用名称。  <br/> 简单 URL 条目支持通配符条目。  <br/> |
   
前端池中的前端服务器的证书:
  
|**证书**|**使用者名称/常用名称**|**使用者替代名称**|**示例**|**注释**|
|:-----|:-----|:-----|:-----|:-----|
|默认值  <br/> |池的 FQDN  <br/> |池的 FQDN 和服务器的 FQDN  <br/> 如果具有多个 SIP 域并已启用自动客户端配置，则证书向导会检测并添加所有受支持的 SIP 域 FQDN。  <br/> 如果此池是客户端的自动登录服务器，而且组策略要求执行严格的域名系统 (DNS) 匹配，那么还需要 sip.sipdomain 条目（对应于您拥有的每个 SIP 域）。  <br/> |SN=eepool.contoso.com; SAN=eepool.contoso.com; SAN=ee01.contoso.com   <br/> 如果此池是客户端的自动登录服务器，而且组策略要求执行严格的 DNS 匹配，则还需要 SAN=sip.contoso.com; SAN=sip.fabrikam.com。  <br/> |证书向导会检测您在安装过程中所指定的任何 SIP 域，然后自动将它们添加到使用者可选名称中。  <br/> 也可将此证书用于服务器到服务器身份验证。  <br/> |
|Web 内部  <br/> |池的 FQDN  <br/> |以下各项：  <br/> •内部 web FQDN (与服务器的 FQDN 不同)  <br/> •服务器 FQDN  <br/> • Skype for Business 池 FQDN  <br/> 和  <br/> •满足简单的 Url  <br/> •拨入式简单 URL  <br/> •管理员简单 URL  <br/> 或者  <br/> •简单 Url 的通配符条目  <br/> |SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> 使用通配符证书：  <br/> SN = ee01;SAN = ee01;SAN =\*contoso.com  <br/> |如果你有多个满足简单的简单 Url, 则必须将它们全部包含为主题备用名称。  <br/> 简单 URL 条目支持通配符条目。  <br/> |
|Web 外部  <br/> |池的 FQDN  <br/> |以下各项：  <br/> •外部 web FQDN  <br/> 和  <br/> •拨入式简单 URL  <br/> •管理员简单 URL  <br/> 或者  <br/> •简单 Url 的通配符条目  <br/> |SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> 使用通配符证书：  <br/> SN = ee01;SAN = webcon01;SAN =\*contoso.com  <br/> |如果你有多个满足简单的简单 Url, 则必须将它们全部包含为主题备用名称。  <br/> 简单 URL 条目支持通配符条目。  <br/> |
   
导演的证书:
  
|**证书**|**使用者名称/常用名称**|**使用者替代名称**|**示例**|
|:-----|:-----|:-----|:-----|
|默认值  <br/> |控制器池  <br/> |Director 的 FQDN, Director pool 的 FQDN。  <br/> 如果此池是客户端的自动登录服务器, 并且组策略需要严格的 DNS 匹配, 则你还需要 sipdomain (对于你拥有的每个 SIP 域) 的条目。  <br/> |pool.contoso.com; SAN=dir01.contoso.com   <br/> 如果此控制器池是客户端的自动登录服务器, 并且组策略需要严格的 DNS 匹配, 你还需要 SAN = sip。SAN = sip  <br/> |
|Web 内部  <br/> |服务器的 FQDN  <br/> |以下各项：  <br/> •内部 web FQDN (与服务器的 FQDN 相同)  <br/> •服务器 FQDN  <br/> • Skype for Business 池 FQDN  <br/> 和  <br/> •满足简单的 Url  <br/> •拨入式简单 URL  <br/> •管理员简单 URL  <br/> 或者  <br/> •简单 Url 的通配符条目  <br/> |SN=dir01.contoso.com; SAN=dir01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> 使用通配符证书：  <br/> SN = dir01;SAN = dir01 SAN =\*contoso.com  <br/> |
|Web 外部  <br/> |服务器的 FQDN  <br/> |以下各项：  <br/> •外部 web FQDN  <br/> 和  <br/> •满足每个 SIP 域的简单 Url  <br/> •拨入式简单 URL  <br/> 或者  <br/> •简单 Url 的通配符条目  <br/> |控制器外部 web FQDN 必须不同于前端池或前端服务器。  <br/> SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> 使用通配符证书：  <br/> SN = dir01;SAN = directorwebcon01 SAN =\*contoso.com  <br/> |
   
独立中介服务器的证书:
  
|**证书**|**使用者名称/常用名称**|**使用者替代名称**|**示例**|
|:-----|:-----|:-----|:-----|
|默认值  <br/> |池的 FQDN  <br/> |池的 FQDN  <br/> 池成员服务器的 FQDN  <br/> |SN=medsvr-pool.contoso.net; SAN=medsvr-pool.contoso.net; SAN=medsvr01.contoso.net  <br/> |
   
Survivable 分支装置的证书 (特别是 Skype for business Server 2019 的 Survivable 分支装置 2015):
  
|**证书**|**使用者名称/常用名称**|**使用者替代名称**|**示例**|
|:-----|:-----|:-----|:-----|
|默认  <br/> |设备的 FQDN  <br/> |SIP.\<sipdomain\> (每个 SIP 域仅需要一个条目)  <br/> |SN=sba01.contoso.net; SAN=sip.contoso.com; SAN=sip.fabrikam.com  <br/> |
   
### <a name="certificates-for-external-user-access-edge"></a>外部用户访问（边缘）的证书

Skype for Business Server 2019 支持使用**单个公共证书**访问和网络会议边缘外部接口, 以及 a/V 身份验证服务, 该服务均通过 Edge 服务器提供。 你的边缘内部接口通常使用由你的内部 CA 颁发的专用证书, 但如果你愿意, 也可以使用公共证书 (如果该证书来自受信任的 CA)。
  
反向代理 (RP) 也会使用公共证书，并会使用 HTTP（更精确地说，是 HTTP 上的 TLS）对 RP 与客户端以及 RP 与内部服务器之间的通信进行加密。
  
### <a name="certificates-for-mobility"></a>移动证书

如果你正在部署移动性, 并且你支持移动客户端的自动发现, 你将需要在你的证书上包含一些其他主题替换名称条目以支持来自移动客户端的安全连接。
  
您需要在以下证书上自动发现的 SAN 名称:
  
- 控制器池
    
- 前端池
    
- 反向代理
    
下表列出了详细信息。
  
这是一个很好的预计划, 但有时你已经部署了 Skype for Business Server 2019, 而无需部署移动性, 并且稍后在你的环境中已有证书。 通过内部 CA 重新颁发证书通常比较简单，但如果使用的是公共 CA 颁发的公共证书，则可能代价高昂。
  
如果你正在查看此内容, 并且你有很多 SIP 域 (这会增加 SAN 的费用), 则可以将反向代理配置为对初始自动发现服务请求使用 HTTP, 而不是使用 HTTPS (这是默认值)配置)。 [针对移动性](../../SfbServer/plan-your-deployment/mobility.md)文章的计划包含详细信息。
  
控制器池和前端池证书要求:
  
|**说明**|**SAN 条目**|
|:-----|:-----|
|内部自动发现服务 URL  <br/> |SAN = lyncdiscoverinternal。\<sipdomain\>  <br/> |
|外部自动发现服务 URL  <br/> |SAN = lyncdiscover。\<sipdomain\>  <br/> |
   
您也可以使用 SAN =\*。\<sipdomain\>
  
反向代理（公共 CA）证书要求：
  
|**说明**|**SAN 条目**|
|:-----|:-----|
|外部自动发现服务 URL  <br/> |SAN = lyncdiscover。\<sipdomain\>  <br/> |
   
此 SAN 需要分配给已分配到反向代理上的 SSL 侦听器的证书。
  
> [!NOTE]
> 你的反向代理侦听器将具有适用于你的外部 Web 服务 URL 的 SANs。 如果你部署了 Director (可选), 则某些示例将是 SAN = skypewebextpool01 和 dirwebexternal.contoso.com。 
  
## <a name="file-share"></a>文件共享
<a name="Fileshare"> </a>

Skype for Business Server 2019 可以对所有文件存储使用相同的文件共享。 但您需要注意以下事项：
  
- 文件共享需要置于直接附加存储 (DAS) 或存储区域网络 (SAN) 上，其中包括分布式文件系统 (DFS) 以及文件存储的独立磁盘冗余阵列 (RAID)。 有关 DFS for Windows Server 2012 的进一步阅读, 请查看[此 DFS 页面](https://technet.microsoft.com/en-us/library/jj127250.aspx)。
    
- 建议为文件共享使用共享群集。 如果你使用的是, 则应群集 Windows Server 2012 或 Windows Server 2012 R2。 为什么要安装最新的 Windows？ 较旧的版本可能不具备启用所有功能的正确权限。 你可以使用群集管理器创建文件共享, 此[创建群集](https://support.microsoft.com/en-us/help/224967)知识库文章将帮助你了解这些详细信息。
    
> [!CAUTION]
> 您应知道，不支持将网络附加存储 (NAS) 用作文件共享，因此，请使用上述其中一个选项。 
  








