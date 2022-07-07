---
title: 规划直接路由
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: filippse
ms.topic: conceptual
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.custom: seo-marvel-mar2020
description: 了解 Microsoft 直接路由如何使你能够将受支持的客户提供的会话边界控制器 (SBC) 连接到电话系统。
ms.openlocfilehash: a5ccb8534ed8772124ae6e2506af81e5b63134d0
ms.sourcegitcommit: d87991ed2d3e4d70edb048378763a17ff689b710
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2022
ms.locfileid: "66682511"
---
# <a name="plan-direct-routing"></a>规划直接路由

> [!Tip]
> 观看以下会话，了解直接路由的好处、如何规划直接路由以及如何部署它： [Microsoft Teams 中的直接路由](https://aka.ms/teams-direct-routing)

通过直接路由，可以将受支持的客户提供的会话边界控制器 (SBC) 连接到电话系统。 使用此功能，可以配置本地公用交换电话网络 (PSTN) 与 Microsoft Teams 客户端的连接，如下图所示： 

![显示本地 PSTN 连接配置的示意图。](media/PlanDirectRouting1-PSTNwithTeams.png "配置与 Microsoft Teams 客户端的本地 PSTN 连接")

  > [!NOTE]
  > Skype for Business Online 还允许你对客户提供的 SBC 进行配对，但这需要在 SBC 和 Microsoft 云之间部署本地Skype for Business Server或特殊版本的 Skype for Business（称为云连接器）。 此方案称为混合语音。 相比之下，直接路由允许在受支持的 SBC 和 Microsoft Cloud 之间建立直接连接。

> [!Important]
> Cloud Connector Edition 将于 2021 年 7 月 31 日停用，Skype for Business Online。 组织升级到 Teams 后，了解如何使用 [直接路由](direct-routing-landing-page.md)将本地电话网络连接到 Teams。 

通过直接路由，可以将 SBC 连接到几乎任何电话中继或与第三方 PSTN 设备互连。 直接路由使你可以： 

- 将几乎所有 PSTN 中继与电话系统配合使用。 

- 配置客户拥有的电话设备（例如第三方专用分支交换 (PBX) 、模拟设备和 Teams）之间的互操作性。

Microsoft 还提供全云语音解决方案，例如通话套餐。 但是，如果以下情况，混合语音解决方案可能最适合你的组织： 

- Microsoft 呼叫计划在您的国家/地区不可用。 

- 组织需要连接到第三方模拟设备、呼叫中心等。 

- 你的组织与 PSTN 运营商有一份现有合同。

直接路由还支持拥有 Microsoft 通话计划附加许可证的用户。 有关详细信息，请参阅 [电话系统和呼叫计划](calling-plan-landing-page.md)。 

使用直接路由时，当用户参加计划的会议时，拨入号码由 Microsoft 音频会议服务提供，这需要适当的许可。  拨出时，Microsoft 音频会议服务使用需要适当许可的联机呼叫功能来放置呼叫。  (请注意，如果用户没有 Microsoft 音频会议许可证，则呼叫路由通过 Direct Routing.) 有关详细信息，请 [参阅 Teams 的联机会议](https://www.microsoft.com/en-us/microsoft-teams/online-meetings)。 
 
规划直接路由的部署是成功实现的关键。 本文介绍基础结构和许可要求，并提供有关 SBC 连接的信息： 

- [基础结构要求](#infrastructure-requirements)
- [许可和其他要求](#licensing-and-other-requirements)
- [SBC 域名](#sbc-domain-names)
- [SBC 的公共受信任证书](#public-trusted-certificate-for-the-sbc)
- [SIP 信号：FQDN](#sip-signaling-fqdns)
- [SIP 信号：端口](#sip-signaling-ports)
- [媒体流量：端口范围](#media-traffic-port-ranges)
- [支持的会话边框控制器 (SBC) ](#supported-session-border-controllers-sbcs)

有关配置直接路由的详细信息，请参阅 [配置直接路由](direct-routing-configure.md)。

## <a name="infrastructure-requirements"></a>基础结构要求
下表列出了支持 SBC、域和其他部署直接路由的网络连接要求的基础结构要求：  

|基础结构要求|需要以下内容|
|:--- |:--- |
|会话边框控制器 (SBC) |支持的 SBC。 有关详细信息，请参阅 [支持的 SBC](#supported-session-border-controllers-sbcs)。|
|连接到 SBC 的电话中继|连接到 SBC 的一个或多个电话中继。 在一端，SBC 通过直接路由连接到电话系统。 SBC 还可以连接到第三方电话实体，如 PBX、模拟电话适配器等。 连接到 SBC 的任何 PSTN 连接选项都将正常工作。  (若要将 PSTN 中继配置到 SBC，请参阅 SBC 供应商或中继提供商。) |
|Microsoft 365 组织|用于托管 Microsoft Teams 用户的 Microsoft 365 组织，以及与 SBC 的配置和连接。|
|用户注册机构|用户必须位于 Microsoft 365 中。<br/>如果你的公司具有与 Microsoft 365 混合连接的本地Skype for Business或 Lync 环境，则无法为本地用户在 Teams 中启用语音。<br/><br/>若要检查用户的注册机构，请使用以下Skype for Business Online PowerShell cmdlet：<br/><code>Get-CsOnlineUser -Identity \<user> \| fl HostingProvider</code> <br/><br/>cmdlet 的输出应显示：<br/><code>HostingProvider : sipfed.online.lync.com</code>|
|域|添加到 Microsoft 365 或Office 365组织的一个或多个域。<br/><br/>请注意，不能使用自动为租户创建的默认域 \*.onmicrosoft.com。<br/><br/>若要查看域，可以使用以下Skype for Business Online PowerShell cmdlet：<br/><code>Get-CsTenant \| fl Domains</code><br/><br/>有关域和 Microsoft 365 或Office 365组织的详细信息，请参阅[域常见问题解答](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a)。|
|SBC 的公共 IP 地址|可用于连接到 SBC 的公共 IP 地址。 根据 SBC 的类型，SBC 可以使用 NAT。|
|SBC 的完全限定域名 (FQDN) |SBC 的 FQDN，其中 FQDN 的域部分是 Microsoft 365 或Office 365组织中的已注册域之一。 有关详细信息，请参阅 [SBC 域名](#sbc-domain-names)。|
|SBC 的公共 DNS 条目 |将 SBC FQDN 映射到公共 IP 地址的公共 DNS 条目。 |
|SBC 的公共受信任证书 |用于与直接路由进行所有通信的 SBC 的证书。 有关详细信息，请参阅 [SBC 的公共受信任证书](#public-trusted-certificate-for-the-sbc)。|
|直接路由的连接点 |直接路由的连接点是以下三个 FQDN：<br/><br/>`sip.pstnhub.microsoft.com` – 必须先尝试全局 FQDN。<br/>`sip2.pstnhub.microsoft.com` – 辅助 FQDN，地理位置映射到第二个优先级区域。<br/>`sip3.pstnhub.microsoft.com` – 第三级 FQDN，在地理上映射到第三个优先级区域。<br/><br/>有关配置要求的信息，请参阅 [SIP 信号：FQDN](#sip-signaling-fqdns)。|
|直接路由媒体的防火墙 IP 地址和端口 |SBC 与云中的以下服务通信：<br/><br/>处理信号的 SIP 代理<br/>处理媒体的媒体处理器 - 媒体旁路打开时除外<br/><br/>这两个服务在 Microsoft Cloud 中具有单独的 IP 地址，本文档稍后对此进行了介绍。<br/><br/>有关详细信息，请参阅 [URL 和 IP 地址范围](/office365/enterprise/urls-and-ip-address-ranges)中的 [Microsoft Teams 部分](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)。 |
|媒体传输配置文件|TCP/RTP/SAVP <br/>UDP/RTP/SAVP|
Microsoft Teams 媒体的防火墙 IP 地址和端口 |有关详细信息，请参阅 [URL 和 IP 地址范围](/office365/enterprise/urls-and-ip-address-ranges)。 |
|||

## <a name="licensing-and-other-requirements"></a>许可和其他要求 

直接路由的用户必须在 Microsoft 365 中分配以下许可证： 

- Microsoft Phone 系统
- Microsoft Teams + Skype for Business计划 2（如果包含在许可中）
- Microsoft 音频会议 (阅读笔记和以下段落，了解有关何时需要此许可证的特定示例。) 

> [!NOTE]
> Skype for Business计划不应从包含计划的任何许可协议中删除。 
> 
> [!IMPORTANT]
> GCC High 和 DoD 用户应禁用 G5 中包含的任何音频会议许可，并等待启用任何音频会议，直到直接路由已完全配置完毕。 在启用音频会议许可证之前，用户应配置电话拨入电话号码和工作拨号盘。 有关更多详细信息，请参阅 [具有 GCC High 和 DoD 直接路由的音频会议](./audio-conferencing-with-direct-routing-for-gcch-and-dod.md) 。


> [!IMPORTANT]
>  如果要将外部参与者添加到计划的会议（通过向他们拨号或提供拨入号码），则需要音频会议许可证。
> 对于 GCC High 和 DoD，请勿为 G5 用户分配音频会议许可证。 对于 G3 用户，在直接路由已完全配置并且用户具有工作拨号盘之前，请勿分配音频会议许可证。


### <a name="ad-hoc-call-escalation-and-audio-conferencing-license"></a>即席呼叫升级和音频会议许可证

Teams 用户可以启动一对一 Teams 到 PSTN 或 Teams 到 Teams 的呼叫，并向其添加 PSTN 参与者。 此方案称为临时会议。 呼叫所采用的路径取决于升级呼叫的用户是否分配了 Microsoft 音频会议许可证：

- **如果升级呼叫的 Teams 用户分配了 Microsoft 音频会议许可证**，则会通过 Microsoft 音频会议服务进行升级。 受邀加入现有呼叫的远程 PSTN 参与者将收到有关传入呼叫的通知，并查看分配给发起升级的 Teams 用户的 Microsoft 网桥数。

- **如果升级调用的 Teams 用户未分配 Microsoft 音频会议许可证**，则通过连接到直接路由接口的会话边界控制器进行升级。 受邀加入呼叫的远程 PSTN 参与者将收到有关传入呼叫的通知，并查看发起升级的 Teams 用户的数目。 用于升级的特定 SBC 由用户的路由策略定义。 

必须确保以下各项：
 
- CsOnlineVoiceRoutingPolicy 分配给用户。 

- 允许专用呼叫在 Microsoft Teams 的租户级别启用。 

直接路由还支持获得 Microsoft 通话套餐许可的用户。 具有通话套餐的电话系统可以使用直接路由接口路由某些呼叫。 但是，用户的电话号码必须联机获取或移植到 Microsoft。  

混合调用计划和同一用户的直接路由连接是可选的，但可能很有用。 例如，为用户分配 Microsoft 呼叫计划，但想要使用 SBC 路由某些调用时。 最常见的方案之一是调用第三方 PBX。  使用第三方 PBX，除了对连接到该 PBX 的电话的呼叫外，所有呼叫均使用 Microsoft 呼叫计划路由，但对连接到第三方 PBX 的手机的呼叫将转到 SBC，因此会保留在企业网络而不是 PSTN 中。 

有关电话系统许可的详细信息，请参阅 [充分利用 Office](https://products.office.com/compare-all-microsoft-office-products?tab=2) 和 [计划选项](/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options) 以及 [Microsoft Teams 附加许可](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。 

## <a name="supported-end-points"></a>支持的终结点 

可以用作终结点：

- 任何 Teams 客户端。 

- 公用区域电话。 请参阅 [为 Microsoft Teams 设置通用区域电话](./set-up-common-area-phones.md)。 在设置具有直接路由的公共区域电话时，不需要呼叫计划许可证。

- Skype for Business 3PIP 手机。 请参阅[Skype for Business手机 (Microsoft Teams 的 3PIP) 支持](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Skype-for-Business-phones-3PIP-support-with-Microsoft-Teams/ba-p/789351)


## <a name="sbc-domain-names"></a>SBC 域名

SBC 域名必须来自租户域中注册的某个名称。 不能将 \*.onmicrosoft.com 租户用于 SBC 的 FQDN 名称。

下表显示了为租户注册的 DNS 名称的示例、该名称是否可以用作 SBC 的 FQDN，以及有效 FQDN 名称的示例：

|DNS 名称|可用于 SBC FQDN|FQDN 名称示例|
|:--- |:--- |:--- |
contoso.com|是|**有效名称：**<br/>sbc1.contoso.com<br/>ssbcs15.contoso.com<br/>europe.contoso.com|
|contoso.onmicrosoft.com|弱|SBC 名称不支持使用 *.onmicrosoft.com 域

假设要使用新域名。 例如，租户已 contoso.com 为在租户中注册的域名，并且你希望使用 sbc1.sip.contoso.com。 必须先在租户的域中注册域名 sip.contoso.com，然后才能将 SBC 与名称 sbc1.sip.contoso.com 配对。 如果在注册域名之前尝试将 SBC 与 sbc1.sip.contoso.com 配对，则会收到以下错误：“无法使用”sbc1.sip.contoso.com“域，因为它未为此租户配置。
添加域名后，还需要使用 UPN user@sip.contoso.com 创建用户并分配 Teams 许可证。 将域名添加到租户的域、创建新名称的用户以及向用户分配许可证后，可能需要长达 24 小时才能完全预配域名。 

一家公司在一个租户中可能有多个 SIP 地址空间。 例如，公司可能 contoso.com 为 SIP 地址空间，fabrikam.com 为第二个 SIP 地址空间。 某些用户有地址 user@contoso.com，有些用户有地址 user@fabrikam.com。 

SBC 只需要一个 FQDN，并且可以从配对租户中的任何地址空间为用户提供服务。 例如，具有名称 sbc1.contoso.com 的 SBC 可以接收和发送具有地址 user@contoso.com 和 user@fabrikam.com 的用户的 PSTN 流量，前提是这些 SIP 地址空间已在同一租户中注册。  

## <a name="public-trusted-certificate-for-the-sbc"></a>SBC 的公共受信任证书

Microsoft 建议通过生成证书签名请求 (CSR) 来请求 SBC 的证书。 有关为 SBC 生成 CSR 的具体说明，请参阅 SBC 供应商提供的互连说明或文档。 

> [!NOTE]
> 大多数证书颁发机构 (CA) 要求私钥大小至少为 2048。 生成 CSR 时请记住这一点。

证书需要将 SBC FQDN 作为通用名称 (CN) 或使用者替代名称 (SAN) 字段。

或者，直接路由支持 CN 和/或 SAN 中的通配符，通配符需要符合 [标准 RFC HTTP over TLS](https://tools.ietf.org/html/rfc2818#section-3.1)。 例如，使用 \*与 SBC FQDN sbc.contoso.com 匹配但与 sbc.test.contoso.com 不匹配的 .contoso.com。

直接路由 SIP 接口将仅信任证书颁发机构 (CA) （属于 Microsoft 受信任的根证书计划）签名的证书。 确保 SBC 证书由属于程序的 CA 签名，并且扩展密钥使用 (EKU) 扩展包含服务器身份验证。
了解详细信息： [计划要求 - Microsoft 受信任的根计划](/security/trusted-root/program-requirements)
  
[包含 CA 证书列表](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)
  
 对于Office 365 GCCH 和 DoD 环境中的直接路由，证书需要由以下根证书颁发机构之一生成：

- DigiCert 全局根 CA
- DigiCert 高保证 EV 根 CA

> [!NOTE]
> 如果为 SBC 上的 Teams 连接启用了相互 TLS (MTLS) 支持，则必须在 Teams TLS 上下文的 SBC 受信任根存储中安装 Baltimore CyberTrust Root 和 DigiCert Global Root G2 证书。  (这是因为 Microsoft 服务证书使用这两个根证书之一。) 若要下载这些根证书，请参阅[Office 365加密链](/microsoft-365/compliance/encryption-office-365-certificate-chains)。 有关详细信息，请参阅 [Office TLS 证书更改](/microsoft-365/compliance/encryption-office-365-tls-certificates-changes)。

## <a name="sip-signaling-fqdns"></a>SIP 信号：FQDN 

在以下环境中提供直接路由：

- Microsoft 365 或 Office 365
- Office 365 GCC
- Office 365 GCC High
- Office 365 DoD

详细了解 GCC、GCC High 和 DoD 等[Office 365和美国政府环境](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government)。

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Microsoft 365、Office 365 和 Office 365 GCC 环境

直接路由的连接点是以下三个 FQDN：

- **sip.pstnhub.microsoft.com** - 必须先尝试全局 FQDN。 当 SBC 发送解析此名称的请求时，Microsoft Azure DNS 服务器将返回一个 IP 地址，该地址指向分配给 SBC 的主 Azure 数据中心。 分配基于数据中心的性能指标以及与 SBC 的地理邻近性。 返回的 IP 地址对应于主 FQDN。

- **sip2.pstnhub.microsoft.com** – 辅助 FQDN - 地理位置映射到第二个优先级区域。

- **sip3.pstnhub.microsoft.com** – 第三级 FQDN - 地理位置映射到第三个优先级区域。

按顺序放置这三个 FQDN 需要：

- 通过查询第一个 FQDN) ，提供 (加载较少、最接近 SBC 数据中心的最佳体验。

- 建立从 SBC 到遇到临时问题的数据中心的连接时，提供故障转移。 有关详细信息，请参阅下面 [的故障转移机制](#failover-mechanism-for-sip-signaling) 。  

FQDN （ sip.pstnhub.microsoft.com、sip2.pstnhub.microsoft.com 和 sip3.pstnhub.microsoft.com ） 将解析为以下子网中的 IP 地址：

- 52.112.0.0/14
- 52.120.0.0/14

需要在防火墙中为所有这些 IP 地址范围打开端口，以允许进出地址的传入和传出流量以进行信号发送。

### <a name="office-gcc-dod-environment"></a>Office GCC DoD 环境

直接路由的连接点是以下 FQDN：

**sip.pstnhub.dod.teams.microsoft.us** - 全局 FQDN。 由于Office 365 DoD 环境仅存在于美国数据中心，因此没有二级和第三级 FQDN。

FQDN sip.pstnhub.dod.teams.microsoft.us 将从以下子网解析为 IP 地址：

- 52.127.64.0/21

需要为防火墙中的所有这些 IP 地址打开端口，以允许进出地址的传入和传出流量以进行信号发送。

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC 高环境

直接路由的连接点是以下 FQDN：

**sip.pstnhub.gov.teams.microsoft.us** - 全局 FQDN。 由于 GCC 高环境仅存在于美国数据中心，因此没有二级和第三级 FQDN。

FQDN sip.pstnhub.gov.teams.microsoft.us 将从以下子网解析为 IP 地址：

- 52.127.88.0/21

需要为防火墙中的所有这些 IP 地址打开端口，以允许进出地址的传入和传出流量以进行信号发送。

## <a name="sip-signaling-ports"></a>SIP 信号：端口

对于提供直接路由的 Microsoft 365 或Office 365环境，必须使用以下端口：

- Microsoft 365 或 Office 365
- Office 365 GCC
- Office 365 GCC High
- Office 365 DoD

|交通|从|到|源端口|目标端口|
|:--- |:--- |:--- |:--- |:--- |
|SIP/TLS|SIP 代理|SBC|1024 – 65535|在 SBC (为Office 365 GCC High/DoD 定义的端口 5061 必须) |
SIP/TLS|SBC|SIP 代理|在 SBC 上定义|5061|
||||||

### <a name="failover-mechanism-for-sip-signaling"></a>SIP 信号的故障转移机制

SBC 发出 DNS 查询来解析 sip.pstnhub.microsoft.com。 根据 SBC 位置和数据中心性能指标，选择主数据中心。 如果主数据中心遇到问题，SBC 将尝试 sip2.pstnhub.microsoft.com，该 sip2.pstnhub.microsoft.com 解析为第二个分配的数据中心，在极少数情况下，两个区域中的数据中心不可用，SBC 将重试提供第三级数据中心 IP 的最后一个 FQDN (sip3.pstnhub.microsoft.com) 。

下表总结了主要数据中心、辅助数据中心和第三级数据中心之间的关系：

|如果主数据中心为|EMEA|NOAM|亚洲|
|:--- |:--- |:--- |:--- |
|辅助数据中心 (sip2.pstnhub.microsoft.com) |我们|欧盟|我们|
|第三级数据中心 (sip3.pstnhub.microsoft.com) |亚洲|亚洲|欧盟|
|||||

## <a name="media-traffic-port-ranges"></a>媒体流量：端口范围
请注意，如果想要在不使用媒体旁路的情况下部署直接路由，则以下要求适用。 有关媒体旁路的防火墙要求，请参阅 [使用直接路由规划媒体旁路](./direct-routing-plan-media-bypass.md)。

媒体流量流向和流出 Microsoft 云中的单独服务。 媒体流量的 IP 地址范围如下所示。

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Microsoft 365、Office 365 和 Office 365 GCC 环境

- 52.112.0.0/14 (IP 地址，从 52.112.0.1 到 52.115.255.254) 。
- 52.120.0.0/14 (IP 地址，从 52.120.0.1 到 52.123.255.254) 。

### <a name="office-365-dod-environment"></a>Office 365 DoD 环境

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC 高环境

- 52.127.88.0/21

### <a name="port-range-applicable-to-all-environments"></a>端口范围 (适用于所有环境) 
下表显示了媒体处理器的端口范围： 

|交通|从|到|源端口|目标端口|
|:--- |:--- |:--- |:--- |:--- |
|UDP/SRTP|媒体处理器|SBC|3478-3481 和 49152 – 53247|在 SBC 上定义|
|UDP/SRTP|SBC|媒体处理器|在 SBC 上定义|3478-3481 和 49152 – 53247|

  > [!NOTE]
  > Microsoft 建议在 SBC 上每次并发调用至少两个端口。


## <a name="media-traffic-media-processors-geography"></a>媒体流量：媒体处理器地理位置

媒体流量通过称为媒体处理器的组件流动。 媒体处理器与 SIP 代理位于同一数据中心：

- NOAM (美国中南部，美国西部和美国东部两个数据中心) 
- 欧洲 (英国南部、法国中部、阿姆斯特丹和都柏林数据中心) 
- 亚洲 (新加坡数据中心) 
- 日本 (JP东西方数据中心) 
- 澳大利亚 (AU 东部和东南部数据中心) 
- LATAM (巴西南) 
- 非洲 (南非北部) 

## <a name="media-traffic-codecs"></a>媒体流量：编解码器

### <a name="leg-between-sbc-and-cloud-media-processor-or-microsoft-teams-client"></a>SBC 和云媒体处理器或 Microsoft Teams 客户端之间的腿

适用于媒体旁路案例和非旁路事例。

会话边框控制器和云媒体处理器之间的直接路由接口 (，无需媒体旁路) 或 Teams 客户端与 SBC (之间（如果启用了媒体旁路) 可以使用以下编解码器：

- 非媒体旁路 (SBC 到云媒体处理器) ：SILK、G.711、G.722、G.729
- 媒体旁路 (SBC 到 Teams 的客户端) ：SILK、G.711、G.722、G.729

可以通过从产品/服务中排除不受欢迎的编解码器，在会话边界控制器上强制使用特定编解码器。

### <a name="leg-between-microsoft-teams-client-and-cloud-media-processor"></a>Microsoft Teams 客户端和云媒体处理器之间的腿

仅适用于非媒体旁路案例。 借助媒体旁路，媒体直接在 Teams 客户端和 SBC 之间流动。

在云媒体处理器和 Microsoft Teams 客户端之间，使用 SILK 或 G.722。 此腿上的编解码器选择基于 Microsoft 算法，这些算法考虑了多个参数。 

  > [!NOTE]
  > 不支持媒体重新定位。 在直接路由调用期间，如果 SBC 向 Teams 直接路由发送新媒体 IP，尽管它是在 SIP 信号中协商的，但永远不会从 Teams 直接路由将媒体发送到新的 IP 地址。

## <a name="supported-session-border-controllers-sbcs"></a>支持的会话边框控制器 (SBC) 

Microsoft 仅支持通过认证的 SBC 与直接路由配对。 由于企业语音对企业至关重要，Microsoft 使用选定的 SBC 运行密集型测试，并与 SBC 供应商合作，确保这两个系统兼容。 

已验证的设备被列为 Teams 直接路由认证。 保证认证设备在所有方案中均可正常工作。 

有关支持的 SBC 的详细信息，请参阅 [经直接路由认证的会话边界控制器](direct-routing-border-controllers.md)。

 
## <a name="see-also"></a>另请参阅

[配置直接路由](direct-routing-configure.md)
