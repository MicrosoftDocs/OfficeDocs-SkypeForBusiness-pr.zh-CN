---
title: "Skype for Business Online 中的媒体质量和网络连接性能"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 9/21/2016
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom: Adm_O365_FullSet
ms.assetid: 5fe3e01b-34cf-44e0-b897-b0b2a83f0917
description: "本主题定义了 Skype for Business Online 服务的网络性能要求以及如何基于对网络连接评的估选择使用 Internet 还是 ExpressRoute 实现网络和 Skype for Business Online 之间的连接。 如果你已决定将 Azure ExpressRoute 部署为 Office 365 的专用连接，本文档还介绍了如何在不同 Skype for Business Online 部署场景中规划 ExpressRoute 连接的指导。"
---

# Skype for Business Online 中的媒体质量和网络连接性能

本主题定义了 Skype for Business Online 服务的网络性能要求以及如何基于对网络连接评的估选择使用 Internet 还是 ExpressRoute 实现网络和 Skype for Business Online 之间的连接。 如果你已决定将 Azure ExpressRoute 部署为 Office 365 的专用连接，本文档还介绍了如何在不同 Skype for Business Online 部署场景中规划 ExpressRoute 连接的指导。
  
通过 IP 的实时媒体（音频、视频和应用程序共享）的质量很大程度上受到端到端网络连接质量的影响。 为获得最佳的 Skype for Business Online 媒体质量，确保公司网络与 Skype for Business Online 之间的高质量连接很重要。 实现这一目标的最佳做法是基于网络容量设置内部网络和云连接，以便所有连接都可以接受 Skype for Business Online 的高峰流量。
  
Azure ExpressRoute 不是包括 Skype for Business Online 在内的 Office 365 服务所必需的。 但 Azure ExpressRoute 是一个可用的部署选项，有助于确保与 Office 365 的连接满足 Skype for Business 的网络性能要求，并确保最优的 Skype for Business Online 媒体质量体验。
  
