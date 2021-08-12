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
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 了解如何使用直接路由规划电话系统绕过媒体，从而缩短媒体流量的路径并提高性能。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6806af0889f3667e85cc49856e605bbe0334d1be3ea3601a844a3b9f568e7619
ms.sourcegitcommit: 2a76435beaac1e5daa647e93f693ea8672ec0135
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/11/2021
ms.locfileid: "57848937"
---
# <a name="plan-for-media-bypass-with-direct-routing"></a>使用直接路由规划媒体旁路

## <a name="about-media-bypass-with-direct-routing"></a>关于使用直接路由绕过媒体

使用媒体旁路可以缩短媒体流量的路径，并减少传输中的跃点数，以提高性能。 借助媒体旁路，媒体将保留在会话边界控制器 (SBC) 与客户端之间，而不是通过 Microsoft 电话 系统发送。 若要配置媒体绕过，SBC 和客户端必须位于同一位置或网络中。

可以使用 **Set-CSOnlinePSTNGateway** 命令（将 **-MediaBypass** 参数设置为 true 或 false）控制每个 SBC 的媒体旁路。 如果启用媒体旁路，这并不意味着所有媒体流量将位于企业网络中。 本文介绍不同方案中的调用流。

下图演示了在绕过媒体的情况下和没有媒体旁路的情况下呼叫流的差异。

如果没有媒体旁路，当客户端发出或接收呼叫时，SBC、Microsoft 电话 System 和 Teams 客户端之间的信号和媒体流，如下图所示：

> [!div class="mx-imgBorder"]
> ![显示无媒体旁路的信号和媒体流](media/direct-routing-media-bypass-1.png)


但假设用户与 SBC 位于同一建筑物或网络中。 例如，假设位于法兰克福的一栋大楼中的用户呼叫 PSTN 用户： 

- **如果不绕过媒体**，媒体将流经阿姆斯特丹或都柏林 (将 Microsoft 数据中心部署到) 并返回到法兰克福的 SBC。 

  选择欧洲的数据中心是因为 SBC 位于欧洲，而 Microsoft 使用离 SBC 最近的数据中心。 尽管此方法不会由于在大多数地理位置的 Microsoft 网络内优化流量流而影响呼叫质量，但流量具有不必要的循环。     

- **借助媒体** 旁路，媒体直接保留在Teams与 SBC 之间，如下图所示：

  > [!div class="mx-imgBorder"]
  > ![使用媒体旁路显示信号和媒体流](media/direct-routing-media-bypass-2.png)

媒体绕过利用名为交互式连接建立 (ICE) 协议Teams SBC 上的 ICE lite。 这些协议使直接路由能够使用最直接的媒体路径以获得最佳质量。 ICE 和 ICE Lite 是 WebRTC 标准。 有关这些协议的详细信息，请参阅 RFC 5245。


## <a name="call-flow-and-firewall-planning"></a>呼叫流和防火墙规划

呼叫流和防火墙规划取决于用户是否直接访问 SBC 的公共 IP 地址，以及用户是在网络内部还是外部。

### <a name="call-flow-if-the-user-has-direct-access-to-the-public-ip-address-of-the-sbc"></a>如果用户对 SBC 的公共 IP 地址具有直接访问权限，则调用流

如果用户直接访问 SBC 的公共 IP 地址，则调用流如下所示：

- 对于媒体旁路Teams客户端必须有权访问 SBC 的公共 IP 地址，即使从内部网络访问。 如果不需要直接媒体，则媒体可以通过传输中继流动。

- 当用户与 SBC 位于同一大楼和/或网络中时，这是建议的解决方案 - 从媒体路径中删除 Microsoft 云组件。

- 信令始终通过 Microsoft 云流动。

下图显示了启用媒体旁路、客户端在内部且客户端能够访问 SBC 的公共 IP 地址（直接媒体 (呼叫) ： 

- 路径的箭头和数字值与调用流[Microsoft Teams一一。](./microsoft-teams-online-call-flows.md)

- SIP 信号始终采用路径 4 和 4' (，具体取决于流量方向) 。 媒体保持本地，采用路径 5b。

