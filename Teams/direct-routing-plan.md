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
- highpri
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.custom: seo-marvel-mar2020
description: 了解Microsoft直接路由如何使你能够将受支持的客户提供的会话边界控制器 (SBC) 连接到电话系统。
ms.openlocfilehash: 811115c23d88ff3ce1b7fa6af8f8757afb33fecf
ms.sourcegitcommit: 0d97dc6616b3d633564409e39c08311af1522705
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/14/2022
ms.locfileid: "69392322"
---
# <a name="plan-direct-routing"></a>规划直接路由

> [!Tip]
> 观看以下课程，了解直接路由的优势、如何规划以及部署方式：[Microsoft Teams 中的直接路由](https://aka.ms/teams-direct-routing)

直接路由允许将受支持的客户提供的会话边界控制器 (SBC) 连接到电话系统。 使用此功能，可以配置本地公用电话交换网络 (PSTN) 与 Microsoft Teams 客户端的连接，如下图所示： 

![显示本地 PSTN 连接的配置的关系图。](media/PlanDirectRouting1-PSTNwithTeams.png "使用 Microsoft Teams 客户端配置本地 PSTN 连接")

  > [!NOTE]
  > Skype for Business Online 还允许配对客户提供的 SBC，但这需要在 SBC 和 Microsoft 云之间进行本地Skype for Business Server部署或特殊版本的Skype for Business（称为云连接器）。 此方案称为混合语音。 相比之下，直接路由允许在支持的 SBC 和 Microsoft 云之间建立直接连接。

> [!Important]
> 云连接器版本将于 2021 年 7 月 31 日停用，Skype for Business Online。 组织升级到 Teams 后，了解如何使用 [直接路由](direct-routing-landing-page.md)将本地电话网络连接到 Teams。 

使用直接路由，可以将 SBC 连接到几乎任何电话中继或与第三方 PSTN 设备互连。 使用直接路由可以： 

- 将几乎任何 PSTN 中继与电话系统配合使用。 

- 配置客户拥有的电话设备之间的互操作性，例如第三方专用分支交换 (PBX) 、模拟设备和 Teams。

Microsoft还提供全云语音解决方案，例如通话套餐。 但是，在以下的情况下，混合语音解决方案可能最适合组织： 

- Microsoft通话套餐在你的国家/地区不可用。 

- 你的组织需要连接到第三方模拟设备、呼叫中心等。 

- 你的组织与 PSTN 运营商签订了现有合同。

直接路由还支持具有Microsoft通话套餐附加许可证的用户。 有关详细信息，请参阅 [电话系统和通话套餐](calling-plan-landing-page.md)。 

使用直接路由时，当用户参加计划的会议时，拨入号码由 Microsoft 音频会议服务提供，这需要适当的许可。  拨出时，Microsoft音频会议服务使用在线呼叫功能发出呼叫，这需要适当的许可。  (请注意，如果用户没有Microsoft音频会议许可证，则呼叫通过直接路由路由。) 有关详细信息，请参阅 [Teams 联机会议](https://www.microsoft.com/en-us/microsoft-teams/online-meetings)。 
 
规划直接路由的部署是成功实现的关键。 本文介绍基础结构和许可要求，并提供有关 SBC 连接的信息： 

- [基础结构要求](#infrastructure-requirements)
- [许可和其他要求](#licensing-and-other-requirements)
- [SBC 域名](#sbc-domain-names)
- [SBC 的公共受信任证书](#public-trusted-certificate-for-the-sbc)
- [SIP 信号：FQDN](#sip-signaling-fqdns)
- [SIP 信令：端口](#sip-signaling-ports)
- [媒体流量：端口范围](#media-traffic-port-ranges)
- [支持的会话边界控制器 (SBC) ](#supported-session-border-controllers-sbcs)

有关配置直接路由的详细信息，请参阅 [配置直接路由](direct-routing-configure.md)。

## <a name="infrastructure-requirements"></a>基础结构要求
下表列出了部署直接路由时支持的 SBC、域和其他网络连接要求的基础结构要求：  

|基础结构要求|你需要以下项|
|:--- |:--- |
|会话边界控制器 (SBC) |支持的 SBC。 有关详细信息，请参阅 [支持的 SBC](#supported-session-border-controllers-sbcs)。|
|连接到 SBC 的电话中继|连接到 SBC 的一个或多个电话中继。 一端是 SBC 通过直接路由连接到电话系统。 SBC 还可以连接到第三方电话实体，例如 PBX、模拟电话适配器等。 连接到 SBC 的任何 PSTN 连接选项都将正常工作。  (有关配置 SBC 的 PSTN 中继，请参阅 SBC 供应商或中继提供商。) |
|Microsoft 365 组织|Microsoft 365 组织，用于托管Microsoft Teams 用户，以及配置和连接到 SBC。|
|用户注册机构|用户必须驻留在 Microsoft 365 中。<br/>如果您的公司具有与 Microsoft 365 混合连接的本地Skype for Business或 Lync 环境，则无法在 Teams 中为本地用户启用语音。<br/><br/>若要检查用户的注册机构，请使用以下 Skype for Business Online PowerShell cmdlet：<br/><code>Get-CsOnlineUser -Identity \<user> \| fl HostingProvider</code> <br/><br/>cmdlet 的输出应显示：<br/><code>HostingProvider : sipfed.online.lync.com</code>|
|域|添加到 Microsoft 365 或 Office 365 组织的一个或多个域。<br/><br/>请注意，不能使用为租户自动创建的默认域 \*.onmicrosoft.com。<br/><br/>若要查看域，可以使用以下 Skype for Business Online PowerShell cmdlet：<br/><code>Get-CsTenant \| fl Domains</code><br/><br/>有关域和 Microsoft 365 或 Office 365 组织的详细信息，请参阅[域常见问题解答](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a)。|
|SBC 的公共 IP 地址|可用于连接到 SBC 的公共 IP 地址。 根据 SBC 的类型，SBC 可以使用 NAT。|
|SBC 的完全限定域名 (FQDN) |SBC 的 FQDN，其中 FQDN 的域部分是 Microsoft 365 或 Office 365 组织中的已注册域之一。 有关详细信息，请参阅 [SBC 域名](#sbc-domain-names)。|
|SBC 的公共 DNS 条目 |将 SBC FQDN 映射到公共 IP 地址的公共 DNS 条目。 |
|SBC 的公共受信任证书 |SBC 的证书，用于与直接路由的所有通信。 有关详细信息，请参阅 [SBC 的公共受信任证书](#public-trusted-certificate-for-the-sbc)。|
|直接路由的连接点 |直接路由的连接点为以下三个 FQDN：<br/><br/>`sip.pstnhub.microsoft.com` – 必须首先尝试全局 FQDN。<br/>`sip2.pstnhub.microsoft.com` – 辅助 FQDN，在地理上映射到第二个优先区域。<br/>`sip3.pstnhub.microsoft.com` – 第三级 FQDN，在地理上映射到第三优先区域。<br/><br/>有关配置要求的信息，请参阅 [SIP 信令：FQDN](#sip-signaling-fqdns)。|
|直接路由媒体的防火墙 IP 地址和端口 |SBC 与云中的以下服务通信：<br/><br/>SIP 代理，用于处理信号<br/>媒体处理器，用于处理媒体 -除非媒体旁路处于打开状态<br/><br/>这两个服务在 Microsoft Cloud 中具有单独的 IP 地址，本文档稍后将对此进行介绍。<br/><br/>有关详细信息，请参阅 [URL 和 IP 地址范围](/office365/enterprise/urls-and-ip-address-ranges)中的 [Microsoft Teams 部分](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)。 |
|媒体传输配置文件|TCP/RTP/SAVP <br/>UDP/RTP/SAVP|
Microsoft Teams 媒体的防火墙 IP 地址和端口 |有关详细信息，请参阅 [URL 和 IP 地址范围](/office365/enterprise/urls-and-ip-address-ranges)。 |
|||

## <a name="licensing-and-other-requirements"></a>许可和其他要求 

直接路由的用户必须在 Microsoft 365 中分配以下许可证： 

- Microsoft电话系统
- Microsoft Teams + Skype for Business计划 2（如果包含在许可中）
- Microsoft音频会议 (请阅读以下说明和段落，了解有关何时需要此许可证的具体示例。) 

> [!NOTE]
> Skype for Business计划不应从包含该计划的任何许可协议中删除。 
> 
> [!IMPORTANT]
> GCC High 和 DoD 用户应禁用 G5 中包含的任何音频会议许可，并等待启用任何音频会议，直到完全配置直接路由。 在启用音频会议许可证之前，用户应配置拨入电话号码和工作拨号盘。 有关更多详细信息 [，请参阅具有 GCC High 和 DoD 的直接路由的音频会议](./audio-conferencing-with-direct-routing-for-gcch-and-dod.md) 。


> [!IMPORTANT]
>  如果要通过拨出外部参与者或提供拨入号码将外部参与者添加到已安排的会议，则需要音频会议许可证。
> 对于 GCC High 和 DoD，请勿为 G5 用户分配音频会议许可证。 对于 G3 用户，在完全配置直接路由并且用户具有有效的拨号盘之前，不要分配音频会议许可证。


### <a name="ad-hoc-call-escalation-and-audio-conferencing-license"></a>临时呼叫升级和音频会议许可证

Teams 用户可以启动一对一的 Teams 到 PSTN 或 Teams 到 Teams 呼叫，并向其添加 PSTN 参与者。 此方案称为临时会议。 呼叫采用的路径取决于升级呼叫的用户是否分配了Microsoft音频会议许可证：

- **如果升级呼叫的 Teams 用户分配了Microsoft音频会议许可证**，则升级将通过Microsoft音频会议服务进行。 受邀加入现有呼叫的远程 PSTN 参与者会收到有关传入呼叫的通知，并看到分配给发起升级的 Teams 用户的Microsoft网桥号码。

- **如果升级呼叫的 Teams 用户未分配Microsoft音频会议许可证**，则升级将通过连接到直接路由接口的会话边界控制器进行。 受邀参加呼叫的远程 PSTN 参与者会收到有关传入呼叫的通知，并查看发起升级的 Teams 用户的号码。 用于升级的特定 SBC 由用户的路由策略定义。 

必须确保以下各项：
 
- CsOnlineVoiceRoutingPolicy 分配给用户。

- 在租户级别为 Microsoft Teams 启用“允许专用呼叫”。

直接路由还支持获得Microsoft通话套餐许可的用户。 具有通话套餐的电话系统可以使用直接路由接口路由某些呼叫。 但是，用户的电话号码必须在线获取或移植到Microsoft。  

为同一用户混合通话套餐和直接路由连接是可选的，但可能很有用。 例如，向用户分配了Microsoft通话套餐，但想要使用 SBC 路由某些呼叫时。 最常见的方案之一是调用第三方 PBX。  对于第三方 PBX，所有呼叫（连接到该 PBX 的电话除外）都使用Microsoft呼叫计划进行路由，但对连接到第三方 PBX 的电话的呼叫将转到 SBC，因此保留在企业网络内，而不是 PSTN。

有关电话系统许可的详细信息，请参阅[充分利用 Office](https://products.office.com/compare-all-microsoft-office-products?tab=2) 和[计划选项](/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options)和 [Microsoft Teams 附加许可](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。

## <a name="supported-end-points"></a>支持的终结点

可以使用 作为终结点：

- 任何 Teams 客户端。

- 公用区域电话。 请参阅[为 Microsoft Teams 设置公用区域电话](./set-up-common-area-phones.md)。 使用直接路由设置公用区域电话时，不需要通话套餐许可证。

- Skype for Business 3PIP 电话。 请参阅[使用 Microsoft Teams (3PIP) 支持的Skype for Business手机](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Skype-for-Business-phones-3PIP-support-with-Microsoft-Teams/ba-p/789351)

## <a name="sbc-domain-names"></a>SBC 域名

SBC 域名必须来自租户的“域”中注册的名称之一。 不能将 \*.onmicrosoft.com 租户用于 SBC 的 FQDN 名称。

下表显示了为租户注册的 DNS 名称的示例、该名称是否可以用作 SBC 的 FQDN 以及有效 FQDN 名称的示例：

|DNS 名称|可用于 SBC FQDN|FQDN 名称的示例|
|:--- |:--- |:--- |
contoso.com|是|**有效名称：**<br/>sbc1.contoso.com<br/>ssbcs15.contoso.com<br/>europe.contoso.com|
|contoso.onmicrosoft.com|否|SBC 名称不支持使用 *.onmicrosoft.com 域

假设要使用新的域名。 例如，租户 contoso.com 为在租户中注册的域名，并且你希望使用 sbc1.sip.contoso.com。 在将 SBC 与名称 sbc1.sip.contoso.com 配对之前，必须在租户的“域”中注册域名 sip.contoso.com。 如果在注册域名之前尝试将 SBC 与 sbc1.sip.contoso.com 配对，将收到以下错误：“无法使用”sbc1.sip.contoso.com“域，因为它未为此租户配置。

添加域名后，还需要使用 UPN user@sip.contoso.com 创建用户并分配 Teams 许可证。 将域名添加到租户的域后，最多可能需要 24 小时才能完全预配该域名，创建具有新名称的用户，并将许可证分配给该用户。

一家公司可能在一个租户中具有多个 SIP 地址空间。 例如，公司可能将 contoso.com 作为 SIP 地址空间，fabrikam.com 作为第二个 SIP 地址空间。 某些用户具有地址 user@contoso.com，某些用户具有地址 user@fabrikam.com。 

SBC 只需要一个 FQDN，并且可以从配对租户中的任何地址空间为用户提供服务。 例如，名称为 sbc1.contoso.com 的 SBC 可以接收和发送地址为 user@contoso.com 和 user@fabrikam.com 的用户的 PSTN 流量，前提是这些 SIP 地址空间注册在同一租户中。  

 > [!NOTE]
 > Azure 通信服务直接路由中的 SBC FQDN 必须与 Teams 直接路由中的 SBC FQDN 不同。
  
## <a name="public-trusted-certificate-for-the-sbc"></a>SBC 的公共受信任证书

Microsoft建议通过 (CSR) 生成证书签名请求来请求 SBC 的证书。 有关为 SBC 生成 CSR 的具体说明，请参阅 SBC 供应商提供的互连说明或文档。

> [!NOTE]
> 大多数证书颁发机构 (CA) 要求私钥大小至少为 2048。 生成 CSR 时，请记住这一点。

证书需要将 SBC FQDN 用作 CN)  (公用名，或将使用者可选名称 (SAN) 字段。

或者，直接路由支持 CN 和/或 SAN 中的通配符，并且通配符需要符合标准 [RFC HTTP Over TLS](https://tools.ietf.org/html/rfc2818#section-3.1)。

例如，使用 \*与 SBC FQDN sbc.contoso.com 匹配但与 sbc.test.contoso.com 不匹配的 .contoso.com。

直接路由 SIP 接口将仅信任证书颁发机构 (CA 签名的证书，) 属于Microsoft受信任的根证书计划的一部分。 请确保 SBC 证书由属于程序的 CA 签名，并且证书的扩展密钥用法 (EKU) 扩展包括服务器身份验证。
了解详细信息：[计划要求 - Microsoft受信任的根程序](/security/trusted-root/program-requirements)
  
[包含的 CA 证书列表](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)
  
 对于 Office 365 GCCH 和 DoD 环境中的直接路由，证书需要由以下根证书颁发机构之一生成：

- DigiCert 全局根 CA
- DigiCert 高保障 EV 根 CA

> [!NOTE]
> 如果为 SBC 上的 Teams 连接启用了相互 TLS (MTLS) 支持，则必须在 Teams TLS 上下文的 SBC 受信任根存储中安装 Baltimore CyberTrust Root 和 DigiCert 全局根 G2 证书。  (这是因为Microsoft服务证书使用这两个根证书之一。) 若要下载这些根证书，请参阅[Office 365加密链](/microsoft-365/compliance/encryption-office-365-certificate-chains)。 有关详细信息，请参阅 [Office TLS 证书更改](/microsoft-365/compliance/encryption-office-365-tls-certificates-changes)。

## <a name="sip-signaling-fqdns"></a>SIP 信号：FQDN

直接路由在以下环境中提供：

- Microsoft 365 或 Office 365
- Office 365 GCC
- Office 365 GCC High
- Office 365 DoD

详细了解[Office 365和美国政府环境](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government)，例如 GCC、GCC High 和 DoD。

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Microsoft 365、Office 365 和 Office 365 GCC 环境

直接路由的连接点为以下三个 FQDN：

- **必须** 首先尝试 sip.pstnhub.microsoft.com 全局 FQDN。 当 SBC 发送解析此名称的请求时，Microsoft Azure DNS 服务器返回一个 IP 地址，该地址指向分配给 SBC 的主 Azure 数据中心。 分配基于数据中心的性能指标和与 SBC 的地理邻近度。 返回的 IP 地址对应于主 FQDN。

- **sip2.pstnhub.microsoft.com** – 辅助 FQDN – 在地理上映射到第二个优先区域。

- **sip3.pstnhub.microsoft.com** - 第三级 FQDN - 在地理上映射到第三个优先区域。

按顺序放置这三个 FQDN 需要：

- 通过查询第一个 FQDN) ， (负载较低且最接近分配的 SBC 数据中心提供最佳体验。

- 从 SBC 建立到遇到临时问题的数据中心的连接时，提供故障转移。 有关详细信息，请参阅下面的 [故障转移机制](#failover-mechanism-for-sip-signaling) 。  

FQDN（sip.pstnhub.microsoft.com、sip2.pstnhub.microsoft.com 和 sip3.pstnhub.microsoft.com）将解析为以下子网中的 IP 地址：

- 52.112.0.0/14
- 52.122.0.0/15

需要在防火墙中为所有这些 IP 地址范围打开端口，以允许传入和传出地址的传入和传出流量以发出信号。

### <a name="office-gcc-dod-environment"></a>Office GCC DoD 环境

直接路由的连接点为以下 FQDN：

**sip.pstnhub.dod.teams.microsoft.us** – 全局 FQDN。 由于Office 365 DoD 环境仅存在于美国数据中心，因此没有辅助和三级 FQDN。

FQDN sip.pstnhub.dod.teams.microsoft.us 将解析为以下子网中的 IP 地址：

- 52.127.64.0/21

需要在防火墙中为所有这些 IP 地址打开端口，以允许传入和传出地址的传入和传出流量，以便发出信号。

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC 高环境

直接路由的连接点为以下 FQDN：

**sip.pstnhub.gov.teams.microsoft.us** – 全局 FQDN。 由于 GCC High 环境仅存在于美国数据中心，因此没有二级和第三级 FQDN。

FQDN sip.pstnhub.gov.teams.microsoft.us 将解析为以下子网中的 IP 地址：

- 52.127.88.0/21

需要在防火墙中为所有这些 IP 地址打开端口，以允许传入和传出地址的传入和传出流量，以便发出信号。

## <a name="sip-signaling-ports"></a>SIP 信令：端口

对于提供直接路由的 Microsoft 365 或 Office 365 环境，必须使用以下端口：

- Microsoft 365 或 Office 365
- Office 365 GCC
- Office 365 GCC High
- Office 365 DoD

|交通|从|到|源端口|目标端口|
|:--- |:--- |:--- |:--- |:--- |
|SIP/TLS|SIP 代理|Sbc|1024 – 65535|在 SBC (上定义的对于 Office 365 GCC High/DoD，必须仅使用端口 5061) |
SIP/TLS|Sbc|SIP 代理|在 SBC 上定义|5061|
||||||

### <a name="failover-mechanism-for-sip-signaling"></a>SIP 信号的故障转移机制

SBC 会发出 DNS 查询来解析 sip.pstnhub.microsoft.com。 根据 SBC 位置和数据中心性能指标，选择主数据中心。 如果主数据中心遇到问题，SBC 将尝试 sip2.pstnhub.microsoft.com，该 sip2.pstnhub.microsoft.com 解析为第二个分配的数据中心，在极少数情况下，两个区域中的数据中心不可用，SBC 会重试最后一个 FQDN (sip3.pstnhub.microsoft.com) ，后者提供第三级数据中心 IP。

下表汇总了主要数据中心、辅助数据中心和三级数据中心之间的关系：

|如果主数据中心为|EMEA|NOAM|亚洲|
|:--- |:--- |:--- |:--- |
|辅助数据中心 (sip2.pstnhub.microsoft.com) |我们|欧盟|我们|
|三级数据中心 (sip3.pstnhub.microsoft.com) |亚洲|亚洲|欧盟|
|||||

## <a name="media-traffic-port-ranges"></a>媒体流量：端口范围

请注意，如果要部署没有媒体旁路的直接路由，则以下要求适用。 有关媒体旁路的防火墙要求，请参阅 [使用直接路由规划媒体旁路](./direct-routing-plan-media-bypass.md)。

媒体流量流入和流出Microsoft云中的单独服务。 媒体流量的 IP 地址范围如下所示。

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Microsoft 365、Office 365 和 Office 365 GCC 环境

- 52.112.0.0/14 (IP 地址从 52.112.0.1 到 52.115.255.254) 。
- 52.120.0.0/14 (IP 地址从 52.120.0.1 到 52.123.255.254) 。

### <a name="office-365-dod-environment"></a>Office 365 DoD 环境

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC 高环境

- 52.127.88.0/21

### <a name="port-range-applicable-to-all-environments"></a>端口范围 (适用于所有环境) 

下表显示了媒体处理器的端口范围：

|交通|从|到|源端口|目标端口|
|:--- |:--- |:--- |:--- |:--- |
|UDP/SRTP|媒体处理器|Sbc|3478-3481 和 49152 – 53247|在 SBC 上定义|
|UDP/SRTP|Sbc|媒体处理器|在 SBC 上定义|3478-3481 和 49152 – 53247|

  > [!NOTE]
  > Microsoft建议 SBC 上每个并发调用至少两个端口。

## <a name="media-traffic-media-processors-geography"></a>媒体流量：媒体处理器地理位置

媒体流量通过称为媒体处理器的组件流动。 媒体处理器与 SIP 代理位于同一数据中心：

- NOAM (美国中南部，两个位于美国西部和美国东部数据中心) 
- 欧洲 (英国南部、法国中部、阿姆斯特丹和都柏林数据中心) 
- 亚洲 (新加坡数据中心) 
- 日本 (JP 东部和西部数据中心) 
- 澳大利亚 (AU 东部和东南部数据中心) 
- 拉丁美洲 (巴西南部) 

## <a name="media-traffic-codecs"></a>媒体流量：编解码器

### <a name="leg-between-sbc-and-cloud-media-processor-or-microsoft-teams-client"></a>SBC 与云媒体处理器或 Microsoft Teams 客户端之间的段

适用于媒体旁路案例和非旁路案例。

会话边界控制器和云媒体处理器之间的直接路由接口 (没有媒体旁路) ，或者 Teams 客户端与 SBC 之间的直接路由接口 (如果启用了媒体旁路) 可以使用以下编解码器：

- 非媒体旁路 (SBC 到云媒体处理器) ：SILK、G.711、G.722、G.729
- 媒体旁路 (SBC 到 Teams 客户端) ：SILK、G.711、G.722、G.729

可以通过从产品/服务中排除不需要的编解码器来强制在会话边界控制器上使用特定编解码器。

### <a name="leg-between-microsoft-teams-client-and-cloud-media-processor"></a>Microsoft Teams 客户端和云媒体处理器之间的腿

仅适用于非媒体旁路情况。 使用媒体旁路，媒体直接在 Teams 客户端和 SBC 之间流动。

在云媒体处理器和 Microsoft Teams 客户端之间的一端，使用 SILK 或 G.722。 此段上的编解码器选择基于Microsoft算法，这些算法考虑了多个参数。

  > [!NOTE]
  > 不支持媒体重新定位。 在直接路由呼叫期间，如果 SBC 向 Teams 直接路由发送新的媒体 IP，尽管它是在 SIP 信令中协商的，但媒体永远不会从 Teams 直接路由发送到新的 IP 地址。

## <a name="supported-session-border-controllers-sbcs"></a>支持的会话边界控制器 (SBC) 

Microsoft仅支持经过认证的 SBC 与直接路由配对。 由于企业语音对企业至关重要，因此Microsoft对所选 SBC 运行密集测试，并与 SBC 供应商合作，确保这两个系统兼容。

已验证的设备列为“Teams 直接路由认证”。 经过认证的设备保证适用于所有方案。

有关支持的 SBC 的详细信息，请参阅 [认证为直接路由的会话边界控制器](direct-routing-border-controllers.md)。

## <a name="support-boundaries"></a>支持边界

Microsoft 仅在与认证设备一起使用时支持具有直接路由的电话系统。 如果出现问题，必须先联系 SBC 供应商的客户支持。 如果需要，SBC 供应商将通过内部渠道将问题呈报给 Microsoft。 Microsoft 保留在非认证设备通过直接路由连接电话系统的情况下拒绝提供支持的权利。 如果 Microsoft 确定客户的直接路由问题与供应商的 SBC 设备有关，则客户需要重新联系 SBC 供应商以获得支持。

## <a name="see-also"></a>另请参阅

[配置直接路由](direct-routing-configure.md)
