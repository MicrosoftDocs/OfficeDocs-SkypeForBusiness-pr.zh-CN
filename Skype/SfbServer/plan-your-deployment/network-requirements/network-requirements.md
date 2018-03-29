---
title: 规划 Skype for Business 2015 的网络要求
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 35c7bb3f-8e0f-48b7-8a2c-857d4b42a4c4
description: 'Summary: Review the network component considerations below before implementing Skype for Business Server 2015.'
ms.openlocfilehash: 3d3fd2141da93a9b0b866fe44e2ed8dee6942f3b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="plan-network-requirements-for-skype-for-business-2015"></a>规划 Skype for Business 2015 的网络要求
 
**Summary:** Review the network component considerations below before implementing Skype for Business Server 2015.
  
The information in these topics is also discussed in the whitepaper [Network Planning, Monitoring, and Troubleshooting with Lync Server](https://www.microsoft.com/en-us/download/details.aspx?id=39084) with additional details and depth. While the content refers explicitly to Lync 2010 and Lync 2013, the considerations for Skype for Business Server 2015 are unchanged.
  
Likewise, if your network involves wi-fi as well as wired access, the whitepaper [Delivering Lync 2013 Real-Time Communications over Wi-Fi](http://www.microsoft.com/en-us/download/details.aspx?id=36494) is a good reference and is equally applicable to Skype for Business Server 2015.
  
网络性能和需求与网络的流量负载直接相关。 When planning your network and server implementations we recommend making use of the [Skype for Business Server 2015 Planning Tool](../../management-tools/planning-tool/planning-tool.md), the [Skype for Business Server 2015 Capacity Planning Calculator](../../management-tools/capacity-planning-calculator.md), and the [Skype for Business Server 2015 Stress and Performance Tool](../../management-tools/stress-and-performance-tool/stress-and-performance-tool.md).
  
## <a name="server-hardware"></a>服务器硬件
<a name="S_hard"> </a>

The network adapter of each server in the Skype for Business Server topology must support at least 1 gigabit per second (Gbps). In general, you should connect all server roles within the Skype for Business Server topology using a low latency and high bandwidth local area network (LAN). LAN 的大小取决于拓扑的大小： 
  
- In Standard Edition topologies, servers should be in a network that supports 1 Gbps Ethernet or equivalent.
    
- In Enterprise Edition topologies, most servers should be in a network that supports more than 1 Gbps, especially when supporting audio/video (A/V) conferencing and application sharing.
    
对于公用电话交换网 (PSTN) 集成，可以使用 T1/E1 线路或 SIP 中继进行集成。
  
## <a name="audiovideo-network-requirements"></a>音频/视频网络要求
<a name="AV_req"> </a>

Network requirements for audio/video (A/V) in a Skype for Business Server deployment include the following:
  
- If you are deploying a single Edge Server or an Edge pool using DNS load balancing, you can configure the  _external_ firewall to perform network address translation (NAT). You can't configure the _internal_ firewall to perform NAT. For details, see [Determining Firewall and 50k Port Range Requirements](http://technet.microsoft.com/library/3b849dc7-175d-40d1-820d-80e6ade6d332.aspx).
    
    > [!IMPORTANT]
    > If you have an Edge pool and are using a hardware load balancer, you must use public IP addresses on the Edge Servers and you can't use NAT for the servers or the pool at your NAT-capable device (for example, a firewall appliance or LAN switch. For details, see [Port Summary - Scaled Consolidated Edge with Hardware Load Balancers](http://technet.microsoft.com/library/91213b1e-f875-464b-83e8-fe3a351595a4.aspx). 
  
- 如果您的组织使用了服务质量 (QoS) 基础结构，则媒体子系统应设计为在此现有基础结构中工作。 
    
- 如果使用 Internet 协议安全性 (IPsec)，建议在用于 A/V 流量的端口范围内禁用 IPsec。 For details, see [IPsec Exceptions](http://technet.microsoft.com/library/241f1eca-6f2f-44de-90b1-2cb659cbe27c.aspx).
    
要提供最佳媒体质量，请执行以下操作：
  
- 设置网络链接，使之在高峰使用时段支持每个音频流 65 千位每秒 (Kbps) 和每个视频流（如果启用）500 Kbps 的吞吐量。 双向音频或视频会话使用两个流，因此简单的音频/电话连接需要 130Kbps 才能覆盖每个流。 Video will likewise use 1000 Kbps total to carry an upstream and downstream connection. 
    
- To cope with unexpected spikes in traffic and increased usage over time, Skype for Business Server media endpoints can adapt to varying network conditions and support three times the throughput for audio and video while still maintaining acceptable quality. 不要认为这种适应性能够掩盖未充分设置的网络中的问题。 In an under-provisioned network, the ability of the Skype for Business Server media endpoints to dynamically deal with varying network conditions (for example, temporary high packet loss) is reduced.
    
- 如果网络链路的设置成本很高，而且难于操作，可能就需要考虑设置较低的流量。 In this scenario, let the elasticity of the Skype for Business Server media endpoints absorb the difference between the traffic volume and the peak traffic level, at the cost of some reduction in the voice quality. 此外，可用于吸收流量中的突发峰值的空间也会减少。
    
- 对于短期内无法正确设置的链路（例如 WAN 链路很差的站点），考虑对某些用户禁用视频。
    
- 配置网络，确保在高峰负载下的最大端到端延迟为 150 毫秒 (ms)。 Latency is the one network impairment that Skype for Business Server media components can't reduce, and it is important to find and eliminate the weak points.
    
- For servers that are running antivirus software, include all servers that are running Skype for Business Server in the exception list to provide optimal performance and audio quality. 
    
## <a name="conferencing-network-requirements"></a>会议网络要求
<a name="Conf_req"> </a>

The bandwidth used to download conference content from the Internet Information Services (IIS) server depends on the size of the content. 您可以选择监控实际使用情况并对带宽计划作出相应的调整。
  
## <a name="network-bandwidth-requirements-for-media-traffic"></a>媒体流量的网络带宽要求
<a name="Conf_req"> </a>

An important part of network planning is ensuring that your network can handle the media traffic generated by Skype for Business Server. 本节帮助您规划媒体流量。 
  
### <a name="media-traffic-network-usage"></a>媒体流量网络使用情况
<a name="Net_req"> </a>

媒体流量带宽使用量可能由于不同变量（如编解码器使用、分辨率和活动级别）的数量而难于计算。 带宽使用量是使用的编解码器和流活动的一种功能，这两者在不同的方案中各不相同。 The following table lists the audio codecs typically used in Skype for Business Server scenarios.
  
**Audio codec bandwidth**

|**Audio codec**|**Scenario**|**Audio payload bit rate (KBPS)**|**Bandwidth audio payload and IP header only (Kbps)**|**Bandwidth audio payload, IP header, UDP, RTP and SRTP (Kbps)**|**Bandwidth audio payload, IP header, UDP, RTP, SRTP and forward error correction (Kbps)**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|RTAudio 宽带  <br/> |对等  <br/> |29.0  <br/> |45.0  <br/> |57.0  <br/> |86.0  <br/> |
|RTAudio 窄带  <br/> |对等 PSTN  <br/> |11.8  <br/> |27.8  <br/> |39.8  <br/> |51.6  <br/> |
|G.722  <br/> |会议  <br/> |64.0  <br/> |80.0  <br/> |95.6  <br/> |159.6  <br/> |
|G.722 立体声  <br/> |对等会议  <br/> |128.0  <br/> |144.0  <br/> |159.6  <br/> |223.6  <br/> |
|G.711  <br/> |PSTN，会议  <br/> |64.0  <br/> |80.0  <br/> |92.0  <br/> |156.0  <br/> |
|Siren  <br/> |会议  <br/> |16.0  <br/> |32.0  <br/> |47.6  <br/> |63.6  <br/> |
|SILK 宽带  <br/> |对等  <br/> |36.0  <br/> |52.0  <br/> |64.0  <br/> |100.0  <br/> |
|SILK 宽带  <br/> |对等  <br/> |26.0  <br/> |42.0  <br/> |54.0  <br/> |80.0  <br/> |
|SILK 宽带  <br/> |对等  <br/> |20.0  <br/> |36.0  <br/> |48.0  <br/> |68.0  <br/> |
|SILK wideband/narrowband  <br/> |对等  <br/> |13.0  <br/> |29.0  <br/> |41.0  <br/> |54.0  <br/> |
   
上表中的带宽数值基于 Siren 和 G.722 编解码器的 20 毫秒数据分包（每秒 50 个数据包），其中包含其他安全实时传输协议 (SRTP) 开销（在会议方案中），并假定流是 100% 活动的。如果链接上出现数据包丢失，则会以动态方式使用前向纠错 (FEC) 以帮助维护音频流的质量。 
  
G.722 编解码器的立体声版本由基于 Lync Room System 的系统使用，Lync Room System 使用一个立体声麦克风或一对单声道麦克风以允许收听者更好地辨别会议室中的多个讲话人。
  
**Video Resolution Bandwidth**

|**Video codec**|**Resolution and aspect ratio**|**Maximum video payload bit rate (Kbps)**|**Minimum video payload bit rate (Kbps)**|
|:-----|:-----|:-----|:-----|
|H.264  <br/> |320x180 (16:9)  <br/> 212x160 (4:3)  <br/> |250  <br/> |15  <br/> |
|H.264/RTVideo  <br/> |424x240 (16:9))  <br/> 320x240 (4:3  <br/> |350  <br/> |100  <br/> |
|H.264  <br/> |480x270 (16:9)  <br/> 424x320 (4:3)  <br/> |450  <br/> |200  <br/> |
|H.264/RTVideo  <br/> |640x360 (16:9)  <br/> 640x480 (4:3)  <br/> |800  <br/> |300  <br/> |
|H.264  <br/> |848x480 (16:9)  <br/> |1500  <br/> |400  <br/> |
|H.264  <br/> |960x540 (16:9)  <br/> |2000  <br/> |500  <br/> |
|H.264/RTVideo  <br/> |1280x720 (16:9)  <br/> |2500  <br/> |700  <br/> |
|H.264  <br/> |1920x1080 (16:9)  <br/> |4000  <br/> |1500  <br/> |
|H.264/RTVideo  <br/> |960x144 (20:3)  <br/> |500  <br/> |15  <br/> |
|H.264  <br/> |1280x192 (20:3)  <br/> |1000  <br/> |250  <br/> |
|H.264  <br/> |1920x288 (20:3)  <br/> |2000  <br/> |500  <br/> |
   
视频的默认编解码器为 H.264/MPEG-4 Part 10 高级视频编码标准及其可扩展的用于临时可扩展性的视频编码扩展。 To maintain interoperability with legacy clients, the RTVideo codec is still used for peer-to-peer calls between Skype for Business Server and legacy clients. In conference sessions with both Skype for Business Server and legacy clients the Skype for Business Server endpoint may encode the video using both video codecs and send the H.264 bitstream to the Skype for Business Server clients and the RTVideo bitstream to legacy clients.
  
所需的带宽取决于分辨率、质量、帧速率和图像中的运动或变化量。每种分辨率都有两个相关的比特率：
  
- **Maximum payload bit rate** This is the bit rate that an endpoint will use for resolution at the maximum frame rate. 此值可实现最高的视频和音频质量。
    
- **Minimum payload bit rate** This is the bit rate below which a Skype for Business Server endpoint will switch to the next lower resolution. 为了保证特定分辨率，可用的视频负载比特率不得低于该分辨率的此最低比特率。 利用此值，您可以了解在最大比特率不可用或不切实际时可能实现的最低值。 对于部分用户，此低比特率视频体验可能被视为无法接受的视频体验，因此在考虑使用这些最低视频负载比特率时应十分谨慎。 请注意，对于静态无变化的视频场景，实际比特率可能会暂时低于此最小比特率。
    
Skype for Business Server supports many resolutions. This allows Skype for Business Server to adjust to different network bandwidth and receiving client capabilities. The default aspect ratio for Skype for Business Server is 16:9. The legacy 4:3 aspect ratio is still supported for webcams which don't allow capture in the 16:9 aspect ratio.
  
使用视频负载比特率时，其中始终包含视频 FEC，因此，无论使用或不使用视频 FEC，值都相同。 
  
终结点不会持续流出音频或视频数据包。根据不同的方案，流活动的级别也不同，这些级别指示为流发送数据包的频率。流活动取决于媒体和方案，而不依赖使用的编解码器。在对等方案中： 
  
- 仅当用户通话时终结点才发送音频流。
    
- 参与双方都会接收到音频流。
    
- 如果使用视频，则双方终结点都会在呼叫过程中发送和接收视频流。
    
- 对于静态视频场景，实际比特率可能会暂时变得很低，因为视频编解码器将跳过编码视频区域的步骤，从前一示例起不作任何更改。
    
在会议方案中：
  
- 仅当用户通话时终结点才发送音频流。
    
- 所有参与者都会接收到音频流。
    
- 如果使用视频，则所有参与者最多将收到 5 个接收视频流和 1 个全景（例如，纵横比 20:3）视频流。 默认情况下，5 个接收视频流是基于当前发言人历史记录的，但用户还可手动选择要从其接收视频流的参与者。 如果启用多视频，则每个视频流的分辨率和带宽要求将更低。
    
- Each participant that turns on the user's send video stream will send one or more video streams. Skype for Business Server has the capability of sending up to five video streams to optimize the video quality for all the receiving clients. 将发送的视频流的实际数量由发送方根据 CPU 容量、可用上行链路带宽和请求特定视频流的接收客户端的数量确定。 最常见的情况是，在旧客户端加入会议的情况下发送 1 个 H.264 和 1 个 RTVideo 视频流。 另一常见方案是，发送若干 H.264 视频流（例如，使用不同视频分辨率）以适应不同的接收方请求。 
    
除音频和视频媒体的实时传输协议 (RTP) 流量所需的带宽之外，实时传输控制协议 (RTCP) 也需要带宽。RTCP 用于报告 RTP 流的统计信息和带外控制。规划时，请使用下表中的带宽数值规划 RTCP 流量。这些值代表用于 RTCP 的最大带宽，并且因控制数据不同，音频流和视频流的这些值也有所不同。 
  
**RTCP Bandwidth**

|**媒体**|**RTCP maximum bandwidth (Kbps)**|
|:-----|:-----|
|音频  <br/> |5  <br/> |
|视频（仅正在发送/接收的 H.264 或 RTVideo）  <br/> |10  <br/> |
|视频（正在发送/接收的 H.264 和 RTVideo）  <br/> |15  <br/> |
   
出于容量规划的目的，以下两项统计数据十分重要：
  
- **Maximum bandwidth without FEC** The maximum bandwidth that a stream will consume. This includes the typical activity of the stream and the typical codec that is used in the scenario without FEC. This is the bandwidth when the stream is at 100% activity and there is no packet loss triggering the use of FEC. This is useful for computing how much bandwidth must be allocated to allow the codec to be used in a given scenario. FEC is not expected to be a requirement on a managed network.
    
- **Maximum bandwidth with FEC** The maximum bandwidth that a stream consumes. This includes the typical activity of the stream and the typical codec that is used in the scenario with FEC. This is the bandwidth when the stream is at 100% activity and there is packet loss triggering the use of FEC to improve quality. This is useful for computing how much bandwidth must be allocated to allow the codec to be used in a given scenario and allow the use of FEC to preserve quality under packet-loss conditions.
    
下表中还列出了另一个带宽值，**典型带宽**。 这是流使用的平均带宽。 这包括方案中的典型流活动和使用的典型编解码器。 此带宽可用于估计在给定时间媒体流量使用的带宽量，但不应用于容量规划，因为活动级别高于平均水平时，个别呼叫会超过该值。 下表中的典型视频流带宽基于在测得的客户数据中观察到的不同视频分辨率的组合，较小的安装具备的实际数量可能与表中数据不同。 For example, in peer-to-peer sessions most users would use the default video render window whereas some percentage of users would increase or maximize the Skype for Business Server application to allow better video resolutions.
  
下表提供了适用于不同方案的值。
  
**Audio/Video Capacity Planning for Peer-to-Peer Sessions**

|**媒体**|**Codec**|**Typical stream bandwidth (Kbps)**|**Maximum stream bandwidth without FEC**|**最大流的带宽和 FEC**|
|:-----|:-----|:-----|:-----|:-----|
|音频  <br/> |RTAudio 宽带  <br/> |39.8  <br/> |62  <br/> |91  <br/> |
|音频  <br/> |RTAudio 窄带  <br/> |29.3  <br/> |44.8  <br/> |56.6  <br/> |
|音频  <br/> |SILK 宽带  <br/> |44.3  <br/> |69  <br/> |105  <br/> |
|Main video when calling Skype for Business Server endpoints  <br/> |H.264  <br/> |460  <br/> |4010（用于最大分辨率 1920x1080）  <br/> |已包含  <br/> |
|Main video when calling Lync 2010 or Office Communicator 2007 R2 endpoints  <br/> |RTVideo  <br/> |460  <br/> |2510（用于最大分辨率 1280x720）  <br/> |已包含  <br/> |
|Panoramic video when calling Skype for Business Server endpoints  <br/> |H.264  <br/> |190  <br/> |2010（用于最大分辨率 1920x288）  <br/> |已包含  <br/> |
|Panoramic video when calling Lync 2010 endpoints  <br/> |RTVideo  <br/> |190  <br/> |510（用于最大分辨率 960x144）  <br/> |已包含  <br/> |
   
**音频/视频容量规划会议**

|**媒体**|**Typical codec**|**典型的流的带宽 (Kbps)**|**而 FEC 的最大流带宽**|**Maximum stream bandwidth with FEC**|
|:-----|:-----|:-----|:-----|:-----|
|音频  <br/> |G.722  <br/> |46.1  <br/> |100.6  <br/> |164.6  <br/> |
|音频  <br/> |Siren  <br/> |25.5  <br/> |52.6  <br/> |68.6  <br/> |
|主视频接收  <br/> |H.264 和 RTVideo¹  <br/> |260  <br/> |8015  <br/> |不适用  <br/> |
|主视频发送  <br/> |H.264 和 RTVideo  <br/> |270  <br/> |8015  <br/> |不适用  <br/> |
|全景视频接收  <br/> |H.264 和 RTVideo  <br/> |190  <br/> |2010（用于最大分辨率 1920x288）  <br/> |不适用  <br/> |
|全景视频发送  <br/> |H.264 和 RTVideo  <br/> |190  <br/> |2515 ²  <br/> |不适用  <br/> |
   
1. RT 视频发给另外 H.264 Lync 2010 客户端在连接到会议时。
  
2. If there are multiple streams, they dynamically share the allocated bandwidth.
  
对于主视频，典型流带宽是用于所有收到的视频流的聚合带宽，最大流是用于所有发送视频流的带宽。即使对于多个视频流，典型视频带宽也小于对等方案，因为很多视频会议使用了内容共享，这会导致视频窗口小很多，从而使视频分辨率更低。例如，如果存在两个传入 1920x1080p 视频流，则将使用的发送和接收流二者支持的最大聚合视频负载带宽为 8000 Kbps。在实际实施中，很少看到最大值。
  
When building out a multiparty conference that uses the gallery view feature, bandwidth utilization increases initially as participants join, then decreases as resolutions are dropped to fit within the maximum. 
  
||**2 参与者**|**3 参与者**|**4 参与者**|**5 的参与者**|**6 参与者**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|**接收的最大分辨率** <br/> |1920x1080  <br/> |1280x720  <br/> |640x360  <br/> |640x360 320x240  <br/> |640x360 320x240  <br/> |
|**总平均比特率** <br/> |2128  <br/> |4050  <br/> |1304  <br/> |1224  <br/> |1565  <br/> |
|**总最大比特率** <br/> |4063  <br/> |5890  <br/> |2860  <br/> |2699  <br/> |3017  <br/> |
   
全景视频的典型流带宽基于仅可传输最高为 960x144 的全景视频的设备。在使用具备 1920x288 全景视频的设备时，预计典型流带宽会提升。 
  
**规划 PSTN 的音频容量**

|**媒体**|**典型的编解码器**|**典型的流的带宽 (Kbps)**|**而 FEC 的最大流带宽**|**最大流的带宽和 FEC**|
|:-----|:-----|:-----|:-----|:-----|
|音频  <br/> |G.711 （这包括 PSTN 参加会议）  <br/> |64.8  <br/> |97  <br/> |161  <br/> |
|音频  <br/> |RTAudio 窄带  <br/> |30.9  <br/> |44.8  <br/> |56.6  <br/> |
   
这些表中的网络带宽数值仅代表单向流量，其中包括分配给每个流的 5 Kbps 的 RTCP 流量开销。 
  
## <a name="managing-quality-of-service"></a>管理服务质量
<a name="man_QOS"> </a>

服务质量 (QoS) 是某些组织中所使用的一种网络技术，目的是有助于针对音频和视频通信提供最佳的最终用户体验。QoS 最常用于带宽有限的网络上：其中大量的网络数据包争用相对数量较小的可用带宽。QoS 允许管理员为承载音频或视频数据的数据包分配较高的优先级。通过为这些数据包提供较高的优先级，与涉及诸如文件传输、Web 浏览或数据库备份等内容的网络会话相比，音频和视频通信可能会以更快的速度完成，并且发生更少的中断。这是因为针对用于文件传输或数据库备份的网络数据包分配了“最佳效果”优先级。
  
> [!NOTE]
> 一般而言，QoS 仅适用于内部网络上的通信会话。在实施 QoS 时，您将服务器和路由器配置为支持数据包标记，但 Internet 或其他网络上可能不支持您所使用的特定方式。即使在其他网络上支持服务质量，也不能保证以您配置服务的相同方式来配置 QoS。如果您使用 MPLS，则需要与您的 MPLS 提供商合作。 
  
Skype for Business Server does not require QoS, but it is strongly recommended. 如果您遇到网络上的数据包丢失问题可用的解决方案是将添加更多的带宽，或者为了实现 QoS。 如果无法增加带宽，则实施 QoS 可能是您解决该问题的唯一办法。
  
Skype 业务服务器提供完全支持 QoS:，意味着已经开始使用 QoS 的公司可以很容易地集成 Skype 业务服务器到其现有的网络基础结构。 为执行此操作，您必须执行以下步骤：
  
- 如果[启用 QoS 对于非 Windows 设备](http://technet.microsoft.com/library/26f793df-aef8-4028-9e3b-6c2c37ea61b9.aspx)。 默认情况下，会针对运行其他操作系统的计算机和其他设备（如 iPhone）禁用 QoS。 Although you can use Skype for Business Server to enable and disable QoS for devices, you typically can't use the product to change the DSCP codes used by these devices.
    
- [Configuring Port Ranges for Your Conferencing, Application, and Mediation Servers](http://technet.microsoft.com/library/4d6eaa5d-0127-453f-be6a-e55384772d83.aspx). 您必须为不同的数据包类型（如音频和视频）保留一组唯一的端口。 通过为业务服务器使用 Skype 不要启用或禁用通过将属性值设置为 True 或 False 的 QoS。 而是可以通过配置端口范围，然后创建并应用组策略，来启用 QoS。 如果您以后决定不使用 QoS 可以"禁用"QoS 通过删除相应的组策略对象。
    
- [Configuring Port Ranges for Your Edge Servers](http://technet.microsoft.com/library/6f0ae442-6624-4e3f-849a-5b9e387fb8cf.aspx). 虽然不需要，但是可以将您的边缘服务器配置为与其他服务器使用相同的端口范围。
    
- [配置您的 Microsoft Lync 客户端的端口范围](http://technet.microsoft.com/library/287d5cea-7ada-461c-9b4a-9da2af315e71.aspx)。 这些端口范围仅适用于客户端计算机，并且通常与在您的服务器上配置的端口范围有所不同。
    
- [配置您的会议、 应用程序和中介服务器的服务策略的质量](http://technet.microsoft.com/library/8adcbbc5-c9f5-476d-ab7f-72e61859cacf.aspx)。 这些策略可确定应用到不同数据包类型的 DSCP 代码。
    
- [Configuring a Quality of Service Policy for Your A/V Edge Servers](http://technet.microsoft.com/library/119ee1f5-45b9-40ba-98e5-c694dd2fc5c2.aspx). 仅应对边缘服务器的内端执行此操作。 原因是 QoS 设计用于内部网络而不是 Internet 上。
    
- [配置对等客户端运行在 Windows 7 或 Windows 8 的服务策略的质量](http://technet.microsoft.com/library/efff2b98-b3fb-4183-a4f0-329a9105ce2c.aspx)。 请注意 Skype 业务服务器不支持其它操作系统，Windows Vista 和 Windows XP 的 QoS。
    
- [配置 Microsoft Lync 手机版的设备上的服务质量](http://technet.microsoft.com/library/a6eb2620-a512-4ab6-bdfd-eb76be43bbfe.aspx)。 默认情况下，QoS 启用 Lync 电话版设备。 您可能想要更改默认 DSCP 值，以确保您的组织中的所有音频数据包均使用相同的 DSCP 代码。
    
> [!NOTE]
> 如果您使用的 Windows Server 2012 或 Windows Server 2012 R2 您可能感兴趣的新的一套可用于在该平台上管理 QoS 的 Windows PowerShell cmdlet。 有关详细信息，请参阅[在 Windows PowerShell 网络 QoS Cmdlet](https://go.microsoft.com/fwlink/p/?LinkId=285379)。 
  
在[网络规划、 监视和使用 Lync 服务器进行故障排除](https://www.microsoft.com/en-us/download/details.aspx?id=39084)的其他详细信息和深度的白皮书还讨论 QoS。 而内容是指明确 Lync 2010 和 Lync 2013，Skype 的业务服务器 2015年的考虑事项不变。
  
## <a name="see-also"></a>另请参阅
<a name="man_QOS"> </a>

#### 

[在 Skype 的 ipv6 业务规划](ipv6.md)
  
[负载平衡的 Skype 的业务要求](load-balancing.md)
  
[Skype 的业务服务器 2015 DNS 要求](dns.md)
  
[服务器的端口和协议要求](ports-and-protocols.md)