> [!div class="mx-imgBorder"]
> ![显示已启用媒体旁路的呼叫流，客户端在内部](media/direct-routing-media-bypass-3.png)


### <a name="call-flow-if-the-user-does-not-have-access-to-the-public-ip-address-of-the-sbc"></a>如果用户无法访问 SBC 的公共 IP 地址，则调用流

下面介绍如果用户无法访问 SBC 的公共 IP 地址，则说明调用流。 

例如，假设用户是外部用户，并且租户管理员决定不向 Internet 中的每个人开放 SBC 的公共 IP 地址，而只向 Microsoft 云开放。 流量的内部组件可以通过传输中继Teams流。 比如以下几种情况：

- Teams使用传输中继。

- 对于媒体旁路，Microsoft 使用一个传输中继版本，该版本要求在 Teams 传输中继和 SBC (之间打开端口 50 000 到 59 999，我们计划在将来转移到需要 3478-3481 端口) 的版本。


下图显示了启用媒体旁路、客户端在外部以及客户端无法访问会话边界控制器的公共 IP 地址时呼叫流 (媒体由 Teams 传输中继) 。

- 路径的箭头和数字值与调用流[Microsoft Teams一一。](./microsoft-teams-online-call-flows.md)

- 媒体通过路径 3、3、4 和 4' 中继

> [!div class="mx-imgBorder"]
> ![如果用户无法访问 SBC 的公共 IP，则显示呼叫流](media/direct-routing-media-bypass-4.png)


### <a name="call-flow-if-a-user-is-outside-the-network-and-has-access-to-the-public-ip-of-the-sbc"></a>如果用户位于网络外部且有权访问 SBC 的公共 IP，则调用流

> [!NOTE]
> 这不是建议的配置，因为它不会利用Teams中继。 相反，应考虑以前的方案，其中用户无法访问 SBC 的公共 IP 地址。 

下图显示了启用媒体旁路时呼叫流、客户端是外部的，并且客户端可以通过直接媒体服务访问 SBC (IP) 。

- 路径的箭头和数字值与调用流Microsoft Teams[一文。](./microsoft-teams-online-call-flows.md)

- SIP 信号始终采用路径 3 和 3' (，具体取决于流量方向) 。 使用路径 2 的媒体流。

> [!div class="mx-imgBorder"]
> ![如果用户无法访问 SBC 的公共 IP，则显示呼叫流](media/direct-routing-media-bypass-5.png)


## <a name="use-of-media-processors-and-transport-relays"></a>媒体处理器和传输中继的使用

Microsoft 云中的两个组件可以在媒体流量的路径中：媒体处理器和传输中继。 

- 媒体处理器是面向公众的组件，可处理非绕过情况下的媒体，并处理语音应用程序的媒体。

   媒体处理器始终位于最终用户非旁路调用的路径中，但绝不会在旁路调用的路径中。 媒体处理器始终位于所有语音应用程序的路径中，例如呼叫公园、组织自动助理和呼叫队列。

- 传输中继用于连接到最近的传输服务，以发送实时流量。

   传输中继可能位于（源自或目标为最终用户）的绕过调用的路径中，具体取决于用户位于何处以及网络的配置方式。

下图显示了两个呼叫流 - 一个已启用媒体旁路，另一个已禁用媒体旁路。

> [!NOTE]
> 该图仅说明源自或目的地为最终用户的流量。  

- 媒体控制器是 Azure 中的微服务，可分配媒体处理器，并创建 SDP (会话) 协议。

- SIP 代理是一个组件，用于将请求中使用的 HTTP REST Teams转换为 SIP。    

> [!div class="mx-imgBorder"]
> ![显示已启用和禁用媒体旁路的呼叫流](media/direct-routing-media-bypass-6.png)


下表总结了媒体处理器与传输中继的区别。

