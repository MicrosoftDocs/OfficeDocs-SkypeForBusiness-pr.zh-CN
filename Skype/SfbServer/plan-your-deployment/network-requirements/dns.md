---
title: Skype 的业务服务器 2015 DNS 要求
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: c50e38d2-b1e4-4ebd-8dc3-85d4ae7a76ee
description: 摘要： 在 Skype 实现业务服务器 2015年前查看本主题中的 DNS 注意事项。
ms.openlocfilehash: 2f19e6dbd040a7f553331b6bcb0d7074a30fd0ea
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="dns-requirements-for-skype-for-business-server-2015"></a>Skype 的业务服务器 2015 DNS 要求
 
**摘要：**Skype 实现业务服务器 2015年之前，请查看本主题中的 DNS 注意事项。
  
这篇文章仅解决 DNS 规划 Skype 业务服务器 2015年部署在组织的内部网络上。 Skype 的在线业务参考"Office 365 的 Url 和 IP 地址范围"在[http://aka.ms/o365ips](http://aka.ms/o365ips)。 
  
域名服务 (DNS) 服务器将 （如 www.contoso.com，大概是 web 服务器) 的主机名映射到 IP 地址 （如 10.10.10.10)。 它可以帮助客户端和相互依赖的服务器在网络上互相通信。 Skype 的实现设置为业务服务器 2015年时您需要确保新的服务器名称 （通常反映他们将从事的角色） 的映射与所分配到的 IP 地址相匹配。
  
