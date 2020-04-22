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
description: 本主题定义了 Skype for Business Online 服务的网络性能要求集，以及如何选择使用 Internet 或 ExpressRoute 在网络和 Skype for business Online 之间进行连接，这取决于你对网络连接的评估。 如果你已决定将 Azure ExpressRoute 部署到 Office 365 的专用连接，此文档还提供了有关如何在不同的 Skype for Business Online 部署方案中规划 ExpressRoute 连接的指南。
ms.openlocfilehash: ed7ad6ebd456122e41ccd74269180ff9c79fa3fb
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2020
ms.locfileid: "43776437"
---
# <a name="media-quality-and-network-connectivity-performance-in-skype-for-business-online"></a>Skype for Business Online 中的媒体质量和网络连接性能

本主题定义了 Skype for Business Online 服务的网络性能要求集，以及如何选择使用 Internet 或 ExpressRoute 在网络和 Skype for business Online 之间进行连接，这取决于你对网络连接的评估。 如果你已决定将 Azure ExpressRoute 部署到 Office 365 的专用连接，此文档还提供了有关如何在不同的 Skype for Business Online 部署方案中规划 ExpressRoute 连接的指南。
  
通过 IP 的实时媒体质量（音频、视频和应用程序共享）很大程度上受到端到端网络连接质量的影响。 为获得最佳的 Skype for Business Online 媒体质量，确保公司网络与 Skype for Business Online 之间的高质量连接很重要。 实现这一目标的最佳做法是基于网络容量设置内部网络和云连接，以便所有连接都可以承受 Skype for Business Online 的高峰流量。
  
Azure ExpressRoute 不是 Office 365 服务（包括 Skype for Business Online）的必要条件。 但是，Azure ExpressRoute 是可用的部署选项之一，可帮助确保与 Office 365 的连接满足 Skype for Business 网络性能要求，并确保最优质的 Skype for business Online 媒体质量体验。
  
