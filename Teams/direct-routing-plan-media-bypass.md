---
title: 使用直接路由规划媒体旁路
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 了解如何使用电话系统直接路由规划媒体旁路，从而缩短媒体流量路径并提高性能。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 638a39a843648ab8fab770c28d92b196201e20f5
ms.sourcegitcommit: c627bd1df17aefdc353bc4da6db169dfe169031e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2022
ms.locfileid: "68680505"
---
# <a name="plan-for-media-bypass-with-direct-routing"></a>使用直接路由规划媒体旁路

## <a name="about-media-bypass-with-direct-routing"></a>关于直接路由的媒体旁路

通过媒体旁路可以缩短媒体流量的路径，并减少传输中的跃点数，以提高性能。 借助媒体旁路，媒体将保留在会话边框控制器 (SBC) 和客户端之间，而不是通过 Microsoft 电话系统发送。 若要配置媒体旁路，SBC 和客户端必须位于同一位置或网络中。

可以通过将 **-MediaBypass** 参数设置为 true 或 false 的 **Set-CSOnlinePSTNGateway** 命令来控制每个 SBC 的媒体旁路。 如果启用媒体旁路，这并不意味着所有媒体流量都将保留在公司网络中。 本文介绍不同方案中的调用流。

下图说明了使用和不绕过媒体的调用流的差异。

如果客户端在 SBC、Microsoft 电话系统和 Teams 客户端之间发出或接收呼叫（包括信号和媒体流）时，无需绕过媒体，如下图所示：

> [!div class="mx-imgBorder"]
> ![显示没有媒体旁路的信号和媒体流。](media/direct-routing-media-bypass-1.png)


但是，假设用户与 SBC 位于同一建筑物或网络中。 例如，假定位于法兰克福某大楼的用户调用 PSTN 用户： 

- **如果不绕过媒体**，媒体将流经阿姆斯特丹或都柏林 (，Microsoft 数据中心部署) ，并返回到法兰克福的 SBC。 

  之所以选择欧洲的数据中心，是因为 SBC 位于欧洲，Microsoft 使用最靠近 SBC 的数据中心。 虽然此方法不会因为优化大多数地理区域中的 Microsoft 网络中的流量而影响呼叫质量，但流量具有不必要的循环。     

- **借助媒体旁路**，媒体将直接保留在 Teams 用户和 SBC 之间，如下图所示：

  > [!div class="mx-imgBorder"]
  > ![显示带媒体旁路的信号和媒体流。](media/direct-routing-media-bypass-2.png)

媒体旁路利用 SBC 上的 Teams 客户端和 ICE 字节上名为交互式连接建立 (ICE) 的协议。 这些协议使直接路由能够使用最直接的媒体路径来获得最佳质量。 ICE 和 ICE Lite 是 WebRTC 标准。 有关这些协议的详细信息，请参阅 RFC 5245。


## <a name="call-flow-and-firewall-planning"></a>呼叫流和防火墙规划

呼叫流和防火墙规划取决于用户是否可以直接访问 SBC 的公共 IP 地址，以及用户是在网络内部还是外部。

### <a name="call-flow-if-the-user-has-direct-access-to-the-public-ip-address-of-the-sbc"></a>如果用户直接访问 SBC 的公共 IP 地址，则呼叫流

如果用户直接访问 SBC 的公共 IP 地址，则调用流如下所示：

- 对于媒体旁路，Teams 客户端必须有权访问 SBC 的公共 IP 地址，甚至从内部网络访问。 如果不需要直接媒体，则媒体可以通过传输中继进行流式传输。

- 当用户与 SBC 位于同一建筑和/或网络中时，建议使用此解决方案 - 从媒体路径中删除 Microsoft 云组件。

- 信号始终流经 Microsoft 云。

下图显示了启用媒体旁路、客户端是内部客户端，并且客户端可以访问 SBC 的公共 IP 地址 (直接媒体) ： 

- 路径的箭头和数值符合 [Microsoft Teams 调用流](./microsoft-teams-online-call-flows.md)。

