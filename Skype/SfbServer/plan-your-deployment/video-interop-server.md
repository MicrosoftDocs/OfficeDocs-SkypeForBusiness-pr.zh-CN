---
title: Skype for business Server 中的视频互操作服务器计划
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
f1.keywords:
- ms.lync.plan.VideoInterop
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4a8daf23-77ba-428b-bcbc-161f6af52c11
description: 摘要：在计划将 Skype for Business 服务器与第三方 teleconferencing 设备集成时，请查看本主题。
ms.openlocfilehash: 5531fd60cc2aa28202903fcc4392fe7830bcdfa0
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2020
ms.locfileid: "41684185"
---
# <a name="plan-for-video-interop-server-in-skype-for-business-server"></a>Skype for business Server 中的视频互操作服务器计划
 
**摘要：** 在计划将 Skype for Business 服务器与第三方 teleconferencing 设备集成时，请查看此主题。
  
现在，Skype for Business 服务器允许你与特定的第三方 VTC （视频 Teleconferencing 系统）解决方案集成。 启用此视频会议互操作性的新服务器角色是视频互操作服务器（VIS），它当前作为独立服务器角色实现，仅供本地安装使用。 VIS 充当第三方电话会议系统和 Skype for business 服务器部署之间的媒介。 对于此版本，VIS 专用于实现与 Cisco/Tandberg 视频系统之间的互操作性。 查看本文以确定是否在 Skype for Business 服务器安装中使用此功能。
  
## <a name="device-interoperability"></a>设备互操作性

通过 Cisco VTCs 在 CUCM 和 VIS 之间设置的 Cisco 统一通信管理器（CallManager 或 CUCM）版本10.5 和 TCP SIP 中继注册，可对互操作进行测试和支持。
  
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
>  Cisco 软件版本需要在这些系统上使用 TC 7.0.0 或更高版本，以便与 Skype for Business 服务器集成，以便按预期工作。
  
## <a name="sip-trunks"></a>SIP 中继

视频互操作服务器在 SIP 干线模式下工作，VTCs 将继续向现有 Cisco 基础结构注册，例如 Cisco 呼叫管理器（CUCM）。 在 CUCM 和 VIS 之间定义了视频 SIP 中继，从而可以在两个系统之间路由呼叫。 仅支持通过 SIP 中继从 VTC 向 VIS 路由呼叫。 因此，VTCs 可以拨入 Skype for Business 会议（通过拨打与呼叫自动助理相关联的电话号码），但不能将其拖放到会议中。
  
![SfB 中的 VIS 图表](../media/87753af5-b1d9-4107-9216-fde45a1af197.png)
  
## <a name="features"></a>功能

此服务器角色提供：
  
- 由第三方视频系统和 Skype for Business 服务器部署使用的 H-p 格式之间的转换。
    
- 从 VTC 以给定分辨率将单个视频流转换为多个不同分辨率的 simulcast 流，以便在 Skype for Business 服务器部署中使用。 这些流可以发送到 AVMCU，然后发送到 Skype for business 服务器终结点和其他已请求不同解决方案的视频系统。 在 Skype for Business A/V 电话会议中参与第三方视频系统时，也可使用此转换。 在特定 VIS 服务器中达到 "转码" 限制后，针对不同解决方案的任何以下请求将仅接收最低分辨率的流。 
    
- 对 CUCM 网关和 Skype for business 服务器视频互操作服务器之间的视频 SIP 主干的支持;VTCs 将继续向 Cisco 网关注册，并通过网关发起对 Skype for Business 部署的调用。 通过视频 SIP 主干将呼叫从网关传送到 Skype for business 视频互操作服务器。
    
- 支持会议室中的用户使用支持的视频系统从该系统拨号加入开启或关闭的会议。 此呼叫将遍历视频 SIP 中继。
    
- 支持具有支持的视频系统的会议室中的用户呼叫 Skype for Business 客户端。 此呼叫将遍历视频 SIP 中继。
    
- 支持来自 Skype for Business 服务器端或来自支持的 VTC 系统的 mid 呼叫控制，包括静音/取消静音音频、暂停/恢复视频、锁定视频和保持/注销呼叫。
    
