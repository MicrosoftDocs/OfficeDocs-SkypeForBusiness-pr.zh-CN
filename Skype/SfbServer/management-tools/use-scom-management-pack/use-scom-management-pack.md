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
description: 摘要： 了解如何配置您 Skype 业务服务器 2015年基础结构，以使用 System Center Operations Manager。
ms.openlocfilehash: cb2eb053142bcbc4c24a61f6dbd7322a3772f4a6
ms.sourcegitcommit: a5b8b0a1e5ae5eb718e296ca6df6687368ee9174
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/05/2018
ms.locfileid: "19504787"
---
# <a name="manage-skype-for-business-server-2015-using-scom-management-pack"></a>使用 SCOM 管理包管理 Skype for Business Server 2015
 
**摘要：** 了解如何配置您 Skype 业务服务器 2015年基础结构，以使用 System Center Operations Manager。
  
在理想的情况，则会永远不会遇到 Skype 问题的业务服务器 2015年。 但是，Skype 业务服务器可能会受到外部因素 — 例如，网络崩溃和硬件故障。 通过使用 Skype 业务 Server 2015 管理包，您可以确定和主动解决潜在问题。 在这种方式，业务 Server 2015 管理包的 Skype 扩展 System Center Operations Manager 的功能。
  
此信息读者是基于监控包 9319.0 版本上的 Skype 业务服务器 2015年通信软件。
  
## <a name="configuration-overview"></a>配置概述

 若要配置您 Skype 业务服务器 2015年基础结构，以使用 System Center Operations Manager，您必须执行以下三个条件：
  
标识和[配置主管理服务器](configure-the-primary.md)。 若要执行此操作，您必须安装 System Center Operations Manager 2012 SP1 或 R2。 
  
 标识和[配置将受监控的企业服务器计算机的 Skype](configure-computers-to-monitor.md)。 若要使用 System Center Operations Manager 监视业务服务器计算机 Skype，必须安装 System Center Operations Manager 代理文件，并配置为充当代理的每台服务器。 
  
 确定和[安装和配置观察程序节点](watcher-nodes.md)。 观察程序节点是定期运行的业务服务器综合事务的 Skype 的计算机 — 验证业务服务器组件，如能够登录到系统或能够交换即时该密钥 Skype 的 Windows PowerShell cmdlet邮件正常运行。 
  
## <a name="system-center-operations-manager-root-management-server-and-agent-support"></a>System Center Operations Manager 根管理服务器和代理支持

管理包可用于 System Center Operations Manager 2007 R2 (64-bit) （仅用于迁移支持） 或 System Center Operations Manager 2012 SP1 &amp; R2 （64 位）。 下表显示了支持的配置管理包的 Skype 的业务服务器 2015年: 
  
|**配置**|**受支持？**|
|:-----|:-----|
|Windows Server 2008 R2 操作系统  <br/> Windows Server 2012 R2 操作系统  <br/> |是。 同时在 Skype 业务服务器 2015年服务器和综合事务观察程序节点上。  <br/> |
|群集服务器  <br/> |不支持。  <br/> |
|无代理监视  <br/> |不支持。  <br/> |
|虚拟环境  <br/> |是。  <br/> |
|加入域的服务器角色  <br/> |业务服务器 2015年服务器角色的所有内部 Skype 必须加入域的。  <br/> |
|独立服务器角色  <br/> |Skype 业务 Server 2015 边缘服务器不需要为加入域的。  <br/> |
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
  
- System Center Operations Manager 代理 
    
-  Microsoft .NET Framework 4.5
    
- 业务服务器核心安装文件 (OcsCore.msi) 和统一通信托管 API (UCMA) 的 Skype （版本必须匹配业务服务器 WatcherNode.msi 版本 Skype）
    
## <a name="files-in-this-monitoring-pack"></a>此监视包中的文件

监控的业务服务器 2015年的 Skype 包包含以下文件：
  
- Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp
    
- Microsoft.LS.2015.Monitoring.ComponentAndUser.mp
    
- WatcherNode.msi
    
## <a name="whats-new"></a>新增功能

以下是新增功能对业务 Server 2015 管理包的 Skype。
  
- **客户端登录的自动发现**客户端应用程序登录到 Skype 的业务服务器 2015年通常会自动发现要登录到的服务器。 综合事务现在支持验证是否正确配置的自动发现。
    
- **运行时间间隔的自定义综合事务**若要简化观察程序节点的过程设置，综合事务可以共享的用户帐户。 这将降低测试测试序列化为了避免冲突的运行频率的频率。 默认情况下，以确保所有测试每 15 分钟运行一次的综合事务具有运行时间。 管理员选择使用更多用户或较少的测试每个用户现在可以减少运行的间隔，以及。
    