- SIP 信号始终采用路径 4 和 4' (，具体取决于流量) 的方向。 媒体保持本地并采用路径 5b。

> [!div class="mx-imgBorder"]
> ![显示启用了媒体旁路且客户端为内部的呼叫流。](media/direct-routing-media-bypass-3.png)


### <a name="call-flow-if-the-user-does-not-have-access-to-the-public-ip-address-of-the-sbc"></a>如果用户无权访问 SBC 的公共 IP 地址，则呼叫流

下面介绍如果用户无权访问 SBC 的公共 IP 地址，则调用流。 

例如，假设用户是外部用户，并且租户管理员决定不向 Internet 中的每个人打开 SBC 的公共 IP 地址，而只向 Microsoft 云开放。 流量的内部组件可以通过 Teams 传输中继流动。 比如以下几种情况：

- 使用 Teams 传输中继。

- 对于媒体旁路，Microsoft 使用需要在 Teams 传输中继和 SBC (之间打开端口 50 000 到 59 999 的传输中继版本，我们计划将来移动到需要 3478-3481 端口) 的版本。


下图显示了启用媒体旁路、客户端处于外部状态且客户端无法访问会话边界控制器的公共 IP 地址的调用流， (媒体由 Teams 传输中继) 中继。

- 路径的箭头和数值符合 [Microsoft Teams 调用流](./microsoft-teams-online-call-flows.md)。

- 媒体通过路径 3、3、4 和 4 进行中继

> [!div class="mx-imgBorder"]
> ![如果用户无权访问 SBC 的公共 IP，则显示呼叫流。](media/direct-routing-media-bypass-4.png)


### <a name="call-flow-if-a-user-is-outside-the-network-and-has-access-to-the-public-ip-of-the-sbc"></a>如果用户在网络外部且有权访问 SBC 的公共 IP，则呼叫流

> [!NOTE]
> 这不是建议的配置，因为它不利用 Teams 传输中继。 相反，应考虑用户无法访问 SBC 的公共 IP 地址的上一种情况。 

下图显示了启用媒体旁路、客户端处于外部状态，并且客户端可以访问 SBC 的公共 IP 地址 (直接媒体) 。

- 路径的箭头和数值符合 [Microsoft Teams 调用流](./microsoft-teams-online-call-flows.md) 文章。

- SIP 信号始终采用路径 3 和 3' (，具体取决于流量) 的方向。 使用路径 2 的媒体流。

> [!div class="mx-imgBorder"]
> ![如果用户无权访问 SBC 的公共 IP，则显示呼叫流。](media/direct-routing-media-bypass-5.png)



## <a name="use-of-media-processors-and-transport-relays"></a>使用媒体处理器和传输中继

Microsoft 云中有两个组件可以位于媒体流量的路径中：媒体处理器和传输中继。 

- 媒体处理器是一个面向公众的组件，用于处理非旁路事例中的媒体，并处理语音应用程序的媒体。

   媒体处理器始终位于最终用户非旁路调用的路径中，但从不位于旁路调用的路径中。 媒体处理器始终位于所有语音应用程序（如呼叫寄存、组织自动助理和呼叫队列）的路径中。

- 传输中继用于连接到最近的传输服务以发送实时流量。

   传输中继可能位于旁路呼叫（源自或发往最终用户）的路径中，具体取决于用户的位置以及网络的配置方式。

下图显示了两个调用流 - 一个启用了媒体旁路，另一个已禁用媒体旁路。

> [!NOTE]
> 此图仅说明源自最终用户或发往最终用户的流量。  

- 媒体控制器是 Azure 中的一个微服务，用于分配媒体处理器并创建会话说明协议 (SDP) 产品/服务。

- SIP 代理是一个组件，用于将 Teams 中使用的 HTTP REST 信号转换为 SIP。    

> [!div class="mx-imgBorder"]
> ![显示启用和禁用了媒体旁路的呼叫流。](media/direct-routing-media-bypass-6.png)


下表汇总了媒体处理器和传输中继之间的差异。

