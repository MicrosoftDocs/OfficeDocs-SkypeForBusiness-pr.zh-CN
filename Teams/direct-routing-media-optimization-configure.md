---
title: 直接路由本地媒体优化
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
ms.openlocfilehash: 8a69a46d7620628c7afffb706354c0f6e7868f3d
ms.sourcegitcommit: 3dd6499416e9fbdcb48187c6322bd607290502ce
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2020
ms.locfileid: "43541589"
---
# <a name="configure-local-media-optimization-for-direct-routing"></a>为直接路由配置本地媒体优化

本地媒体优化的配置基于由其他云语音功能（如基于位置的路由和动态紧急呼叫）通用的网络设置。 若要了解有关网络区域、网络站点、网络子网和受信任的 IP 地址的详细信息，请参阅[云语音功能的网络设置](cloud-voice-network-settings.md)。

在配置本地媒体优化之前，请参阅[用于直接路由的本地媒体优化](direct-routing-media-optimization.md)。  

若要配置本地媒体优化，需要执行以下步骤。 你可以使用团队管理员中心或 PowerShell。 有关详细信息，请参阅[管理网络拓扑](manage-your-network-topology.md)。

1. 配置用户和 SBC 网站（如本文中所述）。
2. 将 SBCs 配置为本地媒体优化（根据 SBC 供应商的规范）。

下图显示了本文的示例中所用的网络设置。

![显示网络设置示例的图表](media/direct-routing-media-op-9.png "网络设置示例")


## <a name="configure-the-user-and-the-sbc-sites"></a>配置用户和 SBC 网站

要配置用户和 SBC 网站，你需要：

