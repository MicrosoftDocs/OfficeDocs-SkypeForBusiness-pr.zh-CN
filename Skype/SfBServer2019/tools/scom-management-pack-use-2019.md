---
title: 使用 SCOM 管理包管理 Skype for Business Server 2019
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 10/26/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
description: '摘要: 了解如何配置 Skype for Business Server 2019 基础结构以与 System Center Operations Manager 配合使用。'
ms.openlocfilehash: 5b33bae3f9ff3d71ec9cf5f33f5332afe58c6258
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34288245"
---
# <a name="manage-skype-for-business-server-2019-using-scom-management-pack"></a>使用 SCOM 管理包管理 Skype for Business Server 2019
 
**摘要:** 了解如何配置 Skype for Business Server 2019 基础结构以与 System Center Operations Manager 配合使用。
  
在理想的世界里, 您永远不会遇到 Skype for Business Server 2019 的问题。 但是, Skype for business 服务器可能受外部因素的影响, 例如网络崩溃和硬件故障。 通过使用 Skype for Business Server 2019 管理包, 您可以主动识别并解决潜在问题。 通过这种方式, Skype for business Server 2019 管理包扩展了 System Center Operations Manager 的功能。
  
此信息基于 Skype for business Server 2019 通信软件的监视包版本9319.0 编写。
  
## <a name="configuration-overview"></a>配置概述

 要配置 Skype for Business Server 2019 基础结构以与 System Center Operations Manager 配合使用, 必须执行以下三项操作:
  
确定并[Configure the Primary Management Server](../../SfbServer/management-tools/use-scom-management-pack/configure-the-primary.md)。 若要执行此操作, 必须安装 System Center Operations Manager 2012 SP1 或 R2。 
  
 标识和[配置将监视的 Skype For Business 服务器计算机](../../SfbServer/management-tools/use-scom-management-pack/configure-computers-to-monitor.md)。 若要使用 System Center Operations Manager 监视 Skype for business 服务器计算机, 必须安装 System Center Operations Manager 代理文件, 并将每台服务器配置为充当代理。 
  
 标识并[安装和配置观察程序节点](../../SfbServer/management-tools/use-scom-management-pack/watcher-nodes.md)。 观察程序节点是定期运行 Skype for business 服务器合成事务的计算机-验证密钥 Skype for business Server 组件的 Windows PowerShell cmdlet, 如登录到系统或交换即时的功能封邮件按预期工作。 
  
## <a name="system-center-operations-manager-root-management-server-and-agent-support"></a>System Center Operations Manager 根管理服务器和代理支持

管理包可以与 System Center Operations Manager 2007 R2 (64 位) 配合使用 (仅支持迁移用途) 或 System Center Operations Manager 2012 SP1 &amp; R2 (64 位)。 下表显示了 Skype for business Server 2019 的管理包支持的配置: 
  
|**配置**|**能?**|
|:-----|:-----|
|Windows Server 2008 R2 操作系统  <br/> Windows Server 2012 R2 操作系统  <br/> |是。 在 Skype for business Server 2019 服务器和综合事务观察程序节点上都是如此。  <br/> |
|群集服务器  <br/> |不支持。  <br/> |
|无代理监视  <br/> |不支持。  <br/> |
|虚拟环境  <br/> |是。  <br/> |
|加入域的服务器角色  <br/> |所有内部 Skype for business Server 2019 服务器角色必须已加入域。  <br/> |
|独立服务器角色  <br/> |Skype for Business Server 2019 Edge 服务器不需要加入域。  <br/> |
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
    
- Skype for business Server core 安装文件 (OcsCore) 和统一通信托管 API (UCMA) (版本必须与 Skype for Business 服务器 WatcherNode 版本相匹配)
    
## <a name="files-in-this-monitoring-pack"></a>此监视包中的文件

Skype for business Server 2019 的监视包包括以下文件:
  
- Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp
    
- Microsoft.LS.2019.Monitoring.ComponentAndUser.mp
    
