---
title: 规划视频互操作性中的服务器 Skype 业务服务器
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.lync.plan.VideoInterop
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4a8daf23-77ba-428b-bcbc-161f6af52c11
description: 摘要： 查看 while planning to 将 Skype 与第三方电话会议设备集成业务服务器本主题。
ms.openlocfilehash: 015f93496879e84c1959db7d6b46b765e0d286e1
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213512"
---
# <a name="plan-for-video-interop-server-in-skype-for-business-server"></a>规划视频互操作性中的服务器 Skype 业务服务器
 
**摘要：** While planning to 将 Skype 与第三方电话会议设备集成业务服务器查看以下主题。
  
Skype 业务服务器现在可以使用某些第三方 VTC （视频电话会议系统） 解决方案的集成。 启用此视频会议的互操作性的新服务器角色是视频互操作服务器 (VIS)，其当前作为独立服务器角色仅适用于本地安装实现。 VIS 作为中介的第三方电话会议系统和 Skype 业务服务器部署。 对于此版本，VIS 专用于实现与 Cisco/Tandberg 视频系统之间的互操作性。 查看此文，确定是否业务服务器安装在您 Skype 中使用此功能。
  
## <a name="device-interoperability"></a>设备互操作性

测试数据并进行互操作 Cisco VTCs 注册支持与 Cisco 统一通信管理器 （CallManager 或 CUCM） 版本 10.5 和 TCP SIP 中继设置 CUCM 和 VIS.之间
  
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
>  Cisco 软件版本 TC7.0.0 或集成业务服务器按预期方式工作的 Skype 与这些系统上需要上方。
  
## <a name="sip-trunks"></a>SIP 中继

在 SIP 中继模式下，VTCs 继续 Cisco 呼叫管理器 (CUCM) 注册的现有 Cisco 基础结构-例如，视频互操作服务器功能。 在 CUCM 和 VIS 之间定义了视频 SIP 中继，从而可以在两个系统之间路由呼叫。 仅支持通过 SIP 中继从 VTC 向 VIS 路由呼叫。 因此，VTCs 可以 （通过拨打与呼叫自动助理的电话号码），拨入 Skype 业务会议但不能拖放入会议。
  
![SfB 中的 VIS 图表](../media/87753af5-b1d9-4107-9216-fde45a1af197.png)
  
## <a name="features"></a>功能

此服务器角色提供：
  
- 用于通过第三方视频系统和 Skype Business Server 部署的 H.264 格式之间的转换。
    
- 在给定分辨率为单个视频流的从转换 VTC 到多个 simulcast 流的不同的业务服务器部署在 Skype 中使用的分辨率。 这些流可被发送到 AVMCU 和 Skype 业务服务器终结点和其他视频系统所请求不同的分辨率。 第三方视频系统参与 for Business A Skype 时也可用于此转换 / V 会议呼叫。 一旦转码限制达到特定 VIS 服务器中，为不同的分辨率任何以下请求只会收到的最低分辨率的流。 
    
- 业务 Server 视频互操作服务器; CUCM 网关和 Skype 之间视频 SIP 中继支持VTCs 继续注册 Cisco 网关，并启动通过网关的业务部署 Skype 调用。 呼叫转移视频的 SIP 中继路由的网关的 Skype 从业务视频互操作服务器。
    
- 支持会议室中的用户使用支持的视频系统从该系统拨号加入开启或关闭的会议。 此呼叫将遍历视频 SIP 中继。
    
- 与支持视频系统会议室中的用户，为业务客户端调用 Skype 的支持。 此呼叫将遍历视频 SIP 中继。
    
- 从业务服务器端 Skype 或点到点和多点包括静音/未经 mute 音频、 暂停/继续视频、 锁定视频和保留/取消保留呼叫的呼叫的支持 VTC 系统中的呼叫控制的支持。
    
## <a name="known-limitations"></a>已知限制

此服务器角色存在以下限制：
  