> [!提示]
> 本主题提供了网络性能指导概述，但本文档并不包含完整的网络评估指导。要查找可以帮助你在全面、完整的网络评估中执行网络性能评测的 Skype for Business Online 合作伙伴列表，请访问 [Skype for Business 合作伙伴解决方案](http://partnersolutions.skypeforbusiness.com/)。 
  
## Skype for Business Online 的网络连接要求

### 影响 Skype for Business Online 媒体质量的因素

影响 Skype for Business Online 实时媒体（音频、视频和应用程序共享）质量的因素有很多，其中包括使用的设备、环境和网络连接。 
  
#### 设备

实时媒体会话、媒体捕捉和所有参与者使用的耳机、网络摄像头等输出设备都对音频和视频的整体质量有很大影响。 低品质设备和错误的设备驱动程序会降低整体的音频声音质量和视频图像质量。 另一方面，经认证的设备或高品质设备有助于消除回声、过滤噪音、提高视频分辨率并减少延迟。
  
尽管并非必须使用经认证的音频和视频媒体设备，但强烈建议使用经 Skype for Business 认证的设备，以获得最佳媒体体验。有关经 Skype for Business 认证的设备列表，请参见 [Skype for Business 电话和设备](https://technet.microsoft.com/en-us/office/dn947482)。你可以使用位于 **Skype for Business 管理中心** 的[Skype for Business Online 呼叫质量仪表板](https://support.office.com/en-us/article/Turning-on-and-using-Call-Quality-Dashboard-in-Skype-for-Business-Online-553fa13c-92d2-4d5c-a3d5-41a073cb047c?ui=en-US&amp;rs=en-US&amp;ad=US)验证所使用的设备是否正常工作并监视音频和视频媒体质量。
  
> [!提示]
> **要获得最佳的 Skype for Business 媒体质量体验，需要使用经认证的设备** 。
  
请务必记住，实时媒体流经的任何媒体设备、Skype for Business 客户端和 Skype for Business 服务器都会带来某种程度的延迟。 设备和软件处理的延迟以及网络延迟都对端到端整体延迟和最终用户体验有很大影响。
  
#### 环境

用户会面及使用音频和视频设备的环境及周边区域是另一个影响音频和视频质量的重要因素。 用户在嘈杂的环境中通话会产生回声和含混不清的音频。 用户在黑暗或低光照环境中则无法生成明亮清晰的视频图像画质。 在会议室设置中，麦克风和视频设备的位置对参与者接收的声音和图像质量有直接影响。
  
要更清晰地了解用户的音频和视频体验，请使用 Skype for Business 应用" **工具**">" **选项**">" **音频设备**"或" **视频设备**"更改使用中的设备并自定义其设置。也可以通过单击" **检查通话质量**"，检查通话的音频质量。如果单击" **检查通话质量**"，则可以报告通话质量和通话测试中发现的问题。
  
![Testing audio in the Skype for Business client.](../images/1730a71e-a09d-4702-8eb6-ef1346a091fa.png)
  
#### Network

通过 IP 网络的实时媒体质量很大程度上受到网络连接质量的影响，特别是以下各项：
  
- **延迟** 点 A 通过网络获得点 B 的 IP 数据包所需的时间。此种网络传播延迟主要与两点间的物理距离和光速（包括两点间各路由器的附加开销）有关。延迟使用单向时间或往返时间 (RTT) 测量。
    
- **数据包丢失率** 通常定义为给定时间窗口内丢失的数据包百分比。数据包丢失率直接影响音频质量：小型、单个数据包丢失几乎没有影响，而连续突发丢包会导致音频彻底中断。
    
- **跨包到达抖动或抖动** 这是连续数据包到达延迟的平均变化率。包括 Skype for Business 在内的大部分现代 VoIP 软件可通过缓冲接受一定程度的抖动。仅在抖动超过缓冲时，参与者才会注意到抖动的影响。
    
> [!注释]
>  抖动缓冲会增加端到端延迟。
  
对于许多并发 Skype for Business Online 实时媒体会话和其他 Office 365 服务及业务应用程序生成的网络流量来说，确保连接网络与 Skype for Business Online 服务的整个网络路径上有足够的带宽是避免网络拥堵、确保出色的实时媒体（音频、视频和应用程序共享）质量的关键。 
  
#### 在拥堵的网络上实施端到端服务质量 (QoS)

而且，网络上流量拥堵会极大地影响媒体质量。 要允许音频和视频数据包在拥堵的网络上比其他网络流量更快地传递且优先传递，使用服务质量 (QoS) 有助于提供最佳的音频和视频通信最终用户体验。
  
借助 QoS 可以为携带音频或视频数据的网络数据包分配更高的优先级。 通过为这些数据包分配更高的优先级，音频和视频通信有可能比涉及文件传输、网络浏览或数据库备份等的网络会话在网络上更快地传递，并且更少中断。 这是因为用于文件传输或数据库备份的网络数据包默认分配了"尽力而为"的优先级，而网络拥堵的影响不是很严重。 如果不为媒体（音频、视频和应用程序共享）数据包分配更高的优先级并将它们也指定为"尽力而为"，它们也将会和所有其他网络流量一起处理。 根据网络拥堵的程度，这可能会以整体较低的音频和视频用户体验而告终。
  
强烈建议在网络上实施端到端 QoS，以确保网络拥堵不会造成影响。 但是，所有网络连接端点必须支持 QoS，这意味着所有端点必须支持 QoS 标记和数据包优先处理。Skype for Business Online 服务在 Microsoft Network 内支持 QoS 标记和优先处理。但是在公共连接（例如从公司网络到 Microsoft Network 的 Internet）内路由的流量不保留 QoS 标记和数据包优先处理。使用 [Azure ExpressRoute](https://azure.microsoft.com/en-us/services/expressroute/) 从你的网络到 Office 365 的私有连接提供可保留 QoS 标记和数据包优先处理的部署解决方案，这样也会提高最终用户的整体音频和视频质量。
  
## 连接到 Skype for Business Online 的网络性能要求
<a name="bk_NetworkPerf"> </a>

Skype for Business 实时媒体在多种不同的设备、客户端应用、服务器软件中跨不同的网络传递。 实时媒体的端到端延迟是在所有组件和网段中出现的延迟总计。 端到端网络连接质量由质量最差的网段决定。 该网段视为此网络流量的瓶颈。
  
下图介绍会议中音频从一个 Skype for Business 参与者单向流到另一个参与者的情况。
  
![ExpressRoute Call Flow.](../images/c026e8e5-ba09-42c0-9e03-60fbfda1cb02.png)
  
在此会议情形中，媒体路径包括以下网段：
  
1. **从用户 1 到 Microsoft Network Edge 的连接** 这通常包括 WiFi 或以太网等网络连接、从用户 1 到 Internet 出口点（你的网络边缘设备）的 WAN 连接和从网络边缘到 Microsoft Network Edge 的 Internet 连接。
    
2. **Microsoft Network 内的连接** 这是 Microsoft Edge 与 Skype for Business Online 数据中心间的连接，在其中使用音频/视频会议服务器。
    
3. **Microsoft Network 内的连接** 这是 Skype for Business Online 数据中心与 Microsoft Network Edge 间的连接。
    
4. **从 Microsoft Network Edge 到用户 2 的连接** 这包括从网络边缘到 Microsoft Network Edge 的 Internet 连接、从用户 2 到 Internet 出口点（你的网络边缘）的 WAN 连接和 WiFi 或以太网等网络连接。
    
下图显示了 Skype for Business Online PSTN 呼叫的组件和网段的细分：
  
![ExpressRoute PSTN Carrier Call Flow.](../images/768a88df-c8a9-4171-a158-565a698f0193.png)
  
在 PSTN 呼叫场景中，媒体路径跨以下网段：
  
1. **从 Skype for Busines 客户端呼叫方到 Microsoft Network 的连接** 这通常包括 WiFi 或以太网等网络连接、从 Skype for Busines 客户端呼叫方到 Internet 出口点（你的网络边缘设备）的 WAN 连接和从网络边缘到 Microsoft Network Edge 的 Internet 连接。
    
2. **Microsoft Network 内的连接** 这是 Microsoft Edge 与 Skype for Business Online 数据中心间的连接，在其中使用中介服务器。
    
3. **Microsoft Network 内的连接** 这是 Skype for Business Online 数据中心与 Microsoft Network Edge 间的连接。
    
4. **Microsoft Network 和 PSTN 服务提供商合作伙伴间的连接** 存在这种连接是为了从 Microsoft Network 外的 Skype for Business 客户端进行 PSTN 呼叫。
    
### 从 Skype for Business 客户端到 Microsoft Network Edge 的网络性能要求
<a name="bk_SfBClienttoEdge"> </a>

要获得最佳 Skype for Business 媒体质量，对于从公司网络到 Microsoft Network Edge 的连接需要满足以下网络性能指标目标或阈值。 此网段包括你的内部网络，其中包括所有 WiFi 和以太网连接、通过 WAN 连接的任何公司站点到站点流量，例如多协议标签交换 (MPLS)，以及与 Microsoft Network Edge 的 Internet 或 ExpressRoute 合作伙伴连接。
  
> [!警告]
> **公司网络上的 Skype for Business 客户端与 Office 365 服务间的连接必须满足以下网络性能要求和阈值。**
  
|||
|:-----|:-----|
|**指标** <br/> |**目标** <br/> |
|延迟（单向）  <br/> |< 50 毫秒  <br/> |
|延迟（RTT 或往返时间）  <br/> |< 100 毫秒  <br/> |
|突发丢包率  <br/> |任意 200 毫秒间隔内 <10%  <br/> |
|数据包丢失  <br/> |任意 15 秒间隔内 <1%  <br/> |
|跨包到达抖动  <br/> |任意 15 秒间隔内 <30 毫秒  <br/> |
|数据包重新排序  <br/> |无序数据包 <0.05%  <br/> |
   
 **其他性能目标要求：**
  
- Microsoft Network 在全世界有超过 160 个 Edge 位置。 我们通过这些 Edge 站点与世界主要 Internet 服务提供商 (ISP) 合作。 延迟指标目标假设你的公司站点或多个站点与 Microsoft Edge 位于同一大洲。
    
- 公司站点与 Microsoft Network Edge 的连接包括采用 WiFi 或其他无线技术的第一跳网络访问。 
    
- 网络性能目标假设采用正确的带宽和/或服务质量方案。 换句话说，当网络连接处于高峰负载时，这直接适用于 Skype for Business 实时媒体流量。
    
### 从网络边缘到 Microsoft Network Edge 的网络性能要求
<a name="bk_YourNetworkEdge"> </a>

以下是连接网络边缘和 Microsoft Network Edge 所需的网络性能目标或阈值。 该网段不包括客户的内部网络或 WAN，并预计在通过 Internet 或 ExpressRoute 合作伙伴网络发送网络流量时作为你测试网络流量的指导，此外也可在与 ExpressRoute 提供商协商性能服务等级协议时使用。
  
> [!警告]
> **公司网络边缘与 Microsoft Network Edge 间的连接必须满足以下网络性能要求和阈值。**
  
|||
|:-----|:-----|
|**指标** <br/> |**目标** <br/> |
|延迟（单向）  <br/> |< 30 毫秒  <br/> |
|延迟 (RTT)  <br/> |< 60 毫秒  <br/> |
|突发丢包率  <br/> |任意 200 毫秒间隔内 <1%  <br/> |
|数据包丢失  <br/> |任意 15 秒间隔内 <0.1%  <br/> |
|跨包到达抖动  <br/> |任意 15 秒间隔内 <15 毫秒  <br/> |
|数据包重新排序  <br/> |无序数据包 <0.01%  <br/> |
   
 **其他性能目标要求：**
  
- 性能目标要求任何公司网络边缘与其最近的 Microsoft Network Edge 间的连接位于同一大洲内。
    
- 网络性能目标假设采用了正确的带宽和/或服务质量方案。当网络连接处于高峰负载时，这也直接适用于 Skype for Business 实时媒体流量。有关正确的带宽和 QoS 方案，请参见 [Skype for Business Online 中的 ExpressRoute 和 QoS](https://support.office.com/en-us/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d?ui=en-US&amp;rs=en-US&amp;ad=US)。
    
## 测量网络性能
<a name="bk_NetworkPerf"> </a>

要评估从任意公司网络站点到 Microsoft Edge 的实际网络性能，特别是延迟和丢包率，可以使用 ping、PSPinghttps://technet.microsoft.com/en-us/sysinternals/psping.aspx、tcpinghttp://www.elifulkerson.com/projects/tcping.php 等工具对从 Microsoft Edge 和数据中心站点运行的一系列 Skype for Business 媒体中继服务进行测试。 
  
测试与 Microsoft Network 的 Internet 连接时，建议对以下媒体中继 VIP 进行测试。 *任播 VIP*  将解析为离测试位置最近的 Microsoft Edge 站点上媒体中继的 IP 地址。
  
||||
|:-----|:-----|:-----|
|**IP 地址** <br/> |**类型** <br/> |**位置** <br/> |
|13.107.8.2  <br/> |VIP  <br/> |全球任播 IP  <br/> |
   
 **下面概述了评估网络性能时要遵循的一些建议：**
  
- 你应评估内部网络和 Office 365 连接。
    
- 你应在一段较长的时间内对所有网络进行评估并收集数据。 我们建议对至少一周内的网络性能进行测试，以便了解所有营业日和营业时间内的使用情况。 这会显示高峰时段。
    
- 你应在网络性能测量中多次取样。 我们建议在收集数据的整个时间段内每 10 分钟从公司站点测量一次。 为比较 Skype for Business Online 网络性能要求，请从该样本数据集抽取 90% 的测量值。 
    
- 你应持续评估网络性能。由于使用方式改变、基于企业的新应用程序使用大量带宽以及组织或公司物理位置更改，网络使用率会随时间而变化。 你务必要持续监视网络性能是否满足这些网络性能要求和目标/阈值，并及时作出判断以确保最佳的实时媒体质量。 
    
## Measuring Network Performance using Azure VMs
<a name="bk_NetworkPerf"> </a>

Instead of testing against the Microsoft network Edge sites, there are network assessment solutions from Skype for Business customers and partners that leverage testing setup for services in the Microsoft Azure cloud. In those solutions, the network assessment tools test latency, packet loss and jitter against custom endpoints set up as a service in the Azure cloud. As a result, the test network traffic travels through one additional network segment, which is the connection within the Microsoft network between the network edges and Azure data centers that hosts the network assessment service.
  
For those network assessment solutions based on Azure hosted testing services. We recommend performing the network assessment within country and/or region. For example, for customer sites in east U.S., the assessment should be performed against a testing service instance hosted in Azure's east US data center region. 
  
Below are the latency (RTT) targets for the Azure service based network assessment setup. The one-way latency targets will be half of the corresponding RTT targets. The packet loss and jitter goals stays the same as those defined for Skype Media Relay based testing.
  
|||||
|:-----|:-----|:-----|:-----|
|**Customer region** <br/> |**Azure region** <br/> |**Your network Edge - Azure Round-trip Time (RTT)** <br/> |**Your Site - Azure Round-trip Time (RTT)** <br/> |
|Central US  <br/> |Central US  <br/> |99  <br/> |139  <br/> |
|East US  <br/> |East US  <br/> |86  <br/> |1:26  <br/> |
|North Central US  <br/> |North Central US  <br/> |Excel 97  <br/> |1:37  <br/> |
|South Central US  <br/> |South Central US  <br/> |94  <br/> |1:34  <br/> |
|West US  <br/> |West US  <br/> |94  <br/> |1:34  <br/> |
|Hawaii US  <br/> |West US  <br/> |1:16  <br/> |1:56  <br/> |
|Canada Central  <br/> |Canada Central  <br/> |1:38  <br/> |178  <br/> |
|Canada East  <br/> |Canada East  <br/> |1-31  <br/> |1.71  <br/> |
|North Europe  <br/> |North Europe  <br/> |99  <br/> |139  <br/> |
|West Europe  <br/> |West Europe  <br/> |95  <br/> |-135  <br/> |
|联系人(东亚地址)  <br/> |联系人(东亚地址)  <br/> |1:18  <br/> |1:58  <br/> |
|Southeast Asia  <br/> |Southeast Asia  <br/> |Excel 97  <br/> |1:37  <br/> |
|Japan East  <br/> |Japan East  <br/> |1:11  <br/> |1:51  <br/> |
|Japan West  <br/> |Japan West  <br/> |1:18  <br/> |1:58  <br/> |
|Brazil South  <br/> |Brazil South  <br/> |70  <br/> |110 (0x6E)  <br/> |
|Australia East  <br/> |Australia East  <br/> |1:24  <br/> |16^4  <br/> |
|Australia Southeast  <br/> |Australia Southeast  <br/> |1:24  <br/> |16^4  <br/> |
|Central India  <br/> |Central India  <br/> |103  <br/> |143  <br/> |
|South India  <br/> |South India  <br/> |103  <br/> |143  <br/> |
|West India  <br/> |West India  <br/> |103  <br/> |143  <br/> |
|China East  <br/> |China East  <br/> |1:20  <br/> |160%  <br/> |
|China North  <br/> |China North  <br/> |1:20  <br/> |160%  <br/> |
   
## 媒体质量和 ExpressRoute
<a name="bk_NetworkPerf"> </a>

Azure ExpressRoute for Office 365 是一个不通过公共 Internet 连接到 Office 365 的专用网络连接。 它使客户可以控制其 Office 365 网络流量使用的路径。 客户无需再关注 Internet 上发生的不可预测的路由，这些路由中的数据将由未知运营商、提供商和 ISP 处理。 通过 ExpressRoute 发送的网络流量直接通过 ExpressRoute 合作伙伴网络发送给 Microsoft 的网络。 这允许客户将使用专线连接的 Office 365 视为位于自己的异地数据中心内。
  
所有 Office 365 许可产品中都提供 Azure ExpressRoute。但是，Office 365 需要 Azure ExpressRoute 高级版附加项以启用全球路由。具有至少 500 个席位且实施 ExpressRoute 的 Office 365 客户可以免费获得所需的  *ExpressRoute 高级版附加项*  。
  
### 要获得出色的媒体质量必须要有 ExpressRoute 吗？

要获得最佳的 Skype for Business Online 媒体质量，Azure ExpressRoute 并非必需。 但它是可帮助你确保云连接满足 Skype for Business 网络性能目标或阈值的部署选项之一。
  
Office 365 是使用 Internet 的高性能且安全的服务。 我们一如既往地保持对新安全功能和区域边缘节点的投入，以不断提高安全性和性能。 Azure ExpressRoute 不是包括 Skype for Business Online 在内的 Office 365 服务所必需的。 Azure ExpressRoute 是一个可用的部署选项，有助于确保与 Office 365 的连接满足 Skype for Business 网络性能要求，并确保最佳的 Skype for Business Online 媒体质量体验。
  
对于 Skype for Business Online 媒体质量来说，务必要使公司站点和 Microsoft Network Edge 之间的连接满足[从 Skype for Business 客户端到 Microsoft Network Edge 的网络性能要求](media-quality-and-network-connectivity-performance-in-skype-for-business-online.md#bk_SfBClienttoEdge)中的性能目标，并确保网络边缘和 Microsoft Network Edge 间的连接满足[从网络边缘到 Microsoft Network Edge 的网络性能要求](media-quality-and-network-connectivity-performance-in-skype-for-business-online.md#bk_YourNetworkEdge)中的性能目标。 
  
另外很重要的一点是，包括内部网络和云连接容量在内的公司物理网络连接能够应对高峰媒体流量。 Azure ExpressRoute 是帮助客户确保 Skype for Business Online 云连接满足所有这些性能要求的众多方法中的一种。
  
### 对于语音质量 SLA 来说，ExpressRoute 是必需的吗？

不，ExpressRoute 不是 Skype for Business Online 语音质量 SLA 所必需的。[Skype for Business Online 语音质量 SLA](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;DocumentTypeId=37) 适用于 Skype for Business Online 语音服务用户进行的任何通话，只要这些通话在授权用户进行任何类型 VoIP 或 PSTN 呼叫的正确许可证和订阅规定范围内。语音质量 SLA 应包括所有下述条件：
  
- 来自 Microsoft 认证的 IP 电话的呼叫。
    
- 有线以太网连接。
    
- 由于 Microsoft Network 问题导致的语音质量问题。
    
> [!注释]
> 语音质量 SLA 不包括：由包含 ExpressRoute 合作伙伴网络和其他网络在内的非 Microsoft 网络引起的低通话质量呼叫。 
  
### Internet 或 Azure ExpressRoute？

在决定 Skype for Business Online 的网络连接选项前，客户必须根据[连接到 Skype for Business Online 的网络性能要求](media-quality-and-network-connectivity-performance-in-skype-for-business-online.md#bk_NetworkPerf)中描述的网络性能要求评估其网络和当前 Internet 连接。
  
如果当前 Internet 连接上的网络性能设置有应对高峰时刻的足够容量且符合站点到 Microsoft Network Edge 和网络边缘到 Microsoft Network Edge 的网络性能要求，则可以继续使用现有 Internet 连接来连接到 Skype for Business Online。
  
对于未满足网络性能要求的公司站点来说，我们强烈建议首先与你的现有网络服务提供商沟通，以提高整体网络性能。 但如果仍不满足要求，使用 Azure ExpressRout 可有助于确保 Skype for Business Online 云连接满足网络性能要求。
  
Azure ExpressRoute 提供以下附加优势：
  
- 关于你的网络和 Microsoft Network 之间的连接可用性的服务等级协议 (SLA)。 保证 ExpressRoute 的可用性 SLA 达 99.9%。
    
- 为 Office 365 服务提供所需的计划内和有保证的带宽。 只需使用 ExpressRoute 发送 Office 365 或 Skype for Business 流量，然后让所有其他 Internet 流量经过网络中的其他 Internet 出口点/入口点，就可以实现此目标。
    
- ExpressRoute is designed to preserve DSCP QoS markings between your network and the Microsoft Network.
    
有关 ExpressRoute QoS 和容量规划的详细详细，请参见 [Skype for Business Online 中的 ExpressRoute 和 QoS](https://support.office.com/en-us/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d?ui=en-US&amp;rs=en-US&amp;ad=US)。
  
### 我可以只为 Skype for Business Online 设置 Azure ExpressRoute 吗？

是的，你可以设置 Azure ExpressRoute，以确保公司网络仅与 Skype for Business Online 之间的优质网络连接。 这将为用户提供最佳实时媒体质量，但你可以继续通过 Internet 连接其他 Office 365 服务。
  
The Border Gateway Protocol (BGP) is a routing protocol on the Internet that is used to route network traffic across the Internet. It is designed to exchange routing information between autonomous systems (AS) found across the Internet. BGP communities values are attribute tags that can be applied to incoming or outgoing routes. BGP communities are often used to signal to the receiving AS which outbound link to use to reach a given destination based on geography, service type or other criteria.
  
在 BGP 社区支持方面，Microsoft 会根据前缀和路由所属的服务，以适当的 BGP 社区值对其进行标记。Microsoft 会使用表示前缀所属地区的适当 BGP 社区值标记通过公共对等和 Microsoft 对等通告的前缀。你可以根据该社区值做出适当的路由决定，以提供最佳路由。可以使用 Skype for Business Online BGP 社区值设置仅适用于 Skype for Business Online 的 ExpressRoute 连接。更多信息，请参见 [ExpressRoute 路由要求](https://azure.microsoft.com/en-us/documentation/articles/expressroute-routing/)。
  
## 适用于 Skype for Business Online 的 ExpressRoute 连接情形
<a name="bk_NetworkPerf"> </a>

如果基于上述建议你决定 ExpressRoute 是适合你的选项，此处提供应在哪里获得 ExpressRoute 连接以及应获得多少 ExpressRoute 连接的建议。
  
### 仅联机部署 - 单一站点

如果你的所有用户都使用 Skype for Business Online 服务，且你的办公区围绕一个物理位置布局，同时你决定部署 Azure ExpressRoute，你应当在公司站点和最近的 [ExpressRoute 对等位置](https://azure.microsoft.com/en-us/documentation/articles/expressroute-locations/)间建立单一 ExpressRoute 连接。
  
下图显示这种部署类型的示例。 在此例中，Contoso 是位于佛罗里达奥兰多的一所大学，教职员工和学生人数达到一万。 从该位置到 Microsoft Edge 站点的 Internet 测试显示高峰上课时间丢包率大于 5%。 他们打算使用带宽超量配置的 ExpressRoute 专线连接到 Office 365，以避免 Office 365 网络拥堵，特别是 Skype for Business Online 实时流量拥堵。 他们通过位于佐治亚州亚特兰大 MeetMe 站点的 ExpressRoute 连接到 Microsoft 云。
  
![ExpressRoute Single Site.](../images/59fbca3c-a3ea-4568-8da5-3281096a7453.png)
  
### 仅联机部署 - 同一大洲内多个站点

如果公司同一地区或大洲内的多个办公室均使用 Skype for Business Online 服务，而且你打算实施 Azure ExpressRoute，建议通过 ExpressRoute 连接主站点，然后有选择地为其他不满足建议网络性能目标的位置添加额外 ExpressRoute 对等。
  
在下例中，Contoso 是一家美国旅行服务公司，总部位于纽约，其他办公室遍布美国各州。 这些通过 WAN 内部互连的办公室使用 MPLS 连接到 Office 365。 起初，他们通过新泽西霍博肯的 Internet 路由器建立与纽约 MeetMe 站点的 ExpressRoute 连接。 
  
就此设置来说，大多数站点到 Microsoft Network（纽约边缘站点）的网络流量符合[从 Skype for Business 客户端到 Microsoft Network Edge 的网络性能要求](media-quality-and-network-connectivity-performance-in-skype-for-business-online.md#bk_SfBClienttoEdge)中描述的 Skype for Business 客户端连接网络性能目标。但是，Contoso 西海岸办公室到纽约间的单向延迟超过 50 毫秒。此外，檀香山是 Contoso 的第二大办公室所在地，从檀香山到纽约的单向延迟超过 80 毫秒。为保证这些办公室中用户的良好媒体质量，Contoso 决定在圣约瑟站点和硅谷的 ExpressRoute MeetMe 站点间增加西海岸 ExpressRoute 连接。
  
![Express Router Multi-site on the same continent.](../images/bf57a473-01e1-4271-9675-385767bc58e1.png)
  
### 仅联机部署 - 不同大洲间多个站点

如果你的所有用户均使用 Skype for Business Online 服务，且你的办公室位于跨多个洲的多个物理位置，如果你决定部署 Azure ExpressRoute，应在每个洲的主站点到其最近的 [ExpressRoute 对等位置](https://azure.microsoft.com/en-us/documentation/articles/expressroute-locations/)间建立至少一个 ExpressRoute 连接。根据成本-效益比，你可以选择从不满足网络性能目标的站点部署其他 ExpressRoute 连接。
  
在下例中，Contoso 是一家大型法人律师事务所，办公室遍布北美和欧洲的各大主要城市。 根据其 Internet 连接和内部网络性能评估，Contoso 决定在北美部署两个 ExpressRoute 连接，并为所有欧洲办公室部署一个 ExpressRoute 回路。
  
![ExpressRoute with multiple sites and continents.](../images/c967550b-dc85-4b37-a7bc-cd825ec86854.png)
  
### 混合部署

如果你部署了内部 Lync 或 Skype for Business 并选择实施混合 Skype for Business Online 集成，我们建议如果你决定部署 Azure ExpressRoute，每个内部 Lync 或 Skype for Business 站点至少需要一个 ExpressRout 连接，办公室所在的每个大洲至少需要一个 ExpressRout 连接。 根据成本-效益比，对于每个大洲你可以选择从不满足网络性能目标的办公室部署其他 ExpressRoute 连接。
  
如果你部署了内部 Skype for Business，则必须遵循 [边缘服务器规划和部署指南](https://technet.microsoft.com/en-us/library/mt346417.aspx)。特别是，必须可以从网络外部到达边缘服务器。这通常通过为边缘服务器分配可路由的公共 IP 地址或使用网络地址转换 (NAT) 来实现。
  
在下例中，Contoso 当前部署了内部 Skype for Business 企业版语音。 他们想将内部用户迁移到 Office 365 联机服务。 他们还决定使用混合部署，以便所有内部和联机用户还可以继续使用现有的 PSTN 基础架构。 Contoso 的内部数据中心和 Skype for Business边缘服务器位于芝加哥。 对于其部署，Contoso 决定在芝加哥数据中心和芝加哥 ExpressRoute 间建立一个 ExpressRoute 连接。 为更好地服务于檀香山办公室，他们还增加了西海岸 ExpressRoute 连接。
  
![ExpressRoute Hybrid.](../images/a7467c56-642f-44e5-adfb-ecca91ba2dd3.png)
  
### 采用 Cloud Connector Edition 的联机部署

Skype for Business Online Cloud Connector Edition 是一个混合产品，由一组打包的执行内部 PSTN 连接的虚拟机组成。 通过在虚拟化环境中部署最少的 Skype for Business 服务器拓扑，你可以使用座机和手机通过现有内部 PSTN 语音基础架构发送和接收呼叫。
  
如果决定部署 Azure ExpressRoute 和 Cloud Connector Edition，我们建议在每个大洲的主站点至其最近的 [ExpressRoute 对等位置](https://azure.microsoft.com/en-us/documentation/articles/expressroute-locations/)间至少建立一个 Express Route 连接。根据成本-效益比，对于每个大洲你可以选择从不满足网络性能目标的站点部署其他 ExpressRoute 连接。
  
如果你部署了内部 Skype for Business，则必须遵循 [Skype for Business Cloud Connector Edition 规划指南](https://technet.microsoft.com/EN-US/library/mt605227.aspx)。特别是，应为访问边缘和音频/视频边缘服务分配公共 IP 地址，且可从 Office 365 数据中心访问这些服务。
  
在下例中，Contoso 是一家欧洲会计公司，在欧洲几个主要国家和城市都有办事处。完全出于协作需求，他们注册了 Skype for Business Online，并决定在每个有实体办事处的国家放置一个 Cloud Connector，以继续使用其 PSTN 基础架构和现有的运营商合约。根据从所有站点和 Microsoft Network Edge 进行的测试，他们认为在伦敦建立单个 ExpressRoute 连接有助于满足[从 Skype for Business 客户端到 Microsoft Network Edge 的网络性能要求](media-quality-and-network-connectivity-performance-in-skype-for-business-online.md#bk_SfBClienttoEdge)中描述的 Skype for Business 客户端连接网络性能目标。
  
![ExpressRoute Cloud Connector One.](../images/ebdc96e5-b22a-4bf2-b668-062460b4b890.png)
  
下面是 Contoso 的另一个部署选项。在此情况下，他们决定在部署了 Cloud Connector 的每个站点建立一个 ExpressRoute 连接。
  
![ExpressRoute Cloud Connector Two.](../images/06d967a9-64f5-4d7d-98ed-3f3add1b7c2b.png)
  
## 另请参阅
<a name="bk_NetworkPerf"> </a>

#### 其他资源

[Skype for Business Online 中的 ExpressRoute 和 QoS](20c654da-30ee-4e4f-a764-8b7d8844431d.md)

