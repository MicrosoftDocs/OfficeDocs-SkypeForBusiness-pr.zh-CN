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
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Optimization
description: 本主题定义 Microsoft Teams 服务的一组网络性能要求，以及如何根据对网络连接的评估选择使用 Internet 或 ExpressRoute 在网络和 Microsoft Teams 之间连接。 如果决定部署 Azure ExpressRoute 以专用连接 Microsoft 365 或 Office 365，本文档还提供了有关如何在不同部署方案中规划 ExpressRoute Microsoft Teams的指导。
ms.openlocfilehash: c73922af3befc9070127d9b9937a82f8b8d94e0b
ms.sourcegitcommit: 9fcd9a7ae78e04cef90415c2a0f30a98fbf8270f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/19/2021
ms.locfileid: "58407031"
---
# <a name="media-quality-and-network-connectivity-performance-in-microsoft-teams"></a>媒体质量和网络中网络连接Microsoft Teams

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

本主题定义 Microsoft Teams 服务的一组网络性能要求，以及如何根据对网络连接的评估选择使用 Internet 或 ExpressRoute 在网络和 Microsoft Teams 之间连接。 如果决定部署 Azure ExpressRoute 以专用连接 Microsoft 365 或 Office 365，本文档还提供了有关如何在不同部署方案中规划 ExpressRoute Microsoft Teams的指导。
  
IP 上Real-Time媒体 (、视频和应用程序共享) 的质量受到端到端网络连接质量的很大影响。 为了Microsoft Teams媒体质量，请务必确保公司网络与公司网络之间Microsoft Teams。 实现此目的的最佳方法就是根据网络容量设置内部网络和云连接，以适应所有连接的高峰流量Microsoft Teams流量。
  
Azure ExpressRoute 不要求使用 Microsoft 365 Office 365 服务（包括 Microsoft Teams）。 但是，Azure ExpressRoute 是可用的部署选项之一，可帮助确保连接到 Microsoft 365 或 Office 365 满足 Microsoft Teams 网络性能要求，并确保最佳的 Microsoft Teams 媒体质量体验。
  