- 不支持新调用从业务部署 Skype 通过视频的 SIP 中继 VTCs。 . 这意味着，仅新从 VTCs 到业务部署 Skype 支持呼叫通过视频的 SIP 中继。 受支持的视频系统的状态将不可用转移到 VIS.视频的 SIP 中继 
    
- 对于视频 SIP 中继模式，仅支持独立的 VIS 池。
    
-  对于通过视频 SIP 中继在 VTC 和 VIS 之间进行的通信，支持 TLS + SRTP 或 TCP + RTP。
    
- 不支持应用程序共享。 会议室中的业务用户 Skype 需要加入 （通过例如便携式计算机） 的业务会议 Skype 和显示应用程序共享屏幕上一个不与 VTC 关联的会议室中可用的监视器。
    
- 不支持 VTC 通过 VIS 加入联盟会议。
    
- 不支持 VTC 通过 VIS 加入联机会议。
    
- 不支持通过 VIS 从 VTC 向 PSTN 路由呼叫。
    
- 不支持通过 VIS 从 PSTN 向 VTC 路由呼叫。
    
## <a name="resiliency-mechanisms"></a>复原机制
<a name="resiliency"> </a>

VIS 支持通过视频 SIP 中继传递的、来自 CUCM 的传入呼叫。 可能会丢失上游或下游连接，因此，要实现强大的复原能力，请考虑两种可能性：
  
1. **VIS 池故障转移**如果主视频的网关指向 VIS 池已关闭，恢复是当视频的网关到两个 （或多个） VIS 池定义了中继。 如果视频的网关确定但不能对主要 VIS 池的呼叫，则只需将呼叫路由到辅助 VIS 池。
    
     ![VIS 池故障转移图](../media/390d93c3-e132-4bbd-8d5a-c70ead9cdfad.png)
  
    特定 VIS 池可以有中继到多个网关，但通常特定网关不能具有中继到多个 VIS 池，因此技巧需要进行以支持此故障转移： 在 DNS 中解析视频的网关的同一个 IP 地址为其定义 2 FDQNs。 表示每个 FQDN 为拓扑文档，其中每个视频的网关具有中继到另一个 VIS 池，并恢复现在是可能的单独视频网关。 （如果使用 TLS，则多个名称将需要视频的网关证书的 SAN 中。）
    
    > [!NOTE]
    > VIS 仅允许传入呼叫来自拓扑文档中配置的网关。 
  
2. **前端故障转移**如果 VIS 池接收来自 CUCM 的调用，但无法访问其主跃注册机构或前端池，则呼叫将路由至备份前端池。
    
     ![前端故障转移图表](../media/6ddc08ec-4708-4c23-9e77-0f88899a2a96.png)
  
    VIS 将跟踪的与其主前端池和与其 （拓扑文档中的注册器服务的备份设置中查找的设置） 的备份的前端池的状态。 向这两个池中，发送选项投票一分钟一次并 VIS 五个连续故障时假定特定的前端池已关闭。 如果主前端池将标记为已向下并且还没有可用的配置备份 VIS 发送新呼叫的网关到备份的前端池。 一旦主前端池恢复后，VIS 将继续使用新的呼叫的主前端池。
    
    VIS 还会为来自视频 SIP 中继的呼叫设置 10 秒计时。 如果在呼叫的视频的 SIP 中继和主下一个跃点前端池没有应答使用一些 （包括 100 尝试） 的 SIP 消息为邀请向其发送此计时器值时，呼叫 s 的备份下一个跃点代理中使用了主要的下一个跃点前端池如果配置，尝试 hould。 
    
    > [!NOTE]
    > 如果首先尝试了备用下一跃点，则接下来不会尝试主下一跃点。 
  
    管理员还可以使用 Windows PowerShell 故障转移命令强制 VIS 使用备用前端池（例如，当必须在主前端池上执行维护时）。
    
## <a name="co-existence-of-voice-and-video-trunks-to-the-same-gateway-peer"></a>指向同一网关对等方的语音和视频中继的共存
<a name="resiliency"> </a>

