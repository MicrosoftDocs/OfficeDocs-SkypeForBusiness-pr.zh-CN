---
title: 规划媒体绕过直接路由
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service:
- msteams
ms.prod: skype-for-business-itpro
localization_priority: Normal
search.appverid: MET150
ms.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
description: 阅读本主题可了解如何规划媒体绕过与电话系统直接路由。
ms.openlocfilehash: 6a152fed20dde9d641abfab1bdba7b211f2dcdb9
ms.sourcegitcommit: 27cf21fb02632e9f65dfa2f995120fb927114b3d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2019
ms.locfileid: "30649209"
---
# <a name="plan-for-media-bypass-with-direct-routing"></a>规划媒体绕过直接路由

## <a name="about-media-bypass-with-direct-routing"></a>有关直接路由的媒体绕过

媒体绕过，可以缩短媒体流量的路径，并降低的更好的性能途中跃点数。 使用媒体旁路，媒体会话边界控制器 (SBC) 而不是通过 Microsoft 电话系统发送它与客户端之间保留。 若要配置媒体绕过、 SBC 和客户端必须相同的位置或网络中。

通过使用**Set CSOnlinePSTNGateway**命令 **-MediaBypass**参数设置为 true 或 false，您可以针对每个 SBC 控制媒体绕过。 如果您启用媒体绕过，这并不意味着在企业网络内，将保持所有媒体通信。 本文介绍在不同方案中的呼叫流程。    

下图说明了具有和没有媒体绕过呼叫流的差异。

媒体旁路的情况下当客户端使或接收呼叫，请信号和媒体之间流动 SBC、 Microsoft 电话系统，和团队客户端，如下图中所示：

![显示信号和媒体流不存在媒体旁路](media/direct-routing-media-bypass-1.png)


但我们假设用户是在同一构建或作为 SBC 网络。 例如，假定正在构建中法兰克福使到 PSTN 用户的呼叫的用户： 

- **没有媒体绕过**，通过阿姆斯特丹或都柏林 （Microsoft 数据中心部署在此） 并返回到在法兰克福 SBC 将流媒体。 

  在欧洲数据中心处于选中状态，因为 SBC 在欧洲，并且 Microsoft 使用 SBC 最接近的数据中心。 虽然此方法不会影响由于优化的通信流大多数地理区域中的 Microsoft 网络内的呼叫质量，流量具有不必要的循环。     

- **使用媒体绕过**，媒体仍保留团队用户直接之间 SBC 下图中所示：

![显示信号和媒体绕过使用的媒体流](media/direct-routing-media-bypass-2.png)

媒体绕过利用协议上团队客户端和 ICE 设备 SBC 调用互动式连接建立 (ICE)。 这些协议启用直接路由中的最直接的媒体路径用于最佳的质量。 ICE 和 ICE 轻量是 WebRTC 标准。 有关这些协议的详细信息，请参阅 RFC 5245。


## <a name="call-flow-and-firewall-planning"></a>呼叫流和防火墙的规划

呼叫流和防火墙的规划取决于用户是否具有直接访问公共 IP 地址的 SBC，以及用户是否为内部或外部网络。

### <a name="call-flow-if-the-user-has-direct-access-to-the-public-ip-address-of-the-sbc"></a>如果用户具有直接访问公共 IP 地址的 SBC，呼叫流

如果用户具有直接访问 SBC 的公共 IP 地址，呼叫流如下所示：

- 媒体绕过团队客户端必须能够访问到公用 IP 地址的 SBC 甚至是从内部网络。 如果不需要直接媒体，媒体能否通过传输中继。

- 这是建议的解决方案，当用户在相同生成和/或 SBC 网络 – 从媒体路径中删除 Microsoft 云组件。

- 通过 Microsoft 云始终信号流。

下图显示启用媒体绕过时的呼叫流和客户端是内部客户端可达到 SBC （直接媒体） 的公共 IP 地址： 

- 箭头和数字值的路径是根据 Microsoft 团队联机呼叫流文档。

- SIP 信号总是采用路径 4 和 4 （取决于通信的方向）。 媒体保持本地和采用路径 5b。

![显示使用媒体旁路的呼叫流启用、 客户端是内部，可达到公用 IP 的会话边界控制器 （直接媒体）](media/direct-routing-media-bypass-3.png)


