---
title: 使用 SCOM 管理包管理 Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/13/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ca03f9ab-a227-4903-85a8-427df6a0a5bb
description: 摘要： 了解如何配置业务服务器 2015年基础结构为您 Skype 使用系统中心操作管理器。
ms.openlocfilehash: 998413a20f775f48cedfc501650d7562850c9965
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="manage-skype-for-business-server-2015-using-scom-management-pack"></a>使用 SCOM 管理包管理 Skype for Business Server 2015
 
**摘要：**了解如何配置业务服务器 2015年基础结构为您 Skype 使用系统中心操作管理器。
  
在理想世界中，永远不会为业务服务器 2015年遇到 Skype 的问题。 但是，Skype 业务服务器可能会受到的外部因素 — — 例如，网络崩溃和硬件故障。 通过使用 Skype 业务服务器 2015年管理包，您能够识别并主动解决的潜在问题。 以这种方式，Skype 业务服务器 2015年管理包的扩展系统中心操作管理器的功能。
  
此信息读者是基于监控包版本 9319.0 上的 Skype 业务服务器 2015年通信软件。
  
## <a name="configuration-overview"></a>配置概述

 若要配置业务服务器 2015年基础结构为您 Skype 与系统中心操作管理器工作，必须做三件事：
  
标识和[配置的主管理服务器](configure-the-primary.md)。 若要执行此操作，必须安装系统中心操作管理器 2012 SP1 或 R2。 
  
 标识和[配置的业务服务器计算机进行监视，Skype](configure-computers-to-monitor.md)。 若要使用系统中心操作管理器监视 Skype 业务服务器计算机，必须安装系统中心操作管理器代理程序文件，并配置每个服务器使其作为代理。 
  
 标识和[安装和配置观察者节点](watcher-nodes.md)。 观察者节点是定期业务服务器综合事务运行 Skype 的计算机 — — 验证业务服务器组件，例如，能够登录到系统或能够即时交换该注册表项 Skype 的 Windows PowerShell cmdlet消息，正如预期的那样。 
  
## <a name="system-center-operations-manager-root-management-server-and-agent-support"></a>系统中心操作管理器根管理服务器和代理支持

管理包可用于系统中心操作管理器 2007 R2 （64 位） （支持出于迁移的目的） 或系统中心操作管理器 2012 SP1 &amp; R2 （64 位）。 下表显示了支持的配置管理包的 Skype 业务服务器 2015年: 
  
|**配置**|**支持？**|
|:-----|:-----|
|Windows Server 2008 R2 操作系统  <br/> Windows Server 2012 R2 操作系统  <br/> |是。 同时在 Skype 业务服务器 2015年服务器和综合事务观察者节点。  <br/> |
|群集服务器  <br/> |不支持。  <br/> |
|无代理监视  <br/> |不支持。  <br/> |
|虚拟环境  <br/> |是。  <br/> |
|加入域的服务器角色  <br/> |所有内部 Skype 业务服务器 2015年服务器角色必须加入域。  <br/> |
|独立服务器角色  <br/> |Skype 的业务服务器 2015年边缘服务器不是需要加入域。  <br/> |
|拓扑限制  <br/> |必须从同一个 Operations Manager 管理组中监视部署环境中的所有服务器角色。  <br/> |
|综合事务观察程序节点  <br/> |支持通过综合事务监视观察程序节点监视方案可用性（需要其他配置）。观察程序节点不需要加入域。  <br/> |
   
下表显示了综合事务观察程序节点的容量和操作系统要求：
  
|**硬件组件**|**最低要求**|
|:-----|:-----|
|CPU  <br/> |以下两种之一：  <br/> 64 位处理器、四核、2.33 GHz 或更快  <br/> 64 位 2 路处理器、双核、2.33 GHz 或更快  <br/> |
|内存  <br/> |8 GB  <br/> |
|操作系统  <br/> |Windows Server 2008 R2  <br/> Windows Server 2012 R2  <br/> |
|网络  <br/> |1 个网络适配器，速度 1 Gbps  <br/> |
   
