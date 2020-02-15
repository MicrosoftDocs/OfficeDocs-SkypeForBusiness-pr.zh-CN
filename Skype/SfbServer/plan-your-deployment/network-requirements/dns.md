---
title: Skype for Business Server 的 DNS 要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c50e38d2-b1e4-4ebd-8dc3-85d4ae7a76ee
description: 摘要：在实施 Skype for Business Server 之前，请查看本主题中的 DNS 注意事项。
ms.openlocfilehash: 33c5e18c6bc8d5a29b0e4a6fa447fbde02028556
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "41982807"
---
# <a name="dns-requirements-for-skype-for-business-server"></a>Skype for Business Server 的 DNS 要求

**摘要：** 在实施 Skype for Business Server 之前，请查看本主题中的 DNS 注意事项。

本文仅解决组织的内部部署网络上的 Skype for business Server 部署的 DNS 规划。 对于 Skype for Business Online，请参阅位置[https://aka.ms/o365ips](https://aka.ms/o365ips)的 "Office 365 URL 和 IP 地址范围"。

域名服务（DNS）服务器映射主机名（如 www）。<span> </span>contoso<span></span>.com （大概是 web 服务器）到 IP 地址（如10.10.10.10）。 帮助客户端和相互依赖的服务器在网络上相互通信。 当您设置 Skype for Business Server 2015 的实施时，需要确保新服务器名称的映射（通常反映它们所采用的角色）与分配给它们的 IP 地址相匹配。

虽然这在最初看起来可能有点令人望而生畏，但使用[Skype For Business Server 2015 规划工具](https://www.microsoft.com/download/details.aspx?id=50357)进行规划的工作量可能会很大。 完成向导的有关计划使用的功能的问题后，为您定义的每个网站都可以在边缘管理报告中查看 DNS 报告，并使用此处列出的信息创建 DNS 记录。 您还可以对所使用的多个名称和 IP 地址进行调整，有关详细信息，请参阅[查看 DNS 报告](../../management-tools/planning-tool/review-the-administrator-reports.md#DNS_Report)。 请注意，你可以将边缘管理报告导出到 Excel 电子表格，并且 DNS 报告将是文件中的工作表之一。 虽然此工具包括[Skype For Business Server 2019 中弃用](../../../SfBServer2019/deprecated.md)的功能，但仍可用于创建初始计划（如果未选择这些功能）

当您按照[Create a DNS 记录 For skype for Business server](../../deploy/install/create-dns-records.md)和构建 skype For business server 的拓扑中所述安装新的实施时，我们会认识到，可以选择使用 Windows Server 2016 或第三方 DNS 包中内置的 DNS 功能，因此我们将在本文中进行常规而不是特定的讨论。 我们将详细介绍所需的内容，以及你应如何满足你的决定。

有经验的 Skype for business、Lync 和 Office 通信套件管理员可能会发现以下表格有用。 如果表格对您感到困惑，随后的章节或文章将 shed 以下概念：

## <a name="summary-tables"></a>摘要表
<a name="BK_Summary"> </a>

下表显示 Skype for business Server 用于向用户提供服务的 DNS 记录。 有些选择是必需的，因为它们仅支持某些功能，如果不需要这些功能，则可以跳过这些功能。 仅限内部访问所需的 DNS 记录位于第一个表中，并且允许内部和外部访问的部署将需要两个表中的记录。

**内部 DNS 映射**

|记录类型|值|解析为|用途|必需|
|:-----|:-----|:-----|:-----|:-----|
|A/AAAA   |前端池 FQDN  <br/> *FE 池。<span> </span>contoso<span></span>*   |前端池服务器 IP 地址  <br/>  DNS LB to *192.168.21.122 192.168.21.123 192.168.21.124*   |前端池的 DNS 负载平衡。 将前端池名称映射到一组 IP 地址。  <br/> 请参阅[在前端池和控制器池中部署 DNS 负载平衡](load-balancing.md#BK_FE_Dir)  |Y   |
|A/AAAA   | 池中的每个前端服务器或 Standard Edition 服务器的 FQDN，或独立服务器 <br/>  *FE01.<span> </span>contoso。<span> </span>com FE02。<span> </span>contoso<span></span>FE03。<span> </span>contoso<span></span>*   |每个服务器的相应 IP  <br/> *192.168.21.122 192.168.21.123 192.168.21.124*   |将服务器名称映射到其 IP 地址。   |Y   |
|A/AAAA   |企业版池内部 Web 服务覆盖 FQDN  <br/> *Web-int<span></span><span></span>.com*   |前端服务器内部 Web 服务的 HLB VIP  <br/> *192.168.21.120*   |启用客户端到服务器 web 流量（如下载 Skype for Business Web 应用程序）所必需的。 对于移动客户端也是必需的。   |Y   |
|A/AAAA   |企业版池外部 Web 服务替代 FQDN  <br/> *Web-外部<span></span><span></span>-.com*   |前端服务器外部 Web 服务的 HLB VIP  <br/>*68.123.56.90*   |启用客户端到服务器 web 流量（如下载 Skype for Business Web 应用程序）所必需的。 如果移动客户端将在内部解析 DNS，则是必需的。 可以解析为 DMZ 反向代理 IP 或 Internet IP。   ||
|A/AAAA   | 后端服务器 SQL Server FQDN <br/> *SQL1.<span> </span>contoso<span></span>*   |服务器 IP 地址  <br/> *192.168.11.90*   |将使用前端池的后端 SQL server 的服务器名称映射到其 IP 地址   ||
|A/AAAA   |后端服务器镜像 SQL Server FQDN  <br/> *SQL2.<span> </span>contoso<span></span>*   |服务器 IP 地址  <br/> *192.168.11.91*   |将使用前端池的后端 SQL 镜像服务器的服务器名称映射到其 IP 地址   ||
|A/AAAA   |控制器池 FQDN  <br/>**注意：** 使用独立控制器服务器时不适用 <br/> *DirPool.<span> </span>contoso<span></span>*   |控制器池 IP 地址  <br/> DNS LB to *192.168.21.132，192.168.21.133，192.168.21.134*   |控制器池服务器的 DNS 负载平衡。 将控制器池的池名称映射到 IP 地址，请参阅[在前端池和控制器池中部署 DNS 负载平衡](load-balancing.md#BK_FE_Dir) <br/> Director 可对用户进行身份验证，并且是可选的。   ||
|A/AAAA   |控制器 FQDN   |每个控制器服务器的服务器 IP 地址   |将 Director 的池名称映射到 IP 地址，请参阅[在前端池和控制器池中部署 DNS 负载平衡](load-balancing.md#BK_FE_Dir)  ||
|A/AAAA   |中介服务器池 FQDN   |池 IP 地址   |中介服务器角色是可选的。 您可以将中介服务器提供的服务与前端服务器或池共同定位。 请参阅[在中介服务器池上使用 DNS 负载平衡](load-balancing.md#BK_Mediation)  ||
|A/AAAA   |中介服务器 FQDN   |服务器 IP 地址   |您可以将中介服务器提供的服务与前端服务器或池共同定位。 请参阅[在中介服务器池上使用 DNS 负载平衡](load-balancing.md#BK_Mediation)  ||
|A/AAAA   |持久聊天服务器 FQDN   |持久聊天服务器 IP 地址   |持久聊天服务器是持久聊天功能所必需的，其他可选。   ||
|A/AAAA   |lyncdiscoverinternal..* \<sipdomain\>* <br/> lyncdiscoverinternal..* <span> </span>contoso<span></span>*   |HLB 前端池 VIP 或控制器 IP  <br/>  192.168.21.121  |"内部自动发现" Service1，是移动性支持所必需的。 如果使用内部 DNS 来解析移动设备，则它应指向外部 IP 或 DMZ VIP。  <br/> 对于 Web 服务，我们需要在前端池上使用 HLB，因为 HTTPS 无法利用 DNS。 对于前端池或控制器池，这应解析为 HLB VIP，或适用于 Standard edition server 或独立控制器服务器的常规 IP。   |Y   |
|CNAME   |lyncdiscoverinternal..* \<sipdomain\>* <br/> lyncdiscoverinternal.. *<span></span>contoso<span></span>*   |HLB FE 池 FQDN 或控制器 FQDN  <br/> Web-int<span></span><span></span>.com   |内部自动发现 Service1 <br/> 如果需要，可以将其作为 CNAME 而不是 A 记录来实现。   ||
|A/AAAA   |sip.* \<sipdomain\>* <br/> sip.* <span> </span>contoso<span></span>*  |前端池服务器 IP 地址（或每个控制器 IP 地址）  <br/>  DNS LB to *192.168.21.122 192.168.21.123 192.168.21.124*   |对于自动配置是必需的，请参阅[Skype For business 客户端的演练查找服务](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype) <br/> 一条记录或记录，指向内部网络上的前端池服务器或控制器服务器，或者客户端为外部时的访问边缘服务   |&#x2777;  |
|A/AAAA   |为 ucupdates-r2.-r2。* \<sipdomain\>* <br/> 为 ucupdates-r2.-r2。* <span> </span>contoso<span></span>*  |HLB FE 池 VIP 或控制器池 HLB VIP 或 SE/控制器服务器 IP  <br/>  192.168.21.121  |部署此记录是可选的 &#x2778;  ||
|SRV   |\_sipinternaltls.\_tcp。* \<sipdomain\> * <br/>端口5061 <br/>\_sipinternaltls.\_tcp。* <span> </span>contoso<span></span>* <br/>端口5061  |前端池 FQDN  <br/>*FE 池。<span> </span>contoso<span></span>*  |允许内部用户自动登录1到前端服务器/池或 SE 服务器/池，以便对登录的客户端请求进行身份验证和重定向。  |&#x2777; |
|A/AAAA |sipinternal.* \<sipdomain\>* <br/>sipinternal.<span> </span> *contoso<span></span>*  |前端池 FQDN  <br/>_FE 池。<span> </span>contoso<span></span>_  |内部用户访问 &#x2776;  |&#x2777;  |
|SRV   | \_ntp.\_udp。* \<sipdomain\> * <br/> \_ntp.\_udp。<span> </span> *contoso<span></span>*  |TimeServer FQDN  <br/> north-america.pool.ntp.org   |Lync Phone Edition 设备所需的 NTP 源   |这是支持桌面手机所必需的。   |
|SRV   |\_sipfederationtls.\_tcp。* \<sipdomain\> * <br/>\_sipfederationtls.\_tcp。<span> </span> *contoso<span></span>*  | 访问边缘服务 FQDN <br/> EdgePool-int<span></span>*<span></span>.com*  |为具有 IOS 或 Windows phone 移动客户端的每个 SIP 域创建一个 SRV 记录。   |对于移动客户端支持   |
|A/AAAA   |管理 URL  <br/>*Web-int<span></span><span></span>.com*  |HLB FE 池 VIP  <br/> 192.168.21.121   |Skype for Business Server 控制面板，请参阅[简单 url](dns.md#BK_Simple)  ||
|A/AAAA   |满足 URL  <br/>*Web-int<span></span><span></span>.com*  |HLB FE 池 VIP  <br/> 192.168.21.121   |联机会议，请参阅[简单 url](dns.md#BK_Simple)  ||
|A/AAAA   |电话拨入式 URL  <br/>*Web-int<span></span><span></span>.com*  |HLB FE 池 VIP  <br/> 192.168.21.121   |电话拨入式会议，请参阅[简单 url](dns.md#BK_Simple)  ||
|A/AAAA   |内部 Web 服务 FQDN  <br/>*Web-int<span></span><span></span>.com*  |HLB FE 池 VIP  <br/> 192.168.21.121   |Skype for business Web 应用使用的 skype for Business Web 服务   ||
|A/AAAA   |Office Web Apps Server 池 FQDN  <br/> OWA.<span> </span>contoso<span></span>   | Office Web Apps Server 池 VIP 地址 <br/> 192.168.1.5   |定义 Office Web Apps Server 池 FQDN   ||
|A/AAAA   | 内部 Web FQDN <br/> Web-int<span></span><span></span>.com   | 前端池 VIP 地址 <br/> 192.168.21.121   |定义 Skype for Business Web 应用使用的内部 Web FQDN  <br/> 如果在此池上使用 DNS 负载平衡，则前端池和内部 web 场不能具有相同的 FQDN。   ||

&#x2776; 客户端使用它来发现前端服务器或前端池，并进行身份验证并以用户身份登录。 有关这方面的更多详细信息，请在[Skype for business 客户端演练中查找服务](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)。

&#x2777; 只有在 Lync 2013 之前和桌面手机上支持旧版客户端时，才需要这样做。

&#x2778; 在统一通信设备已打开但用户从未登录到设备的情况下，A 记录允许设备发现服务器托管设备更新 Web 服务并获取更新。 否则，设备在用户首次登录时通过带内设置获得服务器信息。

下图显示了一个示例，其中包含内部和外部 DNS 记录，以及周围表格中显示的许多记录：

**使用公用 IPv4 地址的边缘网络图**

![DNS 网络图的示例](../../media/2cc9546e-5560-4d95-8fe4-65a792a0e9c3.png)

**外围网络 DNS 映射（内部和外部接口）**

|记录类型|值|解析为|用途|必需|
|:--- |:--- |:--- |:--- |:--- |
|A/AAAA   |内部边缘池 FQDN  <br/>*EdgePool-int<span></span><span></span>.com*  |面向内部的边缘池 IP 地址  <br/> 172.25.33.10、172.25.33.11   |合并的边缘池内部接口 IP 地址   |Y   |
|A/AAAA   |边缘服务器 FQDN  <br/>*缺点-1。<span> </span>contoso<span></span>*  |边缘池中的服务器的面向内部的服务器 IP  <br/> 172.25.33.10   |为池中的每台服务器创建一条记录，并将服务器 FQDN 指向其在池中的内部服务器节点 IP，请参阅[边缘服务器池上的 DNS 负载平衡](load-balancing.md#BK_Edge)。   |Y   |
|A/AAAA   |访问边缘服务池 FQDN  <br/>*Access1.<span> </span>contoso<span></span>*  |访问边缘服务池外部 IP 地址  <br/> 131.107.16.10, 131.107.16.11   |访问边缘服务为出站和入站会话初始协议（SIP）流量提供单个受信任的连接点。   |Y   |
|A/AAAA   |Web 会议边缘服务池 FQDN  <br/>*Webcon1.<span> </span>contoso<span></span>*  |Web 会议边缘服务的外部 IP 地址  <br/> 131.107.16.90, 131.107.16.91   |Web 会议边缘服务使外部用户能够加入托管在内部 Skype for Business Server 环境中的会议。   |Y   |
|A/AAAA   |*av （\<sip）-\>域*池 FQDN <br/>*AV1.<span> </span>contoso<span></span>*  |A/V 边缘外部 IP 地址  <br/> 131.107.16.170, 131.107.16.171   |A/V 边缘服务可向外部用户提供音频、视频、应用程序共享和文件传输。   |Y   |
|CNAME   |sip.* \<sipdomain\>* <br/> sip.* <span> </span>contoso<span></span>*  |外部访问边缘池 FQDN  <br/>*Access1.<span> </span>contoso<span></span>*  |查找边缘服务器池。 请参阅[Skype For business 客户端的演练查找服务](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)  |Y   |
|SRV   |\_sip.\_tls。* \<sipdomain\> * <br/>\_sip.\_tls。<span> </span> *contoso<span></span>*  |外部访问边缘 FQDN  <br/>_Access1.<span> </span>contoso<span></span>_  |用于外部用户访问。 请参阅[Skype For business 客户端的演练查找服务](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)  |Y   |
|SRV   |\_sipfederationtls.\_tcp。* \<sipdomain\> * <br/>\_sipfederationtls.\_tcp。<span> </span> *contoso<span></span>*  |外部访问边缘 FQDN  <br/>*Access1.<span> </span>contoso<span></span>*  |用于联盟和公共 IM 连接   |&#x2776;  |
|SRV   |\_xmpp-服务器。\_tcp。*<sipdomain\> * <br/>\_xmpp-服务器。\_tcp。* <span> </span>contoso<span></span>*  |外部访问边缘 FQDN  <br/>*Access1.<span> </span>contoso<span></span>*  |XMPP 代理服务接受并发送可扩展消息和状态协议（XMPP）消息，并发送到已配置的 XMPP 联盟伙伴。   |Y，若要部署联合身份验证，则可选  <br/> 在 Skype for Business Server 2019 中不可用。|
|SRV   |\_sipfederationtls.\_tcp。* \<sipdomain\> * <br/>\_sipfederationtls.\_tcp。* <span> </span>contoso<span></span>*  |外部访问边缘 FQDN  <br/>*Access1.<span> </span>contoso<span></span>*  |若要支持推送通知服务和 Apple 推送通知服务，请为每个 SIP 域创建一个 SRV 记录。 &#x2778;  ||
|A/AAAA   |外部前端池 web 服务 FQDN  <br/>*Web-外部<span></span><span></span>-.com*  |反向代理公共 IP 地址（代理到前端池的外部 Web 服务 VIP） &#x2776; <br/> 131.107.155.1 代理到192.168.21.120   |Skype for Business Web 应用使用的前端池外部接口   |Y   |
|A/AAAA/CNAME   |lyncdiscover..* \<sipdomain\>* <br/> lyncdiscover..* <span> </span>contoso<span></span>*  |反向代理公用 IP 地址，解析为控制器池的外部 Web 服务 VIP （如果有），如果您没有控制器，则解析为前端池的外部 Web 服务 VIP （如果有的话） &#x2777; <br/> 131.107.155.1 代理到192.168.21.120   | 客户端自动发现的外部记录，也可由反向代理服务器解析的移动性、Skype for Business Web 应用和计划程序 Web 应用程序。 <br/> 若要支持推送通知服务和 Apple 推送通知服务，请为拥有 Microsoft Lync 移动客户端的每个 SIP 域创建一个 SRV 记录。 3   |Y   |
|A/AAAA   |法规.* \<sipdomain\>* <br/> 法规.* <span> </span>contoso<span></span>*  |反向代理公用 IP 地址，解析为前端池的外部 Web 界面  <br/> 131.107.155.1 代理到192.168.21.120   |到 Skype for Business Web 服务的代理  <br/> 请参阅[简单 url](dns.md#BK_Simple)  |Y   |
|A/AAAA   |拨入*\<sipdomain\>* <br/> "*<span></span>contoso<span></span>.com"*  |反向代理公用 IP 地址（指向前端池的外部 Web 界面的代理）  <br/> 131.107.155.1 代理到192.168.21.120   |到 Skype for Business Web 服务的代理  <br/> 请参阅[简单 url](dns.md#BK_Simple)  |Y   |
|A/AAAA   |Office Web Apps Server 池 FQDN  <br/> OWA.<span> </span>contoso<span></span>   | 反向代理公共 IP 地址（指向 Office Web Apps Server 的外部 Web 界面的代理） <br/> 131.107.155.1 代理到192.168.1。5   | Office Web Apps Server 池 VIP 地址 <br/> 192.168.1.5   |定义 Office Web Apps Server 池 FQDN   |

部署联合身份验证所需的 &#x2776;，否则为可选。

&#x2777; 客户端使用它来发现前端服务器或前端池，并进行身份验证并以用户身份登录。

&#x2778; 此要求仅适用于基于 Apple 或 Microsoft 的移动设备上的客户端。 Android 和 Nokia Symbian 设备不使用推送通知。

 有关边缘服务器和外围网络的详细信息，请参阅边缘服务器[DNS 规划](../../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#DNSPlan)内容。

> [!IMPORTANT]
> Skype for Business Server 支持使用 IPv6 寻址。 有关更多详细信息，请参阅[在 Skype For business 中规划 IPv6](ipv6.md) 。

> [!IMPORTANT]
> 有关 Fqdn 的更多详细信息，请参阅[DNS 基础](basics.md)。

**拆分大脑 DNS** 
 <a name="BK_split"> </a>

拆分大脑 DNS 是一种 DNS 配置，其中有两个具有相同命名空间的 DNS 区域。 第一个 DNS 区域处理内部请求，而第二个 DNS 区域处理外部请求，如这些表中所述。 有关详细信息，请参阅[裂脑 DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS)。

## <a name="hybrid-considerations"></a>混合注意事项
<a name="BK_Hybrid"> </a>

如果您计划让一些用户驻留在联机状态，并且某些用户驻留在本地，请参阅混合连接规划一文[Skype For business server 2019](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json)。 你需要将 DNS 配置为适用于 Skype for Business Server 2015 的 DNS，同时添加其他 DNS 记录。

您还应参阅 at 中[https://aka.ms/o365ips](https://aka.ms/o365ips)的 "Office 365 URL 和 IP 地址范围" 以确认您的用户是否有权访问他们所需的联机资源。

## <a name="simple-urls"></a>简单 URL
<a name="BK_Simple"> </a>

统一资源定位器（URL）是对指定其在计算机网络上的位置以及用于检索它的协议的 web 资源的引用。

Skype for Business Server 支持使用三个 "简单" Url 访问服务：

- 将 "**开会**" 用作网站中所有会议的基 URL。 "满足" 简单 URL 的一个示例是 https<span></span>//<span></span>：满足。<span> </span>contoso<span></span>。 特定会议的 URL 可能是 https：<span></span>//<span></span>满足。<span> </span>contoso<span></span>/_username_/7322994。

    使用 "满足简单 URL"，可轻松理解加入会议的链接，并且易于沟通。

- 通过**拨**入，可以访问 "电话拨入式会议设置" 网页。 此页显示会议的拨入号码及其可用语言、分配的会议信息（即，对于不需要预定的会议）以及会议中的 DTMF 控制，并支持对个人标识号 (PIN) 和分配的会议信息的管理。 拨入简单 URL 包含在所有会议邀请中，因此要拨号加入会议的用户可以访问所需的电话号码和 PIN 信息。 拨入式简单 URL 的一个示例是 https://<span></span>拨入。<span> </span>contoso<span></span>。

- **管理员**可以快速访问 Skype For Business Server 控制面板。 通过在组织的防火墙中的任何计算机上，管理员都可以通过在浏览器中键入管理员简单的 URL 来打开 Skype for Business Server 控制面板。 管理简单 URL 是组织内部的。 管理员简单 URL 的一个示例是 https://<span></span>管理员。<span> </span>contoso<span></span>。

在[Skype for Business Server 中的简单 url 的 DNS 要求](simple-urls.md)中更详细地讨论了简单 url。

## <a name="dns-by-server-role"></a>按服务器角色的 DNS
<a name="BK_Servers"> </a>

您可以根据需要设置这些池和服务器的名称，但使其易于记忆并反映其在系统中的功能。

### <a name="dns-records-for-individual-servers-or-pools"></a>单个服务器或池的 DNS 记录

这些一般记录要求适用于 Skype for Business 使用的任何服务器角色。 池是一组运行相同服务的服务器，它们协同工作以处理通过负载平衡器定向给它们的客户端请求。 有关详细信息，请参阅[Skype For business 的负载平衡要求](load-balancing.md)

**服务器/池角色的 DNS 记录要求（假定 DNS 负载平衡）**

|部署方案|DNS 要求|
|:-----|:-----|
|一台服务器：  <br/> 持久聊天、控制器、中介服务器、前端服务器   |将服务器的完全限定的域名 (FQDN) 解析为其 IP 地址的内部 A 记录。  <br/> ServerRole.<span> </span>contoso<span></span>.com 10.10.10。0   |
|池  <br/> 持久聊天、控制器、边缘服务器、中介服务器、前端   |将池中每个服务器节点的完全限定的域名（FQDN）解析为其 IP 地址的内部 A 记录。  <br/>**示例** <br/> ServerRole01.<span> </span>contoso<span></span>; .com 10.10.10。1  <br/> ServerRole02.<span> </span>contoso<span></span>.com 10.10.10。2  <br/> 将池的完全限定域名（FQDN）解析为池中的服务器节点的 IP 地址的多个内部 A 记录。  <br/>**示例** <br/> ServerPool.<span> </span>contoso<span></span>; .com 10.10.10。1  <br/> ServerPool.<span> </span>contoso<span></span>.com 10.10.10。2   |

### <a name="edge-server-specific-dns-topics"></a>边缘服务器特定的 DNS 主题

 若要规划边缘服务器部署，请参阅 Plan for skype for business [server 2015 中的边缘服务器部署](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md)，以及[适用于 Skype for business Server 2015 的高级边缘服务器 DNS 规划](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md)，其中包含以下部分

- [DNS 灾难恢复](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSDR)

- [DNS load balancing － DNS 负载平衡](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB)

- [不带分裂 DNS 的自动配置](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#NoSplitBrainDNS)

- [裂脑 DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS)

- [Skype for Business 客户端查找服务的演练](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)


