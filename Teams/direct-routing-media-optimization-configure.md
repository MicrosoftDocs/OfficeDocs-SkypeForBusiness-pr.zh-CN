---
title: 为本地媒体优化配置直接路由Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 04/07/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: filippse
search.appverid: MET150
f1.keywords:
- NOCSH
description: 为直接路由配置本地媒体优化
appliesto:
- Microsoft Teams
ms.openlocfilehash: e53296b54cd55d6444f665476de020be1ee314e807f905d561ee181e50486333
ms.sourcegitcommit: 2a76435beaac1e5daa647e93f693ea8672ec0135
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/11/2021
ms.locfileid: "57848637"
---
# <a name="configure-local-media-optimization-for-direct-routing"></a>为直接路由配置本地媒体优化

本地媒体优化的配置基于其他云语音功能常用的网络设置，例如Location-Based路由和动态紧急呼叫。 若要详细了解网络区域、网络站点、网络子网和受信任的 IP 地址，请参阅云 [语音功能的网络设置](cloud-voice-network-settings.md)。

配置本地媒体优化之前，请参阅 [直接路由的本地媒体优化](direct-routing-media-optimization.md)。  

若要配置本地媒体优化，需要执行以下步骤。 可以使用 Teams 管理中心或 PowerShell。 有关详细信息，请参阅 [管理网络拓扑](manage-your-network-topology.md)。

1. 根据本文 (配置用户和 SBC) 。
2. 根据 SBC 供应商规范配置用于本地媒体优化 (SBC) 。

下图显示了本文中示例中使用的网络设置。

![显示示例网络设置的示意图](media/direct-routing-media-op-9.png "示例的网络设置")


## <a name="configure-the-user-and-the-sbc-sites"></a>配置用户和 SBC 站点

若要配置用户和 SBC 站点，需要：