- WatcherNode.msi
    
## <a name="whats-new"></a>新增功能

以下功能是 Skype for business Server 2019 管理包的新增功能。
  
- **客户端登录的自动发现**登录到 Skype for business Server 2019 的客户端应用程序通常会自动发现要登录到的服务器。 综合事务现在支持验证是否正确配置了自动发现。
    
- **自定义的综合事务运行间隔**为了简化观察程序节点的设置过程, 综合事务可以共享用户帐户。 这将减慢测试运行的频率, 因为测试被序列化以避免冲突。 默认情况下, 合成事务每隔15分钟运行, 以确保所有测试都有时间运行。 选择对每个用户使用更多用户或较少测试的管理员现在还可以减少运行间隔。
    
- **视频互操作服务合成事务**从其他供应商解决方案迁移到 Skype for business Server 2019 的客户通常希望继续使用来自这些供应商的视频 teleconferencing 设备 (VTCs)。 视频互操作服务器是全新的 Skype for Business Server 2019 服务器角色, 使客户能够通过视频 SIP 主干连接到 Cisco CUCM, 继续使用其会议室中的 Cisco VTCs。 此功能还添加了一个合成事务, 以帮助验证视频互操作服务器是否正常, 并可以通过视频 SIP 主干处理传入连接。
    
- **应用程序共享会议综合事务** 现在支持应用程序共享会议的端到端方案验证。
    
## <a name="monitoring-scenarios"></a>监视方案

Skype for Business Server 2019 管理包利用各种功能来帮助您检测和诊断问题。 这些功能可实时查看 Skype for Business Server 2019 环境的运行状况。
  
|**监视方案**|**说明**|
|:-----|:-----|
|综合事务  <br/> | 用于测试和帮助确保方案 (如登录、联机状态、IM 和会议) 的高可用性的 Windows PowerShell cmdlet。 <br/> 综合事务可从任何地理位置运行，包括企业内部、企业外部和分支机构。  <br/> 当综合事务失败时，系统会创建 HTML 日志来帮助确定失败的确切性质。这包括了解哪项操作失败、每项操作的延迟、用于运行测试的命令行，以及发生的具体错误。  <br/> |
|呼叫可靠性警报  <br/> |Skype for Business Server 2019 服务器编写的呼叫详细记录 (CDRs) 反映用户是否可以连接到呼叫或终止呼叫的原因。 呼叫可靠性警报查询 CDR 数据库来生成警报，这些警报指出大量用户什么时候遇到对等呼叫或基本会议功能的连接问题。  <br/> 涵盖的方案包括音频呼叫、对等即时消息 (IM) 和其他会议功能。  <br/> |
|媒体质量警报  <br/> |在每次通话结束时, 查看由 Skype for business Server 2019 客户端发布的体验质量 (QoE) 报告的数据库查询。 这些查询会产生警报，这些警报可准确指出在什么方案中，用户最有可能在呼叫和会议期间遇到受损的媒体质量。 数据在数据包延迟和丢失等关键指标的基础上建立，这些指标直接影响用户体验的质量。  <br/> |
|组件运行状况警报  <br/> |个别服务器组件会通过事件日志和性能计数器发出警报，以指出可能会严重影响用户方案的故障情况。这些警报指出各种情况，如服务未运行、高故障率、高消息延迟或连接问题。  <br/> |
|依赖项运行状况监视  <br/> |出于各种外部原因, Skype for business 服务器可能会失败。 管理包监视并收集可能表明存在严重问题的关键外部依赖项的数据。 这些依赖关系包括 Internet 信息服务 (IIS) 可用性, 以及用于 Skype for business 服务器的服务器的 CPU。  <br/> |
   
### <a name="alert-prioritization"></a>警报优先级