|  &nbsp; | 媒体处理器 | 传输中继|
| :--------------|:---------------|:------------|
|在媒体路径中，针对最终用户的非旁路调用 | 总是 | 如果客户端无法直接访问媒体处理器 |
|在媒体路径中，针对最终用户的旁路调用 | 从来 没有 | 如果客户端无法访问公共 IP 地址上的 SBC |
|在语音应用程序的媒体路径中 | 总是 | 从来 没有 |
|可以 (B2BUA) 执行转码 \* | 是 | 否，仅在终结点之间中继音频 |

IP 范围为：
- 52.112.0.0/14 (IP 地址，从 52.112.0.1 到 52.115.255.254) 
- 52.120.0.0/14 (IP 地址，从 52.120.0.1 到 52.123.255.254) 

\* 转码说明： 

- 媒体处理器是 B2BUA，这意味着它可以更改编解码器 (例如，在 MP 和 SBC) 之间将 SILK 从 Teams 客户端更改为 MP 和 G.711。

- 传输中继不是 B2BUA，这意味着在客户端和 SBC 之间永远不会更改编解码器，即使流量通过中继流动也是如此。

### <a name="use-of-teams-media-processors-if-trunk-is-configured-for-media-bypass"></a>如果为媒体旁路配置了中继，则使用 Teams 媒体处理器

在以下方案中，Teams 媒体处理器始终插入到媒体路径中：

- 呼叫从 1：1 升级到组呼叫
- 呼叫将转到联合 Teams 用户
- 呼叫被转发或传输到Skype for Business用户

确保 SBC 有权访问媒体处理器和传输中继范围，如下所述。    


## <a name="sip-signaling-fqdns"></a>SIP 信号：FQDN

对于 SIP 信号，FQDN 和防火墙要求与非旁路情况相同。 

在以下 Microsoft 365 或Office 365环境中提供直接路由：
- Microsoft 365 或 Office 365
- Office 365 GCC
- Office 365 GCC High
- Office 365 DoD 详细了解 GCC、GCC High 和 DoD 等[Office 365和美国政府环境](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government)。

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Microsoft 365、Office 365 和 Office 365 GCC 环境

直接路由的连接点是以下三个 FQDN：

- **sip.pstnhub.microsoft.com** - 必须先尝试全局 FQDN。 当 SBC 发送解析此名称的请求时，Microsoft Azure DNS 服务器将返回一个 IP 地址，该地址指向分配给 SBC 的主 Azure 数据中心。 分配基于数据中心的性能指标以及与 SBC 的地理邻近性。 返回的 IP 地址对应于主 FQDN。

- **sip2.pstnhub.microsoft.com** – 辅助 FQDN - 地理位置映射到第二个优先级区域。

- **sip3.pstnhub.microsoft.com** – 第三级 FQDN - 地理位置映射到第三个优先级区域。

必须放置这三个 FQDN 才能：

