---
title: 使用直接路由规划媒体旁路
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
description: 阅读本主题, 了解如何使用手机系统直接路由规划媒体旁路。
ms.openlocfilehash: 70d0b5ea61d0d7a8001bb1dbfabda2c45274e521
ms.sourcegitcommit: 6cbdcb8606044ad7ab49a4e3c828c2dc3d50fcc4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/09/2019
ms.locfileid: "36271442"
---
# <a name="plan-for-media-bypass-with-direct-routing"></a>使用直接路由规划媒体旁路

## <a name="about-media-bypass-with-direct-routing"></a>关于直接路由的媒体旁路

媒体绕过使你可以缩短媒体流量的路径, 并减少传输中的跃点数, 从而提高性能。 通过媒体绕过, 媒体将保留在会话边界控制器 (SBC) 和客户端之间, 而不是通过 Microsoft Phone 系统发送。 要配置绕过媒体, SBC 和客户端必须位于同一位置或网络。

你可以通过使用**CSOnlinePSTNGateway**命令, 将 **-MediaBypass**参数设置为 true 或 false 来控制每个 SBC 的媒体旁路。 如果启用 "媒体绕过", 这并不意味着所有媒体流量都将保留在公司网络中。 本文介绍不同方案中的调用流。    

下图展示了通话流程的区别和不使用媒体旁路的情况。

如果不使用媒体绕过, 则在客户端发出或接收呼叫时, SBC、Microsoft Phone 系统和团队客户端之间的信号和媒体流均为, 如下图所示:

![显示不使用媒体旁路的信号和媒体流](media/direct-routing-media-bypass-1.png)


但是, 假设用户与 SBC 位于同一建筑物或网络中。 例如, 假设法兰克福中的大楼的用户拨打 PSTN 用户的电话: 

- 如果**没有媒体绕过**, 媒体将通过阿姆斯特丹或都柏林 (在 Microsoft 数据中心的部署位置) 和返回到法兰克福中的 SBC 传送。 

  由于 SBC 位于欧洲, Microsoft 使用最接近 SBC 的数据中心, 因此已选中 "欧洲数据中心"。 虽然此方法不会影响在大多数地理区域内的 Microsoft 网络中的流量流量优化时的通话质量, 但流量有不必要的循环。     

- **通过媒体绕过**, 媒体将直接保留在团队用户和 SBC 之间, 如下图所示:

![显示媒体绕过的信号和媒体流](media/direct-routing-media-bypass-2.png)

媒体旁路利用在 SBC 上的团队客户端和 ICE lite 上称为交互式连接建立 (ICE) 的协议。 这些协议使直接路由能够使用最直接的媒体路径来获得最佳质量。 冰和 ICE Lite 是 WebRTC 标准。 有关这些协议的详细信息, 请参阅 RFC 5245。


## <a name="call-flow-and-firewall-planning"></a>通话流程和防火墙规划

呼叫流程和防火墙规划取决于用户是否可以直接访问 SBC 的公共 IP 地址, 以及用户是否在网络内部或外部。

### <a name="call-flow-if-the-user-has-direct-access-to-the-public-ip-address-of-the-sbc"></a>如果用户对 SBC 的公共 IP 地址具有直接访问权限, 则为呼叫流

如果用户对 SBC 的公共 IP 地址具有直接访问权限, 则调用流程如下所示:

- 对于媒体绕过, 团队客户端必须有权访问 SBC 的公共 IP 地址 (即使来自内部网络)。 如果直接媒体不是所需的, 媒体可以通过传输中继进行通信。

- 当用户在与 SBC 相同的建筑物和/或网络中时, 建议使用此方法-从媒体路径中删除 Microsoft 云组件。

- 信号始终通过 Microsoft 云发送流。

下图显示了启用媒体旁路时的调用流, 客户端是内部客户端, 并且客户端可以访问 SBC 的公共 IP 地址 (直接媒体): 