- **视频互操作服务综合事务**客户的迁移到 Skype for Business Server 2015 从其他供应商解决方案通常希望继续使用这些其他供应商的远程视频会议设备 (VTCs)。 视频互操作服务器是新的业务服务器 2015年服务器角色，使客户能够继续通过视频的 SIP 中继连接到 Cisco CUCM 及其会议室中使用 Cisco VTCs Skype。 此功能还添加综合事务，以帮助验证视频互操作服务器处于活动状态，可以通过视频的 SIP 中继处理传入连接。
    
- **应用程序共享会议综合事务** 现在支持应用程序共享会议的端到端方案验证。
    
## <a name="monitoring-scenarios"></a>监视方案

业务 Server 2015 管理包 Skype 利用了各种功能可帮助您检测和诊断问题。 这些功能会提供实时查看 Skype 业务服务器 2015年环境的运行状况。
  
|**监视方案**|**说明**|
|:-----|:-----|
|综合事务  <br/> | 测试和帮助确保方案如登录的高可用性的状态、 IM 和会议的用户的 Windows PowerShell cmdlet。 <br/> 综合事务可从任何地理位置运行，包括企业内部、企业外部和分支机构。  <br/> 当综合事务失败时，系统会创建 HTML 日志来帮助确定失败的确切性质。这包括了解哪项操作失败、每项操作的延迟、用于运行测试的命令行，以及发生的具体错误。  <br/> |
|呼叫可靠性警报  <br/> |呼叫详细记录 (Cdr) 编写的业务 Server 2015 服务器通过 Skype 反映用户是否能够连接到呼叫或终止呼叫的原因。 呼叫可靠性警报查询 CDR 数据库来生成警报，这些警报指出大量用户什么时候遇到对等呼叫或基本会议功能的连接问题。  <br/> 涵盖的方案包括音频呼叫、对等即时消息 (IM) 和其他会议功能。  <br/> |
|媒体质量警报  <br/> |查看发布的 Skype 业务服务器 2015年末尾的每个呼叫的客户端的用户体验质量 (QoE) 报告的数据库查询。 这些查询会产生警报，这些警报可准确指出在什么方案中，用户最有可能在呼叫和会议期间遇到受损的媒体质量。 数据在数据包延迟和丢失等关键指标的基础上建立，这些指标直接影响用户体验的质量。  <br/> |
|组件运行状况警报  <br/> |个别服务器组件会通过事件日志和性能计数器发出警报，以指出可能会严重影响用户方案的故障情况。这些警报指出各种情况，如服务未运行、高故障率、高消息延迟或连接问题。  <br/> |
|依赖项运行状况监视  <br/> |Skype 业务服务器的外部原因有多种失败。 管理包监视并收集可能表明存在严重问题的关键外部依赖项的数据。 这些依赖关系包括 Internet Information Services (IIS) 可用性，以及用于对 Skype 业务服务器的服务器的 CPU。  <br/> |
   
### <a name="alert-prioritization"></a>警报优先级

警报分成以下类别： 
  
 **高优先级的通知：** 这些通知指示导致大用户组的服务中断且需要立即操作的条件。 检测到的综合事务和 （如业务 Server 音频/视频会议的 Skype) 的脱机服务中断合格高优先级的通知。 相比之下，一台计算机上的组件故障不是高优先级警报。 Skype 的业务服务器 2015年具有内置的高可用性功能，这些情况 — 例如，多个前端服务器负载平衡器后面。
  
 **中等优先级的通知：** 这些通知指示影响的用户的子集或指示中呼叫质量问题的条件 — 例如，组件失败、 呼叫建立延迟或较低的音频质量，呼叫中。 此类别中的通知有状态 （也就是说，警报的更改的特性基于状态的网络连接。）例如，如果呼叫建立时间指示延迟，但随后返回到普通阈值，在 System Center Operations Manager 中自动解析为此中等优先级警报和管理员不需要执行操作。 在同一个工作日，通常按管理员不能为自动解析的警报进行寻址。
  
 **其他警报：** 产生这些警报的组件可能影响特定用户或部分用户。例如，典型的警报可能是，通讯簿服务无法解析用户的 Active Directory® 域服务 (AD DS) 条目：testuser@contoso.com。管理员只要有时间就可以处理这些警报。
  
### <a name="synthetic-transactions"></a>综合事务

业务 Server 2015 管理包的 Skype 提供增加的范围通过综合事务的通知。 综合事务是集成测试的端到端用户方案的 Operations Manager 管理包的 Windows PowerShell cmdlet。 当指定服务器以执行综合事务时，这些 cmdlet 管理包定期触发。 生成综合事务的故障生成状态通知。 下面是受支持的 Skype 的业务服务器 2015年的综合事务：
  
**支持注册、 状态和联系人综合事务**