警报分成以下类别： 
  
 **高优先级警报:** 这些警报指示导致大型用户组的服务中断的条件, 并且需要立即执行操作。 综合事务和脱机服务 (如 Skype for Business Server 音频/视频会议) 检测到的中断均为高优先级警报。 相比之下, 单个计算机上的组件故障不是高优先级的警报。 Skype for Business Server 2019 为这些情形 (例如, 负载平衡器背后的多个前端服务器) 提供了内置的高可用性功能。
  
 **中等优先级警报:** 这些警报指示影响用户子集或指示通话质量问题的条件, 例如, 组件故障、通话中的延迟或通话中较低的音频质量。 此类别中的警报是有状态的 (即, 警报的性质根据网络连接的状态而变化。)例如, 如果呼叫建立时间指示延迟, 但随后返回到正常阈值, 则在 System Center Operations Manager 中将自动解决此中等优先级警报, 并且管理员无需执行任何操作。 不能自动解析的警报通常由管理员在同一工作日内解决。
  
 **其他警报：** 产生这些警报的组件可能影响特定用户或部分用户。例如，典型的警报可能是，通讯簿服务无法解析用户的 Active Directory® 域服务 (AD DS) 条目：testuser@contoso.com。管理员只要有时间就可以处理这些警报。
  
### <a name="synthetic-transactions"></a>综合事务

Skype for Business Server 2019 管理包通过综合事务提供了更多的警报覆盖范围。 合成事务是集成到 Operations Manager 管理包中以测试端到端用户方案的 Windows PowerShell cmdlet。 当你指定服务器以执行综合事务时, 这些 cmdlet 将定期由管理包触发。 由合成事务生成状态警报导致的失败。 以下是 Skype for business Server 2019 的受支持的综合事务:
  
**支持的注册、状态和联系人综合事务**

||||
|:-----|:-----|:-----|
|1  <br/> |注册（用户登录）  <br/> |可用的 Lync Server 2010 和更高版本  <br/> |
|2  <br/> |通讯簿服务（文件下载）  <br/> |可用的 Lync Server 2010 和更高版本  <br/> |
|3  <br/> |通讯簿 Web 查询  <br/> |可用的 Lync Server 2010 和更高版本  <br/> |
|4  <br/> |状态  <br/> |可用的 Lync Server 2010 和更高版本  <br/> |
|5  <br/> |统一联系人存储  <br/> |可用的 Lync Server 2013 和更高版本  <br/> |
   
**支持的对等服务综合事务**

||||
|:-----|:-----|:-----|
|6  <br/> |对等即时消息  <br/> |在 Lync Server 2010 和更高版本中可用  <br/> |
|7  <br/> |对等音频视频  <br/> |在 Lync Server 2010 和更高版本中可用  <br/> |
|个  <br/> |MCX 对等即时消息（移动）  <br/> |在2011年9月推出的 Lync Server 2010 发布到 Skype for business 2019  <br/> |
 
> [!NOTE]
> 在 Skype for Business Server 2019 中, MCX (移动服务) 对旧式移动客户端的支持不再可用。 所有当前 Skype for business 移动客户端都已使用统一通信 Web API (UCWA) 来支持即时消息 (IM)、状态和联系人。 具有使用 MCX 的旧客户端的用户将需要升级到当前客户端。
  
**支持的会议和持久聊天综合事务**

||||
|:-----|:-----|:-----|
|db-9  <br/> |音频视频会议  <br/> |在 Lync Server 2010 和更高版本中可用  <br/> |
|10  <br/> |数据会议  <br/> |在 Lync Server 2013 和更高版本中可用  <br/> |
|11  <br/> |即时消息会议  <br/> |在 Lync Server 2010 和更高版本中可用  <br/> |
|至  <br/> | 持久聊天 <br/> |在 Lync Server 2013 和更高版本中可用  <br/> |
|13  <br/> |加入启动器（排定的会议）  <br/> |在 Lync Server 2013 和更高版本中可用  <br/> |
|14  <br/> |电话拨入式会议  <br/> |在 Skype for Business Server 2015 和更高版本中可用 <br/> |
|岁  <br/> |应用程序共享会议  <br/> |在 Skype for Business Server 2015 和更高版本中可用 <br/> |
|utf-16  <br/> |UCWA 会议（Web 会议加入）  <br/> |在 Skype for Business Server 2015 和更高版本中可用 <br/> |
   
