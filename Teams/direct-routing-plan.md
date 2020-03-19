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
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 阅读本主题，了解 Microsoft Phone 系统直接路由如何让你将支持的客户提供的会话边界控制器（SBC）连接到 Microsoft Phone 系统。
ms.openlocfilehash: 0e15f8e76bc9512a28311764c39e34b45131b9d3
ms.sourcegitcommit: 86366b66b15870fe83cbb76e1ae7aa1ce9b3bfe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2020
ms.locfileid: "42858577"
---
# <a name="plan-direct-routing"></a>规划直接路由

> [!Tip]
> 观看以下会话，了解直接路由的好处、如何为其规划以及如何部署它： [Microsoft 团队中的直接路由](https://aka.ms/teams-direct-routing)

Microsoft 手机系统直接路由允许你将支持的客户提供的会话边界控制器（SBC）连接到 Microsoft Phone 系统。  例如，利用此功能，你可以配置与 Microsoft 团队客户端的本地公共交换电话网络（PSTN）连接，如下图所示： 

![显示本地 PSTN 连接配置的图表](media/PlanDirectRouting1-PSTNwithTeams.png "与 Microsoft 团队客户端的本地 PSTN 连接配置")

  > [!NOTE]
  > Skype for Business Online 还允许你与客户提供的 SBC 配对，但这需要一个本地 Skype for business 服务器部署或特殊版本的 Skype for business （称为云连接器），它位于 SBC 和 Microsoft 云之间。 此方案称为混合语音。 相比之下，直接路由允许受支持的 SBC 和 Microsoft 云之间的直接连接。 

通过直接路由，你可以将 SBC 连接到几乎任何电话中继或与第三方 PSTN 设备互连。 直接路由使您能够： 

- 将几乎任何 PSTN 中继与 Microsoft Phone 系统配合使用。 
- 配置客户拥有的电话设备（如第三方专用分支机构（PBX）、模拟设备和 Microsoft Phone 系统）之间的互操作性。

Microsoft 还提供了所有云语音解决方案，例如呼叫计划。 但是，混合语音解决方案可能最适合你的组织，前提是： 

- Microsoft 通话计划在您所在的国家/地区不可用。 
- 您的组织需要连接到第三方模拟设备、呼叫中心等。 
- 您的组织已有一个具有 PSTN 运营商的现有合同。

直接路由还支持拥有 Microsoft 通话计划附加许可证的用户。 有关详细信息，请参阅[电话系统和通话计划](calling-plan-landing-page.md)。 

通过直接路由，当用户参与计划的会议时，拨入号码由 Microsoft 音频会议服务提供，这需要正确的许可。  当拨号时，Microsoft 音频会议服务使用在线呼叫功能来呼叫呼叫，这需要正确的许可。 （请注意，拨号不通过直接路由路由。）有关详细信息，请参阅[与团队联机会议](https://products.office.com/microsoft-teams/online-meeting-solutions)。 
 
规划直接路由的部署是成功实施的关键。 本文介绍基础结构和授权要求，并提供有关 SBC 连接的信息： 

- [基础结构要求](#infrastructure-requirements)
- [许可和其他要求](#licensing-and-other-requirements)
- [SBC 域名称](#sbc-domain-names)
- [适用于 SBC 的公共受信任证书](#public-trusted-certificate-for-the-sbc)
- [SIP 信号： Fqdn](#sip-signaling-fqdns)
- [SIP 信号：端口](#sip-signaling-ports)
- [媒体流量：端口范围](#media-traffic-port-ranges)
- [支持的会话边框控制器（SBCs）](#supported-session-border-controllers-sbcs)

有关配置直接路由的详细信息，请参阅[配置直接路由](direct-routing-configure.md)。

## <a name="infrastructure-requirements"></a>基础结构要求
下表列出了用于部署直接路由的支持的 SBCs、域和其他网络连接要求的基础结构要求：  

|**基础结构要求**|**您需要以下**|
|:--- |:--- |
|会话边框控制器（SBC）|受支持的 SBC。 有关详细信息，请参阅[支持的 SBCs](#supported-session-border-controllers-sbcs)。|
|连接到 SBC 的电话中继|一个或多个电话中继连接到 SBC。 一端，SBC 通过直接路由连接到 Microsoft 手机系统。 SBC 还可以连接到第三方电话实体，如 Pbx、模拟电话适配器等。 任何连接到 SBC 的 PSTN 连接选项都将正常工作。 （有关将 PSTN 中继到 SBC 的配置，请参阅 SBC 供应商或主干提供商。）|
|Office 365 租户|用于家庭 Microsoft 团队用户的 Office 365 租户，以及与 SBC 的配置和连接。|
|用户注册机构|用户必须托管在 Office 365 中。<br/>如果你的公司有一个本地 Skype for Business 或 Lync 环境以及与 Office 365 的混合连接，则无法为驻留在本地的用户启用团队中的语音。<br/><br/>若要检查用户的注册机构，请使用以下 Skype for Business Online PowerShell cmdlet：<br/><code>Get-CsOnlineUser -Identity \<user> \| fl HostingProvider</code> <br/><br/>该 cmdlet 的输出应显示：<br/><code>HostingProvider : sipfed.online.lync.com</code>|
|域|添加到您的 Office 365 租户的一个或多个域。<br/><br/>请注意，你无法使用为你的\*租户自动创建的默认域 onmicrosoft.com。<br/><br/>若要查看域，您可以使用以下 Skype for Business Online PowerShell cmdlet：<br/><code>Get-CsTenant \| fl Domains</code><br/><br/>有关域和 Office 365 租户的详细信息，请参阅[域常见问题解答](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a)。|
|SBC 的公共 IP 地址|可用于连接到 SBC 的公共 IP 地址。 SBC 可以使用 NAT，具体取决于 SBC 的类型。|
|适用于 SBC 的完全限定的域名（FQDN）|SBC 的 FQDN，其中 FQDN 的域部分是 Office 365 租户中注册的域之一。 有关详细信息，请参阅[SBC 域名](#sbc-domain-names)。|
|SBC 的公共 DNS 条目 |将 SBC FQDN 映射到公共 IP 地址的公共 DNS 条目。 |
|适用于 SBC 的公共受信任证书 |用于 SBC 的证书，用于与直接路由的所有通信。 有关详细信息，请参阅[SBC 的公共受信任证书](#public-trusted-certificate-for-the-sbc)。|
|直接路由的连接点 |直接路由的连接点是以下三个 Fqdn：<br/><br/>`sip.pstnhub.microsoft.com`-必须首先尝试全局 FQDN。<br/>`sip2.pstnhub.microsoft.com`-辅助 FQDN，地理位置映射到第二个优先级区域。<br/>`sip3.pstnhub.microsoft.com`-第三方 FQDN-地理位置映射到第三个优先级区域。<br/><br/>有关配置要求的信息，请参阅[SIP 信号： fqdn](#sip-signaling-fqdns)。|
|用于直接路由媒体的防火墙 IP 地址和端口 |SBC 与云中的以下服务进行通信：<br/><br/>负责处理信号的 SIP 代理<br/>处理媒体的媒体处理器-当媒体绕过时除外<br/><br/>这两个服务在 Microsoft 云中具有单独的 IP 地址，如本文档后面部分所述。<br/><br/>有关详细信息，请参阅[Office 365 url 和 IP 地址范围](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)中的 " [Microsoft 团队" 部分](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)。 |
|媒体传输配置文件|TCP/RTP/SAVP <br/>UDP/RTP/SAVP|
适用于 Microsoft 团队媒体的防火墙 IP 地址和端口 |有关详细信息，请参阅[Office 365 url 和 IP 地址范围](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)。 |
|||

## <a name="licensing-and-other-requirements"></a>许可和其他要求 

直接路由用户必须在 Office 365 中分配以下许可证： 

- Microsoft Phone 系统。 
- Microsoft 团队 + Skype for Business 计划2（如果包含在 "授权" 中）。
- Microsoft 音频会议（有关何时需要许可证的具体示例，请阅读备注和以下段落）。

> [!NOTE]
> 不应将 Skype for business 计划从包括它的任何许可协议中删除。 


> [!IMPORTANT]
>  如果你想要将外部参与者添加到计划会议，请通过拨出或提供拨入号码来向其添加外部参与者，需要音频会议许可证。


### <a name="ad-hoc-call-escalation-and-audio-conferencing-license"></a>临时呼叫升级和音频会议许可证

团队用户可以启动一对一团队到 PSTN 或团队成员通话，并向其添加 PSTN 参与者。 此方案称为点对点会议。 该调用所采用的路径取决于进行此呼叫的用户是否已分配 Microsoft 音频会议许可证：

- 如果提出通话的团队用户分配了 Microsoft 音频会议许可证，则会通过 Microsoft 音频会议服务进行升级。 被邀请加入现有呼叫的远程 PSTN 参与者接收有关传入呼叫的通知，并查看分配给启动升级的团队用户的 Microsoft bridge 的号码。
- 如果提出通话的团队用户没有分配 Microsoft 音频会议许可证，则会通过连接到直接路由界面的会话边界控制器进行升级。 被邀请呼叫的远程 PSTN 参与者接收有关传入呼叫的通知，并查看发起升级的团队用户数。 用于升级的特定 SBC 由用户的路由策略定义。 


此外，必须确保以下内容：
 
- CsOnlineVoiceRoutingPolicy 已分配给用户。 
- 允许在 Microsoft 团队的租户级别启用私人通话。 

直接路由还支持为 Microsoft 通话计划授权的用户。 带有呼叫计划的 Microsoft Phone 系统可以使用直接路由界面路由某些呼叫。 但是，用户的电话号码必须是联机购买的或移植到 Microsoft。  

为同一用户混合呼叫计划和直接路由连接是可选的，但可能很有用（例如，当用户分配了 Microsoft 通话计划，但想要使用 SBC 路由某些调用）。 最常见的方案之一是调用第三方的 Pbx。  使用第三方 Pbx，除与连接到该 Pbx 的手机通话外，所有通话均使用 Microsoft 通话计划进行路由，但连接到第三方 Pbx 的电话的电话将转到 SBC，因此在企业网络中，而不是 PSTN。 

有关电话系统许可的详细信息，请参阅[使用 office 365](https://products.office.com/compare-all-microsoft-office-products?tab=2)和[Office 365 计划选项](https://technet.microsoft.com/library/office-365-plan-options.aspx)充分利用 office。 

有关电话系统许可的详细信息，请参阅[Microsoft 团队附加许可](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。 

## <a name="supported-end-points"></a>支持的终结点 

您可以用作终点：

- 任何团队客户端。 
- 常见的区域电话。 请参阅[设置 Microsoft 团队的通用区域电话许可证](https://docs.microsoft.com/microsoftteams/set-up-common-area-phones)。 注意使用直接路由设置普通的区域电话时，不需要呼叫计划许可证。
- Skype for Business 3PIP 手机。 请参阅[Microsoft 团队的 Skype for business 电话（3PIP）支持](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Skype-for-Business-phones-3PIP-support-with-Microsoft-Teams/ba-p/789351)


## <a name="sbc-domain-names"></a>SBC 域名称

SBC 域名必须来自租户域中注册的一个名称。 不能将\*onmicrosoft.com 租户用于 SBC 的 FQDN 名称。

下表显示为租户注册的 DNS 名称的示例、该名称是否可以用作 SBC 的 FQDN 以及有效 FQDN 名称的示例：

|**DNS 名称**|**可用于 SBC FQDN**|**FQDN 名称的示例**|
|:--- |:--- |:--- |
contoso.com|是|**有效的名称：**<br/>sbc1.contoso.com<br/>ssbcs15.contoso.com<br/>europe.contoso.com|
|contoso.onmicrosoft.com|否|SBC 名称不支持使用 * onmicrosoft.com 域

假设您要使用新域名。 例如，你的租户已将 contoso.com 用作你的租户中注册的域名，并且你希望使用 sbc1.sip.contoso.com。 在你可以将 SBC 与 name sbc1.sip.contoso.com 配对之前，必须在租户中的域中注册域名 sip.contoso.com。 如果你在注册域名之前尝试将 SBC 与 sbc1.sip.contoso.com 配对，你将收到以下错误： "无法使用" sbc1.sip.contoso.com "域，因为它不是为此租户配置的。"
添加域名后，你还需要使用 UPN user@sip.contoso.com 创建用户并分配团队许可证。 在将域名添加到租户域之后，可能需要长达24小时才能完全预配域名，并创建一个具有新名称的用户，并为该用户分配一个许可证。 

公司可能在一个租户中有多个 SIP 地址空间。 例如，公司可能已将 contoso.com 用作 SIP 地址空间，而 fabrikam.com 作为第二个 SIP 地址空间。 某些用户具有地址 user@contoso.com，而某些用户具有地址 user@fabrikam.com。 

SBC 仅需要一个 FQDN，并且可以通过配对的租户中的任何地址空间为用户服务。 例如，具有名称 sbc1.contoso.com 的 SBC 可以接收和发送具有地址 user@contoso.com 和 user@fabrikam.com 的用户的 PSTN 流量，只要这些 SIP 地址空间在同一租户中注册。  

## <a name="public-trusted-certificate-for-the-sbc"></a>适用于 SBC 的公共受信任证书

Microsoft 建议你通过生成证书签名请求（CSR）来请求 SBC 的证书。 有关为 SBC 生成 CSR 的特定说明，请参阅由 SBC 供应商提供的互连说明或文档。 

  > [!NOTE]
  > 大多数证书颁发机构（Ca）要求私钥大小至少为2048。 在生成 CSR 时请记住这一点。

证书需要在 "主题"、"公用名" 或 "使用者备用名称" 字段中具有 SBC FQDN。

或者，直接路由支持 SAN 中的通配符，并且通配符需要符合 TLS 上的标准[RFC HTTP](https://tools.ietf.org/html/rfc2818#section-3.1)。 SAN 中将使用\*contoso.com，这将与 SBC FQDN sbc.contoso.com 相匹配，但与 sbc.test.contoso.com 不匹配。

证书需要由以下根证书颁发机构之一生成：

- AffirmTrust
- AddTrust 外部 CA 根
- Baltimore CyberTrust Root
- Buypass
- Cybertrust
- 第3类公共主证书颁发机构
- Comodo 安全根 CA
- 德国 Telekom 
- DigiCert 全局根 CA
- DigiCert 高确定性 EV 根 CA
- Entrust
- GlobalSign
- 转到 Daddy
- GeoTrust
- Verisign，Inc。 
- Starfield 
- 适用于 Microsoft 的 Symantec 企业版移动根 
- SwissSign
- Thawte 时间戳 CA
- Trustwave
- TeliaSonera 
- T 位系统国际 GmbH （德国 Telekom）
- QuoVadis

Microsoft 正在努力根据客户请求添加其他认证机构。 

## <a name="sip-signaling-fqdns"></a>SIP 信号： Fqdn 

直接路由在以下 Office 365 环境中提供：
- Office 365
- Office 365 GCC
- Office 365 GCC 高
- Office 365 DoD

了解有关[Office 365 和美国政府环境](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government)（如 GCC、gcc 高级版和 DoD）的详细信息。

### <a name="office-365-and-office-365-gcc-environments"></a>Office 365 和 Office 365 GCC 环境

直接路由的连接点是以下三个 Fqdn：

- **sip.pstnhub.microsoft.com** -必须首先尝试全局 FQDN。 当 SBC 发送一个请求来解析此名称时，Microsoft Azure DNS 服务器将返回指向分配给 SBC 的主 Azure 数据中心的 IP 地址。 该作业基于数据中心的性能指标和与 SBC 的地理位置的接近度。 返回的 IP 地址对应于主 FQDN。
- **sip2.pstnhub.microsoft.com** -辅助 FQDN-地理位置映射到第二个优先级区域。
- **sip3.pstnhub.microsoft.com** -第三方 FQDN-地理位置映射到第三个优先级区域。

按顺序放置这三个 Fqdn 需要：

- 提供最佳体验（加载时间最少且最接近通过查询第一个 FQDN 分配的 SBC 数据中心）。
- 当从 SBC 建立连接到遇到暂时性问题的数据中心时，请提供故障转移。 有关详细信息，请参阅下面的[故障转移机制](#failover-mechanism-for-sip-signaling)。  

Fqdn （sip.pstnhub.microsoft.com、sip2.pstnhub.microsoft.com 和 sip3.pstnhub.microsoft.com）将解析为以下 IP 地址之一：

- 52.114.148.0
- 52.114.132.46 
- 52.114.75.24 
- 52.114.76.76 
- 52.114.7.24 
- 52.114.14.70

您需要在防火墙中打开所有这些 IP 地址的端口，以允许传入和传出通信发送和接收来自地址的发送信号。  如果你的防火墙支持 DNS 名称，FQDN sip-all.pstnhub.microsoft.com 将解析为所有这些 IP 地址。 


### <a name="office-365-gcc-dod-environment"></a>Office 365 GCC DoD 环境

直接路由的连接点是以下 FQDN：

**sip.pstnhub.dod.teams.microsoft.us** -全局 FQDN。 由于 Office 365 DoD 环境仅存在于美国数据中心，因此没有第二个和第三个 Fqdn。

FQDN sip.pstnhub.dod.teams.microsoft.us 将解析为下列 IP 地址之一：

- 52.127.64.33
- 52.127.68.34

您需要在防火墙中打开所有这些 IP 地址的端口，以允许传入和传出通信发送和接收来自地址的发送信号。  如果你的防火墙支持 DNS 名称，FQDN sip.pstnhub.dod.teams.microsoft.us 将解析为所有这些 IP 地址。 

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC 高环境

直接路由的连接点是以下 FQDN：

**sip.pstnhub.gov.teams.microsoft.us** -全局 FQDN。 由于 GCC 的高环境仅存在于美国数据中心，因此没有第二个和第三个 Fqdn。

FQDN sip.pstnhub.gov.teams.microsoft.us 将解析为下列 IP 地址之一：

- 52.127.88.59
- 52.127.92.64

您需要在防火墙中打开所有这些 IP 地址的端口，以允许传入和传出通信发送和接收来自地址的发送信号。  如果你的防火墙支持 DNS 名称，FQDN sip.pstnhub.gov.teams.microsoft.us 将解析为所有这些 IP 地址。 

## <a name="sip-signaling-ports"></a>SIP 信号：端口

对于 Office 365 环境，您必须使用以下端口，即提供直接路由：
- Office 365
- Office 365 GCC
- Office 365 GCC 高
- Office 365 DoD

|**流量**|**从**|**到**|**源端口**|**目标端口**|
|:--- |:--- |:--- |:--- |:--- |
|SIP/TLS|SIP 代理|SBC|1024-65535|在 SBC 上定义（对于 Office 365，必须使用仅限适用于 Office 的 GCC 5061 和5062）|
SIP/TLS|SBC|SIP 代理|在 SBC 上定义|5061|
||||||

### <a name="failover-mechanism-for-sip-signaling"></a>SIP 信号的故障转移机制

SBC 进行 DNS 查询来解析 sip.pstnhub.microsoft.com。 根据 SBC 位置和数据中心性能指标，选择主数据中心。 如果主数据中心遇到问题，则 SBC 将尝试可解析为第二个分配的数据中心的 sip2.pstnhub.microsoft.com，并且在这种情况下，在两个区域中的数据中心不可用时，SBC 将重试最后一个 FQDN （sip3.pstnhub.microsoft.com），它提供第三数据中心 IP。

下表总结了主数据中心、辅助数据中心和第三数据中心之间的关系：

|**如果主数据中心是**|**EMEA**|**NOAM**|**地区**|
|:--- |:--- |:--- |:--- |
|辅助数据中心（sip2.pstnhub.microsoft.com）|我们|各|我们|
|第三数据中心（sip3.pstnhub.microsoft.com）|地区|地区|各|
|||||

## <a name="media-traffic-port-ranges"></a>媒体流量：端口范围
请注意，如果你想要在不使用媒体绕过的情况下部署直接路由，请应用以下要求。 有关媒体绕过的防火墙要求，请参阅[使用直接路由规划媒体旁路](https://docs.microsoft.com/microsoftteams/direct-routing-plan-media-bypass)。



媒体流量从 Microsoft 云中单独的服务流出。 媒体流量的 IP 范围如下所示。

### <a name="office-365-and-office-365-gcc-environments"></a>Office 365 和 Office 365 GCC 环境

- 52.112.0.0/14 （从52.112.0.1 到52.115.255.254 的 IP 地址）。

### <a name="office-365-gcc-dod-environment"></a>Office 365 GCC DoD 环境

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC 高环境

- 52.127.88.0/21

### <a name="port-range-applicable-to-all-environments"></a>端口范围（适用于所有环境）
下表显示了媒体处理器的端口范围： 

|**流量**|**从**|**到**|**源端口**|**目标端口**|
|:--- |:--- |:--- |:--- |:--- |
|UDP/SRTP|媒体处理器|SBC|49152-53247|在 SBC 上定义|
|UDP/SRTP|SBC|媒体处理器|在 SBC 上定义|49152-53247|

  > [!NOTE]
  > Microsoft 建议在 SBC 上对每个并发调用至少有两个端口。


## <a name="media-traffic-media-processors-geography"></a>媒体流量：媒体处理者地理位置

媒体流量通过名为媒体处理器的组件流出。 媒体处理器与 SIP 代理放在同一数据中心。 此外，还有其他媒体处理器来优化媒体流。 例如，我们目前在澳大利亚（通过新加坡或香港特别行政区）提供 SIP 代理组件，但我们在澳大利亚本地有媒体处理器。 对媒体处理者的需求取决于我们通过发送远距离（例如从澳大利亚到新加坡或香港特别行政区）进行的延迟。 虽然从澳大利亚到香港或新加坡的流量示例中的延迟是为 SIP 流量保持良好的通话质量，但对于实时媒体流量而言，它是不可接受的。

媒体处理器的位置：

SIP 代理和媒体处理器组件部署的位置：
- 我们（美国西部和华南东数据中心的两个）
- 欧洲（阿姆斯特丹和都柏林数据中心）
- 亚洲（新加坡和香港特别行政区）

仅部署媒体处理器的位置（SIP 通过上面列出的最接近的数据中心流）：
- 日本（JP 和西部数据中心）
- 澳大利亚（AU 东和西数据中心）




## <a name="media-traffic-codecs"></a>媒体流量：编解码器

### <a name="leg-between-sbc-and-cloud-media-processor-or-microsoft-teams-client"></a>SBC 和云媒体处理器或 Microsoft 团队客户端之间的腿。
适用于媒体旁路情况和非绕过情况。

会话边界控制器和云媒体处理器（没有媒体旁路）或团队客户端与 SBC 之间（如果启用了媒体旁路）之间的直接路由接口，可以使用以下编解码器：

- 非媒体旁路（SBC 到云媒体处理器）：绞丝、711、722、G 729
- 媒体绕过（SBC 到团队客户端）：绞丝、711、722、729

你可以通过从优惠中排除不需要的编解码器来强制使用会话边界控制器上的特定编解码器。

### <a name="leg-between-microsoft-teams-client-and-cloud-media-processor"></a>Microsoft 团队客户端与云媒体处理器之间的腿
仅适用于非媒体旁路大小写。 通过媒体绕过，媒体将直接在团队客户端和 SBC 之间流动。

在云媒体处理器和 Microsoft 团队客户端之间的腿处使用的是722或。 此段腿的编解码器选项基于 Microsoft 算法，这些算法考虑多个参数。 


## <a name="supported-session-border-controllers-sbcs"></a>支持的会话边框控制器（SBCs）

Microsoft 仅支持经认证的 SBCs 与直接路由配对。 由于企业语音对企业至关重要，Microsoft 使用所选 SBCs 运行大量测试，并与 SBC 供应商一起使用，确保两个系统兼容。 

已验证的设备列为团队直接路由的认证。 认证的设备保证能够在所有情况下正常工作。 

有关支持的 SBCs 的详细信息，请参阅[为直接路由认证的会话边框控制器列表](direct-routing-border-controllers.md)。

 
## <a name="see-also"></a>另请参阅

[配置直接路由](direct-routing-configure.md)