||||
|:-----|:-----|:-----|
|1  <br/> |注册（用户登录）  <br/> |可用的 Lync Server 2010 和场外  <br/> |
|2  <br/> |通讯簿服务（文件下载）  <br/> |可用的 Lync Server 2010 和场外  <br/> |
|3  <br/> |通讯簿 Web 查询  <br/> |可用的 Lync Server 2010 和场外  <br/> |
|4  <br/> |状态  <br/> |可用的 Lync Server 2010 和场外  <br/> |
|5  <br/> |统一联系人存储  <br/> |可用的 Lync Server 2013 和场外  <br/> |
   
**支持的对等服务综合事务**

||||
|:-----|:-----|:-----|
|6  <br/> |对等即时消息  <br/> |Lync Server 2010 中及其他认证实战可用  <br/> |
|7  <br/> |对等音频视频  <br/> |Lync Server 2010 中及其他认证实战可用  <br/> |
|8  <br/> |MCX 对等即时消息（移动）  <br/> |2011 年 9 月版本的 Lync Server 2010 及其他认证实战中提供  <br/> |
   
**支持的会议和持久聊天综合事务**

||||
|:-----|:-----|:-----|
|9  <br/> |音频视频会议  <br/> |Lync Server 2010 中及其他认证实战可用  <br/> |
|10  <br/> |数据会议  <br/> |Lync Server 2013 中及其他认证实战可用  <br/> |
|11  <br/> |即时消息会议  <br/> |Lync Server 2010 中及其他认证实战可用  <br/> |
|12  <br/> | 持久聊天 <br/> |Lync Server 2013 中及其他认证实战可用  <br/> |
|13  <br/> |加入启动器（排定的会议）  <br/> |Lync Server 2013 中及其他认证实战可用  <br/> |
|14  <br/> |电话拨入式会议  <br/> |Skype 业务服务器 2015年中的新增功能  <br/> |
|15  <br/> |应用程序共享会议  <br/> |Skype 业务服务器 2015年中的新增功能  <br/> |
|16  <br/> |UCWA 会议（Web 会议加入）  <br/> |Skype 业务服务器 2015年中的新增功能  <br/> |
   
**支持的网络和合作伙伴依赖项综合事务**

||||
|:-----|:-----|:-----|
|17  <br/> |AV 边缘连接  <br/> |Lync Server 2013 中及其他认证实战可用  <br/> |
|18  <br/> |AV 边缘连接 Exchange 统一消息连接（语音邮件）  <br/> |Lync Server 2013 中及其他认证实战可用  <br/> |
|19  <br/> |PSTN 对等呼叫  <br/> |Lync Server 2010 中及其他认证实战可用  <br/> |
|20  <br/> |XMPP 即时消息（联合）  <br/> |Lync Server 2013 中及其他认证实战可用  <br/> |
|21  <br/> |视频互操作服务器  <br/> |Skype 业务服务器 2015年中的新增功能  <br/> |
   
## <a name="how-health-rolls-up"></a>运行状况的累计方法

下表显示对象 Skype 的运行状况状态业务服务器监控包。
  
|**管理包对象**|**说明**|
|:-----|:-----|
|Skype 业务服务器部署  <br/> |代表 Skype 业务服务器 2015年用于组织中的部署。  <br/> |
|Skype 业务 Server 网站  <br/> |表示部署了服务的不同地理位置。  <br/> |
|Skype 业务服务器池  <br/> |向用户提供即时消息和会议等通信服务的池（在站点内）。适用于前端池、边缘池和控制器池，即使给定池中只有单个计算机。  <br/> |
|Skype 业务服务器角色  <br/> |承载 Skype 业务服务器服务的一个服务器角色。  <br/> |
|Skype 业务 Server 服务  <br/> |表示部署在特定计算机上的功能（例如，fp01.contoso.com 上的用户服务）。  <br/> |
|Skype 业务服务器组件  <br/> |服务的组件（如，通讯簿下载组件是 Web 服务的一部分）。  <br/> |
|Skype 的业务服务器池观察程序  <br/> |对一个池运行的综合事务的实例。  <br/> |
|Skype 的业务服务器注册器观察程序  <br/> |对一个注册器池运行的综合事务的实例。  <br/> |
|Skype 的业务 Server 用户服务池观察程序  <br/> |对一个用户服务池运行的综合事务的实例。  <br/> |
|Skype 的业务服务器语音池观察程序  <br/> |对一个语音池运行的综合事务的实例。  <br/> |
|Skype 的业务服务器端口观察程序  <br/> |对一个池运行的端口检查的实例。  <br/> |
|简单 URL 观察程序  <br/> |执行在部署中配置的简单 URL 的 HTTPS 探测。  <br/> |
   
![SCOM 汇总](../../media/de16195d-3aed-412e-9def-07a481d2ff0f.png)
  
