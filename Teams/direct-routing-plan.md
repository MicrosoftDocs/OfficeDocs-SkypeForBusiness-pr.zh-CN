---
title: 规划直接路由
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 阅读本主题可了解如何 Microsoft 电话系统直接路由允许您将支持、 客户提供会话边界控制器 (SBC) 连接至 Microsoft 电话系统。
ms.openlocfilehash: 1749d5b26be6e3cc4c55bb9a90e47e637fc67230
ms.sourcegitcommit: 33966ebb9ca3d922d47aaa9b9e3a2ddd26c320ca
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "23848614"
---
# <a name="plan-direct-routing"></a>规划直接路由

Microsoft 电话系统直接路由允许您将支持、 客户提供会话边界控制器 (SBC) 连接至 Microsoft 电话系统。  使用此功能，例如，您可以配置内部部署 PSTN 连接使用的 Microsoft 团队客户端，如下图中所示： 

![显示内部部署 PSTN 连接的使用的 Microsoft 团队客户端的配置](media/PlanDirectRouting1-PSTNwithTeams.png)

  > [!NOTE]
  > Skype 业务 online 还允许您对客户提供的 SBC，但这需要在本地 Skype 业务服务器部署或业务，调用云连接器，在 SBC 和 Microsoft 云之间的 Skype 的特殊版本。 此方案中称为混合语音。 相比之下，直接路由允许直接连接支持的 SBC 和 Microsoft 云之间。 

使用直接路由时，可以将您的 SBC 连接到几乎任何电话中继或 interconnect 与第三方公共公用电话交换网 (PSTN) 设备。 直接路由使您能够： 

- 使用 Microsoft 电话系统的几乎任何 PSTN 中继。 
- 配置客户拥有电话设备，如第三方专用交换机 (PBX)、 模拟设备和 Microsoft 电话系统之间的互操作性。

Microsoft 还提供了一云语音解决方案，如调用规划。  但是，混合语音解决方案可能最适合贵组织如果： 

- 在您的国家/地区中不可用 Microsoft 调用规划。 
- 您的组织需要连接至第三方模拟设备、 呼叫中心，等等。 
- 贵组织拥有现有合同与 PSTN 运营商。

