---
title: 规划直接路由
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: conceptual
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.custom: seo-marvel-mar2020
description: 了解如何Microsoft 电话系统直接路由将受支持的客户提供的会话边界控制器与 SBC (连接到) Microsoft 电话系统。
ms.openlocfilehash: 531b1f22a6a59a9ef72bf97be92ab15596736b80
ms.sourcegitcommit: 592e5a0638c7739dfaa3565b67d4edc621eebc9f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/26/2021
ms.locfileid: "52656065"
---
# <a name="plan-direct-routing"></a>规划直接路由

> [!Tip]
> 观看以下会话，了解直接路由的好处、如何规划它以及如何部署[它：直接](https://aka.ms/teams-direct-routing)路由Microsoft Teams

Microsoft 电话使用系统直接路由，可将支持的、客户提供的会话边界控制器 (SBC) 连接到Microsoft 电话系统。  例如，使用此功能，可以配置本地公用电话交换网 (PSTN) 与 Microsoft Teams 客户端的连接，如下图所示： 

![显示本地 PSTN 连接配置的示意图](media/PlanDirectRouting1-PSTNwithTeams.png "使用客户端配置本地 PSTN Microsoft Teams连接")

  > [!NOTE]
  > Skype for Business联机还可以配对客户提供的 SBC，但这需要在 SBC 和 Microsoft 云之间部署本地 Skype for Business Server 或特殊版本的 Skype for Business（称为 Cloud Connector）。 此方案称为混合语音。 相比之下，直接路由允许在支持的 SBC 和 Microsoft 云之间直接连接。

> [!Important]
> Cloud Connector Edition 将于 2021 年 7 月 31 日与 Skype for Business Online 一起停用。 组织升级到 Teams 后，了解如何使用直接路由 将本地电话网络Teams[连接到本地电话网络](direct-routing-landing-page.md)。 

使用直接路由，可以将 SBC 连接到几乎任何电话中继或和第三方 PSTN 设备进行互连。 使用直接路由可以： 

- 将几乎任何 PSTN 中继与 Microsoft 电话系统一起使用。 
- 配置客户拥有的电话设备（例如 PBX (、模拟设备和 Microsoft 电话 系统) 互操作性。

Microsoft 还提供云中所有语音解决方案，例如呼叫计划。 但是，如果： 

- Microsoft 呼叫计划在你的国家/地区不可用。 
- 组织需要连接到第三方模拟设备、呼叫中心等。 
- 你的组织与 PSTN 运营商有一份现有合同。

直接路由还支持拥有 Microsoft 呼叫计划附加许可证的用户。 有关详细信息，请参阅"电话系统[套餐"。](calling-plan-landing-page.md) 