虽然这可能看起来是位令人望而生畏起初，可以将规划这繁重的工作使用[Skype 业务服务器 2015年规划工具](https://www.microsoft.com/en-us/download/details.aspx?id=50357)。 一旦您已经经历了计划使用哪些功能的向导的疑问，为您定义的每个网站可以查看 DNS 报告在边缘管理报告，并使用列出创建 DNS 记录的信息。 您还可以调整到的许多名称和 IP 地址用于详细信息请参阅[审核该 DNS 报告](../../management-tools/planning-tool/review-the-administrator-reports.md#DNS_Report)。 请提醒您可以将边缘管理报表导出到 Excel 电子表格，并且 DNS 报告将为该文件中的工作表。 
  
当您正在安装的新实现[业务服务器 2015年的 Skype 的创建 DNS 记录](../../deploy/install/create-dns-records.md)所述并构建业务服务器 2015 Skype 为您的拓扑结构，我们已经认识到，您可以选择使用内置于 Windows 的 DNS 功能服务器 2016年或第三方 DNS 包，因此我们将把常规，而不是特定本文中讨论。 我们正在详细描述所需内容，以及您如何满足这种需求是您需要确定。
  
经验丰富的业务、 Lync 和办公室通信套件管理员 Skype 可能会发现以下各表很有用。 如果表给您带来困惑，文章的后面部分将搞清楚一些以下概念： 
  
- [摘要表](dns.md#BK_Summary)
    
- [DNS 基础知识](basics.md)
    
- [混合的注意事项](dns.md#BK_Hybrid)
    
- [裂脑 DNS](dns.md#BK_split)
    
- [简单的 Url](dns.md#BK_Simple)
    
- [DNS 服务器角色](dns.md#BK_Servers)
    
## <a name="summary-tables"></a>摘要表
<a name="BK_Summary"> </a>

下表显示了 DNS 记录业务服务器 2015年的 Skype 使用以向用户提供服务。 一些是可选的因为他们只需要为支持某些功能，而且它们如果不需要这些功能可以跳过。 在第一个表中，只是所需的内部访问的 DNS 记录，允许内部和外部访问的部署都需要两个表中的记录。
  
**内部 DNS 映射**

|**记录类型**|**值**|**解析为**|**目的**|**必填**|
|:-----|:-----|:-----|:-----|:-----|
|A/AAAA  <br/> |前结束池的 FQDN  <br/>  *FE pool.contoso.com*  <br/> |前结束池服务器 IP 地址  <br/>  对 DNS 磅*192.168.21.122 192.168.21.123 192.168.21.124*  <br/> |DNS 的前端池的负载平衡。 将前端池名称映射到一组 IP 地址。  <br/> 请参阅[部署 DNS 负载平衡前端池和导演池](load-balancing.md#BK_FE_Dir) <br/> |Y  <br/> |
|A/AAAA  <br/> | 池中的每个前端服务器或标准版服务器或独立服务器的 FQDN <br/>  * FE01.contoso.com，FE02.contoso.com，FE03.contoso.com*  <br/> |每个服务器的相应的 IP  <br/>  *192.168.21.122 192.168.21.123 192.168.21.124*  <br/> |将服务器名称映射到其 IP 地址。  <br/> |Y  <br/> |
|A/AAAA  <br/> |企业池内部 Web 服务覆盖 FQDN  <br/>  *网站 int.contoso.com*  <br/> |前端服务器内部 Web 服务的 HLB VIP  <br/>  * 192.168.21.120 *  <br/> |启用客户端到服务器的 web 通信，如下载 Skype 业务 Web 应用程序的需要。 此外需要为移动式客户机。  <br/> |Y  <br/> |
|A/AAAA  <br/> |企业池外部 Web 服务覆盖 FQDN  <br/>  *网站 ext.contoso.com*  <br/> |前端服务器外部 Web 服务的 HLB VIP  <br/>  *68.123.56.90*  <br/> |启用客户端到服务器的 web 通信，如下载 Skype 业务 Web 应用程序的需要。 如果移动客户端解析 DNS 内部的需要。 DMZ 反向代理服务器 IP 或互联网的 IP，可以解决。  <br/> ||
|A/AAAA  <br/> | 后端服务器 SQL 服务器 FQDN <br/>  *SQL1.contoso.com*  <br/> |服务器的 IP 地址  <br/>  *192.168.11.90*  <br/> |将使用为其 IP 地址的前端池的后端 SQL 服务器的服务器名称映射  <br/> ||
|A/AAAA  <br/> |后端服务器镜像 SQL 服务器 FQDN  <br/>  *SQL2.contoso.com*  <br/> |服务器的 IP 地址  <br/>  *192.168.11.91*  <br/> |将使用为其 IP 地址的前端池后端 SQL 镜像服务器的服务器名称映射  <br/> ||
|A/AAAA  <br/> |导演池的 FQDN  <br/> **注意：**使用独立的控制器服务器时不适用 <br/>  *DirPool.contoso.com*  <br/> |导演池 IP 地址  <br/> 对*192.168.21.132、 192.168.21.133、 192.168.21.134*的 DNS 磅  <br/> |DNS 负载平衡的总监池中的服务器。 映射池名称为主任池为 IP 地址，请参阅[部署前结束池和导演池 DNS 负载平衡](load-balancing.md#BK_FE_Dir) <br/> 控制器可以对用户进行身份验证和是可选的。  <br/> ||
|A/AAAA  <br/> |主管 FQDN  <br/> |每个控制器服务器的服务器 IP 地址  <br/> |映射池名称到 IP 地址，导演请参见[部署前结束池和导演池 DNS 负载平衡](load-balancing.md#BK_FE_Dir) <br/> ||
|A/AAAA  <br/> |中介服务器池的 FQDN  <br/> |池中的 IP 地址  <br/> |中介服务器角色是可选的。 您可以共同找到中介服务器的前端服务器或池所提供的服务。 请参阅[使用 DNS 负载平衡中介服务器池](load-balancing.md#BK_Mediation) <br/> ||
|A/AAAA  <br/> |中介服务器 FQDN  <br/> |服务器的 IP 地址  <br/> |您可以共同找到中介服务器的前端服务器或池所提供的服务。 请参阅[使用 DNS 负载平衡中介服务器池](load-balancing.md#BK_Mediation) <br/> ||
|A/AAAA  <br/> |持久的聊天服务器 FQDN  <br/> |永久性的聊天服务器的 IP 地址  <br/> |持久的聊天服务器持续聊天功能要求，否则是可选的。  <br/> ||
|A/AAAA  <br/> |lyncdiscoverinternal. _\<sipdomain\>_ <br/> lyncdiscoverinternal。*contoso.com*  <br/> |VIP 的 HLB 前端池或控制器 IP  <br/>  192.168.21.121 <br/> |内部自动发现服务 1，所需的移动性支持。 如果内部 DNS 用于解决移动设备，它应指向外部的 IP 或 DMZ VIP。  <br/> 为 Web 服务我们需要 HLB 前端池上的 HTTPS 无法利用 DNS。 前端池或控制器池这应解析为 HLB VIP 或一个普通 IP 标准版服务器或独立控制器服务器。  <br/> |Y  <br/> |
|CNAME  <br/> |lyncdiscoverinternal. _\<sipdomain\>_ <br/> lyncdiscoverinternal. *contoso.com*  <br/> |HLB FE 池的 FQDN 或主管 FQDN  <br/> 网站 int.contoso.com  <br/> |内部自动发现服务 1 <br/> 如果需要，可以实现为一个 CNAME 而不是一个记录这。  <br/> ||
|A/AAAA  <br/> |sip。 _\<sipdomain\>_ <br/> sip。 _contoso.com_ <br/> |前端服务器的 IP 地址 （或为每个控制器的 IP 地址） 的尾池  <br/>  对 DNS 磅*192.168.21.122 192.168.21.123 192.168.21.124*  <br/> |所需的自动配置，请参见[演练的 Skype 业务客户端查找服务](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype) <br/> 当外部客户端指向池前端服务器或内部网络，或访问边缘服务控制器服务器记录或记录  <br/> |2 <br/> |
|A/AAAA  <br/> |ucupdates-r2。 _\<sipdomain\>_ <br/> ucupdates-r2。 _contoso.com_ <br/> |HLB FE 池 VIP 或主任池 HLB VIP 或 SE/控制器服务器 IP  <br/>  192.168.21.121 <br/> |部署此记录是可选 3 <br/> ||
|SRV  <br/> |_sipinternaltls._tcp。 _ \<sipdomain\> _端口 5061 <br/> _sipinternaltls._tcp。 _contoso.com_端口 5061 <br/> |前结束池的 FQDN  <br/>  _FE Pool.contoso.com_ <br/> |允许内部用户自动登录 1 到前端服务器/池或 SE 服务器/池进行身份验证并将用于登录的客户端请求重定向。 <br/> |2 <br/> |
|SRV  <br/> |_sipinternal。 _\<sipdomain\>_ <br/> _sipinternal。 _contoso.com_ <br/> |前结束池的 FQDN  <br/>  _FE Pool.contoso.com_ <br/> |内部用户访问 1 <br/> |2 <br/> |
|SRV  <br/> |_ntp._udp。 _\<sipdomain\>_ <br/> _ntp._udp。 _contoso.com_ <br/> |时间服务器 FQDN  <br/> 北美-america.pool.ntp.org  <br/> |NTP Lync 电话版设备所需的源  <br/> |这是支持桌面电话机所需要的。  <br/> |
|SRV  <br/> |_sipfederationtls._tcp。  _\<sipdomain\>_ <br/> _sipfederationtls._tcp。  _contoso.com_ <br/> | 访问边缘服务 FQDN <br/> EdgePool int. _contoso.com_ <br/> |创建一个有 IOS 或电话移动客户端的 Windows 的每个 SIP 域的 SRV 记录。  <br/> |为移动式客户机支持  <br/> |
|A/AAAA  <br/> |管理 URL  <br/>  _网站 int.contoso.com_ <br/> |HLB FE 池 VIP  <br/> 192.168.21.121  <br/> |Skype 的业务服务器控制面板，看到[简单的 Url](dns.md#BK_Simple) <br/> ||
|A/AAAA  <br/> |满足的 URL  <br/>  _网站 int.contoso.com_ <br/> |HLB FE 池 VIP  <br/> 192.168.21.121  <br/> |联机会议，请参阅[简单的 Url](dns.md#BK_Simple) <br/> ||
|A/AAAA  <br/> |拨入 URL  <br/>  _网站 int.contoso.com_ <br/> |HLB FE 池 VIP  <br/> 192.168.21.121  <br/> |拨入会议看到[简单的 Url](dns.md#BK_Simple) <br/> ||
|A/AAAA  <br/> |内部 Web 服务 FQDN  <br/>  _网站 int.contoso.com_ <br/> |HLB FE 池 VIP  <br/> 192.168.21.121  <br/> |Skype 业务 Skype 业务 Web 应用程序使用的 Web 服务  <br/> ||
|A/AAAA  <br/> |Office 应用程序的 Web 服务器池的 FQDN  <br/> OWA.contoso.com  <br/> | Office 应用程序的 Web 服务器池 VIP 地址 <br/> 192.168.1.5  <br/> |定义 Office Web 应用程序服务器池的 FQDN  <br/> ||
|A/AAAA  <br/> | 内部 Web FQDN <br/> 网站 int.contoso.com  <br/> | 前结束 VIP 地址池 <br/> 192.168.21.121  <br/> |定义用于通过 Skype 业务 Web 应用程序内部 Web FQDN  <br/> 如果您使用 DNS 负载平衡在此池中，您的前端池和内部 web 服务器场不能有相同的 FQDN。  <br/> ||
   
 **1**使用者来发现该前端服务器或前端池，并进行身份验证和登录的用户的客户端。 [演练的 Skype 业务客户端](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)查找服务是对此的更多详细信息。
  
 **2**这只需要支持旧客户端，然后再 Lync 2013 和桌面电话机。
  
 **3**中的情况： 统一通信设备打开的但用户从未登录到该设备，A 记录允许发现承载设备更新 Web 服务的服务器并获取更新的设备。 否则，设备在用户首次登录时通过带内设置获得服务器信息。
  
下图显示的示例，包括内部和外部 DNS 记录，和很多周围的表中显示的记录： 
  
**使用公用 IPv4 地址的边缘网络图**

![DNS 网络图表示例](../../media/2cc9546e-5560-4d95-8fe4-65a792a0e9c3.png)
  
**外围网络 DNS 映射 （内部和外部接口）**

|**记录类型**|**值**|**解析为**|**目的**|**必填**|
|:-----|:-----|:-----|:-----|:-----|
|A/AAAA  <br/> |内部边缘池的 FQDN  <br/>  _EdgePool int.contoso.com_ <br/> |面向内部的边缘池中的 IP 地址  <br/> 172.25.33.10、 172.25.33.11  <br/> |合并边池内部接口的 IP 地址  <br/> |Y  <br/> |
|A/AAAA  <br/> |边缘服务器 FQDN  <br/>  _缺点-1.contoso.com_ <br/> |面向内部的服务器 IP 边缘池中的服务器  <br/> 172.25.33.10  <br/> |创建记录池中的每个服务器与服务器 FQDN 指向其内部服务器节点 IP 池中，请参阅[DNS 上边缘服务器池的负载平衡](load-balancing.md#BK_Edge)。  <br/> |Y  <br/> |
|A/AAAA  <br/> |访问边缘服务池的 FQDN  <br/>  _Access1.contoso.com_ <br/> |访问边缘服务池外部 IP 地址  <br/> 131.107.16.10、 131.107.16.11  <br/> |访问边缘服务提供单一的受信任连接点用于出站和入站会话启动协议 (SIP) 通信。  <br/> |Y  <br/> |
|A/AAAA  <br/> |Web 会议边缘服务池的 FQDN  <br/>  _Webcon1.contoso.com_ <br/> |Web 会议边缘服务外部 IP 地址  <br/> 131.107.16.90、 131.107.16.91  <br/> |Web 会议边缘服务使外部用户可以加入您的企业服务器环境的内部 Skype 上承载的会议。  <br/> |Y  <br/> |
|A/AAAA  <br/> | _av.\<sip 域\>_池的 FQDN <br/>  _AV1.contoso.com_ <br/> |A / V 边缘外部 IP 地址  <br/> 131.107.16.170、 131.107.16.171  <br/> |A / V 边缘服务使音频、 视频、 应用程序共享和文件传输提供给外部用户。  <br/> |Y  <br/> |
|CNAME  <br/> |sip。 _\<sipdomain\>_ <br/> sip。 _contoso.com_ <br/> |外部访问边缘池的 FQDN  <br/>  _Access1.contoso.com_ <br/> |查找边缘服务器池。 请参见[演练的 Skype 业务客户端查找服务](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype) <br/> |Y  <br/> |
|SRV  <br/> |_sip._tls。 _\<sipdomain\>_ <br/> _sip._tls。 _contoso.com_ <br/> |外部访问边缘 FQDN  <br/>  _Access1.contoso.com_ <br/> |用于外部用户访问。 请参见[演练的 Skype 业务客户端查找服务](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype) <br/> |Y  <br/> |
|SRV  <br/> |_sipfederationtls._tcp。 _\<sipdomain\>_ <br/> _sipfederationtls._tcp。 _contoso.com_ <br/> |外部访问边缘 FQDN  <br/>  _Access1.contoso.com_ <br/> |用于联盟和公用 IM 连接  <br/> |1 <br/> |
|SRV  <br/> |_xmpp-server._tcp。 _\<sipdomain\>_ <br/> _xmpp-server._tcp。 _contoso.com_ <br/> |外部访问边缘 FQDN  <br/>  _Access1.contoso.com_ <br/> |XMPP 代理服务接受并将可扩展消息和状态协议 (XMPP) 消息发送与配置的 XMPP 的联盟伙伴。  <br/> |Y，部署联合身份验证，否则为可选  <br/> |
|SRV  <br/> |_sipfederationtls._tcp。  _\<sipdomain\>_ <br/> _sipfederationtls._tcp。  _contoso.com_ <br/> |外部访问边缘 FQDN  <br/>  _Access1.contoso.com_ <br/> |为了支持推送通知服务和苹果推送通知服务，您可以创建一个为每个 SIP 域的 SRV 记录。 3 <br/> ||
|A/AAAA  <br/> |外部的前端池 web 服务 FQDN  <br/>  _网站 ext.contoso.com_ <br/> |反向代理服务器的公共 IP 地址，到您的前端池 1 外部 Web 服务 VIP 的代理 <br/> 131.107.155.1 192.168.21.120 代理  <br/> |前结束池外部接口用于通过 Skype 业务 Web 应用程序  <br/> |Y  <br/> |
|A/AAAA/CNAME  <br/> |lyncdiscover. _\<sipdomain\>_ <br/> lyncdiscover. _contoso.com_ <br/> |如果您没有一个主管 2，反向代理服务器的公用 IP 地址，而解析为主任池，外部 Web 服务 VIP 如果有的话，或为前端池 <br/> 131.107.155.1 192.168.21.120 代理  <br/> | 通过反向代理服务器的外部客户端的记录自动发现，也可由移动，Skype 业务的 Web 应用程序和计划程序 Web 应用程序中，解决 <br/> 若要支持推送通知服务和苹果推送通知服务，您可以创建一个具有 Microsoft Lync 移动客户端的每个 SIP 域的 SRV 记录。 3 <br/> |Y  <br/> |
|A/AAAA  <br/> |满足。 _\<sipdomain\>_ <br/> 满足。 _contoso.com_ <br/> |反向代理服务器的公用 IP 地址，而解析为前端池的外部 Web 界面  <br/> 131.107.155.1 192.168.21.120 代理  <br/> |Skype 业务 Web 服务代理  <br/> [简单的 Url](dns.md#BK_Simple) ，请参阅 <br/> |Y  <br/> |
|A/AAAA  <br/> |拨入_\<sipdomain\>_ <br/> 拨入_contoso.com_ <br/> |反向代理服务器的公共 IP 地址，到前端池的外部 Web 接口的代理  <br/> 131.107.155.1 192.168.21.120 代理  <br/> |Skype 业务 Web 服务代理  <br/> [简单的 Url](dns.md#BK_Simple) ，请参阅 <br/> |Y  <br/> |
|A/AAAA  <br/> |Office 应用程序的 Web 服务器池的 FQDN  <br/> OWA.contoso.com  <br/> | 反向代理服务器的公用 IP 地址，而 Office Web 应用程序服务器的外部 Web 界面的代理 <br/> 131.107.155.1 192.168.1.5 代理  <br/> | Office 应用程序的 Web 服务器池 VIP 地址 <br/> 192.168.1.5  <br/> |定义 Office Web 应用程序服务器池的 FQDN  <br/> |
   
 联合身份验证，否则为可选的部署所需的**1** 。
  
 **2**使用者发现的前端服务器或前端池，并进行身份验证和用户身份登录客户端。
  
 **3**这一要求只适用于苹果上的客户端或基于 Microsoft 的移动设备。 Android 和 Nokia Symbian 设备不使用推送通知。
  
 边缘服务器和外围网络的详细信息，请参阅边缘服务器[DNS 规划](../../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#DNSPlan)内容。
  
> [!IMPORTANT]
> Skype 业务服务器支持使用 IPv6 寻址。 有关更多详细信息，请参阅[规划业务的 Skype 在 IPv6](ipv6.md) 。
  
> [!IMPORTANT]
> 对于 Fqdn 的详细信息，请参阅[DNS 基础](basics.md)。 
  
 **裂脑 DNS** 
 <a name="BK_split"> </a>
 
裂脑 DNS 是 DNS 配置中必须使用相同的命名空间的两个 DNS 区域。 第一个 DNS 区域处理内部请求，而第二个 DNS 区域来处理外部请求，如在这些表中所述。 有关详细信息，请参阅[Split-brain DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS)。 
  
## <a name="hybrid-considerations"></a>混合的注意事项
<a name="BK_Hybrid"> </a>

如果您计划让某些用户位于联机和穴的某些场所，是指混合[的 DNS 设置](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md#BKMK_DNS)。 您将需要为配置 DNS 作为正常的 Skype 业务服务器 2015年还添加其他 DNS 记录。 
  
此外应该在参考的"Office 365 的 Url 和 IP 地址范围"[http://aka.ms/o365ips](http://aka.ms/o365ips)以确认您的用户将有权访问他们需要的联机资源。
  
## <a name="simple-urls"></a>简单 URL
<a name="BK_Simple"> </a>

统一资源定位器 (URL) 是指一种计算机网络，用来检索它的协议在指定其位置的 web 资源。 
  
Skype 业务服务器支持使用三个"简单"的 Url 来访问服务：
  
- **满足**用作基 URL 站点中的所有会议。 一种满足的简单的 URL 是https://meet.contoso.com。为特定会议的 URL 可能是https://meet.contoso.com//7322994 的_用户名_。 
    
    与满足简单的 URL，加入会议的链接都是易于理解、 易于沟通。
    
- **拨入**允许拨入会议设置 web 页的访问。 此页显示其可用的语言，分配会议信息与会议拨入号码 (即，不需要安排的会议)，会议中 DTMF 控件，并支持管理的个人标识号码 （PIN) 并分配会议信息。 拨入简单 URL 包含在所有会议邀请中，以便用户需要拨号加入会议所需的电话号码和 PIN 信息可以访问。 拨入简单 URL 的一个示例是https://dialin.contoso.com。
    
- **管理**业务服务器控件面板使对 Skype 的快速访问。 从您的组织的防火墙内的任何计算机，管理员可以打开 Skype 业务服务器控件面板通过在浏览器中键入管理简单的 URL。 管理简单的 URL 是组织内部的。 管理简单的 URL 的示例是https://admin.contoso.com。
    
在[DNS 中业务服务器 2015年的 Skype 的简单 Url 要求](simple-urls.md)更详细地讨论了简单的 Url。
  
## <a name="dns-by-server-role"></a>DNS 服务器角色
<a name="BK_Servers"> </a>

如愿意，但是使它们成为令人难忘和反映它们的功能在系统中，您可以设置这些池和服务器的名称。
  
### <a name="dns-records-for-individual-servers-or-pools"></a>单独的服务器或池的 DNS 记录

这些泛型记录要求适用于任何服务器角色使用 Skype 的业务。 池是一组服务器运行相同的服务协同工作以处理客户端请求定向到他们通过负载平衡器。 有关详细信息请参阅[负载平衡对 Skype 的业务要求](load-balancing.md)
  
**DNS 服务器/池角色记录要求 （假定 DNS 负载平衡）**

|**部署方案**|**DNS 的要求**|
|:-----|:-----|
|一台服务器：  <br/> 持久的聊天，主任、 中介服务器，前端服务器  <br/> |将服务器的完全限定的域名 (FQDN) 解析为其 IP 地址的内部 A 记录。  <br/> ServerRole.contoso.com 10.10.10.0  <br/> |
|池：  <br/> 持久交谈、 控制器、 边缘服务器、 中介服务器，前端  <br/> |内部记录解析为其 IP 地址池中的每个服务器节点的完全限定的域名 (FQDN)。  <br/> **示例** <br/> ServerRole01.contoso.com 10.10.10.1  <br/> ServerRole02.contoso.com 10.10.10.2  <br/> 多个内部的记录在池中可解析为服务器的节点的 IP 地址池的完全合格的域名称 (FQDN)。  <br/> **示例** <br/> ServerPool.contoso.com 10.10.10.1  <br/> ServerPool.contoso.com 10.10.10.2  <br/> |
   
### <a name="edge-server-specific-dns-topics"></a>边缘服务器特定 DNS 主题

 规划边缘服务器部署，检查[边缘服务器部署在 Skype 的业务服务器 2015年计划](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md)，和[高级边缘服务器 DNS 规划业务服务器 2015年的 Skype](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md)的包含以下部分
  
- [DNS disaster recovery](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSDR)
    
- [DNS load balancing](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB)
    
- [Automatic configuration without split-brain DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#NoSplitBrainDNS)
    
- [Split-brain DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS)
    
- [Walkthrough of Skype for Business clients locating services](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)
    