业务服务器池 Skype 可以包含多个的单个 Skype 对于业务 Server 系统 （与业务服务器角色、 Skype 业务服务器服务和业务服务器组件的 Skype 的多个 Skype)。 因此，故障的单个服务器或组件是较低非常重要的业务服务器池的 Skype 的整体运行状况，因为其他同一池中的服务器可以为客户端提供的应用程序服务。 运行状况将汇总百分比级别上的业务服务器池 Skype 到。 
  
为业务服务器池观察程序 Skype 业务服务器池执行针对 Skype 的综合事务。 一个或多个综合事务（一种称为连续轮询间隔的过程）连续失败将把严重运行状况累计到池级别（任何综合事务最差的结果），如下图所示。 
  
![SCOM 汇总连续轮询](../../media/655de542-cca7-4eda-8052-9a7703ecd0e9.png)
  
## <a name="best-practice-create-a-management-pack-for-customizations"></a>最佳做法：创建管理包进行自定义

默认情况下，Operations Manager 保存所有自定义项，如默认管理包的替代设置。作为最佳做法，应该为您要自定义的每个封装管理包创建一个单独的管理包。 
  
在创建管理包来存储封装管理包的自定义设置时,我们建议相应地命名新管理包,如“Skype for Business Server 2015 自定义项”。 
  
创建新管理包来存储每个封装管理包的自定义项有利于将自定义项更容易地从测试环境导出到生产环境。这还使删除管理包变得更容易，因为您必须先删除所有依赖项才能删除管理包。如果所有管理包的自定义项都保存在默认管理包中，而您需要删除单个管理包，那么您必须删除默认管理包，这将同时删除其他管理包的自定义项。 
  
## <a name="links"></a>链接

以下链接提供了有关 System Center 2012 监视包常见任务的信息：
  
- [管理包生命周期](https://technet.microsoft.com/en-us/library/hh212732.aspx)
    
- [如何导入 Operations Manager 2012 中的管理包](https://technet.microsoft.com/en-us/library/hh212691.aspx)
    
- [如何重写规则或监视器](https://technet.microsoft.com/en-us/library/hh212869.aspx)
    
- [如何为 Operations Manager 2012 中的帐户创建一段连续文本](https://technet.microsoft.com/en-us/library/hh321655.aspx)
    
- [管理运行方式帐户和配置文件](https://technet.microsoft.com/en-us/library/hh212714.aspx)
    
- [如何导出 Operations Manager 管理包](https://technet.microsoft.com/en-us/library/hh320149.aspx)
    
- [如何删除 Operations Manager 管理包](https://technet.microsoft.com/en-us/library/hh230746.aspx)
    
以下链接提供了有关 System Center 2007 监视包常见任务的信息：
  
- [管理包生命周期管理](https://go.microsoft.com/fwlink/p/?LinkId=211463)
    
- [如何导入 Operations Manager 2007 中的管理包](https://go.microsoft.com/fwlink/p/?LinkID=142351)
    
- [如何监视使用覆盖](https://go.microsoft.com/fwlink/p/?LinkID=117777)
    
- [如何为 Operations Manager 2007 中的帐户创建一段连续文本](https://go.microsoft.com/fwlink/p/?LinkID=165410)
    
- [如何修改现有的运行方式配置文件](https://go.microsoft.com/fwlink/p/?LinkID=165412)
    
- [如何导出管理包自定义项](https://go.microsoft.com/fwlink/p/?LinkId=209940)
    
- [如何删除的管理包](https://go.microsoft.com/fwlink/p/?LinkId=209941)
    
关于 Operations Manager 和监控包的问题，请参阅[System Center Operations Manager 社区论坛](https://go.microsoft.com/fwlink/p/?LinkID=179635)。
  
有用资源是包含"通过示例"文章为特定的监控包的[系统中心操作管理器充分发挥其作用](https://opsmgrunleashed.wordpress.com/)博客。
  
有关 Operations Manager 的更多信息，请参阅下面的博客： 
  
- [操作管理器团队博客 （英文)](https://blogs.technet.com/momteam/default.aspx)
    
- [Kevin Holman OpsMgr 博客 （英文)](https://blogs.technet.com/kevinholman/default.aspx)
    
- [在 OpsMgr 想法](https://thoughtsonopsmgr.blogspot.com/)
    
- [Raphael Burri 博客 （英文)](https://rburri.wordpress.com/)
    
- [BWren 的管理空间](https://blogs.technet.com/brianwren/default.aspx)
    
- [操作经理 + + 中](https://blogs.msdn.com/boris_yanushpolsky/default.aspx)
    
> [!IMPORTANT]
> 非 Microsoft 网站上的所有信息和内容由这类网站的所有者或用户提供。对于这类网站上的信息，Microsoft 不坐任何明示、暗示或法定的保证。 
  
## <a name="see-also"></a>另请参阅

[Skype 的业务 Server 2015 管理工具](../../management-tools/management-tools.md)