---
title: 规划视频互操作服务器Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
f1.keywords:
- ms.lync.plan.VideoInterop
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 4a8daf23-77ba-428b-bcbc-161f6af52c11
description: 摘要：在计划将远程会议Skype for Business Server第三方电话会议设备时，请查看本主题。
ms.openlocfilehash: 0e94a7fc84d4174c3fe562355a6550a1b77d909c
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58607899"
---
# <a name="plan-for-video-interop-server-in-skype-for-business-server"></a>规划视频互操作服务器Skype for Business Server
 
**摘要：** 在计划将远程会议Skype for Business Server第三方电话会议设备时，请查看本主题。
  
Skype for Business Server现在允许您集成某些第三方 VTC (视频电话会议系统) 解决方案。 实现此视频会议互操作性的新服务器角色是视频互操作服务器 (VIS) ，它当前作为仅可用于本地安装的独立服务器角色实现。 VIS 充当第三方电话会议系统和会议部署之间的Skype for Business Server中介。 对于此版本，VIS 侧重于与 Cisco/Tandberg 视频系统的互操作性。 查看本文，确定是否在安装过程中使用Skype for Business Server此功能。
  
## <a name="device-interoperability"></a>设备互操作性

通过 Cisco 统一通信管理器 (CallManager 或 CUCM) 版本 10.5 注册的 Cisco VTC 以及 CUCM 和 VIS 之间设置的 TCP SIP 中继，对互操作进行测试和支持。
  
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
>  这些系统上需要 Cisco 软件版本 TC7.0.0 或Skype for Business Server才能按预期工作。
  
## <a name="sip-trunks"></a>SIP 中继