> [!TIP]
> 虽然本主题提供了整体网络性能指南，但网络评估的完整指南超出了本文档的范围。 若要查找可帮助你实现网络性能度量的 Skype for Business Online 合作伙伴的列表，这些合作伙伴可帮助你作为全面、完整的网络评估的一部分，请访问[skype for Business 合作伙伴解决方案](http://partnersolutions.skypeforbusiness.com/)。 
  
## <a name="network-connectivity-requirements-to-skype-for-business-online"></a>Skype for business Online 的网络连接要求

### <a name="factors-that-impact-skype-for-business-online-media-quality"></a>影响 Skype for Business Online 媒体质量的因素

有许多不同的因素会影响 Skype for business Online 实时媒体（音频、视频和应用程序共享）质量，其中包括使用的设备、环境和网络连接。 
  
#### <a name="devices"></a>设备

在实时媒体会话中，所有参与者（如耳机和 Web 摄像头）使用的媒体捕获和呈现设备对整体音频和视频质量有很高的影响。 低品质设备和错误的设备驱动程序会降低整体的音频声音质量和视频图像质量。 另一方面，经认证的设备或高品质设备有助于消除回声、过滤噪音、提高视频分辨率并减少延迟。
  
虽然不需要认证的音频和视频媒体设备，但对于 Skype for Business 来说，我们极力推荐使用此设备来获得最佳媒体体验。 有关所有 Skype for Business 认证设备的列表，请参阅[skype for business 的电话和设备](https://technet.microsoft.com/office/dn947482)。 您可以使用 skype for business [Online 呼叫质量仪表板](/microsoftteams/turning-on-and-using-call-quality-dashboard)（位于**skype for business 管理中心**）来验证使用中的设备是否正常工作，并监控音频和视频媒体质量。
  
> [!TIP]
> **要获得最佳的 Skype For business 媒体质量体验，需要认证的设备**。
  
请务必记住，任何媒体设备、Skype for business 客户端和 Skype for Business 服务器（实时媒体流）将引入一些延迟。 设备和软件处理延迟以及网络延迟会对端到端整体延迟和最终用户体验产生很高的影响和影响。
  
#### <a name="environment"></a>环境

用户会面及使用音频和视频设备的环境及周边区域是另一个影响音频和视频质量的重要因素。用户在嘈杂的环境中通话会产生回声和含混不清的音频。用户在黑暗或低光照环境中则无法生成明亮清晰的视频图像画质。在会议室设置中，麦克风和视频设备的位置对参与者接收的声音和图像质量有直接影响。
  
若要更清楚地了解用户的音频和视频体验，请使用 Skype for business 应用**工具** > **选项** > "**音频设备**" 或 "**视频设备**"，对设备进行更改并自定义其设置。

#### <a name="network"></a>网络

通过 IP 网络的实时媒体的质量很大程度上受到网络连接质量的影响，但尤其是：
  
- **延迟**这是将 IP 数据包从点 A 转到网络上的点 B 所需的时间。 此网络传播延迟实质上与两个点之间的物理距离和光之间的距离保持联系，包括不同路由器所用的额外开销。 延迟是指单向或往返时间（RTT）。
    
- **数据包丢失**这通常定义为在给定时间段内丢失的数据包的百分比。 数据包丢失直接影响音频质量—从少量的单个丢失的数据包几乎没有影响，到导致完整的音频切出的后端到后爆发损失。
    
- **数据包间到达抖动或简单抖动**这是连续数据包之间的延迟的平均变化。 大多数现代 VoIP 软件（包括 Skype for Business）可以通过缓冲来适应某些级别的抖动。 仅当抖动超过的是参与者将注意到抖动效果的缓冲时才会如此。
    
> [!NOTE]
>  抖动的缓冲将增加端到端的延迟。
  
通过许多并发的 Skype for Business Online 实时媒体会话以及其他 Office 365 服务和其他业务应用程序生成的其他网络流量，确保将你的网络连接到 Skype for business Online 服务的整个网络路径上有足够的带宽，这对避免网络拥塞和确保出色媒体实时媒体（音频）非常重要。、视频和应用程序共享）质量。 
  
#### <a name="implementing-quality-of-service-qos-across-congested-networks"></a>通过拥挤的网络实现服务质量（QoS）

此外，网络上的流量堵塞对媒体质量有很大影响。 为了使音频和视频数据包能够更快地在拥挤的网络中以更高的网络流量进行排序，并优先考虑其他网络流量，可使用服务质量（QoS）帮助为音频和视频通信提供最佳的最终用户体验。
  
QoS 为您提供了一种为携带音频或视频数据的网络数据包分配更高优先级的方法。 通过为这些数据包分配较高优先级，音频和视频通信可能会更快地通过网络旅行，且中断较少，而不是涉及文件传输、web 浏览或数据库备份等内容的网络会话。 这是因为在默认情况下用于文件传输或数据库备份的网络数据包被分配 "最大努力" 作为优先级，网络拥塞不会产生大影响。 如果你没有为媒体分配更高优先级（音频、视频和应用程序共享）数据包，并且还将其指定为 "最大努力"，则它们也将与所有其他网络流量一起进行处理。 根据网络拥塞的数量，这可能会为你的用户提供更低的整体音频和视频质量体验。
  
强烈建议你在网络上实现 QoS，以确保网络内的网络拥挤不会受到影响。 但是，为了使其影响最大影响，所有网络终结点必须支持 QoS，这意味着所有终结点都必须遵守 QoS 标记和数据包优先级。 Skype for Business Online 服务服从 Microsoft 网络中的 QoS 标记和优先级。 但是，通过公共连接（如 Internet 从公司网络到 Microsoft 网络）路由的流量不会保留 QoS 标记和数据包优先级。 使用[Azure ExpressRoute](https://azure.microsoft.com/services/expressroute/)从你的网络到 Office 365 的专用连接提供了一个部署解决方案，可保留 QoS 标记和数据包优先级，从而为最终用户增加了整体音频和视频质量。
  
## <a name="network-performance-requirements-to-connect-to-skype-for-business-online"></a>连接到 Skype for Business Online 的网络性能要求
<a name="bkNetworkPerf"> </a>

Skype for Business 实时媒体通过许多不同的设备、客户端应用、服务器软件和跨不同网络传播。 实时媒体的端到端延迟是在所有组件和网段中引入的延迟的总量。 端到端网络连接的质量由具有最差质量的网络段确定。 此段用作此网络流量的瓶颈。
  
下图显示了会议中从一个 Skype for Business 参与者到另一个 Skype for Business 参与者的单向音频流。
  
![ExpressRoute 呼叫流。](../images/c026e8e5-ba09-42c0-9e03-60fbfda1cb02.png)
  
在此会议方案中，媒体路径包含在以下网络段中：
  
1. **从用户1到 Microsoft 网络边缘的连接**这通常包括 WiFi 或以太网、从用户1到 Internet 出口点（网络边缘设备）的 WAN 连接，以及从网络边缘到 Microsoft 网络边缘的网络连接。
    
2. **Microsoft 网络中的连接**这介于 Microsoft Edge 到 Skype for business Online 数据中心之间，其中使用了 A/V 会议服务器。
    
3. **Microsoft 网络中的连接**这是 Skype for Business Online 数据中心和 Microsoft 网络边缘之间的区别。
    
4. **从 Microsoft 网络边缘到用户2的连接**这包括从网络边缘到 Microsoft 网络边缘的 Internet 连接、从用户2到 Internet 出口点（网络边缘）和网络连接（如 WiFi 或以太网）的 WAN 连接。
    
下图显示了 Skype for business Online PSTN 呼叫的组件和网段细目：
  
![ExpressRoute PSTN 载波呼叫流。](../images/768a88df-c8a9-4171-a158-565a698f0193.png)
  
在 PSTN 呼叫方案中，媒体路径与以下网络段交叉：
  
1. **从 Skype For business 客户端呼叫者到 Microsoft 网络边缘的连接**这通常包括 WiFi 或以太网、从 Skype for Business 客户呼叫者到 Internet 出口点（网络边缘设备）的 WAN 连接，以及从网络边缘到 Microsoft 网络边缘的 Internet 连接等网络连接。
    
2. **Microsoft 网络中的连接**这是使用中介服务器的 Microsoft Edge 到 Skype for Business Online 数据中心之间的。
    
3. **Microsoft 网络中的连接**这是 Skype for Business Online 数据中心和 Microsoft 网络边缘之间的区别。
    
4. **Microsoft 网络和 PSTN 服务提供商合作伙伴之间的连接**这是从 Microsoft 网络外部的 Skype for Business 客户端发出 PSTN 呼叫的连接。
    
### <a name="network-performance-requirements-from-a-skype-for-business-client-to-microsoft-network-edge"></a>从 Skype for Business 客户端到 Microsoft 网络边缘的网络性能要求
<a name="bkSfBClienttoEdge"></a>

为了获得最佳的 Skype for Business 媒体质量，从公司网络到 Microsoft 网络边缘的连接需要以下网络性能指标目标或阈值。 此网络段包括您的内部网络，其中包括所有 WiFi 和以太网连接、任何通过 WAN 连接的公司站点到站点流量，例如多协议标签交换（MPLS），以及 Internet 或 ExpressRoute 合作伙伴与 Microsoft 网络边缘的连接。
  
> [!CAUTION]
> **公司网络上的 Skype for Business 客户端与 Office 365 服务之间的连接必须满足以下网络性能要求和阈值。**
  
|||
|:-----|:-----|
|**指标** <br/> |**目标** <br/> |
|延迟（一种方法）  <br/> |< 50ms  <br/> |
|延迟（RTT 或往返时间）  <br/> |< 100ms  <br/> |
|爆发数据包丢失  <br/> |在任何200ms 时间间隔内 <10%  <br/> |
|数据包丢失  <br/> |任何15s 时间间隔内 <1%  <br/> |
|数据包内部到达抖动  <br/> |在任何15s 时间间隔内 <30ms  <br/> |
|数据包重新排序  <br/> |<0.05% 的订单外数据包  <br/> |
   
 **其他性能目标要求：**
  
- Microsoft 网络具有全球超过160个边缘的位置。 我们通过这些边缘网站与全球各地的互联网服务提供商（Isp）协作。 "延迟跃点数" 目标假设您的公司网站或网站，Microsoft 边缘位于同一大陆。
    
- 您的公司网站或 Microsoft network Edge 连接的网站包括第一跃点网络访问权限，该网络访问可以是 WiFi 或其他无线技术。 
    
- 网络性能目标采用适当的带宽和/或服务质量规划。 换句话说，当网络连接处于峰值负载时，此功能直接适用于 Skype for business 实时媒体流量。
    
### <a name="network-performance-requirements-from-your-network-edge-to-microsoft-network-edge"></a>从网络边缘到 Microsoft 网络边缘的网络性能要求
<a name="bkYourNetworkEdge"> </a>

以下是网络边缘与 Microsoft 网络边缘之间的连接所需的网络性能目标或阈值。 此网络段将排除客户的内部网络或 WAN，并将其用作测试通过 Internet 发送的网络流量或通过 ExpressRoute 合作伙伴网络进行测试的指导，还可以在与 ExpressRoute 提供商协商性能服务级别协议（SLA）时使用。
  
> [!CAUTION]
> **公司网络边缘与 Microsoft 网络边缘之间的连接必须满足以下网络性能要求和阈值。**
  
|||
|:-----|:-----|
|**指标** <br/> |**目标** <br/> |
|延迟（一种方法）  <br/> |< 30ms  <br/> |
|延迟（RTT）  <br/> |< 60ms  <br/> |
|爆发数据包丢失  <br/> |在任何 200 ms 间隔期间 <1%  <br/> |
|数据包丢失  <br/> |任何15s 时间间隔内 <0.1%  <br/> |
|数据包内部到达抖动  <br/> |在任何15s 时间间隔内 <15ms  <br/> |
|数据包重新排序  <br/> |<0.01% 的订单外数据包  <br/> |
   
 **其他性能目标要求：**
  
- 性能目标要求任何公司网络边缘与其最近的 Microsoft 网络边缘之间的连接位于同一大洲。
    
- 网络性能目标采用适当的带宽和/或服务质量规划。 这也适用于 Skype for Business 实时媒体流量（当网络连接处于峰值负载时）。 要获得正确的带宽和 QoS 规划，请参阅[Skype for Business Online 中的 ExpressRoute 和 qos](https://support.office.com/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d)。
    
## <a name="measuring-network-performance"></a>测量网络性能
<a name="bkNetworkPerf"> </a>

若要测量实际网络性能，尤其是延迟和数据包丢失（从任何公司网络网站到网络边缘），您可以使用 ping 之类的工具测试从 Microsoft Edge 和数据中心网站运行的一组 Skype for business media 中继服务。 

>[!NOTE]
> 通过 ping （ICMP）测量网络性能不起作用。 因此，以下任意播 IP 公开将停止响应2020年1月开始的 ICMP 请求。 为了有效地衡量网络性能，Microsoft 建议[网络 Assesment 工具](https://www.microsoft.com/download/details.aspx?id=53885)。
  
对于测试到 Microsoft 网络的 Internet 连接，建议针对 Skype for Business media 中继的以下 Vip 进行测试。 "*任意广播" VIP*将解析为 Microsoft 网络 Edge 网站中距离测试位置最近的媒体中继的 IP 地址。
  
||||
|:-----|:-----|:-----|
|**IP 地址** <br/> |**类型** <br/> |**位置** <br/> |
|13.107.8.2  <br/> |VIP  <br/> |全球通用任意广播 IP  <br/> |
   
 **下面是评估网络性能的一些高级别建议：**
  
- 你应该评估内部网络以及与 Office 365 的连接。
    
- 你应该在很长一段时间内评估和收集所有网络的数据。 我们建议你至少为一周的网络性能进行测试，以便你可以查看所有工作日和工作时间的使用模式。 这将显示高峰时段。
    
- 你应考虑网络性能度量的多个示例。 我们建议在您收集数据的整个时段内，从公司网站中每隔10分钟测量一次。 要比较 Skype for Business Online 网络性能要求，请使用此示例数据集的90% 度量值。 
    
- 您应不断评估网络的性能。 由于使用模式更改、新的基于企业的新应用程序使用大量带宽以及对组织或物理公司位置的更改，网络使用率会随着时间的推移而变化。 根据这些网络性能要求和目标/阈值不断监视网络性能，并做出及时调整，以确保最理想的实时媒体质量，这一点非常重要。 
    
## <a name="measuring-network-performance-using-azure-vms"></a>使用 Azure Vm 测量网络性能
<a name="bkNetworkPerf"> </a>

从 Skype for Business 客户和合作伙伴，可利用 Microsoft Azure 云中的服务测试设置，而不是针对 Microsoft 网络 Edge 网站进行测试。 在这些解决方案中，网络评估工具针对在 Azure 云中的服务设置为自定义终结点来测试延迟、数据包丢失和抖动。 因此，测试网络流量将通过一个额外的网络段进行传输，这是 Microsoft 网络中网络边缘和托管网络评估服务的 Azure 数据中心之间的连接。
  
对于基于 Azure 托管测试服务的这些网络评估解决方案。 我们建议在国家和/或地区内执行网络评估。 例如，对于美国东部地区的客户网站，评估应针对在 Azure 东美国数据中心区域托管的测试服务实例执行。 
  
下面是基于 Azure 服务的网络评估设置的延迟（RTT）目标。 单向延迟目标将为相应的 RTT 目标的一半。 "数据包丢失" 和 "抖动目标" 与为基于 Skype 媒体中继的测试定义的目标保持一致。
  
|||||
|:-----|:-----|:-----|:-----|
|**客户区域** <br/> |**Azure 区域** <br/> |**网络边缘-Azure 往返时间（RTT）** <br/> |**您的网站-Azure 往返时间（RTT）** <br/> |
|美国中部  <br/> |美国中部  <br/> |99  <br/> |139  <br/> |
|美国东部  <br/> |美国东部  <br/> |86  <br/> |126  <br/> |
|美国中北部  <br/> |美国中北部  <br/> |97  <br/> |137  <br/> |
|美国中南部  <br/> |美国中南部  <br/> |94  <br/> |134  <br/> |
|美国西部  <br/> |美国西部  <br/> |94  <br/> |134  <br/> |
|美国夏威夷  <br/> |美国西部  <br/> |116  <br/> |156  <br/> |
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
|印度  <br/> |印度  <br/> |103  <br/> |143  <br/> |
|印度西部  <br/> |印度西部  <br/> |103  <br/> |143  <br/> |
|中国东部  <br/> |中国东部  <br/> |120  <br/> |160  <br/> |
|中国北部  <br/> |中国北部  <br/> |120  <br/> |160  <br/> |
   
## <a name="media-quality-and-expressroute"></a>媒体质量和 ExpressRoute
<a name="bkNetworkPerf"> </a>

用于连接到 Office 365 的专用网络连接是用于 Office 365 的 Azure ExpressRoute。 它让客户能够控制其 Office 365 网络流量所采用的路径。 他们不再需要担心数据由未知的运营商、提供商和 Isp 携带的 Internet 上发生的不可预测的路由。 通过 ExpressRoute 发送的网络流量直接通过 ExpressRoute 合作伙伴的网络发送到 Microsoft 网络。 这允许客户将 Office 365 视为位于其自己的非现场数据中心，并具有专用连接。
  
Azure ExpressRoute 适用于所有 Office 365 许可服务。 但是，Office 365 需要 Azure ExpressRoute Premium 加载项才能启用全局路由。 如果客户至少拥有500席位，而实施 ExpressRoute，则无需支付额外费用，即可获得所需的*Expressroute Premium 加载*项。
  
### <a name="is-expressroute-required-for-good-media-quality"></a>是否需要 ExpressRoute 才能获得良好的媒体质量？

Azure ExpressRoute 不是获取最最优的 Skype for Business Online 媒体质量的必要条件。 但是，这是一个部署选项，可帮助你确保你的云连接符合 Skype for Business 网络性能目标或阈值。
  
Office 365 是一种高性能和安全的服务，可使用互联网。 我们将继续投资新的安全功能和区域边缘节点，以不断提高安全性和性能。 Azure ExpressRoute 不是 Office 365 服务（包括 Skype for Business Online）的必要条件。 Azure ExpressRoute 是可用的部署选项之一，可帮助确保与 Office 365 的连接满足 Skype for Business 网络性能要求，并确保最优质的 Skype for business Online 媒体质量体验。
  
对于 Skype for Business Online 媒体质量，您的公司网站和 Microsoft 网络边缘之间的连接必须满足网络性能要求中的性能目标（[从 Skype For business 客户端到 microsoft 网络边缘](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge)），并且网络边缘和 microsoft 网络边缘之间的连接满足网络性能要求中的性能目标，即网络边缘[到 microsoft 网络边缘](media-quality-and-network-connectivity-performance.md#bkYourNetworkEdge)的性能。  
  
您的公司的物理网络连接（包括内部网络和云连接能力）可容纳高峰媒体流量，这也非常重要。 Azure ExpressRoute 是一种可帮助客户确保其 Skype for Business Online 云连接满足所有这些性能要求的多种方法。
  
### <a name="is-expressroute-required-for-voice-quality-sla"></a>语音质量 SLA 是否需要 ExpressRoute？

不需要，Skype for Business Online 语音质量 SLA 不需要 ExpressRoute。 [Skype For Business Online 语音质量 SLA](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;DocumentTypeId=37)适用于任何由任何 Skype For business online 语音服务用户置于正确许可证和订阅中的任何符合条件的通话，该用户可使该用户进行任何类型的 VOIP 或 PSTN 呼叫。 语音质量 SLA 应包括以下所有条件：
  
- 通过 Microsoft 认证的 IP 电话拨打电话。
    
- 有线以太网连接。
    
- Microsoft 网络问题导致的语音质量问题。
    
> [!NOTE]
> 语音质量 SLA 将不包括低呼叫质量的呼叫排除在非 Microsoft 网络（包括 ExpressRoute 合作伙伴和其他网络）中的问题所导致。 
  
### <a name="internet-or-azure-expressroute"></a>Internet 还是 Azure ExpressRoute？

在对 Skype for business Online 的网络连接选项做出决定之前，客户必须根据网络性能要求中描述的网络性能要求评估其网络和当前 Internet 连接，[以连接到 skype](media-quality-and-network-connectivity-performance.md#bkNetworkPerf)For business online。
  
如果当前 Internet 连接的网络性能在高峰时间内设置为足够的容量，并且满足从网站到 Microsoft 网络边缘的网络性能要求和从网络边缘到 Microsoft 网络边缘的网络性能要求，则可以继续使用现有 Internet 连接来连接到 Skype for Business Online。
  
对于无法满足网络性能要求的公司网站，我们强烈建议你首先使用现有的网络服务提供商来提高你的总体网络性能。 但是，如果它们仍未得到满足，使用 Azure ExpressRoute 有助于确保 Skype for Business Online 云连接能够帮助你满足网络性能要求。
  
Azure ExpressRoute 提供以下附加好处：
  
- 您的网络和 Microsoft 网络之间的连接可用性的服务级别协议（SLA）。 ExpressRoute 具有99.9% 的保证可用性 SLA。
    
- Office 365 服务所需的计划和有保证的带宽。 你可以通过使用 ExpressRoute 仅发送 Office 365 流量或 Skype for business 流量来实现此目的，然后让所有其他 Internet 通信转到你的网络的其他 Internet 出口/入口点。
    
- ExpressRoute 设计用于在网络和 Microsoft 网络之间保留 DSCP QoS 标记。
    
有关 ExpressRoute QoS 和容量规划的详细信息，请参阅[Skype For Business Online 中的 ExpressRoute 和 QoS](https://support.office.com/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d)。
  
### <a name="can-i-setup-azure-expressroute-for-skype-for-business-online-only"></a>是否可以仅为 Skype for business Online 设置 Azure ExpressRoute？

是的，你可以设置 Azure ExpressRoute 以确保从你的公司网络获得出色的网络连接，仅适用于 Skype for business Online。 这将为你的用户提供最最优的实时媒体质量，但你可以通过 Internet 继续连接到其他 Office 365 服务。
  
边界网关协议（BGP）是 Internet 上的路由协议，用于在 Internet 上路由网络流量。 它旨在在通过 Internet 发现的自治系统（AS）之间交换路由信息。 BGP 社区值是可应用于传入或传出路由的属性标记。 BGP 社区通常用于根据地理位置、服务类型或其他条件，用来通知接收目标的接收。
  
通过 BGP 社区支持，Microsoft 将根据其所属的服务来标记带有相应 BGP 社区值的前缀和路由。 Microsoft 将通过公共对等和 Microsoft 对等的方式标记前缀，并使用相应的 BGP 社区值指示这些前缀的托管区域。 你可以依靠社区值做出适当的路由决策，以便提供最佳路由。 你可以使用 Skype for Business Online BGP 社区值设置仅适用于 Skype for business Online 的 ExpressRoute 连接。 你可以在[ExpressRoute 路由要求](https://azure.microsoft.com/documentation/articles/expressroute-routing/)中了解更多信息。
  
## <a name="expressroute-connectivity-scenarios-for-skype-for-business-online"></a>适用于 Skype for Business Online 的 ExpressRoute 连接方案
<a name="bkNetworkPerf"> </a>

如果你已确定基于上述建议的 ExpressRoute 适用于你，以下是你应获取的可获取 ExpressRoute 连接的位置和数量的建议。
  
### <a name="online-only-deployment---single-site"></a>仅联机部署-单个网站

如果你的所有用户都使用 Skype for Business Online 服务，并且你的分支位于单个物理位置的中心，并且你决定要部署 Azure ExpressRoute，则应在你的公司网站与最接近的[expressroute 对等位置](https://azure.microsoft.com/documentation/articles/expressroute-locations/)之间设置单一 ExpressRoute 连接。
  
下图显示了此类型部署的示例。 对于本示例，Contoso 是一个大学，位于佛罗里达州的奥兰多。 Contoso 拥有10000教职员工成员和学生。 从其位置到 Microsoft edge 网站的 Internet 测试显示的数据包在高峰时段内损失超过5%。 他们已决定使用 ExpressRoute 和预配的带宽获取与 Office 365 的专用连接，以便他们可以避免 Office 365 的网络拥塞，尤其是 Skype for Business Online 实时流量。 他们通过 ExpressRoute 在亚特兰大、GA MeetMe 网站上连接到 Microsoft 云。
  
![ExpressRoute 单站点。](../images/59fbca3c-a3ea-4568-8da5-3281096a7453.png)
  
### <a name="online-only-deployment---multiple-sites-on-the-same-continent"></a>仅联机部署-同一大洲的多个站点

如果您的公司使用的 Skype for Business Online 服务来自同一区域或洲的多个办事处，并且您选择实现 Azure ExpressRoute，建议通过 ExpressRoute 连接主网站，然后选择为不满足推荐的网络性能目标的其他位置添加其他 ExpressRoute 对等连接。
  
在以下示例中，Contoso 是总部位于纽约的美国旅行服务公司，但在美国有其他办事处。 其办事处通过使用 MPLS 连接到 Office 365 的 WAN 进行连接。 它们最初在 Hoboken 中设置来自其 Internet 路由器的 ExpressRoute 连接，新泽到纽约 MeetMe 网站。 
  
通过此设置，从大多数网站到 Microsoft 网络（纽约边缘网站）的网络流量可以满足[从 skype for business 客户端到 microsoft 网络边缘的网络性能要求](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge)中所述的 Skype for business 客户端连接网络性能目标。 但是，Contoso west coast 办事处与纽约之间的延迟是单向的50ms。 此外，檀香山是 Contoso 的第二个最大办事处，从檀香山到纽约的延迟超过了80ms 的单向。 为确保这些办事处的用户获得良好的媒体质量，Contoso 决定在其圣何塞站点和硅谷 ExpressRoute MeetMe 网站之间添加 west coast ExpressRoute 连接。
  
![同一大洲上的 Express 路由器多站点。](../images/bf57a473-01e1-4271-9675-385767bc58e1.png)
  
### <a name="online-only-deployment---multiple-sites-on-different-continents"></a>仅联机部署-不同洲的多个网站

如果你的所有用户都使用 Skype for Business Online 服务，并且你的办事处位于多个洲的多个物理位置，则如果你决定部署 Azure ExpressRoute，则你应该为每个大陆的主网站与最接近的[ExpressRoute 对等位置](https://azure.microsoft.com/documentation/articles/expressroute-locations/)之间的每个大陆至少设置一个 ExpressRoute 连接。 根据成本与收益，你可以选择从不满足网络性能目标的站点部署其他 ExpressRoute 连接。
  
在以下示例中，Contoso 是一个大型企业法律公司，其中的办事处遍布北美和欧洲的大型城市。 根据其 Internet 连接及其内部网络性能评估，Contoso 决定在北美使用两个 ExpressRoute 连接，并为其所有欧洲办事处部署一个 ExpressRoute 线路。
  
![具有多个站点和多个洲的 ExpressRoute。](../images/c967550b-dc85-4b37-a7bc-cd825ec86854.png)
  
### <a name="hybrid-deployment"></a>混合部署

如果你有本地 Lync 或 Skype for business 部署，并选择实现混合的 Skype for business Online 集成，我们建议，如果你决定部署 Azure ExpressRoute，则对于每个本地 Lync 或 Skype for business Edge 网站以及每个具有办事处的大陆至少有一个 ExpressRoute 连接，我们建议你至少有一个 ExpressRoute 连接。 根据成本与收益，对于每个大陆，你可以选择从不满足网络性能目标的办公室部署其他 ExpressRoute 连接。
  
如果您有本地 Skype for Business 部署，则必须遵循[Edge 服务器规划和部署指南](https://technet.microsoft.com/library/mt346417.aspx)。 具体说来，边缘服务器必须可从您的网络外部访问。 这通常是通过向边缘服务器分配可路由的公共 IP 地址或使用网络地址转换（NAT）实现的。
  
在以下示例中，Contoso 具有现有的本地 Skype for Business 企业语音部署。 他们希望将本地用户迁移到 Office 365 联机服务。 它们还决定使用混合部署，以便它们可以继续对所有内部部署用户和联机用户使用其现有 PSTN 基础结构。 Contoso 的本地数据中心和 Skype for business Edge 服务器位于芝加哥。 对于其部署，Contoso 决定在其芝加哥数据中心和芝加哥 ExpressRoute 之间设置一个 ExpressRoute 连接。 他们还添加了一个 west coast ExpressRoute 连接，以便更好地服务于其檀香山 office。
  
![ExpressRoute 混合。](../images/a7467c56-642f-44e5-adfb-ecca91ba2dd3.png)
  
### <a name="online-deployment-with-cloud-connector-edition"></a>通过云连接器版本进行联机部署

Skype for Business Online 云连接器版是一种混合服务，它包含一组用于实现本地 PSTN 连接的打包虚拟机（Vm）。 通过在虚拟化环境中部署最少的 Skype for Business 服务器拓扑，你将能够通过现有的本地 PSTN 语音基础结构通过座机和手机发送和接收呼叫。
  
如果你决定部署 Azure ExpressRoute 和云连接器版本，我们建议你为每个大陆的主网站的每个大陆至少设置一个 Express 路由连接，使其成为最接近的[ExpressRoute 对等位置](https://azure.microsoft.com/documentation/articles/expressroute-locations/)。 根据成本与收益，对于每个大陆，你可以选择从无法满足网络性能目标的站点部署其他 ExpressRoute 连接。
  
如果您有本地 Skype for business 部署，则必须遵循[Skype for Business 云连接器版的规划指南](https://technet.microsoft.com/library/mt605227.aspx)。 具体说来，应将访问边缘和 A/V 边缘服务分配给公共 IP 地址，并可从 Office 365 数据中心访问。
  
在以下示例中，Contoso 是一个欧洲会计公司，其中包含几个主要欧洲国家和城市的状态。 当他们注册 Skype for Business Online 以满足其所有协作需求时，他们决定为每个国家/地区的云连接器提供一个物理位置，以继续使用其 PSTN 基础结构和已存在的运营商合同。 根据其从其所有站点和 Microsoft 网络边缘进行的测试，他们确定伦敦的单个 ExpressRoute 连接将帮助满足网络性能要求中所述的 Skype for business 客户端连接网络性能目标（[从 skype for business 客户端到 Microsoft 网络边缘](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge)）。
  
![ExpressRoute 云连接器1。](../images/ebdc96e5-b22a-4bf2-b668-062460b4b890.png)
  
下面是 Contoso 的另一个部署选项。 在这种情况下，他们决定在部署云连接器的每个网站上设置 ExpressRoute 连接。 
  
![ExpressRoute 云连接器2。](../images/06d967a9-64f5-4d7d-98ed-3f3add1b7c2b.png)
  
## <a name="related-topics"></a>相关主题

[Skype for Business Online 中的 ExpressRoute 和 QoS](expressroute-and-qos-in-skype-for-business-online.md)

  
 