## <a name="known-limitations"></a>已知限制

此服务器角色存在以下限制：
  
- 不支持通过视频 SIP 主干从 Skype for Business 部署到 VTCs 的新通话。 . 这意味着只有 VTCs 中的新通话才受视频 SIP 主干的支持。 支持的视频系统的状态将在视频 SIP 主干上不可用。 VIS。 
    
- 对于视频 SIP 中继模式，仅支持独立的 VIS 池。
    
-  对于通过视频 SIP 中继在 VTC 和 VIS 之间进行的通信，支持 TLS + SRTP 或 TCP + RTP。
    
- 不支持应用程序共享。 会议室中的 Skype for business 用户需要加入 Skype for business 会议（通过膝上型电脑），并在不与 VTC 关联的会议室中的一个免费显示器上显示应用共享屏幕。
    
- 不支持 VTC 通过 VIS 加入联盟会议。
    
- 不支持 VTC 通过 VIS 加入联机会议。
    
- 不支持通过 VIS 从 VTC 向 PSTN 路由呼叫。
    
- 不支持通过 VIS 从 PSTN 向 VTC 路由呼叫。
    
## <a name="resiliency-mechanisms"></a>复原机制
<a name="resiliency"> </a>

VIS 支持通过视频 SIP 中继传递的、来自 CUCM 的传入呼叫。 可能会丢失上游或下游连接，因此，要实现强大的复原能力，请考虑两种可能性：
  
1. **VIS 池故障转移**如果视频网关所指向的主 VIS 池处于关闭状态，并且视频网关已将中继定义为两个（或更多） VIS 池，则可以进行恢复。 如果视频网关确定它无法调用主 VIS 池，只需将呼叫路由到辅助 VIS 池。
    
     ![VIS 池故障转移图](../media/390d93c3-e132-4bbd-8d5a-c70ead9cdfad.png)
  
    特定的 VIS 池可以具有多个网关的中继，但正常情况下，特定网关不能中继多个 VIS 池，因此需要执行一项操作来支持此故障转移：在 DNS 中定义2个 FDQNs，将其解析为视频网关的同一 IP 地址。 将每个 FQDN 表示为拓扑文档中的单独视频网关，其中每个视频网关都有一个不同 VIS 池的主干，现在可以恢复。 （如果使用 TLS，则多个名称将需要位于视频网关证书的 SAN 中。）
    
    > [!NOTE]
    > VIS 仅允许传入呼叫来自拓扑文档中配置的网关。 
  
2. **前端故障转移**如果 VIS 池接收到来自 CUCM 的呼叫，但无法访问其主要下一个跃点注册机构或前端池，则呼叫将路由到备份前端池。
    
     ![前端故障转移图表](../media/6ddc08ec-4708-4c23-9e77-0f88899a2a96.png)
  
    VIS 将跟踪其主前端池和其备份前端池的状态（在拓扑文档中的注册机构服务的备份设置中找到该设置）。 将每分钟的选项发送到两个池，并且如果有五个连续失败，VIS 假设特定的前端池处于关闭状态。 如果主前端池标记为 down，并且有可用的已配置的备份，则 VIS 会将新的呼叫从网关发送到备份前端池。 主前端池返回后，VIS 将使用主前端池继续进行新的呼叫。
    
    VIS 还会为来自视频 SIP 中继的呼叫设置 10 秒计时。 如果主下一跃点前端池用于来自视频 SIP 干线的呼叫，并且主要的下一跃点前端池未应答在此计时器值中向其发送的邀请（包括100尝试）到该计时器值的 "备份下一跃点代理"，则为呼叫 s如果已配置，则尝试 hould。 
    
    > [!NOTE]
    > 如果首先尝试了备用下一跃点，则接下来不会尝试主下一跃点。 
  
    管理员还可以使用 Windows PowerShell 故障转移命令强制 VIS 使用备用前端池（例如，当必须在主前端池上执行维护时）。
    