## <a name="prerequisites"></a>先决条件

为了运行综合事务观察程序节点，必须先安装以下几项：
  
- 系统中心操作管理器代理 
    
-  Microsoft .NET Framework 4.5
    
- Skype 业务服务器核心安装文件 (OcsCore.msi) 和统一通信托管 API (UCMA) （版本必须匹配 Skype 业务服务器 WatcherNode.msi 版）
    
## <a name="files-in-this-monitoring-pack"></a>此监视包中的文件

Skype 的业务服务器 2015年监控包包括以下文件：
  
- Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp
    
- Microsoft.LS.2015.Monitoring.ComponentAndUser.mp
    
- WatcherNode.msi
    
## <a name="whats-new"></a>新增功能

以下功能是新手 Skype 业务服务器 2015年管理包。
  
- **自动发现的客户端登录**客户端应用程序登录 Skype 的业务服务器 2015年通常会自动发现要登录到的服务器。 综合事务现在支持验证正确配置自动发现。
    
- **自定义综合事务运行的时间间隔**为了简化设置过程的观察程序节点，综合事务可以共享用户帐户。 这将测试运行的测试被序列化，以避免冲突的频率降低。 默认情况下，以确保所有测试每 15 分钟运行一次的综合事务有时间来运行。 现在，管理员选择使用多个用户或每个用户较少的测试可能会降低运行的间隔，以及。
    
- **视频互操作服务综合事务**正在迁移到 Skype 的业务服务器 2015年从其他供应商解决方案通常的客户希望继续使用这些其他供应商提供的远程视频会议设备 (VTCs)。 互操作的视频服务器是为使客户能够继续在他们的会议室中使用 Cisco VTCs，通过视频的 SIP 中继连接至 Cisco CUCM 的业务服务器 2015年服务器角色新 Skype。 此功能还增加了综合事务以确保视频互操作服务器处于活动状态，可以通过视频的 SIP 中继处理传入的连接。
    
- **应用程序共享会议综合事务** 现在支持应用程序共享会议的端到端方案验证。
    
## <a name="monitoring-scenarios"></a>监视方案

为业务服务器 2015年管理包 Skype 利用各种功能可帮助您检测和诊断问题。 这些功能可实时深入查看 Skype 业务服务器 2015年环境的运行状况。
  
|**监视方案**|**说明**|
|:-----|:-----|
|综合事务  <br/> | Windows PowerShell cmdlet 以测试并确保高可用性的方案，例如标志中存在、 IM 和用户的会议。 <br/> 综合事务可从任何地理位置运行，包括企业内部、企业外部和分支机构。  <br/> 当综合事务失败时，系统会创建 HTML 日志来帮助确定失败的确切性质。这包括了解哪项操作失败、每项操作的延迟、用于运行测试的命令行，以及发生的具体错误。  <br/> |
|呼叫可靠性警报  <br/> |为 2015年的业务服务器的服务器编写通过 Skype 呼叫详细记录 (Cdr) 反映用户是否能够连接到调用或调用终止的原因。 呼叫可靠性警报查询 CDR 数据库来生成警报，这些警报指出大量用户什么时候遇到对等呼叫或基本会议功能的连接问题。  <br/> 涵盖的方案包括音频呼叫、对等即时消息 (IM) 和其他会议功能。  <br/> |
|媒体质量警报  <br/> |看一看由 Skype 发布业务服务器 2015年结尾的每个调用的客户端体验质量 (QoE) 报告的数据库查询。 这些查询会产生警报，这些警报可准确指出在什么方案中，用户最有可能在呼叫和会议期间遇到受损的媒体质量。 数据在数据包延迟和丢失等关键指标的基础上建立，这些指标直接影响用户体验的质量。  <br/> |
|组件运行状况警报  <br/> |个别服务器组件会通过事件日志和性能计数器发出警报，以指出可能会严重影响用户方案的故障情况。这些警报指出各种情况，如服务未运行、高故障率、高消息延迟或连接问题。  <br/> |
|依赖项运行状况监视  <br/> |Skype 业务服务器的可能会有各种各样的外部原因而失败。 管理包监视并收集可能表明存在严重问题的关键外部依赖项的数据。 这些依赖项包括 Internet Information Services (IIS) 的可用性和 CPU 的使用 Skype 业务服务器的服务器。  <br/> |
   
