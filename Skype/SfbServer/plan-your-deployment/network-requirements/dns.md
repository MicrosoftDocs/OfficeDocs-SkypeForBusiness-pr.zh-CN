---
title: dns requirements for Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c50e38d2-b1e4-4ebd-8dc3-85d4ae7a76ee
description: 摘要：实施 DNS 之前，请查看本主题中的 DNS Skype for Business Server。
ms.openlocfilehash: fa81b85fb7254130302ed9163a652f03ec1bf33c
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60859829"
---
# <a name="dns-requirements-for-skype-for-business-server"></a>dns requirements for Skype for Business Server

**摘要：** 在实施 DNS 之前，请查看本主题中的 DNS Skype for Business Server。

本文仅介绍针对组织Skype for Business Server部署进行 DNS 规划。 For Skype for Business Online refer to "Office 365 URLs and IP address ranges" at [https://aka.ms/o365ips](/microsoft-365/enterprise/urls-and-ip-address-ranges) .

域名服务 (DNS) 映射主机名 (如 www。 <span></span>contoso .com，假定 web 服务器) IP 地址 (例如 <span></span> 10.10.10.10) 。 它可以帮助客户端和相互依赖的服务器在网络中相互通信。 设置 Skype for Business Server 2015 的实现时，需要确保新服务器名称 (的映射通常反映他们在) 上将承担的角色与分配给他们的 IP 地址匹配。

虽然这最初看起来有点令人担心，但可通过使用[Skype for Business Server 2015 规划工具 完成规划工作](https://www.microsoft.com/download/details.aspx?id=50357)。 完成向导中有关计划使用的功能的问题后，对于定义的每个站点，可以查看边缘管理员报告中的 DNS 报告，并使用其中列出的信息创建 DNS 记录。 您还可以对所使用的许多名称和 IP 地址进行调整，有关详细信息，请参阅 [查看 DNS 报告](../../management-tools/planning-tool/review-the-administrator-reports.md#DNS_Report)。 请记住，可以将边缘管理报告导出到 Excel 电子表格，DNS 报告将是该文件中的工作表之一。 尽管此工具包含[2019 年 10](../../../SfBServer2019/deprecated.md)Skype for Business Server弃用的功能，但是如果未选择这些功能，它仍可用于创建初始计划

在安装新实现（如为 Skype for Business Server 创建[DNS](../../deploy/install/create-dns-records.md)记录和构建 Skype for Business Server 拓扑中所述）时，我们意识到可以选择使用 Windows Server 2016 或第三方 DNS 程序包中内置的 DNS 功能，因此我们将ep 本文中讨论内容是常规的，而不是具体的。 我们详细介绍了需要满足哪些需求以及如何满足此需求，这是您的决定。

有经验的Skype for Business、Lync 和 Office Communications Suite 管理员可能会发现下表非常有用。 如果该表令人困惑，则以下各节或文章将阐明以下概念：

## <a name="summary-tables"></a>摘要表
<a name="BK_Summary"> </a>

下表显示了用于为用户提供Skype for Business Server DNS 记录。 有些是可选的，因为它们仅支持某些功能，并且如果不需要这些功能，可以跳过它们。 内部访问所需的 DNS 记录仅在第一个表中，允许内部和外部访问的部署将需要这两个表中的记录。

**内部 DNS 映射**

|记录类型|值|解析为|用途|必需|
|:-----|:-----|:-----|:-----|:-----|
|A/AAAA   |前端池 FQDN  <br/> *FE-pool。 <span></span>contoso <span></span> .com*   |前端池服务器 IP 地址  <br/>  DNS LB 到 *192.168.21.122 192.168.21.123 192.168.21.124*   |前端池的 DNS 负载平衡。 地图前端池名称设置为一组 IP 地址。  <br/> 请参阅 [在前端池和控制器池上部署 DNS 负载平衡](load-balancing.md#BK_FE_Dir)  |Y   |
|A/AAAA   | 池或独立服务器中每台前端服务器Standard Edition服务器的 FQDN <br/>  *FE01。 <span></span>contoso。 <span></span>com FE02。 <span></span>contoso <span></span> .com FE03。 <span></span>contoso <span></span> .com*   |每个服务器的相应 IP  <br/> *192.168.21.122 192.168.21.123 192.168.21.124*   |地图服务器名称的 IP 地址。   |Y   |
|A/AAAA   |Enterprise池内部 Web 服务覆盖 FQDN  <br/> *Web-int。 <span></span>contoso <span></span> .com*   |前端服务器内部 Web 服务的 HLB VIP  <br/> *192.168.21.120*   |需要启用客户端到服务器 Web 流量，例如下载Skype for Business Web应用。 移动客户端也是必需的。   |Y   |
|A/AAAA   |Enterprise池外部 Web 服务覆盖 FQDN  <br/> *Web-ext。 <span></span>contoso <span></span> .com*   |前端服务器外部 Web 服务的 HLB VIP  <br/>*68.123.56.90*   |需要启用客户端到服务器 Web 流量，例如下载Skype for Business Web应用。 如果移动客户端将在内部解析 DNS，此为必需项。 可以解析为 DMZ 反向代理 IP 或 Internet IP。   ||
|A/AAAA   | 后端服务器SQL服务器 FQDN <br/> *SQL1。 <span></span>contoso <span></span> .com*   |服务器 IP 地址  <br/> *192.168.11.90*   |地图前端池的后端SQL服务器的服务器名称恢复为 IP 地址   ||
|A/AAAA   |后端服务器镜像SQL服务器 FQDN  <br/> *SQL2。 <span></span>contoso <span></span> .com*   |服务器 IP 地址  <br/> *192.168.11.91*   |地图前端池的后端池SQL服务器的服务器名称更新到其 IP 地址   ||
|A/AAAA   |控制器池 FQDN  <br/>**注意：** 使用独立控制器服务器时不适用 <br/> *DirPool。 <span></span>contoso <span></span> .com*   |控制器池 IP 地址  <br/> DNS LB 为 *192.168.21.132、192.168.21.133、192.168.21.134*   |控制器池服务器的 DNS 负载平衡。 地图池的池名称更新为 IP 地址，请参阅在前端池和控制器池上部署[DNS 负载平衡](load-balancing.md#BK_FE_Dir) <br/> 控制器可以对用户进行身份验证，并且是可选的。   ||
|A/AAAA   |控制器 FQDN   |每个控制器服务器的服务器 IP 地址   |地图控制器的池名称解析为 IP 地址，请参阅在前端池和控制器池上部署[DNS 负载平衡](load-balancing.md#BK_FE_Dir)  ||
|A/AAAA   |中介服务器池 FQDN   |池 IP 地址   |中介服务器角色是可选的。 可以将中介服务器提供的服务联合定位到前端服务器或池。 请参阅 [在中介服务器池中使用 DNS 负载平衡](load-balancing.md#BK_Mediation)  ||
|A/AAAA   |中介服务器 FQDN   |服务器 IP 地址   |可以将中介服务器提供的服务联合定位到前端服务器或池。 请参阅 [在中介服务器池中使用 DNS 负载平衡](load-balancing.md#BK_Mediation)  ||
|A/AAAA   |持久聊天服务器 FQDN   |持久聊天服务器 IP 地址   |持久聊天功能需要持久聊天服务器，否则为可选。   ||
|A/AAAA   |lyncdiscoverinternal。*\<sipdomain\>* <br/> lyncdiscoverinternal。*<span></span> contoso <span></span> .com*   |HLB 前端池 VIP 或控制器 IP  <br/>  192.168.21.121  |内部自动发现服务 1，移动性支持要求。 如果使用内部 DNS 解析移动设备，则它应指向外部 IP 或 DMZ VIP。  <br/> 对于 Web 服务，我们需要前端池上的 HLB，因为 HTTPS 无法利用 DNS。 对于前端池或控制器池，这应解析为 HLB VIP，或 Standard Edition Server 或独立控制器服务器的常规 IP。   |Y   |
|CNAME   |lyncdiscoverinternal。*\<sipdomain\>* <br/> lyncdiscoverinternal。 *<span></span>contoso <span></span> .com*   |HLB FE 池 FQDN 或控制器 FQDN  <br/> Web-int。 <span></span>contoso <span></span> .com   |内部自动发现服务1 <br/> 如果需要，可以将它实现为 CNAME，而不是 A 记录。   ||
|A/AAAA   |sip。*\<sipdomain\>* <br/> sip。*<span></span> contoso <span></span> .com*  |前端池服务器 IP 地址 (或每个控制器 IP 地址)   <br/>  DNS LB 到 *192.168.21.122 192.168.21.123 192.168.21.124*   |对于自动配置是必需的，请参阅 Skype for Business[客户端定位服务的演练](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype) <br/> 指向内部网络上前端池服务器或控制器服务器或访问边缘服务的一个或多个记录（当客户端为外部客户端时）   |&#x2777;  |
|A/AAAA   |ucupdates-r2。*\<sipdomain\>* <br/> ucupdates-r2。*<span></span> contoso <span></span> .com*  |HLB FE 池 VIP 或控制器池 HLB VIP，标准版/控制器服务器 IP  <br/>  192.168.21.121  |部署此记录是可选的&#x2778;  ||
|SRV   |\_sipinternaltls。 \_tcp.*\<sipdomain\>* <br/>端口 5061 <br/>\_sipinternaltls。 \_tcp.*<span></span> contoso <span></span> .com* <br/>端口 5061  |前端池 FQDN  <br/>*FE-Pool。 <span></span>contoso <span></span> .com*  |启用内部用户自动登录 1 到前端服务器/池或 标准版 服务器/池，该服务器/池对客户端登录请求进行身份验证和重定向。  |&#x2777; |
|A/AAAA |sipinternal。*\<sipdomain\>* <br/>sipinternal。 <span></span>*contoso <span></span> .com*  |前端池 FQDN  <br/>_FE-Pool。 <span></span>contoso <span></span> .com_  |内部用户访问&#x2776;  |&#x2777;  |
|SRV   | \_ntp. \_udp。*\<sipdomain\>* <br/> \_ntp. \_udp。 <span></span>*contoso <span></span> .com*  |TimeServer FQDN  <br/> north-america.pool.ntp.org   |Lync 电话 Edition 设备所需的 NTP 源   |这是支持桌面话筒的必需项。   |
|SRV   |\_sipfederationtls。 \_tcp.*\<sipdomain\>* <br/>\_sipfederationtls。 \_tcp. <span></span>*contoso <span></span> .com*  | 访问边缘服务 FQDN <br/> EdgePool-int。 <span></span>*contoso <span></span> .com*  |为具有 IOS 或电话移动客户端的每个 SIP 域Windows一条 SRV 记录。   |对于移动客户端支持   |
|A/AAAA   |管理员 URL  <br/>*Web-int。 <span></span>contoso <span></span> .com*  |HLB FE 池 VIP  <br/> 192.168.21.121   |Skype for Business Server控制面板，请参阅[简单 URL](dns.md#BK_Simple)  ||
|A/AAAA   |meet URL  <br/>*Web-int。 <span></span>contoso <span></span> .com*  |HLB FE 池 VIP  <br/> 192.168.21.121   |联机会议，请参阅 [简单 URL](dns.md#BK_Simple)  ||
|A/AAAA   |拨入 URL  <br/>*Web-int。 <span></span>contoso <span></span> .com*  |HLB FE 池 VIP  <br/> 192.168.21.121   |电话拨入式会议，请参阅 [简单 URL](dns.md#BK_Simple)  ||
|A/AAAA   |内部 Web 服务 FQDN  <br/>*Web-int。 <span></span>contoso <span></span> .com*  |HLB FE 池 VIP  <br/> 192.168.21.121   |Skype for BusinessWeb 服务由 Skype for Business Web应用   ||
|A/AAAA   |OfficeWeb Apps Server 池 FQDN  <br/> OWA。 <span></span>contoso <span></span> .com   | OfficeWeb Apps Server 池 VIP 地址 <br/> 192.168.1.5   |定义 Office Web Apps Server 池 FQDN   ||
|A/AAAA   | 内部 Web FQDN <br/> Web-int。 <span></span>contoso <span></span> .com   | 前端池 VIP 地址 <br/> 192.168.21.121   |定义用户所使用的内部 Web FQDN Skype for Business Web应用  <br/> 如果在此池中使用 DNS 负载平衡，则前端池和内部 Web 场不能具有相同的 FQDN。   ||

&#x2776;客户端用于发现前端服务器或前端池，并作为用户进行身份验证和登录。 有关此内容的详细信息，可Skype for Business[客户端的演练中](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)。

&#x2777;仅在 Lync 2013 之前支持旧版客户端和桌面话筒。

&#x2778; 如果统一通信设备已打开，但用户从未登录到该设备，则 A 记录允许设备发现托管设备更新 Web 服务的服务器并获取更新。 否则，设备在用户首次登录时通过带内设置获得服务器信息。

下图显示了一个示例，该示例包括内部和外部 DNS 记录以及周围表格中显示的许多记录：

**使用公用 IPv4 地址的边缘网络图**

![DNS 网络图的示例。](../../media/2cc9546e-5560-4d95-8fe4-65a792a0e9c3.png)

**外围网络 DNS 映射 (接口和外部接口)**

|记录类型|值|解析为|用途|必需|
|:--- |:--- |:--- |:--- |:--- |
|A/AAAA   |内部边缘池 FQDN  <br/>*EdgePool-int。 <span></span>contoso <span></span> .com*  |面向内部的边缘池 IP 地址  <br/> 172.25.33.10, 172.25.33.11   |合并边缘池内部接口 IP 地址   |Y   |
|A/AAAA   |边缘服务器 FQDN  <br/>*Cons-1. <span></span>contoso <span></span> .com*  |边缘池中服务器的面向内部的服务器 IP  <br/> 172.25.33.10   |为池中每个服务器创建一个记录，其中服务器 FQDN 指向池中其内部服务器节点 IP，请参阅[DNS Load Balancing on Edge Server Pools。](load-balancing.md#BK_Edge)   |Y   |
|A/AAAA   |访问边缘服务池 FQDN  <br/>*Access1。 <span></span>contoso <span></span> .com*  |访问边缘服务池外部 IP 地址  <br/> 131.107.16.10, 131.107.16.11   |访问边缘服务为出站和入站会话初始协议提供单一的受信任连接点 (SIP) 流量。   |Y   |
|A/AAAA   |Web 会议边缘服务池 FQDN  <br/>*Webcon1。 <span></span>contoso <span></span> .com*  |Web 会议边缘服务外部 IP 地址  <br/> 131.107.16.90, 131.107.16.91   |Web 会议边缘服务允许外部用户加入在内部会议环境中Skype for Business Server会议。   |Y   |
|A/AAAA   |*av.\<sip-domain\>* 池 FQDN <br/>*AV1。 <span></span>contoso <span></span> .com*  |A/V 边缘外部 IP 地址  <br/> 131.107.16.170, 131.107.16.171   |A/V 边缘服务使外部用户可以使用音频、视频、应用程序共享和文件传输。   |Y   |
|CNAME   |sip。*\<sipdomain\>* <br/> sip。*<span></span> contoso <span></span> .com*  |外部访问边缘池 FQDN  <br/>*Access1。 <span></span>contoso <span></span> .com*  |找到边缘服务器池 。 请参阅[客户端定位Skype for Business演练](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)  |Y   |
|SRV   |\_sip。 \_tls。*\<sipdomain\>* <br/>\_sip。 \_tls。 <span></span>*contoso <span></span> .com*  |外部访问边缘 FQDN  <br/>_Access1。 <span></span>contoso <span></span> .com_  |用于外部用户访问。 请参阅[客户端定位Skype for Business演练](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)  |Y   |
|SRV   |\_sipfederationtls。 \_tcp.*\<sipdomain\>* <br/>\_sipfederationtls。 \_tcp. <span></span>*contoso <span></span> .com*  |外部访问边缘 FQDN  <br/>*Access1。 <span></span>contoso <span></span> .com*  |用于联盟和公共 IM 连接   |&#x2776;  |
|SRV   |\_xmpp-server。 \_tcp.*<sipdomain \>* <br/>\_xmpp-server。 \_tcp.*<span></span> contoso <span></span> .com*  |外部访问边缘 FQDN  <br/>*Access1。 <span></span>contoso <span></span> .com*  |XMPP 代理服务接受并发送 XMPP 联盟伙伴 (XMPP) 发送可扩展消息传递和状态协议。   |Y，用于部署联盟，否则为可选  <br/> 在 2019 Skype for Business Server不可用。|
|SRV   |\_sipfederationtls。 \_tcp.*\<sipdomain\>* <br/>\_sipfederationtls。 \_tcp.*<span></span> contoso <span></span> .com*  |外部访问边缘 FQDN  <br/>*Access1。 <span></span>contoso <span></span> .com*  |若要支持推送通知服务和 Apple 推送通知服务，请为每个 SIP 域创建一条 SRV 记录。 &#x2778;  ||
|A/AAAA   |外部前端池 Web 服务 FQDN  <br/>*Web-ext。 <span></span>contoso <span></span> .com*  |反向代理公用 IP 地址，代理到前端池的外部 Web 服务 VIP &#x2776; <br/> 131.107.155.1 代理到 192.168.21.120   |前端池使用的前端池外部Skype for Business Web应用   |Y   |
|A/AAAA/CNAME   |lyncdiscover。*\<sipdomain\>* <br/> lyncdiscover。*<span></span> contoso <span></span> .com*  |反向代理公用 IP 地址，解析为控制器池的外部 Web 服务 VIP（如果有）或前端池（如果您没有控制器&#x2777; <br/> 131.107.155.1 代理到 192.168.21.120   | 由反向代理服务器解析的客户端自动发现的外部记录，也由移动、Skype for Business Web应用和计划程序 Web 应用使用 <br/> 若要支持推送通知服务和 Apple 推送通知服务，请为具有 Microsoft Lync Mobile 客户端的每个 SIP 域创建一条 SRV 记录。 3  |Y   |
|A/AAAA   |meet。*\<sipdomain\>* <br/> meet。*<span></span> contoso <span></span> .com*  |反向代理公用 IP 地址，解析为前端池的外部 Web 接口  <br/> 131.107.155.1 代理到 192.168.21.120   |Web Skype for Business代理  <br/> 请参阅 [简单 URL](dns.md#BK_Simple)  |Y   |
|A/AAAA   |拨入。*\<sipdomain\>* <br/> 拨入。*<span></span> contoso <span></span> .com*  |反向代理公用 IP 地址，代理到前端池的外部 Web 接口  <br/> 131.107.155.1 代理到 192.168.21.120   |Web Skype for Business代理  <br/> 请参阅 [简单 URL](dns.md#BK_Simple)  |Y   |
|A/AAAA   |OfficeWeb Apps Server 池 FQDN  <br/> OWA。 <span></span>contoso <span></span> .com   | 反向代理公用 IP 地址，代理到 web Apps Server Office Web 接口 <br/> 131.107.155.1 代理到 192.168.1.5   | OfficeWeb Apps Server 池 VIP 地址 <br/> 192.168.1.5   |定义 Office Web Apps Server 池 FQDN   |

&#x2776;部署联盟是必需的，否则为可选。

&#x2777;客户端用于发现前端服务器或前端池，并作为用户进行身份验证和登录。

&#x2778; 此要求仅适用于基于 Apple 或 Microsoft 的移动设备上的客户端。 Android 和 Nokia Symbian 设备不使用推送通知。

 有关边缘服务器和外围网络的更多详细信息，请参阅边缘服务器 DNS [规划](../../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#DNSPlan) 内容。

> [!IMPORTANT]
> Skype for Business Server IPv6 寻址的使用。 有关详细信息，请参阅 Skype for Business 中的规划[IPv6。](ipv6.md)

> [!IMPORTANT]
> 有关 FQDN 的详细信息，请参阅 [DNS 基础知识](basics.md)。

**拆分式 DNS** 
<a name="BK_split"></a>

拆分式 DNS 是一种 DNS 配置，其中两个 DNS 区域具有相同的命名空间。 第一个 DNS 区域处理内部请求，第二个 DNS 区域处理外部请求，如这些表所述。 有关详细信息，请参阅拆分 [式 DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS)。

## <a name="hybrid-considerations"></a>混合注意事项
<a name="BK_Hybrid"> </a>

如果你计划让一些用户联机并某些用户位于本地，请参阅混合连接规划文章[Skype for Business server 2019。](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) 在 2015 年，您需要将 DNS 配置为正常Skype for Business Server并添加其他 DNS 记录。

你还应参阅 "Office 365 URL 和 IP 地址范围"，以确认你的用户将有权访问他们需要 [https://aka.ms/o365ips](/microsoft-365/enterprise/urls-and-ip-address-ranges) 的联机资源。

## <a name="simple-urls"></a>简单 URL
<a name="BK_Simple"> </a>

统一资源定位 (URL) 是一个对 Web 资源的引用，该 Web 资源指定它在计算机网络中的位置以及用于检索该位置的协议。

Skype for Business Server三个"简单"URL 访问服务：

- **Meet** 用作网站中所有会议的基本 URL。 Meet 简单 URL 的一个示例是 <span></span> // https：meet。 <span></span> <span></span>contoso <span></span> .com。 特定会议 URL 可能是 https： <span></span> // <span></span> meet。 <span></span>contoso <span></span> .com/_username_/7322994。

    使用会议简单 URL，加入会议的链接很容易理解且易于通信。

- **拨入** 允许访问电话拨入式会议设置网页。 此页显示会议的拨入号码及其可用语言、分配的会议信息（即，对于不需要预定的会议）以及会议中的 DTMF 控制，并支持对个人标识号 (PIN) 和分配的会议信息的管理。 拨入简单 URL 包含在所有会议邀请中，因此要拨号加入会议的用户可以访问所需的电话号码和 PIN 信息。 拨入简单 URL 的一个示例是 https:// <span></span> 拨入。 <span></span>contoso <span></span> .com。

- **管理员** 允许快速访问Skype for Business Server控制面板。 在组织防火墙内的任何计算机中，管理员可通过在浏览器中Skype for Business Server管理简单 URL 打开"管理"控制面板。 管理简单 URL 是组织内部的。 管理简单 URL 的一个示例是 https:// <span></span> 管理员。 <span></span>contoso <span></span> .com。

有关简单 URL 的 DNS 要求，将详细讨论简单 URL [Skype for Business Server。](simple-urls.md)

## <a name="dns-by-server-role"></a>按服务器角色的 DNS
<a name="BK_Servers"> </a>

您可以设置这些池和服务器的名称，但可以让他们记住并反映他们在系统中的功能。

### <a name="dns-records-for-individual-servers-or-pools"></a>单个服务器或池的 DNS 记录

这些通用记录要求适用于由管理员使用的任何Skype for Business。 池是运行相同服务的一组服务器，这些服务协同工作以处理通过负载平衡器定向到这些服务器的客户端请求。 有关详细信息[，请参阅Skype for Business](load-balancing.md)负载平衡要求

**DNS 记录 服务器/池角色的要求 (DNS 负载平衡)**

|部署方案|DNS 要求|
|:-----|:-----|
|一台服务器：  <br/> 持久聊天、控制器、中介服务器、前端服务器   |将服务器的完全限定的域名 (FQDN) 解析为其 IP 地址的内部 A 记录。  <br/> ServerRole。 <span></span>contoso <span></span> .com 10.10.10.0   |
|池：  <br/> 持久聊天、控制器、边缘服务器、中介服务器、前端   |将池中每个服务器节点的完全限定域名 (FQDN) 解析为 IP 地址的内部 A 记录。  <br/>**示例** <br/> ServerRole01。 <span></span>contoso <span></span> .com 10.10.10.1  <br/> ServerRole02。 <span></span>contoso <span></span> .com 10.10.10.2  <br/> 将池的完全限定域名 (FQDN) 解析为池中服务器节点的 IP 地址的多个内部 A 记录。  <br/>**示例** <br/> ServerPool。 <span></span>contoso <span></span> .com 10.10.10.1  <br/> ServerPool。 <span></span>contoso <span></span> .com 10.10.10.2   |

### <a name="edge-server-specific-dns-topics"></a>边缘服务器特定的 DNS 主题

 若要规划边缘服务器部署，请查看 Plan [for Edge Server deployments in Skype for Business Server 2015](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md)和[Advanced Edge Server DNS planning for Skype for Business Server 2015（](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md)包含以下部分）

- [DNS 灾难恢复](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSDR)

- [DNS load balancing － DNS 负载平衡](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB)

- [无拆分式 DNS 的自动配置](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#NoSplitBrainDNS)

- [拆分式 DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS)

- [客户端定位Skype for Business的演练](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)