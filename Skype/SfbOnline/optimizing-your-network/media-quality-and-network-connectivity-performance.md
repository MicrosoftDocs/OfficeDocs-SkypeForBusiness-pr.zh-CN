---
title: "媒体质量和网络连接的性能"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mpottier, dougand
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 5fe3e01b-34cf-44e0-b897-b0b2a83f0917
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Optimization
description: "本主题定义的一套商业在线服务 Skype 的网络性能要求和如何选择要用于互联网或 ExpressRoute 网络和 Skype 之间的连接性在线业务基于网络的评估连接性。 如果您已决定部署专用连接到 Office 365 的 Azure ExpressRoute，本文档还如何规划您的 ExpressRoute 连接不同 Skype 的在线业务的部署方案中提供指导。"
ms.openlocfilehash: 7b68253fe44850009639de57eadee2edefeb5e0c
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2018
---
# <a name="media-quality-and-network-connectivity-performance-in-skype-for-business-online"></a>媒体质量和网络连接的性能在 Skype 的在线业务

本主题定义的一套商业在线服务 Skype 的网络性能要求和如何选择要用于互联网或 ExpressRoute 网络和 Skype 之间的连接性在线业务基于网络的评估连接性。 如果您已决定部署专用连接到 Office 365 的 Azure ExpressRoute，本文档还如何规划您的 ExpressRoute 连接不同 Skype 的在线业务的部署方案中提供指导。
  
通过端到端网络连接的质量受到很大影响的基于 IP 的实时媒体 （音频、 视频和应用程序共享） 的质量。 为获得最佳的 Skype for Business Online 媒体质量，确保公司网络与 Skype for Business Online 之间的高质量连接很重要。 实现这一目标的最佳做法是基于网络容量设置内部网络和云连接，以便所有连接都可以承受 Skype for Business Online 的高峰流量。
  
Azure 的 ExpressRoute 不是 Office 365 提供服务包括 Skype 的在线业务的必要条件。 但是，Azure ExpressRoute 是一种部署可用的选项，将帮助确保连接到 Office 365 满足业务网络性能需求的 Skype，并确保最大程度优化 Skype 业务在线媒体质量方面的经验。
  