### <a name="alert-prioritization"></a>警报优先级

警报分成以下类别： 
  
 **高优先级的通知：**这些警报指示的状况，需要立即采取操作，导致大量用户的服务中断。 通过综合事务并脱机服务 （如 Skype 的业务服务器音频/视频会议) 检测到中断限定为高优先级的通知。 相比之下，一台计算机上的组件故障不是一条高优先级的警报。 业务服务器 2015年的 Skype 拥有内置的高可用性特征，针对这些情况，例如，多个前端服务器负载平衡器的后面。
  
 **中等优先级的通知：**这些警报指示的状况，影响用户的子集或指示呼叫质量中的问题 — — 例如，组件失败、 呼叫建立的延迟或调用中的音频质量降低。 此类别中的警报的状态 （即通知更改的特性基于网络连接的状态。）例如，如果呼叫建立时间指示延迟，但随后返回到正常阈值，此中等优先级警报会自动解决在系统中心操作管理器，管理员不需要采取的措施。 在同一工作日，通常由管理员不能自动解决的警报进行寻址。
  
 **其他警报：**产生这些警报的组件可能影响特定用户或部分用户。例如，典型的警报可能是，通讯簿服务无法解析用户的 Active Directory® 域服务 (AD DS) 条目：testuser@contoso.com。管理员只要有时间就可以处理这些警报。
  
### <a name="synthetic-transactions"></a>综合事务

Skype 业务服务器 2015年管理包提供警报通过综合事务增加覆盖范围。 综合事务是集成到测试端到端用户方案的操作管理器管理包的 Windows PowerShell cmdlet。 当您指定一个服务器以执行综合事务时，此管理包定期触发这些 cmdlet。 综合事务产生的故障生成一个有状态的警报。 下面是支持综合的业务服务器 2015 Skype 事务：
  
**注册、 在线状态以及联系人支持综合事务**

||||
|:-----|:-----|:-----|
|1  <br/> |注册（用户登录）  <br/> |Lync Server 2010 中可用内外  <br/> |
|2  <br/> |通讯簿服务（文件下载）  <br/> |Lync Server 2010 中可用内外  <br/> |
|3  <br/> |通讯簿 Web 查询  <br/> |Lync Server 2010 中可用内外  <br/> |
|4  <br/> |状态  <br/> |Lync Server 2010 中可用内外  <br/> |
|5  <br/> |统一联系人存储  <br/> |使用 Lync Server 2013 内外  <br/> |
   
**支持的对等服务综合事务**

||||
|:-----|:-----|:-----|
|6  <br/> |对等即时消息  <br/> |Lync Server 2010 中，超出可用  <br/> |
|7  <br/> |对等音频视频  <br/> |Lync Server 2010 中，超出可用  <br/> |
|8  <br/> |MCX 对等即时消息（移动）  <br/> |在 2011 年 9 月发行的 Lync Server 2010 及以后  <br/> |
   
**支持的会议和持久聊天综合事务**

||||
|:-----|:-----|:-----|
|9  <br/> |音频视频会议  <br/> |Lync Server 2010 中，超出可用  <br/> |
|10  <br/> |数据会议  <br/> |在 Lync Server 2013 及以后可用  <br/> |
|11  <br/> |即时消息会议  <br/> |Lync Server 2010 中，超出可用  <br/> |
|12  <br/> | 持久聊天 <br/> |在 Lync Server 2013 及以后可用  <br/> |
|13  <br/> |加入启动器（排定的会议）  <br/> |在 Lync Server 2013 及以后可用  <br/> |
|14  <br/> |电话拨入式会议  <br/> |Skype 业务服务器 2015年中的新增功能  <br/> |
|15  <br/> |应用程序共享会议  <br/> |Skype 业务服务器 2015年中的新增功能  <br/> |
|16  <br/> |UCWA 会议（Web 会议加入）  <br/> |Skype 业务服务器 2015年中的新增功能  <br/> |
   