直接路由还支持 Microsoft 调用规划具有附加许可证的用户。 有关详细信息，请参阅[Office 365 中调用计划](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/what-are-calling-plans-in-office-365)和[授权和其他要求](#licensing-and-other-requirements)。 

使用直接路由时，当用户参与计划内会议，由 Microsoft 音频会议服务，这需要适当许可提供的电话拨入式号码。  拨号时, Microsoft 音频会议服务将放在呼叫使用联机呼叫功能，这需要适当许可。 （请注意，拨出不会路由通过直接路由）。有关详细信息，请参阅[与团队的联机会议](https://products.office.com/microsoft-teams/online-meeting-solutions)。 
 
规划部署的直接路由是关键成功实施。 本文介绍基础结构和许可要求，并提供有关 SBC 连接的信息： 

- [基础结构要求](#infrastructure-requirements)
- [许可和其他要求](#licensing-and-other-requirements)
- [SBC 域名](#sbc-domain-names)
- [SBC 的受信任的公共证书](#public-trusted-certificate-for-the-sbc)
- [SIP 信号： Fqdn 和防火墙端口](#sip-signaling-fqdns-and-firewall-ports)
- [媒体流量： 端口范围](#media-traffic-port-ranges)
- [支持的 Sbc](#supported-session-border-controllers-sbcs)

有关配置直接路由的详细信息，请参阅[配置直接路由](direct-routing-configure.md)。

## <a name="infrastructure-requirements"></a>基础结构要求
下表列出了支持的 SBCs、 域和其他网络连接要求部署直接路由的基础结构要求：  

|**基础结构要求**|**您需要以下**|
|:--- |:--- |
|会话边界控制器 (SBC)|支持的 SBC。 有关详细信息，请参阅[支持的 Sbc](#supported-session-border-controllers-sbcs)。|
|电话中继连接到的 SBC|一个或多个电话中继连接到 SBC。 另一端 SBC 连接到 Microsoft 电话系统通过直接路由。 SBC 还可以连接到第三方电话实体，如 Pbx，模拟电话适配器，依此类推。 连接到 SBC 任何 PSTN 连接选项起作用。 (注意： SBC 到 PSTN 中继的配置，请参阅 SBC 供应商或中继提供商。)|
|Office 365 租户|用于承载您的 Microsoft 团队的用户的配置和与 SBC 连接 Office 365 租户。|
|用户注册器|用户必须驻留在 Office 365 中。<br/>如果您的公司具有内部部署 Skype 混合连接到 Office 365 的业务或 Lync 环境，不能启用团队中的语音功能用户驻留在本地。<br/><br/>要检查用户的注册器，请使用以下 Skype 业务 Online PowerShell cmdlet:<br/><code>Get-CsOnlineUser -Identity \<user> \| fl HostingProvider</code> <br/><br/>应显示 cmdlet 的输出：<br/><code>HostingProvider : sipfed.online.lync.com</code>|
|域|添加到 Office 365 租户的一个或多个域。<br/><br/>**注意：** 不能使用默认域，*。 onmicrosoft.com，为您的租户自动创建的。<br/><br/>若要查看域，可用于以下 Skype 业务 Online PowerShell cmdlet:<br/><code>Get-CsTenant \| fl Domains</code><br/><br/>有关域和 Office 365 租户的详细信息，请参阅[域常见问题](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a)。|
|公共 IP 地址的 SBC|可用于连接到 SBC 公共 IP 地址。 基于类型的 SBC，SBC 可以使用 nat。|
|SBC 的完全限定的域名 (FQDN)|SBC，其中 FQDN 的域部分是其中一个 Office 365 租户中注册的域的 FQDN。 有关详细信息，请参阅[SBC 域名](#sbc-domain-names)。|
|SBC 的公共 DNS 条目 |映射到公共 IP 地址的 SBC FQDN 公共 DNS 条目。 |
|SBC 的受信任的公共证书 |SBC 用于直接路由中的所有通信的证书。 有关详细信息，请参阅[SBC 的受信任的公共证书](#public-trusted-certificate-for-the-sbc)。|
|直接路由的连接点 |直接路由的连接点是具有以下三个 Fqdn:<br/><br/>`sip.pstnhub.microsoft.com`– 必须首先尝试全局 FQDN。<br/>`sip2.pstnhub.microsoft.com`– 辅助 FQDN，地理位置映射到第二个优先级区域。<br/>`sip3.pstnhub.microsoft.com`– 第三级 FQDN，地理位置映射到第三个优先级区域。<br/><br/>有关配置要求的信息，请参阅[SIP 信号： Fqdn 和防火墙端口](#sip-signaling-fqdns-and-firewall-ports)。|
|防火墙的 IP 地址和直接路由的媒体端口 |SBC 对下列服务在云中进行通信：<br/><br/>SIP 代理，处理的信号<br/>媒体处理器，处理媒体-除媒体绕过位于<br/><br/>这两个服务具有单独的 IP 地址中 Microsoft 云，本文档后面所述。<br/><br/>有关详细信息，请参阅[Office 365 Url 和 IP 地址范围](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2)中的[Microsoft 团队部分](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams)。 |
|媒体传输配置文件|TCP/RTP/SAVP <br/>UDP/RTP/SAVP|
防火墙的 IP 地址和端口的 Microsoft 团队媒体 |有关详细信息，请参阅[Office 365 Url 和 IP 地址范围](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2)。 |
|||

## <a name="licensing-and-other-requirements"></a>许可和其他要求 

直接路由中的用户必须具有以下许可证分配 Office 365 中： 

- Microsoft 电话系统 
- Microsoft Teams 
- Microsoft 音频会议 

需要向计划的会议，外部参与者通过向他们拨出或通过提供的电话拨入式号码的音频会议许可证。 
 
  > [!NOTE]
  > E5 许可证包括电话系统和音频会议。   

此外，您必须确保以下：
 
- CsOnlineVoiceRoutingPolicy 分配给用户。 
- 允许专用调用启用租户级别的 Microsoft 团队。 

直接路由还支持的 Microsoft 调用计划许可的用户。 Microsoft 电话系统与调用规划可以将使用直接路由界面一些呼叫路由。 但是，用户的电话号码必须获得联机或移植到 Microsoft。  

混合调用规划和直接路由连接的同一个用户是可选的但可能有用，例如，当用户被分配了 Microsoft 调用规划，但希望将某些通过 SBC 呼叫路由。 是到第三方 Pbx 的呼叫的最常见方案之一。  与第三方 Pbx，所有的呼叫，除连接到该 Pbx 电话的呼叫进行路由通过调用规划 Microsoft;但与连接到第三方 Pbx 电话的呼叫应转至 SBC，因此保持在企业网络内，而不适用于 PSTN。 

有关电话系统授权的详细信息，请参阅[充分利用与 Office 365 的 Office](https://products.office.com/compare-all-microsoft-office-products?tab=2)和[Office 365 计划选项](https://technet.microsoft.com/library/office-365-plan-options.aspx)。 

有关电话系统授权的详细信息，请参阅[业务和 Microsoft 团队授权加载项的 Skype](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing)。 

## <a name="sbc-domain-names"></a>SBC 域名

SBC 域名必须介于 1"域"的租户中注册的名称。 不能使用 *。 onmicrosoft.com 租户的 SBC FQDN 名称。

下表显示的 DNS 名称是否名称可用作的 SBC，FQDN 为租户，请注册示例以及有效的 FQDN 名称的示例：

|**DNS 名称**|**可用于 SBC FQDN**|**FQDN 名称示例**|
|:--- |:--- |:--- |
contoso.com|是|**有效的名称：**<br/>sbc1.contoso.com<br/>ssbcs15.contoso.com<br/>europe.contoso.com|
|contoso.onmicrosoft.com|否|<br/>使用 *。 onmicrosoft.com 域不支持的 SBC 名称

假定您想要使用新的域名。 例如，您的租户具有 contoso.com，在您的租户中注册的域名和您想要使用 sbc1.sip.contoso.com。 可以对使用名称 sbc1.sip.contoso.com SBC 之前，您必须在您的租户中注册域名称 sip.contoso.com"域"中。 如果您尝试在注册的域名之前配对 sbc1.sip.contoso.com 与 SBC，则会收到以下错误:"无法使用"sbc1.sip.contoso.com"域所不配置此租户。"
添加的域名后，您还需要创建 UPN user@sip.contoso.com 具有的用户和分配"团队"许可证。 可能需要 24 小时内完全之后进行的域名添加到您的租户，"域"创建新的名用户，和许可证分配给用户的设置。 

则可能公司有一个租户中的多个 SIP 地址空间。 例如，公司可能必须作为 SIP 地址空间的 contoso.com 和 fabrikam.com 为第二个 SIP 地址空间。 某些用户具有地址 user@contoso.com 和某些用户具有地址 user@fabrikam.com。 

SBC 只需要一个 FQDN，可以从任何地址空间配对租户中的用户提供服务。 例如，名称 sbc1.contoso.com 与 SBC 可以接收和地址 user@contoso.com 和 user@fabrikam.com 具有的用户发送 PSTN 流量，只要在同一租户中注册这些 SIP 地址空间。  

## <a name="public-trusted-certificate-for-the-sbc"></a>SBC 的受信任的公共证书

Microsoft 强烈建议您申请证书的 SBC 通过生成证书签名请求 (CSR)。 有关为 SBC 生成 CSR 的具体说明，请参阅互连说明或 SBC 供应商提供的文档。 

  > [!NOTE]
  > 大多数证书颁发机构 (Ca) 需要为至少为 2048年私钥大小。 生成 CSR 时，请记住这一点。

证书需要有主题、 公共名称或使用者替代名称字段中的 SBC FQDN。

此外，直接路由支持通配符中的常见的名称或 SAN，并且通配符需要符合标准[RFC HTTP Over TLS](https://tools.ietf.org/html/rfc2818#section-3.1)。 一个示例将使用 *。 在 SAN 中，将符合 SBC FQDN sbc.contoso.com，但不会与 sbc.test.contoso.com 相匹配的 contoso.com。

需要由一个以下的根证书颁发机构生成该证书：

- AffirmTrust
- AddTrust 外部 CA 的根
- Baltimore CyberTrust Root
- Buypass
- Cybertrust
- Class 3 主要公用证书颁发机构 
- 德国 Telekom 
- DigiCert 全局根 CA 
- 委托
- GlobalSign
- 转 Daddy
- GeoTrust
- Verisign，Inc. 
- 飞越 
- Microsoft Symantec 企业移动根 
- SwissSign
- Thawte 时间戳 CA
- Trustwave
- TeliaSonera 
- T 系统国际 GmbH (德国 Telekom)
- QuoVadis

Microsoft 正在添加基于客户请求的其他证书颁发机构。 

## <a name="sip-signaling-fqdns-and-firewall-ports"></a>SIP 信号： Fqdn 和防火墙端口 

直接路由的连接点是具有以下三个 Fqdn:

- 必须首先尝试**sip.pstnhub.microsoft.com** – 全局 FQDN –。 当 SBC 发送请求，若要解决此名称时，Microsoft Azure DNS 服务器返回指向主 Azure 数据中心 IP 地址分配给 SBC。 性能指标的数据中心和地理接近 SBC 基于工作分配。 返回的 IP 地址对应于主要的 FQDN。
- **sip2.pstnhub.microsoft.com** – 辅助 FQDN – 地理位置映射到第二个优先级区域。
- **sip3.pstnhub.microsoft.com** – 第三级 FQDN – 地理位置映射到第三个优先级区域。

发出以下三个 Fqdn 顺序是需要：

- 提供最佳用户体验 （不加载和 SBC 数据中心通过查询的第一个 FQDN 分配最接近）。
- 建立从 SBC 连接到数据中心的临时问题时提供故障转移。 有关详细信息，请参阅[故障转移机制](#failover-mechanism-for-sip-signaling)下面。  

– Sip.pstnhub.microsoft.com、 sip2.pstnhub.microsoft.com 和 sip3.pstnhub.microsoft.com – 的 Fqdn 将解析为以下 IP 地址之一：

- 52.114.148.0
- 52.114.132.46 
- 52.114.75.24 
- 52.114.76.76 
- 52.114.7.24 
- 52.114.14.70

您需要打开防火墙以允许与地址的传入和传出流量信号中的所有这些 IP 地址的端口。  如果您的防火墙支持 DNS 名称，FQDN sip-all.pstnhub.microsoft.com 将解析为上面的所有 IP 地址。  您必须使用以下端口：

|**流量**|**从**|**到**|**源端口**|**目标端口**|
|:--- |:--- |:--- |:--- |:--- |
|SIP/TLS|SIP 代理服务器|SBC|1024 到 65535|SBC 上定义|
SIP/TLS|SBC|SIP 代理服务器|SBC 上定义|5061|
||||||

### <a name="failover-mechanism-for-sip-signaling"></a>用于 SIP 信号故障转移机制

SBC 使 DNS 查询解析 sip.pstnhub.microsoft.com。 根据 SBC 位置和数据中心性能指标，主数据中心处于选中状态。 如果主数据中心体验问题、 SBC 将尝试 sip2.pstnhub.microsoft.com，将解析为第二个分配数据中心，并在极少数情况下该数据中心中两个区域都不可用，SBC 重试最后的 FQDN （sip3.pstnhub.microsoft.com)，从而提高了三级的数据中心 IP。

下表总结了主要、 第二和第三级的数据中心之间的关系：

|**如果主数据中心**|**EMEA**|**NOAM**|**亚洲**|
|:--- |:--- |:--- |:--- |
|辅助数据中心 (sip2.pstnhub.microsoft.com)|我们|欧盟|我们|
|三级的数据中心 (sip3.pstnhub.microsoft.com)|亚洲|亚洲|欧盟|
|||||

## <a name="media-traffic-port-ranges"></a>媒体流量： 端口范围

媒体流量排列与单独的 Microsoft 云服务。 媒体流量 IP 范围：
- 52.112.0.0 /14 （IP 地址从 52.112.0.1 52.115.255.254）。

下表中显示的媒体处理器的端口范围： 

|**流量**|**从**|**到**|**源端口**|**目标端口**|
|:--- |:--- |:--- |:--- |:--- |
|UDP/SRTP|媒体处理器|SBC|49 152 – 53 247|SBC 上定义|
|UDP/SRTP|SBC|媒体处理器|SBC 上定义|49 152 – 53 247|
|

  > [!NOTE]
  > Microsoft 建议每个并发呼叫 SBC 上至少两个端口。

## <a name="supported-session-border-controllers-sbcs"></a>支持会话边界控制器 (Sbc)

Microsoft 仅支持认证的 SBC，可直接路由与配对。 企业语音的业务至关重要，因为 Microsoft 运行占用大量测试与所选的 Sbc，并且与 SBC 供应商，以确保在两个系统的工作原理兼容。 

团队直接路由作为认证列出了已验证的设备。 认证的设备都能保证所有方案中工作。 此外没有 Microsoft 之间建立的 SBC 供应商的联合支持过程。  

正在认证正在以下供应商提供：
- [AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams)
- 功能区通信 (以前称为 Sonus):
   - [SBC 边缘系列](https://support.sonus.net/display/UXDOC70/Best+Practice+-+Configuring+SBC+Edge+1000+-+2000+for+Microsoft+Teams+Direct+Routing)
   - [SBC 核心系列](https://support.sonus.net/display/IOT/PBXs+-+SBC+5k7kSWe)
- ThinkTel: ThinkTel 不销售到企业 SBCs，但其 SBC 正在认证。  
 
## <a name="see-also"></a>另请参阅

[配置直接路由](direct-routing-configure.md)