**支持的网络和合作伙伴依赖项综合事务**

||||
|:-----|:-----|:-----|
|日  <br/> |AV 边缘连接  <br/> |在 Lync Server 2013 和更高版本中可用  <br/> |
|18  <br/> |AV 边缘连接 Exchange 统一消息连接（语音邮件）  <br/> |在 Lync Server 2013 和更高版本中可用  <br/> |
|19  <br/> |PSTN 对等呼叫  <br/> |在 Lync Server 2010 和更高版本中可用  <br/> |
|名  <br/> |XMPP 即时消息（联合）  <br/> |在 Lync Server 2013 和更高版本中可用  <br/> |
|21日  <br/> |视频互操作服务器  <br/> |在 Skype for Business Server 2015 和更高版本中可用  <br/> |
   
## <a name="how-health-rolls-up"></a>运行状况的累计方法

下表显示了 Skype for business 服务器监视包对象的运行状态。
  
|**管理包对象**|**说明**|
|:-----|:-----|
|Skype for Business 服务器部署  <br/> |表示组织中 Skype for Business Server 2019 的部署。  <br/> |
|Skype for business 服务器网站  <br/> |表示部署了服务的不同地理位置。  <br/> |
|Skype for business 服务器池  <br/> |向用户提供即时消息和会议等通信服务的池（在站点内）。适用于前端池、边缘池和控制器池，即使给定池中只有单个计算机。  <br/> |
|Skype for Business 服务器角色  <br/> |托管 Skype for Business Server 服务的服务器角色。  <br/> |
|Skype for Business 服务器服务  <br/> |表示部署在特定计算机上的功能（例如，fp01.contoso.com 上的用户服务）。  <br/> |
|Skype for Business 服务器组件  <br/> |服务的组件（如，通讯簿下载组件是 Web 服务的一部分）。  <br/> |
|Skype for Business 服务器池观察程序  <br/> |对一个池运行的综合事务的实例。  <br/> |
|Skype for Business 服务器注册程序观察程序  <br/> |对一个注册器池运行的综合事务的实例。  <br/> |
|Skype for Business 服务器用户服务池观察程序  <br/> |对一个用户服务池运行的综合事务的实例。  <br/> |
|Skype for Business 服务器语音池观察程序  <br/> |对一个语音池运行的综合事务的实例。  <br/> |
|Skype for Business 服务器端口观察程序  <br/> |对一个池运行的端口检查的实例。  <br/> |
|简单 URL 观察程序  <br/> |执行在部署中配置的简单 URL 的 HTTPS 探测。  <br/> |
   
![SCOM 汇总](../../SfbServer/media/de16195d-3aed-412e-9def-07a481d2ff0f.png)
  
Skype for business 服务器池可以包含多个单独的 Skype for business 服务器系统 (具有多个 Skype for business 服务器角色、Skype for business 服务器服务和 Skype for business 服务器组件)。 因此, 单个服务器或组件的失败对 Skype for Business 服务器池的整体运行状况不太重要, 因为同一池中的其他服务器可以向客户端提供应用程序服务。 运行状况将在百分比级别上累加到 Skype for business 服务器池。 
  
Skype for Business 服务器池监视程序针对 Skype for business 服务器池执行合成事务。 一个或多个综合事务（一种称为连续轮询间隔的过程）连续失败将把严重运行状况累计到池级别（任何综合事务最差的结果），如下图所示。 
  
![SCOM 汇总连续轮询](../../SfbServer/media/655de542-cca7-4eda-8052-9a7703ecd0e9.png)
  
## <a name="best-practice-create-a-management-pack-for-customizations"></a>最佳做法：创建管理包进行自定义