- 路径的箭头和数值与[Microsoft 团队 "调用流](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows)" 文章一致。

- SIP 信号始终采用路径4和 4 "(具体取决于流量的方向)。 媒体保持本地, 并采用路径5b。

![显示启用了媒体旁路的呼叫流, 客户端为内部客户端](media/direct-routing-media-bypass-3.png)


### <a name="call-flow-if-the-user-does-not-have-access-to-the-public-ip-address-of-the-sbc"></a>如果用户无权访问 SBC 的公共 IP 地址, 则为呼叫流

如果用户无权访问 SBC 的公共 IP 地址, 则以下描述调用流。 

例如, 假设用户是外部用户, 并且租户管理员决定不将 SBC 的公共 IP 地址打开到 Internet 中的所有人, 但仅限于 Microsoft Cloud。 流量的内部组件可以通过团队传输中继流出。 这是为企业网络外部的用户推荐的配置。 请考虑以下事项：

- 使用团队传输中继。

- 对于媒体绕过, Microsoft 使用传输中继的版本, 需要在团队传输中继和 SBC 之间打开端口 50 000 到 59 999 (将来我们计划移动到仅需要3478和3479端口的版本)。

- 对于媒体优化用途, Microsoft 建议仅将 SBC 的公共 IP 地址打开到团队传输中继。 对于公司网络外部的客户端, Microsoft 建议使用传输中继, 而不是直接到达 SBC 的公共 IP 地址。

下图显示了启用媒体旁路时的调用流, 客户端是外部的, 并且客户端无法访问会话边界控制器的公共 IP 地址 (媒体由团队传输中继进行中继)。

- 路径的箭头和数值与[Microsoft 团队 "调用流](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows)" 文章一致。

- 媒体通过路径3、3 "、4和 4" 进行中继

![显示呼叫流 (如果用户无权访问 SBC 的公共 IP)](media/direct-routing-media-bypass-4.png)


### <a name="call-flow-if-a-user-is-outside-the-network-and-has-access-to-the-public-ip-of-the-sbc"></a>如果用户在网络外部且拥有对 SBC 公共 IP 的访问权限, 则为呼叫流

> [!NOTE]
> 这不是建议的配置, 因为它不会利用团队传输中继。 相反, 你应该考虑以前的情况, 即用户无法访问 SBC 的公共 IP 地址。 

下图显示了启用媒体旁路时的调用流, 客户端是外部的, 并且客户端可以访问 SBC (直接媒体) 的公共 IP 地址。

- 路径的箭头和数值与[Microsoft 团队 "调用流](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows)" 文章一致。

- SIP 信号始终采用路径3和 3 "(具体取决于流量的方向)。 使用路径2进行媒体流。

![显示呼叫流 (如果用户无权访问 SBC 的公共 IP)](media/direct-routing-media-bypass-5.png)


## <a name="use-of-media-processors-and-transport-relays"></a>媒体处理器和传输中继的使用

Microsoft 云中有两个组件可以位于媒体流量的路径中: 媒体处理器和传输中继。 

- 媒体处理器是一个面向公众的组件, 可在非绕过情况下处理媒体并处理语音应用程序媒体。

   媒体处理器始终位于最终用户非绕过呼叫的路径中, 但绝不会位于绕过呼叫的路径中。 媒体处理器始终位于所有语音应用程序的路径中, 例如呼叫寄存、组织的自动助理和通话队列。

- 传输中继用于连接到最接近的传输服务以发送实时流量。

   传输中继可能会 (或可能不在绕过的呼叫) 的路径中, 具体取决于用户的位置和网络的配置方式。

下图显示了两个通话流-一个启用了媒体旁路, 并且禁用了媒体旁路的第二个。 注意图表仅显示从--或目标到最终用户发起的流量。  
- 媒体控制器是 Azure 中的 microservice, 用于分配媒体处理器并创建会话描述协议 (SDP) 提供。

- SIP 代理是将团队中使用的 HTTP REST 信号转换为 SIP 的组件。    

![显示启用和禁用媒体旁路的呼叫流](media/direct-routing-media-bypass-6.png)


下表总结了媒体处理器和传输中继之间的区别。

|    | 媒体处理器 | 传输中继|
| :--------------|:---------------|:------------|
适用于最终用户的非绕过呼叫的媒体路径 | 都 | 绝对 | 
适用于最终用户的绕过呼叫的媒体路径 | 绝对 | 如果客户无法访问公共 IP 地址上的 SBC | 
语音应用程序的媒体路径 | 都 | 绝对 | 
可以执行转码 (B2BUA)\* | 是 | 否, 仅在终结点之间中继音频 | 
全球实例数和位置 | 总共8个: 美国东部和西部2在阿姆斯特丹和都柏林中的2个;2在中国香港和新加坡中;在日本 (在 Q1CY2019 中添加) 的2  | 名

IP 范围是 52.112.0.0/14 (从52.112.0.1 到52.115.255.254 的 IP 地址)。 

\*代码解释解释: 

- 媒体处理器是 B2BUA, 这意味着它可以更改编解码器 (例如, 从团队客户端到 MP, 以及 MP 和 SBC 之间的 711)。

- 传输中继不是 B2BUA, 这意味着在客户端和 SBC 之间不会更改编解码器-即使通信流通过中继流也是如此。

### <a name="use-of-teams-transport-relays-in-escalation-scenarios-if-trunk-is-configured-for-media-bypass"></a>如果为媒体绕过配置了主干, 则在升级方案中使用团队传输中继

在以下情况下, 团队传输中继始终位于媒体路径中:

- 通话从1:1 升级到群组通话
- 呼叫将转到联合团队用户
- 呼叫将转发或转移到 Skype for Business 用户

请确保你的 SBC 有权访问传输中继, 如下所述。    


## <a name="sip-signaling-fqdns"></a>SIP 信号: Fqdn

对于 SIP 信号, FQDN 和防火墙要求与非绕过事例的要求相同。 

直接路由在以下 Office 365 环境中提供:
- Office 365
- Office 365 GCC
- Office 365 GCC 高
- Office 365 DoD 了解有关[Office 365 和美国政府环境](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government)(如 GCC、gcc 高级版和 DoD) 的详细信息。

### <a name="office-365-and-office-365-gcc-environments"></a>Office 365 和 Office 365 GCC 环境

直接路由的连接点是以下三个 Fqdn:

- **sip.pstnhub.microsoft.com** -必须首先尝试全局 FQDN。 当 SBC 发送一个请求来解析此名称时, Microsoft Azure DNS 服务器将返回指向分配给 SBC 的主 Azure 数据中心的 IP 地址。 该作业基于数据中心的性能指标和与 SBC 的地理位置的接近度。 返回的 IP 地址对应于主 FQDN。

- **sip2.pstnhub.microsoft.com** -辅助 FQDN-地理位置映射到第二个优先级区域。

- **sip3.pstnhub.microsoft.com** -第三方 FQDN-地理位置映射到第三个优先级区域。

必须放置这三个 Fqdn 才能:

- 提供最佳体验 (加载时间最少且最接近通过查询第一个 FQDN 分配的 SBC 数据中心)。

- 在将来自 SBC 的连接建立到遇到暂时性问题的数据中心时提供故障转移。 有关详细信息, 请参阅下面的故障转移机制。


Fqdn " **sip.pstnhub.microsoft.com**"、" **sip2.pstnhub.microsoft.com**" 和 " **sip3.pstnhub.microsoft.com** " 将解析为以下 IP 地址之一:
- 52.114.148.0
- 52.114.132.46
- 52.114.75.24
- 52.114.76.76
- 52.114.7.24
- 52.114.14.70

您需要在防火墙中打开所有这些 IP 地址的端口, 以允许传入和传出通信发送和接收来自地址的发送信号。 如果你的防火墙支持 DNS 名称, FQDN **sip-all.pstnhub.microsoft.com**将解析为所有这些 IP 地址。 

### <a name="office-365-gcc-dod-environment"></a>Office 365 GCC DoD 环境

直接路由的连接点是以下 FQDN:

**sip.pstnhub.dod.teams.microsoft.us** -全局 FQDN。 由于 Office 365 DoD 环境仅存在于美国数据中心, 因此没有第二个和第三个 Fqdn。

Fqdn-sip.pstnhub.dod.teams.microsoft.us 将解析为以下 IP 地址之一:

- 52.127.64.33
- 52.127.68.34

您需要在防火墙中打开所有这些 IP 地址的端口, 以允许传入和传出通信发送和接收来自地址的发送信号。  如果你的防火墙支持 DNS 名称, FQDN sip.pstnhub.dod.teams.microsoft.us 将解析为所有这些 IP 地址。 

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC 高环境

直接路由的连接点是以下 FQDN:

**sip.pstnhub.gov.teams.microsoft.us** -全局 FQDN。 由于 GCC 的高环境仅存在于美国数据中心, 因此没有第二个和第三个 Fqdn。

Fqdn-sip.pstnhub.gov.teams.microsoft.us 将解析为以下 IP 地址之一:

- 52.127.88.59
- 52.127.92.64

您需要在防火墙中打开所有这些 IP 地址的端口, 以允许传入和传出通信发送和接收来自地址的发送信号。  如果你的防火墙支持 DNS 名称, FQDN sip.pstnhub.gov.teams.microsoft.us 将解析为所有这些 IP 地址。 

## <a name="sip-signaling-ports"></a>SIP 信号: 端口

对于提供直接路由的所有 Office 365 环境, 端口要求是相同的:
- Office 365
- Office 365 GCC
- Office 365 GCC 高
- Office 365 DoD

您必须使用以下端口:

| 流量 | 从 | 到 | 源端口 | 目标端口|
| :-------- | :-------- |:-----------|:--------|:---------|
SIP/TLS| SIP 代理 | SBC | 1024-65535 | 在 SBC 上定义 |
| SIP/TLS | SBC | SIP 代理 | 在 SBC 上定义 | 5061 |


## <a name="media-traffic-ip-and-port-ranges"></a>媒体流量: IP 和端口范围

如果客户无法使用公共 IP 地址访问 SBC, 则在 SBC 和团队客户端之间进行媒体通信流 (如果直接连接可用或通过团队传输中继)。

### <a name="requirements-for-direct-media-traffic-between-the-teams-client-and-the-sbc"></a>直接媒体流量的要求 (团队客户端和 SBC 之间) 

客户端必须具有对 SBC 公共 IP 地址的指定端口 (见表) 的访问权限。 

注意: 如果客户端在内部网络中, 则媒体将流向 SBC 的公共 IP 地址。 你可以在 NAT 设备上配置 hairpinning, 以使流量永不离开企业网络设备。

| 流量 | 从 | 到 | 源端口 | 目标端口|
| :-------- | :-------- |:-----------|:--------|:---------|
UDP/SRTP | 客户端 | SBC | 50 000-50 019  | 在 SBC 上定义 |
| UDP/SRTP | SBC | 客户端 | 在 SBC 上定义 | 50 000-50 019  |


注意: 如果你有转换客户端源端口的网络设备, 请确保在网络设备和 SBC 之间打开已转换的端口。 

### <a name="requirements-for-using-transport-relays"></a>使用传输中继的要求

传输中继与媒体处理器位于同一范围内 (对于非绕过的情况): 

### <a name="office-365-and-office-365-gcc-environments"></a>Office 365 和 Office 365 GCC 环境

-52.112.0.0/14 (从52.112.0.1 到52.115.255.254 的 IP 地址)

## <a name="office-365-gcc-dod-environment"></a>Office 365 GCC DoD 环境

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC 高环境

- 52.127.88.0/21


下表显示了团队传输中继的端口范围 (适用于所有环境):


| 流量 | 从 | 到 | 源端口 | 目标端口|
| :-------- | :-------- |:-----------|:--------|:---------|
UDP/SRTP | 传输中继 | SBC | 50 000-59 999    | 在 SBC 上定义 |
| UDP/SRTP | SBC | 传输中继 | 在 SBC 上定义 | 50 000-59 999、3478、3479     |


注意: Microsoft 建议在 SBC 上对每个并发调用至少有两个端口。 由于 Microsoft 具有两个版本的传输中继, 因此需要以下内容:

- v4, 它只能使用端口范围 50 000 到 59 999

- v6, 它适用于端口3478、3479

此时, 媒体绕过仅支持传输中继的 v4 版本。 我们将在将来介绍 v6 的支持。 

您需要打开端口3478和3479以进行转换。 当 Microsoft 为具有媒体旁路的 v6 传输中继提供支持时, 不需要重新配置网络设备或 SBCs。 

### <a name="requirements-for-using-media-processors"></a>使用媒体处理器的要求

媒体处理者始终位于语音应用程序和 Web cleints 的媒体路径中 (对于 exampe, 团队 cleint 为 Edge 或 Google Chrome)。 要求与非绕过配置相同。


媒体流量的 IP 范围是 

### <a name="office-365-and-office-365-gcc-environments"></a>Office 365 和 Office 365 GCC 环境

-52.112.0.0/14 (从52.112.0.1 到52.115.255.254 的 IP 地址)

## <a name="office-365-gcc-dod-environment"></a>Office 365 GCC DoD 环境

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC 高环境

- 52.127.88.0/21

下表显示了媒体处理器的端口范围 (适用于所有环境):

| 流量 | 从 | 到 | 源端口 | 目标端口|
| :-------- | :-------- |:-----------|:--------|:---------|
UDP/SRTP | 媒体处理器 | SBC | 49 152-53 247    | 在 SBC 上定义 |
| UDP/SRTP | SBC | 媒体处理器 | 在 SBC 上定义 | 49 152-53 247     |

## <a name="considerations-if-you-have-skype-for-business-phones-in-your-network"></a>在网络中使用 Skype for business 电话时的注意事项  

如果您的网络中有任何使用直接路由的 Skype for Business 终结点 (例如, 团队用户可以拥有基于 Skype for Business 客户端的3PIP 电话), 则为这些用户提供服务的主干上的媒体旁路必须处于关闭状态。

你可以为这些用户创建单独的 trunk, 并为其分配联机语音路由策略。

高级别配置步骤:

- 按类型拆分用户-取决于用户是否具有3PIP 电话。

- 使用不同的 Fqdn 创建两个单独的中继: 一个为媒体绕过启用;另一个不是。 

  这两个中继指向同一个 SBC。 TLS SIP 信号的端口必须不同。 媒体端口必须相同。

- 根据联机语音路由策略中的用户类型分配正确的主干。

下面的示例演示了此逻辑。

| 组用户 | 用户数 | 在 OVRP 中分配的中继 FQDN | 媒体绕过启用 |
| :------------ |:----------------- |:--------------|:--------------|
具有团队客户端和3PIP 手机的用户 | 名 | sbc1.contoso.com:5061 | false | 
只有团队终结点 (包括为团队认证的新电话) 的用户 | 980 | sbc2.contoso.com:5060 | true

这两个中继都可以指向具有相同公共 IP 地址的同一 SBC。 SBC 的 TLS 信号端口必须不同, 如下图所示。 注意你需要确保你的证书支持这两个中继。 在 SAN 中, 你需要具有两个名称 (**sbc1.contoso.com**和**sbc2.contoso.com**) 或具有通配符证书。


![显示两个中继都可以指向具有相同公共 IP 的同一 SBC](media/direct-routing-media-bypass-7.png)

有关如何在同一 SBC 上配置两个中继的信息, 请参阅 SBC 供应商提供的文档:

 - [AudioCodes 部署文档](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Oracle 部署文档](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [功能区通信部署文档](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [TE-系统 (anynode) 部署文档](https://www.anynode.de/anynode-and-microsoft-teams/)

## <a name="client-endpoints-supported-with-media-bypass"></a>媒体绕过支持的客户端终结点

所有团队终结点都支持媒体绕过。

注意对于 webcleints (Microsoft Edge 中的 "团队" Web 应用、Google Chrome 或 Mozilla Firefox), 我们会将调用转换为非绕过, 即使它是绕过调用就开始。 这会自动发生, 不需要管理员执行任何操作。 
 
## <a name="see-also"></a>另请参阅

[使用直接路由配置媒体旁路](direct-routing-configure-media-bypass.md)