|    | 媒体处理器 | 传输中继|
| :--------------|:---------------|:------------|
最终用户的非绕过呼叫的媒体路径 | 始终 | 如果客户端无法直接访问媒体处理器 | 
最终用户的旁路呼叫的媒体路径 | 从不 | 如果客户端无法访问公共 IP 地址上的 SBC | 
在语音应用程序的媒体路径中 | 始终 | 从不 | 
可以在 B2BUA (转码) \* | 是 | 否，仅中继终结点之间的音频 | 
全球实例数和位置 | 总共 10 个：美国东部和西部 2 个;2（阿姆斯特丹和都柏林）;2（香港特别行政区和新加坡）;2（日本）;澳大利亚东部和东南部 2 个 | 多个

IP 范围包括：
- 52.112.0.0/14 (IP 地址从 52.112.0.1 到 52.115.255.254) 
- 52.120.0.0/14 (IP 地址从 52.120.0.1 到 52.123.255.254) 

\* 转码说明： 

- 媒体处理器是 B2BUA，这意味着它可以在 MP 和 SBC (之间更改编解码器，例如 SILK 从 Teams 客户端更改为 MP 和 G.711) 。

- 传输中继不是 B2BUA，这意味着，即使流量通过中继流动，编解码器也永远不会在客户端和 SBC 之间更改。

### <a name="use-of-teams-media-processors-if-trunk-is-configured-for-media-bypass"></a>如果为Teams配置了中继，则使用媒体处理器

Teams在以下情况中，媒体处理器始终插入到媒体路径中：

- 通话从 1：1 升级到群组通话
- 呼叫将进入联合Teams用户
- 呼叫转接或转接给Skype for Business用户

确保 SBC 有权访问媒体处理器和传输中继范围，如下所述。    


## <a name="sip-signaling-fqdns"></a>SIP 信号：FQDN

对于 SIP 信号，FQDN 和防火墙要求与非绕过情况相同。 

直接路由在下列环境或Microsoft 365 Office 365提供：
- Microsoft 365 或 Office 365
- Office 365 GCC
- Office 365 GCC高
- Office 365DoD 详细了解 Office 365和[美国政府](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government)环境，例如 GCC、GCC High 和 DoD。

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Microsoft 365、Office 365 和 Office 365 GCC 环境

直接路由的连接点为以下三个 FQDN：

- **sip.pstnhub.microsoft.com** - 全局 FQDN – 必须先尝试。 当 SBC 发送解析此名称的请求时，Microsoft Azure DNS 服务器将返回指向分配给 SBC 的主要 Azure 数据中心的 IP 地址。 分配基于数据中心的性能指标和与 SBC 的地理邻近性。 返回的 IP 地址对应于主 FQDN。

- **sip2.pstnhub.microsoft.com** - 辅助 FQDN - 在地理上映射到第二个优先级区域。

- **sip3.pstnhub.microsoft.com** - 第三级 FQDN - 在地理上映射到第三个优先区域。

必须放置这三个 FQNS，以便：

- 通过查询第一个 FQDN (，在负载较少且最接近分配的 SBC 数据中心时提供最佳) 。

- 从 SBC 建立到遇到临时问题的数据中心的连接时，提供故障转移。 有关详细信息，请参阅下面的故障转移机制。


FQDN **sip.pstnhub.microsoft.com、sip2.pstnhub.microsoft.com** 和 **sip3.pstnhub.microsoft.com** 将解析为以下子网中的 IP 地址：
- 52.112.0.0/14
- 52.120.0.0/14

需要在防火墙中打开所有这些 IP 范围的端口，以允许传入和传出流量传入和传出地址以发出信号。 如果防火墙支持 DNS 名称，FQDN **sip-all.pstnhub.microsoft.com** 解析为所有这些 IP 子网。 

### <a name="office-365-gcc-dod-environment"></a>Office 365 GCC DoD 环境

直接路由的连接点是以下 FQDN：

**sip.pstnhub.dod.teams.microsoft.us** - 全局 FQDN。 由于Office 365 DoD 环境仅存在于美国数据中心，因此没有辅助和第三级 FQD。

FQDN sip.pstnhub.dod.teams.microsoft.us 将解析为以下子网中的 IP 地址：

- 52.127.64.0/21