具有语音和视频的 SIP 中继的业务服务器支持的 Skype 使用相同的对等网关。 因此，同一 CUCM 部署可能具有指向中介服务器的语音 SIP 中继和指向 VIS 的视频 SIP 中继。
  
- 需要在语音 SIP 中继的拓扑文档中使用特定 FQDN 定义 PSTN 网关。
    
- PSTN 网关的对等方将为中介服务器。
    
- 如有必要可定义多个语音中继，范围从单个 PSTN 网关涵盖到多个中介服务器池。
    
- 需要在视频 SIP 中继的拓扑文档中定义视频网关并使用与 PSTN 网关相同的 FQDN。
    
- 视频网关的对等方将为 VIS。
    
- 可从视频网关到特定 VIS 池定义单个视频中继。
    
- 需要配置 CUCM 以正确路由通过语音中继（或通过视频中继）的呼叫。 例如，从 VTC 拨号时，可能会使用特殊的拨号前缀；CUCM 可将此拨号前缀与指向 VIS 的呼叫关联，相应的转换规则会从指向 VIS 的 SIP 邀请中去掉此前缀。
    
## <a name="co-existence-of-vis-in-the-skype-for-business-release-with-previous-releases-of-lync"></a>Skype for Business 版本中的 VIS 与先前 Lync 版本的共存
<a name="resiliency"> </a>

VIS 只能部署的 Skype 业务部署的一部分。 它可以与 Lync 2013 会议和客户端的属于现有部署; 互操作在这些情况下，VIS 池将需要 Skype 包括 VIS 池的下一个跃点的注册器/FE 池中的业务部署的一部分。
  
VIS 不支持在 RTV 和 H.264 之间进行代码转换。 在会议中，Lync 2013 之前的客户端与 VTC 参与者之间不存在视频互操作性。
  
在会议中拥有 Lync 2013 之前的客户端将导致移动客户端使用 RTV 进行发送，因此，当移动客户端成为主要发言方时，VTC 将无法收到任何视频。
  
为了让 Lync 2013 能够与作为 Skype for Business 部署一部分的 VIS 正常开展协作，Lync 2013 需要应用相应的 CU，以便升级 Lync 2013 客户端、CAA 和 AVMCU，从而可以与 VIS 开展协作。
  
VIS 与 Lync 2013 和 Skype for Business 桌面客户端之间的互操作性已经过测试，确定受到支持。
  
与非桌面 （Android、 Ipad、 Iphone、 Windows Phone、 LMX 等） 的 VIS 互操作性为业务客户端可用 VIS 发行版时适用的应用程序存储中的 Skype 已经过测试和支持。
  
## <a name="recovery-from-packet-loss-via-fec"></a>通过 FEC 从数据包丢失中恢复
<a name="resiliency"> </a>

可打开 FEC 以帮助从数据包丢失中恢复。 如果打开，则 VIS 到 VTC 的路径中使用的视频带宽将增加 50%。
  
## <a name="vis-sizing-and-transcoding-costs"></a>VIS 大小调整和代码转换成本
<a name="resiliency"> </a>

要将来自 Cisco VTC 的单个视频流转换为多个联播视频流，需要利用 CPU 容量。 大约 16 VTCs 可以 （假定 720 p 视频流，从每个 VTC 为 720 p、 360 p、 和 180 p 3 单独 simulcast 流到转换代码） 其视频转换代码中单个 VIS 推荐 FE 平台 Lync 2013 的等效项上运行。 如果关闭代码转换功能，可以节省 VIS CPU 资源。 但是，VIS 从 VTC 请求的视频图像将为最低的通用分辨率，以便满足 Skype for Business 端的所有接收者要求。 请注意，即便关闭代码转换功能，在 Skype for Business 客户端请求某些 VTC 无法发送的低分辨率时，此功能仍可能会被激活。
  
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

[为业务服务器部署中 Skype 视频互操作性的服务器](../deploy/deploy-video-interop-server/deploy-video-interop-server.md)