### <a name="call-flow-if-the-user-does-not-have-access-to-the-public-ip-address-of-the-sbc"></a>如果用户不具有访问公共 IP 地址的 SBC，呼叫流

以下介绍了呼叫流，如果用户不具有访问权的 SBC 的公共 IP 地址。 

例如，假定该用户是外部，并且租户管理员决定不打开 SBC 到 Internet 中的所有人，但仅对 Microsoft 云的公共 IP 地址。 通信的内部组件可以通过团队传输中继流动。 这是公司网络外部的用户的推荐的配置。 请考虑以下事项：

- 使用团队传输中继。

- 媒体绕过，Microsoft 使用需要 （在我们计划将移到的版本，这需要仅 3478 和 3479 端口未来） 中打开端口 50 000 到 59 999 团队传输中继和 SBC 之间的传输中继的版本。

- 为了优化媒体，Microsoft 建议打开仅对团队传输中继 SBC 的公共 IP 地址。 对于公司网络外部的客户端，Microsoft 建议使用传输中继而不直接达到 SBC 的公共 IP 地址。

下图显示启用媒体绕过时的呼叫流和客户端是外部客户端无法访问的会话边界控制器 （媒体中继的团队传输中继） 的公共 IP 地址。

- 箭头和数字值的路径是根据 Microsoft 团队联机呼叫流文档。

- 媒体中继通过路径 3，3，4，4

![如果用户不具有访问公用 IP 的 SBC 显示呼叫流）](media/direct-routing-media-bypass-4.png)


### <a name="call-flow-if-a-user-is-outside-the-network-and-has-access-to-the-public-ip-of-the-sbc"></a>如果某用户是网络外部的并有权访问公用 IP 的 SBC，呼叫流

> [!NOTE]
> 这不是建议的配置，因为它不能利用团队传输中继。 相反，您应考虑前一个场景用户没有访问 SBC 的公共 IP 地址。 

下图显示启用媒体绕过时的呼叫流和客户端是外部客户端可达到 SBC （直接媒体） 的公共 IP 地址。

- 箭头和数字值的路径是根据 Microsoft 团队联机呼叫流文档。

- SIP 信号总是采用路径 3 和 3 （取决于通信的方向）。 使用路径 2 的媒体流。

![如果用户不具有访问公用 IP 的 SBC 显示呼叫流）](media/direct-routing-media-bypass-5.png)


## <a name="use-of-media-processors-and-transport-relays"></a>使用媒体处理器和传输中继

媒体流量的路径中可以是 Microsoft 云中有两个组件： 媒体处理器和传输中继。 

- 媒体处理器是公共面向组件的处理媒体的非绕过的情况下，并处理语音应用程序的媒体。

   媒体处理器通常在最终用户非绕过呼叫的路径，但从不绕过呼叫路径中。 媒体处理器始终位于如呼叫寄存、 组织的自动助理和呼叫的队列的所有语音应用程序的路径。

- 传输中继用于连接到最接近的传输服务，以发送实时通信。

   传输中继可能或可能不是来自或最终用户-具体取决于用户和网络的配置方式发往绕过呼叫-路径中。

下图显示两个呼叫流 – 启用媒体绕过与一个和第二个与媒体绕过已禁用。 注意图表仅说明来自-或往-最终用户通信。  
- 媒体控制器是在分配媒体处理器并创建会话描述协议 (SDP) 提供的 Azure microservice。

- SIP 代理服务器是转换 HTTP REST 信号 SIP 团队中使用的组件。    

![显示显示两个呼叫流 – 媒体绕过与启用和禁用媒体旁路与第二个）](media/direct-routing-media-bypass-6.png)


下表总结了媒体处理器和传输中继之间的差异。

|    | 媒体处理器 | 传输中继|
| :--------------|:---------------|:------------|
面向最终用户的非绕过呼叫的媒体路径中 | 始终 | 从不 | 
面向最终用户的绕过呼叫的媒体路径中 | 从不 | 如果客户端无法访问公共 IP 地址 SBC | 
语音应用程序的媒体路径中 | 始终 | 从不 | 
可以执行转码 (B2BUA)\* | 是 | 否，仅中继终结点之间的音频 | 
Instancess 世界各地的数量和位置 | 总 8： 在美国东和西; 2在阿姆斯特丹和都柏林; 2香港特别行政区和新加坡; 2日本 （正在添加中 Q1CY2019） 2  | 多个

