---
title: 使用 SCOM 管理包管理 Skype for Business Server 2019
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/26/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 摘要：了解如何配置 Skype for Business Server 2019 基础结构以使用 System Center Operations Manager。
ms.openlocfilehash: 8f19998ad5d46074a1225ae0dd4d901bd367d823
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120381"
---
# <a name="manage-skype-for-business-server-2019-using-scom-management-pack"></a>使用 SCOM 管理包管理 Skype for Business Server 2019
 
**摘要：** 了解如何配置 Skype for Business Server 2019 基础结构以使用 System Center Operations Manager。
  
在理想中，Skype for Business Server 2019 永远不会遇到问题。 但是，Skype for Business Server 可能会受外部因素影响，例如网络崩溃和硬件故障。 通过使用 Skype for Business Server 2019 管理包，可以主动识别和解决潜在问题。 这样，Skype for Business Server 2019 管理包将扩展 System Center Operations Manager 的功能。
  
此信息是基于 Skype for Business Server 2019 通信软件监视包 9319.0 版编写的。
  
## <a name="configuration-overview"></a>配置概述

 若要将 Skype for Business Server 2019 基础结构配置为与 System Center Operations Manager 一起运行，必须执行三项操作：
  
标识和 [配置主管理服务器](../../SfbServer/management-tools/use-scom-management-pack/configure-the-primary.md)。 为此，必须安装 System Center Operations Manager 2012 SP1 或 R2。 
  
 标识 [和配置将受监视](../../SfbServer/management-tools/use-scom-management-pack/configure-computers-to-monitor.md)的 Skype for Business Server 计算机。 若要使用 System Center Operations Manager 监视 Skype for Business Server 计算机，必须安装 System Center Operations Manager 代理文件，并配置每台服务器以充当代理。 
  
 标识和 [安装和配置观察程序节点](../../SfbServer/management-tools/use-scom-management-pack/watcher-nodes.md)。 观察程序节点是定期运行 Skype for Business Server 综合事务的计算机 -Windows PowerShell cmdlet，用于验证关键 Skype for Business Server 组件（如登录到系统的能力或交换即时消息的能力）是否正常工作。 
  
## <a name="system-center-operations-manager-root-management-server-and-agent-support"></a>System Center Operations Manager 根管理服务器和代理支持

管理包可以与 System Center Operations Manager 2007 R2 (64 位)  (一起使用，仅支持用于迁移目的) 或 System Center Operations Manager 2012 SP1 &amp; R2 (64 位) 。 下表显示了 Skype for Business Server 2019 管理包支持的配置： 
  
|**配置**|**是否受支持？**|
|:-----|:-----|
|Windows Server 2008 R2 操作系统  <br/> Windows Server 2012 R2 操作系统  <br/> |是。 同时位于 Skype for Business Server 2019 服务器和综合事务观察程序节点上。  <br/> |
|群集服务器  <br/> |不支持。  <br/> |
|无代理监视  <br/> |不支持。  <br/> |
|虚拟环境  <br/> |是。  <br/> |
|加入域的服务器角色  <br/> |所有内部 Skype for Business Server 2019 服务器角色都必须加入域。  <br/> |
|独立服务器角色  <br/> |Skype for Business Server 2019 边缘服务器无需加入域。  <br/> |
|拓扑限制  <br/> |必须从同一 Operations Manager 管理组监视部署中所有服务器角色。  <br/> |
|综合事务观察程序节点  <br/> |支持使用综合事务观察程序节点监视方案可用性 (所需的其他) 。 观察程序节点不需要加入域。  <br/> |
   
下表显示了综合事务观察程序节点的容量和操作系统要求：
  
|**硬件组件**|**最低要求**|
|:-----|:-----|
|CPU  <br/> |以下各项之一：  <br/> 64 位处理器、四核、2.33 GHz 或更高  <br/> 64 位 2 路处理器、双核、2.33 GHz 或更高  <br/> |
|内存  <br/> |8 GB  <br/> |
|操作系统  <br/> |Windows Server 2008 R2  <br/> Windows Server 2012 R2  <br/> |
|网络  <br/> |1 Gbps 的 1 个网络适配器  <br/> |
   
