---
title: 媒体质量和网络连接性能
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mpottier, dougand
ms.topic: article
ms.assetid: 5fe3e01b-34cf-44e0-b897-b0b2a83f0917
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Optimization
description: 本主题定义的业务联机服务 Skype 的网络性能要求集和如何您可以选择业务 online 网络和 Skype 之间的连接使用的 Internet 或 ExpressRoute 基于您的网络的评估连接。 如果您已决定专用连接到 Office 365 部署 Azure ExpressRoute，本文还如何规划中的业务 Online 部署方案的不同 Skype ExpressRoute 连接提供指导。
ms.openlocfilehash: 00d77bc72cbfd99d496bf458e008cce3da7970c3
ms.sourcegitcommit: 7d65eafd5b0163ece91deb7801458c7a45fcc4f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2018
ms.locfileid: "25839122"
---
# <a name="media-quality-and-network-connectivity-performance-in-skype-for-business-online"></a>Skype for Business Online 中的媒体质量和网络连接性能

本主题定义的业务联机服务 Skype 的网络性能要求集和如何您可以选择业务 online 网络和 Skype 之间的连接使用的 Internet 或 ExpressRoute 基于您的网络的评估连接。 如果您已决定专用连接到 Office 365 部署 Azure ExpressRoute，本文还如何规划中的业务 Online 部署方案的不同 Skype ExpressRoute 连接提供指导。
  
Ip 电话 （音频、 视频和应用程序共享） 实时媒体质量极大地受到的端到端网络连接质量。 为获得最佳的 Skype for Business Online 媒体质量，确保公司网络与 Skype for Business Online 之间的高质量连接很重要。 实现这一目标的最佳做法是基于网络容量设置内部网络和云连接，以便所有连接都可以承受 Skype for Business Online 的高峰流量。
  
Azure ExpressRoute 不包括 Skype 业务 online 的 Office 365 服务的要求。 不过，Azure ExpressRoute 是部署之一可用的选项，将帮助确保连接到 Office 365 满足业务网络性能要求 Skype，并确保最佳 Skype 业务联机媒体用户体验质量。
  
