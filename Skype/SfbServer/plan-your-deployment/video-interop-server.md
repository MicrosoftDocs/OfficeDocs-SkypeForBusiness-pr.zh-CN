---
title: 在 Skype for Business Server 2015 中规划视频互操作服务器
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.lync.plan.VideoInterop
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4a8daf23-77ba-428b-bcbc-161f6af52c11
description: 摘要： 在规划将 Skype 与第三方电话会议设备集成的业务服务器 2015年时仔细阅读本主题。
ms.openlocfilehash: 1a0ae30cf383f9f05cc8c37ef2c1ba7b7c76cfb8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-video-interop-server-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中规划视频互操作服务器
 
**摘要：**在规划与第三方电话会议设备集成的业务服务器 2015年的 Skype 时仔细阅读本主题。
  
Skype 业务服务器，现在可以与某些第三方 VTC （视频电话会议系统） 解决方案进行集成。 使此视频会议的互操作性的新服务器角色是视频互操作服务器 (VIS)，这当前实现作为独立服务器角色仅用于内部部署安装。 VIS 作为第三方电话会议系统和业务服务器部署 Skype 之间的媒介。 对于此版本，VIS 着重实现了与 Cisco/Tandberg 视频系统之间的互操作性。 查看这篇文章，以确定是否适用于业务服务器安装在您的 Skype 使用此功能。
  
## <a name="device-interoperability"></a>设备互操作性

在 Cisco VTC 向 CUCM 版本 10.5 注册，并且在 CUCM 与 VIS 之间设置了 TCP SIP 中继的情况下，互操作性经过测试，并得到支持。
  
当前支持的 VTC 包括：
  
- Cisco C40
    
- Cisco C60
    
- Cisco C90
    
- Cisco MX200
    
- Cisco MX300
    
- Cisco DX80
    
- Cisco EX60
    
- Cisco EX90
    
- Cisco SX20
    
> [!NOTE]
>  Cisco 软件版本 TC7.0.0 或以上需要在集成业务服务器以达到预期效果的 Skype 与这些系统上。
  
## <a name="sip-trunks"></a>SIP 中继

在 SIP 中继模式下，VTCs 继续注册现有 Cisco 基础结构 — 例如，Cisco 调用管理器 (CUCM) 的视频互操作服务器功能。 在 CUCM 和 VIS 之间定义了视频 SIP 中继，从而可以在两个系统之间路由呼叫。 仅支持通过 SIP 中继从 VTC 向 VIS 路由呼叫。 因此，VTCs 可以拨入业务会议的 Skype （拨与调用自动助理关联的号码），但不能拖放到会议。
  
![SfB 中的 VIS 图表](../media/87753af5-b1d9-4107-9216-fde45a1af197.png)
  
## <a name="features"></a>功能

此服务器角色提供：
  
- 使用第三方视频系统和 Skype 业务服务器部署的 H.264 格式之间的转换。
    
- 在给定解析一个视频流从转换 VTC 到供使用 Skype 业务服务器部署不同分辨率的多个 simulcast 流。 这些流可以发送到 AVMCU 然后到 Skype 业务服务器终结点和其它已请求在不同分辨率的视频系统。 第三方视频系统所涉及的业务 A 的 Skype 时也将使用此转换 / V 会议呼叫。 一旦转码达到特定的 VIS 服务器中，不同的分辨率为任何以下请求只能收到的最低分辨率的流。 
    
- 支持视频的 CUCM 网关和 Skype 之间的 SIP 中继业务服务器视频互操作服务器;VTCs 继续注册与 Cisco 网关，并发起向业务部署网关通过 Skype 呼叫。 调用从路由的网关的 Skype 业务视频互操作服务器通过视频的 SIP 中继。
    
- 支持会议室中的用户使用支持的视频系统从该系统拨号加入开启或关闭的会议。 此呼叫将遍历视频 SIP 中继。
    
- 业务客户端调用 Skype 在会议室使用受支持的视频系统用户的支持。 此呼叫将遍历视频 SIP 中继。
    
- 中端呼叫控制从业务服务器端为 Skype 或受支持的 VTC 系统的点到点和多点包括静音/未经 mute 音频、 暂停/恢复视频、 锁视频和暂停/取消暂停呼叫的电话支持。
    
## <a name="known-limitations"></a>已知限制

此服务器角色存在以下限制：
  
