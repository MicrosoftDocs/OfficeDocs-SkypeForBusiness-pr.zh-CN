---
title: For Business Server 2015 Skype 的 DNS 要求
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c50e38d2-b1e4-4ebd-8dc3-85d4ae7a76ee
description: 摘要： 为业务服务器 2015年实现 Skype 之前查看本主题中的 DNS 注意事项。
ms.openlocfilehash: d854c9908211a70b8fe863c9535502ba78c48521
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="dns-requirements-for-skype-for-business-server-2015"></a>For Business Server 2015 Skype 的 DNS 要求
 
**摘要：**为业务服务器 2015年实现 Skype 之前查看本主题中的 DNS 注意事项。
  
本文仅介绍 DNS 规划的 Skype 业务服务器 2015年部署在组织的内部网络。 有关业务 online Skype 请参阅"Office 365 Url 和 IP 地址范围"在[http://aka.ms/o365ips](http://aka.ms/o365ips)。 
  
域名服务 (DNS) 服务器将主机名 （例如 www.contoso.com，可能是 web 服务器) 映射到 IP 地址 （例如，10.10.10.10)。 帮助客户端和相互依赖服务器在网络上互相通信。 为业务服务器 2015年设置的 Skype 实现时您需要确保的 （通常反映他们将从事的角色） 的新服务器名称映射与分配给他们的 IP 地址匹配。
  