> [!TIP]
> 尽管本主题提供了整体网络性能指南，但网络评估的完整指南超出了本文档的范围。 若要查找可在全面Microsoft Teams网络评估中帮助您进行网络性能测量的合作伙伴列表，请访问合作伙伴解决方案 Skype for Business [。](http://partnersolutions.skypeforbusiness.com/) 
  
## <a name="network-connectivity-requirements-to-microsoft-teams"></a>连接的网络连接要求Microsoft Teams

### <a name="factors-that-impact-microsoft-teams-media-quality"></a>影响媒体Microsoft Teams的因素

有许多不同因素Microsoft Teams Real-Time媒体 (音频、视频和应用程序共享) ，包括使用的设备、环境和网络连接。 
  
#### <a name="devices"></a>设备

在Real-Time会话中，所有参与者使用的媒体捕获和呈现设备（如耳机和 Web 摄像头）对音频和视频的整体质量具有很大的影响。 低品质设备和错误的设备驱动程序会降低整体的音频声音质量和视频图像质量。 经过认证的设备或优质设备有助于消除回声、过滤噪音、视频分辨率并减少延迟。
  
尽管不需要经过认证的音频和视频媒体设备，但强烈建议使用经认证的设备Microsoft Teams获得最佳媒体体验。 有关所有经认证的Microsoft Teams的列表，请参阅手机和设备 for [Skype for Business。](../../SfbPartnerCertification/certification/devices-ip-phones.md) 可以使用 [Microsoft Teams](/microsoftteams/turning-on-and-using-call-quality-dashboard)Skype for Business 管理中心中的"呼叫质量仪表板 **"来** 验证使用中的设备是否正常工作并监视音频和视频媒体质量。
  
> [!TIP]
> **为获得最佳媒体质量体验，Skype for Business认证设备**。
  
必须记住，任何媒体设备、Microsoft Teams客户端和Skype for Business服务器Real-Time，都引入了一定的延迟。 设备和软件处理延迟以及网络延迟对端到端整体延迟和最终用户体验影响很大。
  
#### <a name="environment"></a>环境

用户会面和使用音频和视频设备的环境和周边区域是音频和视频质量的另一个重要因素。 从嘈杂环境呼叫的用户将具有回声、杂乱和不明确的音频。 用户在黑暗或低光照环境中则无法生成明亮清晰的视频图像画质。 在会议室设置中，麦克风和视频设备的位置对参与者接收的声音和图像质量有直接影响。
  
若要更清晰地了解用户的音频和视频体验，请使用 Skype for Business **应用工具** 选项音频设备或视频设备对使用中的设备进行更改并  >    >  自定义其设置。

#### <a name="network"></a>网络

IP 网络Real-Time媒体的质量受到网络连接质量的很大影响，尤其是以下数量：
  
- **延迟** 这是从网络上的点 A 到点 B 获取 IP 数据包所花的时间。 此网络传播延迟与两个点之间的物理距离和光速有关，包括两者之间的各种路由器所取的额外开销。 延迟以 RTT 流量的单向或往返 () 。
    
- **数据包丢失** 这通常定义为给定时间窗口中丢失的数据包的百分比。 数据包丢失直接影响音频质量 -从小型、单个丢失的数据包几乎没有任何影响，到导致音频完全中断的背对背突发丢失。
    
- **数据包间到达抖动或只是抖动** 这是连续数据包之间的延迟的平均变化。 大多数现代 VoIP 软件Microsoft Teams通过缓冲来适应某些级别的抖动。 只有当抖动超过缓冲时，参与者才能注意到抖动的影响。
    
> [!NOTE]
>  抖动缓冲会增加端到端延迟。
  
对于许多并发 Microsoft Teams Real-Time 媒体会话以及其他 Microsoft 365 或 Office 365 服务和其他业务应用程序生成的网络流量，请确保将网络连接到 Microsoft Teams 服务的整个网络路径有足够的带宽对于避免网络拥塞和确保出色的媒体 Real-Time 媒体 (音频、视频和应用程序共享) 质量至关重要。 
  
#### <a name="implementing-quality-of-service-qos-across-congested-networks"></a>跨交通网络 (QoS) 服务质量

此外，网络上流量拥塞将极大地影响媒体质量。 若要允许音频和视频数据包更快地传输网络并优先处理塞塞网络的其他网络流量，可以使用服务质量 (QoS) 来帮助为音频和视频通信提供最佳最终用户体验。
  
QoS 提供了一种方法，用于为携带音频或视频数据的网络数据包分配更高的优先级。 通过为这些数据包分配更高的优先级，音频和视频通信可能会比涉及文件传输、Web 浏览或数据库备份等内容的网络会话更快地在网络中传输，并且中断更少。 这是因为默认情况下，用于文件传输或数据库备份的网络数据包被分配为"尽力而为"作为优先级，并且网络拥塞不会产生太大的影响。 如果不为媒体共享 (音频、视频和应用程序共享) 数据包分配更高的优先级，并且还将其分配为"尽力而为"，则这些数据包也将连同所有其他网络流量一起处理。 根据网络拥塞量，这可能会导致用户的整体音频和视频质量体验降低。
  
强烈建议在网络中实施 QoS，确保网络拥塞不会影响网络拥塞。 但是，为了产生最大的影响，所有网络终结点都必须支持 QoS，这意味着所有终结点都必须遵守 QoS 标记和数据包优先级。 Microsoft Teams服务在 Microsoft 网络中遵守 QoS 标记和优先级。 但是，通过公共连接（如 Internet）从公司网络路由到 Microsoft 网络的流量不会保留 QoS 标记和数据包优先级。 使用[Azure ExpressRoute](https://azure.microsoft.com/services/expressroute/)从网络到 Microsoft 365 或 Office 365 的专用连接提供一种部署解决方案，可保留 QoS 标记和数据包优先级，进而提高最终用户的整体音频和视频质量。
  
## <a name="network-performance-requirements-to-connect-to-microsoft-teams"></a>连接到客户端的网络性能Microsoft Teams
<a name="bkNetworkPerf"> </a>

Skype for Business Real-Time媒体通过许多不同的设备、客户端应用、服务器软件以及跨不同的网络传输。 媒体的端到端延迟Real-Time所有组件和网段引入的总延迟量。 端到端网络连接的质量由质量最差的网络段决定。 此段充当此网络流量的瓶颈。
  
下图演示了会议中的单向音频流，从一个参与者Microsoft Teams到另一个参与者。
  
![ExpressRoute 呼叫Flow。](../images/c026e8e5-ba09-42c0-9e03-60fbfda1cb02.png)
  
在此会议方案中，媒体路径包括以下网段：
  
1. **从用户 1 到 Microsoft 网络边缘的连接** 这通常包括 WiFi 或以太网等网络连接、从用户 1 到 Internet 出口点的 WAN 连接 (网络边缘设备) ，以及从网络边缘到 Microsoft Network Edge 的 Internet 连接。
    
2. **Microsoft 网络内部连接** 这是在Microsoft Edge Microsoft Teams，使用 A/V 会议服务器的数据中心之间。
    
3. **Microsoft Network 中的连接** 这是在数据中心Microsoft Teams Microsoft Network Edge 之间。
    
4. **从 Microsoft 网络边缘连接到用户 2** 这包括从网络边缘到 Microsoft Network Edge 的 Internet 连接、从用户 2 到 Internet 出口点 (的 WAN 连接) 以及 WiFi 或以太网等网络连接。
    
下图显示了 PSTN 呼叫的组件和网络Microsoft Teams细分：
  
![ExpressRoute PSTN 运营商呼叫Flow。](../images/768a88df-c8a9-4171-a158-565a698f0193.png)
  
在 PSTN 呼叫方案中，媒体路径跨以下网段：
  
1. **从 Skype for Business 客户端调用方到 Microsoft 网络边缘的连接** 这通常包括 WiFi 或以太网等网络连接、从 Skype for Business 客户端调用方到 Internet 出口点的 WAN 连接 (网络边缘设备) ，以及从网络边缘到 Microsoft Network Edge 的 Internet 连接。
    
2. **Microsoft 网络内部连接** 这是在Microsoft Edge Microsoft Teams数据中心之间，其中使用了中介服务器。
    
3. **Microsoft Network 中的连接** 这是在数据中心Microsoft Teams Microsoft Network Edge 之间。
    
4. **Microsoft 网络与 PSTN 服务提供商合作伙伴之间的连接** 这是从 Microsoft 网络外部的客户端Skype for Business PSTN 呼叫的连接。
    
### <a name="network-performance-requirements-from-a-skype-for-business-client-to-microsoft-network-edge"></a>从客户端到 Microsoft network Edge Skype for Business网络性能要求
<a name="bkSfBClienttoEdge"></a>

为了Skype for Business媒体质量，从公司网络到 Microsoft Network Edge 的连接需要以下网络性能指标目标或阈值。 此网络段包括内部网络，这包括所有 WiFi 和以太网连接、通过 WAN 连接的任何公司站点到站点流量，例如多协议标签切换 (MPLS) ，以及到 Microsoft Network Edge 的 Internet 或 ExpressRoute 合作伙伴连接。
  
> [!CAUTION]
> **公司网络中Skype for Business客户端与Microsoft 365服务Office 365必须满足以下网络性能要求和阈值。**

|**指标** <br/> |**目标** <br/> |
|:-----|:-----|
|单向 (延迟)   <br/> |< 50 毫秒  <br/> |
|RTT (往返时间延迟)   <br/> |< 100 毫秒  <br/> |
|突发数据包丢失  <br/> |<200 毫秒间隔内为 10%  <br/> |
|数据包丢失  <br/> |<15 秒间隔内为 1%  <br/> |
|数据包到达间抖动  <br/> |<15 秒时间间隔内为 30 毫秒  <br/> |
|数据包重新排序  <br/> |<0.05% 的无序数据包  <br/> |
   
 **其他性能目标要求：**
  
- Microsoft 网络在全球有 160 多个 Edge 位置。 我们通过这些边缘网站 (INTERNET 服务提供商) ISP。 延迟指标目标假定公司站点和 Microsoft Edge 位于同一大洲。
    
- 公司站点或站点到 Microsoft Network Edge 连接包括第一跃点网络访问，可以是 WiFi 或其他无线技术。 
    
- 网络性能目标假定适当的带宽和/或服务质量规划。 换言之，当网络连接负载Skype for Business Real-Time，这直接适用于媒体流量。
    
### <a name="network-performance-requirements-from-your-network-edge-to-microsoft-network-edge"></a>从网络边缘到 Microsoft Network Edge 的网络性能要求
<a name="bkYourNetworkEdge"> </a>

下面是网络边缘与 Microsoft Network Edge 之间的连接所需的网络性能目标或阈值。 此网络段不包括客户的内部网络或 WAN，旨在指导测试通过 Internet 或 ExpressRoute 合作伙伴网络发送的网络流量，也可在与 ExpressRoute 提供商协商性能服务级别协议 (SLA) 时使用。
  
> [!CAUTION]
> **公司网络边缘到 Microsoft 网络边缘的连接必须满足以下网络性能要求和阈值。**

|**指标** <br/> |**目标** <br/> |
|:-----|:-----|
|单向 (延迟)   <br/> |< 30 毫秒  <br/> |
|RTT (延迟)   <br/> |< 60 毫秒  <br/> |
|突发数据包丢失  <br/> |<200 毫秒间隔内为 1%  <br/> |
|数据包丢失  <br/> |<15 秒间隔内为 0.1%  <br/> |
|数据包到达间抖动  <br/> |<15 秒时间间隔内为 15 毫秒  <br/> |
|数据包重新排序  <br/> |<0.01% 的无序数据包  <br/> |
   
 **其他性能目标要求：**
  
- 性能目标要求公司的任何网络边缘及其最近的 Microsoft Network Edge 之间的连接位于同一大洲。
    
- 网络性能目标假定适当的带宽和/或服务质量规划。 当网络连接负载Skype for Business Real-Time时，这也适用于媒体流量。 有关适当的带宽和 QoS 规划，请参阅 Microsoft Teams[中的 ExpressRoute 和 QoS。](https://support.office.com/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d)
    
## <a name="measuring-network-performance"></a>测量网络性能
<a name="bkNetworkPerf"> </a>

若要测量从任何公司网络站点到网络边缘的实际网络性能，尤其是延迟和数据包丢失，可以使用 ping 等工具，针对从 Microsoft Edge 和数据中心站点运行的一组 Skype for Business 媒体中继服务进行测试。 

>[!NOTE]
> 通过 ping (ICMP) 测量网络性能并不有效。 因此，从 2020 年 1 月开始，下面公开的任何广播 IP 将停止响应 ICMP 请求。 为了有效地衡量网络性能，Microsoft 建议使用 [网络增强工具](https://www.microsoft.com/download/details.aspx?id=53885)。
  
若要测试与 Microsoft 网络的 Internet 连接，建议针对以下媒体中继的 SKYPE FOR BUSINESS测试。 *Anycast VIP* 将解析为离测试位置最近的 Microsoft Network Edge 站点中的媒体中继的 IP 地址。
  

|**IP 地址** <br/> |**类型** <br/> |**位置** <br/>|
|:-----|:-----|:-----|
|13.107.8.2  <br/> |VIP  <br/> |万维网播 IP  <br/> |
   
 **下面是评估网络性能时要遵循的一些高级建议：**
  
- 应评估内部网络，以及连接到 Microsoft 365 或 Office 365。
    
- 应评估并收集长时间内所有网络的数据。 建议至少执行一周的网络性能测试，以便查看所有工作天和小时的使用模式。 这将显示高峰时间。
    
- 应该对网络性能度量进行多次采样。 建议在收集数据的整个时段内每 10 分钟从公司站点进行一次测量。 要比较Microsoft Teams性能要求，请从此示例数据集中取第 90 百分位度量值。 
    
- 应持续评估网络的性能。 由于使用模式更改、使用大量带宽的新基于企业的应用程序，以及组织或物理公司位置的更改，网络利用率会随时间变化。 必须持续监视网络性能，使其符合这些网络性能要求和目标/阈值，并及时进行调整，以确保最佳的媒体Real-Time性能。 
    
## <a name="measuring-network-performance-using-azure-vms"></a>使用 Azure VM 测量网络性能
<a name="bkNetworkPerf"> </a>

除了针对 Microsoft 网络边缘站点进行测试，还有来自 Skype for Business 客户和合作伙伴的网络评估解决方案，这些解决方案对云中的服务使用Microsoft Azure设置。 在这些解决方案中，网络评估工具针对在 Azure 云中设置为服务的自定义终结点测试延迟、数据包丢失和抖动。 因此，测试网络流量会经过另一个网络段，即 Microsoft 网络内网络边缘与托管网络评估服务的 Azure 数据中心之间的连接。
  
对于这些基于 Azure 托管测试服务的网络评估解决方案。 我们建议在国家/地区内和/或区域执行网络评估。 例如，对于美国东部的客户站点，应针对 Azure 美国东部数据中心区域托管的测试服务实例执行评估。 
  
下面是基于 Azure (网络) 设置的 RTT 目标延迟。 单向延迟目标将是相应 RTT 目标的一半。 丢包和抖动目标与针对基于媒体中继的测试Skype目标相同。
  


|**客户区域** <br/> |**Azure 区域** <br/> |**网络边缘 - AZURE 往返时间 (RTT)** <br/> |**站点 - AZURE 往返时间 (RTT)** <br/> |
|:-----|:-----|:-----|:-----|
|美国中部  <br/> |美国中部  <br/> |99  <br/> |139  <br/> |
|美国东部  <br/> |美国东部  <br/> |86  <br/> |126  <br/> |
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
|日本东部  <br/> |日本东部  <br/> |111  <br/> |151  <br/> |
|日本西部  <br/> |日本西部  <br/> |118  <br/> |158  <br/> |
|巴西南部  <br/> |巴西南部  <br/> |70  <br/> |110  <br/> |
|澳大利亚东部  <br/> |澳大利亚东部  <br/> |124  <br/> |164  <br/> |
|澳大利亚东南部  <br/> |澳大利亚东南部  <br/> |124  <br/> |164  <br/> |
|印度中部  <br/> |印度中部  <br/> |103  <br/> |143  <br/> |
|印度南部  <br/> |印度南部  <br/> |103  <br/> |143  <br/> |
|印度西部  <br/> |印度西部  <br/> |103  <br/> |143  <br/> |
|中国东部  <br/> |中国东部  <br/> |120  <br/> |160  <br/> |
|中国北部  <br/> |中国北部  <br/> |120  <br/> |160  <br/> |
   
## <a name="media-quality-and-expressroute"></a>媒体质量和 ExpressRoute
<a name="bkNetworkPerf"> </a>

适用于 Microsoft 365 或 Office 365 的 Azure ExpressRoute 是一个专用网络连接，用于连接到 Microsoft 365 或 Office 365。 它使客户能够控制其网络流量采用的路径。 他们不再需要担心 Internet 上发生不可预测的路由，其中数据由未知运营商、提供商和 ISP 携带。 通过 ExpressRoute 发送的网络流量直接通过 ExpressRoute 合作伙伴的网络发送到 Microsoft 网络。 这样，客户Microsoft 365或Office 365，就像它位于其自己的具有专用连接的场外数据中心一样。
  
Azure ExpressRoute 适用于所有Microsoft 365 Office 365产品/服务。 但是，Azure ExpressRoute 高级版加载项是启用全局路由Microsoft 365 Office 365所需的。 实施 ExpressRoute 的客户至少拥有 500 个席位，可以获取所需的 *ExpressRoute* 高级版附加内容，无需额外付费。
  
### <a name="is-expressroute-required-for-good-media-quality"></a>需要 ExpressRoute 才能确保良好的媒体质量吗？

要获得最佳媒体质量，Azure ExpressRoute Microsoft Teams要求。 但是，它是一个部署选项，可帮助确保云连接满足Skype for Business目标或阈值。
  
Microsoft 365 Office 365是使用 Internet 的高性能和安全服务。 我们将继续投资新的安全功能和区域边缘节点，以持续提高安全性和性能。 Azure ExpressRoute 不要求使用 Microsoft 365 或 Office 365 服务，Microsoft Teams。 Azure ExpressRoute 是可用的部署选项之一，可帮助确保连接到 Microsoft 365 或 Office 365 满足 Skype for Business 网络性能要求，并确保最佳的 Microsoft Teams 媒体质量体验。
  
对于 Microsoft Teams 媒体质量，公司站点与 Microsoft 网络边缘之间的连接必须满足[从 Skype for Business](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge)客户端到 Microsoft Network Edge 的网络性能要求中的性能目标，并且网络边缘与 Microsoft 网络边缘之间的连接满足从网络边缘到 Microsoft Network [Edge](media-quality-and-network-connectivity-performance.md#bkYourNetworkEdge)的网络性能要求中的性能目标，这一点非常重要。  
  
公司的物理网络连接（包括内部网络和云连接容量）必须适应高峰媒体流量，这一点也很重要。 Azure ExpressRoute 是帮助客户确保其云Microsoft Teams满足所有这些性能要求的多种方式之一。
  
### <a name="is-expressroute-required-for-voice-quality-sla"></a>语音质量 SLA 需要 ExpressRoute 吗？

否，ExpressRoute 不是语音质量 SLA Microsoft Teams要求。 语音[Microsoft Teams SLA](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;DocumentTypeId=37)适用于任何 Microsoft Teams 语音服务用户在正确的许可证和订阅中拨打的任何符合条件的呼叫，使该用户能够进行任何类型的 VoIP 或 PSTN 呼叫。 语音质量 SLA 应包括满足以下所有条件：
  
- 来自 Microsoft 认证的 IP 电话的呼叫。
    
- 有线以太网连接。
    
- 由于 Microsoft 网络问题而出现语音质量问题。
    
> [!NOTE]
> 语音质量 SLA 不包括由非 Microsoft 网络（包括 ExpressRoute 合作伙伴和其他网络）中的问题导致呼叫质量低的呼叫。 
  
### <a name="internet-or-azure-expressroute"></a>Internet 还是 Azure ExpressRoute？

在决定要连接的网络连接选项Microsoft Teams，客户必须基于网络性能要求中所述的网络性能要求评估其网络和当前[Internet](media-quality-and-network-connectivity-performance.md#bkNetworkPerf)连接，以连接到 Microsoft Teams。
  
如果当前 Internet 连接的网络性能设置为在高峰期有足够的容量，并且满足从站点到 Microsoft 网络边缘以及从网络边缘到 Microsoft 网络边缘的网络性能要求，则你可以继续使用现有的 Internet 连接连接到 Microsoft Teams。
  
对于不满足网络性能要求的公司站点，强烈建议首先与现有网络服务提供商合作，以提高整体网络性能。 但是，如果仍未满足要求，使用 Azure ExpressRoute 可帮助确保云Microsoft Teams可帮助满足网络性能要求。
  
Azure ExpressRoute 提供以下附加优势：
  
- 服务级别协议 (SLA) 网络与 Microsoft 网络之间的连接可用性。 ExpressRoute 保证的可用性 SLA 为 99.9%。
    
- 服务和服务所需的计划Microsoft 365 Office 365带宽。 为此，只需使用 ExpressRoute 发送 Microsoft 365、Office 365 或 Skype for Business 流量，然后让所有其他 Internet 流量通过网络的其他 Internet 出口/入口点。
    
- ExpressRoute 旨在保留网络和 Microsoft 网络之间的 DSCP QoS 标记。
    
有关 ExpressRoute QoS 和容量规划的信息，请参阅[ExpressRoute](https://support.office.com/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d)和 Microsoft Teams。
  
### <a name="can-i-set-up-azure-expressroute-for-microsoft-teams-only"></a>能否将 Azure ExpressRoute 设置为仅Microsoft Teams？

是的，可以设置 Azure ExpressRoute，以确保从公司网络到仅与公司建立良好的网络连接Microsoft Teams。 这将为用户提供最佳Real-Time媒体质量，但你可以继续通过 Internet 连接到Microsoft 365 Office 365服务。
  
边界网关协议 (BGP) 是 Internet 上的路由协议，用于通过 Internet 路由网络流量。 它设计用于在通过 Internet 找到的 (AS) 系统之间交换路由信息。 BGP 社区值是可应用于传入或传出路由的属性标记。 BGP 社区通常用于向接收 AS 发出信号，接收 AS 的出站链接用于根据地理位置、服务类型或其他条件到达给定目标。
  
借助 BGP 社区支持，Microsoft 将基于前缀和路由所属的服务，使用适当的 BGP 社区值标记前缀和路由。 Microsoft 将标记通过公共对等互连和 Microsoft 对等互连播发的前缀，这些前缀具有相应的 BGP 社区值，指示前缀托管在的区域。 可以依赖社区值做出适当的路由决策，以提供最佳路由。 可以使用 BGP Microsoft Teams设置 ExpressRoute 连接，仅针对 Microsoft Teams。 可以在 ExpressRoute 路由要求 [中了解更多信息](/azure/expressroute/expressroute-routing)。
  
## <a name="expressroute-connectivity-scenarios-for-microsoft-teams"></a>适用于 Microsoft Teams 的 ExpressRoute 连接Microsoft Teams
<a name="bkNetworkPerf"> </a>

如果根据上述建议确定 ExpressRoute 是适合的，下面是应获取的 ExpressRoute 连接位置和数量的建议。
  
### <a name="online-only-deployment---single-site"></a>仅联机部署 - 单个站点

如果所有用户都使用 Microsoft Teams 服务，并且办公室以单个物理位置为中心，并且你决定部署 Azure ExpressRoute，应在公司站点与最近的[ExpressRoute](/azure/expressroute/expressroute-locations)对等位置之间设置单个 ExpressRoute 连接。
  
下图显示了此类部署的示例。 就此示例来说，Contoso 是一所位于美国加州奥兰多的大学。 Contoso 有 10，000 名教职员工和学生。 从 Internet 位置到Microsoft Edge的 Internet 测试显示，在高峰期丢包率超过 5%。 他们决定使用具有过度预配带宽的 ExpressRoute 与 Microsoft 365 或 Office 365 建立专用连接，以避免 Microsoft 365 或 Office 365 网络拥塞，尤其是针对 Microsoft Teams Real-Time 流量。 他们通过位于亚特兰大 GA MeetMe 站点的 ExpressRoute 连接到 Microsoft 云。
  
![ExpressRoute 单站点。](../images/59fbca3c-a3ea-4568-8da5-3281096a7453.png)
  
### <a name="online-only-deployment---multiple-sites-on-the-same-continent"></a>仅联机部署 - 同一大洲的多个站点

如果公司使用来自同一区域或大洲中多个办公室的 Microsoft Teams 服务，并且已选择实施 Azure ExpressRoute，则建议通过 ExpressRoute 连接主站点，并选择性地为不符合建议的网络性能目标的其他位置添加其他 ExpressRoute 对等互连。
  
在下面的示例中，Contoso 是一家美国旅行服务公司，其总部位于纽约，但在美国设有其他办公室。 其办公室通过 WAN 进行互连，该 WAN 使用 MPLS 连接到 Microsoft 365 或 Office 365。 最初，他们设置一个 ExpressRoute 连接，从其 Internet 路由器（其 Internet 路由器在新泽西的 Hoboken）连接到纽约 MeetMe 站点。 
  
通过此设置，从大多数站点发到 Microsoft Network (New York Edge 站点) 的网络流量可以满足 Skype for Business 客户端到 Microsoft Network Edge 的网络性能要求中所述的[Skype for Business](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge)客户端连接网络性能目标。 但是，Contoso 的西海岸办公室到纽约之间的延迟单向超过 50 毫秒。 此外，Hono以 Contoso 为第二大办公室，从金山到纽约的延迟单向超过 80 毫秒。 为了确保这些办公室的用户具有良好的媒体质量，Contoso 决定在圣何塞站点与硅谷 ExpressRoute MeetMe 站点之间添加一个西海岸 ExpressRoute 连接。
  
![同一大洲上的 Express 路由器多站点。](../images/bf57a473-01e1-4271-9675-385767bc58e1.png)
  
### <a name="online-only-deployment---multiple-sites-on-different-continents"></a>仅联机部署 - 位于不同大洲的多个站点

如果所有用户都使用 Microsoft Teams 服务，并且办公室位于多个大洲的多个物理位置，则如果决定部署 Azure ExpressRoute，应在每个大洲的主站点与最近的[ExpressRoute](/azure/expressroute/expressroute-locations)对等位置之间设置至少一个 ExpressRoute 连接。 根据成本与权益，可以选择从不满足网络性能目标的站点部署其他 ExpressRoute 连接。
  
在下面的示例中，Contoso 是一家大型企业法律公司，其办公室遍布北美和欧洲的主要城市。 Contoso 根据 Internet 连接和内部网络性能评估，决定在北美部署两个 ExpressRoute 连接，并针对其所有欧洲办公室部署一条 ExpressRoute 线路。
  
![具有多个站点和大洲的 ExpressRoute。](../images/c967550b-dc85-4b37-a7bc-cd825ec86854.png)
  
### <a name="hybrid-deployment"></a>混合部署

如果您有本地 Lync 或 Microsoft Teams 部署并选择实现混合 Microsoft Teams 集成，我们建议您决定部署 Azure ExpressRoute，则对于每个本地 Lync 或 Microsoft Teams Edge 站点，需要至少具有一个 ExpressRoute 连接，并且每个大洲至少具有一个 ExpressRoute 连接（办公室）。 根据成本与效益，对于每个大洲，可以选择从不满足网络性能目标的办公室部署其他 ExpressRoute 连接。
  
如果有本地部署Microsoft Teams，必须遵循[Edge Server 规划和部署指南](../../SfbServer/plan-your-deployment/edge-server-deployments/edge-server-deployments.md)。 具体而言，必须从网络外部访问边缘服务器。 这通常是通过向边缘服务器分配可路由的公共 IP 地址，或者通过使用 NAT (网络) 。
  
在下面的示例中，Contoso 有一个现有的本地Microsoft Teams 企业语音部署。 他们希望将本地用户迁移到 Microsoft 365 或Office 365联机服务。 他们还决定使用混合部署，以便他们可以继续针对所有本地和联机用户使用其现有 PSTN 基础结构。 Contoso 本地数据中心和 Skype for Business边缘服务器位于芝加哥。 对于部署，Contoso 决定在芝加哥数据中心与芝加哥 ExpressRoute 之间设置一个 ExpressRoute 连接。 他们还添加了一个西海岸 ExpressRoute 连接，以更好地为其十二山办公室提供服务。
  
![ExpressRoute 混合。](../images/a7467c56-642f-44e5-adfb-ecca91ba2dd3.png)
  
### <a name="online-deployment-with-cloud-connector-edition"></a>使用 Cloud Connector Edition 进行联机部署

Skype for Business 云连接器版本是一种混合产品/服务，包含一组打包的虚拟机 (VM) 实现本地 PSTN 连接。 在虚拟化环境中Skype for Business Server最小网络拓扑，可以通过现有的本地 PSTN 语音基础结构通过座机和移动电话发送和接收呼叫。
  
如果决定部署 Azure ExpressRoute 和 Cloud Connector Edition，我们建议在每个大洲的主站点与最近的 [ExpressRoute](/azure/expressroute/expressroute-locations)对等位置之间至少设置一个 Express Route 连接。 根据成本与效益，对于每个大洲，可以选择从不满足网络性能目标的站点部署其他 ExpressRoute 连接。
  
如果在本地部署Microsoft Teams，必须遵循适用于 的[规划Skype for Business 云连接器版本。](../../SfbServer/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-skype-for-business-cloud-connector-edition.md) 具体而言，应为 Access Edge 和 A/V Edge 服务分配公共 IP 地址，Microsoft 365数据中心Office 365访问。
  
在下面的示例中，Contoso 是一家欧洲会计公司，在几个主要的欧洲国家和地区有业务。 当他们注册 Microsoft Teams满足其所有协作需求时，他们决定为具有物理位置的每个国家/地区设置云连接器，以继续使用其 PSTN 基础结构和已存在的运营商合同。 基于从所有站点和 Microsoft Network Edge 进行测试，他们确定，伦敦单个 ExpressRoute 连接将有助于满足从 Skype for Business 客户端到 Microsoft Network [Edge](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge)的网络性能要求中所述的 Microsoft Teams 客户端连接网络性能目标。
  
![ExpressRoute 云连接器 1。](../images/ebdc96e5-b22a-4bf2-b668-062460b4b890.png)
  
下面是 Contoso 的另一个部署选项。 在这种情况下，他们决定在部署云连接器的每个站点设置 ExpressRoute 连接。 
  
![ExpressRoute 云连接器 2。](../images/06d967a9-64f5-4d7d-98ed-3f3add1b7c2b.png)
  
## <a name="related-topics"></a>相关主题

[Skype for Business Online 中的 ExpressRoute 和 QoS](expressroute-and-qos-in-skype-for-business-online.md)

  