视频互操作服务器在 SIP 中继模式下运行，其中 VTC 继续注册现有的 Cisco 基础结构，例如 Cisco 呼叫管理器 (CUCM) 。 在 CUCM 和 VIS 之间定义视频 SIP 中继，以便可以在两个系统之间路由呼叫。 仅支持通过 SIP 中继从 VTC 到 VIS 的呼叫。 因此，VTC 可以通过拨打与呼叫自动助理) 关联的电话号码 (拨入 Skype for Business 会议，但不能拖放到会议。
  
![SfB 中的 VIS 关系图](../media/87753af5-b1d9-4107-9216-fde45a1af197.png)
  
## <a name="features"></a>功能

此服务器角色提供：
  
- 第三方视频系统使用的 H.264 格式与 Skype for Business Server转换。
    
- 将采用给定分辨率的单个视频流从 VTC 转换为多个不同分辨率的双播流，以用于 Skype for Business Server 部署。 这些流可以发送到 AVMCU，然后发送到Skype for Business Server请求不同分辨率的其他视频系统。 当第三方视频系统参与 A/V 电话会议时，也会Skype for Business转换。 在特定的 VIS 服务器中达到转码限制后，对不同分辨率的任何以下请求都只会收到分辨率最低的流。 
    
- 支持 CUCM 网关与 Skype for Business Server 互操作服务器之间的视频 SIP 中继;VTC 继续注册 Cisco 网关，并通过网关向 Skype for Business发起呼叫。 呼叫通过视频 SIP 中继从Skype for Business路由到视频互操作服务器。
    
- 支持会议室中具有支持的视频系统的用户从该系统拨号加入打开或关闭的会议。 此呼叫将遍历视频 SIP 中继。
    
- 支持会议室中的用户通过支持的视频系统呼叫Skype for Business客户端。 呼叫将遍历 SIP 中继。
    
- 支持从 Skype for Business Server 端或支持的 VTC 系统控制点到点呼叫和多点呼叫，包括静音/取消静音音频、暂停/恢复视频、锁定视频以及保持/取消保留呼叫。
    
## <a name="known-limitations"></a>已知限制

此服务器角色具有以下限制：
  
- 不支持从 Skype for Business通过视频 SIP 中继部署到 VTC 的新呼叫。 . 这意味着视频 SIP 中继仅支持从 VTC 到 Skype for Business部署的新呼叫。 支持的视频系统状态无法通过视频 SIP 中继提供给 VIS。 
    
- 视频 SIP 中继模式仅支持独立 VIS 池。
    
-  VTC 与 VIS 之间通过视频 SIP 中继的通信将支持 TLS + SRTP 或 TCP + RTP。
    
- 不支持应用程序共享。 会议室Skype for Business用户需要通过笔记本电脑（例如) ）加入 Skype for Business 会议 (，并且需要在未与 VTC 关联的会议室中的其中一台免费显示器上显示应用共享屏幕。
    
- 不支持 VTC 通过 VIS 加入联盟会议。
    
- 不支持 VTC 通过 VIS 加入联机会议。
    
- 不支持通过 VIS 从 VTC 呼叫 PSTN。
    
- 不支持通过 VIS 从 PSTN 呼叫 VTC。
    
## <a name="resiliency-mechanisms"></a>复原机制
<a name="resiliency"> </a>

VIS 支持通过视频 SIP 中继传输的 CUCM 传入呼叫。 可能会丢失上游或下游的连接，因此若要获得强大的复原能力，请考虑以下两种可能性：
  
1. **VIS 池故障转移** 如果视频网关指向的主 VIS 池关闭，则当视频网关在 VIS 池中定义了指向两个或多个 (的中继) 恢复。 如果视频网关确定它无法对主 VIS 池进行呼叫，则只需将呼叫路由到辅助 VIS 池。
    
     ![VIS 池故障转移关系图](../media/390d93c3-e132-4bbd-8d5a-c70ead9cdfad.png)
  
    特定 VIS 池可以具有到多个网关的中继，但通常特定网关无法具有多个 VIS 池的中继，因此需要执行技巧来支持此故障转移：在 DNS 中定义 2 个 FDQN，它们解析为视频网关的相同 IP 地址。 将每个 FQDN 表示为拓扑文档中的单独视频网关，其中每个视频网关都有一个到不同 VIS 池的中继，现在可以恢复。  (如果使用 TLS，则多个名称将需要位于视频网关证书的 SAN 中。) 
    
    > [!NOTE]
    > VIS 仅允许来自拓扑文档中配置的网关的传入呼叫。 
  
2. **前端故障转移** 如果 VIS 池收到来自 CUCM 的呼叫，但无法访问其主下一跃点注册器或前端池，则呼叫将路由到备份前端池。
    
     ![前端故障转移关系图](../media/6ddc08ec-4708-4c23-9e77-0f88899a2a96.png)
  
    VIS 将跟踪其主前端池及其备份前端池的状态 (该设置位于拓扑文档集中注册器服务的备份设置) 。 它会向两个池一分钟发送一次"选项"轮询，如果连续五次失败，VIS 将假定特定前端池出现故障。 如果主前端池标记为"关闭"，并且存在一个可用的配置备份，VIS 将新呼叫从网关发送到备份前端池。 主前端池返回后，VIS 将恢复使用主前端池进行新呼叫。
    
    VIS 还将对来自视频 SIP 中继的呼叫实施 10 秒计时器。 如果下一跃点主前端池用于来自视频 SIP 中继的呼叫，并且下一跃点主前端池未通过某些 SIP 消息 (包括 100 尝试) 在此计时器值中发送给它的 Invite 应答，则应该尝试呼叫的备份下一跃点代理（如果配置）。 
    
    > [!NOTE]
    > 如果首先尝试备份下一个跃点，则下一步将不会尝试主跃点。 
  
    管理员还可使用 Windows PowerShell 故障转移命令强制 VIS 使用备份前端池，例如，在主前端池上必须执行维护时。
    
## <a name="co-existence-of-voice-and-video-trunks-to-the-same-gateway-peer"></a>语音和视频中继共存到同一网关对等方
<a name="resiliency"> </a>

Skype for Business Server语音和视频 SIP 中继使用相同的对等网关。 因此，同一 CUCM 部署可以具有到中介服务器的语音 SIP 中继和到 VIS 的视频 SIP 中继。
  
- PSTN 网关将需要使用语音 SIP 中继的拓扑文档中的特定 FQDN 进行定义。
    
- PSTN 网关的对等方将是中介服务器。
    
- 如有必要，可以定义从 PSTN 网关到多个中介服务器池的多个语音中继。
    
- 视频网关需要在拓扑文档中为与 PSTN 网关具有相同的 FQDN 的视频 SIP 中继定义。
    
- 视频网关的对等方将为 VIS。
    
- 可以定义从视频网关到特定 VIS 池的单个视频中继。
    
- 需要将 CUCM 配置为通过语音中继和视频中继正确路由呼叫。 例如，从 VTC 拨号时，可能会使用特殊的拨号前缀;CUCM 可以将此拨号前缀与对 VIS 的呼叫关联，相应的转换规则会从"SIP 邀请到 VIS"中去除此前缀。
    
## <a name="co-existence-of-vis-in-the-skype-for-business-release-with-previous-releases-of-lync"></a>在早期版本的 Lync Skype for Business中共存 VIS
<a name="resiliency"> </a>

VIS 只能作为部署部署的一Skype for Business一部分。 它可以与 Lync 2013 会议以及作为现有部署的一部分的客户端进行互操作;在这种情况下，VIS 池将需要是包含注册器/FE 池（作为 VIS 池的下一个跃点）Skype for Business部署中的一部分。
  
VIS 不支持在 RTV 和 H.264 之间进行转码。 Lync 2013 之前客户端与会议中的 VTC 参与者之间没有视频互操作性。
  
在会议中设置 Lync 2013 之前客户端将导致移动客户端使用 RTV 发送，从而导致 VTC 在移动客户端成为主要扬声器时不接收视频。
  
为了使 Lync 2013 与作为 Skype for Business 部署的一部分的 VIS 正确工作，Lync 2013 需要应用相应的 CU，以升级 Lync 2013 客户端、CAA 和 AVMCU 以使用 VIS。
  
VIS 与 Lync 2013 和 Skype for Business客户端的互操作性已经过测试且受支持。
  
VIS 与非桌面 (Android、Ipad、Iphone、Windows Phone、LMX 等 ) Skype for Business 客户端的互操作性在 VIS 发布时可从适用的应用商店获得测试，并且受支持。
  
## <a name="recovery-from-packet-loss-via-fec"></a>通过 FEC 从数据包丢失中恢复
<a name="resiliency"> </a>

可以启用 FEC，帮助从数据包丢失中恢复。 如果打开，将在 VIS 到 VTC 方向使用 50% 以上的视频带宽。
  
## <a name="vis-sizing-and-transcoding-costs"></a>VIS 大小调整和转换成本
<a name="resiliency"> </a>

将单个视频流从 Cisco VTC 转码为多个双播流使用 CPU 容量。 假定每个 VTC 中的 720p 视频流在运行在 Lync 2013 建议的FE 平台等效的单个 VIS 中，在 720p、360p 和 180p) 中，大约 16 个 VTC 可以转换其视频代码 (假定其视频流在 720p、360p 和 180p 流中转换代码。 如果关闭转换码功能，这将节省 VIS CPU。 但是，VIS 从 VTC 请求的视频图像将是满足 VTC 上所有接收器的最低Skype for Business分辨率。 请注意，即使关闭代码转换，在客户端请求Skype for Business VTC 无法发送的某些低分辨率时，也可以激活转换代码。
  
## <a name="call-distribution-from-the-video-gateway-to-vis"></a>从视频网关到 VIS 的呼叫分布
<a name="resiliency"> </a>

分发通过 CUCM 分发机制之一实现：
  
- 使用 DNS 动态。
    
- 在 CUCM 端，可以定义单独的中继，其中每个中继终止于 VIS 池中的不同服务器上。 CUCM 将跨不同中继路由呼叫。
    
## <a name="no-hybrid-interoperability"></a>无混合互操作性
<a name="resiliency"> </a>

对通过本地 VIS 加入联机会议的 VTC 的支持并不Skype for Business。
  
## <a name="no-federation-support"></a>无联合身份验证支持
<a name="resiliency"> </a>

对通过 VIS 加入联盟会议的 VTC 的支持并不Skype for Business。
  
## <a name="see-also"></a>另请参阅
<a name="resiliency"> </a>

[在部署视频互操作服务器Skype for Business Server](../deploy/deploy-video-interop-server/deploy-video-interop-server.md)
