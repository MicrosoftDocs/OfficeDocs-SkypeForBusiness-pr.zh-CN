---
title: 使用 SCOM 管理包管理 Skype for Business Server 2019
ms.reviewer: ''
ms.author: v-lanac
author: LanaChin
manager: serdars
ms.date: 10/26/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 摘要：了解如何将 Skype for Business Server 2019 基础结构配置为与 System Center Operations Manager 配合使用。
ms.openlocfilehash: 54c9f3dadb73df45ddc21cfc40ff83711032a4c2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150539"
---
# <a name="manage-skype-for-business-server-2019-using-scom-management-pack"></a>使用 SCOM 管理包管理 Skype for Business Server 2019
 
**摘要：** 了解如何配置 Skype for Business Server 2019 基础结构以与 System Center Operations Manager 配合使用。
  
在理想的世界中，您永远不会遇到 Skype for Business Server 2019 的问题。 但是，Skype for Business Server 可能受外部因素的影响，例如网络崩溃和硬件故障。 通过使用 Skype for Business Server 2019 管理包，可以主动识别和解决潜在问题。 通过这种方式，Skype for Business Server 2019 管理包扩展了 System Center Operations Manager 的功能。
  
此信息是根据 Skype for business Server 2019 通信软件的监控包版本9319.0 编写的。
  
## <a name="configuration-overview"></a>配置概述

 若要配置 Skype for Business Server 2019 基础结构以使用 System Center Operations Manager，您必须执行以下三项操作：
  
确定并[配置主管理服务器](../../SfbServer/management-tools/use-scom-management-pack/configure-the-primary.md)。 为此，必须安装 System Center Operations Manager 2012 SP1 或 R2。 
  
 确定并[配置将受监视的 Skype For Business 服务器计算机](../../SfbServer/management-tools/use-scom-management-pack/configure-computers-to-monitor.md)。 若要使用 System Center Operations Manager 监视 Skype for business Server 计算机，必须安装 System Center Operations Manager 代理文件，并将每台服务器配置为充当代理。 
  
 确定并[安装和配置观察程序节点](../../SfbServer/management-tools/use-scom-management-pack/watcher-nodes.md)。 观察程序节点是定期运行 Skype for business Server 综合事务的计算机—验证密钥 Skype for Business Server 组件的 Windows PowerShell cmdlet，如登录到系统或 exchange 即时的能力邮件按预期方式工作。 
  
## <a name="system-center-operations-manager-root-management-server-and-agent-support"></a>System Center Operations Manager 根管理服务器和代理支持

管理包可用于 System Center Operations Manager 2007 R2 （64-bit）（仅支持迁移目的）或 System Center Operations Manager 2012 SP1 &amp; R2 （64-bit）。 下表显示了适用于 Skype for business Server 2019 的管理包的受支持的配置： 
  
|**配置**|**是否受支持？**|
|:-----|:-----|
|Windows Server 2008 R2 操作系统  <br/> Windows Server 2012 R2 操作系统  <br/> |是。 在 Skype for Business Server 2019 服务器和综合事务观察程序节点上。  <br/> |
|群集服务器  <br/> |不支持。  <br/> |
|无代理监控  <br/> |不支持。  <br/> |
|虚拟环境  <br/> |是。  <br/> |
|加入域的服务器角色  <br/> |所有内部 Skype for business Server 2019 服务器角色必须加入域。  <br/> |
|独立服务器角色  <br/> |Skype for Business Server 2019 边缘服务器不需要加入域。  <br/> |
|拓扑限制  <br/> |必须从同一个 Operations Manager 管理组监视部署中的所有服务器角色。  <br/> |
|综合事务观察程序节点  <br/> |支持使用综合事务观察程序节点监视方案可用性（需要其他配置）。 不需要将观察程序节点加入域。  <br/> |
   
下表显示了综合事务观察程序节点的容量和操作系统要求：
  
|**硬件组件**|**最低要求**|
|:-----|:-----|
|CPU  <br/> |下列一种含义：  <br/> 64位处理器、四核、2.33 GHz 或更高版本  <br/> 64位双处理器、双核、2.33 GHz 或更高版本  <br/> |
|内存  <br/> |8 GB  <br/> |
|操作系统  <br/> |Windows Server 2008 R2  <br/> Windows Server 2012 R2  <br/> |
|网络  <br/> |1 Gbps 网络适配器  <br/> |
   