> [!TIP]
> 尽管本主题为您提供整个网络的性能指南，全面指导网络评估是超出本文的讨论范围。 要查找联机业务合作伙伴可以帮助您的网络性能度量作为详尽而完整的网络评估的一部分的 Skype 的列表，请访问[Skype 业务合作伙伴解决方案](http://partnersolutions.skypeforbusiness.com/)。 
  
## <a name="network-connectivity-requirements-to-skype-for-business-online"></a>对 Skype 的在线业务网络连接要求

### <a name="factors-that-impact-skype-for-business-online-media-quality"></a>影响 Skype 业务联机媒体质量的因素

有许多不同的因素导致 Skype 业务在线实时媒体 （音频、 视频和应用程序共享） 质量，其中包括使用的设备、 环境和网络连接。 
  
#### <a name="devices"></a>设备

在实时媒体会话中，媒体捕获并呈现由耳机和摄像头等的所有参与者使用的设备具有总体的音频和视频质量很大的影响。 低品质设备和错误的设备驱动程序会降低整体的音频声音质量和视频图像质量。 另一方面，经认证的设备或高品质设备有助于消除回声、过滤噪音、提高视频分辨率并减少延迟。
  
尽管认证音频和视频媒体设备不是必需的但强烈建议设备认证，Skype 为企业最优的媒体体验。 有关的所有业务 Skype 列表认证的设备，请参阅[电话和 Skype 的业务的设备](https://technet.microsoft.com/en-us/office/dn947482)。 可以使用[Skype 业务在线呼叫质量的仪表板](../using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard.md)，发现**Skype 业务管理为中心**，在验证中使用的设备正常工作并监视音频和视频媒体质量。
  
> [!TIP]
> **已认证的设备是需要为业务媒体品质体验最佳 Skype**。
  
请务必记住任何媒体设备、 Skype 业务客户和业务服务器的实时媒体流，通过 Skype 引入一定量的滞后时间。 在设备和软件处理延迟、 网络延迟以及上有很大的影响和贡献的端到端整体滞后时间和最终用户的体验。
  
#### <a name="environment"></a>环境

用户会面及使用音频和视频设备的环境及周边区域是另一个影响音频和视频质量的重要因素。用户在嘈杂的环境中通话会产生回声和含混不清的音频。用户在黑暗或低光照环境中则无法生成明亮清晰的视频图像画质。在会议室设置中，麦克风和视频设备的位置对参与者接收的声音和图像质量有直接影响。
  
能够清楚地了解用户的音频和视频体验使用 Skype 为业务应用程序**工具** > **选项** > **音频设备**或**视频设备**中使用的设备中进行更改和自定义的设置。 您还可以通过单击**检查调用质量**检查呼叫的音频质量。 If they click **Check Call Quality**, they can then report the quality and issues found with the test call.
  
![Testing audio in the Skype for Business client.](../images/1730a71e-a09d-4702-8eb6-ef1346a091fa.png)
  
#### <a name="network"></a>网络

质量的网络连接，但是尤其是由量到跨 IP 网络的实时媒体的质量，是受到很大影响：
  
- **滞后时间**这是获得点 A 到点 B 网络 IP 数据包所需的时间。 这种网络传播延迟实质上限制到两个点光源，包括额外的系统开销之间采取的各种路由器的速度之间的物理距离。 滞后时间被指单向或往返时间 (RTT)。
    
- **数据包丢失**这通常被指在给定的时间窗口中丢失的数据包的百分比。 数据包丢失率直接影响语音质量 — — 小，从单个丢失有几乎没有任何影响，导致完整的音频剪切的背对背的突发包丢失的数据包。
    
- **间数据包到达抖动或简单地抖动**这是连续数据包之间的延迟的平均变化。 大多数现代 VoIP 软件包括 Skype 业务可以适应抖动缓冲通过某些级别。 它是抖动的只有当抖动超过缓冲参与者会注意到的影响。
    
> [!NOTE]
>  抖动缓冲将增加端到端延迟。
  
确保与业务在线实时媒体会话，以及由其他 Office 365 提供服务和其他业务应用程序生成的其他网络通信的多个并发 Skype，没有足够的带宽，整个网络路径上的避免网络拥塞，并确保出色的媒体 （音频、 视频和应用程序共享） 的实时媒体质量的关键商业在线服务为 Skype 连接您的网络。 
  
#### <a name="implementing-quality-of-service-qos-across-congested-networks"></a>实现跨拥塞的网络服务质量 (QoS)

此外，网络上的交通拥堵将大大影响媒体质量。 若要允许更快地通过网络进行传播，它们优先于其他网络通信拥塞的网络中的音频和视频数据包，可以使用服务质量 (QoS) 有助于为音频和视频通信提供一种最佳的最终用户的体验。
  
QoS 为提供一种将高优先级分配给将执行音频或视频数据的网络数据包。 通过对这些数据包分配更高的优先级，音频和视频通信很可能会通过网络传输速度更快，和更少的中断，比网络会议，涉及诸如文件传输、 web 浏览，或数据库进行备份。 这是因为用于文件传输的网络数据包或默认的数据库备份为优先级分配"尽心尽力"和网络拥塞问题不会有大的影响。 如果看不到媒体 （音频、 视频和应用程序共享） 数据包分配更高的优先级，并保留还指派为"最大努力"，他们太将处理以及所有其他网络通信。 根据网络拥塞的量，这将有可能最终降低总体音频和视频质量体验您的用户。
  
强烈建议您在您的网络，以确保在您的网络中的网络拥塞问题不会影响实现 QoS。 但是，对此产生大的影响，所有的网络终结点必须支持 QoS、 所有终结点必须服从 QoS 标记的含义和数据包的优先级。 Skype 的在线业务服务排定 QoS 标记和 Microsoft 网络内的优先顺序。 但是，QoS 标记数据包统筹，不能保留路由通过公共连接到 Microsoft 网络与公司网络互联网等的通信。 从网络到使用[Azure ExpressRoute](https://azure.microsoft.com/en-us/services/expressroute/) Office 365 的专用连接的最终用户提供部署解决方案，保留 QoS 标记和数据包优先级划分，进而整体提高音频和视频质量。
  
## <a name="network-performance-requirements-to-connect-to-skype-for-business-online"></a>业务联机连接到 Skype 的网络性能要求
<a name="bkNetworkPerf"> </a>

Skype 业务实时媒体传输许多不同的设备、 客户端应用程序和服务器软件，并对不同网络。 端到端延迟的实时媒体是延迟的引入跨所有组件和网络段的总金额。 端到端网络连接的质量取决于最差质量的网络段。 这一段作为该网络通信的瓶颈。
  
下图阐释了单向音频流到另一个 Skype 业务参与者从会议中。
  
![ExpressRoute 呼叫流。](../images/c026e8e5-ba09-42c0-9e03-60fbfda1cb02.png)
  
此会议方案中，介质路径包含在下面的网络段之间：
  
1. **从用户 1 到 Microsoft 网络边缘的连接**这通常包括如 WiFi 或以太网、 WAN 连接至互联网出口点 （网络边缘设备），用户 1 和 Microsoft 网络边缘从网络边缘的互联网连接的网络连接。
    
2. **在 Microsoft 网络中的连接**这是对 Skype 的在线业务的数据中心，Microsoft 边缘之间，A / V 会议服务器用于。
    
3. **在 Microsoft 网络中的连接**这是 Skype 的在线业务数据中心和 Microsoft 网络边缘之间。
    
4. **从 Microsoft 网络边缘到用户 2 连接**这包括 Microsoft 网络边缘、 WAN 连接到互联网出口点 （网络边缘），用户 2 如 WiFi 或以太网的网络连接从网络边缘的互联网连接。
    
下图显示了分解的组件和业务在线 PSTN 呼叫 Skype 的网络段：
  
![ExpressRoute PSTN 承运人呼叫流。](../images/768a88df-c8a9-4171-a158-565a698f0193.png)
  
在 PSTN 呼叫方案中，介质路径交叉下面网段：
  
1. **从业务到 Microsoft 网络边缘的客户呼叫方的 Skype 连接**这通常包括如 WiFi 或以太网，从业务客户呼叫方的 Skype 的 WAN 连接到互联网出口点 （网络边缘设备），并且 Microsoft 网络边缘从网络边缘的互联网连接的网络连接。
    
2. **在 Microsoft 网络中的连接**这是对 Skype 的在线业务的数据中心，使用中介服务器的位置的 Microsoft 边缘之间。
    
3. **在 Microsoft 网络中的连接**这是 Skype 的在线业务数据中心和 Microsoft 网络边缘之间。
    
4. **Microsoft 网络和 PSTN 服务提供商合作伙伴之间的连接**这是存在可从 Microsoft 网络之外的业务客户端的 Skype PSTN 呼叫连接。
    
### <a name="network-performance-requirements-from-a-skype-for-business-client-to-microsoft-network-edge"></a>从业务客户端的 Skype 的网络性能要求与 Microsoft 网络边缘
<a name="bkSfBClienttoEdge"></a>

对于商业媒体质量的最佳 Skype，以下网络性能度量目标或阈值都需要从您的公司网络连接到 Microsoft 网络边缘。 网络的这一段包括您的内部网络，这包括所有的 WiFi 和以太网连接，任何公司站点对站点通信通过 WAN 连接，例如多协议标签交换 (MPLS)，以及互联网或 ExpressRoute 合作伙伴与 Microsoft 网络边缘的连接。
  
> [!CAUTION]
> **Skype 业务到 Office 365 提供服务的公司网络上的客户端之间的连接必须符合这些以下网络性能要求和阈值。**
  
|||
|:-----|:-----|
|**跃点计数** <br/> |**目标** <br/> |
|滞后时间 （单向）  <br/> |< 50 ms  <br/> |
|滞后时间 （RTT 或往返时间）  <br/> |< 100 ms  <br/> |
|突发数据包丢失  <br/> |< 10%，在任何 200 ms 时间间隔内  <br/> |
|数据包丢失  <br/> |< 1%，在任何 15 s 时间间隔内  <br/> |
|数据包间到达抖动  <br/> |< 30 ms，在任何 15 s 时间间隔内  <br/> |
|数据包重新排序  <br/> |< 0.05% 无序数据包  <br/> |
   
 **其他性能目标的要求：**
  
- Microsoft 网络具有全球范围内超过 160 边缘位置。 我们的工作与主要互联网服务提供商 (Isp) 世界各地的这些边缘站点。 滞后指标目标假定您公司的网站或站点和 Microsoft 边是在同一个洲。
    
- 您的公司网站或与 Microsoft 网络边缘连接的站点包括第一跃点网络访问权限，可以是 WiFi 或其他无线技术。 
    
- 网络性能目标假定适当的带宽和/或服务规划的质量。 换而言之，这对直接业务实时媒体流量的 Skype 在峰值负载下的网络连接时。
    
### <a name="network-performance-requirements-from-your-network-edge-to-microsoft-network-edge"></a>从网络边缘与 Microsoft 网络边缘的网络性能要求
<a name="bkYourNetworkEdge"> </a>

以下是网络性能目标或阈值所需的网络边缘和 Microsoft 网络边缘之间的连接。 网络的这一段不包括客户的内部网络或广域网，并测试您的网络通信通过互联网，或通过 ExpressRoute 合作伙伴网络发送，也可以协商性能时使用时用作指南服务级别协议 (SLA) 与 ExpressRoute 提供商。
  
> [!CAUTION]
> **这些以下网络性能要求和阈值，必须满足公司网络边缘到 Microsoft 网络边缘之间的连接。**
  
|||
|:-----|:-----|
|**跃点计数** <br/> |**目标** <br/> |
|滞后时间 （单向）  <br/> |< 30 ms  <br/> |
|滞后时间 (RTT)  <br/> |< 60 ms  <br/> |
|突发数据包丢失  <br/> |< 1%，在任何 200 ms 时间间隔内  <br/> |
|数据包丢失  <br/> |< 0.1%，在任何 15 s 时间间隔内  <br/> |
|数据包间到达抖动  <br/> |< 15 ms，在任何 15 s 时间间隔内  <br/> |
|数据包重新排序  <br/> |< 0.01% 无序数据包  <br/> |
   
 **其他性能目标的要求：**
  
- 性能目标要求任何公司的网络边缘和其最近的 Microsoft 网络边缘，在同一个洲之间的连接。
    
- 网络性能目标假定适当的带宽和/或服务规划的质量。 这也适用于 Skype 业务实时媒体通信网络连接在峰值负载下时。 适当的带宽和 QoS 规划，请参阅[ExpressRoute 和在 Skype 的在线业务的 QoS](https://support.office.com/en-us/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d?ui=en-US&amp;rs=en-US&amp;ad=US)。
    
## <a name="measuring-network-performance"></a>衡量网络性能
<a name="bkNetworkPerf"> </a>

要测量的实际网络性能，尤其是对于延迟和数据包丢失，任何公司网络站点到网络边缘，从可以使用 ping 工具，Skype 业务媒体中继服务从 Microsoft 边缘和数据运行一组测试中心的网站。 
  
为了测试互联网连接到 Microsoft 网络，建议您针对以下 Vip 业务媒体中继的 Skype 的测试。 *任何广播 VIP*将解析为 IP 地址的媒体中继测试位置最接近的 Microsoft 网络边缘站点中。
  
||||
|:-----|:-----|:-----|
|**IP 地址** <br/> |**类型** <br/> |**位置** <br/> |
|13.107.8.2  <br/> |VIP  <br/> |世界范围的任何广播 IP  <br/> |
   
 **下面是一些高层次的建议所遵循的评估网络性能：**
  
- 您应该评估您的内部网络以及与 Office 365 的连接。
    
- 您应该评估和长的一段时间对所有您的网络中收集数据。 我们建议您执行最少的一周中，对网络性能的测试，以便您可以看到所有工作日和工时的使用模式。 这将显示高峰时间。
    
- 应采取网络性能测量的多个示例。 我们建议在整个时间段内所收集的数据从公司网站采取测量每隔 10 分钟。 为了比较 Skype 的在线业务的网络性能要求，采用值的 90%测量从该示例数据集。 
    
- 您应该不断地评估网络的性能。 网络利用率不同时间由于使用模式更改、 新的基于企业的应用程序使用大量的带宽，并对组织或物理公司位置的更改而发生变化。 很重要的持续监视您的网络性能，针对这些网络性能的要求和目标中的阈值，并进行及时的调整，以确保最大程度优化实时媒体质量。 
    
## <a name="measuring-network-performance-using-azure-vms"></a>使用 Azure Vm 的网络性能测量
<a name="bkNetworkPerf"> </a>

而不是测试针对 Microsoft 网络边缘站点，有从 Skype 的网络评估解决方案业务客户和合作伙伴利用 Microsoft Azure 云服务的测试设置。 在这些解决方案中，网络评估工具测试延迟、 数据包丢失，抖动对在 Azure 云作为一项服务设置的自定义终结点。 因此，测试网络通讯经由一个额外的网络段中，它是 Microsoft 网络之间的网络边缘内连接和 Azure 数据中心承载网络评估服务。
  
对于那些网络评估解决方案基于 Azure 承载测试服务。 我们建议采取国家和/或区域内的网络评估。 例如，对于在东部美国客户站点，评估应执行对 Azure 的东部美国数据中心区域中承载的测试服务实例。 
  
下面是滞后时间 (RTT) 基于 Azure 服务网络评估设置目标。 单向延迟目标将相应的 RTT 目标的一半。 根据所定义的 Skype 媒体中继基于测试数据包丢失和抖动目标保持不变。
  
|||||
|:-----|:-----|:-----|:-----|
|**客户区域** <br/> |**Azure 的地区** <br/> |**网络边缘的 Azure 往返时间 (RTT)** <br/> |**您的站点-Azure 的往返时间 (RTT)** <br/> |
|美国中部  <br/> |美国中部  <br/> |99  <br/> |139  <br/> |
|东亚的美国  <br/> |东亚的美国  <br/> |86  <br/> |126  <br/> |
|美国中北部  <br/> |美国中北部  <br/> |97  <br/> |137  <br/> |
|美国中南部  <br/> |美国中南部  <br/> |94  <br/> |134  <br/> |
|美国西部  <br/> |美国西部  <br/> |94  <br/> |134  <br/> |
|夏威夷美国  <br/> |美国西部  <br/> |116  <br/> |156  <br/> |
|加拿大中部  <br/> |加拿大中部  <br/> |138  <br/> |178  <br/> |
|加拿大东部  <br/> |加拿大东部  <br/> |131  <br/> |171  <br/> |
|北欧  <br/> |北欧  <br/> |99  <br/> |139  <br/> |
|西欧  <br/> |西欧  <br/> |95  <br/> |135  <br/> |
|东亚  <br/> |东亚  <br/> |118  <br/> |158  <br/> |
|东南亚  <br/> |东南亚  <br/> |97  <br/> |137  <br/> |
|日本东  <br/> |日本东  <br/> |111  <br/> |第 151  <br/> |
|日本西部  <br/> |日本西部  <br/> |118  <br/> |158  <br/> |
|巴西南部  <br/> |巴西南部  <br/> |70  <br/> |110  <br/> |
|澳大利亚东部  <br/> |澳大利亚东部  <br/> |124  <br/> |164  <br/> |
|澳大利亚东南部  <br/> |澳大利亚东南部  <br/> |124  <br/> |164  <br/> |
|中央印度  <br/> |中央印度  <br/> |103  <br/> |143  <br/> |
|印度南部  <br/> |印度南部  <br/> |103  <br/> |143  <br/> |
|西部的印度  <br/> |西部的印度  <br/> |103  <br/> |143  <br/> |
|中国东部  <br/> |中国东部  <br/> |120  <br/> |160  <br/> |
|中国北部  <br/> |中国北部  <br/> |120  <br/> |160  <br/> |
   
## <a name="media-quality-and-expressroute"></a>媒体质量和 ExpressRoute
<a name="bkNetworkPerf"> </a>

对于 Office 365 的 azure ExpressRoute 是专用的网络连接连接到 Office 365。 它为客户提供具有网络通信都采用其 Office 365 的路径控制的能力。 他们再也不关心不可预知传送发生在 Internet 上的未知的运营商、 供应商和 Isp 中携带的数据。 通过 ExpressRoute 发送的网络流量 ExpressRoute 合作伙伴的网络上直接发送到 Microsoft 的网络。 这使客户能够将 Office 365 视为位于他们自己异地数据中心使用专用连接。
  
Azure ExpressRoute 仅供所有 Office 365 提供授权服务。 但是，Azure ExpressRoute 高级加载项时需要 Office 365 启用全局路由。 Office 365 客户具有至少 500 户实现 ExpressRoute 可以获得所需的*ExpressRoute 高级加载项*没有额外的费用。
  
### <a name="is-expressroute-required-for-good-media-quality"></a>ExpressRoute 很好的媒体质量的要求？

Azure 的 ExpressRoute 不是获取最优的 Skype 业务联机媒体质量的必要条件。 它是，但是，一个部署的选项，可以帮助您确保云连接满足业务网络性能目标或阈值 Skype。
  
Office 365 具有高性能和安全使用互联网的服务。 我们将继续投资在新的安全功能和区域的边缘节点不断改进安全性和性能。 Azure 的 ExpressRoute 不是 Office 365 提供服务包括 Skype 的在线业务的必要条件。 Azure 的 ExpressRoute 是一个部署的可用选项，将帮助确保连接到 Office 365 提供满足业务网络性能需求的 Skype，并确保业务联机媒体质量最优的 Skype方面的经验。
  
Skype 业务联机媒体质量，是非常重要的您公司的网站和 Microsoft 网络边缘之间的连接满足[的网络性能要求从业务客户端的 Skype 与 Microsoft 网络中的性能目标边缘](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge)和网络边缘和 Microsoft 网络边缘之间的连接满足[网络性能要求从网络边缘到 Microsoft 网络边缘](media-quality-and-network-connectivity-performance.md#bkYourNetworkEdge)中的性能目标。  
  
还有一点您公司的物理网络连接，包括您的内部网络和云连接容量容纳峰值介质流量。 Azure ExpressRoute 是将帮助客户确保其 Skype 业务在线云连接满足所有这些性能要求的多种方式之一。
  
### <a name="is-expressroute-required-for-voice-quality-sla"></a>ExpressRoute 的语音质量 SLA 要求？

不对，ExpressRoute 不是 Skype 业务在线语音质量 SLA 的要求。 [Skype 业务在线语音质量 SLA 为](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;DocumentTypeId=37)适用于通过任何内正确的许可证并使用户可以进行任何 VoIP 或 PSTN 呼叫类型的订阅的在线业务语音服务用户的 Skype 放任何资格调用。 语音质量 SLA 应包括解决所有满足以下条件：
  
- 调用从 Microsoft 认证的 IP 电话。
    
- 有线以太网连接。
    
- 由于 Microsoft 网络问题的语音质量问题。
    
> [!NOTE]
> 语音质量 SLA 不包括这些调用低通话质量由中非 Microsoft 网络包括 ExpressRoute 合作伙伴和其他网络问题。 
  
### <a name="internet-or-azure-expressroute"></a>互联网或 Azure ExpressRoute？

在之前的网络上的决策到 Skype 的在线业务的连接选项，必须评估客户，他们的网络和基于[网络的性能要求与所述的网络性能要求的当前互联网连接将连接到 Skype 的在线业务](media-quality-and-network-connectivity-performance.md#bkNetworkPerf)。
  
如果通过当前的互联网连接的网络性能设置为在高峰时间，足以满足从站点添加到 Microsoft 网络边缘和 Microsoft 网络边缘您网络边缘的网络性能要求，则可以继续使用您现有的 Internet 连接来连接到 Skype 的在线业务。
  
对于网络性能的要求没有满足其中的公司网站，我们强烈建议您首先使用现有网络服务提供商以改善网络的总体性能。 但是，如果他们仍不能得到满足，使用 Azure ExpressRoute 可以帮助确保您 Skype 业务在线云连接可以帮助您满足网络的性能要求。
  
Azure ExpressRoute 提供以下益处：
  
- 服务级别协议 (SLA) 对可用性的网络和 Microsoft 网络之间的连接。 ExpressRoute 有 99.9%的可用性 SLA 保证。
    
- Office 365 提供服务所需的计划和保证带宽。 可以通过使用 ExpressRoute 的业务通信发送只有 Office 365 的通信或 Skype 实现这一点，然后让所有其他 Internet 通信量进入网络的其他互联网出口/入口点。
    
- ExpressRoute 旨在保护您的网络和 Microsoft 网络之间的 DSCP QoS 标记。
    
有关 ExpressRoute QoS 和容量规划的详细信息，请参阅[ExpressRoute 和在 Skype 的在线业务的 QoS](https://support.office.com/en-us/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d?ui=en-US&amp;rs=en-US&amp;ad=US)。
  
### <a name="can-i-setup-azure-expressroute-for-skype-for-business-online-only"></a>可以设置 Azure ExpressRoute 为 Skype 为业务仅限联机状态？

是的您可以设置 Azure ExpressRoute，以确保优秀的网络连接从公司网络仅 Skype 的在线业务。 这将为用户提供最佳的实时媒体质量，但您可以继续通过 Internet 连接到其他 Office 365 提供服务。
  
边界网关协议 (BGP) 是用来将网络流量路由通过 Internet 互联网上的路由协议。 它旨在通过互联网找到自治系统 (AS) 之间的路由信息交换。 BGP 社区值是可应用于传入或传出路由属性标记。 BGP 社区通常用于为使用来达到特定的目标，根据地理位置、 服务类型或其他条件的出站链接接收到信号。
  
BGP 社区支持，Microsoft 将使用基于的服务所属的适当 BGP 社区值标记前缀和工艺路线。 Microsoft 将标记通过公共对等广告前缀和前缀承载于 Microsoft 替换相应的 BGP 社区值，该值指示该区域对等。 您可以依靠社区值进行适当提供最佳路由的路由决策。 可用于 Skype 业务在线 BGP 社区值设置 ExpressRoute 连接到仅为 Skype 的在线业务。 您可以了解更多[ExpressRoute 路由](https://azure.microsoft.com/en-us/documentation/articles/expressroute-routing/)的要求。
  
## <a name="expressroute-connectivity-scenarios-for-skype-for-business-online"></a>Skype 的在线业务的 ExpressRoute 连接方案
<a name="bkNetworkPerf"> </a>

如果您已决定根据上述建议的 ExpressRoute 为您，下面是在哪里上的建议和多少 ExpressRoute 连接应该获取。
  
### <a name="online-only-deployment---single-site"></a>在线的唯一部署-单个站点

如果您的所有用户使用 Skype 的在线商业服务，并且您的办公室为中心围绕单一的物理位置和您决定部署 Azure ExpressRoute，您应设置单个 ExpressRoute 连接到最接近您公司的网站之间[ExpressRoute 的对等位置](https://azure.microsoft.com/en-us/documentation/articles/expressroute-locations/)。
  
下图举例说明这种类型的部署。 例如，Contoso 就大学位于佛罗里达，奥兰多市举办。 Contoso 有 10000 的教职员和学生。 在高峰类互联网测试它们的位置从 Microsoft 边缘站点显示大于 5%的数据包丢失。 已决定获取到 Office 365 提供过量的带宽使用 ExpressRoute 以便他们可以避免 Office 365 的网络拥塞，尤其是对 Skype 业务在线实时通信的专用的连接。 他们连接到 Microsoft 云通过 ExpressRoute 在佐治亚州亚特兰大 MeetMe 站点。
  
![ExpressRoute 单站点。](../images/59fbca3c-a3ea-4568-8da5-3281096a7453.png)
  
### <a name="online-only-deployment---multiple-sites-on-the-same-continent"></a>联机仅部署-在同一个洲的多个站点

如果您选择实施 Azure ExpressRoute 您的公司正在使用 Skype 来自同一地区或同一大陆，在多个办事处的业务联机服务，建议 ExpressRoute，通过主网站连接，然后选择添加其他ExpressRoute 对用于其他位置不符合所建议的网络性能指标等。
  
在以下示例中，Contoso 是美国旅游服务公司，总部位于纽约，但美国各州都有其它办事处。 其办公室正在间通过使用连接到 Office 365 的 MPLS WAN 连接。 他们最初设置从其 Internet 路由器连接到 ExpressRoute 在 Hoboken，新泽西到纽约 MeetMe 站点。 
  
使用此设置中，从他们的网站的大部分与 Microsoft 网络 （纽约边缘站点） 的网络通信可以满足 Skype 的[从业务客户端的 Skype 的网络性能要求中所述的业务客户端连接网络的性能目标给 Microsoft 网络边缘](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge)。 但是，Contoso 的西海岸到纽约的办公室之间的延迟就会通过单向 50 毫秒。 此外，Honolulu contoso 的第二大办公室，从 Honolulu 纽约的延迟超过 80ms 单向。 若要确保用户在这些办公室中工作正常的介质质量，Contoso 决定添加他们的圣何塞站点和硅谷 ExpressRoute MeetMe 站点之间的西海岸 ExpressRoute 连接。
  
![在同一个洲表示路由器多站点。](../images/bf57a473-01e1-4271-9675-385767bc58e1.png)
  
### <a name="online-only-deployment---multiple-sites-on-different-continents"></a>联机仅部署-在不同的洲的多个站点

如果您的所有用户使用 Skype 的在线商业服务，并且如果您的办公室是在多个物理位置跨多个大陆，如果您决定部署 Azure ExpressRoute，您应设置为每个洲的至少一个 ExpressRoute 连接之间每个洲到其最近的[ExpressRoute 对等位置](https://azure.microsoft.com/en-us/documentation/articles/expressroute-locations/)的主站点。 根据成本与收益，您可以选择部署网络性能目标并不符合其中的站点中的其他 ExpressRoute 连接。
  
在以下示例中，Contoso 在北美和欧洲是大公司的法律事务所在主要城市均设有办事处。 根据他们的 Internet 连接和其内部网络性能评估，Contoso 决定部署两个 ExpressRoute 连接北美和单个 ExpressRoute 电路及其所有欧洲办事处。
  
![与多个站点和大陆的 ExpressRoute。](../images/c967550b-dc85-4b37-a7bc-cd825ec86854.png)
  
### <a name="hybrid-deployment"></a>混合部署

如果有内部 Lync 或 Skype 进行业务部署和选择实现混合 Skype 的在线业务集成，我们建议，如果您决定部署 Azure ExpressRoute，需要有至少一个 ExpressRoute 连接，每个内部 Lync 或 Skype 业务边缘站点和至少一个 ExpressRoute 连接的每个洲均设有办事处。 根据成本与收益，对每个大陆可以部署其他 ExpressRoute 连接从办公室位置没有满足网络的性能目标。
  
如果您有内部 Skype 的商用部署，则必须按照[边缘服务器计划和部署指南](https://technet.microsoft.com/en-us/library/mt346417.aspx)。 具体来说，边缘服务器必须可以从外部网络访问。 这通常被实现通过将可穿绕的公用 IP 地址指派到边缘服务器，或通过使用网络地址转换 (NAT)。
  
在以下示例中，Contoso 有业务企业语音部署现有内部 Skype。 他们想要迁移到 Office 365 提供在线服务的内部用户。 他们还决定使用混合部署，这样他们可以继续使用现有的 PSTN 基础架构的所有内部部署和联机用户。 Contoso 的内部数据中心和业务边缘服务器的 Skype 是在芝加哥。 对于其部署，Contoso 决定设置一个芝加哥数据中心和芝加哥 ExpressRoute 之间的 ExpressRoute 连接。 它们还增加西海岸 ExpressRoute 连接，以更好地服务其 Honolulu 办公室。
  
![ExpressRoute 混合。](../images/a7467c56-642f-44e5-adfb-ecca91ba2dd3.png)
  
### <a name="online-deployment-with-cloud-connector-edition"></a>使用云连接器版联机部署

商务在线云连接器版的 Skype 是封装虚拟机 (Vm) 实现内部的 PSTN 连接一组组成的混合产品。 通过部署在虚拟化环境中的业务服务器拓扑结构的最小 Skype，您将能够发送和接收与 landlines 和现有内部 PSTN 语音基础架构通过手机电话。
  
如果您决定部署 Azure ExpressRoute 和云连接器版，我们建议您可以设置为每个洲每个洲向其接近[ExpressRoute 的对等位置](https://azure.microsoft.com/en-us/documentation/articles/expressroute-locations/)的主站点之间至少一个快速通道连接。 根据成本与收益，对每个大陆可以部署其他 ExpressRoute 连接站点位置没有满足网络的性能目标。
  
如果您有内部 Skype 的商用部署，必须按照[规划指南 》 商务云连接器版的 Skype](https://technet.microsoft.com/EN-US/library/mt605227.aspx)。 具体来说，访问边缘和 A / V 边缘服务应分配公用 IP 地址，可以从 Office 365 提供数据中心访问。
  
在以下示例中，Contoso 是欧洲会计公司具有在几个主要欧洲国家和城市的影响力。 当它们注册为 Skype 在线业务的所有他们的协作需要时，他们决定将云连接器，每个国家能够继续使用他们的 PSTN 基础结构的物理位置和承运人约定已存在。 根据他们从他们的网站和 Microsoft 网络边缘的测试，他们决定在伦敦一次 ExpressRoute 连接有助于满足 Skype 的网络性能[中所述的业务客户端连接网络性能目标要求从业务客户端的 Skype 给 Microsoft 网络边缘](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge)。
  
![ExpressRoute 云连接器一。](../images/ebdc96e5-b22a-4bf2-b668-062460b4b890.png)
  
下面是 Contoso 的另一种部署方法。 在这种情况下，他们决定在每个站点部署云接头的位置设置 ExpressRoute 连接。 
  
![ExpressRoute 云连接器两个。](../images/06d967a9-64f5-4d7d-98ed-3f3add1b7c2b.png)
  
## <a name="related-topics"></a>相关主题

[Skype for Business Online 中的 ExpressRoute 和 QoS](expressroute-and-qos-in-skype-for-business-online.md)