1. [管理外部受信任的 IP 地址](#manage-external-trusted-ip-addresses)。  

2. [通过配置网络区域](#define-the-network-topology) 、网络站点和网络子网来定义网络拓扑。

3. [通过使用相关模式和](#define-the-virtual-network-topology) 代理 SBC (将 SBC) 分配到 () 定义虚拟网络拓扑。


## <a name="configure-sbcs-for-local-media-optimization-according-to-the-sbc-vendor-specification"></a>根据 SBC (规范) SBC 优化的 SBC 应用

本文介绍 Microsoft 组件的配置。 有关 SBC 配置的信息，请参阅 SBC 供应商文档。

以下 SBC 供应商支持本地媒体优化：

| 供应商 | 产品 |    软件版本 |
|:------------|:-------|:-------|
| [Audiocodes](https://www.audiocodes.com/media/13253/connecting-audiocodes-sbc-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf) |    Mediant 500 SBC |   7.20A.256 | 
|            |  Mediant 800 SBC |   7.20A.256 | 
|            |  Mediant 2600 SBC |  7.20A.256 | 
|            |  Mediant 4000 SBC |  7.20A.256 | 
|            |  Mediant 1000B SBC | 7.20A.256 | 
|            |  Mediant 9000 SBC |  7.20A.256 | 
|            |  Mediant Virtual Edition SBC |   7.20A.256 | 
|            |  Mediant Cloud Edition SBC | 7.20A.256 |
| [功能区 SBC Core](https://support.sonus.net/display/ALLDOC/SBC+8.2+-+Configure+Local+Media+Optimization)  |  SBC 5110         | 8.2  |
|            |  SBC 5210         | 8.2  |
|            |  SBC 5400         | 8.2  |
|            |  SBC 7000         | 8.2  |
|            |  SBC SWe          | 8.2  |
| [功能区 SBC Edge](https://support.sonus.net/display/UXDOC81/Best+Practice+-+Configuring+Microsoft+Teams+Local+Media+Optimization)  |  SBC SWe Lite | 8.1.5 |
|               | SBC 1000 | 8.1.5  |
|               | SBC 2000 | 8.1.5  |
| [TE-SYSTEMS](https://www.anynode.de/local_media_optimization/) |  anynode          | 4.0.1+ |
| [Oracle](https://www.oracle.com/industries/communications/enterprise-communications/session-border-controller/microsoft.html) | AP 1100 | 8.4.0.0.0 |
|        | AP 3900 | 8.4.0.0.0 |
|        | AP 4600 | 8.4.0.0.0 | 
|        | AP 6300 | 8.4.0.0.0 |
|        | AP 6350 | 8.4.0.0.0 | 
|        | VME     | 8.4.0.0.0 |


## <a name="manage-external-trusted-ip-addresses"></a>管理外部受信任的 IP 地址

外部受信任的 IP 是企业网络的 Internet 外部 IP。 这些 IP 是客户端连接到 Microsoft Teams 使用的 IP Microsoft 365。 你需要为用户使用本地媒体优化的每个站点添加这些外部 IP。

若要添加每个站点的公共 IP 地址，请使用 New-CsTenantTrustedIPAddress cmdlet。 可以定义租户的无限数量的受信任 IP 地址。 如果 ip 地址Microsoft 365 IPv4 和 IPv6 地址，则需要添加这两种类型的 IP 地址。 对于 IPv4，请使用掩码 32。 对于 IPv6，请使用掩码 128。 可以通过在 cmdlet 上指定不同的 MaskBits 来添加单个外部 IP 地址和外部 IP 子网。

```
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description>
```


添加受信任的 IP 地址的示例。

```
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.110 -MaskBits 32 -Description "Vietnam site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.120 -MaskBits 32 -Description "Indonesia site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.130 -MaskBits 32 -Description "Singapore site trusted IP"
```


## <a name="define-the-network-topology"></a>定义网络拓扑

本部分介绍如何为网络拓扑定义网络区域、网络站点和网络子网。

所有参数都区分大小写，因此需确保使用与设置期间使用的大小写相同的大小写。   (例如，GatewaySiteID 值"越南"和"越南"将被视为不同的 sites.) 

### <a name="define-network-regions"></a>定义网络区域

若要定义网络区域，请使用 New-CsTenantNetworkRegion cmdlet。 RegionID 参数是一个逻辑名称，表示区域地理位置，没有依赖关系或限制。 CentralSite `<site ID>` 参数是可选的。

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

以下示例创建名为 APAC 的网络区域：

```
New-CsTenantNetworkRegion -NetworkRegionID "APAC"  
```

###  <a name="define-network-sites"></a>定义网络站点

若要定义网络站点，请使用 New-CsTenantNetworkSite cmdlet。 每个网络站点必须与网络区域相关联。

```
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

以下示例在 APAC 区域创建三个新的网络站点：越南、印度尼西亚和新加坡：

```
New-CsTenantNetworkSite -NetworkSiteID "Vietnam" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Indonesia" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Singapore" -NetworkRegionID "APAC"
```

### <a name="define-network-subnets"></a>定义网络子网

若要定义网络子网并将其关联到网络站点，请使用 New-CsTenantNetworkSubnet cmdlet。 每个网络子网只能与一个站点相关联。 

```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

以下示例定义三个网络子网，并使它们与三个网络站点（越南、印度尼西亚和新加坡）关联：

```
New-CsTenantNetworkSubnet -SubnetID 192.168.1.0 -MaskBits 24 -NetworkSiteID “Vietnam”
New-CsTenantNetworkSubnet -SubnetID 192.168.2.0 -MaskBits 24 -NetworkSiteID “Indonesia”
New-CsTenantNetworkSubnet -SubnetID 192.168.3.0 -MaskBits 24 -NetworkSiteID “Singapore”
```

## <a name="define-the-virtual-network-topology"></a>定义虚拟网络拓扑 

首先，租户管理员使用 New-CsOnlinePSTNGateway cmdlet 为每个相关的 SBC 创建新的 SBC 配置。
租户管理员通过使用 Set-CsOnlinePSTNGateway cmdlet 为 PSTN 网关对象指定网络站点来定义虚拟网络拓扑：

```
PS C:\> Set-CsOnlinePSTNGateway -Identity <Identity> -GatewaySiteID <site ID> -MediaBypass <true/false> -BypassMode <Always/OnlyForLocalUsers> -ProxySBC  <proxy SBC FQDN or $null>
```

请注意以下事项： 
   - 如果客户具有单个 SBC，则 -ProxySBC 参数必须是具有集中式中继方案的 $null 或 SBC FQDN 值 (Central S) BC。
   - -MediaBypass 参数必须设置为 $true 以支持本地媒体优化。
   - 如果 SBC 未设置 -BypassMode 参数，将不会发送 X-MS 标头。 
   - 所有参数都区分大小写，因此需确保使用的大小写与设置期间使用的大小写相同。   (例如，GatewaySiteID 值"越南"和"越南"将视为不同的站点。) 

以下示例使用"始终绕过"模式将三个 SDC 添加到 APAC 区域的网络站点越南、印度尼西亚和新加坡：

```
Set-CSOnlinePSTNGateway -Identity “proxysbc.contoso.com” -GatewaySiteID “Singapore” -MediaBypass $true -BypassMode “Always” -ProxySBC $null

Set-CSOnlinePSTNGateway -Identity “VNsbc.contoso.com” -GatewaySiteID “Vietnam” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”

Set-CSOnlinePSTNGateway -Identity “IDsbc.contoso.com” -GatewaySiteID “Indonesia” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”
```

注意：若要确保同时配置本地媒体优化和 Location-Based 路由 (LBR) 时不间断的操作，必须通过将每个下游 SBC 的 GatewaySiteLbrEnabled 参数设置为 $true 来为 LBR 启用下游 SBC。  (代理 SBC.) 

根据上述信息，直接路由将包括三个专有的 SIP 标头到 SIP 邀请和重新邀请，如下表所示。

如果定义了 BypassMode，则直接路由邀请和Re-Invites引入的 X-MS 标头：

| 标头名称 | 值 | 备注 | 
|:------------|:-------|:-------|
| X-MS-UserLocation | internal/external | 指示用户是内部用户还是外部用户 |
| 请求 URI 邀请 sip：+84439263000@VNsbc.contoso.com SIP /2.0 | SBC FQDN | 针对调用的 FQDN，即使 SBC 未直接连接到直接路由 |
| X-MS-MediaPath | 示例：proxysbc.contoso.com、VNsbc.contoso.com | 应用于用户和目标 SBC 之间的媒体路径的 SBC 顺序。 最终的 SBC 始终为最后 |
| X-MS-UserSite | usersiteID | 租户管理员定义的字符串 |

## <a name="call-flows"></a>调用流 

下面显示了两种模式的调用流：

- [始终绕过](#always-bypass-mode)
- [仅适用于本地用户](#only-for-local-users-mode)

### <a name="always-bypass-mode"></a>始终绕过模式

始终绕过模式是最简单的配置选项。 如果可以从任何站点访问所有 SDC，租户管理员可以为所有用户和 SDC 配置单个站点。

这些示例显示了以下情况的始终绕过模式：

- [出站调用，并且用户与 SBC 位于同一位置](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [入站呼叫和用户位于 SBC 相同的位置](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [出站调用且用户是外部用户](#outbound-calls-and-the-user-is-external-with-always-bypass)
- [入站呼叫和用户是外部用户](#inbound-calls-and-the-user-is-external-with-always-bypass)

下表显示了示例中使用的 FQDN 和 IP 地址：

| FQDN | SBC 外部 IP 地址 | SBC 内部 IP 地址 | 内部子网 | 位置 | 外部 NAT (受信任的 IP)  |
|:------------|:-------|:-------|:-------|:-------|:-------|
| VNsbc.contoso.com | 无 | 192.168.1.5 | 192.168.1.0/24 | 越南 | 172.16.240.110 |
| IDsbc.contoso.com | 无 | 192.168.2.5 | 192.168.2.0/24 | 印度尼西亚 | 172.16.240.120 |
| proxysbc.contoso.com | 172.16.240.133 | 192.168.3.5 | 192.168.3.0/24 | 新加坡 | 172.16.240.130 |



#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a>出站呼叫和用户位于与始终绕过的 SBC 相同的位置

| 模式 |    用户 |  位置 |  呼叫方向 |
|:------------|:-------|:-------| :-------|
| AlwaysBypass |    内部 |  与 SBC 相同的站点 |  出站 |

下表显示了最终用户配置和操作：

| 用户物理位置| 用户拨打或接收对号码的呼叫 | 用户电话号码  | 联机语音路由策略 | 为 SBC 配置的模式 |
|:------------|:-------|:-------|:-------|:-------|
| 越南 | +84 4 3926 3000 | +84 4 5555 5555   | 优先级 1：^ \+ 84 (\d {9}) $ -VNsbc.contoso.com <br> 优先级 2：.* - proxysbc.contoso.com   | VNsbc.contoso.com – 始终绕过 <br> proxysbc.contoso.com – 始终绕过


下图显示了始终绕过模式的出站呼叫的 SIP 阶梯，以及与 SBC 位于同一位置的用户。

![显示出站呼叫的示意图](media/direct-routing-media-op-10.png "出站调用")

下表显示了直接路由发送的 X-MS 标头：

| 参数 | 解释 |
|:------------|:-------|
| 邀请 +8443926300@VNsbc.contoso.com | 在请求 URI 中发送联机语音路由策略中定义的 SBC 的目标 FQDN | 
| X-MS-UserLocation：内部 | 字段指示用户位于企业网络内 |
| X-MS-MediaPath：VNsbc.contoso.com |   指定客户端必须遍历到目标 SBC 的 SBC。 在这种情况下，由于我们始终绕过，并且客户端在内部是作为标头中的唯一名称发送的目标名称。 | 
|X-MS-UserSite：越南 |   在用户所在的站点内指示的字段。 |


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a>入站呼叫和用户位于与始终绕过的 SBC 相同的位置

| 模式 |    用户 |  位置 |  呼叫方向 |
|:------------|:-------|:-------|:-------|:-------|
| AlwaysBypass |    内部 | 与 SBC 相同的站点 | 入站 |


在入站呼叫中，用户的位置未知，SBC 必须猜测用户的位置。 如果猜测不正确，需要重新邀请。 此情况假定用户是内部用户，媒体可以直接流动，在重新邀请用户 (不需要进一步) 。
连接到直接路由服务的 SBC 通过提供"直接路由"和"Record-Route报告原始 SBC 位置。 根据这些字段，媒体路径由直接路由计算。

注意：如果用户可以有多个终结点，则不能支持 183。 在这种情况下，直接路由始终使用 180 响铃。 

下图显示了使用 AlwaysBypass 模式的入站呼叫中的 SIP 阶梯，并且用户与 SBC 位于同一位置。

![显示 SIP 阶梯的示意图。](media/direct-routing-media-op-11.png)


#### <a name="outbound-calls-and-the-user-is-external-with-always-bypass"></a>出站呼叫和用户是外部的始终绕过

| 模式 |    用户 |  站点 |  呼叫方向
|:------------|:-------|:-------|:-------|
AlwaysBypass |  外部 |  不适用 | 出站 |


下图显示了使用 AlwaysBypass 模式的出站呼叫的 SIP 阶梯，用户是外部用户：

![关系图显示 SIP 阶梯。](media/direct-routing-media-op-12.png)

下表显示了直接路由服务发送的 X-MS 标头：

| 参数 |   解释 |
|:------------|:-------|
|邀请 +8443926300@VNsbc.contoso.com | 在请求 URI 中发送联机语音路由策略中定义的 SBC 的目标 FQDN。|
| X-MS-UserLocation：external | 字段指示用户位于企业网络外部。 |
| X-MS-MediaPath：proxysbc.contoso.com、VNsbc.contoso.com    | 指定客户端必须遍历到目标 SBC 的 SBC。 在这种情况下，由于我们始终绕过，并且客户端是外部的。 |

#### <a name="inbound-calls-and-the-user-is-external-with-always-bypass"></a>入站呼叫和用户是外部的始终绕过

| 模式 | 用户 | 站点 |  呼叫方向 |
|:------------|:-------|:-------|:-------|
AlwaysBypass |  外部 |  不适用 |   入站 |

对于入站呼叫，默认情况下，连接到直接路由的 SBC 需要发送重新邀请 (，如果用户的位置在外部，则始终提供本地媒体候选) 。  X-MediaPath 基于指定的 Record-Route SBC 用户计算。

下图显示了具有 AlwaysBypass 模式的入站呼叫的 SIP 阶梯，并且用户是外部用户。

![再次显示 SIP 阶梯的图表。](media/direct-routing-media-op-13.png)


### <a name="only-for-local-users-mode"></a>仅适用于本地用户模式

目标 SBC 的本地媒体候选项仅在用户与 SBC 位于同一位置时提供。 在所有其他情况下，媒体将流经代理 SBC 的内部或外部 IP。

描述了以下方案：

- [出站调用，并且用户与 SBC 位于同一位置](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [入站呼叫和用户位于 SBC 相同的位置](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [用户不与 SBC 位于同一位置，但位于企业网络中](#user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users)
- [入站呼叫和用户是内部用户，但不与 SBC 位于同一位置](#inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users)

下表显示了最终用户配置和操作：

| 用户物理位置 |  用户拨打或接收对号码的呼叫 |  用户电话号码 | 联机语音路由策略 |   为 SBC 配置的模式 |
|:------------|:-------|:-------|:-------|:-------|
| 越南 | +84 4 3926 3000 |  +84 4 5555 5555 | 优先级 1：^ \+ 84 (\d {9}) $ -VNsbc.contoso.com <br> 优先级 2：.* - proxysbc.contoso.com | VNsbc.contoso.com – OnlyForLocalUsers Proxysbc.contoso.com – 始终绕过 |

#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a>出站呼叫和用户位于 SBC 的同一位置，仅针对本地用户

| 模式 | 用户 | 站点 | 呼叫方向 |
|:------------|:-------|:-------|:-------|
| OnlyForLocalUsers |   内部 |与 SBC 相同   | 出站 |

下图显示了具有 OnlyForLocalUsers 模式的出站调用，并且用户与 SBC 位于同一位置。 当用户与 SBC 位于同一位置时，此流显示在出站 [调用中](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)。

![图表再次显示 SIP 阶梯。](media/direct-routing-media-op-14.png)


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a>入站呼叫和用户位于 SBC 的同一位置，仅针对本地用户

| 模式 | 用户 | 站点 | 呼叫方向 |
|:------------|:-------|:-------|:-------|
| OnlyForLocalUsers |   内部 | 与 SBC 相同 | 入站 |

下图显示了具有 OnlyForLocalUsers 模式的入站调用，并且用户与 SBC 位于同一位置。 当用户与 SBC 位于同一位置时，此流与入站调用 [中所示的流相同](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)。

![另一个显示 SIP 阶梯的图表。](media/direct-routing-media-op-15.png)


#### <a name="user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users"></a>用户不与 SBC 位于同一位置，而是位于企业网络中，仅针对本地用户

| 模式 | 用户 | 站点 |呼叫方向 |
|:------------|:-------|:-------|:-------|
| OnlyForLocalUsers  | 内部 |   不同于 SBC | 出站 |

直接路由根据用户在 SBC 上配置的报告位置和模式来计算 X-MediaPath。


下图显示了具有 OnlyForLocalUsers 模式的出站调用，以及与 SBC 不在同一位置的内部用户。

![另一张图显示了 SIP 阶梯。](media/direct-routing-media-op-16.png)


#### <a name="inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users"></a>入站呼叫和用户是内部用户，但不与仅针对本地用户的 SBC 位于同一位置

| 模式 |    用户 |  站点 |  呼叫方向 |
|:------------|:-------|:-------|:-------|
| OnlyForLocalUsers | 内部 |    不同于 SBC |    入站 |

下图显示了具有 OnlyForLocalUsers 模式的入站呼叫，以及与 SBC 不在同一位置的内部用户。

![另一张显示 SIP 阶梯的图表。](media/direct-routing-media-op-17.png)