**支持的网络和合作伙伴依赖项综合事务**

||||
|:-----|:-----|:-----|
|17  <br/> |AV 边缘连接  <br/> |在 Lync Server 2013 及以后可用  <br/> |
|18  <br/> |AV 边缘连接 Exchange 统一消息连接（语音邮件）  <br/> |在 Lync Server 2013 及以后可用  <br/> |
|19  <br/> |PSTN 对等呼叫  <br/> |Lync Server 2010 中，超出可用  <br/> |
|20  <br/> |XMPP 即时消息（联合）  <br/> |在 Lync Server 2013 及以后可用  <br/> |
|21  <br/> |视频互操作服务器  <br/> |Skype 业务服务器 2015年中的新增功能  <br/> |
   
## <a name="how-health-rolls-up"></a>运行状况的累计方法

下表显示业务服务器的监控包的对象 Skype 的健康状态。
  
|**管理包对象**|**说明**|
|:-----|:-----|
|Skype 业务服务器部署  <br/> |表示部署 Skype 业务服务器 2015年的组织中。  <br/> |
|Skype 业务服务器站点  <br/> |表示部署了服务的不同地理位置。  <br/> |
|Skype 业务服务器池  <br/> |向用户提供即时消息和会议等通信服务的池（在站点内）。适用于前端池、边缘池和控制器池，即使给定池中只有单个计算机。  <br/> |
|Skype 业务服务器角色  <br/> |承载 Skype 业务服务器服务的服务器角色。  <br/> |
|Skype 业务服务器服务  <br/> |表示部署在特定计算机上的功能（例如，fp01.contoso.com 上的用户服务）。  <br/> |
|Skype 业务服务器组件  <br/> |服务的组件（如，通讯簿下载组件是 Web 服务的一部分）。  <br/> |
|Skype 的业务服务器池观察程序  <br/> |对一个池运行的综合事务的实例。  <br/> |
|Skype 的业务服务器注册器观察程序  <br/> |对一个注册器池运行的综合事务的实例。  <br/> |
|Skype 的业务用户服务池观察程序  <br/> |对一个用户服务池运行的综合事务的实例。  <br/> |
|Skype 的业务服务器语音池观察程序  <br/> |对一个语音池运行的综合事务的实例。  <br/> |
|Skype 的业务服务器端口观察程序  <br/> |对一个池运行的端口检查的实例。  <br/> |
|简单 URL 观察程序  <br/> |执行在部署中配置的简单 URL 的 HTTPS 探测。  <br/> |
   
![SCOM 汇总](../../media/de16195d-3aed-412e-9def-07a481d2ff0f.png)
  
Skype 业务服务器池可以包含多个单独 （具有的业务服务器角色、 业务服务器服务 Skype 和 Skype 业务服务器组件的多个 Skype) 业务服务器系统 Skype。 因此，单个服务器或组件故障是到企业服务器池，Skype 的整体健康状况不太重要，因为在同一池中的其他服务器可以向客户端提供了应用程序服务。 运行状况将汇总百分比级别到 Skype 业务服务器池。 
  
Skype 的业务服务器池观察程序执行业务服务器池对 Skype 的综合事务。 一个或多个综合事务（一种称为连续轮询间隔的过程）连续失败将把严重运行状况累计到池级别（任何综合事务最差的结果），如下图所示。 
  
![SCOM 汇总连续轮询](../../media/655de542-cca7-4eda-8052-9a7703ecd0e9.png)
  