## <a name="co-existence-of-voice-and-video-trunks-to-the-same-gateway-peer"></a>指向同一网关对等方的语音和视频中继的共存
<a name="resiliency"> </a>

Skype for Business 服务器支持使用同一网关对等的语音和视频 SIP 中继。 因此，同一 CUCM 部署可能具有指向中介服务器的语音 SIP 中继和指向 VIS 的视频 SIP 中继。
  
- 需要在语音 SIP 中继的拓扑文档中使用特定 FQDN 定义 PSTN 网关。
    
- PSTN 网关的对等方将为中介服务器。
    
- 如有必要可定义多个语音中继，范围从单个 PSTN 网关涵盖到多个中介服务器池。
    
- 需要在视频 SIP 中继的拓扑文档中定义视频网关并使用与 PSTN 网关相同的 FQDN。
    
- 视频网关的对等方将为 VIS。
    
- 可从视频网关到特定 VIS 池定义单个视频中继。
    
- 需要配置 CUCM 以正确路由通过语音中继（或通过视频中继）的呼叫。 例如，从 VTC 拨号时，可能会使用特殊的拨号前缀；CUCM 可将此拨号前缀与指向 VIS 的呼叫关联，相应的转换规则会从指向 VIS 的 SIP 邀请中去掉此前缀。
    
## <a name="co-existence-of-vis-in-the-skype-for-business-release-with-previous-releases-of-lync"></a>Skype for Business 版本中的 VIS 与先前 Lync 版本的共存
<a name="resiliency"> </a>

VIS 仅可作为 Skype for Business 部署的一部分进行部署。 它可以与属于现有部署的 Lync 2013 会议和客户端进行互操作;在这些情况下，VIS 池需要是 Skype for Business 部署的一部分，其中包含一个注册机构/FE 池，该池是 VIS 池的下一跃点。
  
VIS 不支持在 RTV 和 H.264 之间进行代码转换。 在会议中，Lync 2013 之前的客户端与 VTC 参与者之间不存在视频互操作性。
  
在会议中拥有 Lync 2013 之前的客户端将导致移动客户端使用 RTV 进行发送，因此，当移动客户端成为主要发言方时，VTC 将无法收到任何视频。
  
为了让 Lync 2013 能够与作为 Skype for Business 部署一部分的 VIS 正常开展协作，Lync 2013 需要应用相应的 CU，以便升级 Lync 2013 客户端、CAA 和 AVMCU，从而可以与 VIS 开展协作。
  
VIS 与 Lync 2013 和 Skype for Business 桌面客户端之间的互操作性已经过测试，确定受到支持。
  
VIS 与非桌面（Android、Ipad、Iphone、Windows Phone、LMX 等）的互操作性在 VIS 发布时，适用于发布的适用应用商店中提供的 Skype for Business 客户端已经过测试且受支持。
  
## <a name="recovery-from-packet-loss-via-fec"></a>通过 FEC 从数据包丢失中恢复
<a name="resiliency"> </a>

可打开 FEC 以帮助从数据包丢失中恢复。 如果打开，则 VIS 到 VTC 的路径中使用的视频带宽将增加 50%。
  
## <a name="vis-sizing-and-transcoding-costs"></a>VIS 大小调整和代码转换成本
<a name="resiliency"> </a>

要将来自 Cisco VTC 的单个视频流转换为多个联播视频流，需要利用 CPU 容量。 大约 16 VTCs 可以使用它们的视频 transcoded （假设每个 VTC 的720p 视频流都 transcoded 在720p、simulcast 和适用360p）的单个180p 中，在与 Lync 2013 推荐的 FE 平台相同的单个 VIS 中到3个单独的流。 如果关闭代码转换功能，可以节省 VIS CPU 资源。 但是，VIS 从 VTC 请求的视频图像将为最低的通用分辨率，以便满足 Skype for Business 端的所有接收者要求。 请注意，即便关闭代码转换功能，在 Skype for Business 客户端请求某些 VTC 无法发送的低分辨率时，此功能仍可能会被激活。
  
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

[在 Skype for Business 服务器中部署视频互操作服务器](../deploy/deploy-video-interop-server/deploy-video-interop-server.md)