## <a name="prerequisites"></a>先决条件

若要运行综合事务观察程序节点，必须先安装以下内容：
  
- System Center Operations Manager 代理 
    
-  Microsoft .NET Framework 4.5
    
- UCMA (OcsCore.msi) 和统一通信托管 API ()  (版本的 Skype for Business Server 核心安装文件必须与 Skype for Business Server WatcherNode.msi版本) 
    
## <a name="files-in-this-monitoring-pack"></a>此监视包中的文件

Skype for Business Server 2019 监视包包括以下文件：
  
- Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp
    
- Microsoft.LS.2019.Monitoring.ComponentAndUser.mp
    
- WatcherNode.msi
    
## <a name="whats-new"></a>新增功能

以下功能是 Skype for Business Server 2019 管理包的新增功能。

- **[2019 年 9 月更新中的更改](https://www.microsoft.com/download/details.aspx?id=57511)** 某些警报已删除特殊字符。 在某些情况下，特殊字符会干扰 SCOM 命令通道通知功能。

- **客户端登录的自动发现** 登录到 Skype for Business Server 2019 的客户端应用程序通常会自动发现要登录的服务器。 综合事务现在支持验证自动发现配置是否正确。
    
- **自定义的综合事务运行间隔** 为了简化观察程序节点的设置过程，综合事务可以共享用户帐户。 这会降低测试运行的频率，因为测试被序列化以避免冲突。 默认情况下，综合事务每 15 分钟运行一次，以确保所有测试都有时间运行。 选择使用更多用户或更少每个用户的测试的管理员现在也可以缩短运行间隔。
    
- **视频互操作服务综合事务** 从其他供应商解决方案迁移到 Skype for Business Server 2019 的客户通常希望继续使用来自这些其他供应商的视频电话会议设备 (VTC) 视频电话会议设备。 视频互操作服务器是一种新的 Skype for Business Server 2019 服务器角色，通过视频 SIP 中继连接到 Cisco CUCM，客户可以继续在会议室中使用 Cisco VTC。 此功能还添加了综合事务，以帮助验证视频互操作服务器是否启动，并可以处理通过视频 SIP 中继传入的连接。
    
- **应用程序共享会议综合事务** 现在支持应用程序共享会议的端到端方案验证。
    
## <a name="monitoring-scenarios"></a>监视方案

Skype for Business Server 2019 管理包利用各种功能来帮助检测和诊断问题。 这些功能可实时查看 Skype for Business Server 2019 环境的运行状况。
  
|**监视方案**|**说明**|
|:-----|:-----|
|综合事务  <br/> | Windows PowerShell cmdlet 测试并帮助确保方案（如登录、状态、IM 和会议）的高可用性。 <br/> 综合事务可以从任何地理位置运行，包括企业内部、企业外部和分支机构。  <br/> 当综合事务失败时，将创建 HTML 日志以帮助确定失败的确切性质。 这包括了解哪些操作失败、每个操作延迟、用于运行测试的命令行以及发生的特定错误。  <br/> |
|呼叫可靠性警报  <br/> |Skype for Business Server 2019 (写入的呼叫详细信息) CDR 反映了用户能否连接到呼叫或呼叫终止的原因。 呼叫可靠性警报查询 CDR 数据库以生成警报，指示大量用户何时遇到对等呼叫或基本会议功能的连接问题。  <br/> 方案覆盖包括音频呼叫、对等即时消息 (IM) 和其他会议功能。  <br/> |
|媒体质量警报  <br/> |查看每次呼叫结束时由 Skype for Business Server 2019 (QoE) 发布的用户体验质量报告的数据库查询。 这些查询会生成警报，准确指出用户最有可能在呼叫和会议期间遇到媒体质量受损的情况。 数据是在数据包延迟和丢失等关键指标（直接影响用户体验质量）上构建的。  <br/> |
|组件运行状况警报  <br/> |各个服务器组件通过事件日志和性能计数器发出警报，以指示可能显著影响用户方案的故障情况。 这些警报指示各种情况，例如服务未运行、高故障率、高消息延迟或连接问题。  <br/> |
|依赖关系运行状况监视  <br/> |Skype for Business Server 可能会因各种外部原因失败。 管理包监视并收集可指示关键问题的关键外部依赖项的数据。 这些依赖关系Internet Information Services (IIS) 可用性，以及用于 Skype for Business Server 的服务器 CPU。  <br/> |
   
### <a name="alert-prioritization"></a>警报优先顺序

警报分为以下类别： 
  
 **高优先级警报：** 这些警报指示导致大型用户组的服务中断的条件，需要立即采取措施。 综合事务和脱机服务（如 Skype for Business Server 音频/视频会议 (检测到的中断) 高优先级警报。 相比之下，单台计算机的组件故障不是高优先级警报。 Skype for Business Server 2019 具有针对这些情况的内置高可用性功能，例如，负载平衡器后面的多个前端服务器。
  
 **中等优先级警报：** 这些警报指示影响用户子集或指示呼叫质量问题的条件，例如组件故障、呼叫建立延迟或通话中音频质量降低。 此类别中的警报是有状态 (即，警报的性质根据网络连接的状态更改。) 例如，如果呼叫建立时间指示延迟，但之后又返回到正常阈值，将在 System Center Operations Manager 中自动解决此中等优先级警报，管理员无需采取措施。 无法自动解决的警报通常由管理员在同一工作天解决。
  
 **其他警报：** 这些警报由可能影响特定用户或部分用户的组件生成。 例如，典型的警报是通讯簿服务无法分析用户的 Active Directory® 域服务 (AD DS) 条目：testuser@contoso.com。 管理员可以在有可用时间时处理这些警报。
  
### <a name="synthetic-transactions"></a>综合事务

Skype for Business Server 2019 管理包通过综合事务增加了警报的覆盖范围。 综合事务Windows PowerShell集成到 Operations Manager 管理包中以测试端到端用户方案的 cmdlet。 当指定服务器执行综合事务时，管理包会定期触发这些 cmdlet。 由于综合事务导致的故障将生成有状态警报。 以下是 Skype for Business Server 2019 支持的综合事务：
  
**支持的注册、状态和联系人综合事务**

||||
|:-----|:-----|:-----|
|1  <br/> |注册 (用户登录)   <br/> |可用的 Lync Server 2010 及以后版本  <br/> |
|2  <br/> |通讯簿服务 (文件下载)   <br/> |可用的 Lync Server 2010 及以后版本  <br/> |
|3  <br/> |通讯簿 Web 查询  <br/> |可用的 Lync Server 2010 及以后版本  <br/> |
|4   <br/> |状态  <br/> |可用的 Lync Server 2010 及以后版本  <br/> |
|5   <br/> |统一联系人存储  <br/> |可用的 Lync Server 2013 及以后版本  <br/> |
   
**支持的对等服务综合事务**

||||
|:-----|:-----|:-----|
|6   <br/> |对等即时消息  <br/> |在 Lync Server 2010 及以后可用  <br/> |
|7   <br/> |对等音频视频  <br/> |在 Lync Server 2010 及以后可用  <br/> |
|8   <br/> |MCX 对等即时消息 (移动设备)   <br/> |在 Lync Server 2010 到 Skype for Business 2019 的 2011 年 9 月版本中可用  <br/> |
 
> [!NOTE]
> Skype for Business Server 2019 (MCX) Mobility Service 不再提供对旧版移动客户端的支持。 所有当前的 Skype for Business 移动客户端已使用统一通信 Web API (UCWA) 来支持即时消息 (IM) 、状态和联系人。 使用 MCX 的旧客户端的用户将需要升级到当前客户端。
  
**支持的会议和持久聊天综合事务**

||||
|:-----|:-----|:-----|
|9   <br/> |音频视频会议  <br/> |在 Lync Server 2010 及以后可用  <br/> |
|10    <br/> |数据会议  <br/> |在 Lync Server 2013 及以后可用  <br/> |
|11  <br/> |即时消息会议  <br/> |在 Lync Server 2010 及以后可用  <br/> |
|12   <br/> | 持久聊天 <br/> |在 Lync Server 2013 及以后可用  <br/> |
|13  <br/> |加入启动 (安排的会议)   <br/> |在 Lync Server 2013 及以后可用  <br/> |
|14   <br/> |电话拨入式会议  <br/> |可用于 Skype for Business Server 2015 及以后版本 <br/> |
|15   <br/> |应用程序共享会议  <br/> |可用于 Skype for Business Server 2015 及以后版本 <br/> |
|16   <br/> |UCWA 会议 (Web 会议加入)   <br/> |可用于 Skype for Business Server 2015 及以后版本 <br/> |
   
**支持的网络和合作伙伴依赖关系综合事务**

||||
|:-----|:-----|:-----|
|17   <br/> |AV 边缘连接  <br/> |在 Lync Server 2013 及以后可用  <br/> |
|18   <br/> |AV 边缘连接 Exchange 统一消息 (语音邮件)   <br/> |在 Lync Server 2013 及以后可用  <br/> |
|19  <br/> |PSTN 对等呼叫  <br/> |在 Lync Server 2010 及以后可用  <br/> |
|20  <br/> |XMPP 即时消息 (联盟)   <br/> |在 Lync Server 2013 及以后可用  <br/> |
| 21  <br/> |视频互操作服务器  <br/> |可用于 Skype for Business Server 2015 及以后版本  <br/> |
   
## <a name="how-health-rolls-up"></a>运行状况的汇总

下表显示了 Skype for Business Server 监视包的对象的运行状况。
  
|**管理包对象**|**说明**|
|:-----|:-----|
|Skype for Business Server 部署  <br/> |表示在组织中部署 Skype for Business Server 2019。  <br/> |
|Skype for Business Server 站点  <br/> |表示部署服务的不同地理位置。  <br/> |
|Skype for Business Server 池  <br/> |站点 (中的池) ，它为用户提供即时消息和会议等通信服务。 适用于前端池、边缘池和控制器池，即使给定池中只有一台计算机。  <br/> |
|Skype for Business Server 角色  <br/> |托管 Skype for Business Server 服务的服务器角色。  <br/> |
|Skype for Business Server 服务  <br/> |表示特定计算机上部署的功能 (例如，fp01.contoso.com) 。  <br/> |
|Skype for Business Server 组件  <br/> |例如，Service (组件，通讯簿下载组件是 Web 服务包的一) 。  <br/> |
|Skype for Business Server 池观察程序  <br/> |对一个池运行的综合事务的实例。  <br/> |
|Skype for Business Server 注册器观察程序  <br/> |对一个注册器池运行的综合事务的实例。  <br/> |
|Skype for Business Server 用户服务池观察程序  <br/> |对一个用户服务池运行的综合事务的实例。  <br/> |
|Skype for Business Server 语音池观察程序  <br/> |对一个语音池运行的综合事务的实例。  <br/> |
|Skype for Business Server 端口观察程序  <br/> |针对一个池运行的端口检查的实例。  <br/> |
|简单 URL 观察程序  <br/> |在部署中执行配置的简单 URL 的 HTTPS 探测。  <br/> |
   
![SCOM 汇总](../../SfbServer/media/de16195d-3aed-412e-9def-07a481d2ff0f.png)
  
Skype for Business Server 池可以包含多个单独的 Skype for Business Server 系统 (具有多个 Skype for Business Server 角色、Skype for Business Server 服务和 Skype for Business Server 组件) 。 因此，单个服务器或组件的故障对 Skype for Business Server 池的整体运行状况不太关键，因为同一池中的其他服务器可以为客户端提供应用程序服务。 运行状况将按百分比级别汇总到 Skype for Business Server 池。 
  
Skype for Business Server 池观察程序对 Skype for Business Server 池执行综合事务。 一个或多个综合事务连续失败 (称为连续轮询间隔) 的进程将严重运行状况汇总到池级别 (任何综合事务) 最差的情况，如下图所示。 
  
![SCOM 汇总连续轮询](../../SfbServer/media/655de542-cca7-4eda-8052-9a7703ecd0e9.png)
  
## <a name="best-practice-create-a-management-pack-for-customizations"></a>最佳做法：为自定义项创建管理包

默认情况下，Operations Manager 保存所有自定义项，例如对默认管理包的覆盖。 最佳做法是，应为要自定义的每个密封管理包创建单独的管理包。 
  
创建用于存储封装管理包的自定义设置的管理包时，我们建议适当地命名新的管理包，例如"Skype for Business Server 2019 自定义项"。
  
通过创建新的管理包来存储每个密封管理包的自定义项，可以更轻松地将自定义项从测试环境导出到生产环境。 这还便于删除管理包，因为必须先删除任何依赖项，然后才能删除管理包。 如果所有管理包的自定义项都保存在默认管理包中，并且您需要删除单个管理包，则必须先删除默认管理包，该包还会删除其他管理包的自定义项。 
  
## <a name="links"></a>链接

以下链接将您连接到有关与监控包关联的常见System Center 2012的信息：
  
- [管理包生命周期](/previous-versions/system-center/system-center-2012-R2/hh212732(v=sc.12))
    
- [如何在 Operations Manager 2012 中导入管理包](/previous-versions/system-center/system-center-2012-R2/hh212691(v=sc.12))
    
- [如何覆盖规则或监视器](/previous-versions/system-center/system-center-2012-R2/hh212869(v=sc.12))
    
- [如何在 Operations Manager 2012 中创建运行方式帐户](/previous-versions/system-center/system-center-2012-R2/hh321655(v=sc.12))
    
- [管理"作为帐户和配置文件运行"](/previous-versions/system-center/system-center-2012-R2/hh212714(v=sc.12))
    
- [如何导出 Operations Manager 管理包](/previous-versions/system-center/system-center-2012-R2/hh320149(v=sc.12))
    
- [如何删除 Operations Manager 管理包](/previous-versions/system-center/system-center-2012-R2/hh230746(v=sc.12))
    
以下链接将您连接到有关与 System Center 2007 监视包关联的常见任务的信息：
  
- [管理管理包生命周期](/previous-versions/system-center/operations-manager-2007-r2/cc974486(v=technet.10))
    
- [如何在 Operations Manager 2007 中导入管理包](/previous-versions/system-center/operations-manager-2007-r2/cc974494(v=technet.10))
    
- [如何使用替代监视](/previous-versions/system-center/operations-manager-2007-r2/bb309719(v=technet.10))
    
- [如何在 Operations Manager 2007 中创建运行方式帐户](/previous-versions/system-center/operations-manager-2007-r2/bb309445(v=technet.10))
    
- [如何修改现有的"作为配置文件运行"](/previous-versions/system-center/operations-manager-2007-r2/dd891202(v=technet.10))
    
- [如何导出管理包自定义](/previous-versions/system-center/operations-manager-2007-r2/cc974487(v=technet.10))
    
- [如何删除管理包](/previous-versions/system-center/operations-manager-2007-r2/cc974489(v=technet.10))
    
有关 Operations Manager 和监视包的问题，请参阅 [System Center Operations Manager 社区论坛](https://go.microsoft.com/fwlink/p/?LinkID=179635)。
  
System [Center Operations Manager 利用的](https://opsmgrunleashed.wordpress.com/) 博客是一个有用的资源，其中包含特定监视包的"按示例"文章。
  
有关 Operations Manager 的其他信息，请参阅以下博客： 
  
- [Operations Manager 团队博客](https://blogs.technet.com/momteam/default.aspx)
    
- [Kevin Holman 的 OpsMgr 博客](https://blogs.technet.com/kevinholman/default.aspx)
    
- [OpsMgr 的思路](https://thoughtsonopsmgr.blogspot.com/)
    
- [为 Burri 撰写博客](https://rburri.wordpress.com/)
    
- [BWren 的管理空间](https://blogs.technet.com/brianwren/default.aspx)
    
- [Ops Mgr ++](https://blogs.msdn.com/boris_yanushpolsky/default.aspx)
    
> [!IMPORTANT]
> 非 Microsoft 网站上的所有信息和内容都由网站的所有者或用户提供。 Microsoft 对于此网站上的信息不做出明示、暗示或法定的担保。 
  
## <a name="see-also"></a>另请参阅

[Skype for Business Server 2019 管理工具](../management-tools-2019.md)