## <a name="best-practice-create-a-management-pack-for-customizations"></a>最佳做法：创建管理包进行自定义

默认情况下，Operations Manager 保存所有自定义项，如默认管理包的替代设置。作为最佳做法，应该为您要自定义的每个封装管理包创建一个单独的管理包。 
  
在创建管理包来存储封装管理包的自定义设置时,我们建议相应地命名新管理包,如“Skype for Business Server 2015 自定义项”。 
  
创建新管理包来存储每个封装管理包的自定义项有利于将自定义项更容易地从测试环境导出到生产环境。这还使删除管理包变得更容易，因为您必须先删除所有依赖项才能删除管理包。如果所有管理包的自定义项都保存在默认管理包中，而您需要删除单个管理包，那么您必须删除默认管理包，这将同时删除其他管理包的自定义项。 
  
## <a name="links"></a>链接

以下链接提供了有关 System Center 2012 监视包常见任务的信息：
  
- [管理包的生命周期](https://technet.microsoft.com/en-us/library/hh212732.aspx)
    
- [如何导入管理包在运营经理 2012](https://technet.microsoft.com/en-us/library/hh212691.aspx)
    
- [如何重写规则或监视器](https://technet.microsoft.com/en-us/library/hh212869.aspx)
    
- [如何创建作为运营经理 2012年中的帐户运行](https://technet.microsoft.com/en-us/library/hh321655.aspx)
    
- [管理运行方式帐户和配置文件](https://technet.microsoft.com/en-us/library/hh212714.aspx)
    
- [如何导出操作管理器管理包](https://technet.microsoft.com/en-us/library/hh320149.aspx)
    
- [如何删除操作管理器管理包](https://technet.microsoft.com/en-us/library/hh230746.aspx)
    
以下链接提供了有关 System Center 2007 监视包常见任务的信息：
  
- [管理包的生命周期管理](https://go.microsoft.com/fwlink/p/?LinkId=211463)
    
- [如何导入管理包在操作管理器 2007](https://go.microsoft.com/fwlink/p/?LinkID=142351)
    
- [如何监视使用重写](https://go.microsoft.com/fwlink/p/?LinkID=117777)
    
- [如何创建一个运行操作管理器 2007年中的帐户](https://go.microsoft.com/fwlink/p/?LinkID=165410)
    
- [如何修改现有运行方式配置文件](https://go.microsoft.com/fwlink/p/?LinkID=165412)
    
- [如何导出管理包的自定义项](https://go.microsoft.com/fwlink/p/?LinkId=209940)
    
- [如何删除管理包](https://go.microsoft.com/fwlink/p/?LinkId=209941)
    
运营经理和监视包有关的问题，请参阅[系统中心操作管理器社区论坛](https://go.microsoft.com/fwlink/p/?LinkID=179635)。
  
有用资源是[系统中心操作管理器充分发挥其作用](https://opsmgrunleashed.wordpress.com/)的博客中，其中包含特定监视包的"例子"帖子。
  
有关 Operations Manager 的更多信息，请参阅下面的博客： 
  
- [操作管理器团队博客](https://blogs.technet.com/momteam/default.aspx)
    
- [Kevin Holman OpsMgr 博客](https://blogs.technet.com/kevinholman/default.aspx)
    
- [在 OpsMgr 的想法](https://thoughtsonopsmgr.blogspot.com/)
    
- [Raphael Burri 博客](https://rburri.wordpress.com/)
    
- [BWren 的管理空间](https://blogs.technet.com/brianwren/default.aspx)
    
- [Ops Mgr + +](https://blogs.msdn.com/boris_yanushpolsky/default.aspx)
    
> [!IMPORTANT]
> 非 Microsoft 网站上的所有信息和内容由这类网站的所有者或用户提供。对于这类网站上的信息，Microsoft 不坐任何明示、暗示或法定的保证。 
  
## <a name="see-also"></a>另请参阅

#### 

[Skype 业务 2015年服务器管理工具](../../management-tools/management-tools.md)