- 不支持通过视频的 SIP 中继 VTCs 从业务部署 Skype 新调用。 . 这意味着只有新从 VTCs 到调用业务部署 Skype 支持视频的 SIP 中继段。 有关受支持的视频系统存在不能通过向 VIS.视频的 SIP 中继 
    
- 对于视频 SIP 中继模式，仅支持独立的 VIS 池。
    
-  对于通过视频 SIP 中继在 VTC 和 VIS 之间进行的通信，支持 TLS + SRTP 或 TCP + RTP。
    
- 不支持应用程序共享。 在会议室中的业务用户的 Skype 需要加入 Skype 业务大会 （通过例如膝上型电脑） 和应用程序共享一个免费在会议室与 VTC 无关显示器上的屏幕显示。
    
- 不支持 VTC 通过 VIS 加入联盟会议。
    
- 不支持 VTC 通过 VIS 加入联机会议。
    
- 不支持通过 VIS 从 VTC 向 PSTN 路由呼叫。
    
- 不支持通过 VIS 从 PSTN 向 VTC 路由呼叫。
    
## <a name="resiliency-mechanisms"></a>复原机制
<a name="resiliency"> </a>

VIS 支持通过视频 SIP 中继传递的、来自 CUCM 的传入呼叫。 可能会丢失上游或下游连接，因此，要实现强大的复原能力，请考虑两种可能性：
  
1. **VIS 池故障转移**如果视频网关指向主 VIS 池出现故障，恢复是可能如果视频网关已于两个 （或更多） VIS 池定义中继。 如果视频网关确定不能打电话的主要 VIS 池，它只是路由到辅助 VIS 池调用。
    
     ![VIS 池故障转移图](../media/390d93c3-e132-4bbd-8d5a-c70ead9cdfad.png)
  
    特定的 VIS 池可以具有中继到多个网关，但正常情况下特定网关不能具有中继到 VIS 的多个池，因此一轮必须要做，以支持这种故障转移： 它解析为同一视频网关的 IP 地址的 DNS 中定义 2 FDQNs。 为其中每个视频网关具有到其他的 VIS 池，主干拓扑文档中的不同视频网关表示每个 FQDN 和恢复现在已成为可能。 （如果使用 TLS，则多个名称需要视频网关证书的 SAN 中。）
    
    > [!NOTE]
    > VIS 仅允许传入呼叫来自拓扑文档中配置的网关。 
  
2. **前端故障转移**如果 VIS 池接收来自 CUCM 的调用，但不能达到其主要的下一个跃点注册或前端池，调用路由到前端备份池。
    
     ![前端故障转移图表](../media/6ddc08ec-4708-4c23-9e77-0f88899a2a96.png)
  
    VIS 将跟踪的其主要的前端池和其备份 （拓扑文档中注册服务的备份设置中找到的设置） 的前端池的状态。 选项轮询一次一分钟的时间向两个池，和如果有五个连续失败 VIS 假定特定的前端池出现故障。 如果主前端池标记为向下并且还没有可用的配置备份 VIS 新呼叫从发送到前端备份池的网关。 一旦主前端池恢复后，VIS 将恢复主前端池用于新的呼叫。
    
    VIS 还会为来自视频 SIP 中继的呼叫设置 10 秒计时。 如果主下一中继站前端池用于池没有应答 （包括 100 尝试） 某些 SIP 消息在此计时器值，调用 s 的备份下一中继站代理发送给它的邀请到来自视频的 SIP 中继和主要的下一个跃点前结束呼叫如果配置，试 hould。 
    
    > [!NOTE]
    > 如果备份的下一跃点第一次尝试，将不会接下来尝试主。 
  
    管理员还可以使用 Windows PowerShell 故障切换命令强制 VIS 使用备份前端池，例如，当主前端池上执行维护。
    
## <a name="co-existence-of-voice-and-video-trunks-to-the-same-gateway-peer"></a>指向同一网关对等方的语音和视频中继的共存
<a name="resiliency"> </a>

对于语音和视频的 SIP 中继具有的业务服务器支持 Skype 使用相同的网关等。 因此，同一 CUCM 部署可能具有指向中介服务器的语音 SIP 中继和指向 VIS 的视频 SIP 中继。
  
- 需要在语音 SIP 中继的拓扑文档中使用特定 FQDN 定义 PSTN 网关。
    
- PSTN 网关的对等方将为中介服务器。
    
