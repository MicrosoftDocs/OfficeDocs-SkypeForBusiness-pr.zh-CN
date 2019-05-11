---
title: 边缘服务器环境要求中 Skype 业务服务器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 67435465-b4d0-4e38-8e03-56a60b844a34
description: 摘要： 了解 Business Server Skype 中的边缘服务器的环境要求。
ms.openlocfilehash: ab4f8ea78eaceff87d3c17ec4325776ad1d8a117
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33895616"
---
# <a name="edge-server-environmental-requirements-in-skype-for-business-server"></a>边缘服务器环境要求中 Skype 业务服务器
 
**摘要：** 了解 Business Server Skype 中的边缘服务器的环境要求。
  
大量的规划和准备需要执行之外的业务 Server 边缘服务器环境本身 Skype。 本文中，我们将按照下面的列表回顾需要在组织环境中进行哪些准备工作：
  
- [Topology planning](edge-environmental-requirements.md#TopoPlan)
    
- [DNS planning](edge-environmental-requirements.md#DNSPlan)
    
- [Certificate planning](edge-environmental-requirements.md#CertPlan)
    
- [Port and firewall planning](edge-environmental-requirements.md#PortFirewallPlan)
    
## <a name="topology-planning"></a>拓扑规划
<a name="TopoPlan"> </a>

Skype 的业务 Server 边缘服务器拓扑还可以使用：
  
- 可路由的公用 IP 地址。
    
- 不可路由的专用 IP 地址（如果使用**对称**网络地址转换 (NAT)）。
    
> [!TIP]
> 可以配置边缘服务器的不同的端口的单个 IP 地址使用的每个服务，或者可以使用不同的 IP 地址的每个服务，但使用相同的默认端口 （默认情况下将的 TCP 443）。 在后面的 IP 地址要求部分中，我们会介绍更多信息。 
  
如果选择结合 NAT 使用不可路由的专用 IP 地址，请记住以下几点：
  
- 需要在**所有三个**外部接口上使用可路由的专用 IP 地址。
    
- 需要为传入和传出流量配置**对称** NAT。 对称 NAT 是仅支持可用于业务 Server 边缘服务器与 Skype 的 NAT。
    
- 将 NAT 配置为不要更改传入的源地址。 A / V 边缘服务需要能够接收传入的源地址，要查找的最佳媒体路径。
    
- 边缘服务器需要能够相互通信，从其公共 A / V 边缘 IP 地址。 防火墙需要允许此流量。
    
- NAT 可以**仅**用于扩展的合并边缘服务器如果您使用 DNS 负载平衡。 如果使用硬件负载平衡 (HLB)，那就需要使用**无** NAT 的可公共路由的 IP 地址。
    
您必须没有问题，让您的访问，Web 会议和 A / V 边缘接口路由器或防火墙的单个和扩展执行对称 NAT 后面的合并边缘服务器拓扑 （只要您没有使用硬件负载平衡）。
  
### <a name="summary-of-edge-server-topology-options"></a>边缘服务器拓扑选项摘要

我们有几个的拓扑结构选项可用 Skype 业务 Server 边缘服务器部署：
  
- 使用专用 IP 地址和 NAT 的单一合并边缘
    
- 使用公用 IP 地址的单一合并边缘
    
- 使用专用 IP 地址和 NAT 的扩展合并边缘
    
- 使用公用 IP 地址的扩展合并边缘
    
- 使用硬件负载平衡器的扩展合并边缘
    
为帮助你选择一种拓扑，我们准备了下表，该表提供了每种拓扑可选择哪些选项的摘要：
  
|**拓扑**|**高可用性**|**其他所需的边缘池中的外部边缘服务器的 DNS 记录？**|**用于 Skype 业务服务器会话的边缘故障转移**|**用于 Skype Business Server 联盟会话的边缘故障转移**|
|:-----|:-----|:-----|:-----|:-----|
|使用专用 IP 地址和 NAT 的单一合并边缘  <br/> |否  <br/> |否  <br/> |否  <br/> |否  <br/> |
|使用公用 IP 地址的单一合并边缘  <br/> |否  <br/> |否  <br/> |否  <br/> |否  <br/> |
|使用专用 IP 地址和 NAT 的扩展合并边缘（DNS 负载平衡）  <br/> |是  <br/> |是  <br/> |是  <br/> |Yes&sup1;  <br/> |
|使用公用 IP 地址的扩展合并边缘（DNS 负载平衡）  <br/> |是  <br/> |是  <br/> |是  <br/> |Yes&sup1;  <br/> |
|使用硬件负载平衡器的扩展合并边缘  <br/> |是  <br/> |不支持（每个 VIP 一个 DNS A 记录）  <br/> |是  <br/> |是  <br/> |
   
&sup1;Exchange 统一消息 (UM) 使用 DNS 负载平衡的远程用户故障转移需要 Exchange 2013 或更高版本。
  
### <a name="ip-address-requirements"></a>IP 地址要求

在基本级别，这三种服务需要 IP 地址。访问边缘服务、 Web 会议边缘服务和 A / V 边缘服务。 可以选择使用三个 IP 地址，每种服务对应一个地址，也可以使用一个 IP 地址，并选择将每种服务置于不同的端口（有关这方面的更多信息，可查看[Port and firewall planning](edge-environmental-requirements.md#PortFirewallPlan)）。 对于单一合并边缘环境，差不多就是这样。
  
> [!NOTE]
> 前面说过，你可以选择让所有三种服务使用同一个 IP 地址，但运行于不同的端口。但需要澄清的是，我们不建议这样做。如果客户无法访问你在这种情况下使用的备用端口，他们也就不能获得边缘环境的全部功能。 
  
扩展合并拓扑可能稍微复杂一点，所以我们来看一下列出 IP 地址要求的几张表，同时请牢记，拓扑选择的主要决策点是高可用性和负载平衡。高可用性需求可能影响负载平衡选择（在表的后面，我们将深入讨论）。
  
#### <a name="ip-address-requirements-for-scaled-consolidated-edge-ip-address-per-role"></a>扩展合并边缘的 IP 地址要求（每个角色一个 IP 地址）

|**每个池的边缘服务器的数量**|**DNS 负载平衡所需的 IP 地址数量**|**硬件负载平衡所需的 IP 地址数量**|
|:-----|:-----|:-----|
|2  <br/> |6  <br/> |3（每个 VIP 1 个）6  <br/> |
|3  <br/> |9  <br/> |3（每个 VIP 1 个）9  <br/> |
|4  <br/> |12  <br/> |3（每个 VIP 1 个）12  <br/> |
|5  <br/> |15  <br/> |3（每个 VIP 1 个）15  <br/> |
   
#### <a name="ip-address-requirements-for-scale-consolidated-edge-single-ip-address-for-all-roles"></a>扩展合并边缘的 IP 地址要求（所有角色一个 IP 地址）

|**每个池的边缘服务器的数量**|**DNS 负载平衡所需的 IP 地址数量**|**硬件负载平衡所需的 IP 地址数量**|
|:-----|:-----|:-----|
|2  <br/> |2  <br/> |1（每个 VIP 1 个）2  <br/> |
|3  <br/> |3  <br/> |1（每个 VIP 1 个）3  <br/> |
|4  <br/> |4  <br/> |1（每个 VIP 1 个）4  <br/> |
|5  <br/> |5  <br/> |1（每个 VIP 1 个）5  <br/> |
   
我们来看看规划时要考虑的一些其他事项。
  
- **高可用性**： 如果您需要部署中的高可用性，您应部署至少两个池中的边缘服务器。 值得注意 （尽管拓扑生成器将使您可以添加多达 20，具有测试，或不支持，因此我们建议您不执行的），单个边缘池将支持多达 12 个边缘服务器。 如果您需要多个 12 个边缘服务器，您应为其创建其他边缘池。
    
- **硬件负载平衡**： 建议 DNS 负载平衡于大多数的方案。 硬件负载平衡还支持，当然，但值得注意的是它通过 DNS 负载平衡的单个方案有要求：
    
  - 对 Exchange 2007 或 Exchange 2010 （与没有 SP) 统一消息 (UM) 的外部访问。
    
- **DNS 负载平衡**： 的 UM、 Exchange 2010 SP1 和更高版本是否能够支持的 DNS 负载平衡。 请注意，如果您需要使用 DNS 负载平衡的早期版本的 Exchange 转，它将作用，但此的所有流量将都转到第一台服务器池中，是否不可用，该流量随后将失败。
    
    如果您正在使用的公司联盟，还建议 DNS 负载平衡：
- 业务服务器 2015 的 Skype:
    - Lync Server 2010
    - Lync Server 2013
    - Microsoft Office O365
- 业务服务器 2019 的 Skype:
    - Lync Server 2013
    - Skype for Business Server 2015
    - Microsoft Office 365。
    
## <a name="dns-planning"></a>DNS 规划
<a name="DNSPlan"> </a>

当谈到 Skype 业务 Server 边缘服务器部署时，至关重要正确准备 DNS。 如果正确的记录就位，部署就会容易得多。 但愿你选择了上一节中的拓扑，因为我们将作一下总结，然后列出几张表，这些表概列了适用于那些方案的 DNS 记录。 我们还必须一些[高级边缘服务器 DNS 规划 Skype 业务服务器](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md)以进行更多深入读取，如果您需要它。
  
### <a name="dns-records-for-single-consolidated-edge-server-scenarios"></a>DNS 记录的单个合并边缘服务器方案

这些消息将的 DNS 记录，您将需要的单个边缘服务器使用任一公共 Ip 或专用 Ip 使用 nat。 因为这是示例数据，所以我们将提供示例 IP，便于你更容易地制定出自己的条目：
  
- 内部网络适配器：172.25.33.10（未分配默认网关的地址）
    
    > [!NOTE]
    > 确保存在从包含边缘内部接口到包含业务服务器或 Lync Server 2013 的客户端 （例如，从 172.25.33.0 到 192.168.10.0) 运行 Skype 的服务器的任何网络的网络的路由。 
  
- 外部网络适配器：
    
  - 公用 IP：
    
  - 访问边缘： 131.107.155.10 (这是主，默认网关设置为公共路由器，例如： 131.107.155.1)
    
  - Web 会议边缘： 131.107.155.20 （辅）
    
  - A / V 边缘： 131.107.155.30 （辅）
    
  Web 会议和 A / V 边缘公共 IP 地址附加 （辅） 的 IP 地址的高级部分的 Internet 协议版本 4 (TCP/IPv4) 和本地区域连接属性中的 Internet 协议版本 6 (TCP/IPv6) 的属性Windows Server。
    
  - 专用 IP：
    
  - 访问边缘： 10.45.16.10 (这是主，默认网关设置为路由器，例如： 10.45.16.1)
    
  - Web 会议边缘： 分配 10.45.16.20 （辅）
    
  - A / V 边缘： 分配 10.45.16.30 （辅）
    
Web 会议和 A / V 边缘公共 IP 地址附加 （辅） 的 IP 地址的高级部分的 Internet 协议版本 4 (TCP/IPv4) 和本地区域连接属性中的 Internet 协议版本 6 (TCP/IPv6) 的属性Windows Server。
  
> [!TIP]
>这里有其他可行的配置：
  
- 可以在外部网络适配器上使用一个 IP 地址。 我们不建议这样做，因为，然后您将需要区分你使用不同的端口 （可在 Skype 业务服务器） 的服务，但可能会阻止的备用端口一些防火墙。 有关这方面的更多内容，请参阅[Port and firewall planning](edge-environmental-requirements.md#PortFirewallPlan)一节。
    
- 可以准备三个外部网络适配器，而不是一个，为每个服务分配其中一个服务 IP。为什么这样做？因为这会分隔这些服务，如果出现问题，这更便于排查故障，并可能在你解决问题时，让其他服务继续运行。
    
|**位置**|**类型**|**端口**|**FQDN 或 DNS 记录**|**IP 地址或 FQDN**|**备注**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|外部 DNS  <br/> |A 记录  <br/> |NA  <br/> |sip.contoso.com  <br/> |**公共：** 131.107.155.10 <br/> **专用：** 10.45.16.10 <br/> |访问边缘服务的外部接口。 您将需要一个用于每个 SIP 域与 Skype 的企业用户。  <br/> |
|外部 DNS  <br/> |A 记录  <br/> |NA  <br/> |webcon.contoso.com  <br/> |**公共：** 131.107.155.20 <br/> **专用：** 分配 10.45.16.20 <br/> |Web 会议边缘服务的外部接口。  <br/> |
|外部 DNS  <br/> |A 记录  <br/> |NA  <br/> |av.contoso.com  <br/> |**公共：** 131.107.155.30 <br/> **专用：** 分配 10.45.16.30 <br/> |外部接口 a / V 边缘服务。  <br/> |
|外部 DNS  <br/> |SRV 记录  <br/> |443  <br/> |_sip._tls.contoso.com  <br/> |sip.contoso.com  <br/> |访问边缘服务的外部接口。 为 Business Server、 Lync Server 2013 和 Lync Server 2010 的客户端，用于实现在外部的 Skype 需要此 SRV 记录。 您将需要一个用于与 Skype 的每个域的企业用户。  <br/> |
|外部 DNS  <br/> |SRV 记录  <br/> |5061  <br/> |_sipfederationtls._tcp.contoso.com  <br/> |sip.contoso.com  <br/> |访问边缘服务的外部接口。 称为“允许的 SIP 域”的联盟伙伴的自动 DNS 发现需要此 SRV 记录。 您将需要一个用于与 Skype 的每个域的企业用户。  <br/> |
|内部 DNS  <br/> |A 记录  <br/> |NA  <br/> |sfvedge.contoso.net  <br/> |172.25.33.10  <br/> |合并边缘的内部接口。  <br/> |
   
### <a name="dns-records-for-scaled-dns-and-hardware-edge-server-scenarios"></a>扩展 DNS 和硬件边缘服务器方案的 DNS 记录

这些消息将的 DNS 记录，您将需要的单个边缘服务器使用任一公共 Ip 或专用 Ip 使用 nat。 因为这是示例数据，所以我们将提供示例 IP，便于你更容易地制定出自己的条目：
  
- 内部网络适配器：
    
  - 节点 1：172.25.33.10（未分配默认网关的地址）
    
  - 节点 2：172.25.33.11（未分配默认网关的地址）
    
    > [!NOTE]
    > 确保存在从包含边缘内部接口到包含业务服务器或 Lync Server 2013 的客户端 （例如，从 172.25.33.0 到 192.168.10.0) 运行 Skype 的服务器的任何网络的网络的路由。 
  
- 外部网络适配器：
    
  - 节点 1
    
     - 公用 IP：
    
        - 访问边缘： 131.107.155.10 (这是主，默认网关设置为公共路由器，例如： 131.107.155.1)
    
        - Web 会议边缘： 131.107.155.20 （辅）
    
        - A / V 边缘： 131.107.155.30 （辅）
    
          Web 会议和 A / V 边缘公共 IP 地址附加 （辅） 的 IP 地址的高级部分的 Internet 协议版本 4 (TCP/IPv4) 和本地区域连接属性中的 Internet 协议版本 6 (TCP/IPv6) 的属性Windows Server。
    
    - 专用 IP：
    
         - 访问边缘： 10.45.16.10 (这是主，默认网关设置为路由器，例如： 10.45.16.1)
    
         - Web 会议边缘： 分配 10.45.16.20 （辅）
    
         - A / V 边缘： 分配 10.45.16.30 （辅）
    
      Web 会议和 A / V 边缘公共 IP 地址附加 （辅） 的 IP 地址的高级部分的 Internet 协议版本 4 (TCP/IPv4) 和本地区域连接属性中的 Internet 协议版本 6 (TCP/IPv6) 的属性Windows Server。
    
  - 节点 2
    
    - 公用 IP：
    
      - 访问边缘： 131.107.155.11 (这是主，默认网关设置为公共路由器，例如： 131.107.155.1)
    
      - Web 会议边缘： 131.107.155.21 （辅）
    
      - A / V 边缘： 131.107.155.31 （辅）
    
      Web 会议和 A / V 边缘公共 IP 地址附加 （辅） 的 IP 地址的高级部分的 Internet 协议版本 4 (TCP/IPv4) 和本地区域连接属性中的 Internet 协议版本 6 (TCP/IPv6) 的属性Windows Server。
    
  - 专用 IP：
    
    - 访问边缘： 10.45.16.11 (这是主，默认网关设置为路由器，例如： 10.45.16.1)
    
    - Web 会议边缘： 10.45.16.21 （辅）
    
    - A / V 边缘： 10.45.16.31 （辅）
    
      Web 会议和 A / V 边缘公共 IP 地址附加 （辅） 的 IP 地址的高级部分的 Internet 协议版本 4 (TCP/IPv4) 和本地区域连接属性中的 Internet 协议版本 6 (TCP/IPv6) 的属性Windows Server。
    
这里有其他可行的配置：
  
- 可以在外部网络适配器上使用一个 IP 地址。 我们不建议这样做，因为，然后您将需要区分你使用不同的端口 （可在 Skype 业务服务器） 的服务，但可能会阻止的备用端口一些防火墙。 有关这方面的更多内容，请参阅[Port and firewall planning](edge-environmental-requirements.md#PortFirewallPlan)一节。
    
- 可以准备三个外部网络适配器，而不是一个，为每个服务分配其中一个服务 IP。为什么这样做？因为这会分隔这些服务，如果出现问题，这更便于排查故障，并可能在你解决问题时，让其他服务继续运行。
    
|**位置**|**类型**|**端口**|**FQDN 或 DNS 记录**|**IP 地址或 FQDN**|**备注**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|外部 DNS  <br/> |A 记录  <br/> |NA  <br/> |sip.contoso.com  <br/> |**公共：** 131.107.155.10 和 131.107.155.11 <br/> **专用：** 10.45.16.10 和 10.45.16.11 <br/> |访问边缘服务的外部接口。 您将需要一个用于每个 SIP 域与 Skype 的企业用户。  <br/> |
|外部 DNS  <br/> |A 记录  <br/> |NA  <br/> |webcon.contoso.com  <br/> |**公共：** 131.107.155.20 和 131.107.155.21 <br/> **专用：** 分配 10.45.16.20 和 10.45.16.21 <br/> |Web 会议边缘服务的外部接口。  <br/> |
|外部 DNS  <br/> |A 记录  <br/> |NA  <br/> |av.contoso.com  <br/> |**公共：** 131.107.155.30 和 131.107.155.31 <br/> **专用：** 分配 10.45.16.30 和 10.45.16.31 <br/> |外部接口 a / V 边缘服务。  <br/> |
|外部 DNS  <br/> |SRV 记录  <br/> |443  <br/> |_sip._tls.contoso.com  <br/> |sip.contoso.com  <br/> |访问边缘服务的外部接口。 为 Business Server、 Lync Server 2013 和 Lync Server 2010 的客户端，用于实现在外部的 Skype 需要此 SRV 记录。 您将需要一个用于与 Skype 的每个域的业务。  <br/> |
|外部 DNS  <br/> |SRV 记录  <br/> |5061  <br/> |_sipfederationtls._tcp.contoso.com  <br/> |sip.contoso.com  <br/> |访问边缘服务的外部接口。 称为“允许的 SIP 域”的联盟伙伴的自动 DNS 发现需要此 SRV 记录。 您将需要一个用于与 Skype 的每个域的业务。  <br/> |
|内部 DNS  <br/> |A 记录  <br/> |NA  <br/> |sfvedge.contoso.net  <br/> |172.25.33.10 和 172.25.33.11  <br/> |合并边缘的内部接口。  <br/> |
   
### <a name="dns-record-for-federation-all-scenarios"></a>联盟的 DNS 记录（所有方案）

|**位置**|**类型**|**端口**|**FQDN**|**FQDN 主机记录**|**备注**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|外部 DNS  <br/> |SRV  <br/> |5061  <br/> |_sipfederationtls_tcp.contoso.com  <br/> |sip.contoso.com  <br/> |SIP 访问边缘外部接口所需的自动 DNS 发现。 由其他潜在的联盟伙伴使用。 这也称为“允许的 SIP 域”。 您将需要下列任一每个 SIP 域与 Skype 的企业用户。  <br/><br/> **注意：** 移动性和推送通知交换所需要此 SRV 记录。 <br/> |
   
### <a name="dns-records-for-extensible-messaging-and-presence-protocol"></a>可扩展消息传递和状态协议的 DNS 记录

|**位置**|**类型**|**端口**|**FQDN**|**IP 地址或 FQDN 主机记录**|**注释**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|外部 DNS  <br/> |SRV  <br/> |5269  <br/> |_xmpp-server._tcp.contoso.com  <br/> |xmpp.contoso.com  <br/> |访问边缘服务或边缘池上的 XMPP 代理接口。 您需要重复上述过程所需的所有内部 SIP 域与 Skype 业务 Server 启用用户，通过允许与 XMPP 联系人的联系人的位置：  <br/> • 全局策略  <br/> • 启用了用户的站点策略  <br/> • 业务服务器应用到 Skype 的用户策略启用用户  <br/> 在 XMPP 联盟用户策略中，还需要配置允许的 XMPP 策略。  <br/> |
|外部 DNS  <br/> |SRV  <br/> |A  <br/> |xmpp.contoso.com  <br/> |承载 XMPP 代理服务的边缘池的边缘服务器上的访问边缘服务的 IP 地址  <br/> |这点到上边缘服务器或边缘池的访问边缘服务承载 XMPP 代理服务。 通常，你创建的 SRV 记录将指向主机（A 或 AAAA）记录。  <br/> |
   
> [!NOTE]
> XMPP 网关和代理中的业务服务器 2015 Skype 可用，但业务服务器 2019年不再支持在 Skype。 有关详细信息，请参阅[迁移 XMPP 联盟](../../../SfBServer2019/migration/migrating-xmpp-federation.md)。

## <a name="certificate-planning"></a>证书规划
<a name="CertPlan"> </a>

Skype 业务 server 使用证书实现同时服务器之间以及从服务器到客户端的安全的加密通信。 正如你料想的那样，证书需要服务器的 DNS 记录与证书中的任何使用者名称 (SN) 和使用者替代名称 (SAN) 匹配。 在规划阶段，现在这需要花些功夫，确保在 DNS 中注册对应于证书 SN 和 SAN 条目的正确 FQDN。
  
我们将分别讨论外部和内部证书需求，然后查看提供两种需求的表。
  
### <a name="external-certificates"></a>外部证书

至少需要提供的公共证书颁发机构 (CA) 分配给您的外部边缘服务器接口的证书。 我们不能建议特定 CA，但我们尚未的 Ca，[统一通信证书伙伴](https://support.microsoft.com/en-us/kb/929395)可采取看以查看是否列出您首选的 CA 的列表。
  
你什么时候需要向 CA 提出申请，索要这份公共证书，如何提出申请？有几种方式可以完成申请：
  
- 您可以通过 Skype 安装 Business Server，然后选择边缘服务器部署。 业务 Server 部署向导的 Skype 将具有一个步骤以生成证书请求，其中您可以将发送给您所选 CA。
    
- 此外可以使用 Windows PowerShell 命令生成此请求中，如果这是与您的业务需求或部署策略的详细内嵌。
    
- 最后，您的 CA 可能具有自己的提交过程中，可能还包括 Windows PowerShell 或另一种方法。 这种情况下，除了此处提供的供你参考的信息外，你还需要依靠他们的文档。
    
您已将证书后，您需要继续操作，并将其分配给 Skype 中的这些服务的业务服务器：
  
- 访问边缘服务接口
    
- Web 会议边缘服务接口
    
- 音频/视频身份验证服务 (不要将此混淆与 A / V 边缘服务的不使用证书进行加密音频和视频流)
    
> [!IMPORTANT]
> 所有边缘服务器 （如果它们属于相同的边缘服务器池） 都需要具有相同的私钥的媒体中继身份验证服务与完全相同的证书。 
  
### <a name="internal-certificates"></a>内部证书

对于内部边缘服务器接口，您可以使用公用证书从公共 CA 或从组织的内部 CA 颁发的证书。 对于内部证书，需要记住的一点是，它使用 SN 条目，没有 SAN 条目，因此你根本不用关心内部证书的 SAN。
  
### <a name="required-certificates-table"></a>所需证书表

这里有一个表可帮助你申请证书。此处的 FQDN 条目只适用于示例域。你需要根据自己的专用域和公共域提出申请，不过这里有我们所用内容的指南：
  
- contoso<span></span>.com： 公共 FQDN
    
- fabrikam<span></span>.com： 第二个公共 （作为演示了要请求如果您有多个 SIP 域添加） 的 FQDN
    
- Contoso<span></span>.net： 内部域
    
#### <a name="edge-certificate-table"></a>边缘证书表

无论是否正在制作了一个边缘服务器或边缘池，这是您将需要为您的证书：
  
|**组件**|**使用者名称 (SN)**|**使用者替代名称 (SAN)/顺序**|**注释**|
|:-----|:-----|:-----|:-----|
|外部边缘  <br/> |sip.contoso.com  <br/> |sip.contoso.com  <br/> webcon.contoso.com  <br/> sip.fabrikam.com  <br/> |这是需要从公共 CA 申请获得的证书。需要将其分配给以下服务的外部边缘接口：<br/> • 访问边缘  <br/> • Web 会议边缘  <br/> • 音频/视频身份验证  <br/> <br/>San 会自动添加到您的证书请求，并因此后的证书提交请求，基于此部署拓扑生成器中定义的内容，好的消息。 你只需要添加任何其他 SIP 域的 SAN 条目或需要支持的其他条目。 为什么此例中会复制 sip.contoso.com？ 这也是自动发生的，为了让系统正常工作，需要如此。  <br/><br/> **注意：** 此证书还可用于公共即时消息连接。 对此，你无需进行任何其他操作，但是在本文档以前的版本中，这作为单独的表列出，而现在不是。 <br/> |
|内部边缘  <br/> |sfbedge.contoso.com  <br/> |NA  <br/> |可以从公共 CA 或内部 CA 获得此证书。该证书需要包含服务器 EKU（增强型密钥使用），你要将其分配给内部边缘界面。  <br/> |
   
如果可扩展消息传递和状态协议 (XMPP) 需要证书，该证书看上去与上面的外部边缘表条目完全相同，但是有以下两条额外的 SAN 条目：
  
- xmpp。<span> </span>contoso<span></span>.com
    
- \*.contoso<span></span>.com
    
请记住，当前 XMPP 仅支持 Skype 业务服务器的 Google Talk，如果您希望或需要使用的任何其他操作，您需要与第三方供应商涉及确认该功能。
  
## <a name="port-and-firewall-planning"></a>端口和防火墙规划
<a name="PortFirewallPlan"> </a>

获取您规划右端口和防火墙的 Skype 业务 Server 边缘服务器部署可以保存您天或数周的故障排除和压力。 因此，我们会列出几张表，这些表指出了我们的协议用途，以及对于 NAT 和公共 IP 方案，需要开放哪些端口，包括入站和出站。 我们还针对硬件负载平衡方案 (HLB) 提供了单独的表，以及这方面的进一步指导。 对于从该处的更多读取，我们还具有可以签出的特定部署问题进行一些[Skype 业务服务器中的边缘服务器方案](scenarios.md)。
  
### <a name="general-protocol-usage"></a>常规协议用途

在查看外部和内部防火墙的摘要表之前，让我们同样考虑下面的表：
  
|**音频/视频传输**|**使用**|
|:-----|:-----|
|UDP  <br/> |音频和视频的首选传输层协议。  <br/> |
|TCP  <br/> |音频和视频的回退传输层协议。  <br/> 应用程序共享到 Skype Business Server、 Lync Server 2013 和 Lync Server 2010 所需的传输层协议。  <br/> 文件传输到 Business Server、 Lync Server 2013 和 Lync Server 2010 的 Skype 所需的传输层协议。  <br/> |
   
### <a name="external-port-firewall-summary-table"></a>外部端口防火墙摘要表

源 IP 地址和目标 IP 地址将包含相应的信息，这些信息可供结合 NAT 使用专用 IP 地址的用户，以及使用公用 IP 地址的用户使用。 这将涵盖我们[Skype 业务服务器中的边缘服务器方案](scenarios.md)一节中的所有排列。
  
|**角色或协议**|**TCP 或 UDP**|**目标端口或端口范围**|**源 IP 地址**|**目标 IP 地址**|**备注**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP  <br/> 不支持在 Skype 业务服务器 2019 |TCP  <br/> |5269  <br/> |任意  <br/> |XMPP 代理服务 （与访问边缘服务共享 IP 地址  <br/> |XMPP 代理服务接受来自所定义的 XMPP 联盟中 XMPP 联系人的流量。  <br/> |
|访问/HTTP  <br/> |TCP  <br/> |80  <br/> |**使用 NAT 的专用 IP:** 边缘服务器访问边缘服务 <br/> **公用 IP:** 边缘服务器访问边缘服务公共 IP 地址 <br/> |任意  <br/> |证书吊销和 CRL 检查和检索。  <br/> |
|访问/DNS  <br/> |TCP  <br/> |53  <br/> |**使用 NAT 的专用 IP:** 边缘服务器访问边缘服务 <br/> **公用 IP:** 边缘服务器访问边缘服务公共 IP 地址 <br/> |任意  <br/> |通过 TCP 的 DNS 查询。  <br/> |
|访问/DNS  <br/> |UDP  <br/> |53  <br/> |**使用 NAT 的专用 IP:** 边缘服务器访问边缘服务 <br/> **公用 IP:** 边缘服务器访问边缘服务公共 IP 地址 <br/> |任意  <br/> |通过 UDP 的 DNS 查询。  <br/> |
|访问/SIP(TLS)  <br/> |TCP  <br/> |443  <br/> |任意   <br/> |**使用 NAT 的专用 IP:** 边缘服务器访问边缘服务 <br/> **公用 IP:** 边缘服务器访问边缘服务公共 IP 地址 <br/> |外部用户访问的客户端到服务器 SIP 通信。  <br/> |
|访问/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |任意  <br/> |**使用 NAT 的专用 IP:** 边缘服务器访问边缘服务 <br/> **公用 IP:** 边缘服务器访问边缘服务公共 IP 地址 <br/> |适用于使用 SIP 的联盟和公共 IM 连接。  <br/> |
|访问/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |**使用 NAT 的专用 IP:** 边缘服务器访问边缘服务 <br/> **公用 IP:** 边缘服务器访问边缘服务公共 IP 地址 <br/> |任意  <br/> |适用于使用 SIP 的联盟和公共 IM 连接。  <br/> |
|Web 会议/PSOM(TLS)  <br/> |TCP  <br/> |443  <br/> |任意   <br/> |**使用 NAT 的专用 IP:** 边缘服务器 Web 会议边缘服务 <br/> **公用 IP:** 边缘服务器 Web 会议边缘服务公共 IP 地址 <br/> |Web 会议媒体。  <br/> |
|A/V/RTP  <br/> |TCP  <br/> |50000-59999  <br/> |**使用 NAT 的专用 IP:** 边缘服务器 A / V 边缘服务 <br/> **公用 IP:** 边缘服务器 A / V 边缘服务公共 IP 地址 <br/> |任意  <br/> |这可以用于中继媒体流量。  <br/> |
|A/V/RTP  <br/> |UDP  <br/> |50000-59999  <br/> |**使用 NAT 的专用 IP:** 边缘服务器 A / V 边缘服务 <br/> **公用 IP:** 边缘服务器 A / V 边缘服务公共 IP 地址 <br/> |任意  <br/> |这可以用于中继媒体流量。  <br/> |
|A/V/STUN.MSTURN  <br/> |UDP  <br/> |3478  <br/> |**使用 NAT 的专用 IP:** 边缘服务器 A / V 边缘服务 <br/> **公用 IP:** 边缘服务器 A / V 边缘服务公共 IP 地址 <br/> |任意  <br/> |3478 出站：  <br/> • Skype 业务服务器用来确定它与之通信的边缘服务器的版本。  <br/> • 用于边缘服务器之间的媒体流量。  <br/> • 与 Lync Server 2010 的联盟时必需。  <br/> • 如果贵组织中部署多个边缘池需要。  <br/> |
|A/V/STUN.MSTURN  <br/> |UDP  <br/> |3478  <br/> |任意  <br/> |**使用 NAT 的专用 IP:** 边缘服务器 A / V 边缘服务 <br/> **公用 IP:** 边缘服务器 A / V 边缘服务公共 IP 地址 <br/> |在端口 3478 上通过 UDP 进行的候选项 STUN/TURN 协商。  <br/> |
|A/V/STUN.MSTURN  <br/> |TCP  <br/> |443  <br/> |任意   <br/> |**使用 NAT 的专用 IP:** 边缘服务器 A / V 边缘服务 <br/> **公用 IP:** 边缘服务器 A / V 边缘服务公共 IP 地址 <br/> |在端口 443 上通过 TCP 进行的候选项 STUN/TURN 协商。  <br/> |
|A/V/STUN.MSTURN  <br/> |TCP  <br/> |443  <br/> |**使用 NAT 的专用 IP:** 边缘服务器 A / V 边缘服务 <br/> **公用 IP:** 边缘服务器 A / V 边缘服务公共 IP 地址 <br/> |任意  <br/> |在端口 443 上通过 TCP 进行的候选项 STUN/TURN 协商。  <br/> |
   
### <a name="internal-port-firewall-summary-table"></a>内部端口防火墙摘要表

|**协议**|**TCP 或 UDP**|**端口**|**源 IP 地址**|**目标 IP 地址**|**备注**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP/MTLS  <br/> |TCP  <br/> |23456  <br/> |运行 XMPP 网关服务的以下任一项：  <br/> • 前端服务器  <br/> • 前端池  <br/> |边缘服务器内部接口  <br/> |从前端服务器或前端池上运行 XMPP 网关服务的出站 XMPP 流量。  <br/> **注意：** XMPP 网关和代理中的业务服务器 2015 Skype 可用，但业务服务器 2019年不再支持在 Skype。 有关详细信息，请参阅[迁移 XMPP 联盟](../../../SfBServer2019/migration/migrating-xmpp-federation.md)。|
|SIP/MTLS  <br/> |TCP  <br/> |5061  <br/> |任意：  <br/> • 控制器  <br/> • 控制器池  <br/> • 前端服务器  <br/> • 前端池  <br/> |边缘服务器内部接口  <br/> |从控制器，控制器池、 前端服务器或前端池到边缘服务器内部接口的出站 SIP 流量。  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5061  <br/> |边缘服务器内部接口  <br/> |任意：  <br/> • 控制器  <br/> • 控制器池  <br/> • 前端服务器  <br/> • 前端池  <br/> |入站到控制器、 控制器池、 前端服务器或前端池的 SIP 流量从边缘服务器内部接口。  <br/> |
|PSOM/MTLS  <br/> |TCP  <br/> |8057  <br/> |任意：  <br/> • 前端服务器  <br/> • 每台前端服务器  <br/>  在前端池 <br/> |边缘服务器内部接口  <br/> |从 web 会议流量在前端服务器或每个前端服务器 （如果您具有一个前端池） 到您的边缘服务器内部接口。  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5062  <br/> |任意：  <br/> • 前端服务器  <br/> • 前端池  <br/> ？ 使用此边缘服务器的任何 Survivable Branch Appliance  <br/> ？ 使用此边缘服务器的任何 Survivable Branch Server  <br/> |边缘服务器内部接口  <br/> |身份验证的 A / V 用户从前端服务器或前端池，或 Survivable Branch Appliance 或 Survivable Branch Server，使用您的边缘服务器。  <br/> |
|STUN/MSTURN  <br/> |UDP  <br/> |3478  <br/> |任意  <br/> |边缘服务器内部接口  <br/> |首选的路径为 A / V 媒体传输内部和外部用户与您的 Survivable Branch Appliance 或 Survivable Branch Server 之间。  <br/> |
|STUN/MSTURN  <br/> |TCP  <br/> |443  <br/> |任意   <br/> |边缘服务器内部接口  <br/> |回退路径，a / V 媒体传输之间内部和外部用户和您的 Survivable Branch Appliance 或 Survivable Branch Server，如果 UDP 通信不起作用。 然后 TCP 用于文件传输和桌面共享。  <br/> |
|HTTPS  <br/> |TCP  <br/> |端口 4443  <br/> |任意：  <br/> • 包含中央管理存储的前端服务器  <br/> • 包含中央管理存储的前端池  <br/> |边缘服务器内部接口  <br/> |从中央管理存储到边缘服务器的更改复制。  <br/> |
|MTLS  <br/> |TCP  <br/> |50001  <br/> |任意  <br/> |边缘服务器内部接口  <br/> |使用 Skype 业务 Server 命令行管理程序和 Centralized Logging Service cmdlet、 ClsController 命令行 (ClsController.exe) 或代理 (ClsAgent.exe) 命令和日志集合的集中日志记录服务控制器。  <br/> |
|MTLS  <br/> |TCP  <br/> |50002  <br/> |任意  <br/> |边缘服务器内部接口  <br/> |使用 Skype 业务 Server 命令行管理程序和 Centralized Logging Service cmdlet、 ClsController 命令行 (ClsController.exe) 或代理 (ClsAgent.exe) 命令和日志集合的集中日志记录服务控制器。  <br/> |
|MTLS  <br/> |TCP  <br/> |50003  <br/> |任意  <br/> |边缘服务器内部接口  <br/> |使用 Skype 业务 Server 命令行管理程序和 Centralized Logging Service cmdlet、 ClsController 命令行 (ClsController.exe) 或代理 (ClsAgent.exe) 命令和日志集合的集中日志记录服务控制器。  <br/> |
   
### <a name="hardware-load-balancers-for-edge-port-tables"></a>边缘的硬件负载平衡器端口表

我们在其各自的小节中提供了硬件负载平衡器 (HLB) 和边缘端口，因为额外的硬件稍微有点复杂。请参阅下面的表，获得此特定方案的指南：
  
#### <a name="external-port-firewall-summary-table"></a>外部端口防火墙摘要表

源 IP 地址和目标 IP 地址将包含相应的信息，这些信息可供结合 NAT 使用专用 IP 地址的用户，以及使用公用 IP 地址的用户使用。 这将涵盖我们[Skype 业务服务器中的边缘服务器方案](scenarios.md)一节中的所有排列。
  
|**角色或协议**|**TCP 或 UDP**|**目标端口或端口范围**|**源 IP 地址**|**目标 IP 地址**|**备注**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|访问/HTTP  <br/> |TCP  <br/> |80  <br/> |边缘服务器访问边缘服务公共 IP 地址  <br/> |任意  <br/> |证书吊销和 CRL 检查和检索。  <br/> |
|访问/DNS  <br/> |TCP  <br/> |53  <br/> |边缘服务器访问边缘服务公共 IP 地址  <br/> |任意  <br/> |通过 TCP 的 DNS 查询。  <br/> |
|访问/DNS  <br/> |UDP  <br/> |53  <br/> |边缘服务器访问边缘服务公共 IP 地址  <br/> |任意  <br/> |通过 UDP 的 DNS 查询。  <br/> |
|A/V/RTP  <br/> |TCP  <br/> |50000-59999  <br/> |边缘服务器 A / V 边缘服务的 IP 地址  <br/> |任意  <br/> |这可以用于中继媒体流量。  <br/> |
|A/V/RTP  <br/> |UDP  <br/> |50000-59999  <br/> |边缘服务器 A / V 边缘服务公共 IP 地址  <br/> |任意  <br/> |这可以用于中继媒体流量。  <br/> |
|A/V/STUN.MSTURN  <br/> |UDP  <br/> |3478  <br/> |边缘服务器 A / V 边缘服务公共 IP 地址  <br/> |任意  <br/> |3478 出站：  <br/> • Skype 业务服务器用来确定它与之通信的边缘服务器的版本。  <br/> • 用于边缘服务器之间的媒体流量。  <br/> • 联盟时必需。  <br/> • 如果贵组织中部署多个边缘池需要。  <br/> |
|A/V/STUN.MSTURN  <br/> |UDP  <br/> |3478  <br/> |任意  <br/> |边缘服务器 A / V 边缘服务公共 IP 地址  <br/> |在端口 3478 上通过 UDP 进行的候选项 STUN/TURN 协商。  <br/> |
|A/V/STUN.MSTURN  <br/> |TCP  <br/> |443  <br/> |任意   <br/> |边缘服务器 A / V 边缘服务公共 IP 地址  <br/> |在端口 443 上通过 TCP 进行的候选项 STUN/TURN 协商。  <br/> |
|A/V/STUN.MSTURN  <br/> |TCP  <br/> |443  <br/> |边缘服务器 A / V 边缘服务公共 IP 地址  <br/> |任意  <br/> |在端口 443 上通过 TCP 进行的候选项 STUN/TURN 协商。  <br/> |
   
#### <a name="internal-port-firewall-summary-table"></a>内部端口防火墙摘要表

|**协议**|**TCP 或 UDP**|**端口**|**源 IP 地址**|**目标 IP 地址**|**注释**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP/MTLS  <br/> |TCP  <br/> |23456  <br/> |运行 XMPP 网关服务的以下任一项：  <br/> • 前端服务器  <br/> • 前端池运行 XMPP 网关服务的 VIP 地址  <br/> |边缘服务器内部接口  <br/> |从前端服务器或前端池上运行 XMPP 网关服务的出站 XMPP 流量。  <br/><br/> **注意：** XMPP 网关和代理中的业务服务器 2015 Skype 可用，但业务服务器 2019年不再支持在 Skype。 有关详细信息，请参阅[迁移 XMPP 联盟](../../../SfBServer2019/migration/migrating-xmpp-federation.md)。 |
|HTTPS  <br/> |TCP  <br/> |端口 4443  <br/> |任意：  <br/> • 包含中央管理存储的前端服务器  <br/> • 包含中央管理存储的前端池  <br/> |边缘服务器内部接口  <br/> |从中央管理存储到边缘服务器的更改复制。  <br/> |
|PSOM/MTLS  <br/> |TCP  <br/> |8057  <br/> |任意：  <br/> • 前端服务器  <br/> • 前端池中每个前端服务器  <br/> |边缘服务器内部接口  <br/> |从 web 会议流量在前端服务器或每个前端服务器 （如果您具有一个前端池） 到您的边缘服务器内部接口。  <br/> |
|STUN/MSTURN  <br/> |UDP  <br/> |3478  <br/> |任意：  <br/> • 前端服务器  <br/> • 前端池中每个前端服务器  <br/> |边缘服务器内部接口  <br/> |首选的路径为 A / V 媒体传输内部和外部用户与您的 Survivable Branch Appliance 或 Survivable Branch Server 之间。  <br/> |
|STUN/MSTURN  <br/> |TCP  <br/> |443  <br/> |任意：  <br/> • 前端服务器  <br/> • 池中每个前端服务器  <br/> |边缘服务器内部接口  <br/> |回退路径，a / V 媒体传输之间内部和外部用户和您的 Survivable Branch Appliance 或 Survivable Branch Server，如果 UDP 通信不起作用。 然后 TCP 用于文件传输和桌面共享。  <br/> |
|MTLS  <br/> |TCP  <br/> |50001  <br/> |任意  <br/> |边缘服务器内部接口  <br/> |使用 Skype 业务 Server 命令行管理程序和 Centralized Logging Service cmdlet、 ClsController 命令行 (ClsController.exe) 或代理 (ClsAgent.exe) 命令和日志集合的集中日志记录服务控制器。  <br/> |
|MTLS  <br/> |TCP  <br/> |50002  <br/> |任意  <br/> |边缘服务器内部接口  <br/> |使用 Skype 业务 Server 命令行管理程序和 Centralized Logging Service cmdlet、 ClsController 命令行 (ClsController.exe) 或代理 (ClsAgent.exe) 命令和日志集合的集中日志记录服务控制器。  <br/> |
|MTLS  <br/> |TCP  <br/> |50003  <br/> |任意  <br/> |边缘服务器内部接口  <br/> |使用 Skype 业务 Server 命令行管理程序和 Centralized Logging Service cmdlet、 ClsController 命令行 (ClsController.exe) 或代理 (ClsAgent.exe) 命令和日志集合的集中日志记录服务控制器。  <br/> |
   
#### <a name="external-interface-virtual-ips"></a>外部接口虚拟 IP

|**角色或协议**|**TCP 或 UDP**|**目标端口或端口范围**|**源 IP 地址**|**目标 IP 地址**|**备注**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP  <br/> Skype 的业务服务器 2019年中不支持 |TCP  <br/> |5269  <br/> |任意  <br/> |XMPP 代理服务 （与访问边缘服务共享 IP 地址）  <br/> |XMPP 代理服务接受来自所定义的 XMPP 联盟中 XMPP 联系人的流量。  <br/> |
|XMPP  <br/>Skype 的业务服务器 2019年中不支持 |TCP  <br/> |5269  <br/> |XMPP 代理服务 （与访问边缘服务共享 IP 地址）  <br/> |任意  <br/> |XMPP 代理服务发送来自所定义的 XMPP 联盟中 XMPP 联系人的流量。  <br/> |
|访问/SIP(TLS)  <br/> |TCP  <br/> |443  <br/> |任意   <br/> |**使用 NAT 的专用 IP:** 边缘服务器访问边缘服务 <br/> **公用 IP:** 边缘服务器访问边缘服务公共 IP 地址 <br/> |外部用户访问的客户端到服务器 SIP 通信。  <br/> |
|访问/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |任意  <br/> |**使用 NAT 的专用 IP:** 边缘服务器访问边缘服务 <br/> **公用 IP:** 边缘服务器访问边缘服务公共 IP 地址 <br/> |适用于使用 SIP 的联盟和公共 IM 连接。  <br/> |
|访问/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |**使用 NAT 的专用 IP:** 边缘服务器访问边缘服务 <br/> **公用 IP:** 边缘服务器访问边缘服务公共 IP 地址 <br/> |任意  <br/> |适用于使用 SIP 的联盟和公共 IM 连接。  <br/> |
|Web 会议/PSOM(TLS)  <br/> |TCP  <br/> |443  <br/> |任意   <br/> |**使用 NAT 的专用 IP:** 边缘服务器 Web 会议边缘服务 <br/> **公用 IP:** 边缘服务器 Web 会议边缘服务公共 IP 地址 <br/> |Web 会议媒体。  <br/> |
|A/V/STUN.MSTURN  <br/> |UDP  <br/> |3478  <br/> |任意  <br/> |**使用 NAT 的专用 IP:** 边缘服务器 A / V 边缘服务 <br/> **公用 IP:** 边缘服务器 A / V 边缘服务公共 IP 地址 <br/> |在端口 3478 上通过 UDP 进行的候选项 STUN/TURN 协商。  <br/> |
|A/V/STUN.MSTURN  <br/> |TCP  <br/> |443  <br/> |任意   <br/> |**使用 NAT 的专用 IP:** 边缘服务器 A / V 边缘服务 <br/> **公用 IP:** 边缘服务器 A / V 边缘服务公共 IP 地址 <br/> |在端口 443 上通过 TCP 进行的候选项 STUN/TURN 协商。  <br/> |
   
#### <a name="internal-interface-virtual-ips"></a>内部接口虚拟 IP

这里的指南稍有不同。实际上，在 HLB 场合中，我们现在建议在以下情况下，只要有通过内部 VIP 的路由即可：
  
- 如果您使用 Exchange 2007 或 Exchange 2010 统一消息 (UM)。
    
- 你有使用边缘的旧客户端。
    
确实为下表提供了指导对于这些方案，但否则，您应该能够取决于中央管理存储 (CMS) 通信路由到感知的单个边缘服务器 （这确实需要 CMS 边缘服务器上保持最新信息的课程 （英文））。
  
|**协议**|**TCP 或 UDP**|**端口**|**源 IP 地址**|**目标 IP 地址**|**备注**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|访问/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |任意：  <br/> • 控制器  <br/> • 控制器池 VIP 地址  <br/> • 前端服务器  <br/> • 前端池 VIP 地址  <br/> |边缘服务器内部接口  <br/> |从控制器，控制器池 VIP 地址，前端服务器或前端池 VIP 的出站 SIP 流量地址到边缘服务器内部接口。  <br/> |
|访问/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |边缘服务器内部 VIP 接口  <br/> |任意：  <br/> • 控制器  <br/> • 控制器池 VIP 地址  <br/> • 前端服务器  <br/> • 前端池 VIP 地址  <br/> |入站 SIP 流量到 Director，Director 池 VIP 地址、 前端服务器或从边缘服务器内部接口的前端池 VIP 地址。  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5062  <br/> |任意：  <br/> • 前端服务器 IP 地址  <br/> • 前端池的 IP 地址  <br/> ？ 使用此边缘服务器的任何 Survivable Branch Appliance  <br/> ？ 使用此边缘服务器的任何 Survivable Branch Server  <br/> |边缘服务器内部接口  <br/> |身份验证的 A / V 用户从前端服务器或前端池，或 Survivable Branch Appliance 或 Survivable Branch Server，使用您的边缘服务器。  <br/> |
|STUN/MSTURN  <br/> |UDP  <br/> |3478  <br/> |任意  <br/> |边缘服务器内部接口  <br/> |用于内外部用户间的 A/V 媒体传输的首选路径。  <br/> |
|STUN/MSTURN  <br/> |TCP  <br/> |443  <br/> |任意   <br/> |边缘服务器内部 VIP 接口  <br/> |在 UDP 通信不起作用的情况下，在内部用户与外部用户之间传输 A/V 媒体的回退路径。然后 TCP 用于文件传输和桌面共享。  <br/> |