> [!TIP]
> 尽管本主题为您提供了整个网络性能的指导，完成网络评估指南是本文档的范围之外。 若要查找联机业务合作伙伴可帮助您的网络性能度量彻底和完成网络评估的一部分的 Skype 的列表，请访问[业务合作伙伴解决方案的 Skype](http://partnersolutions.skypeforbusiness.com/)。 
  
## <a name="network-connectivity-requirements-to-skype-for-business-online"></a>Skype 到业务 online 的网络连接要求

### <a name="factors-that-impact-skype-for-business-online-media-quality"></a>影响 Skype 业务联机媒体质量的因素

有许多不同的因素包括所使用的设备的业务联机实时 （音频、 视频和应用程序共享） 的媒体质量、 环境和网络连接参与 Skype 的。 
  
#### <a name="devices"></a>设备

在实时的媒体会话中，媒体捕获和呈现设备所使用的所有参与者，如耳机和网络摄像机太大影响总体音频和视频质量。 低品质设备和错误的设备驱动程序会降低整体的音频声音质量和视频图像质量。 另一方面，经认证的设备或高品质设备有助于消除回声、过滤噪音、提高视频分辨率并减少延迟。
  
尽管认证音频和视频媒体设备不是必需的但强烈建议设备认证 for Business 的 Skype 获得最优的媒体体验。 有关所有 Skype for Business 的列表认证的设备，请参阅[电话和设备 for Business 的 Skype](https://technet.microsoft.com/en-us/office/dn947482)。 您可以使用[业务联机呼叫质量仪表板的 Skype](/microsoftteams/turning-on-and-using-call-quality-dashboard)、 位于**业务管理 Skype 中心**，以确认正在使用的设备能否正常工作和监视音频和视频媒体质量。
  
> [!TIP]
> **已认证的设备所需的业务媒体质量体验最最佳 Skype**。
  
务必要记住任何媒体设备、 业务客户端的 Skype 和 Skype 通过哪些实时的媒体流的业务服务器引入一些量延迟。 设备和处理延迟，以及网络延迟的软件上有很大的影响，并参与的端到端总体延迟和最终用户的体验。
  
#### <a name="environment"></a>环境

用户会面及使用音频和视频设备的环境及周边区域是另一个影响音频和视频质量的重要因素。用户在嘈杂的环境中通话会产生回声和含混不清的音频。用户在黑暗或低光照环境中则无法生成明亮清晰的视频图像画质。在会议室设置中，麦克风和视频设备的位置对参与者接收的声音和图像质量有直接影响。
  
若要获取用户的音频和视频体验使用清楚地 Skype 业务应用程序**工具** > **选项** > **音频设备**或**视频设备**更改中使用的设备和自定义其设置。

#### <a name="network"></a>网络

通过 IP 网络实时的媒体质量是会显著影响质量的网络连接，但是尤其是由量：
  
- **延迟**这是获得 IP 数据包到网络上的点 B 点 A 所花费的时间。 实际上，此网络传播延迟被限制到物理距离的两个点和轻量，包括之间执行各种路由器的额外开销的速度。 延迟被按单向或往返时间 (RTT)。
    
- **数据包丢失**这通常被指在给定的时间窗口中丢失数据包的百分比。 数据包丢失直接影响音频质量 — 个人小，从丢失数据包无几乎没有任何影响，导致音频剪切出完整的背对背脉冲损失。
    
- **间数据包到达抖动或只需抖动**这是连续的数据包之间的延迟的平均更改。 最先进的 VoIP 软件包括 for Business 的 Skype 可以适应通过缓冲抖动某些级别。 则只有当抖动超过缓冲参与者会注意到的抖动效果。
    
> [!NOTE]
>  抖动缓冲会增加的端到端延迟。
  
与业务联机实时的媒体会话，以及其他 Office 365 服务和其他业务应用程序生成的其他网络流量的多个并发 Skype，确保没有足够带宽的整个网络路径上的业务 Online 服务，关键以避免网络拥塞，并确保最佳媒体 （音频、 视频和应用程序共享） 的实时媒体质量，您的网络连接到 Skype。 
  
#### <a name="implementing-quality-of-service-qos-across-congested-networks"></a>实现跨网络拥塞的服务质量 (QoS)

此外，通过网络流量拥塞将会显著影响媒体质量。 若要允许更快地通过网络进行传播以及它们优先于其他网络流量拥塞网络中的音频和视频数据包，可以使用服务质量 (QoS) 有助于提供最佳的最终用户体验的音频和视频通信。
  
QoS 提供一种方法，将执行音频或视频的数据的网络数据包分配更高的优先级。 通过向这些数据包分配更高的优先级，音频和视频通信都有可能通过网络传输速度，和较少中断，比网络会话涉及等文件传输、 web 浏览，或数据库进行备份。 这是因为网络数据包用于文件传输或默认情况下的数据库备份为优先级分配"最大努力"和网络拥塞不具有大型影响。 如果不为 （音频、 视频和应用程序共享） 的媒体数据包分配更高的优先级，并将它们作为"最大努力"还分配，它们太将处理以及所有其他网络流量。 根据网络拥塞量，这将可能最终用户降低总体音频和视频质量体验。
  
强烈建议您实现以确保您的网络内的网络拥塞都不会有影响网络上的 QoS。 但是，使此选项的最大的影响，所有网络终结点必须支持 QoS、 所有终结点必须遵守 QoS 标记的含义和数据包的优先顺序。 业务在线服务的 Skype 排定 QoS 标记和 Microsoft 网络中的优先顺序。 但是，通过公共例如公司网络从 Internet 到 Microsoft 网络连接路由的流量不保留 QoS 标记和数据包的优先顺序。 从您的网络的专用连接到 Office 365 使用[Azure ExpressRoute](https://azure.microsoft.com/services/expressroute/)面向最终用户提供的部署解决方案的保留 QoS 标记和数据包的优先顺序的反过来总体增加音频和视频质量。
  
## <a name="network-performance-requirements-to-connect-to-skype-for-business-online"></a>网络性能要求，以连接到 Skype 业务 online
<a name="bkNetworkPerf"> </a>

Skype 业务实时媒体传输通过许多不同的设备、 客户端应用程序、 服务器软件和跨不同的网络。 实时媒体的端到端延迟是延迟的总量的所有组件和网络段都引入。 端到端网络连接质量取决于最差的质量的网络段。 这一段作为此网络流量的瓶颈。
  
下图说明了到另一个业务参与者 Skype 从会议中的单向音频流。
  
![ExpressRoute 呼叫流。](../images/c026e8e5-ba09-42c0-9e03-60fbfda1cb02.png)
  
在此会议方案中的媒体路径跨以下网络段包括：
  
1. **用户 1 到 Microsoft 网络边缘的连接**这通常包括如 WiFi 或以太网、 Internet 出口点 （您的网络边缘设备），与用户 1 之间的 WAN 连接和从您的网络边缘到 Microsoft 网络边缘的 Internet 连接的网络连接。
    
2. **Microsoft 网络中的连接**这是之间的业务 Online 数据中心，Microsoft 边缘到 Skype 其中 A / V 会议服务器使用。
    
3. **Microsoft 网络中的连接**这是业务 Online 数据中心的 Skype 和 Microsoft 网络边缘之间。
    
4. **从 Microsoft 网络边缘到用户 2 的连接**这包括从您的网络边缘到 Microsoft 网络边缘、 WAN 连接从用户 2 到 Internet 出口点 （您的网络边缘），例如，WiFi 或以太网网络连接的 Internet 连接。
    
下图显示细分的组件和网络段的 Skype 业务联机 PSTN 呼叫：
  
![ExpressRoute PSTN 运营商呼叫流。](../images/768a88df-c8a9-4171-a158-565a698f0193.png)
  
在 PSTN 呼叫方案中的媒体路径交叉以下网络段：
  
1. **从业务客户端呼叫者到 Microsoft 网络边缘 Skype 连接**这通常包括如 WiFi 或以太网、 业务客户端呼叫者的 Skype WAN 连接至 Internet 出口点 （您的网络边缘设备） 和从您的网络边缘到 Microsoft 网络边缘的 Internet 连接的网络连接。
    
2. **Microsoft 网络中的连接**这是业务 Online 数据中心，中介服务器的使用位置的 Microsoft 边缘到 Skype 之间。
    
3. **Microsoft 网络中的连接**这是业务 Online 数据中心的 Skype 和 Microsoft 网络边缘之间。
    
4. **Microsoft 网络与 PSTN 服务提供商合作伙伴之间的连接**这是存在放置 Skype 是 Microsoft 网络之外的业务客户端的 PSTN 呼叫的连接。
    
### <a name="network-performance-requirements-from-a-skype-for-business-client-to-microsoft-network-edge"></a>从业务客户端 Skype 与 Microsoft 网络边缘的网络性能要求
<a name="bkSfBClienttoEdge"></a>

对于业务媒体质量的最佳 Skype，以下网络性能指标目标或阈值是需要与 Microsoft 网络边缘从公司网络的连接。 网络的这一段包括您的内部网络，包括所有 WiFi 和以太网连接、 任何公司站点到站点流量通过 WAN 连接，例如多协议标签交换 (MPLS)，以及 Internet 或 ExpressRoute 合作伙伴连接到 Microsoft 网络边缘。
  
> [!CAUTION]
> **连接到 Office 365 服务公司网络上的业务客户端 Skype 之间必须符合这些以下网络性能要求和阈值。**
  
|||
|:-----|:-----|
|**指标** <br/> |**目标** <br/> |
|延迟（单向）  <br/> |< 50 ms  <br/> |
|延迟（RTT 或往返时间）  <br/> |< 100 ms  <br/> |
|突发数据包丢失  <br/> |< 10%，在任何 200 ms 时间间隔内  <br/> |
|数据包丢失  <br/> |< 1%，在任何 15 s 时间间隔内  <br/> |
|数据包中间间隔抖动  <br/> |< 30 ms，在任何 15 s 时间间隔内  <br/> |
|数据包重新排序  <br/> |< 0.05% 无序数据包  <br/> |
   
 **其他性能目标的要求：**
  
- Microsoft 网络具有全球 160 边缘的位置。 我们使用主要 Internet 服务提供商 (Isp) 世界各地的这些边缘网站。 延迟指标目标假定您公司的网站或网站和 Microsoft 边缘位于同一洲。
    
- 您的公司网站或网站添加到 Microsoft 网络边缘连接包含第一个跃点网络访问，可以是 WiFi 或其他无线技术。 
    
- 网络性能目标假定适当的带宽和/或服务规划的质量。 换句话说，此应用于直接业务实时的媒体流量的 Skype 峰值负载下的网络连接时。
    
### <a name="network-performance-requirements-from-your-network-edge-to-microsoft-network-edge"></a>从您的网络边缘到 Microsoft 网络边缘的网络性能要求
<a name="bkYourNetworkEdge"> </a>

以下是网络性能目标或所需的网络边缘和 Microsoft 网络边缘之间的连接的阈值。 网络的这一段排除客户的内部网络或 WAN，并测试您的网络通信的通过 ExpressRoute 合作伙伴网络或 internet 的发送和协商性能时也可以使用时用作指南服务级别协议 (SLA) 您 ExpressRoute 提供程序。
  
> [!CAUTION]
> **公司网络边缘到 Microsoft 网络边缘之间的连接必须符合这些以下网络性能要求和阈值。**
  
|||
|:-----|:-----|
|**指标** <br/> |**目标** <br/> |
|延迟（单向）  <br/> |< 30 ms  <br/> |
|延迟 (RTT)  <br/> |< 60 ms  <br/> |
|突发数据包丢失  <br/> |< 1%，在任何 200 ms 时间间隔内  <br/> |
|数据包丢失  <br/> |< 0.1%，在任何 15 s 时间间隔内  <br/> |
|数据包中间间隔抖动  <br/> |< 15 ms，在任何 15 s 时间间隔内  <br/> |
|数据包重新排序  <br/> |< 0.01% 无序数据包  <br/> |
   
 **其他性能目标的要求：**
  
- 性能目标要求您的公司网络边缘任一和其最近的 Microsoft 网络边缘，可在同一洲之间的连接。
    
- 网络性能目标假定适当的带宽和/或服务规划的质量。 这也适用于 Skype 的业务实时的媒体流量的网络连接时峰值负载下。 正确的带宽和 QoS 规划，请参阅[ExpressRoute 和 Skype 业务 online 中的 QoS](https://support.office.com/en-us/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d?ui=en-US&amp;rs=en-US&amp;ad=US)。
    
## <a name="measuring-network-performance"></a>测量网络性能
<a name="bkNetworkPerf"> </a>

来测量实际网络性能，尤其是对于延迟和数据包丢失，从网络边缘，任何公司网络站点可以使用如 ping 的工具、 测试针对一 Skype 业务媒体中继运行的服务从 Microsoft 边缘和数据中心网站。 
  
测试 Internet 连接到 Microsoft 网络，建议您测试针对以下业务媒体中继的 Skype 的 Vip。 *任意广播 VIP*将解析为 IP 地址的媒体中继中测试位置最接近的 Microsoft 网络边缘网站。
  
||||
|:-----|:-----|:-----|
|**IP 地址** <br/> |**类型** <br/> |**位置** <br/> |
|13.107.8.2  <br/> |VIP  <br/> |世界范围的任何广播 IP  <br/> |
   
 **下面是一些高级别的建议，需遵循的评估网络性能：**
  
- 您应该评估内部网络，以及与 Office 365 的连接。
    
- 您应评估和长的一段时间所有网络收集数据。 我们建议您要执行的一周，最少的网络性能测试，以便您可以看到所有业务日期和时间的使用模式的。 这将显示高峰时间。
    
- 应采取网络性能度量的多个的示例。 我们建议在整个时间段内要收集数据从公司网站学习度量间隔为 10 分钟。 用于比较业务联机网络性能要求 Skype，采用值的 90%度量从该示例数据集。 
    
- 您应该持续评估网络的性能。 网络利用率不同时间由于使用模式更改、 新的基于企业应用程序使用大量的带宽，并更改您的组织或物理公司位置发生变化。 很重要，用于持续监视您对这些网络性能要求和目标/阈值的网络性能和进行及时调整，以确保最佳的实时的媒体质量。 
    
## <a name="measuring-network-performance-using-azure-vms"></a>使用 Azure 虚拟机的测量网络性能
<a name="bkNetworkPerf"> </a>

而不是测试针对 Microsoft 网络边缘站点有从 Skype 业务客户和合作伙伴使用测试安装的 Microsoft Azure 云服务的网络评估解决方案。 在这些解决方案，网络评估工具测试延迟，数据包丢失和抖动针对 Azure 云中作为服务设置的自定义终结点。 因此，测试网络流量经由一个其他网络段，它是 Microsoft 网络之间的网络边缘内部连接和 Azure 数据中心承载的网络评估服务。
  
这些网络评估解决方案基于 Azure 上托管的测试服务。 我们建议执行网络评估国家/地区和/或区域中。 例如，对于在东部美国的客户网站，评估应执行针对 Azure 的 east 美国数据中心区域中承载的测试服务实例。 
  
下面是基于 Azure 服务网络评估设置 (RTT) 目标延迟。 单向延迟目标将相应的 RTT 目标的一半。 根据所定义的 Skype 媒体中继基于测试的数据包丢失和抖动目标保持不变。
  
|||||
|:-----|:-----|:-----|:-----|
|**客户区域** <br/> |**Azure 区域** <br/> |**网络边缘-Azure 往返时间 (RTT)** <br/> |**您的网站-Azure 往返时间 (RTT)** <br/> |
|管理中心美国  <br/> |管理中心美国  <br/> |99  <br/> |139  <br/> |
|东亚美国  <br/> |东亚美国  <br/> |86  <br/> |126  <br/> |
|美国中北部  <br/> |美国中北部  <br/> |97  <br/> |137  <br/> |
|南中央美国  <br/> |南中央美国  <br/> |94  <br/> |134  <br/> |
|西美国  <br/> |西美国  <br/> |94  <br/> |134  <br/> |
|夏威夷美国  <br/> |西美国  <br/> |116  <br/> |156  <br/> |
|加拿大管理中心  <br/> |加拿大管理中心  <br/> |138  <br/> |178  <br/> |
|加拿大 East  <br/> |加拿大 East  <br/> |131  <br/> |171  <br/> |
|北欧  <br/> |北欧  <br/> |99  <br/> |139  <br/> |
|西欧  <br/> |西欧  <br/> |95  <br/> |135  <br/> |
|中国  <br/> |中国  <br/> |118  <br/> |158  <br/> |
|东南方向亚洲  <br/> |东南方向亚洲  <br/> |97  <br/> |137  <br/> |
|日本 East  <br/> |日本 East  <br/> |111  <br/> |151  <br/> |
|日本西  <br/> |日本西  <br/> |118  <br/> |158  <br/> |
|巴西南  <br/> |巴西南  <br/> |70  <br/> |110  <br/> |
|澳大利亚 East  <br/> |澳大利亚 East  <br/> |124  <br/> |164  <br/> |
|澳大利亚东南方向  <br/> |澳大利亚东南方向  <br/> |124  <br/> |164  <br/> |
|管理中心印度  <br/> |管理中心印度  <br/> |103  <br/> |143  <br/> |
|印度南部  <br/> |印度南部  <br/> |103  <br/> |143  <br/> |
|西印度  <br/> |西印度  <br/> |103  <br/> |143  <br/> |
|中国 East  <br/> |中国 East  <br/> |120  <br/> |160  <br/> |
|中国北美  <br/> |中国北美  <br/> |120  <br/> |160  <br/> |
   
## <a name="media-quality-and-expressroute"></a>媒体质量和 ExpressRoute
<a name="bkNetworkPerf"> </a>

Office 365 的 azure ExpressRoute 是用于连接到 Office 365 的专用的网络连接。 它为客户提供具有控制路径网络通信都采用其 Office 365 的功能。 他们不再需要考虑的不可预知传送出现在 Internet 上的未知运营商、 提供程序和 Isp 其中携带数据。 通过 ExpressRoute 发送的网络流量直接通过 ExpressRoute 伙伴的网络发送给 Microsoft 的网络。 这使客户能够将 Office 365 视为位于与专用连接自己非现场数据中心。
  
Azure ExpressRoute 是可用于所有 Office 365 许可产品。 但是，Azure ExpressRoute Premium 加载项，则需要为 Office 365 启用全局路由。 使用至少 500 座位实现 ExpressRoute 的 office 365 客户可以在任何其他费用获得所需的*ExpressRoute Premium 加载项*。
  
### <a name="is-expressroute-required-for-good-media-quality"></a>良好的媒体质量是否要求 ExpressRoute？

Azure ExpressRoute 不获取最优 Skype 业务联机媒体质量的要求。 是，但是，一部署的选项，帮助您确保您云连接满足业务网络性能目标或阈值 Skype。
  
Office 365 的高性能和安全使用 Internet 的服务。 我们将继续在新安全功能以及区域边缘节点持续改进安全性和性能投资。 Azure ExpressRoute 不包括 Skype 业务 online 的 Office 365 服务的要求。 Azure ExpressRoute 是一种部署可用的选项，将帮助确保连接到 Office 365 满足业务网络性能要求 Skype，并确保最佳 Skype 业务联机媒体质量体验。
  
对于业务联机媒体质量的 Skype，十分重要公司网站和 Microsoft 网络边缘之间的连接满足业务客户端 Skype[网络性能要求与 Microsoft 网络中的性能目标边缘](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge)和网络边缘和 Microsoft 网络边缘之间的连接满足[从您的网络边缘到 Microsoft 网络边缘的网络性能要求](media-quality-and-network-connectivity-performance.md#bkYourNetworkEdge)中的性能目标。  
  
也很重要公司的物理网络连接，包括内部网络和云连接容量容纳峰值媒体流量卷。 Azure ExpressRoute 是将帮助确保联机商业云连接其 Skype 满足所有这些性能要求的客户的多种方式。
  
### <a name="is-expressroute-required-for-voice-quality-sla"></a>语音质量 SLA 是否要求 ExpressRoute？

否，不需要业务联机语音质量 SLA 的 Skype ExpressRoute。 [业务联机语音质量 SLA 的 Skype](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;DocumentTypeId=37)适用于发出任何 Skype 业务 Online 中的正确的许可证和订阅，使该用户做出任何类型的 VoIP 或 PSTN 呼叫的语音服务用户的任何合格呼叫。 语音质量 SLA 应包括以下条件的所有所述：
  
- 呼叫来自 Microsoft 认证的 IP 电话。
    
- 有线以太网连接。
    
- 由于 Microsoft 网络问题的语音质量问题。
    
> [!NOTE]
> 语音质量 SLA 排除其中的低的呼叫质量由包括 ExpressRoute 合作伙伴和其他网络的非 Microsoft 网络中的问题导致这些呼叫。 
  
### <a name="internet-or-azure-expressroute"></a>Internet 或 Azure ExpressRoute？

决定在网络连接选项对 Skype 业务 online 之前, 必须评估客户，他们的网络和基于到[网络性能要求中所述的网络性能要求的当前 Internet 连接连接到 Skype 业务 online](media-quality-and-network-connectivity-performance.md#bkNetworkPerf)。
  
如果通过当前的 Internet 连接的网络性能设为期间高峰时间和足够容量满足从网站添加到 Microsoft 网络边缘和 Microsoft 网络边缘到您网络边缘的网络性能要求，则您可以继续使用您现有的 Internet 连接来连接到 Skype 业务 online。
  
对于公司网络性能要求不满足其中网站，我们强烈建议您首先使用您现有网络服务提供程序以提高整个网络性能。 但是，他们仍未被满足，如果使用 Azure ExpressRoute 可以帮助确保您 Skype 业务联机云连接可以帮助您实现网络性能要求。
  
Azure ExpressRoute 提供以下其他好处：
  
- 服务级别协议 (SLA) 可用性的网络和 Microsoft 网络之间的连接。 ExpressRoute 具有为 99.9%保证的可用性 SLA。
    
- 对 Office 365 服务所需的计划和保证带宽。 您可以通过使用 ExpressRoute 业务通信的发送只有 Office 365 流量或 Skype 达到此目的，然后流量通过您的网络的其他 Internet 出口/入口点的所有其他 Internet。
    
- ExpressRoute 旨在保留您的网络和 Microsoft 网络之间的 DSCP QoS 标记。
    
有关 ExpressRoute QoS 和容量规划的详细信息，请参阅[ExpressRoute 和 Skype 业务 online 中的 QoS](https://support.office.com/en-us/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d?ui=en-US&amp;rs=en-US&amp;ad=US)。
  
### <a name="can-i-setup-azure-expressroute-for-skype-for-business-online-only"></a>可以我设置 Azure ExpressRoute Skype 的业务仅限联机状态？

是，您可以设置 Azure ExpressRoute，以确保从公司网络到仅 Skype 的极好的网络连接性业务 online。 这将为您的用户提供最佳的实时的媒体质量，但您可以继续通过 Internet 连接到其他 Office 365 服务。
  
边框网关协议 (BGP) 是用于将网络流量路由 internet Internet 上的路由协议。 它旨在交换找到通过 Internet 自治系统 (AS) 之间的路由信息。 BGP 社区值是可以应用于传入或传出路由属性标记。 BGP 社区通常用于为用于访问给定的目标基于地理位置、 服务类型或其他条件的出站链接接收到信号。
  
与 BGP 社区支持，Microsoft 将使用适当的 BGP 社区值基于其所属的服务标记前缀和路由。 Microsoft 将标记通过公共对等广告前缀和 Microsoft 对等使用适当的 BGP 社区值，该值指示该区域中承载的前缀。 您可以依赖的社区值进行相应的路由决策提供最佳路由。 您只能将 Skype ExpressRoute 连接设置业务联机 BGP 社区值用于 Skype 业务 online。 您可以了解在[ExpressRoute 路由要求](https://azure.microsoft.com/documentation/articles/expressroute-routing/)的详细信息。
  
## <a name="expressroute-connectivity-scenarios-for-skype-for-business-online"></a>Skype 业务 online ExpressRoute 连接方案
<a name="bkNetworkPerf"> </a>

如果您已决定 ExpressRoute 基于上面建议您，下面是在何处的建议和多少 ExpressRoute 连接您应获得。
  
### <a name="online-only-deployment---single-site"></a>联机仅部署-单个网站

如果您的所有用户使用 Skype 业务 Online 服务，并且您的办公室均居中周围单个物理位置和您决定部署 Azure ExpressRoute，您应设置单个 ExpressRoute 连接到最接近您公司的站点之间[ExpressRoute 对等位置](https://azure.microsoft.com/documentation/articles/expressroute-locations/)。
  
下图显示了此类部署的示例。 例如，Contoso 是大学位于奥兰多，市举办。 Contoso 有 10,000 教职员工和学生。 在高峰类中，从其位置对 Microsoft 边缘网站这些 Internet 测试表明大于 5%的数据包丢失。 已决定要获取的专用的连接到 Office 365 具有提供过量带宽使用 ExpressRoute，以便他们可以避免 for Office 365 网络拥塞，尤其是对于业务联机实时通信的 Skype。 他们连接到 Microsoft 云通过 ExpressRoute 佐治亚州 MeetMe 站点。
  
![ExpressRoute 单站点。](../images/59fbca3c-a3ea-4568-8da5-3281096a7453.png)
  
### <a name="online-only-deployment---multiple-sites-on-the-same-continent"></a>Online 仅部署的上同一大陆的多个网站

如果您选择实现 Azure ExpressRoute 贵公司的同一区域或洲中的多间办公室中的业务联机服务使用 Skype，建议您主网站 ExpressRoute，通过连接，然后 （可选） 将添加其他ExpressRoute 不符合建议的网络性能目标其他位置的对等。
  
在以下示例中，Contoso 是美国差旅服务公司总部位于纽约但跨美国具有其他办公室。 他们办公室是间通过 WAN 连接到 Office 365 使用 MPLS 的连接的。 他们最初设置从其 Internet 路由器的 ExpressRoute 连接中 Hoboken，新泽西 New York MeetMe 网站。 
  
使用此设置中，从其网站的最多到 Microsoft 网络 （纽约边缘网站） 的网络流量可以满足业务客户端连接网络性能目标[Skype 业务客户端网络性能要求中所述的 Skype向 Microsoft 网络边缘](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge)。 但是，Contoso 的西海岸办公室到纽约之间的延迟会通过单向 50 毫秒。 此外，Honolulu contoso 的第二大 office，从 Honolulu 纽约的延迟超过 80ms 单向。 若要确保这些办公室中的用户的良好的媒体质量，Contoso 决定将其上海网站和硅谷 ExpressRoute MeetMe 站点之间西海岸 ExpressRoute 连接。
  
![在同一洲 express 路由器多站点。](../images/bf57a473-01e1-4271-9675-385767bc58e1.png)
  
### <a name="online-only-deployment---multiple-sites-on-different-continents"></a>联机仅部署-位于不同大洲的多个站点

如果您的所有用户使用 Skype 进行业务在线服务，并且如果您的办公室是在多个物理位置跨多个大洲，如果您决定部署 Azure ExpressRoute，您应设置为每个大陆的至少一个 ExpressRoute 连接之间为其最接近[ExpressRoute 对等位置](https://azure.microsoft.com/documentation/articles/expressroute-locations/)的每个大陆主网站。 根据成本 vs 好处，您可以选择部署从网络性能目标不满足其中的网站的其他 ExpressRoute 连接。
  
在以下示例中，Contoso 在北美和欧洲是大型企业律师事务所与办公室中主要的城市。 根据他们的 Internet 连接和其内部网络性能评估，Contoso 决定部署在北美和单个 ExpressRoute 电路其所有欧洲办事处的两个 ExpressRoute 连接。
  
![与多个网站和洲 ExpressRoute。](../images/c967550b-dc85-4b37-a7bc-cd825ec86854.png)
  
### <a name="hybrid-deployment"></a>混合部署

如果您具有内部部署 Lync 或业务部署的 Skype 并选择实现混合 Skype 业务联机集成，我们建议您决定部署 Azure ExpressRoute，如果您需要有每个至少一个 ExpressRoute 连接本地 Lync 或 Skype 业务边缘网站和至少一个与办公室的每个大陆 ExpressRoute 连接。 根据成本 vs 收益，对于每个大陆您可以选择部署从网络性能目标不满足其中的办公室的其他 ExpressRoute 连接。
  
如果您有业务部署本地 Skype，您必须遵循的[边缘服务器规划和部署指南](https://technet.microsoft.com/en-us/library/mt346417.aspx)。 具体而言，必须从外部网络上可以访问边缘服务器。 这通常被实现通过将公共可路由 IP 地址分配给边缘服务器，或使用网络地址转换 (NAT)。
  
在以下示例中，Contoso 具有现有的内部部署 Skype 业务企业语音部署。 他们想要将内部部署用户迁移到 Office 365 联机服务。 他们还决定要使用混合部署，以便他们可以继续为所有内部部署和 online 用户使用其现有的 PSTN 基础结构。 Contoso 的本地数据中心和业务边缘服务器的 Skype 处于芝加哥。 对于其部署，Contoso 决定设置其芝加哥数据中心和芝加哥 ExpressRoute 之间的一个 ExpressRoute 连接。 他们还添加西海岸 ExpressRoute 连接更好地为其 Honolulu office 提供服务。
  
![ExpressRoute 混合。](../images/a7467c56-642f-44e5-adfb-ecca91ba2dd3.png)
  
### <a name="online-deployment-with-cloud-connector-edition"></a>与云连接器 Edition online 部署

Skype 业务联机云连接器 edition 是混合提供组成的打包虚拟机 (Vm) 实现内部部署 PSTN 连接的一组。 通过部署虚拟化环境中的企业服务器拓扑最少 Skype，您将能够发送和接收 landlines 与通过现有的内部部署 PSTN 语音基础结构的移动电话的呼叫。
  
如果您决定部署 Azure ExpressRoute 和云连接器 Edition，我们建议为您设置的每个大陆到它的最接近[ExpressRoute 对等位置](https://azure.microsoft.com/documentation/articles/expressroute-locations/)的每个大陆主站点之间的至少一个 Express 路由连接。 根据成本 vs 收益，对于每个大陆您可以选择部署从网络性能目标不满足其中的网站的其他 ExpressRoute 连接。
  
如果您有业务部署本地 Skype，您必须遵循[的商务云连接器版的 Skype 的规划指南](https://technet.microsoft.com/EN-US/library/mt605227.aspx)。 具体而言，访问边缘服务器和 A / V 边缘服务应向其分配公共 IP 地址和从 Office 365 数据中心可访问。
  
在以下示例中，Contoso 是欧洲会计公司与几个主要欧洲国家/地区和城市 （英文） 中的状态。 当他们注册的 Skype 业务 online 所有其协作需求时，他们决定将为每个国家/地区拥有继续使用他们 PSTN 的基础结构的物理位置和已存在的运营商合同云连接器。 根据其测试从其所有网站和 Microsoft 网络边缘，它们确定有助于满足业务客户端连接网络性能目标[网络性能中所述的 Skype 伦敦中的单个 ExpressRoute 连接向 Microsoft Skype 业务客户端要求网络边缘](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge)。
  
![ExpressRoute 云连接器一个。](../images/ebdc96e5-b22a-4bf2-b668-062460b4b890.png)
  
下面是另一个 contoso 的部署选项。 在这种情况下，他们决定要在其中部署云连接器的每个站点设置 ExpressRoute 连接。 
  
![ExpressRoute 云连接器两。](../images/06d967a9-64f5-4d7d-98ed-3f3add1b7c2b.png)
  
## <a name="related-topics"></a>相关主题

[Skype for Business Online 中的 ExpressRoute 和 QoS](expressroute-and-qos-in-skype-for-business-online.md)

  
 