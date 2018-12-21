---
title: Skype for Business Server 的 DNS 要求
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c50e38d2-b1e4-4ebd-8dc3-85d4ae7a76ee
description: 摘要： 实现 Skype 业务服务器之前查看本主题中的 DNS 注意事项。
ms.openlocfilehash: 8f47d7de61521c3908a8094bb7c6c866a55c4842
ms.sourcegitcommit: 81b38b389bfe3acd1aa13ce61c221b7b368c0e2d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2018
ms.locfileid: "27382852"
---
# <a name="dns-requirements-for-skype-for-business-server"></a>Skype for Business Server 的 DNS 要求

**摘要：** 实现 Skype 业务服务器之前查看本主题中的 DNS 注意事项。

本文仅介绍 DNS 规划的 Skype 业务服务器部署在组织的内部网络。 有关业务 online Skype 请参阅"Office 365 Url 和 IP 地址范围"在[https://aka.ms/o365ips](https://aka.ms/o365ips)。

域名服务 (DNS) 服务器映射主机名 (如 www。<span> </span>contoso<span></span>.com、 大概 web 服务器) 为 IP 地址 （例如，10.10.10.10)。 帮助客户端和相互依赖服务器在网络上互相通信。 为业务服务器 2015年设置的 Skype 实现时您需要确保的 （通常反映他们将从事的角色） 的新服务器名称映射与分配给他们的 IP 地址匹配。