1. [管理外部受信任的 IP 地址](#manage-external-trusted-ip-addresses)。  

2. 通过配置网络区域、网络站点和网络子网来[定义网络拓扑](#define-the-network-topology)。

3. 通过将 SBC （s）分配给具有相关模式和代理 SBC 值的站点来[定义虚拟网络拓扑](#define-the-virtual-network-topology)。


## <a name="configure-sbcs-for-local-media-optimization-according-to-the-sbc-vendor-specification"></a>根据 SBC 供应商的规范，配置用于本地媒体优化的 SBC

本文介绍 Microsoft 组件的配置。 有关 SBC 配置的信息，请参阅 SBC 供应商 documenation。

以下 SBC 供应商支持本地媒体优化：

| 供应商 | 产品 |    软件版本 |
|:------------|:-------|:-------| :-------|
| [Audiocodes](https://www.audiocodes.com/media/13253/connecting-audiocodes-sbc-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf) |    Mediant 500 SBC |   7.20 | 
|            |  Mediant 800 SBC |   7.20 | 
|            |  Mediant 2600 SBC |  7.20 | 
|            |  Mediant 4000 SBC |  7.20 | 
|            |  Mediant 1000B SBC | 7.20 | 
|            |  Mediant 9000 SBC |  7.20 | 
|            |  Mediant 虚拟版 SBC |   7.20 | 
|            |  Mediant 云版 SBC | 7.20 |
| [功能区 SBC 核心](https://support.sonus.net/display/ALLDOC/SBC+8.2+-+Configure+Local+Media+Optimization)  |  SBC 5110         | 8.2  |
|            |  SBC 5210         | 8.2  |
|            |  SBC 5400         | 8.2  |
|            |  SBC 7000         | 8.2  |
|            |  SBC SWe          | 8.2  |
| [功能区 SBC 边缘](https://support.sonus.net/display/UXDOC81/Microsoft+Teams+Direct+Routing+-+On+Premises+Deployment)  |  SBC 1000         | 8.1.1，内部版本527 |
|            |  SBC 2000         | 8.1.1，内部版本527 |
|            |  SBC SWe Lite     | 8.1.0，内部版本222 |
| [TE-SYSTEMS](https://www.anynode.de/local_media_optimization/) |  anynode          | 4.0.1 + |
| [Oracle](https://www.oracle.com/industries/communications/enterprise-communications/session-border-controller/microsoft.html) | AP 1100 | 8.4.0.0.0 |
|        | AP 3900 | 8.4.0.0.0 |
|        | AP 4600 | 8.4.0.0.0 | 
|        | AP 6300 | 8.4.0.0.0 |
|        | AP 6350 | 8.4.0.0.0 | 
|        | VME     | 8.4.0.0.0 |


## <a name="manage-external-trusted-ip-addresses"></a>管理外部受信任的 IP 地址

外部受信任的 Ip 是企业网络的 Internet 外部 Ip。 这些 IP 是 Microsoft 团队客户端连接到 Microsoft 365 时使用的 IP 地址。 你需要为每个具有使用本地媒体优化的用户的网站添加这些外部 Ip。

若要为每个网站添加公共 IP 地址，请使用 CsTenantTrustedIPAddress cmdlet。 你可以为租户定义无限数量的受信任 IP 地址。 如果 Microsoft 365 所看到的外部 IPs 是 IPv4 和 IPv6 地址，则需要添加这两种类型的 IP 地址。 对于 IPv4，请使用掩码32。 对于 IPv6，请使用掩码128。 你可以通过在 cmdlet 上指定不同的 MaskBits 来添加单个外部 IP 地址和外部 IP 子网。

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

本节介绍如何为你的网络拓扑定义网络区域、网络站点和网络子网。

所有参数都区分大小写，因此你需要确保使用在安装过程中使用的相同大小写。  （例如，GatewaySiteID 值 "越南" 和 "越南" 将被视为不同的网站。）

### <a name="define-network-regions"></a>定义网络区域

若要定义网络区域，请使用 CsTenantNetworkRegion cmdlet。 RegionID 参数是一个逻辑名称，表示区域的地理位置，并且不具有依赖关系或限制。 CentralSite <site ID>参数是可选的。

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

下面的示例创建了一个名为 APAC 的网络区域：

```
New-CsTenantNetworkRegion -NetworkRegionID "APAC"  
```

###  <a name="define-network-sites"></a>定义网络站点

若要定义网络网站，请使用 CsTenantNetworkSite cmdlet。 每个网络站点都必须与一个网络区域相关联。

```
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

以下示例在 APAC 区域中创建三个新的网络站点、越南、印度尼西亚和新加坡：

```
New-CsTenantNetworkSite -NetworkSiteID "Vietnam" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Indonesia" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Singapore" -NetworkRegionID "APAC"
```

### <a name="define-network-subnets"></a>定义网络子网

若要定义网络子网并将其与网络站点关联，请使用 CsTenantNetworkSubnet cmdlet。 每个网络子网只能与一个网站相关联。 

```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

以下示例定义了三个网络子网，并将其与三个网络站点（越南、印度尼西亚和新加坡）关联：

```
New-CsTenantNetworkSubnet -SubnetID 192.168.1.0 -MaskBits 24 -NetworkSiteID “Vietnam”
New-CsTenantNetworkSubnet -SubnetID 192.168.2.0 -MaskBits 24 -NetworkSiteID “Indonesia”
New-CsTenantNetworkSubnet -SubnetID 192.168.3.0 -MaskBits 24 -NetworkSiteID “Singapore”
```

## <a name="define-the-virtual-network-topology"></a>定义虚拟网络拓扑 

首先，租户管理员使用 CsOnlinePSTNGateway cmdlet 为每个相关 SBC 创建新的 SBC 配置。
租户管理员通过使用 CsOnlinePSTNGateway cmdlet 指定 PSTN 网关对象的网络站点来定义虚拟网络拓扑：

```
PS C:\> Set-CsOnlinePSTNGateway -Identity <Identity> -GatewaySiteID <site ID> -MediaBypass <true/false> -BypassMode <Always/OnlyForLocalUsers> -ProxySBC  <proxy SBC FQDN or $null>
```

请注意以下事项： 
   - 如果客户有单个 SBC，则-ProxySBC 参数必须是必需的 $null 或 SBC FQDN 值（具有集中中继方案的中心 SBC）。
   - 必须将-MediaBypass 参数设置为 $true，才能支持本地媒体优化。
   - 如果 SBC 没有-BypassMode 参数集，则不会发送 X 毫秒标头。 
   - 所有参数都区分大小写，因此你需要确保使用的是在安装期间使用的相同大小写。  （例如，GatewaySiteID 值 "越南" 和 "越南" 将被视为不同的网站。）

以下示例将3个 SBCs 添加到 APAC 区域中的网络站点越南、印度尼西亚和新加坡，模式始终为 "始终绕过"：

```
Set-CSOnlinePSTNGateway -Identity “proxysbc.contoso.com” -GatewaySiteID “Singapore” -MediaBypass $true -BypassMode “Always” -ProxySBC $null

Set-CSOnlinePSTNGateway -Identity “VNsbc.contoso.com” -GatewaySiteID “Vietnam” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”

Set-CSOnlinePSTNGateway -Identity “IDsbc.contoso.com” -GatewaySiteID “Indonesia” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”
```

注意：若要确保在同时配置本地媒体优化和基于位置的路由（LBR）时不间断的操作，必须通过将 GatewaySiteLbrEnabled 参数设置为每个下游 SBC $true 来为 LBR 启用下游 SBCs。 （对于代理 SBC，此设置不是必需的。）

根据上述信息，直接路由将包括三个专用 SIP 标题到 SIP 邀请和重新邀请，如下表所示。

如果定义了 BypassMode，则在邀请和重新邀请时直接路由中引入了 X-MS 标题：

| 标题名称 | 相对值 | 备注 | 
|:------------|:-------|:-------|
| X 毫秒-UserLocation | 内部/外部 | 指示用户是内部还是外部用户 |
| 请求 URI 邀请 sip： + 84439263000@VNsbc.contoso.com SIP/2。0 | SBC FQDN | 即使 SBC 未直接连接到直接路由，仍针对呼叫的 FQDN |
| X 毫秒-MediaPath | 示例： proxysbc.contoso.com、VNsbc.contoso.com | 应用于用户和目标 SBC 之间的媒体路径的 SBCs 顺序。 最终的 SBC 始终持续 |
| X 毫秒-UserSite | usersiteID | 租户管理员定义的字符串 |

## <a name="call-flows"></a>通话流程 

以下显示了两种模式的通话流：

- [始终绕过](#always-bypass-mode)
- [仅适用于本地用户](#only-for-local-users-mode)

### <a name="always-bypass-mode"></a>始终绕过模式

始终绕过模式是最简单的配置选项。 租户管理员可以为所有用户和 SBCs 配置单个网站（如果所有 SBCs 均可从任何网站访问）。

在以下情况下，示例显示 "始终绕过" 模式：

- [出站呼叫和用户与 SBC 位于同一位置](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [入站呼叫和用户与 SBC 位于同一位置](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [出站呼叫和用户是外部的](#outbound-calls-and-the-user-is-external-with-always-bypass)
- [入站呼叫和用户是外部的](#inbound-calls-and-the-user-is-external-with-always-bypass)

下表显示了示例中使用的 FQDN 和 IP 地址：

| FQDN | SBC 外部 IP 地址 | SBC 内部 IP 地址 | 内部子网 | 位置 | 外部 NAT （受信任的 IP） |
|:------------|:-------|:-------|:-------|:-------|:-------|
| VNsbc.contoso.com | 无 | 192.168.1.5 | 192.168.1.0/24 | 越南 | 172.16.240.110 |
| IDsbc.contoso.com | 无 | 192.168.2.5 | 192.168.2.0/24 | 印度尼西亚 | 172.16.240.120 |
| proxysbc.contoso.com | 172.16.240.133 | 192.168.3.5 | 192.168.3.0/24 | 新加坡 | 172.16.240.130 |



#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a>出站呼叫，并且用户与具有始终绕过的 SBC 位于同一位置

| 众 |    用户 |  位置 |  呼叫方向 |
|:------------|:-------|:-------| :-------|
| AlwaysBypass |    内部 |  与 SBC 相同的网站 |  出站 |

下表显示了最终用户配置和操作：

| 用户物理位置| 用户拨打或接听号码 | 用户电话号码  | 联机语音路由策略 | 针对 SBC 配置的模式 |
|:------------|:-------|:-------|:-------|:-------|
| 越南 | + 84 4 3926 3000 | + 84 4 5555 5555   | 优先级1： ^\+84 （\d{9}） $-VNsbc.contoso.com <br> 优先级2：. *-proxysbc.contoso.com   | VNsbc.contoso.com-始终绕过 <br> proxysbc.contoso.com-始终绕过


下图显示了具有 "始终绕过" 模式的出站呼叫和用户位于 SBC 所在位置的 SIP 阶梯。

![显示出站通话的图表](media/direct-routing-media-op-10.png "拨出电话")

下表显示了直接路由发送的 X-MS 标题：

| 参数 | 解释 |
|:------------|:-------|
| 邀请 + 8443926300@VNsbc.contoso.com | 在联机语音路由策略中定义的 SBC 的目标名称在请求 URI 中发送 | 
| X-MS-UserLocation：内部 | 指示用户位于企业网络内的字段 |
| X-MS-MediaPath： VNsbc.contoso.com |   指定客户端必须遍历到目标 SBC 的 SBC。 在这种情况下，我们始终绕过，并且客户端是以标题中的唯一名称形式发送的目标名称。 | 
|X-MS-UserSite：越南 |   用户所在网站内指示的字段。 |


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a>入站呼叫和用户与具有始终绕过的 SBC 位于同一位置

| 众 |    用户 |  位置 |  呼叫方向 |
|:------------|:-------|:-------|:-------|:-------|
| AlwaysBypass |    内部 | 与 SBC 相同的网站 | 封 |


在入站呼叫中，用户的位置是未知的，并且 SBC 必须猜测用户所在的位置。 如果猜测不正确，则需要重新邀请。 这种情况假设用户是内部用户，媒体可以直接流向，不需要执行其他操作（重新邀请）。
连接到直接路由服务的 SBC 通过提供记录-路由和联系人字段来报告发起的 SBC 位置。 根据这些字段，媒体路径由直接路由计算。

注意：假设用户可以有多个终结点，则不可能支持183。 在这种情况下，直接路由将始终使用180铃声。 

下图显示了具有 AlwaysBypass 模式的入站调用中的 SIP 阶梯，并且用户与 SBC 位于同一位置。

![显示 SIP 阶梯的图表](media/direct-routing-media-op-11.png)


#### <a name="outbound-calls-and-the-user-is-external-with-always-bypass"></a>出站呼叫和用户是具有始终绕过的外部呼叫

| 众 |    用户 |  站点 |  呼叫方向
|:------------|:-------|:-------|:-------|
AlwaysBypass |  外部 |  不适用 | 出站 |


下图显示了具有 AlwaysBypass 模式的出站呼叫的 SIP 阶梯，并且用户是外部的：

![显示 SIP 阶梯的图表](media/direct-routing-media-op-12.png)

下表显示了直接路由服务发送的 X-MS 标头：

| 参数 |   解释 |
|:------------|:-------|
|邀请 + 8443926300@VNsbc.contoso.com | 在联机语音路由策略中定义的 SBC 的目标名称在请求 URI 中发送。|
| X-UserLocation：外部 | 指示用户位于企业网络外部的字段。 |
| X-MS-MediaPath： proxysbc.contoso.com，VNsbc.contoso.com    | 指定客户端必须遍历到目标 SBC 的 SBC。 在此情况下，我们始终绕过，并且客户端是外部客户端。 |

#### <a name="inbound-calls-and-the-user-is-external-with-always-bypass"></a>入站呼叫和用户是具有始终绕过的外部呼叫

| 众 | 用户 | 站点 |  呼叫方向 |
|:------------|:-------|:-------|:-------|
AlwaysBypass |  外部 |  不适用 |   封 |

对于入站呼叫，连接到直接路由的 SBC 需要发送重新邀请（默认情况下，始终提供本地媒体候选人）（如果用户是外部的位置）。  X-MediaPath 是基于记录路由和指定的 SBC 用户计算的。

下图显示了具有 AlwaysBypass 模式的入站呼叫的 SIP 阶梯，并且该用户是外部用户。

![显示 SIP 阶梯的图表](media/direct-routing-media-op-13.png)


### <a name="only-for-local-users-mode"></a>仅适用于本地用户模式

仅当用户与 SBC 位于同一位置时，才会提供目标 SBC 的本地媒体候选项。 在所有其他情况下，媒体将通过代理 SBC 的内部或外部 IP 进行通信。

介绍以下方案：

- [出站呼叫和用户与 SBC 位于同一位置](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [入站呼叫和用户与 SBC 位于同一位置](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [用户与 SBC 不在同一位置，但位于企业网络中](#user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users)
- [入站呼叫和用户是内部的，但与 SBC 不在同一位置](#inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users)

下表显示最终用户配置和操作：

| 用户物理位置 |  用户拨打或接听号码 |  用户电话号码 | 联机语音路由策略 |   针对 SBC 配置的模式 |
|:------------|:-------|:-------|:-------|:-------|
| 越南 | + 84 4 3926 3000 |  + 84 4 5555 5555 | 优先级1： ^\+84 （\d{9}） $-VNsbc.contoso.com <br> 优先级2：. *-proxysbc.contoso.com | VNsbc.contoso.com-OnlyForLocalUsers Proxysbc.contoso.com-始终绕过 |

#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a>出站呼叫和用户与 SBC 在同一位置，仅适用于本地用户

| 众 | 用户 | 站点 | 呼叫方向 |
|:------------|:-------|:-------|:-------|
| OnlyForLocalUsers |   内部 |与 SBC 相同   | 出站 |

下图显示了具有 OnlyForLocalUsers 模式的出站调用，并且用户与 SBC 位于同一位置。 这是[当用户与 SBC 位于同一位置时，在出站呼叫](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)中显示的相同流。

![显示 SIP 阶梯的图表](media/direct-routing-media-op-14.png)


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a>入站呼叫和用户与 SBC 在同一位置，仅适用于本地用户

| 众 | 用户 | 站点 | 呼叫方向 |
|:------------|:-------|:-------|:-------|
| OnlyForLocalUsers |   内部 | 与 SBC 相同 | 封 |

下图显示了具有 OnlyForLocalUsers 模式的入站调用，并且用户与 SBC 位于同一位置。 [当用户与 SBC 位于同一位置时](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)，这是与入站通话中所示相同的流。

![显示 SIP 阶梯的图表](media/direct-routing-media-op-15.png)


#### <a name="user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users"></a>用户与 SBC 不在同一位置，但位于企业网络中，仅适用于本地用户

| 众 | 用户 | 站点 |呼叫方向 |
|:------------|:-------|:-------|:-------|
| OnlyForLocalUsers  | 内部 |   与 SBC 不同 | 出站 |

直接路由基于在 SBC 上配置的用户和模式的已报告位置计算 X MediaPath。


下图显示了具有 OnlyForLocalUsers 模式的出站呼叫，以及与 SBC 不在同一位置的内部用户。

![显示 SIP 阶梯的图表](media/direct-routing-media-op-16.png)


#### <a name="inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users"></a>入站呼叫和用户是内部的，但与 SBC 不在同一位置，仅适用于本地用户

| 众 |    用户 |  站点 |  呼叫方向 |
|:------------|:-------|:-------|:-------|
| OnlyForLocalUsers | 内部 |    与 SBC 不同 |    封 |

下图显示了具有 OnlyForLocalUsers 模式的入站呼叫，以及与 SBC 不在同一位置的内部用户。

![显示 SIP 阶梯的图表](media/direct-routing-media-op-17.png)









