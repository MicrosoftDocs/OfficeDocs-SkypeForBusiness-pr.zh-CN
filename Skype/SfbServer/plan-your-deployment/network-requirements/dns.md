---
title: Skype for business 服务器的 DNS 要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c50e38d2-b1e4-4ebd-8dc3-85d4ae7a76ee
description: '摘要: 在实施 Skype for Business 服务器之前, 请查看本主题中的 DNS 注意事项。'
ms.openlocfilehash: 5e6bb5866cfc52dc02a1fc48c19b1f43af6077f7
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/25/2019
ms.locfileid: "35221222"
---
# <a name="dns-requirements-for-skype-for-business-server"></a>Skype for business 服务器的 DNS 要求

**摘要:** 在实施 Skype for Business 服务器之前, 请查看本主题中的 DNS 注意事项。

本文仅介绍组织内部部署网络上的 Skype for business 服务器部署的 DNS 规划。 对于 Skype for Business Online, 请参阅 "Office 365 Url 和 IP 地址范围" [https://aka.ms/o365ips](https://aka.ms/o365ips)。

域名服务 (DNS) 服务器映射主机名 (如 www)。<span> </span>对于<span></span>IP 地址, contoso (假定为 web 服务器) (如 10.10.10.10)。 它帮助客户和相互依赖的服务器在网络上相互通信。 设置 Skype for Business Server 2015 的实现时, 你需要确保新的服务器名称的映射 (通常反映其将占用的角色) 与分配给它们的 IP 地址相匹配。

虽然这看起来可能有点令人望而生畏, 但这可能会使规划的工作量非常繁重, 因为它可以使用[Skype For Business Server 2015 规划工具](https://www.microsoft.com/en-us/download/details.aspx?id=50357)完成。 完成要使用的功能的向导问题后, 对于你定义的每个网站, 你可以在 Edge 管理报表内查看 DNS 报表, 并使用其中列出的信息创建你的 DNS 记录。 您还可以调整所使用的许多名称和 IP 地址, 有关详细信息, 请参阅[查看 DNS 报告](../../management-tools/planning-tool/review-the-administrator-reports.md#DNS_Report)。 请记住, 你可以将 Edge 管理员报表导出为 Excel 电子表格, 并且 DNS 报表将是文件中的工作表之一。 虽然此工具包括[Skype For Business Server 2019 中弃用](../../../SfBServer2019/deprecated.md)的功能, 但仍可用于创建初始计划 (如果未选择这些功能)

按照[创建 skype for Business 服务器的 DNS 记录](../../deploy/install/create-dns-records.md)和构建 skype For business 服务器的拓扑中所述安装新实施时, 我们认为你可以选择使用 Windows Server 中内置的 DNS 功能2016或第三方 DNS 程序包, 因此我们将在本文的常规内容中 (而不是特定的) 继续讨论。 我们将详细介绍所需的内容, 以及满足该需求的方式是您做出的决定。

经验丰富的 Skype for business、Lync 和 Office 通信套件管理员可能会发现下表有用。 如果表中的内容混乱, 后面的部分或文章将 shed 以下概念:

## <a name="summary-tables"></a>摘要表
<a name="BK_Summary"> </a>

下表显示了 Skype for Business 服务器用于向用户提供服务的 DNS 记录。 某些选项是可选的, 因为它们仅需要支持某些功能, 如果不需要这些功能, 则可以跳过这些功能。 仅限内部访问所需的 DNS 记录位于第一个表中, 并且允许内部和外部访问的部署将需要两个表中的记录。

**内部 DNS 映射**

|记录类型|值|解析为|用途|必需|
|:-----|:-----|:-----|:-----|:-----|
|A/AAAA   |前端池 FQDN  <br/> *FE-池。<span> </span>contoso<span></span>*   |前端池服务器 IP 地址  <br/>  DNS 磅到*192.168.21.122 192.168.21.123 192.168.21.124*   |前端池的 DNS 负载平衡。 将前端池名称映射到一组 IP 地址。  <br/> 请参阅[在前端池和控制器池上部署 DNS 负载平衡](load-balancing.md#BK_FE_Dir)  |Y   |
|A/AAAA   | 池或独立服务器中每个前端服务器或标准版服务器的 FQDN <br/>  *FE01.<span> </span>contoso。<span> </span>com FE02。<span> </span>contoso<span></span>FE03。<span> </span>contoso<span></span>*   |每个服务器对应的 IP  <br/> *192.168.21.122 192.168.21.123 192.168.21.124*   |将服务器名称映射到其 IP 地址。   |Y   |
|A/AAAA   |企业版池内部 Web 服务替代 FQDN  <br/> *Web int<span></span><span></span>.com*   |前端服务器内部 Web 服务的 HLB VIP  <br/> *192.168.21.120*   |启用客户端到服务器 web 流量 (如下载 Skype for Business Web 应用) 所需。 对于移动客户端也是必需的。   |Y   |
|A/AAAA   |企业版池外部 Web 服务替代 FQDN  <br/> *Web-ext<span></span><span></span>.com*   |前端服务器外部 Web 服务的 HLB VIP  <br/>*68.123.56.90*   |启用客户端到服务器 web 流量 (如下载 Skype for Business Web 应用) 所需。 如果移动客户端将内部解析 DNS, 则是必需的。 可以解析为 DMZ 反向代理 IP 或 Internet IP。   ||
|A/AAAA   | 后端服务器 SQL Server FQDN <br/> *SQL1.<span> </span>contoso<span></span>*   |服务器 IP 地址  <br/> *192.168.11.90*   |将使用前端池的后端 SQL server 的服务器名称映射到其 IP 地址   ||
|A/AAAA   |后端服务器镜像 SQL Server FQDN  <br/> *SQL2.<span> </span>contoso<span></span>*   |服务器 IP 地址  <br/> *192.168.11.91*   |将使用前端池的后端 SQL 镜像服务器的服务器名称映射到其 IP 地址   ||
|A/AAAA   |控制器池 FQDN  <br/>**注意:** 在使用独立控制器服务器时不适用 <br/> *DirPool.<span> </span>contoso<span></span>*   |控制器池 IP 地址  <br/> DNS 磅到*192.168.21.132、192.168.21.133、192.168.21.134*   |控制器池服务器的 DNS 负载平衡。 将控制器池的池名称映射到 IP 地址, 请参阅[在前端池和控制器池上部署 DNS 负载平衡](load-balancing.md#BK_FE_Dir) <br/> Director 可以对用户进行身份验证, 并且是可选的。   ||
|A/AAAA   |控制器 FQDN   |每个控制器服务器的服务器 IP 地址   |将 Director 的池名称映射到 IP 地址, 请参阅[在前端池和控制器池上部署 DNS 负载平衡](load-balancing.md#BK_FE_Dir)  ||
|A/AAAA   |中介服务器池 FQDN   |池 IP 地址   |中介服务器角色是可选的。 你可以将中介服务器提供的服务与前端服务器或池共同定位。 请参阅[在中介服务器池上使用 DNS 负载平衡](load-balancing.md#BK_Mediation)  ||
|A/AAAA   |中介服务器 FQDN   |服务器 IP 地址   |你可以将中介服务器提供的服务与前端服务器或池共同定位。 请参阅[在中介服务器池上使用 DNS 负载平衡](load-balancing.md#BK_Mediation)  ||
|A/AAAA   |持久聊天服务器 FQDN   |持久聊天服务器 IP 地址   |持久聊天服务器是持久聊天功能所必需的, 否则是可选的。   ||
|A/AAAA   |lyncdiscoverinternal.* \<sipdomain\>* <br/> lyncdiscoverinternal.* <span> </span>contoso<span></span>*   |HLB 前端池 VIP 或控制器 IP  <br/>  192.168.21.121  |"移动支持" 所需的内部自动发现 Service1。 如果使用内部 DNS 解析移动设备, 则它应指向外部 IP 或 DMZ VIP。  <br/> 对于 Web 服务, 我们需要前端池中的 HLB, 因为 HTTPS 无法利用 DNS。 对于前端池或控制器池, 这应该解析为 HLB VIP, 或适用于标准版服务器或独立控制器服务器的常规 IP。   |Y   |
|CNAME   |lyncdiscoverinternal.* \<sipdomain\>* <br/> lyncdiscoverinternal. *<span></span>contoso<span></span>*   |HLB FE 池 FQDN 或控制器 FQDN  <br/> Web int<span></span><span></span>.com   |内部自动发现 Service1 <br/> 如果需要, 你可以将其作为 CNAME (而不是 A 记录) 实现。   ||
|A/AAAA   |sip.* \<sipdomain\>* <br/> sip.* <span> </span>contoso<span></span>*  |前端池服务器 IP 地址 (或每个控制器 IP 地址)  <br/>  DNS 磅到*192.168.21.122 192.168.21.123 192.168.21.124*   |需要自动配置时, 请参阅[Skype For business 客户端查找服务的演练](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype) <br/> 一个记录或记录, 指向内部网络上的前端池服务器或控制器服务器, 或者当客户端为外部客户端时的访问边缘服务   |&#x2777;  |
|A/AAAA   |ucupdates-r2。* \<sipdomain\>* <br/> ucupdates-r2。* <span> </span>contoso<span></span>*  |HLB FE 池 VIP 或控制器池 HLB VIP 或 SE/控制器服务器 IP  <br/>  192.168.21.121  |部署此记录是可选的 &#x2778;  ||
|SRV   |\_sipinternaltls.\_tcp。* \<sipdomain\> * <br/>端口5061 <br/>\_sipinternaltls.\_tcp。* <span> </span>contoso<span></span>* <br/>端口5061  |前端池 FQDN  <br/>*FE-池。<span> </span>contoso<span></span>*  |允许内部用户自动登录1到前端服务器/池或 SE 服务器/池, 以便对登录的客户端请求进行身份验证和重定向。  |&#x2777; |
|A/AAAA |sipinternal.* \<sipdomain\>* <br/>sipinternal.<span> </span> *contoso<span></span>*  |前端池 FQDN  <br/>_FE-池。<span> </span>contoso<span></span>_  |内部用户访问 &#x2776;  |&#x2777;  |
|SRV   | \_ntp.\_udp。* \<sipdomain\> * <br/> \_ntp.\_udp。<span> </span> *contoso<span></span>*  |TimeServer FQDN  <br/> north-america.pool.ntp.org   |Lync Phone Edition 设备所需的 NTP 源   |这是支持桌面手机所必需的。   |
|SRV   |\_sipfederationtls.\_tcp。* \<sipdomain\> * <br/>\_sipfederationtls.\_tcp。<span> </span> *contoso<span></span>*  | Access Edge 服务 FQDN <br/> EdgePool-int<span></span>*<span></span>.com*  |为具有 IOS 或 Windows phone 移动客户端的每个 SIP 域创建一个 SRV 记录。   |对于移动客户端支持   |
|A/AAAA   |管理员 URL  <br/>*Web int<span></span><span></span>.com*  |HLB FE 池 VIP  <br/> 192.168.21.121   |Skype for business Server "控制面板", 请参阅[简单 url](dns.md#BK_Simple)  ||
|A/AAAA   |满足 URL  <br/>*Web int<span></span><span></span>.com*  |HLB FE 池 VIP  <br/> 192.168.21.121   |联机会议, 请参阅[简单 url](dns.md#BK_Simple)  ||
|A/AAAA   |拨入式 URL  <br/>*Web int<span></span><span></span>.com*  |HLB FE 池 VIP  <br/> 192.168.21.121   |电话拨入式会议, 请参阅[简单 url](dns.md#BK_Simple)  ||
|A/AAAA   |内部 Web 服务 FQDN  <br/>*Web int<span></span><span></span>.com*  |HLB FE 池 VIP  <br/> 192.168.21.121   |Skype for business Web 应用使用的 skype for business Web 服务   ||
|A/AAAA   |Office Web Apps 服务器池 FQDN  <br/> OWA.<span> </span>contoso<span></span>   | Office Web Apps 服务器池 VIP 地址 <br/> 192.168.1.5   |定义 Office Web Apps 服务器池 FQDN   ||
|A/AAAA   | 内部 Web FQDN <br/> Web int<span></span><span></span>.com   | 前端池 VIP 地址 <br/> 192.168.21.121   |定义 Skype for business Web 应用使用的内部 Web FQDN  <br/> 如果在此池中使用 DNS 负载平衡, 则您的前端池和内部 web 场不能具有相同的 FQDN。   ||

客户端使用 &#x2776; 发现前端服务器或前端池, 并以用户身份进行身份验证和登录。 有关详细信息的详细信息, 请[查看 Skype For business 客户端查找服务的演练](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)。

&#x2777; 只有在 Lync 2013 和桌面手机上支持旧客户端时才需要此功能。

&#x2778; 在已打开统一通信设备但用户从未登录到设备的情况下, A 记录允许设备发现服务器托管设备更新 Web 服务并获取更新。 否则, 在用户第一次登录时, 设备将通过带内预配获取服务器信息。

下图显示了一个示例, 其中包括内部和外部 DNS 记录以及周围表中显示的许多记录:

**使用公用 IPv4 地址的 Edge 网络图**

![DNS 网络图表示例](../../media/2cc9546e-5560-4d95-8fe4-65a792a0e9c3.png)

**外围网络 DNS 映射 (内部和外部接口)**

|记录类型|值|解析为|用途|必需|
|:--- |:--- |:--- |:--- |:--- |
|A/AAAA   |内部边缘池 FQDN  <br/>*EdgePool-int<span></span><span></span>.com*  |面向内部的边缘池 IP 地址  <br/> 172.25.33.10, 172.25.33.11   |合并的边缘池内部接口 IP 地址   |Y   |
|A/AAAA   |边缘服务器 FQDN  <br/>*缺点-1。<span> </span>contoso<span></span>*  |边缘池中的服务器的面向内部的服务器 IP  <br/> 172.25.33.10   |为池中的每台服务器创建记录, 并且服务器 FQDN 指向其在池中的内部服务器节点 IP, 请参阅[Edge 服务器池上的 DNS 负载平衡](load-balancing.md#BK_Edge)。   |Y   |
|A/AAAA   |Access Edge 服务池 FQDN  <br/>*Access1.<span> </span>contoso<span></span>*  |Access Edge 服务池外部 IP 地址  <br/> 131.107.16.10, 131.107.16.11   |Access Edge 服务为出站和入站会话初始协议 (SIP) 流量提供单个受信任的连接点。   |Y   |
|A/AAAA   |网络会议边缘服务池 FQDN  <br/>*Webcon1.<span> </span>contoso<span></span>*  |网络会议边缘服务外部 IP 地址  <br/> 131.107.16.90, 131.107.16.91   |Web 会议 Edge 服务允许外部用户加入托管在内部 Skype for Business 服务器环境中的会议。   |Y   |
|A/AAAA   |*av (\<sip)-\>域*池 FQDN <br/>*AV1.<span> </span>contoso<span></span>*  |A/V 边缘外部 IP 地址  <br/> 131.107.16.170, 131.107.16.171   |A/V 边缘服务使音频、视频、应用程序共享和文件传输可供外部用户使用。   |Y   |
|CNAME   |sip.* \<sipdomain\>* <br/> sip.* <span> </span>contoso<span></span>*  |外部访问边缘池 FQDN  <br/>*Access1.<span> </span>contoso<span></span>*  |查找边缘服务器池。 查看[查找服务的 Skype For business 客户端演练](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)  |Y   |
|SRV   |\_sip.\_tls。* \<sipdomain\> * <br/>\_sip.\_tls。<span> </span> *contoso<span></span>*  |外部访问边缘 FQDN  <br/>_Access1.<span> </span>contoso<span></span>_  |用于外部用户访问。 查看[查找服务的 Skype For business 客户端演练](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)  |Y   |
|SRV   |\_sipfederationtls.\_tcp。* \<sipdomain\> * <br/>\_sipfederationtls.\_tcp。<span> </span> *contoso<span></span>*  |外部访问边缘 FQDN  <br/>*Access1.<span> </span>contoso<span></span>*  |用于联盟和公共 IM 连接   |&#x2776;  |
|SRV   |\_xmpp-服务器。\_tcp。*<sipdomain\> * <br/>\_xmpp-服务器。\_tcp。* <span> </span>contoso<span></span>*  |外部访问边缘 FQDN  <br/>*Access1.<span> </span>contoso<span></span>*  |XMPP 代理服务接受并向已配置的 XMPP 联盟合作伙伴发送可扩展消息和状态协议 (XMPP) 消息。   |Y, 用于部署联合身份验证, 否则为可选  <br/> 在 Skype for Business Server 2019 中不可用。|
|SRV   |\_sipfederationtls.\_tcp。* \<sipdomain\> * <br/>\_sipfederationtls.\_tcp。* <span> </span>contoso<span></span>*  |外部访问边缘 FQDN  <br/>*Access1.<span> </span>contoso<span></span>*  |若要支持推送通知服务和 Apple 推送通知服务, 请为每个 SIP 域创建一个 SRV 记录。 &#x2778;  ||
|A/AAAA   |外部前端池 web 服务 FQDN  <br/>*Web-ext<span></span><span></span>.com*  |反向代理公共 IP 地址, 代理到你的前端池的外部 Web 服务 VIP &#x2776; <br/> 131.107.155.1 代理到192.168.21.120   |Skype for Business Web 应用使用的前端池外部接口   |Y   |
|A/AAAA/CNAME   |lyncdiscover.* \<sipdomain\>* <br/> lyncdiscover.* <span> </span>contoso<span></span>*  |反向代理公共 IP 地址、解析你的控制器池的外部 Web 服务 VIP (如果有), 或者对于你的前端池 (如果你没有 Director &#x2777;)。 <br/> 131.107.155.1 代理到192.168.21.120   | 客户端自动发现的外部记录, 也由反向代理服务器解决的移动性、Skype for business Web 应用和计划程序 Web 应用的使用 <br/> 若要支持推送通知服务和 Apple 推送通知服务, 请为具有 Microsoft Lync 移动客户端的每个 SIP 域创建一个 SRV 记录。 3  |Y   |
|A/AAAA   |会议.* \<sipdomain\>* <br/> 会议.* <span> </span>contoso<span></span>*  |反向代理公共 IP 地址, 解析为前端池的外部 Web 界面  <br/> 131.107.155.1 代理到192.168.21.120   |代理到 Skype for Business Web 服务  <br/> 请参阅[简单 url](dns.md#BK_Simple)  |Y   |
|A/AAAA   |拨入*\<sipdomain\>* <br/> *<span></span>contoso<span></span>.com*  |反向代理公共 IP 地址, 指向前端池的外部 Web 界面的代理  <br/> 131.107.155.1 代理到192.168.21.120   |代理到 Skype for Business Web 服务  <br/> 请参阅[简单 url](dns.md#BK_Simple)  |Y   |
|A/AAAA   |Office Web Apps 服务器池 FQDN  <br/> OWA.<span> </span>contoso<span></span>   | 反向代理公共 IP 地址, 代理到 Office Web Apps 服务器的外部 Web 界面 <br/> 131.107.155.1 代理到192.168.1。5   | Office Web Apps 服务器池 VIP 地址 <br/> 192.168.1.5   |定义 Office Web Apps 服务器池 FQDN   |

部署联合身份验证所需 &#x2776;, 否则为可选。

客户端使用 &#x2777; 发现前端服务器或前端池, 并以用户身份进行身份验证和登录。

&#x2778; 此要求仅适用于 Apple 或基于 Microsoft 的移动设备上的客户端。 Android 和 Nokia Symbian 设备不使用推送通知。

 有关边缘服务器和外围网络的详细信息, 请参阅边缘服务器[DNS 规划](../../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#DNSPlan)内容。

> [!IMPORTANT]
> Skype for Business 服务器支持使用 IPv6 寻址。 有关详细信息, 请参阅[Skype For business 中的 IPv6 计划](ipv6.md)。

> [!IMPORTANT]
> 有关 Fqdn 的详细信息, 请参阅[DNS 基础知识](basics.md)。

**拆分大脑 DNS** 
 <a name="BK_split"> </a>

分裂的大脑 DNS 是具有相同命名空间的两个 DNS 区域的 DNS 配置。 第一个 DNS 区域处理内部请求, 而第二个 DNS 区域处理外部请求, 如这些表中所述。 有关详细信息, 请参阅[裂脑 DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS)。

## <a name="hybrid-considerations"></a>混合注意事项
<a name="BK_Hybrid"> </a>

如果你计划让某些用户驻留在联机状态, 并且某些用户驻留在本地, 请参阅混合连接计划一文[Skype For business server 2019](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json)。 您需要将 DNS 配置为 Skype for business Server 2015 的普通 DNS, 还需要添加其他 DNS 记录。

您还应参阅 "Office 365 Url 和 IP 地址范围" [https://aka.ms/o365ips](https://aka.ms/o365ips)以确认您的用户是否有权访问他们需要的联机资源。

## <a name="simple-urls"></a>简单 URL
<a name="BK_Simple"> </a>

统一资源定位器 (URL) 是对 web 资源的引用, 该资源指定其在计算机网络上的位置以及用于检索它的协议。

Skype for Business 服务器支持使用三个 "简单" Url 访问服务:

- "**开会**" 用作网站中所有会议的基本 URL。 一个 "满足" 简单 URL 的示例是 https<span></span>//<span></span>: "满足"。<span> </span>contoso<span></span>。 特定会议的 URL 可能是 https:<span></span>//<span></span>开会。<span> </span>contoso<span></span>/_username_/7322994。

    通过 "满足简单 URL", 指向加入会议的链接易于理解且易于沟通。

- 通过**拨入功能**, 可以访问 "电话拨入式会议设置" 网页。 此页面显示会议拨入号码, 其中包含其可用语言、分配的会议信息 (即, 对于不需要安排的会议) 和会议 DTMF 控件, 并支持个人识别码的管理 (PIN) 和分配的会议信息。 拨入式简单 URL 包含在所有会议邀请中, 以便希望拨入会议的用户可以访问必要的电话号码和 PIN 信息。 拨入式简单 URL 的一个示例是 https://<span></span>拨入。<span> </span>contoso<span></span>。

- **管理员**可快速访问 Skype For Business 服务器控制面板。 在你组织的防火墙内的任何计算机中, 管理员都可以通过在浏览器中键入管理员简单的 URL 来打开 Skype for business 服务器的控制面板。 管理员简单的 URL 是您的组织内部的。 管理员简单 URL 的一个示例是 https://<span></span>管理员。<span> </span>contoso<span></span>。

在[Skype for Business 服务器的简单 url 的 DNS 要求](simple-urls.md)中将更详细地讨论简单的 url。

## <a name="dns-by-server-role"></a>按服务器角色的 DNS
<a name="BK_Servers"> </a>

您可以根据需要设置这些池和服务器的名称, 但使它们便于记忆并反映其在系统中的功能。

### <a name="dns-records-for-individual-servers-or-pools"></a>单独服务器或池的 DNS 记录

这些一般记录要求适用于 Skype for Business 使用的任何服务器角色。 池是运行相同服务的一组服务器, 它们协同工作以处理通过负载平衡器定向到它们的客户端请求。 有关详细信息, 请参阅[Skype For business 的负载平衡要求](load-balancing.md)

**服务器/池角色的 DNS 记录要求 (假定 DNS 负载平衡)**

|部署方案|DNS 要求|
|:-----|:-----|
|一台服务器:  <br/> 持久聊天、控制器、中介服务器、前端服务器   |将服务器的完全限定的域名 (FQDN) 解析为其 IP 地址的内部 A 记录。  <br/> ServerRole.<span> </span>contoso<span></span>10.10.10。0   |
|池  <br/> 持久聊天, 控制器, 边缘服务器, 中介服务器, 前端   |一个内部 A 记录, 可将池中的每个服务器节点的完全限定的域名 (FQDN) 解析为其 IP 地址。  <br/>**示例** <br/> ServerRole01.<span> </span>contoso<span></span>.com 的10.10.10。1  <br/> ServerRole02.<span> </span>contoso<span></span>10.10.10。2  <br/> 将池的完全限定的域名 (FQDN) 解析为池中的服务器节点的 IP 地址的多个内部 A 记录。  <br/>**示例** <br/> ServerPool.<span> </span>contoso<span></span>.com 的10.10.10。1  <br/> ServerPool.<span> </span>contoso<span></span>10.10.10。2   |

### <a name="edge-server-specific-dns-topics"></a>边缘服务器特定的 DNS 主题

 若要规划 edge 服务器部署, 请查看[skype for Business server 2015 中的边缘服务器部署计划](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md), 以及[适用于 Skype for business Server 2015 的高级边缘服务器 DNS 规划](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md), 其中包含以下部分

- [DNS disaster recovery](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSDR)

- [DNS load balancing](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB)

- [Automatic configuration without split-brain DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#NoSplitBrainDNS)

- [Split-brain DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS)

- [Walkthrough of Skype for Business clients locating services](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)