使用直接路由时，当用户参与计划的会议时，拨入号码由需要适当许可的 Microsoft 音频会议服务提供。  拨出时，Microsoft 音频会议服务使用在线呼叫功能进行呼叫，这需要适当的许可。  (注意如果用户没有 Microsoft 音频会议许可证，呼叫会通过直接路由路由。) 有关详细信息，请参阅使用 Teams[联机会议](https://products.office.com/microsoft-teams/online-meeting-solutions)。 
 
规划直接路由的部署是成功实现的关键。 本文介绍基础结构和许可要求，并提供有关 SBC 连接的信息： 

- [基础结构要求](#infrastructure-requirements)
- [许可和其他要求](#licensing-and-other-requirements)
- [SBC 域名](#sbc-domain-names)
- [SBC 的公共受信任证书](#public-trusted-certificate-for-the-sbc)
- [SIP 信号：FQDN](#sip-signaling-fqdns)
- [SIP 信号：端口](#sip-signaling-ports)
- [媒体流量：端口范围](#media-traffic-port-ranges)
- [支持的会话边界控制器 (SDC) ](#supported-session-border-controllers-sbcs)

有关配置直接路由的详细信息，请参阅 [配置直接路由](direct-routing-configure.md)。

## <a name="infrastructure-requirements"></a>基础结构要求
下表列出了支持部署直接路由的 SDC、域和其他网络连接要求的基础结构要求：  

|基础结构要求|需要以下各项|
|:--- |:--- |
|会话边界控制器 (SBC) |支持的 SBC。 有关详细信息，请参阅支持的[SDC。](#supported-session-border-controllers-sbcs)|
|连接到 SBC 的电话中继|连接到 SBC 的一个或多个电话中继。 在一端，SBC 通过直接路由Microsoft 电话系统。 SBC 还可以连接到第三方电话实体，例如 PBX、模拟电话适配器等。 连接到 SBC 的任何 PSTN 连接选项都将正常工作。  (有关将 PSTN 中继配置到 SBC 的信息，请参阅 SBC 供应商或中继提供商) |
|Microsoft 365或Office 365组织|用于Microsoft 365或Office 365用户，以及配置Microsoft Teams SBC 的连接的组织。|
|用户注册机构|用户必须归到 Microsoft 365 或 Office 365。<br/>如果您的公司具有与 Microsoft 365 或 Office 365 的混合连接Skype for Business本地 Teams 或 Lync 环境，则您无法为本地用户启用 Teams 语音。<br/><br/>若要检查用户的注册机构，请使用以下 Skype for Business Online PowerShell cmdlet：<br/><code>Get-CsOnlineUser -Identity \<user> \| fl HostingProvider</code> <br/><br/>cmdlet 的输出应显示：<br/><code>HostingProvider : sipfed.online.lync.com</code>|
|域|添加到组织或组织的一个或多个Microsoft 365 Office 365域。<br/><br/>请注意，不能使用为租户自动 onmicrosoft.com \* 的默认域 .onmicrosoft.com。<br/><br/>若要查看域，可以使用以下 Skype for Business Online PowerShell cmdlet：<br/><code>Get-CsTenant \| fl Domains</code><br/><br/>有关域和域或Microsoft 365组织Office 365，请参阅[域常见问题](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a)解答。|
|SBC 的公共 IP 地址|可用于连接到 SBC 的公共 IP 地址。 根据 SBC 的类型，SBC 可以使用 NAT。|
|SBC 的 FQDN (完全) 域名|SBC 的 FQDN，其中 FQDN 的域部分是组织或组织Microsoft 365 Office 365域之一。 有关详细信息，请参阅 [SBC 域名](#sbc-domain-names)。|
|SBC 的公共 DNS 条目 |将 SBC FQDN 映射到公共 IP 地址的公共 DNS 条目。 |
|SBC 的公共受信任证书 |SBC 的证书，用于与直接路由的所有通信。 有关详细信息，请参阅 [SBC 的公共受信任证书](#public-trusted-certificate-for-the-sbc)。|
|直接路由的连接点 |直接路由的连接点为以下三个 FQDN：<br/><br/>`sip.pstnhub.microsoft.com` – 必须先尝试全局 FQDN。<br/>`sip2.pstnhub.microsoft.com` – 辅助 FQDN，在地理上映射到第二个优先级区域。<br/>`sip3.pstnhub.microsoft.com` – 第三级 FQDN，地理上映射到第三个优先区域。<br/><br/>有关配置要求的信息，请参阅[SIP Signaling： FQDN。](#sip-signaling-fqdns)|
|直接路由媒体的防火墙 IP 地址和端口 |SBC 与云中的以下服务通信：<br/><br/>SIP 代理，用于处理信号<br/>媒体处理器，用于处理媒体 -媒体旁路打开时除外<br/><br/>这两个服务在 Microsoft 云中具有单独的 IP 地址，本文档稍后将介绍。<br/><br/>有关详细信息，请参阅 URL [Microsoft Teams](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) [IP 地址范围 中的部分](/office365/enterprise/urls-and-ip-address-ranges)。 |
|媒体传输配置文件|TCP/RTP/SAVP <br/>UDP/RTP/SAVP|
媒体的防火墙 IP 地址Microsoft Teams端口 |有关详细信息，请参阅 [URL 和 IP 地址范围](/office365/enterprise/urls-and-ip-address-ranges)。 |
|||

## <a name="licensing-and-other-requirements"></a>许可和其他要求 

直接路由的用户必须在用户或用户Microsoft 365分配Office 365： 

- Microsoft 电话系统。 
- Microsoft Teams + Skype for Business计划 2（如果包含在许可中）。
- 有关何时 (许可证的特定示例，请阅读以下备注和) 。

> [!NOTE]
> Skype for Business不应从包含该计划的任何许可协议中删除计划。 
> 
> [!IMPORTANT]
> GCC高和 DoD 用户应禁用 G5 中包含的任何音频会议许可，并等待启用任何音频会议，直到直接路由已完全配置。 在启用音频会议许可证之前，用户应已配置拨入电话号码和工作拨号盘。 有关详细信息[，请参阅使用直接路由GCC高和 DoD](./audio-conferencing-with-direct-routing-for-gcch-and-dod.md)的音频会议。


> [!IMPORTANT]
>  如果想通过拨出或提供拨入号码将外部参与者添加到计划会议，需要音频会议许可证。
> 对于GCC高和 DoD，请勿为 G5 用户分配音频会议许可证。  对于 G3 用户，在直接路由完全配置且用户具有工作拨号盘之前，不要分配音频会议许可证。


### <a name="ad-hoc-call-escalation-and-audio-conferencing-license"></a>临时呼叫升级和音频会议许可证

用户可以 Teams Teams PSTN 或 Teams 启动一对一Teams呼叫，并添加 PSTN 参与者。 此方案称为临时会议。 呼叫采用的路径取决于升级呼叫的用户是否分配有 Microsoft 音频会议许可证：

- 如果Teams呼叫的用户分配有 Microsoft 音频会议许可证，则升级是通过 Microsoft 音频会议服务发生的。 受邀加入现有呼叫的远程 PSTN 参与者将收到有关传入呼叫的通知，并查看分配给发起升级的 Teams 用户的 Microsoft 网桥数量。
- 如果Teams升级的用户未分配 Microsoft 音频会议许可证，则升级是通过连接到直接路由接口的会话边界控制器发生的。 受邀加入呼叫的远程 PSTN 参与者将收到有关传入呼叫的通知，并查看发起升级Teams用户的数量。 用于升级的特定 SBC 由用户的路由策略定义。 


此外，必须确保以下各项：
 
- CsOnlineVoiceRoutingPolicy 分配给用户。 
- 在租户级别为用户启用允许专用Microsoft Teams。 

直接路由还支持获得 Microsoft 呼叫计划许可的用户。 Microsoft 电话具有呼叫计划的系统可以使用直接路由接口路由某些调用。 但是，用户的电话号码必须在线获取或移植到 Microsoft。  

为同一用户混合使用呼叫计划和直接路由连接是可选的，但 (例如，当用户分配了 Microsoft 呼叫计划，但想要使用 SBC) 路由某些呼叫时。 最常见的方案之一是调用第三方 PBX。  使用第三方 PBX 时，所有呼叫（连接到该 PBX 的电话除外）都使用 Microsoft 呼叫计划进行路由，但连接到第三方 PBX 的电话的呼叫将转到 SBC，因此停留在企业网络中，而不是 PSTN 内。 

有关许可电话系统，请参阅[从计划选项Office](https://products.office.com/compare-all-microsoft-office-products?tab=2)[和计划选项](/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options)。 

有关许可电话系统，请参阅Microsoft Teams[附加许可。](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md) 

## <a name="supported-end-points"></a>支持的终点 

可以使用 作为终点：

- 任何Teams客户端。 
- 公用区域电话。 请参阅[设置公共区域电话许可证Microsoft Teams。](./set-up-common-area-phones.md) 请注意，使用直接路由设置公用区域电话呼叫计划许可证。
- Skype for Business 3PIP 电话。 请参阅[Skype for Business 3PIP (3PIP) 支持Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Skype-for-Business-phones-3PIP-support-with-Microsoft-Teams/ba-p/789351)


## <a name="sbc-domain-names"></a>SBC 域名

SBC 域名必须来自在租户的"域"中注册的名称之一。 不能将 \* .onmicrosoft.com 租户用于 SBC 的 FQDN 名称。

下表显示了为租户注册的 DNS 名称的示例、该名称是否可以用作 SBC 的 FQDN，以及有效 FQDN 名称的示例：

|DNS 名称|可用于 SBC FQDN|FQDN 名称示例|
|:--- |:--- |:--- |
contoso.com|是|**有效名称：**<br/>sbc1.contoso.com<br/>ssbcs15.contoso.com<br/>europe.contoso.com|
|contoso.onmicrosoft.com|不支持|SBC onmicrosoft.com 不支持使用 *.onmicrosoft.com 域

假设要使用新的域名。 例如，租户已 contoso.com 作为在租户中注册的域名，并且想要使用 sbc1.sip.contoso.com。 在将 SBC 与名称 sbc1.sip.contoso.com 之前，必须在租户 sip.contoso.com 域中注册域名。 如果在注册域名之前尝试将 SBC 与 sbc1.sip.contoso.com 配对，则收到以下错误："无法使用"sbc1.sip.contoso.com"域，因为它未为此租户配置。"
添加域名后，还需要使用 UPN 帐户创建用户 user@sip.contoso.com 分配Teams许可证。 将域名添加到租户的"域"后，可能需要最多 24 小时才能完全预配该域名，将创建具有新名称的用户，并将许可证分配给该用户。 

公司可能在一个租户中具有多个 SIP 地址空间。 例如，公司可能 contoso.com SIP 地址空间，fabrikam.com 第二个 SIP 地址空间。 某些用户具有地址 user@contoso.com 一些用户具有地址 user@fabrikam.com。 

SBC 只需要一个 FQDN，可以从配对租户的任何地址空间为用户提供服务。 例如，名称为 sbc1.contoso.com 的 SBC 可以接收和发送地址为 user@contoso.com 和 user@fabrikam.com 的用户的 PSTN 流量，只要这些 SIP 地址空间注册在同一租户中。  

## <a name="public-trusted-certificate-for-the-sbc"></a>SBC 的公共受信任证书

Microsoft 建议通过生成认证签名请求来请求 SBC 的证书， (CSR) 。 有关为 SBC 生成 CSR 的详细说明，请参阅 SBC 供应商提供的互连说明或文档。 

  > [!NOTE]
  > 大多数证书颁发 (ca) 要求私钥大小至少为 2048。 生成 CSR 时，请记住这一点。

该证书需要将 SBC FQDN 作为 CN (公用) 或 SAN (可选) 名称。 证书应直接从证书颁发机构颁发，而不是从中间提供商颁发。

或者，直接路由支持 CN 和/或 SAN 中的通配符，并且通配符需要符合标准的[RFC HTTP over TLS。](https://tools.ietf.org/html/rfc2818#section-3.1) 例如，使用 \* .contoso.com，它匹配 SBC FQDN sbc.contoso.com，但不与 sbc.test.contoso.com。

证书需要由以下根证书颁发机构之一生成：

- Trust
- AddTrust 外部 CA 根
- Baltimore CyberTrust 根*
- Buypass
- Cybertrust
- 类 3 公共主要证书颁发机构
- Comodo 安全根 CA
- Deutsche Telekom 
- DigiCert 全局根 CA
- DigiCert 高保障 EV 根 CA
- 委托
- GlobalSign
- Go Daddy
- GeoTrust
- Verisign， Inc. 
- SSL.com
- Starfield
- Symantec Enterprise Microsoft 移动根 
- 瑞士
- Thawte 时间戳 CA
- Trustwave
- TeliaSonera 
- T-Systems International GmbH (Deutsche Telekom) 
- QuoVadis
- USERTrust RSA 证书颁发机构
- 宏和后根 CA 1，2，3
- Sectigo 根 CA

对于 GCCH Office 365 DoD 环境中的直接路由，证书需要由以下根证书颁发机构之一生成：
- DigiCert 全局根 CA
- DigiCert 高保障 EV 根 CA

> [!NOTE]
> *如果为 SBC 上的 Teams 连接启用了相互 TLS (MTLS) 支持，则必须在 Teams TLS 上下文的 SBC 受信任根存储中安装 Baltimore CyberTrust 根证书。  (这是因为 Microsoft 服务证书使用 Baltimore 根证书。) 若要下载 Baltimore 根证书，请参阅 Office 365[加密链](/microsoft-365/compliance/encryption-office-365-certificate-chains)。

Microsoft 正在努力根据客户请求添加其他证书颁发机构。 

## <a name="sip-signaling-fqdns"></a>SIP 信号：FQDN 

直接路由在下列环境中提供：
- Microsoft 365 或 Office 365
- Office 365 GCC
- Office 365 GCC高
- Office 365DoD

详细了解 Office 365[和美国政府](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government)环境，例如 GCC、GCC High 和 DoD。

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Microsoft 365、Office 365和Office 365 GCC环境

直接路由的连接点为以下三个 FQDN：

- **sip.pstnhub.microsoft.com** - 全局 FQDN – 必须先尝试。 当 SBC 发送解析此名称的请求时，Microsoft Azure DNS 服务器返回指向分配给 SBC 的主要 Azure 数据中心的 IP 地址。 分配基于数据中心的性能指标和与 SBC 的地理邻近性。 返回的 IP 地址对应于主 FQDN。
- **sip2.pstnhub.microsoft.com** - 辅助 FQDN - 在地理上映射到第二个优先级区域。
- **sip3.pstnhub.microsoft.com** - 第三级 FQDN - 在地理上映射到第三个优先区域。

必须按以下顺序放置这三个 FQDN：

- 通过查询第一个 FQDN (，在负载较少且最接近分配的 SBC 数据中心时提供最佳) 。
- 建立从 SBC 到遇到临时问题的数据中心的连接时，提供故障转移。 有关详细信息，请参阅 [下面的故障转移](#failover-mechanism-for-sip-signaling) 机制。  

FQNS（sip.pstnhub.microsoft.com、sip2.pstnhub.microsoft.com sip3.pstnhub.microsoft.com）将解析为以下 IP 地址之一：

- 52.114.148.0
- 52.114.132.46 
- 52.114.75.24 
- 52.114.76.76 
- 52.114.7.24 
- 52.114.14.70
- 52.114.16.74
- 52.114.20.29
- 52.114.36.156 
- 52.114.32.169

需要在防火墙中打开所有这些 IP 地址的端口，以允许传入和传出流量传入和传出地址以发出信号。  如果防火墙支持 DNS 名称，FQDN **sip-all.pstnhub.microsoft.com** 解析为所有这些 IP 地址。 

> [!IMPORTANT]
> 作为直接Teams和服务改进的一部分，我们于 2020 年 11 月在澳大利亚部署了 Direct Routing 基础结构的新实例。 这反映在两个额外的 IP 地址 (52.114.16.74 和 52.114.20.29) 澳大利亚客户将解析为以下 FQNS – sip.pstnhub.microsoft.com、sip2.pstnhub.microsoft.com 和 sip3.pstnhub.microsoft.com。 需要向 IP 访问控制列表 (ACL) 添加这两个 IP 地址 (52.114.16.74 和 52.114.20.29) ，并打开防火墙中所有这些 IP 地址的端口，以允许传入和传出发信的地址。

> [!IMPORTANT]
> 作为直接路由Teams和服务改进的一部分，我们于 2021 年 5 月在日本部署了 Direct Routing 基础结构的新实例。 这反映在另外两个 IP 地址 (52.114.36.156 和 52.114.32.169) 日本客户将解析为以下 FQNS – sip.pstnhub.microsoft.com、sip2.pstnhub.microsoft.com 和 sip3.pstnhub.microsoft.com。 需要将这两个 IP 地址 (52.114.36.156 和 52.114.32.169) 添加到 IP 访问控制列表 (ACL) ，并打开防火墙中所有这些 IP 地址的端口，以便传入和传出发信的地址。

### <a name="office-365-gcch-and-dod-environment"></a>Office 365GCCH 和 DoD 环境

直接路由的连接点是以下 FQDN：

**sip.pstnhub.dod.teams.microsoft.us** - 全局 FQDN。 由于Office 365 DoD 环境仅存在于美国数据中心，因此没有辅助和第三级 FQD。

FQDN sip.pstnhub.dod.teams.microsoft.us 将解析为以下 IP 地址之一：

- 52.127.64.33
- 52.127.68.34

需要在防火墙中打开所有这些 IP 地址的端口，以允许传入和传出流量传入和传出地址以发出信号。

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC高环境

直接路由的连接点是以下 FQDN：

**sip.pstnhub.gov.teams.microsoft.us** - 全局 FQDN。 由于GCC高环境仅存在于美国数据中心，因此没有辅助和第三级 FQDN。

FQDN sip.pstnhub.gov.teams.microsoft.us 解析为以下 IP 地址之一：

- 52.127.88.59
- 52.127.92.64

需要在防火墙中打开所有这些 IP 地址的端口，以允许传入和传出流量传入和传出地址以发出信号。 如果防火墙支持 DNS 名称，FQDN **sip-all.pstnhub.gov.teams.microsoft.us** 解析为所有这些 IP 地址。 此 FQDN 还可以用作入站呼叫分类的联合 FQDN。

## <a name="sip-signaling-ports"></a>SIP 信号：端口

必须在提供直接路由Microsoft 365 Office 365环境使用以下端口：
- Microsoft 365 或 Office 365
- Office 365 GCC
- Office 365 GCC高
- Office 365DoD

|流量|从|到|源端口|目标端口|
|:--- |:--- |:--- |:--- |:--- |
|SIP/TLS|SIP 代理|SBC|1024 – 65535|在 SBC 端口 (为Office 365 GCC/DoD，只能使用端口 5061) |
SIP/TLS|SBC|SIP 代理|在 SBC 上定义|5061|
||||||

### <a name="failover-mechanism-for-sip-signaling"></a>SIP 信号的故障转移机制

SBC 会进行 DNS 查询来解析 sip.pstnhub.microsoft.com。 根据 SBC 位置和数据中心性能指标，选择主数据中心。 如果主数据中心遇到问题，SBC 将尝试 sip2.pstnhub.microsoft.com，它将解析为第二个分配的数据中心，在两个区域中的数据中心不可用的极少数情况下，SBC 会重试最后一个 FQDN (sip3.pstnhub.microsoft.com) ，它提供第三级数据中心 IP。

下表汇总了主数据中心、辅助数据中心和第三数据中心之间的关系：

|如果主数据中心为|EMEA|NOAM|亚洲|
|:--- |:--- |:--- |:--- |
|辅助数据中心 (sip2.pstnhub.microsoft.com) |美国|欧盟|美国|
|第三数据中心 (sip3.pstnhub.microsoft.com) |亚洲|亚洲|欧盟|
|||||

## <a name="media-traffic-port-ranges"></a>媒体流量：端口范围
请注意，如果要在不绕过媒体的情况下部署直接路由，则以下要求适用。 有关媒体绕过的防火墙要求，请参阅使用直接路由 [规划媒体绕过](./direct-routing-plan-media-bypass.md)。



媒体流量流入和流出 Microsoft 云中的单独服务。 媒体流量的 IP 地址范围如下所示。

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Microsoft 365、Office 365和Office 365 GCC环境

- 52.112.0.0/14 (IP 地址从 52.112.0.1 到 52.115.255.254) 。
- 52.120.0.0/14 (IP 地址从 52.120.0.1 到 52.123.255.254) 。

### <a name="office-365-dod-environment"></a>Office 365DoD 环境

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC高环境

- 52.127.88.0/21

### <a name="port-range-applicable-to-all-environments"></a>端口范围 (适用于所有环境) 
下表显示了媒体处理器的端口范围： 

|流量|从|到|源端口|目标端口|
|:--- |:--- |:--- |:--- |:--- |
|UDP/SRTP|媒体处理器|SBC|3478-3481 和 49152 – 53247|在 SBC 上定义|
|UDP/SRTP|SBC|媒体处理器|在 SBC 上定义|3478-3481 和 49152 – 53247|

  > [!NOTE]
  > Microsoft 建议在 SBC 上每个并发调用至少使用两个端口。


## <a name="media-traffic-media-processors-geography"></a>媒体流量：媒体处理器地理位置

媒体流量通过称为媒体处理器的组件流动。 媒体处理器放置在与 SIP 代理相同的数据中心。 此外，还有其他媒体处理器来优化媒体流。 例如，现在澳大利亚没有 SIP 代理组件 (通过新加坡或香港特别行政区的 SIP 流) 但澳大利亚本地有媒体处理器。 本地媒体处理器需求取决于我们长时间发送流量（例如从澳大利亚到新加坡或香港特别行政区）时所经历的延迟。 尽管从澳大利亚流向香港特别行政区或新加坡的流量示例中的延迟是可接受的，但对于实时媒体流量，可以保留良好的 SIP 流量呼叫质量。

媒体处理器的位置：

SIP 代理和媒体处理器组件部署的位置：
- 美国 (美国西部和东部数据中心有两个) 
- 欧洲 (阿姆斯特丹和都柏林数据中心) 
- 亚洲 (新加坡和香港特别行政区) 
- 日本 (日本东部和西部数据中心) 
- 澳大利亚 (澳大利亚东部和东南部数据中心) 

## <a name="media-traffic-codecs"></a>媒体流量：编解码器

### <a name="leg-between-sbc-and-cloud-media-processor-or-microsoft-teams-client"></a>在 SBC 与云媒体处理器或客户端Microsoft Teams。
适用于媒体绕过案例和非绕过情况。

在会话边界控制器和云媒体处理器 (之间（没有媒体旁路) ）之间或者 Teams 客户端与 SBC (（如果启用了媒体旁路）之间，直接路由接口) 可以使用以下编解码器：

- 通过 SBC (云媒体处理器的非媒体旁路) ：SILK、G.711、G.722、G.729
- 媒体旁路 (SBC Teams客户端) ：SILK、G.711、G.722、G.729

可以通过从产品/服务中排除不需要的编解码器来强制使用会话边界控制器上的特定编解码器。

### <a name="leg-between-microsoft-teams-client-and-cloud-media-processor"></a>在客户端Microsoft Teams云媒体处理器之间移动
仅适用于非媒体旁路情况。 使用媒体旁路，媒体在客户端Teams SBC 之间直接流动。

在云媒体处理器和客户端之间Microsoft Teams使用 SILK 或 G.722。 此方面的编解码器选择基于 Microsoft 算法，这些算法考虑多个参数。 


## <a name="supported-session-border-controllers-sbcs"></a>支持的会话边界控制器 (SDC) 

Microsoft 仅支持通过认证的 SDC 与直接路由配对。 由于企业语音企业至关重要，Microsoft 使用选定的 SBC 运行密集型测试，并配合 SBC 供应商确保两个系统兼容。 

已验证的设备将列为"已认证Teams直接路由"。 保证经认证的设备在所有方案中都正常工作。 

有关支持的 SDC 详细信息，请参阅通过直接路由 认证的 [会话边界控制器列表](direct-routing-border-controllers.md)。

 
## <a name="see-also"></a>另请参阅

[配置直接路由](direct-routing-configure.md)
