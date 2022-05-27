---
title: 为直接路由配置本地媒体优化
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
ms.openlocfilehash: 58cf5f560a22a58cb76ea28389d0dce1e3b3f4fb
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/25/2022
ms.locfileid: "65674874"
---
# <a name="configure-local-media-optimization-for-direct-routing"></a>为直接路由配置本地媒体优化

本地媒体优化的配置基于其他云语音功能（例如Location-Based路由和动态紧急呼叫）通用的网络设置。 若要详细了解网络区域、网络站点、网络子网和受信任的 IP 地址，请参阅 [云语音功能的网络设置](cloud-voice-network-settings.md)。

在配置本地媒体优化之前，请参阅 [本地媒体优化以进行直接路由](direct-routing-media-optimization.md)。

若要配置本地媒体优化，需要执行以下步骤。 可以使用Teams 管理员中心或 PowerShell。 有关详细信息，请参阅 [“管理网络拓扑](manage-your-network-topology.md)”。

1. 如本文) 中所述，配置用户和 SBC 站点 (。
2. 根据 SBC 供应商规范) 配置用于本地媒体优化的 SBC (。

下图显示了在本文的示例中使用的网络设置。

> [!div class="mx-imgBorder"]
> ![显示示例的网络设置的示意图。](media/direct-routing-media-op-9.png "示例的网络设置")

## <a name="configure-the-user-and-the-sbc-sites"></a>配置用户和 SBC 站点

若要配置用户和 SBC 站点，需要：

1. [管理外部受信任的 IP 地址](#manage-external-trusted-ip-addresses)。

2. 通过配置网络区域、网络站点和网络子网来[定义网络拓](#define-the-network-topology)扑。

3. 通过将 SBC (的) 分配到具有相关模式和代理 SBC 值的站点 () 来[定义虚拟网络拓扑](#define-the-virtual-network-topology)。

> [!NOTE]
> 本地媒体优化依赖于客户端位置（相对于公司网络）检测为外部或内部位置，并可访问直接路由 (DR) 会话边界控制器 (SBC) 内部接口。
> 在拆分隧道 VPN 方案中，当客户端终结点检测为客户网络外部时，Microsoft 会向 SBC 发出外部位置的信号，即使客户端可以访问客户的直接路由 SBC 的内部接口。 使用本地媒体优化的直接路由客户可能会经历长时间的呼叫设置时间，在某些情况下，从 PSTN 接听呼叫时没有音频。
> 为了避免这种情况，VPN 管理员必须阻止远程 VPN 用户与直接路由 SBC 内部接口之间的访问。

## <a name="configure-sbcs-for-local-media-optimization-according-to-the-sbc-vendor-specification"></a>根据 SBC 供应商规范配置 SBC (的本地媒体优化) 

本文介绍 Microsoft 组件的配置。 有关 SBC 配置的信息，请参阅 SBC 供应商文档。 有关哪些 SBC 供应商支持本地媒体优化的信息，请 [参阅经过直接路由认证的会话边界控制器](direct-routing-border-controllers.md)。

## <a name="manage-external-trusted-ip-addresses"></a>管理外部受信任的 IP 地址

外部受信任 IP 是企业网络的 Internet 外部 IP。 这些 IP 是Microsoft Teams客户端连接到Microsoft 365时使用的 IP 地址。 需要为使用本地媒体优化的用户所在的每个站点添加这些外部 IP。

若要为每个站点添加公共 IP 地址，请使用New-CsTenantTrustedIPAddress cmdlet。 可以为租户定义无限数量的受信任 IP 地址。 如果Microsoft 365看到的外部 IP 是 IPv4 和 IPv6 地址，则需要添加这两种类型的 IP 地址。 对于 IPv4，请使用掩码 32。 对于 IPv6，请使用掩码 128。 可以通过在 cmdlet 上指定不同的 MaskBits 来添加单个外部 IP 地址和外部 IP 子网。

```powershell
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description>
```

添加受信任 IP 地址的示例。

```powershell
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.110 -MaskBits 32 -Description "Vietnam site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.120 -MaskBits 32 -Description "Indonesia site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.130 -MaskBits 32 -Description "Singapore site trusted IP"
```

## <a name="define-the-network-topology"></a>定义网络拓扑

本部分介绍如何为网络拓扑定义网络区域、网络站点和网络子网。

所有参数都区分大小写，因此需要确保使用安装过程中使用的相同情况。   (例如，GatewaySiteID 值“越南”和“vietnam”将被视为不同的站点。) 

### <a name="define-network-regions"></a>定义网络区域

若要定义网络区域，请使用New-CsTenantNetworkRegion cmdlet。 RegionID 参数是一个逻辑名称，表示区域的地理位置，没有依赖项或限制。 CentralSite `<site ID>` 参数是可选的。

```powershell
New-CsTenantNetworkRegion -NetworkRegionID <region ID>
```

以下示例创建名为 APAC 的网络区域：

```powershell
New-CsTenantNetworkRegion -NetworkRegionID "APAC"
```

### <a name="define-network-sites"></a>定义网络站点

若要定义网络站点，请使用New-CsTenantNetworkSite cmdlet。 每个网络站点必须与网络区域相关联。

```powershell
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

以下示例在 APAC 区域创建三个新的网络站点，越南、印度尼西亚和新加坡：

```powershell
New-CsTenantNetworkSite -NetworkSiteID "Vietnam" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Indonesia" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Singapore" -NetworkRegionID "APAC"
```

### <a name="define-network-subnets"></a>定义网络子网

若要定义网络子网并将其关联到网络站点，请使用New-CsTenantNetworkSubnet cmdlet。 每个网络子网只能与一个站点关联。

```powershell
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

以下示例定义三个网络子网，并将它们与三个网络站点相关联：越南、印度尼西亚和新加坡：

```powershell
New-CsTenantNetworkSubnet -SubnetID 192.168.1.0 -MaskBits 24 -NetworkSiteID "Vietnam"
New-CsTenantNetworkSubnet -SubnetID 192.168.2.0 -MaskBits 24 -NetworkSiteID "Indonesia"
New-CsTenantNetworkSubnet -SubnetID 192.168.3.0 -MaskBits 24 -NetworkSiteID "Singapore"
```

## <a name="define-the-virtual-network-topology"></a>定义虚拟网络拓扑

首先，租户管理员使用New-CsOnlinePSTNGateway cmdlet 为每个相关的 SBC 创建新的 SBC 配置。
租户管理员通过使用Set-CsOnlinePSTNGateway cmdlet 为 PSTN 网关对象指定网络站点来定义虚拟网络拓扑：

```powershell
PS C:\> Set-CsOnlinePSTNGateway -Identity <Identity> -GatewaySiteID <site ID> -MediaBypass <true/false> -BypassMode <Always/OnlyForLocalUsers> -ProxySBC  <proxy SBC FQDN or $null>
```

请注意以下事项：

- 如果客户具有单个 SBC，则 -ProxySBC 参数必须是中心 SBC 的必需$null或 SBC FQDN 值 (集中中继方案) 。
- 必须将 -MediaBypass 参数设置为$true才能支持本地媒体优化。
- 如果 SBC 未设置 -BypassMode 参数，则不会发送 X-MS 标头。
- 所有参数都区分大小写，因此需要确保使用安装过程中使用的相同情况。   (例如，GatewaySiteID 值“越南”和“vietnam”将被视为不同的站点。) 

以下示例将三个 SBC 添加到 APAC 区域中采用“始终绕过”模式的网络站点越南、印度尼西亚和新加坡：

```powershell
Set-CSOnlinePSTNGateway -Identity "proxysbc.contoso.com" -GatewaySiteID "Singapore" -MediaBypass $true -BypassMode "Always" -ProxySBC $null

Set-CSOnlinePSTNGateway -Identity "VNsbc.contoso.com" -GatewaySiteID "Vietnam" -MediaBypass $true -BypassMode "Always" -ProxySBC "proxysbc.contoso.com"

Set-CSOnlinePSTNGateway -Identity "IDsbc.contoso.com" -GatewaySiteID "Indonesia" -MediaBypass $true -BypassMode "Always" -ProxySBC "proxysbc.contoso.com"
```

> [!NOTE]
> 为了确保在同时配置了本地媒体优化和Location-Based路由 (LBR) 时不间断的操作，必须为 LBR 启用下游 SBC，将 GatewaySiteLbrEnabled 参数设置为每个下游 SBC 的$true。  (对于代理 SBC.) ，此设置不是必需的

根据上述信息，直接路由将包括三个专有 SIP 标头到 SIP 邀请和重新邀请，如下表所示。

在邀请上直接路由中引入的 X-MS 标头，如果定义了 BypassMode，则Re-Invites：

|标头名称|值|备注|
|---|---|---|
|X-MS-UserLocation|internal/external|指示用户是内部用户还是外部用户|
|Request-URI INVITE sip： +84439263000@VNsbc.contoso.com SIP /2.0|SBC FQDN|针对调用的 FQDN，即使 SBC 未直接连接到直接路由|
|X-MS-MediaPath|示例：proxysbc.contoso.com、VNsbc.contoso.com|应用于用户与目标 SBC 之间的媒体路径的 SBC 顺序。 最终的 SBC 始终是最后一个|
|X-MS-UserSite|usersiteID|由租户管理员定义的字符串|

## <a name="call-flows"></a>呼叫流

下面显示了两种模式的调用流：

- [始终绕过](#always-bypass-mode)
- [仅适用于本地用户](#only-for-local-users-mode)

### <a name="always-bypass-mode"></a>始终绕过模式

始终绕过模式是最简单的配置选项。 如果所有 SBC 都可从任何站点访问，则租户管理员可以为所有用户和 SBC 配置单个站点。

这些示例演示以下方案的 Always bypass 模式：

- [出站调用和用户与 SBC 位于同一位置](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [入站调用和用户与 SBC 位于同一位置](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [出站呼叫和用户是外部的](#outbound-calls-and-the-user-is-external-with-always-bypass)
- [入站呼叫和用户是外部的](#inbound-calls-and-the-user-is-external-with-always-bypass)

下表显示了示例中使用的 FQDN 和 IP 地址：

|FQDN|SBC 外部 IP 地址|SBC 内部 IP 地址|内部子网|位置|外部 NAT (受信任的 IP) |
|---|---|---|---|---|---|
|VNsbc.contoso.com|无|192.168.1.5|192.168.1.0/24|越南|172.16.240.110|
|IDsbc.contoso.com|无|192.168.2.5|192.168.2.0/24|印度尼西亚|172.16.240.120|
|proxysbc.contoso.com|172.16.240.133|192.168.3.5|192.168.3.0/24|新加坡|172.16.240.130|

#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a>出站调用和用户与具有 Always Bypass 的 SBC 位于同一位置

|模式|用户|位置|呼叫方向|
|---|---|---|---|
|AlwaysBypass|内部|与 SBC 相同的站点|出站|

下表显示了最终用户配置和操作：

|用户物理位置|用户发出或接收对/从号码发出的呼叫|用户电话号码|联机语音路由策略|为 SBC 配置的模式|
|---|---|---|---|---|
|越南|+84 4 3926 3000|+84 4 5555 5555|优先级 1：^\+84 (\d{9}) $ -VNsbc.contoso.com <br> 优先级 2：.* - proxysbc.contoso.com|VNsbc.contoso.com – 始终绕过 <br> proxysbc.contoso.com – 始终绕过|

下图显示了具有 Always 旁路模式的出站调用的 SIP 阶梯，以及与 SBC 位于同一位置的用户。

> [!div class="mx-imgBorder"]
> ![显示出站调用的示意图。](media/direct-routing-media-op-10.png "出站调用")

下表显示了直接路由发送的 X-MS 标头：

|参数|解释|
|---|---|
|邀请 +8443926300@VNsbc.contoso.com|联机语音路由策略中定义的 SBC 的目标 FQDN 在请求 URI 中发送|
|X-MS-UserLocation：内部|该字段指示用户位于公司网络内|
|X-MS-MediaPath：VNsbc.contoso.com|指定客户端必须遍历到目标 SBC 的 SBC。 在这种情况下，由于我们有 Always Bypass，并且客户端是作为标头中的唯一名称发送的目标名称的内部。|
|X-MS-UserSite：越南|在用户所在的网站中指示的字段。|

#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a>入站呼叫和用户与具有 Always Bypass 的 SBC 位于同一位置

|模式|用户|位置|呼叫方向|
|---|---|---|---|---|
|AlwaysBypass|内部|与 SBC 相同的站点|入境|

在入站呼叫中，用户的位置未知，SBC 必须猜测用户的位置。 如果猜测不正确，则需要重新邀请。 这种情况假定用户是内部用户，媒体可以直接流动， (重新邀请) 不需要进一步的操作。
连接到直接路由服务的 SBC 通过提供Record-Route和联系人字段来报告源 SBC 位置。 基于这些字段，媒体路径由直接路由计算。

注意：鉴于用户可以具有多个终结点，则无法支持 183。 在这种情况下，直接路由将始终使用 180 响铃。

下图显示了使用 AlwaysBypass 模式进行入站调用的 SIP 阶梯，并且用户与 SBC 位于同一位置。

> [!div class="mx-imgBorder"]
> ![显示 SIP 阶梯的图示。](media/direct-routing-media-op-11.png)

#### <a name="outbound-calls-and-the-user-is-external-with-always-bypass"></a>出站呼叫和用户是外部的 Always Bypass

|模式|用户|站点|呼叫方向
|---|---|---|---|
|AlwaysBypass|外部|不适用|出站|

下图显示了具有 AlwaysBypass 模式的出站调用的 SIP 阶梯，并且用户是外部的：

> [!div class="mx-imgBorder"]
> ![图中显示了 SIP 阶梯。](media/direct-routing-media-op-12.png)

下表显示了直接路由服务发送的 X-MS 标头：

|参数|解释|
|---|---|
|邀请 +8443926300@VNsbc.contoso.com|在联机语音路由策略中定义的 SBC 的目标 FQDN 在请求 URI 中发送。|
|X-MS-UserLocation：外部|该字段指示用户位于公司网络外部。|
|X-MS-MediaPath：proxysbc.contoso.com、VNsbc.contoso.com|指定客户端必须遍历到目标 SBC 的 SBC。 在这种情况下，因为我们有 Always Bypass，并且客户端是外部客户端。|

#### <a name="inbound-calls-and-the-user-is-external-with-always-bypass"></a>入站调用和用户是外部的 Always Bypass

|模式|用户|站点|呼叫方向|
|---|---|---|---|
|AlwaysBypass|外部|不适用|入境|

对于入站呼叫，连接到直接路由的 SBC 需要默认发送重新邀请 (，如果用户的位置是外部的，则始终) 提供本地媒体候选项。  X-MediaPath 是根据Record-Route和指定的 SBC 用户计算的。

下图显示了具有 AlwaysBypass 模式的入站调用的 SIP 阶梯，并且用户是外部的。

> [!div class="mx-imgBorder"]
> ![再次显示 SIP 阶梯的图示。](media/direct-routing-media-op-13.png)

### <a name="only-for-local-users-mode"></a>仅适用于本地用户模式

仅当用户与 SBC 位于同一位置时，才会提供目标 SBC 的当地媒体候选项。 在所有其他情况下，媒体将流经代理 SBC 的内部或外部 IP。

下面介绍了以下方案：

- [出站调用和用户与 SBC 位于同一位置](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [入站调用和用户与 SBC 位于同一位置](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [用户与 SBC 不在同一位置，但位于公司网络中](#user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users)
- [入站调用和用户是内部的，但与 SBC 的位置不同](#inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users)

下表显示了最终用户配置和操作：

|用户物理位置|用户发出或接收对/从号码发出的呼叫|用户电话号码|联机语音路由策略|为 SBC 配置的模式|
|---|---|---|---|---|
|越南|+84 4 3926  3000|+84 4 5555 5555|优先级 1：^\+84 (\d{9}) $ -VNsbc.contoso.com <br> 优先级 2：.* - proxysbc.contoso.com|VNsbc.contoso.com – OnlyForLocalUsers Proxysbc.contoso.com – 始终绕过|

#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a>出站呼叫和用户与仅适用于本地用户的 SBC 位于同一位置

|模式|用户|站点|呼叫方向|
|---|---|---|---|
|OnlyForLocalUsers|内部|与 SBC 相同|出站|

下图显示了使用 OnlyForLocalUsers 模式的出站调用，并且用户与 SBC 位于同一位置。 当 [用户与 SBC 位于同一位置时，这是出站调用中显示的相同](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)流。

> [!div class="mx-imgBorder"]
> ![关系图再次显示 SIP 阶梯。](media/direct-routing-media-op-14.png)

#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a>入站呼叫和用户与仅适用于本地用户的 SBC 位于同一位置

|模式|用户|站点|呼叫方向|
|---|---|---|---|
|OnlyForLocalUsers|内部|与 SBC 相同|入境|

下图显示了使用 OnlyForLocalUsers 模式的入站调用，并且用户与 SBC 位于同一位置。 当 [用户与 SBC 位于同一位置时，这与入站调用](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)中所示的流相同。

> [!div class="mx-imgBorder"]
> ![另一个显示 SIP 阶梯的图示。](media/direct-routing-media-op-15.png)

#### <a name="user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users"></a>用户与 SBC 不在同一位置，但位于仅适用于本地用户的公司网络中

|模式|用户|站点|呼叫方向|
|---|---|---|---|
|OnlyForLocalUsers|内部|不同于 SBC|出站|

直接路由基于在 SBC 上配置的用户和模式的报告位置计算 X-MediaPath。

下图显示了使用 OnlyForLocalUsers 模式的出站调用，以及与 SBC 不位于同一位置的内部用户。

> [!div class="mx-imgBorder"]
> ![另一张图显示了 SIP 阶梯。](media/direct-routing-media-op-16.png)

#### <a name="inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users"></a>入站呼叫和用户是内部的，但与仅适用于本地用户的 SBC 位置不同

|模式|用户|站点|呼叫方向|
|---|---|---|---|
|OnlyForLocalUsers|内部|不同于 SBC|入境|

下图显示了使用 OnlyForLocalUsers 模式的入站调用，以及与 SBC 不位于同一位置的内部用户。

> [!div class="mx-imgBorder"]
> ![另一个显示 SIP 阶梯的图表。](media/direct-routing-media-op-17.png)