## <a name="prerequisites"></a>先决条件

若要运行综合事务观察程序节点，必须先安装以下各项：
  
- System Center Operations Manager 代理 
    
-  Microsoft .NET Framework 4.5
    
- Skype for business Server core 安装文件（OcsCore）和统一通信托管 API （UCMA）（版本必须与 Skype for Business Server Watchernode.msi 版本相匹配）
    
## <a name="files-in-this-monitoring-pack"></a>此监视包中的文件

Skype for Business Server 2019 的监视包包括以下文件：
  
- Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp
    
- Microsoft.LS.2019.Monitoring.ComponentAndUser.mp
    
- Watchernode.msi
    
## <a name="whats-new"></a>新增功能

以下功能是 Skype for business Server 2019 管理包中新增的功能。

- ** [9 月2019更新](https://www.microsoft.com/download/details.aspx?id=57511)中的更改**某些警报已删除特殊字符。 在某些情况下，特殊字符会干扰 SCOM 命令通道通知功能。

- **客户端登录的自动发现**登录到 Skype for business Server 2019 的客户端应用程序通常会自动发现要登录到的服务器。 综合事务现在支持验证是否正确配置了自动发现。
    
- **自定义的综合事务运行间隔**为了简化观察程序节点的设置过程，综合事务可以共享用户帐户。 这将降低测试在对测试进行序列化时运行的频率，以避免冲突。 默认情况下，综合事务每15分钟运行一次，以确保所有测试都有时间运行。 选择对每个用户使用更多用户或较少的测试的管理员现在可能还会减少运行时间间隔。
    
- **视频互操作服务综合事务**从其他供应商解决方案迁移到 Skype for business Server 2019 的客户通常希望继续使用来自这些其他供应商的视频电话会议设备（Vtc）。 视频互操作服务器是一种新的 Skype for Business Server 2019 服务器角色，通过视频 SIP 中继连接到 Cisco CUCM，客户可以继续使用其会议室中的 Cisco Vtc。 此功能还添加了一个综合事务，以帮助验证视频互操作性服务器是否正常运行，并能够处理通过视频 SIP 中继传入的连接。
    
- **应用程序共享会议综合事务**现在支持对应用程序共享会议进行端到端方案验证。
    
## <a name="monitoring-scenarios"></a>监视方案

Skype for Business Server 2019 管理包利用多种功能来帮助您检测和诊断问题。 这些功能为 Skype for business Server 2019 环境的运行状况提供实时可见性。
  
|**监视方案**|**说明**|
|:-----|:-----|
|综合事务  <br/> | 用于测试的 Windows PowerShell cmdlet，并帮助确保方案（如登录、状态、IM 和会议）的高可用性。 <br/> 综合事务可从任何地理位置运行，包括企业内部、企业外部和分支机构。  <br/> 当综合事务失败时，将创建 HTML 日志 s 以帮助确定故障的确切性质。 这包括了解哪些操作失败、每个操作的延迟、用于运行测试的命令行以及所发生的特定错误。  <br/> |
|呼叫可靠性警报  <br/> |由 Skype for Business Server 2019 服务器编写的呼叫详细信息记录（Cdr）反映了用户是否能够连接到呼叫或终止呼叫的原因。 呼叫可靠性警报查询 CDR 数据库，以生成警报，这些警报指出当大量用户遇到对等呼叫或基本会议功能的连接问题时。  <br/> 方案覆盖范围包括音频呼叫、对等即时消息（IM）和其他会议功能。  <br/> |
|媒体质量警报  <br/> |在每次呼叫结束时，查看由 Skype for Business Server 2019 客户端发布的体验质量（QoE）报告的数据库查询。 这些查询会生成警报，以确定用户最有可能在呼叫和会议期间遇到受损媒体质量的情况。 数据基于关键指标（如数据包延迟和丢失）构建，这将直接影响用户体验的质量。  <br/> |
|组件运行状况警报  <br/> |各个服务器组件通过事件日志和性能计数器引发警报，以指示可能会对用户方案产生重大影响的故障条件。 这些警报指示各种条件，如未运行的服务、高故障率、高邮件延迟或连接问题。  <br/> |
|依赖项运行状况监视  <br/> |由于各种外部原因，Skype for Business Server 可能会失败。 管理包监视和收集可指示严重问题的关键外部依赖项的数据。 这些依赖项包括 Internet Information Services （IIS）可用性以及用于 Skype for business Server 的服务器的 CPU。  <br/> |
   
### <a name="alert-prioritization"></a>警报优先级

警报分为以下几类： 
  
 **高优先级警报：** 这些警报表示为大型用户组导致服务中断并需要立即执行操作的条件。 综合事务和脱机服务（如 Skype for Business Server 音频/视频会议）检测到的中断将成为高优先级警报。 相比之下，单个计算机上的组件故障不是高优先级的警报。 Skype for Business Server 2019 在这些情况下具有内置的高可用性功能—例如，在负载平衡器背后的多台前端服务器。
  
 **中优先级警报：** 这些警报表示影响用户子集或指示呼叫质量问题的条件，例如，组件故障、呼叫中的延迟或呼叫中较低的音频质量等。 此类别中的警报是有状态的（即，警报的性质根据网络连接的状态变化。）例如，如果呼叫建立时间指示延迟但又返回到正常阈值，则在 System Center Operations Manager 中将自动解决此中等优先级警报，管理员无需执行操作。 无法自动解析的警报通常由管理员在同一工作日解决。
  
 **其他警报：** 这些警报是从可能影响特定用户或用户子集的组件生成的。 例如，一个典型的警报是通讯簿服务无法分析用户： testuser@contoso.com 的 Active Directory®域服务（AD DS）条目。 当用户有时间可用时，管理员可以解决这些警报。
  
### <a name="synthetic-transactions"></a>综合事务

Skype for Business Server 2019 管理包通过综合事务提供了更多的警报覆盖范围。 综合事务是集成到 Operations Manager 管理包中以测试端到端用户方案的 Windows PowerShell cmdlet。 当您指定服务器以执行综合事务时，管理包将定期触发这些 cmdlet。 由综合事务生成状态警报导致的故障。 以下是 Skype for business Server 2019 的受支持的综合事务：
  
**注册、状态和联系人的受支持的综合事务**

||||
|:-----|:-----|:-----|
|1  <br/> |注册（用户登录）  <br/> |可用的 Lync Server 2010 及更高版本  <br/> |
|双面  <br/> |通讯簿服务（文件下载）  <br/> |可用的 Lync Server 2010 及更高版本  <br/> |
|第三章  <br/> |通讯簿 Web 查询  <br/> |可用的 Lync Server 2010 及更高版本  <br/> |
|4  <br/> |状态  <br/> |可用的 Lync Server 2010 及更高版本  <br/> |
|5  <br/> |统一联系人存储  <br/> |可用的 Lync Server 2013 及更高版本  <br/> |
   
**对等服务的受支持的综合事务**

||||
|:-----|:-----|:-----|
|6   <br/> |对等即时消息  <br/> |在 Lync Server 2010 和更高版本中可用  <br/> |
|7   <br/> |对等音频视频  <br/> |在 Lync Server 2010 和更高版本中可用  <br/> |
|8   <br/> |MCX 对等即时消息（移动）  <br/> |在2011年9月发布的 Lync Server 2010 发布到 Skype for Business 2019  <br/> |
 
> [!NOTE]
> Skype for Business Server 2019 中不再提供对旧版移动客户端的 MCX （移动服务）支持。 所有当前 Skype for Business 移动客户端都已使用统一通信 Web API （UCWA）来支持即时消息（IM）、状态和联系人。 具有使用 MCX 的旧版客户端的用户将需要升级到当前客户端。
  
**支持的会议和持久聊天综合事务**

||||
|:-----|:-----|:-----|
|9   <br/> |音频视频会议  <br/> |在 Lync Server 2010 和更高版本中可用  <br/> |
|10   <br/> |数据会议  <br/> |在 Lync Server 2013 和更高版本中可用  <br/> |
|11   <br/> |即时消息会议  <br/> |在 Lync Server 2010 和更高版本中可用  <br/> |
|12  <br/> | 持久聊天 <br/> |在 Lync Server 2013 和更高版本中可用  <br/> |
|13   <br/> |联接启动程序（计划会议）  <br/> |在 Lync Server 2013 和更高版本中可用  <br/> |
|14   <br/> |电话拨入式会议  <br/> |在 Skype for Business Server 2015 及更高版本中可用 <br/> |
|15   <br/> |应用程序共享会议  <br/> |在 Skype for Business Server 2015 及更高版本中可用 <br/> |
|16   <br/> |UCWA 会议（web 会议加入）  <br/> |在 Skype for Business Server 2015 及更高版本中可用 <br/> |
   
**支持的网络和合作伙伴依赖项综合事务**

||||
|:-----|:-----|:-----|
|17   <br/> |AV 边缘连接  <br/> |在 Lync Server 2013 和更高版本中可用  <br/> |
|18   <br/> |AV 边缘连接 Exchange 统一消息连接（语音邮件）  <br/> |在 Lync Server 2013 和更高版本中可用  <br/> |
|合  <br/> |PSTN 对等呼叫  <br/> |在 Lync Server 2010 和更高版本中可用  <br/> |
|20  <br/> |XMPP 即时消息（联合）  <br/> |在 Lync Server 2013 和更高版本中可用  <br/> |
|不足  <br/> |视频互操作服务器  <br/> |在 Skype for Business Server 2015 及更高版本中可用  <br/> |
   
## <a name="how-health-rolls-up"></a>运行状况的汇总方式

下表显示了 Skype for business Server 监视包中的对象的运行状况状态。
  
|**管理包对象**|**说明**|
|:-----|:-----|
|Skype for Business Server 部署  <br/> |表示组织中 Skype for Business Server 2019 的部署。  <br/> |
|Skype for Business Server 网站  <br/> |表示部署服务的不同地理位置。  <br/> |
|Skype for Business Server 池  <br/> |向用户提供通信服务（如即时消息和会议）的池（在网站内）。 适用于前端池、边缘池和控制器池，即使在给定池中只有一台计算机也是如此。  <br/> |
|Skype for Business Server 角色  <br/> |承载 Skype for Business Server 服务的服务器角色。  <br/> |
|Skype for Business Server 服务  <br/> |表示在特定计算机上部署的功能（例如，fp01.contoso.com 上的 user service）。  <br/> |
|Skype for Business Server 组件  <br/> |服务的组件（例如，通讯簿下载组件是 Web 服务的一部分）。  <br/> |
|Skype for Business Server 池观察程序  <br/> |针对一个池运行的综合事务的实例。  <br/> |
|Skype for Business Server 注册程序观察程序  <br/> |对一个注册器池运行的综合事务的实例。  <br/> |
|Skype for Business Server 用户服务池观察程序  <br/> |对一个用户服务池运行的综合事务的实例。  <br/> |
|Skype for Business Server 语音池观察程序  <br/> |对一个语音池运行的综合事务的实例。  <br/> |
|Skype for Business Server 端口观察程序  <br/> |对一个池运行的端口检查的实例。  <br/> |
|简单 URL 观察程序  <br/> |对部署中配置的简单 Url 执行 HTTPS 探测。  <br/> |
   
![SCOM 汇总](../../SfbServer/media/de16195d-3aed-412e-9def-07a481d2ff0f.png)
  
Skype for Business Server 池可以包含多个单独的 Skype for business server 系统（具有多个 Skype for business server 角色、Skype for Business Server 服务和 Skype for Business Server 组件）。 因此，单个服务器或组件的故障对 Skype for Business Server 池的整体运行状况不太关键，因为同一池中的其他服务器可以向客户端提供应用程序服务。 运行状况将按百分比级别汇总到 Skype for Business Server 池。 
  
Skype for Business Server 池观察程序对 Skype for business Server 池执行综合事务。 一个或多个综合事务（称为连续轮询间隔的过程）的连续失败将把严重运行状况状态汇总到池级别（任何合成事务的最差），如下图所示。 
  
![SCOM 汇总连续轮询](../../SfbServer/media/655de542-cca7-4eda-8052-9a7703ecd0e9.png)
  
## <a name="best-practice-create-a-management-pack-for-customizations"></a>最佳实践：创建自定义项的管理包

默认情况下，Operations Manager 会保存所有自定义项，如对默认管理包的替代。 作为最佳实践，应为要自定义的每个密封管理包创建单独的管理包。 
  
创建用于存储密封管理包的自定义设置的管理包时，我们建议相应地命名新管理包，如 "Skype for Business Server 2019 自定义项"。
  
创建用于存储每个密封管理包的自定义项的新管理包，可以更轻松地将自定义项从测试环境导出到生产环境。 这也使您可以更轻松地删除管理包，因为在删除管理包之前，必须删除任何依赖项。 如果在默认管理包中保存了所有管理包的自定义项，并且您需要删除一个管理包，则必须首先删除默认管理包，后者也会删除对其他管理包的自定义项。 
  
## <a name="links"></a>链接

以下链接连接到有关与 System Center 2012 监视包关联的常见任务的信息：
  
- [管理包生命周期](https://technet.microsoft.com/library/hh212732.aspx)
    
- [如何在 Operations Manager 2012 中导入管理包](https://technet.microsoft.com/library/hh212691.aspx)
    
- [如何覆盖规则或监视器](https://technet.microsoft.com/library/hh212869.aspx)
    
- [如何在 Operations Manager 2012 中创建运行方式帐户](https://technet.microsoft.com/library/hh321655.aspx)
    
- [管理运行方式帐户和配置文件](https://technet.microsoft.com/library/hh212714.aspx)
    
- [如何导出 Operations Manager 管理包](https://technet.microsoft.com/library/hh320149.aspx)
    
- [如何删除 Operations Manager 管理包](https://technet.microsoft.com/library/hh230746.aspx)
    
以下链接连接到有关与 System Center 2007 监视包关联的常见任务的信息：
  
- [管理管理包生命周期](https://go.microsoft.com/fwlink/p/?LinkId=211463)
    
- [如何在 Operations Manager 2007 中导入管理包](https://go.microsoft.com/fwlink/p/?LinkID=142351)
    
- [如何使用替代进行监视](https://go.microsoft.com/fwlink/p/?LinkID=117777)
    
- [如何在 Operations Manager 2007 中创建运行方式帐户](https://go.microsoft.com/fwlink/p/?LinkID=165410)
    
- [如何修改现有的运行方式配置文件](https://go.microsoft.com/fwlink/p/?LinkID=165412)
    
- [如何导出管理包自定义项](https://go.microsoft.com/fwlink/p/?LinkId=209940)
    
- [如何删除管理包](https://go.microsoft.com/fwlink/p/?LinkId=209941)
    
有关 Operations Manager 和监视包的问题，请参阅[System Center Operations Manager 社区论坛](https://go.microsoft.com/fwlink/p/?LinkID=179635)。
  
[System Center Operations Manager Unleashed](https://opsmgrunleashed.wordpress.com/)博客是一种有用的资源，其中包含特定监视包的 "示例" 公告。
  
有关 Operations Manager 的其他信息，请参阅以下博客： 
  
- [Operations Manager 团队博客](https://blogs.technet.com/momteam/default.aspx)
    
- [古柯 Holman 的 OpsMgr 博客](https://blogs.technet.com/kevinholman/default.aspx)
    
- [有关 OpsMgr 的想法](https://thoughtsonopsmgr.blogspot.com/)
    
- [Raphael Burri 的博客](https://rburri.wordpress.com/)
    
- [BWren 的管理空间](https://blogs.technet.com/brianwren/default.aspx)
    
- [Ops Mgr + +](https://blogs.msdn.com/boris_yanushpolsky/default.aspx)
    
> [!IMPORTANT]
> 非 Microsoft 网站上的所有信息和内容由所有者或网站的用户提供。 对于本网站中的信息，Microsoft 不做任何明示、暗示或法定的担保。 
  
## <a name="see-also"></a>另请参阅

[Skype for Business Server 2019 管理工具](../management-tools-2019.md)