需要在防火墙中打开所有这些 IP 范围的端口，以允许传入和传出流量传入和传出地址以发出信号。  如果防火墙支持 DNS 名称，FQDN sip.pstnhub.dod.teams.microsoft.us 解析为所有这些 IP 子网。 

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC高环境

直接路由的连接点是以下 FQDN：

**sip.pstnhub.gov.teams.microsoft.us** - 全局 FQDN。 由于GCC高环境仅存在于美国数据中心，因此没有辅助和第三级 FQDN。

FQDN sip.pstnhub.gov.teams.microsoft.us 解析为以下子网中的 IP 地址：

- 52.127.88.0/21

需要在防火墙中打开所有这些 IP 范围的端口，以允许传入和传出流量传入和传出地址以发出信号。  如果防火墙支持 DNS 名称，FQDN sip.pstnhub.gov.teams.microsoft.us 解析为所有这些 IP 子网。 

## <a name="sip-signaling-ports"></a>SIP 信号：端口

对于提供直接路由的所有Office 365端口要求相同：
- Microsoft 365 或 Office 365
- Office 365 GCC
- Office 365 GCC高
- Office 365DoD

必须使用以下端口：

| 流量 | 从 | 到 | 源端口 | 目标端口|
| :-------- | :-------- |:-----------|:--------|:---------|
SIP/TLS| SIP 代理 | SBC | 1024 - 65535 | 在 SBC 上定义 |
| SIP/TLS | SBC | SIP 代理 | 在 SBC 上定义 | 5061 |


## <a name="media-traffic-ip-and-port-ranges"></a>媒体流量：IP 和端口范围

媒体流量在 SBC 和 Teams客户端之间流动（如果直接连接可用）或Teams传输中继（如果客户端无法使用公共 IP 地址访问 SBC）。

### <a name="requirements-for-direct-media-traffic-between-the-teams-client-and-the-sbc"></a>在客户端与 SBC (之间Teams媒体流量流量)  

客户端必须有权访问指定的端口， (SBC) IP 地址上的表。 

> [!NOTE]
> 如果客户端位于内部网络中，则媒体将流向 SBC 的公共 IP 地址。 可以在 NAT 设备上配置发固定，使流量永远不会离开企业网络设备。

| 流量 | 从 | 到 | 源端口 | 目标端口|
| :-------- | :-------- |:-----------|:--------|:---------|
UDP/SRTP | 客户端 | SBC | 3478-3481 和 49152 – 53247| 在 SBC 上定义 |
| UDP/SRTP | SBC | 客户端 | 在 SBC 上定义 | 3478-3481 和 49152 – 53247  |


> [!NOTE]
> 如果有转换客户端源端口的网络设备，请确保在网络设备和 SBC 之间打开转换的端口。 

### <a name="requirements-for-using-transport-relays"></a>使用传输中继的要求

对于非绕过情况，传输中继与媒体处理器 (相同) ： 

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Microsoft 365、Office 365 和 Office 365 GCC 环境

- 52.112.0.0 /14 (IP 地址从 52.112.0.1 到 52.115.255.254) 

### <a name="office-365-gcc-dod-environment"></a>Office 365 GCC DoD 环境

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC高环境

- 52.127.88.0/21


适用于所有Teams环境 (传输中继的) 范围如下表所示：


| 流量 | 从 | 到 | 源端口 | 目标端口|
| :-------- | :-------- |:-----------|:--------|:---------|
UDP/SRTP | 传输中继 | SBC | 50 000 -59 999    | 在 SBC 上定义 |
| UDP/SRTP | SBC | 传输中继 | 在 SBC 上定义 | 50 000 – 59 999, 3478-3481     |


> [!NOTE]
> Microsoft 建议在 SBC 上每个并发调用至少使用两个端口。 由于 Microsoft 有两个版本的传输中继，因此需要以下各项：
> 
> - v4，只能使用端口范围 50 000 到 59 999
> 
> - v6，适用于端口 3478-3481

目前，媒体绕过仅支持 v4 版本的传输中继。 我们将在将来引入对 v6 的支持。 

