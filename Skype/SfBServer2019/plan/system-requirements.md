---
title: Skype for Business Server 2019 的系统要求
ms.reviewer: ''
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: ''
description: 摘要：利用本主题准备 Skype for Business Server 2019 服务器和域基础结构。 这里提供了硬件、OS、数据库、软件、所有系统要求和建议以及证书 DNS、文件共享和 Active Directory 信息，可帮助确保服务器场的安装和部署获得成功。
ms.openlocfilehash: c6f30ad4caa8dcb31cf035c3f82de4ab87c41f3d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812590"
---
# <a name="system-requirements-for-skype-for-business-server-2019"></a>Skype for Business Server 2019 的系统要求
 
**摘要：** 利用本主题准备安装 Skype for Business Server 2019。 此处介绍了硬件、OS、软件、数据库、证书、Active Diretory、DNS 和文件共享。 所有系统要求和建议均可帮助确保服务器场的安装和部署获得成功。
  
如你所想，这些只是开始部署 Skype for Business Server 2019 之前的一些准备工作。 本文将指导你完成以下各项的规划：
  
- [硬件](system-requirements.md#Hardware)
  
- [操作系统](system-requirements.md#OS)
  
- [软件](system-requirements.md#Software)

- [后端 SQL 数据库](system-requirements.md#DBs)
  
- [Active Directory](system-requirements.md#AD)
  
- [域名系统 (DNS)](system-requirements.md#DNS)
  
- [证书](system-requirements.md#Certs)
  
- [文件共享](system-requirements.md#Fileshare)

  
## <a name="hardware-for-skype-for-business-server-2019"></a>适用于 Skype for Business Server 2019 的硬件
<a name="Hardware"> </a>

在关闭拓扑（如果还没有，请参阅 [Skype for Business Server 2019 的拓扑和并置](../../SfbServer/plan-your-deployment/topology-basics/topology-basics.md)主题）后，下面就该考虑服务器了。 Skype for Business Server 2019 服务器需要 64 位硬件。 下面是针对硬件的建议。 这些并非强制要求，但它反映了实现最优性能所需要满足的要求。 我们提供了容量规划文档，可帮助你根据自身情况确定是否需要更多容量。
  
标准版服务器的推荐硬件：

|**硬件组件**|**推荐**|
|:-----|:-----|
|CPU  <br/> |Intel Xeon E5-2673 v3 双处理器，6 核，2.4 GHz 或更快。  <br/> Skype for Business Server 2019 角色不支持 Intel Itanium 处理器。  <br/> |
|内存  <br/> |32 GB。  <br/> |
|磁盘  <br/> |以下之一：  <br/> • 8 块或更多 10000 RPM 硬盘，至少 72 GB 可用磁盘空间（2 块磁盘使用 RAID 1，6 块磁盘使用 RAID 10）。  <br/> 或  <br/> • 能够提供与 8 块 10000 RPM 机械硬盘相同的可用空间和类似性能的固态硬盘 (SSD)。  <br/> |
|网络  <br/> |1 个双端口网络适配器，1 Gbps 或更高（可使用 2 个网络适配器，但需要通过一个 MAC 地址和一个 IP 地址配合使用）。  <br/> 前端服务器、后端服务器和标准版服务器**不**支持双宿主或多宿主配置。 <br/> 只要它们不接触操作系统并且被用于监控和管理服务器硬件，你就能够拥有带外管理系统，如 DRAC 或 ILO。 这种情况不会形成多宿主服务器，并且受支持。  <br/> |


前端服务器和后端服务器的推荐硬件：
  
|**硬件组件**|**推荐**|
|:-----|:-----|
|CPU  <br/> |Intel Xeon E5-2673 v3 双处理器，6 核，2.4 GHz 或更快。 <br/> Skype for Business Server 2019 角色不支持 Intel Itanium 处理器。  <br/> |
|内存  <br/> |64 GB。  <br/> |
|磁盘  <br/> |以下之一：  <br/> • 8 块或更多 10000 RPM 硬盘，至少 72 GB 可用磁盘空间（2 块磁盘使用 RAID 1，6 块磁盘使用 RAID 10）。  <br/> 或  <br/> • 能够提供与 8 块 10000 RPM 机械硬盘相同的可用空间和类似性能的固态硬盘 (SSD)。  <br/> |
|网络  <br/> |1 个双端口网络适配器，1 Gbps 或更高（可使用 2 个网络适配器，但需要通过一个 MAC 地址和一个 IP 地址配合使用）。  <br/> 前端服务器、后端服务器和标准版服务器**不**支持双宿主或多宿主配置。 <br/> 只要它们不接触操作系统并且被用于监控和管理服务器硬件，你就能够拥有带外管理系统，如 DRAC 或 ILO。 这种情况不会形成多宿主服务器，并且受支持。  <br/> |
   
边缘服务器、独立中介服务器和控制器的推荐硬件：
  
|**硬件组件**|**推荐**|
|:-----|:-----|
|CPU  <br/> |Intel Xeon E5-2673 v3 双处理器，6 核，2.4 GHz 或更快。  <br/> Skype for Business Server 2019 角色不支持 Intel Itanium 处理器。  <br/> |
|内存  <br/> |32 GB。  <br/> |
|磁盘  <br/> |以下之一：  <br/> • 4 块或更多 10000 RPM 硬盘，至少 72 GB 可用磁盘空间（磁盘应采用双 RAID 1 配置）。  <br/> 或  <br/> • 能够提供与 4 块 10000 RPM 机械硬盘相同的可用空间和类似性能的固态硬盘 (SSD)。  <br/> |
|网络  <br/> |1 个双端口网络适配器，1 Gbps 或更高（可使用 2 个网络适配器，但需要通过一个 MAC 地址和一个 IP 地址配合使用）。  <br/> 视频互操作服务器和控制器**不**支持双宿主或多宿主配置。 <br/> 边缘服务器需要两个网络接口，均为双端口网络适配器、1 Gbps 或更高速度（或两个成对网络适配器，总计 4 个适配器，每一对均与单一 MAC 地址和单一 IP 地址配合使用，总共两对）。  <br/> 在独立中介服务器上，支持安装额外的网络接口卡 (NIC) 以允许配置特定的 PSTN IP 地址。  <br/> |


> [!NOTE]
> 无论服务器角色如何，我们也建议为 Skype for Business Server 2019 采用以下硬件设置（这可能因购买的硬件品牌而异，请参阅制造商文档了解详细信息）：
> - BIOS 配置 - 应该从 NUMA 设置为 FLAT。
> - 启用超线程。
> - RSS 队列设置应设为 8 队列。

   
## <a name="operating-systems-for-skype-for-business-server-2019"></a>适用于 Skype for Business Server 2019 的操作系统
<a name="OS"> </a>

具备硬件之后，你需要安装操作系统 (OS)，它将允许你安装并成功使用 Skype for Business Server 2019。
  
|||
|:-----|:-----|
|Windows Server 2019 <br/> |
|Windows Server 2016 <br/> ||
||
   
除此处列出的操作系统外，其他任何操作系统均无法正常工作；请不要尝试使用其他操作系统来安装 Skype for Business Server 2019。 例如，“服务器核心”选项未列出，因此它不受支持。  注意： Lync Server 2013 不支持操作系统就地升级。  必须部署单独的池并将用户迁移到具有不同操作系统的新池。

> [!NOTE]
> 
> 如果在 Windows Server 2019 计算机上安装 Windows Admin Center 2019，系统会提示你提供侦听端口。 你可能会选择端口 443，但是如果该计算机上安装了 Skype for Business Server 2019，或者要在其上安装 Skype for Business Server 2019，则必须选择其他端口号。
> 
>为什么会这样呢？ 如果 Windows Admin Center 2019 在端口 443 上运行，则无法使用 Skype for Business 控制面板连接到服务器，也无法连接到服务器上运行的任何内部 Web 服务（通讯簿 Web 服务、自动发现服务、WebTicket 服务等）。  实际上，你将无法连接到任何内部 Web 服务 URL。 如果你需要或希望将 Windows Admin Center 2019 安装在具有 Skype for Business Server 2019 的服务器上，请选择其他端口。
> 

  
## <a name="software-that-should-be-installed-before-a-skype-for-business-server-2019-deployment"></a>应在 Skype for Business Server 2019 部署之前安装的软件
<a name="Software"> </a>

要为任何运行 Skype for Business Server 2019 的服务器进行安装和配置，你需要满足一些条件，如下所示。 下面列出了这些条件，后面是针对特定服务器角色的其他要求。

> [!IMPORTANT]
> Skype For Business 2019 支持 .Net Framework 4.8。 
  
 **所有服务器：**
  
|**软件/角色**|**详细信息**|
|:-----|:-----|
|Windows PowerShell 3.0  <br/> |所有 Skype for Business Server 服务器均需安装 Windows PowerShell 3.0。  <br/> • 默认情况下，它应随 Windows Server 2016 一起安装。<br/> |
|Microsoft .NET Framework  <br/> |WCF 服务**功能**作为**服务器管理器**下的 Windows 功能安装，最初无需下载。 <br/> • 在安装此功能时，或者在系统中已经安装此功能而你在执行检查时，务必确保已经选中并且安装了 **HTTP 激活**选项，如下所示： <br/> ![屏幕截图显示 .NET Framework 4.5 功能下的 HTTP 激活选项。](../../SfbServer/media/a4064fa0-fa49-4474-bd98-b9a79ff68f8b.png) <br/> 如果你看到另一则弹出信息，表示要安装“HTTP 激活”，还需要安装其他某些功能，请不必担心。 这种情况非常正常，只要单击“确定”，继续操作即可。 如果未看到此弹出信息，则可以假设这些功能均已安装，你可以继续操作。  <br/> 如果已安装 Windows Server 2016，通常会安装 Microsoft .NET Framework。 但是，Skype for Business Server 需要 Microsoft .NET Framework 4.7 或 4.8，因此你可能需要更新它。 可在[此处](https://support.microsoft.com/help/3186497/the-net-framework-4-7-offline-installer-for-windows/)查找更新<br/> |
|媒体基础  <br/> |对于 Windows Server 2016，请使用 Microsoft 媒体基础安装 Windows Media Format Runtime。  <br/> 所有用于会议的前端服务器和标准版服务器都需要 Windows Media Format Runtime 来运行 Windows Media Audio (.wma) 文件，呼叫寄存、公告和响应组应用程序将通过该文件来播放公告和音乐。  <br/> |
|Windows Identity Foundation  <br/> |我们需要 Windows Identity Foundation 3.5 来支持 Skype for Business Server 2019 的服务器到服务器身份验证情景。  <br/> • 对于 Windows Server 2016，不需要下载任何内容。 打开**服务器管理器**，转到**添加角色和功能向导**。 **Windows Identity Foundation 3.5** 在**功能**部分列出。 如果它已选中，则没有问题。 否则请选中它，并单击“**下一步**”，然后单击“**安装**”按钮。 <br/> |
|远程服务器管理工具  <br/> |角色管理工具：AD DS 和 AD LDS 工具  <br/> |
   
 **前端服务器和标准版服务器也需要：**
  
|**软件/角色**|**详细信息**|
|:-----|:-----|
|Internet 信息服务 (IIS)  <br/> |所有前端服务器以及所有标准版服务器都需要 IIS，选择以下模块：  <br/> • 常用 HTTP 功能：默认文档、HTTP 错误、静态内容  <br/> • 运行状况和诊断：HTTP 日志记录、日志记录工具、跟踪  <br/> • 性能：静态内容压缩、动态内容压缩  <br/> • 安全性：请求筛选、客户端证书映射身份验证、Windows 身份验证  <br/> • 应用程序开发：.NET Extensibility 3.5、.NET Extensibility 4.5、ASP.NET 3.5、ASP.NET 4.5、ISAPI 扩展、ISAPI 筛选器  <br/> • 管理工具：IIS 管理控制台、IIS 管理脚本和工具  <br/> 请注意，还需要使用匿名访问，但在安装 IIS 时即可安装此功能，因此该列表中未提供选择此项功能的选项。  <br/> |
|Windows Media Format Runtime  <br/> | 对于 Windows Server 2016，你需要在**服务器管理器**中安装**媒体基础**功能。 你可以在无此项功能的情况下启动 Skype for Business Server 2019 安装，但系统会提示你安装此功能，随后重新启动服务器，之后才能继续安装 Skype for Business Server 2019。 因此最好提前安装。 <br/> |
|Silverlight  <br/> |你可以从[此处](https://www.microsoft.com/silverlight/)安装最新版本的 Silverlight。  <br/> |
   
为帮助你了解相关过程，我们提供了一个示例 PowerShell 脚本，你可以运行此脚本以自动执行此流程：
  
```PowerShell
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Windows-Identity-Foundation, Server-Media-Foundation, Telnet-Client, BITS, ManagementOData, Web-Mgmt-Console, Web-Metabase, Web-Lgcy-Mgmt-Console, Web-Lgcy-Scripting, Web-WMI, Web-Scripting-Tools, Web-Mgmt-Service
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
    
（你或许会感到好奇，此模块集合确实与前端服务器和标准版服务器相同，只是没有包含动态内容压缩和管理工具。）
  
我们还为此提供了以下一些 PowerShell 代码：
  
```PowerShell
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, Telnet-Client
```

## <a name="back-end-databases-that-will-work-with-skype-for-business-server-2019"></a>将与 Skype for Business Server 2019 配合工作的后端数据库
<a name="DBs"> </a>

安装 Skype for Business Server 2019 标准版时，你将拥有 SQL Server 2016 Express（64 位版本）。

Skype for Business Server 2019 企业版将需要完整的 SQL Server，如下所示（仅限 64 位版本；请不要使用 32 位版本）：
  
||||
|:-----|:-----|:-----|
|Microsoft SQL Server 2019（64 位版本），并且必须运行最新更新。  <br/> |Microsoft SQL Server 2017（64 位版本），并且必须运行最新更新。  <br/> |
Microsoft SQL Server 2016（64 位版本），并且必须运行最新更新。|
 |

如果你想使用的 SQL Server 版本未列于此处，则不能使用。
  
> [!NOTE]
> 你还需要为“监控服务器”角色安装 SQL Server Reporting Services。 
  
### <a name="sql-clustering-and-sql-always-on"></a>SQL 群集和 SQL Always On

支持将 SQL 群集与 Skype for Business Server 2019 结合使用。 如果想要设置 SQL 群集，可在 SQL Server 中完成。
  
确保为 SQL 群集提供主动/被动配置，因为只有此配置才受支持。 请勿与任何其他 SQL 实例共享被动节点。
  
可以为故障转移群集采用以下配置：
  
双节点：
  
- Microsoft SQL Server 2019 标准版（64 位版本），建议运行最新的 Service Pack。
- Microsoft SQL Server 2017 标准版（64 位版本），建议运行最新的 Service Pack。
- Microsoft SQL Server 2016 标准版（64 位版本），建议运行最新的 Service Pack。

16 节点：
  
- Microsoft SQL Server 2019 企业版（64 位版本），建议运行最新的 Service Pack。
- Microsoft SQL Server 2017 企业版（64 位版本），建议运行最新的 Service Pack。
- Microsoft SQL Server 2016 企业版（64 位版本），建议运行最新的 Service Pack。

支持 SQL Always On，你可以在 [Skype for Business Server 2019 中的后端服务器高可用性](../../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md)中了解更多相关信息。
  

###  <a name="additional-server-installation-recommendations"></a>其他服务器安装建议：
  
请勿在任何前端服务器或独立中介服务器上安装任何 Microsoft Internet Security and Acceleration (ISA) Server 客户端软件或其他任何 Winsock 分层服务提供程序 (LSP) 软件（包括任何第三方防火墙或防病毒网络监测软件）。 我们注意到安装此类软件会导致媒体流性能低下。
  

## <a name="active-directory"></a>Active Directory
<a name="AD"> </a>

虽然服务器和服务的大量配置数据存储在 Skype for Business Server 2019 中央管理存储中，但某些内容仍存储在 Active Directory 中：
  
|**Active Directory 对象**|**对象类型**|
|:-----|:-----|
|架构扩展  <br/> |用户对象扩展  <br/> |
||用于 Skype for Business Server 2015 和 Lync Server 2013 的扩展，旨在保持与先前受支持版本的向后兼容性  <br/> |
|Data  <br/> |用户 SIP URI 和其他用户设置  <br/> |
||应用程序的联系对象（如响应组应用程序和会议助理应用程序）  <br/> |
||为实现向后兼容而发布的数据  <br/> |
||中央管理存储的服务控制点 (SCP)  <br/> |
||Kerberos 身份验证帐户（可选计算机对象）  <br/> |
   
### <a name="os-for-domain-controllers"></a>域控制器的操作系统

可使用以下域控制器操作系统：
  
- Windows Server 2019

- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
部署 Skype for Business Server 2019 的任何域的域功能级别，以及部署 Skype for Business Server 2019 的任何林的林功能级别都必须使用以下操作系统之一：
  
- Windows Server 2019

- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
这些环境中能否有只读域控制器？ 当然可以，只要另外有可写入的域控制器即可。
  
请务必知悉，Skype for Business Server 2019 不支持单标签域。 单标签域是什么？ 如果一个根域带有 contoso.local 标签，那么不会有任何问题。 而如果一个根域直接命名为 local，则无法工作，也就是说不支持这种命名方式。 [知识库中的这篇文章](https://support.microsoft.com/kb/300684/)略为详细地介绍了相关内容。
  
Skype for Business Server 2019 也不支持重命名域。 如果确实必须重命名域，则需要卸载 Skype for Business Server 2019，重命名域，然后重新安装 Skype for Business Server 2019。
  
最后，你还可能遇到具有锁定的 AD DS 环境的域，这种域不会产生任何问题。 部署文档中提供了有关如何将 Skype for Business Server 2019 部署到锁定的 AD DS 环境的详细信息。
  
### <a name="ad-topologies"></a>AD 拓扑

Skype for Business Server 2019 支持的拓扑包括：
  
- 具有单个域的单林
    
- 具有单个树和多个域的单林
    
- 具有多个树和互不连接的命名空间的单林
    
- 中央林拓扑中的多林
    
- 资源林拓扑中的多林
    
- 具有 Exchange Online 的 Skype for Business 资源林拓扑中的多个林
    
- 具有 Skype for Business Online 和 Azure Active Directory Connect 的资源林拓扑中的多个林
    
我们提供了图表和说明来帮你确定环境中目前使用的是何种拓扑，或者在安装 Skype for Business Server 2019 之前需要设置何种拓扑。 为简单起见，我们还提供了密钥：
  
![这是用于 Skype for Business 拓扑图的图标的关键](../../SfbServer/media/cc0dbc17-cf81-4b79-bf99-4614cc6828a0.png)
  
#### <a name="single-forest-with-single-domain"></a>具有单个域的单林

![具有单个域的 Active Directory 单林图表](../../SfbServer/media/24921a0b-3a3e-4bad-8427-49300e2e3f7a.png)
  
最简单也是极为常见的一种拓扑，仅有一个域林。
  
#### <a name="single-forest-with-a-single-tree-and-multiple-domains"></a>具有单个树和多个域的单林

![单林、单树和多个域图表](../../SfbServer/media/63b9f0dd-6bac-4ba9-ae68-8be032d09dcb.png)
  
此图表同样显示了一个林，但其中还有一个或多个子域（本例中为 3 个）。 因此用于创建用户的域可能不同于部署 Skype for Business Server 2019 的域。 为什么要考虑这一点？ 请牢记，在部署 Skype for Business Server 前端池时，池中的所有服务器都必须位于单个域中。 你可以通过 Skype for Business Server 对 Windows 通用管理员组的支持实现跨域管理。
  
在上面的图表中，你可以看到，一个域中的用户可以访问相同域或不同域中的 Skype for Business Server 池，即便这些用户身处子域时也是如此。
  
#### <a name="single-forest-with-multiple-trees-and-disjoint-namespaces"></a>具有多个树和互不连接的命名空间的单林

![单林、多个树和互不连接的命名空间图表](../../SfbServer/media/5ede77a1-f5d2-499c-a2c8-d02f3c2f7cd7.png)
  
你可能拥有类似于此图表所示的拓扑，包括一个林，但在该林内有多个域，而且使用不同的 AD 命名空间。 如果是这样，那么这个图表就是很好的演示，因为其中有三个不同域中的用户在访问 Skype for Business Server 2019。 实线表示他们访问的是自身所在域中的 Skype for Business Server 池，虚线表示他们在访问不同树中的池。
  
你可以看到，相同域、相同树甚至不同树中的用户都能成功访问池。
  
#### <a name="multiple-forests-in-a-central-forest-topology"></a>中央林拓扑中的多林

![中央林拓扑中的多林图表](../../SfbServer/media/fec40746-4254-4c84-86b9-aad4a616ea2f.png)
  
Skype for Business Server 2019 支持在中央林拓扑中配置的多个林。 如果你不确定自己的拓扑结构，请注意拓扑中的中央林使用自身内部的对象表示其他林中的用户，并承载此林中任意用户的用户帐户。
  
其工作方式如何？ 目录同步产品（例如 Forefront Identity Manager，即 FIM）管理组织用户帐户的整个生命周期。 在林中创建或删除帐户时，更改将同步到中央林中的对应联系人。
  
显而易见，将 AD 基础结构就地迁移到这种拓扑可能并不容易，但如果你已经采用了这种拓扑，或者仍在规划林基础结构，那么这这种拓扑可能就是理想的选择。 你可以将 Skype for Business Server 2019 部署集中到一个林中，用户可以搜索任何林中的其他用户，并且与之沟通并查看其状态。 所有用户联系人更新都会通过同步软件自动得到处理。
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology"></a>Skype for Business 资源林拓扑中的多个林
<a name="BKMK_multipleforestopology"> </a>

![资源林拓扑图表中的多林](../../SfbServer/media/41efa3b6-d9e6-47df-992b-fefcfc39a80d.png)
  
同样支持资源林拓扑，在这种拓扑中，一个林专门用于运行服务器应用程序，例如 Microsoft Exchange Server 和 Skype for Business Server 2019。 此资源林还承载着活动用户对象的同步表示形式，但不包含启用了登录的用户帐户。 因此资源林用作用户对象所驻留的其他林的共享服务环境，这些林与资源林之间存在林级信任关系。
  
请注意，ExchangeServer 可以部署在与 Skype for Business Server 相同的资源林中，也可以部署在不同的林中。
  
要在这种类型的拓扑中部署 Skype for Business Server 2019，需要在资源林中为用户林中的每个用户帐户创建一个禁用用户对象（如果环境中已有 Microsoft Exchange Server，则它可能已经为你完成了此任务）。 随后需要一种目录同步工具（例如 Forefront Identity Manager，即 FIM）来管理用户帐户的生命周期。
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology-with-exchange-online"></a>具有 Exchange Online 的 Skype for Business 资源林拓扑中的多个林
<a name="BKMK_multipleforestopology"> </a>

此拓扑与 [Skype for Business 资源林拓扑中的多个林](system-requirements.md#BKMK_multipleforestopology)中所述的拓扑类似。
  
在该拓扑中，存在一个或多个用户林，且 Skype for Business Server 部署在专用资源林中。 Exchange Server 可以部署在本地的相同资源林中，也可以部署在不同资源林中，且可配置为与 Exchange Online 混合使用，或者可以由 Exchange Online 专门为本地帐户提供电子邮件服务。 目前没有该拓扑的示意图。
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-skype-for-business-online-and-azure-active-directory-connect"></a>具有 Skype for Business Online 和 Azure Active Directory Connect 的资源林拓扑中的多个林
<a name="BKMK_multipleforestopology"> </a>

![显示两个 AD 林，一个用户林和一个资源林。这两个林具有信任关系。它们使用 Azure AD Connect 与 Office 365 同步。通过 Office 365 为所有用户启用 Skype for Business。](../../SfbServer/media/6d54558d-8786-4ebf-90f6-55ae3fdb5ae7.jpg)
  
在此方案中，一个资源林拓扑中有多个本地林。Active Directory 林之间为完全信任关系。Azure Active Directory Connect 工具用于在本地用户林和 Office 365 之间同步帐户。
  
 组织还有 Office 365，并使用 [Azure Active Directory Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) 将其本地帐户与 Office 365 同步。 启用了 Skype for Business 的用户通过 Office 365 和 Skype for Business Online 启用。 Skype for Business Server 不部署在本地。
  
单一登录身份验证由位于用户林中的 Active Directory 联合身份验证服务场提供。
  
在此方案中，支持部署本地 Exchange、Exchange Online 或 Exchange 混合解决方案，或者根本不部署 Exchange。 （图中只显示了本地 Exchange，但是也完全支持其他 Exchange 解决方案。）
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-hybrid-skype-for-business"></a>有混合 Skype for Business 的资源林拓扑中的多个林
<a name="BKMK_multipleforestopology"> </a>

在该方案中，存在一个或多个本地用户林，Skype for Business 部署在专用资源林中并配置为用于与 Skype for Business Online 的混合模式。 Exchange Server 可以部署在本地的相同资源林中，也可以部署在不同资源林中，且可配置为与 Exchange Online 混合使用。 或者可以由 Exchange Online 专门为本地帐户提供电子邮件服务。
  
有关详细信息，请参阅[配置适用于混合 Skype for Business 的多林环境](../../SfbServer/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/configure-a-multi-forest-environment-for-hybrid.md)。
  
## <a name="domain-name-system-dns"></a>域名系统 (DNS)
<a name="DNS"> </a>

Skype for Business Server 2019 需要 DNS，原因如下：
  
- DNS 支持 Skype for Business Server 2019 发现内部服务器或池，以实现服务器至服务器的通信。
    
- DNS 使客户端机器可以发现用于 SIP 事务的前端池或标准版服务器。
    
- 它会将会议的简单 URL 与托管这些会议的服务器相关联。
    
- DNS 允许外部用户和客户端机器连接至用于即时消息 (IM) 或会议的边缘服务器或 HTTP 反向代理。
    
- 它使未登录的统一通信 (UC) 设备可以发现运行设备更新 Web 服务的前端池或标准版服务器，以获取更新和发送日志。
    
- 使用 DNS 使移动客户端可以自动发现 Web 服务资源，而无需用户在设备设置中手动输入 URL。
    
- DNS 还用于 DNS 负载平衡。
    
请注意，Skype for Business Server 2019 不支持国际化域名 (IDN)。
  
一定要切记，DNS 中的任何名称都必须与 Skype for Business Server 2019 所用服务器上配置的计算机名称相同。 具体来说，不能在这种环境中使用短名称，必须为拓扑生成器使用 FQDN。
  
尽管使用 FQDN 似乎是已加入域的计算机的合理做法，但如果有尚未加入域的边缘服务器，那么它就可能使用默认的短名称，无域后缀。 务必确保在 DNS、边缘服务器、任何 Skype for Business Server 2019 服务器池及相关池上均无此类问题发生。
  
切勿使用 Unicode 字符或下划线。 外部 DNS 和公共证书颁发机构支持标准字符（包括 A-Z、a-z、0-9 和连字符），切记在证书中需要为 SN 分配 FQDN，只要在开始命名时牢记这一点，你就可以免去许多后顾之忧。
  
若要进一步了解网络 DNS 要求，请查看我们的规划文档的[Networking](../../SfbServer/plan-your-deployment/network-requirements/network-requirements.md)部分。
  
## <a name="certificates"></a>证书
<a name="Certs"> </a>

在部署之前，你要做的一件最重要的事情就是确保证书有条不紊。 Skype for Business Server 2019 需要公钥基础结构 (PKI) 来支持传输层安全性 (TLS) 连接和相互传输层安全性 (MTLS) 连接。 基本上，为了以标准化的方式进行通信，Skype for Business Server 会使用证书颁发机构 (CA) 颁发的证书。
  
Skype for Business Server 2019 使用证书的部分用途包括：
  
- 客户端与服务器之间的 TLS 连接
    
- 服务器之间的 MTLS 连接
    
- 使用自动发现伙伴 DNS 的联盟
    
- 远程用户访问即时消息 (IM)
    
- 外部用户访问音频/视频 (AV) 会话、应用程序共享和会议
    
- 与 Web 应用程序和 Outlook Web Access (OWA) 通信
    
因此，必须进行证书规划。 现在，我们来看看在请求证书时需要牢记的一些事情：
  
- 所有服务器证书都必须支持服务器授权（服务器 EKU）。
    
- 所有服务器证书都必须包含一个 CRL 分发点 (CDP)。
    
- 所有证书必须使用操作系统支持的签名算法进行签名。 Skype for Business Server 2019 支持摘要大小（224、256、384 和 512 位）的 SHA-1 和 SHA-2 套件，可满足或超过操作系统的要求。
    
- 运行 Skype for Business Server 2019 的内部服务器支持自动注册。
    
- Skype for Business Server 2019 边缘服务器不支持自动注册。
    
> [!NOTE]
> 不支持使用 RSASSA-PSS 签名算法，否则可能导致登录错误、呼叫转接问题及其他问题。 
  
- 加密密钥长度为 1024、2048 和 4096。建议使用密钥长度 2048 和更大值。
    
- 默认的摘要式或哈希签名算法是 RSA。还支持 ECDH_P256、ECDH_P384 和 ECDH_P521 算法。
    
你需要综合考虑上述问题，在向 CA 请求证书时还有多种不同的舒适级别。 我们将在下方给出进一步的指南，帮助你尽可能轻松地进行规划。
  
### <a name="certificates-for-your-internal-servers"></a>内部服务器的证书

大多数内部服务器都需要证书，极有可能你会通过内部 CA（位于域内的 CA）获取这些证书。 如果愿意，你可以从外部 CA（位于 Internet 上）请求这些证书。 如果你不确定要向哪个公共 CA 请求证书，可以查阅[统一通信证书合作伙伴](/SkypeForBusiness/certification/services-ssl)列表。
  
在 Skype for Business Server 2019 与其他应用程序和服务器（例如 Microsoft Exchange Server）通信时，你也需要证书。 显然，这必须是其他这些应用程序与服务器能够以受支持的方式使用的证书。 Skype for Business Server 2019 和其他 Microsoft 产品支持使用开放式授权 (OAuth) 协议进行服务器到服务器的身份验证和授权。 如果你对此主题感兴趣，我们发表了另一篇有关 OAuth 和 Skype for Business Server 2019 的规划文章。
  
Skype for Business Server 2019 还支持（但并非必要）使用 SHA-256 加密哈希函数签署的证书。 要支持使用 SHA-256 进行外部访问，外部证书需要由公共 CA 使用 SHA-256 颁发。
  
为简化起见，我们将标准版服务器、前端服务器和其他角色的证书要求整理为下表，并以虚构的 contoso.com 为例（你的环境中可能使用其他设置）。 这些均为标准 Web 服务器证书，使用不可导出的私钥。 此外还应注意：
  
- 使用证书向导请求证书时会自动配置服务器增强型密钥使用 (EKU)。
    
- 每个证书友好名称在计算机存储中均必须是唯一的。
    
- 根据下方的示例名称，如果你已在 DNS 中配置 sipinternal.contoso.com 或 sipexternal.contoso.com，则需要将其加入证书的“使用者替代名称 (SAN)”中。
    
标准版服务器的证书：
  
|**证书**|**使用者名称/公用名称**|**使用者替代名称**|**示例**|**批注**|
|:-----|:-----|:-----|:-----|:-----|
|默认值  <br/> |池的 FQDN  <br/> |池的 FQDN 和服务器的 FQDN  <br/> 如果具有多个 SIP 域并已启用自动客户端配置，则证书向导会检测并添加所有受支持的 SIP 域 FQDN。  <br/> 如果此池是客户端的自动登录服务器，而且组策略要求执行严格的域名系统 (DNS) 匹配，那么还需要 sip.sipdomain 条目（对应于您拥有的每个 SIP 域）。  <br/> |SN=se01.contoso.com; SAN=se01.contoso.com  <br/> 如果此池是客户端的自动登录服务器，而且组策略要求执行严格的 DNS 匹配，则还需要 SAN=sip.contoso.com; SAN=sip.fabrikam.com。  <br/> |对于标准版服务器，服务器 FQDN 与池 FQDN 相同。  <br/> 证书向导会检测您在安装过程中所指定的任何 SIP 域，然后自动将它们添加到使用者可选名称中。  <br/> 也可将此证书用于服务器到服务器身份验证。  <br/> |
|Web 内部  <br/> |服务器的 FQDN  <br/> |以下各项：  <br/> • 内部 Web FQDN（与服务器的 FQDN 相同）  <br/> 和  <br/> • 会议简单 URL  <br/> • 拨入简单 URL  <br/> • 管理简单 URL  <br/> 或  <br/> • 简单 URL 的通配符条目  <br/> |SN=se01.contoso.com; SAN=se01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> 使用通配符证书：  <br/> SN=se01.contoso.com; SAN=se01.contoso.com; SAN=\*.contoso.com  <br/> |你无法在拓扑生成器中覆盖内部 Web FQDN。  <br/> 如果你有多个会议简单 URL，则必须将其全部包含为 SAN。  <br/> 简单 URL 条目支持通配符条目。  <br/> |
|Web 外部  <br/> |服务器的 FQDN  <br/> |以下各项：  <br/> • 外部 Web FQDN  <br/> 和  <br/> • 拨入简单 URL  <br/> • 每个 SIP 域的会议简单 URL  <br/> 或  <br/> • 简单 URL 的通配符条目  <br/> |SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> 使用通配符证书：  <br/> SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=\*.contoso.com  <br/> |如果您有多个会议简单 URL，则必须将它们作为使用者可选名称全部添加。  <br/> 简单 URL 条目支持通配符条目。  <br/> |
   
前端池中前端服务器的证书：
  
|**证书**|**使用者名称/公用名称**|**使用者替代名称**|**示例**|**批注**|
|:-----|:-----|:-----|:-----|:-----|
|默认  <br/> |池的 FQDN  <br/> |池的 FQDN 和服务器的 FQDN  <br/> 如果具有多个 SIP 域并已启用自动客户端配置，则证书向导会检测并添加所有受支持的 SIP 域 FQDN。  <br/> 如果此池是客户端的自动登录服务器，而且组策略要求执行严格的域名系统 (DNS) 匹配，那么还需要 sip.sipdomain 条目（对应于您拥有的每个 SIP 域）。  <br/> |SN=eepool.contoso.com; SAN=eepool.contoso.com; SAN=ee01.contoso.com  <br/> 如果此池是客户端的自动登录服务器，而且组策略要求执行严格的 DNS 匹配，则还需要 SAN=sip.contoso.com; SAN=sip.fabrikam.com。  <br/> |证书向导会检测您在安装过程中所指定的任何 SIP 域，然后自动将它们添加到使用者可选名称中。  <br/> 也可将此证书用于服务器到服务器身份验证。  <br/> |
|Web 内部  <br/> |池的 FQDN  <br/> |以下各项：  <br/> • 内部 Web FQDN（与服务器的 FQDN 不同）  <br/> • 服务器 FQDN  <br/> • Skype for Business 池 FQDN  <br/> 和  <br/> • 会议简单 URL  <br/> • 拨入简单 URL  <br/> • 管理简单 URL  <br/> 或  <br/> • 简单 URL 的通配符条目  <br/> |SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> 使用通配符证书：  <br/> SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=\*.contoso.com  <br/> |如果您有多个会议简单 URL，则必须将它们作为使用者可选名称全部添加。  <br/> 简单 URL 条目支持通配符条目。  <br/> |
|Web 外部  <br/> |池的 FQDN  <br/> |以下各项：  <br/> • 外部 Web FQDN  <br/> 和  <br/> • 拨入简单 URL  <br/> • 管理简单 URL  <br/> 或  <br/> • 简单 URL 的通配符条目  <br/> |SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> 使用通配符证书：  <br/> SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=\*.contoso.com  <br/> |如果您有多个会议简单 URL，则必须将它们作为使用者可选名称全部添加。  <br/> 简单 URL 条目支持通配符条目。  <br/> |
   
控制器的证书：
  
|**证书**|**使用者名称/公用名称**|**使用者替代名称**|**示例**|
|:-----|:-----|:-----|:-----|
|默认值  <br/> |控制器池  <br/> |控制器的 FQDN 和控制器池的 FQDN。  <br/> 如果此池是客户端的自动登录服务器，且组策略要求执行严格的 DNS 匹配，那么还需要 sip.sipdomain 条目（对应于你拥有的每个 SIP 域）。  <br/> |pool.contoso.com; SAN=dir01.contoso.com  <br/> 如果此控制器池是客户端的自动登录服务器，而且组策略要求执行严格的 DNS 匹配，那么还需要 SAN=sip.contoso.com; SAN=sip.fabrikam.com。  <br/> |
|Web 内部  <br/> |服务器的 FQDN  <br/> |以下各项：  <br/> • 内部 Web FQDN（与服务器的 FQDN 相同）  <br/> • 服务器 FQDN  <br/> • Skype for Business 池 FQDN  <br/> 和  <br/> • 会议简单 URL  <br/> • 拨入简单 URL  <br/> • 管理简单 URL  <br/> 或  <br/> • 简单 URL 的通配符条目  <br/> |SN=dir01.contoso.com; SAN=dir01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> 使用通配符证书：  <br/> SN=dir01.contoso.com; SAN=dir01.contoso.com SAN=\*.contoso.com  <br/> |
|Web 外部  <br/> |服务器的 FQDN  <br/> |以下各项：  <br/> • 外部 Web FQDN  <br/> 和  <br/> • 每个 SIP 域的会议简单 URL  <br/> • 拨入简单 URL  <br/> 或  <br/> • 简单 URL 的通配符条目  <br/> |控制器外部 Web FQDN 必须不同于前端池或前端服务器。  <br/> SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> 使用通配符证书：  <br/> SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=\*.contoso.com  <br/> |
   
独立中介服务器的证书：
  
|**证书**|**使用者名称/公用名称**|**使用者替代名称**|**示例**|
|:-----|:-----|:-----|:-----|
|默认值  <br/> |池的 FQDN  <br/> |池的 FQDN  <br/> 池成员服务器的 FQDN  <br/> |SN=medsvr-pool.contoso.net; SAN=medsvr-pool.contoso.net; SAN=medsvr01.contoso.net  <br/> |
   
Survivable Branch Appliance（具体是适用于 Skype for Business Server 2019 的 Survivable Branch Appliance 2015）的证书：
  
|**证书**|**使用者名称/公用名称**|**使用者替代名称**|**示例**|
|:-----|:-----|:-----|:-----|
|默认值  <br/> |设备的 FQDN  <br/> |SIP.\<sipdomain\>（每个 SIP 域仅需要一个条目）  <br/> |SN=sba01.contoso.net; SAN=sip.contoso.com; SAN=sip.fabrikam.com  <br/> |
   
### <a name="certificates-for-external-user-access-edge"></a>外部用户访问（边缘）的证书

Skype for Business Server 2019 支持为访问和 Web 会议边缘外部接口外加 A/V 身份验证服务使用**单个公共证书**，这一切均通过边缘服务器提供。 边缘内部接口通常使用内部 CA 颁发的专用证书，但如果愿意，也可以使用受信任的 CA 颁发的公共证书。
  
反向代理 (RP) 也会使用公共证书，并会使用 HTTP（更精确地说，是 HTTP 上的 TLS）对 RP 与客户端以及 RP 与内部服务器之间的通信进行加密。
  
### <a name="certificates-for-mobility"></a>移动证书

如果你在部署移动功能并需要支持移动客户端的自动发现，则需要在证书上包含某些使用者替代名称条目，以支持来自移动客户端的安全连接。
  
你需要在以下证书上包含 SAN 名称以支持自动发现：
  
- 控制器池
    
- 前端池
    
- 反向代理
    
下表列出了详细信息。
  
此时最好做一些预先规划工作，但有时你已经部署了 Skype for Business Server 2019，最初并未打算部署移动技术，但在环境中已有证书之后，又出现了部署移动技术的需要。 通过内部 CA 重新颁发证书通常比较简单，但如果使用的是公共 CA 颁发的公共证书，则可能代价高昂。
  
如果你在寻找这方面的信息，而且有大量的 SIP 域（导致添加 SAN 的成本更为高昂），你可以将反向代理配置为使用 HTTP 处理初始自动发现服务请求，而非使用 HTTPS（默认配置）。 文章[规划移动性](../../SfbServer/plan-your-deployment/mobility.md)提供了更多详细信息。
  
控制器池和前端池证书要求：
  
|**说明**|**SAN 条目**|
|:-----|:-----|
|内部自动发现服务 URL  <br/> |SAN=lyncdiscoverinternal.\<sipdomain\>  <br/> |
|外部自动发现服务 URL  <br/> |SAN=lyncdiscover.\<sipdomain\>  <br/> |
   
或者，你也可以使用 SAN=\*.\<sipdomain\>
  
反向代理（公共 CA）证书要求：
  
|**说明**|**SAN 条目**|
|:-----|:-----|
|外部自动发现服务 URL  <br/> |SAN=lyncdiscover.\<sipdomain\>  <br/> |
   
此 SAN 需要分配给已分配到反向代理上的 SSL 侦听器的证书。
  
> [!NOTE]
> 反向代理侦听器将包含外部 Web 服务 URL 的 SAN。 如果你已部署控制器（可选），部分示例包括 SAN=skypewebextpool01.contoso.com 和 dirwebexternal.contoso.com。 
  
## <a name="file-share"></a>文件共享
<a name="Fileshare"> </a>

Skype for Business Server 2019 可以对所有文件存储使用相同的文件共享。 但您需要注意以下事项：
  
- 文件共享需要置于直接附加存储 (DAS) 或存储区域网络 (SAN) 上，其中包括分布式文件系统 (DFS) 以及文件存储的独立磁盘冗余阵列 (RAID)。 有关 Windows Server 2012 的 DFS 的更多信息，请查看[此 DFS 页面](https://technet.microsoft.com/library/jj127250.aspx)。
    
- 建议为文件共享使用共享群集。 如果你已有共享群集，应该将 Windows Server 2012 或更高版本加入群集

> [!Note]
> **为什么要使用最新的 Windows？** 较旧的版本可能不具备启用所有功能的正确权限。 你可以使用群集管理器创建文件共享。 有关更多详细信息，请参阅此支持文章[如何在群集上创建文件共享](https://support.microsoft.com/help/224967)。
    
> [!CAUTION]
> 你应知道，不支持将网络附加存储 (NAS) 用作文件共享，因此，请使用上述其中一个选项。 此支持限制是由 NAS 设备的可变设计所致，这些设备必须向访问设备共享文件系统的基于 Windows Server 的计算机提供文件系统适应性。
  