- 通过查询第一个 FQDN) ，提供 (加载较少、最接近 SBC 数据中心的最佳体验。

- 建立从 SBC 到遇到临时问题的数据中心的连接时，提供故障转移。 有关详细信息，请参阅下面的故障转移机制。


FQDN **sip.pstnhub.microsoft.com**、 **sip2.pstnhub.microsoft.com** 和 **sip3.pstnhub.microsoft.com** 将解析为以下子网中的 IP 地址：
- 52.112.0.0/14
- 52.120.0.0/14

需要为防火墙中的所有这些 IP 范围打开端口，以允许进出地址的传入和传出流量以进行信号发送。

### <a name="office-365-gcc-dod-environment"></a>Office 365 GCC DoD 环境

直接路由的连接点是以下 FQDN：

**sip.pstnhub.dod.teams.microsoft.us** - 全局 FQDN。 由于Office 365 DoD 环境仅存在于美国数据中心，因此没有二级和第三级 FQDN。

FQDN sip.pstnhub.dod.teams.microsoft.us 将从以下子网解析为 IP 地址：

- 52.127.64.0/21

需要为防火墙中的所有这些 IP 范围打开端口，以允许进出地址的传入和传出流量以进行信号发送。  如果防火墙支持 DNS 名称，则 FQDN sip.pstnhub.dod.teams.microsoft.us 解析为所有这些 IP 子网。 

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC 高环境

直接路由的连接点是以下 FQDN：

**sip.pstnhub.gov.teams.microsoft.us** - 全局 FQDN。 由于 GCC 高环境仅存在于美国数据中心，因此没有二级和第三级 FQDN。

FQDN sip.pstnhub.gov.teams.microsoft.us 将从以下子网解析为 IP 地址：

- 52.127.88.0/21

需要为防火墙中的所有这些 IP 范围打开端口，以允许进出地址的传入和传出流量以进行信号发送。  如果防火墙支持 DNS 名称，则 FQDN sip.pstnhub.gov.teams.microsoft.us 解析为所有这些 IP 子网。 

## <a name="sip-signaling-ports"></a>SIP 信号：端口

对于提供直接路由的所有Office 365环境，端口要求相同：
- Microsoft 365 或 Office 365
- Office 365 GCC
- Office 365 GCC High
- Office 365 DoD

必须使用以下端口：

| 交通 | 从 | 到 | 源端口 | 目标端口|
| :-------- | :-------- |:-----------|:--------|:---------|
| SIP/TLS| SIP 代理 | Sbc | 1024 - 65535 | 在 SBC 上定义 |
| SIP/TLS | Sbc | SIP 代理 | 在 SBC 上定义 | 5061 |


## <a name="media-traffic-ip-and-port-ranges"></a>媒体流量：IP 和端口范围

如果直接连接可用，则媒体流量在 SBC 和 Teams 客户端之间流动;如果客户端无法使用公共 IP 地址访问 SBC，则通过 Teams 传输中继。

### <a name="requirements-for-direct-media-traffic-between-the-teams-client-and-the-sbc"></a>Teams 客户端与 SBC) 之间直接媒体流量 (的要求 

客户端必须有权访问指定端口， (在 SBC 的公共 IP 地址上查看表) 。 

> [!NOTE]
> 如果客户端位于内部网络中，媒体将流向 SBC 的公共 IP 地址。 你可以在 NAT 设备上配置头发固定，以便流量永远不会离开企业网络设备。

| 交通 | 从 | 到 | 源端口 | 目标端口|
| :-------- | :-------- |:-----------|:--------|:---------|
| UDP/SRTP | 客户端 | Sbc | 50000-50019| 在 SBC 上定义 |
| UDP/SRTP | Sbc | 客户端 | 在 SBC 上定义 | 50000-50019  |


> [!NOTE]
> 如果有用于转换客户端源端口的网络设备，请确保在网络设备和 SBC 之间打开翻译的端口。 

### <a name="requirements-for-using-transport-relays"></a>使用传输中继的要求

对于非旁路情况，传输中继与媒体处理器 (的范围相同，) ： 

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Microsoft 365、Office 365 和 Office 365 GCC 环境

- 52.112.0.0 /14 (IP 地址从 52.112.0.1 到 52.115.255.254) 

### <a name="office-365-gcc-dod-environment"></a>Office 365 GCC DoD 环境

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC 高环境

- 52.127.88.0/21


下表显示了适用于所有环境) Teams 传输中继 (端口范围：


| 交通 | 从 | 到 | 源端口 | 目标端口|
| :-------- | :-------- |:-----------|:--------|:---------|
| UDP/SRTP | 传输中继 | Sbc | 50 000 -59 999    | 在 SBC 上定义 |
| UDP/SRTP | Sbc | 传输中继 | 在 SBC 上定义 | 50 000 – 59 999, 3478-3481     |


> [!NOTE]
> Microsoft 建议在 SBC 上每次并发调用至少两个端口。 由于 Microsoft 有两个版本的传输中继，因此需要以下各项：
> 
> - v4，它只能用于端口范围 50 000 到 59 999
> 
> - v6，适用于端口 3478-3481

目前，媒体旁路仅支持 v4 版本的传输中继。 我们将在将来引入对 v6 的支持。 

需要打开端口 3478-3481 以进行转换。 当 Microsoft 引入了对使用媒体旁路的 v6 传输中继的支持时，无需重新配置网络设备或 SBC。 

### <a name="requirements-for-using-media-processors"></a>使用媒体处理器的要求

媒体处理器始终位于语音应用程序和 Web 客户端的媒体路径中 (例如，Edge 中的 Teams 客户端或 Google Chrome) 。 这些要求与非旁路配置的要求相同。


媒体流量的 IP 范围为 

### <a name="office-365-and-office-365-gcc-environments"></a>Office 365和Office 365 GCC 环境

- 52.112.0.0 /14 (IP 地址从 52.112.0.1 到 52.115.255.254) 

### <a name="office-365-gcc-dod-environment"></a>Office 365 GCC DoD 环境

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC 高环境

- 52.127.88.0/21

下表显示了适用于) 的所有环境的媒体处理器 (端口范围：

| 交通 | 从 | 到 | 源端口 | 目标端口|
| :-------- | :-------- |:-----------|:--------|:---------|
| UDP/SRTP | 媒体处理器 | Sbc | 3478-3481 和 49 152 – 53 247    | 在 SBC 上定义 |
| UDP/SRTP | Sbc | 媒体处理器 | 在 SBC 上定义 | 3478-3481 和 49 152 – 53 247     |

## <a name="configure-separate-trunks-for-media-bypass-and-non-media-bypass"></a>为媒体旁路和非媒体旁路配置单独的中继  

如果要从非媒体旁路迁移到媒体旁路，并希望在将所有使用情况迁移到媒体旁路之前确认功能，则可以创建单独的中继和单独的联机语音路由策略，以路由到媒体旁路中继并分配给特定用户。 

高级配置步骤：

- 确定要测试媒体旁路的用户。

- 创建两个具有不同 FQDN 的单独中继：一个启用了媒体旁路;另一个不是。 

  两个中继指向相同的 SBC。 TLS SIP 信号的端口必须不同。 媒体的端口必须相同。

- 创建新的联机语音路由策略，并将媒体旁路中继分配给与此策略的 PSTN 使用情况相关联的相应路由。

- 将新的联机语音路由策略分配给已识别为测试媒体旁路的用户。

下面的示例演示了此逻辑。

| 用户集 | 用户数 | 在 OVRP 中分配的中继 FQDN | 已启用媒体旁路 |
| :------------ |:----------------- |:--------------|:--------------|
| 具有非媒体旁路中继的用户 | 980 | sbc1.contoso.com:5061 | false |
| 具有媒体旁路中继的用户 | 20 | sbc2.contoso.com:5060 | true | 

两个中继可以指向具有相同公共 IP 地址的同一 SBC。 SBC 上的 TLS 信号端口必须不同，如下图所示。 请注意，需要确保证书支持这两个中继。 在 SAN 中，需要有两个名称 (**sbc1.contoso.com** 和 **sbc2.contoso.com**) 或有通配符证书。

> [!div class="mx-imgBorder"]
> ![显示两个中继可以指向具有相同公共 IP 的同一 SBC。](media/direct-routing-media-bypass-7.png)

有关如何在同一 SBC 上配置两个中继的信息，请参阅 SBC 供应商提供的文档：

 - [AudioCodes 部署文档](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Oracle 部署文档](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [功能区通信部署文档](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [TE-Systems (任何节点) 部署文档](https://www.anynode.de/anynode-and-microsoft-teams/)

## <a name="client-endpoints-supported-with-media-bypass"></a>媒体旁路支持的客户端终结点

所有独立的 Teams 桌面客户端、Android 和 iOS 客户端以及 Teams 电话设备都支持媒体旁路。 

对于不支持媒体旁路的所有其他终结点，我们将调用转换为非旁路，即使它作为旁路调用启动。 这会自动发生，不需要管理员执行任何操作。 这包括Skype for Business 3PIP 电话，以及支持直接路由呼叫的 Teams Web 客户端 (在 Microsoft Edge、Google Chrome、Mozilla Firefox) 上运行的基于 WebRTC 的客户端。 
 
## <a name="see-also"></a>另请参阅

[使用直接路由配置媒体旁路](direct-routing-configure-media-bypass.md)