需要打开端口 3478-3481 进行转换。 当 Microsoft 引入了对具有媒体旁路的 v6 传输中继的支持时，不需要重新配置网络设备或 SDC。 

### <a name="requirements-for-using-media-processors"></a>使用媒体处理器的要求

媒体处理器始终位于语音应用程序和 Web 客户端的媒体路径中 (例如，Teams Edge 或 Google Chrome) 。 要求与非绕过配置相同。


媒体流量的 IP 范围为 

### <a name="office-365-and-office-365-gcc-environments"></a>Office 365 Office 365 GCC环境

- 52.112.0.0 /14 (IP 地址从 52.112.0.1 到 52.115.255.254) 

### <a name="office-365-gcc-dod-environment"></a>Office 365 GCC DoD 环境

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC高环境

- 52.127.88.0/21

下表显示了适用于所有 (环境的媒体处理器) 范围：

| 流量 | 从 | 到 | 源端口 | 目标端口|
| :-------- | :-------- |:-----------|:--------|:---------|
UDP/SRTP | 媒体处理器 | SBC | 3478-3481 和 49 152 – 53 247    | 在 SBC 上定义 |
| UDP/SRTP | SBC | 媒体处理器 | 在 SBC 上定义 | 3478-3481 和 49 152 – 53 247     |

## <a name="configure-separate-trunks-for-media-bypass-and-non-media-bypass"></a>为媒体旁路和非媒体旁路配置单独的中继  

如果要从非媒体旁路迁移到媒体旁路，并且想要在将所有使用迁移到媒体旁路之前确认功能，可以创建单独的中继和单独的联机语音路由策略，以路由到媒体旁路中继并分配给特定用户。 

高级配置步骤：

- 标识要测试媒体绕过的用户。

- 使用不同的 FQDN 创建两个单独的中继：一个已启用媒体旁路;另一个不是。 

  这两个中继都指向同一 SBC。 TLS SIP 信号的端口必须不同。 媒体的端口必须相同。

- 创建新的联机语音路由策略，并将媒体旁路中继分配到与此策略的 PSTN 使用情况关联的相应路由。

- 将新的联机语音路由策略分配给标识为测试媒体绕过的用户。

以下示例演示了此逻辑。

| 一组用户 | 用户数 | 在 OVRP 中分配的中继 FQDN | 已启用媒体旁路 |
| :------------ |:----------------- |:--------------|:--------------|
具有非媒体旁路中继的用户 | 980 | sbc1.contoso.com:5061 | false |
具有媒体旁路中继的用户 | 20 | sbc2.contoso.com:5060 | true | 

这两个中继可以指向同一公共 IP 地址相同的 SBC。 SBC 上的 TLS 信号端口必须不同，如下图所示。 请注意，需要确保证书支持这两个中继。 在 SAN 中，需要具有两个名称 (sbc1.contoso.com sbc2.contoso.com) 或具有通配符证书。 

> [!div class="mx-imgBorder"]
> ![显示两个中继可以指向同一公共 IP 相同的 SBC](media/direct-routing-media-bypass-7.png)

若要了解如何在同一 SBC 上配置两个中继，请参阅 SBC 供应商提供的文档：

 - [AudioCodes 部署文档](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Oracle 部署文档](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [功能区通信部署文档](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [TE-Systems (anynode) 部署文档](https://www.anynode.de/anynode-and-microsoft-teams/)

## <a name="client-endpoints-supported-with-media-bypass"></a>媒体旁路支持的客户端终结点

所有独立桌面客户端、Android Teams iOS 客户端和 Teams 电话 设备都支持媒体旁路。 

对于不支持媒体旁路的所有其他终结点，我们会将呼叫转换为非旁路，即使它作为绕过呼叫启动。 这会自动发生，不需要管理员执行任何操作。 这包括 Skype for Business 3PIP 电话和 Teams Web 客户端，这些客户端支持在 Microsoft Edge、Google Chrome、Mozilla Firefox) 上运行的基于 (WebRTC 的客户端进行直接路由。 
 
## <a name="see-also"></a>另请参阅

[使用直接路由配置媒体旁路](direct-routing-configure-media-bypass.md)