默认情况下，Operations Manager 保存所有自定义项，如默认管理包的替代设置。作为最佳做法，应该为您要自定义的每个封装管理包创建一个单独的管理包。 
  
创建用于存储密封的管理包的自定义设置的管理包时, 我们建议相应地为新管理包命名, 如 "Skype for Business Server 2019 自定义项"。
  
创建新管理包来存储每个封装管理包的自定义项有利于将自定义项更容易地从测试环境导出到生产环境。这还使删除管理包变得更容易，因为您必须先删除所有依赖项才能删除管理包。如果所有管理包的自定义项都保存在默认管理包中，而您需要删除单个管理包，那么您必须删除默认管理包，这将同时删除其他管理包的自定义项。 
  
## <a name="links"></a>链接

以下链接提供了有关 System Center 2012 监视包常见任务的信息：
  
- [管理包生命周期](https://technet.microsoft.com/en-us/library/hh212732.aspx)
    
- [如何在 Operations Manager 2012 中导入管理包](https://technet.microsoft.com/en-us/library/hh212691.aspx)
    
- [如何替代规则或监视器](https://technet.microsoft.com/en-us/library/hh212869.aspx)
    
- [如何在 Operations Manager 2012 中创建运行方式帐户](https://technet.microsoft.com/en-us/library/hh321655.aspx)
    
- [管理运行方式帐户和配置文件](https://technet.microsoft.com/en-us/library/hh212714.aspx)
    
- [如何导出 Operations Manager 管理包](https://technet.microsoft.com/en-us/library/hh320149.aspx)
    
- [如何删除 Operations Manager 管理包](https://technet.microsoft.com/en-us/library/hh230746.aspx)
    
以下链接提供了有关 System Center 2007 监视包常见任务的信息：
  
- [管理管理包生命周期](https://go.microsoft.com/fwlink/p/?LinkId=211463)
    
- [如何在 Operations Manager 2007 中导入管理包](https://go.microsoft.com/fwlink/p/?LinkID=142351)
    
- [如何使用替代进行监视](https://go.microsoft.com/fwlink/p/?LinkID=117777)
    
- [如何在 Operations Manager 2007 中创建运行方式帐户](https://go.microsoft.com/fwlink/p/?LinkID=165410)
    
- [如何修改现有的运行方式配置文件](https://go.microsoft.com/fwlink/p/?LinkID=165412)
    
- [如何导出管理包自定义项](https://go.microsoft.com/fwlink/p/?LinkId=209940)
    
- [如何删除管理包](https://go.microsoft.com/fwlink/p/?LinkId=209941)
    
有关 Operations Manager 和监视包的问题, 请参阅[System Center Operations Manager 社区论坛](https://go.microsoft.com/fwlink/p/?LinkID=179635)。
  
" [System Center Operations Manager Unleashed](https://opsmgrunleashed.wordpress.com/)博客" 是一种有用的资源, 其中包含特定监视包的 "按示例" 发布。
  
有关 Operations Manager 的更多信息，请参阅下面的博客： 
  
- [Operations Manager 团队博客](https://blogs.technet.com/momteam/default.aspx)
    
- [古柯 Holman 的 OpsMgr 博客](https://blogs.technet.com/kevinholman/default.aspx)
    
- [有关 OpsMgr 的想法](https://thoughtsonopsmgr.blogspot.com/)
    
- [Raphael Burri 的博客](https://rburri.wordpress.com/)
    
- [BWren 的管理空间](https://blogs.technet.com/brianwren/default.aspx)
    
- [Ops Mgr + +](https://blogs.msdn.com/boris_yanushpolsky/default.aspx)
    
> [!IMPORTANT]
> 非 Microsoft 网站上的所有信息和内容由这类网站的所有者或用户提供。对于这类网站上的信息，Microsoft 不坐任何明示、暗示或法定的保证。 
  
## <a name="see-also"></a>另请参阅

[Skype for Business Server 2019 管理工具](../management-tools-2019.md)