尽管这看似位令人望而生畏开始时，可以完成规划此繁重使用[Skype 业务服务器 2015年规划工具](https://www.microsoft.com/en-us/download/details.aspx?id=50357)。 后已经历有关哪些功能您打算使用的向导的问题，为每个网站定义您可以查看 DNS 报告在边缘管理报告，并使用列出那里创建 DNS 记录的信息。 您还可以制作调整的许多名称和 IP 地址用于详细信息，请参阅[查看 DNS 报告](../../management-tools/planning-tool/review-the-administrator-reports.md#DNS_Report)。 需要记住的提醒您可以导出边缘管理报告 Excel 电子表格，并 DNS 报告将一个文件中的工作表。 
  
时[为业务服务器 2015年的 Skype 创建 DNS 记录](../../deploy/install/create-dns-records.md)中所述，要安装的新实现和生成的 Skype 的业务服务器 2015年拓扑，但我们知道，您可以选择使用 Windows 中内置的 DNS 功能服务器 2016年或第三方 DNS 包，以便我们将保留常规，而不是特定本文中讨论。 我们正在伴随所需，并且如何满足该需要您需要确定。
  
有经验的 Skype 业务、 Lync 和 Office Communications 套件管理员可能会发现以下各表有用。 如果您混淆表，后面的部分或文章将有所帮助的以下概念： 
  
- [摘要表](dns.md#BK_Summary)
    
- [DNS 基础知识](basics.md)
    
- [混合注意事项](dns.md#BK_Hybrid)
    
- [裂脑 DNS](dns.md#BK_split)
    
- [简单 Url](dns.md#BK_Simple)
    
- [按服务器角色的 DNS](dns.md#BK_Servers)
    
## <a name="summary-tables"></a>摘要表
<a name="BK_Summary"> </a>

下表显示了业务服务器 2015年的 Skype 用于向用户提供服务的 DNS 记录。 一些是可选的它们只需要支持某些功能，并且它们如果不需要这些功能可以跳过。 所需的内部访问的 DNS 记录仅位于第一个表格，并允许内部和外部访问的部署需要两个表中的记录。
  
**内部 DNS 映射**

|**记录类型**|**值**|**解析为**|**用途**|**必填**|
|:-----|:-----|:-----|:-----|:-----|
|A/AAAA  <br/> |前端池 FQDN  <br/>  *FE pool.contoso.com*  <br/> |前端池服务器端 IP 地址  <br/>  DNS 磅到*192.168.21.122 192.168.21.123 192.168.21.124*  <br/> |DNS 负载平衡的前端池。 将前端池名称映射到一组 IP 地址。  <br/> 请参阅[部署 DNS 负载平衡的前端池和控制器池](load-balancing.md#BK_FE_Dir) <br/> |Y  <br/> |
|A/AAAA  <br/> | 池中每台前端服务器或 Standard Edition 服务器或独立服务器的 FQDN <br/>  * FE01.contoso.com，FE02.contoso.com，FE03.contoso.com*  <br/> |相应的每台服务器的 IP  <br/>  *192.168.21.122 192.168.21.123 192.168.21.124*  <br/> |将服务器名称映射到其 IP 地址。  <br/> |Y  <br/> |
|A/AAAA  <br/> |企业版池内部 Web 服务覆盖 FQDN  <br/>  *Web int.contoso.com*  <br/> |前端服务器的内部 Web 服务的 HLB VIP  <br/>  * 192.168.21.120 *  <br/> |启用客户端到服务器 web 流量，如企业 Web 应用程序下载 Skype 的需要。 也被必需的移动客户端。  <br/> |Y  <br/> |
|A/AAAA  <br/> |企业版池外部 Web 服务覆盖 FQDN  <br/>  *Web ext.contoso.com*  <br/> |前端服务器的外部 Web 服务的 HLB VIP  <br/>  *68.123.56.90*  <br/> |启用客户端到服务器 web 流量，如企业 Web 应用程序下载 Skype 的需要。 所需移动客户端是否将内部解析 DNS。 可以解析为 DMZ 反向代理服务器 IP 或 Internet IP。  <br/> ||
|A/AAAA  <br/> | 后端服务器的 SQL server FQDN <br/>  *SQL1.contoso.com*  <br/> |服务器的 IP 地址  <br/>  *192.168.11.90*  <br/> |将使用为其 IP 地址的前端池的后端 SQL server 的服务器名称映射  <br/> ||
|A/AAAA  <br/> |后端服务器镜像 SQL server FQDN  <br/>  *SQL2.contoso.com*  <br/> |服务器的 IP 地址  <br/>  *192.168.11.91*  <br/> |将使用为其 IP 地址的前端池的后端 SQL 镜像服务器的服务器名称映射  <br/> ||
|A/AAAA  <br/> |控制器池 FQDN  <br/> **注意：**使用独立控制器服务器时不适用 <br/>  *DirPool.contoso.com*  <br/> |控制器池的 IP 地址  <br/> 对*192.168.21.132、 192.168.21.133、 192.168.21.134* DNS 磅  <br/> |DNS 负载平衡的控制器池服务器。 地图池命名为控制器池为 IP 地址，请参阅[在前端池和控制器池上部署 DNS 负载平衡](load-balancing.md#BK_FE_Dir) <br/> 控制器可以对用户进行身份验证，可选。  <br/> ||
|A/AAAA  <br/> |控制器的 FQDN  <br/> |服务器的每台控制器服务器的 IP 地址  <br/> |映射到 IP 地址、 控制器池名称，请参阅[在前端池和控制器池上部署 DNS 负载平衡](load-balancing.md#BK_FE_Dir) <br/> ||
|A/AAAA  <br/> |中介服务器池 FQDN  <br/> |池的 IP 地址  <br/> |中介服务器角色是可选的。 您可以共同查找到前端服务器或池的中介服务器提供的服务。 请参阅[使用 DNS 负载平衡中介服务器池](load-balancing.md#BK_Mediation) <br/> ||
|A/AAAA  <br/> |中介服务器 FQDN  <br/> |服务器的 IP 地址  <br/> |您可以共同查找到前端服务器或池的中介服务器提供的服务。 请参阅[使用 DNS 负载平衡中介服务器池](load-balancing.md#BK_Mediation) <br/> ||
|A/AAAA  <br/> |持久聊天服务器 FQDN  <br/> |持久聊天服务器 IP 地址  <br/> |持久聊天服务器才能进行持久聊天功能，否则是可选的。  <br/> ||
|A/AAAA  <br/> |lyncdiscoverinternal. _\<sipdomain\>_ <br/> lyncdiscoverinternal。*contoso.com*  <br/> |HLB 前端池 VIP 或控制器 IP  <br/>  192.168.21.121 <br/> |内部自动发现 Service1，所需的移动支持。 如果内部 DNS 用于解析为移动设备，则应指向的外部 ip 地址或 DMZ VIP。  <br/> Web 服务我们需要上的前端池 HLB，如 HTTPS 无法利用 DNS。 前端池或控制器池，这应解析为 HLB VIP 或一个 Standard edition server 或独立控制器服务器的正则 IP。  <br/> |Y  <br/> |
|CNAME  <br/> |lyncdiscoverinternal. _\<sipdomain\>_ <br/> lyncdiscoverinternal. *contoso.com*  <br/> |HLB FE 池 FQDN 或控制器的 FQDN  <br/> Web int.contoso.com  <br/> |内部自动发现 Service1 <br/> 如果需要，可实现作为而不是 A 记录 CNAME 这种情况。  <br/> ||
|A/AAAA  <br/> |sip。 _\<sipdomain\>_ <br/> sip。 _contoso.com_ <br/> |前端的池服务器 IP 地址 （或到每个控制器 IP 地址）  <br/>  DNS 磅到*192.168.21.122 192.168.21.123 192.168.21.124*  <br/> |所需的自动配置，请参阅[演练的 Skype 业务客户端的查找服务](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype) <br/> 记录或外部客户端时指向前端池服务器或控制器服务器在内部网络或访问边缘服务上的记录  <br/> |2 <br/> |
|A/AAAA  <br/> |ucupdates-r2。 _\<sipdomain\>_ <br/> ucupdates-r2。 _contoso.com_ <br/> |HLB FE 池 VIP 或控制器池 HLB VIP 或 SE 服务器/控制器服务器的 IP  <br/>  192.168.21.121 <br/> |部署此记录是可选的 3 <br/> ||
|SRV  <br/> |_sipinternaltls._tcp。 _ \<sipdomain\> _端口 5061 <br/> _sipinternaltls._tcp。 _contoso.com_端口 5061 <br/> |前端池 FQDN  <br/>  _FE Pool.contoso.com_ <br/> |允许内部用户自动登录 1 到前端服务器/池或 SE 服务器/池进行身份验证和重定向客户端登录请求。 <br/> |2 <br/> |
|SRV  <br/> |_sipinternal。 _\<sipdomain\>_ <br/> _sipinternal。 _contoso.com_ <br/> |前端池 FQDN  <br/>  _FE Pool.contoso.com_ <br/> |内部用户访问 1 <br/> |2 <br/> |
|SRV  <br/> |_ntp._udp。 _\<sipdomain\>_ <br/> _ntp._udp。 _contoso.com_ <br/> |时间服务器 FQDN  <br/> 北美 america.pool.ntp.org  <br/> |NTP 源所需的 Lync Phone Edition 设备  <br/> |这需要支持桌面话筒。  <br/> |
|SRV  <br/> |_sipfederationtls._tcp。  _\<sipdomain\>_ <br/> _sipfederationtls._tcp。  _contoso.com_ <br/> | 访问边缘服务 FQDN <br/> EdgePool int. _contoso.com_ <br/> |创建一个具有 IOS 或 Windows phone 移动客户端的每个 SIP 域的 SRV 记录。  <br/> |移动客户端支持  <br/> |
|A/AAAA  <br/> |管理 URL  <br/>  _Web int.contoso.com_ <br/> |FE 池 HLB VIP  <br/> 192.168.21.121  <br/> |Skype 的业务 Server Control Panel，请参阅[简单 Url](dns.md#BK_Simple) <br/> ||
|A/AAAA  <br/> |满足 URL  <br/>  _Web int.contoso.com_ <br/> |FE 池 HLB VIP  <br/> 192.168.21.121  <br/> |联机会议，请参阅[简单 Url](dns.md#BK_Simple) <br/> ||
|A/AAAA  <br/> |电话拨入式 URL  <br/>  _Web int.contoso.com_ <br/> |FE 池 HLB VIP  <br/> 192.168.21.121  <br/> |电话拨入式会议，请参阅[简单 Url](dns.md#BK_Simple) <br/> ||
|A/AAAA  <br/> |内部 Web 服务 FQDN  <br/>  _Web int.contoso.com_ <br/> |FE 池 HLB VIP  <br/> 192.168.21.121  <br/> |Skype Skype 用于企业 Web 应用程序的业务 Web 服务  <br/> ||
|A/AAAA  <br/> |Office Web Apps Server 池 FQDN  <br/> OWA.contoso.com  <br/> | Office Web Apps Server 池 VIP 地址 <br/> 192.168.1.5  <br/> |定义的 Office Web Apps Server 池 FQDN  <br/> ||
|A/AAAA  <br/> | 内部 Web FQDN <br/> Web int.contoso.com  <br/> | 前端池 VIP 地址 <br/> 192.168.21.121  <br/> |定义业务 Web 应用程序中通过 Skype 用于内部 Web FQDN  <br/> 如果您使用 DNS 负载平衡此池上，您的前端池和内部 web 场不能具有相同 FQDN。  <br/> ||
   
 **1**使用者的客户端发现前端服务器或前端池，并进行身份验证和用户的身份登录。 [演练的 Skype 业务客户端的查找服务](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)正在对此的更多详细信息。
  
 **2**这只需要支持旧客户端之前 Lync 2013 和桌面的话筒。
  
 **3**中的情况： 统一通信设备已打开，但用户从来没有登录设备，A 记录允许发现承载设备更新 Web 服务的服务器并获取更新的设备。 否则，设备在用户首次登录时通过带内设置获得服务器信息。
  
下图显示了示例，其中包括内部和外部 DNS 记录，并且许多的周围的表中显示的记录： 
  
**使用公共 IPv4 地址边缘网络图**

![DNS 网络图表示例](../../media/2cc9546e-5560-4d95-8fe4-65a792a0e9c3.png)
  
**外围网络 DNS 映射 （内部和外部接口）**

|**记录类型**|**值**|**解析为**|**用途**|**必填**|
|:-----|:-----|:-----|:-----|:-----|
|A/AAAA  <br/> |内部边缘池 FQDN  <br/>  _EdgePool int.contoso.com_ <br/> |面向内部的边缘池的 IP 地址  <br/> 172.25.33.10、 172.25.33.11  <br/> |合并边缘池内部接口 IP 地址  <br/> |Y  <br/> |
|A/AAAA  <br/> |边缘服务器 FQDN  <br/>  _缺点 1.contoso.com_ <br/> |面向内部的服务器的边缘池中的服务器的 IP  <br/> 172.25.33.10  <br/> |创建一条记录的池中每台服务器与服务器 FQDN 指向其内部服务器节点 IP 池中，请参阅[上边缘服务器池的 DNS 负载平衡](load-balancing.md#BK_Edge)。  <br/> |Y  <br/> |
|A/AAAA  <br/> |访问边缘服务池 FQDN  <br/>  _Access1.contoso.com_ <br/> |访问边缘服务池外部 IP 地址  <br/> 131.107.16.10、 131.107.16.11  <br/> |访问边缘服务的出站和入站会话初始协议 (SIP) 流量提供单一的受信任连接点。  <br/> |Y  <br/> |
|A/AAAA  <br/> |Web 会议边缘服务池 FQDN  <br/>  _Webcon1.contoso.com_ <br/> |Web 会议边缘服务外部 IP 地址  <br/> 131.107.16.90、 131.107.16.91  <br/> |Web 会议边缘服务，外部用户可以加入您的业务服务器环境的内部 Skype 上承载的会议。  <br/> |Y  <br/> |
|A/AAAA  <br/> | _av.\<sip 域\>_ 池 FQDN <br/>  _AV1.contoso.com_ <br/> |A / V 边缘外部 IP 地址  <br/> 131.107.16.170、 131.107.16.171  <br/> |A / V 边缘服务使音频、 视频、 应用程序共享和文件传输供外部用户。  <br/> |Y  <br/> |
|CNAME  <br/> |sip。 _\<sipdomain\>_ <br/> sip。 _contoso.com_ <br/> |外部访问边缘池 FQDN  <br/>  _Access1.contoso.com_ <br/> |查找边缘服务器池。 请参阅[演练的 Skype 业务客户端的查找服务](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype) <br/> |Y  <br/> |
|SRV  <br/> |_sip._tls。 _\<sipdomain\>_ <br/> _sip._tls。 _contoso.com_ <br/> |外部访问边缘 FQDN  <br/>  _Access1.contoso.com_ <br/> |用于外部用户访问。 请参阅[演练的 Skype 业务客户端的查找服务](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype) <br/> |Y  <br/> |
|SRV  <br/> |_sipfederationtls._tcp。 _\<sipdomain\>_ <br/> _sipfederationtls._tcp。 _contoso.com_ <br/> |外部访问边缘 FQDN  <br/>  _Access1.contoso.com_ <br/> |用于联盟和公共 IM 连接  <br/> |1 <br/> |
|SRV  <br/> |_xmpp-server._tcp。 _\<sipdomain\>_ <br/> _xmpp-server._tcp。 _contoso.com_ <br/> |外部访问边缘 FQDN  <br/>  _Access1.contoso.com_ <br/> |XMPP 代理服务接受并与配置 XMPP 联盟伙伴发送可扩展消息传递和状态协议 (XMPP) 消息。  <br/> |Y，部署联合身份验证，否则为可选  <br/> |
|SRV  <br/> |_sipfederationtls._tcp。  _\<sipdomain\>_ <br/> _sipfederationtls._tcp。  _contoso.com_ <br/> |外部访问边缘 FQDN  <br/>  _Access1.contoso.com_ <br/> |若要支持推送通知服务和 Apple 推送通知服务，您可以创建一个 SRV 记录每个 SIP 域。 3 <br/> ||
|A/AAAA  <br/> |外部前端池 web 服务 FQDN  <br/>  _Web ext.contoso.com_ <br/> |反向代理服务器公共 IP 地址，外部 Web 服务 VIP 前端池 1 到代理 <br/> 131.107.155.1 192.168.21.120 代理  <br/> |前端最终池外部接口用于通过 Skype 企业 Web 应用程序  <br/> |Y  <br/> |
|A/AAAA/CNAME  <br/> |lyncdiscover. _\<sipdomain\>_ <br/> lyncdiscover. _contoso.com_ <br/> |如果您没有控制器 2，反向代理服务器公共 IP 地址，解析为外部 Web 服务 VIP 控制器池，如果您没有或前端池 <br/> 131.107.155.1 192.168.21.120 代理  <br/> | 自动发现，也可使用移动功能，业务 Web App 和计划程序 Web 应用程序的 Skype 解析反向代理服务器的客户端外部记录 <br/> 若要支持推送通知服务和 Apple 推送通知服务，您可以创建一个具有 Microsoft Lync 移动客户端的每个 SIP 域的 SRV 记录。 3 <br/> |Y  <br/> |
|A/AAAA  <br/> |满足。 _\<sipdomain\>_ <br/> 满足。 _contoso.com_ <br/> |反向代理服务器公共 IP 地址，解析为前端池的外部 Web 界面  <br/> 131.107.155.1 192.168.21.120 代理  <br/> |Skype 业务 Web 服务代理  <br/> 请参阅[简单 Url](dns.md#BK_Simple) <br/> |Y  <br/> |
|A/AAAA  <br/> |电话拨入式_\<sipdomain\>_ <br/> 电话拨入式_contoso.com_ <br/> |反向代理对于前端池的外部 Web 接口的公共 IP 地址的代理，  <br/> 131.107.155.1 192.168.21.120 代理  <br/> |Skype 业务 Web 服务代理  <br/> 请参阅[简单 Url](dns.md#BK_Simple) <br/> |Y  <br/> |
|A/AAAA  <br/> |Office Web Apps Server 池 FQDN  <br/> OWA.contoso.com  <br/> | 反向代理公共 IP 地址，向外部 Office Web Apps Server 的 Web 接口的代理 <br/> 131.107.155.1 192.168.1.5 代理  <br/> | Office Web Apps Server 池 VIP 地址 <br/> 192.168.1.5  <br/> |定义的 Office Web Apps Server 池 FQDN  <br/> |
   
 部署联合身份验证，否则为可选所需要的**1** 。
  
 **2**使用者的客户端发现的前端服务器或前端池和进行身份验证和用户的身份登录。
  
 **3**这一要求仅适用于 Apple 客户端或基于 Microsoft 的移动设备。 Android 和 Nokia Symbian 设备不使用推送通知。
  
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

如果您计划安装某些用户驻留在本地联机和一些托管，请参阅混合[DNS 设置](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md#BKMK_DNS)。 您需要配置 DNS 正常的 Skype 业务服务器 2015年，以及添加其他 DNS 记录。 
  
此外应在请参阅"Office 365 Url 和 IP 地址范围"[http://aka.ms/o365ips](http://aka.ms/o365ips)以确认您的用户将有权访问他们将需要的联机资源。
  
## <a name="simple-urls"></a>简单 URL
<a name="BK_Simple"> </a>

统一资源定位器 (URL) 的引用指定其位置计算机网络和用于检索该协议的 web 资源。 
  
Skype 业务服务器支持对使用三种"简单"Url 以访问服务：
  
- **满足**用作的基 URL 的网站中的所有会议。 会议简单的示例 URL 是https://meet.contoso.com。可能有特定会议的 URL https://meet.contoso.com/ _用户名_/7322994。 
    
    与会议的简单 URL，加入会议的链接是易于理解且轻松地进行通信。
    
- **电话拨入式**允许访问电话拨入式会议设置网页。 此页显示其可用的语言，分配会议信息与会议拨入号码 (即，不需要安排的会议)，会议 DTMF 控件和个人识别号 （支持管理PIN) 和分配会议信息。 电话拨入式简单 URL 包含所有的会议邀请中，以便想要拨入会议的用户可以访问所需的电话号码和 PIN 信息。 电话拨入式简单 URL 的一个示例是https://dialin.contoso.com。
    
- **管理**业务 Server Control Panel 启用 Skype 快速访问。 从组织防火墙内的任何计算机，管理员可以打开 Skype 业务 Server Control Panel 通过浏览器中键入管理简单 URL。 组织内部的管理简单 URL。 管理简单 URL 的一个示例是https://admin.contoso.com。
    
简单 Url[中的业务服务器 2015 Skype 的简单 Url 的 DNS](simple-urls.md)要求的详细讨论。
  
## <a name="dns-by-server-role"></a>按服务器角色的 DNS
<a name="BK_Servers"> </a>

您可以根据您愿意，但使其记忆和反映其函数系统中设置这些池和服务器的名称。
  
### <a name="dns-records-for-individual-servers-or-pools"></a>为单个服务器或池的 DNS 记录

这些泛型记录要求适用于 for Business 使用 Skype 的任何服务器角色。 池是一组服务器运行相同协同工作以处理客户端请求定向到它们通过负载平衡器的服务。 请参阅的详细信息的[负载平衡的 Skype 的业务要求](load-balancing.md)
  
**DNS 记录要求服务器/池角色 （假定 DNS 负载平衡）**

|**部署方案**|**DNS 要求**|
|:-----|:-----|
|一台服务器：  <br/> 持久聊天，控制器、 中介服务器，前端服务器  <br/> |将服务器的完全限定的域名 (FQDN) 解析为其 IP 地址的内部 A 记录。  <br/> ServerRole.contoso.com 10.10.10.0  <br/> |
|池：  <br/> 持久聊天、 Director、 边缘服务器、 中介服务器，前端  <br/> |内部 A 记录，解析为其 IP 地址的池中每个服务器节点的完全限定的域名 (FQDN)。  <br/> **示例** <br/> ServerRole01.contoso.com 10.10.10.1  <br/> ServerRole02.contoso.com 10.10.10.2  <br/> 在池，多个内部 A 记录可解析为 IP 地址的服务器节点的池的完全限定的域名 (FQDN)。  <br/> **示例** <br/> ServerPool.contoso.com 10.10.10.1  <br/> ServerPool.contoso.com 10.10.10.2  <br/> |
   
### <a name="edge-server-specific-dns-topics"></a>边缘服务器特定 DNS 主题

 若要规划部署边缘服务器，请查看[规划边缘服务器部署中的业务服务器 2015 Skype](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md)和[高级边缘服务器 DNS 规划业务服务器 2015年的 Skype](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md)具有以下各节
  
- [DNS disaster recovery](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSDR)
    
- [DNS load balancing](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB)
    
- [Automatic configuration without split-brain DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#NoSplitBrainDNS)
    
- [Split-brain DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS)
    
- [Walkthrough of Skype for Business clients locating services](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)
    