IP 范围是 52.112.0.0 /14 （IP 地址从 52.112.0.1 52.115.255.254）。 

\*转码说明： 

- 媒体处理器是 B2BUA，这意味着可以将其更改编解码器 （例如，绞丝团队客户端从 MP 和 G.711 MP 和 SBC 之间）。

- 传输中继不 B2BUA，这意味着即使通信流通过中继的编解码器永远不会更改客户端和 SBC-之间。

### <a name="use-of-teams-transport-relays-in-escalation-scenarios-if-trunk-is-configured-for-media-bypass"></a>使用团队传输中继的升级情况下是否中继配置了媒体绕过

团队传输中继始终是以下方案中的媒体路径中：

- 呼叫呈报从 1:1 到的组呼叫
- 呼叫转到联盟团队用户
- 转接呼叫或将其转接到业务用户 Skype

滑动您的 SBC 有权访问传输中继，如下所述。    


## <a name="sip-signaling-fqdns-and-firewall-ports"></a>SIP 信号： Fqdn 和防火墙端口

SIP 信号的 FQDN 和防火墙要求是与非绕过的情况下相同。 

直接路由的连接点是具有以下三个 Fqdn:

- 必须首先尝试**sip.pstnhub.microsoft.com** – 全局 FQDN –。 当 SBC 发送请求，若要解决此名称时，Microsoft Azure DNS 服务器返回指向主 Azure 数据中心 IP 地址分配给 SBC。 性能指标的数据中心和地理接近 SBC 基于工作分配。 返回的 IP 地址对应于主要的 FQDN。

- **sip2.pstnhub.microsoft.com** – 辅助 FQDN – 地理位置映射到第二个优先级区域。

- **sip3.pstnhub.microsoft.com** – 第三级 FQDN – 地理位置映射到第三个优先级区域。

必须放置在以下三个 Fqdn:

- 提供最佳用户体验 （不加载和 SBC 数据中心通过查询的第一个 FQDN 分配最接近）。

- 从 SBC 连接建立到数据中心的临时问题时提供故障转移。 有关详细信息，请参阅下面的故障转移机制。


Fqdn **sip.pstnhub.microsoft.com**、 **sip2.pstnhub.microsoft.com**和**sip3.pstnhub.microsoft.com**将解析为以下 IP 地址之一：
- 52.114.148.0
- 52.114.132.46
- 52.114.75.24
- 52.114.76.76
- 52.114.7.24
- 52.114.14.70

您需要打开防火墙以允许与地址的传入和传出流量信号中的所有这些 IP 地址的端口。 如果您的防火墙支持 DNS 名称解析为上面的所有 IP 地址的 FQDN **sip all.pstnhub.microsoft.com** 。 您必须使用以下端口：

| 流量 | 从 | 到 | 源端口 | 目标端口|
| :-------- | :-------- |:-----------|:--------|:---------|
SIP/TLS| SIP 代理服务器 | SBC | 1024-65535 | SBC 上定义 |
| SIP/TLS | SBC | SIP 代理服务器 | SBC 上定义 | 5061 |


## <a name="media-traffic-ip-and-port-ranges"></a>媒体流量： IP 和端口范围

媒体流量之间流动 SBC 和团队客户端直接连接是否可用，或通过团队传输中继如果客户端无法访问 SBC 使用公共 IP 地址。

### <a name="requirements-for-direct-media-traffic-between-the-teams-client-and-the-sbc"></a>直接媒体流量 （团队客户端和 SBC） 之间的要求 

客户端必须具有对 SBC 的公共 IP 地址上的指定端口 （请参见表） 的访问。 

注意： 如果客户端位于内部网络，媒体流的 SBC 的公共 IP 地址。 您可以配置 hairpinning NAT 设备上，以便流量从不离开企业网络设备。

| 流量 | 从 | 到 | 源端口 | 目标端口|
| :-------- | :-------- |:-----------|:--------|:---------|
UDP/SRTP | 客户端 | SBC | 50 000 – 50 019  | SBC 上定义 |
| UDP/SRTP | SBC | 客户端 | SBC 上定义 | 50 000 – 50 019  |


注意： 如果您有转换客户端的源端口的网络设备，请确保之间的网络设备和 SBC 打开转换后的端口。 