- 如有必要可定义多个语音中继，范围从单个 PSTN 网关涵盖到多个中介服务器池。
    
- 需要在视频 SIP 中继的拓扑文档中定义视频网关并使用与 PSTN 网关相同的 FQDN。
    
- 视频网关的对等方将为 VIS。
    
- 可从视频网关到特定 VIS 池定义单个视频中继。
    
- 需要配置 CUCM 以正确路由通过语音中继（或通过视频中继）的呼叫。 例如，从 VTC 拨号时，可能会使用特殊的拨号前缀；CUCM 可将此拨号前缀与指向 VIS 的呼叫关联，相应的转换规则会从指向 VIS 的 SIP 邀请中去掉此前缀。
    
## <a name="co-existence-of-vis-in-the-skype-for-business-release-with-previous-releases-of-lync"></a>Skype for Business 版本中的 VIS 与先前 Lync 版本的共存
<a name="resiliency"> </a>

VIS 可以仅部署 Skype 的业务部署的一部分。 它可兼容 Lync 2013 会议和属于现有部署; 客户端在这些情况下，VIS 池需要包括的注册/FE 池，则下一中继站 VIS 池的业务部署 Skype 的一部分。
  
VIS 不支持在 RTV 和 H.264 之间进行代码转换。 在会议中，Lync 2013 之前的客户端与 VTC 参与者之间不存在视频互操作性。
  
在会议中有前 Lync 2013 客户端会导致移动客户端发送使用 RTV 导致 VTCs 移动客户端将成为主导的扬声器时接收到任何视频。
  
Lync 2013 为了 Lync 2013 VIS 属于业务部署 Skype 与正常工作，需要适当的 CU 应用程序升级为使用 VIS.Lync 2013 客户端、 CAA，以及 AVMCU
  
业务桌面客户端使用 Lync 2013 和 Skype 的 VIS 的互操作性测试，支持它。
  
与非桌面 （Android、 Ipad、 Iphone、 Windows Phone、 LMX 等） VIS 的互操作性业务客户可从 VIS 发行时适用的应用程序商店的 Skype 已经过测试和支持。
  
## <a name="recovery-from-packet-loss-via-fec"></a>通过 FEC 从数据包丢失中恢复
<a name="resiliency"> </a>

可打开 FEC 以帮助从数据包丢失中恢复。 如果打开，则 VIS 到 VTC 的路径中使用的视频带宽将增加 50%。
  
## <a name="vis-sizing-and-transcoding-costs"></a>VIS 大小调整和代码转换成本
<a name="resiliency"> </a>

要将来自 Cisco VTC 的单个视频流转换为多个联播视频流，需要利用 CPU 容量。 大约 16 VTCs 建议 FE 平台 Lync 2013 的等效项上运行单个 VIS 中有 （假定每个 VTC 的 720p 视频流将转换成 3 单独 simulcast 流在 720p、 360 p 和 p 180） 其视频转换代码。 如果关闭代码转换功能，可以节省 VIS CPU 资源。 但是，VIS 从 VTC 请求的视频图像将为最低的通用分辨率，以便满足 Skype for Business 端的所有接收者要求。 请注意，即便关闭代码转换功能，在 Skype for Business 客户端请求某些 VTC 无法发送的低分辨率时，此功能仍可能会被激活。
  
## <a name="call-distribution-from-the-video-gateway-to-vis"></a>从视频网关到 VIS 的呼叫分配
<a name="resiliency"> </a>

通过以下其中一种 CUCM 分配机制来实现分配：
  
- 使用 DNS 进行动态分配。
    
- 在 CUCM 端，您可以定义各个中继，在其中，每个中继都在 VIS 池中的不同服务器上终结。 CUCM 将跨不同中继路由呼叫。
    
## <a name="no-hybrid-interoperability"></a>无混合互操作性
<a name="resiliency"> </a>

Skype for Business 不支持 VTC 通过本地 VIS 加入联机会议。
  
## <a name="no-federation-support"></a>无联盟支持
<a name="resiliency"> </a>

Skype for Business 不支持 VTC 通过 VIS 加入联盟会议。
  
## <a name="see-also"></a>另请参阅
<a name="resiliency"> </a>

#### 

[在 Skype 的视频互操作服务器部署为业务服务器 2015](../deploy/deploy-video-interop-server/deploy-video-interop-server.md)

