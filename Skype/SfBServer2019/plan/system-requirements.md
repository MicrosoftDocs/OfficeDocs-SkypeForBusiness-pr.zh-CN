---
title: For Business Server 2019 Skype 的系统要求
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 摘要： 准备您的 Skype 业务服务器 2019年服务器和域基础结构与本主题。 硬件、 操作系统、 数据库、 软件、 所有系统要求和建议，以及证书 DNS、 文件共享和 Active Directory 信息，在此处都要帮助确保成功安装和部署服务器场。
ms.openlocfilehash: c7064f4d1c8136cf714d784fd1985efd0f21c979
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2018
ms.locfileid: "26296153"
---
# <a name="system-requirements-for-skype-for-business-server-2019"></a>For Business Server 2019 Skype 的系统要求
 
**摘要：** 准备要使用本主题为业务服务器 2019年安装 Skype。 下面介绍硬件、 操作系统、 软件、 数据库、 证书、 活动目录、 DNS 和 fileshares。 所有的系统要求和建议的此处帮助确保成功安装和部署服务器场。
  
如预期的那样，有一些进行准备开始部署业务服务器 2019 Skype 之前。 本文将指导你制定以下规划：
  
- [硬件](system-requirements.md#Hardware)
  
- [操作系统](system-requirements.md#OS)
  
- [软件](system-requirements.md#Software)

- [后端 SQL 数据库](system-requirements.md#DBs)
  
- [Active Directory](system-requirements.md#AD)
  
- [域名系统 (DNS)](system-requirements.md#DNS)
  
- [证书](system-requirements.md#Certs)
  
- [文件共享](system-requirements.md#Fileshare)

  
## <a name="hardware-for-skype-for-business-server-2019"></a>为业务服务器 2019 Skype 的硬件
<a name="Hardware"> </a>

您必须向下您的拓扑 （并且否则，您可以签出[的业务服务器 2019年的 Skype 拓扑基础知识](../../SfbServer/plan-your-deployment/topology-basics/topology-basics.md)主题） 后，它具有时间考虑服务器。 Skype 业务服务器 2019年服务器要求使用 64 位硬件。 下面给出了我们的硬件建议。 这些不要求，但它们反映所必需的最佳性能的要求。 我们的容量规划文档可帮助你根据自己的环境确定是否需要高于此要求的配置。
  
对于 Standard Edition 服务器的推荐的硬件配置：

|**硬件组件**|**推荐**|
|:-----|:-----|
|CPU  <br/> |Intel Xeon E5 2673 v3 双处理器、 6 核 2.4 ghz 或更高版本。  <br/> Intel Itanium 处理器不支持 Skype 业务服务器 2019年角色。  <br/> |
|内存  <br/> |32 GB。  <br/> |
|磁盘  <br/> |以下之一：  <br/> • 8 块或更多 10000 RPM 硬盘，至少 72 GB 可用磁盘空间（2 块磁盘使用 RAID 1，6 块磁盘使用 RAID 10）。  <br/> 或  <br/> • 能够提供与 8 块 10000 RPM 机械硬盘相同的可用空间和类似性能的固态硬盘 (SSD)。  <br/> |
|网络  <br/> |1 个双端口网络适配器，1 Gbps 或更高（可使用 2 个网络适配器，但需要通过一个 MAC 地址和一个 IP 地址配合使用）。  <br/> 双处理器或多宿主配置是**不**支持前端服务器、 后端服务器，和 Standard Edition 服务器。 <br/> 只要它们不公开给操作系统，并且正在使用监视和管理服务器硬件，您可以通过带管理系统，如 DRAC 或 ILO。 这种情况不会形成多宿主服务器，并且受支持。  <br/> |


前端服务器和后端服务器的推荐的硬件：
  
|**硬件组件**|**推荐**|
|:-----|:-----|
|CPU  <br/> |Intel Xeon E5 2673 v3 双处理器、 6 核 2.4 ghz 或更高版本。 <br/> Intel Itanium 处理器不支持 Skype 业务服务器 2019年角色。  <br/> |
|内存  <br/> |64 千兆字节 (GB)。  <br/> |
|磁盘  <br/> |以下之一：  <br/> • 8 块或更多 10000 RPM 硬盘，至少 72 GB 可用磁盘空间（2 块磁盘使用 RAID 1，6 块磁盘使用 RAID 10）。  <br/> 或  <br/> • 能够提供与 8 块 10000 RPM 机械硬盘相同的可用空间和类似性能的固态硬盘 (SSD)。  <br/> |
|网络  <br/> |1 个双端口网络适配器，1 Gbps 或更高（可使用 2 个网络适配器，但需要通过一个 MAC 地址和一个 IP 地址配合使用）。  <br/> 双处理器或多宿主配置是**不**支持前端服务器、 后端服务器，和 Standard Edition 服务器。 <br/> 只要它们不公开给操作系统，并且正在使用监视和管理服务器硬件，您可以通过带管理系统，如 DRAC 或 ILO。 这种情况不会形成多宿主服务器，并且受支持。  <br/> |
   
建议的边缘服务器、 独立中介服务器和控制器的硬件：
  
|**硬件组件**|**推荐**|
|:-----|:-----|
|CPU  <br/> |Intel Xeon E5 2673 v3 双处理器、 6 核 2.4 ghz 或更高版本。  <br/> Intel Itanium 处理器不支持 Skype 业务服务器 2019年角色。  <br/> |
|内存  <br/> |32 千兆字节。  <br/> |
|磁盘  <br/> |以下之一：  <br/> • 4 块或更多 10000 RPM 硬盘，至少 72 GB 可用磁盘空间（磁盘应采用双 RAID 1 配置）。  <br/> 或  <br/> • 能够提供与 4 块 10000 RPM 机械硬盘相同的可用空间和类似性能的固态硬盘 (SSD)。  <br/> |
|网络  <br/> |1 个双端口网络适配器，1 Gbps 或更高（可使用 2 个网络适配器，但需要通过一个 MAC 地址和一个 IP 地址配合使用）。  <br/> 双处理器或多宿主配置是**不**支持视频互操作服务器和控制器。 <br/> 边缘服务器需要两个网络接口，均为双端口网络适配器、1 Gbps 或更高速度（或两个成对网络适配器，总计 4 个适配器，每一对均与单一 MAC 地址和单一 IP 地址配合使用，总共两对）。  <br/> 在独立中介服务器，支持的其他网络接口卡 (Nic) 以允许的特定 PSTN IP 地址配置安装。  <br/> |


> [!NOTE]
> 无论服务器角色，我们还建议的业务服务器 2019 Skype 的以下硬件设置 (这可能有所不同，具体取决于您已购买，这样的硬件的品牌请参考细节的制造商文档):
> - 单层从 NUMA BIOS config-应设置为。
> - 启用超线程。
> - RSS 队列设置应设置为 8 的队列。

   
## <a name="operating-systems-for-skype-for-business-server-2019"></a>为业务服务器 2019 Skype 的操作系统
<a name="OS"> </a>

就地硬件后，您将需要对安装操作系统 (OS) 使您可以安装和使用业务服务器 2019 Skype 成功。
  
|||
|:-----|:-----|
|Windows Server 2019 <br/> |
|Windows Server 2016 <br/> ||
||
   
除了下面列出的操作系统不会处理正确; 的内容请不尝试使用它的 Skype 安装的业务服务器 2019年。

> [!NOTE]
> 
> 如果您在 Windows Server 2019 计算机上安装 Windows 管理员中心 2019年，它将提示您输入侦听的端口。 您可以选择端口 443，liklihood，但如果该计算机的业务服务器 2019 上，安装具有 Skype，或者是要在其上安装的业务服务器 2019年具有 Skype，则必须选择不同的端口号。
> 
>为什么是这种情况？ 如果在端口 443 上正在运行 Windows 管理员中心 2019年，您将无法连接到服务器的业务控制面板中，使用 Skype 也能够连接到任何 （通讯簿 Web 服务的服务器上运行的内部 web 服务自动发现服务、 WebTicket 服务等)。  实际上，您将无法连接到任何内部 Web 服务 URL。 请在事件需要或的业务服务器 2019年放置 Skype 与服务器上的 Windows 管理员中心 2019年，选择不同的端口。
> 

  
## <a name="software-that-should-be-installed-before-a-skype-for-business-server-2019-deployment"></a>应在业务服务器 2019年部署 Skype 之前安装的软件
<a name="Software"> </a>

有一些事项是，您将需要安装或运行业务服务器 2019 Skype 任何服务器的配置。 这些如下所示后, 跟特定服务器角色的其他要求。
  
 **所有服务器：**
  
|**软件/角色**|**详细信息**|
|:-----|:-----|
|Windows PowerShell 3.0  <br/> |为业务 Server 服务器的所有 Skype 都需要安装的 Windows PowerShell 3.0。  <br/> • 这应与 Windows Server 2016 的默认情况下安装。<br/> |
|Microsoft .NET Framework  <br/> |WCF 服务是一项**功能**已安装作为 Windows 功能，在**服务器管理器**下没有所需的下载。 <br/> • 所需安装此功能，或者如果它已经安装并正在对其，检查的**HTTP 激活**选项还会检查和安装，以确保，如下所示： <br/> ![屏幕截图显示 .NET Framework 4.5 功能下的 HTTP 激活选项。](../../SfbServer/media/a4064fa0-fa49-4474-bd98-b9a79ff68f8b.png) <br/> 如果您看到另一则弹出信息，表示要安装“HTTP 激活”，还需要安装其他某些功能，请不必担心。 这是正常;单击确定，然后继续操作。 如果您没有获得此弹出，您可以假定这些操作已安装并继续操作。  <br/> 安装 Windows Server 2016 时，通常安装 Microsoft.NET Framework。 Skype 业务 server 适用于以下的 Microsoft.NET Framework 版本：  <br/> •.NET 3.5  <br/> •.NET 4.5  <br/> •.NET 4.6.x  <br/> •.NET 4.7 <br/> |
|媒体基础  <br/> |对于 Windows Server 2016 Windows Media Format Runtime 安装 Microsoft 媒体基础。  <br/> 用于会议的所有前端服务器和 Standard Edition 服务器需要 Windows Media Format Runtime，若要运行的 Windows Media 音频 (.wma) 文件的呼叫寄存、 通知和响应组应用程序播放通知和保持音乐。  <br/> |
|Windows Identity Foundation  <br/> |我们需要 Windows Identity Foundation 3.5 对业务服务器 2019 Skype 支持服务器到服务器身份验证方案。  <br/> ？ 对于 Windows Server 2016 没有不需要下载任何内容。 打开**服务器管理器**，转到**添加角色和功能向导**。 **Windows Identity Foundation 3.5** 在**功能**部分列出。 如果选择它，您很好。 否则为选择它，然后单击**下一步**到达**安装**按钮。 <br/> |
|远程服务器管理工具  <br/> |角色管理工具：AD DS 和 AD LDS 工具  <br/> |
   
 **前端服务器和 Standard Edition server 还需要：**
  
|**软件/角色**|**详细信息**|
|:-----|:-----|
|Internet Information Services (IIS)  <br/> |IIS 的以下模块选择需要的所有前端服务器，以及所有 Standard Edition server 上：  <br/> • 常见 HTTP 功能： 默认文档，HTTP 错误静态内容  <br/> • 运行状况和诊断： HTTP 日志记录，日志记录工具，跟踪  <br/> • 性能： 静态内容压缩、 动态内容压缩  <br/> • 安全： 请求筛选、 客户端证书映射身份验证、 Windows 身份验证  <br/> • 应用程序开发：.NET 扩展性 3.5、.NET 扩展性 4.5、 ASP.NET 3.5、 ASP.NET 4.5，ISAPI 扩展 ISAPI 筛选器  <br/> • 管理工具： IIS 管理控制台、 IIS 管理脚本和工具  <br/> 请注意，还需要匿名访问，但在您安装 IIS，以便您无需在列表中选择一个位置时，会看到的。  <br/> |
|Windows Media Format Runtime  <br/> | Windows Server 2016，您需要在**服务器管理器**中安装**媒体 Foundation**功能。 实际可以开始业务服务器 2019年安装没有它，您 Skype 但系统将提示您安装它，然后重新启动服务器，业务服务器 2019年 Skype 之前安装继续。 最好不要提早制定。 <br/> |
|Silverlight  <br/> |您可以安装最新版本的 Silverlight[此处](https://www.microsoft.com/silverlight/)。  <br/> |
   
为帮助您了解相关过程，我们提供了一个示例 PowerShell 脚本，您可以运行此脚本以自动执行此流程：
  
```
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, Telnet-Client
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
    
（如果您想知道，它是设置为具有动态内容压缩的前端服务器和 Standard Edition 服务器相同模块和管理工具遗漏。）
  
我们还为此提供了以下一些 PowerShell 代码：
  
```
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, Telnet-Client
```

## <a name="back-end-databases-that-will-work-with-skype-for-business-server-2019"></a>将用于业务服务器 2019 Skype 的后端数据库
<a name="DBs"> </a>

安装时 Skype 对于业务 Server 2019 Standard Edition，您必须 SQL Server 2016 Express （64 位版本）。

对于业务 Server 2019 Enterprise Edition 的 Skype 将需要完整的 SQL Server，，，如下所示 (仅 64 位版本; 请不要使用 32 位版本):
  
||||
|:-----|:-----|:-----|
|Microsoft SQL Server 2016/2017年企业版 （64 位版本），并且您必须运行与最新的更新和 AlwaysOn 可用性组。  <br/> ||
 |
   
如果您没有看到要使用此处列出的 SQL Server 版本，则无法使用它。
  
> [!NOTE]
> 您还需要安装监控服务器角色的 SQL Server Reporting Services。 
  
### <a name="sql-clustering-and-sql-always-on"></a>SQL 群集和 SQL 始终在

支持与 Skype 的业务服务器 2019 SQL 群集。 如果您想要设置 SQL 群集，完成在 SQL Server 中。
  
请确保您具有主动/被动配置 SQL 群集，这受支持。 不与任何其他 SQL 实例共享被动节点。
  
可以为故障转移群集采用以下配置：
  
双节点：
  
- Microsoft SQL Server 2016/2017年标准 （64 位版本），以及我们建议最新的 service pack 的运行。
    
16 节点：
  
- Microsoft SQL Server 2016/2017年企业版 （64 位版本），以及我们建议最新的 service pack 的运行。
    
我们必须文章，配置 SQL Server 群集的 Skype 的业务服务器 2019，已获取就绪群集的步骤。
 
支持 SQL Always On，并且您可以阅读更多有关该产品中[的业务服务器 2019 Skype 后端服务器高可用性](../../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md)。
  

###  <a name="additional-server-installation-recommendations"></a>其他服务器安装建议：
  
请不要安装任何 Microsoft Internet Security and Acceleration (ISA) Server 客户端软件或任何其他 Winsock 层次服务提供程序 (LSP) 软件 （任何第三方防火墙或网络防病毒检查软件应该包含此处） 上前端服务器或独立中介服务器的任何。 安装该软件时，出现性能不佳的媒体流量。
  

## <a name="active-directory"></a>Active Directory
<a name="AD"> </a>

尽管何种服务器和服务的配置数据存储在业务 Server 2019 中央管理存储的 Skype，有仍 Active Directory 中存储的事情：
  
|**Active Directory 对象**|**对象类型**|
|:-----|:-----|
|架构扩展  <br/> |用户对象扩展  <br/> |
||支持的版本业务服务器 2015年和 Lync Server 2013，以保持与以前的向后兼容的 Skype 的扩展  <br/> |
|数据  <br/> |用户 SIP URI 和其他用户设置  <br/> |
||联系人对象的应用程序 （如响应组应用程序和会议助理应用程序）  <br/> |
||发布的向后兼容性数据  <br/> |
||服务控制点 (SCP) 的中央管理存储  <br/> |
||Kerberos 身份验证帐户 （可选计算机对象）  <br/> |
   
### <a name="os-for-domain-controllers"></a>域控制器的操作系统

可以使用以下域控制器操作系统：
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
Skype 部署的 Business Server 2019 到，任何域的域功能级别和 Skype 部署的 Business Server 2019 到，任何林中的林功能级别必须为下列选项之一：
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
这些环境中能否有只读域控制器？ 当然，只要有还有可写域控制器。
  
务必要了解的业务服务器 2019 Skype 不支持单标签域。 单标签域是什么？ 如果您有一个标有 contoso.local 的根域，这将为工作正常。 如果您有刚刚名为本地的根域，将不会工作，并因此不支持。 [知识库中的这篇文章](https://support.microsoft.com/kb/300684/en-us)略为详细地介绍了相关内容。
  
Skype 的业务服务器 2019年也不支持域的重命名。 如果您真正需要重命名您的域，您将需要卸载 Skype 的业务服务器 2019年执行域重命名，然后重新安装 Skype 的业务服务器 2019年。
  
最后，您可能正在与使用锁定的 AD DS 环境中，域并没关系，可以。 我们有如何业务服务器 2019 Skype 部署到锁定的 AD DS 环境中部署文档中的详细信息。
  
### <a name="ad-topologies"></a>AD 拓扑

支持的拓扑中的业务服务器 2019 Skype 是：
  
- 具有单个域的单林
    
- 具有单个树和多个域的单林
    
- 具有多个树和互不连接的命名空间的单林
    
- 中央林拓扑中的多林
    
- 资源林拓扑中的多林
    
- 具有 Exchange Online 的 Skype for Business 资源林拓扑中的多个林
    
- 有 Skype for Business Online 和 Azure Active Directory Connect 的资源林拓扑中的多个林
    
我们有图表和可帮助您确定哪些拓扑中具有您的环境，或者您可能需要安装业务服务器 2019 Skype 之前设置的说明。 为了简单起见，我们正在还包括键：
  
![这是用于 Skype for Business 拓扑图的图标的关键](../../SfbServer/media/cc0dbc17-cf81-4b79-bf99-4614cc6828a0.png)
  
#### <a name="single-forest-with-single-domain"></a>具有单个域的单林

![支持的 SFB 与 MA 拓扑，仅限云。](../../SfbServer/media/24921a0b-3a3e-4bad-8427-49300e2e3f7a.png)
  
它不变得更简单比这;它是单域林，常用的拓扑。
  
#### <a name="single-forest-with-a-single-tree-and-multiple-domains"></a>具有单个树和多个域的单林

![单林、单树和多个域图表](../../SfbServer/media/63b9f0dd-6bac-4ba9-ae68-8be032d09dcb.png)
  
此图表同样显示了一个林，但其中还有一个或多个子域（本例中为 3 个）。 使业务服务器 2019年部署到的域中创建用户可能不同域 Skype。 为什么要考虑这一点？ 请记住，当您部署业务 Server 前端池的 Skype 务必，该池中的所有服务器都必须能够在单个域。 您可以跨域管理通过 Skype Business Server Windows 通用管理员组的支持。
  
在上图中，您可以看到一个域中的用户能够访问 Skype 的业务服务器池从同一个域或从不同域中，即使子域中这些用户。
  
#### <a name="single-forest-with-multiple-trees-and-disjoint-namespaces"></a>具有多个树和互不连接的命名空间的单林

![单林、多个树和互不连接的命名空间图表](../../SfbServer/media/5ede77a1-f5d2-499c-a2c8-d02f3c2f7cd7.png)
  
您可能遇到的拓扑类似于此图中，您具有一个资源林中，但在该林中是使用单独的 AD 命名空间的多个域。 在这种情况下，此图是很好的图中，因为它包含访问 Skype 的业务服务器 2019年的三个不同域中的用户。 实线指示他们正在访问自己域中的业务服务器池的 Skype 而虚线表示它们完全转到不同树中的池。
  
您可以看到，同一个域、 在同一个树或甚至不同树中的用户可以成功访问池。
  
#### <a name="multiple-forests-in-a-central-forest-topology"></a>中央林拓扑中的多林

![中央林拓扑中的多林图表](../../SfbServer/media/fec40746-4254-4c84-86b9-aad4a616ea2f.png)
  
Skype 的业务服务器 2019年并支持中央林拓扑中配置的多个林。 如果您不确定这是您拥有什么，中央林拓扑中的使用对象中来表示其他林中和承载任何用户林中的用户帐户中的用户。
  
工作原理是什么？ 目录同步产品 （如 Forefront Identity Manager 或 FIM） 管理它们存在整个组织的用户帐户。 在林中创建或删除帐户时，更改将同步到中央林中的对应联系人。
  
很显然，如果您的 AD 基础结构后，将移动到这种拓扑可能不是简单，但如果您已存在，或仍规划自己林中的基础结构，这可以是一个不错的选择。 用户可搜索、 通信，并查看任何林中其他用户的状态时，您可以集中用于在一个林中，业务服务器 2019年部署您 Skype。 所有用户联系人更新都会通过同步软件自动得到处理。
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology"></a>Skype for Business 资源林拓扑中的多个林
<a name="BKMK_multipleforestopology"> </a>

![资源林拓扑图表中的多林](../../SfbServer/media/41efa3b6-d9e6-47df-992b-fefcfc39a80d.png)
  
此外支持资源林拓扑中;是其中一个林专用于运行服务器应用程序，如 Microsoft Exchange Server 和 Skype 的业务服务器 2019年。 此资源林还承载着活动用户对象的同步表示形式，但不包含启用了登录的用户帐户。 因此资源林用作用户对象所驻留的其他林的共享服务环境，这些林与资源林之间存在林级信任关系。
  
请注意，可以在同一个资源林中 Skype 业务服务器或不同的林中部署 Exchange 服务器。
  
若要部署在这种拓扑的业务服务器 2019 Skype，您将在资源林中的每个用户林中的用户帐户创建一个已禁用的用户对象 （如果 Microsoft Exchange Server 已在环境中，此操作可能会为您）。 然后您需要目录同步工具 （如 Forefront Identity Manager 或 FIM） 可以管理其生命周期的用户帐户。
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology-with-exchange-online"></a>具有 Exchange Online 的 Skype for Business 资源林拓扑中的多个林
<a name="BKMK_multipleforestopology"> </a>

此拓扑与 [Skype for Business 资源林拓扑中的多个林](system-requirements.md#BKMK_multipleforestopology)中所述的拓扑类似。
  
在此拓扑中，有一个或多个用户林和 Skype 业务服务器部署在专用的资源林中。 Exchange Server 可以是在本地部署中相同的资源林或另一个林和与 Exchange Online 的混合配置或可能为内部部署帐户以独占方式通过 Exchange Online 提供电子邮件服务。 目前没有该拓扑的示意图。
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-skype-for-business-online-and-azure-active-directory-connect"></a>有 Skype for Business Online 和 Azure Active Directory Connect 的资源林拓扑中的多个林
<a name="BKMK_multipleforestopology"> </a>

![显示两个 AD 林，一个用户林和一个资源林。这两个林具有信任关系。它们使用 Azure AD Connect 与 Office 365 同步。通过 Office 365 为所有用户启用 Skype for Business。](../../SfbServer/media/6d54558d-8786-4ebf-90f6-55ae3fdb5ae7.jpg)
  
在此方案中，一个资源林拓扑中有多个本地林。Active Directory 林之间为完全信任关系。Azure Active Directory Connect 工具用于在本地用户林和 Office 365 之间同步帐户。
  
 组织还有 Office 365，并使用 [Azure Active Directory Connect](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect) 将其本地帐户与 Office 365 同步。 为业务联机通过 Office 365 和 Skype 启用了用户启用了 for Business 的 Skype。 Skype 业务服务器不在本地部署。
  
由位于用户林的 Active Directory 联合身份验证服务服务器场提供单一登录身份验证。
  
在此方案中，支持部署 Exchange 内部部署，Exchange Online 混合 Exchange 解决方案，或没有根本部署的 Exchange。 （此图显示了仅 Exchange 内部部署，但还完全支持的其他 Exchange 解决方案）。
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-hybrid-skype-for-business"></a>有混合 Skype for Business 的资源林拓扑中的多个林
<a name="BKMK_multipleforestopology"> </a>

在此方案中，有一个或多个内部部署用户林中和 for Business 的 Skype 专用的资源林中部署配置为混合模式与 Skype 的业务联机。 Exchange Server 可以是在本地部署中相同的资源林或另一个林，并且可能与 Exchange Online 的混合配置。 此外，可能为内部部署帐户以独占方式通过 Exchange Online 提供电子邮件服务。
  
有关详细信息，请参阅[Configure hybrid for Business 的 Skype 的多林环境](../../SfbServer/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/configure-a-multi-forest-environment-for-hybrid.md)。
  
## <a name="domain-name-system-dns"></a>域名系统 (DNS)
<a name="DNS"> </a>

Skype 的业务服务器 2019年需要 DNS，原因如下：
  
- DNS 使 Skype 的业务服务器 2019 发现内部服务器或池，允许进行服务器到服务器通信。
    
- DNS 允许客户端可以发现的前端池或 Standard Edition server 所使用的 SIP 事务的计算机。
    
- 它会将会议的简单 URL 与托管这些会议的服务器相关联。
    
- DNS 允许外部用户和客户端计算机连接到边缘服务器，或 HTTP 反向代理，即时消息 (IM) 或会议。
    
- 这会让统一的通信 (UC) 未登录的设备发现的前端池或 Standard Edition 服务器正在运行设备更新 web 服务以获取更新和发送日志。
    
- 使用 DNS 使移动客户端可以自动发现 Web 服务资源，而无需用户在设备设置中手动输入 URL。
    
- 它具有用在 DNS 负载平衡。
    
请务必注意业务服务器 2019年的 Skype 不支持国际化的域名 (Idn)。
  
极其重要记住，在 DNS 中的任何名称是与正在使用业务服务器 2019 Skype 任何服务器上配置的计算机名称相同。 具体而言，我们不能在环境中，有任何短名称，并且必须具有的拓扑生成器的 Fqdn。
  
这看起来像会逻辑的任何计算机已加入域，但是如果您有未加入您的域的边缘服务器，它可能具有默认值为短的名称，与任何域后缀。 请确保这不是这样，在 DNS 中或者对边缘服务器或任何 Skype 业务服务器 2019年服务器或池，该专家。
  
肯定不使用 Unicode 字符或下划线。 外部 DNS 和公共证书颁发机构支持标准的字符 （A 到 Z、 a-z、 0-9 和连字符） (需要向证书中的 SN 分配 Fqdn 非常重要记住)，因此您将空闲自己大量问题如果的名称这一点自开始。
  
若要进一步了解网络 DNS 要求，请查看我们的规划文档的[Networking](../../SfbServer/plan-your-deployment/network-requirements/network-requirements.md)部分。
  
## <a name="certificates"></a>证书
<a name="Certs"> </a>

在部署之前，您要做的一件最重要的事情就是确保证书有条不紊。 Skype 的业务服务器 2019年需要公钥基础结构 (PKI) 的传输层安全性 (TLS) 和相互传输层安全性 (MTLS) 连接。 一般情况下，安全地标准化方式进行通信，Skype 业务服务器使用证书颁发机构 (Ca) 颁发的证书。
  
以下是一些业务服务器 2019年的 Skype 使用证书的事情：
  
- 客户端与服务器之间的 TLS 连接
    
- 服务器之间的 MTLS 连接
    
- 使用自动发现伙伴 DNS 的联盟
    
- 远程用户访问即时消息 (IM)
    
- 外部用户访问音频/视频 (AV) 会话、应用程序共享和会议
    
- 谈话对方 web 应用程序和 Outlook Web Access (OWA)
    
因此，证书规划是必不可少的。 现在，让我们看一下一些您需要申请证书时需要注意的事项列表：
  
- 所有服务器证书都必须支持服务器授权（服务器 EKU）。
    
- 所有服务器证书都必须包含一个 CRL 分发点 (CDP)。
    
- 所有证书必须使用操作系统支持的签名算法进行签名。 Skype 的业务服务器 2019年支持 sha-1 和摘要式 160、SHA-2 套件大小 （224、 256、 384 和 512 位）、 和满足或超出的操作系统要求。
    
- 为业务服务器 2019年运行 Skype 的内部服务器支持自动注册。
    
- 自动注册不是支持 Skype 业务 Server 2019 边缘服务器。
    
> [!NOTE]
> 不支持使用 RSASSA-PSS 签名算法，否则可能导致登录错误、呼叫转接问题及其他问题。 
  
- 加密密钥长度为 1024、2048 和 4096。建议使用密钥长度 2048 和更大值。
    
- 默认的摘要式或哈希签名算法是 RSA。还支持 ECDH_P256、ECDH_P384 和 ECDH_P521 算法。
    
很多要考虑的事项，并且没有各种舒适程度使用从 CA 请求证书。 我们将为您提供一些进一步的指导下进行规划尽可能轻松。
  
### <a name="certificates-for-your-internal-servers"></a>内部服务器的证书

所需证书的内部服务器，大多数和很可能将从内部 CA （即位于您的域 CA） 获取它们。 如果需要，您可以从外部 CA （位于 Internet 上的一） 请求这些证书。 如果您想知道哪些公共 CA 应转到，您可以将其签出[统一通信证书伙伴](https://support.microsoft.com/kb/929395/en-us)列表中。
  
您还将与其他应用程序和服务器，例如 Microsoft Exchange Server 通信的业务服务器 2019 Skype 时需要证书。 这将很显然，需要将这些其他应用程序和服务器可以支持的方法中使用的证书。 Skype 业务服务器 2019年和其他 Microsoft 产品支持的服务器到服务器身份验证和授权 Open Authorization (OAuth) 协议。 如果您感兴趣这，我们将其他规划文章 OAuth 和 Skype 的业务服务器 2019年。
  
Skype 的业务服务器 2019年还包括对支持 （而无需） 使用 160、SHA 256 加密哈希函数签名的证书。 要支持使用 SHA-256 进行外部访问，外部证书必须由公共 CA 使用 SHA-256 颁发。
  
简单起见，我们已将 Standard Edition server、 前端池和其他角色的证书要求投入下表中，使用虚构的 contoso.com 所使用的 （您可能要使用的其他内容的示例您的环境）。 这些均为标准 Web 服务器证书，使用不可导出的私钥。 此外还应注意：
  
- 使用证书向导请求证书时会自动配置服务器增强型密钥使用 (EKU)。
    
- 每个证书友好名称在计算机存储中均必须是唯一的。
    
- 按照下面的示例名称，如果您在您的 DNS 配置 sipinternal.contoso.com 或 sipexternal.contoso.com 他们需要添加到证书的使用者替代名称 (SAN)。
    
对于 Standard Edition 服务器的证书：
  
|**证书**|**使用者名称/common 名称**|**使用者替代名称**|**示例**|**注释**|
|:-----|:-----|:-----|:-----|:-----|
|默认值  <br/> |池的 FQDN  <br/> |池的 FQDN 和服务器的 FQDN  <br/> 如果具有多个 SIP 域并已启用自动客户端配置，则证书向导会检测并添加所有受支持的 SIP 域 FQDN。  <br/> 如果此池是客户端的自动登录服务器，而且组策略要求执行严格的域名系统 (DNS) 匹配，那么还需要 sip.sipdomain 条目（对应于您拥有的每个 SIP 域）。  <br/> |SN=se01.contoso.com; SAN=se01.contoso.com  <br/> 如果此池是客户端的自动登录服务器，而且组策略要求执行严格的 DNS 匹配，则还需要 SAN=sip.contoso.com; SAN=sip.fabrikam.com。  <br/> |Standard Edition 服务器上的服务器 FQDN 与池 FQDN 相同。  <br/> 证书向导会检测您在安装过程中所指定的任何 SIP 域，然后自动将它们添加到使用者可选名称中。  <br/> 也可将此证书用于服务器到服务器身份验证。  <br/> |
|Web 内部  <br/> |服务器的 FQDN  <br/> |以下各项：  <br/> • 内部 web FQDN （这是服务器的 FQDN 相同）  <br/> 和  <br/> • 会议简单 Url  <br/> • 电话拨入式简单 URL  <br/> • 管理简单 URL  <br/> 或者  <br/> • 简单 Url 的通配符条目  <br/> |SN=se01.contoso.com; SAN=se01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> 使用通配符证书：  <br/> SN=se01.contoso.com;SAN=se01.contoso.com;SAN =\*。 contoso.com  <br/> |无法覆盖内部 web FQDN 在拓扑生成器。  <br/> 如果您有多个会议简单 Url，则必须包含所有这些 as San。  <br/> 简单 URL 条目支持通配符条目。  <br/> |
|Web 外部  <br/> |服务器的 FQDN  <br/> |以下各项：  <br/> • 外部 web FQDN  <br/> 和  <br/> • 电话拨入式简单 URL  <br/> 每个 SIP 域的 • 会议简单 Url  <br/> 或者  <br/> • 简单 Url 的通配符条目  <br/> |SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> 使用通配符证书：  <br/> SN=se01.contoso.com;SAN=webcon01.contoso.com;SAN =\*。 contoso.com  <br/> |如果您有多个会议简单 Url，您必须包括所有它们作为使用者替代名称。  <br/> 简单 URL 条目支持通配符条目。  <br/> |
   
在前端池前端服务器的证书：
  
|**证书**|**使用者名称/common 名称**|**使用者替代名称**|**示例**|**注释**|
|:-----|:-----|:-----|:-----|:-----|
|默认值  <br/> |池的 FQDN  <br/> |池的 FQDN 和服务器的 FQDN  <br/> 如果具有多个 SIP 域并已启用自动客户端配置，则证书向导会检测并添加所有受支持的 SIP 域 FQDN。  <br/> 如果此池是客户端的自动登录服务器，而且组策略要求执行严格的域名系统 (DNS) 匹配，那么还需要 sip.sipdomain 条目（对应于您拥有的每个 SIP 域）。  <br/> |SN=eepool.contoso.com; SAN=eepool.contoso.com; SAN=ee01.contoso.com   <br/> 如果此池是客户端的自动登录服务器，而且组策略要求执行严格的 DNS 匹配，则还需要 SAN=sip.contoso.com; SAN=sip.fabrikam.com。  <br/> |证书向导会检测您在安装过程中所指定的任何 SIP 域，然后自动将它们添加到使用者可选名称中。  <br/> 也可将此证书用于服务器到服务器身份验证。  <br/> |
|Web 内部  <br/> |池的 FQDN  <br/> |以下各项：  <br/> • 内部 web FQDN （这不是服务器的 FQDN 相同）  <br/> • 服务器 FQDN  <br/> • Skype 业务池 FQDN  <br/> 和  <br/> • 会议简单 Url  <br/> • 电话拨入式简单 URL  <br/> • 管理简单 URL  <br/> 或者  <br/> • 简单 Url 的通配符条目  <br/> |SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> 使用通配符证书：  <br/> SN=ee01.contoso.com;SAN=ee01.contoso.com;SAN =\*。 contoso.com  <br/> |如果您有多个会议简单 Url，您必须包括所有它们作为使用者替代名称。  <br/> 简单 URL 条目支持通配符条目。  <br/> |
|Web 外部  <br/> |池的 FQDN  <br/> |以下各项：  <br/> • 外部 web FQDN  <br/> 和  <br/> • 电话拨入式简单 URL  <br/> • 管理简单 URL  <br/> 或者  <br/> • 简单 Url 的通配符条目  <br/> |SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> 使用通配符证书：  <br/> SN=ee01.contoso.com;SAN=webcon01.contoso.com;SAN =\*。 contoso.com  <br/> |如果您有多个会议简单 Url，您必须包括所有它们作为使用者替代名称。  <br/> 简单 URL 条目支持通配符条目。  <br/> |
   
控制器的证书：
  
|**证书**|**使用者名称/common 名称**|**使用者替代名称**|**示例**|
|:-----|:-----|:-----|:-----|
|默认值  <br/> |控制器池  <br/> |控制器的 FQDN，控制器池的 FQDN。  <br/> 如果此池是客户端和严格的自动登录服务器的 DNS 匹配所需在组策略中，您还需条目 sip.sipdomain （每个 SIP 域必须）。  <br/> |pool.contoso.com; SAN=dir01.contoso.com   <br/> 如果此控制器池是客户端的自动登录服务器，并且严格的 DNS 匹配所需在组策略中，您还需要 SAN=sip.contoso.com;San = sip.fabrikam.com  <br/> |
|Web 内部  <br/> |服务器的 FQDN  <br/> |以下各项：  <br/> • 内部 web FQDN （这是服务器的 FQDN 相同）  <br/> • 服务器 FQDN  <br/> • Skype 业务池 FQDN  <br/> 和  <br/> • 会议简单 Url  <br/> • 电话拨入式简单 URL  <br/> • 管理简单 URL  <br/> 或者  <br/> • 简单 Url 的通配符条目  <br/> |SN=dir01.contoso.com; SAN=dir01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> 使用通配符证书：  <br/> SN=dir01.contoso.com;SAN=dir01.contoso.com SAN =\*。 contoso.com  <br/> |
|Web 外部  <br/> |服务器的 FQDN  <br/> |以下各项：  <br/> • 外部 web FQDN  <br/> 和  <br/> 每个 SIP 域的 • 会议简单 Url  <br/> • 电话拨入式简单 URL  <br/> 或者  <br/> • 简单 Url 的通配符条目  <br/> |控制器外部 web FQDN 必须不同于前端池或前端服务器。  <br/> SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> 使用通配符证书：  <br/> SN=dir01.contoso.com;SAN=directorwebcon01.contoso.com SAN =\*。 contoso.com  <br/> |
   
独立的中介服务器的证书：
  
|**证书**|**使用者名称/common 名称**|**使用者替代名称**|**示例**|
|:-----|:-----|:-----|:-----|
|默认值  <br/> |池的 FQDN  <br/> |池的 FQDN  <br/> 池成员服务器的 FQDN  <br/> |SN=medsvr-pool.contoso.net; SAN=medsvr-pool.contoso.net; SAN=medsvr01.contoso.net  <br/> |
   
Survivable Branch Appliance (具体而言，Survivable Branch Appliance 2015 的 Skype 业务服务器 2019年) 的证书：
  
|**证书**|**使用者名称/common 名称**|**使用者替代名称**|**示例**|
|:-----|:-----|:-----|:-----|
|默认值  <br/> |设备的 FQDN  <br/> |SIP。\<sipdomain\> （需要每个 SIP 域只能有一个条目）  <br/> |SN=sba01.contoso.net; SAN=sip.contoso.com; SAN=sip.fabrikam.com  <br/> |
   
### <a name="certificates-for-external-user-access-edge"></a>外部用户访问（边缘）的证书

Skype 的业务服务器 2019年支持**单个公共证书**的使用访问、 web 会议边缘外部接口，以及 A / V 身份验证服务，它提供通过边缘服务器。 边缘内部接口通常将使用您的内部 CA 颁发的专用证书，但如果您希望使用，可用于公共证书这同样，如果它来自受信任的 CA。
  
反向代理 (RP) 也会使用公共证书，并会使用 HTTP（更精确地说，是 HTTP 上的 TLS）对 RP 与客户端以及 RP 与内部服务器之间的通信进行加密。
  
### <a name="certificates-for-mobility"></a>移动证书

如果您正在部署移动功能，并且您的移动客户端支持自动发现，您将需要包括在您的证书才能支持从移动客户端的安全连接某些其他使用者替代名称条目。
  
您将需要在以下证书上的自动发现 SAN 名称：
  
- 控制器池
    
- 前端池
    
- 反向代理
    
下表列出了细节。
  
这是其中一些预先规划很好，有时您已经部署了 Skype 的业务服务器 2019年而不打算部署的移动功能，但，提出更高版本时您的环境中已经有证书。 通过内部 CA 重新颁发证书通常比较简单，但如果使用的是公共 CA 颁发的公共证书，则可能代价高昂。
  
如果这是您查找在并且您有大量的 SIP 域 （这会使添加成本较高的 SAN），您可以配置反向代理 HTTP 用于初始自动发现服务请求，而不是使用 HTTPS （这是默认值配置）。 [规划移动性的](../../SfbServer/plan-your-deployment/mobility.md)文章提供了对此的详细信息。
  
控制器池和前端池证书要求：
  
|**说明**|**SAN 条目**|
|:-----|:-----|
|内部自动发现服务 URL  <br/> |SAN = lyncdiscoverinternal。\<sipdomain\>  <br/> |
|外部自动发现服务 URL  <br/> |SAN = lyncdiscover。\<sipdomain\>  <br/> |
   
此外，您可以使用 SAN =\*。\<sipdomain\>
  
反向代理（公共 CA）证书要求：
  
|**说明**|**SAN 条目**|
|:-----|:-----|
|外部自动发现服务 URL  <br/> |SAN = lyncdiscover。\<sipdomain\>  <br/> |
   
此 SAN 需要分配给已分配到反向代理上的 SSL 侦听器的证书。
  
> [!NOTE]
> 反向代理侦听器将具有 San 您外部 Web 服务 URL。 如果您已经部署了控制器 （这是可选的），会 SAN=skypewebextpool01.contoso.com 和 dirwebexternal.contoso.com，一些示例。 
  
## <a name="file-share"></a>文件共享
<a name="Fileshare"> </a>

Skype 的业务服务器 2019年可以使用相同的文件共享进行所有文件存储区。 但您需要注意以下事项：
  
- 文件共享需要置于直接附加存储 (DAS) 或存储区域网络 (SAN) 上，其中包括分布式文件系统 (DFS) 以及文件存储的独立磁盘冗余阵列 (RAID)。 如需了解 Windows Server 2012 的 DFS 的更多信息，请访问[此 DFS 页面](https://technet.microsoft.com/en-us/library/jj127250.aspx)。
    
- 建议为文件共享使用共享群集。 如果您正在使用它，您应该组成群集 Windows Server 2012 或 Windows Server 2012 R2。 为什么最新的 Windows？ 较旧的版本可能不具备启用所有功能的正确权限。 你可以使用群集管理员权限创建文件共享，这篇[创建群集](https://support.microsoft.com/en-us/help/224967) KB 文章将帮助你了解相关详细信息。
    
> [!CAUTION]
> 您应知道，不支持将网络附加存储 (NAS) 用作文件共享，因此，请使用上述其中一个选项。 
  