尽管这看似位令人望而生畏开始时，可以完成规划此繁重使用[Skype 业务服务器 2015年规划工具](https://www.microsoft.com/en-us/download/details.aspx?id=50357)。 后已经历有关哪些功能您打算使用的向导的问题，为每个网站定义您可以查看 DNS 报告在边缘管理报告，并使用列出那里创建 DNS 记录的信息。 您还可以制作调整的许多名称和 IP 地址用于详细信息，请参阅[查看 DNS 报告](../../management-tools/planning-tool/review-the-administrator-reports.md#DNS_Report)。 需要记住的提醒您可以导出边缘管理报告 Excel 电子表格，并 DNS 报告将一个文件中的工作表。 虽然此工具包含[从业务服务器 2019年的 Skype 弃用](../../../SfBServer2019/deprecated.md)的功能，它仍然可用来创建初始计划，如果未选定这些功能

时[为 Skype 业务服务器创建 DNS 记录](../../deploy/install/create-dns-records.md)中所述，要安装的新实现和生成的 Skype 的企业服务器拓扑，但我们知道，您可以选择使用内置于 Windows Server 的 DNS 功能2016 或第三方 DNS 包，以便我们将保留常规，而不是特定本文中讨论。 我们正在伴随所需，并且如何满足该需要您需要确定。

有经验的 Skype 业务、 Lync 和 Office Communications 套件管理员可能会发现以下各表有用。 如果您混淆表，后面的部分或文章将有所帮助的以下概念：

## <a name="summary-tables"></a>摘要表
<a name="BK_Summary"> </a>

下表显示了 Skype 业务服务器用于向用户提供服务的 DNS 记录。 一些是可选的它们只需要支持某些功能，并且它们如果不需要这些功能可以跳过。 所需的内部访问的 DNS 记录仅位于第一个表格，并允许内部和外部访问的部署需要两个表中的记录。

**内部 DNS 映射**

|记录类型|值|解析为|用途|必需|
|:-----|:-----|:-----|:-----|:-----|
|A/AAAA   |前端池 FQDN  <br/> *FE-pool。<span> </span>contoso<span></span>.com*   |前端池服务器端 IP 地址  <br/>  DNS 磅到*192.168.21.122 192.168.21.123 192.168.21.124*   |DNS 负载平衡的前端池。 将前端池名称映射到一组 IP 地址。  <br/> 请参阅[部署 DNS 负载平衡的前端池和控制器池](load-balancing.md#BK_FE_Dir)  |Y   |
|A/AAAA   | 池中每台前端服务器或 Standard Edition 服务器或独立服务器的 FQDN <br/>  *FE01。<span> </span>contoso。<span> </span>com FE02。<span> </span>contoso<span></span>.com FE03。<span> </span>contoso<span></span>.com*   |相应的每台服务器的 IP  <br/> *192.168.21.122 192.168.21.123 192.168.21.124*   |将服务器名称映射到其 IP 地址。   |Y   |
|A/AAAA   |企业版池内部 Web 服务覆盖 FQDN  <br/> *Web int.<span></span>contoso<span></span>.com*   |前端服务器的内部 Web 服务的 HLB VIP  <br/> *192.168.21.120*   |启用客户端到服务器 web 流量，如企业 Web 应用程序下载 Skype 的需要。 也被必需的移动客户端。   |Y   |
|A/AAAA   |企业版池外部 Web 服务覆盖 FQDN  <br/> *Web ext.<span></span>contoso<span></span>.com*   |前端服务器的外部 Web 服务的 HLB VIP  <br/>*68.123.56.90*   |启用客户端到服务器 web 流量，如企业 Web 应用程序下载 Skype 的需要。 所需移动客户端是否将内部解析 DNS。 可以解析为 DMZ 反向代理服务器 IP 或 Internet IP。   ||
|A/AAAA   | 后端服务器的 SQL server FQDN <br/> *SQL1。<span> </span>contoso<span></span>.com*   |服务器的 IP 地址  <br/> *192.168.11.90*   |将使用为其 IP 地址的前端池的后端 SQL server 的服务器名称映射   ||
|A/AAAA   |后端服务器镜像 SQL server FQDN  <br/> *SQL2。<span> </span>contoso<span></span>.com*   |服务器的 IP 地址  <br/> *192.168.11.91*   |将使用为其 IP 地址的前端池的后端 SQL 镜像服务器的服务器名称映射   ||
|A/AAAA   |控制器池 FQDN  <br/>**注意：** 使用独立控制器服务器时不适用 <br/> *DirPool。<span> </span>contoso<span></span>.com*   |控制器池的 IP 地址  <br/> 对*192.168.21.132、 192.168.21.133、 192.168.21.134* DNS 磅   |DNS 负载平衡的控制器池服务器。 地图池命名为控制器池为 IP 地址，请参阅[在前端池和控制器池上部署 DNS 负载平衡](load-balancing.md#BK_FE_Dir) <br/> 控制器可以对用户进行身份验证，可选。   ||
|A/AAAA   |控制器的 FQDN   |服务器的每台控制器服务器的 IP 地址   |映射到 IP 地址、 控制器池名称，请参阅[在前端池和控制器池上部署 DNS 负载平衡](load-balancing.md#BK_FE_Dir)  ||
|A/AAAA   |中介服务器池 FQDN   |池的 IP 地址   |中介服务器角色是可选的。 您可以共同查找到前端服务器或池的中介服务器提供的服务。 请参阅[使用 DNS 负载平衡中介服务器池](load-balancing.md#BK_Mediation)  ||
|A/AAAA   |中介服务器 FQDN   |服务器的 IP 地址   |您可以共同查找到前端服务器或池的中介服务器提供的服务。 请参阅[使用 DNS 负载平衡中介服务器池](load-balancing.md#BK_Mediation)  ||
|A/AAAA   |持久聊天服务器 FQDN   |持久聊天服务器 IP 地址   |持久聊天服务器才能进行持久聊天功能，否则是可选的。   ||
|A/AAAA   |lyncdiscoverinternal。* \<sipdomain\>* <br/> lyncdiscoverinternal。* <span> </span>contoso<span></span>.com*   |HLB 前端池 VIP 或控制器 IP  <br/>  192.168.21.121  |内部自动发现 Service1，所需的移动支持。 如果内部 DNS 用于解析为移动设备，则应指向的外部 ip 地址或 DMZ VIP。  <br/> Web 服务我们需要上的前端池 HLB，如 HTTPS 无法利用 DNS。 前端池或控制器池，这应解析为 HLB VIP 或一个 Standard edition server 或独立控制器服务器的正则 IP。   |Y   |
|CNAME   |lyncdiscoverinternal。* \<sipdomain\>* <br/> lyncdiscoverinternal. *<span></span>contoso<span></span>.com*   |HLB FE 池 FQDN 或控制器的 FQDN  <br/> Web int.<span></span>contoso<span></span>.com   |内部自动发现 Service1 <br/> 如果需要，可实现作为而不是 A 记录 CNAME 这种情况。   ||
|A/AAAA   |sip。* \<sipdomain\>* <br/> sip。* <span> </span>contoso<span></span>.com*  |前端的池服务器 IP 地址 （或到每个控制器 IP 地址）  <br/>  DNS 磅到*192.168.21.122 192.168.21.123 192.168.21.124*   |所需的自动配置，请参阅[演练的 Skype 业务客户端的查找服务](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype) <br/> 记录或外部客户端时指向前端池服务器或控制器服务器在内部网络或访问边缘服务上的记录   |& #x 2777;  |
|A/AAAA   |ucupdates-r2。* \<sipdomain\>* <br/> ucupdates-r2。* <span> </span>contoso<span></span>.com*  |HLB FE 池 VIP 或控制器池 HLB VIP 或 SE 服务器/控制器服务器的 IP  <br/>  192.168.21.121  |部署此记录是可选 & #x 2778;  ||
|SRV   |\_sipinternaltls。\_tcp。* \<sipdomain\> * <br/>端口 5061 <br/>\_sipinternaltls。\_tcp。* <span> </span>contoso<span></span>.com* <br/>端口 5061  |前端池 FQDN  <br/>*FE-Pool。<span> </span>contoso<span></span>.com*  |允许内部用户自动登录 1 到前端服务器/池或 SE 服务器/池进行身份验证和重定向客户端登录请求。  |& #x 2777; |
|A/AAAA |sipinternal。* \<sipdomain\>* <br/>sipinternal。<span> </span> *contoso<span></span>.com*  |前端池 FQDN  <br/>_FE-Pool。<span> </span>contoso<span></span>.com_  |内部用户访问和 #x 2776;  |& #x 2777;  |
|SRV   | \_ntp。\_udp。* \<sipdomain\> * <br/> \_ntp。\_udp。<span> </span> *contoso<span></span>.com*  |时间服务器 FQDN  <br/> 北美 america.pool.ntp.org   |NTP 源所需的 Lync Phone Edition 设备   |这需要支持桌面话筒。   |
|SRV   |\_sipfederationtls。\_tcp。* \<sipdomain\> * <br/>\_sipfederationtls。\_tcp。<span> </span> *contoso<span></span>.com*  | 访问边缘服务 FQDN <br/> EdgePool int.<span></span>*contoso<span></span>.com*  |创建一个具有 IOS 或 Windows phone 移动客户端的每个 SIP 域的 SRV 记录。   |移动客户端支持   |
|A/AAAA   |管理 URL  <br/>*Web int.<span></span>contoso<span></span>.com*  |FE 池 HLB VIP  <br/> 192.168.21.121   |Skype 的业务 Server Control Panel，请参阅[简单 Url](dns.md#BK_Simple)  ||
|A/AAAA   |满足 URL  <br/>*Web int.<span></span>contoso<span></span>.com*  |FE 池 HLB VIP  <br/> 192.168.21.121   |联机会议，请参阅[简单 Url](dns.md#BK_Simple)  ||
|A/AAAA   |电话拨入式 URL  <br/>*Web int.<span></span>contoso<span></span>.com*  |FE 池 HLB VIP  <br/> 192.168.21.121   |电话拨入式会议，请参阅[简单 Url](dns.md#BK_Simple)  ||
|A/AAAA   |内部 Web 服务 FQDN  <br/>*Web int.<span></span>contoso<span></span>.com*  |FE 池 HLB VIP  <br/> 192.168.21.121   |Skype Skype 用于企业 Web 应用程序的业务 Web 服务   ||
|A/AAAA   |Office Web Apps Server 池 FQDN  <br/> OWA。<span> </span>contoso<span></span>.com   | Office Web Apps Server 池 VIP 地址 <br/> 192.168.1.5   |定义的 Office Web Apps Server 池 FQDN   ||
|A/AAAA   | 内部 Web FQDN <br/> Web int.<span></span>contoso<span></span>.com   | 前端池 VIP 地址 <br/> 192.168.21.121   |定义业务 Web 应用程序中通过 Skype 用于内部 Web FQDN  <br/> 如果您使用 DNS 负载平衡此池上，您的前端池和内部 web 场不能具有相同 FQDN。   ||

& #x 2776;由客户端用于发现前端服务器或前端池，并进行身份验证和用户的身份登录。 [演练的 Skype 业务客户端的查找服务](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)正在对此的更多详细信息。

& #x 2777;这是只需支持旧客户端之前 Lync 2013 和桌面的话筒。

& #x 2778;在其中一种统一通信设备已打开，但用户从来没有登录设备的情况，A 记录允许发现承载设备更新 Web 服务的服务器并获取更新的设备。 否则，设备在用户首次登录时通过带内设置获得服务器信息。

下图显示了示例，其中包括内部和外部 DNS 记录，并且许多的周围的表中显示的记录：

**使用公共 IPv4 地址边缘网络图**

![DNS 网络图表示例](../../media/2cc9546e-5560-4d95-8fe4-65a792a0e9c3.png)

**外围网络 DNS 映射 （内部和外部接口）**

|记录类型|值|解析为|用途|必需|
|:--- |:--- |:--- |:--- |:--- |
|A/AAAA   |内部边缘池 FQDN  <br/>*EdgePool int.<span></span>contoso<span></span>.com*  |面向内部的边缘池的 IP 地址  <br/> 172.25.33.10、 172.25.33.11   |合并边缘池内部接口 IP 地址   |Y   |
|A/AAAA   |边缘服务器 FQDN  <br/>*缺点-1。<span> </span>contoso<span></span>.com*  |面向内部的服务器的边缘池中的服务器的 IP  <br/> 172.25.33.10   |创建一条记录的池中每台服务器与服务器 FQDN 指向其内部服务器节点 IP 池中，请参阅[上边缘服务器池的 DNS 负载平衡](load-balancing.md#BK_Edge)。   |Y   |
|A/AAAA   |访问边缘服务池 FQDN  <br/>*Access1。<span> </span>contoso<span></span>.com*  |访问边缘服务池外部 IP 地址  <br/> 131.107.16.10、 131.107.16.11   |访问边缘服务的出站和入站会话初始协议 (SIP) 流量提供单一的受信任连接点。   |Y   |
|A/AAAA   |Web 会议边缘服务池 FQDN  <br/>*Webcon1。<span> </span>contoso<span></span>.com*  |Web 会议边缘服务外部 IP 地址  <br/> 131.107.16.90、 131.107.16.91   |Web 会议边缘服务，外部用户可以加入您的业务服务器环境的内部 Skype 上承载的会议。   |Y   |
|A/AAAA   |*av.\<sip 域\>* 池 FQDN <br/>*AV1。<span> </span>contoso<span></span>.com*  |A / V 边缘外部 IP 地址  <br/> 131.107.16.170、 131.107.16.171   |A / V 边缘服务使音频、 视频、 应用程序共享和文件传输供外部用户。   |Y   |
|CNAME   |sip。* \<sipdomain\>* <br/> sip。* <span> </span>contoso<span></span>.com*  |外部访问边缘池 FQDN  <br/>*Access1。<span> </span>contoso<span></span>.com*  |查找边缘服务器池。 请参阅[演练的 Skype 业务客户端的查找服务](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)  |Y   |
|SRV   |\_sip。\_tls。* \<sipdomain\> * <br/>\_sip。\_tls。<span> </span> *contoso<span></span>.com*  |外部访问边缘 FQDN  <br/>_Access1。<span> </span>contoso<span></span>.com_  |用于外部用户访问。 请参阅[演练的 Skype 业务客户端的查找服务](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)  |Y   |
|SRV   |\_sipfederationtls。\_tcp。* \<sipdomain\> * <br/>\_sipfederationtls。\_tcp。<span> </span> *contoso<span></span>.com*  |外部访问边缘 FQDN  <br/>*Access1。<span> </span>contoso<span></span>.com*  |用于联盟和公共 IM 连接   |& #x 2776;  |
|SRV   |\_xmpp 服务器。\_tcp。*<sipdomain\> * <br/>\_xmpp 服务器。\_tcp。* <span> </span>contoso<span></span>.com*  |外部访问边缘 FQDN  <br/>*Access1。<span> </span>contoso<span></span>.com*  |XMPP 代理服务接受并与配置 XMPP 联盟伙伴发送可扩展消息传递和状态协议 (XMPP) 消息。   |Y，部署联合身份验证，否则为可选  <br/> 在业务服务器 2019年的 Skype 中不可用。|
|SRV   |\_sipfederationtls。\_tcp。* \<sipdomain\> * <br/>\_sipfederationtls。\_tcp。* <span> </span>contoso<span></span>.com*  |外部访问边缘 FQDN  <br/>*Access1。<span> </span>contoso<span></span>.com*  |若要支持推送通知服务和 Apple 推送通知服务，您可以创建一个 SRV 记录每个 SIP 域。 & #x 2778;  ||
|A/AAAA   |外部前端池 web 服务 FQDN  <br/>*Web ext.<span></span>contoso<span></span>.com*  |反向代理的公共 IP 地址，而您的前端池和 #x 2776; 外部 Web 服务 VIP 的代理 <br/> 131.107.155.1 192.168.21.120 代理   |前端最终池外部接口用于通过 Skype 企业 Web 应用程序   |Y   |
|A/AAAA/CNAME   |lyncdiscover。* \<sipdomain\>* <br/> lyncdiscover。* <span> </span>contoso<span></span>.com*  |如果您没有控制器和 #x 2777;，反向代理服务器公共 IP 地址，解析为外部 Web 服务 VIP 控制器池，如果您没有或前端池 <br/> 131.107.155.1 192.168.21.120 代理   | 自动发现，也可使用移动功能，业务 Web App 和计划程序 Web 应用程序的 Skype 解析反向代理服务器的客户端外部记录 <br/> 若要支持推送通知服务和 Apple 推送通知服务，您可以创建一个具有 Microsoft Lync 移动客户端的每个 SIP 域的 SRV 记录。 3  |Y   |
|A/AAAA   |满足。* \<sipdomain\>* <br/> 满足。* <span> </span>contoso<span></span>.com*  |反向代理服务器公共 IP 地址，解析为前端池的外部 Web 界面  <br/> 131.107.155.1 192.168.21.120 代理   |Skype 业务 Web 服务代理  <br/> 请参阅[简单 Url](dns.md#BK_Simple)  |Y   |
|A/AAAA   |拨号单元*\<sipdomain\>* <br/> 拨号单元*<span></span>contoso<span></span>.com*  |反向代理对于前端池的外部 Web 接口的公共 IP 地址的代理，  <br/> 131.107.155.1 192.168.21.120 代理   |Skype 业务 Web 服务代理  <br/> 请参阅[简单 Url](dns.md#BK_Simple)  |Y   |
|A/AAAA   |Office Web Apps Server 池 FQDN  <br/> OWA。<span> </span>contoso<span></span>.com   | 反向代理公共 IP 地址，向外部 Office Web Apps Server 的 Web 接口的代理 <br/> 131.107.155.1 192.168.1.5 代理   | Office Web Apps Server 池 VIP 地址 <br/> 192.168.1.5   |定义的 Office Web Apps Server 池 FQDN   |

& #x 2776;部署联合身份验证，否则为可选需要。

& #x 2777;由客户端用于发现的前端服务器或前端池和进行身份验证和用户的身份登录。

& #x 2778;这一要求仅适用于 Apple 客户端或基于 Microsoft 的移动设备。 Android 和 Nokia Symbian 设备不使用推送通知。

 有关边缘服务器和外围网络的详细信息，请参阅[DNS 规划](../../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#DNSPlan)内容的边缘服务器。

> [!IMPORTANT]
> Skype 业务服务器支持使用 IPv6 寻址。 有关详细信息，请参阅[Plan for Business 的 Skype 中的 IPv6 的](ipv6.md)。

> [!IMPORTANT]
> Fqdn 的详细信息，请参阅[DNS 基础知识](basics.md)。

**裂脑 DNS** 
 <a name="BK_split"> </a>

裂脑 DNS 是 DNS 配置了与同一命名空间的两个 DNS 区域。 第一个 DNS 区域处理内部请求，而这些表中提到的第二个 DNS 区域来处理外部请求。 有关更多信息，请参阅[脑 DNS 的情况](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS)。

## <a name="hybrid-considerations"></a>混合注意事项
<a name="BK_Hybrid"> </a>

如果您打算将一些用户驻留联机和一些上驻留的部署，请参阅规划文章[业务服务器 2019 Skype](../../../SfBServer2019/hybrid/plan-hybrid-connectivity.md)的混合连接。 您需要配置 DNS 正常的 Skype 业务服务器 2015年，以及添加其他 DNS 记录。

此外应在请参阅"Office 365 Url 和 IP 地址范围"[https://aka.ms/o365ips](https://aka.ms/o365ips)以确认您的用户将有权访问他们将需要的联机资源。

## <a name="simple-urls"></a>简单 URL
<a name="BK_Simple"> </a>

统一资源定位器 (URL) 的引用指定其位置计算机网络和用于检索该协议的 web 资源。

Skype 业务服务器支持对使用三种"简单"Url 以访问服务：

- **满足**用作的基 URL 的网站中的所有会议。 会议简单 URL 的一个示例是 https:<span></span>//<span></span>满足。<span> </span>contoso<span></span>。 com。 特定会议的 URL 可能是 https:<span></span>//<span></span>满足。<span> </span>contoso<span></span>.com /_username_/7322994。

    与会议的简单 URL，加入会议的链接是易于理解且轻松地进行通信。

- **电话拨入式**允许访问电话拨入式会议设置网页。 此页显示其可用的语言，分配会议信息与会议拨入号码 (即，不需要安排的会议)，会议 DTMF 控件和个人识别号 （支持管理PIN) 和分配会议信息。 电话拨入式简单 URL 包含所有的会议邀请中，以便想要拨入会议的用户可以访问所需的电话号码和 PIN 信息。 电话拨入式简单 URL 的示例为 https://<span></span>dialin。<span> </span>contoso<span></span>。 com。

- **管理**业务 Server Control Panel 启用 Skype 快速访问。 从组织防火墙内的任何计算机，管理员可以打开 Skype 业务 Server Control Panel 通过浏览器中键入管理简单 URL。 组织内部的管理简单 URL。 管理简单 URL 的示例为 https://<span></span>管理员。<span> </span>contoso<span></span>。 com。

简单 Url 处[的 Skype 业务服务器中的简单 Url 的 DNS 要求](simple-urls.md)的详细讨论。

## <a name="dns-by-server-role"></a>按服务器角色的 DNS
<a name="BK_Servers"> </a>

您可以根据您愿意，但使其记忆和反映其函数系统中设置这些池和服务器的名称。

### <a name="dns-records-for-individual-servers-or-pools"></a>为单个服务器或池的 DNS 记录

这些泛型记录要求适用于 for Business 使用 Skype 的任何服务器角色。 池是一组服务器运行相同协同工作以处理客户端请求定向到它们通过负载平衡器的服务。 请参阅的详细信息的[负载平衡的 Skype 的业务要求](load-balancing.md)

**DNS 记录要求服务器/池角色 （假定 DNS 负载平衡）**

|部署方案|DNS 要求|
|:-----|:-----|
|一台服务器：  <br/> 持久聊天，控制器、 中介服务器，前端服务器   |将服务器的完全限定的域名 (FQDN) 解析为其 IP 地址的内部 A 记录。  <br/> ServerRole。<span> </span>contoso<span></span>.com 10.10.10.0   |
|池：  <br/> 持久聊天、 Director、 边缘服务器、 中介服务器，前端   |内部 A 记录，解析为其 IP 地址的池中每个服务器节点的完全限定的域名 (FQDN)。  <br/>**示例** <br/> ServerRole01。<span> </span>contoso<span></span>.com 10.10.10.1  <br/> ServerRole02。<span> </span>contoso<span></span>.com 10.10.10.2  <br/> 在池，多个内部 A 记录可解析为 IP 地址的服务器节点的池的完全限定的域名 (FQDN)。  <br/>**示例** <br/> ServerPool。<span> </span>contoso<span></span>.com 10.10.10.1  <br/> ServerPool。<span> </span>contoso<span></span>.com 10.10.10.2   |

### <a name="edge-server-specific-dns-topics"></a>边缘服务器特定 DNS 主题

 若要规划部署边缘服务器，请查看[规划边缘服务器部署中的业务服务器 2015 Skype](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md)和[高级边缘服务器 DNS 规划业务服务器 2015年的 Skype](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md)具有以下各节

- [DNS disaster recovery](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSDR)

- [DNS load balancing](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB)

- [Automatic configuration without split-brain DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#NoSplitBrainDNS)

- [Split-brain DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS)

- [Walkthrough of Skype for Business clients locating services](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)