### <a name="requirements-for-using-transport-relays"></a>使用传输中继要求

传输中继位于同一个范围为媒体处理器 （无绕过的情况下）： 52.112.0.0 /14 （IP 地址从 52.112.0.1 52.115.255.254）。

下表中显示团队传输中继的端口范围：


| 流量 | 从 | 到 | 源端口 | 目标端口|
| :-------- | :-------- |:-----------|:--------|:---------|
UDP/SRTP | 传输中继 | SBC | 50 000-59 999    | SBC 上定义 |
| UDP/SRTP | SBC | 传输中继 | SBC 上定义 | 50 000 – 59 9999，3478 3479     |


注意： Microsoft 建议每个并发呼叫 SBC 上至少两个端口。 因为 Microsoft 拥有传输中继的两个版本，您需要：

- v4，只能处理的端口范围 50 000 到 59 999

- v6，适用于端口 3478，3479

此时，媒体绕过仅支持传输中继的 v4 版本。 我们将在将来引入 v6 支持。 

您需要打开端口 3478 和转换的 3479。 当 Microsoft 引入了对存在媒体绕过 v6 传输中继支持时，不需要重新配置您的网络设备或 SBCs。 

### <a name="requirements-for-using-media-processors"></a>使用媒体处理器的要求

媒体处理器通常以语音应用程序的媒体路径中。 要求都与非绕过配置相同。


媒体流量的 IP 范围是 52.112.0.0 /14 （IP 地址从 52.112.0.1 52.115.255.254）。

下表中显示的媒体处理器的端口范围：

| 流量 | 从 | 到 | 源端口 | 目标端口|
| :-------- | :-------- |:-----------|:--------|:---------|
UDP/SRTP | 媒体处理器 | SBC | 49 152 – 53 247    | SBC 上定义 |
| UDP/SRTP | SBC | 媒体处理器 | SBC 上定义 | 49 152 – 53 247     |

## <a name="considerations-if-you-have-skype-for-business-phones-in-your-network"></a>如果您有 Skype 业务电话的网络中的注意事项  

如果您有任何 Skype 的网络中的业务终结点使用直接路由-例如，用户可以基于业务客户端--Skype 3PIP 电话团队那些这些用户提供服务中继上的媒体绕过功能必须关闭。

您可以创建单独中继为这些用户，并将其分配的联机语音路由策略。

高级配置步骤：

- 拆分按类型 – 根据用户是否具有 3PIP 电话的用户。

- 创建具有不同 Fqdn 的单独的两个中继： 一个启用媒体绕过;其他不。 

  这两个中继指向同一 SBC。 TLS SIP 信号端口必须不同。 媒体端口必须相同。

- 分配正确中继根据联机语音路由策略中的用户的类型。

下面的示例说明了此逻辑。

| 用户组 | 用户数 | 中继中 OVRP 分配的 FQDN | 启用媒体绕过 |
| :------------ |:----------------- |:--------------|:--------------|
与团队客户端和 3PIP 电话的用户 | 20 | sbc1.contoso.com:5061 | false | 
用户 （包括新团队认证的电话） 的仅团队终结点 | 980 | sbc2.contoso.com:5060 | true

这两个中继可以指向同一 SBC 具有相同的公共 IP 地址。 下图中所示，必须不同，TLS 信号 SBC 上的端口。 请注意，您将需要确保您的证书支持两个中继。 在 SAN，您需要有两个名称 （**sbc1.contoso.com**和**sbc2.contoso.com**） 或拥有通配符证书。


![显示两个中继可以指向同一 SBC 与同一个公共 IP）](media/direct-routing-media-bypass-7.png)

有关如何在相同的 SBC 上配置的两个中继的信息，请参阅您的 SBC 供应商提供的文档：

- AudioCodes
- 功能区
- TE 系统 (Anynode)   

## <a name="client-endpoints-supported-with-media-bypass"></a>客户端终结点支持媒体绕过

支持媒体绕过所有团队终结点，直到进一步通知团队 Web 客户端除外。 

如果用户希望 Microsoft 边缘，Google Chrome 或 Mozilla Firefox 中的团队 Web 应用程序必须关闭此类用户的媒体绕过。 我们将介绍调用将来使用媒体绕过启用中继。   
 
## <a name="see-also"></a>另请参阅

[直接路由配置媒体绕过](direct-routing-configure-media-bypass.md)



