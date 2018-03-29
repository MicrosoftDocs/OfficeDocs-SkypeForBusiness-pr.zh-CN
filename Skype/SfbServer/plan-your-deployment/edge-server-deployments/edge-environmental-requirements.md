---
title: Skype for Business Server 2015 的边缘服务器环境要求
ms.author: heidip
author: microsoftheidi
ms.date: 2/23/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Hybrid
ms.assetid: 67435465-b4d0-4e38-8e03-56a60b844a34
description: 摘要： 了解业务服务器 2015 Skype 在边缘服务器的环境要求。
ms.openlocfilehash: fd3c7d6c5fe138878b0122ea5c1885ad6ef84171
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="edge-server-environmental-requirements-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 的边缘服务器环境要求
 
**摘要：**了解有关业务服务器 2015年边缘服务器在 Skype 的环保要求。
  
大量的规划和准备工作需要采取 Skype 业务服务器 2015年边缘服务器环境本身以外的地方。 本文中，我们将按照下面的列表回顾需要在组织环境中进行哪些准备工作：
  
- [Topology planning](edge-environmental-requirements.md#TopoPlan)
    
- [DNS planning](edge-environmental-requirements.md#DNSPlan)
    
- [Certificate planning](edge-environmental-requirements.md#CertPlan)
    
- [Port and firewall planning](edge-environmental-requirements.md#PortFirewallPlan)
    
## <a name="topology-planning"></a>拓扑规划
<a name="TopoPlan"> </a>

Skype 的业务服务器 2015年边缘服务器拓扑还可以使用：
  
- 可路由的公用 IP 地址。
    
- 不可路由的专用 IP 地址（如果使用**对称**网络地址转换 (NAT)）。
    
> [!TIP]
> 可配置边缘服务器的不同端口使用单个 IP 地址，每个服务，也可以为每个服务，使用不同的 IP 地址，但可以使用同一默认端口 （默认情况下将的 TCP 443）。 在后面的 IP 地址要求部分中，我们会介绍更多信息。 
  
如果选择结合 NAT 使用不可路由的专用 IP 地址，请记住以下几点：
  
- 需要在**所有三个**外部接口上使用可路由的专用 IP 地址。
    
- 需要为传入和传出流量配置**对称** NAT。 对称 NAT 是唯一受支持的可用于业务服务器 2015年边缘服务器与 Skype 的 NAT。
    
- 将 NAT 配置为不要更改传入的源地址。 A / V 边缘服务需要能够接收传入的源地址，以找到最佳媒体路径。
    
- 边缘服务器需要能够与另一个通信从其公用的 A / V 边缘 IP 地址。 防火墙需要允许此流量。
    
- NAT 可以**仅**用于比例合并的边缘服务器如果使用 DNS 负载平衡。 如果使用硬件负载平衡 (HLB)，那就需要使用**无** NAT 的可公共路由的 IP 地址。
    
将有没有问题，让您的访问，Web 会议和 A / V 边缘路由器或执行单一和缩放对称 NAT 防火墙后面的接口合并边缘服务器拓扑 （只要您不使用硬件负载平衡）。
  
### <a name="summary-of-edge-server-topology-options"></a>边缘服务器拓扑选项摘要

我们有几个拓扑可用的 Skype 的业务服务器 2015年边缘服务器部署选项：
  
- 使用专用 IP 地址和 NAT 的单一合并边缘
    
- 使用公用 IP 地址的单一合并边缘
    
- 使用专用 IP 地址和 NAT 的扩展合并边缘
    
- 使用公用 IP 地址的扩展合并边缘
    
- 使用硬件负载平衡器的扩展合并边缘
    
为帮助你选择一种拓扑，我们准备了下表，该表提供了每种拓扑可选择哪些选项的摘要：
  
|**拓扑**|**高可用性**|**其他边缘池中的外部边缘服务器所需的 DNS 记录？**|**Skype 业务服务器会话的边缘故障转移**|**Skype 业务服务器联盟会话边缘故障转移**|
|:-----|:-----|:-----|:-----|:-----|
|使用专用 IP 地址和 NAT 的单一合并边缘  <br/> |否  <br/> |否  <br/> |否  <br/> |否  <br/> |
|使用公用 IP 地址的单一合并边缘  <br/> |否  <br/> |否  <br/> |否  <br/> |否  <br/> |
|使用专用 IP 地址和 NAT 的扩展合并边缘（DNS 负载平衡）  <br/> |是  <br/> |是  <br/> |是  <br/> |是 & sup1;  <br/> |
|使用公用 IP 地址的扩展合并边缘（DNS 负载平衡）  <br/> |是  <br/> |是  <br/> |是  <br/> |是 & sup1;  <br/> |
|使用硬件负载平衡器的扩展合并边缘  <br/> |是  <br/> |不支持（每个 VIP 一个 DNS A 记录）  <br/> |是  <br/> |是  <br/> |
   
和 sup1;Exchange 统一消息 (UM) 使用 DNS 负载平衡的远程用户故障转移要求 2013年或更高版本的 Exchange。
  
### <a name="ip-address-requirements"></a>IP 地址要求

在基本的层面上，这三项服务需要 IP 地址。访问边缘服务、 Web 会议边缘服务和 A / V 边缘服务。 可以选择使用三个 IP 地址，每种服务对应一个地址，也可以使用一个 IP 地址，并选择将每种服务置于不同的端口（有关这方面的更多信息，可查看[Port and firewall planning](edge-environmental-requirements.md#PortFirewallPlan)）。 对于单一合并边缘环境，差不多就是这样。
  
> [!NOTE]
> 前面说过，你可以选择让所有三种服务使用同一个 IP 地址，但运行于不同的端口。但需要澄清的是，我们不建议这样做。如果客户无法访问你在这种情况下使用的备用端口，他们也就不能获得边缘环境的全部功能。 
  
扩展合并拓扑可能稍微复杂一点，所以我们来看一下列出 IP 地址要求的几张表，同时请牢记，拓扑选择的主要决策点是高可用性和负载平衡。高可用性需求可能影响负载平衡选择（在表的后面，我们将深入讨论）。
  
#### <a name="ip-address-requirements-for-scaled-consolidated-edge-ip-address-per-role"></a>扩展合并边缘的 IP 地址要求（每个角色一个 IP 地址）

|**每个池的边缘服务器数**|**数所需的 IP 地址，dns 负载平衡**|**所需硬件负载平衡的 IP 地址数**|
|:-----|:-----|:-----|
|2  <br/> |6  <br/> |3（每个 VIP 1 个）6  <br/> |
|3  <br/> |9  <br/> |3（每个 VIP 1 个）9  <br/> |
|4  <br/> |12  <br/> |3（每个 VIP 1 个）12  <br/> |
|5  <br/> |15  <br/> |3（每个 VIP 1 个）15  <br/> |
   
#### <a name="ip-address-requirements-for-scale-consolidated-edge-single-ip-address-for-all-roles"></a>扩展合并边缘的 IP 地址要求（所有角色一个 IP 地址）

|**每个池的边缘服务器数**|**数所需的 IP 地址，dns 负载平衡**|**所需硬件负载平衡的 IP 地址数**|
|:-----|:-----|:-----|
|2  <br/> |2  <br/> |1（每个 VIP 1 个）2  <br/> |
|3  <br/> |3  <br/> |1（每个 VIP 1 个）3  <br/> |
|4  <br/> |4  <br/> |1（每个 VIP 1 个）4  <br/> |
|5  <br/> |5  <br/> |1（每个 VIP 1 个）5  <br/> |
   
我们来看看规划时要考虑的一些其他事项。
  
- **高可用性**： 如果您在部署中需要高可用性，您应部署在池中至少两个边缘服务器。 值得注意的，单个边池将支持多达 12 个边缘服务器 （尽管拓扑生成器允许您添加达 20，有测试，或不支持，因此，我们建议您不要这样做）。 如果您需要以上 12 个边缘服务器时，您应为其创建其他边缘池。
    
- **硬件负载平衡**： 我们建议 DNS 负载平衡对于大多数方案。 硬件负载平衡也支持，当然，但值得注意的是它具有所需的单个方案通过 DNS 负载平衡：
    
  - 外部访问 Exchange 2007 或 Exchange 2010 （与没有 SP) 统一邮件 (UM)。
    
- **DNS 负载平衡**： 为 UM、 Exchange 2010 SP1 和更高版本都能支持的 DNS 负载平衡。 请注意，如果您需要去 DNS 负载平衡以早期版本的 Exchange，很好，但对此的所有通信都将都转到池中的第一个服务器是否不可用，该通讯随后将失败。
    
    如果您正在使用 Lync Server 2010、 Lync Server 2013 和 Microsoft Office 365 的公司联盟还建议 DNS 负载平衡。
    
## <a name="dns-planning"></a>DNS 规划
<a name="DNSPlan"> </a>

谈到 Skype 业务服务器 2015年边缘服务器部署，关键是要为 DNS 正确地准备。 如果正确的记录就位，部署就会容易得多。 但愿你选择了上一节中的拓扑，因为我们将作一下总结，然后列出几张表，这些表概列了适用于那些方案的 DNS 记录。 我们还必须一些[高级边缘服务器 DNS 规划业务服务器 2015年的 Skype](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md)的更多深入阅读，如果您需要它。
  
### <a name="dns-records-for-single-consolidated-edge-server-scenarios"></a>单一的 DNS 记录合并边缘服务器方案

这些将是您将需要为单个边缘服务器使用任何公共 IPs 或 nat 的专用 Ip 的 DNS 记录 因为这是示例数据，所以我们将提供示例 IP，便于你更容易地制定出自己的条目：
  
- 内部网络适配器：172.25.33.10（未分配默认网关的地址）
    
    > [!NOTE]
    > 请确保从边缘到任何包含服务器 （例如，从 192.168.10.0 到 172.25.33.0) 业务服务器 2015年或 Lync Server 2013 客户端运行 Skype 的网络的内部接口所在网络的路由。 
  
- 外部网络适配器：
    
  - 公用 IP：
    
  - 访问边缘： 131.107.155.10 (这是主，设置为您的公用路由器的默认网关： 131.107.155.1)
    
  - Web 会议边缘： 131.107.155.20 （第二）
    
  - A / V 边缘： 131.107.155.30 （第二）
    
  Web 会议，A / V 边缘的公共 IP 地址的其他属性的 Internet 协议版本 4 (TCP/IPv4) 和 Internet 协议版本 6 (TCP/IPv6) 的本地区域连接属性的高级部分中 （第二） 的 IP 地址Windows 服务器。
    
  - 专用 IP：
    
  - 访问边缘： 10.45.16.10 (这是主，设置您的路由器的默认网关： 10.45.16.1)
    
  - Web 会议边缘： 10.45.16.20 （第二）
    
  - A / V 边缘： 10.45.16.30 （第二）
    
Web 会议，A / V 边缘的公共 IP 地址的其他属性的 Internet 协议版本 4 (TCP/IPv4) 和 Internet 协议版本 6 (TCP/IPv6) 的本地区域连接属性的高级部分中 （第二） 的 IP 地址Windows 服务器。
  
> [!TIP]
>这里有其他可行的配置：
  
- 可以在外部网络适配器上使用一个 IP 地址。 我们不建议这样，因为随后您将需要区分电子服务使用不同的端口 （这可以在 Skype 来完成业务服务器） 但有某些防火墙可能会阻止备用端口。 有关这方面的更多内容，请参阅[Port and firewall planning](edge-environmental-requirements.md#PortFirewallPlan)一节。
    
- 可以准备三个外部网络适配器，而不是一个，为每个服务分配其中一个服务 IP。为什么这样做？因为这会分隔这些服务，如果出现问题，这更便于排查故障，并可能在你解决问题时，让其他服务继续运行。
    
|**位置**|**类型**|**端口**|**FQDN 或 DNS 记录**|**IP 地址或 FQDN**|**说明**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|外部 DNS  <br/> |A 记录  <br/> |NA  <br/> |sip.contoso.com  <br/> |**公共：** 131.107.155.10 <br/> **专用：** 10.45.16.10 <br/> |访问边缘服务的外部接口。 您将需要一个用于每个 SIP 域与 Skype 业务用户。  <br/> |
|外部 DNS  <br/> |A 记录  <br/> |NA  <br/> |webcon.contoso.com  <br/> |**公共：** 131.107.155.20 <br/> **专用：** 10.45.16.20 <br/> |Web 会议边缘服务的外部接口。  <br/> |
|外部 DNS  <br/> |A 记录  <br/> |NA  <br/> |av.contoso.com  <br/> |**公共：** 131.107.155.30 <br/> **专用：** 10.45.16.30 <br/> |外部接口您的 A / V 边缘服务。  <br/> |
|外部 DNS  <br/> |SRV 记录  <br/> |443  <br/> |_sip._tls.contoso.com  <br/> |sip.contoso.com  <br/> |访问边缘服务的外部接口。 此 SRV 记录是必需的 Skype 业务服务器 2015年，Lync Server 2013，Lync Server 2010 对外处理的客户端。 您将需要一个用于每个域与 Skype 业务用户。  <br/> |
|外部 DNS  <br/> |SRV 记录  <br/> |5061  <br/> |_sipfederationtls._tcp.contoso.com  <br/> |sip.contoso.com  <br/> |访问边缘服务的外部接口。 称为“允许的 SIP 域”的联盟伙伴的自动 DNS 发现需要此 SRV 记录。 您将需要一个用于每个域与 Skype 业务用户。  <br/> |
|内部 DNS  <br/> |A 记录  <br/> |NA  <br/> |sfvedge.contoso.net  <br/> |172.25.33.10  <br/> |合并边缘的内部接口。  <br/> |
   
### <a name="dns-records-for-scaled-dns-and-hardware-edge-server-scenarios"></a>缩放的 DNS 和硬件的边缘服务器方案中的 DNS 记录

这些将是您将需要为单个边缘服务器使用任何公共 IPs 或 nat 的专用 Ip 的 DNS 记录 因为这是示例数据，所以我们将提供示例 IP，便于你更容易地制定出自己的条目：
  
- 内部网络适配器：
    
  - 节点 1：172.25.33.10（未分配默认网关的地址）
    
  - 节点 2：172.25.33.11（未分配默认网关的地址）
    
    > [!NOTE]
    > 请确保从边缘到任何包含服务器 （例如，从 192.168.10.0 到 172.25.33.0) 业务服务器 2015年或 Lync Server 2013 客户端运行 Skype 的网络的内部接口所在网络的路由。 
  
- 外部网络适配器：
    
  - 节点 1
    
     - 公用 IP：
    
        - 访问边缘： 131.107.155.10 (这是主，设置为您的公用路由器的默认网关： 131.107.155.1)
    
        - Web 会议边缘： 131.107.155.20 （第二）
    
        - A / V 边缘： 131.107.155.30 （第二）
    
          Web 会议，A / V 边缘的公共 IP 地址的其他属性的 Internet 协议版本 4 (TCP/IPv4) 和 Internet 协议版本 6 (TCP/IPv6) 的本地区域连接属性的高级部分中 （第二） 的 IP 地址Windows 服务器。
    
    - 专用 IP：
    
         - 访问边缘： 10.45.16.10 (这是主，设置您的路由器的默认网关： 10.45.16.1)
    
         - Web 会议边缘： 10.45.16.20 （第二）
    
         - A / V 边缘： 10.45.16.30 （第二）
    
      Web 会议，A / V 边缘的公共 IP 地址的其他属性的 Internet 协议版本 4 (TCP/IPv4) 和 Internet 协议版本 6 (TCP/IPv6) 的本地区域连接属性的高级部分中 （第二） 的 IP 地址Windows 服务器。
    
  - 节点 2
    
     - 公用 IP：
    
       - 访问边缘： 131.107.155.11 (这是主，设置为您的公用路由器的默认网关： 131.107.155.1)
    
       - Web 会议边缘： 131.107.155.21 （第二）
    
       - A / V 边缘： 131.107.155.31 （第二）
    
      Web 会议，A / V 边缘的公共 IP 地址的其他属性的 Internet 协议版本 4 (TCP/IPv4) 和 Internet 协议版本 6 (TCP/IPv6) 的本地区域连接属性的高级部分中 （第二） 的 IP 地址Windows 服务器。
    
  - 专用 IP：
    
      - 访问边缘： 10.45.16.11 (这是主，设置您的路由器的默认网关： 10.45.16.1)
    
      - Web 会议边缘： 10.45.16.21 （第二）
    
      - A / V 边缘： 10.45.16.31 （第二）
    
      Web 会议，A / V 边缘的公共 IP 地址的其他属性的 Internet 协议版本 4 (TCP/IPv4) 和 Internet 协议版本 6 (TCP/IPv6) 的本地区域连接属性的高级部分中 （第二） 的 IP 地址Windows 服务器。
    
这里有其他可行的配置：
  
- 可以在外部网络适配器上使用一个 IP 地址。 我们不建议这样，因为随后您将需要区分电子服务使用不同的端口 （这可以在 Skype 来完成业务服务器） 但有某些防火墙可能会阻止备用端口。 有关这方面的更多内容，请参阅[Port and firewall planning](edge-environmental-requirements.md#PortFirewallPlan)一节。
    
- 可以准备三个外部网络适配器，而不是一个，为每个服务分配其中一个服务 IP。为什么这样做？因为这会分隔这些服务，如果出现问题，这更便于排查故障，并可能在你解决问题时，让其他服务继续运行。
    
|**位置**|**类型**|**端口**|**FQDN 或 DNS 记录**|**IP 地址或 FQDN**|**说明**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|外部 DNS  <br/> |A 记录  <br/> |NA  <br/> |sip.contoso.com  <br/> |**公共：** 131.107.155.10 和 131.107.155.11 <br/> **专用：** 10.45.16.10 和 10.45.16.11 <br/> |访问边缘服务的外部接口。 您将需要一个用于每个 SIP 域与 Skype 业务用户。  <br/> |
|外部 DNS  <br/> |A 记录  <br/> |NA  <br/> |webcon.contoso.com  <br/> |**公共：** 131.107.155.20 和 131.107.155.21 <br/> **专用：** 10.45.16.20 和 10.45.16.21 <br/> |Web 会议边缘服务的外部接口。  <br/> |
|外部 DNS  <br/> |A 记录  <br/> |NA  <br/> |av.contoso.com  <br/> |**公共：** 131.107.155.30 和 131.107.155.31 <br/> **专用：** 10.45.16.30 和 10.45.16.31 <br/> |外部接口您的 A / V 边缘服务。  <br/> |
|外部 DNS  <br/> |SRV 记录  <br/> |443  <br/> |_sip._tls.contoso.com  <br/> |sip.contoso.com  <br/> |访问边缘服务的外部接口。 此 SRV 记录是必需的 Skype 业务服务器 2015年，Lync Server 2013，Lync Server 2010 对外处理的客户端。 您需要一个用于每个域与 Skype 业务。  <br/> |
|外部 DNS  <br/> |SRV 记录  <br/> |5061  <br/> |_sipfederationtls._tcp.contoso.com  <br/> |sip.contoso.com  <br/> |访问边缘服务的外部接口。 称为“允许的 SIP 域”的联盟伙伴的自动 DNS 发现需要此 SRV 记录。 您需要一个用于每个域与 Skype 业务。  <br/> |
|内部 DNS  <br/> |A 记录  <br/> |NA  <br/> |sfvedge.contoso.net  <br/> |172.25.33.10 和 172.25.33.11  <br/> |合并边缘的内部接口。  <br/> |
   
### <a name="dns-record-for-federation-all-scenarios"></a>联盟的 DNS 记录（所有方案）

|**位置**|**类型**|**端口**|**FQDN**|**FQDN 主机记录**|**说明**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|外部 DNS  <br/> |SRV  <br/> |5061  <br/> |_sipfederationtls_tcp.contoso.com  <br/> |sip.contoso.com  <br/> |SIP 访问边缘外部接口所需的自动 DNS 搜索。 由其他潜在的联盟伙伴使用。 这也称为“允许的 SIP 域”。 将适用于业务用户需要一种与 Skype 的每个 SIP 域。  <br/><br/> **注意：**您将需要此 SRV 记录用于移动和交换所推式通知。 <br/> |
   
### <a name="dns-records-for-extensible-messaging-and-presence-protocol"></a>可扩展消息传递和状态协议的 DNS 记录

|**位置**|**类型**|**端口**|**FQDN**|**IP 地址或 FQDN 主机记录**|**说明**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|外部 DNS  <br/> |SRV  <br/> |5269  <br/> |_xmpp server._tcp.contoso.com  <br/> |xmpp.contoso.com  <br/> |XMPP 代理的接口访问边缘服务或边缘池上。 您需要重复此步骤，根据需要为所有内部 SIP 域与 Skype 业务启用用户通过允许用 XMPP 联系人的联系人的位置：  <br/> • 全球政策  <br/> • 在启用用户的网站策略  <br/> • 用户策略应用于企业的 Skype 启用用户  <br/> 在 XMPP 联盟用户策略中，还需要配置允许的 XMPP 策略。  <br/> |
|外部 DNS  <br/> |SRV  <br/> |A  <br/> |xmpp.contoso.com  <br/> |边缘服务器上承载 XMPP 代理服务的边缘池的访问边缘服务 IP 地址  <br/> |这点到边缘服务器或池边缘上的访问边缘服务承载 XMPP 代理服务。 通常，你创建的 SRV 记录将指向主机（A 或 AAAA）记录。  <br/> |
   
## <a name="certificate-planning"></a>证书规划
<a name="CertPlan"> </a>

业务服务器 2015年的 Skype 使用证书来获得安全、 加密从服务器向客户端和服务器之间的通信。 正如你料想的那样，证书需要服务器的 DNS 记录与证书中的任何使用者名称 (SN) 和使用者替代名称 (SAN) 匹配。 在规划阶段，现在这需要花些功夫，确保在 DNS 中注册对应于证书 SN 和 SAN 条目的正确 FQDN。
  
我们将分别讨论外部和内部证书需求，然后查看提供两种需求的表。
  
### <a name="external-certificates"></a>外部证书

至少，需要提供的公用证书颁发机构 (CA) 分配给外部边缘服务器接口的证书。 我们不能建议一个特定的 CA，但我们有的[统一通信证书的合作伙伴](https://support.microsoft.com/en-us/kb/929395)，您可以看一看以查看是否列出了您首选的 CA 的 Ca 列表。
  
你什么时候需要向 CA 提出申请，索要这份公共证书，如何提出申请？有几种方式可以完成申请：
  
- 您可以通过 Skype 业务服务器，然后部署边缘服务器的安装。 Skype 业务服务器部署向导会生成一个证书请求，然后再发送到您选择的 CA 的步骤。
    
- 此外可以使用 Windows PowerShell 命令来生成此请求时，如果这就是与自己的业务需求和部署策略的多个内联。
    
- 最后，您的 CA 可能有他们自己提交的过程，从而也可能导致 Windows PowerShell 或另一种方法。 这种情况下，除了此处提供的供你参考的信息外，你还需要依靠他们的文档。
    
您已经看到了证书后，您需要继续操作并将其分配给这些服务 Skype 业务服务器：
  
- 访问边缘服务接口
    
- Web 会议边缘服务接口
    
- 音频/视频认证服务 (不要混淆这用 A / V 边缘服务与不使用证书来加密音频和视频流)
    
> [!IMPORTANT]
> 对于媒体中继身份验证服务，所有边缘服务器需要有完全相同的证书，连私钥也应相同。 
  
### <a name="internal-certificates"></a>内部证书

对于内部边缘服务器接口，可以使用公共证书从公共 CA 或从您的组织内部 CA 颁发的证书。 对于内部证书，需要记住的一点是，它使用 SN 条目，没有 SAN 条目，因此你根本不用关心内部证书的 SAN。
  
### <a name="required-certificates-table"></a>所需证书表

这里有一个表可帮助你申请证书。此处的 FQDN 条目只适用于示例域。你需要根据自己的专用域和公共域提出申请，不过这里有我们所用内容的指南：
  
- contoso.com：公共 FQDN
    
- fabrikam.com：第二个公共 FQDN（作为要申请内容的演示添加，如果有多个 SIP 域可参考）
    
- Contoso.net：内部域
    
#### <a name="edge-certificate-table"></a>边缘证书表

无论是否要做一个边缘服务器或边缘池，这是您将需要为您的证书：
  
|**组件**|**使用者名称 (SN)**|**使用者备用名称 (SAN) / 顺序**|**说明**|
|:-----|:-----|:-----|:-----|
|外部边缘  <br/> |sip.contoso.com  <br/> |sip.contoso.com  <br/> webcon.contoso.com  <br/> sip.fabrikam.com  <br/> |这是需要从公共 CA 申请获得的证书。需要将其分配给以下服务的外部边缘接口：<br/> • 访问边缘  <br/> • Web 会议边缘  <br/> • 音频/视频身份验证  <br/> <br/>好消息是，San 将自动添加到您的证书申请，因此您在您的证书提交请求，基于此部署拓扑生成器中定义的内容。 你只需要添加任何其他 SIP 域的 SAN 条目或需要支持的其他条目。 为什么此例中会复制 sip.contoso.com？ 这也是自动发生的，为了让系统正常工作，需要如此。  <br/><br/> **注意：**此证书也可以用于公共即时消息连接。 对此，你无需进行任何其他操作，但是在本文档以前的版本中，这作为单独的表列出，而现在不是。 <br/> |
|内部边缘  <br/> |sfbedge.contoso.com  <br/> |NA  <br/> |可以从公共 CA 或内部 CA 获得此证书。该证书需要包含服务器 EKU（增强型密钥使用），你要将其分配给内部边缘界面。  <br/> |
   
如果可扩展消息传递和状态协议 (XMPP) 需要证书，该证书看上去与上面的外部边缘表条目完全相同，但是有以下两条额外的 SAN 条目：
  
- xmpp.contoso.com
    
- \*。 contoso.com
    
请记住，目前只有 Google Talk 支持 XMPP，如果需要将其用于任何其他地方，需要与涉及的第三方厂商确认该功能。
  
## <a name="port-and-firewall-planning"></a>端口和防火墙规划
<a name="PortFirewallPlan"> </a>

获取计划适合端口和防火墙 Skype 业务服务器边缘服务器部署可以节省您的天或几周的故障排除和压力。 因此，我们会列出几张表，这些表指出了我们的协议用途，以及对于 NAT 和公共 IP 方案，需要开放哪些端口，包括入站和出站。 我们还针对硬件负载平衡方案 (HLB) 提供了单独的表，以及这方面的进一步指导。 从那里的详细阅读，我们还提供[业务服务器 2015年的 Skype 的技术图表](../../technical-diagrams.md)，以及为您的特定部署问题可以签出某些[业务服务器 2015年的 Skype 在边缘服务器方案](scenarios.md)。
  
### <a name="general-protocol-usage"></a>常规协议用途

在查看外部和内部防火墙的摘要表之前，让我们同样考虑下面的表：
  
|**音频/视频传输**|**使用**|
|:-----|:-----|
|UDP  <br/> |音频和视频的首选传输层协议。  <br/> |
|TCP  <br/> |音频和视频的回退传输层协议。  <br/> 共享到 Skype 业务服务器 2015 Lync Server 2013，以及 Lync Server 2010 中的应用程序所需的传输层协议。  <br/> 对 Skype 业务服务器 2015 Lync Server 2013，以及 Lync Server 2010 中的文件传输所需的传输层协议。  <br/> |
   
### <a name="external-port-firewall-summary-table"></a>外部端口防火墙摘要表

源 IP 地址和目标 IP 地址将包含相应的信息，这些信息可供结合 NAT 使用专用 IP 地址的用户，以及使用公用 IP 地址的用户使用。 这将涉及我们[在业务服务器 2015年的 Skype 的边缘服务器方案](scenarios.md)一节中的所有排列。
  
|**角色或协议**|**TCP 或 UDP**|**目标端口或端口范围**|**源 IP 地址**|**目标 IP 地址**|**说明**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP  <br/> |TCP  <br/> |5269  <br/> |任意  <br/> |XMPP 代理服务 （访问边缘服务与共享的 IP 地址  <br/> |XMPP 代理服务接受来自定义 XMPP 联合体中的 XMPP 联系人通信。  <br/> |
|访问/HTTP  <br/> |TCP  <br/> |80  <br/> |**使用 NAT 的专用 IP:**边缘服务器访问边缘服务 <br/> **公共 IP:**边缘服务器访问边缘服务公用 IP 地址 <br/> |任意  <br/> |证书吊销和 CRL 检查和检索。  <br/> |
|访问/DNS  <br/> |TCP  <br/> |53  <br/> |**使用 NAT 的专用 IP:**边缘服务器访问边缘服务 <br/> **公共 IP:**边缘服务器访问边缘服务公用 IP 地址 <br/> |任意  <br/> |通过 TCP 的 DNS 查询。  <br/> |
|访问/DNS  <br/> |UDP  <br/> |53  <br/> |**使用 NAT 的专用 IP:**边缘服务器访问边缘服务 <br/> **公共 IP:**边缘服务器访问边缘服务公用 IP 地址 <br/> |任意  <br/> |通过 UDP 的 DNS 查询。  <br/> |
|访问/SIP(TLS)  <br/> |TCP  <br/> |443  <br/> |任意  <br/> |**使用 NAT 的专用 IP:**边缘服务器访问边缘服务 <br/> **公共 IP:**边缘服务器访问边缘服务公用 IP 地址 <br/> |外部用户访问的客户端到服务器 SIP 通信。  <br/> |
|访问/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |任意  <br/> |**使用 NAT 的专用 IP:**边缘服务器访问边缘服务 <br/> **公共 IP:**边缘服务器访问边缘服务公用 IP 地址 <br/> |适用于使用 SIP 的联盟和公共 IM 连接。  <br/> |
|访问/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |**使用 NAT 的专用 IP:**边缘服务器访问边缘服务 <br/> **公共 IP:**边缘服务器访问边缘服务公用 IP 地址 <br/> |任意  <br/> |适用于使用 SIP 的联盟和公共 IM 连接。  <br/> |
|Web 会议/PSOM(TLS)  <br/> |TCP  <br/> |443  <br/> |任意  <br/> |**使用 NAT 的专用 IP:**边缘服务器 Web 会议边缘服务 <br/> **公共 IP:**边缘服务器 Web 会议边缘服务服务公用 IP 地址 <br/> |Web 会议媒体。  <br/> |
|A/V/RTP  <br/> |TCP  <br/> |50000-59999  <br/> |**使用 NAT 的专用 IP:**边缘服务器 A / V 边缘服务服务 <br/> **公共 IP:**边缘服务器 A / V 边缘服务公用 IP 地址 <br/> |任意  <br/> |这可以用于中继媒体流量。  <br/> |
|A/V/RTP  <br/> |UDP  <br/> |50000-59999  <br/> |**使用 NAT 的专用 IP:**边缘服务器 A / V 边缘服务服务 <br/> **公共 IP:**边缘服务器 A / V 边缘服务公用 IP 地址 <br/> |任意  <br/> |这可以用于中继媒体流量。  <br/> |
|A/V/件。MSTURN  <br/> |UDP  <br/> |3478  <br/> |**使用 NAT 的专用 IP:**边缘服务器 A / V 边缘服务 <br/> **公共 IP:**边缘服务器 A / V 边缘服务公用 IP 地址 <br/> |任意  <br/> |3478 出站：  <br/> • 通过 Skype 业务服务器用于确定边缘与之通信的服务器的版本。  <br/> • 用于介质边缘服务器之间的通信。  <br/> • 使用 Lync Server 2010 中的联合身份验证所需。  <br/> • 如果您的组织中部署多个边缘池需要。  <br/> |
|A/V/件。MSTURN  <br/> |UDP  <br/> |3478  <br/> |任意  <br/> |**使用 NAT 的专用 IP:**边缘服务器 A / V 边缘服务 <br/> **公共 IP:**边缘服务器 A / V 边缘服务公用 IP 地址 <br/> |在端口 3478 上通过 UDP 进行的候选项 STUN/TURN 协商。  <br/> |
|A/V/件。MSTURN  <br/> |TCP  <br/> |443  <br/> |任意  <br/> |**使用 NAT 的专用 IP:**边缘服务器 A / V 边缘服务 <br/> **公共 IP:**边缘服务器 A / V 边缘服务公用 IP 地址 <br/> |在端口 443 上通过 TCP 进行的候选项 STUN/TURN 协商。  <br/> |
|A/V/件。MSTURN  <br/> |TCP  <br/> |443  <br/> |**使用 NAT 的专用 IP:**边缘服务器 A / V 边缘服务 <br/> **公共 IP:**边缘服务器 A / V 边缘服务公用 IP 地址 <br/> |任意  <br/> |在端口 443 上通过 TCP 进行的候选项 STUN/TURN 协商。  <br/> |
   
### <a name="internal-port-firewall-summary-table"></a>内部端口防火墙摘要表

|**协议**|**TCP 或 UDP**|**端口**|**源 IP 地址**|**目标 IP 地址**|**说明**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP/MTLS  <br/> |TCP  <br/> |23456  <br/> |运行 XMPP 网关服务的以下任一项：  <br/> • 前端服务器  <br/> • 前端池  <br/> |边缘服务器的内部接口  <br/> |从您在前端服务器或前端池上运行的 XMPP 网关服务的出站 XMPP 通信。  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5061  <br/> |任意：  <br/> • 主管  <br/> • 主任池  <br/> • 前端服务器  <br/> • 前端池  <br/> |边缘服务器的内部接口  <br/> |从您的主管，主管池、 给您边缘服务器的内部接口的前端服务器或前端池的出站 SIP 通信。  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5061  <br/> |边缘服务器的内部接口  <br/> |任意：  <br/> • 主管  <br/> • 主任池  <br/> • 前端服务器  <br/> • 前端池  <br/> |入站的 SIP 通信到导演、 导演池、 前端服务器或前端池从您边缘服务器的内部接口。  <br/> |
|PSOM/MTLS  <br/> |TCP  <br/> |8057  <br/> |任意：  <br/> • 前端服务器  <br/> • 每个前端服务器  <br/>  在前端池 <br/> |边缘服务器的内部接口  <br/> |Web 会议从您前端服务器或每个前端服务器 （如果您有一个前端池） 通讯给您边缘服务器的内部接口。  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5062  <br/> |任意：  <br/> • 前端服务器  <br/> • 前端池  <br/> • 使用此边缘服务器任何高存活力分支装置  <br/> • 使用此边缘服务器所有自动恢复分支服务器  <br/> |边缘服务器的内部接口  <br/> |身份验证的 A / V 从前端服务器或前端池，或高存活力的分支装置或自动恢复分支服务器，使用边缘服务器的用户。  <br/> |
|STUN/MSTURN  <br/> |UDP  <br/> |3478  <br/> |任意  <br/> |边缘服务器的内部接口  <br/> |首选的路径的 A / V 介质内部和外部用户和您高存活力的分支装置或自动恢复分支服务器之间传输。  <br/> |
|STUN/MSTURN  <br/> |TCP  <br/> |443  <br/> |任意  <br/> |边缘服务器的内部接口  <br/> |备用路径 A / V 媒体传输之间内部和外部用户和高存活力的分支装置或自动恢复分支服务器，如果 UDP 通信不起作用。 然后 TCP 用于文件传输和桌面共享。  <br/> |
|HTTPS  <br/> |TCP  <br/> |4443  <br/> |任意：  <br/> • 保存中央管理存储前端服务器  <br/> • 前端池包含中央管理存储  <br/> |边缘服务器的内部接口  <br/> |从中央管理存储的更改复制到边缘服务器存储。  <br/> |
|MTLS  <br/> |TCP  <br/> |50001  <br/> |任意  <br/> |边缘服务器的内部接口  <br/> |集中式日志记录服务控制器使用 Skype 业务服务器管理外壳和集中式日志记录服务的 cmdlet，ClsController 命令行 (ClsController.exe) 或代理 (ClsAgent.exe) 命令和日志收集。  <br/> |
|MTLS  <br/> |TCP  <br/> |50002  <br/> |任意  <br/> |边缘服务器的内部接口  <br/> |集中式日志记录服务控制器使用 Skype 业务服务器管理外壳和集中式日志记录服务的 cmdlet，ClsController 命令行 (ClsController.exe) 或代理 (ClsAgent.exe) 命令和日志收集。  <br/> |
|MTLS  <br/> |TCP  <br/> |50003  <br/> |任意  <br/> |边缘服务器的内部接口  <br/> |集中式日志记录服务控制器使用 Skype 业务服务器管理外壳和集中式日志记录服务的 cmdlet，ClsController 命令行 (ClsController.exe) 或代理 (ClsAgent.exe) 命令和日志收集。  <br/> |
   
### <a name="hardware-load-balancers-for-edge-port-tables"></a>边缘的硬件负载平衡器端口表

我们在其各自的小节中提供了硬件负载平衡器 (HLB) 和边缘端口，因为额外的硬件稍微有点复杂。请参阅下面的表，获得此特定方案的指南：
  
#### <a name="external-port-firewall-summary-table"></a>外部端口防火墙摘要表

源 IP 地址和目标 IP 地址将包含相应的信息，这些信息可供结合 NAT 使用专用 IP 地址的用户，以及使用公用 IP 地址的用户使用。 这将涉及我们[在业务服务器 2015年的 Skype 的边缘服务器方案](scenarios.md)一节中的所有排列。
  
|**角色或协议**|**TCP 或 UDP**|**目标端口或端口范围**|**源 IP 地址**|**目标 IP 地址**|**说明**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|访问/HTTP  <br/> |TCP  <br/> |80  <br/> |边缘服务器访问边缘服务公用 IP 地址  <br/> |任意  <br/> |证书吊销和 CRL 检查和检索。  <br/> |
|访问/DNS  <br/> |TCP  <br/> |53  <br/> |边缘服务器访问边缘服务公用 IP 地址  <br/> |任意  <br/> |通过 TCP 的 DNS 查询。  <br/> |
|访问/DNS  <br/> |UDP  <br/> |53  <br/> |边缘服务器访问边缘服务公用 IP 地址  <br/> |任意  <br/> |通过 UDP 的 DNS 查询。  <br/> |
|A/V/RTP  <br/> |TCP  <br/> |50000-59999  <br/> |边缘服务器 A / V 边缘服务 IP 地址  <br/> |任意  <br/> |这可以用于中继媒体流量。  <br/> |
|A/V/RTP  <br/> |UDP  <br/> |50000-59999  <br/> |边缘服务器 A / V 边缘服务公用 IP 地址  <br/> |任意  <br/> |这可以用于中继媒体流量。  <br/> |
|A/V/件。MSTURN  <br/> |UDP  <br/> |3478  <br/> |边缘服务器 A / V 边缘服务公用 IP 地址  <br/> |任意  <br/> |3478 出站：  <br/> • 通过 Skype 业务服务器用于确定边缘与之通信的服务器的版本。  <br/> • 用于介质边缘服务器之间的通信。  <br/> • 为联盟所必需。  <br/> • 如果您的组织中部署多个边缘池需要。  <br/> |
|A/V/件。MSTURN  <br/> |UDP  <br/> |3478  <br/> |任意  <br/> |边缘服务器 A / V 边缘服务公用 IP 地址  <br/> |在端口 3478 上通过 UDP 进行的候选项 STUN/TURN 协商。  <br/> |
|A/V/件。MSTURN  <br/> |TCP  <br/> |443  <br/> |任意  <br/> |边缘服务器 A / V 边缘服务公用 IP 地址  <br/> |在端口 443 上通过 TCP 进行的候选项 STUN/TURN 协商。  <br/> |
|A/V/件。MSTURN  <br/> |TCP  <br/> |443  <br/> |边缘服务器 A / V 边缘服务公用 IP 地址  <br/> |任意  <br/> |在端口 443 上通过 TCP 进行的候选项 STUN/TURN 协商。  <br/> |
   
#### <a name="internal-port-firewall-summary-table"></a>内部端口防火墙摘要表

|**协议**|**TCP 或 UDP**|**端口**|**源 IP 地址**|**目标 IP 地址**|**说明**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP/MTLS  <br/> |TCP  <br/> |23456  <br/> |运行 XMPP 网关服务的以下任一项：  <br/> • 前端服务器  <br/> • 前端池 VIP 地址运行 XMPP 网关服务  <br/> |边缘服务器的内部接口  <br/> |从您在前端服务器或前端池上运行的 XMPP 网关服务的出站 XMPP 通信。  <br/> |
|HTTPS  <br/> |TCP  <br/> |4443  <br/> |任意：  <br/> • 保存中央管理存储前端服务器  <br/> • 前端池包含中央管理存储  <br/> |边缘服务器的内部接口  <br/> |复制到边缘服务器从中央管理存储的更改。  <br/> |
|PSOM/MTLS  <br/> |TCP  <br/> |8057  <br/> |任意：  <br/> • 前端服务器  <br/> • 在前端池中每个前端服务器  <br/> |边缘服务器的内部接口  <br/> |Web 会议从您前端服务器或每个前端服务器 （如果您有一个前端池） 通讯给您边缘服务器的内部接口。  <br/> |
|STUN/MSTURN  <br/> |UDP  <br/> |3478  <br/> |任意：  <br/> • 前端服务器  <br/> • 在前端池中每个前端服务器  <br/> |边缘服务器的内部接口  <br/> |首选的路径的 A / V 介质内部和外部用户和您高存活力的分支装置或自动恢复分支服务器之间传输。  <br/> |
|STUN/MSTURN  <br/> |TCP  <br/> |443  <br/> |任意：  <br/> • 前端服务器  <br/> • 在池中每个前端服务器  <br/> |边缘服务器的内部接口  <br/> |备用路径 A / V 媒体传输之间内部和外部用户和高存活力的分支装置或自动恢复分支服务器，如果 UDP 通信不起作用。 然后 TCP 用于文件传输和桌面共享。  <br/> |
|MTLS  <br/> |TCP  <br/> |50001  <br/> |任意  <br/> |边缘服务器的内部接口  <br/> |集中式日志记录服务控制器使用 Skype 业务服务器管理外壳和集中式日志记录服务的 cmdlet，ClsController 命令行 (ClsController.exe) 或代理 (ClsAgent.exe) 命令和日志收集。  <br/> |
|MTLS  <br/> |TCP  <br/> |50002  <br/> |任意  <br/> |边缘服务器的内部接口  <br/> |集中式日志记录服务控制器使用 Skype 业务服务器管理外壳和集中式日志记录服务的 cmdlet，ClsController 命令行 (ClsController.exe) 或代理 (ClsAgent.exe) 命令和日志收集。  <br/> |
|MTLS  <br/> |TCP  <br/> |50003  <br/> |任意  <br/> |边缘服务器的内部接口  <br/> |集中式日志记录服务控制器使用 Skype 业务服务器管理外壳和集中式日志记录服务的 cmdlet，ClsController 命令行 (ClsController.exe) 或代理 (ClsAgent.exe) 命令和日志收集。  <br/> |
   
#### <a name="external-interface-virtual-ips"></a>外部接口虚拟 IP

|**角色或协议**|**TCP 或 UDP**|**目标端口或端口范围**|**源 IP 地址**|**目标 IP 地址**|**说明**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP  <br/> |TCP  <br/> |5269  <br/> |任意  <br/> |XMPP 代理服务 （与访问边缘服务共享一个 IP 地址）  <br/> |XMPP 代理服务接受来自定义 XMPP 联合体中的 XMPP 联系人通信。  <br/> |
|XMPP  <br/> |TCP  <br/> |5269  <br/> |XMPP 代理服务 （与访问边缘服务共享一个 IP 地址）  <br/> |任何  <br/> |XMPP 代理服务中的定义的 XMPP 联合体 XMPP 联系人发送通信。  <br/> |
|访问/SIP(TLS)  <br/> |TCP  <br/> |443  <br/> |任意  <br/> |**使用 NAT 的专用 IP:**边缘服务器访问边缘服务 <br/> **公共 IP:**边缘服务器访问边缘服务公用 IP 地址 <br/> |外部用户访问的客户端到服务器 SIP 通信。  <br/> |
|访问/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |任意  <br/> |**使用 NAT 的专用 IP:**边缘服务器访问边缘服务 <br/> **公共 IP:**边缘服务器访问边缘服务公用 IP 地址 <br/> |适用于使用 SIP 的联盟和公共 IM 连接。  <br/> |
|访问/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |**使用 NAT 的专用 IP:**边缘服务器访问边缘服务服务 <br/> **公共 IP:**边缘服务器访问边缘服务公用 IP 地址 <br/> |任意  <br/> |适用于使用 SIP 的联盟和公共 IM 连接。  <br/> |
|Web 会议/PSOM(TLS)  <br/> |TCP  <br/> |443  <br/> |任意  <br/> |**使用 NAT 的专用 IP:**边缘服务器 Web 会议边缘服务 <br/> **公共 IP:**边缘服务器 Web 会议边缘服务公用 IP 地址 <br/> |Web 会议媒体。  <br/> |
|A/V/件。MSTURN  <br/> |UDP  <br/> |3478  <br/> |任意  <br/> |**使用 NAT 的专用 IP:**边缘服务器 A / V 边缘服务 <br/> **公共 IP:**边缘服务器 A / V 边缘服务公用 IP 地址 <br/> |在端口 3478 上通过 UDP 进行的候选项 STUN/TURN 协商。  <br/> |
|A/V/件。MSTURN  <br/> |TCP  <br/> |443  <br/> |任意  <br/> |**使用 NAT 的专用 IP:**边缘服务器 A / V 边缘服务 <br/> **公共 IP:**边缘服务器 A / V 边缘服务公用 IP 地址 <br/> |在端口 443 上通过 TCP 进行的候选项 STUN/TURN 协商。  <br/> |
   
#### <a name="internal-interface-virtual-ips"></a>内部接口虚拟 IP

这里的指南稍有不同。实际上，在 HLB 场合中，我们现在建议在以下情况下，只要有通过内部 VIP 的路由即可：
  
- 如果您使用的 Exchange 2007 或 Exchange 2010 统一消息 (UM)。
    
- 你有使用边缘的旧客户端。
    
下表发出指南，对于这些情况，但否则，您应该能够依靠中央管理存储 (CMS) 通信路由到各个边缘服务器就知道 （这确实需要 CMS 在边缘服务器上保持最新信息，课程的）。
  
|**协议**|**TCP 或 UDP**|**端口**|**源 IP 地址**|**目标 IP 地址**|**说明**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|访问/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |任意：  <br/> • 主管  <br/> • 主管 VIP 地址池  <br/> • 前端服务器  <br/> • 前端池 VIP 地址  <br/> |边缘服务器的内部接口  <br/> |从您的主管主任池前端服务器或前端池 VIP 的 VIP 地址的出站 SIP 通信的地址与您边缘服务器的内部接口。  <br/> |
|访问/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |边缘服务器内部的 VIP 接口  <br/> |任意：  <br/> • 主管  <br/> • 主管 VIP 地址池  <br/> • 前端服务器  <br/> • 前端池 VIP 地址  <br/> |入站 SIP 通信到您的主管主任池 VIP 地址、 前端服务器或从您边缘服务器的内部接口的前端池 VIP 地址。  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5062  <br/> |任意：  <br/> • 前结束服务器 IP 地址  <br/> • 前端池中的 IP 地址  <br/> • 使用此边缘服务器任何高存活力分支装置  <br/> • 使用此边缘服务器所有自动恢复分支服务器  <br/> |边缘服务器的内部接口  <br/> |身份验证的 A / V 从前端服务器或前端池，或高存活力的分支装置或自动恢复分支服务器，使用边缘服务器的用户。  <br/> |
|STUN/MSTURN  <br/> |UDP  <br/> |3478  <br/> |任意  <br/> |边缘服务器的内部接口  <br/> |用于内外部用户间的 A/V 媒体传输的首选路径。  <br/> |
|STUN/MSTURN  <br/> |TCP  <br/> |443  <br/> |任意  <br/> |边缘服务器内部的 VIP 接口  <br/> |在 UDP 通信不起作用的情况下，在内部用户与外部用户之间传输 A/V 媒体的回退路径。然后 TCP 用于文件传输和桌面共享。  <br/> |