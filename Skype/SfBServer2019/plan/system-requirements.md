---
title: 2019 年 Skype for Business Server 的系统要求
ms.reviewer: ''
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: ''
description: 摘要：使用本主题Skype for Business Server 2019 服务器和域基础结构。 此处提供的硬件、操作系统、数据库、软件、所有系统要求和建议以及证书 DNS、文件共享和 Active Directory 信息可帮助确保成功安装和部署服务器场。
ms.openlocfilehash: cb1d7464406ae089fd31c31971cb246d79a83edb
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/30/2021
ms.locfileid: "60011746"
---
# <a name="system-requirements-for-skype-for-business-server-2019"></a>2019 年 Skype for Business Server 的系统要求
 
**摘要：** 使用本主题准备Skype for Business Server 2019。 此处介绍了硬件、操作系统、软件、数据库、证书、ActiveTory、DNS 和文件共享。 此处的所有系统要求和建议都有助于确保成功安装和部署服务器场。
  
正如您预期，在开始部署 2019 年 10 月之前，Skype for Business Server准备工作。 本文将介绍规划以下内容：
  
- [硬件](system-requirements.md#Hardware)
  
- [操作系统](system-requirements.md#OS)
  
- [软件](system-requirements.md#Software)

- [后端SQL数据库](system-requirements.md#DBs)
  
- [Active Directory](system-requirements.md#AD)
  
- [域名系统 (DNS)](system-requirements.md#DNS)
  
- [证书](system-requirements.md#Certs)
  
- [文件共享](system-requirements.md#Fileshare)

  
## <a name="hardware-for-skype-for-business-server-2019"></a>Skype for Business Server 2019 的硬件
<a name="Hardware"> </a>

在拓扑关闭后 (如果未关闭，请查看[Topology Basics for Skype for Business Server 2019主题) ，](../../SfbServer/plan-your-deployment/topology-basics/topology-basics.md)是时候考虑服务器了。 Skype for Business Server 2019 服务器需要 64 位硬件。 我们针对硬件的建议如下。 这些并非要求，但反映了实现最佳性能所需的要求。 我们具有容量规划文档，可帮助您确定是否需要超过此要求，具体取决于您的环境。
  
建议用于服务器Standard Edition硬件：

|硬件组件|建议|
|:-----|:-----|
|CPU   |Intel Xeon E5-2673 v3 双处理器，6 核，2.4 GHz (GHz) 或更高。  <br/> Intel Itanium 处理器不受 Skype for Business Server 2019 角色的支持。   |
|内存   |32 GB (GB) 。   |
|磁盘   |任一：  <br/> • 具有至少 72 GB 可用磁盘空间的 8 个或 80000 RPM 硬盘驱动器 (两个磁盘使用 RAID 1，6 个磁盘使用 RAID 10) 。  <br/> 或  <br/> • 固态硬盘 (SSD) 提供与 8 个 10000 RPM 机械磁盘驱动器相同的可用空间和类似性能。   |
|网络   |1 个双端口网络适配器，可以使用 1 Gbps 或更高 (2 个网络适配器，但它们需要与一个 MAC 地址和一个 IP 地址) 。  <br/> 前端服务器、后端服务器和服务器不支持双Standard Edition配置。 <br/> 只要它们未向操作系统公开，并且用于监视和管理服务器硬件，就可以拥有带外管理系统，如 DRAC 或则使用。 此方案不构成多主服务器，并且受支持。   |


前端服务器和后端服务器的推荐硬件：
  
|硬件组件|建议|
|:-----|:-----|
|CPU   |Intel Xeon E5-2673 v3 双处理器，6 核，2.4 GHz (GHz) 或更高。 <br/> Intel Itanium 处理器不受 Skype for Business Server 2019 角色的支持。   |
|内存   |64 GB (GB) 。   |
|磁盘   |任一：  <br/> • 具有至少 72 GB 可用磁盘空间的 8 个或 80000 RPM 硬盘驱动器 (两个磁盘使用 RAID 1，6 个磁盘使用 RAID 10) 。  <br/> 或  <br/> • 固态硬盘 (SSD) 提供与 8 个 10000 RPM 机械磁盘驱动器相同的可用空间和类似性能。   |
|网络   |1 个双端口网络适配器，可以使用 1 Gbps 或更高 (2 个网络适配器，但它们需要与一个 MAC 地址和一个 IP 地址) 。  <br/> 前端服务器、后端服务器和服务器不支持双Standard Edition配置。 <br/> 只要它们未向操作系统公开，并且用于监视和管理服务器硬件，就可以拥有带外管理系统，如 DRAC 或则使用。 此方案不构成多主服务器，并且受支持。   |
   
边缘服务器、独立中介服务器和控制器的建议硬件：
  
|硬件组件|建议|
|:-----|:-----|
|CPU   |Intel Xeon E5-2673 v3 双处理器，6 核，2.4 GHz (GHz) 或更高。  <br/> Intel Itanium 处理器不受 Skype for Business Server 2019 角色的支持。   |
|内存   |32 GB。   |
|磁盘   |任一：  <br/> • 具有至少 72 GB 可用磁盘空间的 4 个或多个 10000 RPM 硬盘驱动器 (磁盘应处于 2x RAID 1 配置) 。  <br/> 或  <br/> • 固态硬盘 (SSD) 提供与 4 个 10000 RPM 机械磁盘驱动器相同的可用空间和类似性能。   |
|网络   |1 个双端口网络适配器，可以使用 1 Gbps 或更高 (2 个网络适配器，但它们需要与一个 MAC 地址和一个 IP 地址) 。  <br/> 视频互操作服务器 **和控制器不支持** 双主或多主配置。 <br/> 边缘服务器将需要两个网络接口，即两个双端口网络适配器（1 Gbps 或更高 (）或两个成对网络适配器，总共 4 个，每个对与一个 MAC 地址和一个 IP 地址组合在一起，总共两对) 。  <br/> 在独立中介服务器上，支持安装其他网络接口 (NIC) 允许配置特定的 PSTN IP 地址。   |


> [!NOTE]
> 无论服务器角色如何，我们还建议为 Skype for Business Server 2019 (这可能因你购买的硬件品牌而异，因此请参考制造商文档，以) ：
> - BIOS 配置 - 应从 NUMA 设置为 FLAT。
> - 启用超线程。
> - RSS 队列设置应设置为 8 个队列。

   
## <a name="operating-systems-for-skype-for-business-server-2019"></a>Skype for Business Server 2019 的操作系统
<a name="OS"> </a>

硬件就位后，你需要安装操作系统 (OS) ，这将允许你安装并成功使用 Skype for Business Server 2019。
  
- Windows Server 2019 
- Windows Server 2016
   
除了此处列出的操作系统外，其他操作系统都无法正常工作;请勿尝试安装 Skype for Business Server 2019。 例如，服务器核心选项未列出，因此不受支持。

> [!NOTE]
> Lync Server 2013 不支持操作系统的就地升级。 您必须部署单独的池，并使用不同的操作系统将用户迁移到新池。 池中的所有服务器必须具有相同的操作系统版本。

> [!NOTE]
> 
> 如果要在 Windows Server 2019 计算机上安装 Windows Admin Center 2019，它将提示你输入侦听端口。 你可能会选择端口 443，但如果计算机上安装了 Skype for Business Server 2019，或者要安装 Skype for Business Server 2019，则必须选择其他端口号。
> 
>为什么如此？ 如果 Windows 管理中心 2019 在端口 443 上运行，将无法使用 Skype for Business 控制面板连接到服务器，也无法连接到服务器 (通讯簿 Web 服务、自动发现服务、WebTicket 服务等) 上运行的任何内部 Web 服务。  事实上，将无法连接到任何内部 Web 服务 URL。 如果你需要或想要将 Windows 2019 放在具有 Skype for Business Server 2019 的服务器上，请选择其他端口。
> 

  
## <a name="software-that-should-be-installed-before-a-skype-for-business-server-2019-deployment"></a>应在部署 2019 年 Skype for Business Server之前安装的软件
<a name="Software"> </a>

您需要为运行 2019 年 2019 年的任何服务器安装或配置Skype for Business Server一些操作。 下面列出了这些要求，后跟特定服务器角色的其他要求。

> [!IMPORTANT]
> SkypeFor Business 2019 支持 .Net Framework 4.8。 
  
 **所有服务器：**
  
|软件/角色|详细信息|
|:-----|:-----|
|Windows PowerShell 3.0   |所有Skype for Business Server服务器Windows PowerShell 3.0 版。  <br/> • 默认情况下，此组件应随 Windows Server 2016。 |
|Microsoft .NET Framework   |WCF **服务是作为** 服务器管理器下的一项Windows功能安装的功能，最初不需要下载。 <br/> • 在安装此功能时，或者如果该功能已安装并且正在检查它，您需要确保还选中并安装了 **HTTP** 激活选项，如下所示： <br/>![Screenshot showing HTTP Activation option under the .NET Framework 4.5 Features.](../../SfbServer/media/a4064fa0-fa49-4474-bd98-b9a79ff68f8b.png) <br/> 如果收到其他弹出消息，指出需要安装其他一些内容才能安装 HTTP 激活，请不要担心。 这很正常;单击"确定"，然后继续。 如果未显示此弹出窗口，可以假定已安装了上述内容，然后继续操作。  <br/> Microsoft .NET Framework通常在安装 microsoft Windows Server 2016时安装。 Skype for Business Server需要 Microsoft .NET Framework 4.7 或 4.8，因此你可能需要更新它。 你可以在此处找到 [更新](https://support.microsoft.com/help/3186497/the-net-framework-4-7-offline-installer-for-windows/) |
|Media Foundation   |For Windows Server 2016， the Windows Media Format Runtime installs with Microsoft Media Foundation.  <br/> 用于会议的所有前端服务器和 Standard Edition 服务器都需要 Windows Media Format Runtime 来运行呼叫库、通知和响应组应用程序播放通知和音乐的 Windows Media Audio (.wma) 文件。   |
|Windows Identity Foundation   |我们需要使用 Windows Identity Foundation 3.5 来支持 2019 年 3 月Skype for Business Server身份验证方案。  <br/> • Windows Server 2016，无需下载任何内容。 打开 **服务器管理器**，然后转到添加 **角色和功能向导**。 **Windows Identity Foundation 3.5"** 列于"功能 **"** 部分下。 如果已选中，则没有问题。 否则，请选择它并单击 **"下一步** "以到达 **"安装"** 按钮。  |
|远程服务器管理工具   |角色管理工具：AD DS 和 AD LDS 工具   |
   
 **前端服务器和Standard Edition服务器还需要：**
  
|软件/角色|详细信息|
|:-----|:-----|
|Internet 信息服务 (IIS)   |选择以下模块后，所有前端服务器以及所有 Standard Edition都需要 IIS：  <br/> • 常见的 HTTP 功能：默认文档、HTTP 错误、静态内容  <br/> • 运行状况和诊断：HTTP 日志记录、日志记录工具、跟踪  <br/> • 性能：静态内容压缩、动态内容压缩  <br/> • 安全性：请求筛选、客户端证书映射身份验证Windows身份验证  <br/> • 应用程序开发：.NET Extensibility 3.5、.NET Extensibility 4.5、ASP.NET 3.5、ASP.NET 4.5、ISAPI 扩展、ISAPI 筛选器  <br/> • 管理工具：IIS 管理控制台、IIS 管理脚本和工具  <br/> 请注意，还需要匿名访问，但您可以在安装 IIS 时获得此权限，因此在列表中没有选择它的位置。   |
|Windows Media Format Runtime   | 对于Windows Server 2016，你需要在服务器管理器 **中安装媒体****基础功能**。 实际上，无需这样做即可启动 Skype for Business Server 2019 安装，但系统会提示您安装它，然后在继续安装 Skype for Business Server 2019 之前重新启动服务器。 最好提前完成。  |
|Silverlight   |你可以在此处安装最新版本的[Silverlight。](https://www.microsoft.com/silverlight/)   |
   
为了帮助你完成此操作，可以运行下面的 PowerShell 脚本示例来自动执行此操作：
  
```PowerShell
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Windows-Identity-Foundation, Server-Media-Foundation, Telnet-Client, BITS, ManagementOData, Web-Mgmt-Console, Web-Metabase, Web-Lgcy-Mgmt-Console, Web-Lgcy-Scripting, Web-WMI, Web-Scripting-Tools, Web-Mgmt-Service
```

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
    
- 安全
    
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
    
 (如果想知道，此模块集与前端服务器和 Standard Edition 服务器相同，而"动态内容压缩和管理工具"则) 
  
我们在下面也具有一些 PowerShell 代码：
  
```PowerShell
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, Telnet-Client
```

## <a name="back-end-databases-that-will-work-with-skype-for-business-server-2019"></a>与 2019 Skype for Business Server数据库
<a name="DBs"> </a>

在 2019 Skype for Business Server 2019 Standard Edition时，你将拥有 SQL Server 2016 Express (64 位) 。

Skype for Business Server 2019 Enterprise Edition需要完整SQL Server，如下 (64 位版本所示;请勿使用 32 位版本) ：
  
- Microsoft SQL Server 2019 (64 位) 版本，并且必须使用最新更新运行。
- Microsoft SQL Server 2017 (64 位) 版本，并且必须使用最新更新运行。
- Microsoft SQL Server 2016 (64 位) 版本，并且必须使用最新更新运行。

如果你在此处未SQL Server想要使用的版本，则你无法使用它。
  
> [!NOTE]
> 还需要为监控服务器SQL Server Reporting Services安装客户端。 
  
### <a name="sql-clustering-and-sql-always-on"></a>SQL群集和SQL始终打开

SQL支持使用 Skype for Business Server 2019 进行群集。 如果你想要设置群集SQL，则使用 SQL Server。
  
请确保你拥有适用于群集的主动/SQL配置，这受支持。 不要与任何其他实例共享被动SQL节点。
  
你可以将以下内容用于故障转移群集：
  
双节点：
  
- Microsoft SQL Server 2019 Standard (64 位) ，建议运行最新 Service Pack。
- Microsoft SQL Server 2017 Standard (64 位) ，建议运行最新 Service Pack。
- Microsoft SQL Server 2016 Standard (64 位) ，建议运行最新 Service Pack。

16 节点：
  
- Microsoft SQL Server 2019 Enterprise (64 位) ，建议运行最新的 Service Pack。
- Microsoft SQL Server 2017 Enterprise (64 位) ，建议运行最新 Service Pack。
- Microsoft SQL Server 2016 Enterprise (64 位) ，建议运行最新 Service Pack。

SQL支持 Always On，您可以在 Skype for Business Server [2019](../../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md)的后端服务器高可用性中阅读有关它的信息。
  

###  <a name="additional-server-installation-recommendations"></a>其他服务器安装建议：
  
请不要在任何前端服务器或独立中介服务器上安装任何 Microsoft Internet Security and Acceleration (ISA) Server 客户端软件，或其他任何 Winsock 分层服务提供商 (LSP) 软件 (任何第三方防火墙或防病毒网络检查软件将包含在此处) 中。 安装该软件时，可以看到较差的媒体流量性能。
  

## <a name="active-directory"></a>Active Directory
<a name="AD"> </a>

尽管服务器和服务中的大部分配置数据存储在 Skype for Business Server 2019 中央管理存储中，但 Active Directory 中仍存储有一些内容：
  
|Active Directory 对象|对象类型|
|:-----|:-----|
|架构扩展   |用户对象扩展   |
||用于 Skype for Business Server 2015 和 Lync Server 2013 的扩展，以维护与以前受支持的版本的向后兼容性   |
|数据   |用户 SIP URI 和其他用户设置   |
||应用程序（如响应 (和响应组应用程序）的联系人会议助理应用程序)    |
||为实现向后兼容而发布的数据   |
||中央管理存储 (SCP) 服务控制点   |
||Kerberos 身份验证帐户（可选计算机对象）   |
   
### <a name="os-for-domain-controllers"></a>域控制器的操作系统

可以使用以下域控制器操作系统：
  
- Windows Server 2019

- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
部署 Skype for Business Server 2019 的任何域的域功能级别以及部署 Skype for Business Server 2019 的任何林的林功能级别必须为以下项之一：
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
这些环境中能否具有只读域控制器？ 当然可以，只要还有可写入的域控制器。
  
必须了解的是，Skype for Business Server 2019 不支持单标签域。 它们是什么？ 如果你有标记为 contoso.local 的根域，则没有问题。 如果你的根域只是名为 local，则不起作用，因此它不受支持。 有关此内容，本知识库文章 [进行了进一些介绍](https://support.microsoft.com/kb/300684/)。
  
Skype for Business Server 2019 也不支持重命名域。 如果确实需要重命名域，则需要卸载 Skype for Business Server 2019、重命名域，然后重新安装 Skype for Business Server 2019。
  
最后，你可能正在处理具有锁定的 AD DS 环境的域，这很正常。 在部署文档中，我们了解有关如何将 Skype for Business Server 2019 部署到锁定的 AD DS 环境中的信息。
  
### <a name="ad-topologies"></a>AD 拓扑

2019 年 Skype for Business Server支持的拓扑包括：
  
- 具有单个域的单林
    
- 具有单个树和多个域的单林
    
- 具有多个树和互不连接的命名空间的单林
    
- 中央林拓扑中的多林
    
- 资源林拓扑中的多林
    
- 资源林拓扑中的多个Skype for Business具有多个Exchange Online
    
- 资源林拓扑中的多个林，Skype for Business Online 和 Azure Active Directory 连接
    
我们提供了图表和说明，可帮助您确定您的环境中具有的拓扑，或在安装 Skype for Business Server 2019 之前可能需要设置哪些拓扑。 为简单一点，我们还包括一个密钥：
  
![是用于拓扑图的图标Skype for Business键。](../../SfbServer/media/cc0dbc17-cf81-4b79-bf99-4614cc6828a0.png)
  
#### <a name="single-forest-with-single-domain"></a>具有单个域的单林

![包含单个域的 Active Directory 单林关系图。](../../SfbServer/media/24921a0b-3a3e-4bad-8427-49300e2e3f7a.png)
  
它并不简单;它是一个域林，一种常见拓扑。
  
#### <a name="single-forest-with-a-single-tree-and-multiple-domains"></a>具有单个树和多个域的单林

![单林、单树和多组域图。](../../SfbServer/media/63b9f0dd-6bac-4ba9-ae68-8be032d09dcb.png)
  
此图同样显示了一个林，但它也有一个或多个子域 (此特定示例中有三个子) 。 因此，在 中创建用户的域可能不同于部署 2019 Skype for Business Server域。 为什么担心这一点？ 请记住，在部署前端池Skype for Business Server时，该池中的所有服务器都需要位于单个域中。 可以通过通用管理员组Skype for Business Server跨Windows管理。
  
在上图中，可以看到一个域中的用户可以从同一个域或不同域访问 Skype for Business Server 池，即使这些用户位于子域中。
  
#### <a name="single-forest-with-multiple-trees-and-disjoint-namespaces"></a>具有多个树和互不连接的命名空间的单林

![单个林、多个树和脱节命名空间图。](../../SfbServer/media/5ede77a1-f5d2-499c-a2c8-d02f3c2f7cd7.png)
  
您可能具有与此图类似的拓扑，其中您具有一个林，但该林中有多个域，具有单独的 AD 命名空间。 在此例中，此图是一个很好的图示，因为它包含访问 2019 年 3 Skype for Business Server域中的用户。 实线表示他们访问Skype for Business Server域中的池，而虚线表示他们一起进入另一个树中的池。
  
可以看到，同一域、同一树甚至不同树中的用户可以成功访问池。
  
#### <a name="multiple-forests-in-a-central-forest-topology"></a>中央林拓扑中的多林

![中央林拓扑图中的多个林。](../../SfbServer/media/fec40746-4254-4c84-86b9-aad4a616ea2f.png)
  
Skype for Business Server 2019 支持在中央林拓扑中配置的多个林。 如果您不确定自己拥有什么，拓扑中的中央林将使用其中的对象来表示其他林中的用户，并承载林中任何用户的用户帐户。
  
这如何工作？ 目录同步产品 (（如 Forefront Identity Manager）或 FIM) 管理您组织的用户帐户的一直存在。 在林中创建或删除帐户时，该更改将同步到中央林中的相应联系人。
  
很明显，如果 AD 基础结构已就位，那么迁移到此拓扑可能并不简单，但如果已经位于此拓扑中，或者仍在规划林基础结构，这可能是一个不错的选择。 您可以将 2019 Skype for Business Server集中到单个林中，同时用户可以搜索、沟通和查看任何林中其他用户的存在。 使用同步软件自动处理所有用户联系人更新。
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology"></a>资源林拓扑中的Skype for Business林
<a name="BKMK_multipleforestopology"> </a>

![资源林拓扑图中的多个林。](../../SfbServer/media/41efa3b6-d9e6-47df-992b-fefcfc39a80d.png)
  
还支持资源林拓扑;林专用于运行服务器应用程序，如 Microsoft Exchange Server 和 Skype for Business Server 2019。 此资源林还承载活动用户对象的同步表示形式，但没有启用登录的用户帐户。 因此，资源林是用户对象所在的其他林的共享服务环境，并且它们与资源林具有林级信任关系。
  
请注意，Exchange Server可以部署在同一资源林中，Skype for Business Server部署在不同的林中。
  
若要在此类型的拓扑中部署 Skype for Business Server 2019，您可以在资源林中为用户林中每个用户帐户创建一个已禁用的用户对象 (如果环境中已有 Microsoft Exchange Server，则此操作可能会为) 。 然后，你需要目录同步工具 (Forefront Identity Manager 或 FIM) 来管理用户帐户的生命周期。
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology-with-exchange-online"></a>资源林拓扑中的多个Skype for Business具有多个Exchange Online
<a name="BKMK_multipleforestopology"> </a>

此拓扑类似于在资源林拓扑中的多个林Skype for Business[拓扑](system-requirements.md#BKMK_multipleforestopology)。
  
在此拓扑中，存在一个或多个用户林，Skype for Business Server专用资源林中部署此拓扑。 Exchange Server部署在同一资源林或不同林中，并配置为与 Exchange Online 进行混合，或者电子邮件服务可能由 Exchange Online 专门为本地帐户提供。 没有可用于此拓扑的图表。
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-skype-for-business-online-and-azure-active-directory-connect"></a>资源林拓扑中的多个林，Skype for Business Online 和 Azure Active Directory 连接
<a name="BKMK_multipleforestopology"> </a>

![显示两个 AD 林，一个用户林和一个资源林。 这两个林具有信任关系。 它们使用 Azure AD Microsoft 365与 连接。 所有用户都可以通过 Skype for Business 启用Microsoft 365。](../../SfbServer/media/6d54558d-8786-4ebf-90f6-55ae3fdb5ae7.jpg)
  
在此方案中，本地有多个林，具有一个资源林拓扑。 Active Directory 林之间具有完全信任关系。 Azure Active Directory 连接工具用于在内部部署用户林和本地用户林之间Microsoft 365或Office 365。
  
 组织还具有Microsoft 365或Office 365，并使用 Azure Active Directory 连接 将其本地帐户与[](/azure/active-directory/connect/active-directory-aadconnect)Microsoft 365 或 Office 365。 启用此功能的用户Skype for Business通过 Microsoft 365 或 Office 365 Skype for Business Online。 Skype for Business Server本地部署。
  
单一登录身份验证由位于用户林中的 Active Directory 联合身份验证服务服务器场提供。
  
在此方案中，支持在本地部署Exchange、Exchange Online混合 Exchange 解决方案，或完全Exchange部署。  (该图Exchange本地部署，但其他 Exchange 解决方案也完全受支持。) 
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-hybrid-skype-for-business"></a>具有混合部署的资源林拓扑中的多个Skype for Business
<a name="BKMK_multipleforestopology"> </a>

在此方案中，存在一个或多个本地用户林，Skype for Business部署在专用资源林中，并配置为使用 Skype for Business Online 的混合模式。 Exchange Server部署在同一资源林或不同林中，并可以配置为与 Exchange Online 进行混合。 或者，电子邮件服务可能由 Exchange Online 专门为内部部署帐户提供。
  
有关详细信息，请参阅为混合 [Skype for Business 配置多林环境](../../SfbHybrid/hybrid/configure-a-multi-forest-environment-for-hybrid.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)。
  
## <a name="domain-name-system-dns"></a>域名系统 (DNS)
<a name="DNS"> </a>

Skype for Business Server 2019 需要 DNS，原因如下：
  
- DNS 允许 Skype for Business Server 2019 发现内部服务器或池，从而允许服务器到服务器的通信。
    
- DNS 允许客户端计算机发现用于 SIP 事务的前端池或 Standard Edition Server。
    
- 它将会议的简单 URL 与承载这些会议的服务器关联。
    
- DNS 允许外部用户和客户端计算机连接到边缘服务器或 HTTP 反向代理，以便即时消息 (IM) 或会议。
    
- 它允许未登录 (UC) 设备的统一通信发现运行设备更新 Web 服务的前端池或 Standard Edition Server，以获取更新和发送日志。
    
- 使用 DNS，移动客户端可以自动发现 Web 服务资源，而无需用户手动输入其设备设置中的 URL。
    
- 它用于 DNS 负载平衡。
    
需要注意的是，Skype for Business Server 2019 不支持通过 IDN (国际化) 。
  
请记住，DNS 中任何名称与 Skype for Business Server 2019 使用的任何服务器上配置的计算机名称相同，这一点非常重要。 具体来说，环境中不能有任何短名称，并且必须具有用于拓扑生成器的 FQDN。
  
这看起来对于已加入域的任何计算机来说都符合逻辑，但如果边缘服务器未加入域，则其默认名称可能是短名称，没有域后缀。 请确保 DNS 或边缘服务器或任何 Skype for Business Server 2019 服务器或池中不存在这种情况。
  
绝对不要使用 Unicode 字符或下划线。 外部 (DNS 和公共证书颁发机构支持标准字符 (即 A-Z、a-z、0-9 和连字符) 。您需要将 FQDN 分配给证书中的 SN，记住) 这一点很重要，因此从一开始就牢记这一点，您将可以省去许多麻烦。
  
有关网络 DNS 要求的进一步阅读，请查看 [我们的规划文档的](../../SfbServer/plan-your-deployment/network-requirements/network-requirements.md) 网络部分。
  
## <a name="certificates"></a>证书
<a name="Certs"> </a>

在部署之前，可以执行最重要的操作之一是确保证书已按顺序排列。 Skype for Business Server 2019 需要公钥基础结构 (PKI) ，用于传输层安全性 (TLS) 和相互传输层安全性 (MTLS) 连接。 基本上，为了以标准化的方式安全地通信，Skype for Business Server 使用证书颁发机构颁发的证书 (CA) 。
  
Skype for Business Server 2019 将证书用于以下一些用途：
  
- 客户端和服务器之间的 TLS 连接
    
- 服务器之间的 MTLS 连接
    
- 使用自动发现伙伴 DNS 的联盟
    
- 远程用户访问即时消息 (IM)
    
- 外部用户访问音频/视频 (AV) 会话、应用程序共享和会议
    
- 与 Web 应用程序和 OWA (Outlook Web Access) 
    
因此，必须规划证书。 现在，我们来看看请求证书时需要记住的一些内容列表：
  
- 所有服务器证书都必须支持服务器授权（服务器 EKU）。
    
- 所有服务器证书都必须包含一个 CRL 分发点 (CDP)。
    
- 所有证书都必须使用操作系统支持的签名算法进行签名。 Skype for Business Server 2019 支持摘要大小为 (224、256、384 和 512 位) 的 SHA-1 和 SHA-2 套件，并且满足或超过操作系统要求。
    
- 运行 Skype for Business Server 2019 的内部服务器支持自动注册。
    
- Skype for Business Server 2019 边缘服务器不支持自动注册。
    
> [!NOTE]
> 不支持使用 RS UNSUPPORT-PSS 签名算法，并且可能导致登录和呼叫转发问题等错误。 
  
- 支持加密密钥长度为 1024、2048 和 4096。 建议使用密钥长度 2048 及更大。
    
- 默认摘要算法（即哈希签名）算法为 RSA。 还ECDH_P256、ECDH_P384和ECDH_P521算法。
    
需要思考很多，从 CA 请求证书时有多种舒适级别。 我们将在下面为您提供一些进一步指导，尽可能使规划更加难用。
  
### <a name="certificates-for-your-internal-servers"></a>内部服务器的证书

大多数内部服务器都需要证书，很可能你会从内部 CA 证书获取证书 (该 CA 位于你的域或域中) 。 如果需要，可以从位于 Internet (的外部 CA 请求这些) 。 如果您想知道应转到哪一个公共 CA，请查看统一 [通信证书合作伙伴](../../SfbPartnerCertification/certification/services-ssl.md) 列表。
  
当 Skype for Business Server 2019 与其他应用程序和服务器（如 Microsoft Exchange Server）通信时，你还需要证书。 显然，这应该是其他这些应用和服务器可以支持的方式使用的证书。 Skype for Business Server 2019 和其他 Microsoft 产品支持 Open Authorization (OAuth) 协议，用于服务器到服务器身份验证和授权。 如果你对此感兴趣，我们提供了另一篇有关 OAuth 和 Skype for Business Server 2019 的规划文章。
  
Skype for Business Server 2019 还包括对 (的支持，而无需) SHA-256 加密哈希函数签名的证书。 若要支持使用 SHA-256 进行外部访问，外部证书需要由公共 CA 使用 SHA-256 颁发。
  
为了简单明了，我们将 Standard Edition 服务器、前端池和其他角色的证书要求置于下表中，其中的示例使用了虚构的 contoso.com (你可能会为环境) 使用其他内容。 这些证书都是标准 Web 服务器证书，具有不可导出的私钥。 还需要注意其他一些注意事项：
  
- 使用证书向导请求 (EKU) 将自动配置服务器增强型密钥用法。
    
- 每个证书友好名称在计算机存储中必须是唯一的。
    
- 根据下面的示例名称，如果你已在你的 DNS 中配置 sipinternal.contoso.com 或 sipexternal.contoso.com，则需要将它们添加到证书的 SUBJECT Alternative Name (SAN) 。
    
Standard Edition 服务器的证书：
  
|证书|主题名称/公用名|使用者替代名称|示例|备注|
|:-----|:-----|:-----|:-----|:-----|
|默认值   |池的 FQDN   |池的 FQDN 和服务器的 FQDN  <br/> 如果具有多个 SIP 域并已启用自动客户端配置，则证书向导会检测并添加所有受支持的 SIP 域 FQDN。  <br/> 如果此池是客户端的自动登录服务器，而且组策略要求执行严格的域名系统 (DNS) 匹配，那么还需要 sip.sipdomain 条目（对应于您拥有的每个 SIP 域）。   |SN=se01.contoso.com;SAN=se01.contoso.com  <br/> 如果此池是客户端的自动登录服务器，而且组策略要求执行严格的 DNS 匹配，则还需要 SAN=sip.contoso.com; SAN=sip.fabrikam.com。   |在 Standard Edition Server 上，服务器 FQDN 与池 FQDN 相同。  <br/> 证书向导会检测您在安装过程中所指定的任何 SIP 域，然后自动将它们添加到使用者替代名称中。  <br/> 您还可以使用此证书进行服务器到服务器身份验证。   |
|Web 内部   |服务器的 FQDN   |以下各项：  <br/> • 内部 Web FQDN (与服务器服务器的 FQDN 相同)   <br/> AND  <br/> • 开会简单 URL  <br/> • 拨入简单 URL  <br/> • 管理简单 URL  <br/> 或  <br/> • 简单 URL 的通配符条目   |SN=se01.contoso.com;SAN=se01.contoso.com;SAN=meet.contoso.com;SAN=meet.fabrikam.com;SAN=dialin.contoso.com;SAN=admin.contoso.com  <br/> 使用通配符证书：  <br/> SN=se01.contoso.com;SAN=se01.contoso.com;SAN= \* .contoso.com   |无法替代拓扑生成器中的内部 Web FQDN。  <br/> 如果你有多个 Meet 简单 URL，则必须将它们全部包含为 SAN。  <br/> 简单 URL 条目支持通配符条目。   |
|Web 外部   |服务器的 FQDN   |以下各项：  <br/> • 外部 Web FQDN  <br/> AND  <br/> • 拨入简单 URL  <br/> • 每个 SIP 域的 Meet 简单 URL  <br/> 或  <br/> • 简单 URL 的通配符条目   |SN=se01.contoso.com;SAN=webcon01.contoso.com;SAN=meet.contoso.com;SAN=meet.fabrikam.com;SAN=dialin.contoso.com  <br/> 使用通配符证书：  <br/> SN=se01.contoso.com;SAN=webcon01.contoso.com;SAN= \* .contoso.com   |如果您具有多个会议简单 URL，则必须将它们作为使用者替代名称全部添加。  <br/> 简单 URL 条目支持通配符条目。   |
   
前端池中前端服务器的证书：
  
|证书|主题名称/公用名|使用者替代名称|示例|备注|
|:-----|:-----|:-----|:-----|:-----|
|默认   |池的 FQDN   |池的 FQDN 和服务器的 FQDN  <br/> 如果具有多个 SIP 域并已启用自动客户端配置，则证书向导会检测并添加所有受支持的 SIP 域 FQDN。  <br/> 如果此池是客户端的自动登录服务器，而且组策略要求执行严格的域名系统 (DNS) 匹配，那么还需要 sip.sipdomain 条目（对应于您拥有的每个 SIP 域）。   |SN=eepool.contoso.com;SAN=eepool.contoso.com;SAN=ee01.contoso.com  <br/> 如果此池是客户端的自动登录服务器，而且组策略要求执行严格的 DNS 匹配，则还需要 SAN=sip.contoso.com; SAN=sip.fabrikam.com。   |证书向导会检测您在安装过程中所指定的任何 SIP 域，然后自动将它们添加到使用者替代名称中。  <br/> 您还可以使用此证书进行服务器到服务器身份验证。   |
|Web 内部   |池的 FQDN   |以下各项：  <br/> • 内部 Web FQDN (与服务器服务器的 FQDN 不同)   <br/> • 服务器 FQDN  <br/> • Skype for Business池 FQDN  <br/> AND  <br/> • 开会简单 URL  <br/> • 拨入简单 URL  <br/> • 管理简单 URL  <br/> 或  <br/> • 简单 URL 的通配符条目   |SN=ee01.contoso.com;SAN=ee01.contoso.com;SAN=meet.contoso.com;SAN=meet.fabrikam.com;SAN=dialin.contoso.com;SAN=admin.contoso.com  <br/> 使用通配符证书：  <br/> SN=ee01.contoso.com;SAN=ee01.contoso.com;SAN= \* .contoso.com   |如果您具有多个会议简单 URL，则必须将它们作为使用者替代名称全部添加。  <br/> 简单 URL 条目支持通配符条目。   |
|Web 外部   |池的 FQDN   |以下各项：  <br/> • 外部 Web FQDN  <br/> AND  <br/> • 拨入简单 URL  <br/> • 管理简单 URL  <br/> 或  <br/> • 简单 URL 的通配符条目   |SN=ee01.contoso.com;SAN=webcon01.contoso.com;SAN=meet.contoso.com;SAN=meet.fabrikam.com;SAN=dialin.contoso.com  <br/> 使用通配符证书：  <br/> SN=ee01.contoso.com;SAN=webcon01.contoso.com;SAN= \* .contoso.com   |如果您具有多个会议简单 URL，则必须将它们作为使用者替代名称全部添加。  <br/> 简单 URL 条目支持通配符条目。   |
   
控制器的证书：
  
|证书|主题名称/公用名|使用者替代名称|示例|
|:-----|:-----|:-----|:-----|
|默认   |控制器池   |控制器的 FQDN，控制器池的 FQDN。  <br/> 如果此池是客户端的自动登录服务器，并且组策略要求进行严格的 DNS 匹配，则还需要为已登录的每个 SIP 域 (sip.sipdomain) 。   |pool.contoso.com;SAN=dir01.contoso.com  <br/> 如果此控制器池是客户端的自动登录服务器，而且组策略要求执行严格的 DNS 匹配，那么您还需要 SAN=sip.contoso.com; SAN=sip.fabrikam.com。   |
|Web 内部   |服务器的 FQDN   |以下各项：  <br/> • 内部 Web FQDN (与服务器服务器的 FQDN 相同)   <br/> • 服务器 FQDN  <br/> • Skype for Business池 FQDN  <br/> AND  <br/> • 开会简单 URL  <br/> • 拨入简单 URL  <br/> • 管理简单 URL  <br/> 或  <br/> • 简单 URL 的通配符条目   |SN=dir01.contoso.com;SAN=dir01.contoso.com;SAN=meet.contoso.com;SAN=meet.fabrikam.com;SAN=dialin.contoso.com;SAN=admin.contoso.com  <br/> 使用通配符证书：  <br/> SN=dir01.contoso.com;SAN=dir01.contoso.com SAN= \* .contoso.com   |
|Web 外部   |服务器的 FQDN   |以下各项：  <br/> • 外部 Web FQDN  <br/> AND  <br/> • 每个 SIP 域的 Meet 简单 URL  <br/> • 拨入简单 URL  <br/> 或  <br/> • 简单 URL 的通配符条目   |控制器外部 Web FQDN 必须与前端池或前端服务器不同。  <br/> SN=dir01.contoso.com;SAN=directorwebcon01.contoso.com SAN=meet.contoso.com;SAN=meet.fabrikam.com;SAN=dialin.contoso.com  <br/> 使用通配符证书：  <br/> SN=dir01.contoso.com;SAN=directorwebcon01.contoso.com SAN= \* .contoso.com   |
   
独立中介服务器的证书：
  
|证书|主题名称/公用名|使用者替代名称|示例|
|:-----|:-----|:-----|:-----|
|默认值   |池的 FQDN   |池的 FQDN  <br/> 池成员服务器的 FQDN   |SN=medsvr-pool.contoso.net;SAN=medsvr-pool.contoso.net;SAN=medsvr01.contoso.net   |
   
Survivable Branch Appliance (，特别是 Survivable Branch Appliance 2015 for Skype for Business Server 2019) ：
  
|证书|主题名称/公用名|使用者替代名称|示例|
|:-----|:-----|:-----|:-----|
|默认值   |设备的 FQDN   |SIP。\<sipdomain\>  (每个 SIP 域服务器只需要一个)    |SN=sba01.contoso.net;SAN=sip.contoso.com;SAN=sip.fabrikam.com   |
   
### <a name="certificates-for-external-user-access-edge"></a>边缘服务器的外部用户访问 (证书) 

Skype for Business Server 2019支持将单个公共证书用于访问和 Web 会议边缘外部接口，以及 A/V 身份验证服务，该服务全部通过边缘服务器 (提供) 。 边缘内部接口通常使用内部 CA 颁发的专用证书，但如果愿意，也可以对此使用公共证书（如果证书来自受信任的 CA）。
  
反向代理 (RP) 也将使用公共证书，它将加密从 RP 到客户端的通信，以及使用 HTTP (或更精确的 TLS over HTTP) 到内部服务器的通信。
  
### <a name="certificates-for-mobility"></a>移动证书

如果要部署移动功能并且支持移动客户端的自动发现，则需要在证书上添加一些其他主题替代名称条目，以支持来自移动客户端的安全连接。
  
对于以下证书上的自动发现，你需要 SAN 名称：
  
- 控制器池
    
- 前端池
    
- 反向代理
    
下表列出了具体信息。
  
这是一些预先规划良好的地方，但有时你已部署 Skype for Business Server 2019，但不打算部署移动功能，稍后在环境中已有证书时，这一点将启动。 通过内部 CA 重新颁发证书通常非常简单，但使用公共 CA 颁发的公共证书，这一点可能稍高一些。
  
如果你正在查看这一点，并且有很多 SIP 域 (这会使添加 SAN 的成本更高) ，可以将反向代理配置为将 HTTP 用于初始自动发现服务请求，而不是使用 HTTPS (这是默认配置) 。 规划 [移动功能](../../SfbServer/plan-your-deployment/mobility.md) 一文对此有详细信息。
  
控制器池和前端池证书要求：
  
|说明|SAN 条目|
|:-----|:-----|
|内部自动发现服务 URL   |SAN=lyncdiscoverinternal。\<sipdomain\>   |
|外部自动发现服务 URL   |SAN=lyncdiscover。\<sipdomain\>   |
   
您也可以使用 SAN= \* 。\<sipdomain\>
  
反向代理 (公共 CA) 证书要求：
  
|说明|SAN 条目|
|:-----|:-----|
|外部自动发现服务 URL   |SAN=lyncdiscover。\<sipdomain\>   |
   
此 SAN 需要分配给分配给反向代理上的 SSL 侦听器的证书。
  
> [!NOTE]
> 反向代理侦听器将包含外部 Web 服务 URL (SN) 。 例如，SAN=skypewebextpool01.contoso.com 和 dirwebexternal.contoso.com（如果已部署控制器， (可选) ）。 
  
## <a name="file-share"></a>文件共享
<a name="Fileshare"> </a>

Skype for Business Server 2019 可以针对所有文件存储使用相同的文件共享。 您需要记住以下事项：
  
- 文件共享需要位于直接附加存储 (DAS) 或存储区域网络 (SAN) 上，这包括分布式文件系统 (DFS) 以及文件存储的独立磁盘冗余阵列 (RAID) 。 有关 DFS for Windows Server 2012，请查看 [此 DFS 页面](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj127250(v=ws.11))。
    
- 我们建议文件共享使用共享群集。 如果你已在使用一个，则应该Windows Server 2012或更高版本

> [!Note]
> **为什么要使用最新的 Windows？** 旧版本可能没有启用所有功能所需的正确权限。 可以使用群集管理员创建文件共享。 有关详细信息，请参阅此支持文章 [如何在群集上](https://support.microsoft.com/help/224967) 创建文件共享。
    
> [!CAUTION]
> 你应知道，不支持将网络 (NAS) 用作文件共享，因此请使用上面列出的选项之一。 此支持限制是由 NAS 设备的可变设计导致的，这些设备必须针对访问设备的共享文件系统的基于 Windows Server 的计算机提供文件系统自适应性。
